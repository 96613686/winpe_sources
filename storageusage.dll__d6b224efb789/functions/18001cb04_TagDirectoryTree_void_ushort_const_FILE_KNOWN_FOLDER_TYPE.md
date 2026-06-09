# TagDirectoryTree(void *,ushort const *,_FILE_KNOWN_FOLDER_TYPE)

- ea: `0x18001cb04`
- end: `0x18001d019`
- name: `?TagDirectoryTree@@YAJPEAXPEBGW4_FILE_KNOWN_FOLDER_TYPE@@@Z`
- size: `1301`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x18001d020`

## callees

- `0x1800050f0`
- `0x180005c94`
- `0x18000eab8`
- `0x1800152d4`
- `0x180015bac`
- `0x180016f30`
- `0x180017c34`
- `0x180019de0`
- `0x18001c940`
- `0x18001ca14`
- `0x18001cb04`
- `0x18001ec30`
- `0x18001f76c`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18001cd8a`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18001ce7c`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18001cd8a`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18001ce7c`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18001cea8`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18001cea8`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x18001cdfa`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x18001cdfa`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18001cfa0`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18001cfa0`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001cfb1`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001cfdb`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001cfb1`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001cfdb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TagDirectoryTree(void *a1, const unsigned __int16 *a2, unsigned int a3)
{
  unsigned __int64 v6; // rdx
  int v7; // eax
  unsigned int v8; // ebx
  int v9; // edi
  __int64 v10; // r8
  __int64 v11; // rdx
  __int64 v12; // r14
  __int64 v13; // rbx
  __int64 v14; // rcx
  _OWORD *v15; // rcx
  wchar_t *v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rdx
  _OWORD *v19; // rax
  wchar_t *v20; // rcx
  __int64 v21; // r8
  int v22; // r15d
  HANDLE FirstFile; // rsi
  __int64 v24; // r8
  __int64 v25; // rdx
  __int64 v26; // r14
  __int64 v27; // rbx
  __int64 v28; // rcx
  _OWORD *v29; // rcx
  WCHAR *v30; // rax
  __int64 v31; // rdx
  int lpSearchFilter; // [rsp+20h] [rbp-E0h]
  _BYTE v34[8]; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v35; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v36; // [rsp+48h] [rbp-B8h]
  __int64 v37; // [rsp+58h] [rbp-A8h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+70h] [rbp-90h] BYREF
  wchar_t Source[264]; // [rsp+2C0h] [rbp+1C0h] BYREF
  WCHAR pszPathOut[264]; // [rsp+4D0h] [rbp+3D0h] BYREF
  WCHAR FileName[264]; // [rsp+6E0h] [rbp+5E0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+938h] [rbp+838h]

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v35 = 0;
  v36 = 0;
  v37 = 0;
  std::_Container_base12::_Alloc_proxy<std::allocator<std::_Container_proxy>>(&v35);
  memset_0(Source, 0, 0x208u);
  v7 = StringCbCopyW(Source, v6, a2);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v9 = 0;
    v10 = v37;
    v11 = v36;
    if ( (unsigned __int64)v36 <= v37 + 1 )
    {
      std::deque__TagDirectoryTree_::_2_::DirQueItem_std::allocator__TagDirectoryTree_::_2_::DirQueItem___::_Growmap(&v35);
      v10 = v37;
      v11 = v36;
    }
    *((_QWORD *)&v36 + 1) &= v11 - 1;
    v12 = *((_QWORD *)&v36 + 1) + v10;
    v13 = (v11 - 1) & (*((_QWORD *)&v36 + 1) + v10);
    v14 = *((_QWORD *)&v35 + 1);
    if ( !*(_QWORD *)(*((_QWORD *)&v35 + 1) + 8 * v13) )
    {
      *(_QWORD *)(*((_QWORD *)&v35 + 1) + 8 * v13) = std::_Allocate<16,std::_Default_allocate_traits>(520);
      v11 = v36;
      v14 = *((_QWORD *)&v35 + 1);
    }
    v15 = *(_OWORD **)(v14 + 8 * (v12 & (v11 - 1)));
    v16 = Source;
    v17 = 4;
    do
    {
      *v15 = *(_OWORD *)v16;
      v15[1] = *((_OWORD *)v16 + 1);
      v15[2] = *((_OWORD *)v16 + 2);
      v15[3] = *((_OWORD *)v16 + 3);
      v15[4] = *((_OWORD *)v16 + 4);
      v15[5] = *((_OWORD *)v16 + 5);
      v15[6] = *((_OWORD *)v16 + 6);
      v15[7] = *((_OWORD *)v16 + 7);
      v15 += 8;
      v16 += 64;
      --v17;
    }
    while ( v17 );
    *(_QWORD *)v15 = *(_QWORD *)v16;
    ++v37;
LABEL_10:
    while ( v37 )
    {
      if ( IsTaskCancelled(a1) )
      {
        v9 = -2147023673;
        break;
      }
      v18 = *((_QWORD *)&v36 + 1);
      v19 = *(_OWORD **)(*((_QWORD *)&v35 + 1) + 8 * (*((_QWORD *)&v36 + 1) & (v36 - 1)));
      v20 = Source;
      v21 = 4;
      do
      {
        *(_OWORD *)v20 = *v19;
        *((_OWORD *)v20 + 1) = v19[1];
        *((_OWORD *)v20 + 2) = v19[2];
        *((_OWORD *)v20 + 3) = v19[3];
        *((_OWORD *)v20 + 4) = v19[4];
        *((_OWORD *)v20 + 5) = v19[5];
        *((_OWORD *)v20 + 6) = v19[6];
        *((_OWORD *)v20 + 7) = v19[7];
        v20 += 64;
        v19 += 8;
        --v21;
      }
      while ( v21 );
      *(_QWORD *)v20 = *(_QWORD *)v19;
      if ( --v37 )
        *((_QWORD *)&v36 + 1) = v18 + 1;
      else
        *((_QWORD *)&v36 + 1) = 0;
      v34[0] = 0;
      if ( (int)IsDirectoryTagged(Source, a3, v34) >= 0 && !v34[0] )
        TagDirectory(Source, a3);
      v22 = wcsnlen(Source, 0x104u);
      if ( (unsigned int)(v22 + 3) <= 0x104 )
      {
        memset_0(FileName, 0, 0x208u);
        if ( StringCchPrintfW(FileName, 0x104u, L"%s\\*", Source) >= 0 )
        {
          FirstFile = FindFirstFileExW(FileName, FindExInfoBasic, &FindFileData, FindExSearchLimitToDirectories, 0, 2u);
          if ( FirstFile != (HANDLE)-1LL )
          {
            while ( !IsTaskCancelled(a1) )
            {
              if ( (FindFileData.cFileName[0] != 46
                 || FindFileData.cFileName[1] && (FindFileData.cFileName[1] != 46 || FindFileData.cFileName[2]))
                && (FindFileData.dwFileAttributes & 0x10) != 0
                && (FindFileData.dwFileAttributes & 0x400) == 0 )
              {
                memset_0(pszPathOut, 0, 0x208u);
                if ( v22 + (unsigned int)wcsnlen(FindFileData.cFileName, 0x104u) + 1 <= 0x104
                  && PathCchCombine(pszPathOut, 0x208u, Source, FindFileData.cFileName) >= 0 )
                {
                  v24 = v37;
                  v25 = v36;
                  if ( (unsigned __int64)v36 <= v37 + 1 )
                  {
                    std::deque__TagDirectoryTree_::_2_::DirQueItem_std::allocator__TagDirectoryTree_::_2_::DirQueItem___::_Growmap(&v35);
                    v24 = v37;
                    v25 = v36;
                  }
                  *((_QWORD *)&v36 + 1) &= v25 - 1;
                  v26 = *((_QWORD *)&v36 + 1) + v24;
                  v27 = (v25 - 1) & (*((_QWORD *)&v36 + 1) + v24);
                  v28 = *((_QWORD *)&v35 + 1);
                  if ( !*(_QWORD *)(*((_QWORD *)&v35 + 1) + 8 * v27) )
                  {
                    *(_QWORD *)(*((_QWORD *)&v35 + 1) + 8 * v27) = std::_Allocate<16,std::_Default_allocate_traits>(520);
                    v25 = v36;
                    v28 = *((_QWORD *)&v35 + 1);
                  }
                  v29 = *(_OWORD **)(v28 + 8 * (v26 & (v25 - 1)));
                  v30 = pszPathOut;
                  v31 = 4;
                  do
                  {
                    *v29 = *(_OWORD *)v30;
                    v29[1] = *((_OWORD *)v30 + 1);
                    v29[2] = *((_OWORD *)v30 + 2);
                    v29[3] = *((_OWORD *)v30 + 3);
                    v29[4] = *((_OWORD *)v30 + 4);
                    v29[5] = *((_OWORD *)v30 + 5);
                    v29[6] = *((_OWORD *)v30 + 6);
                    v29[7] = *((_OWORD *)v30 + 7);
                    v29 += 8;
                    v30 += 64;
                    --v31;
                  }
                  while ( v31 );
                  *(_QWORD *)v29 = *(_QWORD *)v30;
                  ++v37;
                }
              }
              if ( !FindNextFileW(FirstFile, &FindFileData) )
              {
                FindClose(FirstFile);
                goto LABEL_10;
              }
            }
            v9 = -2147023673;
            FindClose(FirstFile);
            break;
          }
        }
      }
    }
    v8 = v9;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB9C,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\storageusage\\storagegrovelerscans.cpp",
      (const char *)(unsigned int)v7,
      lpSearchFilter);
  }
  std::deque__TagDirectoryTree_::_2_::DirQueItem_std::allocator__TagDirectoryTree_::_2_::DirQueItem___::_deque__TagDirectoryTree_::_2_::DirQueItem_std::allocator__TagDirectoryTree_::_2_::DirQueItem___(&v35);
  return v8;
}

