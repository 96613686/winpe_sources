# CWABStorage::ReadPropArray(_SBinary *,_SPropertyRestriction *,ulong,ulong,ulong *,_ADRLIST * *)

- ea: `0x180042810`
- end: `0x18004309d`
- name: `?ReadPropArray@CWABStorage@@UEAAJPEAU_SBinary@@PEAU_SPropertyRestriction@@KKPEAKPEAPEAU_ADRLIST@@@Z`
- size: `2189`
- prototype: `__int64 __usercall@<rax>(CWABStorage *__hidden this@<rcx>, struct _SBinary *@<rdx>, struct _SPropertyRestriction *@<r8>, unsigned int@<r9d>, unsigned int, unsigned int *, struct _ADRLIST **)`
- caller_count: `0`
- callee_count: `18`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800301e8`
- `0x180030ec0`
- `0x180031618`
- `0x1800323b8`
- `0x180032588`
- `0x180032704`
- `0x1800329b4`
- `0x180032f24`
- `0x180033040`
- `0x18003313c`
- `0x180033ae0`
- `0x18004273c`
- `0x180042810`
- `0x180043ffc`
- `0x180091e92`
- `0x180091eaa`
- `0x180091ef0`
- `0x180093010`

## import_xrefs

- `KERNEL32!ReleaseMutex` at `0x180043075`
- `KERNEL32!ReleaseMutex` at `0x180043075`
- `KERNEL32!SetFilePointer` at `0x180042c11`
- `KERNEL32!SetFilePointer` at `0x180042c11`
- `KERNEL32!LocalAlloc` at `0x1800428f1`
- `KERNEL32!LocalAlloc` at `0x180042a69`
- `KERNEL32!LocalAlloc` at `0x180042ba8`
- `KERNEL32!LocalAlloc` at `0x180042be8`
- `KERNEL32!LocalAlloc` at `0x180042c79`
- `KERNEL32!LocalAlloc` at `0x180042dc2`
- `KERNEL32!LocalAlloc` at `0x180042e02`
- `KERNEL32!LocalAlloc` at `0x180042e4a`
- `KERNEL32!LocalAlloc` at `0x180042e7c`
- `KERNEL32!LocalAlloc` at `0x180042ec2`
- `KERNEL32!LocalAlloc` at `0x180042ef1`
- `KERNEL32!LocalAlloc` at `0x1800428f1`
- `KERNEL32!LocalAlloc` at `0x180042a69`
- `KERNEL32!LocalAlloc` at `0x180042ba8`
- `KERNEL32!LocalAlloc` at `0x180042be8`
- `KERNEL32!LocalAlloc` at `0x180042c79`
- `KERNEL32!LocalAlloc` at `0x180042dc2`
- `KERNEL32!LocalAlloc` at `0x180042e02`
- `KERNEL32!LocalAlloc` at `0x180042e4a`
- `KERNEL32!LocalAlloc` at `0x180042e7c`
- `KERNEL32!LocalAlloc` at `0x180042ec2`
- `KERNEL32!LocalAlloc` at `0x180042ef1`
- `KERNEL32!LocalFree` at `0x180042fbf`
- `KERNEL32!LocalFree` at `0x180042ff0`
- `KERNEL32!LocalFree` at `0x180043000`
- `KERNEL32!LocalFree` at `0x180042fbf`
- `KERNEL32!LocalFree` at `0x180042ff0`
- `KERNEL32!LocalFree` at `0x180043000`
- `KERNEL32!CloseHandle` at `0x18004303d`
- `KERNEL32!CloseHandle` at `0x18004303d`
- `KERNEL32!GetFileSize` at `0x1800429e8`
- `KERNEL32!GetFileSize` at `0x1800429e8`
- `KERNEL32!ReadFile` at `0x180042c38`
- `KERNEL32!ReadFile` at `0x180042c38`

## pseudocode

```c
__int64 __fastcall CWABStorage::ReadPropArray(
        struct _tagMPSWabFileInfo **this,
        struct _SBinary *a2,
        struct _SPropertyRestriction *a3,
        signed int a4,
        unsigned int a5,
        unsigned int *a6,
        struct _ADRLIST **a7)
{
  HANDLE v7; // r15
  char v11; // r14
  HANDLE v12; // r13
  unsigned int *v13; // rsi
  _DWORD *v15; // r14
  int RecordsWithoutLocking; // ebx
  unsigned int v17; // r9d
  __int64 v18; // rcx
  unsigned int *v19; // rsi
  unsigned int v20; // eax
  HWND v21; // rdx
  int v22; // eax
  DWORD FileSize; // eax
  struct _tagMPSWabFileInfo *v24; // rcx
  struct _tagMPSWabFileInfo *v25; // rcx
  struct _ADRLIST *v26; // r14
  ULONG v27; // eax
  unsigned int i; // ecx
  size_t cb; // r8
  struct _tagMPSWabFileInfo *v30; // rax
  struct _tagMPSWabIndexEntryDataEntryID *v31; // rdi
  __int64 v32; // rbx
  unsigned int v33; // edi
  struct _tagMPSWabFileInfo *v34; // rax
  __m128i v35; // xmm1
  __int64 v36; // rcx
  __int64 v37; // rdx
  unsigned int v38; // edi
  __int64 v39; // rbx
  __int64 v40; // rsi
  SIZE_T v41; // rdx
  struct _SPropValue *v42; // rax
  __int64 v43; // rdx
  __int64 v44; // rcx
  SIZE_T v45; // rbx
  HLOCAL v46; // rax
  int v47; // ecx
  char *v48; // rdi
  unsigned int v49; // edx
  int v50; // ecx
  unsigned int v51; // ebx
  __int16 v52; // ax
  int v53; // eax
  __int64 v54; // rax
  size_t v55; // r15
  __int64 j; // rax
  __int64 v57; // rsi
  __int64 v58; // r14
  HLOCAL v59; // rax
  unsigned int m; // r15d
  __int64 v61; // rax
  size_t v62; // rdx
  void *v63; // rcx
  char *v64; // rbx
  size_t v65; // rdi
  HLOCAL v66; // rax
  __int64 k; // r15
  size_t v68; // rdx
  void *v69; // rcx
  char *v70; // rbx
  size_t v71; // rdi
  size_t v72; // rbx
  HLOCAL v73; // rax
  HLOCAL v74; // rax
  struct _ADRLIST **v75; // rdi
  unsigned int v76; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE hFile; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v78; // [rsp+40h] [rbp-C0h]
  int v79; // [rsp+44h] [rbp-BCh]
  unsigned int v80; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int *v81; // [rsp+50h] [rbp-B0h]
  int v82; // [rsp+58h] [rbp-A8h]
  unsigned int v83; // [rsp+5Ch] [rbp-A4h]
  unsigned int v84; // [rsp+60h] [rbp-A0h] BYREF
  DWORD NumberOfBytesRead; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v86; // [rsp+68h] [rbp-98h]
  unsigned int v87; // [rsp+6Ch] [rbp-94h]
  int v88; // [rsp+70h] [rbp-90h]
  int v89; // [rsp+74h] [rbp-8Ch]
  void *v90; // [rsp+78h] [rbp-88h] BYREF
  void *v91; // [rsp+80h] [rbp-80h] BYREF
  DWORD v92; // [rsp+88h] [rbp-78h]
  HLOCAL hMem; // [rsp+90h] [rbp-70h]
  struct _SBinary *v94; // [rsp+98h] [rbp-68h] BYREF
  size_t Size; // [rsp+A0h] [rbp-60h]
  __int64 v96; // [rsp+A8h] [rbp-58h]
  unsigned int *v97; // [rsp+B0h] [rbp-50h]
  struct _ADRLIST **v98; // [rsp+B8h] [rbp-48h]
  __int64 v99; // [rsp+C0h] [rbp-40h]
  struct _ADRLIST *v100; // [rsp+C8h] [rbp-38h]
  _OWORD v101[2]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned int v102[4]; // [rsp+F0h] [rbp-10h] BYREF
  SIZE_T uBytes[2]; // [rsp+100h] [rbp+0h]

