# NtFilterLoad

- ea: `0x1400ec3b4`
- end: `0x1400ec5af`
- name: `NtFilterLoad`
- size: `507`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x1400ecb4c`

## callees

- `0x1400ec074`
- `0x1400ec3b4`
- `0x1400ecc94`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1400ec574`
- `ntdll!RtlFreeHeap` at `0x1400ec596`
- `ntdll!RtlFreeHeap` at `0x1400fcfe7`
- `ntdll!RtlFreeHeap` at `0x1400fd008`
- `ntdll!RtlFreeHeap` at `0x1400ec574`
- `ntdll!RtlFreeHeap` at `0x1400ec596`
- `ntdll!RtlFreeHeap` at `0x1400fcfe7`
- `ntdll!RtlFreeHeap` at `0x1400fd008`
- `ntdll!RtlAllocateHeap` at `0x1400ec4df`
- `ntdll!RtlAllocateHeap` at `0x1400ec4df`
- `ntdll!NtCreateFile` at `0x1400ec4ae`
- `ntdll!NtCreateFile` at `0x1400ec4ae`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1400ec3e9`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1400ec3e9`
- `ntdll!NtClose` at `0x1400ec557`
- `ntdll!NtClose` at `0x1400fcfc8`
- `ntdll!NtClose` at `0x1400ec557`
- `ntdll!NtClose` at `0x1400fcfc8`

## pseudocode

```c
__int64 NtFilterLoad()
{
  void *v0; // rbx
  unsigned int v1; // edi
  unsigned int v2; // eax
  unsigned int v3; // eax
  char *Heap; // rax
  int AllocationSize; // [rsp+20h] [rbp-A8h]
  ULONG FileAttributes; // [rsp+28h] [rbp-A0h]
  struct _UNICODE_STRING v8; // [rsp+68h] [rbp-60h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+78h] [rbp-50h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-40h] BYREF
  __int64 v11; // [rsp+D0h] [rbp+8h] BYREF
  void *FileHandle; // [rsp+D8h] [rbp+10h] BYREF

  FileHandle = (void *)-1LL;
  v0 = 0;
  v8 = 0;
  if ( !RtlDosPathNameToNtPathName_U(L"\\\\.\\FltMgr", &v8, 0, 0) )
  {
    v1 = -2147024893;
    goto LABEL_9;
  }
  *(&ObjectAttributes.Length + 1) = 0;
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &v8;
  IoStatusBlock = 0;
  v2 = NtCreateFile(&FileHandle, 0x120116u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 2u, 1u, 0, 0, 0);
  if ( FileHandle == (void *)-1LL )
  {
    v3 = FilterHResultFromNtStatus(v2);
  }
  else
  {
    Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x10u);
    v0 = Heap;
    if ( !Heap )
    {
      v1 = -2147024882;
      goto LABEL_9;
    }
    *(_WORD *)Heap = 14;
    *(_QWORD *)(Heap + 2) = *(_QWORD *)L"bindflt";
    *(_DWORD *)(Heap + 10) = *(_DWORD *)L"flt";
    *((_WORD *)Heap + 7) = aBindflt[6];
    v3 = NtFilterpDeviceIoControl(FileHandle, 0x88004u, AllocationSize, FileAttributes, (__int64)&v11);
  }
  v1 = v3;
LABEL_9:
  if ( FileHandle != (void *)-1LL )
    NtClose(FileHandle);
  if ( v0 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v0);
  if ( v8.Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8.Buffer);
  return v1;
}

```

## disassembly

