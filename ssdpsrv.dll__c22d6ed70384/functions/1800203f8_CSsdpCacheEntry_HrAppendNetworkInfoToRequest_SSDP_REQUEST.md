# CSsdpCacheEntry::HrAppendNetworkInfoToRequest(_SSDP_REQUEST *)

- ea: `0x1800203f8`
- end: `0x180020592`
- name: `?HrAppendNetworkInfoToRequest@CSsdpCacheEntry@@QEAAJPEAU_SSDP_REQUEST@@@Z`
- size: `410`
- prototype: `__int64 __fastcall(CSsdpCacheEntry *__hidden this, struct _SSDP_REQUEST *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180003a00`
- `0x180014868`

## callees

- `0x1800203f8`
- `0x18002735c`
- `0x180035298`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180020431`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180020445`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180020456`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180020431`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180020445`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180020456`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180020472`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800204f1`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180020544`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180020472`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800204f1`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180020544`

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
0x1800203f8  push    rbx
0x1800203fa  push    rbp
0x1800203fb  push    rsi
0x1800203fc  push    rdi
0x1800203fd  push    r12
0x1800203ff  push    r13
0x180020401  push    r14
0x180020403  push    r15
0x180020405  sub     rsp, 28h
0x180020409  cmp     qword ptr [rdx+40h], 0
0x18002040e  mov     rdi, rdx
0x180020411  mov     rbp, rcx
0x180020414  jz      short loc_18002046B
0x180020416  xor     ebx, ebx
0x180020418  cmp     [rdx+38h], ebx
0x18002041b  jbe     short loc_180020452
0x18002041d  mov     rax, [rdi+40h]
0x180020421  mov     esi, ebx
0x180020423  shl     rsi, 5
0x180020427  mov     rcx, [rax+rsi+10h]; Block
0x18002042c  test    rcx, rcx
0x18002042f  jz      short loc_180020437
0x180020431  call    cs:__imp_free
0x180020437  mov     rax, [rdi+40h]
0x18002043b  mov     rcx, [rax+rsi+18h]; Block
0x180020440  test    rcx, rcx
0x180020443  jz      short loc_18002044B
0x180020445  call    cs:__imp_free
0x18002044b  inc     ebx
0x18002044d  cmp     ebx, [rdi+38h]
0x180020450  jb      short loc_18002041D
0x180020452  mov     rcx, [rdi+40h]; Block
0x180020456  call    cs:__imp_free
0x18002045c  mov     qword ptr [rdi+40h], 0
0x180020464  mov     dword ptr [rdi+38h], 0
0x18002046b  mov     ecx, [rbp+68h]
0x18002046e  shl     rcx, 5; Size
0x180020472  call    cs:__imp_malloc
0x180020478  mov     [rdi+40h], rax
0x18002047c  test    rax, rax
0x18002047f  jnz     short loc_18002048B
0x180020481  mov     ebx, 8007000Eh
0x180020486  jmp     loc_18002057F
0x18002048b  mov     r8d, [rbp+68h]
0x18002048f  xor     edx, edx; Val
0x180020491  shl     r8, 5; Size
0x180020495  mov     rcx, rax; void *
0x180020498  xor     ebx, ebx
0x18002049a  call    memset_0
0x18002049f  xor     esi, esi
0x1800204a1  cmp     esi, [rbp+68h]
0x1800204a4  jnb     loc_180020579
0x1800204aa  mov     rax, [rbp+60h]
0x1800204ae  mov     rcx, [rdi+40h]
0x1800204b2  mov     r15d, esi
0x1800204b5  shl     r15, 6
0x1800204b9  mov     edx, esi
0x1800204bb  shl     rdx, 5
0x1800204bf  mov     [rsp+68h+arg_0], rdx
0x1800204c4  movups  xmm0, xmmword ptr [r15+rax+30h]
0x1800204ca  movdqu  xmmword ptr [rdx+rcx], xmm0
0x1800204cf  mov     r14, [rbp+60h]
0x1800204d3  mov     r13, [r15+r14+20h]
0x1800204d8  test    r13, r13
0x1800204db  jz      short loc_180020521
0x1800204dd  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800204e1  inc     rax
0x1800204e4  cmp     [rax+r13], bl
0x1800204e8  jnz     short loc_1800204E1
0x1800204ea  lea     r12, [rax+1]
0x1800204ee  mov     rcx, r12; Size
0x1800204f1  call    cs:__imp_malloc
0x1800204f7  mov     r14, rax
0x1800204fa  test    rax, rax
0x1800204fd  jz      short loc_180020570
0x1800204ff  mov     r8, r12; Size
0x180020502  mov     rdx, r13; Src
0x180020505  mov     rcx, rax; void *
0x180020508  call    memcpy_0
0x18002050d  mov     rcx, [rdi+40h]
0x180020511  mov     r13, [rsp+68h+arg_0]
0x180020516  mov     [rcx+r13+10h], r14
0x18002051b  mov     r14, [rbp+60h]
0x18002051f  jmp     short loc_180020526
0x180020521  mov     r13, [rsp+68h+arg_0]
0x180020526  mov     r14, [r15+r14+28h]
0x18002052b  test    r14, r14
0x18002052e  jz      short loc_180020569
0x180020530  or      rax, 0FFFFFFFFFFFFFFFFh
0x180020534  inc     rax
0x180020537  cmp     [r14+rax], bl
0x18002053b  jnz     short loc_180020534
0x18002053d  lea     r12, [rax+1]
0x180020541  mov     rcx, r12; Size
0x180020544  call    cs:__imp_malloc
0x18002054a  mov     r15, rax
0x18002054d  test    rax, rax
0x180020550  jz      short loc_180020570
0x180020552  mov     r8, r12; Size
0x180020555  mov     rdx, r14; Src
0x180020558  mov     rcx, rax; void *
0x18002055b  call    memcpy_0
0x180020560  mov     rcx, [rdi+40h]
0x180020564  mov     [rcx+r13+18h], r15
0x180020569  inc     esi
0x18002056b  jmp     loc_1800204A1
0x180020570  mov     ebx, 8007000Eh
0x180020575  test    ebx, ebx
0x180020577  jnz     short loc_18002057F
0x180020579  mov     ecx, [rbp+68h]
0x18002057c  mov     [rdi+38h], ecx
0x18002057f  mov     eax, ebx
0x180020581  add     rsp, 28h
0x180020585  pop     r15
0x180020587  pop     r14
0x180020589  pop     r13
0x18002058b  pop     r12
0x18002058d  pop     rdi
0x18002058e  pop     rsi
0x18002058f  pop     rbp
0x180020590  pop     rbx
0x180020591  retn
```
