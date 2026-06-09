# WinUSB_StartDeviceControlQueues

- ea: `0x14000529c`
- end: `0x1400053cc`
- name: `WinUSB_StartDeviceControlQueues`
- size: `304`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1400026d0`
- `0x1400053d4`
- `0x1400190b0`

## callees

- `0x140001020`
- `0x14000529c`
- `0x140010700`

## pseudocode

```c
__int64 __fastcall WinUSB_StartDeviceControlQueues(__int64 a1)
{
  __int64 v2; // rax
  __int64 v3; // rbx
  __int64 result; // rax

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      5u,
      1u,
      0xD8u,
      (__int64)WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids);
  v2 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1632))(WdfDriverGlobals, a1);
  v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 736))(WdfDriverGlobals, v2);
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 1232))(
    WdfDriverGlobals,
    *(_QWORD *)(a1 + 328));
  result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1232))(WdfDriverGlobals, v3);
  if ( *(_QWORD *)(a1 + 416) )
    result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01015 + 1232))(WdfDriverGlobals);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
      return WPP_RECORDER_SF_(
               (__int64)WPP_GLOBAL_Control->DeviceExtension,
               5u,
               1u,
               0xD9u,
               (__int64)WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x14000529c  push    rbx
0x14000529e  push    rbp
0x14000529f  push    rsi
0x1400052a0  push    rdi
0x1400052a1  push    r15
0x1400052a3  sub     rsp, 30h
0x1400052a7  mov     rdi, rcx
0x1400052aa  lea     rbp, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400052b1  xor     esi, esi
0x1400052b3  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x1400052ba  lea     r15, WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids
0x1400052c1  jz      short loc_1400052EA
0x1400052c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400052ca  cmp     [rcx+48h], si
0x1400052ce  jz      short loc_1400052EA
0x1400052d0  mov     rcx, [rcx+40h]
0x1400052d4  lea     r8d, [rsi+1]
0x1400052d8  mov     r9d, 0D8h
0x1400052de  mov     [rsp+58h+var_38], r15
0x1400052e3  mov     dl, 5
0x1400052e5  call    WPP_RECORDER_SF_
0x1400052ea  mov     rax, cs:WdfFunctions_01015
0x1400052f1  mov     rdx, rdi
0x1400052f4  mov     rcx, cs:WdfDriverGlobals
0x1400052fb  mov     rax, [rax+660h]
0x140005302  call    _guard_dispatch_icall
0x140005307  mov     rcx, cs:WdfFunctions_01015
0x14000530e  mov     rdx, rax
0x140005311  mov     r8, [rcx+2E0h]
0x140005318  mov     rcx, cs:WdfDriverGlobals
0x14000531f  mov     rax, r8
0x140005322  call    _guard_dispatch_icall
0x140005327  mov     rcx, cs:WdfFunctions_01015
0x14000532e  mov     rbx, rax
0x140005331  mov     rdx, [rdi+148h]
0x140005338  mov     rax, [rcx+4D0h]
0x14000533f  mov     rcx, cs:WdfDriverGlobals
0x140005346  call    _guard_dispatch_icall
0x14000534b  mov     rcx, cs:WdfFunctions_01015
0x140005352  mov     rdx, rbx
0x140005355  mov     rax, [rcx+4D0h]
0x14000535c  mov     rcx, cs:WdfDriverGlobals
0x140005363  call    _guard_dispatch_icall
0x140005368  mov     rdx, [rdi+1A0h]
0x14000536f  test    rdx, rdx
0x140005372  jz      short loc_14000538E
0x140005374  mov     rax, cs:WdfFunctions_01015
0x14000537b  mov     rcx, cs:WdfDriverGlobals
0x140005382  mov     rax, [rax+4D0h]
0x140005389  call    _guard_dispatch_icall
0x14000538e  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x140005395  jz      short loc_1400053C0
0x140005397  mov     rcx, cs:WPP_GLOBAL_Control
0x14000539e  cmp     [rcx+48h], si
0x1400053a2  jz      short loc_1400053C0
0x1400053a4  mov     rcx, [rcx+40h]
0x1400053a8  mov     r9d, 0D9h
0x1400053ae  mov     r8d, 1
0x1400053b4  mov     [rsp+58h+var_38], r15
0x1400053b9  mov     dl, 5
0x1400053bb  call    WPP_RECORDER_SF_
0x1400053c0  add     rsp, 30h
0x1400053c4  pop     r15
0x1400053c6  pop     rdi
0x1400053c7  pop     rsi
0x1400053c8  pop     rbp
0x1400053c9  pop     rbx
0x1400053ca  retn
```
