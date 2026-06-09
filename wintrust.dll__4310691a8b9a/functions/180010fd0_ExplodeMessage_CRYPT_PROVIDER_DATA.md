# _ExplodeMessage(_CRYPT_PROVIDER_DATA *)

- ea: `0x180010fd0`
- end: `0x180011408`
- name: `?_ExplodeMessage@@YAHPEAU_CRYPT_PROVIDER_DATA@@@Z`
- size: `1080`
- prototype: `__int64 __fastcall(struct _CRYPT_PROVIDER_DATA *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180029250`

## callees

- `0x180010fd0`
- `0x180011550`
- `0x18002e5d0`
- `0x18004de76`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800112a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800112cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800112ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011355`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011369`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800113a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800113f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800112a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800112cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800112ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011355`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011369`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800113a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800113f3`
- `CRYPT32!CryptMsgGetParam` at `0x180011063`
- `CRYPT32!CryptMsgGetParam` at `0x1800110a9`
- `CRYPT32!CryptMsgGetParam` at `0x180011105`
- `CRYPT32!CryptMsgGetParam` at `0x180011149`
- `CRYPT32!CryptMsgGetParam` at `0x180011063`
- `CRYPT32!CryptMsgGetParam` at `0x1800110a9`
- `CRYPT32!CryptMsgGetParam` at `0x180011105`
- `CRYPT32!CryptMsgGetParam` at `0x180011149`
- `CRYPT32!CertCloseStore` at `0x180011040`
- `CRYPT32!CertCloseStore` at `0x180011306`
- `CRYPT32!CertCloseStore` at `0x180011040`
- `CRYPT32!CertCloseStore` at `0x180011306`
- `CRYPT32!CertOpenStore` at `0x18001100e`
- `CRYPT32!CertOpenStore` at `0x18001100e`
- `imagehlp!IsBufferCleanOfInvalidMarkers` at `0x1800113cb`
- `imagehlp!IsBufferCleanOfInvalidMarkers` at `0x1800113cb`

## pseudocode

```c
__int64 __fastcall _ExplodeMessage(struct _CRYPT_PROVIDER_DATA *a1)
{
  bool v2; // cc
  HCERTSTORE v3; // rax
  void *v4; // rdi
  HCRYPTMSG hMsg; // rcx
  void *v6; // rdi
  bool v7; // zf
  PFN_CPD_MEM_FREE pfnFree; // rax
  HCRYPTMSG v9; // rcx
  BYTE *v10; // rdi
  struct SIP_SUBJECTINFO_ *psSipSubjectInfo; // rcx
  GUID *pgSubjectType; // rdx
  __int64 v13; // rax
  struct SIP_SUBJECTINFO_ *v15; // rcx
  struct MS_ADDINFO_FLAT_ *psFlat; // rdi
  __int64 v17; // rax
  struct SIP_INDIRECT_DATA_ *v18; // rax
  _OWORD *v19; // r8
  struct SIP_INDIRECT_DATA_ *v20; // rdx
  struct SIP_INDIRECT_DATA_ *psIndirectData; // rcx
  DWORD pcbData; // [rsp+70h] [rbp+8h] BYREF
  DWORD v23; // [rsp+78h] [rbp+10h] BYREF
  DWORD v24; // [rsp+80h] [rbp+18h] BYREF

  v2 = a1->cbStruct <= 0xB0;
  pcbData = 0;
  v23 = 0;
  if ( !v2 && a1->fRecallWithState )
  {
LABEL_6:
    hMsg = a1->hMsg;
    pcbData = 0;
    CryptMsgGetParam(hMsg, 4u, 0, 0, &pcbData);
    if ( !pcbData )
    {
      a1->padwTrustStepErrors[33] = -2146885619;
      a1->padwTrustStepErrors[10] = GetLastError();
      return 0;
    }
    v6 = (void *)((__int64 (__fastcall *)(_QWORD))a1->psPfns->pfnAlloc)(pcbData + 1);
    if ( v6 )
    {
      if ( !CryptMsgGetParam(a1->hMsg, 4u, 0, v6, &pcbData) )
      {
        a1->padwTrustStepErrors[10] = GetLastError();
        a1->padwTrustStepErrors[33] = -2146885619;
        operator delete(v6);
        return 0;
      }
      *((_BYTE *)v6 + pcbData) = 0;
      v7 = strcmp_0((const char *)v6, "1.3.6.1.4.1.311.2.1.4") == 0;
      pfnFree = a1->psPfns->pfnFree;
      if ( v7 )
      {
        ((void (__fastcall *)(void *))pfnFree)(v6);
        v9 = a1->hMsg;
        v23 = 0;
        CryptMsgGetParam(v9, 2u, 0, 0, &v23);
        if ( v23 )
        {
          v10 = (BYTE *)((__int64 (*)(void))a1->psPfns->pfnAlloc)();
          if ( v10 )
          {
            if ( CryptMsgGetParam(a1->hMsg, 2u, 0, v10, &v23) )
            {
              if ( *(_DWORD *)(*(_QWORD *)&a1[1].cbStruct + 24LL) )
              {
                psIndirectData = a1->pPDSip->psIndirectData;
                if ( psIndirectData )
                {
                  operator delete(psIndirectData);
                  a1->pPDSip->psIndirectData = 0;
                  a1->pPDSip->psIndirectData = 0;
                }
              }
              if ( (unsigned int)TrustDecode(
                                   0x10000,
                                   (void **)&a1->pPDSip->psIndirectData,
                                   &pcbData,
                                   0xCAu,
                                   a1->dwEncoding,
                                   (const CHAR *)0x7D3,
                                   v10,
                                   v23,
                                   0) )
              {
                psSipSubjectInfo = a1->pPDSip->psSipSubjectInfo;
                pgSubjectType = psSipSubjectInfo->pgSubjectType;
                v13 = *(_QWORD *)&pgSubjectType->Data1 - gPESubject;
                if ( *(_QWORD *)&pgSubjectType->Data1 == gPESubject )
                  v13 = *(_QWORD *)pgSubjectType->Data4 + 0x116A3DB03FFFB874LL;
                if ( !v13 && psSipSubjectInfo->dwReserved1 )
                {
                  v24 = 0;
                  if ( !(unsigned int)IsBufferCleanOfInvalidMarkers(v10, v23, &v24) )
                    a1->pPDSip->psSipSubjectInfo->dwReserved2 = v24;
                }
                ((void (__fastcall *)(BYTE *))a1->psPfns->pfnFree)(v10);
                return 1;
              }
            }
            a1->padwTrustStepErrors[33] = -2146885619;
            a1->padwTrustStepErrors[11] = GetLastError();
            ((void (__fastcall *)(BYTE *))a1->psPfns->pfnFree)(v10);
            return 0;
          }
          goto LABEL_30;
        }
        a1->padwTrustStepErrors[33] = -2146885619;
        a1->padwTrustStepErrors[11] = GetLastError();
        return 0;
      }
      ((void (__fastcall *)(void *))pfnFree)(v6);
      if ( a1->pWintrustData->dwUnionChoice != 2 )
        return 1;
      v15 = a1->pPDSip->psSipSubjectInfo;
      if ( v15->dwUnionChoice != 2 )
        return 1;
      psFlat = v15->psFlat;
      if ( !psFlat )
        return 1;
      v17 = *(_QWORD *)&psFlat[1].cbStruct;
      if ( !v17 || !*(_QWORD *)(v17 + 48) )
        return 1;
      v18 = (struct SIP_INDIRECT_DATA_ *)((__int64 (__fastcall *)(__int64))a1->psPfns->pfnAlloc)(64);
      a1->pPDSip->psIndirectData = v18;
      if ( v18 )
      {
        v19 = *(_OWORD **)(*(_QWORD *)&psFlat[1].cbStruct + 48LL);
        v20 = a1->pPDSip->psIndirectData;
        *(_OWORD *)&v20->Data.pszObjId = *v19;
        *(_OWORD *)&v20->Data.Value.pbData = v19[1];
        v20->DigestAlgorithm.Parameters = (CRYPT_OBJID_BLOB)v19[2];
        v20->Digest = (CRYPT_HASH_BLOB)v19[3];
        return 1;
      }
    }
LABEL_30:
    a1->dwError = GetLastError();
    a1->padwTrustStepErrors[33] = -2146869247;
    return 0;
  }
  v3 = CertOpenStore((LPCSTR)1, a1->dwEncoding, a1->hProv, 1u, a1->hMsg);
  v4 = v3;
  if ( !v3 )
  {
    a1->padwTrustStepErrors[32] = GetLastError();
    return 0;
  }
  if ( ((unsigned int (__fastcall *)(struct _CRYPT_PROVIDER_DATA *, HCERTSTORE))a1->psPfns->pfnAddStore2Chain)(a1, v3) )
  {
    CertCloseStore(v4, 0);
    goto LABEL_6;
  }
  a1->dwError = GetLastError();
  a1->padwTrustStepErrors[32] = -2146869247;
  CertCloseStore(v4, 0);
  return 0;
}

