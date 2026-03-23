# P05 · The Recovery Window (MD+1)

**Section:** 02 - The High-Performance Microcycle

**Workflow step:** Step 1 of 5

**Current version:** 

**Status:** ✅ Tested and approved

**Last updated:** March 2026

---

## 📌 Prompt Text (v1.0 — current)

```
Role: You are a Lead Recovery Specialist and Sports Scientist for an elite European football club.

Action: Analyze the "Inflammatory & Metabolic State" for EVERY Player ID [player_id] using the Physical Pillar metrics. Return in JSON format.

Context: It is MD+1 (24 hours post-match). We are identifying "Stalled Recovery" patterns. This analysis determines if the player moves to CNS Reset (P06) or requires an extended recovery protocol.

Inputs:
- Physical Pillar Data: {
  "physical_readiness_report": [
    {
      "player_id": "824001",
      "physical_pillar": {
        "current_distance_km": 4.2,
        "high_speed_running_m": 12,
        "sprint_distance_m": 0,
        "accelerations": 12,
        "decelerations": 15,
        "player_load": 185,
        "metabolic_power": 2.1
      }
    },
    {
      "player_id": "824002",
      "physical_pillar": {
        "current_distance_km": 10.8,
        "high_speed_running_m": 840,
        "sprint_distance_m": 310,
        "accelerations": 45,
        "decelerations": 52,
        "player_load": 840,
        "metabolic_power": 10.5
      }
    },
    {
      "player_id": "824003",
      "physical_pillar": {
        "current_distance_km": 9.5,
        "high_speed_running_m": 320,
        "sprint_distance_m": 120,
        "accelerations": 22,
        "decelerations": 31,
        "player_load": 690,
        "metabolic_power": 8.8
      }
    },
    {
      "player_id": "824004",
      "physical_pillar": {
        "current_distance_km": 9.7,
        "high_speed_running_m": 290,
        "sprint_distance_m": 115,
        "accelerations": 25,
        "decelerations": 28,
        "player_load": 710,
        "metabolic_power": 8.9
      }
    },
    {
      "player_id": "824005",
      "physical_pillar": {
        "current_distance_km": 9.1,
        "high_speed_running_m": 790,
        "sprint_distance_m": 285,
        "accelerations": 38,
        "decelerations": 41,
        "player_load": 780,
        "metabolic_power": 10.1
      }
    },
    {
      "player_id": "824006",
      "physical_pillar": {
        "current_distance_km": 11.9,
        "high_speed_running_m": 610,
        "sprint_distance_m": 90,
        "accelerations": 58,
        "decelerations": 65,
        "player_load": 910,
        "metabolic_power": 11.2
      }
    },
    {
      "player_id": "824007",
      "physical_pillar": {
        "current_distance_km": 12.4,
        "high_speed_running_m": 920,
        "sprint_distance_m": 180,
        "accelerations": 62,
        "decelerations": 74,
        "player_load": 985,
        "metabolic_power": 12.0
      }
    },
    {
      "player_id": "824008",
      "physical_pillar": {
        "current_distance_km": 11.1,
        "high_speed_running_m": 880,
        "sprint_distance_m": 195,
        "accelerations": 55,
        "decelerations": 68,
        "player_load": 890,
        "metabolic_power": 11.5
      }
    },
    {
      "player_id": "824009",
      "physical_pillar": {
        "current_distance_km": 10.2,
        "high_speed_running_m": 1050,
        "sprint_distance_m": 410,
        "accelerations": 51,
        "decelerations": 48,
        "player_load": 920,
        "metabolic_power": 11.8
      }
    },
    {
      "player_id": "824010",
      "physical_pillar": {
        "current_distance_km": 10.5,
        "high_speed_running_m": 810,
        "sprint_distance_m": 380,
        "accelerations": 48,
        "decelerations": 42,
        "player_load": 850,
        "metabolic_power": 11.0
      }
    },
    {
      "player_id": "824011",
      "physical_pillar": {
        "current_distance_km": 7.8,
        "high_speed_running_m": 910,
        "sprint_distance_m": 340,
        "accelerations": 35,
        "decelerations": 38,
        "player_load": 720,
        "metabolic_power": 10.4
      }
    },
    {
      "player_id": "824012",
      "physical_pillar": {
        "current_distance_km": 3.2,
        "high_speed_running_m": 280,
        "sprint_distance_m": 95,
        "accelerations": 18,
        "decelerations": 22,
        "player_load": 240,
        "metabolic_power": 9.2
      }
    },
    {
      "player_id": "824013",
      "physical_pillar": {
        "current_distance_km": 2.1,
        "high_speed_running_m": 190,
        "sprint_distance_m": 60,
        "accelerations": 12,
        "decelerations": 14,
        "player_load": 160,
        "metabolic_power": 8.5
      }
    },
    {
      "player_id": "824014",
      "physical_pillar": {
        "current_distance_km": 1.2,
        "high_speed_running_m": 85,
        "sprint_distance_m": 30,
        "accelerations": 8,
        "decelerations": 10,
        "player_load": 95,
        "metabolic_power": 8.1
      }
    },
    {
      "player_id": "824015",
      "physical_pillar": {
        "current_distance_km": 0,
        "high_speed_running_m": 0,
        "sprint_distance_m": 0,
        "accelerations": 0,
        "decelerations": 0,
        "player_load": 0,
        "metabolic_power": 0
      }
    },
    {
      "player_id": "824016",
      "physical_pillar": {
        "current_distance_km": 0,
        "high_speed_running_m": 0,
        "sprint_distance_m": 0,
        "accelerations": 0,
        "decelerations": 0,
        "player_load": 0,
        "metabolic_power": 0
      }
    },
    {
      "player_id": "824017",
      "physical_pillar": {
        "current_distance_km": 0,
        "high_speed_running_m": 0,
        "sprint_distance_m": 0,
        "accelerations": 0,
        "decelerations": 0,
        "player_load": 0,
        "metabolic_power": 0
      }
    },
    {
      "player_id": "824018",
      "physical_pillar": {
        "current_distance_km": 0,
        "high_speed_running_m": 0,
        "sprint_distance_m": 0,
        "accelerations": 0,
        "decelerations": 0,
        "player_load": 0,
        "metabolic_power": 0
      }
    },
    {
      "player_id": "824019",
      "physical_pillar": {
        "current_distance_km": 0,
        "high_speed_running_m": 0,
        "sprint_distance_m": 0,
        "accelerations": 0,
        "decelerations": 0,
        "player_load": 0,
        "metabolic_power": 0
      }
    },
    {
      "player_id": "824020",
      "physical_pillar": {
        "current_distance_km": 0,
        "high_speed_running_m": 0,
        "sprint_distance_m": 0,
        "accelerations": 0,
        "decelerations": 0,
        "player_load": 0,
        "metabolic_power": 0
      }
    },
    {
      "player_id": "824021",
      "physical_pillar": {
        "current_distance_km": 0,
        "high_speed_running_m": 0,
        "sprint_distance_m": 0,
        "accelerations": 0,
        "decelerations": 0,
        "player_load": 0,
        "metabolic_power": 0
      }
    },
    {
      "player_id": "824022",
      "physical_pillar": {
        "current_distance_km": 0,
        "high_speed_running_m": 0,
        "sprint_distance_m": 0,
        "accelerations": 0,
        "decelerations": 0,
        "player_load": 0,
        "metabolic_power": 0
      }
    }
  ]
}
- HRV Delta: [hrv_delta]% (Change vs. 7-day rolling baseline)
- Sleep Efficiency: [sleep_eff]% (Quality + Duration score)
- Muscle Soreness: [soreness_val] (Subjective Scale 1-10)

Logic & Thresholds (Mapping to P01 Metrics):
1. Mechanical Window: If "Decelerations" > 60 OR "Accelerations" > 60, flag as "High Eccentric Loading" (+24h recovery extension).
2. Volumetric Load: If "Player Load" status is "Critical" or "Very High," flag for "Systemic Inflammation."
3. Metabolic Window: If [hrv_delta] < -15%, categorize as "Autonomic Nervous System Lag."
4. Clearance: Player is "Cleared for MD+2" ONLY if weighted recovery completion > 70%.

Constraints:
- Maintain a clinical and diagnostic tone.
- Ensure the JSON structure matches the 'matchday_readiness_report' standard.

Recovery Window Data (JSON):
{
  "recovery_analysis_md_plus_1": {
    "player_id": "[player_id]",
    "metrics_reviewed": {
      "load_volume": "[Value from Player Load]",
      "mechanical_stress": "[Value from Decelerations]",
      "metabolic_impact": "[hrv_delta]"
    },
    "recovery_completion_pct": [score_0_100],
    "status": "[Recovering / Stalled / Critical]",
    "clearance_next_phase": [true/false],
    "dominant_fatigue_type": "[Mechanical / Metabolic / Neural]",
    "specialist_intervention": "[e.g., Cryo-chamber, Manual Therapy, Active Recovery, Total Rest]"
  }
}
```

