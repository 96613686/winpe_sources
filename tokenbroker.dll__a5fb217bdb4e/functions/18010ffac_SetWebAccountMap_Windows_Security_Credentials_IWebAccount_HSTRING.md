# SetWebAccountMap(Windows::Security::Credentials::IWebAccount *,HSTRING__ *)

- ea: `0x18010ffac`
- end: `0x180110261`
- name: `?SetWebAccountMap@@YAJPEAUIWebAccount@Credentials@Security@Windows@@PEAUHSTRING__@@@Z`
- size: `693`
- prototype: `__int64 __fastcall(struct Windows::Security::Credentials::IWebAccount *, HSTRING string)`
- caller_count: `2`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800e34c0`
- `0x1800e3540`

## callees

- `0x180007350`
- `0x18000bd40`
- `0x180035880`
- `0x180040980`
- `0x180040cc0`
- `0x1800426b0`
- `0x18004fdbc`
- `0x180051dd0`
- `0x1800729e0`
- `0x180074e0c`
- `0x18010ffac`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1801100ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1801100ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180110113`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180110123`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180110132`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180110204`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180110113`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180110123`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180110132`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180110204`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180110059`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801101df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180110237`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180110059`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801101df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180110237`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1801100cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1801100cb`

## string_xrefs

- `0x18011002e`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x180110081`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x1801101bb`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SetWebAccountMap(
        __int64 (__fastcall ***a1)(struct Windows::Security::Credentials::IWebAccount *, GUID *, __int64 *),
        HSTRING string)
{
  __int64 (__fastcall *v4)(struct Windows::Security::Credentials::IWebAccount *, GUID *, __int64 *); // rbx
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, HSTRING *); // rbx
  HRESULT v9; // eax
  __int64 v10; // rdx
  HSTRING v11; // r8
  int v12; // eax
  unsigned __int64 v13; // r9
  __int64 v14; // rdx
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  int v18; // eax
  int updated; // eax
  int v20; // eax
  int v22; // r9d
  int v23; // [rsp+20h] [rbp-79h]
  HSTRING string1; // [rsp+40h] [rbp-59h] BYREF
  __int64 v25; // [rsp+48h] [rbp-51h] BYREF
  INT32 result; // [rsp+50h] [rbp-49h] BYREF
  HSTRING v27; // [rsp+58h] [rbp-41h] BYREF
  PCWSTR StringRawBuffer; // [rsp+60h] [rbp-39h] BYREF
  PCWSTR v29; // [rsp+68h] [rbp-31h] BYREF
  int v30[2]; // [rsp+70h] [rbp-29h] BYREF
  HSTRING stringa[9]; // [rsp+80h] [rbp-19h] BYREF
  _QWORD v32[3]; // [rsp+C8h] [rbp+2Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v27 = string;
  if ( (unsigned int)dword_180175000 > 4 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180175000,
      byte_180157EF5,
      0,
      0);
  v25 = 0;
  v4 = **a1;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
  v5 = v4((struct Windows::Security::Credentials::IWebAccount *)a1, &GUID_40285a2b_65d5_41f5_b904_76c860d86e26, &v25);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDCA,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
      (const char *)(unsigned int)v5,
      v23);
