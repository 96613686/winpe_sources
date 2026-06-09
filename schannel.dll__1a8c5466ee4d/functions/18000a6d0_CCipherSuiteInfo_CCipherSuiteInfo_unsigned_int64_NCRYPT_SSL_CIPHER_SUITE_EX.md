# CCipherSuiteInfo::CCipherSuiteInfo(unsigned __int64,_NCRYPT_SSL_CIPHER_SUITE_EX *)

- ea: `0x18000a6d0`
- end: `0x18000aa9d`
- name: `??0CCipherSuiteInfo@@QEAA@_KPEAU_NCRYPT_SSL_CIPHER_SUITE_EX@@@Z`
- size: `973`
- prototype: `CCipherSuiteInfo *__fastcall(CCipherSuiteInfo *__hidden this, unsigned __int64, struct _NCRYPT_SSL_CIPHER_SUITE_EX *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a380`

## callees

- `0x18000a6d0`
- `0x18000aaa4`
- `0x18000ab10`
- `0x18000ac00`
- `0x18000ace0`
- `0x18000ad58`
- `0x180057cb4`
- `0x18005a100`
- `0x18005a148`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18000a789`
- `ntdll!RtlReleaseResource` at `0x18000a789`
- `ntdll!RtlAcquireResourceShared` at `0x18000a753`
- `ntdll!RtlAcquireResourceShared` at `0x18000a753`
- `ncrypt!SslIncrementProviderReferenceCount` at `0x18000a76e`
- `ncrypt!SslIncrementProviderReferenceCount` at `0x18000a76e`
- `ncrypt!NCryptOpenStorageProvider` at `0x18000aa88`
- `ncrypt!NCryptOpenStorageProvider` at `0x18000aa88`
- `bcrypt!BCryptFreeBuffer` at `0x18000a94e`
- `bcrypt!BCryptFreeBuffer` at `0x18000a94e`
- `bcrypt!BCryptEnumContextFunctionProviders` at `0x18000a936`
- `bcrypt!BCryptEnumContextFunctionProviders` at `0x18000a936`

## pseudocode

```c
CCipherSuiteInfo *__fastcall CCipherSuiteInfo::CCipherSuiteInfo(
        CCipherSuiteInfo *this,
        __int64 a2,
        struct _NCRYPT_SSL_CIPHER_SUITE_EX *a3)
{
  _DWORD *v3; // r14
  _DWORD *v4; // r15
  CCipherMill *v8; // rcx
  __int64 KeyExchangeInfoFromAlgorithmName; // rax
  int v10; // ebp
  int v11; // r8d
  unsigned int i; // ecx
  __int64 v13; // rax
  int v14; // edx
  unsigned int j; // ecx
  __int64 v16; // rax
  PCRYPT_CONTEXT_FUNCTION_PROVIDERS v17; // rcx
  bool v18; // al
  unsigned __int64 v19; // rax
  char *v20; // rsi
  unsigned int m; // ebx
  ULONG k; // ebx
  ULONG pcbBuffer; // [rsp+70h] [rbp+8h] BYREF
  PCRYPT_CONTEXT_FUNCTION_PROVIDERS ppBuffer; // [rsp+78h] [rbp+10h] BYREF

