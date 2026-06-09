# CWMFileSinkV1::WriteOutIndexObjects(void)

- ea: `0x18000c2a0`
- end: `0x18000c90d`
- name: `?WriteOutIndexObjects@CWMFileSinkV1@@MEAAJXZ`
- size: `1645`
- prototype: `__int64 __fastcall(CWMFileSinkV1 *__hidden this)`
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x180001194`
- `0x1800011ec`
- `0x1800015f0`
- `0x18000c2a0`
- `0x180012ff4`
- `0x180015e80`
- `0x18001e790`
- `0x18001fbac`
- `0x180024a54`
- `0x180027984`
- `0x180027a24`
- `0x180028220`
- `0x180028cf0`
- `0x180028e60`
- `0x180029060`
- `0x1800290a0`
- `0x180029170`
- `0x18002a064`
- `0x18002b010`

## import_xrefs

- `KERNEL32!SetFilePointer` at `0x18000c378`
- `KERNEL32!SetFilePointer` at `0x18000c378`
- `KERNEL32!WriteFile` at `0x18000c662`
- `KERNEL32!WriteFile` at `0x18000c886`
- `KERNEL32!WriteFile` at `0x18000c662`
- `KERNEL32!WriteFile` at `0x18000c886`

## pseudocode

```c
__int64 __fastcall CWMFileSinkV1::WriteOutIndexObjects(CWMFileSinkV1 *this)
{
  __int64 result; // rax
  int v3; // edi
  unsigned __int16 i; // si
  __int64 v5; // rcx
  char *v6; // r14
  char *v7; // r12
  __int64 v8; // rsi
  __int64 v9; // r15
  void *v10; // rcx
  int v11; // eax
  unsigned __int64 v12; // rdx
  __int16 v13; // cx
  unsigned __int16 v14; // si
  __int64 v15; // r8
  __int64 v16; // rcx
  unsigned int v17; // ecx
  __int64 v18; // rcx
  __int64 v19; // r8
  unsigned __int16 v20; // dx
  unsigned __int16 v21; // si
  __int64 v22; // rcx
  unsigned __int16 v23; // ax
  __int64 v24; // rcx
  unsigned int v25; // esi
  __int64 v26; // rcx
  unsigned __int16 v27; // si
  __int64 v28; // rcx
  unsigned __int64 v29; // rdi
  __int64 v30; // rax
  void *v31; // rcx
  __int64 v32; // rsi
  int NextObject; // eax
  __int64 v34; // rcx
  __int64 *v35; // rcx
  __int64 v36; // rax
  __int64 v37; // r8
  __int64 v38; // rax
  __int64 v39; // rcx
  GUID v40; // xmm0
  unsigned __int64 v41; // rsi
  __int64 v42; // rax
  unsigned int v43; // [rsp+30h] [rbp-D0h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+34h] [rbp-CCh] BYREF
  __int128 Buf2; // [rsp+38h] [rbp-C8h] BYREF
  char *v46; // [rsp+48h] [rbp-B8h]
  int v47; // [rsp+50h] [rbp-B0h]
  int v48; // [rsp+54h] [rbp-ACh]
  LONG DistanceToMoveHigh; // [rsp+58h] [rbp-A8h] BYREF
  void *j; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v51[3]; // [rsp+68h] [rbp-98h] BYREF
  int v52; // [rsp+80h] [rbp-80h]
  int v53; // [rsp+84h] [rbp-7Ch]
  _QWORD v54[7]; // [rsp+90h] [rbp-70h] BYREF
  int v55; // [rsp+C8h] [rbp-38h]
  _QWORD v56[2]; // [rsp+F0h] [rbp-10h] BYREF
  GUID v57; // [rsp+100h] [rbp+0h]
  __int64 v58; // [rsp+118h] [rbp+18h]
  __int64 v59; // [rsp+120h] [rbp+20h]
  GUID v60; // [rsp+128h] [rbp+28h]
  __int64 v61; // [rsp+138h] [rbp+38h]
  __int64 v62; // [rsp+140h] [rbp+40h]
  __int64 v63; // [rsp+148h] [rbp+48h]

  if ( *((_DWORD *)this + 2102) && *((_WORD *)this + 4196) )
  {
    if ( *((_QWORD *)this + 40) )
      return 2147549183LL;
    v3 = 0;
    for ( i = 0; i < *((_WORD *)this + 4196); ++i )
    {
      v5 = *((_QWORD *)this + i + 985);
      result = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v5 + 48LL))(
                 v5,
                 10000LL * *((_QWORD *)this + 920));
      v3 = result;
      if ( (int)result < 0 )
        return result;
    }
    v6 = 0;
    v7 = 0;
    if ( *((_DWORD *)this + 9) )
    {
      v8 = *((_QWORD *)this + 1158);
      v9 = -1;
      DistanceToMoveHigh = 0;
      if ( *(_DWORD *)(v8 + 64) )
      {
        v10 = *(void **)(v8 + 24);
        if ( v10 != (void *)-1LL )
          SetFilePointer(v10, 0, &DistanceToMoveHigh, 2u);
        v9 = *(_QWORD *)(v8 + 24);
      }
    }
    else
    {
      v9 = *((_QWORD *)this + 24);
    }
    v11 = (*(__int64 (__fastcall **)(CWMFileSinkV1 *))(*(_QWORD *)this + 288LL))(this);
    v13 = *((_WORD *)this + 4196);
    if ( v11 )
    {
      v14 = 0;
      if ( v13 )
      {
        while ( 1 )
        {
          v15 = *((_QWORD *)this + 30);
          v43 = 0;
          v16 = *((_QWORD *)this + v14 + 985);
          v3 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, unsigned int *))(*(_QWORD *)v16 + 80LL))(
                 v16,
                 v9,
                 v15,
                 &v43);
          if ( v3 < 0 )
            return (unsigned int)v3;
          v17 = v43;
          *((_QWORD *)this + 40) += v43;
          if ( v17 )
            *((_DWORD *)this + 82) = 1;
          if ( ++v14 >= *((_WORD *)this + 4196) )
            goto LABEL_21;
        }
      }
      if ( v3 >= 0 )
      {
LABEL_21:
        v18 = *((_QWORD *)this + 1052);
        if ( v18 )
        {
          v19 = *((_QWORD *)this + 30);
          LODWORD(Buf2) = 0;
          v3 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int128 *))(*(_QWORD *)v18 + 48LL))(
                 v18,
                 v9,
                 v19,
                 &Buf2);
          if ( v3 < 0 )
            goto LABEL_25;
          *((_QWORD *)this + 40) += (unsigned int)Buf2;
        }
        *((_QWORD *)this + 33) += *((_QWORD *)this + 40);
