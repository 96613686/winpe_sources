# std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)

- ea: `0x180008c74`
- end: `0x180008e15`
- name: `??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z`
- size: `417`
- prototype: `std::filesystem::path *__fastcall(std::filesystem::path *Src, struct std::filesystem::path *, std::filesystem *this)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180009540`
- `0x1800096cc`
- `0x1800097fc`
- `0x180009890`

## callees

- `0x180007930`
- `0x1800087e8`
- `0x180008c74`
- `0x180008eb8`
- `0x18000e454`

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
0x180008c74  mov     [rsp+arg_8], rbx
0x180008c79  mov     [rsp+arg_0], rcx
0x180008c7e  push    rbp
0x180008c7f  push    rsi
0x180008c80  push    rdi
0x180008c81  push    r12
0x180008c83  push    r13
0x180008c85  push    r14
0x180008c87  push    r15
0x180008c89  sub     rsp, 20h
0x180008c8d  mov     rdi, r8
0x180008c90  mov     rsi, rdx
0x180008c93  mov     rbx, rcx
0x180008c96  mov     r8d, 1
0x180008c9c  mov     [rsp+58h+arg_10], r8d
0x180008ca1  mov     rdx, [rdi+10h]
0x180008ca5  lea     ebp, [r8+6]
0x180008ca9  cmp     [rdi+18h], rbp
0x180008cad  jbe     short loc_180008CB4
0x180008caf  mov     r15, [rdi]
0x180008cb2  jmp     short loc_180008CB7
0x180008cb4  mov     r15, rdi
0x180008cb7  test    rdx, rdx
0x180008cba  jz      loc_180008DE0
0x180008cc0  lea     r13, [rdx+rdx]
0x180008cc4  mov     rax, r13
0x180008cc7  and     rax, 0FFFFFFFFFFFFFFFEh
0x180008ccb  mov     r9d, 0FFFFFFDFh
0x180008cd1  mov     r10d, 3A0041h
0x180008cd7  cmp     rax, 4
0x180008cdb  jl      short loc_180008CEF
0x180008cdd  mov     eax, [r15]
0x180008ce0  and     eax, r9d
0x180008ce3  sub     eax, r10d
0x180008ce6  cmp     eax, 1Ah
0x180008ce9  jb      loc_180008DE0
0x180008cef  mov     r11d, 5Ch ; '\'
0x180008cf5  cmp     [r15], r11w
0x180008cf9  jz      loc_180008DE0
0x180008cff  cmp     word ptr [r15], 2Fh ; '/'
0x180008d04  jz      loc_180008DE0
0x180008d0a  mov     rcx, [rsi+10h]
0x180008d0e  cmp     [rsi+18h], rbp
0x180008d12  jbe     short loc_180008D17
0x180008d14  mov     rsi, [rsi]
0x180008d17  cmp     rcx, 2
0x180008d1b  jnz     short loc_180008D69
0x180008d1d  mov     eax, [rsi]
0x180008d1f  and     eax, r9d
0x180008d22  sub     eax, r10d
0x180008d25  cmp     eax, 1Ah
0x180008d28  jnb     short loc_180008D6E
0x180008d2a  xor     r12b, r12b
0x180008d2d  lea     r14, [rcx+rcx]
0x180008d31  movzx   edi, r12b
0x180008d35  add     rdi, rcx
0x180008d38  add     rdi, rdx
0x180008d3b  xorps   xmm0, xmm0
0x180008d3e  movups  xmmword ptr [rbx], xmm0
0x180008d41  mov     qword ptr [rbx+10h], 0
0x180008d49  mov     [rbx+18h], rbp
0x180008d4d  xor     eax, eax
0x180008d4f  mov     [rbx], ax
0x180008d52  mov     [rsp+58h+arg_10], r8d
0x180008d57  cmp     rdi, rbp
0x180008d5a  jbe     short loc_180008D88
0x180008d5c  mov     rdx, rdi
0x180008d5f  mov     rcx, rbx; Src
0x180008d62  call    ??$_Reallocate_grow_by@V_lambda_3c42e42a79350c8a48dd4e272c8dbcce_@@$$V@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3c42e42a79350c8a48dd4e272c8dbcce_@@@Z; std::wstring::_Reallocate_grow_by<_lambda_3c42e42a79350c8a48dd4e272c8dbcce_,>(unsigned __int64,_lambda_3c42e42a79350c8a48dd4e272c8dbcce_)
0x180008d67  jmp     short loc_180008D8C
0x180008d69  test    rcx, rcx
0x180008d6c  jz      short loc_180008D2A
0x180008d6e  lea     r14, [rcx+rcx]
0x180008d72  cmp     [r14+rsi-2], r11w
0x180008d78  jz      short loc_180008D2A
0x180008d7a  cmp     word ptr [r14+rsi-2], 2Fh ; '/'
0x180008d81  jz      short loc_180008D2A
0x180008d83  mov     r12b, r8b
0x180008d86  jmp     short loc_180008D31
0x180008d88  mov     [rbx+10h], rdi
0x180008d8c  cmp     [rbx+18h], rbp
0x180008d90  jbe     short loc_180008D97
0x180008d92  mov     rbp, [rbx]
0x180008d95  jmp     short loc_180008D9A
0x180008d97  mov     rbp, rbx
0x180008d9a  mov     r8, r14; Size
0x180008d9d  mov     rdx, rsi; Src
0x180008da0  mov     rcx, rbp; void *
0x180008da3  call    memcpy_0
0x180008da8  lea     rcx, [r14+rbp]
0x180008dac  test    r12b, r12b
0x180008daf  jz      short loc_180008DBA
0x180008db1  mov     word ptr [rcx], 5Ch ; '\'
0x180008db6  add     rcx, 2; void *
0x180008dba  mov     r8, r13; Size
0x180008dbd  mov     rdx, r15; Src
0x180008dc0  call    memcpy_0
0x180008dc5  mov     [rbx+10h], rdi
0x180008dc9  cmp     qword ptr [rbx+18h], 7
0x180008dce  jbe     short loc_180008DD5
0x180008dd0  mov     rcx, [rbx]
0x180008dd3  jmp     short loc_180008DD8
0x180008dd5  mov     rcx, rbx; this
0x180008dd8  xor     eax, eax
0x180008dda  mov     [rcx+rdi*2], ax
0x180008dde  jmp     short loc_180008DFD
0x180008de0  mov     rdx, rsi; struct std::filesystem::path *
0x180008de3  call    ??0path@filesystem@std@@QEAA@AEBV012@@Z; std::filesystem::path::path(std::filesystem::path const &)
0x180008de8  nop
0x180008de9  mov     [rsp+58h+arg_10], 3
0x180008df1  mov     rdx, rdi; this
0x180008df4  mov     rcx, rbx; Src
0x180008df7  call    ??_0path@filesystem@std@@QEAAAEAV012@AEBV012@@Z; std::filesystem::path::operator/=(std::filesystem::path const &)
0x180008dfc  nop
0x180008dfd  mov     rax, rbx
0x180008e00  mov     rbx, [rsp+58h+arg_8]
0x180008e05  add     rsp, 20h
0x180008e09  pop     r15
0x180008e0b  pop     r14
0x180008e0d  pop     r13
0x180008e0f  pop     r12
0x180008e11  pop     rdi
0x180008e12  pop     rsi
0x180008e13  pop     rbp
0x180008e14  retn
```
