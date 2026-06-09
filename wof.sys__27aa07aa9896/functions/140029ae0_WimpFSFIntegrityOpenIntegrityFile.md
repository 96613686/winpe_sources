# WimpFSFIntegrityOpenIntegrityFile

- ea: `0x140029ae0`
- end: `0x140029c98`
- name: `WimpFSFIntegrityOpenIntegrityFile`
- size: `440`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400284d8`
- `0x140028924`

## callees

- `0x140029ae0`

## import_xrefs

- `ntoskrnl!swprintf_s` at `0x140029b9e`
- `ntoskrnl!swprintf_s` at `0x140029b9e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029c75`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029c75`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140029b42`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140029b42`
- `FLTMGR!FltCreateFileEx` at `0x140029c37`
- `FLTMGR!FltCreateFileEx` at `0x140029c37`

## pseudocode

```c
__int64 __fastcall WimpFSFIntegrityOpenIntegrityFile(__int64 a1, __int64 a2, void **a3, PFILE_OBJECT *a4)
{
  SIZE_T v6; // rsi
  struct _UNICODE_STRING *PoolWithTag; // rax
  struct _UNICODE_STRING *v10; // rdi
  unsigned int v11; // ebx
  USHORT v12; // si
  int v13; // eax
  struct _FLT_INSTANCE *v14; // rdx
  struct _FLT_FILTER *v15; // rcx
  NTSTATUS v16; // eax
  PFILE_OBJECT FileObject; // [rsp+80h] [rbp-39h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+88h] [rbp-31h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+98h] [rbp-21h] BYREF
  void *FileHandle; // [rsp+120h] [rbp+67h] BYREF

  FileHandle = 0;
  FileObject = 0;
  v6 = (unsigned __int16)(*(_WORD *)(a1 + 64) + 114);
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  PoolWithTag = (struct _UNICODE_STRING *)ExAllocatePoolWithTag(PagedPool, v6, 0x69637077u);
  v10 = PoolWithTag;
  if ( PoolWithTag )
  {
    PoolWithTag->Buffer = &PoolWithTag[1].Length;
    v12 = v6 - 16;
    PoolWithTag->MaximumLength = v12;
    v13 = swprintf_s(
            &PoolWithTag[1].Length,
            (unsigned __int64)v12 >> 1,
            L"%wZ%s\\%s%016I64X",
            a1 + 64,
            L"\\System Volume Information",
            L"WIMH.",
            a2);
    if ( v13 >= 1 )
    {
      v10->Length = 2 * v13;
      v14 = *(struct _FLT_INSTANCE **)(a1 + 120);
      v15 = *(struct _FLT_FILTER **)(a1 + 104);
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 576;
      ObjectAttributes.ObjectName = v10;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v16 = FltCreateFileEx(
              v15,
              v14,
              &FileHandle,
              &FileObject,
              0x120089u,
              &ObjectAttributes,
              &IoStatusBlock,
              0,
              0,
              7u,
              1u,
              0x840u,
              0,
              0,
              0);
      v11 = v16;
      if ( v16 >= 0 )
      {
        *a3 = FileHandle;
        *a4 = FileObject;
      }
      else if ( v16 == -1073741772 || v16 == -1073741766 )
      {
        v11 = -1073741809;
      }
    }
    else
    {
      v11 = -1073741675;
    }
    ExFreePoolWithTag(v10, 0x69637077u);
  }
  else
  {
    return (unsigned int)-1073741801;
  }
  return v11;
}

```

## disassembly

