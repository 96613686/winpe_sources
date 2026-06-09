# DataCleanupManager::Initialize(int)

- ea: `0x18006a22c`
- end: `0x18006a3af`
- name: `?Initialize@DataCleanupManager@@QEAAJH@Z`
- size: `387`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task`

## callers

- `0x18002ee80`

## callees

- `0x180008f0c`
- `0x18006a22c`
- `0x18007e1a0`
- `0x18012c7b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006a248`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006a248`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006a38f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006a38f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a2d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a347`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a2d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a347`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18006a384`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18006a384`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18006a333`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18006a333`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18006a319`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18006a319`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetSystemPowerStatus` at `0x18006a2c7`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetSystemPowerStatus` at `0x18006a2c7`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x18006a28d`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x18006a28d`

## string_xrefs

- `0x18006a2a7`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datacleanup.cpp`
- `0x18006a2ed`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datacleanup.cpp`
- `0x18006a362`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datacleanup.cpp`

## pseudocode

```c
__int64 __fastcall DataCleanupManager::Initialize(LPCRITICAL_SECTION lpCriticalSection)
{
  signed int v2; // eax
  signed int LastError; // eax
  bool v4; // sf
  struct _TP_TIMER *ThreadpoolTimer; // rbx
  struct _TP_TIMER *v6; // rax
  signed int v7; // eax
  unsigned int v8; // ebx
  _QWORD Recipient[2]; // [rsp+30h] [rbp-38h] BYREF
  _SYSTEM_POWER_STATUS SystemPowerStatus; // [rsp+40h] [rbp-28h] BYREF

  EnterCriticalSection(lpCriticalSection);
  LODWORD(lpCriticalSection[1].DebugInfo) = 1;
  Recipient[0] = DataCleanupManager::_PowerStateChangeCallback;
  Recipient[1] = lpCriticalSection;
  tlx::auto_xxx<void *,unsigned long (*)(void *),&unsigned long PowerSettingUnregisterNotification(void *),0>::_Delete(&lpCriticalSection[1].OwningThread);
  lpCriticalSection[1].OwningThread = 0;
  v2 = PowerSettingRegisterNotification(&GUID_ACDC_POWER_SOURCE, 2u, Recipient, &lpCriticalSection[1].OwningThread);
  if ( v2 )
  {
    if ( v2 > 0 )
      v2 = (unsigned __int16)v2 | 0x80070000;
    Log_HREvent(
      (unsigned int)v2,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datacleanup.cpp",
      59);
  }
  *(_QWORD *)&SystemPowerStatus.ACLineStatus = 0;
  SystemPowerStatus.BatteryFullLifeTime = 0;
  if ( GetSystemPowerStatus(&SystemPowerStatus) )
  {
    LODWORD(lpCriticalSection[1].LockSemaphore) = SystemPowerStatus.ACLineStatus == 1;
  }
  else
  {
    LastError = GetLastError();
    v4 = LastError < 0;
    if ( LastError > 0 )
    {
      LastError = (unsigned __int16)LastError | 0x80070000;
      v4 = LastError < 0;
    }
    if ( v4 )
      Log_HREvent(
        (unsigned int)LastError,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datacleanup.cpp",
        64);
  }
  ThreadpoolTimer = CreateThreadpoolTimer(
                      (PTP_TIMER_CALLBACK)DataCleanupManager::_StaleDataCleanupTimerCallback,
                      lpCriticalSection,
                      0);
  v6 = *(struct _TP_TIMER **)&lpCriticalSection[1].LockCount;
  if ( ThreadpoolTimer == v6 )
  {
    ThreadpoolTimer = *(struct _TP_TIMER **)&lpCriticalSection[1].LockCount;
  }
  else
  {
    if ( v6 )
      CloseThreadpoolTimer(*(PTP_TIMER *)&lpCriticalSection[1].LockCount);
    *(_QWORD *)&lpCriticalSection[1].LockCount = ThreadpoolTimer;
  }
  if ( ThreadpoolTimer )
  {
    SetThreadpoolTimer(ThreadpoolTimer, &pftDueTime, 0, 0);
    v8 = 0;
  }
  else
  {
    v7 = GetLastError();
    v8 = v7;
    if ( v7 > 0 )
      v8 = (unsigned __int16)v7 | 0x80070000;
    Log_HREvent(
      v8,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datacleanup.cpp",
      74);
  }
  LeaveCriticalSection(lpCriticalSection);
  return v8;
}