**Placeholders to Fill**

| Placeholder | Source / Description | Example |
| :--- | :--- | :--- |
| `[player_id]` | 6-digit identification number | `824006` |
| `[p01_physical_pillar_json]` | The physical output from `P01` | `{ "metric": "Decelerations", "value": 65... }` |
| `[hrv_delta]` | % variance in Heart Rate Variability | `-18%` |
| `[sleep_eff]` | Sleep quality score (1-100) | `72` |
| `[soreness_val]` | Subjective muscle pain (1-10) | `8` |

---

## 🏢 Intended Workflow or Task

This prompt acts as the "Gatekeeper" for the training week. It filters the squad into three distinct training paths based on their physiological exit from the previous match.

* **Trigger:** Availability of GPS match data and MD+1 morning wellness/HRV.
* **Actor:** Sports Scientist &nbsp; • &nbsp; Medical aStaff (Head of Recovery, Phisiotherapists, Athletic Trainers).
* **Timing:** Exactly 24 hours post-match (`MD+1`).
* **Next step:** `P06` — CNS & Neural Reset for cleared players.

```
GPS/Wellness Data → [P05 runs] → Recovery Report 
  ↳ [IF Cleared] → P04/P06 Tactical Prep 
  ↳ [IF Stalled] → Medical Intervention
```

