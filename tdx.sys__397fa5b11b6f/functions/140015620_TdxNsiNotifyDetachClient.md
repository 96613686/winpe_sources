# TdxNsiNotifyDetachClient

- ea: `0x140015620`
- end: `0x140015650`
- name: `TdxNsiNotifyDetachClient`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140015620`

## import_xrefs

- `NETIO!NmrProviderDetachClientComplete` at `0x140015639`
- `NETIO!NmrProviderDetachClientComplete` at `0x140015639`

## pseudocode

```c
__int64 __fastcall TdxNsiNotifyDetachClient(__int64 a1)
{
  *(_BYTE *)(a1 + 20) = 1;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 16), 0xFFFFFFFF) == 1 )
    NmrProviderDetachClientComplete(*(HANDLE *)(a1 + 24));
  return 259;
}

```

## disassembly

```asm
0x140015620  sub     rsp, 28h
0x140015624  mov     byte ptr [rcx+14h], 1
0x140015628  or      eax, 0FFFFFFFFh
0x14001562b  lock xadd [rcx+10h], eax
0x140015630  cmp     eax, 1
0x140015633  jnz     short loc_140015645
0x140015635  mov     rcx, [rcx+18h]; NmrBindingHandle
0x140015639  call    cs:__imp_NmrProviderDetachClientComplete
0x140015640  nop     dword ptr [rax+rax+00h]
0x140015645  mov     eax, 103h
0x14001564a  add     rsp, 28h
0x14001564e  retn
```
