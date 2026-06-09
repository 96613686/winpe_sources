# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)

- ea: `0x18000ed54`
- end: `0x18000ee49`
- name: `?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z`
- size: `245`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000eebc`

## callees

- `0x18000eb30`
- `0x18000ed54`
- `0x18000ee50`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000ee25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000ee25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000edc2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000edc2`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
        __int64 a1,
        unsigned __int64 a2)
{
  unsigned __int64 v2; // rbp
  int v4; // ebx
  unsigned __int64 v5; // r9
  _QWORD *v6; // rcx
  _WORD *v7; // rax
  __int64 v8; // r9
  SIZE_T v9; // rsi
  LPVOID v10; // rax
  SIZE_T cb; // [rsp+58h] [rbp+10h] BYREF

  v2 = a2 + 1;
  if ( a2 + 1 < a2 )
    return (unsigned int)-2147024362;
  v5 = *(_QWORD *)(a1 + 16);
  if ( v5 == -1 )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(a1);
    if ( *v6 )
      v5 = v6[1] + 1LL;
    else
      v5 = 0;
    v6[2] = v5;
  }
  if ( !v5 )
  {
    cb = 0;
    v4 = ULongLongMult(v2, 2u, &cb);
    if ( v4 < 0 )
      return (unsigned int)v4;
    v7 = CoTaskMemAlloc(cb);
    if ( v7 )
    {
      *(_QWORD *)(a1 + 16) = v2;
      *(_QWORD *)a1 = v7;
      *v7 = 0;
      return (unsigned int)v4;
    }
    return (unsigned int)-2147024882;
  }
  v4 = 0;
  if ( v2 > v5 )
  {
    cb = 0;
    v4 = ULongLongMult(v5, 2u, &cb);
    if ( v4 >= 0 )
    {
      v9 = cb;
      if ( cb - v8 > 0x800 )
        v9 = v8 + 2048;
      if ( v2 > v9 )
        v9 = v2;
      v10 = CoTaskMemRealloc(*(LPVOID *)a1, 2 * v9);
      if ( v10 )
      {
        *(_QWORD *)(a1 + 16) = v9;
        *(_QWORD *)a1 = v10;
        return (unsigned int)v4;
      }
      return (unsigned int)-2147024882;
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000ed54  push    rbx
0x18000ed56  push    rbp
0x18000ed57  push    rsi
0x18000ed58  push    rdi
0x18000ed59  sub     rsp, 28h
0x18000ed5d  lea     rbp, [rdx+1]
0x18000ed61  mov     rdi, rcx
0x18000ed64  cmp     rbp, rdx
0x18000ed67  jnb     short loc_18000ED73
0x18000ed69  mov     ebx, 80070216h
0x18000ed6e  jmp     loc_18000EE3E
0x18000ed73  mov     r9, [rcx+10h]
0x18000ed77  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x18000ed7b  jnz     short loc_18000ED98
0x18000ed7d  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x18000ed82  cmp     qword ptr [rcx], 0
0x18000ed86  jz      short loc_18000ED91
0x18000ed88  mov     r9, [rcx+8]
0x18000ed8c  inc     r9
0x18000ed8f  jmp     short loc_18000ED94
0x18000ed91  xor     r9d, r9d
0x18000ed94  mov     [rcx+10h], r9
0x18000ed98  test    r9, r9
0x18000ed9b  jnz     short loc_18000EDDB
0x18000ed9d  lea     r8, [rsp+48h+cb]; unsigned __int64 *
0x18000eda2  mov     [rsp+48h+cb], r9
0x18000eda7  lea     edx, [r9+2]; unsigned __int64
0x18000edab  mov     rcx, rbp; unsigned __int64
0x18000edae  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18000edb3  mov     ebx, eax
0x18000edb5  test    eax, eax
0x18000edb7  js      loc_18000EE3E
0x18000edbd  mov     rcx, [rsp+48h+cb]; cb
0x18000edc2  call    cs:__imp_CoTaskMemAlloc
0x18000edc8  test    rax, rax
0x18000edcb  jz      short loc_18000EE39
0x18000edcd  xor     ecx, ecx
0x18000edcf  mov     [rdi+10h], rbp
0x18000edd3  mov     [rdi], rax
0x18000edd6  mov     [rax], cx
0x18000edd9  jmp     short loc_18000EE3E
0x18000eddb  xor     ebx, ebx
0x18000eddd  cmp     rbp, r9
0x18000ede0  jbe     short loc_18000EE3E
0x18000ede2  lea     r8, [rsp+48h+cb]; unsigned __int64 *
0x18000ede7  mov     [rsp+48h+cb], rbx
0x18000edec  lea     edx, [rbx+2]; unsigned __int64
0x18000edef  mov     rcx, r9; unsigned __int64
0x18000edf2  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18000edf7  mov     ebx, eax
0x18000edf9  test    eax, eax
0x18000edfb  js      short loc_18000EE3E
0x18000edfd  mov     rsi, [rsp+48h+cb]
0x18000ee02  mov     rax, rsi
0x18000ee05  sub     rax, r9
0x18000ee08  cmp     rax, 800h
0x18000ee0e  jbe     short loc_18000EE17
0x18000ee10  lea     rsi, [r9+800h]
0x18000ee17  mov     rcx, [rdi]; pv
0x18000ee1a  cmp     rbp, rsi
0x18000ee1d  cmova   rsi, rbp
0x18000ee21  lea     rdx, [rsi+rsi]; cb
0x18000ee25  call    cs:__imp_CoTaskMemRealloc
0x18000ee2b  test    rax, rax
0x18000ee2e  jz      short loc_18000EE39
0x18000ee30  mov     [rdi+10h], rsi
0x18000ee34  mov     [rdi], rax
0x18000ee37  jmp     short loc_18000EE3E
0x18000ee39  mov     ebx, 8007000Eh
0x18000ee3e  mov     eax, ebx
0x18000ee40  add     rsp, 28h
0x18000ee44  pop     rdi
0x18000ee45  pop     rsi
0x18000ee46  pop     rbp
0x18000ee47  pop     rbx
0x18000ee48  retn
```
