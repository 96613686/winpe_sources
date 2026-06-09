# WaitForServiceState(SC_HANDLE__ *,ulong)

- ea: `0x18003ff7c`
- end: `0x1800400a8`
- name: `?WaitForServiceState@@YAJPEAUSC_HANDLE__@@K@Z`
- size: `300`
- prototype: `__int64 __fastcall(SC_HANDLE hService, DWORD dwControl)`
- caller_count: `3`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x18003dd70`
- `0x18003dfc0`
- `0x18003e494`

## callees

- `0x18003abe4`
- `0x18003ff7c`
- `0x18004d030`
- `0x18004d350`

## import_xrefs

- `KERNEL32!Sleep` at `0x180040044`
- `KERNEL32!Sleep` at `0x180040044`
- `ADVAPI32!ControlService` at `0x180040024`
- `ADVAPI32!ControlService` at `0x180040024`
- `ADVAPI32!QueryServiceStatus` at `0x180040052`
- `ADVAPI32!QueryServiceStatus` at `0x180040052`
- `ADVAPI32!StartServiceW` at `0x180040039`
- `ADVAPI32!StartServiceW` at `0x180040039`

## string_xrefs

- `0x18003ffc2`: `Waiting for service to shut down`
- `0x18003ffb9`: `Waiting for service to start`
- `0x18003ffce`: `WaitForServiceState`
- `0x180040069`: `WaitForServiceState`

## pseudocode

```c
__int64 __fastcall WaitForServiceState(SC_HANDLE hService, DWORD dwControl)
{
  unsigned int LastWin32Error; // ebx
  const char *v5; // rdi
  int v6; // r14d
  struct _SERVICE_STATUS ServiceStatus; // [rsp+30h] [rbp-48h] BYREF

  LastWin32Error = 0;
  if ( dwControl == 1 )
  {
    v5 = "Waiting for service to shut down";
  }
  else if ( dwControl == 4 )
  {
    v5 = "Waiting for service to start";
  }
  else
  {
    v5 = dword_1800738E4;
  }
  CSetupLogging::Log(1, "WaitForServiceState", 0, v5, 0);
  v6 = 60;
  while ( 1 )
  {
    if ( !QueryServiceStatus(hService, &ServiceStatus) )
    {
      LastWin32Error = GetLastWin32Error();
      goto LABEL_17;
    }
    if ( ServiceStatus.dwCurrentState == dwControl )
      goto LABEL_17;
    if ( !--v6 )
      break;
    if ( v6 == 5 * (v6 / 5) )
    {
      if ( dwControl == 1 )
      {
        ControlService(hService, 1u, &ServiceStatus);
      }
      else if ( dwControl == 4 )
      {
        StartServiceW(hService, 0, 0);
      }
    }
    Sleep(0x3E8u);
  }
  LastWin32Error = -2147023843;
LABEL_17:
  CSetupLogging::Log(LastWin32Error, "WaitForServiceState", 0, v5, 0);
  return LastWin32Error;
}

```

## disassembly

```asm
0x18003ff7c  mov     [rsp+arg_8], rbx
0x18003ff81  mov     [rsp+arg_10], rbp
0x18003ff86  push    rsi
0x18003ff87  push    rdi
0x18003ff88  push    r14
0x18003ff8a  sub     rsp, 60h
0x18003ff8e  mov     rax, cs:__security_cookie
0x18003ff95  xor     rax, rsp
0x18003ff98  mov     [rsp+78h+var_28], rax
0x18003ff9d  xor     ebx, ebx
0x18003ff9f  mov     eax, edx
0x18003ffa1  mov     esi, edx
0x18003ffa3  mov     rbp, rcx
0x18003ffa6  sub     eax, 1
0x18003ffa9  jz      short loc_18003FFC2
0x18003ffab  cmp     eax, 3
0x18003ffae  jz      short loc_18003FFB9
0x18003ffb0  lea     rdi, dword_1800738E4
0x18003ffb7  jmp     short loc_18003FFC9
0x18003ffb9  lea     rdi, aWaitingForServ; "Waiting for service to start"
0x18003ffc0  jmp     short loc_18003FFC9
0x18003ffc2  lea     rdi, aWaitingForServ_0; "Waiting for service to shut down"
0x18003ffc9  and     [rsp+78h+var_58], rbx
0x18003ffce  lea     rdx, aWaitforservice; "WaitForServiceState"
0x18003ffd5  xor     r8d, r8d; unsigned int
0x18003ffd8  mov     r9, rdi; char *
0x18003ffdb  lea     ecx, [r8+1]; int
0x18003ffdf  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003ffe4  mov     r14d, 3Ch ; '<'
0x18003ffea  jmp     short loc_18004004A
0x18003ffec  cmp     [rsp+78h+ServiceStatus.dwCurrentState], esi
0x18003fff0  jz      short loc_180040063
0x18003fff2  sub     r14d, 1
0x18003fff6  jz      loc_1800400A1
0x18003fffc  mov     eax, 66666667h
0x180040001  imul    r14d
0x180040004  sar     edx, 1
0x180040006  mov     eax, edx
0x180040008  shr     eax, 1Fh
0x18004000b  add     edx, eax
0x18004000d  lea     ecx, [rdx+rdx*4]
0x180040010  cmp     r14d, ecx
0x180040013  jnz     short loc_18004003F
0x180040015  cmp     esi, 1
0x180040018  jnz     short loc_18004002C
0x18004001a  lea     r8, [rsp+78h+ServiceStatus]; lpServiceStatus
0x18004001f  mov     edx, esi; dwControl
0x180040021  mov     rcx, rbp; hService
0x180040024  call    cs:__imp_ControlService
0x18004002a  jmp     short loc_18004003F
0x18004002c  cmp     esi, 4
0x18004002f  jnz     short loc_18004003F
0x180040031  xor     r8d, r8d; lpServiceArgVectors
0x180040034  xor     edx, edx; dwNumServiceArgs
0x180040036  mov     rcx, rbp; hService
0x180040039  call    cs:__imp_StartServiceW
0x18004003f  mov     ecx, 3E8h; dwMilliseconds
0x180040044  call    cs:__imp_Sleep
0x18004004a  lea     rdx, [rsp+78h+ServiceStatus]; lpServiceStatus
0x18004004f  mov     rcx, rbp; hService
0x180040052  call    cs:__imp_QueryServiceStatus
0x180040058  test    eax, eax
0x18004005a  jnz     short loc_18003FFEC
0x18004005c  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x180040061  mov     ebx, eax
0x180040063  and     [rsp+78h+var_58], 0
0x180040069  lea     rdx, aWaitforservice; "WaitForServiceState"
0x180040070  mov     r9, rdi; char *
0x180040073  xor     r8d, r8d; unsigned int
0x180040076  mov     ecx, ebx; int
0x180040078  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18004007d  mov     eax, ebx
0x18004007f  mov     rcx, [rsp+78h+var_28]
0x180040084  xor     rcx, rsp; StackCookie
0x180040087  call    __security_check_cookie
0x18004008c  lea     r11, [rsp+78h+var_18]
0x180040091  mov     rbx, [r11+28h]
0x180040095  mov     rbp, [r11+30h]
0x180040099  mov     rsp, r11
0x18004009c  pop     r14
0x18004009e  pop     rdi
0x18004009f  pop     rsi
0x1800400a0  retn
0x1800400a1  mov     ebx, 8007041Dh
0x1800400a6  jmp     short loc_180040063
```
