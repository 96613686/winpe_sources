# wpr_wrapper::init(char const *,char const *)

- ea: `0x18005b630`
- end: `0x18005ba27`
- name: `?init@wpr_wrapper@@QEAAXPEBD0@Z`
- size: `1015`
- prototype: `void(wpr_wrapper *__hidden this, const char *, const char *)`
- caller_count: `5`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x1800518f0`
- `0x180051980`
- `0x180051b70`
- `0x180051c40`
- `0x180051ce0`

## callees

- `0x180004510`
- `0x180005508`
- `0x180005520`
- `0x18003af08`
- `0x180041400`
- `0x180041564`
- `0x180041dd0`
- `0x180054a20`
- `0x18005856c`
- `0x180058600`
- `0x18005b630`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005b7de`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005b805`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005b7de`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005b805`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005b7ad`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005b7ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b6c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b6fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b7bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b7ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b6c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b6fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b7bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b7ec`
- `OLEAUT32!__imp_SysFreeString` at `0x18005b665`
- `OLEAUT32!__imp_SysFreeString` at `0x18005b689`
- `OLEAUT32!__imp_SysFreeString` at `0x18005b665`
- `OLEAUT32!__imp_SysFreeString` at `0x18005b689`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18005b6b6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18005b6f3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18005b6b6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18005b6f3`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18005b793`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18005b793`

## string_xrefs

