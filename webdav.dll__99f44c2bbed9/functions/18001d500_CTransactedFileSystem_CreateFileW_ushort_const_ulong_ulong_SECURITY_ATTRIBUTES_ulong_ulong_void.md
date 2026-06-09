# CTransactedFileSystem::CreateFileW(ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *)

- ea: `0x18001d500`
- end: `0x18001d56a`
- name: `?CreateFileW@CTransactedFileSystem@@UEAAPEAXPEBGKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z`
- size: `106`
- prototype: `void *(CTransactedFileSystem *__hidden this, const unsigned __int16 *, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *, unsigned int, unsigned int, void *)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, broker_com_uri`

## import_xrefs

- `KERNEL32!CreateFileTransactedW` at `0x18001d55e`
- `KERNEL32!CreateFileTransactedW` at `0x18001d55e`

## pseudocode

```c
HANDLE __fastcall CTransactedFileSystem::CreateFileW(
        HANDLE *this,
        const unsigned __int16 *a2,
        DWORD a3,
        DWORD a4,
        struct _SECURITY_ATTRIBUTES *lpSecurityAttributes,
        DWORD dwCreationDisposition,
        DWORD dwFlagsAndAttributes,
        HANDLE hTemplateFile)
{
  return CreateFileTransactedW(
           a2,
           a3,
           a4,
           lpSecurityAttributes,
           dwCreationDisposition,
           dwFlagsAndAttributes,
           hTemplateFile,
           this[1],
           0,
           0);
}

```

## disassembly

```asm
0x18001d500  push    rbx
0x18001d502  sub     rsp, 50h
0x18001d506  mov     rax, [rcx+8]
0x18001d50a  mov     r10d, r9d
0x18001d50d  mov     r9, [rsp+58h+lpSecurityAttributes]; lpSecurityAttributes
0x18001d515  mov     r11d, r8d
0x18001d518  mov     [rsp+58h+lpExtendedParameter], 0; lpExtendedParameter
0x18001d521  mov     rbx, rdx
0x18001d524  mov     [rsp+58h+pusMiniVersion], 0; pusMiniVersion
0x18001d52d  mov     r8d, r10d; dwShareMode
0x18001d530  mov     [rsp+58h+hTransaction], rax; hTransaction
0x18001d535  mov     edx, r11d; dwDesiredAccess
0x18001d538  mov     rax, [rsp+58h+arg_38]
0x18001d540  mov     rcx, rbx; lpFileName
0x18001d543  mov     [rsp+58h+hTemplateFile], rax; hTemplateFile
0x18001d548  mov     eax, [rsp+58h+arg_30]
0x18001d54f  mov     [rsp+58h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x18001d553  mov     eax, [rsp+58h+arg_28]
0x18001d55a  mov     [rsp+58h+dwCreationDisposition], eax; dwCreationDisposition
0x18001d55e  call    cs:__imp_CreateFileTransactedW
0x18001d564  add     rsp, 50h
0x18001d568  pop     rbx
0x18001d569  retn
```
