# Windows::System::Internal::Launch::ExtensionProperties::~ExtensionProperties(void)

- ea: `0x18006c294`
- end: `0x18006c31f`
- name: `??1ExtensionProperties@Launch@Internal@System@Windows@@QEAA@XZ`
- size: `139`
- prototype: `void __fastcall(Windows::System::Internal::Launch::ExtensionProperties *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180021ae4`
- `0x18002984c`
- `0x18002cf0c`
- `0x180108970`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006c2a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006c2b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006c2c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006c2d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006c2e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006c2fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006c30c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006c2a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006c2b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006c2c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006c2d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006c2e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006c2fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006c30c`

## pseudocode

```c
void __fastcall Windows::System::Internal::Launch::ExtensionProperties::~ExtensionProperties(HSTRING *this)
{
  WindowsDeleteString(this[7]);
  this[7] = 0;
  WindowsDeleteString(this[5]);
  this[5] = 0;
  WindowsDeleteString(this[4]);
  this[4] = 0;
  WindowsDeleteString(this[3]);
  this[3] = 0;
  WindowsDeleteString(this[2]);
  this[2] = 0;
  WindowsDeleteString(this[1]);
  this[1] = 0;
  WindowsDeleteString(*this);
  *this = 0;
}

```

## disassembly

```asm
0x18006c294  push    rbx
0x18006c296  sub     rsp, 20h
0x18006c29a  mov     rbx, rcx
0x18006c29d  mov     rcx, [rcx+38h]; string
0x18006c2a1  call    cs:__imp_WindowsDeleteString
0x18006c2a7  mov     qword ptr [rbx+38h], 0
0x18006c2af  mov     rcx, [rbx+28h]; string
0x18006c2b3  call    cs:__imp_WindowsDeleteString
0x18006c2b9  mov     qword ptr [rbx+28h], 0
0x18006c2c1  mov     rcx, [rbx+20h]; string
0x18006c2c5  call    cs:__imp_WindowsDeleteString
0x18006c2cb  mov     qword ptr [rbx+20h], 0
0x18006c2d3  mov     rcx, [rbx+18h]; string
0x18006c2d7  call    cs:__imp_WindowsDeleteString
0x18006c2dd  mov     qword ptr [rbx+18h], 0
0x18006c2e5  mov     rcx, [rbx+10h]; string
0x18006c2e9  call    cs:__imp_WindowsDeleteString
0x18006c2ef  mov     qword ptr [rbx+10h], 0
0x18006c2f7  mov     rcx, [rbx+8]; string
0x18006c2fb  call    cs:__imp_WindowsDeleteString
0x18006c301  mov     qword ptr [rbx+8], 0
0x18006c309  mov     rcx, [rbx]; string
0x18006c30c  call    cs:__imp_WindowsDeleteString
0x18006c312  mov     qword ptr [rbx], 0
0x18006c319  add     rsp, 20h
0x18006c31d  pop     rbx
0x18006c31e  retn
```
