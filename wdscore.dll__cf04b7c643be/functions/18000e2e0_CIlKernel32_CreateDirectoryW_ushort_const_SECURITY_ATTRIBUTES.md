# CIlKernel32::CreateDirectoryW(ushort const *,_SECURITY_ATTRIBUTES *)

- ea: `0x18000e2e0`
- end: `0x18000e2ed`
- name: `?CreateDirectoryW@CIlKernel32@@UEAAHPEBGPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `13`
- prototype: `__int64 __fastcall(CIlKernel32 *__hidden this, const unsigned __int16 *, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000e2e6`

## pseudocode

```c
BOOL __fastcall CIlKernel32::CreateDirectoryW(
        CIlKernel32 *this,
        const unsigned __int16 *a2,
        struct _SECURITY_ATTRIBUTES *a3)
{
  return CreateDirectoryW(a2, a3);
}

```

## disassembly

```asm
0x18000e2e0  mov     rcx, rdx
0x18000e2e3  mov     rdx, r8
0x18000e2e6  jmp     cs:__imp_CreateDirectoryW
```
