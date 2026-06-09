# CSqlSortManager_100::LoadCompressionTables(LOC_s *)

- ea: `0x1004a2fe0`
- end: `0x1004a35a3`
- name: `?LoadCompressionTables@CSqlSortManager_100@@MEAAHPEAULOC_s@@@Z`
- size: `1475`
- prototype: `__int64 __fastcall(CSqlSortManager_100 *__hidden this, struct LOC_s *)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1004a2fe0`
- `0x1004a3710`
- `0x1004a37e0`
- `0x1004a38a0`
- `0x1004a3970`
- `0x1004a3ba0`
- `0x1004a3df0`
- `0x1004a4050`
- `0x1004a42d0`
- `0x1004a4560`
- `0x1004a4820`

## import_xrefs

- `sqldk!??_V@YAXPEAX@Z` at `0x1004a343f`
- `sqldk!??_V@YAXPEAX@Z` at `0x1004a346a`
- `sqldk!??_V@YAXPEAX@Z` at `0x1004a349d`
- `sqldk!??_V@YAXPEAX@Z` at `0x1004a34d0`
- `sqldk!??_V@YAXPEAX@Z` at `0x1004a3503`
- `sqldk!??_V@YAXPEAX@Z` at `0x1004a3536`
- `sqldk!??_V@YAXPEAX@Z` at `0x1004a3561`
- `sqldk!??_V@YAXPEAX@Z` at `0x1004a3582`
- `sqldk!??_V@YAXPEAX@Z` at `0x1004a343f`
- `sqldk!??_V@YAXPEAX@Z` at `0x1004a346a`
- `sqldk!??_V@YAXPEAX@Z` at `0x1004a349d`
- `sqldk!??_V@YAXPEAX@Z` at `0x1004a34d0`
- `sqldk!??_V@YAXPEAX@Z` at `0x1004a3503`
- `sqldk!??_V@YAXPEAX@Z` at `0x1004a3536`
- `sqldk!??_V@YAXPEAX@Z` at `0x1004a3561`
- `sqldk!??_V@YAXPEAX@Z` at `0x1004a3582`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004a30b1`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004a30b1`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004a3097`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004a3097`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1004a341c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1004a3462`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1004a3491`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1004a34c4`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1004a34f7`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1004a352a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1004a3559`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1004a357a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1004a341c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1004a3462`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1004a3491`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1004a34c4`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1004a34f7`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1004a352a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1004a3559`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1004a357a`

## string_xrefs

- `0x1004a30aa`: `sql\ntdbms\msql\sqlsort\common\sortutil.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CSqlSortManager_100::LoadCompressionTables(CSqlSortManager_100 *this, struct LOC_s *a2)
{
  CSqlSortManager_100 *v3; // r11
  unsigned int v4; // r12d
  _QWORD *v5; // r14
  void *v6; // rdi
  void *v7; // rbx
  void *v8; // rsi
  unsigned int v9; // edx
  unsigned int v10; // r8d
  __int64 v11; // r15
  _QWORD *v12; // rax
  unsigned __int16 *v13; // rcx
  __int64 v14; // r8
  __int64 v15; // rdx
  __int64 v16; // rax
  unsigned __int16 *v17; // rcx
  __int64 v18; // r8
  __int64 v19; // rdx
  unsigned __int16 *v20; // rcx
  __int64 v21; // r8
  __int64 v22; // rdx
  __int64 v23; // rax
  unsigned __int16 *v24; // rcx
  __int64 v25; // r8
  __int64 v26; // rdx
  __int64 v27; // rax
  unsigned __int16 *v28; // rcx
  __int64 v29; // r8
  __int64 v30; // rdx
  __int64 v31; // rax
  unsigned __int16 *v32; // rcx
  __int64 v33; // r8
  __int64 v34; // rdx
  __int64 v35; // rax
  unsigned __int16 *v36; // rcx
  __int64 v37; // r8
  __int64 v38; // rdx
  __int64 v39; // rax
  __int64 v40; // rcx
  _DWORD *v41; // rax
  unsigned int v42; // edx
  int v43; // r8d
  __int64 v44; // rax
  void *v45; // rax
  void *v46; // rax
  void *v47; // rax
  void *v48; // rax
  void *v49; // rax
  void *v50; // rax
  void *v51; // rax
  _QWORD *v52; // rax
  void *v53; // rbx
  void *v54; // rbx
  void *v55; // rbx
  void *v56; // rbx
  void *v58; // [rsp+30h] [rbp-40h] BYREF
  void *Block; // [rsp+38h] [rbp-38h] BYREF
  void *v60; // [rsp+40h] [rbp-30h] BYREF
  void *v61; // [rsp+48h] [rbp-28h] BYREF
  void *v62; // [rsp+50h] [rbp-20h] BYREF
  _QWORD *v63; // [rsp+58h] [rbp-18h]
  __int64 v64; // [rsp+60h] [rbp-10h]
  void *v66; // [rsp+C0h] [rbp+50h] BYREF
  void *v67; // [rsp+C8h] [rbp+58h] BYREF

  v64 = -2;
  v3 = this;
  v4 = 0;
  v5 = 0;
  v63 = 0;
  v6 = 0;
  v67 = 0;
  v62 = 0;
  v61 = 0;
  v60 = 0;
  Block = 0;
  v7 = 0;
  v66 = 0;
  v8 = 0;
  v58 = 0;
  v9 = 0;
  v10 = *((_DWORD *)this + 60);
  if ( v10 )
  {
    while ( 1 )
    {
      v11 = *((_QWORD *)this + 31) + 80LL * v9;
      if ( *(_DWORD *)v11 == *(_DWORD *)a2 )
        break;
      if ( ++v9 >= v10 )
        goto LABEL_41;
    }
    *((_DWORD *)a2 + 5) = 1;
    if ( CSqlSortUtil::m_pmoSqlSort )
      v12 = operator new[](
              0x38u,
              CSqlSortUtil::m_pmoSqlSort,
              "sql\\ntdbms\\msql\\sqlsort\\common\\sortutil.cpp",
              139,
              6u);
    else
      v12 = malloc(0x38u);
    v5 = v12;
    v63 = v12;
    if ( (unsigned int)CSqlSortManager_100::CreateCompressionMap<2>(
                         *(_QWORD *)(v11 + 24),
                         *(_WORD *)(v11 + 8),
                         (__int64 *)&v67)
      && (unsigned int)CSqlSortManager_100::CreateCompressionMap<3>(
                         *(_QWORD *)(v11 + 32),
                         *(_WORD *)(v11 + 10),
                         (__int64 *)&v62)
      && (unsigned int)CSqlSortManager_100::CreateCompressionMap<4>(
                         *(_QWORD *)(v11 + 40),
                         *(_WORD *)(v11 + 12),
                         (__int64 *)&v61)
      && (unsigned int)CSqlSortManager_100::CreateCompressionMap<5>(
                         *(_QWORD *)(v11 + 48),
                         *(_WORD *)(v11 + 14),
                         (__int64 *)&v60)
      && (unsigned int)CSqlSortManager_100::CreateCompressionMap<6>(
                         *(_QWORD *)(v11 + 56),
                         *(_WORD *)(v11 + 16),
                         (__int64 *)&Block) )
    {
      if ( (unsigned int)CSqlSortManager_100::CreateCompressionMap<7>(
                           *(_QWORD *)(v11 + 64),
                           *(_WORD *)(v11 + 18),
                           (__int64 *)&v66) )
      {
        if ( (unsigned int)CSqlSortManager_100::CreateCompressionMap<8>(
                             *(_QWORD *)(v11 + 72),
                             *(_WORD *)(v11 + 20),
                             (__int64 *)&v58) )
        {
          v13 = *(unsigned __int16 **)(v11 + 24);
          if ( *(_WORD *)(v11 + 8) )
          {
            v14 = *((_QWORD *)a2 + 1);
            v15 = *(unsigned __int16 *)(v11 + 8);
            do
            {
              v16 = *v13;
              *(_BYTE *)(v14 + 4 * v16 + 3) &= 0x3Fu;
              *(_BYTE *)(v14 + 4 * v16 + 3) |= 0x80u;
              v13 += 4;
              --v15;
            }
            while ( v15 );
          }
          v17 = *(unsigned __int16 **)(v11 + 32);
          if ( *(_WORD *)(v11 + 10) )
          {
            v18 = *((_QWORD *)a2 + 1);
            v19 = *(unsigned __int16 *)(v11 + 10);
            do
            {
              *(_BYTE *)(v18 + 4LL * *v17 + 3) |= 0xC0u;
              v17 += 5;
              --v19;
            }
            while ( v19 );
          }
          v20 = *(unsigned __int16 **)(v11 + 40);
          if ( *(_WORD *)(v11 + 12) )
          {
            v21 = *((_QWORD *)a2 + 1);
            v22 = *(unsigned __int16 *)(v11 + 12);
            do
            {
              v23 = *v20;
              *(_BYTE *)(v21 + 4 * v23 + 3) &= 0x3Fu;
              *(_BYTE *)(v21 + 4 * v23 + 3) |= 0x40u;
              v20 += 6;
              --v22;
            }
            while ( v22 );
          }
          v24 = *(unsigned __int16 **)(v11 + 48);
          if ( *(_WORD *)(v11 + 14) )
          {
            v25 = *((_QWORD *)a2 + 1);
            v26 = *(unsigned __int16 *)(v11 + 14);
            do
            {
              v27 = *v24;
              *(_BYTE *)(v25 + 4 * v27 + 3) &= 0x3Fu;
              *(_BYTE *)(v25 + 4 * v27 + 3) |= 0x40u;
              v24 += 7;
              --v26;
            }
            while ( v26 );
          }
          v28 = *(unsigned __int16 **)(v11 + 56);
          if ( *(_WORD *)(v11 + 16) )
          {
            v29 = *((_QWORD *)a2 + 1);
            v30 = *(unsigned __int16 *)(v11 + 16);
            do
            {
              v31 = *v28;
              *(_BYTE *)(v29 + 4 * v31 + 3) &= 0x3Fu;
              *(_BYTE *)(v29 + 4 * v31 + 3) |= 0x40u;
              v28 += 8;
              --v30;
            }
            while ( v30 );
          }
          v32 = *(unsigned __int16 **)(v11 + 64);
          if ( *(_WORD *)(v11 + 18) )
          {
            v33 = *((_QWORD *)a2 + 1);
            v34 = *(unsigned __int16 *)(v11 + 18);
            do
            {
              v35 = *v32;
              *(_BYTE *)(v33 + 4 * v35 + 3) &= 0x3Fu;
              *(_BYTE *)(v33 + 4 * v35 + 3) |= 0x40u;
              v32 += 9;
              --v34;
            }
            while ( v34 );
          }
          v36 = *(unsigned __int16 **)(v11 + 72);
          if ( *(_WORD *)(v11 + 20) )
          {
            v37 = *((_QWORD *)a2 + 1);
            v38 = *(unsigned __int16 *)(v11 + 20);
            do
            {
              v39 = *v36;
              *(_BYTE *)(v37 + 4 * v39 + 3) &= 0x3Fu;
              *(_BYTE *)(v37 + 4 * v39 + 3) |= 0x40u;
              v36 += 10;
              --v38;
            }
            while ( v38 );
          }
          v3 = this;
          if ( *((int *)this + 38) > 0 )
          {
            v40 = 0;
            v41 = (_DWORD *)*((_QWORD *)this + 20);
            while ( *v41 != *(_DWORD *)a2 )
            {
              ++v40;
              ++v41;
              if ( v40 >= *((int *)this + 38) )
                goto LABEL_40;
            }
            *((_DWORD *)a2 + 6) = 1;
          }
LABEL_40:
          v6 = v67;
          v7 = v66;
          v8 = v58;
          goto LABEL_41;
        }
        v8 = v58;
      }
      v7 = v66;
    }
    v6 = v67;
    goto LABEL_49;
  }
LABEL_41:
  v42 = 0;
  if ( *((_DWORD *)v3 + 64) )
  {
    v43 = *(_DWORD *)a2;
    do
    {
      v44 = *((_QWORD *)v3 + 33);
      if ( *(_DWORD *)(v44 + 16LL * v42) == v43 )
      {
        *((_QWORD *)a2 + 7) = *(_QWORD *)(v44 + 16LL * v42 + 8);
        *((_DWORD *)a2 + 5) = 1;
      }
      ++v42;
    }
    while ( v42 < *((_DWORD *)v3 + 64) );
  }
  if ( v5 )
  {
    v45 = v6;
    v6 = 0;
    v67 = 0;
    *v5 = v45;
    v46 = v62;
    v62 = 0;
    v5[1] = v46;
    v47 = v61;
    v61 = 0;
    v5[2] = v47;
    v48 = v60;
    v60 = 0;
    v5[3] = v48;
    v49 = Block;
    Block = 0;
    v5[4] = v49;
    v50 = v7;
    v7 = 0;
    v66 = 0;
    v5[5] = v50;
    v51 = v8;
    v8 = 0;
    v58 = 0;
    v5[6] = v51;
    v52 = v5;
    v5 = 0;
    v63 = 0;
    *((_QWORD *)a2 + 6) = v52;
  }
  v4 = 1;
LABEL_49:
  if ( v8 )
  {
    CCompressionMap<8>::`scalar deleting destructor'(v8, 0);
    if ( CSqlSortUtil::m_pmoSqlSort )
      operator delete[](v8);
    else
      free(v8);
  }
  if ( v7 )
  {
    CCompressionMap<8>::`scalar deleting destructor'(v7, 0);
    if ( CSqlSortUtil::m_pmoSqlSort )
      operator delete[](v7);
    else
      free(v7);
  }
  v53 = Block;
  if ( Block )
  {
    CCompressionMap<6>::`scalar deleting destructor'(Block, 0);
    if ( CSqlSortUtil::m_pmoSqlSort )
      operator delete[](Block);
    else
      free(v53);
  }
  v54 = v60;
  if ( v60 )
  {
    CCompressionMap<6>::`scalar deleting destructor'(v60, 0);
    if ( CSqlSortUtil::m_pmoSqlSort )
      operator delete[](v60);
    else
      free(v54);
  }
  v55 = v61;
  if ( v61 )
  {
    CCompressionMap<6>::`scalar deleting destructor'(v61, 0);
    if ( CSqlSortUtil::m_pmoSqlSort )
      operator delete[](v61);
    else
      free(v55);
  }
  v56 = v62;
  if ( v62 )
  {
    CCompressionMap<6>::`scalar deleting destructor'(v62, 0);
    if ( CSqlSortUtil::m_pmoSqlSort )
      operator delete[](v62);
    else
      free(v56);
  }
  if ( v6 )
  {
    CCompressionMap<2>::`scalar deleting destructor'(v6, 0);
    if ( CSqlSortUtil::m_pmoSqlSort )
      operator delete[](v6);
    else
      free(v6);
  }
  if ( v5 )
  {
    if ( CSqlSortUtil::m_pmoSqlSort )
      operator delete[](v5);
    else
      free(v5);
  }
  return v4;
}

```

## disassembly

```asm
0x1004a2fe0  mov     [rsp-38h+arg_0], rcx
0x1004a2fe5  push    rbp
0x1004a2fe6  push    rsi
0x1004a2fe7  push    rdi
0x1004a2fe8  push    r12
0x1004a2fea  push    r13
0x1004a2fec  push    r14
0x1004a2fee  push    r15
0x1004a2ff0  mov     rbp, rsp
0x1004a2ff3  sub     rsp, 70h
0x1004a2ff7  mov     [rbp+var_10], 0FFFFFFFFFFFFFFFEh
0x1004a2fff  mov     [rsp+70h+arg_8], rbx
0x1004a3007  mov     r13, rdx
0x1004a300a  mov     r11, rcx
0x1004a300d  xor     r12d, r12d
0x1004a3010  mov     r14d, r12d
0x1004a3013  mov     [rbp+var_18], r12
0x1004a3017  mov     edi, r12d
0x1004a301a  mov     [rbp+arg_18], r12
0x1004a301e  mov     [rbp+var_20], r12
0x1004a3022  mov     [rbp+var_28], r12
0x1004a3026  mov     [rbp+var_30], r12
0x1004a302a  mov     [rbp+Block], r12
0x1004a302e  mov     ebx, r12d
0x1004a3031  mov     [rbp+arg_10], rbx
0x1004a3035  mov     esi, r12d
0x1004a3038  mov     [rbp+var_40], r12
0x1004a303c  mov     edx, r12d
0x1004a303f  mov     r8d, [rcx+0F0h]
0x1004a3046  test    r8d, r8d
0x1004a3049  jz      loc_1004A3350
0x1004a304f  mov     r9, [rcx+0F8h]
0x1004a3056  mov     r10d, [r13+0]
0x1004a305a  nop     word ptr [rax+rax+00h]
0x1004a3060  mov     eax, edx
0x1004a3062  lea     r15, [rax+rax*4]
0x1004a3066  shl     r15, 4
0x1004a306a  add     r15, r9
0x1004a306d  cmp     [r15], r10d
0x1004a3070  jz      short loc_1004A307E
0x1004a3072  inc     edx
0x1004a3074  cmp     edx, r8d
0x1004a3077  jb      short loc_1004A3060
0x1004a3079  jmp     loc_1004A3350
0x1004a307e  mov     dword ptr [r13+14h], 1
0x1004a3086  mov     rdx, cs:?m_pmoSqlSort@CSqlSortUtil@@0PEAVIMemObj@@EA; IMemObj * CSqlSortUtil::m_pmoSqlSort
0x1004a308d  mov     ecx, 38h ; '8'; Size
0x1004a3092  test    rdx, rdx
0x1004a3095  jnz     short loc_1004A309F
0x1004a3097  call    cs:__imp_malloc
0x1004a309d  jmp     short loc_1004A30B7
0x1004a309f  mov     [rsp+70h+var_50], 6
0x1004a30a4  mov     r9d, 8Bh
0x1004a30aa  lea     r8, aSqlNtdbmsMsqlS; "sql\\ntdbms\\msql\\sqlsort\\common\\sor"...
0x1004a30b1  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x1004a30b7  mov     r14, rax
0x1004a30ba  mov     [rbp+var_18], rax
0x1004a30be  lea     r8, [rbp+arg_18]
0x1004a30c2  movzx   edx, word ptr [r15+8]
0x1004a30c7  mov     rcx, [r15+18h]
0x1004a30cb  call    ??$CreateCompressionMap@$01@CSqlSortManager_100@@KAHPEAU?$COMPRESS_NEW@$01@@GPEAPEAV?$CCompressionMap@$01@@@Z; CSqlSortManager_100::CreateCompressionMap<2>(COMPRESS_NEW<2> *,ushort,CCompressionMap<2> * *)
0x1004a30d0  test    eax, eax
0x1004a30d2  jz      loc_1004A3439
0x1004a30d8  lea     r8, [rbp+var_20]
0x1004a30dc  movzx   edx, word ptr [r15+0Ah]
0x1004a30e1  mov     rcx, [r15+20h]
0x1004a30e5  call    ??$CreateCompressionMap@$02@CSqlSortManager_100@@KAHPEAU?$COMPRESS_NEW@$02@@GPEAPEAV?$CCompressionMap@$02@@@Z; CSqlSortManager_100::CreateCompressionMap<3>(COMPRESS_NEW<3> *,ushort,CCompressionMap<3> * *)
0x1004a30ea  test    eax, eax
0x1004a30ec  jz      loc_1004A3439
0x1004a30f2  lea     r8, [rbp+var_28]
0x1004a30f6  movzx   edx, word ptr [r15+0Ch]
0x1004a30fb  mov     rcx, [r15+28h]
0x1004a30ff  call    ??$CreateCompressionMap@$03@CSqlSortManager_100@@KAHPEAU?$COMPRESS_NEW@$03@@GPEAPEAV?$CCompressionMap@$03@@@Z; CSqlSortManager_100::CreateCompressionMap<4>(COMPRESS_NEW<4> *,ushort,CCompressionMap<4> * *)
0x1004a3104  test    eax, eax
0x1004a3106  jz      loc_1004A3439
0x1004a310c  lea     r8, [rbp+var_30]
0x1004a3110  movzx   edx, word ptr [r15+0Eh]
0x1004a3115  mov     rcx, [r15+30h]
0x1004a3119  call    ??$CreateCompressionMap@$04@CSqlSortManager_100@@KAHPEAU?$COMPRESS_NEW@$04@@GPEAPEAV?$CCompressionMap@$04@@@Z; CSqlSortManager_100::CreateCompressionMap<5>(COMPRESS_NEW<5> *,ushort,CCompressionMap<5> * *)
0x1004a311e  test    eax, eax
0x1004a3120  jz      loc_1004A3439
0x1004a3126  lea     r8, [rbp+Block]
0x1004a312a  movzx   edx, word ptr [r15+10h]
0x1004a312f  mov     rcx, [r15+38h]
0x1004a3133  call    ??$CreateCompressionMap@$05@CSqlSortManager_100@@KAHPEAU?$COMPRESS_NEW@$05@@GPEAPEAV?$CCompressionMap@$05@@@Z; CSqlSortManager_100::CreateCompressionMap<6>(COMPRESS_NEW<6> *,ushort,CCompressionMap<6> * *)
0x1004a3138  test    eax, eax
0x1004a313a  jz      loc_1004A3439
0x1004a3140  lea     r8, [rbp+arg_10]
0x1004a3144  movzx   edx, word ptr [r15+12h]
0x1004a3149  mov     rcx, [r15+40h]
0x1004a314d  call    ??$CreateCompressionMap@$06@CSqlSortManager_100@@KAHPEAU?$COMPRESS_NEW@$06@@GPEAPEAV?$CCompressionMap@$06@@@Z; CSqlSortManager_100::CreateCompressionMap<7>(COMPRESS_NEW<7> *,ushort,CCompressionMap<7> * *)
0x1004a3152  test    eax, eax
0x1004a3154  jz      loc_1004A3435
0x1004a315a  lea     r8, [rbp+var_40]
0x1004a315e  movzx   edx, word ptr [r15+14h]
0x1004a3163  mov     rcx, [r15+48h]
0x1004a3167  call    ??$CreateCompressionMap@$07@CSqlSortManager_100@@KAHPEAU?$COMPRESS_NEW@$07@@GPEAPEAV?$CCompressionMap@$07@@@Z; CSqlSortManager_100::CreateCompressionMap<8>(COMPRESS_NEW<8> *,ushort,CCompressionMap<8> * *)
0x1004a316c  test    eax, eax
0x1004a316e  jz      loc_1004A3431
0x1004a3174  movzx   eax, word ptr [r15+8]
0x1004a3179  mov     rcx, [r15+18h]
0x1004a317d  test    ax, ax
0x1004a3180  jz      short loc_1004A31A9
0x1004a3182  mov     r8, [r13+8]
0x1004a3186  cmp     r12w, ax
0x1004a318a  jnb     short loc_1004A31A9
0x1004a318c  mov     edx, eax
0x1004a318e  xchg    ax, ax
0x1004a3190  movzx   eax, word ptr [rcx]
0x1004a3193  and     byte ptr [r8+rax*4+3], 3Fh
0x1004a3199  or      byte ptr [r8+rax*4+3], 80h
0x1004a319f  lea     rcx, [rcx+8]
0x1004a31a3  sub     rdx, 1
0x1004a31a7  jnz     short loc_1004A3190
0x1004a31a9  movzx   eax, word ptr [r15+0Ah]
0x1004a31ae  mov     rcx, [r15+20h]
0x1004a31b2  test    ax, ax
0x1004a31b5  jz      short loc_1004A31D6
0x1004a31b7  mov     r8, [r13+8]
0x1004a31bb  cmp     r12w, ax
0x1004a31bf  jnb     short loc_1004A31D6
0x1004a31c1  mov     edx, eax
0x1004a31c3  movzx   eax, word ptr [rcx]
0x1004a31c6  or      byte ptr [r8+rax*4+3], 0C0h
0x1004a31cc  lea     rcx, [rcx+0Ah]
0x1004a31d0  sub     rdx, 1
0x1004a31d4  jnz     short loc_1004A31C3
0x1004a31d6  movzx   eax, word ptr [r15+0Ch]
0x1004a31db  mov     rcx, [r15+28h]
0x1004a31df  test    ax, ax
0x1004a31e2  jz      short loc_1004A3209
0x1004a31e4  mov     r8, [r13+8]
0x1004a31e8  cmp     r12w, ax
0x1004a31ec  jnb     short loc_1004A3209
0x1004a31ee  mov     edx, eax
0x1004a31f0  movzx   eax, word ptr [rcx]
0x1004a31f3  and     byte ptr [r8+rax*4+3], 3Fh
0x1004a31f9  or      byte ptr [r8+rax*4+3], 40h
0x1004a31ff  lea     rcx, [rcx+0Ch]
0x1004a3203  sub     rdx, 1
0x1004a3207  jnz     short loc_1004A31F0
0x1004a3209  movzx   eax, word ptr [r15+0Eh]
0x1004a320e  mov     rcx, [r15+30h]
0x1004a3212  test    ax, ax
0x1004a3215  jz      short loc_1004A3249
0x1004a3217  mov     r8, [r13+8]
0x1004a321b  cmp     r12w, ax
0x1004a321f  jnb     short loc_1004A3249
0x1004a3221  mov     edx, eax
0x1004a3223  nop     dword ptr [rax+00h]
0x1004a3227  nop     word ptr [rax+rax+00000000h]
0x1004a3230  movzx   eax, word ptr [rcx]
0x1004a3233  and     byte ptr [r8+rax*4+3], 3Fh
0x1004a3239  or      byte ptr [r8+rax*4+3], 40h
0x1004a323f  lea     rcx, [rcx+0Eh]
0x1004a3243  sub     rdx, 1
0x1004a3247  jnz     short loc_1004A3230
0x1004a3249  movzx   eax, word ptr [r15+10h]
0x1004a324e  mov     rcx, [r15+38h]
0x1004a3252  test    ax, ax
0x1004a3255  jz      short loc_1004A3289
0x1004a3257  mov     r8, [r13+8]
0x1004a325b  cmp     r12w, ax
0x1004a325f  jnb     short loc_1004A3289
0x1004a3261  mov     edx, eax
0x1004a3263  nop     dword ptr [rax+00h]
0x1004a3267  nop     word ptr [rax+rax+00000000h]
0x1004a3270  movzx   eax, word ptr [rcx]
0x1004a3273  and     byte ptr [r8+rax*4+3], 3Fh
0x1004a3279  or      byte ptr [r8+rax*4+3], 40h
0x1004a327f  lea     rcx, [rcx+10h]
0x1004a3283  sub     rdx, 1
0x1004a3287  jnz     short loc_1004A3270
0x1004a3289  movzx   eax, word ptr [r15+12h]
0x1004a328e  mov     rcx, [r15+40h]
0x1004a3292  test    ax, ax
0x1004a3295  jz      short loc_1004A32C9
0x1004a3297  mov     r8, [r13+8]
0x1004a329b  cmp     r12w, ax
0x1004a329f  jnb     short loc_1004A32C9
0x1004a32a1  mov     edx, eax
0x1004a32a3  nop     dword ptr [rax+00h]
0x1004a32a7  nop     word ptr [rax+rax+00000000h]
0x1004a32b0  movzx   eax, word ptr [rcx]
0x1004a32b3  and     byte ptr [r8+rax*4+3], 3Fh
0x1004a32b9  or      byte ptr [r8+rax*4+3], 40h
0x1004a32bf  lea     rcx, [rcx+12h]
0x1004a32c3  sub     rdx, 1
0x1004a32c7  jnz     short loc_1004A32B0
0x1004a32c9  movzx   eax, word ptr [r15+14h]
0x1004a32ce  mov     rcx, [r15+48h]
0x1004a32d2  test    ax, ax
0x1004a32d5  jz      short loc_1004A3309
0x1004a32d7  mov     r8, [r13+8]
0x1004a32db  cmp     r12w, ax
0x1004a32df  jnb     short loc_1004A3309
0x1004a32e1  mov     edx, eax
0x1004a32e3  nop     dword ptr [rax+00h]
0x1004a32e7  nop     word ptr [rax+rax+00000000h]
0x1004a32f0  movzx   eax, word ptr [rcx]
0x1004a32f3  and     byte ptr [r8+rax*4+3], 3Fh
0x1004a32f9  or      byte ptr [r8+rax*4+3], 40h
0x1004a32ff  lea     rcx, [rcx+14h]
0x1004a3303  sub     rdx, 1
0x1004a3307  jnz     short loc_1004A32F0
0x1004a3309  mov     r11, [rbp+arg_0]
0x1004a330d  movsxd  rax, dword ptr [r11+98h]
0x1004a3314  test    eax, eax
0x1004a3316  jle     short loc_1004A3344
0x1004a3318  mov     edx, [r13+0]
0x1004a331c  mov     r8, rax
0x1004a331f  mov     rcx, r12
0x1004a3322  mov     rax, [r11+0A0h]
0x1004a3329  nop     dword ptr [rax+00000000h]
0x1004a3330  cmp     [rax], edx
0x1004a3332  jz      loc_1004A3424
0x1004a3338  inc     rcx
0x1004a333b  add     rax, 4
0x1004a333f  cmp     rcx, r8
0x1004a3342  jl      short loc_1004A3330
0x1004a3344  mov     rdi, [rbp+arg_18]
0x1004a3348  mov     rbx, [rbp+arg_10]
0x1004a334c  mov     rsi, [rbp+var_40]
0x1004a3350  mov     edx, r12d
0x1004a3353  cmp     [r11+100h], edx
0x1004a335a  jbe     short loc_1004A338E
0x1004a335c  mov     r8d, [r13+0]
0x1004a3360  mov     ecx, edx
0x1004a3362  add     rcx, rcx
0x1004a3365  mov     rax, [r11+108h]
0x1004a336c  cmp     [rax+rcx*8], r8d
0x1004a3370  jnz     short loc_1004A3383
0x1004a3372  mov     rax, [rax+rcx*8+8]
0x1004a3377  mov     [r13+38h], rax
0x1004a337b  mov     dword ptr [r13+14h], 1
0x1004a3383  inc     edx
0x1004a3385  cmp     edx, [r11+100h]
0x1004a338c  jb      short loc_1004A3360
0x1004a338e  test    r14, r14
0x1004a3391  jz      short loc_1004A33FA
0x1004a3393  mov     rax, rdi
0x1004a3396  mov     rdi, r12
0x1004a3399  mov     [rbp+arg_18], r12
0x1004a339d  mov     [r14], rax
0x1004a33a0  mov     rax, [rbp+var_20]
0x1004a33a4  mov     [rbp+var_20], r12
0x1004a33a8  mov     [r14+8], rax
0x1004a33ac  mov     rax, [rbp+var_28]
0x1004a33b0  mov     [rbp+var_28], r12
0x1004a33b4  mov     [r14+10h], rax
0x1004a33b8  mov     rax, [rbp+var_30]
0x1004a33bc  mov     [rbp+var_30], r12
0x1004a33c0  mov     [r14+18h], rax
0x1004a33c4  mov     rax, [rbp+Block]
0x1004a33c8  mov     [rbp+Block], r12
0x1004a33cc  mov     [r14+20h], rax
0x1004a33d0  mov     rax, rbx
0x1004a33d3  mov     rbx, r12
0x1004a33d6  mov     [rbp+arg_10], rbx
0x1004a33da  mov     [r14+28h], rax
0x1004a33de  mov     rax, rsi
0x1004a33e1  mov     rsi, r12
0x1004a33e4  mov     [rbp+var_40], r12
0x1004a33e8  mov     [r14+30h], rax
0x1004a33ec  mov     rax, r14
0x1004a33ef  mov     r14, r12
0x1004a33f2  mov     [rbp+var_18], r12
0x1004a33f6  mov     [r13+30h], rax
0x1004a33fa  mov     r12d, 1
0x1004a3400  test    rsi, rsi
0x1004a3403  jz      short loc_1004A3446
0x1004a3405  xor     edx, edx
0x1004a3407  mov     rcx, rsi
0x1004a340a  call    ??_G?$CCompressionMap@$07@@QEAAPEAXI@Z; CCompressionMap<8>::`scalar deleting destructor'(uint)
0x1004a340f  mov     rcx, rsi; Block
0x1004a3412  cmp     cs:?m_pmoSqlSort@CSqlSortUtil@@0PEAVIMemObj@@EA, 0; IMemObj * CSqlSortUtil::m_pmoSqlSort
0x1004a341a  jnz     short loc_1004A343F
0x1004a341c  call    cs:__imp_free
0x1004a3422  jmp     short loc_1004A3446
0x1004a3424  mov     dword ptr [r13+18h], 1
0x1004a342c  jmp     loc_1004A3344
0x1004a3431  mov     rsi, [rbp+var_40]
0x1004a3435  mov     rbx, [rbp+arg_10]
0x1004a3439  mov     rdi, [rbp+arg_18]
0x1004a343d  jmp     short loc_1004A3400
0x1004a343f  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1004a3445  nop
0x1004a3446  test    rbx, rbx
0x1004a3449  jz      short loc_1004A3471
0x1004a344b  xor     edx, edx
0x1004a344d  mov     rcx, rbx
0x1004a3450  call    ??_G?$CCompressionMap@$07@@QEAAPEAXI@Z; CCompressionMap<8>::`scalar deleting destructor'(uint)
0x1004a3455  mov     rcx, rbx; Block
0x1004a3458  cmp     cs:?m_pmoSqlSort@CSqlSortUtil@@0PEAVIMemObj@@EA, 0; IMemObj * CSqlSortUtil::m_pmoSqlSort
0x1004a3460  jnz     short loc_1004A346A
0x1004a3462  call    cs:__imp_free
0x1004a3468  jmp     short loc_1004A3471
0x1004a346a  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1004a3470  nop
0x1004a3471  mov     rbx, [rbp+Block]
  ... truncated ...
```
