# SmpPagefileUsageSampleCompare

- ea: `0x14000b3f0`
- end: `0x14000b3ff`
- name: `SmpPagefileUsageSampleCompare`
- size: `15`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000b3f0`

## pseudocode

```c
__int64 __fastcall SmpPagefileUsageSampleCompare(_DWORD *a1, _DWORD *a2)
{
  if ( *a1 <= *a2 )
    return (unsigned int)-(*a1 < *a2);
  else
    return 1;
}

```

## disassembly

```asm
0x14000b3f0  mov     eax, [rdx]
0x14000b3f2  cmp     [rcx], eax
0x14000b3f4  jbe     short loc_14000B3FC
0x14000b3f6  mov     eax, 1
0x14000b3fb  retn
0x14000b3fc  sbb     eax, eax
0x14000b3fe  retn
```
