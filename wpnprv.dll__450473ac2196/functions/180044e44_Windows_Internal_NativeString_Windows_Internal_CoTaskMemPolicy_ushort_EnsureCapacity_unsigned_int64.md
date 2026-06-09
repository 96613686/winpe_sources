# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)

- ea: `0x180044e44`
- end: `0x180044f73`
- name: `?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z`
- size: `303`
- prototype: `__int64 __fastcall(__int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180032b64`
- `0x18007e4b8`

## callees

- `0x18001c738`
- `0x180044e44`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180044ee0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180044ee0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180044f45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180044f45`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
        __int64 a1,
        unsigned __int64 a2)
{
  unsigned __int64 v2; // rbp
  int v4; // ebx
  unsigned __int64 v5; // r9
  __int64 v6; // rcx
  _WORD *v7; // rax
  __int64 v8; // r9
  SIZE_T v9; // rsi
  LPVOID v10; // rax
  SIZE_T cb; // [rsp+48h] [rbp+10h] BYREF

  v2 = a2 + 1;
  if ( a2 + 1 < a2 )
    return (unsigned int)-2147024362;
  v5 = *(_QWORD *)(a1 + 16);
  v6 = -1;
  if ( v5 == -1 )
  {
    if ( *(_QWORD *)(a1 + 8) == -1 )
    {
      if ( *(_QWORD *)a1 )
      {
        do
          ++v6;
        while ( *(_WORD *)(*(_QWORD *)a1 + 2 * v6) );
      }
      else
      {
        v6 = 0;
      }
      *(_QWORD *)(a1 + 8) = v6;
    }
    else
    {
      v6 = *(_QWORD *)(a1 + 8);
    }
    v5 = (v6 + 1) & -(__int64)(*(_QWORD *)a1 != 0);
    *(_QWORD *)(a1 + 16) = v5;
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
0x180044e44  mov     [rsp+arg_0], rbx
0x180044e49  mov     [rsp+arg_10], rbp
0x180044e4e  push    rsi
0x180044e4f  push    rdi
0x180044e50  push    r14
0x180044e52  sub     rsp, 20h
0x180044e56  lea     rbp, [rdx+1]
0x180044e5a  mov     rdi, rcx
0x180044e5d  cmp     rbp, rdx
0x180044e60  jnb     short loc_180044E6C
0x180044e62  mov     ebx, 80070216h
0x180044e67  jmp     loc_180044F5E
0x180044e6c  mov     r9, [rcx+10h]
0x180044e70  xor     r14d, r14d
0x180044e73  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180044e77  cmp     r9, rcx
0x180044e7a  jnz     short loc_180044EB6
0x180044e7c  cmp     [rdi+8], rcx
0x180044e80  jnz     short loc_180044E9F
0x180044e82  mov     rax, [rdi]
0x180044e85  test    rax, rax
0x180044e88  jz      short loc_180044E96
0x180044e8a  inc     rcx
0x180044e8d  cmp     [rax+rcx*2], r14w
0x180044e92  jnz     short loc_180044E8A
0x180044e94  jmp     short loc_180044E99
0x180044e96  mov     rcx, r14
0x180044e99  mov     [rdi+8], rcx
0x180044e9d  jmp     short loc_180044EA3
0x180044e9f  mov     rcx, [rdi+8]
0x180044ea3  mov     rax, [rdi]
0x180044ea6  inc     rcx
0x180044ea9  neg     rax
0x180044eac  sbb     r9, r9
0x180044eaf  and     r9, rcx
0x180044eb2  mov     [rdi+10h], r9
0x180044eb6  test    r9, r9
0x180044eb9  jnz     short loc_180044EF8
0x180044ebb  lea     r8, [rsp+38h+cb]; unsigned __int64 *
0x180044ec0  mov     [rsp+38h+cb], r14
0x180044ec5  lea     edx, [r9+2]; unsigned __int64
0x180044ec9  mov     rcx, rbp; unsigned __int64
0x180044ecc  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180044ed1  mov     ebx, eax
0x180044ed3  test    eax, eax
0x180044ed5  js      loc_180044F5E
0x180044edb  mov     rcx, [rsp+38h+cb]; cb
0x180044ee0  call    cs:__imp_CoTaskMemAlloc
0x180044ee6  test    rax, rax
0x180044ee9  jz      short loc_180044F59
0x180044eeb  mov     [rdi+10h], rbp
0x180044eef  mov     [rdi], rax
0x180044ef2  mov     [rax], r14w
0x180044ef6  jmp     short loc_180044F5E
0x180044ef8  mov     ebx, r14d
0x180044efb  cmp     rbp, r9
0x180044efe  jbe     short loc_180044F5E
0x180044f00  lea     r8, [rsp+38h+cb]; unsigned __int64 *
0x180044f05  mov     [rsp+38h+cb], r14
0x180044f0a  mov     edx, 2; unsigned __int64
0x180044f0f  mov     rcx, r9; unsigned __int64
0x180044f12  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180044f17  mov     ebx, eax
0x180044f19  test    eax, eax
0x180044f1b  js      short loc_180044F5E
0x180044f1d  mov     rsi, [rsp+38h+cb]
0x180044f22  mov     rax, rsi
0x180044f25  sub     rax, r9
0x180044f28  cmp     rax, 800h
0x180044f2e  jbe     short loc_180044F37
0x180044f30  lea     rsi, [r9+800h]
0x180044f37  mov     rcx, [rdi]; pv
0x180044f3a  cmp     rbp, rsi
0x180044f3d  cmova   rsi, rbp
0x180044f41  lea     rdx, [rsi+rsi]; cb
0x180044f45  call    cs:__imp_CoTaskMemRealloc
0x180044f4b  test    rax, rax
0x180044f4e  jz      short loc_180044F59
0x180044f50  mov     [rdi+10h], rsi
0x180044f54  mov     [rdi], rax
0x180044f57  jmp     short loc_180044F5E
0x180044f59  mov     ebx, 8007000Eh
0x180044f5e  mov     rbp, [rsp+38h+arg_10]
0x180044f63  mov     eax, ebx
0x180044f65  mov     rbx, [rsp+38h+arg_0]
0x180044f6a  add     rsp, 20h
0x180044f6e  pop     r14
0x180044f70  pop     rdi
0x180044f71  pop     rsi
0x180044f72  retn
```
