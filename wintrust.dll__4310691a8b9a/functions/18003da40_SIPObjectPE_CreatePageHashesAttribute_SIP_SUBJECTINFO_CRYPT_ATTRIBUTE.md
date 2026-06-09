# SIPObjectPE_::CreatePageHashesAttribute(SIP_SUBJECTINFO_ *,_CRYPT_ATTRIBUTE *)

- ea: `0x18003da40`
- end: `0x18003dda9`
- name: `?CreatePageHashesAttribute@SIPObjectPE_@@IEAAHPEAUSIP_SUBJECTINFO_@@PEAU_CRYPT_ATTRIBUTE@@@Z`
- size: `873`
- prototype: `__int64 __fastcall(HANDLE *this, struct SIP_SUBJECTINFO_ *, struct _CRYPT_ATTRIBUTE *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18001c104`

## callees

- `0x180016314`
- `0x180016640`
- `0x1800216a8`
- `0x18003da40`
- `0x18003ddb0`
- `0x180048894`
- `0x18004de52`
- `0x18004de6a`
- `0x180051010`

## import_xrefs

- `msvcrt!free` at `0x18003dd6c`
- `msvcrt!free` at `0x18003dd6c`
- `msvcrt!malloc` at `0x18003dc3e`
- `msvcrt!malloc` at `0x18003dc9f`
- `msvcrt!malloc` at `0x18003dcd7`
- `msvcrt!malloc` at `0x18003dc3e`
- `msvcrt!malloc` at `0x18003dc9f`
- `msvcrt!malloc` at `0x18003dcd7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003dadb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003db14`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003dd12`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003dd87`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003dadb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003db14`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003dd12`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003dd87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dd25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dd25`
- `ntdll!RtlNtStatusToDosError` at `0x18003db00`
- `ntdll!RtlNtStatusToDosError` at `0x18003dbc6`
- `ntdll!RtlNtStatusToDosError` at `0x18003db00`
- `ntdll!RtlNtStatusToDosError` at `0x18003dbc6`
- `ntdll!RtlFreeHeap` at `0x18003dd63`
- `ntdll!RtlFreeHeap` at `0x18003dd63`
- `CRYPT32!CryptEncodeObject` at `0x18003dcc7`
- `CRYPT32!CryptEncodeObject` at `0x18003dd00`
- `CRYPT32!CryptEncodeObject` at `0x18003dcc7`
- `CRYPT32!CryptEncodeObject` at `0x18003dd00`
- `CRYPT32!CryptFindOIDInfo` at `0x18003dab3`
- `CRYPT32!CryptFindOIDInfo` at `0x18003dac9`
- `CRYPT32!CryptFindOIDInfo` at `0x18003dab3`
- `CRYPT32!CryptFindOIDInfo` at `0x18003dac9`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18003daf4`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18003daf4`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18003dd7e`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18003dd7e`

## pseudocode

```c
__int64 __fastcall SIPObjectPE_::CreatePageHashesAttribute(
        HANDLE *this,
        struct SIP_SUBJECTINFO_ *a2,
        struct _CRYPT_ATTRIBUTE *a3)
{
  char *v6; // r15
  unsigned int v7; // r14d
  PCCRYPT_OID_INFO OIDInfo; // rax
  DWORD v9; // ecx
  NTSTATUS v10; // eax
  signed int v11; // eax
  NTSTATUS v12; // ecx
  DWORD LastError; // r13d
  CHAR *v14; // rcx
  unsigned int v15; // eax
  size_t v16; // r12
  unsigned __int64 i; // rbx
  struct _CRYPTOAPI_BLOB *pcbEncoded; // rax
  PCRYPT_ATTR_BLOB rgValue; // rbx
  BYTE *pbData; // r9
  SIPObjectPE_ *v21; // rcx
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+48h] [rbp-B0h] BYREF
  PVOID P; // [rsp+50h] [rbp-A8h] BYREF
  __int64 v25; // [rsp+58h] [rbp-A0h]
  __int128 pvStructInfo; // [rsp+60h] [rbp-98h] BYREF
  _BYTE v27[4]; // [rsp+70h] [rbp-88h] BYREF
  signed int v28; // [rsp+74h] [rbp-84h]
  unsigned int v29[2]; // [rsp+80h] [rbp-78h]
  void *v30; // [rsp+88h] [rbp-70h]
  unsigned int v31; // [rsp+90h] [rbp-68h]
  unsigned int v32; // [rsp+108h] [rbp+10h] BYREF
  struct _CRYPT_ATTRIBUTE *v33; // [rsp+110h] [rbp+18h]
  unsigned int v34; // [rsp+118h] [rbp+20h] BYREF

  v33 = a3;
  v32 = 0;
  pvStructInfo = 0;
  P = 0;
  memset_0(v27, 0, 0x58u);
  *(_OWORD *)&a3->pszObjId = 0;
  a3->rgValue = 0;
  v6 = 0;
  v25 = 0;
  phAlgorithm = 0;
  v7 = 1;
  OIDInfo = CryptFindOIDInfo(1u, a2->DigestAlgorithm.pszObjId, 1u);
  if ( !OIDInfo )
  {
    OIDInfo = CryptFindOIDInfo(1u, a2->DigestAlgorithm.pszObjId, 4u);
    if ( !OIDInfo )
    {
      SetLastError(0x80090008);
      v9 = -2146893816;
LABEL_8:
      SetLastError(v9);
LABEL_28:
      LastError = GetLastError();
      if ( a3->rgValue )
        SIPObjectPE_::FreeSpcAttribute(v21, a3);
      v7 = 0;
      goto LABEL_31;
    }
  }
  v10 = BCryptOpenAlgorithmProvider(&phAlgorithm, *(LPCWSTR *)&OIDInfo[1].cbSize, 0, 0);
  if ( v10 )
  {
    v11 = RtlNtStatusToDosError(v10);
    if ( v11 > 0 )
      v11 = (unsigned __int16)v11 | 0x80070000;
LABEL_7:
    v9 = v11;
    goto LABEL_8;
  }
  if ( !(*((unsigned int (__fastcall **)(HANDLE *, struct SIP_SUBJECTINFO_ *, __int64))*this + 16))(
          this,
          a2,
          0x80000000LL) )
  {
    v9 = -2147024809;
    goto LABEL_8;
  }
  if ( !(unsigned int)BigFileHeaderMap(this[1], (struct _BIG_FILE_MAP_INFO *)v27) || *(__int64 *)v29 > 0xFFFFFFFFLL )
    goto LABEL_28;
  v12 = HashGeneratePageHashesEx(
          phAlgorithm,
          v30,
          v29[0],
          v31,
          BigFileHashMapViewOfFileCallbackPE,
          v27,
          &v32,
          (struct PAGE_HASH_V2 **)&P);
  if ( v12 < 0 )
  {
    v11 = v28;
    if ( !v28 )
    {
      v11 = RtlNtStatusToDosError(v12);
      if ( v11 > 0 )
        v11 = (unsigned __int16)v11 | 0x80070000;
    }
    goto LABEL_7;
  }
  v34 = 0;
  if ( HashRetrieveHashLength(phAlgorithm, &v34) )
    goto LABEL_28;
  LastError = 0;
  v14 = "1.3.6.1.4.1.311.2.3.1";
  v15 = v34;
  if ( v34 > 0x14 )
    v14 = "1.3.6.1.4.1.311.2.3.2";
  a3->pszObjId = v14;
  v16 = v15 + 4;
  v25 = v32 * (v15 + 4);
  v6 = (char *)malloc((unsigned int)v25);
  if ( !v6 )
    goto LABEL_28;
  for ( i = 0; i < v32; ++i )
    memcpy_0(&v6[i * v16], (char *)P + 68 * i, v16);
  LODWORD(pvStructInfo) = v25;
  *((_QWORD *)&pvStructInfo + 1) = v6;
  a3->cValue = 1;
  pcbEncoded = (struct _CRYPTOAPI_BLOB *)malloc(0x10u);
  a3->rgValue = pcbEncoded;
  if ( !pcbEncoded )
    goto LABEL_28;
  if ( !CryptEncodeObject(0x10001u, (LPCSTR)0x19, &pvStructInfo, 0, &pcbEncoded->cbData) )
    goto LABEL_28;
  rgValue = a3->rgValue;
  rgValue->pbData = (BYTE *)malloc(rgValue->cbData);
  pbData = a3->rgValue->pbData;
  if ( !pbData || !CryptEncodeObject(0x10001u, (LPCSTR)0x19, &pvStructInfo, pbData, &a3->rgValue->cbData) )
    goto LABEL_28;
