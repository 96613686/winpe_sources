# PersistenceManager::OpenMMF(WPN_INSTANCE_PRIVILEGE,WPN_MMF_HANDLE *,int *)

- ea: `0x1800a5d0c`
- end: `0x1800a61d4`
- name: `?OpenMMF@PersistenceManager@@AEAAJW4WPN_INSTANCE_PRIVILEGE@@PEAUWPN_MMF_HANDLE@@PEAH@Z`
- size: `1224`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800e50f8`
- `0x1800e67f0`

## callees

- `0x180004e38`
- `0x180011618`
- `0x180017a20`
- `0x18002cf14`
- `0x18002e730`
- `0x18002ee38`
- `0x180037600`
- `0x1800516d0`
- `0x1800a0b2c`
- `0x1800a5d0c`
- `0x1800a61dc`
- `0x1800af0a4`
- `0x1800b99f0`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800a5f93`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800a5f93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5f2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5fbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5fdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5ffd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a6057`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a60f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a6131`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a614a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5f2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5fbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5fdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5ffd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a6057`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a60f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a6131`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a614a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a5f18`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a5f18`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800a604d`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800a604d`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800a5e45`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800a5f57`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800a5e45`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800a5f57`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800a6122`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800a6122`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800a60e4`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800a60e4`

## string_xrefs

- `0x1800a5fa5`: `PersistenceManager::OpenMMF`
- `0x1800a6169`: `PersistenceManager::OpenMMF`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PersistenceManager::OpenMMF(__int64 a1, int a2, __int64 a3, _DWORD *a4)
{
  __int64 v8; // rbx
  __int64 v9; // rcx
  signed int v10; // ebx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  const WCHAR *v14; // rax
  int v15; // eax
  DWORD v16; // r12d
  DWORD v17; // eax
  DWORD v18; // eax
  DWORD v19; // eax
  int v20; // edi
  HANDLE FileW; // rax
  const WCHAR *v22; // rax
  int Directory; // eax
  unsigned int v24; // ecx
  signed int v25; // eax
  unsigned int v26; // ecx
  int v27; // r9d
  signed int v28; // eax
  __int64 v29; // r8
  signed int v30; // eax
  HANDLE FileMappingW; // rax
  signed int v32; // eax
  LPVOID v33; // rax
  signed int v34; // eax
  signed int LastError; // eax
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  DWORD v39; // [rsp+40h] [rbp-C0h]
  __int64 v40; // [rsp+48h] [rbp-B8h] BYREF
  DWORD flProtect; // [rsp+50h] [rbp-B0h]
  DWORD dwDesiredAccess; // [rsp+54h] [rbp-ACh]
  __int64 FileInformation; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR Dst[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR v45[264]; // [rsp+280h] [rbp+180h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4D8h] [rbp+3D8h]

  FileInformation = 0;
  v40 = 0;
  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !*(_QWORD *)(a1 + 56) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( a2 >= 2 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v8 = *(_QWORD *)(a1 + 176);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
  Microsoft::WRL::ComPtr<IPlatformConfigurationProvider>::InternalAddRef(v8 + 336);
  v9 = *(_QWORD *)(v8 + 336);
  v40 = v9;
  if ( !v9 )
  {
    v10 = -2143420155;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x400,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\platform.cpp",
      (const char *)0x803E0105LL,
      dwCreationDisposition);
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x834,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\infra\\persistencemanager.cpp",
      (const char *)0x803E0105LL,
      dwCreationDispositiona);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v12 = 65;
      v13 = 2151547141LL;
LABEL_11:
      WPP_SF_d(v11[2], v12, WPP_ac3d69826ca03a16ae3e9918ed4e7821_Traceguids, v13);
      goto LABEL_66;
    }
    goto LABEL_66;
  }
  v14 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 40LL))(v9);
  if ( ExpandEnvironmentStringsW(v14, Dst, 0x104u) - 1 > 0x103 )
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    v27 = 2110;
  }
  else
  {
    v15 = StringCchCatW(Dst, 0x104u, L"\\appdb.dat");
    v10 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x845,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\infra\\persistencemanager.cpp",
        (const char *)(unsigned int)v15,
        dwCreationDisposition);
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v12 = 67;
        v13 = (unsigned int)v10;
        goto LABEL_11;
      }
