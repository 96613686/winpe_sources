# GetPairwiseIdFromRealId(Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId &,Windows::Internal::String &,HSTRING__ * const,HSTRING__ * const)

- ea: `0x1800722ac`
- end: `0x1800724c5`
- name: `?GetPairwiseIdFromRealId@@YAJAEAVStoredObjectId@TokenBroker@Authentication@Security@Internal@Windows@@AEAVString@56@QEAUHSTRING__@@2@Z`
- size: `537`
- prototype: `int(struct Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *, struct Windows::Internal::String *, HSTRING, HSTRING)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18002a790`

## callees

- `0x18000730c`
- `0x180009e40`
- `0x18000bd40`
- `0x18002d940`
- `0x180035880`
- `0x1800426b0`
- `0x180051dd0`
- `0x180051f48`
- `0x180071b10`
- `0x1800722ac`
- `0x180072cd0`
- `0x18008e690`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180072402`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180072402`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800722ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800722ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007231c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180072394`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800722ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800722ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007231c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180072394`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072430`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007243b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072469`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072430`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007243b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072469`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800723ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800723ef`
- `api-ms-win-core-string-l2-1-0!CharLowerW` at `0x1800723b5`
- `api-ms-win-core-string-l2-1-0!CharLowerW` at `0x1800723b5`

## string_xrefs

- `0x180072379`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x180072415`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetPairwiseIdFromRealId(
        struct Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *a1,
        HSTRING *a2,
        HSTRING a3,
        HSTRING a4)
{
  const unsigned __int16 *v8; // r15
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  int v12; // eax
  unsigned int v13; // ebx
  PCWSTR StringRawBuffer; // rax
  WCHAR *v15; // rcx
  __int64 v16; // rbx
  HRESULT v17; // eax
  int v19; // [rsp+20h] [rbp-E0h]
  HSTRING newString; // [rsp+40h] [rbp-C0h] BYREF
  int v21[2]; // [rsp+48h] [rbp-B8h] BYREF
  PCWSTR v22[2]; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING v23; // [rsp+60h] [rbp-A0h] BYREF
  PUCHAR v24; // [rsp+68h] [rbp-98h] BYREF
  ULONG v25; // [rsp+70h] [rbp-90h]
  _QWORD v26[9]; // [rsp+78h] [rbp-88h] BYREF
  LPWSTR lpsz[4]; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING string[4]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v8 = (const unsigned __int16 *)*((_QWORD *)a1 + 2);
  if ( (unsigned int)dword_180175000 > 5 )
  {
    newString = (HSTRING)WindowsGetStringRawBuffer(a4, 0);
    v22[0] = WindowsGetStringRawBuffer(a3, 0);
    Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)string, v8);
    *(_QWORD *)v21 = WindowsGetStringRawBuffer(string[0], 0);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      v9,
      (unsigned int)byte_180158B13,
      v10,
      v11,
      (__int64)v21,
      (__int64)v22,
      (__int64)&newString);
  }
  AccountSystemOnlyInfo::AccountSystemOnlyInfo((AccountSystemOnlyInfo *)&v23);
  v12 = AccountSystemOnlyInfo::InitializeFromAccountId((AccountSystemOnlyInfo *)&v23, a1, a3);
  v13 = v12;
  if ( v12 >= 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(a4, 0);
    std::wstring::wstring(lpsz, StringRawBuffer);
    v15 = (WCHAR *)lpsz;
    if ( lpsz[3] > (LPWSTR)7 )
      v15 = lpsz[0];
    CharLowerW(v15);
    std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<PerAppAccountData>,StringComparerW,std::allocator<std::pair<std::wstring const,std::shared_ptr<PerAppAccountData>>>,0>>::find(
      v26,
      v21,
      lpsz);
    if ( *(_QWORD *)v21 != v26[0] )
    {
      v16 = *(_QWORD *)(*(_QWORD *)v21 + 64LL);
      newString = 0;
      if ( !WindowsIsStringEmpty(*(HSTRING *)(v16 + 16)) )
      {
        v17 = WindowsDuplicateString(*(HSTRING *)(v16 + 16), &newString);
        v13 = v17;
        if ( v17 >= 0 )
        {
          WindowsDeleteString(*a2);
          *a2 = newString;
          newString = 0;
          std::wstring::_Tidy_deallocate(lpsz);
          v13 = 0;
          goto LABEL_17;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x464,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
          (const char *)(unsigned int)v17,
          v19);
        if ( newString )
          WindowsDeleteString(newString);
LABEL_16:
        std::wstring::_Tidy_deallocate(lpsz);
        goto LABEL_17;
      }
      if ( newString )
        WindowsDeleteString(newString);
    }
    v13 = CalculatePairwiseId(a3, v23, a4, &v24, v25, (__int64)a2);
    goto LABEL_16;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x452,
    (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
    (const char *)(unsigned int)v12,
    v19);
LABEL_17:
  AccountSystemOnlyInfo::~AccountSystemOnlyInfo((AccountSystemOnlyInfo *)&v23);
  return v13;
}

