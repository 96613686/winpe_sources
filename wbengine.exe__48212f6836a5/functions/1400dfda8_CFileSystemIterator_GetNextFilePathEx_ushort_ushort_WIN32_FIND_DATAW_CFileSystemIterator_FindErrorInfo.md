# CFileSystemIterator::GetNextFilePathEx(ushort * *,ushort * *,_WIN32_FIND_DATAW *,CFileSystemIterator::FindErrorInfo *)

- ea: `0x1400dfda8`
- end: `0x1400e01fb`
- name: `?GetNextFilePathEx@CFileSystemIterator@@AEAAJPEAPEAG0PEAU_WIN32_FIND_DATAW@@PEAUFindErrorInfo@1@@Z`
- size: `1107`
- prototype: `__int64 __usercall@<rax>(CFileSystemIterator *__hidden this@<rcx>, unsigned __int16 **@<rdx>, unsigned __int16 **@<r8>, struct _WIN32_FIND_DATAW *@<r9>, struct CFileSystemIterator::FindErrorInfo *)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1400dfb2c`

## callees

- `0x140006984`
- `0x140006ca8`
- `0x140006d88`
- `0x1400da05c`
- `0x1400db9b8`
- `0x1400dba10`
- `0x1400dee78`
- `0x1400df3bc`
- `0x1400df638`
- `0x1400df8e0`
- `0x1400dfda8`
- `0x1400e0204`
- `0x1400e0428`
- `0x1400e08f4`
- `0x1400e4518`
- `0x1400e4844`
- `0x140133760`
- `0x140134d20`

## import_xrefs

- `KERNEL32!RaiseException` at `0x1400e012e`
- `KERNEL32!RaiseException` at `0x1400e0176`
- `KERNEL32!RaiseException` at `0x1400e019b`
- `KERNEL32!RaiseException` at `0x1400e012e`
- `KERNEL32!RaiseException` at `0x1400e0176`
- `KERNEL32!RaiseException` at `0x1400e019b`
- `msvcrt!_wcsnicmp` at `0x1400e0051`
- `msvcrt!_wcsnicmp` at `0x1400e0051`

## string_xrefs

- `0x1400dfdf8`: `base\stor\blb\dsm\dsmfs\dll\filesystemiterator.cpp`
- `0x1400dfe42`: `base\stor\blb\dsm\dsmfs\dll\filesystemiterator.cpp`
- `0x1400dff20`: `base\stor\blb\dsm\dsmfs\dll\filesystemiterator.cpp`
- `0x1400dff3e`: `base\stor\blb\dsm\dsmfs\dll\filesystemiterator.cpp`
- `0x1400dff90`: `base\stor\blb\dsm\dsmfs\dll\filesystemiterator.cpp`
- `0x1400dffb9`: `base\stor\blb\dsm\dsmfs\dll\filesystemiterator.cpp`
- `0x1400e0067`: `base\stor\blb\dsm\dsmfs\dll\filesystemiterator.cpp`
- `0x1400e00ee`: `base\stor\blb\dsm\dsmfs\dll\filesystemiterator.cpp`
- `0x1400e01cd`: `base\stor\blb\dsm\dsmfs\dll\filesystemiterator.cpp`
- `0x1400dfeda`: `base\stor\blb\dsm\dsmfs\dll\filesystemiterator.cpp`
- `0x1400dfdec`: `ppstrFilePath && ppstrSnapshotPath`
- `0x1400dfee8`: `CFileSystemIterator::GetNextFilePathEx: Directory search error`
- `0x1400dff84`: `(pstrIteratorPath != 0) || (hr == ((HRESULT)1L))`
- `0x1400e005b`: `_wcsnicmp(pstrIteratorPath, m_pIncludeFiles->ssFilePath.PeekStr(), wcslen(pstrIteratorPath)) == 0`
- `0x1400e00e2`: `strChildPath == (strLogicalFilePath.PeekStr() + (strLogicalFilePath.Length() - strChildPath.Length()))`
- `0x1400dff14`: `*ppstrFilePath == 0`
- `0x1400dff32`: `*ppstrSnapshotPath == 0`
- `0x1400e01c1`: `pstrIteratorPath == 0`

## pseudocode

