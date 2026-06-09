# HUBFDO_EvtDeviceDestroyCallback

- ea: `0x14000d7a0`
- end: `0x14000d7ff`
- name: `HUBFDO_EvtDeviceDestroyCallback`
- size: `95`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14000d7a0`
- `0x140045570`

## import_xrefs

- `ntoskrnl!ExDeleteTimer` at `0x14000d7e1`
- `ntoskrnl!ExDeleteTimer` at `0x14000d7e1`

## pseudocode

```c
__int64 __fastcall HUBFDO_EvtDeviceDestroyCallback(__int64 a1)
{
  __int64 result; // rax
  __int64 v2; // rdx
  __int64 v3; // rbx
  __int64 v4; // rcx

  result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
             WdfDriverGlobals,
             a1,
             off_14006B270);
  v3 = result;
  v4 = *(_QWORD *)(result + 2320);
  if ( v4 )
  {
    LOBYTE(v2) = 1;
    result = ExDeleteTimer(v4, v2, 0, 0);
    *(_QWORD *)(v3 + 2320) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x14000d7a0  push    rbx
0x14000d7a2  sub     rsp, 20h
0x14000d7a6  mov     rax, cs:WdfFunctions_01015
0x14000d7ad  mov     rdx, rcx
0x14000d7b0  mov     r8, cs:off_14006B270
0x14000d7b7  mov     rcx, cs:WdfDriverGlobals
0x14000d7be  mov     rax, [rax+650h]
0x14000d7c5  call    _guard_dispatch_icall
0x14000d7ca  mov     rbx, rax
0x14000d7cd  mov     rcx, [rax+910h]
0x14000d7d4  test    rcx, rcx
0x14000d7d7  jz      short loc_14000D7F8
0x14000d7d9  xor     r9d, r9d
0x14000d7dc  xor     r8d, r8d
0x14000d7df  mov     dl, 1
0x14000d7e1  call    cs:__imp_ExDeleteTimer
0x14000d7e8  nop     dword ptr [rax+rax+00h]
0x14000d7ed  mov     qword ptr [rbx+910h], 0
0x14000d7f8  add     rsp, 20h
0x14000d7fc  pop     rbx
0x14000d7fd  retn
```
