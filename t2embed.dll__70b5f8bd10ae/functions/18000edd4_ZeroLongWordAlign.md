# ZeroLongWordAlign

- ea: `0x18000edd4`
- end: `0x18000ee2d`
- name: `ZeroLongWordAlign`
- size: `89`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ee80`
- `0x18000fd44`
- `0x18001009c`
- `0x1800119f8`
- `0x180012a18`
- `0x180016770`
- `0x1800275d4`
- `0x180029228`
- `0x180029a94`

## callees

- `0x18000edd4`
- `0x180010618`

## pseudocode

```c
__int64 __fastcall ZeroLongWordAlign(__int64 a1, unsigned int a2, unsigned int *a3)
{
  unsigned int v4; // ebx
  __int64 result; // rax
  unsigned int v7; // ebx
  unsigned __int16 i; // di

  v4 = (a2 + 3) & 0xFFFFFFFC;
  *a3 = v4;
  if ( v4 < a2 )
    return 1002;
  v7 = v4 - a2;
  for ( i = 0; i < v7; ++i )
  {
    result = WriteByte(a1, 0, i + a2);
    if ( (_WORD)result )
      return result;
  }
  return 0;
}

```

## disassembly

```asm
0x18000edd4  push    rbx
0x18000edd6  push    rbp
0x18000edd7  push    rsi
0x18000edd8  push    rdi
0x18000edd9  push    r14
0x18000eddb  sub     rsp, 20h
0x18000eddf  lea     ebx, [rdx+3]
0x18000ede2  mov     esi, edx
0x18000ede4  and     ebx, 0FFFFFFFCh
0x18000ede7  mov     rbp, rcx
0x18000edea  mov     [r8], ebx
0x18000eded  cmp     ebx, edx
0x18000edef  jnb     short loc_18000EDF8
0x18000edf1  mov     eax, 3EAh
0x18000edf6  jmp     short loc_18000EE22
0x18000edf8  sub     ebx, esi
0x18000edfa  xor     r14d, r14d
0x18000edfd  mov     edi, r14d
0x18000ee00  movzx   eax, di
0x18000ee03  cmp     eax, ebx
0x18000ee05  jnb     short loc_18000EE1F
0x18000ee07  lea     r8d, [rax+rsi]
0x18000ee0b  xor     edx, edx
0x18000ee0d  mov     rcx, rbp
0x18000ee10  call    WriteByte
0x18000ee15  test    ax, ax
0x18000ee18  jnz     short loc_18000EE22
0x18000ee1a  inc     di
0x18000ee1d  jmp     short loc_18000EE00
0x18000ee1f  mov     eax, r14d
0x18000ee22  add     rsp, 20h
0x18000ee26  pop     r14
0x18000ee28  pop     rdi
0x18000ee29  pop     rsi
0x18000ee2a  pop     rbp
0x18000ee2b  pop     rbx
0x18000ee2c  retn
```
