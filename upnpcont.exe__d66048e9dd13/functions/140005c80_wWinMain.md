# wWinMain

- ea: `0x140005c80`
- end: `0x1400061f9`
- name: `wWinMain`
- size: `1401`
- prototype: `int __stdcall(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1400012e0`

## callees

- `0x140001110`
- `0x14000111c`
- `0x140001490`
- `0x140002bfc`
- `0x140003a10`
- `0x140003a88`
- `0x140003c44`
- `0x140004538`
- `0x14000485c`
- `0x140005294`
- `0x1400053a0`
- `0x140005c40`
- `0x140005c80`
- `0x140007010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140005e18`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140005e30`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140005e18`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140005e30`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400060ef`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000612e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140006140`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400060ef`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000612e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140006140`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x140005e92`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x140005e92`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140005e5c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140005e5c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140006114`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140006114`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140006063`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140006063`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400060b7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400060b7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140006075`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140006075`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140005cc4`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140005cc4`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x140006006`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x140006046`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x140006006`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x140006046`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400061d5`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400061d5`
- `api-ms-win-core-com-l1-1-0!CoResumeClassObjects` at `0x140005edf`
- `api-ms-win-core-com-l1-1-0!CoResumeClassObjects` at `0x140005edf`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x140005d30`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x140005d30`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x140005cb7`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x140005cb7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005db0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005db0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005ea0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006082`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000609b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005ea0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006082`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000609b`
- `api-ms-win-core-heap-l1-1-0!HeapSetInformation` at `0x140005cb1`
- `api-ms-win-core-heap-l1-1-0!HeapSetInformation` at `0x140005cb1`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetMessageW` at `0x140005fd8`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetMessageW` at `0x140005fd8`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!DispatchMessageW` at `0x140005fc6`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!DispatchMessageW` at `0x140005fc6`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!DestroyWindow` at `0x1400060d5`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!DestroyWindow` at `0x1400060d5`

## pseudocode

```c
int __stdcall wWinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)
{
  LPWSTR CommandLineW; // rdi
  HRESULT v5; // eax
  int v6; // ebx
  void *v7; // rcx
  void (__fastcall **v8)(void *); // rbx
  __int64 *v9; // rbx
  __int64 *v10; // rax
  DWORD CurrentThreadId; // eax
  _QWORD *v12; // rax
  const WCHAR *v13; // rcx
  const unsigned __int16 *v14; // rcx
  const unsigned __int16 *v15; // rcx
  __int64 OneOf; // rax
  const WCHAR *v17; // rbx
  __int64 v18; // rdx
  IUnknown *v19; // rcx
  void *v20; // rax
  int v21; // eax
  HRESULT v22; // eax
  int v23; // edi
  const unsigned __int16 *v24; // rdx
  ATL::CComModule *v25; // rcx
  const struct _GUID *v26; // r8
  int v27; // eax
  const unsigned __int16 *v28; // rdx
  GUID *v29; // rcx
  struct ITypeLib *v30; // r8
  __int64 v31; // rbx
  const struct ATL::_ATL_CATMAP_ENTRY *v32; // rax
  __int64 v33; // rbx
  HRESULT v34; // eax
  DWORD v35; // ecx
  __int64 *v36; // rbx
  HRESULT v37; // eax
  __int64 *v38; // rcx
  __int64 v39; // rdx
  struct ATL::CAtlModule *v40; // r14
  void **v41; // rbx
  _QWORD *v42; // rbx
  void *v43; // rcx
  _QWORD *v44; // rbx
  __int64 v45; // rcx
  void (__fastcall *v46)(_QWORD); // rax
  __int64 *v47; // rbx
  __int64 *v48; // rax
  MSG Msg; // [rsp+50h] [rbp-19h] BYREF
  _DWORD v51[2]; // [rsp+80h] [rbp+17h] BYREF

  HeapSetInformation(0, HeapEnableTerminationOnCorruption, 0, 0);
  CommandLineW = GetCommandLineW();
  v5 = CoInitializeEx(0, 0);
  v6 = v5;
  if ( !v5 )
    goto LABEL_6;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 0xAu, (__int64)WPP_4a3c47521d24325c792b44adb038f8ce_Traceguids, v5);
  if ( v6 >= 0 )
