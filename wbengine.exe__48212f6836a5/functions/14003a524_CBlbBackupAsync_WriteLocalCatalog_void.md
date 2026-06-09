# CBlbBackupAsync::WriteLocalCatalog(void)

- ea: `0x14003a524`
- end: `0x14003a8e7`
- name: `?WriteLocalCatalog@CBlbBackupAsync@@AEAAJXZ`
- size: `963`
- prototype: `__int64 __fastcall(CBlbBackupAsync *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, service_task`

## callers

- `0x140038a14`

## callees

- `0x140006ca8`
- `0x140006d94`
- `0x140008ac8`
- `0x14000bb4c`
- `0x14000fe94`
- `0x140014260`
- `0x140014384`
- `0x140028f5c`
- `0x14003a524`
- `0x1400889f0`
- `0x1400f25c0`
- `0x1401022dc`
- `0x140137010`

## import_xrefs

- `KERNEL32!MoveFileExW` at `0x14003a763`
- `KERNEL32!MoveFileExW` at `0x14003a763`
- `KERNEL32!DeleteFileW` at `0x14003a5cb`
- `KERNEL32!DeleteFileW` at `0x14003a6a4`
- `KERNEL32!DeleteFileW` at `0x14003a5cb`
- `KERNEL32!DeleteFileW` at `0x14003a6a4`
- `KERNEL32!GetLastError` at `0x14003a5d5`
- `KERNEL32!GetLastError` at `0x14003a6ae`
- `KERNEL32!GetLastError` at `0x14003a76d`
- `KERNEL32!GetLastError` at `0x14003a5d5`
- `KERNEL32!GetLastError` at `0x14003a6ae`
- `KERNEL32!GetLastError` at `0x14003a76d`
- `ole32!CoTaskMemFree` at `0x14003a868`
- `ole32!CoTaskMemFree` at `0x14003a87e`
- `ole32!CoTaskMemFree` at `0x14003a88c`
- `ole32!CoTaskMemFree` at `0x14003a89a`
- `ole32!CoTaskMemFree` at `0x14003a868`
- `ole32!CoTaskMemFree` at `0x14003a87e`
- `ole32!CoTaskMemFree` at `0x14003a88c`
- `ole32!CoTaskMemFree` at `0x14003a89a`

## string_xrefs

- `0x14003a566`: `base\stor\blb\engine\service\backup.cpp`
- `0x14003a71f`: `base\stor\blb\engine\service\backup.cpp`
- `0x14003a55a`: `m_wszBackupSetDirectory`

## pseudocode

