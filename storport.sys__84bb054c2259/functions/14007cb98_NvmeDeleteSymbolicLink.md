# NvmeDeleteSymbolicLink

- ea: `0x14007cb98`
- end: `0x14007ccd3`
- name: `NvmeDeleteSymbolicLink`
- size: `315`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path`

## callers

- `0x14007ca74`

## callees

- `0x140046bcc`
- `0x14014b400`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14007cbe8`
- `ntoskrnl!RtlInitUnicodeString` at `0x14007cc21`
- `ntoskrnl!RtlInitUnicodeString` at `0x14007cc5a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14007cc93`
- `ntoskrnl!RtlInitUnicodeString` at `0x14007cbe8`
- `ntoskrnl!RtlInitUnicodeString` at `0x14007cc21`
- `ntoskrnl!RtlInitUnicodeString` at `0x14007cc5a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14007cc93`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14007cbf8`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14007cc31`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14007cc6a`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14007cca3`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14007cbf8`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14007cc31`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14007cc6a`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14007cca3`

## pseudocode

```c
__int64 __fastcall NvmeDeleteSymbolicLink(unsigned int a1)
{
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-49h] BYREF
  wchar_t pszDest[64]; // [rsp+30h] [rbp-39h] BYREF

  RtlStringCchPrintfW(pszDest, 0x40u, L"\\Device\\NvmePort%d", a1, 0, 0);
  RtlInitUnicodeString(&DestinationString, pszDest);
  IoDeleteSymbolicLink(&DestinationString);
  RtlStringCchPrintfW(pszDest, 0x40u, L"\\Device\\ScsiPort%d", a1);
  RtlInitUnicodeString(&DestinationString, pszDest);
  IoDeleteSymbolicLink(&DestinationString);
  RtlStringCchPrintfW(pszDest, 0x40u, L"\\DosDevices\\NvmeAdapter%d", a1);
  RtlInitUnicodeString(&DestinationString, pszDest);
  IoDeleteSymbolicLink(&DestinationString);
  RtlStringCchPrintfW(pszDest, 0x40u, L"\\DosDevices\\Scsi%d:", a1);
  RtlInitUnicodeString(&DestinationString, pszDest);
  IoDeleteSymbolicLink(&DestinationString);
  return 0;
}

```

## disassembly

```asm
0x14007cb98  mov     [rsp-8+arg_8], rbx
0x14007cb9d  mov     [rsp-8+arg_10], rdi
0x14007cba2  push    rbp
0x14007cba3  lea     rbp, [rsp-57h]
0x14007cba8  sub     rsp, 0C0h
0x14007cbaf  mov     rax, cs:__security_cookie
0x14007cbb6  xor     rax, rsp
0x14007cbb9  mov     [rbp+57h+var_10], rax
0x14007cbbd  mov     ebx, ecx
0x14007cbbf  lea     r8, aDeviceNvmeport; "\\Device\\NvmePort%d"
0x14007cbc6  xorps   xmm0, xmm0
0x14007cbc9  mov     r9d, ecx
0x14007cbcc  mov     edi, 40h ; '@'
0x14007cbd1  lea     rcx, [rbp+57h+pszDest]; pszDest
0x14007cbd5  mov     edx, edi; cchDest
0x14007cbd7  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14007cbdb  call    RtlStringCchPrintfW
0x14007cbe0  lea     rdx, [rbp+57h+pszDest]; SourceString
0x14007cbe4  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14007cbe8  call    cs:__imp_RtlInitUnicodeString
0x14007cbef  nop     dword ptr [rax+rax+00h]
0x14007cbf4  lea     rcx, [rbp+57h+DestinationString]; SymbolicLinkName
0x14007cbf8  call    cs:__imp_IoDeleteSymbolicLink
0x14007cbff  nop     dword ptr [rax+rax+00h]
0x14007cc04  mov     r9d, ebx
0x14007cc07  lea     r8, aDeviceScsiport; "\\Device\\ScsiPort%d"
0x14007cc0e  mov     edx, edi; cchDest
0x14007cc10  lea     rcx, [rbp+57h+pszDest]; pszDest
0x14007cc14  call    RtlStringCchPrintfW
0x14007cc19  lea     rdx, [rbp+57h+pszDest]; SourceString
0x14007cc1d  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14007cc21  call    cs:__imp_RtlInitUnicodeString
0x14007cc28  nop     dword ptr [rax+rax+00h]
0x14007cc2d  lea     rcx, [rbp+57h+DestinationString]; SymbolicLinkName
0x14007cc31  call    cs:__imp_IoDeleteSymbolicLink
0x14007cc38  nop     dword ptr [rax+rax+00h]
0x14007cc3d  mov     r9d, ebx
0x14007cc40  lea     r8, aDosdevicesNvme; "\\DosDevices\\NvmeAdapter%d"
0x14007cc47  mov     edx, edi; cchDest
0x14007cc49  lea     rcx, [rbp+57h+pszDest]; pszDest
0x14007cc4d  call    RtlStringCchPrintfW
0x14007cc52  lea     rdx, [rbp+57h+pszDest]; SourceString
0x14007cc56  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14007cc5a  call    cs:__imp_RtlInitUnicodeString
0x14007cc61  nop     dword ptr [rax+rax+00h]
0x14007cc66  lea     rcx, [rbp+57h+DestinationString]; SymbolicLinkName
0x14007cc6a  call    cs:__imp_IoDeleteSymbolicLink
0x14007cc71  nop     dword ptr [rax+rax+00h]
0x14007cc76  mov     r9d, ebx
0x14007cc79  lea     r8, aDosdevicesScsi; "\\DosDevices\\Scsi%d:"
0x14007cc80  mov     edx, edi; cchDest
0x14007cc82  lea     rcx, [rbp+57h+pszDest]; pszDest
0x14007cc86  call    RtlStringCchPrintfW
0x14007cc8b  lea     rdx, [rbp+57h+pszDest]; SourceString
0x14007cc8f  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14007cc93  call    cs:__imp_RtlInitUnicodeString
0x14007cc9a  nop     dword ptr [rax+rax+00h]
0x14007cc9f  lea     rcx, [rbp+57h+DestinationString]; SymbolicLinkName
0x14007cca3  call    cs:__imp_IoDeleteSymbolicLink
0x14007ccaa  nop     dword ptr [rax+rax+00h]
0x14007ccaf  xor     eax, eax
0x14007ccb1  mov     rcx, [rbp+57h+var_10]
0x14007ccb5  xor     rcx, rsp; StackCookie
0x14007ccb8  call    __security_check_cookie
0x14007ccbd  lea     r11, [rsp+0C0h+var_s0]
0x14007ccc5  mov     rbx, [r11+18h]
0x14007ccc9  mov     rdi, [r11+20h]
0x14007cccd  mov     rsp, r11
0x14007ccd0  pop     rbp
0x14007ccd1  retn
```
