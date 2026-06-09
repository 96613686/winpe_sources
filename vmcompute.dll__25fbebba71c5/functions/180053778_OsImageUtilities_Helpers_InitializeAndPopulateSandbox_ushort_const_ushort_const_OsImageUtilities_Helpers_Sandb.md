# OsImageUtilities::Helpers::InitializeAndPopulateSandbox(ushort const *,ushort const *,OsImageUtilities::Helpers::SandboxOptions const &,_WC_NESTING_MODE)

- ea: `0x180053778`
- end: `0x1800539c0`
- name: `?InitializeAndPopulateSandbox@Helpers@OsImageUtilities@@YAXPEBG0AEBUSandboxOptions@12@W4_WC_NESTING_MODE@@@Z`
- size: `584`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800542e4`

## callees

- `0x180002f50`
- `0x180006660`
- `0x18000d108`
- `0x18002e454`
- `0x18002eb7c`
- `0x18002f94c`
- `0x1800343d8`
- `0x180039c70`
- `0x180053778`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005386b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005386b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18005385a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18005385a`
- `wc_storage!WcInitializeSandbox` at `0x18005380e`
- `wc_storage!WcInitializeSandbox` at `0x18005380e`
- `wc_storage!WcCreateSandboxStubFiles` at `0x1800538e9`
- `wc_storage!WcCreateSandboxStubFiles` at `0x1800538e9`

## string_xrefs

- `0x18005390d`: `onecore\vm\compute\dll\lib\storage\osimageutilities.cpp`
- `0x18005397f`: `onecore\vm\compute\dll\lib\storage\osimageutilities.cpp`
- `0x1800539ae`: `onecore\vm\compute\dll\lib\storage\osimageutilities.cpp`
- `0x1800538fe`: `relative path: %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall OsImageUtilities::Helpers::InitializeAndPopulateSandbox(
        const WCHAR *a1,
        const WCHAR *a2,
        unsigned __int64 *a3,
        unsigned int a4)
{
  int v8; // eax
  unsigned __int64 i; // rsi
  const WCHAR *v10; // rcx
  DWORD LastError; // eax
  unsigned __int64 v12; // rax
  const char *v13; // rbx
  char v14; // cl
  _QWORD *v15; // rax
  LPCWSTR *v16; // r9
  unsigned int SandboxStubFiles; // eax
  int v18; // [rsp+20h] [rbp-99h]
  char *v19; // [rsp+28h] [rbp-91h]
  LPCWSTR lpFileName[3]; // [rsp+40h] [rbp-79h] BYREF
  unsigned __int64 v21; // [rsp+58h] [rbp-61h]
  __int128 v22; // [rsp+60h] [rbp-59h] BYREF
  __int64 v23; // [rsp+70h] [rbp-49h]
  __int128 v24; // [rsp+78h] [rbp-41h] BYREF
  __int64 v25; // [rsp+88h] [rbp-31h]
  __int128 v26; // [rsp+90h] [rbp-29h] BYREF
  __int64 v27; // [rsp+A0h] [rbp-19h]
  _QWORD Src[4]; // [rsp+A8h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v26 = 0;
  v27 = 0;
  Vml::TemporaryPrivilege::TemporaryPrivilege((Vml::TemporaryPrivilege *)&v26, 17);
  v24 = 0;
  v25 = 0;
  Vml::TemporaryPrivilege::TemporaryPrivilege((Vml::TemporaryPrivilege *)&v24, 18);
  v22 = 0;
  v23 = 0;
  Vml::TemporaryPrivilege::TemporaryPrivilege((Vml::TemporaryPrivilege *)&v22, 10);
  v8 = WcInitializeSandbox(a1, a3[2], (__int64)(a3[3] - a3[2]) >> 5, a4);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x118,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\osimageutilities.cpp",
      (const char *)(unsigned int)v8,
      v18);
  for ( i = 0; i < *a3; ++i )
  {
    Vml::CombineFilePath(lpFileName, a2, *(PCWSTR *)(a3[1] + 16 * i));
    v10 = (const WCHAR *)lpFileName;
    if ( v21 > 7 )
      v10 = lpFileName[0];
    if ( GetFileAttributesW(v10) == -1 )
    {
      LastError = GetLastError();
      if ( LastError - 2 > 1 )
        wil::details::in1diag3::Throw_Win32Msg(
          retaddr,
          (void *)0x122,
          (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\osimageutilities.cpp",
          (const char *)LastError,
          (unsigned int)"%ws",
          *(const char **)(a3[1] + 16 * i));
    }
    else
    {
      Vml::CombineFilePath(Src, a1, *(PCWSTR *)(a3[1] + 16 * i));
      v12 = a3[1];
      v13 = *(const char **)(v12 + 16 * i);
      v14 = *(_BYTE *)(v12 + 16 * i + 8);
      v15 = Src;
      if ( Src[3] > 7u )
        v15 = (_QWORD *)Src[0];
      v16 = lpFileName;
      if ( v21 > 7 )
        v16 = (LPCWSTR *)lpFileName[0];
      LOBYTE(v19) = v14;
      SandboxStubFiles = WcCreateSandboxStubFiles(a1, a3[2], (__int64)(a3[3] - a3[2]) >> 5, v16, v15, v19, a4);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x132,
        (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\osimageutilities.cpp",
        (const char *)SandboxStubFiles,
        (int)"relative path: %ws",
        v13);
      std::wstring::~wstring(Src);
    }
    std::wstring::~wstring(lpFileName);
  }
  Vml::TemporaryPrivilege::~TemporaryPrivilege((Vml::TemporaryPrivilege *)&v22);
  Vml::TemporaryPrivilege::~TemporaryPrivilege((Vml::TemporaryPrivilege *)&v24);
  Vml::TemporaryPrivilege::~TemporaryPrivilege((Vml::TemporaryPrivilege *)&v26);
}

```

