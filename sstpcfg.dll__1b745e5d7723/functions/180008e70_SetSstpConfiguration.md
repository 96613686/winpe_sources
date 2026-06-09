# SetSstpConfiguration

- ea: `0x180008e70`
- end: `0x18000931c`
- name: `SetSstpConfiguration`
- size: `1196`
- prototype: `__int64 __fastcall(__int64, wchar_t *, int, __int64)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, service_task`

## callees

- `0x180002474`
- `0x180003e10`
- `0x180004f10`
- `0x180008e70`
- `0x180009b34`
- `0x18000a014`
- `0x18000a044`
- `0x18000acbc`
- `0x18000ae4e`
- `0x18000ae80`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008f0c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008f0c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000916d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000916d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008fc0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008fc0`
- `CRYPT32!CertFreeCertificateContext` at `0x18000917b`
- `CRYPT32!CertFreeCertificateContext` at `0x18000917b`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180009162`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180009162`

## string_xrefs

- `0x180008ee8`: `System\CurrentControlSet\Services\SstpSvc\Parameters`
- `0x180008f5c`: `Unable to open the SSTPSVC Params Key: %d`
- `0x180009310`: `Trying to store HASH configuration %d`

## pseudocode

```c
__int64 __fastcall SetSstpConfiguration(__int64 a1, wchar_t *a2, int a3, __int64 a4)
{
  __int64 v8; // rcx
  unsigned int v9; // eax
  __int64 v10; // r8
  unsigned int v11; // ebx
  _QWORD *v12; // rcx
  unsigned int v13; // eax
  __int64 v14; // r8
  const wchar_t *v15; // rdx
  unsigned int CertificateFromSha256Hash; // eax
  __int64 v18; // rdx
  __int64 v19; // r8
  unsigned int HashFromCertificate; // eax
  __int64 v21; // rdx
  __int64 v22; // r8
  unsigned int v23; // eax
  __int64 v24; // r8
  int cbData; // [rsp+28h] [rbp-D8h]
  BYTE Data[8]; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  BOOL v28; // [rsp+48h] [rbp-B8h] BYREF
  int v29; // [rsp+4Ch] [rbp-B4h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+50h] [rbp-B0h] BYREF
  _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-A0h] BYREF
  int *v32; // [rsp+70h] [rbp-90h]
  int v33; // [rsp+78h] [rbp-88h]
  int v34; // [rsp+7Ch] [rbp-84h]
  BOOL *v35; // [rsp+80h] [rbp-80h]
  __int64 v36; // [rsp+88h] [rbp-78h]
  int *v37; // [rsp+90h] [rbp-70h]
  __int64 v38; // [rsp+98h] [rbp-68h]
  __int128 v39; // [rsp+A0h] [rbp-60h] BYREF
  int v40; // [rsp+B0h] [rbp-50h]
  int v41; // [rsp+C0h] [rbp-40h] BYREF
  char v42[2044]; // [rsp+C4h] [rbp-3Ch] BYREF

  hKey = 0;
  v40 = 0;
  v41 = 0;
  *(_DWORD *)Data = 1;
  v39 = 0;
  memset_0(v42, 0, sizeof(v42));
  v8 = a1;
  if ( !a1 )
    v8 = -2147483646;
  v9 = RegOpenKeyExW((HKEY)v8, L"System\\CurrentControlSet\\Services\\SstpSvc\\Parameters", 0, 0x2001Fu, &hKey);
  v11 = v9;
  if ( !v9 )
  {
    *(_DWORD *)Data = a3;
    v13 = RegSetValueExW(hKey, L"UseHttps", 0, 4u, Data, 4u);
    v11 = v13;
    if ( v13 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, v14, v13);
      }
      if ( !(_QWORD)xmmword_1800146E0 )
        goto LABEL_26;
      v15 = L"Trying to store HTTP usage failed %d";
LABEL_17:
      LOWORD(v41) = 0;
      FormatRRASErrorString(&v41, v15, v11);
      ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(gSstpCfgEtwContext, xmmword_1800146E0, &v41);
