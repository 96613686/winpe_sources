# T2OSSvcCreateDeltaTTF

- ea: `0x180022ba4`
- end: `0x180022c76`
- name: `T2OSSvcCreateDeltaTTF`
- size: `210`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18002089c`
- `0x180020c40`

## callees

- `0x180019dc0`
- `0x180022ba4`
- `0x1800285cc`

## pseudocode

```c
__int64 __fastcall T2OSSvcCreateDeltaTTF(
        __int64 a1,
        unsigned int a2,
        LPVOID *a3,
        unsigned int *a4,
        unsigned __int16 a5,
        int a6,
        unsigned __int16 a7,
        unsigned __int16 a8,
        __int64 a9,
        __int16 a10)
{
  unsigned int v11; // ebx
  int v13; // [rsp+28h] [rbp-70h]
  int v14; // [rsp+38h] [rbp-60h]

  a6 = 0;
  v11 = 0;
  if ( (unsigned __int16)CreateDeltaTTFEx(a1, a2, a3, &a6, a4, v13, a5, v14, a7, a8, a9, a10) )
  {
    if ( *a3 )
    {
      T2free(*a3);
      *a3 = 0;
    }
    return 262;
  }
  return v11;
}

```

## disassembly

```asm
0x180022ba4  mov     r11, rsp
0x180022ba7  mov     [r11+8], rbx
0x180022bab  mov     [r11+10h], rsi
0x180022baf  mov     [r11+18h], r8
0x180022bb3  push    rdi
0x180022bb4  sub     rsp, 90h
0x180022bbb  mov     rdi, r8
0x180022bbe  xor     esi, esi
0x180022bc0  mov     [r11+30h], esi
0x180022bc4  mov     ebx, esi
0x180022bc6  movzx   eax, [rsp+98h+arg_48]
0x180022bce  mov     [rsp+98h+var_40], ax
0x180022bd3  mov     rax, [rsp+98h+arg_40]
0x180022bdb  mov     [r11-48h], rax
0x180022bdf  movzx   eax, [rsp+98h+arg_38]
0x180022be7  mov     [rsp+98h+var_50], ax
0x180022bec  movzx   eax, [rsp+98h+arg_30]
0x180022bf4  mov     [rsp+98h+var_58], ax
0x180022bf9  movzx   eax, [rsp+98h+arg_20]
0x180022c01  mov     [rsp+98h+var_68], ax
0x180022c06  mov     [r11-78h], r9
0x180022c0a  lea     r9, [r11+30h]
0x180022c0e  call    CreateDeltaTTFEx
0x180022c13  test    ax, ax
0x180022c16  jz      short loc_180022C34
0x180022c18  mov     rcx, [rdi]; lpMem
0x180022c1b  test    rcx, rcx
0x180022c1e  jz      short loc_180022C28
0x180022c20  call    T2free
0x180022c25  mov     [rdi], rsi
0x180022c28  mov     ebx, 106h
0x180022c2d  mov     [rsp+98h+var_18], ebx
0x180022c34  jmp     short loc_180022C5F
0x180022c36  mov     rbx, [rsp+98h+arg_10]
0x180022c3e  cmp     qword ptr [rbx], 0
0x180022c42  jz      short loc_180022C53
0x180022c44  mov     rcx, [rbx]; lpMem
0x180022c47  call    T2free
0x180022c4c  mov     qword ptr [rbx], 0
0x180022c53  mov     ebx, 119h
0x180022c58  mov     [rsp+98h+var_18], ebx
0x180022c5f  mov     eax, ebx
0x180022c61  lea     r11, [rsp+98h+var_8]
0x180022c69  mov     rbx, [r11+10h]
0x180022c6d  mov     rsi, [r11+18h]
0x180022c71  mov     rsp, r11
0x180022c74  pop     rdi
0x180022c75  retn
```
