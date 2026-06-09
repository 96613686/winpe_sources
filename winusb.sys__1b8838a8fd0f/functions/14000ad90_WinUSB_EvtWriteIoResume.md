# WinUSB_EvtWriteIoResume

- ea: `0x14000ad90`
- end: `0x14000ae16`
- name: `WinUSB_EvtWriteIoResume`
- size: `134`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x140001020`
- `0x14000ad90`

## pseudocode

```c
__int64 WinUSB_EvtWriteIoResume()
{
  __int64 result; // rax

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
      result = WPP_RECORDER_SF_(
                 WPP_GLOBAL_Control->DeviceExtension,
                 5,
                 1,
                 41,
                 (__int64)WPP_8fea48f46a3838764f6f48a247805a06_Traceguids);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
        return WPP_RECORDER_SF_(
                 WPP_GLOBAL_Control->DeviceExtension,
                 5,
                 1,
                 42,
                 (__int64)WPP_8fea48f46a3838764f6f48a247805a06_Traceguids);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000ad90  mov     [rsp+arg_0], rbx
0x14000ad95  push    rsi
0x14000ad96  sub     rsp, 30h
0x14000ad9a  lea     rbx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000ada1  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14000ada8  jz      short loc_14000AE0A
0x14000adaa  mov     rcx, cs:WPP_GLOBAL_Control
0x14000adb1  lea     rsi, WPP_8fea48f46a3838764f6f48a247805a06_Traceguids
0x14000adb8  cmp     word ptr [rcx+48h], 0
0x14000adbd  jz      short loc_14000ADD9
0x14000adbf  mov     rcx, [rcx+40h]
0x14000adc3  mov     r9d, 29h ; ')'
0x14000adc9  mov     dl, 5
0x14000adcb  mov     [rsp+38h+var_18], rsi
0x14000add0  lea     r8d, [r9-28h]
0x14000add4  call    WPP_RECORDER_SF_
0x14000add9  cmp     cs:WPP_RECORDER_INITIALIZED, rbx; __annotation("TMF:",
0x14000ade0  jz      short loc_14000AE0A
0x14000ade2  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ade9  cmp     word ptr [rcx+48h], 0
0x14000adee  jz      short loc_14000AE0A
0x14000adf0  mov     rcx, [rcx+40h]
0x14000adf4  mov     r9d, 2Ah ; '*'
0x14000adfa  mov     dl, 5
0x14000adfc  mov     [rsp+38h+var_18], rsi
0x14000ae01  lea     r8d, [r9-29h]
0x14000ae05  call    WPP_RECORDER_SF_
0x14000ae0a  mov     rbx, [rsp+38h+arg_0]
0x14000ae0f  add     rsp, 30h
0x14000ae13  pop     rsi
0x14000ae14  retn
```
