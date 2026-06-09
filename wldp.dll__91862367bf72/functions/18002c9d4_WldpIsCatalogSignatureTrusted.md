# WldpIsCatalogSignatureTrusted

- ea: `0x18002c9d4`
- end: `0x18002d029`
- name: `WldpIsCatalogSignatureTrusted`
- size: `1621`
- prototype: `__int64 __fastcall(__int64, __int64, char, __int64, __int64, _QWORD *, _DWORD *, _BYTE *, _DWORD *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180018518`
- `0x18001e6b8`

## callees

- `0x180018260`
- `0x180019e74`
- `0x18001bb98`
- `0x180021ec0`
- `0x180022a10`
- `0x18002c05c`
- `0x18002c0e4`
- `0x18002c9d4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002cb8f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002cfe9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002cb8f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002cfe9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cb23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cf32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cf5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cb23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cf32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cf5d`
- `WINTRUST!WinVerifyTrust` at `0x18002ce0f`
- `WINTRUST!WinVerifyTrust` at `0x18002ce0f`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle3` at `0x18002cb59`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle3` at `0x18002cbbb`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle3` at `0x18002cb59`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle3` at `0x18002cbbb`
- `WINTRUST!CryptCATAdminAcquireContext2` at `0x18002cb19`
- `WINTRUST!CryptCATAdminAcquireContext2` at `0x18002cb19`
- `WINTRUST!WTConfigCiFreePrivateData` at `0x18002cff7`
- `WINTRUST!WTConfigCiFreePrivateData` at `0x18002cff7`
- `WINTRUST!CryptCATAdminEnumCatalogFromHash` at `0x18002cd52`
- `WINTRUST!CryptCATAdminEnumCatalogFromHash` at `0x18002cd52`
- `WINTRUST!WTIsFirstConfigCiResultPreferred` at `0x18002cec4`
- `WINTRUST!WTIsFirstConfigCiResultPreferred` at `0x18002cec4`
- `WINTRUST!CryptCATCatalogInfoFromContext` at `0x18002cd71`
- `WINTRUST!CryptCATCatalogInfoFromContext` at `0x18002cd71`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x18002cfd5`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x18002cfd5`
- `WINTRUST!CryptCATAdminReleaseCatalogContext` at `0x18002cf52`
- `WINTRUST!CryptCATAdminReleaseCatalogContext` at `0x18002cf52`

## pseudocode

