# PriStubCreateChild

- ea: `0x14000b418`
- end: `0x14000b60b`
- name: `PriStubCreateChild`
- size: `499`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14000b070`

## callees

- `0x14000adb4`
- `0x14000ae40`
- `0x14000b418`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14000b5be`
- `ntoskrnl!ZwClose` at `0x14000b5be`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b5ec`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b5ec`
- `ntoskrnl!ZwDuplicateObject` at `0x14000b574`
- `ntoskrnl!ZwDuplicateObject` at `0x14000b574`
- `FLTMGR!FltObjectDereference` at `0x14000b593`
- `FLTMGR!FltObjectDereference` at `0x14000b5aa`
- `FLTMGR!FltObjectDereference` at `0x14000b593`
- `FLTMGR!FltObjectDereference` at `0x14000b5aa`
- `FLTMGR!FltClose` at `0x14000b5d3`
- `FLTMGR!FltClose` at `0x14000b5d3`
- `FLTMGR!FltCreateFile` at `0x14000b53b`
- `FLTMGR!FltCreateFile` at `0x14000b53b`

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
  PFLT_FILTER Filter; // [rsp+70h] [rbp-71h] BYREF
  PFLT_INSTANCE Instance; // [rsp+78h] [rbp-69h] BYREF
  void *v17; // [rsp+80h] [rbp-61h] BYREF
  void *FileHandle; // [rsp+88h] [rbp-59h] BYREF
  HANDLE Handle; // [rsp+90h] [rbp-51h] BYREF
  __int128 v20; // [rsp+98h] [rbp-49h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A8h] [rbp-39h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+D8h] [rbp-9h] BYREF

  Filter = 0;
  Instance = 0;
  Handle = 0;
  FileHandle = 0;
  v9 = 0;
  v17 = 0;
  v20 = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  ObjectsFromUserHandle = PriGetObjectsFromUserHandle(a1, 0x100131u, &Filter, &Instance, 0, &Handle, 0);
  v11 = Handle;
  v12 = ObjectsFromUserHandle;
  if ( ObjectsFromUserHandle >= 0 )
  {
    v12 = PriDuplicateBufferFromUser(&v17, *((_QWORD *)a6 + 1), *((unsigned __int16 *)a6 + 1));
    if ( v12 < 0 )
    {
      v9 = v17;
    }
    else
    {
      v13 = *a6;
      v9 = v17;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)&v20;
      *(_QWORD *)&v20 = v13;
      *((_QWORD *)&v20 + 1) = v17;
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = v11;
      ObjectAttributes.Attributes = 512;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v12 = FltCreateFile(
              Filter,
              Instance,
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
  if ( Filter )
    FltObjectDereference(Filter);
  if ( Instance )
    FltObjectDereference(Instance);
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
0x14000b418  mov     [rsp-8+DesiredAccess], edx
0x14000b41c  push    rbp
0x14000b41d  push    rbx
0x14000b41e  push    rsi
0x14000b41f  push    rdi
0x14000b420  push    r12
0x14000b422  push    r13
0x14000b424  lea     rbp, [rsp-17h]
0x14000b429  sub     rsp, 0F8h
0x14000b430  xor     edx, edx
0x14000b432  xorps   xmm0, xmm0
0x14000b435  mov     [rsp+120h+AllocationSize], rdx; __int64
0x14000b43a  xor     eax, eax
0x14000b43c  lea     rax, [rbp+3Fh+Handle]
0x14000b440  mov     [rbp+3Fh+Filter], rdx
0x14000b444  mov     [rsp+120h+IoStatusBlock], rax; __int64
0x14000b449  mov     r12d, r9d
0x14000b44c  mov     [rsp+120h+ObjectAttributes], rdx; __int64
0x14000b451  lea     r9, [rbp+3Fh+Instance]
0x14000b455  mov     r13d, r8d
0x14000b458  mov     [rbp+3Fh+Instance], rdx
0x14000b45c  mov     [rbp+3Fh+Handle], rdx
0x14000b460  lea     r8, [rbp+3Fh+Filter]
0x14000b464  mov     [rbp+3Fh+FileHandle], rdx
0x14000b468  mov     edi, edx
0x14000b46a  mov     [rbp+3Fh+var_A0], rdx
0x14000b46e  mov     edx, 100131h; DesiredAccess
0x14000b473  movups  xmmword ptr [rbp+3Fh+var_78.ObjectName], xmm0
0x14000b477  movups  [rbp+3Fh+var_88], xmm0
0x14000b47b  movups  xmmword ptr [rbp+3Fh+var_78.Length], xmm0
0x14000b47f  movups  xmmword ptr [rbp+3Fh+var_78+1Ch], xmm0
0x14000b483  movups  xmmword ptr [rbp+3Fh+var_48], xmm0
0x14000b487  call    PriGetObjectsFromUserHandle
0x14000b48c  mov     rsi, [rbp+3Fh+Handle]
0x14000b490  mov     ebx, eax
0x14000b492  test    eax, eax
0x14000b494  js      loc_14000B588
0x14000b49a  mov     rdi, [rbp+3Fh+arg_28]
0x14000b49e  lea     rcx, [rbp+3Fh+var_A0]
0x14000b4a2  movzx   r8d, word ptr [rdi+2]
0x14000b4a7  mov     rdx, [rdi+8]
0x14000b4ab  call    PriDuplicateBufferFromUser
0x14000b4b0  xor     ecx, ecx
0x14000b4b2  mov     ebx, eax
0x14000b4b4  test    eax, eax
0x14000b4b6  js      loc_14000B584
0x14000b4bc  movups  xmm0, xmmword ptr [rdi]
0x14000b4bf  mov     rdi, [rbp+3Fh+var_A0]
0x14000b4c3  lea     rax, [rbp+3Fh+var_88]
0x14000b4c7  mov     r9d, [rbp+3Fh+DesiredAccess]; DesiredAccess
0x14000b4cb  lea     r8, [rbp+3Fh+FileHandle]; FileHandle
0x14000b4cf  mov     rdx, [rbp+3Fh+Instance]; Instance
0x14000b4d3  mov     [rsp+120h+Flags], ecx; Flags
0x14000b4d7  mov     [rsp+120h+EaLength], ecx; EaLength
0x14000b4db  mov     [rsp+120h+EaBuffer], rcx; EaBuffer
0x14000b4e0  mov     [rsp+120h+CreateOptions], r12d; CreateOptions
0x14000b4e5  mov     [rsp+120h+CreateDisposition], r13d; CreateDisposition
0x14000b4ea  mov     [rbp+3Fh+var_78.ObjectName], rax
0x14000b4ee  mov     eax, [rbp+3Fh+arg_20]
0x14000b4f1  mov     [rsp+120h+ShareAccess], 7; ShareAccess
0x14000b4f9  mov     [rsp+120h+FileAttributes], eax; FileAttributes
0x14000b4fd  lea     rax, [rbp+3Fh+var_48]
0x14000b501  mov     [rsp+120h+AllocationSize], rcx; AllocationSize
0x14000b506  mov     rcx, [rbp+3Fh+Filter]; Filter
0x14000b50a  mov     [rsp+120h+IoStatusBlock], rax; IoStatusBlock
0x14000b50f  lea     rax, [rbp+3Fh+var_78]
0x14000b513  movdqu  [rbp+3Fh+var_88], xmm0
0x14000b518  mov     [rsp+120h+ObjectAttributes], rax; ObjectAttributes
0x14000b51d  xorps   xmm0, xmm0
0x14000b520  mov     qword ptr [rbp+3Fh+var_88+8], rdi
0x14000b524  mov     [rbp+3Fh+var_78.Length], 30h ; '0'
0x14000b52b  mov     [rbp+3Fh+var_78.RootDirectory], rsi
0x14000b52f  mov     [rbp+3Fh+var_78.Attributes], 200h
0x14000b536  movdqu  xmmword ptr [rbp+3Fh+var_78.SecurityDescriptor], xmm0
0x14000b53b  call    cs:__imp_FltCreateFile
0x14000b542  nop     dword ptr [rax+rax+00h]
0x14000b547  mov     ebx, eax
0x14000b549  test    eax, eax
0x14000b54b  js      short loc_14000B588
0x14000b54d  mov     r9, [rbp+3Fh+TargetHandle]; TargetHandle
0x14000b551  or      rcx, 0FFFFFFFFFFFFFFFFh; SourceProcessHandle
0x14000b555  mov     rdx, [rbp+3Fh+FileHandle]; SourceHandle
0x14000b559  mov     r8, rcx; TargetProcessHandle
0x14000b55c  mov     dword ptr [rsp+120h+AllocationSize], 6; Options
0x14000b564  mov     dword ptr [rsp+120h+IoStatusBlock], 0; HandleAttributes
0x14000b56c  mov     dword ptr [rsp+120h+ObjectAttributes], 0; DesiredAccess
0x14000b574  call    cs:__imp_ZwDuplicateObject
0x14000b57b  nop     dword ptr [rax+rax+00h]
0x14000b580  mov     ebx, eax
0x14000b582  jmp     short loc_14000B588
0x14000b584  mov     rdi, [rbp+3Fh+var_A0]
0x14000b588  cmp     [rbp+3Fh+Filter], 0
0x14000b58d  jz      short loc_14000B59F
0x14000b58f  mov     rcx, [rbp+3Fh+Filter]; FltObject
0x14000b593  call    cs:__imp_FltObjectDereference
0x14000b59a  nop     dword ptr [rax+rax+00h]
0x14000b59f  cmp     [rbp+3Fh+Instance], 0
0x14000b5a4  jz      short loc_14000B5B6
0x14000b5a6  mov     rcx, [rbp+3Fh+Instance]; FltObject
0x14000b5aa  call    cs:__imp_FltObjectDereference
0x14000b5b1  nop     dword ptr [rax+rax+00h]
0x14000b5b6  test    rsi, rsi
0x14000b5b9  jz      short loc_14000B5CA
0x14000b5bb  mov     rcx, rsi; Handle
0x14000b5be  call    cs:__imp_ZwClose
0x14000b5c5  nop     dword ptr [rax+rax+00h]
0x14000b5ca  mov     rcx, [rbp+3Fh+FileHandle]; FileHandle
0x14000b5ce  test    rcx, rcx
0x14000b5d1  jz      short loc_14000B5DF
0x14000b5d3  call    cs:__imp_FltClose
0x14000b5da  nop     dword ptr [rax+rax+00h]
0x14000b5df  test    rdi, rdi
0x14000b5e2  jz      short loc_14000B5F8
0x14000b5e4  mov     edx, 574D6365h; Tag
0x14000b5e9  mov     rcx, rdi; P
0x14000b5ec  call    cs:__imp_ExFreePoolWithTag
0x14000b5f3  nop     dword ptr [rax+rax+00h]
0x14000b5f8  mov     eax, ebx
0x14000b5fa  add     rsp, 0F8h
0x14000b601  pop     r13
0x14000b603  pop     r12
0x14000b605  pop     rdi
0x14000b606  pop     rsi
0x14000b607  pop     rbx
0x14000b608  pop     rbp
0x14000b609  retn
```
