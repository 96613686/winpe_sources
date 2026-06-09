# SLActivateProduct

- ea: `0x180031920`
- end: `0x18003213a`
- name: `SLActivateProduct`
- size: `2074`
- prototype: `HRESULT __stdcall(HSLC hSLC, const SLID *pProductSkuId, UINT cbAppSpecificData, const PVOID pvAppSpecificData, const SL_ACTIVATION_INFO_HEADER *pActivationInfo, PCWSTR pwszProxyServer, WORD wProxyPort)`
- caller_count: `0`
- callee_count: `33`
- tags: `service_task, installer_update`

## callees

- `0x180002144`
- `0x1800021a8`
- `0x180002264`
- `0x180004564`
- `0x180004ca0`
- `0x180004d28`
- `0x180004dd0`
- `0x180006c10`
- `0x180007638`
- `0x1800077b0`
- `0x180014c18`
- `0x180024278`
- `0x180024dac`
- `0x180025ad4`
- `0x180025d80`
- `0x180026ba8`
- `0x1800270e0`
- `0x180027a3c`
- `0x180028030`
- `0x18002f1a4`
- `0x1800305dc`
- `0x180031920`
- `0x180042514`
- `0x1800427f4`
- `0x180042acc`
- `0x180042db0`
- `0x180043088`
- `0x180043364`
- `0x18004362c`
- `0x180043900`
- `0x180043bd8`
- `0x180043eac`
- `0x18006ef16`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18003199b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18003199b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180031b00`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180031b00`
- `sppc!SLGetApplicationInformation` at `0x180031ee1`
- `sppc!SLGetApplicationInformation` at `0x180031ee1`
- `sppc!SLpIsCurrentInstalledProductKeyDefaultKey` at `0x180031f71`
- `sppc!SLpIsCurrentInstalledProductKeyDefaultKey` at `0x180031f71`
- `sppc!SLpIAActivateProduct` at `0x180031cdd`
- `sppc!SLpIAActivateProduct` at `0x180031cdd`
- `sppc!SLpVLActivateProduct` at `0x180031c7b`
- `sppc!SLpVLActivateProduct` at `0x180031c7b`
- `sppc!SLGetSLIDList` at `0x180031b63`
- `sppc!SLGetSLIDList` at `0x180031b63`
- `sppc!SLSetGenuineInformation` at `0x180031aee`
- `sppc!SLSetGenuineInformation` at `0x180031b20`
- `sppc!SLSetGenuineInformation` at `0x18003206d`
- `sppc!SLSetGenuineInformation` at `0x180031aee`
- `sppc!SLSetGenuineInformation` at `0x180031b20`
- `sppc!SLSetGenuineInformation` at `0x18003206d`
- `sppc!SLGetProductSkuInformation` at `0x180031d66`
- `sppc!SLGetProductSkuInformation` at `0x1800320b8`
- `sppc!SLGetProductSkuInformation` at `0x180031d66`
- `sppc!SLGetProductSkuInformation` at `0x1800320b8`

## string_xrefs

- `0x180031ed5`: `IsKeyManagementService`
- `0x180031ae0`: `SL_LAST_ACT_ATTEMPT_HRESULT`
- `0x180031b16`: `SL_LAST_ACT_ATTEMPT_TIME`
- `0x18003205a`: `SL_LAST_ACT_ATTEMPT_SERVER_FLAGS`

## pseudocode

