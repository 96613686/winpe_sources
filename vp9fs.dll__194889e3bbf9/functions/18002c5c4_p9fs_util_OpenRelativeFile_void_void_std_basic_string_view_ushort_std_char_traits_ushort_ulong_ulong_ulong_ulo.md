# p9fs::util::OpenRelativeFile(void * *,void *,std::basic_string_view<ushort,std::char_traits<ushort>>,ulong,ulong,ulong,ulong,gsl::span<gsl::byte,-1>,unsigned __int64 *)

- ea: `0x18002c5c4`
- end: `0x18002c6d8`
- name: `?OpenRelativeFile@util@p9fs@@YAJPEAPEAXPEAXV?$basic_string_view@GU?$char_traits@G@std@@@std@@KKKKV?$span@W4byte@gsl@@$0?0@gsl@@PEA_K@Z`
- size: `276`
- prototype: `__int64 __usercall@<rax>(PHANDLE FileHandle@<rcx>, ULONG, ULONG, ULONG, __int64, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x180024f90`
- `0x18002c4ec`

## callees

- `0x180004120`
- `0x180004c98`
- `0x18001d8b4`
- `0x18002c5c4`

## import_xrefs

- `ntdll!NtCreateFile` at `0x18002c685`
- `ntdll!NtCreateFile` at `0x18002c685`

## pseudocode

```c
NTSTATUS __fastcall p9fs::util::OpenRelativeFile(
        PHANDLE FileHandle,
        void *a2,
        __int64 *a3,
        ACCESS_MASK a4,
        ULONG CreateDisposition,
        ULONG FileAttributes,
        ULONG CreateOptions,
        __int64 a8,
        ULONG_PTR *a9)
{
  unsigned __int16 v10; // cx
  NTSTATUS result; // eax
  __int128 pExceptionObject; // [rsp+60h] [rbp-41h] BYREF
  __int64 v13; // [rsp+70h] [rbp-31h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-29h] BYREF
  _WORD v15[2]; // [rsp+A8h] [rbp+7h] BYREF
  int v16; // [rsp+ACh] [rbp+Bh]
  __int64 v17; // [rsp+B0h] [rbp+Fh]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B8h] [rbp+17h] BYREF

  v10 = 2 * *((_WORD *)a3 + 4);
  if ( v10 != 2 * a3[1] )
  {
    pExceptionObject = 0;
    v13 = 0;
    gsl::narrowing_error::narrowing_error((gsl::narrowing_error *)&pExceptionObject);
    throw (gsl::narrowing_error *)&pExceptionObject;
  }
  v15[0] = 2 * *((_WORD *)a3 + 4);
  v15[1] = v10;
  v16 = 0;
  v17 = *a3;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  memset(&ObjectAttributes.Attributes, 0, 24);
  ObjectAttributes.RootDirectory = a2;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v15;
  IoStatusBlock = 0;
  result = NtCreateFile(
             FileHandle,
             a4,
             &ObjectAttributes,
             &IoStatusBlock,
             0,
             FileAttributes,
             7u,
             CreateDisposition,
             CreateOptions,
             *(PVOID *)(a8 + 8),
             *(_DWORD *)a8);
  if ( a9 )
    *a9 = IoStatusBlock.Information;
  return result;
}

```

## disassembly

