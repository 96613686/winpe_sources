# GetRealIdFromPairwiseId(Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId &,Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId &,HSTRING__ * const,HSTRING__ * const)

- ea: `0x1800724cc`
- end: `0x1800729d9`
- name: `?GetRealIdFromPairwiseId@@YAJAEAVStoredObjectId@TokenBroker@Authentication@Security@Internal@Windows@@0QEAUHSTRING__@@1@Z`
- size: `1293`
- prototype: `__int64 __fastcall(struct Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *, struct Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *this, HSTRING, HSTRING)`
- caller_count: `2`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x18002a790`
- `0x180060350`

## callees

- `0x18000730c`
- `0x180009e40`
- `0x18000bd40`
- `0x18002a3e0`
- `0x18002d940`
- `0x180035880`
- `0x180037174`
- `0x180042194`
- `0x1800426b0`
- `0x180044d30`
- `0x1800454f0`
- `0x18004cf80`
- `0x180051dd0`
- `0x180051f48`
- `0x18005a898`
- `0x18005d6c0`
- `0x180071b10`
- `0x1800724cc`
- `0x180072cd0`
- `0x18008e690`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800727a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800727a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180072546`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180072556`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180072575`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800725af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800726eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800727c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007282e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007292e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180072959`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180072546`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180072556`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180072575`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800725af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800726eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800727c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007282e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007292e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180072959`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072889`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007291b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800729b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072889`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007291b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800729b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18007278e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800727b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18007278e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800727b6`
- `api-ms-win-core-string-l2-1-0!CharLowerW` at `0x1800725d0`
- `api-ms-win-core-string-l2-1-0!CharLowerW` at `0x1800725d0`

## string_xrefs

