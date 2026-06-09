# CLI::App::get_subcommands(std::function<bool (CLI::App const *)> const &)

- ea: `0x1400349d0`
- end: `0x140034bc9`
- name: `?get_subcommands@App@CLI@@QEBA?AV?$vector@PEBVApp@CLI@@V?$allocator@PEBVApp@CLI@@@std@@@std@@AEBV?$function@$$A6A_NPEBVApp@CLI@@@Z@4@@Z`
- size: `505`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140039c40`
- `0x14003a7d0`
- `0x140041b00`

## callees

- `0x14000f43c`
- `0x14000f804`
- `0x140010620`
- `0x14001062c`
- `0x140020300`
- `0x1400349d0`
- `0x14004a9e0`
- `0x140067010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall CLI::App::get_subcommands(__int64 a1, _QWORD *a2, __int64 a3)
{
  _QWORD *v6; // rdi
  unsigned __int64 v7; // rbx
  size_t v8; // rbx
  void *v9; // rax
  _QWORD *v10; // rax
  _QWORD *v11; // rdx
  _QWORD *i; // r8
  __int64 *v13; // rbx
  __int64 *v14; // rsi
  __int64 v15; // rcx
  __int64 *v16; // rdi
  __int64 v17; // rcx
  size_t v18; // rdi
  __int64 v20; // [rsp+50h] [rbp+8h] BYREF
  _QWORD *v21; // [rsp+58h] [rbp+10h]

  v21 = a2;
  v6 = 0;
  v7 = (__int64)(*(_QWORD *)(a1 + 776) - *(_QWORD *)(a1 + 768)) >> 4;
  *a2 = 0;
  a2[1] = 0;
  a2[2] = 0;
  if ( v7 )
  {
    if ( v7 > 0x1FFFFFFFFFFFFFFFLL )
      std::vector<std::shared_ptr<CLI::App>>::_Xlength(a1);
    v8 = 8 * v7;
    if ( v8 )
    {
      if ( v8 < 0x1000 )
      {
        v6 = operator new(v8);
      }
      else
      {
        if ( v8 + 39 < v8 )
          std::_Throw_bad_array_new_length();
        v9 = operator new(v8 + 39);
        if ( !v9 )
          __fastfail(5u);
        v6 = (_QWORD *)(((unsigned __int64)v9 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *(v6 - 1) = v9;
      }
    }
    *a2 = v6;
    a2[2] = &v6[v8 / 8];
    memset_0(v6, 0, v8);
    a2[1] = &v6[v8 / 8];
  }
  v10 = *(_QWORD **)(a1 + 776);
  v11 = *(_QWORD **)(a1 + 768);
  for ( i = (_QWORD *)*a2; v11 != v10; ++i )
  {
    *i = *v11;
    v11 += 2;
  }
  if ( *(_QWORD *)(a3 + 56) )
  {
    v13 = (__int64 *)a2[1];
    v14 = (__int64 *)*a2;
    if ( (__int64 *)*a2 != v13 )
    {
      while ( 1 )
      {
        v20 = *v14;
        v15 = *(_QWORD *)(a3 + 56);
        if ( !v15 )
        {
          std::_Xbad_function_call();
          __debugbreak();
        }
        if ( !(*(unsigned __int8 (__fastcall **)(__int64, __int64 *, _QWORD *))(*(_QWORD *)v15 + 16LL))(v15, &v20, i) )
          break;
        if ( ++v14 == v13 )
          return a2;
      }
      if ( v14 != v13 )
      {
        v16 = v14 + 1;
        if ( v14 + 1 == v13 )
          goto LABEL_26;
        do
        {
          v20 = *v16;
          v17 = *(_QWORD *)(a3 + 56);
          if ( !v17 )
          {
            std::_Xbad_function_call();
            __debugbreak();
          }
          if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v17 + 16LL))(v17, &v20) )
            *v14++ = *v16;
          ++v16;
        }
        while ( v16 != v13 );
        if ( v14 != v13 )
        {
LABEL_26:
          v18 = a2[1] - (_QWORD)v13;
          memmove_0(v14, v13, v18);
          a2[1] = (char *)v14 + v18;
        }
      }
    }
  }
  return a2;
}

