# LauncherCachedUriLaunch::~LauncherCachedUriLaunch(void)

- ea: `0x1800b20a0`
- end: `0x1800b2176`
- name: `??1LauncherCachedUriLaunch@@UEAA@XZ`
- size: `214`
- prototype: `void __fastcall(LauncherCachedUriLaunch *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800b37f0`

## callees

- `0x1800049bc`
- `0x1800a5d98`
- `0x1800a5fb4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b20b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b20e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b20f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b2110`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b2128`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b2140`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b2158`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b20b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b20e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b20f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b2110`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b2128`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b2140`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b2158`

## pseudocode

```c
void __fastcall LauncherCachedUriLaunch::~LauncherCachedUriLaunch(HSTRING *this)
{
  WindowsDeleteString(this[29]);
  this[29] = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(this + 28);
  CachedLaunchParameters::~CachedLaunchParameters((CachedLaunchParameters *)(this + 24));
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
  WindowsDeleteString(this[16]);
  this[16] = 0;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::System::Private::IPendingLaunch,Windows::System::Private::IPendingLaunch2,Windows::System::Private::IPendingProtocolLaunch,Windows::System::Private::IPendingFileLaunch,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::System::Private::IPendingLaunch,Windows::System::Private::IPendingLaunch2,Windows::System::Private::IPendingProtocolLaunch,Windows::System::Private::IPendingFileLaunch,Microsoft::WRL::FtmBase>(this);
}

```

## disassembly

```asm
0x1800b20a0  push    rbx
0x1800b20a2  sub     rsp, 20h
0x1800b20a6  mov     rbx, rcx
0x1800b20a9  mov     rcx, [rcx+0E8h]; string
0x1800b20b0  call    cs:__imp_WindowsDeleteString
0x1800b20b6  lea     rcx, [rbx+0E0h]
0x1800b20bd  mov     qword ptr [rbx+0E8h], 0
0x1800b20c8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b20cd  lea     rcx, [rbx+0C0h]; this
0x1800b20d4  call    ??1CachedLaunchParameters@@QEAA@XZ; CachedLaunchParameters::~CachedLaunchParameters(void)
0x1800b20d9  mov     rcx, [rbx+0B8h]; string
0x1800b20e0  call    cs:__imp_WindowsDeleteString
0x1800b20e6  mov     qword ptr [rbx+0B8h], 0
0x1800b20f1  mov     rcx, [rbx+0B0h]; string
0x1800b20f8  call    cs:__imp_WindowsDeleteString
0x1800b20fe  mov     qword ptr [rbx+0B0h], 0
0x1800b2109  mov     rcx, [rbx+0A8h]; string
0x1800b2110  call    cs:__imp_WindowsDeleteString
0x1800b2116  mov     qword ptr [rbx+0A8h], 0
0x1800b2121  mov     rcx, [rbx+0A0h]; string
0x1800b2128  call    cs:__imp_WindowsDeleteString
0x1800b212e  mov     qword ptr [rbx+0A0h], 0
0x1800b2139  mov     rcx, [rbx+98h]; string
0x1800b2140  call    cs:__imp_WindowsDeleteString
0x1800b2146  mov     qword ptr [rbx+98h], 0
0x1800b2151  mov     rcx, [rbx+80h]; string
0x1800b2158  call    cs:__imp_WindowsDeleteString
0x1800b215e  mov     rcx, rbx
0x1800b2161  mov     qword ptr [rbx+80h], 0
0x1800b216c  add     rsp, 20h
0x1800b2170  pop     rbx
0x1800b2171  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIPendingLaunch@Private@System@Windows@@UIPendingLaunch2@567@UIPendingProtocolLaunch@567@UIPendingFileLaunch@567@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::System::Private::IPendingLaunch,Windows::System::Private::IPendingLaunch2,Windows::System::Private::IPendingProtocolLaunch,Windows::System::Private::IPendingFileLaunch,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::System::Private::IPendingLaunch,Windows::System::Private::IPendingLaunch2,Windows::System::Private::IPendingProtocolLaunch,Windows::System::Private::IPendingFileLaunch,Microsoft::WRL::FtmBase>(void)
```
