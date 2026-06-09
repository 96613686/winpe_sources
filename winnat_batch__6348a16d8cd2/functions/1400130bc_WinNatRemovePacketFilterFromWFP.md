# WinNatRemovePacketFilterFromWFP

- ea: `0x1400130bc`
- end: `0x140013142`
- name: `WinNatRemovePacketFilterFromWFP`
- size: `134`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000e980`

## callees

- `0x14000caa0`
- `0x140012910`
- `0x1400130bc`

## import_xrefs

- `fwpkclnt!FwpmFilterDeleteById0` at `0x140013102`
- `fwpkclnt!FwpmFilterDeleteById0` at `0x140013102`
- `fwpkclnt!FwpmEngineClose0` at `0x140013128`
- `fwpkclnt!FwpmEngineClose0` at `0x140013128`
- `fwpkclnt!FwpmEngineOpen0` at `0x1400130e7`
- `fwpkclnt!FwpmEngineOpen0` at `0x1400130e7`

## pseudocode

```c
__int64 __fastcall WinNatRemovePacketFilterFromWFP(__int64 a1)
{
  NTSTATUS v2; // ebx
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  HANDLE engineHandle; // [rsp+48h] [rbp+10h] BYREF

  engineHandle = 0;
  v2 = FwpmEngineOpen0(0, 0xAu, 0, 0, &engineHandle);
  if ( v2 >= 0 )
  {
    v2 = FwpmFilterDeleteById0(engineHandle, *(_QWORD *)(a1 + 112));
    if ( v2 < 0 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v4, v3, v5, v6);
  }
  WinNatDereferenceWFPFilters();
  if ( engineHandle )
    FwpmEngineClose0(engineHandle);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1400130bc  mov     r11, rsp
0x1400130bf  mov     [r11+8], rbx
0x1400130c3  push    rdi
0x1400130c4  sub     rsp, 30h
0x1400130c8  xor     r9d, r9d; session
0x1400130cb  mov     qword ptr [r11+10h], 0
0x1400130d3  mov     rdi, rcx
0x1400130d6  lea     rax, [r11+10h]
0x1400130da  xor     r8d, r8d; authIdentity
0x1400130dd  mov     [r11-18h], rax
0x1400130e1  xor     ecx, ecx; serverName
0x1400130e3  lea     edx, [r9+0Ah]; authnService
0x1400130e7  call    cs:__imp_FwpmEngineOpen0
0x1400130ee  nop     dword ptr [rax+rax+00h]
0x1400130f3  mov     ebx, eax
0x1400130f5  test    eax, eax
0x1400130f7  js      short loc_140013119
0x1400130f9  mov     rdx, [rdi+70h]; id
0x1400130fd  mov     rcx, [rsp+38h+engineHandle]; engineHandle
0x140013102  call    cs:__imp_FwpmFilterDeleteById0
0x140013109  nop     dword ptr [rax+rax+00h]
0x14001310e  mov     ebx, eax
0x140013110  test    eax, eax
0x140013112  jns     short loc_140013119
0x140013114  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140013119  call    WinNatDereferenceWFPFilters
0x14001311e  mov     rcx, [rsp+38h+engineHandle]; engineHandle
0x140013123  test    rcx, rcx
0x140013126  jz      short loc_140013134
0x140013128  call    cs:__imp_FwpmEngineClose0
0x14001312f  nop     dword ptr [rax+rax+00h]
0x140013134  mov     eax, ebx
0x140013136  mov     rbx, [rsp+38h+arg_0]
0x14001313b  add     rsp, 30h
0x14001313f  pop     rdi
0x140013140  retn
```
