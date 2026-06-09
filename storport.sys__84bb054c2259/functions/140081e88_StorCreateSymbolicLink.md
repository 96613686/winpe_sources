# StorCreateSymbolicLink

- ea: `0x140081e88`
- end: `0x14008207d`
- name: `StorCreateSymbolicLink`
- size: `501`
- prototype: `__int64 __fastcall(PUNICODE_STRING DeviceName)`
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, registry_config`

## callers

- `0x1400873c0`
- `0x1400f6ae0`

## callees

- `0x140046bcc`
- `0x140081e88`
- `0x140082084`
- `0x14014b400`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140081f34`
- `ntoskrnl!RtlInitUnicodeString` at `0x140081f5f`
- `ntoskrnl!RtlInitUnicodeString` at `0x140082014`
- `ntoskrnl!RtlInitUnicodeString` at `0x140081f34`
- `ntoskrnl!RtlInitUnicodeString` at `0x140081f5f`
- `ntoskrnl!RtlInitUnicodeString` at `0x140082014`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140081fa4`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140081fd9`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140081fa4`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140081fd9`
- `ntoskrnl!IoCreateSymbolicLink` at `0x140081f73`
- `ntoskrnl!IoCreateSymbolicLink` at `0x140081f8d`
- `ntoskrnl!IoCreateSymbolicLink` at `0x140082028`
- `ntoskrnl!IoCreateSymbolicLink` at `0x140081f73`
- `ntoskrnl!IoCreateSymbolicLink` at `0x140081f8d`
- `ntoskrnl!IoCreateSymbolicLink` at `0x140082028`
- `ntoskrnl!IoGetConfigurationInformation` at `0x140082039`
- `ntoskrnl!IoGetConfigurationInformation` at `0x140082039`

## pseudocode

```c
__int64 __fastcall StorCreateSymbolicLink(PUNICODE_STRING DeviceName, char a2, unsigned int *a3, int *a4)
{
  int v4; // eax
  unsigned int v9; // edi
  unsigned int i; // ebx
  NTSTATUS v11; // eax
  struct _UNICODE_STRING *p_DestinationString; // rcx
  const wchar_t *v13; // r8
  PCONFIGURATION_INFORMATION ConfigurationInformation; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-E0h] BYREF
  struct _UNICODE_STRING SymbolicLinkName; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t pszDest[64]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t SourceString[64]; // [rsp+C0h] [rbp-40h] BYREF

  v4 = *a4;
  DestinationString = 0;
  SymbolicLinkName = 0;
  if ( v4 == 1314275652 )
  {
    if ( !*((_QWORD *)a4 + 77) )
      return NvmeCreateSymbolicLink(DeviceName);
  }
  else if ( v4 != 1094997074 )
  {
    return 3221225659LL;
  }
  v9 = 0;
  for ( i = 0; i <= 0xFFFF; ++i )
  {
    RtlStringCchPrintfW(
      pszDest,
      0x40u,
      L"\\Device\\ScsiPort%d",
      i,
      *(_QWORD *)&DestinationString.Length,
      DestinationString.Buffer,
      *(_QWORD *)&SymbolicLinkName.Length,
      SymbolicLinkName.Buffer);
    RtlInitUnicodeString(&DestinationString, pszDest);
    RtlStringCchPrintfW(SourceString, 0x40u, L"\\Device\\NvmePort%d", i);
    RtlInitUnicodeString(&SymbolicLinkName, SourceString);
    v9 = IoCreateSymbolicLink(&DestinationString, DeviceName);
    if ( !v9 )
    {
      v11 = IoCreateSymbolicLink(&SymbolicLinkName, DeviceName);
      p_DestinationString = &DestinationString;
      v9 = v11;
      if ( !v11 )
      {
        if ( !a2 )
          p_DestinationString = &SymbolicLinkName;
        IoDeleteSymbolicLink(p_DestinationString);
        break;
      }
      IoDeleteSymbolicLink(&DestinationString);
    }
    if ( v9 != -1073741771 )
      return v9;
    if ( i == 0xFFFF )
      return (unsigned int)-1073741670;
  }
  v13 = L"\\DosDevices\\NvmeAdapter%d";
  if ( !a2 )
    v13 = L"\\DosDevices\\Scsi%d:";
  RtlStringCchPrintfW(
    pszDest,
    0x40u,
    v13,
    i,
    *(_QWORD *)&DestinationString.Length,
    DestinationString.Buffer,
    *(_QWORD *)&SymbolicLinkName.Length,
    SymbolicLinkName.Buffer);
  RtlInitUnicodeString(&DestinationString, pszDest);
  IoCreateSymbolicLink(&DestinationString, DeviceName);
  if ( !a2 )
  {
    ConfigurationInformation = IoGetConfigurationInformation();
    ++ConfigurationInformation->ScsiPortCount;
  }
  *a3 = i;
  return v9;
}

```

