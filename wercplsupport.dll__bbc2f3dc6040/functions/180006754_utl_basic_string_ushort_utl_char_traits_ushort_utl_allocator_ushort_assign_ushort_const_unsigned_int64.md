# utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)

- ea: `0x180006754`
- end: `0x18000681f`
- name: `?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z`
- size: `203`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180004d28`
- `0x180005c28`
- `0x180005e04`

## callees

- `0x180001680`
- `0x180006604`
- `0x180006754`
- `0x180012172`
- `0x18001217e`

## pseudocode

```c
char __fastcall utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
        __int64 a1,
        const void *a2,
        unsigned __int64 a3)
{
  _QWORD *v3; // r14
  char v7; // bp
  unsigned __int64 v8; // rax
  __int64 v9; // rbx
  _WORD *v10; // rcx
  char *v11; // rbx
  size_t v12; // r15
  void *v13; // rsi
  void *v15[9]; // [rsp+20h] [rbp-48h] BYREF

  v3 = (_QWORD *)(a1 + 16);
  v7 = 1;
  if ( *(_QWORD *)a1 == a1 + 16 )
    v8 = 7;
  else
    v8 = (__int64)(*v3 - *(_QWORD *)a1) >> 1;
  if ( a3 > v8 )
  {
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_GrowAlloc(
      a1,
      v15,
      a3);
    v11 = (char *)v15[0];
    if ( v15[0] )
    {
      v12 = 2 * a3;
      memcpy_0(v15[0], a2, v12);
      *(_WORD *)&v11[v12] = 0;
      v13 = v15[1];
      if ( *(_QWORD **)a1 != v3 )
        operator delete(*(void **)a1);
      *(_QWORD *)a1 = v11;
      *(_QWORD *)(a1 + 8) = &v11[v12];
      *v3 = &v11[2 * ((__int64)v13 - 1)];
    }
    else
    {
      return 0;
    }
  }
  else
  {
    v9 = 2 * a3;
    memmove_0(*(void **)a1, a2, 2 * a3);
    v10 = (_WORD *)(v9 + *(_QWORD *)a1);
    *(_QWORD *)(a1 + 8) = v10;
    *v10 = 0;
  }
  return v7;
}

```

## disassembly

```asm
0x180006754  push    rbx
0x180006756  push    rbp
0x180006757  push    rsi
0x180006758  push    rdi
0x180006759  push    r12
0x18000675b  push    r14
0x18000675d  push    r15
0x18000675f  sub     rsp, 30h
0x180006763  lea     r14, [rcx+10h]
0x180006767  mov     r15, r8
0x18000676a  mov     r12, rdx
0x18000676d  mov     rdi, rcx
0x180006770  mov     bpl, 1
0x180006773  cmp     [rcx], r14
0x180006776  jnz     short loc_18000677F
0x180006778  mov     eax, 7
0x18000677d  jmp     short loc_180006788
0x18000677f  mov     rax, [r14]
0x180006782  sub     rax, [rcx]
0x180006785  sar     rax, 1
0x180006788  cmp     r15, rax
0x18000678b  ja      short loc_1800067AD
0x18000678d  mov     rcx, [rcx]; void *
0x180006790  lea     rbx, [r8+r8]
0x180006794  mov     r8, rbx; Size
0x180006797  call    memmove_0
0x18000679c  mov     rcx, [rdi]
0x18000679f  add     rcx, rbx
0x1800067a2  xor     esi, esi
0x1800067a4  mov     [rdi+8], rcx
0x1800067a8  mov     [rcx], si
0x1800067ab  jmp     short loc_18000680D
0x1800067ad  lea     rdx, [rsp+68h+var_48]
0x1800067b2  call    ?_GrowAlloc@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAA?AU?$pair@PEAG_K@2@_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_GrowAlloc(unsigned __int64)
0x1800067b7  mov     rbx, [rsp+68h+var_48]
0x1800067bc  xor     esi, esi
0x1800067be  test    rbx, rbx
0x1800067c1  jz      short loc_18000680A
0x1800067c3  add     r15, r15
0x1800067c6  mov     rdx, r12; Src
0x1800067c9  mov     r8, r15; Size
0x1800067cc  mov     rcx, rbx; void *
0x1800067cf  call    memcpy_0
0x1800067d4  mov     [r15+rbx], si
0x1800067d9  mov     rsi, [rsp+68h+var_40]
0x1800067de  cmp     [rdi], r14
0x1800067e1  jz      short loc_1800067F2
0x1800067e3  mov     rcx, [rdi]; Block
0x1800067e6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800067ed  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800067f2  lea     rax, [r15+rbx]
0x1800067f6  mov     [rdi], rbx
0x1800067f9  mov     [rdi+8], rax
0x1800067fd  lea     rax, [rsi-1]
0x180006801  lea     rax, [rbx+rax*2]
0x180006805  mov     [r14], rax
0x180006808  jmp     short loc_18000680D
0x18000680a  mov     bpl, sil
0x18000680d  mov     al, bpl
0x180006810  add     rsp, 30h
0x180006814  pop     r15
0x180006816  pop     r14
0x180006818  pop     r12
0x18000681a  pop     rdi
0x18000681b  pop     rsi
0x18000681c  pop     rbp
0x18000681d  pop     rbx
0x18000681e  retn
```
