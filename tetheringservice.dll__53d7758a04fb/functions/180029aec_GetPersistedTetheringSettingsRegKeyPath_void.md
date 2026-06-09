# GetPersistedTetheringSettingsRegKeyPath(void)

- ea: `0x180029aec`
- end: `0x180029b5b`
- name: `?GetPersistedTetheringSettingsRegKeyPath@@YAPEAGXZ`
- size: `111`
- prototype: `unsigned __int16 near **(void)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180029c10`
- `0x180029ec8`
- `0x18002bd20`

## callees

- `0x180029aec`

## import_xrefs

- `ntdll!RtlGetPersistedStateLocation` at `0x180029b33`
- `ntdll!RtlGetPersistedStateLocation` at `0x180029b33`

## string_xrefs

- `0x180029b0b`: `System\CurrentControlSet\Services\IcsSvc\Settings`

## pseudocode

```c
unsigned __int16 near **GetPersistedTetheringSettingsRegKeyPath(void)
{
  unsigned __int16 near **v0; // rbx

  if ( (_WORD)g_PersistedRegSettingsPath )
    return &g_PersistedRegSettingsPath;
  v0 = &g_PersistedRegSettingsPath;
  if ( (int)RtlGetPersistedStateLocation(
              L"TetheringSettings",
              0,
              L"System\\CurrentControlSet\\Services\\IcsSvc\\Settings",
              0,
              &g_PersistedRegSettingsPath,
              520,
              0) < 0 )
    return (unsigned __int16 near **)L"System\\CurrentControlSet\\Services\\IcsSvc\\Settings";
  return v0;
}

```

## disassembly

```asm
0x180029aec  mov     rax, rsp
0x180029aef  mov     [rax+8], rbx
0x180029af3  mov     [rax+10h], rsi
0x180029af7  push    rdi
0x180029af8  sub     rsp, 40h
0x180029afc  xor     esi, esi
0x180029afe  cmp     cs:?g_PersistedRegSettingsPath@@3PAGA, si; ushort near * g_PersistedRegSettingsPath
0x180029b05  jnz     short loc_180029B44
0x180029b07  mov     [rax-18h], rsi
0x180029b0b  lea     rdi, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\Ic"...
0x180029b12  mov     dword ptr [rax-20h], 208h
0x180029b19  lea     rbx, ?g_PersistedRegSettingsPath@@3PAGA; ushort near * g_PersistedRegSettingsPath
0x180029b20  mov     r8, rdi
0x180029b23  mov     [rax-28h], rbx
0x180029b27  xor     r9d, r9d
0x180029b2a  lea     rcx, aTetheringsetti; "TetheringSettings"
0x180029b31  xor     edx, edx
0x180029b33  call    cs:__imp_RtlGetPersistedStateLocation
0x180029b39  test    eax, eax
0x180029b3b  cmovs   rbx, rdi
0x180029b3f  mov     rax, rbx
0x180029b42  jmp     short loc_180029B4B
0x180029b44  lea     rax, ?g_PersistedRegSettingsPath@@3PAGA; ushort near * g_PersistedRegSettingsPath
0x180029b4b  mov     rbx, [rsp+48h+arg_0]
0x180029b50  mov     rsi, [rsp+48h+arg_8]
0x180029b55  add     rsp, 40h
0x180029b59  pop     rdi
0x180029b5a  retn
```
