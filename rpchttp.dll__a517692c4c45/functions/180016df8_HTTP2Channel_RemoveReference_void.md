# HTTP2Channel::RemoveReference(void)

- ea: `0x180016df8`
- end: `0x180016e4d`
- name: `?RemoveReference@HTTP2Channel@@QEAAXXZ`
- size: `85`
- prototype: `void __fastcall(HTTP2Channel *__hidden this)`
- caller_count: `22`
- callee_count: `2`
- tags: ``

## callers

- `0x180005320`
- `0x1800097b4`
- `0x18000a4ec`
- `0x18000ae80`
- `0x18000b100`
- `0x18000b8c0`
- `0x18000ba10`
- `0x18000dfe8`
- `0x180011108`
- `0x1800117f0`
- `0x180012110`
- `0x180013200`
- `0x180013920`
- `0x180014850`
- `0x180015790`
- `0x180017580`
- `0x180018100`
- `0x180018190`
- `0x1800184f0`
- `0x1800190d0`
- `0x180019e10`
- `0x18001a568`

## callees

- `0x180016df8`
- `0x180025010`

## import_xrefs

- `RPCRT4!I_RpcLogEvent` at `0x180016e25`
- `RPCRT4!I_RpcLogEvent` at `0x180016e25`

## pseudocode

```c
void __fastcall HTTP2Channel::RemoveReference(HTTP2Channel *this)
{
  volatile signed __int32 *v1; // rbx
  __int64 v2; // rdx
  __int64 v3; // r9
  HTTP2Channel *v4; // r8
  signed __int32 v5[8]; // [rsp+0h] [rbp-48h] BYREF
  int v6; // [rsp+20h] [rbp-28h]

  v1 = (volatile signed __int32 *)this;
  _InterlockedOr(v5, 0);
  v2 = *((unsigned int *)this + 9);
  v3 = *((int *)this + 8);
  v4 = this;
  LOBYTE(this) = 114;
  v6 = v2;
  LOBYTE(v2) = 45;
  I_RpcLogEvent(this, v2, v4, v3, v6, 1, 1);
  if ( _InterlockedExchangeAdd(v1 + 9, 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v1 + 56LL))(v1);
}

```

## disassembly

```asm
0x180016df8  push    rbx
0x180016dfa  sub     rsp, 40h
0x180016dfe  mov     rbx, rcx
0x180016e01  lock or [rsp+48h+var_48], 0
0x180016e06  mov     edx, [rcx+24h]
0x180016e09  mov     eax, 1
0x180016e0e  movsxd  r9, dword ptr [rcx+20h]
0x180016e12  mov     r8, rcx
0x180016e15  mov     [rsp+48h+var_18], eax
0x180016e19  mov     cl, 72h ; 'r'
0x180016e1b  mov     [rsp+48h+var_20], eax
0x180016e1f  mov     [rsp+48h+var_28], edx
0x180016e23  mov     dl, 2Dh ; '-'
0x180016e25  call    cs:__imp_I_RpcLogEvent
0x180016e2b  or      eax, 0FFFFFFFFh
0x180016e2e  lock xadd [rbx+24h], eax
0x180016e33  cmp     eax, 1
0x180016e36  jnz     short loc_180016E47
0x180016e38  mov     rax, [rbx]
0x180016e3b  mov     rcx, rbx
0x180016e3e  mov     rax, [rax+38h]
0x180016e42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e47  add     rsp, 40h
0x180016e4b  pop     rbx
0x180016e4c  retn
```
