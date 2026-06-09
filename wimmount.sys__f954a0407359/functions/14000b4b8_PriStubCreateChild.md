# PriStubCreateChild

- ea: `0x14000b4b8`
- end: `0x14000b6ab`
- name: `PriStubCreateChild`
- size: `499`
- prototype: `__int64 __fastcall(void *, ACCESS_MASK, ULONG, ULONG, ULONG FileAttributes, __int128 *, void **TargetHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14000b110`

## callees

- `0x14000ae54`
- `0x14000aee0`
- `0x14000b4b8`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14000b65e`
- `ntoskrnl!ZwClose` at `0x14000b65e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b68c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b68c`
- `ntoskrnl!ZwDuplicateObject` at `0x14000b614`
- `ntoskrnl!ZwDuplicateObject` at `0x14000b614`
- `FLTMGR!FltObjectDereference` at `0x14000b633`
- `FLTMGR!FltObjectDereference` at `0x14000b64a`
- `FLTMGR!FltObjectDereference` at `0x14000b633`
- `FLTMGR!FltObjectDereference` at `0x14000b64a`
- `FLTMGR!FltClose` at `0x14000b673`
- `FLTMGR!FltClose` at `0x14000b673`
- `FLTMGR!FltCreateFile` at `0x14000b5db`
- `FLTMGR!FltCreateFile` at `0x14000b5db`

## pseudocode

```c
__int64 __fastcall PriStubCreateChild(
        void *a1,
        ACCESS_MASK a2,
        ULONG a3,
        ULONG a4,
        ULONG FileAttributes,
        __int128 *a6,
        void **TargetHandle)
{
  void *v9; // rdi
  int ObjectsFromUserHandle; // eax
  HANDLE v11; // rsi
  NTSTATUS v12; // ebx
  __int128 v13; // xmm0
  void *v15; // [rsp+80h] [rbp-61h] BYREF
  void *FileHandle; // [rsp+88h] [rbp-59h] BYREF
  HANDLE Handle; // [rsp+90h] [rbp-51h] BYREF
  __int128 v18; // [rsp+98h] [rbp-49h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A8h] [rbp-39h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+D8h] [rbp-9h] BYREF

  Handle = 0;
  FileHandle = 0;
  v9 = 0;
  v15 = 0;
  v18 = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  ObjectsFromUserHandle = PriGetObjectsFromUserHandle(a1, 0x100131u, 0, (__int64)&Handle, 0);
  v11 = Handle;
  v12 = ObjectsFromUserHandle;
  if ( ObjectsFromUserHandle >= 0 )
  {
    v12 = PriDuplicateBufferFromUser(&v15, *((_QWORD *)a6 + 1), *((unsigned __int16 *)a6 + 1));
    if ( v12 < 0 )
    {
      v9 = v15;
    }
    else
    {
      v13 = *a6;
      v9 = v15;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)&v18;
      *(_QWORD *)&v18 = v13;
      *((_QWORD *)&v18 + 1) = v15;
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = v11;
      ObjectAttributes.Attributes = 512;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v12 = FltCreateFile(
              0,
              0,
              &FileHandle,
              a2,
              &ObjectAttributes,
              &IoStatusBlock,
              0,
              FileAttributes,
              7u,
              a3,
              a4,
              0,
              0,
              0);
      if ( v12 >= 0 )
        v12 = ZwDuplicateObject(
                (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                FileHandle,
                (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                TargetHandle,
                0,
                0,
                6u);
    }
  }
  if ( v11 )
    ZwClose(v11);
  if ( FileHandle )
    FltClose(FileHandle);
  if ( v9 )
    ExFreePoolWithTag(v9, 0x574D6365u);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14000b4b8  mov     [rsp-8+DesiredAccess], edx
0x14000b4bc  push    rbp
0x14000b4bd  push    rbx
0x14000b4be  push    rsi
0x14000b4bf  push    rdi
0x14000b4c0  push    r12
0x14000b4c2  push    r13
0x14000b4c4  lea     rbp, [rsp-17h]
0x14000b4c9  sub     rsp, 0F8h
0x14000b4d0  xor     edx, edx
0x14000b4d2  xorps   xmm0, xmm0
0x14000b4d5  mov     [rsp+120h+AllocationSize], rdx; __int64
0x14000b4da  xor     eax, eax
0x14000b4dc  lea     rax, [rbp+3Fh+Handle]
0x14000b4e0  mov     [rbp+3Fh+Filter], rdx
0x14000b4e4  mov     [rsp+120h+IoStatusBlock], rax; __int64
0x14000b4e9  mov     r12d, r9d
0x14000b4ec  mov     [rsp+120h+ObjectAttributes], rdx; __int64
0x14000b4f1  lea     r9, [rbp+3Fh+Instance]
0x14000b4f5  mov     r13d, r8d
0x14000b4f8  mov     [rbp+3Fh+Instance], rdx
0x14000b4fc  mov     [rbp+3Fh+Handle], rdx
0x14000b500  lea     r8, [rbp+3Fh+Filter]
0x14000b504  mov     [rbp+3Fh+FileHandle], rdx
0x14000b508  mov     edi, edx
0x14000b50a  mov     [rbp+3Fh+var_A0], rdx
0x14000b50e  mov     edx, 100131h; DesiredAccess
0x14000b513  movups  xmmword ptr [rbp+3Fh+var_78.ObjectName], xmm0
0x14000b517  movups  [rbp+3Fh+var_88], xmm0
0x14000b51b  movups  xmmword ptr [rbp+3Fh+var_78.Length], xmm0
0x14000b51f  movups  xmmword ptr [rbp+3Fh+var_78+1Ch], xmm0
0x14000b523  movups  xmmword ptr [rbp+3Fh+var_48], xmm0
0x14000b527  call    PriGetObjectsFromUserHandle
0x14000b52c  mov     rsi, [rbp+3Fh+Handle]
0x14000b530  mov     ebx, eax
0x14000b532  test    eax, eax
0x14000b534  js      loc_14000B628
0x14000b53a  mov     rdi, [rbp+3Fh+arg_28]
0x14000b53e  lea     rcx, [rbp+3Fh+var_A0]
0x14000b542  movzx   r8d, word ptr [rdi+2]
0x14000b547  mov     rdx, [rdi+8]
0x14000b54b  call    PriDuplicateBufferFromUser
0x14000b550  xor     ecx, ecx
0x14000b552  mov     ebx, eax
0x14000b554  test    eax, eax
0x14000b556  js      loc_14000B624
0x14000b55c  movups  xmm0, xmmword ptr [rdi]
0x14000b55f  mov     rdi, [rbp+3Fh+var_A0]
0x14000b563  lea     rax, [rbp+3Fh+var_88]
0x14000b567  mov     r9d, [rbp+3Fh+DesiredAccess]; DesiredAccess
0x14000b56b  lea     r8, [rbp+3Fh+FileHandle]; FileHandle
0x14000b56f  mov     rdx, [rbp+3Fh+Instance]; Instance
0x14000b573  mov     [rsp+120h+Flags], ecx; Flags
0x14000b577  mov     [rsp+120h+EaLength], ecx; EaLength
0x14000b57b  mov     [rsp+120h+EaBuffer], rcx; EaBuffer
0x14000b580  mov     [rsp+120h+CreateOptions], r12d; CreateOptions
0x14000b585  mov     [rsp+120h+CreateDisposition], r13d; CreateDisposition
0x14000b58a  mov     [rbp+3Fh+var_78.ObjectName], rax
0x14000b58e  mov     eax, [rbp+3Fh+arg_20]
0x14000b591  mov     [rsp+120h+ShareAccess], 7; ShareAccess
0x14000b599  mov     [rsp+120h+FileAttributes], eax; FileAttributes
0x14000b59d  lea     rax, [rbp+3Fh+var_48]
0x14000b5a1  mov     [rsp+120h+AllocationSize], rcx; AllocationSize
0x14000b5a6  mov     rcx, [rbp+3Fh+Filter]; Filter
0x14000b5aa  mov     [rsp+120h+IoStatusBlock], rax; IoStatusBlock
0x14000b5af  lea     rax, [rbp+3Fh+var_78]
0x14000b5b3  movdqu  [rbp+3Fh+var_88], xmm0
0x14000b5b8  mov     [rsp+120h+ObjectAttributes], rax; ObjectAttributes
0x14000b5bd  xorps   xmm0, xmm0
0x14000b5c0  mov     qword ptr [rbp+3Fh+var_88+8], rdi
0x14000b5c4  mov     [rbp+3Fh+var_78.Length], 30h ; '0'
0x14000b5cb  mov     [rbp+3Fh+var_78.RootDirectory], rsi
0x14000b5cf  mov     [rbp+3Fh+var_78.Attributes], 200h
0x14000b5d6  movdqu  xmmword ptr [rbp+3Fh+var_78.SecurityDescriptor], xmm0
0x14000b5db  call    cs:__imp_FltCreateFile
0x14000b5e2  nop     dword ptr [rax+rax+00h]
0x14000b5e7  mov     ebx, eax
0x14000b5e9  test    eax, eax
0x14000b5eb  js      short loc_14000B628
0x14000b5ed  mov     r9, [rbp+3Fh+TargetHandle]; TargetHandle
0x14000b5f1  or      rcx, 0FFFFFFFFFFFFFFFFh; SourceProcessHandle
0x14000b5f5  mov     rdx, [rbp+3Fh+FileHandle]; SourceHandle
0x14000b5f9  mov     r8, rcx; TargetProcessHandle
0x14000b5fc  mov     dword ptr [rsp+120h+AllocationSize], 6; Options
0x14000b604  mov     dword ptr [rsp+120h+IoStatusBlock], 0; HandleAttributes
0x14000b60c  mov     dword ptr [rsp+120h+ObjectAttributes], 0; DesiredAccess
0x14000b614  call    cs:__imp_ZwDuplicateObject
0x14000b61b  nop     dword ptr [rax+rax+00h]
0x14000b620  mov     ebx, eax
0x14000b622  jmp     short loc_14000B628
0x14000b624  mov     rdi, [rbp+3Fh+var_A0]
0x14000b628  cmp     [rbp+3Fh+Filter], 0
0x14000b62d  jz      short loc_14000B63F
0x14000b62f  mov     rcx, [rbp+3Fh+Filter]; FltObject
0x14000b633  call    cs:__imp_FltObjectDereference
0x14000b63a  nop     dword ptr [rax+rax+00h]
0x14000b63f  cmp     [rbp+3Fh+Instance], 0
0x14000b644  jz      short loc_14000B656
0x14000b646  mov     rcx, [rbp+3Fh+Instance]; FltObject
0x14000b64a  call    cs:__imp_FltObjectDereference
0x14000b651  nop     dword ptr [rax+rax+00h]
0x14000b656  test    rsi, rsi
0x14000b659  jz      short loc_14000B66A
0x14000b65b  mov     rcx, rsi; Handle
0x14000b65e  call    cs:__imp_ZwClose
0x14000b665  nop     dword ptr [rax+rax+00h]
0x14000b66a  mov     rcx, [rbp+3Fh+FileHandle]; FileHandle
0x14000b66e  test    rcx, rcx
0x14000b671  jz      short loc_14000B67F
0x14000b673  call    cs:__imp_FltClose
0x14000b67a  nop     dword ptr [rax+rax+00h]
0x14000b67f  test    rdi, rdi
0x14000b682  jz      short loc_14000B698
0x14000b684  mov     edx, 574D6365h; Tag
0x14000b689  mov     rcx, rdi; P
0x14000b68c  call    cs:__imp_ExFreePoolWithTag
0x14000b693  nop     dword ptr [rax+rax+00h]
0x14000b698  mov     eax, ebx
0x14000b69a  add     rsp, 0F8h
0x14000b6a1  pop     r13
0x14000b6a3  pop     r12
0x14000b6a5  pop     rdi
0x14000b6a6  pop     rsi
0x14000b6a7  pop     rbx
0x14000b6a8  pop     rbp
0x14000b6a9  retn
```
