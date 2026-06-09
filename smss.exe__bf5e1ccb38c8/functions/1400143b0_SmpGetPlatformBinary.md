# SmpGetPlatformBinary

- ea: `0x1400143b0`
- end: `0x1400146a4`
- name: `SmpGetPlatformBinary`
- size: `756`
- prototype: `__int64 __fastcall(PUNICODE_STRING Destination)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14000c638`

## callees

- `0x1400143b0`
- `0x1400165fc`

## import_xrefs

- `ntdll!NtClose` at `0x14001463c`
- `ntdll!NtClose` at `0x14001463c`
- `ntdll!NtQuerySystemInformation` at `0x140014411`
- `ntdll!NtQuerySystemInformation` at `0x1400144ac`
- `ntdll!NtQuerySystemInformation` at `0x140014411`
- `ntdll!NtQuerySystemInformation` at `0x1400144ac`
- `ntdll!RtlAllocateHeap` at `0x140014458`
- `ntdll!RtlAllocateHeap` at `0x14001448e`
- `ntdll!RtlAllocateHeap` at `0x140014597`
- `ntdll!RtlAllocateHeap` at `0x140014458`
- `ntdll!RtlAllocateHeap` at `0x14001448e`
- `ntdll!RtlAllocateHeap` at `0x140014597`
- `ntdll!RtlFreeHeap` at `0x14001460e`
- `ntdll!RtlFreeHeap` at `0x14001462d`
- `ntdll!RtlFreeHeap` at `0x140014661`
- `ntdll!RtlFreeHeap` at `0x14001460e`
- `ntdll!RtlFreeHeap` at `0x14001462d`
- `ntdll!RtlFreeHeap` at `0x140014661`
- `ntdll!RtlAppendUnicodeToString` at `0x1400145c1`
- `ntdll!RtlAppendUnicodeToString` at `0x1400145d9`
- `ntdll!RtlAppendUnicodeToString` at `0x1400145e6`
- `ntdll!RtlAppendUnicodeToString` at `0x1400145c1`
- `ntdll!RtlAppendUnicodeToString` at `0x1400145d9`
- `ntdll!RtlAppendUnicodeToString` at `0x1400145e6`
- `ntdll!NtCreateFile` at `0x140014523`
- `ntdll!NtCreateFile` at `0x140014523`
- `ntdll!NtWriteFile` at `0x14001456a`
- `ntdll!NtWriteFile` at `0x14001456a`
- `ntdll!NtDeleteFile` at `0x140014670`
- `ntdll!NtDeleteFile` at `0x140014670`

## pseudocode

