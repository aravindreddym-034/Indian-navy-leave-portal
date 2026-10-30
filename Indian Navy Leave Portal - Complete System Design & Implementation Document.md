# **COMNETCEN Automated Leave Management System (ALMS)**

# **System Design, Operational Architecture, and Deployment Specifications**

# **1\. System Overview & Objectives**

COMNETCEN operates as the critical communications hub for naval operational networks, message-handling switches, cryptographic custody, and signal infrastructure. Ensuring 24/7/365 uninterrupted operational readiness demands stringent personnel planning. The Automated Leave Management System (ALMS) transitions COMNETCEN from manual, error-prone record-keeping to a deterministic, rule-governed digital clearinghouse.

The core objectives of the system are:

* **Operational Continuity Assurance:** Mandate that no critical communication role or watchkeeping console is left unstaffed during operational cycles.  
* **Rigid Relief Protocols:** Enforce primary, secondary (TDLR 1), and tertiary (TDLR 2\) relief coverage across all 33 designated center duties.  
* **Deterministic Rostering:** Guarantee non-overlapping absence windows between primary appointment holders and their nominated relief watchkeepers.  
* **Equity and Transparency:** Track entitlement limits (60-day Annual Leave split into three 20-day blocks for permanent staff; 30-day Accumulated Leave split into two 15-day blocks for transitional/support staff) without schedule conflicts.  
* **Auditable Verification:** Provide cryptographic verification, digital signatures, role-based approval routing, and immediate conflict flagging.

# **2\. Personnel Nominal Roll & Leave Entitlement Matrix**

The unit complement for this module comprises 12 sailors spanning executive communications, cryptographic systems, and technical infrastructure branches.

* **Ser 1 to 8:** Permanent establishment personnel entitled to 60 days of Annual Leave (AL), scheduled uniformly in three distinct 20-day blocks across Cycles 1, 2, and 3\.  
* **Ser 9 to 12:** Specialist/transitional personnel entitled to 30 days of Leave, scheduled in two distinct 15-day blocks across Cycles 1 and 2\.

| Ser | Service No | Rank | Name | Branch / Trade | Primary Billet | Leave Entitlement | Cycle Structure |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| 1 | 214582-W | MCPO I (WTR) | R. K. Nair | Executive / Comms | Regulating Master Chief | 60 Days AL | 3 Blocks × 20 Days |
| 2 | 218901-B | MCPO II (TEL) | S. P. Sharma | Comms / Radio | Shift In-Charge (Alpha) | 60 Days AL | 3 Blocks × 20 Days |
| 3 | 221345-N | CPO (TEL) | Amit Kumar | Comms / Signal | Shift In-Charge (Bravo) | 60 Days AL | 3 Blocks × 20 Days |
| 4 | 224512-K | PO (TEL) | Vikram Singh | Network Specialist | Broadcast Network Controller | 60 Days AL | 3 Blocks × 20 Days |
| 5 | 227890-R | PO (TEL) | D. Mukherjee | Cryptographic Maint | Crypto Account Custodian | 60 Days AL | 3 Blocks × 20 Days |
| 6 | 229001-A | LS (TEL) | Rajesh Patel | Comms / VLF-HF | Secure Terminal Operator 1 | 60 Days AL | 3 Blocks × 20 Days |
| 7 | 231456-F | LS (TEL) | M. V. Rao | Radio Systems | Secure Terminal Operator 2 | 60 Days AL | 3 Blocks × 20 Days |
| 8 | 233112-T | SEA I (TEL) | Harish Rawat | Signal Infrastructure | Routing & Dispatcher | 60 Days AL | 3 Blocks × 20 Days |
| 9 | 235678-H | SEA I (TEL) | Kuldeep Yadav | Infrastructure Support | Antennas & Rigging Watch | 30 Days AL | 2 Blocks × 15 Days |
| 10 | 237890-M | SEA I (UW) | G. K. Reddy | Auxiliary Support | Power & UPS In-Charge | 30 Days AL | 2 Blocks × 15 Days |
| 11 | 240123-P | SEA II (TEL) | S. Chakraborty | Network Support | Line & Patching Tech | 30 Days AL | 2 Blocks × 15 Days |
| 12 | 242456-Z | SEA II (TEL) | Ankit Verma | General Operations | Signal Distribution Office | 30 Days AL | 2 Blocks × 15 Days |

