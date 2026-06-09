# winrt::com_ptr<IXMLDOMParseError>::unconditional_release_ref(void)

- ea: `0x140011570`
- end: `0x140011593`
- name: `?unconditional_release_ref@?$com_ptr@UIXMLDOMParseError@@@winrt@@AEAAXXZ`
- size: `35`
- prototype: ``
- caller_count: `15`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140001ce0`
- `0x14000997c`
- `0x140009ab4`
- `0x14000fc50`
- `0x140010704`
- `0x14001085c`
- `0x140010910`
- `0x140011304`
- `0x14001145c`
- `0x1400115c0`
- `0x1400117d8`
- `0x140011ce0`
- `0x140011dfc`
- `0x140012710`
- `0x140019c4c`

## callees

- `0x140034010`

## pseudocode

```c
__int64 __fastcall winrt::com_ptr<IXMLDOMParseError>::unconditional_release_ref(__int64 *a1)
{
  __int64 v1; // rdx

  v1 = *a1;
  *a1 = 0;
  return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
}

```

## disassembly

```asm
0x140011570  sub     rsp, 28h
0x140011574  mov     rdx, [rcx]
0x140011577  mov     qword ptr [rcx], 0
0x14001157e  mov     rax, [rdx]
0x140011581  mov     rcx, rdx
0x140011584  mov     rax, [rax+10h]
0x140011588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001158d  nop
0x14001158e  add     rsp, 28h
0x140011592  retn
```
