# ComputeService::Net::GetAdapterInterfaceGuid(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1400b20d4`
- end: `0x1400b22c6`
- name: `?GetAdapterInterfaceGuid@Net@ComputeService@@YA?AU_GUID@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `498`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1400ad678`

## callees

- `0x140005360`
- `0x14000ea60`
- `0x1400341ac`
- `0x1400b20d4`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400b2245`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400b2245`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x1400b21f8`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x1400b21f8`
- `NetSetupApi!NetSetupGetObjects` at `0x1400b21cc`
- `NetSetupApi!NetSetupGetObjects` at `0x1400b21cc`
- `NetSetupApi!NetSetupInitialize` at `0x1400b2178`
- `NetSetupApi!NetSetupInitialize` at `0x1400b2178`
- `NetSetupApi!NetSetupClose` at `0x1400b222e`
- `NetSetupApi!NetSetupClose` at `0x1400b222e`
- `NetSetupApi!NetSetupSynchronizeDevices` at `0x1400b2160`
- `NetSetupApi!NetSetupSynchronizeDevices` at `0x1400b2160`
- `NetSetupApi!NetSetupFreeObjects` at `0x1400b221f`
- `NetSetupApi!NetSetupFreeObjects` at `0x1400b221f`

## string_xrefs

- `0x1400b226e`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\vmhostednetworkutilities.cpp`
- `0x1400b2283`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\vmhostednetworkutilities.cpp`
- `0x1400b2299`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\vmhostednetworkutilities.cpp`
- `0x1400b22b4`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\vmhostednetworkutilities.cpp`

## pseudocode

```c

```
