# WinUSB_UpdateSqmInfo

- ea: `0x14001a464`
- end: `0x14001a621`
- name: `WinUSB_UpdateSqmInfo`
- size: `445`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x14000e19c`

## callees

- `0x140001020`
- `0x1400011c8`
- `0x140010700`
- `0x14001a464`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14001a546`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001a546`

## pseudocode

```c
__int64 __fastcall WinUSB_UpdateSqmInfo(__int64 a1)
{
  __int64 v2; // rax
  __int64 result; // rax
  int v4; // edx
  char v5; // bl
  int v6; // r9d
  int v7; // edx
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-28h] BYREF
  __int64 v9; // [rsp+78h] [rbp+10h] BYREF

  DestinationString = 0;
  v9 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      83,
      (__int64)WPP_26f1e60b7ed939401ac6450f7fef2921_Traceguids);
  v9 = 0;
  v2 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1632))(WdfDriverGlobals, a1);
  result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, __int64, _QWORD, __int64 *))(WdfFunctions_01015 + 384))(
             WdfDriverGlobals,
             v2,
             1,
             2031616,
             0,
             &v9);
  v5 = result;
  if ( (int)result < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_11;
    v6 = 84;
    goto LABEL_10;
  }
  RtlInitUnicodeString(&DestinationString, L"WinusbIsochUsed");
  result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, struct _UNICODE_STRING *, _QWORD))(WdfFunctions_01015 + 1968))(
             WdfDriverGlobals,
             v9,
             &DestinationString,
             *(unsigned int *)(a1 + 404));
  v5 = result;
  if ( (int)result < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v6 = 85;
LABEL_10:
    LOBYTE(v4) = 2;
    result = WPP_RECORDER_SF_d(
               WPP_GLOBAL_Control->DeviceExtension,
               v4,
               11,
               v6,
               (__int64)WPP_26f1e60b7ed939401ac6450f7fef2921_Traceguids,
               result);
  }
LABEL_11:
  v7 = v9;
  if ( v9 )
    result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01015 + 1848))(WdfDriverGlobals);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v7) = 5;
      return WPP_RECORDER_SF_d(
               WPP_GLOBAL_Control->DeviceExtension,
               v7,
               1,
               86,
               (__int64)WPP_26f1e60b7ed939401ac6450f7fef2921_Traceguids,
               v5);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14001a464  mov     rax, rsp
