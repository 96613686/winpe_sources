# LB_RPCHTTP_SERVER::RemoveReference(void)

- ea: `0x180021238`
- end: `0x180021296`
- name: `?RemoveReference@LB_RPCHTTP_SERVER@@QEAAXXZ`
- size: `94`
- prototype: `void __fastcall(LB_RPCHTTP_SERVER *__hidden this)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x18001fc58`
- `0x180021ed8`
- `0x1800222b4`
- `0x18002305c`
- `0x18002330c`
- `0x1800237c8`

## callees

- `0x180021238`
- `0x180021d58`

## import_xrefs

- `RPCRT4!I_RpcFree` at `0x18002128a`
- `RPCRT4!I_RpcFree` at `0x18002128a`
- `RPCRT4!I_RpcLogEvent` at `0x180021267`
- `RPCRT4!I_RpcLogEvent` at `0x180021267`

## pseudocode

```c
void __fastcall LB_RPCHTTP_SERVER::RemoveReference(LB_RPCHTTP_SERVER *this, __int64 a2)
{
  signed __int32 v3[8]; // [rsp+0h] [rbp-48h] BYREF

  _InterlockedOr(v3, 0);
  LOBYTE(a2) = 45;
  I_RpcLogEvent(114, a2, this, 2005440938, *((_DWORD *)this + 4), 1, 1);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 4, 0xFFFFFFFF) == 1 )
  {
    if ( this )
    {
      LB_RPCHTTP_SERVER::~LB_RPCHTTP_SERVER(this);
      I_RpcFree(this);
    }
  }
}

```

## disassembly

```asm
0x180021238  push    rbx
0x18002123a  sub     rsp, 40h
0x18002123e  mov     rbx, rcx
0x180021241  lock or [rsp+48h+var_48], 0
0x180021246  mov     eax, [rcx+10h]
0x180021249  mov     r9d, 778899AAh
0x18002124f  mov     ecx, 1
0x180021254  mov     r8, rbx
0x180021257  mov     [rsp+48h+var_18], ecx
0x18002125b  mov     dl, 2Dh ; '-'
0x18002125d  mov     [rsp+48h+var_20], ecx
0x180021261  mov     cl, 72h ; 'r'
0x180021263  mov     [rsp+48h+var_28], eax
0x180021267  call    cs:__imp_I_RpcLogEvent
0x18002126d  or      eax, 0FFFFFFFFh
0x180021270  lock xadd [rbx+10h], eax
0x180021275  cmp     eax, 1
0x180021278  jnz     short loc_180021290
0x18002127a  test    rbx, rbx
0x18002127d  jz      short loc_180021290
0x18002127f  mov     rcx, rbx; this
0x180021282  call    ??1LB_RPCHTTP_SERVER@@QEAA@XZ; LB_RPCHTTP_SERVER::~LB_RPCHTTP_SERVER(void)
0x180021287  mov     rcx, rbx; Object
0x18002128a  call    cs:__imp_I_RpcFree
0x180021290  add     rsp, 40h
0x180021294  pop     rbx
0x180021295  retn
```
