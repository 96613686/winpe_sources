# CSecurityVerificationManager::CreateExternalBaseFromPESettings(ushort *,CExternalBase * *)

- ea: `0x180005710`
- end: `0x180005e81`
- name: `?CreateExternalBaseFromPESettings@CSecurityVerificationManager@@QEAAJPEAGPEAPEAVCExternalBase@@@Z`
- size: `1905`
- prototype: `__int64 __fastcall(CSecurityVerificationManager *this, unsigned __int16 *, struct CExternalBase **)`
- caller_count: `5`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180003f80`
- `0x180005308`
- `0x180008e88`
- `0x180019850`
- `0x180036adc`

## callees

- `0x180005710`
- `0x180006c50`
- `0x1800088b0`
- `0x180008e48`
- `0x18001a050`
- `0x1800202e8`
- `0x180029e74`
- `0x18002b1ac`
- `0x18003fc30`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000588d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005c0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005c91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005cfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005d1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000588d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005c0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005c91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005cfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005d1b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000584a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005855`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000584a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005855`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180005b2c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180005b2c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800057bf`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800057bf`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180005b51`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180005b51`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18000580e`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18000580e`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180005841`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180005841`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800057e9`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800057e9`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000595a`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000595a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005a19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005a19`
- `CRYPT32!CryptHashPublicKeyInfo` at `0x180005929`
- `CRYPT32!CryptHashPublicKeyInfo` at `0x180005929`
- `CRYPT32!CertFreeCertificateContext` at `0x180005a24`
- `CRYPT32!CertFreeCertificateContext` at `0x180005a24`
- `WINHTTP!WinHttpTimeFromSystemTime` at `0x180005b3a`
- `WINHTTP!WinHttpTimeFromSystemTime` at `0x180005b3a`
- `dbghelp!ImageNtHeader` at `0x180005823`
- `dbghelp!ImageNtHeader` at `0x180005823`

## pseudocode

```c
__int64 __fastcall CSecurityVerificationManager::CreateExternalBaseFromPESettings(
        CSecurityVerificationManager *this,
        unsigned __int16 *a2,
        struct CExternalBase **a3)
{
  BOOL v6; // r15d
  HANDLE FileW; // rax
  void *v8; // rbx
  HANDLE FileMappingW; // rax
  void *v10; // rdi
  void *v11; // rax
  const void *v12; // rbp
  PIMAGE_NT_HEADERS v13; // rax
  int v14; // esi
  CThirdPartyManager *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r9
  signed int v18; // eax
  int CertContext; // eax
  LPOLESTR v20; // rbx
  CExternalBase *v21; // r15
  __int64 v22; // rdi
  unsigned __int64 v23; // rdi
  unsigned __int64 v24; // rax
  _WORD *v25; // rax
  void *v26; // r14
  __int64 v27; // rcx
  _WORD *v28; // rdx
  _WORD *v29; // rcx
  _WORD *v30; // rbx
  void *v32; // rdi
  void *v33; // rcx
  CExternalBase *v34; // rbx
  CExternalBase *v35; // rbx
  unsigned int v36; // eax
  signed int LastError; // eax
  void *v38; // rcx
  __int64 v39; // rax
  signed int v40; // eax
  signed int v41; // eax
  DWORD pcbComputedHash; // [rsp+40h] [rbp-68h] BYREF
  LPOLESTR lpsz; // [rsp+48h] [rbp-60h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+50h] [rbp-58h] BYREF
  BYTE pbComputedHash[16]; // [rsp+58h] [rbp-50h] BYREF

  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_58c7d8ca840131a6c20521327163655c_Traceguids);
  if ( !a2 || !*a2 || !a3 )
    return 2147942487LL;
  v6 = 0;
  pCertContext = 0;
  *a3 = 0;
  FileW = CreateFileW(a2, 0x80000000, 1u, 0, 3u, 0x8000000u, 0);
  v8 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v14 = LastError;
    if ( LastError > 0 )
      v14 = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    FileMappingW = CreateFileMappingW(FileW, 0, 2u, 0, 0, 0);
    v10 = FileMappingW;
    if ( FileMappingW )
    {
      v11 = MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
      v12 = v11;
      if ( v11 )
      {
        v13 = ImageNtHeader(v11);
        if ( v13 )
        {
          v14 = 0;
          v6 = SLOBYTE(v13->OptionalHeader.DllCharacteristics) < 0;
        }
        else
        {
          v41 = GetLastError();
          v14 = v41;
          if ( v41 > 0 )
            v14 = (unsigned __int16)v41 | 0x80070000;
        }
        UnmapViewOfFile(v12);
      }
      else
      {
        v40 = GetLastError();
        v14 = v40;
        if ( v40 > 0 )
          v14 = (unsigned __int16)v40 | 0x80070000;
      }
      CloseHandle(v10);
    }
    else
    {
      v18 = GetLastError();
      v14 = v18;
      if ( v18 > 0 )
        v14 = (unsigned __int16)v18 | 0x80070000;
    }
    CloseHandle(v8);
  }
  if ( v14 >= 0 )
  {
    if ( !v6 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_58c7d8ca840131a6c20521327163655c_Traceguids);
        v15 = WPP_GLOBAL_Control;
      }
      v14 = -2146893049;
      goto LABEL_43;
    }
    CertContext = (**(__int64 (__fastcall ***)(CSecurityVerificationManager *, struct CExternalBase **))this)(this, a3);
    v14 = CertContext;
    if ( CertContext < 0 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_43;
      }
      v16 = 23;
      goto LABEL_68;
    }
    CertContext = GetCertContext(a2, &pCertContext);
    v14 = CertContext;
    if ( CertContext < 0 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_43;
      }
      v16 = 24;
      goto LABEL_68;
    }
    *(_OWORD *)pbComputedHash = 0;
    pcbComputedHash = 16;
    if ( !CryptHashPublicKeyInfo(
            0,
            0x8003u,
            0,
            1u,
            &pCertContext->pCertInfo->SubjectPublicKeyInfo,
            pbComputedHash,
            &pcbComputedHash)
      || ((*(void (__fastcall **)(CSecurityVerificationManager *, BYTE *))(*(_QWORD *)this + 8LL))(this, pbComputedHash),
          lpsz = 0,
          v14 = StringFromCLSID((const IID *const)pbComputedHash, &lpsz),
          v14 < 0) )
    {
LABEL_41:
      CertFreeCertificateContext(pCertContext);
      if ( v14 < 0 )
      {
LABEL_42:
        v15 = WPP_GLOBAL_Control;
        goto LABEL_43;
      }
      CertContext = CExternalBase::SetCallerPath(*a3, a2);
      v14 = CertContext;
      if ( CertContext >= 0 )
      {
        v34 = *a3;
        ExtractProductOwner(*((unsigned int *)*a3 + 20));
        *((_DWORD *)v34 + 20) &= 0xFFFFF0FF;
        *((_DWORD *)*a3 + 20) = *((_DWORD *)*a3 + 20) & 0xFFFFFF0F | 0x10;
        v35 = *a3;
        v36 = *((_DWORD *)*a3 + 20) & 0xF000;
        if ( v36 == 4096 || v36 == 0x2000 || !v36 || v36 == 20480 || v36 == 12288 || v36 == 0x4000 || v36 == 0x8000 )
        {
          *((_DWORD *)v35 + 20) &= 0xFFFF0FFF;
          if ( (v36 & 0xFFFFBFFF) != 0 )
          {
            *(_OWORD *)pbComputedHash = 0;
            v32 = operator new[](0x7Cu, (const struct std::nothrow_t *)&std::nothrow);
            if ( v32 )
            {
              GetSystemTime((LPSYSTEMTIME)pbComputedHash);
              if ( WinHttpTimeFromSystemTime((const SYSTEMTIME *)pbComputedHash, (LPWSTR)v32)
                && SystemTimeToFileTime((const SYSTEMTIME *)pbComputedHash, (LPFILETIME)v35 + 8) )
              {
                v33 = (void *)*((_QWORD *)v35 + 9);
                if ( v33 )
                  operator delete(v33);
                *((_QWORD *)v35 + 9) = v32;
              }
              else
              {
                GetLastError();
                operator delete(v32);
              }
            }
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_d8f56309d88e3febb8d819a47bcf5371_Traceguids, v36);
          }
          *((_DWORD *)v35 + 20) &= 0xFFFF0FFF;
        }
        goto LABEL_51;
      }
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_43;
      }
      v16 = 25;