LABEL_26:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
    return v6;
  }
  string1 = 0;
  v7 = v25;
  v8 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v25 + 64LL);
  WindowsDeleteString(0);
  string1 = 0;
  v9 = v8(v7, &string1);
  v6 = v9;
  if ( v9 < 0 )
  {
    v10 = 3532;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
      (const char *)(unsigned int)v9,
      v23);
    goto LABEL_24;
  }
  result = 0;
  v9 = WindowsCompareStringOrdinal(string1, string, &result);
  v6 = v9;
  if ( v9 < 0 )
  {
    v10 = 3535;
    goto LABEL_7;
  }
  if ( result && !WindowsIsStringEmpty(string) )
  {
    AccountSystemOnlyInfo::AccountSystemOnlyInfo((AccountSystemOnlyInfo *)stringa);
    v12 = AccountSystemOnlyInfo::InitializeFromAccount(
            (AccountSystemOnlyInfo *)stringa,
            (struct Windows::Security::Credentials::IWebAccount *)a1,
            v11);
    v6 = v12;
    if ( v12 >= 0 )
    {
      if ( (unsigned int)dword_180175000 > 5 )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(stringa[0], 0);
        v29 = WindowsGetStringRawBuffer(stringa[5], 0);
        *(_QWORD *)v30 = WindowsGetStringRawBuffer(string, 0);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v15,
          (unsigned int)&word_180157E66,
          v16,
          v17,
          (__int64)v30,
          (__int64)&v29,
          (__int64)&StringRawBuffer);
      }
      v18 = Windows::Internal::String::Initialize((Windows::Internal::String *)v32, &v27);
      v6 = v18;
      if ( v18 >= 0 )
      {
        updated = UpdateAccountSystemOnlyData((struct AccountSystemOnlyInfo *)stringa);
        v6 = updated;
        if ( updated >= 0 )
        {
          v20 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v25 + 72LL))(v25, v32[0]);
          v6 = v20;
          if ( v20 >= 0 )
          {
LABEL_23:
            AccountSystemOnlyInfo::~AccountSystemOnlyInfo((AccountSystemOnlyInfo *)stringa);
LABEL_24:
            if ( string1 )
              WindowsDeleteString(string1);
            goto LABEL_26;
          }
          v13 = (unsigned int)v20;
          v14 = 3567;
        }
        else
        {
          v13 = (unsigned int)updated;
          v14 = 3564;
        }
      }
      else
      {
        v13 = (unsigned int)v18;
        v14 = 3562;
      }
    }
    else
    {
      v13 = (unsigned int)v12;
      v14 = 3552;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
      (const char *)v13,
      v23);
    goto LABEL_23;
  }
  if ( (unsigned int)dword_180175000 > 5 )
  {
    v27 = (HSTRING)WindowsGetStringRawBuffer(string1, 0);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (unsigned int)&dword_180175000,
      (unsigned int)byte_180157EBB,
      0,
      v22,
      (__int64)&v27);
  }
  if ( string1 )
    WindowsDeleteString(string1);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
  return 0;
}

