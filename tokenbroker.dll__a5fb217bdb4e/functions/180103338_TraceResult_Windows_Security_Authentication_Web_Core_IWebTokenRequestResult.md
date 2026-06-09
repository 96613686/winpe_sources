# TraceResult(Windows::Security::Authentication::Web::Core::IWebTokenRequestResult *)

- ea: `0x180103338`
- end: `0x180103794`
- name: `?TraceResult@@YAXPEAUIWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Z`
- size: `1116`
- prototype: `void __fastcall(struct Windows::Security::Authentication::Web::Core::IWebTokenRequestResult *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180100fb8`

## callees

- `0x180005288`
- `0x180005a54`
- `0x180007350`
- `0x180045a04`
- `0x18004c014`
- `0x18004e850`
- `0x18004fdbc`
- `0x180103338`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010341a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180103606`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801036cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010341a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180103606`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801036cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180103645`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010372e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180103748`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180103780`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180103645`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010372e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180103748`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180103780`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180103401`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18010356a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1801036b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180103401`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18010356a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1801036b6`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall TraceResult(struct Windows::Security::Authentication::Web::Core::IWebTokenRequestResult *a1)
{
  void (__fastcall *v2)(struct Windows::Security::Authentication::Web::Core::IWebTokenRequestResult *, __int64 *); // rbx
  int v3; // ecx
  int v4; // r8d
  int v5; // r9d
  WCHAR *StringRawBuffer; // rax
  void (__fastcall *v7)(struct Windows::Security::Authentication::Web::Core::IWebTokenRequestResult *, __int64 *); // rbx
  int v8; // r9d
  unsigned int i; // esi
  __int64 v10; // rdi
  int (__fastcall *v11)(__int64, _QWORD, __int64 *); // rbx
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  __int64 v15; // rdi
  void (__fastcall *v16)(__int64, __int64 *); // rbx
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  __int64 v20; // rdi
  void (__fastcall *v21)(__int64, __int64 *); // rbx
  int v22; // ecx
  int v23; // r8d
  int v24; // r9d
  PCWSTR v25; // rax
  __int64 v26; // [rsp+40h] [rbp-39h] BYREF
  __int64 v27; // [rsp+48h] [rbp-31h] BYREF
  __int64 v28; // [rsp+50h] [rbp-29h] BYREF
  int v29; // [rsp+58h] [rbp-21h] BYREF
  int v30; // [rsp+5Ch] [rbp-1Dh] BYREF
  __int64 v31; // [rsp+60h] [rbp-19h] BYREF
  __int64 v32; // [rsp+68h] [rbp-11h] BYREF
  HSTRING v33; // [rsp+70h] [rbp-9h] BYREF
  HSTRING v34; // [rsp+78h] [rbp-1h] BYREF
  HSTRING string; // [rsp+80h] [rbp+7h] BYREF
  unsigned int v36; // [rsp+88h] [rbp+Fh] BYREF
  unsigned int v37; // [rsp+8Ch] [rbp+13h] BYREF
  int v38; // [rsp+90h] [rbp+17h] BYREF
  unsigned int v39; // [rsp+94h] [rbp+1Bh] BYREF
  __int64 v40; // [rsp+98h] [rbp+1Fh] BYREF
  HSTRING v41; // [rsp+A0h] [rbp+27h] BYREF
  _QWORD v42[5]; // [rsp+A8h] [rbp+2Fh] BYREF
  unsigned int v43; // [rsp+E0h] [rbp+67h] BYREF
  int v44; // [rsp+E8h] [rbp+6Fh] BYREF
  unsigned int v45; // [rsp+F0h] [rbp+77h] BYREF
  int v46; // [rsp+F8h] [rbp+7Fh] BYREF

  if ( a1 )
  {
    v29 = 2;
    (*(void (__fastcall **)(struct Windows::Security::Authentication::Web::Core::IWebTokenRequestResult *, int *))(*(_QWORD *)a1 + 56LL))(
      a1,
      &v29);
    v46 = 0;
    string = 0;
    v28 = 0;
    v2 = *(void (__fastcall **)(struct Windows::Security::Authentication::Web::Core::IWebTokenRequestResult *, __int64 *))(*(_QWORD *)a1 + 64LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
    v2(a1, &v28);
    if ( v28 )
    {
      (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v28 + 48LL))(v28, &v46);
      (*(void (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v28 + 56LL))(v28, &string);
    }
    if ( (unsigned int)dword_180175000 > 5 )
    {
      if ( WindowsIsStringEmpty(string) )
        StringRawBuffer = (WCHAR *)L"NULL";
      else
        StringRawBuffer = (WCHAR *)WindowsGetStringRawBuffer(string, 0);
      v33 = (HSTRING)StringRawBuffer;
      v44 = v46;
      LOBYTE(v43) = v28 != 0;
      v45 = v29;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        v3,
        (unsigned int)&unk_180156BB8,
        v4,
        v5,
        (__int64)&v45,
        (__int64)&v43,
        (__int64)&v44,
        (__int64)&v33);
    }
    v32 = 0;
    v7 = *(void (__fastcall **)(struct Windows::Security::Authentication::Web::Core::IWebTokenRequestResult *, __int64 *))(*(_QWORD *)a1 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
    v7(a1, &v32);
    if ( v32 )
    {
      v45 = 0;
      (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v32 + 56LL))(v32, &v45);
      if ( (unsigned int)dword_180175000 > 5 )
      {
        v43 = v45;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (unsigned int)&dword_180175000,
          (unsigned int)&byte_180156C2F,
          0,
          v8,
          (__int64)&v43);
      }
      for ( i = 0; i < v45; ++i )
      {
        v27 = 0;
        v10 = v32;
        v11 = *(int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v32 + 48LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
        if ( v11(v10, i, &v27) >= 0 )
        {
          v33 = 0;
          (*(void (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v27 + 48LL))(v27, &v33);
          if ( (unsigned int)dword_180175000 > 5 )
          {
            LOBYTE(v43) = !WindowsIsStringEmpty(v33);
            v36 = i;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(
              v12,
              (unsigned int)word_180156B32,
              v13,
              v14,
              (__int64)&v36,
              (__int64)&v43);
          }
          v31 = 0;
          v15 = v27;
          v16 = *(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v27 + 64LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
          v16(v15, &v31);
          if ( v31 )
          {
            v41 = 0;
            v40 = 0;
            if ( (int)Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount>::As<Windows::Security::Credentials::IWebAccount2>(
                        &v31,
                        &v40) >= 0 )
              (*(void (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v40 + 48LL))(v40, &v41);
            if ( (unsigned int)dword_180175000 > 5 )
            {
              v42[0] = WindowsGetStringRawBuffer(v41, 0);
              v37 = i;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
                v17,
                (unsigned int)byte_180156B7B,
                v18,
                v19,
                (__int64)&v37,
                (__int64)v42);
            }
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
            if ( v41 )
              WindowsDeleteString(v41);
          }
          v30 = 0;
          v34 = 0;
          v26 = 0;
          v20 = v27;
          v21 = *(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v27 + 56LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26);
          v21(v20, &v26);
          if ( v26 )
          {
            (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v26 + 48LL))(v26, &v30);
            (*(void (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v26 + 56LL))(v26, &v34);
          }
          if ( (unsigned int)dword_180175000 > 5 )
          {
            if ( WindowsIsStringEmpty(v34) )
              v25 = L"NULL";
            else
              v25 = WindowsGetStringRawBuffer(v34, 0);
            v42[0] = v25;
            v38 = v30;
            LOBYTE(v44) = v26 != 0;
            v39 = i;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
              v22,
              (unsigned int)&byte_180156A5F,
              v23,
              v24,
              (__int64)&v39,
              (__int64)&v44,
              (__int64)&v38,
              (__int64)v42);
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26);
          if ( v34 )
            WindowsDeleteString(v34);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
          if ( v33 )
            WindowsDeleteString(v33);
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
      }
    }
    else if ( (unsigned int)dword_180175000 > 5 )
    {
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        &dword_180175000,
        qword_180156C08,
        0,
        0);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
    if ( string )
      WindowsDeleteString(string);
  }
  else if ( (unsigned int)dword_180175000 > 5 )
  {
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180175000,
      byte_180156C63,
      0,
      0);
  }
}

```

