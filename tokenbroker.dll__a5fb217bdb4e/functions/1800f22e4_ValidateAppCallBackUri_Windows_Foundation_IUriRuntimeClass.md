# ValidateAppCallBackUri(Windows::Foundation::IUriRuntimeClass *)

- ea: `0x1800f22e4`
- end: `0x1800f257d`
- name: `?ValidateAppCallBackUri@@YAJPEAUIUriRuntimeClass@Foundation@Windows@@@Z`
- size: `665`
- prototype: `__int64 __fastcall(struct Windows::Foundation::IUriRuntimeClass *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800d48b0`

## callees

- `0x180045a04`
- `0x18005d6c0`
- `0x18007ef3c`
- `0x18008e690`
- `0x1800f22e4`
- `0x18011b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800f2376`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800f2376`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f2363`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f23a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f242d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f2465`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f2363`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f23a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f242d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f2465`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f24bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f2558`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f24bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f2558`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800f232e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800f2411`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800f232e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800f2411`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800f243a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800f243a`

## string_xrefs

- `0x1800f2394`: `The ApplicationCallbackUri is invalid`
- `0x1800f2454`: `The ApplicationCallbackUri is invalid`
- `0x1800f24d8`: `The ApplicationCallbackUri is invalid`
- `0x1800f2516`: `The ApplicationCallbackUri is invalid`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ValidateAppCallBackUri(struct Windows::Foundation::IUriRuntimeClass *a1)
{
  int v2; // ecx
  int v3; // r8d
  int v4; // r9d
  PCWSTR StringRawBuffer; // rax
  int v6; // ebx
  int v7; // ecx
  int v8; // r8d
  int v9; // r9d
  const WCHAR *v10; // rax
  int v12; // [rsp+40h] [rbp+7h] BYREF
  HSTRING string; // [rsp+48h] [rbp+Fh] BYREF
  HSTRING v14; // [rsp+50h] [rbp+17h] BYREF
  PCWSTR v15; // [rsp+58h] [rbp+1Fh] BYREF
  PCWSTR v16; // [rsp+60h] [rbp+27h]
  PSID Sid; // [rsp+68h] [rbp+2Fh] BYREF
  __int64 v18; // [rsp+70h] [rbp+37h] BYREF
  int v19; // [rsp+78h] [rbp+3Fh]
  wchar_t v20; // [rsp+7Ch] [rbp+43h]

  string = 0;
  if ( (*(int (__fastcall **)(struct Windows::Foundation::IUriRuntimeClass *, HSTRING *))(*(_QWORD *)a1 + 136LL))(
         a1,
         &string) < 0
    || WindowsIsStringEmpty(string) )
  {
    v6 = -2147024809;
    if ( (unsigned int)dword_180175000 > 2 )
    {
      v15 = L"The ApplicationCallbackUri is invalid";
      v12 = -2147024809;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        v2,
        (unsigned int)&unk_1801531F0,
        v3,
        v4,
        (__int64)&v12,
        (__int64)&v15);
    }
    goto LABEL_18;
  }
  v18 = *(_QWORD *)L"ms-app";
  v19 = *(_DWORD *)L"pp";
  v20 = aMsApp_0[6];
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  if ( (unsigned int)_o__wcsnicmp(&v18, StringRawBuffer, 6) )
  {
    v6 = -2147024809;
    if ( (unsigned int)dword_180175000 > 2 )
    {
      v16 = L"The ApplicationCallbackUri is invalid";
      v15 = WindowsGetStringRawBuffer(string, 0);
      v12 = -2147024809;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        &dword_180175000,
        byte_180153233,
        0);
    }
LABEL_18:
    TryOriginateError(-2147024809, 0x3F2u);
    goto LABEL_19;
  }
  v14 = 0;
  v6 = (*(__int64 (__fastcall **)(struct Windows::Foundation::IUriRuntimeClass *, HSTRING *))(*(_QWORD *)a1 + 88LL))(
         a1,
         &v14);
  if ( v6 < 0 || WindowsIsStringEmpty(v14) )
  {
    v6 = -2147024809;
    if ( (unsigned int)dword_180175000 > 2 )
    {
      v15 = L"The ApplicationCallbackUri is invalid";
      v12 = -2147024809;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        v7,
        (unsigned int)&unk_180153168,
        v8,
        v9,
        (__int64)&v12,
        (__int64)&v15);
    }
  }
  else
  {
    Sid = 0;
    v10 = WindowsGetStringRawBuffer(v14, 0);
    if ( ConvertStringSidToSidW(v10, &Sid) )
      goto LABEL_12;
    v6 = -2147024809;
    if ( (unsigned int)dword_180175000 > 2 )
    {
      v15 = L"The ApplicationCallbackUri is invalid";
      v16 = WindowsGetStringRawBuffer(v14, 0);
      v12 = -2147024809;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        &dword_180175000,
        byte_1801531A9,
        0);
    }
  }
  TryOriginateError(-2147024809, 0x3F2u);
