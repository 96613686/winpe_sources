# WinUSB_DispatchIsochRequests

- ea: `0x14000c948`
- end: `0x14000ca5a`
- name: `WinUSB_DispatchIsochRequests`
- size: `274`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x14000c500`
- `0x14000d9a0`
- `0x14000da50`
- `0x14000e080`

## callees

- `0x140001020`
- `0x14000c948`
- `0x14000eff0`
- `0x140010700`

## pseudocode

```c
void __fastcall WinUSB_DispatchIsochRequests(__int64 a1)
{
  __int64 v2; // rax
  __int64 v3; // rdi
  signed __int32 v4; // ecx
  bool v5; // cc
  signed __int32 v6; // ecx

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      5u,
      1u,
      0x33u,
      (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids);
  if ( _InterlockedIncrement((volatile signed __int32 *)(a1 + 208)) <= 1 )
  {
    v2 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 1392))(
           WdfDriverGlobals,
           *(_QWORD *)(a1 + 160));
    v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
           WdfDriverGlobals,
           v2,
           off_1400150F0);
    do
    {
      while ( 1 )
      {
        WinUSB_SubmitIsochRequests(v3, a1);
        v4 = _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 208), 0xFFFFFFFF);
        v5 = v4 <= 1;
        v6 = v4 - 1;
        if ( v5 )
          break;
        _InterlockedExchange((volatile __int32 *)(a1 + 208), 1);
      }
    }
    while ( v6 );
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
      WPP_RECORDER_SF_(
        (__int64)WPP_GLOBAL_Control->DeviceExtension,
        5u,
        1u,
        0x34u,
        (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids);
  }
}

```

## disassembly

```asm
0x14000c948  push    rbx
0x14000c94a  push    rbp
0x14000c94b  push    rdi
0x14000c94c  push    r14
0x14000c94e  push    r15
0x14000c950  sub     rsp, 30h
0x14000c954  mov     rbx, rcx
0x14000c957  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000c95e  xor     ebp, ebp
0x14000c960  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14000c967  lea     r15, WPP_0eec754a616436344c523d073d150c9e_Traceguids
0x14000c96e  jz      short loc_14000C995
0x14000c970  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c977  cmp     [rcx+48h], bp
0x14000c97b  jz      short loc_14000C995
0x14000c97d  mov     rcx, [rcx+40h]
0x14000c981  lea     r9d, [rbp+33h]
0x14000c985  lea     r8d, [rbp+1]
0x14000c989  mov     [rsp+58h+var_38], r15
0x14000c98e  mov     dl, 5
0x14000c990  call    WPP_RECORDER_SF_
0x14000c995  mov     eax, 1
0x14000c99a  lock xadd [rbx+0D0h], eax
0x14000c9a2  inc     eax
0x14000c9a4  cmp     eax, 1
0x14000c9a7  jg      short loc_14000CA1D
0x14000c9a9  mov     rax, cs:WdfFunctions_01015
0x14000c9b0  mov     rdx, [rbx+0A0h]
0x14000c9b7  mov     rcx, cs:WdfDriverGlobals
0x14000c9be  mov     rax, [rax+570h]
0x14000c9c5  call    _guard_dispatch_icall
0x14000c9ca  mov     rcx, cs:WdfFunctions_01015
0x14000c9d1  mov     rdx, rax
0x14000c9d4  mov     r8, cs:off_1400150F0
0x14000c9db  mov     rax, [rcx+650h]
0x14000c9e2  mov     rcx, cs:WdfDriverGlobals
0x14000c9e9  call    _guard_dispatch_icall
0x14000c9ee  mov     rdi, rax
0x14000c9f1  mov     rdx, rbx
0x14000c9f4  mov     rcx, rdi
0x14000c9f7  call    WinUSB_SubmitIsochRequests
0x14000c9fc  or      ecx, 0FFFFFFFFh
0x14000c9ff  lock xadd [rbx+0D0h], ecx
0x14000ca07  sub     ecx, 1
0x14000ca0a  jle     short loc_14000CA19
0x14000ca0c  mov     eax, 1
0x14000ca11  xchg    eax, [rbx+0D0h]
0x14000ca17  jmp     short loc_14000C9F1
0x14000ca19  test    ecx, ecx
0x14000ca1b  jnz     short loc_14000C9F1
0x14000ca1d  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14000ca24  jz      short loc_14000CA4D
0x14000ca26  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ca2d  cmp     [rcx+48h], bp
0x14000ca31  jz      short loc_14000CA4D
0x14000ca33  mov     rcx, [rcx+40h]
0x14000ca37  mov     r9d, 34h ; '4'
0x14000ca3d  mov     dl, 5
0x14000ca3f  mov     [rsp+58h+var_38], r15
0x14000ca44  lea     r8d, [r9-33h]
0x14000ca48  call    WPP_RECORDER_SF_
0x14000ca4d  add     rsp, 30h
0x14000ca51  pop     r15
0x14000ca53  pop     r14
0x14000ca55  pop     rdi
0x14000ca56  pop     rbp
0x14000ca57  pop     rbx
0x14000ca58  retn
```
