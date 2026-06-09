# AscendingTagCompare

- ea: `0x18001bde0`
- end: `0x18001bdf1`
- name: `AscendingTagCompare`
- size: `17`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001bde0`

## pseudocode

```c
__int64 __fastcall AscendingTagCompare(_DWORD *a1, _DWORD *a2)
{
  if ( *a1 == *a2 )
    return 0;
  else
    return *a1 < *a2 ? -1 : 1;
}

```

## disassembly

```asm
0x18001bde0  mov     eax, [rcx]
0x18001bde2  cmp     eax, [rdx]
0x18001bde4  jnz     short loc_18001BDE9
0x18001bde6  xor     eax, eax
0x18001bde8  retn
0x18001bde9  sbb     eax, eax
0x18001bdeb  and     eax, 0FFFFFFFEh
0x18001bdee  inc     eax
0x18001bdf0  retn
```
