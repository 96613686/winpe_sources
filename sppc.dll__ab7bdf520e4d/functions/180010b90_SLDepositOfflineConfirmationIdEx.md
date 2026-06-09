# SLDepositOfflineConfirmationIdEx

- ea: `0x180010b90`
- end: `0x180010fa3`
- name: `SLDepositOfflineConfirmationIdEx`
- size: `1043`
- prototype: `HRESULT __stdcall(HSLC hSLC, const SLID *pProductSkuId, const SL_ACTIVATION_INFO_HEADER *pActivationInfo, PCWSTR pwszInstallationId, PCWSTR pwszConfirmationId)`
- caller_count: `1`
- callee_count: `19`
- tags: `service_task, installer_update`

## callers

- `0x180010b50`

## callees

- `0x1800021b0`
- `0x180002610`
- `0x1800028f0`
- `0x1800044dc`
- `0x180004f44`
- `0x180004f80`
- `0x180005208`
- `0x180005230`
- `0x18000532c`
- `0x180006844`
- `0x1800069d8`
- `0x18000a8d0`
- `0x18000ecd4`
- `0x18000f144`
- `0x180010b90`
- `0x180011750`
- `0x1800125d0`
- `0x180012810`
- `0x180013980`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180010c88`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180010c88`

## string_xrefs

- `0x180010f8a`: `IsKeyManagementService`
- `0x180010c6b`: `SL_LAST_ACT_ATTEMPT_HRESULT`
- `0x180010c9e`: `SL_LAST_ACT_ATTEMPT_TIME`
- `0x180010cc9`: `SL_LAST_ACT_ATTEMPT_SERVER_FLAGS`

## pseudocode

