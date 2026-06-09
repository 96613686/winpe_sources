# Windows::Internal::Security::Authentication::TokenBroker::PluginRegistrationInternal::GetPluginPFN(Windows::Internal::Security::Authentication::Web::CallerContext *,Windows::Security::Credentials::IWebAccountProvider *,HSTRING__ * *)

- ea: `0x1800262f0`
- end: `0x1800266a8`
- name: `?GetPluginPFN@PluginRegistrationInternal@TokenBroker@Authentication@Security@Internal@Windows@@SAJPEAVCallerContext@Web@3456@PEAUIWebAccountProvider@Credentials@46@PEAPEAUHSTRING__@@@Z`
- size: `952`
- prototype: `__int64 __fastcall(struct Windows::Internal::Security::Authentication::Web::CallerContext *this, struct Windows::Security::Credentials::IWebAccountProvider *, HSTRING *)`
- caller_count: `16`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001ef40`
- `0x180024c88`
- `0x18002eb80`
- `0x1800586a8`
- `0x18005a41c`
- `0x18005aa84`
- `0x18005fdcc`
- `0x180069a40`
- `0x18006b0c0`
- `0x18006e74c`
- `0x180086a40`
- `0x1800c2180`
- `0x1800d1cc0`
- `0x1800d4e70`
- `0x1800e2094`
- `0x1800e2918`

## callees

- `0x18000bd40`
- `0x1800228e0`
- `0x1800262f0`
- `0x180031cf8`
- `0x180040980`
- `0x18008e690`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800263bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800263df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800263ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800265ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800263bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800263df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800263ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800265ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002636e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002637e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002638e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002664b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002665a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026669`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026678`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002636e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002637e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002638e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002664b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002665a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026669`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026678`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800263c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800263c7`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180026529`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180026529`

## string_xrefs