---

## ❗ Problem Being Solved

Prevents "Compounded Fatigue" where players are pushed into high-intensity sessions (`P07`) while still suffering from structural tissue damage or systemic inflammation.

**Pain Points Addressed:**

- Inaccurate Clearance: Distinguishes between a player who is "tired" (systemic) and one who has mechanical tissue damage (structural). `P05` prevents premature return-to-play through automated biomechanical filtering.

- Protocol Automation: Automatically assigns recovery interventions (e.g., `Cryotherapy` vs. `Active Recovery`) based on the dominant fatigue type detected in the `[hrv_delta]` and `[soreness_val]` correlation.

---

## ⚡ Automation Potential

**Overall Level:** `High`

| Dimension | Assessment |
| :--- | :--- |
| **Repetitiveness** | `Very high` &nbsp; - &nbsp; Every player, every `MD+1` without exception. |
| **Data availability** | `High` &nbsp; - &nbsp; Direct mapping from `P01` and Wearable APIs. |
| **Human judgment** | `Medium` &nbsp; - &nbsp; Lead Physio must confirm "Critical" red flags. |

**Human-in-the-Loop Role:** The Head of Recovery and Lead Physio act as final validator. While the AI automates 95% of the screening, any player with a `Critical` status or a combined `hrv_delta` and `soreness_val` anomaly requires a manual clinical assessment before the `MD+2` training session begins.

**Estimated time saving:** ~90% (Automated squad-wide triage vs. individual morning consultations).

---

## ⚠️ Risks and Limitations

| Risk | Level | Mitigation |
| :--- | :---: | :--- |
| **False Negatives** | `Medium` | Players may hide soreness to play. Cross-reference with objective `Deceleration` counts from `P01`. |
| **Data Siloing** | `Low` | The `P05` JSON ensures recovery data flows directly into the Decision Layer (Section 03). |

**Overall Risk Rating:LOW** - Suitable for automated triage with mandatory Physio-led intervention for all "Red Flag" anomalies.

---

## 🔄 Version History

### v1.0 — Initial Draft

**Date:** March 15 2026

**Prompt:** 

