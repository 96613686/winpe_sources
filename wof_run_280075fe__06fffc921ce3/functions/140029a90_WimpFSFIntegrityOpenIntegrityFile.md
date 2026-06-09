# WimpFSFIntegrityOpenIntegrityFile

- ea: `0x140029a90`
- end: `0x140029c48`
- name: `WimpFSFIntegrityOpenIntegrityFile`
- size: `440`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140028488`
- `0x1400288d4`

## callees

- `0x140029a90`

## import_xrefs

- `ntoskrnl!swprintf_s` at `0x140029b4e`
- `ntoskrnl!swprintf_s` at `0x140029b4e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029c25`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029c25`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140029af2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140029af2`
- `FLTMGR!FltCreateFileEx` at `0x140029be7`
- `FLTMGR!FltCreateFileEx` at `0x140029be7`

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
0x140029a90  push    rbp
0x140029a92  push    rbx
0x140029a93  push    rsi
0x140029a94  push    rdi
0x140029a95  push    r12
0x140029a97  push    r13
0x140029a99  push    r14
0x140029a9b  push    r15
0x140029a9d  lea     rbp, [rsp-1Fh]
0x140029aa2  sub     rsp, 0D8h
0x140029aa9  xorps   xmm0, xmm0
0x140029aac  mov     [rbp+57h+FileHandle], 0
0x140029ab4  xor     eax, eax
0x140029ab6  mov     [rbp+57h+FileObject], 0
0x140029abe  movzx   eax, word ptr [rcx+40h]
0x140029ac2  mov     r12, r8
0x140029ac5  add     ax, 72h ; 'r'
0x140029ac9  mov     rbx, rdx
0x140029acc  movzx   esi, ax
0x140029acf  mov     r14, rcx
0x140029ad2  movups  xmmword ptr [rbp+57h+var_78.ObjectName], xmm0
0x140029ad6  mov     edx, esi; NumberOfBytes
0x140029ad8  mov     ecx, 1; PoolType
0x140029add  mov     r8d, 69637077h; Tag
0x140029ae3  mov     r15, r9
0x140029ae6  movups  xmmword ptr [rbp+57h+var_88], xmm0
0x140029aea  movups  xmmword ptr [rbp+57h+var_78.Length], xmm0
0x140029aee  movups  xmmword ptr [rbp+57h+var_78+1Ch], xmm0
0x140029af2  call    cs:__imp_ExAllocatePoolWithTag
0x140029af9  nop     dword ptr [rax+rax+00h]
0x140029afe  mov     rdi, rax
0x140029b01  test    rax, rax
0x140029b04  jnz     short loc_140029B10
0x140029b06  mov     ebx, 0C0000017h
0x140029b0b  jmp     loc_140029C31
0x140029b10  lea     rcx, [rax+10h]; Dst
0x140029b14  mov     [rsp+110h+IoStatusBlock], rbx
0x140029b19  mov     [rax+8], rcx
0x140029b1d  lea     r9, [r14+40h]
0x140029b21  sub     si, 10h
0x140029b25  lea     r8, aWzSS016i64x; "%wZ%s\\%s%016I64X"
0x140029b2c  movzx   edx, si
0x140029b2f  mov     [rax+2], dx
0x140029b33  lea     rax, aWimh; "WIMH."
0x140029b3a  mov     [rsp+110h+ObjectAttributes], rax
0x140029b3f  lea     rax, aSystemVolumeIn_0; "\\System Volume Information"
0x140029b46  shr     rdx, 1; SizeInWords
0x140029b49  mov     qword ptr [rsp+110h+DesiredAccess], rax
0x140029b4e  call    cs:__imp_swprintf_s
0x140029b55  nop     dword ptr [rax+rax+00h]
0x140029b5a  cmp     eax, 1
0x140029b5d  jge     short loc_140029B69
0x140029b5f  mov     ebx, 0C0000095h
0x140029b64  jmp     loc_140029C1D
0x140029b69  xor     esi, esi
0x140029b6b  lea     r9, [rbp+57h+FileObject]; FileObject
0x140029b6f  mov     [rsp+110h+Flags], esi; Flags
0x140029b73  lea     r8, [rbp+57h+FileHandle]; FileHandle
0x140029b77  mov     [rsp+110h+EaLength], esi; EaLength
0x140029b7b  add     ax, ax
0x140029b7e  mov     [rdi], ax
0x140029b81  xorps   xmm0, xmm0
0x140029b84  mov     rdx, [r14+78h]; Instance
0x140029b88  lea     rax, [rbp+57h+var_88]
0x140029b8c  mov     rcx, [r14+68h]; Filter
0x140029b90  mov     [rsp+110h+EaBuffer], rsi; EaBuffer
0x140029b95  mov     [rsp+110h+CreateOptions], 840h; CreateOptions
0x140029b9d  mov     [rsp+110h+CreateDisposition], 1; CreateDisposition
0x140029ba5  mov     [rsp+110h+ShareAccess], 7; ShareAccess
0x140029bad  mov     [rsp+110h+FileAttributes], esi; FileAttributes
0x140029bb1  mov     [rsp+110h+AllocationSize], rsi; AllocationSize
0x140029bb6  mov     [rsp+110h+IoStatusBlock], rax; IoStatusBlock
0x140029bbb  lea     rax, [rbp+57h+var_78]
0x140029bbf  mov     [rsp+110h+ObjectAttributes], rax; ObjectAttributes
0x140029bc4  mov     [rsp+110h+DesiredAccess], 120089h; DesiredAccess
0x140029bcc  mov     [rbp+57h+var_78.Length], 30h ; '0'
0x140029bd3  mov     [rbp+57h+var_78.RootDirectory], rsi
0x140029bd7  mov     [rbp+57h+var_78.Attributes], 240h
0x140029bde  mov     [rbp+57h+var_78.ObjectName], rdi
0x140029be2  movdqu  xmmword ptr [rbp+57h+var_78.SecurityDescriptor], xmm0
0x140029be7  call    cs:__imp_FltCreateFileEx
0x140029bee  nop     dword ptr [rax+rax+00h]
0x140029bf3  mov     ebx, eax
0x140029bf5  test    eax, eax
0x140029bf7  jns     short loc_140029C0E
0x140029bf9  cmp     eax, 0C0000034h
0x140029bfe  jz      short loc_140029C07
0x140029c00  cmp     eax, 0C000003Ah
0x140029c05  jnz     short loc_140029C1D
0x140029c07  mov     ebx, 0C000000Fh
0x140029c0c  jmp     short loc_140029C1D
0x140029c0e  mov     rax, [rbp+57h+FileHandle]
0x140029c12  mov     [r12], rax
0x140029c16  mov     rax, [rbp+57h+FileObject]
0x140029c1a  mov     [r15], rax
0x140029c1d  mov     edx, 69637077h; Tag
0x140029c22  mov     rcx, rdi; P
0x140029c25  call    cs:__imp_ExFreePoolWithTag
0x140029c2c  nop     dword ptr [rax+rax+00h]
0x140029c31  mov     eax, ebx
0x140029c33  add     rsp, 0D8h
0x140029c3a  pop     r15
0x140029c3c  pop     r14
0x140029c3e  pop     r13
0x140029c40  pop     r12
0x140029c42  pop     rdi
0x140029c43  pop     rsi
0x140029c44  pop     rbx
0x140029c45  pop     rbp
0x140029c46  retn
```
