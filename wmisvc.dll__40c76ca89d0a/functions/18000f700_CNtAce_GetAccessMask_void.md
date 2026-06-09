# CNtAce::GetAccessMask(void)

- ea: `0x18000f700`
- end: `0x18000f706`
- name: `?GetAccessMask@CNtAce@@UEAAKXZ_0`
- size: `6`
- prototype: `unsigned int __fastcall(CNtAce *this)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `wbemcomn!?GetAccessMask@CNtAce@@UEAAKXZ` at `0x18000f700`

## pseudocode

```c
// attributes: thunk
unsigned int __fastcall CNtAce::GetAccessMask(CNtAce *this)
{
  return __imp_?GetAccessMask@CNtAce@@UEAAKXZ(this);
}

```

## disassembly

```asm
0x18000f700  jmp     cs:__imp_?GetAccessMask@CNtAce@@UEAAKXZ
```
