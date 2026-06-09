# CTpLogger::StartSession(wchar_t const *)

- ea: `0x18004485c`
- end: `0x180044b0e`
- name: `?StartSession@CTpLogger@@QEAAJPEB_W@Z`
- size: `690`
- prototype: `__int64 __fastcall(CTpLogger *__hidden this, const wchar_t *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180024998`
- `0x18008278c`

## callees

- `0x180015520`
- `0x1800372d8`
- `0x180039950`
- `0x18004485c`
- `0x180050db0`
- `0x180051380`
- `0x1800a0468`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wfopen` at `0x1800449dc`
- `api-ms-win-crt-private-l1-1-0!_o__wfopen` at `0x180044a34`
- `api-ms-win-crt-private-l1-1-0!_o__wfopen` at `0x180044aa7`
- `api-ms-win-crt-private-l1-1-0!_o__wfopen` at `0x180044ad1`
- `api-ms-win-crt-private-l1-1-0!_o__wfopen` at `0x1800449dc`
- `api-ms-win-crt-private-l1-1-0!_o__wfopen` at `0x180044a34`
- `api-ms-win-crt-private-l1-1-0!_o__wfopen` at `0x180044aa7`
- `api-ms-win-crt-private-l1-1-0!_o__wfopen` at `0x180044ad1`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x1800448cb`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x1800448de`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x1800448f1`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x1800449ef`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x180044a47`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x180044aba`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x180044ae4`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x1800448cb`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x1800448de`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x1800448f1`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x1800449ef`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x180044a47`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x180044aba`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x180044ae4`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180044997`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800449c7`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180044a1b`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180044a8e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180044997`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800449c7`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180044a1b`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180044a8e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800448a8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800448a8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CTpLogger::StartSession(CTpLogger *this, const wchar_t *a2)
{
  unsigned int v5; // r8d
  int LoggingDirectory; // ebx
  FILE *v7; // rcx
  FILE *v8; // rcx
  FILE *v9; // rcx
  __int64 v10; // r14
  __int64 v11; // rsi
  __int64 v12; // rdx
  __int64 v13; // rbx
  unsigned __int64 v14; // rcx
  FILE *v15; // rax
  FILE *v16; // rcx
  FILE *v17; // rax
  FILE *v18; // rcx
  __int64 v19; // rdx
  FILE *v20; // rax
  FILE *v21; // rcx
  FILE *v22; // rax
  FILE *v23; // rcx
  char *v24; // [rsp+20h] [rbp-E0h] BYREF
  char v25; // [rsp+28h] [rbp-D8h]
  wchar_t v26[40]; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t FileName[264]; // [rsp+80h] [rbp-80h] BYREF

  if ( !*((_DWORD *)this + 31) )
    return 1;
  v24 = (char *)this + 8;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v25 = 1;
  if ( *((_QWORD *)this + 12) )
  {
    LoggingDirectory = -2147023649;
LABEL_5:
    v7 = (FILE *)*((_QWORD *)this + 11);
    *((_QWORD *)this + 11) = 0;
    if ( v7 )
      fclose(v7);
    v8 = (FILE *)*((_QWORD *)this + 13);
    *((_QWORD *)this + 13) = 0;
    if ( v8 )
      fclose(v8);
    v9 = (FILE *)*((_QWORD *)this + 12);
    *((_QWORD *)this + 12) = 0;
    if ( v9 )
      fclose(v9);
    goto LABEL_11;
  }
  LoggingDirectory = CTpLogger::CreateLoggingDirectory(this, FileName, v5);
  if ( LoggingDirectory < 0 )
    goto LABEL_5;
  v10 = -1;
  v11 = -1;
  do
    ++v11;
  while ( FileName[v11] );
  if ( *((_DWORD *)this + 30) )
  {
    LoggingDirectory = UtilUuidCreateAsString(v26);
    if ( LoggingDirectory < 0 )
      goto LABEL_5;
    v13 = (unsigned int)v11;
    v14 = 2LL * (unsigned int)v11;
    if ( v14 >= 0x208 )
      goto LABEL_31;
    FileName[(unsigned int)v11] = 0;
    if ( (unsigned int)_o_wcscat_s(FileName, 260, v26) )
      goto LABEL_19;
    do
      ++v10;
    while ( FileName[v10] );
    if ( (unsigned int)_o_wcscat_s(FileName, 260, L".log") )
      goto LABEL_19;
    v15 = _wfopen(FileName, L"wt, ccs=UTF-8");
    v16 = (FILE *)*((_QWORD *)this + 12);
    *((_QWORD *)this + 12) = v15;
    if ( v16 )
      fclose(v16);
    if ( !*((_QWORD *)this + 12) )
      goto LABEL_19;
    v14 = 2LL * (unsigned int)v10;
    if ( v14 >= 0x208 )
LABEL_31:
      _report_rangecheckfailure(v14, v12);
    FileName[(unsigned int)v10] = 0;
    if ( (unsigned int)_o_wcscat_s(FileName, 260, L".raw") )
      goto LABEL_19;
    v17 = _wfopen(FileName, L"wb");
    v18 = (FILE *)*((_QWORD *)this + 13);
    *((_QWORD *)this + 13) = v17;
    if ( v18 )
      fclose(v18);
    if ( !*((_QWORD *)this + 13) )
    {
LABEL_19:
      LoggingDirectory = -2147467259;
      goto LABEL_5;
    }
  }
  else
  {
    v13 = (unsigned int)v11;
  }
  CTpLogger::RotateLogs(this);
  if ( (unsigned __int64)(2 * v13) >= 0x208 )
    _report_rangecheckfailure(2 * v13, v19);
  FileName[v13] = 0;
  if ( (unsigned int)_o_wcscat_s(FileName, 260, L"tpclient.al3") )
    goto LABEL_19;
  v20 = _wfopen(FileName, L"r+b");
  v21 = (FILE *)*((_QWORD *)this + 11);
  *((_QWORD *)this + 11) = v20;
  if ( v21 )
    fclose(v21);
  if ( !*((_QWORD *)this + 11) )
  {
    v22 = _wfopen(FileName, L"w+b");
    v23 = (FILE *)*((_QWORD *)this + 11);
    *((_QWORD *)this + 11) = v22;
    if ( v23 )
      fclose(v23);
    if ( !*((_QWORD *)this + 11) )
      goto LABEL_19;
  }
  *((_QWORD *)this + 10) = a2;
  *((_QWORD *)this + 14) = 1;
  LoggingDirectory = 0;
LABEL_11:
  utl::unique_lock<utl::recursive_mutex>::~unique_lock<utl::recursive_mutex>((__int64)&v24);
  return (unsigned int)LoggingDirectory;
}

```

