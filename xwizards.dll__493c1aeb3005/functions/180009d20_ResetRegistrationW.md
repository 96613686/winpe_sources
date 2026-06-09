# ResetRegistrationW

- ea: `0x180009d20`
- end: `0x18000a2c5`
- name: `ResetRegistrationW`
- size: `1445`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180009c70`

## callees

- `0x180004370`
- `0x1800085a8`
- `0x180008634`
- `0x180008fd0`
- `0x180009d20`
- `0x18000ae04`
- `0x18000ae90`
- `0x18000bf70`
- `0x18001516c`
- `0x180032a02`
- `0x180032a30`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18000a1d8`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18000a1d8`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180009fbb`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180009fbb`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180009f6f`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180009f6f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000a0c5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000a0c5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009e6c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009e6c`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180009e1c`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180009e1c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000a234`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000a234`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18000a0b3`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18000a0b3`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18000a0df`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18000a0df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a16f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a17a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a16f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a17a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a26d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a26d`
- `api-ms-win-shcore-obsolete-l1-1-0!CommandLineToArgvW` at `0x180009d68`
- `api-ms-win-shcore-obsolete-l1-1-0!CommandLineToArgvW` at `0x180009d68`
- `USER32!SetProcessDPIAware` at `0x180009dbb`
- `USER32!SetProcessDPIAware` at `0x180009dbb`

## string_xrefs

- `0x180009f61`: `*.xml`

## pseudocode

