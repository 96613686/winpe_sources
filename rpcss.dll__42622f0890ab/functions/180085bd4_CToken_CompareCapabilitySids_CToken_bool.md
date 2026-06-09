# CToken::CompareCapabilitySids(CToken *,bool)

- ea: `0x180085bd4`
- end: `0x180085f16`
- name: `?CompareCapabilitySids@CToken@@QEAAJPEAV1@_N@Z`
- size: `834`
- prototype: `__int64 __fastcall(CToken *__hidden this, struct CToken *, bool)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18008b9c4`

## callees

- `0x18002ba28`
- `0x180034540`
- `0x18006145c`
- `0x18007e3d4`
- `0x180085bd4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085c15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085ce9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085d74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085e46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085c15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085ce9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085d74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085e46`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180085c0f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180085cdf`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180085d6e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180085e38`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180085c0f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180085cdf`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180085d6e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180085e38`
- `KERNELBASE!LocalAlloc` at `0x180085caa`
- `KERNELBASE!LocalAlloc` at `0x180085e03`
- `KERNELBASE!LocalAlloc` at `0x180085caa`
- `KERNELBASE!LocalAlloc` at `0x180085e03`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180085ec1`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180085ef0`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180085efb`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180085ec1`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180085ef0`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180085efb`

## string_xrefs

