# SdbpMergeFindLibraryEntries

- ea: `0x14001cd7c`
- end: `0x14001d48d`
- name: `SdbpMergeFindLibraryEntries`
- size: `1809`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14001d808`

## callees

- `0x14001008c`
- `0x140014380`
- `0x140015e14`
- `0x140016070`
- `0x140016148`
- `0x140018d48`
- `0x14001b2f0`
- `0x14001cd7c`
- `0x14001f90c`
- `0x14002e3e2`

## import_xrefs

- `msvcrt!qsort` at `0x14001d45c`
- `msvcrt!qsort` at `0x14001d45c`
- `ntdll!RtlAllocateHeap` at `0x14001d001`
- `ntdll!RtlAllocateHeap` at `0x14001d357`
- `ntdll!RtlAllocateHeap` at `0x14001d001`
- `ntdll!RtlAllocateHeap` at `0x14001d357`
- `ntdll!RtlReAllocateHeap` at `0x14001d021`
- `ntdll!RtlReAllocateHeap` at `0x14001d377`
- `ntdll!RtlReAllocateHeap` at `0x14001d021`
- `ntdll!RtlReAllocateHeap` at `0x14001d377`

## string_xrefs

- `0x14001d41a`: ` failed to update indexes for the library items list [%x]`

## pseudocode

```c
__int64 __fastcall SdbpMergeFindLibraryEntries(__int64 a1, __int64 a2, unsigned __int64 *a3, int a4, __int64 a5)
{
  __int64 v5; // rdi
  unsigned __int64 *v6; // r14
  __int64 v7; // rsi
  __int64 v8; // rbx
  unsigned int FirstTag; // eax
  unsigned int v10; // eax
  unsigned int v11; // r13d
  unsigned int FirstChild; // r12d
  unsigned __int64 v13; // rbx
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int NextChild; // eax
  __int128 v17; // xmm6
  __int128 v18; // xmm7
  __int16 TagFromTagID; // ax
  unsigned __int64 v20; // rcx
  __int16 v21; // r15
  __int64 v22; // rsi
  unsigned __int64 v23; // rbx
  __int64 v24; // r14
  _DWORD *v25; // rax
  __int64 v26; // rax
  __int16 v27; // r8
  unsigned int v28; // eax
  unsigned __int64 v29; // r15
  unsigned __int64 v30; // rcx
  int updated; // ebx
  __int64 v32; // rsi
  unsigned __int64 v33; // rsi
  unsigned __int128 v34; // rax
  size_t v35; // r14
  void *v36; // r8
  void *v37; // rcx
  PVOID v38; // rax
  PVOID Heap; // rbx
  unsigned __int64 v40; // rax
  __int64 v41; // r8
  const char *v42; // r9
  __int16 v44; // r13
  __int64 v45; // rcx
  __int16 v46; // r8
  unsigned int v47; // eax
  unsigned int v48; // r14d
  __int64 v49; // r15
  unsigned __int64 v50; // rsi
  __int64 v51; // rbx
  unsigned __int64 v52; // rax
  unsigned __int64 v53; // rcx
  __int64 v54; // rdx
  __int128 v55; // xmm6
  unsigned __int64 v56; // rcx
  __int64 v57; // rsi
  unsigned __int64 v58; // rbx
  __int64 v59; // r14
  _DWORD *v60; // rax
  unsigned __int64 v61; // r15
  unsigned __int64 v62; // rcx
  __int64 v63; // rsi
  unsigned __int64 v64; // rsi
  unsigned __int128 v65; // rax
  size_t v66; // r14
  void *v67; // r8
  void *v68; // rcx
  PVOID v69; // rax
  PVOID v70; // rbx
  unsigned __int64 v71; // rax
  unsigned int v72; // r12d
  __int64 v73; // [rsp+28h] [rbp-81h]
  unsigned int v74; // [rsp+38h] [rbp-71h]
  unsigned int v75; // [rsp+38h] [rbp-71h]
  unsigned __int64 v76; // [rsp+40h] [rbp-69h]
  __int128 v77; // [rsp+58h] [rbp-51h]
  __int128 v78; // [rsp+58h] [rbp-51h]
  __int128 v79; // [rsp+68h] [rbp-41h]
  __int128 v80; // [rsp+68h] [rbp-41h]
  __int128 v81; // [rsp+78h] [rbp-31h]
  __int128 v82; // [rsp+78h] [rbp-31h]

  v5 = a5;
  v6 = a3;
  v7 = a2;
  v8 = a1;
  FirstTag = SdbFindFirstTag(a1, 0, 28673);
  if ( !FirstTag )
    return 3221225624LL;
  v10 = SdbFindFirstTag(v8, FirstTag, 28674);
  v74 = v10;
  v11 = v10;
  if ( v10 )
  {
    FirstChild = SdbGetFirstChild(v8, v10);
    if ( FirstChild )
    {
      while ( 1 )
      {
        v17 = 0;
        v18 = 0;
        v77 = 0;
        v79 = 0;
        v81 = 0;
        TagFromTagID = SdbGetTagFromTagID(v8, FirstChild);
        v20 = v6[2];
        WORD6(v77) = TagFromTagID;
        v21 = TagFromTagID;
        LODWORD(v77) = FirstChild;
        if ( v20 )
        {
          v22 = 0;
          v23 = 0;
          v24 = 0;
          do
          {
            v25 = 0;
            if ( v23 < v20 )
            {
              if ( !is_mul_ok(a3[1], v23) || (v25 = (_DWORD *)(a3[5] + a3[1] * v23), (unsigned __int64)v25 < a3[5]) )
                v25 = 0;
            }
            if ( v25[4]
              && *(_WORD *)(*(_QWORD *)v25 + 4LL) == v21
              && (unsigned int)SdbFindFirstTag(a1, FirstChild, *(_WORD *)(*(_QWORD *)v25 + 6LL)) )
            {
              if ( v23 >= 0x40 )
              {
                v22 |= 1LL << ((unsigned __int8)v23 - 64);
                *((_QWORD *)&v79 + 1) = v22;
              }
              else
              {
                v24 |= 1LL << v23;
                *(_QWORD *)&v79 = v24;
              }
            }
            v20 = a3[2];
            ++v23;
          }
          while ( v23 < v20 );
          v5 = a5;
          v11 = v74;
          v17 = v79;
          v8 = a1;
        }
        v26 = 0;
        while ( *((_WORD *)qword_140039F70 + 5 * v26) != v21 )
        {
          if ( (unsigned __int64)++v26 >= 0x24 )
            goto LABEL_29;
        }
        v27 = *((_WORD *)qword_140039F70 + 5 * v26 + 1);
        if ( v27 )
        {
          v28 = SdbFindFirstTag(v8, FirstChild, v27);
          DWORD2(v77) = v28;
          if ( v28 )
          {
            *(_QWORD *)&v81 = SdbpTagToKey(v8, v28, 0);
            v18 = v81;
          }
        }
LABEL_29:
        v29 = *(_QWORD *)(v5 + 16);
        if ( v29 >= *(_QWORD *)(v5 + 24) )
        {
          v30 = v29 + 1;
          if ( v29 + 1 <= *(_QWORD *)(v5 + 24) )
          {
            updated = -1073741811;
            goto LABEL_48;
          }
          v32 = *(_QWORD *)(v5 + 32) - 1LL;
          if ( v32 + v30 < v30
            || !is_mul_ok(*(_QWORD *)(v5 + 24), *(_QWORD *)(v5 + 8))
            || (v33 = (v32 + v30) & ~v32,
                v34 = v33 * (unsigned __int128)*(unsigned __int64 *)(v5 + 8),
                v35 = v33 * *(_QWORD *)(v5 + 8),
                !is_mul_ok(v33, *(_QWORD *)(v5 + 8))) )
          {
            updated = -1073741675;
            goto LABEL_48;
          }
          v36 = *(void **)(v5 + 40);
          v37 = *(void **)v5;
          if ( v36 )
          {
            Heap = RtlReAllocateHeap(v37, DWORD2(v34), v36, v34);
          }
          else
          {
            v38 = RtlAllocateHeap(v37, DWORD2(v34), v34);
            Heap = v38;
            if ( v38 )
              memset_0(v38, 0, v35);
          }
          if ( !Heap )
          {
            updated = -1073741801;
            goto LABEL_48;
          }
          *(_QWORD *)(v5 + 40) = Heap;
          *(_QWORD *)(v5 + 24) = v33;
        }
        if ( !is_mul_ok(*(_QWORD *)(v5 + 8), v29) )
          break;
        v40 = *(_QWORD *)(v5 + 40) + *(_QWORD *)(v5 + 8) * v29;
        if ( v40 < *(_QWORD *)(v5 + 40) )
          break;
        *(_OWORD *)v40 = v77;
        *(_OWORD *)(v40 + 16) = v17;
        *(_OWORD *)(v40 + 32) = v18;
        *(_QWORD *)(v40 + 48) = 0;
        ++*(_QWORD *)(v5 + 16);
        v8 = a1;
        FirstChild = SdbGetNextChild(a1, v11, FirstChild);
        if ( !FirstChild )
        {
          v7 = a2;
          goto LABEL_4;
        }
        v6 = a3;
      }
      updated = -1073741675;
LABEL_48:
      v41 = 1280;
      goto LABEL_49;
    }
  }
LABEL_4:
  v13 = *(_QWORD *)(v5 + 16);
  v76 = v13;
  v14 = SdbFindFirstTag(v7, 0, 28673);
  if ( !v14 )
    return 3221225624LL;
  v15 = SdbFindFirstTag(v7, v14, 28674);
  v75 = v15;
  if ( v15 )
  {
    NextChild = SdbGetFirstChild(v7, v15);
    while ( 2 )
    {
      v72 = NextChild;
      if ( NextChild )
      {
        v44 = SdbGetTagFromTagID(v7, NextChild);
        v45 = 0;
        while ( *((_WORD *)qword_140039F70 + 5 * v45) != v44 )
        {
          if ( (unsigned __int64)++v45 >= 0x24 )
            goto LABEL_103;
        }
        v46 = *((_WORD *)qword_140039F70 + 5 * v45 + 1);
        if ( !v46 )
        {
LABEL_103:
          NextChild = SdbGetNextChild(v7, v75, v72);
          continue;
        }
        v47 = SdbFindFirstTag(v7, v72, v46);
        v48 = v47;
        if ( !v47 )
        {
          AslLogCallPrintf(
            3,
            "SdbpMergeFindLibraryEntries",
            1319,
            "Skipping merge tagid 0x%X as the entry had no merge key",
            v72);
          goto LABEL_103;
        }
        v49 = SdbpTagToKey(v7, v47, 0);
        if ( !v49 && SdbpTagToKey(v7, v48, 1) == 1 )
        {
          AslLogCallPrintf(
            3,
            "SdbpMergeFindLibraryEntries",
            1327,
            "Skipping merge of tagid 0x%X. The entry had a merge key (0x%X) but key has was zero.",
            v72,
            v48);
          goto LABEL_103;
        }
        v50 = 0;
        if ( v13 )
        {
          while ( 1 )
          {
            v51 = 0;
            if ( v50 < *(_QWORD *)(v5 + 16) )
            {
              v52 = *(_QWORD *)(v5 + 8) * v50;
              if ( !is_mul_ok(*(_QWORD *)(v5 + 8), v50)
                || (v53 = *(_QWORD *)(v5 + 40), v51 = v53 + v52, v53 + v52 < v53) )
              {
                v51 = 0;
              }
            }
            if ( *(_WORD *)(v51 + 12) == v44 )
            {
              v54 = *(unsigned int *)(v51 + 8);
              if ( (_DWORD)v54 )
              {
                if ( *(_QWORD *)(v51 + 32) == v49 && SdbpMergeAreTagValuesEqual(a1, v54, a2, v48, 1) )
                  break;
              }
            }
            if ( ++v50 >= v76 )
              goto LABEL_71;
          }
          *(_DWORD *)(v51 + 4) = v72;
          goto LABEL_102;
        }
LABEL_71:
        v55 = 0;
        v78 = 0;
        v82 = (unsigned __int64)v49;
        v80 = 0;
        *(_QWORD *)((char *)&v78 + 4) = __PAIR64__(v48, v72);
        WORD6(v78) = v44;
        v56 = a3[2];
        if ( v56 )
        {
          v57 = 0;
          v58 = 0;
          v59 = 0;
          do
          {
            v60 = 0;
            if ( v58 < v56 )
            {
              if ( !is_mul_ok(a3[1], v58) || (v60 = (_DWORD *)(a3[5] + a3[1] * v58), (unsigned __int64)v60 < a3[5]) )
                v60 = 0;
            }
            if ( v60[4]
              && *(_WORD *)(*(_QWORD *)v60 + 4LL) == v44
              && (unsigned int)SdbFindFirstTag(a2, v72, *(_WORD *)(*(_QWORD *)v60 + 6LL)) )
            {
              if ( v58 >= 0x40 )
              {
                v57 |= 1LL << ((unsigned __int8)v58 - 64);
                *((_QWORD *)&v80 + 1) = v57;
              }
              else
              {
                v59 |= 1LL << v58;
                *(_QWORD *)&v80 = v59;
              }
            }
            v56 = a3[2];
            ++v58;
          }
          while ( v58 < v56 );
          v5 = a5;
          v55 = v80;
        }
        v61 = *(_QWORD *)(v5 + 16);
        if ( v61 >= *(_QWORD *)(v5 + 24) )
        {
          v62 = v61 + 1;
          if ( v61 + 1 <= *(_QWORD *)(v5 + 24) )
          {
            updated = -1073741811;
LABEL_109:
            v41 = 1384;
LABEL_49:
            v42 = "Failed to append tag change information to array [%x]";
LABEL_50:
            LODWORD(v73) = updated;
            AslLogCallPrintf(1, "SdbpMergeFindLibraryEntries", v41, v42, v73);
            return (unsigned int)updated;
          }
          v63 = *(_QWORD *)(v5 + 32) - 1LL;
          if ( v62 + v63 < v62
            || !is_mul_ok(*(_QWORD *)(v5 + 24), *(_QWORD *)(v5 + 8))
            || (v64 = (v62 + v63) & ~v63,
                v65 = v64 * (unsigned __int128)*(unsigned __int64 *)(v5 + 8),
                v66 = v64 * *(_QWORD *)(v5 + 8),
                !is_mul_ok(v64, *(_QWORD *)(v5 + 8))) )
          {
            updated = -1073741675;
            goto LABEL_109;
          }
          v67 = *(void **)(v5 + 40);
          v68 = *(void **)v5;
          if ( v67 )
          {
            v70 = RtlReAllocateHeap(v68, DWORD2(v65), v67, v64 * *(_QWORD *)(v5 + 8));
          }
          else
          {
            v69 = RtlAllocateHeap(v68, DWORD2(v65), v64 * *(_QWORD *)(v5 + 8));
            v70 = v69;
            if ( v69 )
              memset_0(v69, 0, v66);
          }
          if ( !v70 )
          {
            updated = -1073741801;
            goto LABEL_109;
          }
          *(_QWORD *)(v5 + 40) = v70;
          *(_QWORD *)(v5 + 24) = v64;
        }
        if ( is_mul_ok(*(_QWORD *)(v5 + 8), v61) )
        {
          v71 = *(_QWORD *)(v5 + 40) + *(_QWORD *)(v5 + 8) * v61;
          if ( v71 >= *(_QWORD *)(v5 + 40) )
          {
            *(_OWORD *)v71 = v78;
            *(_OWORD *)(v71 + 16) = v55;
            *(_OWORD *)(v71 + 32) = v82;
            *(_QWORD *)(v71 + 48) = 0;
            ++*(_QWORD *)(v5 + 16);
LABEL_102:
            v13 = v76;
            v7 = a2;
            goto LABEL_103;
          }
        }
        updated = -1073741675;
        goto LABEL_109;
      }
      break;
    }
  }
  updated = SdbpMergeUpdateEntryIndexKeys((unsigned __int64 *)v5, a3, a1, v7, a4);
  if ( updated < 0 )
  {
    v42 = " failed to update indexes for the library items list [%x]";
    v41 = 1399;
    goto LABEL_50;
  }
  qsort(*(void **)(v5 + 40), *(_QWORD *)(v5 + 16), 0x38u, SdbpMergeCompareEntriesSort);
  return 0;
}

