# W3WP_HOST::PreloadClr(void)

- ea: `0x1800062bc`
- end: `0x18000674e`
- name: `?PreloadClr@W3WP_HOST@@QEAAJXZ`
- size: `1170`
- prototype: `__int64 __fastcall(W3WP_HOST *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18000561c`

## callees

- `0x180003b18`
- `0x18000453c`
- `0x1800062bc`
- `0x1800076cc`
- `0x18000d0ec`
- `0x18000d2be`
- `0x18000d2f0`
- `0x18000e010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180006418`
- `msvcrt!wcsrchr` at `0x180006418`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800063b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006620`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800063b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006620`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800063f0`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800063f0`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000639f`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000639f`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000658e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000658e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000638c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180006406`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000642c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180006476`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800064ad`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000657f`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800065bb`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000638c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180006406`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000642c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180006476`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800064ad`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000657f`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800065bb`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180006357`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180006375`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000645b`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800064fe`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180006357`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180006375`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000645b`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800064fe`
- `iisutil!PuDbgPrint` at `0x180006557`
- `iisutil!PuDbgPrint` at `0x180006557`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x180006668`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x180006707`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x180006668`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x180006707`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180006313`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180006313`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800064e9`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800064e9`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x180006446`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x180006446`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180006718`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180006718`

## string_xrefs

- `0x18000653e`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`
- `0x1800064f7`: `\Aspnet.config`

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
  int v16; // eax
  unsigned int v17; // esi
  const WCHAR *v18; // rax
  GUID *v19; // rbx
  const unsigned __int16 *v20; // r8
  int v21; // eax
  signed int v22; // eax
  unsigned int v23; // edx
  __int64 v24; // rax
  GUID *v25; // rbx
  WCHAR *v27; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v28[56]; // [rsp+58h] [rbp-A8h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v30[128]; // [rsp+2E0h] [rbp+1E0h] BYREF

  memset_0(v30, 0, sizeof(v30));
  STRU::STRU((STRU *)v28, v30, 0x80u);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FrameworkInstallationPath = W3WP_HOST::GetFrameworkInstallationPath(v2, (struct STRU *)v28);
  if ( FrameworkInstallationPath >= 0 )
  {
    FrameworkInstallationPath = STRU::Append((STRU *)v28, *(const unsigned __int16 **)(*((_QWORD *)this + 39) + 40LL));
    if ( FrameworkInstallationPath >= 0 )
    {
      FrameworkInstallationPath = STRU::Append((STRU *)v28, L"*");
      if ( FrameworkInstallationPath >= 0 )
      {
        Str = STRU::QueryStr((STRU *)v28);
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
        v8 = STRU::QueryStr((STRU *)v28);
        v9 = wcsrchr(v8, 0x5Cu);
        v10 = STRU::QueryStr((STRU *)v28);
        STRU::SetLen((STRU *)v28, v9 - v10 + 1);
        FrameworkInstallationPath = STRU::Append((STRU *)v28, FindFileData.cFileName);
        if ( FrameworkInstallationPath >= 0 )
        {
          v11 = STRU::QueryStr((STRU *)v28);
          FrameworkInstallationPath = SMALL_STRU::Copy((W3WP_HOST *)((char *)this + 1600), v11);
          if ( FrameworkInstallationPath >= 0 )
          {
            if ( !*(_DWORD *)(*((_QWORD *)this + 39) + 88LL) )
            {
              v12 = STRU::QueryStr((STRU *)v28);
              v13 = W3WP_HOST::TryPreloadClrViaHelperLoader(this, v12);
              FrameworkInstallationPath = v13;
              if ( !v13 )
                goto LABEL_7;
              if ( v13 < 0 )
                goto LABEL_43;
            }
            v14 = *(const unsigned __int16 **)(*((_QWORD *)this + 39) + 48LL);
            v15 = v14 ? STRU::Copy((STRU *)v28, v14) : STRU::Append((STRU *)v28, L"\\Aspnet.config");
            FrameworkInstallationPath = v15;
            if ( v15 >= 0 )
            {
              v16 = CLR_HOSTING::Initialize();
              FrameworkInstallationPath = v16;
              if ( v16 < 0 )
              {
                if ( (g_dwDebugFlags & 3) != 0 )
                  PuDbgPrint(
                    g_pDebug,
                    "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
                    2932,
                    "W3WP_HOST::PreloadClr",
                    "Failed to initialize the CLR hosting library hr = %x\n",
                    v16);
                goto LABEL_8;
              }
              v17 = 22;
              if ( FindFileData.cFileName[1] >= 0x32u )
                v17 = 139286;
              v18 = STRU::QueryStr((STRU *)v28);
              if ( GetFileAttributesW(v18) == -1 )
              {
                if ( *(_QWORD *)(*((_QWORD *)this + 39) + 48LL) )
                {
                  v22 = GetLastError();
                  v23 = v22;
                  if ( v22 > 0 )
                    v23 = (unsigned __int16)v22 | 0x80070000;
                  v24 = *((_QWORD *)this + 39);
                  v27 = 0;
                  v27 = *(WCHAR **)(v24 + 48);
                  EVENT_LOG::LogEvent(
                    (W3WP_HOST *)((char *)this + 80),
                    0x800008FC,
                    1u,
                    (const unsigned __int16 **const)&v27,
                    v23);
                }
                v25 = &CLSID_CLRRuntimeHost;
                if ( FindFileData.cFileName[1] < 0x32u )
                  v25 = &CLSID_CorRuntimeHost;
                if ( CLR_HOSTING::s_pFnCoreBindToRuntimeEx )
                {
                  v21 = CLR_HOSTING::s_pFnCoreBindToRuntimeEx(
                          FindFileData.cFileName,
                          L"svr",
                          v17,
                          v25,
                          &IID_IUnknown,
                          (void **)this + 38);
                  goto LABEL_37;
                }
              }
              else
              {
                v19 = &CLSID_CLRRuntimeHost;
                if ( FindFileData.cFileName[1] < 0x32u )
                  v19 = &CLSID_CorRuntimeHost;
                v20 = STRU::QueryStr((STRU *)v28);
                if ( CLR_HOSTING::s_pFnCoreBindToRuntimeHost )
                {
                  v21 = CLR_HOSTING::s_pFnCoreBindToRuntimeHost(
                          FindFileData.cFileName,
                          L"svr",
                          v20,
                          0,
                          v17,
                          v19,
                          &IID_IUnknown,
                          (void **)this + 38);
LABEL_37:
                  FrameworkInstallationPath = v21;
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
  v27 = 0;
  if ( FindFileData.cFileName[0] )
    cFileName = FindFileData.cFileName;
  else
    cFileName = *(WCHAR **)(*((_QWORD *)this + 39) + 40LL);
  v27 = cFileName;
  EVENT_LOG::LogEvent(
    (W3WP_HOST *)((char *)this + 80),
    0xC00008F6,
    1u,
    (const unsigned __int16 **const)&v27,
    FrameworkInstallationPath);
LABEL_43:
  STRU::~STRU((STRU *)v28);
  return (unsigned int)FrameworkInstallationPath;
}

```

