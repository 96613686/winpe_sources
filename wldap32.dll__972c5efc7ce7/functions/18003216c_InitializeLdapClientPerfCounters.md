# InitializeLdapClientPerfCounters

- ea: `0x18003216c`
- end: `0x180032543`
- name: `InitializeLdapClientPerfCounters`
- size: `983`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180026b50`

## callees

- `0x1800037a8`
- `0x18002a8a0`
- `0x18002b284`
- `0x18003216c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032190`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032190`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003251a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004c9a2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003251a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004c9a2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032530`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c9b7`
- `api-ms-win-core-perfcounters-l1-1-0!PerfStartProviderEx` at `0x18003222a`
- `api-ms-win-core-perfcounters-l1-1-0!PerfStartProviderEx` at `0x18003222a`
- `api-ms-win-core-perfcounters-l1-1-0!PerfStopProvider` at `0x180032279`
- `api-ms-win-core-perfcounters-l1-1-0!PerfStopProvider` at `0x18003233c`
- `api-ms-win-core-perfcounters-l1-1-0!PerfStopProvider` at `0x180032279`
- `api-ms-win-core-perfcounters-l1-1-0!PerfStopProvider` at `0x18003233c`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x1800322e3`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x1800322e3`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterSetInfo` at `0x18003225b`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterSetInfo` at `0x18003225b`

## string_xrefs

- `0x1800321ea`: `%s  Failed to create Instance Name\n`
- `0x180032320`: `%s  Failed to create perf counter instance\n`

## pseudocode

```c
void InitializeLdapClientPerfCounters()
{
  ULONG started; // ebx
  HANDLE v1; // rcx
  _PROVIDER_CONTEXT ProviderContext; // [rsp+20h] [rbp-38h] BYREF
  PCWSTR Name; // [rsp+60h] [rbp+8h] BYREF

  if ( !pLdapPerfCounterInstance )
  {
    Name = 0;
    EnterCriticalSection(&LoadLibLock);
    if ( pLdapPerfCounterInstance )
    {
LABEL_27:
      LeaveCriticalSection(&LoadLibLock);
      LocalFree((HLOCAL)Name);
      return;
    }
    if ( !(unsigned int)CreateInstanceName((unsigned __int16 **)&Name) )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x4000000) != 0 )
        LDAPClientPrint(0x4000000, "%s  Failed to create Instance Name\n", "InitializeLdapClientPerfCounters:213");
      goto LABEL_27;
    }
    memset(&ProviderContext, 0, sizeof(ProviderContext));
    ProviderContext.ContextSize = 40;
    started = PerfStartProviderEx(
                &LdapPerformanceCountersProviderGuid,
                &ProviderContext,
                &LdapPerformanceCountersProvider);
    if ( started )
      goto LABEL_9;
    started = PerfSetCounterSetInfo(LdapPerformanceCountersProvider, &LdapPerformanceCountersSetInfo, 0x368u);
    v1 = LdapPerformanceCountersProvider;
    if ( started )
    {
      if ( LdapPerformanceCountersProvider )
      {
        PerfStopProvider(LdapPerformanceCountersProvider);
LABEL_9:
        v1 = 0;
        LdapPerformanceCountersProvider = 0;
      }
    }
    else
    {
      started = 0;
    }
    if ( started )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x4000000) != 0 )
        LDAPClientPrint(
          0x4000000,
          "%s  Failed to Initialize Counters with error:%d\n",
          "InitializeLdapClientPerfCounters:226",
          started);
    }
    else
    {
      pLdapPerfCounterInstance = PerfCreateInstance(v1, &LdapPerformanceCountersSetGuid, Name, 0);
      if ( pLdapPerfCounterInstance )
      {
        SetPerfCounterRef(1u, &gPerfCounters);
        SetPerfCounterRef(2u, &qword_180066088);
        SetPerfCounterRef(3u, &qword_180066090);
        SetPerfCounterRef(4u, &qword_180066098);
        SetPerfCounterRef(5u, &qword_1800660A0);
        SetPerfCounterRef(6u, &qword_1800660A8);
        SetPerfCounterRef(7u, &qword_1800660B0);
        SetPerfCounterRef(8u, &qword_1800660B8);
        SetPerfCounterRef(9u, &qword_1800660C0);
        SetPerfCounterRef(0xAu, &qword_1800660C8);
        SetPerfCounterRef(0xBu, &qword_1800660D0);
        SetPerfCounterRef(0xCu, &qword_1800660D8);
        SetPerfCounterRef(0xDu, &qword_1800660E0);
        SetPerfCounterRef(0xEu, &qword_1800660E8);
        SetPerfCounterRef(0xFu, &qword_1800660F0);
        SetPerfCounterRef(0x10u, &qword_1800660F8);
        SetPerfCounterRef(0x11u, &qword_180066100);
        SetPerfCounterRef(0x12u, &qword_180066108);
        SetPerfCounterRef(0x13u, &qword_180066110);
        SetPerfCounterRef(0x14u, &qword_180066118);
        SetPerfCounterRef(0x15u, &qword_180066120);
        SetPerfCounterRef(0x16u, &qword_180066128);
        SetPerfCounterRef(0x17u, &qword_180066130);
        SetPerfCounterRef(0x18u, &qword_180066138);
        SetPerfCounterRef(0x19u, &qword_180066140);
        SetPerfCounterRef(0x1Au, &qword_180066148);
      }
      else
      {
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x4000000) != 0 )
          LDAPClientPrint(
            0x4000000,
            "%s  Failed to create perf counter instance\n",
            "InitializeLdapClientPerfCounters:243");
        if ( LdapPerformanceCountersProvider )
        {
          PerfStopProvider(LdapPerformanceCountersProvider);
          LdapPerformanceCountersProvider = 0;
        }
      }
    }
    goto LABEL_27;
  }
}

```

