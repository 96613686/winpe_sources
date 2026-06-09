# utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)

- ea: `0x1800095d0`
- end: `0x1800096a1`
- name: `?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z`
- size: `209`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `6`
- tags: ``

## callers

- `0x1800095a8`
- `0x18000e18c`
- `0x18000e440`
- `0x18000e6a4`
- `0x18000ec8c`
- `0x180010df0`

## callees

- `0x180009408`
- `0x180009530`
- `0x1800095d0`
- `0x18000977c`
- `0x180016c06`
- `0x180016c12`

## pseudocode

```c
char __fastcall utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
        __int64 a1,
        const void *a2,
        unsigned __int64 a3)
{
  __int64 v5; // rbx
  unsigned __int64 v7; // r14
  char v8; // bp
  const void *v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // rbx
  _WORD *v14; // r12
  size_t v15; // rbx
  void *v16[2]; // [rsp+20h] [rbp-58h] BYREF

  v5 = (__int64)(*(_QWORD *)(a1 + 8) - *(_QWORD *)a1) >> 1;
  v7 = v5 + a3;
  if ( v5 + a3 >= a3 )
  {
    v8 = 1;
    if ( v7 <= utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::capacity(
                 a1,
                 a2) )
    {
      v13 = 2 * v12;
      memmove_0(*(void **)(v11 + 8), v10, 2 * v12);
      *(_QWORD *)(a1 + 8) += v13;
      **(_WORD **)(a1 + 8) = 0;
      return v8;
    }
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_GrowAlloc(
      v11,
      v16,
      v7);
    v14 = v16[0];
    if ( v16[0] )
    {
      v15 = v5;
      memcpy_0(v16[0], *(const void **)a1, v15 * 2);
      memcpy_0(&v14[v15], a2, 2 * a3);
      v14[v7] = 0;
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Reinit(
        a1,
        v16,
        v7);
      return v8;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800095d0  push    rbx
0x1800095d2  push    rbp
0x1800095d3  push    rsi
0x1800095d4  push    rdi
0x1800095d5  push    r12
0x1800095d7  push    r13
0x1800095d9  push    r14
0x1800095db  push    r15
0x1800095dd  sub     rsp, 38h
0x1800095e1  mov     rbx, [rcx+8]
0x1800095e5  mov     r15, r8
0x1800095e8  sub     rbx, [rcx]
0x1800095eb  mov     r13, rdx
0x1800095ee  sar     rbx, 1
0x1800095f1  mov     rsi, rcx
0x1800095f4  lea     r14, [rbx+r8]
0x1800095f8  cmp     r14, r8
0x1800095fb  jnb     short loc_180009616
0x1800095fd  xor     edi, edi
0x1800095ff  mov     bpl, dil
0x180009602  mov     al, bpl
0x180009605  add     rsp, 38h
0x180009609  pop     r15
0x18000960b  pop     r14
0x18000960d  pop     r13
0x18000960f  pop     r12
0x180009611  pop     rdi
0x180009612  pop     rsi
0x180009613  pop     rbp
0x180009614  pop     rbx
0x180009615  retn
0x180009616  mov     bpl, 1
0x180009619  call    ?capacity@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEBA_KXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::capacity(void)
0x18000961e  cmp     r14, rax
0x180009621  ja      short loc_180009642
0x180009623  mov     rcx, [rcx+8]; void *
0x180009627  lea     rbx, [r8+r8]
0x18000962b  mov     r8, rbx; Size
0x18000962e  call    memmove_0
0x180009633  add     [rsi+8], rbx
0x180009637  mov     rax, [rsi+8]
0x18000963b  xor     edi, edi
0x18000963d  mov     [rax], di
0x180009640  jmp     short loc_180009602
0x180009642  mov     r8, r14
0x180009645  lea     rdx, [rsp+78h+var_58]
0x18000964a  call    ?_GrowAlloc@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAA?AU?$pair@PEAG_K@2@_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_GrowAlloc(unsigned __int64)
0x18000964f  mov     r12, [rsp+78h+var_58]
0x180009654  xor     edi, edi
0x180009656  test    r12, r12
0x180009659  jz      short loc_1800095FF
0x18000965b  mov     rdx, [rsi]; Src
0x18000965e  add     rbx, rbx
0x180009661  mov     r8, rbx; Size
0x180009664  mov     rcx, r12; void *
0x180009667  call    memcpy_0
0x18000966c  lea     r8, [r15+r15]; Size
0x180009670  mov     rdx, r13; Src
0x180009673  lea     rcx, [rbx+r12]; void *
0x180009677  call    memcpy_0
0x18000967c  movaps  xmm0, xmmword ptr [rsp+78h+var_58]
0x180009681  lea     rdx, [rsp+78h+var_58]
0x180009686  mov     r8, r14
0x180009689  movdqa  xmmword ptr [rsp+78h+var_58], xmm0
0x18000968f  mov     rcx, rsi
0x180009692  mov     [r12+r14*2], di
0x180009697  call    ?_Reinit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXU?$pair@PEAG_K@2@_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Reinit(utl::pair<ushort *,unsigned __int64>,unsigned __int64)
0x18000969c  jmp     loc_180009602
```
