# Domain Profile

## Field

**Primary:** Environmental Economics / Natural Resource Economics / Development Economics
**Adjacent subfields:** Public Economics, Political Economy, Latin American Economics, Spatial Economics

---

## Target Journals (ranked by tier)

| Tier | Journals |
|------|----------|
| Top-5 | AER, JPE, QJE, REStud, Econometrica |
| Top field | JAERE, JDE, AEJ:Applied, AEJ:Economic Policy, JEP |
| Strong field | JEEM, World Development, Ecological Economics, JEG, EDE, Land Economics |
| Specialty | Latin American Economic Review, Economía (LACEA), Cuadernos de Economía, CEPAL Review, Desarrollo y Sociedad |

---

## Common Data Sources

| Dataset | Type | Access | Notes |
|---------|------|--------|-------|
| INEC ENEMDU | Household survey | Public | Annual; employment, income, poverty — harmonized from 2003; methodology breaks in 2003 and 2014 |
| INEC Censo de Población y Vivienda | Census | Public | 2001, 2010, 2022 waves; parish/canton level; good for baseline controls |
| Ministerio del Ambiente y Agua (MAATE) | Admin | Public | Concession registries, protected areas (SNAP), deforestation alerts |
| Hansen Global Forest Change | Satellite | Public | 30m annual tree cover loss 2001–present; validate against MAATE |
| MODIS / Landsat | Satellite | Public | Land use, NDVI, burned area; free via Google Earth Engine |
| Global Forest Watch | Satellite | Public | Near-real-time deforestation alerts; overlays concessions and protected areas |
| BCE (Banco Central del Ecuador) | Admin/macro | Public | Oil production, fiscal transfers, cantonal GDP proxies |
| SRI (Servicio de Rentas Internas) | Admin | Restricted | Firm-level tax records; useful for local economic activity |
| SIISE / Sistema Integrado de Indicadores | Admin | Public | Social indicators at cantonal/parroquial level; NBI poverty index |
| RAISG Amazonian Network | GIS/spatial | Public | Indigenous territories, protected areas, oil blocks — pan-Amazonian |
| IIRSA / COSIPLAN | Infrastructure | Public | Road and infrastructure projects — useful for transport cost IVs |
| SNAP (Sistema Nacional de Áreas Protegidas) | Admin/GIS | Public | Protected area boundaries, management categories, establishment dates |
| Secretaría de Hidrocarburos | Admin | Public | Oil block concessions, production volumes by block and period |
| World Bank PovcalNet / SEDLAC | Harmonized survey | Public | Cross-country poverty comparisons, LAC harmonized data |

---

## Common Identification Strategies

| Strategy | Typical Application | Key Assumption to Defend |
|----------|-------------------|------------------------|
| Difference-in-Differences | Policy rollout (oil block licensing rounds, PES program expansion) across cantons/parishes | Parallel pre-trends; no anticipation effects; SUTVA (no spillovers to control) |
| Regression Discontinuity | Geographic boundaries (protected area edges, concession borders, administrative cutoffs) | No manipulation of running variable near cutoff; continuity of other covariates at threshold |
| IV / Commodity price shocks | Instrument local resource revenues with global oil/metal price × proven reserves or production capacity | Price shocks exogenous to local conditions; exclusion restriction (no direct effect on welfare beyond resource channel) |
| Shift-share / Bartik | Instrument local exposure using national industry shares × national commodity shocks | Pre-determined shares (Goldsmith-Pinkham et al. 2020); shares uncorrelated with local demand shocks |
| Synthetic Control | Single treated unit (specific province, Yasuní ITT, national moratorium) with good pre-period fit | Convex combination of controls reproduces pre-treatment trend; no spillovers to donor pool |
| Staggered DiD / Event Study | Sequential rollout of concessions, roads, or PES payments | Heterogeneous treatment timing — use Callaway-Sant'Anna (2021) or Sun-Abraham (2021) estimators, not TWFE |
| Spatial RD | Oil block / protected area / indigenous territory boundaries as discontinuities | No sorting across the boundary; boundary placement not endogenous to outcomes |

---

## Field Conventions

- **Log outcomes:** Log-transform income, production, and GDP proxies; report as elasticities with clear denominators
- **Spatial autocorrelation:** Always test and correct; report Conley SEs at multiple cutoffs (50, 100, 200 km); justify chosen bandwidth
- **Heterogeneous effects:** Break out by indigenous/non-indigenous status, poverty quintile (NBI), urban/rural, proximity to extraction
- **Resource curse framing:** Address Dutch disease, institutional degradation channels, and local vs. national distribution of rents
- **Environmental externalities:** Quantify externalities where possible; discuss distributional incidence (who bears costs, who gets rents)
- **Conservation-development trade-off:** Referees expect explicit treatment of efficiency–equity tension; avoid assuming they align
- **ENEMDU comparability:** Note and handle 2003 and 2014 methodology breaks explicitly; use harmonized samples when pooling
- **Clustering:** Cluster at canton or province level for canton-level policy variation; justify clustering choice; report wild cluster bootstrap if few clusters
- **Staggered timing:** Never use vanilla TWFE for staggered adoption designs; use modern estimators; show event study plot
- **Placebo tests:** Geographic placebos (nearby unaffected areas) are highly valued in spatial designs; donut-hole RD for buffer zones
- **Indigenous rights:** Ecuador's 2008 constitution (Buen Vivir, Rights of Nature) creates legally distinct treatment for indigenous territories — always check overlap with RAISG data
- **Oil fiscal transfers:** Ecuador's oil revenue sharing formula changed in 2010 — document and address any discontinuities this creates

