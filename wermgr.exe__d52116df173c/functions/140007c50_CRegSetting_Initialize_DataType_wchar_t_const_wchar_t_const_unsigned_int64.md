# CRegSetting::Initialize(_DataType,wchar_t const *,wchar_t const *,unsigned __int64)

- ea: `0x140007c50`
- end: `0x140007ce8`
- name: `?Initialize@CRegSetting@@QEAAJW4_DataType@@PEB_W1_K@Z`
- size: `152`
- prototype: `__int64 __fastcall(__int64, int, _WORD *, _WORD *, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400084f4`
- `0x14000964c`
- `0x14000e49c`

## callees

- `0x140007c50`
- `0x14000db44`

## pseudocode

```c
__int64 __fastcall CRegSetting::Initialize(__int64 a1, int a2, _WORD *a3, _WORD *a4, __int64 a5)
{
  unsigned __int64 v5; // rdi
  unsigned __int64 v10; // r8
  __int64 result; // rax

  v5 = -1;
  if ( a3 )
  {
    v10 = -1;
    do
      ++v10;
    while ( a3[v10] );
  }
  else
  {
    v10 = 0;
  }
  if ( !utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(a1 + 32, a3, v10) )
    return 2147500037LL;
  if ( a4 )
  {
    do
      ++v5;
    while ( a4[v5] );
  }
  else
  {
    v5 = 0;
  }
  if ( !utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(a1 + 64, a4, v5) )
    return 2147500037LL;
  *(_QWORD *)(a1 + 96) = a5;
  *(_QWORD *)(a1 + 16) = *(_QWORD *)(a1 + 8);
  result = 0;
  *(_DWORD *)(a1 + 4) = a2;
  *(_WORD *)a1 = 256;
  return result;
}

```

## disassembly

```asm
0x140007c50  push    rbx
0x140007c52  push    rbp
0x140007c53  push    rsi
0x140007c54  push    rdi
0x140007c55  push    r14
0x140007c57  sub     rsp, 20h
0x140007c5b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140007c5f  xor     r14d, r14d
0x140007c62  mov     rsi, r9
0x140007c65  mov     rax, r8
0x140007c68  mov     ebp, edx
0x140007c6a  mov     rbx, rcx
0x140007c6d  test    r8, r8
0x140007c70  jz      short loc_140007C81
0x140007c72  mov     r8, rdi
0x140007c75  inc     r8
0x140007c78  cmp     [rax+r8*2], r14w
0x140007c7d  jnz     short loc_140007C75
0x140007c7f  jmp     short loc_140007C84
0x140007c81  mov     r8, r14
0x140007c84  add     rcx, 20h ; ' '
0x140007c88  mov     rdx, rax
0x140007c8b  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x140007c90  test    al, al
0x140007c92  jz      short loc_140007CD8
0x140007c94  test    rsi, rsi
0x140007c97  jz      short loc_140007CA5
0x140007c99  inc     rdi
0x140007c9c  cmp     [rsi+rdi*2], r14w
0x140007ca1  jnz     short loc_140007C99
0x140007ca3  jmp     short loc_140007CA8
0x140007ca5  mov     rdi, r14
0x140007ca8  lea     rcx, [rbx+40h]
0x140007cac  mov     r8, rdi
0x140007caf  mov     rdx, rsi
0x140007cb2  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x140007cb7  test    al, al
0x140007cb9  jz      short loc_140007CD8
0x140007cbb  mov     rax, [rsp+48h+arg_20]
0x140007cc0  mov     [rbx+60h], rax
0x140007cc4  mov     rax, [rbx+8]
0x140007cc8  mov     [rbx+10h], rax
0x140007ccc  xor     eax, eax
0x140007cce  mov     [rbx+4], ebp
0x140007cd1  mov     word ptr [rbx], 100h
0x140007cd6  jmp     short loc_140007CDD
0x140007cd8  mov     eax, 80004005h
0x140007cdd  add     rsp, 20h
0x140007ce1  pop     r14
0x140007ce3  pop     rdi
0x140007ce4  pop     rsi
0x140007ce5  pop     rbp
0x140007ce6  pop     rbx
0x140007ce7  retn
```
