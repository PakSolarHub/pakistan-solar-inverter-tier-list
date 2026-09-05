# Inverter database schema

The project treats the specification database as the source of truth and the tier list as a derived view. Missing information must never be guessed.

## 1. Identity and classification

- `id`
- `brand`
- `model`
- `series`
- `variant`
- `market_name`
- `device_type`: hybrid / on-grid / off-grid / battery inverter / other
- `phase`: single / split / three / other
- `rated_power_kw`
- `rated_apparent_power_kva`
- `status`: research / verified / discontinued / archived
- `tier`: S / A / B / C / D / UNRATED
- `score`
- `confidence`
- `first_seen_date`
- `last_verified_date`

## 2. AC output

- rated continuous output power
- maximum apparent power
- maximum continuous output current
- peak/surge output power
- peak/surge duration
- overload capability and duration
- AC output voltage
- AC voltage range
- output frequency
- frequency range
- phase configuration
- pure sine wave
- total harmonic distortion (THD)
- power factor range
- efficiency
- peak efficiency
- Euro efficiency
- transfer/switching time
- UPS mode
- EPS/backup output
- backup output limitations
- parallel operation
- maximum parallel units
- phase balancing / phase assignment

## 3. PV input / MPPT

- maximum PV input power
- maximum PV input voltage
- PV startup voltage
- minimum PV operating voltage
- MPPT voltage range
- number of MPPT trackers
- number of PV inputs
- strings per MPPT
- maximum PV input current per MPPT
- maximum short-circuit current per MPPT
- maximum total PV current
- MPPT tracking efficiency
- PV oversizing limit
- independent MPPT operation
- string monitoring
- reverse-polarity protection
- PV insulation detection
- low-light/startup behaviour
- cold-weather voltage considerations
- supported PV module/string constraints

## 4. Battery

- nominal battery voltage
- battery voltage operating range
- battery chemistry support
- lithium support
- lead-acid support
- maximum charge current
- maximum discharge current
- maximum charge power
- maximum discharge power
- programmable charge voltage
- programmable discharge voltage
- low-voltage cutoff
- battery temperature sensor
- battery current measurement
- battery-less operation
- battery priority modes
- solar-first / grid-first / battery-first modes
- time-of-use scheduling
- force charge
- force discharge
- battery reserve SOC
- minimum SOC
- maximum SOC
- generator charging
- AC/grid charging

## 5. Battery BMS and communications

- CAN
- RS485
- RS232
- USB
- supported BMS protocols
- documented battery brands/models
- automatic battery detection
- user-defined battery profile
- BMS data displayed
- BMS-controlled charge/discharge limits
- battery communication cable requirements

## 6. Grid / AC input / generator

- grid nominal voltage
- grid voltage operating range
- grid frequency
- grid frequency operating range
- maximum grid input current
- maximum AC input power
- grid charging current
- AC bypass
- bypass capacity
- generator compatibility
- generator input voltage limits
- generator frequency limits
- generator maximum current/power
- generator auto-start
- dry-contact generator control
- grid/generator switching behaviour
- AC coupling
- microinverter compatibility
- anti-islanding
- grid protection
- islanding detection
- neutral requirements
- earth/ground requirements
- zero-export
- export limitation
- CT clamp support
- smart meter support
- supported meter models
- feed-in/export support

## 7. Protection and electrical safety

- over-voltage protection
- under-voltage protection
- over-current protection
- short-circuit protection
- over-temperature protection
- surge protection
- lightning protection
- DC isolator
- AC isolator requirement
- PV fuse requirements
- battery fuse/breaker requirements
- residual-current requirements
- insulation monitoring
- anti-islanding certification
- EMC compliance
- electrical safety certifications
- applicable standards

## 8. Physical and environmental

- dimensions: width / height / depth
- weight
- mounting method
- installation orientation
- cooling method
- fan count
- fan type
- fan replaceability
- heatsink design if documented
- noise level
- ingress protection (IP) rating
- indoor/outdoor rating
- operating temperature
- storage temperature
- temperature derating threshold
- derating curve
- maximum operating humidity
- altitude rating
- corrosion resistance
- PCB conformal coating
- enclosure material
- cable entry method
- terminal types
- recommended clearances
- installation environment

## 9. Display, controls and firmware

