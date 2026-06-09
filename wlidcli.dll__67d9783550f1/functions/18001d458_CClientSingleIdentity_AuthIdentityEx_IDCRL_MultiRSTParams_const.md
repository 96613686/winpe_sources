# CClientSingleIdentity::AuthIdentityEx(IDCRL::_MultiRSTParams * const)

- ea: `0x18001d458`
- end: `0x18001d5e2`
- name: `?AuthIdentityEx@CClientSingleIdentity@@QEAAJQEAU_MultiRSTParams@IDCRL@@@Z`
- size: `394`
- prototype: `__int64 __fastcall(CClientSingleIdentity *__hidden this, struct IDCRL::_MultiRSTParams *const)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18002706c`
- `0x180031c30`

## callees

- `0x18000cc9c`
- `0x18000e870`
- `0x18001ca08`
- `0x18001d458`
- `0x18001d904`
- `0x18001d930`
- `0x18001e36c`
- `0x18001e630`
- `0x18001f920`
- `0x1800530e4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001d4e5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001d4e5`

## string_xrefs

- `0x18001d4f9`: `ERROR: Cannot make network requests on this thread,  this is a wininet callback thread. 0x%x`
- `0x18001d535`: `ERROR: GetAcquireTokenParam failed (0x%x).`
- `0x18001d59e`: `ERROR: AcquireTokenFromSvc failed (0x%x).`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CClientSingleIdentity::AuthIdentityEx(
        CClientSingleIdentity *this,
        struct IDCRL::_MultiRSTParams *const a2)
{
  int AcquireTokenParam; // eax
  const unsigned __int16 *v5; // r9
  unsigned int v6; // r8d
  int v7; // r8d
  int v8; // r9d
  unsigned __int8 v9; // cl
  CClientSingleIdentity *v10; // rcx
  void *v11; // r8
  CClientPassportClientLibrary *v12; // rcx
  unsigned int v13; // ebx
  const unsigned __int16 *v15; // [rsp+20h] [rbp-30h]
  const unsigned __int16 *v16; // [rsp+20h] [rbp-30h]
  _QWORD v17[4]; // [rsp+30h] [rbp-20h] BYREF
  int v18; // [rsp+78h] [rbp+28h] BYREF
  void *v19; // [rsp+80h] [rbp+30h] BYREF

  v18 = 0;
  v17[0] = "CClientSingleIdentity::AuthIdentityEx";
  v17[1] = &v18;
  v17[2] = 0;
  v17[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"clientcore\\ds\\ext\\live\\identity\\api\\classic\\idcrlidentity.cpp",
    "CClientSingleIdentity::AuthIdentityEx",
    (const char *)0x253,
    0,
    v15);
  v19 = 0;
  if ( !a2 )
  {
    AcquireTokenParam = -2147188712;
    v18 = -2147188712;
    v5 = L"ERROR: pcMultiRSTParams is NULL (0x%x).";
    v6 = 602;
LABEL_13:
    v9 = 2;
    goto LABEL_14;
  }
  if ( TlsGetValue(*((_DWORD *)g_pPPCRL + 228)) == (LPVOID)1 )
  {
    AcquireTokenParam = -2147188679;
    v18 = -2147188679;
    v5 = L"ERROR: Cannot make network requests on this thread,  this is a wininet callback thread. 0x%x";
    v6 = 612;
    v9 = 3;
LABEL_14:
    LODWORD(v16) = AcquireTokenParam;
    TracePrintW(v9, "clientcore\\ds\\ext\\live\\identity\\api\\classic\\idcrlidentity.cpp", v6, v5, v16);
    goto LABEL_15;
  }
  AcquireTokenParam = GetAcquireTokenParam((_DWORD)this, (_DWORD)a2, v7, v8, *((_DWORD *)this + 51), (__int64)&v19);
  v18 = AcquireTokenParam;
  if ( AcquireTokenParam < 0 )
  {
    v5 = L"ERROR: GetAcquireTokenParam failed (0x%x).";
    v6 = 626;
    goto LABEL_13;
  }
  if ( CClientSingleIdentity::IsAsync(this) )
  {
    CClientSingleIdentity::SetRequestStatus(v10, -2147186641);
    v11 = v19;
    v19 = 0;
    v18 = CClientPassportClientLibrary::QueueWorkItem(
            v12,
            (void (*)(void *, unsigned __int8, unsigned __int8))AcquireTokensFromSvcWorker,
            v11);
    if ( v18 >= 0 )
      v18 = 297031;
    else
      CClientSingleIdentity::SetRequestStatus(this, 0);
  }
  else
  {
    AcquireTokenParam = CClientSingleIdentity::AcquireTokenFromSvc(v10, v19);
    v18 = AcquireTokenParam;
    if ( AcquireTokenParam < 0 )
    {
      v5 = L"ERROR: AcquireTokenFromSvc failed (0x%x).";
      v6 = 653;
      goto LABEL_13;
    }
  }
LABEL_15:
  v13 = v18;
  ATL::CAutoPtr<_AcquireTokenParam>::Free(&v19);
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v17);
  return v13;
}

