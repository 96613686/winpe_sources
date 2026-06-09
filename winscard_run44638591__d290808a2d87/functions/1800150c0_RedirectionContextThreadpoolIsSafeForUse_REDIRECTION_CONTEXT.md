# RedirectionContextThreadpoolIsSafeForUse(_REDIRECTION_CONTEXT *)

- ea: `0x1800150c0`
- end: `0x1800150df`
- name: `?RedirectionContextThreadpoolIsSafeForUse@@YA_NPEAU_REDIRECTION_CONTEXT@@@Z`
- size: `31`
- prototype: `bool __fastcall(struct _REDIRECTION_CONTEXT *)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180006400`
- `0x1800176a0`
- `0x180020d68`
- `0x180021150`

## callees

- `0x1800150c0`

## import_xrefs

- `ntdll!RtlDllShutdownInProgress` at `0x1800150ca`
- `ntdll!RtlDllShutdownInProgress` at `0x1800150ca`

## pseudocode

```c
bool __fastcall RedirectionContextThreadpoolIsSafeForUse(struct _REDIRECTION_CONTEXT *a1)
{
  return !*((_BYTE *)a1 + 40) && !RtlDllShutdownInProgress();
}

```

## disassembly

```asm
0x1800150c0  sub     rsp, 28h
0x1800150c4  cmp     byte ptr [rcx+28h], 0
0x1800150c8  jnz     short loc_1800150DB
0x1800150ca  call    cs:__imp_RtlDllShutdownInProgress
0x1800150d0  test    al, al
0x1800150d2  jnz     short loc_1800150DB
0x1800150d4  mov     al, 1
0x1800150d6  add     rsp, 28h
0x1800150da  retn
0x1800150db  xor     al, al
0x1800150dd  jmp     short loc_1800150D6
```
