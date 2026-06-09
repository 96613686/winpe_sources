# SoftpubDumpStructure

- ea: `0x180046380`
- end: `0x180046cd4`
- name: `SoftpubDumpStructure`
- size: `2388`
- prototype: `__int64 __fastcall(struct _CRYPT_PROVIDER_DATA *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x18000cf50`
- `0x18001e4e0`
- `0x180045934`
- `0x180045b18`
- `0x180045e84`
- `0x180046230`
- `0x180046380`
- `0x18004deb0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800463df`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800463df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046ca1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046ca1`

## string_xrefs

- `0x180046906`: `|       |.. pcwszFilePath:            %s\n`
- `0x1800467f4`: `|       |.. pcwszCatalogFilePath:     %s\n`
- `0x180046822`: `|       |.. pcwszMemberFilePath:      %s\n`
- `0x18004684c`: `|       |.. pbCaclulatedFileHash:     `
- `0x1800468a3`: `|       +-- cbCaclulatedFileHash:     %ld\n`
- `0x18004676b`: `|       |.. cbMemSignedMsg:           %ld\n`
- `0x180046782`: `|       +.. pbMemSignedMsg:           0x%p\n`
- `0x1800469dc`: `|.. dwRegSecuritySettings:            0x%08.8lx\n`

## pseudocode

```c
__int64 __fastcall SoftpubDumpStructure(struct _CRYPT_PROVIDER_DATA *a1)
{
  HANDLE FileW; // rax
  void *v3; // rbx
  WINTRUST_DATA *pWintrustData; // rdi
  struct WINTRUST_FILE_INFO_ *v6; // rax
  struct WINTRUST_FILE_INFO_ *v7; // r8
  unsigned int v8; // r15d
  struct _FILETIME *hFile; // rcx
  struct WINTRUST_FILE_INFO_ *v10; // rax
  struct WINTRUST_FILE_INFO_ *v11; // rax
  unsigned int v12; // r15d
  const unsigned __int16 *v13; // rdx
  struct WINTRUST_FILE_INFO_ *v14; // rax
  struct WINTRUST_FILE_INFO_ *v15; // rax
  struct WINTRUST_FILE_INFO_ *v16; // rax
  int v17; // r15d
  struct WINTRUST_FILE_INFO_ *pFile; // rax
  struct WINTRUST_FILE_INFO_ *v19; // rcx
  GUID *pgKnownSubject; // rcx
  GUID *pgActionID; // rcx
  signed int cdwTrustStepErrors; // eax
  signed int i; // edi
  const unsigned __int16 *v24; // rdx
  signed int chStores; // eax
  signed int j; // edi
  const unsigned __int16 *v27; // rdx
  GUID *p_gSubject; // rcx
  signed int k; // edi
  CRYPT_PROVIDER_SGNR *ProvSignerFromChain; // r13
  int csCounterSigners; // eax
  signed int v32; // r15d
  CRYPT_PROVIDER_SGNR *v33; // rax
  const char *v34; // r8
  _WORD v35[64]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v36[64]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v37[128]; // [rsp+140h] [rbp+40h] BYREF

  FileW = CreateFileW(L"C:\\TRUSTPOL.TXT", 0xC0000000, 0, 0, 2u, 0x80u, 0);
  v3 = FileW;
  if ( FileW == (HANDLE)-1LL )
    return 1;
  FPrintfU(FileW, L"CRYPT_PROVIDER_DATA:\r\n");
  pWintrustData = a1->pWintrustData;
  FPrintfU(v3, L"+======================================================\r\n");
  FPrintfU(v3, L"+-- pWintrustData:\r\n");
  FPrintfU(v3, L"|   |.. cbStruct:                     %ld\r\n", pWintrustData->cbStruct);
  FPrintfU(v3, L"|   |.. pPolicyCallbackData:          %p\r\n", pWintrustData->pPolicyCallbackData);
  FPrintfU(v3, L"|   |.. dwUIChoice:                   %ld\r\n", pWintrustData->dwUIChoice);
  FPrintfU(v3, L"|   |.. fdRevocationChecks:           %ld\r\n", pWintrustData->fdwRevocationChecks);
  FPrintfU(v3, L"|   |.. dwUnionChoice:                %ld\r\n", pWintrustData->dwUnionChoice);
  switch ( pWintrustData->dwUnionChoice )
  {
    case 1u:
      pFile = pWintrustData->pFile;
      if ( pFile && pFile->cbStruct >= 0x18 )
      {
        FPrintfU(v3, L"|   +-- pFile:\r\n");
        FPrintfU(v3, L"|       |.. cbStruct:                 %ld\r\n", pWintrustData->pFile->cbStruct);
        FPrintfU(v3, L"|       |.. pcwszFilePath:            %s\r\n", pWintrustData->pFile->pcwszFilePath);
        FPrintfU(v3, L"|       |.. hFile:                    0x%p\r\n", pWintrustData->pFile->hFile);
        v35[0] = 0;
        v19 = pWintrustData->pFile;
        if ( v19->cbStruct >= 0x20 )
        {
          pgKnownSubject = v19->pgKnownSubject;
          if ( pgKnownSubject )
            guid2wstr(pgKnownSubject, v35);
        }
        FPrintfU(v3, L"|       +-- pgKnownSubject:           %s\r\n", v35);
      }
      else
      {
        FPrintfU(v3, L"|   +-- pFile: <<< bad parameter! >>>\r\n");
      }
      break;
    case 2u:
      v15 = pWintrustData->pFile;
      if ( v15 && v15->cbStruct >= 0x28 )
      {
        FPrintfU(v3, L"|   +-- pCatalog:\r\n");
        FPrintfU(v3, L"|       |.. cbStruct:                 %ld\r\n", pWintrustData->pFile->cbStruct);
        FPrintfU(v3, L"|       |.. dwCatalogVersion:         0x%lx\r\n", *(&pWintrustData->pFile->cbStruct + 1));
        FPrintfU(v3, L"|       |.. pcwszCatalogFilePath:     %s\r\n", pWintrustData->pFile->pcwszFilePath);
        FPrintfU(v3, L"|       |.. pcwszMemberTag:           %s\r\n", pWintrustData->pFile->hFile);
        FPrintfU(v3, L"|       |.. pcwszMemberFilePath:      %s\r\n", pWintrustData->pFile->pgKnownSubject);
        FPrintfU(v3, L"|       |.. hMemberFile:              0x%p\r\n", *(_QWORD *)&pWintrustData->pFile[1].cbStruct);
        FPrintfU(v3, L"|       |.. pbCaclulatedFileHash:     ");
        v16 = pWintrustData->pFile;
        if ( SLODWORD(v16[1].hFile) > 0 )
        {
          v17 = 0;
          do
          {
            FPrintfU(v3, L"%02.2X", *((unsigned __int8 *)v16[1].pcwszFilePath + v17));
            v16 = pWintrustData->pFile;
            ++v17;
          }
          while ( v17 < SLODWORD(v16[1].hFile) );
        }
        FPrintfU(v3, L"\r\n");
        FPrintfU(v3, L"|       +-- cbCaclulatedFileHash:     %ld\r\n", LODWORD(pWintrustData->pFile[1].hFile));
      }
      else
      {
        FPrintfU(v3, L"|   +-- pCatalog: <<< bad parameter! >>>\r\n");
      }
      break;
    case 3u:
      v14 = pWintrustData->pFile;
      if ( v14 && v14->cbStruct >= 0x40 )
      {
        FPrintfU(v3, L"|   +-- pBlob:\r\n");
        FPrintfU(v3, L"|       |.. cbStruct:                 %ld\r\n", pWintrustData->pFile->cbStruct);
        v35[0] = 0;
        guid2wstr(&pWintrustData->pFile->cbStruct + 1, v35);
        FPrintfU(v3, L"        |.. gSubject:                 %s\r\n", v35);
        FPrintfU(v3, L"|       |.. pcwszDisplayName:         %s\r\n", pWintrustData->pFile->pgKnownSubject);
        FPrintfU(v3, L"|       |.. cbMemObject:              %ld\r\n", pWintrustData->pFile[1].cbStruct);
        FPrintfU(v3, L"|       |.. pbMemObject:              0x%p\r\n", pWintrustData->pFile[1].pcwszFilePath);
        FPrintfU(v3, L"|       |.. cbMemSignedMsg:           %ld\r\n", LODWORD(pWintrustData->pFile[1].hFile));
        FPrintfU(v3, L"|       +.. pbMemSignedMsg:           0x%p\r\n", pWintrustData->pFile[1].pgKnownSubject);
      }
      else
      {
        FPrintfU(v3, L"|   +-- pBlob: <<< bad parameter! >>>\r\n");
      }
      break;
    case 4u:
      v10 = pWintrustData->pFile;
      if ( v10 && v10->cbStruct >= 0x28 )
      {
        FPrintfU(v3, L"|   +-- pSgnr:\r\n");
        FPrintfU(v3, L"|       |.. cbStruct:                 %ld\r\n", pWintrustData->pFile->cbStruct);
        FPrintfU(v3, L"|       |.. pcwszDisplayName:         %s\r\n", pWintrustData->pFile->pcwszFilePath);
        FPrintfU(v3, L"|       |.. psSignerInfo:             0x%p\r\n", pWintrustData->pFile->hFile);
        FPrintfU(v3, L"|       |.. chStores:                 %ld\r\n", LODWORD(pWintrustData->pFile->pgKnownSubject));
        v11 = pWintrustData->pFile;
        if ( SLODWORD(v11->pgKnownSubject) > 0 )
        {
          v12 = 0;
          do
          {
            v13 = L"|       +.. pahStores[%02.2d]:        0x%p\r\n";
            if ( v12 != LODWORD(v11->pgKnownSubject) - 1 )
              v13 = L"|       |.. pahStores[%02.2d]:        0x%p\r\n";
            FPrintfU(v3, v13, v12, *(_QWORD *)(*(_QWORD *)&v11[1].cbStruct + 8LL * (int)v12));
            v11 = pWintrustData->pFile;
            ++v12;
          }
          while ( (signed int)v12 < SLODWORD(v11->pgKnownSubject) );
        }
      }
      else
      {
        FPrintfU(v3, L"|   +-- pSgnr: <<< bad parameter! >>>\r\n");
      }
      break;
    case 5u:
      v6 = pWintrustData->pFile;
      if ( v6 && v6->cbStruct >= 0x38 )
      {
        FPrintfU(v3, L"|   +-- pCert:\r\n");
        FPrintfU(v3, L"|       |.. cbStruct:                 %ld\r\n", pWintrustData->pFile->cbStruct);
        FPrintfU(v3, L"|       |.. pcwszDisplayName:         %s\r\n", pWintrustData->pFile->pcwszFilePath);
        FPrintfU(v3, L"|       |.. psCertContext:            0x%p\r\n", pWintrustData->pFile->hFile);
        FPrintfU(v3, L"|       |.. chStores:                 %ld\r\n", LODWORD(pWintrustData->pFile->pgKnownSubject));
        v7 = pWintrustData->pFile;
        if ( SLODWORD(v7->pgKnownSubject) > 0 )
        {
          v8 = 0;
          do
          {
            FPrintfU(
              v3,
              L"|       |.. pahStores[%02.2d]:        0x%p\r\n",
              v8,
              *(_QWORD *)(*(_QWORD *)&v7[1].cbStruct + 8LL * (int)v8));
            v7 = pWintrustData->pFile;
            ++v8;
          }
          while ( (signed int)v8 < SLODWORD(v7->pgKnownSubject) );
        }
        FPrintfU(v3, L"|       |.. dwFlags:                  0x%08.8lX\r\n", LODWORD(v7[1].pcwszFilePath));
        v36[0] = 0;
        v37[0] = 0;
        hFile = (struct _FILETIME *)pWintrustData->pFile[1].hFile;
        if ( hFile )
          GetStringDateTime(hFile, v36, v37);
        FPrintfU(v3, L"|       |-- psftVerifyAsOf:               %s - %s\r\n", v37, v36);
      }
      else
      {
        FPrintfU(v3, L"|   +-- pCert: <<< bad parameter! >>>\r\n");
      }
      break;
    default:
      FPrintfU(v3, L"|       +.. ***Unknown structure type***\r\n");
      break;
  }
  FPrintfU(v3, L"|.. WndParent:                        0x%p\r\n", a1->hWndParent);
  pgActionID = a1->pgActionID;
  v35[0] = 0;
  guid2wstr(pgActionID, v35);
  FPrintfU(v3, L"|.. pgActionID:                       %s\r\n", v35);
  FPrintfU(v3, L"|.. hProv:                            0x%Iu\r\n", a1->hProv);
  FPrintfU(v3, L"|.. dwError:                          0x%08.8lx\r\n", a1->dwError);
  FPrintfU(v3, L"|.. dwRegSecuritySettings:            0x%08.8lx\r\n", a1->dwRegSecuritySettings);
  FPrintfU(v3, L"|.. dwRegPolicySettings:              0x%08.8lx\r\n", a1->dwRegPolicySettings);
  FPrintfU(v3, L"|.. dwEncoding:                       0x%08.8lx\r\n", a1->dwEncoding);
  PrintfPFNs(v3, a1);
  FPrintfU(v3, L"|.. padwTrustStepErrors:\r\n");
  cdwTrustStepErrors = a1->cdwTrustStepErrors;
  if ( cdwTrustStepErrors > 0 )
  {
    for ( i = 0; i < cdwTrustStepErrors; ++i )
    {
      v24 = L"|   +.. Step[%02.2d]:                     0x%08.8lx\r\n";
      if ( i != cdwTrustStepErrors - 1 )
        v24 = L"|   |.. Step[%02.2d]:                     0x%08.8lx\r\n";
      FPrintfU(v3, v24, (unsigned int)i, a1->padwTrustStepErrors[i]);
      cdwTrustStepErrors = a1->cdwTrustStepErrors;
    }
  }
  FPrintfU(v3, L"|.. pahStores:\r\n");
  chStores = a1->chStores;
  if ( chStores > 0 )
  {
    for ( j = 0; j < chStores; ++j )
    {
      v27 = L"|   +.. Store[%02.2d]:                    0x%p\r\n";
      if ( j != chStores - 1 )
        v27 = L"|   |.. Store[%02.2d]:                    0x%p\r\n";
      FPrintfU(v3, v27, (unsigned int)j, a1->pahStores[j]);
      chStores = a1->chStores;
    }
  }
  FPrintfU(v3, L"|.. hMsg:                             0x%p\r\n", a1->hMsg);
  if ( a1->dwSubjectChoice == 1 )
  {
    p_gSubject = &a1->pPDSip->gSubject;
    v35[0] = 0;
    guid2wstr(p_gSubject, v35);
    FPrintfU(v3, L"|.. pPDSip:\r\n");
    FPrintfU(v3, L"|   |.. gSubject:                     %s\r\n", v35);
    FPrintfU(v3, L"|   |.. pSip:                         0x%p\r\n", a1->pPDSip->pSip);
    FPrintfU(v3, L"|   |.. pCATSip:                      0x%p\r\n", a1->pPDSip->pCATSip);
    FPrintfU(v3, L"|   |.. psSipSubjectInfo:             0x%p\r\n", a1->pPDSip->psSipSubjectInfo);
    FPrintfU(v3, L"|   |.. psSipCATSubjectInfo:          0x%p\r\n", a1->pPDSip->psSipCATSubjectInfo);
    FPrintfU(v3, L"|   +.. psIndirectData:               0x%p\r\n", a1->pPDSip->psIndirectData);
  }
  FPrintfU(v3, L"|.. csSigners:                        %lu\r\n", a1->csSigners);
  for ( k = 0; k < (signed int)a1->csSigners; ++k )
  {
    ProvSignerFromChain = WTHelperGetProvSignerFromChain(a1, k, 0, 0);
    PrintfSignerStruct(v3, ProvSignerFromChain, k, 0, 0);
    csCounterSigners = ProvSignerFromChain->csCounterSigners;
    if ( csCounterSigners )
    {
      v32 = 0;
      if ( csCounterSigners > 0 )
      {
        do
        {
          v33 = WTHelperGetProvSignerFromChain(a1, k, 1, v32);
          PrintfSignerStruct(v3, v33, k, 1, v32++);
        }
        while ( v32 < (signed int)ProvSignerFromChain->csCounterSigners );
      }
    }
  }
  FPrintfU(v3, L"|.. pszUsageOID:                      %p\r\n", a1->pszUsageOID);
  v34 = "TRUE";
  if ( !a1->fRecallWithState )
    v34 = "FALSE";
  FPrintfU(v3, L"|.. fRecallWithState:                 %hs\r\n", v34);
  GetStringDateTime(&a1->sftSystemTime, v36, v37);
  FPrintfU(v3, L"|.. sftSystemTime:                    %s - %s\r\n", v37, v36);
  FPrintfU(v3, L"+======================================================\r\n");
  CloseHandle(v3);
  return 0;
}