```

## disassembly

```asm
0x18001d458  mov     [rsp-18h+arg_0], rbx
0x18001d45d  push    rbp
0x18001d45e  push    rdi
0x18001d45f  push    r14
0x18001d461  mov     rbp, rsp
0x18001d464  sub     rsp, 50h
0x18001d468  mov     rdi, rdx
0x18001d46b  mov     rbx, rcx
0x18001d46e  mov     [rbp+arg_8], 0
0x18001d475  lea     rdx, aCclientsinglei_6; "CClientSingleIdentity::AuthIdentityEx"
0x18001d47c  mov     [rbp+var_20], rdx
0x18001d480  lea     rax, [rbp+arg_8]
0x18001d484  mov     [rbp+var_18], rax
0x18001d488  mov     [rbp+var_10], 0
0x18001d490  mov     [rbp+var_8], 0
0x18001d498  xor     r9d, r9d; unsigned int
0x18001d49b  mov     r8d, 253h; char *
0x18001d4a1  lea     r14, aClientcoreDsEx_17; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x18001d4a8  mov     rcx, r14; this
0x18001d4ab  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18001d4b0  nop
0x18001d4b1  mov     [rbp+arg_10], 0
0x18001d4b9  test    rdi, rdi
0x18001d4bc  jnz     short loc_18001D4D8
0x18001d4be  mov     eax, 80048018h
0x18001d4c3  mov     [rbp+arg_8], eax
0x18001d4c6  lea     r9, aErrorPcmultirs; "ERROR: pcMultiRSTParams is NULL (0x%x)."
0x18001d4cd  mov     r8d, 25Ah
0x18001d4d3  jmp     loc_18001D5AB
0x18001d4d8  mov     rcx, cs:?g_pPPCRL@@3PEAVCClientPassportClientLibrary@@EA; CClientPassportClientLibrary * g_pPPCRL
0x18001d4df  mov     ecx, [rcx+390h]; dwTlsIndex
0x18001d4e5  call    cs:__imp_TlsGetValue
0x18001d4eb  cmp     rax, 1
0x18001d4ef  jnz     short loc_18001D510
0x18001d4f1  mov     eax, 80048039h
0x18001d4f6  mov     [rbp+arg_8], eax
0x18001d4f9  lea     r9, aErrorCannotMak; "ERROR: Cannot make network requests on "...
0x18001d500  mov     r8d, 264h
0x18001d506  mov     ecx, 3
0x18001d50b  jmp     loc_18001D5B0
0x18001d510  lea     rax, [rbp+arg_10]
0x18001d514  mov     [rsp+50h+var_28], rax
0x18001d519  mov     eax, [rbx+0CCh]
0x18001d51f  mov     dword ptr [rsp+50h+var_30], eax
0x18001d523  mov     rdx, rdi
0x18001d526  mov     rcx, rbx
0x18001d529  call    ?GetAcquireTokenParam@@YAJPEAVCClientSingleIdentity@@QEAU_MultiRSTParams@IDCRL@@W4PPCRLUserType@@HKAEAV?$CAutoPtr@U_AcquireTokenParam@@@ATL@@@Z; GetAcquireTokenParam(CClientSingleIdentity *,IDCRL::_MultiRSTParams * const,PPCRLUserType,int,ulong,ATL::CAutoPtr<_AcquireTokenParam> &)
0x18001d52e  mov     [rbp+arg_8], eax
0x18001d531  test    eax, eax
0x18001d533  jns     short loc_18001D544
0x18001d535  lea     r9, aErrorGetacquir; "ERROR: GetAcquireTokenParam failed (0x%"...
0x18001d53c  mov     r8d, 272h
0x18001d542  jmp     short loc_18001D5AB
0x18001d544  mov     rcx, rbx; this
0x18001d547  call    ?IsAsync@CClientSingleIdentity@@QEAA_NXZ; CClientSingleIdentity::IsAsync(void)
0x18001d54c  test    al, al
0x18001d54e  jz      short loc_18001D58E
0x18001d550  mov     edx, 8004882Fh; int
0x18001d555  call    ?SetRequestStatus@CClientSingleIdentity@@QEAAXJ@Z; CClientSingleIdentity::SetRequestStatus(long)
0x18001d55a  mov     r8, [rbp+arg_10]; void *
0x18001d55e  mov     [rbp+arg_10], 0
0x18001d566  lea     rdx, ?AcquireTokensFromSvcWorker@@YAXPEAXEE@Z; void (*)(void *, unsigned __int8, unsigned __int8)
0x18001d56d  call    ?QueueWorkItem@CClientPassportClientLibrary@@QEAAJP6AXPEAXEE@Z0@Z; CClientPassportClientLibrary::QueueWorkItem(void (*)(void *,uchar,uchar),void *)
0x18001d572  mov     [rbp+arg_8], eax
0x18001d575  test    eax, eax
0x18001d577  jns     short loc_18001D585
0x18001d579  xor     edx, edx; int
0x18001d57b  mov     rcx, rbx; this
0x18001d57e  call    ?SetRequestStatus@CClientSingleIdentity@@QEAAXJ@Z; CClientSingleIdentity::SetRequestStatus(long)
0x18001d583  jmp     short loc_18001D5BC
0x18001d585  mov     [rbp+arg_8], 48847h
0x18001d58c  jmp     short loc_18001D5BC
0x18001d58e  mov     rdx, [rbp+arg_10]; void *
0x18001d592  call    ?AcquireTokenFromSvc@CClientSingleIdentity@@QEAAJPEAX@Z; CClientSingleIdentity::AcquireTokenFromSvc(void *)
0x18001d597  mov     [rbp+arg_8], eax
0x18001d59a  test    eax, eax
0x18001d59c  jns     short loc_18001D5BC
0x18001d59e  lea     r9, aErrorAcquireto; "ERROR: AcquireTokenFromSvc failed (0x%x"...
0x18001d5a5  mov     r8d, 28Dh; unsigned int
0x18001d5ab  mov     ecx, 2; unsigned __int8
0x18001d5b0  mov     dword ptr [rsp+50h+var_30], eax
0x18001d5b4  mov     rdx, r14; char *
0x18001d5b7  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001d5bc  mov     ebx, [rbp+arg_8]
0x18001d5bf  lea     rcx, [rbp+arg_10]
0x18001d5c3  call    ?Free@?$CAutoPtr@U_AcquireTokenParam@@@ATL@@QEAAXXZ; ATL::CAutoPtr<_AcquireTokenParam>::Free(void)
0x18001d5c8  nop
0x18001d5c9  lea     rcx, [rbp+var_20]
0x18001d5cd  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18001d5d2  mov     eax, ebx
0x18001d5d4  mov     rbx, [rsp+50h+arg_0]
0x18001d5d9  add     rsp, 50h
0x18001d5dd  pop     r14
0x18001d5df  pop     rdi
0x18001d5e0  pop     rbp
0x18001d5e1  retn
```
