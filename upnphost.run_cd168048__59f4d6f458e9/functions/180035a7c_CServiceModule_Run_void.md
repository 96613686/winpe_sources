# CServiceModule::Run(void)

- ea: `0x180035a7c`
- end: `0x180035e93`
- name: `?Run@CServiceModule@@QEAAXXZ`
- size: `1047`
- prototype: `void __fastcall(CServiceModule *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180035e9c`

## callees

- `0x1800074dc`
- `0x1800134e4`
- `0x180034254`
- `0x180035a7c`
- `0x18003b1cc`
- `0x18003b800`
- `0x18003c018`
- `0x180040588`
- `0x1800441d8`
- `0x1800458e0`
- `0x180047f00`
- `0x180053d5c`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180035ab1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180035b14`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180035ab1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180035b14`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180035b6e`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180035b6e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180035e6d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180035e6d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180035bd5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180035bd5`

## pseudocode

```c
void __fastcall CServiceModule::Run(CServiceModule *this)
{
  int v1; // ebx
  int v2; // ebp
  unsigned int Win32Error; // eax
  unsigned int v4; // eax
  unsigned int v5; // eax
  unsigned int v6; // eax
  unsigned int v7; // eax
  unsigned int NetworkSID; // eax
  CServiceModule *v9; // rcx
  int v10; // ebx
  int v11; // eax
  int v12; // esi
  unsigned int v13; // r8d
  wchar_t *v14; // rcx
  ATL::_ATL_OBJMAP_ENTRY30 *v15; // rdi
  int v16; // ebx
  int v17; // eax
  wchar_t *v18; // rcx
  LPVOID ppv; // [rsp+70h] [rbp+8h] BYREF

  ppv = this;
  v1 = 0;
  dword_180075D00 = 0;
  dword_180075D04 = 0;
  v2 = 0;
  g_hUnregWorkItemEvent = CreateEventW(0, 0, 0, 0);
  if ( !g_hUnregWorkItemEvent )
  {
    Win32Error = HrFromLastWin32Error();
    v1 = Win32Error;
    if ( Win32Error )
    {
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_2670124a663039e2f0c82c5e619b77a4_Traceguids, Win32Error);
    }
  }
  hEvent = CreateEventW(0, 0, 0, 0);
  if ( !hEvent )
  {
    v4 = HrFromLastWin32Error();
    v1 = v4;
    if ( v4 )
    {
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_2670124a663039e2f0c82c5e619b77a4_Traceguids, v4);
    }
  }
  if ( v1 >= 0 )
  {
    v5 = CoInitializeEx(0, 4u);
    v1 = v5;
    if ( !v5 )
      goto LABEL_17;
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_2670124a663039e2f0c82c5e619b77a4_Traceguids, v5);
    if ( v1 >= 0 )
    {
LABEL_17:
      ppv = 0;
      v2 = 1;
      v6 = CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &IID_IGlobalOptions, &ppv);
      v1 = v6;
      if ( !v6 )
        goto LABEL_22;
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_2670124a663039e2f0c82c5e619b77a4_Traceguids, v6);
      if ( v1 >= 0 )
      {
LABEL_22:
        v7 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 5, 1);
        v1 = v7;
        if ( v7 && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_2670124a663039e2f0c82c5e619b77a4_Traceguids, v7);
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      }
    }
  }
  if ( v1 < 0 || (int)CWorkItem::HrSyncInitialize() < 0 )
    goto LABEL_68;
  NetworkSID = HrCreateNetworkSID();
  v10 = NetworkSID;
  if ( NetworkSID )
  {
    v9 = (CServiceModule *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_2670124a663039e2f0c82c5e619b77a4_Traceguids, NetworkSID);
    if ( v10 < 0 )
      goto LABEL_68;
  }
  v11 = CServiceModule::TestPersistedRegistrations(v9);
  DWORD2(xmmword_180075D18) = 69;
  v12 = v11;
  CServiceModule::SetServiceStatus((CServiceModule *)&_Module, 4u);
  v14 = (wchar_t *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control )
  {
    if ( (WPP_GLOBAL_Control[14] & 0x40) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_2670124a663039e2f0c82c5e619b77a4_Traceguids);
      v14 = (wchar_t *)WPP_GLOBAL_Control;
    }
    if ( v14 != (wchar_t *)&WPP_GLOBAL_Control && (v14[14] & 0x40) != 0 )
      WPP_SF_(*((_QWORD *)v14 + 2), 23, WPP_2670124a663039e2f0c82c5e619b77a4_Traceguids);
  }
  v15 = qword_180075CF8;
  if ( qword_180075CF8 && (v16 = 0, *(_QWORD *)qword_180075CF8) )
  {
    while ( !v16 )
    {
      v17 = ATL::_ATL_OBJMAP_ENTRY30::RegisterClassObject(v15, 0x14u, v13);
      v15 = (ATL::_ATL_OBJMAP_ENTRY30 *)((char *)v15 + 72);
      v16 = v17;
      if ( !*(_QWORD *)v15 )
      {
        if ( v17 )
          goto LABEL_46;
        goto LABEL_45;
      }
    }
  }
  else
  {
LABEL_45:
    v16 = ATL::AtlComModuleRegisterClassObjects((struct ATL::_ATL_COM_MODULE70 *)v14, 0x14u, v13);
LABEL_46:
    if ( !v16 )
    {
      v18 = (wchar_t *)WPP_GLOBAL_Control;
      goto LABEL_53;
    }
  }
  v18 = (wchar_t *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      24,
      WPP_2670124a663039e2f0c82c5e619b77a4_Traceguids,
      (unsigned int)v16);
    v18 = (wchar_t *)WPP_GLOBAL_Control;
  }
  if ( v16 < 0 )
    goto LABEL_68;
LABEL_53:
  if ( v12 )
  {
    v16 = CServiceModule::CompleteInitialization((CServiceModule *)v18);
    if ( v16 < 0 )
      goto LABEL_68;
    v18 = (wchar_t *)WPP_GLOBAL_Control;
  }
  if ( !hEvent )
    goto LABEL_69;
  if ( !g_pSvchostSharedGlobals )
  {
    if ( v18 != (wchar_t *)&WPP_GLOBAL_Control && (v18[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)v18 + 2), 26, WPP_2670124a663039e2f0c82c5e619b77a4_Traceguids);
    goto LABEL_68;
  }
  if ( (*((unsigned int (__fastcall **)(__int64 *, const WCHAR *, HANDLE, void (__fastcall *)(void *, int), __int64 *, _DWORD))g_pSvchostSharedGlobals
        + 24))(
         &qword_180075D08,
         L"upnphost",
         hEvent,
         CServiceModule::StopService,
         &_Module,
         0) )
  {
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_2670124a663039e2f0c82c5e619b77a4_Traceguids);
    v16 = -2147467259;
  }
  if ( v16 < 0 )
LABEL_68:
    CServiceModule::Stop((CServiceModule *)&_Module);
LABEL_69:
  if ( v2 )
    CoUninitialize();
}

```

