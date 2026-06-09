# WriteOutFormat12CmapData

- ea: `0x180027ea8`
- end: `0x180027f5d`
- name: `WriteOutFormat12CmapData`
- size: `181`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001d5f8`

## callees

- `0x180011640`
- `0x180027ea8`

## pseudocode

```c
__int16 __fastcall WriteOutFormat12CmapData(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5,
        _DWORD *a6)
{
  __int16 result; // ax
  unsigned int v10; // edi
  unsigned int v11; // ebx
  _WORD v12[36]; // [rsp+30h] [rbp-48h] BYREF

  v12[0] = 0;
  result = WriteGeneric(a1, a2, 0x10u, (unsigned __int8 *)&CMAP_FORMAT12_CONTROL, a5, v12);
  if ( !result )
  {
    v10 = 0;
    v11 = a5 + v12[0];
    while ( v10 < a4 )
    {
      result = WriteGeneric(a1, a3 + 12LL * v10, 0xCu, (unsigned __int8 *)&FORMAT12_GROUPS_CONTROL, v11, v12);
      if ( result )
        return result;
      v11 += v12[0];
      ++v10;
    }
    *a6 = v11 - a5;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180027ea8  push    rbx
0x180027eaa  push    rbp
0x180027eab  push    rsi
0x180027eac  push    rdi
0x180027ead  push    r12
0x180027eaf  push    r14
0x180027eb1  push    r15
0x180027eb3  sub     rsp, 40h
0x180027eb7  mov     esi, [rsp+78h+arg_20]
0x180027ebe  lea     rax, [rsp+78h+var_48]
0x180027ec3  xor     r12d, r12d
0x180027ec6  mov     [rsp+78h+var_50], rax
0x180027ecb  mov     ebp, r9d
0x180027ece  mov     [rsp+78h+var_48], r12w
0x180027ed4  mov     r15, r8
0x180027ed7  mov     [rsp+78h+var_58], esi
0x180027edb  lea     r9, CMAP_FORMAT12_CONTROL
0x180027ee2  mov     r14, rcx
0x180027ee5  lea     r8d, [r12+10h]
0x180027eea  call    WriteGeneric
0x180027eef  test    ax, ax
0x180027ef2  jnz     short loc_180027F4E
0x180027ef4  movzx   ebx, [rsp+78h+var_48]
0x180027ef9  mov     edi, r12d
0x180027efc  add     ebx, esi
0x180027efe  cmp     edi, ebp
0x180027f00  jnb     short loc_180027F3F
0x180027f02  mov     eax, edi
0x180027f04  lea     r9, FORMAT12_GROUPS_CONTROL
0x180027f0b  mov     r8d, 0Ch
0x180027f11  lea     rcx, [rax+rax*2]
0x180027f15  lea     rax, [rsp+78h+var_48]
0x180027f1a  lea     rdx, [r15+rcx*4]
0x180027f1e  mov     [rsp+78h+var_50], rax
0x180027f23  mov     rcx, r14
0x180027f26  mov     [rsp+78h+var_58], ebx
0x180027f2a  call    WriteGeneric
0x180027f2f  test    ax, ax
0x180027f32  jnz     short loc_180027F4E
0x180027f34  movzx   eax, [rsp+78h+var_48]
0x180027f39  add     ebx, eax
0x180027f3b  inc     edi
0x180027f3d  jmp     short loc_180027EFE
0x180027f3f  mov     rax, [rsp+78h+arg_28]
0x180027f47  sub     ebx, esi
0x180027f49  mov     [rax], ebx
0x180027f4b  mov     eax, r12d
0x180027f4e  add     rsp, 40h
0x180027f52  pop     r15
0x180027f54  pop     r14
0x180027f56  pop     r12
0x180027f58  pop     rdi
0x180027f59  pop     rsi
0x180027f5a  pop     rbp
0x180027f5b  pop     rbx
0x180027f5c  retn
```
