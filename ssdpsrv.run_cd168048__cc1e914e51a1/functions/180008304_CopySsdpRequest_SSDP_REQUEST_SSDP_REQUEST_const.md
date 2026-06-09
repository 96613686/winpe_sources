# CopySsdpRequest(_SSDP_REQUEST *,_SSDP_REQUEST const *)

- ea: `0x180008304`
- end: `0x1800085db`
- name: `?CopySsdpRequest@@YAHPEAU_SSDP_REQUEST@@PEBU1@@Z`
- size: `727`
- prototype: `__int64 __fastcall(struct _NETWORK_LOCATION_INFO **, const struct _SSDP_REQUEST *)`
- caller_count: `8`
- callee_count: `5`
- tags: ``

## callers

- `0x180006a60`
- `0x1800070d0`
- `0x180009a84`
- `0x18000ac50`
- `0x18000b630`
- `0x18000baf8`
- `0x18001a370`
- `0x1800308bc`

## callees

- `0x180008190`
- `0x180008304`
- `0x180019850`
- `0x18002911c`
- `0x180036394`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180008335`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180008391`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180008443`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000848f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800084e3`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180008540`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180008587`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180008335`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180008391`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180008443`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000848f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800084e3`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180008540`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180008587`

## pseudocode

```c
__int64 __fastcall CopySsdpRequest(struct _NETWORK_LOCATION_INFO **a1, const struct _SSDP_REQUEST *a2)
{
  unsigned int v4; // eax
  size_t v5; // rdi
  struct _NETWORK_LOCATION_INFO *v6; // rax
  __int64 v7; // rdi
  unsigned int i; // ebp
  __int64 v9; // rdx
  __int64 v10; // rcx
  _BYTE *v11; // rdx
  __int64 v12; // rcx
  _BYTE *v13; // r8
  unsigned __int64 v14; // rcx
  __int64 v15; // rax
  _BYTE *v16; // rax
  __int64 v18; // rax
  __int64 v19; // rcx
  char *v20; // rax
  const char *v21; // r8
  __int64 v22; // rdx
  __int64 v23; // rax
  __int64 v24; // rcx
  char *v25; // rax
  const char *v26; // r8
  __int64 v27; // rdx
  __int64 v28; // rax
  __int64 v29; // rcx
  char *v30; // rax
  const char *v31; // r8
  __int64 v32; // rdx
  __int64 v33; // rax
  __int64 v34; // rcx
  char *v35; // rax
  const char *v36; // r8
  struct _NETWORK_LOCATION_INFO *v37; // rax

  memset_0(a1, 0, 0x58u);
  *(_DWORD *)a1 = *(_DWORD *)a2;
  v4 = *((_DWORD *)a2 + 18);
  *((_DWORD *)a1 + 18) = v4;
  v5 = 8LL * v4;
  v6 = (struct _NETWORK_LOCATION_INFO *)malloc(v5);
  a1[10] = v6;
  if ( !v6 )
    goto LABEL_21;
  memset_0(v6, 0, v5);
  v7 = -1;
  for ( i = 0; i < *((_DWORD *)a2 + 18); ++i )
  {
    v9 = *(_QWORD *)(*((_QWORD *)a2 + 10) + 8LL * i);
    if ( v9 )
    {
      v10 = -1;
      do
        ++v10;
      while ( *(_BYTE *)(v9 + v10) );
      *((_QWORD *)a1[10] + i) = malloc(v10 + 1);
      v11 = (_BYTE *)*((_QWORD *)a1[10] + i);
      if ( !v11 )
        goto LABEL_21;
      v12 = -1;
      v13 = *(_BYTE **)(*((_QWORD *)a2 + 10) + 8LL * i);
      do
        ++v12;
      while ( v13[v12] );
      v14 = v12 + 1;
      if ( !v14 )
        goto LABEL_21;
      if ( v14 > 0x7FFFFFFF )
      {
        *v11 = 0;
        goto LABEL_21;
      }
      v15 = 2147483646;
      do
      {
        if ( !v15 )
          break;
        if ( !*v13 )
          break;
        *v11++ = *v13++;
        --v15;
        --v14;
      }
      while ( v14 );
      v16 = v11 - 1;
      if ( v14 )
        v16 = v11;
      *v16 = 0;
      if ( !v14 )
        goto LABEL_21;
    }
  }
  v18 = *((_QWORD *)a2 + 3);
  if ( v18 )
  {
    v19 = -1;
    do
      ++v19;
    while ( *(_BYTE *)(v18 + v19) );
    v20 = (char *)malloc(v19 + 1);
    a1[3] = (struct _NETWORK_LOCATION_INFO *)v20;
    if ( !v20 )
      goto LABEL_21;
    v21 = (const char *)*((_QWORD *)a2 + 3);
    v22 = -1;
    do
      ++v22;
    while ( v21[v22] );
    if ( (int)StringCbCopyA(v20, v22 + 1, v21) < 0 )
      goto LABEL_21;
  }
  v23 = *((_QWORD *)a2 + 2);
  if ( v23 )
  {
    v24 = -1;
    do
      ++v24;
    while ( *(_BYTE *)(v23 + v24) );
    v25 = (char *)malloc(v24 + 1);
    a1[2] = (struct _NETWORK_LOCATION_INFO *)v25;
    if ( !v25 )
      goto LABEL_21;
    v26 = (const char *)*((_QWORD *)a2 + 2);
    v27 = -1;
    do
      ++v27;
    while ( v26[v27] );
    if ( (int)StringCbCopyA(v25, v27 + 1, v26) < 0 )
      goto LABEL_21;
  }
  v28 = *((_QWORD *)a2 + 1);
  if ( v28 )
  {
    v29 = -1;
    do
      ++v29;
    while ( *(_BYTE *)(v28 + v29) );
    v30 = (char *)malloc(v29 + 1);
    a1[1] = (struct _NETWORK_LOCATION_INFO *)v30;
    if ( !v30 )
      goto LABEL_21;
    v31 = (const char *)*((_QWORD *)a2 + 1);
    v32 = -1;
    do
      ++v32;
    while ( v31[v32] );
    if ( (int)StringCbCopyA(v30, v32 + 1, v31) < 0 )
      goto LABEL_21;
  }
  *((_OWORD *)a1 + 2) = *((_OWORD *)a2 + 2);
  v33 = *((_QWORD *)a2 + 6);
  if ( v33 )
  {
    v34 = -1;
    do
      ++v34;
    while ( *(_BYTE *)(v33 + v34) );
    v35 = (char *)malloc(v34 + 1);
    a1[6] = (struct _NETWORK_LOCATION_INFO *)v35;
    if ( !v35 )
      goto LABEL_21;
    v36 = (const char *)*((_QWORD *)a2 + 6);
    do
      ++v7;
    while ( v36[v7] );
    if ( (int)StringCbCopyA(v35, v7 + 1, v36) < 0 )
      goto LABEL_21;
  }
  if ( *((_QWORD *)a2 + 8) )
  {
    v37 = (struct _NETWORK_LOCATION_INFO *)malloc(32LL * *((unsigned int *)a2 + 14));
    a1[8] = v37;
    if ( v37 )
    {
      memset_0(v37, 0, 32LL * *((unsigned int *)a2 + 14));
      if ( !(unsigned int)CopyNetworkLocationInfo(
                            a1[8],
                            *((struct _NETWORK_LOCATION_INFO **)a2 + 8),
                            *((_DWORD *)a2 + 14)) )
      {
        *((_DWORD *)a1 + 14) = *((_DWORD *)a2 + 14);
        return 1;
      }
    }
LABEL_21:
    FreeSsdpRequest((struct _SSDP_REQUEST *)a1);
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180008304  push    rbx
0x180008306  push    rbp
0x180008307  push    rsi
0x180008308  push    rdi
0x180008309  push    r14
0x18000830b  push    r15
0x18000830d  sub     rsp, 28h
0x180008311  mov     rbx, rdx
0x180008314  mov     rsi, rcx
0x180008317  xor     edx, edx; Val
0x180008319  lea     r8d, [rdx+58h]; Size
0x18000831d  call    memset_0
0x180008322  mov     eax, [rbx]
0x180008324  mov     [rsi], eax
0x180008326  mov     eax, [rbx+48h]
0x180008329  mov     edi, eax
0x18000832b  mov     [rsi+48h], eax
0x18000832e  shl     rdi, 3
0x180008332  mov     rcx, rdi; Size
0x180008335  call    cs:__imp_malloc
0x18000833c  nop     dword ptr [rax+rax+00h]
0x180008341  xor     r15d, r15d
0x180008344  mov     [rsi+50h], rax
0x180008348  test    rax, rax
0x18000834b  jz      loc_180008413
0x180008351  mov     r8, rdi; Size
0x180008354  xor     edx, edx; Val
0x180008356  mov     rcx, rax; void *
0x180008359  call    memset_0
0x18000835e  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180008362  mov     ebp, r15d
0x180008365  cmp     ebp, [rbx+48h]
0x180008368  jnb     loc_18000842B
0x18000836e  mov     rax, [rbx+50h]
0x180008372  mov     r14d, ebp
0x180008375  mov     rdx, [rax+r14*8]
0x180008379  test    rdx, rdx
0x18000837c  jz      loc_180008409
0x180008382  mov     rcx, rdi
0x180008385  inc     rcx
0x180008388  cmp     [rdx+rcx], r15b
0x18000838c  jnz     short loc_180008385
0x18000838e  inc     rcx; Size
0x180008391  call    cs:__imp_malloc
0x180008398  nop     dword ptr [rax+rax+00h]
0x18000839d  mov     rcx, [rsi+50h]
0x1800083a1  mov     [rcx+r14*8], rax
0x1800083a5  mov     rax, [rsi+50h]
0x1800083a9  mov     rdx, [rax+r14*8]
0x1800083ad  test    rdx, rdx
0x1800083b0  jz      short loc_180008413
0x1800083b2  mov     rax, [rbx+50h]
0x1800083b6  mov     rcx, rdi
0x1800083b9  mov     r8, [rax+r14*8]
0x1800083bd  inc     rcx
0x1800083c0  cmp     [r8+rcx], r15b
0x1800083c4  jnz     short loc_1800083BD
0x1800083c6  add     rcx, 1
0x1800083ca  jz      short loc_180008413
0x1800083cc  cmp     rcx, 7FFFFFFFh
0x1800083d3  ja      short loc_180008410
0x1800083d5  mov     eax, 7FFFFFFEh
0x1800083da  test    rax, rax
0x1800083dd  jz      short loc_1800083F9
0x1800083df  mov     r9b, [r8]
0x1800083e2  test    r9b, r9b
0x1800083e5  jz      short loc_1800083F9
0x1800083e7  mov     [rdx], r9b
0x1800083ea  inc     r8
0x1800083ed  inc     rdx
0x1800083f0  dec     rax
0x1800083f3  sub     rcx, 1
0x1800083f7  jnz     short loc_1800083DA
0x1800083f9  test    rcx, rcx
0x1800083fc  lea     rax, [rdx-1]
0x180008400  cmovnz  rax, rdx
0x180008404  mov     [rax], r15b
0x180008407  jz      short loc_180008413
0x180008409  inc     ebp
0x18000840b  jmp     loc_180008365
0x180008410  mov     [rdx], r15b
0x180008413  mov     rcx, rsi; struct _SSDP_REQUEST *
0x180008416  call    ?FreeSsdpRequest@@YAXPEAU_SSDP_REQUEST@@@Z; FreeSsdpRequest(_SSDP_REQUEST *)
0x18000841b  xor     eax, eax
0x18000841d  add     rsp, 28h
0x180008421  pop     r15
0x180008423  pop     r14
0x180008425  pop     rdi
0x180008426  pop     rsi
0x180008427  pop     rbp
0x180008428  pop     rbx
0x180008429  retn
0x18000842b  mov     rax, [rbx+18h]
0x18000842f  test    rax, rax
0x180008432  jz      short loc_180008477
0x180008434  mov     rcx, rdi
0x180008437  inc     rcx
0x18000843a  cmp     [rax+rcx], r15b
0x18000843e  jnz     short loc_180008437
0x180008440  inc     rcx; Size
0x180008443  call    cs:__imp_malloc
0x18000844a  nop     dword ptr [rax+rax+00h]
0x18000844f  mov     [rsi+18h], rax
0x180008453  test    rax, rax
0x180008456  jz      short loc_180008413
0x180008458  mov     r8, [rbx+18h]; char *
0x18000845c  mov     rdx, rdi
0x18000845f  inc     rdx
0x180008462  cmp     [r8+rdx], r15b
0x180008466  jnz     short loc_18000845F
0x180008468  inc     rdx; unsigned __int64
0x18000846b  mov     rcx, rax; char *
0x18000846e  call    ?StringCbCopyA@@YAJPEAD_KPEBD@Z; StringCbCopyA(char *,unsigned __int64,char const *)
0x180008473  test    eax, eax
0x180008475  js      short loc_180008413
0x180008477  mov     rax, [rbx+10h]
0x18000847b  test    rax, rax
0x18000847e  jz      short loc_1800084CB
0x180008480  mov     rcx, rdi
0x180008483  inc     rcx
0x180008486  cmp     [rax+rcx], r15b
0x18000848a  jnz     short loc_180008483
0x18000848c  inc     rcx; Size
0x18000848f  call    cs:__imp_malloc
0x180008496  nop     dword ptr [rax+rax+00h]
0x18000849b  mov     [rsi+10h], rax
0x18000849f  test    rax, rax
0x1800084a2  jz      loc_180008413
0x1800084a8  mov     r8, [rbx+10h]; char *
0x1800084ac  mov     rdx, rdi
0x1800084af  inc     rdx
0x1800084b2  cmp     [r8+rdx], r15b
0x1800084b6  jnz     short loc_1800084AF
0x1800084b8  inc     rdx; unsigned __int64
0x1800084bb  mov     rcx, rax; char *
0x1800084be  call    ?StringCbCopyA@@YAJPEAD_KPEBD@Z; StringCbCopyA(char *,unsigned __int64,char const *)
0x1800084c3  test    eax, eax
0x1800084c5  js      loc_180008413
0x1800084cb  mov     rax, [rbx+8]
0x1800084cf  test    rax, rax
0x1800084d2  jz      short loc_18000851F
0x1800084d4  mov     rcx, rdi
0x1800084d7  inc     rcx
0x1800084da  cmp     [rax+rcx], r15b
0x1800084de  jnz     short loc_1800084D7
0x1800084e0  inc     rcx; Size
0x1800084e3  call    cs:__imp_malloc
0x1800084ea  nop     dword ptr [rax+rax+00h]
0x1800084ef  mov     [rsi+8], rax
0x1800084f3  test    rax, rax
0x1800084f6  jz      loc_180008413
0x1800084fc  mov     r8, [rbx+8]; char *
0x180008500  mov     rdx, rdi
0x180008503  inc     rdx
0x180008506  cmp     [r8+rdx], r15b
0x18000850a  jnz     short loc_180008503
0x18000850c  inc     rdx; unsigned __int64
0x18000850f  mov     rcx, rax; char *
0x180008512  call    ?StringCbCopyA@@YAJPEAD_KPEBD@Z; StringCbCopyA(char *,unsigned __int64,char const *)
0x180008517  test    eax, eax
0x180008519  js      loc_180008413
0x18000851f  movups  xmm0, xmmword ptr [rbx+20h]
0x180008523  movdqu  xmmword ptr [rsi+20h], xmm0
0x180008528  mov     rax, [rbx+30h]
0x18000852c  test    rax, rax
0x18000852f  jz      short loc_18000857A
0x180008531  mov     rcx, rdi
0x180008534  inc     rcx
0x180008537  cmp     [rax+rcx], r15b
0x18000853b  jnz     short loc_180008534
0x18000853d  inc     rcx; Size
0x180008540  call    cs:__imp_malloc
0x180008547  nop     dword ptr [rax+rax+00h]
0x18000854c  mov     [rsi+30h], rax
0x180008550  test    rax, rax
0x180008553  jz      loc_180008413
0x180008559  mov     r8, [rbx+30h]; char *
0x18000855d  inc     rdi
0x180008560  cmp     [r8+rdi], r15b
0x180008564  jnz     short loc_18000855D
0x180008566  lea     rdx, [rdi+1]; unsigned __int64
0x18000856a  mov     rcx, rax; char *
0x18000856d  call    ?StringCbCopyA@@YAJPEAD_KPEBD@Z; StringCbCopyA(char *,unsigned __int64,char const *)
0x180008572  test    eax, eax
0x180008574  js      loc_180008413
0x18000857a  cmp     [rbx+40h], r15
0x18000857e  jz      short loc_1800085D1
0x180008580  mov     ecx, [rbx+38h]
0x180008583  shl     rcx, 5; Size
0x180008587  call    cs:__imp_malloc
0x18000858e  nop     dword ptr [rax+rax+00h]
0x180008593  mov     [rsi+40h], rax
0x180008597  test    rax, rax
0x18000859a  jz      loc_180008413
0x1800085a0  mov     r8d, [rbx+38h]
0x1800085a4  xor     edx, edx; Val
0x1800085a6  shl     r8, 5; Size
0x1800085aa  mov     rcx, rax; void *
0x1800085ad  call    memset_0
0x1800085b2  mov     r8d, [rbx+38h]; unsigned int
0x1800085b6  mov     rdx, [rbx+40h]; struct _NETWORK_LOCATION_INFO *
0x1800085ba  mov     rcx, [rsi+40h]; struct _NETWORK_LOCATION_INFO *
0x1800085be  call    ?CopyNetworkLocationInfo@@YAJPEAU_NETWORK_LOCATION_INFO@@0K@Z; CopyNetworkLocationInfo(_NETWORK_LOCATION_INFO *,_NETWORK_LOCATION_INFO *,ulong)
0x1800085c3  test    eax, eax
0x1800085c5  jnz     loc_180008413
0x1800085cb  mov     ecx, [rbx+38h]
0x1800085ce  mov     [rsi+38h], ecx
0x1800085d1  mov     eax, 1
0x1800085d6  jmp     loc_18000841D
```
