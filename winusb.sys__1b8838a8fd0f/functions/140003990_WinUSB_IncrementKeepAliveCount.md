# WinUSB_IncrementKeepAliveCount

- ea: `0x140003990`
- end: `0x140003a0b`
- name: `WinUSB_IncrementKeepAliveCount`
- size: `123`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x140001e04`
- `0x1400034cc`
- `0x140008df0`
- `0x1400099d0`
- `0x14000a450`
- `0x14000af00`
- `0x14000b670`

## callees

- `0x140003990`
- `0x140010700`

## pseudocode

```c
void __fastcall WinUSB_IncrementKeepAliveCount(__int64 a1)
{
  __int64 v2; // rax
  __int64 v3; // rax

  if ( WPP_MAIN_CB.Queue.ListEntry.Flink )
  {
    if ( *(_QWORD *)(a1 + 392) )
    {
      v2 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01015 + 2216))(WdfDriverGlobals);
      v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1120))(WdfDriverGlobals, v2);
      ((void (__fastcall *)(__int64, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink)(v3, *(_QWORD *)(a1 + 392));
      _InterlockedIncrement((volatile signed __int32 *)(a1 + 400));
    }
  }
}

```

## disassembly

```asm
0x140003990  push    rbx
0x140003992  sub     rsp, 20h
0x140003996  cmp     qword ptr cs:WPP_MAIN_CB.Queue, 0
0x14000399e  mov     rbx, rcx
0x1400039a1  jz      short loc_140003A04
0x1400039a3  cmp     qword ptr [rcx+188h], 0
0x1400039ab  jz      short loc_140003A04
0x1400039ad  mov     rax, cs:WdfFunctions_01015
0x1400039b4  mov     rcx, cs:WdfDriverGlobals
0x1400039bb  mov     rax, [rax+8A8h]
0x1400039c2  call    _guard_dispatch_icall
0x1400039c7  mov     rcx, cs:WdfFunctions_01015
0x1400039ce  mov     rdx, rax
0x1400039d1  mov     r8, [rcx+460h]
0x1400039d8  mov     rcx, cs:WdfDriverGlobals
0x1400039df  mov     rax, r8
0x1400039e2  call    _guard_dispatch_icall
0x1400039e7  mov     rdx, [rbx+188h]
0x1400039ee  mov     rcx, rax
0x1400039f1  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400039f8  call    _guard_dispatch_icall
0x1400039fd  lock inc dword ptr [rbx+190h]
0x140003a04  add     rsp, 20h
0x140003a08  pop     rbx
0x140003a09  retn
```