- `0x180026353`: `onecore\ds\security\tokenbroker\broker\lib\pluginreginternal.cpp`
- `0x180026554`: `onecore\ds\security\tokenbroker\broker\lib\pluginreginternal.cpp`
- `0x1800265ab`: `onecore\ds\security\tokenbroker\broker\lib\pluginreginternal.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Windows::Internal::Security::Authentication::TokenBroker::PluginRegistrationInternal::GetPluginPFN(
        struct Windows::Internal::Security::Authentication::Web::CallerContext *this,
        __int64 (__fastcall ***a2)(struct Windows::Security::Credentials::IWebAccountProvider *, GUID *, __int64 *),
        HSTRING *a3)
{
  int v5; // eax
  unsigned int v6; // ebx
  HSTRING v8; // rsi
  HSTRING v9; // rbx
  HSTRING v10; // rdi
  PCWSTR StringRawBuffer; // r15
  PCWSTR v12; // r14
  PCWSTR v13; // r8
  __int64 v14; // rcx
  __int64 v15; // rdx
  int v16; // edx
  __int64 v17; // rax
  int v18; // eax
  int v19; // ecx
  int v20; // eax
  unsigned int v21; // r14d
  struct Windows::Internal::Security::Authentication::Web::IWamProviderRegistrationInformation *v22; // rcx
  HSTRING v23; // rcx
  int v24; // eax
  struct Windows::Internal::Security::Authentication::Web::IWamProviderRegistrationInformation *v25; // rcx
  int v26; // r9d
  struct Windows::Internal::Security::Authentication::Web::IWamProviderRegistrationInformation *v27; // rdx
  int UserDataCount; // [rsp+20h] [rbp-89h]
  struct Windows::Internal::Security::Authentication::Web::IWamProviderRegistrationInformation *v29; // [rsp+30h] [rbp-79h] BYREF
  HSTRING v30; // [rsp+38h] [rbp-71h] BYREF
  PCWSTR v31; // [rsp+40h] [rbp-69h] BYREF
  HSTRING v32; // [rsp+48h] [rbp-61h] BYREF
  HSTRING v33; // [rsp+50h] [rbp-59h] BYREF
  HSTRING string; // [rsp+58h] [rbp-51h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+60h] [rbp-49h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+70h] [rbp-39h] BYREF
  char *v37; // [rsp+80h] [rbp-29h]
  int v38; // [rsp+88h] [rbp-21h]
  int v39; // [rsp+8Ch] [rbp-1Dh]
  PCWSTR v40; // [rsp+90h] [rbp-19h]
  int v41; // [rsp+98h] [rbp-11h]
  int v42; // [rsp+9Ch] [rbp-Dh]
  PCWSTR v43; // [rsp+A0h] [rbp-9h]
  int v44; // [rsp+A8h] [rbp-1h]
  int v45; // [rsp+ACh] [rbp+3h]
  PCWSTR v46; // [rsp+B0h] [rbp+7h]
  int v47; // [rsp+B8h] [rbp+Fh]
  int v48; // [rsp+BCh] [rbp+13h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v32 = 0;
  v33 = 0;
  string = 0;
  v5 = Windows::Internal::Security::Authentication::TokenBroker::PluginManager::MapAliasesToPluginId(
         a2,
         &v32,
         &v33,
         &string);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v8 = v32;
    v9 = v33;
    v10 = string;
    if ( (unsigned int)dword_180175000 > 4 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      if ( WindowsIsStringEmpty(v9) )
        v12 = L"NULL";
      else
        v12 = WindowsGetStringRawBuffer(v9, 0);
      v13 = WindowsGetStringRawBuffer(v8, 0);
      v14 = -1;
      if ( StringRawBuffer )
      {
        v15 = -1;
        do
          ++v15;
        while ( StringRawBuffer[v15] );
        v16 = 2 * v15 + 2;
      }
      else
      {
        StringRawBuffer = &word_1801330B0;
        v16 = 2;
      }
      v46 = StringRawBuffer;
      v47 = v16;
      v48 = 0;
      if ( v12 )
      {
        v17 = -1;
        do
          ++v17;
        while ( v12[v17] );
        v18 = 2 * v17 + 2;
      }
      else
      {
        v12 = &word_1801330B0;
        v18 = 2;
      }
      v43 = v12;
      v44 = v18;
      v45 = 0;
      if ( v13 )
      {
        do
          ++v14;
        while ( v13[v14] );
        v19 = 2 * v14 + 2;
      }
      else
      {
        v13 = &word_1801330B0;
        v19 = 2;
      }
      v40 = v13;
      v41 = v19;
      v42 = 0;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 4;
      EventDescriptor.Keyword = 0;
      UserData.Ptr = (ULONGLONG)off_180175008;
      UserData.Size = *(unsigned __int16 *)off_180175008;
      UserData.Reserved = 2;
      v37 = byte_180151355;
      v38 = 64;
      v39 = 1;
      LODWORD(v31) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 5u, &UserData);
    }
    v30 = 0;
    v29 = 0;
    v20 = Windows::Internal::Security::Authentication::Web::CWamProviderRegistrationInternal::GetFromId(v10, this, &v29);
    v21 = v20;
    if ( v20 >= 0 )
    {
      v24 = (*(__int64 (__fastcall **)(struct Windows::Internal::Security::Authentication::Web::IWamProviderRegistrationInformation *, HSTRING *))(*(_QWORD *)v29 + 88LL))(
              v29,
              &v30);
      v21 = v24;
      if ( v24 >= 0 )
      {
        if ( (unsigned int)dword_180175000 > 5 )
        {
          v31 = WindowsGetStringRawBuffer(v30, 0);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            (unsigned int)&dword_180175000,
            (unsigned int)word_180151312,
            0,
            v26,
            (__int64)&v31);
        }
        *a3 = v30;
        v23 = 0;
        v30 = 0;
        v27 = v29;
        if ( v29 )
        {
          v29 = 0;
          (*(void (__fastcall **)(struct Windows::Internal::Security::Authentication::Web::IWamProviderRegistrationInformation *))(*(_QWORD *)v27 + 16LL))(v27);
          v23 = v30;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x85,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\pluginreginternal.cpp",
          (const char *)(unsigned int)v24,
          UserDataCount);
        v25 = v29;
        if ( v29 )
        {
          v29 = 0;
          (*(void (__fastcall **)(struct Windows::Internal::Security::Authentication::Web::IWamProviderRegistrationInformation *))(*(_QWORD *)v25 + 16LL))(v25);
        }
        v23 = v30;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x83,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\pluginreginternal.cpp",
        (const char *)(unsigned int)v20,
        UserDataCount);
      v22 = v29;
      if ( v29 )
      {
        v29 = 0;
        (*(void (__fastcall **)(struct Windows::Internal::Security::Authentication::Web::IWamProviderRegistrationInformation *))(*(_QWORD *)v22 + 16LL))(v22);
      }
      v23 = v30;
    }
    if ( v23 )
      WindowsDeleteString(v23);
    if ( v10 )
      WindowsDeleteString(v10);
    if ( v9 )
      WindowsDeleteString(v9);
    if ( v8 )
      WindowsDeleteString(v8);
    return v21;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6D,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\pluginreginternal.cpp",
      (const char *)(unsigned int)v5,
      UserDataCount);
    if ( string )
      WindowsDeleteString(string);
    if ( v33 )
      WindowsDeleteString(v33);
    if ( v32 )
      WindowsDeleteString(v32);
    return v6;
  }
}

```