LABEL_25:
        if ( !v6 )
          goto LABEL_27;
        goto LABEL_26;
      }
      return (unsigned int)v3;
    }
    if ( !v13 )
      goto LABEL_21;
    CASFIndexObjectEx::CASFIndexObjectEx((CASFIndexObjectEx *)v54);
    v20 = *((_WORD *)this + 4196);
    v55 = 1000;
    v3 = CASFBaseIndexObjectEx::SetSpecifierCount((CASFBaseIndexObjectEx *)v54, v20);
    if ( v3 < 0 )
    {
LABEL_34:
      v54[0] = &CASFIndexObjectEx::`vftable';
      CASFBaseIndexObjectEx::~CASFBaseIndexObjectEx((CASFBaseIndexObjectEx *)v54);
      return (unsigned int)v3;
    }
    v21 = 0;
    if ( *((_WORD *)this + 4196) )
    {
      do
      {
        v22 = *((_QWORD *)this + v21 + 985);
        v23 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v22 + 24LL))(v22);
        v3 = CASFBaseIndexObjectEx::SetSpecifier((CASFBaseIndexObjectEx *)v54, v21, v23, 3u);
        if ( v3 < 0 )
          goto LABEL_34;
      }
      while ( ++v21 < *((_WORD *)this + 4196) );
    }
    v24 = *((_QWORD *)this + 985);
    v43 = 0;
    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v24 + 56LL))(v24, &v43);
    if ( !v43 )
    {
      v3 = -2147418113;
      goto LABEL_34;
    }
    CASFBaseIndexObjectEx::SetBlockCount((CASFBaseIndexObjectEx *)v54, v43);
    v25 = 0;
    if ( v43 )
    {
      do
      {
        v26 = *((_QWORD *)this + 985);
        LODWORD(Buf2) = 0;
        v3 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *))(*(_QWORD *)v26 + 64LL))(v26, v25, &Buf2);
        if ( v3 < 0 )
          goto LABEL_34;
        v3 = CASFBaseIndexObjectEx::SetBlock((CASFBaseIndexObjectEx *)v54, v25, Buf2);
        if ( v3 < 0 )
          goto LABEL_34;
      }
      while ( ++v25 < v43 );
    }
    v27 = 0;
    if ( *((_WORD *)this + 4196) )
    {
      do
      {
        v28 = *((_QWORD *)this + v27 + 985);
        v3 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD *))(*(_QWORD *)v28 + 72LL))(v28, v27, v54);
        if ( v3 < 0 )
          goto LABEL_34;
      }
      while ( ++v27 < *((_WORD *)this + 4196) );
    }
    v29 = CASFBaseIndexObjectEx::Space((CASFBaseIndexObjectEx *)v54);
    v6 = (char *)operator new[](v29);
    if ( !v6 )
    {
      v3 = -2147024882;
      goto LABEL_34;
    }
    v53 = *(_DWORD *)(*((_QWORD *)this + 30) + 664LL);
    v51[2] = &v6[v29];
    v51[0] = v6;
    v51[1] = v6;
    v52 = 1;
    CASFBaseIndexObjectEx::Persist((CASFBaseIndexObjectEx *)v54, (struct CASFArchive *)v51);
    NumberOfBytesWritten = 0;
    if ( !WriteFile((HANDLE)v9, v6, v29, &NumberOfBytesWritten, 0) || NumberOfBytesWritten < (unsigned int)v29 )
    {
      v3 = -2147467259;
      goto LABEL_77;
    }
    *((_QWORD *)this + 40) = NumberOfBytesWritten;
    v30 = *((_QWORD *)this + 30);
    *((_DWORD *)this + 83) = 1;
    v31 = *(void **)(v30 + 592);
    for ( j = v31; ; v31 = j )
    {
      *(_QWORD *)&Buf2 = 0;
      v32 = 0;
      v3 = 0;
      if ( !v31 )
        break;
      NextObject = CASFMMStream::GetNextObject((CASFMMStream *)v31, (struct CASFLonghandObject **)&Buf2, &j);
      v32 = Buf2;
      if ( NextObject < 0 )
        break;
      Buf2 = *(_OWORD *)(Buf2 + 16);
      if ( !memcmp_0(&CLSID_CAsfStreamPropertiesObjectV1, &Buf2, 0x10u) )
      {
        Buf2 = *(_OWORD *)(v32 + 56);
        if ( !memcmp_0(&Buf2, &CLSID_AsfXStreamTypeIcmVideo, 0x10u) )
        {
          v34 = *(unsigned __int16 *)(v32 + 104);
          if ( (unsigned __int16)(v34 - 1) > 0x3Eu )
          {
            v3 = -2147418113;
            break;
          }
          _mm_lfence();
          v35 = (__int64 *)*((_QWORD *)this + v34 + 921);
          if ( v35 )
          {
            v36 = *v35;
            v37 = *((_QWORD *)this + 30);
            LODWORD(Buf2) = 0;
            if ( (*(int (__fastcall **)(__int64 *, __int64, __int64, __int128 *))(v36 + 80))(v35, v9, v37, &Buf2) >= 0 )
            {
              *((_QWORD *)this + 40) += (unsigned int)Buf2;
              *((_DWORD *)this + 82) = 1;
            }
          }
        }
      }
      CASFLonghandObject::Release((CASFLonghandObject *)v32);
    }
    if ( v32 )
      CASFLonghandObject::Release((CASFLonghandObject *)v32);
    if ( !*((_DWORD *)this + 82) )
    {
      v58 = 0;
      v56[0] = &CASFIndexObject::`vftable';
      v38 = *((_QWORD *)this + 30);
      v59 = 1;
      v57 = CLSID_CAsfIndexObjectV2;
      v56[1] = 108;
      v63 = 0;
      v62 = 0;
      v39 = *(_QWORD *)(v38 + 616);
      if ( v39 )
        v40 = *(GUID *)(v39 + 72);
      else
        v40 = GUID_NULL;
      v61 = 0;
      v60 = v40;
      CASFIndexObject::SetEntryCount((CASFIndexObject *)v56, 0);
      v41 = (unsigned int)(6 * v62 + 56);
      v7 = (char *)operator new[](v41);
      if ( !v7 )
      {
        v3 = -2147024882;
LABEL_70:
        CASFIndexObject::~CASFIndexObject((CASFIndexObject *)v56);
LABEL_77:
        v54[0] = &CASFIndexObjectEx::`vftable';
        CASFBaseIndexObjectEx::~CASFBaseIndexObjectEx((CASFBaseIndexObjectEx *)v54);
LABEL_26:
        operator delete(v6, v12);
LABEL_27:
        if ( v7 )
          operator delete(v7, v12);
        return (unsigned int)v3;
      }
      v42 = *((_QWORD *)this + 30);
      *(_QWORD *)&Buf2 = v7;
      *((_QWORD *)&Buf2 + 1) = v7;
      v47 = 1;
      v48 = *(_DWORD *)(v42 + 664);
      v46 = &v7[v41];
      v3 = CASFIndexObject::Persist((CASFIndexObject *)v56, (struct CASFArchive *)&Buf2);
      if ( !WriteFile((HANDLE)v9, v7, v41, &NumberOfBytesWritten, 0) || NumberOfBytesWritten < (unsigned int)v41 )
      {
        v3 = -2147467259;
        goto LABEL_70;
      }
      *((_QWORD *)this + 40) += NumberOfBytesWritten;
      CASFIndexObject::~CASFIndexObject((CASFIndexObject *)v56);
    }
    v54[0] = &CASFIndexObjectEx::`vftable';
    CASFBaseIndexObjectEx::~CASFBaseIndexObjectEx((CASFBaseIndexObjectEx *)v54);
    goto LABEL_21;
  }
  return 0;
}

