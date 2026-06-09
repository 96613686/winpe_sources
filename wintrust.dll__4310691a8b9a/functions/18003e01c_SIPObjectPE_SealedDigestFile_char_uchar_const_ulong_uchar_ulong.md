# SIPObjectPE_::SealedDigestFile(char *,uchar const *,ulong,uchar *,ulong *)

- ea: `0x18003e01c`
- end: `0x18003e379`
- name: `?SealedDigestFile@SIPObjectPE_@@AEAA_NPEADPEBEKPEAEPEAK@Z`
- size: `861`
- prototype: `bool __fastcall(HANDLE *this, char *, const unsigned __int8 *, unsigned int, unsigned __int8 *pbOutput, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x18003de50`

## callees

- `0x180016314`
- `0x180016640`
- `0x1800216a8`
- `0x180039f08`
- `0x18003d7d0`
- `0x18003e01c`
- `0x18003e380`
- `0x18003ebf8`
- `0x1800482ec`
- `0x18004de6a`
- `0x18004deb0`

## import_xrefs

- `msvcrt!free` at `0x18003e1f0`
- `msvcrt!free` at `0x18003e33e`
- `msvcrt!free` at `0x18003e1f0`
- `msvcrt!free` at `0x18003e33e`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18003e226`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18003e226`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003e08f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003e326`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003e08f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003e326`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e15a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e15a`
- `ntdll!RtlNtStatusToDosError` at `0x18003e29b`
- `ntdll!RtlNtStatusToDosError` at `0x18003e29b`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18003e0e2`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18003e0e2`
- `bcrypt!BCryptHashData` at `0x18003e251`
- `bcrypt!BCryptHashData` at `0x18003e26e`
- `bcrypt!BCryptHashData` at `0x18003e251`
- `bcrypt!BCryptHashData` at `0x18003e26e`
- `bcrypt!BCryptCreateHash` at `0x18003e1a8`
- `bcrypt!BCryptCreateHash` at `0x18003e1a8`
- `bcrypt!BCryptFinishHash` at `0x18003e28b`
- `bcrypt!BCryptFinishHash` at `0x18003e28b`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18003e31c`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18003e31c`
- `bcrypt!BCryptDestroyHash` at `0x18003e09f`
- `bcrypt!BCryptDestroyHash` at `0x18003e34e`
- `bcrypt!BCryptDestroyHash` at `0x18003e09f`
- `bcrypt!BCryptDestroyHash` at `0x18003e34e`

## pseudocode

```c
bool __fastcall SIPObjectPE_::SealedDigestFile(
        HANDLE *this,
        char *a2,
        const unsigned __int8 *a3,
        unsigned int a4,
        unsigned __int8 *pbOutput,
        unsigned int *a6)
{
  const WCHAR *v9; // rsi
  int Hash; // eax
  ULONG v12; // eax
  DWORD LastError; // eax
  __int64 v14; // rcx
  PUCHAR *v15; // rax
  PUCHAR v16; // rdx
  int v17; // eax
  bool v18; // bl
  DWORD dwErrCode; // [rsp+40h] [rbp-C0h] BYREF
  int v20; // [rsp+44h] [rbp-BCh] BYREF
  ULONG cbOutput; // [rsp+48h] [rbp-B8h] BYREF
  UCHAR pbInput[8]; // [rsp+50h] [rbp-B0h] BYREF
  PUCHAR v23; // [rsp+58h] [rbp-A8h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+60h] [rbp-A0h] BYREF
  void *Block; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v26[8]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v27[16]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v28; // [rsp+C0h] [rbp-40h]
  void *v29; // [rsp+C8h] [rbp-38h]
  unsigned int v30; // [rsp+D0h] [rbp-30h]
  BCRYPT_HASH_HANDLE hHash[2]; // [rsp+110h] [rbp+10h] BYREF
  UCHAR pbHashObject[512]; // [rsp+120h] [rbp+20h] BYREF
  int v33; // [rsp+320h] [rbp+220h]

  *(_OWORD *)hHash = 0;
  v33 = 0;
  v26[6] = hHash;
  v9 = I_OidToCngAlgId(a2);
  if ( !v9 )
  {
    SetLastError(0x80090008);
    if ( hHash[1] )
      BCryptDestroyHash(hHash[1]);
    return 0;
  }
  dwErrCode = 0;
  memset_0(v27, 0, 0x58u);
  *(_QWORD *)pbInput = 0;
  v23 = 0;
  phAlgorithm = 0;
  Hash = BCryptOpenAlgorithmProvider(&phAlgorithm, v9, 0, 0);
  v20 = Hash;
  if ( Hash < 0 )
    goto LABEL_28;
  cbOutput = 0;
  if ( HashRetrieveHashLength(phAlgorithm, (UCHAR *)&cbOutput) >= 0 )
  {
    if ( !a6 )
    {
      dwErrCode = 160;
      goto LABEL_35;
    }
    if ( pbOutput )
    {
      v12 = cbOutput;
      if ( *a6 < cbOutput )
      {
        dwErrCode = 14;
LABEL_34:
        *a6 = v12;
        goto LABEL_35;
      }
      if ( !(unsigned int)BigFileHeaderMap(this[1], (struct _BIG_FILE_MAP_INFO *)v27) )
      {
        LastError = GetLastError();
LABEL_29:
        dwErrCode = LastError;
        goto LABEL_35;
      }
      Hash = HashParsePEHeader(v29, v28, v30, (struct HASHLIB_CERT_INFO *)pbInput);
      v20 = Hash;
      if ( Hash < 0 )
        goto LABEL_28;
      Hash = BCryptCreateHash(phAlgorithm, &hHash[1], pbHashObject, 0x200u, 0, 0, 0);
      v20 = Hash;
      if ( Hash < 0 )
        goto LABEL_28;
      v15 = (PUCHAR *)SIPObject_::BuildWinCertificate(v14, (__int64)&Block, a3, a4);
      if ( &v23 != v15 )
      {
        v16 = *v15;
        *v15 = 0;
        std::unique_ptr<_WIN_CERTIFICATE,deleter<release::c_free::tag>>::reset(&v23, v16);
      }
      if ( Block )
        free(Block);
      if ( !v23 )
      {
        dwErrCode = 14;
        goto LABEL_35;
      }
      if ( *(_DWORD *)pbInput || *(_DWORD *)&pbInput[4] )
      {
        v26[0] = pbInput;
        v26[1] = v27;
        v26[2] = &v23;
        v26[3] = &v20;
        v26[4] = hHash;
        v26[5] = &dwErrCode;
        v17 = seh_invoke__lambda_664708497b1175ea3a57c95164b02304_(&dwErrCode, v26);
        if ( dwErrCode )
          goto LABEL_35;
        if ( !v17 )
        {
          dwErrCode = -2147418113;
          goto LABEL_35;
        }
      }
      else
      {
        *(_DWORD *)pbInput = (GetFileSize(this[1], 0) + 7) & 0xFFFFFFF8;
        *(_DWORD *)&pbInput[4] = *(_DWORD *)v23;
        Hash = BCryptHashData(hHash[1], pbInput, 8u, 0);
        v20 = Hash;
        if ( Hash < 0 )
          goto LABEL_28;
        Hash = BCryptHashData(hHash[1], v23, *(_DWORD *)v23, 0);
        v20 = Hash;
        if ( Hash < 0 )
          goto LABEL_28;
      }
      Hash = BCryptFinishHash(hHash[1], pbOutput, cbOutput, 0);
      v20 = Hash;
      if ( Hash < 0 )
      {
LABEL_28:
        LastError = RtlNtStatusToDosError(Hash);
        goto LABEL_29;
      }
    }
    v12 = cbOutput;
    goto LABEL_34;
  }
  dwErrCode = -2146893816;
LABEL_35:
  BigFileUnmap((struct _BIG_FILE_MAP_INFO *)v27);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  SetLastError(dwErrCode);
  v18 = dwErrCode == 0;
  if ( v23 )
    free(v23);
  if ( hHash[1] )
    BCryptDestroyHash(hHash[1]);
  return v18;
}

