# WriteGenericRepeat

- ea: `0x180010ae4`
- end: `0x180010b83`
- name: `WriteGenericRepeat`
- size: `159`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x1800110d0`
- `0x1800119f8`
- `0x180012a18`
- `0x180016770`
- `0x180028388`
- `0x180029a94`

## callees

- `0x180010ae4`
- `0x180011640`

## pseudocode

```c
__int16 __fastcall WriteGenericRepeat(
        __int64 a1,
        __int64 a2,
        unsigned __int8 *a3,
        unsigned int a4,
        _DWORD *a5,
        unsigned __int16 a6,
        unsigned __int16 a7)
{
  unsigned __int16 i; // bx
  __int16 result; // ax
  _WORD v13[36]; // [rsp+30h] [rbp-48h] BYREF

  v13[0] = 0;
  for ( i = 0; i < a6; ++i )
  {
    result = WriteGeneric(a1, a2, a7, a3, a4, v13);
    if ( result )
      return result;
    a4 += v13[0];
    a2 += a7;
  }
  *a5 = a7 * a6;
  return 0;
}

```

## disassembly

```asm
0x180010ae4  push    rbx
0x180010ae6  push    rbp
0x180010ae7  push    rsi
0x180010ae8  push    r12
0x180010aea  push    r14
0x180010aec  push    r15
0x180010aee  sub     rsp, 48h
0x180010af2  xor     r12d, r12d
0x180010af5  mov     esi, r9d
0x180010af8  mov     [rsp+78h+var_48], r12w
0x180010afe  mov     ebx, r12d
0x180010b01  mov     r14, r8
0x180010b04  mov     rbp, rdx
0x180010b07  mov     r15, rcx
0x180010b0a  cmp     bx, [rsp+78h+arg_28]
0x180010b12  jnb     short loc_180010B55
0x180010b14  movzx   r8d, [rsp+78h+arg_30]
0x180010b1d  lea     rax, [rsp+78h+var_48]
0x180010b22  mov     [rsp+78h+var_50], rax
0x180010b27  mov     r9, r14
0x180010b2a  mov     rdx, rbp
0x180010b2d  mov     [rsp+78h+var_58], esi
0x180010b31  mov     rcx, r15
0x180010b34  call    WriteGeneric
0x180010b39  test    ax, ax
0x180010b3c  jnz     short loc_180010B75
0x180010b3e  movzx   eax, [rsp+78h+var_48]
0x180010b43  add     esi, eax
0x180010b45  movzx   eax, [rsp+78h+arg_30]
0x180010b4d  add     rbp, rax
0x180010b50  inc     bx
0x180010b53  jmp     short loc_180010B0A
0x180010b55  movzx   eax, [rsp+78h+arg_30]
0x180010b5d  movzx   ecx, [rsp+78h+arg_28]
0x180010b65  imul    ecx, eax
0x180010b68  mov     rax, [rsp+78h+arg_20]
0x180010b70  mov     [rax], ecx
0x180010b72  mov     eax, r12d
0x180010b75  add     rsp, 48h
0x180010b79  pop     r15
0x180010b7b  pop     r14
0x180010b7d  pop     r12
0x180010b7f  pop     rsi
0x180010b80  pop     rbp
0x180010b81  pop     rbx
0x180010b82  retn
```
