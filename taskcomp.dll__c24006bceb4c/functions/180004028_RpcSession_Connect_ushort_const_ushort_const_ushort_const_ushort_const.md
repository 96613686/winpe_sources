# RpcSession::Connect(ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x180004028`
- end: `0x18000418d`
- name: `?Connect@RpcSession@@QEAAJPEBG000@Z`
- size: `357`
- prototype: `__int64 __fastcall(RpcSession *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000a994`

## callees

- `0x180003470`
- `0x180004028`
- `0x180004e50`
- `0x180004fbc`
- `0x18002e5b0`

## import_xrefs

- `RPCRT4!RpcStringFreeW` at `0x1800040aa`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18000414b`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18000414b`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000408a`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000408a`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800040d1`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800040d1`

## pseudocode

```c
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
    wmi::ScopeGuardImpl1<void * (*)(void *),unsigned short *>::~ScopeGuardImpl1<void * (*)(void *),unsigned short *>((__int64)v14);
  }
  _bstr_t::~_bstr_t((_bstr_t *)v13);
  return v6;
}

```

## disassembly

```asm
0x180004028  mov     [rsp-8+arg_8], rbx
0x18000402d  mov     [rsp-8+arg_10], rdi
0x180004032  push    rbp
0x180004033  lea     rbp, [rsp-4Fh]
0x180004038  sub     rsp, 0C0h
0x18000403f  mov     rax, cs:__security_cookie
0x180004046  xor     rax, rsp
0x180004049  mov     [rbp+4Fh+var_10], rax
0x18000404d  mov     rdi, rcx
0x180004050  mov     [rbp+4Fh+var_80], 0
0x180004058  lea     rdx, aHost; "host/"
0x18000405f  lea     rcx, [rbp+4Fh+var_70]; this
0x180004063  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180004068  nop
0x180004069  lea     rax, [rbp+4Fh+var_80]
0x18000406d  mov     [rsp+0C0h+StringBinding], rax; StringBinding
0x180004072  mov     [rsp+0C0h+Options], 0; Options
0x18000407b  xor     r9d, r9d; Endpoint
0x18000407e  xor     r8d, r8d; NetworkAddr
0x180004081  lea     rdx, Protseq; "ncalrpc"
0x180004088  xor     ecx, ecx; ObjUuid
0x18000408a  call    cs:__imp_RpcStringBindingComposeW
0x180004090  mov     ebx, eax
0x180004092  test    eax, eax
0x180004094  jz      short loc_1800040AA
0x180004096  jle     loc_180004161
0x18000409c  movzx   ebx, ax
0x18000409f  or      ebx, 80070000h
0x1800040a5  jmp     loc_180004161
0x1800040aa  mov     rax, cs:__imp_RpcStringFreeW
0x1800040b1  mov     [rbp+4Fh+var_68], 0
0x1800040b5  mov     [rbp+4Fh+var_60], rax
0x1800040b9  lea     rax, [rbp+4Fh+var_80]
0x1800040bd  mov     [rbp+4Fh+var_58], rax
0x1800040c1  mov     [rbp+4Fh+Binding], 0
0x1800040c9  lea     rdx, [rbp+4Fh+Binding]; Binding
0x1800040cd  mov     rcx, [rbp+4Fh+var_80]; StringBinding
0x1800040d1  call    cs:__imp_RpcBindingFromStringBindingW
0x1800040d7  mov     ebx, eax
0x1800040d9  test    eax, eax
0x1800040db  jz      short loc_1800040F3
0x1800040dd  jle     short loc_1800040E8
0x1800040df  movzx   ebx, ax
0x1800040e2  or      ebx, 80070000h
0x1800040e8  lea     rcx, [rbp+4Fh+var_68]
0x1800040ec  call    ??1?$ScopeGuardImpl1@P6APEAXPEAX@ZPEAG@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<void * (*)(void *),ushort *>::~ScopeGuardImpl1<void * (*)(void *),ushort *>(void)
0x1800040f1  jmp     short loc_180004161
0x1800040f3  mov     rcx, [rbp+4Fh+Binding]; Binding
0x1800040f7  mov     [rdi+10h], rcx
0x1800040fb  xorps   xmm0, xmm0
0x1800040fe  movups  [rbp+4Fh+var_50], xmm0
0x180004102  movups  [rbp+4Fh+var_40], xmm0
0x180004106  movups  [rbp+4Fh+var_30], xmm0
0x18000410a  mov     dword ptr [rbp+4Fh+var_30+0Ch], 2
0x180004111  mov     qword ptr [rbp+4Fh+var_20.Version], 1
0x180004119  mov     [rbp+4Fh+var_20.IdentityTracking], 0
0x180004120  mov     [rbp+4Fh+var_20.ImpersonationType], 3
0x180004127  lea     rax, [rbp+4Fh+var_20]
0x18000412b  mov     [rsp+0C0h+SecurityQOS], rax; SecurityQOS
0x180004130  mov     dword ptr [rsp+0C0h+StringBinding], 0FFFFFFFFh; AuthzSvc
0x180004138  mov     [rsp+0C0h+Options], 0; AuthIdentity
0x180004141  xor     edx, edx; ServerPrincName
0x180004143  lea     r9d, [rdx+0Ah]; AuthnSvc
0x180004147  lea     r8d, [rdx+6]; AuthnLevel
0x18000414b  call    cs:__imp_RpcBindingSetAuthInfoExW
0x180004151  mov     ebx, eax
0x180004153  test    eax, eax
0x180004155  jnz     short loc_1800040DD
0x180004157  lea     rcx, [rbp+4Fh+var_68]
0x18000415b  call    ??1?$ScopeGuardImpl1@P6APEAXPEAX@ZPEAG@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<void * (*)(void *),ushort *>::~ScopeGuardImpl1<void * (*)(void *),ushort *>(void)
0x180004160  nop
0x180004161  lea     rcx, [rbp+4Fh+var_70]; this
0x180004165  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18000416a  mov     eax, ebx
0x18000416c  mov     rcx, [rbp+4Fh+var_10]
0x180004170  xor     rcx, rsp; StackCookie
0x180004173  call    __security_check_cookie
0x180004178  lea     r11, [rsp+0C0h+var_s0]
0x180004180  mov     rbx, [r11+18h]
0x180004184  mov     rdi, [r11+20h]
0x180004188  mov     rsp, r11
0x18000418b  pop     rbp
0x18000418c  retn
```