- `0x180072520`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x180072600`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x1800728db`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x180072978`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall GetRealIdFromPairwiseId(
        struct Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *a1,
        struct Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *this,
        HSTRING a3,
        HSTRING a4)
{
  int BaseHexByteString; // eax
  unsigned int v9; // ebx
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  PCWSTR v13; // rax
  WCHAR *v14; // rcx
  int AllObjectIdsForType; // eax
  int v16; // ecx
  int v17; // r8d
  struct Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId **i; // rbx
  struct Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId **v19; // rsi
  int v20; // edi
  wchar_t *v21; // rcx
  __int64 v22; // rdi
  int v23; // edi
  const unsigned __int16 *v24; // rax
  const unsigned __int16 *v25; // rax
  __int64 v27; // rdx
  const unsigned __int16 *v28; // rax
  int v29; // eax
  __int64 v30; // rdx
  const unsigned __int16 *v31; // rax
  __int64 *v32; // [rsp+20h] [rbp-E0h]
  HSTRING newString; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *StringRawBuffer; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v35; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v36; // [rsp+58h] [rbp-A8h] BYREF
  int v37; // [rsp+60h] [rbp-A0h]
  __int128 v38; // [rsp+68h] [rbp-98h]
  __int64 v39; // [rsp+78h] [rbp-88h]
  __int128 v40; // [rsp+80h] [rbp-80h] BYREF
  __int64 v41; // [rsp+90h] [rbp-70h]
  PCWSTR v42; // [rsp+98h] [rbp-68h]
  __int64 v43; // [rsp+A0h] [rbp-60h] BYREF
  HSTRING v44; // [rsp+B0h] [rbp-50h] BYREF
  PUCHAR v45; // [rsp+B8h] [rbp-48h] BYREF
  ULONG v46; // [rsp+C0h] [rbp-40h]
  _QWORD v47[9]; // [rsp+C8h] [rbp-38h] BYREF
  HSTRING string; // [rsp+110h] [rbp+10h] BYREF
  int v49; // [rsp+118h] [rbp+18h]
  __int128 v50; // [rsp+120h] [rbp+20h]
  __int64 v51; // [rsp+130h] [rbp+30h]
  LPWSTR lpsz[4]; // [rsp+138h] [rbp+38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  newString = 0;
  BaseHexByteString = Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::GetBaseHexByteString(
                        a1,
                        (const unsigned __int16 **)&newString);
  v9 = BaseHexByteString;
  if ( BaseHexByteString < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3B2,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
      (const char *)(unsigned int)BaseHexByteString,
      (int)v32);
    return v9;
  }
  if ( (unsigned int)dword_180175000 > 5 )
  {
    StringRawBuffer = (unsigned __int16 *)WindowsGetStringRawBuffer(a4, 0);
    v35 = (__int64)WindowsGetStringRawBuffer(a3, 0);
    Windows::Internal::StringReference::_ConstructorHelper(
      (Windows::Internal::StringReference *)&string,
      (const unsigned __int16 *)newString);
    newString = (HSTRING)WindowsGetStringRawBuffer(string, 0);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      v10,
      (unsigned int)word_180158E22,
      v11,
      v12,
      (__int64)&newString,
      (__int64)&v35,
      (__int64)&StringRawBuffer);
  }
  v13 = WindowsGetStringRawBuffer(a4, 0);
  std::wstring::wstring(lpsz, v13);
  v14 = (WCHAR *)lpsz;
  if ( lpsz[3] > (LPWSTR)7 )
    v14 = lpsz[0];
  CharLowerW(v14);
  v40 = 0;
  v41 = 0;
  AllObjectIdsForType = Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfo::GetAllObjectIdsForType(
                          0,
                          a3,
                          &v40);
  v9 = AllObjectIdsForType;
  if ( AllObjectIdsForType < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3C6,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
      (const char *)(unsigned int)AllObjectIdsForType,
      (int)v32);
    goto LABEL_32;
  }
  if ( (unsigned int)dword_180175000 > 5 )
  {
    StringRawBuffer = (unsigned __int16 *)((__int64)(*((_QWORD *)&v40 + 1) - v40) >> 4);
    newString = (HSTRING)1;
    v35 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
      v16,
      (unsigned int)word_180158DCA,
      v17,
      (unsigned int)&v35,
      (__int64)&newString,
      (__int64)&StringRawBuffer);
  }
  v19 = (struct Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId **)*((_QWORD *)&v40 + 1);
  for ( i = (struct Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId **)v40; ; i += 2 )
  {
    if ( i == v19 )
    {
      v9 = -2147024894;
      goto LABEL_32;
    }
    newString = 0;
    string = 0;
    v49 = 0;
    v50 = 0;
    v51 = 0;
    v36 = 0;
    v37 = 0;
    v38 = 0;
    v39 = 0;
    AccountSystemOnlyInfo::AccountSystemOnlyInfo((AccountSystemOnlyInfo *)&v44);
    v20 = AccountSystemOnlyInfo::InitializeFromAccountId((AccountSystemOnlyInfo *)&v44, *i, a3);
    if ( v20 < 0 )
    {
      StringRawBuffer = 0;
      Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::GetBaseHexByteString(
        *i,
        (const unsigned __int16 **)&StringRawBuffer);
      if ( (unsigned int)dword_180175000 > 3 )
      {
        v42 = WindowsGetStringRawBuffer(a3, 0);
        v21 = L"null";
        if ( StringRawBuffer )
          v21 = StringRawBuffer;
        StringRawBuffer = v21;
        LODWORD(v35) = v20;
        v32 = &v35;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          &dword_180175000,
          word_180158D5A,
          0);
      }
      goto LABEL_27;
    }
    std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<PerAppAccountData>,StringComparerW,std::allocator<std::pair<std::wstring const,std::shared_ptr<PerAppAccountData>>>,0>>::find(
      v47,
      &v43,
      lpsz);
    if ( v43 != v47[0] )
    {
      v22 = *(_QWORD *)(v43 + 64);
      if ( !WindowsIsStringEmpty(*(HSTRING *)(v22 + 16)) )
      {
        v23 = WindowsDuplicateString(*(HSTRING *)(v22 + 16), &newString);
        if ( v23 < 0 )
        {
          v27 = 1022;
          goto LABEL_35;
        }
      }
    }
    if ( !WindowsIsStringEmpty(newString) )
    {
      v24 = WindowsGetStringRawBuffer(newString, 0);
      v23 = Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::InitializeFromStringId(
              (Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *)&string,
              v24);
      if ( v23 < 0 )
      {
        v27 = 1030;
LABEL_35:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v27,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
          (const char *)(unsigned int)v23,
          (int)v32);
        goto LABEL_36;
      }
      v23 = 0;
      if ( Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::AreEqual(
             (const struct Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *)&string,
             a1) )
      {
        break;
      }
    }
    v23 = CalculatePairwiseId(a3, v44, a4, &v45, v46, (__int64)&newString);
    if ( v23 < 0 )
    {
      v27 = 1056;
      goto LABEL_35;
    }
    v25 = WindowsGetStringRawBuffer(newString, 0);
    v23 = Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::InitializeFromStringId(
            (Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *)&string,
            v25);
    if ( v23 < 0 )
    {
      v27 = 1059;
      goto LABEL_35;
    }
    v23 = 0;
    if ( Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::AreEqual(
           (const struct Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *)&string,
           a1) )
    {
      v31 = WindowsGetStringRawBuffer(v44, 0);
      v29 = Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::InitializeFromStringId(this, v31);
      v9 = v29;
      if ( v29 < 0 )
      {
        v30 = 1065;
LABEL_44:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v30,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
          (const char *)(unsigned int)v29,
          (int)v32);
        AccountSystemOnlyInfo::~AccountSystemOnlyInfo((AccountSystemOnlyInfo *)&v44);
        Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::InternalRelease((Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *)&v36);
        Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::InternalRelease((Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *)&string);
        if ( newString )
          WindowsDeleteString(newString);
        goto LABEL_32;
      }
      goto LABEL_36;
    }
LABEL_27:
    AccountSystemOnlyInfo::~AccountSystemOnlyInfo((AccountSystemOnlyInfo *)&v44);
    Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::InternalRelease((Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *)&v36);
    Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::InternalRelease((Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *)&string);
    if ( newString )
      WindowsDeleteString(newString);
  }
  v28 = WindowsGetStringRawBuffer(v44, 0);
  v29 = Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::InitializeFromStringId(this, v28);
  v9 = v29;
  if ( v29 < 0 )
  {
    v30 = 1036;
    goto LABEL_44;
  }
LABEL_36:
  AccountSystemOnlyInfo::~AccountSystemOnlyInfo((AccountSystemOnlyInfo *)&v44);
  Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::InternalRelease((Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *)&v36);
  Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::InternalRelease((Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *)&string);
  if ( newString )
    WindowsDeleteString(newString);
  v9 = v23;
LABEL_32:
  std::vector<std::shared_ptr<Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId>>::_Tidy(&v40);
  std::wstring::_Tidy_deallocate(lpsz);
  return v9;
}

```

