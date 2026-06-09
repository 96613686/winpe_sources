# MetadataIntegrity::MetadataHashStrategy::Initialize(wchar_t const *)

- ea: `0x1801ec54c`
- end: `0x1801ec783`
- name: `?Initialize@MetadataHashStrategy@MetadataIntegrity@@QEAAJPEB_W@Z`
- size: `567`
- prototype: `int(MetadataIntegrity::MetadataHashStrategy *__hidden this, const wchar_t *)`
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1801ed6dc`
- `0x1801ede9c`
- `0x1801ee618`
- `0x1801f085c`

## callees

- `0x180111c4c`
- `0x18012b618`
- `0x1801ec54c`
- `0x180238960`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1801ec5a5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1801ec5cf`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1801ec5f9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1801ec5a5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1801ec5cf`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1801ec5f9`
- `bcrypt!BCryptCreateHash` at `0x1801ec680`
- `bcrypt!BCryptCreateHash` at `0x1801ec680`
- `bcrypt!BCryptGetProperty` at `0x1801ec6cd`
- `bcrypt!BCryptGetProperty` at `0x1801ec6cd`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1801ec63d`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1801ec63d`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1801ec656`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1801ec719`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1801ec656`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1801ec719`
- `bcrypt!BCryptDestroyHash` at `0x1801ec693`
- `bcrypt!BCryptDestroyHash` at `0x1801ec728`
- `bcrypt!BCryptDestroyHash` at `0x1801ec693`
- `bcrypt!BCryptDestroyHash` at `0x1801ec728`

## pseudocode

```c
__int64 __fastcall MetadataIntegrity::MetadataHashStrategy::Initialize(
        MetadataIntegrity::MetadataHashStrategy *this,
        const wchar_t *lpString2)
{
  const WCHAR *v4; // rsi
  int v6; // edi
  NTSTATUS Property; // eax
  void *v8; // rcx
  BCRYPT_ALG_HANDLE v9; // rcx
  void *v10; // rcx
  void *v11; // rcx
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+40h] [rbp-20h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp-18h] BYREF
  ULONG pcbResult; // [rsp+50h] [rbp-10h] BYREF

  if ( lpString2
    && ((v4 = L"SHA256", CompareStringW(0x7Fu, 1u, L"SHA256", -1, lpString2, -1) == 2)
     || (v4 = L"SHA384", CompareStringW(0x7Fu, 1u, L"SHA384", -1, lpString2, -1) == 2)
     || (v4 = L"SHA512", CompareStringW(0x7Fu, 1u, L"SHA512", -1, lpString2, -1) == 2)) )
  {
    if ( v4 == *(const WCHAR **)this && *((_QWORD *)this + 1) && *((_QWORD *)this + 2) )
    {
      return 0;
    }
    else
    {
      v6 = 0;
      phHash = 0;
      phAlgorithm = 0;
      Property = BCryptOpenAlgorithmProvider(&phAlgorithm, v4, 0, 0x20u);
      if ( Property < 0 )
        goto LABEL_16;
      v8 = (void *)*((_QWORD *)this + 1);
      if ( v8 )
        BCryptCloseAlgorithmProvider(v8, 0);
      v9 = phAlgorithm;
      *((_QWORD *)this + 1) = phAlgorithm;
      phAlgorithm = 0;
      Property = BCryptCreateHash(v9, &phHash, 0, 0, 0, 0, 0x20u);
      if ( Property < 0 )
        goto LABEL_16;
      v10 = (void *)*((_QWORD *)this + 2);
      if ( v10 )
        BCryptDestroyHash(v10);
      v11 = (void *)*((_QWORD *)this + 1);
      *((_QWORD *)this + 2) = phHash;
      phHash = 0;
      *(_QWORD *)this = v4;
      pcbResult = 0;
      Property = BCryptGetProperty(v11, L"HashDigestLength", (PUCHAR)this + 24, 4u, &pcbResult, 0);
      if ( Property < 0 )
      {
LABEL_16:
        v6 = HRESULT_FROM_NTSTATUS(Property);
        if ( v6 < 0 )
          WUTrace("MetadataIntegrity::MetadataHashStrategy::Initialize", 118, 0x800000, 1, v6, L"Method failed");
      }
      if ( phAlgorithm )
        BCryptCloseAlgorithmProvider(phAlgorithm, 0);
      if ( phHash )
        BCryptDestroyHash(phHash);
      return (unsigned int)v6;
    }
  }
  else
  {
    WUTrace(0, 0, 0x800000, 1, 0, L"Unsupport hash algorithm[%ws]", lpString2);
    return 2149871937LL;
  }
}

```

