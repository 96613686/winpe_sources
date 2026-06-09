# CServiceModule::Run(void)

- ea: `0x180033b14`
- end: `0x180033ed9`
- name: `?Run@CServiceModule@@QEAAXXZ`
- size: `965`
- prototype: `void __fastcall(CServiceModule *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180033ee0`

## callees

- `0x18001347c`
- `0x18001e478`
- `0x180032458`
- `0x180033b14`
- `0x180038ce4`
- `0x180039298`
- `0x180039a84`
- `0x180041894`
- `0x180042eb8`
- `0x180045338`
- `0x1800506d8`
- `0x180055010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180033b40`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180033b9d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180033b40`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180033b9d`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180033bf6`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180033bf6`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180033ec5`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180033ec5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180033c5f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180033c5f`

## pseudocode

```c
void __fastcall CServiceModule::Run(CServiceModule *this)
{
  int v1; // ebx
  int v2; // esi
  unsigned int Win32Error; // eax
  unsigned int v4; // eax
  unsigned int v5; // eax
  int v6; // ebx
  unsigned int v7; // eax
  int v8; // ebx
  unsigned int v9; // eax
  int v10; // ebx
  unsigned int NetworkSID; // eax
  CServiceModule *v12; // rcx
  int v13; // ebx
  int v14; // eax
  int v15; // edi
  unsigned int v16; // r8d
  wchar_t *v17; // rcx
  unsigned int v18; // eax
  int v19; // ebx
  wchar_t *v20; // rcx
  LPVOID ppv; // [rsp+80h] [rbp+8h] BYREF

  ppv = this;
  v1 = 0;
  dword_180071C10 = 0;
  dword_180071C14 = 0;
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
  if ( v1 < 0 )
    goto LABEL_61;
  v5 = CoInitializeEx(0, 4u);
  v6 = v5;
  if ( v5 )
  {
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_2670124a663039e2f0c82c5e619b77a4_Traceguids, v5);
    if ( v6 < 0 )
      goto LABEL_61;
  }
  ppv = 0;
  v2 = 1;
  v7 = CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &IID_IGlobalOptions, &ppv);
  v8 = v7;
  if ( v7 )
  {
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_2670124a663039e2f0c82c5e619b77a4_Traceguids, v7);
    if ( v8 < 0 )
      goto LABEL_61;
  }
  v9 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 5, 1);
  v10 = v9;
  if ( v9 && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_2670124a663039e2f0c82c5e619b77a4_Traceguids, v9);
  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v10 < 0 || (int)CWorkItem::HrSyncInitialize() < 0 )
    goto LABEL_61;
  NetworkSID = HrCreateNetworkSID();
  v13 = NetworkSID;
  if ( NetworkSID )
  {
    v12 = (CServiceModule *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_2670124a663039e2f0c82c5e619b77a4_Traceguids, NetworkSID);
    if ( v13 < 0 )
      goto LABEL_61;
  }
  v14 = CServiceModule::TestPersistedRegistrations(v12);
  DWORD2(xmmword_180071C28) = 69;
  v15 = v14;
  CServiceModule::SetServiceStatus((CServiceModule *)&_Module, 4u);
  v17 = (wchar_t *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control )
  {
    if ( (WPP_GLOBAL_Control[14] & 0x40) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_2670124a663039e2f0c82c5e619b77a4_Traceguids);
      v17 = (wchar_t *)WPP_GLOBAL_Control;
    }
    if ( v17 != (wchar_t *)&WPP_GLOBAL_Control && (v17[14] & 0x40) != 0 )
      WPP_SF_(*((_QWORD *)v17 + 2), 23, WPP_2670124a663039e2f0c82c5e619b77a4_Traceguids);
  }
  v18 = ATL::CComModule::RegisterClassObjects((ATL::CComModule *)v17, 0x14u, v16);
  v19 = v18;
  if ( !v18 )
  {
    v20 = (wchar_t *)WPP_GLOBAL_Control;
    goto LABEL_46;
  }
  v20 = (wchar_t *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_2670124a663039e2f0c82c5e619b77a4_Traceguids, v18);
    v20 = (wchar_t *)WPP_GLOBAL_Control;
  }
  if ( v19 < 0 )
  {
LABEL_61:
    CServiceModule::Stop((HANDLE *)&_Module);
    if ( !v2 )
      return;
    goto LABEL_62;
  }
LABEL_46:
  if ( v15 )
  {
    v19 = CServiceModule::CompleteInitialization((struct IUnknown *)v20);
    if ( v19 < 0 )
      goto LABEL_61;
    v20 = (wchar_t *)WPP_GLOBAL_Control;
  }
  if ( !hEvent )
    goto LABEL_62;
  if ( !g_pSvchostSharedGlobals )
  {
    if ( v20 != (wchar_t *)&WPP_GLOBAL_Control && (v20[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)v20 + 2), 26, WPP_2670124a663039e2f0c82c5e619b77a4_Traceguids);
    goto LABEL_61;
  }
  if ( (*((unsigned int (__fastcall **)(__int64 *, const WCHAR *, HANDLE, void (__fastcall *)(void *, int), __int64 *, _DWORD))g_pSvchostSharedGlobals
        + 24))(
         &qword_180071C18,
         L"upnphost",
         hEvent,
         CServiceModule::StopService,
         &_Module,
         0) )
  {
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_2670124a663039e2f0c82c5e619b77a4_Traceguids);
    v19 = -2147467259;
  }
  if ( v19 < 0 )
    goto LABEL_61;
LABEL_62:
  CoUninitialize();
}

```

