# winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)

- ea: `0x14005fcbc`
- end: `0x14005fcd5`
- name: `?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ`
- size: `25`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `39`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14004c588`
- `0x14004c644`
- `0x14004ec70`
- `0x14004edbc`
- `0x14004ef08`
- `0x14004f020`
- `0x14004f138`
- `0x14004f250`
- `0x14004f39c`
- `0x14004f4b4`
- `0x14004f5cc`
- `0x14004f6e4`
- `0x14004f800`
- `0x14004f91c`
- `0x14004fe34`
- `0x14004ff9c`
- `0x140050184`
- `0x14005038c`
- `0x14005043c`
- `0x140051ea0`
- `0x14005273c`
- `0x140052bf8`
- `0x140053660`
- `0x1400536e4`
- `0x1400538ac`
- `0x140053948`
- `0x140053fcc`
- `0x1400578bc`
- `0x140057a74`
- `0x140057e34`
- `0x14005add4`
- `0x14005b72c`
- `0x14005b8bc`
- `0x14005e3e0`
- `0x14005e538`
- `0x14005e648`
- `0x14005e8fc`
- `0x14005ec1c`
- `0x14005fbe0`

## callees

- `0x140067010`

## pseudocode

```c
__int64 __fastcall winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(__int64 *a1)
{
  __int64 v1; // rdx

  v1 = *a1;
  *a1 = 0;
  return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
}

```

## disassembly

```asm
0x14005fcbc  mov     rdx, [rcx]
0x14005fcbf  mov     qword ptr [rcx], 0
0x14005fcc6  mov     rcx, rdx
0x14005fcc9  mov     rax, [rdx]
0x14005fccc  mov     rax, [rax+10h]
0x14005fcd0  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
