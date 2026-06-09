# Windows::Internal::Notifications::AdaptiveNotification::~AdaptiveNotification(void)

- ea: `0x180024c74`
- end: `0x180024d38`
- name: `??1AdaptiveNotification@Notifications@Internal@Windows@@UEAA@XZ`
- size: `196`
- prototype: `void __fastcall(Windows::Internal::Notifications::AdaptiveNotification *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180024d80`

## callees

- `0x180005670`
- `0x18000e2dc`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024c9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024cb1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024cc3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024cd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024ce7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024cf9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024d0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024d1d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024c9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024cb1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024cc3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024cd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024ce7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024cf9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024d0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024d1d`

## pseudocode

```c
void __fastcall Windows::Internal::Notifications::AdaptiveNotification::~AdaptiveNotification(HSTRING *this)
{
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(this + 18);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(this + 17);
  WindowsDeleteString(this[16]);
  this[16] = 0;
  WindowsDeleteString(this[15]);
  this[15] = 0;
  WindowsDeleteString(this[14]);
  this[14] = 0;
  WindowsDeleteString(this[13]);
  this[13] = 0;
  WindowsDeleteString(this[12]);
  this[12] = 0;
  WindowsDeleteString(this[11]);
  this[11] = 0;
  WindowsDeleteString(this[10]);
  this[10] = 0;
  WindowsDeleteString(this[9]);
  this[9] = 0;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Microsoft::WRL::FtmBase,Windows::Internal::Notifications::IWpnToastActivator>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Microsoft::WRL::FtmBase,Windows::Internal::Notifications::IWpnToastActivator>(this);
}

```

## disassembly

```asm
0x180024c74  push    rbx
0x180024c76  sub     rsp, 20h
0x180024c7a  mov     rbx, rcx
0x180024c7d  add     rcx, 90h
0x180024c84  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180024c89  lea     rcx, [rbx+88h]
0x180024c90  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180024c95  mov     rcx, [rbx+80h]; string
0x180024c9c  call    cs:__imp_WindowsDeleteString
0x180024ca2  mov     qword ptr [rbx+80h], 0
0x180024cad  mov     rcx, [rbx+78h]; string
0x180024cb1  call    cs:__imp_WindowsDeleteString
0x180024cb7  mov     qword ptr [rbx+78h], 0
0x180024cbf  mov     rcx, [rbx+70h]; string
0x180024cc3  call    cs:__imp_WindowsDeleteString
0x180024cc9  mov     qword ptr [rbx+70h], 0
0x180024cd1  mov     rcx, [rbx+68h]; string
0x180024cd5  call    cs:__imp_WindowsDeleteString
0x180024cdb  mov     qword ptr [rbx+68h], 0
0x180024ce3  mov     rcx, [rbx+60h]; string
0x180024ce7  call    cs:__imp_WindowsDeleteString
0x180024ced  mov     qword ptr [rbx+60h], 0
0x180024cf5  mov     rcx, [rbx+58h]; string
0x180024cf9  call    cs:__imp_WindowsDeleteString
0x180024cff  mov     qword ptr [rbx+58h], 0
0x180024d07  mov     rcx, [rbx+50h]; string
0x180024d0b  call    cs:__imp_WindowsDeleteString
0x180024d11  mov     qword ptr [rbx+50h], 0
0x180024d19  mov     rcx, [rbx+48h]; string
0x180024d1d  call    cs:__imp_WindowsDeleteString
0x180024d23  mov     rcx, rbx
0x180024d26  mov     qword ptr [rbx+48h], 0
0x180024d2e  add     rsp, 20h
0x180024d32  pop     rbx
0x180024d33  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@VFtmBase@23@UIWpnToastActivator@Notifications@Internal@Windows@@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Microsoft::WRL::FtmBase,Windows::Internal::Notifications::IWpnToastActivator>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Microsoft::WRL::FtmBase,Windows::Internal::Notifications::IWpnToastActivator>(void)
```
