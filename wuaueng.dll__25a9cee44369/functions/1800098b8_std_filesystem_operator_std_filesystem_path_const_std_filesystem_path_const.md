# std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)

- ea: `0x1800098b8`
- end: `0x180009a59`
- name: `??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z`
- size: `417`
- prototype: `std::filesystem::path *__fastcall(std::filesystem::path *Src, struct std::filesystem::path *, _QWORD *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180008148`
- `0x180008388`
- `0x180009a60`
- `0x18000a430`

## callees

- `0x180008f84`
- `0x1800090a0`
- `0x180009650`
- `0x1800098b8`
- `0x180015df0`

## pseudocode

```c
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
0x1800098b8  mov     [rsp+arg_8], rbx
0x1800098bd  mov     [rsp+arg_0], rcx
0x1800098c2  push    rbp
0x1800098c3  push    rsi
0x1800098c4  push    rdi
0x1800098c5  push    r12
0x1800098c7  push    r13
0x1800098c9  push    r14
0x1800098cb  push    r15
0x1800098cd  sub     rsp, 20h
0x1800098d1  mov     rdi, r8
0x1800098d4  mov     rsi, rdx
0x1800098d7  mov     rbx, rcx
0x1800098da  mov     r10d, 1
0x1800098e0  mov     [rsp+58h+arg_10], r10d
0x1800098e5  mov     r13, [r8+10h]
0x1800098e9  mov     r15, r8
0x1800098ec  cmp     qword ptr [r8+18h], 7
0x1800098f1  jbe     short loc_1800098F6
0x1800098f3  mov     r15, [r8]
0x1800098f6  lea     rax, ds:0[r13*2]
0x1800098fe  xor     edx, edx
0x180009900  test    r13, r13
0x180009903  jz      loc_180009A24
0x180009909  and     rax, 0FFFFFFFFFFFFFFFEh
0x18000990d  mov     r8d, 0FFFFFFDFh
0x180009913  mov     r9d, 3A0041h
0x180009919  cmp     rax, 4
0x18000991d  jl      short loc_180009931
0x18000991f  mov     eax, [r15]
0x180009922  and     eax, r8d
0x180009925  sub     eax, r9d
0x180009928  cmp     eax, 1Ah
0x18000992b  jb      loc_180009A24
0x180009931  mov     r11d, 5Ch ; '\'
0x180009937  cmp     [r15], r11w
0x18000993b  jz      loc_180009A24
0x180009941  cmp     word ptr [r15], 2Fh ; '/'
0x180009946  jz      loc_180009A24
0x18000994c  mov     rcx, [rsi+10h]
0x180009950  cmp     qword ptr [rsi+18h], 7
0x180009955  jbe     short loc_18000995A
0x180009957  mov     rsi, [rsi]
0x18000995a  cmp     rcx, 2
0x18000995e  jnz     short loc_1800099AB
0x180009960  mov     eax, [rsi]
0x180009962  and     eax, r8d
0x180009965  sub     eax, r9d
0x180009968  cmp     eax, 1Ah
0x18000996b  jnb     short loc_1800099B0
0x18000996d  mov     r12b, dl
0x180009970  lea     r14, [rcx+rcx]
0x180009974  movzx   edi, r12b
0x180009978  add     rdi, rcx
0x18000997b  add     rdi, r13
0x18000997e  xorps   xmm0, xmm0
0x180009981  movups  xmmword ptr [rbx], xmm0
0x180009984  mov     [rbx+10h], rdx
0x180009988  mov     qword ptr [rbx+18h], 7
0x180009990  mov     [rbx], dx
0x180009993  mov     [rsp+58h+arg_10], r10d
0x180009998  cmp     rdi, 7
0x18000999c  jbe     short loc_1800099CA
0x18000999e  mov     rdx, rdi
0x1800099a1  mov     rcx, rbx; Src
0x1800099a4  call    ??$_Reallocate_grow_by@V_lambda_d27e2b2d334e86d578b418f53091db3c_@@$$V@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_d27e2b2d334e86d578b418f53091db3c_@@@Z; std::wstring::_Reallocate_grow_by<_lambda_d27e2b2d334e86d578b418f53091db3c_,>(unsigned __int64,_lambda_d27e2b2d334e86d578b418f53091db3c_)
0x1800099a9  jmp     short loc_1800099CE
0x1800099ab  test    rcx, rcx
0x1800099ae  jz      short loc_18000996D
0x1800099b0  lea     r14, [rcx+rcx]
0x1800099b4  cmp     [r14+rsi-2], r11w
0x1800099ba  jz      short loc_18000996D
0x1800099bc  cmp     word ptr [r14+rsi-2], 2Fh ; '/'
0x1800099c3  jz      short loc_18000996D
0x1800099c5  mov     r12b, r10b
0x1800099c8  jmp     short loc_180009974
0x1800099ca  mov     [rbx+10h], rdi
0x1800099ce  mov     rbp, rbx
0x1800099d1  cmp     qword ptr [rbx+18h], 7
0x1800099d6  jbe     short loc_1800099DB
0x1800099d8  mov     rbp, [rbx]
0x1800099db  mov     r8, r14; Size
0x1800099de  mov     rdx, rsi; Src
0x1800099e1  mov     rcx, rbp; void *
0x1800099e4  call    memmove
0x1800099e9  lea     rcx, [r14+rbp]
0x1800099ed  xor     esi, esi
0x1800099ef  test    r12b, r12b
0x1800099f2  jz      short loc_1800099FD
0x1800099f4  mov     word ptr [rcx], 5Ch ; '\'
0x1800099f9  add     rcx, 2; void *
0x1800099fd  lea     r8, ds:0[r13*2]; Size
0x180009a05  mov     rdx, r15; Src
0x180009a08  call    memmove
0x180009a0d  mov     [rbx+10h], rdi
0x180009a11  mov     rax, rbx
0x180009a14  cmp     qword ptr [rbx+18h], 7
0x180009a19  jbe     short loc_180009A1E
0x180009a1b  mov     rax, [rbx]
0x180009a1e  mov     [rax+rdi*2], si
0x180009a22  jmp     short loc_180009A41
0x180009a24  mov     rdx, rsi; struct std::filesystem::path *
0x180009a27  call    ??0path@filesystem@std@@QEAA@AEBV012@@Z; std::filesystem::path::path(std::filesystem::path const &)
0x180009a2c  nop
0x180009a2d  mov     [rsp+58h+arg_10], 3
0x180009a35  mov     rdx, rdi; void *
0x180009a38  mov     rcx, rbx; Src
0x180009a3b  call    ??_0path@filesystem@std@@QEAAAEAV012@AEBV012@@Z; std::filesystem::path::operator/=(std::filesystem::path const &)
0x180009a40  nop
0x180009a41  mov     rax, rbx
0x180009a44  mov     rbx, [rsp+58h+arg_8]
0x180009a49  add     rsp, 20h
0x180009a4d  pop     r15
0x180009a4f  pop     r14
0x180009a51  pop     r13
0x180009a53  pop     r12
0x180009a55  pop     rdi
0x180009a56  pop     rsi
0x180009a57  pop     rbp
0x180009a58  retn
```
