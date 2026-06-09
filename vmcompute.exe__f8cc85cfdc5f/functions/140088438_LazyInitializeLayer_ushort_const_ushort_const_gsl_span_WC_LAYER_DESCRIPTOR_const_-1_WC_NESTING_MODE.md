# LazyInitializeLayer(ushort const *,ushort const *,gsl::span<_WC_LAYER_DESCRIPTOR const,-1>,_WC_NESTING_MODE)

- ea: `0x140088438`
- end: `0x14008868f`
- name: `?LazyInitializeLayer@@YAXPEBG0V?$span@$$CBU_WC_LAYER_DESCRIPTOR@@$0?0@gsl@@W4_WC_NESTING_MODE@@@Z`
- size: `599`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400ac778`

## callees

- `0x140017040`
- `0x140024030`
- `0x140080180`
- `0x140087ef4`
- `0x1400881e4`
- `0x140088438`
- `0x140088698`
- `0x140088724`
- `0x140089850`
- `0x1400aaf6c`
- `0x1400c40e0`
- `0x1401332f0`
- `0x1402335cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400884f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400884f2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400885f4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400885f4`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1400884c1`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1400884c1`
- `wc_storage!WcInitializeSandboxEx` at `0x140088598`
- `wc_storage!WcInitializeSandboxEx` at `0x140088598`

## string_xrefs

- `0x1400884de`: `onecore\vm\compute\shared\storage\layerutilities.cpp`
- `0x1400885af`: `onecore\vm\compute\shared\storage\layerutilities.cpp`
- `0x140088618`: `onecore\vm\compute\shared\storage\layerutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall LazyInitializeLayer(__int64 a1, __int64 a2, unsigned int *a3)
{
  const WCHAR *v5; // rdx
  const WCHAR *v6; // rcx
  const char *v7; // r9
  char v8; // bl
  char v9; // al
  unsigned __int16 **v10; // rdx
  const unsigned __int16 *v11; // rdx
  PCWSTR *v12; // rdx
  unsigned __int16 **v13; // rcx
  int v14; // eax
  const WCHAR *v15; // rcx
  const char *v16; // r9
  void *v17[2]; // [rsp+40h] [rbp-79h] BYREF
  __int128 v18; // [rsp+50h] [rbp-69h] BYREF
  unsigned __int16 *v19[3]; // [rsp+60h] [rbp-59h] BYREF
  unsigned __int64 v20; // [rsp+78h] [rbp-41h]
  LPCWSTR lpFileName[3]; // [rsp+80h] [rbp-39h] BYREF
  unsigned __int64 v22; // [rsp+98h] [rbp-21h]
  PCWSTR pszPathIn[3]; // [rsp+A0h] [rbp-19h] BYREF
  unsigned __int64 v24; // [rsp+B8h] [rbp-1h]
  struct _LUID v25[2]; // [rsp+C0h] [rbp+7h] BYREF
  __int64 v26; // [rsp+D0h] [rbp+17h]
  struct _LUID v27[2]; // [rsp+D8h] [rbp+1Fh] BYREF
  __int64 v28; // [rsp+E8h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v18 = *(_OWORD *)a3;
  SandboxStatePath(pszPathIn, a1, a3, &v18);
  *(_OWORD *)&v27[0].LowPart = 0;
  v28 = 0;
  Vml::TemporaryPrivilege::TemporaryPrivilege(v27, 17);
  v5 = (const WCHAR *)pszPathIn;
  if ( v24 > 7 )
    v5 = pszPathIn[0];
  CommonUtilities::CombineFilePath((PWSTR)lpFileName, v5, L"initialized");
  v6 = (const WCHAR *)lpFileName;
  if ( v22 > 7 )
    v6 = lpFileName[0];
  if ( GetFileAttributesW(v6) != -1 )
  {
    v8 = 1;
LABEL_7:
    v9 = 0;
    goto LABEL_8;
  }
  v8 = 0;
  if ( GetLastError() == 2 )
    goto LABEL_7;
  v9 = 1;
LABEL_8:
  if ( v9 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x2E,
      (unsigned int)"onecore\\vm\\compute\\shared\\storage\\layerutilities.cpp",
      v7);
  if ( !v8 )
  {
    Vml::PathEnsureBackslash(v19, a1);
    v17[0] = 0;
    v10 = v19;
    if ( v20 > 7 )
      v10 = (unsigned __int16 **)v19[0];
    GetDiskHandle(v17, v10);
    v11 = (const unsigned __int16 *)v19;
    if ( v20 > 7 )
      v11 = v19[0];
    ExpandVolume(v17[0], v11);
    *(_OWORD *)&v25[0].LowPart = 0;
    v26 = 0;
    Vml::TemporaryPrivilege::TemporaryPrivilege(v25, 18);
    v12 = pszPathIn;
    if ( v24 > 7 )
      v12 = (PCWSTR *)pszPathIn[0];
    v13 = v19;
    if ( v20 > 7 )
      v13 = (unsigned __int16 **)v19[0];
    v14 = WcInitializeSandboxEx(v13, v12, *((_QWORD *)a3 + 1), *a3);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3F,
        (unsigned int)"onecore\\vm\\compute\\shared\\storage\\layerutilities.cpp",
        (const char *)(unsigned int)v14,
        0);
    v15 = (const WCHAR *)lpFileName;
    if ( v22 > 7 )
      v15 = lpFileName[0];
    *(_QWORD *)&v18 = CreateFileW(v15, 0x40000000u, 3u, 0, 1u, 0x2000000u, 0);
    if ( (((_QWORD)v18 + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x4A,
        (unsigned int)"onecore\\vm\\compute\\shared\\storage\\layerutilities.cpp",
        v16);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v18);
    Vml::TemporaryPrivilege::~TemporaryPrivilege(v25);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v17);
    Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v19);
  }
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)lpFileName);
  Vml::TemporaryPrivilege::~TemporaryPrivilege(v27);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)pszPathIn);
}