```

## disassembly

```asm
0x18003e01c  push    rbp
0x18003e01e  push    rbx
0x18003e01f  push    rsi
0x18003e020  push    rdi
0x18003e021  push    r12
0x18003e023  push    r13
0x18003e025  push    r14
0x18003e027  push    r15
0x18003e029  lea     rbp, [rsp-248h]
0x18003e031  sub     rsp, 348h
0x18003e038  mov     rax, cs:__security_cookie
0x18003e03f  xor     rax, rsp
0x18003e042  mov     [rbp+280h+var_50], rax
0x18003e049  mov     r12d, r9d
0x18003e04c  mov     r15, r8
0x18003e04f  mov     r14, rcx
0x18003e052  mov     rdi, [rbp+280h+pbOutput]
0x18003e059  mov     rbx, [rbp+280h+arg_28]
0x18003e060  xorps   xmm0, xmm0
0x18003e063  movdqa  xmmword ptr [rbp+280h+hHash], xmm0
0x18003e068  xor     r13d, r13d
0x18003e06b  mov     [rbp+280h+var_60], r13d
0x18003e072  lea     rax, [rbp+280h+hHash]
0x18003e076  mov     [rbp+280h+var_2E0], rax
0x18003e07a  mov     rcx, rdx; pvKey
0x18003e07d  call    ?I_OidToCngAlgId@@YAPEBGPEBD@Z; I_OidToCngAlgId(char const *)
0x18003e082  mov     rsi, rax
0x18003e085  test    rax, rax
0x18003e088  jnz     short loc_18003E0AC
0x18003e08a  mov     ecx, 80090008h; dwErrCode
0x18003e08f  call    cs:__imp_SetLastError
0x18003e095  nop
0x18003e096  mov     rcx, [rbp+280h+hHash+8]; hHash
0x18003e09a  test    rcx, rcx
0x18003e09d  jz      short loc_18003E0A5
0x18003e09f  call    cs:__imp_BCryptDestroyHash
0x18003e0a5  xor     al, al
0x18003e0a7  jmp     loc_18003E356
0x18003e0ac  mov     [rsp+380h+dwErrCode], r13d
0x18003e0b1  mov     [rsp+380h+var_33C], r13d
0x18003e0b6  xor     edx, edx; Val
0x18003e0b8  lea     r8d, [rdx+58h]; Size
0x18003e0bc  lea     rcx, [rbp+280h+var_2D0]; void *
0x18003e0c0  call    memset_0
0x18003e0c5  mov     qword ptr [rsp+380h+pbInput], r13
0x18003e0ca  mov     [rsp+380h+var_328], r13
0x18003e0cf  mov     [rsp+380h+phAlgorithm], r13
0x18003e0d4  xor     r9d, r9d; dwFlags
0x18003e0d7  xor     r8d, r8d; pszImplementation
0x18003e0da  mov     rdx, rsi; pszAlgId
0x18003e0dd  lea     rcx, [rsp+380h+phAlgorithm]; phAlgorithm
0x18003e0e2  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18003e0e8  mov     [rsp+380h+var_33C], eax
0x18003e0ec  test    eax, eax
0x18003e0ee  js      loc_18003E299
0x18003e0f4  mov     [rsp+380h+cbOutput], r13d
0x18003e0f9  lea     rdx, [rsp+380h+cbOutput]; unsigned int *
0x18003e0fe  mov     rcx, [rsp+380h+phAlgorithm]; void *
0x18003e103  call    ?HashRetrieveHashLength@@YAJPEAXPEAK@Z; HashRetrieveHashLength(void *,ulong *)
0x18003e108  test    eax, eax
0x18003e10a  jns     short loc_18003E119
0x18003e10c  mov     [rsp+380h+dwErrCode], 80090008h
0x18003e114  jmp     loc_18003E307
0x18003e119  test    rbx, rbx
0x18003e11c  jnz     short loc_18003E12B
0x18003e11e  mov     [rsp+380h+dwErrCode], 0A0h
0x18003e126  jmp     loc_18003E307
0x18003e12b  test    rdi, rdi
0x18003e12e  jz      loc_18003E301
0x18003e134  mov     eax, [rsp+380h+cbOutput]
0x18003e138  cmp     [rbx], eax
0x18003e13a  jnb     short loc_18003E149
0x18003e13c  mov     [rsp+380h+dwErrCode], 0Eh
0x18003e144  jmp     loc_18003E305
0x18003e149  lea     rdx, [rbp+280h+var_2D0]; struct _BIG_FILE_MAP_INFO *
0x18003e14d  mov     rcx, [r14+8]; hFile
0x18003e151  call    ?BigFileHeaderMap@@YAHPEAXPEAU_BIG_FILE_MAP_INFO@@@Z; BigFileHeaderMap(void *,_BIG_FILE_MAP_INFO *)
0x18003e156  test    eax, eax
0x18003e158  jnz     short loc_18003E165
0x18003e15a  call    cs:__imp_GetLastError
0x18003e160  jmp     loc_18003E2A1
0x18003e165  lea     r9, [rsp+380h+pbInput]; struct HASHLIB_CERT_INFO *
0x18003e16a  mov     r8d, [rbp+280h+var_2B0]; unsigned int
0x18003e16e  mov     edx, [rbp+280h+var_2C0]; unsigned int
0x18003e171  mov     rcx, [rbp+280h+var_2B8]; void *
0x18003e175  call    ?HashParsePEHeader@@YAJPEBXKKPEAUHASHLIB_CERT_INFO@@@Z; HashParsePEHeader(void const *,ulong,ulong,HASHLIB_CERT_INFO *)
0x18003e17a  mov     [rsp+380h+var_33C], eax
0x18003e17e  test    eax, eax
0x18003e180  js      loc_18003E299
0x18003e186  mov     [rsp+380h+dwFlags], r13d; dwFlags
0x18003e18b  mov     [rsp+380h+cbSecret], r13d; cbSecret
0x18003e190  mov     [rsp+380h+pbSecret], r13; pbSecret
0x18003e195  mov     r9d, 200h; cbHashObject
0x18003e19b  lea     r8, [rbp+280h+pbHashObject]; pbHashObject
0x18003e19f  lea     rdx, [rbp+280h+hHash+8]; phHash
0x18003e1a3  mov     rcx, [rsp+380h+phAlgorithm]; hAlgorithm
0x18003e1a8  call    cs:__imp_BCryptCreateHash
0x18003e1ae  mov     [rsp+380h+var_33C], eax
0x18003e1b2  test    eax, eax
0x18003e1b4  js      loc_18003E299
0x18003e1ba  mov     r9d, r12d
0x18003e1bd  mov     r8, r15
0x18003e1c0  lea     rdx, [rsp+380h+Block]
0x18003e1c5  call    ?BuildWinCertificate@SIPObject_@@IEAA?AV?$unique_ptr@U_WIN_CERTIFICATE@@U?$deleter@Utag@c_free@release@@@@@std@@PEBEK@Z; SIPObject_::BuildWinCertificate(uchar const *,ulong)
0x18003e1ca  nop
0x18003e1cb  lea     rcx, [rsp+380h+var_328]
0x18003e1d0  cmp     rcx, rax
0x18003e1d3  jz      short loc_18003E1E6
0x18003e1d5  mov     rdx, [rax]
0x18003e1d8  mov     [rax], r13
0x18003e1db  lea     rcx, [rsp+380h+var_328]
0x18003e1e0  call    ?reset@?$unique_ptr@U_WIN_CERTIFICATE@@U?$deleter@Utag@c_free@release@@@@@std@@QEAAXPEAU_WIN_CERTIFICATE@@@Z; std::unique_ptr<_WIN_CERTIFICATE,deleter<release::c_free::tag>>::reset(_WIN_CERTIFICATE *)
0x18003e1e5  nop
0x18003e1e6  mov     rcx, [rsp+380h+Block]; Block
0x18003e1eb  test    rcx, rcx
0x18003e1ee  jz      short loc_18003E1F6
0x18003e1f0  call    cs:__imp_free
0x18003e1f6  cmp     [rsp+380h+var_328], r13
0x18003e1fb  jnz     short loc_18003E20A
0x18003e1fd  mov     [rsp+380h+dwErrCode], 0Eh
0x18003e205  jmp     loc_18003E307
0x18003e20a  cmp     dword ptr [rsp+380h+pbInput], r13d
0x18003e20f  jnz     loc_18003E2A7
0x18003e215  cmp     dword ptr [rsp+380h+pbInput+4], r13d
0x18003e21a  jnz     loc_18003E2A7
0x18003e220  xor     edx, edx; lpFileSizeHigh
0x18003e222  mov     rcx, [r14+8]; hFile
0x18003e226  call    cs:__imp_GetFileSize
0x18003e22c  add     eax, 7
0x18003e22f  and     eax, 0FFFFFFF8h
0x18003e232  mov     dword ptr [rsp+380h+pbInput], eax
0x18003e236  mov     rax, [rsp+380h+var_328]
0x18003e23b  mov     ecx, [rax]
0x18003e23d  mov     dword ptr [rsp+380h+pbInput+4], ecx
0x18003e241  xor     r9d, r9d; dwFlags
0x18003e244  lea     r8d, [r9+8]; cbInput
0x18003e248  lea     rdx, [rsp+380h+pbInput]; pbInput
0x18003e24d  mov     rcx, [rbp+280h+hHash+8]; hHash
0x18003e251  call    cs:__imp_BCryptHashData
0x18003e257  mov     [rsp+380h+var_33C], eax
0x18003e25b  test    eax, eax
0x18003e25d  js      short loc_18003E299
0x18003e25f  xor     r9d, r9d; dwFlags
0x18003e262  mov     rdx, [rsp+380h+var_328]; pbInput
0x18003e267  mov     r8d, [rdx]; cbInput
0x18003e26a  mov     rcx, [rbp+280h+hHash+8]; hHash
0x18003e26e  call    cs:__imp_BCryptHashData
0x18003e274  mov     [rsp+380h+var_33C], eax
0x18003e278  test    eax, eax
0x18003e27a  js      short loc_18003E299
0x18003e27c  xor     r9d, r9d; dwFlags
0x18003e27f  mov     r8d, [rsp+380h+cbOutput]; cbOutput
0x18003e284  mov     rdx, rdi; pbOutput
0x18003e287  mov     rcx, [rbp+280h+hHash+8]; hHash
0x18003e28b  call    cs:__imp_BCryptFinishHash
0x18003e291  mov     [rsp+380h+var_33C], eax
0x18003e295  test    eax, eax
0x18003e297  jns     short loc_18003E301
0x18003e299  mov     ecx, eax; Status
0x18003e29b  call    cs:__imp_RtlNtStatusToDosError
0x18003e2a1  mov     [rsp+380h+dwErrCode], eax
0x18003e2a5  jmp     short loc_18003E307
0x18003e2a7  lea     rax, [rsp+380h+pbInput]
0x18003e2ac  mov     [rsp+380h+var_310], rax
0x18003e2b1  lea     rax, [rbp+280h+var_2D0]
0x18003e2b5  mov     [rsp+380h+var_308], rax
0x18003e2ba  lea     rax, [rsp+380h+var_328]
0x18003e2bf  mov     [rbp+280h+var_300], rax
0x18003e2c3  lea     rax, [rsp+380h+var_33C]
0x18003e2c8  mov     [rbp+280h+var_2F8], rax
0x18003e2cc  lea     rax, [rbp+280h+hHash]
0x18003e2d0  mov     [rbp+280h+var_2F0], rax
0x18003e2d4  lea     rax, [rsp+380h+dwErrCode]
0x18003e2d9  mov     [rbp+280h+var_2E8], rax
0x18003e2dd  lea     rdx, [rsp+380h+var_310]
0x18003e2e2  lea     rcx, [rsp+380h+dwErrCode]
0x18003e2e7  call    seh_invoke__lambda_664708497b1175ea3a57c95164b02304___; seh_invoke__lambda_664708497b1175ea3a57c95164b02304_
0x18003e2ec  cmp     [rsp+380h+dwErrCode], r13d
0x18003e2f1  jnz     short loc_18003E307
0x18003e2f3  test    eax, eax
0x18003e2f5  jnz     short loc_18003E27C
0x18003e2f7  mov     [rsp+380h+dwErrCode], 8000FFFFh
0x18003e2ff  jmp     short loc_18003E307
0x18003e301  mov     eax, [rsp+380h+cbOutput]
0x18003e305  mov     [rbx], eax
0x18003e307  lea     rcx, [rbp+280h+var_2D0]; struct _BIG_FILE_MAP_INFO *
0x18003e30b  call    ?BigFileUnmap@@YAXPEAU_BIG_FILE_MAP_INFO@@@Z; BigFileUnmap(_BIG_FILE_MAP_INFO *)
0x18003e310  mov     rcx, [rsp+380h+phAlgorithm]; hAlgorithm
0x18003e315  test    rcx, rcx
0x18003e318  jz      short loc_18003E322
0x18003e31a  xor     edx, edx; dwFlags
0x18003e31c  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18003e322  mov     ecx, [rsp+380h+dwErrCode]; dwErrCode
0x18003e326  call    cs:__imp_SetLastError
0x18003e32c  cmp     [rsp+380h+dwErrCode], r13d
0x18003e331  setz    bl
0x18003e334  mov     rcx, [rsp+380h+var_328]; Block
0x18003e339  test    rcx, rcx
0x18003e33c  jz      short loc_18003E345
0x18003e33e  call    cs:__imp_free
0x18003e344  nop
0x18003e345  mov     rcx, [rbp+280h+hHash+8]; hHash
0x18003e349  test    rcx, rcx
0x18003e34c  jz      short loc_18003E354
0x18003e34e  call    cs:__imp_BCryptDestroyHash
0x18003e354  mov     al, bl
0x18003e356  mov     rcx, [rbp+280h+var_50]
0x18003e35d  xor     rcx, rsp; StackCookie
0x18003e360  call    __security_check_cookie
0x18003e365  add     rsp, 348h
0x18003e36c  pop     r15
0x18003e36e  pop     r14
0x18003e370  pop     r13
0x18003e372  pop     r12
0x18003e374  pop     rdi
0x18003e375  pop     rsi
0x18003e376  pop     rbx
0x18003e377  pop     rbp
0x18003e378  retn
```
