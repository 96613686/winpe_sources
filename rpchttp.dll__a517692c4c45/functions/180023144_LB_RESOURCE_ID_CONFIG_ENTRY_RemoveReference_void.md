# LB_RESOURCE_ID_CONFIG_ENTRY::RemoveReference(void)

- ea: `0x180023144`
- end: `0x180023199`
- name: `?RemoveReference@LB_RESOURCE_ID_CONFIG_ENTRY@@QEAAXXZ`
- size: `85`
- prototype: `void __fastcall(LB_RESOURCE_ID_CONFIG_ENTRY *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180021d58`
- `0x180021f7c`
- `0x18002305c`
- `0x180023208`
- `0x180023688`

## callees

- `0x180021e20`
- `0x180023144`

## import_xrefs

- `RPCRT4!I_RpcLogEvent` at `0x180023173`
- `RPCRT4!I_RpcLogEvent` at `0x180023173`

## pseudocode

```c
void __fastcall LB_RESOURCE_ID_CONFIG_ENTRY::RemoveReference(LB_RESOURCE_ID_CONFIG_ENTRY *this, __int64 a2)
{
  unsigned int v3; // edx
  signed __int32 v4[8]; // [rsp+0h] [rbp-48h] BYREF

  _InterlockedOr(v4, 0);
  LOBYTE(a2) = 45;
  I_RpcLogEvent(114, a2, this, 2005440955, *((_DWORD *)this + 4), 1, 1);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 4, 0xFFFFFFFF) == 1 )
  {
    if ( this )
      LB_RESOURCE_ID_CONFIG_ENTRY::`scalar deleting destructor'(this, v3);
  }
}

```

## disassembly

```asm
0x180023144  push    rbx
0x180023146  sub     rsp, 40h
0x18002314a  mov     rbx, rcx
0x18002314d  lock or [rsp+48h+var_48], 0
0x180023152  mov     eax, [rcx+10h]
0x180023155  mov     r9d, 778899BBh
0x18002315b  mov     ecx, 1
0x180023160  mov     r8, rbx
0x180023163  mov     [rsp+48h+var_18], ecx
0x180023167  mov     dl, 2Dh ; '-'
0x180023169  mov     [rsp+48h+var_20], ecx
0x18002316d  mov     cl, 72h ; 'r'
0x18002316f  mov     [rsp+48h+var_28], eax
0x180023173  call    cs:__imp_I_RpcLogEvent
0x180023179  or      eax, 0FFFFFFFFh
0x18002317c  lock xadd [rbx+10h], eax
0x180023181  cmp     eax, 1
0x180023184  jnz     short loc_180023193
0x180023186  test    rbx, rbx
0x180023189  jz      short loc_180023193
0x18002318b  mov     rcx, rbx; this
0x18002318e  call    ??_GLB_RESOURCE_ID_CONFIG_ENTRY@@QEAAPEAXI@Z; LB_RESOURCE_ID_CONFIG_ENTRY::`scalar deleting destructor'(uint)
0x180023193  add     rsp, 40h
0x180023197  pop     rbx
0x180023198  retn
```