## disassembly

```asm
0x1800724cc  push    rbp
0x1800724ce  push    rbx
0x1800724cf  push    rsi
0x1800724d0  push    rdi
0x1800724d1  push    r12
0x1800724d3  push    r13
0x1800724d5  push    r14
0x1800724d7  push    r15
0x1800724d9  lea     rbp, [rsp-68h]
0x1800724de  sub     rsp, 168h
0x1800724e5  mov     rax, cs:__security_cookie
0x1800724ec  xor     rax, rsp
0x1800724ef  mov     [rbp+0A0h+var_48], rax
0x1800724f3  mov     r13, r9
0x1800724f6  mov     r14, r8
0x1800724f9  mov     r12, rdx
0x1800724fc  mov     r15, rcx
0x1800724ff  xor     edi, edi
0x180072501  mov     [rsp+1A0h+newString], rdi
0x180072506  lea     rdx, [rsp+1A0h+newString]; unsigned __int16 **
0x18007250b  call    ?GetBaseHexByteString@StoredObjectId@TokenBroker@Authentication@Security@Internal@Windows@@QEAAJPEAPEBG@Z; Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::GetBaseHexByteString(ushort const * *)
0x180072510  mov     ebx, eax
0x180072512  test    eax, eax
0x180072514  jns     short loc_180072536
0x180072516  mov     rcx, [rbp+0A8h]; this
0x18007251d  mov     r9d, eax; char *
0x180072520  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180072527  mov     edx, 3B2h; void *
0x18007252c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180072531  jmp     loc_1800728B4
0x180072536  mov     eax, cs:dword_180175000
0x18007253c  cmp     eax, 5
0x18007253f  jbe     short loc_1800725AA
0x180072541  xor     edx, edx; length
0x180072543  mov     rcx, r13; string
0x180072546  call    cs:__imp_WindowsGetStringRawBuffer
0x18007254c  mov     [rsp+1A0h+var_158], rax
0x180072551  xor     edx, edx; length
0x180072553  mov     rcx, r14; string
0x180072556  call    cs:__imp_WindowsGetStringRawBuffer
0x18007255c  mov     [rsp+1A0h+var_150], rax
0x180072561  mov     rdx, [rsp+1A0h+newString]; unsigned __int16 *
0x180072566  lea     rcx, [rbp+0A0h+string]; this
0x18007256a  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18007256f  xor     edx, edx; length
0x180072571  mov     rcx, [rbp+0A0h+string]; string
0x180072575  call    cs:__imp_WindowsGetStringRawBuffer
0x18007257b  mov     [rsp+1A0h+newString], rax
0x180072580  lea     rax, [rsp+1A0h+var_158]
0x180072585  mov     [rsp+1A0h+var_170], rax
0x18007258a  lea     rax, [rsp+1A0h+var_150]
0x18007258f  mov     [rsp+1A0h+var_178], rax
0x180072594  lea     rax, [rsp+1A0h+newString]
0x180072599  mov     qword ptr [rsp+1A0h+var_180], rax; int
0x18007259e  lea     rdx, word_180158E22
0x1800725a5  call    ??$Write@U?$_tlgWrapSz@G@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800725aa  xor     edx, edx; length
0x1800725ac  mov     rcx, r13; string
0x1800725af  call    cs:__imp_WindowsGetStringRawBuffer
0x1800725b5  mov     rdx, rax
0x1800725b8  lea     rcx, [rbp+0A0h+lpsz]
0x1800725bc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800725c1  nop
0x1800725c2  lea     rcx, [rbp+0A0h+lpsz]
0x1800725c6  cmp     [rbp+0A0h+var_50], 7
0x1800725cb  cmova   rcx, [rbp+0A0h+lpsz]; lpsz
0x1800725d0  call    cs:__imp_CharLowerW
0x1800725d6  xorps   xmm0, xmm0
0x1800725d9  movdqu  [rbp+0A0h+var_120], xmm0
0x1800725de  mov     [rbp+0A0h+var_110], rdi
0x1800725e2  lea     r8, [rbp+0A0h+var_120]
0x1800725e6  mov     rdx, r14
0x1800725e9  xor     ecx, ecx
0x1800725eb  call    ?GetAllObjectIdsForType@StoredObjectInfo@TokenBroker@Authentication@Security@Internal@Windows@@SAJW4StoredObjectType@23456@QEAUHSTRING__@@AEAV?$vector@V?$shared_ptr@VStoredObjectId@TokenBroker@Authentication@Security@Internal@Windows@@@std@@V?$allocator@V?$shared_ptr@VStoredObjectId@TokenBroker@Authentication@Security@Internal@Windows@@@std@@@2@@std@@@Z; Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfo::GetAllObjectIdsForType(Windows::Internal::Security::Authentication::TokenBroker::StoredObjectType,HSTRING__ * const,std::vector<std::shared_ptr<Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId>> &)
0x1800725f0  mov     ebx, eax
0x1800725f2  test    eax, eax
0x1800725f4  jns     short loc_180072616
0x1800725f6  mov     rcx, [rbp+0A8h]; this
0x1800725fd  mov     r9d, eax; char *
0x180072600  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180072607  mov     edx, 3C6h; void *
0x18007260c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180072611  jmp     loc_1800728A1
0x180072616  mov     eax, cs:dword_180175000
0x18007261c  cmp     eax, 5
0x18007261f  jbe     short loc_180072669
0x180072621  mov     rax, qword ptr [rbp+0A0h+var_120+8]
0x180072625  sub     rax, qword ptr [rbp+0A0h+var_120]
0x180072629  sar     rax, 4
0x18007262d  mov     [rsp+1A0h+var_158], rax
0x180072632  mov     [rsp+1A0h+newString], 1
0x18007263b  mov     [rsp+1A0h+var_150], 1000000h
0x180072644  lea     rax, [rsp+1A0h+var_158]
0x180072649  mov     [rsp+1A0h+var_178], rax
0x18007264e  lea     rax, [rsp+1A0h+newString]
0x180072653  mov     qword ptr [rsp+1A0h+var_180], rax
0x180072658  lea     r9, [rsp+1A0h+var_150]
0x18007265d  lea     rdx, word_180158DCA
0x180072664  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBX1IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteAgg@@YAJ011I2@ZPEBX@@SAJPEBU_tlgProvider_t@@PEBX1AEBU?$_tlgWrapperByVal@$07@@22@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,void const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x180072669  mov     rbx, qword ptr [rbp+0A0h+var_120]
0x18007266d  mov     rsi, qword ptr [rbp+0A0h+var_120+8]
0x180072671  jmp     loc_180072893
0x180072676  mov     [rsp+1A0h+newString], rdi
0x18007267b  mov     [rbp+0A0h+string], rdi
0x18007267f  mov     [rbp+0A0h+var_88], edi
0x180072682  xorps   xmm0, xmm0
0x180072685  movdqu  [rbp+0A0h+var_80], xmm0
0x18007268a  mov     [rbp+0A0h+var_70], rdi
0x18007268e  mov     [rsp+1A0h+var_148], rdi
0x180072693  mov     [rsp+1A0h+var_140], edi
0x180072697  movdqu  [rsp+1A0h+var_138], xmm0
0x18007269d  mov     [rsp+1A0h+var_128], rdi
0x1800726a2  lea     rcx, [rbp+0A0h+var_F0]; this
0x1800726a6  call    ??0AccountSystemOnlyInfo@@QEAA@XZ; AccountSystemOnlyInfo::AccountSystemOnlyInfo(void)
0x1800726ab  nop
0x1800726ac  mov     r8, r14; HSTRING
0x1800726af  mov     rdx, [rbx]; struct Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *
0x1800726b2  lea     rcx, [rbp+0A0h+var_F0]; this
0x1800726b6  call    ?InitializeFromAccountId@AccountSystemOnlyInfo@@QEAAJAEAVStoredObjectId@TokenBroker@Authentication@Security@Internal@Windows@@PEAUHSTRING__@@@Z; AccountSystemOnlyInfo::InitializeFromAccountId(Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId &,HSTRING__ *)
0x1800726bb  mov     edi, eax
0x1800726bd  test    eax, eax
0x1800726bf  jns     loc_18007276B
0x1800726c5  mov     [rsp+1A0h+var_158], 0
0x1800726ce  lea     rdx, [rsp+1A0h+var_158]; unsigned __int16 **
0x1800726d3  mov     rcx, [rbx]; this
0x1800726d6  call    ?GetBaseHexByteString@StoredObjectId@TokenBroker@Authentication@Security@Internal@Windows@@QEAAJPEAPEBG@Z; Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::GetBaseHexByteString(ushort const * *)
0x1800726db  mov     ecx, cs:dword_180175000
0x1800726e1  cmp     ecx, 3
0x1800726e4  jbe     short loc_180072745
0x1800726e6  xor     edx, edx; length
0x1800726e8  mov     rcx, r14; string
0x1800726eb  call    cs:__imp_WindowsGetStringRawBuffer
0x1800726f1  mov     [rbp+0A0h+var_108], rax
0x1800726f5  lea     rcx, aNull; "null"
0x1800726fc  mov     rax, [rsp+1A0h+var_158]
0x180072701  test    rax, rax
0x180072704  cmovnz  rcx, rax
0x180072708  mov     [rsp+1A0h+var_158], rcx
0x18007270d  mov     dword ptr [rsp+1A0h+var_150], edi
0x180072711  lea     rax, [rbp+0A0h+var_108]
0x180072715  mov     [rsp+1A0h+var_170], rax
0x18007271a  lea     rax, [rsp+1A0h+var_158]
0x18007271f  mov     [rsp+1A0h+var_178], rax
0x180072724  lea     rax, [rsp+1A0h+var_150]
0x180072729  mov     qword ptr [rsp+1A0h+var_180], rax
0x18007272e  xor     r8d, r8d
0x180072731  lea     rdx, word_180158D5A
0x180072738  lea     rcx, dword_180175000
0x18007273f  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180072744  nop
0x180072745  lea     rcx, [rbp+0A0h+var_F0]; this
0x180072749  call    ??1AccountSystemOnlyInfo@@QEAA@XZ; AccountSystemOnlyInfo::~AccountSystemOnlyInfo(void)
0x18007274e  nop
0x18007274f  lea     rcx, [rsp+1A0h+var_148]; this
0x180072754  call    ?InternalRelease@StoredObjectId@TokenBroker@Authentication@Security@Internal@Windows@@AEAAXXZ; Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::InternalRelease(void)
0x180072759  nop
0x18007275a  lea     rcx, [rbp+0A0h+string]; this
0x18007275e  call    ?InternalRelease@StoredObjectId@TokenBroker@Authentication@Security@Internal@Windows@@AEAAXXZ; Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::InternalRelease(void)
0x180072763  nop
0x180072764  xor     edi, edi
0x180072766  jmp     loc_18007287F
0x18007276b  lea     r8, [rbp+0A0h+lpsz]
0x18007276f  lea     rdx, [rbp+0A0h+var_100]
0x180072773  lea     rcx, [rbp+0A0h+var_D8]
0x180072777  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UPerAppAccountData@@@2@UStringComparerW@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UPerAppAccountData@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UPerAppAccountData@@@2@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<PerAppAccountData>,StringComparerW,std::allocator<std::pair<std::wstring const,std::shared_ptr<PerAppAccountData>>>,0>>::find(std::wstring const &)
0x18007277c  mov     rax, [rbp+0A0h+var_100]
0x180072780  cmp     rax, [rbp+0A0h+var_D8]
0x180072784  jz      short loc_1800727B1
0x180072786  mov     rdi, [rax+40h]
0x18007278a  mov     rcx, [rdi+10h]; string
0x18007278e  call    cs:__imp_WindowsIsStringEmpty
0x180072794  test    eax, eax
0x180072796  jnz     short loc_1800727B1
0x180072798  lea     rdx, [rsp+1A0h+newString]; newString
0x18007279d  mov     rcx, [rdi+10h]; string
0x1800727a1  call    cs:__imp_WindowsDuplicateString
0x1800727a7  mov     edi, eax
0x1800727a9  test    eax, eax
0x1800727ab  js      loc_1800728D6
0x1800727b1  mov     rcx, [rsp+1A0h+newString]; string
0x1800727b6  call    cs:__imp_WindowsIsStringEmpty
0x1800727bc  test    eax, eax
0x1800727be  jnz     short loc_1800727F9
0x1800727c0  xor     edx, edx; length
0x1800727c2  mov     rcx, [rsp+1A0h+newString]; string
0x1800727c7  call    cs:__imp_WindowsGetStringRawBuffer
0x1800727cd  mov     rdx, rax; unsigned __int16 *
0x1800727d0  lea     rcx, [rbp+0A0h+string]; this
0x1800727d4  call    ?InitializeFromStringId@StoredObjectId@TokenBroker@Authentication@Security@Internal@Windows@@QEAAJPEBG@Z; Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::InitializeFromStringId(ushort const *)
0x1800727d9  mov     edi, eax
0x1800727db  test    eax, eax
0x1800727dd  js      loc_18007294C
0x1800727e3  mov     rdx, r15; struct Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *
0x1800727e6  lea     rcx, [rbp+0A0h+string]; struct Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *
0x1800727ea  call    ?AreEqual@StoredObjectId@TokenBroker@Authentication@Security@Internal@Windows@@SA_NAEBV123456@0@Z; Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::AreEqual(Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId const &,Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId const &)
0x1800727ef  xor     edi, edi
0x1800727f1  test    al, al
0x1800727f3  jnz     loc_180072928
0x1800727f9  lea     rax, [rsp+1A0h+newString]
0x1800727fe  mov     [rsp+1A0h+var_178], rax; __int64
0x180072803  mov     eax, [rbp+0A0h+var_E0]
0x180072806  mov     [rsp+1A0h+var_180], eax; int
0x18007280a  lea     r9, [rbp+0A0h+var_E8]
0x18007280e  mov     r8, r13; HSTRING
0x180072811  mov     rdx, [rbp+0A0h+var_F0]; string
0x180072815  mov     rcx, r14; HSTRING
0x180072818  call    ?CalculatePairwiseId@@YAJQEAUHSTRING__@@00AEAV?$unique_ptr@PEAXULocalAllocDeleter@TokenBroker@Authentication@Security@Internal@Windows@@@std@@KAEAVString@Internal@Windows@@@Z; CalculatePairwiseId(HSTRING__ * const,HSTRING__ * const,HSTRING__ * const,std::unique_ptr<void *,Windows::Internal::Security::Authentication::TokenBroker::LocalAllocDeleter> &,ulong,Windows::Internal::String &)
0x18007281d  mov     edi, eax
0x18007281f  test    eax, eax
0x180072821  js      loc_1800729CE
0x180072827  xor     edx, edx; length
0x180072829  mov     rcx, [rsp+1A0h+newString]; string
0x18007282e  call    cs:__imp_WindowsGetStringRawBuffer
0x180072834  mov     rdx, rax; unsigned __int16 *
0x180072837  lea     rcx, [rbp+0A0h+string]; this
0x18007283b  call    ?InitializeFromStringId@StoredObjectId@TokenBroker@Authentication@Security@Internal@Windows@@QEAAJPEBG@Z; Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::InitializeFromStringId(ushort const *)
0x180072840  mov     edi, eax
0x180072842  test    eax, eax
0x180072844  js      loc_1800729C4
0x18007284a  mov     rdx, r15; struct Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *
0x18007284d  lea     rcx, [rbp+0A0h+string]; struct Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *
0x180072851  call    ?AreEqual@StoredObjectId@TokenBroker@Authentication@Security@Internal@Windows@@SA_NAEBV123456@0@Z; Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::AreEqual(Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId const &,Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId const &)
0x180072856  xor     edi, edi
0x180072858  test    al, al
0x18007285a  jnz     loc_180072953
0x180072860  lea     rcx, [rbp+0A0h+var_F0]; this
0x180072864  call    ??1AccountSystemOnlyInfo@@QEAA@XZ; AccountSystemOnlyInfo::~AccountSystemOnlyInfo(void)
0x180072869  nop
0x18007286a  lea     rcx, [rsp+1A0h+var_148]; this
0x18007286f  call    ?InternalRelease@StoredObjectId@TokenBroker@Authentication@Security@Internal@Windows@@AEAAXXZ; Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::InternalRelease(void)
0x180072874  nop
0x180072875  lea     rcx, [rbp+0A0h+string]; this
0x180072879  call    ?InternalRelease@StoredObjectId@TokenBroker@Authentication@Security@Internal@Windows@@AEAAXXZ; Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::InternalRelease(void)
0x18007287e  nop
0x18007287f  mov     rcx, [rsp+1A0h+newString]; string
0x180072884  test    rcx, rcx
0x180072887  jz      short loc_18007288F
0x180072889  call    cs:__imp_WindowsDeleteString
0x18007288f  add     rbx, 10h
0x180072893  cmp     rbx, rsi
0x180072896  jnz     loc_180072676
0x18007289c  mov     ebx, 80070002h
0x1800728a1  lea     rcx, [rbp+0A0h+var_120]
0x1800728a5  call    ?_Tidy@?$vector@V?$shared_ptr@VStoredObjectId@TokenBroker@Authentication@Security@Internal@Windows@@@std@@V?$allocator@V?$shared_ptr@VStoredObjectId@TokenBroker@Authentication@Security@Internal@Windows@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId>>::_Tidy(void)
0x1800728aa  nop
0x1800728ab  lea     rcx, [rbp+0A0h+lpsz]
0x1800728af  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800728b4  mov     eax, ebx
0x1800728b6  mov     rcx, [rbp+0A0h+var_48]
0x1800728ba  xor     rcx, rsp; StackCookie
0x1800728bd  call    __security_check_cookie
0x1800728c2  add     rsp, 168h
0x1800728c9  pop     r15
0x1800728cb  pop     r14
0x1800728cd  pop     r13
0x1800728cf  pop     r12
0x1800728d1  pop     rdi
0x1800728d2  pop     rsi
0x1800728d3  pop     rbx
0x1800728d4  pop     rbp
0x1800728d5  retn
0x1800728d6  mov     edx, 3FEh; void *
0x1800728db  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x1800728e2  mov     r9d, edi; char *
0x1800728e5  mov     rcx, [rbp+0A8h]; this
0x1800728ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800728f1  nop
0x1800728f2  lea     rcx, [rbp+0A0h+var_F0]; this
0x1800728f6  call    ??1AccountSystemOnlyInfo@@QEAA@XZ; AccountSystemOnlyInfo::~AccountSystemOnlyInfo(void)
0x1800728fb  nop
0x1800728fc  lea     rcx, [rsp+1A0h+var_148]; this
0x180072901  call    ?InternalRelease@StoredObjectId@TokenBroker@Authentication@Security@Internal@Windows@@AEAAXXZ; Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::InternalRelease(void)
0x180072906  nop
0x180072907  lea     rcx, [rbp+0A0h+string]; this
0x18007290b  call    ?InternalRelease@StoredObjectId@TokenBroker@Authentication@Security@Internal@Windows@@AEAAXXZ; Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::InternalRelease(void)
0x180072910  nop
0x180072911  mov     rcx, [rsp+1A0h+newString]; string
0x180072916  test    rcx, rcx
0x180072919  jz      short loc_180072921
0x18007291b  call    cs:__imp_WindowsDeleteString
0x180072921  mov     ebx, edi
0x180072923  jmp     loc_1800728A1
0x180072928  xor     edx, edx; length
0x18007292a  mov     rcx, [rbp+0A0h+var_F0]; string
0x18007292e  call    cs:__imp_WindowsGetStringRawBuffer
0x180072934  mov     rdx, rax; unsigned __int16 *
0x180072937  mov     rcx, r12; this
0x18007293a  call    ?InitializeFromStringId@StoredObjectId@TokenBroker@Authentication@Security@Internal@Windows@@QEAAJPEBG@Z; Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::InitializeFromStringId(ushort const *)
0x18007293f  mov     ebx, eax
0x180072941  test    eax, eax
0x180072943  jns     short loc_1800728F2
0x180072945  mov     edx, 40Ch
0x18007294a  jmp     short loc_180072975
0x18007294c  mov     edx, 406h
0x180072951  jmp     short loc_1800728DB
0x180072953  xor     edx, edx; length
0x180072955  mov     rcx, [rbp+0A0h+var_F0]; string
0x180072959  call    cs:__imp_WindowsGetStringRawBuffer
0x18007295f  mov     rdx, rax; unsigned __int16 *
0x180072962  mov     rcx, r12; this
  ... truncated ...
```
