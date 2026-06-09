# _RNvXsi_NtCsexo9QDNEsji_5alloc3vecINtB5_3VecINtNtCs9MWeMO1rkJG_4core6option6OptionINtNtB7_5boxed3BoxNtNtCs1fYFp9lPHeY_14handle_manager19GdiHandleEntryTable19GdiHandleEntryTableINtCs1EG24RjTlfM_9gdi_alloc15TaggedAllocatorKm63746547_EEEB2N_ENtNtNtBK_3ops4drop4Drop4dropB1D_

- ea: `0x140005590`
- end: `0x14000565c`
- name: `_RNvXsi_NtCsexo9QDNEsji_5alloc3vecINtB5_3VecINtNtCs9MWeMO1rkJG_4core6option6OptionINtNtB7_5boxed3BoxNtNtCs1fYFp9lPHeY_14handle_manager19GdiHandleEntryTable19GdiHandleEntryTableINtCs1EG24RjTlfM_9gdi_alloc15TaggedAllocatorKm63746547_EEEB2N_ENtNtNtBK_3ops4drop4Drop4dropB1D_`
- size: `204`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140003740`
- `0x14000a400`
- `0x140019140`

## callees

- `0x140005590`
- `0x14001790a`

## pseudocode

```c
void __fastcall RNvXsi_NtCsexo9QDNEsji_5alloc3vecINtB5_3VecINtNtCs9MWeMO1rkJG_4core6option6OptionINtNtB7_5boxed3BoxNtNtCs1fYFp9lPHeY_14handle_manager19GdiHandleEntryTable19GdiHandleEntryTableINtCs1EG24RjTlfM_9gdi_alloc15TaggedAllocatorKm63746547_EEEB2N_ENtNtNtBK_3ops4drop4Drop4dropB1D_(
        __int64 a1)
{
  __int64 v1; // rdi
  __int64 v2; // rbx
  __int64 i; // r14
  __int64 v4; // rsi
  __int64 v5; // rax
  __int64 v6; // r15
  __int64 *v7; // r12

  v1 = *(_QWORD *)(a1 + 16);
  if ( v1 )
  {
    v2 = *(_QWORD *)(a1 + 8);
    for ( i = 0; i != v1; ++i )
    {
      v4 = *(_QWORD *)(v2 + 8 * i);
      if ( v4 )
      {
        v5 = *(_QWORD *)v4;
        if ( !__OFSUB__(-*(_QWORD *)v4, 1) )
        {
          v6 = *(_QWORD *)(v4 + 16);
          if ( v6 )
          {
            v7 = (__int64 *)(*(_QWORD *)(v4 + 8) + 8LL);
            do
            {
              if ( *(v7 - 1) )
                Win32FreePool_0(*v7);
              v7 += 3;
              --v6;
            }
            while ( v6 );
            v5 = *(_QWORD *)v4;
          }
          if ( v5 )
            Win32FreePool_0(*(_QWORD *)(v4 + 8));
        }
        if ( *(_BYTE *)(v4 + 56) == 1 )
        {
          if ( *(_QWORD *)(v4 + 48) )
            Win32FreePool_0(*(_QWORD *)(v4 + 32));
        }
        Win32FreePool_0(v4);
      }
    }
  }
}

```

## disassembly

```asm
0x140005590  push    r15
0x140005592  push    r14
0x140005594  push    r12
0x140005596  push    rsi
0x140005597  push    rdi
0x140005598  push    rbx
0x140005599  sub     rsp, 28h
0x14000559d  mov     rdi, [rcx+10h]
0x1400055a1  test    rdi, rdi
0x1400055a4  jz      loc_14000564E
0x1400055aa  mov     rbx, [rcx+8]
0x1400055ae  xor     r14d, r14d
0x1400055b1  jmp     short loc_1400055D0
0x1400055c0  mov     rcx, rsi
0x1400055c3  call    Win32FreePool_0
0x1400055c8  inc     r14
0x1400055cb  cmp     r14, rdi
0x1400055ce  jz      short loc_14000564E
0x1400055d0  mov     rsi, [rbx+r14*8]
0x1400055d4  test    rsi, rsi
0x1400055d7  jz      short loc_1400055C8
0x1400055d9  mov     rax, [rsi]
0x1400055dc  mov     rcx, rax
0x1400055df  neg     rcx
0x1400055e2  jo      short loc_14000562D
0x1400055e4  mov     r15, [rsi+10h]
0x1400055e8  test    r15, r15
0x1400055eb  jz      short loc_14000561F
0x1400055ed  mov     r12, [rsi+8]
0x1400055f1  add     r12, 8
0x1400055f5  jmp     short loc_140005609
0x140005600  add     r12, 18h
0x140005604  dec     r15
0x140005607  jz      short loc_14000561C
0x140005609  cmp     qword ptr [r12-8], 0
0x14000560f  jz      short loc_140005600
0x140005611  mov     rcx, [r12]
0x140005615  call    Win32FreePool_0
0x14000561a  jmp     short loc_140005600
0x14000561c  mov     rax, [rsi]
0x14000561f  test    rax, rax
0x140005622  jz      short loc_14000562D
0x140005624  mov     rcx, [rsi+8]
0x140005628  call    Win32FreePool_0
0x14000562d  movzx   eax, byte ptr [rsi+38h]
0x140005631  cmp     al, 2
0x140005633  jz      short loc_1400055C0
0x140005635  cmp     al, 1
0x140005637  jnz     short loc_1400055C0
0x140005639  cmp     qword ptr [rsi+30h], 0
0x14000563e  jz      short loc_1400055C0
0x140005640  mov     rcx, [rsi+20h]
0x140005644  call    Win32FreePool_0
0x140005649  jmp     loc_1400055C0
0x14000564e  add     rsp, 28h
0x140005652  pop     rbx
0x140005653  pop     rdi
0x140005654  pop     rsi
0x140005655  pop     r12
0x140005657  pop     r14
0x140005659  pop     r15
0x14000565b  retn
```
