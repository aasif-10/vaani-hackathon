# VAANI - Requirements Document

## Project Overview
VAANI is a voice-first, AI-powered platform designed to democratize access to government welfare schemes and grievance redressal mechanisms for rural India. The platform enables citizens to interact through phone calls, WhatsApp voice messages, and SMS to discover eligible schemes, file grievances, track status, and ensure timely resolution through automated escalation.

---

## Problem Statement

Rural citizens in India face significant barriers in accessing government welfare schemes and grievance redressal systems:

- **Information Gap**: Lack of awareness about available schemes and eligibility criteria
- **Language Barriers**: Most digital platforms are not available in local languages or dialects
- **Digital Literacy**: Limited smartphone penetration and low digital literacy rates
- **Complex Processes**: Bureaucratic procedures are difficult to navigate without assistance
- **Lack of Follow-up**: No systematic way to track grievance status or ensure resolution
- **Accessibility**: Existing systems require internet access and literacy, excluding marginalized communities

---

## Goals & Objectives

### Primary Goals
1. Enable voice-based discovery of government welfare schemes in local languages
2. Simplify grievance filing through conversational AI interfaces
3. Provide automated tracking and status updates for filed grievances
4. Implement intelligent escalation for delayed resolutions
5. Bridge the digital divide by supporting low-tech communication channels

### Objectives
- Achieve 95%+ accuracy in voice recognition for regional languages
- Reduce average grievance filing time from 2+ hours to under 10 minutes
- Support at least 10 Indian languages at launch
- Enable scheme discovery for 100+ central and state government programs
- Provide real-time status tracking with SMS/voice notifications
- Implement automated escalation within 48 hours of SLA breach

---

## Functional Requirements

### FR1: Multi-Channel Access
- **FR1.1**: Support inbound phone calls via IVR system
- **FR1.2**: Accept WhatsApp voice messages for asynchronous interaction
- **FR1.3**: Enable SMS-based text commands for basic queries
- **FR1.4**: Provide toll-free number access across India

### FR2: Voice Interaction & NLP
- **FR2.1**: Recognize and process speech in 10+ Indian languages
- **FR2.2**: Support conversational AI with context retention across sessions
- **FR2.3**: Handle mixed language inputs (code-switching)
- **FR2.4**: Provide voice responses in user's preferred language
- **FR2.5**: Implement fallback to human operator for complex queries

### FR3: Scheme Discovery
- **FR3.1**: Collect user demographic information through conversation
- **FR3.2**: Match user profile against eligibility criteria of 100+ schemes
- **FR3.3**: Provide personalized list of eligible schemes
- **FR3.4**: Explain scheme benefits, application process, and required documents
- **FR3.5**: Store user preferences for future recommendations

### FR4: Grievance Filing
- **FR4.1**: Guide users through grievance filing via voice prompts
- **FR4.2**: Capture grievance details: category, description, location, supporting info
- **FR4.3**: Generate unique grievance ID for tracking
- **FR4.4**: Send confirmation via SMS with grievance ID and expected resolution time
- **FR4.5**: Support attachment of photos/documents via WhatsApp

### FR5: Status Tracking
- **FR5.1**: Allow users to check status using grievance ID via any channel
- **FR5.2**: Provide automated status updates at key milestones
- **FR5.3**: Send proactive notifications for status changes
- **FR5.4**: Maintain complete audit trail of grievance lifecycle

### FR6: Automated Escalation
- **FR6.1**: Monitor grievance resolution timelines against defined SLAs
- **FR6.2**: Trigger automatic escalation to higher authorities on delays
- **FR6.3**: Notify user when escalation occurs
- **FR6.4**: Track escalation levels and response times
- **FR6.5**: Generate alerts for critical unresolved cases

### FR7: User Management
- **FR7.1**: Create user profiles with phone number as primary identifier
- **FR7.2**: Store demographic data, language preference, and location
- **FR7.3**: Maintain interaction history across all channels
- **FR7.4**: Support anonymous grievance filing with limited tracking

### FR8: Reporting & Analytics
- **FR8.1**: Generate dashboards for grievance trends and resolution rates
- **FR8.2**: Track scheme awareness and application rates
- **FR8.3**: Monitor system performance metrics (call success rate, accuracy)
- **FR8.4**: Provide insights for policy makers and administrators

---

## Non-Functional Requirements

### NFR1: Performance
- Voice recognition response time < 2 seconds
- IVR call connection time < 5 seconds
- System availability: 99.5% uptime
- Support 10,000 concurrent calls
- WhatsApp message processing < 30 seconds

### NFR2: Scalability
- Horizontally scalable architecture to handle growing user base
- Support for adding new languages without system redesign
- Ability to integrate new government schemes dynamically
- Database design to handle millions of grievances

### NFR3: Security & Privacy
- End-to-end encryption for voice data transmission
- Compliance with India's data protection regulations
- Secure storage of personal information with access controls
- Anonymization of data for analytics
- Regular security audits and penetration testing

### NFR4: Usability
- Zero learning curve for voice interaction
- Support for users with no digital literacy
- Clear voice prompts with option to repeat
- Graceful error handling with helpful guidance
- Maximum 3-level menu depth in IVR

### NFR5: Reliability
- Automatic failover for critical services
- Data backup every 6 hours
- Disaster recovery plan with 24-hour RTO
- Graceful degradation during partial outages