```c
__int64 __fastcall ResetRegistrationW(__int64 a1, __int64 a2, const WCHAR *a3)
{
  _QWORD *v4; // rbx
  unsigned int LastErrorHRESULT; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  int v8; // r15d
  const wchar_t *v9; // rsi
  unsigned int v10; // r12d
  int v11; // ecx
  _WORD *v12; // rdx
  HRESULT v13; // eax
  HRESULT v14; // r13d
  HRESULT Instance; // eax
  int v16; // eax
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // r9
  int v20; // eax
  HANDLE FirstFileW; // rsi
  __int64 v22; // r15
  DWORD FullPathNameW; // eax
  unsigned int v24; // r11d
  unsigned int v25; // eax
  _QWORD *v26; // rcx
  int v27; // edx
  int v28; // eax
  int pNumArgs; // [rsp+50h] [rbp-B0h] BYREF
  struct IXWizard *ppv; // [rsp+58h] [rbp-A8h] BYREF
  DWORD ExitCode[2]; // [rsp+60h] [rbp-A0h] BYREF
  HRESULT v33; // [rsp+68h] [rbp-98h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+70h] [rbp-90h] BYREF
  LPWSTR FilePart; // [rsp+88h] [rbp-78h] BYREF
  HLOCAL hMem; // [rsp+90h] [rbp-70h]
  struct _STARTUPINFOW StartupInfo; // [rsp+A0h] [rbp-60h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+110h] [rbp+10h] BYREF
  WCHAR CommandLine[296]; // [rsp+360h] [rbp+260h] BYREF
  WCHAR Buffer[264]; // [rsp+5B0h] [rbp+4B0h] BYREF

  *(_QWORD *)ExitCode = a1;
  pNumArgs = 0;
  hMem = CommandLineToArgvW(a3, &pNumArgs);
  v4 = hMem;
  if ( !hMem )
  {
    LastErrorHRESULT = GetLastErrorHRESULT();
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v7 = 32;
LABEL_72:
      WPP_SF_d(v6[2], v7, WPP_68058977b0c233f043f68faaec20b8c5_Traceguids, LastErrorHRESULT);
      return LastErrorHRESULT;
    }
    return LastErrorHRESULT;
  }
  v8 = 0;
  v9 = 0;
  v10 = 0;
  SetProcessDPIAware();
  v11 = pNumArgs;
  while ( v11 )
  {
    while ( 1 )
    {
      pNumArgs = --v11;
      v12 = (_WORD *)v4[v11];
      if ( ((*v12 - 45) & 0xFFFD) == 0 )
        break;
      if ( !v11 )
        goto LABEL_14;
      v9 = (const wchar_t *)v4[v11];
    }
    if ( v12[1] == 99 )
    {
      v8 = 1;
    }
    else if ( v12[1] == 109 )
    {
      v10 |= 0x10000u;
    }
  }
LABEL_14:
  pNumArgs = v11 - 1;
  v13 = CoInitializeEx(0, 6u);
  LastErrorHRESULT = 0;
  v33 = v13;
  v14 = v13;
  if ( v13 != -2147417850 )
    LastErrorHRESULT = v13;
  if ( (LastErrorHRESULT & 0x80000000) == 0 )
  {
    ppv = 0;
    Instance = CoCreateInstance(&CLSID_CXWizard, 0, 0x401u, &IID_IXWizard, (LPVOID *)&ppv);
    LastErrorHRESULT = Instance;
    if ( Instance < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          39,
          WPP_68058977b0c233f043f68faaec20b8c5_Traceguids,
          (unsigned int)Instance);
      goto LABEL_64;
    }
    LastErrorHRESULT = (*(__int64 (__fastcall **)(struct IXWizard *, __int64, __int64))(*(_QWORD *)ppv + 216LL))(
                         ppv,
                         1,
                         a1);
    if ( (LastErrorHRESULT & 0x80000000) != 0 )
      goto LABEL_60;
    v16 = HrRemoveAllXWizardComponentsFromRegistry(0, 2, (__int64 *)ppv);
    LastErrorHRESULT = v16;
    if ( v16 < 0 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v18 = 33;
        v19 = (unsigned int)v16;
LABEL_27:
        WPP_SF_d(v17[2], v18, WPP_68058977b0c233f043f68faaec20b8c5_Traceguids, v19);
        goto LABEL_60;
      }
      goto LABEL_60;
    }
    v20 = HrForceRemoveAllWizardComponents(ppv);
    LastErrorHRESULT = v20;
    if ( v20 < 0 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v18 = 34;
        v19 = (unsigned int)v20;
        goto LABEL_27;
      }
      goto LABEL_60;
    }
    if ( v8 )
      goto LABEL_60;
    for ( ; v9; ++v9 )
    {
      if ( *v9 != 32 )
        break;
    }
    memset_0(&FindFileData, 0, sizeof(FindFileData));
    if ( !v9 || !*v9 )
      v9 = L"*.xml";
    FirstFileW = FindFirstFileW(v9, &FindFileData);
    if ( FirstFileW == (HANDLE)-1LL )
    {
LABEL_60:
      (*(void (__fastcall **)(struct IXWizard *))(*(_QWORD *)ppv + 16LL))(ppv);
LABEL_64:
      if ( v14 != -2147417850 )
        CoUninitialize();
      goto LABEL_69;
    }
    v22 = *(_QWORD *)ExitCode;
    while ( 1 )
    {
      FilePart = 0;
      LastErrorHRESULT = 1;
      memset_0(Buffer, 0, 0x20Au);
      FullPathNameW = GetFullPathNameW(FindFileData.cFileName, 0x105u, Buffer, &FilePart);
      if ( FullPathNameW )
      {
        if ( FullPathNameW < 0x105 )
          break;
      }
LABEL_58:
      if ( !FindNextFileW(FirstFileW, &FindFileData) )
      {
        v14 = v33;
        goto LABEL_60;
      }
    }
    CommandLine[0] = 0;
    StringCchCopyW(CommandLine, 0x121u, L"findstr.exe");
    StringCchCatW(CommandLine, v24, L" ");
    StringCchCatW(CommandLine, 0x121u, L"xwizard.dtd");
    StringCchCatW(CommandLine, 0x121u, L" ");
    StringCchCatW(CommandLine, 0x121u, Buffer);
    memset_0(&StartupInfo.cb + 1, 0, 0x64u);
    StartupInfo.cb = 104;
    memset(&ProcessInformation, 0, sizeof(ProcessInformation));
    if ( CreateProcessW(0, CommandLine, 0, 0, 0, 0x8000000u, 0, 0, &StartupInfo, &ProcessInformation) )
    {
      if ( WaitForSingleObject(ProcessInformation.hProcess, 0xFFFFFFFF) == -1 )
      {
        v25 = GetLastErrorHRESULT();
        LastErrorHRESULT = v25;
        v26 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          v27 = 36;
          goto LABEL_52;
        }
      }
      else
      {
        ExitCode[0] = 0;
        if ( GetExitCodeProcess(ProcessInformation.hProcess, ExitCode) )
        {
          LastErrorHRESULT = ExitCode[0] != 0;
          goto LABEL_53;
        }
        v25 = GetLastErrorHRESULT();
        LastErrorHRESULT = v25;
        v26 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          v27 = 35;
LABEL_52:
          WPP_SF_SD(
            v26[2],
            v27,
            (unsigned int)WPP_68058977b0c233f043f68faaec20b8c5_Traceguids,
            (unsigned int)CommandLine,
            v25);
        }
      }
    }
    else
    {
      v25 = GetLastErrorHRESULT();
      LastErrorHRESULT = v25;
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v27 = 37;
        goto LABEL_52;
      }
    }
LABEL_53:
    CloseHandle(ProcessInformation.hProcess);
    CloseHandle(ProcessInformation.hThread);
    if ( !LastErrorHRESULT )
    {
      v28 = InternalProcessXMLFile(v22, FindFileData.cFileName, v10, 0, ppv);
      LastErrorHRESULT = v28;
      if ( v28 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          38,
          (unsigned int)WPP_68058977b0c233f043f68faaec20b8c5_Traceguids,
          (unsigned int)FindFileData.cFileName,
          v28);
    }
    goto LABEL_58;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_68058977b0c233f043f68faaec20b8c5_Traceguids, LastErrorHRESULT);
LABEL_69:
  LocalFree(hMem);
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v7 = 41;
    goto LABEL_72;
  }
  return LastErrorHRESULT;
}

```

