# RpcSession::Connect(ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x18002237c`
- end: `0x1800225f2`
- name: `?Connect@RpcSession@@QEAAJPEBG000@Z`
- size: `630`
- prototype: `__int64 __fastcall(RpcSession *this, unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800218e0`

## callees

- `0x180008d30`
- `0x18002237c`
- `0x180022600`
- `0x1800318d8`
- `0x1800381f8`
- `0x180039590`
- `0x18004e950`

## import_xrefs

- `RPCRT4!RpcBindingFromStringBindingW` at `0x180022497`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180022497`
- `RPCRT4!RpcStringBindingComposeW` at `0x180022450`
- `RPCRT4!RpcStringBindingComposeW` at `0x180022450`
- `RPCRT4!RpcStringFreeW` at `0x180022470`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1800225ab`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1800225ab`

## pseudocode

```c
__int64 __fastcall RpcSession::Connect(
        RpcSession *this,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5)
{
  unsigned __int16 *v9; // r15
  unsigned int v10; // r12d
  unsigned __int16 v11; // ax
  unsigned __int16 *v12; // r8
  unsigned __int16 *v13; // rdx
  RPC_STATUS v14; // eax
  signed int v15; // ebx
  RPC_STATUS v16; // eax
  bool v17; // cc
  RPC_BINDING_HANDLE v18; // r10
  unsigned int *v19; // rax
  unsigned __int64 v20; // r9
  unsigned __int64 v21; // rcx
  unsigned __int64 v22; // rcx
  RPC_WSTR StringBinding; // [rsp+40h] [rbp-71h] BYREF
  unsigned __int16 **v25; // [rsp+48h] [rbp-69h] BYREF
  _BYTE v26[8]; // [rsp+50h] [rbp-61h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+58h] [rbp-59h] BYREF
  _BYTE v28[8]; // [rsp+60h] [rbp-51h] BYREF
  RPC_STATUS (__stdcall *v29)(RPC_WSTR *); // [rsp+68h] [rbp-49h]
  RPC_WSTR *p_StringBinding; // [rsp+70h] [rbp-41h]
  unsigned int v31[4]; // [rsp+78h] [rbp-39h] BYREF
  unsigned int v32[4]; // [rsp+88h] [rbp-29h] BYREF
  unsigned int v33[4]; // [rsp+98h] [rbp-19h] BYREF
  RPC_SECURITY_QOS SecurityQOS; // [rsp+A8h] [rbp-9h] BYREF

  v9 = 0;
  StringBinding = 0;
  _bstr_t::_bstr_t((_bstr_t *)&v25, L"host/");
  if ( a2 && *a2 )
  {
    v10 = 9;
    _bstr_t::_bstr_t((_bstr_t *)v26, a2);
    _bstr_t::operator+=((struct _bstr_t *)&v25, (struct _bstr_t *)v26);
    _bstr_t::_Free((_bstr_t *)v26);
    if ( v25 )
      v9 = *v25;
    v11 = a2[1];
    if ( *a2 == v11 && v11 == 92 )
      a2 += 2;
    v12 = a2;
    v13 = L"ncacn_ip_tcp";
  }
  else
  {
    v10 = 10;
    v12 = 0;
    v13 = L"ncalrpc";
  }
  v14 = RpcStringBindingComposeW(0, v13, v12, 0, 0, &StringBinding);
  v15 = v14;
  if ( !v14 )
  {
    v28[0] = 0;
    v29 = RpcStringFreeW;
    p_StringBinding = &StringBinding;
    Binding = 0;
    v16 = RpcBindingFromStringBindingW(StringBinding, &Binding);
    v15 = v16;
    v17 = v16 <= 0;
    if ( v16 )
    {
LABEL_14:
      if ( !v17 )
        v15 = (unsigned __int16)v16 | 0x80070000;
      goto LABEL_16;
    }
    v18 = Binding;
    *((_QWORD *)this + 2) = Binding;
    v19 = 0;
    *(_OWORD *)v31 = 0;
    *(_OWORD *)v32 = 0;
    *(_OWORD *)v33 = 0;
    v33[3] = 2;
    v20 = -1;
    if ( a3 && *a3 )
    {
      *(_QWORD *)v31 = a3;
      v21 = -1;
      do
        ++v21;
      while ( a3[v21] );
      v15 = ULongLongToULong(v21, &v31[2]);
      if ( v15 < 0 )
        goto LABEL_16;
      v19 = v31;
    }
    if ( a4 && *a4 )
    {
      *(_QWORD *)v32 = a4;
      v22 = v20;
      do
        ++v22;
      while ( a4[v22] );
      v15 = ULongLongToULong(v22, &v32[2]);
      if ( v15 < 0 )
        goto LABEL_16;
      v19 = v31;
    }
    if ( !a5 )
      goto LABEL_34;
    *(_QWORD *)v33 = a5;
    do
      ++v20;
    while ( a5[v20] );
    v15 = ULongLongToULong(v20, &v33[2]);
    if ( v15 >= 0 )
    {
      v19 = v31;
LABEL_34:
      *(_QWORD *)&SecurityQOS.Version = 1;
      SecurityQOS.IdentityTracking = 0;
      SecurityQOS.ImpersonationType = 3;
      v16 = RpcBindingSetAuthInfoExW(v18, v9, 6u, v10, v19, 0xFFFFFFFF, &SecurityQOS);
      v15 = v16;
      v17 = v16 <= 0;
      if ( !v16 )
      {
        wmi::ScopeGuardImpl1<void (*)(void *),_SYSTEMTIME *>::~ScopeGuardImpl1<void (*)(void *),_SYSTEMTIME *>(v28);
        v15 = 0;
        goto LABEL_36;
      }
      goto LABEL_14;
    }
LABEL_16:
    wmi::ScopeGuardImpl1<void (*)(void *),_SYSTEMTIME *>::~ScopeGuardImpl1<void (*)(void *),_SYSTEMTIME *>(v28);
    goto LABEL_36;
  }
  if ( v14 > 0 )
    v15 = (unsigned __int16)v14 | 0x80070000;
LABEL_36:
  _bstr_t::_Free((_bstr_t *)&v25);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18002237c  push    rbp
0x18002237e  push    rbx
0x18002237f  push    rsi
0x180022380  push    rdi
0x180022381  push    r12
0x180022383  push    r13
0x180022385  push    r14
0x180022387  push    r15
0x180022389  lea     rbp, [rsp-17h]
0x18002238e  sub     rsp, 0C8h
0x180022395  mov     rax, cs:__security_cookie
0x18002239c  xor     rax, rsp
0x18002239f  mov     [rbp+4Fh+var_48], rax
0x1800223a3  mov     rsi, r9
0x1800223a6  mov     rdi, r8
0x1800223a9  mov     rbx, rdx
0x1800223ac  mov     r13, rcx
0x1800223af  mov     r14, [rbp+4Fh+arg_20]
0x1800223b3  xor     r15d, r15d
0x1800223b6  mov     [rbp+4Fh+var_C0], r15
0x1800223ba  lea     rdx, aHost; "host/"
0x1800223c1  lea     rcx, [rbp+4Fh+var_B8]; this
0x1800223c5  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800223ca  nop
0x1800223cb  test    rbx, rbx
0x1800223ce  jz      short loc_180022429
0x1800223d0  cmp     [rbx], r15w
0x1800223d4  jz      short loc_180022429
0x1800223d6  lea     r12d, [r15+9]
0x1800223da  mov     rdx, rbx; unsigned __int16 *
0x1800223dd  lea     rcx, [rbp+4Fh+var_B0]; this
0x1800223e1  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800223e6  nop
0x1800223e7  lea     rdx, [rbp+4Fh+var_B0]; struct _bstr_t *
0x1800223eb  lea     rcx, [rbp+4Fh+var_B8]; struct _bstr_t *
0x1800223ef  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x1800223f4  nop
0x1800223f5  lea     rcx, [rbp+4Fh+var_B0]; this
0x1800223f9  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800223fe  mov     rax, [rbp+4Fh+var_B8]
0x180022402  test    rax, rax
0x180022405  jz      short loc_18002240A
0x180022407  mov     r15, [rax]
0x18002240a  movzx   eax, word ptr [rbx+2]
0x18002240e  cmp     [rbx], ax
0x180022411  jnz     short loc_18002241D
0x180022413  cmp     ax, 5Ch ; '\'
0x180022417  jnz     short loc_18002241D
0x180022419  add     rbx, 4
0x18002241d  mov     r8, rbx
0x180022420  lea     rdx, aNcacnIpTcp; "ncacn_ip_tcp"
0x180022427  jmp     short loc_180022439
0x180022429  mov     r12d, 0Ah
0x18002242f  xor     r8d, r8d; NetworkAddr
0x180022432  lea     rdx, ProtSeq; "ncalrpc"
0x180022439  lea     rax, [rbp+4Fh+var_C0]
0x18002243d  mov     [rsp+100h+StringBinding], rax; StringBinding
0x180022442  mov     [rsp+100h+Options], 0; Options
0x18002244b  xor     r9d, r9d; Endpoint
0x18002244e  xor     ecx, ecx; ObjUuid
0x180022450  call    cs:__imp_RpcStringBindingComposeW
0x180022456  mov     ebx, eax
0x180022458  test    eax, eax
0x18002245a  jz      short loc_180022470
0x18002245c  jle     loc_1800225C7
0x180022462  movzx   ebx, bx
0x180022465  or      ebx, 80070000h
0x18002246b  jmp     loc_1800225C7
0x180022470  mov     rax, cs:__imp_RpcStringFreeW
0x180022477  mov     [rbp+4Fh+var_A0], 0
0x18002247b  mov     [rbp+4Fh+var_98], rax
0x18002247f  lea     rax, [rbp+4Fh+var_C0]
0x180022483  mov     [rbp+4Fh+var_90], rax
0x180022487  mov     [rbp+4Fh+Binding], 0
0x18002248f  lea     rdx, [rbp+4Fh+Binding]; Binding
0x180022493  mov     rcx, [rbp+4Fh+var_C0]; StringBinding
0x180022497  call    cs:__imp_RpcBindingFromStringBindingW
0x18002249d  mov     ebx, eax
0x18002249f  test    eax, eax
0x1800224a1  jz      short loc_1800224BC
0x1800224a3  jle     short loc_1800224AE
0x1800224a5  movzx   ebx, ax
0x1800224a8  or      ebx, 80070000h
0x1800224ae  lea     rcx, [rbp+4Fh+var_A0]
0x1800224b2  call    ??1?$ScopeGuardImpl1@P6AXPEAX@ZPEAU_SYSTEMTIME@@@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<void (*)(void *),_SYSTEMTIME *>::~ScopeGuardImpl1<void (*)(void *),_SYSTEMTIME *>(void)
0x1800224b7  jmp     loc_1800225C7
0x1800224bc  mov     r10, [rbp+4Fh+Binding]
0x1800224c0  mov     [r13+10h], r10
0x1800224c4  xor     r13d, r13d
0x1800224c7  mov     eax, r13d
0x1800224ca  xorps   xmm0, xmm0
0x1800224cd  movups  xmmword ptr [rbp+4Fh+var_88], xmm0
0x1800224d1  movups  xmmword ptr [rbp+4Fh+var_78], xmm0
0x1800224d5  movups  xmmword ptr [rbp+4Fh+var_68], xmm0
0x1800224d9  mov     [rbp+4Fh+var_68+0Ch], 2
0x1800224e0  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800224e4  test    rdi, rdi
0x1800224e7  jz      short loc_180022513
0x1800224e9  cmp     [rdi], r13w
0x1800224ed  jz      short loc_180022513
0x1800224ef  mov     qword ptr [rbp+4Fh+var_88], rdi
0x1800224f3  mov     rcx, r9
0x1800224f6  inc     rcx; unsigned __int64
0x1800224f9  cmp     [rdi+rcx*2], r13w
0x1800224fe  jnz     short loc_1800224F6
0x180022500  lea     rdx, [rbp+4Fh+var_88+8]; unsigned int *
0x180022504  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180022509  mov     ebx, eax
0x18002250b  test    eax, eax
0x18002250d  js      short loc_1800224AE
0x18002250f  lea     rax, [rbp+4Fh+var_88]
0x180022513  test    rsi, rsi
0x180022516  jz      short loc_180022546
0x180022518  cmp     [rsi], r13w
0x18002251c  jz      short loc_180022546
0x18002251e  mov     qword ptr [rbp+4Fh+var_78], rsi
0x180022522  mov     rcx, r9
0x180022525  inc     rcx; unsigned __int64
0x180022528  cmp     [rsi+rcx*2], r13w
0x18002252d  jnz     short loc_180022525
0x18002252f  lea     rdx, [rbp+4Fh+var_78+8]; unsigned int *
0x180022533  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180022538  mov     ebx, eax
0x18002253a  test    eax, eax
0x18002253c  js      loc_1800224AE
0x180022542  lea     rax, [rbp+4Fh+var_88]
0x180022546  test    r14, r14
0x180022549  jz      short loc_180022573
0x18002254b  mov     qword ptr [rbp+4Fh+var_68], r14
0x18002254f  inc     r9
0x180022552  cmp     [r14+r9*2], r13w
0x180022557  jnz     short loc_18002254F
0x180022559  lea     rdx, [rbp+4Fh+var_68+8]; unsigned int *
0x18002255d  mov     rcx, r9; unsigned __int64
0x180022560  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180022565  mov     ebx, eax
0x180022567  test    eax, eax
0x180022569  js      loc_1800224AE
0x18002256f  lea     rax, [rbp+4Fh+var_88]
0x180022573  mov     qword ptr [rbp+4Fh+var_58.Version], 1
0x18002257b  mov     [rbp+4Fh+var_58.IdentityTracking], r13d
0x18002257f  mov     [rbp+4Fh+var_58.ImpersonationType], 3
0x180022586  lea     rcx, [rbp+4Fh+var_58]
0x18002258a  mov     [rsp+100h+SecurityQOS], rcx; SecurityQOS
0x18002258f  mov     dword ptr [rsp+100h+StringBinding], 0FFFFFFFFh; AuthzSvc
0x180022597  mov     [rsp+100h+Options], rax; AuthIdentity
0x18002259c  mov     r9d, r12d; AuthnSvc
0x18002259f  mov     r8d, 6; AuthnLevel
0x1800225a5  mov     rdx, r15; ServerPrincName
0x1800225a8  mov     rcx, r10; Binding
0x1800225ab  call    cs:__imp_RpcBindingSetAuthInfoExW
0x1800225b1  mov     ebx, eax
0x1800225b3  test    eax, eax
0x1800225b5  jnz     loc_1800224A3
0x1800225bb  lea     rcx, [rbp+4Fh+var_A0]
0x1800225bf  call    ??1?$ScopeGuardImpl1@P6AXPEAX@ZPEAU_SYSTEMTIME@@@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<void (*)(void *),_SYSTEMTIME *>::~ScopeGuardImpl1<void (*)(void *),_SYSTEMTIME *>(void)
0x1800225c4  mov     ebx, r13d
0x1800225c7  lea     rcx, [rbp+4Fh+var_B8]; this
0x1800225cb  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800225d0  mov     eax, ebx
0x1800225d2  mov     rcx, [rbp+4Fh+var_48]
0x1800225d6  xor     rcx, rsp; StackCookie
0x1800225d9  call    __security_check_cookie
0x1800225de  add     rsp, 0C8h
0x1800225e5  pop     r15
0x1800225e7  pop     r14
0x1800225e9  pop     r13
0x1800225eb  pop     r12
0x1800225ed  pop     rdi
0x1800225ee  pop     rsi
0x1800225ef  pop     rbx
0x1800225f0  pop     rbp
0x1800225f1  retn
```
