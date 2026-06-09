# _tlgKeywordOn

- ea: `0x140001008`
- end: `0x14000102f`
- name: `_tlgKeywordOn`
- size: `39`
- prototype: ``
- caller_count: `14`
- callee_count: `1`
- tags: ``

## callers

- `0x140007310`
- `0x14001ba40`
- `0x14001be40`
- `0x14001e4a0`
- `0x14001e7e4`
- `0x14001ea54`
- `0x14001ed50`
- `0x14001f2d0`
- `0x1400202cc`
- `0x1400204a4`
- `0x140022920`
- `0x14002a080`
- `0x14002a678`
- `0x14002a804`

## callees

- `0x140001008`

## pseudocode

```c
char tlgKeywordOn()
{
  char v0; // cl

  v0 = 1;
  if ( (qword_140011010 & 1) == 0 || (qword_140011018 & 1) != qword_140011018 )
    return 0;
  return v0;
}

```

## disassembly

```asm
0x140001008  mov     rdx, cs:qword_140011018
0x14000100f  mov     ecx, 1
0x140001014  mov     rax, cs:qword_140011010
0x14000101b  test    cl, al
0x14000101d  jz      short loc_14000102A
0x14000101f  mov     rax, rdx
0x140001022  and     rax, rcx
0x140001025  cmp     rax, rdx
0x140001028  jz      short loc_14000102C
0x14000102a  xor     cl, cl
0x14000102c  mov     al, cl
0x14000102e  retn
```
