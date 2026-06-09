# Microsoft::Diagnostics::SystemStateManager::WaitUntilGameCoreNetworkReady(void *)

- ea: `0x1800ff8f0`
- end: `0x1800ffac2`
- name: `?WaitUntilGameCoreNetworkReady@SystemStateManager@Diagnostics@Microsoft@@QEAA_NPEAX@Z`
- size: `466`
- prototype: `bool __fastcall(Microsoft::Diagnostics::SystemStateManager *__hidden this, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1801a3ddc`

## callees

- `0x18005b050`
- `0x1800ff8f0`
- `0x1800ffac8`
- `0x1800ffb00`
- `0x18012de40`
- `0x180175cec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ffa55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ffa55`
- `ntdll!NtQueryLicenseValue` at `0x1800ff94b`
- `ntdll!NtQueryLicenseValue` at `0x1800ff94b`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800ffa44`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800ffa44`
- `IPHLPAPI!NotifyNetworkConnectivityHintChange` at `0x1800ffa03`
- `IPHLPAPI!NotifyNetworkConnectivityHintChange` at `0x1800ffa03`
- `IPHLPAPI!GetNetworkConnectivityHint` at `0x1800ff984`
- `IPHLPAPI!GetNetworkConnectivityHint` at `0x1800ff984`

## pseudocode

```c

```