```asm
0x140029ae0  push    rbp
0x140029ae2  push    rbx
0x140029ae3  push    rsi
0x140029ae4  push    rdi
0x140029ae5  push    r12
0x140029ae7  push    r13
0x140029ae9  push    r14
0x140029aeb  push    r15
0x140029aed  lea     rbp, [rsp-1Fh]
0x140029af2  sub     rsp, 0D8h
0x140029af9  xorps   xmm0, xmm0
0x140029afc  mov     [rbp+57h+FileHandle], 0
0x140029b04  xor     eax, eax
0x140029b06  mov     [rbp+57h+FileObject], 0
0x140029b0e  movzx   eax, word ptr [rcx+40h]
0x140029b12  mov     r12, r8
0x140029b15  add     ax, 72h ; 'r'
0x140029b19  mov     rbx, rdx
0x140029b1c  movzx   esi, ax
0x140029b1f  mov     r14, rcx
0x140029b22  movups  xmmword ptr [rbp+57h+var_78.ObjectName], xmm0
0x140029b26  mov     edx, esi; NumberOfBytes
0x140029b28  mov     ecx, 1; PoolType
0x140029b2d  mov     r8d, 69637077h; Tag
0x140029b33  mov     r15, r9
0x140029b36  movups  xmmword ptr [rbp+57h+var_88], xmm0
0x140029b3a  movups  xmmword ptr [rbp+57h+var_78.Length], xmm0
0x140029b3e  movups  xmmword ptr [rbp+57h+var_78+1Ch], xmm0
0x140029b42  call    cs:__imp_ExAllocatePoolWithTag
0x140029b49  nop     dword ptr [rax+rax+00h]
0x140029b4e  mov     rdi, rax
0x140029b51  test    rax, rax
0x140029b54  jnz     short loc_140029B60
0x140029b56  mov     ebx, 0C0000017h
0x140029b5b  jmp     loc_140029C81
0x140029b60  lea     rcx, [rax+10h]; Dst
0x140029b64  mov     [rsp+110h+IoStatusBlock], rbx
0x140029b69  mov     [rax+8], rcx
0x140029b6d  lea     r9, [r14+40h]
0x140029b71  sub     si, 10h
0x140029b75  lea     r8, aWzSS016i64x; "%wZ%s\\%s%016I64X"
0x140029b7c  movzx   edx, si
0x140029b7f  mov     [rax+2], dx
0x140029b83  lea     rax, aWimh; "WIMH."
0x140029b8a  mov     [rsp+110h+ObjectAttributes], rax
0x140029b8f  lea     rax, aSystemVolumeIn_0; "\\System Volume Information"
0x140029b96  shr     rdx, 1; SizeInWords
0x140029b99  mov     qword ptr [rsp+110h+DesiredAccess], rax
0x140029b9e  call    cs:__imp_swprintf_s
0x140029ba5  nop     dword ptr [rax+rax+00h]
0x140029baa  cmp     eax, 1
0x140029bad  jge     short loc_140029BB9
0x140029baf  mov     ebx, 0C0000095h
0x140029bb4  jmp     loc_140029C6D
0x140029bb9  xor     esi, esi
0x140029bbb  lea     r9, [rbp+57h+FileObject]; FileObject
0x140029bbf  mov     [rsp+110h+Flags], esi; Flags
0x140029bc3  lea     r8, [rbp+57h+FileHandle]; FileHandle
0x140029bc7  mov     [rsp+110h+EaLength], esi; EaLength
0x140029bcb  add     ax, ax
0x140029bce  mov     [rdi], ax
0x140029bd1  xorps   xmm0, xmm0
0x140029bd4  mov     rdx, [r14+78h]; Instance
0x140029bd8  lea     rax, [rbp+57h+var_88]
0x140029bdc  mov     rcx, [r14+68h]; Filter
0x140029be0  mov     [rsp+110h+EaBuffer], rsi; EaBuffer
0x140029be5  mov     [rsp+110h+CreateOptions], 840h; CreateOptions
0x140029bed  mov     [rsp+110h+CreateDisposition], 1; CreateDisposition
0x140029bf5  mov     [rsp+110h+ShareAccess], 7; ShareAccess
0x140029bfd  mov     [rsp+110h+FileAttributes], esi; FileAttributes
0x140029c01  mov     [rsp+110h+AllocationSize], rsi; AllocationSize
0x140029c06  mov     [rsp+110h+IoStatusBlock], rax; IoStatusBlock
0x140029c0b  lea     rax, [rbp+57h+var_78]
0x140029c0f  mov     [rsp+110h+ObjectAttributes], rax; ObjectAttributes
0x140029c14  mov     [rsp+110h+DesiredAccess], 120089h; DesiredAccess
0x140029c1c  mov     [rbp+57h+var_78.Length], 30h ; '0'
0x140029c23  mov     [rbp+57h+var_78.RootDirectory], rsi
0x140029c27  mov     [rbp+57h+var_78.Attributes], 240h
0x140029c2e  mov     [rbp+57h+var_78.ObjectName], rdi
0x140029c32  movdqu  xmmword ptr [rbp+57h+var_78.SecurityDescriptor], xmm0
0x140029c37  call    cs:__imp_FltCreateFileEx
0x140029c3e  nop     dword ptr [rax+rax+00h]
0x140029c43  mov     ebx, eax
0x140029c45  test    eax, eax
0x140029c47  jns     short loc_140029C5E
0x140029c49  cmp     eax, 0C0000034h
0x140029c4e  jz      short loc_140029C57
0x140029c50  cmp     eax, 0C000003Ah
0x140029c55  jnz     short loc_140029C6D
0x140029c57  mov     ebx, 0C000000Fh
0x140029c5c  jmp     short loc_140029C6D
0x140029c5e  mov     rax, [rbp+57h+FileHandle]
0x140029c62  mov     [r12], rax
0x140029c66  mov     rax, [rbp+57h+FileObject]
0x140029c6a  mov     [r15], rax
0x140029c6d  mov     edx, 69637077h; Tag
0x140029c72  mov     rcx, rdi; P
0x140029c75  call    cs:__imp_ExFreePoolWithTag
0x140029c7c  nop     dword ptr [rax+rax+00h]
0x140029c81  mov     eax, ebx
0x140029c83  add     rsp, 0D8h
0x140029c8a  pop     r15
0x140029c8c  pop     r14
0x140029c8e  pop     r13
0x140029c90  pop     r12
0x140029c92  pop     rdi
0x140029c93  pop     rsi
0x140029c94  pop     rbx
0x140029c95  pop     rbp
0x140029c96  retn
```
