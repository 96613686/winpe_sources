# writeQuantizer

- ea: `0x1800028f4`
- end: `0x18000299e`
- name: `writeQuantizer`
- size: `170`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002214`
- `0x180032cb4`
- `0x180042878`
- `0x180042a84`

## callees

- `0x1800028f4`
- `0x180003830`

## pseudocode

```c
__int64 __fastcall writeQuantizer(_QWORD *a1, __int64 a2, char a3, unsigned __int64 a4, __int64 a5)
{
  char v7; // r11
  __int64 result; // rax
  __int64 v10; // r8
  char v11; // r11
  unsigned __int64 i; // r11
  __int64 v13; // r11

  v7 = 2;
  if ( (unsigned __int8)a3 <= 2u )
    v7 = a3;
  if ( a4 > 1 )
    putBit16z(a2, v7 & 3, 2);
  result = putBit16z(a2, *(unsigned __int8 *)(*a1 + 20 * a5), 8);
  if ( v11 == 1 )
    return putBit16z(a2, *(unsigned __int8 *)(a1[1] + 20 * a5), v10);
  if ( v11 )
  {
    for ( i = 1; i < a4; i = v13 + 1 )
      result = putBit16z(a2, *(unsigned __int8 *)(a1[i] + 20 * a5), v10);
  }
  return result;
}

```

## disassembly

```asm
0x1800028f4  push    rbx
0x1800028f6  push    rbp
0x1800028f7  push    rsi
0x1800028f8  push    rdi
0x1800028f9  sub     rsp, 28h
0x1800028fd  mov     rsi, rcx
0x180002900  movzx   eax, r8b
0x180002904  mov     ecx, 2
0x180002909  mov     rbp, r9
0x18000290c  cmp     r8b, cl
0x18000290f  mov     r11d, ecx
0x180002912  mov     rbx, rdx
0x180002915  cmovbe  r11d, eax
0x180002919  cmp     r9, 1
0x18000291d  jbe     short loc_180002933
0x18000291f  movzx   edx, r11b
0x180002923  mov     r8d, ecx
0x180002926  and     edx, 3
0x180002929  mov     rcx, rbx
0x18000292c  call    putBit16z
0x180002931  jmp     short loc_180002936
0x180002933  xor     r11b, r11b
0x180002936  mov     rax, [rsp+48h+arg_20]
0x18000293b  mov     r8d, 8
0x180002941  mov     rcx, rbx
0x180002944  lea     rdi, [rax+rax*4]
0x180002948  mov     rax, [rsi]
0x18000294b  movzx   edx, byte ptr [rax+rdi*4]
0x18000294f  call    putBit16z
0x180002954  cmp     r11b, 1
0x180002958  jnz     short loc_18000296C
0x18000295a  mov     rax, [rsi+8]
0x18000295e  mov     rcx, rbx
0x180002961  movzx   edx, byte ptr [rax+rdi*4]
0x180002965  call    putBit16z
0x18000296a  jmp     short loc_180002994
0x18000296c  test    r11b, r11b
0x18000296f  jz      short loc_180002994
0x180002971  mov     r11d, 1
0x180002977  cmp     rbp, r11
0x18000297a  jbe     short loc_180002994
0x18000297c  mov     rax, [rsi+r11*8]
0x180002980  mov     rcx, rbx
0x180002983  movzx   edx, byte ptr [rax+rdi*4]
0x180002987  call    putBit16z
0x18000298c  inc     r11
0x18000298f  cmp     r11, rbp
0x180002992  jb      short loc_18000297C
0x180002994  add     rsp, 28h
0x180002998  pop     rdi
0x180002999  pop     rsi
0x18000299a  pop     rbp
0x18000299b  pop     rbx
0x18000299c  retn
```
