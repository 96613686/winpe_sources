# PriCreateTransactional

- ea: `0x140002164`
- end: `0x140002234`
- name: `PriCreateTransactional`
- size: `208`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, int, PHANDLE FileHandle, PFILE_OBJECT *FileObject)`
- caller_count: `1`
- callee_count: `0`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14000223c`

## import_xrefs

- `FLTMGR!FltCreateFileEx2` at `0x14000221e`
- `FLTMGR!FltCreateFileEx2` at `0x14000221e`

## pseudocode

```c
NTSTATUS __fastcall PriCreateTransactional(
        struct _FLT_FILTER *a1,
        struct _FLT_INSTANCE *a2,
        struct _TXN_PARAMETER_BLOCK *a3,
        __int64 a4,
        struct _UNICODE_STRING *a5,
        int a6,
        PHANDLE FileHandle,
        PFILE_OBJECT *FileObject)
{
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp-39h] BYREF
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+90h] [rbp-29h] BYREF
  __int64 v11; // [rsp+B0h] [rbp-9h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B8h] [rbp-1h] BYREF

  ObjectAttributes.ObjectName = a5;
  DriverContext.TxnParameters = a3;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  v11 = 1;
  DriverContext.Size = 40;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  IoStatusBlock = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  memset(&DriverContext.Size + 1, 0, 22);
  return FltCreateFileEx2(
           a1,
           a2,
           FileHandle,
           FileObject,
           0x10000u,
           &ObjectAttributes,
           &IoStatusBlock,
           0,
           0x80u,
           7u,
           1u,
           0x204001u,
           0,
           0,
           0,
           &DriverContext);
}

```

## disassembly

```asm
0x140002164  push    rbp
0x140002166  lea     rbp, [rsp-37h]
0x14000216b  sub     rsp, 0F0h
0x140002172  mov     rax, [rbp+37h+arg_20]
0x140002176  xor     r10d, r10d
0x140002179  mov     [rbp+37h+var_38.ObjectName], rax
0x14000217d  xorps   xmm0, xmm0
0x140002180  xorps   xmm1, xmm1
0x140002183  mov     [rbp+37h+var_60.TxnParameters], r8
0x140002187  mov     r8, [rbp+37h+FileHandle]; FileHandle
0x14000218b  lea     r9d, [r10+1]
0x14000218f  mov     qword ptr [rbp+37h+var_38.Length], 30h ; '0'
0x140002197  lea     eax, [r10+28h]
0x14000219b  mov     [rbp+37h+var_40], r9
0x14000219f  mov     [rbp+37h+var_60.Size], ax
0x1400021a3  lea     rax, [rbp+37h+var_60]
0x1400021a7  mov     [rsp+0F0h+DriverContext], rax; DriverContext
0x1400021ac  lea     rax, [rbp+37h+var_70]
0x1400021b0  mov     [rsp+0F0h+Flags], r10d; Flags
0x1400021b5  mov     [rsp+0F0h+EaLength], r10d; EaLength
0x1400021ba  mov     [rsp+0F0h+EaBuffer], r10; EaBuffer
0x1400021bf  mov     [rsp+0F0h+CreateOptions], 204001h; CreateOptions
0x1400021c7  mov     [rsp+0F0h+CreateDisposition], r9d; CreateDisposition
0x1400021cc  mov     r9, [rbp+37h+FileObject]; FileObject
0x1400021d0  mov     [rsp+0F0h+ShareAccess], 7; ShareAccess
0x1400021d8  mov     [rsp+0F0h+FileAttributes], 80h; FileAttributes
0x1400021e0  mov     [rsp+0F0h+AllocationSize], r10; AllocationSize
0x1400021e5  mov     [rsp+0F0h+IoStatusBlock], rax; IoStatusBlock
0x1400021ea  lea     rax, [rbp+37h+var_38]
0x1400021ee  mov     [rsp+0F0h+ObjectAttributes], rax; ObjectAttributes
0x1400021f3  mov     [rsp+0F0h+DesiredAccess], 10000h; DesiredAccess
0x1400021fb  mov     qword ptr [rbp+37h+var_38.Attributes], 240h
0x140002203  movups  xmmword ptr [rbp+37h+var_70], xmm0
0x140002207  mov     [rbp+37h+var_38.RootDirectory], r10
0x14000220b  movdqu  xmmword ptr [rbp+37h+var_38.SecurityDescriptor], xmm0
0x140002210  mov     dword ptr [rbp+37h+var_60.DeviceObjectHint+2], r10d
0x140002214  movdqu  xmmword ptr [rbp+37h+var_60+2], xmm1
0x140002219  mov     word ptr [rbp+37h+var_60.DeviceObjectHint+6], r10w
0x14000221e  call    cs:__imp_FltCreateFileEx2
0x140002225  nop     dword ptr [rax+rax+00h]
0x14000222a  add     rsp, 0F0h
0x140002231  pop     rbp
0x140002232  retn
```
