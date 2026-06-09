# ScCacheFreeEnumItems

- ea: `0x1800374f4`
- end: `0x1800375cd`
- name: `ScCacheFreeEnumItems`
- size: `217`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180012d08`
- `0x180015728`
- `0x180030ba8`

## callees

- `0x18000a408`
- `0x18000a590`
- `0x180013734`
- `0x1800374f4`
- `0x18003d010`

## pseudocode

```c
__int64 __fastcall ScCacheFreeEnumItems(__int64 a1, __int64 a2, unsigned int a3)
{
  PVOID v6; // rcx
  unsigned int i; // ebx

  WppTraceIndent(a1, 0);
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids, WPP_pszIndent);
  }
  for ( i = 0; i < a3; ++i )
    (*(void (__fastcall **)(_QWORD))(a1 + 56))(*(_QWORD *)(a2 + 16LL * i + 8));
  if ( a2 )
    (*(void (__fastcall **)(__int64))(a1 + 56))(a2);
  WppTraceIndent((__int64)v6, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      44,
      (unsigned int)WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids,
      WPP_pszIndent,
      0);
  }
  return 0;
}

```

## disassembly

```asm
0x1800374f4  push    rbx
0x1800374f6  push    rbp
0x1800374f7  push    rsi
0x1800374f8  push    rdi
0x1800374f9  push    r14
0x1800374fb  sub     rsp, 30h
0x1800374ff  mov     rdi, rdx
0x180037502  mov     esi, r8d
0x180037505  xor     edx, edx
0x180037507  mov     rbp, rcx
0x18003750a  call    WppTraceIndent
0x18003750f  mov     rcx, cs:WPP_GLOBAL_Control
0x180037516  lea     r14, WPP_GLOBAL_Control
0x18003751d  cmp     rcx, r14
0x180037520  jz      short loc_18003754A
0x180037522  test    byte ptr [rcx+1Ch], 2
0x180037526  jz      short loc_18003754A
0x180037528  cmp     byte ptr [rcx+19h], 5
0x18003752c  jb      short loc_18003754A
0x18003752e  mov     r9, cs:WPP_pszIndent
0x180037535  lea     r8, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids
0x18003753c  mov     rcx, [rcx+10h]
0x180037540  mov     edx, 2Bh ; '+'
0x180037545  call    WPP_SF_s
0x18003754a  xor     ebx, ebx
0x18003754c  test    esi, esi
0x18003754e  jz      short loc_180037569
0x180037550  mov     rax, [rbp+38h]
0x180037554  mov     ecx, ebx
0x180037556  add     rcx, rcx
0x180037559  mov     rcx, [rdi+rcx*8+8]
0x18003755e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037563  inc     ebx
0x180037565  cmp     ebx, esi
0x180037567  jb      short loc_180037550
0x180037569  test    rdi, rdi
0x18003756c  jz      short loc_18003757A
0x18003756e  mov     rax, [rbp+38h]
0x180037572  mov     rcx, rdi
0x180037575  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003757a  mov     edx, 1
0x18003757f  call    WppTraceIndent
0x180037584  mov     rcx, cs:WPP_GLOBAL_Control
0x18003758b  cmp     rcx, r14
0x18003758e  jz      short loc_1800375C0
0x180037590  test    byte ptr [rcx+1Ch], 2
0x180037594  jz      short loc_1800375C0
0x180037596  cmp     byte ptr [rcx+19h], 5
0x18003759a  jb      short loc_1800375C0
0x18003759c  mov     r9, cs:WPP_pszIndent
0x1800375a3  lea     r8, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids
0x1800375aa  mov     rcx, [rcx+10h]
0x1800375ae  mov     edx, 2Ch ; ','
0x1800375b3  mov     [rsp+58h+var_38], 0
0x1800375bb  call    WPP_SF_sd
0x1800375c0  xor     eax, eax
0x1800375c2  add     rsp, 30h
0x1800375c6  pop     r14
0x1800375c8  pop     rdi
0x1800375c9  pop     rsi
0x1800375ca  pop     rbp
0x1800375cb  pop     rbx
0x1800375cc  retn
```
