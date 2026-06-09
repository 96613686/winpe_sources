# CImpITransactionJoin::JoinTransaction(IUnknown *,long,ulong,ITransactionOptions *)

- ea: `0x383a50b80`
- end: `0x383a51173`
- name: `?JoinTransaction@CImpITransactionJoin@@UEAAJPEAUIUnknown@@JKPEAUITransactionOptions@@@Z`
- size: `1523`
- prototype: `int(CImpITransactionJoin *__hidden this, struct IUnknown *, int, unsigned int, struct ITransactionOptions *)`
- caller_count: `0`
- callee_count: `13`
- tags: ``

## callees

- `0x3838427d0`
- `0x3838434c0`
- `0x3838435e0`
- `0x38391ac40`
- `0x38391aed0`
- `0x38391af80`
- `0x38391afe0`
- `0x3839bd220`
- `0x3839bd770`
- `0x3839bd830`
- `0x3839d3de0`
- `0x3839f2650`
- `0x383a50b80`

## import_xrefs

- `OLEAUT32!__imp_SetErrorInfo` at `0x383a50c8b`
- `OLEAUT32!__imp_SetErrorInfo` at `0x383a50c8b`
- `RPCRT4!UuidCreate` at `0x383a50f49`
- `RPCRT4!UuidCreate` at `0x383a50f49`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CImpITransactionJoin::JoinTransaction(
        CImpITransactionJoin *this,
        struct IUnknown *a2,
        int a3,
        int a4,
        struct ITransactionOptions *a5)
{
  __int64 v9; // rbx
  __int64 v10; // rsi
  const struct _GUID *v11; // r8
  unsigned int v12; // r9d
  unsigned int v13; // ebx
  unsigned int v14; // eax
  __int64 v15; // rax
  unsigned int v16; // eax
  unsigned int v17; // eax
  int v18; // eax
  const struct _GUID *v19; // r8
  RPC_STATUS v20; // eax
  const struct _GUID *v21; // r8
  int v22; // eax
  struct CErrorData *v23; // r9
  const struct _GUID *v24; // r8
  unsigned int v25; // eax
  void *v26; // rcx
  int v27; // eax
  struct CErrorData *v28; // r9
  __int64 v29; // rcx
  struct tagDISPPARAMS *v31; // [rsp+20h] [rbp-C8h]
  char v32; // [rsp+40h] [rbp-A8h]
  int v33; // [rsp+44h] [rbp-A4h] BYREF
  __int64 v34; // [rsp+48h] [rbp-A0h] BYREF
  __int64 v35; // [rsp+50h] [rbp-98h]
  __int64 v36; // [rsp+58h] [rbp-90h]
  __int64 v37; // [rsp+60h] [rbp-88h]
  UUID Uuid; // [rsp+68h] [rbp-80h] BYREF
  _DWORD Src[12]; // [rsp+78h] [rbp-70h] BYREF

