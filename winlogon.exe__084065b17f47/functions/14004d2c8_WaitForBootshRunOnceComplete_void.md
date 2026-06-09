# WaitForBootshRunOnceComplete(void)

- ea: `0x14004d2c8`
- end: `0x14004d497`
- name: `?WaitForBootshRunOnceComplete@@YAXXZ`
- size: `463`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140016284`

## callees

- `0x1400057f4`
- `0x140041c34`
- `0x14004d2c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14004d38f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14004d38f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14004d3cb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14004d3cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004d47f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004d47f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14004d308`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14004d339`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14004d308`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14004d339`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14004d377`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14004d405`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14004d377`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14004d405`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x14004d3b5`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x14004d3b5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004d31a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004d489`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004d31a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004d489`

## string_xrefs

- `0x14004d2fb`: `SYSTEM\CurrentControlSet\Services\Bootsh\Parameters\RunOnce`
- `0x14004d32f`: `SYSTEM\CurrentControlSet\Services\Bootsh\Parameters`

## pseudocode

```c
void WaitForBootshRunOnceComplete(void)
{
  HANDLE EventW; // rbx
  DWORD v1; // eax
  __int64 v2; // r9
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+20h] BYREF
  int Data; // [rsp+68h] [rbp+28h] BYREF
  DWORD Type; // [rsp+70h] [rbp+30h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp+38h] BYREF

  hKey = 0;
  phkResult = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Services\\Bootsh\\Parameters\\RunOnce",
          0,
          0x20019u,
          &hKey) )
  {
    RegCloseKey(hKey);
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"SYSTEM\\CurrentControlSet\\Services\\Bootsh\\Parameters",
            0,
            0x20019u,
            &phkResult) )
    {
      Data = 0;
      Type = 4;
      cbData = 4;
      if ( RegQueryValueExW(phkResult, L"RunOnce.Done", 0, &Type, (LPBYTE)&Data, &cbData) )
      {
        EventW = CreateEventW(0, 0, 0, 0);
        if ( EventW )
        {
          while ( !RegNotifyChangeKeyValue(phkResult, 0, 4u, EventW, 1) )
          {
            v1 = WaitForSingleObject(EventW, 0x4E20u);
            if ( v1 )
            {
              if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids, v1);
              }
              break;
            }
            Data = 0;
            Type = 4;
            cbData = 4;
            if ( !RegQueryValueExW(phkResult, L"RunOnce.Done", 0, &Type, (LPBYTE)&Data, &cbData) )
            {
              if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids, v2);
              }
              break;
            }
          }
          CloseHandle(EventW);
        }
      }
      RegCloseKey(phkResult);
    }
  }
}

