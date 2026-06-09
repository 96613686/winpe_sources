# UninitializeLdapClientPerfCounters

- ea: `0x18003254c`
- end: `0x1800325dd`
- name: `UninitializeLdapClientPerfCounters`
- size: `145`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180025cc8`

## callees

- `0x1800037a8`
- `0x18003254c`

## import_xrefs

- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x180032563`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x180032563`
- `api-ms-win-core-perfcounters-l1-1-0!PerfStopProvider` at `0x1800325c0`
- `api-ms-win-core-perfcounters-l1-1-0!PerfStopProvider` at `0x1800325c0`

## string_xrefs

- `0x18003259d`: `%s  Failed to delete Perf Instance with error:%d\n`

## pseudocode

```c
void UninitializeLdapClientPerfCounters()
{
  ULONG v0; // eax

  if ( pLdapPerfCounterInstance )
  {
    v0 = PerfDeleteInstance(LdapPerformanceCountersProvider, pLdapPerfCounterInstance);
    if ( v0 && g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x4000000) != 0 )
      LDAPClientPrint(
        0x4000000,
        "%s  Failed to delete Perf Instance with error:%d\n",
        "UninitializeLdapClientPerfCounters:312",
        v0);
    pLdapPerfCounterInstance = 0;
    if ( LdapPerformanceCountersProvider )
    {
      PerfStopProvider(LdapPerformanceCountersProvider);
      LdapPerformanceCountersProvider = 0;
    }
  }
}

```

## disassembly

```asm
0x18003254c  sub     rsp, 28h
0x180032550  mov     rdx, cs:?pLdapPerfCounterInstance@@3PEAU_PERF_COUNTERSET_INSTANCE@@EA; InstanceBlock
0x180032557  test    rdx, rdx
0x18003255a  jz      short loc_1800325D7
0x18003255c  mov     rcx, cs:LdapPerformanceCountersProvider; Provider
0x180032563  call    cs:__imp_PerfDeleteInstance
0x18003256a  nop     dword ptr [rax+rax+00h]
0x18003256f  test    eax, eax
0x180032571  jz      short loc_1800325A9
0x180032573  cmp     cs:g_fTracingOn, 0
0x18003257a  jz      short loc_1800325A9
0x18003257c  cmp     cs:g_fProviderEnabled, 0
0x180032583  jz      short loc_1800325A9
0x180032585  mov     ecx, 4000000h
0x18003258a  test    cs:g_ulTraceFlags, rcx
0x180032591  jz      short loc_1800325A9
0x180032593  mov     r9d, eax
0x180032596  lea     r8, aUninitializeld; "UninitializeLdapClientPerfCounters:312"
0x18003259d  lea     rdx, aSFailedToDelet; "%s  Failed to delete Perf Instance with"...
0x1800325a4  call    LDAPClientPrint
0x1800325a9  mov     rcx, cs:LdapPerformanceCountersProvider; ProviderHandle
0x1800325b0  mov     cs:?pLdapPerfCounterInstance@@3PEAU_PERF_COUNTERSET_INSTANCE@@EA, 0; _PERF_COUNTERSET_INSTANCE * pLdapPerfCounterInstance
0x1800325bb  test    rcx, rcx
0x1800325be  jz      short loc_1800325D7
0x1800325c0  call    cs:__imp_PerfStopProvider
0x1800325c7  nop     dword ptr [rax+rax+00h]
0x1800325cc  mov     cs:LdapPerformanceCountersProvider, 0
0x1800325d7  add     rsp, 28h
0x1800325db  retn
```
