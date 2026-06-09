# RpcSession::Connect(ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x180004210`
- end: `0x180004388`
- name: `?Connect@RpcSession@@QEAAJPEBG000@Z`
- size: `376`
- prototype: `__int64 __fastcall(RpcSession *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000af88`

## callees

- `0x180003600`
- `0x180004210`
- `0x1800050d0`
- `0x18000525c`
- `0x180030700`

## import_xrefs

- `RPCRT4!RpcStringFreeW` at `0x180004298`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18000433f`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18000433f`
- `RPCRT4!RpcStringBindingComposeW` at `0x180004272`
- `RPCRT4!RpcStringBindingComposeW` at `0x180004272`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800042bf`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800042bf`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RpcSession::Connect(
        RpcSession *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  RPC_STATUS v5; // eax
  unsigned int v6; // ebx
  RPC_STATUS v7; // eax
  bool v8; // cc
  RPC_BINDING_HANDLE v9; // rcx
  RPC_WSTR StringBinding; // [rsp+40h] [rbp-31h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+48h] [rbp-29h] BYREF
  _BYTE v13[8]; // [rsp+50h] [rbp-21h] BYREF
  _BYTE v14[8]; // [rsp+58h] [rbp-19h] BYREF
  RPC_STATUS (__stdcall *v15)(RPC_WSTR *); // [rsp+60h] [rbp-11h]
  RPC_WSTR *p_StringBinding; // [rsp+68h] [rbp-9h]
  __int128 v17; // [rsp+70h] [rbp-1h]
  __int128 v18; // [rsp+80h] [rbp+Fh]
  __int128 v19; // [rsp+90h] [rbp+1Fh]
  RPC_SECURITY_QOS SecurityQOS; // [rsp+A0h] [rbp+2Fh] BYREF

  StringBinding = 0;
  _bstr_t::_bstr_t((_bstr_t *)v13, L"host/");
  v5 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, 0, 0, &StringBinding);
  v6 = v5;
  if ( v5 )
  {
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
  }
  else
  {
    v14[0] = 0;
    v15 = RpcStringFreeW;
    p_StringBinding = &StringBinding;
    Binding = 0;
    v7 = RpcBindingFromStringBindingW(StringBinding, &Binding);
    v6 = v7;
    v8 = v7 <= 0;
    if ( v7 )
      goto LABEL_5;
    v9 = Binding;
    *((_QWORD *)this + 2) = Binding;
    v17 = 0;
    v18 = 0;
    v19 = 0;
    HIDWORD(v19) = 2;
    *(_QWORD *)&SecurityQOS.Version = 1;
    SecurityQOS.IdentityTracking = 0;
    SecurityQOS.ImpersonationType = 3;
    v7 = RpcBindingSetAuthInfoExW(v9, 0, 6u, 0xAu, 0, 0xFFFFFFFF, &SecurityQOS);
    v6 = v7;
    v8 = v7 <= 0;
    if ( v7 )
    {
LABEL_5:
      if ( !v8 )
        v6 = (unsigned __int16)v7 | 0x80070000;
    }
    wmi::ScopeGuardImpl1<void * (*)(void *),unsigned short *>::~ScopeGuardImpl1<void * (*)(void *),unsigned short *>(v14);
  }
  _bstr_t::~_bstr_t((_bstr_t *)v13);
  return v6;
}

