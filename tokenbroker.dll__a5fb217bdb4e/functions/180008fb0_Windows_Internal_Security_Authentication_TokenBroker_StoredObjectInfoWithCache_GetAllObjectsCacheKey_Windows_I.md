# Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfoWithCache::GetAllObjectsCacheKey(Windows::Internal::Security::Authentication::TokenBroker::StoredObjectType,HSTRING__ * const,Windows::Internal::String &)

- ea: `0x180008fb0`
- end: `0x1800096db`
- name: `?GetAllObjectsCacheKey@StoredObjectInfoWithCache@TokenBroker@Authentication@Security@Internal@Windows@@SAJW4StoredObjectType@23456@QEAUHSTRING__@@AEAVString@56@@Z`
- size: `1835`
- prototype: `static int __high(enum Windows::Internal::Security::Authentication::TokenBroker::StoredObjectType, HSTRING, struct Windows::Internal::String *)`
- caller_count: `3`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180076f60`
- `0x1800787a0`
- `0x180111d50`

## callees

- `0x18000730c`
- `0x180008fb0`
- `0x1800096e4`
- `0x180009770`
- `0x180009e80`
- `0x18000bd40`
- `0x18007ad10`
- `0x18008e690`
- `0x18009c748`
- `0x18009da88`
- `0x1800d6d80`
- `0x18011b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x1800090cb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180009262`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180009262`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009311`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800093ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009311`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800093ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180009275`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180009275`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18000904c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18000904c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180009073`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800091ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180009073`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800091ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000902b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009068`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009189`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009368`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000939f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000943d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000945e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009566`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000963d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000968c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000969f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000902b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009068`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009189`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009368`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000939f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000943d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000945e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009566`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000963d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000968c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000969f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000938b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180009422`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000938b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180009422`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009329`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009359`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000944f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000948a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800095a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000960f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009329`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009359`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000944f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000948a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800095a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000960f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800092d9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800092d9`
- `CRYPT32!CryptBinaryToStringW` at `0x1800092bf`
- `CRYPT32!CryptBinaryToStringW` at `0x180009303`
- `CRYPT32!CryptBinaryToStringW` at `0x1800092bf`
- `CRYPT32!CryptBinaryToStringW` at `0x180009303`

## string_xrefs

- `0x180009668`: `onecore\ds\security\tokenbroker\inc\appcallbackuri.h`
- `0x1800096c3`: `onecore\ds\security\tokenbroker\inc\appcallbackuri.h`
- `0x180009340`: `onecore\ds\security\tokenbroker\datastore\lib\filestore.cpp`
- `0x1800094d4`: `onecore\ds\security\tokenbroker\datastore\lib\filestore.cpp`
- `0x1800094fb`: `onecore\ds\security\tokenbroker\datastore\lib\filestore.cpp`
- `0x18000954c`: `onecore\ds\security\tokenbroker\datastore\lib\filestore.cpp`
- `0x1800095bb`: `onecore\ds\security\tokenbroker\datastore\lib\filestore.cpp`
- `0x180009623`: `onecore\ds\security\tokenbroker\datastore\lib\filestore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfoWithCache::GetAllObjectsCacheKey(
        unsigned int a1,
        HSTRING a2,
        HSTRING *a3)
{
  int v4; // edx
  int ObjectTypeDirectoryNameFromObjectType; // eax
  unsigned int v6; // ebx
  HSTRING v7; // rdi
  HRESULT v8; // eax
  HRESULT v9; // r14d
  HSTRING v10; // rsi
  PCWSTR StringRawBuffer; // rax
  __int64 v12; // r8
  __int64 v13; // rdx
  PCNZWCH v14; // r8
  PCNZWCH *v15; // r15
  const WCHAR *v16; // r12
  PCNZWCH *v17; // r14
  HRESULT v18; // r15d
  PCNZWCH *v19; // rcx
  unsigned __int64 v20; // r13
  unsigned __int64 v21; // rdx
  HSTRING v22; // rbx
  __int64 v23; // r8
  PCWSTR v24; // rax
  __int64 v25; // r8
  const WCHAR *v26; // rsi
  unsigned __int64 v27; // rdi
  int v28; // eax
  unsigned int v29; // edi
  DWORD v30; // edi
  BYTE *v31; // r14
  WCHAR *v32; // rsi
  signed int LastError; // eax
  signed int v34; // eax
  HSTRING v35; // rcx
  int pcchString; // [rsp+20h] [rbp-99h]
  int pcchStringa; // [rsp+20h] [rbp-99h]
  int pcchStringb; // [rsp+20h] [rbp-99h]
  HSTRING newString; // [rsp+30h] [rbp-89h] BYREF
  DWORD cbBinary; // [rsp+38h] [rbp-81h]
  HSTRING v42; // [rsp+40h] [rbp-79h] BYREF
  BYTE *pbBinary; // [rsp+48h] [rbp-71h]
  HSTRING v44; // [rsp+50h] [rbp-69h]
  HSTRING *v45; // [rsp+58h] [rbp-61h]
  __int64 v46; // [rsp+60h] [rbp-59h]
  HSTRING v47; // [rsp+68h] [rbp-51h]
  PCWSTR sourceString[2]; // [rsp+70h] [rbp-49h] BYREF
  __m128i v49; // [rsp+80h] [rbp-39h]
  PCNZWCH v50[2]; // [rsp+90h] [rbp-29h] BYREF
  __m128i si128; // [rsp+A0h] [rbp-19h]
  HSTRING string; // [rsp+B0h] [rbp-9h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+B8h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v45 = a3;
  cbBinary = 0;
  pbBinary = 0;
  *(_OWORD *)sourceString = 0;
  v49 = 0;
  std::wstring::_Construct_empty(sourceString, a1);
  v42 = 0;
  if ( v4 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x835,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\filestore.cpp",
      (const char *)0x80070032LL,
      pcchString);
    if ( v49.m128i_i64[1] > 7uLL )
      std::_Deallocate<16>(sourceString[0], 2 * v49.m128i_i64[1] + 2);
    return 2147942450LL;
  }
  else
  {
    ObjectTypeDirectoryNameFromObjectType = Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfo::GetObjectTypeDirectoryNameFromObjectType(
                                              0,
                                              &v42);
    v6 = ObjectTypeDirectoryNameFromObjectType;
    if ( ObjectTypeDirectoryNameFromObjectType >= 0 )
    {
      WindowsDeleteString(0);
      v44 = 0;
      v7 = 0;
      v46 = 0;
      newString = 0;
      v8 = WindowsDuplicateString(a2, &newString);
      v9 = v8;
      if ( v8 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x11B,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\inc\\appcallbackuri.h",
          (const char *)(unsigned int)v8,
          pcchString);
LABEL_72:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x83C,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\filestore.cpp",
          (const char *)(unsigned int)v9,
          pcchStringb);
        if ( v49.m128i_i64[1] > 7uLL )
          std::_Deallocate<16>(sourceString[0], 2 * v49.m128i_i64[1] + 2);
        return (unsigned int)v9;
      }
      v10 = newString;
      v47 = newString;
      WindowsDeleteString(0);
      StringRawBuffer = WindowsGetStringRawBuffer(v10, 0);
      *(_OWORD *)v50 = 0;
      si128 = 0;
      v12 = -1;
      do
        ++v12;
      while ( StringRawBuffer[v12] );
      std::wstring::_Construct<1,unsigned short const *>(v50, StringRawBuffer);
      v14 = v50[0];
      if ( si128.m128i_i64[1] > 7uLL )
      {
        v15 = (PCNZWCH *)v50[0];
        v16 = &v50[0][si128.m128i_i64[0]];
        v17 = (PCNZWCH *)v50[0];
      }
      else
      {
        v15 = v50;
        v16 = (const WCHAR *)v50 + si128.m128i_i64[0];
        v17 = v50;
      }
      if ( v17 != (PCNZWCH *)v16 )
      {
        do
        {
          *(_WORD *)v15 = ((__int64 (__fastcall *)(_QWORD, __int64, PCNZWCH))_o_towlower)(
                            *(unsigned __int16 *)v17,
                            v13,
                            v14);
          v15 = (PCNZWCH *)((char *)v15 + 2);
          v17 = (PCNZWCH *)((char *)v17 + 2);
        }
        while ( v17 != (PCNZWCH *)v16 );
        v14 = v50[0];
      }
      v18 = -2147467261;
      if ( si128.m128i_i64[1] <= 7uLL )
      {
        v19 = v50;
      }
      else
      {
        v19 = (PCNZWCH *)v14;
        if ( !v14 )
        {
          v9 = -2147467261;
LABEL_91:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x11E,
            (unsigned int)"onecore\\ds\\security\\tokenbroker\\inc\\appcallbackuri.h",
            (const char *)(unsigned int)v9,
            pcchString);
          std::wstring::_Tidy_deallocate(v50);
          if ( v7 )
            WindowsDeleteString(v7);
          if ( v10 )
            WindowsDeleteString(v10);
          goto LABEL_72;
        }
      }
      newString = 0;
      v20 = -1;
      v21 = -1;
      do
        ++v21;
      while ( *((_WORD *)v19 + v21) );
      if ( v21 <= 0xFFFFFFFF )
      {
        v9 = WindowsCreateString((PCNZWCH)v19, v21, &newString);
        if ( v9 >= 0 )
        {
          v7 = newString;
          WindowsDeleteString(0);
        }
        v14 = v50[0];
      }
      else
      {
        v9 = -2147024362;
      }
      if ( v9 >= 0 )
      {
        v22 = v7;
        v44 = v7;
        if ( si128.m128i_i64[1] > 7uLL )
          std::_Deallocate<16>(v14, 2 * si128.m128i_i64[1] + 2);
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        LOWORD(v50[0]) = 0;
        if ( v10 )
          WindowsDeleteString(v10);
        std::wstring::_Assign<unsigned short>(sourceString, L"@@TB", 4);
        v23 = -1;
        do
          ++v23;
        while ( *((_WORD *)v42 + v23) );
        std::wstring::_Append<unsigned short>(sourceString);
        std::wstring::_Append<unsigned short>(sourceString);
        v24 = WindowsGetStringRawBuffer(v7, 0);
        v25 = -1;
        do
          ++v25;
        while ( v24[v25] );
        std::wstring::_Append<unsigned short>(sourceString);
        std::wstring::_Append<unsigned short>(sourceString);
        v26 = (const WCHAR *)sourceString;
        if ( v49.m128i_i64[1] > 7uLL )
          v26 = sourceString[0];
        v27 = -1;
        do
          ++v27;
        while ( v26[v27] );
        if ( v27 > 0xFFFFFFFF )
        {
          LODWORD(v27) = -1;
          RaiseException(0xC000000D, 1u, 0, 0);
        }
        WindowsCreateStringReference(v26, v27, &hstringHeader, &string);
        v28 = Sha1HashString(string);
        v29 = v28;
        if ( v28 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x844,
            (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\filestore.cpp",
            (const char *)(unsigned int)v28,
            pcchString);
          if ( v22 )
            WindowsDeleteString(v22);
          if ( v49.m128i_i64[1] > 7uLL )
            std::_Deallocate<16>(sourceString[0], 2 * v49.m128i_i64[1] + 2);
          v49 = _mm_load_si128((const __m128i *)&_xmm);
          LOWORD(sourceString[0]) = 0;
          if ( pbBinary )
            LocalFree(pbBinary);
        }
        else
        {
          LODWORD(newString) = 0;
          v30 = cbBinary;
          v31 = pbBinary;
          if ( CryptBinaryToStringW(pbBinary, cbBinary, 0x40000001u, 0, (DWORD *)&newString)
            && (v32 = (WCHAR *)LocalAlloc(0x40u, 2LL * (unsigned int)newString)) != 0 )
          {
            if ( CryptBinaryToStringW(v31, v30, 0x40000001u, v32, (DWORD *)&newString) )
            {
              v42 = 0;
              do
                ++v20;
              while ( v32[v20] );
              if ( v20 <= 0xFFFFFFFF )
              {
                v18 = WindowsCreateString(v32, v20, &v42);
                if ( v18 >= 0 )
                {
                  v35 = *v45;
                  *v45 = v42;
                  WindowsDeleteString(v35);
                }
              }
              else
              {
                v18 = -2147024362;
              }
              if ( v18 >= 0 )
              {
                LocalFree(v32);
                if ( v22 )
                  WindowsDeleteString(v22);
                if ( v49.m128i_i64[1] > 7uLL )
                  std::_Deallocate<16>(sourceString[0], 2 * v49.m128i_i64[1] + 2);
                v49 = _mm_load_si128((const __m128i *)&_xmm);
                LOWORD(sourceString[0]) = 0;
                goto LABEL_66;
              }
LABEL_42:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x848,
                (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\filestore.cpp",
                (const char *)(unsigned int)v18,
                pcchStringa);
              if ( v32 )
                LocalFree(v32);
              if ( v22 )
                WindowsDeleteString(v22);
              std::wstring::_Tidy_deallocate(sourceString);
LABEL_66:
              if ( v31 )
                LocalFree(v31);
              return (unsigned int)v18;
            }
            LastError = GetLastError();
            v29 = LastError;
            if ( LastError > 0 )
              v29 = (unsigned __int16)LastError | 0x80070000;
            LocalFree(v32);
          }
          else
          {
            v34 = GetLastError();
            v29 = v34;
            if ( v34 > 0 )
              v29 = (unsigned __int16)v34 | 0x80070000;
          }
          if ( (v29 & 0x80000000) == 0 )
          {
            v32 = 0;
            goto LABEL_42;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x845,
            (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\filestore.cpp",
            (const char *)v29,
            pcchStringa);
          if ( v22 )
            WindowsDeleteString(v22);
          if ( v49.m128i_i64[1] > 7uLL )
            std::_Deallocate<16>(sourceString[0], 2 * v49.m128i_i64[1] + 2);
          v49 = _mm_load_si128((const __m128i *)&_xmm);
          LOWORD(sourceString[0]) = 0;
          if ( v31 )
          {
            LocalFree(v31);
            return v29;
          }
        }
        return v29;
      }
      goto LABEL_91;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x838,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\filestore.cpp",
      (const char *)(unsigned int)ObjectTypeDirectoryNameFromObjectType,
      pcchString);
    if ( v49.m128i_i64[1] > 7uLL )
      std::_Deallocate<16>(sourceString[0], 2 * v49.m128i_i64[1] + 2);
    return v6;
  }
}

