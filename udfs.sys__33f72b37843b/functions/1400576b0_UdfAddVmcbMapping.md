# UdfAddVmcbMapping

- ea: `0x1400576b0`
- end: `0x140057c21`
- name: `UdfAddVmcbMapping`
- size: `1393`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x14003d660`

## callees

- `0x140009014`
- `0x14000ca10`
- `0x14001093c`
- `0x140010990`
- `0x140018ff8`
- `0x140019244`
- `0x140019398`
- `0x140056b54`
- `0x1400576b0`

## import_xrefs

- `ntoskrnl!FsRtlLookupLargeMcbEntry` at `0x14005776d`
- `ntoskrnl!FsRtlLookupLargeMcbEntry` at `0x14005776d`
- `ntoskrnl!FsRtlRemoveLargeMcbEntry` at `0x14005aea9`
- `ntoskrnl!FsRtlRemoveLargeMcbEntry` at `0x14005aed1`
- `ntoskrnl!FsRtlRemoveLargeMcbEntry` at `0x14005aea9`
- `ntoskrnl!FsRtlRemoveLargeMcbEntry` at `0x14005aed1`
- `ntoskrnl!CcFlushCache` at `0x140057a1d`
- `ntoskrnl!CcFlushCache` at `0x140057a1d`
- `ntoskrnl!CcPurgeCacheSection` at `0x14005793d`
- `ntoskrnl!CcPurgeCacheSection` at `0x14005793d`
- `ntoskrnl!FsRtlAddMcbEntry` at `0x140057b00`
- `ntoskrnl!FsRtlAddMcbEntry` at `0x140057b34`
- `ntoskrnl!FsRtlAddMcbEntry` at `0x140057b00`
- `ntoskrnl!FsRtlAddMcbEntry` at `0x140057b34`

## pseudocode

```c
char __fastcall UdfAddVmcbMapping(__int64 a1, __int64 a2, LBN a3, unsigned int a4, char a5, _DWORD *a6, ULONG *a7)
{
  LBN v10; // edi
  VBN v11; // r14d
  BOOLEAN v12; // al
  __int64 v13; // rdx
  __int64 v14; // r8
  ULONG v15; // esi
  ULONG *v16; // rdx
  char v17; // r15
  _DWORD *v18; // r8
  LBN v19; // esi
  unsigned int v20; // r14d
  int v21; // eax
  unsigned int v22; // edi
  __int64 v23; // rdx
  __int64 v24; // r9
  unsigned int v25; // edi
  union _LARGE_INTEGER v26; // r9
  VBN v27; // ecx
  int v28; // edi
  VBN v29; // ecx
  int v31; // [rsp+40h] [rbp-78h]
  unsigned __int64 v32; // [rsp+48h] [rbp-70h]
  int v33; // [rsp+50h] [rbp-68h] BYREF
  __int64 Lbn; // [rsp+58h] [rbp-60h] BYREF
  unsigned int v35; // [rsp+60h] [rbp-58h]
  union _LARGE_INTEGER FileOffset; // [rsp+68h] [rbp-50h] BYREF
  __int64 SectorCountFromLbn[4]; // [rsp+70h] [rbp-48h] BYREF
  char v38; // [rsp+C0h] [rbp+8h]
  LBN Vbn; // [rsp+D0h] [rbp+18h]

  Vbn = a3;
  BYTE1(v31) = 0;
  BYTE2(v31) = 0;
  v38 = 0;
  FileOffset.QuadPart = 0;
  v10 = 0;
  v32 = 0;
  v11 = 0;
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x400000) != 0 )
  {
    WPP_SF_dd(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
      24,
      WPP_c4c254f43dbb37edeabcdd77880d9f11_Traceguids,
      a3,
      a4);
    a3 = Vbn;
  }
  Lbn = 0;
  SectorCountFromLbn[0] = 0;
  v12 = FsRtlLookupLargeMcbEntry((PLARGE_MCB)(a2 + 248), a3, &Lbn, SectorCountFromLbn, 0, 0, 0);
  if ( (_DWORD)Lbn == -1 )
  {
    *a6 = 0;
    v12 = 0;
  }
  else
  {
    *a6 = Lbn;
  }
  v15 = SectorCountFromLbn[0];
  if ( v12 )
  {
    if ( a4 > LODWORD(SectorCountFromLbn[0]) )
      UdfRaiseStatusEx(a1, 3221225730LL, 0);
    if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x400000) != 0 )
    {
      WPP_SF_d(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 25, WPP_c4c254f43dbb37edeabcdd77880d9f11_Traceguids);
    }
    v16 = a7;
    *a7 = v15;
    v17 = 0;
    v18 = a6;
  }
  else
  {
    if ( a5 && *(_DWORD *)(a2 + 312) )
    {
      v19 = Vbn;
      v20 = Vbn & ~*(_DWORD *)(a2 + 292);
      v21 = Vbn & *(_DWORD *)(a2 + 292);
      LODWORD(Lbn) = v21;
      v33 = 0;
      v35 = 0;
      v22 = 0;
      v17 = 1;
      while ( 1 )
      {
        v35 = v22;
        if ( v22 >= *(_DWORD *)(a2 + 288) )
          break;
        if ( v22 != v21 )
        {
          if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x400000) != 0 )
          {
            WPP_SF_Dd(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), v13, v14, v20, v22);
          }
          if ( (unsigned __int8)UdfVmcbLookupMcbEntry(a2 + 248, v22 + v20, &v33, 0) )
          {
            if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x400000) != 0 )
            {
              WPP_SF_d(
                *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
                27,
                WPP_c4c254f43dbb37edeabcdd77880d9f11_Traceguids);
            }
            v23 = v33 - v22;
            v11 = v23 + Lbn;
            HIDWORD(v32) = v23 + Lbn;
            v10 = Vbn;
            LODWORD(v32) = Vbn;
            v15 = a4;
            FileOffset.QuadPart = v23 << *(_DWORD *)(a2 + 296);
            CcPurgeCacheSection(
              *(PSECTION_OBJECT_POINTERS *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 272LL) + 504LL) + 40LL),
              &FileOffset,
              0x1000u,
              0);
            v38 = 1;
            goto LABEL_44;
          }
          v21 = Lbn;
        }
        ++v22;
      }
    }
    else
    {
      v17 = 1;
      v19 = Vbn;
    }
    if ( !*(_DWORD *)(a2 + 316) )
    {
      UdfVmcbPurgeSomeMappings(a1, a2);
      if ( !*(_DWORD *)(a2 + 316) )
      {
        v24 = *(unsigned int *)(a2 + 304);
        v25 = *(_DWORD *)(a2 + 308) - v24;
        if ( v25 >= 16 << *(_DWORD *)(a2 + 300) )
          v25 = 16 << *(_DWORD *)(a2 + 300);
        v26.QuadPart = v24 << *(_DWORD *)(*(_QWORD *)(a1 + 16) + 72LL);
        FileOffset = v26;
        if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x400000) != 0 )
        {
          ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD))WPP_SF_dd)(
            *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
            28,
            WPP_c4c254f43dbb37edeabcdd77880d9f11_Traceguids,
            (union _LARGE_INTEGER)v26.QuadPart,
            v25);
        }
        CcFlushCache(
          *(PSECTION_OBJECT_POINTERS *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 272LL) + 504LL) + 40LL),
          &FileOffset,
          v25 << *(_DWORD *)(*(_QWORD *)(a1 + 16) + 72LL),
          0);
        UdfVmcbPurgeSomeMappings(a1, a2);
        if ( !*(_DWORD *)(a2 + 316) )
          UdfRaiseStatusEx(a1, 3221225701LL, 0);
      }
    }
    v27 = *(_DWORD *)(a2 + 304);
    v11 = v27;
    HIDWORD(v32) = v27;
    v28 = *(_DWORD *)(a2 + 292);
    if ( a5 )
    {
      v11 = v27 + (v19 & v28);
      v10 = v19;
      v32 = __PAIR64__(v11, v19);
      v15 = a4;
    }
    else
    {
      v10 = v19 & ~v28;
      LODWORD(v32) = v10;
      v15 = *(_DWORD *)(a2 + 288);
    }
    v29 = *(_DWORD *)(a2 + 288) + v27;
    *(_DWORD *)(a2 + 304) = v29;
    if ( v29 == *(_DWORD *)(a2 + 308) )
      *(_DWORD *)(a2 + 304) = 16;
