# OsEventsThread

- ea: `0x18005ef80`
- end: `0x18005f20a`
- name: `OsEventsThread`
- size: `650`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18005e6cc`
- `0x18005e984`
- `0x18005eac4`
- `0x18005eda4`
- `0x18005ef80`
- `0x18005f210`
- `0x18005f298`
- `0x18008cca0`
- `0x180092008`
- `0x180092ee4`
- `0x18009aee0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005f0bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005f0bb`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18005f0fd`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18005f197`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18005f0fd`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18005f197`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005effd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005effd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005efa5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005efa5`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18005f07a`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18005f07a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005f0c4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005f0c4`

## string_xrefs

- `0x18005efec`: `System\CurrentControlSet\Control\ComputerName\ActiveComputerName`

## pseudocode

```c
__int64 __fastcall OsEventsThread(PVOID Parameter)
{
  char *EventW; // rbx
  char v3; // di
  DWORD v4; // eax
  __int64 v5; // rcx
  DWORD v6; // eax
  DWORD v7; // eax
  DWORD v8; // eax
  DWORD v9; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  HKEY hKey; // [rsp+30h] [rbp-48h] BYREF
  HANDLE Handles[6]; // [rsp+38h] [rbp-40h] BYREF

  EventW = (char *)CreateEventW(0, 0, 0, 0);
  if ( EventW == (char *)-1LL || EventW + 1 == (char *)1 )
    return 8;
  hKey = 0;
  v3 = 0;
  RegOpenKeyExW(
    HKEY_LOCAL_MACHINE,
    L"System\\CurrentControlSet\\Control\\ComputerName\\ActiveComputerName",
    0,
    0x20019u,
    &hKey);
  if ( hKey )
  {
    v10 = RegNotifyChangeKeyValue(hKey, 1, 4u, EventW, 1);
    if ( v10 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_2c2d62d8dcc43732bdae633c77dd2d8d_Traceguids, v10);
      }
    }
  }
  OsEventsSetNoonTimer();
  OsEventsAdjustTimestampPolicy();
  do
  {
    Handles[0] = qword_180111548;
    Handles[1] = hObject;
    Handles[2] = qword_180111550;
    Handles[3] = hTimer;
    Handles[5] = qword_180111560;
    Handles[4] = EventW;
    OsEventsManagePowerCallbacks(0);
    v4 = WaitForMultipleObjectsEx(6u, Handles, 0, 0xFFFFFFFF, 0);
    if ( v4 )
    {
      v6 = v4 - 1;
      if ( v6 )
      {
        v7 = v6 - 1;
        if ( !v7 )
        {
          LOBYTE(v5) = dword_18011193C != 0;
          OsEventsWriteTimestamp(v5);
          continue;
        }
        v8 = v7 - 1;
        if ( !v8 )
        {
          OsEventsPublish6013();
          DueTime.QuadPart = 0;
LABEL_33:
          OsEventsSetNoonTimer();
          continue;
        }
        v9 = v8 - 1;
        if ( v9 )
        {
          if ( v9 != 1 )
            continue;
          goto LABEL_33;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_2c2d62d8dcc43732bdae633c77dd2d8d_Traceguids);
        }
        v11 = RegNotifyChangeKeyValue(hKey, 1, 4u, EventW, 1);
        if ( v11
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_2c2d62d8dcc43732bdae633c77dd2d8d_Traceguids, v11);
        }
        OsEventsPublish6011();
      }
      else
      {
        OsEventsAdjustTimestampPolicy();
      }
    }
    else
    {
      v3 = 1;
    }
  }
  while ( !v3 );
  OsEventsCleanShutdown();
  if ( hKey )
    RegCloseKey(hKey);
  CloseHandle(EventW);
  return 0;
}

```

## disassembly

