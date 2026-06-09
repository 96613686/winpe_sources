# _RNvMs_NtCs1fYFp9lPHeY_14handle_manager16GdiHandleManagerNtB4_16GdiHandleManager6Create

- ea: `0x14000a400`
- end: `0x14000a5db`
- name: `_RNvMs_NtCs1fYFp9lPHeY_14handle_manager16GdiHandleManagerNtB4_16GdiHandleManager6Create`
- size: `475`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, unsigned int, char)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1400036c0`

## callees

- `0x140005590`
- `0x1400096c0`
- `0x14000a400`
- `0x14001790a`
- `0x140017940`
- `0x140017a10`
- `0x140018650`
- `0x140019140`

## pseudocode

```c
__int64 __fastcall RNvMs_NtCs1fYFp9lPHeY_14handle_manager16GdiHandleManagerNtB4_16GdiHandleManager6Create(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        unsigned int a4,
        char a5)
{
  char v6; // r12
  __int64 v10; // rax
  __int64 v11; // rbx
  __int64 v12; // rdi
  int v13; // eax
  _QWORD *v14; // rbx
  __int64 v16; // [rsp+0h] [rbp-A8h] BYREF
  __int128 v17; // [rsp+20h] [rbp-88h]
  int v18; // [rsp+30h] [rbp-78h]
  __int64 v19; // [rsp+40h] [rbp-68h] BYREF
  int v20; // [rsp+48h] [rbp-60h]
  __int128 v21; // [rsp+4Ch] [rbp-5Ch]
  int v22; // [rsp+5Ch] [rbp-4Ch]
  __int64 v23; // [rsp+60h] [rbp-48h]

  if ( a4 < a2 && a4 < 0x10000 )
    RNvNtCs9MWeMO1rkJG_4core9panicking9panic_fmt(
      "Bad entry countLayoutsizealignCapacityOverflowAllocErrorlayoutnon_exhaustive()",
      31,
      &off_14001B368);
  v6 = a5;
  if ( !a5 )
    RNvNtCs9MWeMO1rkJG_4core9panicking9panic_fmt(
      "Bad startIndexBad entry countLayoutsizealignCapacityOverflowAllocErrorlayoutnon_exhaustive()",
      29,
      &off_14001B350);
  v10 = Win32AllocPool_0(72, 1668114503);
  if ( !v10 )
  {
    *(_QWORD *)a1 = 0xE00000001LL;
    goto LABEL_19;
  }
  v11 = v10;
  v12 = v10;
  *(_QWORD *)v10 = 0;
  *(_QWORD *)(v10 + 8) = 4;
  *(_QWORD *)(v10 + 16) = 0;
  *(_QWORD *)(v10 + 24) = 0x8000000000000000uLL;
  *(_QWORD *)(v10 + 56) = 0;
  *(_DWORD *)(v10 + 64) = a2;
  *(_BYTE *)(v10 + 68) = a5;
  RNvMNtCs1fYFp9lPHeY_14handle_manager23GdiHandleEntryDirectoryNtB2_23GdiHandleEntryDirectory6Create(&v19, a3, a4);
  v13 = v20;
  if ( __OFSUB__(-v19, 1) )
  {
    if ( !v20 )
    {
LABEL_11:
      *(_QWORD *)(a1 + 8) = v12;
      *(_DWORD *)a1 = 0;
      goto LABEL_19;
    }
  }
  else
  {
    v18 = v22;
    v17 = v21;
    *(_QWORD *)(v12 + 24) = v19;
    *(_DWORD *)(v12 + 32) = v13;
    *(_OWORD *)(v12 + 36) = v17;
    *(_DWORD *)(v12 + 52) = v18;
    while ( (unsigned __int8)RNvMs_NtCs1fYFp9lPHeY_14handle_manager16GdiHandleManagerNtB4_16GdiHandleManager17AcquireEntryIndex(
                               v12,
                               (unsigned int *)&v19) )
    {
      if ( !--v6 )
        goto LABEL_11;
    }
    v13 = 14;
  }
  v14 = (_QWORD *)(v11 + 24);
  *(_DWORD *)(a1 + 4) = v13;
  *(_DWORD *)a1 = 1;
  if ( *v14 != 0x8000000000000000uLL )
  {
    RNvXsi_NtCsexo9QDNEsji_5alloc3vecINtB5_3VecINtNtCs9MWeMO1rkJG_4core6option6OptionINtNtB7_5boxed3BoxNtNtCs1fYFp9lPHeY_14handle_manager19GdiHandleEntryTable19GdiHandleEntryTableINtCs1EG24RjTlfM_9gdi_alloc15TaggedAllocatorKm63746547_EEEB2N_ENtNtNtBK_3ops4drop4Drop4dropB1D_(v14);
    if ( *v14 )
      Win32FreePool_0(*(_QWORD *)(v12 + 32));
  }
  if ( *(_QWORD *)v12 )
    Win32FreePool_0(*(_QWORD *)(v12 + 8));
  Win32FreePool_0(v12);
LABEL_19:
  if ( _security_cookie != ((unsigned __int64)&v16 ^ v23) )
    JUMPOUT(0x14000A5DALL);
  return a1;
}