LABEL_31:
  BigFileUnmap((struct _BIG_FILE_MAP_INFO *)v27);
  if ( P )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  free(v6);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  SetLastError(LastError);
  return v7;
}

```

## disassembly

```asm
0x18003da40  mov     rax, rsp
0x18003da43  mov     [rax+8], rbx
0x18003da47  mov     [rax+18h], r8
0x18003da4b  push    rsi
0x18003da4c  push    r12
0x18003da4e  push    r13
0x18003da50  push    r14
0x18003da52  push    r15
0x18003da54  sub     rsp, 0D0h
0x18003da5b  mov     rsi, r8
0x18003da5e  mov     r13, rdx
0x18003da61  mov     rbx, rcx
0x18003da64  mov     dword ptr [rax+10h], 0
0x18003da6b  xorps   xmm0, xmm0
0x18003da6e  movups  [rsp+0F8h+pvStructInfo], xmm0
0x18003da73  mov     [rsp+0F8h+P], 0
0x18003da7c  xor     edx, edx; Val
0x18003da7e  lea     r8d, [rdx+58h]; Size
0x18003da82  lea     rcx, [rsp+0F8h+var_88]; void *
0x18003da87  call    memset_0
0x18003da8c  xorps   xmm0, xmm0
0x18003da8f  xor     eax, eax
0x18003da91  movups  xmmword ptr [rsi], xmm0
0x18003da94  mov     [rsi+10h], rax
0x18003da98  xor     r15d, r15d
0x18003da9b  mov     [rsp+0F8h+var_A0], r15
0x18003daa0  mov     [rsp+0F8h+phAlgorithm], rax
0x18003daa5  lea     r14d, [rax+1]
0x18003daa9  mov     r8d, r14d; dwGroupId
0x18003daac  mov     rdx, [r13+38h]; pvKey
0x18003dab0  mov     ecx, r14d; dwKeyType
0x18003dab3  call    cs:__imp_CryptFindOIDInfo
0x18003dab9  test    rax, rax
0x18003dabc  jnz     short loc_18003DAE5
0x18003dabe  lea     r8d, [r15+4]; dwGroupId
0x18003dac2  mov     rdx, [r13+38h]; pvKey
0x18003dac6  mov     ecx, r14d; dwKeyType
0x18003dac9  call    cs:__imp_CryptFindOIDInfo
0x18003dacf  test    rax, rax
0x18003dad2  jnz     short loc_18003DAE5
0x18003dad4  mov     ebx, 80090008h
0x18003dad9  mov     ecx, ebx; dwErrCode
0x18003dadb  call    cs:__imp_SetLastError
0x18003dae1  mov     ecx, ebx
0x18003dae3  jmp     short loc_18003DB14
0x18003dae5  xor     r9d, r9d; dwFlags
0x18003dae8  xor     r8d, r8d; pszImplementation
0x18003daeb  mov     rdx, [rax+30h]; pszAlgId
0x18003daef  lea     rcx, [rsp+0F8h+phAlgorithm]; phAlgorithm
0x18003daf4  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18003dafa  test    eax, eax
0x18003dafc  jz      short loc_18003DB1F
0x18003dafe  mov     ecx, eax; Status
0x18003db00  call    cs:__imp_RtlNtStatusToDosError
0x18003db06  test    eax, eax
0x18003db08  jle     short loc_18003DB12
0x18003db0a  movzx   eax, ax
0x18003db0d  or      eax, 80070000h
0x18003db12  mov     ecx, eax; dwErrCode
0x18003db14  call    cs:__imp_SetLastError
0x18003db1a  jmp     loc_18003DD25
0x18003db1f  mov     rax, [rbx]
0x18003db22  mov     r8d, 80000000h
0x18003db28  mov     rdx, r13
0x18003db2b  mov     rcx, rbx
0x18003db2e  mov     rax, [rax+80h]
0x18003db35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003db3a  test    eax, eax
0x18003db3c  jnz     short loc_18003DB45
0x18003db3e  mov     ecx, 80070057h
0x18003db43  jmp     short loc_18003DB14
0x18003db45  lea     rdx, [rsp+0F8h+var_88]; struct _BIG_FILE_MAP_INFO *
0x18003db4a  mov     rcx, [rbx+8]; hFile
0x18003db4e  call    ?BigFileHeaderMap@@YAHPEAXPEAU_BIG_FILE_MAP_INFO@@@Z; BigFileHeaderMap(void *,_BIG_FILE_MAP_INFO *)
0x18003db53  test    eax, eax
0x18003db55  jz      loc_18003DD25
0x18003db5b  mov     eax, 0FFFFFFFFh
0x18003db60  mov     r8, qword ptr [rsp+0F8h+var_78]; unsigned int
0x18003db68  cmp     r8, rax
0x18003db6b  jg      loc_18003DD25
0x18003db71  lea     rax, [rsp+0F8h+P]
0x18003db76  mov     [rsp+0F8h+var_C0], rax; struct PAGE_HASH_V2 **
0x18003db7b  lea     rax, [rsp+0F8h+arg_8]
0x18003db83  mov     [rsp+0F8h+var_C8], rax; unsigned int *
0x18003db88  lea     rax, [rsp+0F8h+var_88]
0x18003db8d  mov     [rsp+0F8h+var_D0], rax; void *
0x18003db92  lea     rax, ?BigFileHashMapViewOfFileCallbackPE@@YAJPEAXKPEAKPEAPEAX1@Z; BigFileHashMapViewOfFileCallbackPE(void *,ulong,ulong *,void * *,ulong *)
0x18003db99  mov     [rsp+0F8h+pcbEncoded], rax; int (*)(void *, unsigned int, unsigned int *, void **, unsigned int *)
0x18003db9e  mov     r9d, [rsp+0F8h+var_68]; unsigned int
0x18003dba6  mov     rdx, [rsp+0F8h+var_70]; void *
0x18003dbae  mov     rcx, [rsp+0F8h+phAlgorithm]; void *
0x18003dbb3  call    ?HashGeneratePageHashesEx@@YAJPEAXPEBXKKP6AJ0KPEAKPEAPEAX2@Z02PEAPEAUPAGE_HASH_V2@@@Z; HashGeneratePageHashesEx(void *,void const *,ulong,ulong,long (*)(void *,ulong,ulong *,void * *,ulong *),void *,ulong *,PAGE_HASH_V2 * *)
0x18003dbb8  mov     ecx, eax; Status
0x18003dbba  test    eax, eax
0x18003dbbc  jns     short loc_18003DBE1
0x18003dbbe  mov     eax, [rsp+0F8h+var_84]
0x18003dbc2  test    eax, eax
0x18003dbc4  jnz     short loc_18003DBD8
0x18003dbc6  call    cs:__imp_RtlNtStatusToDosError
0x18003dbcc  test    eax, eax
0x18003dbce  jle     short loc_18003DBD8
0x18003dbd0  movzx   eax, ax
0x18003dbd3  or      eax, 80070000h
0x18003dbd8  mov     [rsp+0F8h+var_B8], eax
0x18003dbdc  jmp     loc_18003DB12
0x18003dbe1  mov     [rsp+0F8h+arg_18], 0
0x18003dbec  lea     rdx, [rsp+0F8h+arg_18]; unsigned int *
0x18003dbf4  mov     rcx, [rsp+0F8h+phAlgorithm]; void *
0x18003dbf9  call    ?HashRetrieveHashLength@@YAJPEAXPEAK@Z; HashRetrieveHashLength(void *,ulong *)
0x18003dbfe  test    eax, eax
0x18003dc00  jnz     loc_18003DD25
0x18003dc06  xor     r13d, r13d
0x18003dc09  lea     rcx, a136141311231; "1.3.6.1.4.1.311.2.3.1"
0x18003dc10  lea     rdx, a136141311232; "1.3.6.1.4.1.311.2.3.2"
0x18003dc17  mov     eax, [rsp+0F8h+arg_18]
0x18003dc1e  cmp     eax, 14h
0x18003dc21  cmova   rcx, rdx
0x18003dc25  mov     [rsi], rcx
0x18003dc28  lea     r12d, [rax+4]
0x18003dc2c  mov     eax, r12d
0x18003dc2f  imul    eax, [rsp+0F8h+arg_8]
0x18003dc37  mov     [rsp+0F8h+var_A0], rax
0x18003dc3c  mov     ecx, eax; Size
0x18003dc3e  call    cs:__imp_malloc
0x18003dc44  mov     r15, rax
0x18003dc47  test    rax, rax
0x18003dc4a  jz      loc_18003DD25
0x18003dc50  mov     eax, [rsp+0F8h+arg_8]
0x18003dc57  xor     ebx, ebx
0x18003dc59  test    rax, rax
0x18003dc5c  jz      short loc_18003DC88
0x18003dc5e  imul    rdx, rbx, 44h ; 'D'
0x18003dc62  add     rdx, [rsp+0F8h+P]; Src
0x18003dc67  mov     rcx, r12
0x18003dc6a  imul    rcx, rbx
0x18003dc6e  add     rcx, r15; void *
0x18003dc71  mov     r8, r12; Size
0x18003dc74  call    memcpy_0
0x18003dc79  add     rbx, r14
0x18003dc7c  mov     eax, [rsp+0F8h+arg_8]
0x18003dc83  cmp     rbx, rax
0x18003dc86  jb      short loc_18003DC5E
0x18003dc88  mov     rax, [rsp+0F8h+var_A0]
0x18003dc8d  mov     dword ptr [rsp+0F8h+pvStructInfo], eax
0x18003dc91  mov     qword ptr [rsp+0F8h+pvStructInfo+8], r15
0x18003dc96  mov     [rsi+8], r14d
0x18003dc9a  mov     ecx, 10h; Size
0x18003dc9f  call    cs:__imp_malloc
0x18003dca5  mov     [rsi+10h], rax
0x18003dca9  test    rax, rax
0x18003dcac  jz      short loc_18003DD25
0x18003dcae  mov     [rsp+0F8h+pcbEncoded], rax; pcbEncoded
0x18003dcb3  xor     r9d, r9d; pbEncoded
0x18003dcb6  lea     r8, [rsp+0F8h+pvStructInfo]; pvStructInfo
0x18003dcbb  lea     r12d, [r9+19h]
0x18003dcbf  mov     edx, r12d; lpszStructType
0x18003dcc2  mov     ecx, 10001h; dwCertEncodingType
0x18003dcc7  call    cs:__imp_CryptEncodeObject
0x18003dccd  test    eax, eax
0x18003dccf  jz      short loc_18003DD25
0x18003dcd1  mov     rbx, [rsi+10h]
0x18003dcd5  mov     ecx, [rbx]; Size
0x18003dcd7  call    cs:__imp_malloc
0x18003dcdd  mov     [rbx+8], rax
0x18003dce1  mov     rax, [rsi+10h]
0x18003dce5  mov     r9, [rax+8]; pbEncoded
0x18003dce9  test    r9, r9
0x18003dcec  jz      short loc_18003DD25
0x18003dcee  mov     [rsp+0F8h+pcbEncoded], rax; pcbEncoded
0x18003dcf3  lea     r8, [rsp+0F8h+pvStructInfo]; pvStructInfo
0x18003dcf8  mov     edx, r12d; lpszStructType
0x18003dcfb  mov     ecx, 10001h; dwCertEncodingType
0x18003dd00  call    cs:__imp_CryptEncodeObject
0x18003dd06  test    eax, eax
0x18003dd08  jz      short loc_18003DD25
0x18003dd0a  jmp     short loc_18003DD40
0x18003dd0c  mov     [rsp+0F8h+var_B8], eax
0x18003dd10  mov     ecx, eax; dwErrCode
0x18003dd12  call    cs:__imp_SetLastError
0x18003dd18  mov     rsi, [rsp+0F8h+arg_10]
0x18003dd20  mov     r15, [rsp+0F8h+var_A0]
0x18003dd25  call    cs:__imp_GetLastError
0x18003dd2b  mov     r13d, eax
0x18003dd2e  cmp     qword ptr [rsi+10h], 0
0x18003dd33  jz      short loc_18003DD3D
0x18003dd35  mov     rdx, rsi; struct _CRYPT_ATTRIBUTE *
0x18003dd38  call    ?FreeSpcAttribute@SIPObjectPE_@@IEAAXPEAU_CRYPT_ATTRIBUTE@@@Z; SIPObjectPE_::FreeSpcAttribute(_CRYPT_ATTRIBUTE *)
0x18003dd3d  xor     r14d, r14d
0x18003dd40  lea     rcx, [rsp+0F8h+var_88]; struct _BIG_FILE_MAP_INFO *
0x18003dd45  call    ?BigFileUnmap@@YAXPEAU_BIG_FILE_MAP_INFO@@@Z; BigFileUnmap(_BIG_FILE_MAP_INFO *)
0x18003dd4a  mov     r8, [rsp+0F8h+P]; P
0x18003dd4f  test    r8, r8
0x18003dd52  jz      short loc_18003DD69
0x18003dd54  mov     rcx, gs:60h
0x18003dd5d  xor     edx, edx; Flags
0x18003dd5f  mov     rcx, [rcx+30h]; HeapHandle
0x18003dd63  call    cs:__imp_RtlFreeHeap
0x18003dd69  mov     rcx, r15; Block
0x18003dd6c  call    cs:__imp_free
0x18003dd72  mov     rcx, [rsp+0F8h+phAlgorithm]; hAlgorithm
0x18003dd77  test    rcx, rcx
0x18003dd7a  jz      short loc_18003DD84
0x18003dd7c  xor     edx, edx; dwFlags
0x18003dd7e  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18003dd84  mov     ecx, r13d; dwErrCode
0x18003dd87  call    cs:__imp_SetLastError
0x18003dd8d  mov     eax, r14d
0x18003dd90  mov     rbx, [rsp+0F8h+arg_0]
0x18003dd98  add     rsp, 0D0h
0x18003dd9f  pop     r15
0x18003dda1  pop     r14
0x18003dda3  pop     r13
0x18003dda5  pop     r12
0x18003dda7  pop     rsi
0x18003dda8  retn
```
