# CSqlSortManager::DBCreateTables(ulong,sortkey_s *)

- ea: `0x1004a2940`
- end: `0x1004a2dd6`
- name: `?DBCreateTables@CSqlSortManager@@UEAAPEAULOC_s@@KPEAUsortkey_s@@@Z`
- size: `1174`
- prototype: `struct LOC_s *__fastcall(CSqlSortManager *__hidden this, unsigned int, struct sortkey_s *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1004011fc`
- `0x100401cc0`
- `0x1004a25f0`
- `0x1004a2940`

## import_xrefs

- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004a2988`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004a29dd`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004a2988`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004a29dd`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004a296e`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004a29c3`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004a296e`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004a29c3`

## string_xrefs

- `0x1004a2981`: `sql\ntdbms\msql\sqlsort\common\sortutil.cpp`
- `0x1004a29d6`: `sql\ntdbms\msql\sqlsort\common\sortutil.cpp`

## pseudocode

```c
struct LOC_s *__fastcall CSqlSortManager::DBCreateTables(const void **this, int a2, struct sortkey_s *a3)
{
  char *v6; // rax
  char *v7; // rbx
  struct sortkey_s *v8; // rax
  __int64 v9; // rbp
  _DWORD *v10; // r9
  __int64 v11; // rax
  __int64 v12; // rcx
  char *v13; // rdx
  char *v14; // r8
  unsigned __int64 i; // r9
  __int64 v16; // rcx
  char v17; // al
  __int64 v18; // rcx
  _QWORD *v19; // rax
  unsigned int *v20; // rax
  unsigned __int16 *v21; // rdx
  __int64 v22; // rcx
  unsigned __int16 *j; // r8
  __int64 v24; // rcx
  unsigned __int16 v25; // ax
  unsigned __int16 *k; // r8
  __int64 v27; // rcx
  char v28; // al
  __int64 *v29; // rax
  _BYTE *v30; // rax
  char v31; // cl
  __int64 v32; // rdx
  char *v33; // rdi
  __int64 v34; // r8
  unsigned int v35; // ecx
  _DWORD *v36; // rax

  if ( CSqlSortUtil::m_pmoSqlSort )
    v6 = (char *)operator new[](
                   0x148u,
                   CSqlSortUtil::m_pmoSqlSort,
                   "sql\\ntdbms\\msql\\sqlsort\\common\\sortutil.cpp",
                   139,
                   6u);
  else
    v6 = (char *)malloc(0x148u);
  v7 = v6;
  if ( !v6 )
    return 0;
  memset_0(v6 + 4, 0, 0x144u);
  *(_DWORD *)v7 = a2;
  if ( !a3 )
  {
    if ( CSqlSortUtil::m_pmoSqlSort )
      v8 = (struct sortkey_s *)operator new[](
                                 0x40000u,
                                 CSqlSortUtil::m_pmoSqlSort,
                                 "sql\\ntdbms\\msql\\sqlsort\\common\\sortutil.cpp",
                                 139,
                                 6u);
    else
      v8 = (struct sortkey_s *)malloc(0x40000u);
    a3 = v8;
    if ( !v8 )
    {
LABEL_49:
      CSqlSortManager::ReleaseLocale((CSqlSortManager *)this, (struct LOC_s *)v7);
      return 0;
    }
    memmove(v8, this[8], 0x40000u);
  }
  *((_WORD *)v7 + 32) = 34;
  v9 = 0;
  *((_QWORD *)v7 + 1) = a3;
  if ( *((int *)this + 18) > 0 )
  {
    v10 = this[10];
    v11 = 0;
    while ( *v10 != a2 )
    {
      ++v11;
      v10 += 3;
      if ( v11 >= *((int *)this + 18) )
        goto LABEL_18;
    }
    v12 = (unsigned int)v10[1];
    v13 = (char *)this[11];
    v14 = &v13[6 * v12];
    for ( i = (unsigned __int64)&v13[6 * v12 + 6 * (unsigned int)v10[2]];
          (unsigned __int64)v14 < i;
          *((_BYTE *)a3 + 4 * v16 + 3) = v17 )
    {
      *((_WORD *)a3 + 2 * *(unsigned __int16 *)v14) = *((_WORD *)v14 + 1);
      *((_BYTE *)a3 + 4 * *(unsigned __int16 *)v14 + 2) = v14[4];
      v16 = *(unsigned __int16 *)v14;
      v17 = v14[5];
      v14 += 6;
    }
  }
LABEL_18:
  if ( *((int *)this + 24) > 0 )
  {
    v18 = 0;
    v19 = this[13];
    while ( *(_DWORD *)v19 != a2 )
    {
      ++v18;
      v19 += 2;
      if ( v18 >= *((int *)this + 24) )
        goto LABEL_29;
    }
    v20 = (unsigned int *)v19[1];
    v21 = (unsigned __int16 *)*((_QWORD *)v20 + 1);
    v22 = *v20;
    if ( v20[1] == 2 )
    {
      for ( j = &v21[2 * v22]; v21 < j; *((_WORD *)a3 + 2 * v24) = v25 )
      {
        v24 = *v21;
        v25 = v21[1];
        v21 += 2;
      }
    }
    else
    {
      for ( k = &v21[3 * v22]; v21 < k; *((_BYTE *)a3 + 4 * v27 + 3) = v28 )
      {
        *((_WORD *)a3 + 2 * *v21) = v21[1];
        *((_BYTE *)a3 + 4 * *v21 + 2) = *((_BYTE *)v21 + 4);
        v27 = *v21;
        v28 = *((_BYTE *)v21 + 5);
        v21 += 3;
      }
    }
  }
LABEL_29:
  *((_DWORD *)v7 + 17) = 0;
  if ( *((_BYTE *)this + 8) < 2u )
  {
    v29 = qword_100CB59D0;
    while ( *(_DWORD *)v29 != a2 )
    {
      v29 = (__int64 *)((char *)v29 + 12);
      if ( (__int64)v29 >= (__int64)qword_100CB59E8 )
        goto LABEL_42;
    }
    *((_DWORD *)v7 + 17) = 1;
    memset_0(v7 + 86, 0, 0xF2u);
    *((_DWORD *)v7 + 18) = 50462976;
    v30 = v7 + 87;
    *((_DWORD *)v7 + 19) = 117835012;
    v31 = 0x80;
    *((_DWORD *)v7 + 20) = 185207048;
    v32 = 121;
    *((_WORD *)v7 + 42) = 3340;
    *((_DWORD *)v7 + 50) = 286265102;
    *((_DWORD *)v7 + 51) = 353637138;
    *((_DWORD *)v7 + 52) = 421009174;
    *((_DWORD *)v7 + 53) = 488381210;
    *((_DWORD *)v7 + 54) = 555753246;
    qmemcpy(
      v7 + 220,
      "\"#$%&'()*+,-./0123456789:;<=>?@ABCDEFGHIJKLMNOPQRSTUVWXYZ[\\]^_`abcdefghijklmnopqrstuvwxyz{|}",
      92);
    *((_WORD *)v7 + 156) = 32638;
    do
    {
      if ( !*(v30 - 1) )
        *(v30 - 1) = v31++;
      if ( !*v30 )
        *v30 = v31++;
      v30 += 2;
      --v32;
    }
    while ( v32 );
    v33 = (char *)a3 + 8;
    *((_WORD *)v7 + 32) = (unsigned __int8)v7[106];
    v34 = 0x4000;
    do
    {
      v35 = *((unsigned __int16 *)v33 - 4);
      v33 += 16;
      *((_WORD *)v33 - 12) = (unsigned __int8)v35 | ((unsigned __int8)v7[((unsigned __int64)v35 >> 8) + 72] << 8);
      *((_WORD *)v33 - 10) = (unsigned __int8)*((_WORD *)v33 - 10)
                           | ((unsigned __int8)v7[((unsigned __int64)*((unsigned __int16 *)v33 - 10) >> 8) + 72] << 8);
      *((_WORD *)v33 - 8) = (unsigned __int8)*((_WORD *)v33 - 8)
                          | ((unsigned __int8)v7[((unsigned __int64)*((unsigned __int16 *)v33 - 8) >> 8) + 72] << 8);
      *((_WORD *)v33 - 6) = (unsigned __int8)*((_WORD *)v33 - 6)
                          | ((unsigned __int8)v7[((unsigned __int64)*((unsigned __int16 *)v33 - 6) >> 8) + 72] << 8);
      --v34;
    }
    while ( v34 );
  }
