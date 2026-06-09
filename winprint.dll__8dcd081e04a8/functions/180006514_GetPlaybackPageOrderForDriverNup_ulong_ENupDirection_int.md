# GetPlaybackPageOrderForDriverNup(ulong,_ENupDirection,int)

- ea: `0x180006514`
- end: `0x18000654d`
- name: `?GetPlaybackPageOrderForDriverNup@@YAPEAKKW4_ENupDirection@@H@Z`
- size: `57`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800065e8`
- `0x180006770`

## callees

- `0x180006514`

## pseudocode

```c
__int64 *__fastcall GetPlaybackPageOrderForDriverNup(int a1, unsigned int a2, int a3)
{
  unsigned int v3; // r9d

  v3 = a2;
  if ( a3 == 2 && ((a1 - 2) & 0xFFFFFFFB) == 0 )
    v3 = a2 + 4;
  return &qword_180009970[8 * (v3 + 8LL * *((unsigned int *)qword_18000A370 + (unsigned int)(a1 - 1)))];
}

```

## disassembly

```asm
0x180006514  mov     r9d, edx
0x180006517  cmp     r8d, 2
0x18000651b  jnz     short loc_18000652B
0x18000651d  lea     eax, [rcx-2]
0x180006520  test    eax, 0FFFFFFFBh
0x180006525  jnz     short loc_18000652B
0x180006527  add     r9d, 4
0x18000652b  dec     ecx
0x18000652d  lea     rax, qword_18000A370
0x180006534  mov     edx, [rax+rcx*4]
0x180006537  lea     rcx, qword_180009970
0x18000653e  mov     eax, r9d
0x180006541  lea     rax, [rax+rdx*8]
0x180006545  shl     rax, 6
0x180006549  add     rax, rcx
0x18000654c  retn
```
