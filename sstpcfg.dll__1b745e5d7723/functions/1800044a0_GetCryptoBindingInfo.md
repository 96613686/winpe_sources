# GetCryptoBindingInfo

- ea: `0x1800044a0`
- end: `0x180004c28`
- name: `GetCryptoBindingInfo`
- size: `1928`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180005ea0`
- `0x180007450`

## callees

- `0x1800044a0`
- `0x18000a014`
- `0x18000a044`
- `0x18000acbc`
- `0x18000ae4e`
- `0x18000ae80`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004574`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004574`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004b7b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004b7b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004709`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800048f7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004ad7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004709`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800048f7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004ad7`
- `rtutils!RouterLogEventStringW` at `0x1800045ab`
- `rtutils!RouterLogEventStringW` at `0x1800048b2`
- `rtutils!RouterLogEventStringW` at `0x180004aa1`
- `rtutils!RouterLogEventStringW` at `0x1800045ab`
- `rtutils!RouterLogEventStringW` at `0x1800048b2`
- `rtutils!RouterLogEventStringW` at `0x180004aa1`

## string_xrefs

- `0x180004ad0`: `isHashConfiguredByAdmin`
- `0x180004550`: `System\CurrentControlSet\Services\SstpSvc\Parameters`
- `0x1800045f4`: `Unable to open the parameter store for SSTPSVC: %d`
- `0x18000466a`: `GetCryptoBindingInfo completes with %d`

## pseudocode