```c
__int64 __fastcall CFileSystemIterator::GetNextFilePathEx(
        CFileSystemIterator *this,
        const wchar_t **a2,
        const wchar_t **a3,
        struct _WIN32_FIND_DATAW *a4,
        struct CFileSystemIterator::FindErrorInfo *a5)
{
  int v9; // esi
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int NextFile; // eax
  unsigned int v15; // edx
  CFileSystemIterator::IncludeFiles *v16; // rcx
  void *v17; // rcx
  const wchar_t *v18; // rdi
  __int64 v19; // rdx
  __int64 v20; // r15
  size_t v21; // r8
  int v22; // ebx
  int v23; // r15d
  signed int v24; // eax
  __int64 **v25; // rcx
  signed int v26; // eax
  signed int v27; // eax
  void *Block[2]; // [rsp+30h] [rbp-B1h] BYREF
  __int64 v30; // [rsp+40h] [rbp-A1h] BYREF
  int v31; // [rsp+48h] [rbp-99h]
  _WORD *v32; // [rsp+50h] [rbp-91h]
  int v33; // [rsp+58h] [rbp-89h]
  char v34; // [rsp+5Ch] [rbp-85h]
  _WORD v35[24]; // [rsp+60h] [rbp-81h] BYREF
  __int64 *v36; // [rsp+90h] [rbp-51h] BYREF
  int v37; // [rsp+98h] [rbp-49h]
  CFileSystemIterator **v38; // [rsp+A0h] [rbp-41h]
  int v39; // [rsp+A8h] [rbp-39h]
  char v40; // [rsp+ACh] [rbp-35h]
  CFileSystemIterator *v41; // [rsp+B0h] [rbp-31h] BYREF

  if ( !a2 || !a3 )
    BlbAssert("base\\stor\\blb\\dsm\\dsmfs\\dll\\filesystemiterator.cpp", 0xFAu, "ppstrFilePath && ppstrSnapshotPath");
  *a3 = 0;
  v9 = 0;
  *a2 = 0;
  Block[0] = 0;
  do
  {
    v10 = *((_DWORD *)this + 214);
    if ( v10 )
    {
      v11 = v10 - 1;
      if ( v11 )
      {
        v12 = v11 - 1;
        if ( v12 )
        {
          v13 = v12 - 1;
          if ( v13 )
          {
            if ( v13 != 1 )
            {
              BlbAssert("base\\stor\\blb\\dsm\\dsmfs\\dll\\filesystemiterator.cpp", 0x11Eu, "false");
              continue;
            }
            NextFile = CFileSystemIterator::GetNextFile(this, (unsigned __int16 **)Block, a4, a5);
          }
          else
          {
            NextFile = CFileSystemIterator::GetFirstFile(this, (unsigned __int16 **)Block, a4, a5);
          }
        }
        else
        {
          NextFile = CFileSystemIterator::GetNextDirectory(this, (unsigned __int16 **)Block, a4, a5);
        }
      }
      else
      {
        NextFile = CFileSystemIterator::GetNextParent(this, (unsigned __int16 **)Block, a4, a5);
      }
    }
    else
    {
      NextFile = CFileSystemIterator::GetNextInclude(this, a5);
    }
    v9 = NextFile;
  }
  while ( v9 == -2147023650 );
  if ( v9 < 0 )
  {
    v37 = v9;
    v36 = g_traceProviderTRACE_COMPONENT_DSM;
    v39 = 298;
    v38 = (CFileSystemIterator **)L"base\\stor\\blb\\dsm\\dsmfs\\dll\\filesystemiterator.cpp";
    v41 = this;
    CTraceFailureHelper::TraceMessage(
      (CTraceFailureHelper *)&v36,
      L"%ws: lVal : %S",
      L"CFileSystemIterator::GetNextFilePathEx: Directory search error",
      "hr");
    *((_DWORD *)this + 214) = 0;
    if ( *a2 )
      BlbAssert("base\\stor\\blb\\dsm\\dsmfs\\dll\\filesystemiterator.cpp", 0x176u, "*ppstrFilePath == 0");
    if ( *a3 )
      BlbAssert("base\\stor\\blb\\dsm\\dsmfs\\dll\\filesystemiterator.cpp", 0x177u, "*ppstrSnapshotPath == 0");
    v16 = (CFileSystemIterator::IncludeFiles *)*((_QWORD *)this + 3);
    if ( v16 )
      CFileSystemIterator::IncludeFiles::`scalar deleting destructor'(v16, v15);
    v17 = Block[0];
    *((_QWORD *)this + 3) = 0;
    operator delete[](v17);
    goto LABEL_52;
  }
  v18 = (const wchar_t *)Block[0];
  if ( Block[0] )
  {
    if ( v9 != 1 )
      goto LABEL_30;
  }
  else if ( v9 != 1 )
  {
    BlbAssert(
      "base\\stor\\blb\\dsm\\dsmfs\\dll\\filesystemiterator.cpp",
      0x12Eu,
      "(pstrIteratorPath != 0) || (hr == ((HRESULT)1L))");
LABEL_30:
    if ( !*((_QWORD *)this + 3) )
      BlbAssert("base\\stor\\blb\\dsm\\dsmfs\\dll\\filesystemiterator.cpp", 0x134u, "m_pIncludeFiles != NULL");
    v19 = *((_QWORD *)this + 3);
    if ( *(_DWORD *)(v19 + 184) )
    {
      v30 = 0;
      v31 = 24;
      v33 = 0;
      v35[0] = 0;
      if ( *((_DWORD *)this + 214) == 1 )
      {
        v36 = 0;
        v38 = &v41;
        v39 = 0;
        LOWORD(v41) = 0;
        v40 = v40 & 0xF8 | 2;
        v20 = -1;
        v37 = 24;
        v32 = v35;
        v21 = -1;
        v34 = v34 & 0xF8 | 2;
        do
          ++v21;
        while ( v18[v21] );
        if ( _wcsnicmp(v18, *(const wchar_t **)(v19 + 16), v21) )
          BlbAssert(
            "base\\stor\\blb\\dsm\\dsmfs\\dll\\filesystemiterator.cpp",
            0x14Cu,
            "_wcsnicmp(pstrIteratorPath, m_pIncludeFiles->ssFilePath.PeekStr(), wcslen(pstrIteratorPath)) == 0");
        CoreSDK::CSmartStrTemplateBase<unsigned short>::SSSet(
          &v36,
          *(_QWORD *)(*((_QWORD *)this + 3) + 176LL),
          *(unsigned int *)(*((_QWORD *)this + 3) + 184LL));
        do
          ++v20;
        while ( v18[v20] );
        CoreSDK::CSmartStrTemplateBase<unsigned short>::Set(&v30, *(_QWORD *)(*((_QWORD *)this + 3) + 16LL) + 2 * v20);
        v22 = v39;
        v23 = v33;
        if ( (unsigned int)CoreSDK::CSmartStrTemplateBase<unsigned short>::Compare(
                             (unsigned int)&v30,
                             (int)v38 + 2 * (v39 - v33),
                             1,
                             -1,
                             0) )
        {
          BlbAssert(
            "base\\stor\\blb\\dsm\\dsmfs\\dll\\filesystemiterator.cpp",
            0x156u,
            "strChildPath == (strLogicalFilePath.PeekStr() + (strLogicalFilePath.Length() - strChildPath.Length()))");
          v22 = v39;
          v23 = v33;
        }
        Truncate(&v36, (unsigned int)(v22 - v23));
        v24 = Copy(&v36, a2);
        if ( v24 < 0 )
          RaiseException(v24, 1u, 0, 0);
        CoreSDK::CSmartStrTemplateBase<unsigned short>::~CSmartStrTemplateBase<unsigned short>((__int64)&v30);
        v25 = &v36;
      }
      else
      {
        v32 = v35;
        v34 = v34 & 0xF8 | 2;
        v26 = CoreSDK::CSmartStrTemplateBase<unsigned short>::Set(&v30, v18);
        if ( v26 < 0 )
          RaiseException(v26, 1u, 0, 0);
        v27 = CFileSystemIterator::MapActualFilePathToLogicalFilePath(this, &v30, a2);
        if ( v27 < 0 )
          RaiseException(v27, 1u, 0, 0);
        v25 = (__int64 **)&v30;
      }
      CoreSDK::CSmartStrTemplateBase<unsigned short>::~CSmartStrTemplateBase<unsigned short>((__int64)v25);
      *a3 = v18;
    }
    else
    {
      *a2 = v18;
      *a3 = 0;
    }
LABEL_52:
    v18 = 0;
  }
  if ( v18 )
    BlbAssert("base\\stor\\blb\\dsm\\dsmfs\\dll\\filesystemiterator.cpp", 0x17Fu, "pstrIteratorPath == 0");
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1400dfda8  push    rbp
0x1400dfdaa  push    rbx
0x1400dfdab  push    rsi
0x1400dfdac  push    rdi
0x1400dfdad  push    r12
0x1400dfdaf  push    r13
0x1400dfdb1  push    r14
0x1400dfdb3  push    r15
0x1400dfdb5  lea     rbp, [rsp-17h]
0x1400dfdba  sub     rsp, 0F8h
0x1400dfdc1  mov     rax, cs:__security_cookie
0x1400dfdc8  xor     rax, rsp
0x1400dfdcb  mov     [rbp+4Fh+var_50], rax
0x1400dfdcf  mov     rdi, [rbp+4Fh+arg_20]
0x1400dfdd3  xor     r15d, r15d
0x1400dfdd6  mov     r14, r9
0x1400dfdd9  mov     r13, r8
0x1400dfddc  mov     r12, rdx
0x1400dfddf  mov     rbx, rcx
0x1400dfde2  test    rdx, rdx
0x1400dfde5  jz      short loc_1400DFDEC
0x1400dfde7  test    r8, r8
0x1400dfdea  jnz     short loc_1400DFE04
0x1400dfdec  lea     r8, aPpstrfilepathP; "ppstrFilePath && ppstrSnapshotPath"
0x1400dfdf3  mov     edx, 0FAh; unsigned int
0x1400dfdf8  lea     rcx, aBaseStorBlbDsm; "base\\stor\\blb\\dsm\\dsmfs\\dll\\files"...
0x1400dfdff  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x1400dfe04  mov     [r13+0], r15
0x1400dfe08  mov     esi, r15d
0x1400dfe0b  mov     [r12], r15
0x1400dfe0f  mov     [rsp+130h+Block], r15
0x1400dfe14  mov     ecx, [rbx+358h]
0x1400dfe1a  test    ecx, ecx
0x1400dfe1c  jz      loc_1400DFEA4
0x1400dfe22  sub     ecx, 1
0x1400dfe25  jz      short loc_1400DFE8F
0x1400dfe27  sub     ecx, 1
0x1400dfe2a  jz      short loc_1400DFE7A
0x1400dfe2c  sub     ecx, 1
0x1400dfe2f  jz      short loc_1400DFE65
0x1400dfe31  cmp     ecx, 1
0x1400dfe34  jz      short loc_1400DFE50
0x1400dfe36  lea     r8, aFalse; "false"
0x1400dfe3d  mov     edx, 11Eh; unsigned int
0x1400dfe42  lea     rcx, aBaseStorBlbDsm; "base\\stor\\blb\\dsm\\dsmfs\\dll\\files"...
0x1400dfe49  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x1400dfe4e  jmp     short loc_1400DFEB1
0x1400dfe50  mov     r9, rdi; struct CFileSystemIterator::FindErrorInfo *
0x1400dfe53  lea     rdx, [rsp+130h+Block]; unsigned __int16 **
0x1400dfe58  mov     r8, r14; struct _WIN32_FIND_DATAW *
0x1400dfe5b  mov     rcx, rbx; this
0x1400dfe5e  call    ?GetNextFile@CFileSystemIterator@@AEAAJPEAPEAGPEAU_WIN32_FIND_DATAW@@PEAUFindErrorInfo@1@@Z; CFileSystemIterator::GetNextFile(ushort * *,_WIN32_FIND_DATAW *,CFileSystemIterator::FindErrorInfo *)
0x1400dfe63  jmp     short loc_1400DFEAF
0x1400dfe65  mov     r9, rdi; struct CFileSystemIterator::FindErrorInfo *
0x1400dfe68  lea     rdx, [rsp+130h+Block]; unsigned __int16 **
0x1400dfe6d  mov     r8, r14; struct _WIN32_FIND_DATAW *
0x1400dfe70  mov     rcx, rbx; this
0x1400dfe73  call    ?GetFirstFile@CFileSystemIterator@@AEAAJPEAPEAGPEAU_WIN32_FIND_DATAW@@PEAUFindErrorInfo@1@@Z; CFileSystemIterator::GetFirstFile(ushort * *,_WIN32_FIND_DATAW *,CFileSystemIterator::FindErrorInfo *)
0x1400dfe78  jmp     short loc_1400DFEAF
0x1400dfe7a  mov     r9, rdi; struct CFileSystemIterator::FindErrorInfo *
0x1400dfe7d  lea     rdx, [rsp+130h+Block]; unsigned __int16 **
0x1400dfe82  mov     r8, r14; struct _WIN32_FIND_DATAW *
0x1400dfe85  mov     rcx, rbx; this
0x1400dfe88  call    ?GetNextDirectory@CFileSystemIterator@@AEAAJPEAPEAGPEAU_WIN32_FIND_DATAW@@PEAUFindErrorInfo@1@@Z; CFileSystemIterator::GetNextDirectory(ushort * *,_WIN32_FIND_DATAW *,CFileSystemIterator::FindErrorInfo *)
0x1400dfe8d  jmp     short loc_1400DFEAF
0x1400dfe8f  mov     r9, rdi; struct CFileSystemIterator::FindErrorInfo *
0x1400dfe92  lea     rdx, [rsp+130h+Block]; unsigned __int16 **
0x1400dfe97  mov     r8, r14; struct _WIN32_FIND_DATAW *
0x1400dfe9a  mov     rcx, rbx; this
0x1400dfe9d  call    ?GetNextParent@CFileSystemIterator@@AEAAJPEAPEAGPEAU_WIN32_FIND_DATAW@@PEAUFindErrorInfo@1@@Z; CFileSystemIterator::GetNextParent(ushort * *,_WIN32_FIND_DATAW *,CFileSystemIterator::FindErrorInfo *)
0x1400dfea2  jmp     short loc_1400DFEAF
0x1400dfea4  mov     rdx, rdi; struct CFileSystemIterator::FindErrorInfo *
0x1400dfea7  mov     rcx, rbx; this
0x1400dfeaa  call    ?GetNextInclude@CFileSystemIterator@@AEAAJPEAUFindErrorInfo@1@@Z; CFileSystemIterator::GetNextInclude(CFileSystemIterator::FindErrorInfo *)
0x1400dfeaf  mov     esi, eax
0x1400dfeb1  cmp     esi, 800704DEh
0x1400dfeb7  jz      loc_1400DFE14
0x1400dfebd  test    esi, esi
0x1400dfebf  jns     loc_1400DFF6B
0x1400dfec5  lea     rax, ?g_traceProviderTRACE_COMPONENT_DSM@@3VCTraceProvider@@A; CTraceProvider g_traceProviderTRACE_COMPONENT_DSM
0x1400dfecc  mov     [rbp+4Fh+var_98], esi
0x1400dfecf  mov     [rbp+4Fh+var_A0], rax
0x1400dfed3  lea     r9, aHr; "hr"
0x1400dfeda  lea     rax, aBaseStorBlbDsm_15; "base\\stor\\blb\\dsm\\dsmfs\\dll\\files"...
0x1400dfee1  mov     [rbp+4Fh+var_88], 12Ah
0x1400dfee8  lea     r8, aCfilesystemite; "CFileSystemIterator::GetNextFilePathEx:"...
0x1400dfeef  mov     [rbp+4Fh+var_90], rax
0x1400dfef3  lea     rdx, aWsLvalS; "%ws: lVal : %S"
0x1400dfefa  mov     [rbp+4Fh+var_80], rbx
0x1400dfefe  lea     rcx, [rbp+4Fh+var_A0]; this
0x1400dff02  call    ?TraceMessage@CTraceFailureHelper@@QEAAXPEBGZZ; CTraceFailureHelper::TraceMessage(ushort const *,...)
0x1400dff07  mov     [rbx+358h], r15d
0x1400dff0e  cmp     [r12], r15
0x1400dff12  jz      short loc_1400DFF2C
0x1400dff14  lea     r8, aPpstrfilepath0_0; "*ppstrFilePath == 0"
0x1400dff1b  mov     edx, 176h; unsigned int
0x1400dff20  lea     rcx, aBaseStorBlbDsm; "base\\stor\\blb\\dsm\\dsmfs\\dll\\files"...
0x1400dff27  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x1400dff2c  cmp     [r13+0], r15
0x1400dff30  jz      short loc_1400DFF4A
0x1400dff32  lea     r8, aPpstrsnapshotp; "*ppstrSnapshotPath == 0"
0x1400dff39  mov     edx, 177h; unsigned int
0x1400dff3e  lea     rcx, aBaseStorBlbDsm; "base\\stor\\blb\\dsm\\dsmfs\\dll\\files"...
0x1400dff45  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x1400dff4a  mov     rcx, [rbx+18h]; this
0x1400dff4e  test    rcx, rcx
0x1400dff51  jz      short loc_1400DFF58
0x1400dff53  call    ??_GIncludeFiles@CFileSystemIterator@@QEAAPEAXI@Z; CFileSystemIterator::IncludeFiles::`scalar deleting destructor'(uint)
0x1400dff58  mov     rcx, [rsp+130h+Block]; Block
0x1400dff5d  mov     [rbx+18h], r15
0x1400dff61  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x1400dff66  jmp     loc_1400E01B9
0x1400dff6b  mov     rdi, [rsp+130h+Block]
0x1400dff70  mov     r14d, 1
0x1400dff76  test    rdi, rdi
0x1400dff79  jnz     short loc_1400DFF9E
0x1400dff7b  cmp     esi, r14d
0x1400dff7e  jz      loc_1400E01BC
0x1400dff84  lea     r8, aPstriteratorpa_0; "(pstrIteratorPath != 0) || (hr == ((HRE"...
0x1400dff8b  mov     edx, 12Eh; unsigned int
0x1400dff90  lea     rcx, aBaseStorBlbDsm; "base\\stor\\blb\\dsm\\dsmfs\\dll\\files"...
0x1400dff97  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x1400dff9c  jmp     short loc_1400DFFA7
0x1400dff9e  cmp     esi, r14d
0x1400dffa1  jz      loc_1400E01BC
0x1400dffa7  cmp     [rbx+18h], r15
0x1400dffab  jnz     short loc_1400DFFC5
0x1400dffad  lea     r8, aMPincludefiles_1; "m_pIncludeFiles != NULL"
0x1400dffb4  mov     edx, 134h; unsigned int
0x1400dffb9  lea     rcx, aBaseStorBlbDsm; "base\\stor\\blb\\dsm\\dsmfs\\dll\\files"...
0x1400dffc0  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x1400dffc5  mov     rdx, [rbx+18h]
0x1400dffc9  cmp     [rdx+0B8h], r15d
0x1400dffd0  jz      loc_1400E01B1
0x1400dffd6  mov     [rsp+130h+var_F0], r15
0x1400dffdb  mov     [rsp+130h+var_E8], 18h
0x1400dffe3  mov     [rsp+130h+var_D8], r15d
0x1400dffe8  mov     [rsp+130h+var_D0], r15w
0x1400dffee  cmp     [rbx+358h], r14d
0x1400dfff5  jnz     loc_1400E0144
0x1400dfffb  lea     rax, [rbp+4Fh+var_80]
0x1400dffff  mov     [rbp+4Fh+var_A0], r15
0x1400e0003  mov     [rbp+4Fh+var_90], rax
0x1400e0007  mov     al, [rbp+4Fh+var_84]
0x1400e000a  and     al, 0FAh
0x1400e000c  mov     [rbp+4Fh+var_88], r15d
0x1400e0010  or      al, 2
0x1400e0012  mov     word ptr [rbp+4Fh+var_80], r15w
0x1400e0017  mov     [rbp+4Fh+var_84], al
0x1400e001a  or      r15, 0FFFFFFFFFFFFFFFFh
0x1400e001e  lea     rax, [rsp+130h+var_D0]
0x1400e0023  mov     [rbp+4Fh+var_98], 18h
0x1400e002a  mov     [rsp+130h+var_E0], rax
0x1400e002f  mov     r8, r15
0x1400e0032  mov     al, [rsp+130h+var_D4]
0x1400e0036  and     al, 0FAh
0x1400e0038  or      al, 2
0x1400e003a  mov     [rsp+130h+var_D4], al
0x1400e003e  xor     eax, eax
0x1400e0040  inc     r8; MaxCount
0x1400e0043  cmp     [rdi+r8*2], ax
0x1400e0048  jnz     short loc_1400E0040
0x1400e004a  mov     rdx, [rdx+10h]; String2
0x1400e004e  mov     rcx, rdi; String1
0x1400e0051  call    cs:__imp__wcsnicmp
0x1400e0057  test    eax, eax
0x1400e0059  jz      short loc_1400E0073
0x1400e005b  lea     r8, aWcsnicmpPstrit; "_wcsnicmp(pstrIteratorPath, m_pIncludeF"...
0x1400e0062  mov     edx, 14Ch; unsigned int
0x1400e0067  lea     rcx, aBaseStorBlbDsm; "base\\stor\\blb\\dsm\\dsmfs\\dll\\files"...
0x1400e006e  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x1400e0073  mov     rdx, [rbx+18h]
0x1400e0077  lea     rcx, [rbp+4Fh+var_A0]
0x1400e007b  mov     r8d, [rdx+0B8h]
0x1400e0082  mov     rdx, [rdx+0B0h]
0x1400e0089  call    ?SSSet@?$CSmartStrTemplateBase@G@CoreSDK@@AEAAJPEBGK@Z; CoreSDK::CSmartStrTemplateBase<ushort>::SSSet(ushort const *,ulong)
0x1400e008e  xor     eax, eax
0x1400e0090  inc     r15
0x1400e0093  cmp     [rdi+r15*2], ax
0x1400e0098  jnz     short loc_1400E0090
0x1400e009a  mov     rax, [rbx+18h]
0x1400e009e  mov     rcx, [rax+10h]
0x1400e00a2  lea     rdx, [rcx+r15*2]
0x1400e00a6  lea     rcx, [rsp+130h+var_F0]
0x1400e00ab  call    ?Set@?$CSmartStrTemplateBase@G@CoreSDK@@QEAAJPEBG@Z; CoreSDK::CSmartStrTemplateBase<ushort>::Set(ushort const *)
0x1400e00b0  mov     rax, [rbp+4Fh+var_90]
0x1400e00b4  or      r9d, 0FFFFFFFFh
0x1400e00b8  mov     ebx, [rbp+4Fh+var_88]
0x1400e00bb  mov     r8d, r14d
0x1400e00be  mov     r15d, [rsp+130h+var_D8]
0x1400e00c3  mov     ecx, ebx
0x1400e00c5  sub     ecx, r15d
0x1400e00c8  mov     [rsp+130h+var_110], 0
0x1400e00d0  lea     rdx, [rax+rcx*2]
0x1400e00d4  lea     rcx, [rsp+130h+var_F0]
0x1400e00d9  call    ?Compare@?$CSmartStrTemplateBase@G@CoreSDK@@QEBAHPEBGHKK@Z; CoreSDK::CSmartStrTemplateBase<ushort>::Compare(ushort const *,int,ulong,ulong)
0x1400e00de  test    eax, eax
0x1400e00e0  jz      short loc_1400E0102
0x1400e00e2  lea     r8, aStrchildpathSt; "strChildPath == (strLogicalFilePath.Pee"...
0x1400e00e9  mov     edx, 156h; unsigned int
0x1400e00ee  lea     rcx, aBaseStorBlbDsm; "base\\stor\\blb\\dsm\\dsmfs\\dll\\files"...
0x1400e00f5  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x1400e00fa  mov     ebx, [rbp+4Fh+var_88]
0x1400e00fd  mov     r15d, [rsp+130h+var_D8]
0x1400e0102  sub     ebx, r15d
0x1400e0105  lea     rcx, [rbp+4Fh+var_A0]
0x1400e0109  mov     edx, ebx
0x1400e010b  call    ?Truncate@@YAXAEAV?$CSmartStrTemplate@G$0BI@@CoreSDK@@K@Z; Truncate(CoreSDK::CSmartStrTemplate<ushort,24> &,ulong)
0x1400e0110  mov     rdx, r12
0x1400e0113  lea     rcx, [rbp+4Fh+var_A0]
0x1400e0117  call    ?Copy@@YAJAEAV?$CSmartStrTemplate@G$0BI@@CoreSDK@@PEAPEAG@Z; Copy(CoreSDK::CSmartStrTemplate<ushort,24> &,ushort * *)
0x1400e011c  xor     r15d, r15d
0x1400e011f  test    eax, eax
0x1400e0121  jns     short loc_1400E0134
0x1400e0123  xor     r9d, r9d; lpArguments
0x1400e0126  xor     r8d, r8d; nNumberOfArguments
0x1400e0129  mov     edx, r14d; dwExceptionFlags
0x1400e012c  mov     ecx, eax; dwExceptionCode
0x1400e012e  call    cs:__imp_RaiseException
0x1400e0134  lea     rcx, [rsp+130h+var_F0]
0x1400e0139  call    ??1?$CSmartStrTemplateBase@G@CoreSDK@@IEAA@XZ; CoreSDK::CSmartStrTemplateBase<ushort>::~CSmartStrTemplateBase<ushort>(void)
0x1400e013e  lea     rcx, [rbp+4Fh+var_A0]
0x1400e0142  jmp     short loc_1400E01A6
0x1400e0144  lea     rax, [rsp+130h+var_D0]
0x1400e0149  mov     rdx, rdi
0x1400e014c  mov     [rsp+130h+var_E0], rax
0x1400e0151  lea     rcx, [rsp+130h+var_F0]
0x1400e0156  mov     al, [rsp+130h+var_D4]
0x1400e015a  and     al, 0FAh
0x1400e015c  or      al, 2
0x1400e015e  mov     [rsp+130h+var_D4], al
0x1400e0162  call    ?Set@?$CSmartStrTemplateBase@G@CoreSDK@@QEAAJPEBG@Z; CoreSDK::CSmartStrTemplateBase<ushort>::Set(ushort const *)
0x1400e0167  test    eax, eax
0x1400e0169  jns     short loc_1400E017C
0x1400e016b  xor     r9d, r9d; lpArguments
0x1400e016e  xor     r8d, r8d; nNumberOfArguments
0x1400e0171  mov     edx, r14d; dwExceptionFlags
0x1400e0174  mov     ecx, eax; dwExceptionCode
0x1400e0176  call    cs:__imp_RaiseException
0x1400e017c  mov     r8, r12
0x1400e017f  lea     rdx, [rsp+130h+var_F0]
0x1400e0184  mov     rcx, rbx
0x1400e0187  call    ?MapActualFilePathToLogicalFilePath@CFileSystemIterator@@AEAAJAEAV?$CSmartStrTemplate@G$0BI@@CoreSDK@@PEAPEAG@Z; CFileSystemIterator::MapActualFilePathToLogicalFilePath(CoreSDK::CSmartStrTemplate<ushort,24> &,ushort * *)
0x1400e018c  test    eax, eax
0x1400e018e  jns     short loc_1400E01A1
0x1400e0190  xor     r9d, r9d; lpArguments
0x1400e0193  xor     r8d, r8d; nNumberOfArguments
0x1400e0196  mov     edx, r14d; dwExceptionFlags
0x1400e0199  mov     ecx, eax; dwExceptionCode
0x1400e019b  call    cs:__imp_RaiseException
0x1400e01a1  lea     rcx, [rsp+130h+var_F0]
0x1400e01a6  call    ??1?$CSmartStrTemplateBase@G@CoreSDK@@IEAA@XZ; CoreSDK::CSmartStrTemplateBase<ushort>::~CSmartStrTemplateBase<ushort>(void)
0x1400e01ab  mov     [r13+0], rdi
0x1400e01af  jmp     short loc_1400E01B9
0x1400e01b1  mov     [r12], rdi
0x1400e01b5  mov     [r13+0], r15
0x1400e01b9  mov     rdi, r15
0x1400e01bc  test    rdi, rdi
0x1400e01bf  jz      short loc_1400E01D9
0x1400e01c1  lea     r8, aPstriteratorpa; "pstrIteratorPath == 0"
0x1400e01c8  mov     edx, 17Fh; unsigned int
0x1400e01cd  lea     rcx, aBaseStorBlbDsm; "base\\stor\\blb\\dsm\\dsmfs\\dll\\files"...
0x1400e01d4  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x1400e01d9  mov     eax, esi
0x1400e01db  mov     rcx, [rbp+4Fh+var_50]
0x1400e01df  xor     rcx, rsp; StackCookie
0x1400e01e2  call    __security_check_cookie
0x1400e01e7  add     rsp, 0F8h
0x1400e01ee  pop     r15
0x1400e01f0  pop     r14
0x1400e01f2  pop     r13
0x1400e01f4  pop     r12
0x1400e01f6  pop     rdi
0x1400e01f7  pop     rsi
0x1400e01f8  pop     rbx
0x1400e01f9  pop     rbp
0x1400e01fa  retn
```
