# INTERNAL_ERROR_ACTION(long)

- ea: `0x180016d88`
- end: `0x180016d98`
- name: `?INTERNAL_ERROR_ACTION@@YAXJ@Z`
- size: `16`
- prototype: `void __fastcall __noreturn()`
- caller_count: `4`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800165c8`
- `0x1800166bc`
- `0x180016e28`
- `0x180017028`

## import_xrefs

- `ntdll!RtlRaiseStatus` at `0x180016d91`
- `ntdll!RtlRaiseStatus` at `0x180016d91`

## pseudocode

```c
void __fastcall __noreturn INTERNAL_ERROR_ACTION()
{
  RtlRaiseStatus(-1073741595);
}

```

## disassembly

```asm
0x180016d88  sub     rsp, 28h
0x180016d8c  mov     ecx, 0C00000E5h; Status
0x180016d91  call    cs:__imp_RtlRaiseStatus
```