# **3\. Complete Charter of Duties & Relief Protocol**

The operational effectiveness of COMNETCEN requires a comprehensive map of all 33 critical unit duties. The duty allocation below enforces strict non-circularity: Primary \$\\ne\$ TDLR 1 \$\\ne\$ TDLR 2\.

| Duty ID | Charter of Duty / Operational Responsibility | Primary Handler | TDLR 1 (First Relief) | TDLR 2 (Secondary Relief) | Fallback Operational Action Protocol |
| :---- | :---- | :---- | :---- | :---- | :---- |
| D-01 | Station Log & Regulating Office Administration | Ser 1 | Ser 2 | Ser 3 | Relinquish to Senior Watchkeeper on station |
| D-02 | HF Operations & Global Broadcast Link Controller | Ser 2 | Ser 3 | Ser 4 | Fallback to secondary transceiver bench A |
| D-03 | Tactical Data Link & Shore Integration Switch | Ser 3 | Ser 4 | Ser 2 | Route via alternate shore fiber ring |
| D-04 | VLF Receiver Site Monitoring & Synchronization | Ser 4 | Ser 2 | Ser 6 | Lock receiver presets to baseline status |
| D-05 | Crypto Key Variable Loading & Distribution | Ser 5 | Ser 4 | Ser 7 | Enact Key Vault dual-custody override |
| D-06 | Cryptographic Physical Custody & Zeroization Logs | Ser 5 | Ser 1 | Ser 8 | Log inspection by Regulating Master Chief |
| D-07 | Strategic IP Gateway Router Monitoring | Ser 4 | Ser 6 | Ser 11 | Switch core traffic to bypass node |
| D-08 | Primary Fleet Broadcast Multiplexer Tuning | Ser 6 | Ser 7 | Ser 8 | Engage auto-failover to backup mux |
| D-09 | Shore-to-Ship Telegraphic Line Terminal Ops | Ser 7 | Ser 8 | Ser 6 | Reroute traffic via redundant copper pair |
| D-10 | Primary Signal Dispatch & Routing Matrix | Ser 8 | Ser 9 | Ser 12 | Shift routing desk to secondary console |
| D-11 | Secure Voice Console Watchkeeping & Escalation | Ser 6 | Ser 8 | Ser 2 | Connect alternate secure conference line |
| D-12 | Satellite Ground Terminal (SATCOM) Tracking | Ser 7 | Ser 6 | Ser 9 | Switch antenna pedestal to auto-stabilize |
| D-13 | Message Switching Unit (MSU) Buffer Clearance | Ser 8 | Ser 12 | Ser 7 | Transfer queued flash buffer to manual spool |
| D-14 | Emergency Transceiver Battery Bank Verification | Ser 10 | Ser 9 | Ser 11 | Direct hook-up to offline DC power unit |
| D-15 | Network Hardware Level-1 Diagnostics & Swapping | Ser 11 | Ser 4 | Ser 10 | Pull and replace using pre-flashed chassis |
| D-16 | Main Distribution Frame (MDF) Patch Management | Ser 11 | Ser 12 | Ser 9 | Isolate and strap alternate cross-connects |
| D-17 | Antenna Matrix Switching & VSWR Verification | Ser 9 | Ser 10 | Ser 11 | Divert RF feed to dummy load array |
| D-18 | Diesel Generator Automatic Transfer Switch (ATS) | Ser 10 | Ser 11 | Ser 1 | Manual transfer to base feeder sub-station |
| D-19 | COMSEC Equipment Daily Zeroization Audits | Ser 5 | Ser 2 | Ser 1 | Dual physical muster with Duty Officer |
| D-20 | Offline Cryptographic Tape Inward/Outward Registry | Ser 1 | Ser 5 | Ser 4 | Seal register pending physical inspection |
| D-21 | Red Data Network Firewall Ruleset Review | Ser 4 | Ser 5 | Ser 6 | Lock egress policy; prevent rule modifications |
| D-22 | Physical Perimeter Intrusion & Rack Access Logs | Ser 1 | Ser 10 | Ser 8 | Freeze electronic access badges |
| D-23 | Optical Fiber Transceiver Link Budget Audits | Ser 11 | Ser 9 | Ser 4 | Switch to auxiliary multimode run |
| D-24 | Distress Frequency (2182 kHz / 156.8 MHz) Guard | Ser 2 | Ser 6 | Ser 7 | Bridge emergency audio to main console |
| D-25 | Tactical Air Comms Ground Relay Interlink | Ser 3 | Ser 7 | Ser 6 | Re-point UHF yagi array to omni tower |
| D-26 | Classified Waste Destruction & Incineration Log | Ser 1 | Ser 3 | Ser 5 | Impound waste safe; require Duty Officer key |
| D-27 | Technical Stores & Spares Requisition Registry | Ser 3 | Ser 1 | Ser 10 | Freeze stock issues; activate emergency reserve |
| D-28 | Shift Duty Rostering & Change-of-Watch Orders | Ser 2 | Ser 1 | Ser 3 | Standardize shifts to standing Alpha watch |
| D-29 | Fleet Teleprinter Maintenance & Head Cleaning | Ser 8 | Ser 7 | Ser 12 | Swap to solid-state serial capture unit |
| D-30 | Signal Archive Tape Backup & Hard Drive Rotation | Ser 5 | Ser 8 | Ser 11 | Archive to locked off-site NAS enclosure |
| D-31 | Cooling & HVAC Environment Verification in Crypto | Ser 10 | Ser 12 | Ser 1 | Deploy auxiliary split air-conditioning unit |
| D-32 | Classified Document Transit Bags Escort & Seal | Ser 12 | Ser 8 | Ser 10 | Hand over custody to armed guard commander |
| D-33 | Daily Synchronization of Atomic Clocks / NTP Nodes | Ser 4 | Ser 3 | Ser 5 | Lock system time to internal oven oscillator |

