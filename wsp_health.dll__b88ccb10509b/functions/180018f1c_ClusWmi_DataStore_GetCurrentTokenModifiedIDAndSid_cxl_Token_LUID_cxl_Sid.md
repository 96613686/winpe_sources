# ClusWmi::DataStore::GetCurrentTokenModifiedIDAndSid(cxl::Token &,_LUID *,cxl::Sid *)

- ea: `0x180018f1c`
- end: `0x18001911b`
- name: `?GetCurrentTokenModifiedIDAndSid@DataStore@ClusWmi@@AEAA_NAEAVToken@cxl@@PEAU_LUID@@PEAVSid@4@@Z`
- size: `511`
- prototype: `bool(ClusWmi::DataStore *__hidden this, struct cxl::Token *, struct _LUID *, struct cxl::Sid *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001880c`

## callees

- `0x180002ae0`
- `0x18000bf68`
- `0x18000e044`
- `0x180013ec0`
- `0x180013f94`
- `0x1800140e8`
- `0x180016aa8`
- `0x180018f1c`
- `0x180019274`
- `0x18003c200`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018fc8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018fc8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180018f8b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180018f8b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180018f53`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180018f53`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180018fbe`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180018fbe`

## string_xrefs

- `0x180018fe9`: `Could not duplicate process token, error = %d`
- `0x1800190d6`: `Could not determine the user SID.`
- `0x18001902a`: `The thread token could not be opened due to the impersonation level.  This is likely from an impersonation level less than RPC_C_IMP_LEVEL_IMPERSONATE.`

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
    cxl::TextWriter::operator<<<cxl::ENDL>((__int64)v12);
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
      cxl::TextWriter::operator<<<cxl::ENDL>((__int64)v14);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180018f1c  mov     [rsp+arg_0], rbx
