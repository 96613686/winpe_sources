# RPC_INTERFACE::DispatchToStubWorker(_RPC_MESSAGE *,uint,int,long *)

- ea: `0x18001c6e0`
- end: `0x18001cf05`
- name: `?DispatchToStubWorker@RPC_INTERFACE@@AEAAJPEAU_RPC_MESSAGE@@IHPEAJ@Z`
- size: `2085`
- prototype: `__int64 __fastcall(RPC_INTERFACE *this, struct _RPC_MESSAGE *, unsigned int, int, int *)`
- caller_count: `4`
- callee_count: `14`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001c110`
- `0x180023b80`
- `0x1800287e0`
- `0x180070458`

## callees

- `0x18001c6e0`
- `0x18001e6d0`
- `0x18001e7d0`
- `0x180022fb8`
- `0x180028f44`
- `0x180028fcc`
- `0x180029018`
- `0x1800295d8`
- `0x180059b74`
- `0x180079a64`
- `0x18007d814`
- `0x18008bfe8`
- `0x1800ceda0`
- `0x1800d7010`

## import_xrefs

- `ntdll!RtlSetThreadSubProcessTag` at `0x18001c85f`
- `ntdll!RtlSetThreadSubProcessTag` at `0x18001c8ae`
- `ntdll!RtlSetThreadSubProcessTag` at `0x18001c85f`
- `ntdll!RtlSetThreadSubProcessTag` at `0x18001c8ae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001caac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001caac`

## pseudocode

```c
__int64 __fastcall RPC_INTERFACE::DispatchToStubWorker(
        RPC_INTERFACE *this,
        struct _RPC_MESSAGE *a2,
        unsigned int a3,
        int a4,
        int *a5)
{
  unsigned int v5; // r10d
  unsigned __int64 ReservedForNtRpc; // rbx
  unsigned int v9; // r12d
  char *v10; // r13
  __int64 v11; // rcx
  __int64 v12; // r14
  unsigned int ProcNum; // r15d
  __int64 v14; // rcx
  _DWORD *Handle; // rcx
  struct THREAD *v16; // rax
  int v17; // r8d
  _QWORD *ReservedForRuntime; // rax
  _QWORD *v19; // r14
  unsigned int v20; // ebx
  __int64 v21; // rax
  __int64 v22; // rcx
  __int64 v23; // rax
  struct ServerContextHandle *v24; // rdx
  void *Buffer; // rax
  unsigned int i; // ecx
  __int64 v28; // r13
  __int64 v29; // rdx
  unsigned int j; // ecx
  struct tagExtendedErrorInfo *ExtendedErrorInfoRecord; // rax
  struct tagExtendedErrorInfo *v32; // r14
  __int64 v33; // xmm0_8
  int v34; // eax
  __int64 v35; // xmm0_8
  int v36; // eax
  int v37; // eax
  __int64 v38; // xmm0_8
  int v39; // eax
  int v40; // eax
  __int64 v41; // xmm0_8
  int v42; // eax
  int v43; // eax
  __int64 v44; // rcx
  unsigned __int16 v45; // r8
  __int64 v46; // rax
  unsigned int v47; // ecx
  RPC_BINDING_HANDLE v48; // rcx
  signed __int32 v49[8]; // [rsp+0h] [rbp-100h] BYREF
  char v50; // [rsp+30h] [rbp-D0h] BYREF
  char v51; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v52; // [rsp+40h] [rbp-C0h]
  int *v53; // [rsp+48h] [rbp-B8h]
  struct _RPC_MESSAGE *v54; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v55; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v56; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v57; // [rsp+68h] [rbp-98h]
  __int64 v58; // [rsp+70h] [rbp-90h] BYREF
  __int64 v59; // [rsp+78h] [rbp-88h] BYREF
  __int64 v60; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v61[2]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v62; // [rsp+A0h] [rbp-60h]
  __int128 v63; // [rsp+B0h] [rbp-50h]
  __int64 v64; // [rsp+C0h] [rbp-40h]
  __int64 v65; // [rsp+C8h] [rbp-38h]
  __int128 v66; // [rsp+D0h] [rbp-30h]
  _DWORD v67[3]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v68[12]; // [rsp+ECh] [rbp-14h]
  __int64 v69; // [rsp+F8h] [rbp-8h]
  __int128 v70; // [rsp+100h] [rbp+0h]
  __int64 *v71; // [rsp+110h] [rbp+10h]
  __int128 v72; // [rsp+118h] [rbp+18h]
  __int64 v73; // [rsp+128h] [rbp+28h]
  __int128 v74; // [rsp+130h] [rbp+30h]
  _BYTE v75[16]; // [rsp+140h] [rbp+40h] BYREF
  char *v76; // [rsp+150h] [rbp+50h]
  __int64 v77; // [rsp+158h] [rbp+58h]
  char *v78; // [rsp+160h] [rbp+60h]
  __int64 v79; // [rsp+168h] [rbp+68h]
  __int64 *v80; // [rsp+170h] [rbp+70h]
  __int64 v81; // [rsp+178h] [rbp+78h]
  __int64 *v82; // [rsp+180h] [rbp+80h]
  __int64 v83; // [rsp+188h] [rbp+88h]
  __int64 *v84; // [rsp+190h] [rbp+90h]
  __int64 v85; // [rsp+198h] [rbp+98h]

  v5 = a3;
  v53 = a5;
  v52 = a3;
  ReservedForNtRpc = (unsigned __int64)NtCurrentTeb()->ReservedForNtRpc;
  if ( ReservedForNtRpc )
  {
    ReservedForNtRpc ^= 0xABABABABDEDEDEDEuLL;
    if ( *(HANDLE *)(ReservedForNtRpc + 16) != NtCurrentTeb()->ClientId.UniqueThread )
      __fastfail(0x1Eu);
  }
  v9 = 0;
  v10 = (char *)this + 80;
  if ( (*((_DWORD *)this + 42) & 0x2000000) != 0 )
  {
    v11 = *((_QWORD *)this + 22) + 80LL * a4;
    a2->TransferSyntax = (PRPC_SYNTAX_IDENTIFIER)v11;
    v12 = *(_QWORD *)(v11 + 24);
    if ( v12 )
      goto LABEL_6;
  }
  else
  {
    a2->TransferSyntax = (PRPC_SYNTAX_IDENTIFIER)((char *)this + 104);
  }
  v12 = *((_QWORD *)this + 16);
LABEL_6:
  if ( (*((_DWORD *)this + 2) & 2) != 0 )
    ProcNum = 0;
  else
    ProcNum = a2->ProcNum;
  if ( !a3 )
  {
    if ( (*((_DWORD *)this + 2) & 1) == 0 )
    {
      v44 = *(_QWORD *)this;
      if ( *(_DWORD *)(*(_QWORD *)this + 336LL) )
      {
        if ( !*(_DWORD *)(v44 + 340) || _InterlockedDecrement((volatile signed __int32 *)(v44 + 120)) >= 0 )
          goto LABEL_11;
        _InterlockedIncrement((volatile signed __int32 *)(v44 + 120));
        v9 = 1723;
        v45 = 182;
      }
      else
      {
        v9 = 1715;
        v45 = 181;
      }
      RpcpErrorAddRecord(2u, v9, v45, 0, 0);
LABEL_81:
      v5 = v52;
      goto LABEL_11;
    }
    if ( *((_DWORD *)this + 51) != 1234 )
    {
      _InterlockedOr(v49, 0);
      v47 = *((_DWORD *)this + 51);
      if ( *((_DWORD *)this + 87) > v47 )
      {
        v9 = 1723;
        _InterlockedOr(v49, 0);
        RpcpErrorAddRecord(2u, 1723, 0xB4u, *((_DWORD *)this + 87), v47);
        goto LABEL_81;
      }
    }
  }
LABEL_11:
  if ( ProcNum >= *(_DWORD *)v12 )
  {
    if ( v9 != 1723 )
      RPC_INTERFACE::EndCall(this, v5, 0);
    v9 = 1745;
    RpcpErrorAddRecord(2u, 1745, 0xB7u, 0, 0);
    goto LABEL_32;
  }
  if ( v9 )
  {
LABEL_32:
    (*(void (__fastcall **)(RPC_BINDING_HANDLE, struct _RPC_MESSAGE *))(*(_QWORD *)a2->Handle + 120LL))(a2->Handle, a2);
    return v9;
  }
  v14 = *(_QWORD *)this;
  v57 = 0;
  ++*(_DWORD *)(v14 + 64);
  *((_QWORD *)a2->ReservedForRuntime + 1) = a2->Buffer;
  Handle = a2->Handle;
  a2->RpcInterfaceInformation = v10;
  if ( v5 )
    Handle[58] |= 1u;
  *((_QWORD *)Handle + 28) = a2->Buffer;
  v16 = ThreadSelf();
  if ( v16 )
  {
    *((_DWORD *)v16 + 51) = ProcNum;
    *((_OWORD *)v16 + 13) = *(_OWORD *)((char *)this + 84);
    *((_DWORD *)v16 + 56) = *((_DWORD *)this + 25);
  }
  if ( *((_QWORD *)this + 69) )
    v57 = ((__int64 (*)(void))RtlSetThreadSubProcessTag)();
  if ( (unsigned int)((__int64 (__fastcall *)(_QWORD, struct _RPC_MESSAGE *, int *))DispatchToStubInC)(
                       *(_QWORD *)(*(_QWORD *)(v12 + 8) + 8LL * ProcNum),
                       a2,
                       v53) )
  {
    if ( dword_1800FE624 )
    {
      for ( i = 0; i < 4; ++i )
      {
        if ( `LogEventToEtw'::`2'::EtwEventSubjectFilter[i] == 120 )
          goto LABEL_56;
      }
      if ( (Microsoft_Windows_RPCEnableBits & 8) != 0 )
      {
        v46 = *(_QWORD *)(v12 + 8);
        v54 = a2;
        v51 = 83;
        v50 = 120;
        v56 = *(_QWORD *)(v46 + 8LL * ProcNum);
        v69 = 1;
        *((_QWORD *)&v70 + 1) = 1;
        v55 = *v53;
        *(_QWORD *)&v68[4] = &v50;
        *(_QWORD *)&v70 = &v51;
        v71 = &v55;
        *((_QWORD *)&v72 + 1) = &v56;
        *(_QWORD *)&v74 = &v54;
        *(_QWORD *)&v72 = 8;
        v73 = 8;
        *((_QWORD *)&v74 + 1) = 8;
        McGenEventWrite_EtwEventWriteTransfer(
          (unsigned int)&RpcEtwGuid_Context,
          (unsigned int)RPCLogEvent,
          v17,
          6,
          (__int64)v67);
      }
    }
LABEL_56:
    v9 = -1073606642;
    v28 = 3;
    LODWORD(v55) = GetCurrentThreadId();
    v67[0] = 3;
    LODWORD(v69) = 4;
    LOWORD(v70) = ProcNum;
    v29 = (unsigned int)*v53;
    LODWORD(v54) = *((_DWORD *)this + 21);
    v67[2] = (_DWORD)v54;
    LODWORD(v53) = a2->RpcFlags;
    LODWORD(v72) = (_DWORD)v53;
    LODWORD(v56) = v29;
    LODWORD(v71) = 3;
    LODWORD(v73) = 3;
    LODWORD(v74) = v55;
    if ( dword_1800FE624 )
    {
      for ( j = 0; j < 4; ++j )
      {
        if ( `LogEventToEtw'::`2'::EtwEventSubjectFilter[j] == 73 )
          goto LABEL_63;
      }
      if ( (Microsoft_Windows_RPCEnableBits & 8) != 0 )
      {
        v60 = (int)v54;
        v58 = v29;
        v76 = &v51;
        v59 = 1;
        v78 = &v50;
        v80 = &v58;
        v82 = &v59;
        v84 = &v60;
        v50 = 1;
        v51 = 73;
        v77 = 1;
        v79 = 1;
        v81 = 8;
        v83 = 8;
        v85 = 8;
        McGenEventWrite_EtwEventWriteTransfer(
          (unsigned int)&RpcEtwGuid_Context,
          (unsigned int)RPCLogEvent,
          (unsigned int)"HbBr",
          6,
          (__int64)v75);
      }
    }
LABEL_63:
    ExtendedErrorInfoRecord = AllocateExtendedErrorInfoRecord(4u);
    v32 = ExtendedErrorInfoRecord;
    if ( ExtendedErrorInfoRecord )
    {
      InitializePrivateEEInfo(ExtendedErrorInfoRecord);
      v33 = *(_QWORD *)v68;
      *((_WORD *)v32 + 28) = 1;
      *((_DWORD *)v32 + 12) = 1;
      *((_DWORD *)v32 + 13) = v56;
      *((_DWORD *)v32 + 17) = v67[1];
      *((_DWORD *)v32 + 18) = (_DWORD)v54;
      v34 = *(_DWORD *)&v68[8];
      *(_QWORD *)((char *)v32 + 76) = v33;
      v35 = *(_QWORD *)((char *)&v70 + 2);
      *((_DWORD *)v32 + 21) = v34;
      v36 = HIDWORD(v69);
      *((_DWORD *)v32 + 16) = 3;
      *((_DWORD *)v32 + 22) = 4;
      *((_DWORD *)v32 + 23) = v36;
      v37 = *(_DWORD *)((char *)&v70 + 10);
      *((_WORD *)v32 + 48) = ProcNum;
      *(_QWORD *)((char *)v32 + 98) = v35;
      v38 = *(_QWORD *)((char *)&v72 + 4);
      *(_DWORD *)((char *)v32 + 106) = v37;
      *((_WORD *)v32 + 55) = HIWORD(v70);
      v39 = HIDWORD(v71);
      *((_DWORD *)v32 + 28) = 3;
      *((_DWORD *)v32 + 29) = v39;
      *((_DWORD *)v32 + 30) = (_DWORD)v53;
      v40 = HIDWORD(v72);
      *(_QWORD *)((char *)v32 + 124) = v38;
      v41 = *(_QWORD *)((char *)&v74 + 4);
      *((_DWORD *)v32 + 33) = v40;
      v42 = HIDWORD(v73);
      *((_DWORD *)v32 + 34) = 3;
      *((_DWORD *)v32 + 35) = v42;
      *((_DWORD *)v32 + 36) = v55;
      v43 = HIDWORD(v74);
      *(_QWORD *)((char *)v32 + 148) = v41;
      *((_DWORD *)v32 + 39) = v43;
      if ( (unsigned int)AddPrivateRecord(v32) )
        FreeEEInfoRecord(v32);
    }
    else
    {
      do
        FreeEEInfoPrivateParam(&v67[6 * v28--]);
      while ( v28 != -1 );
    }
  }
  if ( *((_QWORD *)this + 69) )
    RtlSetThreadSubProcessTag(v57);
  ReservedForRuntime = a2->ReservedForRuntime;
  v61[0] = 0;
  v62 = 0;
  v61[1] = 0;
  v63 = 0;
  v65 = 0;
  v66 = 0;
  v64 = 0;
  *(_QWORD *)&v62 = ReservedForRuntime[1];
  *(_DWORD *)(ReservedForNtRpc + 120) &= ~4u;
  if ( *(_DWORD *)ReservedForNtRpc )
  {
    if ( !v9 || (void *)v62 == a2->Buffer )
      return v9;
    goto LABEL_32;
  }
  v19 = a2->Handle;
  if ( *((_DWORD *)a2->Handle + 65) )
  {
    v20 = 0;
    while ( v20 < *((_DWORD *)v19 + 64) )
    {
      v21 = v20++;
      v22 = 8 * v21;
      v23 = v19[31];
      v24 = *(struct ServerContextHandle **)(v22 + v23);
      if ( v24 )
      {
        if ( ((unsigned __int8)v24 & 1) != 0 )
        {
          --*((_DWORD *)v19 + 65);
          *(_QWORD *)(v22 + v23) = 0;
        }
        else
        {
          NDRSContextHandlePostDispatchProcessing((struct SCALL *)v19, v24);
        }
      }
    }
  }
  if ( (v19[29] & 1) != 0 )
    *((_DWORD *)v19 + 58) &= ~1u;
  Buffer = a2->Buffer;
  if ( v9 )
  {
    if ( (void *)v62 != Buffer )
      (*(void (__fastcall **)(RPC_BINDING_HANDLE, _QWORD *))(*(_QWORD *)a2->Handle + 120LL))(a2->Handle, v61);
    if ( a2->Buffer )
      (*(void (__fastcall **)(RPC_BINDING_HANDLE, struct _RPC_MESSAGE *))(*(_QWORD *)a2->Handle + 120LL))(
        a2->Handle,
        a2);
    RPC_INTERFACE::EndCall(this, v52, 0);
  }
  else
  {
    if ( (void *)v62 == Buffer )
    {
      v48 = a2->Handle;
      a2->RpcFlags = 0;
      a2->BufferLength = 0;
      (*(void (__fastcall **)(RPC_BINDING_HANDLE, struct _RPC_MESSAGE *, _QWORD))(*(_QWORD *)v48 + 112LL))(v48, a2, 0);
    }
    (*(void (__fastcall **)(RPC_BINDING_HANDLE, _QWORD *))(*(_QWORD *)a2->Handle + 120LL))(a2->Handle, v61);
    if ( !v52 && (*((_DWORD *)this + 2) & 1) == 0 && *(_DWORD *)(*(_QWORD *)this + 340LL) )
      _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)this + 120LL));
  }
  return v9;
}