## disassembly

```asm
0x180053778  push    rbp
0x18005377a  push    rbx
0x18005377b  push    rsi
0x18005377c  push    rdi
0x18005377d  push    r12
0x18005377f  push    r13
0x180053781  push    r14
0x180053783  push    r15
0x180053785  lea     rbp, [rsp-1Fh]
0x18005378a  sub     rsp, 0D8h
0x180053791  mov     rax, cs:__security_cookie
0x180053798  xor     rax, rsp
0x18005379b  mov     [rbp+57h+var_48], rax
0x18005379f  mov     r13d, r9d
0x1800537a2  mov     rdi, r8
0x1800537a5  mov     r15, rdx
0x1800537a8  mov     r12, rcx
0x1800537ab  xorps   xmm0, xmm0
0x1800537ae  xor     eax, eax
0x1800537b0  movups  [rbp+57h+var_80], xmm0
0x1800537b4  mov     [rbp+57h+var_70], rax
0x1800537b8  lea     edx, [rax+11h]; int
0x1800537bb  lea     rcx, [rbp+57h+var_80]; this
0x1800537bf  call    ??0TemporaryPrivilege@Vml@@QEAA@J@Z; Vml::TemporaryPrivilege::TemporaryPrivilege(long)
0x1800537c4  nop
0x1800537c5  xorps   xmm0, xmm0
0x1800537c8  xor     eax, eax
0x1800537ca  movups  [rbp+57h+var_98], xmm0
0x1800537ce  mov     [rbp+57h+var_88], rax
0x1800537d2  lea     edx, [rax+12h]; int
0x1800537d5  lea     rcx, [rbp+57h+var_98]; this
0x1800537d9  call    ??0TemporaryPrivilege@Vml@@QEAA@J@Z; Vml::TemporaryPrivilege::TemporaryPrivilege(long)
0x1800537de  nop
0x1800537df  xorps   xmm0, xmm0
0x1800537e2  xor     eax, eax
0x1800537e4  movups  [rbp+57h+var_B0], xmm0
0x1800537e8  mov     [rbp+57h+var_A0], rax
0x1800537ec  lea     edx, [rax+0Ah]; int
0x1800537ef  lea     rcx, [rbp+57h+var_B0]; this
0x1800537f3  call    ??0TemporaryPrivilege@Vml@@QEAA@J@Z; Vml::TemporaryPrivilege::TemporaryPrivilege(long)
0x1800537f8  nop
0x1800537f9  mov     rdx, [rdi+10h]
0x1800537fd  mov     r8, [rdi+18h]
0x180053801  sub     r8, rdx
0x180053804  sar     r8, 5
0x180053808  mov     r9d, r13d
0x18005380b  mov     rcx, r12
0x18005380e  call    cs:__imp_WcInitializeSandbox
0x180053815  nop     dword ptr [rax+rax+00h]
0x18005381a  mov     rcx, [rbp+5Fh]; this
0x18005381e  test    eax, eax
0x180053820  js      loc_18005397C
0x180053826  xor     esi, esi
0x180053828  cmp     [rdi], rsi
0x18005382b  jbe     loc_18005393E
0x180053831  mov     r14, rsi
0x180053834  add     r14, r14
0x180053837  mov     r8, [rdi+8]
0x18005383b  mov     r8, [r8+r14*8]; pszMore
0x18005383f  mov     rdx, r15; pszPathIn
0x180053842  lea     rcx, [rbp+57h+lpFileName]; Src
0x180053846  call    ?CombineFilePath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; Vml::CombineFilePath(ushort const *,ushort const *)
0x18005384b  nop
0x18005384c  lea     rcx, [rbp+57h+lpFileName]
0x180053850  cmp     [rbp+57h+var_B8], 7
0x180053855  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x18005385a  call    cs:__imp_GetFileAttributesW
0x180053861  nop     dword ptr [rax+rax+00h]
0x180053866  cmp     eax, 0FFFFFFFFh
0x180053869  jnz     short loc_18005388B
0x18005386b  call    cs:__imp_GetLastError
0x180053872  nop     dword ptr [rax+rax+00h]
0x180053877  mov     r9d, eax; char *
0x18005387a  lea     ecx, [rax-2]
0x18005387d  cmp     ecx, 1
0x180053880  ja      loc_180053991
0x180053886  jmp     loc_180053929
0x18005388b  mov     r8, [rdi+8]
0x18005388f  mov     r8, [r8+r14*8]; pszMore
0x180053893  mov     rdx, r12; pszPathIn
0x180053896  lea     rcx, [rbp+57h+Src]; Src
0x18005389a  call    ?CombineFilePath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; Vml::CombineFilePath(ushort const *,ushort const *)
0x18005389f  nop
0x1800538a0  mov     rax, [rdi+8]
0x1800538a4  mov     rbx, [rax+r14*8]
0x1800538a8  mov     cl, [rax+r14*8+8]
0x1800538ad  lea     rax, [rbp+57h+Src]
0x1800538b1  cmp     [rbp+57h+var_50], 7
0x1800538b6  cmova   rax, [rbp+57h+Src]
0x1800538bb  lea     r9, [rbp+57h+lpFileName]
0x1800538bf  cmp     [rbp+57h+var_B8], 7
0x1800538c4  cmova   r9, [rbp+57h+lpFileName]
0x1800538c9  mov     rdx, [rdi+10h]
0x1800538cd  mov     r8, [rdi+18h]
0x1800538d1  sub     r8, rdx
0x1800538d4  sar     r8, 5
0x1800538d8  mov     [rsp+110h+var_E0], r13d
0x1800538dd  mov     byte ptr [rsp+110h+var_E8], cl
0x1800538e1  mov     qword ptr [rsp+110h+var_F0], rax
0x1800538e6  mov     rcx, r12
0x1800538e9  call    cs:__imp_WcCreateSandboxStubFiles
0x1800538f0  nop     dword ptr [rax+rax+00h]
0x1800538f5  mov     rcx, [rbp+5Fh]; this
0x1800538f9  mov     [rsp+110h+var_E8], rbx; char *
0x1800538fe  lea     rdx, aRelativePathWs; "relative path: %ws"
0x180053905  mov     qword ptr [rsp+110h+var_F0], rdx; int
0x18005390a  mov     r9d, eax; char *
0x18005390d  lea     r8, aOnecoreVmCompu_3; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x180053914  mov     edx, 132h; void *
0x180053919  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18005391e  nop
0x18005391f  lea     rcx, [rbp+57h+Src]
0x180053923  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180053928  nop
0x180053929  lea     rcx, [rbp+57h+lpFileName]
0x18005392d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180053932  inc     rsi
0x180053935  cmp     rsi, [rdi]
0x180053938  jb      loc_180053831
0x18005393e  lea     rcx, [rbp+57h+var_B0]; this
0x180053942  call    ??1TemporaryPrivilege@Vml@@QEAA@XZ; Vml::TemporaryPrivilege::~TemporaryPrivilege(void)
0x180053947  nop
0x180053948  lea     rcx, [rbp+57h+var_98]; this
0x18005394c  call    ??1TemporaryPrivilege@Vml@@QEAA@XZ; Vml::TemporaryPrivilege::~TemporaryPrivilege(void)
0x180053951  nop
0x180053952  lea     rcx, [rbp+57h+var_80]; this
0x180053956  call    ??1TemporaryPrivilege@Vml@@QEAA@XZ; Vml::TemporaryPrivilege::~TemporaryPrivilege(void)
0x18005395b  mov     rcx, [rbp+57h+var_48]
0x18005395f  xor     rcx, rsp; StackCookie
0x180053962  call    __security_check_cookie
0x180053967  add     rsp, 0D8h
0x18005396e  pop     r15
0x180053970  pop     r14
0x180053972  pop     r13
0x180053974  pop     r12
0x180053976  pop     rdi
0x180053977  pop     rsi
0x180053978  pop     rbx
0x180053979  pop     rbp
0x18005397a  retn
0x18005397c  mov     r9d, eax; char *
0x18005397f  lea     r8, aOnecoreVmCompu_3; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x180053986  mov     edx, 118h; void *
0x18005398b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180053991  mov     rax, [rdi+8]
0x180053995  mov     rcx, [rbp+5Fh]; this
0x180053999  mov     rax, [rax+r14*8]
0x18005399d  mov     [rsp+110h+var_E8], rax; char *
0x1800539a2  lea     rax, aWs; "%ws"
0x1800539a9  mov     qword ptr [rsp+110h+var_F0], rax; unsigned int
0x1800539ae  lea     r8, aOnecoreVmCompu_3; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x1800539b5  mov     edx, 122h; void *
0x1800539ba  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
```
