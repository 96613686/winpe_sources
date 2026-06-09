# Windows::Internal::Flighting::OneSettings::OneSettingsPayload::GetFlightType(Windows::Data::Json::IJsonObject *,Windows::Internal::Flighting::OneSettings::OneSettingsFlightType *)

- ea: `0x180016760`
- end: `0x18001686a`
- name: `?GetFlightType@OneSettingsPayload@OneSettings@Flighting@Internal@Windows@@UEAAJPEAUIJsonObject@Json@Data@5@PEAW4OneSettingsFlightType@2345@@Z`
- size: `266`
- prototype: `__int64 __fastcall(Windows::Internal::Flighting::OneSettings::OneSettingsPayload *__hidden this, struct Windows::Data::Json::IJsonObject *, enum Windows::Internal::Flighting::OneSettings::OneSettingsFlightType *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003110`
- `0x180006b9c`
- `0x18000e5ac`
- `0x180016760`
- `0x180019ac4`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016796`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800167f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001683c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016796`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800167f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001683c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180016814`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180016814`

## string_xrefs

- `0x1800167e0`: `onecore\base\flighting\onesettings\libs\configurationsmanager\onesettingspayload.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall Windows::Internal::Flighting::OneSettings::OneSettingsPayload::GetFlightType(
        Windows::Internal::Flighting::OneSettings::OneSettingsPayload *this,
        struct Windows::Data::Json::IJsonObject *a2,
        enum Windows::Internal::Flighting::OneSettings::OneSettingsFlightType *a3)
{
  __int64 (__fastcall *v5)(struct Windows::Data::Json::IJsonObject *, PVOID, HSTRING *); // rbx
  HSTRING_HEADER *v6; // rax
  int v7; // eax
  unsigned int v8; // ebx
  int v10; // eax
  PCWSTR StringRawBuffer; // rax
  HSTRING string; // [rsp+20h] [rbp-48h] BYREF
  __int16 v13; // [rsp+28h] [rbp-40h] BYREF
  HSTRING_HEADER v14; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  string = 0;
  v5 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, HSTRING *))(*(_QWORD *)a2 + 80LL);
  WindowsDeleteString(0);
  string = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v14, (const WCHAR **)off_18005BBD8);
  v7 = v5(a2, v6[1].Reserved.Reserved1, &string);
  v8 = v7;
  if ( v7 >= 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    FlightIdUtils::WexpConfigurationIdFromFlightId(&v13, StringRawBuffer);
    v10 = (v13 != 0) + 1;
  }
  else
  {
    if ( v7 != -2089484279 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1EC,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\onesettingspayload.cpp",
        (const char *)(unsigned int)v7,
        (int)string);
      WindowsDeleteString(string);
      return v8;
    }
    v10 = 0;
  }
  *(_DWORD *)a3 = v10;
  WindowsDeleteString(string);
  return 0;
}

```

## disassembly

```asm
0x180016760  mov     [rsp+arg_0], rbx
0x180016765  mov     [rsp+arg_18], rsi
0x18001676a  push    rdi
0x18001676b  sub     rsp, 60h
0x18001676f  mov     rax, cs:__security_cookie
0x180016776  xor     rax, rsp
0x180016779  mov     [rsp+68h+var_18], rax
0x18001677e  mov     rdi, r8
0x180016781  mov     rsi, rdx
0x180016784  mov     [rsp+68h+string], 0
0x18001678d  mov     rax, [rdx]
0x180016790  mov     rbx, [rax+50h]
0x180016794  xor     ecx, ecx; string
0x180016796  call    cs:__imp_WindowsDeleteString
0x18001679c  mov     [rsp+68h+string], 0; int
0x1800167a5  lea     rdx, off_18005BBD8; "__flightId"
0x1800167ac  lea     rcx, [rsp+68h+var_38]
0x1800167b1  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800167b6  nop
0x1800167b7  lea     r8, [rsp+68h+string]
0x1800167bc  mov     rdx, [rax+18h]
0x1800167c0  mov     rcx, rsi
0x1800167c3  mov     rax, rbx
0x1800167c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167cb  mov     ebx, eax
0x1800167cd  test    eax, eax
0x1800167cf  jns     short loc_180016801
0x1800167d1  cmp     eax, 83750009h
0x1800167d6  jz      short loc_180016809
0x1800167d8  mov     rcx, [rsp+68h]; this
0x1800167dd  mov     r9d, eax; char *
0x1800167e0  lea     r8, aOnecoreBaseFli_30; "onecore\\base\\flighting\\onesettings\\"...
0x1800167e7  mov     edx, 1ECh; void *
0x1800167ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800167f1  nop
0x1800167f2  mov     rcx, [rsp+68h+string]; string
0x1800167f7  call    cs:__imp_WindowsDeleteString
0x1800167fd  mov     eax, ebx
0x1800167ff  jmp     short loc_18001684A
0x180016801  cmp     ebx, 83750009h
0x180016807  jnz     short loc_18001680D
0x180016809  xor     eax, eax
0x18001680b  jmp     short loc_180016835
0x18001680d  xor     edx, edx; length
0x18001680f  mov     rcx, [rsp+68h+string]; string
0x180016814  call    cs:__imp_WindowsGetStringRawBuffer
0x18001681a  mov     rdx, rax
0x18001681d  lea     rcx, [rsp+68h+var_40]
0x180016822  call    ?WexpConfigurationIdFromFlightId@FlightIdUtils@@YA?AUWexpConfiguration@1@PEBG@Z; FlightIdUtils::WexpConfigurationIdFromFlightId(ushort const *)
0x180016827  movzx   eax, [rsp+68h+var_40]
0x18001682c  neg     ax
0x18001682f  sbb     eax, eax
0x180016831  neg     eax
0x180016833  inc     eax
0x180016835  mov     [rdi], eax
0x180016837  mov     rcx, [rsp+68h+string]; string
0x18001683c  call    cs:__imp_WindowsDeleteString
0x180016842  xor     eax, eax
0x180016844  jmp     short loc_18001684A
0x180016846  mov     eax, dword ptr [rsp+68h+string]
0x18001684a  mov     rcx, [rsp+68h+var_18]
0x18001684f  xor     rcx, rsp; StackCookie
0x180016852  call    __security_check_cookie
0x180016857  lea     r11, [rsp+68h+var_8]
0x18001685c  mov     rbx, [r11+10h]
0x180016860  mov     rsi, [r11+28h]
0x180016864  mov     rsp, r11
0x180016867  pop     rdi
0x180016868  retn
```
