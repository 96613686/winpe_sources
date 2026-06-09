# Smb2GetVolumeHandleFromFileHandle

- ea: `0x14008ec6c`
- end: `0x14008edab`
- name: `Smb2GetVolumeHandleFromFileHandle`
- size: `319`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140063dd4`

## callees

- `0x140038490`
- `0x14008ec6c`
- `0x14008edb4`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14008ed78`
- `ntoskrnl!ObfDereferenceObject` at `0x14009671a`
- `ntoskrnl!ObfDereferenceObject` at `0x14008ed78`
- `ntoskrnl!ObfDereferenceObject` at `0x14009671a`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14008ecd7`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14008ecd7`
- `ntoskrnl!NtOpenFile` at `0x14008ed65`
- `ntoskrnl!NtOpenFile` at `0x14008ed65`

## pseudocode

```c
void *__fastcall Smb2GetVolumeHandleFromFileHandle(void *a1)
{
  NTSTATUS VolumeName; // ebx
  PVOID Object; // [rsp+30h] [rbp-178h] BYREF
  void *FileHandle; // [rsp+38h] [rbp-170h] BYREF
  __int128 v5; // [rsp+40h] [rbp-168h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-158h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp-128h] BYREF
  char v8; // [rsp+90h] [rbp-118h] BYREF

  Object = 0;
  IoStatusBlock = 0;
  v5 = 0;
  memset(&ObjectAttributes, 0, 44);
  FileHandle = (void *)-1LL;
  if ( ObReferenceObjectByHandle(a1, 0x100020u, 0, 0, &Object, 0) < 0 )
    return 0;
  *((_QWORD *)&v5 + 1) = &v8;
  LODWORD(v5) = 0x1000000;
  VolumeName = Smb2GetVolumeName(Object, &v5);
  if ( VolumeName >= 0 )
  {
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)&v5;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    VolumeName = NtOpenFile(&FileHandle, 0, &ObjectAttributes, &IoStatusBlock, 0, 0);
  }
  ObfDereferenceObject(Object);
  if ( VolumeName < 0 )
    return 0;
  else
    return FileHandle;
}

```

## disassembly

```asm
0x14008ec6c  push    rbx
0x14008ec6e  sub     rsp, 1A0h
0x14008ec75  mov     rax, cs:__security_cookie
0x14008ec7c  xor     rax, rsp
0x14008ec7f  mov     [rsp+1A8h+var_18], rax
0x14008ec87  mov     [rsp+1A8h+var_178], 0
0x14008ec90  xorps   xmm0, xmm0
0x14008ec93  movups  xmmword ptr [rsp+1A8h+IoStatusBlock], xmm0
0x14008ec9b  xorps   xmm1, xmm1
0x14008ec9e  movups  [rsp+1A8h+var_168], xmm1
0x14008eca3  xor     eax, eax
0x14008eca5  movups  xmmword ptr [rsp+1A8h+ObjectAttributes.Length], xmm0
0x14008ecaa  movups  xmmword ptr [rsp+1A8h+ObjectAttributes.ObjectName], xmm0
0x14008ecaf  movups  xmmword ptr [rsp+1A8h+ObjectAttributes+1Ch], xmm0
0x14008ecb4  mov     [rsp+1A8h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x14008ecbd  mov     [rsp+1A8h+HandleInformation], rax; HandleInformation
0x14008ecc2  lea     rax, [rsp+1A8h+var_178]
0x14008ecc7  mov     [rsp+1A8h+Object], rax; Object
0x14008eccc  xor     r9d, r9d; AccessMode
0x14008eccf  xor     r8d, r8d; ObjectType
0x14008ecd2  mov     edx, 100020h; DesiredAccess
0x14008ecd7  call    cs:__imp_ObReferenceObjectByHandle
0x14008ecde  nop     dword ptr [rax+rax+00h]
0x14008ece3  test    eax, eax
0x14008ece5  js      loc_14008EDA7
0x14008eceb  lea     rax, [rsp+1A8h+var_118]
0x14008ecf3  mov     qword ptr [rsp+1A8h+var_168+8], rax
0x14008ecf8  mov     dword ptr [rsp+1A8h+var_168], 1000000h
0x14008ed00  lea     rdx, [rsp+1A8h+var_168]
0x14008ed05  mov     rcx, [rsp+1A8h+var_178]
0x14008ed0a  call    Smb2GetVolumeName
0x14008ed0f  mov     ebx, eax
0x14008ed11  test    eax, eax
0x14008ed13  js      short loc_14008ED73
0x14008ed15  mov     [rsp+1A8h+ObjectAttributes.Length], 30h ; '0'
0x14008ed1d  mov     [rsp+1A8h+ObjectAttributes.RootDirectory], 0
0x14008ed26  mov     [rsp+1A8h+ObjectAttributes.Attributes], 240h
0x14008ed2e  lea     rax, [rsp+1A8h+var_168]
0x14008ed33  mov     [rsp+1A8h+ObjectAttributes.ObjectName], rax
0x14008ed38  xorps   xmm0, xmm0
0x14008ed3b  movdqu  xmmword ptr [rsp+1A8h+ObjectAttributes.SecurityDescriptor], xmm0
0x14008ed41  mov     dword ptr [rsp+1A8h+HandleInformation], 0; OpenOptions
0x14008ed49  mov     dword ptr [rsp+1A8h+Object], 0; ShareAccess
0x14008ed51  lea     r9, [rsp+1A8h+IoStatusBlock]; IoStatusBlock
0x14008ed59  lea     r8, [rsp+1A8h+ObjectAttributes]; ObjectAttributes
0x14008ed5e  xor     edx, edx; DesiredAccess
0x14008ed60  lea     rcx, [rsp+1A8h+FileHandle]; FileHandle
0x14008ed65  call    cs:__imp_NtOpenFile
0x14008ed6c  nop     dword ptr [rax+rax+00h]
0x14008ed71  mov     ebx, eax
0x14008ed73  mov     rcx, [rsp+1A8h+var_178]; Object
0x14008ed78  call    cs:__imp_ObfDereferenceObject
0x14008ed7f  nop     dword ptr [rax+rax+00h]
0x14008ed84  test    ebx, ebx
0x14008ed86  js      short loc_14008EDA7
0x14008ed88  mov     rax, [rsp+1A8h+FileHandle]
0x14008ed8d  mov     rcx, [rsp+1A8h+var_18]
0x14008ed95  xor     rcx, rsp; StackCookie
0x14008ed98  call    __security_check_cookie
0x14008ed9d  add     rsp, 1A0h
0x14008eda4  pop     rbx
0x14008eda5  retn
0x14008eda7  xor     eax, eax
0x14008eda9  jmp     short loc_14008ED8D
0x14009670d  push    rbp
0x14009670f  sub     rsp, 30h
0x140096713  mov     rbp, rdx
0x140096716  mov     rcx, [rbp+30h]; Object
0x14009671a  call    cs:__imp_ObfDereferenceObject
0x140096721  nop     dword ptr [rax+rax+00h]
0x140096726  nop
0x140096727  add     rsp, 30h
0x14009672b  pop     rbp
0x14009672c  retn
```
