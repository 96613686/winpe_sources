# winrt::com_ptr<winrt::impl::IErrorInfo>::unconditional_release_ref(void)

- ea: `0x18000abac`
- end: `0x18000abc5`
- name: `?unconditional_release_ref@?$com_ptr@UIErrorInfo@impl@winrt@@@winrt@@AEAAXXZ`
- size: `25`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000aa80`

## callees

- `0x18000d010`

## pseudocode

```c
__int64 __fastcall winrt::com_ptr<winrt::impl::IErrorInfo>::unconditional_release_ref(__int64 *a1)
{
  __int64 v1; // rdx

  v1 = *a1;
  *a1 = 0;
  return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
}

```

## disassembly

```asm
0x18000abac  mov     rdx, [rcx]
0x18000abaf  mov     qword ptr [rcx], 0
0x18000abb6  mov     rcx, rdx
0x18000abb9  mov     rax, [rdx]
0x18000abbc  mov     rax, [rax+10h]
0x18000abc0  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
