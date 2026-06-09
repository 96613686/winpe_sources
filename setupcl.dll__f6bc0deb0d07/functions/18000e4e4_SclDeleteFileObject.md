# SclDeleteFileObject

- ea: `0x18000e4e4`
- end: `0x18000e666`
- name: `SclDeleteFileObject`
- size: `386`
- prototype: `__int64 __fastcall(const WCHAR *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x180002b98`

## callees

- `0x180001c74`
- `0x18000a524`
- `0x18000e4e4`
- `0x1800179e0`

## import_xrefs

- `ntdll!NtClose` at `0x18000e645`
- `ntdll!NtClose` at `0x18000e645`
- `ntdll!NtOpenFile` at `0x18000e575`
- `ntdll!NtOpenFile` at `0x18000e575`
- `ntdll!NtSetInformationFile` at `0x18000e5d7`
- `ntdll!NtSetInformationFile` at `0x18000e5fd`
- `ntdll!NtSetInformationFile` at `0x18000e5d7`
- `ntdll!NtSetInformationFile` at `0x18000e5fd`

## string_xrefs

- `0x18000e59e`: `(%lx): Failed to open [%ws]`
- `0x18000e57b`: `SclDeleteFileObject`
- `0x18000e60e`: `(%lx): Unable to delete [%ws]`

## pseudocode

