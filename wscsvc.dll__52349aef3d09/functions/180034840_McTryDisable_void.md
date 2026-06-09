# McTryDisable(void)

- ea: `0x180034840`
- end: `0x180034853`
- name: `?McTryDisable@@YAXXZ`
- size: `19`
- prototype: `void __fastcall(HKEY)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180034334`

## string_xrefs

- `0x180034847`: `SYSTEM\CurrentControlSet\Control\MCUpdate`

## pseudocode

```c
void __fastcall McTryDisable(HKEY a1)
{
  VelocityDeleteReg(a1, L"SYSTEM\\CurrentControlSet\\Control\\MCUpdate", L"SelfHost");
}

```

## disassembly

```asm
0x180034840  lea     r8, aSelfhost; "SelfHost"
0x180034847  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Control\\MCU"...
0x18003484e  jmp     ?VelocityDeleteReg@@YAHPEAUHKEY__@@PEBG1@Z; VelocityDeleteReg(HKEY__ *,ushort const *,ushort const *)
```