# **4\. Master Operational Leave Schedule for Year 2027**

To maintain uninterrupted operational readiness and complete all leave entitlements strictly within calendar year 2027 (Jan 1 to Dec 26, 2027, with no spillover into 2028), personnel leave is distributed across three balanced 120-day cycles using a duty-independent parallel rotation. At no point are watch buddies sharing any of the 33 critical appointments absent simultaneously.

* **Cycle 1 (01 Jan 2027 – 30 Apr 2027):** Ser 1–8 execute Block 1 (20 days each); Ser 9–12 execute Block 1 (15 days each).  
* **Cycle 2 (01 May 2027 – 28 Aug 2027):** Ser 1–8 execute Block 2 (20 days each); Ser 9–12 execute Block 2 (15 days each, concluding their full 30-day entitlement).  
* **Cycle 3 (29 Aug 2027 – 26 Dec 2027):** Ser 1–8 execute Block 3 (20 days each, concluding their full 60-day entitlement); Ser 9–12 remain on full-time station watch.

| Ser | Name | Leave Window: Block 1 | Leave Window: Block 2 | Leave Window: Block 3 | Total Days |
| :---- | :---- | :---- | :---- | :---- | :---- |
| 1 | R. K. Nair | 01 Jan 2027 – 20 Jan 2027 | 01 May 2027 – 20 May 2027 | 29 Aug 2027 – 17 Sep 2027 | 60 |
| 2 | S. P. Sharma | 21 Jan 2027 – 09 Feb 2027 | 21 May 2027 – 09 Jun 2027 | 18 Sep 2027 – 07 Oct 2027 | 60 |
| 3 | Amit Kumar | 10 Feb 2027 – 01 Mar 2027 | 10 Jun 2027 – 29 Jun 2027 | 08 Oct 2027 – 27 Oct 2027 | 60 |
| 4 | Vikram Singh | 02 Mar 2027 – 21 Mar 2027 | 30 Jun 2027 – 19 Jul 2027 | 28 Oct 2027 – 16 Nov 2027 | 60 |
| 5 | D. Mukherjee | 22 Mar 2027 – 10 Apr 2027 | 20 Jul 2027 – 08 Aug 2027 | 17 Nov 2027 – 06 Dec 2027 | 60 |
| 6 | Rajesh Patel | 01 Jan 2027 – 20 Jan 2027 | 01 May 2027 – 20 May 2027 | 29 Aug 2027 – 17 Sep 2027 | 60 |
| 7 | M. V. Rao | 11 Apr 2027 – 30 Apr 2027 | 09 Aug 2027 – 28 Aug 2027 | 07 Dec 2027 – 26 Dec 2027 | 60 |
| 8 | Harish Rawat | 10 Feb 2027 – 01 Mar 2027 | 10 Jun 2027 – 29 Jun 2027 | 08 Oct 2027 – 27 Oct 2027 | 60 |
| 9 | Kuldeep Yadav | 21 Jan 2027 – 04 Feb 2027 | 21 May 2027 – 04 Jun 2027 | N/A (30 Days Entitled) | 30 |
| 10 | G. K. Reddy | 22 Mar 2027 – 05 Apr 2027 | 20 Jul 2027 – 03 Aug 2027 | N/A (30 Days Entitled) | 30 |
| 11 | S. Chakraborty | 11 Apr 2027 – 25 Apr 2027 | 09 Aug 2027 – 23 Aug 2027 | N/A (30 Days Entitled) | 30 |
| 12 | Ankit Verma | 02 Mar 2027 – 16 Mar 2027 | 30 Jun 2027 – 14 Jul 2027 | N/A (30 Days Entitled) | 30 |

