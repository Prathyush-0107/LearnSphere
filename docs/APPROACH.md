# Project Approach & Architecture — Build Secure 24

**Team ID:** 5  
**Project Name:** LearnSphere  
**Team Name:** Byte  
**Team Size:** 4 Members  
**Primary Track / Domain:** PS-03 — EdTech Learning and Assessment Platform

---

## 1. Problem Understanding, Scope & Threat Model

### 1.1 Problem Statement & Real-World Motivation

LearnSphere is an EdTech learning and assessment platform designed to bring student learning, courses, assessments, results, instructor management, and administrative functions into one platform.

The current hackathon MVP focuses primarily on the frontend experience and security-oriented product design. A production implementation would require a backend API, persistent database, server-side authentication, and server-side authorization.

### 1.2 Target Users & Personas

**Student**
- Views available courses.
- Enrolls in courses.
- Accesses assessments.
- Views assessment results.
- Uses the optional AI learning assistant.
- Views the security center.

**Instructor**
- Views and manages course-related functionality.
- Uses the instructor dashboard.
- Manages assessment-related functionality.

**Administrator**
- Uses the administrator dashboard.
- Manages platform and user-oriented functionality.

### 1.3 Threat Model & Attack Surface

#### Critical Assets

- User account information.
- Authentication credentials in a production implementation.
- Course and assessment data.
- Assessment submissions and results.
- User role information.
- Session/authentication tokens in a production backend.

#### Potential Attack Vectors

- Credential stuffing and brute-force login attempts.
- Broken access control.
- Privilege escalation.
- Unauthorized access to another user's assessment or results.
- Injection attacks against a future backend/API.
- Client-side manipulation of role information.
- Session/token theft in a production implementation.
- Malicious or malformed user input.

#### OWASP Considerations

The design considers:
- Broken access control.
- Identification and authentication failures.
- Injection.
- Security misconfiguration.
- Cryptographic failures.
- Improper handling of sensitive information.

The current frontend demonstrates role-aware navigation, but client-side role checks alone are not a security boundary. A production implementation must enforce authorization on the backend/API.

---

## 2. Technical Architecture & Secure System Design

### 2.1 High-Level Architecture Overview

The current hackathon MVP consists of a browser-based frontend.

```text
User
  |
  v
LearnSphere Web UI
  |
  +-- Student Dashboard
  +-- Courses
  +-- Assessments
  +-- AI Assistant
  +-- Security Center
  +-- Instructor Dashboard
  +-- Administrator Dashboard