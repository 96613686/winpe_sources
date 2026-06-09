# InitWudfDriverManager(void)

- ea: `0x14008868c`
- end: `0x140088934`
- name: `?InitWudfDriverManager@@YAKXZ`
- size: `680`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, service_task`

## callers

- `0x1400848e0`

## callees

- `0x140001988`
- `0x140004c58`
- `0x14001f99c`
- `0x140036fd4`
- `0x1400425b8`
- `0x140051360`
- `0x14008868c`
- `0x14008893c`
- `0x140088974`
- `0x1400899d0`
- `0x140089ea8`
- `0x14008b4d8`
- `0x14008b52c`
- `0x140091f24`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400887bc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400887bc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14008891c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14008891c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140088764`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400887c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140088764`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400887c7`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x1400886cd`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x1400886cd`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x140088756`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x140088756`

## string_xrefs

- `0x14008874d`: `WudfPlatform.dll`

## pseudocode

```c
__int64 InitWudfDriverManager(void)
{
  PRPC_ASYNC_STATE v0; // rcx
  __int64 v1; // rdx
  unsigned int LastError; // ebx
  int v3; // esi
  HMODULE LibraryW; // rax
  HMODULE v5; // rdi
  PRPC_ASYNC_STATE v6; // rcx
  __int64 v7; // rdx
  const struct std::nothrow_t *v8; // rdx
  WdfDriverManager *v9; // rax
  WdfDriverManager *v10; // rcx
  PRPC_ASYNC_STATE v11; // rcx
  __int64 v12; // rdx
  const WCHAR *v14; // [rsp+30h] [rbp+8h] BYREF

  v14 = 0;
  if ( !wcsncmp(L"wudfsvc", L"-ProcMgmtName:", 0xEu) )
    v14 = L"atform.dll";
  if ( !(unsigned int)RtlGetCurrentServiceSessionId() )
  {
    if ( (unsigned int)IsRunningWinPE() && !(unsigned int)IsUMDFEnabledInWinPEMode() )
    {
      v0 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
        || (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 1) == 0
        || *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) < 2u )
      {
        return 50;
      }
      v1 = 11;
      goto LABEL_8;
    }
    v3 = 0;
    LibraryW = LoadLibraryW(L"WudfPlatform.dll");
    v5 = LibraryW;
    if ( !LibraryW )
    {
      LastError = GetLastError();
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
        && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 1) != 0
        && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 2u )
      {
        v7 = 12;
LABEL_21:
        WPP_SF_d(v6->u.APC.hThread, v7, WPP_83606e3015453ddf14f71b0fb23de8dd_Traceguids, LastError);
        goto LABEL_32;
      }
      goto LABEL_32;
    }
    if ( !GetProcAddress(LibraryW, "GetAndInitializePlatformObject") )
    {
      LastError = GetLastError();
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
        && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 1) != 0
        && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 2u )
      {
        v7 = 13;
        goto LABEL_21;
      }
LABEL_32:
      if ( !LastError || !v3 )
      {
LABEL_50:
        if ( !v5 )
          return LastError;
LABEL_51:
        FreeLibrary(v5);
        return LastError;
      }
LABEL_49:
      TraceLoggingUnregister_EventUnregister(&dword_1400BA378);
      McGenEventUnregister_EventUnregister();
      goto LABEL_50;
    }
    McGenEventRegister_EventRegister();
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_1400BA378);
    LastError = WdfDriverManager::InitializePlatformLibrary();
    if ( (LastError & 0x80000000) != 0 )
    {
      v3 = 1;
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
        && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 1) != 0
        && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 2u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->u.APC.hThread, 14, WPP_83606e3015453ddf14f71b0fb23de8dd_Traceguids, LastError);
      }
      goto LABEL_32;
    }
    v9 = (WdfDriverManager *)operator new(0x168u, v8);
    if ( v9 )
    {
      DrvMgrExt = WdfDriverManager::WdfDriverManager(v9);
      if ( DrvMgrExt )
      {
        LastError = WdfDriverManager::Initialize(v10, (struct DrvMgrCmdLineArguments *)&v14);
        if ( !LastError )
        {
          LastError = 0;
          goto LABEL_51;
        }
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          || (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 1) == 0
          || *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) < 2u )
        {
          goto LABEL_49;
        }
        v12 = 16;
LABEL_48:
        WPP_SF_d(v11->u.APC.hThread, v12, WPP_83606e3015453ddf14f71b0fb23de8dd_Traceguids, LastError);
        goto LABEL_49;
      }
    }
    else
    {
      DrvMgrExt = 0;
    }
    LastError = 14;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
      || (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 1) == 0
      || *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) < 2u )
    {
      goto LABEL_49;
    }
    v12 = 15;
    goto LABEL_48;
  }
  v0 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
    || (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 1) == 0
    || *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) < 2u )
  {
    return 50;
  }
  v1 = 10;
LABEL_8:
  WPP_SF_(v0->u.APC.hThread, v1, WPP_83606e3015453ddf14f71b0fb23de8dd_Traceguids);
  return 50;
}

```