## disassembly

```asm
0x180009d20  mov     [rsp-8+arg_8], rbx
0x180009d25  push    rbp
0x180009d26  push    rsi
0x180009d27  push    rdi
0x180009d28  push    r12
0x180009d2a  push    r13
0x180009d2c  push    r14
0x180009d2e  push    r15
0x180009d30  lea     rbp, [rsp-6D0h]
0x180009d38  sub     rsp, 7D0h
0x180009d3f  mov     rax, cs:__security_cookie
0x180009d46  xor     rax, rsp
0x180009d49  mov     [rbp+700h+var_40], rax
0x180009d50  mov     rdi, rcx
0x180009d53  mov     qword ptr [rsp+800h+ExitCode], rcx
0x180009d58  xor     r14d, r14d
0x180009d5b  lea     rdx, [rsp+800h+pNumArgs]; pNumArgs
0x180009d60  mov     rcx, r8; lpCmdLine
0x180009d63  mov     [rsp+800h+pNumArgs], r14d
0x180009d68  call    cs:__imp_CommandLineToArgvW
0x180009d6e  mov     [rbp+700h+hMem], rax
0x180009d72  mov     rbx, rax
0x180009d75  test    rax, rax
0x180009d78  jnz     short loc_180009DB2
0x180009d7a  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x180009d7f  mov     ebx, eax
0x180009d81  mov     rcx, cs:WPP_GLOBAL_Control
0x180009d88  lea     rdi, WPP_GLOBAL_Control
0x180009d8f  cmp     rcx, rdi
0x180009d92  jz      loc_18000A299
0x180009d98  test    byte ptr [rcx+1Ch], 4
0x180009d9c  jz      loc_18000A299
0x180009da2  lea     edx, [r14+20h]
0x180009da6  lea     r8, WPP_68058977b0c233f043f68faaec20b8c5_Traceguids
0x180009dad  jmp     loc_18000A28D
0x180009db2  mov     r15d, r14d
0x180009db5  mov     rsi, r14
0x180009db8  mov     r12d, r14d
0x180009dbb  call    cs:__imp_SetProcessDPIAware
0x180009dc1  mov     ecx, [rsp+800h+pNumArgs]
0x180009dc5  jmp     short loc_180009E0B
0x180009dc7  dec     ecx
0x180009dc9  mov     r8d, 0FFFDh
0x180009dcf  movsxd  rax, ecx
0x180009dd2  mov     [rsp+800h+pNumArgs], ecx
0x180009dd6  mov     rdx, [rbx+rax*8]
0x180009dda  movzx   eax, word ptr [rdx]
0x180009ddd  sub     ax, 2Dh ; '-'
0x180009de1  test    r8w, ax
0x180009de5  jz      short loc_180009DF0
0x180009de7  test    ecx, ecx
0x180009de9  jz      short loc_180009E0F
0x180009deb  mov     rsi, rdx
0x180009dee  jmp     short loc_180009DC7
0x180009df0  cmp     word ptr [rdx+2], 63h ; 'c'
0x180009df5  jz      short loc_180009E05
0x180009df7  cmp     word ptr [rdx+2], 6Dh ; 'm'
0x180009dfc  jnz     short loc_180009E0B
0x180009dfe  bts     r12d, 10h
0x180009e03  jmp     short loc_180009E0B
0x180009e05  mov     r15d, 1
0x180009e0b  test    ecx, ecx
0x180009e0d  jnz     short loc_180009DC7
0x180009e0f  dec     ecx
0x180009e11  mov     edx, 6; dwCoInit
0x180009e16  mov     [rsp+800h+pNumArgs], ecx
0x180009e1a  xor     ecx, ecx; pvReserved
0x180009e1c  call    cs:__imp_CoInitializeEx
0x180009e22  mov     ebx, r14d
0x180009e25  mov     [rsp+800h+var_798], eax
0x180009e29  cmp     eax, 80010106h
0x180009e2e  lea     r14, WPP_68058977b0c233f043f68faaec20b8c5_Traceguids
0x180009e35  mov     r13d, eax
0x180009e38  cmovnz  ebx, eax
0x180009e3b  test    ebx, ebx
0x180009e3d  js      loc_18000A23C
0x180009e43  lea     rax, [rsp+800h+var_7A8]
0x180009e48  mov     [rsp+800h+var_7A8], 0
0x180009e51  lea     r9, IID_IXWizard; riid
0x180009e58  mov     [rsp+800h+ppv], rax; ppv
0x180009e5d  xor     edx, edx; pUnkOuter
0x180009e5f  lea     rcx, CLSID_CXWizard; rclsid
0x180009e66  mov     r8d, 401h; dwClsContext
0x180009e6c  call    cs:__imp_CoCreateInstance
0x180009e72  mov     ebx, eax
0x180009e74  test    eax, eax
0x180009e76  js      loc_18000A1FE
0x180009e7c  mov     rcx, [rsp+800h+var_7A8]
0x180009e81  mov     r8, rdi
0x180009e84  mov     edx, 1
0x180009e89  mov     rax, [rcx]
0x180009e8c  mov     rax, [rax+0D8h]
0x180009e93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e98  lea     rdi, WPP_GLOBAL_Control
0x180009e9f  mov     ebx, eax
0x180009ea1  test    eax, eax
0x180009ea3  js      loc_18000A1EB
0x180009ea9  mov     r8, [rsp+800h+var_7A8]
0x180009eae  mov     edx, 2
0x180009eb3  xor     ecx, ecx
0x180009eb5  call    ?HrRemoveAllXWizardComponentsFromRegistry@@YAJHW4tagXW_XML_ONERROR_TYPE@@PEAUIXWizard@@@Z; HrRemoveAllXWizardComponentsFromRegistry(int,tagXW_XML_ONERROR_TYPE,IXWizard *)
0x180009eba  mov     ebx, eax
0x180009ebc  test    eax, eax
0x180009ebe  jns     short loc_180009EE4
0x180009ec0  mov     rcx, cs:WPP_GLOBAL_Control
0x180009ec7  cmp     rcx, rdi
0x180009eca  jz      loc_18000A1EB
0x180009ed0  test    byte ptr [rcx+1Ch], 4
0x180009ed4  jz      loc_18000A1EB
0x180009eda  mov     edx, 21h ; '!'
0x180009edf  mov     r9d, eax
0x180009ee2  jmp     short loc_180009F16
0x180009ee4  mov     rcx, [rsp+800h+var_7A8]; struct IXWizard *
0x180009ee9  call    ?HrForceRemoveAllWizardComponents@@YAJPEAUIXWizard@@@Z; HrForceRemoveAllWizardComponents(IXWizard *)
0x180009eee  mov     ebx, eax
0x180009ef0  test    eax, eax
0x180009ef2  jns     short loc_180009F27
0x180009ef4  mov     rcx, cs:WPP_GLOBAL_Control
0x180009efb  cmp     rcx, rdi
0x180009efe  jz      loc_18000A1EB
0x180009f04  test    byte ptr [rcx+1Ch], 4
0x180009f08  jz      loc_18000A1EB
0x180009f0e  mov     edx, 22h ; '"'
0x180009f13  mov     r9d, eax
0x180009f16  mov     rcx, [rcx+10h]
0x180009f1a  mov     r8, r14
0x180009f1d  call    WPP_SF_d
0x180009f22  jmp     loc_18000A1EB
0x180009f27  test    r15d, r15d
0x180009f2a  jnz     loc_18000A1EB
0x180009f30  test    rsi, rsi
0x180009f33  jz      short loc_180009F44
0x180009f35  lea     edx, [r15+20h]
0x180009f39  cmp     [rsi], dx
0x180009f3c  jnz     short loc_180009F44
0x180009f3e  add     rsi, 2
0x180009f42  jnz     short loc_180009F39
0x180009f44  xor     edx, edx; Val
0x180009f46  lea     rcx, [rbp+700h+FindFileData]; void *
0x180009f4a  mov     r8d, 250h; Size
0x180009f50  call    memset_0
0x180009f55  xor     eax, eax
0x180009f57  test    rsi, rsi
0x180009f5a  jz      short loc_180009F61
0x180009f5c  cmp     [rsi], ax
0x180009f5f  jnz     short loc_180009F68
0x180009f61  lea     rsi, aXml; "*.xml"
0x180009f68  lea     rdx, [rbp+700h+FindFileData]; lpFindFileData
0x180009f6c  mov     rcx, rsi; lpFileName
0x180009f6f  call    cs:__imp_FindFirstFileW
0x180009f75  mov     rsi, rax
0x180009f78  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180009f7c  jz      loc_18000A1EB
0x180009f82  mov     r15, qword ptr [rsp+800h+ExitCode]
0x180009f87  xor     r13d, r13d
0x180009f8a  xor     edx, edx; Val
0x180009f8c  mov     [rbp+700h+FilePart], r13
0x180009f90  mov     r8d, 20Ah; Size
0x180009f96  lea     rcx, [rbp+700h+Buffer]; void *
0x180009f9d  mov     ebx, 1
0x180009fa2  call    memset_0
0x180009fa7  lea     r9, [rbp+700h+FilePart]; lpFilePart
0x180009fab  mov     edx, 105h; nBufferLength
0x180009fb0  lea     r8, [rbp+700h+Buffer]; lpBuffer
0x180009fb7  lea     rcx, [rbp+700h+FindFileData.cFileName]; lpFileName
0x180009fbb  call    cs:__imp_GetFullPathNameW
0x180009fc1  test    eax, eax
0x180009fc3  jz      loc_18000A1D1
0x180009fc9  cmp     eax, 105h
0x180009fce  jnb     loc_18000A1D1
0x180009fd4  mov     r11d, 121h
0x180009fda  mov     [rbp+700h+CommandLine], r13w
0x180009fe2  mov     edx, r11d; unsigned __int64
0x180009fe5  lea     r8, aFindstrExe; "findstr.exe"
0x180009fec  lea     rcx, [rbp+700h+CommandLine]; unsigned __int16 *
0x180009ff3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180009ff8  lea     r8, asc_18003C374; " "
0x180009fff  mov     edx, r11d; unsigned __int64
0x18000a002  lea     rcx, [rbp+700h+CommandLine]; unsigned __int16 *
0x18000a009  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a00e  lea     r8, aXwizardDtd; "xwizard.dtd"
0x18000a015  mov     edx, 121h; unsigned __int64
0x18000a01a  lea     rcx, [rbp+700h+CommandLine]; unsigned __int16 *
0x18000a021  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a026  lea     r8, asc_18003C374; " "
0x18000a02d  mov     edx, 121h; unsigned __int64
0x18000a032  lea     rcx, [rbp+700h+CommandLine]; unsigned __int16 *
0x18000a039  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a03e  lea     r8, [rbp+700h+Buffer]; unsigned __int16 *
0x18000a045  mov     edx, 121h; unsigned __int64
0x18000a04a  lea     rcx, [rbp+700h+CommandLine]; unsigned __int16 *
0x18000a051  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a056  xor     edx, edx; Val
0x18000a058  lea     r8d, [rbx+63h]; Size
0x18000a05c  lea     rcx, [rbp+700h+StartupInfo+4]; void *
0x18000a060  call    memset_0
0x18000a065  xor     eax, eax
0x18000a067  mov     [rbp+700h+StartupInfo.cb], 68h ; 'h'
0x18000a06e  mov     qword ptr [rbp+700h+ProcessInformation.dwProcessId], rax
0x18000a072  lea     rdx, [rbp+700h+CommandLine]; lpCommandLine
0x18000a079  lea     rax, [rsp+800h+ProcessInformation]
0x18000a07e  xorps   xmm0, xmm0
0x18000a081  mov     [rsp+800h+lpProcessInformation], rax; lpProcessInformation
0x18000a086  xor     r9d, r9d; lpThreadAttributes
0x18000a089  lea     rax, [rbp+700h+StartupInfo]
0x18000a08d  xor     r8d, r8d; lpProcessAttributes
0x18000a090  mov     [rsp+800h+lpStartupInfo], rax; lpStartupInfo
0x18000a095  xor     ecx, ecx; lpApplicationName
0x18000a097  mov     [rsp+800h+lpCurrentDirectory], r13; lpCurrentDirectory
0x18000a09c  mov     [rsp+800h+lpEnvironment], r13; lpEnvironment
0x18000a0a1  mov     [rsp+800h+dwCreationFlags], 8000000h; dwCreationFlags
0x18000a0a9  mov     dword ptr [rsp+800h+ppv], r13d; bInheritHandles
0x18000a0ae  movups  xmmword ptr [rsp+800h+ProcessInformation.hProcess], xmm0
0x18000a0b3  call    cs:__imp_CreateProcessW
0x18000a0b9  test    eax, eax
0x18000a0bb  jz      short loc_18000A135
0x18000a0bd  mov     rcx, [rsp+800h+ProcessInformation.hProcess]; hHandle
0x18000a0c2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000a0c5  call    cs:__imp_WaitForSingleObject
0x18000a0cb  cmp     eax, 0FFFFFFFFh
0x18000a0ce  jz      short loc_18000A115
0x18000a0d0  mov     rcx, [rsp+800h+ProcessInformation.hProcess]; hProcess
0x18000a0d5  lea     rdx, [rsp+800h+ExitCode]; lpExitCode
0x18000a0da  mov     [rsp+800h+ExitCode], r13d
0x18000a0df  call    cs:__imp_GetExitCodeProcess
0x18000a0e5  test    eax, eax
0x18000a0e7  jz      short loc_18000A0F5
0x18000a0e9  cmp     [rsp+800h+ExitCode], r13d
0x18000a0ee  jnz     short loc_18000A16A
0x18000a0f0  mov     ebx, r13d
0x18000a0f3  jmp     short loc_18000A16A
0x18000a0f5  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x18000a0fa  mov     ebx, eax
0x18000a0fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a103  cmp     rcx, rdi
0x18000a106  jz      short loc_18000A16A
0x18000a108  test    byte ptr [rcx+1Ch], 4
0x18000a10c  jz      short loc_18000A16A
0x18000a10e  mov     edx, 23h ; '#'
0x18000a113  jmp     short loc_18000A153
0x18000a115  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x18000a11a  mov     ebx, eax
0x18000a11c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a123  cmp     rcx, rdi
0x18000a126  jz      short loc_18000A16A
0x18000a128  test    byte ptr [rcx+1Ch], 4
0x18000a12c  jz      short loc_18000A16A
0x18000a12e  mov     edx, 24h ; '$'
0x18000a133  jmp     short loc_18000A153
0x18000a135  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x18000a13a  mov     ebx, eax
0x18000a13c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a143  cmp     rcx, rdi
0x18000a146  jz      short loc_18000A16A
0x18000a148  test    byte ptr [rcx+1Ch], 4
0x18000a14c  jz      short loc_18000A16A
0x18000a14e  mov     edx, 25h ; '%'
0x18000a153  mov     rcx, [rcx+10h]
0x18000a157  lea     r9, [rbp+700h+CommandLine]
0x18000a15e  mov     r8, r14
0x18000a161  mov     dword ptr [rsp+800h+ppv], eax
0x18000a165  call    WPP_SF_SD
0x18000a16a  mov     rcx, [rsp+800h+ProcessInformation.hProcess]; hObject
0x18000a16f  call    cs:__imp_CloseHandle
0x18000a175  mov     rcx, [rsp+800h+ProcessInformation.hThread]; hObject
0x18000a17a  call    cs:__imp_CloseHandle
0x18000a180  test    ebx, ebx
0x18000a182  jnz     short loc_18000A1D1
0x18000a184  mov     rax, [rsp+800h+var_7A8]
0x18000a189  lea     rdx, [rbp+700h+FindFileData.cFileName]
0x18000a18d  xor     r9d, r9d
0x18000a190  mov     [rsp+800h+ppv], rax
0x18000a195  mov     r8d, r12d
0x18000a198  mov     rcx, r15
0x18000a19b  call    InternalProcessXMLFile
0x18000a1a0  mov     ebx, eax
0x18000a1a2  test    eax, eax
0x18000a1a4  jns     short loc_18000A1D1
0x18000a1a6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a1ad  cmp     rcx, rdi
0x18000a1b0  jz      short loc_18000A1D1
0x18000a1b2  test    byte ptr [rcx+1Ch], 4
0x18000a1b6  jz      short loc_18000A1D1
0x18000a1b8  mov     rcx, [rcx+10h]
0x18000a1bc  lea     r9, [rbp+700h+FindFileData.cFileName]
0x18000a1c0  mov     edx, 26h ; '&'
0x18000a1c5  mov     dword ptr [rsp+800h+ppv], eax
0x18000a1c9  mov     r8, r14
0x18000a1cc  call    WPP_SF_SD
0x18000a1d1  lea     rdx, [rbp+700h+FindFileData]; lpFindFileData
0x18000a1d5  mov     rcx, rsi; hFindFile
0x18000a1d8  call    cs:__imp_FindNextFileW
0x18000a1de  test    eax, eax
0x18000a1e0  jnz     loc_180009F8A
0x18000a1e6  mov     r13d, [rsp+800h+var_798]
0x18000a1eb  mov     rcx, [rsp+800h+var_7A8]
0x18000a1f0  mov     rax, [rcx]
0x18000a1f3  mov     rax, [rax+10h]
0x18000a1f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1fc  jmp     short loc_18000A22B
  ... truncated ...
```
