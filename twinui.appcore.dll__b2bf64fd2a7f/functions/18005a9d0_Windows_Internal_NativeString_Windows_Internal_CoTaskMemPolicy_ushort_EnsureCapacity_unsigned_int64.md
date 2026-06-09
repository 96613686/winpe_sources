# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)

- ea: `0x18005a9d0`
- end: `0x18005aac5`
- name: `?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z`
- size: `245`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18005add0`
- `0x180062348`
- `0x180072df0`
- `0x1800788c4`

## callees

- `0x180016694`
- `0x1800193f4`
- `0x18005a9d0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005aa3e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005aa3e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18005aaa1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18005aaa1`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
        __int64 a1,
        unsigned __int64 a2,
        __int64 a3)
{
  unsigned __int64 v3; // rbp
  int v5; // ebx
  unsigned __int64 v6; // r9
  _QWORD *v7; // rcx
  _WORD *v8; // rax
  __int64 v9; // r9
  SIZE_T v10; // rsi
  LPVOID v11; // rax
  SIZE_T cb; // [rsp+58h] [rbp+10h] BYREF

  v3 = a2 + 1;
  if ( a2 + 1 < a2 )
    return (unsigned int)-2147024362;
  v6 = *(_QWORD *)(a1 + 16);
  if ( v6 == -1 )
  {
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_EnsureCount(a1, a2, a3, -1);
    if ( *v7 )
      v6 = v7[1] + 1LL;
    else
      v6 = 0;
    v7[2] = v6;
  }
  if ( !v6 )
  {
    cb = 0;
    v5 = ULongLongMult(v3, 2u, &cb);
    if ( v5 < 0 )
      return (unsigned int)v5;
    v8 = CoTaskMemAlloc(cb);
    if ( v8 )
    {
      *(_QWORD *)(a1 + 16) = v3;
      *(_QWORD *)a1 = v8;
      *v8 = 0;
      return (unsigned int)v5;
    }
    return (unsigned int)-2147024882;
  }
  v5 = 0;
  if ( v3 > v6 )
  {
    cb = 0;
    v5 = ULongLongMult(v6, 2u, &cb);
    if ( v5 >= 0 )
    {
      v10 = cb;
      if ( cb - v9 > 0x800 )
        v10 = v9 + 2048;
      if ( v3 > v10 )
        v10 = v3;
      v11 = CoTaskMemRealloc(*(LPVOID *)a1, 2 * v10);
      if ( v11 )
      {
        *(_QWORD *)(a1 + 16) = v10;
        *(_QWORD *)a1 = v11;
        return (unsigned int)v5;
      }
      return (unsigned int)-2147024882;
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18005a9d0  push    rbx
0x18005a9d2  push    rbp
0x18005a9d3  push    rsi
0x18005a9d4  push    rdi
0x18005a9d5  sub     rsp, 28h
0x18005a9d9  lea     rbp, [rdx+1]
0x18005a9dd  mov     rdi, rcx
0x18005a9e0  cmp     rbp, rdx
0x18005a9e3  jnb     short loc_18005A9EF
0x18005a9e5  mov     ebx, 80070216h
0x18005a9ea  jmp     loc_18005AABA
0x18005a9ef  mov     r9, [rcx+10h]
0x18005a9f3  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x18005a9f7  jnz     short loc_18005AA14
0x18005a9f9  call    ?_EnsureCount@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_EnsureCount(void)
0x18005a9fe  cmp     qword ptr [rcx], 0
0x18005aa02  jz      short loc_18005AA0D
0x18005aa04  mov     r9, [rcx+8]
0x18005aa08  inc     r9
0x18005aa0b  jmp     short loc_18005AA10
0x18005aa0d  xor     r9d, r9d
0x18005aa10  mov     [rcx+10h], r9
0x18005aa14  test    r9, r9
0x18005aa17  jnz     short loc_18005AA57
0x18005aa19  lea     r8, [rsp+48h+cb]; unsigned __int64 *
0x18005aa1e  mov     [rsp+48h+cb], r9
0x18005aa23  lea     edx, [r9+2]; unsigned __int64
0x18005aa27  mov     rcx, rbp; unsigned __int64
0x18005aa2a  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18005aa2f  mov     ebx, eax
0x18005aa31  test    eax, eax
0x18005aa33  js      loc_18005AABA
0x18005aa39  mov     rcx, [rsp+48h+cb]; cb
0x18005aa3e  call    cs:__imp_CoTaskMemAlloc
0x18005aa44  test    rax, rax
0x18005aa47  jz      short loc_18005AAB5
0x18005aa49  xor     ecx, ecx
0x18005aa4b  mov     [rdi+10h], rbp
0x18005aa4f  mov     [rdi], rax
0x18005aa52  mov     [rax], cx
0x18005aa55  jmp     short loc_18005AABA
0x18005aa57  xor     ebx, ebx
0x18005aa59  cmp     rbp, r9
0x18005aa5c  jbe     short loc_18005AABA
0x18005aa5e  lea     r8, [rsp+48h+cb]; unsigned __int64 *
0x18005aa63  mov     [rsp+48h+cb], rbx
0x18005aa68  lea     edx, [rbx+2]; unsigned __int64
0x18005aa6b  mov     rcx, r9; unsigned __int64
0x18005aa6e  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18005aa73  mov     ebx, eax
0x18005aa75  test    eax, eax
0x18005aa77  js      short loc_18005AABA
0x18005aa79  mov     rsi, [rsp+48h+cb]
0x18005aa7e  mov     rax, rsi
0x18005aa81  sub     rax, r9
0x18005aa84  cmp     rax, 800h
0x18005aa8a  jbe     short loc_18005AA93
0x18005aa8c  lea     rsi, [r9+800h]
0x18005aa93  mov     rcx, [rdi]; pv
0x18005aa96  cmp     rbp, rsi
0x18005aa99  cmova   rsi, rbp
0x18005aa9d  lea     rdx, [rsi+rsi]; cb
0x18005aaa1  call    cs:__imp_CoTaskMemRealloc
0x18005aaa7  test    rax, rax
0x18005aaaa  jz      short loc_18005AAB5
0x18005aaac  mov     [rdi+10h], rsi
0x18005aab0  mov     [rdi], rax
0x18005aab3  jmp     short loc_18005AABA
0x18005aab5  mov     ebx, 8007000Eh
0x18005aaba  mov     eax, ebx
0x18005aabc  add     rsp, 28h
0x18005aac0  pop     rdi
0x18005aac1  pop     rsi
0x18005aac2  pop     rbp
0x18005aac3  pop     rbx
0x18005aac4  retn
```