- `0x18005b74f`: `\windowsperformancerecordercontrol.dll`
- `0x18005b76c`: `\windowsperformancerecordercontrol.dll`
- `0x18005b7d3`: `WPRCCreateInstance`
- `0x18005b7fa`: `WPRCCreateInstanceUnderInstanceName`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall wpr_wrapper::init(wpr_wrapper *this, const char *a2, const char *a3)
{
  int v6; // edx
  unsigned __int16 *v7; // rax
  int v8; // edx
  unsigned __int16 *v9; // rax
  UINT SystemDirectoryW; // edi
  DWORD LastError; // eax
  WCHAR *v12; // rcx
  DWORD v13; // eax
  __int64 v14; // rcx
  __int64 v15; // rdi
  LPWSTR *v16; // rbx
  const WCHAR *v17; // rcx
  HMODULE LibraryW; // rbx
  HMODULE v19; // rcx
  DWORD v20; // eax
  FARPROC ProcAddress; // rax
  DWORD v22; // eax
  FARPROC v23; // rax
  int v24; // eax
  __int64 v25; // rcx
  __int64 v26; // rbx
  __int64 v27; // rdx
  __int64 v28; // [rsp+40h] [rbp-C0h] BYREF
  LPWSTR lpBuffer[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v30; // [rsp+58h] [rbp-A8h]
  unsigned __int64 v31; // [rsp+60h] [rbp-A0h]
  _BYTE pExceptionObject[1072]; // [rsp+70h] [rbp-90h] BYREF

  SysFreeString(*((BSTR *)this + 3));
  v7 = A2WBSTR(a2, v6);
  *((_QWORD *)this + 3) = v7;
  if ( !v7 && a2 )
    goto LABEL_39;
  SysFreeString(*((BSTR *)this + 4));
  if ( !a3 )
    a3 = "WinDiag";
  v9 = A2WBSTR(a3, v8);
  *((_QWORD *)this + 4) = v9;
  if ( !v9 )
LABEL_39:
    ATL::AtlThrowImpl(-2147024882);
  SystemDirectoryW = GetSystemDirectoryW(0, 0);
  if ( !SystemDirectoryW )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      windiag::system_exception::system_exception(
        (windiag::system_exception *)pExceptionObject,
        LastError,
        0,
        "[%s:%d] failed; ",
        "init",
        26);
      throw (windiag::system_exception *)pExceptionObject;
    }
  }
  std::wstring::wstring(lpBuffer, SystemDirectoryW + 64);
  v12 = (WCHAR *)lpBuffer;
  if ( v31 > 7 )
    v12 = lpBuffer[0];
  if ( GetSystemDirectoryW(v12, SystemDirectoryW + 64) != SystemDirectoryW )
  {
    v13 = GetLastError();
    if ( v13 )
    {
      windiag::system_exception::system_exception(
        (windiag::system_exception *)pExceptionObject,
        v13,
        0,
        "[%s:%d] failed; ",
        "init",
        28);
      throw (windiag::system_exception *)pExceptionObject;
    }
  }
  std::wstring::resize(lpBuffer);
  v14 = v30;
  if ( v31 - v30 < 0x26 )
  {
    std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,unsigned short const *,unsigned __int64>(
      lpBuffer,
      38);
  }
  else
  {
    v15 = v30 + 38;
    v30 += 38;
    v16 = lpBuffer;
    if ( v31 > 7 )
      v16 = (LPWSTR *)lpBuffer[0];
    memmove_0((char *)v16 + 2 * v14, L"\\windowsperformancerecordercontrol.dll", 0x4Cu);
    *((_WORD *)v16 + v15) = 0;
  }
  v17 = (const WCHAR *)lpBuffer;
  if ( v31 > 7 )
    v17 = lpBuffer[0];
  LibraryW = LoadLibraryW(v17);
  v19 = (HMODULE)*((_QWORD *)this + 2);
  if ( v19 )
  {
    *((_QWORD *)this + 2) = 0;
    FreeLibrary(v19);
  }
  *((_QWORD *)this + 2) = LibraryW;
  if ( !LibraryW )
  {
    v20 = GetLastError();
    if ( v20 )
    {
      windiag::system_exception::system_exception(
        (windiag::system_exception *)pExceptionObject,
        v20,
        0,
        "[%s:%d] failed; ",
        "init",
        33);
      throw (windiag::system_exception *)pExceptionObject;
    }
  }
  v28 = 0;
  ProcAddress = GetProcAddress(*((HMODULE *)this + 2), "WPRCCreateInstance");
  *(_QWORD *)this = ProcAddress;
  if ( !ProcAddress )
  {
    v22 = GetLastError();
    if ( v22 )
    {
      windiag::system_exception::system_exception(
        (windiag::system_exception *)pExceptionObject,
        v22,
        0,
        "[%s:%d] failed; ",
        "init",
        38);
      throw (windiag::system_exception *)pExceptionObject;
    }
  }
  v23 = GetProcAddress(*((HMODULE *)this + 2), "WPRCCreateInstanceUnderInstanceName");
  *((_QWORD *)this + 1) = v23;
  if ( v23 )
    v24 = ((__int64 (__fastcall *)(_QWORD, GUID *, _QWORD, __int64, GUID *, __int64 *))v23)(
            *((_QWORD *)this + 4),
            &GUID_971a7808_88be_4aad_9e1e_7c7e258512e3,
            0,
            1,
            &GUID_c66bc1c2_d913_4bf0_9e08_014523e4a205,
            &v28);
  else
    v24 = (*(__int64 (__fastcall **)(GUID *, _QWORD, __int64, GUID *, __int64 *))this)(
            &GUID_971a7808_88be_4aad_9e1e_7c7e258512e3,
            0,
            1,
            &GUID_c66bc1c2_d913_4bf0_9e08_014523e4a205,
            &v28);
  if ( v24 < 0 )
  {
    windiag::system_exception::system_exception(
      (windiag::system_exception *)pExceptionObject,
      v24,
      0,
      "[%s:%d] failed; ",
      "init",
      42);
    throw (windiag::system_exception *)pExceptionObject;
  }
  v25 = v28;
  if ( *((_QWORD *)this + 5) != v28 )
  {
    v26 = v28;
    if ( v28 )
    {
      (*(void (**)(void))(*(_QWORD *)v28 + 8LL))();
      v25 = v28;
    }
    v27 = *((_QWORD *)this + 5);
    if ( v27 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v27 + 16LL))(*((_QWORD *)this + 5));
      v25 = v28;
    }
    *((_QWORD *)this + 5) = v26;
  }
  if ( v25 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  std::wstring::~wstring(lpBuffer);
}