LABEL_42:
  if ( *((int *)this + 28) > 0 )
  {
    v36 = this[15];
    while ( *v36 != a2 )
    {
      ++v9;
      ++v36;
      if ( v9 >= *((int *)this + 28) )
        goto LABEL_48;
    }
    *((_DWORD *)v7 + 4) = 1;
  }
LABEL_48:
  if ( !(*((unsigned int (__fastcall **)(const void **, char *))*this + 13))(this, v7) )
    goto LABEL_49;
  return (struct LOC_s *)v7;
}

```

## disassembly

```asm
0x1004a2940  mov     [rsp+arg_8], rbx
0x1004a2945  mov     [rsp+arg_10], rsi
0x1004a294a  mov     [rsp+arg_18], rdi
0x1004a294f  push    r14
0x1004a2951  sub     rsp, 30h
0x1004a2955  mov     esi, edx
0x1004a2957  mov     r14, rcx
0x1004a295a  mov     rdx, cs:?m_pmoSqlSort@CSqlSortUtil@@0PEAVIMemObj@@EA; IMemObj * CSqlSortUtil::m_pmoSqlSort
0x1004a2961  mov     rdi, r8
0x1004a2964  mov     ecx, 148h; Size
0x1004a2969  test    rdx, rdx
0x1004a296c  jnz     short loc_1004A2976
0x1004a296e  call    cs:__imp_malloc
0x1004a2974  jmp     short loc_1004A298E
0x1004a2976  mov     r9d, 8Bh
0x1004a297c  mov     [rsp+38h+var_18], 6
0x1004a2981  lea     r8, aSqlNtdbmsMsqlS; "sql\\ntdbms\\msql\\sqlsort\\common\\sor"...
0x1004a2988  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x1004a298e  mov     rbx, rax
0x1004a2991  test    rax, rax
0x1004a2994  jz      loc_1004A2DB9
0x1004a299a  lea     rcx, [rax+4]; void *
0x1004a299e  xor     edx, edx; Val
0x1004a29a0  mov     r8d, 144h; Size
0x1004a29a6  call    memset_0
0x1004a29ab  mov     [rbx], esi
0x1004a29ad  test    rdi, rdi
0x1004a29b0  jnz     short loc_1004A2A01
0x1004a29b2  mov     rdx, cs:?m_pmoSqlSort@CSqlSortUtil@@0PEAVIMemObj@@EA; IMemObj * CSqlSortUtil::m_pmoSqlSort
0x1004a29b9  mov     ecx, 40000h; Size
0x1004a29be  test    rdx, rdx
0x1004a29c1  jnz     short loc_1004A29CB
0x1004a29c3  call    cs:__imp_malloc
0x1004a29c9  jmp     short loc_1004A29E3
0x1004a29cb  mov     r9d, 8Bh
0x1004a29d1  mov     [rsp+38h+var_18], 6
0x1004a29d6  lea     r8, aSqlNtdbmsMsqlS; "sql\\ntdbms\\msql\\sqlsort\\common\\sor"...
0x1004a29dd  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x1004a29e3  mov     rdi, rax
0x1004a29e6  test    rax, rax
0x1004a29e9  jz      loc_1004A2DAE
0x1004a29ef  mov     rdx, [r14+40h]; Src
0x1004a29f3  mov     r8d, 40000h; Size
0x1004a29f9  mov     rcx, rax; void *
0x1004a29fc  call    memmove
0x1004a2a01  mov     eax, 22h ; '"'
0x1004a2a06  mov     [rsp+38h+arg_0], rbp
0x1004a2a0b  mov     [rbx+40h], ax
0x1004a2a0f  xor     ebp, ebp
0x1004a2a11  mov     [rbx+8], rdi
0x1004a2a15  movsxd  rax, dword ptr [r14+48h]
0x1004a2a19  test    eax, eax
0x1004a2a1b  jle     short loc_1004A2A90
0x1004a2a1d  mov     r9, [r14+50h]
0x1004a2a21  mov     rcx, rax
0x1004a2a24  mov     eax, ebp
0x1004a2a26  cmp     [r9], esi
0x1004a2a29  jz      short loc_1004A2A39
0x1004a2a2b  inc     rax
0x1004a2a2e  add     r9, 0Ch
0x1004a2a32  cmp     rax, rcx
0x1004a2a35  jl      short loc_1004A2A26
0x1004a2a37  jmp     short loc_1004A2A90
0x1004a2a39  mov     ecx, [r9+4]
0x1004a2a3d  mov     rdx, [r14+58h]
0x1004a2a41  lea     rax, [rcx+rcx*2]
0x1004a2a45  lea     r8, [rdx+rax*2]
0x1004a2a49  mov     eax, [r9+8]
0x1004a2a4d  add     rax, rcx
0x1004a2a50  lea     rax, [rax+rax*2]
0x1004a2a54  lea     r9, [rdx+rax*2]
0x1004a2a58  cmp     r8, r9
0x1004a2a5b  jnb     short loc_1004A2A90
0x1004a2a5d  nop     dword ptr [rax]
0x1004a2a60  movzx   ecx, word ptr [r8]
0x1004a2a64  movzx   eax, word ptr [r8+2]
0x1004a2a69  mov     [rdi+rcx*4], ax
0x1004a2a6d  movzx   ecx, word ptr [r8]
0x1004a2a71  movzx   eax, byte ptr [r8+4]
0x1004a2a76  mov     [rdi+rcx*4+2], al
0x1004a2a7a  movzx   ecx, word ptr [r8]
0x1004a2a7e  movzx   eax, byte ptr [r8+5]
0x1004a2a83  add     r8, 6
0x1004a2a87  mov     [rdi+rcx*4+3], al
0x1004a2a8b  cmp     r8, r9
0x1004a2a8e  jb      short loc_1004A2A60
0x1004a2a90  movsxd  rax, dword ptr [r14+60h]
0x1004a2a94  test    eax, eax
0x1004a2a96  jle     loc_1004A2B2A
0x1004a2a9c  mov     rdx, rax
0x1004a2a9f  mov     rcx, rbp
0x1004a2aa2  mov     rax, [r14+68h]
0x1004a2aa6  cmp     [rax], esi
0x1004a2aa8  jz      short loc_1004A2AB8
0x1004a2aaa  inc     rcx
0x1004a2aad  add     rax, 10h
0x1004a2ab1  cmp     rcx, rdx
0x1004a2ab4  jl      short loc_1004A2AA6
0x1004a2ab6  jmp     short loc_1004A2B2A
0x1004a2ab8  mov     rax, [rax+8]
0x1004a2abc  cmp     dword ptr [rax+4], 2
0x1004a2ac0  mov     rdx, [rax+8]
0x1004a2ac4  mov     ecx, [rax]
0x1004a2ac6  jnz     short loc_1004A2AE7
0x1004a2ac8  lea     r8, [rdx+rcx*4]
0x1004a2acc  cmp     rdx, r8
0x1004a2acf  jnb     short loc_1004A2B2A
0x1004a2ad1  movzx   ecx, word ptr [rdx]
0x1004a2ad4  movzx   eax, word ptr [rdx+2]
0x1004a2ad8  add     rdx, 4
0x1004a2adc  mov     [rdi+rcx*4], ax
0x1004a2ae0  cmp     rdx, r8
0x1004a2ae3  jb      short loc_1004A2AD1
0x1004a2ae5  jmp     short loc_1004A2B2A
0x1004a2ae7  lea     rcx, [rcx+rcx*2]
0x1004a2aeb  lea     r8, [rdx+rcx*2]
0x1004a2aef  cmp     rdx, r8
0x1004a2af2  jnb     short loc_1004A2B2A
0x1004a2af4  nop     dword ptr [rax+00h]
0x1004a2af8  nop     dword ptr [rax+rax+00000000h]
0x1004a2b00  movzx   ecx, word ptr [rdx]
0x1004a2b03  movzx   eax, word ptr [rdx+2]
0x1004a2b07  mov     [rdi+rcx*4], ax
0x1004a2b0b  movzx   ecx, word ptr [rdx]
0x1004a2b0e  movzx   eax, byte ptr [rdx+4]
0x1004a2b12  mov     [rdi+rcx*4+2], al
0x1004a2b16  movzx   ecx, word ptr [rdx]
0x1004a2b19  movzx   eax, byte ptr [rdx+5]
0x1004a2b1d  add     rdx, 6
0x1004a2b21  mov     [rdi+rcx*4+3], al
0x1004a2b25  cmp     rdx, r8
0x1004a2b28  jb      short loc_1004A2B00
0x1004a2b2a  mov     [rbx+44h], ebp
0x1004a2b2d  cmp     byte ptr [r14+8], 2
0x1004a2b32  jnb     loc_1004A2D6E
0x1004a2b38  lea     rax, qword_100CB59D0
0x1004a2b3f  lea     rcx, qword_100CB59E8
0x1004a2b46  cmp     [rax], esi
0x1004a2b48  jz      short loc_1004A2B58
0x1004a2b4a  add     rax, 0Ch
0x1004a2b4e  cmp     rax, rcx
0x1004a2b51  jl      short loc_1004A2B46
0x1004a2b53  jmp     loc_1004A2D6E
0x1004a2b58  lea     rcx, [rbx+56h]; void *
0x1004a2b5c  mov     dword ptr [rbx+44h], 1
0x1004a2b63  xor     edx, edx; Val
0x1004a2b65  mov     r8d, 0F2h; Size
0x1004a2b6b  call    memset_0
0x1004a2b70  mov     dword ptr [rbx+48h], 3020100h
0x1004a2b77  lea     rax, [rbx+57h]
0x1004a2b7b  mov     dword ptr [rbx+4Ch], 7060504h
0x1004a2b82  mov     cl, 80h
0x1004a2b84  mov     dword ptr [rbx+50h], 0B0A0908h
0x1004a2b8b  mov     edx, 79h ; 'y'
0x1004a2b90  mov     word ptr [rbx+54h], 0D0Ch
0x1004a2b96  mov     dword ptr [rbx+0C8h], 11100F0Eh
0x1004a2ba0  mov     dword ptr [rbx+0CCh], 15141312h
0x1004a2baa  mov     dword ptr [rbx+0D0h], 19181716h
0x1004a2bb4  mov     dword ptr [rbx+0D4h], 1D1C1B1Ah
0x1004a2bbe  mov     dword ptr [rbx+0D8h], 21201F1Eh
0x1004a2bc8  mov     dword ptr [rbx+0DCh], 25242322h
0x1004a2bd2  mov     dword ptr [rbx+0E0h], 29282726h
0x1004a2bdc  mov     dword ptr [rbx+0E4h], 2D2C2B2Ah
0x1004a2be6  mov     dword ptr [rbx+0E8h], 31302F2Eh
0x1004a2bf0  mov     dword ptr [rbx+0ECh], 35343332h
0x1004a2bfa  mov     dword ptr [rbx+0F0h], 39383736h
0x1004a2c04  mov     dword ptr [rbx+0F4h], 3D3C3B3Ah
0x1004a2c0e  mov     dword ptr [rbx+0F8h], 41403F3Eh
0x1004a2c18  mov     dword ptr [rbx+0FCh], 45444342h
0x1004a2c22  mov     dword ptr [rbx+100h], 49484746h
0x1004a2c2c  mov     dword ptr [rbx+104h], 4D4C4B4Ah
0x1004a2c36  mov     dword ptr [rbx+108h], 51504F4Eh
0x1004a2c40  mov     dword ptr [rbx+10Ch], 55545352h
0x1004a2c4a  mov     dword ptr [rbx+110h], 59585756h
0x1004a2c54  mov     dword ptr [rbx+114h], 5D5C5B5Ah
0x1004a2c5e  mov     dword ptr [rbx+118h], 61605F5Eh
0x1004a2c68  mov     dword ptr [rbx+11Ch], 65646362h
0x1004a2c72  mov     dword ptr [rbx+120h], 69686766h
0x1004a2c7c  mov     dword ptr [rbx+124h], 6D6C6B6Ah
0x1004a2c86  mov     dword ptr [rbx+128h], 71706F6Eh
0x1004a2c90  mov     dword ptr [rbx+12Ch], 75747372h
0x1004a2c9a  mov     dword ptr [rbx+130h], 79787776h
0x1004a2ca4  mov     dword ptr [rbx+134h], 7D7C7B7Ah
0x1004a2cae  mov     word ptr [rbx+138h], 7F7Eh
0x1004a2cb7  cmp     [rax-1], bpl
0x1004a2cbb  jnz     short loc_1004A2CC2
0x1004a2cbd  mov     [rax-1], cl
0x1004a2cc0  inc     cl
0x1004a2cc2  cmp     [rax], bpl
0x1004a2cc5  jnz     short loc_1004A2CCB
0x1004a2cc7  mov     [rax], cl
0x1004a2cc9  inc     cl
0x1004a2ccb  add     rax, 2
0x1004a2ccf  sub     rdx, 1
0x1004a2cd3  jnz     short loc_1004A2CB7
0x1004a2cd5  movzx   eax, byte ptr [rbx+6Ah]
0x1004a2cd9  add     rdi, 8
0x1004a2cdd  mov     [rbx+40h], ax
0x1004a2ce1  mov     r8d, 4000h
0x1004a2ce7  nop     word ptr [rax+rax+00000000h]
0x1004a2cf0  movzx   ecx, word ptr [rdi-8]
0x1004a2cf4  lea     rdi, [rdi+10h]
0x1004a2cf8  mov     eax, ecx
0x1004a2cfa  shr     rax, 8
0x1004a2cfe  movzx   edx, byte ptr [rax+rbx+48h]
0x1004a2d03  shl     dx, 8
0x1004a2d07  movzx   eax, cl
0x1004a2d0a  or      dx, ax
0x1004a2d0d  mov     [rdi-18h], dx
0x1004a2d11  movzx   ecx, word ptr [rdi-14h]
0x1004a2d15  mov     eax, ecx
0x1004a2d17  shr     rax, 8
0x1004a2d1b  movzx   edx, byte ptr [rax+rbx+48h]
0x1004a2d20  shl     dx, 8
0x1004a2d24  movzx   eax, cl
0x1004a2d27  or      dx, ax
0x1004a2d2a  mov     [rdi-14h], dx
0x1004a2d2e  movzx   ecx, word ptr [rdi-10h]
0x1004a2d32  mov     eax, ecx
0x1004a2d34  shr     rax, 8
0x1004a2d38  movzx   edx, byte ptr [rax+rbx+48h]
0x1004a2d3d  shl     dx, 8
0x1004a2d41  movzx   eax, cl
0x1004a2d44  or      dx, ax
0x1004a2d47  mov     [rdi-10h], dx
0x1004a2d4b  movzx   ecx, word ptr [rdi-0Ch]
0x1004a2d4f  mov     eax, ecx
0x1004a2d51  shr     rax, 8
0x1004a2d55  movzx   edx, byte ptr [rax+rbx+48h]
0x1004a2d5a  shl     dx, 8
0x1004a2d5e  movzx   eax, cl
0x1004a2d61  or      dx, ax
0x1004a2d64  mov     [rdi-0Ch], dx
0x1004a2d68  sub     r8, 1
0x1004a2d6c  jnz     short loc_1004A2CF0
0x1004a2d6e  movsxd  rax, dword ptr [r14+70h]
0x1004a2d72  test    eax, eax
0x1004a2d74  jle     short loc_1004A2D99
0x1004a2d76  mov     rcx, rax
0x1004a2d79  mov     rax, [r14+78h]
0x1004a2d7d  nop     dword ptr [rax]
0x1004a2d80  cmp     [rax], esi
0x1004a2d82  jz      short loc_1004A2D92
0x1004a2d84  inc     rbp
0x1004a2d87  add     rax, 4
0x1004a2d8b  cmp     rbp, rcx
0x1004a2d8e  jl      short loc_1004A2D80
0x1004a2d90  jmp     short loc_1004A2D99
0x1004a2d92  mov     dword ptr [rbx+10h], 1
0x1004a2d99  mov     rax, [r14]
0x1004a2d9c  mov     rdx, rbx
0x1004a2d9f  mov     rcx, r14
0x1004a2da2  call    qword ptr [rax+68h]
0x1004a2da5  mov     rbp, [rsp+38h+arg_0]
0x1004a2daa  test    eax, eax
0x1004a2dac  jnz     short loc_1004A2DBD
0x1004a2dae  mov     rdx, rbx; struct LOC_s *
0x1004a2db1  mov     rcx, r14; this
0x1004a2db4  call    ?ReleaseLocale@CSqlSortManager@@IEAAXPEAULOC_s@@@Z; CSqlSortManager::ReleaseLocale(LOC_s *)
0x1004a2db9  xor     eax, eax
0x1004a2dbb  jmp     short loc_1004A2DC0
0x1004a2dbd  mov     rax, rbx
0x1004a2dc0  mov     rbx, [rsp+38h+arg_8]
0x1004a2dc5  mov     rsi, [rsp+38h+arg_10]
0x1004a2dca  mov     rdi, [rsp+38h+arg_18]
0x1004a2dcf  add     rsp, 30h
0x1004a2dd3  pop     r14
0x1004a2dd5  retn
```
