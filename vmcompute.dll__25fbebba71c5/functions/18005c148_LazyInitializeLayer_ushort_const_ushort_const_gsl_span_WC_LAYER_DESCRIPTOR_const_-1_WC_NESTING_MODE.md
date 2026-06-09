# LazyInitializeLayer(ushort const *,ushort const *,gsl::span<_WC_LAYER_DESCRIPTOR const,-1>,_WC_NESTING_MODE)

- ea: `0x18005c148`
- end: `0x18005c3e1`
- name: `?LazyInitializeLayer@@YAXPEBG0V?$span@$$CBU_WC_LAYER_DESCRIPTOR@@$0?0@gsl@@W4_WC_NESTING_MODE@@@Z`
- size: `665`
- prototype: `__int64 __fastcall(PCWSTR pszPathIn)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180030d40`
- `0x180035d90`

## callees

- `0x180002f50`
- `0x180006660`
- `0x18000d0ec`
- `0x18000d108`
- `0x18002e454`
- `0x18002eb7c`
- `0x18002f94c`
- `0x18005c148`
- `0x18005c3e8`
- `0x18005fa48`
- `0x180060340`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c38c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c38c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005c315`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005c33b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005c315`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005c33b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005c2de`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005c2de`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18005c1d6`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18005c1d6`
- `wc_storage!WcInitializeSandboxEx` at `0x18005c293`
- `wc_storage!WcInitializeSandboxEx` at `0x18005c293`

## string_xrefs

- `0x18005c3a8`: `onecore\vm\compute\shared\storage\layerutilities.cpp`
- `0x18005c3ba`: `onecore\vm\compute\shared\storage\layerutilities.cpp`
- `0x18005c3cf`: `onecore\vm\compute\shared\storage\layerutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall LazyInitializeLayer(PCWSTR pszPathIn, __int64 a2, unsigned int *a3, int a4)
{
  const WCHAR *v7; // rdx
  const WCHAR *v8; // rcx
  const char *v9; // r9
  char v10; // bl
  char v11; // al
  _QWORD *v12; // rdx
  const unsigned __int16 *v13; // rdx
  PCWSTR *v14; // rdx
  _QWORD *v15; // rcx
  int v16; // eax
  const WCHAR *v17; // rcx
  char *FileW; // rax
  const char *v19; // r9
  HANDLE hObject[2]; // [rsp+40h] [rbp-89h] BYREF
  __int128 v22; // [rsp+50h] [rbp-79h]
  _QWORD Src[3]; // [rsp+60h] [rbp-69h] BYREF
  unsigned __int64 v24; // [rsp+78h] [rbp-51h]
  LPCWSTR lpFileName[3]; // [rsp+80h] [rbp-49h] BYREF
  unsigned __int64 v26; // [rsp+98h] [rbp-31h]
  PCWSTR pszPathIna[3]; // [rsp+A0h] [rbp-29h] BYREF
  unsigned __int64 v28; // [rsp+B8h] [rbp-11h]
  __int128 v29; // [rsp+C0h] [rbp-9h] BYREF
  __int64 v30; // [rsp+D0h] [rbp+7h]
  __int128 v31; // [rsp+D8h] [rbp+Fh] BYREF
  __int64 v32; // [rsp+E8h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  v22 = *(_OWORD *)a3;
  SandboxStatePath(pszPathIna, pszPathIn);
  v31 = 0;
  v32 = 0;
  Vml::TemporaryPrivilege::TemporaryPrivilege((Vml::TemporaryPrivilege *)&v31, 17);
  v7 = (const WCHAR *)pszPathIna;
  if ( v28 > 7 )
    v7 = pszPathIna[0];
  Vml::CombineFilePath(lpFileName, v7, L"initialized");
  v8 = (const WCHAR *)lpFileName;
  if ( v26 > 7 )
    v8 = lpFileName[0];
  if ( GetFileAttributesW(v8) != -1 )
  {
    v10 = 1;
LABEL_7:
    v11 = 0;
    goto LABEL_8;
  }
  v10 = 0;
  if ( GetLastError() == 2 )
    goto LABEL_7;
  v11 = 1;
LABEL_8:
  if ( v11 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x2E,
      (unsigned int)"onecore\\vm\\compute\\shared\\storage\\layerutilities.cpp",
      v9);
  if ( !v10 )
  {
    Vml::CombineFilePath(Src, pszPathIn, L".\\");
    hObject[0] = 0;
    v12 = Src;
    if ( v24 > 7 )
      v12 = (_QWORD *)Src[0];
    GetDiskHandle(hObject, v12);
    v13 = (const unsigned __int16 *)Src;
    if ( v24 > 7 )
      v13 = (const unsigned __int16 *)Src[0];
    ExpandVolume(hObject[0], v13);
    v29 = 0;
    v30 = 0;
    Vml::TemporaryPrivilege::TemporaryPrivilege((Vml::TemporaryPrivilege *)&v29, 18);
    v14 = pszPathIna;
    if ( v28 > 7 )
      v14 = (PCWSTR *)pszPathIna[0];
    v15 = Src;
    if ( v24 > 7 )
      v15 = (_QWORD *)Src[0];
    v16 = WcInitializeSandboxEx(v15, v14, *((_QWORD *)a3 + 1), *a3);
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3F,
        (unsigned int)"onecore\\vm\\compute\\shared\\storage\\layerutilities.cpp",
        (const char *)(unsigned int)v16,
        a4);
    v17 = (const WCHAR *)lpFileName;
    if ( v26 > 7 )
      v17 = lpFileName[0];
    FileW = (char *)CreateFileW(v17, 0x40000000u, 3u, 0, 1u, 0x2000000u, 0);
    *(_QWORD *)&v22 = FileW;
    if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x4A,
        (unsigned int)"onecore\\vm\\compute\\shared\\storage\\layerutilities.cpp",
        v19);
    if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(FileW);
    Vml::TemporaryPrivilege::~TemporaryPrivilege((Vml::TemporaryPrivilege *)&v29);
    if ( (unsigned __int64)hObject[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(hObject[0]);
    std::wstring::~wstring(Src);
  }
  std::wstring::~wstring(lpFileName);
  Vml::TemporaryPrivilege::~TemporaryPrivilege((Vml::TemporaryPrivilege *)&v31);
  return std::wstring::~wstring(pszPathIna);
}

```

