# NtFilterpCommonAttach

- ea: `0x14024d284`
- end: `0x14024d52b`
- name: `NtFilterpCommonAttach`
- size: `679`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, loader_planting, broker_com_uri`

## callers

- `0x14024d534`

## callees

- `0x1401365b9`
- `0x14024cce0`
- `0x14024d284`
- `0x14024d9f8`
- `0x1402a0e68`

## import_xrefs

- `ntdll!RtlDosPathNameToNtPathName_U` at `0x14024d2de`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x14024d2de`
- `ntdll!NtCreateFile` at `0x14024d3a1`
- `ntdll!NtCreateFile` at `0x14024d3a1`
- `ntdll!RtlAllocateHeap` at `0x14024d423`
- `ntdll!RtlAllocateHeap` at `0x14024d423`
- `ntdll!NtClose` at `0x14024d4ce`
- `ntdll!NtClose` at `0x1402ba121`
- `ntdll!NtClose` at `0x14024d4ce`
- `ntdll!NtClose` at `0x1402ba121`
- `ntdll!RtlFreeHeap` at `0x14024d4f1`
- `ntdll!RtlFreeHeap` at `0x14024d518`
- `ntdll!RtlFreeHeap` at `0x1402ba146`
- `ntdll!RtlFreeHeap` at `0x1402ba16d`
- `ntdll!RtlFreeHeap` at `0x14024d4f1`
- `ntdll!RtlFreeHeap` at `0x14024d518`
- `ntdll!RtlFreeHeap` at `0x1402ba146`
- `ntdll!RtlFreeHeap` at `0x1402ba16d`

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
        local_unwind_0(v15, &loc_14024D3D8);
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
0x14024d284  mov     rax, rsp
0x14024d287  mov     [rax+8], rbx
0x14024d28b  mov     [rax+10h], rsi
0x14024d28f  mov     [rax+20h], r9
0x14024d293  mov     [rax+18h], r8d
0x14024d297  push    rdi
0x14024d298  push    r14
0x14024d29a  push    r15
0x14024d29c  sub     rsp, 0C0h
0x14024d2a3  mov     [rsp+0D8h+var_70], rsp
0x14024d2a8  mov     rdi, rdx
0x14024d2ab  xor     r15d, r15d
0x14024d2ae  mov     ebx, r15d
0x14024d2b1  mov     [rax-78h], rbx
0x14024d2b5  mov     qword ptr [rax+20h], 0FFFFFFFFFFFFFFFFh
0x14024d2bd  xorps   xmm0, xmm0
0x14024d2c0  movups  xmmword ptr [rax-68h], xmm0
0x14024d2c4  test    rdx, rdx
0x14024d2c7  jz      loc_14024D4BB
0x14024d2cd  xor     r9d, r9d; DirectoryInfo
0x14024d2d0  xor     r8d, r8d; NtFileNamePart
0x14024d2d3  lea     rdx, [rax-68h]; NtPathName
0x14024d2d7  lea     rcx, DosPathName; "\\\\.\\FltMgr"
0x14024d2de  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x14024d2e5  nop     dword ptr [rax+rax+00h]
0x14024d2ea  test    al, al
0x14024d2ec  jnz     short loc_14024D2F8
0x14024d2ee  mov     edi, 80070003h
0x14024d2f3  jmp     loc_14024D4C0
0x14024d2f8  xor     eax, eax
0x14024d2fa  mov     dword ptr [rsp+0D8h+ObjectAttributes+4], eax
0x14024d301  xorps   xmm0, xmm0
0x14024d304  movups  xmmword ptr [rsp+0D8h+ObjectAttributes.Length], xmm0
0x14024d30c  movups  xmmword ptr [rsp+0D8h+ObjectAttributes.ObjectName], xmm0
0x14024d314  movups  xmmword ptr [rsp+0D8h+ObjectAttributes+1Ch], xmm0
0x14024d31c  mov     [rsp+0D8h+ObjectAttributes.Length], 30h ; '0'
0x14024d327  mov     [rsp+0D8h+ObjectAttributes.RootDirectory], r15
0x14024d32f  mov     [rsp+0D8h+ObjectAttributes.Attributes], 40h ; '@'
0x14024d33a  lea     rax, [rsp+0D8h+var_68]
0x14024d33f  mov     [rsp+0D8h+ObjectAttributes.ObjectName], rax
0x14024d347  movdqu  xmmword ptr [rsp+0D8h+ObjectAttributes.SecurityDescriptor], xmm0
0x14024d350  movups  xmmword ptr [rsp+0D8h+IoStatusBlock], xmm0
0x14024d358  mov     [rsp+0D8h+EaLength], r15d; EaLength
0x14024d35d  mov     [rsp+0D8h+EaBuffer], r15; EaBuffer
0x14024d362  mov     [rsp+0D8h+CreateOptions], r15d; CreateOptions
0x14024d367  mov     [rsp+0D8h+CreateDisposition], 1; CreateDisposition
0x14024d36f  mov     [rsp+0D8h+ShareAccess], 3; ShareAccess
0x14024d377  mov     [rsp+0D8h+FileAttributes], 80h; int
0x14024d37f  mov     [rsp+0D8h+AllocationSize], r15; int
0x14024d384  lea     r9, [rsp+0D8h+IoStatusBlock]; IoStatusBlock
0x14024d38c  lea     r8, [rsp+0D8h+ObjectAttributes]; ObjectAttributes
0x14024d394  mov     edx, 12019Fh; DesiredAccess
0x14024d399  lea     rcx, [rsp+0D8h+FileHandle]; FileHandle
0x14024d3a1  call    cs:__imp_NtCreateFile
0x14024d3a8  nop     dword ptr [rax+rax+00h]
0x14024d3ad  cmp     [rsp+0D8h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x14024d3b6  jnz     short loc_14024D3F9
0x14024d3b8  mov     ecx, eax
0x14024d3ba  call    FilterHResultFromNtStatus
0x14024d3bf  mov     dword ptr [rsp+0D8h+arg_10], eax
0x14024d3c6  lea     rdx, loc_14024D3D8
0x14024d3cd  mov     rcx, [rsp+0D8h+var_70]
0x14024d3d2  call    _local_unwind_0
0x14024d3d7  nop
0x14024d3d8  mov     eax, dword ptr [rsp+0D8h+arg_10]
0x14024d3df  lea     r11, [rsp+0D8h+var_18]
0x14024d3e7  mov     rbx, [r11+20h]
0x14024d3eb  mov     rsi, [r11+28h]
0x14024d3ef  mov     rsp, r11
0x14024d3f2  pop     r15
0x14024d3f4  pop     r14
0x14024d3f6  pop     rdi
0x14024d3f7  retn
0x14024d3f9  or      rax, 0FFFFFFFFFFFFFFFFh
0x14024d3fd  inc     rax
0x14024d400  cmp     [rdi+rax*2], r15w
0x14024d405  jnz     short loc_14024D3FD
0x14024d407  add     ax, ax
0x14024d40a  movzx   esi, ax
0x14024d40d  lea     r14d, [rsi+22h]
0x14024d411  mov     r8d, r14d; Size
0x14024d414  mov     rcx, gs:60h
0x14024d41d  xor     edx, edx; Flags
0x14024d41f  mov     rcx, [rcx+30h]; HeapHandle
0x14024d423  call    cs:__imp_RtlAllocateHeap
0x14024d42a  nop     dword ptr [rax+rax+00h]
0x14024d42f  mov     rbx, rax
0x14024d432  mov     [rsp+0D8h+var_78], rax
0x14024d437  test    rax, rax
0x14024d43a  jnz     short loc_14024D443
0x14024d43c  mov     edi, 8007000Eh
0x14024d441  jmp     short loc_14024D4C0
0x14024d443  mov     dword ptr [rax], 14000Eh
0x14024d449  movsd   xmm0, qword ptr cs:aBindflt; "bindflt"
0x14024d451  movsd   qword ptr [rax+14h], xmm0
0x14024d456  mov     eax, dword ptr cs:aBindflt+8; "flt"
0x14024d45c  mov     [rbx+1Ch], eax
0x14024d45f  movzx   eax, word ptr cs:aBindflt+0Ch; "t"
0x14024d466  mov     [rbx+20h], ax
0x14024d46a  mov     [rbx+4], si
0x14024d46e  mov     eax, 22h ; '"'
0x14024d473  mov     [rbx+6], ax
0x14024d477  lea     rcx, [rbx+22h]; void *
0x14024d47b  mov     r8, rsi; Size
0x14024d47e  mov     rdx, rdi; Src
0x14024d481  call    memcpy_0
0x14024d486  mov     qword ptr [rbx+8], 1
0x14024d48e  mov     [rbx+10h], r15d
0x14024d492  lea     rax, [rsp+0D8h+arg_10]
0x14024d49a  mov     qword ptr [rsp+0D8h+ShareAccess], rax; __int64
0x14024d49f  mov     r9d, r14d
0x14024d4a2  mov     r8, rbx
0x14024d4a5  mov     edx, 88010h; FsControlCode
0x14024d4aa  mov     rcx, [rsp+0D8h+FileHandle]; Handle
0x14024d4b2  call    NtFilterpDeviceIoControl
0x14024d4b7  mov     edi, eax
0x14024d4b9  jmp     short loc_14024D4C0
0x14024d4bb  mov     edi, 80070057h
0x14024d4c0  mov     rcx, [rsp+0D8h+FileHandle]; Handle
0x14024d4c8  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14024d4cc  jz      short loc_14024D4DA
0x14024d4ce  call    cs:__imp_NtClose
0x14024d4d5  nop     dword ptr [rax+rax+00h]
0x14024d4da  test    rbx, rbx
0x14024d4dd  jz      short loc_14024D4FD
0x14024d4df  mov     rcx, gs:60h
0x14024d4e8  mov     r8, rbx; P
0x14024d4eb  xor     edx, edx; Flags
0x14024d4ed  mov     rcx, [rcx+30h]; HeapHandle
0x14024d4f1  call    cs:__imp_RtlFreeHeap
0x14024d4f8  nop     dword ptr [rax+rax+00h]
0x14024d4fd  cmp     [rsp+0D8h+P], r15
0x14024d502  jz      short loc_14024D524
0x14024d504  mov     rcx, gs:60h
0x14024d50d  mov     r8, [rsp+0D8h+P]; P
0x14024d512  xor     edx, edx; Flags
0x14024d514  mov     rcx, [rcx+30h]; HeapHandle
0x14024d518  call    cs:__imp_RtlFreeHeap
0x14024d51f  nop     dword ptr [rax+rax+00h]
0x14024d524  mov     eax, edi
0x14024d526  jmp     loc_14024D3DF
0x1402ba10b  push    rbp
0x1402ba10d  sub     rsp, 60h
0x1402ba111  mov     rbp, rdx
0x1402ba114  mov     rcx, [rbp+0F8h]; Handle
0x1402ba11b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1402ba11f  jz      short loc_1402BA12E
0x1402ba121  call    cs:__imp_NtClose
0x1402ba128  nop     dword ptr [rax+rax+00h]
0x1402ba12d  nop
0x1402ba12e  mov     r8, [rbp+60h]; P
0x1402ba132  test    r8, r8
0x1402ba135  jz      short loc_1402BA153
0x1402ba137  mov     rcx, gs:60h
0x1402ba140  xor     edx, edx; Flags
0x1402ba142  mov     rcx, [rcx+30h]; HeapHandle
0x1402ba146  call    cs:__imp_RtlFreeHeap
0x1402ba14d  nop     dword ptr [rax+rax+00h]
0x1402ba152  nop
0x1402ba153  cmp     qword ptr [rbp+78h], 0
0x1402ba158  jz      short loc_1402BA17A
0x1402ba15a  mov     rcx, gs:60h
0x1402ba163  mov     r8, [rbp+78h]; P
0x1402ba167  xor     edx, edx; Flags
0x1402ba169  mov     rcx, [rcx+30h]; HeapHandle
0x1402ba16d  call    cs:__imp_RtlFreeHeap
0x1402ba174  nop     dword ptr [rax+rax+00h]
0x1402ba179  nop
0x1402ba17a  add     rsp, 60h
0x1402ba17e  pop     rbp
0x1402ba17f  retn
```