  v37 = -2;
  v34 = -1;
  if ( (bidGblFlags & 4) != 0 && off_383B4ABD0[0] )
  {
    LODWORD(v31) = a3;
    bidScopeEnterW(&v34, off_383B4ABD0[0], *(unsigned int *)(*((_QWORD *)this + 1) + 52LL), a2);
  }
  v9 = *((_QWORD *)this + 1);
  v10 = *(_QWORD *)(v9 + 840);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(v9 + 24) + 32LL) + 8LL))(*(_QWORD *)(v9 + 24) + 32LL);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(v10 + 88) + 32LL) + 8LL))(*(_QWORD *)(v10 + 88) + 32LL);
  v35 = *(_QWORD *)(v9 + 24);
  v36 = *(_QWORD *)(v10 + 88);
  v32 = 0;
  if ( !g_AllocatorInUse )
  {
    v33 = 0;
    (*(void (__fastcall **)(struct ISOSHost *, int *))(*(_QWORD *)g_pISOSHost + 24LL))(g_pISOSHost, &v33);
    if ( !v33 )
    {
      (*(void (__fastcall **)(struct ISOSHost *))(*(_QWORD *)g_pISOSHost + 200LL))(g_pISOSHost);
      v32 = 1;
    }
  }
  SetErrorInfo(0, 0);
  if ( !a2 )
  {
    if ( (*(_BYTE *)(*((_QWORD *)this + 1) + 848LL) & 8) != 0 )
    {
      v27 = CDBConnection::EnlistTransaction((CDBConnection *)v10, 0, v11);
      v13 = v27;
      if ( v27 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
          v27 = bidTraceHR(off_383B433F0[0], 350217, (unsigned int)v27);
        CError::PostSqlErrors(
          (CError *)(unsigned int)v27,
          (int)&IID_ITransactionJoin,
          (const struct _GUID *)(v10 + 136),
          v28);
        goto LABEL_68;
      }
      *(_DWORD *)(*((_QWORD *)this + 1) + 848LL) &= ~8u;
    }
    goto LABEL_67;
  }
  if ( a4 )
  {
    if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
      bidTraceW(off_383B433F0[0], 219177, off_383B49128[0], 2147799051LL);
    v13 = CError::PostHResult((CError *)0x8004D00BLL, (int)&IID_ITransactionJoin, v11);
    goto LABEL_68;
  }
  if ( a3 != -1 && !CDBConnection::SetIsoLevelStringId((CDBConnection *)v10, a3) )
  {
    if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
      bidTraceW(off_383B433F0[0], 227369, off_383B49128[0], 2147799048LL);
    v13 = CError::PostHResult((CError *)0x8004D008LL, (int)&IID_ITransactionJoin, v11);
    goto LABEL_68;
  }
  if ( (*(_BYTE *)(*((_QWORD *)this + 1) + 848LL) & 1) != 0 )
  {
    if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
      bidTraceW(off_383B433F0[0], 236585, off_383B49128[0], 2147799059LL);
    v13 = CError::PostHResult((CError *)0x8004D013LL, (int)&IID_ITransactionJoin, v11);
    goto LABEL_68;
  }
  if ( *(_QWORD *)(v10 + 72) )
  {
    v13 = -2147168227;
    if ( (bidGblFlags & 2) != 0 )
      v14 = bidTraceHR(off_383B433F0[0], 245769, 2147799069LL);
    else
      v14 = -2147168227;
    CError::PostError((CError *)v14, (int)&IID_ITransactionJoin, (const struct _GUID *)0x9F03, v12, v31);
LABEL_68:
    if ( (bidGblFlags & 2) != 0 && off_383B49C80[0] )
      bidTraceW(off_383B433F0[0], 362496, off_383B49C80[0], v13);
    goto LABEL_71;
  }
  v15 = *(_QWORD *)(v10 + 1832);
  if ( (*(_BYTE *)(v15 + 400) & 1) == 0 )
    goto LABEL_84;
  if ( *(int *)(v15 + 360) > 0 )
  {
    v16 = -2147467259;
    v13 = -2147467259;
    if ( (bidGblFlags & 2) != 0 )
      v16 = bidTraceHR(off_383B433F0[0], 257033, 2147500037LL);
    CError::PostError((CError *)v16, (int)&IID_ITransactionJoin, (const struct _GUID *)0x9F1D, v12, v31);
    goto LABEL_68;
  }
  if ( (*(_BYTE *)(v15 + 400) & 1) == 0 )
  {
LABEL_84:
    if ( *(_DWORD *)(*(_QWORD *)(v15 + 16) + 824LL) )
    {
      v17 = -2147467259;
      v13 = -2147467259;
      if ( (bidGblFlags & 2) != 0 )
        v17 = bidTraceHR(off_383B433F0[0], 268297, 2147500037LL);
      CError::PostError((CError *)v17, (int)&IID_ITransactionJoin, (const struct _GUID *)0x9F05, v12, v31);
      goto LABEL_68;
    }
  }
  if ( a5 )
  {
    v18 = ((__int64 (__fastcall *)(struct ITransactionOptions *, _DWORD *))a5->lpVtbl->GetOptions)(a5, Src);
    v13 = v18;
    if ( v18 < 0 )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_71;
      bidTraceHR(off_383B433F0[0], 281609, (unsigned int)v18);
      goto LABEL_68;
    }
    if ( Src[0] )
    {
      if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
        bidTraceW(off_383B433F0[0], 289833, off_383B49128[0], 2147799063LL);
      v13 = CError::PostHResult((CError *)0x8004D017LL, (int)&IID_ITransactionJoin, v19);
      goto LABEL_68;
    }
  }
  v20 = UuidCreate(&Uuid);
  if ( v20 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
      v20 = bidTraceHR(off_383B433F0[0], 302089, (unsigned int)v20);
    v13 = CError::PostHResult((CError *)(unsigned int)v20, (int)&IID_ITransactionJoin, v21);
    goto LABEL_68;
  }
  v22 = CDBConnection::EnlistTransaction((CDBConnection *)v10, a2, v21);
  v13 = v22;
  if ( v22 >= 0 )
  {
    *(UUID *)(*((_QWORD *)this + 1) + 856LL) = Uuid;
    v26 = (void *)(*((_QWORD *)this + 1) + 896LL);
    if ( a5 )
      memcpy(v26, Src, 0x2Cu);
    else
      memset(v26, 0, 0x2Cu);
    *(_DWORD *)(*((_QWORD *)this + 1) + 848LL) |= 8u;
LABEL_67:
    v13 = 0;
    goto LABEL_68;
  }
  if ( (bidGblFlags & 2) != 0 )
    v22 = bidTraceHR(off_383B433F0[0], 313353, (unsigned int)v22);
  CError::PostSqlErrors((CError *)(unsigned int)v22, (int)&IID_ITransactionJoin, (const struct _GUID *)(v10 + 136), v23);
  v25 = CDBConnection::EnlistTransaction((CDBConnection *)v10, 0, v24);
  if ( (bidGblFlags & 2) != 0 )
  {
    bidTraceHR(off_383B433F0[0], 320521, v25);
    goto LABEL_68;
  }
