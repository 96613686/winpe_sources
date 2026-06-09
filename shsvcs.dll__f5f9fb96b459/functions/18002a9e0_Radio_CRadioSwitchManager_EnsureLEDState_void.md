# Radio::CRadioSwitchManager::EnsureLEDState(void)

- ea: `0x18002a9e0`
- end: `0x18002aa0e`
- name: `?EnsureLEDState@CRadioSwitchManager@Radio@@QEAAXXZ`
- size: `46`
- prototype: `void __fastcall(Radio::CRadioSwitchManager *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180014de0`
- `0x18002aae8`
- `0x18002ac70`

## callees

- `0x18002a9e0`

## import_xrefs

- `Rmapi!__imp_GetAirplaneModeFromRegistry` at `0x18002a9ef`
- `Rmapi!__imp_GetAirplaneModeFromRegistry` at `0x18002a9ef`
- `Rmapi!__imp_SetRadioLed` at `0x18002aa02`
- `Rmapi!__imp_SetRadioLed` at `0x18002aa02`

## pseudocode

```c
void __fastcall Radio::CRadioSwitchManager::EnsureLEDState(Radio::CRadioSwitchManager *this)
{
  unsigned __int8 AirplaneModeFromRegistry; // al

  if ( *((_BYTE *)this + 41) )
  {
    AirplaneModeFromRegistry = GetAirplaneModeFromRegistry();
    SetRadioLed((char *)this + 656, AirplaneModeFromRegistry ^ 1u);
  }
}

```

## disassembly

```asm
0x18002a9e0  push    rbx
0x18002a9e2  sub     rsp, 20h
0x18002a9e6  cmp     byte ptr [rcx+29h], 0
0x18002a9ea  mov     rbx, rcx
0x18002a9ed  jz      short loc_18002AA08
0x18002a9ef  call    cs:__imp_GetAirplaneModeFromRegistry
0x18002a9f5  movzx   edx, al
0x18002a9f8  lea     rcx, [rbx+290h]
0x18002a9ff  xor     edx, 1
0x18002aa02  call    cs:__imp_SetRadioLed
0x18002aa08  add     rsp, 20h
0x18002aa0c  pop     rbx
0x18002aa0d  retn
```