0x14001a467  mov     [rax+8], rbx
0x14001a46b  mov     [rax+18h], rbp
0x14001a46f  push    rsi
0x14001a470  push    rdi
0x14001a471  push    r14
0x14001a473  sub     rsp, 50h
0x14001a477  xorps   xmm0, xmm0
0x14001a47a  xor     esi, esi
0x14001a47c  movups  xmmword ptr [rax-28h], xmm0
0x14001a480  mov     [rax+10h], rsi
0x14001a484  mov     rdi, rcx
0x14001a487  lea     rbp, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001a48e  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14001a495  lea     r14, WPP_26f1e60b7ed939401ac6450f7fef2921_Traceguids
0x14001a49c  jz      short loc_14001A4C2
0x14001a49e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a4a5  cmp     [rcx+48h], si
0x14001a4a9  jz      short loc_14001A4C2
0x14001a4ab  mov     rcx, [rcx+40h]
0x14001a4af  lea     r9d, [rsi+53h]
0x14001a4b3  lea     r8d, [rsi+1]
0x14001a4b7  mov     [rax-48h], r14
0x14001a4bb  mov     dl, 5
0x14001a4bd  call    WPP_RECORDER_SF_
0x14001a4c2  mov     rax, cs:WdfFunctions_01015
0x14001a4c9  mov     rdx, rdi
0x14001a4cc  mov     rcx, cs:WdfDriverGlobals
0x14001a4d3  mov     [rsp+68h+arg_8], rsi
0x14001a4d8  mov     rax, [rax+660h]
0x14001a4df  call    _guard_dispatch_icall
0x14001a4e4  mov     rcx, cs:WdfFunctions_01015
0x14001a4eb  mov     rdx, rax
0x14001a4ee  mov     r9d, 1F0000h
0x14001a4f4  mov     r8d, 1
0x14001a4fa  mov     r10, [rcx+180h]
0x14001a501  lea     rcx, [rsp+68h+arg_8]
0x14001a506  mov     [rsp+68h+var_40], rcx
0x14001a50b  mov     rax, r10
0x14001a50e  mov     rcx, cs:WdfDriverGlobals
0x14001a515  mov     [rsp+68h+var_48], rsi
0x14001a51a  call    _guard_dispatch_icall
0x14001a51f  mov     ebx, eax
0x14001a521  test    eax, eax
0x14001a523  jns     short loc_14001A53A
0x14001a525  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14001a52c  jz      loc_14001A5B3
0x14001a532  mov     r9d, 54h ; 'T'
0x14001a538  jmp     short loc_14001A592
0x14001a53a  lea     rdx, aWinusbisochuse; "WinusbIsochUsed"
0x14001a541  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x14001a546  call    cs:__imp_RtlInitUnicodeString
0x14001a54d  nop     dword ptr [rax+rax+00h]
0x14001a552  mov     rax, cs:WdfFunctions_01015
0x14001a559  lea     r8, [rsp+68h+DestinationString]
0x14001a55e  mov     r9d, [rdi+194h]
0x14001a565  mov     rdx, [rsp+68h+arg_8]
0x14001a56a  mov     rcx, cs:WdfDriverGlobals
0x14001a571  mov     rax, [rax+7B0h]
0x14001a578  call    _guard_dispatch_icall
0x14001a57d  mov     ebx, eax
0x14001a57f  test    eax, eax
0x14001a581  jns     short loc_14001A5B3
0x14001a583  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14001a58a  jz      short loc_14001A5B3
0x14001a58c  mov     r9d, 55h ; 'U'
0x14001a592  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a599  mov     r8d, 0Bh
0x14001a59f  mov     dword ptr [rsp+68h+var_40], eax
0x14001a5a3  mov     dl, 2
0x14001a5a5  mov     [rsp+68h+var_48], r14
0x14001a5aa  mov     rcx, [rcx+40h]
0x14001a5ae  call    WPP_RECORDER_SF_d
0x14001a5b3  mov     rdx, [rsp+68h+arg_8]
0x14001a5b8  test    rdx, rdx
0x14001a5bb  jz      short loc_14001A5D7
0x14001a5bd  mov     rax, cs:WdfFunctions_01015
0x14001a5c4  mov     rcx, cs:WdfDriverGlobals
0x14001a5cb  mov     rax, [rax+738h]
0x14001a5d2  call    _guard_dispatch_icall
0x14001a5d7  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14001a5de  jz      short loc_14001A60B
0x14001a5e0  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a5e7  cmp     [rcx+48h], si
0x14001a5eb  jz      short loc_14001A60B
0x14001a5ed  mov     rcx, [rcx+40h]
0x14001a5f1  mov     r9d, 56h ; 'V'
0x14001a5f7  mov     dword ptr [rsp+68h+var_40], ebx
0x14001a5fb  mov     dl, 5
0x14001a5fd  mov     [rsp+68h+var_48], r14
0x14001a602  lea     r8d, [r9-55h]
0x14001a606  call    WPP_RECORDER_SF_d
0x14001a60b  lea     r11, [rsp+68h+var_18]
0x14001a610  mov     rbx, [r11+20h]
0x14001a614  mov     rbp, [r11+30h]
0x14001a618  mov     rsp, r11
0x14001a61b  pop     r14
0x14001a61d  pop     rdi
0x14001a61e  pop     rsi
0x14001a61f  retn
```