LABEL_71:
  if ( v32 )
    (*(void (__fastcall **)(struct ISOSHost *))(*(_QWORD *)g_pISOSHost + 208LL))(g_pISOSHost);
  if ( v36 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(v36 + 32) + 24LL))(v36 + 32);
    v29 = v35;
LABEL_76:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(v29 + 32) + 24LL))(v29 + 32);
    goto LABEL_77;
  }
  v29 = v35;
  if ( v35 )
    goto LABEL_76;
LABEL_77:
  if ( v34 != -1 && (bidGblFlags & 4) != 0 && bidID != -1 )
    off_383B15058();
  return v13;
}

```

## disassembly

```asm
0x383a50b80  push    rbx
0x383a50b82  push    rbp
0x383a50b83  push    rsi
0x383a50b84  push    rdi
0x383a50b85  push    r12
0x383a50b87  push    r14
0x383a50b89  push    r15
0x383a50b8b  sub     rsp, 0B0h
0x383a50b92  mov     [rsp+0E8h+var_88], 0FFFFFFFFFFFFFFFEh
0x383a50b9b  mov     rax, cs:__security_cookie
0x383a50ba2  xor     rax, rsp
0x383a50ba5  mov     [rsp+0E8h+var_40], rax
0x383a50bad  mov     r12d, r9d
0x383a50bb0  mov     ebp, r8d
0x383a50bb3  mov     r15, rdx
0x383a50bb6  mov     rdi, rcx
0x383a50bb9  mov     r14, [rsp+0E8h+arg_20]
0x383a50bc1  mov     [rsp+0E8h+var_A0], 0FFFFFFFFFFFFFFFFh
0x383a50bca  test    byte ptr cs:_bidGblFlags, 4
0x383a50bd1  jz      short loc_383A50C0A
0x383a50bd3  mov     rax, cs:off_383B4ABD0; "<ITransactionJoin::JoinTransaction|OLED"...
0x383a50bda  test    rax, rax
0x383a50bdd  jz      short loc_383A50C0A
0x383a50bdf  mov     rax, [rcx+8]
0x383a50be3  mov     [rsp+0E8h+var_B8], r14
0x383a50be8  mov     [rsp+0E8h+var_C0], r9d
0x383a50bed  mov     dword ptr [rsp+0E8h+var_C8], r8d; struct tagDISPPARAMS *
0x383a50bf2  mov     r9, rdx
0x383a50bf5  mov     r8d, [rax+34h]
0x383a50bf9  mov     rdx, cs:off_383B4ABD0; "<ITransactionJoin::JoinTransaction|OLED"...
0x383a50c00  lea     rcx, [rsp+0E8h+var_A0]
0x383a50c05  call    _bidScopeEnterW
0x383a50c0a  mov     rbx, [rdi+8]
0x383a50c0e  mov     rsi, [rbx+348h]
0x383a50c15  mov     rcx, [rbx+18h]
0x383a50c19  add     rcx, 20h ; ' '
0x383a50c1d  mov     rax, [rcx]
0x383a50c20  call    qword ptr [rax+8]
0x383a50c23  mov     rcx, [rsi+58h]
0x383a50c27  add     rcx, 20h ; ' '
0x383a50c2b  mov     rax, [rcx]
0x383a50c2e  call    qword ptr [rax+8]
0x383a50c31  mov     r11, [rbx+18h]
0x383a50c35  mov     [rsp+0E8h+var_98], r11
0x383a50c3a  mov     rax, [rsi+58h]
0x383a50c3e  mov     [rsp+0E8h+var_90], rax
0x383a50c43  mov     [rsp+0E8h+var_A8], 0
0x383a50c48  cmp     cs:?g_AllocatorInUse@@3W4AllocatorEnum@@A, 0; AllocatorEnum g_AllocatorInUse
0x383a50c4f  jnz     short loc_383A50C87
0x383a50c51  mov     [rsp+0E8h+var_A4], 0
0x383a50c59  mov     rcx, cs:?g_pISOSHost@@3PEAUISOSHost@@EA; ISOSHost * g_pISOSHost
0x383a50c60  mov     rax, [rcx]
0x383a50c63  lea     rdx, [rsp+0E8h+var_A4]
0x383a50c68  call    qword ptr [rax+18h]
0x383a50c6b  cmp     [rsp+0E8h+var_A4], 0
0x383a50c70  jnz     short loc_383A50C87
0x383a50c72  mov     rcx, cs:?g_pISOSHost@@3PEAUISOSHost@@EA; ISOSHost * g_pISOSHost
0x383a50c79  mov     rax, [rcx]
0x383a50c7c  call    qword ptr [rax+0C8h]
0x383a50c82  mov     [rsp+0E8h+var_A8], 1
0x383a50c87  xor     edx, edx; perrinfo
0x383a50c89  xor     ecx, ecx; dwReserved
0x383a50c8b  call    cs:__imp_SetErrorInfo
0x383a50c91  test    r15, r15
0x383a50c94  jz      loc_383A5104A
0x383a50c9a  test    r12d, r12d
0x383a50c9d  jz      short loc_383A50CF2
0x383a50c9f  test    byte ptr cs:_bidGblFlags, 2
0x383a50ca6  jz      short loc_383A50CDA
0x383a50ca8  mov     rcx, cs:off_383B433F0; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383a50caf  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x383a50cb6  test    rax, rax
0x383a50cb9  jz      short loc_383A50CDA
0x383a50cbb  mov     dword ptr [rsp+0E8h+var_C8], 0D6h
0x383a50cc3  mov     r9d, 8004D00Bh
0x383a50cc9  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x383a50cd0  mov     edx, 35829h
0x383a50cd5  call    _bidTraceW
0x383a50cda  lea     rdx, IID_ITransactionJoin; int
0x383a50ce1  mov     ecx, 8004D00Bh; this
0x383a50ce6  call    ?PostHResult@CError@@QEAAJJPEBU_GUID@@@Z; CError::PostHResult(long,_GUID const *)
0x383a50ceb  mov     ebx, eax
0x383a50ced  jmp     loc_383A510A8
0x383a50cf2  cmp     ebp, 0FFFFFFFFh
0x383a50cf5  jz      short loc_383A50D58
0x383a50cf7  mov     edx, ebp; int
0x383a50cf9  mov     rcx, rsi; this
0x383a50cfc  call    ?SetIsoLevelStringId@CDBConnection@@QEAAIJ@Z; CDBConnection::SetIsoLevelStringId(long)
0x383a50d01  test    eax, eax
0x383a50d03  jnz     short loc_383A50D58
0x383a50d05  test    byte ptr cs:_bidGblFlags, 2
0x383a50d0c  jz      short loc_383A50D40
0x383a50d0e  mov     rcx, cs:off_383B433F0; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383a50d15  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x383a50d1c  test    rax, rax
0x383a50d1f  jz      short loc_383A50D40
0x383a50d21  mov     dword ptr [rsp+0E8h+var_C8], 0DEh
0x383a50d29  mov     r9d, 8004D008h
0x383a50d2f  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x383a50d36  mov     edx, 37829h
0x383a50d3b  call    _bidTraceW
0x383a50d40  lea     rdx, IID_ITransactionJoin; int
0x383a50d47  mov     ecx, 8004D008h; this
0x383a50d4c  call    ?PostHResult@CError@@QEAAJJPEBU_GUID@@@Z; CError::PostHResult(long,_GUID const *)
0x383a50d51  mov     ebx, eax
0x383a50d53  jmp     loc_383A510A8
0x383a50d58  mov     rax, [rdi+8]
0x383a50d5c  test    byte ptr [rax+350h], 1
0x383a50d63  jz      short loc_383A50DB8
0x383a50d65  test    byte ptr cs:_bidGblFlags, 2
0x383a50d6c  jz      short loc_383A50DA0
0x383a50d6e  mov     rcx, cs:off_383B433F0; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383a50d75  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x383a50d7c  test    rax, rax
0x383a50d7f  jz      short loc_383A50DA0
0x383a50d81  mov     dword ptr [rsp+0E8h+var_C8], 0E7h
0x383a50d89  mov     r9d, 8004D013h
0x383a50d8f  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x383a50d96  mov     edx, 39C29h
0x383a50d9b  call    _bidTraceW
0x383a50da0  lea     rdx, IID_ITransactionJoin; int
0x383a50da7  mov     ecx, 8004D013h; this
0x383a50dac  call    ?PostHResult@CError@@QEAAJJPEBU_GUID@@@Z; CError::PostHResult(long,_GUID const *)
0x383a50db1  mov     ebx, eax
0x383a50db3  jmp     loc_383A510A8
0x383a50db8  cmp     qword ptr [rsi+48h], 0
0x383a50dbd  jz      short loc_383A50DFE
0x383a50dbf  mov     ebx, 8004D01Dh
0x383a50dc4  test    byte ptr cs:_bidGblFlags, 2
0x383a50dcb  jz      short loc_383A50DE3
0x383a50dcd  mov     r8d, ebx
0x383a50dd0  mov     edx, 3C009h
0x383a50dd5  mov     rcx, cs:off_383B433F0; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383a50ddc  call    _bidTraceHR
0x383a50de1  jmp     short loc_383A50DE5
0x383a50de3  mov     eax, ebx
0x383a50de5  mov     r8d, 9F03h; struct _GUID *
0x383a50deb  lea     rdx, IID_ITransactionJoin; int
0x383a50df2  mov     ecx, eax; this
0x383a50df4  call    ?PostError@CError@@QEAAJJPEBU_GUID@@KPEAUtagDISPPARAMS@@@Z; CError::PostError(long,_GUID const *,ulong,tagDISPPARAMS *)
0x383a50df9  jmp     loc_383A510A8
0x383a50dfe  mov     rax, [rsi+728h]
0x383a50e05  test    byte ptr [rax+190h], 1
0x383a50e0c  jz      short loc_383A50E5D
0x383a50e0e  cmp     dword ptr [rax+168h], 0
0x383a50e15  jle     short loc_383A50E54
0x383a50e17  mov     eax, 80004005h
0x383a50e1c  mov     ebx, eax
0x383a50e1e  test    byte ptr cs:_bidGblFlags, 2
0x383a50e25  jz      short loc_383A50E3B
0x383a50e27  mov     r8d, eax
0x383a50e2a  mov     edx, 3EC09h
0x383a50e2f  mov     rcx, cs:off_383B433F0; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383a50e36  call    _bidTraceHR
0x383a50e3b  mov     r8d, 9F1Dh; struct _GUID *
0x383a50e41  lea     rdx, IID_ITransactionJoin; int
0x383a50e48  mov     ecx, eax; this
0x383a50e4a  call    ?PostError@CError@@QEAAJJPEBU_GUID@@KPEAUtagDISPPARAMS@@@Z; CError::PostError(long,_GUID const *,ulong,tagDISPPARAMS *)
0x383a50e4f  jmp     loc_383A510A8
0x383a50e54  test    byte ptr [rax+190h], 1
0x383a50e5b  jnz     short loc_383A50EA7
0x383a50e5d  mov     rax, [rax+10h]
0x383a50e61  cmp     dword ptr [rax+338h], 0
0x383a50e68  jz      short loc_383A50EA7
0x383a50e6a  mov     eax, 80004005h
0x383a50e6f  mov     ebx, eax
0x383a50e71  test    byte ptr cs:_bidGblFlags, 2
0x383a50e78  jz      short loc_383A50E8E
0x383a50e7a  mov     r8d, eax
0x383a50e7d  mov     edx, 41809h
0x383a50e82  mov     rcx, cs:off_383B433F0; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383a50e89  call    _bidTraceHR
0x383a50e8e  mov     r8d, 9F05h; struct _GUID *
0x383a50e94  lea     rdx, IID_ITransactionJoin; int
0x383a50e9b  mov     ecx, eax; this
0x383a50e9d  call    ?PostError@CError@@QEAAJJPEBU_GUID@@KPEAUtagDISPPARAMS@@@Z; CError::PostError(long,_GUID const *,ulong,tagDISPPARAMS *)
0x383a50ea2  jmp     loc_383A510A8
0x383a50ea7  test    r14, r14
0x383a50eaa  jz      loc_383A50F44
0x383a50eb0  mov     rax, [r14]
0x383a50eb3  lea     rdx, [rsp+0E8h+Src]
0x383a50eb8  mov     rcx, r14
0x383a50ebb  call    qword ptr [rax+20h]
0x383a50ebe  mov     ebx, eax
0x383a50ec0  test    eax, eax
0x383a50ec2  jns     short loc_383A50EEA
0x383a50ec4  test    byte ptr cs:_bidGblFlags, 2
0x383a50ecb  jz      loc_383A510D9
0x383a50ed1  mov     r8d, eax
0x383a50ed4  mov     edx, 44C09h
0x383a50ed9  mov     rcx, cs:off_383B433F0; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383a50ee0  call    _bidTraceHR
0x383a50ee5  jmp     loc_383A510A8
0x383a50eea  cmp     [rsp+0E8h+Src], 0
0x383a50eef  jz      short loc_383A50F44
0x383a50ef1  test    byte ptr cs:_bidGblFlags, 2
0x383a50ef8  jz      short loc_383A50F2C
0x383a50efa  mov     rcx, cs:off_383B433F0; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383a50f01  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x383a50f08  test    rax, rax
0x383a50f0b  jz      short loc_383A50F2C
0x383a50f0d  mov     dword ptr [rsp+0E8h+var_C8], 11Bh
0x383a50f15  mov     r9d, 8004D017h
0x383a50f1b  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x383a50f22  mov     edx, 46C29h
0x383a50f27  call    _bidTraceW
0x383a50f2c  lea     rdx, IID_ITransactionJoin; int
0x383a50f33  mov     ecx, 8004D017h; this
0x383a50f38  call    ?PostHResult@CError@@QEAAJJPEBU_GUID@@@Z; CError::PostHResult(long,_GUID const *)
0x383a50f3d  mov     ebx, eax
0x383a50f3f  jmp     loc_383A510A8
0x383a50f44  lea     rcx, [rsp+0E8h+Uuid]; Uuid
0x383a50f49  call    cs:__imp_UuidCreate
0x383a50f4f  test    eax, eax
0x383a50f51  jns     short loc_383A50F85
0x383a50f53  test    byte ptr cs:_bidGblFlags, 2
0x383a50f5a  jz      short loc_383A50F70
0x383a50f5c  mov     r8d, eax
0x383a50f5f  mov     edx, 49C09h
0x383a50f64  mov     rcx, cs:off_383B433F0; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383a50f6b  call    _bidTraceHR
0x383a50f70  lea     rdx, IID_ITransactionJoin; int
0x383a50f77  mov     ecx, eax; this
0x383a50f79  call    ?PostHResult@CError@@QEAAJJPEBU_GUID@@@Z; CError::PostHResult(long,_GUID const *)
0x383a50f7e  mov     ebx, eax
0x383a50f80  jmp     loc_383A510A8
0x383a50f85  mov     rdx, r15; struct IUnknown *
0x383a50f88  mov     rcx, rsi; this
0x383a50f8b  call    ?EnlistTransaction@CDBConnection@@QEAAJPEAUIUnknown@@PEBU_GUID@@@Z; CDBConnection::EnlistTransaction(IUnknown *,_GUID const *)
0x383a50f90  mov     ebx, eax
0x383a50f92  test    eax, eax
0x383a50f94  jns     short loc_383A50FF8
0x383a50f96  test    byte ptr cs:_bidGblFlags, 2
0x383a50f9d  jz      short loc_383A50FB3
0x383a50f9f  mov     r8d, eax
0x383a50fa2  mov     edx, 4C809h
0x383a50fa7  mov     rcx, cs:off_383B433F0; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383a50fae  call    _bidTraceHR
0x383a50fb3  lea     r8, [rsi+88h]; struct _GUID *
0x383a50fba  lea     rdx, IID_ITransactionJoin; int
0x383a50fc1  mov     ecx, eax; this
0x383a50fc3  call    ?PostSqlErrors@CError@@QEAAJJPEBU_GUID@@PEAVCErrorData@@@Z; CError::PostSqlErrors(long,_GUID const *,CErrorData *)
0x383a50fc8  xor     edx, edx; struct IUnknown *
0x383a50fca  mov     rcx, rsi; this
0x383a50fcd  call    ?EnlistTransaction@CDBConnection@@QEAAJPEAUIUnknown@@PEBU_GUID@@@Z; CDBConnection::EnlistTransaction(IUnknown *,_GUID const *)
0x383a50fd2  test    byte ptr cs:_bidGblFlags, 2
0x383a50fd9  jz      loc_383A510D9
0x383a50fdf  mov     r8d, eax
0x383a50fe2  mov     edx, 4E409h
0x383a50fe7  mov     rcx, cs:off_383B433F0; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383a50fee  call    _bidTraceHR
0x383a50ff3  jmp     loc_383A510A8
0x383a50ff8  mov     rcx, [rdi+8]
0x383a50ffc  mov     rax, qword ptr [rsp+0E8h+Uuid.Data1]
0x383a51001  mov     [rcx+358h], rax
0x383a51008  mov     rax, qword ptr [rsp+0E8h+Uuid.Data4]
0x383a5100d  mov     [rcx+360h], rax
0x383a51014  mov     rcx, [rdi+8]
0x383a51018  mov     r8d, 2Ch ; ','; Size
0x383a5101e  add     rcx, 380h; void *
0x383a51025  test    r14, r14
0x383a51028  jz      short loc_383A51036
0x383a5102a  lea     rdx, [rsp+0E8h+Src]; Src
0x383a5102f  call    memcpy
0x383a51034  jmp     short loc_383A5103D
0x383a51036  xor     edx, edx; Val
0x383a51038  call    memset
0x383a5103d  mov     rax, [rdi+8]
0x383a51041  or      dword ptr [rax+350h], 8
0x383a51048  jmp     short loc_383A510A6
0x383a5104a  mov     rax, [rdi+8]
0x383a5104e  test    byte ptr [rax+350h], 8
0x383a51055  jz      short loc_383A510A6
0x383a51057  xor     edx, edx; struct IUnknown *
0x383a51059  mov     rcx, rsi; this
0x383a5105c  call    ?EnlistTransaction@CDBConnection@@QEAAJPEAUIUnknown@@PEBU_GUID@@@Z; CDBConnection::EnlistTransaction(IUnknown *,_GUID const *)
0x383a51061  mov     ebx, eax
0x383a51063  test    eax, eax
0x383a51065  jns     short loc_383A5109B
0x383a51067  test    byte ptr cs:_bidGblFlags, 2
0x383a5106e  jz      short loc_383A51084
0x383a51070  mov     r8d, eax
0x383a51073  mov     edx, 55809h
0x383a51078  mov     rcx, cs:off_383B433F0; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383a5107f  call    _bidTraceHR
0x383a51084  lea     r8, [rsi+88h]; struct _GUID *
0x383a5108b  lea     rdx, IID_ITransactionJoin; int
0x383a51092  mov     ecx, eax; this
0x383a51094  call    ?PostSqlErrors@CError@@QEAAJJPEBU_GUID@@PEAVCErrorData@@@Z; CError::PostSqlErrors(long,_GUID const *,CErrorData *)
0x383a51099  jmp     short loc_383A510A8
0x383a5109b  mov     rax, [rdi+8]
0x383a5109f  and     dword ptr [rax+350h], 0FFFFFFF7h
0x383a510a6  xor     ebx, ebx
0x383a510a8  test    byte ptr cs:_bidGblFlags, 2
0x383a510af  jz      short loc_383A510D9
0x383a510b1  mov     rax, cs:off_383B49C80; "<ITransactionJoin::JoinTransaction|OLED"...
0x383a510b8  test    rax, rax
0x383a510bb  jz      short loc_383A510D9
0x383a510bd  mov     r9d, ebx
0x383a510c0  mov     r8, cs:off_383B49C80; "<ITransactionJoin::JoinTransaction|OLED"...
  ... truncated ...
```
