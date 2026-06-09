# I_CryptCATCDFEnumNextMember

- ea: `0x18002ddbc`
- end: `0x18002e344`
- name: `I_CryptCATCDFEnumNextMember`
- size: `1416`
- prototype: `__int64 __usercall@<rax>(struct CRYPTCATCDF_ *@<rcx>, unsigned __int16 *@<rdx>, void (*)(unsigned int, unsigned int, unsigned __int16 *)@<r8>, int, int)`
- caller_count: `2`
- callee_count: `17`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18003bc50`
- `0x18003bce0`

## callees

- `0x1800077b0`
- `0x18000bdb0`
- `0x18000d1c0`
- `0x18000d270`
- `0x18002ddbc`
- `0x18003a6c0`
- `0x18003a838`
- `0x18003aafc`
- `0x18003ae4c`
- `0x18003b10c`
- `0x18003b2b8`
- `0x18003b498`
- `0x18003b5e4`
- `0x18004de46`
- `0x18004de52`
- `0x18004deb0`
- `0x180051010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002e027`
- `msvcrt!_wcsicmp` at `0x18002e027`
- `msvcrt!_wcsnicmp` at `0x18002df10`
- `msvcrt!_wcsnicmp` at `0x18002df10`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002df6a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002df6a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e318`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e318`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002df93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e122`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e18b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e243`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002df93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e122`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e18b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e243`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e041`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e0da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e2d1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e2da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e2e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e30d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e041`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e0da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e2d1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e2da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e2e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e30d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e2f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e2f7`
- `CRYPT32!CryptSIPRetrieveSubjectGuidForCatalogFile` at `0x18002e17d`
- `CRYPT32!CryptSIPRetrieveSubjectGuidForCatalogFile` at `0x18002e17d`

## pseudocode