```c
__int64 __fastcall SmpGetPlatformBinary(PUNICODE_STRING Destination, _QWORD *a2)
{
  NTSTATUS v4; // eax
  char v6; // r14
  WCHAR *v7; // rsi
  NTSTATUS appended; // ebx
  unsigned int v9; // ebx
  WCHAR *Heap; // rax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp-29h] BYREF
  __int64 SystemInformation; // [rsp+70h] [rbp-19h] BYREF
  PVOID Buffer[2]; // [rsp+78h] [rbp-11h]
  SIZE_T Size; // [rsp+88h] [rbp-1h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp+7h] BYREF
  void *FileHandle; // [rsp+100h] [rbp+77h] BYREF
  union _LARGE_INTEGER AllocationSize; // [rsp+108h] [rbp+7Fh] BYREF

  SystemInformation = 0;
  AllocationSize.QuadPart = 0;
  FileHandle = 0;
  Size = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  *(_OWORD *)Buffer = 0;
  v4 = NtQuerySystemInformation(SystemProcessInformation|0x80, &SystemInformation, 0x20u, 0);
  if ( v4 != -1073741789 )
  {
    if ( v4 != -1073741637 )
      SmpSendPlatformBinaryStatus(1, 0, 0, 0);
    return 3221225473LL;
  }
  v6 = 0;
  v7 = 0;
  Buffer[0] = RtlAllocateHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, (unsigned int)Size);
  if ( Buffer[0] )
  {
    if ( !HIDWORD(Size)
      || (Buffer[1] = RtlAllocateHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 8u, HIDWORD(Size) + 2LL)) != 0 )
    {
      appended = NtQuerySystemInformation(SystemProcessInformation|0x80, &SystemInformation, 0x20u, 0);
      if ( appended < 0 )
        goto LABEL_19;
      AllocationSize.QuadPart = (unsigned int)Size;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)L">@";
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 0;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      appended = NtCreateFile(
                   &FileHandle,
                   0x120106u,
                   &ObjectAttributes,
                   &IoStatusBlock,
                   &AllocationSize,
                   0x80u,
                   0,
                   0,
                   0x64u,
                   0,
                   0);
      if ( appended < 0 )
      {
        FileHandle = 0;
        goto LABEL_19;
      }
      v6 = 1;
      appended = NtWriteFile(FileHandle, 0, 0, 0, &IoStatusBlock, Buffer[0], Size, 0, 0);
      if ( appended < 0 )
        goto LABEL_19;
      v9 = 22;
      if ( HIDWORD(Size) )
        v9 = HIDWORD(Size) + 24;
      Heap = (WCHAR *)RtlAllocateHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, v9);
      v7 = Heap;
      if ( Heap )
      {
        *Destination = 0;
        Destination->MaximumLength = v9;
        Destination->Buffer = Heap;
        appended = RtlAppendUnicodeToString(Destination, L"wpbbin.exe");
        if ( HIDWORD(Size) )
        {
          RtlAppendUnicodeToString(Destination, L" ");
          appended = RtlAppendUnicodeToString(Destination, (PCWSTR)Buffer[1]);
        }
        *a2 = SystemInformation;
        goto LABEL_19;
      }
    }
  }
  appended = -1073741823;
LABEL_19:
  if ( Buffer[0] )
    RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, Buffer[0]);
  if ( Buffer[1] )
    RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, Buffer[1]);
  if ( FileHandle )
    NtClose(FileHandle);
  if ( appended < 0 )
  {
    Destination->Buffer = 0;
    if ( v7 )
      RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, v7);
    if ( v6 )
      NtDeleteFile(&ObjectAttributes);
    SmpSendPlatformBinaryStatus(1, 0, 0, 0);
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x1400143b0  mov     [rsp-8+arg_0], rbx
0x1400143b5  mov     [rsp-8+arg_8], rsi
0x1400143ba  push    rbp
0x1400143bb  push    rdi
0x1400143bc  push    r12
0x1400143be  push    r14
0x1400143c0  push    r15
0x1400143c2  lea     rbp, [rsp-37h]
0x1400143c7  sub     rsp, 0C0h
0x1400143ce  xorps   xmm0, xmm0
0x1400143d1  xor     r12d, r12d
0x1400143d4  xor     eax, eax
0x1400143d6  mov     [rbp+57h+SystemInformation], r12
0x1400143da  mov     r15, rdx
0x1400143dd  mov     qword ptr [rbp+57h+arg_18], r12
0x1400143e1  mov     rdi, rcx
0x1400143e4  mov     [rbp+57h+FileHandle], r12
0x1400143e8  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1400143ec  lea     ebx, [rax+20h]
0x1400143ef  mov     [rbp+57h+Size], r12
0x1400143f3  mov     r8d, ebx; SystemInformationLength
0x1400143f6  lea     ecx, [rbx+65h]; SystemInformationClass
0x1400143f9  xor     r9d, r9d; ReturnLength
0x1400143fc  lea     rdx, [rbp+57h+SystemInformation]; SystemInformation
0x140014400  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x140014404  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140014408  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x14001440c  movdqu  xmmword ptr [rbp+57h+Buffer], xmm0
0x140014411  call    cs:__imp_NtQuerySystemInformation
0x140014417  cmp     eax, 0C0000023h
0x14001441c  jz      short loc_14001443F
0x14001441e  cmp     eax, 0C00000BBh
0x140014423  jz      short loc_140014435
0x140014425  xor     r9d, r9d
0x140014428  lea     ecx, [rbx-1Fh]
0x14001442b  xor     r8d, r8d
0x14001442e  xor     edx, edx
0x140014430  call    SmpSendPlatformBinaryStatus
0x140014435  mov     eax, 0C0000001h
0x14001443a  jmp     loc_140014688
0x14001443f  mov     rcx, gs:60h
0x140014448  xor     edx, edx; Flags
0x14001444a  mov     r8d, dword ptr [rbp+57h+Size]; Size
0x14001444e  mov     r14b, r12b
0x140014451  mov     rsi, r12
0x140014454  mov     rcx, [rcx+30h]; HeapHandle
0x140014458  call    cs:__imp_RtlAllocateHeap
0x14001445e  mov     [rbp+57h+Buffer], rax
0x140014462  test    rax, rax
0x140014465  jnz     short loc_140014471
0x140014467  mov     ebx, 0C0000001h
0x14001446c  jmp     loc_1400145F5
0x140014471  mov     eax, dword ptr [rbp+57h+Size+4]
0x140014474  test    eax, eax
0x140014476  jz      short loc_14001449D
0x140014478  mov     rcx, gs:60h
0x140014481  lea     r8, [rax+2]; Size
0x140014485  mov     edx, 8; Flags
0x14001448a  mov     rcx, [rcx+30h]; HeapHandle
0x14001448e  call    cs:__imp_RtlAllocateHeap
0x140014494  mov     [rbp+57h+Buffer+8], rax
0x140014498  test    rax, rax
0x14001449b  jz      short loc_140014467
0x14001449d  xor     r9d, r9d; ReturnLength
0x1400144a0  lea     rdx, [rbp+57h+SystemInformation]; SystemInformation
0x1400144a4  mov     r8d, ebx; SystemInformationLength
0x1400144a7  mov     ecx, 85h; SystemInformationClass
0x1400144ac  call    cs:__imp_NtQuerySystemInformation
0x1400144b2  mov     ebx, eax
0x1400144b4  test    eax, eax
0x1400144b6  js      loc_1400145F5
0x1400144bc  mov     eax, dword ptr [rbp+57h+Size]
0x1400144bf  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1400144c3  mov     [rsp+0E0h+EaLength], r12d; EaLength
0x1400144c8  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400144cc  mov     [rsp+0E0h+EaBuffer], r12; EaBuffer
0x1400144d1  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1400144d5  mov     [rsp+0E0h+CreateOptions], 64h ; 'd'; CreateOptions
0x1400144dd  xorps   xmm0, xmm0
0x1400144e0  mov     qword ptr [rbp+57h+arg_18], rax
0x1400144e4  mov     edx, 120106h; DesiredAccess
0x1400144e9  mov     [rsp+0E0h+CreateDisposition], r12d; CreateDisposition
0x1400144ee  lea     rax, SmpPlatformBinaryName; ">@"
0x1400144f5  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400144f9  lea     rax, [rbp+57h+arg_18]
0x1400144fd  mov     [rsp+0E0h+ShareAccess], r12d; ShareAccess
0x140014502  mov     [rsp+0E0h+FileAttributes], 80h; FileAttributes
0x14001450a  mov     [rsp+0E0h+AllocationSize], rax; AllocationSize
0x14001450f  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140014516  mov     [rbp+57h+ObjectAttributes.RootDirectory], r12
0x14001451a  mov     [rbp+57h+ObjectAttributes.Attributes], r12d
0x14001451e  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140014523  call    cs:__imp_NtCreateFile
0x140014529  mov     ebx, eax
0x14001452b  test    eax, eax
0x14001452d  jns     short loc_140014538
0x14001452f  mov     [rbp+57h+FileHandle], r12
0x140014533  jmp     loc_1400145F5
0x140014538  mov     eax, dword ptr [rbp+57h+Size]
0x14001453b  xor     r9d, r9d; ApcContext
0x14001453e  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x140014542  xor     r8d, r8d; ApcRoutine
0x140014545  mov     qword ptr [rsp+0E0h+CreateOptions], r12; Key
0x14001454a  xor     edx, edx; Event
0x14001454c  mov     qword ptr [rsp+0E0h+CreateDisposition], r12; ByteOffset
0x140014551  mov     r14b, 1
0x140014554  mov     [rsp+0E0h+ShareAccess], eax; Length
0x140014558  mov     rax, [rbp+57h+Buffer]
0x14001455c  mov     qword ptr [rsp+0E0h+FileAttributes], rax; Buffer
0x140014561  lea     rax, [rbp+57h+IoStatusBlock]
0x140014565  mov     [rsp+0E0h+AllocationSize], rax; IoStatusBlock
0x14001456a  call    cs:__imp_NtWriteFile
0x140014570  mov     ebx, eax
0x140014572  test    eax, eax
0x140014574  js      short loc_1400145F5
0x140014576  mov     eax, dword ptr [rbp+57h+Size+4]
0x140014579  mov     ebx, 16h
0x14001457e  test    eax, eax
0x140014580  jz      short loc_140014585
0x140014582  lea     ebx, [rax+18h]
0x140014585  mov     rcx, gs:60h
0x14001458e  xor     edx, edx; Flags
0x140014590  mov     r8d, ebx; Size
0x140014593  mov     rcx, [rcx+30h]; HeapHandle
0x140014597  call    cs:__imp_RtlAllocateHeap
0x14001459d  mov     rsi, rax
0x1400145a0  test    rax, rax
0x1400145a3  jz      loc_140014467
0x1400145a9  xorps   xmm0, xmm0
0x1400145ac  lea     rdx, aWpbbinExe; "wpbbin.exe"
0x1400145b3  movups  xmmword ptr [rdi], xmm0
0x1400145b6  mov     rcx, rdi; Destination
0x1400145b9  mov     [rdi+2], bx
0x1400145bd  mov     [rdi+8], rax
0x1400145c1  call    cs:__imp_RtlAppendUnicodeToString
0x1400145c7  mov     ebx, eax
0x1400145c9  cmp     dword ptr [rbp+57h+Size+4], r12d
0x1400145cd  jbe     short loc_1400145EE
0x1400145cf  lea     rdx, Source; " "
0x1400145d6  mov     rcx, rdi; Destination
0x1400145d9  call    cs:__imp_RtlAppendUnicodeToString
0x1400145df  mov     rdx, [rbp+57h+Buffer+8]; Source
0x1400145e3  mov     rcx, rdi; Destination
0x1400145e6  call    cs:__imp_RtlAppendUnicodeToString
0x1400145ec  mov     ebx, eax
0x1400145ee  mov     rax, [rbp+57h+SystemInformation]
0x1400145f2  mov     [r15], rax
0x1400145f5  cmp     [rbp+57h+Buffer], r12
0x1400145f9  jz      short loc_140014614
0x1400145fb  mov     rcx, gs:60h
0x140014604  xor     edx, edx; Flags
0x140014606  mov     r8, [rbp+57h+Buffer]; BaseAddress
0x14001460a  mov     rcx, [rcx+30h]; HeapHandle
0x14001460e  call    cs:__imp_RtlFreeHeap
0x140014614  cmp     [rbp+57h+Buffer+8], r12
0x140014618  jz      short loc_140014633
0x14001461a  mov     rcx, gs:60h
0x140014623  xor     edx, edx; Flags
0x140014625  mov     r8, [rbp+57h+Buffer+8]; BaseAddress
0x140014629  mov     rcx, [rcx+30h]; HeapHandle
0x14001462d  call    cs:__imp_RtlFreeHeap
0x140014633  mov     rcx, [rbp+57h+FileHandle]; Handle
0x140014637  test    rcx, rcx
0x14001463a  jz      short loc_140014642
0x14001463c  call    cs:__imp_NtClose
0x140014642  test    ebx, ebx
0x140014644  jns     short loc_140014686
0x140014646  mov     [rdi+8], r12
0x14001464a  test    rsi, rsi
0x14001464d  jz      short loc_140014667
0x14001464f  mov     rcx, gs:60h
0x140014658  mov     r8, rsi; BaseAddress
0x14001465b  xor     edx, edx; Flags
0x14001465d  mov     rcx, [rcx+30h]; HeapHandle
0x140014661  call    cs:__imp_RtlFreeHeap
0x140014667  test    r14b, r14b
0x14001466a  jz      short loc_140014676
0x14001466c  lea     rcx, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140014670  call    cs:__imp_NtDeleteFile
0x140014676  xor     edx, edx
0x140014678  xor     r9d, r9d
0x14001467b  xor     r8d, r8d
0x14001467e  lea     ecx, [rdx+1]
0x140014681  call    SmpSendPlatformBinaryStatus
0x140014686  mov     eax, ebx
0x140014688  lea     r11, [rsp+0E0h+var_20]
0x140014690  mov     rbx, [r11+30h]
0x140014694  mov     rsi, [r11+38h]
0x140014698  mov     rsp, r11
0x14001469b  pop     r15
0x14001469d  pop     r14
0x14001469f  pop     r12
0x1400146a1  pop     rdi
0x1400146a2  pop     rbp
0x1400146a3  retn
```
