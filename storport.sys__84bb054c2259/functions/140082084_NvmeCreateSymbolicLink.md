# NvmeCreateSymbolicLink

- ea: `0x140082084`
- end: `0x140082251`
- name: `NvmeCreateSymbolicLink`
- size: `461`
- prototype: `__int64 __fastcall(PUNICODE_STRING DeviceName)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, registry_config`

## callers

- `0x140081e88`

## callees

- `0x140046bcc`
- `0x140082084`
- `0x14014b400`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400820f8`
- `ntoskrnl!RtlInitUnicodeString` at `0x140082123`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400821ba`
- `ntoskrnl!RtlInitUnicodeString` at `0x140082208`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400820f8`
- `ntoskrnl!RtlInitUnicodeString` at `0x140082123`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400821ba`
- `ntoskrnl!RtlInitUnicodeString` at `0x140082208`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140082168`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140082168`
- `ntoskrnl!IoCreateSymbolicLink` at `0x140082137`
- `ntoskrnl!IoCreateSymbolicLink` at `0x140082151`
- `ntoskrnl!IoCreateSymbolicLink` at `0x1400821ce`
- `ntoskrnl!IoCreateSymbolicLink` at `0x14008221c`
- `ntoskrnl!IoCreateSymbolicLink` at `0x140082137`
- `ntoskrnl!IoCreateSymbolicLink` at `0x140082151`
- `ntoskrnl!IoCreateSymbolicLink` at `0x1400821ce`
- `ntoskrnl!IoCreateSymbolicLink` at `0x14008221c`
- `ntoskrnl!IoGetConfigurationInformation` at `0x1400821da`
- `ntoskrnl!IoGetConfigurationInformation` at `0x1400821da`

## pseudocode

```c
__int64 __fastcall NvmeCreateSymbolicLink(PUNICODE_STRING DeviceName, unsigned int *a2)
{
  unsigned int v2; // edi
  unsigned int v5; // ebx
  PCONFIGURATION_INFORMATION ConfigurationInformation; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-E0h] BYREF
  struct _UNICODE_STRING SymbolicLinkName; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t pszDest[64]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t SourceString[64]; // [rsp+C0h] [rbp-40h] BYREF

  v2 = 0;
  v5 = -1073741823;
  DestinationString = 0;
  SymbolicLinkName = 0;
  while ( v2 <= 0xFFFF )
  {
    RtlStringCchPrintfW(
      pszDest,
      0x40u,
      L"\\Device\\ScsiPort%d",
      v2,
      *(_QWORD *)&DestinationString.Length,
      DestinationString.Buffer,
      *(_QWORD *)&SymbolicLinkName.Length,
      SymbolicLinkName.Buffer);
    RtlInitUnicodeString(&DestinationString, pszDest);
    RtlStringCchPrintfW(SourceString, 0x40u, L"\\Device\\NvmePort%d", v2);
    RtlInitUnicodeString(&SymbolicLinkName, SourceString);
    v5 = IoCreateSymbolicLink(&DestinationString, DeviceName);
    if ( !v5 )
    {
      v5 = IoCreateSymbolicLink(&SymbolicLinkName, DeviceName);
      if ( !v5 )
        break;
      IoDeleteSymbolicLink(&DestinationString);
    }
    if ( v5 != -1073741771 )
      return v5;
    if ( v2 == 0xFFFF )
      return (unsigned int)-1073741670;
    ++v2;
  }
  RtlStringCchPrintfW(
    pszDest,
    0x40u,
    L"\\DosDevices\\Scsi%d:",
    v2,
    *(_QWORD *)&DestinationString.Length,
    DestinationString.Buffer,
    *(_QWORD *)&SymbolicLinkName.Length,
    SymbolicLinkName.Buffer);
  RtlInitUnicodeString(&DestinationString, pszDest);
  IoCreateSymbolicLink(&DestinationString, DeviceName);
  ConfigurationInformation = IoGetConfigurationInformation();
  ++ConfigurationInformation->ScsiPortCount;
  RtlStringCchPrintfW(SourceString, 0x40u, L"\\DosDevices\\NvmeAdapter%d", v2);
  RtlInitUnicodeString(&SymbolicLinkName, SourceString);
  IoCreateSymbolicLink(&SymbolicLinkName, DeviceName);
  *a2 = v2;
  return v5;
}

```

## disassembly

