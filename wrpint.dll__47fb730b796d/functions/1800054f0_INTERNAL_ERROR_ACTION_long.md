# INTERNAL_ERROR_ACTION(long)

- ea: `0x1800054f0`
- end: `0x1800054fb`
- name: `?INTERNAL_ERROR_ACTION@@YAXJ@Z`
- size: `11`
- prototype: `void __fastcall __noreturn(NTSTATUS)`
- caller_count: `17`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001010`
- `0x180002500`
- `0x180005540`
- `0x1800075a0`
- `0x180007620`
- `0x180007f68`
- `0x180008248`
- `0x180008aac`
- `0x180008e30`
- `0x180009150`
- `0x180009a88`
- `0x180009be8`
- `0x180011e10`
- `0x180012e78`
- `0x18001a260`
- `0x18001ab5c`
- `0x18001b30c`

## import_xrefs

- `ntdll!RtlRaiseStatus` at `0x1800054f4`
- `ntdll!RtlRaiseStatus` at `0x1800054f4`

## pseudocode

```c
void __fastcall __noreturn INTERNAL_ERROR_ACTION(NTSTATUS a1)
{
  RtlRaiseStatus(a1);
}

```

## disassembly

```asm
0x1800054f0  sub     rsp, 28h
0x1800054f4  call    cs:__imp_RtlRaiseStatus
```