LABEL_68:
      v17 = (unsigned int)CertContext;
      goto LABEL_69;
    }
    v20 = lpsz;
    v21 = *a3;
    if ( !lpsz )
    {
      v30 = 0;
      goto LABEL_83;
    }
    v22 = -1;
    do
      ++v22;
    while ( lpsz[v22] );
    v23 = v22 + 1;
    v24 = 2 * v23;
    if ( !is_mul_ok(v23, 2u) )
      v24 = -1;
    v25 = operator new[](v24, (const struct std::nothrow_t *)&std::nothrow);
    v26 = v25;
    if ( !v25 )
    {
      if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_bc50b57d3a7f3ca15f27abc6215da79e_Traceguids);
      }
      v14 = -2147024882;
      goto LABEL_40;
    }
    if ( v23 )
    {
      if ( v23 <= 0x7FFFFFFF )
      {
        v27 = 2147483646;
        v28 = v25;
        do
        {
          if ( !v27 )
            break;
          if ( !*v20 )
            break;
          *v28++ = *v20++;
          --v27;
          --v23;
        }
        while ( v23 );
        v29 = v28 - 1;
        v30 = v25;
        v14 = 0;
        if ( v23 )
          v29 = v28;
        *v29 = 0;
        goto LABEL_39;
      }
      v14 = -2147024809;
      *v25 = 0;
    }
    else
    {
      v14 = -2147024809;
    }
    v30 = 0;
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_bc50b57d3a7f3ca15f27abc6215da79e_Traceguids, 2147942487LL);
    }
    operator delete(v26);
