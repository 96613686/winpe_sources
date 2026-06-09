# NtFilterInstanceCreate

- ea: `0x1400ec11c`
- end: `0x1400ec3ac`
- name: `NtFilterInstanceCreate`
- size: `656`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x1400ec840`

## callees

- `0x140006080`
- `0x1400ec074`
- `0x1400ec11c`
- `0x1400ecc94`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1400ec341`
- `ntdll!RtlFreeHeap` at `0x1400ec386`
- `ntdll!RtlFreeHeap` at `0x1400fcf45`
- `ntdll!RtlFreeHeap` at `0x1400fcf8d`
- `ntdll!RtlFreeHeap` at `0x1400ec341`
- `ntdll!RtlFreeHeap` at `0x1400ec386`
- `ntdll!RtlFreeHeap` at `0x1400fcf45`
- `ntdll!RtlFreeHeap` at `0x1400fcf8d`
- `ntdll!RtlAllocateHeap` at `0x1400ec27a`
- `ntdll!RtlAllocateHeap` at `0x1400ec27a`
- `ntdll!NtCreateFile` at `0x1400ec232`
- `ntdll!NtCreateFile` at `0x1400ec232`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1400ec171`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1400ec171`
- `ntdll!NtClose` at `0x1400ec359`
- `ntdll!NtClose` at `0x1400fcf62`
- `ntdll!NtClose` at `0x1400ec359`
- `ntdll!NtClose` at `0x1400fcf62`

## pseudocode