```asm
0x18002c5c4  mov     [rsp-8+arg_10], rbx
0x18002c5c9  push    rbp
0x18002c5ca  lea     rbp, [rsp-2Fh]
0x18002c5cf  sub     rsp, 0D0h
0x18002c5d6  mov     rax, cs:__security_cookie
0x18002c5dd  xor     rax, rsp
0x18002c5e0  mov     [rbp+2Fh+var_8], rax
0x18002c5e4  mov     r11d, r9d
0x18002c5e7  mov     r10, rcx
0x18002c5ea  mov     r9, [rbp+2Fh+arg_38]
0x18002c5ee  mov     rbx, [rbp+2Fh+arg_40]
0x18002c5f2  mov     rax, [r8+8]
0x18002c5f6  add     rax, rax
0x18002c5f9  movzx   ecx, ax
0x18002c5fc  xorps   xmm0, xmm0
0x18002c5ff  cmp     rcx, rax
0x18002c602  jnz     loc_18002C6B4
0x18002c608  xor     eax, eax
0x18002c60a  mov     [rbp+2Fh+var_28], cx
0x18002c60e  mov     [rbp+2Fh+var_26], cx
0x18002c612  mov     [rbp+2Fh+var_24], eax
0x18002c615  mov     rax, [r8]
0x18002c618  mov     [rbp+2Fh+var_20], rax
0x18002c61c  mov     qword ptr [rbp+2Fh+ObjectAttributes.Length], 30h ; '0'
0x18002c624  mov     qword ptr [rbp+2Fh+ObjectAttributes.Attributes], 0
0x18002c62c  mov     [rbp+2Fh+ObjectAttributes.RootDirectory], rdx
0x18002c630  lea     rax, [rbp+2Fh+var_28]
0x18002c634  mov     [rbp+2Fh+ObjectAttributes.ObjectName], rax
0x18002c638  movdqu  xmmword ptr [rbp+2Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x18002c63d  movups  xmmword ptr [rbp+2Fh+IoStatusBlock], xmm0
0x18002c641  mov     eax, [r9]
0x18002c644  mov     [rsp+0D0h+EaLength], eax; EaLength
0x18002c648  mov     rax, [r9+8]
0x18002c64c  mov     [rsp+0D0h+EaBuffer], rax; EaBuffer
0x18002c651  mov     eax, [rbp+2Fh+arg_30]
0x18002c654  mov     [rsp+0D0h+CreateOptions], eax; CreateOptions
0x18002c658  mov     eax, [rbp+2Fh+arg_20]
0x18002c65b  mov     [rsp+0D0h+CreateDisposition], eax; CreateDisposition
0x18002c65f  mov     [rsp+0D0h+ShareAccess], 7; ShareAccess
0x18002c667  mov     eax, [rbp+2Fh+arg_28]
0x18002c66a  mov     [rsp+0D0h+FileAttributes], eax; FileAttributes
0x18002c66e  mov     [rsp+0D0h+AllocationSize], 0; AllocationSize
0x18002c677  lea     r9, [rbp+2Fh+IoStatusBlock]; IoStatusBlock
0x18002c67b  lea     r8, [rbp+2Fh+ObjectAttributes]; ObjectAttributes
0x18002c67f  mov     edx, r11d; DesiredAccess
0x18002c682  mov     rcx, r10; FileHandle
0x18002c685  call    cs:__imp_NtCreateFile
0x18002c68b  test    rbx, rbx
0x18002c68e  jz      short loc_18002C697
0x18002c690  mov     rcx, [rbp+2Fh+IoStatusBlock.Information]
0x18002c694  mov     [rbx], rcx
0x18002c697  mov     rcx, [rbp+2Fh+var_8]
0x18002c69b  xor     rcx, rsp; StackCookie
0x18002c69e  call    __security_check_cookie
0x18002c6a3  mov     rbx, [rsp+0D0h+arg_10]
0x18002c6ab  add     rsp, 0D0h
0x18002c6b2  pop     rbp
0x18002c6b3  retn
0x18002c6b4  xor     eax, eax
0x18002c6b6  movups  [rbp+2Fh+pExceptionObject], xmm0
0x18002c6ba  mov     [rbp+2Fh+var_60], rax
0x18002c6be  lea     rcx, [rbp+2Fh+pExceptionObject]; this
0x18002c6c2  call    ??0narrowing_error@gsl@@QEAA@XZ; gsl::narrowing_error::narrowing_error(void)
0x18002c6c7  lea     rdx, _TI2?AUnarrowing_error@gsl@@; pThrowInfo
0x18002c6ce  lea     rcx, [rbp+2Fh+pExceptionObject]; pExceptionObject
0x18002c6d2  call    _CxxThrowException_0
```