LABEL_39:
    if ( v14 < 0 )
    {
LABEL_40:
      CoTaskMemFree(lpsz);
      goto LABEL_41;
    }
LABEL_83:
    v38 = (void *)*((_QWORD *)v21 + 1);
    if ( v38 )
      operator delete(v38);
    v39 = *(_QWORD *)v21;
    *((_QWORD *)v21 + 1) = v30;
    v14 = (*(__int64 (__fastcall **)(CExternalBase *))(v39 + 32))(v21);
    goto LABEL_40;
  }
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v16 = 22;
    v17 = (unsigned int)v14;
LABEL_69:
    WPP_SF_d(*((_QWORD *)v15 + 2), v16, WPP_58c7d8ca840131a6c20521327163655c_Traceguids, v17);
    goto LABEL_42;
  }
LABEL_43:
  if ( *a3 )
  {
    (**(void (__fastcall ***)(_QWORD, __int64))*a3)(*a3, 1);
    *a3 = 0;
LABEL_51:
    v15 = WPP_GLOBAL_Control;
  }
  if ( v15 != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)v15 + 2), 26, WPP_58c7d8ca840131a6c20521327163655c_Traceguids, (unsigned int)v14);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180005710  push    r12
0x180005712  push    r13
0x180005714  push    r14
0x180005716  sub     rsp, 90h
0x18000571d  mov     rax, cs:__security_cookie
0x180005724  xor     rax, rsp
0x180005727  mov     [rsp+0A8h+var_40], rax
0x18000572c  mov     r13, r8
0x18000572f  mov     r12, rdx
0x180005732  mov     r14, rcx
0x180005735  mov     rcx, cs:WPP_GLOBAL_Control
0x18000573c  lea     rax, WPP_GLOBAL_Control
0x180005743  cmp     rcx, rax
0x180005746  jnz     loc_180005A62
0x18000574c  mov     [rsp+0A8h+var_20], rbp
0x180005754  mov     [rsp+0A8h+var_28], rsi
0x18000575c  test    r12, r12
0x18000575f  jz      loc_180005A86
0x180005765  xor     ebp, ebp
0x180005767  cmp     bp, [r12]
0x18000576c  jz      loc_180005A86
0x180005772  test    r13, r13
0x180005775  jz      loc_180005A86
0x18000577b  mov     [rsp+0A8h+arg_18], rbx
0x180005783  xor     r9d, r9d; lpSecurityAttributes
0x180005786  mov     [rsp+0A8h+hTemplateFile], rbp; hTemplateFile
0x18000578b  mov     edx, 80000000h; dwDesiredAccess
0x180005790  mov     [rsp+0A8h+var_30], rdi
0x180005795  mov     r8d, 1; dwShareMode
0x18000579b  mov     [rsp+0A8h+var_38], r15
0x1800057a0  mov     rcx, r12; lpFileName
0x1800057a3  mov     [rsp+0A8h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x1800057ab  mov     r15d, ebp
0x1800057ae  mov     [rsp+0A8h+pCertContext], rbp
0x1800057b3  mov     [r13+0], rbp
0x1800057b7  mov     [rsp+0A8h+dwCreationDisposition], 3; dwCreationDisposition
0x1800057bf  call    cs:__imp_CreateFileW
0x1800057c5  mov     rbx, rax
0x1800057c8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800057cc  jz      loc_180005C0A
0x1800057d2  mov     qword ptr [rsp+0A8h+dwFlagsAndAttributes], rbp; lpName
0x1800057d7  xor     r9d, r9d; dwMaximumSizeHigh
0x1800057da  xor     edx, edx; lpFileMappingAttributes
0x1800057dc  mov     [rsp+0A8h+dwCreationDisposition], ebp; dwMaximumSizeLow
0x1800057e0  mov     r8d, 2; flProtect
0x1800057e6  mov     rcx, rax; hFile
0x1800057e9  call    cs:__imp_CreateFileMappingW
0x1800057ef  mov     rdi, rax
0x1800057f2  test    rax, rax
0x1800057f5  jz      loc_18000588D
0x1800057fb  xor     r9d, r9d; dwFileOffsetLow
0x1800057fe  mov     qword ptr [rsp+0A8h+dwCreationDisposition], rbp; dwNumberOfBytesToMap
0x180005803  xor     r8d, r8d; dwFileOffsetHigh
0x180005806  mov     edx, 4; dwDesiredAccess
0x18000580b  mov     rcx, rax; hFileMappingObject
0x18000580e  call    cs:__imp_MapViewOfFile
0x180005814  mov     rbp, rax
0x180005817  test    rax, rax
0x18000581a  jz      loc_180005CFD
0x180005820  mov     rcx, rax; Base
0x180005823  call    cs:__imp_ImageNtHeader
0x180005829  test    rax, rax
0x18000582c  jz      loc_180005D1B
0x180005832  xor     esi, esi
0x180005834  test    byte ptr [rax+5Eh], 80h
0x180005838  jnz     loc_180005D39
0x18000583e  mov     rcx, rbp; lpBaseAddress
0x180005841  call    cs:__imp_UnmapViewOfFile
0x180005847  mov     rcx, rdi; hObject
0x18000584a  call    cs:__imp_CloseHandle
0x180005850  xor     ebp, ebp
0x180005852  mov     rcx, rbx; hObject
0x180005855  call    cs:__imp_CloseHandle
0x18000585b  test    esi, esi
0x18000585d  jns     short loc_1800058A4
0x18000585f  mov     rcx, cs:WPP_GLOBAL_Control
0x180005866  lea     rdi, WPP_GLOBAL_Control
0x18000586d  cmp     rcx, rdi
0x180005870  jz      loc_180005A40
0x180005876  test    byte ptr [rcx+1Ch], 1
0x18000587a  jz      loc_180005A40
0x180005880  mov     edx, 16h
0x180005885  mov     r9d, esi
0x180005888  jmp     loc_180005BF5
0x18000588d  call    cs:__imp_GetLastError
0x180005893  mov     esi, eax
0x180005895  test    eax, eax
0x180005897  jle     short loc_180005852
0x180005899  movzx   esi, ax
0x18000589c  or      esi, 80070000h
0x1800058a2  jmp     short loc_180005852
0x1800058a4  test    r15d, r15d
0x1800058a7  jz      loc_180005D44
0x1800058ad  test    esi, esi
0x1800058af  js      short loc_18000585F
0x1800058b1  mov     rax, [r14]
0x1800058b4  mov     rdx, r13
0x1800058b7  mov     rcx, r14
0x1800058ba  mov     rax, [rax]
0x1800058bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058c2  mov     esi, eax
0x1800058c4  test    eax, eax
0x1800058c6  js      loc_180005D83
0x1800058cc  lea     rdx, [rsp+0A8h+pCertContext]; ppSigner
0x1800058d1  mov     rcx, r12; pvObject
0x1800058d4  call    ?GetCertContext@@YAJPEBGPEAPEBU_CERT_CONTEXT@@@Z; GetCertContext(ushort const *,_CERT_CONTEXT const * *)
0x1800058d9  mov     esi, eax
0x1800058db  test    eax, eax
0x1800058dd  js      loc_180005BCC
0x1800058e3  mov     rax, [rsp+0A8h+pCertContext]
0x1800058e8  xorps   xmm0, xmm0
0x1800058eb  movups  xmmword ptr [rsp+0A8h+pbComputedHash], xmm0
0x1800058f0  mov     [rsp+0A8h+pcbComputedHash], 10h
0x1800058f8  mov     r9d, 1; dwCertEncodingType
0x1800058fe  xor     r8d, r8d; dwFlags
0x180005901  mov     edx, 8003h; Algid
0x180005906  mov     rcx, [rax+18h]
0x18000590a  lea     rax, [rsp+0A8h+pcbComputedHash]
0x18000590f  mov     [rsp+0A8h+hTemplateFile], rax; pcbComputedHash
0x180005914  add     rcx, 60h ; '`'
0x180005918  lea     rax, [rsp+0A8h+pbComputedHash]
0x18000591d  mov     qword ptr [rsp+0A8h+dwFlagsAndAttributes], rax; pbComputedHash
0x180005922  mov     qword ptr [rsp+0A8h+dwCreationDisposition], rcx; pInfo
0x180005927  xor     ecx, ecx; hCryptProv
0x180005929  call    cs:__imp_CryptHashPublicKeyInfo
0x18000592f  test    eax, eax
0x180005931  jz      loc_180005A1F
0x180005937  mov     rax, [r14]
0x18000593a  lea     rdx, [rsp+0A8h+pbComputedHash]
0x18000593f  mov     rcx, r14
0x180005942  mov     rax, [rax+8]
0x180005946  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000594b  lea     rdx, [rsp+0A8h+lpsz]; lplpsz
0x180005950  mov     [rsp+0A8h+lpsz], rbp
0x180005955  lea     rcx, [rsp+0A8h+pbComputedHash]; rclsid
0x18000595a  call    cs:__imp_StringFromCLSID
0x180005960  mov     esi, eax
0x180005962  test    eax, eax
0x180005964  js      loc_180005A1F
0x18000596a  mov     rbx, [rsp+0A8h+lpsz]
0x18000596f  mov     r15, [r13+0]
0x180005973  test    rbx, rbx
0x180005976  jz      loc_180005DAE
0x18000597c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180005983  mov     rdi, rcx
0x180005986  inc     rdi
0x180005989  cmp     word ptr [rbx+rdi*2], 0
0x18000598e  jnz     short loc_180005986
0x180005990  inc     rdi
0x180005993  mov     eax, 2
0x180005998  mul     rdi
0x18000599b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800059a2  cmovb   rax, rcx
0x1800059a6  mov     rcx, rax; unsigned __int64
0x1800059a9  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800059ae  mov     r14, rax
0x1800059b1  test    rax, rax
0x1800059b4  jz      loc_180005CAB
0x1800059ba  test    rdi, rdi
0x1800059bd  jz      loc_180005DBD
0x1800059c3  cmp     rdi, 7FFFFFFFh
0x1800059ca  ja      loc_180005DB6
0x1800059d0  mov     ecx, 7FFFFFFEh
0x1800059d5  mov     rdx, rax
0x1800059d8  test    rcx, rcx
0x1800059db  jz      short loc_1800059F9
0x1800059dd  movzx   eax, word ptr [rbx]
0x1800059e0  test    ax, ax
0x1800059e3  jz      short loc_1800059F9
0x1800059e5  mov     [rdx], ax
0x1800059e8  add     rbx, 2
0x1800059ec  add     rdx, 2
0x1800059f0  dec     rcx
0x1800059f3  sub     rdi, 1
0x1800059f7  jnz     short loc_1800059D8
0x1800059f9  test    rdi, rdi
0x1800059fc  lea     rcx, [rdx-2]
0x180005a00  mov     rbx, r14
0x180005a03  mov     esi, ebp
0x180005a05  cmovnz  rcx, rdx
0x180005a09  mov     [rcx], bp
0x180005a0c  test    esi, esi
0x180005a0e  jns     loc_180005CD6
0x180005a14  mov     rcx, [rsp+0A8h+lpsz]; pv
0x180005a19  call    cs:__imp_CoTaskMemFree
0x180005a1f  mov     rcx, [rsp+0A8h+pCertContext]; pCertContext
0x180005a24  call    cs:__imp_CertFreeCertificateContext
0x180005a2a  test    esi, esi
0x180005a2c  jns     loc_180005B75
0x180005a32  lea     rdi, WPP_GLOBAL_Control
0x180005a39  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a40  mov     r8, [r13+0]
0x180005a44  test    r8, r8
0x180005a47  jz      short loc_180005AB8
0x180005a49  mov     rax, [r8]
0x180005a4c  mov     edx, 1
0x180005a51  mov     rcx, r8
0x180005a54  mov     rax, [rax]
0x180005a57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a5c  mov     [r13+0], rbp
0x180005a60  jmp     short loc_180005AB1
0x180005a62  test    byte ptr [rcx+1Ch], 8
0x180005a66  jz      loc_18000574C
0x180005a6c  mov     rcx, [rcx+10h]
0x180005a70  lea     r8, WPP_58c7d8ca840131a6c20521327163655c_Traceguids
0x180005a77  mov     edx, 14h
0x180005a7c  call    WPP_SF_
0x180005a81  jmp     loc_18000574C
0x180005a86  mov     eax, 80070057h
0x180005a8b  jmp     short loc_180005ADB
0x180005a8d  cmp     eax, 2000h
0x180005a92  jz      short loc_180005A9C
0x180005a94  test    eax, eax
0x180005a96  jnz     loc_180005C28
0x180005a9c  and     dword ptr [rbx+50h], 0FFFF0FFFh
0x180005aa3  test    eax, 0FFFFBFFFh
0x180005aa8  jnz     short loc_180005B06
0x180005aaa  lea     rdi, WPP_GLOBAL_Control
0x180005ab1  mov     rcx, cs:WPP_GLOBAL_Control
0x180005ab8  mov     r15, [rsp+0A8h+var_38]
0x180005abd  cmp     rcx, rdi
0x180005ac0  mov     rdi, [rsp+0A8h+var_30]
0x180005ac5  mov     rbx, [rsp+0A8h+arg_18]
0x180005acd  jz      short loc_180005AD9
0x180005acf  test    byte ptr [rcx+1Ch], 8
0x180005ad3  jnz     loc_180005E64
0x180005ad9  mov     eax, esi
0x180005adb  mov     rsi, [rsp+0A8h+var_28]
0x180005ae3  mov     rbp, [rsp+0A8h+var_20]
0x180005aeb  mov     rcx, [rsp+0A8h+var_40]
0x180005af0  xor     rcx, rsp; StackCookie
0x180005af3  call    __security_check_cookie
0x180005af8  add     rsp, 90h
0x180005aff  pop     r14
0x180005b01  pop     r13
0x180005b03  pop     r12
0x180005b05  retn
0x180005b06  xorps   xmm0, xmm0
0x180005b09  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180005b10  mov     ecx, 7Ch ; '|'; unsigned __int64
0x180005b15  movups  xmmword ptr [rsp+0A8h+pbComputedHash], xmm0
0x180005b1a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180005b1f  mov     rdi, rax
0x180005b22  test    rax, rax
0x180005b25  jz      short loc_180005AAA
0x180005b27  lea     rcx, [rsp+0A8h+pbComputedHash]; lpSystemTime
0x180005b2c  call    cs:__imp_GetSystemTime
0x180005b32  mov     rdx, rdi; pwszTime
0x180005b35  lea     rcx, [rsp+0A8h+pbComputedHash]; pst
0x180005b3a  call    cs:__imp_WinHttpTimeFromSystemTime
0x180005b40  test    eax, eax
0x180005b42  jz      loc_180005C91
0x180005b48  lea     rdx, [rbx+40h]; lpFileTime
0x180005b4c  lea     rcx, [rsp+0A8h+pbComputedHash]; lpSystemTime
0x180005b51  call    cs:__imp_SystemTimeToFileTime
0x180005b57  test    eax, eax
0x180005b59  jz      loc_180005C91
0x180005b5f  mov     rcx, [rbx+48h]; Block
0x180005b63  test    rcx, rcx
0x180005b66  jnz     loc_180005CCC
0x180005b6c  mov     [rbx+48h], rdi
0x180005b70  jmp     loc_180005AAA
0x180005b75  mov     rcx, [r13+0]; this
0x180005b79  mov     rdx, r12; unsigned __int16 *
0x180005b7c  call    ?SetCallerPath@CExternalBase@@QEAAJPEBG@Z; CExternalBase::SetCallerPath(ushort const *)
0x180005b81  mov     esi, eax
0x180005b83  test    eax, eax
0x180005b85  js      loc_180005E39
0x180005b8b  mov     rbx, [r13+0]
0x180005b8f  mov     ecx, [rbx+50h]
0x180005b92  call    ?ExtractProductOwner@@YA?AW4ProductOwner@@K@Z; ExtractProductOwner(ulong)
0x180005b97  and     dword ptr [rbx+50h], 0FFFFF0FFh
0x180005b9e  mov     rcx, [r13+0]
0x180005ba2  mov     eax, [rcx+50h]
0x180005ba5  and     eax, 0FFFFFF1Fh
0x180005baa  or      eax, 10h
0x180005bad  mov     [rcx+50h], eax
0x180005bb0  mov     rbx, [r13+0]
0x180005bb4  mov     eax, [rbx+50h]
0x180005bb7  and     eax, 0F000h
0x180005bbc  cmp     eax, 1000h
0x180005bc1  jnz     loc_180005A8D
0x180005bc7  jmp     loc_180005A9C
0x180005bcc  mov     rcx, cs:WPP_GLOBAL_Control
0x180005bd3  lea     rdi, WPP_GLOBAL_Control
0x180005bda  cmp     rcx, rdi
0x180005bdd  jz      loc_180005A40
0x180005be3  test    byte ptr [rcx+1Ch], 1
0x180005be7  jz      loc_180005A40
0x180005bed  mov     edx, 18h
0x180005bf2  mov     r9d, eax
0x180005bf5  mov     rcx, [rcx+10h]
0x180005bf9  lea     r8, WPP_58c7d8ca840131a6c20521327163655c_Traceguids
0x180005c00  call    WPP_SF_d
0x180005c05  jmp     loc_180005A39
0x180005c0a  call    cs:__imp_GetLastError
0x180005c10  mov     esi, eax
0x180005c12  test    eax, eax
0x180005c14  jle     loc_18000585B
0x180005c1a  movzx   esi, ax
  ... truncated ...
```
