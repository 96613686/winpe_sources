# TextLogFindSection

- ea: `0x180016d84`
- end: `0x180016dcc`
- name: `TextLogFindSection`
- size: `72`
- prototype: `__int64 __fastcall(__int64, int, __int64, unsigned int *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800027a0`
- `0x1800056d0`
- `0x18000b160`
- `0x1800177e0`

## callees

- `0x18000b890`
- `0x180016d84`

## pseudocode

```c
__int64 __fastcall TextLogFindSection(__int64 a1, int a2, __int64 a3, unsigned int *a4)
{
  unsigned int i; // ebx

  for ( i = 0; (unsigned int)TextLogEnumerateOpenSections(a1, i, a3); ++i )
  {
    if ( *(_DWORD *)(a3 + 4) == a2 )
    {
      *a4 = i;
      return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180016d84  push    rbx
0x180016d86  push    rbp
0x180016d87  push    rsi
0x180016d88  push    rdi
0x180016d89  push    r14
0x180016d8b  sub     rsp, 20h
0x180016d8f  mov     rsi, r9
0x180016d92  mov     rdi, r8
0x180016d95  mov     ebp, edx
0x180016d97  mov     r14, rcx
0x180016d9a  xor     ebx, ebx
0x180016d9c  mov     r8, rdi
0x180016d9f  mov     edx, ebx
0x180016da1  mov     rcx, r14
0x180016da4  call    TextLogEnumerateOpenSections
0x180016da9  test    eax, eax
0x180016dab  jz      short loc_180016DBF
0x180016dad  cmp     [rdi+4], ebp
0x180016db0  jz      short loc_180016DB6
0x180016db2  inc     ebx
0x180016db4  jmp     short loc_180016D9C
0x180016db6  mov     [rsi], ebx
0x180016db8  mov     eax, 1
0x180016dbd  jmp     short loc_180016DC1
0x180016dbf  xor     eax, eax
0x180016dc1  add     rsp, 20h
0x180016dc5  pop     r14
0x180016dc7  pop     rdi
0x180016dc8  pop     rsi
0x180016dc9  pop     rbp
0x180016dca  pop     rbx
0x180016dcb  retn
```
