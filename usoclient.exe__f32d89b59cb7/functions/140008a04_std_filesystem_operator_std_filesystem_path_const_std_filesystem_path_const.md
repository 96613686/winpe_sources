# std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)

- ea: `0x140008a04`
- end: `0x140008ba5`
- name: `??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z`
- size: `417`
- prototype: `std::filesystem::path *__fastcall(std::filesystem::path *Src, struct std::filesystem::path *, std::filesystem *this)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x140009390`
- `0x1400095d8`
- `0x14000966c`
- `0x14000a678`

## callees

- `0x14000760c`
- `0x1400084c4`
- `0x140008a04`
- `0x140008c48`
- `0x14000ac54`

## pseudocode

```c
std::filesystem::path *__fastcall std::filesystem::operator/(
        std::filesystem::path *Src,
        struct std::filesystem::path *a2,
        std::filesystem *this)
{
  __int64 v6; // rdx
  std::filesystem *v7; // r15
  size_t v8; // r13
  __int64 v9; // rcx
  unsigned __int8 v10; // r12
  size_t v11; // r14
  unsigned __int64 v12; // rdi
  std::filesystem::path *v13; // rbp
  _WORD *v14; // rcx
  std::filesystem::path *v15; // rcx

  v6 = *((_QWORD *)this + 2);
  if ( *((_QWORD *)this + 3) <= 7u )
    v7 = this;
  else
    v7 = *(std::filesystem **)this;
  if ( !v6
    || (v8 = 2 * v6, 2 * v6 >= 4) && (*(_DWORD *)v7 & 0xFFFFFFDF) - 3801153 < 0x1A
    || *(_WORD *)v7 == 92
    || *(_WORD *)v7 == 47 )
  {
    std::filesystem::path::path(Src, a2);
    std::filesystem::path::operator/=(Src, this);
    return Src;
  }
  v9 = *((_QWORD *)a2 + 2);
  if ( *((_QWORD *)a2 + 3) > 7u )
    a2 = *(struct std::filesystem::path **)a2;
  if ( v9 == 2 )
  {
    if ( (*(_DWORD *)a2 & 0xFFFFFFDF) - 3801153 < 0x1A )
      goto LABEL_13;
  }
  else if ( !v9 )
  {
    goto LABEL_13;
  }
  v11 = 2 * v9;
  if ( *((_WORD *)a2 + v9 - 1) != 92 && *(_WORD *)((char *)a2 + v11 - 2) != 47 )
  {
    v10 = 1;
    goto LABEL_14;
  }
LABEL_13:
  v10 = 0;
  v11 = 2 * v9;
LABEL_14:
  v12 = v6 + v9 + v10;
  *(_OWORD *)Src = 0;
  *((_QWORD *)Src + 2) = 0;
  *((_QWORD *)Src + 3) = 7;
  *(_WORD *)Src = 0;
  if ( v12 <= 7 )
    *((_QWORD *)Src + 2) = v12;
  else
    std::wstring::_Reallocate_grow_by<_lambda_3c42e42a79350c8a48dd4e272c8dbcce_,>(Src);
  if ( *((_QWORD *)Src + 3) <= 7u )
    v13 = Src;
  else
    v13 = *(std::filesystem::path **)Src;
  memcpy_0(v13, a2, v11);
  v14 = (_WORD *)((char *)v13 + v11);
  if ( v10 )
    *v14++ = 92;
  memcpy_0(v14, v7, v8);
  *((_QWORD *)Src + 2) = v12;
  if ( *((_QWORD *)Src + 3) <= 7u )
    v15 = Src;
  else
    v15 = *(std::filesystem::path **)Src;
  *((_WORD *)v15 + v12) = 0;
  return Src;
}

```

## disassembly

