# CBthActiveConnector::_RefreshBatteryState(int *)

- ea: `0x180012058`
- end: `0x180012128`
- name: `?_RefreshBatteryState@CBthActiveConnector@@AEAAJPEAH@Z`
- size: `208`
- prototype: `__int64 __fastcall(CBthActiveConnector *__hidden this, int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180006360`
- `0x180011b04`

## callees

- `0x180007f28`
- `0x1800097d0`
- `0x180012058`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800120bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800120bf`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetSystemPowerStatus` at `0x180012093`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetSystemPowerStatus` at `0x180012093`

## pseudocode

```c
__int64 __fastcall CBthActiveConnector::_RefreshBatteryState(CBthActiveConnector *this, int *a2)
{
  unsigned int v4; // ebx
  __int32 v5; // ecx
  signed int LastError; // eax
  _SYSTEM_POWER_STATUS SystemPowerStatus; // [rsp+20h] [rbp-28h] BYREF

  *(_QWORD *)&SystemPowerStatus.ACLineStatus = 0;
  SystemPowerStatus.BatteryFullLifeTime = 0;
  if ( a2 )
    *a2 = 0;
  if ( GetSystemPowerStatus(&SystemPowerStatus) )
  {
    v4 = 0;
    v5 = (SystemPowerStatus.ACLineStatus & 0xFD) == 0;
    if ( v5 != _InterlockedExchange((volatile __int32 *)this + 2, v5) && a2 )
      *a2 = 1;
  }
  else
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( (v4 & 0x80000000) != 0
      && WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_0f88d5a9d8393f53423a785fee9a5214_Traceguids, v4);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180012058  mov     [rsp+arg_10], rbx
0x18001205d  mov     [rsp+arg_18], rsi
0x180012062  push    rdi
0x180012063  sub     rsp, 40h
0x180012067  mov     rax, cs:__security_cookie
0x18001206e  xor     rax, rsp
0x180012071  mov     [rsp+48h+var_18], rax
0x180012076  xor     eax, eax
0x180012078  mov     rdi, rdx
0x18001207b  mov     qword ptr [rsp+48h+SystemPowerStatus.ACLineStatus], rax
0x180012080  mov     rsi, rcx
0x180012083  mov     [rsp+48h+SystemPowerStatus.BatteryFullLifeTime], eax
0x180012087  test    rdx, rdx
0x18001208a  jz      short loc_18001208E
0x18001208c  mov     [rdx], eax
0x18001208e  lea     rcx, [rsp+48h+SystemPowerStatus]; lpSystemPowerStatus
0x180012093  call    cs:__imp_GetSystemPowerStatus
0x180012099  test    eax, eax
0x18001209b  jz      short loc_1800120BF
0x18001209d  xor     ebx, ebx
0x18001209f  test    [rsp+48h+SystemPowerStatus.ACLineStatus], 0FDh
0x1800120a4  mov     ecx, ebx
0x1800120a6  setz    cl
0x1800120a9  mov     eax, ecx
0x1800120ab  xchg    eax, [rsi+8]
0x1800120ae  cmp     ecx, eax
0x1800120b0  jz      short loc_180012109
0x1800120b2  test    rdi, rdi
0x1800120b5  jz      short loc_180012109
0x1800120b7  mov     dword ptr [rdi], 1
0x1800120bd  jmp     short loc_180012109
0x1800120bf  call    cs:__imp_GetLastError
0x1800120c5  mov     ebx, eax
0x1800120c7  test    eax, eax
0x1800120c9  jle     short loc_1800120D4
0x1800120cb  movzx   ebx, ax
0x1800120ce  or      ebx, 80070000h
0x1800120d4  test    ebx, ebx
0x1800120d6  jns     short loc_180012109
0x1800120d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800120df  lea     rax, WPP_GLOBAL_Control
0x1800120e6  cmp     rcx, rax
0x1800120e9  jz      short loc_180012109
0x1800120eb  test    byte ptr [rcx+1Ch], 2
0x1800120ef  jz      short loc_180012109
0x1800120f1  mov     rcx, [rcx+10h]
0x1800120f5  lea     r8, WPP_0f88d5a9d8393f53423a785fee9a5214_Traceguids
0x1800120fc  mov     edx, 33h ; '3'
0x180012101  mov     r9d, ebx
0x180012104  call    WPP_SF_d
0x180012109  mov     eax, ebx
0x18001210b  mov     rcx, [rsp+48h+var_18]
0x180012110  xor     rcx, rsp; StackCookie
0x180012113  call    __security_check_cookie
0x180012118  mov     rbx, [rsp+48h+arg_10]
0x18001211d  mov     rsi, [rsp+48h+arg_18]
0x180012122  add     rsp, 40h
0x180012126  pop     rdi
0x180012127  retn
```