## disassembly

```asm
0x18004485c  push    rbp
0x18004485e  push    rbx
0x18004485f  push    rsi
0x180044860  push    rdi
0x180044861  push    r12
0x180044863  push    r13
0x180044865  push    r14
0x180044867  push    r15
0x180044869  lea     rbp, [rsp-1A8h]
0x180044871  sub     rsp, 2A8h
0x180044878  mov     rax, cs:__security_cookie
0x18004487f  xor     rax, rsp
0x180044882  mov     [rbp+1E0h+var_50], rax
0x180044889  mov     r15, rdx
0x18004488c  mov     rdi, rcx
0x18004488f  xor     r12d, r12d
0x180044892  cmp     [rcx+7Ch], r12d
0x180044896  jnz     short loc_18004489F
0x180044898  lea     eax, [r12+1]
0x18004489d  jmp     short loc_180044904
0x18004489f  add     rcx, 8; lpCriticalSection
0x1800448a3  mov     [rsp+2E0h+var_2C0], rcx
0x1800448a8  call    cs:__imp_EnterCriticalSection
0x1800448ae  mov     [rsp+2E0h+var_2B8], 1
0x1800448b3  cmp     [rdi+60h], r12
0x1800448b7  jz      short loc_180044927
0x1800448b9  mov     ebx, 800704DFh
0x1800448be  mov     rcx, [rdi+58h]; Stream
0x1800448c2  mov     [rdi+58h], r12
0x1800448c6  test    rcx, rcx
0x1800448c9  jz      short loc_1800448D1
0x1800448cb  call    cs:__imp_fclose
0x1800448d1  mov     rcx, [rdi+68h]; Stream
0x1800448d5  mov     [rdi+68h], r12
0x1800448d9  test    rcx, rcx
0x1800448dc  jz      short loc_1800448E4
0x1800448de  call    cs:__imp_fclose
0x1800448e4  mov     rcx, [rdi+60h]; Stream
0x1800448e8  mov     [rdi+60h], r12
0x1800448ec  test    rcx, rcx
0x1800448ef  jz      short loc_1800448F8
0x1800448f1  call    cs:__imp_fclose
0x1800448f7  nop
0x1800448f8  lea     rcx, [rsp+2E0h+var_2C0]
0x1800448fd  call    ??1?$unique_lock@Vrecursive_mutex@utl@@@utl@@QEAA@XZ; utl::unique_lock<utl::recursive_mutex>::~unique_lock<utl::recursive_mutex>(void)
0x180044902  mov     eax, ebx
0x180044904  mov     rcx, [rbp+1E0h+var_50]
0x18004490b  xor     rcx, rsp; StackCookie
0x18004490e  call    __security_check_cookie
0x180044913  add     rsp, 2A8h
0x18004491a  pop     r15
0x18004491c  pop     r14
0x18004491e  pop     r13
0x180044920  pop     r12
0x180044922  pop     rdi
0x180044923  pop     rsi
0x180044924  pop     rbx
0x180044925  pop     rbp
0x180044926  retn
0x180044927  lea     rdx, [rbp+1E0h+FileName]; wchar_t *
0x18004492b  mov     rcx, rdi; this
0x18004492e  call    ?CreateLoggingDirectory@CTpLogger@@AEAAJPEA_WK@Z; CTpLogger::CreateLoggingDirectory(wchar_t *,ulong)
0x180044933  mov     ebx, eax
0x180044935  test    eax, eax
0x180044937  js      short loc_1800448BE
0x180044939  lea     rax, [rbp+1E0h+FileName]
0x18004493d  or      r14, 0FFFFFFFFFFFFFFFFh
0x180044941  mov     rsi, r14
0x180044944  inc     rsi
0x180044947  cmp     [rax+rsi*2], r12w
0x18004494c  jnz     short loc_180044944
0x18004494e  mov     r13d, 208h
0x180044954  cmp     [rdi+78h], r12d
0x180044958  jbe     loc_180044A5E
0x18004495e  lea     rcx, [rsp+2E0h+var_2B0]; wchar_t *
0x180044963  call    ?UtilUuidCreateAsString@@YAJPEA_W@Z; UtilUuidCreateAsString(wchar_t *)
0x180044968  mov     ebx, eax
0x18004496a  test    eax, eax
0x18004496c  js      loc_1800448BE
0x180044972  mov     ebx, esi
0x180044974  lea     rcx, [rbx+rbx]
0x180044978  cmp     rcx, r13
0x18004497b  jnb     loc_180044A58
0x180044981  mov     [rbp+rcx+1E0h+FileName], r12w
0x180044987  lea     r8, [rsp+2E0h+var_2B0]
0x18004498c  mov     esi, 104h
0x180044991  mov     edx, esi
0x180044993  lea     rcx, [rbp+1E0h+FileName]
0x180044997  call    cs:__imp__o_wcscat_s
0x18004499d  test    eax, eax
0x18004499f  jz      short loc_1800449AB
0x1800449a1  mov     ebx, 80004005h
0x1800449a6  jmp     loc_1800448BE
0x1800449ab  lea     rax, [rbp+1E0h+FileName]
0x1800449af  inc     r14
0x1800449b2  cmp     [rax+r14*2], r12w
0x1800449b7  jnz     short loc_1800449AF
0x1800449b9  lea     r8, aLog; ".log"
0x1800449c0  mov     rdx, rsi
0x1800449c3  lea     rcx, [rbp+1E0h+FileName]
0x1800449c7  call    cs:__imp__o_wcscat_s
0x1800449cd  test    eax, eax
0x1800449cf  jnz     short loc_1800449A1
0x1800449d1  lea     rdx, aWtCcsUtf8; "wt, ccs=UTF-8"
0x1800449d8  lea     rcx, [rbp+1E0h+FileName]; FileName
0x1800449dc  call    cs:__imp__wfopen
0x1800449e2  mov     rcx, [rdi+60h]; Stream
0x1800449e6  mov     [rdi+60h], rax
0x1800449ea  test    rcx, rcx
0x1800449ed  jz      short loc_1800449F5
0x1800449ef  call    cs:__imp_fclose
0x1800449f5  cmp     [rdi+60h], r12
0x1800449f9  jz      short loc_1800449A1
0x1800449fb  mov     eax, r14d
0x1800449fe  lea     rcx, [rax+rax]
0x180044a02  cmp     rcx, r13
0x180044a05  jnb     short loc_180044A58
0x180044a07  mov     [rbp+rcx+1E0h+FileName], r12w
0x180044a0d  lea     r8, aRaw_0; ".raw"
0x180044a14  mov     rdx, rsi
0x180044a17  lea     rcx, [rbp+1E0h+FileName]
0x180044a1b  call    cs:__imp__o_wcscat_s
0x180044a21  test    eax, eax
0x180044a23  jnz     loc_1800449A1
0x180044a29  lea     rdx, aWb; "wb"
0x180044a30  lea     rcx, [rbp+1E0h+FileName]; FileName
0x180044a34  call    cs:__imp__wfopen
0x180044a3a  mov     rcx, [rdi+68h]; Stream
0x180044a3e  mov     [rdi+68h], rax
0x180044a42  test    rcx, rcx
0x180044a45  jz      short loc_180044A4D
0x180044a47  call    cs:__imp_fclose
0x180044a4d  cmp     [rdi+68h], r12
0x180044a51  jnz     short loc_180044A65
0x180044a53  jmp     loc_1800449A1
0x180044a58  call    __report_rangecheckfailure
0x180044a5e  mov     ebx, esi
0x180044a60  mov     esi, 104h
0x180044a65  mov     rcx, rdi; this
0x180044a68  call    ?RotateLogs@CTpLogger@@AEAAJXZ; CTpLogger::RotateLogs(void)
0x180044a6d  lea     rcx, [rbx+rbx]
0x180044a71  cmp     rcx, r13
0x180044a74  jnb     loc_180044B08
0x180044a7a  mov     [rbp+rcx+1E0h+FileName], r12w
0x180044a80  lea     r8, aTpclientAl3; "tpclient.al3"
0x180044a87  mov     rdx, rsi
0x180044a8a  lea     rcx, [rbp+1E0h+FileName]
0x180044a8e  call    cs:__imp__o_wcscat_s
0x180044a94  test    eax, eax
0x180044a96  jnz     loc_1800449A1
0x180044a9c  lea     rdx, aRB; "r+b"
0x180044aa3  lea     rcx, [rbp+1E0h+FileName]; FileName
0x180044aa7  call    cs:__imp__wfopen
0x180044aad  mov     rcx, [rdi+58h]; Stream
0x180044ab1  mov     [rdi+58h], rax
0x180044ab5  test    rcx, rcx
0x180044ab8  jz      short loc_180044AC0
0x180044aba  call    cs:__imp_fclose
0x180044ac0  cmp     [rdi+58h], r12
0x180044ac4  jnz     short loc_180044AF4
0x180044ac6  lea     rdx, aWB; "w+b"
0x180044acd  lea     rcx, [rbp+1E0h+FileName]; FileName
0x180044ad1  call    cs:__imp__wfopen
0x180044ad7  mov     rcx, [rdi+58h]; Stream
0x180044adb  mov     [rdi+58h], rax
0x180044adf  test    rcx, rcx
0x180044ae2  jz      short loc_180044AEA
0x180044ae4  call    cs:__imp_fclose
0x180044aea  cmp     [rdi+58h], r12
0x180044aee  jz      loc_1800449A1
0x180044af4  mov     [rdi+50h], r15
0x180044af8  mov     qword ptr [rdi+70h], 1
0x180044b00  mov     ebx, r12d
0x180044b03  jmp     loc_1800448F8
0x180044b08  call    __report_rangecheckfailure
```