### NFR6: Localization
- Native speaker voice quality for all supported languages
- Cultural sensitivity in conversation design
- Regional dialect support for major languages
- Local holiday and working hours awareness

### NFR7: Compliance
- Adherence to TRAI regulations for telecom services
- Compliance with Right to Information Act
- Integration with government grievance portals (CPGRAMS)
- Audit logs for all transactions

---

## User Personas

### Persona 1: Lakshmi - Rural Farmer
- **Age**: 45
- **Location**: Village in Karnataka
- **Language**: Kannada
- **Education**: Primary school
- **Technology**: Basic feature phone, no internet
- **Needs**: Discover agricultural subsidies, file complaint about delayed pension
- **Pain Points**: Cannot read complex forms, no internet access, doesn't know which schemes exist

### Persona 2: Ramesh - Daily Wage Worker
- **Age**: 32
- **Location**: Small town in Uttar Pradesh
- **Language**: Hindi
- **Education**: 8th grade
- **Technology**: Smartphone with limited data
- **Needs**: Check MGNREGA payment status, file grievance about ration card
- **Pain Points**: Limited time during work hours, prefers voice over typing

### Persona 3: Savitri - Elderly Widow
- **Age**: 68
- **Location**: Rural Rajasthan
- **Language**: Rajasthani/Hindi
- **Education**: Illiterate
- **Technology**: Relies on neighbor's phone
- **Needs**: Access widow pension, file complaint about healthcare facility
- **Pain Points**: Cannot read or write, needs simple voice-only interface

### Persona 4: Arjun - Youth Volunteer
- **Age**: 24
- **Location**: Semi-urban Tamil Nadu
- **Language**: Tamil, English
- **Education**: Graduate
- **Technology**: Smartphone with WhatsApp
- **Needs**: Help community members file grievances, track multiple cases
- **Pain Points**: Needs efficient way to manage multiple grievances for others

---

## Assumptions & Constraints

### Assumptions
- Users have access to at least a basic mobile phone
- Government scheme databases are accessible via APIs or can be scraped
- Telecom infrastructure supports voice calls in target regions
- Users are willing to share demographic information for scheme matching
- Government departments will respond to escalated grievances

### Constraints
- **Budget**: Hackathon project with limited cloud credits
- **Timeline**: MVP to be developed within hackathon duration
- **Data Access**: May not have real-time integration with all government systems
- **Telephony**: Dependent on third-party telecom APIs (Twilio, Exotel)
- **Language Models**: Limited by available multilingual NLP models
- **Testing**: Limited ability to test with actual rural users during hackathon
- **Regulatory**: Cannot store sensitive government IDs without proper compliance

---

## Success Metrics

### User Adoption
- 1,000+ unique users within first month of launch
- 60%+ user retention rate (return users)
- Average 3+ interactions per user

### Operational Efficiency
- 90%+ voice recognition accuracy across supported languages
- 80%+ successful call completion rate
- Average grievance filing time < 10 minutes
- 70%+ of grievances resolved within SLA

### Impact Metrics
- 50%+ increase in scheme awareness among users
- 30%+ increase in scheme applications from target demographics
- 40% reduction in grievance resolution time vs. traditional methods
- 25%+ of delayed grievances successfully escalated and resolved

### Technical Performance
- 99%+ system uptime
- < 3 second average response time
- < 5% error rate in NLP processing
- Support 500+ concurrent users in MVP phase

---

## Out of Scope

The following items are explicitly out of scope for the initial version:

1. **Direct Scheme Application**: System will guide users but not submit applications directly to government portals
2. **Payment Processing**: No financial transactions or payment gateway integration
3. **Document Verification**: No automated verification of user-submitted documents
4. **Video Calls**: Only voice and text-based interactions
5. **Web Portal**: No web-based user interface (voice/SMS only)
6. **Legal Advice**: System provides information only, not legal consultation
7. **Emergency Services**: Not designed for emergency response or 911-type services
8. **Offline Mode**: Requires active phone/data connection
9. **Third-party Integrations**: No integration with NGOs or private service providers
10. **Advanced Analytics**: No predictive modeling or AI-driven policy recommendations
11. **Multi-user Accounts**: One phone number = one user profile
12. **Historical Data Migration**: No import of existing grievances from other systems

---

## Appendix

### Technology Stack (Proposed)
- **Voice Recognition**: Google Speech-to-Text, Azure Speech Services
- **NLP**: Bhashini API, OpenAI Whisper for multilingual support
- **Telephony**: Twilio/Exotel for IVR and SMS
- **WhatsApp**: WhatsApp Business API
- **Backend**: Node.js/Python with FastAPI
- **Database**: PostgreSQL for structured data, MongoDB for conversation logs
- **AI/ML**: LangChain for conversational AI, RAG for scheme matching
- **Hosting**: AWS/Azure with auto-scaling

### Supported Languages (Phase 1)
Hindi, Bengali, Telugu, Marathi, Tamil, Gujarati, Kannada, Malayalam, Odia, Punjabi

### Government Schemes Categories
- Agriculture & Farmers Welfare
- Social Security & Pensions
- Healthcare & Insurance
- Education & Scholarships
- Housing & Sanitation
- Employment & Skill Development
- Women & Child Development
- Financial Inclusion

---

**Document Version**: 1.0  
**Last Updated**: February 15, 2026  
**Status**: Draft for Hackathon Submission
