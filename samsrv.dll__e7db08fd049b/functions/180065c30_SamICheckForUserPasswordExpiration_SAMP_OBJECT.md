# SamICheckForUserPasswordExpiration(_SAMP_OBJECT *)

- ea: `0x180065c30`
- end: `0x180065eca`
- name: `?SamICheckForUserPasswordExpiration@@YAJPEAU_SAMP_OBJECT@@@Z`
- size: `666`
- prototype: `__int64 __fastcall(struct _SAMP_OBJECT *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180068820`

## callees

- `0x1800028e0`
- `0x18000e7f0`
- `0x180021ad0`
- `0x180027e24`
- `0x18002cd80`
- `0x18002d720`
- `0x180037284`
- `0x1800372ac`
- `0x180065c30`

## import_xrefs

- `ntdll!NtQuerySystemTime` at `0x180065e37`
- `ntdll!NtQuerySystemTime` at `0x180065e37`
- `LSASRV!LsarQueryDomainInformationPolicy` at `0x180065d41`
- `LSASRV!LsarQueryDomainInformationPolicy` at `0x180065d41`
- `LSASRV!LsarClose` at `0x180065da5`
- `LSASRV!LsarClose` at `0x180065da5`
- `LSASRV!LsaIOpenPolicyTrusted` at `0x180065d27`
- `LSASRV!LsaIOpenPolicyTrusted` at `0x180065d27`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180065d8b`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180065d8b`

## pseudocode

```c

```