```asm
0x18005ef80  push    rbp
0x18005ef82  push    rbx
0x18005ef83  push    rdi
0x18005ef84  push    r12
0x18005ef86  mov     rbp, rsp
0x18005ef89  sub     rsp, 78h
0x18005ef8d  mov     rax, cs:__security_cookie
0x18005ef94  xor     rax, rsp
0x18005ef97  mov     [rbp+var_10], rax
0x18005ef9b  xor     r9d, r9d; lpName
0x18005ef9e  xor     r8d, r8d; bInitialState
0x18005efa1  xor     edx, edx; bManualReset
0x18005efa3  xor     ecx, ecx; lpEventAttributes
0x18005efa5  call    cs:__imp_CreateEventW
0x18005efab  mov     rbx, rax
0x18005efae  inc     rax
0x18005efb1  cmp     rax, 1
0x18005efb5  ja      short loc_18005EFD2
0x18005efb7  mov     eax, 8
0x18005efbc  mov     rcx, [rbp+var_10]
0x18005efc0  xor     rcx, rsp; StackCookie
0x18005efc3  call    __security_check_cookie
0x18005efc8  add     rsp, 78h
0x18005efcc  pop     r12
0x18005efce  pop     rdi
0x18005efcf  pop     rbx
0x18005efd0  pop     rbp
0x18005efd1  retn
0x18005efd2  lea     rax, [rbp+hKey]
0x18005efd6  mov     [rbp+hKey], 0
0x18005efde  mov     r9d, 20019h; samDesired
0x18005efe4  mov     [rsp+78h+phkResult], rax; phkResult
0x18005efe9  xor     r8d, r8d; ulOptions
0x18005efec  lea     rdx, aSystemCurrentc_3; "System\\CurrentControlSet\\Control\\Com"...
0x18005eff3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005effa  xor     dil, dil
0x18005effd  call    cs:__imp_RegOpenKeyExW
0x18005f003  mov     rcx, [rbp+hKey]; hKey
0x18005f007  lea     r12, WPP_GLOBAL_Control
0x18005f00e  test    rcx, rcx
0x18005f011  jnz     loc_18005F0E9
0x18005f017  call    OsEventsSetNoonTimer
0x18005f01c  call    OsEventsAdjustTimestampPolicy
0x18005f021  mov     rax, cs:qword_180111548
0x18005f028  xor     ecx, ecx
0x18005f02a  mov     [rbp+Handles], rax
0x18005f02e  mov     rax, cs:hObject
0x18005f035  mov     [rbp+var_38], rax
0x18005f039  mov     rax, cs:qword_180111550
0x18005f040  mov     [rbp+var_30], rax
0x18005f044  mov     rax, cs:hTimer
0x18005f04b  mov     [rbp+var_28], rax
0x18005f04f  mov     rax, cs:qword_180111560
0x18005f056  mov     [rbp+var_18], rax
0x18005f05a  mov     [rbp+var_20], rbx
0x18005f05e  call    OsEventsManagePowerCallbacks
0x18005f063  xor     r8d, r8d; bWaitAll
0x18005f066  mov     dword ptr [rsp+78h+phkResult], 0; bAlertable
0x18005f06e  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18005f072  lea     rdx, [rbp+Handles]; lpHandles
0x18005f076  lea     ecx, [r8+6]; nCount
0x18005f07a  call    cs:__imp_WaitForMultipleObjectsEx
0x18005f080  test    eax, eax
0x18005f082  jz      loc_18005F202
0x18005f088  sub     eax, 1
0x18005f08b  jz      loc_18005F1F8
0x18005f091  sub     eax, 1
0x18005f094  jnz     short loc_18005F0D1
0x18005f096  cmp     cs:dword_18011193C, eax
0x18005f09c  setnz   cl
0x18005f09f  call    OsEventsWriteTimestamp
0x18005f0a4  test    dil, dil
0x18005f0a7  jz      loc_18005F021
0x18005f0ad  call    OsEventsCleanShutdown
0x18005f0b2  mov     rcx, [rbp+hKey]; hKey
0x18005f0b6  test    rcx, rcx
0x18005f0b9  jz      short loc_18005F0C1
0x18005f0bb  call    cs:__imp_RegCloseKey
0x18005f0c1  mov     rcx, rbx; hObject
0x18005f0c4  call    cs:__imp_CloseHandle
0x18005f0ca  xor     eax, eax
0x18005f0cc  jmp     loc_18005EFBC
0x18005f0d1  sub     eax, 1
0x18005f0d4  jz      loc_18005F1DE
0x18005f0da  sub     eax, 1
0x18005f0dd  jz      short loc_18005F14F
0x18005f0df  cmp     eax, 1
0x18005f0e2  jnz     short loc_18005F0A4
0x18005f0e4  jmp     loc_18005F1EE
0x18005f0e9  mov     edx, 1; bWatchSubtree
0x18005f0ee  mov     dword ptr [rsp+78h+phkResult], 1; fAsynchronous
0x18005f0f6  mov     r9, rbx; hEvent
0x18005f0f9  lea     r8d, [rdx+3]; dwNotifyFilter
0x18005f0fd  call    cs:__imp_RegNotifyChangeKeyValue
0x18005f103  test    eax, eax
0x18005f105  jz      loc_18005F017
0x18005f10b  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f112  cmp     rcx, r12
0x18005f115  jz      loc_18005F017
0x18005f11b  test    dword ptr [rcx+1Ch], 4000h
0x18005f122  jz      loc_18005F017
0x18005f128  cmp     byte ptr [rcx+19h], 2
0x18005f12c  jb      loc_18005F017
0x18005f132  mov     rcx, [rcx+10h]
0x18005f136  lea     r8, WPP_2c2d62d8dcc43732bdae633c77dd2d8d_Traceguids
0x18005f13d  mov     edx, 30h ; '0'
0x18005f142  mov     r9d, eax
0x18005f145  call    WPP_SF_d
0x18005f14a  jmp     loc_18005F017
0x18005f14f  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f156  cmp     rcx, r12
0x18005f159  jz      short loc_18005F17F
0x18005f15b  test    dword ptr [rcx+1Ch], 4000h
0x18005f162  jz      short loc_18005F17F
0x18005f164  cmp     byte ptr [rcx+19h], 4
0x18005f168  jb      short loc_18005F17F
0x18005f16a  mov     rcx, [rcx+10h]
0x18005f16e  lea     r8, WPP_2c2d62d8dcc43732bdae633c77dd2d8d_Traceguids
0x18005f175  mov     edx, 31h ; '1'
0x18005f17a  call    WPP_SF_
0x18005f17f  mov     rcx, [rbp+hKey]; hKey
0x18005f183  mov     edx, 1; bWatchSubtree
0x18005f188  mov     r9, rbx; hEvent
0x18005f18b  mov     dword ptr [rsp+78h+phkResult], 1; fAsynchronous
0x18005f193  lea     r8d, [rdx+3]; dwNotifyFilter
0x18005f197  call    cs:__imp_RegNotifyChangeKeyValue
0x18005f19d  test    eax, eax
0x18005f19f  jz      short loc_18005F1D4
0x18005f1a1  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f1a8  cmp     rcx, r12
0x18005f1ab  jz      short loc_18005F1D4
0x18005f1ad  test    dword ptr [rcx+1Ch], 4000h
0x18005f1b4  jz      short loc_18005F1D4
0x18005f1b6  cmp     byte ptr [rcx+19h], 2
0x18005f1ba  jb      short loc_18005F1D4
0x18005f1bc  mov     rcx, [rcx+10h]
0x18005f1c0  lea     r8, WPP_2c2d62d8dcc43732bdae633c77dd2d8d_Traceguids
0x18005f1c7  mov     edx, 32h ; '2'
0x18005f1cc  mov     r9d, eax
0x18005f1cf  call    WPP_SF_d
0x18005f1d4  call    OsEventsPublish6011
0x18005f1d9  jmp     loc_18005F0A4
0x18005f1de  call    OsEventsPublish6013
0x18005f1e3  mov     qword ptr cs:DueTime, 0
0x18005f1ee  call    OsEventsSetNoonTimer
0x18005f1f3  jmp     loc_18005F0A4
0x18005f1f8  call    OsEventsAdjustTimestampPolicy
0x18005f1fd  jmp     loc_18005F0A4
0x18005f202  mov     dil, 1
0x18005f205  jmp     loc_18005F0A4
```
