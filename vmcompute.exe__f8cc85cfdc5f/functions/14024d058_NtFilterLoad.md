# NtFilterLoad

- ea: `0x14024d058`
- end: `0x14024d27b`
- name: `NtFilterLoad`
- size: `547`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x14024d890`

## callees

- `0x14024cce0`
- `0x14024d058`
- `0x14024d9f8`

## import_xrefs

- `ntdll!RtlDosPathNameToNtPathName_U` at `0x14024d08d`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x14024d08d`
- `ntdll!NtCreateFile` at `0x14024d158`
- `ntdll!NtCreateFile` at `0x14024d158`
- `ntdll!RtlAllocateHeap` at `0x14024d192`
- `ntdll!RtlAllocateHeap` at `0x14024d192`
- `ntdll!NtClose` at `0x14024d210`
- `ntdll!NtClose` at `0x1402ba0a5`
- `ntdll!NtClose` at `0x14024d210`
- `ntdll!NtClose` at `0x1402ba0a5`
- `ntdll!RtlFreeHeap` at `0x14024d233`
- `ntdll!RtlFreeHeap` at `0x14024d25b`
- `ntdll!RtlFreeHeap` at `0x1402ba0ca`
- `ntdll!RtlFreeHeap` at `0x1402ba0f1`
- `ntdll!RtlFreeHeap` at `0x14024d233`
- `ntdll!RtlFreeHeap` at `0x14024d25b`
- `ntdll!RtlFreeHeap` at `0x1402ba0ca`
- `ntdll!RtlFreeHeap` at `0x1402ba0f1`

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
0x14024d058  mov     rax, rsp
0x14024d05b  mov     [rax+18h], rbx
0x14024d05f  push    rdi
0x14024d060  sub     rsp, 0C0h
0x14024d067  mov     qword ptr [rax+10h], 0FFFFFFFFFFFFFFFFh
0x14024d06f  xor     ebx, ebx
0x14024d071  mov     [rax-68h], rbx
0x14024d075  xorps   xmm0, xmm0
0x14024d078  movups  xmmword ptr [rax-60h], xmm0
0x14024d07c  xor     r9d, r9d; DirectoryInfo
0x14024d07f  xor     r8d, r8d; NtFileNamePart
0x14024d082  lea     rdx, [rax-60h]; NtPathName
0x14024d086  lea     rcx, DosPathName; "\\\\.\\FltMgr"
0x14024d08d  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x14024d094  nop     dword ptr [rax+rax+00h]
0x14024d099  test    al, al
0x14024d09b  jnz     short loc_14024D0A7
0x14024d09d  mov     edi, 80070003h
0x14024d0a2  jmp     loc_14024D202
0x14024d0a7  xor     eax, eax
0x14024d0a9  mov     dword ptr [rsp+0C8h+ObjectAttributes+4], eax
0x14024d0b0  xorps   xmm0, xmm0
0x14024d0b3  movups  xmmword ptr [rsp+0C8h+ObjectAttributes.Length], xmm0
0x14024d0bb  movups  xmmword ptr [rsp+0C8h+ObjectAttributes.ObjectName], xmm0
0x14024d0c3  movups  xmmword ptr [rsp+0C8h+ObjectAttributes+1Ch], xmm0
0x14024d0cb  mov     [rsp+0C8h+ObjectAttributes.Length], 30h ; '0'
0x14024d0d6  mov     [rsp+0C8h+ObjectAttributes.RootDirectory], rax
0x14024d0de  mov     [rsp+0C8h+ObjectAttributes.Attributes], 40h ; '@'
0x14024d0e9  lea     rax, [rsp+0C8h+var_60]
0x14024d0ee  mov     [rsp+0C8h+ObjectAttributes.ObjectName], rax
0x14024d0f6  movdqu  xmmword ptr [rsp+0C8h+ObjectAttributes.SecurityDescriptor], xmm0
0x14024d0ff  movups  xmmword ptr [rsp+0C8h+IoStatusBlock], xmm0
0x14024d104  mov     [rsp+0C8h+EaLength], 0; EaLength
0x14024d10c  mov     [rsp+0C8h+EaBuffer], 0; EaBuffer
0x14024d115  mov     [rsp+0C8h+CreateOptions], 0; CreateOptions
0x14024d11d  mov     [rsp+0C8h+CreateDisposition], 1; CreateDisposition
0x14024d125  mov     [rsp+0C8h+ShareAccess], 2; ShareAccess
0x14024d12d  mov     [rsp+0C8h+FileAttributes], 80h; int
0x14024d135  mov     [rsp+0C8h+AllocationSize], 0; int
0x14024d13e  lea     r9, [rsp+0C8h+IoStatusBlock]; IoStatusBlock
0x14024d143  lea     r8, [rsp+0C8h+ObjectAttributes]; ObjectAttributes
0x14024d14b  mov     edx, 120116h; DesiredAccess
0x14024d150  lea     rcx, [rsp+0C8h+FileHandle]; FileHandle
0x14024d158  call    cs:__imp_NtCreateFile
0x14024d15f  nop     dword ptr [rax+rax+00h]
0x14024d164  cmp     [rsp+0C8h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x14024d16d  jnz     short loc_14024D17B
0x14024d16f  mov     ecx, eax
0x14024d171  call    FilterHResultFromNtStatus
0x14024d176  jmp     loc_14024D200
0x14024d17b  mov     rcx, gs:60h
0x14024d184  mov     edi, 10h
0x14024d189  mov     r8d, edi; Size
0x14024d18c  xor     edx, edx; Flags
0x14024d18e  mov     rcx, [rcx+30h]; HeapHandle
0x14024d192  call    cs:__imp_RtlAllocateHeap
0x14024d199  nop     dword ptr [rax+rax+00h]
0x14024d19e  mov     rbx, rax
0x14024d1a1  mov     [rsp+0C8h+var_68], rax
0x14024d1a6  test    rax, rax
0x14024d1a9  jnz     short loc_14024D1B2
0x14024d1ab  mov     edi, 8007000Eh
0x14024d1b0  jmp     short loc_14024D202
0x14024d1b2  mov     eax, 0Eh
0x14024d1b7  mov     [rbx], ax
0x14024d1ba  movsd   xmm0, qword ptr cs:aBindflt; "bindflt"
0x14024d1c2  movsd   qword ptr [rbx+2], xmm0
0x14024d1c7  mov     eax, dword ptr cs:aBindflt+8; "flt"
0x14024d1cd  mov     [rbx+0Ah], eax
0x14024d1d0  movzx   eax, word ptr cs:aBindflt+0Ch; "t"
0x14024d1d7  mov     [rbx+0Eh], ax
0x14024d1db  lea     rax, [rsp+0C8h+arg_0]
0x14024d1e3  mov     qword ptr [rsp+0C8h+ShareAccess], rax; __int64
0x14024d1e8  mov     r9d, edi
0x14024d1eb  mov     r8, rbx
0x14024d1ee  mov     edx, 88004h; FsControlCode
0x14024d1f3  mov     rcx, [rsp+0C8h+FileHandle]; Handle
0x14024d1fb  call    NtFilterpDeviceIoControl
0x14024d200  mov     edi, eax
0x14024d202  mov     rcx, [rsp+0C8h+FileHandle]; Handle
0x14024d20a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14024d20e  jz      short loc_14024D21C
0x14024d210  call    cs:__imp_NtClose
0x14024d217  nop     dword ptr [rax+rax+00h]
0x14024d21c  test    rbx, rbx
0x14024d21f  jz      short loc_14024D23F
0x14024d221  mov     rcx, gs:60h
0x14024d22a  mov     r8, rbx; P
0x14024d22d  xor     edx, edx; Flags
0x14024d22f  mov     rcx, [rcx+30h]; HeapHandle
0x14024d233  call    cs:__imp_RtlFreeHeap
0x14024d23a  nop     dword ptr [rax+rax+00h]
0x14024d23f  cmp     [rsp+0C8h+P], 0
0x14024d245  jz      short loc_14024D267
0x14024d247  mov     rcx, gs:60h
0x14024d250  mov     r8, [rsp+0C8h+P]; P
0x14024d255  xor     edx, edx; Flags
0x14024d257  mov     rcx, [rcx+30h]; HeapHandle
0x14024d25b  call    cs:__imp_RtlFreeHeap
0x14024d262  nop     dword ptr [rax+rax+00h]
0x14024d267  mov     eax, edi
0x14024d269  mov     rbx, [rsp+0C8h+arg_10]
0x14024d271  add     rsp, 0C0h
0x14024d278  pop     rdi
0x14024d279  retn
0x1402ba08f  push    rbp
0x1402ba091  sub     rsp, 60h
0x1402ba095  mov     rbp, rdx
0x1402ba098  mov     rcx, [rbp+0D8h]; Handle
0x1402ba09f  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1402ba0a3  jz      short loc_1402BA0B2
0x1402ba0a5  call    cs:__imp_NtClose
0x1402ba0ac  nop     dword ptr [rax+rax+00h]
0x1402ba0b1  nop
0x1402ba0b2  mov     r8, [rbp+60h]; P
0x1402ba0b6  test    r8, r8
0x1402ba0b9  jz      short loc_1402BA0D7
0x1402ba0bb  mov     rcx, gs:60h
0x1402ba0c4  xor     edx, edx; Flags
0x1402ba0c6  mov     rcx, [rcx+30h]; HeapHandle
0x1402ba0ca  call    cs:__imp_RtlFreeHeap
0x1402ba0d1  nop     dword ptr [rax+rax+00h]
0x1402ba0d6  nop
0x1402ba0d7  cmp     qword ptr [rbp+70h], 0
0x1402ba0dc  jz      short loc_1402BA0FE
0x1402ba0de  mov     rcx, gs:60h
0x1402ba0e7  mov     r8, [rbp+70h]; P
0x1402ba0eb  xor     edx, edx; Flags
0x1402ba0ed  mov     rcx, [rcx+30h]; HeapHandle
0x1402ba0f1  call    cs:__imp_RtlFreeHeap
0x1402ba0f8  nop     dword ptr [rax+rax+00h]
0x1402ba0fd  nop
0x1402ba0fe  add     rsp, 60h
0x1402ba102  pop     rbp
0x1402ba103  retn
```