```c
__int64 __fastcall GetCryptoBindingInfo(
        __int64 a1,
        unsigned __int8 a2,
        bool *a3,
        char a4,
        _DWORD *a5,
        _OWORD *a6,
        _OWORD *a7)
{
  char v8; // r13
  LSTATUS dwErrorCode; // eax
  unsigned int v10; // ebx
  __int64 v11; // r8
  _QWORD *v12; // rcx
  unsigned __int8 v13; // r12
  unsigned int Value; // ebx
  __int64 v15; // r8
  __int128 v16; // xmm1
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  const wchar_t *v19; // r8
  unsigned int v20; // ebx
  __int64 v21; // r8
  _OWORD *v22; // rcx
  int v23; // eax
  _QWORD *v24; // rcx
  __int64 v25; // rdx
  const wchar_t *v26; // r8
  unsigned int v27; // eax
  __int64 v28; // r8
  __int64 cbData; // [rsp+44h] [rbp-BCh] BYREF
  BYTE v33[4]; // [rsp+4Ch] [rbp-B4h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  bool *v35; // [rsp+58h] [rbp-A8h]
  _OWORD *v36; // [rsp+60h] [rbp-A0h]
  _DWORD *v37; // [rsp+68h] [rbp-98h]
  BYTE v38[16]; // [rsp+70h] [rbp-90h] BYREF
  int v39; // [rsp+80h] [rbp-80h]
  BYTE Data[16]; // [rsp+88h] [rbp-78h] BYREF
  __int128 v41; // [rsp+98h] [rbp-68h]
  int v42; // [rsp+B0h] [rbp-50h] BYREF
  char v43[2044]; // [rsp+B4h] [rbp-4Ch] BYREF

  v37 = a5;
  v36 = a6;
  v8 = 0;
  v35 = a3;
  v39 = 0;
  v42 = 0;
  hKey = 0;
  cbData = 0;
  *(_DWORD *)v33 = 0;
  *(_OWORD *)v38 = 0;
  *(_OWORD *)Data = 0;
  v41 = 0;
  memset_0(v43, 0, sizeof(v43));
  if ( !a1 )
    a1 = -2147483646;
  dwErrorCode = RegOpenKeyExW((HKEY)a1, L"System\\CurrentControlSet\\Services\\SstpSvc\\Parameters", 0, 0x20019u, &hKey);
  v10 = dwErrorCode;
  if ( dwErrorCode )
  {
    RouterLogEventStringW(EventSource, 2u, 0x11u, 0, 0, dwErrorCode, 0);
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 150, v11, v10);
      v12 = WPP_GLOBAL_Control;
    }
    if ( (_QWORD)xmmword_1800146E0 )
    {
      LOWORD(v42) = 0;
      FormatRRASErrorString(&v42, L"Unable to open the parameter store for SSTPSVC: %d", v10);
      ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(gSstpCfgEtwContext, xmmword_1800146E0, &v42);
      v12 = WPP_GLOBAL_Control;
    }
    v13 = a2;
    goto LABEL_11;
  }
  if ( (a2 & 2) != 0 )
  {
    LODWORD(cbData) = 32;
    Value = RegQueryValueExW(hKey, L"SHA256CertificateHash", 0, (LPDWORD)&cbData + 1, Data, (LPDWORD)&cbData);
    if ( !Value )
    {
      v15 = (unsigned int)cbData;
      if ( cbData == 0x300000020LL )
      {
        v8 = 2;
        if ( a7 )
        {
          v16 = v41;
          *a7 = *(_OWORD *)Data;
          a7[1] = v16;
        }
        goto LABEL_49;
      }
      Value = 13;
      if ( HIDWORD(cbData) != 3 )
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 151);
          v17 = WPP_GLOBAL_Control;
        }
        v18 = xmmword_1800146E0;
        if ( !(_QWORD)xmmword_1800146E0 )
          goto LABEL_41;
        v19 = L"Invalid data type for sha256 cert hash";
        goto LABEL_39;
      }
      if ( (_DWORD)cbData != 32 )
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 152, (unsigned int)cbData, (unsigned int)cbData);
          v15 = (unsigned int)cbData;
          v17 = WPP_GLOBAL_Control;
        }
        if ( !(_QWORD)xmmword_1800146E0 )
          goto LABEL_41;
        LOWORD(v42) = 0;
        FormatRRASErrorString(&v42, L"Invalid sha256 cert hash length: %d", v15);
        v18 = xmmword_1800146E0;
        v19 = (const wchar_t *)&v42;
LABEL_39:
        ((void (__fastcall *)(__int64, __int64, const wchar_t *))gSstpCfgTemplateFunc)(gSstpCfgEtwContext, v18, v19);
      }
    }
    v17 = WPP_GLOBAL_Control;
LABEL_41:
    if ( v17 != &WPP_GLOBAL_Control && (*((_BYTE *)v17 + 28) & 0x40) != 0 && *((_BYTE *)v17 + 25) )
      WPP_SF_d(v17[2], 153, v15, Value);
    if ( (_QWORD)xmmword_1800146E0 )
    {
      LOWORD(v42) = 0;
      FormatRRASErrorString(&v42, L"Unable to query the SHA256 cert hash: %d", Value);
      ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(gSstpCfgEtwContext, xmmword_1800146E0, &v42);
    }
    if ( a4 )
      RouterLogEventStringW(EventSource, 2u, 0x12u, 0, 0, Value, 0);
  }
LABEL_49:
  v13 = a2;
  if ( (a2 & 1) != 0 )
  {
    LODWORD(cbData) = 20;
    v20 = RegQueryValueExW(hKey, L"SHA1CertificateHash", 0, (LPDWORD)&cbData + 1, v38, (LPDWORD)&cbData);
    if ( !v20 )
    {
      v21 = (unsigned int)cbData;
      if ( cbData == 0x300000014LL )
      {
        v22 = v36;
        v8 |= 1u;
        if ( v36 )
        {
          v23 = v39;
          *v36 = *(_OWORD *)v38;
          *((_DWORD *)v22 + 4) = v23;
        }
        goto LABEL_78;
      }
      v20 = 13;
      if ( HIDWORD(cbData) != 3 )
      {
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 154);
          v24 = WPP_GLOBAL_Control;
        }
        v25 = xmmword_1800146E0;
        if ( !(_QWORD)xmmword_1800146E0 )
          goto LABEL_70;
        v26 = L"Invalid data type for sha1 cert hash";
        goto LABEL_68;
      }
      if ( (_DWORD)cbData != 20 )
      {
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 155, (unsigned int)cbData, (unsigned int)cbData);
          v21 = (unsigned int)cbData;
          v24 = WPP_GLOBAL_Control;
        }
        if ( !(_QWORD)xmmword_1800146E0 )
          goto LABEL_70;
        LOWORD(v42) = 0;
        FormatRRASErrorString(&v42, L"Invalid sha1 cert hash length: %d", v21);
        v25 = xmmword_1800146E0;
        v26 = (const wchar_t *)&v42;
LABEL_68:
        ((void (__fastcall *)(__int64, __int64, const wchar_t *))gSstpCfgTemplateFunc)(gSstpCfgEtwContext, v25, v26);
      }
    }
    v24 = WPP_GLOBAL_Control;
LABEL_70:
    if ( v24 != &WPP_GLOBAL_Control && (*((_BYTE *)v24 + 28) & 0x40) != 0 && *((_BYTE *)v24 + 25) )
      WPP_SF_d(v24[2], 156, v21, v20);
    if ( (_QWORD)xmmword_1800146E0 )
    {
      LOWORD(v42) = 0;
      FormatRRASErrorString(&v42, L"Unable to query the SHA1 cert hash - bailing out : %d", v20);
      ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(gSstpCfgEtwContext, xmmword_1800146E0, &v42);
    }
    if ( a4 )
      RouterLogEventStringW(EventSource, 2u, 0x13u, 0, 0, v20, 0);
  }
LABEL_78:
  LODWORD(cbData) = 4;
  v27 = RegQueryValueExW(hKey, L"isHashConfiguredByAdmin", 0, (LPDWORD)&cbData + 1, v33, (LPDWORD)&cbData);
  v10 = v27;
  if ( v27 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 157, v28, v27);
    }
    if ( (_QWORD)xmmword_1800146E0 )
    {
      LOWORD(v42) = 0;
      FormatRRASErrorString(&v42, L"Unable to query the cert hash origin - bailing out : %d", v10);
      ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(gSstpCfgEtwContext, xmmword_1800146E0, &v42);
    }
    if ( v10 == 2 )
    {
      v10 = 0;
      if ( v35 )
        *v35 = 0;
    }
  }
  else if ( v35 )
  {
    *v35 = *(_DWORD *)v33 != 0;
  }
  RegCloseKey(hKey);
  v12 = WPP_GLOBAL_Control;
LABEL_11:
  if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 0x40) != 0 && *((_BYTE *)v12 + 25) >= 2u )
  {
    WPP_SF_d(v12[2], 158, v11, v10);
    v12 = WPP_GLOBAL_Control;
  }
  if ( (_QWORD)xmmword_1800146E0 )
  {
    LOWORD(v42) = 0;
    FormatRRASErrorString(&v42, L"GetCryptoBindingInfo completes with %d", v10);
    ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(gSstpCfgEtwContext, xmmword_1800146E0, &v42);
    v12 = WPP_GLOBAL_Control;
  }
  if ( v37 )
  {
    if ( v13 == v8 )
      *v37 = 0;
    else
      *v37 = 2 - (v8 != 0);
    v12 = WPP_GLOBAL_Control;
  }
  if ( !v10 )
  {
    if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 0x40) != 0 && *((_BYTE *)v12 + 25) >= 2u )
      WPP_SF_d(v12[2], 159, v11, v13);
    if ( (_QWORD)xmmword_1800146E0 )
    {
      LOWORD(v42) = 0;
      FormatRRASErrorString(&v42, L"HashAlgo Supported: 0x%x", v13);
      ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(gSstpCfgEtwContext, xmmword_1800146E0, &v42);
    }
  }
  return v10;
}

```

