# WinUSB_IsochQueueReadyNotification

- ea: `0x14000d9a0`
- end: `0x14000da3b`
- name: `WinUSB_IsochQueueReadyNotification`
- size: `155`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callees

- `0x140001020`
- `0x14000c948`
- `0x14000d9a0`

## pseudocode

```c
__int64 __fastcall WinUSB_IsochQueueReadyNotification(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx
  __int64 result; // rax
  int v4; // edx

  v2 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      53,
      (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids);
  }
  result = WinUSB_DispatchIsochRequests(v2);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v4) = 5;
      return WPP_RECORDER_SF_(
               WPP_GLOBAL_Control->DeviceExtension,
               v4,
               1,
               54,
               (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000d9a0  mov     [rsp+arg_0], rbx
0x14000d9a5  mov     [rsp+arg_8], rbp
0x14000d9aa  push    rdi
0x14000d9ab  sub     rsp, 30h
0x14000d9af  mov     rbx, rdx
0x14000d9b2  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000d9b9  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14000d9c0  lea     rbp, WPP_0eec754a616436344c523d073d150c9e_Traceguids
0x14000d9c7  jz      short loc_14000D9F1
0x14000d9c9  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d9d0  cmp     word ptr [rcx+48h], 0
0x14000d9d5  jz      short loc_14000D9F1
0x14000d9d7  mov     rcx, [rcx+40h]
0x14000d9db  mov     r9d, 35h ; '5'
0x14000d9e1  mov     dl, 5
0x14000d9e3  mov     [rsp+38h+var_18], rbp
0x14000d9e8  lea     r8d, [r9-34h]
0x14000d9ec  call    WPP_RECORDER_SF_
0x14000d9f1  mov     rcx, rbx
0x14000d9f4  call    WinUSB_DispatchIsochRequests
0x14000d9f9  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x14000da00  jz      short loc_14000DA2A
0x14000da02  mov     rcx, cs:WPP_GLOBAL_Control
0x14000da09  cmp     word ptr [rcx+48h], 0
0x14000da0e  jz      short loc_14000DA2A
0x14000da10  mov     rcx, [rcx+40h]
0x14000da14  mov     r9d, 36h ; '6'
0x14000da1a  mov     dl, 5
0x14000da1c  mov     [rsp+38h+var_18], rbp
0x14000da21  lea     r8d, [r9-35h]
0x14000da25  call    WPP_RECORDER_SF_
0x14000da2a  mov     rbx, [rsp+38h+arg_0]
0x14000da2f  mov     rbp, [rsp+38h+arg_8]
0x14000da34  add     rsp, 30h
0x14000da38  pop     rdi
0x14000da39  retn
```
