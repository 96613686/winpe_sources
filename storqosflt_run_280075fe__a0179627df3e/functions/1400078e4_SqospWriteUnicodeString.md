# SqospWriteUnicodeString

- ea: `0x1400078e4`
- end: `0x140007931`
- name: `SqospWriteUnicodeString`
- size: `77`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140007938`

## callees

- `0x1400078e4`
- `0x140008f40`

## pseudocode

```c
__int64 __fastcall SqospWriteUnicodeString(__int64 a1, unsigned int a2, _DWORD *a3, const void **a4)
{
  __int64 v4; // rdi
  size_t v6; // r8
  __int64 result; // rax

  v4 = (unsigned int)*a3;
  v6 = *(unsigned __int16 *)a4;
  if ( (int)v4 + (int)v6 > a2 )
    return 0;
  memmove((void *)(v4 + a1), a4[1], v6);
  result = *(unsigned __int16 *)a4;
  *a3 = result + v4;
  return result;
}

```

## disassembly

```asm
0x1400078e4  mov     [rsp+arg_0], rbx
0x1400078e9  mov     [rsp+arg_8], rsi
0x1400078ee  push    rdi
0x1400078ef  sub     rsp, 20h
0x1400078f3  mov     edi, [r8]
0x1400078f6  mov     rsi, r8
0x1400078f9  movzx   r8d, word ptr [r9]; Size
0x1400078fd  mov     rbx, r9
0x140007900  lea     eax, [rdi+r8]
0x140007904  cmp     eax, edx
0x140007906  jbe     short loc_14000790C
0x140007908  xor     eax, eax
0x14000790a  jmp     short loc_140007920
0x14000790c  mov     rdx, [r9+8]; Src
0x140007910  add     rcx, rdi; void *
0x140007913  call    memmove
0x140007918  movzx   eax, word ptr [rbx]
0x14000791b  lea     ecx, [rax+rdi]
0x14000791e  mov     [rsi], ecx
0x140007920  mov     rbx, [rsp+28h+arg_0]
0x140007925  mov     rsi, [rsp+28h+arg_8]
0x14000792a  add     rsp, 20h
0x14000792e  pop     rdi
0x14000792f  retn
```