```

## disassembly

```asm
0x18001c6e0  push    rbp
0x18001c6e2  push    rbx
0x18001c6e3  push    rsi
0x18001c6e4  push    rdi
0x18001c6e5  lea     rbp, [rsp-0C8h]
0x18001c6ed  sub     rsp, 1C8h
0x18001c6f4  mov     rax, cs:__security_cookie
0x18001c6fb  xor     rax, rsp
0x18001c6fe  mov     [rbp+0E0h+var_40], rax
0x18001c705  mov     rax, [rbp+0E0h+arg_20]
0x18001c70c  mov     r10d, r8d
0x18001c70f  mov     [rsp+1E0h+var_198], rax
0x18001c714  mov     rsi, rdx
0x18001c717  mov     rax, gs:30h
0x18001c720  mov     rdi, rcx
0x18001c723  mov     [rsp+1E0h+var_1A0], r8d
0x18001c728  mov     rbx, [rax+1698h]
0x18001c72f  test    rbx, rbx
0x18001c732  jz      short loc_18001C758
0x18001c734  mov     rax, 0ABABABABDEDEDEDEh
0x18001c73e  xor     rbx, rax
0x18001c741  mov     rax, gs:30h
0x18001c74a  mov     rcx, [rax+48h]
0x18001c74e  cmp     [rbx+10h], rcx
0x18001c752  jnz     loc_18001C944
0x18001c758  mov     [rsp+1E0h+arg_10], r12
0x18001c760  xor     r12d, r12d
0x18001c763  mov     [rsp+1E0h+var_20], r13
0x18001c76b  lea     r13, [rdi+50h]
0x18001c76f  test    dword ptr [r13+58h], 2000000h
0x18001c777  mov     [rsp+1E0h+var_28], r14
0x18001c77f  mov     [rsp+1E0h+var_30], r15
0x18001c787  jz      loc_18001C9FC
0x18001c78d  movsxd  rax, r9d
0x18001c790  lea     rcx, [rax+rax*4]
0x18001c794  shl     rcx, 4
0x18001c798  add     rcx, [rdi+0B0h]
0x18001c79f  mov     [rdx+20h], rcx
0x18001c7a3  mov     r14, [rcx+18h]
0x18001c7a7  test    r14, r14
0x18001c7aa  jnz     short loc_18001C7B3
0x18001c7ac  mov     r14, [rdi+80h]
0x18001c7b3  mov     eax, [rdi+8]
0x18001c7b6  test    al, 2
0x18001c7b8  jz      loc_18001C969
0x18001c7be  xor     r15d, r15d
0x18001c7c1  test    r8d, r8d
0x18001c7c4  jnz     short loc_18001C7E1
0x18001c7c6  mov     eax, [rdi+8]
0x18001c7c9  test    al, 1
0x18001c7cb  jz      loc_18001CC41
0x18001c7d1  cmp     dword ptr [rdi+0CCh], 4D2h
0x18001c7db  jnz     loc_18001CE5A
0x18001c7e1  cmp     r15d, [r14]
0x18001c7e4  jnb     loc_18001CA09
0x18001c7ea  test    r12d, r12d
0x18001c7ed  jnz     loc_18001CA45
0x18001c7f3  mov     rcx, [rdi]
0x18001c7f6  mov     [rsp+1E0h+var_178], 0
0x18001c7ff  mov     eax, [rcx+40h]
0x18001c802  inc     eax
0x18001c804  mov     [rcx+40h], eax
0x18001c807  mov     rcx, [rsi+30h]
0x18001c80b  mov     rax, [rsi+10h]
0x18001c80f  mov     [rcx+8], rax
0x18001c813  mov     rcx, [rsi]
0x18001c816  mov     [rsi+28h], r13
0x18001c81a  test    r10d, r10d
0x18001c81d  jnz     loc_18001CEA6
0x18001c823  mov     rax, [rsi+10h]
0x18001c827  mov     [rcx+0E0h], rax
0x18001c82e  call    ?ThreadSelf@@YAPEAVTHREAD@@XZ; ThreadSelf(void)
0x18001c833  test    rax, rax
0x18001c836  jz      short loc_18001C853
0x18001c838  mov     [rax+0CCh], r15d
0x18001c83f  movups  xmm0, xmmword ptr [rdi+54h]
0x18001c843  movups  xmmword ptr [rax+0D0h], xmm0
0x18001c84a  mov     ecx, [rdi+64h]
0x18001c84d  mov     [rax+0E0h], ecx
0x18001c853  mov     rcx, [rdi+228h]
0x18001c85a  test    rcx, rcx
0x18001c85d  jz      short loc_18001C870
0x18001c85f  call    cs:__imp_RtlSetThreadSubProcessTag
0x18001c866  nop     dword ptr [rax+rax+00h]
0x18001c86b  mov     [rsp+1E0h+var_178], rax
0x18001c870  mov     r8, [rsp+1E0h+var_198]
0x18001c875  mov     rdx, rsi
0x18001c878  mov     rax, cs:DispatchToStubInC
0x18001c87f  mov     ecx, r15d
0x18001c882  lea     r13, ds:0[rcx*8]
0x18001c88a  mov     rcx, [r14+8]
0x18001c88e  mov     rcx, [rcx+r13]
0x18001c892  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c897  test    eax, eax
0x18001c899  jnz     loc_18001CA75
0x18001c89f  cmp     qword ptr [rdi+228h], 0
0x18001c8a7  jz      short loc_18001C8BA
0x18001c8a9  mov     rcx, [rsp+1E0h+var_178]
0x18001c8ae  call    cs:__imp_RtlSetThreadSubProcessTag
0x18001c8b5  nop     dword ptr [rax+rax+00h]
0x18001c8ba  mov     rax, [rsi+30h]
0x18001c8be  xor     r10d, r10d
0x18001c8c1  mov     [rbp+0E0h+var_150], r10
0x18001c8c5  xorps   xmm0, xmm0
0x18001c8c8  movdqa  [rbp+0E0h+var_140], xmm0
0x18001c8cd  xorps   xmm1, xmm1
0x18001c8d0  mov     [rbp+0E0h+var_148], r10
0x18001c8d4  movdqa  [rbp+0E0h+var_130], xmm1
0x18001c8d9  mov     [rbp+0E0h+var_118], r10
0x18001c8dd  movdqa  [rbp+0E0h+var_110], xmm0
0x18001c8e2  mov     [rbp+0E0h+var_120], r10
0x18001c8e6  mov     rcx, [rax+8]
0x18001c8ea  mov     qword ptr [rbp+0E0h+var_140], rcx
0x18001c8ee  and     dword ptr [rbx+78h], 0FFFFFFFBh
0x18001c8f2  cmp     [rbx], r10d
0x18001c8f5  jnz     short loc_18001C94B
0x18001c8f7  mov     r14, [rsi]
0x18001c8fa  cmp     [r14+104h], r10d
0x18001c901  jbe     short loc_18001C972
0x18001c903  mov     ebx, r10d
0x18001c906  mov     r9d, [r14+100h]
0x18001c90d  cmp     ebx, r9d
0x18001c910  jnb     short loc_18001C972
0x18001c912  mov     eax, ebx
0x18001c914  inc     ebx
0x18001c916  lea     rcx, ds:0[rax*8]
0x18001c91e  mov     rax, [r14+0F8h]
0x18001c925  mov     rdx, [rcx+rax]; struct ServerContextHandle *
0x18001c929  test    rdx, rdx
0x18001c92c  jz      short loc_18001C90D
0x18001c92e  test    dl, 1
0x18001c931  jz      loc_18001CC31
0x18001c937  dec     dword ptr [r14+104h]
0x18001c93e  mov     [rcx+rax], r10
0x18001c942  jmp     short loc_18001C906
0x18001c944  mov     ecx, 1Eh
0x18001c949  int     29h; Win8: RtlFailFast(ecx)
0x18001c94b  test    r12d, r12d
0x18001c94e  jz      short loc_18001C9BD
0x18001c950  mov     rax, [rsi+10h]
0x18001c954  cmp     qword ptr [rbp+0E0h+var_140], rax
0x18001c958  jz      short loc_18001C9BD
0x18001c95a  mov     rcx, [rsi]
0x18001c95d  mov     rax, [rcx]
0x18001c960  mov     rax, [rax+78h]
0x18001c964  jmp     loc_18001CA4F
0x18001c969  mov     r15d, [rdx+1Ch]
0x18001c96d  jmp     loc_18001C7C1
0x18001c972  mov     eax, [r14+0E8h]
0x18001c979  test    al, 1
0x18001c97b  jnz     loc_18001CE4D
0x18001c981  mov     rax, [rsi+10h]
0x18001c985  test    r12d, r12d
0x18001c988  jnz     loc_18001CE16
0x18001c98e  cmp     qword ptr [rbp+0E0h+var_140], rax
0x18001c992  jz      loc_18001CECB
0x18001c998  mov     rcx, [rsi]
0x18001c99b  lea     rdx, [rbp+0E0h+var_150]
0x18001c99f  mov     rax, [rcx]
0x18001c9a2  mov     rax, [rax+78h]
0x18001c9a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c9ab  cmp     [rsp+1E0h+var_1A0], 0
0x18001c9b0  jnz     short loc_18001C9BD
0x18001c9b2  mov     eax, [rdi+8]
0x18001c9b5  test    al, 1
0x18001c9b7  jz      loc_18001CA5C
0x18001c9bd  mov     r14, [rsp+1E0h+var_28]
0x18001c9c5  mov     eax, r12d
0x18001c9c8  mov     r12, [rsp+1E0h+arg_10]
0x18001c9d0  mov     r13, [rsp+1E0h+var_20]
0x18001c9d8  mov     r15, [rsp+1E0h+var_30]
0x18001c9e0  mov     rcx, [rbp+0E0h+var_40]
0x18001c9e7  xor     rcx, rsp; StackCookie
0x18001c9ea  call    __security_check_cookie
0x18001c9ef  add     rsp, 1C8h
0x18001c9f6  pop     rdi
0x18001c9f7  pop     rsi
0x18001c9f8  pop     rbx
0x18001c9f9  pop     rbp
0x18001c9fa  retn
0x18001c9fc  lea     rax, [r13+18h]
0x18001ca00  mov     [rdx+20h], rax
0x18001ca04  jmp     loc_18001C7AC
0x18001ca09  cmp     r12d, 6BBh
0x18001ca10  jz      short loc_18001CA20
0x18001ca12  xor     r8d, r8d; int
0x18001ca15  mov     edx, r10d; unsigned int
0x18001ca18  mov     rcx, rdi; this
0x18001ca1b  call    ?EndCall@RPC_INTERFACE@@QEAAXIH@Z; RPC_INTERFACE::EndCall(uint,int)
0x18001ca20  mov     r12d, 6D1h
0x18001ca26  mov     [rsp+1E0h+var_1C0], 0; struct tagParam *
0x18001ca2f  mov     edx, r12d; int
0x18001ca32  mov     r8d, 0B7h; unsigned __int16
0x18001ca38  xor     r9d, r9d; int
0x18001ca3b  mov     ecx, 2; unsigned int
0x18001ca40  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x18001ca45  mov     rcx, [rsi]
0x18001ca48  mov     r8, [rcx]
0x18001ca4b  mov     rax, [r8+78h]
0x18001ca4f  mov     rdx, rsi
0x18001ca52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ca57  jmp     loc_18001C9BD
0x18001ca5c  mov     rax, [rdi]
0x18001ca5f  cmp     dword ptr [rax+154h], 0
0x18001ca66  jz      loc_18001C9BD
0x18001ca6c  lock inc dword ptr [rax+78h]
0x18001ca70  jmp     loc_18001C9BD
0x18001ca75  cmp     cs:dword_1800FE624, 0
0x18001ca7c  lea     rdx, ?EtwEventSubjectFilter@?1??LogEventToEtw@@YAXEE_J00@Z@4QBEB; "HbBr"
0x18001ca83  jz      short loc_18001CAA6
0x18001ca85  xor     ecx, ecx
0x18001ca87  cmp     ecx, 4
0x18001ca8a  jnb     short loc_18001CA99
0x18001ca8c  movsxd  rax, ecx
0x18001ca8f  cmp     byte ptr [rax+rdx], 78h ; 'x'
0x18001ca93  jz      short loc_18001CAA6
0x18001ca95  inc     ecx
0x18001ca97  jmp     short loc_18001CA87
0x18001ca99  test    cs:Microsoft_Windows_RPCEnableBits, 8
0x18001caa0  jnz     loc_18001CC9F
0x18001caa6  mov     r12d, 0C002100Eh
0x18001caac  call    cs:__imp_GetCurrentThreadId
0x18001cab3  nop     dword ptr [rax+rax+00h]
0x18001cab8  cmp     cs:dword_1800FE624, 0
0x18001cabf  mov     r13d, 3
0x18001cac5  mov     ecx, eax
0x18001cac7  mov     dword ptr [rsp+1E0h+var_188], eax
0x18001cacb  mov     rax, [rsp+1E0h+var_198]
0x18001cad0  mov     [rbp+0E0h+var_100], r13d
0x18001cad4  mov     dword ptr [rbp+0E0h+var_E8], 4
0x18001cadb  mov     word ptr [rbp+0E0h+var_E0], r15w
0x18001cae0  mov     edx, [rax]
0x18001cae2  mov     eax, [rdi+54h]
0x18001cae5  mov     dword ptr [rsp+1E0h+var_190], eax
0x18001cae9  mov     [rbp+0E0h+var_F8], eax
0x18001caec  mov     eax, [rsi+48h]
0x18001caef  mov     dword ptr [rsp+1E0h+var_198], eax
0x18001caf3  mov     dword ptr [rbp+0E0h+var_C8], eax
0x18001caf6  mov     dword ptr [rsp+1E0h+var_180], edx
0x18001cafa  mov     dword ptr [rbp+0E0h+var_D0], r13d
0x18001cafe  mov     dword ptr [rbp+0E0h+var_B8], r13d
0x18001cb02  mov     dword ptr [rbp+0E0h+var_B0], ecx
0x18001cb05  jz      short loc_18001CB30
0x18001cb07  xor     ecx, ecx
0x18001cb09  lea     r8, ?EtwEventSubjectFilter@?1??LogEventToEtw@@YAXEE_J00@Z@4QBEB; "HbBr"
0x18001cb10  cmp     ecx, 4
0x18001cb13  jnb     short loc_18001CB23
0x18001cb15  movsxd  rax, ecx
0x18001cb18  cmp     byte ptr [rax+r8], 49h ; 'I'
0x18001cb1d  jz      short loc_18001CB30
0x18001cb1f  inc     ecx
0x18001cb21  jmp     short loc_18001CB10
0x18001cb23  test    cs:Microsoft_Windows_RPCEnableBits, 8
0x18001cb2a  jnz     loc_18001CD44
0x18001cb30  mov     ecx, 4; unsigned int
0x18001cb35  call    ?AllocateExtendedErrorInfoRecord@@YAPEAUtagExtendedErrorInfo@@K@Z; AllocateExtendedErrorInfoRecord(ulong)
0x18001cb3a  mov     r14, rax
0x18001cb3d  test    rax, rax
0x18001cb40  jz      loc_18001CDF0
0x18001cb46  mov     rcx, rax; struct tagExtendedErrorInfo *
0x18001cb49  call    ?InitializePrivateEEInfo@@YAXPEAUtagExtendedErrorInfo@@@Z; InitializePrivateEEInfo(tagExtendedErrorInfo *)
0x18001cb4e  movsd   xmm0, [rbp+0E0h+var_F4]
0x18001cb53  mov     eax, 1
0x18001cb58  mov     [r14+38h], ax
0x18001cb5d  mov     rcx, r14; struct tagExtendedErrorInfo *
0x18001cb60  mov     [r14+30h], eax
0x18001cb64  mov     eax, dword ptr [rsp+1E0h+var_180]
0x18001cb68  mov     [r14+34h], eax
0x18001cb6c  mov     eax, [rbp+0E0h+var_FC]
0x18001cb6f  mov     [r14+44h], eax
0x18001cb73  mov     eax, dword ptr [rsp+1E0h+var_190]
0x18001cb77  mov     [r14+48h], eax
0x18001cb7b  mov     eax, [rbp+0E0h+var_EC]
0x18001cb7e  movsd   qword ptr [r14+4Ch], xmm0
0x18001cb84  movsd   xmm0, [rbp+0E0h+var_E0+2]
0x18001cb89  mov     [r14+54h], eax
0x18001cb8d  mov     eax, dword ptr [rbp+0E0h+var_E8+4]
0x18001cb90  mov     [r14+40h], r13d
0x18001cb94  mov     dword ptr [r14+58h], 4
0x18001cb9c  mov     [r14+5Ch], eax
0x18001cba0  mov     eax, [rbp+0E0h+var_D6]
0x18001cba3  mov     [r14+60h], r15w
0x18001cba8  movsd   qword ptr [r14+62h], xmm0
0x18001cbae  movsd   xmm0, [rbp+0E0h+var_C8+4]
0x18001cbb3  mov     [r14+6Ah], eax
0x18001cbb7  movzx   eax, [rbp+0E0h+var_D2]
0x18001cbbb  mov     [r14+6Eh], ax
0x18001cbc0  mov     eax, dword ptr [rbp+0E0h+var_D0+4]
0x18001cbc3  mov     [r14+70h], r13d
0x18001cbc7  mov     [r14+74h], eax
0x18001cbcb  mov     eax, dword ptr [rsp+1E0h+var_198]
0x18001cbcf  mov     [r14+78h], eax
0x18001cbd3  mov     eax, [rbp+0E0h+var_BC]
0x18001cbd6  movsd   qword ptr [r14+7Ch], xmm0
0x18001cbdc  movsd   xmm0, [rbp+0E0h+var_B0+4]
0x18001cbe1  mov     [r14+84h], eax
0x18001cbe8  mov     eax, dword ptr [rbp+0E0h+var_B8+4]
0x18001cbeb  mov     [r14+88h], r13d
0x18001cbf2  mov     [r14+8Ch], eax
0x18001cbf9  mov     eax, dword ptr [rsp+1E0h+var_188]
  ... truncated ...
```