  v7 = 0;
  v86 = a4;
  v83 = a5;
  v98 = a7;
  v76 = 0;
  v11 = a4;
  *a7 = 0;
  v12 = 0;
  v97 = a6;
  v13 = 0;
  v94 = 0;
  hFile = 0;
  NumberOfBytesRead = 0;
  v81 = 0;
  v90 = 0;
  v84 = 0;
  v91 = 0;
  *(_OWORD *)v102 = 0;
  *(_OWORD *)uBytes = 0;
  if ( !a5 )
    return 2147942487LL;
  v89 = 0;
  v88 = 0;
  if ( (a4 & 0x7FFFFFFE) != 0 || !a6 || !a3 )
  {
    RecordsWithoutLocking = -2147024809;
    goto LABEL_110;
  }
  if ( a4 < 0 )
  {
    hMem = a6;
LABEL_17:
    if ( !(unsigned int)CWABStorage::LockFile((CWABStorage *)this) )
    {
      RecordsWithoutLocking = -2147024891;
      goto LABEL_102;
    }
    v89 = 1;
    RecordsWithoutLocking = CWABStorage::_FindRecordsWithoutLocking((CWABStorage *)this, a2, v11, a3, &v76, &v94);
    if ( RecordsWithoutLocking >= 0 )
    {
      if ( !v76 )
      {
        RecordsWithoutLocking = -2147221233;
        goto LABEL_102;
      }
      v22 = OpenWABFile(*((WCHAR **)this[1] + 2), v21, &hFile);
      v12 = hFile;
      RecordsWithoutLocking = v22;
      if ( v22 >= 0 )
      {
        if ( hFile != (HANDLE)-1LL )
        {
          FileSize = GetFileSize(hFile, 0);
          v24 = this[1];
          v92 = FileSize;
          if ( !(unsigned int)ReloadMPSWabFileInfo(v24, v12) )
          {
LABEL_25:
            RecordsWithoutLocking = -2147221221;
            goto LABEL_102;
          }
          v25 = this[1];
          if ( (*(_DWORD *)(*((_QWORD *)v25 + 3) + 128LL) & 0x110) != 0 && (int)HrDoQuickWABIntegrityCheck(v25, v12) < 0 )
          {
            RecordsWithoutLocking = HrDoDetailedWABIntegrityCheck(this[1], v12);
            if ( RecordsWithoutLocking < 0 )
              goto LABEL_102;
          }
          if ( v76 > 0xFFFFFFE
            || (v26 = (struct _ADRLIST *)LocalAlloc(0x40u, 16LL * v76 + 24), v100 = v26, (*v98 = v26) == 0) )
          {
LABEL_30:
            RecordsWithoutLocking = -2147024882;
            goto LABEL_102;
          }
          v26->cEntries = v76;
          v27 = 0;
          v79 = 0;
          for ( i = 0; ; i = v87 + 1 )
          {
            v87 = i;
            if ( i >= v76 )
            {
              v26->cEntries = v27;
              RecordsWithoutLocking = 0;
              goto LABEL_102;
            }
            v80 = 0;
            if ( v94[i].cb >= 4 )
              cb = 4;
            else
              cb = v94[i].cb;
            memcpy_0(&v80, v94[i].lpb, cb);
            v30 = this[1];
            v31 = (struct _tagMPSWabIndexEntryDataEntryID *)*((_QWORD *)v30 + 5);
            if ( !(unsigned int)BinSearchEID(v31, v80, *(_DWORD *)(*((_QWORD *)v30 + 3) + 36LL), &v84) )
              goto LABEL_41;
            v32 = v84;
            v33 = *((_DWORD *)v31 + 2 * v84 + 1);
            if ( !(unsigned int)ReadDataFromWABFile(v12, v33, v102, 0x20u) )
              goto LABEL_106;
            v34 = this[1];
            v35 = *(__m128i *)v102;
            v36 = *((_QWORD *)v34 + 5);
            v37 = *((_QWORD *)v34 + 3);
            v101[0] = *(_OWORD *)v102;
            v101[1] = *(_OWORD *)uBytes;
            if ( !(unsigned int)bIsValidRecord(
                                  v101,
                                  *(unsigned int *)(v37 + 20),
                                  v33,
                                  v92,
                                  1,
                                  *(_DWORD *)(v36 + 8 * v32)) )
              break;
            if ( _mm_cvtsi128_si32(_mm_srli_si128(v35, 4)) == 3 )
              goto LABEL_41;
            v38 = v83;
            v39 = v83;
            v40 = v79;
            v96 = v40 * 16;
            v41 = 24LL * v83;
            v26->aEntries[v40].cValues = v83;
            v42 = (struct _SPropValue *)LocalAlloc(0x40u, v41);
            v26->aEntries[v40].rgPropVals = v42;
            if ( !v42 )
            {
              RecordsWithoutLocking = -2147024882;
              goto LABEL_101;
            }
            v43 = 0;
            do
            {
              v44 = v43;
              v43 = (unsigned int)(v43 + 1);
              v26->aEntries[v40].rgPropVals[v44].ulPropTag = 10;
            }
            while ( (unsigned int)v43 < v38 );
            LocalFreeAndNull(&v90);
            v81 = (unsigned int *)LocalAlloc(0x40u, HIDWORD(uBytes[1]));
            v13 = v81;
            v90 = v81;
            if ( !v81 )
              goto LABEL_30;
            if ( SetFilePointer(v12, SHIDWORD(uBytes[0]), 0, 1u) == -1 )
              goto LABEL_25;
            if ( !ReadFile(v12, v13, HIDWORD(uBytes[1]), &NumberOfBytesRead, 0) )
            {
LABEL_106:
              RecordsWithoutLocking = -2147221226;
              goto LABEL_102;
            }
            if ( NumberOfBytesRead != HIDWORD(uBytes[1])
              || !(unsigned int)SecurityCheckPropArrayBuffer((unsigned __int8 *)v13, HIDWORD(uBytes[1]), v102[3]) )
            {
              goto LABEL_25;
            }
            LocalFreeAndNull(&v91);
            v45 = 4 * v39;
            v46 = LocalAlloc(0x40u, v45);
            hFile = v46;
            v7 = v46;
            v91 = v46;
            if ( !v46 )
              goto LABEL_30;
            memset_0(v46, 0, v45 & 0xFFFFFFFFFFFFFFFCuLL);
            v47 = 0;
            v48 = (char *)v13;
            v82 = 0;
            v49 = 0;
            while ( 2 )
            {
              v78 = v49;
              if ( v49 < v102[3] && v47 != v83 )
              {
                v50 = *(_DWORD *)v48;
                v51 = 0;
                v52 = *(_DWORD *)v48;
                v80 = 0;
                v53 = v52 & 0x1000;
                if ( v53 )
                {
                  v51 = *((_DWORD *)v48 + 1);
                  v80 = v51;
                }
                v54 = v53 != 0 ? 8LL : 4LL;
                v55 = *(unsigned int *)&v48[v54];
                v48 += v54 + 4;
                for ( j = 0; ; j = (unsigned int)(j + 1) )
                {
                  if ( (unsigned int)j >= v83 )
                    goto LABEL_95;
                  v99 = (unsigned int)j;
                  if ( v50 == *((_DWORD *)hMem + j) )
                    break;
                }
                if ( *((_DWORD *)hFile + (unsigned int)j) == 1 )
                {
LABEL_95:
                  v47 = v82;
                  v48 += v55;
                  v7 = hFile;
                  goto LABEL_96;
                }
                v57 = 3LL * (unsigned int)j;
                v58 = *(__int64 *)((char *)&v26->aEntries[0].rgPropVals + v96);
                *(_DWORD *)(v58 + 24LL * (unsigned int)j) = v50;
                if ( (unsigned __int16)v50 <= 0x14u )
                {
                  if ( (unsigned __int16)v50 == 20
                    || (unsigned __int16)v50 == 2
                    || (unsigned __int16)v50 == 3
                    || (unsigned __int16)v50 == 4
                    || (unsigned __int16)v50 == 6
                    || (unsigned __int16)v50 == 7
                    || (unsigned __int16)v50 == 11 )
                  {
LABEL_71:
                    memcpy_0((void *)(v58 + 8 * (v57 + 1)), v48, v55);
                    v48 += v55;
                    goto LABEL_93;
                  }
LABEL_94:
                  v47 = v82 + 1;
                  v7 = hFile;
                  v26 = v100;
                  ++v82;
                  *((_DWORD *)hFile + v99) = 1;
LABEL_96:
                  ++v49;
                  continue;
                }
                if ( (unsigned __int16)v50 == 31 )
                  goto LABEL_90;
                if ( (unsigned __int16)v50 == 64 )
                  goto LABEL_71;
                if ( (unsigned __int16)v50 == 72 )
                {
LABEL_90:
                  v72 = v55;
                  v74 = LocalAlloc(0x40u, v55);
                  *(_QWORD *)(v58 + 8 * v57 + 8) = v74;
                  if ( !v74 )
                    goto LABEL_100;
                  memcpy_0(v74, v48, v55);
                }
                else
                {
                  if ( (unsigned __int16)v50 != 258 )
                  {
                    if ( (unsigned __int16)v50 == 4127 )
                    {
                      v66 = LocalAlloc(0x40u, 8LL * v51);
                      *(_QWORD *)(v58 + 8 * v57 + 16) = v66;
                      if ( v66 )
                      {
                        *(_DWORD *)(v58 + 8 * v57 + 8) = v51;
                        for ( k = 0; (unsigned int)k < v51; k = (unsigned int)(k + 1) )
                        {
                          v68 = *(unsigned int *)v48;
                          Size = v68;
                          *(_QWORD *)(*(_QWORD *)(v58 + 8 * v57 + 16) + 8 * k) = LocalAlloc(0x40u, v68);
                          v69 = *(void **)(*(_QWORD *)(v58 + 8 * v57 + 16) + 8 * k);
                          if ( !v69 )
                            goto LABEL_100;
                          v70 = v48 + 4;
                          v71 = Size;
                          memcpy_0(v69, v70, Size);
                          v48 = &v70[v71];
                          v51 = v80;
                        }
                        goto LABEL_93;
                      }
                    }
                    else
                    {
                      if ( (unsigned __int16)v50 != 4354 )
                        goto LABEL_94;
                      v59 = LocalAlloc(0x40u, 16LL * v51);
                      *(_QWORD *)(v58 + 8 * v57 + 16) = v59;
                      if ( v59 )
                      {
                        *(_DWORD *)(v58 + 8 * v57 + 8) = v51;
                        for ( m = 0; m < v51; ++m )
                        {
                          v61 = *(_QWORD *)(v58 + 8 * v57 + 16);
                          v62 = *(unsigned int *)v48;
                          Size = v62;
                          *(_DWORD *)(v61 + 16LL * m) = v62;
                          *(_QWORD *)(*(_QWORD *)(v58 + 8 * v57 + 16) + 16LL * m + 8) = LocalAlloc(0x40u, v62);
                          v63 = *(void **)(*(_QWORD *)(v58 + 8 * v57 + 16) + 16LL * m + 8);
                          if ( !v63 )
                            goto LABEL_100;
                          v64 = v48 + 4;
                          v65 = Size;
                          memcpy_0(v63, v64, Size);
                          v48 = &v64[v65];
                          v51 = v80;
                        }
                        goto LABEL_93;
                      }
                    }
LABEL_100:
                    v7 = hFile;
                    RecordsWithoutLocking = -2147024882;
LABEL_101:
                    v13 = v81;
                    goto LABEL_102;
                  }
                  v72 = v55;
                  v73 = LocalAlloc(0x40u, v55);
                  *(_QWORD *)(v58 + 8 * v57 + 16) = v73;
                  if ( !v73 )
                    goto LABEL_100;
                  memcpy_0(v73, v48, v55);
                  *(_DWORD *)(v58 + 8 * v57 + 8) = v55;
                }
                v48 += v72;
LABEL_93:
                v49 = v78;
                goto LABEL_94;
              }
              break;
            }
            if ( (v86 & 0x80000000) == 0 )
            {
              RecordsWithoutLocking = ConvertWCPropsToALocalAlloc(
                                        *(struct _SPropValue **)((char *)&v26->aEntries[0].rgPropVals + v96),
                                        *(ULONG *)((char *)&v26->aEntries[0].cValues + v96));
              if ( RecordsWithoutLocking < 0 )
                goto LABEL_101;
            }
            LocalFreeAndNull(&v90);
            LocalFreeAndNull(&v91);
            v13 = (unsigned int *)v90;
            v27 = v79 + 1;
            v7 = v91;
            ++v79;
            v81 = (unsigned int *)v90;
LABEL_42:
            ;
          }
          v88 = 1;
LABEL_41:
          v27 = v79;
          goto LABEL_42;
        }
        RecordsWithoutLocking = -2147467259;
      }
    }
LABEL_102:
    if ( hMem && hMem != v97 )
      LocalFree(hMem);
    goto LABEL_110;
  }
  hMem = LocalAlloc(0x40u, 4LL * a5);
  v15 = hMem;
  if ( hMem )
  {
    v17 = v83;
    v18 = 0;
    v19 = v97;
    do
    {
      v20 = v19[v18];
      if ( (unsigned __int16)v20 == 30 )
      {
        v20 = v20 & 0xFFFF0000 | 0x1F;
      }
      else if ( (unsigned __int16)v20 == 4126 )
      {
        v20 = v20 & 0xFFFF0000 | 0x101F;
      }
      v15[v18] = v20;
      v18 = (unsigned int)(v18 + 1);
    }
    while ( (unsigned int)v18 < v17 );
    v13 = v81;
    v11 = v86;
    goto LABEL_17;
  }
  RecordsWithoutLocking = -2147024882;
LABEL_110:
  if ( v13 )
    LocalFree(v13);
  if ( v7 )
    LocalFree(v7);
  (*((void (__fastcall **)(struct _tagMPSWabFileInfo **, _QWORD, struct _SBinary *))*this + 7))(this, v76, v94);
  if ( v88 )
    TagWABFileError(*((struct _tagMPSWabFileHeader **)this[1] + 3), v12);
  if ( v12 )
    CloseHandle(v12);
  if ( RecordsWithoutLocking < 0 )
  {
    v75 = v98;
    if ( *v98 )
    {
      (*((void (__fastcall **)(struct _tagMPSWabFileInfo **))*this + 4))(this);
      *v75 = 0;
    }
  }
  if ( v89 )
    ReleaseMutex(*((HANDLE *)this[1] + 6));
  return (unsigned int)RecordsWithoutLocking;
}