## disassembly

```asm
0x18005c148  push    rbp
0x18005c14a  push    rbx
0x18005c14b  push    rsi
0x18005c14c  push    rdi
0x18005c14d  push    r14
0x18005c14f  lea     rbp, [rsp-37h]
0x18005c154  sub     rsp, 100h
0x18005c15b  mov     rax, cs:__security_cookie
0x18005c162  xor     rax, rsp
0x18005c165  mov     [rbp+57h+var_30], rax
0x18005c169  mov     r14d, r9d
0x18005c16c  mov     rdi, r8
0x18005c16f  mov     rsi, rcx
0x18005c172  movaps  xmm0, xmmword ptr [r8]
0x18005c176  movdqa  [rbp+57h+var_D0], xmm0
0x18005c17b  lea     r9, [rbp+57h+var_D0]
0x18005c17f  mov     r8, rdx
0x18005c182  mov     rdx, rcx; pszPathIn
0x18005c185  lea     rcx, [rbp+57h+pszPathIn]; Src
0x18005c189  call    ?SandboxStatePath@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0V?$span@$$CBU_WC_LAYER_DESCRIPTOR@@$0?0@gsl@@@Z; SandboxStatePath(ushort const *,ushort const *,gsl::span<_WC_LAYER_DESCRIPTOR const,-1>)
0x18005c18e  nop
0x18005c18f  xorps   xmm0, xmm0
0x18005c192  xor     eax, eax
0x18005c194  movups  [rbp+57h+var_48], xmm0
0x18005c198  mov     [rbp+57h+var_38], rax
0x18005c19c  lea     edx, [rax+11h]; int
0x18005c19f  lea     rcx, [rbp+57h+var_48]; this
0x18005c1a3  call    ??0TemporaryPrivilege@Vml@@QEAA@J@Z; Vml::TemporaryPrivilege::TemporaryPrivilege(long)
0x18005c1a8  nop
0x18005c1a9  lea     rdx, [rbp+57h+pszPathIn]
0x18005c1ad  cmp     [rbp+57h+var_68], 7
0x18005c1b2  cmova   rdx, [rbp+57h+pszPathIn]; pszPathIn
0x18005c1b7  lea     r8, aInitialized; "initialized"
0x18005c1be  lea     rcx, [rbp+57h+lpFileName]; Src
0x18005c1c2  call    ?CombineFilePath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; Vml::CombineFilePath(ushort const *,ushort const *)
0x18005c1c7  nop
0x18005c1c8  lea     rcx, [rbp+57h+lpFileName]
0x18005c1cc  cmp     [rbp+57h+var_88], 7
0x18005c1d1  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x18005c1d6  call    cs:__imp_GetFileAttributesW
0x18005c1dd  nop     dword ptr [rax+rax+00h]
0x18005c1e2  cmp     eax, 0FFFFFFFFh
0x18005c1e5  jz      loc_18005C38A
0x18005c1eb  mov     bl, 1
0x18005c1ed  xor     al, al
0x18005c1ef  mov     rcx, [rbp+5Fh]; this
0x18005c1f3  test    al, al
0x18005c1f5  jnz     loc_18005C3BA
0x18005c1fb  test    bl, bl
0x18005c1fd  jnz     loc_18005C352
0x18005c203  lea     r8, asc_1800935F4; ".\\"
0x18005c20a  mov     rdx, rsi; pszPathIn
0x18005c20d  lea     rcx, [rbp+57h+Src]; Src
0x18005c211  call    ?CombineFilePath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; Vml::CombineFilePath(ushort const *,ushort const *)
0x18005c216  nop
0x18005c217  mov     [rsp+120h+hObject], 0
0x18005c220  lea     rdx, [rbp+57h+Src]
0x18005c224  cmp     [rbp+57h+var_A8], 7
0x18005c229  cmova   rdx, [rbp+57h+Src]
0x18005c22e  lea     rcx, [rsp+120h+hObject]
0x18005c233  call    ?GetDiskHandle@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEBG@Z; GetDiskHandle(ushort const *)
0x18005c238  nop
0x18005c239  lea     rdx, [rbp+57h+Src]
0x18005c23d  cmp     [rbp+57h+var_A8], 7
0x18005c242  cmova   rdx, [rbp+57h+Src]; unsigned __int16 *
0x18005c247  mov     rcx, [rsp+120h+hObject]; void *
0x18005c24c  call    ?ExpandVolume@@YA_NPEAXPEBG@Z; ExpandVolume(void *,ushort const *)
0x18005c251  xorps   xmm0, xmm0
0x18005c254  xor     eax, eax
0x18005c256  movups  [rbp+57h+var_60], xmm0
0x18005c25a  mov     [rbp+57h+var_50], rax
0x18005c25e  lea     edx, [rax+12h]; int
0x18005c261  lea     rcx, [rbp+57h+var_60]; this
0x18005c265  call    ??0TemporaryPrivilege@Vml@@QEAA@J@Z; Vml::TemporaryPrivilege::TemporaryPrivilege(long)
0x18005c26a  nop
0x18005c26b  lea     rdx, [rbp+57h+pszPathIn]
0x18005c26f  cmp     [rbp+57h+var_68], 7
0x18005c274  cmova   rdx, [rbp+57h+pszPathIn]
0x18005c279  lea     rcx, [rbp+57h+Src]
0x18005c27d  cmp     [rbp+57h+var_A8], 7
0x18005c282  cmova   rcx, [rbp+57h+Src]
0x18005c287  mov     [rsp+120h+dwCreationDisposition], r14d; int
0x18005c28c  mov     r9d, [rdi]
0x18005c28f  mov     r8, [rdi+8]
0x18005c293  call    cs:__imp_WcInitializeSandboxEx
0x18005c29a  nop     dword ptr [rax+rax+00h]
0x18005c29f  mov     rcx, [rbp+5Fh]; this
0x18005c2a3  test    eax, eax
0x18005c2a5  js      loc_18005C3CC
0x18005c2ab  lea     rcx, [rbp+57h+lpFileName]
0x18005c2af  cmp     [rbp+57h+var_88], 7
0x18005c2b4  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x18005c2b9  mov     [rsp+120h+hTemplateFile], 0; hTemplateFile
0x18005c2c2  mov     [rsp+120h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18005c2ca  mov     [rsp+120h+dwCreationDisposition], 1; dwCreationDisposition
0x18005c2d2  xor     r9d, r9d; lpSecurityAttributes
0x18005c2d5  mov     edx, 40000000h; dwDesiredAccess
0x18005c2da  lea     r8d, [r9+3]; dwShareMode
0x18005c2de  call    cs:__imp_CreateFileW
0x18005c2e5  nop     dword ptr [rax+rax+00h]
0x18005c2ea  mov     qword ptr [rbp+57h+var_D0], rax
0x18005c2ee  lea     rcx, [rax+1]
0x18005c2f2  test    rcx, 0FFFFFFFFFFFFFFFEh
0x18005c2f9  setz    dl
0x18005c2fc  mov     rcx, [rbp+5Fh]; this
0x18005c300  test    dl, dl
0x18005c302  jnz     loc_18005C3A8
0x18005c308  lea     rcx, [rax-1]
0x18005c30c  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18005c310  ja      short loc_18005C322
0x18005c312  mov     rcx, rax; hObject
0x18005c315  call    cs:__imp_CloseHandle
0x18005c31c  nop     dword ptr [rax+rax+00h]
0x18005c321  nop
0x18005c322  lea     rcx, [rbp+57h+var_60]; this
0x18005c326  call    ??1TemporaryPrivilege@Vml@@QEAA@XZ; Vml::TemporaryPrivilege::~TemporaryPrivilege(void)
0x18005c32b  nop
0x18005c32c  mov     rcx, [rsp+120h+hObject]; hObject
0x18005c331  lea     rax, [rcx-1]
0x18005c335  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005c339  ja      short loc_18005C348
0x18005c33b  call    cs:__imp_CloseHandle
0x18005c342  nop     dword ptr [rax+rax+00h]
0x18005c347  nop
0x18005c348  lea     rcx, [rbp+57h+Src]
0x18005c34c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005c351  nop
0x18005c352  lea     rcx, [rbp+57h+lpFileName]
0x18005c356  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005c35b  nop
0x18005c35c  lea     rcx, [rbp+57h+var_48]; this
0x18005c360  call    ??1TemporaryPrivilege@Vml@@QEAA@XZ; Vml::TemporaryPrivilege::~TemporaryPrivilege(void)
0x18005c365  nop
0x18005c366  lea     rcx, [rbp+57h+pszPathIn]
0x18005c36a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005c36f  mov     rcx, [rbp+57h+var_30]
0x18005c373  xor     rcx, rsp; StackCookie
0x18005c376  call    __security_check_cookie
0x18005c37b  add     rsp, 100h
0x18005c382  pop     r14
0x18005c384  pop     rdi
0x18005c385  pop     rsi
0x18005c386  pop     rbx
0x18005c387  pop     rbp
0x18005c388  retn
0x18005c38a  xor     bl, bl
0x18005c38c  call    cs:__imp_GetLastError
0x18005c393  nop     dword ptr [rax+rax+00h]
0x18005c398  cmp     eax, 2
0x18005c39b  jz      loc_18005C1ED
0x18005c3a1  mov     al, 1
0x18005c3a3  jmp     loc_18005C1EF
0x18005c3a8  lea     r8, aOnecoreVmCompu_11; "onecore\\vm\\compute\\shared\\storage\\"...
0x18005c3af  mov     edx, 4Ah ; 'J'; void *
0x18005c3b4  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18005c3ba  lea     r8, aOnecoreVmCompu_11; "onecore\\vm\\compute\\shared\\storage\\"...
0x18005c3c1  mov     edx, 2Eh ; '.'; void *
0x18005c3c6  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18005c3cc  mov     r9d, eax; char *
0x18005c3cf  lea     r8, aOnecoreVmCompu_11; "onecore\\vm\\compute\\shared\\storage\\"...
0x18005c3d6  mov     edx, 3Fh ; '?'; void *
0x18005c3db  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