```

## disassembly

```asm
0x1400349d0  mov     [rsp+arg_10], rbx
0x1400349d5  mov     [rsp+arg_18], rbp
0x1400349da  mov     [rsp+arg_8], rdx
0x1400349df  push    rsi
0x1400349e0  push    rdi
0x1400349e1  push    r14
0x1400349e3  sub     rsp, 30h
0x1400349e7  mov     rbp, r8
0x1400349ea  mov     r14, rdx
0x1400349ed  mov     rsi, rcx
0x1400349f0  xor     edi, edi
0x1400349f2  mov     [rsp+48h+var_28], edi
0x1400349f6  mov     rbx, [rcx+308h]
0x1400349fd  sub     rbx, [rcx+300h]
0x140034a04  sar     rbx, 4
0x140034a08  mov     [rdx], rdi
0x140034a0b  mov     [rdx+8], rdi
0x140034a0f  mov     [rdx+10h], rdi
0x140034a13  test    rbx, rbx
0x140034a16  jz      loc_140034A9C
0x140034a1c  mov     rax, 1FFFFFFFFFFFFFFFh
0x140034a26  cmp     rbx, rax
0x140034a29  ja      loc_140034BBD
0x140034a2f  lea     rbx, ds:0[rbx*8]
0x140034a37  test    rbx, rbx
0x140034a3a  jz      short loc_140034A7C
0x140034a3c  cmp     rbx, 1000h
0x140034a43  jb      short loc_140034A71
0x140034a45  lea     rcx, [rbx+27h]; Size
0x140034a49  cmp     rcx, rbx
0x140034a4c  jbe     loc_140034BC3
0x140034a52  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140034a57  test    rax, rax
0x140034a5a  jnz     short loc_140034A63
0x140034a5c  mov     ecx, 5
0x140034a61  int     29h; Win8: RtlFailFast(ecx)
0x140034a63  lea     rdi, [rax+27h]
0x140034a67  and     rdi, 0FFFFFFFFFFFFFFE0h
0x140034a6b  mov     [rdi-8], rax
0x140034a6f  jmp     short loc_140034A7C
0x140034a71  mov     rcx, rbx; Size
0x140034a74  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140034a79  mov     rdi, rax
0x140034a7c  mov     [r14], rdi
0x140034a7f  lea     rcx, [rdi+rbx]
0x140034a83  mov     [r14+10h], rcx
0x140034a87  mov     r8, rbx; Size
0x140034a8a  xor     edx, edx; Val
0x140034a8c  mov     rcx, rdi; void *
0x140034a8f  call    memset_0
0x140034a94  lea     rax, [rdi+rbx]
0x140034a98  mov     [r14+8], rax
0x140034a9c  mov     [rsp+48h+var_28], 1
0x140034aa4  mov     rax, [rsi+308h]
0x140034aab  mov     rdx, [rsi+300h]
0x140034ab2  mov     r8, [r14]
0x140034ab5  cmp     rdx, rax
0x140034ab8  jz      short loc_140034AD3
0x140034aba  nop     word ptr [rax+rax+00h]
0x140034ac0  mov     rcx, [rdx]
0x140034ac3  mov     [r8], rcx
0x140034ac6  add     rdx, 10h
0x140034aca  lea     r8, [r8+8]
0x140034ace  cmp     rdx, rax
0x140034ad1  jnz     short loc_140034AC0
0x140034ad3  cmp     qword ptr [rbp+38h], 0
0x140034ad8  jz      loc_140034B9B
0x140034ade  mov     rbx, [r14+8]
0x140034ae2  mov     rsi, [r14]
0x140034ae5  cmp     rsi, rbx
0x140034ae8  jz      loc_140034B9B
0x140034aee  xchg    ax, ax
0x140034af0  mov     rax, [rsi]
0x140034af3  mov     [rsp+48h+arg_0], rax
0x140034af8  mov     rcx, [rbp+38h]
0x140034afc  test    rcx, rcx
0x140034aff  jz      loc_140034BB1
0x140034b05  mov     rax, [rcx]
0x140034b08  lea     rdx, [rsp+48h+arg_0]
0x140034b0d  mov     rax, [rax+10h]
0x140034b11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140034b16  test    al, al
0x140034b18  jz      short loc_140034B25
0x140034b1a  add     rsi, 8
0x140034b1e  cmp     rsi, rbx
0x140034b21  jnz     short loc_140034AF0
0x140034b23  jmp     short loc_140034B9B
0x140034b25  cmp     rsi, rbx
0x140034b28  jz      short loc_140034B9B
0x140034b2a  lea     rdi, [rsi+8]
0x140034b2e  cmp     rdi, rbx
0x140034b31  jz      short loc_140034B7E
0x140034b33  nop     dword ptr [rax+00h]
0x140034b37  nop     word ptr [rax+rax+00000000h]
0x140034b40  mov     rax, [rdi]
0x140034b43  mov     [rsp+48h+arg_0], rax
0x140034b48  mov     rcx, [rbp+38h]
0x140034b4c  test    rcx, rcx
0x140034b4f  jz      short loc_140034BB7
0x140034b51  mov     rax, [rcx]
0x140034b54  lea     rdx, [rsp+48h+arg_0]
0x140034b59  mov     rax, [rax+10h]
0x140034b5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140034b62  test    al, al
0x140034b64  jz      short loc_140034B70
0x140034b66  mov     rax, [rdi]
0x140034b69  mov     [rsi], rax
0x140034b6c  add     rsi, 8
0x140034b70  add     rdi, 8
0x140034b74  cmp     rdi, rbx
0x140034b77  jnz     short loc_140034B40
0x140034b79  cmp     rsi, rbx
0x140034b7c  jz      short loc_140034B9B
0x140034b7e  mov     rdi, [r14+8]
0x140034b82  sub     rdi, rbx
0x140034b85  mov     r8, rdi; Size
0x140034b88  mov     rdx, rbx; Src
0x140034b8b  mov     rcx, rsi; void *
0x140034b8e  call    memmove_0
0x140034b93  lea     rax, [rsi+rdi]
0x140034b97  mov     [r14+8], rax
0x140034b9b  mov     rax, r14
0x140034b9e  mov     rbx, [rsp+48h+arg_10]
0x140034ba3  mov     rbp, [rsp+48h+arg_18]
0x140034ba8  add     rsp, 30h
0x140034bac  pop     r14
0x140034bae  pop     rdi
0x140034baf  pop     rsi
0x140034bb0  retn
0x140034bb1  call    ?_Xbad_function_call@std@@YAXXZ_0; std::_Xbad_function_call(void)
0x140034bb6  int     3; Trap to Debugger
0x140034bb7  call    ?_Xbad_function_call@std@@YAXXZ_0; std::_Xbad_function_call(void)
0x140034bbc  int     3; Trap to Debugger
0x140034bbd  call    ?_Xlength@?$vector@V?$shared_ptr@VApp@CLI@@@std@@V?$allocator@V?$shared_ptr@VApp@CLI@@@std@@@2@@std@@CAXXZ; std::vector<std::shared_ptr<CLI::App>>::_Xlength(void)
0x140034bc3  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
```