  v3 = (_DWORD *)((char *)this + 48);
  *((_DWORD *)this + 2) = 0;
  v4 = (_DWORD *)((char *)this + 52);
  *((_DWORD *)this + 3) = *((_DWORD *)a3 + 69);
  *((_DWORD *)this + 4) = *((_DWORD *)a3 + 102) >> 3;
  *((_DWORD *)this + 5) = *((_DWORD *)a3 + 68);
  *((_DWORD *)this + 6) = *((_DWORD *)a3 + 135);
  *((_DWORD *)this + 7) = *((_DWORD *)a3 + 2);
  *((_BYTE *)this + 56) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 106) = 0;
  *((_QWORD *)this + 107) = 0;
  *((_DWORD *)this + 12) = 0;
  *((_DWORD *)this + 13) = 0;
  RtlAcquireResourceShared(&Resource, 1u);
  if ( a2 )
  {
    if ( *(_QWORD *)this != a2 )
    {
      CCipherMill::DeferenceProvider(v8, (unsigned __int64 *)this);
      if ( (int)SslIncrementProviderReferenceCount(a2) >= 0 )
      {
        _InterlockedIncrement(&dword_1800AE5A0);
        *(_QWORD *)this = a2;
      }
    }
  }
  RtlReleaseResource(&Resource);
  KeyExchangeInfoFromAlgorithmName = I_GetKeyExchangeInfoFromAlgorithmName((wchar_t *)a3 + 206);
  if ( KeyExchangeInfoFromAlgorithmName )
  {
    v10 = *(_DWORD *)(KeyExchangeInfoFromAlgorithmName + 12);
  }
  else
  {
    v10 = 0;
    if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        &WPP_eb5149e4312e3fc6c7b47b99acf2d5dc_Traceguids,
        (char *)a3 + 412);
  }
  *((_DWORD *)this + 8) = v10;
  *((_DWORD *)this + 9) = LookupCertificateAlg(a3);
  *((_DWORD *)this + 10) = LookupSymmetricCipherAlg(a3);
  *((_DWORD *)this + 11) = LookupChecksumAlg(a3);
  wcscpy_s((wchar_t *)this + 101, 0x40u, (const wchar_t *)a3 + 72);
  wcscpy_s((wchar_t *)this + 165, 0x40u, (const wchar_t *)a3 + 206);
  wcscpy_s((wchar_t *)this + 229, 0x40u, (const wchar_t *)a3 + 274);
  wcscpy_s((wchar_t *)this + 293, 0x40u, (const wchar_t *)a3 + 140);
  wcscpy_s((wchar_t *)this + 357, 0x40u, (const wchar_t *)a3 + 340);
  if ( *((_DWORD *)a3 + 1) != 772 )
  {
    v11 = *((_DWORD *)this + 8);
    if ( v3 )
      *v3 = 0;
    for ( i = 0; i < g_dwKeyExchangeInfoTotalCount; ++i )
    {
      v13 = g_pKeyExchangeInfo[i];
      if ( v13 && *(_DWORD *)(v13 + 12) == v11 )
      {
        if ( v3 )
          *v3 = *(_DWORD *)(v13 + 16);
        break;
      }
    }
    v14 = *((_DWORD *)this + 9);
    if ( v4 )
      *v4 = 0;
    for ( j = 0; j < g_dwSignatureInfoTotalCount; ++j )
    {
      v16 = g_pSignatureInfo[j];
      if ( v16 && *(_DWORD *)(v16 + 12) == v14 )
      {
        if ( v4 )
          *v4 = *(_DWORD *)(v16 + 16);
        break;
      }
    }
  }
  pcbBuffer = 0;
  ppBuffer = 0;
  if ( BCryptEnumContextFunctionProviders(1u, 0, 3u, (LPCWSTR)a3 + 274, &pcbBuffer, &ppBuffer) >= 0 )
  {
    for ( k = 0; ; ++k )
    {
      v17 = ppBuffer;
      if ( k >= ppBuffer->cProviders )
        goto LABEL_30;
      if ( !wcsicmp(ppBuffer->rgpszProviders[k], L"Microsoft Primitive Provider") )
        break;
      if ( NCryptOpenStorageProvider((NCRYPT_PROV_HANDLE *)this + 8, ppBuffer->rgpszProviders[k], 0) >= 0 )
      {
        *((_BYTE *)this + 56) = 1;
        goto LABEL_48;
      }
    }
    *((_QWORD *)this + 8) = hProvider;
    *((_BYTE *)this + 56) = 0;
LABEL_48:
    v17 = ppBuffer;
    goto LABEL_30;
  }
  v17 = ppBuffer;
