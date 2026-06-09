# SdpVerifyDirectoryIntegrity(ushort const *,ushort const *,_LIST_ENTRY *)

- ea: `0x18000787c`
- end: `0x180007bb7`
- name: `?SdpVerifyDirectoryIntegrity@@YAJPEBG0PEAU_LIST_ENTRY@@@Z`
- size: `827`
- prototype: `__int64 __fastcall(const unsigned __int16 *, WCHAR *, struct _LIST_ENTRY *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180007bc0`

## callees

- `0x1800012a4`
- `0x1800020f8`
- `0x180007000`
- `0x18000729c`
- `0x1800076a4`
- `0x18000787c`
- `0x180026fa0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180007a11`
- `msvcrt!_wcsicmp` at `0x180007a11`
- `KERNEL32!GetLastError` at `0x180007afe`
- `KERNEL32!GetLastError` at `0x180007b2b`
- `KERNEL32!GetLastError` at `0x180007afe`
- `KERNEL32!GetLastError` at `0x180007b2b`
- `WINTRUST!CryptCATOpen` at `0x180007907`
- `WINTRUST!CryptCATOpen` at `0x180007907`
- `WINTRUST!CryptCATClose` at `0x180007b70`
- `WINTRUST!CryptCATClose` at `0x180007b70`
- `WINTRUST!CryptCATEnumerateMember` at `0x180007a25`
- `WINTRUST!CryptCATEnumerateMember` at `0x180007a25`
- `WINTRUST!CryptCATGetAttrInfo` at `0x180007972`
- `WINTRUST!CryptCATGetAttrInfo` at `0x180007972`

## string_xrefs

- `0x1800078c9`: `SdpVerifyDirectoryIntegrity`
- `0x180007a53`: `SdpVerifyDirectoryIntegrity`
- `0x180007a7d`: `SdpVerifyDirectoryIntegrity`
- `0x180007aa2`: `SdpVerifyDirectoryIntegrity`
- `0x180007ac2`: `SdpVerifyDirectoryIntegrity`
- `0x180007b42`: `SdpVerifyDirectoryIntegrity`

## pseudocode

