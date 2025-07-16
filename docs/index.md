# Port Facility Management Software (SORAT)
## Schedule On Route And Transit - Project Documentation

### Executive Summary

This document outlines the foundational architecture and scope for the development of SORAT (Schedule On Route And Transit), a comprehensive Electronic Traffic Management System Platform designed to revolutionize port facility operations. The system aims to digitize and streamline the movement of trucks, containers, and cargo through port facilities, ensuring efficient, secure, and transparent operations.

### Project Overview

**Project Name:** SORAT - Electronic Traffic Management System Platform  
**Client:** Port Management Authority in collaboration with Intrass Limited  
**Objective:** Upgrade existing port traffic management to a fully digital, IoT-enabled system with real-time tracking, automated notifications, and comprehensive stakeholder management.

### 1. System Scope and Objectives

#### 1.1 Primary Objectives
- **Digitize Port Access Control:** Implement a schedule-based system where no truck can access port areas without prior scheduling
- **Real-time Vehicle Tracking:** Monitor all containerized and non-containerized cargo movements
- **Stakeholder Integration:** Seamlessly connect all port ecosystem participants through a unified platform
- **Operational Efficiency:** Reduce manual processes, wait times, and operational bottlenecks
- **Security Enhancement:** Implement robust verification and monitoring systems
- **Revenue Optimization:** Introduce transparent, transaction-based billing system

#### 1.2 Coverage Scope
- **Containerized Cargo:** Import and export containers, empty container movements
- **Non-containerized Cargo:** Bulk cargo, frozen goods, and specialized freight
- **Vehicle Management:** Truck registration, scheduling, and route optimization
- **Container Exchange:** Facilitate efficient container/truck exchanges between freight forwarders and transporters

### 2. Stakeholder Ecosystem

#### 2.1 Primary Stakeholders
1. **Freight Forwarders**
    - Platform registration and transaction management
    - Container delivery coordination
    - Import/export documentation handling

2. **Transporters**
    - Vehicle registration and enrollment
    - Route confirmation and transit status updates
    - Transit Commencement Permit (TCP) management

3. **Shippers**
    - Transaction verification and cargo tracking
    - Departure confirmation from warehouses
    - Receipt confirmation for delivered goods

4. **Shipping Companies**
    - Terminal Delivery Order (TDO) management
    - Export Delivery Note (EDN) processing
    - Entry Permit (EP) coordination

5. **Port Terminals**
    - Container delivery verification
    - Booking number management
    - Operational status updates

6. **Empty Container Terminals**
    - Empty container receipt confirmation
    - Terminal delay management
    - Transporter coordination

7. **Transit Park Operators**
    - Parking slot availability reporting
    - Truck arrival/departure confirmation
    - Operational status management

8. **Security and Traffic Control Agencies**
    - Transaction verification and monitoring
    - Access control and security oversight
    - Compliance enforcement

### 3. Technical Architecture

#### 3.1 System Architecture Overview
The SORAT platform follows a distributed, IoT-enabled architecture with edge computing capabilities, cloud backend services, and multi-platform client applications.

#### 3.2 Core Components

##### 3.2.1 IoT Edge Infrastructure
- **Hardware Requirements:**
    - IoT Edge Device: Jetson Nano, Raspberry Pi 4, or industrial camera system
    - HD IR Camera with night vision support
    - Local storage: SSD or SD card for offline logging
    - Power system: Solar + Battery backup for remote locations

- **Edge Processing:**
    - AI Plate Detection: OpenALPR/YOLOv5 ANPR/OpenCV + Tesseract
    - Real-time video processing and plate extraction
    - Local caching and offline mode support
    - Edge ML model updates over-the-air

##### 3.2.2 Backend Services
- **API Layer:** Node.js, Python Flask, or FastAPI
- **Database:** PostgreSQL for transporter/plate registry, Firebase for real-time updates
- **Authentication:** Role-based access control for different stakeholder types
- **Data Encryption:** TLS + Local AES encryption for plate logs
- **Notification Engine:** Twilio, Firebase Cloud Messaging, WhatsApp Business API

##### 3.2.3 Client Applications
- **Mobile Application:** Cross-platform app for transporters and field operators
- **Web Dashboard:** ReactJS/VueJS admin interface for monitoring and management
- **WhatsApp Integration:** Business API for instant notifications
- **SMS/Email Notifications:** Multi-channel communication system

