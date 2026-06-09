# std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)

- ea: `0x140008a34`
- end: `0x140008bd5`
- name: `??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z`
- size: `417`
- prototype: `std::filesystem::path *__fastcall(std::filesystem::path *Src, struct std::filesystem::path *, std::filesystem *this)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x1400093c0`
- `0x140009608`
- `0x14000969c`
- `0x14000a6a8`

## callees

- `0x1400075ec`
- `0x1400084a4`
- `0x140008a34`
- `0x140008c78`
- `0x14000ac74`

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
0x140008a34  mov     [rsp+arg_8], rbx
0x140008a39  mov     [rsp+arg_0], rcx
0x140008a3e  push    rbp
0x140008a3f  push    rsi
0x140008a40  push    rdi
0x140008a41  push    r12
0x140008a43  push    r13
0x140008a45  push    r14
0x140008a47  push    r15
0x140008a49  sub     rsp, 20h
0x140008a4d  mov     rdi, r8
0x140008a50  mov     rsi, rdx
0x140008a53  mov     rbx, rcx
0x140008a56  mov     r8d, 1
0x140008a5c  mov     [rsp+58h+arg_10], r8d
0x140008a61  mov     rdx, [rdi+10h]
0x140008a65  lea     ebp, [r8+6]
0x140008a69  cmp     [rdi+18h], rbp
0x140008a6d  jbe     short loc_140008A74
0x140008a6f  mov     r15, [rdi]
0x140008a72  jmp     short loc_140008A77
0x140008a74  mov     r15, rdi
0x140008a77  test    rdx, rdx
0x140008a7a  jz      loc_140008BA0
0x140008a80  lea     r13, [rdx+rdx]
0x140008a84  mov     rax, r13
0x140008a87  and     rax, 0FFFFFFFFFFFFFFFEh
0x140008a8b  mov     r9d, 0FFFFFFDFh
0x140008a91  mov     r10d, 3A0041h
0x140008a97  cmp     rax, 4
0x140008a9b  jl      short loc_140008AAF
0x140008a9d  mov     eax, [r15]
0x140008aa0  and     eax, r9d
0x140008aa3  sub     eax, r10d
0x140008aa6  cmp     eax, 1Ah
0x140008aa9  jb      loc_140008BA0
0x140008aaf  mov     r11d, 5Ch ; '\'
0x140008ab5  cmp     [r15], r11w
0x140008ab9  jz      loc_140008BA0
0x140008abf  cmp     word ptr [r15], 2Fh ; '/'
0x140008ac4  jz      loc_140008BA0
0x140008aca  mov     rcx, [rsi+10h]
0x140008ace  cmp     [rsi+18h], rbp
0x140008ad2  jbe     short loc_140008AD7
0x140008ad4  mov     rsi, [rsi]
0x140008ad7  cmp     rcx, 2
0x140008adb  jnz     short loc_140008B29
0x140008add  mov     eax, [rsi]
0x140008adf  and     eax, r9d
0x140008ae2  sub     eax, r10d
0x140008ae5  cmp     eax, 1Ah
0x140008ae8  jnb     short loc_140008B2E
0x140008aea  xor     r12b, r12b
0x140008aed  lea     r14, [rcx+rcx]
0x140008af1  movzx   edi, r12b
0x140008af5  add     rdi, rcx
0x140008af8  add     rdi, rdx
0x140008afb  xorps   xmm0, xmm0
0x140008afe  movups  xmmword ptr [rbx], xmm0
0x140008b01  mov     qword ptr [rbx+10h], 0
0x140008b09  mov     [rbx+18h], rbp
0x140008b0d  xor     eax, eax
0x140008b0f  mov     [rbx], ax
0x140008b12  mov     [rsp+58h+arg_10], r8d
0x140008b17  cmp     rdi, rbp
0x140008b1a  jbe     short loc_140008B48
0x140008b1c  mov     rdx, rdi
0x140008b1f  mov     rcx, rbx; Src
0x140008b22  call    ??$_Reallocate_grow_by@V_lambda_3c42e42a79350c8a48dd4e272c8dbcce_@@$$V@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3c42e42a79350c8a48dd4e272c8dbcce_@@@Z; std::wstring::_Reallocate_grow_by<_lambda_3c42e42a79350c8a48dd4e272c8dbcce_,>(unsigned __int64,_lambda_3c42e42a79350c8a48dd4e272c8dbcce_)
0x140008b27  jmp     short loc_140008B4C
0x140008b29  test    rcx, rcx
0x140008b2c  jz      short loc_140008AEA
0x140008b2e  lea     r14, [rcx+rcx]
0x140008b32  cmp     [r14+rsi-2], r11w
0x140008b38  jz      short loc_140008AEA
0x140008b3a  cmp     word ptr [r14+rsi-2], 2Fh ; '/'
0x140008b41  jz      short loc_140008AEA
0x140008b43  mov     r12b, r8b
0x140008b46  jmp     short loc_140008AF1
0x140008b48  mov     [rbx+10h], rdi
0x140008b4c  cmp     [rbx+18h], rbp
0x140008b50  jbe     short loc_140008B57
0x140008b52  mov     rbp, [rbx]
0x140008b55  jmp     short loc_140008B5A
0x140008b57  mov     rbp, rbx
0x140008b5a  mov     r8, r14; Size
0x140008b5d  mov     rdx, rsi; Src
0x140008b60  mov     rcx, rbp; void *
0x140008b63  call    memcpy_0
0x140008b68  lea     rcx, [r14+rbp]
0x140008b6c  test    r12b, r12b
0x140008b6f  jz      short loc_140008B7A
0x140008b71  mov     word ptr [rcx], 5Ch ; '\'
0x140008b76  add     rcx, 2; void *
0x140008b7a  mov     r8, r13; Size
0x140008b7d  mov     rdx, r15; Src
0x140008b80  call    memcpy_0
0x140008b85  mov     [rbx+10h], rdi
0x140008b89  cmp     qword ptr [rbx+18h], 7
0x140008b8e  jbe     short loc_140008B95
0x140008b90  mov     rcx, [rbx]
0x140008b93  jmp     short loc_140008B98
0x140008b95  mov     rcx, rbx; this
0x140008b98  xor     eax, eax
0x140008b9a  mov     [rcx+rdi*2], ax
0x140008b9e  jmp     short loc_140008BBD
0x140008ba0  mov     rdx, rsi; struct std::filesystem::path *
0x140008ba3  call    ??0path@filesystem@std@@QEAA@AEBV012@@Z; std::filesystem::path::path(std::filesystem::path const &)
0x140008ba8  nop
0x140008ba9  mov     [rsp+58h+arg_10], 3
0x140008bb1  mov     rdx, rdi; this
0x140008bb4  mov     rcx, rbx; Src
0x140008bb7  call    ??_0path@filesystem@std@@QEAAAEAV012@AEBV012@@Z; std::filesystem::path::operator/=(std::filesystem::path const &)
0x140008bbc  nop
0x140008bbd  mov     rax, rbx
0x140008bc0  mov     rbx, [rsp+58h+arg_8]
0x140008bc5  add     rsp, 20h
0x140008bc9  pop     r15
0x140008bcb  pop     r14
0x140008bcd  pop     r13
0x140008bcf  pop     r12
0x140008bd1  pop     rdi
0x140008bd2  pop     rsi
0x140008bd3  pop     rbp
0x140008bd4  retn
```
