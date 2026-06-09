# LazyInitializeLayer(ushort const *,ushort const *,gsl::span<_WC_LAYER_DESCRIPTOR const,-1>,_WC_NESTING_MODE)

- ea: `0x14004218c`
- end: `0x14004241f`
- name: `?LazyInitializeLayer@@YAXPEBG0V?$span@$$CBU_WC_LAYER_DESCRIPTOR@@$0?0@gsl@@W4_WC_NESTING_MODE@@@Z`
- size: `659`
- prototype: `__int64 __fastcall(PCWSTR pszPathIn)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1400d9704`

## callees

- `0x140005360`
- `0x140008760`
- `0x14000ddac`
- `0x14000ea60`
- `0x140040bc4`
- `0x140040ff8`
- `0x140041b14`
- `0x140041d9c`
- `0x140041ff0`
- `0x14004218c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400423b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400423b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004234a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140042369`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004234a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140042369`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140042319`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140042319`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14004221d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14004221d`
- `wc_storage!WcInitializeSandboxEx` at `0x1400422d4`
- `wc_storage!WcInitializeSandboxEx` at `0x1400422d4`

## string_xrefs

- `0x1400423ce`: `onecore\vm\compute\shared\storage\layerutilities.cpp`
- `0x1400423e6`: `onecore\vm\compute\shared\storage\layerutilities.cpp`
- `0x1400423f8`: `onecore\vm\compute\shared\storage\layerutilities.cpp`
- `0x14004240d`: `onecore\vm\compute\shared\storage\layerutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall LazyInitializeLayer(PCWSTR pszPathIn, __int64 a2, _QWORD *a3)
{
  const WCHAR *v5; // rdx
  const WCHAR *v6; // rcx
  const char *v7; // r9
  char v8; // bl
  char v9; // al
  unsigned __int16 **v10; // rdx
  const unsigned __int16 *v11; // rdx
  _QWORD *v12; // rdx
  unsigned __int16 **v13; // rcx
  int v14; // eax
  const WCHAR *v15; // rcx
  char *FileW; // rax
  const char *v17; // r9
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-89h]
  HANDLE hObject[2]; // [rsp+40h] [rbp-69h] BYREF
  unsigned __int16 *v20[3]; // [rsp+50h] [rbp-59h] BYREF
  unsigned __int64 v21; // [rsp+68h] [rbp-41h]
  LPCWSTR lpFileName[3]; // [rsp+70h] [rbp-39h] BYREF
  unsigned __int64 v23; // [rsp+88h] [rbp-21h]
  _QWORD Src[3]; // [rsp+90h] [rbp-19h] BYREF
  unsigned __int64 v25; // [rsp+A8h] [rbp-1h]
  __int128 v26; // [rsp+B0h] [rbp+7h] BYREF
  __int64 v27; // [rsp+C0h] [rbp+17h]
  __int128 v28; // [rsp+C8h] [rbp+1Fh] BYREF
  __int64 v29; // [rsp+D8h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  if ( !*a3 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x78,
      (unsigned int)"onecore\\vm\\compute\\shared\\storage\\layerutilities.cpp",
      (const char *)0x80070057LL,
      dwCreationDisposition);
  CommonUtilities::CombineFilePath(Src, pszPathIn, L"WcSandboxState");
  v28 = 0;
  v29 = 0;
  Vml::TemporaryPrivilege::TemporaryPrivilege((Vml::TemporaryPrivilege *)&v28, 17);
  v5 = (const WCHAR *)Src;
  if ( v25 > 7 )
    v5 = (const WCHAR *)Src[0];
  CommonUtilities::CombineFilePath(lpFileName, v5, L"initialized");
  v6 = (const WCHAR *)lpFileName;
  if ( v23 > 7 )
    v6 = lpFileName[0];
  if ( GetFileAttributesW(v6) != -1 )
  {
    v8 = 1;
LABEL_8:
    v9 = 0;
    goto LABEL_9;
  }
  v8 = 0;
  if ( GetLastError() == 2 )
    goto LABEL_8;
  v9 = 1;
LABEL_9:
  if ( v9 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x2E,
      (unsigned int)"onecore\\vm\\compute\\shared\\storage\\layerutilities.cpp",
      v7);
  if ( !v8 )
  {
    CommonUtilities::CombineFilePath(v20, pszPathIn, L".\\");
    hObject[0] = 0;
    v10 = v20;
    if ( v21 > 7 )
      v10 = (unsigned __int16 **)v20[0];
    GetDiskHandle(hObject, v10);
    v11 = (const unsigned __int16 *)v20;
    if ( v21 > 7 )
      v11 = v20[0];
    ExpandVolume(hObject[0], v11);
    v26 = 0;
    v27 = 0;
    Vml::TemporaryPrivilege::TemporaryPrivilege((Vml::TemporaryPrivilege *)&v26, 18);
    v12 = Src;
    if ( v25 > 7 )
      v12 = (_QWORD *)Src[0];
    v13 = v20;
    if ( v21 > 7 )
      v13 = (unsigned __int16 **)v20[0];
    v14 = WcInitializeSandboxEx(v13, v12, a3[1], *(unsigned int *)a3);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3F,
        (unsigned int)"onecore\\vm\\compute\\shared\\storage\\layerutilities.cpp",
        (const char *)(unsigned int)v14,
        0);
    v15 = (const WCHAR *)lpFileName;
    if ( v23 > 7 )
      v15 = lpFileName[0];
    FileW = (char *)CreateFileW(v15, 0x40000000u, 3u, 0, 1u, 0x2000000u, 0);
    hObject[1] = FileW;
    if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x4A,
        (unsigned int)"onecore\\vm\\compute\\shared\\storage\\layerutilities.cpp",
        v17);
    if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(FileW);
    Vml::TemporaryPrivilege::~TemporaryPrivilege((Vml::TemporaryPrivilege *)&v26);
    if ( (unsigned __int64)hObject[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(hObject[0]);
    std::wstring::~wstring(v20);
  }
  std::wstring::~wstring(lpFileName);
  Vml::TemporaryPrivilege::~TemporaryPrivilege((Vml::TemporaryPrivilege *)&v28);
  std::wstring::~wstring(Src);
}

```

