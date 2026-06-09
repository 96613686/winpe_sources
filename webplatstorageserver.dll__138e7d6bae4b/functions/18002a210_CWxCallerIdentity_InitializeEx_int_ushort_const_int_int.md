# CWxCallerIdentity::InitializeEx(int,ushort const *,int,int)

- ea: `0x18002a210`
- end: `0x18002aa66`
- name: `?InitializeEx@CWxCallerIdentity@@QEAAJHPEBGHH@Z`
- size: `2134`
- prototype: `__int64 __fastcall(CWxCallerIdentity *this, __int64, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002a060`
- `0x18003d8a0`

## callees

- `0x180020ea0`
- `0x18002a210`
- `0x18002aa70`
- `0x18002aad8`
- `0x180046f20`
- `0x18004b4e0`
- `0x180080fb0`
- `0x180084259`
- `0x1800844c4`
- `0x1800b6064`
- `0x1800b75a0`
- `0x1800c5008`
- `0x1800c5208`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002a584`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002a584`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002a5f1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002a5f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a757`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a7c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a7f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a81a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a844`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a757`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a7c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a7f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a81a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a844`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18002a4a4`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18002a4a4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002a34d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002a3c9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002a480`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002a34d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002a3c9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002a480`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002a362`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002a362`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002a374`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002a374`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a647`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a647`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a6b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a6b3`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002a4d5`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002a4d5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWxCallerIdentity::InitializeEx(CWxCallerIdentity *this, __int64 a2, const unsigned __int16 *a3)
{
  const unsigned __int16 *v4; // rdi
  int AdjustedCallerToken; // eax
  __int64 v6; // rdx
  HANDLE v7; // rcx
  PSID v8; // r8
  HANDLE v9; // r12
  signed int PackageSid; // r14d
  const unsigned __int16 *v11; // r15
  int v12; // ebx
  PUCHAR SidSubAuthorityCount; // rax
  DWORD v14; // edi
  _WORD *v15; // r15
  _WORD *v16; // rcx
  __int64 v17; // rbx
  unsigned int v18; // ecx
  unsigned int v19; // ecx
  int v20; // eax
  int v21; // ecx
  int v22; // r14d
  __int64 v23; // rcx
  _WORD *v24; // rax
  _WORD *v25; // rsi
  unsigned __int16 *v26; // rdi
  void *v27; // rsi
  signed int v29; // eax
  signed int LastError; // eax
  signed int v31; // eax
  signed int v32; // eax
  signed int v33; // eax
  __int64 v34; // rdx
  __int64 v35; // rcx
  unsigned __int64 v36; // rdx
  unsigned int v37[2]; // [rsp+48h] [rbp-C0h] BYREF
  const unsigned __int16 *v38; // [rsp+50h] [rbp-B8h] BYREF
  const unsigned __int16 *v39; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v40; // [rsp+60h] [rbp-A8h]
  _QWORD v41[2]; // [rsp+68h] [rbp-A0h] BYREF
  HANDLE TokenHandle; // [rsp+78h] [rbp-90h] BYREF
  DWORD ReturnLength; // [rsp+80h] [rbp-88h] BYREF
  int v44; // [rsp+84h] [rbp-84h]
  __int64 v45; // [rsp+88h] [rbp-80h] BYREF
  PSID pSourceSid[2]; // [rsp+98h] [rbp-70h] BYREF
  __int128 v47; // [rsp+A8h] [rbp-60h]
  __int128 v48; // [rsp+B8h] [rbp-50h]
  __int128 v49; // [rsp+C8h] [rbp-40h]
  int v50; // [rsp+D8h] [rbp-30h]
  _OWORD pDestinationSid[4]; // [rsp+E8h] [rbp-20h] BYREF
  int v52; // [rsp+128h] [rbp+20h]
  _OWORD TokenInformation[7]; // [rsp+138h] [rbp+30h] BYREF

  v52 = 0;
  v4 = 0;
  TokenHandle = 0;
  v37[0] = 0;
  memset(pDestinationSid, 0, sizeof(pDestinationSid));
  v41[0] = &qword_1800D76F0;
  v41[1] = 0;
  ReturnLength = 0;
  v38 = 0;
  if ( (BYTE3(xmmword_180113B20) & 0x20) != 0 )
    WPP_SF_qSll(this, a2, a3, this);
  AdjustedCallerToken = WxGetAdjustedCallerToken(*((_DWORD *)this + 6), (int *)&ReturnLength, v37, &TokenHandle);
  v9 = TokenHandle;
  PackageSid = AdjustedCallerToken;
  if ( AdjustedCallerToken < 0 )
  {
    HIDWORD(TokenHandle) = 366;
    goto LABEL_53;
  }
  if ( *((_DWORD *)this + 6) )
    *((_DWORD *)this + 7) = ReturnLength;
  v39 = &qword_1800D76F0;
  v50 = 0;
  *(_OWORD *)pSourceSid = 0;
  v11 = &qword_1800D76F0;
  v47 = 0;
  v48 = 0;
  v40 = 0;
  v12 = 0;
  v49 = 0;
  HIDWORD(TokenHandle) = 0;
  memset(TokenInformation, 0, 108);
  ReturnLength = 108;
  if ( GetTokenInformation(v9, TokenIntegrityLevel, TokenInformation, 0x6Cu, &ReturnLength) )
  {
    PackageSid = 0;
    SidSubAuthorityCount = GetSidSubAuthorityCount(*(PSID *)&TokenInformation[0]);
    v14 = *GetSidSubAuthority(*(PSID *)&TokenInformation[0], (unsigned __int8)(*SidSubAuthorityCount - 1));
  }
  else
  {
    v14 = 4096;
    LastError = GetLastError();
    PackageSid = LastError;
    if ( LastError > 0 )
      PackageSid = (unsigned __int16)LastError | 0x80070000;
    HIDWORD(TokenHandle) = 307;
    if ( PackageSid >= 0 )
      PackageSid = -2147418113;
  }
  if ( PackageSid < 0 )
  {
    HIDWORD(TokenHandle) = 344;
LABEL_14:
    if ( PackageSid < 0 )
    {
      v4 = v38;
      HIDWORD(TokenHandle) = 159;
      goto LABEL_20;
    }
    ReturnLength = 0;
    goto LABEL_16;
  }
  if ( v14 < 0x2000 )
  {
    TokenHandle = 0;
    ReturnLength = 0;
    if ( GetTokenInformation(v9, TokenIsAppContainer, &ReturnLength, 4u, (PDWORD)&TokenHandle) )
    {
      PackageSid = 0;
    }
    else
    {
      v29 = GetLastError();
      PackageSid = v29;
      if ( v29 > 0 )
        PackageSid = (unsigned __int16)v29 | 0x80070000;
      HIDWORD(TokenHandle) = 158;
      if ( PackageSid >= 0 )
        PackageSid = -2147418113;
    }
    if ( PackageSid < 0 )
      HIDWORD(TokenHandle) = 357;
    goto LABEL_14;
  }
  PackageSid = 0;
  ReturnLength = 0;
  if ( !(unsigned __int8)IsGetPackageFullNamePresent() )
    goto LABEL_16;
  TokenHandle = 0;
  v45 = 0;
  v35 = (__int64)v9;
  if ( !v9 )
    v35 = -6;
  AppModelPolicy_GetPolicy_Internal(v35, v34, &ReturnLength, &v45, &TokenHandle);
  if ( ReturnLength != 1966081 )
  {
LABEL_16:
    v12 = 0;
    goto LABEL_17;
  }
  PackageSid = WxGetPackageSid(v9, v36, pSourceSid);
  if ( PackageSid < 0 )
  {
    v4 = v38;
    HIDWORD(TokenHandle) = 174;
    goto LABEL_20;
  }
  PackageSid = WxSIDToSIDString((struct _SID *)pSourceSid, (struct CWxString *)&v39);
  if ( PackageSid < 0 )
  {
    v4 = v38;
    HIDWORD(TokenHandle) = 177;
    goto LABEL_20;
  }
  v11 = v39;
  v12 = 1;
LABEL_17:
  v4 = v38;
  v39 = &qword_1800D76F0;
  v40 = 0;
  if ( v11 != &qword_1800D76F0 )
    v4 = v11;
  v38 = v4;
LABEL_20:
  CWxString::~CWxString((CWxString *)&v39);
  if ( PackageSid < 0 )
  {
    HIDWORD(TokenHandle) = 377;
    goto LABEL_53;
  }
  if ( v12 )
  {
    PackageSid = CWxString::Set((CWxCallerIdentity *)((char *)this + 8), v4);
    if ( PackageSid < 0 )
    {
      HIDWORD(TokenHandle) = 385;
      goto LABEL_53;
    }
    *((_DWORD *)this + 9) = 1;
    goto LABEL_52;
  }
  if ( v37[0] != 1 )
  {
    if ( v37[0] == 2 )
    {
      PackageSid = CWxString::Set((CWxCallerIdentity *)((char *)this + 8), L"L");
      if ( PackageSid < 0 )
      {
        HIDWORD(TokenHandle) = 418;
        goto LABEL_53;
      }
    }
    else
    {
      if ( v37[0] != 3 )
      {
        PackageSid = -2147418113;
        HIDWORD(TokenHandle) = 427;
        goto LABEL_53;
      }
      PackageSid = CWxString::Set((CWxCallerIdentity *)((char *)this + 8), L"M");
      if ( PackageSid < 0 )
      {
        HIDWORD(TokenHandle) = 422;
        goto LABEL_53;
      }
    }
LABEL_52:
    *((_DWORD *)this + 1) = v37[0];
    goto LABEL_53;
  }
  TokenHandle = (HANDLE)76;
  if ( GetTokenInformation(v9, TokenAppContainerSid, pSourceSid, 0x4Cu, (PDWORD)&TokenHandle) )
  {
    v8 = pSourceSid[0];
    if ( !pSourceSid[0] )
    {
      HIDWORD(TokenHandle) = 226;
      PackageSid = -2147418113;
      goto LABEL_113;
    }
    if ( CopySid(0x44u, pDestinationSid, pSourceSid[0]) )
    {
      PackageSid = 0;
    }
    else
    {
      v32 = GetLastError();
      PackageSid = v32;
      if ( v32 > 0 )
        PackageSid = (unsigned __int16)v32 | 0x80070000;
      HIDWORD(TokenHandle) = 228;
      if ( PackageSid >= 0 )
        PackageSid = -2147418113;
    }
  }
  else
  {
    v31 = GetLastError();
    PackageSid = v31;
    if ( v31 > 0 )
      PackageSid = (unsigned __int16)v31 | 0x80070000;
    HIDWORD(TokenHandle) = 224;
    if ( PackageSid >= 0 )
      PackageSid = -2147418113;
  }
  if ( PackageSid < 0 )
  {
LABEL_113:
    HIDWORD(TokenHandle) = 396;
    goto LABEL_53;
  }
  v44 = 0;
  TokenHandle = 0;
  if ( !ConvertSidToStringSidW(pDestinationSid, (LPWSTR *)&TokenHandle) )
  {
    v33 = GetLastError();
    PackageSid = v33;
    if ( v33 > 0 )
      PackageSid = (unsigned __int16)v33 | 0x80070000;
    v44 = 114;
    if ( PackageSid >= 0 )
      PackageSid = -2147418113;
    goto LABEL_49;
  }
  v15 = TokenHandle;
  if ( *((_DWORD *)this + 4) )
  {
    v16 = (_WORD *)*((_QWORD *)this + 1);
    *((_DWORD *)this + 4) = 0;
    *v16 = 0;
  }
  if ( !v15 )
    goto LABEL_61;
  v17 = -1;
  do
    ++v17;
  while ( v15[v17] );
  PackageSid = 0;
  if ( !(_DWORD)v17 )
    goto LABEL_48;
  v18 = v17 + *((_DWORD *)this + 4) + 1;
  if ( *((_DWORD *)this + 5) < v18 )
  {
    v19 = v18 + 2;
    v20 = 256;
    if ( v19 > 0x100 )
    {
      v6 = 1024;
      if ( v19 > 0x400 )
      {
        v20 = 4096;
        if ( v19 <= 0x1000 )
          v20 = 1024;
      }
    }
    else
    {
      v20 = 64;
    }
    v21 = -v20 & (v20 + v19 - 1);
    v22 = v21 - 1;
    if ( (unsigned int)(v21 - 1) <= 0xFFFFFFE )
    {
      v23 = (unsigned int)(2 * v21);
      HIDWORD(v45) = 0;
      if ( g_fWxHeapExtensionInitialized )
        v24 = (_WORD *)((__int64 (__fastcall *)(__int64))qword_180113768)(v23);
      else
        v24 = HeapAlloc(g_hWxProcessHeap, 0, (unsigned int)v23);
      v25 = v24;
      if ( !v24 )
      {
        HIDWORD(v45) = 52;
        PackageSid = -2147024882;
        v44 = 115;
        goto LABEL_48;
      }
      *v24 = 0;
      v26 = (unsigned __int16 *)*((_QWORD *)this + 1);
      memcpy_0(v24, v26, 2LL * *((unsigned int *)this + 4));
      v25[*((unsigned int *)this + 4)] = 0;
      *((_DWORD *)this + 5) = v22;
      *((_QWORD *)this + 1) = v25;
      PackageSid = 0;
      if ( v26 && v26 != &qword_1800D76F0 )
      {
        if ( g_fWxHeapExtensionInitialized )
          g_WxHeapExtensionInterfaces(v26);
        else
          HeapFree(g_hWxProcessHeap, 0, v26);
      }
      goto LABEL_47;
    }
LABEL_61:
    PackageSid = -2147024809;
    v44 = 115;
    goto LABEL_48;
  }
LABEL_47:
  v27 = (void *)(*((_QWORD *)this + 1) + 2LL * *((unsigned int *)this + 4));
  memcpy_0(v27, v15, 2LL * (unsigned int)v17);
  *((_WORD *)v27 + (unsigned int)v17) = 0;
  *((_DWORD *)this + 4) += v17;
LABEL_48:
  v4 = v38;
LABEL_49:
  v7 = TokenHandle;
  if ( TokenHandle )
  {
    LocalFree(TokenHandle);
    TokenHandle = 0;
  }
  if ( PackageSid >= 0 )
    goto LABEL_52;
  HIDWORD(TokenHandle) = 414;
LABEL_53:
  if ( (BYTE3(xmmword_180113B20) & 0x20) != 0 )
    WPP_SF_qd(v7, v6, v8, this, PackageSid);
  if ( v4 )
    WxFreeHeapEx((void **)&v38);
  CWxString::~CWxString((CWxString *)v41);
  if ( v9 )
    CloseHandle(v9);
  return (unsigned int)PackageSid;
}

```