LABEL_6:
    CoInitializeSecurity(0, -1, 0, 0, 2u, 3u, 0, 0, 0);
  v8 = (void (__fastcall **)(void *))&off_14000B000;
  dword_14000B3A4 = 5000;
  dword_14000B3A8 = 1000;
  if ( &off_14000B000 != (_UNKNOWN *)-1LL )
  {
    qword_14000B378 = (__int64)&off_14000B000;
    if ( off_14000B000 )
    {
      do
      {
        LOBYTE(v7) = 1;
        v8[8](v7);
        v8 += 9;
      }
      while ( *v8 );
    }
  }
  v9 = off_14000B0B0[0];
  v10 = off_14000B0B8;
  while ( v9 < v10 )
  {
    if ( *v9 )
    {
      LOBYTE(v7) = 1;
      (*(void (__fastcall **)(void *))(*v9 + 64))(v7);
      v10 = off_14000B0B8;
    }
    ++v9;
  }
  CurrentThreadId = GetCurrentThreadId();
  qword_14000B388 = 0;
  dword_14000B380 = CurrentThreadId;
  v12 = operator new(0x18u);
  if ( v12 )
  {
    *v12 = 0;
    v12[1] = 0;
    *((_DWORD *)v12 + 4) = 0;
  }
  else
  {
    v12 = 0;
  }
  qword_14000B388 = v12;
  if ( v12 )
    Block = 0;
  v13 = CommandLineW;
  wcscpy((wchar_t *)v51, L"-/");
  while ( 1 )
  {
    OneOf = MyFindOneOf(v13, (LPCWSTR)v51);
    v17 = (const WCHAR *)OneOf;
    if ( !OneOf )
    {
      hObject = CreateEventW(0, 0, 0, 0);
      if ( hObject )
      {
        v51[0] = 0;
        v20 = (void *)_o__beginthreadex(0, 0, WTL::CServerAppModule::MonitorProc, &_Module, 0, v51);
        if ( v20 )
          CloseHandle(v20);
      }
      v21 = ATL::CComModule::RegisterClassObjects(v19, v18, 4u);
      if ( v21
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          0xBu,
          (__int64)WPP_4a3c47521d24325c792b44adb038f8ce_Traceguids,
          v21);
      }
      v22 = CoResumeClassObjects();
      v23 = v22;
      if ( v22
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          0xCu,
          (__int64)WPP_4a3c47521d24325c792b44adb038f8ce_Traceguids,
          v22);
      }
      memset(&Msg, 0, sizeof(Msg));
      while ( GetMessageW(&Msg, 0, 0, 0) )
        DispatchMessageW(&Msg);
      v33 = qword_14000B378;
      if ( qword_14000B378 && (v34 = 0, *(_QWORD *)qword_14000B378) )
      {
        while ( !v34 )
        {
          v35 = *(_DWORD *)(v33 + 40);
          if ( v35 )
            v34 = CoRevokeClassObject(v35);
          else
            v34 = 0;
          v33 += 72;
          if ( !*(_QWORD *)v33 )
          {
            if ( v34 )
              break;
            goto LABEL_60;
          }
        }
      }
      else
      {
LABEL_60:
        v36 = off_14000B0B0[0];
        v37 = 0;
        v38 = off_14000B0B8;
        while ( v36 < v38 && !v37 )
        {
          v39 = *v36;
          if ( *v36 )
          {
            if ( *(_DWORD *)(v39 + 40) )
            {
              v37 = CoRevokeClassObject(*(_DWORD *)(v39 + 40));
              v38 = off_14000B0B8;
            }
            else
            {
              v37 = 0;
            }
          }
          ++v36;
        }
      }
      SetEvent(CContainer::s_hEventShutdown);
      WaitForSingleObject(CContainer::s_hThreadShutdown, 0x1F4u);
      CloseHandle(CContainer::s_hThreadShutdown);
      CContainer::s_hThreadShutdown = 0;
      goto LABEL_69;
    }
    if ( !(unsigned int)_o__wcsicmp(OneOf, L"UnregServer") )
      break;
    if ( !(unsigned int)_o__wcsicmp(v17, L"RegServer") )
    {
      v23 = MyRegisterAppId(v15);
      if ( v23 < 0 )
        goto LABEL_69;
      v27 = ATL::CComModule::RegisterServer(v25, v24, v26);
      goto LABEL_49;
    }
    v13 = v17;
  }
  v23 = MyUnregisterAppId(v14);
  if ( v23 >= 0 )
  {
    v31 = qword_14000B378;
    if ( qword_14000B378 )
    {
      while ( *(_QWORD *)v31 )
      {
        v32 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v31 + 56))();
        v23 = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v31, v32, 0);
        if ( v23 < 0 )
          goto LABEL_69;
        v23 = (*(__int64 (__fastcall **)(_QWORD))(v31 + 8))(0);
        if ( v23 < 0 )
          goto LABEL_69;
        v31 += 72;
      }
    }
    if ( !ATL::_pPerfUnRegFunc || (v23 = ATL::_pPerfUnRegFunc(), v23 >= 0) )
    {
      v27 = ATL::CAtlComModule::UnregisterServer(v29, v28, v30);
LABEL_49:
      v23 = v27;
    }
  }
