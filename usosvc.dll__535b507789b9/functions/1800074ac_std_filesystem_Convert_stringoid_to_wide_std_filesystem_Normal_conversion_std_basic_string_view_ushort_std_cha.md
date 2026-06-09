# std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::basic_string_view<ushort,std::char_traits<ushort>>,std::filesystem::_Normal_conversion)

- ea: `0x1800074ac`
- end: `0x18000757d`
- name: `??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@V?$basic_string_view@GU?$char_traits@G@std@@@1@U_Normal_conversion@01@@Z`
- size: `209`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x1800081ec`
- `0x180009540`
- `0x180009600`
- `0x1800096cc`
- `0x1800097fc`

## callees

- `0x180007344`
- `0x1800074ac`
- `0x18000a348`
- `0x18000e454`

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
0x1800074ac  mov     [rsp+arg_0], rcx
0x1800074b1  push    rbx
0x1800074b2  push    rbp
0x1800074b3  push    rsi
0x1800074b4  push    rdi
0x1800074b5  sub     rsp, 38h
0x1800074b9  mov     rbx, [rdx+8]
0x1800074bd  xorps   xmm0, xmm0
0x1800074c0  movups  xmmword ptr [rcx], xmm0
0x1800074c3  mov     qword ptr [rcx+10h], 0
0x1800074cb  mov     rsi, rcx
0x1800074ce  mov     qword ptr [rcx+18h], 0
0x1800074d6  mov     rcx, 7FFFFFFFFFFFFFFEh
0x1800074e0  cmp     rbx, rcx
0x1800074e3  ja      loc_180007577
0x1800074e9  mov     rbp, [rdx]
0x1800074ec  cmp     rbx, 7
0x1800074f0  ja      short loc_180007517
0x1800074f2  mov     [rsi+10h], rbx
0x1800074f6  mov     rdx, rbp; Src
0x1800074f9  add     rbx, rbx
0x1800074fc  mov     qword ptr [rsi+18h], 7
0x180007504  mov     r8, rbx; Size
0x180007507  mov     rcx, rsi; void *
0x18000750a  call    memcpy_0
0x18000750f  xor     eax, eax
0x180007511  mov     [rbx+rsi], ax
0x180007515  jmp     short loc_18000756B
0x180007517  mov     rax, rbx
0x18000751a  or      rax, 7
0x18000751e  cmp     rax, rcx
0x180007521  ja      short loc_180007532
0x180007523  mov     edx, 0Ah
0x180007528  mov     rcx, rax
0x18000752b  cmp     rax, rdx
0x18000752e  cmovb   rcx, rdx
0x180007532  lea     rdx, [rsp+58h+arg_0]
0x180007537  mov     [rsp+58h+arg_0], rcx
0x18000753c  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CAPEAGAEAV?$allocator@G@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<ushort> &,unsigned __int64 &)
0x180007541  mov     rcx, [rsp+58h+arg_0]
0x180007546  mov     rdx, rbp; Src
0x180007549  mov     [rsi+10h], rbx
0x18000754d  mov     rdi, rax
0x180007550  mov     [rsi+18h], rcx
0x180007554  add     rbx, rbx
0x180007557  mov     rcx, rax; void *
0x18000755a  mov     [rsi], rax
0x18000755d  mov     r8, rbx; Size
0x180007560  call    memcpy_0
0x180007565  xor     ecx, ecx
0x180007567  mov     [rbx+rdi], cx
0x18000756b  mov     rax, rsi
0x18000756e  add     rsp, 38h
0x180007572  pop     rdi
0x180007573  pop     rsi
0x180007574  pop     rbp
0x180007575  pop     rbx
0x180007576  retn
0x180007577  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
