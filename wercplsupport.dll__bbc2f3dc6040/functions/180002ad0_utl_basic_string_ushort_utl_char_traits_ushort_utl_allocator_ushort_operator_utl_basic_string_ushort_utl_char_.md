# utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::operator=(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&)

- ea: `0x180002ad0`
- end: `0x180002b71`
- name: `??4?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAAAEAV01@$$QEAV01@@Z`
- size: `161`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180004970`
- `0x180004d28`
- `0x180005c28`

## callees

- `0x180001680`
- `0x180002ad0`
- `0x1800121b0`

## pseudocode

```c
__int64 __fastcall utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::operator=(
        __int64 a1,
        __int64 a2)
{
  _OWORD *v2; // rbp
  _OWORD *v3; // rsi
  __int128 v4; // xmm6
  __int64 v5; // rbx
  _OWORD *v6; // r15
  __int64 result; // rax

  v2 = *(_OWORD **)a2;
  v3 = (_OWORD *)(a2 + 16);
  v4 = *(_OWORD *)(a2 + 16);
  v5 = *(_QWORD *)(a2 + 8);
  v6 = (_OWORD *)(a1 + 16);
  *(_QWORD *)a2 = a2 + 16;
  *(_WORD *)(a2 + 16) = 0;
  *(_QWORD *)(a2 + 8) = a2 + 16;
  if ( *(_QWORD *)a1 != a1 + 16 )
    operator delete(*(void **)a1);
  if ( v2 == v3 )
  {
    v2 = v6;
    v5 = a1 + 2 * (((v5 - a2 - 16) >> 1) + 8);
  }
  *(_QWORD *)a1 = v2;
  result = a1;
  *(_QWORD *)(a1 + 8) = v5;
  *v6 = v4;
  return result;
}

```

## disassembly

```asm
0x180002ad0  push    rbx
0x180002ad2  push    rbp
0x180002ad3  push    rsi
0x180002ad4  push    rdi
0x180002ad5  push    r14
0x180002ad7  push    r15
0x180002ad9  sub     rsp, 48h
0x180002add  movaps  [rsp+78h+var_48], xmm6
0x180002ae2  mov     rax, cs:__security_cookie
0x180002ae9  xor     rax, rsp
0x180002aec  mov     [rsp+78h+var_58], rax
0x180002af1  mov     rbp, [rdx]
0x180002af4  lea     rsi, [rdx+10h]
0x180002af8  movups  xmm6, xmmword ptr [rsi]
0x180002afb  mov     rbx, [rdx+8]
0x180002aff  lea     r15, [rcx+10h]
0x180002b03  xor     eax, eax
0x180002b05  mov     [rdx], rsi
0x180002b08  mov     [rsi], ax
0x180002b0b  mov     r14, rdx
0x180002b0e  mov     [rdx+8], rsi
0x180002b12  mov     rdi, rcx
0x180002b15  cmp     [rcx], r15
0x180002b18  jz      short loc_180002B29
0x180002b1a  mov     rcx, [rcx]; Block
0x180002b1d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180002b24  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180002b29  cmp     rbp, rsi
0x180002b2c  jnz     short loc_180002B43
0x180002b2e  sub     rbx, r14
0x180002b31  mov     rbp, r15
0x180002b34  sub     rbx, 10h
0x180002b38  sar     rbx, 1
0x180002b3b  add     rbx, 8
0x180002b3f  lea     rbx, [rdi+rbx*2]
0x180002b43  mov     [rdi], rbp
0x180002b46  mov     rax, rdi
0x180002b49  mov     [rdi+8], rbx
0x180002b4d  movdqu  xmmword ptr [r15], xmm6
0x180002b52  mov     rcx, [rsp+78h+var_58]
0x180002b57  xor     rcx, rsp; StackCookie
0x180002b5a  call    __security_check_cookie
0x180002b5f  movaps  xmm6, [rsp+78h+var_48]
0x180002b64  add     rsp, 48h
0x180002b68  pop     r15
0x180002b6a  pop     r14
0x180002b6c  pop     rdi
0x180002b6d  pop     rsi
0x180002b6e  pop     rbp
0x180002b6f  pop     rbx
0x180002b70  retn
```