```c
wchar_t *__fastcall I_CryptCATCDFEnumNextMember(
        struct CRYPTCATCDF_ *a1,
        unsigned __int16 *a2,
        void (__fastcall *a3)(__int64, __int64, unsigned __int16 *),
        CRYPTCATMEMBER **a4,
        int a5,
        int a6)
{
  wchar_t *v9; // rsi
  WCHAR *v10; // rdi
  BYTE *v11; // r13
  DWORD LastError; // ebx
  unsigned __int64 v13; // r8
  int Member; // eax
  BOOL v15; // r12d
  const unsigned __int16 *v16; // rdx
  __int64 v17; // rdi
  wchar_t *v18; // rax
  int v19; // eax
  _DWORD *hCATStore; // rcx
  int v21; // eax
  unsigned int v22; // r10d
  const unsigned __int16 *v23; // rdx
  const unsigned __int16 *v24; // r9
  unsigned int v25; // r10d
  const unsigned __int16 *v26; // rdx
  wchar_t *v27; // r12
  DWORD v28; // eax
  WCHAR *v29; // r8
  CRYPTCATMEMBER *v30; // r12
  wchar_t *String1; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbSIPIndirectData; // [rsp+48h] [rbp-B8h] BYREF
  int v34; // [rsp+4Ch] [rbp-B4h]
  LPCWSTR lpFileName; // [rsp+50h] [rbp-B0h] BYREF
  BYTE *pbSIPIndirectData; // [rsp+58h] [rbp-A8h] BYREF
  LPWSTR pwszReferenceTag; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE hObject; // [rsp+68h] [rbp-98h]
  CRYPTCATMEMBER **v39; // [rsp+70h] [rbp-90h]
  struct _GUID Buf1; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 Src[1032]; // [rsp+90h] [rbp-70h] BYREF

  v39 = a4;
  hObject = (HANDLE)-1LL;
  String1 = 0;
  lpFileName = 0;
  pwszReferenceTag = 0;
  pbSIPIndirectData = 0;
  v9 = 0;
  cbSIPIndirectData = 0;
  v10 = 0;
  v11 = 0;
  Buf1 = 0;
  if ( !a1 || (unsigned __int64)a1->hFile - 1 > 0xFFFFFFFFFFFFFFFDuLL )
    goto LABEL_64;
  LastError = 0;
  Src[0] = 0;
  CDFPositionAtLastMember(a1);
  Member = CDFGetNextMember(a1, Src, v13, a2);
  v15 = 0;
  if ( !Member )
    goto LABEL_65;
  CDFPositionAtLastMember(a1);
  if ( !CDFGetParam(a1, v16, Src, 0, (unsigned __int16 **)&lpFileName, Src) )
  {
    if ( a3 )
      a3(0x10000, 65537, Src);
    LastError = -2147467259;
    goto LABEL_8;
  }
  v17 = -1;
  do
    ++v17;
  while ( Src[v17] );
  v18 = (wchar_t *)CatalogNew((unsigned int)(2 * v17 + 2));
  v9 = v18;
  if ( !v18 )
  {
    LastError = 8;
LABEL_8:
    v10 = (WCHAR *)lpFileName;
    goto LABEL_65;
  }
  memcpy_0(v18, Src, 2 * v17 + 2);
  v19 = _wcsnicmp(v9, L"<HASH>", 6u);
  hCATStore = a1->hCATStore;
  v34 = v19;
  if ( !hCATStore || hCATStore[1] != 256 && v19 && a6 )
  {
    v10 = (WCHAR *)lpFileName;
    a5 = 0;
LABEL_64:
    LastError = 87;
    goto LABEL_65;
  }
  v10 = (WCHAR *)lpFileName;
  hObject = CreateFileW(lpFileName, 0x80000000, 5u, 0, 3u, 0x80u, 0);
  if ( hObject == (HANDLE)-1LL )
  {
    if ( a3 )
      a3(0x10000, 65540, v10);
    LastError = GetLastError();
    goto LABEL_65;
  }
  v21 = StringCchCopyW(Src, 0x404u, v9);
  if ( v21 < 0 )
    goto LABEL_61;
  v21 = StringCchCatW(Src, v22, L"PageHashes");
  if ( v21 < 0 )
    goto LABEL_61;
  CDFPositionAtLastMember(a1);
  v24 = L"true";
  if ( !g_PageHashes )
    v24 = L"false";
  CDFGetParam(a1, v23, Src, v24, &String1, v9);
  if ( String1 )
    LOBYTE(v15) = _wcsicmp(String1, L"true") == 0;
  else
    v15 = g_PageHashes;
  LocalFree(String1);
  CryptCATSetCreatePageHashesFlag(a1->hCATStore, v15);
  v21 = StringCchCopyW(Src, 0x404u, v9);
  if ( v21 < 0 || (v21 = StringCchCatW(Src, v25, L"ALTSIPID"), v21 < 0) )
  {
LABEL_61:
    a5 = 0;
    LastError = (unsigned __int16)v21;
    goto LABEL_65;
  }
  CDFPositionAtLastMember(a1);
  String1 = 0;
  CDFGetParam(a1, v26, Src, 0, &String1, v9);
  v27 = String1;
  if ( String1 )
  {
    CDFTextToGUID(String1, &Buf1, (void (*)(unsigned int, unsigned int, unsigned __int16 *))a3);
    LocalFree(v27);
    LOBYTE(v27) = 1;
  }
  else if ( !CryptSIPRetrieveSubjectGuidForCatalogFile(v10, 0, &Buf1) )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = -2147467259;
    goto LABEL_65;
  }
  LODWORD(String1) = 0;
  while ( !CDFCalcIndirectData(a1, 0, v10, &Buf1, &cbSIPIndirectData, &pbSIPIndirectData, (unsigned int *)&String1) )
  {
    v28 = GetLastError();
    LastError = v28;
    if ( v28 != 193 && v28 != -2147024703 || !g_FallbackFlat || (_BYTE)v27 || memcmp_0(&Buf1, qword_180057450, 0x10u) )
    {
      if ( !LastError )
        LastError = -2147467259;
      if ( a3 )
        a3(0x10000, 65538, v10);
      v11 = pbSIPIndirectData;
      goto LABEL_65;
    }
    Buf1 = (struct _GUID)xmmword_180055B40;
  }
  v11 = pbSIPIndirectData;
  v29 = v9;
  if ( a6 && !v34 )
  {
    if ( !(unsigned int)MsCatConstructHashTag(
                          *((unsigned int *)pbSIPIndirectData + 12),
                          *((_QWORD *)pbSIPIndirectData + 7),
                          &pwszReferenceTag) )
    {
      LastError = 8;
      goto LABEL_65;
    }
    v29 = pwszReferenceTag;
  }
  v30 = CryptCATPutMemberInfo(a1->hCATStore, v10, v29, &Buf1, (DWORD)String1, cbSIPIndirectData, v11);
  if ( v30 )
  {
    if ( !a6 || v34 || (unsigned int)CDFMakeCompatibilityMember(a1) )
    {
      *v39 = v30;
      LastError = 0;
    }
  }
  else
  {
    LastError = GetLastError();
    if ( LastError == -2146885627 && a3 )
      a3(0x10000, 2, v9);
  }
LABEL_65:
  LocalFree(pwszReferenceTag);
  LocalFree(v11);
  LocalFree(v10);
  if ( hObject != (HANDLE)-1LL )
    CloseHandle(hObject);
  if ( LastError && !a5 )
  {
    LocalFree(v9);
    v9 = 0;
  }
  SetLastError(LastError);
  return v9;
}

```