```

## disassembly

```asm
0x14004d2c8  push    rbp
0x14004d2ca  push    rbx
0x14004d2cb  push    rsi
0x14004d2cc  mov     rbp, rsp
0x14004d2cf  sub     rsp, 40h
0x14004d2d3  lea     rax, [rbp+hKey]
0x14004d2d7  mov     [rbp+hKey], 0
0x14004d2df  mov     ebx, 20019h
0x14004d2e4  mov     [rbp+arg_18], 0
0x14004d2ec  mov     rsi, 0FFFFFFFF80000002h
0x14004d2f3  mov     [rsp+40h+phkResult], rax; phkResult
0x14004d2f8  mov     r9d, ebx; samDesired
0x14004d2fb  lea     rdx, aSystemCurrentc_15; "SYSTEM\\CurrentControlSet\\Services\\Bo"...
0x14004d302  mov     rcx, rsi; hKey
0x14004d305  xor     r8d, r8d; ulOptions
0x14004d308  call    cs:__imp_RegOpenKeyExW
0x14004d30e  test    eax, eax
0x14004d310  jnz     loc_14004D48F
0x14004d316  mov     rcx, [rbp+hKey]; hKey
0x14004d31a  call    cs:__imp_RegCloseKey
0x14004d320  lea     rax, [rbp+arg_18]
0x14004d324  mov     r9d, ebx; samDesired
0x14004d327  xor     r8d, r8d; ulOptions
0x14004d32a  mov     [rsp+40h+phkResult], rax; phkResult
0x14004d32f  lea     rdx, aSystemCurrentc_11; "SYSTEM\\CurrentControlSet\\Services\\Bo"...
0x14004d336  mov     rcx, rsi; hKey
0x14004d339  call    cs:__imp_RegOpenKeyExW
0x14004d33f  test    eax, eax
0x14004d341  jnz     loc_14004D48F
0x14004d347  mov     rcx, [rbp+arg_18]; hKey
0x14004d34b  lea     esi, [rax+4]
0x14004d34e  mov     [rbp+Data], eax
0x14004d351  lea     r9, [rbp+Type]; lpType
0x14004d355  lea     rax, [rbp+cbData]
0x14004d359  mov     [rbp+Type], esi
0x14004d35c  mov     [rsp+40h+lpcbData], rax; lpcbData
0x14004d361  lea     rdx, aRunonceDone; "RunOnce.Done"
0x14004d368  lea     rax, [rbp+Data]
0x14004d36c  mov     [rbp+cbData], esi
0x14004d36f  xor     r8d, r8d; lpReserved
0x14004d372  mov     [rsp+40h+phkResult], rax; lpData
0x14004d377  call    cs:__imp_RegQueryValueExW
0x14004d37d  test    eax, eax
0x14004d37f  jz      loc_14004D485
0x14004d385  xor     r9d, r9d; lpName
0x14004d388  xor     r8d, r8d; bInitialState
0x14004d38b  xor     edx, edx; bManualReset
0x14004d38d  xor     ecx, ecx; lpEventAttributes
0x14004d38f  call    cs:__imp_CreateEventW
0x14004d395  mov     rbx, rax
0x14004d398  test    rax, rax
0x14004d39b  jz      loc_14004D485
0x14004d3a1  mov     rcx, [rbp+arg_18]; hKey
0x14004d3a5  mov     r9, rbx; hEvent
0x14004d3a8  mov     r8d, esi; dwNotifyFilter
0x14004d3ab  mov     dword ptr [rsp+40h+phkResult], 1; fAsynchronous
0x14004d3b3  xor     edx, edx; bWatchSubtree
0x14004d3b5  call    cs:__imp_RegNotifyChangeKeyValue
0x14004d3bb  test    eax, eax
0x14004d3bd  jnz     loc_14004D47C
0x14004d3c3  mov     edx, 4E20h; dwMilliseconds
0x14004d3c8  mov     rcx, rbx; hHandle
0x14004d3cb  call    cs:__imp_WaitForSingleObject
0x14004d3d1  mov     r9d, eax
0x14004d3d4  test    eax, eax
0x14004d3d6  jnz     short loc_14004D448
0x14004d3d8  mov     rcx, [rbp+arg_18]; hKey
0x14004d3dc  lea     r9, [rbp+Type]; lpType
0x14004d3e0  mov     [rbp+Data], eax
0x14004d3e3  lea     rdx, aRunonceDone; "RunOnce.Done"
0x14004d3ea  lea     rax, [rbp+cbData]
0x14004d3ee  mov     [rbp+Type], esi
0x14004d3f1  mov     [rsp+40h+lpcbData], rax; lpcbData
0x14004d3f6  xor     r8d, r8d; lpReserved
0x14004d3f9  lea     rax, [rbp+Data]
0x14004d3fd  mov     [rbp+cbData], esi
0x14004d400  mov     [rsp+40h+phkResult], rax; lpData
0x14004d405  call    cs:__imp_RegQueryValueExW
0x14004d40b  test    eax, eax
0x14004d40d  jnz     short loc_14004D3A1
0x14004d40f  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d416  lea     rax, WPP_GLOBAL_Control
0x14004d41d  cmp     rcx, rax
0x14004d420  jz      short loc_14004D47C
0x14004d422  test    dword ptr [rcx+1Ch], 1000h
0x14004d429  jz      short loc_14004D47C
0x14004d42b  cmp     [rcx+19h], sil
0x14004d42f  jb      short loc_14004D47C
0x14004d431  mov     rcx, [rcx+10h]
0x14004d435  lea     r8, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids
0x14004d43c  mov     edx, 69h ; 'i'
0x14004d441  call    WPP_SF_
0x14004d446  jmp     short loc_14004D47C
0x14004d448  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d44f  lea     rax, WPP_GLOBAL_Control
0x14004d456  cmp     rcx, rax
0x14004d459  jz      short loc_14004D47C
0x14004d45b  test    byte ptr [rcx+1Ch], 20h
0x14004d45f  jz      short loc_14004D47C
0x14004d461  cmp     byte ptr [rcx+19h], 2
0x14004d465  jb      short loc_14004D47C
0x14004d467  mov     rcx, [rcx+10h]
0x14004d46b  lea     r8, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids
0x14004d472  mov     edx, 68h ; 'h'
0x14004d477  call    WPP_SF_d
0x14004d47c  mov     rcx, rbx; hObject
0x14004d47f  call    cs:__imp_CloseHandle
0x14004d485  mov     rcx, [rbp+arg_18]; hKey
0x14004d489  call    cs:__imp_RegCloseKey
0x14004d48f  add     rsp, 40h
0x14004d493  pop     rsi
0x14004d494  pop     rbx
0x14004d495  pop     rbp
0x14004d496  retn
```