```asm
0x140008a04  mov     [rsp+arg_8], rbx
0x140008a09  mov     [rsp+arg_0], rcx
0x140008a0e  push    rbp
0x140008a0f  push    rsi
0x140008a10  push    rdi
0x140008a11  push    r12
0x140008a13  push    r13
0x140008a15  push    r14
0x140008a17  push    r15
0x140008a19  sub     rsp, 20h
0x140008a1d  mov     rdi, r8
0x140008a20  mov     rsi, rdx
0x140008a23  mov     rbx, rcx
0x140008a26  mov     r8d, 1
0x140008a2c  mov     [rsp+58h+arg_10], r8d
0x140008a31  mov     rdx, [rdi+10h]
0x140008a35  lea     ebp, [r8+6]
0x140008a39  cmp     [rdi+18h], rbp
0x140008a3d  jbe     short loc_140008A44
0x140008a3f  mov     r15, [rdi]
0x140008a42  jmp     short loc_140008A47
0x140008a44  mov     r15, rdi
0x140008a47  test    rdx, rdx
0x140008a4a  jz      loc_140008B70
0x140008a50  lea     r13, [rdx+rdx]
0x140008a54  mov     rax, r13
0x140008a57  and     rax, 0FFFFFFFFFFFFFFFEh
0x140008a5b  mov     r9d, 0FFFFFFDFh
0x140008a61  mov     r10d, 3A0041h
0x140008a67  cmp     rax, 4
0x140008a6b  jl      short loc_140008A7F
0x140008a6d  mov     eax, [r15]
0x140008a70  and     eax, r9d
0x140008a73  sub     eax, r10d
0x140008a76  cmp     eax, 1Ah
0x140008a79  jb      loc_140008B70
0x140008a7f  mov     r11d, 5Ch ; '\'
0x140008a85  cmp     [r15], r11w
0x140008a89  jz      loc_140008B70
0x140008a8f  cmp     word ptr [r15], 2Fh ; '/'
0x140008a94  jz      loc_140008B70
0x140008a9a  mov     rcx, [rsi+10h]
0x140008a9e  cmp     [rsi+18h], rbp
0x140008aa2  jbe     short loc_140008AA7
0x140008aa4  mov     rsi, [rsi]
0x140008aa7  cmp     rcx, 2
0x140008aab  jnz     short loc_140008AF9
0x140008aad  mov     eax, [rsi]
0x140008aaf  and     eax, r9d
0x140008ab2  sub     eax, r10d
0x140008ab5  cmp     eax, 1Ah
0x140008ab8  jnb     short loc_140008AFE
0x140008aba  xor     r12b, r12b
0x140008abd  lea     r14, [rcx+rcx]
0x140008ac1  movzx   edi, r12b
0x140008ac5  add     rdi, rcx
0x140008ac8  add     rdi, rdx
0x140008acb  xorps   xmm0, xmm0
0x140008ace  movups  xmmword ptr [rbx], xmm0
0x140008ad1  mov     qword ptr [rbx+10h], 0
0x140008ad9  mov     [rbx+18h], rbp
0x140008add  xor     eax, eax
0x140008adf  mov     [rbx], ax
0x140008ae2  mov     [rsp+58h+arg_10], r8d
0x140008ae7  cmp     rdi, rbp
0x140008aea  jbe     short loc_140008B18
0x140008aec  mov     rdx, rdi
0x140008aef  mov     rcx, rbx; Src
0x140008af2  call    ??$_Reallocate_grow_by@V_lambda_3c42e42a79350c8a48dd4e272c8dbcce_@@$$V@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3c42e42a79350c8a48dd4e272c8dbcce_@@@Z; std::wstring::_Reallocate_grow_by<_lambda_3c42e42a79350c8a48dd4e272c8dbcce_,>(unsigned __int64,_lambda_3c42e42a79350c8a48dd4e272c8dbcce_)
0x140008af7  jmp     short loc_140008B1C
0x140008af9  test    rcx, rcx
0x140008afc  jz      short loc_140008ABA
0x140008afe  lea     r14, [rcx+rcx]
0x140008b02  cmp     [r14+rsi-2], r11w
0x140008b08  jz      short loc_140008ABA
0x140008b0a  cmp     word ptr [r14+rsi-2], 2Fh ; '/'
0x140008b11  jz      short loc_140008ABA
0x140008b13  mov     r12b, r8b
0x140008b16  jmp     short loc_140008AC1
0x140008b18  mov     [rbx+10h], rdi
0x140008b1c  cmp     [rbx+18h], rbp
0x140008b20  jbe     short loc_140008B27
0x140008b22  mov     rbp, [rbx]
0x140008b25  jmp     short loc_140008B2A
0x140008b27  mov     rbp, rbx
0x140008b2a  mov     r8, r14; Size
0x140008b2d  mov     rdx, rsi; Src
0x140008b30  mov     rcx, rbp; void *
0x140008b33  call    memcpy_0
0x140008b38  lea     rcx, [r14+rbp]
0x140008b3c  test    r12b, r12b
0x140008b3f  jz      short loc_140008B4A
0x140008b41  mov     word ptr [rcx], 5Ch ; '\'
0x140008b46  add     rcx, 2; void *
0x140008b4a  mov     r8, r13; Size
0x140008b4d  mov     rdx, r15; Src
0x140008b50  call    memcpy_0
0x140008b55  mov     [rbx+10h], rdi
0x140008b59  cmp     qword ptr [rbx+18h], 7
0x140008b5e  jbe     short loc_140008B65
0x140008b60  mov     rcx, [rbx]
0x140008b63  jmp     short loc_140008B68
0x140008b65  mov     rcx, rbx; this
0x140008b68  xor     eax, eax
0x140008b6a  mov     [rcx+rdi*2], ax
0x140008b6e  jmp     short loc_140008B8D
0x140008b70  mov     rdx, rsi; struct std::filesystem::path *
0x140008b73  call    ??0path@filesystem@std@@QEAA@AEBV012@@Z; std::filesystem::path::path(std::filesystem::path const &)
0x140008b78  nop
0x140008b79  mov     [rsp+58h+arg_10], 3
0x140008b81  mov     rdx, rdi; this
0x140008b84  mov     rcx, rbx; Src
0x140008b87  call    ??_0path@filesystem@std@@QEAAAEAV012@AEBV012@@Z; std::filesystem::path::operator/=(std::filesystem::path const &)
0x140008b8c  nop
0x140008b8d  mov     rax, rbx
0x140008b90  mov     rbx, [rsp+58h+arg_8]
0x140008b95  add     rsp, 20h
0x140008b99  pop     r15
0x140008b9b  pop     r14
0x140008b9d  pop     r13
0x140008b9f  pop     r12
0x140008ba1  pop     rdi
0x140008ba2  pop     rsi
0x140008ba3  pop     rbp
0x140008ba4  retn
```
