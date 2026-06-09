# ShouldUseWlanString

- ea: `0x18003ace0`
- end: `0x18003ad46`
- name: `ShouldUseWlanString`
- size: `102`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18003ace0`

## import_xrefs

- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x18003ad2a`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x18003ad2a`

## pseudocode

```c
_BOOL8 ShouldUseWlanString()
{
  int v1; // [rsp+50h] [rbp+8h] BYREF

  v1 = 0;
  return !(unsigned int)GetPersistedRegistryValueW(
                          L"SettingsNetwork",
                          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Control Panel\\Settings\\Network",
                          L"WiFiToWlan",
                          16,
                          0,
                          &v1,
                          4,
                          0)
      && v1 != 0;
}

```

## disassembly

```asm
0x18003ace0  mov     rax, rsp
0x18003ace3  sub     rsp, 48h
0x18003ace7  mov     qword ptr [rax-10h], 0
0x18003acef  mov     r9d, 10h
0x18003acf5  mov     dword ptr [rax-18h], 4
0x18003acfc  lea     r8, aWifitowlan; "WiFiToWlan"
0x18003ad03  mov     dword ptr [rax+8], 0
0x18003ad0a  lea     rax, [rax+8]
0x18003ad0e  mov     [rsp+48h+var_20], rax
0x18003ad13  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18003ad1a  lea     rcx, aSettingsnetwor; "SettingsNetwork"
0x18003ad21  mov     [rsp+48h+var_28], 0
0x18003ad2a  call    cs:__imp_GetPersistedRegistryValueW
0x18003ad30  test    eax, eax
0x18003ad32  jz      short loc_18003AD38
0x18003ad34  xor     eax, eax
0x18003ad36  jmp     short loc_18003AD41
0x18003ad38  xor     eax, eax
0x18003ad3a  cmp     [rsp+48h+arg_0], eax
0x18003ad3e  setnz   al
0x18003ad41  add     rsp, 48h
0x18003ad45  retn
```
