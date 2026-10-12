# SAMS v18 — Unified Administrative + HR Suite

This release merges the useful HR Monitoring System functions into SAMS while keeping SAMS as the main authenticated application and Firebase project.

## Added / Upgraded

### Unified Employee Masterlist
The existing SAMS Employee Masterlist is expanded with:
- Employee No.
- Position
- Personnel Type
- Employment Status
- Leave Basis
- Date Hired
- Plantilla Item
- Salary Grade / Step
- Basic Salary
- PERA / ACA
- Station Code
- Mobile
- Email / Office
- linked SAMS UID when available

The same master employee ID is used by Supplies, Equipment, DTR, Leave, 201 File, Training, Performance, and Leave Ledger.

### DTR / Attendance
- Monthly employee loading
- Detailed tardiness and undertime entry
- CSC-equivalent monitoring computation
- Pay-status / leave-charge review
- Division action and payroll notes
- Configurable teaching schedule treatment

### Consolidated HR
- Monthly DTR summary
- Saved monthly snapshots
- DTR CSV export
- Leave-register CSV export
- Employee Leave Card / Leave Ledger
- Opening VL / SL / VSC balances
- Approved-leave deductions
- DTR attendance-equivalent deductions
- Configurable monthly VL / SL accrual settings

### 201 File Monitoring
Tracks:
- PDS
- SALN
- Appointment
- TOR / Diploma
- Eligibility
- NBI / Medical

### Training / L&D
- Training history
- Provider, dates, hours, level, certificate availability
- Employees can view their own records
- HR/Admin manages records

### Performance
- IPCRF / OPCRF
- Period
- Numeric and adjectival rating
- Submission status
- Employees can view their own records
- HR/Admin manages records

### Reliability
- Existing soft-delete model retained
- New HR records use role-based Firestore access
- Existing authentication, audit, notifications, online CS Form No. 6, RIS, equipment slip, walk-in workflows, dashboard, reports and backup export remain intact

## Important policy note
The automated leave ledger is a monitoring aid. VL/SL accrual values and teaching attendance treatment are configurable under Settings. Authorized HR personnel should validate the applicable policy and source records before using balances for official action.

## Deployment
1. Replace `index.html` in the GitHub Pages repository.
2. Firebase Console -> Firestore Database -> Rules
3. Replace the current rules with the included `firestore.rules`
4. Click Publish
5. Wait for GitHub Pages deployment and press Ctrl + F5

Do not retire the old HR database until data migration/reconciliation is completed.