LABEL_26:
      RegCloseKey(hKey);
      goto LABEL_27;
    }
    if ( a4 )
    {
      CertificateFromSha256Hash = GetCertificateFromSha256Hash(a2);
      v11 = CertificateFromSha256Hash;
      if ( CertificateFromSha256Hash )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, v19, CertificateFromSha256Hash);
        }
        if ( (_QWORD)xmmword_1800146E0 )
        {
          LOWORD(v41) = 0;
          FormatRRASErrorString(&v41, L"Unable to get Certificate from hash %d", v11);
          ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(
            gSstpCfgEtwContext,
            xmmword_1800146E0,
            &v41);
        }
        goto LABEL_26;
      }
      LOBYTE(v18) = 1;
      HashFromCertificate = GetHashFromCertificate(0, v18, &v39, 0);
      v11 = HashFromCertificate;
      if ( HashFromCertificate )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, v22, HashFromCertificate);
        }
        if ( !(_QWORD)xmmword_1800146E0 )
          goto LABEL_26;
        v15 = L"Unable to get hash from Certificate  %d";
        goto LABEL_17;
      }
      LOBYTE(cbData) = 1;
      v23 = StoreCertHash(a1, v21, v22, &v39, a4, cbData);
      v11 = v23;
      if ( v23 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, v24, v23);
        }
        if ( !(_QWORD)xmmword_1800146E0 )
          goto LABEL_26;
        v15 = L"Trying to store HASH configuration %d";
        goto LABEL_17;
      }
    }
    else
    {
      ClearCertHash(hKey);
    }
    if ( (!a1 || a1 == -2147483646)
      && (unsigned int)dword_180014000 > 5
      && (qword_180014010 & 0x400000000000LL) != 0
      && (qword_180014018 & 0x400000000000LL) == qword_180014018 )
    {
      EventDescriptor.Keyword = 0x400000000000LL;
      v29 = a3;
      v36 = 4;
      v38 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      v28 = a4 != 0;
      v35 = &v28;
      v37 = &v29;
      *(_DWORD *)&EventDescriptor.Level = 5;
      UserData.Ptr = (ULONGLONG)off_180014008;
      UserData.Size = *(unsigned __int16 *)off_180014008;
      v32 = &dword_1800119B4;
      UserData.Reserved = 2;
      v33 = 75;
      v34 = 1;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
    }
    goto LABEL_26;
  }
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, v10, v9);
    v12 = WPP_GLOBAL_Control;
  }
  if ( (_QWORD)xmmword_1800146E0 )
  {
    LOWORD(v41) = 0;
    FormatRRASErrorString(&v41, L"Unable to open the SSTPSVC Params Key: %d", v11);
    ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(gSstpCfgEtwContext, xmmword_1800146E0, &v41);
LABEL_27:
    v12 = WPP_GLOBAL_Control;
  }
  if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 0xC0) == 0xC0 )
    WPP_SF_(v12[2], 65);
  return v11;
}

