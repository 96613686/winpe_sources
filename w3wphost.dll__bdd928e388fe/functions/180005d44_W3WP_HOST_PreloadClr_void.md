# W3WP_HOST::PreloadClr(void)

- ea: `0x180005d44`
- end: `0x18000613d`
- name: `?PreloadClr@W3WP_HOST@@QEAAJXZ`
- size: `1017`
- prototype: `__int64 __fastcall(W3WP_HOST *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800051dc`

## callees

- `0x180003878`
- `0x1800041ec`
- `0x180005d44`
- `0x180006fe8`
- `0x18000c1e8`
- `0x18000c39e`
- `0x18000c3d0`
- `0x18000d010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180005e6c`
- `msvcrt!wcsrchr` at `0x180005e6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005e17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006028`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005e17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006028`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180005e50`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180005e50`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180005e0b`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180005e0b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180005fa2`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180005fa2`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180005dfe`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180005e60`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180005e7a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180005eae`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180005edf`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180005f99`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180005fc9`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180005dfe`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180005e60`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180005e7a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180005eae`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180005edf`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180005f99`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180005fc9`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180005dd5`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180005ded`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180005e9d`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180005f24`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180005dd5`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180005ded`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180005e9d`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180005f24`
- `iisutil!PuDbgPrint` at `0x180005f77`
- `iisutil!PuDbgPrint` at `0x180005f77`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x18000606a`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x180006103`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x18000606a`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x180006103`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180005d9b`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180005d9b`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180005f15`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180005f15`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x180005e8e`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x180005e8e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000610e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000610e`

## string_xrefs

