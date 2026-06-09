# ClusWmi::DataStore::GetCurrentTokenModifiedIDAndSid(cxl::Token &,_LUID *,cxl::Sid *)

- ea: `0x18001cabc`
- end: `0x18001ccd3`
- name: `?GetCurrentTokenModifiedIDAndSid@DataStore@ClusWmi@@AEAA_NAEAVToken@cxl@@PEAU_LUID@@PEAVSid@4@@Z`
- size: `535`
- prototype: `bool(ClusWmi::DataStore *__hidden this, struct cxl::Token *, struct _LUID *, struct cxl::Sid *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001c3a0`

## callees

- `0x180002ad0`
- `0x18000cd24`
- `0x18000eb18`
- `0x180015be4`
- `0x1800160a8`
- `0x180016300`
- `0x18001a5f0`
- `0x18001cabc`
- `0x18001ce34`
- `0x180073058`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cb7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cb7a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001cb31`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001cb31`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001caf3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001caf3`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18001cb6a`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18001cb6a`

## string_xrefs

- `0x18001cba1`: `Could not duplicate process token, error = %d`
- `0x18001cbe2`: `The thread token could not be opened due to the impersonation level.  This is likely from an impersonation level less than RPC_C_IMP_LEVEL_IMPERSONATE.`
- `0x18001cc8e`: `Could not determine the user SID.`

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
0x18001cabc  mov     [rsp+arg_0], rbx
0x18001cac1  push    rsi
0x18001cac2  push    rdi
0x18001cac3  push    r14
0x18001cac5  sub     rsp, 0C0h
0x18001cacc  mov     rax, cs:__security_cookie
0x18001cad3  xor     rax, rsp
0x18001cad6  mov     [rsp+0D8h+var_28], rax
0x18001cade  mov     rsi, r9
0x18001cae1  mov     rdi, rdx
0x18001cae4  mov     qword ptr [rsp+0D8h+var_A0], rdx
0x18001cae9  mov     [rsp+0D8h+var_98], r8
0x18001caee  mov     [rsp+0D8h+var_90], r9
0x18001caf3  call    cs:__imp_GetCurrentThread
0x18001cafa  nop     dword ptr [rax+rax+00h]
0x18001caff  mov     r9, rax; void *
0x18001cb02  xor     r8d, r8d; int
0x18001cb05  lea     edx, [r8+8]; unsigned int
0x18001cb09  mov     rcx, rdi; this
0x18001cb0c  call    ?TryOpenThreadToken@Token@cxl@@QEAAKKHPEAX@Z; cxl::Token::TryOpenThreadToken(ulong,int,void *)
0x18001cb11  mov     [rsp+0D8h+var_A8], eax
0x18001cb15  cmp     eax, 3F0h
0x18001cb1a  jnz     loc_18001CBC9
0x18001cb20  mov     [rsp+0D8h+var_A8], 0
0x18001cb28  mov     [rsp+0D8h+ExistingTokenHandle], 0
0x18001cb31  call    cs:__imp_GetCurrentProcess
0x18001cb38  nop     dword ptr [rax+rax+00h]
0x18001cb3d  mov     r8, rax; void *
0x18001cb40  mov     edx, 2000Ah; unsigned int
0x18001cb45  lea     rcx, [rsp+0D8h+var_88]; this
0x18001cb4a  call    ?OpenProcessToken@Token@cxl@@QEAAXKPEAX@Z; cxl::Token::OpenProcessToken(ulong,void *)
0x18001cb4f  mov     rbx, [rsp+0D8h+ExistingTokenHandle]
0x18001cb54  xor     r14d, r14d
0x18001cb57  mov     rcx, rdi; this
0x18001cb5a  call    ?Clear@Token@cxl@@QEAAXXZ; cxl::Token::Clear(void)
0x18001cb5f  lea     r8, [rdi+8]; DuplicateTokenHandle
0x18001cb63  lea     edx, [r14+2]; ImpersonationLevel
0x18001cb67  mov     rcx, rbx; ExistingTokenHandle
0x18001cb6a  call    cs:__imp_DuplicateToken
0x18001cb71  nop     dword ptr [rax+rax+00h]
0x18001cb76  test    eax, eax
0x18001cb78  jnz     short loc_18001CB89
0x18001cb7a  call    cs:__imp_GetLastError
0x18001cb81  nop     dword ptr [rax+rax+00h]
0x18001cb86  mov     r14d, eax
0x18001cb89  mov     [rsp+0D8h+var_A8], r14d
0x18001cb8e  test    r14d, r14d
0x18001cb91  jz      short loc_18001CBAE
0x18001cb93  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18001cb98  lea     rcx, [rax+50h]; struct cxl::TextWriter *
0x18001cb9c  lea     r8, [rsp+0D8h+var_A8]
0x18001cba1  lea     rdx, aCouldNotDuplic; "Could not duplicate process token, erro"...
0x18001cba8  call    ??$WriteLine@DK$$V@TextWriter@cxl@@QEAAXPEBDAEBK@Z; cxl::TextWriter::WriteLine<char,ulong,>(char const *,ulong const &)
0x18001cbad  nop
0x18001cbae  lea     rcx, [rsp+0D8h+var_88]; this
0x18001cbb3  call    ?Clear@Token@cxl@@QEAAXXZ; cxl::Token::Clear(void)
0x18001cbb8  nop
0x18001cbb9  jmp     short loc_18001CBFD
0x18001cbbb  jmp     short $+2
0x18001cbbd  mov     rdi, qword ptr [rsp+0D8h+var_A0]
0x18001cbc2  mov     rsi, [rsp+0D8h+var_90]
0x18001cbc7  jmp     short loc_18001CBFD
0x18001cbc9  cmp     eax, 542h
0x18001cbce  jnz     short loc_18001CBFD
0x18001cbd0  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18001cbd5  lea     rbx, [rax+50h]
0x18001cbd9  mov     rax, [rbx]
0x18001cbdc  mov     r8d, 97h
0x18001cbe2  lea     rdx, aTheThreadToken; "The thread token could not be opened du"...
0x18001cbe9  mov     rcx, rbx
0x18001cbec  mov     rax, [rax+10h]
0x18001cbf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cbf5  mov     rcx, rbx
0x18001cbf8  call    ??$?6UENDL@cxl@@@TextWriter@cxl@@QEAAAEAV01@AEBUENDL@1@@Z; cxl::TextWriter::operator<<<cxl::ENDL>(cxl::ENDL const &)
0x18001cbfd  cmp     [rsp+0D8h+var_A8], 0
0x18001cc02  jnz     loc_18001CCAC
0x18001cc08  xorps   xmm0, xmm0
0x18001cc0b  xor     eax, eax
0x18001cc0d  movups  [rsp+0D8h+var_60], xmm0
0x18001cc12  movups  [rsp+0D8h+var_50], xmm0
0x18001cc1a  movups  [rsp+0D8h+var_40], xmm0
0x18001cc22  mov     [rsp+0D8h+var_30], rax
0x18001cc2a  mov     [rsp+0D8h+var_A0], eax
0x18001cc2e  lea     rax, [rsp+0D8h+var_A0]
0x18001cc33  mov     [rsp+0D8h+var_B8], rax; PDWORD
0x18001cc38  mov     r9d, 38h ; '8'; unsigned int
0x18001cc3e  lea     r8, [rsp+0D8h+var_60]; void *
0x18001cc43  lea     edx, [r9-2Eh]; enum _TOKEN_INFORMATION_CLASS
0x18001cc47  mov     rcx, rdi; this
0x18001cc4a  call    ?GetInformation@Token@cxl@@QEAA_NW4_TOKEN_INFORMATION_CLASS@@PEAXKPEAK@Z; cxl::Token::GetInformation(_TOKEN_INFORMATION_CLASS,void *,ulong,ulong *)
0x18001cc4f  test    al, al
0x18001cc51  jz      short loc_18001CCAA
0x18001cc53  mov     rdx, [rsp+0D8h+var_98]
0x18001cc58  mov     rax, [rsp+0D8h+var_30]
0x18001cc60  mov     [rdx], rax
0x18001cc63  mov     rdx, rsi; struct cxl::Sid *
0x18001cc66  mov     rcx, rdi; this
0x18001cc69  call    ?GetUserSid@Token@cxl@@QEAA_NPEAVSid@2@@Z; cxl::Token::GetUserSid(cxl::Sid *)
0x18001cc6e  test    al, al
0x18001cc70  jz      short loc_18001CC7C
0x18001cc72  cmp     qword ptr [rsi+10h], 0
0x18001cc77  setnz   al
0x18001cc7a  jmp     short loc_18001CCAE
0x18001cc7c  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18001cc81  lea     rbx, [rax+28h]
0x18001cc85  mov     rax, [rbx]
0x18001cc88  mov     r8d, 21h ; '!'
0x18001cc8e  lea     rdx, aCouldNotDeterm; "Could not determine the user SID."
0x18001cc95  mov     rcx, rbx
0x18001cc98  mov     rax, [rax+10h]
0x18001cc9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cca1  mov     rcx, rbx
0x18001cca4  call    ??$?6UENDL@cxl@@@TextWriter@cxl@@QEAAAEAV01@AEBUENDL@1@@Z; cxl::TextWriter::operator<<<cxl::ENDL>(cxl::ENDL const &)
0x18001cca9  nop
0x18001ccaa  jmp     short $+2
0x18001ccac  xor     al, al
0x18001ccae  mov     rcx, [rsp+0D8h+var_28]
0x18001ccb6  xor     rcx, rsp; StackCookie
0x18001ccb9  call    __security_check_cookie
0x18001ccbe  mov     rbx, [rsp+0D8h+arg_0]
0x18001ccc6  add     rsp, 0C0h
0x18001cccd  pop     r14
0x18001cccf  pop     rdi
0x18001ccd0  pop     rsi
0x18001ccd1  retn
```
