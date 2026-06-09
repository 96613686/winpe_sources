# std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)

- ea: `0x1800061a4`
- end: `0x180006345`
- name: `??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z`
- size: `417`
- prototype: `__int64 __fastcall(void *Src, struct std::filesystem::path *, void *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180006b3c`
- `0x180006bd4`
- `0x180006d98`
- `0x180007158`

## callees

- `0x180005f3c`
- `0x1800061a4`
- `0x180006358`
- `0x180008928`
- `0x180015e40`

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
0x1800061a4  mov     [rsp+arg_8], rbx
0x1800061a9  mov     [rsp+arg_0], rcx
0x1800061ae  push    rbp
0x1800061af  push    rsi
0x1800061b0  push    rdi
0x1800061b1  push    r12
0x1800061b3  push    r13
0x1800061b5  push    r14
0x1800061b7  push    r15
0x1800061b9  sub     rsp, 20h
0x1800061bd  mov     rdi, r8
0x1800061c0  mov     rsi, rdx
0x1800061c3  mov     rbx, rcx
0x1800061c6  mov     r10d, 1
0x1800061cc  mov     [rsp+58h+arg_10], r10d
0x1800061d1  mov     r13, [r8+10h]
0x1800061d5  mov     r15, r8
0x1800061d8  cmp     qword ptr [r8+18h], 7
0x1800061dd  jbe     short loc_1800061E2
0x1800061df  mov     r15, [r8]
0x1800061e2  lea     rax, ds:0[r13*2]
0x1800061ea  xor     edx, edx
0x1800061ec  test    r13, r13
0x1800061ef  jz      loc_180006310
0x1800061f5  and     rax, 0FFFFFFFFFFFFFFFEh
0x1800061f9  mov     r8d, 0FFFFFFDFh
0x1800061ff  mov     r9d, 3A0041h
0x180006205  cmp     rax, 4
0x180006209  jl      short loc_18000621D
0x18000620b  mov     eax, [r15]
0x18000620e  and     eax, r8d
0x180006211  sub     eax, r9d
0x180006214  cmp     eax, 1Ah
0x180006217  jb      loc_180006310
0x18000621d  mov     r11d, 5Ch ; '\'
0x180006223  cmp     [r15], r11w
0x180006227  jz      loc_180006310
0x18000622d  cmp     word ptr [r15], 2Fh ; '/'
0x180006232  jz      loc_180006310
0x180006238  mov     rcx, [rsi+10h]
0x18000623c  cmp     qword ptr [rsi+18h], 7
0x180006241  jbe     short loc_180006246
0x180006243  mov     rsi, [rsi]
0x180006246  cmp     rcx, 2
0x18000624a  jnz     short loc_180006297
0x18000624c  mov     eax, [rsi]
0x18000624e  and     eax, r8d
0x180006251  sub     eax, r9d
0x180006254  cmp     eax, 1Ah
0x180006257  jnb     short loc_18000629C
0x180006259  mov     r12b, dl
0x18000625c  lea     r14, [rcx+rcx]
0x180006260  movzx   edi, r12b
0x180006264  add     rdi, rcx
0x180006267  add     rdi, r13
0x18000626a  xorps   xmm0, xmm0
0x18000626d  movups  xmmword ptr [rbx], xmm0
0x180006270  mov     [rbx+10h], rdx
0x180006274  mov     qword ptr [rbx+18h], 7
0x18000627c  mov     [rbx], dx
0x18000627f  mov     [rsp+58h+arg_10], r10d
0x180006284  cmp     rdi, 7
0x180006288  jbe     short loc_1800062B6
0x18000628a  mov     rdx, rdi
0x18000628d  mov     rcx, rbx; Src
0x180006290  call    ??$_Reallocate_grow_by@V_lambda_d27e2b2d334e86d578b418f53091db3c_@@$$V@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_d27e2b2d334e86d578b418f53091db3c_@@@Z; std::wstring::_Reallocate_grow_by<_lambda_d27e2b2d334e86d578b418f53091db3c_,>(unsigned __int64,_lambda_d27e2b2d334e86d578b418f53091db3c_)
0x180006295  jmp     short loc_1800062BA
0x180006297  test    rcx, rcx
0x18000629a  jz      short loc_180006259
0x18000629c  lea     r14, [rcx+rcx]
0x1800062a0  cmp     [r14+rsi-2], r11w
0x1800062a6  jz      short loc_180006259
0x1800062a8  cmp     word ptr [r14+rsi-2], 2Fh ; '/'
0x1800062af  jz      short loc_180006259
0x1800062b1  mov     r12b, r10b
0x1800062b4  jmp     short loc_180006260
0x1800062b6  mov     [rbx+10h], rdi
0x1800062ba  mov     rbp, rbx
0x1800062bd  cmp     qword ptr [rbx+18h], 7
0x1800062c2  jbe     short loc_1800062C7
0x1800062c4  mov     rbp, [rbx]
0x1800062c7  mov     r8, r14; Size
0x1800062ca  mov     rdx, rsi; Src
0x1800062cd  mov     rcx, rbp; void *
0x1800062d0  call    memmove
0x1800062d5  lea     rcx, [r14+rbp]
0x1800062d9  xor     esi, esi
0x1800062db  test    r12b, r12b
0x1800062de  jz      short loc_1800062E9
0x1800062e0  mov     word ptr [rcx], 5Ch ; '\'
0x1800062e5  add     rcx, 2; void *
0x1800062e9  lea     r8, ds:0[r13*2]; Size
0x1800062f1  mov     rdx, r15; Src
0x1800062f4  call    memmove
0x1800062f9  mov     [rbx+10h], rdi
0x1800062fd  mov     rax, rbx
0x180006300  cmp     qword ptr [rbx+18h], 7
0x180006305  jbe     short loc_18000630A
0x180006307  mov     rax, [rbx]
0x18000630a  mov     [rax+rdi*2], si
0x18000630e  jmp     short loc_18000632D
0x180006310  mov     rdx, rsi; struct std::filesystem::path *
0x180006313  call    ??0path@filesystem@std@@QEAA@AEBV012@@Z; std::filesystem::path::path(std::filesystem::path const &)
0x180006318  nop
0x180006319  mov     [rsp+58h+arg_10], 3
0x180006321  mov     rdx, rdi; void *
0x180006324  mov     rcx, rbx; Src
0x180006327  call    ??_0path@filesystem@std@@QEAAAEAV012@AEBV012@@Z; std::filesystem::path::operator/=(std::filesystem::path const &)
0x18000632c  nop
0x18000632d  mov     rax, rbx
0x180006330  mov     rbx, [rsp+58h+arg_8]
0x180006335  add     rsp, 20h
0x180006339  pop     r15
0x18000633b  pop     r14
0x18000633d  pop     r13
0x18000633f  pop     r12
0x180006341  pop     rdi
0x180006342  pop     rsi
0x180006343  pop     rbp
0x180006344  retn
```
