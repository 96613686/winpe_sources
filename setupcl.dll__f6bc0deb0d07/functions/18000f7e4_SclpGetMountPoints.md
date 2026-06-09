# SclpGetMountPoints

- ea: `0x18000f7e4`
- end: `0x18000faa7`
- name: `SclpGetMountPoints`
- size: `707`
- prototype: `__int64 __fastcall(__int64, ULONG **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x18000fc6c`

## callees

- `0x180001c74`
- `0x18000a524`
- `0x18000f7e4`
- `0x1800179e0`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000f91d`
- `ntdll!RtlAllocateHeap` at `0x18000f9b7`
- `ntdll!RtlAllocateHeap` at `0x18000f91d`
- `ntdll!RtlAllocateHeap` at `0x18000f9b7`
- `ntdll!NtClose` at `0x18000fa7c`
- `ntdll!NtClose` at `0x18000fa7c`
- `ntdll!RtlFreeHeap` at `0x18000f99c`
- `ntdll!RtlFreeHeap` at `0x18000fa68`
- `ntdll!RtlFreeHeap` at `0x18000f99c`
- `ntdll!RtlFreeHeap` at `0x18000fa68`
- `ntdll!NtCreateFile` at `0x18000f8a7`
- `ntdll!NtCreateFile` at `0x18000f8a7`
- `ntdll!NtDeviceIoControlFile` at `0x18000f966`
- `ntdll!NtDeviceIoControlFile` at `0x18000fa06`
- `ntdll!NtDeviceIoControlFile` at `0x18000f966`
- `ntdll!NtDeviceIoControlFile` at `0x18000fa06`

## string_xrefs

- `0x18000f8c8`: `(%lx): Unable to open handle to [%ws].`
- `0x18000f817`: `\Device\MountPointManager`
- `0x18000f8b5`: `\\.\MountPointManager`
- `0x18000f8e2`: `SclpGetMountPoints`
- `0x18000fa3f`: `SclpGetMountPoints`
- `0x18000fa1e`: `(%lx): Unable to query mount points.`

## pseudocode

```c
__int64 __fastcall SclpGetMountPoints(__int64 a1, ULONG **a2)
{
  NTSTATUS v4; // ebx
  __int64 v5; // rcx
  ULONG *Heap; // rax
  ULONG *v7; // rdi
  NTSTATUS v8; // eax
  int v9; // r9d
  ULONG v10; // ebx
  ULONG *v11; // rax
  __int64 v12; // rcx
  ULONG ShareAccess[2]; // [rsp+30h] [rbp-79h]
  ULONG ShareAccessa[2]; // [rsp+30h] [rbp-79h]
  void *FileHandle; // [rsp+60h] [rbp-49h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+68h] [rbp-41h] BYREF
  struct _UNICODE_STRING v18; // [rsp+78h] [rbp-31h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-21h] BYREF
  __int128 InputBuffer; // [rsp+B8h] [rbp+Fh] BYREF
  __int64 v21; // [rsp+C8h] [rbp+1Fh]

  FileHandle = 0;
  v21 = 0;
  memset(&ObjectAttributes, 0, 44);
  v18 = 0;
  IoStatusBlock = 0;
  InputBuffer = 0;
  INIT_OBJA_EX((__int64)&ObjectAttributes, &v18, L"\\Device\\MountPointManager", 64, 0);
  v4 = NtCreateFile(&FileHandle, 0xC0000000, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 3u, 1u, 0, 0, 0);
  if ( v4 < 0 )
  {
    v5 = a1 + 1152;
    ShareAccess[0] = v4;
    if ( !a1 )
      v5 = 0;
    SclLogGenericMessage(
      v5,
      3,
      (int)SclEvent_Generic_Error,
      493,
      (__int64)"SclpGetMountPoints",
      "(%lx): Unable to open handle to [%ws].",
      *(_QWORD *)ShareAccess,
      L"\\\\.\\MountPointManager");
    goto LABEL_17;
  }
  Heap = (ULONG *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x20u);
  v7 = Heap;
  if ( !Heap )
  {
LABEL_10:
    v4 = -1073741801;
    goto LABEL_17;
  }
  v8 = NtDeviceIoControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x6D0008u, &InputBuffer, 0x18u, Heap, 0x20u);
  v4 = v8;
  if ( v8 >= 0 )
  {
LABEL_16:
    *a2 = v7;
    goto LABEL_17;
  }
  if ( v8 == -2147483643 )
  {
    v10 = *v7;
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
    v11 = (ULONG *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v10);
    v7 = v11;
    if ( !v11 )
      goto LABEL_10;
    v4 = NtDeviceIoControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x6D0008u, &InputBuffer, 0x18u, v11, v10);
    if ( v4 < 0 )
    {
      v9 = 559;
      goto LABEL_13;
    }
    goto LABEL_16;
  }
  v9 = 525;