```c
__int64 __fastcall SclDeleteFileObject(const WCHAR *a1)
{
  NTSTATUS v1; // ebx
  char v3[8]; // [rsp+40h] [rbp-59h] BYREF
  void *FileHandle; // [rsp+48h] [rbp-51h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-49h] BYREF
  struct _UNICODE_STRING v6; // [rsp+60h] [rbp-39h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-29h] BYREF
  _OWORD FileInformation[2]; // [rsp+A0h] [rbp+7h] BYREF
  __int64 v9; // [rsp+C0h] [rbp+27h]

  v3[0] = 1;
  FileHandle = 0;
  v9 = 128;
  v6 = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  memset(FileInformation, 0, sizeof(FileInformation));
  INIT_OBJA_EX((__int64)&ObjectAttributes, &v6, a1, 64, 0);
  v1 = NtOpenFile(&FileHandle, 0x110100u, &ObjectAttributes, &IoStatusBlock, 0, 0x4060u);
  if ( v1 < 0 )
  {
    SclLogGenericMessage(0, 3, (unsigned int)SclEvent_Generic_Error, 571, (__int64)"SclDeleteFileObject");
LABEL_5:
    SclLogGenericMessage(0, 3, (unsigned int)SclEvent_Generic_Error, 589, (__int64)"SclDeleteFileObject");
    goto LABEL_6;
  }
  v1 = NtSetInformationFile(FileHandle, &IoStatusBlock, FileInformation, 0x28u, FileBasicInformation);
  if ( v1 < 0 )
    goto LABEL_5;
  v1 = NtSetInformationFile(FileHandle, &IoStatusBlock, v3, 1u, FileDispositionInformation);
  if ( v1 < 0 )
    goto LABEL_5;
LABEL_6:
  if ( FileHandle )
    NtClose(FileHandle);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18000e4e4  push    rbp
0x18000e4e6  push    rbx
0x18000e4e7  push    rdi
0x18000e4e8  push    r15
0x18000e4ea  lea     rbp, [rsp-3Fh]
0x18000e4ef  sub     rsp, 0D8h
0x18000e4f6  mov     rax, cs:__security_cookie
0x18000e4fd  xor     rax, rsp
0x18000e500  mov     [rbp+57h+var_28], rax
0x18000e504  xorps   xmm0, xmm0
0x18000e507  mov     [rbp+57h+var_B0], 1
0x18000e50b  xor     eax, eax
0x18000e50d  lea     rdx, [rbp+57h+var_90]
0x18000e511  mov     rdi, rcx
0x18000e514  mov     [rbp+57h+var_30], rax
0x18000e518  mov     r8, rcx
0x18000e51b  mov     [rbp+57h+FileHandle], rax
0x18000e51f  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18000e523  lea     r9d, [rax+40h]
0x18000e527  mov     dword ptr [rbp+57h+var_30], 80h
0x18000e52e  lea     rcx, [rbp+57h+ObjectAttributes]
0x18000e532  mov     qword ptr [rsp+0F0h+ShareAccess], rax
0x18000e537  movups  [rbp+57h+var_90], xmm0
0x18000e53b  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18000e53f  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18000e543  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18000e547  movups  [rbp+57h+FileInformation], xmm0
0x18000e54b  movups  [rbp+57h+var_40], xmm0
0x18000e54f  call    INIT_OBJA_EX
0x18000e554  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18000e558  mov     [rsp+0F0h+OpenOptions], 4060h; OpenOptions
0x18000e560  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18000e564  mov     [rsp+0F0h+ShareAccess], 0; ShareAccess
0x18000e56c  mov     edx, 110100h; DesiredAccess
0x18000e571  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x18000e575  call    cs:__imp_NtOpenFile
0x18000e57b  lea     r15, aScldeletefileo; "SclDeleteFileObject"
0x18000e582  mov     ebx, eax
0x18000e584  test    eax, eax
0x18000e586  jns     short loc_18000E5BD
0x18000e588  mov     [rsp+0F0h+var_B8], rdi
0x18000e58d  lea     r8, SclEvent_Generic_Error
0x18000e594  mov     [rsp+0F0h+var_C0], eax
0x18000e598  mov     r9d, 23Bh
0x18000e59e  lea     rax, aLxFailedToOpen_0; "(%lx): Failed to open [%ws]"
0x18000e5a5  mov     edx, 3
0x18000e5aa  mov     qword ptr [rsp+0F0h+OpenOptions], rax
0x18000e5af  xor     ecx, ecx
0x18000e5b1  mov     qword ptr [rsp+0F0h+ShareAccess], r15
0x18000e5b6  call    SclLogGenericMessage
0x18000e5bb  jmp     short loc_18000E609
0x18000e5bd  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x18000e5c1  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x18000e5c5  mov     r9d, 28h ; '('; Length
0x18000e5cb  mov     [rsp+0F0h+ShareAccess], 4; FileInformationClass
0x18000e5d3  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18000e5d7  call    cs:__imp_NtSetInformationFile
0x18000e5dd  mov     ebx, eax
0x18000e5df  test    eax, eax
0x18000e5e1  js      short loc_18000E609
0x18000e5e3  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x18000e5e7  lea     r8, [rbp+57h+var_B0]; FileInformation
0x18000e5eb  mov     r9d, 1; Length
0x18000e5f1  mov     [rsp+0F0h+ShareAccess], 0Dh; FileInformationClass
0x18000e5f9  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18000e5fd  call    cs:__imp_NtSetInformationFile
0x18000e603  mov     ebx, eax
0x18000e605  test    eax, eax
0x18000e607  jns     short loc_18000E63C
0x18000e609  mov     [rsp+0F0h+var_B8], rdi
0x18000e60e  lea     rax, aLxUnableToDele; "(%lx): Unable to delete [%ws]"
0x18000e615  mov     [rsp+0F0h+var_C0], ebx
0x18000e619  lea     r8, SclEvent_Generic_Error
0x18000e620  mov     qword ptr [rsp+0F0h+OpenOptions], rax
0x18000e625  mov     r9d, 24Dh
0x18000e62b  mov     edx, 3
0x18000e630  mov     qword ptr [rsp+0F0h+ShareAccess], r15
0x18000e635  xor     ecx, ecx
0x18000e637  call    SclLogGenericMessage
0x18000e63c  mov     rcx, [rbp+57h+FileHandle]; Handle
0x18000e640  test    rcx, rcx
0x18000e643  jz      short loc_18000E64B
0x18000e645  call    cs:__imp_NtClose
0x18000e64b  mov     eax, ebx
0x18000e64d  mov     rcx, [rbp+57h+var_28]
0x18000e651  xor     rcx, rsp; StackCookie
0x18000e654  call    __security_check_cookie
0x18000e659  add     rsp, 0D8h
0x18000e660  pop     r15
0x18000e662  pop     rdi
0x18000e663  pop     rbx
0x18000e664  pop     rbp
0x18000e665  retn
```
