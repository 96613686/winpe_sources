# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)

- ea: `0x18002cbac`
- end: `0x18002cca1`
- name: `?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z`
- size: `245`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001f1f0`
- `0x180020334`
- `0x18002ccd8`

## callees

- `0x18002b444`
- `0x18002cbac`
- `0x18002cca8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002cc1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002cc1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18002cc7d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18002cc7d`

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
0x18002cbac  push    rbx
0x18002cbae  push    rbp
0x18002cbaf  push    rsi
0x18002cbb0  push    rdi
0x18002cbb1  sub     rsp, 28h
0x18002cbb5  lea     rbp, [rdx+1]
0x18002cbb9  mov     rdi, rcx
0x18002cbbc  cmp     rbp, rdx
0x18002cbbf  jnb     short loc_18002CBCB
0x18002cbc1  mov     ebx, 80070216h
0x18002cbc6  jmp     loc_18002CC96
0x18002cbcb  mov     r9, [rcx+10h]
0x18002cbcf  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x18002cbd3  jnz     short loc_18002CBF0
0x18002cbd5  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x18002cbda  cmp     qword ptr [rcx], 0
0x18002cbde  jz      short loc_18002CBE9
0x18002cbe0  mov     r9, [rcx+8]
0x18002cbe4  inc     r9
0x18002cbe7  jmp     short loc_18002CBEC
0x18002cbe9  xor     r9d, r9d
0x18002cbec  mov     [rcx+10h], r9
0x18002cbf0  test    r9, r9
0x18002cbf3  jnz     short loc_18002CC33
0x18002cbf5  lea     r8, [rsp+48h+cb]; unsigned __int64 *
0x18002cbfa  mov     [rsp+48h+cb], r9
0x18002cbff  lea     edx, [r9+2]; unsigned __int64
0x18002cc03  mov     rcx, rbp; unsigned __int64
0x18002cc06  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18002cc0b  mov     ebx, eax
0x18002cc0d  test    eax, eax
0x18002cc0f  js      loc_18002CC96
0x18002cc15  mov     rcx, [rsp+48h+cb]; cb
0x18002cc1a  call    cs:__imp_CoTaskMemAlloc
0x18002cc20  test    rax, rax
0x18002cc23  jz      short loc_18002CC91
0x18002cc25  xor     ecx, ecx
0x18002cc27  mov     [rdi+10h], rbp
0x18002cc2b  mov     [rdi], rax
0x18002cc2e  mov     [rax], cx
0x18002cc31  jmp     short loc_18002CC96
0x18002cc33  xor     ebx, ebx
0x18002cc35  cmp     rbp, r9
0x18002cc38  jbe     short loc_18002CC96
0x18002cc3a  lea     r8, [rsp+48h+cb]; unsigned __int64 *
0x18002cc3f  mov     [rsp+48h+cb], rbx
0x18002cc44  lea     edx, [rbx+2]; unsigned __int64
0x18002cc47  mov     rcx, r9; unsigned __int64
0x18002cc4a  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18002cc4f  mov     ebx, eax
0x18002cc51  test    eax, eax
0x18002cc53  js      short loc_18002CC96
0x18002cc55  mov     rsi, [rsp+48h+cb]
0x18002cc5a  mov     rax, rsi
0x18002cc5d  sub     rax, r9
0x18002cc60  cmp     rax, 800h
0x18002cc66  jbe     short loc_18002CC6F
0x18002cc68  lea     rsi, [r9+800h]
0x18002cc6f  mov     rcx, [rdi]; pv
0x18002cc72  cmp     rbp, rsi
0x18002cc75  cmova   rsi, rbp
0x18002cc79  lea     rdx, [rsi+rsi]; cb
0x18002cc7d  call    cs:__imp_CoTaskMemRealloc
0x18002cc83  test    rax, rax
0x18002cc86  jz      short loc_18002CC91
0x18002cc88  mov     [rdi+10h], rsi
0x18002cc8c  mov     [rdi], rax
0x18002cc8f  jmp     short loc_18002CC96
0x18002cc91  mov     ebx, 8007000Eh
0x18002cc96  mov     eax, ebx
0x18002cc98  add     rsp, 28h
0x18002cc9c  pop     rdi
0x18002cc9d  pop     rsi
0x18002cc9e  pop     rbp
0x18002cc9f  pop     rbx
0x18002cca0  retn
```