LABEL_44:
    if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x400000) != 0 )
    {
      WPP_SF_DDD(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
        29,
        WPP_c4c254f43dbb37edeabcdd77880d9f11_Traceguids,
        v11,
        v10,
        v15);
    }
    if ( !FsRtlAddMcbEntry((PMCB)(a2 + 216), v11, v10, v15) )
      UdfRaiseStatusEx(a1, 3221225701LL, 0);
    BYTE1(v31) = 1;
    if ( !FsRtlAddMcbEntry((PMCB)(a2 + 248), v10, v11, v15) )
      UdfRaiseStatusEx(a1, 3221225701LL, 0);
    BYTE2(v31) = 1;
    v18 = a6;
    *a6 = Vbn + v11 - v10;
    v16 = a7;
    *a7 = v10 + v15 - Vbn;
    *(_DWORD *)(a2 + 312) -= v15;
    if ( !v38 )
      --*(_DWORD *)(a2 + 316);
  }
  LOBYTE(v31) = v17;
  if ( v17
    && *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x400000) != 0 )
  {
    WPP_SF_DDDDD(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), v16, v18, v11, v10, v15, *v18, *v16, v31, v32);
  }
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x400000) != 0 )
  {
    WPP_SF_d(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 31, WPP_c4c254f43dbb37edeabcdd77880d9f11_Traceguids);
  }
  return v17;
}

