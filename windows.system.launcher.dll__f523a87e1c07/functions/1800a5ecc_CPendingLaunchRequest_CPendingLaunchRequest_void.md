# CPendingLaunchRequest::~CPendingLaunchRequest(void)

- ea: `0x1800a5ecc`
- end: `0x1800a5fae`
- name: `??1CPendingLaunchRequest@@UEAA@XZ`
- size: `226`
- prototype: `void __fastcall(CPendingLaunchRequest *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800a6640`

## callees

- `0x1800049bc`
- `0x1800a5d98`
- `0x1800a5fb4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a5edc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a5f0c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a5f24`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a5f3c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a5f54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a5f6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a5f81`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a5edc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a5f0c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a5f24`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a5f3c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a5f54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a5f6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a5f81`

## pseudocode

```c
void __fastcall CPendingLaunchRequest::~CPendingLaunchRequest(HSTRING *this)
{
  WindowsDeleteString(this[29]);
  this[29] = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(this + 28);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(this + 27);
  WindowsDeleteString(this[26]);
  this[26] = 0;
  WindowsDeleteString(this[19]);
  this[19] = 0;
  WindowsDeleteString(this[18]);
  this[18] = 0;
  WindowsDeleteString(this[17]);
  this[17] = 0;
  WindowsDeleteString(this[16]);
  this[16] = 0;
  WindowsDeleteString(this[15]);
  this[15] = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(this + 14);
  CachedLaunchParameters::~CachedLaunchParameters((CachedLaunchParameters *)(this + 11));
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::System::Private::IPendingLaunch,Windows::System::Private::IPendingLaunch2,Windows::System::Private::IPendingProtocolLaunch,Windows::System::Private::IPendingFileLaunch,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::System::Private::IPendingLaunch,Windows::System::Private::IPendingLaunch2,Windows::System::Private::IPendingProtocolLaunch,Windows::System::Private::IPendingFileLaunch,Microsoft::WRL::FtmBase>(this);
}

```

## disassembly

```asm
0x1800a5ecc  push    rbx
0x1800a5ece  sub     rsp, 20h
0x1800a5ed2  mov     rbx, rcx
0x1800a5ed5  mov     rcx, [rcx+0E8h]; string
0x1800a5edc  call    cs:__imp_WindowsDeleteString
0x1800a5ee2  lea     rcx, [rbx+0E0h]
0x1800a5ee9  mov     qword ptr [rbx+0E8h], 0
0x1800a5ef4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a5ef9  lea     rcx, [rbx+0D8h]
0x1800a5f00  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a5f05  mov     rcx, [rbx+0D0h]; string
0x1800a5f0c  call    cs:__imp_WindowsDeleteString
0x1800a5f12  mov     qword ptr [rbx+0D0h], 0
0x1800a5f1d  mov     rcx, [rbx+98h]; string
0x1800a5f24  call    cs:__imp_WindowsDeleteString
0x1800a5f2a  mov     qword ptr [rbx+98h], 0
0x1800a5f35  mov     rcx, [rbx+90h]; string
0x1800a5f3c  call    cs:__imp_WindowsDeleteString
0x1800a5f42  mov     qword ptr [rbx+90h], 0
0x1800a5f4d  mov     rcx, [rbx+88h]; string
0x1800a5f54  call    cs:__imp_WindowsDeleteString
0x1800a5f5a  mov     qword ptr [rbx+88h], 0
0x1800a5f65  mov     rcx, [rbx+80h]; string
0x1800a5f6c  call    cs:__imp_WindowsDeleteString
0x1800a5f72  mov     qword ptr [rbx+80h], 0
0x1800a5f7d  mov     rcx, [rbx+78h]; string
0x1800a5f81  call    cs:__imp_WindowsDeleteString
0x1800a5f87  lea     rcx, [rbx+70h]
0x1800a5f8b  mov     qword ptr [rbx+78h], 0
0x1800a5f93  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a5f98  lea     rcx, [rbx+58h]; this
0x1800a5f9c  call    ??1CachedLaunchParameters@@QEAA@XZ; CachedLaunchParameters::~CachedLaunchParameters(void)
0x1800a5fa1  mov     rcx, rbx
0x1800a5fa4  add     rsp, 20h
0x1800a5fa8  pop     rbx
0x1800a5fa9  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIPendingLaunch@Private@System@Windows@@UIPendingLaunch2@567@UIPendingProtocolLaunch@567@UIPendingFileLaunch@567@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::System::Private::IPendingLaunch,Windows::System::Private::IPendingLaunch2,Windows::System::Private::IPendingProtocolLaunch,Windows::System::Private::IPendingFileLaunch,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::System::Private::IPendingLaunch,Windows::System::Private::IPendingLaunch2,Windows::System::Private::IPendingProtocolLaunch,Windows::System::Private::IPendingFileLaunch,Microsoft::WRL::FtmBase>(void)
```
