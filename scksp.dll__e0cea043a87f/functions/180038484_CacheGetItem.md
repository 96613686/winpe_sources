# CacheGetItem

- ea: `0x180038484`
- end: `0x180038524`
- name: `CacheGetItem`
- size: `160`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180037120`
- `0x180037730`
- `0x180037a4c`

## callees

- `0x180038484`
- `0x18003852c`
- `0x1800385f0`
- `0x18003c1f6`
- `0x18003c240`

## pseudocode

```c
unsigned int __fastcall CacheGetItem(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int v6; // eax
  int v7; // edx
  __int64 i; // rbx
  UCHAR Buf2[32]; // [rsp+20h] [rbp-38h] BYREF

  v6 = I_CacheHashKeys(a2, a2, Buf2);
  if ( v6 )
    return errcntrctlib::WIN32_FROM_NTSTATUS((errcntrctlib *)v6, v7);
  for ( i = *(_QWORD *)(a1 + 8LL * (Buf2[0] & 0xF)); ; i = *(_QWORD *)(i + 16) )
  {
    if ( !i )
      return 1168;
    if ( !memcmp_0((const void *)(i + 24), Buf2, 0x20u) )
      break;
  }
  if ( !*(_QWORD *)(i + 8) || !*(_DWORD *)i )
    return 1168;
  *(_DWORD *)a4 = *(_DWORD *)i;
  *(_QWORD *)(a4 + 8) = *(_QWORD *)(i + 8);
  return 0;
}

```

## disassembly

```asm
0x180038484  mov     [rsp+arg_0], rbx
0x180038489  push    rdi
0x18003848a  sub     rsp, 50h
0x18003848e  mov     rax, cs:__security_cookie
0x180038495  xor     rax, rsp
0x180038498  mov     [rsp+58h+var_18], rax
0x18003849d  mov     rbx, rcx
0x1800384a0  lea     r8, [rsp+58h+Buf2]
0x1800384a5  mov     rcx, rdx
0x1800384a8  mov     rdi, r9
0x1800384ab  call    I_CacheHashKeys
0x1800384b0  test    eax, eax
0x1800384b2  jz      short loc_1800384BD
0x1800384b4  mov     ecx, eax; this
0x1800384b6  call    ?WIN32_FROM_NTSTATUS@errcntrctlib@@YAKJ@Z; errcntrctlib::WIN32_FROM_NTSTATUS(long)
0x1800384bb  jmp     short loc_1800384F1
0x1800384bd  movzx   eax, [rsp+58h+Buf2]
0x1800384c2  and     eax, 0Fh
0x1800384c5  mov     rbx, [rbx+rax*8]
0x1800384c9  jmp     short loc_1800384E7
0x1800384cb  lea     rcx, [rbx+18h]; Buf1
0x1800384cf  mov     r8d, 20h ; ' '; Size
0x1800384d5  lea     rdx, [rsp+58h+Buf2]; Buf2
0x1800384da  call    memcmp_0
0x1800384df  test    eax, eax
0x1800384e1  jz      short loc_180038509
0x1800384e3  mov     rbx, [rbx+10h]
0x1800384e7  test    rbx, rbx
0x1800384ea  jnz     short loc_1800384CB
0x1800384ec  mov     eax, 490h
0x1800384f1  mov     rcx, [rsp+58h+var_18]
0x1800384f6  xor     rcx, rsp; StackCookie
0x1800384f9  call    __security_check_cookie
0x1800384fe  mov     rbx, [rsp+58h+arg_0]
0x180038503  add     rsp, 50h
0x180038507  pop     rdi
0x180038508  retn
0x180038509  cmp     qword ptr [rbx+8], 0
0x18003850e  jz      short loc_1800384EC
0x180038510  mov     eax, [rbx]
0x180038512  test    eax, eax
0x180038514  jz      short loc_1800384EC
0x180038516  mov     [rdi], eax
0x180038518  mov     rax, [rbx+8]
0x18003851c  mov     [rdi+8], rax
0x180038520  xor     eax, eax
0x180038522  jmp     short loc_1800384F1
```
