# std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::basic_string_view<ushort,std::char_traits<ushort>>,std::filesystem::_Normal_conversion)

- ea: `0x140007188`
- end: `0x140007259`
- name: `??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@V?$basic_string_view@GU?$char_traits@G@std@@@1@U_Normal_conversion@01@@Z`
- size: `209`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x140007ec8`
- `0x140009390`
- `0x14000950c`
- `0x1400095d8`
- `0x14000a678`

## callees

- `0x140007020`
- `0x140007188`
- `0x14000a2ac`
- `0x14000ac54`

## pseudocode

```c
_QWORD *__fastcall std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(
        _QWORD *a1,
        __int64 a2)
{
  unsigned __int64 v2; // rbx
  __int64 v4; // rcx
  const void *v5; // rbp
  size_t v6; // rbx
  _QWORD *v7; // rax
  _QWORD *v8; // rcx
  _QWORD *v9; // rdi
  size_t v10; // rbx
  _QWORD *v12; // [rsp+60h] [rbp+8h] BYREF

  v12 = a1;
  v2 = *(_QWORD *)(a2 + 8);
  *(_OWORD *)a1 = 0;
  a1[2] = 0;
  a1[3] = 0;
  v4 = 0x7FFFFFFFFFFFFFFELL;
  if ( v2 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlen_string();
  v5 = *(const void **)a2;
  if ( v2 > 7 )
  {
    if ( (v2 | 7) <= 0x7FFFFFFFFFFFFFFELL )
    {
      v4 = v2 | 7;
      if ( (v2 | 7) < 0xA )
        v4 = 10;
    }
    v12 = (_QWORD *)v4;
    v7 = std::wstring::_Allocate_for_capacity<0>(v4, &v12);
    v8 = v12;
    a1[2] = v2;
    v9 = v7;
    a1[3] = v8;
    v10 = 2 * v2;
    *a1 = v7;
    memcpy_0(v7, v5, v10);
    *(_WORD *)((char *)v9 + v10) = 0;
  }
  else
  {
    a1[2] = v2;
    v6 = 2 * v2;
    a1[3] = 7;
    memcpy_0(a1, v5, v6);
    *(_WORD *)((char *)a1 + v6) = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x140007188  mov     [rsp+arg_0], rcx
0x14000718d  push    rbx
0x14000718e  push    rbp
0x14000718f  push    rsi
0x140007190  push    rdi
0x140007191  sub     rsp, 38h
0x140007195  mov     rbx, [rdx+8]
0x140007199  xorps   xmm0, xmm0
0x14000719c  movups  xmmword ptr [rcx], xmm0
0x14000719f  mov     qword ptr [rcx+10h], 0
0x1400071a7  mov     rsi, rcx
0x1400071aa  mov     qword ptr [rcx+18h], 0
0x1400071b2  mov     rcx, 7FFFFFFFFFFFFFFEh
0x1400071bc  cmp     rbx, rcx
0x1400071bf  ja      loc_140007253
0x1400071c5  mov     rbp, [rdx]
0x1400071c8  cmp     rbx, 7
0x1400071cc  ja      short loc_1400071F3
0x1400071ce  mov     [rsi+10h], rbx
0x1400071d2  mov     rdx, rbp; Src
0x1400071d5  add     rbx, rbx
0x1400071d8  mov     qword ptr [rsi+18h], 7
0x1400071e0  mov     r8, rbx; Size
0x1400071e3  mov     rcx, rsi; void *
0x1400071e6  call    memcpy_0
0x1400071eb  xor     eax, eax
0x1400071ed  mov     [rbx+rsi], ax
0x1400071f1  jmp     short loc_140007247
0x1400071f3  mov     rax, rbx
0x1400071f6  or      rax, 7
0x1400071fa  cmp     rax, rcx
0x1400071fd  ja      short loc_14000720E
0x1400071ff  mov     edx, 0Ah
0x140007204  mov     rcx, rax
0x140007207  cmp     rax, rdx
0x14000720a  cmovb   rcx, rdx
0x14000720e  lea     rdx, [rsp+58h+arg_0]
0x140007213  mov     [rsp+58h+arg_0], rcx
0x140007218  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CAPEAGAEAV?$allocator@G@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<ushort> &,unsigned __int64 &)
0x14000721d  mov     rcx, [rsp+58h+arg_0]
0x140007222  mov     rdx, rbp; Src
0x140007225  mov     [rsi+10h], rbx
0x140007229  mov     rdi, rax
0x14000722c  mov     [rsi+18h], rcx
0x140007230  add     rbx, rbx
0x140007233  mov     rcx, rax; void *
0x140007236  mov     [rsi], rax
0x140007239  mov     r8, rbx; Size
0x14000723c  call    memcpy_0
0x140007241  xor     ecx, ecx
0x140007243  mov     [rbx+rdi], cx
0x140007247  mov     rax, rsi
0x14000724a  add     rsp, 38h
0x14000724e  pop     rdi
0x14000724f  pop     rsi
0x140007250  pop     rbp
0x140007251  pop     rbx
0x140007252  retn
0x140007253  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
