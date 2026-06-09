# CWABStorage::DeleteRecord(_SBinary *)

- ea: `0x180040930`
- end: `0x180040e25`
- name: `?DeleteRecord@CWABStorage@@UEAAJPEAU_SBinary@@@Z`
- size: `1269`
- prototype: `__int64 __fastcall(CWABStorage *__hidden this, struct _SBinary *)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800189ec`
- `0x1800301e8`
- `0x180030300`
- `0x180030ec0`
- `0x180031618`
- `0x180032200`
- `0x1800323b8`
- `0x180032588`
- `0x180032704`
- `0x180032fd8`
- `0x180040930`
- `0x18004273c`
- `0x180043f98`
- `0x180091ef0`

## import_xrefs

- `KERNEL32!ReleaseMutex` at `0x180040df6`
- `KERNEL32!ReleaseMutex` at `0x180040df6`
- `KERNEL32!SetFilePointer` at `0x180040b4c`
- `KERNEL32!SetFilePointer` at `0x180040c47`
- `KERNEL32!SetFilePointer` at `0x180040d18`
- `KERNEL32!SetFilePointer` at `0x180040b4c`
- `KERNEL32!SetFilePointer` at `0x180040c47`
- `KERNEL32!SetFilePointer` at `0x180040d18`
- `KERNEL32!WriteFile` at `0x180040b8f`
- `KERNEL32!WriteFile` at `0x180040c90`
- `KERNEL32!WriteFile` at `0x180040d89`
- `KERNEL32!WriteFile` at `0x180040b8f`
- `KERNEL32!WriteFile` at `0x180040c90`
- `KERNEL32!WriteFile` at `0x180040d89`
- `KERNEL32!CloseHandle` at `0x180040de3`
- `KERNEL32!CloseHandle` at `0x180040de3`

## pseudocode

