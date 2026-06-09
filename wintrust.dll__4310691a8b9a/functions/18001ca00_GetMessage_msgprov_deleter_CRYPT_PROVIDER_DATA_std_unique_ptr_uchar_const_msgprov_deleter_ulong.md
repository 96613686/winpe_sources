# GetMessage_<msgprov_deleter>(_CRYPT_PROVIDER_DATA *,std::unique_ptr<uchar const,msgprov_deleter> *,ulong *)

- ea: `0x18001ca00`
- end: `0x18001cd6e`
- name: `??$GetMessage_@Umsgprov_deleter@@@@YAHPEAU_CRYPT_PROVIDER_DATA@@PEAV?$unique_ptr@$$CBEUmsgprov_deleter@@@std@@PEAK@Z`
- size: `878`
- prototype: `__int64 __fastcall(struct _CRYPT_PROVIDER_DATA *, const BYTE **, DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180029250`

## callees

- `0x18001ca00`
- `0x18001cd74`
- `0x180022738`
- `0x180046d3c`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cbf9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cc68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ccd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cd0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cd48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cbf9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cc68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ccd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cd0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cd48`
- `CRYPT32!I_CryptGetDefaultCryptProv` at `0x18001cb4b`
- `CRYPT32!I_CryptGetDefaultCryptProv` at `0x18001cb4b`
- `CRYPT32!CryptMsgOpenToDecode` at `0x18001cb78`
- `CRYPT32!CryptMsgOpenToDecode` at `0x18001cb78`
- `CRYPT32!CryptMsgUpdate` at `0x18001cb9e`
- `CRYPT32!CryptMsgUpdate` at `0x18001cb9e`
- `CRYPT32!CryptMsgClose` at `0x18001cd2c`
- `CRYPT32!CryptMsgClose` at `0x18001cd2c`

## pseudocode

```c
__int64 __fastcall GetMessage_<msgprov_deleter>(struct _CRYPT_PROVIDER_DATA *a1, const BYTE **a2, DWORD *a3)
{
  DWORD v6; // r13d
  const BYTE *v7; // rbx
  DWORD dwUnionChoice; // ecx
  struct _PROVDATA_SIP *pPDSip; // rax
  struct SIP_DISPATCH_INFO_ *pSip; // rbp
  struct SIP_SUBJECTINFO_ *psSipSubjectInfo; // r15
  __int64 v12; // rax
  const BYTE *v13; // r14
  DWORD v14; // eax
  DWORD v15; // r15d
  DWORD v16; // ecx
  const BYTE *v17; // rax
  int v18; // eax
  __int64 v19; // rcx
  HCRYPTPROV_LEGACY hProv; // rbp
  HCRYPTMSG v21; // rax
  void *v22; // rbp
  DWORD v23; // eax
  DWORD v25; // ecx
  DWORD v26; // ecx
  struct _PROVDATA_SIP *v27; // rax
  _QWORD v28[9]; // [rsp+30h] [rbp-48h] BYREF
  DWORD cbData; // [rsp+80h] [rbp+8h] BYREF
  DWORD v30; // [rsp+88h] [rbp+10h] BYREF

  cbData = 0;
  v6 = 0;
  v30 = 0;
  v7 = a2[1];
  v28[1] = v7;
  v28[0] = 0;
  dwUnionChoice = a1->pWintrustData->dwUnionChoice;
  if ( dwUnionChoice == 3 || (v25 = dwUnionChoice - 1) == 0 )
  {
LABEL_2:
    pPDSip = a1->pPDSip;
    pSip = pPDSip->pSip;
    psSipSubjectInfo = pPDSip->psSipSubjectInfo;
    goto LABEL_3;
  }
  v26 = v25 - 1;
  if ( v26 )
  {
    if ( v26 != 4 )
    {
      a1->padwTrustStepErrors[32] = -2146762496;
      std::unique_ptr<unsigned char,msgprov_deleter>::_Delete(v28);
      return 0;
    }
    v6 = 4;
    goto LABEL_2;
  }
  if ( a1->hMsg )
    return 1;
  v27 = a1->pPDSip;
  pSip = v27->pCATSip;
  psSipSubjectInfo = v27->psSipCATSubjectInfo;
LABEL_3:
  ((void (__fastcall *)(struct SIP_SUBJECTINFO_ *, DWORD *, _QWORD, DWORD *, _QWORD))pSip->pfGet)(
    psSipSubjectInfo,
    &v30,
    0,
    &cbData,
    0);
  if ( !cbData )
  {
    a1->padwTrustStepErrors[3] = GetLastError();
    a1->padwTrustStepErrors[32] = -2146762496;
    return 0;
  }
  v12 = ((__int64 (*)(void))a1->psPfns->pfnAlloc)();
  v13 = (const BYTE *)v12;
  if ( !v12 )
  {
    a1->dwError = GetLastError();
    a1->padwTrustStepErrors[32] = -2146869247;
    goto LABEL_51;
  }
  v28[0] = v12;
  if ( !((unsigned int (__fastcall *)(struct SIP_SUBJECTINFO_ *, DWORD *, _QWORD, DWORD *, __int64))pSip->pfGet)(
          psSipSubjectInfo,
          &v30,
          0,
          &cbData,
          v12) )
  {
    a1->padwTrustStepErrors[3] = GetLastError();
    a1->padwTrustStepErrors[32] = -2146762496;
LABEL_51:
    std::unique_ptr<unsigned char,msgprov_deleter>::_Delete(v28);
    return 0;
  }
  v14 = v30;
  v15 = 0;
  a1->dwEncoding = v30;
  if ( (v14 & 0x10000) != 0 && cbData >= 2 )
  {
    if ( (*v13 & 0x1F) == 0x1F )
    {
      v17 = v13 + 1;
      v16 = 2;
      while ( *(char *)v17 < 0 )
      {
        if ( v16 >= cbData )
          goto LABEL_17;
        ++v17;
        ++v16;
      }
      if ( v16 >= cbData )
        goto LABEL_17;
    }
    else
    {
      v16 = 1;
      v17 = v13;
    }
    v18 = v17[1];
    if ( (_BYTE)v18 == 0x80 || (v18 & 0x80u) == 0 )
    {
      v19 = v16 + 1;
    }
    else
    {
      v19 = (v18 & 0xFFFFFF7F) + v16 + 1;
      if ( (unsigned int)v19 > cbData )
        goto LABEL_17;
    }
    if ( (_DWORD)v19 && (unsigned int)v19 < cbData && v13[v19] == 2 )
      v15 = 2;
  }
LABEL_17:
  hProv = a1->hProv;
  if ( hProv && hProv == I_CryptGetDefaultCryptProv(0) )
    hProv = 0;
  v21 = CryptMsgOpenToDecode(a1->dwEncoding, v6, v15, hProv, 0, 0);
  v22 = v21;
  if ( !v21 )
  {
    a1->padwTrustStepErrors[8] = GetLastError();
    a1->padwTrustStepErrors[32] = -2146885619;
    (*(void (__fastcall **)(const BYTE *))(*((_QWORD *)v7 + 8) + 16LL))(v13);
    return 0;
  }
  if ( !CryptMsgUpdate(v21, v13, cbData, 1) )
  {
    a1->padwTrustStepErrors[8] = GetLastError();
    a1->padwTrustStepErrors[32] = -2146885619;
LABEL_47:
    CryptMsgClose(v22);
    goto LABEL_51;
  }
  if ( a1->pWintrustData->dwUnionChoice == 6 && !(unsigned int)GetDetachedMessage_(v22, a1) )
    goto LABEL_47;
  v23 = cbData;
  a1->hMsg = v22;
  *a3 = v23;
  if ( v13 != *a2 )
  {
    std::unique_ptr<unsigned char const,msgprov_deleter>::_Delete(a2);
    *a2 = v13;
  }
  a2[1] = v7;
  return 1;
}

