# CopyBlockOver

- ea: `0x1800273f4`
- end: `0x180027478`
- name: `CopyBlockOver`
- size: `132`
- prototype: `__int64 __fastcall(int, int, int, int, size_t Size)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800119f8`

## callees

- `0x180012020`
- `0x180017eb0`
- `0x1800273f4`
- `0x18002a55a`

## pseudocode

```c
__int64 __fastcall CopyBlockOver(_QWORD *a1, _QWORD *a2, unsigned int a3, unsigned int a4, size_t Size)
{
  __int64 v6; // rbp
  __int64 v8; // r14
  __int64 result; // rax

  v6 = a3;
  v8 = a4;
  if ( a3 + *a1 == a4 + *a2 || !(_DWORD)Size )
    return 0;
  result = CheckInOffset(a2, a4, (unsigned int)Size);
  if ( !(_WORD)result )
  {
    result = CheckOutOffset(a1, (unsigned int)v6);
    if ( !(_WORD)result )
    {
      memmove_0((void *)(v6 + *a1), (const void *)(v8 + *a2), (unsigned int)Size);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800273f4  push    rbx
0x1800273f6  push    rbp
0x1800273f7  push    rsi
0x1800273f8  push    rdi
0x1800273f9  push    r12
0x1800273fb  push    r14
0x1800273fd  push    r15
0x1800273ff  sub     rsp, 20h
0x180027403  mov     r11, [rcx]
0x180027406  xor     r12d, r12d
0x180027409  mov     r10, [rdx]
0x18002740c  mov     rsi, rdx
0x18002740f  mov     ebp, r8d
0x180027412  mov     rdi, rcx
0x180027415  mov     r14d, r9d
0x180027418  add     r11, rbp
0x18002741b  add     r10, r14
0x18002741e  cmp     r11, r10
0x180027421  jz      short loc_180027466
0x180027423  mov     eax, dword ptr [rsp+58h+Size]
0x18002742a  test    eax, eax
0x18002742c  jz      short loc_180027466
0x18002742e  mov     r8d, eax
0x180027431  mov     edx, r9d
0x180027434  mov     rcx, rsi
0x180027437  mov     ebx, eax
0x180027439  call    CheckInOffset
0x18002743e  test    ax, ax
0x180027441  jnz     short loc_180027469
0x180027443  mov     edx, ebp
0x180027445  mov     rcx, rdi
0x180027448  call    CheckOutOffset
0x18002744d  test    ax, ax
0x180027450  jnz     short loc_180027469
0x180027452  mov     rdx, [rsi]
0x180027455  mov     r8d, ebx; Size
0x180027458  mov     rcx, [rdi]
0x18002745b  add     rdx, r14; Src
0x18002745e  add     rcx, rbp; void *
0x180027461  call    memmove_0
0x180027466  mov     eax, r12d
0x180027469  add     rsp, 20h
0x18002746d  pop     r15
0x18002746f  pop     r14
0x180027471  pop     r12
0x180027473  pop     rdi
0x180027474  pop     rsi
0x180027475  pop     rbp
0x180027476  pop     rbx
0x180027477  retn
```
