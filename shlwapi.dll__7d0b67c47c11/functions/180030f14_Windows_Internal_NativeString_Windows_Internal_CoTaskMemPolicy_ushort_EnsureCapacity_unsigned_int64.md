# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)

- ea: `0x180030f14`
- end: `0x180031010`
- name: `?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z`
- size: `252`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002d494`
- `0x1800303c4`
- `0x180031fac`

## callees

- `0x18000fec0`
- `0x180030f14`
- `0x180031018`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180030fe8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180030fe8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180030f85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180030f85`

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
0x180030f14  mov     [rsp+arg_10], rbx
0x180030f19  push    rbp
0x180030f1a  push    rsi
0x180030f1b  push    rdi
0x180030f1c  sub     rsp, 30h
0x180030f20  lea     rbp, [rdx+1]
0x180030f24  mov     rdi, rcx
0x180030f27  cmp     rbp, rdx
0x180030f2a  jnb     short loc_180030F36
0x180030f2c  mov     ebx, 80070216h
0x180030f31  jmp     loc_180031001
0x180030f36  mov     r9, [rcx+10h]
0x180030f3a  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x180030f3e  jnz     short loc_180030F5B
0x180030f40  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x180030f45  cmp     qword ptr [rcx], 0
0x180030f49  jz      short loc_180030F54
0x180030f4b  mov     r9, [rcx+8]
0x180030f4f  inc     r9
0x180030f52  jmp     short loc_180030F57
0x180030f54  xor     r9d, r9d
0x180030f57  mov     [rcx+10h], r9
0x180030f5b  test    r9, r9
0x180030f5e  jnz     short loc_180030F9E
0x180030f60  lea     r8, [rsp+48h+cb]; unsigned __int64 *
0x180030f65  mov     [rsp+48h+cb], r9
0x180030f6a  lea     edx, [r9+2]; unsigned __int64
0x180030f6e  mov     rcx, rbp; unsigned __int64
0x180030f71  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180030f76  mov     ebx, eax
0x180030f78  test    eax, eax
0x180030f7a  js      loc_180031001
0x180030f80  mov     rcx, [rsp+48h+cb]; cb
0x180030f85  call    cs:__imp_CoTaskMemAlloc
0x180030f8b  test    rax, rax
0x180030f8e  jz      short loc_180030FFC
0x180030f90  xor     ecx, ecx
0x180030f92  mov     [rdi+10h], rbp
0x180030f96  mov     [rdi], rax
0x180030f99  mov     [rax], cx
0x180030f9c  jmp     short loc_180031001
0x180030f9e  xor     ebx, ebx
0x180030fa0  cmp     rbp, r9
0x180030fa3  jbe     short loc_180031001
0x180030fa5  lea     r8, [rsp+48h+cb]; unsigned __int64 *
0x180030faa  mov     [rsp+48h+cb], rbx
0x180030faf  lea     edx, [rbx+2]; unsigned __int64
0x180030fb2  mov     rcx, r9; unsigned __int64
0x180030fb5  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180030fba  mov     ebx, eax
0x180030fbc  test    eax, eax
0x180030fbe  js      short loc_180031001
0x180030fc0  mov     rsi, [rsp+48h+cb]
0x180030fc5  mov     rax, rsi
0x180030fc8  sub     rax, r9
0x180030fcb  cmp     rax, 800h
0x180030fd1  jbe     short loc_180030FDA
0x180030fd3  lea     rsi, [r9+800h]
0x180030fda  mov     rcx, [rdi]; pv
0x180030fdd  cmp     rbp, rsi
0x180030fe0  cmova   rsi, rbp
0x180030fe4  lea     rdx, [rsi+rsi]; cb
0x180030fe8  call    cs:__imp_CoTaskMemRealloc
0x180030fee  test    rax, rax
0x180030ff1  jz      short loc_180030FFC
0x180030ff3  mov     [rdi+10h], rsi
0x180030ff7  mov     [rdi], rax
0x180030ffa  jmp     short loc_180031001
0x180030ffc  mov     ebx, 8007000Eh
0x180031001  mov     eax, ebx
0x180031003  mov     rbx, [rsp+48h+arg_10]
0x180031008  add     rsp, 30h
0x18003100c  pop     rdi
0x18003100d  pop     rsi
0x18003100e  pop     rbp
0x18003100f  retn
```
