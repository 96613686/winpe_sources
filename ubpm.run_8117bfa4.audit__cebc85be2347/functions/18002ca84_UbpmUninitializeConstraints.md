# UbpmUninitializeConstraints

- ea: `0x18002ca84`
- end: `0x18002cada`
- name: `UbpmUninitializeConstraints`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001880`

## callees

- `0x18002ca84`
- `0x180036d44`

## import_xrefs

- `CSystemEventsBrokerClient!CSebDeleteEvent` at `0x18002caae`
- `CSystemEventsBrokerClient!CSebDeleteEvent` at `0x18002caae`

## pseudocode

```c
__int64 UbpmUninitializeConstraints()
{
  __int64 i; // rbx
  __int64 v1; // rcx
  __int64 v2; // rcx

  for ( i = 0; i != 5; ++i )
  {
    v1 = 28 * i;
    if ( (*((_DWORD *)&g_CSebConditions + 7 * i + 5) || *(_DWORD *)((char *)&g_CSebConditions + v1 + 24))
      && (int)CSebDeleteEvent(*(struct _UBPM_GLOBAL_STATE_CONDITIONS near **)((char *)&g_CSebConditions + v1 + 20)) < 0 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v2);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18002ca84  mov     [rsp+arg_0], rbx
0x18002ca89  push    rdi
0x18002ca8a  sub     rsp, 20h
0x18002ca8e  xor     ebx, ebx
0x18002ca90  lea     rdi, ?g_CSebConditions@@3PAU_UBPM_GLOBAL_STATE_CONDITIONS@@A; _UBPM_GLOBAL_STATE_CONDITIONS near * g_CSebConditions
0x18002ca97  imul    rcx, rbx, 1Ch
0x18002ca9b  cmp     dword ptr [rcx+rdi+14h], 0
0x18002caa0  jnz     short loc_18002CAA9
0x18002caa2  cmp     dword ptr [rcx+rdi+18h], 0
0x18002caa7  jz      short loc_18002CAC3
0x18002caa9  mov     rcx, [rcx+rdi+14h]
0x18002caae  call    cs:__imp_CSebDeleteEvent
0x18002cab5  nop     dword ptr [rax+rax+00h]
0x18002caba  test    eax, eax
0x18002cabc  jns     short loc_18002CAC3
0x18002cabe  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002cac3  inc     rbx
0x18002cac6  cmp     rbx, 5
0x18002caca  jnz     short loc_18002CA97
0x18002cacc  mov     rbx, [rsp+28h+arg_0]
0x18002cad1  xor     eax, eax
0x18002cad3  add     rsp, 20h
0x18002cad7  pop     rdi
0x18002cad8  retn
```
