# CPersistedTableRegistryStore::GetItemStream(ushort const *,int,ulong,IStream * *)

- ea: `0x1801bcb80`
- end: `0x1801bcfbb`
- name: `?GetItemStream@CPersistedTableRegistryStore@@UEAAJPEBGHKPEAPEAUIStream@@@Z`
- size: `1083`
- prototype: `int(CPersistedTableRegistryStore *__hidden this, const unsigned __int16 *, int, unsigned int, struct IStream **)`
- caller_count: `2`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x1801bbc30`
- `0x1801bca10`

## callees

- `0x180038f50`
- `0x18007bbf0`
- `0x18007c1c0`
- `0x18007fd1c`
- `0x1800b5d60`
- `0x1801bcb80`
- `0x1801bd2a8`
- `0x1801bdab8`
- `0x1801bdf98`
- `0x1801bdfd4`
- `0x1801bdff4`
- `0x1801bf820`
- `0x1801ff4d0`
- `0x180370e34`
- `0x1803b1f60`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1801bce2e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1801bce2e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801bcd21`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801bcd2f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801bcd87`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801bcdbc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801bcd21`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801bcd2f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801bcd87`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801bcdbc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801bcc87`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801bcc87`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801bcf13`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801bcf13`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1801bcdfb`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1801bcdfb`
- `api-ms-win-shcore-stream-l1-1-0!SHOpenRegStream2W` at `0x1801bccc1`
- `api-ms-win-shcore-stream-l1-1-0!SHOpenRegStream2W` at `0x1801bccc1`

## string_xrefs

- `0x1801bce22`: `LastUpdatedTime`
- `0x1801bcce8`: `onecoreuap\shell\windows.storage\persistedtableregistrystore.cpp`
- `0x1801bcdd7`: `onecoreuap\shell\windows.storage\persistedtableregistrystore.cpp`
- `0x1801bcea2`: `onecoreuap\shell\windows.storage\persistedtableregistrystore.cpp`
- `0x1801bcf31`: `onecoreuap\shell\windows.storage\persistedtableregistrystore.cpp`
- `0x1801bcf73`: `onecoreuap\shell\windows.storage\persistedtableregistrystore.cpp`
- `0x1801bcfa4`: `onecoreuap\shell\windows.storage\persistedtableregistrystore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CPersistedTableRegistryStore::GetItemStream(
        CPersistedTableRegistryStore *this,
        const unsigned __int16 *a2,
        int a3,
        DWORD a4,
        struct IStream **a5)
{
  unsigned int v9; // edi
  int TableRegKey; // eax
  signed int BOOLWithREGSAM; // ebx
  void *v12; // rax
  int v13; // eax
  LSTATUS v14; // eax
  void *v15; // rdx
  IStream *v16; // rdi
  LSTATUS v18; // eax
  DWORD IsVolatile; // ebx
  unsigned int v20; // eax
  int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  int phkResultb; // [rsp+20h] [rbp-E0h]
  int phkResultc; // [rsp+20h] [rbp-E0h]
  HANDLE Token; // [rsp+50h] [rbp-B0h] BYREF
  int v26; // [rsp+58h] [rbp-A8h] BYREF
  struct IStream **v27; // [rsp+60h] [rbp-A0h]
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  HKEY hkey; // [rsp+70h] [rbp-90h] BYREF
  BYTE Data[8]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v31[192]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  v27 = a5;
  WinRTStorageTelemetry::WatchCurrentThread(v31, "GetItemStream", 0);
  *a5 = 0;
  hKey = 0;
  if ( (a4 & 3) != 0 || (v9 = 131097, a3) )
    v9 = 131103;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  TableRegKey = CPersistedTableRegistryStore::_GetTableRegKey(this, v9, &hKey);
  BOOLWithREGSAM = TableRegKey;
  if ( TableRegKey < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEC,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\persistedtableregistrystore.cpp",
      (const char *)(unsigned int)TableRegKey,
      phkResult);
LABEL_12:
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_15;
  }
  Token = (HANDLE)-1LL;
  v12 = (void *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 120LL))(*((_QWORD *)this + 3));
  v13 = wil::impersonate_token_nothrow(v12);
  BOOLWithREGSAM = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEF,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\persistedtableregistrystore.cpp",
      (const char *)(unsigned int)v13,
      phkResult);
    goto LABEL_12;
  }
  hkey = 0;
  if ( (a4 & 3) != 0 )
  {
    IsVolatile = (unsigned __int8)PersistedTableTraits::GetIsVolatile(*((unsigned int *)this + 11));
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hkey,
      0);
    v20 = RegCreateKeyExW(hKey, a2, 0, 0, IsVolatile, v9, 0, &hkey, 0);
    if ( v20 )
    {
      BOOLWithREGSAM = wil::details::in1diag3::Return_Win32(
                         retaddr,
                         (void *)0xF6,
                         (unsigned int)"onecoreuap\\shell\\windows.storage\\persistedtableregistrystore.cpp",
                         (const char *)v20,
                         phkResulta);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&Token);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      goto LABEL_15;
    }
  }
  else
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hkey,
      0);
    v14 = RegOpenKeyExW(hKey, a2, 0, v9, &hkey);
    BOOLWithREGSAM = CheckAndReportError(v14 != 0 ? 0x80070057 : 0, 0xC623u, a2);
    if ( BOOLWithREGSAM < 0 )
      goto LABEL_10;
  }
  v16 = SHOpenRegStream2W(hkey, 0, L"Link", a4);
  if ( !v16 )
  {
    BOOLWithREGSAM = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x101,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\persistedtableregistrystore.cpp",
      (const char *)0x8007000ELL,
      phkResulta);
    goto LABEL_10;
  }
  if ( a3 )
  {
    *(_QWORD *)Data = 0;
    GetSystemTimePreciseAsFileTime(Data);
    v18 = RegSetValueExW(hkey, L"LastUpdatedTime", 0, 3u, Data, 8u);
    BOOLWithREGSAM = v18;
    if ( v18 > 0 )
      BOOLWithREGSAM = (unsigned __int16)v18 | 0x80070000;
    if ( BOOLWithREGSAM < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x109,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\persistedtableregistrystore.cpp",
        (const char *)(unsigned int)BOOLWithREGSAM,
        phkResultb);
      (*(void (__fastcall **)(IStream *))(*(_QWORD *)v16 + 16LL))(v16);
    }
    else
    {
      v26 = 0;
      BOOLWithREGSAM = SHRegGetBOOLWithREGSAM(hKey, a2, L"Roamable", 0, &v26);
      if ( (int)(BOOLWithREGSAM + 0x80000000) < 0 || BOOLWithREGSAM == -2147024894 )
        goto LABEL_17;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x10D,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\persistedtableregistrystore.cpp",
        (const char *)(unsigned int)BOOLWithREGSAM,
        phkResultc);
      (*(void (__fastcall **)(IStream *))(*(_QWORD *)v16 + 16LL))(v16);
    }
