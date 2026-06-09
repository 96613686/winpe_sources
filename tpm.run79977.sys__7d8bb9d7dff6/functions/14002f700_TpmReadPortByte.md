# TpmReadPortByte

- ea: `0x14002f700`
- end: `0x14002f74d`
- name: `TpmReadPortByte`
- size: `77`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140001620`
- `0x140001a30`
- `0x1400052b0`
- `0x140024df0`
- `0x140025020`

## callees

- `0x14002f700`

## pseudocode

```c
unsigned __int8 __fastcall TpmReadPortByte(unsigned __int16 a1, int a2)
{
  unsigned __int16 v4; // dx
  int i; // ecx
  unsigned __int8 v6; // al

  if ( !a2 )
    return -96;
  __outbyte(a1 + 4, a2);
  __outbyte(a1 + 8, BYTE1(a2));
  v4 = a1 + 12;
  __outbyte(a1 + 12, 1u);
  for ( i = 0; i < 2000; ++i )
  {
    v6 = __inbyte(v4);
    if ( (v6 & 2) != 0 )
      return __inbyte(a1);
  }
  return 0;
}

```

## disassembly

```asm
0x14002f700  mov     r8d, edx
0x14002f703  mov     r9, rcx
0x14002f706  test    edx, edx
0x14002f708  jnz     short loc_14002F70E
0x14002f70a  mov     al, 0A0h
0x14002f70c  retn
0x14002f70e  nop
0x14002f70f  lea     edx, [rcx+4]
0x14002f712  mov     al, r8b
0x14002f715  shr     r8d, 8
0x14002f719  out     dx, al
0x14002f71a  nop
0x14002f71b  lea     edx, [rcx+8]
0x14002f71e  nop
0x14002f71f  mov     al, r8b
0x14002f722  out     dx, al
0x14002f723  nop
0x14002f724  lea     edx, [rcx+0Ch]
0x14002f727  nop
0x14002f728  mov     al, 1
0x14002f72a  out     dx, al
0x14002f72b  nop
0x14002f72c  xor     ecx, ecx
0x14002f72e  cmp     ecx, 7D0h
0x14002f734  jge     short loc_14002F74A
0x14002f736  nop
0x14002f737  in      al, dx
0x14002f738  nop
0x14002f739  test    al, 2
0x14002f73b  jnz     short loc_14002F741
0x14002f73d  inc     ecx
0x14002f73f  jmp     short loc_14002F72E
0x14002f741  nop
0x14002f742  movzx   edx, r9w
0x14002f746  in      al, dx
0x14002f747  nop
0x14002f748  retn
0x14002f74a  xor     al, al
0x14002f74c  retn
```
