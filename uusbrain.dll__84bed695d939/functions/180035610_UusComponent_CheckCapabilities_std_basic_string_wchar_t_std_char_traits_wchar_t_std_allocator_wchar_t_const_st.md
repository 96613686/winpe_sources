# UusComponent::CheckCapabilities(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::optional<std::filesystem::path>,std::optional<UusVersion>,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x180035610`
- end: `0x1800357e2`
- name: `?CheckCapabilities@UusComponent@@QEBA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$optional@Vpath@filesystem@std@@@3@V?$optional@VUusVersion@@@3@0@Z`
- size: `466`
- prototype: `char __fastcall(UusCapabilities *, __int64, __int64, __int64, _BYTE *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800394b8`

## callees

- `0x180028728`
- `0x180029644`
- `0x180034914`
- `0x180035610`
- `0x1800427d0`
- `0x180047a30`

## pseudocode

```c
char __fastcall UusComponent::CheckCapabilities(UusCapabilities *a1, __int64 a2, __int64 a3, __int64 a4, _BYTE *a5)
{
  __int64 v5; // rbx
  __int64 v6; // rdi
  UusCapabilities *v8; // r15
  char v9; // si
  int *v10; // r14
  int *v11; // r15
  __int64 v12; // rbx
  int v13; // r12d
  void **v15; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v16; // [rsp+38h] [rbp-C8h]
  char v17; // [rsp+40h] [rbp-C0h]
  _BYTE *v18; // [rsp+48h] [rbp-B8h]
  __int64 v19; // [rsp+50h] [rbp-B0h]
  __int64 v20; // [rsp+58h] [rbp-A8h]
  void ***v21; // [rsp+60h] [rbp-A0h]
  _BYTE *v22; // [rsp+68h] [rbp-98h]
  _QWORD v23[2]; // [rsp+70h] [rbp-90h] BYREF
  char v24; // [rsp+80h] [rbp-80h]
  _BYTE v25[32]; // [rsp+88h] [rbp-78h] BYREF
  char v26; // [rsp+A8h] [rbp-58h]
  void ***v27; // [rsp+B0h] [rbp-50h]
  _BYTE v28[32]; // [rsp+B8h] [rbp-48h] BYREF
  char v29; // [rsp+D8h] [rbp-28h]
  __int64 v30; // [rsp+E0h] [rbp-20h]
  __int64 v31; // [rsp+E8h] [rbp-18h]

  v5 = a4;
  v19 = a4;
  v6 = a3;
  v20 = a3;
  v8 = a1;
  v30 = a3;
  v31 = a4;
  v18 = a5;
  v21 = &v15;
  v17 = 0;
  if ( *(_BYTE *)(a4 + 16) )
  {
    v15 = &UusVersion::`vftable';
    v16 = *(_QWORD *)(a4 + 8);
    v17 = 1;
  }
  v27 = &v15;
  v22 = v25;
  LOBYTE(a1) = 0;
  v26 = 0;
  if ( *(_BYTE *)(a3 + 32) )
  {
    std::wstring::wstring((__int64)v25, a3);
    LOBYTE(a1) = 1;
    v26 = 1;
  }
  v22 = v25;
  v9 = 1;
  v10 = (int *)*((_QWORD *)v8 + 4);
  v11 = (int *)*((_QWORD *)v8 + 5);
  if ( v10 != v11 )
  {
    v12 = (__int64)v18;
    do
    {
      v13 = *v10;
      v21 = (void ***)v23;
      v24 = 0;
      if ( v17 )
      {
        v23[0] = &UusVersion::`vftable';
        v23[1] = v16;
        v24 = 1;
      }
      v18 = v28;
      v29 = 0;
      if ( (_BYTE)a1 )
      {
        std::wstring::wstring((__int64)v28, (__int64)v25);
        v29 = 1;
      }
      v9 = UusCapabilities::Check(a1, v13, a2, (__int64)v28, (__int64)v23, v12) ? v9 : 0;
      ++v10;
      LOBYTE(a1) = v26;
    }
    while ( v10 != v11 );
    v5 = v19;
    v6 = v20;
  }
  if ( (_BYTE)a1 )
    std::wstring::_Tidy_deallocate((__int64)v25);
  if ( v17 )
    ((void (__fastcall *)(void ***, _QWORD))*v15)(&v15, 0);
  if ( *(_BYTE *)(v6 + 32) )
    std::wstring::_Tidy_deallocate(v6);
  if ( *(_BYTE *)(v5 + 16) )
    (**(void (__fastcall ***)(__int64, _QWORD))v5)(v5, 0);
  return v9;
}

```

## disassembly

```asm
0x180035610  push    rbp
0x180035612  push    rbx
0x180035613  push    rsi
0x180035614  push    rdi
0x180035615  push    r12
0x180035617  push    r13
0x180035619  push    r14
0x18003561b  push    r15
0x18003561d  lea     rbp, [rsp-8]
0x180035622  sub     rsp, 108h
0x180035629  mov     rax, cs:__security_cookie
0x180035630  xor     rax, rsp
0x180035633  mov     [rbp+40h+var_50], rax
0x180035637  mov     rbx, r9
0x18003563a  mov     [rsp+140h+var_F0], rbx
0x18003563f  mov     rdi, r8
0x180035642  mov     [rsp+140h+var_E8], r8
0x180035647  mov     r13, rdx
0x18003564a  mov     r15, rcx
0x18003564d  mov     [rbp+40h+var_60], r8
0x180035651  mov     [rbp+40h+var_58], rbx
0x180035655  mov     rax, [rbp+40h+arg_20]
0x180035659  mov     [rsp+140h+var_F8], rax
0x18003565e  lea     rax, [rsp+140h+var_110]
0x180035663  mov     [rsp+140h+var_E0], rax
0x180035668  mov     [rsp+140h+var_100], 0
0x18003566d  lea     rax, ??_7UusVersion@@6B@; const UusVersion::`vftable'
0x180035674  cmp     byte ptr [r9+10h], 0
0x180035679  jz      short loc_18003568E
0x18003567b  mov     [rsp+140h+var_110], rax
0x180035680  mov     rax, [r9+8]
0x180035684  mov     [rsp+140h+var_108], rax
0x180035689  mov     [rsp+140h+var_100], 1
0x18003568e  lea     rax, [rsp+140h+var_110]
0x180035693  mov     [rbp+40h+var_90], rax
0x180035697  lea     rax, [rbp+40h+var_B8]
0x18003569b  mov     [rsp+140h+var_D8], rax
0x1800356a0  xor     cl, cl
0x1800356a2  mov     [rbp+40h+var_98], cl
0x1800356a5  cmp     [r8+20h], cl
0x1800356a9  jz      short loc_1800356BC
0x1800356ab  mov     rdx, r8
0x1800356ae  lea     rcx, [rbp+40h+var_B8]
0x1800356b2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800356b7  mov     cl, 1
0x1800356b9  mov     [rbp+40h+var_98], cl
0x1800356bc  lea     rax, [rbp+40h+var_B8]
0x1800356c0  mov     [rsp+140h+var_D8], rax
0x1800356c5  mov     sil, 1
0x1800356c8  mov     r14, [r15+20h]
0x1800356cc  mov     r15, [r15+28h]
0x1800356d0  cmp     r14, r15
0x1800356d3  jz      loc_18003576D
0x1800356d9  mov     rbx, [rsp+140h+var_F8]
0x1800356de  lea     rdi, ??_7UusVersion@@6B@; const UusVersion::`vftable'
0x1800356e5  mov     r12d, [r14]
0x1800356e8  lea     rax, [rsp+140h+var_D0]
0x1800356ed  mov     [rsp+140h+var_E0], rax
0x1800356f2  mov     [rbp+40h+var_C0], 0
0x1800356f6  cmp     [rsp+140h+var_100], 0
0x1800356fb  jz      short loc_180035710
0x1800356fd  mov     [rsp+140h+var_D0], rdi
0x180035702  mov     rax, [rsp+140h+var_108]
0x180035707  mov     [rsp+140h+var_C8], rax
0x18003570c  mov     [rbp+40h+var_C0], 1
0x180035710  lea     rax, [rbp+40h+var_88]
0x180035714  mov     [rsp+140h+var_F8], rax
0x180035719  mov     [rbp+40h+var_68], 0
0x18003571d  test    cl, cl
0x18003571f  jz      short loc_180035732
0x180035721  lea     rdx, [rbp+40h+var_B8]
0x180035725  lea     rcx, [rbp+40h+var_88]
0x180035729  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003572e  mov     [rbp+40h+var_68], 1
0x180035732  mov     [rsp+140h+var_118], rbx
0x180035737  lea     rax, [rsp+140h+var_D0]
0x18003573c  mov     [rsp+140h+var_120], rax
0x180035741  lea     r9, [rbp+40h+var_88]
0x180035745  mov     r8, r13
0x180035748  mov     edx, r12d
0x18003574b  call    ?Check@UusCapabilities@@QEAA_NW4UusCapability@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$optional@Vpath@filesystem@std@@@4@V?$optional@VUusVersion@@@4@1@Z; UusCapabilities::Check(UusCapability,std::wstring const &,std::optional<std::filesystem::path>,std::optional<UusVersion>,std::wstring const &)
0x180035750  neg     al
0x180035752  sbb     cl, cl
0x180035754  and     sil, cl
0x180035757  add     r14, 4
0x18003575b  mov     cl, [rbp+40h+var_98]
0x18003575e  cmp     r14, r15
0x180035761  jnz     short loc_1800356E5
0x180035763  mov     rbx, [rsp+140h+var_F0]
0x180035768  mov     rdi, [rsp+140h+var_E8]
0x18003576d  xor     r14d, r14d
0x180035770  test    cl, cl
0x180035772  jz      short loc_18003577E
0x180035774  lea     rcx, [rbp+40h+var_B8]
0x180035778  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003577d  nop
0x18003577e  cmp     [rsp+140h+var_100], r14b
0x180035783  jz      short loc_18003579A
0x180035785  mov     rax, [rsp+140h+var_110]
0x18003578a  xor     edx, edx
0x18003578c  lea     rcx, [rsp+140h+var_110]
0x180035791  mov     rax, [rax]
0x180035794  call    _guard_dispatch_icall
0x180035799  nop
0x18003579a  cmp     [rdi+20h], r14b
0x18003579e  jz      short loc_1800357A9
0x1800357a0  mov     rcx, rdi
0x1800357a3  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800357a8  nop
0x1800357a9  cmp     [rbx+10h], r14b
0x1800357ad  jz      short loc_1800357BF
0x1800357af  mov     rdx, [rbx]
0x1800357b2  mov     rax, [rdx]
0x1800357b5  xor     edx, edx
0x1800357b7  mov     rcx, rbx
0x1800357ba  call    _guard_dispatch_icall
0x1800357bf  mov     al, sil
0x1800357c2  mov     rcx, [rbp+40h+var_50]
0x1800357c6  xor     rcx, rsp; StackCookie
0x1800357c9  call    __security_check_cookie
0x1800357ce  add     rsp, 108h
0x1800357d5  pop     r15
0x1800357d7  pop     r14
0x1800357d9  pop     r13
0x1800357db  pop     r12
0x1800357dd  pop     rdi
0x1800357de  pop     rsi
0x1800357df  pop     rbx
0x1800357e0  pop     rbp
0x1800357e1  retn
```