```c
__int64 __fastcall CBlbBackupAsync::WriteLocalCatalog(CBlbBackupAsync *this)
{
  void *v1; // r12
  WCHAR *v2; // r15
  int appended; // eax
  signed int v5; // ebx
  int File; // eax
  DWORD LastError; // eax
  unsigned __int16 *v8; // r13
  WCHAR *v9; // r14
  DWORD v10; // eax
  WCHAR *v11; // rsi
  _QWORD *v12; // rdi
  unsigned __int64 v13; // r13
  LPCWSTR lpExistingFileName; // [rsp+80h] [rbp+48h] BYREF
  LPCWSTR lpNewFileName; // [rsp+88h] [rbp+50h] BYREF
  LPCWSTR lpFileName; // [rsp+90h] [rbp+58h] BYREF
  LPVOID pv; // [rsp+98h] [rbp+60h] BYREF

  v1 = 0;
  v2 = 0;
  pv = 0;
  lpFileName = 0;
  lpNewFileName = 0;
  lpExistingFileName = 0;
  if ( !*((_QWORD *)this + 59) )
    BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0x22F8u, "m_wszBackupSetDirectory");
  if ( (*((_BYTE *)this + 340) & 4) == 0 )
    goto LABEL_14;
  appended = BlbAppendLocalCatalogFile(*((unsigned __int16 **)this + 59), 0, 0, (unsigned __int16 **)&pv);
  v1 = pv;
  v5 = appended;
  if ( appended < 0 )
    goto LABEL_54;
  File = BlbFindFile((unsigned __int16 *)pv, (unsigned __int16 **)&lpFileName);
  v2 = (WCHAR *)lpFileName;
  v5 = File;
  if ( File >= 0 )
  {
    if ( lpFileName && !DeleteFileW(lpFileName) )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          395,
          (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
          (_DWORD)v2,
          LastError);
      }
      if ( v5 > 0 )
        v5 = (unsigned __int16)v5 | 0x80070000;
      goto LABEL_52;
    }
LABEL_14:
    v5 = BlbAppendLocalCatalogFile(
           *((unsigned __int16 **)this + 59),
           (UUID *)((char *)this + 296),
           0,
           (unsigned __int16 **)&lpNewFileName);
    if ( v5 < 0 )
    {
LABEL_50:
      if ( lpNewFileName )
        CoTaskMemFree((LPVOID)lpNewFileName);
      goto LABEL_52;
    }
    if ( (*((_BYTE *)this + 340) & 1) != 0 )
    {
      v8 = (unsigned __int16 *)lpNewFileName;
      v5 = BlbutilDuplicateString(lpNewFileName, (unsigned __int16 **)&lpExistingFileName, 0);
      if ( v5 >= 0 )
      {
        v9 = (WCHAR *)lpExistingFileName;
        goto LABEL_28;
      }
    }
    else
    {
      v5 = BlbAppendLocalCatalogFile(
             *((unsigned __int16 **)this + 59),
             (UUID *)((char *)this + 296),
             1u,
             (unsigned __int16 **)&lpExistingFileName);
      if ( v5 >= 0 )
      {
        v9 = (WCHAR *)lpExistingFileName;
        if ( !DeleteFileW(lpExistingFileName) )
        {
          v10 = GetLastError();
          v5 = v10;
          if ( v10 != 2 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_Sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                396,
                (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
                (_DWORD)v9,
                v10);
            }
LABEL_25:
            if ( v5 > 0 )
              v5 = (unsigned __int16)v5 | 0x80070000;
            goto LABEL_48;
          }
        }
        v8 = (unsigned __int16 *)lpNewFileName;
LABEL_28:
        if ( !*((_QWORD *)this + 50) )
          BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0x2343u, "m_pLocalCatalog");
        v5 = (*(__int64 (__fastcall **)(_QWORD, WCHAR *))(**((_QWORD **)this + 50) + 136LL))(*((_QWORD *)this + 50), v9);
        if ( v5 < 0 )
          goto LABEL_48;
        if ( (*((_BYTE *)this + 340) & 1) != 0 || MoveFileExW(v9, v8, 1u) )
        {
          if ( *((char *)this + 340) < 0 && *((_BYTE *)this + 276) )
          {
            lpExistingFileName = (LPCWSTR)operator new(0x20u);
            v11 = (WCHAR *)lpExistingFileName;
            if ( lpExistingFileName )
            {
              *((_BYTE *)lpExistingFileName + 8) = 0;
              *(_QWORD *)v11 = &CblbCatalogVerifier::`vftable';
              *((_QWORD *)v11 + 3) = 0;
              *((_QWORD *)v11 + 2) = 0;
            }
            else
            {
              v11 = 0;
            }
            v5 = CblbCatalogVerifier::Init((CblbCatalogVerifier *)v11, v8);
            if ( v5 >= 0 )
            {
              v12 = (_QWORD *)((char *)this + 776);
              v13 = v12[1];
              if ( v13 >= v12[2]
                && !(unsigned __int8)ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::GrowBuffer(
                                       v12,
                                       v13 + 1) )
              {
                ATL::AtlThrowImpl(-2147024882);
              }
              *(_QWORD *)(*v12 + 8 * v13) = v11;
              ++v12[1];
            }
          }
          goto LABEL_48;
        }
        v5 = GetLastError();
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_SSD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            397,
            (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
            (_DWORD)v9,
            (__int64)v8,
            v5);
        }
        goto LABEL_25;
      }
    }
    v9 = (WCHAR *)lpExistingFileName;
LABEL_48:
    if ( v9 )
      CoTaskMemFree(v9);
    goto LABEL_50;
  }
LABEL_52:
  if ( v2 )
    CoTaskMemFree(v2);
