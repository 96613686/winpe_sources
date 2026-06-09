# utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)

- ea: `0x14000d6e8`
- end: `0x14000d7bc`
- name: `?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z`
- size: `212`
- prototype: ``
- caller_count: `33`
- callee_count: `6`
- tags: ``

## callers

- `0x140003b50`
- `0x140006008`
- `0x140006a30`
- `0x140006de0`
- `0x14000cc80`
- `0x14000d2ec`
- `0x14000d314`
- `0x14000d570`
- `0x14000d62c`
- `0x14001291c`
- `0x140013658`
- `0x140015cac`
- `0x14001663c`
- `0x140019094`
- `0x14001915c`
- `0x14001aa58`
- `0x14001d828`
- `0x14001e0c0`
- `0x140029664`
- `0x14002987c`
- `0x14002a55c`
- `0x14002a814`
- `0x14002ab70`
- `0x14002bd08`
- `0x14002cc9c`
- `0x14002d1c0`
- `0x14002e0cc`
- `0x14002f018`
- `0x14002f0d8`
- `0x14002f198`
- `0x14002f284`
- `0x14002f4a8`
- `0x14002f904`

## callees

- `0x1400038fc`
- `0x140008100`
- `0x14000d6e8`
- `0x14001b2d4`
- `0x140031828`
- `0x140031834`

## pseudocode

```c
char __fastcall utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
        __int64 a1,
        const void *a2,
        unsigned __int64 a3)
{
  __int64 v5; // rbx
  unsigned __int64 v7; // r14
  char v8; // bp
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // rbx
  _WORD *v13; // r12
  size_t v14; // rbx
  void *v15[2]; // [rsp+20h] [rbp-58h] BYREF

  v5 = (__int64)(*(_QWORD *)(a1 + 8) - *(_QWORD *)a1) >> 1;
  v7 = v5 + a3;
  if ( v5 + a3 >= a3 )
  {
    v8 = 1;
    if ( v7 <= utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::capacity(a1) )
    {
      v12 = 2 * v11;
      memmove_0(*(void **)(v10 + 8), a2, 2 * v11);
      *(_QWORD *)(a1 + 8) += v12;
      **(_WORD **)(a1 + 8) = 0;
      return v8;
    }
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_GrowAlloc(v10, v15, v7);
    v13 = v15[0];
    if ( v15[0] )
    {
      v14 = v5;
      memcpy_0(v15[0], *(const void **)a1, v14 * 2);
      memcpy_0(&v13[v14], a2, 2 * a3);
      v13[v7] = 0;
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Reinit(a1, v15, v7);
      return v8;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14000d6e8  push    rbx
0x14000d6ea  push    rbp
0x14000d6eb  push    rsi
0x14000d6ec  push    rdi
0x14000d6ed  push    r12
0x14000d6ef  push    r13
0x14000d6f1  push    r14
0x14000d6f3  push    r15
0x14000d6f5  sub     rsp, 38h
0x14000d6f9  mov     rbx, [rcx+8]
0x14000d6fd  mov     r15, r8
0x14000d700  sub     rbx, [rcx]
0x14000d703  mov     r13, rdx
0x14000d706  sar     rbx, 1
0x14000d709  mov     rsi, rcx
0x14000d70c  lea     r14, [rbx+r8]
0x14000d710  cmp     r14, r8
0x14000d713  jnb     short loc_14000D72E
0x14000d715  xor     edi, edi
0x14000d717  mov     bpl, dil
0x14000d71a  mov     al, bpl
0x14000d71d  add     rsp, 38h
0x14000d721  pop     r15
0x14000d723  pop     r14
0x14000d725  pop     r13
0x14000d727  pop     r12
0x14000d729  pop     rdi
0x14000d72a  pop     rsi
0x14000d72b  pop     rbp
0x14000d72c  pop     rbx
0x14000d72d  retn
0x14000d72e  mov     bpl, 1
0x14000d731  call    ?capacity@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEBA_KXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::capacity(void)
0x14000d736  cmp     r14, rax
0x14000d739  ja      short loc_14000D75D
0x14000d73b  mov     rcx, [rcx+8]; void *
0x14000d73f  lea     rbx, [r8+r8]
0x14000d743  mov     r8, rbx; Size
0x14000d746  mov     rdx, r13; Src
0x14000d749  call    memmove_0
0x14000d74e  add     [rsi+8], rbx
0x14000d752  mov     rax, [rsi+8]
0x14000d756  xor     edi, edi
0x14000d758  mov     [rax], di
0x14000d75b  jmp     short loc_14000D71A
0x14000d75d  mov     r8, r14
0x14000d760  lea     rdx, [rsp+78h+var_58]
0x14000d765  call    ?_GrowAlloc@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAA?AU?$pair@PEA_W_K@2@_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_GrowAlloc(unsigned __int64)
0x14000d76a  mov     r12, [rsp+78h+var_58]
0x14000d76f  xor     edi, edi
0x14000d771  test    r12, r12
0x14000d774  jz      short loc_14000D717
0x14000d776  mov     rdx, [rsi]; Src
0x14000d779  add     rbx, rbx
0x14000d77c  mov     r8, rbx; Size
0x14000d77f  mov     rcx, r12; void *
0x14000d782  call    memcpy_0
0x14000d787  lea     r8, [r15+r15]; Size
0x14000d78b  mov     rdx, r13; Src
0x14000d78e  lea     rcx, [rbx+r12]; void *
0x14000d792  call    memcpy_0
0x14000d797  movaps  xmm0, xmmword ptr [rsp+78h+var_58]
0x14000d79c  lea     rdx, [rsp+78h+var_58]
0x14000d7a1  mov     r8, r14
0x14000d7a4  movdqa  xmmword ptr [rsp+78h+var_58], xmm0
0x14000d7aa  mov     rcx, rsi
0x14000d7ad  mov     [r12+r14*2], di
0x14000d7b2  call    ?_Reinit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXU?$pair@PEA_W_K@2@_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Reinit(utl::pair<wchar_t *,unsigned __int64>,unsigned __int64)
0x14000d7b7  jmp     loc_14000D71A
```