```c
HRESULT __stdcall SLActivateProduct(
        HSLC hSLC,
        const SLID *pProductSkuId,
        UINT cbAppSpecificData,
        const PVOID pvAppSpecificData,
        const SL_ACTIVATION_INFO_HEADER *pActivationInfo,
        PCWSTR pwszProxyServer,
        WORD wProxyPort)
{
  int v9; // ecx
  int v10; // r13d
  int v11; // esi
  int v12; // r12d
  HRESULT v13; // edi
  const SL_ACTIVATION_INFO_HEADER *v14; // rbx
  int v15; // eax
  __int64 v16; // rcx
  HRESULT v17; // ebx
  SLID *v18; // rdx
  __int64 v19; // rdx
  int v20; // ecx
  int v21; // r8d
  int v22; // r9d
  HRESULT v23; // eax
  __int64 v24; // rcx
  PBYTE v25; // rcx
  int v26; // eax
  __int64 v27; // rcx
  HRESULT v28; // eax
  unsigned int v29; // ebx
  int v30; // ecx
  int v31; // r8d
  int v32; // r9d
  HRESULT v33; // eax
  int v34; // ecx
  int v35; // r8d
  int v36; // r9d
  int IsCurrentInstalledProductKeyDefaultKey; // eax
  int v39; // [rsp+30h] [rbp-D0h] BYREF
  UINT pnReturnIds; // [rsp+34h] [rbp-CCh] BYREF
  HRESULT v41; // [rsp+38h] [rbp-C8h] BYREF
  int v42; // [rsp+3Ch] [rbp-C4h] BYREF
  UINT pcbValue; // [rsp+40h] [rbp-C0h] BYREF
  HRESULT v44; // [rsp+44h] [rbp-BCh] BYREF
  SLID *pApplicationId; // [rsp+48h] [rbp-B8h] BYREF
  int v46; // [rsp+50h] [rbp-B0h] BYREF
  int v47; // [rsp+54h] [rbp-ACh] BYREF
  PBYTE v48; // [rsp+58h] [rbp-A8h] BYREF
  PBYTE ppbValue; // [rsp+60h] [rbp-A0h] BYREF
  SLDATATYPE peDataType; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int128 v51; // [rsp+70h] [rbp-90h]
  __int128 v52; // [rsp+80h] [rbp-80h] BYREF
  BYTE v53[16]; // [rsp+90h] [rbp-70h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v55[2]; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v56; // [rsp+B8h] [rbp-48h]
  __int128 v57; // [rsp+C8h] [rbp-38h]
  __int64 v58; // [rsp+D8h] [rbp-28h]
  __int128 Buf2; // [rsp+E0h] [rbp-20h] BYREF
  _OWORD Buf1[5]; // [rsp+F0h] [rbp-10h] BYREF
  int pbValue; // [rsp+150h] [rbp+50h] BYREF

  v41 = 0;
  v44 = 0;
  v42 = 0;
  v46 = 0;
  pnReturnIds = 0;
  pApplicationId = 0;
  peDataType = SL_DATA_NONE;
  pcbValue = 0;
  v48 = 0;
  ppbValue = 0;
  Buf1[0] = 0;
  SystemTimeAsFileTime = 0;
  Buf2 = 0;
  pbValue = 0;
  v55[0] = 0;
  v56 = 0;
  v39 = 0;
  v57 = 0;
  v58 = 0xFFFFFFFFLL;
  v55[1] = GetTickCount64();
  if ( (int)sub_180027A3C(&v39) >= 0 )
  {
    v9 = v58;
    if ( v39 )
      v9 = 0;
    LODWORD(v58) = v9;
  }
  sub_180006C10(0);
  v39 = 0;
  v47 = 0;
  v10 = 0;
  v11 = 0;
  v12 = 0;
  v51 = 0;
  v52 = 0;
  *(_OWORD *)v53 = 0;
  if ( !hSLC || !pProductSkuId )
  {
    v13 = -2147024809;
    sub_180004CA0(2147942487LL);
LABEL_7:
    pbValue = -2147024809;
    goto LABEL_19;
  }
  v14 = pActivationInfo;
  LOWORD(v52) = wProxyPort;
  v51 = __PAIR128__((unsigned __int64)pwszProxyServer, (unsigned __int64)pActivationInfo);
  sub_180004564((char *)&v52 + 8);
  *(_DWORD *)&v53[8] = 0;
  *(_QWORD *)v53 = v55;
  if ( v14 )
  {
    if ( v14->cbSize < 8 )
    {
      v13 = -2147024809;
      sub_180004CA0(2147942487LL);
      pbValue = -2147024809;
      sub_180043BD8(qword_180081260, &dword_18008DBC4);
      goto LABEL_19;
    }
    if ( v14->type != SL_ACTIVATION_TYPE_ACTIVE_DIRECTORY )
    {
      v13 = -2147024809;
      sub_180004CA0(2147942487LL);
      sub_180043088(&dword_180082844, byte_18008D320);
      goto LABEL_7;
    }
    v15 = sub_180014C18(hSLC, (SLID *)pProductSkuId);
    goto LABEL_15;
  }
  v17 = SLGetSLIDList(hSLC, SL_ID_PRODUCT_SKU, pProductSkuId, SL_ID_APPLICATION, &pnReturnIds, &pApplicationId);
  if ( v17 < 0 )
    pnReturnIds = 0;
  v13 = sub_1800270E0(hSLC, (SLID *)pProductSkuId);
  if ( v13 < 0 )
    sub_180004564((char *)&v52 + 8);
  v18 = (SLID *)&xmmword_180073828;
  if ( pnReturnIds )
    v18 = pApplicationId;
  sub_1800077B0(v55, v18, pProductSkuId, *((_QWORD *)&v52 + 1), 0);
  if ( v13 < 0 )
  {
LABEL_30:
    v16 = (unsigned int)v13;
    goto LABEL_17;
  }
  LOBYTE(v19) = 1;
  sub_18002F1A4(qword_18008F2E8, v19);
  v15 = sub_180004D28(*((_QWORD *)&v52 + 1), L"PGS:TB", &v46);
  v13 = v15;
  if ( v15 < 0 )
    goto LABEL_16;
  if ( v46 )
  {
    v13 = sub_180024DAC();
    if ( (unsigned int)dword_18008C000 > 5 && (unsigned __int8)sub_180002264() )
    {
      v44 = v13;
      sub_180002144(v20, (unsigned int)&dword_180085E64, v21, v22, (__int64)&v44);
    }
    if ( v13 >= 0 )
    {
      pbValue = v13;
      sub_180043364(qword_1800828D0, qword_18008D370);
      goto LABEL_19;
    }
    goto LABEL_30;
  }
  v15 = sub_180004D28(*((_QWORD *)&v52 + 1), L"Volume:GVLK", &v41);
  v13 = v15;
  if ( v15 < 0 )
    goto LABEL_16;
  if ( !v41 )
  {
    v15 = sub_180004D28(*((_QWORD *)&v52 + 1), L"VT:IA", &v42);
    v13 = v15;
    if ( v15 < 0 )
      goto LABEL_16;
    if ( v42 )
    {
      sub_180043EAC(byte_180082640, qword_18008D118);
      v12 = 1;
      sub_1800427F4(qword_180082530, qword_18008D048);
      v15 = SLpIAActivateProduct(hSLC, pProductSkuId);
      goto LABEL_15;
    }
    v15 = sub_180026BA8(hSLC, pProductSkuId, Buf1);
    v13 = v15;
    if ( v15 < 0 )
      goto LABEL_16;
    v10 = 1;
    if ( v17 >= 0
      && pnReturnIds == 1
      && *(_QWORD *)&pApplicationId->Data1 == 0x4D71D68255C92734LL
      && *(_QWORD *)pApplicationId->Data4 == 0x9F05163FECD63E98uLL )
    {
      sub_180007638(&ppbValue);
      v23 = SLGetProductSkuInformation(hSLC, pProductSkuId, L"DependsOn", 0, &pcbValue, &ppbValue);
      if ( v23 < 0 )
      {
        if ( v23 == -1073418222 )
        {
          v33 = sub_180025D80(v24, &v39);
          v11 = v39;
          v13 = v33;
          if ( (unsigned int)dword_18008C000 > 5 && (unsigned __int8)sub_180002264() )
          {
            v42 = v11;
            v41 = v13;
            sub_1800021A8(v34, (unsigned int)word_180085E1A, v35, v36, (__int64)&v41, (__int64)&v42);
          }
          if ( v13 < 0 )
            goto LABEL_30;
          if ( v11 >= 0 )
          {
            v13 = 0;
            goto LABEL_75;
          }
          IsCurrentInstalledProductKeyDefaultKey = SLpIsCurrentInstalledProductKeyDefaultKey(hSLC, &v47);
          v13 = IsCurrentInstalledProductKeyDefaultKey;
          if ( IsCurrentInstalledProductKeyDefaultKey < 0 )
          {
            sub_180004CA0((unsigned int)IsCurrentInstalledProductKeyDefaultKey);
            sub_18004362C(byte_180082DD0, byte_18008D7D8);
            goto LABEL_18;
          }
          if ( v47 )
          {
            if ( v11 != -2147221164 )
            {
              v13 = v11;
              v16 = (unsigned int)v11;
              goto LABEL_17;
            }
            v13 = -1073430525;
            sub_180004CA0(3221536771LL);
            goto LABEL_75;
          }
        }
      }
      else
      {
        v25 = ppbValue;
        if ( !ppbValue )
          v25 = (PBYTE)L"NULL";
        v26 = sub_180004DD0(v25);
        v27 = (unsigned int)v26;
        if ( v26 < 0 )
          sub_180004CA0((unsigned int)v26);
        sub_180006C10(v27);
      }
    }
    v15 = sub_180014C18(hSLC, (SLID *)pProductSkuId);
    v13 = v15;
    if ( v15 < 0 )
      goto LABEL_16;
    if ( v17 >= 0
      && pnReturnIds == 1
      && *(_QWORD *)&pApplicationId->Data1 == 0x4D71D68255C92734LL
      && *(_QWORD *)pApplicationId->Data4 == 0x9F05163FECD63E98uLL )
    {
      v28 = sub_180025D80(pApplicationId, &v39);
      v29 = dword_18008C000;
      v13 = v28;
      sub_180042514(byte_1800831B0, byte_18008DA98);
      v11 = v39;
      if ( v29 > 5 && (unsigned __int8)sub_180002264() )
      {
        sub_180043900(qword_180085AF8, qword_18008D220);
        v42 = v11;
        v41 = v13;
        sub_1800021A8(v30, (unsigned int)&unk_180085DD0, v31, v32, (__int64)&v41, (__int64)&v42);
      }
      if ( v13 < 0 )
        goto LABEL_30;
    }
    v13 = sub_180004D28(*((_QWORD *)&v52 + 1), L"Volume:CSVLK", &v44);
    sub_180042DB0(qword_1800831F0, byte_18008DAE0);
    if ( v13 < 0 )
      goto LABEL_30;
    if ( v44 && pnReturnIds )
    {
      sub_180007638(&v48);
      SLGetApplicationInformation(hSLC, pApplicationId, L"IsKeyManagementService", &peDataType, &pcbValue, &v48);
      sub_180042ACC(qword_180085CB0, &dword_18008D3CC);
LABEL_75:
      pbValue = v13;
      goto LABEL_19;
    }
LABEL_18:
    pbValue = v13;
    if ( v13 == -1073422296 )
      goto LABEL_93;
    goto LABEL_19;
  }
  v12 = 1;
  v15 = SLpVLActivateProduct(hSLC, pProductSkuId);
LABEL_15:
  v13 = v15;
  if ( v15 < 0 )
  {
LABEL_16:
    v16 = (unsigned int)v15;
LABEL_17:
    sub_180004CA0(v16);
    goto LABEL_18;
  }
  pbValue = v15;
LABEL_19:
  if ( SLSetGenuineInformation(
         pProductSkuId,
         L"SL_LAST_ACT_ATTEMPT_HRESULT",
         SL_DATA_BINARY,
         4u,
         (const BYTE *)&pbValue) >= 0 )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    SLSetGenuineInformation(
      pProductSkuId,
      L"SL_LAST_ACT_ATTEMPT_TIME",
      SL_DATA_BINARY,
      8u,
      (const BYTE *)&SystemTimeAsFileTime);
    if ( pbValue < 0 )
    {
      if ( v11 < 0 && ((v11 & 0xF000) != 0x8000 || (v11 & 0x1FFF0000) != 0x3F0000) && (v11 & 0x1FFF0000) != 0x7E10000 )
        *(_DWORD *)&v53[8] = 0;
    }
    else
    {
      *(_DWORD *)&v53[8] = -2147483647;
    }
    if ( v10 && ((int)sub_180026BA8(hSLC, pProductSkuId, &Buf2) < 0 || memcmp(Buf1, &Buf2, 0x10u)) )
      *(_DWORD *)&v53[8] = -2147483647;
    if ( *(_DWORD *)&v53[8] )
      SLSetGenuineInformation(pProductSkuId, L"SL_LAST_ACT_ATTEMPT_SERVER_FLAGS", SL_DATA_BINARY, 4u, &v53[8]);
  }
LABEL_93:
  if ( pbValue >= 0 )
  {
    if ( v12 )
      sub_1800305DC(hSLC, (SLID *)pProductSkuId);
    if ( pbValue >= 0 )
      sub_180025AD4();
  }
  if ( SLGetProductSkuInformation(hSLC, pProductSkuId, L"VLActivationType", 0, &pcbValue, &v48) >= 0
    && pcbValue == 4
    && (unsigned int)(*(_DWORD *)v48 - 1) <= 2 )
  {
    HIDWORD(v58) = *(_DWORD *)v48;
    sub_180006C10(0);
  }
  sub_180028030(v55, (unsigned int)v13);
  sub_180006C10((unsigned int)v13);
  sub_180004564((char *)&v52 + 8);
  sub_180024278(v55);
  sub_180007638(&ppbValue);
  sub_180007638(&v48);
  sub_180007638(&pApplicationId);
  return v13;
}

```

