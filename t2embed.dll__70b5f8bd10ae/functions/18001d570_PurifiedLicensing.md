# PurifiedLicensing

- ea: `0x18001d570`
- end: `0x18001d592`
- name: `PurifiedLicensing`
- size: `34`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001862c`
- `0x1800190a4`
- `0x180021394`
- `0x18002173c`
- `0x180021990`

## callees

- `0x18001d570`

## pseudocode

```c
__int16 __fastcall PurifiedLicensing(char a1)
{
  __int16 result; // ax

  if ( (a1 & 0xFE) == 0 )
    return 0;
  result = 8;
  if ( (a1 & 8) == 0 )
    return (a1 & 4) != 0 ? 4 : 2;
  return result;
}

```

## disassembly

```asm
0x18001d570  test    cl, 0FEh
0x18001d573  jnz     short loc_18001D578
0x18001d575  xor     eax, eax
0x18001d577  retn
0x18001d578  mov     eax, 8
0x18001d57d  test    al, cl
0x18001d57f  jnz     short locret_18001D591
0x18001d581  and     cl, 4
0x18001d584  neg     cl
0x18001d586  sbb     ax, ax
0x18001d589  and     ax, 2
0x18001d58d  add     ax, 2
0x18001d591  retn
```
