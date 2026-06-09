# HTTP2Channel::FinishSubmitAsync(void)

- ea: `0x180009d58`
- end: `0x180009d95`
- name: `?FinishSubmitAsync@HTTP2Channel@@QEAAXXZ`
- size: `61`
- prototype: `void __fastcall(HTTP2Channel *__hidden this)`
- caller_count: `23`
- callee_count: `0`
- tags: ``

## callers

- `0x180007f88`
- `0x1800081e8`
- `0x180008d20`
- `0x180009d9c`
- `0x180010940`
- `0x180010a60`
- `0x180011390`
- `0x1800114d0`
- `0x1800117f0`
- `0x180012110`
- `0x180013200`
- `0x180013920`
- `0x180015790`
- `0x1800158e0`
- `0x180017580`
- `0x180018130`
- `0x1800189a0`
- `0x1800190d0`
- `0x180019490`
- `0x18001964c`
- `0x180019858`
- `0x18001a568`
- `0x18001ac8c`

## import_xrefs

- `RPCRT4!I_RpcLogEvent` at `0x180009d85`
- `RPCRT4!I_RpcLogEvent` at `0x180009d85`

## pseudocode

```c
void __fastcall HTTP2Channel::FinishSubmitAsync(HTTP2Channel *this)
{
  HTTP2Channel *v1; // rbx
  __int64 v2; // rdx
  __int64 v3; // r9
  HTTP2Channel *v4; // r8
  signed __int32 v5[8]; // [rsp+0h] [rbp-48h] BYREF
  int v6; // [rsp+20h] [rbp-28h]

  v1 = this;
  _InterlockedOr(v5, 0);
  v2 = *((unsigned int *)this + 11);
  v3 = *((int *)this + 8);
  v4 = this;
  LOBYTE(this) = 50;
  v6 = v2;
  LOBYTE(v2) = 45;
  I_RpcLogEvent(this, v2, v4, v3, v6, 1, 1);
  _InterlockedDecrement((volatile signed __int32 *)v1 + 11);
}

```

## disassembly

```asm
0x180009d58  push    rbx
0x180009d5a  sub     rsp, 40h
0x180009d5e  mov     rbx, rcx
0x180009d61  lock or [rsp+48h+var_48], 0
0x180009d66  mov     edx, [rcx+2Ch]
0x180009d69  mov     eax, 1
0x180009d6e  movsxd  r9, dword ptr [rcx+20h]
0x180009d72  mov     r8, rcx
0x180009d75  mov     [rsp+48h+var_18], eax
0x180009d79  mov     cl, 32h ; '2'
0x180009d7b  mov     [rsp+48h+var_20], eax
0x180009d7f  mov     [rsp+48h+var_28], edx
0x180009d83  mov     dl, 2Dh ; '-'
0x180009d85  call    cs:__imp_I_RpcLogEvent
0x180009d8b  lock dec dword ptr [rbx+2Ch]
0x180009d8f  add     rsp, 40h
0x180009d93  pop     rbx
0x180009d94  retn
```
