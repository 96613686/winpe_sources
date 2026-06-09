# CSsdpCacheEntry::HrAppendNetworkInfoToRequest(_SSDP_REQUEST *)

- ea: `0x180021c54`
- end: `0x180021e13`
- name: `?HrAppendNetworkInfoToRequest@CSsdpCacheEntry@@QEAAJPEAU_SSDP_REQUEST@@@Z`
- size: `447`
- prototype: `__int64 __fastcall(CSsdpCacheEntry *__hidden this, struct _SSDP_REQUEST *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180005260`
- `0x180016e2c`

## callees

- `0x180021c54`
- `0x18002911c`
- `0x180037dd8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180021c8d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180021ca7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180021cbe`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180021c8d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180021ca7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180021cbe`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180021ce0`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180021d65`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180021dbe`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180021ce0`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180021d65`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180021dbe`

## pseudocode

```c
__int64 __fastcall CSsdpCacheEntry::HrAppendNetworkInfoToRequest(CSsdpCacheEntry *this, struct _SSDP_REQUEST *a2)
{
  unsigned int i; // ebx
  __int64 v5; // rsi
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rax
  unsigned int v9; // ebx
  unsigned int j; // esi
  unsigned __int64 v11; // r15
  __int64 v12; // r14
  _BYTE *v13; // r13
  __int64 v14; // rax
  size_t v15; // r12
  void *v16; // rax
  void *v17; // r14
  __int64 v18; // r13
  _BYTE *v19; // r14
  __int64 v20; // rax
  size_t v21; // r12
  void *v22; // rax
  void *v23; // r15
  __int64 v25; // [rsp+70h] [rbp+8h]

  if ( *((_QWORD *)a2 + 8) )
  {
    for ( i = 0; i < *((_DWORD *)a2 + 14); ++i )
    {
      v5 = 32LL * i;
      v6 = *(void **)(*((_QWORD *)a2 + 8) + v5 + 16);
      if ( v6 )
        free(v6);
      v7 = *(void **)(*((_QWORD *)a2 + 8) + v5 + 24);
      if ( v7 )
        free(v7);
    }
    free(*((void **)a2 + 8));
    *((_QWORD *)a2 + 8) = 0;
    *((_DWORD *)a2 + 14) = 0;
  }
  v8 = malloc(32LL * *((unsigned int *)this + 26));
  *((_QWORD *)a2 + 8) = v8;
  if ( v8 )
  {
    v9 = 0;
    memset_0(v8, 0, 32LL * *((unsigned int *)this + 26));
    for ( j = 0; j < *((_DWORD *)this + 26); ++j )
    {
      v11 = (unsigned __int64)j << 6;
      v25 = 32LL * j;
      *(_OWORD *)(v25 + *((_QWORD *)a2 + 8)) = *(_OWORD *)(v11 + *((_QWORD *)this + 12) + 48);
      v12 = *((_QWORD *)this + 12);
      v13 = *(_BYTE **)(v11 + v12 + 32);
      if ( v13 )
      {
        v14 = -1;
        do
          ++v14;
        while ( v13[v14] );
        v15 = v14 + 1;
        v16 = malloc(v14 + 1);
        v17 = v16;
        if ( !v16 )
          return (unsigned int)-2147024882;
        memcpy_0(v16, v13, v15);
        v18 = 32LL * j;
        *(_QWORD *)(*((_QWORD *)a2 + 8) + v25 + 16) = v17;
        v12 = *((_QWORD *)this + 12);
      }
      else
      {
        v18 = 32LL * j;
      }
      v19 = *(_BYTE **)(v11 + v12 + 40);
      if ( v19 )
      {
        v20 = -1;
        do
          ++v20;
        while ( v19[v20] );
        v21 = v20 + 1;
        v22 = malloc(v20 + 1);
        v23 = v22;
        if ( !v22 )
          return (unsigned int)-2147024882;
        memcpy_0(v22, v19, v21);
        *(_QWORD *)(*((_QWORD *)a2 + 8) + v18 + 24) = v23;
      }
    }
    *((_DWORD *)a2 + 14) = *((_DWORD *)this + 26);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v9;
}

```

## disassembly

```asm
0x180021c54  push    rbx
0x180021c56  push    rbp
0x180021c57  push    rsi
0x180021c58  push    rdi
0x180021c59  push    r12
0x180021c5b  push    r13
0x180021c5d  push    r14
0x180021c5f  push    r15
0x180021c61  sub     rsp, 28h
0x180021c65  cmp     qword ptr [rdx+40h], 0
0x180021c6a  mov     rdi, rdx
0x180021c6d  mov     rbp, rcx
0x180021c70  jz      short loc_180021CD9
0x180021c72  xor     ebx, ebx
0x180021c74  cmp     [rdx+38h], ebx
0x180021c77  jbe     short loc_180021CBA
0x180021c79  mov     rax, [rdi+40h]
0x180021c7d  mov     esi, ebx
0x180021c7f  shl     rsi, 5
0x180021c83  mov     rcx, [rax+rsi+10h]; Block
0x180021c88  test    rcx, rcx
0x180021c8b  jz      short loc_180021C99
0x180021c8d  call    cs:__imp_free
0x180021c94  nop     dword ptr [rax+rax+00h]
0x180021c99  mov     rax, [rdi+40h]
0x180021c9d  mov     rcx, [rax+rsi+18h]; Block
0x180021ca2  test    rcx, rcx
0x180021ca5  jz      short loc_180021CB3
0x180021ca7  call    cs:__imp_free
0x180021cae  nop     dword ptr [rax+rax+00h]
0x180021cb3  inc     ebx
0x180021cb5  cmp     ebx, [rdi+38h]
0x180021cb8  jb      short loc_180021C79
0x180021cba  mov     rcx, [rdi+40h]; Block
0x180021cbe  call    cs:__imp_free
0x180021cc5  nop     dword ptr [rax+rax+00h]
0x180021cca  mov     qword ptr [rdi+40h], 0
0x180021cd2  mov     dword ptr [rdi+38h], 0
0x180021cd9  mov     ecx, [rbp+68h]
0x180021cdc  shl     rcx, 5; Size
0x180021ce0  call    cs:__imp_malloc
0x180021ce7  nop     dword ptr [rax+rax+00h]
0x180021cec  mov     [rdi+40h], rax
0x180021cf0  test    rax, rax
0x180021cf3  jnz     short loc_180021CFF
0x180021cf5  mov     ebx, 8007000Eh
0x180021cfa  jmp     loc_180021DFF
0x180021cff  mov     r8d, [rbp+68h]
0x180021d03  xor     edx, edx; Val
0x180021d05  shl     r8, 5; Size
0x180021d09  mov     rcx, rax; void *
0x180021d0c  xor     ebx, ebx
0x180021d0e  call    memset_0
0x180021d13  xor     esi, esi
0x180021d15  cmp     esi, [rbp+68h]
0x180021d18  jnb     loc_180021DF9
0x180021d1e  mov     rax, [rbp+60h]
0x180021d22  mov     rcx, [rdi+40h]
0x180021d26  mov     r15d, esi
0x180021d29  shl     r15, 6
0x180021d2d  mov     edx, esi
0x180021d2f  shl     rdx, 5
0x180021d33  mov     [rsp+68h+arg_0], rdx
0x180021d38  movups  xmm0, xmmword ptr [r15+rax+30h]
0x180021d3e  movdqu  xmmword ptr [rdx+rcx], xmm0
0x180021d43  mov     r14, [rbp+60h]
0x180021d47  mov     r13, [r15+r14+20h]
0x180021d4c  test    r13, r13
0x180021d4f  jz      short loc_180021D9B
0x180021d51  or      rax, 0FFFFFFFFFFFFFFFFh
0x180021d55  inc     rax
0x180021d58  cmp     [rax+r13], bl
0x180021d5c  jnz     short loc_180021D55
0x180021d5e  lea     r12, [rax+1]
0x180021d62  mov     rcx, r12; Size
0x180021d65  call    cs:__imp_malloc
0x180021d6c  nop     dword ptr [rax+rax+00h]
0x180021d71  mov     r14, rax
0x180021d74  test    rax, rax
0x180021d77  jz      short loc_180021DF0
0x180021d79  mov     r8, r12; Size
0x180021d7c  mov     rdx, r13; Src
0x180021d7f  mov     rcx, rax; void *
0x180021d82  call    memcpy_0
0x180021d87  mov     rcx, [rdi+40h]
0x180021d8b  mov     r13, [rsp+68h+arg_0]
0x180021d90  mov     [rcx+r13+10h], r14
0x180021d95  mov     r14, [rbp+60h]
0x180021d99  jmp     short loc_180021DA0
0x180021d9b  mov     r13, [rsp+68h+arg_0]
0x180021da0  mov     r14, [r15+r14+28h]
0x180021da5  test    r14, r14
0x180021da8  jz      short loc_180021DE9
0x180021daa  or      rax, 0FFFFFFFFFFFFFFFFh
0x180021dae  inc     rax
0x180021db1  cmp     [r14+rax], bl
0x180021db5  jnz     short loc_180021DAE
0x180021db7  lea     r12, [rax+1]
0x180021dbb  mov     rcx, r12; Size
0x180021dbe  call    cs:__imp_malloc
0x180021dc5  nop     dword ptr [rax+rax+00h]
0x180021dca  mov     r15, rax
0x180021dcd  test    rax, rax
0x180021dd0  jz      short loc_180021DF0
0x180021dd2  mov     r8, r12; Size
0x180021dd5  mov     rdx, r14; Src
0x180021dd8  mov     rcx, rax; void *
0x180021ddb  call    memcpy_0
0x180021de0  mov     rcx, [rdi+40h]
0x180021de4  mov     [rcx+r13+18h], r15
0x180021de9  inc     esi
0x180021deb  jmp     loc_180021D15
0x180021df0  mov     ebx, 8007000Eh
0x180021df5  test    ebx, ebx
0x180021df7  jnz     short loc_180021DFF
0x180021df9  mov     ecx, [rbp+68h]
0x180021dfc  mov     [rdi+38h], ecx
0x180021dff  mov     eax, ebx
0x180021e01  add     rsp, 28h
0x180021e05  pop     r15
0x180021e07  pop     r14
0x180021e09  pop     r13
0x180021e0b  pop     r12
0x180021e0d  pop     rdi
0x180021e0e  pop     rsi
0x180021e0f  pop     rbp
0x180021e10  pop     rbx
0x180021e11  retn
```
