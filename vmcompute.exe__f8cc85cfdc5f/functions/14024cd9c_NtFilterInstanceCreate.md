# NtFilterInstanceCreate

- ea: `0x14024cd9c`
- end: `0x14024d051`
- name: `NtFilterInstanceCreate`
- size: `693`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x14024d534`

## callees

- `0x1401365b9`
- `0x14024cce0`
- `0x14024cd9c`
- `0x14024d9f8`

## import_xrefs

- `ntdll!RtlDosPathNameToNtPathName_U` at `0x14024cdf1`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x14024cdf1`
- `ntdll!NtCreateFile` at `0x14024ceb8`
- `ntdll!NtCreateFile` at `0x14024ceb8`
- `ntdll!RtlAllocateHeap` at `0x14024cf06`
- `ntdll!RtlAllocateHeap` at `0x14024cf06`
- `ntdll!NtClose` at `0x14024cff1`
- `ntdll!NtClose` at `0x1402ba033`
- `ntdll!NtClose` at `0x14024cff1`
- `ntdll!NtClose` at `0x1402ba033`
- `ntdll!RtlFreeHeap` at `0x14024cfd3`
- `ntdll!RtlFreeHeap` at `0x14024d024`
- `ntdll!RtlFreeHeap` at `0x1402ba010`
- `ntdll!RtlFreeHeap` at `0x1402ba064`
- `ntdll!RtlFreeHeap` at `0x14024cfd3`
- `ntdll!RtlFreeHeap` at `0x14024d024`
- `ntdll!RtlFreeHeap` at `0x1402ba010`
- `ntdll!RtlFreeHeap` at `0x1402ba064`

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
0x14024cd9c  mov     rax, rsp
0x14024cd9f  mov     [rax+20h], r9
0x14024cda3  mov     [rax+8], rcx
0x14024cda7  push    rbx
0x14024cda8  push    rsi
0x14024cda9  push    rdi
0x14024cdaa  push    r12
0x14024cdac  push    r13
0x14024cdae  push    r14
0x14024cdb0  push    r15
0x14024cdb2  sub     rsp, 0C0h
0x14024cdb9  mov     rsi, r9
0x14024cdbc  mov     r14, rdx
0x14024cdbf  xor     r13d, r13d
0x14024cdc2  mov     edi, r13d
0x14024cdc5  mov     [rsp+0F8h+var_90], r13
0x14024cdca  mov     [rsp+0F8h+var_98], r13d
0x14024cdcf  mov     qword ptr [rax+8], 0FFFFFFFFFFFFFFFFh
0x14024cdd7  xorps   xmm0, xmm0
0x14024cdda  movups  xmmword ptr [rsp+0F8h+NtPathName.Length], xmm0
0x14024cddf  xor     r9d, r9d; DirectoryInfo
0x14024cde2  xor     r8d, r8d; NtFileNamePart
0x14024cde5  lea     rdx, [rsp+0F8h+NtPathName]; NtPathName
0x14024cdea  lea     rcx, DosPathName; "\\\\.\\FltMgr"
0x14024cdf1  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x14024cdf8  nop     dword ptr [rax+rax+00h]
0x14024cdfd  test    al, al
0x14024cdff  jnz     short loc_14024CE0F
0x14024ce01  mov     ebx, 80070003h
0x14024ce06  mov     [rsp+0F8h+var_98], ebx
0x14024ce0a  jmp     loc_14024CFBC
0x14024ce0f  xor     eax, eax
0x14024ce11  mov     dword ptr [rsp+0F8h+ObjectAttributes+4], eax
0x14024ce18  xorps   xmm0, xmm0
0x14024ce1b  movups  xmmword ptr [rsp+0F8h+ObjectAttributes.Length], xmm0
0x14024ce23  movups  xmmword ptr [rsp+0F8h+ObjectAttributes.ObjectName], xmm0
0x14024ce2b  movups  xmmword ptr [rsp+0F8h+ObjectAttributes+1Ch], xmm0
0x14024ce33  mov     [rsp+0F8h+ObjectAttributes.Length], 30h ; '0'
0x14024ce3e  mov     [rsp+0F8h+ObjectAttributes.RootDirectory], r13
0x14024ce46  mov     [rsp+0F8h+ObjectAttributes.Attributes], 40h ; '@'
0x14024ce51  lea     rax, [rsp+0F8h+NtPathName]
0x14024ce56  mov     [rsp+0F8h+ObjectAttributes.ObjectName], rax
0x14024ce5e  movdqu  xmmword ptr [rsp+0F8h+ObjectAttributes.SecurityDescriptor], xmm0
0x14024ce67  movups  xmmword ptr [rsp+0F8h+IoStatusBlock], xmm0
0x14024ce6f  mov     [rsp+0F8h+EaLength], r13d; EaLength
0x14024ce74  mov     [rsp+0F8h+EaBuffer], r13; EaBuffer
0x14024ce79  mov     [rsp+0F8h+CreateOptions], r13d; CreateOptions
0x14024ce7e  mov     [rsp+0F8h+CreateDisposition], 1; CreateDisposition
0x14024ce86  mov     [rsp+0F8h+ShareAccess], 3; ShareAccess
0x14024ce8e  mov     [rsp+0F8h+FileAttributes], 80h; int
0x14024ce96  mov     [rsp+0F8h+AllocationSize], r13; int
0x14024ce9b  lea     r9, [rsp+0F8h+IoStatusBlock]; IoStatusBlock
0x14024cea3  lea     r8, [rsp+0F8h+ObjectAttributes]; ObjectAttributes
0x14024ceab  mov     edx, 12019Fh; DesiredAccess
0x14024ceb0  lea     rcx, [rsp+0F8h+FileHandle]; FileHandle
0x14024ceb8  call    cs:__imp_NtCreateFile
0x14024cebf  nop     dword ptr [rax+rax+00h]
0x14024cec4  cmp     [rsp+0F8h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x14024cecd  jnz     short loc_14024CEDB
0x14024cecf  mov     ecx, eax
0x14024ced1  call    FilterHResultFromNtStatus
0x14024ced6  jmp     loc_14024CFB6
0x14024cedb  or      rax, 0FFFFFFFFFFFFFFFFh
0x14024cedf  inc     rax
0x14024cee2  cmp     [r14+rax*2], r13w
0x14024cee7  jnz     short loc_14024CEDF
0x14024cee9  add     ax, ax
0x14024ceec  movzx   r15d, ax
0x14024cef0  lea     r12d, [r15+22h]
0x14024cef4  mov     r8d, r12d; Size
0x14024cef7  mov     rcx, gs:60h
0x14024cf00  xor     edx, edx; Flags
0x14024cf02  mov     rcx, [rcx+30h]; HeapHandle
0x14024cf06  call    cs:__imp_RtlAllocateHeap
0x14024cf0d  nop     dword ptr [rax+rax+00h]
0x14024cf12  mov     rdi, rax
0x14024cf15  mov     [rsp+0F8h+var_90], rax
0x14024cf1a  test    rax, rax
0x14024cf1d  jnz     short loc_14024CF29
0x14024cf1f  mov     ebx, 8007000Eh
0x14024cf24  jmp     loc_14024CE06
0x14024cf29  mov     dword ptr [rax+4], 8
0x14024cf30  lea     rbx, [rax+8]
0x14024cf34  mov     dword ptr [rax], 1
0x14024cf3a  mov     dword ptr [rbx], 0C000Eh
0x14024cf40  mov     edx, 0Eh
0x14024cf45  movzx   ecx, word ptr [rbx+2]
0x14024cf49  movsd   xmm0, qword ptr cs:aBindflt; "bindflt"
0x14024cf51  movsd   qword ptr [rcx+rbx], xmm0
0x14024cf56  mov     eax, dword ptr cs:aBindflt+8; "flt"
0x14024cf5c  mov     [rcx+rbx+8], eax
0x14024cf60  movzx   eax, word ptr cs:aBindflt+0Ch; "t"
0x14024cf67  mov     [rcx+rbx+0Ch], ax
0x14024cf6c  movzx   eax, word ptr [rbx+2]
0x14024cf70  add     ax, dx
0x14024cf73  movzx   ecx, ax
0x14024cf76  mov     [rbx+6], cx
0x14024cf7a  mov     [rbx+4], r15w
0x14024cf7f  add     rcx, rbx; void *
0x14024cf82  mov     r8, r15; Size
0x14024cf85  mov     rdx, r14; Src
0x14024cf88  call    memcpy_0
0x14024cf8d  mov     [rbx+8], r13d
0x14024cf91  lea     rax, [rsp+0F8h+arg_10]
0x14024cf99  mov     qword ptr [rsp+0F8h+ShareAccess], rax; __int64
0x14024cf9e  mov     r9d, r12d
0x14024cfa1  mov     r8, rdi
0x14024cfa4  mov     edx, 8400Ch; FsControlCode
0x14024cfa9  mov     rcx, [rsp+0F8h+FileHandle]; Handle
0x14024cfb1  call    NtFilterpDeviceIoControl
0x14024cfb6  mov     [rsp+0F8h+var_98], eax
0x14024cfba  mov     ebx, eax
0x14024cfbc  test    rdi, rdi
0x14024cfbf  jz      short loc_14024CFDF
0x14024cfc1  mov     rcx, gs:60h
0x14024cfca  mov     r8, rdi; P
0x14024cfcd  xor     edx, edx; Flags
0x14024cfcf  mov     rcx, [rcx+30h]; HeapHandle
0x14024cfd3  call    cs:__imp_RtlFreeHeap
0x14024cfda  nop     dword ptr [rax+rax+00h]
0x14024cfdf  test    ebx, ebx
0x14024cfe1  jns     short loc_14024D009
0x14024cfe3  mov     rcx, [rsp+0F8h+FileHandle]; Handle
0x14024cfeb  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14024cfef  jz      short loc_14024D009
0x14024cff1  call    cs:__imp_NtClose
0x14024cff8  nop     dword ptr [rax+rax+00h]
0x14024cffd  mov     [rsp+0F8h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x14024d009  cmp     [rsp+0F8h+NtPathName.Buffer], r13
0x14024d00e  jz      short loc_14024D030
0x14024d010  mov     rcx, gs:60h
0x14024d019  mov     r8, [rsp+0F8h+NtPathName.Buffer]; P
0x14024d01e  xor     edx, edx; Flags
0x14024d020  mov     rcx, [rcx+30h]; HeapHandle
0x14024d024  call    cs:__imp_RtlFreeHeap
0x14024d02b  nop     dword ptr [rax+rax+00h]
0x14024d030  mov     rax, [rsp+0F8h+FileHandle]
0x14024d038  mov     [rsi], rax
0x14024d03b  mov     eax, ebx
0x14024d03d  add     rsp, 0C0h
0x14024d044  pop     r15
0x14024d046  pop     r14
0x14024d048  pop     r13
0x14024d04a  pop     r12
0x14024d04c  pop     rdi
0x14024d04d  pop     rsi
0x14024d04e  pop     rbx
0x14024d04f  retn
0x1402b9fef  push    rbp
0x1402b9ff1  sub     rsp, 60h
0x1402b9ff5  mov     rbp, rdx
0x1402b9ff8  mov     r8, [rbp+68h]; P
0x1402b9ffc  test    r8, r8
0x1402b9fff  jz      short loc_1402BA01D
0x1402ba001  mov     rcx, gs:60h
0x1402ba00a  xor     edx, edx; Flags
0x1402ba00c  mov     rcx, [rcx+30h]; HeapHandle
0x1402ba010  call    cs:__imp_RtlFreeHeap
0x1402ba017  nop     dword ptr [rax+rax+00h]
0x1402ba01c  nop
0x1402ba01d  test    dword ptr [rbp+60h], 80000000h
0x1402ba024  jz      short loc_1402BA04A
0x1402ba026  mov     rcx, [rbp+100h]; Handle
0x1402ba02d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1402ba031  jz      short loc_1402BA04A
0x1402ba033  call    cs:__imp_NtClose
0x1402ba03a  nop     dword ptr [rax+rax+00h]
0x1402ba03f  mov     qword ptr [rbp+100h], 0FFFFFFFFFFFFFFFFh
0x1402ba04a  cmp     qword ptr [rbp+78h], 0
0x1402ba04f  jz      short loc_1402BA071
0x1402ba051  mov     rcx, gs:60h
0x1402ba05a  mov     r8, [rbp+78h]; P
0x1402ba05e  xor     edx, edx; Flags
0x1402ba060  mov     rcx, [rcx+30h]; HeapHandle
0x1402ba064  call    cs:__imp_RtlFreeHeap
0x1402ba06b  nop     dword ptr [rax+rax+00h]
0x1402ba070  nop
0x1402ba071  mov     rcx, [rbp+118h]
0x1402ba078  mov     rax, [rbp+100h]
0x1402ba07f  mov     [rcx], rax
0x1402ba082  add     rsp, 60h
0x1402ba086  pop     rbp
0x1402ba087  retn
```
