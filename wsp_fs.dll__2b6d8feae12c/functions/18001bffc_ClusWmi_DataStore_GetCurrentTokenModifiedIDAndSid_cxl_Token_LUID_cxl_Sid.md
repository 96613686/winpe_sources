# ClusWmi::DataStore::GetCurrentTokenModifiedIDAndSid(cxl::Token &,_LUID *,cxl::Sid *)

- ea: `0x18001bffc`
- end: `0x18001c1fb`
- name: `?GetCurrentTokenModifiedIDAndSid@DataStore@ClusWmi@@AEAA_NAEAVToken@cxl@@PEAU_LUID@@PEAVSid@4@@Z`
- size: `511`
- prototype: `bool(ClusWmi::DataStore *__hidden this, struct cxl::Token *, struct _LUID *, struct cxl::Sid *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001b8ec`

## callees

- `0x180002a70`
- `0x18000c9dc`
- `0x18000e6f4`
- `0x1800154e0`
- `0x180015968`
- `0x180015b9c`
- `0x180019bb0`
- `0x18001bffc`
- `0x18001c354`
- `0x1800714f8`
- `0x1800a9010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c0a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c0a8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001c06b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001c06b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001c033`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001c033`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18001c09e`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18001c09e`

## string_xrefs

- `0x18001c0c9`: `Could not duplicate process token, error = %d`
- `0x18001c1b6`: `Could not determine the user SID.`
- `0x18001c10a`: `The thread token could not be opened due to the impersonation level.  This is likely from an impersonation level less than RPC_C_IMP_LEVEL_IMPERSONATE.`

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
0x18001bffc  mov     [rsp+arg_0], rbx
0x18001c001  push    rsi
0x18001c002  push    rdi
0x18001c003  push    r14
0x18001c005  sub     rsp, 0C0h
0x18001c00c  mov     rax, cs:__security_cookie
0x18001c013  xor     rax, rsp
0x18001c016  mov     [rsp+0D8h+var_28], rax
0x18001c01e  mov     rsi, r9
0x18001c021  mov     rdi, rdx
0x18001c024  mov     qword ptr [rsp+0D8h+var_A0], rdx
0x18001c029  mov     [rsp+0D8h+var_98], r8
0x18001c02e  mov     [rsp+0D8h+var_90], r9
0x18001c033  call    cs:__imp_GetCurrentThread
0x18001c039  mov     r9, rax; void *
0x18001c03c  xor     r8d, r8d; int
0x18001c03f  lea     edx, [r8+8]; unsigned int
0x18001c043  mov     rcx, rdi; this
0x18001c046  call    ?TryOpenThreadToken@Token@cxl@@QEAAKKHPEAX@Z; cxl::Token::TryOpenThreadToken(ulong,int,void *)
0x18001c04b  mov     [rsp+0D8h+var_A8], eax
0x18001c04f  cmp     eax, 3F0h
0x18001c054  jnz     loc_18001C0F1
0x18001c05a  mov     [rsp+0D8h+var_A8], 0
0x18001c062  mov     [rsp+0D8h+ExistingTokenHandle], 0
0x18001c06b  call    cs:__imp_GetCurrentProcess
0x18001c071  mov     r8, rax; void *
0x18001c074  mov     edx, 2000Ah; unsigned int
0x18001c079  lea     rcx, [rsp+0D8h+var_88]; this
0x18001c07e  call    ?OpenProcessToken@Token@cxl@@QEAAXKPEAX@Z; cxl::Token::OpenProcessToken(ulong,void *)
0x18001c083  mov     rbx, [rsp+0D8h+ExistingTokenHandle]
0x18001c088  xor     r14d, r14d
0x18001c08b  mov     rcx, rdi; this
0x18001c08e  call    ?Clear@Token@cxl@@QEAAXXZ; cxl::Token::Clear(void)
0x18001c093  lea     r8, [rdi+8]; DuplicateTokenHandle
0x18001c097  lea     edx, [r14+2]; ImpersonationLevel
0x18001c09b  mov     rcx, rbx; ExistingTokenHandle
0x18001c09e  call    cs:__imp_DuplicateToken
0x18001c0a4  test    eax, eax
0x18001c0a6  jnz     short loc_18001C0B1
0x18001c0a8  call    cs:__imp_GetLastError
0x18001c0ae  mov     r14d, eax
0x18001c0b1  mov     [rsp+0D8h+var_A8], r14d
0x18001c0b6  test    r14d, r14d
0x18001c0b9  jz      short loc_18001C0D6
0x18001c0bb  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18001c0c0  lea     rcx, [rax+50h]; struct cxl::TextWriter *
0x18001c0c4  lea     r8, [rsp+0D8h+var_A8]
0x18001c0c9  lea     rdx, aCouldNotDuplic; "Could not duplicate process token, erro"...
0x18001c0d0  call    ??$WriteLine@DK$$V@TextWriter@cxl@@QEAAXPEBDAEBK@Z; cxl::TextWriter::WriteLine<char,ulong,>(char const *,ulong const &)
0x18001c0d5  nop
0x18001c0d6  lea     rcx, [rsp+0D8h+var_88]; this
0x18001c0db  call    ?Clear@Token@cxl@@QEAAXXZ; cxl::Token::Clear(void)
0x18001c0e0  nop
0x18001c0e1  jmp     short loc_18001C125
0x18001c0e3  jmp     short $+2
0x18001c0e5  mov     rdi, qword ptr [rsp+0D8h+var_A0]
0x18001c0ea  mov     rsi, [rsp+0D8h+var_90]
0x18001c0ef  jmp     short loc_18001C125
0x18001c0f1  cmp     eax, 542h
0x18001c0f6  jnz     short loc_18001C125
0x18001c0f8  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18001c0fd  lea     rbx, [rax+50h]
0x18001c101  mov     rax, [rbx]
0x18001c104  mov     r8d, 97h
0x18001c10a  lea     rdx, aTheThreadToken; "The thread token could not be opened du"...
0x18001c111  mov     rcx, rbx
0x18001c114  mov     rax, [rax+10h]
0x18001c118  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c11d  mov     rcx, rbx
0x18001c120  call    ??$?6UENDL@cxl@@@TextWriter@cxl@@QEAAAEAV01@AEBUENDL@1@@Z; cxl::TextWriter::operator<<<cxl::ENDL>(cxl::ENDL const &)
0x18001c125  cmp     [rsp+0D8h+var_A8], 0
0x18001c12a  jnz     loc_18001C1D4
0x18001c130  xorps   xmm0, xmm0
0x18001c133  xor     eax, eax
0x18001c135  movups  [rsp+0D8h+var_60], xmm0
0x18001c13a  movups  [rsp+0D8h+var_50], xmm0
0x18001c142  movups  [rsp+0D8h+var_40], xmm0
0x18001c14a  mov     [rsp+0D8h+var_30], rax
0x18001c152  mov     [rsp+0D8h+var_A0], eax
0x18001c156  lea     rax, [rsp+0D8h+var_A0]
0x18001c15b  mov     [rsp+0D8h+var_B8], rax; PDWORD
0x18001c160  mov     r9d, 38h ; '8'; unsigned int
0x18001c166  lea     r8, [rsp+0D8h+var_60]; void *
0x18001c16b  lea     edx, [r9-2Eh]; enum _TOKEN_INFORMATION_CLASS
0x18001c16f  mov     rcx, rdi; this
0x18001c172  call    ?GetInformation@Token@cxl@@QEAA_NW4_TOKEN_INFORMATION_CLASS@@PEAXKPEAK@Z; cxl::Token::GetInformation(_TOKEN_INFORMATION_CLASS,void *,ulong,ulong *)
0x18001c177  test    al, al
0x18001c179  jz      short loc_18001C1D2
0x18001c17b  mov     rdx, [rsp+0D8h+var_98]
0x18001c180  mov     rax, [rsp+0D8h+var_30]
0x18001c188  mov     [rdx], rax
0x18001c18b  mov     rdx, rsi; struct cxl::Sid *
0x18001c18e  mov     rcx, rdi; this
0x18001c191  call    ?GetUserSid@Token@cxl@@QEAA_NPEAVSid@2@@Z; cxl::Token::GetUserSid(cxl::Sid *)
0x18001c196  test    al, al
0x18001c198  jz      short loc_18001C1A4
0x18001c19a  cmp     qword ptr [rsi+10h], 0
0x18001c19f  setnz   al
0x18001c1a2  jmp     short loc_18001C1D6
0x18001c1a4  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18001c1a9  lea     rbx, [rax+28h]
0x18001c1ad  mov     rax, [rbx]
0x18001c1b0  mov     r8d, 21h ; '!'
0x18001c1b6  lea     rdx, aCouldNotDeterm; "Could not determine the user SID."
0x18001c1bd  mov     rcx, rbx
0x18001c1c0  mov     rax, [rax+10h]
0x18001c1c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c1c9  mov     rcx, rbx
0x18001c1cc  call    ??$?6UENDL@cxl@@@TextWriter@cxl@@QEAAAEAV01@AEBUENDL@1@@Z; cxl::TextWriter::operator<<<cxl::ENDL>(cxl::ENDL const &)
0x18001c1d1  nop
0x18001c1d2  jmp     short $+2
0x18001c1d4  xor     al, al
0x18001c1d6  mov     rcx, [rsp+0D8h+var_28]
0x18001c1de  xor     rcx, rsp; StackCookie
0x18001c1e1  call    __security_check_cookie
0x18001c1e6  mov     rbx, [rsp+0D8h+arg_0]
0x18001c1ee  add     rsp, 0C0h
0x18001c1f5  pop     r14
0x18001c1f7  pop     rdi
0x18001c1f8  pop     rsi
0x18001c1f9  retn
```
