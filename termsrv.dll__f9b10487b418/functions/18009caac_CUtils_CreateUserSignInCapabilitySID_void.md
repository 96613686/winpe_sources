# CUtils::CreateUserSignInCapabilitySID(void * *)

- ea: `0x18009caac`
- end: `0x18009cc3a`
- name: `?CreateUserSignInCapabilitySID@CUtils@@SAJPEAPEAX@Z`
- size: `398`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005ca70`
- `0x1800b9104`

## callees

- `0x18000a210`
- `0x180032724`
- `0x18009caac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009cb2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009cb7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009cb2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009cb7a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009cbc6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009cbe3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009cc0c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009cc29`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009cbc6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009cbe3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009cc0c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009cc29`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18009cb70`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18009cb70`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18009cb52`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18009cb52`
- `api-ms-win-security-base-l1-2-2!DeriveCapabilitySidsFromName` at `0x18009cb23`
- `api-ms-win-security-base-l1-2-2!DeriveCapabilitySidsFromName` at `0x18009cb23`

## string_xrefs

- `0x18009cb89`: `CopySid failed: 0x%x in %s`
- `0x18009cae5`: `ppUserSignInCapabilitySid`
- `0x18009cade`: `CUtils::CreateUserSignInCapabilitySID`
- `0x18009cba1`: `CUtils::CreateUserSignInCapabilitySID`
- `0x18009cb3c`: `CreateUserSignInCapabilitySID - DeriveCapabilitySidsFromName failed: 0x%x in %s`
- `0x18009cb97`: `Too many sids??? failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CUtils::CreateUserSignInCapabilitySID(void **a1)
{
  unsigned int v2; // edi
  signed int v3; // eax
  size_t LengthSid; // rbx
  void *v5; // rax
  PSID *v6; // r8
  signed int LastError; // eax
  HLOCAL *v8; // rcx
  __int64 i; // rsi
  HLOCAL *v10; // rcx
  __int64 j; // rsi
  unsigned int v13; // [rsp+60h] [rbp+28h] BYREF
  unsigned int v14; // [rsp+68h] [rbp+30h] BYREF
  HLOCAL v15; // [rsp+70h] [rbp+38h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp+40h] BYREF

  hMem = 0;
  v13 = 0;
  v15 = 0;
  v14 = 0;
  if ( a1 )
  {
    v2 = 0;
    if ( (unsigned int)DeriveCapabilitySidsFromName(L"UserSignInSupport", &hMem, &v13, &v15, &v14)
      || (v3 = GetLastError(), v2 = v3, v3 >= 0) )
    {
      if ( v14 == 1 )
      {
        LengthSid = GetLengthSid(*(PSID *)v15);
        v5 = operator new(LengthSid);
        v6 = (PSID *)v15;
        *a1 = v5;
        if ( !CopySid(LengthSid, v5, *v6) )
        {
          LastError = GetLastError();
          v2 = LastError;
          if ( LastError < 0 )
            _DbgPrintMessage(
              8,
              "CopySid failed: 0x%x in %s",
              (unsigned int)LastError,
              "CUtils::CreateUserSignInCapabilitySID");
        }
      }
      else
      {
        v2 = -2147467259;
        _DbgPrintMessage(
          8,
          "Too many sids??? failed: 0x%x in %s",
          2147500037LL,
          "CUtils::CreateUserSignInCapabilitySID");
      }
    }
    else
    {
      _DbgPrintMessage(
        8,
        "CreateUserSignInCapabilitySID - DeriveCapabilitySidsFromName failed: 0x%x in %s",
        (unsigned int)v3,
        "CUtils::CreateUserSignInCapabilitySID");
    }
  }
  else
  {
    _DbgPrintMessage(
      8,
      "Missing paramter %s in %s",
      "ppUserSignInCapabilitySid",
      "CUtils::CreateUserSignInCapabilitySID");
    v2 = -2147024809;
  }
  v8 = (HLOCAL *)hMem;
  if ( hMem )
  {
    for ( i = 0; (unsigned int)i < v13; v8 = (HLOCAL *)hMem )
    {
      LocalFree(v8[i]);
      *((_QWORD *)hMem + i) = 0;
      i = (unsigned int)(i + 1);
    }
    LocalFree(v8);
    hMem = 0;
    v13 = 0;
  }
  v10 = (HLOCAL *)v15;
  if ( v15 )
  {
    for ( j = 0; (unsigned int)j < v14; v10 = (HLOCAL *)v15 )
    {
      LocalFree(v10[j]);
      *((_QWORD *)v15 + j) = 0;
      j = (unsigned int)(j + 1);
    }
    LocalFree(v10);
  }
  return v2;
}

```

## disassembly