```
Role: You are a Lead Recovery Specialist and Sports Scientist for an elite European football club.

Action: Analyze the "Inflammatory & Metabolic State" for EVERY Player ID [player_id] using the Physical Pillar metrics. Return in JSON format.

Context: It is MD+1 (24 hours post-match). We are identifying "Stalled Recovery" patterns. This analysis determines if the player moves to CNS Reset (P06) or requires an extended recovery protocol.

Inputs:
- Physical Pillar Data: {
  "physical_readiness_report": [
    {
      "player_id": "824001",
      "physical_pillar": {
        "current_distance_km": 4.2,
        "high_speed_running_m": 12,
        "sprint_distance_m": 0,
        "accelerations": 12,
        "decelerations": 15,
        "player_load": 185,
        "metabolic_power": 2.1
      }
    },
    {
      "player_id": "824002",
      "physical_pillar": {
        "current_distance_km": 10.8,
        "high_speed_running_m": 840,
        "sprint_distance_m": 310,
        "accelerations": 45,
        "decelerations": 52,
        "player_load": 840,
        "metabolic_power": 10.5
      }
    },
    {
      "player_id": "824003",
      "physical_pillar": {
        "current_distance_km": 9.5,
        "high_speed_running_m": 320,
        "sprint_distance_m": 120,
        "accelerations": 22,
        "decelerations": 31,
        "player_load": 690,
        "metabolic_power": 8.8
      }
    },
    {
      "player_id": "824004",
      "physical_pillar": {
        "current_distance_km": 9.7,
        "high_speed_running_m": 290,
        "sprint_distance_m": 115,
        "accelerations": 25,
        "decelerations": 28,
        "player_load": 710,
        "metabolic_power": 8.9
      }
    },
    {
      "player_id": "824005",
      "physical_pillar": {
        "current_distance_km": 9.1,
        "high_speed_running_m": 790,
        "sprint_distance_m": 285,
        "accelerations": 38,
        "decelerations": 41,
        "player_load": 780,
        "metabolic_power": 10.1
      }
    },
    {
      "player_id": "824006",
      "physical_pillar": {
        "current_distance_km": 11.9,
        "high_speed_running_m": 610,
        "sprint_distance_m": 90,
        "accelerations": 58,
        "decelerations": 65,
        "player_load": 910,
        "metabolic_power": 11.2
      }
    },
    {
      "player_id": "824007",
      "physical_pillar": {
        "current_distance_km": 12.4,
        "high_speed_running_m": 920,
        "sprint_distance_m": 180,
        "accelerations": 62,
        "decelerations": 74,
        "player_load": 985,
        "metabolic_power": 12.0
      }
    },
    {
      "player_id": "824008",
      "physical_pillar": {
        "current_distance_km": 11.1,
        "high_speed_running_m": 880,
        "sprint_distance_m": 195,
        "accelerations": 55,
        "decelerations": 68,
        "player_load": 890,
        "metabolic_power": 11.5
      }
    },
    {
      "player_id": "824009",
      "physical_pillar": {
        "current_distance_km": 10.2,
        "high_speed_running_m": 1050,
        "sprint_distance_m": 410,
        "accelerations": 51,
        "decelerations": 48,
        "player_load": 920,
        "metabolic_power": 11.8
      }
    },
    {
      "player_id": "824010",
      "physical_pillar": {
        "current_distance_km": 10.5,
        "high_speed_running_m": 810,
        "sprint_distance_m": 380,
        "accelerations": 48,
        "decelerations": 42,
        "player_load": 850,
        "metabolic_power": 11.0
      }
    },
    {
      "player_id": "824011",
      "physical_pillar": {
        "current_distance_km": 7.8,
        "high_speed_running_m": 910,
        "sprint_distance_m": 340,
        "accelerations": 35,
        "decelerations": 38,
        "player_load": 720,
        "metabolic_power": 10.4
      }
    },
    {
      "player_id": "824012",
      "physical_pillar": {
        "current_distance_km": 3.2,
        "high_speed_running_m": 280,
        "sprint_distance_m": 95,
        "accelerations": 18,
        "decelerations": 22,
        "player_load": 240,
        "metabolic_power": 9.2
      }
    },
    {
      "player_id": "824013",
      "physical_pillar": {
        "current_distance_km": 2.1,
        "high_speed_running_m": 190,
        "sprint_distance_m": 60,
        "accelerations": 12,
        "decelerations": 14,
        "player_load": 160,
        "metabolic_power": 8.5
      }
    },
    {
      "player_id": "824014",
      "physical_pillar": {
        "current_distance_km": 1.2,
        "high_speed_running_m": 85,
        "sprint_distance_m": 30,
        "accelerations": 8,
        "decelerations": 10,
        "player_load": 95,
        "metabolic_power": 8.1
      }
    },
    {
      "player_id": "824015",
      "physical_pillar": {
        "current_distance_km": 0,
        "high_speed_running_m": 0,
        "sprint_distance_m": 0,
        "accelerations": 0,
        "decelerations": 0,
        "player_load": 0,
        "metabolic_power": 0
      }
    },
    {
      "player_id": "824016",
      "physical_pillar": {
        "current_distance_km": 0,
        "high_speed_running_m": 0,
        "sprint_distance_m": 0,
        "accelerations": 0,
        "decelerations": 0,
        "player_load": 0,
        "metabolic_power": 0
      }
    },
    {
      "player_id": "824017",
      "physical_pillar": {
        "current_distance_km": 0,
        "high_speed_running_m": 0,
        "sprint_distance_m": 0,
        "accelerations": 0,
        "decelerations": 0,
        "player_load": 0,
        "metabolic_power": 0
      }
    },
    {
      "player_id": "824018",
      "physical_pillar": {
        "current_distance_km": 0,
        "high_speed_running_m": 0,
        "sprint_distance_m": 0,
        "accelerations": 0,
        "decelerations": 0,
        "player_load": 0,
        "metabolic_power": 0
      }
    },
    {
      "player_id": "824019",
      "physical_pillar": {
        "current_distance_km": 0,
        "high_speed_running_m": 0,
        "sprint_distance_m": 0,
        "accelerations": 0,
        "decelerations": 0,
        "player_load": 0,
        "metabolic_power": 0
      }
    },
    {
      "player_id": "824020",
      "physical_pillar": {
        "current_distance_km": 0,
        "high_speed_running_m": 0,
        "sprint_distance_m": 0,
        "accelerations": 0,
        "decelerations": 0,
        "player_load": 0,
        "metabolic_power": 0
      }
    },
    {
      "player_id": "824021",
      "physical_pillar": {
        "current_distance_km": 0,
        "high_speed_running_m": 0,
        "sprint_distance_m": 0,
        "accelerations": 0,
        "decelerations": 0,
        "player_load": 0,
        "metabolic_power": 0
      }
    },
    {
      "player_id": "824022",
      "physical_pillar": {
        "current_distance_km": 0,
        "high_speed_running_m": 0,
        "sprint_distance_m": 0,
        "accelerations": 0,
        "decelerations": 0,
        "player_load": 0,
        "metabolic_power": 0
      }
    }
  ]
}
- HRV Delta: [hrv_delta]% (Change vs. 7-day rolling baseline)
- Sleep Efficiency: [sleep_eff]% (Quality + Duration score)
- Muscle Soreness: [soreness_val] (Subjective Scale 1-10)

Logic & Thresholds (Mapping to P01 Metrics):
1. Mechanical Window: If "Decelerations" > 60 OR "Accelerations" > 60, flag as "High Eccentric Loading" (+24h recovery extension).
2. Volumetric Load: If "Player Load" status is "Critical" or "Very High," flag for "Systemic Inflammation."
3. Metabolic Window: If [hrv_delta] < -15%, categorize as "Autonomic Nervous System Lag."
4. Clearance: Player is "Cleared for MD+2" ONLY if weighted recovery completion > 70%.

Constraints:
- Maintain a clinical and diagnostic tone.
- Ensure the JSON structure matches the 'matchday_readiness_report' standard.

Recovery Window Data (JSON):
{
  "recovery_analysis_md_plus_1": {
    "player_id": "[player_id]",
    "metrics_reviewed": {
      "load_volume": "[Value from Player Load]",
      "mechanical_stress": "[Value from Decelerations]",
      "metabolic_impact": "[hrv_delta]"
    },
    "recovery_completion_pct": [score_0_100],
    "status": "[Recovering / Stalled / Critical]",
    "clearance_next_phase": [true/false],
    "dominant_fatigue_type": "[Mechanical / Metabolic / Neural]",
    "specialist_intervention": "[e.g., Cryo-chamber, Manual Therapy, Active Recovery, Total Rest]"
  }
}
```