```c
HRESULT __stdcall SLDepositOfflineConfirmationIdEx(
        HSLC hSLC,
        const SLID *pProductSkuId,
        const SL_ACTIVATION_INFO_HEADER *pActivationInfo,
        PCWSTR pwszInstallationId,
        PCWSTR pwszConfirmationId)
{
  PBYTE v5; // rsi
  HRESULT v10; // edi
  int v11; // ecx
  int v12; // eax
  __int64 v13; // rcx
  HRESULT v15; // ebx
  int v16; // [rsp+30h] [rbp-41h] BYREF
  UINT pnReturnIds; // [rsp+34h] [rbp-3Dh] BYREF
  int v18; // [rsp+38h] [rbp-39h]
  BYTE v19[4]; // [rsp+3Ch] [rbp-35h] BYREF
  SLDATATYPE peDataType; // [rsp+40h] [rbp-31h] BYREF
  PBYTE ppbValue; // [rsp+48h] [rbp-29h] BYREF
  SLID *pApplicationId; // [rsp+50h] [rbp-21h] BYREF
  void *Buf2; // [rsp+58h] [rbp-19h] BYREF
  void *Buf1; // [rsp+60h] [rbp-11h] BYREF
  SLID *pPKeyId; // [rsp+68h] [rbp-9h] BYREF
  __int64 v26[2]; // [rsp+70h] [rbp-1h] BYREF
  __int128 v27; // [rsp+80h] [rbp+Fh] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+90h] [rbp+1Fh] BYREF
  int pbValue; // [rsp+D0h] [rbp+5Fh] BYREF

  v5 = 0;
  v16 = 0;
  pPKeyId = 0;
  v26[0] = (__int64)&v27 + 8;
  v26[1] = (__int64)&v27;
  pnReturnIds = 0;
  ppbValue = 0;
  Buf1 = 0;
  Buf2 = 0;
  v18 = 0;
  pApplicationId = 0;
  pbValue = 0;
  SystemTimeAsFileTime = 0;
  *(_DWORD *)v19 = 0;
  v27 = 0;
  if ( hSLC && pProductSkuId && pwszInstallationId && pwszConfirmationId )
  {
    v12 = sub_180004F44(v26, 1, pProductSkuId);
    v10 = v12;
    if ( v12 < 0 )
      goto LABEL_7;
    v12 = sub_18000F144(v26, 2, pwszInstallationId);
    v10 = v12;
    if ( v12 < 0 )
      goto LABEL_7;
    v12 = sub_18000F144(v26, 3, pwszConfirmationId);
    v10 = v12;
    if ( v12 < 0 )
      goto LABEL_7;
    if ( !pActivationInfo )
    {
      v16 = 0;
      v12 = sub_180004F80(v26, 4, &v16);
      v10 = v12;
      if ( v12 < 0 )
        goto LABEL_7;
      goto LABEL_24;
    }
    if ( pActivationInfo->cbSize == 24 && pActivationInfo->type == SL_ACTIVATION_TYPE_ACTIVE_DIRECTORY )
    {
      v16 = 1;
      v12 = sub_180004F80(v26, 4, &v16);
      v10 = v12;
      if ( v12 < 0 )
        goto LABEL_7;
      v12 = sub_18000F144(v26, 5, *(_QWORD *)&pActivationInfo[1]);
      v10 = v12;
      if ( v12 < 0 )
        goto LABEL_7;
      v12 = sub_18000F144(v26, 6, *(_QWORD *)&pActivationInfo[2]);
      v10 = v12;
      if ( v12 < 0 )
        goto LABEL_7;
LABEL_24:
      v10 = sub_1800044DC(v26, (__int64)hSLC, 0x17u, 0, 1);
      if ( v10 < 0 )
      {
LABEL_25:
        v13 = (unsigned int)v10;
        goto LABEL_8;
      }
      sub_1800021B0(byte_180019020, qword_18001E670);
      if ( v16 )
        goto LABEL_9;
      v15 = SLGetSLIDList(hSLC, SL_ID_PRODUCT_SKU, pProductSkuId, SL_ID_PKEY, &pnReturnIds, &pPKeyId);
      sub_1800028F0(&dword_180019D84, qword_18001E5C8);
      if ( v15 < 0 )
        goto LABEL_9;
      if ( pnReturnIds )
      {
        if ( SLGetPKeyInformation(hSLC, pPKeyId, L"Channel", &peDataType, &pnReturnIds, &ppbValue) < 0 )
          goto LABEL_9;
        v5 = ppbValue;
      }
      if ( !v5 )
      {
LABEL_38:
        pbValue = v10;
        goto LABEL_10;
      }
      sub_180002610(&dword_180019334, &dword_18001E9C4);
      v12 = sub_1800069D8(v5);
      v10 = v12;
      if ( v12 >= 0 )
      {
        v12 = sub_1800069D8(L"Volume:CSVLK");
        v10 = v12;
        if ( v12 >= 0 )
        {
          v10 = sub_18000ECD4(Buf1, Buf2);
          if ( v10 < 0 )
            goto LABEL_25;
          if ( v18
            && SLGetSLIDList(
                 hSLC,
                 SL_ID_PRODUCT_SKU,
                 pProductSkuId,
                 SL_ID_APPLICATION,
                 (UINT *)&peDataType,
                 &pApplicationId) >= 0 )
          {
            sub_18000532C(&ppbValue);
            SLGetApplicationInformation(
              hSLC,
              pApplicationId,
              L"IsKeyManagementService",
              &peDataType,
              &pnReturnIds,
              &ppbValue);
            goto LABEL_38;
          }
LABEL_9:
          pbValue = v10;
          if ( v10 == -1073422296 )
            goto LABEL_13;
          goto LABEL_10;
        }
      }
LABEL_7:
      v13 = (unsigned int)v12;
LABEL_8:
      sub_180006844(v13);
      goto LABEL_9;
    }
  }
  v10 = -2147024809;
  sub_180006844(2147942487LL);
  pbValue = v11;
LABEL_10:
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
    if ( pbValue >= 0 )
    {
      *(_DWORD *)v19 = -2147483647;
      SLSetGenuineInformation(pProductSkuId, L"SL_LAST_ACT_ATTEMPT_SERVER_FLAGS", SL_DATA_BINARY, 4u, v19);
    }
  }
LABEL_13:
  sub_18000A8D0((unsigned int)v10);
  sub_18000532C(&pApplicationId);
  sub_180005230(&Buf2);
  sub_180005230(&Buf1);
  sub_18000532C(&ppbValue);
  sub_18000532C(&pPKeyId);
  sub_180005208(v26);
  return v10;
}

```

