# WinUSB_ControlTransferCompletion

- ea: `0x1400024d0`
- end: `0x140002643`
- name: `WinUSB_ControlTransferCompletion`
- size: `371`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140001020`
- `0x1400011c8`
- `0x14000193c`
- `0x1400024d0`
- `0x14000264c`
- `0x140010700`

## pseudocode

```c
__int64 __fastcall WinUSB_ControlTransferCompletion(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v6; // rbx
  __int64 v8; // rax
  __int64 v9; // rax
  int v10; // eax
  int v11; // edx
  unsigned int v12; // ebx
  __int64 v13; // rdi
  __int64 result; // rax
  int v15; // edx

  v6 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      123,
      (__int64)WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids);
  }
  v8 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1392))(WdfDriverGlobals, v6);
  v9 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         v8,
         off_1400150F0);
  WinUSB_DecrementKeepAliveCount(v9, a1);
  v10 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 2032))(WdfDriverGlobals, a1);
  v12 = v10;
  if ( v10 >= 0 )
  {
    v13 = *(unsigned int *)(*(_QWORD *)(a3 + 24) + 24LL);
  }
  else
  {
    v13 = 0;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v11) = 2;
      WPP_RECORDER_SF_dD(
        WPP_GLOBAL_Control->DeviceExtension,
        v11,
        3,
        124,
        (__int64)WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids,
        *(_DWORD *)(a4 + 28),
        v10);
    }
  }
  result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, __int64))(WdfFunctions_01015 + 2120))(
             WdfDriverGlobals,
             a1,
             v12,
             v13);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v15) = 5;
      return WPP_RECORDER_SF_d(
               WPP_GLOBAL_Control->DeviceExtension,
               v15,
               1,
               125,
               (__int64)WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids,
               v12);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400024d0  push    rbx
0x1400024d2  push    rbp
0x1400024d3  push    rsi
0x1400024d4  push    rdi
0x1400024d5  push    r12
0x1400024d7  push    r14
0x1400024d9  push    r15
0x1400024db  sub     rsp, 40h
0x1400024df  mov     rbp, r9
0x1400024e2  mov     rdi, r8
0x1400024e5  mov     rbx, rdx
0x1400024e8  mov     rsi, rcx
0x1400024eb  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400024f2  xor     r14d, r14d
0x1400024f5  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400024fc  lea     r12, WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids
0x140002503  jz      short loc_14000252B
0x140002505  mov     rcx, cs:WPP_GLOBAL_Control
0x14000250c  cmp     [rcx+48h], r14w
0x140002511  jz      short loc_14000252B
0x140002513  mov     rcx, [rcx+40h]
0x140002517  lea     r9d, [r14+7Bh]
0x14000251b  lea     r8d, [r14+1]
0x14000251f  mov     [rsp+78h+var_58], r12
0x140002524  mov     dl, 5
0x140002526  call    WPP_RECORDER_SF_
0x14000252b  mov     rax, cs:WdfFunctions_01015
0x140002532  mov     rdx, rbx
0x140002535  mov     rcx, cs:WdfDriverGlobals
0x14000253c  mov     rax, [rax+570h]
0x140002543  call    _guard_dispatch_icall
0x140002548  mov     rcx, cs:WdfFunctions_01015
0x14000254f  mov     rdx, rax
0x140002552  mov     r8, cs:off_1400150F0
0x140002559  mov     rax, [rcx+650h]
0x140002560  mov     rcx, cs:WdfDriverGlobals
0x140002567  call    _guard_dispatch_icall
0x14000256c  mov     rdx, rsi
0x14000256f  mov     rcx, rax
0x140002572  call    WinUSB_DecrementKeepAliveCount
0x140002577  mov     rax, cs:WdfFunctions_01015
0x14000257e  mov     rdx, rsi
0x140002581  mov     rcx, cs:WdfDriverGlobals
0x140002588  mov     rax, [rax+7F0h]
0x14000258f  call    _guard_dispatch_icall
0x140002594  mov     ebx, eax
0x140002596  test    eax, eax
0x140002598  jns     short loc_1400025D4
0x14000259a  mov     rdi, r14
0x14000259d  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x1400025a4  jz      short loc_1400025DB
0x1400025a6  mov     ecx, [rbp+1Ch]
0x1400025a9  mov     r9d, 7Ch ; '|'
0x1400025af  mov     [rsp+78h+var_48], eax
0x1400025b3  mov     dl, 2
0x1400025b5  mov     [rsp+78h+var_50], ecx
0x1400025b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400025c0  lea     r8d, [r9-79h]
0x1400025c4  mov     [rsp+78h+var_58], r12
0x1400025c9  mov     rcx, [rcx+40h]
0x1400025cd  call    WPP_RECORDER_SF_dD
0x1400025d2  jmp     short loc_1400025DB
0x1400025d4  mov     rax, [rdi+18h]
0x1400025d8  mov     edi, [rax+18h]
0x1400025db  mov     rax, cs:WdfFunctions_01015
0x1400025e2  mov     r9, rdi
0x1400025e5  mov     rcx, cs:WdfDriverGlobals
0x1400025ec  mov     r8d, ebx
0x1400025ef  mov     rdx, rsi
0x1400025f2  mov     rax, [rax+848h]
0x1400025f9  call    _guard_dispatch_icall
0x1400025fe  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140002605  jz      short loc_140002633
0x140002607  mov     rcx, cs:WPP_GLOBAL_Control
0x14000260e  cmp     [rcx+48h], r14w
0x140002613  jz      short loc_140002633
0x140002615  mov     rcx, [rcx+40h]
0x140002619  mov     r9d, 7Dh ; '}'
0x14000261f  mov     [rsp+78h+var_50], ebx
0x140002623  mov     dl, 5
0x140002625  mov     [rsp+78h+var_58], r12
0x14000262a  lea     r8d, [r9-7Ch]
0x14000262e  call    WPP_RECORDER_SF_d
0x140002633  add     rsp, 40h
0x140002637  pop     r15
0x140002639  pop     r14
0x14000263b  pop     r12
0x14000263d  pop     rdi
0x14000263e  pop     rsi
0x14000263f  pop     rbp
0x140002640  pop     rbx
0x140002641  retn
```
