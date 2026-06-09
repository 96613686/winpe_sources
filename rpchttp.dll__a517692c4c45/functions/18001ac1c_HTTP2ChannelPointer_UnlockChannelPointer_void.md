# HTTP2ChannelPointer::UnlockChannelPointer(void)

- ea: `0x18001ac1c`
- end: `0x18001ac57`
- name: `?UnlockChannelPointer@HTTP2ChannelPointer@@QEAAXXZ`
- size: `59`
- prototype: `void __fastcall(HTTP2ChannelPointer *this, __int64)`
- caller_count: `42`
- callee_count: `0`
- tags: ``

## callers

- `0x180004058`
- `0x180005788`
- `0x1800058a0`
- `0x1800059b0`
- `0x180006050`
- `0x180007be0`
- `0x180007dcc`
- `0x180007e74`
- `0x180007ef0`
- `0x180009b40`
- `0x180009b90`
- `0x18000a2d8`
- `0x18000a340`
- `0x18000adc4`
- `0x18000ae20`
- `0x18000d934`
- `0x18000dfe8`
- `0x18000ed90`
- `0x18000f334`
- `0x18000f548`
- `0x1800106b8`
- `0x180010b58`
- `0x180010bbc`
- `0x180011450`
- `0x180011c90`
- `0x180012110`
- `0x180013920`
- `0x180014850`
- `0x1800158e0`
- `0x1800168d0`
- `0x180017db0`
- `0x180018690`
- `0x180018c70`
- `0x180018d50`
- `0x1800191ec`
- `0x180019a00`
- `0x180019a90`
- `0x180019e10`
- `0x18001a170`
- `0x18001a360`
- `0x18001a840`
- `0x18001adac`

## import_xrefs

- `RPCRT4!I_RpcLogEvent` at `0x18001ac48`
- `RPCRT4!I_RpcLogEvent` at `0x18001ac48`

## pseudocode

```c
void __fastcall HTTP2ChannelPointer::UnlockChannelPointer(HTTP2ChannelPointer *this, __int64 a2)
{
  signed __int32 v3[8]; // [rsp+0h] [rbp-48h] BYREF

  _InterlockedOr(v3, 0);
  LOBYTE(a2) = 45;
  I_RpcLogEvent(50, a2, this, *((_QWORD *)this + 1), *(_DWORD *)this, 1, 1);
  _InterlockedDecrement((volatile signed __int32 *)this);
}

```

## disassembly

```asm
0x18001ac1c  push    rbx
0x18001ac1e  sub     rsp, 40h
0x18001ac22  mov     rbx, rcx
0x18001ac25  lock or [rsp+48h+var_48], 0
0x18001ac2a  mov     eax, [rcx]
0x18001ac2c  mov     r8, rbx
0x18001ac2f  mov     r9, [rbx+8]
0x18001ac33  mov     ecx, 1
0x18001ac38  mov     [rsp+48h+var_18], ecx
0x18001ac3c  mov     dl, 2Dh ; '-'
0x18001ac3e  mov     [rsp+48h+var_20], ecx
0x18001ac42  mov     cl, 32h ; '2'
0x18001ac44  mov     [rsp+48h+var_28], eax
0x18001ac48  call    cs:__imp_I_RpcLogEvent
0x18001ac4e  lock dec dword ptr [rbx]
0x18001ac51  add     rsp, 40h
0x18001ac55  pop     rbx
0x18001ac56  retn
```