LABEL_69:
  if ( hObject && CloseHandle(hObject) )
    hObject = 0;
  v40 = ATL::_pAtlModule;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)ATL::_pAtlModule + 24));
  v41 = (void **)Block;
  if ( Block )
  {
    if ( *((int *)Block + 2) > 0 )
    {
      DestroyWindow(**(HWND **)Block);
      v41 = (void **)Block;
    }
    if ( v41 )
    {
      if ( *v41 )
      {
        free(*v41);
        *v41 = 0;
      }
      v41[1] = 0;
      operator delete(v41);
    }
  }
  Block = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v40 + 24));
  v42 = qword_14000B388;
  if ( qword_14000B388 )
  {
    if ( *(_QWORD *)qword_14000B388 )
    {
      free(*(void **)qword_14000B388);
      *v42 = 0;
    }
    v43 = (void *)v42[1];
    if ( v43 )
    {
      free(v43);
      v42[1] = 0;
    }
    *((_DWORD *)v42 + 4) = 0;
    operator delete(v42);
  }
  v44 = (_QWORD *)qword_14000B378;
  if ( qword_14000B378 )
  {
    while ( *v44 )
    {
      v45 = v44[4];
      if ( v45 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
      v46 = (void (__fastcall *)(_QWORD))v44[8];
      v44[4] = 0;
      v46(0);
      v44 += 9;
    }
  }
  v47 = off_14000B0B0[0];
  v48 = off_14000B0B8;
  while ( v47 < v48 )
  {
    if ( *v47 )
    {
      (*(void (__fastcall **)(_QWORD))(*v47 + 64))(0);
      v48 = off_14000B0B8;
    }
    ++v47;
  }
  ATL::CAtlModule::Term((ATL::CAtlModule *)&_Module);
  CoUninitialize();
  return v23;
}