LABEL_10:
    if ( hkey )
      RegCloseKey(hkey);
    goto LABEL_12;
  }
LABEL_17:
  *v27 = v16;
  if ( hkey )
    RegCloseKey(hkey);
  if ( Token != (HANDLE)-1LL )
    wil::details::RevertImpersonateToken(Token, v15);
  if ( hKey )
    RegCloseKey(hKey);
  BOOLWithREGSAM = 0;
LABEL_15:
  StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit((StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit *)v31);
  return (unsigned int)BOOLWithREGSAM;
}

```

## disassembly

```asm
0x1801bcb80  mov     [rsp-8+arg_10], rbx
0x1801bcb85  push    rbp
0x1801bcb86  push    rsi
0x1801bcb87  push    rdi
0x1801bcb88  push    r12
0x1801bcb8a  push    r13
0x1801bcb8c  push    r14
0x1801bcb8e  push    r15
0x1801bcb90  lea     rbp, [rsp-50h]
0x1801bcb95  sub     rsp, 150h
0x1801bcb9c  mov     rax, cs:__security_cookie
0x1801bcba3  xor     rax, rsp
0x1801bcba6  mov     [rbp+80h+var_40], rax
0x1801bcbaa  mov     r13d, r9d
0x1801bcbad  mov     r14d, r8d
0x1801bcbb0  mov     r12, rdx
0x1801bcbb3  mov     r15, rcx
0x1801bcbb6  mov     rbx, [rbp+80h+arg_20]
0x1801bcbbd  mov     [rsp+180h+var_120], rbx
0x1801bcbc2  xor     r8d, r8d
0x1801bcbc5  lea     rdx, aGetitemstream; "GetItemStream"
0x1801bcbcc  lea     rcx, [rbp+80h+var_100]
0x1801bcbd0  call    ?WatchCurrentThread@WinRTStorageTelemetry@@SA?AVActivityThreadWatcherWithCapturedCallerContextReportOnExit@StorageTelemetry@@PEBD_N@Z; WinRTStorageTelemetry::WatchCurrentThread(char const *,bool)
0x1801bcbd5  nop
0x1801bcbd6  mov     qword ptr [rbx], 0
0x1801bcbdd  mov     [rsp+180h+hKey], 0
0x1801bcbe6  mov     esi, r13d
0x1801bcbe9  and     esi, 3
0x1801bcbec  jnz     short loc_1801BCBF8
0x1801bcbee  test    r14d, r14d
0x1801bcbf1  mov     edi, 20019h
0x1801bcbf6  jz      short loc_1801BCBFD
0x1801bcbf8  mov     edi, 2001Fh
0x1801bcbfd  xor     edx, edx
0x1801bcbff  lea     rcx, [rsp+180h+hKey]
0x1801bcc04  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1801bcc09  lea     r8, [rsp+180h+hKey]; HKEY *
0x1801bcc0e  mov     edx, edi; unsigned int
0x1801bcc10  mov     rcx, r15; this
0x1801bcc13  call    ?_GetTableRegKey@CPersistedTableRegistryStore@@AEAAJKPEAPEAUHKEY__@@@Z; CPersistedTableRegistryStore::_GetTableRegKey(ulong,HKEY__ * *)
0x1801bcc18  mov     ebx, eax
0x1801bcc1a  test    eax, eax
0x1801bcc1c  js      loc_1801BCF9A
0x1801bcc22  mov     [rsp+180h+Token], 0FFFFFFFFFFFFFFFFh
0x1801bcc2b  mov     rcx, [r15+18h]
0x1801bcc2f  mov     rax, [rcx]
0x1801bcc32  mov     rax, [rax+78h]
0x1801bcc36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bcc3b  mov     rcx, rax; Token
0x1801bcc3e  lea     rdx, [rsp+180h+Token]
0x1801bcc43  call    ?impersonate_token_nothrow@wil@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@@Z; wil::impersonate_token_nothrow(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>> &)
0x1801bcc48  mov     ebx, eax
0x1801bcc4a  test    eax, eax
0x1801bcc4c  js      loc_1801BCDCD
0x1801bcc52  mov     [rsp+180h+hkey], 0
0x1801bcc5b  test    esi, esi
0x1801bcc5d  jnz     loc_1801BCEC9
0x1801bcc63  xor     edx, edx
0x1801bcc65  lea     rcx, [rsp+180h+hkey]
0x1801bcc6a  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1801bcc6f  lea     rax, [rsp+180h+hkey]
0x1801bcc74  mov     [rsp+180h+phkResult], rax; int
0x1801bcc79  mov     r9d, edi; samDesired
0x1801bcc7c  xor     r8d, r8d; ulOptions
0x1801bcc7f  mov     rdx, r12; lpSubKey
0x1801bcc82  mov     rcx, [rsp+180h+hKey]; hKey
0x1801bcc87  call    cs:__imp_RegOpenKeyExW
0x1801bcc8e  nop     dword ptr [rax+rax+00h]
0x1801bcc93  neg     eax
0x1801bcc95  sbb     ecx, ecx
0x1801bcc97  and     ecx, 80070057h; int
0x1801bcc9d  mov     r8, r12
0x1801bcca0  mov     edx, 0C623h; unsigned int
0x1801bcca5  call    ?CheckAndReportError@@YAJJIZZ; CheckAndReportError(long,uint,...)
0x1801bccaa  mov     ebx, eax
0x1801bccac  test    eax, eax
0x1801bccae  js      short loc_1801BCCFA
0x1801bccb0  mov     r9d, r13d; grfMode
0x1801bccb3  lea     r8, aLink_0; "Link"
0x1801bccba  xor     edx, edx; pszSubkey
0x1801bccbc  mov     rcx, [rsp+180h+hkey]; hkey
0x1801bccc1  call    cs:__imp_SHOpenRegStream2W
0x1801bccc8  nop     dword ptr [rax+rax+00h]
0x1801bcccd  mov     rdi, rax
0x1801bccd0  test    rax, rax
0x1801bccd3  jnz     loc_1801BCD70
0x1801bccd9  mov     rcx, [rbp+88h]; this
0x1801bcce0  mov     ebx, 8007000Eh
0x1801bcce5  mov     r9d, ebx; char *
0x1801bcce8  lea     r8, aOnecoreuapShel_45; "onecoreuap\\shell\\windows.storage\\per"...
0x1801bccef  mov     edx, 101h; void *
0x1801bccf4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801bccf9  nop
0x1801bccfa  mov     rcx, [rsp+180h+hkey]; hKey
0x1801bccff  test    rcx, rcx
0x1801bcd02  jnz     loc_1801BCDBC
0x1801bcd08  mov     rcx, [rsp+180h+Token]; Token
0x1801bcd0d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1801bcd11  jnz     loc_1801BCDB2
0x1801bcd17  mov     rcx, [rsp+180h+hKey]; hKey
0x1801bcd1c  test    rcx, rcx
0x1801bcd1f  jz      short loc_1801BCD3D
0x1801bcd21  call    cs:__imp_RegCloseKey
0x1801bcd28  nop     dword ptr [rax+rax+00h]
0x1801bcd2d  jmp     short loc_1801BCD3D
0x1801bcd2f  call    cs:__imp_RegCloseKey
0x1801bcd36  nop     dword ptr [rax+rax+00h]
0x1801bcd3b  xor     ebx, ebx
0x1801bcd3d  lea     rcx, [rbp+80h+var_100]; this
0x1801bcd41  call    ??1ActivityThreadWatcherWithCapturedCallerContextReportOnExit@StorageTelemetry@@QEAA@XZ; StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit(void)
0x1801bcd46  mov     eax, ebx
0x1801bcd48  mov     rcx, [rbp+80h+var_40]
0x1801bcd4c  xor     rcx, rsp; StackCookie
0x1801bcd4f  call    __security_check_cookie
0x1801bcd54  mov     rbx, [rsp+180h+arg_10]
0x1801bcd5c  add     rsp, 150h
0x1801bcd63  pop     r15
0x1801bcd65  pop     r14
0x1801bcd67  pop     r13
0x1801bcd69  pop     r12
0x1801bcd6b  pop     rdi
0x1801bcd6c  pop     rsi
0x1801bcd6d  pop     rbp
0x1801bcd6e  retn
0x1801bcd70  test    r14d, r14d
0x1801bcd73  jnz     short loc_1801BCDED
0x1801bcd75  mov     rax, [rsp+180h+var_120]
0x1801bcd7a  mov     [rax], rdi
0x1801bcd7d  mov     rcx, [rsp+180h+hkey]; hKey
0x1801bcd82  test    rcx, rcx
0x1801bcd85  jz      short loc_1801BCD94
0x1801bcd87  call    cs:__imp_RegCloseKey
0x1801bcd8e  nop     dword ptr [rax+rax+00h]
0x1801bcd93  nop
0x1801bcd94  mov     rcx, [rsp+180h+Token]; Token
0x1801bcd99  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1801bcd9d  jnz     short loc_1801BCDAB
0x1801bcd9f  mov     rcx, [rsp+180h+hKey]; hKey
0x1801bcda4  test    rcx, rcx
0x1801bcda7  jz      short loc_1801BCD3B
0x1801bcda9  jmp     short loc_1801BCD2F
0x1801bcdab  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x1801bcdb0  jmp     short loc_1801BCD9F
0x1801bcdb2  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x1801bcdb7  jmp     loc_1801BCD17
0x1801bcdbc  call    cs:__imp_RegCloseKey
0x1801bcdc3  nop     dword ptr [rax+rax+00h]
0x1801bcdc8  jmp     loc_1801BCD08
0x1801bcdcd  mov     rcx, [rbp+88h]; this
0x1801bcdd4  mov     r9d, eax; char *
0x1801bcdd7  lea     r8, aOnecoreuapShel_45; "onecoreuap\\shell\\windows.storage\\per"...
0x1801bcdde  mov     edx, 0EFh; void *
0x1801bcde3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801bcde8  jmp     loc_1801BCD08
0x1801bcded  mov     qword ptr [rsp+180h+Data], 0
0x1801bcdf6  lea     rcx, [rsp+180h+Data]
0x1801bcdfb  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x1801bce02  nop     dword ptr [rax+rax+00h]
0x1801bce07  mov     [rsp+180h+cbData], 8; cbData
0x1801bce0f  lea     rax, [rsp+180h+Data]
0x1801bce14  mov     [rsp+180h+phkResult], rax; int
0x1801bce19  mov     r9d, 3; dwType
0x1801bce1f  xor     r8d, r8d; Reserved
0x1801bce22  lea     rdx, aLastupdatedtim; "LastUpdatedTime"
0x1801bce29  mov     rcx, [rsp+180h+hkey]; hKey
0x1801bce2e  call    cs:__imp_RegSetValueExW
0x1801bce35  nop     dword ptr [rax+rax+00h]
0x1801bce3a  mov     ebx, eax
0x1801bce3c  test    eax, eax
0x1801bce3e  jle     short loc_1801BCE49
0x1801bce40  movzx   ebx, ax
0x1801bce43  or      ebx, 80070000h
0x1801bce49  test    ebx, ebx
0x1801bce4b  js      loc_1801BCF69
0x1801bce51  mov     [rsp+180h+var_128], 0
0x1801bce59  lea     rax, [rsp+180h+var_128]
0x1801bce5e  mov     [rsp+180h+phkResult], rax; int
0x1801bce63  xor     r9d, r9d; unsigned int
0x1801bce66  lea     r8, Value; "Roamable"
0x1801bce6d  mov     rdx, r12; unsigned __int16 *
0x1801bce70  mov     rcx, [rsp+180h+hKey]; HKEY
0x1801bce75  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x1801bce7a  mov     ebx, eax
0x1801bce7c  mov     eax, 80000000h
0x1801bce81  lea     ecx, [rbx+rax]
0x1801bce84  test    eax, ecx
0x1801bce86  jnz     loc_1801BCD75
0x1801bce8c  cmp     ebx, 80070002h
0x1801bce92  jz      loc_1801BCD75
0x1801bce98  mov     rcx, [rbp+88h]; this
0x1801bce9f  mov     r9d, ebx; char *
0x1801bcea2  lea     r8, aOnecoreuapShel_45; "onecoreuap\\shell\\windows.storage\\per"...
0x1801bcea9  mov     edx, 10Dh; void *
0x1801bceae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801bceb3  nop
0x1801bceb4  mov     rax, [rdi]
0x1801bceb7  mov     rcx, rdi
0x1801bceba  mov     rax, [rax+10h]
0x1801bcebe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bcec3  nop
0x1801bcec4  jmp     loc_1801BCCFA
0x1801bcec9  mov     ecx, [r15+2Ch]
0x1801bcecd  call    ?GetIsVolatile@PersistedTableTraits@@SA_NW4__MIDL___MIDL_itf_winrtfileapi_0000_0036_0001@@@Z; PersistedTableTraits::GetIsVolatile(__MIDL___MIDL_itf_winrtfileapi_0000_0036_0001)
0x1801bced2  movzx   ebx, al
0x1801bced5  xor     edx, edx
0x1801bced7  lea     rcx, [rsp+180h+hkey]
0x1801bcedc  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1801bcee1  mov     [rsp+180h+lpdwDisposition], 0; lpdwDisposition
0x1801bceea  lea     rax, [rsp+180h+hkey]
0x1801bceef  mov     [rsp+180h+var_148], rax; phkResult
0x1801bcef4  mov     [rsp+180h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1801bcefd  mov     [rsp+180h+cbData], edi; samDesired
0x1801bcf01  mov     dword ptr [rsp+180h+phkResult], ebx; unsigned int
0x1801bcf05  xor     r9d, r9d; lpClass
0x1801bcf08  xor     r8d, r8d; Reserved
0x1801bcf0b  mov     rdx, r12; lpSubKey
0x1801bcf0e  mov     rcx, [rsp+180h+hKey]; hKey
0x1801bcf13  call    cs:__imp_RegCreateKeyExW
0x1801bcf1a  nop     dword ptr [rax+rax+00h]
0x1801bcf1f  test    eax, eax
0x1801bcf21  jz      loc_1801BCCB0
0x1801bcf27  mov     rcx, [rbp+88h]; this
0x1801bcf2e  mov     r9d, eax; char *
0x1801bcf31  lea     r8, aOnecoreuapShel_45; "onecoreuap\\shell\\windows.storage\\per"...
0x1801bcf38  mov     edx, 0F6h; void *
0x1801bcf3d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801bcf42  mov     ebx, eax
0x1801bcf44  lea     rcx, [rsp+180h+hkey]
0x1801bcf49  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801bcf4e  nop
0x1801bcf4f  lea     rcx, [rsp+180h+Token]
0x1801bcf54  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x1801bcf59  nop
0x1801bcf5a  lea     rcx, [rsp+180h+hKey]
0x1801bcf5f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801bcf64  jmp     loc_1801BCD3D
0x1801bcf69  mov     rcx, [rbp+88h]; this
0x1801bcf70  mov     r9d, ebx; char *
0x1801bcf73  lea     r8, aOnecoreuapShel_45; "onecoreuap\\shell\\windows.storage\\per"...
0x1801bcf7a  mov     edx, 109h; void *
0x1801bcf7f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801bcf84  nop
0x1801bcf85  mov     rax, [rdi]
0x1801bcf88  mov     rcx, rdi
0x1801bcf8b  mov     rax, [rax+10h]
0x1801bcf8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bcf94  nop
0x1801bcf95  jmp     loc_1801BCCFA
0x1801bcf9a  mov     rcx, [rbp+88h]; this
0x1801bcfa1  mov     r9d, eax; char *
0x1801bcfa4  lea     r8, aOnecoreuapShel_45; "onecoreuap\\shell\\windows.storage\\per"...
0x1801bcfab  mov     edx, 0ECh; void *
0x1801bcfb0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801bcfb5  jmp     loc_1801BCD17
```