## disassembly

```asm
0x18003216c  push    rbx
0x18003216e  sub     rsp, 50h
0x180032172  cmp     cs:?pLdapPerfCounterInstance@@3PEAU_PERF_COUNTERSET_INSTANCE@@EA, 0; _PERF_COUNTERSET_INSTANCE * pLdapPerfCounterInstance
0x18003217a  jnz     loc_18003253C
0x180032180  mov     [rsp+58h+Name], 0
0x180032189  lea     rcx, LoadLibLock; lpCriticalSection
0x180032190  call    cs:__imp_EnterCriticalSection
0x180032197  nop     dword ptr [rax+rax+00h]
0x18003219c  nop
0x18003219d  cmp     cs:?pLdapPerfCounterInstance@@3PEAU_PERF_COUNTERSET_INSTANCE@@EA, 0; _PERF_COUNTERSET_INSTANCE * pLdapPerfCounterInstance
0x1800321a5  jnz     loc_180032513
0x1800321ab  lea     rcx, [rsp+58h+Name]; unsigned __int16 **
0x1800321b0  call    ?CreateInstanceName@@YAHPEAPEAG@Z; CreateInstanceName(ushort * *)
0x1800321b5  test    eax, eax
0x1800321b7  jnz     short loc_1800321FB
0x1800321b9  cmp     cs:g_fTracingOn, eax
0x1800321bf  jz      loc_180032513
0x1800321c5  cmp     cs:g_fProviderEnabled, eax
0x1800321cb  jz      loc_180032513
0x1800321d1  mov     ecx, 4000000h
0x1800321d6  test    cs:g_ulTraceFlags, rcx
0x1800321dd  jz      loc_180032513
0x1800321e3  lea     r8, aInitializeldap; "InitializeLdapClientPerfCounters:213"
0x1800321ea  lea     rdx, aSFailedToCreat; "%s  Failed to create Instance Name\n"
0x1800321f1  call    LDAPClientPrint
0x1800321f6  jmp     loc_180032513
0x1800321fb  xorps   xmm0, xmm0
0x1800321fe  xor     eax, eax
0x180032200  movups  xmmword ptr [rsp+58h+ProviderContext.ContextSize], xmm0
0x180032205  movups  xmmword ptr [rsp+58h+ProviderContext.MemAllocRoutine], xmm0
0x18003220a  mov     [rsp+58h+ProviderContext.pMemContext], rax
0x18003220f  mov     [rsp+58h+ProviderContext.ContextSize], 28h ; '('
0x180032217  lea     r8, LdapPerformanceCountersProvider; Provider
0x18003221e  lea     rdx, [rsp+58h+ProviderContext]; ProviderContext
0x180032223  lea     rcx, LdapPerformanceCountersProviderGuid; ProviderGuid
0x18003222a  call    cs:__imp_PerfStartProviderEx
0x180032231  nop     dword ptr [rax+rax+00h]
0x180032236  mov     ebx, eax
0x180032238  test    eax, eax
0x18003223a  jz      short loc_180032247
0x18003223c  xor     ecx, ecx
0x18003223e  mov     cs:LdapPerformanceCountersProvider, rcx
0x180032245  jmp     short loc_180032289
0x180032247  mov     r8d, 368h; TemplateSize
0x18003224d  lea     rdx, LdapPerformanceCountersSetInfo; Template
0x180032254  mov     rcx, cs:LdapPerformanceCountersProvider; ProviderHandle
0x18003225b  call    cs:__imp_PerfSetCounterSetInfo
0x180032262  nop     dword ptr [rax+rax+00h]
0x180032267  mov     ebx, eax
0x180032269  mov     rcx, cs:LdapPerformanceCountersProvider; ProviderHandle
0x180032270  test    eax, eax
0x180032272  jz      short loc_180032287
0x180032274  test    rcx, rcx
0x180032277  jz      short loc_180032289
0x180032279  call    cs:__imp_PerfStopProvider
0x180032280  nop     dword ptr [rax+rax+00h]
0x180032285  jmp     short loc_18003223C
0x180032287  xor     ebx, ebx
0x180032289  test    ebx, ebx
0x18003228b  jz      short loc_1800322D4
0x18003228d  cmp     cs:g_fTracingOn, 0
0x180032294  jz      loc_180032513
0x18003229a  cmp     cs:g_fProviderEnabled, 0
0x1800322a1  jz      loc_180032513
0x1800322a7  mov     ecx, 4000000h
0x1800322ac  test    cs:g_ulTraceFlags, rcx
0x1800322b3  jz      loc_180032513
0x1800322b9  mov     r9d, ebx
0x1800322bc  lea     r8, aInitializeldap_0; "InitializeLdapClientPerfCounters:226"
0x1800322c3  lea     rdx, aSFailedToIniti; "%s  Failed to Initialize Counters with "...
0x1800322ca  call    LDAPClientPrint
0x1800322cf  jmp     loc_180032513
0x1800322d4  xor     r9d, r9d; Id
0x1800322d7  mov     r8, [rsp+58h+Name]; Name
0x1800322dc  lea     rdx, LdapPerformanceCountersSetGuid; CounterSetGuid
0x1800322e3  call    cs:__imp_PerfCreateInstance
0x1800322ea  nop     dword ptr [rax+rax+00h]
0x1800322ef  mov     cs:?pLdapPerfCounterInstance@@3PEAU_PERF_COUNTERSET_INSTANCE@@EA, rax; _PERF_COUNTERSET_INSTANCE * pLdapPerfCounterInstance
0x1800322f6  test    rax, rax
0x1800322f9  jnz     short loc_180032358
0x1800322fb  cmp     cs:g_fTracingOn, eax
0x180032301  jz      short loc_18003232C
0x180032303  cmp     cs:g_fProviderEnabled, eax
0x180032309  jz      short loc_18003232C
0x18003230b  mov     ecx, 4000000h
0x180032310  test    cs:g_ulTraceFlags, rcx
0x180032317  jz      short loc_18003232C
0x180032319  lea     r8, aInitializeldap_1; "InitializeLdapClientPerfCounters:243"
0x180032320  lea     rdx, aSFailedToCreat_0; "%s  Failed to create perf counter insta"...
0x180032327  call    LDAPClientPrint
0x18003232c  mov     rcx, cs:LdapPerformanceCountersProvider; ProviderHandle
0x180032333  test    rcx, rcx
0x180032336  jz      loc_180032513
0x18003233c  call    cs:__imp_PerfStopProvider
0x180032343  nop     dword ptr [rax+rax+00h]
0x180032348  mov     cs:LdapPerformanceCountersProvider, 0
0x180032353  jmp     loc_180032513
0x180032358  lea     rdx, gPerfCounters; Address
0x18003235f  mov     ecx, 1; CounterId
0x180032364  call    ?SetPerfCounterRef@@YAXKPECX@Z; SetPerfCounterRef(ulong,void volatile *)
0x180032369  lea     rdx, qword_180066088; Address
0x180032370  mov     ecx, 2; CounterId
0x180032375  call    ?SetPerfCounterRef@@YAXKPECX@Z; SetPerfCounterRef(ulong,void volatile *)
0x18003237a  lea     rdx, qword_180066090; Address
0x180032381  mov     ecx, 3; CounterId
0x180032386  call    ?SetPerfCounterRef@@YAXKPECX@Z; SetPerfCounterRef(ulong,void volatile *)
0x18003238b  lea     rdx, qword_180066098; Address
0x180032392  mov     ecx, 4; CounterId
0x180032397  call    ?SetPerfCounterRef@@YAXKPECX@Z; SetPerfCounterRef(ulong,void volatile *)
0x18003239c  lea     rdx, qword_1800660A0; Address
0x1800323a3  mov     ecx, 5; CounterId
0x1800323a8  call    ?SetPerfCounterRef@@YAXKPECX@Z; SetPerfCounterRef(ulong,void volatile *)
0x1800323ad  lea     rdx, qword_1800660A8; Address
0x1800323b4  mov     ecx, 6; CounterId
0x1800323b9  call    ?SetPerfCounterRef@@YAXKPECX@Z; SetPerfCounterRef(ulong,void volatile *)
0x1800323be  lea     rdx, qword_1800660B0; Address
0x1800323c5  mov     ecx, 7; CounterId
0x1800323ca  call    ?SetPerfCounterRef@@YAXKPECX@Z; SetPerfCounterRef(ulong,void volatile *)
0x1800323cf  lea     rdx, qword_1800660B8; Address
0x1800323d6  mov     ecx, 8; CounterId
0x1800323db  call    ?SetPerfCounterRef@@YAXKPECX@Z; SetPerfCounterRef(ulong,void volatile *)
0x1800323e0  lea     rdx, qword_1800660C0; Address
0x1800323e7  mov     ecx, 9; CounterId
0x1800323ec  call    ?SetPerfCounterRef@@YAXKPECX@Z; SetPerfCounterRef(ulong,void volatile *)
0x1800323f1  lea     rdx, qword_1800660C8; Address
0x1800323f8  mov     ecx, 0Ah; CounterId
0x1800323fd  call    ?SetPerfCounterRef@@YAXKPECX@Z; SetPerfCounterRef(ulong,void volatile *)
0x180032402  lea     rdx, qword_1800660D0; Address
0x180032409  mov     ecx, 0Bh; CounterId
0x18003240e  call    ?SetPerfCounterRef@@YAXKPECX@Z; SetPerfCounterRef(ulong,void volatile *)
0x180032413  lea     rdx, qword_1800660D8; Address
0x18003241a  mov     ecx, 0Ch; CounterId
0x18003241f  call    ?SetPerfCounterRef@@YAXKPECX@Z; SetPerfCounterRef(ulong,void volatile *)
0x180032424  lea     rdx, qword_1800660E0; Address
0x18003242b  mov     ecx, 0Dh; CounterId
0x180032430  call    ?SetPerfCounterRef@@YAXKPECX@Z; SetPerfCounterRef(ulong,void volatile *)
0x180032435  lea     rdx, qword_1800660E8; Address
0x18003243c  mov     ecx, 0Eh; CounterId
0x180032441  call    ?SetPerfCounterRef@@YAXKPECX@Z; SetPerfCounterRef(ulong,void volatile *)
0x180032446  lea     rdx, qword_1800660F0; Address
0x18003244d  mov     ecx, 0Fh; CounterId
0x180032452  call    ?SetPerfCounterRef@@YAXKPECX@Z; SetPerfCounterRef(ulong,void volatile *)
0x180032457  lea     rdx, qword_1800660F8; Address
0x18003245e  mov     ecx, 10h; CounterId
0x180032463  call    ?SetPerfCounterRef@@YAXKPECX@Z; SetPerfCounterRef(ulong,void volatile *)
0x180032468  lea     rdx, qword_180066100; Address
0x18003246f  mov     ecx, 11h; CounterId
0x180032474  call    ?SetPerfCounterRef@@YAXKPECX@Z; SetPerfCounterRef(ulong,void volatile *)
0x180032479  lea     rdx, qword_180066108; Address
0x180032480  mov     ecx, 12h; CounterId
0x180032485  call    ?SetPerfCounterRef@@YAXKPECX@Z; SetPerfCounterRef(ulong,void volatile *)
0x18003248a  lea     rdx, qword_180066110; Address
0x180032491  mov     ecx, 13h; CounterId
0x180032496  call    ?SetPerfCounterRef@@YAXKPECX@Z; SetPerfCounterRef(ulong,void volatile *)
0x18003249b  lea     rdx, qword_180066118; Address
0x1800324a2  mov     ecx, 14h; CounterId
0x1800324a7  call    ?SetPerfCounterRef@@YAXKPECX@Z; SetPerfCounterRef(ulong,void volatile *)
0x1800324ac  lea     rdx, qword_180066120; Address
0x1800324b3  mov     ecx, 15h; CounterId
0x1800324b8  call    ?SetPerfCounterRef@@YAXKPECX@Z; SetPerfCounterRef(ulong,void volatile *)
0x1800324bd  lea     rdx, qword_180066128; Address
0x1800324c4  mov     ecx, 16h; CounterId
0x1800324c9  call    ?SetPerfCounterRef@@YAXKPECX@Z; SetPerfCounterRef(ulong,void volatile *)
0x1800324ce  lea     rdx, qword_180066130; Address
0x1800324d5  mov     ecx, 17h; CounterId
0x1800324da  call    ?SetPerfCounterRef@@YAXKPECX@Z; SetPerfCounterRef(ulong,void volatile *)
0x1800324df  lea     rdx, qword_180066138; Address
0x1800324e6  mov     ecx, 18h; CounterId
0x1800324eb  call    ?SetPerfCounterRef@@YAXKPECX@Z; SetPerfCounterRef(ulong,void volatile *)
0x1800324f0  lea     rdx, qword_180066140; Address
0x1800324f7  mov     ecx, 19h; CounterId
0x1800324fc  call    ?SetPerfCounterRef@@YAXKPECX@Z; SetPerfCounterRef(ulong,void volatile *)
0x180032501  lea     rdx, qword_180066148; Address
0x180032508  mov     ecx, 1Ah; CounterId
0x18003250d  call    ?SetPerfCounterRef@@YAXKPECX@Z; SetPerfCounterRef(ulong,void volatile *)
0x180032512  nop
0x180032513  lea     rcx, LoadLibLock; lpCriticalSection
0x18003251a  call    cs:__imp_LeaveCriticalSection
0x180032521  nop     dword ptr [rax+rax+00h]
0x180032526  mov     rcx, [rsp+58h+Name]
0x18003252b  add     rsp, 50h
0x18003252f  pop     rbx
0x180032530  jmp     cs:__imp_LocalFree
0x18003253c  add     rsp, 50h
0x180032540  pop     rbx
0x180032541  retn
0x18004c992  push    rbp
0x18004c994  sub     rsp, 20h
0x18004c998  mov     rbp, rdx
0x18004c99b  lea     rcx, LoadLibLock; lpCriticalSection
0x18004c9a2  call    cs:__imp_LeaveCriticalSection
0x18004c9a9  nop     dword ptr [rax+rax+00h]
0x18004c9ae  mov     rcx, [rbp+60h]
0x18004c9b2  add     rsp, 20h
0x18004c9b6  pop     rbp
0x18004c9b7  jmp     cs:__imp_LocalFree
```