#### 3.3 System Workflow

##### 3.3.1 Vehicle Detection and Processing
1. **Detection:** Camera detects vehicle entering gate area
2. **Recognition:** Edge device processes video and extracts plate number using ANPR
3. **Verification:** Plate number cross-checked with transporter database
4. **Logging:** Transaction logged with timestamp, location, and status
5. **Notification:** Real-time alerts sent to relevant stakeholders
6. **Dashboard Update:** Admin dashboard reflects live status changes

##### 3.3.2 Transaction Management
- **Unique Transaction IDs:** Sequential numbering with import/export prefixes
- **Status Tracking:** Real-time status updates throughout the cargo journey
- **Documentation Management:** Digital handling of TDO, EDN, EP, and other permits
- **Billing Integration:** Automated transaction-based charging system

### 4. System Features

#### 4.1 Core Features
- **Scheduled Access Control:** No vehicle enters without pre-scheduling
- **Real-time Tracking:** Live monitoring of all vehicle and container movements
- **Automated Notifications:** SMS, WhatsApp, email, and app notifications
- **Document Management:** Digital permit and documentation handling
- **Route Optimization:** Intelligent route designation and management
- **Performance Monitoring:** Comprehensive analytics and reporting

#### 4.2 Advanced Features
- **Color-coded Information System:** Visual status indicators for quick identification
- **Progress Monitoring:** Complete transaction lifecycle tracking
- **Performance Assessment:** KPI tracking and operational analytics
- **Multi-language Support:** Localized interface for diverse user base
- **Offline Mode:** Edge device functionality during connectivity issues

#### 4.3 Optional Add-ons
- **QR Code Integration:** Alternative identification for authorized transformers and freight forwarders
- **Barrier Gate Integration:** Automated gate control based on verification results
- **Vehicle Weight Sensors:** Load verification and compliance monitoring
- **Advanced Analytics:** AI-powered insights and predictive analytics

### 5. Security and Compliance

#### 5.1 Security Framework
- **Data Encryption:** End-to-end encryption for all sensitive data
- **Access Control:** Role-based permissions for different stakeholder types
- **Audit Logging:** Comprehensive logging of all system activities
- **Secure Communication:** TLS encryption for all API communications
- **Local Security:** AES encryption for edge device data storage

#### 5.2 Compliance Requirements
- **Port Authority Regulations:** Adherence to local port management guidelines
- **Data Protection:** Compliance with applicable data privacy laws
- **Security Protocols:** Integration with existing port security systems
- **Operational Standards:** Alignment with international port management standards

### 6. Implementation Strategy

#### 6.1 Phase 1: Foundation (Months 1-3)
- **Backend Development:** Core API services and database setup
- **Authentication System:** Role-based access control implementation
- **Basic Mobile App:** Essential functionality for transporters
- **IoT Edge Setup:** Hardware deployment and basic ANPR integration

#### 6.2 Phase 2: Core Features (Months 4-6)
- **Full Stakeholder Integration:** Complete platform for all user types
- **Advanced Notifications:** Multi-channel communication system
- **Web Dashboard:** Comprehensive admin interface
- **Container Exchange System:** Freight forwarder/transporter coordination

#### 6.3 Phase 3: Advanced Features (Months 7-9)
- **Analytics Dashboard:** Performance monitoring and reporting
- **Advanced Security:** Enhanced encryption and access controls
- **Integration APIs:** Third-party system connectivity
- **Mobile App Enhancement:** Advanced features and offline capabilities

#### 6.4 Phase 4: Optimization (Months 10-12)
- **Performance Tuning:** System optimization and scaling
- **Advanced Analytics:** AI-powered insights and reporting
- **Optional Add-ons:** QR codes, barrier gates, weight sensors
- **User Training:** Comprehensive stakeholder onboarding

### 7. Conclusion

SORAT is a modern, scalable, and secure solution for port facility management. By digitizing and automating critical workflows, it reduces operational friction, increases throughput, and provides the transparency and control required by today’s port authorities and logistics operators.

---

**Document Version:** 1.0  
**Last Updated:** July 2025  
**Next Review:** October 2025


