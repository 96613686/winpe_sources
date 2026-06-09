# ComClassRegistrationEntryProperties::~ComClassRegistrationEntryProperties(void)

- ea: `0x18000e148`
- end: `0x18000e335`
- name: `??1ComClassRegistrationEntryProperties@@QEAA@XZ`
- size: `493`
- prototype: `void __fastcall(ComClassRegistrationEntryProperties *__hidden this)`
- caller_count: `9`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000e0bc`
- `0x18008d028`
- `0x18008df18`
- `0x1800a7ff0`
- `0x1800a83ac`
- `0x1800d70a8`
- `0x1800dabe0`
- `0x1800db410`
- `0x1800e30e0`

## callees

- `0x18000d494`
- `0x18000d4c4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e15c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e17e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e19e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e1b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e1c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e1da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e1ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e202`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e216`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e22a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e23e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e252`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e272`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e292`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e2a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e2ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e2ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e2df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e2f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e304`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e312`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e320`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e15c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e17e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e19e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e1b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e1c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e1da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e1ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e202`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e216`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e22a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e23e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e252`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e272`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e292`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e2a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e2ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e2ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e2df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e2f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e304`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e312`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e320`

## pseudocode

```c
void __fastcall ComClassRegistrationEntryProperties::~ComClassRegistrationEntryProperties(HSTRING *this)
{
  WindowsDeleteString(this[67]);
  this[67] = 0;
  SecurityDescriptor::Release((SecurityDescriptor *)(this + 63));
  WindowsDeleteString(this[57]);
  this[57] = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(this + 52);
  WindowsDeleteString(this[50]);
  this[50] = 0;
  WindowsDeleteString(this[48]);
  this[48] = 0;
  WindowsDeleteString(this[46]);
  this[46] = 0;
  WindowsDeleteString(this[44]);
  this[44] = 0;
  WindowsDeleteString(this[41]);
  this[41] = 0;
  WindowsDeleteString(this[39]);
  this[39] = 0;
  WindowsDeleteString(this[37]);
  this[37] = 0;
  WindowsDeleteString(this[35]);
  this[35] = 0;
  WindowsDeleteString(this[31]);
  this[31] = 0;
  WindowsDeleteString(this[29]);
  this[29] = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(this + 27);
  WindowsDeleteString(this[26]);
  this[26] = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(this + 24);
  WindowsDeleteString(this[23]);
  this[23] = 0;
  WindowsDeleteString(this[21]);
  this[21] = 0;
  WindowsDeleteString(this[19]);
  this[19] = 0;
  WindowsDeleteString(this[17]);
  this[17] = 0;
  WindowsDeleteString(this[15]);
  this[15] = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(this + 10);
  WindowsDeleteString(this[8]);
  this[8] = 0;
  WindowsDeleteString(this[6]);
  this[6] = 0;
  WindowsDeleteString(this[4]);
  this[4] = 0;
  WindowsDeleteString(this[2]);
  this[2] = 0;
}

```

## disassembly

