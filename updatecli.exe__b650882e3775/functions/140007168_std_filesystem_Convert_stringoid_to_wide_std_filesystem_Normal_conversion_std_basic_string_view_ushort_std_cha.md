# std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::basic_string_view<ushort,std::char_traits<ushort>>,std::filesystem::_Normal_conversion)

- ea: `0x140007168`
- end: `0x140007239`
- name: `??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@V?$basic_string_view@GU?$char_traits@G@std@@@1@U_Normal_conversion@01@@Z`
- size: `209`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x140007ea8`
- `0x1400093c0`
- `0x14000953c`
- `0x140009608`
- `0x14000a6a8`

## callees

- `0x140007000`
- `0x140007168`
- `0x14000a2dc`
- `0x14000ac74`

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
0x140007168  mov     [rsp+arg_0], rcx
0x14000716d  push    rbx
0x14000716e  push    rbp
0x14000716f  push    rsi
0x140007170  push    rdi
0x140007171  sub     rsp, 38h
0x140007175  mov     rbx, [rdx+8]
0x140007179  xorps   xmm0, xmm0
0x14000717c  movups  xmmword ptr [rcx], xmm0
0x14000717f  mov     qword ptr [rcx+10h], 0
0x140007187  mov     rsi, rcx
0x14000718a  mov     qword ptr [rcx+18h], 0
0x140007192  mov     rcx, 7FFFFFFFFFFFFFFEh
0x14000719c  cmp     rbx, rcx
0x14000719f  ja      loc_140007233
0x1400071a5  mov     rbp, [rdx]
0x1400071a8  cmp     rbx, 7
0x1400071ac  ja      short loc_1400071D3
0x1400071ae  mov     [rsi+10h], rbx
0x1400071b2  mov     rdx, rbp; Src
0x1400071b5  add     rbx, rbx
0x1400071b8  mov     qword ptr [rsi+18h], 7
0x1400071c0  mov     r8, rbx; Size
0x1400071c3  mov     rcx, rsi; void *
0x1400071c6  call    memcpy_0
0x1400071cb  xor     eax, eax
0x1400071cd  mov     [rbx+rsi], ax
0x1400071d1  jmp     short loc_140007227
0x1400071d3  mov     rax, rbx
0x1400071d6  or      rax, 7
0x1400071da  cmp     rax, rcx
0x1400071dd  ja      short loc_1400071EE
0x1400071df  mov     edx, 0Ah
0x1400071e4  mov     rcx, rax
0x1400071e7  cmp     rax, rdx
0x1400071ea  cmovb   rcx, rdx
0x1400071ee  lea     rdx, [rsp+58h+arg_0]
0x1400071f3  mov     [rsp+58h+arg_0], rcx
0x1400071f8  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CAPEAGAEAV?$allocator@G@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<ushort> &,unsigned __int64 &)
0x1400071fd  mov     rcx, [rsp+58h+arg_0]
0x140007202  mov     rdx, rbp; Src
0x140007205  mov     [rsi+10h], rbx
0x140007209  mov     rdi, rax
0x14000720c  mov     [rsi+18h], rcx
0x140007210  add     rbx, rbx
0x140007213  mov     rcx, rax; void *
0x140007216  mov     [rsi], rax
0x140007219  mov     r8, rbx; Size
0x14000721c  call    memcpy_0
0x140007221  xor     ecx, ecx
0x140007223  mov     [rbx+rdi], cx
0x140007227  mov     rax, rsi
0x14000722a  add     rsp, 38h
0x14000722e  pop     rdi
0x14000722f  pop     rsi
0x140007230  pop     rbp
0x140007231  pop     rbx
0x140007232  retn
0x140007233  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
