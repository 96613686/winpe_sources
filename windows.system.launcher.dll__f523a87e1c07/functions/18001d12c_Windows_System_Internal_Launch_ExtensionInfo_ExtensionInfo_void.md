# Windows::System::Internal::Launch::ExtensionInfo::~ExtensionInfo(void)

- ea: `0x18001d12c`
- end: `0x18001d255`
- name: `??1ExtensionInfo@Launch@Internal@System@Windows@@UEAA@XZ`
- size: `297`
- prototype: `void __fastcall(Windows::System::Internal::Launch::ExtensionInfo *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800a6680`

## callees

- `0x1800049bc`
- `0x18001d2cc`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d14c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d162`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d176`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d18a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d19e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d1b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d1c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d1d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d1e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d1f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d201`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d20f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d21d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d22b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d239`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d14c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d162`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d176`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d18a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d19e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d1b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d1c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d1d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d1e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d1f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d201`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d20f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d21d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d22b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d239`

## pseudocode

```c
void __fastcall Windows::System::Internal::Launch::ExtensionInfo::~ExtensionInfo(HSTRING *this)
{
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(this + 27);
  WindowsDeleteString(this[25]);
  this[25] = 0;
  WindowsDeleteString(this[23]);
  this[23] = 0;
  WindowsDeleteString(this[22]);
  this[22] = 0;
  WindowsDeleteString(this[21]);
  this[21] = 0;
  WindowsDeleteString(this[20]);
  this[20] = 0;
  WindowsDeleteString(this[18]);
  this[18] = 0;
  WindowsDeleteString(this[17]);
  this[17] = 0;
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
  WindowsDeleteString(this[8]);
  this[8] = 0;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::System::IRemoteLauncherOptions,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::System::IRemoteLauncherOptions,Microsoft::WRL::FtmBase>(this);
}

```

## disassembly

```asm
0x18001d12c  mov     [rsp+arg_0], rbx
0x18001d131  push    rdi
0x18001d132  sub     rsp, 20h
0x18001d136  mov     rbx, rcx
0x18001d139  add     rcx, 0D8h
0x18001d140  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001d145  mov     rcx, [rbx+0C8h]; string
0x18001d14c  call    cs:__imp_WindowsDeleteString
0x18001d152  xor     edi, edi
0x18001d154  mov     [rbx+0C8h], rdi
0x18001d15b  mov     rcx, [rbx+0B8h]; string
0x18001d162  call    cs:__imp_WindowsDeleteString
0x18001d168  mov     [rbx+0B8h], rdi
0x18001d16f  mov     rcx, [rbx+0B0h]; string
0x18001d176  call    cs:__imp_WindowsDeleteString
0x18001d17c  mov     [rbx+0B0h], rdi
0x18001d183  mov     rcx, [rbx+0A8h]; string
0x18001d18a  call    cs:__imp_WindowsDeleteString
0x18001d190  mov     [rbx+0A8h], rdi
0x18001d197  mov     rcx, [rbx+0A0h]; string
0x18001d19e  call    cs:__imp_WindowsDeleteString
0x18001d1a4  mov     [rbx+0A0h], rdi
0x18001d1ab  mov     rcx, [rbx+90h]; string
0x18001d1b2  call    cs:__imp_WindowsDeleteString
0x18001d1b8  mov     [rbx+90h], rdi
0x18001d1bf  mov     rcx, [rbx+88h]; string
0x18001d1c6  call    cs:__imp_WindowsDeleteString
0x18001d1cc  mov     [rbx+88h], rdi
0x18001d1d3  mov     rcx, [rbx+78h]; string
0x18001d1d7  call    cs:__imp_WindowsDeleteString
0x18001d1dd  mov     [rbx+78h], rdi
0x18001d1e1  mov     rcx, [rbx+70h]; string
0x18001d1e5  call    cs:__imp_WindowsDeleteString
0x18001d1eb  mov     [rbx+70h], rdi
0x18001d1ef  mov     rcx, [rbx+68h]; string
0x18001d1f3  call    cs:__imp_WindowsDeleteString
0x18001d1f9  mov     [rbx+68h], rdi
0x18001d1fd  mov     rcx, [rbx+60h]; string
0x18001d201  call    cs:__imp_WindowsDeleteString
0x18001d207  mov     [rbx+60h], rdi
0x18001d20b  mov     rcx, [rbx+58h]; string
0x18001d20f  call    cs:__imp_WindowsDeleteString
0x18001d215  mov     [rbx+58h], rdi
0x18001d219  mov     rcx, [rbx+50h]; string
0x18001d21d  call    cs:__imp_WindowsDeleteString
0x18001d223  mov     [rbx+50h], rdi
0x18001d227  mov     rcx, [rbx+48h]; string
0x18001d22b  call    cs:__imp_WindowsDeleteString
0x18001d231  mov     [rbx+48h], rdi
0x18001d235  mov     rcx, [rbx+40h]; string
0x18001d239  call    cs:__imp_WindowsDeleteString
0x18001d23f  mov     rcx, rbx
0x18001d242  mov     [rbx+40h], rdi
0x18001d246  mov     rbx, [rsp+28h+arg_0]
0x18001d24b  add     rsp, 20h
0x18001d24f  pop     rdi
0x18001d250  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIRemoteLauncherOptions@System@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::System::IRemoteLauncherOptions,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::System::IRemoteLauncherOptions,Microsoft::WRL::FtmBase>(void)
```