## disassembly

```asm
0x1801ec54c  mov     [rsp-28h+arg_10], rbx
0x1801ec551  push    rbp
0x1801ec552  push    rsi
0x1801ec553  push    rdi
0x1801ec554  push    r12
0x1801ec556  push    r15
0x1801ec558  mov     rbp, rsp
0x1801ec55b  sub     rsp, 60h
0x1801ec55f  mov     rax, cs:__security_cookie
0x1801ec566  xor     rax, rsp
0x1801ec569  mov     [rbp+var_8], rax
0x1801ec56d  mov     rdi, rdx
0x1801ec570  mov     rbx, rcx
0x1801ec573  mov     r12d, 1
0x1801ec579  test    rdx, rdx
0x1801ec57c  jz      loc_1801EC732
0x1801ec582  or      r15d, 0FFFFFFFFh
0x1801ec586  lea     rsi, pszAlgId; "SHA256"
0x1801ec58d  mov     [rsp+60h+cchCount2], r15d; cchCount2
0x1801ec592  lea     ecx, [r12+7Eh]; Locale
0x1801ec597  mov     [rsp+60h+lpString2], rdx; lpString2
0x1801ec59c  mov     r9d, r15d; cchCount1
0x1801ec59f  mov     edx, r12d; dwCmpFlags
0x1801ec5a2  mov     r8, rsi; lpString1
0x1801ec5a5  call    cs:__imp_CompareStringW
0x1801ec5ab  cmp     eax, 2
0x1801ec5ae  jz      short loc_1801EC608
0x1801ec5b0  lea     rsi, aSha384; "SHA384"
0x1801ec5b7  mov     [rsp+60h+cchCount2], r15d; cchCount2
0x1801ec5bc  mov     r8, rsi; lpString1
0x1801ec5bf  mov     [rsp+60h+lpString2], rdi; lpString2
0x1801ec5c4  mov     r9d, r15d; cchCount1
0x1801ec5c7  lea     ecx, [r12+7Eh]; Locale
0x1801ec5cc  mov     edx, r12d; dwCmpFlags
0x1801ec5cf  call    cs:__imp_CompareStringW
0x1801ec5d5  cmp     eax, 2
0x1801ec5d8  jz      short loc_1801EC608
0x1801ec5da  lea     rsi, aSha512; "SHA512"
0x1801ec5e1  mov     [rsp+60h+cchCount2], r15d; cchCount2
0x1801ec5e6  mov     r8, rsi; lpString1
0x1801ec5e9  mov     [rsp+60h+lpString2], rdi; lpString2
0x1801ec5ee  mov     r9d, r15d; cchCount1
0x1801ec5f1  lea     ecx, [r12+7Eh]; Locale
0x1801ec5f6  mov     edx, r12d; dwCmpFlags
0x1801ec5f9  call    cs:__imp_CompareStringW
0x1801ec5ff  cmp     eax, 2
0x1801ec602  jnz     loc_1801EC732
0x1801ec608  cmp     rsi, [rbx]
0x1801ec60b  jnz     short loc_1801EC622
0x1801ec60d  cmp     qword ptr [rbx+8], 0
0x1801ec612  jz      short loc_1801EC622
0x1801ec614  cmp     qword ptr [rbx+10h], 0
0x1801ec619  jz      short loc_1801EC622
0x1801ec61b  xor     eax, eax
0x1801ec61d  jmp     loc_1801EC763
0x1801ec622  xor     edi, edi
0x1801ec624  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x1801ec628  xor     r8d, r8d; pszImplementation
0x1801ec62b  mov     [rbp+phHash], rdi
0x1801ec62f  mov     rdx, rsi; pszAlgId
0x1801ec632  mov     [rbp+phAlgorithm], rdi
0x1801ec636  lea     r15d, [rdi+20h]
0x1801ec63a  mov     r9d, r15d; dwFlags
0x1801ec63d  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1801ec643  test    eax, eax
0x1801ec645  js      loc_1801EC6D7
0x1801ec64b  mov     rcx, [rbx+8]; hAlgorithm
0x1801ec64f  test    rcx, rcx
0x1801ec652  jz      short loc_1801EC65C
0x1801ec654  xor     edx, edx; dwFlags
0x1801ec656  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1801ec65c  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1801ec660  lea     rdx, [rbp+phHash]; phHash
0x1801ec664  mov     [rsp+60h+dwFlags], r15d; dwFlags
0x1801ec669  xor     r9d, r9d; cbHashObject
0x1801ec66c  mov     [rsp+60h+cchCount2], edi; cbSecret
0x1801ec670  xor     r8d, r8d; pbHashObject
0x1801ec673  mov     [rbx+8], rcx
0x1801ec677  mov     [rsp+60h+lpString2], rdi; pbSecret
0x1801ec67c  mov     [rbp+phAlgorithm], rdi
0x1801ec680  call    cs:__imp_BCryptCreateHash
0x1801ec686  test    eax, eax
0x1801ec688  js      short loc_1801EC6D7
0x1801ec68a  mov     rcx, [rbx+10h]; hHash
0x1801ec68e  test    rcx, rcx
0x1801ec691  jz      short loc_1801EC699
0x1801ec693  call    cs:__imp_BCryptDestroyHash
0x1801ec699  mov     rax, [rbp+phHash]
0x1801ec69d  lea     r8, [rbx+18h]; pbOutput
0x1801ec6a1  mov     rcx, [rbx+8]; hObject
0x1801ec6a5  lea     rdx, pszProperty; "HashDigestLength"
0x1801ec6ac  mov     [rbx+10h], rax
0x1801ec6b0  mov     r9d, 4; cbOutput
0x1801ec6b6  lea     rax, [rbp+pcbResult]
0x1801ec6ba  mov     [rsp+60h+cchCount2], edi; dwFlags
0x1801ec6be  mov     [rsp+60h+lpString2], rax; pcbResult
0x1801ec6c3  mov     [rbp+phHash], rdi
0x1801ec6c7  mov     [rbx], rsi
0x1801ec6ca  mov     [rbp+pcbResult], edi
0x1801ec6cd  call    cs:__imp_BCryptGetProperty
0x1801ec6d3  test    eax, eax
0x1801ec6d5  jns     short loc_1801EC70E
0x1801ec6d7  mov     ecx, eax; int
0x1801ec6d9  call    ?HRESULT_FROM_NTSTATUS@@YAJJ@Z; HRESULT_FROM_NTSTATUS(long)
0x1801ec6de  mov     edi, eax
0x1801ec6e0  test    eax, eax
0x1801ec6e2  jns     short loc_1801EC70E
0x1801ec6e4  lea     rax, aMethodFailed; "Method failed"
0x1801ec6eb  mov     r9d, r12d
0x1801ec6ee  mov     qword ptr [rsp+60h+cchCount2], rax
0x1801ec6f3  lea     rcx, aMetadataintegr_16; "MetadataIntegrity::MetadataHashStrategy"...
0x1801ec6fa  mov     edx, 76h ; 'v'
0x1801ec6ff  mov     dword ptr [rsp+60h+lpString2], edi
0x1801ec703  mov     r8d, 800000h
0x1801ec709  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1801ec70e  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1801ec712  test    rcx, rcx
0x1801ec715  jz      short loc_1801EC71F
0x1801ec717  xor     edx, edx; dwFlags
0x1801ec719  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1801ec71f  mov     rcx, [rbp+phHash]; hHash
0x1801ec723  test    rcx, rcx
0x1801ec726  jz      short loc_1801EC72E
0x1801ec728  call    cs:__imp_BCryptDestroyHash
0x1801ec72e  mov     eax, edi
0x1801ec730  jmp     short loc_1801EC763
0x1801ec732  lea     rax, aUnsupportHashA; "Unsupport hash algorithm[%ws]"
0x1801ec739  mov     qword ptr [rsp+60h+dwFlags], rdi
0x1801ec73e  mov     qword ptr [rsp+60h+cchCount2], rax
0x1801ec743  mov     r9d, r12d
0x1801ec746  xor     edx, edx
0x1801ec748  mov     [rsp+60h+lpString2], 0
0x1801ec751  xor     ecx, ecx
0x1801ec753  mov     r8d, 800000h
0x1801ec759  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1801ec75e  mov     eax, 80247141h
0x1801ec763  mov     rcx, [rbp+var_8]
0x1801ec767  xor     rcx, rsp; StackCookie
0x1801ec76a  call    __security_check_cookie
0x1801ec76f  mov     rbx, [rsp+60h+arg_10]
0x1801ec777  add     rsp, 60h
0x1801ec77b  pop     r15
0x1801ec77d  pop     r12
0x1801ec77f  pop     rdi
0x1801ec780  pop     rsi
0x1801ec781  pop     rbp
0x1801ec782  retn
```