```

## disassembly

```asm
0x140005c80  push    rbp
0x140005c82  push    rbx
0x140005c83  push    rsi
0x140005c84  push    rdi
0x140005c85  push    r14
0x140005c87  push    r15
0x140005c89  lea     rbp, [rsp-2Fh]
0x140005c8e  sub     rsp, 98h
0x140005c95  mov     rax, cs:__security_cookie
0x140005c9c  xor     rax, rsp
0x140005c9f  mov     [rbp+57h+var_38], rax
0x140005ca3  xor     r9d, r9d; HeapInformationLength
0x140005ca6  xor     r8d, r8d; HeapInformation
0x140005ca9  xor     ecx, ecx; HeapHandle
0x140005cab  lea     esi, [r9+1]
0x140005caf  mov     edx, esi; HeapInformationClass
0x140005cb1  call    cs:__imp_HeapSetInformation
0x140005cb7  call    cs:__imp_GetCommandLineW
0x140005cbd  xor     edx, edx; dwCoInit
0x140005cbf  xor     ecx, ecx; pvReserved
0x140005cc1  mov     rdi, rax
0x140005cc4  call    cs:__imp_CoInitializeEx
0x140005cca  xor     r15d, r15d
0x140005ccd  lea     r14, WPP_GLOBAL_Control
0x140005cd4  mov     ebx, eax
0x140005cd6  test    eax, eax
0x140005cd8  jz      short loc_140005D06
0x140005cda  mov     rcx, cs:WPP_GLOBAL_Control
0x140005ce1  cmp     rcx, r14
0x140005ce4  jz      short loc_140005D02
0x140005ce6  test    [rcx+1Ch], sil
0x140005cea  jz      short loc_140005D02
0x140005cec  mov     rcx, [rcx+10h]
0x140005cf0  lea     edx, [rsi+9]
0x140005cf3  mov     r9d, eax
0x140005cf6  lea     r8, WPP_4a3c47521d24325c792b44adb038f8ce_Traceguids
0x140005cfd  call    WPP_SF_d
0x140005d02  test    ebx, ebx
0x140005d04  js      short loc_140005D36
0x140005d06  mov     [rsp+0C0h+pReserved3], r15; pReserved3
0x140005d0b  xor     r9d, r9d; pReserved1
0x140005d0e  mov     [rsp+0C0h+dwCapabilities], r15d; dwCapabilities
0x140005d13  xor     r8d, r8d; asAuthSvc
0x140005d16  mov     [rsp+0C0h+pAuthList], r15; pAuthList
0x140005d1b  or      edx, 0FFFFFFFFh; cAuthSvc
0x140005d1e  mov     [rsp+0C0h+dwImpLevel], 3; dwImpLevel
0x140005d26  xor     ecx, ecx; pSecDesc
0x140005d28  mov     [rsp+0C0h+dwAuthnLevel], 2; dwAuthnLevel
0x140005d30  call    cs:__imp_CoInitializeSecurity
0x140005d36  lea     rbx, off_14000B000
0x140005d3d  mov     cs:dword_14000B3A4, 1388h
0x140005d47  mov     cs:dword_14000B3A8, 3E8h
0x140005d51  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140005d55  jz      short loc_140005D7C
0x140005d57  cmp     cs:off_14000B000, r15
0x140005d5e  mov     cs:qword_14000B378, rbx
0x140005d65  jz      short loc_140005D7C
0x140005d67  mov     rax, [rbx+40h]
0x140005d6b  mov     cl, sil
0x140005d6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005d73  lea     rbx, [rbx+48h]
0x140005d77  cmp     [rbx], r15
0x140005d7a  jnz     short loc_140005D67
0x140005d7c  mov     rbx, cs:off_14000B0B0
0x140005d83  mov     rax, cs:off_14000B0B8
0x140005d8a  jmp     short loc_140005DAB
0x140005d8c  mov     rdx, [rbx]
0x140005d8f  test    rdx, rdx
0x140005d92  jz      short loc_140005DA7
0x140005d94  mov     rax, [rdx+40h]
0x140005d98  mov     cl, sil
0x140005d9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005da0  mov     rax, cs:off_14000B0B8
0x140005da7  add     rbx, 8
0x140005dab  cmp     rbx, rax
0x140005dae  jb      short loc_140005D8C
0x140005db0  call    cs:__imp_GetCurrentThreadId
0x140005db6  mov     ecx, 18h; Size
0x140005dbb  mov     cs:qword_14000B388, r15
0x140005dc2  mov     cs:dword_14000B380, eax
0x140005dc8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140005dcd  test    rax, rax
0x140005dd0  jz      short loc_140005DDF
0x140005dd2  mov     [rax], r15
0x140005dd5  mov     [rax+8], r15
0x140005dd9  mov     [rax+10h], r15d
0x140005ddd  jmp     short loc_140005DE2
0x140005ddf  mov     rax, r15
0x140005de2  mov     cs:qword_14000B388, rax
0x140005de9  test    rax, rax
0x140005dec  jz      short loc_140005DF5
0x140005dee  mov     cs:Block, r15
0x140005df5  mov     eax, dword ptr cs:asc_140008E80; "-/"
0x140005dfb  mov     rcx, rdi
0x140005dfe  mov     dword ptr [rbp+57h+var_40], eax
0x140005e01  movzx   eax, word ptr cs:asc_140008E80+4; ""
0x140005e08  mov     word ptr [rbp+57h+var_40+4], ax
0x140005e0c  jmp     short loc_140005E41
0x140005e0e  lea     rdx, aUnregserver; "UnregServer"
0x140005e15  mov     rcx, rbx
0x140005e18  call    cs:__imp__o__wcsicmp
0x140005e1e  test    eax, eax
0x140005e20  jz      loc_140005F3F
0x140005e26  lea     rdx, aRegserver; "RegServer"
0x140005e2d  mov     rcx, rbx
0x140005e30  call    cs:__imp__o__wcsicmp
0x140005e36  test    eax, eax
0x140005e38  jz      loc_140005F29
0x140005e3e  mov     rcx, rbx; lpsz
0x140005e41  lea     rdx, [rbp+57h+var_40]; LPCWSTR
0x140005e45  call    MyFindOneOf
0x140005e4a  mov     rbx, rax
0x140005e4d  test    rax, rax
0x140005e50  jnz     short loc_140005E0E
0x140005e52  xor     r9d, r9d; lpName
0x140005e55  xor     r8d, r8d; bInitialState
0x140005e58  xor     edx, edx; bManualReset
0x140005e5a  xor     ecx, ecx; lpEventAttributes
0x140005e5c  call    cs:__imp_CreateEventW
0x140005e62  mov     cs:hObject, rax
0x140005e69  test    rax, rax
0x140005e6c  jz      short loc_140005EA6
0x140005e6e  lea     rax, [rbp+57h+var_40]
0x140005e72  mov     dword ptr [rbp+57h+var_40], r15d
0x140005e76  mov     qword ptr [rsp+0C0h+dwImpLevel], rax
0x140005e7b  lea     r9, ?_Module@@3VCServerAppModule@WTL@@A; WTL::CServerAppModule _Module
0x140005e82  lea     r8, ?MonitorProc@CServerAppModule@WTL@@SAKPEAX@Z; WTL::CServerAppModule::MonitorProc(void *)
0x140005e89  mov     [rsp+0C0h+dwAuthnLevel], r15d
0x140005e8e  xor     edx, edx
0x140005e90  xor     ecx, ecx
0x140005e92  call    cs:__imp__o__beginthreadex
0x140005e98  test    rax, rax
0x140005e9b  jz      short loc_140005EA6
0x140005e9d  mov     rcx, rax; hObject
0x140005ea0  call    cs:__imp_CloseHandle
0x140005ea6  mov     r8d, 4; unsigned int
0x140005eac  call    ?RegisterClassObjects@CComModule@ATL@@QEAAJKK@Z; ATL::CComModule::RegisterClassObjects(ulong,ulong)
0x140005eb1  test    eax, eax
0x140005eb3  jz      short loc_140005EDF
0x140005eb5  mov     rcx, cs:WPP_GLOBAL_Control
0x140005ebc  cmp     rcx, r14
0x140005ebf  jz      short loc_140005EDF
0x140005ec1  test    [rcx+1Ch], sil
0x140005ec5  jz      short loc_140005EDF
0x140005ec7  mov     rcx, [rcx+10h]
0x140005ecb  lea     r8, WPP_4a3c47521d24325c792b44adb038f8ce_Traceguids
0x140005ed2  mov     edx, 0Bh
0x140005ed7  mov     r9d, eax
0x140005eda  call    WPP_SF_d
0x140005edf  call    cs:__imp_CoResumeClassObjects
0x140005ee5  mov     edi, eax
0x140005ee7  test    eax, eax
0x140005ee9  jz      short loc_140005F15
0x140005eeb  mov     rcx, cs:WPP_GLOBAL_Control
0x140005ef2  cmp     rcx, r14
0x140005ef5  jz      short loc_140005F15
0x140005ef7  test    [rcx+1Ch], sil
0x140005efb  jz      short loc_140005F15
0x140005efd  mov     rcx, [rcx+10h]
0x140005f01  lea     r8, WPP_4a3c47521d24325c792b44adb038f8ce_Traceguids
0x140005f08  mov     edx, 0Ch
0x140005f0d  mov     r9d, eax
0x140005f10  call    WPP_SF_d
0x140005f15  xorps   xmm0, xmm0
0x140005f18  movups  xmmword ptr [rbp+57h+Msg.hwnd], xmm0
0x140005f1c  movups  xmmword ptr [rbp+57h+Msg.wParam], xmm0
0x140005f20  movups  xmmword ptr [rbp+57h+Msg.time], xmm0
0x140005f24  jmp     loc_140005FCC
0x140005f29  call    ?MyRegisterAppId@@YAJPEBG@Z; MyRegisterAppId(ushort const *)
0x140005f2e  mov     edi, eax
0x140005f30  test    eax, eax
0x140005f32  js      loc_14000608F
0x140005f38  call    ?RegisterServer@CComModule@ATL@@QEAAJHPEBU_GUID@@@Z; ATL::CComModule::RegisterServer(int,_GUID const *)
0x140005f3d  jmp     short loc_140005FBB
0x140005f3f  call    ?MyUnregisterAppId@@YAJPEBG@Z; MyUnregisterAppId(ushort const *)
0x140005f44  mov     edi, eax
0x140005f46  test    eax, eax
0x140005f48  js      loc_14000608F
0x140005f4e  mov     rbx, cs:qword_14000B378
0x140005f55  test    rbx, rbx
0x140005f58  jz      short loc_140005F9B
0x140005f5a  jmp     short loc_140005F96
0x140005f5c  mov     rax, [rbx+38h]
0x140005f60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005f65  mov     rcx, [rbx]; rguid
0x140005f68  xor     r8d, r8d; int
0x140005f6b  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x140005f6e  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x140005f73  mov     edi, eax
0x140005f75  test    eax, eax
0x140005f77  js      loc_14000608F
0x140005f7d  mov     rax, [rbx+8]
0x140005f81  xor     ecx, ecx
0x140005f83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005f88  mov     edi, eax
0x140005f8a  test    eax, eax
0x140005f8c  js      loc_14000608F
0x140005f92  add     rbx, 48h ; 'H'
0x140005f96  cmp     [rbx], r15
0x140005f99  jnz     short loc_140005F5C
0x140005f9b  mov     rax, cs:?_pPerfUnRegFunc@ATL@@3P6AJXZEA; long (*ATL::_pPerfUnRegFunc)(void)
0x140005fa2  test    rax, rax
0x140005fa5  jz      short loc_140005FB6
0x140005fa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005fac  mov     edi, eax
0x140005fae  test    eax, eax
0x140005fb0  js      loc_14000608F
0x140005fb6  call    ?UnregisterServer@CAtlComModule@ATL@@QEAAJHPEBU_GUID@@@Z; ATL::CAtlComModule::UnregisterServer(int,_GUID const *)
0x140005fbb  mov     edi, eax
0x140005fbd  jmp     loc_14000608F
0x140005fc2  lea     rcx, [rbp+57h+Msg]; lpMsg
0x140005fc6  call    cs:__imp_DispatchMessageW
0x140005fcc  xor     r9d, r9d; wMsgFilterMax
0x140005fcf  lea     rcx, [rbp+57h+Msg]; lpMsg
0x140005fd3  xor     r8d, r8d; wMsgFilterMin
0x140005fd6  xor     edx, edx; hWnd
0x140005fd8  call    cs:__imp_GetMessageW
0x140005fde  test    eax, eax
0x140005fe0  jnz     short loc_140005FC2
0x140005fe2  mov     rbx, cs:qword_14000B378
0x140005fe9  test    rbx, rbx
0x140005fec  jz      short loc_140006019
0x140005fee  mov     eax, r15d
0x140005ff1  cmp     [rbx], r15
0x140005ff4  jz      short loc_140006019
0x140005ff6  test    eax, eax
0x140005ff8  jnz     short loc_14000605C
0x140005ffa  mov     ecx, [rbx+28h]; dwRegister
0x140005ffd  test    ecx, ecx
0x140005fff  jnz     short loc_140006006
0x140006001  mov     eax, r15d
0x140006004  jmp     short loc_14000600C
0x140006006  call    cs:__imp_CoRevokeClassObject
0x14000600c  add     rbx, 48h ; 'H'
0x140006010  cmp     [rbx], r15
0x140006013  jnz     short loc_140005FF6
0x140006015  test    eax, eax
0x140006017  jnz     short loc_14000605C
0x140006019  mov     rbx, cs:off_14000B0B0
0x140006020  mov     eax, r15d
0x140006023  mov     rcx, cs:off_14000B0B8
0x14000602a  jmp     short loc_140006057
0x14000602c  test    eax, eax
0x14000602e  jnz     short loc_14000605C
0x140006030  mov     rdx, [rbx]
0x140006033  test    rdx, rdx
0x140006036  jz      short loc_140006053
0x140006038  cmp     [rdx+28h], r15d
0x14000603c  jnz     short loc_140006043
0x14000603e  mov     eax, r15d
0x140006041  jmp     short loc_140006053
0x140006043  mov     ecx, [rdx+28h]; dwRegister
0x140006046  call    cs:__imp_CoRevokeClassObject
0x14000604c  mov     rcx, cs:off_14000B0B8
0x140006053  add     rbx, 8
0x140006057  cmp     rbx, rcx
0x14000605a  jb      short loc_14000602C
0x14000605c  mov     rcx, cs:?s_hEventShutdown@CContainer@@0PEAXEA; hEvent
0x140006063  call    cs:__imp_SetEvent
0x140006069  mov     rcx, cs:?s_hThreadShutdown@CContainer@@0PEAXEA; hHandle
0x140006070  mov     edx, 1F4h; dwMilliseconds
0x140006075  call    cs:__imp_WaitForSingleObject
0x14000607b  mov     rcx, cs:?s_hThreadShutdown@CContainer@@0PEAXEA; hObject
0x140006082  call    cs:__imp_CloseHandle
0x140006088  mov     cs:?s_hThreadShutdown@CContainer@@0PEAXEA, r15; void * CContainer::s_hThreadShutdown
0x14000608f  mov     rcx, cs:hObject; hObject
0x140006096  test    rcx, rcx
0x140006099  jz      short loc_1400060AC
0x14000609b  call    cs:__imp_CloseHandle
0x1400060a1  test    eax, eax
0x1400060a3  jz      short loc_1400060AC
0x1400060a5  mov     cs:hObject, r15
0x1400060ac  mov     r14, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1400060b3  lea     rcx, [r14+18h]; lpCriticalSection
0x1400060b7  call    cs:__imp_EnterCriticalSection
0x1400060bd  mov     rbx, cs:Block
0x1400060c4  test    rbx, rbx
0x1400060c7  jz      short loc_140006109
0x1400060c9  cmp     [rbx+8], r15d
0x1400060cd  jle     short loc_1400060E2
0x1400060cf  mov     rcx, [rbx]
0x1400060d2  mov     rcx, [rcx]; hWnd
0x1400060d5  call    cs:__imp_DestroyWindow
0x1400060db  mov     rbx, cs:Block
0x1400060e2  test    rbx, rbx
0x1400060e5  jz      short loc_140006109
0x1400060e7  mov     rcx, [rbx]; Block
0x1400060ea  test    rcx, rcx
0x1400060ed  jz      short loc_1400060F8
0x1400060ef  call    cs:__imp_free
0x1400060f5  mov     [rbx], r15
0x1400060f8  mov     edx, 10h
0x1400060fd  mov     [rbx+8], r15
0x140006101  mov     rcx, rbx; Block
0x140006104  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140006109  lea     rcx, [r14+18h]; lpCriticalSection
0x14000610d  mov     cs:Block, r15
0x140006114  call    cs:__imp_LeaveCriticalSection
0x14000611a  mov     rbx, cs:qword_14000B388
0x140006121  test    rbx, rbx
  ... truncated ...
```
