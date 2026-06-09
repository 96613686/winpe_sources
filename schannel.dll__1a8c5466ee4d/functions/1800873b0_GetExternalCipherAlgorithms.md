# GetExternalCipherAlgorithms

- ea: `0x1800873b0`
- end: `0x180087679`
- name: `GetExternalCipherAlgorithms`
- size: `713`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003c970`

## callees

- `0x18003ccdc`
- `0x1800487bc`
- `0x1800597b0`
- `0x18005a148`
- `0x18005a160`
- `0x18005f160`
- `0x180087310`
- `0x1800873b0`
- `0x180087d00`
- `0x180087df0`
- `0x180087e10`

## import_xrefs

- `ntdll!NtEnumerateKey` at `0x180087481`
- `ntdll!NtEnumerateKey` at `0x180087481`
- `bcrypt!BCryptGetProperty` at `0x18008756f`
- `bcrypt!BCryptGetProperty` at `0x18008756f`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180087580`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18008758b`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180087580`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18008758b`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18008753c`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18008753c`

## string_xrefs

- `0x180087422`: `\Registry\MACHINE\System\CurrentControlSet\Control\Cryptography\Providers\Microsoft SSL Protocol Provider\Cipher`
- `0x1800874c8`: `\Registry\MACHINE\System\CurrentControlSet\Control\Cryptography\Providers\Microsoft SSL Protocol Provider\Cipher`

## pseudocode

```c
__int64 GetExternalCipherAlgorithms()
{
  __int64 result; // rax
  ULONG v1; // edi
  unsigned __int64 v2; // r9
  HANDLE v3; // rbx
  _OWORD *v4; // rax
  __int64 v5; // rbx
  __int64 v6; // rax
  __int64 v7; // rax
  wchar_t *v8; // rcx
  int v9; // ecx
  UCHAR pbOutput[8]; // [rsp+30h] [rbp-D0h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE v12; // [rsp+40h] [rbp-C0h] BYREF
  ULONG ResultLength; // [rsp+48h] [rbp-B8h] BYREF
  ULONG pcbResult; // [rsp+4Ch] [rbp-B4h] BYREF
  HANDLE KeyHandle[2]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszAlgId[64]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t Source[64]; // [rsp+E0h] [rbp-20h] BYREF
  int KeyInformation; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v19[12]; // [rsp+164h] [rbp+64h] BYREF
  unsigned __int16 v20[264]; // [rsp+170h] [rbp+70h] BYREF
  WCHAR v21[64]; // [rsp+380h] [rbp+280h] BYREF

  KeyHandle[0] = 0;
  v12 = 0;
  memset_0(v21, 0, sizeof(v21));
  *(_DWORD *)pbOutput = 0;
  phAlgorithm = 0;
  pcbResult = 0;
  result = FreeExternalCipherAlgorithms();
  if ( (unsigned int)g_dwCipherInfoTotalCount < 0x10 )
  {
    result = TlsOpenRegKey(
               L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\Cryptography\\Providers\\Microsoft SSL Protocol "
                "Provider\\Cipher",
               0,
               KeyHandle);
    if ( (int)result >= 0 )
    {
      v1 = 0;
      for ( ResultLength = 0; (unsigned int)g_dwCipherInfoTotalCount < 0x10; ++v1 )
      {
        KeyInformation = 0;
        memset_0(v19, 0, 0x214u);
        if ( NtEnumerateKey(KeyHandle[0], v1, KeyBasicInformation, &KeyInformation, 0x218u, &ResultLength) < 0 )
          return TlsCloseRegKey(KeyHandle);
        v2 = -1;
        do
          ++v2;
        while ( v20[v2] );
        if ( (int)RtlStringCchCopyNW(v21, 0x40u, v20, v2) >= 0
          && (int)TlsOpenRegKey(
                    L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\Cryptography\\Providers\\Microsoft SSL Prot"
                     "ocol Provider\\Cipher",
                    v21,
                    &v12) >= 0 )
        {
          memset_0(pszAlgId, 0, 0x100u);
          v3 = v12;
          if ( (int)GetSslStringFromRegistry(v12, L"CngAlgorithm", pszAlgId) < 0 )
          {
            TlsCloseRegKey(&v12);
            continue;
          }
          GetSslStringFromRegistry(v3, L"CipherMode", Source);
          TlsCloseRegKey(&v12);
          if ( BCryptOpenAlgorithmProvider(&phAlgorithm, pszAlgId, 0, 0) >= 0 )
          {
            if ( BCryptGetProperty(phAlgorithm, L"BlockLength", pbOutput, 4u, &pcbResult, 0) >= 0 )
            {
              BCryptCloseAlgorithmProvider(phAlgorithm, 0);
              v4 = (_OWORD *)SafeAllocaAllocateFromHeap(32);
              v5 = (__int64)v4;
              if ( v4 )
              {
                *v4 = 0;
                v4[1] = 0;
                v6 = SafeAllocaAllocateFromHeap(128);
                *(_QWORD *)v5 = v6;
                if ( v6 )
                {
                  v7 = SafeAllocaAllocateFromHeap(128);
                  v8 = *(wchar_t **)v5;
                  *(_QWORD *)(v5 + 24) = v7;
                  if ( v7 )
                  {
                    wcscpy_s(v8, 0x40u, pszAlgId);
                    wcscpy_s(*(wchar_t **)(v5 + 24), 0x40u, Source);
                    v9 = g_dwCipherInfoTotalCount++;
                    *(_DWORD *)(v5 + 12) = v9 - 1073741830;
                    *(_DWORD *)(v5 + 16) = v9 + 28665;
                    *(_DWORD *)(v5 + 8) = *(_DWORD *)pbOutput;
                    g_pCipherInfo[v9] = v5;
                    continue;
                  }
                  SchannelFree(v8);
                }
                SchannelFree(v5);
              }
            }
            else
            {
              BCryptCloseAlgorithmProvider(phAlgorithm, 0);
            }
          }
        }
      }
      return TlsCloseRegKey(KeyHandle);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800873b0  push    rbp
0x1800873b2  push    rbx
0x1800873b3  push    rsi
0x1800873b4  push    rdi
0x1800873b5  push    r14
0x1800873b7  push    r15
0x1800873b9  lea     rbp, [rsp-318h]
0x1800873c1  sub     rsp, 418h
0x1800873c8  mov     rax, cs:__security_cookie
0x1800873cf  xor     rax, rsp
0x1800873d2  mov     [rbp+340h+var_40], rax
0x1800873d9  xor     esi, esi
0x1800873db  lea     rcx, [rbp+340h+var_C0]; void *
0x1800873e2  mov     r14d, 80h
0x1800873e8  mov     [rsp+440h+KeyHandle], rsi
0x1800873ed  mov     r8d, r14d; Size
0x1800873f0  mov     [rsp+440h+var_400], rsi
0x1800873f5  xor     edx, edx; Val
0x1800873f7  call    memset_0
0x1800873fc  mov     dword ptr [rsp+440h+pbOutput], esi
0x180087400  mov     [rsp+440h+phAlgorithm], rsi
0x180087405  mov     [rsp+440h+pcbResult], esi
0x180087409  call    FreeExternalCipherAlgorithms
0x18008740e  cmp     cs:g_dwCipherInfoTotalCount, 10h
0x180087415  jnb     loc_18008765A
0x18008741b  lea     r8, [rsp+440h+KeyHandle]; KeyHandle
0x180087420  xor     edx, edx; PCWSTR
0x180087422  lea     rcx, aRegistryMachin_2; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x180087429  call    TlsOpenRegKey
0x18008742e  test    eax, eax
0x180087430  js      loc_18008765A
0x180087436  cmp     cs:g_dwCipherInfoTotalCount, 10h
0x18008743d  mov     edi, esi
0x18008743f  mov     [rsp+440h+var_3F8], esi
0x180087443  jnb     loc_180087650
0x180087449  lea     r15d, [rsi+40h]
0x18008744d  xor     edx, edx; Val
0x18008744f  mov     [rbp+340h+KeyInformation], esi
0x180087452  mov     r8d, 214h; Size
0x180087458  lea     rcx, [rbp+340h+var_2DC]; void *
0x18008745c  call    memset_0
0x180087461  mov     rcx, [rsp+440h+KeyHandle]; KeyHandle
0x180087466  lea     rax, [rsp+440h+var_3F8]
0x18008746b  mov     [rsp+440h+ResultLength], rax; ResultLength
0x180087470  lea     r9, [rbp+340h+KeyInformation]; KeyInformation
0x180087474  xor     r8d, r8d; KeyInformationClass
0x180087477  mov     [rsp+440h+Length], 218h; Length
0x18008747f  mov     edx, edi; Index
0x180087481  call    cs:__imp_NtEnumerateKey
0x180087487  test    eax, eax
0x180087489  js      loc_180087650
0x18008748f  lea     rax, [rbp+340h+var_2D0]
0x180087493  or      r9, 0FFFFFFFFFFFFFFFFh
0x180087497  inc     r9; unsigned __int64
0x18008749a  cmp     [rax+r9*2], si
0x18008749f  jnz     short loc_180087497
0x1800874a1  lea     r8, [rbp+340h+var_2D0]; unsigned __int16 *
0x1800874a5  mov     rdx, r15; unsigned __int64
0x1800874a8  lea     rcx, [rbp+340h+var_C0]; unsigned __int16 *
0x1800874af  call    ?RtlStringCchCopyNW@@YAJPEAG_KPEBG1@Z; RtlStringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1800874b4  test    eax, eax
0x1800874b6  js      loc_180087641
0x1800874bc  lea     r8, [rsp+440h+var_400]; KeyHandle
0x1800874c1  lea     rdx, [rbp+340h+var_C0]; PCWSTR
0x1800874c8  lea     rcx, aRegistryMachin_2; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x1800874cf  call    TlsOpenRegKey
0x1800874d4  test    eax, eax
0x1800874d6  js      loc_180087641
0x1800874dc  xor     edx, edx; Val
0x1800874de  lea     rcx, [rsp+440h+pszAlgId]; void *
0x1800874e3  mov     r8d, 100h; Size
0x1800874e9  call    memset_0
0x1800874ee  mov     rbx, [rsp+440h+var_400]
0x1800874f3  lea     r8, [rsp+440h+pszAlgId]; unsigned __int16 *
0x1800874f8  mov     rcx, rbx; KeyHandle
0x1800874fb  lea     rdx, aCngalgorithm; "CngAlgorithm"
0x180087502  call    GetSslStringFromRegistry
0x180087507  test    eax, eax
0x180087509  js      loc_180087637
0x18008750f  lea     r8, [rbp+340h+Source]; unsigned __int16 *
0x180087513  mov     rcx, rbx; KeyHandle
0x180087516  lea     rdx, aCiphermode; "CipherMode"
0x18008751d  call    GetSslStringFromRegistry
0x180087522  lea     rcx, [rsp+440h+var_400]
0x180087527  call    TlsCloseRegKey
0x18008752c  xor     r9d, r9d; dwFlags
0x18008752f  lea     rdx, [rsp+440h+pszAlgId]; pszAlgId
0x180087534  xor     r8d, r8d; pszImplementation
0x180087537  lea     rcx, [rsp+440h+phAlgorithm]; phAlgorithm
0x18008753c  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180087542  test    eax, eax
0x180087544  js      loc_180087641
0x18008754a  mov     rcx, [rsp+440h+phAlgorithm]; hObject
0x18008754f  lea     rax, [rsp+440h+pcbResult]
0x180087554  mov     dword ptr [rsp+440h+ResultLength], esi; dwFlags
0x180087558  lea     r8, [rsp+440h+pbOutput]; pbOutput
0x18008755d  mov     r9d, 4; cbOutput
0x180087563  mov     qword ptr [rsp+440h+Length], rax; pcbResult
0x180087568  lea     rdx, aBlocklength; "BlockLength"
0x18008756f  call    cs:__imp_BCryptGetProperty
0x180087575  mov     rcx, [rsp+440h+phAlgorithm]; hAlgorithm
0x18008757a  xor     edx, edx; dwFlags
0x18008757c  test    eax, eax
0x18008757e  jns     short loc_18008758B
0x180087580  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180087586  jmp     loc_180087641
0x18008758b  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180087591  mov     ecx, 20h ; ' '
0x180087596  call    SafeAllocaAllocateFromHeap
0x18008759b  mov     rbx, rax
0x18008759e  test    rax, rax
0x1800875a1  jz      loc_180087641
0x1800875a7  xorps   xmm0, xmm0
0x1800875aa  mov     rcx, r14
0x1800875ad  movups  xmmword ptr [rax], xmm0
0x1800875b0  movups  xmmword ptr [rax+10h], xmm0
0x1800875b4  call    SafeAllocaAllocateFromHeap
0x1800875b9  mov     [rbx], rax
0x1800875bc  test    rax, rax
0x1800875bf  jnz     short loc_1800875CB
0x1800875c1  mov     rcx, rbx
0x1800875c4  call    SchannelFree
0x1800875c9  jmp     short loc_180087641
0x1800875cb  mov     rcx, r14
0x1800875ce  call    SafeAllocaAllocateFromHeap
0x1800875d3  mov     rcx, [rbx]; Destination
0x1800875d6  mov     [rbx+18h], rax
0x1800875da  test    rax, rax
0x1800875dd  jnz     short loc_1800875E6
0x1800875df  call    SchannelFree
0x1800875e4  jmp     short loc_1800875C1
0x1800875e6  lea     r8, [rsp+440h+pszAlgId]; Source
0x1800875eb  mov     rdx, r15; SizeInWords
0x1800875ee  call    wcscpy_s
0x1800875f3  mov     rcx, [rbx+18h]; Destination
0x1800875f7  lea     r8, [rbp+340h+Source]; Source
0x1800875fb  mov     rdx, r15; SizeInWords
0x1800875fe  call    wcscpy_s
0x180087603  mov     ecx, cs:g_dwCipherInfoTotalCount
0x180087609  inc     cs:g_dwCipherInfoTotalCount
0x18008760f  lea     eax, [rcx-40000006h]
0x180087615  mov     [rbx+0Ch], eax
0x180087618  lea     eax, [rcx+6FF9h]
0x18008761e  mov     [rbx+10h], eax
0x180087621  mov     eax, dword ptr [rsp+440h+pbOutput]
0x180087625  mov     [rbx+8], eax
0x180087628  mov     eax, ecx
0x18008762a  lea     rcx, g_pCipherInfo
0x180087631  mov     [rcx+rax*8], rbx
0x180087635  jmp     short loc_180087641
0x180087637  lea     rcx, [rsp+440h+var_400]
0x18008763c  call    TlsCloseRegKey
0x180087641  inc     edi
0x180087643  cmp     cs:g_dwCipherInfoTotalCount, 10h
0x18008764a  jb      loc_18008744D
0x180087650  lea     rcx, [rsp+440h+KeyHandle]
0x180087655  call    TlsCloseRegKey
0x18008765a  mov     rcx, [rbp+340h+var_40]
0x180087661  xor     rcx, rsp; StackCookie
0x180087664  call    __security_check_cookie
0x180087669  add     rsp, 418h
0x180087670  pop     r15
0x180087672  pop     r14
0x180087674  pop     rdi
0x180087675  pop     rsi
0x180087676  pop     rbx
0x180087677  pop     rbp
0x180087678  retn
```
