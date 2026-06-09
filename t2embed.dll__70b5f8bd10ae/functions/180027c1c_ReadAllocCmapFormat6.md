# ReadAllocCmapFormat6

- ea: `0x180027c1c`
- end: `0x180027d1f`
- name: `ReadAllocCmapFormat6`
- size: `259`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000f298`

## callees

- `0x1800134a0`
- `0x180015190`
- `0x1800164a0`
- `0x1800164e0`
- `0x180017480`
- `0x180027c1c`

## pseudocode

```c
__int64 __fastcall ReadAllocCmapFormat6(__int64 *a1, __int64 a2, __int64 a3, __int64 a4, _WORD *a5, __int64 *a6)
{
  unsigned int CmapSubtable; // ebp
  _WORD *v8; // rdi
  __int64 result; // rax
  __int64 v10; // rax
  __int64 *v11; // rbx
  unsigned __int16 GenericRepeat; // di
  int v13[4]; // [rsp+40h] [rbp-28h] BYREF
  unsigned __int16 v14; // [rsp+78h] [rbp+10h] BYREF

  v14 = 0;
  v13[0] = 0;
  CmapSubtable = FindCmapSubtable(a1, 3, a3, a4);
  if ( !CmapSubtable )
    return 1006;
  v8 = a5;
  result = ReadGeneric(a1, (__int64)a5, 0xAu, (unsigned __int8 *)&CMAP_FORMAT6_CONTROL, CmapSubtable, &v14);
  if ( (_WORD)result )
    return result;
  if ( *v8 != 6 )
    return 1006;
  v10 = Mem_Alloc(2LL * (unsigned __int16)v8[4]);
  v11 = a6;
  *a6 = v10;
  if ( !v10 )
    return 1005;
  GenericRepeat = ReadGenericRepeat(a1, v10, (unsigned __int8 *)WORD_CONTROL, CmapSubtable + v14, v13, v8[4], 2u);
  if ( !GenericRepeat )
    return 0;
  Mem_Free(*v11);
  result = GenericRepeat;
  *v11 = 0;
  return result;
}

```

## disassembly

```asm
0x180027c1c  mov     rax, rsp
0x180027c1f  mov     [rax+8], rbx
0x180027c23  mov     [rax+18h], rbp
0x180027c27  mov     [rax+10h], dx
0x180027c2b  push    rsi
0x180027c2c  push    rdi
0x180027c2d  push    r14
0x180027c2f  sub     rsp, 50h
0x180027c33  xor     r14d, r14d
0x180027c36  mov     rsi, rcx
0x180027c39  mov     [rax+10h], r14w
0x180027c3e  mov     [rax-28h], r14d
0x180027c42  lea     edx, [r14+3]
0x180027c46  call    FindCmapSubtable
0x180027c4b  mov     ebp, eax
0x180027c4d  test    eax, eax
0x180027c4f  jz      loc_180027D05
0x180027c55  mov     rdi, [rsp+68h+arg_20]
0x180027c5d  lea     rax, [rsp+68h+arg_8]
0x180027c62  mov     [rsp+68h+var_40], rax
0x180027c67  lea     r8d, [r14+0Ah]
0x180027c6b  mov     rdx, rdi
0x180027c6e  mov     dword ptr [rsp+68h+var_48], ebp
0x180027c72  lea     r9, CMAP_FORMAT6_CONTROL
0x180027c79  mov     rcx, rsi
0x180027c7c  call    ReadGeneric
0x180027c81  test    ax, ax
0x180027c84  jnz     loc_180027D0A
0x180027c8a  cmp     word ptr [rdi], 6
0x180027c8e  jnz     short loc_180027D05
0x180027c90  movzx   ecx, word ptr [rdi+8]
0x180027c94  add     rcx, rcx; Size
0x180027c97  call    Mem_Alloc
0x180027c9c  mov     rbx, [rsp+68h+arg_28]
0x180027ca4  mov     rdx, rax
0x180027ca7  mov     [rbx], rax
0x180027caa  test    rax, rax
0x180027cad  jnz     short loc_180027CB6
0x180027caf  mov     eax, 3EDh
0x180027cb4  jmp     short loc_180027D0A
0x180027cb6  movzx   eax, word ptr [rdi+8]
0x180027cba  lea     r8, WORD_CONTROL
0x180027cc1  movzx   r9d, [rsp+68h+arg_8]
0x180027cc7  mov     rcx, rsi
0x180027cca  mov     [rsp+68h+var_38], 2
0x180027cd1  add     r9d, ebp
0x180027cd4  mov     word ptr [rsp+68h+var_40], ax
0x180027cd9  lea     rax, [rsp+68h+var_28]
0x180027cde  mov     [rsp+68h+var_48], rax
0x180027ce3  call    ReadGenericRepeat
0x180027ce8  movzx   edi, ax
0x180027ceb  test    ax, ax
0x180027cee  jz      short loc_180027D00
0x180027cf0  mov     rcx, [rbx]
0x180027cf3  call    Mem_Free
0x180027cf8  movzx   eax, di
0x180027cfb  mov     [rbx], r14
0x180027cfe  jmp     short loc_180027D0A
0x180027d00  mov     eax, r14d
0x180027d03  jmp     short loc_180027D0A
0x180027d05  mov     eax, 3EEh
0x180027d0a  lea     r11, [rsp+68h+var_18]
0x180027d0f  mov     rbx, [r11+20h]
0x180027d13  mov     rbp, [r11+30h]
0x180027d17  mov     rsp, r11
0x180027d1a  pop     r14
0x180027d1c  pop     rdi
0x180027d1d  pop     rsi
0x180027d1e  retn
```
