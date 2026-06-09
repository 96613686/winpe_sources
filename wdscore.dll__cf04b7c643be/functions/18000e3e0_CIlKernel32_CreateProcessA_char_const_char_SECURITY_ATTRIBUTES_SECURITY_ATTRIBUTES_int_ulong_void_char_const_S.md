# CIlKernel32::CreateProcessA(char const *,char *,_SECURITY_ATTRIBUTES *,_SECURITY_ATTRIBUTES *,int,ulong,void *,char const *,_STARTUPINFOA *,_PROCESS_INFORMATION *)

- ea: `0x18000e3e0`
- end: `0x18000e45a`
- name: `?CreateProcessA@CIlKernel32@@UEAAHPEBDPEADPEAU_SECURITY_ATTRIBUTES@@2HKPEAX0PEAU_STARTUPINFOA@@PEAU_PROCESS_INFORMATION@@@Z`
- size: `122`
- prototype: `int(CIlKernel32 *__hidden this, const char *, char *, struct _SECURITY_ATTRIBUTES *, struct _SECURITY_ATTRIBUTES *, int, unsigned int, void *, const char *, struct _STARTUPINFOA *, struct _PROCESS_INFORMATION *)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateProcessA` at `0x18000e447`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessA` at `0x18000e447`

## pseudocode

```c
BOOL __fastcall CIlKernel32::CreateProcessA(
        CIlKernel32 *this,
        const char *a2,
        char *a3,
        struct _SECURITY_ATTRIBUTES *a4,
        struct _SECURITY_ATTRIBUTES *lpThreadAttributes,
        BOOL bInheritHandles,
        DWORD dwCreationFlags,
        void *lpEnvironment,
        const char *lpCurrentDirectory,
        struct _STARTUPINFOA *lpStartupInfo,
        struct _PROCESS_INFORMATION *lpProcessInformation)
{
  return CreateProcessA(
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
0x18000e3e0  push    rbx
0x18000e3e2  sub     rsp, 50h
0x18000e3e6  mov     rax, [rsp+58h+arg_50]
0x18000e3ee  mov     r10, r9
0x18000e3f1  mov     r9, [rsp+58h+lpThreadAttributes]; lpThreadAttributes
0x18000e3f9  mov     r11, r8
0x18000e3fc  mov     [rsp+58h+lpProcessInformation], rax; lpProcessInformation
0x18000e401  mov     rcx, rdx; lpApplicationName
0x18000e404  mov     rax, [rsp+58h+arg_48]
0x18000e40c  mov     r8, r10; lpProcessAttributes
0x18000e40f  mov     [rsp+58h+lpStartupInfo], rax; lpStartupInfo
0x18000e414  mov     rdx, r11; lpCommandLine
0x18000e417  mov     rax, [rsp+58h+arg_40]
0x18000e41f  mov     [rsp+58h+lpCurrentDirectory], rax; lpCurrentDirectory
0x18000e424  mov     rax, [rsp+58h+arg_38]
0x18000e42c  mov     [rsp+58h+lpEnvironment], rax; lpEnvironment
0x18000e431  mov     eax, [rsp+58h+arg_30]
0x18000e438  mov     [rsp+58h+dwCreationFlags], eax; dwCreationFlags
0x18000e43c  mov     eax, [rsp+58h+arg_28]
0x18000e443  mov     [rsp+58h+bInheritHandles], eax; bInheritHandles
0x18000e447  call    cs:__imp_CreateProcessA
0x18000e44e  nop     dword ptr [rax+rax+00h]
0x18000e453  add     rsp, 50h
0x18000e457  pop     rbx
0x18000e458  retn
```
