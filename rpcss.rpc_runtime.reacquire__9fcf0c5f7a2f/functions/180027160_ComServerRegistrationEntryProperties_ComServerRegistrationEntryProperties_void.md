# ComServerRegistrationEntryProperties::~ComServerRegistrationEntryProperties(void)

- ea: `0x180027160`
- end: `0x18002722d`
- name: `??1ComServerRegistrationEntryProperties@@QEAA@XZ`
- size: `205`
- prototype: `void __fastcall(ComServerRegistrationEntryProperties *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800270ec`
- `0x180094084`
- `0x1800dc52c`
- `0x1800e64cc`

## callees

- `0x1800274d4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027170`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002718e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800271a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800271c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800271e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800271fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027212`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027170`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002718e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800271a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800271c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800271e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800271fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027212`

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
0x180027160  push    rbx
0x180027162  sub     rsp, 20h
0x180027166  mov     rbx, rcx
0x180027169  mov     rcx, [rcx+0A8h]; string
0x180027170  call    cs:__imp_WindowsDeleteString
0x180027177  nop     dword ptr [rax+rax+00h]
0x18002717c  mov     qword ptr [rbx+0A8h], 0
0x180027187  mov     rcx, [rbx+98h]; string
0x18002718e  call    cs:__imp_WindowsDeleteString
0x180027195  nop     dword ptr [rax+rax+00h]
0x18002719a  mov     qword ptr [rbx+98h], 0
0x1800271a5  mov     rcx, [rbx+70h]; string
0x1800271a9  call    cs:__imp_WindowsDeleteString
0x1800271b0  nop     dword ptr [rax+rax+00h]
0x1800271b5  mov     qword ptr [rbx+70h], 0
0x1800271bd  mov     rcx, [rbx+50h]; string
0x1800271c1  call    cs:__imp_WindowsDeleteString
0x1800271c8  nop     dword ptr [rax+rax+00h]
0x1800271cd  lea     rcx, [rbx+38h]; this
0x1800271d1  mov     qword ptr [rbx+50h], 0
0x1800271d9  call    ?Release@SecurityDescriptor@@QEAAXXZ; SecurityDescriptor::Release(void)
0x1800271de  mov     rcx, [rbx+28h]; string
0x1800271e2  call    cs:__imp_WindowsDeleteString
0x1800271e9  nop     dword ptr [rax+rax+00h]
0x1800271ee  mov     qword ptr [rbx+28h], 0
0x1800271f6  mov     rcx, [rbx+18h]; string
0x1800271fa  call    cs:__imp_WindowsDeleteString
0x180027201  nop     dword ptr [rax+rax+00h]
0x180027206  mov     qword ptr [rbx+18h], 0
0x18002720e  mov     rcx, [rbx+8]; string
0x180027212  call    cs:__imp_WindowsDeleteString
0x180027219  nop     dword ptr [rax+rax+00h]
0x18002721e  mov     qword ptr [rbx+8], 0
0x180027226  add     rsp, 20h
0x18002722a  pop     rbx
0x18002722b  retn
```
