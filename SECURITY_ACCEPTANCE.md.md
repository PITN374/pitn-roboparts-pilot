# PITN.ai Security Acceptance Record (Phase 4)

- **Deployment URL:** https://humanoidsandcobots.vercel.app/admin
- **Status:** PASS / Accepted for Pilot
- **Date:** August 2026

## PASS/FAIL Acceptance Matrix

| Test Item | Verification Detail | Result |
| :--- | :--- | :--- |
| **1. RLS Enabled & Policies** | Row-Level Security is active on Supabase tables (`parts` & `rfqs`) with proper conditional rules. | **PASS** |
| **2. Logged-out vs Admin Role** | Unauthenticated users hitting `/admin` are blocked by the password gate; Content vs Admin role boundaries are strictly enforced. | **PASS** |
| **3. Direct Unauthenticated API Call** | Direct API or Supabase write requests from unauthenticated clients without valid permissions are rejected. | **PASS** |
| **4. No Secrets Exposed** | Privileged keys remain securely server-side; no service-role secrets are exposed in the browser bundle. | **PASS** |
| **5. Password Verification Location** | The temporary `/admin` passcode check and role-based permissions are securely handled. | **PASS** |

*Note: The "Simulating Role" toggle inager admin UI is strictly a frontend test helper for verification. Real authentication, authorization, and review constraints are strictly enforced server-side via Supabase RLS policies.*