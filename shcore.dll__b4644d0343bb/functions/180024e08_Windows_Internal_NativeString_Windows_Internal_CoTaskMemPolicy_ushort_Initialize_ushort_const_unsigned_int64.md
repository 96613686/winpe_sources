# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)

- ea: `0x180024e08`
- end: `0x180024ff1`
- name: `?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z`
- size: `489`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180023528`
- `0x180026780`
- `0x180079cd8`
- `0x180088d24`

## callees

- `0x1800137a8`
- `0x180024e08`
- `0x18003aaa8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180024e99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180024e99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180024fd0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180024fd0`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
        __int64 a1,
        _WORD *a2,
        unsigned __int64 a3)
{
  _WORD *v3; // r15
  __int64 v5; // rcx
  unsigned __int64 v6; // rsi
  unsigned __int64 v7; // rbp
  unsigned __int64 v8; // r9
  int v9; // ebx
  _WORD *v11; // rax
  _WORD *v12; // rdx
  unsigned __int64 v13; // rax
  _WORD *v14; // rcx
  __int64 v15; // r9
  unsigned __int64 v16; // r14
  LPVOID v17; // rax
  unsigned __int64 v18; // [rsp+58h] [rbp+10h] BYREF

  v3 = a2;
  if ( !a2 )
  {
    v9 = 0;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(a1);
    return (unsigned int)v9;
  }
  v5 = -1;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  if ( a3 == -1 )
  {
    a3 = v6;
  }
  else if ( a3 < v6 )
  {
    v6 = a3;
  }
  v7 = a3 + 1;
  if ( a3 + 1 < a3 )
    return (unsigned int)-2147024362;
  v8 = *(_QWORD *)(a1 + 16);
  if ( v8 == -1 )
  {
    if ( *(_QWORD *)(a1 + 8) == -1 )
    {
      if ( *(_QWORD *)a1 )
      {
        do
          ++v5;
        while ( *(_WORD *)(*(_QWORD *)a1 + 2 * v5) );
      }
      else
      {
        v5 = 0;
      }
      *(_QWORD *)(a1 + 8) = v5;
    }
    else
    {
      v5 = *(_QWORD *)(a1 + 8);
    }
    v8 = (v5 + 1) & -(__int64)(*(_QWORD *)a1 != 0);
    *(_QWORD *)(a1 + 16) = v8;
  }
  if ( v8 )
  {
    v9 = 0;
    if ( v7 > v8 )
    {
      v18 = 0;
      v9 = ULongLongMult(v8, 2u, &v18);
      if ( v9 >= 0 )
      {
        v16 = v18;
        if ( v18 - v15 > 0x800 )
          v16 = v15 + 2048;
        if ( v7 > v16 )
          v16 = v7;
        v17 = CoTaskMemRealloc(*(LPVOID *)a1, 2 * v16);
        if ( !v17 )
          return (unsigned int)-2147024882;
        *(_QWORD *)(a1 + 16) = v16;
        *(_QWORD *)a1 = v17;
        goto LABEL_15;
      }
    }
LABEL_14:
    if ( v9 < 0 )
      return (unsigned int)v9;
    goto LABEL_15;
  }
  if ( !is_mul_ok(v7, 2u) )
    return (unsigned int)-2147024362;
  v11 = CoTaskMemAlloc(2 * v7);
  if ( !v11 )
  {
    v9 = -2147024882;
    goto LABEL_14;
  }
  *(_QWORD *)(a1 + 16) = v7;
  v9 = 0;
  *(_QWORD *)a1 = v11;
  *v11 = 0;
LABEL_15:
  if ( v7 )
  {
    v12 = *(_WORD **)a1;
    if ( v6 > 0x7FFFFFFE || v7 > 0x7FFFFFFF )
    {
      *v12 = 0;
    }
    else
    {
      v13 = v6;
      do
      {
        if ( !v13 )
          break;
        if ( !*v3 )
          break;
        *v12++ = *v3++;
        --v13;
        --v7;
      }
      while ( v7 );
      v14 = v12 - 1;
      if ( v7 )
        v14 = v12;
      *v14 = 0;
    }
  }
  *(_QWORD *)(a1 + 8) = v6;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180024e08  mov     [rsp+arg_0], rbx
0x180024e0d  mov     [rsp+arg_10], rbp
0x180024e12  push    rsi
0x180024e13  push    rdi
0x180024e14  push    r12
0x180024e16  push    r14
0x180024e18  push    r15
0x180024e1a  sub     rsp, 20h
0x180024e1e  xor     r12d, r12d
0x180024e21  mov     r15, rdx
0x180024e24  mov     rdi, rcx
0x180024e27  test    rdx, rdx
0x180024e2a  jz      loc_180024F13
0x180024e30  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180024e34  mov     rsi, rcx
0x180024e37  inc     rsi
0x180024e3a  cmp     [rdx+rsi*2], r12w
0x180024e3f  jnz     short loc_180024E37
0x180024e41  cmp     r8, rcx
0x180024e44  jnz     loc_180024F26
0x180024e4a  mov     r8, rsi
0x180024e4d  lea     rbp, [r8+1]
0x180024e51  cmp     rbp, r8
0x180024e54  jb      short loc_180024E78
0x180024e56  mov     r9, [rdi+10h]
0x180024e5a  cmp     r9, rcx
0x180024e5d  jz      loc_180024F32
0x180024e63  test    r9, r9
0x180024e66  jnz     loc_180024F7B
0x180024e6c  lea     eax, [r9+2]
0x180024e70  mul     rbp
0x180024e73  test    rdx, rdx
0x180024e76  jz      short loc_180024E96
0x180024e78  mov     ebx, 80070216h
0x180024e7d  mov     rbp, [rsp+48h+arg_10]
0x180024e82  mov     eax, ebx
0x180024e84  mov     rbx, [rsp+48h+arg_0]
0x180024e89  add     rsp, 20h
0x180024e8d  pop     r15
0x180024e8f  pop     r14
0x180024e91  pop     r12
0x180024e93  pop     rdi
0x180024e94  pop     rsi
0x180024e95  retn
0x180024e96  mov     rcx, rax; cb
0x180024e99  call    cs:__imp_CoTaskMemAlloc
0x180024e9f  test    rax, rax
0x180024ea2  jz      loc_180024F71
0x180024ea8  mov     [rdi+10h], rbp
0x180024eac  mov     ebx, r12d
0x180024eaf  mov     [rdi], rax
0x180024eb2  mov     [rax], r12w
0x180024eb6  jmp     short loc_180024EBC
0x180024eb8  test    ebx, ebx
0x180024eba  js      short loc_180024E7D
0x180024ebc  test    rbp, rbp
0x180024ebf  jz      short loc_180024F0A
0x180024ec1  mov     rdx, [rdi]
0x180024ec4  cmp     rsi, 7FFFFFFEh
0x180024ecb  ja      short loc_180024F20
0x180024ecd  cmp     rbp, 7FFFFFFFh
0x180024ed4  ja      short loc_180024F20
0x180024ed6  mov     rax, rsi
0x180024ed9  test    rax, rax
0x180024edc  jz      short loc_180024EFB
0x180024ede  movzx   ecx, word ptr [r15]
0x180024ee2  test    cx, cx
0x180024ee5  jz      short loc_180024EFB
0x180024ee7  mov     [rdx], cx
0x180024eea  add     r15, 2
0x180024eee  add     rdx, 2
0x180024ef2  dec     rax
0x180024ef5  sub     rbp, 1
0x180024ef9  jnz     short loc_180024ED9
0x180024efb  test    rbp, rbp
0x180024efe  lea     rcx, [rdx-2]
0x180024f02  cmovnz  rcx, rdx
0x180024f06  mov     [rcx], r12w
0x180024f0a  mov     [rdi+8], rsi
0x180024f0e  jmp     loc_180024E7D
0x180024f13  mov     ebx, r12d
0x180024f16  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180024f1b  jmp     loc_180024E7D
0x180024f20  mov     [rdx], r12w
0x180024f24  jmp     short loc_180024F0A
0x180024f26  cmp     r8, rsi
0x180024f29  cmovb   rsi, r8
0x180024f2d  jmp     loc_180024E4D
0x180024f32  cmp     [rdi+8], rcx
0x180024f36  jnz     short loc_180024F55
0x180024f38  mov     rax, [rdi]
0x180024f3b  test    rax, rax
0x180024f3e  jnz     short loc_180024F45
0x180024f40  mov     rcx, r12
0x180024f43  jmp     short loc_180024F4F
0x180024f45  inc     rcx
0x180024f48  cmp     [rax+rcx*2], r12w
0x180024f4d  jnz     short loc_180024F45
0x180024f4f  mov     [rdi+8], rcx
0x180024f53  jmp     short loc_180024F59
0x180024f55  mov     rcx, [rdi+8]
0x180024f59  mov     rax, [rdi]
0x180024f5c  inc     rcx
0x180024f5f  neg     rax
0x180024f62  sbb     r9, r9
0x180024f65  and     r9, rcx
0x180024f68  mov     [rdi+10h], r9
0x180024f6c  jmp     loc_180024E63
0x180024f71  mov     ebx, 8007000Eh
0x180024f76  jmp     loc_180024EB8
0x180024f7b  mov     ebx, r12d
0x180024f7e  cmp     rbp, r9
0x180024f81  jbe     loc_180024EB8
0x180024f87  lea     r8, [rsp+48h+arg_8]; unsigned __int64 *
0x180024f8c  mov     [rsp+48h+arg_8], r12
0x180024f91  mov     edx, 2; unsigned __int64
0x180024f96  mov     rcx, r9; unsigned __int64
0x180024f99  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180024f9e  mov     ebx, eax
0x180024fa0  test    eax, eax
0x180024fa2  js      loc_180024EB8
0x180024fa8  mov     r14, [rsp+48h+arg_8]
0x180024fad  mov     rax, r14
0x180024fb0  sub     rax, r9
0x180024fb3  cmp     rax, 800h
0x180024fb9  jbe     short loc_180024FC2
0x180024fbb  lea     r14, [r9+800h]
0x180024fc2  mov     rcx, [rdi]; pv
0x180024fc5  cmp     rbp, r14
0x180024fc8  cmova   r14, rbp
0x180024fcc  lea     rdx, [r14+r14]; cb
0x180024fd0  call    cs:__imp_CoTaskMemRealloc
0x180024fd6  test    rax, rax
0x180024fd9  jz      short loc_180024FE7
0x180024fdb  mov     [rdi+10h], r14
0x180024fdf  mov     [rdi], rax
0x180024fe2  jmp     loc_180024EBC
0x180024fe7  mov     ebx, 8007000Eh
0x180024fec  jmp     loc_180024E7D
```