```

## disassembly

```asm
0x1800722ac  push    rbp
0x1800722ae  push    rbx
0x1800722af  push    rsi
0x1800722b0  push    rdi
0x1800722b1  push    r14
0x1800722b3  push    r15
0x1800722b5  lea     rbp, [rsp-18h]
0x1800722ba  sub     rsp, 118h
0x1800722c1  mov     rax, cs:__security_cookie
0x1800722c8  xor     rax, rsp
0x1800722cb  mov     [rbp+40h+var_40], rax
0x1800722cf  mov     r14, r9
0x1800722d2  mov     rsi, r8
0x1800722d5  mov     rdi, rdx
0x1800722d8  mov     rbx, rcx
0x1800722db  mov     r15, [rcx+10h]
0x1800722df  mov     eax, cs:dword_180175000
0x1800722e5  cmp     eax, 5
0x1800722e8  jbe     short loc_180072351
0x1800722ea  xor     edx, edx; length
0x1800722ec  mov     rcx, r9; string
0x1800722ef  call    cs:__imp_WindowsGetStringRawBuffer
0x1800722f5  mov     [rsp+140h+newString], rax
0x1800722fa  xor     edx, edx; length
0x1800722fc  mov     rcx, rsi; string
0x1800722ff  call    cs:__imp_WindowsGetStringRawBuffer
0x180072305  mov     [rsp+140h+var_F0], rax
0x18007230a  mov     rdx, r15; unsigned __int16 *
0x18007230d  lea     rcx, [rbp+40h+string]; this
0x180072311  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x180072316  xor     edx, edx; length
0x180072318  mov     rcx, [rbp+40h+string]; string
0x18007231c  call    cs:__imp_WindowsGetStringRawBuffer
0x180072322  mov     qword ptr [rsp+140h+var_F8], rax
0x180072327  lea     rax, [rsp+140h+newString]
0x18007232c  mov     [rsp+140h+var_110], rax
0x180072331  lea     rax, [rsp+140h+var_F0]
0x180072336  mov     [rsp+140h+var_118], rax
0x18007233b  lea     rax, [rsp+140h+var_F8]
0x180072340  mov     qword ptr [rsp+140h+var_120], rax; int
0x180072345  lea     rdx, byte_180158B13
0x18007234c  call    ??$Write@U?$_tlgWrapSz@G@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180072351  lea     rcx, [rsp+140h+var_E0]; this
0x180072356  call    ??0AccountSystemOnlyInfo@@QEAA@XZ; AccountSystemOnlyInfo::AccountSystemOnlyInfo(void)
0x18007235b  nop
0x18007235c  mov     r8, rsi; HSTRING
0x18007235f  mov     rdx, rbx; struct Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *
0x180072362  lea     rcx, [rsp+140h+var_E0]; this
0x180072367  call    ?InitializeFromAccountId@AccountSystemOnlyInfo@@QEAAJAEAVStoredObjectId@TokenBroker@Authentication@Security@Internal@Windows@@PEAUHSTRING__@@@Z; AccountSystemOnlyInfo::InitializeFromAccountId(Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId &,HSTRING__ *)
0x18007236c  mov     ebx, eax
0x18007236e  test    eax, eax
0x180072370  jns     short loc_18007238F
0x180072372  mov     rcx, [rbp+48h]; this
0x180072376  mov     r9d, eax; char *
0x180072379  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180072380  mov     edx, 452h; void *
0x180072385  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007238a  jmp     loc_18007249D
0x18007238f  xor     edx, edx; length
0x180072391  mov     rcx, r14; string
0x180072394  call    cs:__imp_WindowsGetStringRawBuffer
0x18007239a  mov     rdx, rax
0x18007239d  lea     rcx, [rbp+40h+lpsz]
0x1800723a1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800723a6  nop
0x1800723a7  lea     rcx, [rbp+40h+lpsz]
0x1800723ab  cmp     [rbp+40h+var_68], 7
0x1800723b0  cmova   rcx, [rbp+40h+lpsz]; lpsz
0x1800723b5  call    cs:__imp_CharLowerW
0x1800723bb  lea     r8, [rbp+40h+lpsz]
0x1800723bf  lea     rdx, [rsp+140h+var_F8]
0x1800723c4  lea     rcx, [rsp+140h+var_C8]
0x1800723c9  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UPerAppAccountData@@@2@UStringComparerW@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UPerAppAccountData@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UPerAppAccountData@@@2@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<PerAppAccountData>,StringComparerW,std::allocator<std::pair<std::wstring const,std::shared_ptr<PerAppAccountData>>>,0>>::find(std::wstring const &)
0x1800723ce  mov     rax, qword ptr [rsp+140h+var_F8]
0x1800723d3  cmp     rax, [rsp+140h+var_C8]
0x1800723d8  jz      loc_18007246F
0x1800723de  mov     rbx, [rax+40h]
0x1800723e2  mov     [rsp+140h+newString], 0
0x1800723eb  mov     rcx, [rbx+10h]; string
0x1800723ef  call    cs:__imp_WindowsIsStringEmpty
0x1800723f5  test    eax, eax
0x1800723f7  jnz     short loc_18007245F
0x1800723f9  lea     rdx, [rsp+140h+newString]; newString
0x1800723fe  mov     rcx, [rbx+10h]; string
0x180072402  call    cs:__imp_WindowsDuplicateString
0x180072408  mov     ebx, eax
0x18007240a  test    eax, eax
0x18007240c  jns     short loc_180072438
0x18007240e  mov     rcx, [rbp+48h]; this
0x180072412  mov     r9d, eax; char *
0x180072415  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x18007241c  mov     edx, 464h; void *
0x180072421  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180072426  mov     rcx, [rsp+140h+newString]; string
0x18007242b  test    rcx, rcx
0x18007242e  jz      short loc_180072493
0x180072430  call    cs:__imp_WindowsDeleteString
0x180072436  jmp     short loc_180072493
0x180072438  mov     rcx, [rdi]; string
0x18007243b  call    cs:__imp_WindowsDeleteString
0x180072441  mov     rax, [rsp+140h+newString]
0x180072446  mov     [rdi], rax
0x180072449  mov     [rsp+140h+newString], 0
0x180072452  lea     rcx, [rbp+40h+lpsz]
0x180072456  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007245b  xor     ebx, ebx
0x18007245d  jmp     short loc_18007249D
0x18007245f  mov     rcx, [rsp+140h+newString]; string
0x180072464  test    rcx, rcx
0x180072467  jz      short loc_18007246F
0x180072469  call    cs:__imp_WindowsDeleteString
0x18007246f  mov     [rsp+140h+var_118], rdi; __int64
0x180072474  mov     eax, [rsp+140h+var_D0]
0x180072478  mov     [rsp+140h+var_120], eax; ULONG
0x18007247c  lea     r9, [rsp+140h+var_D8]
0x180072481  mov     r8, r14; HSTRING
0x180072484  mov     rdx, [rsp+140h+var_E0]; string
0x180072489  mov     rcx, rsi; HSTRING
0x18007248c  call    ?CalculatePairwiseId@@YAJQEAUHSTRING__@@00AEAV?$unique_ptr@PEAXULocalAllocDeleter@TokenBroker@Authentication@Security@Internal@Windows@@@std@@KAEAVString@Internal@Windows@@@Z; CalculatePairwiseId(HSTRING__ * const,HSTRING__ * const,HSTRING__ * const,std::unique_ptr<void *,Windows::Internal::Security::Authentication::TokenBroker::LocalAllocDeleter> &,ulong,Windows::Internal::String &)
0x180072491  mov     ebx, eax
0x180072493  lea     rcx, [rbp+40h+lpsz]
0x180072497  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007249c  nop
0x18007249d  lea     rcx, [rsp+140h+var_E0]; this
0x1800724a2  call    ??1AccountSystemOnlyInfo@@QEAA@XZ; AccountSystemOnlyInfo::~AccountSystemOnlyInfo(void)
0x1800724a7  mov     eax, ebx
0x1800724a9  mov     rcx, [rbp+40h+var_40]
0x1800724ad  xor     rcx, rsp; StackCookie
0x1800724b0  call    __security_check_cookie
0x1800724b5  add     rsp, 118h
0x1800724bc  pop     r15
0x1800724be  pop     r14
0x1800724c0  pop     rdi
0x1800724c1  pop     rsi
0x1800724c2  pop     rbx
0x1800724c3  pop     rbp
0x1800724c4  retn
```