## disassembly

```asm
0x1800044a0  push    rbp
0x1800044a2  push    rbx
0x1800044a3  push    r12
0x1800044a5  push    r13
0x1800044a7  push    r14
0x1800044a9  lea     rbp, [rsp-7C0h]
0x1800044b1  sub     rsp, 8C0h
0x1800044b8  mov     rax, cs:__security_cookie
0x1800044bf  xor     rax, rsp
0x1800044c2  mov     [rbp+7E0h+var_30], rax
0x1800044c9  mov     rax, [rbp+7E0h+arg_20]
0x1800044d0  xorps   xmm1, xmm1
0x1800044d3  mov     r12, [rbp+7E0h+arg_30]
0x1800044da  mov     rbx, rcx
0x1800044dd  mov     [rsp+8E0h+var_878], rax
0x1800044e2  lea     rcx, [rbp+7E0h+var_82C]; void *
0x1800044e6  mov     rax, [rbp+7E0h+arg_28]
0x1800044ed  xorps   xmm0, xmm0
0x1800044f0  mov     [rsp+8E0h+var_880], rax
0x1800044f5  xor     r13b, r13b
0x1800044f8  xor     eax, eax
0x1800044fa  mov     [rsp+8E0h+var_888], r8
0x1800044ff  mov     [rsp+8E0h+var_8A0], dl
0x180004503  mov     r8d, 7FCh; Size
0x180004509  xor     edx, edx; Val
0x18000450b  mov     [rbp+7E0h+var_860], eax
0x18000450e  mov     [rbp+7E0h+var_830], eax
0x180004511  mov     [rsp+8E0h+var_89F], r9b
0x180004516  mov     [rsp+8E0h+hKey], 0
0x18000451f  mov     [rsp+8E0h+Type], 0
0x180004527  mov     [rsp+8E0h+cbData], 0
0x18000452f  mov     dword ptr [rsp+8E0h+var_894], 0
0x180004537  movups  xmmword ptr [rsp+8E0h+var_870], xmm0
0x18000453c  movups  xmmword ptr [rbp+7E0h+Data], xmm1
0x180004540  movups  [rbp+7E0h+var_848], xmm1
0x180004544  call    memset_0
0x180004549  mov     rax, 0FFFFFFFF80000002h
0x180004550  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\Ss"...
0x180004557  test    rbx, rbx
0x18000455a  mov     r9d, 20019h; samDesired
0x180004560  cmovz   rbx, rax
0x180004564  lea     rax, [rsp+8E0h+hKey]
0x180004569  mov     rcx, rbx; hKey
0x18000456c  mov     [rsp+8E0h+phkResult], rax; phkResult
0x180004571  xor     r8d, r8d; ulOptions
0x180004574  call    cs:__imp_RegOpenKeyExW
0x18000457a  mov     ebx, eax
0x18000457c  test    eax, eax
0x18000457e  jz      loc_1800046C8
0x180004584  mov     rcx, cs:EventSource; hLogHandle
0x18000458b  xor     r9d, r9d; dwSubStringCount
0x18000458e  mov     [rsp+8E0h+dwErrorIndex], 0; dwErrorIndex
0x180004596  mov     [rsp+8E0h+dwErrorCode], eax; dwErrorCode
0x18000459a  mov     [rsp+8E0h+phkResult], 0; plpszSubStringArray
0x1800045a3  lea     edx, [r9+2]; dwEventType
0x1800045a7  lea     r8d, [r9+11h]; dwMessageId
0x1800045ab  call    cs:__imp_RouterLogEventStringW
0x1800045b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800045b8  lea     r14, WPP_GLOBAL_Control
0x1800045bf  cmp     rcx, r14
0x1800045c2  jz      short loc_1800045E8
0x1800045c4  test    byte ptr [rcx+1Ch], 40h
0x1800045c8  jz      short loc_1800045E8
0x1800045ca  cmp     byte ptr [rcx+19h], 1
0x1800045ce  jb      short loc_1800045E8
0x1800045d0  mov     rcx, [rcx+10h]
0x1800045d4  mov     edx, 96h
0x1800045d9  mov     r9d, ebx
0x1800045dc  call    WPP_SF_d
0x1800045e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800045e8  cmp     qword ptr cs:xmmword_1800146E0, 0
0x1800045f0  jz      short loc_180004630
0x1800045f2  xor     eax, eax
0x1800045f4  lea     rdx, aUnableToOpenTh_1; "Unable to open the parameter store for "...
0x1800045fb  mov     r8d, ebx
0x1800045fe  mov     word ptr [rbp+7E0h+var_830], ax
0x180004602  lea     rcx, [rbp+7E0h+var_830]
0x180004606  call    FormatRRASErrorString
0x18000460b  mov     rdx, qword ptr cs:xmmword_1800146E0
0x180004612  lea     r8, [rbp+7E0h+var_830]
0x180004616  mov     rcx, cs:gSstpCfgEtwContext
0x18000461d  mov     rax, cs:gSstpCfgTemplateFunc
0x180004624  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004629  mov     rcx, cs:WPP_GLOBAL_Control
0x180004630  mov     r12b, [rsp+8E0h+var_8A0]
0x180004635  cmp     rcx, r14
0x180004638  jz      short loc_18000465E
0x18000463a  test    byte ptr [rcx+1Ch], 40h
0x18000463e  jz      short loc_18000465E
0x180004640  cmp     byte ptr [rcx+19h], 2
0x180004644  jb      short loc_18000465E
0x180004646  mov     rcx, [rcx+10h]
0x18000464a  mov     edx, 9Eh
0x18000464f  mov     r9d, ebx
0x180004652  call    WPP_SF_d
0x180004657  mov     rcx, cs:WPP_GLOBAL_Control
0x18000465e  cmp     qword ptr cs:xmmword_1800146E0, 0
0x180004666  jz      short loc_1800046A6
0x180004668  xor     eax, eax
0x18000466a  lea     rdx, aGetcryptobindi_1; "GetCryptoBindingInfo completes with %d"
0x180004671  mov     r8d, ebx
0x180004674  mov     word ptr [rbp+7E0h+var_830], ax
0x180004678  lea     rcx, [rbp+7E0h+var_830]
0x18000467c  call    FormatRRASErrorString
0x180004681  mov     rdx, qword ptr cs:xmmword_1800146E0
0x180004688  lea     r8, [rbp+7E0h+var_830]
0x18000468c  mov     rcx, cs:gSstpCfgEtwContext
0x180004693  mov     rax, cs:gSstpCfgTemplateFunc
0x18000469a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000469f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800046a6  mov     rdx, [rsp+8E0h+var_878]
0x1800046ab  test    rdx, rdx
0x1800046ae  jz      loc_180004B9E
0x1800046b4  cmp     r12b, r13b
0x1800046b7  jnz     loc_180004B8D
0x1800046bd  mov     dword ptr [rdx], 0
0x1800046c3  jmp     loc_180004B97
0x1800046c8  test    [rsp+8E0h+var_8A0], 2
0x1800046cd  lea     r14, WPP_GLOBAL_Control
0x1800046d4  jz      loc_1800048B8
0x1800046da  mov     rcx, [rsp+8E0h+hKey]; hKey
0x1800046df  lea     rax, [rsp+8E0h+cbData]
0x1800046e4  mov     qword ptr [rsp+8E0h+dwErrorCode], rax; lpcbData
0x1800046e9  lea     r9, [rsp+8E0h+Type]; lpType
0x1800046ee  lea     rax, [rbp+7E0h+Data]
0x1800046f2  mov     [rsp+8E0h+cbData], 20h ; ' '
0x1800046fa  xor     r8d, r8d; lpReserved
0x1800046fd  mov     [rsp+8E0h+phkResult], rax; lpData
0x180004702  lea     rdx, aSha256certific; "SHA256CertificateHash"
0x180004709  call    cs:__imp_RegQueryValueExW
0x18000470f  mov     ebx, eax
0x180004711  test    eax, eax
0x180004713  jnz     loc_18000481A
0x180004719  cmp     [rsp+8E0h+Type], 3
0x18000471e  mov     r8d, [rsp+8E0h+cbData]
0x180004723  jnz     short loc_18000474F
0x180004725  cmp     r8d, 20h ; ' '
0x180004729  jnz     short loc_18000474F
0x18000472b  mov     r13b, 2
0x18000472e  test    r12, r12
0x180004731  jz      loc_1800048B8
0x180004737  movups  xmm0, xmmword ptr [rbp+7E0h+Data]
0x18000473b  movups  xmm1, [rbp+7E0h+var_848]
0x18000473f  movups  xmmword ptr [r12], xmm0
0x180004744  movups  xmmword ptr [r12+10h], xmm1
0x18000474a  jmp     loc_1800048B8
0x18000474f  cmp     [rsp+8E0h+Type], 3
0x180004754  mov     ebx, 0Dh
0x180004759  jz      short loc_1800047A1
0x18000475b  mov     rcx, cs:WPP_GLOBAL_Control
0x180004762  cmp     rcx, r14
0x180004765  jz      short loc_180004788
0x180004767  test    byte ptr [rcx+1Ch], 40h
0x18000476b  jz      short loc_180004788
0x18000476d  cmp     byte ptr [rcx+19h], 1
0x180004771  jb      short loc_180004788
0x180004773  mov     rcx, [rcx+10h]
0x180004777  mov     edx, 97h
0x18000477c  call    WPP_SF_
0x180004781  mov     rcx, cs:WPP_GLOBAL_Control
0x180004788  mov     rdx, qword ptr cs:xmmword_1800146E0
0x18000478f  test    rdx, rdx
0x180004792  jz      loc_180004821
0x180004798  lea     r8, aInvalidDataTyp; "Invalid data type for sha256 cert hash"
0x18000479f  jmp     short loc_180004807
0x1800047a1  cmp     r8d, 20h ; ' '
0x1800047a5  jz      short loc_18000481A
0x1800047a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800047ae  cmp     rcx, r14
0x1800047b1  jz      short loc_1800047DC
0x1800047b3  test    byte ptr [rcx+1Ch], 40h
0x1800047b7  jz      short loc_1800047DC
0x1800047b9  cmp     byte ptr [rcx+19h], 1
0x1800047bd  jb      short loc_1800047DC
0x1800047bf  mov     rcx, [rcx+10h]
0x1800047c3  mov     edx, 98h
0x1800047c8  mov     r9d, r8d
0x1800047cb  call    WPP_SF_d
0x1800047d0  mov     r8d, [rsp+8E0h+cbData]
0x1800047d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800047dc  cmp     qword ptr cs:xmmword_1800146E0, 0
0x1800047e4  jz      short loc_180004821
0x1800047e6  xor     eax, eax
0x1800047e8  lea     rdx, aInvalidSha256C; "Invalid sha256 cert hash length: %d"
0x1800047ef  lea     rcx, [rbp+7E0h+var_830]
0x1800047f3  mov     word ptr [rbp+7E0h+var_830], ax
0x1800047f7  call    FormatRRASErrorString
0x1800047fc  mov     rdx, qword ptr cs:xmmword_1800146E0
0x180004803  lea     r8, [rbp+7E0h+var_830]
0x180004807  mov     rcx, cs:gSstpCfgEtwContext
0x18000480e  mov     rax, cs:gSstpCfgTemplateFunc
0x180004815  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000481a  mov     rcx, cs:WPP_GLOBAL_Control
0x180004821  cmp     rcx, r14
0x180004824  jz      short loc_180004843
0x180004826  test    byte ptr [rcx+1Ch], 40h
0x18000482a  jz      short loc_180004843
0x18000482c  cmp     byte ptr [rcx+19h], 1
0x180004830  jb      short loc_180004843
0x180004832  mov     rcx, [rcx+10h]
0x180004836  mov     edx, 99h
0x18000483b  mov     r9d, ebx
0x18000483e  call    WPP_SF_d
0x180004843  cmp     qword ptr cs:xmmword_1800146E0, 0
0x18000484b  jz      short loc_180004884
0x18000484d  xor     eax, eax
0x18000484f  lea     rdx, aUnableToQueryT_2; "Unable to query the SHA256 cert hash: %"...
0x180004856  mov     r8d, ebx
0x180004859  mov     word ptr [rbp+7E0h+var_830], ax
0x18000485d  lea     rcx, [rbp+7E0h+var_830]
0x180004861  call    FormatRRASErrorString
0x180004866  mov     rdx, qword ptr cs:xmmword_1800146E0
0x18000486d  lea     r8, [rbp+7E0h+var_830]
0x180004871  mov     rcx, cs:gSstpCfgEtwContext
0x180004878  mov     rax, cs:gSstpCfgTemplateFunc
0x18000487f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004884  cmp     [rsp+8E0h+var_89F], r13b
0x180004889  jz      short loc_1800048B8
0x18000488b  mov     rcx, cs:EventSource; hLogHandle
0x180004892  xor     r9d, r9d; dwSubStringCount
0x180004895  mov     [rsp+8E0h+dwErrorIndex], 0; dwErrorIndex
0x18000489d  mov     [rsp+8E0h+dwErrorCode], ebx; dwErrorCode
0x1800048a1  mov     [rsp+8E0h+phkResult], 0; plpszSubStringArray
0x1800048aa  lea     edx, [r9+2]; dwEventType
0x1800048ae  lea     r8d, [r9+12h]; dwMessageId
0x1800048b2  call    cs:__imp_RouterLogEventStringW
0x1800048b8  mov     r12b, [rsp+8E0h+var_8A0]
0x1800048bd  test    r12b, 1
0x1800048c1  jz      loc_180004AA7
0x1800048c7  mov     rcx, [rsp+8E0h+hKey]; hKey
0x1800048cc  lea     rax, [rsp+8E0h+cbData]
0x1800048d1  mov     qword ptr [rsp+8E0h+dwErrorCode], rax; lpcbData
0x1800048d6  lea     r9, [rsp+8E0h+Type]; lpType
0x1800048db  lea     rax, [rsp+8E0h+var_870]
0x1800048e0  mov     [rsp+8E0h+cbData], 14h
0x1800048e8  xor     r8d, r8d; lpReserved
0x1800048eb  mov     [rsp+8E0h+phkResult], rax; lpData
0x1800048f0  lea     rdx, aSha1certificat; "SHA1CertificateHash"
0x1800048f7  call    cs:__imp_RegQueryValueExW
0x1800048fd  mov     ebx, eax
0x1800048ff  test    eax, eax
0x180004901  jnz     loc_180004A09
0x180004907  cmp     [rsp+8E0h+Type], 3
0x18000490c  mov     r8d, [rsp+8E0h+cbData]
0x180004911  jnz     short loc_18000493E
0x180004913  cmp     r8d, 14h
0x180004917  jnz     short loc_18000493E
0x180004919  mov     rcx, [rsp+8E0h+var_880]
0x18000491e  or      r13b, 1
0x180004922  test    rcx, rcx
0x180004925  jz      loc_180004AA7
0x18000492b  movups  xmm0, xmmword ptr [rsp+8E0h+var_870]
0x180004930  mov     eax, [rbp+7E0h+var_860]
0x180004933  movups  xmmword ptr [rcx], xmm0
0x180004936  mov     [rcx+10h], eax
0x180004939  jmp     loc_180004AA7
0x18000493e  cmp     [rsp+8E0h+Type], 3
0x180004943  mov     ebx, 0Dh
0x180004948  jz      short loc_180004990
0x18000494a  mov     rcx, cs:WPP_GLOBAL_Control
0x180004951  cmp     rcx, r14
0x180004954  jz      short loc_180004977
0x180004956  test    byte ptr [rcx+1Ch], 40h
0x18000495a  jz      short loc_180004977
0x18000495c  cmp     byte ptr [rcx+19h], 1
0x180004960  jb      short loc_180004977
0x180004962  mov     rcx, [rcx+10h]
0x180004966  mov     edx, 9Ah
0x18000496b  call    WPP_SF_
0x180004970  mov     rcx, cs:WPP_GLOBAL_Control
0x180004977  mov     rdx, qword ptr cs:xmmword_1800146E0
0x18000497e  test    rdx, rdx
0x180004981  jz      loc_180004A10
0x180004987  lea     r8, aInvalidDataTyp_0; "Invalid data type for sha1 cert hash"
0x18000498e  jmp     short loc_1800049F6
0x180004990  cmp     r8d, 14h
0x180004994  jz      short loc_180004A09
0x180004996  mov     rcx, cs:WPP_GLOBAL_Control
0x18000499d  cmp     rcx, r14
0x1800049a0  jz      short loc_1800049CB
0x1800049a2  test    byte ptr [rcx+1Ch], 40h
0x1800049a6  jz      short loc_1800049CB
0x1800049a8  cmp     byte ptr [rcx+19h], 1
0x1800049ac  jb      short loc_1800049CB
0x1800049ae  mov     rcx, [rcx+10h]
0x1800049b2  mov     edx, 9Bh
0x1800049b7  mov     r9d, r8d
0x1800049ba  call    WPP_SF_d
0x1800049bf  mov     r8d, [rsp+8E0h+cbData]
0x1800049c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800049cb  cmp     qword ptr cs:xmmword_1800146E0, 0
0x1800049d3  jz      short loc_180004A10
0x1800049d5  xor     eax, eax
0x1800049d7  lea     rdx, aInvalidSha1Cer; "Invalid sha1 cert hash length: %d"
0x1800049de  lea     rcx, [rbp+7E0h+var_830]
0x1800049e2  mov     word ptr [rbp+7E0h+var_830], ax
0x1800049e6  call    FormatRRASErrorString
0x1800049eb  mov     rdx, qword ptr cs:xmmword_1800146E0
0x1800049f2  lea     r8, [rbp+7E0h+var_830]
0x1800049f6  mov     rcx, cs:gSstpCfgEtwContext
  ... truncated ...
```