- `0x180005f5e`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`
- `0x180005f1d`: `\Aspnet.config`

## pseudocode

```c
__int64 __fastcall W3WP_HOST::PreloadClr(W3WP_HOST *this)
{
  W3WP_HOST *v2; // rcx
  int FrameworkInstallationPath; // ebx
  const WCHAR *Str; // rax
  HANDLE FirstFileW; // rax
  signed int LastError; // eax
  WCHAR *cFileName; // rax
  const wchar_t *v8; // rax
  wchar_t *v9; // rbx
  unsigned __int16 *v10; // rax
  const unsigned __int16 *v11; // rax
  const unsigned __int16 *v12; // rax
  int v13; // eax
  const unsigned __int16 *v14; // rdx
  int v15; // eax
  unsigned int v16; // esi
  const WCHAR *v17; // rax
  GUID *v18; // rbx
  const unsigned __int16 *v19; // r8
  int v20; // eax
  signed int v21; // eax
  unsigned int v22; // edx
  __int64 v23; // rax
  GUID *v24; // rbx
  WCHAR *v26; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v27[56]; // [rsp+58h] [rbp-A8h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v29[128]; // [rsp+2E0h] [rbp+1E0h] BYREF

  memset_0(v29, 0, sizeof(v29));
  STRU::STRU((STRU *)v27, v29, 0x80u);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FrameworkInstallationPath = W3WP_HOST::GetFrameworkInstallationPath(v2, (struct STRU *)v27);
  if ( FrameworkInstallationPath >= 0 )
  {
    FrameworkInstallationPath = STRU::Append((STRU *)v27, *(const unsigned __int16 **)(*((_QWORD *)this + 39) + 40LL));
    if ( FrameworkInstallationPath >= 0 )
    {
      FrameworkInstallationPath = STRU::Append((STRU *)v27, L"*");
      if ( FrameworkInstallationPath >= 0 )
      {
        Str = STRU::QueryStr((STRU *)v27);
        FirstFileW = FindFirstFileW(Str, &FindFileData);
        if ( FirstFileW == (HANDLE)-1LL )
        {
          LastError = GetLastError();
          FrameworkInstallationPath = LastError;
          if ( LastError > 0 )
            FrameworkInstallationPath = (unsigned __int16)LastError | 0x80070000;
          goto LABEL_7;
        }
        FindClose(FirstFileW);
        v8 = STRU::QueryStr((STRU *)v27);
        v9 = wcsrchr(v8, 0x5Cu);
        v10 = STRU::QueryStr((STRU *)v27);
        STRU::SetLen((STRU *)v27, v9 - v10 + 1);
        FrameworkInstallationPath = STRU::Append((STRU *)v27, FindFileData.cFileName);
        if ( FrameworkInstallationPath >= 0 )
        {
          v11 = STRU::QueryStr((STRU *)v27);
          FrameworkInstallationPath = SMALL_STRU::Copy((W3WP_HOST *)((char *)this + 1600), v11);
          if ( FrameworkInstallationPath >= 0 )
          {
            if ( !*(_DWORD *)(*((_QWORD *)this + 39) + 88LL) )
            {
              v12 = STRU::QueryStr((STRU *)v27);
              v13 = W3WP_HOST::TryPreloadClrViaHelperLoader(this, v12);
              FrameworkInstallationPath = v13;
              if ( !v13 )
                goto LABEL_7;
              if ( v13 < 0 )
                goto LABEL_43;
            }
            v14 = *(const unsigned __int16 **)(*((_QWORD *)this + 39) + 48LL);
            v15 = v14 ? STRU::Copy((STRU *)v27, v14) : STRU::Append((STRU *)v27, L"\\Aspnet.config");
            FrameworkInstallationPath = v15;
            if ( v15 >= 0 )
            {
              FrameworkInstallationPath = CLR_HOSTING::Initialize();
              if ( FrameworkInstallationPath < 0 )
              {
                if ( (g_dwDebugFlags & 3) != 0 )
                  PuDbgPrint(
                    g_pDebug,
                    "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
                    2932,
                    "W3WP_HOST::PreloadClr",
                    "Failed to initialize the CLR hosting library hr = %x\n");
                goto LABEL_8;
              }
              v16 = 22;
              if ( FindFileData.cFileName[1] >= 0x32u )
                v16 = 139286;
              v17 = STRU::QueryStr((STRU *)v27);
              if ( GetFileAttributesW(v17) == -1 )
              {
                if ( *(_QWORD *)(*((_QWORD *)this + 39) + 48LL) )
                {
                  v21 = GetLastError();
                  v22 = v21;
                  if ( v21 > 0 )
                    v22 = (unsigned __int16)v21 | 0x80070000;
                  v23 = *((_QWORD *)this + 39);
                  v26 = 0;
                  v26 = *(WCHAR **)(v23 + 48);
                  EVENT_LOG::LogEvent(
                    (W3WP_HOST *)((char *)this + 80),
                    0x800008FC,
                    1u,
                    (const unsigned __int16 **const)&v26,
                    v22);
                }
                v24 = &CLSID_CLRRuntimeHost;
                if ( FindFileData.cFileName[1] < 0x32u )
                  v24 = &CLSID_CorRuntimeHost;
                if ( CLR_HOSTING::s_pFnCoreBindToRuntimeEx )
                {
                  v20 = CLR_HOSTING::s_pFnCoreBindToRuntimeEx(
                          FindFileData.cFileName,
                          L"svr",
                          v16,
                          v24,
                          &IID_IUnknown,
                          (void **)this + 38);
                  goto LABEL_37;
                }
              }
              else
              {
                v18 = &CLSID_CLRRuntimeHost;
                if ( FindFileData.cFileName[1] < 0x32u )
                  v18 = &CLSID_CorRuntimeHost;
                v19 = STRU::QueryStr((STRU *)v27);
                if ( CLR_HOSTING::s_pFnCoreBindToRuntimeHost )
                {
                  v20 = CLR_HOSTING::s_pFnCoreBindToRuntimeHost(
                          FindFileData.cFileName,
                          L"svr",
                          v19,
                          0,
                          v16,
                          v18,
                          &IID_IUnknown,
                          (void **)this + 38);
LABEL_37:
                  FrameworkInstallationPath = v20;
                  goto LABEL_39;
                }
              }
              FrameworkInstallationPath = -2147024846;
LABEL_39:
              if ( FrameworkInstallationPath == -2147024846 )
              {
                FrameworkInstallationPath = 0;
                goto LABEL_43;
              }
LABEL_7:
              if ( FrameworkInstallationPath >= 0 )
                goto LABEL_43;
            }
          }
        }
      }
    }
  }
LABEL_8:
  v26 = 0;
  if ( FindFileData.cFileName[0] )
    cFileName = FindFileData.cFileName;
  else
    cFileName = *(WCHAR **)(*((_QWORD *)this + 39) + 40LL);
  v26 = cFileName;
  EVENT_LOG::LogEvent(
    (W3WP_HOST *)((char *)this + 80),
    0xC00008F6,
    1u,
    (const unsigned __int16 **const)&v26,
    FrameworkInstallationPath);
LABEL_43:
  STRU::~STRU((STRU *)v27);
  return (unsigned int)FrameworkInstallationPath;
}

