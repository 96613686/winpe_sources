# BlbMoveTargetDirectoryForCSVFS(ushort *,ushort *)

- ea: `0x140106400`
- end: `0x1401068cd`
- name: `?BlbMoveTargetDirectoryForCSVFS@@YAJPEAG0@Z`
- size: `1229`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, service_task`

## callers

- `0x1400204e8`

## callees

- `0x140006ca8`
- `0x140007ad3`
- `0x14000bb24`
- `0x14000bb4c`
- `0x140014260`
- `0x140014384`
- `0x14008863c`
- `0x1400f105c`
- `0x140106400`
- `0x140134d20`

## import_xrefs

- `KERNEL32!RemoveDirectoryW` at `0x140106747`
- `KERNEL32!RemoveDirectoryW` at `0x140106747`
- `KERNEL32!FindClose` at `0x140106865`
- `KERNEL32!FindClose` at `0x140106865`
- `KERNEL32!MoveFileW` at `0x1401066ff`
- `KERNEL32!MoveFileW` at `0x1401066ff`
- `KERNEL32!FindNextFileW` at `0x140106727`
- `KERNEL32!FindNextFileW` at `0x140106727`
- `KERNEL32!FindFirstFileW` at `0x14010655f`
- `KERNEL32!FindFirstFileW` at `0x14010655f`
- `KERNEL32!GetLastError` at `0x14010656e`
- `KERNEL32!GetLastError` at `0x140106735`
- `KERNEL32!GetLastError` at `0x140106755`
- `KERNEL32!GetLastError` at `0x1401067b6`
- `KERNEL32!GetLastError` at `0x14010656e`
- `KERNEL32!GetLastError` at `0x140106735`
- `KERNEL32!GetLastError` at `0x140106755`
- `KERNEL32!GetLastError` at `0x1401067b6`
- `ole32!CoTaskMemFree` at `0x14010661d`
- `ole32!CoTaskMemFree` at `0x140106634`
- `ole32!CoTaskMemFree` at `0x14010668a`
- `ole32!CoTaskMemFree` at `0x1401066a1`
- `ole32!CoTaskMemFree` at `0x14010661d`
- `ole32!CoTaskMemFree` at `0x140106634`
- `ole32!CoTaskMemFree` at `0x14010668a`
- `ole32!CoTaskMemFree` at `0x1401066a1`

## string_xrefs

- `0x14010646f`: `wszOldDirectory != NULL`
- `0x14010648c`: `wszNewDirectory != NULL`

## pseudocode

```c
__int64 __fastcall BlbMoveTargetDirectoryForCSVFS(unsigned __int16 *a1, unsigned __int16 *a2)
{
  WCHAR *v4; // rdi
  WCHAR *v5; // r14
  void *v6; // rsi
  int v7; // eax
  signed int appended; // ebx
  PVOID *v9; // rcx
  HANDLE FirstFileW; // r13
  signed int v11; // eax
  int v12; // edx
  int v13; // ecx
  void *v14; // rdi
  signed int LastError; // eax
  signed int v16; // eax
  signed int v17; // eax
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR lpFileName; // [rsp+38h] [rbp-C8h] BYREF
  LPCWSTR lpNewFileName; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR lpExistingFileName; // [rsp+48h] [rbp-B8h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+50h] [rbp-B0h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 142, &WPP_a4ce851ccccc3ce18ba06013107ef47e_Traceguids);
  }
  if ( !a1 )
    BlbAssert("base\\stor\\blb\\engine\\blbengutils\\blbbackuptargetutils.cpp", 0xFDFu, "wszOldDirectory != NULL");
  if ( !a2 )
    BlbAssert("base\\stor\\blb\\engine\\blbengutils\\blbbackuptargetutils.cpp", 0xFE0u, "wszNewDirectory != NULL");
  v4 = 0;
  lpFileName = 0;
  v5 = 0;
  lpExistingFileName = 0;
  v6 = 0;
  lpNewFileName = 0;
  pv = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v7 = BlbCheckCreateDirectory(a2, 1u, 0, 0);
  appended = v7;
  if ( v7 < 0 )
  {
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return (unsigned int)appended;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_67;
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      143,
      (unsigned int)&WPP_a4ce851ccccc3ce18ba06013107ef47e_Traceguids,
      (_DWORD)a2,
      v7);
    goto LABEL_66;
  }
  appended = BlbutilAppendString(a1, L"\\*", (unsigned __int16 **)&lpFileName);
  if ( appended < 0 )
  {
LABEL_66:
    v9 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_67;
  }
  FirstFileW = FindFirstFileW(lpFileName, &FindFileData);
  if ( FirstFileW != (HANDLE)-1LL )
  {
    while ( 1 )
    {
      v12 = FindFileData.cFileName[0] - 46;
      if ( FindFileData.cFileName[0] == 46 )
        v12 = FindFileData.cFileName[1];
      if ( v12 )
      {
        v13 = FindFileData.cFileName[0] - 46;
        if ( FindFileData.cFileName[0] == 46 )
        {
          v13 = FindFileData.cFileName[1] - 46;
          if ( FindFileData.cFileName[1] == 46 )
            v13 = FindFileData.cFileName[2];
        }
        if ( v13 )
        {
          if ( v4 )
          {
            CoTaskMemFree(v4);
            lpExistingFileName = 0;
          }
          if ( v6 )
          {
            CoTaskMemFree(v6);
            pv = 0;
          }
          appended = BlbutilAppendString(a1, L"\\", (unsigned __int16 **)&pv);
          if ( appended < 0 )
            goto LABEL_65;
          v14 = pv;
          appended = BlbutilAppendString(
                       (const unsigned __int16 *)pv,
                       FindFileData.cFileName,
                       (unsigned __int16 **)&lpExistingFileName);
          if ( appended < 0 )
            goto LABEL_65;
          if ( v5 )
          {
            CoTaskMemFree(v5);
            lpNewFileName = 0;
          }
          if ( v14 )
          {
            CoTaskMemFree(v14);
            pv = 0;
          }
          appended = BlbutilAppendString(a2, L"\\", (unsigned __int16 **)&pv);
          if ( appended < 0 )
            goto LABEL_65;
          v6 = pv;
          appended = BlbutilAppendString(
                       (const unsigned __int16 *)pv,
                       FindFileData.cFileName,
                       (unsigned __int16 **)&lpNewFileName);
          if ( appended < 0 )
            goto LABEL_65;
          v5 = (WCHAR *)lpNewFileName;
          v4 = (WCHAR *)lpExistingFileName;
          if ( !MoveFileW(lpExistingFileName, lpNewFileName) )
            break;
        }
      }
      memset_0(&FindFileData, 0, sizeof(FindFileData));
      if ( !FindNextFileW(FirstFileW, &FindFileData) )
      {
        LastError = GetLastError();
        if ( LastError == 18 )
        {
          if ( !RemoveDirectoryW(a1) )
          {
            v16 = GetLastError();
            appended = v16;
            if ( v16 > 0 )
              appended = (unsigned __int16)v16 | 0x80070000;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_Sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                147,
                (unsigned int)&WPP_a4ce851ccccc3ce18ba06013107ef47e_Traceguids,
                (_DWORD)a1,
                appended);
            }
          }
        }
        else
        {
          if ( LastError > 0 )
            appended = (unsigned __int16)LastError | 0x80070000;
          else
            appended = LastError;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 146, &WPP_a4ce851ccccc3ce18ba06013107ef47e_Traceguids);
          }
        }
        goto LABEL_65;
      }
    }
    v17 = GetLastError();
    appended = v17;
    if ( v17 > 0 )
      appended = (unsigned __int16)v17 | 0x80070000;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_SSD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        145,
        (unsigned int)&WPP_a4ce851ccccc3ce18ba06013107ef47e_Traceguids,
        (_DWORD)v4,
        (__int64)v5,
        appended);
    }