## disassembly

```asm
0x14004218c  mov     [rsp-8+arg_8], rbx
0x140042191  push    rbp
0x140042192  push    rsi
0x140042193  push    rdi
0x140042194  lea     rbp, [rsp-47h]
0x140042199  sub     rsp, 0F0h
0x1400421a0  mov     rax, cs:__security_cookie
0x1400421a7  xor     rax, rsp
0x1400421aa  mov     [rbp+57h+var_20], rax
0x1400421ae  mov     rdi, r8
0x1400421b1  mov     rsi, rcx
0x1400421b4  mov     rcx, [rbp+5Fh]; this
0x1400421b8  cmp     qword ptr [r8], 0
0x1400421bc  jz      loc_1400423E0
0x1400421c2  lea     r8, aWcsandboxstate; "WcSandboxState"
0x1400421c9  mov     rdx, rsi; pszPathIn
0x1400421cc  lea     rcx, [rbp+57h+Src]; Src
0x1400421d0  call    ?CombineFilePath@CommonUtilities@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; CommonUtilities::CombineFilePath(ushort const *,ushort const *)
0x1400421d5  nop
0x1400421d6  xorps   xmm0, xmm0
0x1400421d9  xor     eax, eax
0x1400421db  movups  [rbp+57h+var_38], xmm0
0x1400421df  mov     [rbp+57h+var_28], rax
0x1400421e3  lea     edx, [rax+11h]; int
0x1400421e6  lea     rcx, [rbp+57h+var_38]; this
0x1400421ea  call    ??0TemporaryPrivilege@Vml@@QEAA@J@Z; Vml::TemporaryPrivilege::TemporaryPrivilege(long)
0x1400421ef  nop
0x1400421f0  lea     rdx, [rbp+57h+Src]
0x1400421f4  cmp     [rbp+57h+var_58], 7
0x1400421f9  cmova   rdx, [rbp+57h+Src]; pszPathIn
0x1400421fe  lea     r8, aInitialized; "initialized"
0x140042205  lea     rcx, [rbp+57h+lpFileName]; Src
0x140042209  call    ?CombineFilePath@CommonUtilities@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; CommonUtilities::CombineFilePath(ushort const *,ushort const *)
0x14004220e  nop
0x14004220f  lea     rcx, [rbp+57h+lpFileName]
0x140042213  cmp     [rbp+57h+var_78], 7
0x140042218  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x14004221d  call    cs:__imp_GetFileAttributesW
0x140042223  cmp     eax, 0FFFFFFFFh
0x140042226  jz      loc_1400423B6
0x14004222c  mov     bl, 1
0x14004222e  xor     al, al
0x140042230  mov     rcx, [rbp+5Fh]; this
0x140042234  test    al, al
0x140042236  jnz     loc_1400423F8
0x14004223c  test    bl, bl
0x14004223e  jnz     loc_14004237A
0x140042244  lea     r8, pszMore; ".\\"
0x14004224b  mov     rdx, rsi; pszPathIn
0x14004224e  lea     rcx, [rbp+57h+var_B0]; Src
0x140042252  call    ?CombineFilePath@CommonUtilities@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; CommonUtilities::CombineFilePath(ushort const *,ushort const *)
0x140042257  nop
0x140042258  mov     [rbp+57h+hObject], 0
0x140042260  lea     rdx, [rbp+57h+var_B0]
0x140042264  cmp     [rbp+57h+var_98], 7
0x140042269  cmova   rdx, [rbp+57h+var_B0]
0x14004226e  lea     rcx, [rbp+57h+hObject]
0x140042272  call    ?GetDiskHandle@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEBG@Z; GetDiskHandle(ushort const *)
0x140042277  nop
0x140042278  lea     rdx, [rbp+57h+var_B0]
0x14004227c  cmp     [rbp+57h+var_98], 7
0x140042281  cmova   rdx, [rbp+57h+var_B0]; unsigned __int16 *
0x140042286  mov     rcx, [rbp+57h+hObject]; void *
0x14004228a  call    ?ExpandVolume@@YA_NPEAXPEBG@Z; ExpandVolume(void *,ushort const *)
0x14004228f  xorps   xmm0, xmm0
0x140042292  xor     eax, eax
0x140042294  movups  [rbp+57h+var_50], xmm0
0x140042298  mov     [rbp+57h+var_40], rax
0x14004229c  lea     edx, [rax+12h]; int
0x14004229f  lea     rcx, [rbp+57h+var_50]; this
0x1400422a3  call    ??0TemporaryPrivilege@Vml@@QEAA@J@Z; Vml::TemporaryPrivilege::TemporaryPrivilege(long)
0x1400422a8  nop
0x1400422a9  lea     rdx, [rbp+57h+Src]
0x1400422ad  cmp     [rbp+57h+var_58], 7
0x1400422b2  cmova   rdx, [rbp+57h+Src]
0x1400422b7  lea     rcx, [rbp+57h+var_B0]
0x1400422bb  cmp     [rbp+57h+var_98], 7
0x1400422c0  cmova   rcx, [rbp+57h+var_B0]
0x1400422c5  mov     [rsp+100h+dwCreationDisposition], 0; int
0x1400422cd  mov     r9d, [rdi]
0x1400422d0  mov     r8, [rdi+8]
0x1400422d4  call    cs:__imp_WcInitializeSandboxEx
0x1400422da  mov     rcx, [rbp+5Fh]; this
0x1400422de  test    eax, eax
0x1400422e0  js      loc_14004240A
0x1400422e6  lea     rcx, [rbp+57h+lpFileName]
0x1400422ea  cmp     [rbp+57h+var_78], 7
0x1400422ef  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x1400422f4  mov     [rsp+100h+hTemplateFile], 0; hTemplateFile
0x1400422fd  mov     [rsp+100h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x140042305  mov     [rsp+100h+dwCreationDisposition], 1; dwCreationDisposition
0x14004230d  xor     r9d, r9d; lpSecurityAttributes
0x140042310  mov     edx, 40000000h; dwDesiredAccess
0x140042315  lea     r8d, [r9+3]; dwShareMode
0x140042319  call    cs:__imp_CreateFileW
0x14004231f  mov     [rbp+57h+var_B8], rax
0x140042323  lea     rcx, [rax+1]
0x140042327  test    rcx, 0FFFFFFFFFFFFFFFEh
0x14004232e  setz    dl
0x140042331  mov     rcx, [rbp+5Fh]; this
0x140042335  test    dl, dl
0x140042337  jnz     loc_1400423CE
0x14004233d  lea     rcx, [rax-1]
0x140042341  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x140042345  ja      short loc_140042351
0x140042347  mov     rcx, rax; hObject
0x14004234a  call    cs:__imp_CloseHandle
0x140042350  nop
0x140042351  lea     rcx, [rbp+57h+var_50]; this
0x140042355  call    ??1TemporaryPrivilege@Vml@@QEAA@XZ; Vml::TemporaryPrivilege::~TemporaryPrivilege(void)
0x14004235a  nop
0x14004235b  mov     rcx, [rbp+57h+hObject]; hObject
0x14004235f  lea     rax, [rcx-1]
0x140042363  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140042367  ja      short loc_140042370
0x140042369  call    cs:__imp_CloseHandle
0x14004236f  nop
0x140042370  lea     rcx, [rbp+57h+var_B0]; void *
0x140042374  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140042379  nop
0x14004237a  lea     rcx, [rbp+57h+lpFileName]; void *
0x14004237e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140042383  nop
0x140042384  lea     rcx, [rbp+57h+var_38]; this
0x140042388  call    ??1TemporaryPrivilege@Vml@@QEAA@XZ; Vml::TemporaryPrivilege::~TemporaryPrivilege(void)
0x14004238d  nop
0x14004238e  lea     rcx, [rbp+57h+Src]; void *
0x140042392  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140042397  mov     rcx, [rbp+57h+var_20]
0x14004239b  xor     rcx, rsp; StackCookie
0x14004239e  call    __security_check_cookie
0x1400423a3  mov     rbx, [rsp+100h+arg_8]
0x1400423ab  add     rsp, 0F0h
0x1400423b2  pop     rdi
0x1400423b3  pop     rsi
0x1400423b4  pop     rbp
0x1400423b5  retn
0x1400423b6  xor     bl, bl
0x1400423b8  call    cs:__imp_GetLastError
0x1400423be  cmp     eax, 2
0x1400423c1  jz      loc_14004222E
0x1400423c7  mov     al, 1
0x1400423c9  jmp     loc_140042230
0x1400423ce  lea     r8, aOnecoreVmCompu_37; "onecore\\vm\\compute\\shared\\storage\\"...
0x1400423d5  mov     edx, 4Ah ; 'J'; void *
0x1400423da  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400423e0  mov     r9d, 80070057h; char *
0x1400423e6  lea     r8, aOnecoreVmCompu_37; "onecore\\vm\\compute\\shared\\storage\\"...
0x1400423ed  mov     edx, 78h ; 'x'; void *
0x1400423f2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400423f8  lea     r8, aOnecoreVmCompu_37; "onecore\\vm\\compute\\shared\\storage\\"...
0x1400423ff  mov     edx, 2Eh ; '.'; void *
0x140042404  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14004240a  mov     r9d, eax; char *
0x14004240d  lea     r8, aOnecoreVmCompu_37; "onecore\\vm\\compute\\shared\\storage\\"...
0x140042414  mov     edx, 3Fh ; '?'; void *
0x140042419  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