## disassembly

```asm
0x180033b14  mov     [rsp+arg_0], rcx
0x180033b19  push    rbx
0x180033b1a  push    rsi
0x180033b1b  push    rdi
0x180033b1c  push    r12
0x180033b1e  push    r14
0x180033b20  push    r15
0x180033b22  sub     rsp, 48h
0x180033b26  xor     ebx, ebx
0x180033b28  xor     r9d, r9d; lpName
0x180033b2b  xor     r8d, r8d; bInitialState
0x180033b2e  mov     cs:dword_180071C10, ebx
0x180033b34  xor     edx, edx; bManualReset
0x180033b36  mov     cs:dword_180071C14, ebx
0x180033b3c  xor     ecx, ecx; lpEventAttributes
0x180033b3e  xor     esi, esi
0x180033b40  call    cs:__imp_CreateEventW
0x180033b46  mov     cs:?g_hUnregWorkItemEvent@@3PEAXEA, rax; void * g_hUnregWorkItemEvent
0x180033b4d  lea     r14d, [rbx+1]
0x180033b51  lea     r12, WPP_2670124a663039e2f0c82c5e619b77a4_Traceguids
0x180033b58  lea     r15, WPP_GLOBAL_Control
0x180033b5f  test    rax, rax
0x180033b62  jnz     short loc_180033B93
0x180033b64  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180033b69  mov     ebx, eax
0x180033b6b  test    eax, eax
0x180033b6d  jz      short loc_180033B93
0x180033b6f  mov     rcx, cs:WPP_GLOBAL_Control
0x180033b76  cmp     rcx, r15
0x180033b79  jz      short loc_180033B93
0x180033b7b  test    [rcx+1Ch], r14b
0x180033b7f  jz      short loc_180033B93
0x180033b81  mov     rcx, [rcx+10h]
0x180033b85  lea     edx, [rsi+10h]
0x180033b88  mov     r9d, eax
0x180033b8b  mov     r8, r12
0x180033b8e  call    WPP_SF_d
0x180033b93  xor     r9d, r9d; lpName
0x180033b96  xor     r8d, r8d; bInitialState
0x180033b99  xor     edx, edx; bManualReset
0x180033b9b  xor     ecx, ecx; lpEventAttributes
0x180033b9d  call    cs:__imp_CreateEventW
0x180033ba3  mov     cs:hEvent, rax
0x180033baa  test    rax, rax
0x180033bad  jnz     short loc_180033BE0
0x180033baf  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180033bb4  mov     ebx, eax
0x180033bb6  test    eax, eax
0x180033bb8  jz      short loc_180033BE0
0x180033bba  mov     rcx, cs:WPP_GLOBAL_Control
0x180033bc1  cmp     rcx, r15
0x180033bc4  jz      short loc_180033BE0
0x180033bc6  test    [rcx+1Ch], r14b
0x180033bca  jz      short loc_180033BE0
0x180033bcc  mov     rcx, [rcx+10h]
0x180033bd0  mov     edx, 11h
0x180033bd5  mov     r9d, eax
0x180033bd8  mov     r8, r12
0x180033bdb  call    WPP_SF_d
0x180033be0  lea     rdi, ?_Module@@3VCServiceModule@@A; CServiceModule _Module
0x180033be7  test    ebx, ebx
0x180033be9  js      loc_180033EB9
0x180033bef  mov     edx, 4; dwCoInit
0x180033bf4  xor     ecx, ecx; pvReserved
0x180033bf6  call    cs:__imp_CoInitializeEx
0x180033bfc  mov     ebx, eax
0x180033bfe  test    eax, eax
0x180033c00  jz      short loc_180033C30
0x180033c02  mov     rcx, cs:WPP_GLOBAL_Control
0x180033c09  cmp     rcx, r15
0x180033c0c  jz      short loc_180033C28
0x180033c0e  test    [rcx+1Ch], r14b
0x180033c12  jz      short loc_180033C28
0x180033c14  mov     rcx, [rcx+10h]
0x180033c18  mov     edx, 12h
0x180033c1d  mov     r9d, eax
0x180033c20  mov     r8, r12
0x180033c23  call    WPP_SF_d
0x180033c28  test    ebx, ebx
0x180033c2a  js      loc_180033EB9
0x180033c30  lea     rax, [rsp+78h+arg_0]
0x180033c38  mov     [rsp+78h+arg_0], 0
0x180033c44  lea     r9, IID_IGlobalOptions; riid
0x180033c4b  mov     [rsp+78h+ppv], rax; ppv
0x180033c50  mov     r8d, r14d; dwClsContext
0x180033c53  lea     rcx, CLSID_GlobalOptions; rclsid
0x180033c5a  xor     edx, edx; pUnkOuter
0x180033c5c  mov     esi, r14d
0x180033c5f  call    cs:__imp_CoCreateInstance
0x180033c65  mov     ebx, eax
0x180033c67  test    eax, eax
0x180033c69  jz      short loc_180033C99
0x180033c6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180033c72  cmp     rcx, r15
0x180033c75  jz      short loc_180033C91
0x180033c77  test    [rcx+1Ch], r14b
0x180033c7b  jz      short loc_180033C91
0x180033c7d  mov     rcx, [rcx+10h]
0x180033c81  mov     edx, 13h
0x180033c86  mov     r9d, eax
0x180033c89  mov     r8, r12
0x180033c8c  call    WPP_SF_d
0x180033c91  test    ebx, ebx
0x180033c93  js      loc_180033EB9
0x180033c99  mov     rcx, [rsp+78h+arg_0]
0x180033ca1  mov     r8, r14
0x180033ca4  mov     edx, 5
0x180033ca9  mov     rax, [rcx]
0x180033cac  mov     rax, [rax+18h]
0x180033cb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033cb5  mov     ebx, eax
0x180033cb7  test    eax, eax
0x180033cb9  jz      short loc_180033CE1
0x180033cbb  mov     rcx, cs:WPP_GLOBAL_Control
0x180033cc2  cmp     rcx, r15
0x180033cc5  jz      short loc_180033CE1
0x180033cc7  test    [rcx+1Ch], r14b
0x180033ccb  jz      short loc_180033CE1
0x180033ccd  mov     rcx, [rcx+10h]
0x180033cd1  mov     edx, 14h
0x180033cd6  mov     r9d, eax
0x180033cd9  mov     r8, r12
0x180033cdc  call    WPP_SF_d
0x180033ce1  mov     rcx, [rsp+78h+arg_0]
0x180033ce9  mov     rax, [rcx]
0x180033cec  mov     rax, [rax+10h]
0x180033cf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033cf5  test    ebx, ebx
0x180033cf7  js      loc_180033EB9
0x180033cfd  call    ?HrSyncInitialize@CWorkItem@@SAJXZ; CWorkItem::HrSyncInitialize(void)
0x180033d02  test    eax, eax
0x180033d04  js      loc_180033EB9
0x180033d0a  call    ?HrCreateNetworkSID@@YAJXZ; HrCreateNetworkSID(void)
0x180033d0f  mov     ebx, eax
0x180033d11  test    eax, eax
0x180033d13  jz      short loc_180033D43
0x180033d15  mov     rcx, cs:WPP_GLOBAL_Control
0x180033d1c  cmp     rcx, r15
0x180033d1f  jz      short loc_180033D3B
0x180033d21  test    [rcx+1Ch], r14b
0x180033d25  jz      short loc_180033D3B
0x180033d27  mov     rcx, [rcx+10h]
0x180033d2b  mov     edx, 15h
0x180033d30  mov     r9d, eax
0x180033d33  mov     r8, r12
0x180033d36  call    WPP_SF_d
0x180033d3b  test    ebx, ebx
0x180033d3d  js      loc_180033EB9
0x180033d43  call    ?TestPersistedRegistrations@CServiceModule@@AEAAHXZ; CServiceModule::TestPersistedRegistrations(void)
0x180033d48  mov     edx, 4; unsigned int
0x180033d4d  mov     dword ptr cs:xmmword_180071C28+8, 45h ; 'E'
0x180033d57  lea     rcx, ?_Module@@3VCServiceModule@@A; this
0x180033d5e  mov     edi, eax
0x180033d60  call    ?SetServiceStatus@CServiceModule@@QEAAXK@Z; CServiceModule::SetServiceStatus(ulong)
0x180033d65  mov     rcx, cs:WPP_GLOBAL_Control
0x180033d6c  cmp     rcx, r15
0x180033d6f  jz      short loc_180033DAB
0x180033d71  test    byte ptr [rcx+1Ch], 40h
0x180033d75  jz      short loc_180033D8F
0x180033d77  mov     rcx, [rcx+10h]
0x180033d7b  mov     edx, 16h
0x180033d80  mov     r8, r12
0x180033d83  call    WPP_SF_
0x180033d88  mov     rcx, cs:WPP_GLOBAL_Control
0x180033d8f  cmp     rcx, r15
0x180033d92  jz      short loc_180033DAB
0x180033d94  test    byte ptr [rcx+1Ch], 40h
0x180033d98  jz      short loc_180033DAB
0x180033d9a  mov     rcx, [rcx+10h]
0x180033d9e  mov     edx, 17h
0x180033da3  mov     r8, r12
0x180033da6  call    WPP_SF_
0x180033dab  mov     edx, 14h; unsigned int
0x180033db0  call    ?RegisterClassObjects@CComModule@ATL@@QEAAJKK@Z; ATL::CComModule::RegisterClassObjects(ulong,ulong)
0x180033db5  mov     ebx, eax
0x180033db7  test    eax, eax
0x180033db9  jz      short loc_180033DF2
0x180033dbb  mov     rcx, cs:WPP_GLOBAL_Control
0x180033dc2  cmp     rcx, r15
0x180033dc5  jz      short loc_180033DE8
0x180033dc7  test    [rcx+1Ch], r14b
0x180033dcb  jz      short loc_180033DE8
0x180033dcd  mov     rcx, [rcx+10h]
0x180033dd1  mov     edx, 18h
0x180033dd6  mov     r9d, eax
0x180033dd9  mov     r8, r12
0x180033ddc  call    WPP_SF_d
0x180033de1  mov     rcx, cs:WPP_GLOBAL_Control
0x180033de8  test    ebx, ebx
0x180033dea  js      loc_180033EB2
0x180033df0  jmp     short loc_180033DF9
0x180033df2  mov     rcx, cs:WPP_GLOBAL_Control; this
0x180033df9  test    edi, edi
0x180033dfb  jz      short loc_180033E13
0x180033dfd  call    ?CompleteInitialization@CServiceModule@@QEAAJXZ; CServiceModule::CompleteInitialization(void)
0x180033e02  mov     ebx, eax
0x180033e04  test    eax, eax
0x180033e06  js      loc_180033EB2
0x180033e0c  mov     rcx, cs:WPP_GLOBAL_Control
0x180033e13  mov     r8, cs:hEvent
0x180033e1a  test    r8, r8
0x180033e1d  jz      loc_180033EC5
0x180033e23  mov     rax, cs:?g_pSvchostSharedGlobals@@3PEAU_SVCHOST_GLOBAL_DATA@@EA; _SVCHOST_GLOBAL_DATA * g_pSvchostSharedGlobals
0x180033e2a  test    rax, rax
0x180033e2d  jz      short loc_180033E96
0x180033e2f  mov     rax, [rax+0C0h]
0x180033e36  lea     rdi, ?_Module@@3VCServiceModule@@A; CServiceModule _Module
0x180033e3d  mov     [rsp+78h+var_50], 0
0x180033e45  lea     r9, ?StopService@CServiceModule@@SAXPEAXH@Z; CServiceModule::StopService(void *,int)
0x180033e4c  lea     rdx, ServiceName; "upnphost"
0x180033e53  mov     [rsp+78h+ppv], rdi
0x180033e58  lea     rcx, qword_180071C18
0x180033e5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033e64  test    eax, eax
0x180033e66  jz      short loc_180033E90
0x180033e68  mov     rcx, cs:WPP_GLOBAL_Control
0x180033e6f  cmp     rcx, r15
0x180033e72  jz      short loc_180033E8B
0x180033e74  test    [rcx+1Ch], r14b
0x180033e78  jz      short loc_180033E8B
0x180033e7a  mov     rcx, [rcx+10h]
0x180033e7e  mov     edx, 19h
0x180033e83  mov     r8, r12
0x180033e86  call    WPP_SF_
0x180033e8b  mov     ebx, 80004005h
0x180033e90  test    ebx, ebx
0x180033e92  jns     short loc_180033EC5
0x180033e94  jmp     short loc_180033EB9
0x180033e96  cmp     rcx, r15
0x180033e99  jz      short loc_180033EB2
0x180033e9b  test    [rcx+1Ch], r14b
0x180033e9f  jz      short loc_180033EB2
0x180033ea1  mov     rcx, [rcx+10h]
0x180033ea5  mov     edx, 1Ah
0x180033eaa  mov     r8, r12
0x180033ead  call    WPP_SF_
0x180033eb2  lea     rdi, ?_Module@@3VCServiceModule@@A; CServiceModule _Module
0x180033eb9  mov     rcx, rdi; this
0x180033ebc  call    ?Stop@CServiceModule@@QEAAXXZ; CServiceModule::Stop(void)
0x180033ec1  test    esi, esi
0x180033ec3  jz      short loc_180033ECB
0x180033ec5  call    cs:__imp_CoUninitialize
0x180033ecb  add     rsp, 48h
0x180033ecf  pop     r15
0x180033ed1  pop     r14
0x180033ed3  pop     r12
0x180033ed5  pop     rdi
0x180033ed6  pop     rsi
0x180033ed7  pop     rbx
0x180033ed8  retn
```
