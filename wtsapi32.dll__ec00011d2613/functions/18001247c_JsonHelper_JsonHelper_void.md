# JsonHelper::~JsonHelper(void)

- ea: `0x18001247c`
- end: `0x180012517`
- name: `??1JsonHelper@@UEAA@XZ`
- size: `155`
- prototype: `void __fastcall(JsonHelper *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800125d0`

## callees

- `0x18001247c`
- `0x180013880`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800124c9`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800124c9`

## pseudocode

```c
void __fastcall JsonHelper::~JsonHelper(JsonHelper *this)
{
  *(_QWORD *)this = &JsonHelper::`vftable';
  *((_QWORD *)this + 1) = &JsonHelper::`vftable'{for `INonDelegatingUnknown'};
  *((_QWORD *)this + 2) = &JsonHelper::`vftable'{for `CTSObject'};
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease((__int64 *)this + 7);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease((__int64 *)this + 9);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease((__int64 *)this + 8);
  if ( *((_BYTE *)this + 80) )
    RoUninitialize();
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease((__int64 *)this + 9);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease((__int64 *)this + 8);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease((__int64 *)this + 7);
  *((_QWORD *)this + 1) = &CTSUnknown::`vftable'{for `INonDelegatingUnknown'};
  *((_QWORD *)this + 2) = &CTSObject::`vftable';
  *((_DWORD *)this + 9) |= 8u;
  *(_QWORD *)this = &IJsonHelper::`vftable';
}

```

## disassembly

```asm
0x18001247c  push    rbx
0x18001247e  push    rbp
0x18001247f  push    rsi
0x180012480  push    rdi
0x180012481  sub     rsp, 28h
0x180012485  lea     rax, ??_7JsonHelper@@6B@; const JsonHelper::`vftable'
0x18001248c  mov     rbx, rcx
0x18001248f  mov     [rcx], rax
0x180012492  lea     rax, ??_7JsonHelper@@6BINonDelegatingUnknown@@@; const JsonHelper::`vftable'{for `INonDelegatingUnknown'}
0x180012499  mov     [rcx+8], rax
0x18001249d  lea     rax, ??_7JsonHelper@@6BCTSObject@@@; const JsonHelper::`vftable'{for `CTSObject'}
0x1800124a4  mov     [rcx+10h], rax
0x1800124a8  add     rcx, 38h ; '8'
0x1800124ac  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x1800124b1  lea     rcx, [rbx+48h]
0x1800124b5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x1800124ba  lea     rcx, [rbx+40h]
0x1800124be  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x1800124c3  cmp     byte ptr [rbx+50h], 0
0x1800124c7  jz      short loc_1800124CF
0x1800124c9  call    cs:__imp_RoUninitialize
0x1800124cf  lea     rcx, [rbx+48h]
0x1800124d3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x1800124d8  lea     rcx, [rbx+40h]
0x1800124dc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x1800124e1  lea     rcx, [rbx+38h]
0x1800124e5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x1800124ea  lea     rax, ??_7CTSUnknown@@6BINonDelegatingUnknown@@@; const CTSUnknown::`vftable'{for `INonDelegatingUnknown'}
0x1800124f1  mov     [rbx+8], rax
0x1800124f5  lea     rax, ??_7CTSObject@@6B@; const CTSObject::`vftable'
0x1800124fc  mov     [rbx+10h], rax
0x180012500  lea     rax, ??_7IJsonHelper@@6B@; const IJsonHelper::`vftable'
0x180012507  or      dword ptr [rbx+24h], 8
0x18001250b  mov     [rbx], rax
0x18001250e  add     rsp, 28h
0x180012512  pop     rdi
0x180012513  pop     rsi
0x180012514  pop     rbp
0x180012515  pop     rbx
0x180012516  retn
```