```c
__int64 __fastcall SdpVerifyDirectoryIntegrity(const unsigned __int16 *a1, WCHAR *a2, struct _LIST_ENTRY *a3)
{
  WCHAR *v3; // r15
  unsigned __int8 *v4; // r14
  wchar_t *v5; // rsi
  int v6; // r8d
  signed int v7; // ebx
  char *v8; // r12
  CRYPTCATMEMBER *i; // rdx
  CRYPTCATATTRIBUTE *v10; // r12
  const unsigned __int16 *pbValue; // r12
  int v12; // eax
  int v13; // eax
  int FileHash; // eax
  int v15; // eax
  const wchar_t *pwszReferenceTag; // rdx
  CRYPTCATMEMBER *v17; // r13
  int v18; // r8d
  int v19; // r9d
  int v20; // r9d
  int v21; // r8d
  signed int v22; // eax
  signed int LastError; // eax
  wchar_t *String1; // [rsp+30h] [rbp-20h] BYREF
  unsigned __int8 *v26; // [rsp+38h] [rbp-18h] BYREF
  LPCWSTR lpFileName; // [rsp+40h] [rbp-10h] BYREF
  HANDLE hCatalog; // [rsp+48h] [rbp-8h]
  unsigned int v31; // [rsp+A8h] [rbp+58h] BYREF

  v3 = 0;
  v4 = 0;
  v5 = 0;
  lpFileName = 0;
  v31 = 0;
  v26 = 0;
  String1 = 0;
  if ( !a1 )
  {
    v6 = 1214;
LABEL_3:
    v7 = -2147024809;
    SdpDebugTrace(1u, L"SdpVerifyDirectoryIntegrity", v6, -2147024809);
    return (unsigned int)v7;
  }
  if ( !a2 )
  {
    v6 = 1215;
    goto LABEL_3;
  }
  v8 = (char *)CryptCATOpen(a2, 0, 0, 1u, 0x10001u);
  hCatalog = v8;
  if ( (unsigned __int64)(v8 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    if ( v7 >= 0 )
      v7 = -2147467259;
    SdpDebugTrace(1u, L"SdpVerifyDirectoryIntegrity", 1222, v7);
    if ( !v8 || v8 == (char *)-1LL )
      goto LABEL_49;
  }
  else
  {
    v7 = 0;
    for ( i = 0; ; i = v17 )
    {
      v17 = CryptCATEnumerateMember(v8, i);
      if ( !v17 )
      {
        if ( a3->Flink == a3 )
          goto LABEL_48;
        v18 = 1263;
        goto LABEL_26;
      }
      if ( v3 )
      {
        operator delete(v3);
        v3 = 0;
        lpFileName = 0;
      }
      if ( v4 )
      {
        operator delete(v4);
        v4 = 0;
        v26 = 0;
      }
      if ( v5 )
      {
        operator delete(v5);
        v5 = 0;
        String1 = 0;
      }
      v10 = CryptCATGetAttrInfo(v8, v17, (LPWSTR)L"Filename");
      if ( (unsigned __int64)&v10[-1].dwReserved + 7 > 0xFFFFFFFFFFFFFFFDuLL )
      {
        v22 = GetLastError();
        v7 = v22;
        if ( v22 > 0 )
          v7 = (unsigned __int16)v22 | 0x80070000;
        v18 = 1234;
        if ( v7 >= 0 )
          v7 = -2147467259;
        v19 = v7;
        goto LABEL_28;
      }
      pbValue = (const unsigned __int16 *)v10->pbValue;
      if ( !pbValue )
      {
        v19 = -2147467261;
        v18 = 1236;
LABEL_27:
        v7 = v19;
LABEL_28:
        SdpDebugTrace(1u, L"SdpVerifyDirectoryIntegrity", v18, v19);
        goto LABEL_48;
      }
      v12 = SdpRemoveFileFromList(a3, pbValue);
      v7 = v12;
      if ( v12 < 0 )
      {
        v19 = v12;
        v18 = 1240;
        goto LABEL_28;
      }
      v13 = SdpBuildPath(a1, pbValue, (unsigned __int16 **)&lpFileName);
      v7 = v13;
      if ( v13 < 0 )
        break;
      v3 = (WCHAR *)lpFileName;
      FileHash = SdpGetFileHash(lpFileName, &v26, &v31);
      v7 = FileHash;
      if ( FileHash < 0 )
      {
        SdpDebugTrace(1u, L"SdpVerifyDirectoryIntegrity", 1246, FileHash);
        v4 = v26;
        goto LABEL_48;
      }
      v4 = v26;
      v15 = SdpHashToString(v26, v31, &String1);
      v7 = v15;
      if ( v15 < 0 )
      {
        v20 = v15;
        v21 = 1249;
        goto LABEL_31;
      }
      pwszReferenceTag = v17->pwszReferenceTag;
      if ( !pwszReferenceTag )
      {
        v20 = -2147467261;
        v21 = 1251;
        v7 = -2147467261;
LABEL_31:
        SdpDebugTrace(1u, L"SdpVerifyDirectoryIntegrity", v21, v20);
        v5 = String1;
        goto LABEL_48;
      }
      v5 = String1;
      if ( _wcsicmp(String1, pwszReferenceTag) )
      {
        v18 = 1255;
LABEL_26:
        v19 = -2143551225;
        goto LABEL_27;
      }
      v8 = (char *)hCatalog;
    }
    SdpDebugTrace(1u, L"SdpVerifyDirectoryIntegrity", 1243, v13);
    v3 = (WCHAR *)lpFileName;
  }
LABEL_48:
  CryptCATClose(hCatalog);
LABEL_49:
  if ( v3 )
    operator delete(v3);
  if ( v4 )
    operator delete(v4);
  if ( v5 )
    operator delete(v5);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000787c  mov     [rsp-38h+arg_8], rbx
0x180007881  mov     [rsp-38h+arg_10], r8
0x180007886  mov     [rsp-38h+arg_0], rcx
0x18000788b  push    rbp
0x18000788c  push    rsi
0x18000788d  push    rdi
0x18000788e  push    r12
0x180007890  push    r13
0x180007892  push    r14
0x180007894  push    r15
0x180007896  mov     rbp, rsp
0x180007899  sub     rsp, 50h
0x18000789d  xor     r15d, r15d
0x1800078a0  xor     r14d, r14d
0x1800078a3  xor     esi, esi
0x1800078a5  mov     [rbp+lpFileName], r15
0x1800078a9  mov     [rbp+arg_18], r15d
0x1800078ad  mov     rax, rdx
0x1800078b0  mov     [rbp+var_18], r14
0x1800078b4  mov     [rbp+String1], rsi
0x1800078b8  test    rcx, rcx
0x1800078bb  jnz     short loc_1800078E2
0x1800078bd  mov     r8d, 4BEh; int
0x1800078c3  mov     r9d, 80070057h; int
0x1800078c9  lea     rdx, aSdpverifydirec_0; "SdpVerifyDirectoryIntegrity"
0x1800078d0  mov     ecx, 1; Level
0x1800078d5  mov     ebx, r9d
0x1800078d8  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800078dd  jmp     loc_180007B9D
0x1800078e2  test    rax, rax
0x1800078e5  jnz     short loc_1800078EF
0x1800078e7  mov     r8d, 4BFh
0x1800078ed  jmp     short loc_1800078C3
0x1800078ef  mov     edi, 1
0x1800078f4  mov     [rsp+50h+dwEncodingType], 10001h; dwEncodingType
0x1800078fc  mov     r9d, edi; dwPublicVersion
0x1800078ff  xor     r8d, r8d; hProv
0x180007902  xor     edx, edx; fdwOpenFlags
0x180007904  mov     rcx, rax; pwszFileName
0x180007907  call    cs:__imp_CryptCATOpen
0x18000790d  mov     r12, rax
0x180007910  mov     [rbp+hCatalog], rax
0x180007914  dec     rax
0x180007917  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000791b  ja      loc_180007B2B
0x180007921  xor     ebx, ebx
0x180007923  xor     edx, edx
0x180007925  jmp     loc_180007A22
0x18000792a  test    r15, r15
0x18000792d  jz      short loc_18000793E
0x18000792f  mov     rcx, r15; Block
0x180007932  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007937  xor     r15d, r15d
0x18000793a  mov     [rbp+lpFileName], r15
0x18000793e  test    r14, r14
0x180007941  jz      short loc_180007952
0x180007943  mov     rcx, r14; Block
0x180007946  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000794b  xor     r14d, r14d
0x18000794e  mov     [rbp+var_18], r14
0x180007952  test    rsi, rsi
0x180007955  jz      short loc_180007965
0x180007957  mov     rcx, rsi; Block
0x18000795a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000795f  xor     esi, esi
0x180007961  mov     [rbp+String1], rsi
0x180007965  lea     r8, aFilename; "Filename"
0x18000796c  mov     rdx, r13; pCatMember
0x18000796f  mov     rcx, r12; hCatalog
0x180007972  call    cs:__imp_CryptCATGetAttrInfo
0x180007978  mov     r12, rax
0x18000797b  dec     rax
0x18000797e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180007982  ja      loc_180007AFE
0x180007988  mov     r12, [r12+18h]
0x18000798d  test    r12, r12
0x180007990  jz      loc_180007AED
0x180007996  mov     rcx, [rbp+arg_10]; struct _LIST_ENTRY *
0x18000799a  mov     rdx, r12; unsigned __int16 *
0x18000799d  call    ?SdpRemoveFileFromList@@YAJPEAU_LIST_ENTRY@@PEBG@Z; SdpRemoveFileFromList(_LIST_ENTRY *,ushort const *)
0x1800079a2  mov     ebx, eax
0x1800079a4  test    eax, eax
0x1800079a6  js      loc_180007ADF
0x1800079ac  mov     rcx, [rbp+arg_0]; unsigned __int16 *
0x1800079b0  lea     r8, [rbp+lpFileName]; unsigned __int16 **
0x1800079b4  mov     rdx, r12; unsigned __int16 *
0x1800079b7  call    ?SdpBuildPath@@YAJPEBG0PEAPEAG@Z; SdpBuildPath(ushort const *,ushort const *,ushort * *)
0x1800079bc  mov     ebx, eax
0x1800079be  test    eax, eax
0x1800079c0  js      loc_180007ABF
0x1800079c6  mov     r15, [rbp+lpFileName]
0x1800079ca  lea     r8, [rbp+arg_18]; unsigned int *
0x1800079ce  mov     rcx, r15; lpFileName
0x1800079d1  lea     rdx, [rbp+var_18]; unsigned __int8 **
0x1800079d5  call    ?SdpGetFileHash@@YAJPEBGPEAPEAEAEAK@Z; SdpGetFileHash(ushort const *,uchar * *,ulong &)
0x1800079da  mov     ebx, eax
0x1800079dc  test    eax, eax
0x1800079de  js      loc_180007A9F
0x1800079e4  mov     r14, [rbp+var_18]
0x1800079e8  lea     r8, [rbp+String1]; unsigned __int16 **
0x1800079ec  mov     edx, [rbp+arg_18]; unsigned int
0x1800079ef  mov     rcx, r14; unsigned __int8 *
0x1800079f2  call    ?SdpHashToString@@YAJPEAEKPEAPEAG@Z; SdpHashToString(uchar *,ulong,ushort * *)
0x1800079f7  mov     ebx, eax
0x1800079f9  test    eax, eax
0x1800079fb  js      loc_180007A94
0x180007a01  mov     rdx, [r13+8]; String2
0x180007a05  test    rdx, rdx
0x180007a08  jz      short loc_180007A6E
0x180007a0a  mov     rsi, [rbp+String1]
0x180007a0e  mov     rcx, rsi; String1
0x180007a11  call    cs:__imp__wcsicmp
0x180007a17  test    eax, eax
0x180007a19  jnz     short loc_180007A66
0x180007a1b  mov     r12, [rbp+hCatalog]
0x180007a1f  mov     rdx, r13; pPrevMember
0x180007a22  mov     rcx, r12; hCatalog
0x180007a25  call    cs:__imp_CryptCATEnumerateMember
0x180007a2b  mov     r13, rax
0x180007a2e  test    rax, rax
0x180007a31  jnz     loc_18000792A
0x180007a37  mov     rax, [rbp+arg_10]
0x180007a3b  cmp     [rax], rax
0x180007a3e  jz      loc_180007B6C
0x180007a44  mov     r8d, 4EFh; int
0x180007a4a  mov     r9d, 803C0107h; int
0x180007a50  mov     ebx, r9d
0x180007a53  lea     rdx, aSdpverifydirec_0; "SdpVerifyDirectoryIntegrity"
0x180007a5a  mov     ecx, edi; Level
0x180007a5c  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180007a61  jmp     loc_180007B6C
0x180007a66  mov     r8d, 4E7h
0x180007a6c  jmp     short loc_180007A4A
0x180007a6e  mov     r9d, 80004003h; int
0x180007a74  mov     r8d, 4E3h; int
0x180007a7a  mov     ebx, r9d
0x180007a7d  lea     rdx, aSdpverifydirec_0; "SdpVerifyDirectoryIntegrity"
0x180007a84  mov     ecx, edi; Level
0x180007a86  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180007a8b  mov     rsi, [rbp+String1]
0x180007a8f  jmp     loc_180007B6C
0x180007a94  mov     r9d, eax
0x180007a97  mov     r8d, 4E1h
0x180007a9d  jmp     short loc_180007A7D
0x180007a9f  mov     r9d, eax; int
0x180007aa2  lea     rdx, aSdpverifydirec_0; "SdpVerifyDirectoryIntegrity"
0x180007aa9  mov     r8d, 4DEh; int
0x180007aaf  mov     ecx, edi; Level
0x180007ab1  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180007ab6  mov     r14, [rbp+var_18]
0x180007aba  jmp     loc_180007B6C
0x180007abf  mov     r9d, eax; int
0x180007ac2  lea     rdx, aSdpverifydirec_0; "SdpVerifyDirectoryIntegrity"
0x180007ac9  mov     r8d, 4DBh; int
0x180007acf  mov     ecx, edi; Level
0x180007ad1  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180007ad6  mov     r15, [rbp+lpFileName]
0x180007ada  jmp     loc_180007B6C
0x180007adf  mov     r9d, eax
0x180007ae2  mov     r8d, 4D8h
0x180007ae8  jmp     loc_180007A53
0x180007aed  mov     r9d, 80004003h
0x180007af3  mov     r8d, 4D4h
0x180007af9  jmp     loc_180007A50
0x180007afe  call    cs:__imp_GetLastError
0x180007b04  mov     ebx, eax
0x180007b06  test    eax, eax
0x180007b08  jle     short loc_180007B13
0x180007b0a  movzx   ebx, ax
0x180007b0d  or      ebx, 80070000h
0x180007b13  test    ebx, ebx
0x180007b15  mov     eax, 80004005h
0x180007b1a  mov     r8d, 4D2h
0x180007b20  cmovns  ebx, eax
0x180007b23  mov     r9d, ebx
0x180007b26  jmp     loc_180007A53
0x180007b2b  call    cs:__imp_GetLastError
0x180007b31  mov     ebx, eax
0x180007b33  test    eax, eax
0x180007b35  jle     short loc_180007B40
0x180007b37  movzx   ebx, ax
0x180007b3a  or      ebx, 80070000h
0x180007b40  test    ebx, ebx
0x180007b42  lea     rdx, aSdpverifydirec_0; "SdpVerifyDirectoryIntegrity"
0x180007b49  mov     eax, 80004005h
0x180007b4e  mov     r8d, 4C6h; int
0x180007b54  cmovns  ebx, eax
0x180007b57  mov     ecx, edi; Level
0x180007b59  mov     r9d, ebx; int
0x180007b5c  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180007b61  test    r12, r12
0x180007b64  jz      short loc_180007B76
0x180007b66  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x180007b6a  jz      short loc_180007B76
0x180007b6c  mov     rcx, [rbp+hCatalog]; hCatalog
0x180007b70  call    cs:__imp_CryptCATClose
0x180007b76  test    r15, r15
0x180007b79  jz      short loc_180007B83
0x180007b7b  mov     rcx, r15; Block
0x180007b7e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007b83  test    r14, r14
0x180007b86  jz      short loc_180007B90
0x180007b88  mov     rcx, r14; Block
0x180007b8b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007b90  test    rsi, rsi
0x180007b93  jz      short loc_180007B9D
0x180007b95  mov     rcx, rsi; Block
0x180007b98  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007b9d  mov     eax, ebx
0x180007b9f  mov     rbx, [rsp+50h+arg_8]
0x180007ba7  add     rsp, 50h
0x180007bab  pop     r15
0x180007bad  pop     r14
0x180007baf  pop     r13
0x180007bb1  pop     r12
0x180007bb3  pop     rdi
0x180007bb4  pop     rsi
0x180007bb5  pop     rbp
0x180007bb6  retn
```
