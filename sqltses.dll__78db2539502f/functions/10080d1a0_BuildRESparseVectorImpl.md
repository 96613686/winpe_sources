# BuildRESparseVectorImpl

- ea: `0x10080d1a0`
- end: `0x10080d6fe`
- name: `BuildRESparseVectorImpl`
- size: `1374`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x10080d180`

## callees

- `0x1004011fc`
- `0x100406280`
- `0x10048bd50`
- `0x10048cd80`
- `0x10048cee0`
- `0x10048d040`
- `0x10080d1a0`

## import_xrefs

- `sqldk!??_V@YAXPEAX@Z` at `0x10080d659`
- `sqldk!??_V@YAXPEAX@Z` at `0x10080d67b`
- `sqldk!??_V@YAXPEAX@Z` at `0x10080d69f`
- `sqldk!??_V@YAXPEAX@Z` at `0x10080d6d0`
- `sqldk!??_V@YAXPEAX@Z` at `0x10080d659`
- `sqldk!??_V@YAXPEAX@Z` at `0x10080d67b`
- `sqldk!??_V@YAXPEAX@Z` at `0x10080d69f`
- `sqldk!??_V@YAXPEAX@Z` at `0x10080d6d0`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10080d2a9`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10080d2a9`
- `sqldk!SystemThread_TlsIndex` at `0x10080d240`
- `sqldk!SystemThread_TlsOffset` at `0x10080d249`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10080d262`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10080d262`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10080d457`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10080d518`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10080d548`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10080d5a4`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10080d457`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10080d518`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10080d548`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10080d5a4`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
void __fastcall BuildRESparseVectorImpl(__int64 a1, __int64 a2)
{
  __int64 v3; // rsi
  __int64 v4; // rax
  __int64 v5; // rdi
  __int64 v6; // r8
  __int64 v7; // r15
  __int64 v8; // rbx
  __int64 v9; // rcx
  struct IMemObj *v10; // rbx
  unsigned __int64 v11; // rax
  void *v12; // r12
  __int64 v13; // r8
  unsigned __int16 v14; // dx
  __int64 v15; // rdi
  unsigned __int8 *v16; // r15
  int v17; // r13d
  int v18; // r14d
  const struct CTypeInfo *v19; // rbx
  bool v20; // cf
  __int64 v21; // r12
  __int64 v22; // rax
  unsigned __int8 *v23; // rdi
  unsigned __int16 v24; // si
  bool v25; // cl
  __int16 v26; // ax
  __int64 v27; // rbx
  __int64 v28; // r13
  int v29; // edi
  __int64 v30; // r15
  _QWORD *v31; // rbx
  char v32[4]; // [rsp+30h] [rbp-D0h] BYREF
  int v33; // [rsp+34h] [rbp-CCh]
  struct IMemObj *v34; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v35; // [rsp+48h] [rbp-B8h]
  __int64 v36; // [rsp+50h] [rbp-B0h]
  struct IMemObj *v37; // [rsp+58h] [rbp-A8h] BYREF
  int v38; // [rsp+64h] [rbp-9Ch]
  int v39; // [rsp+68h] [rbp-98h]
  void *v40; // [rsp+70h] [rbp-90h]
  struct IMemObj *v41; // [rsp+78h] [rbp-88h] BYREF
  int v42; // [rsp+84h] [rbp-7Ch]
  int v43; // [rsp+88h] [rbp-78h]
  void *v44; // [rsp+90h] [rbp-70h]
  struct IMemObj *v45; // [rsp+98h] [rbp-68h] BYREF
  int v46; // [rsp+A4h] [rbp-5Ch]
  int v47; // [rsp+A8h] [rbp-58h]
  void *v48; // [rsp+B0h] [rbp-50h]
  __int64 v49; // [rsp+B8h] [rbp-48h]
  __int64 v50; // [rsp+C0h] [rbp-40h]
  _QWORD *v51; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v52; // [rsp+D0h] [rbp-30h]
  void *v53; // [rsp+D8h] [rbp-28h]
  int v54; // [rsp+E0h] [rbp-20h]
  __int64 v55; // [rsp+E8h] [rbp-18h]
  __int64 v56; // [rsp+F0h] [rbp-10h]
  __int64 v57; // [rsp+F8h] [rbp-8h]
  __int64 v58; // [rsp+100h] [rbp+0h]
  __int64 v59; // [rsp+108h] [rbp+8h]
  _QWORD *v62; // [rsp+170h] [rbp+70h] BYREF
  unsigned int v63; // [rsp+178h] [rbp+78h] BYREF

  v58 = -2;
  v3 = a1;
  v4 = *(_QWORD *)(a1 + 32);
  v5 = *(int *)(v4 + 12);
  v33 = v5;
  if ( (int)v5 <= 0 )
  {
    *(_BYTE *)a2 = 3;
    return;
  }
  v6 = *(unsigned __int16 *)(v4 + 18);
  v57 = *(_QWORD *)(*(_QWORD *)(a1 + 56) + 8 * v6);
  v63 = *(unsigned __int16 *)(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 32LL) + 2 * v6);
  (*(void (__fastcall **)(_QWORD, __int64, unsigned int *, __int64, _DWORD))(**(_QWORD **)(a1 + 80) + 96LL))(
    *(_QWORD *)(a1 + 80),
    v57,
    &v63,
    a1,
    0);
  v7 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v57 + 8LL))(v57, 0);
  v56 = v7;
  v59 = v7;
  v8 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v9 = *(_QWORD *)(v8 + 256);
  if ( !v9 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v9 = *(_QWORD *)(v8 + 256);
  }
  v10 = *(struct IMemObj **)(v9 + 1000);
  v54 = v5;
  v55 = (unsigned int)v5;
  v11 = 8LL * (unsigned int)v5;
  if ( !is_mul_ok((unsigned int)v5, 8u) )
    v11 = -1;
  v12 = operator new[](v11, v10, "sql\\ntdbms\\msql\\expr\\runtime\\ReSparseVectorEsIntrinsic.cpp", 30, 3u);
  v53 = v12;
  memset_0(v12, 0, (unsigned int)(8 * v5));
  v34 = v10;
  v62 = &v37;
  v37 = v10;
  v39 = 40;
  v40 = 0;
  v41 = v10;
  v43 = 40;
  v44 = 0;
  v51 = &v45;
  v45 = v10;
  v47 = 40;
  v48 = 0;
  v49 = 0;
  v36 = v7;
  v14 = 0;
  v35 = 0;
  v38 = 0;
  v42 = 0;
  v46 = 0;
  v52 = v5;
  v15 = 0;
  v50 = 0;
  v16 = (unsigned __int8 *)(a2 + 40);
  v17 = 0;
  do
  {
    v18 = *((_DWORD *)v16 - 8);
    v19 = (const struct CTypeInfo *)(*(_QWORD *)(*(_QWORD *)(v3 + 16) + 168LL)
                                   + 32LL * (v17 + (unsigned int)*(unsigned __int16 *)(*(_QWORD *)(v3 + 32) + 24LL)));
    if ( *(v16 - 8) == 3 )
    {
      v20 = v14 < 0x800u;
      goto LABEL_37;
    }
    if ( *((_WORD *)v19 + 8) == 0xFFFF )
      goto LABEL_30;
    v21 = *(unsigned __int8 *)v19;
    v22 = *((unsigned __int8 *)&xsm_rgOrdFromXvt + v21);
    if ( *((_BYTE *)&CTypeInfo::sxm_rgfIsLargeObject + v22) )
    {
      v12 = v53;
LABEL_30:
      v27 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int16 *))(**(_QWORD **)v16 + 8LL))(
              *(_QWORD *)v16,
              0,
              v13,
              &CTypeInfo::tiBit);
      if ( (*(unsigned int (__fastcall **)(__int64, char *))(*(_QWORD *)v27 + 152LL))(v27, v32) )
        ex_raise(71, 2, 20, 99);
      if ( (v32[0] & 1) == 0 )
      {
        *((_QWORD *)v12 + v15) = v27;
        LODWORD(v62) = v18;
        if ( v35 >= 0x800u )
          ex_raise(98, 16, 16, 1);
        CTDynArray<unsigned long,CFnI_Default<unsigned long>,CFnD_Noop<unsigned long>,CMemObjAlloc<0>>::UlAdd(
          &v37,
          &v62);
        v62 = (_QWORD *)v27;
        CTDynArray<ApproxCountDistinctHashValueItem *,CFnI_Default<ApproxCountDistinctHashValueItem *>,CFnD_Ptr<ApproxCountDistinctHashValueItem>,CMemObjAlloc<0>>::UlAdd(
          &v41,
          &v62);
        CTDynArray<unsigned short,CFnI_Default<unsigned short>,CFnD_Noop<unsigned short>,CMemObjAlloc<0>>::UlAdd(
          &v45,
          &CRESparseVector::x_usLobIndicator);
        v14 = v35 + 1;
        goto LABEL_40;
      }
      v20 = v35 < 0x800u;
LABEL_37:
      LODWORD(v62) = v18;
      if ( !v20 )
        ex_raise(98, 16, 16, 1);
      CTDynArray<unsigned long,CFnI_Default<unsigned long>,CFnD_Noop<unsigned long>,CMemObjAlloc<0>>::UlAdd(&v37, &v62);
      v62 = 0;
      CTDynArray<ApproxCountDistinctHashValueItem *,CFnI_Default<ApproxCountDistinctHashValueItem *>,CFnD_Ptr<ApproxCountDistinctHashValueItem>,CMemObjAlloc<0>>::UlAdd(
        &v41,
        &v62);
      CTDynArray<unsigned short,CFnI_Default<unsigned short>,CFnD_Noop<unsigned short>,CMemObjAlloc<0>>::UlAdd(
        &v45,
        &CRESparseVector::x_usNullIndicator);
      v14 = v35 + 1;
LABEL_40:
      v35 = v14;
      goto LABEL_41;
    }
    if ( *((_BYTE *)&CTypeInfo::sxm_rgfIsNumeric + v22) )
    {
      v23 = v16 + 3;
    }
    else if ( *((_BYTE *)&xsm_rgfIsDeepType + v22) )
    {
      v23 = *(unsigned __int8 **)v16;
    }
    else
    {
      v23 = v16;
    }
    if ( *((_BYTE *)&CTypeInfo::sxm_rgfIsNumeric + *((unsigned __int8 *)&xsm_rgOrdFromXvt + v21)) )
    {
      v24 = *((unsigned __int8 *)&qword_1008644E8[255] + v16[1] + 7);
    }
    else
    {
      v24 = CXVariant::CbSize((CXVariant *)(v16 - 8), v19);
      LOBYTE(v21) = *(_BYTE *)v19;
      v14 = v35;
    }
    v51 = v23;
    LODWORD(v62) = v18;
    if ( v14 >= 0x800u )
      ex_raise(98, 16, 16, 1);
    CTDynArray<unsigned long,CFnI_Default<unsigned long>,CFnD_Noop<unsigned long>,CMemObjAlloc<0>>::UlAdd(&v37, &v62);
    CTDynArray<ApproxCountDistinctHashValueItem *,CFnI_Default<ApproxCountDistinctHashValueItem *>,CFnD_Ptr<ApproxCountDistinctHashValueItem>,CMemObjAlloc<0>>::UlAdd(
      &v41,
      &v51);
    v25 = *((_BYTE *)&xsm_rgfIsDeepType + *((unsigned __int8 *)&xsm_rgOrdFromXvt + (unsigned __int8)v21)) && v24 > 0x10u;
    v26 = v24 | 0x8000;
    if ( !v25 )
      v26 = v24;
    LOWORD(v62) = v26;
    CTDynArray<unsigned short,CFnI_Default<unsigned short>,CFnD_Noop<unsigned short>,CMemObjAlloc<0>>::UlAdd(&v45, &v62);
    v14 = ++v35;
    v15 = v50;
    v3 = a1;
LABEL_41:
    ++v17;
    v50 = ++v15;
    v16 += 64;
    v12 = v53;
  }
  while ( v15 < v52 );
  v28 = v55;
  v29 = v33;
  v30 = v56;
  CRESparseVectorWriter::Write((CRESparseVectorWriter *)&v34);
  *(_QWORD *)(a2 + 8) = v57;
  *(_QWORD *)(a2 + 16) = v63;
  *(_BYTE *)a2 = 0;
  v46 = 0;
  if ( v48 )
  {
    operator delete[](v48);
    v48 = 0;
  }
  v47 = 0;
  v42 = 0;
  if ( v44 )
  {
    operator delete[](v44);
    v44 = 0;
  }
  v43 = 0;
  v38 = 0;
  if ( v40 )
  {
    operator delete[](v40);
    v40 = 0;
  }
  v39 = 0;
  if ( v29 )
  {
    v31 = v12;
    do
    {
      if ( *v31 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v31 + 16LL))(*v31);
      ++v31;
      --v28;
    }
    while ( v28 );
  }
  operator delete[](v12);
  if ( v30 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
}

```

