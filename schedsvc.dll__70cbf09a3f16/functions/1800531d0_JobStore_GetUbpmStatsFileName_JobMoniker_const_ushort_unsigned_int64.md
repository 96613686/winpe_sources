# JobStore::GetUbpmStatsFileName(JobMoniker const &,ushort *,unsigned __int64)

- ea: `0x1800531d0`
- end: `0x180053315`
- name: `?GetUbpmStatsFileName@JobStore@@QEBAJAEBVJobMoniker@@PEAG_K@Z`
- size: `325`
- prototype: `__int64 __fastcall(JobStore *this, UUID *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18006bd70`
- `0x18006e700`

## callees

- `0x18002132c`
- `0x18002ae80`
- `0x180052584`
- `0x1800531d0`
- `0x1800538cc`
- `0x180056794`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180053243`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180053243`
- `RPCRT4!UuidToStringW` at `0x180053211`
- `RPCRT4!UuidToStringW` at `0x180053211`
- `RPCRT4!RpcStringFreeW` at `0x1800531e4`

## string_xrefs

- `0x180053236`: `%SystemRoot%\System32\logfiles\UbpmMigratedStats\`

## pseudocode

```c

```