```

## disassembly

```asm
0x180005d44  mov     [rsp-8+arg_8], rbx
0x180005d49  mov     [rsp-8+arg_10], rsi
0x180005d4e  push    rbp
0x180005d4f  push    rdi
0x180005d50  push    r14
0x180005d52  lea     rbp, [rsp-2F0h]
0x180005d5a  sub     rsp, 3F0h
0x180005d61  mov     rax, cs:__security_cookie
0x180005d68  xor     rax, rsp
0x180005d6b  mov     [rbp+300h+var_20], rax
0x180005d72  mov     rdi, rcx
0x180005d75  xor     edx, edx; Val
0x180005d77  lea     rcx, [rbp+300h+var_120]; void *
0x180005d7e  mov     r8d, 100h; Size
0x180005d84  call    memset_0
0x180005d89  mov     r8d, 80h
0x180005d8f  lea     rdx, [rbp+300h+var_120]
0x180005d96  lea     rcx, [rsp+400h+var_3A8]
0x180005d9b  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180005da1  xor     edx, edx; Val
0x180005da3  lea     rcx, [rbp+300h+FindFileData]; void *
0x180005da7  mov     r8d, 250h; Size
0x180005dad  call    memset_0
0x180005db2  lea     rdx, [rsp+400h+var_3A8]; struct STRU *
0x180005db7  call    ?GetFrameworkInstallationPath@W3WP_HOST@@AEAAJPEAVSTRU@@@Z; W3WP_HOST::GetFrameworkInstallationPath(STRU *)
0x180005dbc  xor     r14d, r14d
0x180005dbf  mov     ebx, eax
0x180005dc1  test    eax, eax
0x180005dc3  js      short loc_180005E34
0x180005dc5  mov     rdx, [rdi+138h]
0x180005dcc  lea     rcx, [rsp+400h+var_3A8]
0x180005dd1  mov     rdx, [rdx+28h]
0x180005dd5  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180005ddb  mov     ebx, eax
0x180005ddd  test    eax, eax
0x180005ddf  js      short loc_180005E34
0x180005de1  lea     rdx, asc_18000F8F4; "*"
0x180005de8  lea     rcx, [rsp+400h+var_3A8]
0x180005ded  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180005df3  mov     ebx, eax
0x180005df5  test    eax, eax
0x180005df7  js      short loc_180005E34
0x180005df9  lea     rcx, [rsp+400h+var_3A8]
0x180005dfe  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180005e04  mov     rcx, rax; lpFileName
0x180005e07  lea     rdx, [rbp+300h+FindFileData]; lpFindFileData
0x180005e0b  call    cs:__imp_FindFirstFileW
0x180005e11  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180005e15  jnz     short loc_180005E4D
0x180005e17  call    cs:__imp_GetLastError
0x180005e1d  mov     ebx, eax
0x180005e1f  test    eax, eax
0x180005e21  jle     short loc_180005E2C
0x180005e23  movzx   ebx, ax
0x180005e26  or      ebx, 80070000h
0x180005e2c  test    ebx, ebx
0x180005e2e  jns     loc_180006109
0x180005e34  mov     [rsp+400h+var_3B0], r14
0x180005e39  cmp     [rbp+300h+FindFileData.cFileName], r14w
0x180005e3e  jz      loc_1800060DB
0x180005e44  lea     rax, [rbp+300h+FindFileData.cFileName]
0x180005e48  jmp     loc_1800060E6
0x180005e4d  mov     rcx, rax; hFindFile
0x180005e50  call    cs:__imp_FindClose
0x180005e56  lea     rcx, [rsp+400h+var_3A8]
0x180005e5b  mov     ebx, 5Ch ; '\'
0x180005e60  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180005e66  mov     rcx, rax; Str
0x180005e69  movzx   edx, bx; Ch
0x180005e6c  call    cs:__imp_wcsrchr
0x180005e72  lea     rcx, [rsp+400h+var_3A8]
0x180005e77  mov     rbx, rax
0x180005e7a  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180005e80  sub     rbx, rax
0x180005e83  lea     rcx, [rsp+400h+var_3A8]
0x180005e88  sar     rbx, 1
0x180005e8b  lea     edx, [rbx+1]
0x180005e8e  call    cs:__imp_?SetLen@STRU@@QEAA_NK@Z; STRU::SetLen(ulong)
0x180005e94  lea     rdx, [rbp+300h+FindFileData.cFileName]
0x180005e98  lea     rcx, [rsp+400h+var_3A8]
0x180005e9d  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180005ea3  mov     ebx, eax
0x180005ea5  test    eax, eax
0x180005ea7  js      short loc_180005E34
0x180005ea9  lea     rcx, [rsp+400h+var_3A8]
0x180005eae  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180005eb4  mov     rdx, rax; unsigned __int16 *
0x180005eb7  lea     rcx, [rdi+640h]; this
0x180005ebe  call    ?Copy@SMALL_STRU@@QEAAJPEBG@Z; SMALL_STRU::Copy(ushort const *)
0x180005ec3  mov     ebx, eax
0x180005ec5  test    eax, eax
0x180005ec7  js      loc_180005E34
0x180005ecd  mov     rax, [rdi+138h]
0x180005ed4  cmp     [rax+58h], r14d
0x180005ed8  jnz     short loc_180005F00
0x180005eda  lea     rcx, [rsp+400h+var_3A8]
0x180005edf  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180005ee5  mov     rdx, rax; unsigned __int16 *
0x180005ee8  mov     rcx, rdi; this
0x180005eeb  call    ?TryPreloadClrViaHelperLoader@W3WP_HOST@@QEAAJPEBG@Z; W3WP_HOST::TryPreloadClrViaHelperLoader(ushort const *)
0x180005ef0  mov     ebx, eax
0x180005ef2  test    eax, eax
0x180005ef4  jz      loc_180005E2C
0x180005efa  js      loc_180006109
0x180005f00  mov     rax, [rdi+138h]
0x180005f07  lea     rcx, [rsp+400h+var_3A8]
0x180005f0c  mov     rdx, [rax+30h]
0x180005f10  test    rdx, rdx
0x180005f13  jz      short loc_180005F1D
0x180005f15  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180005f1b  jmp     short loc_180005F2A
0x180005f1d  lea     rdx, aAspnetConfig; "\\Aspnet.config"
0x180005f24  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180005f2a  mov     ebx, eax
0x180005f2c  test    eax, eax
0x180005f2e  js      loc_180005E34
0x180005f34  call    ?Initialize@CLR_HOSTING@@SAJXZ; CLR_HOSTING::Initialize(void)
0x180005f39  mov     ebx, eax
0x180005f3b  test    eax, eax
0x180005f3d  jns     short loc_180005F82
0x180005f3f  test    byte ptr cs:g_dwDebugFlags, 3
0x180005f46  jz      loc_180005E34
0x180005f4c  mov     rcx, cs:g_pDebug
0x180005f53  lea     r9, aW3wpHostPreloa; "W3WP_HOST::PreloadClr"
0x180005f5a  mov     dword ptr [rsp+400h+var_3D8], eax
0x180005f5e  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180005f65  lea     rax, aFailedToInitia_2; "Failed to initialize the CLR hosting li"...
0x180005f6c  mov     r8d, 0B74h
0x180005f72  mov     [rsp+400h+var_3E0], rax
0x180005f77  call    cs:__imp_PuDbgPrint
0x180005f7d  jmp     loc_180005E34
0x180005f82  cmp     [rbp+300h+FindFileData.cFileName+2], 32h ; '2'
0x180005f87  lea     rcx, [rsp+400h+var_3A8]
0x180005f8c  mov     eax, 22016h
0x180005f91  mov     esi, 16h
0x180005f96  cmovnb  esi, eax
0x180005f99  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180005f9f  mov     rcx, rax; lpFileName
0x180005fa2  call    cs:__imp_GetFileAttributesW
0x180005fa8  cmp     eax, 0FFFFFFFFh
0x180005fab  jz      short loc_18000601B
0x180005fad  cmp     [rbp+300h+FindFileData.cFileName+2], 32h ; '2'
0x180005fb2  lea     rax, CLSID_CorRuntimeHost
0x180005fb9  lea     rbx, CLSID_CLRRuntimeHost
0x180005fc0  lea     rcx, [rsp+400h+var_3A8]
0x180005fc5  cmovb   rbx, rax
0x180005fc9  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180005fcf  mov     r8, rax
0x180005fd2  mov     rax, cs:?s_pFnCoreBindToRuntimeHost@CLR_HOSTING@@0P6AJPEBG00PEAXKAEBU_GUID@@2PEAPEAX@ZEA; long (*CLR_HOSTING::s_pFnCoreBindToRuntimeHost)(ushort const *,ushort const *,ushort const *,void *,ulong,_GUID const &,_GUID const &,void * *)
0x180005fd9  test    rax, rax
0x180005fdc  jz      loc_1800060C5
0x180005fe2  lea     rcx, [rdi+130h]
0x180005fe9  xor     r9d, r9d
0x180005fec  mov     [rsp+400h+var_3C8], rcx
0x180005ff1  lea     rdx, aSvr; "svr"
0x180005ff8  lea     rcx, IID_IUnknown
0x180005fff  mov     [rsp+400h+var_3D0], rcx
0x180006004  lea     rcx, [rbp+300h+FindFileData.cFileName]
0x180006008  mov     [rsp+400h+var_3D8], rbx
0x18000600d  mov     dword ptr [rsp+400h+var_3E0], esi
0x180006011  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006016  jmp     loc_1800060C1
0x18000601b  mov     rax, [rdi+138h]
0x180006022  cmp     [rax+30h], r14
0x180006026  jz      short loc_180006070
0x180006028  call    cs:__imp_GetLastError
0x18000602e  mov     edx, eax
0x180006030  test    eax, eax
0x180006032  jle     short loc_18000603D
0x180006034  movzx   edx, ax
0x180006037  or      edx, 80070000h
0x18000603d  mov     rax, [rdi+138h]
0x180006044  lea     r9, [rsp+400h+var_3B0]
0x180006049  mov     [rsp+400h+var_3B0], r14
0x18000604e  mov     r8d, 1
0x180006054  mov     dword ptr [rsp+400h+var_3E0], edx
0x180006058  mov     edx, 800008FCh
0x18000605d  mov     rcx, [rax+30h]
0x180006061  mov     [rsp+400h+var_3B0], rcx
0x180006066  lea     rcx, [rdi+50h]
0x18000606a  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z; EVENT_LOG::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x180006070  cmp     [rbp+300h+FindFileData.cFileName+2], 32h ; '2'
0x180006075  lea     rax, CLSID_CorRuntimeHost
0x18000607c  lea     rbx, CLSID_CLRRuntimeHost
0x180006083  cmovb   rbx, rax
0x180006087  mov     rax, cs:?s_pFnCoreBindToRuntimeEx@CLR_HOSTING@@0P6AJPEBG0KAEBU_GUID@@1PEAPEAX@ZEA; long (*CLR_HOSTING::s_pFnCoreBindToRuntimeEx)(ushort const *,ushort const *,ulong,_GUID const &,_GUID const &,void * *)
0x18000608e  test    rax, rax
0x180006091  jz      short loc_1800060C5
0x180006093  lea     rcx, [rdi+130h]
0x18000609a  mov     r9, rbx
0x18000609d  mov     [rsp+400h+var_3D8], rcx
0x1800060a2  lea     rdx, aSvr; "svr"
0x1800060a9  lea     rcx, IID_IUnknown
0x1800060b0  mov     r8d, esi
0x1800060b3  mov     [rsp+400h+var_3E0], rcx
0x1800060b8  lea     rcx, [rbp+300h+FindFileData.cFileName]
0x1800060bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060c1  mov     ebx, eax
0x1800060c3  jmp     short loc_1800060CA
0x1800060c5  mov     ebx, 80070032h
0x1800060ca  cmp     ebx, 80070032h
0x1800060d0  jnz     loc_180005E2C
0x1800060d6  mov     ebx, r14d
0x1800060d9  jmp     short loc_180006109
0x1800060db  mov     rax, [rdi+138h]
0x1800060e2  mov     rax, [rax+28h]
0x1800060e6  mov     r8d, 1
0x1800060ec  mov     [rsp+400h+var_3B0], rax
0x1800060f1  lea     rcx, [rdi+50h]
0x1800060f5  mov     dword ptr [rsp+400h+var_3E0], ebx
0x1800060f9  lea     r9, [rsp+400h+var_3B0]
0x1800060fe  mov     edx, 0C00008F6h
0x180006103  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z; EVENT_LOG::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x180006109  lea     rcx, [rsp+400h+var_3A8]
0x18000610e  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180006114  mov     eax, ebx
0x180006116  mov     rcx, [rbp+300h+var_20]
0x18000611d  xor     rcx, rsp; StackCookie
0x180006120  call    __security_check_cookie
0x180006125  lea     r11, [rsp+400h+var_10]
0x18000612d  mov     rbx, [r11+28h]
0x180006131  mov     rsi, [r11+30h]
0x180006135  mov     rsp, r11
0x180006138  pop     r14
0x18000613a  pop     rdi
0x18000613b  pop     rbp
0x18000613c  retn
```