```

## disassembly

```asm
0x180008e70  push    rbp
0x180008e72  push    rbx
0x180008e73  push    rsi
0x180008e74  push    rdi
0x180008e75  push    r12
0x180008e77  push    r13
0x180008e79  push    r14
0x180008e7b  push    r15
0x180008e7d  lea     rbp, [rsp-7D8h]
0x180008e85  sub     rsp, 8D8h
0x180008e8c  mov     rax, cs:__security_cookie
0x180008e93  xor     rax, rsp
0x180008e96  mov     [rbp+810h+var_50], rax
0x180008e9d  xor     eax, eax
0x180008e9f  mov     [rsp+910h+hKey], 0
0x180008ea8  mov     r13d, r8d
0x180008eab  mov     [rbp+810h+var_860], eax
0x180008eae  mov     r12, rdx
0x180008eb1  mov     [rbp+810h+var_850], eax
0x180008eb4  mov     r14, rcx
0x180008eb7  mov     dword ptr [rsp+910h+Data], 1
0x180008ebf  xorps   xmm0, xmm0
0x180008ec2  lea     rcx, [rbp+810h+var_84C]; void *
0x180008ec6  xor     esi, esi
0x180008ec8  xor     edx, edx; Val
0x180008eca  mov     r8d, 7FCh; Size
0x180008ed0  mov     [rsp+910h+var_8E0], rsi
0x180008ed5  movups  [rbp+810h+var_870], xmm0
0x180008ed9  mov     r15, r9
0x180008edc  call    memset_0
0x180008ee1  mov     rax, 0FFFFFFFF80000002h
0x180008ee8  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\Ss"...
0x180008eef  test    r14, r14
0x180008ef2  mov     rcx, r14
0x180008ef5  mov     r9d, 2001Fh; samDesired
0x180008efb  cmovz   rcx, rax; hKey
0x180008eff  lea     rax, [rsp+910h+hKey]
0x180008f04  xor     r8d, r8d; ulOptions
0x180008f07  mov     [rsp+910h+phkResult], rax; phkResult
0x180008f0c  call    cs:__imp_RegOpenKeyExW
0x180008f12  mov     ebx, eax
0x180008f14  test    eax, eax
0x180008f16  jz      short loc_180008F96
0x180008f18  mov     rcx, cs:WPP_GLOBAL_Control
0x180008f1f  lea     rdi, WPP_GLOBAL_Control
0x180008f26  cmp     rcx, rdi
0x180008f29  jz      short loc_180008F4D
0x180008f2b  test    byte ptr [rcx+1Ch], 40h
0x180008f2f  jz      short loc_180008F4D
0x180008f31  cmp     byte ptr [rcx+19h], 1
0x180008f35  jb      short loc_180008F4D
0x180008f37  mov     rcx, [rcx+10h]
0x180008f3b  lea     edx, [rsi+3Ch]
0x180008f3e  mov     r9d, eax
0x180008f41  call    WPP_SF_d
0x180008f46  mov     rcx, cs:WPP_GLOBAL_Control
0x180008f4d  cmp     qword ptr cs:xmmword_1800146E0, rsi
0x180008f54  jz      loc_180009188
0x180008f5a  xor     eax, eax
0x180008f5c  lea     rdx, aUnableToOpenTh; "Unable to open the SSTPSVC Params Key: "...
0x180008f63  mov     r8d, ebx
0x180008f66  mov     word ptr [rbp+810h+var_850], ax
0x180008f6a  lea     rcx, [rbp+810h+var_850]
0x180008f6e  call    FormatRRASErrorString
0x180008f73  mov     rdx, qword ptr cs:xmmword_1800146E0
0x180008f7a  lea     r8, [rbp+810h+var_850]
0x180008f7e  mov     rcx, cs:gSstpCfgEtwContext
0x180008f85  mov     rax, cs:gSstpCfgTemplateFunc
0x180008f8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f91  jmp     loc_180009181
0x180008f96  mov     ecx, 4
0x180008f9b  mov     dword ptr [rsp+910h+Data], r13d
0x180008fa0  mov     [rsp+910h+cbData], ecx; cbData
0x180008fa4  lea     rax, [rsp+910h+Data]
0x180008fa9  mov     r9d, ecx; dwType
0x180008fac  mov     [rsp+910h+phkResult], rax; lpData
0x180008fb1  mov     rcx, [rsp+910h+hKey]; hKey
0x180008fb6  lea     rdx, aUsehttps; "UseHttps"
0x180008fbd  xor     r8d, r8d; Reserved
0x180008fc0  call    cs:__imp_RegSetValueExW
0x180008fc6  lea     rdi, WPP_GLOBAL_Control
0x180008fcd  mov     ebx, eax
0x180008fcf  test    eax, eax
0x180008fd1  jz      short loc_180009045
0x180008fd3  mov     rcx, cs:WPP_GLOBAL_Control
0x180008fda  cmp     rcx, rdi
0x180008fdd  jz      short loc_180008FFC
0x180008fdf  test    byte ptr [rcx+1Ch], 40h
0x180008fe3  jz      short loc_180008FFC
0x180008fe5  cmp     byte ptr [rcx+19h], 2
0x180008fe9  jb      short loc_180008FFC
0x180008feb  mov     rcx, [rcx+10h]
0x180008fef  mov     edx, 3Dh ; '='
0x180008ff4  mov     r9d, eax
0x180008ff7  call    WPP_SF_d
0x180008ffc  cmp     qword ptr cs:xmmword_1800146E0, rsi
0x180009003  jz      loc_180009168
0x180009009  lea     rdx, aTryingToStoreH_0; "Trying to store HTTP usage failed %d"
0x180009010  xor     eax, eax
0x180009012  lea     rcx, [rbp+810h+var_850]
0x180009016  mov     r8d, ebx
0x180009019  mov     word ptr [rbp+810h+var_850], ax
0x18000901d  call    FormatRRASErrorString
0x180009022  mov     rdx, qword ptr cs:xmmword_1800146E0
0x180009029  lea     r8, [rbp+810h+var_850]
0x18000902d  mov     rcx, cs:gSstpCfgEtwContext
0x180009034  mov     rax, cs:gSstpCfgTemplateFunc
0x18000903b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009040  jmp     loc_180009168
0x180009045  test    r15, r15
0x180009048  jnz     loc_1800091CC
0x18000904e  mov     rcx, [rsp+910h+hKey]; hKey
0x180009053  call    ClearCertHash
0x180009058  test    r14, r14
0x18000905b  jz      short loc_18000906A
0x18000905d  cmp     r14, 0FFFFFFFF80000002h
0x180009064  jnz     loc_180009168
0x18000906a  mov     eax, cs:dword_180014000
0x180009070  cmp     eax, 5
0x180009073  jbe     loc_180009168
0x180009079  mov     rcx, cs:qword_180014018
0x180009080  mov     rdx, 400000000000h
0x18000908a  mov     rax, cs:qword_180014010
0x180009091  test    rdx, rax
0x180009094  jz      loc_180009168
0x18000909a  mov     rax, rcx
0x18000909d  and     rax, rdx
0x1800090a0  cmp     rax, rcx
0x1800090a3  jnz     loc_180009168
0x1800090a9  xor     eax, eax
0x1800090ab  mov     [rsp+910h+EventDescriptor.Keyword], rdx
0x1800090b0  mov     r8d, 4
0x1800090b6  mov     [rsp+910h+var_8C4], r13d
0x1800090bb  mov     [rbp+810h+var_888], r8
0x1800090bf  lea     rcx, _TraceLoggingMetadata
0x1800090c6  mov     [rbp+810h+var_878], r8
0x1800090ca  lea     rdx, [rsp+910h+EventDescriptor]; EventDescriptor
0x1800090cf  mov     dword ptr [rsp+910h+EventDescriptor.Id], 0B000000h
0x1800090d7  test    r15, r15
0x1800090da  setnz   al
0x1800090dd  xor     r9d, r9d; RelatedActivityId
0x1800090e0  mov     [rsp+910h+var_8C8], eax
0x1800090e4  lea     rax, [rsp+910h+var_8C8]
0x1800090e9  mov     [rbp+810h+var_890], rax
0x1800090ed  lea     rax, [rsp+910h+var_8C4]
0x1800090f2  mov     [rbp+810h+var_880], rax
0x1800090f6  movzx   eax, cs:word_1800119AA
0x1800090fd  mov     dword ptr [rsp+910h+EventDescriptor.Level], eax
0x180009101  mov     rax, cs:off_180014008
0x180009108  mov     [rsp+910h+UserData.Ptr], rax
0x18000910d  movzx   eax, word ptr [rax]
0x180009110  mov     [rsp+910h+UserData.Size], eax
0x180009114  lea     rax, dword_1800119B4
0x18000911b  mov     [rsp+910h+var_8A0], rax
0x180009120  lea     rax, _TraceLoggingMetadataEnd
0x180009127  sub     eax, ecx
0x180009129  mov     dword ptr [rsp+910h+UserData.0Ch], 2
0x180009131  mov     [rsp+910h+var_898], 4Bh ; 'K'
0x180009139  mov     [rsp+910h+var_894], 1
0x180009141  mov     dword ptr [rsp+910h+var_8E0], eax
0x180009145  mov     eax, dword ptr [rsp+910h+var_8E0]
0x180009149  mov     rcx, cs:RegHandle; RegHandle
0x180009150  lea     rax, [rsp+910h+UserData]
0x180009155  mov     qword ptr [rsp+910h+cbData], rax; UserData
0x18000915a  mov     dword ptr [rsp+910h+phkResult], r8d; UserDataCount
0x18000915f  xor     r8d, r8d; ActivityId
0x180009162  call    cs:__imp_EventWriteTransfer
0x180009168  mov     rcx, [rsp+910h+hKey]; hKey
0x18000916d  call    cs:__imp_RegCloseKey
0x180009173  test    rsi, rsi
0x180009176  jz      short loc_180009181
0x180009178  mov     rcx, rsi; pCertContext
0x18000917b  call    cs:__imp_CertFreeCertificateContext
0x180009181  mov     rcx, cs:WPP_GLOBAL_Control
0x180009188  cmp     rcx, rdi
0x18000918b  jz      short loc_1800091A7
0x18000918d  mov     eax, [rcx+1Ch]
0x180009190  and     eax, 0C0h
0x180009195  cmp     al, 0C0h
0x180009197  jnz     short loc_1800091A7
0x180009199  mov     rcx, [rcx+10h]
0x18000919d  mov     edx, 41h ; 'A'
0x1800091a2  call    WPP_SF_
0x1800091a7  mov     eax, ebx
0x1800091a9  mov     rcx, [rbp+810h+var_50]
0x1800091b0  xor     rcx, rsp; StackCookie
0x1800091b3  call    __security_check_cookie
0x1800091b8  add     rsp, 8D8h
0x1800091bf  pop     r15
0x1800091c1  pop     r14
0x1800091c3  pop     r13
0x1800091c5  pop     r12
0x1800091c7  pop     rdi
0x1800091c8  pop     rsi
0x1800091c9  pop     rbx
0x1800091ca  pop     rbp
0x1800091cb  retn
0x1800091cc  lea     r9, [rsp+910h+var_8E0]
0x1800091d1  mov     r8, r15
0x1800091d4  mov     edx, 20h ; ' '
0x1800091d9  mov     rcx, r12; Source
0x1800091dc  call    GetCertificateFromSha256Hash
0x1800091e1  mov     ebx, eax
0x1800091e3  test    eax, eax
0x1800091e5  jz      short loc_18000925A
0x1800091e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800091ee  cmp     rcx, rdi
0x1800091f1  jz      short loc_180009210
0x1800091f3  test    byte ptr [rcx+1Ch], 40h
0x1800091f7  jz      short loc_180009210
0x1800091f9  cmp     byte ptr [rcx+19h], 2
0x1800091fd  jb      short loc_180009210
0x1800091ff  mov     rcx, [rcx+10h]
0x180009203  mov     edx, 3Eh ; '>'
0x180009208  mov     r9d, eax
0x18000920b  call    WPP_SF_d
0x180009210  cmp     qword ptr cs:xmmword_1800146E0, rsi
0x180009217  jz      short loc_180009250
0x180009219  xor     eax, eax
0x18000921b  lea     rdx, aUnableToGetCer_3; "Unable to get Certificate from hash %d"
0x180009222  mov     r8d, ebx
0x180009225  mov     word ptr [rbp+810h+var_850], ax
0x180009229  lea     rcx, [rbp+810h+var_850]
0x18000922d  call    FormatRRASErrorString
0x180009232  mov     rdx, qword ptr cs:xmmword_1800146E0
0x180009239  lea     r8, [rbp+810h+var_850]
0x18000923d  mov     rcx, cs:gSstpCfgEtwContext
0x180009244  mov     rax, cs:gSstpCfgTemplateFunc
0x18000924b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009250  mov     rsi, [rsp+910h+var_8E0]
0x180009255  jmp     loc_180009168
0x18000925a  mov     rsi, [rsp+910h+var_8E0]
0x18000925f  lea     r8, [rbp+810h+var_870]
0x180009263  mov     rcx, rsi
0x180009266  xor     r9d, r9d
0x180009269  mov     dl, 1
0x18000926b  call    GetHashFromCertificate
0x180009270  mov     ebx, eax
0x180009272  test    eax, eax
0x180009274  jz      short loc_1800092B9
0x180009276  mov     rcx, cs:WPP_GLOBAL_Control
0x18000927d  cmp     rcx, rdi
0x180009280  jz      short loc_18000929F
0x180009282  test    byte ptr [rcx+1Ch], 40h
0x180009286  jz      short loc_18000929F
0x180009288  cmp     byte ptr [rcx+19h], 2
0x18000928c  jb      short loc_18000929F
0x18000928e  mov     rcx, [rcx+10h]
0x180009292  mov     edx, 3Fh ; '?'
0x180009297  mov     r9d, eax
0x18000929a  call    WPP_SF_d
0x18000929f  cmp     qword ptr cs:xmmword_1800146E0, 0
0x1800092a7  jz      loc_180009168
0x1800092ad  lea     rdx, aUnableToGetHas_0; "Unable to get hash from Certificate  %d"
0x1800092b4  jmp     loc_180009010
0x1800092b9  mov     byte ptr [rsp+910h+cbData], 1
0x1800092be  lea     r9, [rbp+810h+var_870]
0x1800092c2  mov     rcx, r14
0x1800092c5  mov     [rsp+910h+phkResult], r15
0x1800092ca  call    StoreCertHash
0x1800092cf  mov     ebx, eax
0x1800092d1  test    eax, eax
0x1800092d3  jz      loc_180009058
0x1800092d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800092e0  cmp     rcx, rdi
0x1800092e3  jz      short loc_180009302
0x1800092e5  test    byte ptr [rcx+1Ch], 40h
0x1800092e9  jz      short loc_180009302
0x1800092eb  cmp     byte ptr [rcx+19h], 2
0x1800092ef  jb      short loc_180009302
0x1800092f1  mov     rcx, [rcx+10h]
0x1800092f5  mov     edx, 40h ; '@'
0x1800092fa  mov     r9d, eax
0x1800092fd  call    WPP_SF_d
0x180009302  cmp     qword ptr cs:xmmword_1800146E0, 0
0x18000930a  jz      loc_180009168
0x180009310  lea     rdx, aTryingToStoreH; "Trying to store HASH configuration %d"
0x180009317  jmp     loc_180009010
```