```asm
0x140082084  mov     [rsp-8+arg_10], rbx
0x140082089  push    rbp
0x14008208a  push    rsi
0x14008208b  push    rdi
0x14008208c  push    r12
0x14008208e  push    r14
0x140082090  lea     rbp, [rsp-50h]
0x140082095  sub     rsp, 150h
0x14008209c  mov     rax, cs:__security_cookie
0x1400820a3  xor     rax, rsp
0x1400820a6  mov     [rbp+70h+var_30], rax
0x1400820aa  xor     edi, edi
0x1400820ac  xorps   xmm0, xmm0
0x1400820af  xorps   xmm1, xmm1
0x1400820b2  mov     r14, rdx
0x1400820b5  mov     rsi, rcx
0x1400820b8  mov     ebx, 0C0000001h
0x1400820bd  movups  xmmword ptr [rsp+170h+DestinationString.Length], xmm0
0x1400820c2  lea     r12d, [rdi+40h]
0x1400820c6  movups  xmmword ptr [rsp+170h+SymbolicLinkName.Length], xmm1
0x1400820cb  cmp     edi, 0FFFFh
0x1400820d1  ja      loc_140082199
0x1400820d7  mov     r9d, edi
0x1400820da  lea     r8, aDeviceScsiport; "\\Device\\ScsiPort%d"
0x1400820e1  mov     rdx, r12; cchDest
0x1400820e4  lea     rcx, [rsp+170h+pszDest]; pszDest
0x1400820e9  call    RtlStringCchPrintfW
0x1400820ee  lea     rdx, [rsp+170h+pszDest]; SourceString
0x1400820f3  lea     rcx, [rsp+170h+DestinationString]; DestinationString
0x1400820f8  call    cs:__imp_RtlInitUnicodeString
0x1400820ff  nop     dword ptr [rax+rax+00h]
0x140082104  mov     r9d, edi
0x140082107  lea     r8, aDeviceNvmeport; "\\Device\\NvmePort%d"
0x14008210e  mov     rdx, r12; cchDest
0x140082111  lea     rcx, [rbp+70h+SourceString]; pszDest
0x140082115  call    RtlStringCchPrintfW
0x14008211a  lea     rdx, [rbp+70h+SourceString]; SourceString
0x14008211e  lea     rcx, [rsp+170h+SymbolicLinkName]; DestinationString
0x140082123  call    cs:__imp_RtlInitUnicodeString
0x14008212a  nop     dword ptr [rax+rax+00h]
0x14008212f  mov     rdx, rsi; DeviceName
0x140082132  lea     rcx, [rsp+170h+DestinationString]; SymbolicLinkName
0x140082137  call    cs:__imp_IoCreateSymbolicLink
0x14008213e  nop     dword ptr [rax+rax+00h]
0x140082143  mov     ebx, eax
0x140082145  test    eax, eax
0x140082147  jnz     short loc_140082174
0x140082149  mov     rdx, rsi; DeviceName
0x14008214c  lea     rcx, [rsp+170h+SymbolicLinkName]; SymbolicLinkName
0x140082151  call    cs:__imp_IoCreateSymbolicLink
0x140082158  nop     dword ptr [rax+rax+00h]
0x14008215d  mov     ebx, eax
0x14008215f  test    eax, eax
0x140082161  jz      short loc_140082199
0x140082163  lea     rcx, [rsp+170h+DestinationString]; SymbolicLinkName
0x140082168  call    cs:__imp_IoDeleteSymbolicLink
0x14008216f  nop     dword ptr [rax+rax+00h]
0x140082174  cmp     ebx, 0C0000035h
0x14008217a  jnz     loc_14008222B
0x140082180  cmp     edi, 0FFFFh
0x140082186  jz      short loc_14008218F
0x140082188  inc     edi
0x14008218a  jmp     loc_1400820CB
0x14008218f  mov     ebx, 0C000009Ah
0x140082194  jmp     loc_14008222B
0x140082199  mov     r9d, edi
0x14008219c  lea     r8, aDosdevicesScsi; "\\DosDevices\\Scsi%d:"
0x1400821a3  mov     rdx, r12; cchDest
0x1400821a6  lea     rcx, [rsp+170h+pszDest]; pszDest
0x1400821ab  call    RtlStringCchPrintfW
0x1400821b0  lea     rdx, [rsp+170h+pszDest]; SourceString
0x1400821b5  lea     rcx, [rsp+170h+DestinationString]; DestinationString
0x1400821ba  call    cs:__imp_RtlInitUnicodeString
0x1400821c1  nop     dword ptr [rax+rax+00h]
0x1400821c6  mov     rdx, rsi; DeviceName
0x1400821c9  lea     rcx, [rsp+170h+DestinationString]; SymbolicLinkName
0x1400821ce  call    cs:__imp_IoCreateSymbolicLink
0x1400821d5  nop     dword ptr [rax+rax+00h]
0x1400821da  call    cs:__imp_IoGetConfigurationInformation
0x1400821e1  nop     dword ptr [rax+rax+00h]
0x1400821e6  mov     r9d, edi
0x1400821e9  lea     r8, aDosdevicesNvme; "\\DosDevices\\NvmeAdapter%d"
0x1400821f0  mov     rdx, r12; cchDest
0x1400821f3  lea     rcx, [rbp+70h+SourceString]; pszDest
0x1400821f7  inc     dword ptr [rax+10h]
0x1400821fa  call    RtlStringCchPrintfW
0x1400821ff  lea     rdx, [rbp+70h+SourceString]; SourceString
0x140082203  lea     rcx, [rsp+170h+SymbolicLinkName]; DestinationString
0x140082208  call    cs:__imp_RtlInitUnicodeString
0x14008220f  nop     dword ptr [rax+rax+00h]
0x140082214  mov     rdx, rsi; DeviceName
0x140082217  lea     rcx, [rsp+170h+SymbolicLinkName]; SymbolicLinkName
0x14008221c  call    cs:__imp_IoCreateSymbolicLink
0x140082223  nop     dword ptr [rax+rax+00h]
0x140082228  mov     [r14], edi
0x14008222b  mov     eax, ebx
0x14008222d  mov     rcx, [rbp+70h+var_30]
0x140082231  xor     rcx, rsp; StackCookie
0x140082234  call    __security_check_cookie
0x140082239  mov     rbx, [rsp+170h+arg_10]
0x140082241  add     rsp, 150h
0x140082248  pop     r14
0x14008224a  pop     r12
0x14008224c  pop     rdi
0x14008224d  pop     rsi
0x14008224e  pop     rbp
0x14008224f  retn
```
