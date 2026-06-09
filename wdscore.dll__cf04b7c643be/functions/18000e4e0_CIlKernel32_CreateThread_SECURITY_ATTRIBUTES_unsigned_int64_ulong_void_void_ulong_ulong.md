# CIlKernel32::CreateThread(_SECURITY_ATTRIBUTES *,unsigned __int64,ulong (*)(void *),void *,ulong,ulong *)

- ea: `0x18000e4e0`
- end: `0x18000e51f`
- name: `?CreateThread@CIlKernel32@@UEAAPEAXPEAU_SECURITY_ATTRIBUTES@@_KP6AKPEAX@Z2KPEAK@Z`
- size: `63`
- prototype: `void *(CIlKernel32 *__hidden this, struct _SECURITY_ATTRIBUTES *, unsigned __int64, unsigned int (*)(void *), void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000e50c`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000e50c`

## pseudocode

```c
HANDLE __fastcall CIlKernel32::CreateThread(
        CIlKernel32 *this,
        struct _SECURITY_ATTRIBUTES *a2,
        SIZE_T a3,
        unsigned int (*a4)(void *),
        void *lpParameter,
        DWORD dwCreationFlags,
        unsigned int *lpThreadId)
{
  return CreateThread(a2, a3, a4, lpParameter, dwCreationFlags, lpThreadId);
}

```

## disassembly

```asm
0x18000e4e0  push    rbx
0x18000e4e2  sub     rsp, 30h
0x18000e4e6  mov     rax, [rsp+38h+arg_30]
0x18000e4eb  mov     r10, r9
0x18000e4ee  mov     r9, [rsp+38h+lpParameter]; lpParameter
0x18000e4f3  mov     r11, r8
0x18000e4f6  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x18000e4fb  mov     rcx, rdx; lpThreadAttributes
0x18000e4fe  mov     eax, [rsp+38h+arg_28]
0x18000e502  mov     r8, r10; lpStartAddress
0x18000e505  mov     rdx, r11; dwStackSize
0x18000e508  mov     [rsp+38h+dwCreationFlags], eax; dwCreationFlags
0x18000e50c  call    cs:__imp_CreateThread
0x18000e513  nop     dword ptr [rax+rax+00h]
0x18000e518  add     rsp, 30h
0x18000e51c  pop     rbx
0x18000e51d  retn
```
