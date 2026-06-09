# ClusWmi::DataStore::GetCurrentTokenModifiedIDAndSid(cxl::Token &,_LUID *,cxl::Sid *)

- ea: `0x1800198ec`
- end: `0x180019b03`
- name: `?GetCurrentTokenModifiedIDAndSid@DataStore@ClusWmi@@AEAA_NAEAVToken@cxl@@PEAU_LUID@@PEAVSid@4@@Z`
- size: `535`
- prototype: `bool(ClusWmi::DataStore *__hidden this, struct cxl::Token *, struct _LUID *, struct cxl::Sid *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800191d0`

## callees

- `0x180002b50`
- `0x18000c2f8`
- `0x18000e4b8`
- `0x180014620`
- `0x180014708`
- `0x180014878`
- `0x1800173f4`
- `0x1800198ec`
- `0x180019c64`
- `0x18003d7fc`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800199aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800199aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180019961`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180019961`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180019923`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180019923`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18001999a`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18001999a`

## string_xrefs

- `0x1800199d1`: `Could not duplicate process token, error = %d`
- `0x180019a12`: `The thread token could not be opened due to the impersonation level.  This is likely from an impersonation level less than RPC_C_IMP_LEVEL_IMPERSONATE.`
- `0x180019abe`: `Could not determine the user SID.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
bool __fastcall ClusWmi::DataStore::GetCurrentTokenModifiedIDAndSid(
        ClusWmi::DataStore *this,
        void **a2,
        struct _LUID *a3,
        struct cxl::Sid *a4)
{
  struct cxl::Sid *v4; // rsi
  void **v5; // rdi
  HANDLE CurrentThread; // rax
  unsigned int v7; // eax
  HANDLE CurrentProcess; // rax
  HANDLE v9; // rbx
  DWORD LastError; // r14d
  struct cxl::TraceManager *v11; // rax
  char *v12; // rbx
  char *v14; // rbx
  struct cxl::TraceManager *v15; // rax
  struct cxl::TraceManager *v16; // rax
  unsigned int WinError; // [rsp+30h] [rbp-A8h]
  DWORD v18[2]; // [rsp+38h] [rbp-A0h] BYREF
  struct _LUID *v19; // [rsp+40h] [rbp-98h]
  struct cxl::Sid *v20; // [rsp+48h] [rbp-90h]
  __int64 v21; // [rsp+50h] [rbp-88h] BYREF
  HANDLE ExistingTokenHandle; // [rsp+58h] [rbp-80h]
  std::system_error *v23; // [rsp+60h] [rbp-78h] BYREF
  const cxl::Exception *v24; // [rsp+68h] [rbp-70h] BYREF
  _OWORD v25[3]; // [rsp+78h] [rbp-60h] BYREF
  struct _LUID v26; // [rsp+A8h] [rbp-30h]

  v4 = a4;
  v5 = a2;
  *(_QWORD *)v18 = a2;
  v19 = a3;
  v20 = a4;
  CurrentThread = GetCurrentThread();
  v7 = cxl::Token::TryOpenThreadToken((cxl::Token *)v5, 8u, 0, CurrentThread);
  WinError = v7;
  if ( v7 == 1008 )
  {
    ExistingTokenHandle = 0;
    CurrentProcess = GetCurrentProcess();
    try
    {
      cxl::Token::OpenProcessToken((cxl::Token *)&v21, 0x2000Au, CurrentProcess);
      v9 = ExistingTokenHandle;
      LastError = 0;
      cxl::Token::Clear((cxl::Token *)v5);
      if ( !DuplicateToken(v9, SecurityImpersonation, v5 + 1) )
        LastError = GetLastError();
      WinError = LastError;
      if ( LastError )
      {
        v11 = cxl::TraceManager::Instance();
        cxl::TextWriter::WriteLine<char,unsigned long,>(
          (struct cxl::TraceManager *)((char *)v11 + 80),
          "Could not duplicate process token, error = %d");
      }
      cxl::Token::Clear((cxl::Token *)&v21);
    }
    catch ( std::system_error *v23 )
    {
      WinError = *((_DWORD *)v23 + 6);
      v15 = cxl::TraceManager::Instance();
      cxl::TextWriter::WriteLine<char,unsigned long,>(
        (struct cxl::TraceManager *)((char *)v15 + 80),
        "Could not open process token, system_error = %d");
      v5 = *(void ***)v18;
      v4 = v20;
    }
    catch ( const cxl::Exception *v24 )
    {
      v21 = *((_QWORD *)v24 + 11);
      WinError = cxl::ErrorCode::GetWinError((cxl::ErrorCode *)&v21);
      v16 = cxl::TraceManager::Instance();
      cxl::TextWriter::WriteLine<char,unsigned long,>(
        (struct cxl::TraceManager *)((char *)v16 + 80),
        "Could not open process token, WinError = %d");
      v5 = *(void ***)v18;
      v4 = v20;
    }
  }
  else if ( v7 == 1346 )
  {
    v12 = (char *)cxl::TraceManager::Instance() + 80;
    (*(void (__fastcall **)(char *, const char *, __int64))(*(_QWORD *)v12 + 16LL))(
      v12,
      "The thread token could not be opened due to the impersonation level.  This is likely from an impersonation level l"
      "ess than RPC_C_IMP_LEVEL_IMPERSONATE.",
      151);
    cxl::TextWriter::operator<<<cxl::ENDL>(v12);
  }
  if ( !WinError )
  {
    memset(v25, 0, sizeof(v25));
    v26 = 0;
    v18[0] = 0;
    if ( cxl::Token::GetInformation((cxl::Token *)v5, TokenStatistics, v25, 0x38u, v18) )
    {
      *v19 = v26;
      if ( cxl::Token::GetUserSid((cxl::Token *)v5, v4) )
        return *((_QWORD *)v4 + 2) != 0;
      v14 = (char *)cxl::TraceManager::Instance() + 40;
      (*(void (__fastcall **)(char *, const char *, __int64))(*(_QWORD *)v14 + 16LL))(
        v14,
        "Could not determine the user SID.",
        33);
      cxl::TextWriter::operator<<<cxl::ENDL>(v14);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800198ec  mov     [rsp+arg_0], rbx
0x1800198f1  push    rsi
0x1800198f2  push    rdi
0x1800198f3  push    r14
0x1800198f5  sub     rsp, 0C0h
0x1800198fc  mov     rax, cs:__security_cookie
0x180019903  xor     rax, rsp
0x180019906  mov     [rsp+0D8h+var_28], rax
0x18001990e  mov     rsi, r9
0x180019911  mov     rdi, rdx
0x180019914  mov     qword ptr [rsp+0D8h+var_A0], rdx
0x180019919  mov     [rsp+0D8h+var_98], r8
0x18001991e  mov     [rsp+0D8h+var_90], r9
0x180019923  call    cs:__imp_GetCurrentThread
0x18001992a  nop     dword ptr [rax+rax+00h]
0x18001992f  mov     r9, rax; void *
0x180019932  xor     r8d, r8d; int
0x180019935  lea     edx, [r8+8]; unsigned int
0x180019939  mov     rcx, rdi; this
0x18001993c  call    ?TryOpenThreadToken@Token@cxl@@QEAAKKHPEAX@Z; cxl::Token::TryOpenThreadToken(ulong,int,void *)
0x180019941  mov     [rsp+0D8h+var_A8], eax
0x180019945  cmp     eax, 3F0h
0x18001994a  jnz     loc_1800199F9
0x180019950  mov     [rsp+0D8h+var_A8], 0
0x180019958  mov     [rsp+0D8h+ExistingTokenHandle], 0
0x180019961  call    cs:__imp_GetCurrentProcess
0x180019968  nop     dword ptr [rax+rax+00h]
0x18001996d  mov     r8, rax; void *
0x180019970  mov     edx, 2000Ah; unsigned int
0x180019975  lea     rcx, [rsp+0D8h+var_88]; this
0x18001997a  call    ?OpenProcessToken@Token@cxl@@QEAAXKPEAX@Z; cxl::Token::OpenProcessToken(ulong,void *)
0x18001997f  mov     rbx, [rsp+0D8h+ExistingTokenHandle]
0x180019984  xor     r14d, r14d
0x180019987  mov     rcx, rdi; this
0x18001998a  call    ?Clear@Token@cxl@@QEAAXXZ; cxl::Token::Clear(void)
0x18001998f  lea     r8, [rdi+8]; DuplicateTokenHandle
0x180019993  lea     edx, [r14+2]; ImpersonationLevel
0x180019997  mov     rcx, rbx; ExistingTokenHandle
0x18001999a  call    cs:__imp_DuplicateToken
0x1800199a1  nop     dword ptr [rax+rax+00h]
0x1800199a6  test    eax, eax
0x1800199a8  jnz     short loc_1800199B9
0x1800199aa  call    cs:__imp_GetLastError
0x1800199b1  nop     dword ptr [rax+rax+00h]
0x1800199b6  mov     r14d, eax
0x1800199b9  mov     [rsp+0D8h+var_A8], r14d
0x1800199be  test    r14d, r14d
0x1800199c1  jz      short loc_1800199DE
0x1800199c3  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x1800199c8  lea     rcx, [rax+50h]; struct cxl::TextWriter *
0x1800199cc  lea     r8, [rsp+0D8h+var_A8]
0x1800199d1  lea     rdx, aCouldNotDuplic; "Could not duplicate process token, erro"...
0x1800199d8  call    ??$WriteLine@DK$$V@TextWriter@cxl@@QEAAXPEBDAEBK@Z; cxl::TextWriter::WriteLine<char,ulong,>(char const *,ulong const &)
0x1800199dd  nop
0x1800199de  lea     rcx, [rsp+0D8h+var_88]; this
0x1800199e3  call    ?Clear@Token@cxl@@QEAAXXZ; cxl::Token::Clear(void)
0x1800199e8  nop
0x1800199e9  jmp     short loc_180019A2D
0x1800199eb  jmp     short $+2
0x1800199ed  mov     rdi, qword ptr [rsp+0D8h+var_A0]
0x1800199f2  mov     rsi, [rsp+0D8h+var_90]
0x1800199f7  jmp     short loc_180019A2D
0x1800199f9  cmp     eax, 542h
0x1800199fe  jnz     short loc_180019A2D
0x180019a00  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180019a05  lea     rbx, [rax+50h]
0x180019a09  mov     rax, [rbx]
0x180019a0c  mov     r8d, 97h
0x180019a12  lea     rdx, aTheThreadToken; "The thread token could not be opened du"...
0x180019a19  mov     rcx, rbx
0x180019a1c  mov     rax, [rax+10h]
0x180019a20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a25  mov     rcx, rbx
0x180019a28  call    ??$?6UENDL@cxl@@@TextWriter@cxl@@QEAAAEAV01@AEBUENDL@1@@Z; cxl::TextWriter::operator<<<cxl::ENDL>(cxl::ENDL const &)
0x180019a2d  cmp     [rsp+0D8h+var_A8], 0
0x180019a32  jnz     loc_180019ADC
0x180019a38  xorps   xmm0, xmm0
0x180019a3b  xor     eax, eax
0x180019a3d  movups  [rsp+0D8h+var_60], xmm0
0x180019a42  movups  [rsp+0D8h+var_50], xmm0
0x180019a4a  movups  [rsp+0D8h+var_40], xmm0
0x180019a52  mov     [rsp+0D8h+var_30], rax
0x180019a5a  mov     [rsp+0D8h+var_A0], eax
0x180019a5e  lea     rax, [rsp+0D8h+var_A0]
0x180019a63  mov     [rsp+0D8h+var_B8], rax; PDWORD
0x180019a68  mov     r9d, 38h ; '8'; unsigned int
0x180019a6e  lea     r8, [rsp+0D8h+var_60]; void *
0x180019a73  lea     edx, [r9-2Eh]; enum _TOKEN_INFORMATION_CLASS
0x180019a77  mov     rcx, rdi; this
0x180019a7a  call    ?GetInformation@Token@cxl@@QEAA_NW4_TOKEN_INFORMATION_CLASS@@PEAXKPEAK@Z; cxl::Token::GetInformation(_TOKEN_INFORMATION_CLASS,void *,ulong,ulong *)
0x180019a7f  test    al, al
0x180019a81  jz      short loc_180019ADA
0x180019a83  mov     rdx, [rsp+0D8h+var_98]
0x180019a88  mov     rax, [rsp+0D8h+var_30]
0x180019a90  mov     [rdx], rax
0x180019a93  mov     rdx, rsi; struct cxl::Sid *
0x180019a96  mov     rcx, rdi; this
0x180019a99  call    ?GetUserSid@Token@cxl@@QEAA_NPEAVSid@2@@Z; cxl::Token::GetUserSid(cxl::Sid *)
0x180019a9e  test    al, al
0x180019aa0  jz      short loc_180019AAC
0x180019aa2  cmp     qword ptr [rsi+10h], 0
0x180019aa7  setnz   al
0x180019aaa  jmp     short loc_180019ADE
0x180019aac  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180019ab1  lea     rbx, [rax+28h]
0x180019ab5  mov     rax, [rbx]
0x180019ab8  mov     r8d, 21h ; '!'
0x180019abe  lea     rdx, aCouldNotDeterm; "Could not determine the user SID."
0x180019ac5  mov     rcx, rbx
0x180019ac8  mov     rax, [rax+10h]
0x180019acc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ad1  mov     rcx, rbx
0x180019ad4  call    ??$?6UENDL@cxl@@@TextWriter@cxl@@QEAAAEAV01@AEBUENDL@1@@Z; cxl::TextWriter::operator<<<cxl::ENDL>(cxl::ENDL const &)
0x180019ad9  nop
0x180019ada  jmp     short $+2
0x180019adc  xor     al, al
0x180019ade  mov     rcx, [rsp+0D8h+var_28]
0x180019ae6  xor     rcx, rsp; StackCookie
0x180019ae9  call    __security_check_cookie
0x180019aee  mov     rbx, [rsp+0D8h+arg_0]
0x180019af6  add     rsp, 0C0h
0x180019afd  pop     r14
0x180019aff  pop     rdi
0x180019b00  pop     rsi
0x180019b01  retn
```
