# SclFileObjectExists

- ea: `0x18000e66c`
- end: `0x18000e739`
- name: `SclFileObjectExists`
- size: `205`
- prototype: `bool __fastcall(const WCHAR *)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180002b98`
- `0x180009904`
- `0x18000bc68`

## callees

- `0x180001c74`
- `0x18000e66c`
- `0x1800179e0`

## import_xrefs

- `ntdll!RtlSetThreadErrorMode` at `0x18000e6bf`
- `ntdll!RtlSetThreadErrorMode` at `0x18000e710`
- `ntdll!RtlSetThreadErrorMode` at `0x18000e6bf`
- `ntdll!RtlSetThreadErrorMode` at `0x18000e710`
- `ntdll!NtQueryAttributesFile` at `0x18000e6f2`
- `ntdll!NtQueryAttributesFile` at `0x18000e6f2`

## pseudocode

```c
bool __fastcall SclFileObjectExists(const WCHAR *a1)
{
  NTSTATUS v2; // ebx
  bool v3; // bl
  ULONG OldMode; // [rsp+30h] [rbp-29h] BYREF
  struct _UNICODE_STRING v6; // [rsp+38h] [rbp-21h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+48h] [rbp-11h] BYREF
  _FILE_BASIC_INFORMATION FileInformation; // [rsp+78h] [rbp+1Fh] BYREF

  OldMode = 0;
  v6 = 0;
  memset(&ObjectAttributes, 0, 44);
  memset(&FileInformation, 0, sizeof(FileInformation));
  v2 = RtlSetThreadErrorMode(0x50u, &OldMode);
  INIT_OBJA_EX((__int64)&ObjectAttributes, &v6, a1, 64, 0);
  v3 = v2 >= 0
    && NtQueryAttributesFile(&ObjectAttributes, &FileInformation) >= 0
    && (FileInformation.FileAttributes & 0x10) == 0;
  RtlSetThreadErrorMode(OldMode, 0);
  return v3;
}

```

## disassembly

```asm
0x18000e66c  mov     [rsp-8+arg_8], rbx
0x18000e671  mov     [rsp-8+arg_10], rdi
0x18000e676  push    rbp
0x18000e677  lea     rbp, [rsp-57h]
0x18000e67c  sub     rsp, 0B0h
0x18000e683  mov     rax, cs:__security_cookie
0x18000e68a  xor     rax, rsp
0x18000e68d  mov     [rbp+57h+var_10], rax
0x18000e691  xorps   xmm0, xmm0
0x18000e694  lea     rdx, [rbp+57h+OldMode]; OldMode
0x18000e698  xor     eax, eax
0x18000e69a  mov     rdi, rcx
0x18000e69d  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18000e6a1  mov     [rbp+57h+OldMode], eax
0x18000e6a4  movups  [rbp+57h+var_78], xmm0
0x18000e6a8  lea     ecx, [rax+50h]; NewMode
0x18000e6ab  mov     qword ptr [rbp+57h+FileInformation.FileAttributes], rax
0x18000e6af  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18000e6b3  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18000e6b7  movups  xmmword ptr [rbp+57h+FileInformation.CreationTime], xmm0
0x18000e6bb  movups  xmmword ptr [rbp+57h+FileInformation.LastWriteTime], xmm0
0x18000e6bf  call    cs:__imp_RtlSetThreadErrorMode
0x18000e6c5  mov     r9d, 40h ; '@'
0x18000e6cb  mov     [rsp+0B0h+var_90], 0
0x18000e6d4  mov     r8, rdi
0x18000e6d7  lea     rdx, [rbp+57h+var_78]
0x18000e6db  lea     rcx, [rbp+57h+ObjectAttributes]
0x18000e6df  mov     ebx, eax
0x18000e6e1  call    INIT_OBJA_EX
0x18000e6e6  test    ebx, ebx
0x18000e6e8  js      short loc_18000E709
0x18000e6ea  lea     rdx, [rbp+57h+FileInformation]; FileInformation
0x18000e6ee  lea     rcx, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18000e6f2  call    cs:__imp_NtQueryAttributesFile
0x18000e6f8  test    eax, eax
0x18000e6fa  js      short loc_18000E709
0x18000e6fc  mov     ebx, [rbp+57h+FileInformation.FileAttributes]
0x18000e6ff  shr     ebx, 4
0x18000e702  not     bl
0x18000e704  and     bl, 1
0x18000e707  jmp     short loc_18000E70B
0x18000e709  xor     bl, bl
0x18000e70b  mov     ecx, [rbp+57h+OldMode]; NewMode
0x18000e70e  xor     edx, edx; OldMode
0x18000e710  call    cs:__imp_RtlSetThreadErrorMode
0x18000e716  mov     al, bl
0x18000e718  mov     rcx, [rbp+57h+var_10]
0x18000e71c  xor     rcx, rsp; StackCookie
0x18000e71f  call    __security_check_cookie
0x18000e724  lea     r11, [rsp+0B0h+var_s0]
0x18000e72c  mov     rbx, [r11+18h]
0x18000e730  mov     rdi, [r11+20h]
0x18000e734  mov     rsp, r11
0x18000e737  pop     rbp
0x18000e738  retn
```
