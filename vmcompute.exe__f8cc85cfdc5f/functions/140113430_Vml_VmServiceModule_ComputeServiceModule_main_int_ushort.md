# Vml::VmServiceModule<ComputeServiceModule>::main(int,ushort * *)

- ea: `0x140113430`
- end: `0x140113654`
- name: `?main@?$VmServiceModule@VComputeServiceModule@@@Vml@@QEAAHHPEAPEAG@Z`
- size: `548`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x14013ec14`

## callees

- `0x1400024d0`
- `0x140080180`
- `0x140087500`
- `0x140113430`
- `0x14011365c`
- `0x1401332f0`
- `0x140139790`
- `0x140139ce8`
- `0x14013b328`
- `0x14013c6d0`
- `0x14013cc1c`
- `0x14013d1b4`
- `0x1402c4010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140113528`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140113554`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140113528`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140113554`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1401134c5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1401134c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140113472`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140113472`
- `api-ms-win-core-heap-l1-1-0!HeapSetInformation` at `0x14011348e`
- `api-ms-win-core-heap-l1-1-0!HeapSetInformation` at `0x1401134b2`
- `api-ms-win-core-heap-l1-1-0!HeapSetInformation` at `0x14011348e`
- `api-ms-win-core-heap-l1-1-0!HeapSetInformation` at `0x1401134b2`
- `api-ms-win-service-core-l1-1-0!StartServiceCtrlDispatcherW` at `0x14011359f`
- `api-ms-win-service-core-l1-1-0!StartServiceCtrlDispatcherW` at `0x14011359f`

## string_xrefs

- `0x1401134e0`: `onecore\vm\common\vml\VmModules.h`
- `0x1401135b4`: `onecore\vm\common\vml\VmModules.h`

## pseudocode

```c
__int64 __fastcall Vml::VmServiceModule<ComputeServiceModule>::main(__int64 a1, int a2, __int64 a3)
{
  HANDLE ProcessHeap; // rbx
  __int64 v6; // rcx
  __int64 v7; // rcx
  const char *v8; // r9
  int i; // ebx
  _WORD *v10; // rcx
  _WORD *v11; // r15
  const char *v12; // r9
  __int64 v13; // rax
  int HeapInformation; // [rsp+30h] [rbp-48h] BYREF
  SERVICE_TABLE_ENTRYW ServiceStartTable; // [rsp+38h] [rbp-40h] BYREF
  __int64 v17; // [rsp+48h] [rbp-30h]
  __int64 v18; // [rsp+50h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  ProcessHeap = GetProcessHeap();
  HeapSetInformation(ProcessHeap, HeapEnableTerminationOnCorruption, 0, 0);
  HeapInformation = 2;
  HeapSetInformation(ProcessHeap, HeapCompatibilityInformation, &HeapInformation, 4u);
  try
  {
    Vml::VmExeModule<ComputeServiceModule>::InitializeSecurityMitigationOptions(v6);
    GetModuleHandleW(0);
    Vml::VmModule<ComputeServiceModule>::Initialize(v7);
    if ( a2 <= 0 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xB33,
        (unsigned int)"onecore\\vm\\common\\vml\\VmModules.h",
        v8);
    for ( i = 0; i < a2 - 1; ++i )
    {
      v10 = *(_WORD **)(a3 + 8LL * i + 8);
      if ( ((*v10 - 45) & 0xFFFD) == 0 )
      {
        v11 = v10 + 1;
        if ( !(unsigned int)_o__wcsicmp(v10 + 1, L"regserver") )
        {
          Vml::VmServiceModule<ComputeServiceModule>::RegisterServer();
          goto LABEL_22;
        }
        if ( !(unsigned int)_o__wcsicmp(v11, L"unregserver") )
        {
          Vml::VmServiceModule<ComputeServiceModule>::UnregisterServer();
          goto LABEL_22;
        }
      }
    }
    ServiceStartTable.lpServiceName = (LPWSTR)Vml::VmServiceModule<ComputeServiceModule>::GetServiceName(&g_Module);
    ServiceStartTable.lpServiceProc = (LPSERVICE_MAIN_FUNCTIONW)Vml::VmServiceModule<ComputeServiceModule>::ServiceMain;
    v17 = 0;
    v18 = 0;
    if ( !StartServiceCtrlDispatcherW(&ServiceStartTable) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xB42,
        (unsigned int)"onecore\\vm\\common\\vml\\VmModules.h",
        v12);
  }
  catch ( ... )
  {
  }
LABEL_22:
  if ( qword_1403D36D8 )
    qword_1403D36D8();
  Vml::VmSharableObject::WaitUntilAllocatedObjectCountIsZero();
  VmlEtwTraceFinalize();
  if ( (*(__int64 (__fastcall **)(__int64 *))(g_Module + 48))(&g_Module) )
  {
    v13 = (*(__int64 (__fastcall **)(__int64 *))(g_Module + 40))(&g_Module);
    TraceLoggingUnregister_EventUnregister(v13);
  }
  Vml::VmModuleBase::gm_ModuleBase = 0;
  return 0;
}

```