## disassembly

```asm
0x140081e88  mov     [rsp-8+arg_8], rbx
0x140081e8d  mov     [rsp-8+arg_18], rsi
0x140081e92  push    rbp
0x140081e93  push    rdi
0x140081e94  push    r13
0x140081e96  push    r14
0x140081e98  push    r15
0x140081e9a  lea     rbp, [rsp-50h]
0x140081e9f  sub     rsp, 150h
0x140081ea6  mov     rax, cs:__security_cookie
0x140081ead  xor     rax, rsp
0x140081eb0  mov     [rbp+70h+var_30], rax
0x140081eb4  mov     eax, [r9]
0x140081eb7  xorps   xmm0, xmm0
0x140081eba  xorps   xmm1, xmm1
0x140081ebd  mov     r14, r8
0x140081ec0  mov     r15b, dl
0x140081ec3  mov     rsi, rcx
0x140081ec6  movups  xmmword ptr [rsp+170h+DestinationString.Length], xmm0
0x140081ecb  movups  xmmword ptr [rsp+170h+SymbolicLinkName.Length], xmm1
0x140081ed0  cmp     eax, 4E564144h
0x140081ed5  jnz     short loc_140081EEE
0x140081ed7  cmp     qword ptr [r9+268h], 0
0x140081edf  jnz     short loc_140081EFF
0x140081ee1  mov     rdx, r8
0x140081ee4  call    NvmeCreateSymbolicLink
0x140081ee9  jmp     loc_14008204D
0x140081eee  cmp     eax, 41445452h
0x140081ef3  jz      short loc_140081EFF
0x140081ef5  mov     eax, 0C00000BBh
0x140081efa  jmp     loc_14008204D
0x140081eff  xor     edi, edi
0x140081f01  xor     ebx, ebx
0x140081f03  lea     r13d, [rdi+40h]
0x140081f07  cmp     ebx, 0FFFFh
0x140081f0d  ja      loc_140081FE5
0x140081f13  mov     r9d, ebx
0x140081f16  lea     r8, aDeviceScsiport; "\\Device\\ScsiPort%d"
0x140081f1d  mov     rdx, r13; cchDest
0x140081f20  lea     rcx, [rsp+170h+pszDest]; pszDest
0x140081f25  call    RtlStringCchPrintfW
0x140081f2a  lea     rdx, [rsp+170h+pszDest]; SourceString
0x140081f2f  lea     rcx, [rsp+170h+DestinationString]; DestinationString
0x140081f34  call    cs:__imp_RtlInitUnicodeString
0x140081f3b  nop     dword ptr [rax+rax+00h]
0x140081f40  mov     r9d, ebx
0x140081f43  lea     r8, aDeviceNvmeport; "\\Device\\NvmePort%d"
0x140081f4a  mov     rdx, r13; cchDest
0x140081f4d  lea     rcx, [rbp+70h+SourceString]; pszDest
0x140081f51  call    RtlStringCchPrintfW
0x140081f56  lea     rdx, [rbp+70h+SourceString]; SourceString
0x140081f5a  lea     rcx, [rsp+170h+SymbolicLinkName]; DestinationString
0x140081f5f  call    cs:__imp_RtlInitUnicodeString
0x140081f66  nop     dword ptr [rax+rax+00h]
0x140081f6b  mov     rdx, rsi; DeviceName
0x140081f6e  lea     rcx, [rsp+170h+DestinationString]; SymbolicLinkName
0x140081f73  call    cs:__imp_IoCreateSymbolicLink
0x140081f7a  nop     dword ptr [rax+rax+00h]
0x140081f7f  mov     edi, eax
0x140081f81  test    eax, eax
0x140081f83  jnz     short loc_140081FB0
0x140081f85  mov     rdx, rsi; DeviceName
0x140081f88  lea     rcx, [rsp+170h+SymbolicLinkName]; SymbolicLinkName
0x140081f8d  call    cs:__imp_IoCreateSymbolicLink
0x140081f94  nop     dword ptr [rax+rax+00h]
0x140081f99  lea     rcx, [rsp+170h+DestinationString]; SymbolicLinkName
0x140081f9e  mov     edi, eax
0x140081fa0  test    eax, eax
0x140081fa2  jz      short loc_140081FCF
0x140081fa4  call    cs:__imp_IoDeleteSymbolicLink
0x140081fab  nop     dword ptr [rax+rax+00h]
0x140081fb0  cmp     edi, 0C0000035h
0x140081fb6  jnz     loc_14008204B
0x140081fbc  cmp     ebx, 0FFFFh
0x140081fc2  jz      loc_140082076
0x140081fc8  inc     ebx
0x140081fca  jmp     loc_140081F07
0x140081fcf  test    r15b, r15b
0x140081fd2  jnz     short loc_140081FD9
0x140081fd4  lea     rcx, [rsp+170h+SymbolicLinkName]; SymbolicLinkName
0x140081fd9  call    cs:__imp_IoDeleteSymbolicLink
0x140081fe0  nop     dword ptr [rax+rax+00h]
0x140081fe5  lea     rax, aDosdevicesScsi; "\\DosDevices\\Scsi%d:"
0x140081fec  test    r15b, r15b
0x140081fef  lea     r8, aDosdevicesNvme; "\\DosDevices\\NvmeAdapter%d"
0x140081ff6  mov     r9d, ebx
0x140081ff9  cmovz   r8, rax; pszFormat
0x140081ffd  lea     rcx, [rsp+170h+pszDest]; pszDest
0x140082002  mov     rdx, r13; cchDest
0x140082005  call    RtlStringCchPrintfW
0x14008200a  lea     rdx, [rsp+170h+pszDest]; SourceString
0x14008200f  lea     rcx, [rsp+170h+DestinationString]; DestinationString
0x140082014  call    cs:__imp_RtlInitUnicodeString
0x14008201b  nop     dword ptr [rax+rax+00h]
0x140082020  mov     rdx, rsi; DeviceName
0x140082023  lea     rcx, [rsp+170h+DestinationString]; SymbolicLinkName
0x140082028  call    cs:__imp_IoCreateSymbolicLink
0x14008202f  nop     dword ptr [rax+rax+00h]
0x140082034  test    r15b, r15b
0x140082037  jnz     short loc_140082048
0x140082039  call    cs:__imp_IoGetConfigurationInformation
0x140082040  nop     dword ptr [rax+rax+00h]
0x140082045  inc     dword ptr [rax+10h]
0x140082048  mov     [r14], ebx
0x14008204b  mov     eax, edi
0x14008204d  mov     rcx, [rbp+70h+var_30]
0x140082051  xor     rcx, rsp; StackCookie
0x140082054  call    __security_check_cookie
0x140082059  lea     r11, [rsp+170h+var_20]
0x140082061  mov     rbx, [r11+38h]
0x140082065  mov     rsi, [r11+48h]
0x140082069  mov     rsp, r11
0x14008206c  pop     r15
0x14008206e  pop     r14
0x140082070  pop     r13
0x140082072  pop     rdi
0x140082073  pop     rbp
0x140082074  retn
0x140082076  mov     edi, 0C000009Ah
0x14008207b  jmp     short loc_14008204B
```
