# std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::_Hashval(ushort const * const &)

- ea: `0x180020320`
- end: `0x1800203c0`
- name: `?_Hashval@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@IEBA_KAEBQEBG@Z`
- size: `160`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001d78c`
- `0x18001d930`
- `0x18001f830`
- `0x180020768`

## callees

- `0x180020320`

## import_xrefs

- `msvcrt!towlower` at `0x180020350`
- `msvcrt!towlower` at `0x180020350`

## pseudocode

```c
unsigned __int64 __fastcall std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::_Hashval(
        __int64 a1,
        wint_t **a2)
{
  wint_t *v2; // rbx
  __int64 v3; // rax
  wint_t *v5; // rsi
  int v6; // edi
  int v7; // eax
  unsigned __int64 v8; // rdx
  bool v9; // sf
  int v10; // ecx
  int v11; // eax
  unsigned __int64 result; // rax

  v2 = *a2;
  v3 = -1;
  do
    ++v3;
  while ( v2[v3] );
  v5 = &v2[v3];
  v6 = -2128831035;
  while ( v2 != v5 )
    v6 = towlower(*v2++) ^ (16777619 * v6);
  v7 = 0x7FFFFFFF * (v6 / 127773);
  v8 = *(_QWORD *)(a1 + 40);
  v9 = 16807 * v6 - v7 < 0;
  v10 = 16807 * v6 - v7;
  v11 = v10 + 0x7FFFFFFF;
  if ( !v9 )
    v11 = v10;
  result = v8 & v11;
  if ( *(_QWORD *)(a1 + 48) <= result )
    return result - (v8 >> 1) - 1;
  return result;
}

```

## disassembly

```asm
0x180020320  push    rbx
0x180020322  push    rbp
0x180020323  push    rsi
0x180020324  push    rdi
0x180020325  push    r14
0x180020327  sub     rsp, 20h
0x18002032b  mov     rbx, [rdx]
0x18002032e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180020332  xor     r14d, r14d
0x180020335  mov     rbp, rcx
0x180020338  inc     rax
0x18002033b  cmp     [rbx+rax*2], r14w
0x180020340  jnz     short loc_180020338
0x180020342  lea     rsi, [rbx+rax*2]
0x180020346  mov     edi, 811C9DC5h
0x18002034b  jmp     short loc_18002036D
0x18002034d  movzx   ecx, word ptr [rbx]; C
0x180020350  call    cs:__imp_towlower
0x180020357  nop     dword ptr [rax+rax+00h]
0x18002035c  imul    rdi, 1000193h
0x180020363  movzx   ecx, ax
0x180020366  xor     rdi, rcx
0x180020369  add     rbx, 2
0x18002036d  cmp     rbx, rsi
0x180020370  jnz     short loc_18002034D
0x180020372  mov     eax, 834E0B5Fh
0x180020377  imul    ecx, edi, 41A7h
0x18002037d  imul    edi
0x18002037f  add     edx, edi
0x180020381  sar     edx, 10h
0x180020384  mov     eax, edx
0x180020386  shr     eax, 1Fh
0x180020389  add     edx, eax
0x18002038b  imul    eax, edx, 7FFFFFFFh
0x180020391  mov     rdx, [rbp+28h]
0x180020395  sub     ecx, eax
0x180020397  lea     eax, [rcx+7FFFFFFFh]
0x18002039d  cmovns  eax, ecx
0x1800203a0  cdqe
0x1800203a2  and     rax, rdx
0x1800203a5  cmp     [rbp+30h], rax
0x1800203a9  ja      short loc_1800203B4
0x1800203ab  shr     rdx, 1
0x1800203ae  sub     rax, rdx
0x1800203b1  dec     rax
0x1800203b4  add     rsp, 20h
0x1800203b8  pop     r14
0x1800203ba  pop     rdi
0x1800203bb  pop     rsi
0x1800203bc  pop     rbp
0x1800203bd  pop     rbx
0x1800203be  retn
```
