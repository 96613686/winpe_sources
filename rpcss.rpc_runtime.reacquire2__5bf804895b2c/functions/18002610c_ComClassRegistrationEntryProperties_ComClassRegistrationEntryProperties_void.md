# ComClassRegistrationEntryProperties::~ComClassRegistrationEntryProperties(void)

- ea: `0x18002610c`
- end: `0x18002637e`
- name: `??1ComClassRegistrationEntryProperties@@QEAA@XZ`
- size: `626`
- prototype: `void __fastcall(ComClassRegistrationEntryProperties *__hidden this)`
- caller_count: `9`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002606c`
- `0x1800941bc`
- `0x18009515c`
- `0x1800ad060`
- `0x1800ad46c`
- `0x1800ddce4`
- `0x1800e1970`
- `0x1800e21e0`
- `0x1800ea530`

## callees

- `0x1800274d4`
- `0x18002750c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026120`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026148`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002616e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026188`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800261a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800261bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800261d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800261f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002620a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026224`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002623e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026258`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002627e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800262a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800262be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800262d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800262f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026309`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026326`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002633a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002634e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026362`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026120`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026148`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002616e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026188`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800261a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800261bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800261d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800261f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002620a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026224`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002623e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026258`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002627e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800262a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800262be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800262d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800262f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026309`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026326`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002633a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002634e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026362`

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
0x18002610c  mov     [rsp+arg_0], rbx
0x180026111  push    rdi
0x180026112  sub     rsp, 20h
0x180026116  mov     rbx, rcx
0x180026119  mov     rcx, [rcx+218h]; string
0x180026120  call    cs:__imp_WindowsDeleteString
0x180026127  nop     dword ptr [rax+rax+00h]
0x18002612c  xor     edi, edi
0x18002612e  lea     rcx, [rbx+1F8h]; this
0x180026135  mov     [rbx+218h], rdi
0x18002613c  call    ?Release@SecurityDescriptor@@QEAAXXZ; SecurityDescriptor::Release(void)
0x180026141  mov     rcx, [rbx+1C8h]; string
0x180026148  call    cs:__imp_WindowsDeleteString
0x18002614f  nop     dword ptr [rax+rax+00h]
0x180026154  lea     rcx, [rbx+1A0h]
0x18002615b  mov     [rbx+1C8h], rdi
0x180026162  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180026167  mov     rcx, [rbx+190h]; string
0x18002616e  call    cs:__imp_WindowsDeleteString
0x180026175  nop     dword ptr [rax+rax+00h]
0x18002617a  mov     [rbx+190h], rdi
0x180026181  mov     rcx, [rbx+180h]; string
0x180026188  call    cs:__imp_WindowsDeleteString
0x18002618f  nop     dword ptr [rax+rax+00h]
0x180026194  mov     [rbx+180h], rdi
0x18002619b  mov     rcx, [rbx+170h]; string
0x1800261a2  call    cs:__imp_WindowsDeleteString
0x1800261a9  nop     dword ptr [rax+rax+00h]
0x1800261ae  mov     [rbx+170h], rdi
0x1800261b5  mov     rcx, [rbx+160h]; string
0x1800261bc  call    cs:__imp_WindowsDeleteString
0x1800261c3  nop     dword ptr [rax+rax+00h]
0x1800261c8  mov     [rbx+160h], rdi
0x1800261cf  mov     rcx, [rbx+148h]; string
0x1800261d6  call    cs:__imp_WindowsDeleteString
0x1800261dd  nop     dword ptr [rax+rax+00h]
0x1800261e2  mov     [rbx+148h], rdi
0x1800261e9  mov     rcx, [rbx+138h]; string
0x1800261f0  call    cs:__imp_WindowsDeleteString
0x1800261f7  nop     dword ptr [rax+rax+00h]
0x1800261fc  mov     [rbx+138h], rdi
0x180026203  mov     rcx, [rbx+128h]; string
0x18002620a  call    cs:__imp_WindowsDeleteString
0x180026211  nop     dword ptr [rax+rax+00h]
0x180026216  mov     [rbx+128h], rdi
0x18002621d  mov     rcx, [rbx+118h]; string
0x180026224  call    cs:__imp_WindowsDeleteString
0x18002622b  nop     dword ptr [rax+rax+00h]
0x180026230  mov     [rbx+118h], rdi
0x180026237  mov     rcx, [rbx+0F8h]; string
0x18002623e  call    cs:__imp_WindowsDeleteString
0x180026245  nop     dword ptr [rax+rax+00h]
0x18002624a  mov     [rbx+0F8h], rdi
0x180026251  mov     rcx, [rbx+0E8h]; string
0x180026258  call    cs:__imp_WindowsDeleteString
0x18002625f  nop     dword ptr [rax+rax+00h]
0x180026264  lea     rcx, [rbx+0D8h]
0x18002626b  mov     [rbx+0E8h], rdi
0x180026272  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180026277  mov     rcx, [rbx+0D0h]; string
0x18002627e  call    cs:__imp_WindowsDeleteString
0x180026285  nop     dword ptr [rax+rax+00h]
0x18002628a  lea     rcx, [rbx+0C0h]
0x180026291  mov     [rbx+0D0h], rdi
0x180026298  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002629d  mov     rcx, [rbx+0B8h]; string
0x1800262a4  call    cs:__imp_WindowsDeleteString
0x1800262ab  nop     dword ptr [rax+rax+00h]
0x1800262b0  mov     [rbx+0B8h], rdi
0x1800262b7  mov     rcx, [rbx+0A8h]; string
0x1800262be  call    cs:__imp_WindowsDeleteString
0x1800262c5  nop     dword ptr [rax+rax+00h]
0x1800262ca  mov     [rbx+0A8h], rdi
0x1800262d1  mov     rcx, [rbx+98h]; string
0x1800262d8  call    cs:__imp_WindowsDeleteString
0x1800262df  nop     dword ptr [rax+rax+00h]
0x1800262e4  mov     [rbx+98h], rdi
0x1800262eb  mov     rcx, [rbx+88h]; string
0x1800262f2  call    cs:__imp_WindowsDeleteString
0x1800262f9  nop     dword ptr [rax+rax+00h]
0x1800262fe  mov     [rbx+88h], rdi
0x180026305  mov     rcx, [rbx+78h]; string
0x180026309  call    cs:__imp_WindowsDeleteString
0x180026310  nop     dword ptr [rax+rax+00h]
0x180026315  lea     rcx, [rbx+50h]
0x180026319  mov     [rbx+78h], rdi
0x18002631d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180026322  mov     rcx, [rbx+40h]; string
0x180026326  call    cs:__imp_WindowsDeleteString
0x18002632d  nop     dword ptr [rax+rax+00h]
0x180026332  mov     [rbx+40h], rdi
0x180026336  mov     rcx, [rbx+30h]; string
0x18002633a  call    cs:__imp_WindowsDeleteString
0x180026341  nop     dword ptr [rax+rax+00h]
0x180026346  mov     [rbx+30h], rdi
0x18002634a  mov     rcx, [rbx+20h]; string
0x18002634e  call    cs:__imp_WindowsDeleteString
0x180026355  nop     dword ptr [rax+rax+00h]
0x18002635a  mov     [rbx+20h], rdi
0x18002635e  mov     rcx, [rbx+10h]; string
0x180026362  call    cs:__imp_WindowsDeleteString
0x180026369  nop     dword ptr [rax+rax+00h]
0x18002636e  mov     [rbx+10h], rdi
0x180026372  mov     rbx, [rsp+28h+arg_0]
0x180026377  add     rsp, 20h
0x18002637b  pop     rdi
0x18002637c  retn
```