## disassembly

```asm
0x1800062bc  mov     [rsp-8+arg_8], rbx
0x1800062c1  mov     [rsp-8+arg_10], rsi
0x1800062c6  push    rbp
0x1800062c7  push    rdi
0x1800062c8  push    r14
0x1800062ca  lea     rbp, [rsp-2F0h]
0x1800062d2  sub     rsp, 3F0h
0x1800062d9  mov     rax, cs:__security_cookie
0x1800062e0  xor     rax, rsp
0x1800062e3  mov     [rbp+300h+var_20], rax
0x1800062ea  mov     rdi, rcx
0x1800062ed  xor     edx, edx; Val
0x1800062ef  lea     rcx, [rbp+300h+var_120]; void *
0x1800062f6  mov     r8d, 100h; Size
0x1800062fc  call    memset_0
0x180006301  mov     r8d, 80h
0x180006307  lea     rdx, [rbp+300h+var_120]
0x18000630e  lea     rcx, [rsp+400h+var_3A8]
0x180006313  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000631a  nop     dword ptr [rax+rax+00h]
0x18000631f  xor     edx, edx; Val
0x180006321  lea     rcx, [rbp+300h+FindFileData]; void *
0x180006325  mov     r8d, 250h; Size
0x18000632b  call    memset_0
0x180006330  lea     rdx, [rsp+400h+var_3A8]; struct STRU *
0x180006335  call    ?GetFrameworkInstallationPath@W3WP_HOST@@AEAAJPEAVSTRU@@@Z; W3WP_HOST::GetFrameworkInstallationPath(STRU *)
0x18000633a  xor     r14d, r14d
0x18000633d  mov     ebx, eax
0x18000633f  test    eax, eax
0x180006341  js      loc_1800063D4
0x180006347  mov     rdx, [rdi+138h]
0x18000634e  lea     rcx, [rsp+400h+var_3A8]
0x180006353  mov     rdx, [rdx+28h]
0x180006357  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000635e  nop     dword ptr [rax+rax+00h]
0x180006363  mov     ebx, eax
0x180006365  test    eax, eax
0x180006367  js      short loc_1800063D4
0x180006369  lea     rdx, asc_180010904; "*"
0x180006370  lea     rcx, [rsp+400h+var_3A8]
0x180006375  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000637c  nop     dword ptr [rax+rax+00h]
0x180006381  mov     ebx, eax
0x180006383  test    eax, eax
0x180006385  js      short loc_1800063D4
0x180006387  lea     rcx, [rsp+400h+var_3A8]
0x18000638c  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180006393  nop     dword ptr [rax+rax+00h]
0x180006398  mov     rcx, rax; lpFileName
0x18000639b  lea     rdx, [rbp+300h+FindFileData]; lpFindFileData
0x18000639f  call    cs:__imp_FindFirstFileW
0x1800063a6  nop     dword ptr [rax+rax+00h]
0x1800063ab  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800063af  jnz     short loc_1800063ED
0x1800063b1  call    cs:__imp_GetLastError
0x1800063b8  nop     dword ptr [rax+rax+00h]
0x1800063bd  mov     ebx, eax
0x1800063bf  test    eax, eax
0x1800063c1  jle     short loc_1800063CC
0x1800063c3  movzx   ebx, ax
0x1800063c6  or      ebx, 80070000h
0x1800063cc  test    ebx, ebx
0x1800063ce  jns     loc_180006713
0x1800063d4  mov     [rsp+400h+var_3B0], r14
0x1800063d9  cmp     [rbp+300h+FindFileData.cFileName], r14w
0x1800063de  jz      loc_1800066DF
0x1800063e4  lea     rax, [rbp+300h+FindFileData.cFileName]
0x1800063e8  jmp     loc_1800066EA
0x1800063ed  mov     rcx, rax; hFindFile
0x1800063f0  call    cs:__imp_FindClose
0x1800063f7  nop     dword ptr [rax+rax+00h]
0x1800063fc  lea     rcx, [rsp+400h+var_3A8]
0x180006401  mov     ebx, 5Ch ; '\'
0x180006406  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000640d  nop     dword ptr [rax+rax+00h]
0x180006412  mov     rcx, rax; Str
0x180006415  movzx   edx, bx; Ch
0x180006418  call    cs:__imp_wcsrchr
0x18000641f  nop     dword ptr [rax+rax+00h]
0x180006424  lea     rcx, [rsp+400h+var_3A8]
0x180006429  mov     rbx, rax
0x18000642c  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180006433  nop     dword ptr [rax+rax+00h]
0x180006438  sub     rbx, rax
0x18000643b  lea     rcx, [rsp+400h+var_3A8]
0x180006440  sar     rbx, 1
0x180006443  lea     edx, [rbx+1]
0x180006446  call    cs:__imp_?SetLen@STRU@@QEAA_NK@Z; STRU::SetLen(ulong)
0x18000644d  nop     dword ptr [rax+rax+00h]
0x180006452  lea     rdx, [rbp+300h+FindFileData.cFileName]
0x180006456  lea     rcx, [rsp+400h+var_3A8]
0x18000645b  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180006462  nop     dword ptr [rax+rax+00h]
0x180006467  mov     ebx, eax
0x180006469  test    eax, eax
0x18000646b  js      loc_1800063D4
0x180006471  lea     rcx, [rsp+400h+var_3A8]
0x180006476  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000647d  nop     dword ptr [rax+rax+00h]
0x180006482  mov     rdx, rax; unsigned __int16 *
0x180006485  lea     rcx, [rdi+640h]; this
0x18000648c  call    ?Copy@SMALL_STRU@@QEAAJPEBG@Z; SMALL_STRU::Copy(ushort const *)
0x180006491  mov     ebx, eax
0x180006493  test    eax, eax
0x180006495  js      loc_1800063D4
0x18000649b  mov     rax, [rdi+138h]
0x1800064a2  cmp     [rax+58h], r14d
0x1800064a6  jnz     short loc_1800064D4
0x1800064a8  lea     rcx, [rsp+400h+var_3A8]
0x1800064ad  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800064b4  nop     dword ptr [rax+rax+00h]
0x1800064b9  mov     rdx, rax; unsigned __int16 *
0x1800064bc  mov     rcx, rdi; this
0x1800064bf  call    ?TryPreloadClrViaHelperLoader@W3WP_HOST@@QEAAJPEBG@Z; W3WP_HOST::TryPreloadClrViaHelperLoader(ushort const *)
0x1800064c4  mov     ebx, eax
0x1800064c6  test    eax, eax
0x1800064c8  jz      loc_1800063CC
0x1800064ce  js      loc_180006713
0x1800064d4  mov     rax, [rdi+138h]
0x1800064db  lea     rcx, [rsp+400h+var_3A8]
0x1800064e0  mov     rdx, [rax+30h]
0x1800064e4  test    rdx, rdx
0x1800064e7  jz      short loc_1800064F7
0x1800064e9  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800064f0  nop     dword ptr [rax+rax+00h]
0x1800064f5  jmp     short loc_18000650A
0x1800064f7  lea     rdx, aAspnetConfig; "\\Aspnet.config"
0x1800064fe  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180006505  nop     dword ptr [rax+rax+00h]
0x18000650a  mov     ebx, eax
0x18000650c  test    eax, eax
0x18000650e  js      loc_1800063D4
0x180006514  call    ?Initialize@CLR_HOSTING@@SAJXZ; CLR_HOSTING::Initialize(void)
0x180006519  mov     ebx, eax
0x18000651b  test    eax, eax
0x18000651d  jns     short loc_180006568
0x18000651f  test    byte ptr cs:g_dwDebugFlags, 3
0x180006526  jz      loc_1800063D4
0x18000652c  mov     rcx, cs:g_pDebug
0x180006533  lea     r9, aW3wpHostPreloa; "W3WP_HOST::PreloadClr"
0x18000653a  mov     dword ptr [rsp+400h+var_3D8], eax
0x18000653e  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180006545  lea     rax, aFailedToInitia_2; "Failed to initialize the CLR hosting li"...
0x18000654c  mov     r8d, 0B74h
0x180006552  mov     [rsp+400h+var_3E0], rax
0x180006557  call    cs:__imp_PuDbgPrint
0x18000655e  nop     dword ptr [rax+rax+00h]
0x180006563  jmp     loc_1800063D4
0x180006568  cmp     [rbp+300h+FindFileData.cFileName+2], 32h ; '2'
0x18000656d  lea     rcx, [rsp+400h+var_3A8]
0x180006572  mov     eax, 22016h
0x180006577  mov     esi, 16h
0x18000657c  cmovnb  esi, eax
0x18000657f  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180006586  nop     dword ptr [rax+rax+00h]
0x18000658b  mov     rcx, rax; lpFileName
0x18000658e  call    cs:__imp_GetFileAttributesW
0x180006595  nop     dword ptr [rax+rax+00h]
0x18000659a  cmp     eax, 0FFFFFFFFh
0x18000659d  jz      short loc_180006613
0x18000659f  cmp     [rbp+300h+FindFileData.cFileName+2], 32h ; '2'
0x1800065a4  lea     rax, CLSID_CorRuntimeHost
0x1800065ab  lea     rbx, CLSID_CLRRuntimeHost
0x1800065b2  lea     rcx, [rsp+400h+var_3A8]
0x1800065b7  cmovb   rbx, rax
0x1800065bb  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800065c2  nop     dword ptr [rax+rax+00h]
0x1800065c7  mov     r8, rax
0x1800065ca  mov     rax, cs:?s_pFnCoreBindToRuntimeHost@CLR_HOSTING@@0P6AJPEBG00PEAXKAEBU_GUID@@2PEAPEAX@ZEA; long (*CLR_HOSTING::s_pFnCoreBindToRuntimeHost)(ushort const *,ushort const *,ushort const *,void *,ulong,_GUID const &,_GUID const &,void * *)
0x1800065d1  test    rax, rax
0x1800065d4  jz      loc_1800066C9
0x1800065da  lea     rcx, [rdi+130h]
0x1800065e1  xor     r9d, r9d
0x1800065e4  mov     [rsp+400h+var_3C8], rcx
0x1800065e9  lea     rdx, aSvr; "svr"
0x1800065f0  lea     rcx, IID_IUnknown
0x1800065f7  mov     [rsp+400h+var_3D0], rcx
0x1800065fc  lea     rcx, [rbp+300h+FindFileData.cFileName]
0x180006600  mov     [rsp+400h+var_3D8], rbx
0x180006605  mov     dword ptr [rsp+400h+var_3E0], esi
0x180006609  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000660e  jmp     loc_1800066C5
0x180006613  mov     rax, [rdi+138h]
0x18000661a  cmp     [rax+30h], r14
0x18000661e  jz      short loc_180006674
0x180006620  call    cs:__imp_GetLastError
0x180006627  nop     dword ptr [rax+rax+00h]
0x18000662c  mov     edx, eax
0x18000662e  test    eax, eax
0x180006630  jle     short loc_18000663B
0x180006632  movzx   edx, ax
0x180006635  or      edx, 80070000h
0x18000663b  mov     rax, [rdi+138h]
0x180006642  lea     r9, [rsp+400h+var_3B0]
0x180006647  mov     [rsp+400h+var_3B0], r14
0x18000664c  mov     r8d, 1
0x180006652  mov     dword ptr [rsp+400h+var_3E0], edx
0x180006656  mov     edx, 800008FCh
0x18000665b  mov     rcx, [rax+30h]
0x18000665f  mov     [rsp+400h+var_3B0], rcx
0x180006664  lea     rcx, [rdi+50h]
0x180006668  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z; EVENT_LOG::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x18000666f  nop     dword ptr [rax+rax+00h]
0x180006674  cmp     [rbp+300h+FindFileData.cFileName+2], 32h ; '2'
0x180006679  lea     rax, CLSID_CorRuntimeHost
0x180006680  lea     rbx, CLSID_CLRRuntimeHost
0x180006687  cmovb   rbx, rax
0x18000668b  mov     rax, cs:?s_pFnCoreBindToRuntimeEx@CLR_HOSTING@@0P6AJPEBG0KAEBU_GUID@@1PEAPEAX@ZEA; long (*CLR_HOSTING::s_pFnCoreBindToRuntimeEx)(ushort const *,ushort const *,ulong,_GUID const &,_GUID const &,void * *)
0x180006692  test    rax, rax
0x180006695  jz      short loc_1800066C9
0x180006697  lea     rcx, [rdi+130h]
0x18000669e  mov     r9, rbx
0x1800066a1  mov     [rsp+400h+var_3D8], rcx
0x1800066a6  lea     rdx, aSvr; "svr"
0x1800066ad  lea     rcx, IID_IUnknown
0x1800066b4  mov     r8d, esi
0x1800066b7  mov     [rsp+400h+var_3E0], rcx
0x1800066bc  lea     rcx, [rbp+300h+FindFileData.cFileName]
0x1800066c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066c5  mov     ebx, eax
0x1800066c7  jmp     short loc_1800066CE
0x1800066c9  mov     ebx, 80070032h
0x1800066ce  cmp     ebx, 80070032h
0x1800066d4  jnz     loc_1800063CC
0x1800066da  mov     ebx, r14d
0x1800066dd  jmp     short loc_180006713
0x1800066df  mov     rax, [rdi+138h]
0x1800066e6  mov     rax, [rax+28h]
0x1800066ea  mov     r8d, 1
0x1800066f0  mov     [rsp+400h+var_3B0], rax
0x1800066f5  lea     rcx, [rdi+50h]
0x1800066f9  mov     dword ptr [rsp+400h+var_3E0], ebx
0x1800066fd  lea     r9, [rsp+400h+var_3B0]
0x180006702  mov     edx, 0C00008F6h
0x180006707  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z; EVENT_LOG::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x18000670e  nop     dword ptr [rax+rax+00h]
0x180006713  lea     rcx, [rsp+400h+var_3A8]
0x180006718  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000671f  nop     dword ptr [rax+rax+00h]
0x180006724  mov     eax, ebx
0x180006726  mov     rcx, [rbp+300h+var_20]
0x18000672d  xor     rcx, rsp; StackCookie
0x180006730  call    __security_check_cookie
0x180006735  lea     r11, [rsp+400h+var_10]
0x18000673d  mov     rbx, [r11+28h]
0x180006741  mov     rsi, [r11+30h]
0x180006745  mov     rsp, r11
0x180006748  pop     r14
0x18000674a  pop     rdi
0x18000674b  pop     rbp
0x18000674c  retn
```