```asm
0x18009caac  push    rbp
0x18009caae  push    rbx
0x18009caaf  push    rsi
0x18009cab0  push    rdi
0x18009cab1  mov     rbp, rsp
0x18009cab4  sub     rsp, 38h
0x18009cab8  mov     [rbp+hMem], 0
0x18009cac0  mov     rsi, rcx
0x18009cac3  mov     [rbp+arg_0], 0
0x18009caca  mov     [rbp+arg_10], 0
0x18009cad2  mov     [rbp+arg_8], 0
0x18009cad9  test    rcx, rcx
0x18009cadc  jnz     short loc_18009CB05
0x18009cade  lea     r9, aCutilsCreateus; "CUtils::CreateUserSignInCapabilitySID"
0x18009cae5  lea     r8, aPpusersigninca; "ppUserSignInCapabilitySid"
0x18009caec  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x18009caf3  lea     ecx, [rsi+8]; int
0x18009caf6  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18009cafb  mov     edi, 80070057h
0x18009cb00  jmp     loc_18009CBB2
0x18009cb05  lea     rax, [rbp+arg_8]
0x18009cb09  xor     edi, edi
0x18009cb0b  lea     r9, [rbp+arg_10]
0x18009cb0f  mov     [rsp+38h+var_18], rax
0x18009cb14  lea     r8, [rbp+arg_0]
0x18009cb18  lea     rdx, [rbp+hMem]
0x18009cb1c  lea     rcx, aUsersigninsupp; "UserSignInSupport"
0x18009cb23  call    cs:__imp_DeriveCapabilitySidsFromName
0x18009cb29  test    eax, eax
0x18009cb2b  jnz     short loc_18009CB45
0x18009cb2d  call    cs:__imp_GetLastError
0x18009cb33  mov     edi, eax
0x18009cb35  test    eax, eax
0x18009cb37  jns     short loc_18009CB45
0x18009cb39  mov     r8d, eax
0x18009cb3c  lea     rdx, aCreateusersign; "CreateUserSignInCapabilitySID - DeriveC"...
0x18009cb43  jmp     short loc_18009CBA1
0x18009cb45  cmp     [rbp+arg_8], 1
0x18009cb49  jnz     short loc_18009CB92
0x18009cb4b  mov     rcx, [rbp+arg_10]
0x18009cb4f  mov     rcx, [rcx]; pSid
0x18009cb52  call    cs:__imp_GetLengthSid
0x18009cb58  mov     ecx, eax; Size
0x18009cb5a  mov     ebx, eax
0x18009cb5c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18009cb61  mov     r8, [rbp+arg_10]
0x18009cb65  mov     rdx, rax; pDestinationSid
0x18009cb68  mov     [rsi], rax
0x18009cb6b  mov     ecx, ebx; nDestinationSidLength
0x18009cb6d  mov     r8, [r8]; pSourceSid
0x18009cb70  call    cs:__imp_CopySid
0x18009cb76  test    eax, eax
0x18009cb78  jnz     short loc_18009CBB2
0x18009cb7a  call    cs:__imp_GetLastError
0x18009cb80  mov     edi, eax
0x18009cb82  test    eax, eax
0x18009cb84  jns     short loc_18009CBB2
0x18009cb86  mov     r8d, eax
0x18009cb89  lea     rdx, aCopysidFailed0; "CopySid failed: 0x%x in %s"
0x18009cb90  jmp     short loc_18009CBA1
0x18009cb92  mov     edi, 80004005h
0x18009cb97  lea     rdx, aTooManySidsFai; "Too many sids??? failed: 0x%x in %s"
0x18009cb9e  mov     r8d, edi
0x18009cba1  lea     r9, aCutilsCreateus; "CUtils::CreateUserSignInCapabilitySID"
0x18009cba8  mov     ecx, 8; int
0x18009cbad  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18009cbb2  mov     rcx, [rbp+hMem]
0x18009cbb6  test    rcx, rcx
0x18009cbb9  jz      short loc_18009CBF8
0x18009cbbb  xor     esi, esi
0x18009cbbd  cmp     [rbp+arg_0], esi
0x18009cbc0  jbe     short loc_18009CBE3
0x18009cbc2  mov     rcx, [rcx+rsi*8]; hMem
0x18009cbc6  call    cs:__imp_LocalFree
0x18009cbcc  mov     rax, [rbp+hMem]
0x18009cbd0  mov     qword ptr [rax+rsi*8], 0
0x18009cbd8  inc     esi
0x18009cbda  mov     rcx, [rbp+hMem]; hMem
0x18009cbde  cmp     esi, [rbp+arg_0]
0x18009cbe1  jb      short loc_18009CBC2
0x18009cbe3  call    cs:__imp_LocalFree
0x18009cbe9  mov     [rbp+hMem], 0
0x18009cbf1  mov     [rbp+arg_0], 0
0x18009cbf8  mov     rcx, [rbp+arg_10]
0x18009cbfc  test    rcx, rcx
0x18009cbff  jz      short loc_18009CC2F
0x18009cc01  xor     esi, esi
0x18009cc03  cmp     [rbp+arg_8], esi
0x18009cc06  jbe     short loc_18009CC29
0x18009cc08  mov     rcx, [rcx+rsi*8]; hMem
0x18009cc0c  call    cs:__imp_LocalFree
0x18009cc12  mov     rax, [rbp+arg_10]
0x18009cc16  mov     qword ptr [rax+rsi*8], 0
0x18009cc1e  inc     esi
0x18009cc20  mov     rcx, [rbp+arg_10]; hMem
0x18009cc24  cmp     esi, [rbp+arg_8]
0x18009cc27  jb      short loc_18009CC08
0x18009cc29  call    cs:__imp_LocalFree
0x18009cc2f  mov     eax, edi
0x18009cc31  add     rsp, 38h
0x18009cc35  pop     rdi
0x18009cc36  pop     rsi
0x18009cc37  pop     rbx
0x18009cc38  pop     rbp
0x18009cc39  retn
```