```

## disassembly

```asm
0x1400576b0  mov     rax, rsp
0x1400576b3  mov     [rax+20h], r9d
0x1400576b7  mov     [rax+18h], r8d
0x1400576bb  mov     [rax+10h], rdx
0x1400576bf  push    rbx
0x1400576c0  push    rsi
0x1400576c1  push    rdi
0x1400576c2  push    r12
0x1400576c4  push    r13
0x1400576c6  push    r14
0x1400576c8  push    r15
0x1400576ca  sub     rsp, 80h
0x1400576d1  mov     r15d, r9d
0x1400576d4  mov     rbx, rdx
0x1400576d7  mov     r13, rcx
0x1400576da  xor     esi, esi
0x1400576dc  mov     [rax-78h], sil
0x1400576e0  mov     [rax-77h], sil
0x1400576e4  mov     [rax-76h], sil
0x1400576e8  mov     [rax+8], sil
0x1400576ec  mov     [rax-50h], rsi
0x1400576f0  mov     edi, esi
0x1400576f2  mov     [rax-70h], esi
0x1400576f5  mov     r14d, esi
0x1400576f8  mov     [rax-6Ch], esi
0x1400576fb  mov     [rax-74h], esi
0x1400576fe  lea     rax, WPP_GLOBAL_Control
0x140057705  mov     rcx, cs:WPP_GLOBAL_Control
0x14005770c  mov     r12d, 400000h
0x140057712  cmp     rcx, rax
0x140057715  jz      short loc_140057740
0x140057717  test    [rcx+2Ch], r12d
0x14005771b  jz      short loc_140057740
0x14005771d  lea     edx, [rsi+18h]
0x140057720  mov     dword ptr [rsp+0B8h+StartingLbn], r9d
0x140057725  mov     r9d, r8d
0x140057728  lea     r8, WPP_c4c254f43dbb37edeabcdd77880d9f11_Traceguids
0x14005772f  mov     rcx, [rcx+18h]
0x140057733  call    WPP_SF_dd
0x140057738  mov     r8d, [rsp+0B8h+Vbn]
0x140057740  mov     [rsp+0B8h+Lbn], rsi
0x140057745  mov     [rsp+0B8h+SectorCountFromLbn], rsi
0x14005774a  lea     rcx, [rbx+0F8h]; Mcb
0x140057751  mov     edx, r8d; Vbn
0x140057754  mov     [rsp+0B8h+Index], rsi; Index
0x140057759  mov     [rsp+0B8h+SectorCountFromStartingLbn], rsi; SectorCountFromStartingLbn
0x14005775e  mov     [rsp+0B8h+StartingLbn], rsi; StartingLbn
0x140057763  lea     r9, [rsp+0B8h+SectorCountFromLbn]; SectorCountFromLbn
0x140057768  lea     r8, [rsp+0B8h+Lbn]; Lbn
0x14005776d  call    cs:__imp_FsRtlLookupLargeMcbEntry
0x140057774  nop     dword ptr [rax+rax+00h]
0x140057779  mov     r9, [rsp+0B8h+Lbn]
0x14005777e  mov     rcx, [rsp+0B8h+arg_28]
0x140057786  cmp     r9d, 0FFFFFFFFh
0x14005778a  jnz     short loc_140057796
0x14005778c  mov     [rcx], esi
0x14005778e  mov     al, sil
0x140057791  mov     r9d, esi
0x140057794  jmp     short loc_140057799
0x140057796  mov     [rcx], r9d
0x140057799  mov     rsi, [rsp+0B8h+SectorCountFromLbn]
0x14005779e  mov     [rsp+0B8h+var_74], esi
0x1400577a2  test    al, al
0x1400577a4  jz      short loc_140057803
0x1400577a6  cmp     r15d, esi
0x1400577a9  ja      short loc_1400577F3
0x1400577ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1400577b2  lea     rbx, WPP_GLOBAL_Control
0x1400577b9  cmp     rcx, rbx
0x1400577bc  jz      short loc_1400577D9
0x1400577be  test    [rcx+2Ch], r12d
0x1400577c2  jz      short loc_1400577D9
0x1400577c4  mov     edx, 19h
0x1400577c9  lea     r8, WPP_c4c254f43dbb37edeabcdd77880d9f11_Traceguids
0x1400577d0  mov     rcx, [rcx+18h]
0x1400577d4  call    WPP_SF_d
0x1400577d9  mov     rdx, [rsp+0B8h+arg_30]
0x1400577e1  mov     [rdx], esi
0x1400577e3  xor     r15b, r15b
0x1400577e6  mov     r8, [rsp+0B8h+arg_28]
0x1400577ee  jmp     loc_140057BA2
0x1400577f3  xor     r8d, r8d
0x1400577f6  mov     edx, 0C0000102h
0x1400577fb  mov     rcx, r13
0x1400577fe  call    UdfRaiseStatusEx
0x140057803  cmp     [rsp+0B8h+arg_20], 0
0x14005780b  jz      loc_140057962
0x140057811  cmp     dword ptr [rbx+138h], 0
0x140057818  jbe     loc_140057962
0x14005781e  mov     eax, [rbx+124h]
0x140057824  mov     r14d, eax
0x140057827  not     r14d
0x14005782a  mov     esi, [rsp+0B8h+Vbn]
0x140057831  and     r14d, esi
0x140057834  and     eax, esi
0x140057836  mov     dword ptr [rsp+0B8h+Lbn], eax
0x14005783a  mov     [rsp+0B8h+var_68], 0
0x140057842  mov     [rsp+0B8h+var_58], 0
0x14005784a  xor     edi, edi
0x14005784c  lea     r15d, [rdi+1]
0x140057850  mov     [rsp+0B8h+var_58], edi
0x140057854  cmp     edi, [rbx+120h]
0x14005785a  jnb     loc_14005796F
0x140057860  cmp     edi, eax
0x140057862  jnz     short loc_140057869
0x140057864  jmp     loc_14005795A
0x140057869  mov     rcx, cs:WPP_GLOBAL_Control
0x140057870  lea     rax, WPP_GLOBAL_Control
0x140057877  cmp     rcx, rax
0x14005787a  jz      short loc_140057892
0x14005787c  test    [rcx+2Ch], r12d
0x140057880  jz      short loc_140057892
0x140057882  mov     dword ptr [rsp+0B8h+StartingLbn], edi
0x140057886  mov     r9d, r14d
0x140057889  mov     rcx, [rcx+18h]
0x14005788d  call    WPP_SF_Dd
0x140057892  lea     edx, [rdi+r14]
0x140057896  xor     r9d, r9d
0x140057899  lea     r8, [rsp+0B8h+var_68]
0x14005789e  lea     rcx, [rbx+0F8h]
0x1400578a5  call    UdfVmcbLookupMcbEntry
0x1400578aa  test    al, al
0x1400578ac  jz      loc_140057956
0x1400578b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400578b9  lea     rax, WPP_GLOBAL_Control
0x1400578c0  cmp     rcx, rax
0x1400578c3  jz      short loc_1400578E5
0x1400578c5  test    [rcx+2Ch], r12d
0x1400578c9  jz      short loc_1400578E5
0x1400578cb  mov     edx, 1Bh
0x1400578d0  mov     r9d, [rsp+0B8h+var_68]
0x1400578d5  lea     r8, WPP_c4c254f43dbb37edeabcdd77880d9f11_Traceguids
0x1400578dc  mov     rcx, [rcx+18h]
0x1400578e0  call    WPP_SF_d
0x1400578e5  mov     eax, [rsp+0B8h+var_68]
0x1400578e9  sub     eax, edi
0x1400578eb  mov     edx, eax
0x1400578ed  mov     r14d, dword ptr [rsp+0B8h+Lbn]
0x1400578f2  add     r14d, eax
0x1400578f5  mov     [rsp+0B8h+var_6C], r14d
0x1400578fa  mov     edi, esi
0x1400578fc  mov     [rsp+0B8h+var_70], esi
0x140057900  mov     esi, [rsp+0B8h+SectorCount]
0x140057907  mov     [rsp+0B8h+var_74], esi
0x14005790b  mov     ecx, [rbx+128h]
0x140057911  shl     rdx, cl
0x140057914  mov     qword ptr [rsp+0B8h+FileOffset], rdx
0x140057919  mov     rax, [r13+10h]
0x14005791d  mov     rcx, [rax+110h]
0x140057924  mov     rcx, [rcx+1F8h]
0x14005792b  xor     r9d, r9d; Flags
0x14005792e  mov     r8d, 1000h; Length
0x140057934  lea     rdx, [rsp+0B8h+FileOffset]; FileOffset
0x140057939  mov     rcx, [rcx+28h]; SectionObjectPointer
0x14005793d  call    cs:__imp_CcPurgeCacheSection
0x140057944  nop     dword ptr [rax+rax+00h]
0x140057949  mov     [rsp+0B8h+arg_0], r15b
0x140057951  jmp     loc_140057AB7
0x140057956  mov     eax, dword ptr [rsp+0B8h+Lbn]
0x14005795a  add     edi, r15d
0x14005795d  jmp     loc_140057850
0x140057962  mov     r15d, 1
0x140057968  mov     esi, [rsp+0B8h+Vbn]
0x14005796f  cmp     dword ptr [rbx+13Ch], 0
0x140057976  jnz     loc_140057A4D
0x14005797c  mov     rdx, rbx
0x14005797f  mov     rcx, r13
0x140057982  call    UdfVmcbPurgeSomeMappings
0x140057987  cmp     dword ptr [rbx+13Ch], 0
0x14005798e  jnz     loc_140057A4D
0x140057994  mov     ecx, [rbx+12Ch]
0x14005799a  mov     eax, 10h
0x14005799f  shl     eax, cl
0x1400579a1  mov     r9d, [rbx+130h]
0x1400579a8  mov     edi, [rbx+134h]
0x1400579ae  sub     edi, r9d
0x1400579b1  cmp     edi, eax
0x1400579b3  cmovnb  edi, eax
0x1400579b6  mov     rcx, [r13+10h]
0x1400579ba  mov     ecx, [rcx+48h]
0x1400579bd  shl     r9, cl
0x1400579c0  mov     qword ptr [rsp+0B8h+FileOffset], r9
0x1400579c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400579cc  lea     rax, WPP_GLOBAL_Control
0x1400579d3  cmp     rcx, rax
0x1400579d6  jz      short loc_1400579F7
0x1400579d8  test    [rcx+2Ch], r12d
0x1400579dc  jz      short loc_1400579F7
0x1400579de  mov     edx, 1Ch
0x1400579e3  mov     dword ptr [rsp+0B8h+StartingLbn], edi
0x1400579e7  lea     r8, WPP_c4c254f43dbb37edeabcdd77880d9f11_Traceguids
0x1400579ee  mov     rcx, [rcx+18h]
0x1400579f2  call    WPP_SF_dd
0x1400579f7  mov     rax, [r13+10h]
0x1400579fb  mov     ecx, [rax+48h]
0x1400579fe  shl     edi, cl
0x140057a00  mov     rax, [rax+110h]
0x140057a07  mov     rcx, [rax+1F8h]
0x140057a0e  xor     r9d, r9d; IoStatus
0x140057a11  mov     r8d, edi; Length
0x140057a14  lea     rdx, [rsp+0B8h+FileOffset]; FileOffset
0x140057a19  mov     rcx, [rcx+28h]; SectionObjectPointer
0x140057a1d  call    cs:__imp_CcFlushCache
0x140057a24  nop     dword ptr [rax+rax+00h]
0x140057a29  mov     rdx, rbx
0x140057a2c  mov     rcx, r13
0x140057a2f  call    UdfVmcbPurgeSomeMappings
0x140057a34  cmp     dword ptr [rbx+13Ch], 0
0x140057a3b  jnz     short loc_140057A4D
0x140057a3d  xor     r8d, r8d
0x140057a40  mov     edx, 0C00000E5h
0x140057a45  mov     rcx, r13
0x140057a48  call    UdfRaiseStatusEx
0x140057a4d  mov     ecx, [rbx+130h]
0x140057a53  mov     r14d, ecx
0x140057a56  mov     [rsp+0B8h+var_6C], ecx
0x140057a5a  mov     edi, [rbx+124h]
0x140057a60  cmp     [rsp+0B8h+arg_20], 0
0x140057a68  jnz     short loc_140057A7A
0x140057a6a  not     edi
0x140057a6c  and     edi, esi
0x140057a6e  mov     [rsp+0B8h+var_70], edi
0x140057a72  mov     esi, [rbx+120h]
0x140057a78  jmp     short loc_140057A95
0x140057a7a  mov     r14d, edi
0x140057a7d  and     r14d, esi
0x140057a80  add     r14d, ecx
0x140057a83  mov     [rsp+0B8h+var_6C], r14d
0x140057a88  mov     edi, esi
0x140057a8a  mov     [rsp+0B8h+var_70], esi
0x140057a8e  mov     esi, [rsp+0B8h+SectorCount]
0x140057a95  mov     [rsp+0B8h+var_74], esi
0x140057a99  add     ecx, [rbx+120h]
0x140057a9f  mov     [rbx+130h], ecx
0x140057aa5  cmp     ecx, [rbx+134h]
0x140057aab  jnz     short loc_140057AB7
0x140057aad  mov     dword ptr [rbx+130h], 10h
0x140057ab7  mov     rcx, cs:WPP_GLOBAL_Control
0x140057abe  lea     rax, WPP_GLOBAL_Control
0x140057ac5  cmp     rcx, rax
0x140057ac8  jz      short loc_140057AF0
0x140057aca  test    [rcx+2Ch], r12d
0x140057ace  jz      short loc_140057AF0
0x140057ad0  mov     edx, 1Dh
0x140057ad5  mov     dword ptr [rsp+0B8h+SectorCountFromStartingLbn], esi
0x140057ad9  mov     dword ptr [rsp+0B8h+StartingLbn], edi
0x140057add  mov     r9d, r14d
0x140057ae0  lea     r8, WPP_c4c254f43dbb37edeabcdd77880d9f11_Traceguids
0x140057ae7  mov     rcx, [rcx+18h]
0x140057aeb  call    WPP_SF_DDD
0x140057af0  lea     rcx, [rbx+0D8h]; Mcb
0x140057af7  mov     r9d, esi; SectorCount
0x140057afa  mov     r8d, edi; Lbn
0x140057afd  mov     edx, r14d; Vbn
0x140057b00  call    cs:__imp_FsRtlAddMcbEntry
0x140057b07  nop     dword ptr [rax+rax+00h]
0x140057b0c  test    al, al
0x140057b0e  jnz     short loc_140057B20
0x140057b10  xor     r8d, r8d
0x140057b13  mov     edx, 0C00000E5h
0x140057b18  mov     rcx, r13
0x140057b1b  call    UdfRaiseStatusEx
0x140057b20  mov     [rsp+0B8h+var_77], r15b
0x140057b25  mov     r9d, esi; SectorCount
0x140057b28  mov     r8d, r14d; Lbn
0x140057b2b  mov     edx, edi; Vbn
0x140057b2d  lea     rcx, [rbx+0F8h]; Mcb
0x140057b34  call    cs:__imp_FsRtlAddMcbEntry
0x140057b3b  nop     dword ptr [rax+rax+00h]
0x140057b40  test    al, al
0x140057b42  jnz     short loc_140057B54
0x140057b44  xor     r8d, r8d
0x140057b47  mov     edx, 0C00000E5h
0x140057b4c  mov     rcx, r13
0x140057b4f  call    UdfRaiseStatusEx
0x140057b54  mov     [rsp+0B8h+var_76], r15b
0x140057b59  mov     eax, r14d
0x140057b5c  sub     eax, edi
0x140057b5e  add     eax, [rsp+0B8h+Vbn]
0x140057b65  mov     r8, [rsp+0B8h+arg_28]
0x140057b6d  mov     [r8], eax
0x140057b70  mov     eax, esi
0x140057b72  sub     eax, [rsp+0B8h+Vbn]
0x140057b79  add     eax, edi
0x140057b7b  mov     rdx, [rsp+0B8h+arg_30]
0x140057b83  mov     [rdx], eax
0x140057b85  sub     [rbx+138h], esi
0x140057b8b  cmp     [rsp+0B8h+arg_0], 0
0x140057b93  jnz     short loc_140057B9B
0x140057b95  dec     dword ptr [rbx+13Ch]
0x140057b9b  lea     rbx, WPP_GLOBAL_Control
0x140057ba2  mov     [rsp+0B8h+var_78], r15b
0x140057ba7  test    r15b, r15b
0x140057baa  jz      short loc_140057BDF
0x140057bac  mov     rcx, cs:WPP_GLOBAL_Control
0x140057bb3  cmp     rcx, rbx
0x140057bb6  jz      short loc_140057BDF
0x140057bb8  test    [rcx+2Ch], r12d
0x140057bbc  jz      short loc_140057BDF
0x140057bbe  mov     eax, [rdx]
  ... truncated ...
```