## disassembly

```asm
0x14008868c  mov     [rsp+arg_8], rbx
0x140088691  mov     [rsp+arg_10], rsi
0x140088696  push    rdi
0x140088697  sub     rsp, 20h
0x14008869b  mov     r8d, 0Eh; MaxCount
0x1400886a1  mov     [rsp+28h+arg_0], 0
0x1400886aa  lea     rdx, aProcmgmtname; "-ProcMgmtName:"
0x1400886b1  lea     rcx, aWudfsvc; "wudfsvc"
0x1400886b8  call    wcsncmp
0x1400886bd  test    eax, eax
0x1400886bf  jnz     short loc_1400886CD
0x1400886c1  lea     rax, aWudfplatformDl_0+0Ch; "atform.dll"
0x1400886c8  mov     [rsp+28h+arg_0], rax
0x1400886cd  call    cs:__imp_RtlGetCurrentServiceSessionId
0x1400886d3  test    eax, eax
0x1400886d5  jz      short loc_140088715
0x1400886d7  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400886de  lea     rax, WPP_GLOBAL_Control
0x1400886e5  cmp     rcx, rax
0x1400886e8  jz      short loc_14008870B
0x1400886ea  test    byte ptr [rcx+44h], 1
0x1400886ee  jz      short loc_14008870B
0x1400886f0  cmp     byte ptr [rcx+41h], 2
0x1400886f4  jb      short loc_14008870B
0x1400886f6  mov     edx, 0Ah
0x1400886fb  mov     rcx, [rcx+38h]
0x1400886ff  lea     r8, WPP_83606e3015453ddf14f71b0fb23de8dd_Traceguids
0x140088706  call    WPP_SF_
0x14008870b  mov     ebx, 32h ; '2'
0x140088710  jmp     loc_140088922
0x140088715  call    IsRunningWinPE
0x14008871a  test    eax, eax
0x14008871c  jz      short loc_14008874D
0x14008871e  call    IsUMDFEnabledInWinPEMode
0x140088723  test    eax, eax
0x140088725  jnz     short loc_14008874D
0x140088727  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008872e  lea     rax, WPP_GLOBAL_Control
0x140088735  cmp     rcx, rax
0x140088738  jz      short loc_14008870B
0x14008873a  test    byte ptr [rcx+44h], 1
0x14008873e  jz      short loc_14008870B
0x140088740  cmp     byte ptr [rcx+41h], 2
0x140088744  jb      short loc_14008870B
0x140088746  mov     edx, 0Bh
0x14008874b  jmp     short loc_1400886FB
0x14008874d  lea     rcx, aWudfplatformDl_0; "WudfPlatform.dll"
0x140088754  xor     esi, esi
0x140088756  call    cs:__imp_LoadLibraryW
0x14008875c  mov     rdi, rax
0x14008875f  test    rax, rax
0x140088762  jnz     short loc_1400887B2
0x140088764  call    cs:__imp_GetLastError
0x14008876a  mov     ebx, eax
0x14008876c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140088773  lea     rax, WPP_GLOBAL_Control
0x14008877a  cmp     rcx, rax
0x14008877d  jz      loc_140088850
0x140088783  test    byte ptr [rcx+44h], 1
0x140088787  jz      loc_140088850
0x14008878d  cmp     byte ptr [rcx+41h], 2
0x140088791  jb      loc_140088850
0x140088797  lea     edx, [rsi+0Ch]
0x14008879a  mov     rcx, [rcx+38h]
0x14008879e  lea     r8, WPP_83606e3015453ddf14f71b0fb23de8dd_Traceguids
0x1400887a5  mov     r9d, ebx
0x1400887a8  call    WPP_SF_d
0x1400887ad  jmp     loc_140088850
0x1400887b2  lea     rdx, aGetandinitiali_0; "GetAndInitializePlatformObject"
0x1400887b9  mov     rcx, rdi; hModule
0x1400887bc  call    cs:__imp_GetProcAddress
0x1400887c2  test    rax, rax
0x1400887c5  jnz     short loc_1400887F5
0x1400887c7  call    cs:__imp_GetLastError
0x1400887cd  mov     ebx, eax
0x1400887cf  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400887d6  lea     rax, WPP_GLOBAL_Control
0x1400887dd  cmp     rcx, rax
0x1400887e0  jz      short loc_140088850
0x1400887e2  test    byte ptr [rcx+44h], 1
0x1400887e6  jz      short loc_140088850
0x1400887e8  cmp     byte ptr [rcx+41h], 2
0x1400887ec  jb      short loc_140088850
0x1400887ee  mov     edx, 0Dh
0x1400887f3  jmp     short loc_14008879A
0x1400887f5  call    McGenEventRegister_EventRegister
0x1400887fa  xor     r8d, r8d
0x1400887fd  lea     rcx, dword_1400BA378; CallbackContext
0x140088804  xor     edx, edx
0x140088806  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x14008880b  call    ?InitializePlatformLibrary@WdfDriverManager@@SAJXZ; WdfDriverManager::InitializePlatformLibrary(void)
0x140088810  mov     ebx, eax
0x140088812  test    eax, eax
0x140088814  jns     short loc_140088865
0x140088816  mov     esi, 1
0x14008881b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140088822  lea     rax, WPP_GLOBAL_Control
0x140088829  cmp     rcx, rax
0x14008882c  jz      short loc_140088850
0x14008882e  test    [rcx+44h], sil
0x140088832  jz      short loc_140088850
0x140088834  cmp     byte ptr [rcx+41h], 2
0x140088838  jb      short loc_140088850
0x14008883a  mov     rcx, [rcx+38h]
0x14008883e  lea     edx, [rsi+0Dh]
0x140088841  mov     r9d, ebx
0x140088844  lea     r8, WPP_83606e3015453ddf14f71b0fb23de8dd_Traceguids
0x14008884b  call    WPP_SF_d
0x140088850  test    ebx, ebx
0x140088852  jz      loc_140088914
0x140088858  test    esi, esi
0x14008885a  jz      loc_140088914
0x140088860  jmp     loc_140088903
0x140088865  mov     ecx, 168h; Size
0x14008886a  call    ??2@YAPEAX_KK0@Z; operator new(unsigned __int64,ulong,unsigned __int64)
0x14008886f  test    rax, rax
0x140088872  jz      short loc_1400888C2
0x140088874  mov     rcx, rax; this
0x140088877  call    ??0WdfDriverManager@@QEAA@XZ; WdfDriverManager::WdfDriverManager(void)
0x14008887c  mov     cs:?DrvMgrExt@@3PEAVWdfDriverManager@@EA, rax; WdfDriverManager * DrvMgrExt
0x140088883  test    rax, rax
0x140088886  jz      short loc_1400888C9
0x140088888  lea     rdx, [rsp+28h+arg_0]; struct DrvMgrCmdLineArguments *
0x14008888d  call    ?Initialize@WdfDriverManager@@QEAAKPEAVDrvMgrCmdLineArguments@@@Z; WdfDriverManager::Initialize(DrvMgrCmdLineArguments *)
0x140088892  mov     ebx, eax
0x140088894  test    eax, eax
0x140088896  jz      short loc_1400888BE
0x140088898  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008889f  lea     rax, WPP_GLOBAL_Control
0x1400888a6  cmp     rcx, rax
0x1400888a9  jz      short loc_140088903
0x1400888ab  test    byte ptr [rcx+44h], 1
0x1400888af  jz      short loc_140088903
0x1400888b1  cmp     byte ptr [rcx+41h], 2
0x1400888b5  jb      short loc_140088903
0x1400888b7  mov     edx, 10h
0x1400888bc  jmp     short loc_1400888F0
0x1400888be  xor     ebx, ebx
0x1400888c0  jmp     short loc_140088919
0x1400888c2  mov     cs:?DrvMgrExt@@3PEAVWdfDriverManager@@EA, rsi; WdfDriverManager * DrvMgrExt
0x1400888c9  mov     ebx, 0Eh
0x1400888ce  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400888d5  lea     rax, WPP_GLOBAL_Control
0x1400888dc  cmp     rcx, rax
0x1400888df  jz      short loc_140088903
0x1400888e1  test    byte ptr [rcx+44h], 1
0x1400888e5  jz      short loc_140088903
0x1400888e7  cmp     byte ptr [rcx+41h], 2
0x1400888eb  jb      short loc_140088903
0x1400888ed  lea     edx, [rbx+1]
0x1400888f0  mov     rcx, [rcx+38h]
0x1400888f4  lea     r8, WPP_83606e3015453ddf14f71b0fb23de8dd_Traceguids
0x1400888fb  mov     r9d, ebx
0x1400888fe  call    WPP_SF_d
0x140088903  lea     rcx, dword_1400BA378
0x14008890a  call    TraceLoggingUnregister_EventUnregister
0x14008890f  call    McGenEventUnregister_EventUnregister
0x140088914  test    rdi, rdi
0x140088917  jz      short loc_140088922
0x140088919  mov     rcx, rdi; hLibModule
0x14008891c  call    cs:__imp_FreeLibrary
0x140088922  mov     rsi, [rsp+28h+arg_10]
0x140088927  mov     eax, ebx
0x140088929  mov     rbx, [rsp+28h+arg_8]
0x14008892e  add     rsp, 20h
0x140088932  pop     rdi
0x140088933  retn
```
