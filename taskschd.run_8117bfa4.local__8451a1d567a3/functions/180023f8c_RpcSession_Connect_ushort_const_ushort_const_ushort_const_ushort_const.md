# RpcSession::Connect(ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x180023f8c`
- end: `0x180024215`
- name: `?Connect@RpcSession@@QEAAJPEBG000@Z`
- size: `649`
- prototype: `int(RpcSession *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180023340`

## callees

- `0x180009150`
- `0x180023f8c`
- `0x180024220`
- `0x1800343c8`
- `0x18003b208`
- `0x18003c6d0`
- `0x180052640`

## import_xrefs

- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800240ad`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800240ad`
- `RPCRT4!RpcStringBindingComposeW` at `0x180024060`
- `RPCRT4!RpcStringBindingComposeW` at `0x180024060`
- `RPCRT4!RpcStringFreeW` at `0x180024086`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1800241c7`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1800241c7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x180023f8c  push    rbp
0x180023f8e  push    rbx
0x180023f8f  push    rsi
0x180023f90  push    rdi
0x180023f91  push    r12
0x180023f93  push    r13
0x180023f95  push    r14
0x180023f97  push    r15
0x180023f99  lea     rbp, [rsp-17h]
0x180023f9e  sub     rsp, 0C8h
0x180023fa5  mov     rax, cs:__security_cookie
0x180023fac  xor     rax, rsp
0x180023faf  mov     [rbp+4Fh+var_48], rax
0x180023fb3  mov     rsi, r9
0x180023fb6  mov     rdi, r8
0x180023fb9  mov     rbx, rdx
0x180023fbc  mov     r13, rcx
0x180023fbf  mov     r14, [rbp+4Fh+arg_20]
0x180023fc3  xor     r15d, r15d
0x180023fc6  mov     [rbp+4Fh+var_C0], r15
0x180023fca  lea     rdx, aHost; "host/"
0x180023fd1  lea     rcx, [rbp+4Fh+var_B8]; this
0x180023fd5  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180023fda  nop
0x180023fdb  test    rbx, rbx
0x180023fde  jz      short loc_180024039
0x180023fe0  cmp     [rbx], r15w
0x180023fe4  jz      short loc_180024039
0x180023fe6  lea     r12d, [r15+9]
0x180023fea  mov     rdx, rbx; unsigned __int16 *
0x180023fed  lea     rcx, [rbp+4Fh+var_B0]; this
0x180023ff1  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180023ff6  nop
0x180023ff7  lea     rdx, [rbp+4Fh+var_B0]; struct _bstr_t *
0x180023ffb  lea     rcx, [rbp+4Fh+var_B8]; struct _bstr_t *
0x180023fff  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x180024004  nop
0x180024005  lea     rcx, [rbp+4Fh+var_B0]; this
0x180024009  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18002400e  mov     rax, [rbp+4Fh+var_B8]
0x180024012  test    rax, rax
0x180024015  jz      short loc_18002401A
0x180024017  mov     r15, [rax]
0x18002401a  movzx   eax, word ptr [rbx+2]
0x18002401e  cmp     [rbx], ax
0x180024021  jnz     short loc_18002402D
0x180024023  cmp     ax, 5Ch ; '\'
0x180024027  jnz     short loc_18002402D
0x180024029  add     rbx, 4
0x18002402d  mov     r8, rbx
0x180024030  lea     rdx, aNcacnIpTcp; "ncacn_ip_tcp"
0x180024037  jmp     short loc_180024049
0x180024039  mov     r12d, 0Ah
0x18002403f  xor     r8d, r8d; NetworkAddr
0x180024042  lea     rdx, ProtSeq; "ncalrpc"
0x180024049  lea     rax, [rbp+4Fh+var_C0]
0x18002404d  mov     [rsp+100h+StringBinding], rax; StringBinding
0x180024052  mov     [rsp+100h+Options], 0; Options
0x18002405b  xor     r9d, r9d; Endpoint
0x18002405e  xor     ecx, ecx; ObjUuid
0x180024060  call    cs:__imp_RpcStringBindingComposeW
0x180024067  nop     dword ptr [rax+rax+00h]
0x18002406c  mov     ebx, eax
0x18002406e  test    eax, eax
0x180024070  jz      short loc_180024086
0x180024072  jle     loc_1800241E9
0x180024078  movzx   ebx, bx
0x18002407b  or      ebx, 80070000h
0x180024081  jmp     loc_1800241E9
0x180024086  mov     rax, cs:__imp_RpcStringFreeW
0x18002408d  mov     [rbp+4Fh+var_A0], 0
0x180024091  mov     [rbp+4Fh+var_98], rax
0x180024095  lea     rax, [rbp+4Fh+var_C0]
0x180024099  mov     [rbp+4Fh+var_90], rax
0x18002409d  mov     [rbp+4Fh+Binding], 0
0x1800240a5  lea     rdx, [rbp+4Fh+Binding]; Binding
0x1800240a9  mov     rcx, [rbp+4Fh+var_C0]; StringBinding
0x1800240ad  call    cs:__imp_RpcBindingFromStringBindingW
0x1800240b4  nop     dword ptr [rax+rax+00h]
0x1800240b9  mov     ebx, eax
0x1800240bb  test    eax, eax
0x1800240bd  jz      short loc_1800240D8
0x1800240bf  jle     short loc_1800240CA
0x1800240c1  movzx   ebx, ax
0x1800240c4  or      ebx, 80070000h
0x1800240ca  lea     rcx, [rbp+4Fh+var_A0]
0x1800240ce  call    ??1?$ScopeGuardImpl1@P6AXPEAX@ZPEAU_SYSTEMTIME@@@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<void (*)(void *),_SYSTEMTIME *>::~ScopeGuardImpl1<void (*)(void *),_SYSTEMTIME *>(void)
0x1800240d3  jmp     loc_1800241E9
0x1800240d8  mov     r10, [rbp+4Fh+Binding]
0x1800240dc  mov     [r13+10h], r10
0x1800240e0  xor     r13d, r13d
0x1800240e3  mov     eax, r13d
0x1800240e6  xorps   xmm0, xmm0
0x1800240e9  movups  xmmword ptr [rbp+4Fh+var_88], xmm0
0x1800240ed  movups  xmmword ptr [rbp+4Fh+var_78], xmm0
0x1800240f1  movups  xmmword ptr [rbp+4Fh+var_68], xmm0
0x1800240f5  mov     [rbp+4Fh+var_68+0Ch], 2
0x1800240fc  or      r9, 0FFFFFFFFFFFFFFFFh
0x180024100  test    rdi, rdi
0x180024103  jz      short loc_18002412F
0x180024105  cmp     [rdi], r13w
0x180024109  jz      short loc_18002412F
0x18002410b  mov     qword ptr [rbp+4Fh+var_88], rdi
0x18002410f  mov     rcx, r9
0x180024112  inc     rcx; unsigned __int64
0x180024115  cmp     [rdi+rcx*2], r13w
0x18002411a  jnz     short loc_180024112
0x18002411c  lea     rdx, [rbp+4Fh+var_88+8]; unsigned int *
0x180024120  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180024125  mov     ebx, eax
0x180024127  test    eax, eax
0x180024129  js      short loc_1800240CA
0x18002412b  lea     rax, [rbp+4Fh+var_88]
0x18002412f  test    rsi, rsi
0x180024132  jz      short loc_180024162
0x180024134  cmp     [rsi], r13w
0x180024138  jz      short loc_180024162
0x18002413a  mov     qword ptr [rbp+4Fh+var_78], rsi
0x18002413e  mov     rcx, r9
0x180024141  inc     rcx; unsigned __int64
0x180024144  cmp     [rsi+rcx*2], r13w
0x180024149  jnz     short loc_180024141
0x18002414b  lea     rdx, [rbp+4Fh+var_78+8]; unsigned int *
0x18002414f  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180024154  mov     ebx, eax
0x180024156  test    eax, eax
0x180024158  js      loc_1800240CA
0x18002415e  lea     rax, [rbp+4Fh+var_88]
0x180024162  test    r14, r14
0x180024165  jz      short loc_18002418F
0x180024167  mov     qword ptr [rbp+4Fh+var_68], r14
0x18002416b  inc     r9
0x18002416e  cmp     [r14+r9*2], r13w
0x180024173  jnz     short loc_18002416B
0x180024175  lea     rdx, [rbp+4Fh+var_68+8]; unsigned int *
0x180024179  mov     rcx, r9; unsigned __int64
0x18002417c  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180024181  mov     ebx, eax
0x180024183  test    eax, eax
0x180024185  js      loc_1800240CA
0x18002418b  lea     rax, [rbp+4Fh+var_88]
0x18002418f  mov     qword ptr [rbp+4Fh+var_58.Version], 1
0x180024197  mov     [rbp+4Fh+var_58.IdentityTracking], r13d
0x18002419b  mov     [rbp+4Fh+var_58.ImpersonationType], 3
0x1800241a2  lea     rcx, [rbp+4Fh+var_58]
0x1800241a6  mov     [rsp+100h+SecurityQOS], rcx; SecurityQOS
0x1800241ab  mov     dword ptr [rsp+100h+StringBinding], 0FFFFFFFFh; AuthzSvc
0x1800241b3  mov     [rsp+100h+Options], rax; AuthIdentity
0x1800241b8  mov     r9d, r12d; AuthnSvc
0x1800241bb  mov     r8d, 6; AuthnLevel
0x1800241c1  mov     rdx, r15; ServerPrincName
0x1800241c4  mov     rcx, r10; Binding
0x1800241c7  call    cs:__imp_RpcBindingSetAuthInfoExW
0x1800241ce  nop     dword ptr [rax+rax+00h]
0x1800241d3  mov     ebx, eax
0x1800241d5  test    eax, eax
0x1800241d7  jnz     loc_1800240BF
0x1800241dd  lea     rcx, [rbp+4Fh+var_A0]
0x1800241e1  call    ??1?$ScopeGuardImpl1@P6AXPEAX@ZPEAU_SYSTEMTIME@@@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<void (*)(void *),_SYSTEMTIME *>::~ScopeGuardImpl1<void (*)(void *),_SYSTEMTIME *>(void)
0x1800241e6  mov     ebx, r13d
0x1800241e9  lea     rcx, [rbp+4Fh+var_B8]; this
0x1800241ed  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800241f2  mov     eax, ebx
0x1800241f4  mov     rcx, [rbp+4Fh+var_48]
0x1800241f8  xor     rcx, rsp; StackCookie
0x1800241fb  call    __security_check_cookie
0x180024200  add     rsp, 0C8h
0x180024207  pop     r15
0x180024209  pop     r14
0x18002420b  pop     r13
0x18002420d  pop     r12
0x18002420f  pop     rdi
0x180024210  pop     rsi
0x180024211  pop     rbx
0x180024212  pop     rbp
0x180024213  retn
```