---

## Notation Conventions

| Symbol | Meaning | Anti-pattern |
|--------|---------|-------------|
| $Y_{it}$ | Outcome for unit $i$ (canton/parish/household) at time $t$ | Don't use $y$ without subscripts |
| $D_{it}$ | Treatment indicator (1 if area/unit treated at $t$) | Don't use $T$ — reserved for time horizon |
| $X_{it}$ | Vector of time-varying controls | Don't use $Z$ for controls — reserved for instruments |
| $Z_{it}$ | Instrument for endogenous variable | Don't use $W$ or $V$ for instruments |
| $\delta_t$ | Time fixed effects | Don't absorb silently into $\alpha$ without declaring |
| $\alpha_i$ | Unit fixed effects | Distinguish clearly from regression slope coefficients |
| $\tau$ | Treatment effect (causal estimand) | Don't use $\beta$ for the causal parameter — use $\tau$ or $\beta_1$ with explicit label |
| $\varepsilon_{it}$ | Idiosyncratic error | Use $\varepsilon$, not $e$ or $u$ |
| $\beta$ | Vector of slope coefficients | Bold for vectors; scalar for single coefficient |

---

## Seminal References

| Paper | Why It Matters |
|-------|---------------|
| Dell (2010, QJE) | Mita mining — long-run effects of colonial extraction; spatial RD benchmark for Latin America |
| Dube & Vargas (2013, REStud) | Commodity price shocks and armed conflict in Colombia — model for oil/mining IV strategy |
| Aragon & Rud (2013, AEJ:Applied) | Mining and local economic development — backward linkages framework; direct model for Ecuador context |
| Angrist & Kugler (2008, REStud) | Rural windfall effects and coca in Colombia — quasi-experimental resource boom in LAC |
| Asher & Novosad (2020, AER) | Roads and local economic development — infrastructure as IV; benchmark for transport cost instruments |
| Ferraro & Hanauer (2014, Science) | Protected areas and poverty — matched DiD for conservation programs; PES evaluation model |
| Bulte et al. (2005, World Dev.) | Resource curse at the sub-national level — motivation for canton-level analysis |
| Callaway & Sant'Anna (2021, JoE) | Staggered DiD estimator — required for any analysis with sequential rollout |
| Sun & Abraham (2021, JoE) | Interaction-weighted staggered DiD — alternative to Callaway-Sant'Anna; cite both |
| Goldsmith-Pinkham et al. (2020, AER) | Bartik/shift-share IV validity conditions — required if using shift-share identification |
| Conley (1999, JoE) | Spatial HAC standard errors — required for any spatial regression |
| Ponce & McClintock (2014) | Ecuador-specific oil extraction and local welfare — key regional benchmark |
| Larrea & Warnars (2009) | Ecuador oil extraction and poverty paradox — motivational background for resource curse in Ecuador |
| Burbano de Lara & van Dexter (2018) | Yasuní-ITT and Ecuador's extractive economy — institutional context |

---

## Field-Specific Referee Concerns

- **"Why not DiD with parallel trends?"** — For spatial designs, must show pre-trends test or visual event study with confidence bands
- **"Selection into treatment"** — Areas with extractive activity differ systematically (geology, remoteness, institutions); address via spatial controls, matching pre-treatment, or boundary design
- **"Spillovers / SUTVA"** — Resource booms affect neighboring cantons (migration, fiscal transfers, market linkages); test and discuss spillover contamination explicitly
- **"Staggered TWFE bias"** — If treatment is staggered, vanilla TWFE is insufficient; must use Callaway-Sant'Anna or Sun-Abraham; show event study
- **"Measurement of deforestation"** — Hansen GFC has noise and omits some disturbance types; validate against official MAATE data; discuss detection thresholds and pixel-level uncertainty
- **"Indigenous land rights"** — Referees will ask about differential effects on indigenous territories (constitutionally protected; consulta previa required); test heterogeneity explicitly
- **"Dutch disease vs fiscal channel"** — Distinguish mechanisms; discuss even without clean identification of the mechanism channel
- **"External validity"** — Ecuador ≠ all resource-rich developing countries; bound claims to comparable small open economies with commodity dependence
- **"2008 constitution endogeneity"** — Ecuador's Buen Vivir and Rights of Nature provisions may themselves respond to resource pressures; treat as potential confound in post-2008 periods
- **"Oil revenue formula changes"** — 2010 reform of Ecuador's oil revenue sharing creates a potential structural break; address explicitly
- **"Conley standard errors bandwidth choice"** — Referees expect sensitivity to bandwidth; report 50, 100, 200 km; discuss which is theoretically appropriate

---

## Quality Tolerance Thresholds

| Quantity | Tolerance | Rationale |
|----------|-----------|-----------|
| Point estimates | 1e-6 | Numerical precision |
| Standard errors | 1e-4 | Robust/clustered SE stability |
| Spatial Conley SEs | Check 50, 100, 200 km cutoffs | Robustness to bandwidth choice |
| Coverage rates (simulation) | ± 0.01 | Simulation with B ≥ 500 replications |
| Pre-trend F-statistic p-value | > 0.10 | Joint test of pre-period coefficients |
| First-stage F-statistic (IV) | > 10 (rule of thumb); report Olea-Pflueger robust statistic | Instrument strength |