```

## disassembly

```asm
0x180042810  push    rbp
0x180042812  push    rbx
0x180042813  push    rsi
0x180042814  push    rdi
0x180042815  push    r12
0x180042817  push    r13
0x180042819  push    r14
0x18004281b  push    r15
0x18004281d  lea     rbp, [rsp-28h]
0x180042822  sub     rsp, 128h
0x180042829  mov     rax, cs:__security_cookie
0x180042830  xor     rax, rsp
0x180042833  mov     [rbp+60h+var_50], rax
0x180042837  mov     eax, [rbp+60h+arg_20]
0x18004283d  xor     r15d, r15d
0x180042840  xorps   xmm0, xmm0
0x180042843  mov     [rsp+160h+var_F8], r9d
0x180042848  mov     rdi, rdx
0x18004284b  mov     [rsp+160h+var_104], eax
0x18004284f  mov     rdx, [rbp+60h+arg_30]
0x180042856  mov     rbx, r8
0x180042859  xor     r8d, r8d
0x18004285c  mov     [rbp+60h+var_A8], rdx
0x180042860  mov     [rsp+160h+var_130], r15d
0x180042865  mov     r12, rcx
0x180042868  mov     rcx, [rbp+60h+arg_28]
0x18004286f  mov     r14d, r9d
0x180042872  mov     [rdx], r8
0x180042875  mov     r13d, r15d
0x180042878  mov     [rbp+60h+var_B0], rcx
0x18004287c  mov     esi, r15d
0x18004287f  mov     [rbp+60h+var_C8], r15
0x180042883  mov     [rsp+160h+hFile], r15
0x180042888  mov     [rsp+160h+NumberOfBytesRead], r15d
0x18004288d  mov     [rsp+160h+var_110], r15
0x180042892  mov     [rsp+160h+var_E8], r15
0x180042897  mov     [rsp+160h+var_100], r15d
0x18004289c  mov     [rbp+60h+var_E0], r15
0x1800428a0  movups  xmmword ptr [rbp+60h+var_70], xmm0
0x1800428a4  movups  xmmword ptr [rbp+60h+uBytes], xmm0
0x1800428a8  cmp     eax, 1
0x1800428ab  jnb     short loc_1800428B7
0x1800428ad  mov     eax, 80070057h
0x1800428b2  jmp     loc_18004307D
0x1800428b7  mov     [rsp+160h+var_EC], r8d
0x1800428bc  mov     [rsp+160h+var_F0], r8d
0x1800428c1  test    r9d, 7FFFFFFEh
0x1800428c8  jnz     loc_180042FE3
0x1800428ce  test    rcx, rcx
0x1800428d1  jz      loc_180042FE3
0x1800428d7  test    rbx, rbx
0x1800428da  jz      loc_180042FE3
0x1800428e0  test    r9d, r9d
0x1800428e3  js      short loc_180042956
0x1800428e5  mov     rdx, rax
0x1800428e8  mov     ecx, 40h ; '@'; uFlags
0x1800428ed  shl     rdx, 2; uBytes
0x1800428f1  call    cs:__imp_LocalAlloc
0x1800428f7  mov     [rbp+60h+hMem], rax
0x1800428fb  mov     r14, rax
0x1800428fe  test    rax, rax
0x180042901  jnz     short loc_18004290D
0x180042903  mov     ebx, 8007000Eh
0x180042908  jmp     loc_180042FE8
0x18004290d  mov     r9d, [rsp+160h+var_104]
0x180042912  xor     ecx, ecx
0x180042914  mov     rsi, [rbp+60h+var_B0]
0x180042918  mov     eax, [rsi+rcx*4]
0x18004291b  movzx   edx, ax
0x18004291e  cmp     edx, 1Eh
0x180042921  jnz     short loc_18004292D
0x180042923  and     eax, 0FFFF001Fh
0x180042928  or      eax, 1Fh
0x18004292b  jmp     short loc_18004293F
0x18004292d  cmp     edx, 101Eh
0x180042933  jnz     short loc_18004293F
0x180042935  and     eax, 0FFFF101Fh
0x18004293a  or      eax, 101Fh
0x18004293f  mov     [r14+rcx*4], eax
0x180042943  inc     ecx
0x180042945  cmp     ecx, r9d
0x180042948  jb      short loc_180042918
0x18004294a  mov     rsi, [rsp+160h+var_110]
0x18004294f  mov     r14d, [rsp+160h+var_F8]
0x180042954  jmp     short loc_18004295A
0x180042956  mov     [rbp+60h+hMem], rcx
0x18004295a  mov     rcx, r12; this
0x18004295d  call    ?LockFile@CWABStorage@@AEAAHXZ; CWABStorage::LockFile(void)
0x180042962  test    eax, eax
0x180042964  jnz     short loc_180042970
0x180042966  mov     ebx, 80070005h
0x18004296b  jmp     loc_180042FAD
0x180042970  lea     rax, [rbp+60h+var_C8]
0x180042974  mov     [rsp+160h+var_EC], 1
0x18004297c  mov     [rsp+160h+var_138], rax; struct _SBinary **
0x180042981  mov     r9, rbx; struct _SPropertyRestriction *
0x180042984  lea     rax, [rsp+160h+var_130]
0x180042989  mov     r8d, r14d; unsigned int
0x18004298c  mov     rdx, rdi; struct _SBinary *
0x18004298f  mov     [rsp+160h+lpOverlapped], rax; unsigned int *
0x180042994  mov     rcx, r12; this
0x180042997  call    ?_FindRecordsWithoutLocking@CWABStorage@@AEAAJPEAU_SBinary@@KPEAU_SPropertyRestriction@@PEAKPEAPEAU2@@Z; CWABStorage::_FindRecordsWithoutLocking(_SBinary *,ulong,_SPropertyRestriction *,ulong *,_SBinary * *)
0x18004299c  mov     ebx, eax
0x18004299e  test    eax, eax
0x1800429a0  js      loc_180042FAD
0x1800429a6  cmp     [rsp+160h+var_130], r13d
0x1800429ab  jnz     short loc_1800429B7
0x1800429ad  mov     ebx, 8004010Fh
0x1800429b2  jmp     loc_180042FAD
0x1800429b7  mov     rcx, [r12+8]
0x1800429bc  lea     r8, [rsp+160h+hFile]; void **
0x1800429c1  mov     rcx, [rcx+10h]; lpFileName
0x1800429c5  call    ?OpenWABFile@@YAJPEAGPEAUHWND__@@PEAPEAX@Z; OpenWABFile(ushort *,HWND__ *,void * *)
0x1800429ca  mov     r13, [rsp+160h+hFile]
0x1800429cf  mov     ebx, eax
0x1800429d1  test    eax, eax
0x1800429d3  js      loc_180042FAD
0x1800429d9  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x1800429dd  jz      loc_180042FDC
0x1800429e3  xor     edx, edx; lpFileSizeHigh
0x1800429e5  mov     rcx, r13; hFile
0x1800429e8  call    cs:__imp_GetFileSize
0x1800429ee  mov     rcx, [r12+8]; struct _tagMPSWabFileInfo *
0x1800429f3  mov     rdx, r13; void *
0x1800429f6  mov     [rbp+60h+var_D8], eax
0x1800429f9  call    ?ReloadMPSWabFileInfo@@YAHPEAU_tagMPSWabFileInfo@@PEAX@Z; ReloadMPSWabFileInfo(_tagMPSWabFileInfo *,void *)
0x1800429fe  test    eax, eax
0x180042a00  jnz     short loc_180042A0C
0x180042a02  mov     ebx, 8004011Bh
0x180042a07  jmp     loc_180042FAD
0x180042a0c  mov     rcx, [r12+8]; struct _tagMPSWabFileInfo *
0x180042a11  mov     rax, [rcx+18h]
0x180042a15  test    dword ptr [rax+80h], 110h
0x180042a1f  jz      short loc_180042A44
0x180042a21  mov     rdx, r13; void *
0x180042a24  call    ?HrDoQuickWABIntegrityCheck@@YAJPEAU_tagMPSWabFileInfo@@PEAX@Z; HrDoQuickWABIntegrityCheck(_tagMPSWabFileInfo *,void *)
0x180042a29  test    eax, eax
0x180042a2b  jns     short loc_180042A44
0x180042a2d  mov     rcx, [r12+8]; struct _tagMPSWabFileInfo *
0x180042a32  mov     rdx, r13; void *
0x180042a35  call    ?HrDoDetailedWABIntegrityCheck@@YAJPEAU_tagMPSWabFileInfo@@PEAX@Z; HrDoDetailedWABIntegrityCheck(_tagMPSWabFileInfo *,void *)
0x180042a3a  mov     ebx, eax
0x180042a3c  test    eax, eax
0x180042a3e  js      loc_180042FAD
0x180042a44  cmp     [rsp+160h+var_130], 0FFFFFFEh
0x180042a4c  jbe     short loc_180042A58
0x180042a4e  mov     ebx, 8007000Eh
0x180042a53  jmp     loc_180042FAD
0x180042a58  mov     edx, [rsp+160h+var_130]
0x180042a5c  mov     ecx, 40h ; '@'; uFlags
0x180042a61  shl     rdx, 4
0x180042a65  add     rdx, 18h; uBytes
0x180042a69  call    cs:__imp_LocalAlloc
0x180042a6f  mov     r14, rax
0x180042a72  mov     [rbp+60h+var_98], rax
0x180042a76  mov     rax, [rbp+60h+var_A8]
0x180042a7a  mov     [rax], r14
0x180042a7d  test    r14, r14
0x180042a80  jz      short loc_180042A4E
0x180042a82  mov     eax, [rsp+160h+var_130]
0x180042a86  mov     [r14], eax
0x180042a89  xor     eax, eax
0x180042a8b  mov     [rsp+160h+var_11C], eax
0x180042a8f  xor     ecx, ecx
0x180042a91  mov     [rsp+160h+var_F4], ecx
0x180042a95  cmp     ecx, [rsp+160h+var_130]
0x180042a99  jnb     loc_180042FD5
0x180042a9f  mov     rax, [rbp+60h+var_C8]
0x180042aa3  mov     edx, ecx
0x180042aa5  add     rdx, rdx
0x180042aa8  mov     [rsp+160h+var_118], 0
0x180042ab0  cmp     dword ptr [rax+rdx*8], 4
0x180042ab4  jnb     short loc_180042ABC
0x180042ab6  mov     r8d, [rax+rdx*8]
0x180042aba  jmp     short loc_180042AC2
0x180042abc  mov     r8d, 4; Size
0x180042ac2  mov     rdx, [rax+rdx*8+8]; Src
0x180042ac7  lea     rcx, [rsp+160h+var_118]; void *
0x180042acc  call    memcpy_0
0x180042ad1  mov     rax, [r12+8]
0x180042ad6  lea     r9, [rsp+160h+var_100]; unsigned int *
0x180042adb  mov     edx, [rsp+160h+var_118]; unsigned int
0x180042adf  mov     r8, [rax+18h]
0x180042ae3  mov     rdi, [rax+28h]
0x180042ae7  mov     rcx, rdi; struct _tagMPSWabIndexEntryDataEntryID *
0x180042aea  mov     r8d, [r8+24h]; unsigned int
0x180042aee  call    ?BinSearchEID@@YAHPEAU_tagMPSWabIndexEntryDataEntryID@@KKPEAK@Z; BinSearchEID(_tagMPSWabIndexEntryDataEntryID *,ulong,ulong,ulong *)
0x180042af3  test    eax, eax
0x180042af5  jz      short loc_180042B66
0x180042af7  mov     ebx, [rsp+160h+var_100]
0x180042afb  lea     r8, [rbp+60h+var_70]; void *
0x180042aff  mov     r9d, 20h ; ' '; unsigned int
0x180042b05  mov     rcx, r13; hFile
0x180042b08  mov     edi, [rdi+rbx*8+4]
0x180042b0c  mov     edx, edi; unsigned int
0x180042b0e  call    ?ReadDataFromWABFile@@YAHPEAXK0K@Z; ReadDataFromWABFile(void *,ulong,void *,ulong)
0x180042b13  test    eax, eax
0x180042b15  jz      loc_180042FCE
0x180042b1b  mov     rax, [r12+8]
0x180042b20  mov     r8d, edi
0x180042b23  movups  xmm1, xmmword ptr [rbp+60h+var_70]
0x180042b27  mov     r9d, [rbp+60h+var_D8]
0x180042b2b  movups  xmm0, xmmword ptr [rbp+60h+uBytes]
0x180042b2f  mov     rcx, [rax+28h]
0x180042b33  mov     rdx, [rax+18h]
0x180042b37  movaps  [rbp+60h+var_90], xmm1
0x180042b3b  movaps  [rbp+60h+var_80], xmm0
0x180042b3f  mov     eax, [rcx+rbx*8]
0x180042b42  lea     rcx, [rbp+60h+var_90]
0x180042b46  mov     edx, [rdx+14h]
0x180042b49  mov     dword ptr [rsp+160h+var_138], eax
0x180042b4d  mov     dword ptr [rsp+160h+lpOverlapped], 1
0x180042b55  call    ?bIsValidRecord@@YAHU_tagMPSWabRecordHeader@@KKKHK@Z; bIsValidRecord(_tagMPSWabRecordHeader,ulong,ulong,ulong,int,ulong)
0x180042b5a  test    eax, eax
0x180042b5c  jnz     short loc_180042B75
0x180042b5e  mov     [rsp+160h+var_F0], 1
0x180042b66  mov     eax, [rsp+160h+var_11C]
0x180042b6a  mov     ecx, [rsp+160h+var_F4]
0x180042b6e  inc     ecx
0x180042b70  jmp     loc_180042A91
0x180042b75  psrldq  xmm1, 4
0x180042b7a  movd    eax, xmm1
0x180042b7e  cmp     eax, 3
0x180042b81  jz      short loc_180042B66
0x180042b83  mov     edi, [rsp+160h+var_104]
0x180042b87  mov     ecx, 40h ; '@'; uFlags
0x180042b8c  movsxd  rsi, [rsp+160h+var_11C]
0x180042b91  mov     ebx, edi
0x180042b93  shl     rsi, 4
0x180042b97  mov     [rbp+60h+var_B8], rsi
0x180042b9b  lea     rdx, [rdi+rdi*2]
0x180042b9f  shl     rdx, 3; uBytes
0x180042ba3  mov     [rsi+r14+0Ch], edi
0x180042ba8  call    cs:__imp_LocalAlloc
0x180042bae  mov     [rsi+r14+10h], rax
0x180042bb3  test    rax, rax
0x180042bb6  jz      loc_180042FC7
0x180042bbc  xor     edx, edx
0x180042bbe  mov     rax, [rsi+r14+10h]
0x180042bc3  lea     rcx, [rdx+rdx*2]
0x180042bc7  inc     edx
0x180042bc9  mov     dword ptr [rax+rcx*8], 0Ah
0x180042bd0  cmp     edx, edi
0x180042bd2  jb      short loc_180042BBE
0x180042bd4  lea     rcx, [rsp+160h+var_E8]; void **
0x180042bd9  call    ?LocalFreeAndNull@@YAXPEAPEAX@Z; LocalFreeAndNull(void * *)
0x180042bde  mov     edx, dword ptr [rbp+60h+uBytes+0Ch]; uBytes
0x180042be1  mov     edi, 40h ; '@'
0x180042be6  mov     ecx, edi; uFlags
0x180042be8  call    cs:__imp_LocalAlloc
0x180042bee  mov     [rsp+160h+var_110], rax
0x180042bf3  mov     rsi, rax
0x180042bf6  mov     [rsp+160h+var_E8], rax
0x180042bfb  test    rax, rax
0x180042bfe  jz      loc_180042A4E
0x180042c04  mov     edx, dword ptr [rbp+60h+uBytes+4]; lDistanceToMove
0x180042c07  lea     r9d, [rdi-3Fh]; dwMoveMethod
0x180042c0b  xor     r8d, r8d; lpDistanceToMoveHigh
0x180042c0e  mov     rcx, r13; hFile
0x180042c11  call    cs:__imp_SetFilePointer
0x180042c17  cmp     eax, 0FFFFFFFFh
0x180042c1a  jz      loc_180042A02
0x180042c20  mov     r8d, dword ptr [rbp+60h+uBytes+0Ch]; nNumberOfBytesToRead
0x180042c24  lea     r9, [rsp+160h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180042c29  mov     rdx, rsi; lpBuffer
0x180042c2c  mov     [rsp+160h+lpOverlapped], 0; lpOverlapped
0x180042c35  mov     rcx, r13; hFile
0x180042c38  call    cs:__imp_ReadFile
0x180042c3e  test    eax, eax
0x180042c40  jz      loc_180042FCE
0x180042c46  mov     edx, dword ptr [rbp+60h+uBytes+0Ch]; unsigned int
0x180042c49  cmp     [rsp+160h+NumberOfBytesRead], edx
0x180042c4d  jnz     loc_180042A02
0x180042c53  mov     r8d, [rbp+60h+var_70+0Ch]; unsigned int
0x180042c57  mov     rcx, rsi; unsigned __int8 *
0x180042c5a  call    ?SecurityCheckPropArrayBuffer@@YAHPEAEKK@Z; SecurityCheckPropArrayBuffer(uchar *,ulong,ulong)
0x180042c5f  test    eax, eax
0x180042c61  jz      loc_180042A02
0x180042c67  lea     rcx, [rbp+60h+var_E0]; void **
0x180042c6b  call    ?LocalFreeAndNull@@YAXPEAPEAX@Z; LocalFreeAndNull(void * *)
0x180042c70  shl     rbx, 2
0x180042c74  mov     ecx, edi; uFlags
0x180042c76  mov     rdx, rbx; uBytes
0x180042c79  call    cs:__imp_LocalAlloc
0x180042c7f  mov     [rsp+160h+hFile], rax
0x180042c84  mov     r15, rax
0x180042c87  mov     [rbp+60h+var_E0], rax
0x180042c8b  test    rax, rax
0x180042c8e  jz      loc_180042A4E
0x180042c94  and     rbx, 0FFFFFFFFFFFFFFFCh
0x180042c98  xor     edx, edx; Val
0x180042c9a  mov     r8, rbx; Size
0x180042c9d  mov     rcx, rax; void *
0x180042ca0  call    memset_0
0x180042ca5  xor     ecx, ecx
0x180042ca7  mov     rdi, rsi
0x180042caa  mov     [rsp+160h+var_108], ecx
0x180042cae  xor     edx, edx
0x180042cb0  mov     [rsp+160h+var_120], edx
0x180042cb4  cmp     edx, [rbp+60h+var_70+0Ch]
  ... truncated ...
```