```

## disassembly

```asm
0x180010fd0  push    rbx
0x180010fd2  push    rsi
0x180010fd3  push    rdi
0x180010fd4  sub     rsp, 50h
0x180010fd8  xor     esi, esi
0x180010fda  mov     rbx, rcx
0x180010fdd  cmp     dword ptr [rcx], 0B0h
0x180010fe3  mov     [rsp+68h+pcbData], esi
0x180010fe7  mov     [rsp+68h+arg_8], esi
0x180010feb  jbe     short loc_180010FF5
0x180010fed  cmp     [rcx+0B0h], esi
0x180010ff3  jnz     short loc_180011046
0x180010ff5  mov     rax, [rcx+70h]
0x180010ff9  mov     r9d, 1; dwFlags
0x180010fff  mov     r8, [rcx+28h]; hCryptProv
0x180011003  mov     edx, [rcx+68h]; dwEncodingType
0x180011006  mov     ecx, r9d; lpszStoreProvider
0x180011009  mov     [rsp+68h+pvPara], rax; pvPara
0x18001100e  call    cs:__imp_CertOpenStore
0x180011014  mov     rdi, rax
0x180011017  test    rax, rax
0x18001101a  jz      loc_1800113F3
0x180011020  mov     rax, [rbx+40h]
0x180011024  mov     rdx, rdi
0x180011027  mov     rcx, rbx
0x18001102a  mov     rax, [rax+18h]
0x18001102e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011033  test    eax, eax
0x180011035  jz      loc_1800112EA
0x18001103b  xor     edx, edx; dwFlags
0x18001103d  mov     rcx, rdi; hCertStore
0x180011040  call    cs:__imp_CertCloseStore
0x180011046  mov     rcx, [rbx+70h]; hCryptMsg
0x18001104a  lea     rax, [rsp+68h+pcbData]
0x18001104f  xor     r9d, r9d; pvData
0x180011052  mov     [rsp+68h+pvPara], rax; pcbData
0x180011057  xor     r8d, r8d; dwIndex
0x18001105a  mov     [rsp+68h+pcbData], esi
0x18001105e  mov     edx, 4; dwParamType
0x180011063  call    cs:__imp_CryptMsgGetParam
0x180011069  mov     ecx, [rsp+68h+pcbData]
0x18001106d  test    ecx, ecx
0x18001106f  jz      loc_180011347
0x180011075  mov     rax, [rbx+40h]
0x180011079  inc     ecx
0x18001107b  mov     rax, [rax+8]
0x18001107f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011084  mov     rdi, rax
0x180011087  test    rax, rax
0x18001108a  jz      loc_1800112CC
0x180011090  mov     rcx, [rbx+70h]; hCryptMsg
0x180011094  lea     rax, [rsp+68h+pcbData]
0x180011099  mov     r9, rdi; pvData
0x18001109c  mov     [rsp+68h+pvPara], rax; pcbData
0x1800110a1  xor     r8d, r8d; dwIndex
0x1800110a4  mov     edx, 4; dwParamType
0x1800110a9  call    cs:__imp_CryptMsgGetParam
0x1800110af  test    eax, eax
0x1800110b1  jz      loc_180011369
0x1800110b7  mov     eax, [rsp+68h+pcbData]
0x1800110bb  lea     rdx, a136141311214; "1.3.6.1.4.1.311.2.1.4"
0x1800110c2  mov     rcx, rdi; Str1
0x1800110c5  mov     [rax+rdi], sil
0x1800110c9  call    strcmp_0
0x1800110ce  mov     ecx, eax
0x1800110d0  mov     rax, [rbx+40h]
0x1800110d4  test    ecx, ecx
0x1800110d6  mov     rcx, rdi
0x1800110d9  mov     rax, [rax+10h]
0x1800110dd  jnz     loc_180011201
0x1800110e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110e8  mov     rcx, [rbx+70h]; hCryptMsg
0x1800110ec  lea     rax, [rsp+68h+arg_8]
0x1800110f1  xor     r9d, r9d; pvData
0x1800110f4  mov     [rsp+68h+pvPara], rax; pcbData
0x1800110f9  xor     r8d, r8d; dwIndex
0x1800110fc  mov     [rsp+68h+arg_8], esi
0x180011100  mov     edx, 2; dwParamType
0x180011105  call    cs:__imp_CryptMsgGetParam
0x18001110b  mov     ecx, [rsp+68h+arg_8]
0x18001110f  test    ecx, ecx
0x180011111  jz      loc_180011393
0x180011117  mov     rax, [rbx+40h]
0x18001111b  mov     rax, [rax+8]
0x18001111f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011124  mov     rdi, rax
0x180011127  test    rax, rax
0x18001112a  jz      loc_1800112CC
0x180011130  mov     rcx, [rbx+70h]; hCryptMsg
0x180011134  lea     rax, [rsp+68h+arg_8]
0x180011139  mov     r9, rdi; pvData
0x18001113c  mov     [rsp+68h+pvPara], rax; pcbData
0x180011141  xor     r8d, r8d; dwIndex
0x180011144  mov     edx, 2; dwParamType
0x180011149  call    cs:__imp_CryptMsgGetParam
0x18001114f  test    eax, eax
0x180011151  jz      loc_180011298
0x180011157  mov     rax, [rbx+0E0h]
0x18001115e  cmp     [rax+18h], esi
0x180011161  jnz     loc_180011313
0x180011167  mov     eax, [rsp+68h+arg_8]
0x18001116b  lea     r8, [rsp+68h+pcbData]
0x180011170  mov     rdx, [rbx+0A0h]
0x180011177  mov     r9d, 0CAh
0x18001117d  mov     [rsp+68h+var_28], esi
0x180011181  add     rdx, 38h ; '8'
0x180011185  mov     [rsp+68h+var_30], eax
0x180011189  mov     ecx, 10000h
0x18001118e  mov     eax, [rbx+68h]
0x180011191  mov     [rsp+68h+var_38], rdi
0x180011196  mov     [rsp+68h+var_40], 7D3h
0x18001119f  mov     dword ptr [rsp+68h+pvPara], eax
0x1800111a3  call    TrustDecode
0x1800111a8  test    eax, eax
0x1800111aa  jz      loc_180011298
0x1800111b0  mov     rax, [rbx+0A0h]
0x1800111b7  mov     rcx, [rax+28h]
0x1800111bb  mov     rdx, [rcx+8]
0x1800111bf  mov     rax, [rdx]
0x1800111c2  sub     rax, cs:_gPESubject
0x1800111c9  jnz     short loc_1800111D6
0x1800111cb  mov     rax, [rdx+8]
0x1800111cf  sub     rax, cs:qword_180056D80
0x1800111d6  test    rax, rax
0x1800111d9  jnz     short loc_1800111E4
0x1800111db  cmp     [rcx+28h], esi
0x1800111de  ja      loc_1800113B5
0x1800111e4  mov     rax, [rbx+40h]
0x1800111e8  mov     rcx, rdi
0x1800111eb  mov     rax, [rax+10h]
0x1800111ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800111f4  mov     eax, 1
0x1800111f9  add     rsp, 50h
0x1800111fd  pop     rdi
0x1800111fe  pop     rsi
0x1800111ff  pop     rbx
0x180011200  retn
0x180011201  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011206  mov     rax, [rbx+8]
0x18001120a  cmp     dword ptr [rax+20h], 2
0x18001120e  jnz     short loc_1800111F4
0x180011210  mov     rax, [rbx+0A0h]
0x180011217  mov     rcx, [rax+28h]
0x18001121b  cmp     dword ptr [rcx+68h], 2
0x18001121f  jnz     short loc_1800111F4
0x180011221  mov     rdi, [rcx+70h]
0x180011225  test    rdi, rdi
0x180011228  jz      short loc_1800111F4
0x18001122a  mov     rax, [rdi+10h]
0x18001122e  test    rax, rax
0x180011231  jz      short loc_1800111F4
0x180011233  cmp     [rax+30h], rsi
0x180011237  jz      short loc_1800111F4
0x180011239  mov     rax, [rbx+40h]
0x18001123d  mov     ecx, 40h ; '@'
0x180011242  mov     rax, [rax+8]
0x180011246  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001124b  mov     rcx, rax
0x18001124e  mov     rax, [rbx+0A0h]
0x180011255  mov     [rax+38h], rcx
0x180011259  test    rcx, rcx
0x18001125c  jz      short loc_1800112CC
0x18001125e  mov     rcx, [rdi+10h]
0x180011262  mov     r8, [rcx+30h]
0x180011266  mov     rcx, [rbx+0A0h]
0x18001126d  movups  xmm0, xmmword ptr [r8]
0x180011271  mov     rdx, [rcx+38h]
0x180011275  movups  xmmword ptr [rdx], xmm0
0x180011278  movups  xmm1, xmmword ptr [r8+10h]
0x18001127d  movups  xmmword ptr [rdx+10h], xmm1
0x180011281  movups  xmm0, xmmword ptr [r8+20h]
0x180011286  movups  xmmword ptr [rdx+20h], xmm0
0x18001128a  movups  xmm1, xmmword ptr [r8+30h]
0x18001128f  movups  xmmword ptr [rdx+30h], xmm1
0x180011293  jmp     loc_1800111F4
0x180011298  mov     rax, [rbx+50h]
0x18001129c  mov     dword ptr [rax+84h], 8009200Dh
0x1800112a6  call    cs:__imp_GetLastError
0x1800112ac  mov     ecx, eax
0x1800112ae  mov     rax, [rbx+50h]
0x1800112b2  mov     [rax+2Ch], ecx
0x1800112b5  mov     rcx, rdi
0x1800112b8  mov     rax, [rbx+40h]
0x1800112bc  mov     rax, [rax+10h]
0x1800112c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800112c5  xor     eax, eax
0x1800112c7  jmp     loc_1800111F9
0x1800112cc  call    cs:__imp_GetLastError
0x1800112d2  mov     [rbx+30h], eax
0x1800112d5  mov     rax, [rbx+50h]
0x1800112d9  mov     dword ptr [rax+84h], 80096001h
0x1800112e3  xor     eax, eax
0x1800112e5  jmp     loc_1800111F9
0x1800112ea  call    cs:__imp_GetLastError
0x1800112f0  mov     [rbx+30h], eax
0x1800112f3  xor     edx, edx; dwFlags
0x1800112f5  mov     rax, [rbx+50h]
0x1800112f9  mov     rcx, rdi; hCertStore
0x1800112fc  mov     dword ptr [rax+80h], 80096001h
0x180011306  call    cs:__imp_CertCloseStore
0x18001130c  xor     eax, eax
0x18001130e  jmp     loc_1800111F9
0x180011313  mov     rax, [rbx+0A0h]
0x18001131a  mov     rcx, [rax+38h]; Block
0x18001131e  test    rcx, rcx
0x180011321  jz      loc_180011167
0x180011327  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001132c  mov     rax, [rbx+0A0h]
0x180011333  mov     [rax+38h], rsi
0x180011337  mov     rax, [rbx+0A0h]
0x18001133e  mov     [rax+38h], rsi
0x180011342  jmp     loc_180011167
0x180011347  mov     rax, [rbx+50h]
0x18001134b  mov     dword ptr [rax+84h], 8009200Dh
0x180011355  call    cs:__imp_GetLastError
0x18001135b  mov     ecx, eax
0x18001135d  mov     rax, [rbx+50h]
0x180011361  mov     [rax+28h], ecx
0x180011364  jmp     loc_1800112C5
0x180011369  call    cs:__imp_GetLastError
0x18001136f  mov     ecx, eax
0x180011371  mov     rax, [rbx+50h]
0x180011375  mov     [rax+28h], ecx
0x180011378  mov     rcx, rdi; Block
0x18001137b  mov     rax, [rbx+50h]
0x18001137f  mov     dword ptr [rax+84h], 8009200Dh
0x180011389  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001138e  jmp     loc_1800112C5
0x180011393  mov     rax, [rbx+50h]
0x180011397  mov     dword ptr [rax+84h], 8009200Dh
0x1800113a1  call    cs:__imp_GetLastError
0x1800113a7  mov     ecx, eax
0x1800113a9  mov     rax, [rbx+50h]
0x1800113ad  mov     [rax+2Ch], ecx
0x1800113b0  jmp     loc_1800112C5
0x1800113b5  mov     edx, [rsp+68h+arg_8]
0x1800113b9  lea     r8, [rsp+68h+arg_10]
0x1800113c1  mov     rcx, rdi
0x1800113c4  mov     [rsp+68h+arg_10], esi
0x1800113cb  call    cs:__imp_IsBufferCleanOfInvalidMarkers
0x1800113d1  test    eax, eax
0x1800113d3  jnz     loc_1800111E4
0x1800113d9  mov     rax, [rbx+0A0h]
0x1800113e0  mov     rcx, [rax+28h]
0x1800113e4  mov     eax, [rsp+68h+arg_10]
0x1800113eb  mov     [rcx+58h], eax
0x1800113ee  jmp     loc_1800111E4
0x1800113f3  call    cs:__imp_GetLastError
0x1800113f9  mov     rcx, [rbx+50h]
0x1800113fd  mov     [rcx+80h], eax
0x180011403  jmp     loc_1800112C5
```
