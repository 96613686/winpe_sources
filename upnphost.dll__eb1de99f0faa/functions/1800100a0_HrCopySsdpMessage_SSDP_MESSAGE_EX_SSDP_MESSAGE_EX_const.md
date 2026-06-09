# HrCopySsdpMessage(_SSDP_MESSAGE_EX * *,_SSDP_MESSAGE_EX const *)

- ea: `0x1800100a0`
- end: `0x18001057d`
- name: `?HrCopySsdpMessage@@YAJPEAPEAU_SSDP_MESSAGE_EX@@PEBU1@@Z`
- size: `1245`
- prototype: `__int64 __fastcall(struct _SSDP_MESSAGE_EX **, const struct _SSDP_MESSAGE_EX *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000fdf4`

## callees

- `0x18000db4c`
- `0x1800100a0`
- `0x180010590`
- `0x18003ae80`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001044f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180010492`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800104ae`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001044f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180010492`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800104ae`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800100d1`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800101a6`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001025a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180010336`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800104e2`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800100d1`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800101a6`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001025a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180010336`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800104e2`
- `SSDPAPI!FreeSsdpMessageEx` at `0x1800102cd`
- `SSDPAPI!FreeSsdpMessageEx` at `0x1800102cd`

## string_xrefs

- `0x18001055b`: `HrCopySsdpMessage`

## pseudocode

