# Smb2GetVolumeHandleFromFileHandle

- ea: `0x14008ec1c`
- end: `0x14008ed5b`
- name: `Smb2GetVolumeHandleFromFileHandle`
- size: `319`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140063d84`

## callees

- `0x140038490`
- `0x14008ec1c`
- `0x14008ed64`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14008ed28`
- `ntoskrnl!ObfDereferenceObject` at `0x1400966ca`
- `ntoskrnl!ObfDereferenceObject` at `0x14008ed28`
- `ntoskrnl!ObfDereferenceObject` at `0x1400966ca`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14008ec87`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14008ec87`
- `ntoskrnl!NtOpenFile` at `0x14008ed15`
- `ntoskrnl!NtOpenFile` at `0x14008ed15`

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
0x14008ec1c  push    rbx
0x14008ec1e  sub     rsp, 1A0h
0x14008ec25  mov     rax, cs:__security_cookie
0x14008ec2c  xor     rax, rsp
0x14008ec2f  mov     [rsp+1A8h+var_18], rax
0x14008ec37  mov     [rsp+1A8h+var_178], 0
0x14008ec40  xorps   xmm0, xmm0
0x14008ec43  movups  xmmword ptr [rsp+1A8h+IoStatusBlock], xmm0
0x14008ec4b  xorps   xmm1, xmm1
0x14008ec4e  movups  [rsp+1A8h+var_168], xmm1
0x14008ec53  xor     eax, eax
0x14008ec55  movups  xmmword ptr [rsp+1A8h+ObjectAttributes.Length], xmm0
0x14008ec5a  movups  xmmword ptr [rsp+1A8h+ObjectAttributes.ObjectName], xmm0
0x14008ec5f  movups  xmmword ptr [rsp+1A8h+ObjectAttributes+1Ch], xmm0
0x14008ec64  mov     [rsp+1A8h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x14008ec6d  mov     [rsp+1A8h+HandleInformation], rax; HandleInformation
0x14008ec72  lea     rax, [rsp+1A8h+var_178]
0x14008ec77  mov     [rsp+1A8h+Object], rax; Object
0x14008ec7c  xor     r9d, r9d; AccessMode
0x14008ec7f  xor     r8d, r8d; ObjectType
0x14008ec82  mov     edx, 100020h; DesiredAccess
0x14008ec87  call    cs:__imp_ObReferenceObjectByHandle
0x14008ec8e  nop     dword ptr [rax+rax+00h]
0x14008ec93  test    eax, eax
0x14008ec95  js      loc_14008ED57
0x14008ec9b  lea     rax, [rsp+1A8h+var_118]
0x14008eca3  mov     qword ptr [rsp+1A8h+var_168+8], rax
0x14008eca8  mov     dword ptr [rsp+1A8h+var_168], 1000000h
0x14008ecb0  lea     rdx, [rsp+1A8h+var_168]
0x14008ecb5  mov     rcx, [rsp+1A8h+var_178]
0x14008ecba  call    Smb2GetVolumeName
0x14008ecbf  mov     ebx, eax
0x14008ecc1  test    eax, eax
0x14008ecc3  js      short loc_14008ED23
0x14008ecc5  mov     [rsp+1A8h+ObjectAttributes.Length], 30h ; '0'
0x14008eccd  mov     [rsp+1A8h+ObjectAttributes.RootDirectory], 0
0x14008ecd6  mov     [rsp+1A8h+ObjectAttributes.Attributes], 240h
0x14008ecde  lea     rax, [rsp+1A8h+var_168]
0x14008ece3  mov     [rsp+1A8h+ObjectAttributes.ObjectName], rax
0x14008ece8  xorps   xmm0, xmm0
0x14008eceb  movdqu  xmmword ptr [rsp+1A8h+ObjectAttributes.SecurityDescriptor], xmm0
0x14008ecf1  mov     dword ptr [rsp+1A8h+HandleInformation], 0; OpenOptions
0x14008ecf9  mov     dword ptr [rsp+1A8h+Object], 0; ShareAccess
0x14008ed01  lea     r9, [rsp+1A8h+IoStatusBlock]; IoStatusBlock
0x14008ed09  lea     r8, [rsp+1A8h+ObjectAttributes]; ObjectAttributes
0x14008ed0e  xor     edx, edx; DesiredAccess
0x14008ed10  lea     rcx, [rsp+1A8h+FileHandle]; FileHandle
0x14008ed15  call    cs:__imp_NtOpenFile
0x14008ed1c  nop     dword ptr [rax+rax+00h]
0x14008ed21  mov     ebx, eax
0x14008ed23  mov     rcx, [rsp+1A8h+var_178]; Object
0x14008ed28  call    cs:__imp_ObfDereferenceObject
0x14008ed2f  nop     dword ptr [rax+rax+00h]
0x14008ed34  test    ebx, ebx
0x14008ed36  js      short loc_14008ED57
0x14008ed38  mov     rax, [rsp+1A8h+FileHandle]
0x14008ed3d  mov     rcx, [rsp+1A8h+var_18]
0x14008ed45  xor     rcx, rsp; StackCookie
0x14008ed48  call    __security_check_cookie
0x14008ed4d  add     rsp, 1A0h
0x14008ed54  pop     rbx
0x14008ed55  retn
0x14008ed57  xor     eax, eax
0x14008ed59  jmp     short loc_14008ED3D
0x1400966bd  push    rbp
0x1400966bf  sub     rsp, 30h
0x1400966c3  mov     rbp, rdx
0x1400966c6  mov     rcx, [rbp+30h]; Object
0x1400966ca  call    cs:__imp_ObfDereferenceObject
0x1400966d1  nop     dword ptr [rax+rax+00h]
0x1400966d6  nop
0x1400966d7  add     rsp, 30h
0x1400966db  pop     rbp
0x1400966dc  retn
```