LABEL_65:
    FindClose(FirstFileW);
    goto LABEL_66;
  }
  v11 = GetLastError();
  appended = v11;
  if ( v11 > 0 )
    appended = (unsigned __int16)v11 | 0x80070000;
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
LABEL_67:
      if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 1) != 0 && *((_BYTE *)v9 + 25) >= 4u )
        WPP_SF_(v9[2], 148, &WPP_a4ce851ccccc3ce18ba06013107ef47e_Traceguids);
      return (unsigned int)appended;
    }
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      144,
      (unsigned int)&WPP_a4ce851ccccc3ce18ba06013107ef47e_Traceguids,
      (_DWORD)lpFileName,
      appended);
    goto LABEL_66;
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x140106400  mov     [rsp-8+arg_10], rbx
0x140106405  push    rbp
0x140106406  push    rsi
0x140106407  push    rdi
0x140106408  push    r12
0x14010640a  push    r13
0x14010640c  push    r14
0x14010640e  push    r15
0x140106410  lea     rbp, [rsp-1B0h]
0x140106418  sub     rsp, 2B0h
0x14010641f  mov     rax, cs:__security_cookie
0x140106426  xor     rax, rsp
0x140106429  mov     [rbp+1E0h+var_40], rax
0x140106430  mov     r12, rdx
0x140106433  mov     r15, rcx
0x140106436  mov     rcx, cs:WPP_GLOBAL_Control
0x14010643d  lea     rax, WPP_GLOBAL_Control
0x140106444  cmp     rcx, rax
0x140106447  jz      short loc_14010646A
0x140106449  test    byte ptr [rcx+1Ch], 1
0x14010644d  jz      short loc_14010646A
0x14010644f  cmp     byte ptr [rcx+19h], 4
0x140106453  jb      short loc_14010646A
0x140106455  mov     rcx, [rcx+10h]
0x140106459  lea     r8, WPP_a4ce851ccccc3ce18ba06013107ef47e_Traceguids
0x140106460  mov     edx, 8Eh
0x140106465  call    WPP_SF_
0x14010646a  test    r15, r15
0x14010646d  jnz     short loc_140106487
0x14010646f  lea     r8, aWszolddirector; "wszOldDirectory != NULL"
0x140106476  mov     edx, 0FDFh; unsigned int
0x14010647b  lea     rcx, aBaseStorBlbEng_16; "base\\stor\\blb\\engine\\blbengutils\\b"...
0x140106482  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x140106487  test    r12, r12
0x14010648a  jnz     short loc_1401064A4
0x14010648c  lea     r8, aWsznewdirector; "wszNewDirectory != NULL"
0x140106493  mov     edx, 0FE0h; unsigned int
0x140106498  lea     rcx, aBaseStorBlbEng_16; "base\\stor\\blb\\engine\\blbengutils\\b"...
0x14010649f  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x1401064a4  xor     edi, edi
0x1401064a6  mov     [rsp+2E0h+lpFileName], 0
0x1401064af  xor     r14d, r14d
0x1401064b2  mov     [rsp+2E0h+lpExistingFileName], rdi
0x1401064b7  xor     esi, esi
0x1401064b9  mov     [rsp+2E0h+lpNewFileName], r14
0x1401064be  xor     edx, edx; Val
0x1401064c0  mov     [rsp+2E0h+pv], rsi
0x1401064c5  mov     r8d, 250h; Size
0x1401064cb  lea     rcx, [rsp+2E0h+FindFileData]; void *
0x1401064d0  call    memset_0
0x1401064d5  xor     r9d, r9d; unsigned __int16 *
0x1401064d8  xor     r8d, r8d; unsigned __int8
0x1401064db  mov     dl, 1; unsigned __int8
0x1401064dd  mov     rcx, r12; unsigned __int16 *
0x1401064e0  call    ?BlbCheckCreateDirectory@@YAJPEAGEE0@Z; BlbCheckCreateDirectory(ushort *,uchar,uchar,ushort *)
0x1401064e5  mov     ebx, eax
0x1401064e7  test    eax, eax
0x1401064e9  jns     short loc_140106537
0x1401064eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1401064f2  lea     rsi, WPP_GLOBAL_Control
0x1401064f9  cmp     rcx, rsi
0x1401064fc  jz      loc_1401068A1
0x140106502  test    byte ptr [rcx+1Ch], 1
0x140106506  jz      loc_14010687B
0x14010650c  cmp     byte ptr [rcx+19h], 2
0x140106510  jb      loc_14010687B
0x140106516  mov     edx, 8Fh
0x14010651b  mov     dword ptr [rsp+2E0h+var_2C0], eax
0x14010651f  mov     r9, r12
0x140106522  mov     rcx, [rcx+10h]
0x140106526  lea     r8, WPP_a4ce851ccccc3ce18ba06013107ef47e_Traceguids
0x14010652d  call    WPP_SF_Sd
0x140106532  jmp     loc_140106874
0x140106537  lea     r8, [rsp+2E0h+lpFileName]; unsigned __int16 **
0x14010653c  mov     rcx, r15; unsigned __int16 *
0x14010653f  lea     rdx, asc_140142BFC; "\\*"
0x140106546  call    ?BlbutilAppendString@@YAJPEBG0PEAPEAG@Z; BlbutilAppendString(ushort const *,ushort const *,ushort * *)
0x14010654b  mov     ebx, eax
0x14010654d  test    eax, eax
0x14010654f  js      loc_14010686D
0x140106555  mov     rcx, [rsp+2E0h+lpFileName]; lpFileName
0x14010655a  lea     rdx, [rsp+2E0h+FindFileData]; lpFindFileData
0x14010655f  call    cs:__imp_FindFirstFileW
0x140106565  mov     r13, rax
0x140106568  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14010656c  jnz     short loc_1401065C1
0x14010656e  call    cs:__imp_GetLastError
0x140106574  mov     ebx, eax
0x140106576  test    eax, eax
0x140106578  jle     short loc_140106583
0x14010657a  movzx   ebx, ax
0x14010657d  or      ebx, 80070000h
0x140106583  mov     rcx, cs:WPP_GLOBAL_Control
0x14010658a  lea     rsi, WPP_GLOBAL_Control
0x140106591  cmp     rcx, rsi
0x140106594  jz      loc_1401068A1
0x14010659a  test    byte ptr [rcx+1Ch], 1
0x14010659e  jz      loc_14010687B
0x1401065a4  cmp     byte ptr [rcx+19h], 2
0x1401065a8  jb      loc_14010687B
0x1401065ae  mov     r9, [rsp+2E0h+lpFileName]
0x1401065b3  mov     edx, 90h
0x1401065b8  mov     dword ptr [rsp+2E0h+var_2C0], ebx
0x1401065bc  jmp     loc_140106522
0x1401065c1  movzx   edx, [rsp+2E0h+FindFileData.cFileName]
0x1401065c6  mov     r8d, 2Eh ; '.'
0x1401065cc  movzx   eax, r8w
0x1401065d0  sub     edx, eax
0x1401065d2  jnz     short loc_1401065E0
0x1401065d4  movzx   edx, [rsp+2E0h+FindFileData.cFileName+2]
0x1401065d9  xor     eax, eax
0x1401065db  movzx   ecx, ax
0x1401065de  sub     edx, ecx
0x1401065e0  test    edx, edx
0x1401065e2  jz      loc_14010670D
0x1401065e8  movzx   ecx, [rsp+2E0h+FindFileData.cFileName]
0x1401065ed  movzx   eax, r8w
0x1401065f1  sub     ecx, eax
0x1401065f3  jnz     short loc_14010660D
0x1401065f5  movzx   ecx, [rsp+2E0h+FindFileData.cFileName+2]
0x1401065fa  movzx   eax, r8w
0x1401065fe  sub     ecx, eax
0x140106600  jnz     short loc_14010660D
0x140106602  movzx   ecx, [rbp+1E0h+FindFileData.cFileName+4]
0x140106606  xor     eax, eax
0x140106608  movzx   edx, ax
0x14010660b  sub     ecx, edx
0x14010660d  test    ecx, ecx
0x14010660f  jz      loc_14010670D
0x140106615  test    rdi, rdi
0x140106618  jz      short loc_14010662C
0x14010661a  mov     rcx, rdi; pv
0x14010661d  call    cs:__imp_CoTaskMemFree
0x140106623  mov     [rsp+2E0h+lpExistingFileName], 0
0x14010662c  test    rsi, rsi
0x14010662f  jz      short loc_140106643
0x140106631  mov     rcx, rsi; pv
0x140106634  call    cs:__imp_CoTaskMemFree
0x14010663a  mov     [rsp+2E0h+pv], 0
0x140106643  lea     r8, [rsp+2E0h+pv]; unsigned __int16 **
0x140106648  mov     rcx, r15; unsigned __int16 *
0x14010664b  lea     rdx, asc_14013C090; "\\"
0x140106652  call    ?BlbutilAppendString@@YAJPEBG0PEAPEAG@Z; BlbutilAppendString(ushort const *,ushort const *,ushort * *)
0x140106657  mov     ebx, eax
0x140106659  test    eax, eax
0x14010665b  js      loc_14010685B
0x140106661  mov     rdi, [rsp+2E0h+pv]
0x140106666  lea     r8, [rsp+2E0h+lpExistingFileName]; unsigned __int16 **
0x14010666b  mov     rcx, rdi; unsigned __int16 *
0x14010666e  lea     rdx, [rsp+2E0h+FindFileData.cFileName]; unsigned __int16 *
0x140106673  call    ?BlbutilAppendString@@YAJPEBG0PEAPEAG@Z; BlbutilAppendString(ushort const *,ushort const *,ushort * *)
0x140106678  mov     ebx, eax
0x14010667a  test    eax, eax
0x14010667c  js      loc_14010685B
0x140106682  test    r14, r14
0x140106685  jz      short loc_140106699
0x140106687  mov     rcx, r14; pv
0x14010668a  call    cs:__imp_CoTaskMemFree
0x140106690  mov     [rsp+2E0h+lpNewFileName], 0
0x140106699  test    rdi, rdi
0x14010669c  jz      short loc_1401066B0
0x14010669e  mov     rcx, rdi; pv
0x1401066a1  call    cs:__imp_CoTaskMemFree
0x1401066a7  mov     [rsp+2E0h+pv], 0
0x1401066b0  lea     r8, [rsp+2E0h+pv]; unsigned __int16 **
0x1401066b5  mov     rcx, r12; unsigned __int16 *
0x1401066b8  lea     rdx, asc_14013C090; "\\"
0x1401066bf  call    ?BlbutilAppendString@@YAJPEBG0PEAPEAG@Z; BlbutilAppendString(ushort const *,ushort const *,ushort * *)
0x1401066c4  mov     ebx, eax
0x1401066c6  test    eax, eax
0x1401066c8  js      loc_14010685B
0x1401066ce  mov     rsi, [rsp+2E0h+pv]
0x1401066d3  lea     r8, [rsp+2E0h+lpNewFileName]; unsigned __int16 **
0x1401066d8  mov     rcx, rsi; unsigned __int16 *
0x1401066db  lea     rdx, [rsp+2E0h+FindFileData.cFileName]; unsigned __int16 *
0x1401066e0  call    ?BlbutilAppendString@@YAJPEBG0PEAPEAG@Z; BlbutilAppendString(ushort const *,ushort const *,ushort * *)
0x1401066e5  mov     ebx, eax
0x1401066e7  test    eax, eax
0x1401066e9  js      loc_14010685B
0x1401066ef  mov     r14, [rsp+2E0h+lpNewFileName]
0x1401066f4  mov     rdi, [rsp+2E0h+lpExistingFileName]
0x1401066f9  mov     rdx, r14; lpNewFileName
0x1401066fc  mov     rcx, rdi; lpExistingFileName
0x1401066ff  call    cs:__imp_MoveFileW
0x140106705  test    eax, eax
0x140106707  jz      loc_1401067B6
0x14010670d  xor     edx, edx; Val
0x14010670f  lea     rcx, [rsp+2E0h+FindFileData]; void *
0x140106714  mov     r8d, 250h; Size
0x14010671a  call    memset_0
0x14010671f  lea     rdx, [rsp+2E0h+FindFileData]; lpFindFileData
0x140106724  mov     rcx, r13; hFindFile
0x140106727  call    cs:__imp_FindNextFileW
0x14010672d  test    eax, eax
0x14010672f  jnz     loc_1401065C1
0x140106735  call    cs:__imp_GetLastError
0x14010673b  cmp     eax, 12h
0x14010673e  jnz     loc_140106811
0x140106744  mov     rcx, r15; lpPathName
0x140106747  call    cs:__imp_RemoveDirectoryW
0x14010674d  test    eax, eax
0x14010674f  jnz     loc_14010685B
0x140106755  call    cs:__imp_GetLastError
0x14010675b  mov     ebx, eax
0x14010675d  test    eax, eax
0x14010675f  jle     short loc_14010676A
0x140106761  movzx   ebx, ax
0x140106764  or      ebx, 80070000h
0x14010676a  mov     rcx, cs:WPP_GLOBAL_Control
0x140106771  lea     rsi, WPP_GLOBAL_Control
0x140106778  cmp     rcx, rsi
0x14010677b  jz      loc_140106862
0x140106781  test    byte ptr [rcx+1Ch], 1
0x140106785  jz      loc_140106862
0x14010678b  cmp     byte ptr [rcx+19h], 2
0x14010678f  jb      loc_140106862
0x140106795  mov     rcx, [rcx+10h]
0x140106799  lea     r8, WPP_a4ce851ccccc3ce18ba06013107ef47e_Traceguids
0x1401067a0  mov     edx, 93h
0x1401067a5  mov     dword ptr [rsp+2E0h+var_2C0], ebx
0x1401067a9  mov     r9, r15
0x1401067ac  call    WPP_SF_Sd
0x1401067b1  jmp     loc_140106862
0x1401067b6  call    cs:__imp_GetLastError
0x1401067bc  mov     ebx, eax
0x1401067be  test    eax, eax
0x1401067c0  jle     short loc_1401067CB
0x1401067c2  movzx   ebx, ax
0x1401067c5  or      ebx, 80070000h
0x1401067cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1401067d2  lea     rsi, WPP_GLOBAL_Control
0x1401067d9  cmp     rcx, rsi
0x1401067dc  jz      loc_140106862
0x1401067e2  test    byte ptr [rcx+1Ch], 1
0x1401067e6  jz      short loc_140106862
0x1401067e8  cmp     byte ptr [rcx+19h], 2
0x1401067ec  jb      short loc_140106862
0x1401067ee  mov     rcx, [rcx+10h]
0x1401067f2  lea     r8, WPP_a4ce851ccccc3ce18ba06013107ef47e_Traceguids
0x1401067f9  mov     edx, 91h
0x1401067fe  mov     [rsp+2E0h+var_2B8], ebx
0x140106802  mov     r9, rdi
0x140106805  mov     [rsp+2E0h+var_2C0], r14
0x14010680a  call    WPP_SF_SSD
0x14010680f  jmp     short loc_140106862
0x140106811  test    eax, eax
0x140106813  jg      short loc_140106819
0x140106815  mov     ebx, eax
0x140106817  jmp     short loc_140106822
0x140106819  movzx   ebx, ax
0x14010681c  or      ebx, 80070000h
0x140106822  mov     rcx, cs:WPP_GLOBAL_Control
0x140106829  lea     rsi, WPP_GLOBAL_Control
0x140106830  cmp     rcx, rsi
0x140106833  jz      short loc_140106862
0x140106835  test    byte ptr [rcx+1Ch], 1
0x140106839  jz      short loc_140106862
0x14010683b  cmp     byte ptr [rcx+19h], 2
0x14010683f  jb      short loc_140106862
0x140106841  mov     rcx, [rcx+10h]
0x140106845  lea     r8, WPP_a4ce851ccccc3ce18ba06013107ef47e_Traceguids
0x14010684c  mov     edx, 92h
0x140106851  mov     r9d, ebx
0x140106854  call    WPP_SF_d
0x140106859  jmp     short loc_140106862
0x14010685b  lea     rsi, WPP_GLOBAL_Control
0x140106862  mov     rcx, r13; hFindFile
0x140106865  call    cs:__imp_FindClose
0x14010686b  jmp     short loc_140106874
0x14010686d  lea     rsi, WPP_GLOBAL_Control
0x140106874  mov     rcx, cs:WPP_GLOBAL_Control
0x14010687b  cmp     rcx, rsi
0x14010687e  jz      short loc_1401068A1
0x140106880  test    byte ptr [rcx+1Ch], 1
0x140106884  jz      short loc_1401068A1
0x140106886  cmp     byte ptr [rcx+19h], 4
0x14010688a  jb      short loc_1401068A1
0x14010688c  mov     rcx, [rcx+10h]
0x140106890  lea     r8, WPP_a4ce851ccccc3ce18ba06013107ef47e_Traceguids
0x140106897  mov     edx, 94h
0x14010689c  call    WPP_SF_
0x1401068a1  mov     eax, ebx
0x1401068a3  mov     rcx, [rbp+1E0h+var_40]
0x1401068aa  xor     rcx, rsp; StackCookie
0x1401068ad  call    __security_check_cookie
0x1401068b2  mov     rbx, [rsp+2E0h+arg_10]
0x1401068ba  add     rsp, 2B0h
0x1401068c1  pop     r15
0x1401068c3  pop     r14
0x1401068c5  pop     r13
0x1401068c7  pop     r12
0x1401068c9  pop     rdi
0x1401068ca  pop     rsi
0x1401068cb  pop     rbp
0x1401068cc  retn
```