```

## disassembly

```asm
0x18001cb04  mov     [rsp-8+arg_18], rbx
0x18001cb09  push    rbp
0x18001cb0a  push    rsi
0x18001cb0b  push    rdi
0x18001cb0c  push    r12
0x18001cb0e  push    r13
0x18001cb10  push    r14
0x18001cb12  push    r15
0x18001cb14  lea     rbp, [rsp-800h]
0x18001cb1c  sub     rsp, 900h
0x18001cb23  mov     rax, cs:__security_cookie
0x18001cb2a  xor     rax, rsp
0x18001cb2d  mov     [rbp+830h+var_40], rax
0x18001cb34  mov     r13d, r8d
0x18001cb37  mov     rbx, rdx
0x18001cb3a  mov     r12, rcx
0x18001cb3d  xor     edx, edx; Val
0x18001cb3f  mov     r8d, 250h; Size
0x18001cb45  lea     rcx, [rsp+930h+FindFileData]; void *
0x18001cb4a  call    memset_0
0x18001cb4f  xorps   xmm0, xmm0
0x18001cb52  movdqu  [rsp+930h+var_8F8], xmm0
0x18001cb58  xorps   xmm1, xmm1
0x18001cb5b  movdqu  [rsp+930h+var_8E8], xmm1
0x18001cb61  xor     r15d, r15d
0x18001cb64  mov     [rsp+930h+var_8D8], r15
0x18001cb69  lea     rcx, [rsp+930h+var_8F8]
0x18001cb6e  call    ??$_Alloc_proxy@V?$allocator@U_Container_proxy@std@@@std@@@_Container_base12@std@@QEAAX$$QEAV?$allocator@U_Container_proxy@std@@@1@@Z; std::_Container_base12::_Alloc_proxy<std::allocator<std::_Container_proxy>>(std::allocator<std::_Container_proxy> &&)
0x18001cb73  nop
0x18001cb74  xor     edx, edx; Val
0x18001cb76  mov     r8d, 208h; Size
0x18001cb7c  lea     rcx, [rbp+830h+Source]; void *
0x18001cb83  call    memset_0
0x18001cb88  mov     r8, rbx; unsigned __int16 *
0x18001cb8b  lea     rcx, [rbp+830h+Source]; unsigned __int16 *
0x18001cb92  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18001cb97  mov     ebx, eax
0x18001cb99  test    eax, eax
0x18001cb9b  jns     short loc_18001CBBD
0x18001cb9d  mov     rcx, [rbp+838h]; this
0x18001cba4  mov     r9d, eax; char *
0x18001cba7  lea     r8, aOnecoreDrivers; "onecore\\drivers\\storage\\storsvc\\sto"...
0x18001cbae  mov     edx, 0B9Ch; void *
0x18001cbb3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cbb8  jmp     loc_18001CFE3
0x18001cbbd  mov     edi, r15d
0x18001cbc0  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001cbc4  mov     r8, [rsp+930h+var_8D8]
0x18001cbc9  lea     rax, [r8+1]
0x18001cbcd  mov     rdx, qword ptr [rsp+930h+var_8E8]
0x18001cbd2  cmp     rdx, rax
0x18001cbd5  ja      short loc_18001CBEB
0x18001cbd7  lea     rcx, [rsp+930h+var_8F8]
0x18001cbdc  call    std__deque__TagDirectoryTree____2___DirQueItem_std__allocator__TagDirectoryTree____2___DirQueItem______Growmap
0x18001cbe1  mov     r8, [rsp+930h+var_8D8]
0x18001cbe6  mov     rdx, qword ptr [rsp+930h+var_8E8]
0x18001cbeb  lea     rcx, [rdx-1]
0x18001cbef  mov     rax, qword ptr [rsp+930h+var_8E8+8]
0x18001cbf4  and     rax, rcx
0x18001cbf7  mov     qword ptr [rsp+930h+var_8E8+8], rax
0x18001cbfc  lea     r14, [rax+r8]
0x18001cc00  mov     rbx, r14
0x18001cc03  and     rbx, rcx
0x18001cc06  mov     rcx, qword ptr [rsp+930h+var_8F8+8]
0x18001cc0b  cmp     [rcx+rbx*8], r15
0x18001cc0f  jnz     short loc_18001CC2E
0x18001cc11  mov     ecx, 208h
0x18001cc16  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18001cc1b  mov     rcx, qword ptr [rsp+930h+var_8F8+8]
0x18001cc20  mov     [rcx+rbx*8], rax
0x18001cc24  mov     rdx, qword ptr [rsp+930h+var_8E8]
0x18001cc29  mov     rcx, qword ptr [rsp+930h+var_8F8+8]
0x18001cc2e  lea     rax, [rdx-1]
0x18001cc32  and     rax, r14
0x18001cc35  mov     rcx, [rcx+rax*8]
0x18001cc39  lea     rax, [rbp+830h+Source]
0x18001cc40  mov     edx, 4
0x18001cc45  lea     r15d, [rdx+7Ch]
0x18001cc49  movups  xmm0, xmmword ptr [rax]
0x18001cc4c  movups  xmmword ptr [rcx], xmm0
0x18001cc4f  movups  xmm1, xmmword ptr [rax+10h]
0x18001cc53  movups  xmmword ptr [rcx+10h], xmm1
0x18001cc57  movups  xmm0, xmmword ptr [rax+20h]
0x18001cc5b  movups  xmmword ptr [rcx+20h], xmm0
0x18001cc5f  movups  xmm1, xmmword ptr [rax+30h]
0x18001cc63  movups  xmmword ptr [rcx+30h], xmm1
0x18001cc67  movups  xmm0, xmmword ptr [rax+40h]
0x18001cc6b  movups  xmmword ptr [rcx+40h], xmm0
0x18001cc6f  movups  xmm1, xmmword ptr [rax+50h]
0x18001cc73  movups  xmmword ptr [rcx+50h], xmm1
0x18001cc77  movups  xmm0, xmmword ptr [rax+60h]
0x18001cc7b  movups  xmmword ptr [rcx+60h], xmm0
0x18001cc7f  movups  xmm1, xmmword ptr [rax+70h]
0x18001cc83  movups  xmmword ptr [rcx+70h], xmm1
0x18001cc87  add     rcx, r15
0x18001cc8a  add     rax, r15
0x18001cc8d  sub     rdx, 1
0x18001cc91  jnz     short loc_18001CC49
0x18001cc93  mov     rax, [rax]
0x18001cc96  mov     [rcx], rax
0x18001cc99  inc     [rsp+930h+var_8D8]
0x18001cc9e  xor     ebx, ebx
0x18001cca0  mov     r14d, 104h
0x18001cca6  cmp     [rsp+930h+var_8D8], rbx
0x18001ccab  jz      loc_18001CFD2
0x18001ccb1  mov     rcx, r12; void *
0x18001ccb4  call    ?IsTaskCancelled@@YA_NPEAX@Z; IsTaskCancelled(void *)
0x18001ccb9  test    al, al
0x18001ccbb  jnz     loc_18001CFCD
0x18001ccc1  mov     rdx, qword ptr [rsp+930h+var_8E8+8]
0x18001ccc6  mov     rcx, qword ptr [rsp+930h+var_8E8]
0x18001cccb  dec     rcx
0x18001ccce  and     rcx, rdx
0x18001ccd1  mov     rax, qword ptr [rsp+930h+var_8F8+8]
0x18001ccd6  mov     rax, [rax+rcx*8]
0x18001ccda  lea     rcx, [rbp+830h+Source]
0x18001cce1  mov     r8d, 4
0x18001cce7  movups  xmm0, xmmword ptr [rax]
0x18001ccea  movups  xmmword ptr [rcx], xmm0
0x18001cced  movups  xmm1, xmmword ptr [rax+10h]
0x18001ccf1  movups  xmmword ptr [rcx+10h], xmm1
0x18001ccf5  movups  xmm0, xmmword ptr [rax+20h]
0x18001ccf9  movups  xmmword ptr [rcx+20h], xmm0
0x18001ccfd  movups  xmm1, xmmword ptr [rax+30h]
0x18001cd01  movups  xmmword ptr [rcx+30h], xmm1
0x18001cd05  movups  xmm0, xmmword ptr [rax+40h]
0x18001cd09  movups  xmmword ptr [rcx+40h], xmm0
0x18001cd0d  movups  xmm1, xmmword ptr [rax+50h]
0x18001cd11  movups  xmmword ptr [rcx+50h], xmm1
0x18001cd15  movups  xmm0, xmmword ptr [rax+60h]
0x18001cd19  movups  xmmword ptr [rcx+60h], xmm0
0x18001cd1d  movups  xmm1, xmmword ptr [rax+70h]
0x18001cd21  movups  xmmword ptr [rcx+70h], xmm1
0x18001cd25  add     rcx, r15
0x18001cd28  add     rax, r15
0x18001cd2b  sub     r8, 1
0x18001cd2f  jnz     short loc_18001CCE7
0x18001cd31  mov     rax, [rax]
0x18001cd34  mov     [rcx], rax
0x18001cd37  sub     [rsp+930h+var_8D8], 1
0x18001cd3d  jnz     short loc_18001CD46
0x18001cd3f  mov     qword ptr [rsp+930h+var_8E8+8], rbx
0x18001cd44  jmp     short loc_18001CD4F
0x18001cd46  lea     rax, [rdx+1]
0x18001cd4a  mov     qword ptr [rsp+930h+var_8E8+8], rax
0x18001cd4f  mov     [rsp+930h+var_900], bl
0x18001cd53  lea     r8, [rsp+930h+var_900]
0x18001cd58  mov     edx, r13d
0x18001cd5b  lea     rcx, [rbp+830h+Source]
0x18001cd62  call    ?IsDirectoryTagged@@YAJPEBGW4_FILE_KNOWN_FOLDER_TYPE@@AEA_N@Z; IsDirectoryTagged(ushort const *,_FILE_KNOWN_FOLDER_TYPE,bool &)
0x18001cd67  test    eax, eax
0x18001cd69  js      short loc_18001CD80
0x18001cd6b  cmp     [rsp+930h+var_900], bl
0x18001cd6f  jnz     short loc_18001CD80
0x18001cd71  mov     edx, r13d
0x18001cd74  lea     rcx, [rbp+830h+Source]
0x18001cd7b  call    ?TagDirectory@@YAJPEBGW4_FILE_KNOWN_FOLDER_TYPE@@@Z; TagDirectory(ushort const *,_FILE_KNOWN_FOLDER_TYPE)
0x18001cd80  mov     rdx, r14; MaxCount
0x18001cd83  lea     rcx, [rbp+830h+Source]; Source
0x18001cd8a  call    cs:__imp_wcsnlen
0x18001cd90  mov     r15, rax
0x18001cd93  lea     ecx, [rax+3]
0x18001cd96  cmp     ecx, r14d
0x18001cd99  ja      loc_18001CFBB
0x18001cd9f  xor     edx, edx; Val
0x18001cda1  mov     r8d, 208h; Size
0x18001cda7  lea     rcx, [rbp+830h+FileName]; void *
0x18001cdae  call    memset_0
0x18001cdb3  lea     r9, [rbp+830h+Source]
0x18001cdba  lea     r8, aS_0; "%s\\*"
0x18001cdc1  mov     rdx, r14; unsigned __int64
0x18001cdc4  lea     rcx, [rbp+830h+FileName]; unsigned __int16 *
0x18001cdcb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001cdd0  test    eax, eax
0x18001cdd2  js      loc_18001CFBB
0x18001cdd8  mov     [rsp+930h+dwAdditionalFlags], 2; dwAdditionalFlags
0x18001cde0  mov     [rsp+930h+lpSearchFilter], rbx; lpSearchFilter
0x18001cde5  mov     r9d, 1; fSearchOp
0x18001cdeb  lea     r8, [rsp+930h+FindFileData]; lpFindFileData
0x18001cdf0  mov     edx, r9d; fInfoLevelId
0x18001cdf3  lea     rcx, [rbp+830h+FileName]; lpFileName
0x18001cdfa  call    cs:__imp_FindFirstFileExW
0x18001ce00  mov     rsi, rax
0x18001ce03  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001ce07  jz      loc_18001CFBB
0x18001ce0d  mov     rcx, r12; void *
0x18001ce10  call    ?IsTaskCancelled@@YA_NPEAX@Z; IsTaskCancelled(void *)
0x18001ce15  test    al, al
0x18001ce17  jnz     loc_18001CFC6
0x18001ce1d  movzx   eax, [rbp+830h+var_892]
0x18001ce21  cmp     [rbp+830h+pszMore], 2Eh ; '.'
0x18001ce26  jnz     short loc_18001CE48
0x18001ce28  test    ax, ax
0x18001ce2b  jz      loc_18001CF98
0x18001ce31  cmp     [rbp+830h+pszMore], 2Eh ; '.'
0x18001ce36  jnz     short loc_18001CE48
0x18001ce38  cmp     ax, 2Eh ; '.'
0x18001ce3c  jnz     short loc_18001CE48
0x18001ce3e  cmp     [rbp+830h+var_890], bx
0x18001ce42  jz      loc_18001CF98
0x18001ce48  test    byte ptr [rsp+930h+FindFileData], 10h
0x18001ce4d  jz      loc_18001CF98
0x18001ce53  test    [rsp+930h+FindFileData], 400h
0x18001ce5b  jnz     loc_18001CF98
0x18001ce61  xor     edx, edx; Val
0x18001ce63  mov     r8d, 208h; Size
0x18001ce69  lea     rcx, [rbp+830h+pszPathOut]; void *
0x18001ce70  call    memset_0
0x18001ce75  mov     rdx, r14; MaxCount
0x18001ce78  lea     rcx, [rbp+830h+pszMore]; Source
0x18001ce7c  call    cs:__imp_wcsnlen
0x18001ce82  lea     ecx, [rax+1]
0x18001ce85  add     ecx, r15d
0x18001ce88  cmp     ecx, r14d
0x18001ce8b  ja      loc_18001CF98
0x18001ce91  lea     r9, [rbp+830h+pszMore]; pszMore
0x18001ce95  lea     r8, [rbp+830h+Source]; pszPathIn
0x18001ce9c  mov     edx, 208h; cchPathOut
0x18001cea1  lea     rcx, [rbp+830h+pszPathOut]; pszPathOut
0x18001cea8  call    cs:__imp_PathCchCombine
0x18001ceae  test    eax, eax
0x18001ceb0  js      loc_18001CF98
0x18001ceb6  mov     r8, [rsp+930h+var_8D8]
0x18001cebb  lea     rax, [r8+1]
0x18001cebf  mov     rdx, qword ptr [rsp+930h+var_8E8]
0x18001cec4  cmp     rdx, rax
0x18001cec7  ja      short loc_18001CEDD
0x18001cec9  lea     rcx, [rsp+930h+var_8F8]
0x18001cece  call    std__deque__TagDirectoryTree____2___DirQueItem_std__allocator__TagDirectoryTree____2___DirQueItem______Growmap
0x18001ced3  mov     r8, [rsp+930h+var_8D8]
0x18001ced8  mov     rdx, qword ptr [rsp+930h+var_8E8]
0x18001cedd  lea     rcx, [rdx-1]
0x18001cee1  mov     rax, qword ptr [rsp+930h+var_8E8+8]
0x18001cee6  and     rax, rcx
0x18001cee9  mov     qword ptr [rsp+930h+var_8E8+8], rax
0x18001ceee  lea     r14, [rax+r8]
0x18001cef2  mov     rbx, r14
0x18001cef5  and     rbx, rcx
0x18001cef8  mov     rcx, qword ptr [rsp+930h+var_8F8+8]
0x18001cefd  cmp     [rcx+rbx*8], rdi
0x18001cf01  jnz     short loc_18001CF20
0x18001cf03  mov     ecx, 208h
0x18001cf08  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18001cf0d  mov     rcx, qword ptr [rsp+930h+var_8F8+8]
0x18001cf12  mov     [rcx+rbx*8], rax
0x18001cf16  mov     rdx, qword ptr [rsp+930h+var_8E8]
0x18001cf1b  mov     rcx, qword ptr [rsp+930h+var_8F8+8]
0x18001cf20  lea     rax, [rdx-1]
0x18001cf24  and     rax, r14
0x18001cf27  mov     rcx, [rcx+rax*8]
0x18001cf2b  lea     rax, [rbp+830h+pszPathOut]
0x18001cf32  mov     edx, 4
0x18001cf37  lea     r8d, [rdx+7Ch]
0x18001cf3b  movups  xmm0, xmmword ptr [rax]
0x18001cf3e  movups  xmmword ptr [rcx], xmm0
0x18001cf41  movups  xmm1, xmmword ptr [rax+10h]
0x18001cf45  movups  xmmword ptr [rcx+10h], xmm1
0x18001cf49  movups  xmm0, xmmword ptr [rax+20h]
0x18001cf4d  movups  xmmword ptr [rcx+20h], xmm0
0x18001cf51  movups  xmm1, xmmword ptr [rax+30h]
0x18001cf55  movups  xmmword ptr [rcx+30h], xmm1
0x18001cf59  movups  xmm0, xmmword ptr [rax+40h]
0x18001cf5d  movups  xmmword ptr [rcx+40h], xmm0
0x18001cf61  movups  xmm1, xmmword ptr [rax+50h]
0x18001cf65  movups  xmmword ptr [rcx+50h], xmm1
0x18001cf69  movups  xmm0, xmmword ptr [rax+60h]
0x18001cf6d  movups  xmmword ptr [rcx+60h], xmm0
0x18001cf71  movups  xmm1, xmmword ptr [rax+70h]
0x18001cf75  movups  xmmword ptr [rcx+70h], xmm1
0x18001cf79  add     rcx, r8
0x18001cf7c  add     rax, r8
0x18001cf7f  sub     rdx, 1
0x18001cf83  jnz     short loc_18001CF3B
0x18001cf85  mov     rax, [rax]
0x18001cf88  mov     [rcx], rax
0x18001cf8b  inc     [rsp+930h+var_8D8]
0x18001cf90  xor     ebx, ebx
0x18001cf92  mov     r14d, 104h
0x18001cf98  lea     rdx, [rsp+930h+FindFileData]; lpFindFileData
0x18001cf9d  mov     rcx, rsi; hFindFile
0x18001cfa0  call    cs:__imp_FindNextFileW
0x18001cfa6  test    eax, eax
0x18001cfa8  jnz     loc_18001CE0D
0x18001cfae  mov     rcx, rsi; hFindFile
0x18001cfb1  call    cs:__imp_FindClose
0x18001cfb7  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001cfbb  mov     r15d, 80h
0x18001cfc1  jmp     loc_18001CCA6
0x18001cfc6  mov     edi, 800704C7h
0x18001cfcb  jmp     short loc_18001CFD8
0x18001cfcd  mov     edi, 800704C7h
0x18001cfd2  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18001cfd6  jz      short loc_18001CFE1
0x18001cfd8  mov     rcx, rsi; hFindFile
0x18001cfdb  call    cs:__imp_FindClose
0x18001cfe1  mov     ebx, edi
0x18001cfe3  lea     rcx, [rsp+930h+var_8F8]
0x18001cfe8  call    std__deque__TagDirectoryTree____2___DirQueItem_std__allocator__TagDirectoryTree____2___DirQueItem______deque__TagDirectoryTree____2___DirQueItem_std__allocator__TagDirectoryTree____2___DirQueItem___
0x18001cfed  mov     eax, ebx
0x18001cfef  mov     rcx, [rbp+830h+var_40]
  ... truncated ...
```