```

## disassembly

```asm
0x180008fb0  mov     [rsp-8+arg_0], rbx
0x180008fb5  push    rbp
0x180008fb6  push    rsi
0x180008fb7  push    rdi
0x180008fb8  push    r12
0x180008fba  push    r13
0x180008fbc  push    r14
0x180008fbe  push    r15
0x180008fc0  lea     rbp, [rsp-27h]
0x180008fc5  sub     rsp, 0E0h
0x180008fcc  mov     rax, cs:__security_cookie
0x180008fd3  xor     rax, rsp
0x180008fd6  mov     [rbp+57h+var_40], rax
0x180008fda  mov     [rbp+57h+var_B8], r8
0x180008fde  mov     rsi, rdx
0x180008fe1  mov     edx, ecx
0x180008fe3  xor     r14d, r14d
0x180008fe6  mov     [rsp+110h+cbBinary], r14d
0x180008feb  mov     [rbp+57h+pbBinary], r14
0x180008fef  xorps   xmm0, xmm0
0x180008ff2  movups  xmmword ptr [rbp+57h+sourceString], xmm0
0x180008ff6  xorps   xmm1, xmm1
0x180008ff9  movdqu  [rbp+57h+var_90], xmm1
0x180008ffe  lea     rcx, [rbp+57h+sourceString]
0x180009002  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x180009007  nop
0x180009008  mov     [rbp+57h+var_D0], r14
0x18000900c  test    edx, edx
0x18000900e  jnz     loc_1800095B1
0x180009014  lea     rdx, [rbp+57h+var_D0]
0x180009018  xor     ecx, ecx
0x18000901a  call    ?GetObjectTypeDirectoryNameFromObjectType@StoredObjectInfo@TokenBroker@Authentication@Security@Internal@Windows@@KAJW4StoredObjectType@23456@PEAPEBG@Z; Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfo::GetObjectTypeDirectoryNameFromObjectType(Windows::Internal::Security::Authentication::TokenBroker::StoredObjectType,ushort const * *)
0x18000901f  mov     ebx, eax
0x180009021  test    eax, eax
0x180009023  js      loc_1800094CD
0x180009029  xor     ecx, ecx; string
0x18000902b  call    cs:__imp_WindowsDeleteString
0x180009031  mov     ebx, r14d
0x180009034  mov     [rbp+57h+var_C0], rbx
0x180009038  mov     edi, r14d
0x18000903b  mov     [rbp+57h+var_B0], r14
0x18000903f  mov     [rsp+110h+newString], r14
0x180009044  lea     rdx, [rsp+110h+newString]; newString
0x180009049  mov     rcx, rsi; string
0x18000904c  call    cs:__imp_WindowsDuplicateString
0x180009052  mov     r14d, eax
0x180009055  test    eax, eax
0x180009057  js      loc_1800096BC
0x18000905d  mov     rsi, [rsp+110h+newString]
0x180009062  mov     [rbp+57h+var_A8], rsi
0x180009066  xor     ecx, ecx; string
0x180009068  call    cs:__imp_WindowsDeleteString
0x18000906e  xor     edx, edx; length
0x180009070  mov     rcx, rsi; string
0x180009073  call    cs:__imp_WindowsGetStringRawBuffer
0x180009079  xorps   xmm0, xmm0
0x18000907c  movups  xmmword ptr [rbp+57h+var_80], xmm0
0x180009080  xorps   xmm1, xmm1
0x180009083  movdqu  [rbp+57h+var_70], xmm1
0x180009088  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18000908f  nop
0x180009090  inc     r8
0x180009093  cmp     word ptr [rax+r8*2], 0
0x180009099  jnz     short loc_180009090
0x18000909b  mov     rdx, rax
0x18000909e  lea     rcx, [rbp+57h+var_80]
0x1800090a2  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800090a7  nop
0x1800090a8  mov     r8, [rbp+57h+var_80]
0x1800090ac  mov     rax, qword ptr [rbp+57h+var_70]
0x1800090b0  cmp     qword ptr [rbp+57h+var_70+8], 7
0x1800090b5  ja      loc_1800093CC
0x1800090bb  lea     r15, [rbp+57h+var_80]
0x1800090bf  lea     rcx, [rbp+57h+var_80]
0x1800090c3  lea     r12, [rcx+rax*2]
0x1800090c7  lea     r14, [rbp+57h+var_80]
0x1800090cb  mov     r13, cs:__imp__o_towlower
0x1800090d2  cmp     r14, r12
0x1800090d5  jz      short loc_180009101
0x1800090d7  nop     word ptr [rax+rax+00000000h]
0x1800090e0  movzx   ecx, word ptr [r14]
0x1800090e4  mov     rax, r13
0x1800090e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090ec  mov     [r15], ax
0x1800090f0  lea     r15, [r15+2]
0x1800090f4  add     r14, 2
0x1800090f8  cmp     r14, r12
0x1800090fb  jnz     short loc_1800090E0
0x1800090fd  mov     r8, [rbp+57h+var_80]
0x180009101  mov     r15d, 80004003h
0x180009107  cmp     qword ptr [rbp+57h+var_70+8], 7
0x18000910c  jbe     loc_18000937D
0x180009112  mov     rcx, r8; sourceString
0x180009115  test    r8, r8
0x180009118  jz      loc_1800096AA
0x18000911e  mov     [rsp+110h+newString], 0
0x180009127  mov     r13, 0FFFFFFFFFFFFFFFFh
0x18000912e  mov     rdx, r13
0x180009131  inc     rdx; length
0x180009134  cmp     word ptr [rcx+rdx*2], 0
0x180009139  jnz     short loc_180009131
0x18000913b  mov     r12d, 0FFFFFFFFh
0x180009141  cmp     rdx, r12
0x180009144  jbe     loc_180009386
0x18000914a  mov     r14d, 80070216h
0x180009150  test    r14d, r14d
0x180009153  js      loc_180009661
0x180009159  mov     rbx, rdi
0x18000915c  mov     [rbp+57h+var_C0], rbx
0x180009160  mov     rdx, qword ptr [rbp+57h+var_70+8]
0x180009164  cmp     rdx, 7
0x180009168  ja      loc_1800093DB
0x18000916e  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180009176  movdqu  [rbp+57h+var_70], xmm0
0x18000917b  xor     eax, eax
0x18000917d  mov     word ptr [rbp+57h+var_80], ax
0x180009181  test    rsi, rsi
0x180009184  jz      short loc_18000919A
0x180009186  mov     rcx, rsi; string
0x180009189  call    cs:__imp_WindowsDeleteString
0x18000918f  jmp     short loc_18000919A
0x180009191  test    r14d, r14d
0x180009194  js      loc_1800094F4
0x18000919a  mov     r8d, 4
0x1800091a0  lea     rdx, aTb; "@@TB"
0x1800091a7  lea     rcx, [rbp+57h+sourceString]
0x1800091ab  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800091b0  mov     rdx, [rbp+57h+var_D0]
0x1800091b4  mov     r8, r13
0x1800091b7  nop     word ptr [rax+rax+00000000h]
0x1800091c0  inc     r8
0x1800091c3  cmp     word ptr [rdx+r8*2], 0
0x1800091c9  jnz     short loc_1800091C0
0x1800091cb  lea     rcx, [rbp+57h+sourceString]; Src
0x1800091cf  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800091d4  mov     r8d, 13h
0x1800091da  lea     rdx, aAllObjects; ":__ALL__OBJECTS__@@"
0x1800091e1  lea     rcx, [rbp+57h+sourceString]; Src
0x1800091e5  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800091ea  xor     edx, edx; length
0x1800091ec  mov     rcx, rbx; string
0x1800091ef  call    cs:__imp_WindowsGetStringRawBuffer
0x1800091f5  mov     r8, r13
0x1800091f8  nop     dword ptr [rax+rax+00000000h]
0x180009200  inc     r8
0x180009203  cmp     word ptr [rax+r8*2], 0
0x180009209  jnz     short loc_180009200
0x18000920b  mov     rdx, rax
0x18000920e  lea     rcx, [rbp+57h+sourceString]; Src
0x180009212  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180009217  mov     r8d, 2
0x18000921d  lea     rdx, asc_180130688; "@@"
0x180009224  lea     rcx, [rbp+57h+sourceString]; Src
0x180009228  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18000922d  lea     rsi, [rbp+57h+sourceString]
0x180009231  cmp     qword ptr [rbp+57h+var_90+8], 7
0x180009236  cmova   rsi, [rbp+57h+sourceString]
0x18000923b  mov     rdi, r13
0x18000923e  xchg    ax, ax
0x180009240  inc     rdi
0x180009243  cmp     word ptr [rsi+rdi*2], 0
0x180009248  jnz     short loc_180009240
0x18000924a  cmp     rdi, r12
0x18000924d  jbe     short loc_180009268
0x18000924f  mov     edi, r12d
0x180009252  xor     r9d, r9d; lpArguments
0x180009255  xor     r8d, r8d; nNumberOfArguments
0x180009258  mov     edx, 1; dwExceptionFlags
0x18000925d  mov     ecx, 0C000000Dh; dwExceptionCode
0x180009262  call    cs:__imp_RaiseException
0x180009268  lea     r9, [rbp+57h+string]; string
0x18000926c  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180009270  mov     edx, edi; length
0x180009272  mov     rcx, rsi; sourceString
0x180009275  call    cs:__imp_WindowsCreateStringReference
0x18000927b  lea     r8, [rsp+110h+cbBinary]
0x180009280  lea     rdx, [rbp+57h+pbBinary]
0x180009284  mov     rcx, [rbp+57h+string]; string
0x180009288  call    ?Sha1HashString@@YAJQEAUHSTRING__@@AEAV?$unique_ptr@PEAXULocalAllocDeleter@TokenBroker@Authentication@Security@Internal@Windows@@@std@@PEAK@Z; Sha1HashString(HSTRING__ * const,std::unique_ptr<void *,Windows::Internal::Security::Authentication::TokenBroker::LocalAllocDeleter> &,ulong *)
0x18000928d  mov     edi, eax
0x18000928f  test    eax, eax
0x180009291  js      loc_180009545
0x180009297  mov     dword ptr [rsp+110h+newString], 0
0x18000929f  mov     edi, [rsp+110h+cbBinary]
0x1800092a3  mov     r14, [rbp+57h+pbBinary]
0x1800092a7  lea     rax, [rsp+110h+newString]
0x1800092ac  mov     qword ptr [rsp+110h+pcchString], rax; pcchString
0x1800092b1  xor     r9d, r9d; pszString
0x1800092b4  mov     r8d, 40000001h; dwFlags
0x1800092ba  mov     edx, edi; cbBinary
0x1800092bc  mov     rcx, r14; pbBinary
0x1800092bf  call    cs:__imp_CryptBinaryToStringW
0x1800092c5  test    eax, eax
0x1800092c7  jz      loc_1800093AE
0x1800092cd  mov     edx, dword ptr [rsp+110h+newString]
0x1800092d1  add     rdx, rdx; uBytes
0x1800092d4  mov     ecx, 40h ; '@'; uFlags
0x1800092d9  call    cs:__imp_LocalAlloc
0x1800092df  mov     rsi, rax
0x1800092e2  test    rax, rax
0x1800092e5  jz      loc_1800093AE
0x1800092eb  lea     rax, [rsp+110h+newString]
0x1800092f0  mov     qword ptr [rsp+110h+pcchString], rax; int
0x1800092f5  mov     r9, rsi; pszString
0x1800092f8  mov     r8d, 40000001h; dwFlags
0x1800092fe  mov     edx, edi; cbBinary
0x180009300  mov     rcx, r14; pbBinary
0x180009303  call    cs:__imp_CryptBinaryToStringW
0x180009309  test    eax, eax
0x18000930b  jnz     loc_1800093F0
0x180009311  call    cs:__imp_GetLastError
0x180009317  mov     edi, eax
0x180009319  test    eax, eax
0x18000931b  jle     short loc_180009326
0x18000931d  movzx   edi, ax
0x180009320  or      edi, 80070000h
0x180009326  mov     rcx, rsi; hMem
0x180009329  call    cs:__imp_LocalFree
0x18000932f  test    edi, edi
0x180009331  js      loc_18000961C
0x180009337  xor     esi, esi
0x180009339  mov     rcx, [rbp+5Fh]; this
0x18000933d  mov     r9d, r15d; char *
0x180009340  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180009347  mov     edx, 848h; void *
0x18000934c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009351  test    rsi, rsi
0x180009354  jz      short loc_180009360
0x180009356  mov     rcx, rsi; hMem
0x180009359  call    cs:__imp_LocalFree
0x18000935f  nop
0x180009360  test    rbx, rbx
0x180009363  jz      short loc_18000936F
0x180009365  mov     rcx, rbx; string
0x180009368  call    cs:__imp_WindowsDeleteString
0x18000936e  nop
0x18000936f  lea     rcx, [rbp+57h+sourceString]
0x180009373  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180009378  jmp     loc_180009482
0x18000937d  lea     rcx, [rbp+57h+var_80]
0x180009381  jmp     loc_18000911E
0x180009386  lea     r8, [rsp+110h+newString]; string
0x18000938b  call    cs:__imp_WindowsCreateString
0x180009391  mov     r14d, eax
0x180009394  test    eax, eax
0x180009396  js      short loc_1800093A5
0x180009398  mov     rdi, [rsp+110h+newString]
0x18000939d  xor     ecx, ecx; string
0x18000939f  call    cs:__imp_WindowsDeleteString
0x1800093a5  mov     r8, [rbp+57h+var_80]
0x1800093a9  jmp     loc_180009150
0x1800093ae  call    cs:__imp_GetLastError
0x1800093b4  mov     edi, eax
0x1800093b6  test    eax, eax
0x1800093b8  jle     loc_18000932F
0x1800093be  movzx   edi, ax
0x1800093c1  or      edi, 80070000h
0x1800093c7  jmp     loc_18000932F
0x1800093cc  mov     r15, r8
0x1800093cf  lea     r12, [r8+rax*2]
0x1800093d3  mov     r14, r8
0x1800093d6  jmp     loc_1800090CB
0x1800093db  lea     rdx, ds:2[rdx*2]
0x1800093e3  mov     rcx, r8
0x1800093e6  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800093eb  jmp     loc_18000916E
0x1800093f0  mov     [rbp+57h+var_D0], 0
0x1800093f8  nop     dword ptr [rax+rax+00000000h]
0x180009400  inc     r13
0x180009403  cmp     word ptr [rsi+r13*2], 0
0x180009409  jnz     short loc_180009400
0x18000940b  cmp     r13, r12
0x18000940e  jbe     short loc_180009418
0x180009410  mov     r15d, 80070216h
0x180009416  jmp     short loc_180009443
0x180009418  mov     edx, r13d; length
0x18000941b  lea     r8, [rbp+57h+var_D0]; string
0x18000941f  mov     rcx, rsi; sourceString
0x180009422  call    cs:__imp_WindowsCreateString
0x180009428  mov     r15d, eax
0x18000942b  test    eax, eax
0x18000942d  js      short loc_180009443
0x18000942f  mov     rdx, [rbp+57h+var_B8]
0x180009433  mov     rcx, [rdx]; string
0x180009436  mov     rax, [rbp+57h+var_D0]
0x18000943a  mov     [rdx], rax
0x18000943d  call    cs:__imp_WindowsDeleteString
0x180009443  test    r15d, r15d
0x180009446  js      loc_180009339
0x18000944c  mov     rcx, rsi; hMem
0x18000944f  call    cs:__imp_LocalFree
0x180009455  nop
0x180009456  test    rbx, rbx
0x180009459  jz      short loc_180009465
0x18000945b  mov     rcx, rbx; string
0x18000945e  call    cs:__imp_WindowsDeleteString
0x180009464  nop
0x180009465  mov     rdx, qword ptr [rbp+57h+var_90+8]
0x180009469  cmp     rdx, 7
0x18000946d  ja      short loc_1800094BA
  ... truncated ...
```
