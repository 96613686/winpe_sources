# NtFilterpCommonAttach

- ea: `0x1400ec5b8`
- end: `0x1400ec83a`
- name: `NtFilterpCommonAttach`
- size: `642`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, loader_planting, broker_com_uri`

## callers

- `0x1400ec840`

## callees

- `0x140006080`
- `0x1400ec074`
- `0x1400ec5b8`
- `0x1400ecc94`
- `0x1400f4ec4`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1400ec80c`
- `ntdll!RtlFreeHeap` at `0x1400ec82d`
- `ntdll!RtlFreeHeap` at `0x1400fd051`
- `ntdll!RtlFreeHeap` at `0x1400fd072`
- `ntdll!RtlFreeHeap` at `0x1400ec80c`
- `ntdll!RtlFreeHeap` at `0x1400ec82d`
- `ntdll!RtlFreeHeap` at `0x1400fd051`
- `ntdll!RtlFreeHeap` at `0x1400fd072`
- `ntdll!RtlAllocateHeap` at `0x1400ec74a`
- `ntdll!RtlAllocateHeap` at `0x1400ec74a`
- `ntdll!NtCreateFile` at `0x1400ec6cf`
- `ntdll!NtCreateFile` at `0x1400ec6cf`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1400ec612`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1400ec612`
- `ntdll!NtClose` at `0x1400ec7ef`
- `ntdll!NtClose` at `0x1400fd032`
- `ntdll!NtClose` at `0x1400ec7ef`
- `ntdll!NtClose` at `0x1400fd032`

## pseudocode

```c
__int64 __fastcall NtFilterpCommonAttach(__int64 a1, _WORD *a2, int a3)
{
  _QWORD *v4; // rbx
  unsigned int v5; // edi
  unsigned int v6; // eax
  __int64 v8; // rax
  size_t v9; // rsi
  char *Heap; // rax
  __int64 v11; // [rsp+0h] [rbp-D8h] BYREF
  PLARGE_INTEGER AllocationSize; // [rsp+20h] [rbp-B8h]
  ULONG FileAttributes; // [rsp+28h] [rbp-B0h]
  char *v14; // [rsp+60h] [rbp-78h]
  __int64 *v15; // [rsp+68h] [rbp-70h]
  struct _UNICODE_STRING v16; // [rsp+70h] [rbp-68h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp-58h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-48h] BYREF
  __int64 v19; // [rsp+F0h] [rbp+18h] BYREF
  void *FileHandle; // [rsp+F8h] [rbp+20h] BYREF

  LODWORD(v19) = a3;
  v15 = &v11;
  v4 = 0;
  v14 = 0;
  FileHandle = (void *)-1LL;
  v16 = 0;
  if ( a2 )
  {
    if ( RtlDosPathNameToNtPathName_U(L"\\\\.\\FltMgr", &v16, 0, 0) )
    {
      *(&ObjectAttributes.Length + 1) = 0;
      memset(&ObjectAttributes.Attributes + 1, 0, 20);
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 64;
      ObjectAttributes.ObjectName = &v16;
      IoStatusBlock = 0;
      v6 = NtCreateFile(&FileHandle, 0x12019Fu, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 3u, 1u, 0, 0, 0);
      if ( FileHandle == (void *)-1LL )
      {
        LODWORD(v19) = FilterHResultFromNtStatus(v6);
        local_unwind_0(v15, &loc_1400EC700);
        return (unsigned int)v19;
      }
      v8 = -1;
      do
        ++v8;
      while ( a2[v8] );
      v9 = (unsigned __int16)(2 * v8);
      Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned int)(v9 + 34));
      v4 = Heap;
      v14 = Heap;
      if ( Heap )
      {
        *(_DWORD *)Heap = 1310734;
        *(_QWORD *)(Heap + 20) = *(_QWORD *)L"bindflt";
        *((_DWORD *)Heap + 7) = *(_DWORD *)L"flt";
        *((_WORD *)Heap + 16) = aBindflt[6];
        *((_WORD *)Heap + 2) = v9;
        *((_WORD *)Heap + 3) = 34;
        memcpy_0(Heap + 34, a2, v9);
        v4[1] = 1;
        *((_DWORD *)v4 + 4) = 0;
        v5 = NtFilterpDeviceIoControl(FileHandle, 0x88010u, (int)AllocationSize, FileAttributes, (__int64)&v19);
      }
      else
      {
        v5 = -2147024882;
      }
    }
    else
    {
      v5 = -2147024893;
    }
  }
  else
  {
    v5 = -2147024809;
  }
  if ( FileHandle != (void *)-1LL )
    NtClose(FileHandle);
  if ( v4 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
  if ( v16.Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v16.Buffer);
  return v5;
}

```

## disassembly

