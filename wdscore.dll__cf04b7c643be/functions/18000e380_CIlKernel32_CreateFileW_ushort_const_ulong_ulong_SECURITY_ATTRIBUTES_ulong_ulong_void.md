# CIlKernel32::CreateFileW(ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *)

- ea: `0x18000e380`
- end: `0x18000e3cd`
- name: `?CreateFileW@CIlKernel32@@UEAAPEAXPEBGKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z`
- size: `77`
- prototype: `void *(CIlKernel32 *__hidden this, const unsigned __int16 *, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *, unsigned int, unsigned int, void *)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, broker_com_uri`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000e3ba`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000e3ba`

## pseudocode

```c
HANDLE __fastcall CIlKernel32::CreateFileW(
        CIlKernel32 *this,
        const unsigned __int16 *a2,
        DWORD a3,
        DWORD a4,
        struct _SECURITY_ATTRIBUTES *lpSecurityAttributes,
        DWORD dwCreationDisposition,
        DWORD dwFlagsAndAttributes,
        HANDLE hTemplateFile)
{
  return CreateFileW(a2, a3, a4, lpSecurityAttributes, dwCreationDisposition, dwFlagsAndAttributes, hTemplateFile);
}

```

## disassembly

```asm
0x18000e380  push    rbx
0x18000e382  sub     rsp, 40h
0x18000e386  mov     rax, [rsp+48h+arg_38]
0x18000e38e  mov     r10d, r9d
0x18000e391  mov     r9, [rsp+48h+lpSecurityAttributes]; lpSecurityAttributes
0x18000e396  mov     r11d, r8d
0x18000e399  mov     [rsp+48h+hTemplateFile], rax; hTemplateFile
0x18000e39e  mov     rcx, rdx; lpFileName
0x18000e3a1  mov     eax, [rsp+48h+arg_30]
0x18000e3a8  mov     r8d, r10d; dwShareMode
0x18000e3ab  mov     [rsp+48h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x18000e3af  mov     edx, r11d; dwDesiredAccess
0x18000e3b2  mov     eax, [rsp+48h+arg_28]
0x18000e3b6  mov     [rsp+48h+dwCreationDisposition], eax; dwCreationDisposition
0x18000e3ba  call    cs:__imp_CreateFileW
0x18000e3c1  nop     dword ptr [rax+rax+00h]
0x18000e3c6  add     rsp, 40h
0x18000e3ca  pop     rbx
0x18000e3cb  retn
```
