# ATL::CComDynamicUnkArray::Add(IUnknown *)

- ea: `0x180002d38`
- end: `0x180002e03`
- name: `?Add@CComDynamicUnkArray@ATL@@QEAAKPEAUIUnknown@@@Z`
- size: `203`
- prototype: `unsigned int __fastcall(ATL::CComDynamicUnkArray *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180002e80`

## callees

- `0x1800016f0`
- `0x180002d38`
- `0x18001423e`

## import_xrefs

- `msvcrt!calloc` at `0x180002d5e`
- `msvcrt!calloc` at `0x180002d5e`

## pseudocode

```c
__int64 __fastcall ATL::CComDynamicUnkArray::Add(ATL::CComDynamicUnkArray *this, struct IUnknown *a2)
{
  int v2; // edi
  _OWORD *v5; // rax
  unsigned int v6; // edx
  _QWORD *v7; // rcx
  unsigned __int64 v8; // r8
  int v9; // edi
  char *v10; // rcx
  __int64 result; // rax
  __int64 v12; // rax

  v2 = *((_DWORD *)this + 2);
  if ( !v2 )
  {
    v2 = 4;
    v5 = calloc(8u, 4u);
    if ( !v5 )
      return 0;
    *(_QWORD *)this = v5;
    *v5 = 0;
    *((_DWORD *)this + 2) = 4;
    v5[1] = 0;
  }
  v6 = 1;
  v7 = *(_QWORD **)this;
  v8 = *(_QWORD *)this + 8LL * v2;
  if ( *(_QWORD *)this >= v8 )
  {
LABEL_7:
    v9 = 2 * v2;
    v10 = (char *)_recalloc(*(void **)this, 8u, v9);
    if ( v10 )
    {
      v12 = *((int *)this + 2);
      *(_QWORD *)this = v10;
      memset_0(&v10[8 * v12], 0, 8 * v12);
      *(_QWORD *)(*(_QWORD *)this + 8LL * *((int *)this + 2)) = a2;
      result = (unsigned int)(*((_DWORD *)this + 2) + 1);
      *((_DWORD *)this + 2) = v9;
      return result;
    }
    return 0;
  }
  while ( *v7 )
  {
    ++v6;
    if ( (unsigned __int64)++v7 >= v8 )
      goto LABEL_7;
  }
  *v7 = a2;
  return v6;
}

```

## disassembly

```asm
0x180002d38  mov     [rsp+arg_0], rbx
0x180002d3d  mov     [rsp+arg_8], rsi
0x180002d42  push    rdi
0x180002d43  sub     rsp, 20h
0x180002d47  mov     edi, [rcx+8]
0x180002d4a  mov     rsi, rdx
0x180002d4d  mov     rbx, rcx
0x180002d50  test    edi, edi
0x180002d52  jnz     short loc_180002D79
0x180002d54  mov     edi, 4
0x180002d59  mov     edx, edi; Size
0x180002d5b  lea     ecx, [rdi+4]; Count
0x180002d5e  call    cs:__imp_calloc
0x180002d64  test    rax, rax
0x180002d67  jz      short loc_180002DBC
0x180002d69  xorps   xmm0, xmm0
0x180002d6c  mov     [rbx], rax
0x180002d6f  movups  xmmword ptr [rax], xmm0
0x180002d72  mov     [rbx+8], edi
0x180002d75  movups  xmmword ptr [rax+10h], xmm0
0x180002d79  mov     r9, [rbx]
0x180002d7c  mov     edx, 1
0x180002d81  movsxd  rax, edi
0x180002d84  mov     rcx, r9
0x180002d87  lea     r8, [r9+rax*8]
0x180002d8b  cmp     r9, r8
0x180002d8e  jnb     short loc_180002DA1
0x180002d90  cmp     qword ptr [rcx], 0
0x180002d94  jz      short loc_180002DC0
0x180002d96  inc     edx
0x180002d98  add     rcx, 8
0x180002d9c  cmp     rcx, r8
0x180002d9f  jb      short loc_180002D90
0x180002da1  add     edi, edi
0x180002da3  mov     edx, 8; Count
0x180002da8  movsxd  r8, edi; Size
0x180002dab  mov     rcx, r9; Block
0x180002dae  call    cs:__imp__recalloc
0x180002db4  mov     rcx, rax
0x180002db7  test    rax, rax
0x180002dba  jnz     short loc_180002DC7
0x180002dbc  xor     eax, eax
0x180002dbe  jmp     short loc_180002DF3
0x180002dc0  mov     [rcx], rsi
0x180002dc3  mov     eax, edx
0x180002dc5  jmp     short loc_180002DF3
0x180002dc7  movsxd  rax, dword ptr [rbx+8]
0x180002dcb  xor     edx, edx; Val
0x180002dcd  mov     [rbx], rcx
0x180002dd0  lea     r8, ds:0[rax*8]; Size
0x180002dd8  add     rcx, r8; void *
0x180002ddb  call    memset_0
0x180002de0  movsxd  rcx, dword ptr [rbx+8]
0x180002de4  mov     rax, [rbx]
0x180002de7  mov     [rax+rcx*8], rsi
0x180002deb  mov     eax, [rbx+8]
0x180002dee  inc     eax
0x180002df0  mov     [rbx+8], edi
0x180002df3  mov     rbx, [rsp+28h+arg_0]
0x180002df8  mov     rsi, [rsp+28h+arg_8]
0x180002dfd  add     rsp, 20h
0x180002e01  pop     rdi
0x180002e02  retn
```
