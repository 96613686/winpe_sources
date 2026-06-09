# ProcessorManager::InitProperties(IVirtualMachine *,INumaManager *,bool,Config::VmWorkerProcess::ProcessorSettings const &,Config::VmWorkerProcess::CompatibilitySettings const &)

- ea: `0x14005ccd4`
- end: `0x14005d981`
- name: `?InitProperties@ProcessorManager@@AEAAXPEAUIVirtualMachine@@PEAUINumaManager@@_NAEBUProcessorSettings@VmWorkerProcess@Config@@AEBUCompatibilitySettings@56@@Z`
- size: `3245`
- prototype: `void __fastcall(ProcessorManager *__hidden this, struct IVirtualMachine *, struct INumaManager *, bool, const struct Config::VmWorkerProcess::ProcessorSettings *, const struct Config::VmWorkerProcess::CompatibilitySettings *)`
- caller_count: `1`
- callee_count: `50`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140271494`

## callees

- `0x14001ec28`
- `0x140021dc0`
- `0x140022548`
- `0x140022658`
- `0x1400305c0`
- `0x140031438`
- `0x1400364a0`
- `0x14004517c`
- `0x14004e798`
- `0x14004f4d0`
- `0x140053bbc`
- `0x1400545bc`
- `0x140055af4`
- `0x140055ca8`
- `0x14005b468`
- `0x14005c320`
- `0x14005c4b8`
- `0x14005ccd4`
- `0x14005def8`
- `0x14005df20`
- `0x14005dfdc`
- `0x14005e07c`
- `0x14005e2c8`
- `0x14005e390`
- `0x1400663bc`
- `0x140069058`
- `0x1400690dc`
- `0x14006fe88`
- `0x140073f70`
- `0x140078628`
- `0x140083990`
- `0x14008ff18`
- `0x1400c1de4`
- `0x14011ea40`
- `0x14011edec`
- `0x14011f6fc`
- `0x140138908`
- `0x14014e8e4`
- `0x140161ed4`
- `0x1401877f4`
- `0x1401c9f78`
- `0x14026fa84`
- `0x1402703c4`
- `0x14027043c`
- `0x140272130`
- `0x140272464`
- `0x140272d44`
- `0x1402731b4`
- `0x1402a28f0`
- `0x1402cb010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x14005ce12`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x14005ce12`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14005d6f4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14005d6f4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14005d741`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14005d741`
- `vid!VidGetPartitionPropertyEx` at `0x14005d8dc`
- `vid!VidGetPartitionPropertyEx` at `0x14005d8dc`
- `vid!VidGetPartitionProperty` at `0x14005d0a9`
- `vid!VidGetPartitionProperty` at `0x14005d4e2`
- `vid!VidGetPartitionProperty` at `0x14005d0a9`
- `vid!VidGetPartitionProperty` at `0x14005d4e2`

## string_xrefs

- `0x14005cfcc`: `Failed to initialize settings from config repository.\n`

## pseudocode

```c

```
