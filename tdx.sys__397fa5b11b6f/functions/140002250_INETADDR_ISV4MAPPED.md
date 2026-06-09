# INETADDR_ISV4MAPPED

- ea: `0x140002250`
- end: `0x14000228b`
- name: `INETADDR_ISV4MAPPED`
- size: `59`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140001550`
- `0x140001980`
- `0x140001c5c`
- `0x140001ce0`
- `0x140007b90`
- `0x140018090`

## callees

- `0x140002250`

## pseudocode

```c
bool __fastcall INETADDR_ISV4MAPPED(_WORD *a1)
{
  return *a1 == 23 && !a1[4] && !a1[5] && !a1[6] && !a1[7] && !a1[8] && a1[9] == 0xFFFF;
}

```

## disassembly

```asm
0x140002250  cmp     word ptr [rcx], 17h
0x140002254  jz      short loc_14000225A
0x140002256  xor     al, al
0x140002258  retn
0x14000225a  cmp     word ptr [rcx+8], 0
0x14000225f  jnz     short loc_140002256
0x140002261  cmp     word ptr [rcx+0Ah], 0
0x140002266  jnz     short loc_140002256
0x140002268  cmp     word ptr [rcx+0Ch], 0
0x14000226d  jnz     short loc_140002256
0x14000226f  cmp     word ptr [rcx+0Eh], 0
0x140002274  jnz     short loc_140002256
0x140002276  cmp     word ptr [rcx+10h], 0
0x14000227b  jnz     short loc_140002256
0x14000227d  mov     eax, 0FFFFh
0x140002282  cmp     [rcx+12h], ax
0x140002286  jnz     short loc_140002256
0x140002288  mov     al, 1
0x14000228a  retn
```
