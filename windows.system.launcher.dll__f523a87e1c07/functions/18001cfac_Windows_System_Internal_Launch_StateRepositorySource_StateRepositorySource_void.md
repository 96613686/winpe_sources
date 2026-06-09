# Windows::System::Internal::Launch::StateRepositorySource::~StateRepositorySource(void)

- ea: `0x18001cfac`
- end: `0x18001d0d6`
- name: `??1StateRepositorySource@Launch@Internal@System@Windows@@UEAA@XZ`
- size: `298`
- prototype: `void __fastcall(Windows::System::Internal::Launch::StateRepositorySource *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001cf70`

## callees

- `0x1800049bc`
- `0x18001d0dc`
- `0x18001d10c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001cfbc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001cfd4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001cfec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d004`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d01c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d034`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d04c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d064`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d07c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d094`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d0bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001cfbc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001cfd4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001cfec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d004`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d01c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d034`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d04c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d064`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d07c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d094`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d0bb`

## pseudocode

```c
void __fastcall Windows::System::Internal::Launch::StateRepositorySource::~StateRepositorySource(HSTRING *this)
{
  WindowsDeleteString(this[25]);
  this[25] = 0;
  WindowsDeleteString(this[24]);
  this[24] = 0;
  WindowsDeleteString(this[23]);
  this[23] = 0;
  WindowsDeleteString(this[22]);
  this[22] = 0;
  WindowsDeleteString(this[21]);
  this[21] = 0;
  WindowsDeleteString(this[20]);
  this[20] = 0;
  WindowsDeleteString(this[19]);
  this[19] = 0;
  WindowsDeleteString(this[18]);
  this[18] = 0;
  WindowsDeleteString(this[17]);
  this[17] = 0;
  WindowsDeleteString(this[16]);
  this[16] = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(this + 15);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(this + 14);
  WindowsDeleteString(this[13]);
  this[13] = 0;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IQuerySource,IObjectWithRegistryKey,IPropertyBag,Windows::System::Internal::Launch::IObjectWithExtensionInfo,Windows::Internal::Shell::FileAssociations::IAssociationQuerySource,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IQuerySource,IObjectWithRegistryKey,IPropertyBag,Windows::System::Internal::Launch::IObjectWithExtensionInfo,Windows::Internal::Shell::FileAssociations::IAssociationQuerySource,Microsoft::WRL::FtmBase>(this);
}

```

## disassembly

```asm
0x18001cfac  push    rbx
0x18001cfae  sub     rsp, 20h
0x18001cfb2  mov     rbx, rcx
0x18001cfb5  mov     rcx, [rcx+0C8h]; string
0x18001cfbc  call    cs:__imp_WindowsDeleteString
0x18001cfc2  mov     qword ptr [rbx+0C8h], 0
0x18001cfcd  mov     rcx, [rbx+0C0h]; string
0x18001cfd4  call    cs:__imp_WindowsDeleteString
0x18001cfda  mov     qword ptr [rbx+0C0h], 0
0x18001cfe5  mov     rcx, [rbx+0B8h]; string
0x18001cfec  call    cs:__imp_WindowsDeleteString
0x18001cff2  mov     qword ptr [rbx+0B8h], 0
0x18001cffd  mov     rcx, [rbx+0B0h]; string
0x18001d004  call    cs:__imp_WindowsDeleteString
0x18001d00a  mov     qword ptr [rbx+0B0h], 0
0x18001d015  mov     rcx, [rbx+0A8h]; string
0x18001d01c  call    cs:__imp_WindowsDeleteString
0x18001d022  mov     qword ptr [rbx+0A8h], 0
0x18001d02d  mov     rcx, [rbx+0A0h]; string
0x18001d034  call    cs:__imp_WindowsDeleteString
0x18001d03a  mov     qword ptr [rbx+0A0h], 0
0x18001d045  mov     rcx, [rbx+98h]; string
0x18001d04c  call    cs:__imp_WindowsDeleteString
0x18001d052  mov     qword ptr [rbx+98h], 0
0x18001d05d  mov     rcx, [rbx+90h]; string
0x18001d064  call    cs:__imp_WindowsDeleteString
0x18001d06a  mov     qword ptr [rbx+90h], 0
0x18001d075  mov     rcx, [rbx+88h]; string
0x18001d07c  call    cs:__imp_WindowsDeleteString
0x18001d082  mov     qword ptr [rbx+88h], 0
0x18001d08d  mov     rcx, [rbx+80h]; string
0x18001d094  call    cs:__imp_WindowsDeleteString
0x18001d09a  lea     rcx, [rbx+78h]
0x18001d09e  mov     qword ptr [rbx+80h], 0
0x18001d0a9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001d0ae  lea     rcx, [rbx+70h]
0x18001d0b2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001d0b7  mov     rcx, [rbx+68h]; string
0x18001d0bb  call    cs:__imp_WindowsDeleteString
0x18001d0c1  mov     rcx, rbx
0x18001d0c4  mov     qword ptr [rbx+68h], 0
0x18001d0cc  add     rsp, 20h
0x18001d0d0  pop     rbx
0x18001d0d1  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIQuerySource@@UIObjectWithRegistryKey@@UIPropertyBag@@UIObjectWithExtensionInfo@Launch@Internal@System@Windows@@UIAssociationQuerySource@FileAssociations@Shell@9Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IQuerySource,IObjectWithRegistryKey,IPropertyBag,Windows::System::Internal::Launch::IObjectWithExtensionInfo,Windows::Internal::Shell::FileAssociations::IAssociationQuerySource,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IQuerySource,IObjectWithRegistryKey,IPropertyBag,Windows::System::Internal::Launch::IObjectWithExtensionInfo,Windows::Internal::Shell::FileAssociations::IAssociationQuerySource,Microsoft::WRL::FtmBase>(void)
```
