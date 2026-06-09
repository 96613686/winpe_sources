# WinUSB_CancelRead

- ea: `0x1400088a0`
- end: `0x140008a9d`
- name: `WinUSB_CancelRead`
- size: `509`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x140001020`
- `0x1400088a0`
- `0x140010700`

## string_xrefs

- `0x1400089c2`: `onecore\drivers\wdm\usb\driver\winusb\sys\read.c`

## pseudocode

```c
__int64 __fastcall WinUSB_CancelRead(__int64 a1)
{
  __int64 v2; // rax
  __int64 v3; // rax
  __int64 v4; // rbx
  __int64 v5; // rax
  __int64 v6; // rdi
  __int64 v7; // rdx
  __int64 result; // rax
  __int64 v9; // r8
  _OWORD v10[5]; // [rsp+30h] [rbp-58h] BYREF

  memset(v10, 0, 24);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      65,
      (__int64)WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids);
  v2 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 2256))(WdfDriverGlobals, a1);
  v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1256))(WdfDriverGlobals, v2);
  v4 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         v3,
         off_1400150F0);
  v5 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         a1,
         off_140015040);
  v6 = *(_QWORD *)(*(_QWORD *)(v4 + 136)
                 + 8 * (*(unsigned __int8 *)(v5 + 24) + 35LL * *(unsigned __int8 *)(v5 + 25))
                 + 24);
  v7 = *(_QWORD *)(v6 + 104);
  *(_BYTE *)(v6 + 88) = 1;
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 2064))(WdfDriverGlobals, v7);
  LODWORD(v4) = _InterlockedExchange((volatile __int32 *)(v6 + 92), 1);
  result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, __int64, const char *))(WdfFunctions_01015
                                                                                                  + 1648))(
             WdfDriverGlobals,
             a1,
             0,
             1996,
             "onecore\\drivers\\wdm\\usb\\driver\\winusb\\sys\\read.c");
  if ( (_DWORD)v4 == 1 )
  {
    *(_QWORD *)((char *)v10 + 12) = 0;
    DWORD1(v10[1]) = 0;
    *(_QWORD *)&v10[0] = 24;
    DWORD2(v10[0]) = 0;
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _OWORD *))(WdfFunctions_01015 + 1992))(
      WdfDriverGlobals,
      *(_QWORD *)(v6 + 104),
      v10);
    v9 = *(unsigned int *)(v6 + 96);
    *(_QWORD *)(v6 + 80) = 0;
    result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01015 + 2104))(
               WdfDriverGlobals,
               a1,
               v9);
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
      return WPP_RECORDER_SF_(
               WPP_GLOBAL_Control->DeviceExtension,
               5,
               1,
               66,
               (__int64)WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x1400088a0  push    rbx
0x1400088a2  push    rbp
0x1400088a3  push    rsi
0x1400088a4  push    rdi
0x1400088a5  push    r12
0x1400088a7  push    r15
0x1400088a9  sub     rsp, 58h
0x1400088ad  xorps   xmm0, xmm0
0x1400088b0  xor     eax, eax
0x1400088b2  movups  [rsp+88h+var_58], xmm0
0x1400088b7  mov     [rsp+88h+var_48], rax
0x1400088bc  mov     rsi, rcx
0x1400088bf  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400088c6  xor     ebp, ebp
0x1400088c8  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400088cf  lea     r12, WPP_54c280395e213bf831c2a4b77063b8cf_Traceguids
0x1400088d6  jz      short loc_1400088FD
0x1400088d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400088df  cmp     [rcx+48h], bp
0x1400088e3  jz      short loc_1400088FD
0x1400088e5  mov     rcx, [rcx+40h]
0x1400088e9  lea     r9d, [rax+41h]
0x1400088ed  lea     r8d, [rax+1]
0x1400088f1  mov     [rsp+88h+var_68], r12
0x1400088f6  mov     dl, 5
0x1400088f8  call    WPP_RECORDER_SF_
0x1400088fd  mov     rax, cs:WdfFunctions_01015
0x140008904  mov     rdx, rsi
0x140008907  mov     rcx, cs:WdfDriverGlobals
0x14000890e  mov     rax, [rax+8D0h]
0x140008915  call    _guard_dispatch_icall
0x14000891a  mov     rcx, cs:WdfFunctions_01015
0x140008921  mov     rdx, rax
0x140008924  mov     r8, [rcx+4E8h]
0x14000892b  mov     rcx, cs:WdfDriverGlobals
0x140008932  mov     rax, r8
0x140008935  call    _guard_dispatch_icall
0x14000893a  mov     rcx, cs:WdfFunctions_01015
0x140008941  mov     rdx, rax
0x140008944  mov     r8, cs:off_1400150F0
0x14000894b  mov     rax, [rcx+650h]
0x140008952  mov     rcx, cs:WdfDriverGlobals
0x140008959  call    _guard_dispatch_icall
0x14000895e  mov     rcx, cs:WdfFunctions_01015
0x140008965  mov     rbx, rax
0x140008968  mov     r8, cs:off_140015040
0x14000896f  mov     rdx, rsi
0x140008972  mov     rax, [rcx+650h]
0x140008979  mov     rcx, cs:WdfDriverGlobals
0x140008980  call    _guard_dispatch_icall
0x140008985  movzx   ecx, byte ptr [rax+19h]
0x140008989  imul    rdx, rcx, 23h ; '#'
0x14000898d  movzx   ecx, byte ptr [rax+18h]
0x140008991  mov     rax, [rbx+88h]
0x140008998  add     rdx, rcx
0x14000899b  mov     rdi, [rax+rdx*8+18h]
0x1400089a0  mov     rdx, [rdi+68h]
0x1400089a4  mov     byte ptr [rdi+58h], 1
0x1400089a8  mov     rax, cs:WdfFunctions_01015
0x1400089af  mov     rcx, cs:WdfDriverGlobals
0x1400089b6  mov     rax, [rax+810h]
0x1400089bd  call    _guard_dispatch_icall
0x1400089c2  lea     rcx, aOnecoreDrivers_2; "onecore\\drivers\\wdm\\usb\\driver\\win"...
0x1400089c9  mov     ebx, 1
0x1400089ce  xchg    ebx, [rdi+5Ch]
0x1400089d1  mov     rax, cs:WdfFunctions_01015
0x1400089d8  mov     r9d, 7CCh
0x1400089de  mov     [rsp+88h+var_68], rcx
0x1400089e3  xor     r8d, r8d
0x1400089e6  mov     rcx, cs:WdfDriverGlobals
0x1400089ed  mov     rdx, rsi
0x1400089f0  mov     rax, [rax+670h]
0x1400089f7  call    _guard_dispatch_icall
0x1400089fc  cmp     ebx, 1
0x1400089ff  jnz     short loc_140008A5F
0x140008a01  mov     rax, cs:WdfFunctions_01015
0x140008a08  lea     r8, [rsp+88h+var_58]
0x140008a0d  mov     rcx, cs:WdfDriverGlobals
0x140008a14  mov     qword ptr [rsp+88h+var_58+0Ch], rbp
0x140008a19  mov     dword ptr [rsp+88h+var_48+4], ebp
0x140008a1d  mov     qword ptr [rsp+88h+var_58], 18h
0x140008a26  mov     dword ptr [rsp+88h+var_58+8], ebp
0x140008a2a  mov     rax, [rax+7C8h]
0x140008a31  mov     rdx, [rdi+68h]
0x140008a35  call    _guard_dispatch_icall
0x140008a3a  mov     r8d, [rdi+60h]
0x140008a3e  mov     rdx, rsi
0x140008a41  mov     [rdi+50h], rbp
0x140008a45  mov     rax, cs:WdfFunctions_01015
0x140008a4c  mov     rcx, cs:WdfDriverGlobals
0x140008a53  mov     rax, [rax+838h]
0x140008a5a  call    _guard_dispatch_icall
0x140008a5f  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140008a66  jz      short loc_140008A8F
0x140008a68  mov     rcx, cs:WPP_GLOBAL_Control
0x140008a6f  cmp     [rcx+48h], bp
0x140008a73  jz      short loc_140008A8F
0x140008a75  mov     rcx, [rcx+40h]
0x140008a79  mov     r9d, 42h ; 'B'
0x140008a7f  mov     dl, 5
0x140008a81  mov     [rsp+88h+var_68], r12
0x140008a86  lea     r8d, [r9-41h]
0x140008a8a  call    WPP_RECORDER_SF_
0x140008a8f  add     rsp, 58h
0x140008a93  pop     r15
0x140008a95  pop     r12
0x140008a97  pop     rdi
0x140008a98  pop     rsi
0x140008a99  pop     rbp
0x140008a9a  pop     rbx
0x140008a9b  retn
```
