# [thunk]:CWsmTrackingConfig::SetLogSessionInfo`adjustor{8}' (ushort const *,ushort const *)

- ea: `0x14000bf40`
- end: `0x14000bf49`
- name: `?SetLogSessionInfo@CWsmTrackingConfig@@W7EAAJPEBG0@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x14000bdf0`

## pseudocode

```c
__int64 __fastcall CWsmTrackingConfig::SetLogSessionInfo(
        __int64 a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  return CWsmTrackingConfig::SetLogSessionInfo((__int64 (__fastcall ***)(CWsmTrackingConfig *))(a1 - 8), a2, a3);
}

```

## disassembly

```asm
0x14000bf40  sub     rcx, 8; this
0x14000bf44  jmp     ?SetLogSessionInfo@CWsmTrackingConfig@@UEAAJPEBG0@Z; CWsmTrackingConfig::SetLogSessionInfo(ushort const *,ushort const *)
```