```c
__int64 __fastcall HrCopySsdpMessage(struct _SSDP_MESSAGE_EX **a1, const struct _SSDP_MESSAGE_EX *a2)
{
  char *v3; // rax
  char *v4; // r15
  const char *v5; // rcx
  unsigned int v6; // esi
  int v7; // r13d
  char *v8; // rcx
  const char *v9; // rcx
  const char *v10; // rcx
  const char *v11; // rcx
  _BYTE *v12; // rbx
  __int64 v13; // rbp
  __int64 v14; // r14
  void *v15; // r8
  __int64 v16; // rax
  bool v17; // zf
  unsigned int v18; // esi
  __int64 v19; // rdi
  _BYTE *v20; // rax
  __int64 v21; // rcx
  _BYTE *v22; // rdx
  _BYTE *v23; // rax
  const char *v24; // rcx
  _BYTE *v25; // rbx
  _BYTE *v26; // rbx
  void *v27; // rdx
  unsigned int v28; // esi
  __int64 v29; // rdi
  _BYTE *v30; // rax
  _BYTE *v31; // rcx
  _BYTE *v32; // rax
  void *v34; // r8
  __int64 v35; // rax
  unsigned int v36; // esi
  __int64 v37; // rdi
  _BYTE *v38; // rax
  __int64 v39; // rcx
  _BYTE *v40; // rdx
  _BYTE *v41; // rax
  char *v42; // rax
  __int64 v43; // rdi
  char *v44; // rax
  char *v45; // rax
  char *v46; // rax
  _QWORD *v47; // rax
  _QWORD *v48; // r14
  char *v49; // rax

  v3 = (char *)malloc(0x78u);
  v4 = v3;
  if ( !v3 )
    goto LABEL_44;
  v5 = (const char *)*((_QWORD *)a2 + 2);
  *((_QWORD *)v3 + 2) = 0;
  *(_OWORD *)(v3 + 88) = 0;
  *((_QWORD *)v3 + 13) = 0;
  v6 = 0;
  *((_DWORD *)v3 + 11) = *((_DWORD *)a2 + 11);
  *((_DWORD *)v3 + 10) = *((_DWORD *)a2 + 10);
  *((_QWORD *)v3 + 14) = 0;
  *(_OWORD *)(v3 + 56) = *(_OWORD *)((char *)a2 + 56);
  if ( v5 )
  {
    v7 = -2147024882;
    v8 = SzaDupSza(v5);
    if ( v8 )
      v7 = 0;
  }
  else
  {
    v7 = 0;
    v8 = 0;
  }
  *((_QWORD *)v4 + 2) = v8;
  v9 = (const char *)*((_QWORD *)a2 + 9);
  if ( v9 && v7 >= 0 )
  {
    v42 = SzaDupSza(v9);
    *((_QWORD *)v4 + 9) = v42;
    if ( !v42 )
      v7 = -2147024882;
  }
  else
  {
    *((_QWORD *)v4 + 9) = 0;
  }
  v10 = (const char *)*((_QWORD *)a2 + 10);
  if ( v10 && v7 >= 0 )
  {
    v44 = SzaDupSza(v10);
    *((_QWORD *)v4 + 10) = v44;
    if ( !v44 )
      v7 = -2147024882;
  }
  else
  {
    *((_QWORD *)v4 + 10) = 0;
  }
  v11 = (const char *)*((_QWORD *)a2 + 6);
  if ( v11 && v7 >= 0 )
  {
    v45 = SzaDupSza(v11);
    *((_QWORD *)v4 + 6) = v45;
    if ( !v45 )
      v7 = -2147024882;
  }
  else
  {
    *((_QWORD *)v4 + 6) = 0;
  }
  v12 = (_BYTE *)*((_QWORD *)a2 + 1);
  v13 = 2147483646;
  v14 = -1;
  if ( !v12 || v7 < 0 )
  {
    *((_QWORD *)v4 + 1) = 0;
    goto LABEL_25;
  }
  v15 = 0;
  v16 = -1;
  do
    v17 = v12[++v16] == 0;
  while ( !v17 );
  v18 = v16 + 1;
  if ( (_DWORD)v16 != -1 )
  {
    v19 = v18;
    v20 = malloc(v18);
    v15 = v20;
    if ( v20 )
    {
      if ( v18 > 0x7FFFFFFF )
      {
        *v20 = 0;
      }
      else
      {
        v21 = 2147483646;
        v22 = v20;
        do
        {
          if ( !v21 )
            break;
          if ( !*v12 )
            break;
          *v22++ = *v12++;
          --v21;
          --v19;
        }
        while ( v19 );
        v23 = v22 - 1;
        if ( v19 )
          v23 = v22;
        *v23 = 0;
        if ( v19 )
          goto LABEL_24;
      }
      free(v15);
      v6 = 0;
      *((_QWORD *)v4 + 1) = 0;
      goto LABEL_81;
    }
  }
LABEL_24:
  v6 = 0;
  *((_QWORD *)v4 + 1) = v15;
  if ( !v15 )
LABEL_81:
    v7 = -2147024882;
LABEL_25:
  v24 = (const char *)*((_QWORD *)a2 + 4);
  if ( v24 && v7 >= 0 )
  {
    v46 = SzaDupSza(v24);
    *((_QWORD *)v4 + 4) = v46;
    if ( !v46 )
      v7 = -2147024882;
  }
  else
  {
    *((_QWORD *)v4 + 4) = 0;
  }
  v25 = *(_BYTE **)a2;
  if ( !*(_QWORD *)a2 || v7 < 0 )
  {
    *(_QWORD *)v4 = 0;
    goto LABEL_29;
  }
  v34 = 0;
  v35 = -1;
  do
    v17 = v25[++v35] == 0;
  while ( !v17 );
  v36 = v35 + 1;
  if ( (_DWORD)v35 != -1 )
  {
    v37 = v36;
    v38 = malloc(v36);
    v34 = v38;
    if ( v38 )
    {
      if ( v36 > 0x7FFFFFFF )
      {
        *v38 = 0;
      }
      else
      {
        v39 = 2147483646;
        v40 = v38;
        do
        {
          if ( !v39 )
            break;
          if ( !*v25 )
            break;
          *v40++ = *v25++;
          --v39;
          --v37;
        }
        while ( v37 );
        v41 = v40 - 1;
        if ( v37 )
          v41 = v40;
        *v41 = 0;
        if ( v37 )
          goto LABEL_62;
      }
      free(v34);
      v6 = 0;
      *(_QWORD *)v4 = 0;
LABEL_87:
      v7 = -2147024882;
      goto LABEL_29;
    }
  }
LABEL_62:
  v6 = 0;
  *(_QWORD *)v4 = v34;
  if ( !v34 )
    goto LABEL_87;
LABEL_29:
  v26 = (_BYTE *)*((_QWORD *)a2 + 3);
  if ( !v26 || v7 < 0 )
  {
    *((_QWORD *)v4 + 3) = 0;
    if ( v7 < 0 )
      goto LABEL_46;
LABEL_68:
    v43 = *((unsigned int *)a2 + 26);
    if ( (_DWORD)v43 && *((_QWORD *)a2 + 14) )
    {
      *((_DWORD *)v4 + 26) = v43;
      v47 = malloc(8 * v43);
      *((_QWORD *)v4 + 14) = v47;
      v48 = v47;
      if ( !v47 )
        goto LABEL_44;
      memset_0(v47, 0, 8 * v43);
      while ( v6 < (unsigned int)v43 )
      {
        v49 = SzaDupSza(*(const char **)(8LL * v6 + *((_QWORD *)a2 + 14)));
        v48[v6] = v49;
        if ( !v49 )
          goto LABEL_44;
        ++v6;
      }
    }
    *a1 = (struct _SSDP_MESSAGE_EX *)v4;
    goto LABEL_47;
  }
  v27 = 0;
  do
    v17 = v26[++v14] == 0;
  while ( !v17 );
  v28 = v14 + 1;
  if ( (_DWORD)v14 != -1 )
  {
    v29 = v28;
    v30 = malloc(v28);
    v27 = v30;
    if ( v30 )
    {
      if ( v28 > 0x7FFFFFFF )
      {
        *v30 = 0;
      }
      else
      {
        v31 = v30;
        do
        {
          if ( !v13 )
            break;
          if ( !*v26 )
            break;
          *v31++ = *v26++;
          --v13;
          --v29;
        }
        while ( v29 );
        v32 = v31 - 1;
        if ( v29 )
          v32 = v31;
        *v32 = 0;
        if ( v29 )
          goto LABEL_43;
      }
      free(v27);
      *((_QWORD *)v4 + 3) = 0;
      goto LABEL_44;
    }
  }
LABEL_43:
  *((_QWORD *)v4 + 3) = v27;
  if ( v27 )
  {
    v6 = 0;
    goto LABEL_68;
  }
LABEL_44:
  v7 = -2147024882;
LABEL_46:
  FreeSsdpMessageEx(v4);
LABEL_47:
  if ( v7 && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      (unsigned int)WPP_46aece34ec5f3261a433300ce9b09bc3_Traceguids,
      (unsigned int)"HrCopySsdpMessage",
      v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800100a0  mov     rax, rsp
0x1800100a3  mov     [rax+8], rcx
0x1800100a7  push    r13
0x1800100a9  sub     rsp, 50h
0x1800100ad  mov     [rax+10h], rbx
0x1800100b1  mov     ecx, 78h ; 'x'; Size
0x1800100b6  mov     [rax+18h], rbp
0x1800100ba  mov     [rax+20h], rsi
0x1800100be  mov     [rax-10h], rdi
0x1800100c2  mov     [rax-18h], r12
0x1800100c6  mov     r12, rdx
0x1800100c9  mov     [rax-20h], r14
0x1800100cd  mov     [rax-28h], r15
0x1800100d1  call    cs:__imp_malloc
0x1800100d7  mov     r15, rax
0x1800100da  test    rax, rax
0x1800100dd  jz      loc_1800102B5
0x1800100e3  mov     rcx, [r12+10h]; char *
0x1800100e8  xor     eax, eax
0x1800100ea  mov     [r15+10h], rax
0x1800100ee  xorps   xmm0, xmm0
0x1800100f1  movups  xmmword ptr [r15+58h], xmm0
0x1800100f6  mov     [r15+68h], rax
0x1800100fa  xor     esi, esi
0x1800100fc  mov     eax, [r12+2Ch]
0x180010101  mov     [r15+2Ch], eax
0x180010105  mov     eax, [r12+28h]
0x18001010a  mov     [r15+28h], eax
0x18001010e  mov     [r15+70h], rsi
0x180010112  movups  xmm0, xmmword ptr [r12+38h]
0x180010118  movups  xmmword ptr [r15+38h], xmm0
0x18001011d  test    rcx, rcx
0x180010120  jnz     loc_1800103E3
0x180010126  mov     r13d, esi
0x180010129  mov     ecx, esi
0x18001012b  mov     [r15+10h], rcx
0x18001012f  mov     rcx, [r12+48h]; char *
0x180010134  test    rcx, rcx
0x180010137  jnz     loc_18001039A
0x18001013d  mov     [r15+48h], rsi
0x180010141  mov     rcx, [r12+50h]; char *
0x180010146  test    rcx, rcx
0x180010149  jnz     loc_1800103FD
0x18001014f  mov     [r15+50h], rsi
0x180010153  mov     rcx, [r12+30h]; char *
0x180010158  test    rcx, rcx
0x18001015b  jnz     loc_180010423
0x180010161  mov     [r15+30h], rsi
0x180010165  mov     rbx, [r12+8]
0x18001016a  mov     ebp, 7FFFFFFEh
0x18001016f  mov     r14, 0FFFFFFFFFFFFFFFFh
0x180010176  test    rbx, rbx
0x180010179  jz      loc_1800103C0
0x18001017f  test    r13d, r13d
0x180010182  js      loc_1800103C0
0x180010188  mov     r8, rsi
0x18001018b  mov     rax, r14
0x18001018e  xchg    ax, ax
0x180010190  cmp     [rbx+rax+1], sil
0x180010195  lea     rax, [rax+1]
0x180010199  jnz     short loc_180010190
0x18001019b  lea     esi, [rax+1]
0x18001019e  test    esi, esi
0x1800101a0  jz      short loc_1800101F7
0x1800101a2  mov     ecx, esi; Size
0x1800101a4  mov     edi, esi
0x1800101a6  call    cs:__imp_malloc
0x1800101ac  mov     r8, rax
0x1800101af  test    rax, rax
0x1800101b2  jz      short loc_1800101F7
0x1800101b4  cmp     esi, 7FFFFFFFh
0x1800101ba  ja      loc_180010449
0x1800101c0  mov     rcx, rbp
0x1800101c3  mov     rdx, rax
0x1800101c6  test    rcx, rcx
0x1800101c9  jz      short loc_1800101E3
0x1800101cb  movzx   eax, byte ptr [rbx]
0x1800101ce  test    al, al
0x1800101d0  jz      short loc_1800101E3
0x1800101d2  mov     [rdx], al
0x1800101d4  inc     rbx
0x1800101d7  inc     rdx
0x1800101da  dec     rcx
0x1800101dd  sub     rdi, 1
0x1800101e1  jnz     short loc_1800101C6
0x1800101e3  test    rdi, rdi
0x1800101e6  lea     rax, [rdx-1]
0x1800101ea  cmovnz  rax, rdx
0x1800101ee  mov     byte ptr [rax], 0
0x1800101f1  jz      loc_18001044C
0x1800101f7  xor     esi, esi
0x1800101f9  mov     [r15+8], r8
0x1800101fd  test    r8, r8
0x180010200  jz      loc_18001045B
0x180010206  mov     rcx, [r12+20h]; char *
0x18001020b  test    rcx, rcx
0x18001020e  jnz     loc_180010466
0x180010214  mov     [r15+20h], rsi
0x180010218  mov     rbx, [r12]
0x18001021c  test    rbx, rbx
0x18001021f  jnz     loc_180010309
0x180010225  mov     [r15], rsi
0x180010228  mov     rbx, [r12+18h]
0x18001022d  test    rbx, rbx
0x180010230  jz      loc_1800102BD
0x180010236  test    r13d, r13d
0x180010239  js      loc_1800102BD
0x18001023f  mov     rdx, rsi
0x180010242  cmp     byte ptr [rbx+r14+1], 0
0x180010248  lea     r14, [r14+1]
0x18001024c  jnz     short loc_180010242
0x18001024e  lea     esi, [r14+1]
0x180010252  test    esi, esi
0x180010254  jz      short loc_1800102A8
0x180010256  mov     ecx, esi; Size
0x180010258  mov     edi, esi
0x18001025a  call    cs:__imp_malloc
0x180010260  mov     rdx, rax
0x180010263  test    rax, rax
0x180010266  jz      short loc_1800102A8
0x180010268  cmp     esi, 7FFFFFFFh
0x18001026e  ja      loc_1800104A8
0x180010274  mov     rcx, rax
0x180010277  test    rbp, rbp
0x18001027a  jz      short loc_180010294
0x18001027c  movzx   eax, byte ptr [rbx]
0x18001027f  test    al, al
0x180010281  jz      short loc_180010294
0x180010283  mov     [rcx], al
0x180010285  inc     rbx
0x180010288  inc     rcx
0x18001028b  dec     rbp
0x18001028e  sub     rdi, 1
0x180010292  jnz     short loc_180010277
0x180010294  test    rdi, rdi
0x180010297  lea     rax, [rcx-1]
0x18001029b  cmovnz  rax, rcx
0x18001029f  mov     byte ptr [rax], 0
0x1800102a2  jz      loc_1800104AB
0x1800102a8  mov     [r15+18h], rdx
0x1800102ac  test    rdx, rdx
0x1800102af  jnz     loc_1800104C1
0x1800102b5  mov     r13d, 8007000Eh
0x1800102bb  jmp     short loc_1800102CA
0x1800102bd  mov     [r15+18h], rsi
0x1800102c1  test    r13d, r13d
0x1800102c4  jns     loc_1800103C9
0x1800102ca  mov     rcx, r15
0x1800102cd  call    cs:__imp_FreeSsdpMessageEx
0x1800102d3  mov     r15, [rsp+58h+var_28]
0x1800102d8  mov     r14, [rsp+58h+var_20]
0x1800102dd  mov     r12, [rsp+58h+var_18]
0x1800102e2  mov     rdi, [rsp+58h+var_10]
0x1800102e7  mov     rsi, [rsp+58h+arg_18]
0x1800102ec  mov     rbp, [rsp+58h+arg_10]
0x1800102f1  mov     rbx, [rsp+58h+arg_8]
0x1800102f6  test    r13d, r13d
0x1800102f9  jnz     loc_180010536
0x1800102ff  mov     eax, r13d
0x180010302  add     rsp, 50h
0x180010306  pop     r13
0x180010308  retn
0x180010309  test    r13d, r13d
0x18001030c  js      loc_180010225
0x180010312  mov     r8, rsi
0x180010315  mov     rax, r14
0x180010318  nop     dword ptr [rax+rax+00000000h]
0x180010320  cmp     byte ptr [rbx+rax+1], 0
0x180010325  lea     rax, [rax+1]
0x180010329  jnz     short loc_180010320
0x18001032b  lea     esi, [rax+1]
0x18001032e  test    esi, esi
0x180010330  jz      short loc_180010387
0x180010332  mov     ecx, esi; Size
0x180010334  mov     edi, esi
0x180010336  call    cs:__imp_malloc
0x18001033c  mov     r8, rax
0x18001033f  test    rax, rax
0x180010342  jz      short loc_180010387
0x180010344  cmp     esi, 7FFFFFFFh
0x18001034a  ja      loc_18001048C
0x180010350  mov     rcx, rbp
0x180010353  mov     rdx, rax
0x180010356  test    rcx, rcx
0x180010359  jz      short loc_180010373
0x18001035b  movzx   eax, byte ptr [rbx]
0x18001035e  test    al, al
0x180010360  jz      short loc_180010373
0x180010362  mov     [rdx], al
0x180010364  inc     rbx
0x180010367  inc     rdx
0x18001036a  dec     rcx
0x18001036d  sub     rdi, 1
0x180010371  jnz     short loc_180010356
0x180010373  test    rdi, rdi
0x180010376  lea     rax, [rdx-1]
0x18001037a  cmovnz  rax, rdx
0x18001037e  mov     byte ptr [rax], 0
0x180010381  jz      loc_18001048F
0x180010387  xor     esi, esi
0x180010389  mov     [r15], r8
0x18001038c  test    r8, r8
0x18001038f  jnz     loc_180010228
0x180010395  jmp     loc_18001049D
0x18001039a  test    r13d, r13d
0x18001039d  js      loc_18001013D
0x1800103a3  call    ?SzaDupSza@@YAPEADPEBD@Z; SzaDupSza(char const *)
0x1800103a8  mov     [r15+48h], rax
0x1800103ac  test    rax, rax
0x1800103af  jnz     loc_180010141
0x1800103b5  mov     r13d, 8007000Eh
0x1800103bb  jmp     loc_180010141
0x1800103c0  mov     [r15+8], rsi
0x1800103c4  jmp     loc_180010206
0x1800103c9  mov     edi, [r12+68h]
0x1800103ce  test    edi, edi
0x1800103d0  jnz     loc_1800104C8
0x1800103d6  mov     rax, [rsp+58h+arg_0]
0x1800103db  mov     [rax], r15
0x1800103de  jmp     loc_1800102D3
0x1800103e3  call    ?SzaDupSza@@YAPEADPEBD@Z; SzaDupSza(char const *)
0x1800103e8  test    rax, rax
0x1800103eb  mov     r13d, 8007000Eh
0x1800103f1  mov     rcx, rax
0x1800103f4  cmovnz  r13d, esi
0x1800103f8  jmp     loc_18001012B
0x1800103fd  test    r13d, r13d
0x180010400  js      loc_18001014F
0x180010406  call    ?SzaDupSza@@YAPEADPEBD@Z; SzaDupSza(char const *)
0x18001040b  mov     [r15+50h], rax
0x18001040f  test    rax, rax
0x180010412  jnz     loc_180010153
0x180010418  mov     r13d, 8007000Eh
0x18001041e  jmp     loc_180010153
0x180010423  test    r13d, r13d
0x180010426  js      loc_180010161
0x18001042c  call    ?SzaDupSza@@YAPEADPEBD@Z; SzaDupSza(char const *)
0x180010431  mov     [r15+30h], rax
0x180010435  test    rax, rax
0x180010438  jnz     loc_180010165
0x18001043e  mov     r13d, 8007000Eh
0x180010444  jmp     loc_180010165
0x180010449  mov     byte ptr [rax], 0
0x18001044c  mov     rcx, r8; Block
0x18001044f  call    cs:__imp_free
0x180010455  xor     esi, esi
0x180010457  mov     [r15+8], rsi
0x18001045b  mov     r13d, 8007000Eh
0x180010461  jmp     loc_180010206
0x180010466  test    r13d, r13d
0x180010469  js      loc_180010214
0x18001046f  call    ?SzaDupSza@@YAPEADPEBD@Z; SzaDupSza(char const *)
0x180010474  mov     [r15+20h], rax
0x180010478  test    rax, rax
0x18001047b  jnz     loc_180010218
0x180010481  mov     r13d, 8007000Eh
0x180010487  jmp     loc_180010218
0x18001048c  mov     byte ptr [rax], 0
0x18001048f  mov     rcx, r8; Block
0x180010492  call    cs:__imp_free
0x180010498  xor     esi, esi
0x18001049a  mov     [r15], rsi
0x18001049d  mov     r13d, 8007000Eh
0x1800104a3  jmp     loc_180010228
0x1800104a8  mov     byte ptr [rax], 0
0x1800104ab  mov     rcx, rdx; Block
0x1800104ae  call    cs:__imp_free
0x1800104b4  mov     qword ptr [r15+18h], 0
0x1800104bc  jmp     loc_1800102B5
0x1800104c1  xor     esi, esi
0x1800104c3  jmp     loc_1800103C9
0x1800104c8  cmp     qword ptr [r12+70h], 0
0x1800104ce  jz      loc_1800103D6
0x1800104d4  mov     rbx, rdi
0x1800104d7  mov     [r15+68h], edi
0x1800104db  shl     rbx, 3
0x1800104df  mov     rcx, rbx; Size
0x1800104e2  call    cs:__imp_malloc
0x1800104e8  mov     [r15+70h], rax
0x1800104ec  mov     r14, rax
0x1800104ef  test    rax, rax
0x1800104f2  jz      loc_1800102B5
0x1800104f8  mov     r8, rbx; Size
0x1800104fb  xor     edx, edx; Val
0x1800104fd  mov     rcx, rax; void *
0x180010500  call    memset_0
0x180010505  cmp     esi, edi
0x180010507  jnb     loc_1800103D6
0x18001050d  mov     rcx, [r12+70h]
0x180010512  mov     eax, esi
0x180010514  lea     rbx, ds:0[rax*8]
0x18001051c  mov     rcx, [rbx+rcx]; char *
0x180010520  call    ?SzaDupSza@@YAPEADPEBD@Z; SzaDupSza(char const *)
0x180010525  mov     [r14+rbx], rax
0x180010529  test    rax, rax
0x18001052c  jz      loc_1800102B5
0x180010532  inc     esi
0x180010534  jmp     short loc_180010505
0x180010536  mov     rcx, cs:WPP_GLOBAL_Control
0x18001053d  lea     rax, WPP_GLOBAL_Control
  ... truncated ...
```
