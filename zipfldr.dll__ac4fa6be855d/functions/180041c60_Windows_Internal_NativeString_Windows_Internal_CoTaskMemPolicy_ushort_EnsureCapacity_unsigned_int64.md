# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)

- ea: `0x180041c60`
- end: `0x180041d5c`
- name: `?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z`
- size: `252`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180035658`
- `0x180041470`

## callees

- `0x180023164`
- `0x180041c60`
- `0x180041d64`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180041cd1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180041cd1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180041d34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180041d34`

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
  SIZE_T cb[5]; // [rsp+20h] [rbp-28h] BYREF

  v2 = a2 + 1;
  if ( a2 + 1 < a2 )
    return (unsigned int)-2147024362;
  v5 = *(_QWORD *)(a1 + 16);
  if ( v5 == -1 )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount();
    if ( *v6 )
      v5 = v6[1] + 1LL;
    else
      v5 = 0;
    v6[2] = v5;
  }
  if ( !v5 )
  {
    cb[0] = 0;
    v4 = ULongLongMult(v2, 2u, cb);
    if ( v4 < 0 )
      return (unsigned int)v4;
    v7 = CoTaskMemAlloc(cb[0]);
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
    cb[0] = 0;
    v4 = ULongLongMult(v5, 2u, cb);
    if ( v4 >= 0 )
    {
      v9 = cb[0];
      if ( cb[0] - v8 > 0x800 )
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
0x180041c60  mov     [rsp+arg_10], rbx
0x180041c65  push    rbp
0x180041c66  push    rsi
0x180041c67  push    rdi
0x180041c68  sub     rsp, 30h
0x180041c6c  lea     rbp, [rdx+1]
0x180041c70  mov     rdi, rcx
0x180041c73  cmp     rbp, rdx
0x180041c76  jnb     short loc_180041C82
0x180041c78  mov     ebx, 80070216h
0x180041c7d  jmp     loc_180041D4D
0x180041c82  mov     r9, [rcx+10h]
0x180041c86  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x180041c8a  jnz     short loc_180041CA7
0x180041c8c  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x180041c91  cmp     qword ptr [rcx], 0
0x180041c95  jz      short loc_180041CA0
0x180041c97  mov     r9, [rcx+8]
0x180041c9b  inc     r9
0x180041c9e  jmp     short loc_180041CA3
0x180041ca0  xor     r9d, r9d
0x180041ca3  mov     [rcx+10h], r9
0x180041ca7  test    r9, r9
0x180041caa  jnz     short loc_180041CEA
0x180041cac  lea     r8, [rsp+48h+cb]; unsigned __int64 *
0x180041cb1  mov     [rsp+48h+cb], r9
0x180041cb6  lea     edx, [r9+2]; unsigned __int64
0x180041cba  mov     rcx, rbp; unsigned __int64
0x180041cbd  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180041cc2  mov     ebx, eax
0x180041cc4  test    eax, eax
0x180041cc6  js      loc_180041D4D
0x180041ccc  mov     rcx, [rsp+48h+cb]; cb
0x180041cd1  call    cs:__imp_CoTaskMemAlloc
0x180041cd7  test    rax, rax
0x180041cda  jz      short loc_180041D48
0x180041cdc  xor     ecx, ecx
0x180041cde  mov     [rdi+10h], rbp
0x180041ce2  mov     [rdi], rax
0x180041ce5  mov     [rax], cx
0x180041ce8  jmp     short loc_180041D4D
0x180041cea  xor     ebx, ebx
0x180041cec  cmp     rbp, r9
0x180041cef  jbe     short loc_180041D4D
0x180041cf1  lea     r8, [rsp+48h+cb]; unsigned __int64 *
0x180041cf6  mov     [rsp+48h+cb], rbx
0x180041cfb  lea     edx, [rbx+2]; unsigned __int64
0x180041cfe  mov     rcx, r9; unsigned __int64
0x180041d01  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180041d06  mov     ebx, eax
0x180041d08  test    eax, eax
0x180041d0a  js      short loc_180041D4D
0x180041d0c  mov     rsi, [rsp+48h+cb]
0x180041d11  mov     rax, rsi
0x180041d14  sub     rax, r9
0x180041d17  cmp     rax, 800h
0x180041d1d  jbe     short loc_180041D26
0x180041d1f  lea     rsi, [r9+800h]
0x180041d26  mov     rcx, [rdi]; pv
0x180041d29  cmp     rbp, rsi
0x180041d2c  cmova   rsi, rbp
0x180041d30  lea     rdx, [rsi+rsi]; cb
0x180041d34  call    cs:__imp_CoTaskMemRealloc
0x180041d3a  test    rax, rax
0x180041d3d  jz      short loc_180041D48
0x180041d3f  mov     [rdi+10h], rsi
0x180041d43  mov     [rdi], rax
0x180041d46  jmp     short loc_180041D4D
0x180041d48  mov     ebx, 8007000Eh
0x180041d4d  mov     eax, ebx
0x180041d4f  mov     rbx, [rsp+48h+arg_10]
0x180041d54  add     rsp, 30h
0x180041d58  pop     rdi
0x180041d59  pop     rsi
0x180041d5a  pop     rbp
0x180041d5b  retn
```
