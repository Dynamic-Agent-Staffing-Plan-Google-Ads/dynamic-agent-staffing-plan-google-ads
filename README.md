# Dynamic Agent Staffing Plan Google Ads


## Google Case Study
**AUTHORS (Equal Contribution)**: Agarwal Vedaant, Raturi Atharv, Voutov Monika, Zhivotov Konstantin

## INTRODUCTION

Millions of businesses advertise on Google, with thousands of new advertisers joining daily. To support high-potential advertisers, Google provides 60-day personal onboarding through dedicated local agents. Each agent can support up to 10 advertisers, but fluctuating daily sign-ups create challenges in matching supply (agents) with demand (eligible advertisers). Overstaffing leads to idle costs; understaffing reduces incremental revenue from delayed or missed onboarding. This project builds a month-by-month dynamic staffing plan to optimize cost and support quality across regions.

## OBJECTIVE

The goal is to maximize net revenue by dynamically hiring and firing agents based on forecasted advertiser sign-ups.

**Decision Variable**: 

Number of agents to hire/fire each month per region, s.t:

* 1-month ramp-up period (hire)

* 1-month notice period + 40% salary penalty (fire)

**Key Constraints**:

* Each agent handles ≤ 10 advertisers
* Advertisers stay for 60 days
* Eligible advertisers only (budget above threshold)
* Agent support boosts revenue via probabilistic incremental uplift

## FUTURE WORK AND SUGGESTIONS

The proposed implementation follows a greedy assignment algorithm, in which all eligible advertisers are immediately assigned to agents. While this ensures maximum coverage, it may not yield the optimal staffing plan under cost constraints. Therefore, proposal for future work is to utilize a wait pool and assignment delays – within the allowed 60 day window – to reduce unnecessary hires during temporary demand peaks. In some cases, advertisers may not need be assigned at all if their expected uplift does not justify the hiring/firing cost.

For the original problem statement, Google assumes agent assignment within their respective country. We propose exploring cross-country agent assignments between countries with overlapping languages and time zones(e.g., USA and Canada), to smooth out capacity bottlenecks and leverage global resources more efficiently.

Lastly, integrating seasonality should be considered. Demand surges during certain periods (e.g., Q2 and Q4) suggest that hiring ramps and firing cooldown periods of 4–6 months would more realistically reflect operational constraints and workforce morale.