LABEL_13:
  ShareAccessa[0] = v4;
  v12 = a1 + 1152;
  if ( !a1 )
    v12 = 0;
  SclLogGenericMessage(
    v12,
    3,
    (int)SclEvent_Generic_Error,
    v9,
    (__int64)"SclpGetMountPoints",
    "(%lx): Unable to query mount points.",
    *(_QWORD *)ShareAccessa);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
LABEL_17:
  if ( FileHandle )
    NtClose(FileHandle);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000f7e4  mov     [rsp-8+arg_10], rbx
0x18000f7e9  push    rbp
0x18000f7ea  push    rsi
0x18000f7eb  push    rdi
0x18000f7ec  push    r14
0x18000f7ee  push    r15
0x18000f7f0  lea     rbp, [rsp-37h]
0x18000f7f5  sub     rsp, 0E0h
0x18000f7fc  mov     rax, cs:__security_cookie
0x18000f803  xor     rax, rsp
0x18000f806  mov     [rbp+57h+var_30], rax
0x18000f80a  xorps   xmm0, xmm0
0x18000f80d  mov     [rbp+57h+FileHandle], 0
0x18000f815  xor     eax, eax
0x18000f817  lea     r8, aDeviceMountpoi; "\\Device\\MountPointManager"
0x18000f81e  mov     r15, rdx
0x18000f821  mov     [rbp+57h+var_38], rax
0x18000f825  mov     rsi, rcx
0x18000f828  mov     [rsp+100h+AllocationSize], rax
0x18000f82d  xorps   xmm1, xmm1
0x18000f830  lea     rdx, [rbp+57h+var_88]
0x18000f834  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18000f838  lea     r9d, [rax+40h]
0x18000f83c  lea     rcx, [rbp+57h+ObjectAttributes]
0x18000f840  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18000f844  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18000f848  movups  [rbp+57h+var_88], xmm0
0x18000f84c  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm1
0x18000f850  movups  [rbp+57h+InputBuffer], xmm0
0x18000f854  call    INIT_OBJA_EX
0x18000f859  mov     [rsp+100h+EaLength], 0; EaLength
0x18000f861  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18000f865  mov     [rsp+100h+EaBuffer], 0; EaBuffer
0x18000f86e  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18000f872  mov     [rsp+100h+CreateOptions], 0; CreateOptions
0x18000f87a  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x18000f87e  mov     [rsp+100h+CreateDisposition], 1; CreateDisposition
0x18000f886  mov     r14d, 3
0x18000f88c  mov     [rsp+100h+ShareAccess], r14d; ShareAccess
0x18000f891  mov     edx, 0C0000000h; DesiredAccess
0x18000f896  mov     [rsp+100h+FileAttributes], 80h; FileAttributes
0x18000f89e  mov     [rsp+100h+AllocationSize], 0; AllocationSize
0x18000f8a7  call    cs:__imp_NtCreateFile
0x18000f8ad  mov     ebx, eax
0x18000f8af  test    eax, eax
0x18000f8b1  jns     short loc_18000F905
0x18000f8b3  xor     edx, edx
0x18000f8b5  lea     rax, aMountpointmana; "\\\\.\\MountPointManager"
0x18000f8bc  mov     qword ptr [rsp+100h+CreateDisposition], rax
0x18000f8c1  lea     rcx, [rsi+480h]
0x18000f8c8  lea     rax, aLxUnableToOpen; "(%lx): Unable to open handle to [%ws]."
0x18000f8cf  mov     [rsp+100h+ShareAccess], ebx
0x18000f8d3  mov     qword ptr [rsp+100h+FileAttributes], rax
0x18000f8d8  lea     r8, SclEvent_Generic_Error
0x18000f8df  test    rsi, rsi
0x18000f8e2  lea     rax, aSclpgetmountpo; "SclpGetMountPoints"
0x18000f8e9  mov     r9d, 1EDh
0x18000f8ef  mov     [rsp+100h+AllocationSize], rax
0x18000f8f4  cmovz   rcx, rdx
0x18000f8f8  mov     edx, r14d
0x18000f8fb  call    SclLogGenericMessage
0x18000f900  jmp     loc_18000FA73
0x18000f905  mov     rcx, gs:60h
0x18000f90e  mov     ebx, 20h ; ' '
0x18000f913  mov     r8d, ebx; Size
0x18000f916  mov     rcx, [rcx+30h]; HeapHandle
0x18000f91a  lea     edx, [rbx-18h]; Flags
0x18000f91d  call    cs:__imp_RtlAllocateHeap
0x18000f923  mov     rdi, rax
0x18000f926  test    rax, rax
0x18000f929  jz      loc_18000F9C5
0x18000f92f  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x18000f933  xor     r9d, r9d; ApcContext
0x18000f936  mov     dword ptr [rsp+100h+EaBuffer], ebx; OutputBufferLength
0x18000f93a  xor     r8d, r8d; ApcRoutine
0x18000f93d  mov     qword ptr [rsp+100h+CreateOptions], rax; OutputBuffer
0x18000f942  xor     edx, edx; Event
0x18000f944  mov     [rsp+100h+CreateDisposition], 18h; InputBufferLength
0x18000f94c  lea     rax, [rbp+57h+InputBuffer]
0x18000f950  mov     qword ptr [rsp+100h+ShareAccess], rax; InputBuffer
0x18000f955  lea     rax, [rbp+57h+IoStatusBlock]
0x18000f959  mov     [rsp+100h+FileAttributes], 6D0008h; IoControlCode
0x18000f961  mov     [rsp+100h+AllocationSize], rax; IoStatusBlock
0x18000f966  call    cs:__imp_NtDeviceIoControlFile
0x18000f96c  mov     ebx, eax
0x18000f96e  test    eax, eax
0x18000f970  jns     loc_18000FA70
0x18000f976  cmp     eax, 80000005h
0x18000f97b  jz      short loc_18000F988
0x18000f97d  mov     r9d, 20Dh
0x18000f983  jmp     loc_18000FA18
0x18000f988  mov     rcx, gs:60h
0x18000f991  mov     r8, rdi; P
0x18000f994  mov     ebx, [rdi]
0x18000f996  xor     edx, edx; Flags
0x18000f998  mov     rcx, [rcx+30h]; HeapHandle
0x18000f99c  call    cs:__imp_RtlFreeHeap
0x18000f9a2  mov     rcx, gs:60h
0x18000f9ab  mov     r8d, ebx; Size
0x18000f9ae  mov     edx, 8; Flags
0x18000f9b3  mov     rcx, [rcx+30h]; HeapHandle
0x18000f9b7  call    cs:__imp_RtlAllocateHeap
0x18000f9bd  mov     rdi, rax
0x18000f9c0  test    rax, rax
0x18000f9c3  jnz     short loc_18000F9CF
0x18000f9c5  mov     ebx, 0C0000017h
0x18000f9ca  jmp     loc_18000FA73
0x18000f9cf  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x18000f9d3  xor     r9d, r9d; ApcContext
0x18000f9d6  mov     dword ptr [rsp+100h+EaBuffer], ebx; OutputBufferLength
0x18000f9da  xor     r8d, r8d; ApcRoutine
0x18000f9dd  mov     qword ptr [rsp+100h+CreateOptions], rax; OutputBuffer
0x18000f9e2  xor     edx, edx; Event
0x18000f9e4  mov     [rsp+100h+CreateDisposition], 18h; InputBufferLength
0x18000f9ec  lea     rax, [rbp+57h+InputBuffer]
0x18000f9f0  mov     qword ptr [rsp+100h+ShareAccess], rax; InputBuffer
0x18000f9f5  lea     rax, [rbp+57h+IoStatusBlock]
0x18000f9f9  mov     [rsp+100h+FileAttributes], 6D0008h; IoControlCode
0x18000fa01  mov     [rsp+100h+AllocationSize], rax; IoStatusBlock
0x18000fa06  call    cs:__imp_NtDeviceIoControlFile
0x18000fa0c  mov     ebx, eax
0x18000fa0e  test    eax, eax
0x18000fa10  jns     short loc_18000FA70
0x18000fa12  mov     r9d, 22Fh
0x18000fa18  xor     eax, eax
0x18000fa1a  mov     [rsp+100h+ShareAccess], ebx
0x18000fa1e  lea     rdx, aLxUnableToQuer; "(%lx): Unable to query mount points."
0x18000fa25  test    rsi, rsi
0x18000fa28  mov     qword ptr [rsp+100h+FileAttributes], rdx
0x18000fa2d  lea     rcx, [rsi+480h]
0x18000fa34  cmovz   rcx, rax
0x18000fa38  lea     r8, SclEvent_Generic_Error
0x18000fa3f  lea     rax, aSclpgetmountpo; "SclpGetMountPoints"
0x18000fa46  mov     r10d, ebx
0x18000fa49  mov     edx, r14d
0x18000fa4c  mov     [rsp+100h+AllocationSize], rax
0x18000fa51  call    SclLogGenericMessage
0x18000fa56  mov     rcx, gs:60h
0x18000fa5f  mov     r8, rdi; P
0x18000fa62  xor     edx, edx; Flags
0x18000fa64  mov     rcx, [rcx+30h]; HeapHandle
0x18000fa68  call    cs:__imp_RtlFreeHeap
0x18000fa6e  jmp     short loc_18000FA73
0x18000fa70  mov     [r15], rdi
0x18000fa73  mov     rcx, [rbp+57h+FileHandle]; Handle
0x18000fa77  test    rcx, rcx
0x18000fa7a  jz      short loc_18000FA82
0x18000fa7c  call    cs:__imp_NtClose
0x18000fa82  mov     eax, ebx
0x18000fa84  mov     rcx, [rbp+57h+var_30]
0x18000fa88  xor     rcx, rsp; StackCookie
0x18000fa8b  call    __security_check_cookie
0x18000fa90  mov     rbx, [rsp+100h+arg_10]
0x18000fa98  add     rsp, 0E0h
0x18000fa9f  pop     r15
0x18000faa1  pop     r14
0x18000faa3  pop     rdi
0x18000faa4  pop     rsi
0x18000faa5  pop     rbp
0x18000faa6  retn
```
