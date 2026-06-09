# CIlKernel32::CreateProcessW(ushort const *,ushort *,_SECURITY_ATTRIBUTES *,_SECURITY_ATTRIBUTES *,int,ulong,void *,ushort const *,_STARTUPINFOW *,_PROCESS_INFORMATION *)

- ea: `0x18000e460`
- end: `0x18000e4da`
- name: `?CreateProcessW@CIlKernel32@@UEAAHPEBGPEAGPEAU_SECURITY_ATTRIBUTES@@2HKPEAX0PEAU_STARTUPINFOW@@PEAU_PROCESS_INFORMATION@@@Z`
- size: `122`
- prototype: `int(CIlKernel32 *__hidden this, const unsigned __int16 *, unsigned __int16 *, struct _SECURITY_ATTRIBUTES *, struct _SECURITY_ATTRIBUTES *, int, unsigned int, void *, const unsigned __int16 *, struct _STARTUPINFOW *, struct _PROCESS_INFORMATION *)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18000e4c7`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18000e4c7`

## pseudocode

```c
BOOL __fastcall CIlKernel32::CreateProcessW(
        CIlKernel32 *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        struct _SECURITY_ATTRIBUTES *a4,
        struct _SECURITY_ATTRIBUTES *lpThreadAttributes,
        BOOL bInheritHandles,
        DWORD dwCreationFlags,
        void *lpEnvironment,
        const unsigned __int16 *lpCurrentDirectory,
        struct _STARTUPINFOW *lpStartupInfo,
        struct _PROCESS_INFORMATION *lpProcessInformation)
{
  return CreateProcessW(
           a2,
           a3,
           a4,
           lpThreadAttributes,
           bInheritHandles,
           dwCreationFlags,
           lpEnvironment,
           lpCurrentDirectory,
           lpStartupInfo,
           lpProcessInformation);
}

```

## disassembly

```asm
0x18000e460  push    rbx
0x18000e462  sub     rsp, 50h
0x18000e466  mov     rax, [rsp+58h+arg_50]
0x18000e46e  mov     r10, r9
0x18000e471  mov     r9, [rsp+58h+lpThreadAttributes]; lpThreadAttributes
0x18000e479  mov     r11, r8
0x18000e47c  mov     [rsp+58h+lpProcessInformation], rax; lpProcessInformation
0x18000e481  mov     rcx, rdx; lpApplicationName
0x18000e484  mov     rax, [rsp+58h+arg_48]
0x18000e48c  mov     r8, r10; lpProcessAttributes
0x18000e48f  mov     [rsp+58h+lpStartupInfo], rax; lpStartupInfo
0x18000e494  mov     rdx, r11; lpCommandLine
0x18000e497  mov     rax, [rsp+58h+arg_40]
0x18000e49f  mov     [rsp+58h+lpCurrentDirectory], rax; lpCurrentDirectory
0x18000e4a4  mov     rax, [rsp+58h+arg_38]
0x18000e4ac  mov     [rsp+58h+lpEnvironment], rax; lpEnvironment
0x18000e4b1  mov     eax, [rsp+58h+arg_30]
0x18000e4b8  mov     [rsp+58h+dwCreationFlags], eax; dwCreationFlags
0x18000e4bc  mov     eax, [rsp+58h+arg_28]
0x18000e4c3  mov     [rsp+58h+bInheritHandles], eax; bInheritHandles
0x18000e4c7  call    cs:__imp_CreateProcessW
0x18000e4ce  nop     dword ptr [rax+rax+00h]
0x18000e4d3  add     rsp, 50h
0x18000e4d7  pop     rbx
0x18000e4d8  retn
```
