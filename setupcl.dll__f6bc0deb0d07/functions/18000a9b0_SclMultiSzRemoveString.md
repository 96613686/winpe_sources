# SclMultiSzRemoveString

- ea: `0x18000a9b0`
- end: `0x18000aa79`
- name: `SclMultiSzRemoveString`
- size: `201`
- prototype: `__int64 __fastcall(unsigned __int64, __int64, _WORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180002cc8`

## callees

- `0x180005938`
- `0x18000a9b0`
- `0x1800179b9`

## pseudocode

```c
__int64 __fastcall SclMultiSzRemoveString(unsigned __int64 a1, __int64 a2, _WORD *a3, _QWORD *a4)
{
  int v7; // ebp
  unsigned __int64 v8; // r11
  unsigned __int64 v9; // rbx
  unsigned __int64 v11; // [rsp+40h] [rbp+8h] BYREF

  v11 = 0;
  if ( !a1 || !a2 || !a3 || (unsigned __int64)a3 < a1 || (unsigned __int64)a3 >= a1 + 2 * a2 || !*a3 )
    return 3221225485LL;
  v7 = RtlStringCchLengthW(a3, a2 - ((__int64)((__int64)a3 - a1) >> 1), &v11);
  if ( v7 < 0 )
  {
    v9 = v8;
    v7 = 0;
  }
  else
  {
    v9 = v11;
    if ( v11 < v8 - 1 )
      v9 = v11 + 1;
  }
  if ( v9 < v8 )
    memmove_0(a3, &a3[v9], 2 * (v8 - v9));
  if ( a4 )
    *a4 = a2 - v9;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000a9b0  mov     [rsp+arg_8], rbx
0x18000a9b5  mov     [rsp+arg_10], rbp
0x18000a9ba  push    rsi
0x18000a9bb  push    rdi
0x18000a9bc  push    r14
0x18000a9be  sub     rsp, 20h
0x18000a9c2  mov     [rsp+38h+arg_0], 0
0x18000a9cb  mov     r14, r9
0x18000a9ce  mov     rdi, r8
0x18000a9d1  mov     rsi, rdx
0x18000a9d4  test    rcx, rcx
0x18000a9d7  jz      loc_18000AA61
0x18000a9dd  test    rdx, rdx
0x18000a9e0  jz      short loc_18000AA61
0x18000a9e2  test    r8, r8
0x18000a9e5  jz      short loc_18000AA61
0x18000a9e7  cmp     r8, rcx
0x18000a9ea  jb      short loc_18000AA61
0x18000a9ec  lea     rax, [rcx+rdx*2]
0x18000a9f0  cmp     r8, rax
0x18000a9f3  jnb     short loc_18000AA61
0x18000a9f5  xor     eax, eax
0x18000a9f7  cmp     ax, [r8]
0x18000a9fb  jz      short loc_18000AA61
0x18000a9fd  mov     r11, rdx
0x18000aa00  mov     rax, r8
0x18000aa03  sub     rax, rcx
0x18000aa06  lea     r8, [rsp+38h+arg_0]
0x18000aa0b  sar     rax, 1
0x18000aa0e  mov     rcx, rdi
0x18000aa11  sub     r11, rax
0x18000aa14  mov     rdx, r11
0x18000aa17  call    RtlStringCchLengthW
0x18000aa1c  mov     ebp, eax
0x18000aa1e  test    eax, eax
0x18000aa20  js      short loc_18000AA35
0x18000aa22  mov     rbx, [rsp+38h+arg_0]
0x18000aa27  lea     rcx, [r11-1]
0x18000aa2b  cmp     rbx, rcx
0x18000aa2e  jnb     short loc_18000AA3A
0x18000aa30  inc     rbx
0x18000aa33  jmp     short loc_18000AA3A
0x18000aa35  mov     rbx, r11
0x18000aa38  xor     ebp, ebp
0x18000aa3a  cmp     rbx, r11
0x18000aa3d  jnb     short loc_18000AA52
0x18000aa3f  sub     r11, rbx
0x18000aa42  lea     rdx, [rdi+rbx*2]; Src
0x18000aa46  mov     rcx, rdi; void *
0x18000aa49  lea     r8, [r11+r11]; Size
0x18000aa4d  call    memmove_0
0x18000aa52  test    r14, r14
0x18000aa55  jz      short loc_18000AA5D
0x18000aa57  sub     rsi, rbx
0x18000aa5a  mov     [r14], rsi
0x18000aa5d  mov     eax, ebp
0x18000aa5f  jmp     short loc_18000AA66
0x18000aa61  mov     eax, 0C000000Dh
0x18000aa66  mov     rbx, [rsp+38h+arg_8]
0x18000aa6b  mov     rbp, [rsp+38h+arg_10]
0x18000aa70  add     rsp, 20h
0x18000aa74  pop     r14
0x18000aa76  pop     rdi
0x18000aa77  pop     rsi
0x18000aa78  retn
```