## disassembly

```asm
0x140113430  mov     [rsp+arg_0], rbx
0x140113435  mov     [rsp+arg_8], rsi
0x14011343a  push    r12
0x14011343c  push    r14
0x14011343e  push    r15
0x140113440  sub     rsp, 60h
0x140113444  mov     rax, cs:__security_cookie
0x14011344b  xor     rax, rsp
0x14011344e  mov     [rsp+78h+var_20], rax
0x140113453  mov     r12, r8
0x140113456  mov     r14d, edx
0x140113459  lea     rsi, ?g_Module@@3VComputeServiceModule@@A; ComputeServiceModule g_Module
0x140113460  mov     [rsp+78h+var_50], rsi
0x140113465  mov     [rsp+78h+var_54], 1
0x14011346d  mov     [rsp+78h+var_58], 0
0x140113472  call    cs:__imp_GetProcessHeap
0x140113479  nop     dword ptr [rax+rax+00h]
0x14011347e  mov     rbx, rax
0x140113481  xor     r9d, r9d; HeapInformationLength
0x140113484  xor     r8d, r8d; HeapInformation
0x140113487  lea     edx, [r9+1]; HeapInformationClass
0x14011348b  mov     rcx, rax; HeapHandle
0x14011348e  call    cs:__imp_HeapSetInformation
0x140113495  nop     dword ptr [rax+rax+00h]
0x14011349a  mov     [rsp+78h+HeapInformation], 2
0x1401134a2  mov     r9d, 4; HeapInformationLength
0x1401134a8  lea     r8, [rsp+78h+HeapInformation]; HeapInformation
0x1401134ad  xor     edx, edx; HeapInformationClass
0x1401134af  mov     rcx, rbx; HeapHandle
0x1401134b2  call    cs:__imp_HeapSetInformation
0x1401134b9  nop     dword ptr [rax+rax+00h]
0x1401134be  call    ?InitializeSecurityMitigationOptions@?$VmExeModule@VComputeServiceModule@@@Vml@@IEAAXXZ; Vml::VmExeModule<ComputeServiceModule>::InitializeSecurityMitigationOptions(void)
0x1401134c3  xor     ecx, ecx; lpModuleName
0x1401134c5  call    cs:__imp_GetModuleHandleW
0x1401134cc  nop     dword ptr [rax+rax+00h]
0x1401134d1  call    ?Initialize@?$VmModule@VComputeServiceModule@@@Vml@@QEAAXPEAUHINSTANCE__@@@Z; Vml::VmModule<ComputeServiceModule>::Initialize(HINSTANCE__ *)
0x1401134d6  mov     rcx, [rsp+78h]; this
0x1401134db  test    r14d, r14d
0x1401134de  jg      short loc_1401134F2
0x1401134e0  lea     r8, aOnecoreVmCommo_2; "onecore\\vm\\common\\vml\\VmModules.h"
0x1401134e7  mov     edx, 0B33h; void *
0x1401134ec  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1401134f2  mov     [rsp+78h+var_58], 1
0x1401134f7  xor     ebx, ebx
0x1401134f9  lea     eax, [r14-1]
0x1401134fd  cmp     ebx, eax
0x1401134ff  jge     short loc_14011356F
0x140113501  movsxd  rax, ebx
0x140113504  mov     rcx, [r12+rax*8+8]
0x140113509  movzx   eax, word ptr [rcx]
0x14011350c  sub     ax, 2Dh ; '-'
0x140113510  mov     edx, 0FFFDh
0x140113515  test    dx, ax
0x140113518  jnz     short loc_14011356B
0x14011351a  lea     r15, [rcx+2]
0x14011351e  lea     rdx, aRegserver; "regserver"
0x140113525  mov     rcx, r15
0x140113528  call    cs:__imp__o__wcsicmp
0x14011352f  nop     dword ptr [rax+rax+00h]
0x140113534  test    eax, eax
0x140113536  jnz     short loc_14011354A
0x140113538  call    ?RegisterServer@?$VmServiceModule@VComputeServiceModule@@@Vml@@QEAAXXZ; Vml::VmServiceModule<ComputeServiceModule>::RegisterServer(void)
0x14011353d  mov     [rsp+78h+var_54], 0
0x140113545  jmp     loc_1401135D2
0x14011354a  lea     rdx, aUnregserver; "unregserver"
0x140113551  mov     rcx, r15
0x140113554  call    cs:__imp__o__wcsicmp
0x14011355b  nop     dword ptr [rax+rax+00h]
0x140113560  test    eax, eax
0x140113562  jnz     short loc_14011356B
0x140113564  call    ?UnregisterServer@?$VmServiceModule@VComputeServiceModule@@@Vml@@QEAAXXZ; Vml::VmServiceModule<ComputeServiceModule>::UnregisterServer(void)
0x140113569  jmp     short loc_14011353D
0x14011356b  inc     ebx
0x14011356d  jmp     short loc_1401134F9
0x14011356f  mov     rcx, rsi
0x140113572  call    ?GetServiceName@?$VmServiceModule@VComputeServiceModule@@@Vml@@QEBAPEBGXZ; Vml::VmServiceModule<ComputeServiceModule>::GetServiceName(void)
0x140113577  mov     [rsp+78h+ServiceStartTable.lpServiceName], rax
0x14011357c  lea     rax, ?ServiceMain@?$VmServiceModule@VComputeServiceModule@@@Vml@@CAXKPEAPEAG@Z; Vml::VmServiceModule<ComputeServiceModule>::ServiceMain(ulong,ushort * *)
0x140113583  mov     [rsp+78h+ServiceStartTable.lpServiceProc], rax
0x140113588  mov     [rsp+78h+var_30], 0
0x140113591  mov     [rsp+78h+var_28], 0
0x14011359a  lea     rcx, [rsp+78h+ServiceStartTable]; lpServiceStartTable
0x14011359f  call    cs:__imp_StartServiceCtrlDispatcherW
0x1401135a6  nop     dword ptr [rax+rax+00h]
0x1401135ab  mov     rcx, [rsp+78h]; this
0x1401135b0  test    eax, eax
0x1401135b2  jnz     short loc_14011353D
0x1401135b4  lea     r8, aOnecoreVmCommo_2; "onecore\\vm\\common\\vml\\VmModules.h"
0x1401135bb  mov     edx, 0B42h; void *
0x1401135c0  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1401135c6  cmp     [rsp+78h+var_58], 0
0x1401135cb  jz      short loc_14011362B
0x1401135cd  mov     rsi, [rsp+78h+var_50]
0x1401135d2  mov     rax, cs:qword_1403D36D8
0x1401135d9  test    rax, rax
0x1401135dc  jz      short loc_1401135E3
0x1401135de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401135e3  call    ?WaitUntilAllocatedObjectCountIsZero@VmSharableObject@Vml@@SAXXZ; Vml::VmSharableObject::WaitUntilAllocatedObjectCountIsZero(void)
0x1401135e8  call    ?VmlEtwTraceFinalize@@YAXXZ; VmlEtwTraceFinalize(void)
0x1401135ed  mov     rax, cs:?g_Module@@3VComputeServiceModule@@A; ComputeServiceModule g_Module
0x1401135f4  mov     rcx, rsi
0x1401135f7  mov     rax, [rax+30h]
0x1401135fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140113600  test    rax, rax
0x140113603  jz      short loc_140113620
0x140113605  mov     rax, cs:?g_Module@@3VComputeServiceModule@@A; ComputeServiceModule g_Module
0x14011360c  mov     rcx, rsi
0x14011360f  mov     rax, [rax+28h]
0x140113613  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140113618  mov     rcx, rax
0x14011361b  call    TraceLoggingUnregister_EventUnregister
0x140113620  mov     cs:?gm_ModuleBase@VmModuleBase@Vml@@1PEAV12@EA, 0; Vml::VmModuleBase * Vml::VmModuleBase::gm_ModuleBase
0x14011362b  mov     eax, [rsp+78h+var_54]
0x14011362f  mov     rcx, [rsp+78h+var_20]
0x140113634  xor     rcx, rsp; StackCookie
0x140113637  call    __security_check_cookie
0x14011363c  lea     r11, [rsp+78h+var_18]
0x140113641  mov     rbx, [r11+20h]
0x140113645  mov     rsi, [r11+28h]
0x140113649  mov     rsp, r11
0x14011364c  pop     r15
0x14011364e  pop     r14
0x140113650  pop     r12
0x140113652  retn
```