## disassembly

```asm
0x180103338  push    rbp
0x18010333a  push    rbx
0x18010333b  push    rsi
0x18010333c  push    rdi
0x18010333d  push    r14
0x18010333f  lea     rbp, [rsp-37h]
0x180103344  sub     rsp, 0B0h
0x18010334b  mov     rdi, rcx
0x18010334e  xor     r14d, r14d
0x180103351  test    rcx, rcx
0x180103354  jnz     short loc_180103383
0x180103356  mov     eax, cs:dword_180175000
0x18010335c  cmp     eax, 5
0x18010335f  jbe     loc_180103786
0x180103365  xor     r9d, r9d
0x180103368  xor     r8d, r8d
0x18010336b  lea     rdx, byte_180156C63
0x180103372  lea     rcx, dword_180175000
0x180103379  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18010337e  jmp     loc_180103786
0x180103383  mov     [rbp+57h+var_78], 2
0x18010338a  mov     rax, [rcx]
0x18010338d  lea     rdx, [rbp+57h+var_78]
0x180103391  mov     rax, [rax+38h]
0x180103395  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010339a  mov     [rbp+57h+arg_18], r14d
0x18010339e  mov     [rbp+57h+string], r14
0x1801033a2  mov     [rbp+57h+var_80], r14
0x1801033a6  mov     rax, [rdi]
0x1801033a9  mov     rbx, [rax+40h]
0x1801033ad  lea     rcx, [rbp+57h+var_80]
0x1801033b1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801033b6  lea     rdx, [rbp+57h+var_80]
0x1801033ba  mov     rcx, rdi
0x1801033bd  mov     rax, rbx
0x1801033c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801033c5  mov     rcx, [rbp+57h+var_80]
0x1801033c9  test    rcx, rcx
0x1801033cc  jz      short loc_1801033F2
0x1801033ce  mov     rax, [rcx]
0x1801033d1  lea     rdx, [rbp+57h+arg_18]
0x1801033d5  mov     rax, [rax+30h]
0x1801033d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801033de  mov     rcx, [rbp+57h+var_80]
0x1801033e2  mov     rax, [rcx]
0x1801033e5  lea     rdx, [rbp+57h+string]
0x1801033e9  mov     rax, [rax+38h]
0x1801033ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801033f2  mov     eax, cs:dword_180175000
0x1801033f8  cmp     eax, 5
0x1801033fb  jbe     short loc_180103468
0x1801033fd  mov     rcx, [rbp+57h+string]; string
0x180103401  call    cs:__imp_WindowsIsStringEmpty
0x180103407  test    eax, eax
0x180103409  jz      short loc_180103414
0x18010340b  lea     rax, aNull_1; "NULL"
0x180103412  jmp     short loc_180103420
0x180103414  xor     edx, edx; length
0x180103416  mov     rcx, [rbp+57h+string]; string
0x18010341a  call    cs:__imp_WindowsGetStringRawBuffer
0x180103420  mov     [rbp+57h+var_60], rax
0x180103424  mov     eax, [rbp+57h+arg_18]
0x180103427  mov     [rbp+57h+arg_8], eax
0x18010342a  cmp     [rbp+57h+var_80], r14
0x18010342e  setnz   byte ptr [rbp+57h+arg_0]
0x180103432  mov     eax, [rbp+57h+var_78]
0x180103435  mov     [rbp+57h+arg_10], eax
0x180103438  lea     rax, [rbp+57h+var_60]
0x18010343c  mov     [rsp+0D0h+var_98], rax
0x180103441  lea     rax, [rbp+57h+arg_8]
0x180103445  mov     [rsp+0D0h+var_A0], rax
0x18010344a  lea     rax, [rbp+57h+arg_0]
0x18010344e  mov     [rsp+0D0h+var_A8], rax
0x180103453  lea     rax, [rbp+57h+arg_10]
0x180103457  mov     [rsp+0D0h+var_B0], rax
0x18010345c  lea     rdx, unk_180156BB8
0x180103463  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$00@@U1@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$00@@3AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x180103468  mov     [rbp+57h+var_68], r14
0x18010346c  mov     rax, [rdi]
0x18010346f  mov     rbx, [rax+30h]
0x180103473  lea     rcx, [rbp+57h+var_68]
0x180103477  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010347c  lea     rdx, [rbp+57h+var_68]
0x180103480  mov     rcx, rdi
0x180103483  mov     rax, rbx
0x180103486  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010348b  mov     rcx, [rbp+57h+var_68]
0x18010348f  test    rcx, rcx
0x180103492  jnz     short loc_1801034C1
0x180103494  mov     eax, cs:dword_180175000
0x18010349a  cmp     eax, 5
0x18010349d  jbe     loc_180103763
0x1801034a3  xor     r9d, r9d
0x1801034a6  xor     r8d, r8d
0x1801034a9  lea     rdx, qword_180156C08
0x1801034b0  lea     rcx, dword_180175000
0x1801034b7  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1801034bc  jmp     loc_180103763
0x1801034c1  mov     [rbp+57h+arg_10], r14d
0x1801034c5  mov     rax, [rcx]
0x1801034c8  lea     rdx, [rbp+57h+arg_10]
0x1801034cc  mov     rax, [rax+38h]
0x1801034d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801034d5  mov     eax, cs:dword_180175000
0x1801034db  cmp     eax, 5
0x1801034de  jbe     short loc_180103505
0x1801034e0  mov     eax, [rbp+57h+arg_10]
0x1801034e3  mov     [rbp+57h+arg_0], eax
0x1801034e6  lea     rax, [rbp+57h+arg_0]
0x1801034ea  mov     [rsp+0D0h+var_B0], rax
0x1801034ef  xor     r8d, r8d
0x1801034f2  lea     rdx, byte_180156C2F
0x1801034f9  lea     rcx, dword_180175000
0x180103500  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180103505  mov     esi, r14d
0x180103508  cmp     [rbp+57h+arg_10], r14d
0x18010350c  jbe     loc_180103763
0x180103512  mov     [rbp+57h+var_88], r14
0x180103516  mov     rdi, [rbp+57h+var_68]
0x18010351a  mov     rax, [rdi]
0x18010351d  mov     rbx, [rax+30h]
0x180103521  lea     rcx, [rbp+57h+var_88]
0x180103525  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010352a  lea     r8, [rbp+57h+var_88]
0x18010352e  mov     edx, esi
0x180103530  mov     rcx, rdi
0x180103533  mov     rax, rbx
0x180103536  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010353b  test    eax, eax
0x18010353d  js      loc_18010374F
0x180103543  mov     [rbp+57h+var_60], r14
0x180103547  mov     rcx, [rbp+57h+var_88]
0x18010354b  mov     rax, [rcx]
0x18010354e  lea     rdx, [rbp+57h+var_60]
0x180103552  mov     rax, [rax+30h]
0x180103556  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010355b  mov     eax, cs:dword_180175000
0x180103561  cmp     eax, 5
0x180103564  jbe     short loc_180103597
0x180103566  mov     rcx, [rbp+57h+var_60]; string
0x18010356a  call    cs:__imp_WindowsIsStringEmpty
0x180103570  test    eax, eax
0x180103572  setz    byte ptr [rbp+57h+arg_0]
0x180103576  mov     [rbp+57h+var_48], esi
0x180103579  lea     rax, [rbp+57h+arg_0]
0x18010357d  mov     [rsp+0D0h+var_A8], rax
0x180103582  lea     rax, [rbp+57h+var_48]
0x180103586  mov     [rsp+0D0h+var_B0], rax
0x18010358b  lea     rdx, word_180156B32
0x180103592  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)
0x180103597  mov     [rbp+57h+var_70], r14
0x18010359b  mov     rdi, [rbp+57h+var_88]
0x18010359f  mov     rax, [rdi]
0x1801035a2  mov     rbx, [rax+40h]
0x1801035a6  lea     rcx, [rbp+57h+var_70]
0x1801035aa  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801035af  lea     rdx, [rbp+57h+var_70]
0x1801035b3  mov     rcx, rdi
0x1801035b6  mov     rax, rbx
0x1801035b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801035be  cmp     [rbp+57h+var_70], r14
0x1801035c2  jz      loc_18010364B
0x1801035c8  mov     [rbp+57h+var_30], r14
0x1801035cc  mov     [rbp+57h+var_38], r14
0x1801035d0  lea     rdx, [rbp+57h+var_38]
0x1801035d4  lea     rcx, [rbp+57h+var_70]
0x1801035d8  call    ??$As@UIWebAccount2@Credentials@Security@Windows@@@?$ComPtr@UIWebAccount@Credentials@Security@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWebAccount2@Credentials@Security@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount>::As<Windows::Security::Credentials::IWebAccount2>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount2>>)
0x1801035dd  test    eax, eax
0x1801035df  js      short loc_1801035F5
0x1801035e1  mov     rcx, [rbp+57h+var_38]
0x1801035e5  mov     rax, [rcx]
0x1801035e8  lea     rdx, [rbp+57h+var_30]
0x1801035ec  mov     rax, [rax+30h]
0x1801035f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801035f5  mov     eax, cs:dword_180175000
0x1801035fb  cmp     eax, 5
0x1801035fe  jbe     short loc_180103632
0x180103600  xor     edx, edx; length
0x180103602  mov     rcx, [rbp+57h+var_30]; string
0x180103606  call    cs:__imp_WindowsGetStringRawBuffer
0x18010360c  mov     [rbp+57h+var_28], rax
0x180103610  mov     [rbp+57h+var_44], esi
0x180103613  lea     rax, [rbp+57h+var_28]
0x180103617  mov     [rsp+0D0h+var_A8], rax
0x18010361c  lea     rax, [rbp+57h+var_44]
0x180103620  mov     [rsp+0D0h+var_B0], rax
0x180103625  lea     rdx, byte_180156B7B
0x18010362c  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x180103631  nop
0x180103632  lea     rcx, [rbp+57h+var_38]
0x180103636  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010363b  nop
0x18010363c  mov     rcx, [rbp+57h+var_30]; string
0x180103640  test    rcx, rcx
0x180103643  jz      short loc_18010364B
0x180103645  call    cs:__imp_WindowsDeleteString
0x18010364b  mov     [rbp+57h+var_74], r14d
0x18010364f  mov     [rbp+57h+var_58], r14
0x180103653  mov     [rbp+57h+var_90], r14
0x180103657  mov     rdi, [rbp+57h+var_88]
0x18010365b  mov     rax, [rdi]
0x18010365e  mov     rbx, [rax+38h]
0x180103662  lea     rcx, [rbp+57h+var_90]
0x180103666  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010366b  lea     rdx, [rbp+57h+var_90]
0x18010366f  mov     rcx, rdi
0x180103672  mov     rax, rbx
0x180103675  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010367a  mov     rcx, [rbp+57h+var_90]
0x18010367e  test    rcx, rcx
0x180103681  jz      short loc_1801036A7
0x180103683  mov     rax, [rcx]
0x180103686  lea     rdx, [rbp+57h+var_74]
0x18010368a  mov     rax, [rax+30h]
0x18010368e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180103693  mov     rcx, [rbp+57h+var_90]
0x180103697  mov     rax, [rcx]
0x18010369a  lea     rdx, [rbp+57h+var_58]
0x18010369e  mov     rax, [rax+38h]
0x1801036a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801036a7  mov     eax, cs:dword_180175000
0x1801036ad  cmp     eax, 5
0x1801036b0  jbe     short loc_18010371B
0x1801036b2  mov     rcx, [rbp+57h+var_58]; string
0x1801036b6  call    cs:__imp_WindowsIsStringEmpty
0x1801036bc  test    eax, eax
0x1801036be  jz      short loc_1801036C9
0x1801036c0  lea     rax, aNull_1; "NULL"
0x1801036c7  jmp     short loc_1801036D5
0x1801036c9  xor     edx, edx; length
0x1801036cb  mov     rcx, [rbp+57h+var_58]; string
0x1801036cf  call    cs:__imp_WindowsGetStringRawBuffer
0x1801036d5  mov     [rbp+57h+var_28], rax
0x1801036d9  mov     eax, [rbp+57h+var_74]
0x1801036dc  mov     [rbp+57h+var_40], eax
0x1801036df  cmp     [rbp+57h+var_90], r14
0x1801036e3  setnz   byte ptr [rbp+57h+arg_8]
0x1801036e7  mov     [rbp+57h+var_3C], esi
0x1801036ea  lea     rax, [rbp+57h+var_28]
0x1801036ee  mov     [rsp+0D0h+var_98], rax
0x1801036f3  lea     rax, [rbp+57h+var_40]
0x1801036f7  mov     [rsp+0D0h+var_A0], rax
0x1801036fc  lea     rax, [rbp+57h+arg_8]
0x180103700  mov     [rsp+0D0h+var_A8], rax
0x180103705  lea     rax, [rbp+57h+var_3C]
0x180103709  mov     [rsp+0D0h+var_B0], rax
0x18010370e  lea     rdx, byte_180156A5F
0x180103715  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$00@@U1@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$00@@3AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18010371a  nop
0x18010371b  lea     rcx, [rbp+57h+var_90]
0x18010371f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180103724  nop
0x180103725  mov     rcx, [rbp+57h+var_58]; string
0x180103729  test    rcx, rcx
0x18010372c  jz      short loc_180103735
0x18010372e  call    cs:__imp_WindowsDeleteString
0x180103734  nop
0x180103735  lea     rcx, [rbp+57h+var_70]
0x180103739  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010373e  nop
0x18010373f  mov     rcx, [rbp+57h+var_60]; string
0x180103743  test    rcx, rcx
0x180103746  jz      short loc_18010374F
0x180103748  call    cs:__imp_WindowsDeleteString
0x18010374e  nop
0x18010374f  lea     rcx, [rbp+57h+var_88]
0x180103753  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180103758  inc     esi
0x18010375a  cmp     esi, [rbp+57h+arg_10]
0x18010375d  jb      loc_180103512
0x180103763  lea     rcx, [rbp+57h+var_68]
0x180103767  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010376c  nop
0x18010376d  lea     rcx, [rbp+57h+var_80]
0x180103771  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180103776  nop
0x180103777  mov     rcx, [rbp+57h+string]; string
0x18010377b  test    rcx, rcx
0x18010377e  jz      short loc_180103786
0x180103780  call    cs:__imp_WindowsDeleteString
0x180103786  add     rsp, 0B0h
0x18010378d  pop     r14
0x18010378f  pop     rdi
0x180103790  pop     rsi
0x180103791  pop     rbx
0x180103792  pop     rbp
0x180103793  retn
```