- `0x180085c72`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x180085c90`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x180085d38`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x180085dcb`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x180085de9`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x180085e95`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x180085eaa`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x180085c6b`: `CToken::CompareCapabilitySids`
- `0x180085d31`: `CToken::CompareCapabilitySids`
- `0x180085dc4`: `CToken::CompareCapabilitySids`
- `0x180085e8e`: `CToken::CompareCapabilitySids`

## pseudocode

```c
__int64 __fastcall CToken::CompareCapabilitySids(HANDLE *this, HANDLE *a2)
{
  signed int LastError; // eax
  int v5; // ebx
  __int64 v6; // rdx
  unsigned int *v7; // rsi
  signed int v8; // eax
  __int64 v9; // rdx
  signed int v10; // eax
  unsigned int *v11; // rdi
  signed int v12; // eax
  unsigned int *v13; // rcx
  char v14; // al
  int ReturnLength; // [rsp+20h] [rbp-28h]
  int ReturnLengtha; // [rsp+20h] [rbp-28h]
  int ReturnLengthb; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  SIZE_T uBytes; // [rsp+60h] [rbp+18h] BYREF

  LODWORD(uBytes) = 0;
  GetTokenInformation(this[9], TokenCapabilities, 0, 0, (PDWORD)&uBytes);
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
  if ( v5 == -2147024774 )
  {
    v7 = (unsigned int *)LocalAlloc(0, (unsigned int)uBytes);
    if ( !v7 )
    {
      v5 = -2147024882;
      v6 = 523;
      goto LABEL_10;
    }
    if ( GetTokenInformation(this[9], TokenCapabilities, v7, uBytes, (PDWORD)&uBytes) )
    {
      GetTokenInformation(a2[9], TokenCapabilities, 0, 0, (PDWORD)&uBytes);
      v10 = GetLastError();
      v5 = v10;
      if ( v10 > 0 )
        v5 = (unsigned __int16)v10 | 0x80070000;
      if ( v5 == -2147024774 )
      {
        v11 = (unsigned int *)LocalAlloc(0, (unsigned int)uBytes);
        if ( v11 )
        {
          if ( GetTokenInformation(a2[9], TokenCapabilities, v11, uBytes, (PDWORD)&uBytes) )
          {
            v5 = 1;
            LOBYTE(ReturnLengthb) = 0;
            v14 = CompareSidAndAttributeArrays(v7 + 2, *v7, v11 + 2, *v11, ReturnLengthb, 1);
            v13 = v11;
            if ( v14 )
            {
              LocalFree(v11);
              v5 = 0;
              goto LABEL_47;
            }
          }
          else
          {
            v12 = GetLastError();
            v5 = v12;
            if ( v12 > 0 )
              v5 = (unsigned __int16)v12 | 0x80070000;
            if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
              ComTraceMessageT<long>(
                (__int64)"onecore\\com\\combase\\rpcss\\objex\\token.cxx",
                (__int64)"CToken::CompareCapabilitySids",
                0x223u,
                0,
                (__int64)L"%!HRESULT!",
                v5);
            if ( v5 < 0 )
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x224,
                (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\token.cxx",
                (const char *)(unsigned int)v5,
                ReturnLengthb);
            v13 = v11;
          }
          LocalFree(v13);
LABEL_47:
          LocalFree(v7);
          return (unsigned int)v5;
        }
        v5 = -2147024882;
        v9 = 542;
      }
      else
      {
        if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
          ComTraceMessageT<long>(
            (__int64)"onecore\\com\\combase\\rpcss\\objex\\token.cxx",
            (__int64)"CToken::CompareCapabilitySids",
            0x218u,
            0,
            (__int64)L"%!HRESULT!",
            v5);
        if ( v5 >= 0 )
          goto LABEL_47;
        v9 = 537;
      }
    }
    else
    {
      v8 = GetLastError();
      v5 = v8;
      if ( v8 > 0 )
        v5 = (unsigned __int16)v8 | 0x80070000;
      if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
        ComTraceMessageT<long>(
          (__int64)"onecore\\com\\combase\\rpcss\\objex\\token.cxx",
          (__int64)"CToken::CompareCapabilitySids",
          0x210u,
          0,
          (__int64)L"%!HRESULT!",
          v5);
      if ( v5 >= 0 )
        goto LABEL_47;
      v9 = 529;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\token.cxx",
      (const char *)(unsigned int)v5,
      ReturnLengtha);
    goto LABEL_47;
  }
  if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
    ComTraceMessageT<long>(
      (__int64)"onecore\\com\\combase\\rpcss\\objex\\token.cxx",
      (__int64)"CToken::CompareCapabilitySids",
      0x205u,
      0,
      (__int64)L"%!HRESULT!",
      v5);
  if ( v5 < 0 )
  {
    v6 = 518;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\token.cxx",
      (const char *)(unsigned int)v5,
      ReturnLength);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180085bd4  mov     rax, rsp
0x180085bd7  mov     [rax+8], rbx
0x180085bdb  mov     [rax+10h], rbp
0x180085bdf  mov     [rax+18h], r8b
0x180085be3  push    rsi
0x180085be4  push    rdi
0x180085be5  push    r15
0x180085be7  sub     rsp, 30h
0x180085beb  xor     r9d, r9d; TokenInformationLength
0x180085bee  mov     dword ptr [rax+18h], 0
0x180085bf5  mov     rbp, rdx
0x180085bf8  lea     rax, [rax+18h]
0x180085bfc  mov     rdi, rcx
0x180085bff  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180085c04  mov     rcx, [rcx+48h]; TokenHandle
0x180085c08  xor     r8d, r8d; TokenInformation
0x180085c0b  lea     edx, [r9+1Eh]; TokenInformationClass
0x180085c0f  call    cs:__imp_GetTokenInformation
0x180085c15  call    cs:__imp_GetLastError
0x180085c1b  mov     ebx, eax
0x180085c1d  mov     r15d, 80070000h
0x180085c23  test    eax, eax
0x180085c25  jle     short loc_180085C2D
0x180085c27  movzx   ebx, ax
0x180085c2a  or      ebx, r15d
0x180085c2d  cmp     ebx, 8007007Ah
0x180085c33  jz      short loc_180085CA4
0x180085c35  mov     eax, cs:dword_18014E4B8
0x180085c3b  test    eax, eax
0x180085c3d  jnz     short loc_180085C52
0x180085c3f  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x180085c45  jz      short loc_180085C7E
0x180085c47  xor     ecx, ecx
0x180085c49  call    IsWppLevelEnabled
0x180085c4e  test    al, al
0x180085c50  jz      short loc_180085C7E
0x180085c52  lea     rax, aHresult; "%!HRESULT!"
0x180085c59  mov     [rsp+48h+var_20], ebx
0x180085c5d  xor     r9d, r9d
0x180085c60  mov     [rsp+48h+ReturnLength], rax; int
0x180085c65  mov     r8d, 205h
0x180085c6b  lea     rdx, aCtokenComparec; "CToken::CompareCapabilitySids"
0x180085c72  lea     rcx, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x180085c79  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x180085c7e  test    ebx, ebx
0x180085c80  jns     loc_180085F01
0x180085c86  mov     edx, 206h; void *
0x180085c8b  mov     rcx, [rsp+48h]; this
0x180085c90  lea     r8, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x180085c97  mov     r9d, ebx; char *
0x180085c9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180085c9f  jmp     loc_180085F01
0x180085ca4  mov     edx, dword ptr [rsp+48h+uBytes]; uBytes
0x180085ca8  xor     ecx, ecx; uFlags
0x180085caa  call    cs:__imp_LocalAlloc
0x180085cb0  mov     rsi, rax
0x180085cb3  test    rax, rax
0x180085cb6  jnz     short loc_180085CC4
0x180085cb8  mov     ebx, 8007000Eh
0x180085cbd  mov     edx, 20Bh
0x180085cc2  jmp     short loc_180085C8B
0x180085cc4  mov     r9d, dword ptr [rsp+48h+uBytes]; TokenInformationLength
0x180085cc9  lea     rax, [rsp+48h+uBytes]
0x180085cce  mov     rcx, [rdi+48h]; TokenHandle
0x180085cd2  mov     r8, rsi; TokenInformation
0x180085cd5  mov     edx, 1Eh; TokenInformationClass
0x180085cda  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180085cdf  call    cs:__imp_GetTokenInformation
0x180085ce5  test    eax, eax
0x180085ce7  jnz     short loc_180085D56
0x180085ce9  call    cs:__imp_GetLastError
0x180085cef  mov     ebx, eax
0x180085cf1  test    eax, eax
0x180085cf3  jle     short loc_180085CFB
0x180085cf5  movzx   ebx, ax
0x180085cf8  or      ebx, r15d
0x180085cfb  mov     eax, cs:dword_18014E4B8
0x180085d01  test    eax, eax
0x180085d03  jnz     short loc_180085D18
0x180085d05  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x180085d0b  jz      short loc_180085D44
0x180085d0d  xor     ecx, ecx
0x180085d0f  call    IsWppLevelEnabled
0x180085d14  test    al, al
0x180085d16  jz      short loc_180085D44
0x180085d18  lea     rax, aHresult; "%!HRESULT!"
0x180085d1f  mov     [rsp+48h+var_20], ebx
0x180085d23  xor     r9d, r9d
0x180085d26  mov     [rsp+48h+ReturnLength], rax
0x180085d2b  mov     r8d, 210h
0x180085d31  lea     rdx, aCtokenComparec; "CToken::CompareCapabilitySids"
0x180085d38  lea     rcx, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x180085d3f  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x180085d44  test    ebx, ebx
0x180085d46  jns     loc_180085EF8
0x180085d4c  mov     edx, 211h
0x180085d51  jmp     loc_180085DE4
0x180085d56  mov     rcx, [rbp+48h]; TokenHandle
0x180085d5a  lea     rax, [rsp+48h+uBytes]
0x180085d5f  xor     r9d, r9d; TokenInformationLength
0x180085d62  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180085d67  xor     r8d, r8d; TokenInformation
0x180085d6a  lea     edx, [r9+1Eh]; TokenInformationClass
0x180085d6e  call    cs:__imp_GetTokenInformation
0x180085d74  call    cs:__imp_GetLastError
0x180085d7a  mov     ebx, eax
0x180085d7c  test    eax, eax
0x180085d7e  jle     short loc_180085D86
0x180085d80  movzx   ebx, ax
0x180085d83  or      ebx, r15d
0x180085d86  cmp     ebx, 8007007Ah
0x180085d8c  jz      short loc_180085DFD
0x180085d8e  mov     eax, cs:dword_18014E4B8
0x180085d94  test    eax, eax
0x180085d96  jnz     short loc_180085DAB
0x180085d98  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x180085d9e  jz      short loc_180085DD7
0x180085da0  xor     ecx, ecx
0x180085da2  call    IsWppLevelEnabled
0x180085da7  test    al, al
0x180085da9  jz      short loc_180085DD7
0x180085dab  lea     rax, aHresult; "%!HRESULT!"
0x180085db2  mov     [rsp+48h+var_20], ebx
0x180085db6  xor     r9d, r9d
0x180085db9  mov     [rsp+48h+ReturnLength], rax; int
0x180085dbe  mov     r8d, 218h
0x180085dc4  lea     rdx, aCtokenComparec; "CToken::CompareCapabilitySids"
0x180085dcb  lea     rcx, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x180085dd2  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x180085dd7  test    ebx, ebx
0x180085dd9  jns     loc_180085EF8
0x180085ddf  mov     edx, 219h; void *
0x180085de4  mov     rcx, [rsp+48h]; this
0x180085de9  lea     r8, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x180085df0  mov     r9d, ebx; char *
0x180085df3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180085df8  jmp     loc_180085EF8
0x180085dfd  mov     edx, dword ptr [rsp+48h+uBytes]; uBytes
0x180085e01  xor     ecx, ecx; uFlags
0x180085e03  call    cs:__imp_LocalAlloc
0x180085e09  mov     rdi, rax
0x180085e0c  test    rax, rax
0x180085e0f  jnz     short loc_180085E1D
0x180085e11  mov     ebx, 8007000Eh
0x180085e16  mov     edx, 21Eh
0x180085e1b  jmp     short loc_180085DE4
0x180085e1d  mov     r9d, dword ptr [rsp+48h+uBytes]; TokenInformationLength
0x180085e22  lea     rax, [rsp+48h+uBytes]
0x180085e27  mov     rcx, [rbp+48h]; TokenHandle
0x180085e2b  mov     r8, rdi; TokenInformation
0x180085e2e  mov     edx, 1Eh; TokenInformationClass
0x180085e33  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180085e38  call    cs:__imp_GetTokenInformation
0x180085e3e  test    eax, eax
0x180085e40  jnz     loc_180085EC9
0x180085e46  call    cs:__imp_GetLastError
0x180085e4c  mov     ebx, eax
0x180085e4e  test    eax, eax
0x180085e50  jle     short loc_180085E58
0x180085e52  movzx   ebx, ax
0x180085e55  or      ebx, r15d
0x180085e58  mov     eax, cs:dword_18014E4B8
0x180085e5e  test    eax, eax
0x180085e60  jnz     short loc_180085E75
0x180085e62  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x180085e68  jz      short loc_180085EA1
0x180085e6a  xor     ecx, ecx
0x180085e6c  call    IsWppLevelEnabled
0x180085e71  test    al, al
0x180085e73  jz      short loc_180085EA1
0x180085e75  lea     rax, aHresult; "%!HRESULT!"
0x180085e7c  mov     [rsp+48h+var_20], ebx
0x180085e80  xor     r9d, r9d
0x180085e83  mov     [rsp+48h+ReturnLength], rax; int
0x180085e88  mov     r8d, 223h
0x180085e8e  lea     rdx, aCtokenComparec; "CToken::CompareCapabilitySids"
0x180085e95  lea     rcx, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x180085e9c  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x180085ea1  test    ebx, ebx
0x180085ea3  jns     short loc_180085EBE
0x180085ea5  mov     rcx, [rsp+48h]; this
0x180085eaa  lea     r8, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x180085eb1  mov     r9d, ebx; char *
0x180085eb4  mov     edx, 224h; void *
0x180085eb9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180085ebe  mov     rcx, rdi; hMem
0x180085ec1  call    cs:__imp_LocalFree
0x180085ec7  jmp     short loc_180085EF8
0x180085ec9  mov     r9d, [rdi]
0x180085ecc  lea     r8, [rdi+8]
0x180085ed0  mov     edx, [rsi]
0x180085ed2  lea     rcx, [rsi+8]
0x180085ed6  mov     ebx, 1
0x180085edb  mov     [rsp+48h+var_20], ebx
0x180085edf  mov     byte ptr [rsp+48h+ReturnLength], 0
0x180085ee4  call    ?CompareSidAndAttributeArrays@@YA_NPEAU_SID_AND_ATTRIBUTES@@K0K_NW4RuntimeBehavior@AppModel@@@Z; CompareSidAndAttributeArrays(_SID_AND_ATTRIBUTES *,ulong,_SID_AND_ATTRIBUTES *,ulong,bool,AppModel::RuntimeBehavior)
0x180085ee9  mov     rcx, rdi; hMem
0x180085eec  test    al, al
0x180085eee  jz      short loc_180085EC1
0x180085ef0  call    cs:__imp_LocalFree
0x180085ef6  xor     ebx, ebx
0x180085ef8  mov     rcx, rsi; hMem
0x180085efb  call    cs:__imp_LocalFree
0x180085f01  mov     rbp, [rsp+48h+arg_8]
0x180085f06  mov     eax, ebx
0x180085f08  mov     rbx, [rsp+48h+arg_0]
0x180085f0d  add     rsp, 30h
0x180085f11  pop     r15
0x180085f13  pop     rdi
0x180085f14  pop     rsi
0x180085f15  retn
```