```

## disassembly

```asm
0x18001ca00  mov     rax, rsp
0x18001ca03  push    rbx
0x18001ca04  push    rbp
0x18001ca05  push    rsi
0x18001ca06  push    rdi
0x18001ca07  push    r12
0x18001ca09  push    r13
0x18001ca0b  push    r15
0x18001ca0d  sub     rsp, 40h
0x18001ca11  mov     rsi, rdx
0x18001ca14  mov     rdi, rcx
0x18001ca17  xor     edx, edx
0x18001ca19  mov     r12, r8
0x18001ca1c  mov     [rax+8], edx
0x18001ca1f  mov     r13d, edx
0x18001ca22  mov     [rax+10h], edx
0x18001ca25  mov     rbx, [rsi+8]
0x18001ca29  mov     [rax-40h], rbx
0x18001ca2d  mov     [rax-48h], rdx
0x18001ca31  mov     rax, [rcx+8]
0x18001ca35  mov     ecx, [rax+20h]
0x18001ca38  cmp     ecx, 3
0x18001ca3b  jnz     loc_18001CC25
0x18001ca41  mov     rax, [rdi+0A0h]
0x18001ca48  mov     rbp, [rax+18h]
0x18001ca4c  mov     r15, [rax+28h]
0x18001ca50  mov     rax, [rbp+10h]
0x18001ca54  lea     r9, [rsp+78h+cbData]
0x18001ca5c  mov     [rsp+78h+pRecipientInfo], rdx
0x18001ca61  xor     r8d, r8d
0x18001ca64  lea     rdx, [rsp+78h+arg_8]
0x18001ca6c  mov     rcx, r15
0x18001ca6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ca74  mov     ecx, [rsp+78h+cbData]
0x18001ca7b  test    ecx, ecx
0x18001ca7d  jz      loc_18001CBF9
0x18001ca83  mov     rax, [rdi+40h]
0x18001ca87  mov     [rsp+78h+arg_10], r14
0x18001ca8f  mov     rax, [rax+8]
0x18001ca93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ca98  mov     r14, rax
0x18001ca9b  test    rax, rax
0x18001ca9e  jz      loc_18001CD48
0x18001caa4  mov     [rsp+78h+var_48], rax
0x18001caa9  lea     r9, [rsp+78h+cbData]
0x18001cab1  mov     [rsp+78h+pRecipientInfo], rax
0x18001cab6  lea     rdx, [rsp+78h+arg_8]
0x18001cabe  mov     rax, [rbp+10h]
0x18001cac2  xor     r8d, r8d
0x18001cac5  mov     rcx, r15
0x18001cac8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cacd  test    eax, eax
0x18001cacf  jz      loc_18001CCD6
0x18001cad5  mov     eax, [rsp+78h+arg_8]
0x18001cadc  xor     r15d, r15d
0x18001cadf  mov     [rdi+68h], eax
0x18001cae2  bt      eax, 10h
0x18001cae6  jnb     short loc_18001CB40
0x18001cae8  mov     edx, [rsp+78h+cbData]
0x18001caef  cmp     edx, 2
0x18001caf2  jb      short loc_18001CB40
0x18001caf4  movzx   eax, byte ptr [r14]
0x18001caf8  mov     r8d, 2
0x18001cafe  and     al, 1Fh
0x18001cb00  cmp     al, 1Fh
0x18001cb02  jz      loc_18001CCF3
0x18001cb08  mov     ecx, 1
0x18001cb0d  mov     rax, r14
0x18001cb10  movzx   eax, byte ptr [rax+1]
0x18001cb14  cmp     al, 80h
0x18001cb16  jz      loc_18001CC4D
0x18001cb1c  test    al, al
0x18001cb1e  jns     loc_18001CC4D
0x18001cb24  btr     eax, 7
0x18001cb28  inc     ecx
0x18001cb2a  add     ecx, eax
0x18001cb2c  cmp     ecx, edx
0x18001cb2e  ja      short loc_18001CB40
0x18001cb30  test    ecx, ecx
0x18001cb32  jz      short loc_18001CB40
0x18001cb34  cmp     ecx, edx
0x18001cb36  jnb     short loc_18001CB40
0x18001cb38  cmp     [rcx+r14], r8b
0x18001cb3c  cmovz   r15d, r8d
0x18001cb40  mov     rbp, [rdi+28h]
0x18001cb44  test    rbp, rbp
0x18001cb47  jz      short loc_18001CB5A
0x18001cb49  xor     ecx, ecx
0x18001cb4b  call    cs:__imp_I_CryptGetDefaultCryptProv
0x18001cb51  xor     ecx, ecx
0x18001cb53  cmp     rbp, rax
0x18001cb56  cmovz   rbp, rcx
0x18001cb5a  mov     ecx, [rdi+68h]; dwMsgEncodingType
0x18001cb5d  mov     r9, rbp; hCryptProv
0x18001cb60  mov     [rsp+78h+pStreamInfo], 0; pStreamInfo
0x18001cb69  mov     r8d, r15d; dwMsgType
0x18001cb6c  mov     edx, r13d; dwFlags
0x18001cb6f  mov     [rsp+78h+pRecipientInfo], 0; pRecipientInfo
0x18001cb78  call    cs:__imp_CryptMsgOpenToDecode
0x18001cb7e  mov     rbp, rax
0x18001cb81  test    rax, rax
0x18001cb84  jz      loc_18001CC68
0x18001cb8a  mov     r8d, [rsp+78h+cbData]; cbData
0x18001cb92  mov     r9d, 1; fFinal
0x18001cb98  mov     rdx, r14; pbData
0x18001cb9b  mov     rcx, rax; hCryptMsg
0x18001cb9e  call    cs:__imp_CryptMsgUpdate
0x18001cba4  test    eax, eax
0x18001cba6  jz      loc_18001CD0E
0x18001cbac  mov     rax, [rdi+8]
0x18001cbb0  cmp     dword ptr [rax+20h], 6
0x18001cbb4  jz      loc_18001CD34
0x18001cbba  mov     eax, [rsp+78h+cbData]
0x18001cbc1  mov     [rdi+70h], rbp
0x18001cbc5  mov     [r12], eax
0x18001cbc9  cmp     r14, [rsi]
0x18001cbcc  jz      short loc_18001CBD9
0x18001cbce  mov     rcx, rsi
0x18001cbd1  call    ?_Delete@?$unique_ptr@$$CBEUmsgprov_deleter@@@std@@AEAAXXZ; std::unique_ptr<uchar const,msgprov_deleter>::_Delete(void)
0x18001cbd6  mov     [rsi], r14
0x18001cbd9  mov     [rsi+8], rbx
0x18001cbdd  mov     eax, 1
0x18001cbe2  mov     r14, [rsp+78h+arg_10]
0x18001cbea  add     rsp, 40h
0x18001cbee  pop     r15
0x18001cbf0  pop     r13
0x18001cbf2  pop     r12
0x18001cbf4  pop     rdi
0x18001cbf5  pop     rsi
0x18001cbf6  pop     rbp
0x18001cbf7  pop     rbx
0x18001cbf8  retn
0x18001cbf9  call    cs:__imp_GetLastError
0x18001cbff  mov     rcx, [rdi+50h]
0x18001cc03  mov     [rcx+0Ch], eax
0x18001cc06  mov     rax, [rdi+50h]
0x18001cc0a  mov     dword ptr [rax+80h], 800B0100h
0x18001cc14  xor     eax, eax
0x18001cc16  add     rsp, 40h
0x18001cc1a  pop     r15
0x18001cc1c  pop     r13
0x18001cc1e  pop     r12
0x18001cc20  pop     rdi
0x18001cc21  pop     rsi
0x18001cc22  pop     rbp
0x18001cc23  pop     rbx
0x18001cc24  retn
0x18001cc25  sub     ecx, 1
0x18001cc28  jz      loc_18001CA41
0x18001cc2e  sub     ecx, 1
0x18001cc31  jnz     short loc_18001CCA7
0x18001cc33  cmp     [rdi+70h], rdx
0x18001cc37  jz      short loc_18001CC54
0x18001cc39  mov     eax, 1
0x18001cc3e  add     rsp, 40h
0x18001cc42  pop     r15
0x18001cc44  pop     r13
0x18001cc46  pop     r12
0x18001cc48  pop     rdi
0x18001cc49  pop     rsi
0x18001cc4a  pop     rbp
0x18001cc4b  pop     rbx
0x18001cc4c  retn
0x18001cc4d  inc     ecx
0x18001cc4f  jmp     loc_18001CB30
0x18001cc54  mov     rax, [rdi+0A0h]
0x18001cc5b  mov     rbp, [rax+20h]
0x18001cc5f  mov     r15, [rax+30h]
0x18001cc63  jmp     loc_18001CA50
0x18001cc68  call    cs:__imp_GetLastError
0x18001cc6e  mov     rcx, [rdi+50h]
0x18001cc72  mov     [rcx+20h], eax
0x18001cc75  mov     rcx, r14
0x18001cc78  mov     rax, [rdi+50h]
0x18001cc7c  mov     dword ptr [rax+80h], 8009200Dh
0x18001cc86  mov     rax, [rbx+40h]
0x18001cc8a  mov     rax, [rax+10h]
0x18001cc8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc93  xor     eax, eax
0x18001cc95  jmp     loc_18001CBE2
0x18001cc9a  cmp     ecx, edx
0x18001cc9c  jb      loc_18001CB10
0x18001cca2  jmp     loc_18001CB40
0x18001cca7  cmp     ecx, 4
0x18001ccaa  jz      short loc_18001CCCB
0x18001ccac  mov     rax, [rdi+50h]
0x18001ccb0  lea     rcx, [rsp+78h+var_48]
0x18001ccb5  mov     dword ptr [rax+80h], 800B0100h
0x18001ccbf  call    ?_Delete@?$unique_ptr@EUmsgprov_deleter@@@std@@AEAAXXZ; std::unique_ptr<uchar,msgprov_deleter>::_Delete(void)
0x18001ccc4  xor     eax, eax
0x18001ccc6  jmp     loc_18001CBEA
0x18001cccb  mov     r13d, 4
0x18001ccd1  jmp     loc_18001CA41
0x18001ccd6  call    cs:__imp_GetLastError
0x18001ccdc  mov     rcx, [rdi+50h]
0x18001cce0  mov     [rcx+0Ch], eax
0x18001cce3  mov     rax, [rdi+50h]
0x18001cce7  mov     dword ptr [rax+80h], 800B0100h
0x18001ccf1  jmp     short loc_18001CD5F
0x18001ccf3  lea     rax, [r14+1]
0x18001ccf7  mov     ecx, r8d
0x18001ccfa  cmp     [rax], r15b
0x18001ccfd  jge     short loc_18001CC9A
0x18001ccff  cmp     ecx, edx
0x18001cd01  jnb     loc_18001CB40
0x18001cd07  inc     rax
0x18001cd0a  inc     ecx
0x18001cd0c  jmp     short loc_18001CCFA
0x18001cd0e  call    cs:__imp_GetLastError
0x18001cd14  mov     rcx, [rdi+50h]
0x18001cd18  mov     [rcx+20h], eax
0x18001cd1b  mov     rax, [rdi+50h]
0x18001cd1f  mov     dword ptr [rax+80h], 8009200Dh
0x18001cd29  mov     rcx, rbp; hCryptMsg
0x18001cd2c  call    cs:__imp_CryptMsgClose
0x18001cd32  jmp     short loc_18001CD5F
0x18001cd34  mov     rdx, rdi; struct _CRYPT_PROVIDER_DATA *
0x18001cd37  mov     rcx, rbp; hCryptMsg
0x18001cd3a  call    ?GetDetachedMessage_@@YAHPEAXPEAU_CRYPT_PROVIDER_DATA@@@Z; GetDetachedMessage_(void *,_CRYPT_PROVIDER_DATA *)
0x18001cd3f  test    eax, eax
0x18001cd41  jz      short loc_18001CD29
0x18001cd43  jmp     loc_18001CBBA
0x18001cd48  call    cs:__imp_GetLastError
0x18001cd4e  mov     [rdi+30h], eax
0x18001cd51  mov     rax, [rdi+50h]
0x18001cd55  mov     dword ptr [rax+80h], 80096001h
0x18001cd5f  lea     rcx, [rsp+78h+var_48]
0x18001cd64  call    ?_Delete@?$unique_ptr@EUmsgprov_deleter@@@std@@AEAAXXZ; std::unique_ptr<uchar,msgprov_deleter>::_Delete(void)
0x18001cd69  jmp     loc_18001CC93
```
