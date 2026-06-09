# HTTP2Channel::AddReference(void)

- ea: `0x1800043d8`
- end: `0x180004411`
- name: `?AddReference@HTTP2Channel@@QEAAXXZ`
- size: `57`
- prototype: `void __fastcall(HTTP2Channel *__hidden this)`
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x1800054b8`
- `0x18000dfe8`
- `0x180012110`
- `0x180013920`
- `0x180014850`
- `0x180017580`
- `0x18001964c`
- `0x180019e10`
- `0x18001a568`

## import_xrefs

- `RPCRT4!I_RpcLogEvent` at `0x180004406`
- `RPCRT4!I_RpcLogEvent` at `0x180004406`

## pseudocode

```c
void __fastcall HTTP2Channel::AddReference(HTTP2Channel *this)
{
  signed __int32 v1; // edx
  __int64 v2; // r9
  __int64 v3; // rdx
  HTTP2Channel *v4; // r8
  int v5; // [rsp+20h] [rbp-28h]

  v1 = _InterlockedExchangeAdd((volatile signed __int32 *)this + 9, 1u);
  v2 = *((int *)this + 8);
  v3 = (unsigned int)(v1 + 1);
  v4 = this;
  v5 = v3;
  LOBYTE(this) = 114;
  LOBYTE(v3) = 43;
  I_RpcLogEvent(this, v3, v4, v2, v5, 1, 1);
}

```

## disassembly

```asm
0x1800043d8  sub     rsp, 48h
0x1800043dc  mov     r8d, 1
0x1800043e2  mov     edx, r8d
0x1800043e5  lock xadd [rcx+24h], edx
0x1800043ea  movsxd  r9, dword ptr [rcx+20h]
0x1800043ee  add     edx, r8d
0x1800043f1  mov     [rsp+48h+var_18], r8d
0x1800043f6  mov     [rsp+48h+var_20], r8d
0x1800043fb  mov     r8, rcx
0x1800043fe  mov     [rsp+48h+var_28], edx
0x180004402  mov     cl, 72h ; 'r'
0x180004404  mov     dl, 2Bh ; '+'
0x180004406  call    cs:__imp_I_RpcLogEvent
0x18000440c  add     rsp, 48h
0x180004410  retn
```