- display type
- display size
- physical buttons
- touch interface
- LEDs/status indicators
- local configuration
- installer settings
- user settings
- firmware version
- firmware update method
- remote firmware update
- local firmware update
- firmware rollback capability
- event/fault log
- error codes
- event history retention
- data logging interval

## 10. Communications and monitoring

- Wi-Fi
- Ethernet
- 4G/cellular
- Bluetooth
- RS485
- CAN
- USB
- Modbus RTU
- Modbus TCP
- dry contacts
- local web interface
- cloud platform
- mobile app name
- Android support
- iOS support
- app rating/availability notes
- remote monitoring
- remote configuration
- remote firmware updates
- historical generation data
- historical battery data
- historical load data
- historical grid data
- alerts
- push notifications
- email notifications
- installer portal
- API availability
- API documentation
- cloud dependency
- local-only monitoring option
- data export

## 11. Warranty and support

- stated warranty period
- warranty start point
- warranty registration requirement
- extended warranty
- warranty exclusions
- warranty territory
- authorized warranty provider
- official importer
- authorized distributor
- authorized dealer network
- service centers
- repair vs replacement policy
- advance replacement
- typical turnaround time
- spare-parts availability
- PCB availability
- fan availability
- display availability
- communications dongle availability
- local repairability
- installer familiarity
- support contact channels

## 12. Pakistan market

- current street price
- MSRP/list price if published
- price range
- price date
- price source
- price history
- availability status
- major cities stocked
- official Pakistani presence
- importer/distributor
- dealer list
- installation cost estimate
- commissioning/setup cost
- monitoring dongle included
- CT/meter included
- cables/accessories included
- battery compatibility in Pakistan
- panel compatibility commonly reported in Pakistan
- local installer adoption

## 13. OEM / platform provenance

- brand
- OEM/manufacturer
- OEM model
- OEM series/platform
- hardware platform
- firmware/platform family
- known rebrands
- known equivalent models
- OEM evidence
- rebrand evidence
- evidence confidence
- source URLs
- verification date

OEM claims are classified as verified, probable, possible, conflicting, or unknown. A reseller's branding claim is not enough to mark an OEM relationship as verified.

## 14. Reliability and field evidence

- owner report count
- independently observed unit count
- reported failure count
- confirmed failure count
- failure rate where sample size permits
- failure types
- thermal failures
- fan failures
- MPPT failures
- MOSFET/power-stage failures
- relay/contact failures
- display failures
- Wi-Fi/app failures
- BMS communication failures
- grid synchronization failures
- nuisance trips
- firmware problems
- battery charging problems
- warranty claims
- reported resolution rate
- recurring issue severity
- sample size
- observation period
- evidence confidence

Reliability statistics must show sample size and evidence quality. Anecdotal reports must not be presented as a measured failure rate.

## 15. Evidence model

Every material claim should be traceable to evidence. Each evidence item should record:

- `evidence_id`
- claim supported
- source type: manufacturer / datasheet / manual / certification / distributor / installer / owner / independent test / community
- URL or document reference
- publisher/author
- publication date if known
- access/verification date
- quoted specification or observation
- evidence strength
- conflicting-source flag
- notes

Recommended confidence states: `verified`, `strong`, `moderate`, `weak`, `community_reported`, `conflicting`, `not_specified`, `unknown`.

## 16. Comparison-ready normalized values

Where useful, store both the manufacturer's original value and a normalized value/unit. Examples:

- watts / kilowatts
- volts
- amps
- hertz
- percent
- milliseconds
- degrees Celsius
- kilograms
- millimeters
- decibels
- IP rating
- PKR
- SOC percent

Do not silently convert ambiguous manufacturer specifications. Preserve the original wording in evidence and store the normalized interpretation separately.

## 17. Data quality rules

1. Never invent a specification.
2. `not_specified` means the manufacturer does not state it in the reviewed source; `unknown` means research has not established it.
3. Preserve conflicting specifications rather than selecting the most convenient value.
4. Record the source and verification date for important claims.
5. Separate manufacturer claims from independent measurements and owner reports.
6. Do not turn one owner's experience into a general reliability statistic.
7. Keep price records time-stamped because Pakistan market prices change frequently.
8. Tier and score are derived fields; the underlying evidence remains authoritative.
9. A model stays `UNRATED` when evidence is insufficient for a defensible ranking.
10. Schema additions should be backwards-compatible where practical.