## disassembly

```asm
0x180031920  push    rbp
0x180031922  push    rbx
0x180031923  push    rsi
0x180031924  push    rdi
0x180031925  push    r12
0x180031927  push    r13
0x180031929  push    r14
0x18003192b  push    r15
0x18003192d  lea     rbp, [rsp-8]
0x180031932  sub     rsp, 108h
0x180031939  xor     edi, edi
0x18003193b  xorps   xmm0, xmm0
0x18003193e  xorps   xmm1, xmm1
0x180031941  mov     [rsp+140h+var_108], edi
0x180031945  mov     [rsp+140h+var_FC], edi
0x180031949  mov     r14, rdx
0x18003194c  mov     [rsp+140h+var_104], edi
0x180031950  mov     r15, rcx
0x180031953  mov     [rsp+140h+var_F0], edi
0x180031957  mov     [rsp+140h+pnReturnIds], edi
0x18003195b  mov     [rsp+140h+pApplicationId], rdi
0x180031960  mov     [rsp+140h+peDataType], edi
0x180031964  mov     [rsp+140h+pcbValue], edi
0x180031968  mov     [rsp+140h+var_E8], rdi
0x18003196d  mov     [rsp+140h+ppbValue], rdi
0x180031972  movups  [rbp+40h+Buf1], xmm0
0x180031976  mov     qword ptr [rbp+40h+SystemTimeAsFileTime.dwLowDateTime], rdi
0x18003197a  movups  [rbp+40h+Buf2], xmm1
0x18003197e  mov     [rbp+40h+arg_0], edi
0x180031981  mov     [rbp+40h+var_98], rdi
0x180031985  mov     [rbp+40h+var_90], rdi
0x180031989  mov     [rbp+40h+var_68], rdi
0x18003198d  movdqu  [rbp+40h+var_88], xmm0
0x180031992  mov     [rsp+140h+var_110], edi
0x180031996  movdqu  [rbp+40h+var_78], xmm1
0x18003199b  call    cs:GetTickCount64
0x1800319a1  lea     rcx, [rsp+140h+var_110]
0x1800319a6  mov     dword ptr [rbp+40h+var_68], 0FFFFFFFFh
0x1800319ad  mov     [rbp+40h+var_90], rax
0x1800319b1  call    sub_180027A3C
0x1800319b6  test    eax, eax
0x1800319b8  js      short loc_1800319C7
0x1800319ba  mov     ecx, dword ptr [rbp+40h+var_68]
0x1800319bd  cmp     [rsp+140h+var_110], edi
0x1800319c1  cmovnz  ecx, edi
0x1800319c4  mov     dword ptr [rbp+40h+var_68], ecx
0x1800319c7  xor     ecx, ecx
0x1800319c9  call    sub_180006C10
0x1800319ce  mov     [rsp+140h+var_110], edi
0x1800319d2  xorps   xmm0, xmm0
0x1800319d5  mov     [rsp+140h+var_EC], edi
0x1800319d9  mov     r13d, edi
0x1800319dc  mov     esi, edi
0x1800319de  mov     r12d, edi
0x1800319e1  movups  [rsp+140h+var_D0], xmm0
0x1800319e6  movups  [rbp+40h+var_C0], xmm0
0x1800319ea  movups  xmmword ptr [rbp+40h+var_B0], xmm0
0x1800319ee  test    r15, r15
0x1800319f1  jnz     short loc_180031A09
0x1800319f3  mov     ebx, 80070057h
0x1800319f8  mov     ecx, ebx
0x1800319fa  mov     edi, ebx
0x1800319fc  call    sub_180004CA0
0x180031a01  mov     [rbp+40h+arg_0], ebx
0x180031a04  jmp     loc_180031ACF
0x180031a09  test    r14, r14
0x180031a0c  jz      short loc_1800319F3
0x180031a0e  mov     rax, [rbp+40h+pwszProxyServer]
0x180031a12  lea     rcx, [rbp+40h+var_C0+8]
0x180031a16  mov     rbx, [rbp+40h+pActivationInfo]
0x180031a1a  mov     qword ptr [rsp+140h+var_D0+8], rax
0x180031a1f  movzx   eax, [rbp+40h+wProxyPort]
0x180031a26  mov     word ptr [rbp+40h+var_C0], ax
0x180031a2a  mov     qword ptr [rsp+140h+var_D0], rbx
0x180031a2f  call    sub_180004564
0x180031a34  mov     dword ptr [rbp+40h+var_B0+8], edi
0x180031a37  lea     rax, [rbp+40h+var_98]
0x180031a3b  mov     qword ptr [rbp+40h+var_B0], rax
0x180031a3f  test    rbx, rbx
0x180031a42  jz      loc_180031B42
0x180031a48  cmp     dword ptr [rbx], 8
0x180031a4b  jnb     short loc_180031A73
0x180031a4d  mov     ebx, 80070057h
0x180031a52  mov     ecx, ebx
0x180031a54  mov     edi, ebx
0x180031a56  call    sub_180004CA0
0x180031a5b  lea     rdx, dword_18008DBC4
0x180031a62  mov     [rbp+40h+arg_0], ebx
0x180031a65  lea     rcx, qword_180081260
0x180031a6c  call    sub_180043BD8
0x180031a71  jmp     short loc_180031ACF
0x180031a73  cmp     dword ptr [rbx+4], 1
0x180031a77  jz      short loc_180031A9F
0x180031a79  mov     ebx, 80070057h
0x180031a7e  mov     ecx, ebx
0x180031a80  mov     edi, ebx
0x180031a82  call    sub_180004CA0
0x180031a87  lea     rdx, byte_18008D320
0x180031a8e  lea     rcx, dword_180082844
0x180031a95  call    sub_180043088
0x180031a9a  jmp     loc_180031A01
0x180031a9f  lea     r8, [rsp+140h+var_D0]
0x180031aa4  mov     rdx, r14; pProductSkuId
0x180031aa7  mov     rcx, r15; hSLC
0x180031aaa  call    sub_180014C18
0x180031aaf  mov     edi, eax
0x180031ab1  test    eax, eax
0x180031ab3  jns     loc_180031B3D
0x180031ab9  mov     ecx, eax
0x180031abb  call    sub_180004CA0
0x180031ac0  mov     [rbp+40h+arg_0], edi
0x180031ac3  cmp     edi, 0C004E028h
0x180031ac9  jz      loc_180032073
0x180031acf  mov     ebx, 3
0x180031ad4  lea     rax, [rbp+40h+arg_0]
0x180031ad8  mov     r8d, ebx; eDataType
0x180031adb  mov     [rsp+140h+pbValue], rax; pbValue
0x180031ae0  lea     rdx, aSlLastActAttem; "SL_LAST_ACT_ATTEMPT_HRESULT"
0x180031ae7  mov     rcx, r14; pQueryId
0x180031aea  lea     r9d, [rbx+1]; cbValue
0x180031aee  call    cs:SLSetGenuineInformation
0x180031af4  test    eax, eax
0x180031af6  js      loc_180032073
0x180031afc  lea     rcx, [rbp+40h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180031b00  call    cs:GetSystemTimeAsFileTime
0x180031b06  lea     rax, [rbp+40h+SystemTimeAsFileTime]
0x180031b0a  mov     r8d, ebx; eDataType
0x180031b0d  lea     r9d, [rbx+5]; cbValue
0x180031b11  mov     [rsp+140h+pbValue], rax; pbValue
0x180031b16  lea     rdx, aSlLastActAttem_0; "SL_LAST_ACT_ATTEMPT_TIME"
0x180031b1d  mov     rcx, r14; pQueryId
0x180031b20  call    cs:SLSetGenuineInformation
0x180031b26  cmp     [rbp+40h+arg_0], 0
0x180031b2a  mov     ebx, 80000001h
0x180031b2f  jl      loc_180031FD2
0x180031b35  mov     dword ptr [rbp+40h+var_B0+8], ebx
0x180031b38  jmp     loc_180032018
0x180031b3d  mov     [rbp+40h+arg_0], eax
0x180031b40  jmp     short loc_180031ACF
0x180031b42  xor     r9d, r9d; eReturnIdType
0x180031b45  lea     rax, [rsp+140h+pApplicationId]
0x180031b4a  mov     [rsp+140h+ppReturnIds], rax; ppReturnIds
0x180031b4f  mov     r8, r14; pQueryId
0x180031b52  lea     rax, [rsp+140h+pnReturnIds]
0x180031b57  mov     rcx, r15; hSLC
0x180031b5a  mov     [rsp+140h+pbValue], rax; pnReturnIds
0x180031b5f  lea     edx, [r9+1]; eQueryIdType
0x180031b63  call    cs:SLGetSLIDList
0x180031b69  mov     ebx, eax
0x180031b6b  test    eax, eax
0x180031b6d  jns     short loc_180031B73
0x180031b6f  mov     [rsp+140h+pnReturnIds], edi
0x180031b73  lea     r8, [rbp+40h+var_C0+8]
0x180031b77  mov     rdx, r14; pQueryId
0x180031b7a  mov     rcx, r15; hSLC
0x180031b7d  call    sub_1800270E0
0x180031b82  mov     edi, eax
0x180031b84  test    eax, eax
0x180031b86  jns     short loc_180031B91
0x180031b88  lea     rcx, [rbp+40h+var_C0+8]
0x180031b8c  call    sub_180004564
0x180031b91  lea     rdx, xmmword_180073828
0x180031b98  cmp     [rsp+140h+pnReturnIds], esi
0x180031b9c  jz      short loc_180031BA3
0x180031b9e  mov     rdx, [rsp+140h+pApplicationId]
0x180031ba3  mov     r9, qword ptr [rbp+40h+var_C0+8]
0x180031ba7  lea     rcx, [rbp+40h+var_98]
0x180031bab  mov     r8, r14
0x180031bae  mov     [rsp+140h+pbValue], rsi
0x180031bb3  call    sub_1800077B0
0x180031bb8  test    edi, edi
0x180031bba  jns     short loc_180031BC3
0x180031bbc  mov     ecx, edi
0x180031bbe  jmp     loc_180031ABB
0x180031bc3  mov     dl, 1
0x180031bc5  lea     rcx, qword_18008F2E8
0x180031bcc  call    sub_18002F1A4
0x180031bd1  mov     rcx, qword ptr [rbp+40h+var_C0+8]
0x180031bd5  lea     r8, [rsp+140h+var_F0]
0x180031bda  lea     rdx, aPgsTb; "PGS:TB"
0x180031be1  call    sub_180004D28
0x180031be6  mov     edi, eax
0x180031be8  test    eax, eax
0x180031bea  js      loc_180031AB9
0x180031bf0  cmp     [rsp+140h+var_F0], esi
0x180031bf4  jz      short loc_180031C4A
0x180031bf6  call    sub_180024DAC
0x180031bfb  mov     edi, eax
0x180031bfd  mov     eax, cs:dword_18008C000
0x180031c03  cmp     eax, 5
0x180031c06  jbe     short loc_180031C2B
0x180031c08  call    sub_180002264
0x180031c0d  test    al, al
0x180031c0f  jz      short loc_180031C2B
0x180031c11  lea     rax, [rsp+140h+var_FC]
0x180031c16  mov     [rsp+140h+var_FC], edi
0x180031c1a  lea     rdx, dword_180085E64
0x180031c21  mov     [rsp+140h+pbValue], rax
0x180031c26  call    sub_180002144
0x180031c2b  test    edi, edi
0x180031c2d  js      short loc_180031BBC
0x180031c2f  lea     rdx, qword_18008D370
0x180031c36  mov     [rbp+40h+arg_0], edi
0x180031c39  lea     rcx, qword_1800828D0
0x180031c40  call    sub_180043364
0x180031c45  jmp     loc_180031ACF
0x180031c4a  mov     rcx, qword ptr [rbp+40h+var_C0+8]
0x180031c4e  lea     r8, [rsp+140h+var_108]
0x180031c53  lea     rdx, aVolumeGvlk; "Volume:GVLK"
0x180031c5a  call    sub_180004D28
0x180031c5f  mov     edi, eax
0x180031c61  test    eax, eax
0x180031c63  js      loc_180031AB9
0x180031c69  cmp     [rsp+140h+var_108], esi
0x180031c6d  jz      short loc_180031C86
0x180031c6f  mov     rdx, r14
0x180031c72  mov     rcx, r15
0x180031c75  mov     r12d, 1
0x180031c7b  call    cs:SLpVLActivateProduct
0x180031c81  jmp     loc_180031AAF
0x180031c86  mov     rcx, qword ptr [rbp+40h+var_C0+8]
0x180031c8a  lea     r8, [rsp+140h+var_104]
0x180031c8f  lea     rdx, aVtIa; "VT:IA"
0x180031c96  call    sub_180004D28
0x180031c9b  mov     edi, eax
0x180031c9d  test    eax, eax
0x180031c9f  js      loc_180031AB9
0x180031ca5  cmp     [rsp+140h+var_104], esi
0x180031ca9  jz      short loc_180031CE8
0x180031cab  lea     rdx, qword_18008D118
0x180031cb2  lea     rcx, byte_180082640
0x180031cb9  call    sub_180043EAC
0x180031cbe  lea     rdx, qword_18008D048
0x180031cc5  mov     r12d, 1
0x180031ccb  lea     rcx, qword_180082530
0x180031cd2  call    sub_1800427F4
0x180031cd7  mov     rdx, r14
0x180031cda  mov     rcx, r15
0x180031cdd  call    cs:SLpIAActivateProduct
0x180031ce3  jmp     loc_180031AAF
0x180031ce8  lea     r8, [rbp+40h+Buf1]
0x180031cec  mov     rdx, r14
0x180031cef  mov     rcx, r15
0x180031cf2  call    sub_180026BA8
0x180031cf7  mov     edi, eax
0x180031cf9  test    eax, eax
0x180031cfb  js      loc_180031AB9
0x180031d01  mov     r13d, 1
0x180031d07  test    ebx, ebx
0x180031d09  js      loc_180031D9E
0x180031d0f  cmp     [rsp+140h+pnReturnIds], r13d
0x180031d14  jnz     loc_180031D9E
0x180031d1a  mov     rcx, [rsp+140h+pApplicationId]
0x180031d1f  mov     rax, qword ptr cs:pQueryId.Data1
0x180031d26  cmp     rax, [rcx]
0x180031d29  jnz     short loc_180031D9E
0x180031d2b  mov     rax, qword ptr cs:pQueryId.Data4
0x180031d32  cmp     rax, [rcx+8]
0x180031d36  jnz     short loc_180031D9E
0x180031d38  lea     rcx, [rsp+140h+ppbValue]
0x180031d3d  call    sub_180007638
0x180031d42  lea     rax, [rsp+140h+ppbValue]
0x180031d47  xor     r9d, r9d; peDataType
0x180031d4a  mov     [rsp+140h+ppReturnIds], rax; ppbValue
0x180031d4f  lea     r8, aDependson; "DependsOn"
0x180031d56  lea     rax, [rsp+140h+pcbValue]
0x180031d5b  mov     rdx, r14; pProductSkuId
0x180031d5e  mov     rcx, r15; hSLC
0x180031d61  mov     [rsp+140h+pbValue], rax; pcbValue
0x180031d66  call    cs:SLGetProductSkuInformation
0x180031d6c  test    eax, eax
0x180031d6e  js      loc_180031EFC
0x180031d74  mov     rcx, [rsp+140h+ppbValue]
0x180031d79  test    rcx, rcx
0x180031d7c  jnz     short loc_180031D85
0x180031d7e  lea     rcx, aNull; "NULL"
0x180031d85  lea     rdx, [rbp+40h+var_78]
0x180031d89  call    sub_180004DD0
0x180031d8e  mov     ecx, eax
0x180031d90  test    eax, eax
0x180031d92  jns     short loc_180031D99
0x180031d94  call    sub_180004CA0
0x180031d99  call    sub_180006C10
0x180031d9e  lea     r8, [rsp+140h+var_D0]
0x180031da3  mov     rdx, r14; pProductSkuId
0x180031da6  mov     rcx, r15; hSLC
0x180031da9  call    sub_180014C18
0x180031dae  mov     edi, eax
0x180031db0  test    eax, eax
0x180031db2  js      loc_180031AB9
0x180031db8  test    ebx, ebx
0x180031dba  js      loc_180031E67
0x180031dc0  cmp     [rsp+140h+pnReturnIds], r13d
0x180031dc5  jnz     loc_180031E67
0x180031dcb  mov     rcx, [rsp+140h+pApplicationId]
0x180031dd0  mov     rax, qword ptr cs:pQueryId.Data1
0x180031dd7  cmp     rax, [rcx]
0x180031dda  jnz     loc_180031E67
0x180031de0  mov     rax, qword ptr cs:pQueryId.Data4
0x180031de7  cmp     rax, [rcx+8]
  ... truncated ...
```