```

## disassembly

```asm
0x18005b630  mov     [rsp-8+arg_18], rbx
0x18005b635  push    rbp
0x18005b636  push    rsi
0x18005b637  push    rdi
0x18005b638  lea     rbp, [rsp-3B0h]
0x18005b640  sub     rsp, 4B0h
0x18005b647  mov     rax, cs:__security_cookie
0x18005b64e  xor     rax, rsp
0x18005b651  mov     [rbp+3C0h+var_20], rax
0x18005b658  mov     rbx, r8
0x18005b65b  mov     rdi, rdx
0x18005b65e  mov     rsi, rcx
0x18005b661  mov     rcx, [rcx+18h]; bstrString
0x18005b665  call    cs:__imp_SysFreeString
0x18005b66b  mov     rcx, rdi; lpMultiByteStr
0x18005b66e  call    ?A2WBSTR@@YAPEAGPEBDH@Z; A2WBSTR(char const *,int)
0x18005b673  mov     [rsi+18h], rax
0x18005b677  test    rax, rax
0x18005b67a  jnz     short loc_18005B685
0x18005b67c  test    rdi, rdi
0x18005b67f  jnz     loc_18005B92C
0x18005b685  mov     rcx, [rsi+20h]; bstrString
0x18005b689  call    cs:__imp_SysFreeString
0x18005b68f  lea     rax, szAgent; "WinDiag"
0x18005b696  test    rbx, rbx
0x18005b699  cmovz   rbx, rax
0x18005b69d  mov     rcx, rbx; lpMultiByteStr
0x18005b6a0  call    ?A2WBSTR@@YAPEAGPEBDH@Z; A2WBSTR(char const *,int)
0x18005b6a5  mov     [rsi+20h], rax
0x18005b6a9  test    rax, rax
0x18005b6ac  jz      loc_18005B92C
0x18005b6b2  xor     edx, edx; uSize
0x18005b6b4  xor     ecx, ecx; lpBuffer
0x18005b6b6  call    cs:__imp_GetSystemDirectoryW
0x18005b6bc  mov     edi, eax
0x18005b6be  test    eax, eax
0x18005b6c0  jnz     short loc_18005B6D0
0x18005b6c2  call    cs:__imp_GetLastError
0x18005b6c8  test    eax, eax
0x18005b6ca  jnz     loc_18005B937
0x18005b6d0  lea     ebx, [rdi+40h]
0x18005b6d3  mov     edx, ebx
0x18005b6d5  lea     rcx, [rsp+4C0h+lpBuffer]
0x18005b6da  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@_KG@Z; std::wstring::wstring(unsigned __int64,ushort)
0x18005b6df  nop
0x18005b6e0  lea     rcx, [rsp+4C0h+lpBuffer]
0x18005b6e5  cmp     [rsp+4C0h+var_460], 7
0x18005b6eb  cmova   rcx, [rsp+4C0h+lpBuffer]; lpBuffer
0x18005b6f1  mov     edx, ebx; uSize
0x18005b6f3  call    cs:__imp_GetSystemDirectoryW
0x18005b6f9  cmp     eax, edi
0x18005b6fb  jz      short loc_18005B70B
0x18005b6fd  call    cs:__imp_GetLastError
0x18005b703  test    eax, eax
0x18005b705  jnz     loc_18005B973
0x18005b70b  lea     edx, [rdi-1]
0x18005b70e  lea     rcx, [rsp+4C0h+lpBuffer]; Src
0x18005b713  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18005b718  mov     rcx, [rsp+4C0h+var_468]
0x18005b71d  mov     rax, [rsp+4C0h+var_460]
0x18005b722  sub     rax, rcx
0x18005b725  cmp     rax, 26h ; '&'
0x18005b729  jb      short loc_18005B763
0x18005b72b  lea     rdi, [rcx+26h]
0x18005b72f  mov     [rsp+4C0h+var_468], rdi
0x18005b734  lea     rbx, [rsp+4C0h+lpBuffer]
0x18005b739  cmp     [rsp+4C0h+var_460], 7
0x18005b73f  cmova   rbx, [rsp+4C0h+lpBuffer]
0x18005b745  lea     rcx, [rbx+rcx*2]; void *
0x18005b749  mov     r8d, 4Ch ; 'L'; Size
0x18005b74f  lea     rdx, aWindowsperform_0; "\\windowsperformancerecordercontrol.dll"
0x18005b756  call    memmove_0
0x18005b75b  xor     eax, eax
0x18005b75d  mov     [rbx+rdi*2], ax
0x18005b761  jmp     short loc_18005B782
0x18005b763  mov     [rsp+4C0h+var_4A0], 26h ; '&'; __int64
0x18005b76c  lea     r9, aWindowsperform_0; "\\windowsperformancerecordercontrol.dll"
0x18005b773  mov     edx, 26h ; '&'
0x18005b778  lea     rcx, [rsp+4C0h+lpBuffer]; Src
0x18005b77d  call    ??$_Reallocate_grow_by@V_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@Z; std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64)
0x18005b782  lea     rcx, [rsp+4C0h+lpBuffer]
0x18005b787  cmp     [rsp+4C0h+var_460], 7
0x18005b78d  cmova   rcx, [rsp+4C0h+lpBuffer]; lpLibFileName
0x18005b793  call    cs:__imp_LoadLibraryW
0x18005b799  mov     rbx, rax
0x18005b79c  mov     rcx, [rsi+10h]; hLibModule
0x18005b7a0  test    rcx, rcx
0x18005b7a3  jz      short loc_18005B7B3
0x18005b7a5  mov     qword ptr [rsi+10h], 0
0x18005b7ad  call    cs:__imp_FreeLibrary
0x18005b7b3  mov     [rsi+10h], rbx
0x18005b7b7  test    rbx, rbx
0x18005b7ba  jnz     short loc_18005B7CA
0x18005b7bc  call    cs:__imp_GetLastError
0x18005b7c2  test    eax, eax
0x18005b7c4  jnz     loc_18005B9AF
0x18005b7ca  mov     [rsp+4C0h+var_480], 0
0x18005b7d3  lea     rdx, aWprccreateinst; "WPRCCreateInstance"
0x18005b7da  mov     rcx, [rsi+10h]; hModule
0x18005b7de  call    cs:__imp_GetProcAddress
0x18005b7e4  mov     [rsi], rax
0x18005b7e7  test    rax, rax
0x18005b7ea  jnz     short loc_18005B7FA
0x18005b7ec  call    cs:__imp_GetLastError
0x18005b7f2  test    eax, eax
0x18005b7f4  jnz     loc_18005B9EB
0x18005b7fa  lea     rdx, aWprccreateinst_0; "WPRCCreateInstanceUnderInstanceName"
0x18005b801  mov     rcx, [rsi+10h]; hModule
0x18005b805  call    cs:__imp_GetProcAddress
0x18005b80b  mov     [rsi+8], rax
0x18005b80f  lea     r9, _GUID_c66bc1c2_d913_4bf0_9e08_014523e4a205
0x18005b816  test    rax, rax
0x18005b819  jz      short loc_18005B845
0x18005b81b  lea     rcx, [rsp+4C0h+var_480]
0x18005b820  mov     [rsp+4C0h+var_498], rcx
0x18005b825  mov     [rsp+4C0h+var_4A0], r9
0x18005b82a  mov     r9d, 1
0x18005b830  xor     r8d, r8d
0x18005b833  lea     rdx, _GUID_971a7808_88be_4aad_9e1e_7c7e258512e3
0x18005b83a  mov     rcx, [rsi+20h]
0x18005b83e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b843  jmp     short loc_18005B864
0x18005b845  lea     rax, [rsp+4C0h+var_480]
0x18005b84a  mov     [rsp+4C0h+var_4A0], rax
0x18005b84f  xor     edx, edx
0x18005b851  lea     r8d, [rdx+1]
0x18005b855  lea     rcx, _GUID_971a7808_88be_4aad_9e1e_7c7e258512e3
0x18005b85c  mov     rax, [rsi]
0x18005b85f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b864  test    eax, eax
0x18005b866  js      loc_18005B8EF
0x18005b86c  mov     rcx, [rsp+4C0h+var_480]
0x18005b871  cmp     [rsi+28h], rcx
0x18005b875  jz      short loc_18005B8B1
0x18005b877  mov     rbx, rcx
0x18005b87a  test    rcx, rcx
0x18005b87d  jz      short loc_18005B890
0x18005b87f  mov     rax, [rcx]
0x18005b882  mov     rax, [rax+8]
0x18005b886  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b88b  mov     rcx, [rsp+4C0h+var_480]
0x18005b890  mov     rdx, [rsi+28h]
0x18005b894  test    rdx, rdx
0x18005b897  jz      short loc_18005B8AD
0x18005b899  mov     rax, [rdx]
0x18005b89c  mov     rcx, rdx
0x18005b89f  mov     rax, [rax+10h]
0x18005b8a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b8a8  mov     rcx, [rsp+4C0h+var_480]
0x18005b8ad  mov     [rsi+28h], rbx
0x18005b8b1  test    rcx, rcx
0x18005b8b4  jz      short loc_18005B8C3
0x18005b8b6  mov     rax, [rcx]
0x18005b8b9  mov     rax, [rax+10h]
0x18005b8bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b8c2  nop
0x18005b8c3  lea     rcx, [rsp+4C0h+lpBuffer]
0x18005b8c8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005b8cd  mov     rcx, [rbp+3C0h+var_20]
0x18005b8d4  xor     rcx, rsp; StackCookie
0x18005b8d7  call    __security_check_cookie
0x18005b8dc  mov     rbx, [rsp+4C0h+arg_18]
0x18005b8e4  add     rsp, 4B0h
0x18005b8eb  pop     rdi
0x18005b8ec  pop     rsi
0x18005b8ed  pop     rbp
0x18005b8ee  retn
0x18005b8ef  movsxd  rdx, eax; __int64
0x18005b8f2  mov     dword ptr [rsp+4C0h+var_498], 2Ah ; '*'
0x18005b8fa  lea     rax, aInit; "init"
0x18005b901  mov     [rsp+4C0h+var_4A0], rax
0x18005b906  lea     r9, aSDFailed; "[%s:%d] failed; "
0x18005b90d  xor     r8d, r8d; void *
0x18005b910  lea     rcx, [rsp+4C0h+pExceptionObject]; this
0x18005b915  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x18005b91a  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x18005b921  lea     rcx, [rsp+4C0h+pExceptionObject]; pExceptionObject
0x18005b926  call    _CxxThrowException_0
0x18005b92c  mov     ecx, 8007000Eh; int
0x18005b931  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18005b937  mov     edx, eax; __int64
0x18005b939  mov     dword ptr [rsp+4C0h+var_498], 1Ah
0x18005b941  lea     rax, aInit; "init"
0x18005b948  mov     [rsp+4C0h+var_4A0], rax
0x18005b94d  lea     r9, aSDFailed; "[%s:%d] failed; "
0x18005b954  xor     r8d, r8d; void *
0x18005b957  lea     rcx, [rsp+4C0h+pExceptionObject]; this
0x18005b95c  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x18005b961  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x18005b968  lea     rcx, [rsp+4C0h+pExceptionObject]; pExceptionObject
0x18005b96d  call    _CxxThrowException_0
0x18005b973  mov     edx, eax; __int64
0x18005b975  mov     dword ptr [rsp+4C0h+var_498], 1Ch
0x18005b97d  lea     rax, aInit; "init"
0x18005b984  mov     [rsp+4C0h+var_4A0], rax
0x18005b989  lea     r9, aSDFailed; "[%s:%d] failed; "
0x18005b990  xor     r8d, r8d; void *
0x18005b993  lea     rcx, [rsp+4C0h+pExceptionObject]; this
0x18005b998  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x18005b99d  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x18005b9a4  lea     rcx, [rsp+4C0h+pExceptionObject]; pExceptionObject
0x18005b9a9  call    _CxxThrowException_0
0x18005b9af  mov     edx, eax; __int64
0x18005b9b1  mov     dword ptr [rsp+4C0h+var_498], 21h ; '!'
0x18005b9b9  lea     rax, aInit; "init"
0x18005b9c0  mov     [rsp+4C0h+var_4A0], rax
0x18005b9c5  lea     r9, aSDFailed; "[%s:%d] failed; "
0x18005b9cc  xor     r8d, r8d; void *
0x18005b9cf  lea     rcx, [rsp+4C0h+pExceptionObject]; this
0x18005b9d4  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x18005b9d9  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x18005b9e0  lea     rcx, [rsp+4C0h+pExceptionObject]; pExceptionObject
0x18005b9e5  call    _CxxThrowException_0
0x18005b9eb  mov     edx, eax; __int64
0x18005b9ed  mov     dword ptr [rsp+4C0h+var_498], 26h ; '&'
0x18005b9f5  lea     rax, aInit; "init"
0x18005b9fc  mov     [rsp+4C0h+var_4A0], rax
0x18005ba01  lea     r9, aSDFailed; "[%s:%d] failed; "
0x18005ba08  xor     r8d, r8d; void *
0x18005ba0b  lea     rcx, [rsp+4C0h+pExceptionObject]; this
0x18005ba10  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x18005ba15  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x18005ba1c  lea     rcx, [rsp+4C0h+pExceptionObject]; pExceptionObject
0x18005ba21  call    _CxxThrowException_0
```