```asm
0x1400ec5b8  mov     rax, rsp
0x1400ec5bb  mov     [rax+8], rbx
0x1400ec5bf  mov     [rax+10h], rsi
0x1400ec5c3  mov     [rax+20h], r9
0x1400ec5c7  mov     [rax+18h], r8d
0x1400ec5cb  push    rdi
0x1400ec5cc  push    r14
0x1400ec5ce  push    r15
0x1400ec5d0  sub     rsp, 0C0h
0x1400ec5d7  mov     [rsp+0D8h+var_70], rsp
0x1400ec5dc  mov     rdi, rdx
0x1400ec5df  xor     r15d, r15d
0x1400ec5e2  mov     ebx, r15d
0x1400ec5e5  mov     [rax-78h], rbx
0x1400ec5e9  mov     qword ptr [rax+20h], 0FFFFFFFFFFFFFFFFh
0x1400ec5f1  xorps   xmm0, xmm0
0x1400ec5f4  movups  xmmword ptr [rax-68h], xmm0
0x1400ec5f8  test    rdx, rdx
0x1400ec5fb  jz      loc_1400EC7DC
0x1400ec601  xor     r9d, r9d; DirectoryInfo
0x1400ec604  xor     r8d, r8d; NtFileNamePart
0x1400ec607  lea     rdx, [rax-68h]; NtPathName
0x1400ec60b  lea     rcx, DosPathName; "\\\\.\\FltMgr"
0x1400ec612  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x1400ec618  test    al, al
0x1400ec61a  jnz     short loc_1400EC626
0x1400ec61c  mov     edi, 80070003h
0x1400ec621  jmp     loc_1400EC7E1
0x1400ec626  xor     eax, eax
0x1400ec628  mov     dword ptr [rsp+0D8h+ObjectAttributes+4], eax
0x1400ec62f  xorps   xmm0, xmm0
0x1400ec632  movups  xmmword ptr [rsp+0D8h+ObjectAttributes.Length], xmm0
0x1400ec63a  movups  xmmword ptr [rsp+0D8h+ObjectAttributes.ObjectName], xmm0
0x1400ec642  movups  xmmword ptr [rsp+0D8h+ObjectAttributes+1Ch], xmm0
0x1400ec64a  mov     [rsp+0D8h+ObjectAttributes.Length], 30h ; '0'
0x1400ec655  mov     [rsp+0D8h+ObjectAttributes.RootDirectory], r15
0x1400ec65d  mov     [rsp+0D8h+ObjectAttributes.Attributes], 40h ; '@'
0x1400ec668  lea     rax, [rsp+0D8h+var_68]
0x1400ec66d  mov     [rsp+0D8h+ObjectAttributes.ObjectName], rax
0x1400ec675  movdqu  xmmword ptr [rsp+0D8h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400ec67e  movups  xmmword ptr [rsp+0D8h+IoStatusBlock], xmm0
0x1400ec686  mov     [rsp+0D8h+EaLength], r15d; EaLength
0x1400ec68b  mov     [rsp+0D8h+EaBuffer], r15; EaBuffer
0x1400ec690  mov     [rsp+0D8h+CreateOptions], r15d; CreateOptions
0x1400ec695  mov     [rsp+0D8h+CreateDisposition], 1; CreateDisposition
0x1400ec69d  mov     [rsp+0D8h+ShareAccess], 3; ShareAccess
0x1400ec6a5  mov     [rsp+0D8h+FileAttributes], 80h; int
0x1400ec6ad  mov     [rsp+0D8h+AllocationSize], r15; int
0x1400ec6b2  lea     r9, [rsp+0D8h+IoStatusBlock]; IoStatusBlock
0x1400ec6ba  lea     r8, [rsp+0D8h+ObjectAttributes]; ObjectAttributes
0x1400ec6c2  mov     edx, 12019Fh; DesiredAccess
0x1400ec6c7  lea     rcx, [rsp+0D8h+FileHandle]; FileHandle
0x1400ec6cf  call    cs:__imp_NtCreateFile
0x1400ec6d5  cmp     [rsp+0D8h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x1400ec6de  jnz     short loc_1400EC720
0x1400ec6e0  mov     ecx, eax
0x1400ec6e2  call    FilterHResultFromNtStatus
0x1400ec6e7  mov     dword ptr [rsp+0D8h+arg_10], eax
0x1400ec6ee  lea     rdx, loc_1400EC700
0x1400ec6f5  mov     rcx, [rsp+0D8h+var_70]
0x1400ec6fa  call    _local_unwind_0
0x1400ec6ff  nop
0x1400ec700  mov     eax, dword ptr [rsp+0D8h+arg_10]
0x1400ec707  lea     r11, [rsp+0D8h+var_18]
0x1400ec70f  mov     rbx, [r11+20h]
0x1400ec713  mov     rsi, [r11+28h]
0x1400ec717  mov     rsp, r11
0x1400ec71a  pop     r15
0x1400ec71c  pop     r14
0x1400ec71e  pop     rdi
0x1400ec71f  retn
0x1400ec720  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400ec724  inc     rax
0x1400ec727  cmp     [rdi+rax*2], r15w
0x1400ec72c  jnz     short loc_1400EC724
0x1400ec72e  add     ax, ax
0x1400ec731  movzx   esi, ax
0x1400ec734  lea     r14d, [rsi+22h]
0x1400ec738  mov     r8d, r14d; Size
0x1400ec73b  mov     rcx, gs:60h
0x1400ec744  xor     edx, edx; Flags
0x1400ec746  mov     rcx, [rcx+30h]; HeapHandle
0x1400ec74a  call    cs:__imp_RtlAllocateHeap
0x1400ec750  mov     rbx, rax
0x1400ec753  mov     [rsp+0D8h+var_78], rax
0x1400ec758  test    rax, rax
0x1400ec75b  jnz     short loc_1400EC764
0x1400ec75d  mov     edi, 8007000Eh
0x1400ec762  jmp     short loc_1400EC7E1
0x1400ec764  mov     dword ptr [rax], 14000Eh
0x1400ec76a  movsd   xmm0, qword ptr cs:aBindflt; "bindflt"
0x1400ec772  movsd   qword ptr [rax+14h], xmm0
0x1400ec777  mov     eax, dword ptr cs:aBindflt+8; "flt"
0x1400ec77d  mov     [rbx+1Ch], eax
0x1400ec780  movzx   eax, word ptr cs:aBindflt+0Ch; "t"
0x1400ec787  mov     [rbx+20h], ax
0x1400ec78b  mov     [rbx+4], si
0x1400ec78f  mov     eax, 22h ; '"'
0x1400ec794  mov     [rbx+6], ax
0x1400ec798  lea     rcx, [rbx+22h]; void *
0x1400ec79c  mov     r8, rsi; Size
0x1400ec79f  mov     rdx, rdi; Src
0x1400ec7a2  call    memcpy_0
0x1400ec7a7  mov     qword ptr [rbx+8], 1
0x1400ec7af  mov     [rbx+10h], r15d
0x1400ec7b3  lea     rax, [rsp+0D8h+arg_10]
0x1400ec7bb  mov     qword ptr [rsp+0D8h+ShareAccess], rax; __int64
0x1400ec7c0  mov     r9d, r14d
0x1400ec7c3  mov     r8, rbx
0x1400ec7c6  mov     edx, 88010h; FsControlCode
0x1400ec7cb  mov     rcx, [rsp+0D8h+FileHandle]; Handle
0x1400ec7d3  call    NtFilterpDeviceIoControl
0x1400ec7d8  mov     edi, eax
0x1400ec7da  jmp     short loc_1400EC7E1
0x1400ec7dc  mov     edi, 80070057h
0x1400ec7e1  mov     rcx, [rsp+0D8h+FileHandle]; Handle
0x1400ec7e9  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1400ec7ed  jz      short loc_1400EC7F5
0x1400ec7ef  call    cs:__imp_NtClose
0x1400ec7f5  test    rbx, rbx
0x1400ec7f8  jz      short loc_1400EC812
0x1400ec7fa  mov     rcx, gs:60h
0x1400ec803  mov     r8, rbx; P
0x1400ec806  xor     edx, edx; Flags
0x1400ec808  mov     rcx, [rcx+30h]; HeapHandle
0x1400ec80c  call    cs:__imp_RtlFreeHeap
0x1400ec812  cmp     [rsp+0D8h+P], r15
0x1400ec817  jz      short loc_1400EC833
0x1400ec819  mov     rcx, gs:60h
0x1400ec822  mov     r8, [rsp+0D8h+P]; P
0x1400ec827  xor     edx, edx; Flags
0x1400ec829  mov     rcx, [rcx+30h]; HeapHandle
0x1400ec82d  call    cs:__imp_RtlFreeHeap
0x1400ec833  mov     eax, edi
0x1400ec835  jmp     loc_1400EC707
0x1400fd01c  push    rbp
0x1400fd01e  sub     rsp, 60h
0x1400fd022  mov     rbp, rdx
0x1400fd025  mov     rcx, [rbp+0F8h]; Handle
0x1400fd02c  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1400fd030  jz      short loc_1400FD039
0x1400fd032  call    cs:__imp_NtClose
0x1400fd038  nop
0x1400fd039  mov     r8, [rbp+60h]; P
0x1400fd03d  test    r8, r8
0x1400fd040  jz      short loc_1400FD058
0x1400fd042  mov     rcx, gs:60h
0x1400fd04b  xor     edx, edx; Flags
0x1400fd04d  mov     rcx, [rcx+30h]; HeapHandle
0x1400fd051  call    cs:__imp_RtlFreeHeap
0x1400fd057  nop
0x1400fd058  cmp     qword ptr [rbp+78h], 0
0x1400fd05d  jz      short loc_1400FD079
0x1400fd05f  mov     rcx, gs:60h
0x1400fd068  mov     r8, [rbp+78h]; P
0x1400fd06c  xor     edx, edx; Flags
0x1400fd06e  mov     rcx, [rcx+30h]; HeapHandle
0x1400fd072  call    cs:__imp_RtlFreeHeap
0x1400fd078  nop
0x1400fd079  add     rsp, 60h
0x1400fd07d  pop     rbp
0x1400fd07e  retn
```
