# PnpServiceControlHandlerEx

- ea: `0x18000e890`
- end: `0x18000ea0d`
- name: `PnpServiceControlHandlerEx`
- size: `381`
- prototype: `__int64 __fastcall(DWORD dwControl, __int64 dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x18000de70`
- `0x18000e890`
- `0x18000f970`
- `0x1800136f8`
- `0x180014198`
- `0x180014248`
- `0x180018970`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000e99b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000e99b`

## pseudocode

```c
__int64 __fastcall PnpServiceControlHandlerEx(
        DWORD dwControl,
        __int64 dwEventType,
        LPVOID lpEventData,
        LPVOID lpContext)
{
  __int64 v4; // r9
  __int64 v5; // rcx
  unsigned int v6; // ebx
  void *v8; // rcx
  HANDLE v9; // rcx
  _BYTE v10[16]; // [rsp+30h] [rbp-28h] BYREF

  v4 = dwControl;
  _m_prefetchw(&PnpServiceControlFlags);
  v5 = PnpServiceControlFlags | 2u;
  if ( (_InterlockedOr(&PnpServiceControlFlags, 2u) & 1) != 0 )
  {
    v6 = 1115;
    goto LABEL_3;
  }
  v6 = 0;
  switch ( (_DWORD)v4 )
  {
    case 4:
      break;
    case 1:
      if ( (byte_180023989 & 2) != 0 )
        McGenEventWrite_EtwEventWriteTransfer(
          v5,
          (unsigned int)DEVICEINSTALL_STOP_CONTROL,
          (_DWORD)lpEventData,
          1,
          (__int64)v10);
      if ( !PnpServicePreshutdownRequired )
        goto LABEL_23;
      v6 = PnpServiceRegisterPreshutdownRestart(v5, dwEventType, lpEventData);
      if ( !v6 )
        goto LABEL_23;
      break;
    case 6:
      v9 = PnpServiceParamChangeEvent;
      if ( PnpServiceParamChangeEvent )
        SetEvent(PnpServiceParamChangeEvent);
      PnPServiceStatusUpdate(v9, (unsigned int)PnpServiceCurrentState, 0, 0);
      break;
    case 0xF:
      if ( (byte_180023989 & 2) != 0 )
        McGenEventWrite_EtwEventWriteTransfer(
          v5,
          (unsigned int)DEVICEINSTALL_STOP_SHUTDOWN,
          (_DWORD)lpEventData,
          1,
          (__int64)v10);
      PnpServicePreshutdown = 1;
LABEL_23:
      PnPServiceStatusUpdate(v5, 3, 0, 0);
      PnpServiceSignalStop();
      break;
    default:
      if ( (_DWORD)v4 != 32 )
      {
        v6 = 1052;
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_0e80b14c55a13f72cdcecc79ffb17787_Traceguids, v4, 1052);
        PnPServiceStatusUpdate(v8, (unsigned int)PnpServiceCurrentState, 0, 1052);
      }
      break;
  }
LABEL_3:
  _InterlockedAnd(&PnpServiceControlFlags, 0xFFFFFFFD);
  return v6;
}