0x180018f21  push    rsi
0x180018f22  push    rdi
0x180018f23  push    r14
0x180018f25  sub     rsp, 0C0h
0x180018f2c  mov     rax, cs:__security_cookie
0x180018f33  xor     rax, rsp
0x180018f36  mov     [rsp+0D8h+var_28], rax
0x180018f3e  mov     rsi, r9
0x180018f41  mov     rdi, rdx
0x180018f44  mov     qword ptr [rsp+0D8h+var_A0], rdx
0x180018f49  mov     [rsp+0D8h+var_98], r8
0x180018f4e  mov     [rsp+0D8h+var_90], r9
0x180018f53  call    cs:__imp_GetCurrentThread
0x180018f59  mov     r9, rax; void *
0x180018f5c  xor     r8d, r8d; int
0x180018f5f  lea     edx, [r8+8]; unsigned int
0x180018f63  mov     rcx, rdi; this
0x180018f66  call    ?TryOpenThreadToken@Token@cxl@@QEAAKKHPEAX@Z; cxl::Token::TryOpenThreadToken(ulong,int,void *)
0x180018f6b  mov     [rsp+0D8h+var_A8], eax
0x180018f6f  cmp     eax, 3F0h
0x180018f74  jnz     loc_180019011
0x180018f7a  mov     [rsp+0D8h+var_A8], 0
0x180018f82  mov     [rsp+0D8h+ExistingTokenHandle], 0
0x180018f8b  call    cs:__imp_GetCurrentProcess
0x180018f91  mov     r8, rax; void *
0x180018f94  mov     edx, 2000Ah; unsigned int
0x180018f99  lea     rcx, [rsp+0D8h+var_88]; this
0x180018f9e  call    ?OpenProcessToken@Token@cxl@@QEAAXKPEAX@Z; cxl::Token::OpenProcessToken(ulong,void *)
0x180018fa3  mov     rbx, [rsp+0D8h+ExistingTokenHandle]
0x180018fa8  xor     r14d, r14d
0x180018fab  mov     rcx, rdi; this
0x180018fae  call    ?Clear@Token@cxl@@QEAAXXZ; cxl::Token::Clear(void)
0x180018fb3  lea     r8, [rdi+8]; DuplicateTokenHandle
0x180018fb7  lea     edx, [r14+2]; ImpersonationLevel
0x180018fbb  mov     rcx, rbx; ExistingTokenHandle
0x180018fbe  call    cs:__imp_DuplicateToken
0x180018fc4  test    eax, eax
0x180018fc6  jnz     short loc_180018FD1
0x180018fc8  call    cs:__imp_GetLastError
0x180018fce  mov     r14d, eax
0x180018fd1  mov     [rsp+0D8h+var_A8], r14d
0x180018fd6  test    r14d, r14d
0x180018fd9  jz      short loc_180018FF6
0x180018fdb  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180018fe0  lea     rcx, [rax+50h]; struct cxl::TextWriter *
0x180018fe4  lea     r8, [rsp+0D8h+var_A8]
0x180018fe9  lea     rdx, aCouldNotDuplic; "Could not duplicate process token, erro"...
0x180018ff0  call    ??$WriteLine@DK$$V@TextWriter@cxl@@QEAAXPEBDAEBK@Z; cxl::TextWriter::WriteLine<char,ulong,>(char const *,ulong const &)
0x180018ff5  nop
0x180018ff6  lea     rcx, [rsp+0D8h+var_88]; this
0x180018ffb  call    ?Clear@Token@cxl@@QEAAXXZ; cxl::Token::Clear(void)
0x180019000  nop
0x180019001  jmp     short loc_180019045
0x180019003  jmp     short $+2
0x180019005  mov     rdi, qword ptr [rsp+0D8h+var_A0]
0x18001900a  mov     rsi, [rsp+0D8h+var_90]
0x18001900f  jmp     short loc_180019045
0x180019011  cmp     eax, 542h
0x180019016  jnz     short loc_180019045
0x180019018  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18001901d  lea     rbx, [rax+50h]
0x180019021  mov     rax, [rbx]
0x180019024  mov     r8d, 97h
0x18001902a  lea     rdx, aTheThreadToken; "The thread token could not be opened du"...
0x180019031  mov     rcx, rbx
0x180019034  mov     rax, [rax+10h]
0x180019038  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001903d  mov     rcx, rbx
0x180019040  call    ??$?6UENDL@cxl@@@TextWriter@cxl@@QEAAAEAV01@AEBUENDL@1@@Z; cxl::TextWriter::operator<<<cxl::ENDL>(cxl::ENDL const &)
0x180019045  cmp     [rsp+0D8h+var_A8], 0
0x18001904a  jnz     loc_1800190F4
0x180019050  xorps   xmm0, xmm0
0x180019053  xor     eax, eax
0x180019055  movups  [rsp+0D8h+var_60], xmm0
0x18001905a  movups  [rsp+0D8h+var_50], xmm0
0x180019062  movups  [rsp+0D8h+var_40], xmm0
0x18001906a  mov     [rsp+0D8h+var_30], rax
0x180019072  mov     [rsp+0D8h+var_A0], eax
0x180019076  lea     rax, [rsp+0D8h+var_A0]
0x18001907b  mov     [rsp+0D8h+var_B8], rax; PDWORD
0x180019080  mov     r9d, 38h ; '8'; unsigned int
0x180019086  lea     r8, [rsp+0D8h+var_60]; void *
0x18001908b  lea     edx, [r9-2Eh]; enum _TOKEN_INFORMATION_CLASS
0x18001908f  mov     rcx, rdi; this
0x180019092  call    ?GetInformation@Token@cxl@@QEAA_NW4_TOKEN_INFORMATION_CLASS@@PEAXKPEAK@Z; cxl::Token::GetInformation(_TOKEN_INFORMATION_CLASS,void *,ulong,ulong *)
0x180019097  test    al, al
0x180019099  jz      short loc_1800190F2
0x18001909b  mov     rdx, [rsp+0D8h+var_98]
0x1800190a0  mov     rax, [rsp+0D8h+var_30]
0x1800190a8  mov     [rdx], rax
0x1800190ab  mov     rdx, rsi; struct cxl::Sid *
0x1800190ae  mov     rcx, rdi; this
0x1800190b1  call    ?GetUserSid@Token@cxl@@QEAA_NPEAVSid@2@@Z; cxl::Token::GetUserSid(cxl::Sid *)
0x1800190b6  test    al, al
0x1800190b8  jz      short loc_1800190C4
0x1800190ba  cmp     qword ptr [rsi+10h], 0
0x1800190bf  setnz   al
0x1800190c2  jmp     short loc_1800190F6
0x1800190c4  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x1800190c9  lea     rbx, [rax+28h]
0x1800190cd  mov     rax, [rbx]
0x1800190d0  mov     r8d, 21h ; '!'
0x1800190d6  lea     rdx, aCouldNotDeterm; "Could not determine the user SID."
0x1800190dd  mov     rcx, rbx
0x1800190e0  mov     rax, [rax+10h]
0x1800190e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800190e9  mov     rcx, rbx
0x1800190ec  call    ??$?6UENDL@cxl@@@TextWriter@cxl@@QEAAAEAV01@AEBUENDL@1@@Z; cxl::TextWriter::operator<<<cxl::ENDL>(cxl::ENDL const &)
0x1800190f1  nop
0x1800190f2  jmp     short $+2
0x1800190f4  xor     al, al
0x1800190f6  mov     rcx, [rsp+0D8h+var_28]
0x1800190fe  xor     rcx, rsp; StackCookie
0x180019101  call    __security_check_cookie
0x180019106  mov     rbx, [rsp+0D8h+arg_0]
0x18001910e  add     rsp, 0C0h
0x180019115  pop     r14
0x180019117  pop     rdi
0x180019118  pop     rsi
0x180019119  retn
```