```c
__int64 __fastcall WldpIsCatalogSignatureTrusted(
        __int64 a1,
        __int64 a2,
        char a3,
        __int64 a4,
        __int64 a5,
        _QWORD *a6,
        _DWORD *a7,
        _BYTE *a8,
        _DWORD *a9)
{
  char v9; // bl
  BYTE *v11; // rsi
  GUID *v12; // rax
  signed int v13; // eax
  char *v14; // rbx
  __int64 unique_hlocal; // rax
  HLOCAL v16; // rcx
  __int64 v17; // r14
  unsigned __int64 v18; // r12
  unsigned __int64 v19; // r15
  CATALOG_INFO *p_psCatInfo; // rax
  int *v21; // rcx
  __int64 v22; // rdx
  HCATINFO v23; // rax
  void *v24; // r13
  signed int LastError; // eax
  signed int v26; // eax
  _DWORD *v27; // rax
  char v29; // [rsp+31h] [rbp-CFh] BYREF
  char v30; // [rsp+32h] [rbp-CEh]
  DWORD cbHash; // [rsp+34h] [rbp-CCh] BYREF
  HCATADMIN hCatAdmin; // [rsp+38h] [rbp-C8h] BYREF
  HLOCAL hMem; // [rsp+40h] [rbp-C0h] BYREF
  HCATINFO phPrevCatInfo; // [rsp+48h] [rbp-B8h] BYREF
  _DWORD *v35; // [rsp+50h] [rbp-B0h]
  _BYTE *v36; // [rsp+58h] [rbp-A8h]
  BYTE *pbHash; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD *v38; // [rsp+68h] [rbp-98h]
  _OWORD v39[3]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v40; // [rsp+A0h] [rbp-60h]
  __int128 v41; // [rsp+B0h] [rbp-50h]
  __int64 v42; // [rsp+C0h] [rbp-40h]
  __int64 v43; // [rsp+C8h] [rbp-38h]
  __int64 v44; // [rsp+D0h] [rbp-30h]
  GUID *pgActionID; // [rsp+D8h] [rbp-28h]
  __int64 v46; // [rsp+E0h] [rbp-20h]
  __int64 v47; // [rsp+E8h] [rbp-18h]
  __int128 v48; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v49; // [rsp+100h] [rbp+0h]
  __int128 v50; // [rsp+110h] [rbp+10h]
  __int128 v51; // [rsp+120h] [rbp+20h]
  __int64 v52; // [rsp+130h] [rbp+30h]
  __int128 pWVTData; // [rsp+140h] [rbp+40h] BYREF
  __int128 v54; // [rsp+150h] [rbp+50h]
  __int128 v55; // [rsp+160h] [rbp+60h]
  __int128 v56; // [rsp+170h] [rbp+70h] BYREF
  __int128 v57; // [rsp+180h] [rbp+80h]
  __int64 v58; // [rsp+190h] [rbp+90h]
  __int128 v59; // [rsp+1A0h] [rbp+A0h]
  int v60; // [rsp+1B0h] [rbp+B0h] BYREF
  __int16 v61; // [rsp+1B4h] [rbp+B4h]
  _BYTE v62[522]; // [rsp+1B6h] [rbp+B6h] BYREF
  __int128 v63; // [rsp+3C0h] [rbp+2C0h] BYREF
  __m128i v64; // [rsp+3D0h] [rbp+2D0h]
  __m128i v65; // [rsp+3E0h] [rbp+2E0h]
  _DWORD v66[60]; // [rsp+3F0h] [rbp+2F0h] BYREF
  CATALOG_INFO psCatInfo; // [rsp+4E0h] [rbp+3E0h] BYREF

  v46 = a4;
  v9 = a3;
  v30 = a3;
  v43 = a2;
  v44 = a1;
  v47 = a5;
  v38 = a6;
  v35 = a7;
  v36 = a8;
  memset_0(&psCatInfo, 0, sizeof(psCatInfo));
  cbHash = 0;
  memset_0(&pWVTData, 0, 0x58u);
  phPrevCatInfo = 0;
  hCatAdmin = 0;
  memset_0(&v48, 0, 0x48u);
  v63 = 0;
  v64 = 0;
  v65 = 0;
  memset(v39, 0, sizeof(v39));
  memset_0(v66, 0, 0xE8u);
  v66[0] = 232;
  v11 = 0;
  pbHash = 0;
  v59 = 0;
  v12 = (GUID *)&stru_180047D90;
  if ( !v9 )
    v12 = (GUID *)&::pgActionID;
  pgActionID = v12;
  if ( !(unsigned int)CryptCATAdminAcquireContext2(&hCatAdmin, 0, 0, 0, 0)
    || !(unsigned int)CryptCATAdminCalcHashFromFileHandle3(hCatAdmin, a1, &cbHash, 0, 1) )
  {
    goto LABEL_4;
  }
  unique_hlocal = wil::make_unique_hlocal_nothrow<unsigned char [0]>(&hMem, cbHash);
  wistd::unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::operator=(
    &pbHash,
    unique_hlocal);
  v16 = hMem;
  hMem = 0;
  if ( v16 )
    LocalFree(v16);
  v11 = pbHash;
  if ( !pbHash )
  {
    LODWORD(v14) = -2147024882;
    goto LABEL_39;
  }
  if ( (unsigned int)CryptCATAdminCalcHashFromFileHandle3(hCatAdmin, a1, &cbHash, pbHash, 1) )
  {
    v17 = 0;
    phPrevCatInfo = 0;
    hMem = (HLOCAL)*((_QWORD *)&v39[2] + 1);
    LOBYTE(v18) = BYTE12(v59);
    LODWORD(v19) = DWORD1(v59);
    while ( 1 )
    {
      memset_0(v39, 0, 0x48u);
      v48 = v39[0];
      v49 = v39[1];
      v50 = v39[2];
      v51 = v40;
      v52 = v41;
      memset_0(v39, 0, 0x58u);
      pWVTData = v39[0];
      v54 = v39[1];
      v55 = v39[2];
      v56 = v40;
      v57 = v41;
      v58 = v42;
      v60 = 524;
      v61 = 0;
      memset_0(v62, 0, 0x206u);
      p_psCatInfo = &psCatInfo;
      v21 = &v60;
      v22 = 4;
      do
      {
        *(_OWORD *)&p_psCatInfo->cbStruct = *(_OWORD *)v21;
        *(_OWORD *)&p_psCatInfo->wszCatalogFile[6] = *((_OWORD *)v21 + 1);
        *(_OWORD *)&p_psCatInfo->wszCatalogFile[14] = *((_OWORD *)v21 + 2);
        *(_OWORD *)&p_psCatInfo->wszCatalogFile[22] = *((_OWORD *)v21 + 3);
        *(_OWORD *)&p_psCatInfo->wszCatalogFile[30] = *((_OWORD *)v21 + 4);
        *(_OWORD *)&p_psCatInfo->wszCatalogFile[38] = *((_OWORD *)v21 + 5);
        *(_OWORD *)&p_psCatInfo->wszCatalogFile[46] = *((_OWORD *)v21 + 6);
        *(_OWORD *)&p_psCatInfo->wszCatalogFile[54] = *((_OWORD *)v21 + 7);
        p_psCatInfo = (CATALOG_INFO *)((char *)p_psCatInfo + 128);
        v21 += 32;
        --v22;
      }
      while ( v22 );
      *(_OWORD *)&p_psCatInfo[-1].wszCatalogFile[258] = *(_OWORD *)(v21 - 1);
      *(_QWORD *)&v39[0] = 48;
      memset((char *)v39 + 8, 0, 40);
      v63 = v39[0];
      v64 = (__m128i)v39[1];
      v65 = 0u;
      v23 = CryptCATAdminEnumCatalogFromHash(hCatAdmin, v11, cbHash, 0, &phPrevCatInfo);
      v24 = v23;
      if ( !v23 )
        break;
      if ( !CryptCATCatalogInfoFromContext(v23, &psCatInfo, 0) )
      {
        LastError = GetLastError();
        LODWORD(v14) = LastError;
        if ( LastError > 0 )
          LODWORD(v14) = (unsigned __int16)LastError | 0x80070000;
LABEL_31:
        CryptCATAdminReleaseCatalogContext(hCatAdmin, v24, 0);
        goto LABEL_39;
      }
      LODWORD(v48) = 72;
      *((_QWORD *)&v48 + 1) = psCatInfo.wszCatalogFile;
      *(_QWORD *)&v49 = 0;
      *((_QWORD *)&v49 + 1) = v43;
      *(_QWORD *)&v50 = v44;
      *((_QWORD *)&v50 + 1) = v11;
      LODWORD(v51) = cbHash;
      LODWORD(pWVTData) = 88;
      *((_QWORD *)&v54 + 1) = 0x100000002LL;
      LODWORD(v55) = 2;
      *((_QWORD *)&v55 + 1) = &v48;
      LODWORD(v56) = 1;
      DWORD2(v57) = 4224;
      if ( v9 )
      {
        *((_QWORD *)&pWVTData + 1) = &v63;
        v65.m128i_i64[1] = (__int64)v66;
      }
      v14 = (char *)(unsigned int)WinVerifyTrust(HWND_MESSAGE|0x2LL, pgActionID, &pWVTData);
      if ( !(unsigned __int8)IsWvtErrorRecoverable(v14) )
        goto LABEL_31;
      std::vector_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd::integral_constant_unsigned___int64_0__void___void___0_std::nullptr_t______std::allocator_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd::integral_constant_unsigned___int64_0__void___void___0_std::nullptr_t_________::emplace_back_void___(
        v46,
        (char *)&v56 + 8);
      if ( v47 )
        std::vector_wil::unique_struct_CONFIG_CI_PROV_INFO_RESULT2_PRIVATE__void____cdecl___CONFIG_CI_PROV_INFO_RESULT2_PRIVATE______WTConfigCiFreePrivateData_void____cdecl___CONFIG_CI_PROV_INFO_RESULT2_PRIVATE_____noexcept__NewProviderData__std::allocator_wil::unique_struct_CONFIG_CI_PROV_INFO_RESULT2_PRIVATE__void____cdecl___CONFIG_CI_PROV_INFO_RESULT2_PRIVATE______WTConfigCiFreePrivateData_void____cdecl___CONFIG_CI_PROV_INFO_RESULT2_PRIVATE_____noexcept__NewProviderData_____::emplace_back_wil::unique_struct_CONFIG_CI_PROV_INFO_RESULT2_PRIVATE__void____cdecl___CONFIG_CI_PROV_INFO_RESULT2_PRIVATE______WTConfigCiFreePrivateData_void____cdecl___CONFIG_CI_PROV_INFO_RESULT2_PRIVATE_____noexcept__NewProviderData___(
          v47,
          v66);
      v9 = v30;
      if ( v30 )
      {
        if ( v17 )
        {
          v29 = 0;
          WTIsFirstConfigCiResultPreferred(v65.m128i_i64[1], hMem, &v29);
          if ( v29 )
          {
            LODWORD(v19) = v64.m128i_i32[1];
            LOBYTE(v18) = v64.m128i_i8[12];
          }
          else
          {
            *v38 = v17;
          }
        }
        else
        {
          v39[0] = v63;
          v39[1] = v64;
          v19 = HIDWORD(v64.m128i_i64[0]);
          v18 = HIDWORD(_mm_srli_si128(v64, 8).m128i_u64[0]);
          hMem = (HLOCAL)_mm_srli_si128(v65, 8).m128i_u64[0];
        }
        ++v17;
      }
      phPrevCatInfo = v24;
    }
    v26 = GetLastError();
    LODWORD(v14) = v26;
    if ( v26 > 0 )
      LODWORD(v14) = (unsigned __int16)v26 | 0x80070000;
    if ( (_DWORD)v14 == -2147023728 )
    {
      LODWORD(v14) = 0;
      v27 = v35;
      if ( v30 )
      {
        *v35 = v19;
        *v36 = v18;
      }
      else
      {
        *a9 = -566945214;
        a9[1] = 298880601;
        a9[2] = -1073723508;
        a9[3] = -292175281;
        *v27 = 2;
        *v36 = 0;
      }
    }
  }
  else
  {
LABEL_4:
    v13 = GetLastError();
    LODWORD(v14) = v13;
    if ( v13 > 0 )
      LODWORD(v14) = (unsigned __int16)v13 | 0x80070000;
  }
LABEL_39:
  if ( hCatAdmin )
    CryptCATAdminReleaseContext(hCatAdmin, 0);
  pbHash = 0;
  if ( v11 )
    LocalFree(v11);
  WTConfigCiFreePrivateData(v66);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18002c9d4  mov     [rsp-8+arg_10], rbx
0x18002c9d9  push    rbp
0x18002c9da  push    rsi
0x18002c9db  push    rdi
0x18002c9dc  push    r12
0x18002c9de  push    r13
0x18002c9e0  push    r14
0x18002c9e2  push    r15
0x18002c9e4  lea     rbp, [rsp-600h]
0x18002c9ec  sub     rsp, 700h
0x18002c9f3  mov     rax, cs:__security_cookie
0x18002c9fa  xor     rax, rsp
0x18002c9fd  mov     [rbp+630h+var_40], rax
0x18002ca04  mov     [rbp+630h+var_650], r9
0x18002ca08  mov     bl, r8b
0x18002ca0b  mov     [rsp+730h+var_6FE], bl
0x18002ca0f  mov     [rbp+630h+var_668], rdx
0x18002ca13  mov     r14, rcx
0x18002ca16  mov     [rbp+630h+var_660], rcx
0x18002ca1a  mov     rdi, [rbp+630h+arg_40]
0x18002ca21  mov     rax, [rbp+630h+arg_20]
0x18002ca28  mov     [rbp+630h+var_648], rax
0x18002ca2c  mov     rax, [rbp+630h+arg_28]
0x18002ca33  mov     [rsp+730h+var_6C8], rax
0x18002ca38  mov     rax, [rbp+630h+arg_30]
0x18002ca3f  mov     [rsp+730h+var_6E0], rax
0x18002ca44  mov     rax, [rbp+630h+arg_38]
0x18002ca4b  mov     [rsp+730h+var_6D8], rax
0x18002ca50  xor     edx, edx; Val
0x18002ca52  mov     r8d, 20Ch; Size
0x18002ca58  lea     rcx, [rbp+630h+psCatInfo]; void *
0x18002ca5f  call    memset_0
0x18002ca64  xor     r13d, r13d
0x18002ca67  mov     [rsp+730h+cbHash], r13d
0x18002ca6c  mov     [rsp+730h+var_700], r13b
0x18002ca71  xor     edx, edx; Val
0x18002ca73  lea     r8d, [r13+58h]; Size
0x18002ca77  lea     rcx, [rbp+630h+pWVTData]; void *
0x18002ca7b  call    memset_0
0x18002ca80  mov     [rsp+730h+var_6E8], r13
0x18002ca85  mov     [rsp+730h+hCatAdmin], r13
0x18002ca8a  xor     edx, edx; Val
0x18002ca8c  lea     r8d, [r13+48h]; Size
0x18002ca90  lea     rcx, [rbp+630h+var_640]; void *
0x18002ca94  call    memset_0
0x18002ca99  xorps   xmm0, xmm0
0x18002ca9c  movups  [rbp+630h+var_370], xmm0
0x18002caa3  movups  [rbp+630h+var_360], xmm0
0x18002caaa  movups  [rbp+630h+var_350], xmm0
0x18002cab1  xorps   xmm1, xmm1
0x18002cab4  movups  [rsp+730h+var_6C0], xmm1
0x18002cab9  movups  [rbp+630h+var_6B0], xmm1
0x18002cabd  movups  [rbp+630h+var_6A0], xmm1
0x18002cac1  mov     esi, 0E8h
0x18002cac6  mov     r8d, esi; Size
0x18002cac9  xor     edx, edx; Val
0x18002cacb  lea     rcx, [rbp+630h+var_340]; void *
0x18002cad2  call    memset_0
0x18002cad7  mov     [rbp+630h+var_340], esi
0x18002cadd  mov     esi, r13d
0x18002cae0  mov     [rsp+730h+pbHash], r13
0x18002cae5  xorps   xmm0, xmm0
0x18002cae8  movups  [rbp+630h+var_590], xmm0
0x18002caef  lea     rcx, pgActionID
0x18002caf6  lea     rax, stru_180047D90
0x18002cafd  test    bl, bl
0x18002caff  cmovz   rax, rcx
0x18002cb03  mov     [rbp+630h+pgActionID], rax
0x18002cb07  mov     dword ptr [rsp+730h+phPrevCatInfo], r13d
0x18002cb0c  xor     r9d, r9d
0x18002cb0f  xor     r8d, r8d
0x18002cb12  xor     edx, edx
0x18002cb14  lea     rcx, [rsp+730h+hCatAdmin]
0x18002cb19  call    cs:__imp_CryptCATAdminAcquireContext2
0x18002cb1f  test    eax, eax
0x18002cb21  jnz     short loc_18002CB41
0x18002cb23  call    cs:__imp_GetLastError
0x18002cb29  mov     ebx, eax
0x18002cb2b  test    eax, eax
0x18002cb2d  jle     loc_18002CFC9
0x18002cb33  movzx   ebx, ax
0x18002cb36  or      ebx, 80070000h
0x18002cb3c  jmp     loc_18002CFC9
0x18002cb41  mov     dword ptr [rsp+730h+phPrevCatInfo], 1
0x18002cb49  xor     r9d, r9d
0x18002cb4c  lea     r8, [rsp+730h+cbHash]
0x18002cb51  mov     rdx, r14
0x18002cb54  mov     rcx, [rsp+730h+hCatAdmin]
0x18002cb59  call    cs:__imp_CryptCATAdminCalcHashFromFileHandle3
0x18002cb5f  test    eax, eax
0x18002cb61  jz      short loc_18002CB23
0x18002cb63  mov     edx, [rsp+730h+cbHash]
0x18002cb67  lea     rcx, [rsp+730h+hMem]
0x18002cb6c  call    ??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)
0x18002cb71  nop
0x18002cb72  mov     rdx, rax
0x18002cb75  lea     rcx, [rsp+730h+pbHash]
0x18002cb7a  call    ??4?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::operator=(wistd::unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>> &&)
0x18002cb7f  nop
0x18002cb80  mov     rcx, [rsp+730h+hMem]; hMem
0x18002cb85  mov     [rsp+730h+hMem], r13
0x18002cb8a  test    rcx, rcx
0x18002cb8d  jz      short loc_18002CB95
0x18002cb8f  call    cs:__imp_LocalFree
0x18002cb95  mov     rsi, [rsp+730h+pbHash]
0x18002cb9a  test    rsi, rsi
0x18002cb9d  jz      loc_18002CFC4
0x18002cba3  mov     dword ptr [rsp+730h+phPrevCatInfo], 1
0x18002cbab  mov     r9, rsi
0x18002cbae  lea     r8, [rsp+730h+cbHash]
0x18002cbb3  mov     rdx, r14
0x18002cbb6  mov     rcx, [rsp+730h+hCatAdmin]
0x18002cbbb  call    cs:__imp_CryptCATAdminCalcHashFromFileHandle3
0x18002cbc1  test    eax, eax
0x18002cbc3  jz      loc_18002CB23
0x18002cbc9  mov     r14, r13
0x18002cbcc  mov     [rsp+730h+var_6E8], r13
0x18002cbd1  mov     rax, qword ptr [rbp+630h+var_6A0+8]
0x18002cbd5  mov     [rsp+730h+hMem], rax
0x18002cbda  mov     r12b, byte ptr [rbp+630h+var_590+0Ch]
0x18002cbe1  mov     r15d, dword ptr [rbp+630h+var_590+4]
0x18002cbe8  xor     edx, edx; Val
0x18002cbea  lea     r8d, [rdx+48h]; Size
0x18002cbee  lea     rcx, [rsp+730h+var_6C0]; void *
0x18002cbf3  call    memset_0
0x18002cbf8  movups  xmm0, [rsp+730h+var_6C0]
0x18002cbfd  movaps  [rbp+630h+var_640], xmm0
0x18002cc01  movups  xmm1, [rbp+630h+var_6B0]
0x18002cc05  movaps  [rbp+630h+var_630], xmm1
0x18002cc09  movups  xmm0, [rbp+630h+var_6A0]
0x18002cc0d  movaps  [rbp+630h+var_620], xmm0
0x18002cc11  movups  xmm1, [rbp+630h+var_690]
0x18002cc15  movaps  [rbp+630h+var_610], xmm1
0x18002cc19  movsd   xmm0, qword ptr [rbp+630h+var_680]
0x18002cc1e  movsd   [rbp+630h+var_600], xmm0
0x18002cc23  xor     edx, edx; Val
0x18002cc25  lea     r8d, [rdx+58h]; Size
0x18002cc29  lea     rcx, [rsp+730h+var_6C0]; void *
0x18002cc2e  call    memset_0
0x18002cc33  movups  xmm0, [rsp+730h+var_6C0]
0x18002cc38  movaps  [rbp+630h+pWVTData], xmm0
0x18002cc3c  movups  xmm1, [rbp+630h+var_6B0]
0x18002cc40  movaps  [rbp+630h+var_5E0], xmm1
0x18002cc44  movups  xmm0, [rbp+630h+var_6A0]
0x18002cc48  movaps  [rbp+630h+var_5D0], xmm0
0x18002cc4c  movups  xmm1, [rbp+630h+var_690]
0x18002cc50  movaps  [rbp+630h+var_5C0], xmm1
0x18002cc54  movups  xmm0, [rbp+630h+var_680]
0x18002cc58  movaps  [rbp+630h+var_5B0], xmm0
0x18002cc5f  movsd   xmm1, [rbp+630h+var_670]
0x18002cc64  movsd   [rbp+630h+var_5A0], xmm1
0x18002cc6c  mov     [rbp+630h+var_580], 20Ch
0x18002cc76  mov     [rbp+630h+var_57C], r13w
0x18002cc7e  xor     edx, edx; Val
0x18002cc80  mov     r8d, 206h; Size
0x18002cc86  lea     rcx, [rbp+630h+var_57A]; void *
0x18002cc8d  call    memset_0
0x18002cc92  lea     rax, [rbp+630h+psCatInfo]
0x18002cc99  lea     rcx, [rbp+630h+var_580]
0x18002cca0  mov     edx, 4
0x18002cca5  lea     r8d, [rdx+7Ch]
0x18002cca9  movups  xmm0, xmmword ptr [rcx]
0x18002ccac  movups  xmmword ptr [rax], xmm0
0x18002ccaf  movups  xmm1, xmmword ptr [rcx+10h]
0x18002ccb3  movups  xmmword ptr [rax+10h], xmm1
0x18002ccb7  movups  xmm0, xmmword ptr [rcx+20h]
0x18002ccbb  movups  xmmword ptr [rax+20h], xmm0
0x18002ccbf  movups  xmm1, xmmword ptr [rcx+30h]
0x18002ccc3  movups  xmmword ptr [rax+30h], xmm1
0x18002ccc7  movups  xmm0, xmmword ptr [rcx+40h]
0x18002cccb  movups  xmmword ptr [rax+40h], xmm0
0x18002cccf  movups  xmm1, xmmword ptr [rcx+50h]
0x18002ccd3  movups  xmmword ptr [rax+50h], xmm1
0x18002ccd7  movups  xmm0, xmmword ptr [rcx+60h]
0x18002ccdb  movups  xmmword ptr [rax+60h], xmm0
0x18002ccdf  movups  xmm1, xmmword ptr [rcx+70h]
0x18002cce3  movups  xmmword ptr [rax+70h], xmm1
0x18002cce7  add     rax, r8
0x18002ccea  add     rcx, r8
0x18002cced  sub     rdx, 1
0x18002ccf1  jnz     short loc_18002CCA9
0x18002ccf3  movups  xmm0, xmmword ptr [rcx-4]
0x18002ccf7  movups  xmmword ptr [rax-4], xmm0
0x18002ccfb  mov     qword ptr [rsp+730h+var_6C0], 30h ; '0'
0x18002cd04  xorps   xmm0, xmm0
0x18002cd07  xor     eax, eax
0x18002cd09  movups  [rsp+730h+var_6C0+8], xmm0
0x18002cd0e  movups  [rbp+630h+var_6B0+8], xmm0
0x18002cd12  mov     qword ptr [rbp+630h+var_6A0+8], rax
0x18002cd16  movups  xmm0, [rsp+730h+var_6C0]
0x18002cd1b  movups  [rbp+630h+var_370], xmm0
0x18002cd22  movups  xmm1, [rbp+630h+var_6B0]
0x18002cd26  movups  [rbp+630h+var_360], xmm1
0x18002cd2d  movups  xmm0, [rbp+630h+var_6A0]
0x18002cd31  movups  [rbp+630h+var_350], xmm0
0x18002cd38  lea     rax, [rsp+730h+var_6E8]
0x18002cd3d  mov     [rsp+730h+phPrevCatInfo], rax; phPrevCatInfo
0x18002cd42  xor     r9d, r9d; dwFlags
0x18002cd45  mov     r8d, [rsp+730h+cbHash]; cbHash
0x18002cd4a  mov     rdx, rsi; pbHash
0x18002cd4d  mov     rcx, [rsp+730h+hCatAdmin]; hCatAdmin
0x18002cd52  call    cs:__imp_CryptCATAdminEnumCatalogFromHash
0x18002cd58  mov     r13, rax
0x18002cd5b  test    rax, rax
0x18002cd5e  jz      loc_18002CF5D
0x18002cd64  xor     r8d, r8d; dwFlags
0x18002cd67  lea     rdx, [rbp+630h+psCatInfo]; psCatInfo
0x18002cd6e  mov     rcx, rax; hCatInfo
0x18002cd71  call    cs:__imp_CryptCATCatalogInfoFromContext
0x18002cd77  test    eax, eax
0x18002cd79  jz      loc_18002CF32
0x18002cd7f  mov     dword ptr [rbp+630h+var_640], 48h ; 'H'
0x18002cd86  lea     rax, [rbp+630h+psCatInfo.wszCatalogFile]
0x18002cd8d  mov     qword ptr [rbp+630h+var_640+8], rax
0x18002cd91  mov     qword ptr [rbp+630h+var_630], 0
0x18002cd99  mov     rax, [rbp+630h+var_668]
0x18002cd9d  mov     qword ptr [rbp+630h+var_630+8], rax
0x18002cda1  mov     rax, [rbp+630h+var_660]
0x18002cda5  mov     qword ptr [rbp+630h+var_620], rax
0x18002cda9  mov     qword ptr [rbp+630h+var_620+8], rsi
0x18002cdad  mov     eax, [rsp+730h+cbHash]
0x18002cdb1  mov     dword ptr [rbp+630h+var_610], eax
0x18002cdb4  mov     dword ptr [rbp+630h+pWVTData], 58h ; 'X'
0x18002cdbb  mov     eax, 2
0x18002cdc0  mov     dword ptr [rbp+630h+var_5E0+8], eax
0x18002cdc3  mov     dword ptr [rbp+630h+var_5D0], eax
0x18002cdc6  lea     rax, [rbp+630h+var_640]
0x18002cdca  mov     qword ptr [rbp+630h+var_5D0+8], rax
0x18002cdce  mov     dword ptr [rbp+630h+var_5C0], 1
0x18002cdd5  mov     dword ptr [rbp+630h+var_5E0+0Ch], 1
0x18002cddc  mov     dword ptr [rbp+630h+var_5B0+8], 1080h
0x18002cde6  test    bl, bl
0x18002cde8  jz      short loc_18002CE03
0x18002cdea  lea     rax, [rbp+630h+var_370]
0x18002cdf1  mov     qword ptr [rbp+630h+pWVTData+8], rax
0x18002cdf5  lea     rax, [rbp+630h+var_340]
0x18002cdfc  mov     qword ptr [rbp+630h+var_350+8], rax
0x18002ce03  lea     r8, [rbp+630h+pWVTData]; pWVTData
0x18002ce07  mov     rdx, [rbp+630h+pgActionID]; pgActionID
0x18002ce0b  or      rcx, 0FFFFFFFFFFFFFFFFh; hwnd
0x18002ce0f  call    cs:__imp_WinVerifyTrust
0x18002ce15  mov     ebx, eax
0x18002ce17  lea     rdx, [rsp+730h+var_700]
0x18002ce1c  mov     ecx, eax
0x18002ce1e  call    IsWvtErrorRecoverable
0x18002ce23  test    al, al
0x18002ce25  jz      loc_18002CF47
0x18002ce2b  lea     rdx, [rbp+630h+var_5C0+8]
0x18002ce2f  mov     rcx, [rbp+630h+var_650]
0x18002ce33  call    std__vector_wil__unique_any_t_wil__details__unique_storage_wil__details__resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd__integral_constant_unsigned___int64_0__void___void___0_std__nullptr_t______std__allocator_wil__unique_any_t_wil__details__unique_storage_wil__details__resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd__integral_constant_unsigned___int64_0__void___void___0_std__nullptr_t___________emplace_back_void___
0x18002ce38  mov     rax, [rbp+630h+var_648]
0x18002ce3c  test    rax, rax
0x18002ce3f  jz      short loc_18002CE50
0x18002ce41  lea     rdx, [rbp+630h+var_340]
0x18002ce48  mov     rcx, rax
0x18002ce4b  call    std__vector_wil__unique_struct_CONFIG_CI_PROV_INFO_RESULT2_PRIVATE__void____cdecl___CONFIG_CI_PROV_INFO_RESULT2_PRIVATE______WTConfigCiFreePrivateData_void____cdecl___CONFIG_CI_PROV_INFO_RESULT2_PRIVATE_____noexcept__NewProviderData__std__allocator_wil__unique_struct_CONFIG_CI_PROV_INFO_RESULT2_PRIVATE__void____cdecl___CONFIG_CI_PROV_INFO_RESULT2_PRIVATE______WTConfigCiFreePrivateData_void____cdecl___CONFIG_CI_PROV_INFO_RESULT2_PRIVATE_____noexcept__NewProviderData_______emplace_back_wil__unique_struct_CONFIG_CI_PROV_INFO_RESULT2_PRIVATE__void____cdecl___CONFIG_CI_PROV_INFO_RESULT2_PRIVATE______WTConfigCiFreePrivateData_void____cdecl___CONFIG_CI_PROV_INFO_RESULT2_PRIVATE_____noexcept__NewProviderData___
0x18002ce50  cmp     [rsp+730h+var_700], 0
0x18002ce55  jnz     loc_18002CEF9
0x18002ce5b  mov     bl, [rsp+730h+var_6FE]
0x18002ce5f  test    bl, bl
0x18002ce61  jz      loc_18002CEEC
0x18002ce67  test    r14, r14
0x18002ce6a  jnz     short loc_18002CEAE
0x18002ce6c  movups  xmm0, [rbp+630h+var_370]
0x18002ce73  movups  [rsp+730h+var_6C0], xmm0
0x18002ce78  movups  xmm1, [rbp+630h+var_360]
0x18002ce7f  movups  [rbp+630h+var_6B0], xmm1
0x18002ce83  movups  xmm0, [rbp+630h+var_350]
0x18002ce8a  movq    r15, xmm1
0x18002ce8f  shr     r15, 20h
0x18002ce93  psrldq  xmm1, 8
0x18002ce98  movq    r12, xmm1
0x18002ce9d  shr     r12, 20h
0x18002cea1  psrldq  xmm0, 8
0x18002cea6  movq    [rsp+730h+hMem], xmm0
0x18002ceac  jmp     short loc_18002CEE9
0x18002ceae  mov     [rsp+730h+var_6FF], 0
0x18002ceb3  lea     r8, [rsp+730h+var_6FF]
0x18002ceb8  mov     rdx, [rsp+730h+hMem]
0x18002cebd  mov     rcx, qword ptr [rbp+630h+var_350+8]
0x18002cec4  call    cs:__imp_WTIsFirstConfigCiResultPreferred
0x18002ceca  cmp     [rsp+730h+var_6FF], 0
0x18002cecf  jz      short loc_18002CEE1
0x18002ced1  mov     r15d, dword ptr [rbp+630h+var_360+4]
0x18002ced8  mov     r12b, byte ptr [rbp+630h+var_360+0Ch]
0x18002cedf  jmp     short loc_18002CEE9
0x18002cee1  mov     rax, [rsp+730h+var_6C8]
0x18002cee6  mov     [rax], r14
0x18002cee9  inc     r14
0x18002ceec  mov     [rsp+730h+var_6E8], r13
0x18002cef1  xor     r13d, r13d
0x18002cef4  jmp     loc_18002CBE8
0x18002cef9  xor     ebx, ebx
0x18002cefb  mov     dword ptr [rdi], 0DE351A42h
0x18002cf01  mov     dword ptr [rdi+4], 11D08E59h
0x18002cf08  mov     dword ptr [rdi+8], 0C000478Ch
0x18002cf0f  mov     dword ptr [rdi+0Ch], 0EE95C24Fh
0x18002cf16  mov     rax, [rsp+730h+var_6E0]
0x18002cf1b  mov     dword ptr [rax], 1
0x18002cf21  mov     rax, [rsp+730h+var_6D8]
  ... truncated ...
```
