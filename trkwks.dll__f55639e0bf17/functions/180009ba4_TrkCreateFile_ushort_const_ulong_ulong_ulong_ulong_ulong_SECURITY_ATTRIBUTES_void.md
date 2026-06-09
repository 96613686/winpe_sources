# TrkCreateFile(ushort const *,ulong,ulong,ulong,ulong,ulong,_SECURITY_ATTRIBUTES *,void * *)

- ea: `0x180009ba4`
- end: `0x180009ce0`
- name: `?TrkCreateFile@@YAJPEBGKKKKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAX@Z`
- size: `316`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int, ULONG, ULONG, ULONG CreateDisposition, ULONG CreateOptions, struct _SECURITY_ATTRIBUTES *, void **FileHandle)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000997c`
- `0x1800099ec`
- `0x18000e8a8`

## callees

- `0x180009ba4`

## import_xrefs

- `ntdll!NtCreateFile` at `0x180009c79`
- `ntdll!NtCreateFile` at `0x180009c79`
- `ntdll!RtlFreeHeap` at `0x180009c9c`
- `ntdll!RtlFreeHeap` at `0x180009c9c`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180009bf0`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180009bf0`

## pseudocode

```c
__int64 __fastcall TrkCreateFile(
        const unsigned __int16 *a1,
        int a2,
        ULONG a3,
        ULONG a4,
        ULONG CreateDisposition,
        ULONG CreateOptions,
        struct _SECURITY_ATTRIBUTES *a7,
        void **FileHandle)
{
  PWSTR Buffer; // rdi
  ULONG v12; // ecx
  NTSTATUS v13; // ebx
  bool v15; // zf
  struct _UNICODE_STRING NtPathName; // [rsp+60h] [rbp-49h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-39h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-29h] BYREF

  *FileHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  IoStatusBlock = 0;
  NtPathName = 0;
  if ( RtlDosPathNameToNtPathName_U(a1, &NtPathName, 0, 0) )
  {
    Buffer = NtPathName.Buffer;
    v12 = 64;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    ObjectAttributes.ObjectName = &NtPathName;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( a7 )
    {
      v15 = !a7->bInheritHandle;
      ObjectAttributes.SecurityDescriptor = a7->lpSecurityDescriptor;
      if ( !v15 )
        v12 = 66;
      ObjectAttributes.Attributes = v12;
    }
    v13 = NtCreateFile(
            FileHandle,
            a2 | 0x100000,
            &ObjectAttributes,
            &IoStatusBlock,
            0,
            a3,
            a4,
            CreateDisposition,
            CreateOptions,
            0,
            0);
    if ( v13 < 0 )
      *FileHandle = 0;
    if ( Buffer )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
  }
  else
  {
    return (unsigned int)-1073741773;
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180009ba4  push    rbp
0x180009ba6  push    rbx
0x180009ba7  push    rsi
0x180009ba8  push    rdi
0x180009ba9  push    r14
0x180009bab  push    r15
0x180009bad  lea     rbp, [rsp-0Fh]
0x180009bb2  sub     rsp, 0B8h
0x180009bb9  mov     rsi, [rbp+37h+FileHandle]
0x180009bbd  xorps   xmm0, xmm0
0x180009bc0  mov     r14d, r9d
0x180009bc3  mov     r15d, r8d
0x180009bc6  mov     ebx, edx
0x180009bc8  xorps   xmm1, xmm1
0x180009bcb  xor     r9d, r9d; DirectoryInfo
0x180009bce  lea     rdx, [rbp+37h+NtPathName]; NtPathName
0x180009bd2  xor     r8d, r8d; NtFileNamePart
0x180009bd5  mov     qword ptr [rsi], 0
0x180009bdc  movups  xmmword ptr [rbp+37h+ObjectAttributes.Length], xmm0
0x180009be0  movups  xmmword ptr [rbp+37h+ObjectAttributes.ObjectName], xmm0
0x180009be4  movups  xmmword ptr [rbp+37h+ObjectAttributes.SecurityDescriptor], xmm0
0x180009be8  movups  xmmword ptr [rbp+37h+IoStatusBlock], xmm0
0x180009bec  movups  xmmword ptr [rbp+37h+NtPathName.Length], xmm1
0x180009bf0  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x180009bf6  test    al, al
0x180009bf8  jz      loc_180009CBD
0x180009bfe  mov     rdx, [rbp+37h+arg_30]
0x180009c02  lea     rax, [rbp+37h+NtPathName]
0x180009c06  mov     rdi, [rbp+37h+NtPathName.Buffer]
0x180009c0a  mov     ecx, 40h ; '@'
0x180009c0f  mov     [rbp+37h+ObjectAttributes.Length], 30h ; '0'
0x180009c16  xorps   xmm0, xmm0
0x180009c19  mov     [rbp+37h+ObjectAttributes.RootDirectory], 0
0x180009c21  mov     [rbp+37h+ObjectAttributes.Attributes], ecx
0x180009c24  mov     [rbp+37h+ObjectAttributes.ObjectName], rax
0x180009c28  movdqu  xmmword ptr [rbp+37h+ObjectAttributes.SecurityDescriptor], xmm0
0x180009c2d  test    rdx, rdx
0x180009c30  jnz     loc_180009CC4
0x180009c36  mov     eax, [rbp+37h+arg_28]
0x180009c39  lea     r9, [rbp+37h+IoStatusBlock]; IoStatusBlock
0x180009c3d  mov     [rsp+0E0h+EaLength], 0; EaLength
0x180009c45  lea     r8, [rbp+37h+ObjectAttributes]; ObjectAttributes
0x180009c49  mov     [rsp+0E0h+EaBuffer], 0; EaBuffer
0x180009c52  bts     ebx, 14h
0x180009c56  mov     [rsp+0E0h+CreateOptions], eax; CreateOptions
0x180009c5a  mov     edx, ebx; DesiredAccess
0x180009c5c  mov     eax, [rbp+37h+arg_20]
0x180009c5f  mov     rcx, rsi; FileHandle
0x180009c62  mov     [rsp+0E0h+CreateDisposition], eax; CreateDisposition
0x180009c66  mov     [rsp+0E0h+ShareAccess], r14d; ShareAccess
0x180009c6b  mov     [rsp+0E0h+FileAttributes], r15d; FileAttributes
0x180009c70  mov     [rsp+0E0h+AllocationSize], 0; AllocationSize
0x180009c79  call    cs:__imp_NtCreateFile
0x180009c7f  mov     ebx, eax
0x180009c81  test    eax, eax
0x180009c83  js      short loc_180009CB4
0x180009c85  test    rdi, rdi
0x180009c88  jz      short loc_180009CA2
0x180009c8a  mov     rcx, gs:60h
0x180009c93  mov     r8, rdi; P
0x180009c96  xor     edx, edx; Flags
0x180009c98  mov     rcx, [rcx+30h]; HeapHandle
0x180009c9c  call    cs:__imp_RtlFreeHeap
0x180009ca2  mov     eax, ebx
0x180009ca4  add     rsp, 0B8h
0x180009cab  pop     r15
0x180009cad  pop     r14
0x180009caf  pop     rdi
0x180009cb0  pop     rsi
0x180009cb1  pop     rbx
0x180009cb2  pop     rbp
0x180009cb3  retn
0x180009cb4  mov     qword ptr [rsi], 0
0x180009cbb  jmp     short loc_180009C85
0x180009cbd  mov     ebx, 0C0000033h
0x180009cc2  jmp     short loc_180009CA2
0x180009cc4  mov     rax, [rdx+8]
0x180009cc8  cmp     dword ptr [rdx+10h], 0
0x180009ccc  mov     [rbp+37h+ObjectAttributes.SecurityDescriptor], rax
0x180009cd0  mov     eax, 42h ; 'B'
0x180009cd5  cmovnz  ecx, eax
0x180009cd8  mov     [rbp+37h+ObjectAttributes.Attributes], ecx
0x180009cdb  jmp     loc_180009C36
```