## disassembly

```asm
0x10080d1a0  mov     [rsp-8+arg_8], rdx
0x10080d1a5  mov     [rsp-8+arg_0], rcx
0x10080d1aa  push    rbp
0x10080d1ab  push    rbx
0x10080d1ac  push    rsi
0x10080d1ad  push    rdi
0x10080d1ae  push    r12
0x10080d1b0  push    r13
0x10080d1b2  push    r14
0x10080d1b4  push    r15
0x10080d1b6  lea     rbp, [rsp-18h]
0x10080d1bb  sub     rsp, 118h
0x10080d1c2  mov     [rbp+50h+var_50], 0FFFFFFFFFFFFFFFEh
0x10080d1ca  mov     r14, rdx
0x10080d1cd  mov     rsi, rcx
0x10080d1d0  mov     rax, [rcx+20h]
0x10080d1d4  movsxd  rdi, dword ptr [rax+0Ch]
0x10080d1d8  mov     [rsp+150h+var_11C], edi
0x10080d1dc  test    edi, edi
0x10080d1de  jle     loc_10080D6E7
0x10080d1e4  movzx   r8d, word ptr [rax+12h]
0x10080d1e9  mov     rax, [rcx+38h]
0x10080d1ed  mov     rbx, [rax+r8*8]
0x10080d1f1  mov     [rbp+50h+var_58], rbx
0x10080d1f5  mov     rax, [rcx+10h]
0x10080d1f9  mov     rdx, [rax+20h]
0x10080d1fd  movzx   eax, word ptr [rdx+r8*2]
0x10080d202  mov     [rbp+50h+arg_18], eax
0x10080d205  mov     rcx, [rcx+50h]
0x10080d209  mov     rax, [rcx]
0x10080d20c  mov     [rsp+150h+var_130], 0
0x10080d214  mov     r9, rsi
0x10080d217  lea     r8, [rbp+50h+arg_18]
0x10080d21b  mov     rdx, rbx
0x10080d21e  call    qword ptr [rax+60h]
0x10080d221  mov     rax, [rbx]
0x10080d224  xor     edx, edx
0x10080d226  mov     rcx, rbx
0x10080d229  call    qword ptr [rax+8]
0x10080d22c  mov     r15, rax
0x10080d22f  mov     [rbp+50h+var_60], rax
0x10080d233  mov     [rbp+50h+var_48], rax
0x10080d237  mov     r8, gs:58h
0x10080d240  mov     rcx, cs:__imp_SystemThread_TlsIndex
0x10080d247  mov     edx, [rcx]
0x10080d249  mov     rcx, cs:__imp_SystemThread_TlsOffset
0x10080d250  mov     ebx, [rcx]
0x10080d252  add     rbx, [r8+rdx*8]
0x10080d256  mov     rcx, [rbx+100h]
0x10080d25d  test    rcx, rcx
0x10080d260  jnz     short loc_10080D26F
0x10080d262  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10080d268  mov     rcx, [rbx+100h]
0x10080d26f  mov     rbx, [rcx+3E8h]
0x10080d276  mov     [rbp+50h+var_70], edi
0x10080d279  mov     r13d, edi
0x10080d27c  mov     [rbp+50h+var_68], r13
0x10080d280  mov     eax, 8
0x10080d285  mul     r13
0x10080d288  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x10080d28f  cmovo   rax, rcx
0x10080d293  mov     byte ptr [rsp+150h+var_130], 3
0x10080d298  lea     r9d, [rcx+1Fh]
0x10080d29c  lea     r8, aSqlNtdbmsMsqlE_1; "sql\\ntdbms\\msql\\expr\\runtime\\ReSpa"...
0x10080d2a3  mov     rdx, rbx
0x10080d2a6  mov     rcx, rax
0x10080d2a9  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x10080d2af  mov     r12, rax
0x10080d2b2  mov     [rbp+50h+var_78], rax
0x10080d2b6  lea     r8d, ds:0[rdi*8]; Size
0x10080d2be  xor     edx, edx; Val
0x10080d2c0  mov     rcx, rax; void *
0x10080d2c3  call    memset_0
0x10080d2c8  nop
0x10080d2c9  mov     [rsp+150h+var_110], rbx
0x10080d2ce  xor     ecx, ecx
0x10080d2d0  mov     [rsp+150h+var_108], cx
0x10080d2d5  mov     [rsp+150h+var_100], rcx
0x10080d2da  lea     rax, [rsp+150h+var_F8]
0x10080d2df  mov     [rbp+50h+arg_10], rax
0x10080d2e3  mov     [rsp+150h+var_F8], rbx
0x10080d2e8  mov     [rsp+150h+var_EC], ecx
0x10080d2ec  mov     [rsp+150h+var_E8], 28h ; '('
0x10080d2f4  mov     [rsp+150h+var_E0], rcx
0x10080d2f9  lea     rax, [rsp+150h+var_D8]
0x10080d2fe  mov     [rbp+50h+var_80], rax
0x10080d302  mov     [rsp+150h+var_D8], rbx
0x10080d307  mov     [rbp+50h+var_CC], ecx
0x10080d30a  mov     [rbp+50h+var_C8], 28h ; '('
0x10080d311  mov     [rbp+50h+var_C0], rcx
0x10080d315  lea     rax, [rbp+50h+var_B8]
0x10080d319  mov     [rbp+50h+var_88], rax
0x10080d31d  mov     [rbp+50h+var_B8], rbx
0x10080d321  xor     ebx, ebx
0x10080d323  mov     [rbp+50h+var_AC], ebx
0x10080d326  mov     [rbp+50h+var_A8], 28h ; '('
0x10080d32d  mov     [rbp+50h+var_A0], rbx
0x10080d331  mov     [rbp+50h+var_98], rbx
0x10080d335  mov     [rsp+150h+var_100], r15
0x10080d33a  movzx   edx, bx
0x10080d33d  mov     [rsp+150h+var_108], bx
0x10080d342  mov     [rsp+150h+var_EC], ebx
0x10080d346  mov     [rbp+50h+var_CC], ebx
0x10080d349  mov     [rbp+50h+var_AC], ebx
0x10080d34c  mov     [rbp+50h+var_80], rdi
0x10080d350  test    edi, edi
0x10080d352  jle     loc_10080D628
0x10080d358  mov     edi, ebx
0x10080d35a  mov     [rbp+50h+var_90], rbx
0x10080d35e  lea     r15, [r14+28h]
0x10080d362  mov     r10d, 800h
0x10080d368  mov     r11d, 0FFFFh
0x10080d36e  lea     r9, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x10080d375  mov     r13d, edi
0x10080d378  nop     dword ptr [rax+rax+00000000h]
0x10080d380  mov     r14d, [r15-20h]
0x10080d384  mov     rax, [rsi+20h]
0x10080d388  movzx   ebx, word ptr [rax+18h]
0x10080d38c  add     ebx, r13d
0x10080d38f  shl     rbx, 5
0x10080d393  mov     rax, [rsi+10h]
0x10080d397  add     rbx, [rax+0A8h]
0x10080d39e  cmp     byte ptr [r15-8], 3
0x10080d3a3  jnz     short loc_10080D3AE
0x10080d3a5  cmp     dx, r10w
0x10080d3a9  jmp     loc_10080D58F
0x10080d3ae  cmp     [rbx+10h], r11w
0x10080d3b3  jz      loc_10080D4E4
0x10080d3b9  movzx   r12d, byte ptr [rbx]
0x10080d3bd  movzx   eax, ds:rva ?xsm_rgOrdFromXvt@@3QBEB[r9+r12]; CTypeInfo const CTypeInfo::tiBit
0x10080d3c6  cmp     byte ptr [rax+r9+4F3B00h], 0
0x10080d3cf  jnz     loc_10080D4E0
0x10080d3d5  cmp     byte ptr [rax+r9+464240h], 0
0x10080d3de  jz      short loc_10080D3E6
0x10080d3e0  lea     rdi, [r15+3]
0x10080d3e4  jmp     short loc_10080D3F9
0x10080d3e6  cmp     byte ptr [rax+r9+45BE00h], 0
0x10080d3ef  jz      short loc_10080D3F6
0x10080d3f1  mov     rdi, [r15]
0x10080d3f4  jmp     short loc_10080D3F9
0x10080d3f6  mov     rdi, r15
0x10080d3f9  movzx   ecx, ds:rva ?xsm_rgOrdFromXvt@@3QBEB[r9+r12]; CTypeInfo const CTypeInfo::tiBit
0x10080d402  cmp     byte ptr [rcx+r9+464240h], 0
0x10080d40b  jz      short loc_10080D41D
0x10080d40d  movzx   eax, byte ptr [r15+1]
0x10080d412  movzx   esi, byte ptr [rax+r9+464CE7h]
0x10080d41b  jmp     short loc_10080D43A
0x10080d41d  mov     rdx, rbx; struct CTypeInfo *
0x10080d420  lea     rcx, [r15-8]; this
0x10080d424  call    ?CbSize@CXVariant@@QEBAKPEBVCTypeInfo@@@Z; CXVariant::CbSize(CTypeInfo const *)
0x10080d429  mov     esi, eax
0x10080d42b  movzx   r12d, byte ptr [rbx]
0x10080d42f  movzx   edx, [rsp+150h+var_108]
0x10080d434  mov     r10d, 800h
0x10080d43a  mov     [rbp+50h+var_88], rdi
0x10080d43e  mov     dword ptr [rbp+50h+arg_10], r14d
0x10080d442  cmp     dx, r10w
0x10080d446  jb      short loc_10080D45D
0x10080d448  mov     edx, 10h
0x10080d44d  lea     ecx, [rdx+52h]
0x10080d450  lea     r9d, [rdx-0Fh]
0x10080d454  mov     r8d, edx
0x10080d457  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10080d45d  lea     rdx, [rbp+50h+arg_10]
0x10080d461  lea     rcx, [rsp+150h+var_F8]
0x10080d466  call    ?UlAdd@?$CTDynArray@KV?$CFnI_Default@K@@V?$CFnD_Noop@K@@V?$CMemObjAlloc@$0A@@@@@QEAAKAEBK@Z; CTDynArray<ulong,CFnI_Default<ulong>,CFnD_Noop<ulong>,CMemObjAlloc<0>>::UlAdd(ulong const &)
0x10080d46b  lea     rdx, [rbp+50h+var_88]
0x10080d46f  lea     rcx, [rsp+150h+var_D8]
0x10080d474  call    ?UlAdd@?$CTDynArray@PEAUApproxCountDistinctHashValueItem@@V?$CFnI_Default@PEAUApproxCountDistinctHashValueItem@@@@V?$CFnD_Ptr@UApproxCountDistinctHashValueItem@@@@V?$CMemObjAlloc@$0A@@@@@QEAAKAEBQEAUApproxCountDistinctHashValueItem@@@Z; CTDynArray<ApproxCountDistinctHashValueItem *,CFnI_Default<ApproxCountDistinctHashValueItem *>,CFnD_Ptr<ApproxCountDistinctHashValueItem>,CMemObjAlloc<0>>::UlAdd(ApproxCountDistinctHashValueItem * const &)
0x10080d479  movzx   eax, r12b
0x10080d47d  lea     rdx, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x10080d484  movzx   ecx, byte ptr [rax+rdx+45AE60h]
0x10080d48c  cmp     byte ptr [rcx+rdx+45BE00h], 0
0x10080d494  jz      short loc_10080D4A0
0x10080d496  cmp     si, 10h
0x10080d49a  jbe     short loc_10080D4A0
0x10080d49c  mov     cl, 1
0x10080d49e  jmp     short loc_10080D4A2
0x10080d4a0  xor     cl, cl
0x10080d4a2  movzx   eax, si
0x10080d4a5  mov     edx, 8000h
0x10080d4aa  or      ax, dx
0x10080d4ad  test    cl, cl
0x10080d4af  cmovz   ax, si
0x10080d4b3  mov     word ptr [rbp+50h+arg_10], ax
0x10080d4b7  lea     rdx, [rbp+50h+arg_10]
0x10080d4bb  lea     rcx, [rbp+50h+var_B8]
0x10080d4bf  call    ?UlAdd@?$CTDynArray@GV?$CFnI_Default@G@@V?$CFnD_Noop@G@@V?$CMemObjAlloc@$0A@@@@@QEAAKAEBG@Z; CTDynArray<ushort,CFnI_Default<ushort>,CFnD_Noop<ushort>,CMemObjAlloc<0>>::UlAdd(ushort const &)
0x10080d4c4  movzx   edx, [rsp+150h+var_108]
0x10080d4c9  inc     dx
0x10080d4cc  mov     [rsp+150h+var_108], dx
0x10080d4d1  mov     rdi, [rbp+50h+var_90]
0x10080d4d5  mov     rsi, [rbp+50h+arg_0]
0x10080d4d9  xor     ebx, ebx
0x10080d4db  jmp     loc_10080D5E9
0x10080d4e0  mov     r12, [rbp+50h+var_78]
0x10080d4e4  mov     rcx, [r15]
0x10080d4e7  mov     rax, [rcx]
0x10080d4ea  xor     edx, edx
0x10080d4ec  call    qword ptr [rax+8]
0x10080d4ef  mov     rbx, rax
0x10080d4f2  mov     r8, [rax]
0x10080d4f5  lea     rdx, [rsp+150h+var_120]
0x10080d4fa  mov     rcx, rax
0x10080d4fd  call    qword ptr [r8+98h]
0x10080d504  test    eax, eax
0x10080d506  jz      short loc_10080D51E
0x10080d508  mov     edx, 2
0x10080d50d  lea     ecx, [rdx+45h]
0x10080d510  lea     r9d, [rdx+61h]
0x10080d514  lea     r8d, [rdx+12h]
0x10080d518  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10080d51e  mov     eax, 800h
0x10080d523  test    [rsp+150h+var_120], 1
0x10080d528  jnz     short loc_10080D58A
0x10080d52a  mov     [r12+rdi*8], rbx
0x10080d52e  mov     dword ptr [rbp+50h+arg_10], r14d
0x10080d532  cmp     [rsp+150h+var_108], ax
0x10080d537  jb      short loc_10080D54E
0x10080d539  mov     edx, 10h
0x10080d53e  lea     ecx, [rdx+52h]
0x10080d541  lea     r9d, [rdx-0Fh]
0x10080d545  mov     r8d, edx
0x10080d548  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10080d54e  lea     rdx, [rbp+50h+arg_10]
0x10080d552  lea     rcx, [rsp+150h+var_F8]
0x10080d557  call    ?UlAdd@?$CTDynArray@KV?$CFnI_Default@K@@V?$CFnD_Noop@K@@V?$CMemObjAlloc@$0A@@@@@QEAAKAEBK@Z; CTDynArray<ulong,CFnI_Default<ulong>,CFnD_Noop<ulong>,CMemObjAlloc<0>>::UlAdd(ulong const &)
0x10080d55c  mov     [rbp+50h+arg_10], rbx
0x10080d560  lea     rdx, [rbp+50h+arg_10]
0x10080d564  lea     rcx, [rsp+150h+var_D8]
0x10080d569  call    ?UlAdd@?$CTDynArray@PEAUApproxCountDistinctHashValueItem@@V?$CFnI_Default@PEAUApproxCountDistinctHashValueItem@@@@V?$CFnD_Ptr@UApproxCountDistinctHashValueItem@@@@V?$CMemObjAlloc@$0A@@@@@QEAAKAEBQEAUApproxCountDistinctHashValueItem@@@Z; CTDynArray<ApproxCountDistinctHashValueItem *,CFnI_Default<ApproxCountDistinctHashValueItem *>,CFnD_Ptr<ApproxCountDistinctHashValueItem>,CMemObjAlloc<0>>::UlAdd(ApproxCountDistinctHashValueItem * const &)
0x10080d56e  lea     rdx, ?x_usLobIndicator@CRESparseVector@@2GB; ushort const CRESparseVector::x_usLobIndicator
0x10080d575  lea     rcx, [rbp+50h+var_B8]
0x10080d579  call    ?UlAdd@?$CTDynArray@GV?$CFnI_Default@G@@V?$CFnD_Noop@G@@V?$CMemObjAlloc@$0A@@@@@QEAAKAEBG@Z; CTDynArray<ushort,CFnI_Default<ushort>,CFnD_Noop<ushort>,CMemObjAlloc<0>>::UlAdd(ushort const &)
0x10080d57e  movzx   edx, [rsp+150h+var_108]
0x10080d583  inc     dx
0x10080d586  xor     ebx, ebx
0x10080d588  jmp     short loc_10080D5E4
0x10080d58a  cmp     [rsp+150h+var_108], ax
0x10080d58f  mov     dword ptr [rbp+50h+arg_10], r14d
0x10080d593  jb      short loc_10080D5AA
0x10080d595  mov     edx, 10h
0x10080d59a  lea     r9d, [rdx-0Fh]
0x10080d59e  mov     r8d, edx
0x10080d5a1  lea     ecx, [rdx+52h]
0x10080d5a4  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10080d5aa  lea     rdx, [rbp+50h+arg_10]
0x10080d5ae  lea     rcx, [rsp+150h+var_F8]
0x10080d5b3  call    ?UlAdd@?$CTDynArray@KV?$CFnI_Default@K@@V?$CFnD_Noop@K@@V?$CMemObjAlloc@$0A@@@@@QEAAKAEBK@Z; CTDynArray<ulong,CFnI_Default<ulong>,CFnD_Noop<ulong>,CMemObjAlloc<0>>::UlAdd(ulong const &)
0x10080d5b8  xor     ebx, ebx
0x10080d5ba  mov     [rbp+50h+arg_10], rbx
0x10080d5be  lea     rdx, [rbp+50h+arg_10]
0x10080d5c2  lea     rcx, [rsp+150h+var_D8]
0x10080d5c7  call    ?UlAdd@?$CTDynArray@PEAUApproxCountDistinctHashValueItem@@V?$CFnI_Default@PEAUApproxCountDistinctHashValueItem@@@@V?$CFnD_Ptr@UApproxCountDistinctHashValueItem@@@@V?$CMemObjAlloc@$0A@@@@@QEAAKAEBQEAUApproxCountDistinctHashValueItem@@@Z; CTDynArray<ApproxCountDistinctHashValueItem *,CFnI_Default<ApproxCountDistinctHashValueItem *>,CFnD_Ptr<ApproxCountDistinctHashValueItem>,CMemObjAlloc<0>>::UlAdd(ApproxCountDistinctHashValueItem * const &)
0x10080d5cc  lea     rdx, ?x_usNullIndicator@CRESparseVector@@2GB; ushort const CRESparseVector::x_usNullIndicator
0x10080d5d3  lea     rcx, [rbp+50h+var_B8]
0x10080d5d7  call    ?UlAdd@?$CTDynArray@GV?$CFnI_Default@G@@V?$CFnD_Noop@G@@V?$CMemObjAlloc@$0A@@@@@QEAAKAEBG@Z; CTDynArray<ushort,CFnI_Default<ushort>,CFnD_Noop<ushort>,CMemObjAlloc<0>>::UlAdd(ushort const &)
0x10080d5dc  movzx   edx, [rsp+150h+var_108]
0x10080d5e1  inc     dx
0x10080d5e4  mov     [rsp+150h+var_108], dx
0x10080d5e9  inc     r13d
0x10080d5ec  inc     rdi
0x10080d5ef  mov     [rbp+50h+var_90], rdi
0x10080d5f3  add     r15, 40h ; '@'
0x10080d5f7  cmp     rdi, [rbp+50h+var_80]
0x10080d5fb  mov     r12, [rbp+50h+var_78]
0x10080d5ff  lea     r9, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x10080d606  mov     r10d, 800h
0x10080d60c  mov     r11d, 0FFFFh
0x10080d612  jl      loc_10080D380
0x10080d618  mov     r13, [rbp+50h+var_68]
0x10080d61c  mov     r14, [rbp+50h+arg_8]
0x10080d620  mov     edi, [rsp+150h+var_11C]
0x10080d624  mov     r15, [rbp+50h+var_60]
0x10080d628  lea     rcx, [rsp+150h+var_110]; this
0x10080d62d  call    ?Write@CRESparseVectorWriter@@QEAAXXZ; CRESparseVectorWriter::Write(void)
0x10080d632  mov     rax, [rbp+50h+var_58]
0x10080d636  mov     [r14+8], rax
0x10080d63a  mov     eax, [rbp+50h+arg_18]
0x10080d63d  mov     [r14+10h], rax
0x10080d641  mov     byte ptr [r14], 0
0x10080d645  lea     rax, [rbp+50h+var_B8]
0x10080d649  mov     [rbp+50h+arg_0], rax
0x10080d64d  mov     [rbp+50h+var_AC], ebx
0x10080d650  mov     rcx, [rbp+50h+var_A0]
0x10080d654  test    rcx, rcx
0x10080d657  jz      short loc_10080D663
0x10080d659  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10080d65f  mov     [rbp+50h+var_A0], rbx
0x10080d663  mov     [rbp+50h+var_A8], ebx
0x10080d666  lea     rax, [rsp+150h+var_D8]
0x10080d66b  mov     [rbp+50h+arg_0], rax
0x10080d66f  mov     [rbp+50h+var_CC], ebx
0x10080d672  mov     rcx, [rbp+50h+var_C0]
0x10080d676  test    rcx, rcx
0x10080d679  jz      short loc_10080D685
0x10080d67b  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10080d681  mov     [rbp+50h+var_C0], rbx
0x10080d685  mov     [rbp+50h+var_C8], ebx
0x10080d688  lea     rax, [rsp+150h+var_F8]
  ... truncated ...
```
