# WanIpDeleteDialOutSubInterfaceComplete

- ea: `0x14000d2e0`
- end: `0x14000d2ff`
- name: `WanIpDeleteDialOutSubInterfaceComplete`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1400032dc`
- `0x14000d2e0`

## pseudocode

```c
void __fastcall WanIpDeleteDialOutSubInterfaceComplete(__int64 *a1)
{
  __int64 v1; // rcx

  v1 = *a1;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v1 + 96), 0xFFFFFFFF) == 1 )
    FreeConnection((_QWORD *)v1);
}

```

## disassembly

```asm
0x14000d2e0  sub     rsp, 28h
0x14000d2e4  mov     rcx, [rcx]; Entry
0x14000d2e7  or      eax, 0FFFFFFFFh
0x14000d2ea  lock xadd [rcx+60h], eax
0x14000d2ef  cmp     eax, 1
0x14000d2f2  jnz     short loc_14000D2F9
0x14000d2f4  call    FreeConnection
0x14000d2f9  add     rsp, 28h
0x14000d2fd  retn
```
