# WinNatRemovePacketFilterFromWFP

- ea: `0x1400139fc`
- end: `0x140013a82`
- name: `WinNatRemovePacketFilterFromWFP`
- size: `134`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000e9b0`

## callees

- `0x14000caa0`
- `0x140013250`
- `0x1400139fc`

## import_xrefs

- `fwpkclnt!FwpmFilterDeleteById0` at `0x140013a42`
- `fwpkclnt!FwpmFilterDeleteById0` at `0x140013a42`
- `fwpkclnt!FwpmEngineClose0` at `0x140013a68`
- `fwpkclnt!FwpmEngineClose0` at `0x140013a68`
- `fwpkclnt!FwpmEngineOpen0` at `0x140013a27`
- `fwpkclnt!FwpmEngineOpen0` at `0x140013a27`

## pseudocode

```c
__int64 __fastcall WinNatRemovePacketFilterFromWFP(__int64 a1)
{
  NTSTATUS v2; // ebx
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
  HANDLE engineHandle; // [rsp+48h] [rbp+10h] BYREF

  engineHandle = 0;
  v2 = FwpmEngineOpen0(0, 0xAu, 0, 0, &engineHandle);
  if ( v2 >= 0 )
  {
    v2 = FwpmFilterDeleteById0(engineHandle, *(_QWORD *)(a1 + 112));
    if ( v2 < 0 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v4, v3, v5);
  }
  WinNatDereferenceWFPFilters();
  if ( engineHandle )
    FwpmEngineClose0(engineHandle);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1400139fc  mov     r11, rsp
0x1400139ff  mov     [r11+8], rbx
0x140013a03  push    rdi
0x140013a04  sub     rsp, 30h
0x140013a08  xor     r9d, r9d; session
0x140013a0b  mov     qword ptr [r11+10h], 0
0x140013a13  mov     rdi, rcx
0x140013a16  lea     rax, [r11+10h]
0x140013a1a  xor     r8d, r8d; authIdentity
0x140013a1d  mov     [r11-18h], rax
0x140013a21  xor     ecx, ecx; serverName
0x140013a23  lea     edx, [r9+0Ah]; authnService
0x140013a27  call    cs:__imp_FwpmEngineOpen0
0x140013a2e  nop     dword ptr [rax+rax+00h]
0x140013a33  mov     ebx, eax
0x140013a35  test    eax, eax
0x140013a37  js      short loc_140013A59
0x140013a39  mov     rdx, [rdi+70h]; id
0x140013a3d  mov     rcx, [rsp+38h+engineHandle]; engineHandle
0x140013a42  call    cs:__imp_FwpmFilterDeleteById0
0x140013a49  nop     dword ptr [rax+rax+00h]
0x140013a4e  mov     ebx, eax
0x140013a50  test    eax, eax
0x140013a52  jns     short loc_140013A59
0x140013a54  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140013a59  call    WinNatDereferenceWFPFilters
0x140013a5e  mov     rcx, [rsp+38h+engineHandle]; engineHandle
0x140013a63  test    rcx, rcx
0x140013a66  jz      short loc_140013A74
0x140013a68  call    cs:__imp_FwpmEngineClose0
0x140013a6f  nop     dword ptr [rax+rax+00h]
0x140013a74  mov     eax, ebx
0x140013a76  mov     rbx, [rsp+38h+arg_0]
0x140013a7b  add     rsp, 30h
0x140013a7f  pop     rdi
0x140013a80  retn
```