```

## disassembly

```asm
0x14001cd7c  mov     rax, rsp
0x14001cd7f  mov     [rax+20h], r9d
0x14001cd83  mov     [rax+18h], r8
0x14001cd87  mov     [rax+10h], rdx
0x14001cd8b  mov     [rax+8], rcx
0x14001cd8f  push    rbp
0x14001cd90  push    rbx
0x14001cd91  push    rsi
0x14001cd92  push    rdi
0x14001cd93  push    r12
0x14001cd95  push    r13
0x14001cd97  push    r14
0x14001cd99  push    r15
0x14001cd9b  lea     rbp, [rax-57h]
0x14001cd9f  sub     rsp, 0B8h
0x14001cda6  mov     rdi, [rbp+4Fh+arg_20]
0x14001cdaa  xorps   xmm0, xmm0
0x14001cdad  mov     r14, r8
0x14001cdb0  movaps  xmmword ptr [rax-58h], xmm6
0x14001cdb4  mov     rsi, rdx
0x14001cdb7  movaps  xmmword ptr [rax-68h], xmm7
0x14001cdbb  xor     edx, edx
0x14001cdbd  mov     r8d, 7001h
0x14001cdc3  movups  [rbp+4Fh+var_A0], xmm0
0x14001cdc7  mov     rbx, rcx
0x14001cdca  movups  [rbp+4Fh+var_90], xmm0
0x14001cdce  movups  [rbp+4Fh+var_80], xmm0
0x14001cdd2  call    SdbFindFirstTag
0x14001cdd7  xor     r15d, r15d
0x14001cdda  test    eax, eax
0x14001cddc  jz      loc_14001D466
0x14001cde2  mov     r8d, 7002h
0x14001cde8  mov     edx, eax
0x14001cdea  mov     rcx, rbx
0x14001cded  call    SdbFindFirstTag
0x14001cdf2  mov     [rbp+4Fh+var_C0], eax
0x14001cdf5  mov     r13d, eax
0x14001cdf8  test    eax, eax
0x14001cdfa  jz      short loc_14001CE0D
0x14001cdfc  mov     edx, eax
0x14001cdfe  mov     rcx, rbx
0x14001ce01  call    SdbGetFirstChild
0x14001ce06  mov     r12d, eax
0x14001ce09  test    eax, eax
0x14001ce0b  jnz     short loc_14001CE5B
0x14001ce0d  mov     rbx, [rdi+10h]
0x14001ce11  xor     edx, edx
0x14001ce13  mov     r8d, 7001h
0x14001ce19  mov     [rbp+4Fh+var_B8], rbx
0x14001ce1d  mov     rcx, rsi
0x14001ce20  call    SdbFindFirstTag
0x14001ce25  test    eax, eax
0x14001ce27  jz      loc_14001D466
0x14001ce2d  mov     r8d, 7002h
0x14001ce33  mov     edx, eax
0x14001ce35  mov     rcx, rsi
0x14001ce38  call    SdbFindFirstTag
0x14001ce3d  mov     [rbp+4Fh+var_C0], eax
0x14001ce40  test    eax, eax
0x14001ce42  jz      loc_14001D3FA
0x14001ce48  mov     edx, eax
0x14001ce4a  mov     rcx, rsi
0x14001ce4d  call    SdbGetFirstChild
0x14001ce52  jmp     loc_14001D3EF
0x14001ce57  mov     r14, [rbp+4Fh+arg_10]
0x14001ce5b  xorps   xmm6, xmm6
0x14001ce5e  xor     eax, eax
0x14001ce60  xorps   xmm7, xmm7
0x14001ce63  mov     [rbp+4Fh+var_B8], rax
0x14001ce67  mov     edx, r12d
0x14001ce6a  mov     rcx, rbx
0x14001ce6d  movups  [rbp+4Fh+var_A0], xmm6
0x14001ce71  movups  [rbp+4Fh+var_90], xmm6
0x14001ce75  movups  [rbp+4Fh+var_80], xmm7
0x14001ce79  call    SdbGetTagFromTagID
0x14001ce7e  mov     rcx, [r14+10h]
0x14001ce82  xor     r9d, r9d
0x14001ce85  mov     word ptr [rbp+4Fh+var_A0+0Ch], ax
0x14001ce89  movzx   r15d, ax
0x14001ce8d  mov     dword ptr [rbp+4Fh+var_A0], r12d
0x14001ce91  test    rcx, rcx
0x14001ce94  jz      loc_14001CF31
0x14001ce9a  mov     rsi, qword ptr [rbp+4Fh+var_90+8]
0x14001ce9e  mov     ebx, r9d
0x14001cea1  mov     r14, qword ptr [rbp+4Fh+var_90]
0x14001cea5  mov     rdi, [rbp+4Fh+arg_0]
0x14001cea9  mov     r13, [rbp+4Fh+arg_10]
0x14001cead  mov     rax, r9
0x14001ceb0  cmp     rbx, rcx
0x14001ceb3  jnb     short loc_14001CED2
0x14001ceb5  mov     rax, rbx
0x14001ceb8  mov     [rbp+4Fh+var_B0], r9
0x14001cebc  mul     qword ptr [r13+8]
0x14001cec0  test    rdx, rdx
0x14001cec3  jnz     short loc_14001CECF
0x14001cec5  add     rax, [r13+28h]
0x14001cec9  cmp     rax, [r13+28h]
0x14001cecd  jnb     short loc_14001CED2
0x14001cecf  mov     rax, r9
0x14001ced2  cmp     [rax+10h], r9d
0x14001ced6  jz      short loc_14001CF15
0x14001ced8  mov     r8, [rax]
0x14001cedb  cmp     [r8+4], r15w
0x14001cee0  jnz     short loc_14001CF15
0x14001cee2  movzx   r8d, word ptr [r8+6]
0x14001cee7  mov     edx, r12d
0x14001ceea  mov     rcx, rdi
0x14001ceed  call    SdbFindFirstTag
0x14001cef2  xor     r9d, r9d
0x14001cef5  test    eax, eax
0x14001cef7  jz      short loc_14001CF15
0x14001cef9  cmp     rbx, 40h ; '@'
0x14001cefd  jnb     short loc_14001CF09
0x14001ceff  bts     r14, rbx
0x14001cf03  mov     qword ptr [rbp+4Fh+var_90], r14
0x14001cf07  jmp     short loc_14001CF15
0x14001cf09  lea     rax, [rbx-40h]
0x14001cf0d  bts     rsi, rax
0x14001cf11  mov     qword ptr [rbp+4Fh+var_90+8], rsi
0x14001cf15  mov     rcx, [r13+10h]
0x14001cf19  inc     rbx
0x14001cf1c  cmp     rbx, rcx
0x14001cf1f  jb      short loc_14001CEAD
0x14001cf21  mov     rdi, [rbp+4Fh+arg_20]
0x14001cf25  mov     r13d, [rbp+4Fh+var_C0]
0x14001cf29  movups  xmm6, [rbp+4Fh+var_90]
0x14001cf2d  mov     rbx, [rbp+4Fh+arg_0]
0x14001cf31  mov     rax, r9
0x14001cf34  lea     rcx, qword_140039F70
0x14001cf3b  lea     r8, [rax+rax*4]
0x14001cf3f  cmp     [rcx+r8*2], r15w
0x14001cf44  jz      short loc_14001CF51
0x14001cf46  inc     rax
0x14001cf49  cmp     rax, 24h ; '$'
0x14001cf4d  jb      short loc_14001CF3B
0x14001cf4f  jmp     short loc_14001CF8A
0x14001cf51  movzx   r8d, word ptr [rcx+r8*2+2]
0x14001cf57  test    r8w, r8w
0x14001cf5b  jz      short loc_14001CF8A
0x14001cf5d  mov     edx, r12d
0x14001cf60  mov     rcx, rbx
0x14001cf63  call    SdbFindFirstTag
0x14001cf68  xor     r9d, r9d
0x14001cf6b  mov     dword ptr [rbp+4Fh+var_A0+8], eax
0x14001cf6e  test    eax, eax
0x14001cf70  jz      short loc_14001CF8A
0x14001cf72  xor     r8d, r8d
0x14001cf75  mov     edx, eax
0x14001cf77  mov     rcx, rbx
0x14001cf7a  call    SdbpTagToKey
0x14001cf7f  mov     qword ptr [rbp+4Fh+var_80], rax
0x14001cf83  xor     r9d, r9d
0x14001cf86  movups  xmm7, [rbp+4Fh+var_80]
0x14001cf8a  mov     r15, [rdi+10h]
0x14001cf8e  cmp     r15, [rdi+18h]
0x14001cf92  jb      loc_14001D041
0x14001cf98  lea     rcx, [r15+1]
0x14001cf9c  cmp     rcx, [rdi+18h]
0x14001cfa0  ja      short loc_14001CFAC
0x14001cfa2  mov     ebx, 0C000000Dh
0x14001cfa7  jmp     loc_14001D0A6
0x14001cfac  mov     rsi, [rdi+20h]
0x14001cfb0  dec     rsi
0x14001cfb3  lea     r8, [rsi+rcx]
0x14001cfb7  cmp     r8, rcx
0x14001cfba  jb      loc_14001D0A1
0x14001cfc0  mov     rax, [rdi+8]
0x14001cfc4  mul     qword ptr [rdi+18h]
0x14001cfc8  mov     [rbp+4Fh+var_B0], r9
0x14001cfcc  test    rdx, rdx
0x14001cfcf  jnz     loc_14001D0A1
0x14001cfd5  mov     rax, [rdi+8]
0x14001cfd9  not     rsi
0x14001cfdc  and     rsi, r8
0x14001cfdf  mov     [rbp+4Fh+var_B0], r9
0x14001cfe3  mul     rsi
0x14001cfe6  mov     r14, rax
0x14001cfe9  test    rdx, rdx
0x14001cfec  jnz     loc_14001D0A1
0x14001cff2  mov     r8, [rdi+28h]; Ptr
0x14001cff6  mov     rcx, [rdi]; Heap
0x14001cff9  test    r8, r8
0x14001cffc  jnz     short loc_14001D01E
0x14001cffe  mov     r8, rax; Size
0x14001d001  call    cs:__imp_RtlAllocateHeap
0x14001d007  mov     rbx, rax
0x14001d00a  test    rax, rax
0x14001d00d  jz      short loc_14001D02A
0x14001d00f  mov     r8, r14; Size
0x14001d012  xor     edx, edx; Val
0x14001d014  mov     rcx, rax; void *
0x14001d017  call    memset_0
0x14001d01c  jmp     short loc_14001D02A
0x14001d01e  mov     r9, r14; Size
0x14001d021  call    cs:__imp_RtlReAllocateHeap
0x14001d027  mov     rbx, rax
0x14001d02a  xor     r9d, r9d
0x14001d02d  test    rbx, rbx
0x14001d030  jnz     short loc_14001D039
0x14001d032  mov     ebx, 0C0000017h
0x14001d037  jmp     short loc_14001D0A6
0x14001d039  mov     [rdi+28h], rbx
0x14001d03d  mov     [rdi+18h], rsi
0x14001d041  mov     rax, r15
0x14001d044  mov     [rbp+4Fh+var_B0], r9
0x14001d048  mul     qword ptr [rdi+8]
0x14001d04c  test    rdx, rdx
0x14001d04f  jnz     short loc_14001D0AC
0x14001d051  add     rax, [rdi+28h]
0x14001d055  cmp     rax, [rdi+28h]
0x14001d059  jb      short loc_14001D0AC
0x14001d05b  movups  xmm0, [rbp+4Fh+var_A0]
0x14001d05f  movups  xmmword ptr [rax], xmm0
0x14001d062  movsd   xmm0, [rbp+4Fh+var_B8]
0x14001d067  movups  xmmword ptr [rax+10h], xmm6
0x14001d06b  movups  xmmword ptr [rax+20h], xmm7
0x14001d06f  movsd   qword ptr [rax+30h], xmm0
0x14001d074  inc     qword ptr [rdi+10h]
0x14001d078  mov     rbx, [rbp+4Fh+arg_0]
0x14001d07c  mov     r8d, r12d
0x14001d07f  mov     rcx, rbx
0x14001d082  mov     edx, r13d
0x14001d085  call    SdbGetNextChild
0x14001d08a  xor     r15d, r15d
0x14001d08d  mov     r12d, eax
0x14001d090  test    eax, eax
0x14001d092  jnz     loc_14001CE57
0x14001d098  mov     rsi, [rbp+4Fh+arg_8]
0x14001d09c  jmp     loc_14001CE0D
0x14001d0a1  mov     ebx, 0C0000095h
0x14001d0a6  test    ebx, ebx
0x14001d0a8  js      short loc_14001D0B1
0x14001d0aa  jmp     short loc_14001D078
0x14001d0ac  mov     ebx, 0C0000095h
0x14001d0b1  mov     r8d, 500h
0x14001d0b7  lea     r9, aFailedToAppend_0; "Failed to append tag change information"...
0x14001d0be  lea     rdx, aSdbpmergefindl; "SdbpMergeFindLibraryEntries"
0x14001d0c5  mov     dword ptr [rsp+0F0h+var_D0], ebx
0x14001d0c9  mov     ecx, 1
0x14001d0ce  call    AslLogCallPrintf
0x14001d0d3  mov     eax, ebx
0x14001d0d5  jmp     loc_14001D46B
0x14001d0da  mov     edx, r12d
0x14001d0dd  mov     rcx, rsi
0x14001d0e0  call    SdbGetTagFromTagID
0x14001d0e5  movzx   r13d, ax
0x14001d0e9  mov     rcx, r15
0x14001d0ec  lea     rax, qword_140039F70
0x14001d0f3  lea     rdx, [rcx+rcx*4]
0x14001d0f7  cmp     [rax+rdx*2], r13w
0x14001d0fc  jz      short loc_14001D10C
0x14001d0fe  inc     rcx
0x14001d101  cmp     rcx, 24h ; '$'
0x14001d105  jb      short loc_14001D0F3
0x14001d107  jmp     loc_14001D3E1
0x14001d10c  movzx   r8d, word ptr [rax+rdx*2+2]
0x14001d112  test    r8w, r8w
0x14001d116  jz      loc_14001D3E1
0x14001d11c  mov     edx, r12d
0x14001d11f  mov     rcx, rsi
0x14001d122  call    SdbFindFirstTag
0x14001d127  mov     r14d, eax
0x14001d12a  test    eax, eax
0x14001d12c  jnz     short loc_14001D154
0x14001d12e  lea     r9, aSkippingMergeT; "Skipping merge tagid 0x%X as the entry "...
0x14001d135  mov     dword ptr [rsp+0F0h+var_D0], r12d
0x14001d13a  mov     r8d, 527h
0x14001d140  lea     rdx, aSdbpmergefindl; "SdbpMergeFindLibraryEntries"
0x14001d147  lea     ecx, [rax+3]
0x14001d14a  call    AslLogCallPrintf
0x14001d14f  jmp     loc_14001D3E1
0x14001d154  xor     r8d, r8d
0x14001d157  mov     edx, r14d
0x14001d15a  mov     rcx, rsi
0x14001d15d  call    SdbpTagToKey
0x14001d162  xor     r9d, r9d
0x14001d165  mov     r15, rax
0x14001d168  test    rax, rax
0x14001d16b  jnz     short loc_14001D1B0
0x14001d16d  lea     r8d, [rax+1]
0x14001d171  mov     edx, r14d
0x14001d174  mov     rcx, rsi
0x14001d177  call    SdbpTagToKey
0x14001d17c  cmp     rax, 1
0x14001d180  jnz     short loc_14001D1AD
0x14001d182  mov     [rsp+0F0h+var_C8], r14d
0x14001d187  lea     r9, aSkippingMergeO; "Skipping merge of tagid 0x%X. The entry"...
0x14001d18e  mov     r8d, 52Fh
0x14001d194  mov     dword ptr [rsp+0F0h+var_D0], r12d
0x14001d199  lea     rdx, aSdbpmergefindl; "SdbpMergeFindLibraryEntries"
0x14001d1a0  lea     ecx, [rax+2]
0x14001d1a3  call    AslLogCallPrintf
0x14001d1a8  jmp     loc_14001D3DE
0x14001d1ad  xor     r9d, r9d
0x14001d1b0  mov     rsi, r9
0x14001d1b3  test    rbx, rbx
0x14001d1b6  jz      short loc_14001D221
0x14001d1b8  mov     rbx, r9
0x14001d1bb  cmp     rsi, [rdi+10h]
0x14001d1bf  jnb     short loc_14001D1E1
  ... truncated ...
```
