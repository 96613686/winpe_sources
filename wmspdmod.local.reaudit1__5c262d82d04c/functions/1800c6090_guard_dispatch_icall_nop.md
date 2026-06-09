# _guard_dispatch_icall_nop

- ea: `0x1800c6090`
- end: `0x1800c6092`
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
- `0x18006d8b0`
- `0x18006db30`
- `0x18006dc30`
- `0x18006dd60`
- `0x18006de50`
- `0x18006e090`
- `0x18006e0e0`
- `0x18006e640`
- `0x18006e710`
- `0x180078f18`
- `0x180079244`
- `0x1800795c0`
- `0x18007c4e0`
- `0x18007c65c`
- `0x18007c7b4`
- `0x18007cad0`
- `0x18007cd70`
- `0x180082218`
- `0x180082540`
- `0x180082710`

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
0x1800c6090  jmp     rax
```