# **5\. Technical System Architecture & Database Schema**

The COMNETCEN Leave Portal operates on an on-premise, air-gapped web stack designed for secure containerized deployment.

* **Backend Engine:** Python (FastAPI / Django REST Framework) providing strict transactional integrity.  
* **Database Management System:** PostgreSQL 15 with deterministic constraints and foreign-key isolation.  
* **Security & Auth:** PKI/Smart-Card Authentication with Role-Based Access Control (RBAC).

```
                      +------------------------------------+
                      |    Client Layer: Modern Browser    |
                      |   (Vite + React + Tailwind CSS)    |
                      +-----------------+------------------+
                                        |
                             HTTPS / mTLS Encryption
                                        |
                                        v
                      +-----------------+------------------+
                      |   Reverse Proxy & Web Server       |
                      |          (NGINX / TLS)             |
                      +-----------------+------------------+
                                        |
                             ASGI Request Dispatch
                                        |
                                        v
                      +-----------------+------------------+
                      |      FastAPI Backend Engine        |
                      |  - JWT / Smart Card Authentication |
                      |  - Leave Validation & Conflict Rule|
                      |  - Digital Signature Verifier      |
                      +-----------------+------------------+
                                        |
                             SQLAlchemy ORM / psycopg2
                                        |
                                        v
                      +-----------------+------------------+
                      |     PostgreSQL 15 Database         |
                      |  - sailors, duties, leave_records  |
                      |  - Audit Log & Hash Chaining       |
                      +------------------------------------+
```

## **5.1 Sailors Table (`sailors`)**

```
CREATE TABLE sailors (
    serial_no INT PRIMARY KEY,
    service_no VARCHAR(16) UNIQUE NOT NULL,
    rank VARCHAR(32) NOT NULL,
    name VARCHAR(128) NOT NULL,
    branch VARCHAR(64) NOT NULL,
    primary_billet VARCHAR(128) NOT NULL,
    entitled_days INT NOT NULL CHECK (entitled_days IN (30, 60)),
    block_allowance INT NOT NULL,
    is_active BOOLEAN DEFAULT TRUE,
    created_at TIMESTAMP WITH TIME ZONE DEFAULT CURRENT_TIMESTAMP
);
```

## **5.2 Duties Table (`duties`)**

