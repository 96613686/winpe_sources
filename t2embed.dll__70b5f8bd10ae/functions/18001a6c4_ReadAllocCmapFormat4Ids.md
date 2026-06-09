# ReadAllocCmapFormat4Ids

- ea: `0x18001a6c4`
- end: `0x18001a79c`
- name: `ReadAllocCmapFormat4Ids`
- size: `216`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180016f54`
- `0x180017330`

## callees

- `0x1800134a0`
- `0x1800164a0`
- `0x1800164e0`
- `0x18001a6c4`
- `0x18001a7a4`

## pseudocode

```c
__int64 __fastcall ReadAllocCmapFormat4Ids(
        __int64 *a1,
        unsigned __int16 a2,
        __int64 a3,
        __int64 *a4,
        unsigned __int16 *a5,
        unsigned int a6,
        _DWORD *a7)
{
  unsigned __int16 v9; // r10
  unsigned __int16 v10; // ax
  __int64 result; // rax
  __int64 v12; // rax
  unsigned __int16 GenericRepeat; // di

  v9 = 0;
  *a4 = 0;
  while ( v9 < a2 )
  {
    if ( *(_WORD *)(a3 + 8LL * v9) < *(_WORD *)(a3 + 8LL * v9 + 2) )
      return 1060;
    ++v9;
  }
  v10 = GuessNumCmapGlyphIds(a2, a3);
  *a5 = v10;
  if ( !v10 )
    return 0;
  v12 = Mem_Alloc(2LL * v10);
  *a4 = v12;
  if ( !v12 )
    return 1005;
  GenericRepeat = ReadGenericRepeat(a1, v12, (unsigned __int8 *)WORD_CONTROL, a6, a7, *a5, 2u);
  if ( !GenericRepeat )
    return 0;
  Mem_Free(*a4);
  result = GenericRepeat;
  *a4 = 0;
  return result;
}

```

## disassembly

```asm
0x18001a6c4  push    rbx
0x18001a6c6  push    rbp
0x18001a6c7  push    rsi
0x18001a6c8  push    rdi
0x18001a6c9  sub     rsp, 48h
0x18001a6cd  mov     rbx, r9
0x18001a6d0  xor     ebp, ebp
0x18001a6d2  mov     r9, r8
0x18001a6d5  movzx   r11d, dx
0x18001a6d9  mov     rsi, rcx
0x18001a6dc  mov     r10d, ebp
0x18001a6df  mov     [rbx], rbp
0x18001a6e2  cmp     r10w, r11w
0x18001a6e6  jb      short loc_18001A70F
0x18001a6e8  mov     rdx, r9
0x18001a6eb  movzx   ecx, r11w
0x18001a6ef  call    GuessNumCmapGlyphIds
0x18001a6f4  mov     rdi, [rsp+68h+arg_20]
0x18001a6fc  mov     [rdi], ax
0x18001a6ff  test    ax, ax
0x18001a702  jnz     short loc_18001A72D
0x18001a704  mov     eax, ebp
0x18001a706  add     rsp, 48h
0x18001a70a  pop     rdi
0x18001a70b  pop     rsi
0x18001a70c  pop     rbp
0x18001a70d  pop     rbx
0x18001a70e  retn
0x18001a70f  movzx   r8d, r10w
0x18001a713  movzx   eax, word ptr [r9+r8*8+2]
0x18001a719  cmp     [r9+r8*8], ax
0x18001a71e  jb      short loc_18001A726
0x18001a720  inc     r10w
0x18001a724  jmp     short loc_18001A6E2
0x18001a726  mov     eax, 424h
0x18001a72b  jmp     short loc_18001A706
0x18001a72d  movzx   ecx, ax
0x18001a730  add     rcx, rcx; Size
0x18001a733  call    Mem_Alloc
0x18001a738  mov     [rbx], rax
0x18001a73b  mov     rdx, rax
0x18001a73e  test    rax, rax
0x18001a741  jnz     short loc_18001A74A
0x18001a743  mov     eax, 3EDh
0x18001a748  jmp     short loc_18001A706
0x18001a74a  movzx   eax, word ptr [rdi]
0x18001a74d  lea     r8, WORD_CONTROL
0x18001a754  mov     r9d, [rsp+68h+arg_28]
0x18001a75c  mov     rcx, rsi
0x18001a75f  mov     [rsp+68h+var_38], 2
0x18001a766  mov     [rsp+68h+var_40], ax
0x18001a76b  mov     rax, [rsp+68h+arg_30]
0x18001a773  mov     [rsp+68h+var_48], rax
0x18001a778  call    ReadGenericRepeat
0x18001a77d  movzx   edi, ax
0x18001a780  test    ax, ax
0x18001a783  jz      loc_18001A704
0x18001a789  mov     rcx, [rbx]
0x18001a78c  call    Mem_Free
0x18001a791  movzx   eax, di
0x18001a794  mov     [rbx], rbp
0x18001a797  jmp     loc_18001A706
```