## disassembly

```asm
0x18002ddbc  push    rbp
0x18002ddbe  push    rbx
0x18002ddbf  push    rsi
0x18002ddc0  push    rdi
0x18002ddc1  push    r12
0x18002ddc3  push    r13
0x18002ddc5  push    r14
0x18002ddc7  push    r15
0x18002ddc9  lea     rbp, [rsp-7B8h]
0x18002ddd1  sub     rsp, 8B8h
0x18002ddd8  mov     rax, cs:__security_cookie
0x18002dddf  xor     rax, rsp
0x18002dde2  mov     [rbp+7F0h+var_50], rax
0x18002dde9  mov     r14, rcx
0x18002ddec  mov     [rsp+8F0h+var_880], r9
0x18002ddf1  xor     ecx, ecx
0x18002ddf3  mov     [rsp+8F0h+hObject], 0FFFFFFFFFFFFFFFFh
0x18002ddfc  mov     [rsp+8F0h+String1], rcx
0x18002de01  xorps   xmm0, xmm0
0x18002de04  mov     [rsp+8F0h+lpFileName], rcx
0x18002de09  mov     r15, r8
0x18002de0c  mov     [rsp+8F0h+pwszReferenceTag], rcx
0x18002de11  mov     r12, rdx
0x18002de14  mov     [rsp+8F0h+pbSIPIndirectData], rcx
0x18002de19  mov     esi, ecx
0x18002de1b  mov     [rsp+8F0h+cbSIPIndirectData], ecx
0x18002de1f  mov     edi, ecx
0x18002de21  mov     r13d, ecx
0x18002de24  movups  xmmword ptr [rsp+8F0h+Buf1.Data1], xmm0
0x18002de29  test    r14, r14
0x18002de2c  jz      loc_18002E2C4
0x18002de32  mov     rax, [r14+8]
0x18002de36  dec     rax
0x18002de39  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002de3d  ja      loc_18002E2C4
0x18002de43  mov     ebx, ecx
0x18002de45  mov     [rbp+7F0h+Src], cx
0x18002de49  mov     rcx, r14; struct CRYPTCATCDF_ *
0x18002de4c  call    ?CDFPositionAtLastMember@@YAHPEAUCRYPTCATCDF_@@@Z; CDFPositionAtLastMember(CRYPTCATCDF_ *)
0x18002de51  mov     r9, r12; unsigned __int16 *
0x18002de54  lea     rdx, [rbp+7F0h+Src]; unsigned __int16 *
0x18002de58  mov     rcx, r14; struct CRYPTCATCDF_ *
0x18002de5b  call    ?CDFGetNextMember@@YAHPEAUCRYPTCATCDF_@@PEAG_KPEBG@Z; CDFGetNextMember(CRYPTCATCDF_ *,ushort *,unsigned __int64,ushort const *)
0x18002de60  xor     r12d, r12d
0x18002de63  test    eax, eax
0x18002de65  jz      loc_18002E2CC
0x18002de6b  mov     rcx, r14; struct CRYPTCATCDF_ *
0x18002de6e  call    ?CDFPositionAtLastMember@@YAHPEAUCRYPTCATCDF_@@@Z; CDFPositionAtLastMember(CRYPTCATCDF_ *)
0x18002de73  lea     rax, [rbp+7F0h+Src]
0x18002de77  xor     r9d, r9d; unsigned __int16 *
0x18002de7a  mov     qword ptr [rsp+8F0h+dwFlagsAndAttributes], rax; unsigned __int16 *
0x18002de7f  lea     r8, [rbp+7F0h+Src]; unsigned __int16 *
0x18002de83  lea     rax, [rsp+8F0h+lpFileName]
0x18002de88  mov     rcx, r14; struct CRYPTCATCDF_ *
0x18002de8b  mov     qword ptr [rsp+8F0h+dwCreationDisposition], rax; unsigned __int16 **
0x18002de90  call    ?CDFGetParam@@YAHPEAUCRYPTCATCDF_@@PEBG11PEAPEAG1@Z; CDFGetParam(CRYPTCATCDF_ *,ushort const *,ushort const *,ushort const *,ushort * *,ushort const *)
0x18002de95  test    eax, eax
0x18002de97  jnz     short loc_18002DEC1
0x18002de99  test    r15, r15
0x18002de9c  jz      short loc_18002DEB2
0x18002de9e  mov     edx, 10001h
0x18002dea3  lea     r8, [rbp+7F0h+Src]
0x18002dea7  mov     rax, r15
0x18002deaa  lea     ecx, [rdx-1]
0x18002dead  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002deb2  mov     ebx, 80004005h
0x18002deb7  mov     rdi, [rsp+8F0h+lpFileName]
0x18002debc  jmp     loc_18002E2CC
0x18002dec1  lea     rax, [rbp+7F0h+Src]
0x18002dec5  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002dec9  inc     rdi
0x18002decc  cmp     [rax+rdi*2], r12w
0x18002ded1  jnz     short loc_18002DEC9
0x18002ded3  lea     ecx, ds:2[rdi*2]; uBytes
0x18002deda  call    CatalogNew
0x18002dedf  mov     rsi, rax
0x18002dee2  test    rax, rax
0x18002dee5  jnz     short loc_18002DEEC
0x18002dee7  lea     ebx, [rax+8]
0x18002deea  jmp     short loc_18002DEB7
0x18002deec  lea     r8, ds:2[rdi*2]; Size
0x18002def4  mov     rcx, rsi; void *
0x18002def7  lea     rdx, [rbp+7F0h+Src]; Src
0x18002defb  call    memcpy_0
0x18002df00  mov     r8d, 6; MaxCount
0x18002df06  lea     rdx, aHash; "<HASH>"
0x18002df0d  mov     rcx, rsi; String1
0x18002df10  call    cs:__imp__wcsnicmp
0x18002df16  mov     rcx, [r14+28h]
0x18002df1a  mov     [rsp+8F0h+var_8A4], eax
0x18002df1e  test    rcx, rcx
0x18002df21  jz      loc_18002E2B1
0x18002df27  cmp     dword ptr [rcx+4], 100h
0x18002df2e  jz      short loc_18002DF41
0x18002df30  test    eax, eax
0x18002df32  jz      short loc_18002DF41
0x18002df34  cmp     [rbp+7F0h+arg_28], r12d
0x18002df3b  jnz     loc_18002E2B1
0x18002df41  mov     rdi, [rsp+8F0h+lpFileName]
0x18002df46  xor     r9d, r9d; lpSecurityAttributes
0x18002df49  mov     [rsp+8F0h+hTemplateFile], r12; hTemplateFile
0x18002df4e  mov     edx, 80000000h; dwDesiredAccess
0x18002df53  mov     [rsp+8F0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18002df5b  mov     rcx, rdi; lpFileName
0x18002df5e  mov     [rsp+8F0h+dwCreationDisposition], 3; dwCreationDisposition
0x18002df66  lea     r8d, [r9+5]; dwShareMode
0x18002df6a  call    cs:__imp_CreateFileW
0x18002df70  mov     [rsp+8F0h+hObject], rax
0x18002df75  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002df79  jnz     short loc_18002DFA0
0x18002df7b  test    r15, r15
0x18002df7e  jz      short loc_18002DF93
0x18002df80  mov     edx, 10004h
0x18002df85  mov     r8, rdi
0x18002df88  mov     rax, r15
0x18002df8b  lea     ecx, [rdx-4]
0x18002df8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002df93  call    cs:__imp_GetLastError
0x18002df99  mov     ebx, eax
0x18002df9b  jmp     loc_18002E2CC
0x18002dfa0  mov     r10d, 404h
0x18002dfa6  lea     rcx, [rbp+7F0h+Src]; unsigned __int16 *
0x18002dfaa  mov     edx, r10d; unsigned __int64
0x18002dfad  mov     r8, rsi; unsigned __int16 *
0x18002dfb0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002dfb5  test    eax, eax
0x18002dfb7  js      loc_18002E2A5
0x18002dfbd  lea     r8, aPagehashes; "PageHashes"
0x18002dfc4  mov     edx, r10d; unsigned __int64
0x18002dfc7  lea     rcx, [rbp+7F0h+Src]; unsigned __int16 *
0x18002dfcb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002dfd0  test    eax, eax
0x18002dfd2  js      loc_18002E2A5
0x18002dfd8  mov     rcx, r14; struct CRYPTCATCDF_ *
0x18002dfdb  call    ?CDFPositionAtLastMember@@YAHPEAUCRYPTCATCDF_@@@Z; CDFPositionAtLastMember(CRYPTCATCDF_ *)
0x18002dfe0  cmp     cs:?g_PageHashes@@3HA, r12d; int g_PageHashes
0x18002dfe7  lea     rax, aFalse; "false"
0x18002dfee  lea     r9, aTrue; "true"
0x18002dff5  mov     qword ptr [rsp+8F0h+dwFlagsAndAttributes], rsi; unsigned __int16 *
0x18002dffa  cmovz   r9, rax; unsigned __int16 *
0x18002dffe  lea     r8, [rbp+7F0h+Src]; unsigned __int16 *
0x18002e002  lea     rax, [rsp+8F0h+String1]
0x18002e007  mov     rcx, r14; struct CRYPTCATCDF_ *
0x18002e00a  mov     qword ptr [rsp+8F0h+dwCreationDisposition], rax; unsigned __int16 **
0x18002e00f  call    ?CDFGetParam@@YAHPEAUCRYPTCATCDF_@@PEBG11PEAPEAG1@Z; CDFGetParam(CRYPTCATCDF_ *,ushort const *,ushort const *,ushort const *,ushort * *,ushort const *)
0x18002e014  cmp     [rsp+8F0h+String1], r12
0x18002e019  jz      short loc_18002E035
0x18002e01b  mov     rcx, [rsp+8F0h+String1]; String1
0x18002e020  lea     rdx, aTrue; "true"
0x18002e027  call    cs:__imp__wcsicmp
0x18002e02d  test    eax, eax
0x18002e02f  setz    r12b
0x18002e033  jmp     short loc_18002E03C
0x18002e035  mov     r12d, cs:?g_PageHashes@@3HA; int g_PageHashes
0x18002e03c  mov     rcx, [rsp+8F0h+String1]; hMem
0x18002e041  call    cs:__imp_LocalFree
0x18002e047  mov     rcx, [r14+28h]; hCatalog
0x18002e04b  mov     edx, r12d; newCreatePageHashesFlag
0x18002e04e  call    CryptCATSetCreatePageHashesFlag
0x18002e053  mov     r10d, 404h
0x18002e059  lea     rcx, [rbp+7F0h+Src]; unsigned __int16 *
0x18002e05d  mov     edx, r10d; unsigned __int64
0x18002e060  mov     r8, rsi; unsigned __int16 *
0x18002e063  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002e068  xor     r12d, r12d
0x18002e06b  test    eax, eax
0x18002e06d  js      loc_18002E2A5
0x18002e073  lea     r8, aAltsipid; "ALTSIPID"
0x18002e07a  mov     edx, r10d; unsigned __int64
0x18002e07d  lea     rcx, [rbp+7F0h+Src]; unsigned __int16 *
0x18002e081  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002e086  test    eax, eax
0x18002e088  js      loc_18002E2A5
0x18002e08e  mov     rcx, r14; struct CRYPTCATCDF_ *
0x18002e091  call    ?CDFPositionAtLastMember@@YAHPEAUCRYPTCATCDF_@@@Z; CDFPositionAtLastMember(CRYPTCATCDF_ *)
0x18002e096  lea     rax, [rsp+8F0h+String1]
0x18002e09b  mov     qword ptr [rsp+8F0h+dwFlagsAndAttributes], rsi; unsigned __int16 *
0x18002e0a0  xor     r9d, r9d; unsigned __int16 *
0x18002e0a3  mov     qword ptr [rsp+8F0h+dwCreationDisposition], rax; unsigned __int16 **
0x18002e0a8  lea     r8, [rbp+7F0h+Src]; unsigned __int16 *
0x18002e0ac  mov     [rsp+8F0h+String1], r12
0x18002e0b1  mov     rcx, r14; struct CRYPTCATCDF_ *
0x18002e0b4  call    ?CDFGetParam@@YAHPEAUCRYPTCATCDF_@@PEBG11PEAPEAG1@Z; CDFGetParam(CRYPTCATCDF_ *,ushort const *,ushort const *,ushort const *,ushort * *,ushort const *)
0x18002e0b9  mov     r12, [rsp+8F0h+String1]
0x18002e0be  test    r12, r12
0x18002e0c1  jz      loc_18002E173
0x18002e0c7  mov     r8, r15; void (*)(unsigned int, unsigned int, unsigned __int16 *)
0x18002e0ca  lea     rdx, [rsp+8F0h+Buf1]; struct _GUID *
0x18002e0cf  mov     rcx, r12; unsigned __int16 *
0x18002e0d2  call    ?CDFTextToGUID@@YAXPEBGPEAU_GUID@@P6AXKKPEAG@Z@Z; CDFTextToGUID(ushort const *,_GUID *,void (*)(ulong,ulong,ushort *))
0x18002e0d7  mov     rcx, r12; hMem
0x18002e0da  call    cs:__imp_LocalFree
0x18002e0e0  mov     r12d, 1
0x18002e0e6  mov     dword ptr [rsp+8F0h+String1], ebx
0x18002e0ea  lea     rax, [rsp+8F0h+String1]
0x18002e0ef  mov     r8, rdi; unsigned __int16 *
0x18002e0f2  mov     [rsp+8F0h+hTemplateFile], rax; unsigned int *
0x18002e0f7  lea     r9, [rsp+8F0h+Buf1]; struct _GUID *
0x18002e0fc  lea     rax, [rsp+8F0h+pbSIPIndirectData]
0x18002e101  xor     edx, edx; bool
0x18002e103  mov     qword ptr [rsp+8F0h+dwFlagsAndAttributes], rax; unsigned __int8 **
0x18002e108  mov     rcx, r14; struct CRYPTCATCDF_ *
0x18002e10b  lea     rax, [rsp+8F0h+cbSIPIndirectData]
0x18002e110  mov     qword ptr [rsp+8F0h+dwCreationDisposition], rax; unsigned int *
0x18002e115  call    ?CDFCalcIndirectData@@YAHPEBUCRYPTCATCDF_@@_NPEBGPEBU_GUID@@PEAKPEAPEAE4@Z; CDFCalcIndirectData(CRYPTCATCDF_ const *,bool,ushort const *,_GUID const *,ulong *,uchar * *,ulong *)
0x18002e11a  test    eax, eax
0x18002e11c  jnz     loc_18002E1D7
0x18002e122  call    cs:__imp_GetLastError
0x18002e128  mov     ebx, eax
0x18002e12a  cmp     eax, 0C1h
0x18002e12f  jz      short loc_18002E138
0x18002e131  cmp     eax, 800700C1h
0x18002e136  jnz     short loc_18002E1A8
0x18002e138  cmp     cs:?g_FallbackFlat@@3HA, r13d; int g_FallbackFlat
0x18002e13f  jz      short loc_18002E1A8
0x18002e141  test    r12b, r12b
0x18002e144  jnz     short loc_18002E1A8
0x18002e146  mov     r8d, 10h; Size
0x18002e14c  lea     rdx, qword_180057450; Buf2
0x18002e153  lea     rcx, [rsp+8F0h+Buf1]; Buf1
0x18002e158  call    memcmp_0
0x18002e15d  test    eax, eax
0x18002e15f  jnz     short loc_18002E1A8
0x18002e161  movups  xmm0, cs:xmmword_180055B40
0x18002e168  movdqu  xmmword ptr [rsp+8F0h+Buf1.Data1], xmm0
0x18002e16e  jmp     loc_18002E0EA
0x18002e173  lea     r8, [rsp+8F0h+Buf1]; pgSubject
0x18002e178  xor     edx, edx; hFileIn
0x18002e17a  mov     rcx, rdi; FileName
0x18002e17d  call    cs:__imp_CryptSIPRetrieveSubjectGuidForCatalogFile
0x18002e183  test    eax, eax
0x18002e185  jnz     loc_18002E0E6
0x18002e18b  call    cs:__imp_GetLastError
0x18002e191  xor     r12d, r12d
0x18002e194  mov     ebx, eax
0x18002e196  test    eax, eax
0x18002e198  jnz     loc_18002E2CC
0x18002e19e  mov     ebx, 80004005h
0x18002e1a3  jmp     loc_18002E2CC
0x18002e1a8  xor     r12d, r12d
0x18002e1ab  mov     eax, 80004005h
0x18002e1b0  test    ebx, ebx
0x18002e1b2  cmovz   ebx, eax
0x18002e1b5  test    r15, r15
0x18002e1b8  jz      short loc_18002E1CD
0x18002e1ba  mov     edx, 10002h
0x18002e1bf  mov     r8, rdi
0x18002e1c2  mov     rax, r15
0x18002e1c5  lea     ecx, [rdx-2]
0x18002e1c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e1cd  mov     r13, [rsp+8F0h+pbSIPIndirectData]
0x18002e1d2  jmp     loc_18002E2CC
0x18002e1d7  mov     r13, [rsp+8F0h+pbSIPIndirectData]
0x18002e1dc  xor     r12d, r12d
0x18002e1df  mov     r8, rsi
0x18002e1e2  cmp     [rbp+7F0h+arg_28], r12d
0x18002e1e9  jz      short loc_18002E215
0x18002e1eb  cmp     [rsp+8F0h+var_8A4], r12d
0x18002e1f0  jnz     short loc_18002E215
0x18002e1f2  mov     rdx, [r13+38h]
0x18002e1f6  lea     r8, [rsp+8F0h+pwszReferenceTag]
0x18002e1fb  mov     ecx, [r13+30h]
0x18002e1ff  call    MsCatConstructHashTag
0x18002e204  test    eax, eax
0x18002e206  jnz     short loc_18002E210
0x18002e208  lea     ebx, [rax+8]
0x18002e20b  jmp     loc_18002E2CC
0x18002e210  mov     r8, [rsp+8F0h+pwszReferenceTag]; pwszReferenceTag
0x18002e215  mov     eax, [rsp+8F0h+cbSIPIndirectData]
0x18002e219  lea     r9, [rsp+8F0h+Buf1]; pgSubjectType
0x18002e21e  mov     rcx, [r14+28h]; hCatalog
0x18002e222  mov     rdx, rdi; pwszFileName
0x18002e225  mov     [rsp+8F0h+hTemplateFile], r13; pbSIPIndirectData
0x18002e22a  mov     [rsp+8F0h+dwFlagsAndAttributes], eax; cbSIPIndirectData
0x18002e22e  mov     eax, dword ptr [rsp+8F0h+String1]
0x18002e232  mov     [rsp+8F0h+dwCreationDisposition], eax; dwCertVersion
0x18002e236  call    CryptCATPutMemberInfo
0x18002e23b  mov     r12, rax
0x18002e23e  test    rax, rax
0x18002e241  jnz     short loc_18002E26E
0x18002e243  call    cs:__imp_GetLastError
0x18002e249  mov     ebx, eax
0x18002e24b  cmp     eax, 80092005h
0x18002e250  jnz     short loc_18002E2CC
0x18002e252  test    r15, r15
0x18002e255  jz      short loc_18002E2CC
0x18002e257  mov     r8, rsi
0x18002e25a  lea     edx, [r12+2]
0x18002e25f  mov     ecx, 10000h
0x18002e264  mov     rax, r15
0x18002e267  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e26c  jmp     short loc_18002E2CC
0x18002e26e  cmp     [rbp+7F0h+arg_28], 0
0x18002e275  jz      short loc_18002E295
0x18002e277  cmp     [rsp+8F0h+var_8A4], 0
0x18002e27c  jnz     short loc_18002E295
0x18002e27e  lea     r9, [rsp+8F0h+Buf1]
0x18002e283  mov     r8, rdi
0x18002e286  mov     rdx, r12
0x18002e289  mov     rcx, r14; struct CRYPTCATCDF_ *
  ... truncated ...
```
