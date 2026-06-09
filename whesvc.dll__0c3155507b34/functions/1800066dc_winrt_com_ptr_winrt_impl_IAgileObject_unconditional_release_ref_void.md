# winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)

- ea: `0x1800066dc`
- end: `0x1800066f5`
- name: `?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ`
- size: `25`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `29`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180010094`
- `0x180010550`
- `0x180011000`
- `0x180011bdc`
- `0x180011ed0`
- `0x1800120a0`
- `0x180019c88`
- `0x18001a1f0`
- `0x18001a69c`
- `0x18001a868`
- `0x18001aa34`
- `0x18001b6d4`
- `0x18001b748`
- `0x18001bfec`
- `0x18001c0e4`
- `0x180020634`
- `0x180020a8c`
- `0x180020dc4`
- `0x1800214d8`
- `0x1800227bc`
- `0x180022fcc`
- `0x180023438`
- `0x1800236f8`
- `0x180023ae8`
- `0x180023ba8`
- `0x1800255e0`
- `0x1800256ac`
- `0x180026b9a`
- `0x180026e6a`

## callees

- `0x180029010`

## pseudocode

```c
__int64 __fastcall winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(__int64 *a1)
{
  __int64 v1; // rdx

  v1 = *a1;
  *a1 = 0;
  return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
}

```

## disassembly

```asm
0x1800066dc  mov     rdx, [rcx]
0x1800066df  mov     qword ptr [rcx], 0
0x1800066e6  mov     rcx, rdx
0x1800066e9  mov     rax, [rdx]
0x1800066ec  mov     rax, [rax+10h]
0x1800066f0  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
