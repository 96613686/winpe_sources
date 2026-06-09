# WimpFSFBreakForIntegrityFailure

- ea: `0x140029594`
- end: `0x1400295d4`
- name: `WimpFSFBreakForIntegrityFailure`
- size: `64`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140029c50`
- `0x140029f28`
- `0x14002abe8`

## callees

- `0x140029594`

## import_xrefs

- `ntoskrnl!RtlCheckRegistryKey` at `0x1400295bd`
- `ntoskrnl!RtlCheckRegistryKey` at `0x1400295bd`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x1400295a1`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x1400295a1`

## pseudocode

```c
void WimpFSFBreakForIntegrityFailure()
{
  if ( !g_WimIntegrityDoNotBreakIntoKd
    && !KdRefreshDebuggerNotPresent()
    && RtlCheckRegistryKey(2u, (PWSTR)L"CI\\WIMIntegrity\\DisableKdBreak") < 0 )
  {
    __debugbreak();
  }
}

```

## disassembly

```asm
0x140029594  sub     rsp, 28h
0x140029598  cmp     cs:g_WimIntegrityDoNotBreakIntoKd, 0
0x14002959f  jnz     short loc_1400295CE
0x1400295a1  call    cs:__imp_KdRefreshDebuggerNotPresent
0x1400295a8  nop     dword ptr [rax+rax+00h]
0x1400295ad  test    al, al
0x1400295af  jnz     short loc_1400295CE
0x1400295b1  lea     rdx, Path; "CI\\WIMIntegrity\\DisableKdBreak"
0x1400295b8  mov     ecx, 2; RelativeTo
0x1400295bd  call    cs:__imp_RtlCheckRegistryKey
0x1400295c4  nop     dword ptr [rax+rax+00h]
0x1400295c9  test    eax, eax
0x1400295cb  jns     short loc_1400295CE
0x1400295cd  int     3; Trap to Debugger
0x1400295ce  add     rsp, 28h
0x1400295d2  retn
```