```
CREATE TABLE duties (
    duty_id VARCHAR(8) PRIMARY KEY,
    duty_name VARCHAR(128) NOT NULL,
    primary_sailor_id INT NOT NULL REFERENCES sailors(serial_no),
    tdlr_1_id INT NOT NULL REFERENCES sailors(serial_no),
    tdlr_2_id INT NOT NULL REFERENCES sailors(serial_no),
    fallback_protocol TEXT NOT NULL,
    is_critical BOOLEAN DEFAULT TRUE,
    CONSTRAINT chk_distinct_personnel CHECK (
        primary_sailor_id <> tdlr_1_id AND
        primary_sailor_id <> tdlr_2_id AND
        tdlr_1_id <> tdlr_2_id
    )
);
```

## **5.3 Leave Records Table (`leave_records`)**

```
CREATE TYPE leave_status_enum AS ENUM (
    'DRAFT', 
    'SUBMITTED', 
    'TDLR_VERIFIED', 
    'OFFICER_APPROVED', 
    'REJECTED', 
    'CANCELLED'
);

CREATE TABLE leave_records (
    record_id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    sailor_id INT NOT NULL REFERENCES sailors(serial_no),
    cycle_number INT NOT NULL CHECK (cycle_number IN (1, 2, 3)),
    start_date DATE NOT NULL,
    end_date DATE NOT NULL,
    duration_days INT GENERATED ALWAYS AS (end_date - start_date + 1) STORED,
    status leave_status_enum DEFAULT 'DRAFT',
    tdlr_1_verified BOOLEAN DEFAULT FALSE,
    tdlr_2_verified BOOLEAN DEFAULT FALSE,
    digital_signature BYTEA,
    rejection_reason TEXT,
    created_at TIMESTAMP WITH TIME ZONE DEFAULT CURRENT_TIMESTAMP,
    CONSTRAINT chk_date_order CHECK (end_date >= start_date)
);
```

# **6\. Algorithmic Conflict Resolution & Backend Validation Logic**

## **6.1 Validation Pipeline**

1. **Entitlement & Block Bounds Check:**  
   Confirm total accumulated leave days do not exceed `entitled_days`. Verify that individual block sizes strictly adhere to the sailor's profile (20 days for Ser 1–8, 15 days for Ser 9–12).  
2. **Duty Direct Conflict Evaluation:**  
   Identify all duties where the applicant is assigned as `Primary`, `TDLR 1`, or `TDLR 2`.  
3. **Tri-Tier Concurrency Conflict:**  
   For each duty associated with the applicant, query `leave_records` to verify that no pairing among {Primary, TDLR 1, TDLR 2} overlaps over the proposed `[start_date, end_date]`.  
4. **Active Center Redundancy Verification:**  
   Ensure that at least two relief tiers remain on active duty at COMNETCEN across the candidate date window.  
5. **State Transition Assertion:**  
   Allow advancement to `OFFICER_APPROVED` status only if the non-overlap condition is proven across all 33 duty definitions.

## **6.2 Python Conflict Engine Implementation**

```py
from datetime import date
from typing import List, Dict, Any, Tuple

class LeaveConflictEngine:
    def __init__(self, sailors: Dict[int, Dict[str, Any]], duties: List[Dict[str, Any]], leaves: List[Dict[str, Any]]):
        self.sailors = sailors
        self.duties = duties
        self.leaves = leaves

    def validate_request(self, applicant_id: int, new_start: date, new_end: date) -> Tuple[bool, List[str]]:
        errors = []
        duration = (new_end - new_start).days + 1
        applicant = self.sailors.get(applicant_id)

        if not applicant:
            return False, ["Applicant ID does not exist in Nominal Roll."]

        # Check block duration constraint
        allowed_block = 20 if applicant["entitled_days"] == 60 else 15
        if duration != allowed_block:
            errors.append(f"Invalid duration: {duration} days. Required: {allowed_block} days.")

        # Aggregate taken leave
        taken_days = sum(
            (l["end_date"] - l["start_date"]).days + 1
            for l in self.leaves
            if l["sailor_id"] == applicant_id and l["status"] in ["SUBMITTED", "TDLR_VERIFIED", "OFFICER_APPROVED"]
        )
        if taken_days + duration > applicant["entitled_days"]:
            errors.append(f"Quota exceeded: Taking {duration} days will exceed entitlement of {applicant['entitled_days']} days.")

        # Identify all relevant duties
        relevant_duties = [
            d for d in self.duties
            if applicant_id in (d["primary_sailor_id"], d["tdlr_1_id"], d["tdlr_2_id"])
        ]

        # Scan for duty conflicts
        for d in relevant_duties:
            duty_serials = {d["primary_sailor_id"], d["tdlr_1_id"], d["tdlr_2_id"]}
            watch_buddies = duty_serials - {applicant_id}

            for buddy_id in watch_buddies:
                for active_leave in self.leaves:
                    if active_leave["sailor_id"] == buddy_id and active_leave["status"] in ["SUBMITTED", "TDLR_VERIFIED", "OFFICER_APPROVED"]:
                        # Detect calendar overlap
                        overlap = max(new_start, active_leave["start_date"]) <= min(new_end, active_leave["end_date"])
                        if overlap:
                            errors.append(
                                f"Critical Conflict: Duty {d['duty_id']} ({d['duty_name']}). "
                                f"Watchkeeper Ser {buddy_id} is on leave from {active_leave['start_date']} to {active_leave['end_date']}."
                            )

        return (len(errors) == 0, errors)
```

