# CIlKernel32::CreateFileMappingW(void *,_SECURITY_ATTRIBUTES *,ulong,ulong,ulong,ushort const *)

- ea: `0x18000e330`
- end: `0x18000e36f`
- name: `?CreateFileMappingW@CIlKernel32@@UEAAPEAXPEAXPEAU_SECURITY_ATTRIBUTES@@KKKPEBG@Z`
- size: `63`
- prototype: `void *(CIlKernel32 *__hidden this, void *, struct _SECURITY_ATTRIBUTES *, unsigned int, unsigned int, unsigned int, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, installer_update, broker_com_uri`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18000e35c`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18000e35c`

## pseudocode

```c
HANDLE __fastcall CIlKernel32::CreateFileMappingW(
        CIlKernel32 *this,
        void *a2,
        struct _SECURITY_ATTRIBUTES *a3,
        DWORD a4,
        DWORD dwMaximumSizeHigh,
        DWORD dwMaximumSizeLow,
        const unsigned __int16 *lpName)
{
  return CreateFileMappingW(a2, a3, a4, dwMaximumSizeHigh, dwMaximumSizeLow, lpName);
}

```

## disassembly

```asm
0x18000e330  push    rbx
0x18000e332  sub     rsp, 30h
0x18000e336  mov     rax, [rsp+38h+arg_30]
0x18000e33b  mov     r10d, r9d
0x18000e33e  mov     r9d, [rsp+38h+dwMaximumSizeHigh]; dwMaximumSizeHigh
0x18000e343  mov     r11, r8
0x18000e346  mov     [rsp+38h+lpName], rax; lpName
0x18000e34b  mov     rcx, rdx; hFile
0x18000e34e  mov     eax, [rsp+38h+arg_28]
0x18000e352  mov     r8d, r10d; flProtect
0x18000e355  mov     rdx, r11; lpFileMappingAttributes
0x18000e358  mov     [rsp+38h+dwMaximumSizeLow], eax; dwMaximumSizeLow
0x18000e35c  call    cs:__imp_CreateFileMappingW
0x18000e363  nop     dword ptr [rax+rax+00h]
0x18000e368  add     rsp, 30h
0x18000e36c  pop     rbx
0x18000e36d  retn
```