```asm
0x1400ec3b4  mov     rax, rsp
0x1400ec3b7  mov     [rax+18h], rbx
0x1400ec3bb  push    rdi
0x1400ec3bc  sub     rsp, 0C0h
0x1400ec3c3  mov     qword ptr [rax+10h], 0FFFFFFFFFFFFFFFFh
0x1400ec3cb  xor     ebx, ebx
0x1400ec3cd  mov     [rax-68h], rbx
0x1400ec3d1  xorps   xmm0, xmm0
0x1400ec3d4  movups  xmmword ptr [rax-60h], xmm0
0x1400ec3d8  xor     r9d, r9d; DirectoryInfo
0x1400ec3db  xor     r8d, r8d; NtFileNamePart
0x1400ec3de  lea     rdx, [rax-60h]; NtPathName
0x1400ec3e2  lea     rcx, DosPathName; "\\\\.\\FltMgr"
0x1400ec3e9  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x1400ec3ef  test    al, al
0x1400ec3f1  jnz     short loc_1400EC3FD
0x1400ec3f3  mov     edi, 80070003h
0x1400ec3f8  jmp     loc_1400EC549
0x1400ec3fd  xor     eax, eax
0x1400ec3ff  mov     dword ptr [rsp+0C8h+ObjectAttributes+4], eax
0x1400ec406  xorps   xmm0, xmm0
0x1400ec409  movups  xmmword ptr [rsp+0C8h+ObjectAttributes.Length], xmm0
0x1400ec411  movups  xmmword ptr [rsp+0C8h+ObjectAttributes.ObjectName], xmm0
0x1400ec419  movups  xmmword ptr [rsp+0C8h+ObjectAttributes+1Ch], xmm0
0x1400ec421  mov     [rsp+0C8h+ObjectAttributes.Length], 30h ; '0'
0x1400ec42c  mov     [rsp+0C8h+ObjectAttributes.RootDirectory], rax
0x1400ec434  mov     [rsp+0C8h+ObjectAttributes.Attributes], 40h ; '@'
0x1400ec43f  lea     rax, [rsp+0C8h+var_60]
0x1400ec444  mov     [rsp+0C8h+ObjectAttributes.ObjectName], rax
0x1400ec44c  movdqu  xmmword ptr [rsp+0C8h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400ec455  movups  xmmword ptr [rsp+0C8h+IoStatusBlock], xmm0
0x1400ec45a  mov     [rsp+0C8h+EaLength], 0; EaLength
0x1400ec462  mov     [rsp+0C8h+EaBuffer], 0; EaBuffer
0x1400ec46b  mov     [rsp+0C8h+CreateOptions], 0; CreateOptions
0x1400ec473  mov     [rsp+0C8h+CreateDisposition], 1; CreateDisposition
0x1400ec47b  mov     [rsp+0C8h+ShareAccess], 2; ShareAccess
0x1400ec483  mov     [rsp+0C8h+FileAttributes], 80h; int
0x1400ec48b  mov     [rsp+0C8h+AllocationSize], 0; int
0x1400ec494  lea     r9, [rsp+0C8h+IoStatusBlock]; IoStatusBlock
0x1400ec499  lea     r8, [rsp+0C8h+ObjectAttributes]; ObjectAttributes
0x1400ec4a1  mov     edx, 120116h; DesiredAccess
0x1400ec4a6  lea     rcx, [rsp+0C8h+FileHandle]; FileHandle
0x1400ec4ae  call    cs:__imp_NtCreateFile
0x1400ec4b4  cmp     [rsp+0C8h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x1400ec4bd  jnz     short loc_1400EC4C8
0x1400ec4bf  mov     ecx, eax
0x1400ec4c1  call    FilterHResultFromNtStatus
0x1400ec4c6  jmp     short loc_1400EC547
0x1400ec4c8  mov     rcx, gs:60h
0x1400ec4d1  mov     edi, 10h
0x1400ec4d6  mov     r8d, edi; Size
0x1400ec4d9  xor     edx, edx; Flags
0x1400ec4db  mov     rcx, [rcx+30h]; HeapHandle
0x1400ec4df  call    cs:__imp_RtlAllocateHeap
0x1400ec4e5  mov     rbx, rax
0x1400ec4e8  mov     [rsp+0C8h+var_68], rax
0x1400ec4ed  test    rax, rax
0x1400ec4f0  jnz     short loc_1400EC4F9
0x1400ec4f2  mov     edi, 8007000Eh
0x1400ec4f7  jmp     short loc_1400EC549
0x1400ec4f9  mov     eax, 0Eh
0x1400ec4fe  mov     [rbx], ax
0x1400ec501  movsd   xmm0, qword ptr cs:aBindflt; "bindflt"
0x1400ec509  movsd   qword ptr [rbx+2], xmm0
0x1400ec50e  mov     eax, dword ptr cs:aBindflt+8; "flt"
0x1400ec514  mov     [rbx+0Ah], eax
0x1400ec517  movzx   eax, word ptr cs:aBindflt+0Ch; "t"
0x1400ec51e  mov     [rbx+0Eh], ax
0x1400ec522  lea     rax, [rsp+0C8h+arg_0]
0x1400ec52a  mov     qword ptr [rsp+0C8h+ShareAccess], rax; __int64
0x1400ec52f  mov     r9d, edi
0x1400ec532  mov     r8, rbx
0x1400ec535  mov     edx, 88004h; FsControlCode
0x1400ec53a  mov     rcx, [rsp+0C8h+FileHandle]; Handle
0x1400ec542  call    NtFilterpDeviceIoControl
0x1400ec547  mov     edi, eax
0x1400ec549  mov     rcx, [rsp+0C8h+FileHandle]; Handle
0x1400ec551  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1400ec555  jz      short loc_1400EC55D
0x1400ec557  call    cs:__imp_NtClose
0x1400ec55d  test    rbx, rbx
0x1400ec560  jz      short loc_1400EC57A
0x1400ec562  mov     rcx, gs:60h
0x1400ec56b  mov     r8, rbx; P
0x1400ec56e  xor     edx, edx; Flags
0x1400ec570  mov     rcx, [rcx+30h]; HeapHandle
0x1400ec574  call    cs:__imp_RtlFreeHeap
0x1400ec57a  cmp     [rsp+0C8h+P], 0
0x1400ec580  jz      short loc_1400EC59C
0x1400ec582  mov     rcx, gs:60h
0x1400ec58b  mov     r8, [rsp+0C8h+P]; P
0x1400ec590  xor     edx, edx; Flags
0x1400ec592  mov     rcx, [rcx+30h]; HeapHandle
0x1400ec596  call    cs:__imp_RtlFreeHeap
0x1400ec59c  mov     eax, edi
0x1400ec59e  mov     rbx, [rsp+0C8h+arg_10]
0x1400ec5a6  add     rsp, 0C0h
0x1400ec5ad  pop     rdi
0x1400ec5ae  retn
0x1400fcfb2  push    rbp
0x1400fcfb4  sub     rsp, 60h
0x1400fcfb8  mov     rbp, rdx
0x1400fcfbb  mov     rcx, [rbp+0D8h]; Handle
0x1400fcfc2  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1400fcfc6  jz      short loc_1400FCFCF
0x1400fcfc8  call    cs:__imp_NtClose
0x1400fcfce  nop
0x1400fcfcf  mov     r8, [rbp+60h]; P
0x1400fcfd3  test    r8, r8
0x1400fcfd6  jz      short loc_1400FCFEE
0x1400fcfd8  mov     rcx, gs:60h
0x1400fcfe1  xor     edx, edx; Flags
0x1400fcfe3  mov     rcx, [rcx+30h]; HeapHandle
0x1400fcfe7  call    cs:__imp_RtlFreeHeap
0x1400fcfed  nop
0x1400fcfee  cmp     qword ptr [rbp+70h], 0
0x1400fcff3  jz      short loc_1400FD00F
0x1400fcff5  mov     rcx, gs:60h
0x1400fcffe  mov     r8, [rbp+70h]; P
0x1400fd002  xor     edx, edx; Flags
0x1400fd004  mov     rcx, [rcx+30h]; HeapHandle
0x1400fd008  call    cs:__imp_RtlFreeHeap
0x1400fd00e  nop
0x1400fd00f  add     rsp, 60h
0x1400fd013  pop     rbp
0x1400fd014  retn
```