## disassembly

```asm
0x1800262f0  mov     [rsp-8+arg_18], rbx
0x1800262f5  push    rbp
0x1800262f6  push    rsi
0x1800262f7  push    rdi
0x1800262f8  push    r12
0x1800262fa  push    r13
0x1800262fc  push    r14
0x1800262fe  push    r15
0x180026300  lea     rbp, [rsp-27h]
0x180026305  sub     rsp, 0D0h
0x18002630c  mov     rax, cs:__security_cookie
0x180026313  xor     rax, rsp
0x180026316  mov     [rbp+57h+var_40], rax
0x18002631a  mov     r13, r8
0x18002631d  mov     rax, rdx
0x180026320  mov     r12, rcx
0x180026323  xor     r15d, r15d
0x180026326  mov     [rbp+57h+var_B8], r15
0x18002632a  mov     [rbp+57h+var_B0], r15
0x18002632e  mov     [rbp+57h+string], r15
0x180026332  lea     r9, [rbp+57h+string]; struct Windows::Internal::String *
0x180026336  lea     r8, [rbp+57h+var_B0]; struct Windows::Internal::String *
0x18002633a  lea     rdx, [rbp+57h+var_B8]; struct Windows::Internal::String *
0x18002633e  mov     rcx, rax; struct Windows::Security::Credentials::IWebAccountProvider *
0x180026341  call    ?MapAliasesToPluginId@PluginManager@TokenBroker@Authentication@Security@Internal@Windows@@SAJPEAUIWebAccountProvider@Credentials@46@AEAVString@56@11@Z; Windows::Internal::Security::Authentication::TokenBroker::PluginManager::MapAliasesToPluginId(Windows::Security::Credentials::IWebAccountProvider *,Windows::Internal::String &,Windows::Internal::String &,Windows::Internal::String &)
0x180026346  mov     ebx, eax
0x180026348  test    eax, eax
0x18002634a  jns     short loc_18002639B
0x18002634c  mov     rcx, [rbp+5Fh]; this
0x180026350  mov     r9d, eax; char *
0x180026353  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18002635a  mov     edx, 6Dh ; 'm'; void *
0x18002635f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026364  nop
0x180026365  mov     rcx, [rbp+57h+string]; string
0x180026369  test    rcx, rcx
0x18002636c  jz      short loc_180026375
0x18002636e  call    cs:__imp_WindowsDeleteString
0x180026374  nop
0x180026375  mov     rcx, [rbp+57h+var_B0]; string
0x180026379  test    rcx, rcx
0x18002637c  jz      short loc_180026385
0x18002637e  call    cs:__imp_WindowsDeleteString
0x180026384  nop
0x180026385  mov     rcx, [rbp+57h+var_B8]; string
0x180026389  test    rcx, rcx
0x18002638c  jz      short loc_180026394
0x18002638e  call    cs:__imp_WindowsDeleteString
0x180026394  mov     eax, ebx
0x180026396  jmp     loc_180026681
0x18002639b  mov     eax, cs:dword_180175000
0x1800263a1  mov     rsi, [rbp+57h+var_B8]
0x1800263a5  mov     rbx, [rbp+57h+var_B0]
0x1800263a9  mov     rdi, [rbp+57h+string]
0x1800263ad  cmp     eax, 4
0x1800263b0  jbe     loc_18002652F
0x1800263b6  xor     edx, edx; length
0x1800263b8  mov     rcx, rdi; string
0x1800263bb  call    cs:__imp_WindowsGetStringRawBuffer
0x1800263c1  mov     r15, rax
0x1800263c4  mov     rcx, rbx; string
0x1800263c7  call    cs:__imp_WindowsIsStringEmpty
0x1800263cd  test    eax, eax
0x1800263cf  jz      short loc_1800263DA
0x1800263d1  lea     r14, aNull_1; "NULL"
0x1800263d8  jmp     short loc_1800263E8
0x1800263da  xor     edx, edx; length
0x1800263dc  mov     rcx, rbx; string
0x1800263df  call    cs:__imp_WindowsGetStringRawBuffer
0x1800263e5  mov     r14, rax
0x1800263e8  xor     edx, edx; length
0x1800263ea  mov     rcx, rsi; string
0x1800263ed  call    cs:__imp_WindowsGetStringRawBuffer
0x1800263f3  mov     r8, rax
0x1800263f6  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800263fd  test    r15, r15
0x180026400  jz      short loc_180026425
0x180026402  mov     rdx, rcx
0x180026405  nop     word ptr [rax+rax+00000000h]
0x180026410  lea     rdx, [rdx+1]
0x180026414  cmp     word ptr [r15+rdx*2], 0
0x18002641a  jnz     short loc_180026410
0x18002641c  lea     edx, ds:2[rdx*2]
0x180026423  jmp     short loc_180026431
0x180026425  lea     r15, word_1801330B0
0x18002642c  mov     edx, 2
0x180026431  mov     [rbp+57h+var_50], r15
0x180026435  mov     [rbp+57h+var_48], edx
0x180026438  xor     r15d, r15d
0x18002643b  mov     [rbp+57h+var_44], r15d
0x18002643f  test    r14, r14
0x180026442  jz      short loc_180026464
0x180026444  mov     rax, rcx
0x180026447  nop     word ptr [rax+rax+00000000h]
0x180026450  lea     rax, [rax+1]
0x180026454  cmp     [r14+rax*2], r15w
0x180026459  jnz     short loc_180026450
0x18002645b  lea     eax, ds:2[rax*2]
0x180026462  jmp     short loc_180026470
0x180026464  lea     r14, word_1801330B0
0x18002646b  mov     eax, 2
0x180026470  mov     [rbp+57h+var_60], r14
0x180026474  mov     [rbp+57h+var_58], eax
0x180026477  mov     [rbp+57h+var_54], r15d
0x18002647b  test    r8, r8
0x18002647e  jz      short loc_180026494
0x180026480  lea     rcx, [rcx+1]
0x180026484  cmp     [r8+rcx*2], r15w
0x180026489  jnz     short loc_180026480
0x18002648b  lea     ecx, ds:2[rcx*2]
0x180026492  jmp     short loc_1800264A0
0x180026494  lea     r8, word_1801330B0
0x18002649b  mov     ecx, 2
0x1800264a0  mov     [rbp+57h+var_70], r8
0x1800264a4  mov     [rbp+57h+var_68], ecx
0x1800264a7  mov     [rbp+57h+var_64], r15d
0x1800264ab  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x1800264b2  movzx   eax, cs:word_18015134B
0x1800264b9  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x1800264bc  mov     [rbp+57h+EventDescriptor.Keyword], r15
0x1800264c0  mov     rax, cs:off_180175008
0x1800264c7  mov     [rbp+57h+var_90.Ptr], rax
0x1800264cb  movzx   eax, word ptr [rax]
0x1800264ce  mov     [rbp+57h+var_90.Size], eax
0x1800264d1  mov     dword ptr [rbp+57h+var_90.0Ch], 2
0x1800264d8  lea     rax, byte_180151355
0x1800264df  mov     [rbp+57h+var_80], rax
0x1800264e3  mov     [rbp+57h+var_78], 40h ; '@'
0x1800264ea  mov     [rbp+57h+var_74], 1
0x1800264f1  lea     rax, _TraceLoggingMetadataEnd
0x1800264f8  lea     rcx, _TraceLoggingMetadata
0x1800264ff  sub     eax, ecx
0x180026501  mov     dword ptr [rbp+57h+var_C0], eax
0x180026504  mov     eax, dword ptr [rbp+57h+var_C0]
0x180026507  lea     rax, [rbp+57h+var_90]
0x18002650b  mov     [rsp+100h+UserData], rax; UserData
0x180026510  mov     [rsp+100h+UserDataCount], 5; int
0x180026518  xor     r9d, r9d; RelatedActivityId
0x18002651b  xor     r8d, r8d; ActivityId
0x18002651e  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x180026522  mov     rcx, cs:RegHandle; RegHandle
0x180026529  call    cs:__imp_EventWriteTransfer
0x18002652f  mov     [rbp+57h+var_C8], r15
0x180026533  mov     [rbp+57h+var_D0], r15
0x180026537  lea     r8, [rbp+57h+var_D0]; struct Windows::Internal::Security::Authentication::Web::IWamProviderRegistrationInformation **
0x18002653b  mov     rdx, r12; this
0x18002653e  mov     rcx, rdi; HSTRING
0x180026541  call    ?GetFromId@CWamProviderRegistrationInternal@Web@Authentication@Security@Internal@Windows@@SAJPEAUHSTRING__@@AEAVCallerContext@23456@PEAPEAUIWamProviderRegistrationInformation@23456@@Z; Windows::Internal::Security::Authentication::Web::CWamProviderRegistrationInternal::GetFromId(HSTRING__ *,Windows::Internal::Security::Authentication::Web::CallerContext &,Windows::Internal::Security::Authentication::Web::IWamProviderRegistrationInformation * *)
0x180026546  mov     r14d, eax
0x180026549  test    eax, eax
0x18002654b  jns     short loc_180026589
0x18002654d  mov     rcx, [rbp+5Fh]; this
0x180026551  mov     r9d, eax; char *
0x180026554  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18002655b  mov     edx, 83h; void *
0x180026560  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026565  nop
0x180026566  mov     rcx, [rbp+57h+var_D0]
0x18002656a  test    rcx, rcx
0x18002656d  jz      short loc_180026580
0x18002656f  mov     [rbp+57h+var_D0], r15
0x180026573  mov     rax, [rcx]
0x180026576  mov     rax, [rax+10h]
0x18002657a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002657f  nop
0x180026580  mov     rcx, [rbp+57h+var_C8]
0x180026584  jmp     loc_180026646
0x180026589  mov     rcx, [rbp+57h+var_D0]
0x18002658d  mov     rax, [rcx]
0x180026590  lea     rdx, [rbp+57h+var_C8]
0x180026594  mov     rax, [rax+58h]
0x180026598  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002659d  mov     r14d, eax
0x1800265a0  test    eax, eax
0x1800265a2  jns     short loc_1800265DD
0x1800265a4  mov     rcx, [rbp+5Fh]; this
0x1800265a8  mov     r9d, eax; char *
0x1800265ab  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800265b2  mov     edx, 85h; void *
0x1800265b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800265bc  nop
0x1800265bd  mov     rcx, [rbp+57h+var_D0]
0x1800265c1  test    rcx, rcx
0x1800265c4  jz      short loc_1800265D7
0x1800265c6  mov     [rbp+57h+var_D0], r15
0x1800265ca  mov     rax, [rcx]
0x1800265cd  mov     rax, [rax+10h]
0x1800265d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800265d6  nop
0x1800265d7  mov     rcx, [rbp+57h+var_C8]
0x1800265db  jmp     short loc_180026646
0x1800265dd  mov     eax, cs:dword_180175000
0x1800265e3  cmp     eax, 5
0x1800265e6  jbe     short loc_180026617
0x1800265e8  xor     edx, edx; length
0x1800265ea  mov     rcx, [rbp+57h+var_C8]; string
0x1800265ee  call    cs:__imp_WindowsGetStringRawBuffer
0x1800265f4  mov     [rbp+57h+var_C0], rax
0x1800265f8  lea     rax, [rbp+57h+var_C0]
0x1800265fc  mov     qword ptr [rsp+100h+UserDataCount], rax
0x180026601  xor     r8d, r8d
0x180026604  lea     rdx, word_180151312
0x18002660b  lea     rcx, dword_180175000
0x180026612  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180026617  mov     rax, [rbp+57h+var_C8]
0x18002661b  mov     [r13+0], rax
0x18002661f  mov     rcx, r15
0x180026622  mov     [rbp+57h+var_C8], rcx
0x180026626  mov     rdx, [rbp+57h+var_D0]
0x18002662a  test    rdx, rdx
0x18002662d  jz      short loc_180026646
0x18002662f  mov     [rbp+57h+var_D0], r15
0x180026633  mov     rax, [rdx]
0x180026636  mov     rcx, rdx
0x180026639  mov     rax, [rax+10h]
0x18002663d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026642  mov     rcx, [rbp+57h+var_C8]; string
0x180026646  test    rcx, rcx
0x180026649  jz      short loc_180026652
0x18002664b  call    cs:__imp_WindowsDeleteString
0x180026651  nop
0x180026652  test    rdi, rdi
0x180026655  jz      short loc_180026661
0x180026657  mov     rcx, rdi; string
0x18002665a  call    cs:__imp_WindowsDeleteString
0x180026660  nop
0x180026661  test    rbx, rbx
0x180026664  jz      short loc_180026670
0x180026666  mov     rcx, rbx; string
0x180026669  call    cs:__imp_WindowsDeleteString
0x18002666f  nop
0x180026670  test    rsi, rsi
0x180026673  jz      short loc_18002667E
0x180026675  mov     rcx, rsi; string
0x180026678  call    cs:__imp_WindowsDeleteString
0x18002667e  mov     eax, r14d
0x180026681  mov     rcx, [rbp+57h+var_40]
0x180026685  xor     rcx, rsp; StackCookie
0x180026688  call    __security_check_cookie
0x18002668d  mov     rbx, [rsp+100h+arg_18]
0x180026695  add     rsp, 0D0h
0x18002669c  pop     r15
0x18002669e  pop     r14
0x1800266a0  pop     r13
0x1800266a2  pop     r12
0x1800266a4  pop     rdi
0x1800266a5  pop     rsi
0x1800266a6  pop     rbp
0x1800266a7  retn
```
