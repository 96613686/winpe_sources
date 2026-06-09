# JobStore::GetUbpmStatsFileName(JobMoniker const &,ushort *,unsigned __int64)

- ea: `0x1800559ec`
- end: `0x180055b3e`
- name: `?GetUbpmStatsFileName@JobStore@@QEBAJAEBVJobMoniker@@PEAG_K@Z`
- size: `338`
- prototype: `int(JobStore *__hidden this, const struct JobMoniker *, unsigned __int16 *, unsigned __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18006f3b8`
- `0x180071e38`

## callees

- `0x180001e10`
- `0x18002db74`
- `0x180054c80`
- `0x1800559ec`
- `0x180056144`
- `0x180059140`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180055a65`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180055a65`
- `RPCRT4!UuidToStringW` at `0x180055a2d`
- `RPCRT4!UuidToStringW` at `0x180055a2d`
- `RPCRT4!RpcStringFreeW` at `0x180055a00`

## string_xrefs

- `0x180055a58`: `%SystemRoot%\System32\logfiles\UbpmMigratedStats\`

## pseudocode

```c

```