## disassembly

```asm
0x180010b90  mov     [rsp-8+arg_8], rbx
0x180010b95  mov     [rsp-8+arg_10], rsi
0x180010b9a  push    rbp
0x180010b9b  push    rdi
0x180010b9c  push    r12
0x180010b9e  push    r13
0x180010ba0  push    r15
0x180010ba2  lea     rbp, [rsp-2Fh]
0x180010ba7  sub     rsp, 0A0h
0x180010bae  xor     esi, esi
0x180010bb0  mov     [rbp+4Fh+var_90], 0
0x180010bb7  mov     [rbp+4Fh+pPKeyId], 0
0x180010bbf  lea     rax, [rbp+4Fh+var_40+8]
0x180010bc3  mov     [rbp+4Fh+var_50], rax
0x180010bc7  lea     rax, [rbp+4Fh+var_40]
0x180010bcb  mov     [rbp+4Fh+var_48], rax
0x180010bcf  xorps   xmm0, xmm0
0x180010bd2  mov     [rbp+4Fh+pnReturnIds], 0
0x180010bd9  mov     r12, r9
0x180010bdc  mov     [rbp+4Fh+ppbValue], rsi
0x180010be0  mov     rbx, r8
0x180010be3  mov     [rbp+4Fh+Buf1], rsi
0x180010be7  mov     r15, rdx
0x180010bea  mov     [rbp+4Fh+Buf2], rsi
0x180010bee  mov     r13, rcx
0x180010bf1  mov     [rbp+4Fh+var_88], esi
0x180010bf4  mov     [rbp+4Fh+pApplicationId], rsi
0x180010bf8  mov     [rbp+4Fh+arg_0], esi
0x180010bfb  mov     qword ptr [rbp+4Fh+SystemTimeAsFileTime.dwLowDateTime], rsi
0x180010bff  mov     dword ptr [rbp+4Fh+var_84], esi
0x180010c02  movdqu  [rbp+4Fh+var_40], xmm0
0x180010c07  test    rcx, rcx
0x180010c0a  jnz     short loc_180010C1D
0x180010c0c  mov     ecx, 80070057h
0x180010c11  mov     edi, ecx
0x180010c13  call    sub_180006844
0x180010c18  mov     [rbp+4Fh+arg_0], ecx
0x180010c1b  jmp     short loc_180010C5A
0x180010c1d  test    r15, r15
0x180010c20  jz      short loc_180010C0C
0x180010c22  test    r12, r12
0x180010c25  jz      short loc_180010C0C
0x180010c27  cmp     [rbp+4Fh+pwszConfirmationId], rsi
0x180010c2b  jz      short loc_180010C0C
0x180010c2d  mov     r8, r15
0x180010c30  lea     rcx, [rbp+4Fh+var_50]
0x180010c34  mov     edx, 1
0x180010c39  call    sub_180004F44
0x180010c3e  mov     edi, eax
0x180010c40  test    eax, eax
0x180010c42  jns     loc_180010D33
0x180010c48  mov     ecx, eax
0x180010c4a  call    sub_180006844
0x180010c4f  mov     [rbp+4Fh+arg_0], edi
0x180010c52  cmp     edi, 0C004E028h
0x180010c58  jz      short loc_180010CD8
0x180010c5a  mov     ebx, 4
0x180010c5f  lea     rax, [rbp+4Fh+arg_0]
0x180010c63  mov     r9d, ebx; cbValue
0x180010c66  mov     [rsp+0C0h+pbValue], rax; pbValue
0x180010c6b  lea     rdx, aSlLastActAttem; "SL_LAST_ACT_ATTEMPT_HRESULT"
0x180010c72  mov     rcx, r15; pQueryId
0x180010c75  lea     esi, [rbx-1]
0x180010c78  mov     r8d, esi; eDataType
0x180010c7b  call    SLSetGenuineInformation
0x180010c80  test    eax, eax
0x180010c82  js      short loc_180010CD8
0x180010c84  lea     rcx, [rbp+4Fh+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180010c88  call    cs:GetSystemTimeAsFileTime
0x180010c8e  lea     rax, [rbp+4Fh+SystemTimeAsFileTime]
0x180010c92  mov     r8d, esi; eDataType
0x180010c95  lea     r9d, [rbx+4]; cbValue
0x180010c99  mov     [rsp+0C0h+pbValue], rax; pbValue
0x180010c9e  lea     rdx, aSlLastActAttem_0; "SL_LAST_ACT_ATTEMPT_TIME"
0x180010ca5  mov     rcx, r15; pQueryId
0x180010ca8  call    SLSetGenuineInformation
0x180010cad  cmp     [rbp+4Fh+arg_0], 0
0x180010cb1  jl      short loc_180010CD8
0x180010cb3  lea     rax, [rbp+4Fh+var_84]
0x180010cb7  mov     dword ptr [rbp+4Fh+var_84], 80000001h
0x180010cbe  mov     r9d, ebx; cbValue
0x180010cc1  mov     [rsp+0C0h+pbValue], rax; pbValue
0x180010cc6  mov     r8d, esi; eDataType
0x180010cc9  lea     rdx, aSlLastActAttem_1; "SL_LAST_ACT_ATTEMPT_SERVER_FLAGS"
0x180010cd0  mov     rcx, r15; pQueryId
0x180010cd3  call    SLSetGenuineInformation
0x180010cd8  mov     ecx, edi
0x180010cda  call    sub_18000A8D0
0x180010cdf  lea     rcx, [rbp+4Fh+pApplicationId]
0x180010ce3  call    sub_18000532C
0x180010ce8  lea     rcx, [rbp+4Fh+Buf2]
0x180010cec  call    sub_180005230
0x180010cf1  lea     rcx, [rbp+4Fh+Buf1]
0x180010cf5  call    sub_180005230
0x180010cfa  lea     rcx, [rbp+4Fh+ppbValue]
0x180010cfe  call    sub_18000532C
0x180010d03  lea     rcx, [rbp+4Fh+pPKeyId]
0x180010d07  call    sub_18000532C
0x180010d0c  lea     rcx, [rbp+4Fh+var_50]
0x180010d10  call    sub_180005208
0x180010d15  lea     r11, [rsp+0C0h+var_20]
0x180010d1d  mov     eax, edi
0x180010d1f  mov     rbx, [r11+38h]
0x180010d23  mov     rsi, [r11+40h]
0x180010d27  mov     rsp, r11
0x180010d2a  pop     r15
0x180010d2c  pop     r13
0x180010d2e  pop     r12
0x180010d30  pop     rdi
0x180010d31  pop     rbp
0x180010d32  retn
0x180010d33  mov     r8, r12
0x180010d36  lea     rcx, [rbp+4Fh+var_50]
0x180010d3a  mov     edx, 2
0x180010d3f  call    sub_18000F144
0x180010d44  mov     edi, eax
0x180010d46  test    eax, eax
0x180010d48  js      loc_180010C48
0x180010d4e  mov     r8, [rbp+4Fh+pwszConfirmationId]
0x180010d52  lea     rcx, [rbp+4Fh+var_50]
0x180010d56  mov     edx, 3
0x180010d5b  call    sub_18000F144
0x180010d60  mov     edi, eax
0x180010d62  test    eax, eax
0x180010d64  js      loc_180010C48
0x180010d6a  test    rbx, rbx
0x180010d6d  jz      short loc_180010DE1
0x180010d6f  cmp     dword ptr [rbx], 18h
0x180010d72  jnz     loc_180010C0C
0x180010d78  mov     r12d, 1
0x180010d7e  cmp     [rbx+4], r12d
0x180010d82  jnz     loc_180010C0C
0x180010d88  lea     r8, [rbp+4Fh+var_90]
0x180010d8c  mov     [rbp+4Fh+var_90], r12d
0x180010d90  lea     edx, [r12+3]
0x180010d95  lea     rcx, [rbp+4Fh+var_50]
0x180010d99  call    sub_180004F80
0x180010d9e  mov     edi, eax
0x180010da0  test    eax, eax
0x180010da2  js      loc_180010C48
0x180010da8  mov     r8, [rbx+8]
0x180010dac  lea     edx, [r12+4]
0x180010db1  lea     rcx, [rbp+4Fh+var_50]
0x180010db5  call    sub_18000F144
0x180010dba  mov     edi, eax
0x180010dbc  test    eax, eax
0x180010dbe  js      loc_180010C48
0x180010dc4  mov     r8, [rbx+10h]
0x180010dc8  lea     edx, [r12+5]
0x180010dcd  lea     rcx, [rbp+4Fh+var_50]
0x180010dd1  call    sub_18000F144
0x180010dd6  mov     edi, eax
0x180010dd8  test    eax, eax
0x180010dda  jns     short loc_180010E06
0x180010ddc  jmp     loc_180010C48
0x180010de1  lea     r8, [rbp+4Fh+var_90]
0x180010de5  mov     [rbp+4Fh+var_90], esi
0x180010de8  mov     edx, 4
0x180010ded  lea     rcx, [rbp+4Fh+var_50]
0x180010df1  call    sub_180004F80
0x180010df6  mov     edi, eax
0x180010df8  test    eax, eax
0x180010dfa  js      loc_180010C48
0x180010e00  mov     r12d, 1
0x180010e06  xor     r9d, r9d
0x180010e09  mov     dword ptr [rsp+0C0h+pbValue], r12d
0x180010e0e  mov     rdx, r13
0x180010e11  lea     rcx, [rbp+4Fh+var_50]
0x180010e15  lea     r8d, [r9+17h]
0x180010e19  call    sub_1800044DC
0x180010e1e  mov     edi, eax
0x180010e20  test    eax, eax
0x180010e22  jns     short loc_180010E2B
0x180010e24  mov     ecx, edi
0x180010e26  jmp     loc_180010C4A
0x180010e2b  lea     rdx, qword_18001E670
0x180010e32  lea     rcx, byte_180019020
0x180010e39  call    sub_1800021B0
0x180010e3e  cmp     [rbp+4Fh+var_90], esi
0x180010e41  jnz     loc_180010C4F
0x180010e47  lea     rax, [rbp+4Fh+pPKeyId]
0x180010e4b  mov     r9d, 4; eReturnIdType
0x180010e51  mov     [rsp+0C0h+ppReturnIds], rax; ppReturnIds
0x180010e56  mov     r8, r15; pQueryId
0x180010e59  lea     rax, [rbp+4Fh+pnReturnIds]
0x180010e5d  mov     edx, r12d; eQueryIdType
0x180010e60  mov     rcx, r13; hSLC
0x180010e63  mov     [rsp+0C0h+pbValue], rax; pnReturnIds
0x180010e68  call    SLGetSLIDList
0x180010e6d  lea     rdx, qword_18001E5C8
0x180010e74  mov     ebx, eax
0x180010e76  lea     rcx, dword_180019D84
0x180010e7d  call    sub_1800028F0
0x180010e82  test    ebx, ebx
0x180010e84  js      loc_180010C4F
0x180010e8a  cmp     [rbp+4Fh+pnReturnIds], esi
0x180010e8d  jbe     short loc_180010EC4
0x180010e8f  mov     rdx, [rbp+4Fh+pPKeyId]; pPKeyId
0x180010e93  lea     rax, [rbp+4Fh+ppbValue]
0x180010e97  mov     [rsp+0C0h+ppReturnIds], rax; ppbValue
0x180010e9c  lea     r9, [rbp+4Fh+peDataType]; peDataType
0x180010ea0  lea     rax, [rbp+4Fh+pnReturnIds]
0x180010ea4  mov     rcx, r13; hSLC
0x180010ea7  lea     r8, aChannel; "Channel"
0x180010eae  mov     [rsp+0C0h+pbValue], rax; pcbValue
0x180010eb3  call    SLGetPKeyInformation
0x180010eb8  test    eax, eax
0x180010eba  js      loc_180010C4F
0x180010ec0  mov     rsi, [rbp+4Fh+ppbValue]
0x180010ec4  test    rsi, rsi
0x180010ec7  jz      loc_180010F9B
0x180010ecd  lea     rdx, dword_18001E9C4
0x180010ed4  lea     rcx, dword_180019334
0x180010edb  call    sub_180002610
0x180010ee0  test    rsi, rsi
0x180010ee3  jz      loc_180010F9B
0x180010ee9  lea     rdx, [rbp+4Fh+Buf1]
0x180010eed  mov     rcx, rsi; Src
0x180010ef0  call    sub_1800069D8
0x180010ef5  mov     edi, eax
0x180010ef7  test    eax, eax
0x180010ef9  js      loc_180010C48
0x180010eff  lea     rdx, [rbp+4Fh+Buf2]
0x180010f03  lea     rcx, aVolumeCsvlk; "Volume:CSVLK"
0x180010f0a  call    sub_1800069D8
0x180010f0f  mov     edi, eax
0x180010f11  test    eax, eax
0x180010f13  js      loc_180010C48
0x180010f19  mov     rdx, [rbp+4Fh+Buf2]; Buf2
0x180010f1d  lea     r8, [rbp+4Fh+var_88]
0x180010f21  mov     rcx, [rbp+4Fh+Buf1]; Buf1
0x180010f25  call    sub_18000ECD4
0x180010f2a  mov     edi, eax
0x180010f2c  test    eax, eax
0x180010f2e  js      loc_180010E24
0x180010f34  cmp     [rbp+4Fh+var_88], 0
0x180010f38  jz      loc_180010C4F
0x180010f3e  lea     rax, [rbp+4Fh+pApplicationId]
0x180010f42  xor     r9d, r9d; eReturnIdType
0x180010f45  mov     [rsp+0C0h+ppReturnIds], rax; ppReturnIds
0x180010f4a  mov     r8, r15; pQueryId
0x180010f4d  lea     rax, [rbp+4Fh+peDataType]
0x180010f51  mov     edx, r12d; eQueryIdType
0x180010f54  mov     rcx, r13; hSLC
0x180010f57  mov     [rsp+0C0h+pbValue], rax; pnReturnIds
0x180010f5c  call    SLGetSLIDList
0x180010f61  test    eax, eax
0x180010f63  js      loc_180010C4F
0x180010f69  lea     rcx, [rbp+4Fh+ppbValue]
0x180010f6d  call    sub_18000532C
0x180010f72  mov     rdx, [rbp+4Fh+pApplicationId]; pApplicationId
0x180010f76  lea     rax, [rbp+4Fh+ppbValue]
0x180010f7a  mov     [rsp+0C0h+ppReturnIds], rax; ppbValue
0x180010f7f  lea     r9, [rbp+4Fh+peDataType]; peDataType
0x180010f83  lea     rax, [rbp+4Fh+pnReturnIds]
0x180010f87  mov     rcx, r13; hSLC
0x180010f8a  lea     r8, aIskeymanagemen; "IsKeyManagementService"
0x180010f91  mov     [rsp+0C0h+pbValue], rax; pcbValue
0x180010f96  call    SLGetApplicationInformation
0x180010f9b  mov     [rbp+4Fh+arg_0], edi
0x180010f9e  jmp     loc_180010C5A
```
