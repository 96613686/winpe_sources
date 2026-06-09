# CopySsdpRequest(_SSDP_REQUEST *,_SSDP_REQUEST const *)

- ea: `0x180006eb8`
- end: `0x180007164`
- name: `?CopySsdpRequest@@YAHPEAU_SSDP_REQUEST@@PEBU1@@Z`
- size: `684`
- prototype: `__int64 __fastcall(struct _NETWORK_LOCATION_INFO **, const struct _SSDP_REQUEST *)`
- caller_count: `8`
- callee_count: `5`
- tags: ``

## callers

- `0x180005740`
- `0x180005d90`
- `0x1800084e0`
- `0x1800095d8`
- `0x180009fd0`
- `0x180015c78`
- `0x180019180`
- `0x18002e724`

## callees

- `0x180006d70`
- `0x180006eb8`
- `0x180017400`
- `0x18002735c`
- `0x1800338f8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180006ee9`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180006f3f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180006fea`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180007030`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000707e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800070d5`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180007116`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180006ee9`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180006f3f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180006fea`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180007030`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000707e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800070d5`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180007116`

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
0x180006eb8  push    rbx
0x180006eba  push    rbp
0x180006ebb  push    rsi
0x180006ebc  push    rdi
0x180006ebd  push    r14
0x180006ebf  push    r15
0x180006ec1  sub     rsp, 28h
0x180006ec5  mov     rbx, rdx
0x180006ec8  mov     rsi, rcx
0x180006ecb  xor     edx, edx; Val
0x180006ecd  lea     r8d, [rdx+58h]; Size
0x180006ed1  call    memset_0
0x180006ed6  mov     eax, [rbx]
0x180006ed8  mov     [rsi], eax
0x180006eda  mov     eax, [rbx+48h]
0x180006edd  mov     edi, eax
0x180006edf  mov     [rsi+48h], eax
0x180006ee2  shl     rdi, 3
0x180006ee6  mov     rcx, rdi; Size
0x180006ee9  call    cs:__imp_malloc
0x180006eef  xor     r15d, r15d
0x180006ef2  mov     [rsi+50h], rax
0x180006ef6  test    rax, rax
0x180006ef9  jz      loc_180006FBB
0x180006eff  mov     r8, rdi; Size
0x180006f02  xor     edx, edx; Val
0x180006f04  mov     rcx, rax; void *
0x180006f07  call    memset_0
0x180006f0c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180006f10  mov     ebp, r15d
0x180006f13  cmp     ebp, [rbx+48h]
0x180006f16  jnb     loc_180006FD2
0x180006f1c  mov     rax, [rbx+50h]
0x180006f20  mov     r14d, ebp
0x180006f23  mov     rdx, [rax+r14*8]
0x180006f27  test    rdx, rdx
0x180006f2a  jz      loc_180006FB1
0x180006f30  mov     rcx, rdi
0x180006f33  inc     rcx
0x180006f36  cmp     [rdx+rcx], r15b
0x180006f3a  jnz     short loc_180006F33
0x180006f3c  inc     rcx; Size
0x180006f3f  call    cs:__imp_malloc
0x180006f45  mov     rcx, [rsi+50h]
0x180006f49  mov     [rcx+r14*8], rax
0x180006f4d  mov     rax, [rsi+50h]
0x180006f51  mov     rdx, [rax+r14*8]
0x180006f55  test    rdx, rdx
0x180006f58  jz      short loc_180006FBB
0x180006f5a  mov     rax, [rbx+50h]
0x180006f5e  mov     rcx, rdi
0x180006f61  mov     r8, [rax+r14*8]
0x180006f65  inc     rcx
0x180006f68  cmp     [r8+rcx], r15b
0x180006f6c  jnz     short loc_180006F65
0x180006f6e  add     rcx, 1
0x180006f72  jz      short loc_180006FBB
0x180006f74  cmp     rcx, 7FFFFFFFh
0x180006f7b  ja      short loc_180006FB8
0x180006f7d  mov     eax, 7FFFFFFEh
0x180006f82  test    rax, rax
0x180006f85  jz      short loc_180006FA1
0x180006f87  mov     r9b, [r8]
0x180006f8a  test    r9b, r9b
0x180006f8d  jz      short loc_180006FA1
0x180006f8f  mov     [rdx], r9b
0x180006f92  inc     r8
0x180006f95  inc     rdx
0x180006f98  dec     rax
0x180006f9b  sub     rcx, 1
0x180006f9f  jnz     short loc_180006F82
0x180006fa1  test    rcx, rcx
0x180006fa4  lea     rax, [rdx-1]
0x180006fa8  cmovnz  rax, rdx
0x180006fac  mov     [rax], r15b
0x180006faf  jz      short loc_180006FBB
0x180006fb1  inc     ebp
0x180006fb3  jmp     loc_180006F13
0x180006fb8  mov     [rdx], r15b
0x180006fbb  mov     rcx, rsi; struct _SSDP_REQUEST *
0x180006fbe  call    ?FreeSsdpRequest@@YAXPEAU_SSDP_REQUEST@@@Z; FreeSsdpRequest(_SSDP_REQUEST *)
0x180006fc3  xor     eax, eax
0x180006fc5  add     rsp, 28h
0x180006fc9  pop     r15
0x180006fcb  pop     r14
0x180006fcd  pop     rdi
0x180006fce  pop     rsi
0x180006fcf  pop     rbp
0x180006fd0  pop     rbx
0x180006fd1  retn
0x180006fd2  mov     rax, [rbx+18h]
0x180006fd6  test    rax, rax
0x180006fd9  jz      short loc_180007018
0x180006fdb  mov     rcx, rdi
0x180006fde  inc     rcx
0x180006fe1  cmp     [rax+rcx], r15b
0x180006fe5  jnz     short loc_180006FDE
0x180006fe7  inc     rcx; Size
0x180006fea  call    cs:__imp_malloc
0x180006ff0  mov     [rsi+18h], rax
0x180006ff4  test    rax, rax
0x180006ff7  jz      short loc_180006FBB
0x180006ff9  mov     r8, [rbx+18h]; char *
0x180006ffd  mov     rdx, rdi
0x180007000  inc     rdx
0x180007003  cmp     [r8+rdx], r15b
0x180007007  jnz     short loc_180007000
0x180007009  inc     rdx; unsigned __int64
0x18000700c  mov     rcx, rax; char *
0x18000700f  call    ?StringCbCopyA@@YAJPEAD_KPEBD@Z; StringCbCopyA(char *,unsigned __int64,char const *)
0x180007014  test    eax, eax
0x180007016  js      short loc_180006FBB
0x180007018  mov     rax, [rbx+10h]
0x18000701c  test    rax, rax
0x18000701f  jz      short loc_180007066
0x180007021  mov     rcx, rdi
0x180007024  inc     rcx
0x180007027  cmp     [rax+rcx], r15b
0x18000702b  jnz     short loc_180007024
0x18000702d  inc     rcx; Size
0x180007030  call    cs:__imp_malloc
0x180007036  mov     [rsi+10h], rax
0x18000703a  test    rax, rax
0x18000703d  jz      loc_180006FBB
0x180007043  mov     r8, [rbx+10h]; char *
0x180007047  mov     rdx, rdi
0x18000704a  inc     rdx
0x18000704d  cmp     [r8+rdx], r15b
0x180007051  jnz     short loc_18000704A
0x180007053  inc     rdx; unsigned __int64
0x180007056  mov     rcx, rax; char *
0x180007059  call    ?StringCbCopyA@@YAJPEAD_KPEBD@Z; StringCbCopyA(char *,unsigned __int64,char const *)
0x18000705e  test    eax, eax
0x180007060  js      loc_180006FBB
0x180007066  mov     rax, [rbx+8]
0x18000706a  test    rax, rax
0x18000706d  jz      short loc_1800070B4
0x18000706f  mov     rcx, rdi
0x180007072  inc     rcx
0x180007075  cmp     [rax+rcx], r15b
0x180007079  jnz     short loc_180007072
0x18000707b  inc     rcx; Size
0x18000707e  call    cs:__imp_malloc
0x180007084  mov     [rsi+8], rax
0x180007088  test    rax, rax
0x18000708b  jz      loc_180006FBB
0x180007091  mov     r8, [rbx+8]; char *
0x180007095  mov     rdx, rdi
0x180007098  inc     rdx
0x18000709b  cmp     [r8+rdx], r15b
0x18000709f  jnz     short loc_180007098
0x1800070a1  inc     rdx; unsigned __int64
0x1800070a4  mov     rcx, rax; char *
0x1800070a7  call    ?StringCbCopyA@@YAJPEAD_KPEBD@Z; StringCbCopyA(char *,unsigned __int64,char const *)
0x1800070ac  test    eax, eax
0x1800070ae  js      loc_180006FBB
0x1800070b4  movups  xmm0, xmmword ptr [rbx+20h]
0x1800070b8  movdqu  xmmword ptr [rsi+20h], xmm0
0x1800070bd  mov     rax, [rbx+30h]
0x1800070c1  test    rax, rax
0x1800070c4  jz      short loc_180007109
0x1800070c6  mov     rcx, rdi
0x1800070c9  inc     rcx
0x1800070cc  cmp     [rax+rcx], r15b
0x1800070d0  jnz     short loc_1800070C9
0x1800070d2  inc     rcx; Size
0x1800070d5  call    cs:__imp_malloc
0x1800070db  mov     [rsi+30h], rax
0x1800070df  test    rax, rax
0x1800070e2  jz      loc_180006FBB
0x1800070e8  mov     r8, [rbx+30h]; char *
0x1800070ec  inc     rdi
0x1800070ef  cmp     [r8+rdi], r15b
0x1800070f3  jnz     short loc_1800070EC
0x1800070f5  lea     rdx, [rdi+1]; unsigned __int64
0x1800070f9  mov     rcx, rax; char *
0x1800070fc  call    ?StringCbCopyA@@YAJPEAD_KPEBD@Z; StringCbCopyA(char *,unsigned __int64,char const *)
0x180007101  test    eax, eax
0x180007103  js      loc_180006FBB
0x180007109  cmp     [rbx+40h], r15
0x18000710d  jz      short loc_18000715A
0x18000710f  mov     ecx, [rbx+38h]
0x180007112  shl     rcx, 5; Size
0x180007116  call    cs:__imp_malloc
0x18000711c  mov     [rsi+40h], rax
0x180007120  test    rax, rax
0x180007123  jz      loc_180006FBB
0x180007129  mov     r8d, [rbx+38h]
0x18000712d  xor     edx, edx; Val
0x18000712f  shl     r8, 5; Size
0x180007133  mov     rcx, rax; void *
0x180007136  call    memset_0
0x18000713b  mov     r8d, [rbx+38h]; unsigned int
0x18000713f  mov     rdx, [rbx+40h]; struct _NETWORK_LOCATION_INFO *
0x180007143  mov     rcx, [rsi+40h]; struct _NETWORK_LOCATION_INFO *
0x180007147  call    ?CopyNetworkLocationInfo@@YAJPEAU_NETWORK_LOCATION_INFO@@0K@Z; CopyNetworkLocationInfo(_NETWORK_LOCATION_INFO *,_NETWORK_LOCATION_INFO *,ulong)
0x18000714c  test    eax, eax
0x18000714e  jnz     loc_180006FBB
0x180007154  mov     ecx, [rbx+38h]
0x180007157  mov     [rsi+38h], ecx
0x18000715a  mov     eax, 1
0x18000715f  jmp     loc_180006FC5
```
