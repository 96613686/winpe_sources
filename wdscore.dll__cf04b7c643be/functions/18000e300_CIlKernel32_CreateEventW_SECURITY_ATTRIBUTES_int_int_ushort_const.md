# CIlKernel32::CreateEventW(_SECURITY_ATTRIBUTES *,int,int,ushort const *)

- ea: `0x18000e300`
- end: `0x18000e31b`
- name: `?CreateEventW@CIlKernel32@@UEAAPEAXPEAU_SECURITY_ATTRIBUTES@@HHPEBG@Z`
- size: `27`
- prototype: `void *__fastcall(CIlKernel32 *__hidden this, struct _SECURITY_ATTRIBUTES *, int, int, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000e314`

## pseudocode

```c
HANDLE __fastcall CIlKernel32::CreateEventW(
        CIlKernel32 *this,
        struct _SECURITY_ATTRIBUTES *a2,
        BOOL a3,
        BOOL a4,
        const unsigned __int16 *a5)
{
  return CreateEventW(a2, a3, a4, a5);
}

```

## disassembly

```asm
0x18000e300  mov     eax, r9d
0x18000e303  mov     r10d, r8d
0x18000e306  mov     r9, [rsp+arg_20]
0x18000e30b  mov     rcx, rdx
0x18000e30e  mov     r8d, eax
0x18000e311  mov     edx, r10d
0x18000e314  jmp     cs:__imp_CreateEventW
```