```

## disassembly

```asm
0x18000e890  push    rbx
0x18000e892  sub     rsp, 50h
0x18000e896  mov     rax, cs:__security_cookie
0x18000e89d  xor     rax, rsp
0x18000e8a0  mov     [rsp+58h+var_18], rax
0x18000e8a5  mov     r9d, ecx
0x18000e8a8  prefetchw byte ptr cs:PnpServiceControlFlags
0x18000e8af  mov     eax, cs:PnpServiceControlFlags
0x18000e8b5  mov     ecx, eax
0x18000e8b7  or      ecx, 2
0x18000e8ba  lock cmpxchg cs:PnpServiceControlFlags, ecx
0x18000e8c2  jnz     short loc_18000E8B5
0x18000e8c4  test    al, 1
0x18000e8c6  jz      short loc_18000E8EA
0x18000e8c8  mov     ebx, 45Bh
0x18000e8cd  lock and cs:PnpServiceControlFlags, 0FFFFFFFDh
0x18000e8d5  mov     eax, ebx
0x18000e8d7  mov     rcx, [rsp+58h+var_18]
0x18000e8dc  xor     rcx, rsp; StackCookie
0x18000e8df  call    __security_check_cookie
0x18000e8e4  add     rsp, 50h
0x18000e8e8  pop     rbx
0x18000e8e9  retn
0x18000e8ea  xor     ebx, ebx
0x18000e8ec  cmp     r9d, 4
0x18000e8f0  jz      short loc_18000E8CD
0x18000e8f2  mov     eax, r9d
0x18000e8f5  sub     eax, 1
0x18000e8f8  jz      loc_18000E9B7
0x18000e8fe  sub     eax, 5
0x18000e901  jz      loc_18000E98F
0x18000e907  sub     eax, 9
0x18000e90a  jz      short loc_18000E95E
0x18000e90c  cmp     eax, 11h
0x18000e90f  jz      short loc_18000E8CD
0x18000e911  mov     ebx, 41Ch
0x18000e916  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e91d  lea     rax, WPP_GLOBAL_Control
0x18000e924  cmp     rcx, rax
0x18000e927  jz      short loc_18000E948
0x18000e929  test    byte ptr [rcx+1Ch], 1
0x18000e92d  jz      short loc_18000E948
0x18000e92f  mov     rcx, [rcx+10h]
0x18000e933  lea     r8, WPP_0e80b14c55a13f72cdcecc79ffb17787_Traceguids
0x18000e93a  mov     edx, 17h
0x18000e93f  mov     dword ptr [rsp+58h+var_38], ebx
0x18000e943  call    WPP_SF_dd
0x18000e948  mov     edx, cs:PnpServiceCurrentState
0x18000e94e  mov     r9d, ebx
0x18000e951  xor     r8d, r8d
0x18000e954  call    PnPServiceStatusUpdate
0x18000e959  jmp     loc_18000E8CD
0x18000e95e  test    cs:byte_180023989, 2
0x18000e965  jz      short loc_18000E983
0x18000e967  lea     rax, [rsp+58h+var_28]
0x18000e96c  mov     r9d, 1
0x18000e972  lea     rdx, DEVICEINSTALL_STOP_SHUTDOWN
0x18000e979  mov     [rsp+58h+var_38], rax
0x18000e97e  call    McGenEventWrite_EtwEventWriteTransfer
0x18000e983  mov     cs:PnpServicePreshutdown, 1
0x18000e98d  jmp     short loc_18000E9F3
0x18000e98f  mov     rcx, cs:PnpServiceParamChangeEvent; hEvent
0x18000e996  test    rcx, rcx
0x18000e999  jz      short loc_18000E9A1
0x18000e99b  call    cs:__imp_SetEvent
0x18000e9a1  mov     edx, cs:PnpServiceCurrentState
0x18000e9a7  xor     r9d, r9d
0x18000e9aa  xor     r8d, r8d
0x18000e9ad  call    PnPServiceStatusUpdate
0x18000e9b2  jmp     loc_18000E8CD
0x18000e9b7  test    cs:byte_180023989, 2
0x18000e9be  jz      short loc_18000E9DC
0x18000e9c0  lea     rax, [rsp+58h+var_28]
0x18000e9c5  mov     r9d, 1
0x18000e9cb  lea     rdx, DEVICEINSTALL_STOP_CONTROL
0x18000e9d2  mov     [rsp+58h+var_38], rax
0x18000e9d7  call    McGenEventWrite_EtwEventWriteTransfer
0x18000e9dc  cmp     cs:PnpServicePreshutdownRequired, ebx
0x18000e9e2  jz      short loc_18000E9F3
0x18000e9e4  call    PnpServiceRegisterPreshutdownRestart
0x18000e9e9  mov     ebx, eax
0x18000e9eb  test    eax, eax
0x18000e9ed  jnz     loc_18000E8CD
0x18000e9f3  xor     r9d, r9d
0x18000e9f6  xor     r8d, r8d
0x18000e9f9  mov     edx, 3
0x18000e9fe  call    PnPServiceStatusUpdate
0x18000ea03  call    PnpServiceSignalStop
0x18000ea08  jmp     loc_18000E8CD
```
