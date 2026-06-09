# ComServerRegistrationEntryProperties::~ComServerRegistrationEntryProperties(void)

- ea: `0x18000d1b4`
- end: `0x18000d256`
- name: `??1ComServerRegistrationEntryProperties@@QEAA@XZ`
- size: `162`
- prototype: `void __fastcall(ComServerRegistrationEntryProperties *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000d14c`
- `0x18008cef4`
- `0x1800d5a38`
- `0x1800df3d8`

## callees

- `0x18000d494`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d1c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d1dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d1f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d203`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d21e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d230`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d242`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d1c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d1dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d1f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d203`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d21e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d230`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d242`

## pseudocode

```c
void __fastcall ComServerRegistrationEntryProperties::~ComServerRegistrationEntryProperties(HSTRING *this)
{
  WindowsDeleteString(this[21]);
  this[21] = 0;
  WindowsDeleteString(this[19]);
  this[19] = 0;
  WindowsDeleteString(this[14]);
  this[14] = 0;
  WindowsDeleteString(this[10]);
  this[10] = 0;
  SecurityDescriptor::Release((SecurityDescriptor *)(this + 7));
  WindowsDeleteString(this[5]);
  this[5] = 0;
  WindowsDeleteString(this[3]);
  this[3] = 0;
  WindowsDeleteString(this[1]);
  this[1] = 0;
}

```

## disassembly

```asm
0x18000d1b4  push    rbx
0x18000d1b6  sub     rsp, 20h
0x18000d1ba  mov     rbx, rcx
0x18000d1bd  mov     rcx, [rcx+0A8h]; string
0x18000d1c4  call    cs:__imp_WindowsDeleteString
0x18000d1ca  mov     qword ptr [rbx+0A8h], 0
0x18000d1d5  mov     rcx, [rbx+98h]; string
0x18000d1dc  call    cs:__imp_WindowsDeleteString
0x18000d1e2  mov     qword ptr [rbx+98h], 0
0x18000d1ed  mov     rcx, [rbx+70h]; string
0x18000d1f1  call    cs:__imp_WindowsDeleteString
0x18000d1f7  mov     qword ptr [rbx+70h], 0
0x18000d1ff  mov     rcx, [rbx+50h]; string
0x18000d203  call    cs:__imp_WindowsDeleteString
0x18000d209  lea     rcx, [rbx+38h]; this
0x18000d20d  mov     qword ptr [rbx+50h], 0
0x18000d215  call    ?Release@SecurityDescriptor@@QEAAXXZ; SecurityDescriptor::Release(void)
0x18000d21a  mov     rcx, [rbx+28h]; string
0x18000d21e  call    cs:__imp_WindowsDeleteString
0x18000d224  mov     qword ptr [rbx+28h], 0
0x18000d22c  mov     rcx, [rbx+18h]; string
0x18000d230  call    cs:__imp_WindowsDeleteString
0x18000d236  mov     qword ptr [rbx+18h], 0
0x18000d23e  mov     rcx, [rbx+8]; string
0x18000d242  call    cs:__imp_WindowsDeleteString
0x18000d248  mov     qword ptr [rbx+8], 0
0x18000d250  add     rsp, 20h
0x18000d254  pop     rbx
0x18000d255  retn
```
