# winrt::com_ptr<winrt::impl::IErrorInfo>::unconditional_release_ref(void)

- ea: `0x180013ff8`
- end: `0x180014011`
- name: `?unconditional_release_ref@?$com_ptr@UIErrorInfo@impl@winrt@@@winrt@@AEAAXXZ`
- size: `25`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180015780`
- `0x180015bc6`

## callees

- `0x180017010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
0x180013ff8  mov     rdx, [rcx]
0x180013ffb  mov     qword ptr [rcx], 0
0x180014002  mov     rcx, rdx
0x180014005  mov     rax, [rdx]
0x180014008  mov     rax, [rax+10h]
0x18001400c  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
