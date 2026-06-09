# FusionpInitializeCriticalSectionCommon(ulong,_RTL_CRITICAL_SECTION *,ulong)

- ea: `0x18004b140`
- end: `0x18004b1a6`
- name: `?FusionpInitializeCriticalSectionCommon@@YAHKPEAU_RTL_CRITICAL_SECTION@@K@Z`
- size: `102`
- prototype: `__int64 __fastcall(unsigned int, struct _RTL_CRITICAL_SECTION *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004ad80`

## callees

- `0x18004b140`
- `0x180067ac0`

## import_xrefs

- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18004b181`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18004b181`
- `ntdll!RtlUnhandledExceptionFilter` at `0x18006a22e`
- `ntdll!RtlUnhandledExceptionFilter` at `0x18006a22e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004b18f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004b18f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18004b155`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18004b155`

## string_xrefs

- `0x18004b171`: `SXS.DLL: FusionpInitializeCriticalSectionCommon - Unhandled exception caught: 0x%08lx`

## pseudocode

```c
__int64 __fastcall FusionpInitializeCriticalSectionCommon(__int64 a1, struct _RTL_CRITICAL_SECTION *a2)
{
  InitializeCriticalSection(&g_ActCtxCtbListCritSec);
  return 1;
}

```

## disassembly

```asm
0x18004b140  push    rbx
0x18004b142  sub     rsp, 40h
0x18004b146  mov     [rsp+48h+var_20], 0
0x18004b14e  lea     rcx, ?g_ActCtxCtbListCritSec@@3VCCriticalSectionNoConstructor@@A; lpCriticalSection
0x18004b155  call    cs:__imp_InitializeCriticalSection
0x18004b15c  nop     dword ptr [rax+rax+00h]
0x18004b161  mov     eax, 1
0x18004b166  mov     [rsp+48h+var_20], eax
0x18004b16a  jmp     short loc_18004B19F
0x18004b16c  mov     ebx, eax
0x18004b16e  mov     r8d, eax
0x18004b171  lea     rdx, aSxsDllFusionpi; "SXS.DLL: FusionpInitializeCriticalSecti"...
0x18004b178  xor     ecx, ecx; bool
0x18004b17a  call    ?FusionpReportCondition@@YAX_NPEBDZZ; FusionpReportCondition(bool,char const *,...)
0x18004b17f  mov     ecx, ebx; Status
0x18004b181  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18004b188  nop     dword ptr [rax+rax+00h]
0x18004b18d  mov     ecx, eax; dwErrCode
0x18004b18f  call    cs:__imp_SetLastError
0x18004b196  nop     dword ptr [rax+rax+00h]
0x18004b19b  mov     eax, [rsp+48h+var_20]
0x18004b19f  add     rsp, 40h
0x18004b1a3  pop     rbx
0x18004b1a4  retn
0x18006a206  push    rbp
0x18006a208  sub     rsp, 20h
0x18006a20c  mov     rbp, rdx
0x18006a20f  mov     [rbp+30h], rcx
0x18006a213  mov     rax, [rbp+30h]
0x18006a217  mov     rcx, [rax]
0x18006a21a  cmp     dword ptr [rcx], 0C0000017h
0x18006a220  jz      short loc_18006A259
0x18006a222  cmp     dword ptr [rcx], 0C000009Ah
0x18006a228  jz      short loc_18006A259
0x18006a22a  mov     rcx, [rbp+30h]; ExceptionInfo
0x18006a22e  call    cs:__imp_RtlUnhandledExceptionFilter
0x18006a235  nop     dword ptr [rax+rax+00h]
0x18006a23a  mov     [rbp+2Ch], eax
0x18006a23d  mov     eax, [rbp+2Ch]
0x18006a240  mov     [rbp+20h], eax
0x18006a243  mov     eax, [rbp+20h]
0x18006a246  test    eax, eax
0x18006a248  jnz     short loc_18006A251
0x18006a24a  mov     dword ptr [rbp+20h], 1
0x18006a251  mov     eax, [rbp+20h]
0x18006a254  mov     [rbp+24h], eax
0x18006a257  jmp     short loc_18006A260
0x18006a259  mov     dword ptr [rbp+24h], 1
0x18006a260  mov     eax, [rbp+24h]
0x18006a263  add     rsp, 20h
0x18006a267  pop     rbp
0x18006a268  retn
```
