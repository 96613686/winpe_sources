# _guard_dispatch_icall_nop

- ea: `0x1800c60f0`
- end: `0x1800c60f2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `134`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1800687e0`
- `0x180068bc8`
- `0x180068e60`
- `0x180069000`
- `0x1800691b0`
- `0x180069328`
- `0x180069cb0`
- `0x180069d30`
- `0x180069dd0`
- `0x18006a0c0`
- `0x18006a1c0`
- `0x18006a240`
- `0x18006a2c0`
- `0x18006a5b0`
- `0x18006a6a0`
- `0x18006a720`
- `0x18006a880`
- `0x18006c1e0`
- `0x18006c300`
- `0x18006c420`
- `0x18006c470`
- `0x18006c550`
- `0x18006c670`
- `0x18006c7a0`
- `0x18006c850`
- `0x18006c8a0`
- `0x18006c950`
- `0x18006cc40`
- `0x18006cd70`
- `0x18006d464`
- `0x18006d910`
- `0x18006db90`
- `0x18006dc90`
- `0x18006ddc0`
- `0x18006deb0`
- `0x18006e0f0`
- `0x18006e140`
- `0x18006e6a0`
- `0x18006e770`
- `0x180078f78`
- `0x1800792a4`
- `0x180079620`
- `0x18007c540`
- `0x18007c6bc`
- `0x18007c814`
- `0x18007cb30`
- `0x18007cdd0`
- `0x180082278`
- `0x1800825a0`
- `0x180082770`

## pseudocode

```c
__int64 __fastcall guard_dispatch_icall_nop()
{
  __int64 (*v0)(void); // rax

  return v0();
}

```

## disassembly

```asm
0x1800c60f0  jmp     rax
```
