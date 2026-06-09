# std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)

- ea: `0x140006d08`
- end: `0x140006ea9`
- name: `??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z`
- size: `417`
- prototype: `__int64 __fastcall(void *Src, struct std::filesystem::path *, void *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x140007060`
- `0x140007320`

## callees

- `0x140006aa0`
- `0x140006d08`
- `0x140006ebc`
- `0x140009400`
- `0x140020b20`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
std::filesystem::path *__fastcall std::filesystem::operator/(
        std::filesystem::path *Src,
        struct std::filesystem::path *a2,
        _QWORD *a3)
{
  struct std::filesystem::path *v4; // rsi
  __int64 v6; // r13
  _DWORD *v7; // r15
  __int64 v8; // rcx
  unsigned __int8 v9; // r12
  size_t v10; // r14
  unsigned __int64 v11; // rdi
  std::filesystem::path *v12; // rbp
  _WORD *v13; // rcx
  std::filesystem::path *v14; // rax

  v4 = a2;
  v6 = a3[2];
  v7 = a3;
  if ( a3[3] > 7u )
    v7 = (_DWORD *)*a3;
  if ( !v6 || 2 * v6 >= 4 && (*v7 & 0xFFFFFFDF) - 3801153 < 0x1A || *(_WORD *)v7 == 92 || *(_WORD *)v7 == 47 )
  {
    std::filesystem::path::path(Src, a2);
    std::filesystem::path::operator/=(Src, (std::filesystem *)a3);
    return Src;
  }
  v8 = *((_QWORD *)a2 + 2);
  if ( *((_QWORD *)a2 + 3) > 7u )
    v4 = *(struct std::filesystem::path **)a2;
  if ( v8 == 2 )
  {
    if ( (*(_DWORD *)v4 & 0xFFFFFFDF) - 3801153 < 0x1A )
      goto LABEL_12;
  }
  else if ( !v8 )
  {
    goto LABEL_12;
  }
  v10 = 2 * v8;
  if ( *((_WORD *)v4 + v8 - 1) != 92 && *(_WORD *)((char *)v4 + v10 - 2) != 47 )
  {
    v9 = 1;
    goto LABEL_13;
  }
LABEL_12:
  v9 = 0;
  v10 = 2 * v8;
LABEL_13:
  v11 = v6 + v8 + v9;
  *(_OWORD *)Src = 0;
  *((_QWORD *)Src + 2) = 0;
  *((_QWORD *)Src + 3) = 7;
  *(_WORD *)Src = 0;
  if ( v11 <= 7 )
    *((_QWORD *)Src + 2) = v11;
  else
    std::wstring::_Reallocate_grow_by<_lambda_d27e2b2d334e86d578b418f53091db3c_,>(Src);
  v12 = Src;
  if ( *((_QWORD *)Src + 3) > 7u )
    v12 = *(std::filesystem::path **)Src;
  memmove(v12, v4, v10);
  v13 = (_WORD *)((char *)v12 + v10);
  if ( v9 )
    *v13++ = 92;
  memmove(v13, v7, 2 * v6);
  *((_QWORD *)Src + 2) = v11;
  v14 = Src;
  if ( *((_QWORD *)Src + 3) > 7u )
    v14 = *(std::filesystem::path **)Src;
  *((_WORD *)v14 + v11) = 0;
  return Src;
}