```

## disassembly

```asm
0x14000a400  push    r15
0x14000a402  push    r14
0x14000a404  push    r13
0x14000a406  push    r12
0x14000a408  push    rsi
0x14000a409  push    rdi
0x14000a40a  push    rbp
0x14000a40b  push    rbx
0x14000a40c  sub     rsp, 68h
0x14000a410  mov     rsi, rcx
0x14000a413  mov     rax, cs:__security_cookie
0x14000a41a  xor     rax, rsp
0x14000a41d  mov     [rsp+0A8h+var_48], rax
0x14000a422  cmp     r9d, 10000h
0x14000a429  setb    al
0x14000a42c  cmp     r9d, edx
0x14000a42f  setb    cl
0x14000a432  test    al, cl
0x14000a434  jnz     loc_14000A5B5
0x14000a43a  movzx   r12d, [rsp+0A8h+arg_20]
0x14000a443  test    r12b, r12b
0x14000a446  jz      loc_14000A59D
0x14000a44c  mov     ebp, r9d
0x14000a44f  mov     r14, r8
0x14000a452  mov     r15d, edx
0x14000a455  mov     ecx, 48h ; 'H'
0x14000a45a  mov     edx, 636D6847h
0x14000a45f  call    Win32AllocPool_0
0x14000a464  test    rax, rax
0x14000a467  jz      short loc_14000A4CB
0x14000a469  mov     rbx, rax
0x14000a46c  mov     rdi, rax
0x14000a46f  mov     r13, 8000000000000000h
0x14000a479  mov     qword ptr [rbx], 0
0x14000a480  mov     qword ptr [rbx+8], 4
0x14000a488  mov     qword ptr [rbx+10h], 0
0x14000a490  mov     [rbx+18h], r13
0x14000a494  mov     qword ptr [rbx+38h], 0
0x14000a49c  mov     [rbx+40h], r15d
0x14000a4a0  mov     [rbx+44h], r12b
0x14000a4a4  lea     rcx, [rsp+0A8h+var_68]
0x14000a4a9  mov     rdx, r14
0x14000a4ac  mov     r8d, ebp
0x14000a4af  call    _RNvMNtCs1fYFp9lPHeY_14handle_manager23GdiHandleEntryDirectoryNtB2_23GdiHandleEntryDirectory6Create
0x14000a4b4  mov     rcx, [rsp+0A8h+var_68]
0x14000a4b9  mov     rax, rcx
0x14000a4bc  neg     rax
0x14000a4bf  mov     eax, [rsp+0A8h+var_60]
0x14000a4c3  jno     short loc_14000A4DD
0x14000a4c5  test    eax, eax
0x14000a4c7  jnz     short loc_14000A535
0x14000a4c9  jmp     short loc_14000A524
0x14000a4cb  mov     rax, 0E00000001h
0x14000a4d5  mov     [rsi], rax
0x14000a4d8  jmp     loc_14000A575
0x14000a4dd  mov     edx, [rsp+0A8h+var_4C]
0x14000a4e1  mov     [rsp+0A8h+var_78], edx
0x14000a4e5  movups  xmm0, [rsp+0A8h+var_5C]
0x14000a4ea  movaps  [rsp+0A8h+var_88], xmm0
0x14000a4ef  mov     [rdi+18h], rcx
0x14000a4f3  mov     [rdi+20h], eax
0x14000a4f6  movaps  xmm0, [rsp+0A8h+var_88]
0x14000a4fb  movups  xmmword ptr [rdi+24h], xmm0
0x14000a4ff  mov     eax, [rsp+0A8h+var_78]
0x14000a503  mov     [rdi+34h], eax
0x14000a506  lea     r14, [rsp+0A8h+var_68]
0x14000a50b  nop     dword ptr [rax+rax+00h]
0x14000a510  mov     rcx, rdi
0x14000a513  mov     rdx, r14
0x14000a516  call    _RNvMs_NtCs1fYFp9lPHeY_14handle_manager16GdiHandleManagerNtB4_16GdiHandleManager17AcquireEntryIndex
0x14000a51b  test    al, al
0x14000a51d  jz      short loc_14000A530
0x14000a51f  dec     r12b
0x14000a522  jnz     short loc_14000A510
0x14000a524  mov     [rsi+8], rdi
0x14000a528  mov     dword ptr [rsi], 0
0x14000a52e  jmp     short loc_14000A575
0x14000a530  mov     eax, 0Eh
0x14000a535  add     rbx, 18h
0x14000a539  mov     [rsi+4], eax
0x14000a53c  mov     dword ptr [rsi], 1
0x14000a542  cmp     [rbx], r13
0x14000a545  jz      short loc_14000A55E
0x14000a547  mov     rcx, rbx
0x14000a54a  call    _RNvXsi_NtCsexo9QDNEsji_5alloc3vecINtB5_3VecINtNtCs9MWeMO1rkJG_4core6option6OptionINtNtB7_5boxed3BoxNtNtCs1fYFp9lPHeY_14handle_manager19GdiHandleEntryTable19GdiHandleEntryTableINtCs1EG24RjTlfM_9gdi_alloc15TaggedAllocatorKm63746547_EEEB2N_ENtNtNtBK_3ops4drop4Drop4dropB1D_
0x14000a54f  cmp     qword ptr [rbx], 0
0x14000a553  jz      short loc_14000A55E
0x14000a555  mov     rcx, [rdi+20h]
0x14000a559  call    Win32FreePool_0
0x14000a55e  cmp     qword ptr [rdi], 0
0x14000a562  jz      short loc_14000A56D
0x14000a564  mov     rcx, [rdi+8]
0x14000a568  call    Win32FreePool_0
0x14000a56d  mov     rcx, rdi
0x14000a570  call    Win32FreePool_0
0x14000a575  mov     rax, [rsp+0A8h+var_48]
0x14000a57a  xor     rax, rsp
0x14000a57d  mov     rcx, cs:__security_cookie
0x14000a584  cmp     rcx, rax
0x14000a587  jnz     short loc_14000A5CD
0x14000a589  mov     rax, rsi
0x14000a58c  add     rsp, 68h
0x14000a590  pop     rbx
0x14000a591  pop     rbp
0x14000a592  pop     rdi
0x14000a593  pop     rsi
0x14000a594  pop     r12
0x14000a596  pop     r13
0x14000a598  pop     r14
0x14000a59a  pop     r15
0x14000a59c  retn
0x14000a59d  lea     rcx, aBadStartindexb; "Bad startIndexBad entry countLayoutsize"...
0x14000a5a4  lea     r8, off_14001B350; "handle_manager\\src\\GdiHandleManager.r"...
0x14000a5ab  mov     edx, 1Dh
0x14000a5b0  call    _RNvNtCs9MWeMO1rkJG_4core9panicking9panic_fmt
0x14000a5b5  lea     rcx, aBadStartindexb+0Eh; "Bad entry countLayoutsizealignCapacityO"...
0x14000a5bc  lea     r8, off_14001B368; "handle_manager\\src\\GdiHandleManager.r"...
0x14000a5c3  mov     edx, 1Fh
0x14000a5c8  call    _RNvNtCs9MWeMO1rkJG_4core9panicking9panic_fmt
0x14000a5cd  mov     rcx, [rsp+0A8h+var_48]
0x14000a5d2  xor     rcx, rsp; StackCookie
0x14000a5d5  call    __security_check_cookie
```
