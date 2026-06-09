# Windows::Internal::Notifications::AdaptiveImage::~AdaptiveImage(void)

- ea: `0x180023620`
- end: `0x18002366c`
- name: `??1AdaptiveImage@Notifications@Internal@Windows@@UEAA@XZ`
- size: `76`
- prototype: `void __fastcall(Windows::Internal::Notifications::AdaptiveImage *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180023840`

## callees

- `0x18000e30c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002362d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002363f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023651`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002362d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002363f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023651`

## pseudocode

```c
void __fastcall Windows::Internal::Notifications::AdaptiveImage::~AdaptiveImage(HSTRING *this)
{
  WindowsDeleteString(this[11]);
  this[11] = 0;
  WindowsDeleteString(this[10]);
  this[10] = 0;
  WindowsDeleteString(this[9]);
  this[9] = 0;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Microsoft::WRL::FtmBase,Windows::Internal::Notifications::IAdaptiveImage>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Microsoft::WRL::FtmBase,Windows::Internal::Notifications::IAdaptiveImage>(this);
}

```

## disassembly

```asm
0x180023620  push    rbx
0x180023622  sub     rsp, 20h
0x180023626  mov     rbx, rcx
0x180023629  mov     rcx, [rcx+58h]; string
0x18002362d  call    cs:__imp_WindowsDeleteString
0x180023633  mov     qword ptr [rbx+58h], 0
0x18002363b  mov     rcx, [rbx+50h]; string
0x18002363f  call    cs:__imp_WindowsDeleteString
0x180023645  mov     qword ptr [rbx+50h], 0
0x18002364d  mov     rcx, [rbx+48h]; string
0x180023651  call    cs:__imp_WindowsDeleteString
0x180023657  mov     rcx, rbx
0x18002365a  mov     qword ptr [rbx+48h], 0
0x180023662  add     rsp, 20h
0x180023666  pop     rbx
0x180023667  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@VFtmBase@23@UIAdaptiveImage@Notifications@Internal@Windows@@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Microsoft::WRL::FtmBase,Windows::Internal::Notifications::IAdaptiveImage>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Microsoft::WRL::FtmBase,Windows::Internal::Notifications::IAdaptiveImage>(void)
```