```

## disassembly

```asm
0x180046380  mov     [rsp-8+arg_8], rbx
0x180046385  mov     [rsp-8+arg_10], rsi
0x18004638a  push    rbp
0x18004638b  push    rdi
0x18004638c  push    r12
0x18004638e  push    r13
0x180046390  push    r15
0x180046392  lea     rbp, [rsp-150h]
0x18004639a  sub     rsp, 250h
0x1800463a1  mov     rax, cs:__security_cookie
0x1800463a8  xor     rax, rsp
0x1800463ab  mov     [rbp+170h+var_30], rax
0x1800463b2  mov     rsi, rcx
0x1800463b5  xor     r12d, r12d
0x1800463b8  mov     [rsp+270h+hTemplateFile], r12; hTemplateFile
0x1800463bd  lea     rcx, aCTrustpolTxt; "C:\\TRUSTPOL.TXT"
0x1800463c4  mov     [rsp+270h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800463cc  xor     r9d, r9d; lpSecurityAttributes
0x1800463cf  xor     r8d, r8d; dwShareMode
0x1800463d2  mov     [rsp+270h+dwCreationDisposition], 2; dwCreationDisposition
0x1800463da  mov     edx, 0C0000000h; dwDesiredAccess
0x1800463df  call    cs:__imp_CreateFileW
0x1800463e5  mov     rbx, rax
0x1800463e8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800463ec  jnz     short loc_1800463F6
0x1800463ee  lea     eax, [rbx+2]
0x1800463f1  jmp     loc_180046CA9
0x1800463f6  lea     rdx, aCryptProviderD; "CRYPT_PROVIDER_DATA:\r\n"
0x1800463fd  mov     rcx, rbx; void *
0x180046400  call    ?FPrintfU@@YAXPEAXPEBGZZ; FPrintfU(void *,ushort const *,...)
0x180046405  mov     rdi, [rsi+8]
0x180046409  lea     rdx, asc_180059050; "+======================================"...
0x180046410  mov     rcx, rbx; void *
0x180046413  call    ?FPrintfU@@YAXPEAXPEBGZZ; FPrintfU(void *,ushort const *,...)
0x180046418  lea     rdx, aPwintrustdata; "+-- pWintrustData:\r\n"
0x18004641f  mov     rcx, rbx; void *
0x180046422  call    ?FPrintfU@@YAXPEAXPEBGZZ; FPrintfU(void *,ushort const *,...)
0x180046427  mov     r8d, [rdi]
0x18004642a  lea     rdx, aCbstructLd_1; "|   |.. cbStruct:                     %"...
0x180046431  mov     rcx, rbx; void *
0x180046434  call    ?FPrintfU@@YAXPEAXPEBGZZ; FPrintfU(void *,ushort const *,...)
0x180046439  mov     r8, [rdi+8]
0x18004643d  lea     rdx, aPpolicycallbac; "|   |.. pPolicyCallbackData:          %"...
0x180046444  mov     rcx, rbx; void *
0x180046447  call    ?FPrintfU@@YAXPEAXPEBGZZ; FPrintfU(void *,ushort const *,...)
0x18004644c  mov     r8d, [rdi+18h]
0x180046450  lea     rdx, aDwuichoiceLd; "|   |.. dwUIChoice:                   %"...
0x180046457  mov     rcx, rbx; void *
0x18004645a  call    ?FPrintfU@@YAXPEAXPEBGZZ; FPrintfU(void *,ushort const *,...)
0x18004645f  mov     r8d, [rdi+1Ch]
0x180046463  lea     rdx, aFdrevocationch; "|   |.. fdRevocationChecks:           %"...
0x18004646a  mov     rcx, rbx; void *
0x18004646d  call    ?FPrintfU@@YAXPEAXPEBGZZ; FPrintfU(void *,ushort const *,...)
0x180046472  mov     r8d, [rdi+20h]
0x180046476  lea     rdx, aDwunionchoiceL; "|   |.. dwUnionChoice:                %"...
0x18004647d  mov     rcx, rbx; void *
0x180046480  call    ?FPrintfU@@YAXPEAXPEBGZZ; FPrintfU(void *,ushort const *,...)
0x180046485  mov     ecx, [rdi+20h]
0x180046488  sub     ecx, 1
0x18004648b  jz      loc_1800468C7
0x180046491  sub     ecx, 1
0x180046494  jz      loc_18004679E
0x18004649a  sub     ecx, 1
0x18004649d  jz      loc_1800466BB
0x1800464a3  sub     ecx, 1
0x1800464a6  jz      loc_1800465D9
0x1800464ac  cmp     ecx, 1
0x1800464af  jz      short loc_1800464BD
0x1800464b1  lea     rdx, aUnknownStructu; "|       +.. ***Unknown structure type**"...
0x1800464b8  jmp     loc_18004696F
0x1800464bd  mov     rax, [rdi+28h]
0x1800464c1  test    rax, rax
0x1800464c4  jz      loc_1800465CD
0x1800464ca  cmp     dword ptr [rax], 38h ; '8'
0x1800464cd  jb      loc_1800465CD
0x1800464d3  lea     rdx, aPcert; "|   +-- pCert:\r\n"
0x1800464da  mov     rcx, rbx; void *
0x1800464dd  call    ?FPrintfU@@YAXPEAXPEBGZZ; FPrintfU(void *,ushort const *,...)
0x1800464e2  mov     r8, [rdi+28h]
0x1800464e6  lea     rdx, aCbstructLd_0; "|       |.. cbStruct:                 %"...
0x1800464ed  mov     rcx, rbx; void *
0x1800464f0  mov     r8d, [r8]
0x1800464f3  call    ?FPrintfU@@YAXPEAXPEBGZZ; FPrintfU(void *,ushort const *,...)
0x1800464f8  mov     r8, [rdi+28h]
0x1800464fc  lea     rdx, aPcwszdisplayna; "|       |.. pcwszDisplayName:         %"...
0x180046503  mov     rcx, rbx; void *
0x180046506  mov     r8, [r8+8]
0x18004650a  call    ?FPrintfU@@YAXPEAXPEBGZZ; FPrintfU(void *,ushort const *,...)
0x18004650f  mov     r8, [rdi+28h]
0x180046513  lea     rdx, aPscertcontext0; "|       |.. psCertContext:            0"...
0x18004651a  mov     rcx, rbx; void *
0x18004651d  mov     r8, [r8+10h]
0x180046521  call    ?FPrintfU@@YAXPEAXPEBGZZ; FPrintfU(void *,ushort const *,...)
0x180046526  mov     r8, [rdi+28h]
0x18004652a  lea     rdx, aChstoresLd; "|       |.. chStores:                 %"...
0x180046531  mov     rcx, rbx; void *
0x180046534  mov     r8d, [r8+18h]
0x180046538  call    ?FPrintfU@@YAXPEAXPEBGZZ; FPrintfU(void *,ushort const *,...)
0x18004653d  mov     r8, [rdi+28h]
0x180046541  cmp     [r8+18h], r12d
0x180046545  jle     short loc_18004657A
0x180046547  mov     r15d, r12d
0x18004654a  lea     r12, aPahstores022d0_0; "|       |.. pahStores[%02.2d]:        0"...
0x180046551  mov     r9, [r8+20h]
0x180046555  mov     rdx, r12; unsigned __int16 *
0x180046558  movsxd  rax, r15d
0x18004655b  mov     r8d, r15d
0x18004655e  mov     rcx, rbx; void *
0x180046561  mov     r9, [r9+rax*8]
0x180046565  call    ?FPrintfU@@YAXPEAXPEBGZZ; FPrintfU(void *,ushort const *,...)
0x18004656a  mov     r8, [rdi+28h]
0x18004656e  inc     r15d
0x180046571  cmp     r15d, [r8+18h]
0x180046575  jl      short loc_180046551
0x180046577  xor     r12d, r12d
0x18004657a  mov     r8d, [r8+28h]
0x18004657e  lea     rdx, aDwflags0x088lx; "|       |.. dwFlags:                  0"...
0x180046585  mov     rcx, rbx; void *
0x180046588  call    ?FPrintfU@@YAXPEAXPEBGZZ; FPrintfU(void *,ushort const *,...)
0x18004658d  mov     [rbp+170h+var_1B0], r12w
0x180046592  mov     [rbp+170h+var_130], r12w
0x180046597  mov     rax, [rdi+28h]
0x18004659b  mov     rcx, [rax+30h]; struct _FILETIME *
0x18004659f  test    rcx, rcx
0x1800465a2  jz      short loc_1800465B1
0x1800465a4  lea     r8, [rbp+170h+var_130]; unsigned __int16 *
0x1800465a8  lea     rdx, [rbp+170h+var_1B0]; unsigned __int16 *
0x1800465ac  call    ?GetStringDateTime@@YAXPEAU_FILETIME@@PEAG1@Z; GetStringDateTime(_FILETIME *,ushort *,ushort *)
0x1800465b1  lea     r9, [rbp+170h+var_1B0]
0x1800465b5  mov     rcx, rbx; void *
0x1800465b8  lea     r8, [rbp+170h+var_130]
0x1800465bc  lea     rdx, aPsftverifyasof; "|       |-- psftVerifyAsOf:            "...
0x1800465c3  call    ?FPrintfU@@YAXPEAXPEBGZZ; FPrintfU(void *,ushort const *,...)
0x1800465c8  jmp     loc_180046977
0x1800465cd  lea     rdx, aPcertBadParame; "|   +-- pCert: <<< bad parameter! >>>\r"...
0x1800465d4  jmp     loc_18004696F
0x1800465d9  mov     rax, [rdi+28h]
0x1800465dd  test    rax, rax
0x1800465e0  jz      loc_1800466AF
0x1800465e6  cmp     dword ptr [rax], 28h ; '('
0x1800465e9  jb      loc_1800466AF
0x1800465ef  lea     rdx, aPsgnr; "|   +-- pSgnr:\r\n"
0x1800465f6  mov     rcx, rbx; void *
0x1800465f9  call    ?FPrintfU@@YAXPEAXPEBGZZ; FPrintfU(void *,ushort const *,...)
0x1800465fe  mov     r8, [rdi+28h]
0x180046602  lea     rdx, aCbstructLd_0; "|       |.. cbStruct:                 %"...
0x180046609  mov     rcx, rbx; void *
0x18004660c  mov     r8d, [r8]
0x18004660f  call    ?FPrintfU@@YAXPEAXPEBGZZ; FPrintfU(void *,ushort const *,...)
0x180046614  mov     r8, [rdi+28h]
0x180046618  lea     rdx, aPcwszdisplayna; "|       |.. pcwszDisplayName:         %"...
0x18004661f  mov     rcx, rbx; void *
0x180046622  mov     r8, [r8+8]
0x180046626  call    ?FPrintfU@@YAXPEAXPEBGZZ; FPrintfU(void *,ushort const *,...)
0x18004662b  mov     r8, [rdi+28h]
0x18004662f  lea     rdx, aPssignerinfo0x; "|       |.. psSignerInfo:             0"...
0x180046636  mov     rcx, rbx; void *
0x180046639  mov     r8, [r8+10h]
0x18004663d  call    ?FPrintfU@@YAXPEAXPEBGZZ; FPrintfU(void *,ushort const *,...)
0x180046642  mov     r8, [rdi+28h]
0x180046646  lea     rdx, aChstoresLd; "|       |.. chStores:                 %"...
0x18004664d  mov     rcx, rbx; void *
0x180046650  mov     r8d, [r8+18h]
0x180046654  call    ?FPrintfU@@YAXPEAXPEBGZZ; FPrintfU(void *,ushort const *,...)
0x180046659  mov     rax, [rdi+28h]
0x18004665d  cmp     [rax+18h], r12d
0x180046661  jle     loc_180046977
0x180046667  mov     r15d, r12d
0x18004666a  lea     r12, aPahstores022d0_0; "|       |.. pahStores[%02.2d]:        0"...
0x180046671  mov     r9, [rax+20h]
0x180046675  lea     rdx, aPahstores022d0; "|       +.. pahStores[%02.2d]:        0"...
0x18004667c  mov     eax, [rax+18h]
0x18004667f  mov     r8d, r15d
0x180046682  movsxd  rcx, r15d
0x180046685  dec     eax
0x180046687  cmp     r15d, eax
0x18004668a  cmovnz  rdx, r12; unsigned __int16 *
0x18004668e  mov     r9, [r9+rcx*8]
0x180046692  mov     rcx, rbx; void *
0x180046695  call    ?FPrintfU@@YAXPEAXPEBGZZ; FPrintfU(void *,ushort const *,...)
0x18004669a  mov     rax, [rdi+28h]
0x18004669e  inc     r15d
0x1800466a1  cmp     r15d, [rax+18h]
0x1800466a5  jl      short loc_180046671
0x1800466a7  xor     r12d, r12d
0x1800466aa  jmp     loc_180046977
0x1800466af  lea     rdx, aPsgnrBadParame; "|   +-- pSgnr: <<< bad parameter! >>>\r"...
0x1800466b6  jmp     loc_18004696F
0x1800466bb  mov     rax, [rdi+28h]
0x1800466bf  test    rax, rax
0x1800466c2  jz      loc_180046792
0x1800466c8  cmp     dword ptr [rax], 40h ; '@'
0x1800466cb  jb      loc_180046792
0x1800466d1  lea     rdx, aPblob; "|   +-- pBlob:\r\n"
0x1800466d8  mov     rcx, rbx; void *
0x1800466db  call    ?FPrintfU@@YAXPEAXPEBGZZ; FPrintfU(void *,ushort const *,...)
0x1800466e0  mov     r8, [rdi+28h]
0x1800466e4  lea     rdx, aCbstructLd_0; "|       |.. cbStruct:                 %"...
0x1800466eb  mov     rcx, rbx; void *
0x1800466ee  mov     r8d, [r8]
0x1800466f1  call    ?FPrintfU@@YAXPEAXPEBGZZ; FPrintfU(void *,ushort const *,...)
0x1800466f6  mov     [rsp+270h+var_230], r12w
0x1800466fc  lea     rdx, [rsp+270h+var_230]
0x180046701  mov     rcx, [rdi+28h]
0x180046705  add     rcx, 4
0x180046709  call    guid2wstr
0x18004670e  lea     r8, [rsp+270h+var_230]
0x180046713  mov     rcx, rbx; void *
0x180046716  lea     rdx, aGsubjectS_0; "        |.. gSubject:                 %"...
0x18004671d  call    ?FPrintfU@@YAXPEAXPEBGZZ; FPrintfU(void *,ushort const *,...)
0x180046722  mov     r8, [rdi+28h]
0x180046726  lea     rdx, aPcwszdisplayna; "|       |.. pcwszDisplayName:         %"...
0x18004672d  mov     rcx, rbx; void *
0x180046730  mov     r8, [r8+18h]
0x180046734  call    ?FPrintfU@@YAXPEAXPEBGZZ; FPrintfU(void *,ushort const *,...)
0x180046739  mov     r8, [rdi+28h]
0x18004673d  lea     rdx, aCbmemobjectLd; "|       |.. cbMemObject:              %"...
0x180046744  mov     rcx, rbx; void *
0x180046747  mov     r8d, [r8+20h]
0x18004674b  call    ?FPrintfU@@YAXPEAXPEBGZZ; FPrintfU(void *,ushort const *,...)
0x180046750  mov     r8, [rdi+28h]
0x180046754  lea     rdx, aPbmemobject0xP; "|       |.. pbMemObject:              0"...
0x18004675b  mov     rcx, rbx; void *
0x18004675e  mov     r8, [r8+28h]
0x180046762  call    ?FPrintfU@@YAXPEAXPEBGZZ; FPrintfU(void *,ushort const *,...)
0x180046767  mov     r8, [rdi+28h]
0x18004676b  lea     rdx, aCbmemsignedmsg; "|       |.. cbMemSignedMsg:           %"...
0x180046772  mov     rcx, rbx; void *
0x180046775  mov     r8d, [r8+30h]
0x180046779  call    ?FPrintfU@@YAXPEAXPEBGZZ; FPrintfU(void *,ushort const *,...)
0x18004677e  mov     r8, [rdi+28h]
0x180046782  lea     rdx, aPbmemsignedmsg; "|       +.. pbMemSignedMsg:           0"...
0x180046789  mov     r8, [r8+38h]
0x18004678d  jmp     loc_18004695E
0x180046792  lea     rdx, aPblobBadParame; "|   +-- pBlob: <<< bad parameter! >>>\r"...
0x180046799  jmp     loc_18004696F
0x18004679e  mov     rax, [rdi+28h]
0x1800467a2  test    rax, rax
0x1800467a5  jz      loc_1800468BB
0x1800467ab  cmp     dword ptr [rax], 28h ; '('
0x1800467ae  jb      loc_1800468BB
0x1800467b4  lea     rdx, aPcatalog; "|   +-- pCatalog:\r\n"
0x1800467bb  mov     rcx, rbx; void *
0x1800467be  call    ?FPrintfU@@YAXPEAXPEBGZZ; FPrintfU(void *,ushort const *,...)
0x1800467c3  mov     r8, [rdi+28h]
0x1800467c7  lea     rdx, aCbstructLd_0; "|       |.. cbStruct:                 %"...
0x1800467ce  mov     rcx, rbx; void *
0x1800467d1  mov     r8d, [r8]
0x1800467d4  call    ?FPrintfU@@YAXPEAXPEBGZZ; FPrintfU(void *,ushort const *,...)
0x1800467d9  mov     r8, [rdi+28h]
0x1800467dd  lea     rdx, aDwcatalogversi; "|       |.. dwCatalogVersion:         0"...
0x1800467e4  mov     rcx, rbx; void *
0x1800467e7  mov     r8d, [r8+4]
0x1800467eb  call    ?FPrintfU@@YAXPEAXPEBGZZ; FPrintfU(void *,ushort const *,...)
0x1800467f0  mov     r8, [rdi+28h]
0x1800467f4  lea     rdx, aPcwszcatalogfi; "|       |.. pcwszCatalogFilePath:     %"...
0x1800467fb  mov     rcx, rbx; void *
0x1800467fe  mov     r8, [r8+8]
0x180046802  call    ?FPrintfU@@YAXPEAXPEBGZZ; FPrintfU(void *,ushort const *,...)
0x180046807  mov     r8, [rdi+28h]
0x18004680b  lea     rdx, aPcwszmembertag; "|       |.. pcwszMemberTag:           %"...
0x180046812  mov     rcx, rbx; void *
0x180046815  mov     r8, [r8+10h]
0x180046819  call    ?FPrintfU@@YAXPEAXPEBGZZ; FPrintfU(void *,ushort const *,...)
0x18004681e  mov     r8, [rdi+28h]
0x180046822  lea     rdx, aPcwszmemberfil; "|       |.. pcwszMemberFilePath:      %"...
0x180046829  mov     rcx, rbx; void *
0x18004682c  mov     r8, [r8+18h]
0x180046830  call    ?FPrintfU@@YAXPEAXPEBGZZ; FPrintfU(void *,ushort const *,...)
0x180046835  mov     r8, [rdi+28h]
0x180046839  lea     rdx, aHmemberfile0xP; "|       |.. hMemberFile:              0"...
0x180046840  mov     rcx, rbx; void *
0x180046843  mov     r8, [r8+20h]
0x180046847  call    ?FPrintfU@@YAXPEAXPEBGZZ; FPrintfU(void *,ushort const *,...)
0x18004684c  lea     rdx, aPbcaclulatedfi; "|       |.. pbCaclulatedFileHash:     "
0x180046853  mov     rcx, rbx; void *
0x180046856  call    ?FPrintfU@@YAXPEAXPEBGZZ; FPrintfU(void *,ushort const *,...)
0x18004685b  mov     rax, [rdi+28h]
0x18004685f  cmp     [rax+30h], r12d
0x180046863  jle     short loc_180046890
0x180046865  mov     r15d, r12d
0x180046868  mov     rax, [rax+28h]
0x18004686c  lea     rdx, a022x; "%02.2X"
0x180046873  movsxd  rcx, r15d
0x180046876  movzx   r8d, byte ptr [rax+rcx]
0x18004687b  mov     rcx, rbx; void *
0x18004687e  call    ?FPrintfU@@YAXPEAXPEBGZZ; FPrintfU(void *,ushort const *,...)
0x180046883  mov     rax, [rdi+28h]
0x180046887  inc     r15d
0x18004688a  cmp     r15d, [rax+30h]
0x18004688e  jl      short loc_180046868
0x180046890  lea     rdx, asc_1800597A0; "\r\n"
0x180046897  mov     rcx, rbx; void *
0x18004689a  call    ?FPrintfU@@YAXPEAXPEBGZZ; FPrintfU(void *,ushort const *,...)
0x18004689f  mov     r8, [rdi+28h]
0x1800468a3  lea     rdx, aCbcaclulatedfi; "|       +-- cbCaclulatedFileHash:     %"...
0x1800468aa  mov     rcx, rbx; void *
0x1800468ad  mov     r8d, [r8+30h]
0x1800468b1  call    ?FPrintfU@@YAXPEAXPEBGZZ; FPrintfU(void *,ushort const *,...)
0x1800468b6  jmp     loc_180046977
  ... truncated ...
```
