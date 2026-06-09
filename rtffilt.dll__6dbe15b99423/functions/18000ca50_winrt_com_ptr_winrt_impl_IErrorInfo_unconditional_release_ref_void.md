# winrt::com_ptr<winrt::impl::IErrorInfo>::unconditional_release_ref(void)

- ea: `0x18000ca50`
- end: `0x18000ca69`
- name: `?unconditional_release_ref@?$com_ptr@UIErrorInfo@impl@winrt@@@winrt@@AEAAXXZ`
- size: `25`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180019de0`
- `0x18001a226`

## callees

- `0x18001b010`

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
0x18000ca50  mov     rdx, [rcx]
0x18000ca53  mov     qword ptr [rcx], 0
0x18000ca5a  mov     rcx, rdx
0x18000ca5d  mov     rax, [rdx]
0x18000ca60  mov     rax, [rax+10h]
0x18000ca64  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
