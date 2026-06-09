# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)

- ea: `0x180019b68`
- end: `0x180019c52`
- name: `?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z`
- size: `234`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180019d84`
- `0x18004f93c`
- `0x18005132c`
- `0x180051950`

## callees

- `0x180019a94`
- `0x180019b68`
- `0x180019c58`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180019c2e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180019c2e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019bce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019bce`

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
    v4 = ULongLongMult(v2, a2, &cb);
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
    v4 = ULongLongMult(v5, a2, &cb);
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
0x180019b68  push    rbx
0x180019b6a  push    rbp
0x180019b6b  push    rsi
0x180019b6c  push    rdi
0x180019b6d  sub     rsp, 28h
0x180019b71  lea     rbp, [rdx+1]
0x180019b75  mov     rdi, rcx
0x180019b78  cmp     rbp, rdx
0x180019b7b  jnb     short loc_180019B87
0x180019b7d  mov     ebx, 80070216h
0x180019b82  jmp     loc_180019C47
0x180019b87  mov     r9, [rcx+10h]
0x180019b8b  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x180019b8f  jnz     short loc_180019BAC
0x180019b91  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x180019b96  cmp     qword ptr [rcx], 0
0x180019b9a  jz      short loc_180019BA5
0x180019b9c  mov     r9, [rcx+8]
0x180019ba0  inc     r9
0x180019ba3  jmp     short loc_180019BA8
0x180019ba5  xor     r9d, r9d
0x180019ba8  mov     [rcx+10h], r9
0x180019bac  test    r9, r9
0x180019baf  jnz     short loc_180019BE7
0x180019bb1  lea     r8, [rsp+48h+cb]; unsigned __int64 *
0x180019bb6  mov     [rsp+48h+cb], r9
0x180019bbb  mov     rcx, rbp; unsigned __int64
0x180019bbe  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180019bc3  mov     ebx, eax
0x180019bc5  test    eax, eax
0x180019bc7  js      short loc_180019C47
0x180019bc9  mov     rcx, [rsp+48h+cb]; cb
0x180019bce  call    cs:__imp_CoTaskMemAlloc
0x180019bd4  test    rax, rax
0x180019bd7  jz      short loc_180019C42
0x180019bd9  xor     ecx, ecx
0x180019bdb  mov     [rdi+10h], rbp
0x180019bdf  mov     [rdi], rax
0x180019be2  mov     [rax], cx
0x180019be5  jmp     short loc_180019C47
0x180019be7  xor     ebx, ebx
0x180019be9  cmp     rbp, r9
0x180019bec  jbe     short loc_180019C47
0x180019bee  lea     r8, [rsp+48h+cb]; unsigned __int64 *
0x180019bf3  mov     [rsp+48h+cb], rbx
0x180019bf8  mov     rcx, r9; unsigned __int64
0x180019bfb  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180019c00  mov     ebx, eax
0x180019c02  test    eax, eax
0x180019c04  js      short loc_180019C47
0x180019c06  mov     rsi, [rsp+48h+cb]
0x180019c0b  mov     rax, rsi
0x180019c0e  sub     rax, r9
0x180019c11  cmp     rax, 800h
0x180019c17  jbe     short loc_180019C20
0x180019c19  lea     rsi, [r9+800h]
0x180019c20  mov     rcx, [rdi]; pv
0x180019c23  cmp     rbp, rsi
0x180019c26  cmova   rsi, rbp
0x180019c2a  lea     rdx, [rsi+rsi]; cb
0x180019c2e  call    cs:__imp_CoTaskMemRealloc
0x180019c34  test    rax, rax
0x180019c37  jz      short loc_180019C42
0x180019c39  mov     [rdi+10h], rsi
0x180019c3d  mov     [rdi], rax
0x180019c40  jmp     short loc_180019C47
0x180019c42  mov     ebx, 8007000Eh
0x180019c47  mov     eax, ebx
0x180019c49  add     rsp, 28h
0x180019c4d  pop     rdi
0x180019c4e  pop     rsi
0x180019c4f  pop     rbp
0x180019c50  pop     rbx
0x180019c51  retn
```
