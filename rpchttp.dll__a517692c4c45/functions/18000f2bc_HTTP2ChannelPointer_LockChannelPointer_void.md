# HTTP2ChannelPointer::LockChannelPointer(void)

- ea: `0x18000f2bc`
- end: `0x18000f32c`
- name: `?LockChannelPointer@HTTP2ChannelPointer@@QEAAPEAVHTTP2Channel@@XZ`
- size: `112`
- prototype: `struct HTTP2Channel *__fastcall(HTTP2ChannelPointer *this, __int64)`
- caller_count: `18`
- callee_count: `1`
- tags: ``

## callers

- `0x180004058`
- `0x180006050`
- `0x180007be0`
- `0x18000a2d8`
- `0x18000adc4`
- `0x18000ae20`
- `0x18000f334`
- `0x18000f488`
- `0x18000f548`
- `0x1800106b8`
- `0x180010b58`
- `0x180012110`
- `0x180013920`
- `0x180014850`
- `0x1800158e0`
- `0x1800168d0`
- `0x180018690`
- `0x18001a840`

## callees

- `0x18000f2bc`

## import_xrefs

- `RPCRT4!I_RpcLogEvent` at `0x18000f2ec`
- `RPCRT4!I_RpcLogEvent` at `0x18000f316`
- `RPCRT4!I_RpcLogEvent` at `0x18000f2ec`
- `RPCRT4!I_RpcLogEvent` at `0x18000f316`

## pseudocode

```c
struct HTTP2Channel *__fastcall HTTP2ChannelPointer::LockChannelPointer(HTTP2ChannelPointer *this, __int64 a2)
{
  HTTP2ChannelPointer *v2; // rbx
  int v3; // eax
  __int64 v4; // r9
  HTTP2ChannelPointer *v5; // r8
  __int64 v6; // rcx
  signed __int32 v7; // edx
  bool v8; // sf
  __int64 v9; // rdx
  struct HTTP2Channel *result; // rax
  signed __int32 v11[8]; // [rsp+0h] [rbp-48h] BYREF
  int v12; // [rsp+20h] [rbp-28h]

  v2 = this;
  _InterlockedOr(v11, 0);
  v3 = *(_DWORD *)this;
  v4 = *((_QWORD *)this + 1);
  v5 = this;
  LOBYTE(a2) = 43;
  LOBYTE(this) = 50;
  I_RpcLogEvent(this, a2, v5, v4, v3, 1, 1);
  v7 = _InterlockedExchangeAdd((volatile signed __int32 *)v2, 1u);
  v8 = v7 + 1 < 0;
  v9 = (unsigned int)(v7 + 1);
  result = (struct HTTP2Channel *)*((_QWORD *)v2 + 1);
  if ( v8 )
  {
    v12 = v9;
    LOBYTE(v6) = 50;
    LOBYTE(v9) = 45;
    I_RpcLogEvent(v6, v9, v2, result, v12, 1, 1);
    _InterlockedDecrement((volatile signed __int32 *)v2);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000f2bc  mov     [rsp+arg_0], rbx
0x18000f2c1  push    rdi
0x18000f2c2  sub     rsp, 40h
0x18000f2c6  mov     rbx, rcx
0x18000f2c9  lock or [rsp+48h+var_48], 0
0x18000f2ce  mov     eax, [rcx]
0x18000f2d0  mov     edi, 1
0x18000f2d5  mov     r9, [rcx+8]
0x18000f2d9  mov     r8, rcx
0x18000f2dc  mov     [rsp+48h+var_18], edi
0x18000f2e0  mov     dl, 2Bh ; '+'
0x18000f2e2  mov     [rsp+48h+var_20], edi
0x18000f2e6  mov     cl, 32h ; '2'
0x18000f2e8  mov     [rsp+48h+var_28], eax
0x18000f2ec  call    cs:__imp_I_RpcLogEvent
0x18000f2f2  mov     edx, edi
0x18000f2f4  lock xadd [rbx], edx
0x18000f2f8  add     edx, edi
0x18000f2fa  mov     rax, [rbx+8]
0x18000f2fe  jns     short loc_18000F321
0x18000f300  mov     [rsp+48h+var_18], edi
0x18000f304  mov     r9, rax
0x18000f307  mov     [rsp+48h+var_20], edi
0x18000f30b  mov     r8, rbx
0x18000f30e  mov     [rsp+48h+var_28], edx
0x18000f312  mov     cl, 32h ; '2'
0x18000f314  mov     dl, 2Dh ; '-'
0x18000f316  call    cs:__imp_I_RpcLogEvent
0x18000f31c  lock dec dword ptr [rbx]
0x18000f31f  xor     eax, eax
0x18000f321  mov     rbx, [rsp+48h+arg_0]
0x18000f326  add     rsp, 40h
0x18000f32a  pop     rdi
0x18000f32b  retn
```
