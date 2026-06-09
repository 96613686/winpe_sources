# CreateVmSharedMemorySection

- ea: `0x140237f64`
- end: `0x14023815b`
- name: `CreateVmSharedMemorySection`
- size: `503`
- prototype: `__int64 __fastcall(void **, __int64, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14022f3f0`

## callees

- `0x140237f64`
- `0x140238164`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140238116`
- `ntoskrnl!ZwClose` at `0x140238116`
- `ntoskrnl!ExFreePoolWithTag` at `0x140238130`
- `ntoskrnl!ExFreePoolWithTag` at `0x140238130`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140238140`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140238140`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140238004`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140238004`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140238038`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140238038`
- `ntoskrnl!ExAllocatePool2` at `0x140237fda`
- `ntoskrnl!ExAllocatePool2` at `0x140237fda`
- `ntoskrnl!ZwCreateSection` at `0x1402380f4`
- `ntoskrnl!ZwCreateSection` at `0x1402380f4`
- `ntoskrnl!ZwCreateFile` at `0x1402380bb`
- `ntoskrnl!ZwCreateFile` at `0x1402380bb`

## pseudocode

```c
__int64 __fastcall CreateVmSharedMemorySection(void **a1, __int64 a2, __int64 a3, __int64 *a4)
{
  __int64 v5; // rcx
  NTSTATUS appended; // ebx
  void *FileHandle; // [rsp+60h] [rbp-59h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+68h] [rbp-51h] BYREF
  void *SectionHandle; // [rsp+78h] [rbp-41h] BYREF
  union _LARGE_INTEGER AllocationSize; // [rsp+80h] [rbp-39h] BYREF
  UNICODE_STRING Source; // [rsp+88h] [rbp-31h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+98h] [rbp-21h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+C8h] [rbp+Fh] BYREF

  FileHandle = 0;
  v5 = *a4;
  SectionHandle = 0;
  AllocationSize.QuadPart = (v5 + 4095) & 0xFFFFFFFFFFFFF000uLL;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  Source = 0;
  Destination = 0;
  if ( v5 > 0 )
  {
    Destination.MaximumLength = 224;
    Destination.Buffer = (PWSTR)ExAllocatePool2(64, 224, 1801932115);
    if ( Destination.Buffer )
    {
      appended = RtlAppendUnicodeToString(
                   &Destination,
                   L"\\Device\\vmsmb\\VSMB-{dcc079ae-60ba-4d07-847c-3493609c0870}\\SharedMemory$\\");
      if ( appended >= 0 )
      {
        appended = StringFromGuid(a2, &Source);
        if ( appended >= 0 )
        {
          appended = RtlAppendUnicodeStringToString(&Destination, &Source);
          if ( appended >= 0 )
          {
            ObjectAttributes.ObjectName = &Destination;
            ObjectAttributes.Length = 48;
            ObjectAttributes.RootDirectory = 0;
            ObjectAttributes.Attributes = 64;
            *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
            appended = ZwCreateFile(
                         &FileHandle,
                         3u,
                         &ObjectAttributes,
                         &IoStatusBlock,
                         &AllocationSize,
                         0x80u,
                         0,
                         3u,
                         0,
                         0,
                         0);
            if ( appended >= 0 )
            {
              appended = ZwCreateSection(&SectionHandle, 6u, 0, 0, 4u, 0x8000000u, FileHandle);
              if ( appended >= 0 )
                *a1 = SectionHandle;
            }
          }
        }
      }
    }
    else
    {
      appended = -1073741670;
    }
    if ( FileHandle )
      ZwClose(FileHandle);
  }
  else
  {
    appended = -1073741582;
  }
  if ( Destination.Buffer )
    ExFreePoolWithTag(Destination.Buffer, 0x6B674D53u);
  RtlFreeUnicodeString(&Source);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x140237f64  push    rbp
0x140237f66  push    rbx
0x140237f67  push    rsi
0x140237f68  push    rdi
0x140237f69  lea     rbp, [rsp-2Fh]
0x140237f6e  sub     rsp, 0E8h
0x140237f75  xor     eax, eax
0x140237f77  xorps   xmm0, xmm0
0x140237f7a  mov     [rbp+47h+FileHandle], rax
0x140237f7e  mov     rsi, rcx
0x140237f81  mov     rcx, [r9]
0x140237f84  xorps   xmm1, xmm1
0x140237f87  mov     [rbp+47h+SectionHandle], rax
0x140237f8b  mov     rdi, rdx
0x140237f8e  movups  xmmword ptr [rbp+47h+ObjectAttributes.ObjectName], xmm0
0x140237f92  lea     rax, [rcx+0FFFh]
0x140237f99  and     rax, 0FFFFFFFFFFFFF000h
0x140237f9f  mov     qword ptr [rbp+47h+var_80], rax
0x140237fa3  movups  xmmword ptr [rbp+47h+ObjectAttributes.Length], xmm0
0x140237fa7  movups  xmmword ptr [rbp+47h+ObjectAttributes+1Ch], xmm0
0x140237fab  movups  xmmword ptr [rbp+47h+IoStatusBlock], xmm0
0x140237faf  movups  xmmword ptr [rbp+47h+Source.Length], xmm1
0x140237fb3  movups  xmmword ptr [rbp+47h+Destination.Length], xmm0
0x140237fb7  test    rcx, rcx
0x140237fba  jg      short loc_140237FC6
0x140237fbc  mov     ebx, 0C00000F2h
0x140237fc1  jmp     loc_140238122
0x140237fc6  mov     edx, 0E0h
0x140237fcb  mov     ecx, 40h ; '@'
0x140237fd0  mov     r8d, 6B674D53h
0x140237fd6  mov     [rbp+47h+Destination.MaximumLength], dx
0x140237fda  call    cs:__imp_ExAllocatePool2
0x140237fe1  nop     dword ptr [rax+rax+00h]
0x140237fe6  mov     [rbp+47h+Destination.Buffer], rax
0x140237fea  test    rax, rax
0x140237fed  jnz     short loc_140237FF9
0x140237fef  mov     ebx, 0C000009Ah
0x140237ff4  jmp     loc_14023810D
0x140237ff9  lea     rdx, aDeviceVmsmbVsm; "\\Device\\vmsmb\\VSMB-{dcc079ae-60ba-4d"...
0x140238000  lea     rcx, [rbp+47h+Destination]; Destination
0x140238004  call    cs:__imp_RtlAppendUnicodeToString
0x14023800b  nop     dword ptr [rax+rax+00h]
0x140238010  mov     ebx, eax
0x140238012  test    eax, eax
0x140238014  js      loc_14023810D
0x14023801a  lea     rdx, [rbp+47h+Source]
0x14023801e  mov     rcx, rdi
0x140238021  call    StringFromGuid
0x140238026  mov     ebx, eax
0x140238028  test    eax, eax
0x14023802a  js      loc_14023810D
0x140238030  lea     rdx, [rbp+47h+Source]; Source
0x140238034  lea     rcx, [rbp+47h+Destination]; Destination
0x140238038  call    cs:__imp_RtlAppendUnicodeStringToString
0x14023803f  nop     dword ptr [rax+rax+00h]
0x140238044  mov     ebx, eax
0x140238046  test    eax, eax
0x140238048  js      loc_14023810D
0x14023804e  mov     [rsp+100h+EaLength], 0; EaLength
0x140238056  lea     rax, [rbp+47h+Destination]
0x14023805a  mov     [rsp+100h+EaBuffer], 0; EaBuffer
0x140238063  lea     r9, [rbp+47h+IoStatusBlock]; IoStatusBlock
0x140238067  mov     [rsp+100h+CreateOptions], 0; CreateOptions
0x14023806f  lea     r8, [rbp+47h+ObjectAttributes]; ObjectAttributes
0x140238073  mov     edx, 3; DesiredAccess
0x140238078  mov     [rbp+47h+ObjectAttributes.ObjectName], rax
0x14023807c  mov     [rsp+100h+CreateDisposition], edx; CreateDisposition
0x140238080  lea     rax, [rbp+47h+var_80]
0x140238084  mov     [rsp+100h+ShareAccess], 0; ShareAccess
0x14023808c  lea     rcx, [rbp+47h+FileHandle]; FileHandle
0x140238090  xorps   xmm0, xmm0
0x140238093  mov     [rsp+100h+FileAttributes], 80h; FileAttributes
0x14023809b  mov     [rsp+100h+AllocationSize], rax; AllocationSize
0x1402380a0  mov     [rbp+47h+ObjectAttributes.Length], 30h ; '0'
0x1402380a7  mov     [rbp+47h+ObjectAttributes.RootDirectory], 0
0x1402380af  mov     [rbp+47h+ObjectAttributes.Attributes], 40h ; '@'
0x1402380b6  movdqu  xmmword ptr [rbp+47h+ObjectAttributes.SecurityDescriptor], xmm0
0x1402380bb  call    cs:__imp_ZwCreateFile
0x1402380c2  nop     dword ptr [rax+rax+00h]
0x1402380c7  mov     ebx, eax
0x1402380c9  test    eax, eax
0x1402380cb  js      short loc_14023810D
0x1402380cd  mov     rax, [rbp+47h+FileHandle]
0x1402380d1  lea     rcx, [rbp+47h+SectionHandle]; SectionHandle
0x1402380d5  mov     qword ptr [rsp+100h+ShareAccess], rax; FileHandle
0x1402380da  xor     r9d, r9d; MaximumSize
0x1402380dd  mov     [rsp+100h+FileAttributes], 8000000h; AllocationAttributes
0x1402380e5  xor     r8d, r8d; ObjectAttributes
0x1402380e8  mov     dword ptr [rsp+100h+AllocationSize], 4; SectionPageProtection
0x1402380f0  lea     edx, [r9+6]; DesiredAccess
0x1402380f4  call    cs:__imp_ZwCreateSection
0x1402380fb  nop     dword ptr [rax+rax+00h]
0x140238100  mov     ebx, eax
0x140238102  test    eax, eax
0x140238104  js      short loc_14023810D
0x140238106  mov     rax, [rbp+47h+SectionHandle]
0x14023810a  mov     [rsi], rax
0x14023810d  mov     rcx, [rbp+47h+FileHandle]; Handle
0x140238111  test    rcx, rcx
0x140238114  jz      short loc_140238122
0x140238116  call    cs:__imp_ZwClose
0x14023811d  nop     dword ptr [rax+rax+00h]
0x140238122  mov     rcx, [rbp+47h+Destination.Buffer]; P
0x140238126  test    rcx, rcx
0x140238129  jz      short loc_14023813C
0x14023812b  mov     edx, 6B674D53h; Tag
0x140238130  call    cs:__imp_ExFreePoolWithTag
0x140238137  nop     dword ptr [rax+rax+00h]
0x14023813c  lea     rcx, [rbp+47h+Source]; UnicodeString
0x140238140  call    cs:__imp_RtlFreeUnicodeString
0x140238147  nop     dword ptr [rax+rax+00h]
0x14023814c  mov     eax, ebx
0x14023814e  add     rsp, 0E8h
0x140238155  pop     rdi
0x140238156  pop     rsi
0x140238157  pop     rbx
0x140238158  pop     rbp
0x140238159  retn
```