## disassembly

```asm
0x180035a7c  mov     [rsp+arg_8], rbx
0x180035a81  mov     [rsp+arg_10], rbp
0x180035a86  mov     [rsp+arg_0], rcx
0x180035a8b  push    rsi
0x180035a8c  push    rdi
0x180035a8d  push    r12
0x180035a8f  push    r13
0x180035a91  push    r15
0x180035a93  sub     rsp, 40h
0x180035a97  xor     ebx, ebx
0x180035a99  xor     r9d, r9d; lpName
0x180035a9c  xor     r8d, r8d; bInitialState
0x180035a9f  mov     cs:dword_180075D00, ebx
0x180035aa5  xor     edx, edx; bManualReset
0x180035aa7  mov     cs:dword_180075D04, ebx
0x180035aad  xor     ecx, ecx; lpEventAttributes
0x180035aaf  xor     ebp, ebp
0x180035ab1  call    cs:__imp_CreateEventW
0x180035ab8  nop     dword ptr [rax+rax+00h]
0x180035abd  mov     cs:?g_hUnregWorkItemEvent@@3PEAXEA, rax; void * g_hUnregWorkItemEvent
0x180035ac4  lea     r15d, [rbx+1]
0x180035ac8  lea     r13, WPP_2670124a663039e2f0c82c5e619b77a4_Traceguids
0x180035acf  lea     r12, WPP_GLOBAL_Control
0x180035ad6  test    rax, rax
0x180035ad9  jnz     short loc_180035B0A
0x180035adb  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180035ae0  mov     ebx, eax
0x180035ae2  test    eax, eax
0x180035ae4  jz      short loc_180035B0A
0x180035ae6  mov     rcx, cs:WPP_GLOBAL_Control
0x180035aed  cmp     rcx, r12
0x180035af0  jz      short loc_180035B0A
0x180035af2  test    [rcx+1Ch], r15b
0x180035af6  jz      short loc_180035B0A
0x180035af8  mov     rcx, [rcx+10h]
0x180035afc  lea     edx, [rbp+10h]
0x180035aff  mov     r9d, eax
0x180035b02  mov     r8, r13
0x180035b05  call    WPP_SF_d
0x180035b0a  xor     r9d, r9d; lpName
0x180035b0d  xor     r8d, r8d; bInitialState
0x180035b10  xor     edx, edx; bManualReset
0x180035b12  xor     ecx, ecx; lpEventAttributes
0x180035b14  call    cs:__imp_CreateEventW
0x180035b1b  nop     dword ptr [rax+rax+00h]
0x180035b20  mov     cs:hEvent, rax
0x180035b27  test    rax, rax
0x180035b2a  jnz     short loc_180035B5D
0x180035b2c  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180035b31  mov     ebx, eax
0x180035b33  test    eax, eax
0x180035b35  jz      short loc_180035B5D
0x180035b37  mov     rcx, cs:WPP_GLOBAL_Control
0x180035b3e  cmp     rcx, r12
0x180035b41  jz      short loc_180035B5D
0x180035b43  test    [rcx+1Ch], r15b
0x180035b47  jz      short loc_180035B5D
0x180035b49  mov     rcx, [rcx+10h]
0x180035b4d  mov     edx, 11h
0x180035b52  mov     r9d, eax
0x180035b55  mov     r8, r13
0x180035b58  call    WPP_SF_d
0x180035b5d  mov     edi, 4
0x180035b62  test    ebx, ebx
0x180035b64  js      loc_180035C67
0x180035b6a  mov     edx, edi; dwCoInit
0x180035b6c  xor     ecx, ecx; pvReserved
0x180035b6e  call    cs:__imp_CoInitializeEx
0x180035b75  nop     dword ptr [rax+rax+00h]
0x180035b7a  mov     ebx, eax
0x180035b7c  test    eax, eax
0x180035b7e  jz      short loc_180035BAC
0x180035b80  mov     rcx, cs:WPP_GLOBAL_Control
0x180035b87  cmp     rcx, r12
0x180035b8a  jz      short loc_180035BA4
0x180035b8c  test    [rcx+1Ch], r15b
0x180035b90  jz      short loc_180035BA4
0x180035b92  mov     rcx, [rcx+10h]
0x180035b96  lea     edx, [rdi+0Eh]
0x180035b99  mov     r9d, eax
0x180035b9c  mov     r8, r13
0x180035b9f  call    WPP_SF_d
0x180035ba4  test    ebx, ebx
0x180035ba6  js      loc_180035C67
0x180035bac  lea     rax, [rsp+68h+arg_0]
0x180035bb1  mov     [rsp+68h+arg_0], 0
0x180035bba  lea     r9, IID_IGlobalOptions; riid
0x180035bc1  mov     [rsp+68h+ppv], rax; ppv
0x180035bc6  mov     r8d, r15d; dwClsContext
0x180035bc9  lea     rcx, CLSID_GlobalOptions; rclsid
0x180035bd0  xor     edx, edx; pUnkOuter
0x180035bd2  mov     ebp, r15d
0x180035bd5  call    cs:__imp_CoCreateInstance
0x180035bdc  nop     dword ptr [rax+rax+00h]
0x180035be1  mov     ebx, eax
0x180035be3  test    eax, eax
0x180035be5  jz      short loc_180035C11
0x180035be7  mov     rcx, cs:WPP_GLOBAL_Control
0x180035bee  cmp     rcx, r12
0x180035bf1  jz      short loc_180035C0D
0x180035bf3  test    [rcx+1Ch], r15b
0x180035bf7  jz      short loc_180035C0D
0x180035bf9  mov     rcx, [rcx+10h]
0x180035bfd  mov     edx, 13h
0x180035c02  mov     r9d, eax
0x180035c05  mov     r8, r13
0x180035c08  call    WPP_SF_d
0x180035c0d  test    ebx, ebx
0x180035c0f  js      short loc_180035C67
0x180035c11  mov     rcx, [rsp+68h+arg_0]
0x180035c16  mov     r8, r15
0x180035c19  mov     edx, 5
0x180035c1e  mov     rax, [rcx]
0x180035c21  mov     rax, [rax+18h]
0x180035c25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035c2a  mov     ebx, eax
0x180035c2c  test    eax, eax
0x180035c2e  jz      short loc_180035C56
0x180035c30  mov     rcx, cs:WPP_GLOBAL_Control
0x180035c37  cmp     rcx, r12
0x180035c3a  jz      short loc_180035C56
0x180035c3c  test    [rcx+1Ch], r15b
0x180035c40  jz      short loc_180035C56
0x180035c42  mov     rcx, [rcx+10h]
0x180035c46  mov     edx, 14h
0x180035c4b  mov     r9d, eax
0x180035c4e  mov     r8, r13
0x180035c51  call    WPP_SF_d
0x180035c56  mov     rcx, [rsp+68h+arg_0]
0x180035c5b  mov     rax, [rcx]
0x180035c5e  mov     rax, [rax+10h]
0x180035c62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035c67  lea     rsi, ?_Module@@3VCServiceModule@@A; CServiceModule _Module
0x180035c6e  test    ebx, ebx
0x180035c70  js      loc_180035E61
0x180035c76  call    ?HrSyncInitialize@CWorkItem@@SAJXZ; CWorkItem::HrSyncInitialize(void)
0x180035c7b  test    eax, eax
0x180035c7d  js      loc_180035E61
0x180035c83  call    ?HrCreateNetworkSID@@YAJXZ; HrCreateNetworkSID(void)
0x180035c88  mov     ebx, eax
0x180035c8a  test    eax, eax
0x180035c8c  jz      short loc_180035CBC
0x180035c8e  mov     rcx, cs:WPP_GLOBAL_Control
0x180035c95  cmp     rcx, r12
0x180035c98  jz      short loc_180035CB4
0x180035c9a  test    [rcx+1Ch], r15b
0x180035c9e  jz      short loc_180035CB4
0x180035ca0  mov     rcx, [rcx+10h]
0x180035ca4  mov     edx, 15h
0x180035ca9  mov     r9d, eax
0x180035cac  mov     r8, r13
0x180035caf  call    WPP_SF_d
0x180035cb4  test    ebx, ebx
0x180035cb6  js      loc_180035E61
0x180035cbc  call    ?TestPersistedRegistrations@CServiceModule@@AEAAHXZ; CServiceModule::TestPersistedRegistrations(void)
0x180035cc1  mov     edx, edi; unsigned int
0x180035cc3  mov     dword ptr cs:xmmword_180075D18+8, 45h ; 'E'
0x180035ccd  lea     rcx, ?_Module@@3VCServiceModule@@A; this
0x180035cd4  mov     esi, eax
0x180035cd6  call    ?SetServiceStatus@CServiceModule@@QEAAXK@Z; CServiceModule::SetServiceStatus(ulong)
0x180035cdb  mov     rcx, cs:WPP_GLOBAL_Control
0x180035ce2  cmp     rcx, r12
0x180035ce5  jz      short loc_180035D21
0x180035ce7  test    byte ptr [rcx+1Ch], 40h
0x180035ceb  jz      short loc_180035D05
0x180035ced  mov     rcx, [rcx+10h]
0x180035cf1  mov     edx, 16h
0x180035cf6  mov     r8, r13
0x180035cf9  call    WPP_SF_
0x180035cfe  mov     rcx, cs:WPP_GLOBAL_Control
0x180035d05  cmp     rcx, r12
0x180035d08  jz      short loc_180035D21
0x180035d0a  test    byte ptr [rcx+1Ch], 40h
0x180035d0e  jz      short loc_180035D21
0x180035d10  mov     rcx, [rcx+10h]
0x180035d14  mov     edx, 17h
0x180035d19  mov     r8, r13
0x180035d1c  call    WPP_SF_
0x180035d21  mov     rdi, cs:qword_180075CF8
0x180035d28  test    rdi, rdi
0x180035d2b  jz      short loc_180035D53
0x180035d2d  xor     ebx, ebx
0x180035d2f  cmp     [rdi], rbx
0x180035d32  jz      short loc_180035D53
0x180035d34  test    ebx, ebx
0x180035d36  jnz     short loc_180035D63
0x180035d38  lea     edx, [rbx+14h]; unsigned int
0x180035d3b  mov     rcx, rdi; this
0x180035d3e  call    ?RegisterClassObject@_ATL_OBJMAP_ENTRY30@ATL@@QEAAJKK@Z; ATL::_ATL_OBJMAP_ENTRY30::RegisterClassObject(ulong,ulong)
0x180035d43  add     rdi, 48h ; 'H'
0x180035d47  mov     ebx, eax
0x180035d49  cmp     qword ptr [rdi], 0
0x180035d4d  jnz     short loc_180035D34
0x180035d4f  test    eax, eax
0x180035d51  jnz     short loc_180035D5F
0x180035d53  mov     edx, 14h; unsigned int
0x180035d58  call    ?AtlComModuleRegisterClassObjects@ATL@@YAJPEAU_ATL_COM_MODULE70@1@KK@Z; ATL::AtlComModuleRegisterClassObjects(ATL::_ATL_COM_MODULE70 *,ulong,ulong)
0x180035d5d  mov     ebx, eax
0x180035d5f  test    ebx, ebx
0x180035d61  jz      short loc_180035D9A
0x180035d63  mov     rcx, cs:WPP_GLOBAL_Control
0x180035d6a  cmp     rcx, r12
0x180035d6d  jz      short loc_180035D90
0x180035d6f  test    [rcx+1Ch], r15b
0x180035d73  jz      short loc_180035D90
0x180035d75  mov     rcx, [rcx+10h]
0x180035d79  mov     edx, 18h
0x180035d7e  mov     r9d, ebx
0x180035d81  mov     r8, r13
0x180035d84  call    WPP_SF_d
0x180035d89  mov     rcx, cs:WPP_GLOBAL_Control
0x180035d90  test    ebx, ebx
0x180035d92  js      loc_180035E5A
0x180035d98  jmp     short loc_180035DA1
0x180035d9a  mov     rcx, cs:WPP_GLOBAL_Control; this
0x180035da1  test    esi, esi
0x180035da3  jz      short loc_180035DBB
0x180035da5  call    ?CompleteInitialization@CServiceModule@@QEAAJXZ; CServiceModule::CompleteInitialization(void)
0x180035daa  mov     ebx, eax
0x180035dac  test    eax, eax
0x180035dae  js      loc_180035E5A
0x180035db4  mov     rcx, cs:WPP_GLOBAL_Control
0x180035dbb  mov     r8, cs:hEvent
0x180035dc2  test    r8, r8
0x180035dc5  jz      loc_180035E69
0x180035dcb  mov     rax, cs:?g_pSvchostSharedGlobals@@3PEAU_SVCHOST_GLOBAL_DATA@@EA; _SVCHOST_GLOBAL_DATA * g_pSvchostSharedGlobals
0x180035dd2  test    rax, rax
0x180035dd5  jz      short loc_180035E3E
0x180035dd7  mov     rax, [rax+0C0h]
0x180035dde  lea     rsi, ?_Module@@3VCServiceModule@@A; CServiceModule _Module
0x180035de5  mov     [rsp+68h+var_40], 0
0x180035ded  lea     r9, ?StopService@CServiceModule@@SAXPEAXH@Z; CServiceModule::StopService(void *,int)
0x180035df4  lea     rdx, ServiceName; "upnphost"
0x180035dfb  mov     [rsp+68h+ppv], rsi
0x180035e00  lea     rcx, qword_180075D08
0x180035e07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035e0c  test    eax, eax
0x180035e0e  jz      short loc_180035E38
0x180035e10  mov     rcx, cs:WPP_GLOBAL_Control
0x180035e17  cmp     rcx, r12
0x180035e1a  jz      short loc_180035E33
0x180035e1c  test    [rcx+1Ch], r15b
0x180035e20  jz      short loc_180035E33
0x180035e22  mov     rcx, [rcx+10h]
0x180035e26  mov     edx, 19h
0x180035e2b  mov     r8, r13
0x180035e2e  call    WPP_SF_
0x180035e33  mov     ebx, 80004005h
0x180035e38  test    ebx, ebx
0x180035e3a  jns     short loc_180035E69
0x180035e3c  jmp     short loc_180035E61
0x180035e3e  cmp     rcx, r12
0x180035e41  jz      short loc_180035E5A
0x180035e43  test    [rcx+1Ch], r15b
0x180035e47  jz      short loc_180035E5A
0x180035e49  mov     rcx, [rcx+10h]
0x180035e4d  mov     edx, 1Ah
0x180035e52  mov     r8, r13
0x180035e55  call    WPP_SF_
0x180035e5a  lea     rsi, ?_Module@@3VCServiceModule@@A; CServiceModule _Module
0x180035e61  mov     rcx, rsi; this
0x180035e64  call    ?Stop@CServiceModule@@QEAAXXZ; CServiceModule::Stop(void)
0x180035e69  test    ebp, ebp
0x180035e6b  jz      short loc_180035E79
0x180035e6d  call    cs:__imp_CoUninitialize
0x180035e74  nop     dword ptr [rax+rax+00h]
0x180035e79  lea     r11, [rsp+68h+var_28]
0x180035e7e  mov     rbx, [r11+38h]
0x180035e82  mov     rbp, [r11+40h]
0x180035e86  mov     rsp, r11
0x180035e89  pop     r15
0x180035e8b  pop     r13
0x180035e8d  pop     r12
0x180035e8f  pop     rdi
0x180035e90  pop     rsi
0x180035e91  retn
```
