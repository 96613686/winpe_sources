# winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)

- ea: `0x140009ee0`
- end: `0x140009ef9`
- name: `?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ`
- size: `25`
- prototype: ``
- caller_count: `51`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140009dec`
- `0x14000c704`
- `0x14000ccdc`
- `0x14000cd18`
- `0x14000cd74`
- `0x14000cdd0`
- `0x14000ce2c`
- `0x14000d250`
- `0x14000d27c`
- `0x14000d2e8`
- `0x14000e72c`
- `0x14001080c`
- `0x140010e9c`
- `0x140011108`
- `0x14001d21c`
- `0x14001d26c`
- `0x14001d2b4`
- `0x14001d2fc`
- `0x14001d730`
- `0x14001e66c`
- `0x14001e7c0`
- `0x14001e86c`
- `0x14001eb2c`
- `0x14001ec70`
- `0x14001f340`
- `0x14001f504`
- `0x14001f584`
- `0x14001f5d4`
- `0x14001f624`
- `0x14001f674`
- `0x14001f6c4`
- `0x14001f778`
- `0x14001f818`
- `0x140021538`
- `0x140022168`
- `0x1400223d8`
- `0x14002323c`
- `0x1400237c4`
- `0x1400238dc`
- `0x1400239f4`
- `0x140023b0c`
- `0x140023c24`
- `0x140023d44`
- `0x140024118`
- `0x140024208`
- `0x140024450`
- `0x1400247dc`
- `0x140024f10`
- `0x140025030`
- `0x1400256e8`

## callees

- `0x140029010`

## pseudocode

```c
__int64 __fastcall winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(
        __int64 *a1)
{
  __int64 v1; // rdx

  v1 = *a1;
  *a1 = 0;
  return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
}

```

## disassembly

```asm
0x140009ee0  mov     rdx, [rcx]
0x140009ee3  mov     qword ptr [rcx], 0
0x140009eea  mov     rcx, rdx
0x140009eed  mov     rax, [rdx]
0x140009ef0  mov     rax, [rax+10h]
0x140009ef4  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