LABEL_12:
  if ( v14 )
    WindowsDeleteString(v14);
LABEL_19:
  if ( string )
    WindowsDeleteString(string);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800f22e4  mov     [rsp-8+arg_8], rbx
0x1800f22e9  push    rbp
0x1800f22ea  lea     rbp, [rsp-57h]
0x1800f22ef  sub     rsp, 90h
0x1800f22f6  mov     rax, cs:__security_cookie
0x1800f22fd  xor     rax, rsp
0x1800f2300  mov     [rbp+57h+var_10], rax
0x1800f2304  mov     rbx, rcx
0x1800f2307  mov     [rbp+57h+string], 0
0x1800f230f  mov     rax, [rcx]
0x1800f2312  lea     rdx, [rbp+57h+string]
0x1800f2316  mov     rax, [rax+88h]
0x1800f231d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f2322  test    eax, eax
0x1800f2324  js      loc_1800F2506
0x1800f232a  mov     rcx, [rbp+57h+string]; string
0x1800f232e  call    cs:__imp_WindowsIsStringEmpty
0x1800f2334  test    eax, eax
0x1800f2336  jnz     loc_1800F2506
0x1800f233c  movsd   xmm0, qword ptr cs:aMsApp_0; "ms-app"
0x1800f2344  movsd   [rbp+57h+var_20], xmm0
0x1800f2349  mov     eax, dword ptr cs:aMsApp_0+8; "pp"
0x1800f234f  mov     [rbp+57h+var_18], eax
0x1800f2352  movzx   eax, word ptr cs:aMsApp_0+0Ch; ""
0x1800f2359  mov     [rbp+57h+var_14], ax
0x1800f235d  xor     edx, edx; length
0x1800f235f  mov     rcx, [rbp+57h+string]; string
0x1800f2363  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f2369  mov     r8d, 6
0x1800f236f  mov     rdx, rax
0x1800f2372  lea     rcx, [rbp+57h+var_20]
0x1800f2376  call    cs:__imp__o__wcsnicmp
0x1800f237c  test    eax, eax
0x1800f237e  jz      short loc_1800F23E8
0x1800f2380  mov     eax, cs:dword_180175000
0x1800f2386  mov     ebx, 80070057h
0x1800f238b  cmp     eax, 2
0x1800f238e  jbe     loc_1800F2542
0x1800f2394  lea     rax, aTheApplication; "The ApplicationCallbackUri is invalid"
0x1800f239b  mov     [rbp+57h+var_30], rax
0x1800f239f  xor     edx, edx; length
0x1800f23a1  mov     rcx, [rbp+57h+string]; string
0x1800f23a5  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f23ab  mov     [rbp+57h+var_38], rax
0x1800f23af  mov     [rbp+57h+var_50], ebx
0x1800f23b2  lea     rax, [rbp+57h+var_30]
0x1800f23b6  mov     [rsp+90h+var_60], rax
0x1800f23bb  lea     rax, [rbp+57h+var_38]
0x1800f23bf  mov     [rsp+90h+var_68], rax
0x1800f23c4  lea     rax, [rbp+57h+var_50]
0x1800f23c8  mov     [rsp+90h+var_70], rax
0x1800f23cd  xor     r8d, r8d
0x1800f23d0  lea     rdx, byte_180153233
0x1800f23d7  lea     rcx, dword_180175000
0x1800f23de  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800f23e3  jmp     loc_1800F2542
0x1800f23e8  mov     [rbp+57h+var_40], 0
0x1800f23f0  mov     rax, [rbx]
0x1800f23f3  lea     rdx, [rbp+57h+var_40]
0x1800f23f7  mov     rcx, rbx
0x1800f23fa  mov     rax, [rax+58h]
0x1800f23fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f2403  mov     ebx, eax
0x1800f2405  test    eax, eax
0x1800f2407  js      loc_1800F24C8
0x1800f240d  mov     rcx, [rbp+57h+var_40]; string
0x1800f2411  call    cs:__imp_WindowsIsStringEmpty
0x1800f2417  test    eax, eax
0x1800f2419  jnz     loc_1800F24C8
0x1800f241f  mov     [rbp+57h+Sid], 0
0x1800f2427  xor     edx, edx; length
0x1800f2429  mov     rcx, [rbp+57h+var_40]; string
0x1800f242d  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f2433  lea     rdx, [rbp+57h+Sid]; Sid
0x1800f2437  mov     rcx, rax; StringSid
0x1800f243a  call    cs:__imp_ConvertStringSidToSidW
0x1800f2440  test    eax, eax
0x1800f2442  jnz     short loc_1800F24B0
0x1800f2444  mov     eax, cs:dword_180175000
0x1800f244a  mov     ebx, 80070057h
0x1800f244f  cmp     eax, 2
0x1800f2452  jbe     short loc_1800F24A3
0x1800f2454  lea     rax, aTheApplication; "The ApplicationCallbackUri is invalid"
0x1800f245b  mov     [rbp+57h+var_38], rax
0x1800f245f  xor     edx, edx; length
0x1800f2461  mov     rcx, [rbp+57h+var_40]; string
0x1800f2465  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f246b  mov     [rbp+57h+var_30], rax
0x1800f246f  mov     [rbp+57h+var_50], ebx
0x1800f2472  lea     rax, [rbp+57h+var_38]
0x1800f2476  mov     [rsp+90h+var_60], rax
0x1800f247b  lea     rax, [rbp+57h+var_30]
0x1800f247f  mov     [rsp+90h+var_68], rax
0x1800f2484  lea     rax, [rbp+57h+var_50]
0x1800f2488  mov     [rsp+90h+var_70], rax
0x1800f248d  xor     r8d, r8d
0x1800f2490  lea     rdx, byte_1801531A9
0x1800f2497  lea     rcx, dword_180175000
0x1800f249e  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800f24a3  mov     edx, 3F2h; unsigned __int16
0x1800f24a8  mov     ecx, ebx; int
0x1800f24aa  call    ?TryOriginateError@@YAXJG@Z; TryOriginateError(long,ushort)
0x1800f24af  nop
0x1800f24b0  mov     rcx, [rbp+57h+var_40]; string
0x1800f24b4  test    rcx, rcx
0x1800f24b7  jz      loc_1800F254F
0x1800f24bd  call    cs:__imp_WindowsDeleteString
0x1800f24c3  jmp     loc_1800F254F
0x1800f24c8  mov     eax, cs:dword_180175000
0x1800f24ce  mov     ebx, 80070057h
0x1800f24d3  cmp     eax, 2
0x1800f24d6  jbe     short loc_1800F24A3
0x1800f24d8  lea     rax, aTheApplication; "The ApplicationCallbackUri is invalid"
0x1800f24df  mov     [rbp+57h+var_38], rax
0x1800f24e3  mov     [rbp+57h+var_50], ebx
0x1800f24e6  lea     rax, [rbp+57h+var_38]
0x1800f24ea  mov     [rsp+90h+var_68], rax
0x1800f24ef  lea     rax, [rbp+57h+var_50]
0x1800f24f3  mov     [rsp+90h+var_70], rax
0x1800f24f8  lea     rdx, unk_180153168
0x1800f24ff  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x1800f2504  jmp     short loc_1800F24A3
0x1800f2506  mov     eax, cs:dword_180175000
0x1800f250c  mov     ebx, 80070057h
0x1800f2511  cmp     eax, 2
0x1800f2514  jbe     short loc_1800F2542
0x1800f2516  lea     rax, aTheApplication; "The ApplicationCallbackUri is invalid"
0x1800f251d  mov     [rbp+57h+var_38], rax
0x1800f2521  mov     [rbp+57h+var_50], ebx
0x1800f2524  lea     rax, [rbp+57h+var_38]
0x1800f2528  mov     [rsp+90h+var_68], rax
0x1800f252d  lea     rax, [rbp+57h+var_50]
0x1800f2531  mov     [rsp+90h+var_70], rax
0x1800f2536  lea     rdx, unk_1801531F0
0x1800f253d  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x1800f2542  mov     edx, 3F2h; unsigned __int16
0x1800f2547  mov     ecx, ebx; int
0x1800f2549  call    ?TryOriginateError@@YAXJG@Z; TryOriginateError(long,ushort)
0x1800f254e  nop
0x1800f254f  mov     rcx, [rbp+57h+string]; string
0x1800f2553  test    rcx, rcx
0x1800f2556  jz      short loc_1800F255E
0x1800f2558  call    cs:__imp_WindowsDeleteString
0x1800f255e  mov     eax, ebx
0x1800f2560  mov     rcx, [rbp+57h+var_10]
0x1800f2564  xor     rcx, rsp; StackCookie
0x1800f2567  call    __security_check_cookie
0x1800f256c  mov     rbx, [rsp+90h+arg_8]
0x1800f2574  add     rsp, 90h
0x1800f257b  pop     rbp
0x1800f257c  retn
```
