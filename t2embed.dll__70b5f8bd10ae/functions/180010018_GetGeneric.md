# GetGeneric

- ea: `0x180010018`
- end: `0x180010094`
- name: `GetGeneric`
- size: `124`
- prototype: ``
- caller_count: `16`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ee80`
- `0x18000f298`
- `0x18000fe8c`
- `0x18000ffc4`
- `0x180010448`
- `0x1800110d0`
- `0x1800119f8`
- `0x18001357c`
- `0x1800190a4`
- `0x18001b538`
- `0x18002089c`
- `0x180020c40`
- `0x180021394`
- `0x180027480`
- `0x180028dfc`
- `0x18002912c`

## callees

- `0x180010018`
- `0x1800134b4`
- `0x180015190`

## pseudocode

```c
__int64 __fastcall GetGeneric(__int64 *a1, __int64 a2, unsigned __int16 a3)
{
  __int64 v5; // rdi
  unsigned int v6; // ebx
  __int16 v8; // [rsp+80h] [rbp+18h] BYREF

  v8 = 0;
  v5 = 3LL * a3;
  v6 = TTTableOffset((__int64)a1, (&off_180031040)[3 * a3]);
  if ( !v6 )
    return 0;
  if ( (unsigned __int16)ReadGeneric(
                           a1,
                           a2,
                           (unsigned __int16)(&off_180031040)[v5 + 1],
                           (unsigned __int8 *)(&off_180031040)[v5 + 2],
                           v6,
                           &v8) )
    return 0;
  return v6;
}

```

## disassembly

```asm
0x180010018  mov     rax, rsp
0x18001001b  push    rbx
0x18001001c  push    rbp
0x18001001d  push    rsi
0x18001001e  push    rdi
0x18001001f  push    r14
0x180010021  push    r15
0x180010023  sub     rsp, 38h
0x180010027  mov     rbp, rdx
0x18001002a  lea     r15, off_180031040; "head"
0x180010031  xor     r14d, r14d
0x180010034  mov     rsi, rcx
0x180010037  mov     [rax+18h], r14w
0x18001003c  movzx   eax, r8w
0x180010040  lea     rdi, [rax+rax*2]
0x180010044  mov     rdx, [r15+rdi*8]
0x180010048  call    TTTableOffset
0x18001004d  mov     ebx, eax
0x18001004f  test    eax, eax
0x180010051  jz      short loc_180010085
0x180010053  mov     r9, [r15+rdi*8+10h]
0x180010058  lea     rax, [rsp+68h+arg_10]
0x180010060  movzx   r8d, word ptr [r15+rdi*8+8]
0x180010066  mov     rdx, rbp
0x180010069  mov     [rsp+68h+var_40], rax
0x18001006e  mov     rcx, rsi
0x180010071  mov     [rsp+68h+var_48], ebx
0x180010075  call    ReadGeneric
0x18001007a  test    ax, ax
0x18001007d  cmovnz  ebx, r14d
0x180010081  mov     eax, ebx
0x180010083  jmp     short loc_180010087
0x180010085  xor     eax, eax
0x180010087  add     rsp, 38h
0x18001008b  pop     r15
0x18001008d  pop     r14
0x18001008f  pop     rdi
0x180010090  pop     rsi
0x180010091  pop     rbp
0x180010092  pop     rbx
0x180010093  retn
```
