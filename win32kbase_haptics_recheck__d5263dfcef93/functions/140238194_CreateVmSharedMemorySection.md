# CreateVmSharedMemorySection

- ea: `0x140238194`
- end: `0x14023838b`
- name: `CreateVmSharedMemorySection`
- size: `503`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14022f360`

## callees

- `0x140238194`
- `0x140238394`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140238346`
- `ntoskrnl!ZwClose` at `0x140238346`
- `ntoskrnl!ExFreePoolWithTag` at `0x140238360`
- `ntoskrnl!ExFreePoolWithTag` at `0x140238360`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140238370`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140238370`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140238234`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140238234`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140238268`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140238268`
- `ntoskrnl!ExAllocatePool2` at `0x14023820a`
- `ntoskrnl!ExAllocatePool2` at `0x14023820a`
- `ntoskrnl!ZwCreateSection` at `0x140238324`
- `ntoskrnl!ZwCreateSection` at `0x140238324`
- `ntoskrnl!ZwCreateFile` at `0x1402382eb`
- `ntoskrnl!ZwCreateFile` at `0x1402382eb`

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
0x140238194  push    rbp
0x140238196  push    rbx
0x140238197  push    rsi
0x140238198  push    rdi
0x140238199  lea     rbp, [rsp-2Fh]
0x14023819e  sub     rsp, 0E8h
0x1402381a5  xor     eax, eax
0x1402381a7  xorps   xmm0, xmm0
0x1402381aa  mov     [rbp+47h+FileHandle], rax
0x1402381ae  mov     rsi, rcx
0x1402381b1  mov     rcx, [r9]
0x1402381b4  xorps   xmm1, xmm1
0x1402381b7  mov     [rbp+47h+SectionHandle], rax
0x1402381bb  mov     rdi, rdx
0x1402381be  movups  xmmword ptr [rbp+47h+ObjectAttributes.ObjectName], xmm0
0x1402381c2  lea     rax, [rcx+0FFFh]
0x1402381c9  and     rax, 0FFFFFFFFFFFFF000h
0x1402381cf  mov     qword ptr [rbp+47h+var_80], rax
0x1402381d3  movups  xmmword ptr [rbp+47h+ObjectAttributes.Length], xmm0
0x1402381d7  movups  xmmword ptr [rbp+47h+ObjectAttributes+1Ch], xmm0
0x1402381db  movups  xmmword ptr [rbp+47h+IoStatusBlock], xmm0
0x1402381df  movups  xmmword ptr [rbp+47h+Source.Length], xmm1
0x1402381e3  movups  xmmword ptr [rbp+47h+Destination.Length], xmm0
0x1402381e7  test    rcx, rcx
0x1402381ea  jg      short loc_1402381F6
0x1402381ec  mov     ebx, 0C00000F2h
0x1402381f1  jmp     loc_140238352
0x1402381f6  mov     edx, 0E0h
0x1402381fb  mov     ecx, 40h ; '@'
0x140238200  mov     r8d, 6B674D53h
0x140238206  mov     [rbp+47h+Destination.MaximumLength], dx
0x14023820a  call    cs:__imp_ExAllocatePool2
0x140238211  nop     dword ptr [rax+rax+00h]
0x140238216  mov     [rbp+47h+Destination.Buffer], rax
0x14023821a  test    rax, rax
0x14023821d  jnz     short loc_140238229
0x14023821f  mov     ebx, 0C000009Ah
0x140238224  jmp     loc_14023833D
0x140238229  lea     rdx, aDeviceVmsmbVsm; "\\Device\\vmsmb\\VSMB-{dcc079ae-60ba-4d"...
0x140238230  lea     rcx, [rbp+47h+Destination]; Destination
0x140238234  call    cs:__imp_RtlAppendUnicodeToString
0x14023823b  nop     dword ptr [rax+rax+00h]
0x140238240  mov     ebx, eax
0x140238242  test    eax, eax
0x140238244  js      loc_14023833D
0x14023824a  lea     rdx, [rbp+47h+Source]
0x14023824e  mov     rcx, rdi
0x140238251  call    StringFromGuid
0x140238256  mov     ebx, eax
0x140238258  test    eax, eax
0x14023825a  js      loc_14023833D
0x140238260  lea     rdx, [rbp+47h+Source]; Source
0x140238264  lea     rcx, [rbp+47h+Destination]; Destination
0x140238268  call    cs:__imp_RtlAppendUnicodeStringToString
0x14023826f  nop     dword ptr [rax+rax+00h]
0x140238274  mov     ebx, eax
0x140238276  test    eax, eax
0x140238278  js      loc_14023833D
0x14023827e  mov     [rsp+100h+EaLength], 0; EaLength
0x140238286  lea     rax, [rbp+47h+Destination]
0x14023828a  mov     [rsp+100h+EaBuffer], 0; EaBuffer
0x140238293  lea     r9, [rbp+47h+IoStatusBlock]; IoStatusBlock
0x140238297  mov     [rsp+100h+CreateOptions], 0; CreateOptions
0x14023829f  lea     r8, [rbp+47h+ObjectAttributes]; ObjectAttributes
0x1402382a3  mov     edx, 3; DesiredAccess
0x1402382a8  mov     [rbp+47h+ObjectAttributes.ObjectName], rax
0x1402382ac  mov     [rsp+100h+CreateDisposition], edx; CreateDisposition
0x1402382b0  lea     rax, [rbp+47h+var_80]
0x1402382b4  mov     [rsp+100h+ShareAccess], 0; ShareAccess
0x1402382bc  lea     rcx, [rbp+47h+FileHandle]; FileHandle
0x1402382c0  xorps   xmm0, xmm0
0x1402382c3  mov     [rsp+100h+FileAttributes], 80h; FileAttributes
0x1402382cb  mov     [rsp+100h+AllocationSize], rax; AllocationSize
0x1402382d0  mov     [rbp+47h+ObjectAttributes.Length], 30h ; '0'
0x1402382d7  mov     [rbp+47h+ObjectAttributes.RootDirectory], 0
0x1402382df  mov     [rbp+47h+ObjectAttributes.Attributes], 40h ; '@'
0x1402382e6  movdqu  xmmword ptr [rbp+47h+ObjectAttributes.SecurityDescriptor], xmm0
0x1402382eb  call    cs:__imp_ZwCreateFile
0x1402382f2  nop     dword ptr [rax+rax+00h]
0x1402382f7  mov     ebx, eax
0x1402382f9  test    eax, eax
0x1402382fb  js      short loc_14023833D
0x1402382fd  mov     rax, [rbp+47h+FileHandle]
0x140238301  lea     rcx, [rbp+47h+SectionHandle]; SectionHandle
0x140238305  mov     qword ptr [rsp+100h+ShareAccess], rax; FileHandle
0x14023830a  xor     r9d, r9d; MaximumSize
0x14023830d  mov     [rsp+100h+FileAttributes], 8000000h; AllocationAttributes
0x140238315  xor     r8d, r8d; ObjectAttributes
0x140238318  mov     dword ptr [rsp+100h+AllocationSize], 4; SectionPageProtection
0x140238320  lea     edx, [r9+6]; DesiredAccess
0x140238324  call    cs:__imp_ZwCreateSection
0x14023832b  nop     dword ptr [rax+rax+00h]
0x140238330  mov     ebx, eax
0x140238332  test    eax, eax
0x140238334  js      short loc_14023833D
0x140238336  mov     rax, [rbp+47h+SectionHandle]
0x14023833a  mov     [rsi], rax
0x14023833d  mov     rcx, [rbp+47h+FileHandle]; Handle
0x140238341  test    rcx, rcx
0x140238344  jz      short loc_140238352
0x140238346  call    cs:__imp_ZwClose
0x14023834d  nop     dword ptr [rax+rax+00h]
0x140238352  mov     rcx, [rbp+47h+Destination.Buffer]; P
0x140238356  test    rcx, rcx
0x140238359  jz      short loc_14023836C
0x14023835b  mov     edx, 6B674D53h; Tag
0x140238360  call    cs:__imp_ExFreePoolWithTag
0x140238367  nop     dword ptr [rax+rax+00h]
0x14023836c  lea     rcx, [rbp+47h+Source]; UnicodeString
0x140238370  call    cs:__imp_RtlFreeUnicodeString
0x140238377  nop     dword ptr [rax+rax+00h]
0x14023837c  mov     eax, ebx
0x14023837e  add     rsp, 0E8h
0x140238385  pop     rdi
0x140238386  pop     rsi
0x140238387  pop     rbx
0x140238388  pop     rbp
0x140238389  retn
```
