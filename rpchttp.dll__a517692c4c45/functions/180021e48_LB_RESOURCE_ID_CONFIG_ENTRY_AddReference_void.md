# LB_RESOURCE_ID_CONFIG_ENTRY::AddReference(void)

- ea: `0x180021e48`
- end: `0x180021e7e`
- name: `?AddReference@LB_RESOURCE_ID_CONFIG_ENTRY@@QEAAXXZ`
- size: `54`
- prototype: `void __fastcall(LB_RESOURCE_ID_CONFIG_ENTRY *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x180021f7c`
- `0x1800222b4`
- `0x180023208`
- `0x180023688`

## import_xrefs

- `RPCRT4!I_RpcLogEvent` at `0x180021e73`
- `RPCRT4!I_RpcLogEvent` at `0x180021e73`

## pseudocode

```c
void __fastcall LB_RESOURCE_ID_CONFIG_ENTRY::AddReference(LB_RESOURCE_ID_CONFIG_ENTRY *this)
{
  LB_RESOURCE_ID_CONFIG_ENTRY *v1; // r8
  signed __int32 v2; // [rsp+20h] [rbp-28h]

  v1 = this;
  v2 = _InterlockedIncrement((volatile signed __int32 *)this + 4);
  LOBYTE(this) = 114;
  I_RpcLogEvent(this, 43, v1, 2005440955, v2, 1, 1);
}

```

## disassembly

```asm
0x180021e48  sub     rsp, 48h
0x180021e4c  mov     edx, 1
0x180021e51  mov     eax, edx
0x180021e53  lock xadd [rcx+10h], eax
0x180021e58  mov     [rsp+48h+var_18], edx
0x180021e5c  add     eax, edx
0x180021e5e  mov     [rsp+48h+var_20], edx
0x180021e62  mov     r8, rcx
0x180021e65  mov     dl, 2Bh ; '+'
0x180021e67  mov     [rsp+48h+var_28], eax
0x180021e6b  mov     r9d, 778899BBh
0x180021e71  mov     cl, 72h ; 'r'
0x180021e73  call    cs:__imp_I_RpcLogEvent
0x180021e79  add     rsp, 48h
0x180021e7d  retn
```