```asm
0x18000e148  mov     [rsp+arg_0], rbx
0x18000e14d  push    rdi
0x18000e14e  sub     rsp, 20h
0x18000e152  mov     rbx, rcx
0x18000e155  mov     rcx, [rcx+218h]; string
0x18000e15c  call    cs:__imp_WindowsDeleteString
0x18000e162  xor     edi, edi
0x18000e164  lea     rcx, [rbx+1F8h]; this
0x18000e16b  mov     [rbx+218h], rdi
0x18000e172  call    ?Release@SecurityDescriptor@@QEAAXXZ; SecurityDescriptor::Release(void)
0x18000e177  mov     rcx, [rbx+1C8h]; string
0x18000e17e  call    cs:__imp_WindowsDeleteString
0x18000e184  lea     rcx, [rbx+1A0h]
0x18000e18b  mov     [rbx+1C8h], rdi
0x18000e192  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000e197  mov     rcx, [rbx+190h]; string
0x18000e19e  call    cs:__imp_WindowsDeleteString
0x18000e1a4  mov     [rbx+190h], rdi
0x18000e1ab  mov     rcx, [rbx+180h]; string
0x18000e1b2  call    cs:__imp_WindowsDeleteString
0x18000e1b8  mov     [rbx+180h], rdi
0x18000e1bf  mov     rcx, [rbx+170h]; string
0x18000e1c6  call    cs:__imp_WindowsDeleteString
0x18000e1cc  mov     [rbx+170h], rdi
0x18000e1d3  mov     rcx, [rbx+160h]; string
0x18000e1da  call    cs:__imp_WindowsDeleteString
0x18000e1e0  mov     [rbx+160h], rdi
0x18000e1e7  mov     rcx, [rbx+148h]; string
0x18000e1ee  call    cs:__imp_WindowsDeleteString
0x18000e1f4  mov     [rbx+148h], rdi
0x18000e1fb  mov     rcx, [rbx+138h]; string
0x18000e202  call    cs:__imp_WindowsDeleteString
0x18000e208  mov     [rbx+138h], rdi
0x18000e20f  mov     rcx, [rbx+128h]; string
0x18000e216  call    cs:__imp_WindowsDeleteString
0x18000e21c  mov     [rbx+128h], rdi
0x18000e223  mov     rcx, [rbx+118h]; string
0x18000e22a  call    cs:__imp_WindowsDeleteString
0x18000e230  mov     [rbx+118h], rdi
0x18000e237  mov     rcx, [rbx+0F8h]; string
0x18000e23e  call    cs:__imp_WindowsDeleteString
0x18000e244  mov     [rbx+0F8h], rdi
0x18000e24b  mov     rcx, [rbx+0E8h]; string
0x18000e252  call    cs:__imp_WindowsDeleteString
0x18000e258  lea     rcx, [rbx+0D8h]
0x18000e25f  mov     [rbx+0E8h], rdi
0x18000e266  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000e26b  mov     rcx, [rbx+0D0h]; string
0x18000e272  call    cs:__imp_WindowsDeleteString
0x18000e278  lea     rcx, [rbx+0C0h]
0x18000e27f  mov     [rbx+0D0h], rdi
0x18000e286  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000e28b  mov     rcx, [rbx+0B8h]; string
0x18000e292  call    cs:__imp_WindowsDeleteString
0x18000e298  mov     [rbx+0B8h], rdi
0x18000e29f  mov     rcx, [rbx+0A8h]; string
0x18000e2a6  call    cs:__imp_WindowsDeleteString
0x18000e2ac  mov     [rbx+0A8h], rdi
0x18000e2b3  mov     rcx, [rbx+98h]; string
0x18000e2ba  call    cs:__imp_WindowsDeleteString
0x18000e2c0  mov     [rbx+98h], rdi
0x18000e2c7  mov     rcx, [rbx+88h]; string
0x18000e2ce  call    cs:__imp_WindowsDeleteString
0x18000e2d4  mov     [rbx+88h], rdi
0x18000e2db  mov     rcx, [rbx+78h]; string
0x18000e2df  call    cs:__imp_WindowsDeleteString
0x18000e2e5  lea     rcx, [rbx+50h]
0x18000e2e9  mov     [rbx+78h], rdi
0x18000e2ed  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000e2f2  mov     rcx, [rbx+40h]; string
0x18000e2f6  call    cs:__imp_WindowsDeleteString
0x18000e2fc  mov     [rbx+40h], rdi
0x18000e300  mov     rcx, [rbx+30h]; string
0x18000e304  call    cs:__imp_WindowsDeleteString
0x18000e30a  mov     [rbx+30h], rdi
0x18000e30e  mov     rcx, [rbx+20h]; string
0x18000e312  call    cs:__imp_WindowsDeleteString
0x18000e318  mov     [rbx+20h], rdi
0x18000e31c  mov     rcx, [rbx+10h]; string
0x18000e320  call    cs:__imp_WindowsDeleteString
0x18000e326  mov     [rbx+10h], rdi
0x18000e32a  mov     rbx, [rsp+28h+arg_0]
0x18000e32f  add     rsp, 20h
0x18000e333  pop     rdi
0x18000e334  retn
```