LABEL_54:
  if ( v1 )
    CoTaskMemFree(v1);
  if ( v5 < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 398, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14003a524  push    rbp
0x14003a526  push    rbx
0x14003a527  push    rsi
0x14003a528  push    rdi
0x14003a529  push    r12
0x14003a52b  push    r13
0x14003a52d  push    r14
0x14003a52f  push    r15
0x14003a531  mov     rbp, rsp
0x14003a534  sub     rsp, 38h
0x14003a538  xor     r12d, r12d
0x14003a53b  xor     r15d, r15d
0x14003a53e  mov     rdi, rcx
0x14003a541  mov     [rbp+pv], r12
0x14003a545  mov     [rbp+lpFileName], r15
0x14003a549  mov     [rbp+lpNewFileName], r12
0x14003a54d  mov     [rbp+lpExistingFileName], r12
0x14003a551  cmp     [rcx+1D8h], r12
0x14003a558  jnz     short loc_14003A572
0x14003a55a  lea     r8, aMWszbackupsetd; "m_wszBackupSetDirectory"
0x14003a561  mov     edx, 22F8h; unsigned int
0x14003a566  lea     rcx, aBaseStorBlbEng_20; "base\\stor\\blb\\engine\\service\\backu"...
0x14003a56d  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14003a572  test    byte ptr [rdi+154h], 4
0x14003a579  lea     r13, WPP_GLOBAL_Control
0x14003a580  jz      loc_14003A627
0x14003a586  mov     rcx, [rdi+1D8h]; unsigned __int16 *
0x14003a58d  lea     r9, [rbp+pv]; unsigned __int16 **
0x14003a591  xor     r8d, r8d; unsigned __int8
0x14003a594  xor     edx, edx; Uuid
0x14003a596  call    ?BlbAppendLocalCatalogFile@@YAJPEAGPEAU_GUID@@EPEAPEAG@Z; BlbAppendLocalCatalogFile(ushort *,_GUID *,uchar,ushort * *)
0x14003a59b  mov     r12, [rbp+pv]
0x14003a59f  mov     ebx, eax
0x14003a5a1  test    eax, eax
0x14003a5a3  js      loc_14003A892
0x14003a5a9  lea     rdx, [rbp+lpFileName]; unsigned __int16 **
0x14003a5ad  mov     rcx, r12; unsigned __int16 *
0x14003a5b0  call    ?BlbFindFile@@YAJPEAGPEAPEAG@Z; BlbFindFile(ushort *,ushort * *)
0x14003a5b5  mov     r15, [rbp+lpFileName]
0x14003a5b9  mov     ebx, eax
0x14003a5bb  test    eax, eax
0x14003a5bd  js      loc_14003A884
0x14003a5c3  test    r15, r15
0x14003a5c6  jz      short loc_14003A627
0x14003a5c8  mov     rcx, r15; lpFileName
0x14003a5cb  call    cs:__imp_DeleteFileW
0x14003a5d1  test    eax, eax
0x14003a5d3  jnz     short loc_14003A627
0x14003a5d5  call    cs:__imp_GetLastError
0x14003a5db  mov     ebx, eax
0x14003a5dd  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a5e4  cmp     rcx, r13
0x14003a5e7  jz      short loc_14003A611
0x14003a5e9  test    byte ptr [rcx+1Ch], 1
0x14003a5ed  jz      short loc_14003A611
0x14003a5ef  cmp     byte ptr [rcx+19h], 2
0x14003a5f3  jb      short loc_14003A611
0x14003a5f5  mov     rcx, [rcx+10h]
0x14003a5f9  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14003a600  mov     edx, 18Bh
0x14003a605  mov     dword ptr [rsp+38h+var_18], eax
0x14003a609  mov     r9, r15
0x14003a60c  call    WPP_SF_Sd
0x14003a611  test    ebx, ebx
0x14003a613  jle     loc_14003A884
0x14003a619  movzx   ebx, bx
0x14003a61c  or      ebx, 80070000h
0x14003a622  jmp     loc_14003A884
0x14003a627  mov     rcx, [rdi+1D8h]; unsigned __int16 *
0x14003a62e  lea     rsi, [rdi+128h]
0x14003a635  mov     rdx, rsi; Uuid
0x14003a638  lea     r9, [rbp+lpNewFileName]; unsigned __int16 **
0x14003a63c  xor     r8d, r8d; unsigned __int8
0x14003a63f  call    ?BlbAppendLocalCatalogFile@@YAJPEAGPEAU_GUID@@EPEAPEAG@Z; BlbAppendLocalCatalogFile(ushort *,_GUID *,uchar,ushort * *)
0x14003a644  mov     ebx, eax
0x14003a646  test    eax, eax
0x14003a648  js      loc_14003A875
0x14003a64e  test    byte ptr [rdi+154h], 1
0x14003a655  jz      short loc_14003A67D
0x14003a657  mov     r13, [rbp+lpNewFileName]
0x14003a65b  lea     rdx, [rbp+lpExistingFileName]; unsigned __int16 **
0x14003a65f  mov     rcx, r13; unsigned __int16 *
0x14003a662  xor     r8d, r8d; unsigned __int64
0x14003a665  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x14003a66a  mov     ebx, eax
0x14003a66c  test    eax, eax
0x14003a66e  js      loc_14003A85C
0x14003a674  mov     r14, [rbp+lpExistingFileName]
0x14003a678  jmp     loc_14003A709
0x14003a67d  mov     rcx, [rdi+1D8h]; unsigned __int16 *
0x14003a684  lea     r9, [rbp+lpExistingFileName]; unsigned __int16 **
0x14003a688  mov     r8b, 1; unsigned __int8
0x14003a68b  mov     rdx, rsi; Uuid
0x14003a68e  call    ?BlbAppendLocalCatalogFile@@YAJPEAGPEAU_GUID@@EPEAPEAG@Z; BlbAppendLocalCatalogFile(ushort *,_GUID *,uchar,ushort * *)
0x14003a693  mov     ebx, eax
0x14003a695  test    eax, eax
0x14003a697  js      loc_14003A85C
0x14003a69d  mov     r14, [rbp+lpExistingFileName]
0x14003a6a1  mov     rcx, r14; lpFileName
0x14003a6a4  call    cs:__imp_DeleteFileW
0x14003a6aa  test    eax, eax
0x14003a6ac  jnz     short loc_14003A705
0x14003a6ae  call    cs:__imp_GetLastError
0x14003a6b4  mov     ebx, eax
0x14003a6b6  cmp     eax, 2
0x14003a6b9  jz      short loc_14003A705
0x14003a6bb  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a6c2  cmp     rcx, r13
0x14003a6c5  jz      short loc_14003A6EF
0x14003a6c7  test    byte ptr [rcx+1Ch], 1
0x14003a6cb  jz      short loc_14003A6EF
0x14003a6cd  cmp     byte ptr [rcx+19h], 2
0x14003a6d1  jb      short loc_14003A6EF
0x14003a6d3  mov     rcx, [rcx+10h]
0x14003a6d7  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14003a6de  mov     edx, 18Ch
0x14003a6e3  mov     dword ptr [rsp+38h+var_18], eax
0x14003a6e7  mov     r9, r14
0x14003a6ea  call    WPP_SF_Sd
0x14003a6ef  test    ebx, ebx
0x14003a6f1  jle     loc_14003A860
0x14003a6f7  movzx   ebx, bx
0x14003a6fa  or      ebx, 80070000h
0x14003a700  jmp     loc_14003A860
0x14003a705  mov     r13, [rbp+lpNewFileName]
0x14003a709  cmp     qword ptr [rdi+190h], 0
0x14003a711  jnz     short loc_14003A72B
0x14003a713  lea     r8, aMPlocalcatalog; "m_pLocalCatalog"
0x14003a71a  mov     edx, 2343h; unsigned int
0x14003a71f  lea     rcx, aBaseStorBlbEng_20; "base\\stor\\blb\\engine\\service\\backu"...
0x14003a726  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14003a72b  mov     rcx, [rdi+190h]
0x14003a732  mov     rdx, r14
0x14003a735  mov     rax, [rcx]
0x14003a738  mov     rax, [rax+88h]
0x14003a73f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003a744  mov     ebx, eax
0x14003a746  test    eax, eax
0x14003a748  js      loc_14003A860
0x14003a74e  test    byte ptr [rdi+154h], 1
0x14003a755  jnz     short loc_14003A7C6
0x14003a757  mov     r8d, 1; dwFlags
0x14003a75d  mov     rdx, r13; lpNewFileName
0x14003a760  mov     rcx, r14; lpExistingFileName
0x14003a763  call    cs:__imp_MoveFileExW
0x14003a769  test    eax, eax
0x14003a76b  jnz     short loc_14003A7C6
0x14003a76d  call    cs:__imp_GetLastError
0x14003a773  mov     ebx, eax
0x14003a775  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a77c  lea     rax, WPP_GLOBAL_Control
0x14003a783  cmp     rcx, rax
0x14003a786  jz      loc_14003A6EF
0x14003a78c  test    byte ptr [rcx+1Ch], 1
0x14003a790  jz      loc_14003A6EF
0x14003a796  cmp     byte ptr [rcx+19h], 2
0x14003a79a  jb      loc_14003A6EF
0x14003a7a0  mov     rcx, [rcx+10h]
0x14003a7a4  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14003a7ab  mov     edx, 18Dh
0x14003a7b0  mov     [rsp+38h+var_10], ebx
0x14003a7b4  mov     r9, r14
0x14003a7b7  mov     [rsp+38h+var_18], r13
0x14003a7bc  call    WPP_SF_SSD
0x14003a7c1  jmp     loc_14003A6EF
0x14003a7c6  test    byte ptr [rdi+154h], 80h
0x14003a7cd  jz      loc_14003A860
0x14003a7d3  cmp     byte ptr [rdi+114h], 0
0x14003a7da  jz      loc_14003A860
0x14003a7e0  mov     ecx, 20h ; ' '; Size
0x14003a7e5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14003a7ea  xor     ecx, ecx
0x14003a7ec  mov     [rbp+lpExistingFileName], rax
0x14003a7f0  mov     rsi, rax
0x14003a7f3  test    rax, rax
0x14003a7f6  jz      short loc_14003A80F
0x14003a7f8  lea     rax, ??_7CblbCatalogVerifier@@6B@; const CblbCatalogVerifier::`vftable'
0x14003a7ff  mov     [rsi+8], cl
0x14003a802  mov     [rsi], rax
0x14003a805  mov     [rsi+18h], rcx
0x14003a809  mov     [rsi+10h], rcx
0x14003a80d  jmp     short loc_14003A812
0x14003a80f  mov     rsi, rcx
0x14003a812  mov     rdx, r13; unsigned __int16 *
0x14003a815  mov     rcx, rsi; this
0x14003a818  call    ?Init@CblbCatalogVerifier@@QEAAJPEAG@Z; CblbCatalogVerifier::Init(ushort *)
0x14003a81d  mov     ebx, eax
0x14003a81f  test    eax, eax
0x14003a821  js      short loc_14003A860
0x14003a823  add     rdi, 308h
0x14003a82a  mov     r13, [rdi+8]
0x14003a82e  cmp     r13, [rdi+10h]
0x14003a832  jb      short loc_14003A84F
0x14003a834  lea     rdx, [r13+1]
0x14003a838  mov     rcx, rdi
0x14003a83b  call    ?GrowBuffer@?$CAtlArray@V?$CAutoPtr@VCAccessAce@CDacl@ATL@@@ATL@@V?$CAutoPtrElementTraits@VCAccessAce@CDacl@ATL@@@2@@ATL@@AEAA_N_K@Z; ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::GrowBuffer(unsigned __int64)
0x14003a840  test    al, al
0x14003a842  jnz     short loc_14003A84F
0x14003a844  mov     ecx, 8007000Eh; int
0x14003a849  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14003a84f  mov     rax, [rdi]
0x14003a852  mov     [rax+r13*8], rsi
0x14003a856  inc     qword ptr [rdi+8]
0x14003a85a  jmp     short loc_14003A860
0x14003a85c  mov     r14, [rbp+lpExistingFileName]
0x14003a860  test    r14, r14
0x14003a863  jz      short loc_14003A86E
0x14003a865  mov     rcx, r14; pv
0x14003a868  call    cs:__imp_CoTaskMemFree
0x14003a86e  lea     r13, WPP_GLOBAL_Control
0x14003a875  mov     rcx, [rbp+lpNewFileName]; pv
0x14003a879  test    rcx, rcx
0x14003a87c  jz      short loc_14003A884
0x14003a87e  call    cs:__imp_CoTaskMemFree
0x14003a884  test    r15, r15
0x14003a887  jz      short loc_14003A892
0x14003a889  mov     rcx, r15; pv
0x14003a88c  call    cs:__imp_CoTaskMemFree
0x14003a892  test    r12, r12
0x14003a895  jz      short loc_14003A8A0
0x14003a897  mov     rcx, r12; pv
0x14003a89a  call    cs:__imp_CoTaskMemFree
0x14003a8a0  test    ebx, ebx
0x14003a8a2  jns     short loc_14003A8D4
0x14003a8a4  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a8ab  cmp     rcx, r13
0x14003a8ae  jz      short loc_14003A8D4
0x14003a8b0  test    byte ptr [rcx+1Ch], 1
0x14003a8b4  jz      short loc_14003A8D4
0x14003a8b6  cmp     byte ptr [rcx+19h], 2
0x14003a8ba  jb      short loc_14003A8D4
0x14003a8bc  mov     rcx, [rcx+10h]
0x14003a8c0  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14003a8c7  mov     edx, 18Eh
0x14003a8cc  mov     r9d, ebx
0x14003a8cf  call    WPP_SF_d
0x14003a8d4  mov     eax, ebx
0x14003a8d6  add     rsp, 38h
0x14003a8da  pop     r15
0x14003a8dc  pop     r14
0x14003a8de  pop     r13
0x14003a8e0  pop     r12
0x14003a8e2  pop     rdi
0x14003a8e3  pop     rsi
0x14003a8e4  pop     rbx
0x14003a8e5  pop     rbp
0x14003a8e6  retn
```