LABEL_66:
      if ( (Microsoft_Windows_PushNotifications_PlatformEnableBits & 0x20) != 0 )
        McTemplateU0zq_EventWriteTransfer(v11, WPNCORE_EVENT_FILEPATH_INIT, Dst, (unsigned int)v10);
      goto LABEL_68;
    }
    v16 = 3;
    if ( a2 != 1 )
      v16 = 1;
    v17 = 2;
    if ( a2 != 1 )
      v17 = 4;
    flProtect = v17;
    v18 = 4;
    if ( a2 != 1 )
      v18 = 2;
    dwDesiredAccess = v18;
    v19 = 0x80000000;
    if ( a2 != 1 )
      v19 = -1073741824;
    v39 = v19;
    v20 = 0;
    while ( 1 )
    {
      FileW = CreateFileW(Dst, v19, v16, 0, 4u, 0x80u, 0);
      *(_QWORD *)a3 = FileW;
      if ( FileW != (HANDLE)-1LL )
        break;
      if ( GetLastError() == 3 )
      {
        v22 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v40 + 40LL))(v40);
        if ( ExpandEnvironmentStringsW(v22, v45, 0x104u) - 1 > 0x103 )
        {
          v25 = GetLastError();
          v10 = v25;
          if ( v25 > 0 )
            v10 = (unsigned __int16)v25 | 0x80070000;
          v27 = 2153;
          goto LABEL_64;
        }
        Directory = RecursiveCreateDirectory(v45);
        v10 = Directory;
        if ( Directory < 0 )
        {
          WpnDebugInitTrace(
            v24,
            L"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\infra\\persistencemanager.cpp",
            L"PersistenceManager::OpenMMF",
            2177,
            Directory);
          goto LABEL_66;
        }
      }
      else
      {
        if ( v20 >= 50 )
        {
          v28 = GetLastError();
          v10 = v28;
          if ( v28 > 0 )
            v10 = (unsigned __int16)v28 | 0x80070000;
          v27 = 2193;
          goto LABEL_64;
        }
        ++v20;
        Sleep(0x64u);
      }
      v19 = v39;
    }
    if ( GetLastError() == 183 || a2 )
    {
      if ( a4 )
        *a4 = 0;
    }
    else
    {
      FileInformation = 0;
      FileInformation = 165104LL * *(unsigned __int16 *)(*(_QWORD *)(a1 + 56) + 6LL) + 32;
      if ( !SetFileInformationByHandle(*(HANDLE *)a3, FileAllocationInfo, &FileInformation, 8u) )
      {
        v30 = GetLastError();
        v10 = v30;
        if ( v30 > 0 )
          v10 = (unsigned __int16)v30 | 0x80070000;
        if ( v10 < 0 )
          v10 = 0;
      }
      if ( a4 )
        *a4 = 1;
      if ( (Microsoft_Windows_PushNotifications_PlatformEnableBits & 0x10) != 0 )
        McGenEventWrite_EventWriteTransfer(&WPNCORE_PROVIDER_GUID_Context, WPNPLAT_CREATE_NEW_FILE, v29, 1);
    }
    FileMappingW = CreateFileMappingW(
                     *(HANDLE *)a3,
                     0,
                     flProtect,
                     (165104 * (unsigned __int64)*(unsigned __int16 *)(*(_QWORD *)(a1 + 56) + 6LL) + 32) >> 32,
                     165104 * (unsigned int)*(unsigned __int16 *)(*(_QWORD *)(a1 + 56) + 6LL) + 32,
                     0);
    *(_QWORD *)(a3 + 8) = FileMappingW;
    if ( FileMappingW )
    {
      v33 = MapViewOfFile(FileMappingW, dwDesiredAccess, 0, 0, 0);
      *(_QWORD *)(a3 + 16) = v33;
      if ( v33 )
        goto LABEL_65;
      v34 = GetLastError();
      v10 = v34;
      if ( v34 > 0 )
        v10 = (unsigned __int16)v34 | 0x80070000;
      v27 = 2262;
    }
    else
    {
      v32 = GetLastError();
      v10 = v32;
      if ( v32 > 0 )
        v10 = (unsigned __int16)v32 | 0x80070000;
      v27 = 2251;
    }
  }
LABEL_64:
  WpnDebugInitTrace(
    v26,
    L"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\infra\\persistencemanager.cpp",
    L"PersistenceManager::OpenMMF",
    v27,
    v10);
LABEL_65:
  if ( v10 < 0 )
    goto LABEL_66;
