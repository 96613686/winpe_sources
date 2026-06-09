# WanpSetupExternalName

- ea: `0x140017a4c`
- end: `0x140017ae8`
- name: `WanpSetupExternalName`
- size: `156`
- prototype: `__int64 __fastcall(PUNICODE_STRING DeviceName)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, installer_update`

## callers

- `0x14000353c`
- `0x14001a078`

## callees

- `0x1400050b0`
- `0x140017a4c`

## import_xrefs

- `ntoskrnl!IoCreateSymbolicLink` at `0x140017aa1`
- `ntoskrnl!IoCreateSymbolicLink` at `0x140017aa1`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140017ab8`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140017ab8`
- `ntoskrnl!RtlInitUnicodeString` at `0x140017a89`
- `ntoskrnl!RtlInitUnicodeString` at `0x140017a89`

## pseudocode

```c
__int64 __fastcall WanpSetupExternalName(PUNICODE_STRING DeviceName, const WCHAR *a2, char a3)
{
  NTSTATUS v5; // eax
  unsigned int v6; // ecx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-F8h] BYREF
  char v9; // [rsp+30h] [rbp-E8h] BYREF

  *(_QWORD *)&DestinationString.Length = 0;
  DestinationString.Buffer = (wchar_t *)&v9;
  RtlInitUnicodeString(&DestinationString, a2);
  if ( a3 )
  {
    v5 = IoCreateSymbolicLink(&DestinationString, DeviceName);
    v6 = 0;
    if ( v5 < 0 )
      return (unsigned int)v5;
    return v6;
  }
  else
  {
    IoDeleteSymbolicLink(&DestinationString);
    return 0;
  }
}

```

## disassembly

```asm
0x140017a4c  mov     [rsp+arg_10], rbx
0x140017a51  push    rdi
0x140017a52  sub     rsp, 110h
0x140017a59  mov     rax, cs:__security_cookie
0x140017a60  xor     rax, rsp
0x140017a63  mov     [rsp+118h+var_18], rax
0x140017a6b  mov     rdi, rcx
0x140017a6e  mov     qword ptr [rsp+118h+DestinationString.Length], 0
0x140017a77  lea     rax, [rsp+118h+var_E8]
0x140017a7c  mov     bl, r8b
0x140017a7f  lea     rcx, [rsp+118h+DestinationString]; DestinationString
0x140017a84  mov     [rsp+118h+DestinationString.Buffer], rax
0x140017a89  call    cs:__imp_RtlInitUnicodeString
0x140017a90  nop     dword ptr [rax+rax+00h]
0x140017a95  lea     rcx, [rsp+118h+DestinationString]; SymbolicLinkName
0x140017a9a  test    bl, bl
0x140017a9c  jz      short loc_140017AB8
0x140017a9e  mov     rdx, rdi; DeviceName
0x140017aa1  call    cs:__imp_IoCreateSymbolicLink
0x140017aa8  nop     dword ptr [rax+rax+00h]
0x140017aad  xor     ecx, ecx
0x140017aaf  test    eax, eax
0x140017ab1  cmovs   ecx, eax
0x140017ab4  mov     eax, ecx
0x140017ab6  jmp     short loc_140017AC6
0x140017ab8  call    cs:__imp_IoDeleteSymbolicLink
0x140017abf  nop     dword ptr [rax+rax+00h]
0x140017ac4  xor     eax, eax
0x140017ac6  mov     rcx, [rsp+118h+var_18]
0x140017ace  xor     rcx, rsp; StackCookie
0x140017ad1  call    __security_check_cookie
0x140017ad6  mov     rbx, [rsp+118h+arg_10]
0x140017ade  add     rsp, 110h
0x140017ae5  pop     rdi
0x140017ae6  retn
```
