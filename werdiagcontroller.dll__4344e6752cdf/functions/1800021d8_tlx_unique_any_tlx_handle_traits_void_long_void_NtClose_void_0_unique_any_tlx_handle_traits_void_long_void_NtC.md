# tlx::unique_any<tlx::handle_traits<void *,long (*)(void *),&NtClose(void *),0>>::~unique_any<tlx::handle_traits<void *,long (*)(void *),&NtClose(void *),0>>(void)

- ea: `0x1800021d8`
- end: `0x1800021ef`
- name: `??1?$unique_any@U?$handle_traits@PEAXP6AJPEAX@Z$1?NtClose@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ`
- size: `23`
- prototype: `NTSTATUS __fastcall(void **)`
- caller_count: `6`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000653a`
- `0x18000655e`
- `0x180006570`
- `0x180006582`
- `0x1800065a6`
- `0x1800065b8`

## callees

- `0x1800021d8`

## import_xrefs

- `ntdll!NtClose` at `0x1800021e4`
- `ntdll!NtClose` at `0x1800021e4`

## pseudocode

```c
NTSTATUS __fastcall tlx::unique_any<tlx::handle_traits<void *,long (*)(void *),&long NtClose(void *),0>>::~unique_any<tlx::handle_traits<void *,long (*)(void *),&long NtClose(void *),0>>(
        void **a1)
{
  void *v1; // rcx
  NTSTATUS result; // eax

  v1 = *a1;
  if ( v1 )
    return NtClose(v1);
  return result;
}

```

## disassembly

```asm
0x1800021d8  sub     rsp, 28h
0x1800021dc  mov     rcx, [rcx]; Handle
0x1800021df  test    rcx, rcx
0x1800021e2  jz      short loc_1800021EA
0x1800021e4  call    cs:__imp_NtClose
0x1800021ea  add     rsp, 28h
0x1800021ee  retn
```
