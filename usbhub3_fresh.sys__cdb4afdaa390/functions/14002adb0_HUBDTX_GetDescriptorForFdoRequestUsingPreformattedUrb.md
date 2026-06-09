# HUBDTX_GetDescriptorForFdoRequestUsingPreformattedUrb

- ea: `0x14002adb0`
- end: `0x14002aeee`
- name: `HUBDTX_GetDescriptorForFdoRequestUsingPreformattedUrb`
- size: `318`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140022ee0`

## callees

- `0x1400067ac`
- `0x14000a53c`
- `0x14000ca70`
- `0x14002adb0`
- `0x140045570`

## pseudocode

```c
__int64 __fastcall HUBDTX_GetDescriptorForFdoRequestUsingPreformattedUrb(__int64 *a1)
{
  __int64 result; // rax
  int v3; // edx
  __int64 v4; // rax

  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 (__fastcall *)(__int64, __int64, __int64, __int64 *), __int64 *))(WdfFunctions_01015 + 2080))(
    WdfDriverGlobals,
    a1[63],
    HUBDTX_GetDeviceDescriptorComplete,
    a1);
  result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, _QWORD))(WdfFunctions_01015 + 2024))(
             WdfDriverGlobals,
             a1[63],
             *(_QWORD *)(*a1 + 32),
             0);
  if ( !(_BYTE)result )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v3) = 2;
      WPP_RECORDER_SF_(*(_QWORD *)(a1[1] + 1432), v3, 5, 112, (__int64)WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids);
    }
    HUBSM_AddEvent((__int64)(a1 + 64), 4004);
    HUBFDO_CompleteGetDescriptorRequest(*a1, *(unsigned __int16 *)(a1[1] + 200), a1[63], -1073741823, 0);
    v4 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64 *))(WdfFunctions_01015 + 1632))(WdfDriverGlobals, a1);
    return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, const char *, __int64, const char *))(WdfFunctions_01015 + 1648))(
             WdfDriverGlobals,
             v4,
             "User Mode FDO Request",
             6371,
             "onecore\\drivers\\wdm\\usb\\usb3\\hub\\src\\devicexfer.c");
  }
  return result;
}

```

## disassembly

```asm
0x14002adb0  mov     [rsp+arg_0], rbx
0x14002adb5  push    rdi
0x14002adb6  sub     rsp, 30h
0x14002adba  mov     rax, cs:WdfFunctions_01015
0x14002adc1  lea     r8, HUBDTX_GetDeviceDescriptorComplete
0x14002adc8  mov     rdx, [rcx+1F8h]
0x14002adcf  mov     rdi, rcx
0x14002add2  mov     r9, rcx
0x14002add5  mov     rcx, cs:WdfDriverGlobals
0x14002addc  mov     rax, [rax+820h]
0x14002ade3  call    _guard_dispatch_icall
0x14002ade8  mov     r8, [rdi]
0x14002adeb  xor     r9d, r9d
0x14002adee  mov     rax, cs:WdfFunctions_01015
0x14002adf5  mov     rdx, [rdi+1F8h]
0x14002adfc  mov     rcx, cs:WdfDriverGlobals
0x14002ae03  mov     r8, [r8+20h]
0x14002ae07  mov     rax, [rax+7E8h]
0x14002ae0e  call    _guard_dispatch_icall
0x14002ae13  test    al, al
0x14002ae15  jnz     loc_14002AEE2
0x14002ae1b  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002ae22  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002ae29  jz      short loc_14002AE53
0x14002ae2b  mov     rcx, [rdi+8]
0x14002ae2f  lea     rax, WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids
0x14002ae36  mov     r9d, 70h ; 'p'
0x14002ae3c  mov     [rsp+38h+var_18], rax
0x14002ae41  mov     dl, 2
0x14002ae43  mov     rcx, [rcx+598h]
0x14002ae4a  lea     r8d, [r9-6Bh]
0x14002ae4e  call    WPP_RECORDER_SF_
0x14002ae53  lea     rcx, [rdi+200h]
0x14002ae5a  mov     edx, 0FA4h
0x14002ae5f  call    HUBSM_AddEvent
0x14002ae64  mov     rax, [rdi+8]
0x14002ae68  mov     r9d, 0C0000001h
0x14002ae6e  mov     r8, [rdi+1F8h]
0x14002ae75  mov     rcx, [rdi]
0x14002ae78  mov     dword ptr [rsp+38h+var_18], 0
0x14002ae80  movzx   edx, word ptr [rax+0C8h]
0x14002ae87  call    HUBFDO_CompleteGetDescriptorRequest
0x14002ae8c  mov     rax, cs:WdfFunctions_01015
0x14002ae93  mov     rdx, rdi
0x14002ae96  mov     rcx, cs:WdfDriverGlobals
0x14002ae9d  mov     rax, [rax+660h]
0x14002aea4  call    _guard_dispatch_icall
0x14002aea9  mov     rcx, cs:WdfFunctions_01015
0x14002aeb0  lea     r8, UserModeFdoRequest; "User Mode FDO Request"
0x14002aeb7  mov     rdx, rax
0x14002aeba  mov     r9d, 18E3h
0x14002aec0  mov     r10, [rcx+670h]
0x14002aec7  lea     rcx, aOnecoreDrivers_6; "onecore\\drivers\\wdm\\usb\\usb3\\hub\\"...
0x14002aece  mov     [rsp+38h+var_18], rcx
0x14002aed3  mov     rax, r10
0x14002aed6  mov     rcx, cs:WdfDriverGlobals
0x14002aedd  call    _guard_dispatch_icall
0x14002aee2  mov     rbx, [rsp+38h+arg_0]
0x14002aee7  add     rsp, 30h
0x14002aeeb  pop     rdi
0x14002aeec  retn
```