```

## disassembly

```asm
0x180004210  mov     [rsp-8+arg_8], rbx
0x180004215  mov     [rsp-8+arg_10], rdi
0x18000421a  push    rbp
0x18000421b  lea     rbp, [rsp-4Fh]
0x180004220  sub     rsp, 0C0h
0x180004227  mov     rax, cs:__security_cookie
0x18000422e  xor     rax, rsp
0x180004231  mov     [rbp+4Fh+var_10], rax
0x180004235  mov     rdi, rcx
0x180004238  mov     [rbp+4Fh+var_80], 0
0x180004240  lea     rdx, aHost; "host/"
0x180004247  lea     rcx, [rbp+4Fh+var_70]; this
0x18000424b  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180004250  nop
0x180004251  lea     rax, [rbp+4Fh+var_80]
0x180004255  mov     [rsp+0C0h+StringBinding], rax; StringBinding
0x18000425a  mov     [rsp+0C0h+Options], 0; Options
0x180004263  xor     r9d, r9d; Endpoint
0x180004266  xor     r8d, r8d; NetworkAddr
0x180004269  lea     rdx, Protseq; "ncalrpc"
0x180004270  xor     ecx, ecx; ObjUuid
0x180004272  call    cs:__imp_RpcStringBindingComposeW
0x180004279  nop     dword ptr [rax+rax+00h]
0x18000427e  mov     ebx, eax
0x180004280  test    eax, eax
0x180004282  jz      short loc_180004298
0x180004284  jle     loc_18000435B
0x18000428a  movzx   ebx, ax
0x18000428d  or      ebx, 80070000h
0x180004293  jmp     loc_18000435B
0x180004298  mov     rax, cs:__imp_RpcStringFreeW
0x18000429f  mov     [rbp+4Fh+var_68], 0
0x1800042a3  mov     [rbp+4Fh+var_60], rax
0x1800042a7  lea     rax, [rbp+4Fh+var_80]
0x1800042ab  mov     [rbp+4Fh+var_58], rax
0x1800042af  mov     [rbp+4Fh+Binding], 0
0x1800042b7  lea     rdx, [rbp+4Fh+Binding]; Binding
0x1800042bb  mov     rcx, [rbp+4Fh+var_80]; StringBinding
0x1800042bf  call    cs:__imp_RpcBindingFromStringBindingW
0x1800042c6  nop     dword ptr [rax+rax+00h]
0x1800042cb  mov     ebx, eax
0x1800042cd  test    eax, eax
0x1800042cf  jz      short loc_1800042E7
0x1800042d1  jle     short loc_1800042DC
0x1800042d3  movzx   ebx, ax
0x1800042d6  or      ebx, 80070000h
0x1800042dc  lea     rcx, [rbp+4Fh+var_68]
0x1800042e0  call    ??1?$ScopeGuardImpl1@P6APEAXPEAX@ZPEAG@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<void * (*)(void *),ushort *>::~ScopeGuardImpl1<void * (*)(void *),ushort *>(void)
0x1800042e5  jmp     short loc_18000435B
0x1800042e7  mov     rcx, [rbp+4Fh+Binding]; Binding
0x1800042eb  mov     [rdi+10h], rcx
0x1800042ef  xorps   xmm0, xmm0
0x1800042f2  movups  [rbp+4Fh+var_50], xmm0
0x1800042f6  movups  [rbp+4Fh+var_40], xmm0
0x1800042fa  movups  [rbp+4Fh+var_30], xmm0
0x1800042fe  mov     dword ptr [rbp+4Fh+var_30+0Ch], 2
0x180004305  mov     qword ptr [rbp+4Fh+var_20.Version], 1
0x18000430d  mov     [rbp+4Fh+var_20.IdentityTracking], 0
0x180004314  mov     [rbp+4Fh+var_20.ImpersonationType], 3
0x18000431b  lea     rax, [rbp+4Fh+var_20]
0x18000431f  mov     [rsp+0C0h+SecurityQOS], rax; SecurityQOS
0x180004324  mov     dword ptr [rsp+0C0h+StringBinding], 0FFFFFFFFh; AuthzSvc
0x18000432c  mov     [rsp+0C0h+Options], 0; AuthIdentity
0x180004335  xor     edx, edx; ServerPrincName
0x180004337  lea     r9d, [rdx+0Ah]; AuthnSvc
0x18000433b  lea     r8d, [rdx+6]; AuthnLevel
0x18000433f  call    cs:__imp_RpcBindingSetAuthInfoExW
0x180004346  nop     dword ptr [rax+rax+00h]
0x18000434b  mov     ebx, eax
0x18000434d  test    eax, eax
0x18000434f  jnz     short loc_1800042D1
0x180004351  lea     rcx, [rbp+4Fh+var_68]
0x180004355  call    ??1?$ScopeGuardImpl1@P6APEAXPEAX@ZPEAG@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<void * (*)(void *),ushort *>::~ScopeGuardImpl1<void * (*)(void *),ushort *>(void)
0x18000435a  nop
0x18000435b  lea     rcx, [rbp+4Fh+var_70]; this
0x18000435f  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180004364  mov     eax, ebx
0x180004366  mov     rcx, [rbp+4Fh+var_10]
0x18000436a  xor     rcx, rsp; StackCookie
0x18000436d  call    __security_check_cookie
0x180004372  lea     r11, [rsp+0C0h+var_s0]
0x18000437a  mov     rbx, [r11+18h]
0x18000437e  mov     rdi, [r11+20h]
0x180004382  mov     rsp, r11
0x180004385  pop     rbp
0x180004386  retn
```