```c
__int64 __fastcall NtFilterInstanceCreate(__int64 a1, _WORD *a2, __int64 a3, void **a4)
{
  char *v6; // rdi
  int v7; // ebx
  unsigned int v8; // eax
  int v9; // eax
  __int64 v10; // rax
  size_t v11; // r15
  char *Heap; // rax
  char *v13; // rbx
  __int64 v14; // rcx
  unsigned __int16 v15; // ax
  int AllocationSize; // [rsp+20h] [rbp-D8h]
  ULONG FileAttributes; // [rsp+28h] [rbp-D0h]
  struct _UNICODE_STRING NtPathName; // [rsp+70h] [rbp-88h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp-78h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-68h] BYREF
  void *FileHandle; // [rsp+100h] [rbp+8h] BYREF
  __int64 v23; // [rsp+110h] [rbp+18h] BYREF
  void **v24; // [rsp+118h] [rbp+20h]

  v24 = a4;
  v6 = 0;
  FileHandle = (void *)-1LL;
  NtPathName = 0;
  if ( !RtlDosPathNameToNtPathName_U(L"\\\\.\\FltMgr", &NtPathName, 0, 0) )
  {
    v7 = -2147024893;
    goto LABEL_11;
  }
  *(&ObjectAttributes.Length + 1) = 0;
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &NtPathName;
  IoStatusBlock = 0;
  v8 = NtCreateFile(&FileHandle, 0x12019Fu, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 3u, 1u, 0, 0, 0);
  if ( FileHandle == (void *)-1LL )
  {
    v9 = FilterHResultFromNtStatus(v8);
  }
  else
  {
    v10 = -1;
    do
      ++v10;
    while ( a2[v10] );
    v11 = (unsigned __int16)(2 * v10);
    Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned int)(v11 + 34));
    v6 = Heap;
    if ( !Heap )
    {
      v7 = -2147024882;
      goto LABEL_11;
    }
    *((_DWORD *)Heap + 1) = 8;
    v13 = Heap + 8;
    *(_DWORD *)Heap = 1;
    *((_DWORD *)Heap + 2) = 786446;
    v14 = *((unsigned __int16 *)Heap + 5);
    *(_QWORD *)&v13[v14] = *(_QWORD *)L"bindflt";
    *(_DWORD *)&v13[v14 + 8] = *(_DWORD *)L"flt";
    *(_WORD *)&v13[v14 + 12] = aBindflt[6];
    v15 = *((_WORD *)Heap + 5) + 14;
    *((_WORD *)v13 + 3) = v15;
    *((_WORD *)v13 + 2) = v11;
    memcpy_0(&v13[v15], a2, v11);
    *((_DWORD *)v13 + 2) = 0;
    v9 = NtFilterpDeviceIoControl(FileHandle, 0x8400Cu, AllocationSize, FileAttributes, (__int64)&v23);
  }
  v7 = v9;
LABEL_11:
  if ( v6 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
  if ( v7 < 0 && FileHandle != (void *)-1LL )
  {
    NtClose(FileHandle);
    FileHandle = (void *)-1LL;
  }
  if ( NtPathName.Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtPathName.Buffer);
  *a4 = FileHandle;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400ec11c  mov     rax, rsp
0x1400ec11f  mov     [rax+20h], r9
0x1400ec123  mov     [rax+8], rcx
0x1400ec127  push    rbx
0x1400ec128  push    rsi
0x1400ec129  push    rdi
0x1400ec12a  push    r12
0x1400ec12c  push    r13
0x1400ec12e  push    r14
0x1400ec130  push    r15
0x1400ec132  sub     rsp, 0C0h
0x1400ec139  mov     rsi, r9
0x1400ec13c  mov     r14, rdx
0x1400ec13f  xor     r13d, r13d
0x1400ec142  mov     edi, r13d
0x1400ec145  mov     [rsp+0F8h+var_90], r13
0x1400ec14a  mov     [rsp+0F8h+var_98], r13d
0x1400ec14f  mov     qword ptr [rax+8], 0FFFFFFFFFFFFFFFFh
0x1400ec157  xorps   xmm0, xmm0
0x1400ec15a  movups  xmmword ptr [rsp+0F8h+NtPathName.Length], xmm0
0x1400ec15f  xor     r9d, r9d; DirectoryInfo
0x1400ec162  xor     r8d, r8d; NtFileNamePart
0x1400ec165  lea     rdx, [rsp+0F8h+NtPathName]; NtPathName
0x1400ec16a  lea     rcx, DosPathName; "\\\\.\\FltMgr"
0x1400ec171  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x1400ec177  test    al, al
0x1400ec179  jnz     short loc_1400EC189
0x1400ec17b  mov     ebx, 80070003h
0x1400ec180  mov     [rsp+0F8h+var_98], ebx
0x1400ec184  jmp     loc_1400EC32A
0x1400ec189  xor     eax, eax
0x1400ec18b  mov     dword ptr [rsp+0F8h+ObjectAttributes+4], eax
0x1400ec192  xorps   xmm0, xmm0
0x1400ec195  movups  xmmword ptr [rsp+0F8h+ObjectAttributes.Length], xmm0
0x1400ec19d  movups  xmmword ptr [rsp+0F8h+ObjectAttributes.ObjectName], xmm0
0x1400ec1a5  movups  xmmword ptr [rsp+0F8h+ObjectAttributes+1Ch], xmm0
0x1400ec1ad  mov     [rsp+0F8h+ObjectAttributes.Length], 30h ; '0'
0x1400ec1b8  mov     [rsp+0F8h+ObjectAttributes.RootDirectory], r13
0x1400ec1c0  mov     [rsp+0F8h+ObjectAttributes.Attributes], 40h ; '@'
0x1400ec1cb  lea     rax, [rsp+0F8h+NtPathName]
0x1400ec1d0  mov     [rsp+0F8h+ObjectAttributes.ObjectName], rax
0x1400ec1d8  movdqu  xmmword ptr [rsp+0F8h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400ec1e1  movups  xmmword ptr [rsp+0F8h+IoStatusBlock], xmm0
0x1400ec1e9  mov     [rsp+0F8h+EaLength], r13d; EaLength
0x1400ec1ee  mov     [rsp+0F8h+EaBuffer], r13; EaBuffer
0x1400ec1f3  mov     [rsp+0F8h+CreateOptions], r13d; CreateOptions
0x1400ec1f8  mov     [rsp+0F8h+CreateDisposition], 1; CreateDisposition
0x1400ec200  mov     [rsp+0F8h+ShareAccess], 3; ShareAccess
0x1400ec208  mov     [rsp+0F8h+FileAttributes], 80h; int
0x1400ec210  mov     [rsp+0F8h+AllocationSize], r13; int
0x1400ec215  lea     r9, [rsp+0F8h+IoStatusBlock]; IoStatusBlock
0x1400ec21d  lea     r8, [rsp+0F8h+ObjectAttributes]; ObjectAttributes
0x1400ec225  mov     edx, 12019Fh; DesiredAccess
0x1400ec22a  lea     rcx, [rsp+0F8h+FileHandle]; FileHandle
0x1400ec232  call    cs:__imp_NtCreateFile
0x1400ec238  cmp     [rsp+0F8h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x1400ec241  jnz     short loc_1400EC24F
0x1400ec243  mov     ecx, eax
0x1400ec245  call    FilterHResultFromNtStatus
0x1400ec24a  jmp     loc_1400EC324
0x1400ec24f  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400ec253  inc     rax
0x1400ec256  cmp     [r14+rax*2], r13w
0x1400ec25b  jnz     short loc_1400EC253
0x1400ec25d  add     ax, ax
0x1400ec260  movzx   r15d, ax
0x1400ec264  lea     r12d, [r15+22h]
0x1400ec268  mov     r8d, r12d; Size
0x1400ec26b  mov     rcx, gs:60h
0x1400ec274  xor     edx, edx; Flags
0x1400ec276  mov     rcx, [rcx+30h]; HeapHandle
0x1400ec27a  call    cs:__imp_RtlAllocateHeap
0x1400ec280  mov     rdi, rax
0x1400ec283  mov     [rsp+0F8h+var_90], rax
0x1400ec288  test    rax, rax
0x1400ec28b  jnz     short loc_1400EC297
0x1400ec28d  mov     ebx, 8007000Eh
0x1400ec292  jmp     loc_1400EC180
0x1400ec297  mov     dword ptr [rax+4], 8
0x1400ec29e  lea     rbx, [rax+8]
0x1400ec2a2  mov     dword ptr [rax], 1
0x1400ec2a8  mov     dword ptr [rbx], 0C000Eh
0x1400ec2ae  mov     edx, 0Eh
0x1400ec2b3  movzx   ecx, word ptr [rbx+2]
0x1400ec2b7  movsd   xmm0, qword ptr cs:aBindflt; "bindflt"
0x1400ec2bf  movsd   qword ptr [rcx+rbx], xmm0
0x1400ec2c4  mov     eax, dword ptr cs:aBindflt+8; "flt"
0x1400ec2ca  mov     [rcx+rbx+8], eax
0x1400ec2ce  movzx   eax, word ptr cs:aBindflt+0Ch; "t"
0x1400ec2d5  mov     [rcx+rbx+0Ch], ax
0x1400ec2da  movzx   eax, word ptr [rbx+2]
0x1400ec2de  add     ax, dx
0x1400ec2e1  movzx   ecx, ax
0x1400ec2e4  mov     [rbx+6], cx
0x1400ec2e8  mov     [rbx+4], r15w
0x1400ec2ed  add     rcx, rbx; void *
0x1400ec2f0  mov     r8, r15; Size
0x1400ec2f3  mov     rdx, r14; Src
0x1400ec2f6  call    memcpy_0
0x1400ec2fb  mov     [rbx+8], r13d
0x1400ec2ff  lea     rax, [rsp+0F8h+arg_10]
0x1400ec307  mov     qword ptr [rsp+0F8h+ShareAccess], rax; __int64
0x1400ec30c  mov     r9d, r12d
0x1400ec30f  mov     r8, rdi
0x1400ec312  mov     edx, 8400Ch; FsControlCode
0x1400ec317  mov     rcx, [rsp+0F8h+FileHandle]; Handle
0x1400ec31f  call    NtFilterpDeviceIoControl
0x1400ec324  mov     [rsp+0F8h+var_98], eax
0x1400ec328  mov     ebx, eax
0x1400ec32a  test    rdi, rdi
0x1400ec32d  jz      short loc_1400EC347
0x1400ec32f  mov     rcx, gs:60h
0x1400ec338  mov     r8, rdi; P
0x1400ec33b  xor     edx, edx; Flags
0x1400ec33d  mov     rcx, [rcx+30h]; HeapHandle
0x1400ec341  call    cs:__imp_RtlFreeHeap
0x1400ec347  test    ebx, ebx
0x1400ec349  jns     short loc_1400EC36B
0x1400ec34b  mov     rcx, [rsp+0F8h+FileHandle]; Handle
0x1400ec353  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1400ec357  jz      short loc_1400EC36B
0x1400ec359  call    cs:__imp_NtClose
0x1400ec35f  mov     [rsp+0F8h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x1400ec36b  cmp     [rsp+0F8h+NtPathName.Buffer], r13
0x1400ec370  jz      short loc_1400EC38C
0x1400ec372  mov     rcx, gs:60h
0x1400ec37b  mov     r8, [rsp+0F8h+NtPathName.Buffer]; P
0x1400ec380  xor     edx, edx; Flags
0x1400ec382  mov     rcx, [rcx+30h]; HeapHandle
0x1400ec386  call    cs:__imp_RtlFreeHeap
0x1400ec38c  mov     rax, [rsp+0F8h+FileHandle]
0x1400ec394  mov     [rsi], rax
0x1400ec397  mov     eax, ebx
0x1400ec399  add     rsp, 0C0h
0x1400ec3a0  pop     r15
0x1400ec3a2  pop     r14
0x1400ec3a4  pop     r13
0x1400ec3a6  pop     r12
0x1400ec3a8  pop     rdi
0x1400ec3a9  pop     rsi
0x1400ec3aa  pop     rbx
0x1400ec3ab  retn
0x1400fcf24  push    rbp
0x1400fcf26  sub     rsp, 60h
0x1400fcf2a  mov     rbp, rdx
0x1400fcf2d  mov     r8, [rbp+68h]; P
0x1400fcf31  test    r8, r8
0x1400fcf34  jz      short loc_1400FCF4C
0x1400fcf36  mov     rcx, gs:60h
0x1400fcf3f  xor     edx, edx; Flags
0x1400fcf41  mov     rcx, [rcx+30h]; HeapHandle
0x1400fcf45  call    cs:__imp_RtlFreeHeap
0x1400fcf4b  nop
0x1400fcf4c  test    dword ptr [rbp+60h], 80000000h
0x1400fcf53  jz      short loc_1400FCF73
0x1400fcf55  mov     rcx, [rbp+100h]; Handle
0x1400fcf5c  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1400fcf60  jz      short loc_1400FCF73
0x1400fcf62  call    cs:__imp_NtClose
0x1400fcf68  mov     qword ptr [rbp+100h], 0FFFFFFFFFFFFFFFFh
0x1400fcf73  cmp     qword ptr [rbp+78h], 0
0x1400fcf78  jz      short loc_1400FCF94
0x1400fcf7a  mov     rcx, gs:60h
0x1400fcf83  mov     r8, [rbp+78h]; P
0x1400fcf87  xor     edx, edx; Flags
0x1400fcf89  mov     rcx, [rcx+30h]; HeapHandle
0x1400fcf8d  call    cs:__imp_RtlFreeHeap
0x1400fcf93  nop
0x1400fcf94  mov     rcx, [rbp+118h]
0x1400fcf9b  mov     rax, [rbp+100h]
0x1400fcfa2  mov     [rcx], rax
0x1400fcfa5  add     rsp, 60h
0x1400fcfa9  pop     rbp
0x1400fcfaa  retn
```