**Output:**

```
{
  "matchday_readiness_report": [
    {
      "recovery_analysis_md_plus_1": {
        "player_id": "824001",
        "metrics_reviewed": {
          "load_volume": 185,
          "mechanical_stress": 15,
          "metabolic_impact": "N/A"
        },
        "recovery_completion_pct": 95,
        "status": "Recovering",
        "clearance_next_phase": true,
        "dominant_fatigue_type": "None",
        "specialist_intervention": "Active Recovery (P06)"
      }
    },
    {
      "recovery_analysis_md_plus_1": {
        "player_id": "824002",
        "metrics_reviewed": {
          "load_volume": 840,
          "mechanical_stress": 52,
          "metabolic_impact": "N/A"
        },
        "recovery_completion_pct": 68,
        "status": "Stalled",
        "clearance_next_phase": false,
        "dominant_fatigue_type": "Metabolic",
        "specialist_intervention": "Cryo-chamber & Contrast Baths"
      }
    },
    {
      "recovery_analysis_md_plus_1": {
        "player_id": "824003",
        "metrics_reviewed": {
          "load_volume": 690,
          "mechanical_stress": 31,
          "metabolic_impact": "N/A"
        },
        "recovery_completion_pct": 78,
        "status": "Recovering",
        "clearance_next_phase": true,
        "dominant_fatigue_type": "Metabolic",
        "specialist_intervention": "Active Recovery (P06)"
      }
    },
    {
      "recovery_analysis_md_plus_1": {
        "player_id": "824004",
        "metrics_reviewed": {
          "load_volume": 710,
          "mechanical_stress": 28,
          "metabolic_impact": "N/A"
        },
        "recovery_completion_pct": 76,
        "status": "Recovering",
        "clearance_next_phase": true,
        "dominant_fatigue_type": "Metabolic",
        "specialist_intervention": "Active Recovery (P06)"
      }
    },
    {
      "recovery_analysis_md_plus_1": {
        "player_id": "824005",
        "metrics_reviewed": {
          "load_volume": 780,
          "mechanical_stress": 41,
          "metabolic_impact": "N/A"
        },
        "recovery_completion_pct": 72,
        "status": "Recovering",
        "clearance_next_phase": true,
        "dominant_fatigue_type": "Metabolic",
        "specialist_intervention": "Manual Therapy"
      }
    },
    {
      "recovery_analysis_md_plus_1": {
        "player_id": "824006",
        "metrics_reviewed": {
          "load_volume": 910,
          "mechanical_stress": 65,
          "metabolic_impact": "N/A"
        },
        "recovery_completion_pct": 52,
        "status": "Critical",
        "clearance_next_phase": false,
        "dominant_fatigue_type": "Mechanical",
        "specialist_intervention": "High Eccentric Extension: Total Rest & Soft Tissue Work"
      }
    },
    {
      "recovery_analysis_md_plus_1": {
        "player_id": "824007",
        "metrics_reviewed": {
          "load_volume": 985,
          "mechanical_stress": 74,
          "metabolic_impact": "N/A"
        },
        "recovery_completion_pct": 45,
        "status": "Critical",
        "clearance_next_phase": false,
        "dominant_fatigue_type": "Mechanical",
        "specialist_intervention": "High Eccentric Extension: Systematic Anti-Inflammatory Protocol"
      }
    },
    {
      "recovery_analysis_md_plus_1": {
        "player_id": "824008",
        "metrics_reviewed": {
          "load_volume": 890,
          "mechanical_stress": 68,
          "metabolic_impact": "N/A"
        },
        "recovery_completion_pct": 55,
        "status": "Critical",
        "clearance_next_phase": false,
        "dominant_fatigue_type": "Mechanical",
        "specialist_intervention": "High Eccentric Extension: Compression & Cryo"
      }
    },
    {
      "recovery_analysis_md_plus_1": {
        "player_id": "824009",
        "metrics_reviewed": {
          "load_volume": 920,
          "mechanical_stress": 48,
          "metabolic_impact": "N/A"
        },
        "recovery_completion_pct": 62,
        "status": "Stalled",
        "clearance_next_phase": false,
        "dominant_fatigue_type": "Metabolic",
        "specialist_intervention": "Systemic Inflammation: Pool Recovery"
      }
    },
    {
      "recovery_analysis_md_plus_1": {
        "player_id": "824010",
        "metrics_reviewed": {
          "load_volume": 850,
          "mechanical_stress": 42,
          "metabolic_impact": "N/A"
        },
        "recovery_completion_pct": 69,
        "status": "Stalled",
        "clearance_next_phase": false,
        "dominant_fatigue_type": "Metabolic",
        "specialist_intervention": "Nutritional Repletion & Manual Therapy"
      }
    },
    {
      "recovery_analysis_md_plus_1": {
        "player_id": "824011",
        "metrics_reviewed": {
          "load_volume": 720,
          "mechanical_stress": 38,
          "metabolic_impact": "N/A"
        },
        "recovery_completion_pct": 75,
        "status": "Recovering",
        "clearance_next_phase": true,
        "dominant_fatigue_type": "Metabolic",
        "specialist_intervention": "Active Recovery (P06)"
      }
    },
    {
      "recovery_analysis_md_plus_1": {
        "player_id": "824012",
        "metrics_reviewed": {
          "load_volume": 240,
          "mechanical_stress": 22,
          "metabolic_impact": "N/A"
        },
        "recovery_completion_pct": 92,
        "status": "Recovering",
        "clearance_next_phase": true,
        "dominant_fatigue_type": "None",
        "specialist_intervention": "Standard Post-Match Activation"
      }
    },
    {
      "recovery_analysis_md_plus_1": {
        "player_id": "824013",
        "metrics_reviewed": {
          "load_volume": 160,
          "mechanical_stress": 14,
          "metabolic_impact": "N/A"
        },
        "recovery_completion_pct": 96,
        "status": "Recovering",
        "clearance_next_phase": true,
        "dominant_fatigue_type": "None",
        "specialist_intervention": "Standard Post-Match Activation"
      }
    },
    {
      "recovery_analysis_md_plus_1": {
        "player_id": "824014",
        "metrics_reviewed": {
          "load_volume": 95,
          "mechanical_stress": 10,
          "metabolic_impact": "N/A"
        },
        "recovery_completion_pct": 98,
        "status": "Recovering",
        "clearance_next_phase": true,
        "dominant_fatigue_type": "None",
        "specialist_intervention": "Standard Post-Match Activation"
      }
    }
  ]
}
```

