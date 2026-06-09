# WinUSB_EvtWriteIoStop

- ea: `0x14000ae20`
- end: `0x14000aef4`
- name: `WinUSB_EvtWriteIoStop`
- size: `212`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x140001020`
- `0x14000ae20`
- `0x140010700`

## pseudocode

```c
__int64 __fastcall WinUSB_EvtWriteIoStop(__int64 a1, __int64 a2, char a3)
{
  __int64 v4; // rdi
  __int64 result; // rax

  v4 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(a2) = 5;
    result = WPP_RECORDER_SF_(
               WPP_GLOBAL_Control->DeviceExtension,
               a2,
               1,
               39,
               (__int64)WPP_8fea48f46a3838764f6f48a247805a06_Traceguids);
  }
  if ( (a3 & 1) != 0 )
  {
    result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01015 + 2272))(
               WdfDriverGlobals,
               v4,
               0);
  }
  else if ( (a3 & 2) != 0 )
  {
    result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 2064))(WdfDriverGlobals, v4);
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(a2) = 5;
      return WPP_RECORDER_SF_(
               WPP_GLOBAL_Control->DeviceExtension,
               a2,
               1,
               40,
               (__int64)WPP_8fea48f46a3838764f6f48a247805a06_Traceguids);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000ae20  push    rbx
0x14000ae22  push    rbp
0x14000ae23  push    rdi
0x14000ae24  push    r14
0x14000ae26  sub     rsp, 38h
0x14000ae2a  mov     ebx, r8d
0x14000ae2d  mov     rdi, rdx
0x14000ae30  lea     rbp, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000ae37  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14000ae3e  lea     r14, WPP_8fea48f46a3838764f6f48a247805a06_Traceguids
0x14000ae45  jz      short loc_14000AE6F
0x14000ae47  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ae4e  cmp     word ptr [rcx+48h], 0
0x14000ae53  jz      short loc_14000AE6F
0x14000ae55  mov     rcx, [rcx+40h]
0x14000ae59  mov     r9d, 27h ; '''
0x14000ae5f  mov     dl, 5
0x14000ae61  mov     [rsp+58h+var_38], r14
0x14000ae66  lea     r8d, [r9-26h]
0x14000ae6a  call    WPP_RECORDER_SF_
0x14000ae6f  test    bl, 1
0x14000ae72  jz      short loc_14000AE96
0x14000ae74  mov     rax, cs:WdfFunctions_01015
0x14000ae7b  xor     r8d, r8d
0x14000ae7e  mov     rcx, cs:WdfDriverGlobals
0x14000ae85  mov     rdx, rdi
0x14000ae88  mov     rax, [rax+8E0h]
0x14000ae8f  call    _guard_dispatch_icall
0x14000ae94  jmp     short loc_14000AEB8
0x14000ae96  test    bl, 2
0x14000ae99  jz      short loc_14000AEB8
0x14000ae9b  mov     rax, cs:WdfFunctions_01015
0x14000aea2  mov     rdx, rdi
0x14000aea5  mov     rcx, cs:WdfDriverGlobals
0x14000aeac  mov     rax, [rax+810h]
0x14000aeb3  call    _guard_dispatch_icall
0x14000aeb8  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14000aebf  jz      short loc_14000AEE9
0x14000aec1  mov     rcx, cs:WPP_GLOBAL_Control
0x14000aec8  cmp     word ptr [rcx+48h], 0
0x14000aecd  jz      short loc_14000AEE9
0x14000aecf  mov     rcx, [rcx+40h]
0x14000aed3  mov     r9d, 28h ; '('
0x14000aed9  mov     dl, 5
0x14000aedb  mov     [rsp+58h+var_38], r14
0x14000aee0  lea     r8d, [r9-27h]
0x14000aee4  call    WPP_RECORDER_SF_
0x14000aee9  add     rsp, 38h
0x14000aeed  pop     r14
0x14000aeef  pop     rdi
0x14000aef0  pop     rbp
0x14000aef1  pop     rbx
0x14000aef2  retn
```