```c
__int64 __fastcall CWABStorage::DeleteRecord(CWABStorage *this, struct _SBinary *a2)
{
  HANDLE v2; // rsi
  int v3; // r14d
  struct _SBinary *v4; // rbx
  void **v6; // r8
  unsigned int v7; // r15d
  __int64 v8; // rax
  int v9; // ebx
  HWND v10; // rdx
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rax
  struct _tagMPSWabIndexEntryDataEntryID *v14; // r12
  __int64 v15; // r15
  bool v16; // zf
  __int64 v17; // rdx
  __int64 v18; // rcx
  unsigned int v19; // r8d
  __int64 v20; // rcx
  int v21; // eax
  __int64 v22; // rcx
  int v23; // eax
  unsigned int v24; // r12d
  __int64 v25; // rdx
  unsigned int v26; // r13d
  __int64 v27; // r9
  __int64 v28; // r9
  unsigned int v29; // ecx
  __int64 v30; // rcx
  int v31; // eax
  __int64 v32; // rcx
  int v33; // eax
  __int64 v34; // rcx
  int v35; // eax
  _DWORD *v36; // rcx
  __int64 i; // rdx
  __int64 v38; // r10
  __int64 v39; // r8
  __int64 v40; // rcx
  unsigned int v42; // [rsp+40h] [rbp-29h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+44h] [rbp-25h] BYREF
  unsigned int v44; // [rsp+48h] [rbp-21h]
  HANDLE hFile; // [rsp+50h] [rbp-19h] BYREF
  void *v46[2]; // [rsp+58h] [rbp-11h] BYREF
  _OWORD v47[2]; // [rsp+68h] [rbp-1h] BYREF

  v2 = 0;
  v42 = 0;
  hFile = 0;
  v3 = 0;
  NumberOfBytesWritten = 0;
  v4 = a2;
  memset(v47, 0, sizeof(v47));
  *(_OWORD *)v46 = 0;
  if ( !a2 )
    goto LABEL_61;
  if ( a2->cb != 4 && IsWABEntryID(a2->cb, (struct ENTRYID *)a2->lpb, 0, 0, 0, 0, 0) == 7 )
  {
    IsWABEntryID(v4->cb, (struct ENTRYID *)v4->lpb, &v46[1], v46, 0, 0, 0);
    v6 = v46;
    if ( LODWORD(v46[0]) != 4 )
      v6 = (void **)v4;
    v4 = (struct _SBinary *)v6;
  }
  if ( v4->cb != 4 )
  {
LABEL_61:
    v9 = -2147024809;
    goto LABEL_62;
  }
  v7 = *(_DWORD *)v4->lpb;
  v8 = *((_QWORD *)this + 1);
  v44 = v7;
  if ( *(_DWORD *)(v8 + 8) || !(unsigned int)CWABStorage::LockFile(this) )
  {
    v9 = -2147024891;
    goto LABEL_62;
  }
  v3 = 1;
  v11 = OpenWABFile(*(LPCWSTR *)(*((_QWORD *)this + 1) + 16LL), v10, &hFile);
  v2 = hFile;
  v9 = v11;
  if ( v11 >= 0 )
  {
    if ( !(unsigned int)ReloadMPSWabFileInfo(*((struct _tagMPSWabFileInfo **)this + 1), hFile) )
    {
LABEL_13:
      v9 = -2147467259;
      goto LABEL_62;
    }
    v12 = *((_QWORD *)this + 1);
    if ( (*(_DWORD *)(*(_QWORD *)(v12 + 24) + 128LL) & 0x110) == 0
      || (int)HrDoQuickWABIntegrityCheck((struct _tagMPSWabFileInfo *)v12, v2) >= 0
      || (v9 = HrDoDetailedWABIntegrityCheck(*((struct _tagMPSWabFileInfo **)this + 1), v2), v9 >= 0) )
    {
      if ( !(unsigned int)TagWriteTransaction(*(struct _tagMPSWabFileHeader **)(*((_QWORD *)this + 1) + 24LL), v2, 1) )
        goto LABEL_13;
      v13 = *((_QWORD *)this + 1);
      v14 = *(struct _tagMPSWabIndexEntryDataEntryID **)(v13 + 40);
      if ( !(unsigned int)BinSearchEID(v14, v7, *(_DWORD *)(*(_QWORD *)(v13 + 24) + 36LL), &v42) )
      {
        v9 = -2147221241;
        goto LABEL_62;
      }
      v15 = v42;
      if ( !(unsigned int)ReadDataFromWABFile(v2, *((_DWORD *)v14 + 2 * v42 + 1), v47, 0x20u) )
        goto LABEL_21;
      v16 = LODWORD(v47[0]) == 0;
      LODWORD(v47[0]) = 0;
      v42 = v16;
      if ( (unsigned int)WriteDataToWABFile(
                           v2,
                           *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 1) + 40LL) + 8 * v15 + 4),
                           v47,
                           0x20u) )
      {
        if ( SetFilePointer(v2, *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 1) + 24LL) + 32LL) + 8 * v15, 0, 0) != -1 )
        {
          v17 = *((_QWORD *)this + 1);
          v18 = (unsigned int)(v15 + 1);
          v19 = *(_DWORD *)(*(_QWORD *)(v17 + 24) + 36LL);
          if ( v19 > (unsigned int)v18
            && !WriteFile(v2, (LPCVOID)(*(_QWORD *)(v17 + 40) + 8 * v18), 8 * (v19 - v15) - 8, &NumberOfBytesWritten, 0) )
          {
            goto LABEL_62;
          }
          v20 = *(_QWORD *)(*((_QWORD *)this + 1) + 24LL);
          v21 = *(_DWORD *)(v20 + 36);
          if ( v21 )
            *(_DWORD *)(v20 + 36) = v21 - 1;
          v22 = *(_QWORD *)(*((_QWORD *)this + 1) + 24LL);
          v23 = *(_DWORD *)(v22 + 28);
          if ( v23 )
            *(_DWORD *)(v22 + 28) = v23 - 8;
          v24 = 1;
          while ( 2 )
          {
            if ( v24 >= 6 )
            {
              if ( !v42 )
              {
                v34 = *(_QWORD *)(*((_QWORD *)this + 1) + 24LL);
                v35 = *(_DWORD *)(v34 + 120);
                if ( v35 )
                  *(_DWORD *)(v34 + 120) = v35 - 1;
                ++*(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 1) + 24LL) + 16LL);
                *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 1) + 24LL) + 128LL) |= 0x1000u;
              }
              if ( SetFilePointer(v2, 0, 0, 0) != -1 )
              {
                v36 = *(_DWORD **)(*((_QWORD *)this + 1) + 24LL);
                if ( v36[9] != v36[30] )
                  v36[32] |= 0x10u;
                for ( i = 1; i != 6; ++i )
                {
                  v38 = *((_QWORD *)this + 1);
                  v39 = *(_QWORD *)(v38 + 24);
                  if ( *(_DWORD *)(v39 + 16 * i + 36) > *(_DWORD *)(v39 + 120) )
                  {
                    *(_DWORD *)(v39 + 128) |= 0x10u;
                    v38 = *((_QWORD *)this + 1);
                  }
                }
                if ( WriteFile(v2, *(LPCVOID *)(v38 + 24), 0xA4u, &NumberOfBytesWritten, 0) )
                {
                  v40 = *((_QWORD *)this + 1);
                  if ( *(_DWORD *)(*(_QWORD *)(v40 + 24) + 16LL) > 0x64u )
                    CompressFile((LPCWSTR *)v40, v2, 0, 0, 0);
                  v9 = 0;
                }
                goto LABEL_62;
              }
            }
            else if ( LoadIndex(*((struct _tagMPSWabFileInfo **)this + 1), v24, v2) )
            {
              v25 = *((_QWORD *)this + 1);
              v26 = 0;
              v27 = *(_QWORD *)(v25 + 24);
              while ( 1 )
              {
                if ( v26 >= *(_DWORD *)(v27 + 16LL * v24 + 36) )
                  goto LABEL_45;
                if ( *(_DWORD *)(68LL * v26 + *(_QWORD *)(v25 + 32) + 64) == v44 )
                  break;
                ++v26;
              }
              if ( v26 == -1 )
              {
LABEL_45:
                ++v24;
                continue;
              }
              if ( SetFilePointer(v2, *(_DWORD *)(16 * (v24 + 2LL) + v27) + 68 * v26, 0, 0) == -1 )
                break;
              v28 = *((_QWORD *)this + 1);
              v29 = *(_DWORD *)(*(_QWORD *)(v28 + 24) + 16LL * v24 + 36);
              if ( v29 <= v26 + 1
                || WriteFile(
                     v2,
                     (LPCVOID)(*(_QWORD *)(v28 + 32) + 68LL * (v26 + 1)),
                     68 * (v29 - v26) - 68,
                     &NumberOfBytesWritten,
                     0) )
              {
                v30 = *(_QWORD *)(*((_QWORD *)this + 1) + 24LL);
                v31 = *(_DWORD *)(v30 + 16LL * v24 + 36);
                if ( v31 )
                  *(_DWORD *)(v30 + 16LL * v24 + 36) = v31 - 1;
                v32 = *(_QWORD *)(*((_QWORD *)this + 1) + 24LL);
                v33 = *(_DWORD *)(v32 + 16LL * v24 + 28);
                if ( v33 )
                  *(_DWORD *)(v32 + 16LL * v24 + 28) = v33 - 68;
                goto LABEL_45;
              }
              goto LABEL_62;
            }
            break;
          }
        }
LABEL_21:
        v9 = -2147221221;
      }
    }
  }
LABEL_62:
  TagWriteTransaction(*(struct _tagMPSWabFileHeader **)(*((_QWORD *)this + 1) + 24LL), v2, 0);
  if ( v2 )
    CloseHandle(v2);
  if ( v3 )
    ReleaseMutex(*(HANDLE *)(*((_QWORD *)this + 1) + 48LL));
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180040930  mov     [rsp-8+arg_10], rbx
0x180040935  push    rbp
0x180040936  push    rsi
0x180040937  push    rdi
0x180040938  push    r12
0x18004093a  push    r13
0x18004093c  push    r14
0x18004093e  push    r15
0x180040940  lea     rbp, [rsp-27h]
0x180040945  sub     rsp, 90h
0x18004094c  mov     rax, cs:__security_cookie
0x180040953  xor     rax, rsp
0x180040956  mov     [rbp+57h+var_38], rax
0x18004095a  xor     esi, esi
0x18004095c  mov     [rbp+57h+var_80], 0
0x180040963  xorps   xmm0, xmm0
0x180040966  mov     [rbp+57h+hFile], rsi
0x18004096a  xor     r14d, r14d
0x18004096d  mov     [rbp+57h+NumberOfBytesWritten], esi
0x180040970  mov     rbx, rdx
0x180040973  mov     rdi, rcx
0x180040976  movups  [rbp+57h+var_58], xmm0
0x18004097a  movups  [rbp+57h+var_48], xmm0
0x18004097e  movups  xmmword ptr [rbp+57h+var_68], xmm0
0x180040982  test    rdx, rdx
0x180040985  jz      loc_180040DC3
0x18004098b  cmp     dword ptr [rdx], 4
0x18004098e  jz      short loc_1800409E5
0x180040990  mov     rdx, [rdx+8]; struct ENTRYID *
0x180040994  xor     r9d, r9d; void **
0x180040997  mov     ecx, [rbx]; unsigned int
0x180040999  xor     r8d, r8d; void **
0x18004099c  mov     [rsp+0C0h+var_90], rsi; unsigned int *
0x1800409a1  mov     [rsp+0C0h+var_98], rsi; unsigned int *
0x1800409a6  mov     [rsp+0C0h+lpOverlapped], rsi; void **
0x1800409ab  call    ?IsWABEntryID@@YAEKPEAUENTRYID@@PEAPEAX11PEAK2@Z; IsWABEntryID(ulong,ENTRYID *,void * *,void * *,void * *,ulong *,ulong *)
0x1800409b0  cmp     al, 7
0x1800409b2  jnz     short loc_1800409E5
0x1800409b4  mov     rdx, [rbx+8]; struct ENTRYID *
0x1800409b8  lea     r9, [rbp+57h+var_68]; void **
0x1800409bc  mov     ecx, [rbx]; unsigned int
0x1800409be  lea     r8, [rbp+57h+var_68+8]; void **
0x1800409c2  mov     [rsp+0C0h+var_90], rsi; unsigned int *
0x1800409c7  mov     [rsp+0C0h+var_98], rsi; unsigned int *
0x1800409cc  mov     [rsp+0C0h+lpOverlapped], rsi; void **
0x1800409d1  call    ?IsWABEntryID@@YAEKPEAUENTRYID@@PEAPEAX11PEAK2@Z; IsWABEntryID(ulong,ENTRYID *,void * *,void * *,void * *,ulong *,ulong *)
0x1800409d6  cmp     dword ptr [rbp+57h+var_68], 4
0x1800409da  lea     r8, [rbp+57h+var_68]
0x1800409de  cmovnz  r8, rbx
0x1800409e2  mov     rbx, r8
0x1800409e5  cmp     dword ptr [rbx], 4
0x1800409e8  jnz     loc_180040DC3
0x1800409ee  mov     rax, [rbx+8]
0x1800409f2  mov     r15d, [rax]
0x1800409f5  mov     rax, [rdi+8]
0x1800409f9  mov     [rbp+57h+var_78], r15d
0x1800409fd  cmp     [rax+8], esi
0x180040a00  jz      short loc_180040A0C
0x180040a02  mov     ebx, 80070005h
0x180040a07  jmp     loc_180040DC8
0x180040a0c  mov     rcx, rdi; this
0x180040a0f  call    ?LockFile@CWABStorage@@AEAAHXZ; CWABStorage::LockFile(void)
0x180040a14  test    eax, eax
0x180040a16  jz      short loc_180040A02
0x180040a18  mov     rcx, [rdi+8]
0x180040a1c  lea     r8, [rbp+57h+hFile]; void **
0x180040a20  mov     r14d, 1
0x180040a26  mov     rcx, [rcx+10h]; lpFileName
0x180040a2a  call    ?OpenWABFile@@YAJPEAGPEAUHWND__@@PEAPEAX@Z; OpenWABFile(ushort *,HWND__ *,void * *)
0x180040a2f  mov     rsi, [rbp+57h+hFile]
0x180040a33  mov     ebx, eax
0x180040a35  test    eax, eax
0x180040a37  js      loc_180040DC8
0x180040a3d  mov     rcx, [rdi+8]; struct _tagMPSWabFileInfo *
0x180040a41  mov     rdx, rsi; void *
0x180040a44  call    ?ReloadMPSWabFileInfo@@YAHPEAU_tagMPSWabFileInfo@@PEAX@Z; ReloadMPSWabFileInfo(_tagMPSWabFileInfo *,void *)
0x180040a49  test    eax, eax
0x180040a4b  jnz     short loc_180040A57
0x180040a4d  mov     ebx, 80004005h
0x180040a52  jmp     loc_180040DC8
0x180040a57  mov     rcx, [rdi+8]; struct _tagMPSWabFileInfo *
0x180040a5b  mov     rax, [rcx+18h]
0x180040a5f  test    dword ptr [rax+80h], 110h
0x180040a69  jz      short loc_180040A8D
0x180040a6b  mov     rdx, rsi; void *
0x180040a6e  call    ?HrDoQuickWABIntegrityCheck@@YAJPEAU_tagMPSWabFileInfo@@PEAX@Z; HrDoQuickWABIntegrityCheck(_tagMPSWabFileInfo *,void *)
0x180040a73  test    eax, eax
0x180040a75  jns     short loc_180040A8D
0x180040a77  mov     rcx, [rdi+8]; struct _tagMPSWabFileInfo *
0x180040a7b  mov     rdx, rsi; void *
0x180040a7e  call    ?HrDoDetailedWABIntegrityCheck@@YAJPEAU_tagMPSWabFileInfo@@PEAX@Z; HrDoDetailedWABIntegrityCheck(_tagMPSWabFileInfo *,void *)
0x180040a83  mov     ebx, eax
0x180040a85  test    eax, eax
0x180040a87  js      loc_180040DC8
0x180040a8d  mov     rcx, [rdi+8]
0x180040a91  mov     r8d, r14d; int
0x180040a94  mov     rdx, rsi; hFile
0x180040a97  mov     rcx, [rcx+18h]; struct _tagMPSWabFileHeader *
0x180040a9b  call    ?TagWriteTransaction@@YAHPEAU_tagMPSWabFileHeader@@PEAXH@Z; TagWriteTransaction(_tagMPSWabFileHeader *,void *,int)
0x180040aa0  test    eax, eax
0x180040aa2  jz      short loc_180040A4D
0x180040aa4  mov     rax, [rdi+8]
0x180040aa8  lea     r9, [rbp+57h+var_80]; unsigned int *
0x180040aac  mov     edx, r15d; unsigned int
0x180040aaf  mov     r8, [rax+18h]
0x180040ab3  mov     r12, [rax+28h]
0x180040ab7  mov     rcx, r12; struct _tagMPSWabIndexEntryDataEntryID *
0x180040aba  mov     r8d, [r8+24h]; unsigned int
0x180040abe  call    ?BinSearchEID@@YAHPEAU_tagMPSWabIndexEntryDataEntryID@@KKPEAK@Z; BinSearchEID(_tagMPSWabIndexEntryDataEntryID *,ulong,ulong,ulong *)
0x180040ac3  test    eax, eax
0x180040ac5  jnz     short loc_180040AD1
0x180040ac7  mov     ebx, 80040107h
0x180040acc  jmp     loc_180040DC8
0x180040ad1  mov     r15d, [rbp+57h+var_80]
0x180040ad5  lea     r8, [rbp+57h+var_58]; void *
0x180040ad9  mov     r9d, 20h ; ' '; unsigned int
0x180040adf  mov     rcx, rsi; hFile
0x180040ae2  mov     edx, [r12+r15*8+4]; unsigned int
0x180040ae7  call    ?ReadDataFromWABFile@@YAHPEAXK0K@Z; ReadDataFromWABFile(void *,ulong,void *,ulong)
0x180040aec  test    eax, eax
0x180040aee  jnz     short loc_180040AFA
0x180040af0  mov     ebx, 8004011Bh
0x180040af5  jmp     loc_180040DC8
0x180040afa  xor     eax, eax
0x180040afc  lea     r8, [rbp+57h+var_58]; void *
0x180040b00  cmp     dword ptr [rbp+57h+var_58], eax
0x180040b03  mov     r9d, 20h ; ' '; unsigned int
0x180040b09  mov     dword ptr [rbp+57h+var_58], 0
0x180040b10  mov     rcx, rsi; hFile
0x180040b13  cmovz   eax, r14d
0x180040b17  mov     [rbp+57h+var_80], eax
0x180040b1a  mov     rax, [rdi+8]
0x180040b1e  mov     rdx, [rax+28h]
0x180040b22  mov     edx, [rdx+r15*8+4]; unsigned int
0x180040b27  call    ?WriteDataToWABFile@@YAHPEAXK0K@Z; WriteDataToWABFile(void *,ulong,void *,ulong)
0x180040b2c  test    eax, eax
0x180040b2e  jz      loc_180040DC8
0x180040b34  mov     rax, [rdi+8]
0x180040b38  xor     r9d, r9d; dwMoveMethod
0x180040b3b  xor     r8d, r8d; lpDistanceToMoveHigh
0x180040b3e  mov     rcx, [rax+18h]
0x180040b42  mov     eax, [rcx+20h]
0x180040b45  mov     rcx, rsi; hFile
0x180040b48  lea     edx, [rax+r15*8]; lDistanceToMove
0x180040b4c  call    cs:__imp_SetFilePointer
0x180040b52  cmp     eax, 0FFFFFFFFh
0x180040b55  jz      short loc_180040AF0
0x180040b57  mov     rdx, [rdi+8]
0x180040b5b  lea     ecx, [r15+1]
0x180040b5f  mov     rax, [rdx+18h]
0x180040b63  mov     r8d, [rax+24h]
0x180040b67  cmp     r8d, ecx
0x180040b6a  jbe     short loc_180040B9D
0x180040b6c  mov     rax, [rdx+28h]
0x180040b70  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180040b74  sub     r8d, r15d
0x180040b77  mov     [rsp+0C0h+lpOverlapped], 0; lpOverlapped
0x180040b80  lea     rdx, [rax+rcx*8]; lpBuffer
0x180040b84  mov     rcx, rsi; hFile
0x180040b87  lea     r8d, ds:0FFFFFFFFFFFFFFF8h[r8*8]; nNumberOfBytesToWrite
0x180040b8f  call    cs:__imp_WriteFile
0x180040b95  test    eax, eax
0x180040b97  jz      loc_180040DC8
0x180040b9d  mov     rax, [rdi+8]
0x180040ba1  mov     rcx, [rax+18h]
0x180040ba5  mov     eax, [rcx+24h]
0x180040ba8  test    eax, eax
0x180040baa  jz      short loc_180040BB1
0x180040bac  dec     eax
0x180040bae  mov     [rcx+24h], eax
0x180040bb1  mov     rax, [rdi+8]
0x180040bb5  mov     rcx, [rax+18h]
0x180040bb9  mov     eax, [rcx+1Ch]
0x180040bbc  test    eax, eax
0x180040bbe  jz      short loc_180040BC6
0x180040bc0  add     eax, 0FFFFFFF8h
0x180040bc3  mov     [rcx+1Ch], eax
0x180040bc6  mov     r12d, r14d
0x180040bc9  cmp     r12d, 6
0x180040bcd  jnb     loc_180040CD7
0x180040bd3  mov     rcx, [rdi+8]; struct _tagMPSWabFileInfo *
0x180040bd7  mov     r8, rsi; void *
0x180040bda  mov     edx, r12d; unsigned int
0x180040bdd  call    ?LoadIndex@@YAHPEAU_tagMPSWabFileInfo@@KPEAX@Z; LoadIndex(_tagMPSWabFileInfo *,ulong,void *)
0x180040be2  test    eax, eax
0x180040be4  jz      loc_180040AF0
0x180040bea  mov     rdx, [rdi+8]
0x180040bee  xor     r13d, r13d
0x180040bf1  mov     r10d, [rbp+57h+var_78]
0x180040bf5  mov     r15d, r12d
0x180040bf8  mov     r8d, r12d
0x180040bfb  add     r15, r15
0x180040bfe  mov     r9, [rdx+18h]
0x180040c02  cmp     r13d, [r9+r15*8+24h]
0x180040c07  jnb     loc_180040CCF
0x180040c0d  mov     eax, r13d
0x180040c10  imul    rcx, rax, 44h ; 'D'
0x180040c14  mov     rax, [rdx+20h]
0x180040c18  cmp     [rcx+rax+40h], r10d
0x180040c1d  jz      short loc_180040C24
0x180040c1f  add     r13d, r14d
0x180040c22  jmp     short loc_180040C02
0x180040c24  cmp     r13d, 0FFFFFFFFh
0x180040c28  jz      loc_180040CCF
0x180040c2e  lea     rax, [r8+2]
0x180040c32  imul    edx, r13d, 44h ; 'D'
0x180040c36  shl     rax, 4
0x180040c3a  xor     r8d, r8d; lpDistanceToMoveHigh
0x180040c3d  mov     rcx, rsi; hFile
0x180040c40  add     edx, [rax+r9]; lDistanceToMove
0x180040c44  xor     r9d, r9d; dwMoveMethod
0x180040c47  call    cs:__imp_SetFilePointer
0x180040c4d  cmp     eax, 0FFFFFFFFh
0x180040c50  jz      loc_180040AF0
0x180040c56  mov     r9, [rdi+8]
0x180040c5a  lea     edx, [r13+1]
0x180040c5e  mov     rax, [r9+18h]
0x180040c62  mov     ecx, [rax+r15*8+24h]
0x180040c67  cmp     ecx, edx
0x180040c69  jbe     short loc_180040C9E
0x180040c6b  mov     eax, edx
0x180040c6d  sub     ecx, r13d
0x180040c70  imul    r8d, ecx, 44h ; 'D'
0x180040c74  mov     rcx, rsi; hFile
0x180040c77  imul    rdx, rax, 44h ; 'D'
0x180040c7b  sub     r8d, 44h ; 'D'; nNumberOfBytesToWrite
0x180040c7f  mov     [rsp+0C0h+lpOverlapped], 0; lpOverlapped
0x180040c88  add     rdx, [r9+20h]; lpBuffer
0x180040c8c  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180040c90  call    cs:__imp_WriteFile
0x180040c96  test    eax, eax
0x180040c98  jz      loc_180040DC8
0x180040c9e  mov     rax, [rdi+8]
0x180040ca2  mov     rcx, [rax+18h]
0x180040ca6  mov     eax, [rcx+r15*8+24h]
0x180040cab  test    eax, eax
0x180040cad  jz      short loc_180040CB6
0x180040caf  dec     eax
0x180040cb1  mov     [rcx+r15*8+24h], eax
0x180040cb6  mov     rax, [rdi+8]
0x180040cba  mov     rcx, [rax+18h]
0x180040cbe  mov     eax, [rcx+r15*8+1Ch]
0x180040cc3  test    eax, eax
0x180040cc5  jz      short loc_180040CCF
0x180040cc7  add     eax, 0FFFFFFBCh
0x180040cca  mov     [rcx+r15*8+1Ch], eax
0x180040ccf  add     r12d, r14d
0x180040cd2  jmp     loc_180040BC9
0x180040cd7  cmp     [rbp+57h+var_80], 0
0x180040cdb  jnz     short loc_180040D0D
0x180040cdd  mov     rax, [rdi+8]
0x180040ce1  mov     rcx, [rax+18h]
0x180040ce5  mov     eax, [rcx+78h]
0x180040ce8  test    eax, eax
0x180040cea  jz      short loc_180040CF1
0x180040cec  dec     eax
0x180040cee  mov     [rcx+78h], eax
0x180040cf1  mov     rax, [rdi+8]
0x180040cf5  mov     rcx, [rax+18h]
0x180040cf9  add     [rcx+10h], r14d
0x180040cfd  mov     rax, [rdi+8]
0x180040d01  mov     rcx, [rax+18h]
0x180040d05  bts     dword ptr [rcx+80h], 0Ch
0x180040d0d  xor     r9d, r9d; dwMoveMethod
0x180040d10  xor     r8d, r8d; lpDistanceToMoveHigh
0x180040d13  xor     edx, edx; lDistanceToMove
0x180040d15  mov     rcx, rsi; hFile
0x180040d18  call    cs:__imp_SetFilePointer
0x180040d1e  cmp     eax, 0FFFFFFFFh
0x180040d21  jz      loc_180040AF0
0x180040d27  mov     rax, [rdi+8]
0x180040d2b  mov     rcx, [rax+18h]
0x180040d2f  mov     eax, [rcx+78h]
0x180040d32  cmp     [rcx+24h], eax
0x180040d35  jz      short loc_180040D3E
0x180040d37  or      dword ptr [rcx+80h], 10h
0x180040d3e  mov     rdx, r14
0x180040d41  mov     r10, [rdi+8]
0x180040d45  mov     rcx, rdx
0x180040d48  add     rcx, rcx
0x180040d4b  mov     r8, [r10+18h]
0x180040d4f  mov     eax, [r8+78h]
0x180040d53  cmp     [r8+rcx*8+24h], eax
0x180040d58  jbe     short loc_180040D66
0x180040d5a  or      dword ptr [r8+80h], 10h
0x180040d62  mov     r10, [rdi+8]
0x180040d66  add     rdx, r14
0x180040d69  cmp     rdx, 6
0x180040d6d  jnz     short loc_180040D41
0x180040d6f  mov     rdx, [r10+18h]; lpBuffer
0x180040d73  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180040d77  mov     r8d, 0A4h; nNumberOfBytesToWrite
0x180040d7d  mov     [rsp+0C0h+lpOverlapped], 0; lpOverlapped
0x180040d86  mov     rcx, rsi; hFile
0x180040d89  call    cs:__imp_WriteFile
0x180040d8f  test    eax, eax
0x180040d91  jz      short loc_180040DC8
0x180040d93  mov     rcx, [rdi+8]; struct _tagMPSWabFileInfo *
0x180040d97  mov     rax, [rcx+18h]
0x180040d9b  cmp     dword ptr [rax+10h], 64h ; 'd'
  ... truncated ...
```