```

## disassembly

```asm
0x140088438  mov     [rsp-8+arg_8], rbx
0x14008843d  push    rbp
0x14008843e  push    rsi
0x14008843f  push    rdi
0x140088440  lea     rbp, [rsp-47h]
0x140088445  sub     rsp, 100h
0x14008844c  mov     rax, cs:__security_cookie
0x140088453  xor     rax, rsp
0x140088456  mov     [rbp+57h+var_20], rax
0x14008845a  mov     rdi, r8
0x14008845d  mov     rsi, rcx
0x140088460  movaps  xmm0, xmmword ptr [r8]
0x140088464  movdqa  [rbp+57h+var_C0], xmm0
0x140088469  lea     r9, [rbp+57h+var_C0]
0x14008846d  mov     rdx, rcx
0x140088470  lea     rcx, [rbp+57h+pszPathIn]
0x140088474  call    ?SandboxStatePath@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0V?$span@$$CBU_WC_LAYER_DESCRIPTOR@@$0?0@gsl@@@Z; SandboxStatePath(ushort const *,ushort const *,gsl::span<_WC_LAYER_DESCRIPTOR const,-1>)
0x140088479  nop
0x14008847a  xorps   xmm0, xmm0
0x14008847d  xor     eax, eax
0x14008847f  movups  xmmword ptr [rbp+57h+var_38.LowPart], xmm0
0x140088483  mov     [rbp+57h+var_28], rax
0x140088487  lea     edx, [rax+11h]; int
0x14008848a  lea     rcx, [rbp+57h+var_38]; this
0x14008848e  call    ??0TemporaryPrivilege@Vml@@QEAA@J@Z; Vml::TemporaryPrivilege::TemporaryPrivilege(long)
0x140088493  nop
0x140088494  lea     rdx, [rbp+57h+pszPathIn]
0x140088498  cmp     [rbp+57h+var_58], 7
0x14008849d  cmova   rdx, [rbp+57h+pszPathIn]; pszPathIn
0x1400884a2  lea     r8, pszMore; "initialized"
0x1400884a9  lea     rcx, [rbp+57h+lpFileName]; pszPathOut
0x1400884ad  call    ?CombineFilePath@CommonUtilities@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; CommonUtilities::CombineFilePath(ushort const *,ushort const *)
0x1400884b2  nop
0x1400884b3  lea     rcx, [rbp+57h+lpFileName]
0x1400884b7  cmp     [rbp+57h+var_78], 7
0x1400884bc  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x1400884c1  call    cs:__imp_GetFileAttributesW
0x1400884c8  nop     dword ptr [rax+rax+00h]
0x1400884cd  cmp     eax, 0FFFFFFFFh
0x1400884d0  jz      short loc_1400884F0
0x1400884d2  mov     bl, 1
0x1400884d4  xor     al, al
0x1400884d6  mov     rcx, [rbp+5Fh]; this
0x1400884da  test    al, al
0x1400884dc  jz      short loc_140088507
0x1400884de  lea     r8, aOnecoreVmCompu_83; "onecore\\vm\\compute\\shared\\storage\\"...
0x1400884e5  mov     edx, 2Eh ; '.'; void *
0x1400884ea  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400884f0  xor     bl, bl
0x1400884f2  call    cs:__imp_GetLastError
0x1400884f9  nop     dword ptr [rax+rax+00h]
0x1400884fe  cmp     eax, 2
0x140088501  jz      short loc_1400884D4
0x140088503  mov     al, 1
0x140088505  jmp     short loc_1400884D6
0x140088507  test    bl, bl
0x140088509  jnz     loc_140088652
0x14008850f  mov     rdx, rsi
0x140088512  lea     rcx, [rbp+57h+var_B0]
0x140088516  call    ?PathEnsureBackslash@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; Vml::PathEnsureBackslash(ushort const *)
0x14008851b  nop
0x14008851c  mov     [rbp+57h+var_D0], 0
0x140088524  lea     rdx, [rbp+57h+var_B0]
0x140088528  cmp     [rbp+57h+var_98], 7
0x14008852d  cmova   rdx, [rbp+57h+var_B0]
0x140088532  lea     rcx, [rbp+57h+var_D0]
0x140088536  call    ?GetDiskHandle@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEBG@Z; GetDiskHandle(ushort const *)
0x14008853b  nop
0x14008853c  lea     rdx, [rbp+57h+var_B0]
0x140088540  cmp     [rbp+57h+var_98], 7
0x140088545  cmova   rdx, [rbp+57h+var_B0]; unsigned __int16 *
0x14008854a  mov     rcx, [rbp+57h+var_D0]; void *
0x14008854e  call    ?ExpandVolume@@YA_NPEAXPEBG@Z; ExpandVolume(void *,ushort const *)
0x140088553  xorps   xmm0, xmm0
0x140088556  xor     eax, eax
0x140088558  movups  xmmword ptr [rbp+57h+var_50.LowPart], xmm0
0x14008855c  mov     [rbp+57h+var_40], rax
0x140088560  lea     edx, [rax+12h]; int
0x140088563  lea     rcx, [rbp+57h+var_50]; this
0x140088567  call    ??0TemporaryPrivilege@Vml@@QEAA@J@Z; Vml::TemporaryPrivilege::TemporaryPrivilege(long)
0x14008856c  nop
0x14008856d  lea     rdx, [rbp+57h+pszPathIn]
0x140088571  cmp     [rbp+57h+var_58], 7
0x140088576  cmova   rdx, [rbp+57h+pszPathIn]
0x14008857b  lea     rcx, [rbp+57h+var_B0]
0x14008857f  cmp     [rbp+57h+var_98], 7
0x140088584  cmova   rcx, [rbp+57h+var_B0]
0x140088589  mov     [rsp+110h+dwCreationDisposition], 0; int
0x140088591  mov     r9d, [rdi]
0x140088594  mov     r8, [rdi+8]
0x140088598  call    cs:__imp_WcInitializeSandboxEx
0x14008859f  nop     dword ptr [rax+rax+00h]
0x1400885a4  mov     rcx, [rbp+5Fh]; this
0x1400885a8  test    eax, eax
0x1400885aa  jns     short loc_1400885C1
0x1400885ac  mov     r9d, eax; char *
0x1400885af  lea     r8, aOnecoreVmCompu_83; "onecore\\vm\\compute\\shared\\storage\\"...
0x1400885b6  mov     edx, 3Fh ; '?'; void *
0x1400885bb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400885c1  lea     rcx, [rbp+57h+lpFileName]
0x1400885c5  cmp     [rbp+57h+var_78], 7
0x1400885ca  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x1400885cf  mov     [rsp+110h+hTemplateFile], 0; hTemplateFile
0x1400885d8  mov     [rsp+110h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x1400885e0  mov     [rsp+110h+dwCreationDisposition], 1; dwCreationDisposition
0x1400885e8  xor     r9d, r9d; lpSecurityAttributes
0x1400885eb  mov     edx, 40000000h; dwDesiredAccess
0x1400885f0  lea     r8d, [r9+3]; dwShareMode
0x1400885f4  call    cs:__imp_CreateFileW
0x1400885fb  nop     dword ptr [rax+rax+00h]
0x140088600  mov     qword ptr [rbp+57h+var_C0], rax
0x140088604  inc     rax
0x140088607  test    rax, 0FFFFFFFFFFFFFFFEh
0x14008860d  setz    al
0x140088610  mov     rcx, [rbp+5Fh]; this
0x140088614  test    al, al
0x140088616  jz      short loc_14008862A
0x140088618  lea     r8, aOnecoreVmCompu_83; "onecore\\vm\\compute\\shared\\storage\\"...
0x14008861f  mov     edx, 4Ah ; 'J'; void *
0x140088624  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14008862a  lea     rcx, [rbp+57h+var_C0]; void *
0x14008862e  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x140088633  nop
0x140088634  lea     rcx, [rbp+57h+var_50]; this
0x140088638  call    ??1TemporaryPrivilege@Vml@@QEAA@XZ; Vml::TemporaryPrivilege::~TemporaryPrivilege(void)
0x14008863d  nop
0x14008863e  lea     rcx, [rbp+57h+var_D0]; void *
0x140088642  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x140088647  nop
0x140088648  lea     rcx, [rbp+57h+var_B0]; this
0x14008864c  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x140088651  nop
0x140088652  lea     rcx, [rbp+57h+lpFileName]; this
0x140088656  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x14008865b  nop
0x14008865c  lea     rcx, [rbp+57h+var_38]; this
0x140088660  call    ??1TemporaryPrivilege@Vml@@QEAA@XZ; Vml::TemporaryPrivilege::~TemporaryPrivilege(void)
0x140088665  nop
0x140088666  lea     rcx, [rbp+57h+pszPathIn]; this
0x14008866a  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x14008866f  mov     rcx, [rbp+57h+var_20]
0x140088673  xor     rcx, rsp; StackCookie
0x140088676  call    __security_check_cookie
0x14008867b  mov     rbx, [rsp+110h+arg_8]
0x140088683  add     rsp, 100h
0x14008868a  pop     rdi
0x14008868b  pop     rsi
0x14008868c  pop     rbp
0x14008868d  retn
```