```

## disassembly

```asm
0x18010ffac  mov     [rsp-8+arg_10], rbx
0x18010ffb1  mov     [rsp-8+arg_18], rsi
0x18010ffb6  push    rbp
0x18010ffb7  push    rdi
0x18010ffb8  push    r14
0x18010ffba  lea     rbp, [rsp-47h]
0x18010ffbf  sub     rsp, 0E0h
0x18010ffc6  mov     rsi, rdx
0x18010ffc9  mov     r14, rcx
0x18010ffcc  mov     [rbp+57h+var_98], rdx
0x18010ffd0  mov     eax, cs:dword_180175000
0x18010ffd6  cmp     eax, 4
0x18010ffd9  jbe     short loc_18010FFF4
0x18010ffdb  xor     r9d, r9d
0x18010ffde  xor     r8d, r8d
0x18010ffe1  lea     rdx, byte_180157EF5
0x18010ffe8  lea     rcx, dword_180175000
0x18010ffef  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18010fff4  mov     [rbp+57h+var_A8], 0
0x18010fffc  mov     rax, [r14]
0x18010ffff  mov     rbx, [rax]
0x180110002  lea     rcx, [rbp+57h+var_A8]
0x180110006  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18011000b  lea     r8, [rbp+57h+var_A8]
0x18011000f  lea     rdx, _GUID_40285a2b_65d5_41f5_b904_76c860d86e26
0x180110016  mov     rcx, r14
0x180110019  mov     rax, rbx
0x18011001c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180110021  mov     ebx, eax
0x180110023  test    eax, eax
0x180110025  jns     short loc_180110044
0x180110027  mov     rcx, [rbp+5Fh]; this
0x18011002b  mov     r9d, eax; char *
0x18011002e  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180110035  mov     edx, 0DCAh; void *
0x18011003a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011003f  jmp     loc_1801101E6
0x180110044  mov     [rbp+57h+string1], 0
0x18011004c  mov     rdi, [rbp+57h+var_A8]
0x180110050  mov     rax, [rdi]
0x180110053  mov     rbx, [rax+40h]
0x180110057  xor     ecx, ecx; string
0x180110059  call    cs:__imp_WindowsDeleteString
0x18011005f  mov     [rbp+57h+string1], 0
0x180110067  lea     rdx, [rbp+57h+string1]
0x18011006b  mov     rcx, rdi
0x18011006e  mov     rax, rbx
0x180110071  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180110076  mov     ebx, eax
0x180110078  test    eax, eax
0x18011007a  jns     short loc_180110099
0x18011007c  mov     edx, 0DCCh; void *
0x180110081  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180110088  mov     r9d, eax; char *
0x18011008b  mov     rcx, [rbp+5Fh]; this
0x18011008f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180110094  jmp     loc_1801101D6
0x180110099  mov     [rbp+57h+result], 0
0x1801100a0  lea     r8, [rbp+57h+result]; result
0x1801100a4  mov     rdx, rsi; string2
0x1801100a7  mov     rcx, [rbp+57h+string1]; string1
0x1801100ab  call    cs:__imp_WindowsCompareStringOrdinal
0x1801100b1  mov     ebx, eax
0x1801100b3  test    eax, eax
0x1801100b5  jns     short loc_1801100BE
0x1801100b7  mov     edx, 0DCFh
0x1801100bc  jmp     short loc_180110081
0x1801100be  cmp     [rbp+57h+result], 0
0x1801100c2  jz      loc_1801101F3
0x1801100c8  mov     rcx, rsi; string
0x1801100cb  call    cs:__imp_WindowsIsStringEmpty
0x1801100d1  test    eax, eax
0x1801100d3  jnz     loc_1801101F3
0x1801100d9  lea     rcx, [rbp+57h+string]; this
0x1801100dd  call    ??0AccountSystemOnlyInfo@@QEAA@XZ; AccountSystemOnlyInfo::AccountSystemOnlyInfo(void)
0x1801100e2  nop
0x1801100e3  mov     rdx, r14; struct Windows::Security::Credentials::IWebAccount *
0x1801100e6  lea     rcx, [rbp+57h+string]; this
0x1801100ea  call    ?InitializeFromAccount@AccountSystemOnlyInfo@@QEAAJPEAUIWebAccount@Credentials@Security@Windows@@PEAUHSTRING__@@@Z; AccountSystemOnlyInfo::InitializeFromAccount(Windows::Security::Credentials::IWebAccount *,HSTRING__ *)
0x1801100ef  mov     ebx, eax
0x1801100f1  test    eax, eax
0x1801100f3  jns     short loc_180110102
0x1801100f5  mov     r9d, eax
0x1801100f8  mov     edx, 0DE0h
0x1801100fd  jmp     loc_1801101BB
0x180110102  mov     eax, cs:dword_180175000
0x180110108  cmp     eax, 5
0x18011010b  jbe     short loc_180110163
0x18011010d  xor     edx, edx; length
0x18011010f  mov     rcx, [rbp+57h+string]; string
0x180110113  call    cs:__imp_WindowsGetStringRawBuffer
0x180110119  mov     [rbp+57h+var_90], rax
0x18011011d  xor     edx, edx; length
0x18011011f  mov     rcx, [rbp+57h+var_48]; string
0x180110123  call    cs:__imp_WindowsGetStringRawBuffer
0x180110129  mov     [rbp+57h+var_88], rax
0x18011012d  xor     edx, edx; length
0x18011012f  mov     rcx, rsi; string
0x180110132  call    cs:__imp_WindowsGetStringRawBuffer
0x180110138  mov     qword ptr [rbp+57h+var_80], rax
0x18011013c  lea     rax, [rbp+57h+var_90]
0x180110140  mov     [rsp+0F0h+var_C0], rax
0x180110145  lea     rax, [rbp+57h+var_88]
0x180110149  mov     [rsp+0F0h+var_C8], rax
0x18011014e  lea     rax, [rbp+57h+var_80]
0x180110152  mov     qword ptr [rsp+0F0h+var_D0], rax; int
0x180110157  lea     rdx, word_180157E66
0x18011015e  call    ??$Write@U?$_tlgWrapSz@G@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180110163  lea     rdx, [rbp+57h+var_98]; HSTRING *
0x180110167  lea     rcx, [rbp+57h+var_28]; this
0x18011016b  call    ?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z; Windows::Internal::String::Initialize(HSTRING__ * const &)
0x180110170  mov     ebx, eax
0x180110172  test    eax, eax
0x180110174  jns     short loc_180110180
0x180110176  mov     r9d, eax
0x180110179  mov     edx, 0DEAh
0x18011017e  jmp     short loc_1801101BB
0x180110180  lea     rcx, [rbp+57h+string]; struct AccountSystemOnlyInfo *
0x180110184  call    ?UpdateAccountSystemOnlyData@@YAJAEAUAccountSystemOnlyInfo@@@Z; UpdateAccountSystemOnlyData(AccountSystemOnlyInfo &)
0x180110189  mov     ebx, eax
0x18011018b  test    eax, eax
0x18011018d  jns     short loc_180110199
0x18011018f  mov     r9d, eax
0x180110192  mov     edx, 0DECh
0x180110197  jmp     short loc_1801101BB
0x180110199  mov     rcx, [rbp+57h+var_A8]
0x18011019d  mov     rax, [rcx]
0x1801101a0  mov     rdx, [rbp+57h+var_28]
0x1801101a4  mov     rax, [rax+48h]
0x1801101a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801101ad  mov     ebx, eax
0x1801101af  test    eax, eax
0x1801101b1  jns     short loc_1801101CC
0x1801101b3  mov     r9d, eax; char *
0x1801101b6  mov     edx, 0DEFh; void *
0x1801101bb  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x1801101c2  mov     rcx, [rbp+5Fh]; this
0x1801101c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801101cb  nop
0x1801101cc  lea     rcx, [rbp+57h+string]; this
0x1801101d0  call    ??1AccountSystemOnlyInfo@@QEAA@XZ; AccountSystemOnlyInfo::~AccountSystemOnlyInfo(void)
0x1801101d5  nop
0x1801101d6  mov     rcx, [rbp+57h+string1]; string
0x1801101da  test    rcx, rcx
0x1801101dd  jz      short loc_1801101E6
0x1801101df  call    cs:__imp_WindowsDeleteString
0x1801101e5  nop
0x1801101e6  lea     rcx, [rbp+57h+var_A8]
0x1801101ea  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801101ef  mov     eax, ebx
0x1801101f1  jmp     short loc_180110249
0x1801101f3  mov     eax, cs:dword_180175000
0x1801101f9  cmp     eax, 5
0x1801101fc  jbe     short loc_18011022E
0x1801101fe  xor     edx, edx; length
0x180110200  mov     rcx, [rbp+57h+string1]; string
0x180110204  call    cs:__imp_WindowsGetStringRawBuffer
0x18011020a  mov     [rbp+57h+var_98], rax
0x18011020e  lea     rax, [rbp+57h+var_98]
0x180110212  mov     qword ptr [rsp+0F0h+var_D0], rax
0x180110217  xor     r8d, r8d
0x18011021a  lea     rdx, byte_180157EBB
0x180110221  lea     rcx, dword_180175000
0x180110228  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18011022d  nop
0x18011022e  mov     rcx, [rbp+57h+string1]; string
0x180110232  test    rcx, rcx
0x180110235  jz      short loc_18011023E
0x180110237  call    cs:__imp_WindowsDeleteString
0x18011023d  nop
0x18011023e  lea     rcx, [rbp+57h+var_A8]
0x180110242  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180110247  xor     eax, eax
0x180110249  lea     r11, [rsp+0F0h+var_10]
0x180110251  mov     rbx, [r11+30h]
0x180110255  mov     rsi, [r11+38h]
0x180110259  mov     rsp, r11
0x18011025c  pop     r14
0x18011025e  pop     rdi
0x18011025f  pop     rbp
0x180110260  retn
```
