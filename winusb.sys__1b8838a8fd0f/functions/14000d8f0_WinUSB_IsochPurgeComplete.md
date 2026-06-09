# WinUSB_IsochPurgeComplete

- ea: `0x14000d8f0`
- end: `0x14000d999`
- name: `WinUSB_IsochPurgeComplete`
- size: `169`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140001020`
- `0x14000d8f0`
- `0x140010700`

## pseudocode

```c
__int64 __fastcall WinUSB_IsochPurgeComplete(__int64 a1)
{
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        5,
        1,
        89,
        (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        4,
        3,
        90,
        (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids);
  }
  return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1232))(WdfDriverGlobals, a1);
}

```

## disassembly

```asm
0x14000d8f0  mov     [rsp+arg_0], rbx
0x14000d8f5  mov     [rsp+arg_8], rsi
0x14000d8fa  push    rdi
0x14000d8fb  sub     rsp, 30h
0x14000d8ff  mov     rbx, rcx
0x14000d902  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000d909  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14000d910  jz      short loc_14000D96B
0x14000d912  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d919  lea     rsi, WPP_0eec754a616436344c523d073d150c9e_Traceguids
0x14000d920  cmp     word ptr [rcx+48h], 0
0x14000d925  jz      short loc_14000D941
0x14000d927  mov     rcx, [rcx+40h]
0x14000d92b  mov     r9d, 59h ; 'Y'
0x14000d931  mov     dl, 5
0x14000d933  mov     [rsp+38h+var_18], rsi
0x14000d938  lea     r8d, [r9-58h]
0x14000d93c  call    WPP_RECORDER_SF_
0x14000d941  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x14000d948  jz      short loc_14000D96B
0x14000d94a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d951  mov     r9d, 5Ah ; 'Z'
0x14000d957  mov     dl, 4
0x14000d959  mov     [rsp+38h+var_18], rsi
0x14000d95e  mov     rcx, [rcx+40h]
0x14000d962  lea     r8d, [r9-57h]
0x14000d966  call    WPP_RECORDER_SF_
0x14000d96b  mov     rax, cs:WdfFunctions_01015
0x14000d972  mov     rdx, rbx
0x14000d975  mov     rcx, cs:WdfDriverGlobals
0x14000d97c  mov     rax, [rax+4D0h]
0x14000d983  call    _guard_dispatch_icall
0x14000d988  mov     rbx, [rsp+38h+arg_0]
0x14000d98d  mov     rsi, [rsp+38h+arg_8]
0x14000d992  add     rsp, 30h
0x14000d996  pop     rdi
0x14000d997  retn
```