# **7\. Web Portal Implementation Plan**

## **7.1 Key User Interface Modules**

* **Console Dashboard:** Displays operational readiness gauges, watches currently staffed, and a dynamic timeline showing active shift personnel.  
* **Application & Scheduling Wizard:** Calendar interface restricting selection strictly to allowed 20-day or 15-day blocks, preventing manual submission errors.  
* **TDLR Relief Ledger:** Overview of primary tasks, active relief assignments, and one-click cryptographic acknowledgments for designated substitutes.  
* **Officer Approval Deck:** Comprehensive operational review console that visualizes the entire 33-duty readiness matrix before an officer signs off on a leave block.

## **7.2 Implementation Schedule & Milestones**

| Phase | Milestone Description | Start Date | Finish Date | Status | Required Deliverables |
| :---- | :---- | :---- | :---- | :---- | :---- |
| M-1 | Systems Requirement & Security Baseline | W1 | W2 | Complete | Approved Functional Spec & Architecture Blueprint |
| M-2 | Database Schema & Constraints Setup | W3 | W4 | In Progress | PostgreSQL DB Init, FK Rigidity, Table Constraints |
| M-3 | Core Engine & Backend Validation Dev | W5 | W7 | Scheduled | Python Fast-API Routes & Conflict Engine Tests |
| M-4 | Modern Web UI & Dashboard Build | W8 | W10 | Scheduled | React/Vite Dashboards & Relief Handover Portal |
| M-5 | Air-Gapped Simulation & User Acceptance | W11 | W12 | Scheduled | Stress Simulation across 33 Duties & Security Audit |
| M-6 | Final Deployment & Station Commission | W13 | W14 | Scheduled | Deployment on COMNETCEN Base LAN Cluster |

## **7.3 Administrative Approval Workflow**

```
[ Sailor Submits Leave Request ]
               |
               v
[ Automated Constraint Engine ]
      |                 |
(Validation Passed)   (Conflict Detected)
      |                 |
      v                 v
[ Await TDLR 1 & 2 ]   [ Hard Rejection: Reason Flagged ]
[ Digital Sign-off ]
      |
      v
[ Officer-in-Charge Final Review ]
      |                 |
  (Approved)        (Rejected)
      |                 |
      v                 v
[ Shift Register ]   [ Returned to Sailor ]
[ Auto-Updated   ]
```

1. **Submission Phase:** The applicant enters their requested block through the digital interface.  
2. **Rule Enforcement:** The conflict engine screens the proposed dates against database constraints (entitlements, block length, active duty clashes).  
3. **Relief Endorsement:** If clear, the request automatically routes to designated TDLR 1 and TDLR 2 personnel for digital concurrence and task hand-off.  
4. **Command Approval:** The Officer-in-Charge reviews the verified request alongside the real-time COMNETCEN duty chart.  
5. **Roster Integration:** Upon final digital authorization, watch rosters, gateway permissions, and emergency logs update across the center automatically.