```

## disassembly

```asm
0x140006d08  mov     [rsp+arg_8], rbx
0x140006d0d  mov     [rsp+arg_0], rcx
0x140006d12  push    rbp
0x140006d13  push    rsi
0x140006d14  push    rdi
0x140006d15  push    r12
0x140006d17  push    r13
0x140006d19  push    r14
0x140006d1b  push    r15
0x140006d1d  sub     rsp, 20h
0x140006d21  mov     rdi, r8
0x140006d24  mov     rsi, rdx
0x140006d27  mov     rbx, rcx
0x140006d2a  mov     r10d, 1
0x140006d30  mov     [rsp+58h+arg_10], r10d
0x140006d35  mov     r13, [r8+10h]
0x140006d39  mov     r15, r8
0x140006d3c  cmp     qword ptr [r8+18h], 7
0x140006d41  jbe     short loc_140006D46
0x140006d43  mov     r15, [r8]
0x140006d46  lea     rax, ds:0[r13*2]
0x140006d4e  xor     edx, edx
0x140006d50  test    r13, r13
0x140006d53  jz      loc_140006E74
0x140006d59  and     rax, 0FFFFFFFFFFFFFFFEh
0x140006d5d  mov     r8d, 0FFFFFFDFh
0x140006d63  mov     r9d, 3A0041h
0x140006d69  cmp     rax, 4
0x140006d6d  jl      short loc_140006D81
0x140006d6f  mov     eax, [r15]
0x140006d72  and     eax, r8d
0x140006d75  sub     eax, r9d
0x140006d78  cmp     eax, 1Ah
0x140006d7b  jb      loc_140006E74
0x140006d81  mov     r11d, 5Ch ; '\'
0x140006d87  cmp     [r15], r11w
0x140006d8b  jz      loc_140006E74
0x140006d91  cmp     word ptr [r15], 2Fh ; '/'
0x140006d96  jz      loc_140006E74
0x140006d9c  mov     rcx, [rsi+10h]
0x140006da0  cmp     qword ptr [rsi+18h], 7
0x140006da5  jbe     short loc_140006DAA
0x140006da7  mov     rsi, [rsi]
0x140006daa  cmp     rcx, 2
0x140006dae  jnz     short loc_140006DFB
0x140006db0  mov     eax, [rsi]
0x140006db2  and     eax, r8d
0x140006db5  sub     eax, r9d
0x140006db8  cmp     eax, 1Ah
0x140006dbb  jnb     short loc_140006E00
0x140006dbd  mov     r12b, dl
0x140006dc0  lea     r14, [rcx+rcx]
0x140006dc4  movzx   edi, r12b
0x140006dc8  add     rdi, rcx
0x140006dcb  add     rdi, r13
0x140006dce  xorps   xmm0, xmm0
0x140006dd1  movups  xmmword ptr [rbx], xmm0
0x140006dd4  mov     [rbx+10h], rdx
0x140006dd8  mov     qword ptr [rbx+18h], 7
0x140006de0  mov     [rbx], dx
0x140006de3  mov     [rsp+58h+arg_10], r10d
0x140006de8  cmp     rdi, 7
0x140006dec  jbe     short loc_140006E1A
0x140006dee  mov     rdx, rdi
0x140006df1  mov     rcx, rbx; Src
0x140006df4  call    ??$_Reallocate_grow_by@V_lambda_d27e2b2d334e86d578b418f53091db3c_@@$$V@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_d27e2b2d334e86d578b418f53091db3c_@@@Z; std::wstring::_Reallocate_grow_by<_lambda_d27e2b2d334e86d578b418f53091db3c_,>(unsigned __int64,_lambda_d27e2b2d334e86d578b418f53091db3c_)
0x140006df9  jmp     short loc_140006E1E
0x140006dfb  test    rcx, rcx
0x140006dfe  jz      short loc_140006DBD
0x140006e00  lea     r14, [rcx+rcx]
0x140006e04  cmp     [r14+rsi-2], r11w
0x140006e0a  jz      short loc_140006DBD
0x140006e0c  cmp     word ptr [r14+rsi-2], 2Fh ; '/'
0x140006e13  jz      short loc_140006DBD
0x140006e15  mov     r12b, r10b
0x140006e18  jmp     short loc_140006DC4
0x140006e1a  mov     [rbx+10h], rdi
0x140006e1e  mov     rbp, rbx
0x140006e21  cmp     qword ptr [rbx+18h], 7
0x140006e26  jbe     short loc_140006E2B
0x140006e28  mov     rbp, [rbx]
0x140006e2b  mov     r8, r14; Size
0x140006e2e  mov     rdx, rsi; Src
0x140006e31  mov     rcx, rbp; void *
0x140006e34  call    memmove
0x140006e39  lea     rcx, [r14+rbp]
0x140006e3d  xor     esi, esi
0x140006e3f  test    r12b, r12b
0x140006e42  jz      short loc_140006E4D
0x140006e44  mov     word ptr [rcx], 5Ch ; '\'
0x140006e49  add     rcx, 2; void *
0x140006e4d  lea     r8, ds:0[r13*2]; Size
0x140006e55  mov     rdx, r15; Src
0x140006e58  call    memmove
0x140006e5d  mov     [rbx+10h], rdi
0x140006e61  mov     rax, rbx
0x140006e64  cmp     qword ptr [rbx+18h], 7
0x140006e69  jbe     short loc_140006E6E
0x140006e6b  mov     rax, [rbx]
0x140006e6e  mov     [rax+rdi*2], si
0x140006e72  jmp     short loc_140006E91
0x140006e74  mov     rdx, rsi; struct std::filesystem::path *
0x140006e77  call    ??0path@filesystem@std@@QEAA@AEBV012@@Z; std::filesystem::path::path(std::filesystem::path const &)
0x140006e7c  nop
0x140006e7d  mov     [rsp+58h+arg_10], 3
0x140006e85  mov     rdx, rdi; void *
0x140006e88  mov     rcx, rbx; Src
0x140006e8b  call    ??_0path@filesystem@std@@QEAAAEAV012@AEBV012@@Z; std::filesystem::path::operator/=(std::filesystem::path const &)
0x140006e90  nop
0x140006e91  mov     rax, rbx
0x140006e94  mov     rbx, [rsp+58h+arg_8]
0x140006e99  add     rsp, 20h
0x140006e9d  pop     r15
0x140006e9f  pop     r14
0x140006ea1  pop     r13
0x140006ea3  pop     r12
0x140006ea5  pop     rdi
0x140006ea6  pop     rsi
0x140006ea7  pop     rbp
0x140006ea8  retn
```
