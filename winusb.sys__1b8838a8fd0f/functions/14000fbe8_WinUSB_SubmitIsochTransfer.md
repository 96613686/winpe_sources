# WinUSB_SubmitIsochTransfer

- ea: `0x14000fbe8`
- end: `0x14000fe0c`
- name: `WinUSB_SubmitIsochTransfer`
- size: `548`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, installer_update`

## callers

- `0x14000ea0c`
- `0x14000eff0`

## callees

- `0x140001020`
- `0x1400011c8`
- `0x1400013d0`
- `0x14000dccc`
- `0x14000e7bc`
- `0x14000fbe8`
- `0x14000fe14`
- `0x140010700`

## pseudocode

```c
__int64 __fastcall WinUSB_SubmitIsochTransfer(__int64 a1, unsigned int a2, int a3, __int64 a4, __int64 a5)
{
  __int64 v9; // rdi
  __int64 v10; // rbp
  int v11; // ebx
  int v12; // eax
  __int64 v14; // [rsp+28h] [rbp-50h]

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      5u,
      1u,
      0x78u,
      (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids);
  v9 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         a1,
         off_140015068);
  v10 = *(_QWORD *)v9;
  *(_QWORD *)(v9 + 16) = 0;
  v11 = WinUSB_MapIsochTransfer(v9);
  if ( v11 < 0 )
    goto LABEL_20;
  v11 = WinUSB_SetupIsochUrb(a1, a4, v10, *(_DWORD *)(v9 + 120), a2, a3);
  if ( v11 < 0 )
    goto LABEL_20;
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, __int64))(WdfFunctions_01015 + 2080))(
    WdfDriverGlobals,
    a1,
    a5,
    v9);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_q(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      4u,
      3u,
      0x79u,
      (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids,
      a1);
  _InterlockedAdd((volatile signed __int32 *)(v10 + 200), *(_DWORD *)(v9 + 40));
  if ( !(*(unsigned __int8 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, _QWORD))(WdfFunctions_01015 + 2024))(
          WdfDriverGlobals,
          a1,
          *(_QWORD *)(v10 + 160),
          0) )
  {
    _InterlockedAdd((volatile signed __int32 *)(v10 + 200), -*(_DWORD *)(v9 + 40));
    v12 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 2032))(WdfDriverGlobals, a1);
    v11 = v12;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(v14) = v12;
      WPP_RECORDER_SF_d(
        (__int64)WPP_GLOBAL_Control->DeviceExtension,
        2u,
        3u,
        0x7Au,
        (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids,
        v14);
    }
    if ( v11 < 0 )
    {
LABEL_20:
      if ( *(_QWORD *)(v9 + 16) )
        WinUSB_UnmapIsochBuffer(v9);
    }
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LODWORD(v14) = v11;
    WPP_RECORDER_SF_d(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      5u,
      1u,
      0x7Bu,
      (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids,
      v14);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14000fbe8  push    rbx
0x14000fbea  push    rbp
0x14000fbeb  push    rsi
0x14000fbec  push    rdi
0x14000fbed  push    r12
0x14000fbef  push    r13
0x14000fbf1  push    r14
0x14000fbf3  push    r15
0x14000fbf5  sub     rsp, 38h
0x14000fbf9  mov     r14, r9
0x14000fbfc  mov     r15d, r8d
0x14000fbff  mov     r12d, edx
0x14000fc02  mov     rsi, rcx
0x14000fc05  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000fc0c  xor     r13d, r13d
0x14000fc0f  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14000fc16  lea     rax, WPP_0eec754a616436344c523d073d150c9e_Traceguids
0x14000fc1d  jz      short loc_14000FC45
0x14000fc1f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fc26  cmp     [rcx+48h], r13w
0x14000fc2b  jz      short loc_14000FC45
0x14000fc2d  mov     rcx, [rcx+40h]
0x14000fc31  lea     r9d, [r13+78h]
0x14000fc35  lea     r8d, [r13+1]
0x14000fc39  mov     [rsp+78h+var_58], rax
0x14000fc3e  mov     dl, 5
0x14000fc40  call    WPP_RECORDER_SF_
0x14000fc45  mov     rax, cs:WdfFunctions_01015
0x14000fc4c  mov     rdx, rsi
0x14000fc4f  mov     r8, cs:off_140015068
0x14000fc56  mov     rcx, cs:WdfDriverGlobals
0x14000fc5d  mov     rax, [rax+650h]
0x14000fc64  call    _guard_dispatch_icall
0x14000fc69  mov     rcx, rax
0x14000fc6c  mov     rdi, rax
0x14000fc6f  mov     rbp, [rax]
0x14000fc72  mov     [rax+10h], r13
0x14000fc76  call    WinUSB_MapIsochTransfer
0x14000fc7b  mov     ebx, eax
0x14000fc7d  test    eax, eax
0x14000fc7f  js      loc_14000FDA7
0x14000fc85  mov     r9d, [rdi+78h]
0x14000fc89  mov     r8, rbp
0x14000fc8c  mov     dword ptr [rsp+78h+var_50], r15d
0x14000fc91  mov     rdx, r14
0x14000fc94  mov     rcx, rsi
0x14000fc97  mov     dword ptr [rsp+78h+var_58], r12d
0x14000fc9c  call    WinUSB_SetupIsochUrb
0x14000fca1  mov     ebx, eax
0x14000fca3  test    eax, eax
0x14000fca5  js      loc_14000FDA7
0x14000fcab  mov     rax, cs:WdfFunctions_01015
0x14000fcb2  mov     r9, rdi
0x14000fcb5  mov     r8, [rsp+78h+arg_20]
0x14000fcbd  mov     rdx, rsi
0x14000fcc0  mov     rcx, cs:WdfDriverGlobals
0x14000fcc7  mov     rax, [rax+820h]
0x14000fcce  call    _guard_dispatch_icall
0x14000fcd3  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000fcda  mov     r12d, 3
0x14000fce0  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14000fce7  lea     r14, WPP_0eec754a616436344c523d073d150c9e_Traceguids
0x14000fcee  jz      short loc_14000FD14
0x14000fcf0  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fcf7  lea     r9d, [r12+76h]
0x14000fcfc  mov     [rsp+78h+var_50], rsi
0x14000fd01  mov     r8d, r12d
0x14000fd04  mov     dl, 4
0x14000fd06  mov     [rsp+78h+var_58], r14
0x14000fd0b  mov     rcx, [rcx+40h]
0x14000fd0f  call    WPP_RECORDER_SF_q
0x14000fd14  mov     eax, [rdi+28h]
0x14000fd17  lock add [rbp+0C8h], eax
0x14000fd1e  mov     rax, cs:WdfFunctions_01015
0x14000fd25  xor     r9d, r9d
0x14000fd28  mov     r8, [rbp+0A0h]
0x14000fd2f  mov     rdx, rsi
0x14000fd32  mov     rcx, cs:WdfDriverGlobals
0x14000fd39  mov     rax, [rax+7E8h]
0x14000fd40  call    _guard_dispatch_icall
0x14000fd45  test    al, al
0x14000fd47  jnz     short loc_14000FDC3
0x14000fd49  mov     eax, [rdi+28h]
0x14000fd4c  neg     eax
0x14000fd4e  lock add [rbp+0C8h], eax
0x14000fd55  mov     rax, cs:WdfFunctions_01015
0x14000fd5c  mov     rdx, rsi
0x14000fd5f  mov     rcx, cs:WdfDriverGlobals
0x14000fd66  mov     rax, [rax+7F0h]
0x14000fd6d  call    _guard_dispatch_icall
0x14000fd72  mov     ebx, eax
0x14000fd74  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14000fd7b  jz      short loc_14000FDA1
0x14000fd7d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fd84  mov     r9d, 7Ah ; 'z'
0x14000fd8a  mov     dword ptr [rsp+78h+var_50], eax
0x14000fd8e  mov     r8d, r12d
0x14000fd91  mov     dl, 2
0x14000fd93  mov     [rsp+78h+var_58], r14
0x14000fd98  mov     rcx, [rcx+40h]
0x14000fd9c  call    WPP_RECORDER_SF_d
0x14000fda1  test    ebx, ebx
0x14000fda3  jns     short loc_14000FDC3
0x14000fda5  jmp     short loc_14000FDB5
0x14000fda7  lea     r15, WPP_RECORDER_INITIALIZED
0x14000fdae  lea     r14, WPP_0eec754a616436344c523d073d150c9e_Traceguids
0x14000fdb5  cmp     [rdi+10h], r13
0x14000fdb9  jz      short loc_14000FDC3
0x14000fdbb  mov     rcx, rdi
0x14000fdbe  call    WinUSB_UnmapIsochBuffer
0x14000fdc3  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14000fdca  jz      short loc_14000FDF8
0x14000fdcc  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fdd3  cmp     [rcx+48h], r13w
0x14000fdd8  jz      short loc_14000FDF8
0x14000fdda  mov     rcx, [rcx+40h]
0x14000fdde  mov     r9d, 7Bh ; '{'
0x14000fde4  mov     dword ptr [rsp+78h+var_50], ebx
0x14000fde8  mov     dl, 5
0x14000fdea  mov     [rsp+78h+var_58], r14
0x14000fdef  lea     r8d, [r9-7Ah]
0x14000fdf3  call    WPP_RECORDER_SF_d
0x14000fdf8  mov     eax, ebx
0x14000fdfa  add     rsp, 38h
0x14000fdfe  pop     r15
0x14000fe00  pop     r14
0x14000fe02  pop     r13
0x14000fe04  pop     r12
0x14000fe06  pop     rdi
0x14000fe07  pop     rsi
0x14000fe08  pop     rbp
0x14000fe09  pop     rbx
0x14000fe0a  retn
```