### v1.0 — Initial Draft ✅ Current

**Date:** March 16 2026

**Changes:** Expanded the input/output logic to include all 22 Player IDs, ensuring that non-playing squad members (Player Load = 0) are still filtered through the recovery system to confirm baseline readiness.

**Output:**

```
{
  "matchday_readiness_report": [
    {
      "player_id": "824001",
      "recovery_analysis_md_plus_1": {
        "metrics_reviewed": { "load_volume": 185, "mechanical_stress": 15, "metabolic_impact": "-2%" },
        "recovery_completion_pct": 94,
        "status": "Recovering",
        "clearance_next_phase": true,
        "dominant_fatigue_type": "None",
        "specialist_intervention": "Active Recovery"
      }
    },
    {
      "player_id": "824002",
      "recovery_analysis_md_plus_1": {
        "metrics_reviewed": { "load_volume": 840, "mechanical_stress": 52, "metabolic_impact": "-18%" },
        "recovery_completion_pct": 62,
        "status": "Stalled",
        "clearance_next_phase": false,
        "dominant_fatigue_type": "Metabolic",
        "specialist_intervention": "CNS Reset (P06) + Hydrotherapy"
      }
    },
    {
      "player_id": "824003",
      "recovery_analysis_md_plus_1": {
        "metrics_reviewed": { "load_volume": 690, "mechanical_stress": 31, "metabolic_impact": "-8%" },
        "recovery_completion_pct": 78,
        "status": "Recovering",
        "clearance_next_phase": true,
        "dominant_fatigue_type": "Metabolic",
        "specialist_intervention": "Manual Therapy"
      }
    },
    {
      "player_id": "824004",
      "recovery_analysis_md_plus_1": {
        "metrics_reviewed": { "load_volume": 710, "mechanical_stress": 28, "metabolic_impact": "-11%" },
        "recovery_completion_pct": 74,
        "status": "Recovering",
        "clearance_next_phase": true,
        "dominant_fatigue_type": "Metabolic",
        "specialist_intervention": "Compression Garments"
      }
    },
    {
      "player_id": "824005",
      "recovery_analysis_md_plus_1": {
        "metrics_reviewed": { "load_volume": 780, "mechanical_stress": 41, "metabolic_impact": "-14%" },
        "recovery_completion_pct": 68,
        "status": "Stalled",
        "clearance_next_phase": false,
        "dominant_fatigue_type": "Metabolic",
        "specialist_intervention": "Cryo-chamber + Nutrition Optimization"
      }
    },
    {
      "player_id": "824006",
      "recovery_analysis_md_plus_1": {
        "metrics_reviewed": { "load_volume": 910, "mechanical_stress": 65, "metabolic_impact": "-12%" },
        "recovery_completion_pct": 55,
        "status": "Critical",
        "clearance_next_phase": false,
        "dominant_fatigue_type": "Mechanical",
        "specialist_intervention": "Extended Recovery Protocol (+24h) + Manual Therapy"
      }
    },
    {
      "player_id": "824007",
      "recovery_analysis_md_plus_1": {
        "metrics_reviewed": { "load_volume": 985, "mechanical_stress": 74, "metabolic_impact": "-22%" },
        "recovery_completion_pct": 42,
        "status": "Critical",
        "clearance_next_phase": false,
        "dominant_fatigue_type": "Mixed (Mechanical/Metabolic)",
        "specialist_intervention": "Total Rest + Anti-inflammatory Protocol"
      }
    },
    {
      "player_id": "824008",
      "recovery_analysis_md_plus_1": {
        "metrics_reviewed": { "load_volume": 890, "mechanical_stress": 68, "metabolic_impact": "-16%" },
        "recovery_completion_pct": 58,
        "status": "Stalled",
        "clearance_next_phase": false,
        "dominant_fatigue_type": "Mechanical",
        "specialist_intervention": "CNS Reset (P06) + Cryo-chamber"
      }
    },
    {
      "player_id": "824009",
      "recovery_analysis_md_plus_1": {
        "metrics_reviewed": { "load_volume": 920, "mechanical_stress": 48, "metabolic_impact": "-19%" },
        "recovery_completion_pct": 61,
        "status": "Stalled",
        "clearance_next_phase": false,
        "dominant_fatigue_type": "Metabolic",
        "specialist_intervention": "Hydrotherapy + Sleep Extension"
      }
    },
    {
      "player_id": "824010",
      "recovery_analysis_md_plus_1": {
        "metrics_reviewed": { "load_volume": 850, "mechanical_stress": 42, "metabolic_impact": "-9%" },
        "recovery_completion_pct": 72,
        "status": "Recovering",
        "clearance_next_phase": true,
        "dominant_fatigue_type": "Metabolic",
        "specialist_intervention": "Active Recovery"
      }
    },
    {
      "player_id": "824011",
      "recovery_analysis_md_plus_1": {
        "metrics_reviewed": { "load_volume": 720, "mechanical_stress": 38, "metabolic_impact": "-5%" },
        "recovery_completion_pct": 82,
        "status": "Recovering",
        "clearance_next_phase": true,
        "dominant_fatigue_type": "Neural",
        "specialist_intervention": "Compression Garments"
      }
    },
    {
      "player_id": "824012",
      "recovery_analysis_md_plus_1": {
        "metrics_reviewed": { "load_volume": 240, "mechanical_stress": 22, "metabolic_impact": "-3%" },
        "recovery_completion_pct": 92,
        "status": "Recovering",
        "clearance_next_phase": true,
        "dominant_fatigue_type": "None",
        "specialist_intervention": "Active Recovery"
      }
    },
    {
      "player_id": "824013",
      "recovery_analysis_md_plus_1": {
        "metrics_reviewed": { "load_volume": 160, "mechanical_stress": 14, "metabolic_impact": "-1%" },
        "recovery_completion_pct": 96,
        "status": "Recovering",
        "clearance_next_phase": true,
        "dominant_fatigue_type": "None",
        "specialist_intervention": "On-field Compensation Session"
      }
    },
    {
      "player_id": "824014",
      "recovery_analysis_md_plus_1": {
        "metrics_reviewed": { "load_volume": 95, "mechanical_stress": 10, "metabolic_impact": "0%" },
        "recovery_completion_pct": 98,
        "status": "Recovering",
        "clearance_next_phase": true,
        "dominant_fatigue_type": "None",
        "specialist_intervention": "On-field Compensation Session"
      }
    },
    {
      "player_id": "824015",
      "recovery_analysis_md_plus_1": {
        "metrics_reviewed": { "load_volume": 0, "mechanical_stress": 0, "metabolic_impact": "0%" },
        "recovery_completion_pct": 100,
        "status": "Recovering",
        "clearance_next_phase": true,
        "dominant_fatigue_type": "None",
        "specialist_intervention": "Sub-maximal Conditioning"
      }
    },
    {
      "player_id": "824016",
      "recovery_analysis_md_plus_1": {
        "metrics_reviewed": { "load_volume": 0, "mechanical_stress": 0, "metabolic_impact": "+2%" },
        "recovery_completion_pct": 100,
        "status": "Recovering",
        "clearance_next_phase": true,
        "dominant_fatigue_type": "None",
        "specialist_intervention": "Full Training Load"
      }
    },
    {
      "player_id": "824017",
      "recovery_analysis_md_plus_1": {
        "metrics_reviewed": { "load_volume": 0, "mechanical_stress": 0, "metabolic_impact": "-1%" },
        "recovery_completion_pct": 100,
        "status": "Recovering",
        "clearance_next_phase": true,
        "dominant_fatigue_type": "None",
        "specialist_intervention": "Full Training Load"
      }
    },
    {
      "player_id": "824018",
      "recovery_analysis_md_plus_1": {
        "metrics_reviewed": { "load_volume": 0, "mechanical_stress": 0, "metabolic_impact": "0%" },
        "recovery_completion_pct": 100,
        "status": "Recovering",
        "clearance_next_phase": true,
        "dominant_fatigue_type": "None",
        "specialist_intervention": "Full Training Load"
      }
    },
    {
      "player_id": "824019",
      "recovery_analysis_md_plus_1": {
        "metrics_reviewed": { "load_volume": 0, "mechanical_stress": 0, "metabolic_impact": "-3%" },
        "recovery_completion_pct": 100,
        "status": "Recovering",
        "clearance_next_phase": true,
        "dominant_fatigue_type": "None",
        "specialist_intervention": "Full Training Load"
      }
    },
    {
      "player_id": "824020",
      "recovery_analysis_md_plus_1": {
        "metrics_reviewed": { "load_volume": 0, "mechanical_stress": 0, "metabolic_impact": "0%" },
        "recovery_completion_pct": 100,
        "status": "Recovering",
        "clearance_next_phase": true,
        "dominant_fatigue_type": "None",
        "specialist_intervention": "Full Training Load"
      }
    },
    {
      "player_id": "824021",
      "recovery_analysis_md_plus_1": {
        "metrics_reviewed": { "load_volume": 0, "mechanical_stress": 0, "metabolic_impact": "+1%" },
        "recovery_completion_pct": 100,
        "status": "Recovering",
        "clearance_next_phase": true,
        "dominant_fatigue_type": "None",
        "specialist_intervention": "Full Training Load"
      }
    },
    {
      "player_id": "824022",
      "recovery_analysis_md_plus_1": {
        "metrics_reviewed": { "load_volume": 0, "mechanical_stress": 0, "metabolic_impact": "0%" },
        "recovery_completion_pct": 100,
        "status": "Recovering",
        "clearance_next_phase": true,
        "dominant_fatigue_type": "None",
        "specialist_intervention": "Full Training Load"
      }
    }
  ]
}
```

**Observed effect:** The updated version achieved 100% squad coverage by introducing baseline defaults for bench players, ensuring no "Data Silos" remained in the 22-man report.