```

## disassembly

```asm
0x18000c2a0  push    rbp
0x18000c2a2  push    rbx
0x18000c2a3  push    rsi
0x18000c2a4  push    rdi
0x18000c2a5  push    r12
0x18000c2a7  push    r13
0x18000c2a9  push    r14
0x18000c2ab  push    r15
0x18000c2ad  lea     rbp, [rsp-68h]
0x18000c2b2  sub     rsp, 168h
0x18000c2b9  mov     rax, cs:__security_cookie
0x18000c2c0  xor     rax, rsp
0x18000c2c3  mov     [rbp+0A0h+var_50], rax
0x18000c2c7  xor     r13d, r13d
0x18000c2ca  mov     rbx, rcx
0x18000c2cd  cmp     [rcx+20D8h], r13d
0x18000c2d4  jz      loc_18000C8EB
0x18000c2da  cmp     r13w, [rcx+20C8h]
0x18000c2e2  jz      loc_18000C8EB
0x18000c2e8  cmp     [rcx+140h], r13
0x18000c2ef  jbe     short loc_18000C2FB
0x18000c2f1  mov     eax, 8000FFFFh
0x18000c2f6  jmp     loc_18000C8ED
0x18000c2fb  mov     edi, r13d
0x18000c2fe  mov     esi, r13d
0x18000c301  mov     r14d, 1
0x18000c307  cmp     si, [rbx+20C8h]
0x18000c30e  jnb     short loc_18000C342
0x18000c310  imul    rdx, [rbx+1CC0h], 2710h
0x18000c31b  movzx   eax, si
0x18000c31e  mov     rcx, [rbx+rax*8+1EC8h]
0x18000c326  mov     rax, [rcx]
0x18000c329  mov     rax, [rax+30h]
0x18000c32d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c332  mov     edi, eax
0x18000c334  test    eax, eax
0x18000c336  js      loc_18000C8ED
0x18000c33c  add     si, r14w
0x18000c340  jmp     short loc_18000C307
0x18000c342  mov     r14, r13
0x18000c345  mov     r12, r13
0x18000c348  cmp     [rbx+24h], r13d
0x18000c34c  jz      short loc_18000C384
0x18000c34e  mov     rsi, [rbx+2430h]
0x18000c355  or      r15, 0FFFFFFFFFFFFFFFFh
0x18000c359  mov     [rsp+1A0h+DistanceToMoveHigh], r13d
0x18000c35e  cmp     [rsi+40h], r13d
0x18000c362  jz      short loc_18000C38B
0x18000c364  mov     rcx, [rsi+18h]; hFile
0x18000c368  cmp     rcx, r15
0x18000c36b  jz      short loc_18000C37E
0x18000c36d  lea     r9d, [r15+3]; dwMoveMethod
0x18000c371  xor     edx, edx; lDistanceToMove
0x18000c373  lea     r8, [rsp+1A0h+DistanceToMoveHigh]; lpDistanceToMoveHigh
0x18000c378  call    cs:__imp_SetFilePointer
0x18000c37e  mov     r15, [rsi+18h]
0x18000c382  jmp     short loc_18000C38B
0x18000c384  mov     r15, [rbx+0C0h]
0x18000c38b  mov     rax, [rbx]
0x18000c38e  mov     rcx, rbx
0x18000c391  mov     rax, [rax+120h]
0x18000c398  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c39d  movzx   ecx, word ptr [rbx+20C8h]
0x18000c3a4  test    eax, eax
0x18000c3a6  jz      loc_18000C486
0x18000c3ac  mov     esi, r13d
0x18000c3af  cmp     r13w, cx
0x18000c3b3  jnb     loc_18000C480
0x18000c3b9  mov     r8, [rbx+0F0h]
0x18000c3c0  lea     r9, [rsp+1A0h+var_170]
0x18000c3c5  movzx   eax, si
0x18000c3c8  mov     rdx, r15
0x18000c3cb  mov     [rsp+1A0h+var_170], r13d
0x18000c3d0  mov     rcx, [rbx+rax*8+1EC8h]
0x18000c3d8  mov     rax, [rcx]
0x18000c3db  mov     rax, [rax+50h]
0x18000c3df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3e4  mov     edi, eax
0x18000c3e6  test    eax, eax
0x18000c3e8  js      loc_18000C479
0x18000c3ee  mov     ecx, [rsp+1A0h+var_170]
0x18000c3f2  mov     eax, 1
0x18000c3f7  add     [rbx+140h], rcx
0x18000c3fe  test    ecx, ecx
0x18000c400  jz      short loc_18000C408
0x18000c402  mov     [rbx+148h], eax
0x18000c408  add     si, ax
0x18000c40b  cmp     si, [rbx+20C8h]
0x18000c412  jb      short loc_18000C3B9
0x18000c414  mov     rcx, [rbx+20E0h]
0x18000c41b  test    rcx, rcx
0x18000c41e  jz      short loc_18000C451
0x18000c420  mov     r8, [rbx+0F0h]
0x18000c427  lea     r9, [rsp+1A0h+Buf2]
0x18000c42c  mov     dword ptr [rsp+1A0h+Buf2], r13d
0x18000c431  mov     rdx, r15
0x18000c434  mov     rax, [rcx]
0x18000c437  mov     rax, [rax+30h]
0x18000c43b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c440  mov     edi, eax
0x18000c442  test    eax, eax
0x18000c444  js      short loc_18000C45F
0x18000c446  mov     eax, dword ptr [rsp+1A0h+Buf2]
0x18000c44a  add     [rbx+140h], rax
0x18000c451  mov     rax, [rbx+140h]
0x18000c458  add     [rbx+108h], rax
0x18000c45f  test    r14, r14
0x18000c462  jz      short loc_18000C46C
0x18000c464  mov     rcx, r14; void *
0x18000c467  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c46c  test    r12, r12
0x18000c46f  jz      short loc_18000C479
0x18000c471  mov     rcx, r12; void *
0x18000c474  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c479  mov     eax, edi
0x18000c47b  jmp     loc_18000C8ED
0x18000c480  test    edi, edi
0x18000c482  js      short loc_18000C479
0x18000c484  jmp     short loc_18000C414
0x18000c486  test    cx, cx
0x18000c489  jz      short loc_18000C414
0x18000c48b  lea     rcx, [rbp+0A0h+var_110]; this
0x18000c48f  call    ??0CASFIndexObjectEx@@QEAA@XZ; CASFIndexObjectEx::CASFIndexObjectEx(void)
0x18000c494  movzx   edx, word ptr [rbx+20C8h]; unsigned __int16
0x18000c49b  lea     rcx, [rbp+0A0h+var_110]; this
0x18000c49f  mov     [rbp+0A0h+var_D8], 3E8h
0x18000c4a6  call    ?SetSpecifierCount@CASFBaseIndexObjectEx@@UEAAJG@Z; CASFBaseIndexObjectEx::SetSpecifierCount(ushort)
0x18000c4ab  mov     edi, eax
0x18000c4ad  test    eax, eax
0x18000c4af  jns     short loc_18000C4C7
0x18000c4b1  lea     rcx, [rbp+0A0h+var_110]; this
0x18000c4b5  lea     rax, ??_7CASFIndexObjectEx@@6B@; const CASFIndexObjectEx::`vftable'
0x18000c4bc  mov     [rbp+0A0h+var_110], rax
0x18000c4c0  call    ??1CASFBaseIndexObjectEx@@UEAA@XZ; CASFBaseIndexObjectEx::~CASFBaseIndexObjectEx(void)
0x18000c4c5  jmp     short loc_18000C479
0x18000c4c7  mov     esi, r13d
0x18000c4ca  mov     r14d, 1
0x18000c4d0  cmp     r13w, [rbx+20C8h]
0x18000c4d8  jnb     short loc_18000C51D
0x18000c4da  movzx   eax, si
0x18000c4dd  mov     edi, 3
0x18000c4e2  mov     rcx, [rbx+rax*8+1EC8h]
0x18000c4ea  mov     rax, [rcx]
0x18000c4ed  mov     rax, [rax+18h]
0x18000c4f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c4f6  movzx   r8d, ax; unsigned __int16
0x18000c4fa  lea     rcx, [rbp+0A0h+var_110]; this
0x18000c4fe  movzx   r9d, di; unsigned __int16
0x18000c502  movzx   edx, si; unsigned __int16
0x18000c505  call    ?SetSpecifier@CASFBaseIndexObjectEx@@UEAAJGGG@Z; CASFBaseIndexObjectEx::SetSpecifier(ushort,ushort,ushort)
0x18000c50a  mov     edi, eax
0x18000c50c  test    eax, eax
0x18000c50e  js      short loc_18000C4B1
0x18000c510  add     si, r14w
0x18000c514  cmp     si, [rbx+20C8h]
0x18000c51b  jb      short loc_18000C4DA
0x18000c51d  mov     rcx, [rbx+1EC8h]
0x18000c524  lea     rdx, [rsp+1A0h+var_170]
0x18000c529  mov     [rsp+1A0h+var_170], r13d
0x18000c52e  mov     rax, [rcx]
0x18000c531  mov     rax, [rax+38h]
0x18000c535  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c53a  mov     edx, [rsp+1A0h+var_170]; unsigned int
0x18000c53e  lea     rcx, [rbp+0A0h+var_110]; this
0x18000c542  test    edx, edx
0x18000c544  jnz     short loc_18000C550
0x18000c546  mov     edi, 8000FFFFh
0x18000c54b  jmp     loc_18000C4B5
0x18000c550  call    ?SetBlockCount@CASFBaseIndexObjectEx@@UEAAJK@Z; CASFBaseIndexObjectEx::SetBlockCount(ulong)
0x18000c555  mov     esi, r13d
0x18000c558  cmp     [rsp+1A0h+var_170], r13d
0x18000c55d  jbe     short loc_18000C5AB
0x18000c55f  mov     rcx, [rbx+1EC8h]
0x18000c566  lea     r8, [rsp+1A0h+Buf2]
0x18000c56b  mov     dword ptr [rsp+1A0h+Buf2], r13d
0x18000c570  mov     edx, esi
0x18000c572  mov     rax, [rcx]
0x18000c575  mov     rax, [rax+40h]
0x18000c579  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c57e  mov     edi, eax
0x18000c580  test    eax, eax
0x18000c582  js      loc_18000C4B1
0x18000c588  mov     r8d, dword ptr [rsp+1A0h+Buf2]; unsigned int
0x18000c58d  lea     rcx, [rbp+0A0h+var_110]; this
0x18000c591  mov     edx, esi; unsigned int
0x18000c593  call    ?SetBlock@CASFBaseIndexObjectEx@@UEAAJKK@Z; CASFBaseIndexObjectEx::SetBlock(ulong,ulong)
0x18000c598  mov     edi, eax
0x18000c59a  test    eax, eax
0x18000c59c  js      loc_18000C4B1
0x18000c5a2  add     esi, r14d
0x18000c5a5  cmp     esi, [rsp+1A0h+var_170]
0x18000c5a9  jb      short loc_18000C55F
0x18000c5ab  mov     esi, r13d
0x18000c5ae  cmp     r13w, [rbx+20C8h]
0x18000c5b6  jnb     short loc_18000C5ED
0x18000c5b8  movzx   eax, si
0x18000c5bb  lea     r8, [rbp+0A0h+var_110]
0x18000c5bf  movzx   edx, si
0x18000c5c2  mov     rcx, [rbx+rax*8+1EC8h]
0x18000c5ca  mov     rax, [rcx]
0x18000c5cd  mov     rax, [rax+48h]
0x18000c5d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c5d6  mov     edi, eax
0x18000c5d8  test    eax, eax
0x18000c5da  js      loc_18000C4B1
0x18000c5e0  add     si, r14w
0x18000c5e4  cmp     si, [rbx+20C8h]
0x18000c5eb  jb      short loc_18000C5B8
0x18000c5ed  lea     rcx, [rbp+0A0h+var_110]; this
0x18000c5f1  call    ?Space@CASFBaseIndexObjectEx@@UEAAKXZ; CASFBaseIndexObjectEx::Space(void)
0x18000c5f6  mov     ecx, eax; unsigned __int64
0x18000c5f8  mov     edi, eax
0x18000c5fa  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000c5ff  mov     r14, rax
0x18000c602  test    rax, rax
0x18000c605  jnz     short loc_18000C611
0x18000c607  mov     edi, 8007000Eh
0x18000c60c  jmp     loc_18000C4B1
0x18000c611  mov     rax, [rbx+0F0h]
0x18000c618  lea     rdx, [rsp+1A0h+var_138]; struct CASFArchive *
0x18000c61d  mov     esi, 1
0x18000c622  mov     ecx, [rax+298h]
0x18000c628  lea     rax, [rdi+r14]
0x18000c62c  mov     [rbp+0A0h+var_11C], ecx
0x18000c62f  lea     rcx, [rbp+0A0h+var_110]; this
0x18000c633  mov     [rsp+1A0h+var_128], rax
0x18000c638  mov     [rsp+1A0h+var_138], r14
0x18000c63d  mov     [rsp+1A0h+var_130], r14
0x18000c642  mov     [rbp+0A0h+var_120], esi
0x18000c645  call    ?Persist@CASFBaseIndexObjectEx@@UEAAJAEAVCASFArchive@@@Z; CASFBaseIndexObjectEx::Persist(CASFArchive &)
0x18000c64a  lea     r9, [rsp+1A0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000c64f  mov     [rsp+1A0h+NumberOfBytesWritten], r13d
0x18000c654  mov     r8d, edi; nNumberOfBytesToWrite
0x18000c657  mov     [rsp+1A0h+lpOverlapped], r13; lpOverlapped
0x18000c65c  mov     rdx, r14; lpBuffer
0x18000c65f  mov     rcx, r15; hFile
0x18000c662  call    cs:__imp_WriteFile
0x18000c668  test    eax, eax
0x18000c66a  jz      loc_18000C8CD
0x18000c670  cmp     [rsp+1A0h+NumberOfBytesWritten], edi
0x18000c674  jb      loc_18000C8CD
0x18000c67a  mov     eax, [rsp+1A0h+NumberOfBytesWritten]
0x18000c67e  mov     [rbx+140h], rax
0x18000c685  mov     rax, [rbx+0F0h]
0x18000c68c  mov     [rbx+14Ch], esi
0x18000c692  mov     rcx, [rax+250h]; this
0x18000c699  mov     [rsp+1A0h+var_140], rcx
0x18000c69e  mov     qword ptr [rsp+1A0h+Buf2], r13
0x18000c6a3  mov     rsi, r13
0x18000c6a6  mov     edi, r13d
0x18000c6a9  test    rcx, rcx
0x18000c6ac  jz      loc_18000C787
0x18000c6b2  lea     r8, [rsp+1A0h+var_140]; void **
0x18000c6b7  lea     rdx, [rsp+1A0h+Buf2]; struct CASFLonghandObject **
0x18000c6bc  call    ?GetNextObject@CASFMMStream@@QEAAJPEAPEAVCASFLonghandObject@@AEAPEAX@Z; CASFMMStream::GetNextObject(CASFLonghandObject * *,void * &)
0x18000c6c1  mov     rsi, qword ptr [rsp+1A0h+Buf2]
0x18000c6c6  test    eax, eax
0x18000c6c8  js      loc_18000C787
0x18000c6ce  movups  xmm0, xmmword ptr [rsi+10h]
0x18000c6d2  mov     r8d, 10h; Size
0x18000c6d8  lea     rdx, [rsp+1A0h+Buf2]; Buf2
0x18000c6dd  lea     rcx, CLSID_CAsfStreamPropertiesObjectV1; Buf1
0x18000c6e4  movdqu  [rsp+1A0h+Buf2], xmm0
0x18000c6ea  call    memcmp_0
0x18000c6ef  test    eax, eax
0x18000c6f1  jnz     short loc_18000C770
0x18000c6f3  movups  xmm0, xmmword ptr [rsi+38h]
0x18000c6f7  lea     r8d, [rax+10h]; Size
0x18000c6fb  lea     rdx, CLSID_AsfXStreamTypeIcmVideo; Buf2
0x18000c702  lea     rcx, [rsp+1A0h+Buf2]; Buf1
0x18000c707  movdqu  [rsp+1A0h+Buf2], xmm0
0x18000c70d  call    memcmp_0
0x18000c712  test    eax, eax
0x18000c714  jnz     short loc_18000C770
0x18000c716  movzx   ecx, word ptr [rsi+68h]
0x18000c71a  mov     edi, 1
0x18000c71f  movzx   eax, cx
0x18000c722  sub     ax, di
0x18000c725  cmp     ax, 3Eh ; '>'
0x18000c729  ja      short loc_18000C782
0x18000c72b  lfence
0x18000c72e  mov     rcx, [rbx+rcx*8+1CC8h]
0x18000c736  test    rcx, rcx
0x18000c739  jz      short loc_18000C770
0x18000c73b  mov     rax, [rcx]
0x18000c73e  lea     r9, [rsp+1A0h+Buf2]
0x18000c743  mov     r8, [rbx+0F0h]
0x18000c74a  mov     rdx, r15
0x18000c74d  mov     dword ptr [rsp+1A0h+Buf2], r13d
0x18000c752  mov     rax, [rax+50h]
0x18000c756  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c75b  test    eax, eax
0x18000c75d  js      short loc_18000C770
0x18000c75f  mov     eax, dword ptr [rsp+1A0h+Buf2]
0x18000c763  add     [rbx+140h], rax
0x18000c76a  mov     [rbx+148h], edi
0x18000c770  mov     rcx, rsi; this
0x18000c773  call    ?Release@CASFLonghandObject@@QEAAKXZ; CASFLonghandObject::Release(void)
0x18000c778  mov     rcx, [rsp+1A0h+var_140]
0x18000c77d  jmp     loc_18000C69E
  ... truncated ...
```