```

## disassembly

```asm
0x18006a22c  mov     [rsp+arg_8], rbx
0x18006a231  push    rdi
0x18006a232  sub     rsp, 60h
0x18006a236  mov     rax, cs:__security_cookie
0x18006a23d  xor     rax, rsp
0x18006a240  mov     [rsp+68h+var_18], rax
0x18006a245  mov     rdi, rcx
0x18006a248  call    cs:__imp_EnterCriticalSection
0x18006a24e  lea     rax, ?_PowerStateChangeCallback@DataCleanupManager@@CAKPEAXK0@Z; DataCleanupManager::_PowerStateChangeCallback(void *,ulong,void *)
0x18006a255  mov     dword ptr [rdi+28h], 1
0x18006a25c  lea     rbx, [rdi+38h]
0x18006a260  mov     [rsp+68h+Recipient], rax
0x18006a265  mov     rcx, rbx
0x18006a268  mov     [rsp+68h+var_30], rdi
0x18006a26d  call    ?_Delete@?$auto_xxx@PEAXP6AKPEAX@Z$1?PowerSettingUnregisterNotification@@YAK0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,ulong (*)(void *),&PowerSettingUnregisterNotification(void *),0>::_Delete(void)
0x18006a272  mov     r9, rbx; RegistrationHandle
0x18006a275  mov     qword ptr [rbx], 0
0x18006a27c  lea     r8, [rsp+68h+Recipient]; Recipient
0x18006a281  mov     edx, 2; Flags
0x18006a286  lea     rcx, GUID_ACDC_POWER_SOURCE; SettingGuid
0x18006a28d  call    cs:__imp_PowerSettingRegisterNotification
0x18006a293  test    eax, eax
0x18006a295  jz      short loc_18006A2B7
0x18006a297  jle     short loc_18006A2A1
0x18006a299  movzx   eax, ax
0x18006a29c  or      eax, 80070000h
0x18006a2a1  mov     r9d, 3Bh ; ';'
0x18006a2a7  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18006a2ae  xor     edx, edx
0x18006a2b0  mov     ecx, eax
0x18006a2b2  call    Log_HREvent
0x18006a2b7  xor     eax, eax
0x18006a2b9  lea     rcx, [rsp+68h+SystemPowerStatus]; lpSystemPowerStatus
0x18006a2be  mov     qword ptr [rsp+68h+SystemPowerStatus.ACLineStatus], rax
0x18006a2c3  mov     [rsp+68h+SystemPowerStatus.BatteryFullLifeTime], eax
0x18006a2c7  call    cs:__imp_GetSystemPowerStatus
0x18006a2cd  test    eax, eax
0x18006a2cf  jnz     short loc_18006A2FF
0x18006a2d1  call    cs:__imp_GetLastError
0x18006a2d7  test    eax, eax
0x18006a2d9  jle     short loc_18006A2E5
0x18006a2db  movzx   eax, ax
0x18006a2de  or      eax, 80070000h
0x18006a2e3  test    eax, eax
0x18006a2e5  jns     short loc_18006A30C
0x18006a2e7  mov     r9d, 40h ; '@'
0x18006a2ed  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18006a2f4  xor     edx, edx
0x18006a2f6  mov     ecx, eax
0x18006a2f8  call    Log_HREvent
0x18006a2fd  jmp     short loc_18006A30C
0x18006a2ff  xor     eax, eax
0x18006a301  cmp     [rsp+68h+SystemPowerStatus.ACLineStatus], 1
0x18006a306  setz    al
0x18006a309  mov     [rdi+40h], eax
0x18006a30c  xor     r8d, r8d; pcbe
0x18006a30f  lea     rcx, ?_StaleDataCleanupTimerCallback@DataCleanupManager@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18006a316  mov     rdx, rdi; pv
0x18006a319  call    cs:__imp_CreateThreadpoolTimer
0x18006a31f  mov     rbx, rax
0x18006a322  mov     rax, [rdi+30h]
0x18006a326  cmp     rbx, rax
0x18006a329  jz      short loc_18006A33F
0x18006a32b  test    rax, rax
0x18006a32e  jz      short loc_18006A339
0x18006a330  mov     rcx, rax; pti
0x18006a333  call    cs:__imp_CloseThreadpoolTimer
0x18006a339  mov     [rdi+30h], rbx
0x18006a33d  jmp     short loc_18006A342
0x18006a33f  mov     rbx, rax
0x18006a342  test    rbx, rbx
0x18006a345  jnz     short loc_18006A374
0x18006a347  call    cs:__imp_GetLastError
0x18006a34d  mov     ebx, eax
0x18006a34f  test    eax, eax
0x18006a351  jle     short loc_18006A35C
0x18006a353  movzx   ebx, ax
0x18006a356  or      ebx, 80070000h
0x18006a35c  mov     r9d, 4Ah ; 'J'
0x18006a362  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18006a369  xor     edx, edx
0x18006a36b  mov     ecx, ebx
0x18006a36d  call    Log_HREvent
0x18006a372  jmp     short loc_18006A38C
0x18006a374  xor     r9d, r9d; msWindowLength
0x18006a377  lea     rdx, pftDueTime; pftDueTime
0x18006a37e  xor     r8d, r8d; msPeriod
0x18006a381  mov     rcx, rbx; pti
0x18006a384  call    cs:__imp_SetThreadpoolTimer
0x18006a38a  xor     ebx, ebx
0x18006a38c  mov     rcx, rdi; lpCriticalSection
0x18006a38f  call    cs:__imp_LeaveCriticalSection
0x18006a395  mov     eax, ebx
0x18006a397  mov     rcx, [rsp+68h+var_18]
0x18006a39c  xor     rcx, rsp; StackCookie
0x18006a39f  call    __security_check_cookie
0x18006a3a4  mov     rbx, [rsp+68h+arg_8]
0x18006a3a9  add     rsp, 60h
0x18006a3ad  pop     rdi
0x18006a3ae  retn
```
