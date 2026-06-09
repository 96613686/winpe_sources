# WinUSB_DecrementKeepAliveCount

- ea: `0x14000264c`
- end: `0x1400026c7`
- name: `WinUSB_DecrementKeepAliveCount`
- size: `123`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x140001e04`
- `0x1400024d0`
- `0x1400034cc`
- `0x140008df0`
- `0x1400093e0`
- `0x1400099d0`
- `0x14000a450`
- `0x14000af00`
- `0x14000b670`

## callees

- `0x14000264c`
- `0x140010700`

## pseudocode

```c
void __fastcall WinUSB_DecrementKeepAliveCount(__int64 a1)
{
  __int64 v2; // rax
  __int64 v3; // rax

  if ( WPP_MAIN_CB.Queue.ListEntry.Flink )
  {
    if ( *(_QWORD *)(a1 + 392) )
    {
      v2 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01015 + 2216))(WdfDriverGlobals);
      v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1120))(WdfDriverGlobals, v2);
      (*(void (__fastcall **)(__int64, _QWORD))&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels)(v3, *(_QWORD *)(a1 + 392));
      _InterlockedDecrement((volatile signed __int32 *)(a1 + 400));
    }
  }
}

```

## disassembly

```asm
0x14000264c  push    rbx
0x14000264e  sub     rsp, 20h
0x140002652  cmp     qword ptr cs:WPP_MAIN_CB.Queue, 0
0x14000265a  mov     rbx, rcx
0x14000265d  jz      short loc_1400026C0
0x14000265f  cmp     qword ptr [rcx+188h], 0
0x140002667  jz      short loc_1400026C0
0x140002669  mov     rax, cs:WdfFunctions_01015
0x140002670  mov     rcx, cs:WdfDriverGlobals
0x140002677  mov     rax, [rax+8A8h]
0x14000267e  call    _guard_dispatch_icall
0x140002683  mov     rcx, cs:WdfFunctions_01015
0x14000268a  mov     rdx, rax
0x14000268d  mov     r8, [rcx+460h]
0x140002694  mov     rcx, cs:WdfDriverGlobals
0x14000269b  mov     rax, r8
0x14000269e  call    _guard_dispatch_icall
0x1400026a3  mov     rdx, [rbx+188h]
0x1400026aa  mov     rcx, rax
0x1400026ad  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x1400026b4  call    _guard_dispatch_icall
0x1400026b9  lock dec dword ptr [rbx+190h]
0x1400026c0  add     rsp, 20h
0x1400026c4  pop     rbx
0x1400026c5  retn
```
