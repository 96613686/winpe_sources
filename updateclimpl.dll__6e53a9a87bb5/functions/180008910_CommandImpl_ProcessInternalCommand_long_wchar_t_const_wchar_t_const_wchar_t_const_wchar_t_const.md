# CommandImpl::ProcessInternalCommand(long (*)(wchar_t const *,wchar_t const *),wchar_t const *,wchar_t const *)

- ea: `0x180008910`
- end: `0x180008924`
- name: `?ProcessInternalCommand@CommandImpl@@CAJP6AJPEB_W0@Z00@Z`
- size: `20`
- prototype: `__int64 __fastcall(__int64 (__fastcall *)(const wchar_t *, const wchar_t *), const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800084bc`

## callees

- `0x1800148e0`

## pseudocode

```c
__int64 __fastcall CommandImpl::ProcessInternalCommand(
        __int64 (__fastcall *a1)(const wchar_t *, const wchar_t *),
        const wchar_t *a2,
        const wchar_t *a3)
{
  return a1(a2, a3);
}

```

## disassembly

```asm
0x180008910  mov     rax, rdx
0x180008913  mov     r9, rcx
0x180008916  mov     rcx, rax
0x180008919  mov     rdx, r8
0x18000891c  mov     rax, r9
0x18000891f  jmp     _guard_dispatch_icall
```