LABEL_68:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800a5d0c  mov     [rsp-8+arg_8], rbx
0x1800a5d11  push    rbp
0x1800a5d12  push    rsi
0x1800a5d13  push    rdi
0x1800a5d14  push    r12
0x1800a5d16  push    r13
0x1800a5d18  push    r14
0x1800a5d1a  push    r15
0x1800a5d1c  lea     rbp, [rsp-3A0h]
0x1800a5d24  sub     rsp, 4A0h
0x1800a5d2b  mov     rax, cs:__security_cookie
0x1800a5d32  xor     rax, rsp
0x1800a5d35  mov     [rbp+3D0h+var_40], rax
0x1800a5d3c  mov     rsi, r9
0x1800a5d3f  mov     r14, r8
0x1800a5d42  mov     r15d, edx
0x1800a5d45  mov     r13, rcx
0x1800a5d48  mov     [rsp+4D0h+FileInformation], 0
0x1800a5d51  mov     [rsp+4D0h+var_488], 0
0x1800a5d5a  test    r8, r8
0x1800a5d5d  jnz     short loc_1800A5D64
0x1800a5d5f  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "MMFHandle != NULL")
0x1800a5d64  cmp     qword ptr [r13+38h], 0
0x1800a5d69  jnz     short loc_1800A5D70
0x1800a5d6b  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "m_AppDBRegHeader != NULL")
0x1800a5d70  mov     edi, 2
0x1800a5d75  cmp     r15d, edi
0x1800a5d78  jl      short loc_1800A5D7F
0x1800a5d7a  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "Privilege < MAX_INSTANCE_PRIVILEGE")
0x1800a5d7f  mov     rbx, [r13+0B0h]
0x1800a5d86  lea     rcx, [rsp+4D0h+var_488]
0x1800a5d8b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a5d90  lea     rcx, [rbx+150h]
0x1800a5d97  call    ?InternalAddRef@?$ComPtr@UIPlatformConfigurationProvider@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IPlatformConfigurationProvider>::InternalAddRef(void)
0x1800a5d9c  mov     rcx, [rbx+150h]
0x1800a5da3  mov     [rsp+4D0h+var_488], rcx
0x1800a5da8  test    rcx, rcx
0x1800a5dab  jnz     short loc_1800A5E29
0x1800a5dad  mov     rcx, [rbp+3D8h]; this
0x1800a5db4  mov     ebx, 803E0105h
0x1800a5db9  mov     r9d, ebx; char *
0x1800a5dbc  lea     r8, aOnecoreuapBase_161; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800a5dc3  mov     edx, 400h; void *
0x1800a5dc8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a5dcd  mov     rcx, [rbp+3D8h]; this
0x1800a5dd4  mov     r9d, ebx; char *
0x1800a5dd7  lea     r8, aOnecoreuapBase_24; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800a5dde  mov     edx, 834h; void *
0x1800a5de3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800a5de8  lea     rax, WPP_GLOBAL_Control
0x1800a5def  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a5df6  cmp     rcx, rax
0x1800a5df9  jz      loc_1800A6180
0x1800a5dff  test    byte ptr [rcx+1Ch], 80h
0x1800a5e03  jz      loc_1800A6180
0x1800a5e09  mov     edx, 41h ; 'A'
0x1800a5e0e  mov     r9d, 803E0105h
0x1800a5e14  lea     r8, WPP_ac3d69826ca03a16ae3e9918ed4e7821_Traceguids
0x1800a5e1b  mov     rcx, [rcx+10h]
0x1800a5e1f  call    WPP_SF_d
0x1800a5e24  jmp     loc_1800A6180
0x1800a5e29  mov     rax, [rcx]
0x1800a5e2c  mov     rax, [rax+28h]
0x1800a5e30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5e35  mov     rcx, rax; lpSrc
0x1800a5e38  mov     ebx, 104h
0x1800a5e3d  mov     r8d, ebx; nSize
0x1800a5e40  lea     rdx, [rsp+4D0h+Dst]; lpDst
0x1800a5e45  call    cs:__imp_ExpandEnvironmentStringsW
0x1800a5e4b  dec     eax
0x1800a5e4d  cmp     eax, 103h
0x1800a5e52  ja      loc_1800A614A
0x1800a5e58  lea     r8, aAppdbDat; "\\appdb.dat"
0x1800a5e5f  mov     edx, ebx; unsigned __int64
0x1800a5e61  lea     rcx, [rsp+4D0h+Dst]; unsigned __int16 *
0x1800a5e66  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800a5e6b  mov     ebx, eax
0x1800a5e6d  test    eax, eax
0x1800a5e6f  jns     short loc_1800A5EBA
0x1800a5e71  mov     rcx, [rbp+3D8h]; this
0x1800a5e78  mov     r9d, eax; char *
0x1800a5e7b  lea     r8, aOnecoreuapBase_24; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800a5e82  mov     edx, 845h; void *
0x1800a5e87  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800a5e8c  lea     rax, WPP_GLOBAL_Control
0x1800a5e93  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a5e9a  cmp     rcx, rax
0x1800a5e9d  jz      loc_1800A6180
0x1800a5ea3  test    byte ptr [rcx+1Ch], 80h
0x1800a5ea7  jz      loc_1800A6180
0x1800a5ead  mov     edx, 43h ; 'C'
0x1800a5eb2  mov     r9d, ebx
0x1800a5eb5  jmp     loc_1800A5E14
0x1800a5eba  mov     edx, 1
0x1800a5ebf  lea     r12d, [rdx+2]
0x1800a5ec3  cmp     r15d, edx
0x1800a5ec6  cmovnz  r12d, edx
0x1800a5eca  mov     eax, edi
0x1800a5ecc  lea     r8d, [rdx+3]
0x1800a5ed0  cmovnz  eax, r8d
0x1800a5ed4  mov     [rsp+4D0h+flProtect], eax
0x1800a5ed8  mov     eax, r8d
0x1800a5edb  cmovnz  eax, edi
0x1800a5ede  mov     [rsp+4D0h+dwDesiredAccess], eax
0x1800a5ee2  mov     eax, 80000000h
0x1800a5ee7  mov     ecx, 0C0000000h
0x1800a5eec  cmovnz  eax, ecx
0x1800a5eef  mov     [rsp+4D0h+var_490], eax
0x1800a5ef3  xor     edi, edi
0x1800a5ef5  mov     [rsp+4D0h+hTemplateFile], 0; hTemplateFile
0x1800a5efe  mov     [rsp+4D0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800a5f06  mov     [rsp+4D0h+dwCreationDisposition], r8d; dwCreationDisposition
0x1800a5f0b  xor     r9d, r9d; lpSecurityAttributes
0x1800a5f0e  mov     r8d, r12d; dwShareMode
0x1800a5f11  mov     edx, eax; dwDesiredAccess
0x1800a5f13  lea     rcx, [rsp+4D0h+Dst]; lpFileName
0x1800a5f18  call    cs:__imp_CreateFileW
0x1800a5f1e  mov     [r14], rax
0x1800a5f21  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800a5f25  jnz     loc_1800A5FFD
0x1800a5f2b  call    cs:__imp_GetLastError
0x1800a5f31  cmp     eax, 3
0x1800a5f34  jnz     short loc_1800A5F87
0x1800a5f36  mov     rcx, [rsp+4D0h+var_488]
0x1800a5f3b  mov     rax, [rcx]
0x1800a5f3e  mov     rax, [rax+28h]
0x1800a5f42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5f47  mov     rcx, rax; lpSrc
0x1800a5f4a  mov     r8d, 104h; nSize
0x1800a5f50  lea     rdx, [rbp+3D0h+var_250]; lpDst
0x1800a5f57  call    cs:__imp_ExpandEnvironmentStringsW
0x1800a5f5d  dec     eax
0x1800a5f5f  cmp     eax, 103h
0x1800a5f64  ja      short loc_1800A5FBD
0x1800a5f66  lea     rcx, [rbp+3D0h+var_250]; unsigned __int16 *
0x1800a5f6d  call    ?RecursiveCreateDirectory@@YAJPEBG@Z; RecursiveCreateDirectory(ushort const *)
0x1800a5f72  mov     ebx, eax
0x1800a5f74  test    eax, eax
0x1800a5f76  js      short loc_1800A5F9B
0x1800a5f78  mov     eax, [rsp+4D0h+var_490]
0x1800a5f7c  mov     r8d, 4
0x1800a5f82  jmp     loc_1800A5EF5
0x1800a5f87  cmp     edi, 32h ; '2'
0x1800a5f8a  jge     short loc_1800A5FDD
0x1800a5f8c  inc     edi
0x1800a5f8e  mov     ecx, 64h ; 'd'; dwMilliseconds
0x1800a5f93  call    cs:__imp_Sleep
0x1800a5f99  jmp     short loc_1800A5F78
0x1800a5f9b  mov     [rsp+4D0h+dwCreationDisposition], eax; int
0x1800a5f9f  mov     r9d, 881h; int
0x1800a5fa5  lea     r8, aPersistenceman_2; "PersistenceManager::OpenMMF"
0x1800a5fac  lea     rdx, aOnecoreuapBase_2; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800a5fb3  call    ?WpnDebugInitTrace@@YAXKPEBG0HJ@Z; WpnDebugInitTrace(ulong,ushort const *,ushort const *,int,long)
0x1800a5fb8  jmp     loc_1800A6180
0x1800a5fbd  call    cs:__imp_GetLastError
0x1800a5fc3  mov     ebx, eax
0x1800a5fc5  test    eax, eax
0x1800a5fc7  jle     short loc_1800A5FD2
0x1800a5fc9  movzx   ebx, ax
0x1800a5fcc  or      ebx, 80070000h
0x1800a5fd2  mov     r9d, 869h
0x1800a5fd8  jmp     loc_1800A6165
0x1800a5fdd  call    cs:__imp_GetLastError
0x1800a5fe3  mov     ebx, eax
0x1800a5fe5  test    eax, eax
0x1800a5fe7  jle     short loc_1800A5FF2
0x1800a5fe9  movzx   ebx, ax
0x1800a5fec  or      ebx, 80070000h
0x1800a5ff2  mov     r9d, 891h
0x1800a5ff8  jmp     loc_1800A6165
0x1800a5ffd  call    cs:__imp_GetLastError
0x1800a6003  mov     edi, 80070000h
0x1800a6008  cmp     eax, 0B7h
0x1800a600d  jz      loc_1800A60A8
0x1800a6013  test    r15d, r15d
0x1800a6016  jnz     loc_1800A60A8
0x1800a601c  mov     [rsp+4D0h+FileInformation], 0
0x1800a6025  mov     rax, [r13+38h]
0x1800a6029  movzx   ecx, word ptr [rax+6]
0x1800a602d  imul    rax, rcx, 284F0h
0x1800a6034  add     rax, 20h ; ' '
0x1800a6038  mov     [rsp+4D0h+FileInformation], rax
0x1800a603d  lea     r9d, [r15+8]; dwBufferSize
0x1800a6041  lea     r8, [rsp+4D0h+FileInformation]; lpFileInformation
0x1800a6046  lea     edx, [r15+5]; FileInformationClass
0x1800a604a  mov     rcx, [r14]; hFile
0x1800a604d  call    cs:__imp_SetFileInformationByHandle
0x1800a6053  test    eax, eax
0x1800a6055  jnz     short loc_1800A606F
0x1800a6057  call    cs:__imp_GetLastError
0x1800a605d  mov     ebx, eax
0x1800a605f  test    eax, eax
0x1800a6061  jle     short loc_1800A6068
0x1800a6063  movzx   ebx, ax
0x1800a6066  or      ebx, edi
0x1800a6068  xor     eax, eax
0x1800a606a  test    ebx, ebx
0x1800a606c  cmovs   ebx, eax
0x1800a606f  test    rsi, rsi
0x1800a6072  jz      short loc_1800A607A
0x1800a6074  mov     dword ptr [rsi], 1
0x1800a607a  test    cs:Microsoft_Windows_PushNotifications_PlatformEnableBits, 10h
0x1800a6081  jz      short loc_1800A60B3
0x1800a6083  lea     rax, [rsp+4D0h+var_470]
0x1800a6088  mov     qword ptr [rsp+4D0h+dwCreationDisposition], rax
0x1800a608d  mov     r9d, 1
0x1800a6093  lea     rdx, WPNPLAT_CREATE_NEW_FILE
0x1800a609a  lea     rcx, WPNCORE_PROVIDER_GUID_Context
0x1800a60a1  call    McGenEventWrite_EventWriteTransfer
0x1800a60a6  jmp     short loc_1800A60B3
0x1800a60a8  test    rsi, rsi
0x1800a60ab  jz      short loc_1800A60B3
0x1800a60ad  mov     dword ptr [rsi], 0
0x1800a60b3  mov     rax, [r13+38h]
0x1800a60b7  movzx   ecx, word ptr [rax+6]
0x1800a60bb  imul    rax, rcx, 284F0h
0x1800a60c2  add     rax, 20h ; ' '
0x1800a60c6  mov     r9, rax
0x1800a60c9  shr     r9, 20h; dwMaximumSizeHigh
0x1800a60cd  mov     qword ptr [rsp+4D0h+dwFlagsAndAttributes], 0; lpName
0x1800a60d6  mov     [rsp+4D0h+dwCreationDisposition], eax; dwMaximumSizeLow
0x1800a60da  mov     r8d, [rsp+4D0h+flProtect]; flProtect
0x1800a60df  xor     edx, edx; lpFileMappingAttributes
0x1800a60e1  mov     rcx, [r14]; hFile
0x1800a60e4  call    cs:__imp_CreateFileMappingW
0x1800a60ea  mov     [r14+8], rax
0x1800a60ee  test    rax, rax
0x1800a60f1  jnz     short loc_1800A610C
0x1800a60f3  call    cs:__imp_GetLastError
0x1800a60f9  mov     ebx, eax
0x1800a60fb  test    eax, eax
0x1800a60fd  jle     short loc_1800A6104
0x1800a60ff  movzx   ebx, ax
0x1800a6102  or      ebx, edi
0x1800a6104  mov     r9d, 8CBh
0x1800a610a  jmp     short loc_1800A6165
0x1800a610c  mov     qword ptr [rsp+4D0h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x1800a6115  xor     r9d, r9d; dwFileOffsetLow
0x1800a6118  xor     r8d, r8d; dwFileOffsetHigh
0x1800a611b  mov     edx, [rsp+4D0h+dwDesiredAccess]; dwDesiredAccess
0x1800a611f  mov     rcx, rax; hFileMappingObject
0x1800a6122  call    cs:__imp_MapViewOfFile
0x1800a6128  mov     [r14+10h], rax
0x1800a612c  test    rax, rax
0x1800a612f  jnz     short loc_1800A617C
0x1800a6131  call    cs:__imp_GetLastError
0x1800a6137  mov     ebx, eax
0x1800a6139  test    eax, eax
0x1800a613b  jle     short loc_1800A6142
0x1800a613d  movzx   ebx, ax
0x1800a6140  or      ebx, edi
0x1800a6142  mov     r9d, 8D6h
0x1800a6148  jmp     short loc_1800A6165
0x1800a614a  call    cs:__imp_GetLastError
0x1800a6150  mov     ebx, eax
0x1800a6152  test    eax, eax
0x1800a6154  jle     short loc_1800A615F
0x1800a6156  movzx   ebx, ax
0x1800a6159  or      ebx, 80070000h
0x1800a615f  mov     r9d, 83Eh; int
0x1800a6165  mov     [rsp+4D0h+dwCreationDisposition], ebx; int
0x1800a6169  lea     r8, aPersistenceman_2; "PersistenceManager::OpenMMF"
0x1800a6170  lea     rdx, aOnecoreuapBase_2; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800a6177  call    ?WpnDebugInitTrace@@YAXKPEBG0HJ@Z; WpnDebugInitTrace(ulong,ushort const *,ushort const *,int,long)
0x1800a617c  test    ebx, ebx
0x1800a617e  jns     short loc_1800A619E
0x1800a6180  test    cs:Microsoft_Windows_PushNotifications_PlatformEnableBits, 20h
0x1800a6187  jz      short loc_1800A619E
0x1800a6189  mov     r9d, ebx
0x1800a618c  lea     r8, [rsp+4D0h+Dst]
0x1800a6191  lea     rdx, WPNCORE_EVENT_FILEPATH_INIT
0x1800a6198  call    McTemplateU0zq_EventWriteTransfer
0x1800a619d  nop
0x1800a619e  lea     rcx, [rsp+4D0h+var_488]
0x1800a61a3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a61a8  mov     eax, ebx
0x1800a61aa  mov     rcx, [rbp+3D0h+var_40]
0x1800a61b1  xor     rcx, rsp; StackCookie
0x1800a61b4  call    __security_check_cookie
0x1800a61b9  mov     rbx, [rsp+4D0h+arg_8]
0x1800a61c1  add     rsp, 4A0h
0x1800a61c8  pop     r15
0x1800a61ca  pop     r14
0x1800a61cc  pop     r13
0x1800a61ce  pop     r12
0x1800a61d0  pop     rdi
0x1800a61d1  pop     rsi
0x1800a61d2  pop     rbp
0x1800a61d3  retn
```