## disassembly

```asm
0x18002a210  mov     r11, rsp
0x18002a213  push    rbp
0x18002a214  push    r12
0x18002a216  push    r14
0x18002a218  lea     rbp, [r11-0D8h]
0x18002a21f  sub     rsp, 1C0h
0x18002a226  mov     rax, cs:__security_cookie
0x18002a22d  xor     rax, rsp
0x18002a230  mov     [rbp+0D0h+var_30], rax
0x18002a237  mov     [r11+10h], rbx
0x18002a23b  xorps   xmm0, xmm0
0x18002a23e  mov     [r11+18h], rsi
0x18002a242  lea     rbx, qword_1800D76F0
0x18002a249  xor     esi, esi
0x18002a24b  mov     [r11+20h], rdi
0x18002a24f  xor     eax, eax
0x18002a251  mov     [r11-20h], r13
0x18002a255  mov     dword ptr [rsp+1D0h+TokenHandle+4], esi
0x18002a259  mov     r13, rcx
0x18002a25c  mov     [rbp+0D0h+var_B0], eax
0x18002a25f  mov     edi, esi
0x18002a261  mov     [rsp+1D0h+TokenHandle], rsi
0x18002a266  mov     [rsp+1D0h+var_190], esi
0x18002a26a  movups  [rbp+0D0h+pDestinationSid], xmm0
0x18002a26e  mov     [rsp+1D0h+var_170], rbx
0x18002a273  movups  [rbp+0D0h+var_E0], xmm0
0x18002a277  mov     [rsp+1D0h+var_168], rsi
0x18002a27c  movups  [rbp+0D0h+var_D0], xmm0
0x18002a280  mov     [rsp+1D0h+ReturnLength], esi
0x18002a284  movups  [rbp+0D0h+var_C0], xmm0
0x18002a288  mov     [rsp+1D0h+var_188], rsi
0x18002a28d  test    byte ptr cs:xmmword_180113B20+3, 20h
0x18002a294  jnz     loc_18002A869
0x18002a29a  mov     ecx, [r13+18h]; int
0x18002a29e  lea     r9, [rsp+1D0h+TokenHandle]; void **
0x18002a2a3  lea     r8, [rsp+1D0h+var_190]; unsigned int *
0x18002a2a8  lea     rdx, [rsp+1D0h+ReturnLength]; int *
0x18002a2ad  call    ?WxGetAdjustedCallerToken@@YAJHPEAHPEAKPEAPEAX@Z; WxGetAdjustedCallerToken(int,int *,ulong *,void * *)
0x18002a2b2  mov     r12, [rsp+1D0h+TokenHandle]
0x18002a2b7  mov     r14d, eax
0x18002a2ba  test    eax, eax
0x18002a2bc  js      loc_18002A5F9
0x18002a2c2  mov     [rsp+1D0h+var_20], r15
0x18002a2ca  cmp     [r13+18h], esi
0x18002a2ce  jnz     loc_18002A876
0x18002a2d4  xorps   xmm0, xmm0
0x18002a2d7  mov     dword ptr [rsp+1D0h+TokenHandle+4], esi
0x18002a2db  xor     eax, eax
0x18002a2dd  mov     [rsp+1D0h+var_180], rbx
0x18002a2e2  mov     [rbp+0D0h+var_100], eax
0x18002a2e5  lea     r8, [rbp+0D0h+TokenInformation]; TokenInformation
0x18002a2e9  movups  xmmword ptr [rbp+0D0h+pSourceSid], xmm0
0x18002a2ed  mov     r15, rbx
0x18002a2f0  mov     r9d, 6Ch ; 'l'; TokenInformationLength
0x18002a2f6  movups  [rbp+0D0h+var_130], xmm0
0x18002a2fa  mov     edx, 19h; TokenInformationClass
0x18002a2ff  mov     rcx, r12; TokenHandle
0x18002a302  movups  [rbp+0D0h+var_120], xmm0
0x18002a306  mov     [rsp+1D0h+var_178], rsi
0x18002a30b  mov     ebx, esi
0x18002a30d  movups  [rbp+0D0h+var_110], xmm0
0x18002a311  mov     dword ptr [rsp+1D0h+TokenHandle+4], esi
0x18002a315  mov     dword ptr [rsp+1D0h+TokenHandle+4], eax
0x18002a319  lea     rax, [rsp+1D0h+ReturnLength]
0x18002a31e  movups  xmmword ptr [rbp+0D0h+var_50], xmm0
0x18002a325  mov     [rsp+20h], rax; ReturnLength
0x18002a32a  movups  [rbp+0D0h+TokenInformation], xmm0
0x18002a32e  mov     [rsp+1D0h+ReturnLength], 6Ch ; 'l'
0x18002a336  movups  [rbp+0D0h+var_90], xmm0
0x18002a33a  movups  [rbp+0D0h+var_80], xmm0
0x18002a33e  movups  [rbp+0D0h+var_70], xmm0
0x18002a342  movups  [rbp+0D0h+var_60], xmm0
0x18002a346  movups  xmmword ptr [rbp+0D0h+var_50+0Ch], xmm0
0x18002a34d  call    cs:__imp_GetTokenInformation
0x18002a353  test    eax, eax
0x18002a355  jz      loc_18002A7C1
0x18002a35b  mov     rcx, qword ptr [rbp+0D0h+TokenInformation]; pSid
0x18002a35f  xor     r14d, r14d
0x18002a362  call    cs:__imp_GetSidSubAuthorityCount
0x18002a368  movzx   ecx, byte ptr [rax]
0x18002a36b  dec     cl
0x18002a36d  movzx   edx, cl; nSubAuthority
0x18002a370  mov     rcx, qword ptr [rbp+0D0h+TokenInformation]; pSid
0x18002a374  call    cs:__imp_GetSidSubAuthority
0x18002a37a  mov     edi, [rax]
0x18002a37c  test    r14d, r14d
0x18002a37f  js      loc_18002A781
0x18002a385  cmp     edi, 2000h
0x18002a38b  jnb     loc_18002A893
0x18002a391  cmp     edi, 1000h
0x18002a397  jb      short loc_18002A39E
0x18002a399  mov     esi, 2
0x18002a39e  xor     edi, edi
0x18002a3a0  lea     rax, [rsp+1D0h+TokenHandle]
0x18002a3a5  mov     r9d, 4; TokenInformationLength
0x18002a3ab  mov     dword ptr [rsp+1D0h+TokenHandle+4], edi
0x18002a3af  lea     r8, [rsp+1D0h+ReturnLength]; TokenInformation
0x18002a3b4  mov     dword ptr [rsp+1D0h+TokenHandle], edi
0x18002a3b8  mov     edx, 1Dh; TokenInformationClass
0x18002a3bd  mov     [rsp+1D0h+ReturnLength], edi
0x18002a3c1  mov     rcx, r12; TokenHandle
0x18002a3c4  mov     [rsp+20h], rax; ReturnLength
0x18002a3c9  call    cs:__imp_GetTokenInformation
0x18002a3cf  test    eax, eax
0x18002a3d1  jz      loc_18002A757
0x18002a3d7  cmp     [rsp+1D0h+ReturnLength], ebx
0x18002a3db  mov     r14d, edi
0x18002a3de  setnz   dil
0x18002a3e2  test    r14d, r14d
0x18002a3e5  js      loc_18002A78E
0x18002a3eb  test    edi, edi
0x18002a3ed  jz      short loc_18002A3F4
0x18002a3ef  mov     esi, 1
0x18002a3f4  test    r14d, r14d
0x18002a3f7  js      loc_18002A8AC
0x18002a3fd  mov     [rsp+1D0h+ReturnLength], ebx
0x18002a401  cmp     esi, 2
0x18002a404  ja      loc_18002A8C0
0x18002a40a  xor     esi, esi
0x18002a40c  mov     ebx, esi
0x18002a40e  mov     rdi, [rsp+1D0h+var_188]
0x18002a413  lea     rax, qword_1800D76F0
0x18002a41a  cmp     r15, rax
0x18002a41d  mov     [rsp+1D0h+var_180], rax
0x18002a422  mov     [rsp+1D0h+var_178], rsi
0x18002a427  cmovnz  rdi, r15
0x18002a42b  mov     [rsp+1D0h+var_188], rdi
0x18002a430  lea     rcx, [rsp+1D0h+var_180]; this
0x18002a435  call    ??1CWxString@@QEAA@XZ; CWxString::~CWxString(void)
0x18002a43a  test    r14d, r14d
0x18002a43d  js      loc_18002A6F6
0x18002a443  test    ebx, ebx
0x18002a445  jnz     loc_18002A96A
0x18002a44b  mov     eax, [rsp+1D0h+var_190]
0x18002a44f  cmp     eax, 1
0x18002a452  jnz     loc_18002A71D
0x18002a458  lea     rax, [rsp+1D0h+TokenHandle]
0x18002a45d  mov     dword ptr [rsp+1D0h+TokenHandle+4], esi
0x18002a461  mov     r9d, 4Ch ; 'L'; TokenInformationLength
0x18002a467  mov     [rsp+20h], rax; ReturnLength
0x18002a46c  lea     r8, [rbp+0D0h+pSourceSid]; TokenInformation
0x18002a470  mov     dword ptr [rsp+1D0h+TokenHandle], 4Ch ; 'L'
0x18002a478  mov     edx, 1Fh; TokenInformationClass
0x18002a47d  mov     rcx, r12; TokenHandle
0x18002a480  call    cs:__imp_GetTokenInformation
0x18002a486  test    eax, eax
0x18002a488  jz      loc_18002A7F0
0x18002a48e  mov     r8, [rbp+0D0h+pSourceSid]; pSourceSid
0x18002a492  test    r8, r8
0x18002a495  jz      loc_18002A9E2
0x18002a49b  lea     rdx, [rbp+0D0h+pDestinationSid]; pDestinationSid
0x18002a49f  mov     ecx, 44h ; 'D'; nDestinationSidLength
0x18002a4a4  call    cs:__imp_CopySid
0x18002a4aa  test    eax, eax
0x18002a4ac  jz      loc_18002A81A
0x18002a4b2  mov     r14d, esi
0x18002a4b5  mov     ebx, 8000FFFFh
0x18002a4ba  test    r14d, r14d
0x18002a4bd  js      loc_18002A9F0
0x18002a4c3  lea     rdx, [rsp+1D0h+TokenHandle]; StringSid
0x18002a4c8  mov     [rsp+1D0h+var_154], esi
0x18002a4cc  lea     rcx, [rbp+0D0h+pDestinationSid]; Sid
0x18002a4d0  mov     [rsp+1D0h+TokenHandle], rsi
0x18002a4d5  call    cs:__imp_ConvertSidToStringSidW
0x18002a4db  test    eax, eax
0x18002a4dd  jz      loc_18002A844
0x18002a4e3  cmp     dword ptr [r13+10h], 0
0x18002a4e8  mov     r15, [rsp+1D0h+TokenHandle]
0x18002a4ed  jz      short loc_18002A4FA
0x18002a4ef  mov     rcx, [r13+8]
0x18002a4f3  mov     [r13+10h], esi
0x18002a4f7  mov     [rcx], si
0x18002a4fa  test    r15, r15
0x18002a4fd  jz      loc_18002A6E3
0x18002a503  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18002a50a  nop     word ptr [rax+rax+00h]
0x18002a510  inc     rbx
0x18002a513  cmp     word ptr [r15+rbx*2], 0
0x18002a519  jnz     short loc_18002A510
0x18002a51b  mov     r14d, esi
0x18002a51e  test    ebx, ebx
0x18002a520  jz      loc_18002A6D8
0x18002a526  mov     ecx, [r13+10h]
0x18002a52a  inc     ecx
0x18002a52c  add     ecx, ebx
0x18002a52e  cmp     [r13+14h], ecx
0x18002a532  jnb     loc_18002A603
0x18002a538  add     ecx, 2
0x18002a53b  mov     eax, 100h
0x18002a540  cmp     ecx, eax
0x18002a542  ja      loc_18002AA1D
0x18002a548  mov     eax, 40h ; '@'
0x18002a54d  dec     ecx
0x18002a54f  add     ecx, eax
0x18002a551  neg     eax
0x18002a553  and     ecx, eax
0x18002a555  lea     r14d, [rcx-1]
0x18002a559  cmp     r14d, 0FFFFFFEh
0x18002a560  ja      loc_18002A6E3
0x18002a566  add     ecx, ecx
0x18002a568  mov     [rbp+0D0h+var_14C], esi
0x18002a56b  cmp     cs:?g_fWxHeapExtensionInitialized@@3HA, 0; int g_fWxHeapExtensionInitialized
0x18002a572  jnz     loc_18002AA39
0x18002a578  mov     r8d, ecx; dwBytes
0x18002a57b  xor     edx, edx; dwFlags
0x18002a57d  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x18002a584  call    cs:__imp_HeapAlloc
0x18002a58a  mov     rsi, rax
0x18002a58d  test    rax, rax
0x18002a590  jz      loc_18002A703
0x18002a596  xor     eax, eax
0x18002a598  mov     rcx, rsi; void *
0x18002a59b  mov     [rsi], ax
0x18002a59e  mov     rdi, [r13+8]
0x18002a5a2  mov     r8d, [r13+10h]
0x18002a5a6  mov     rdx, rdi; Src
0x18002a5a9  add     r8, r8; Size
0x18002a5ac  call    memcpy_0
0x18002a5b1  mov     ecx, [r13+10h]
0x18002a5b5  xor     eax, eax
0x18002a5b7  mov     [rsi+rcx*2], ax
0x18002a5bb  mov     [r13+14h], r14d
0x18002a5bf  mov     [r13+8], rsi
0x18002a5c3  xor     esi, esi
0x18002a5c5  mov     r14d, esi
0x18002a5c8  test    rdi, rdi
0x18002a5cb  jz      short loc_18002A603
0x18002a5cd  lea     rax, qword_1800D76F0
0x18002a5d4  cmp     rdi, rax
0x18002a5d7  jz      short loc_18002A603
0x18002a5d9  cmp     cs:?g_fWxHeapExtensionInitialized@@3HA, esi; int g_fWxHeapExtensionInitialized
0x18002a5df  jnz     loc_18002A7AD
0x18002a5e5  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x18002a5ec  mov     r8, rdi; lpMem
0x18002a5ef  xor     edx, edx; dwFlags
0x18002a5f1  call    cs:__imp_HeapFree
0x18002a5f7  jmp     short loc_18002A60C
0x18002a5f9  mov     dword ptr [rsp+1D0h+TokenHandle+4], 16Eh
0x18002a601  jmp     short loc_18002A66B
0x18002a603  test    r14d, r14d
0x18002a606  js      loc_18002A6E9
0x18002a60c  mov     ecx, [r13+10h]
0x18002a610  mov     rdx, r15; Src
0x18002a613  mov     rax, [r13+8]
0x18002a617  lea     rsi, [rax+rcx*2]
0x18002a61b  mov     eax, ebx
0x18002a61d  mov     rcx, rsi; void *
0x18002a620  lea     rdi, [rax+rax]
0x18002a624  mov     r8, rdi; Size
0x18002a627  call    memcpy_0
0x18002a62c  xor     eax, eax
0x18002a62e  mov     [rdi+rsi], ax
0x18002a632  add     [r13+10h], ebx
0x18002a636  mov     rdi, [rsp+1D0h+var_188]
0x18002a63b  xor     esi, esi
0x18002a63d  mov     rcx, [rsp+1D0h+TokenHandle]; hMem
0x18002a642  test    rcx, rcx
0x18002a645  jz      short loc_18002A652
0x18002a647  call    cs:__imp_LocalFree
0x18002a64d  mov     [rsp+1D0h+TokenHandle], rsi
0x18002a652  test    r14d, r14d
0x18002a655  js      loc_18002AA4A
0x18002a65b  mov     eax, [rsp+1D0h+var_190]
0x18002a65f  mov     [r13+4], eax
0x18002a663  mov     r15, [rsp+1D0h+var_20]
0x18002a66b  mov     rsi, [rsp+1D0h+arg_10]
0x18002a673  mov     rbx, [rsp+1D0h+arg_8]
0x18002a67b  test    byte ptr cs:xmmword_180113B20+3, 20h
0x18002a682  jnz     loc_18002A79B
0x18002a688  mov     r13, [rsp+1B8h]
0x18002a690  test    rdi, rdi
0x18002a693  mov     rdi, [rsp+1D0h+arg_18]
0x18002a69b  jnz     loc_18002AA57
0x18002a6a1  lea     rcx, [rsp+1D0h+var_170]; this
0x18002a6a6  call    ??1CWxString@@QEAA@XZ; CWxString::~CWxString(void)
0x18002a6ab  test    r12, r12
0x18002a6ae  jz      short loc_18002A6B9
0x18002a6b0  mov     rcx, r12; hObject
0x18002a6b3  call    cs:__imp_CloseHandle
0x18002a6b9  mov     eax, r14d
0x18002a6bc  mov     rcx, [rbp+0D0h+var_30]
0x18002a6c3  xor     rcx, rsp; StackCookie
0x18002a6c6  call    __security_check_cookie
0x18002a6cb  add     rsp, 1C0h
0x18002a6d2  pop     r14
0x18002a6d4  pop     r12
0x18002a6d6  pop     rbp
0x18002a6d7  retn
0x18002a6d8  test    r14d, r14d
0x18002a6db  jns     loc_18002A636
0x18002a6e1  jmp     short loc_18002A6E9
0x18002a6e3  mov     r14d, 80070057h
0x18002a6e9  mov     [rsp+1D0h+var_154], 73h ; 's'
0x18002a6f1  jmp     loc_18002A636
0x18002a6f6  mov     dword ptr [rsp+1D0h+TokenHandle+4], 179h
0x18002a6fe  jmp     loc_18002A663
0x18002a703  mov     [rbp+0D0h+var_14C], 34h ; '4'
0x18002a70a  mov     r14d, 8007000Eh
0x18002a710  mov     [rsp+1D0h+var_154], 73h ; 's'
0x18002a718  jmp     loc_18002A636
  ... truncated ...
```
