# CopyBlock

- ea: `0x18002738c`
- end: `0x1800273ed`
- name: `CopyBlock`
- size: `97`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x18001009c`
- `0x180016770`
- `0x18001dc84`
- `0x180028c2c`

## callees

- `0x180012020`
- `0x180017eb0`
- `0x18002738c`
- `0x18002a55a`

## pseudocode

```c
__int64 __fastcall CopyBlock(_QWORD *a1, unsigned int a2, unsigned int a3, unsigned int a4)
{
  __int64 result; // rax
  __int64 v9; // rcx

  if ( a2 == a3 || !a4 )
    return 0;
  result = CheckInOffset(a1, a3, a4);
  if ( !(_WORD)result )
  {
    result = CheckOutOffset(v9, a2);
    if ( !(_WORD)result )
    {
      memmove_0((void *)(*a1 + a2), (const void *)(*a1 + a3), a4);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002738c  push    rbx
0x18002738e  push    rbp
0x18002738f  push    rsi
0x180027390  push    rdi
0x180027391  push    r14
0x180027393  sub     rsp, 20h
0x180027397  xor     r14d, r14d
0x18002739a  mov     esi, r8d
0x18002739d  mov     ebx, edx
0x18002739f  mov     rdi, rcx
0x1800273a2  cmp     edx, r8d
0x1800273a5  jz      short loc_1800273DF
0x1800273a7  test    r9d, r9d
0x1800273aa  jz      short loc_1800273DF
0x1800273ac  mov     r8d, r9d
0x1800273af  mov     edx, esi
0x1800273b1  mov     ebp, r9d
0x1800273b4  call    CheckInOffset
0x1800273b9  test    ax, ax
0x1800273bc  jnz     short loc_1800273E2
0x1800273be  mov     r8d, ebp
0x1800273c1  mov     edx, ebx
0x1800273c3  call    CheckOutOffset
0x1800273c8  test    ax, ax
0x1800273cb  jnz     short loc_1800273E2
0x1800273cd  mov     edx, esi
0x1800273cf  mov     ecx, ebx
0x1800273d1  add     rdx, [rdi]; Src
0x1800273d4  mov     r8d, ebp; Size
0x1800273d7  add     rcx, [rdi]; void *
0x1800273da  call    memmove_0
0x1800273df  mov     eax, r14d
0x1800273e2  add     rsp, 20h
0x1800273e6  pop     r14
0x1800273e8  pop     rdi
0x1800273e9  pop     rsi
0x1800273ea  pop     rbp
0x1800273eb  pop     rbx
0x1800273ec  retn
```
