# HUBPARENT_ResetHubComplete

- ea: `0x140007b70`
- end: `0x140007c95`
- name: `HUBPARENT_ResetHubComplete`
- size: `293`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x140001f94`
- `0x1400024b8`
- `0x140007b70`
- `0x14000a53c`
- `0x1400110b0`
- `0x140045570`

## pseudocode

```c
__int64 __fastcall HUBPARENT_ResetHubComplete(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v5; // rax
  __int64 v6; // rax
  int v7; // edx
  __int64 v8; // rcx
  __int64 v9; // rdi
  int v10; // ebx
  int v11; // edx

  v5 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01015 + 1392))(WdfDriverGlobals);
  v6 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         v5,
         off_14006B270);
  v9 = v6;
  v10 = *(_DWORD *)(a3 + 8);
  if ( (byte_14006ED41 & 0x20) != 0 )
    McTemplateK0pq_EtwWriteTransfer(
      v8,
      (const EVENT_DESCRIPTOR *)USBHUB3_ETW_EVENT_HUB_RESET_REQUEST_COMPLETE,
      0,
      *(_QWORD *)(v6 + 248),
      v10);
  if ( v10 >= 0 )
  {
    if ( (*(_DWORD *)(v9 + 2424) & 1) != 0 )
      HUBMUX_PropogateDeviceProgrammingLostFlagsToAllDSMs(v9);
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v7) = 2;
    WPP_RECORDER_SF_d(*(_QWORD *)(v9 + 2536), v7, 3, 18, (__int64)WPP_7215ce29f44d3be25ae6d82bbfc5240b_Traceguids, v10);
  }
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1664))(WdfDriverGlobals, a1);
  if ( v10 < 0 )
  {
    v11 = 2070;
    if ( v10 == -1073741810 )
      v11 = 2074;
  }
  else
  {
    v11 = 2066;
  }
  return HUBSM_AddEvent(v9 + 1280, v11);
}

```

## disassembly

```asm
0x140007b70  mov     [rsp+arg_0], rbx
0x140007b75  mov     [rsp+arg_8], rsi
0x140007b7a  push    rdi
0x140007b7b  sub     rsp, 30h
0x140007b7f  mov     rax, cs:WdfFunctions_01015
0x140007b86  mov     rsi, rcx
0x140007b89  mov     rcx, cs:WdfDriverGlobals
0x140007b90  mov     rbx, r8
0x140007b93  mov     rax, [rax+570h]
0x140007b9a  call    _guard_dispatch_icall
0x140007b9f  mov     rdx, cs:WdfFunctions_01015
0x140007ba6  mov     r9, rax
0x140007ba9  mov     r8, cs:off_14006B270
0x140007bb0  mov     rcx, cs:WdfDriverGlobals
0x140007bb7  mov     rax, [rdx+650h]
0x140007bbe  mov     rdx, r9
0x140007bc1  call    _guard_dispatch_icall
0x140007bc6  test    cs:byte_14006ED41, 20h
0x140007bcd  mov     rdi, rax
0x140007bd0  mov     ebx, [rbx+8]
0x140007bd3  jz      short loc_140007BEF
0x140007bd5  mov     r9, [rax+0F8h]
0x140007bdc  lea     rdx, USBHUB3_ETW_EVENT_HUB_RESET_REQUEST_COMPLETE
0x140007be3  xor     r8d, r8d
0x140007be6  mov     dword ptr [rsp+38h+var_18], ebx
0x140007bea  call    McTemplateK0pq_EtwWriteTransfer
0x140007bef  test    ebx, ebx
0x140007bf1  jns     short loc_140007C2D
0x140007bf3  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140007bfa  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140007c01  jz      short loc_140007C3F
0x140007c03  mov     rcx, [rdi+9E8h]
0x140007c0a  lea     rax, WPP_7215ce29f44d3be25ae6d82bbfc5240b_Traceguids
0x140007c11  mov     r9d, 12h
0x140007c17  mov     [rsp+38h+var_10], ebx
0x140007c1b  mov     dl, 2
0x140007c1d  mov     [rsp+38h+var_18], rax
0x140007c22  lea     r8d, [r9-0Fh]
0x140007c26  call    WPP_RECORDER_SF_d
0x140007c2b  jmp     short loc_140007C3F
0x140007c2d  mov     eax, [rdi+978h]
0x140007c33  test    al, 1
0x140007c35  jz      short loc_140007C3F
0x140007c37  mov     rcx, rdi
0x140007c3a  call    HUBMUX_PropogateDeviceProgrammingLostFlagsToAllDSMs
0x140007c3f  mov     rax, cs:WdfFunctions_01015
0x140007c46  mov     rdx, rsi
0x140007c49  mov     rcx, cs:WdfDriverGlobals
0x140007c50  mov     rax, [rax+680h]
0x140007c57  call    _guard_dispatch_icall
0x140007c5c  test    ebx, ebx
0x140007c5e  js      short loc_140007C67
0x140007c60  mov     edx, 812h
0x140007c65  jmp     short loc_140007C78
0x140007c67  mov     edx, 816h
0x140007c6c  cmp     ebx, 0C000000Eh
0x140007c72  lea     eax, [rdx+4]
0x140007c75  cmovz   edx, eax
0x140007c78  lea     rcx, [rdi+500h]
0x140007c7f  call    HUBSM_AddEvent
0x140007c84  mov     rbx, [rsp+38h+arg_0]
0x140007c89  mov     rsi, [rsp+38h+arg_8]
0x140007c8e  add     rsp, 30h
0x140007c92  pop     rdi
0x140007c93  retn
```
