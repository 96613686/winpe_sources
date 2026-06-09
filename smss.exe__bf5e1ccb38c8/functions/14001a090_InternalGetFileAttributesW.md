# InternalGetFileAttributesW

- ea: `0x14001a090`
- end: `0x14001a19a`
- name: `InternalGetFileAttributesW`
- size: `266`
- prototype: `__int64 __fastcall(PCWSTR Name)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400130f4`
- `0x14001ae48`

## callees

- `0x14001a090`
- `0x14001cabc`
- `0x14001cc40`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x14001a155`
- `ntdll!RtlFreeHeap` at `0x14001a155`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x14001a0e0`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x14001a0e0`
- `ntdll!NtQueryAttributesFile` at `0x14001a13b`
- `ntdll!NtQueryAttributesFile` at `0x14001a13b`
- `ntdll!RtlSetLastWin32Error` at `0x14001a0fd`
- `ntdll!RtlSetLastWin32Error` at `0x14001a0fd`
- `ntdll!RtlIsDosDeviceName_U` at `0x14001a167`
- `ntdll!RtlIsDosDeviceName_U` at `0x14001a167`

## pseudocode

```c
__int64 __fastcall InternalGetFileAttributesW(PCWSTR Name)
{
  int v2; // eax
  __int64 v3; // rcx
  PVOID v4; // rbx
  NTSTATUS v5; // edi
  PVOID BaseAddress[2]; // [rsp+20h] [rbp-39h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-29h] BYREF
  struct _FILE_BASIC_INFORMATION FileInformation; // [rsp+60h] [rbp+7h] BYREF

  memset(&ObjectAttributes, 0, 44);
  *(_OWORD *)BaseAddress = 0;
  memset(&FileInformation, 0, sizeof(FileInformation));
  v2 = RtlDosPathNameToNtPathName_U_WithStatus(Name, BaseAddress, 0, 0);
  if ( v2 >= 0 )
  {
    v4 = BaseAddress[1];
    ObjectAttributes.ObjectName = (PUNICODE_STRING)BaseAddress;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    ObjectAttributes.Attributes = 64;
    v5 = NtQueryAttributesFile(&ObjectAttributes, &FileInformation);
    RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, v4);
    if ( v5 >= 0 )
      return FileInformation.FileAttributes;
    if ( RtlIsDosDeviceName_U(Name) )
      return 32;
    v3 = (unsigned int)v5;
    goto LABEL_11;
  }
  if ( v2 == -1073741801 || v2 == -1073741670 )
  {
    v3 = (unsigned int)v2;
LABEL_11:
    BaseSetLastNTError(v3);
    return 0xFFFFFFFFLL;
  }
  RtlSetLastWin32Error(3u);
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x14001a090  push    rbp
0x14001a092  push    rbx
0x14001a093  push    rsi
0x14001a094  push    rdi
0x14001a095  lea     rbp, [rsp-3Fh]
0x14001a09a  sub     rsp, 98h
0x14001a0a1  mov     rax, cs:__security_cookie
0x14001a0a8  xor     rax, rsp
0x14001a0ab  mov     [rbp+57h+var_28], rax
0x14001a0af  xorps   xmm0, xmm0
0x14001a0b2  lea     rdx, [rbp+57h+BaseAddress]
0x14001a0b6  xorps   xmm1, xmm1
0x14001a0b9  xor     eax, eax
0x14001a0bb  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14001a0bf  xor     r9d, r9d
0x14001a0c2  mov     qword ptr [rbp+57h+FileInformation.FileAttributes], rax
0x14001a0c6  xor     r8d, r8d
0x14001a0c9  mov     rsi, rcx
0x14001a0cc  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x14001a0d0  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14001a0d4  movups  xmmword ptr [rbp+57h+BaseAddress], xmm0
0x14001a0d8  movups  xmmword ptr [rbp+57h+FileInformation.CreationTime], xmm1
0x14001a0dc  movups  xmmword ptr [rbp+57h+FileInformation.LastWriteTime], xmm1
0x14001a0e0  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x14001a0e6  test    eax, eax
0x14001a0e8  jns     short loc_14001A109
0x14001a0ea  cmp     eax, 0C0000017h
0x14001a0ef  jz      short loc_14001A105
0x14001a0f1  cmp     eax, 0C000009Ah
0x14001a0f6  jz      short loc_14001A105
0x14001a0f8  mov     ecx, 3; LastError
0x14001a0fd  call    cs:__imp_RtlSetLastWin32Error
0x14001a103  jmp     short loc_14001A17F
0x14001a105  mov     ecx, eax
0x14001a107  jmp     short loc_14001A17A
0x14001a109  mov     rbx, [rbp+57h+BaseAddress+8]
0x14001a10d  lea     rax, [rbp+57h+BaseAddress]
0x14001a111  xorps   xmm0, xmm0
0x14001a114  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14001a118  lea     rdx, [rbp+57h+FileInformation]; FileInformation
0x14001a11c  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14001a123  lea     rcx, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14001a127  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x14001a12f  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14001a134  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x14001a13b  call    cs:__imp_NtQueryAttributesFile
0x14001a141  mov     rcx, gs:60h
0x14001a14a  mov     r8, rbx; BaseAddress
0x14001a14d  xor     edx, edx; Flags
0x14001a14f  mov     edi, eax
0x14001a151  mov     rcx, [rcx+30h]; HeapHandle
0x14001a155  call    cs:__imp_RtlFreeHeap
0x14001a15b  test    edi, edi
0x14001a15d  js      short loc_14001A164
0x14001a15f  mov     eax, [rbp+57h+FileInformation.FileAttributes]
0x14001a162  jmp     short loc_14001A182
0x14001a164  mov     rcx, rsi; Name
0x14001a167  call    cs:__imp_RtlIsDosDeviceName_U
0x14001a16d  test    eax, eax
0x14001a16f  jz      short loc_14001A178
0x14001a171  mov     eax, 20h ; ' '
0x14001a176  jmp     short loc_14001A182
0x14001a178  mov     ecx, edi
0x14001a17a  call    BaseSetLastNTError
0x14001a17f  or      eax, 0FFFFFFFFh
0x14001a182  mov     rcx, [rbp+57h+var_28]
0x14001a186  xor     rcx, rsp; StackCookie
0x14001a189  call    __security_check_cookie
0x14001a18e  add     rsp, 98h
0x14001a195  pop     rdi
0x14001a196  pop     rsi
0x14001a197  pop     rbx
0x14001a198  pop     rbp
0x14001a199  retn
```
