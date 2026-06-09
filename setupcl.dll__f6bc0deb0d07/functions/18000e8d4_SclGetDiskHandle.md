# SclGetDiskHandle

- ea: `0x18000e8d4`
- end: `0x18000ea21`
- name: `SclGetDiskHandle`
- size: `333`
- prototype: `__int64 __fastcall(__int64, unsigned int, void **)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x18000f22c`
- `0x180010170`

## callees

- `0x180001c74`
- `0x180001d48`
- `0x18000a524`
- `0x18000e8d4`
- `0x1800179e0`

## import_xrefs

- `ntdll!NtCreateFile` at `0x18000e9a5`
- `ntdll!NtCreateFile` at `0x18000e9a5`

## string_xrefs

- `0x18000e9dc`: `(%lx): Unable to open handle to [%ws].`

## pseudocode

```c
__int64 __fastcall SclGetDiskHandle(__int64 a1, unsigned int a2, void **a3)
{
  int v5; // ebx
  int v6; // ecx
  struct _UNICODE_STRING v8; // [rsp+60h] [rbp-A0h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-90h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-80h] BYREF
  wchar_t v11[264]; // [rsp+B0h] [rbp-50h] BYREF

  v5 = RtlStringCchPrintfW(v11, 0x104u, L"\\Device\\Harddisk%u\\Partition0", a2);
  if ( v5 >= 0 )
  {
    v8 = 0;
    memset(&ObjectAttributes, 0, 44);
    IoStatusBlock = 0;
    INIT_OBJA_EX((__int64)&ObjectAttributes, &v8, v11, 64, 0);
    v5 = NtCreateFile(a3, 0x12019Fu, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 3u, 1u, 0, 0, 0);
    if ( v5 < 0 )
    {
      v6 = a1 + 1152;
      if ( !a1 )
        v6 = 0;
      SclLogGenericMessage(v6, 3, (unsigned int)SclEvent_Generic_Error, 340, (__int64)"SclGetDiskHandle");
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000e8d4  mov     [rsp-8+arg_18], rbx
0x18000e8d9  push    rbp
0x18000e8da  push    rsi
0x18000e8db  push    rdi
0x18000e8dc  lea     rbp, [rsp-1D0h]
0x18000e8e4  sub     rsp, 2D0h
0x18000e8eb  mov     rax, cs:__security_cookie
0x18000e8f2  xor     rax, rsp
0x18000e8f5  mov     [rbp+1E0h+var_20], rax
0x18000e8fc  mov     rsi, r8
0x18000e8ff  mov     rdi, rcx
0x18000e902  mov     r9d, edx
0x18000e905  lea     r8, aDeviceHarddisk; "\\Device\\Harddisk%u\\Partition0"
0x18000e90c  mov     edx, 104h
0x18000e911  lea     rcx, [rbp+1E0h+var_230]
0x18000e915  call    RtlStringCchPrintfW
0x18000e91a  mov     ebx, eax
0x18000e91c  test    eax, eax
0x18000e91e  js      loc_18000E9FD
0x18000e924  xorps   xmm0, xmm0
0x18000e927  lea     r8, [rbp+1E0h+var_230]
0x18000e92b  xor     eax, eax
0x18000e92d  lea     rdx, [rsp+2E0h+var_280]
0x18000e932  movups  xmmword ptr [rbp+1E0h+ObjectAttributes.ObjectName], xmm0
0x18000e936  lea     rcx, [rbp+1E0h+ObjectAttributes]
0x18000e93a  mov     [rsp+2E0h+AllocationSize], rax
0x18000e93f  movups  [rsp+2E0h+var_280], xmm0
0x18000e944  lea     r9d, [rax+40h]
0x18000e948  movups  xmmword ptr [rbp+1E0h+ObjectAttributes.Length], xmm0
0x18000e94c  movups  xmmword ptr [rbp+1E0h+ObjectAttributes+1Ch], xmm0
0x18000e950  movups  xmmword ptr [rsp+2E0h+IoStatusBlock], xmm0
0x18000e955  call    INIT_OBJA_EX
0x18000e95a  mov     [rsp+2E0h+EaLength], 0; EaLength
0x18000e962  lea     r9, [rsp+2E0h+IoStatusBlock]; IoStatusBlock
0x18000e967  mov     [rsp+2E0h+EaBuffer], 0; EaBuffer
0x18000e970  lea     r8, [rbp+1E0h+ObjectAttributes]; ObjectAttributes
0x18000e974  mov     [rsp+2E0h+CreateOptions], 0; CreateOptions
0x18000e97c  mov     edx, 12019Fh; DesiredAccess
0x18000e981  mov     [rsp+2E0h+CreateDisposition], 1; CreateDisposition
0x18000e989  mov     rcx, rsi; FileHandle
0x18000e98c  mov     [rsp+2E0h+ShareAccess], 3; ShareAccess
0x18000e994  mov     [rsp+2E0h+FileAttributes], 80h; FileAttributes
0x18000e99c  mov     [rsp+2E0h+AllocationSize], 0; AllocationSize
0x18000e9a5  call    cs:__imp_NtCreateFile
0x18000e9ab  mov     ebx, eax
0x18000e9ad  test    eax, eax
0x18000e9af  jns     short loc_18000E9FD
0x18000e9b1  xor     eax, eax
0x18000e9b3  lea     rcx, [rdi+480h]
0x18000e9ba  test    rdi, rdi
0x18000e9bd  lea     r8, SclEvent_Generic_Error
0x18000e9c4  mov     r9d, 154h
0x18000e9ca  mov     edx, 3
0x18000e9cf  cmovz   rcx, rax
0x18000e9d3  lea     rax, [rbp+1E0h+var_230]
0x18000e9d7  mov     qword ptr [rsp+2E0h+CreateDisposition], rax
0x18000e9dc  lea     rax, aLxUnableToOpen; "(%lx): Unable to open handle to [%ws]."
0x18000e9e3  mov     [rsp+2E0h+ShareAccess], ebx
0x18000e9e7  mov     qword ptr [rsp+2E0h+FileAttributes], rax
0x18000e9ec  lea     rax, aSclgetdiskhand; "SclGetDiskHandle"
0x18000e9f3  mov     [rsp+2E0h+AllocationSize], rax
0x18000e9f8  call    SclLogGenericMessage
0x18000e9fd  mov     eax, ebx
0x18000e9ff  mov     rcx, [rbp+1E0h+var_20]
0x18000ea06  xor     rcx, rsp; StackCookie
0x18000ea09  call    __security_check_cookie
0x18000ea0e  mov     rbx, [rsp+2E0h+arg_18]
0x18000ea16  add     rsp, 2D0h
0x18000ea1d  pop     rdi
0x18000ea1e  pop     rsi
0x18000ea1f  pop     rbp
0x18000ea20  retn
```