LABEL_30:
  if ( v17 )
    BCryptFreeBuffer(v17);
  v18 = *((_DWORD *)a3 + 2) == 3
     || *((_DWORD *)a3 + 2) == 98
     || *((_DWORD *)a3 + 2) == 99
     || *((_DWORD *)a3 + 2) == 100
     || *((_DWORD *)a3 + 2) == 131200;
  *((_BYTE *)this + 72) = v18;
  wcscpy_s((wchar_t *)this + 37, 0x40u, (const wchar_t *)a3 + 8);
  v19 = -1;
  do
    ++v19;
  while ( *((_WORD *)this + v19 + 37) );
  if ( v19 > 5 )
  {
    v20 = (char *)this + 2 * v19;
    for ( m = 0; m < 3; ++m )
    {
      if ( !wcsicmp((const wchar_t *)v20 + 32, (&off_180093FE0)[99 * m]) )
      {
        *((_WORD *)v20 + 32) = 0;
        return this;
      }
    }
  }
  return this;
}

```

## disassembly

```asm
0x18000a6d0  mov     [rsp+arg_10], rbx
0x18000a6d5  push    rbp
0x18000a6d6  push    rsi
0x18000a6d7  push    rdi
0x18000a6d8  push    r12
0x18000a6da  push    r13
0x18000a6dc  push    r14
0x18000a6de  push    r15
0x18000a6e0  sub     rsp, 30h
0x18000a6e4  xor     r13d, r13d
0x18000a6e7  lea     r14, [rcx+30h]
0x18000a6eb  mov     [rcx+8], r13d
0x18000a6ef  lea     r15, [rcx+34h]
0x18000a6f3  mov     eax, [r8+114h]
0x18000a6fa  mov     rbx, rdx
0x18000a6fd  mov     [rcx+0Ch], eax
0x18000a700  mov     rdi, rcx
0x18000a703  mov     eax, [r8+198h]
0x18000a70a  mov     dl, 1; Wait
0x18000a70c  shr     eax, 3
0x18000a70f  mov     rsi, r8
0x18000a712  mov     [rcx+10h], eax
0x18000a715  mov     eax, [r8+110h]
0x18000a71c  mov     [rcx+14h], eax
0x18000a71f  mov     eax, [r8+21Ch]
0x18000a726  mov     [rcx+18h], eax
0x18000a729  mov     eax, [r8+8]
0x18000a72d  mov     [rcx+1Ch], eax
0x18000a730  mov     [rcx+38h], r13b
0x18000a734  mov     [rcx+40h], r13
0x18000a738  mov     [rcx+350h], r13
0x18000a73f  mov     [rcx+358h], r13
0x18000a746  lea     rcx, Resource; Resource
0x18000a74d  mov     [r14], r13d
0x18000a750  mov     [r15], r13d
0x18000a753  call    cs:__imp_RtlAcquireResourceShared
0x18000a759  test    rbx, rbx
0x18000a75c  jz      short loc_18000A782
0x18000a75e  cmp     [rdi], rbx
0x18000a761  jz      short loc_18000A782
0x18000a763  mov     rdx, rdi; unsigned __int64 *
0x18000a766  call    ?DeferenceProvider@CCipherMill@@QEAAXPEA_K@Z; CCipherMill::DeferenceProvider(unsigned __int64 *)
0x18000a76b  mov     rcx, rbx
0x18000a76e  call    cs:__imp_SslIncrementProviderReferenceCount
0x18000a774  test    eax, eax
0x18000a776  js      short loc_18000A782
0x18000a778  lock inc cs:dword_1800AE5A0
0x18000a77f  mov     [rdi], rbx
0x18000a782  lea     rcx, Resource; Resource
0x18000a789  call    cs:__imp_RtlReleaseResource
0x18000a78f  lea     rcx, [rsi+19Ch]; String1
0x18000a796  call    I_GetKeyExchangeInfoFromAlgorithmName
0x18000a79b  test    rax, rax
0x18000a79e  jnz     short loc_18000A7DA
0x18000a7a0  mov     ebp, r13d
0x18000a7a3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a7aa  lea     rax, WPP_GLOBAL_Control
0x18000a7b1  cmp     rcx, rax
0x18000a7b4  jz      short loc_18000A7DD
0x18000a7b6  test    byte ptr [rcx+1Ch], 1
0x18000a7ba  jz      short loc_18000A7DD
0x18000a7bc  mov     rcx, [rcx+10h]
0x18000a7c0  lea     r9, [rsi+19Ch]
0x18000a7c7  mov     edx, 0Ah
0x18000a7cc  lea     r8, WPP_eb5149e4312e3fc6c7b47b99acf2d5dc_Traceguids
0x18000a7d3  call    WPP_SF_S
0x18000a7d8  jmp     short loc_18000A7DD
0x18000a7da  mov     ebp, [rax+0Ch]
0x18000a7dd  mov     rcx, rsi; struct _NCRYPT_SSL_CIPHER_SUITE_EX *
0x18000a7e0  mov     [rdi+20h], ebp
0x18000a7e3  call    ?LookupCertificateAlg@@YAIPEAU_NCRYPT_SSL_CIPHER_SUITE_EX@@@Z; LookupCertificateAlg(_NCRYPT_SSL_CIPHER_SUITE_EX *)
0x18000a7e8  mov     rcx, rsi; struct _NCRYPT_SSL_CIPHER_SUITE_EX *
0x18000a7eb  mov     [rdi+24h], eax
0x18000a7ee  call    ?LookupSymmetricCipherAlg@@YAIPEAU_NCRYPT_SSL_CIPHER_SUITE_EX@@@Z; LookupSymmetricCipherAlg(_NCRYPT_SSL_CIPHER_SUITE_EX *)
0x18000a7f3  mov     rcx, rsi; struct _NCRYPT_SSL_CIPHER_SUITE_EX *
0x18000a7f6  mov     [rdi+28h], eax
0x18000a7f9  call    ?LookupChecksumAlg@@YAIPEAU_NCRYPT_SSL_CIPHER_SUITE_EX@@@Z; LookupChecksumAlg(_NCRYPT_SSL_CIPHER_SUITE_EX *)
0x18000a7fe  lea     r8, [rsi+90h]; Source
0x18000a805  mov     [rdi+2Ch], eax
0x18000a808  lea     rcx, [rdi+0CAh]; Destination
0x18000a80f  mov     edx, 40h ; '@'; SizeInWords
0x18000a814  call    wcscpy_s
0x18000a819  lea     rcx, [rdi+14Ah]; Destination
0x18000a820  mov     edx, 40h ; '@'; SizeInWords
0x18000a825  lea     r8, [rsi+19Ch]; Source
0x18000a82c  call    wcscpy_s
0x18000a831  lea     rcx, [rdi+1CAh]; Destination
0x18000a838  mov     edx, 40h ; '@'; SizeInWords
0x18000a83d  lea     r8, [rsi+224h]; Source
0x18000a844  call    wcscpy_s
0x18000a849  lea     r8, [rsi+118h]; Source
0x18000a850  mov     edx, 40h ; '@'; SizeInWords
0x18000a855  lea     rcx, [rdi+24Ah]; Destination
0x18000a85c  call    wcscpy_s
0x18000a861  lea     r8, [rsi+2A8h]; Source
0x18000a868  mov     edx, 40h ; '@'; SizeInWords
0x18000a86d  lea     rcx, [rdi+2CAh]; Destination
0x18000a874  call    wcscpy_s
0x18000a879  cmp     dword ptr [rsi+4], 304h
0x18000a880  lea     rbp, __ImageBase
0x18000a887  jz      short loc_18000A904
0x18000a889  mov     r8d, [rdi+20h]
0x18000a88d  test    r14, r14
0x18000a890  jz      short loc_18000A895
0x18000a892  mov     [r14], r13d
0x18000a895  mov     edx, cs:g_dwKeyExchangeInfoTotalCount
0x18000a89b  mov     ecx, r13d
0x18000a89e  xchg    ax, ax
0x18000a8a0  cmp     ecx, edx
0x18000a8a2  jnb     short loc_18000A8C8
0x18000a8a4  mov     eax, ecx
0x18000a8a6  mov     rax, ss:rva g_pKeyExchangeInfo[rbp+rax*8]
0x18000a8ae  test    rax, rax
0x18000a8b1  jz      short loc_18000A8B9
0x18000a8b3  cmp     [rax+0Ch], r8d
0x18000a8b7  jz      short loc_18000A8BD
0x18000a8b9  inc     ecx
0x18000a8bb  jmp     short loc_18000A8A0
0x18000a8bd  test    r14, r14
0x18000a8c0  jz      short loc_18000A8C8
0x18000a8c2  mov     eax, [rax+10h]
0x18000a8c5  mov     [r14], eax
0x18000a8c8  mov     edx, [rdi+24h]
0x18000a8cb  test    r15, r15
0x18000a8ce  jnz     loc_18000AA61
0x18000a8d4  mov     ecx, r13d
0x18000a8d7  cmp     ecx, cs:g_dwSignatureInfoTotalCount
0x18000a8dd  jnb     short loc_18000A904
0x18000a8df  mov     eax, ecx
0x18000a8e1  mov     rax, ss:rva g_pSignatureInfo[rbp+rax*8]
0x18000a8e9  test    rax, rax
0x18000a8ec  jz      loc_180089AD2
0x18000a8f2  cmp     [rax+0Ch], edx
0x18000a8f5  jnz     loc_180089AD2
0x18000a8fb  test    r15, r15
0x18000a8fe  jnz     loc_18000AA69
0x18000a904  lea     rax, [rsp+68h+arg_8]
0x18000a909  mov     [rsp+68h+arg_0], r13d
0x18000a90e  mov     [rsp+68h+ppBuffer], rax; ppBuffer
0x18000a913  lea     r9, [rsi+224h]; pszFunction
0x18000a91a  lea     rax, [rsp+68h+arg_0]
0x18000a91f  mov     [rsp+68h+arg_8], r13
0x18000a924  xor     edx, edx; pszContext
0x18000a926  mov     [rsp+68h+pcbBuffer], rax; pcbBuffer
0x18000a92b  mov     ecx, 1; dwTable
0x18000a930  mov     r8d, 3; dwInterface
0x18000a936  call    cs:__imp_BCryptEnumContextFunctionProviders
0x18000a93c  test    eax, eax
0x18000a93e  jns     loc_18000A9DD
0x18000a944  mov     rcx, [rsp+68h+arg_8]; pvBuffer
0x18000a949  test    rcx, rcx
0x18000a94c  jz      short loc_18000A954
0x18000a94e  call    cs:__imp_BCryptFreeBuffer
0x18000a954  mov     ecx, [rsi+8]
0x18000a957  sub     ecx, 3
0x18000a95a  jz      loc_18000AA5A
0x18000a960  sub     ecx, 5Fh ; '_'
0x18000a963  jz      loc_18000AA5A
0x18000a969  sub     ecx, 1
0x18000a96c  jz      loc_18000AA5A
0x18000a972  sub     ecx, 1
0x18000a975  jz      loc_18000AA5A
0x18000a97b  cmp     ecx, 2001Ch
0x18000a981  jz      loc_18000AA5A
0x18000a987  xor     al, al
0x18000a989  lea     r8, [rsi+10h]; Source
0x18000a98d  mov     [rdi+48h], al
0x18000a990  mov     edx, 40h ; '@'; SizeInWords
0x18000a995  lea     rcx, [rdi+4Ah]; Destination
0x18000a999  call    wcscpy_s
0x18000a99e  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000a9a5  inc     rax
0x18000a9a8  cmp     [rdi+rax*2+4Ah], r13w
0x18000a9ae  jnz     short loc_18000A9A5
0x18000a9b0  cmp     rax, 5
0x18000a9b4  jbe     short loc_18000A9C2
0x18000a9b6  lea     rsi, [rdi+rax*2]
0x18000a9ba  mov     ebx, r13d
0x18000a9bd  cmp     ebx, 3
0x18000a9c0  jb      short loc_18000AA2B
0x18000a9c2  mov     rbx, [rsp+68h+arg_10]
0x18000a9ca  mov     rax, rdi
0x18000a9cd  add     rsp, 30h
0x18000a9d1  pop     r15
0x18000a9d3  pop     r14
0x18000a9d5  pop     r13
0x18000a9d7  pop     r12
0x18000a9d9  pop     rdi
0x18000a9da  pop     rsi
0x18000a9db  pop     rbp
0x18000a9dc  retn
0x18000a9dd  mov     ebx, r13d
0x18000a9e0  mov     rcx, [rsp+68h+arg_8]
0x18000a9e5  cmp     ebx, [rcx]
0x18000a9e7  jnb     short loc_18000AA1F
0x18000a9e9  mov     rcx, [rcx+8]
0x18000a9ed  lea     rdx, aMicrosoftPrimi; "Microsoft Primitive Provider"
0x18000a9f4  mov     eax, ebx
0x18000a9f6  lea     rbp, ds:0[rax*8]
0x18000a9fe  mov     rcx, [rcx+rbp]; String1
0x18000aa02  call    _wcsicmp
0x18000aa07  test    eax, eax
0x18000aa09  jnz     short loc_18000AA74
0x18000aa0b  mov     rax, cs:hProvider
0x18000aa12  mov     [rdi+40h], rax
0x18000aa16  mov     [rdi+38h], r13b
0x18000aa1a  mov     rcx, [rsp+68h+arg_8]
0x18000aa1f  lea     rbp, __ImageBase
0x18000aa26  jmp     loc_18000A949
0x18000aa2b  mov     eax, ebx
0x18000aa2d  lea     rcx, [rsi+40h]; String1
0x18000aa31  imul    rdx, rax, 318h
0x18000aa38  mov     rdx, [rdx+rbp+93FE0h]; String2
0x18000aa40  call    _wcsicmp
0x18000aa45  test    eax, eax
0x18000aa47  jz      short loc_18000AA50
0x18000aa49  inc     ebx
0x18000aa4b  jmp     loc_18000A9BD
0x18000aa50  mov     [rsi+40h], r13w
0x18000aa55  jmp     loc_18000A9C2
0x18000aa5a  mov     al, 1
0x18000aa5c  jmp     loc_18000A989
0x18000aa61  mov     [r15], r13d
0x18000aa64  jmp     loc_18000A8D4
0x18000aa69  mov     eax, [rax+10h]
0x18000aa6c  mov     [r15], eax
0x18000aa6f  jmp     loc_18000A904
0x18000aa74  mov     rax, [rsp+68h+arg_8]
0x18000aa79  lea     rcx, [rdi+40h]; phProvider
0x18000aa7d  xor     r8d, r8d; dwFlags
0x18000aa80  mov     rdx, [rax+8]
0x18000aa84  mov     rdx, [rdx+rbp]; pszProviderName
0x18000aa88  call    cs:__imp_NCryptOpenStorageProvider
0x18000aa8e  test    eax, eax
0x18000aa90  jns     loc_180089AD9
0x18000aa96  inc     ebx
0x18000aa98  jmp     loc_18000A9E0
0x180089ad2  inc     ecx
0x180089ad4  jmp     loc_18000A8D7
0x180089ad9  mov     byte ptr [rdi+38h], 1
0x180089add  jmp     loc_18000AA1A
```
