# ClientEndpoint::GetPayloadString(void)

- ea: `0x18002d8b8`
- end: `0x18002d97d`
- name: `?GetPayloadString@ClientEndpoint@@QEBA?AVHString@Wrappers@WRL@Microsoft@@XZ`
- size: `197`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018684`

## callees

- `0x180005f50`
- `0x1800101fc`
- `0x1800133c4`
- `0x18002d8b8`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002d926`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002d926`

## string_xrefs

- `0x18002d8f7`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientendpoint.cpp`
- `0x18002d94d`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientendpoint.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall ClientEndpoint::GetPayloadString(__int64 a1, _QWORD *a2)
{
  int v3; // eax
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, _QWORD *); // rbx
  int v6; // eax
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 v9; // [rsp+40h] [rbp+8h] BYREF
  _QWORD *v10; // [rsp+48h] [rbp+10h]

  v10 = a2;
  v9 = 0;
  v3 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Data::Json::IJsonValue>(
         (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))(a1 + 72),
         (__int64)&v9);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xBB,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientendpoint.cpp",
      (const char *)(unsigned int)v3,
      0);
  *a2 = 0;
  v4 = v9;
  v5 = *(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v9 + 56LL);
  WindowsDeleteString(0);
  *a2 = 0;
  v6 = v5(v4, a2);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xBF,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientendpoint.cpp",
      (const char *)(unsigned int)v6,
      1);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v9);
  return a2;
}

```

## disassembly

```asm
0x18002d8b8  mov     rax, rsp
0x18002d8bb  mov     [rax+18h], rbx
0x18002d8bf  mov     [rax+20h], rsi
0x18002d8c3  mov     [rax+10h], rdx
0x18002d8c7  push    rdi
0x18002d8c8  sub     rsp, 30h
0x18002d8cc  mov     rsi, rdx
0x18002d8cf  mov     dword ptr [rax-18h], 0
0x18002d8d6  mov     qword ptr [rax+8], 0
0x18002d8de  add     rcx, 48h ; 'H'
0x18002d8e2  lea     rdx, [rax+8]
0x18002d8e6  call    ??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)
0x18002d8eb  mov     rcx, [rsp+38h]; this
0x18002d8f0  test    eax, eax
0x18002d8f2  jns     short loc_18002D909
0x18002d8f4  mov     r9d, eax; char *
0x18002d8f7  lea     r8, aOnecoreBaseFli; "onecore\\base\\flighting\\onesettings\\"...
0x18002d8fe  mov     edx, 0BBh; void *
0x18002d903  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002d909  mov     qword ptr [rsi], 0
0x18002d910  mov     [rsp+38h+var_18], 1; int
0x18002d918  mov     rdi, [rsp+38h+arg_0]
0x18002d91d  mov     rax, [rdi]
0x18002d920  mov     rbx, [rax+38h]
0x18002d924  xor     ecx, ecx; string
0x18002d926  call    cs:__imp_WindowsDeleteString
0x18002d92c  mov     qword ptr [rsi], 0
0x18002d933  mov     rdx, rsi
0x18002d936  mov     rcx, rdi
0x18002d939  mov     rax, rbx
0x18002d93c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d941  mov     rcx, [rsp+38h]; this
0x18002d946  test    eax, eax
0x18002d948  jns     short loc_18002D95F
0x18002d94a  mov     r9d, eax; char *
0x18002d94d  lea     r8, aOnecoreBaseFli; "onecore\\base\\flighting\\onesettings\\"...
0x18002d954  mov     edx, 0BFh; void *
0x18002d959  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002d95f  lea     rcx, [rsp+38h+arg_0]
0x18002d964  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002d969  mov     rax, rsi
0x18002d96c  mov     rbx, [rsp+38h+arg_10]
0x18002d971  mov     rsi, [rsp+38h+arg_18]
0x18002d976  add     rsp, 30h
0x18002d97a  pop     rdi
0x18002d97b  retn
```
