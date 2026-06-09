# WaitForDesiredService

- ea: `0x140026b80`
- end: `0x140027114`
- name: `WaitForDesiredService`
- size: `1428`
- prototype: `__int64 __fastcall(LPCWSTR lpServiceName)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x140025480`
- `0x140025d50`

## callees

- `0x1400057f4`
- `0x140026970`
- `0x140026b80`
- `0x140041c34`
- `0x140053720`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400270b3`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400270b3`
- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x140026df8`
- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x140026df8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026ca2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026d32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026e76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026eb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026ef0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026ca2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026d32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026e76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026eb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026ef0`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x140026c09`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x140026c09`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1400270d4`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14002710c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14009dec2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14009ded2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1400270d4`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14002710c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14009dec2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14009ded2`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x140026d0b`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x140026d0b`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x140026c35`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x140026c35`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x140026dcb`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x140026dcb`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x140026c57`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x140026d24`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x140026c57`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x140026d24`

## string_xrefs

- `0x140026c00`: `ServicesActive`

## pseudocode

```c
__int64 __fastcall WaitForDesiredService(LPCWSTR lpServiceName, DWORD a2, int a3)
{
  char v4; // si
  SC_HANDLE v6; // rdi
  DWORD v7; // r12d
  DWORD v8; // r14d
  SC_HANDLE v9; // rbx
  SC_HANDLE v10; // rax
  __int64 v11; // r9
  char dwCurrentState; // cl
  DWORD LastError; // esi
  CUser *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r9
  DWORD v17; // eax
  __int64 v18; // r9
  DWORD v19; // eax
  SERVICE_NOTIFY_2W pNotifyBuffer; // [rsp+50h] [rbp-A8h] BYREF
  _SERVICE_STATUS ServiceStatus; // [rsp+A0h] [rbp-58h] BYREF

  v4 = a2;
  v6 = 0;
  memset(&pNotifyBuffer, 0, sizeof(pNotifyBuffer));
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v7 = 0;
  v8 = 20;
  while ( 1 )
  {
    v9 = OpenSCManagerW(0, L"ServicesActive", 1u);
    if ( v9 )
    {
      if ( !a3 )
        v8 = 4;
      v10 = OpenServiceW(v9, lpServiceName, v8);
      v6 = v10;
      if ( !v10 )
      {
        LastError = GetLastError();
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_84;
        }
        v15 = 21;
        goto LABEL_19;
      }
      if ( !QueryServiceStatus(v10, &ServiceStatus) )
      {
        LastError = GetLastError();
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_84;
        }
        v15 = 22;
        goto LABEL_19;
      }
      if ( !a3 )
      {
LABEL_8:
        dwCurrentState = ServiceStatus.dwCurrentState;
        goto LABEL_9;
      }
      dwCurrentState = ServiceStatus.dwCurrentState;
      if ( ((ServiceStatus.dwCurrentState - 2) & 0xFFFFFFFD) == 0 )
      {
LABEL_9:
        if ( (dwCurrentState & 4) != 0 )
          goto LABEL_10;
        if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_Sl(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            25,
            (unsigned int)WPP_dee1fec175ed3bc1a62ebb36f32fb4e0_Traceguids,
            (_DWORD)lpServiceName,
            v4);
        }
        pNotifyBuffer.dwVersion = 2;
        pNotifyBuffer.pfnNotifyCallback = (PFN_SC_NOTIFY_CALLBACK)NotifyCallback;
        v17 = NotifyServiceStatusChangeW(v6, 8u, &pNotifyBuffer);
        LastError = v17;
        if ( v17 )
        {
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_84;
          }
          v15 = 26;
          v16 = v17;
        }
        else
        {
          if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_dee1fec175ed3bc1a62ebb36f32fb4e0_Traceguids, v18);
          }
          v19 = SleepEx(a2, 1);
          LastError = v19;
          if ( v19 )
          {
            if ( v19 == 192 )
            {
              LastError = pNotifyBuffer.dwNotificationStatus;
              if ( !pNotifyBuffer.dwNotificationStatus )
              {
                if ( pNotifyBuffer.ServiceStatus.dwCurrentState != 4 )
                {
                  LastError = 1460;
                  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    WPP_SF_Sl(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      31,
                      (unsigned int)WPP_dee1fec175ed3bc1a62ebb36f32fb4e0_Traceguids,
                      (_DWORD)lpServiceName,
                      pNotifyBuffer.ServiceStatus.dwCurrentState);
                  }
                  goto LABEL_84;
                }
LABEL_10:
                if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_dee1fec175ed3bc1a62ebb36f32fb4e0_Traceguids, v11);
                }
                LastError = 0;
                goto LABEL_84;
              }
              v14 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_84;
              }
              v15 = 30;
              goto LABEL_19;
            }
            v14 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_84;
            }
            v15 = 29;
            v16 = v19;
          }
          else
          {
            LastError = 1460;
            v14 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_84;
            }
            v15 = 28;
            v16 = a2;
          }
        }
LABEL_20:
        WPP_SF_d(*((_QWORD *)v14 + 2), v15, WPP_dee1fec175ed3bc1a62ebb36f32fb4e0_Traceguids, v16);
        goto LABEL_84;
      }
      if ( !StartServiceW(v6, 0, 0) )
      {
        LastError = GetLastError();
        if ( LastError != 1056 )
        {
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_84;
          }
          v15 = 23;
          goto LABEL_19;
        }
        v4 = a2;
      }
      if ( QueryServiceStatus(v6, &ServiceStatus) )
        goto LABEL_8;
      LastError = GetLastError();
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_84;
      }
      v15 = 24;
LABEL_19:
      v16 = LastError;
      goto LABEL_20;
    }
    LastError = GetLastError();
    if ( LastError != 1460 )
      break;
    v4 = a2;
    if ( v7 > a2 )
    {
      LastError = 1460;
      goto LABEL_84;
    }
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_dee1fec175ed3bc1a62ebb36f32fb4e0_Traceguids, a2);
    }
    Sleep(0x64u);
    v7 += 100;
  }
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v15 = 19;
    goto LABEL_19;
  }
LABEL_84:
  if ( v6 )
    CloseServiceHandle(v6);
  if ( v9 )
    CloseServiceHandle(v9);
  return LastError;
}

```

## disassembly

```asm
0x140026b80  mov     r11, rsp
0x140026b83  mov     [r11+18h], rbx
0x140026b87  mov     [r11+20h], rsi
0x140026b8b  push    rdi
0x140026b8c  push    r12
0x140026b8e  push    r13
0x140026b90  push    r14
0x140026b92  push    r15
0x140026b94  sub     rsp, 0D0h
0x140026b9b  mov     rax, cs:__security_cookie
0x140026ba2  xor     rax, rsp
0x140026ba5  mov     [rsp+0F8h+var_38], rax
0x140026bad  mov     r15d, r8d
0x140026bb0  mov     esi, edx
0x140026bb2  mov     [rsp+0F8h+dwMilliseconds], edx
0x140026bb6  mov     r13, rcx
0x140026bb9  mov     [rsp+0F8h+var_B8], 0
0x140026bc2  xor     edi, edi
0x140026bc4  mov     [rsp+0F8h+var_C0], rdi
0x140026bc9  xorps   xmm0, xmm0
0x140026bcc  movups  xmmword ptr [rsp+0F8h+pNotifyBuffer.dwVersion], xmm0
0x140026bd1  movups  xmmword ptr [rsp+0F8h+pNotifyBuffer.pContext], xmm0
0x140026bd6  movups  xmmword ptr [rsp+0F8h+pNotifyBuffer.ServiceStatus.dwCurrentState], xmm0
0x140026bdb  movups  xmmword ptr [r11-78h], xmm0
0x140026be0  movups  xmmword ptr [r11-68h], xmm0
0x140026be5  xor     eax, eax
0x140026be7  movups  xmmword ptr [r11-58h], xmm0
0x140026bec  movups  xmmword ptr [r11-4Ch], xmm0
0x140026bf1  xor     r12d, r12d
0x140026bf4  mov     r14d, 14h
0x140026bfa  mov     r8d, 1; dwDesiredAccess
0x140026c00  lea     rdx, DatabaseName; "ServicesActive"
0x140026c07  xor     ecx, ecx; lpMachineName
0x140026c09  call    cs:__imp_OpenSCManagerW
0x140026c0f  mov     rbx, rax
0x140026c12  mov     [rsp+0F8h+var_B8], rax
0x140026c17  test    rax, rax
0x140026c1a  jz      loc_140026CA2
0x140026c20  mov     eax, 4
0x140026c25  test    r15d, r15d
0x140026c28  cmovz   r14d, eax
0x140026c2c  mov     r8d, r14d; dwDesiredAccess
0x140026c2f  mov     rdx, r13; lpServiceName
0x140026c32  mov     rcx, rbx; hSCManager
0x140026c35  call    cs:__imp_OpenServiceW
0x140026c3b  mov     rdi, rax
0x140026c3e  mov     [rsp+0F8h+var_C0], rax
0x140026c43  test    rax, rax
0x140026c46  jz      loc_140026EB3
0x140026c4c  lea     rdx, [rsp+0F8h+ServiceStatus]; lpServiceStatus
0x140026c54  mov     rcx, rax; hService
0x140026c57  call    cs:__imp_QueryServiceStatus
0x140026c5d  test    eax, eax
0x140026c5f  jz      loc_140026E76
0x140026c65  test    r15d, r15d
0x140026c68  jnz     loc_140026CEE
0x140026c6e  mov     ecx, [rsp+0F8h+ServiceStatus.dwCurrentState]
0x140026c75  test    cl, 4
0x140026c78  jz      loc_140026D93
0x140026c7e  lea     r15, WPP_GLOBAL_Control
0x140026c85  mov     rcx, cs:WPP_GLOBAL_Control
0x140026c8c  cmp     rcx, r15
0x140026c8f  jz      short loc_140026C9B
0x140026c91  test    byte ptr [rcx+1Ch], 1
0x140026c95  jnz     loc_140026D6F
0x140026c9b  xor     esi, esi
0x140026c9d  jmp     loc_1400270C7
0x140026ca2  call    cs:__imp_GetLastError
0x140026ca8  mov     esi, eax
0x140026caa  cmp     eax, 5B4h
0x140026caf  jz      loc_140027066
0x140026cb5  mov     rcx, cs:WPP_GLOBAL_Control
0x140026cbc  lea     rax, WPP_GLOBAL_Control
0x140026cc3  cmp     rcx, rax
0x140026cc6  jz      short loc_140026C9D
0x140026cc8  test    byte ptr [rcx+1Ch], 1
0x140026ccc  jz      short loc_140026C9D
0x140026cce  cmp     byte ptr [rcx+19h], 2
0x140026cd2  jb      short loc_140026C9D
0x140026cd4  mov     edx, 13h
0x140026cd9  mov     r9d, esi
0x140026cdc  lea     r8, WPP_dee1fec175ed3bc1a62ebb36f32fb4e0_Traceguids
0x140026ce3  mov     rcx, [rcx+10h]
0x140026ce7  call    WPP_SF_d
0x140026cec  jmp     short loc_140026C9D
0x140026cee  mov     ecx, [rsp+0F8h+ServiceStatus.dwCurrentState]
0x140026cf5  lea     eax, [rcx-2]
0x140026cf8  test    eax, 0FFFFFFFDh
0x140026cfd  jz      loc_140026C75
0x140026d03  xor     r8d, r8d; lpServiceArgVectors
0x140026d06  xor     edx, edx; dwNumServiceArgs
0x140026d08  mov     rcx, rdi; hService
0x140026d0b  call    cs:__imp_StartServiceW
0x140026d11  test    eax, eax
0x140026d13  jz      loc_140026EF0
0x140026d19  lea     rdx, [rsp+0F8h+ServiceStatus]; lpServiceStatus
0x140026d21  mov     rcx, rdi; hService
0x140026d24  call    cs:__imp_QueryServiceStatus
0x140026d2a  test    eax, eax
0x140026d2c  jnz     loc_140026C6E
0x140026d32  call    cs:__imp_GetLastError
0x140026d38  mov     esi, eax
0x140026d3a  mov     rcx, cs:WPP_GLOBAL_Control
0x140026d41  lea     rax, WPP_GLOBAL_Control
0x140026d48  cmp     rcx, rax
0x140026d4b  jz      loc_140026C9D
0x140026d51  test    byte ptr [rcx+1Ch], 1
0x140026d55  jz      loc_140026C9D
0x140026d5b  cmp     byte ptr [rcx+19h], 2
0x140026d5f  jb      loc_140026C9D
0x140026d65  mov     edx, 18h
0x140026d6a  jmp     loc_140026CD9
0x140026d6f  cmp     byte ptr [rcx+19h], 4
0x140026d73  jb      loc_140026C9B
0x140026d79  mov     edx, 20h ; ' '
0x140026d7e  lea     r8, WPP_dee1fec175ed3bc1a62ebb36f32fb4e0_Traceguids
0x140026d85  mov     rcx, [rcx+10h]
0x140026d89  call    WPP_SF_
0x140026d8e  jmp     loc_140026C9B
0x140026d93  mov     rcx, cs:WPP_GLOBAL_Control
0x140026d9a  lea     r15, WPP_GLOBAL_Control
0x140026da1  cmp     rcx, r15
0x140026da4  jnz     loc_140026F3D
0x140026daa  mov     [rsp+0F8h+pNotifyBuffer.dwVersion], 2
0x140026db2  lea     rax, ?NotifyCallback@@YAXPEAX@Z; NotifyCallback(void *)
0x140026db9  mov     [rsp+0F8h+pNotifyBuffer.pfnNotifyCallback], rax
0x140026dbe  lea     r8, [rsp+0F8h+pNotifyBuffer]; pNotifyBuffer
0x140026dc3  mov     edx, 8; dwNotifyMask
0x140026dc8  mov     rcx, rdi; hService
0x140026dcb  call    cs:__imp_NotifyServiceStatusChangeW
0x140026dd1  mov     esi, eax
0x140026dd3  test    eax, eax
0x140026dd5  jnz     loc_140026F72
0x140026ddb  mov     rcx, cs:WPP_GLOBAL_Control
0x140026de2  cmp     rcx, r15
0x140026de5  jnz     loc_140026FA3
0x140026deb  mov     edx, 1; bAlertable
0x140026df0  mov     r14d, [rsp+0F8h+dwMilliseconds]
0x140026df5  mov     ecx, r14d; dwMilliseconds
0x140026df8  call    cs:__imp_SleepEx
0x140026dfe  mov     esi, eax
0x140026e00  test    eax, eax
0x140026e02  jz      loc_140026FD1
0x140026e08  cmp     eax, 0C0h
0x140026e0d  jnz     loc_140027007
0x140026e13  mov     esi, [rsp+0F8h+pNotifyBuffer.dwNotificationStatus]
0x140026e17  test    esi, esi
0x140026e19  jnz     loc_140027038
0x140026e1f  mov     eax, [rsp+0F8h+pNotifyBuffer.ServiceStatus.dwCurrentState]
0x140026e23  cmp     eax, 4
0x140026e26  jz      loc_140026C85
0x140026e2c  mov     esi, 5B4h
0x140026e31  mov     rcx, cs:WPP_GLOBAL_Control
0x140026e38  cmp     rcx, r15
0x140026e3b  jz      loc_140026C9D
0x140026e41  test    byte ptr [rcx+1Ch], 1
0x140026e45  jz      loc_140026C9D
0x140026e4b  cmp     byte ptr [rcx+19h], 2
0x140026e4f  jb      loc_140026C9D
0x140026e55  mov     edx, 1Fh
0x140026e5a  mov     [rsp+0F8h+var_D8], eax
0x140026e5e  mov     r9, r13
0x140026e61  lea     r8, WPP_dee1fec175ed3bc1a62ebb36f32fb4e0_Traceguids
0x140026e68  mov     rcx, [rcx+10h]
0x140026e6c  call    WPP_SF_Sl
0x140026e71  jmp     loc_140026C9D
0x140026e76  call    cs:__imp_GetLastError
0x140026e7c  mov     esi, eax
0x140026e7e  mov     rcx, cs:WPP_GLOBAL_Control
0x140026e85  lea     rax, WPP_GLOBAL_Control
0x140026e8c  cmp     rcx, rax
0x140026e8f  jz      loc_140026C9D
0x140026e95  test    byte ptr [rcx+1Ch], 1
0x140026e99  jz      loc_140026C9D
0x140026e9f  cmp     byte ptr [rcx+19h], 2
0x140026ea3  jb      loc_140026C9D
0x140026ea9  mov     edx, 16h
0x140026eae  jmp     loc_140026CD9
0x140026eb3  call    cs:__imp_GetLastError
0x140026eb9  mov     esi, eax
0x140026ebb  mov     rcx, cs:WPP_GLOBAL_Control
0x140026ec2  lea     rax, WPP_GLOBAL_Control
0x140026ec9  cmp     rcx, rax
0x140026ecc  jz      loc_140026C9D
0x140026ed2  test    byte ptr [rcx+1Ch], 1
0x140026ed6  jz      loc_140026C9D
0x140026edc  cmp     byte ptr [rcx+19h], 2
0x140026ee0  jb      loc_140026C9D
0x140026ee6  mov     edx, 15h
0x140026eeb  jmp     loc_140026CD9
0x140026ef0  call    cs:__imp_GetLastError
0x140026ef6  mov     esi, eax
0x140026ef8  cmp     eax, 420h
0x140026efd  jz      short loc_140026F34
0x140026eff  mov     rcx, cs:WPP_GLOBAL_Control
0x140026f06  lea     rax, WPP_GLOBAL_Control
0x140026f0d  cmp     rcx, rax
0x140026f10  jz      loc_140026C9D
0x140026f16  test    byte ptr [rcx+1Ch], 1
0x140026f1a  jz      loc_140026C9D
0x140026f20  cmp     byte ptr [rcx+19h], 2
0x140026f24  jb      loc_140026C9D
0x140026f2a  mov     edx, 17h
0x140026f2f  jmp     loc_140026CD9
0x140026f34  mov     esi, [rsp+0F8h+dwMilliseconds]
0x140026f38  jmp     loc_140026D19
0x140026f3d  test    byte ptr [rcx+1Ch], 1
0x140026f41  jz      loc_140026DAA
0x140026f47  cmp     byte ptr [rcx+19h], 4
0x140026f4b  jb      loc_140026DAA
0x140026f51  mov     edx, 19h
0x140026f56  mov     [rsp+0F8h+var_D8], esi
0x140026f5a  mov     r9, r13
0x140026f5d  lea     r8, WPP_dee1fec175ed3bc1a62ebb36f32fb4e0_Traceguids
0x140026f64  mov     rcx, [rcx+10h]
0x140026f68  call    WPP_SF_Sl
0x140026f6d  jmp     loc_140026DAA
0x140026f72  mov     rcx, cs:WPP_GLOBAL_Control
0x140026f79  cmp     rcx, r15
0x140026f7c  jz      loc_140026C9D
0x140026f82  test    byte ptr [rcx+1Ch], 1
0x140026f86  jz      loc_140026C9D
0x140026f8c  cmp     byte ptr [rcx+19h], 2
0x140026f90  jb      loc_140026C9D
0x140026f96  mov     edx, 1Ah
0x140026f9b  mov     r9d, eax
0x140026f9e  jmp     loc_140026CDC
0x140026fa3  test    byte ptr [rcx+1Ch], 1
0x140026fa7  jz      loc_140026DEB
0x140026fad  cmp     byte ptr [rcx+19h], 4
0x140026fb1  jb      loc_140026DEB
0x140026fb7  mov     edx, 1Bh
0x140026fbc  lea     r8, WPP_dee1fec175ed3bc1a62ebb36f32fb4e0_Traceguids
0x140026fc3  mov     rcx, [rcx+10h]
0x140026fc7  call    WPP_SF_
0x140026fcc  jmp     loc_140026DEB
0x140026fd1  mov     esi, 5B4h
0x140026fd6  mov     rcx, cs:WPP_GLOBAL_Control
0x140026fdd  cmp     rcx, r15
0x140026fe0  jz      loc_140026C9D
0x140026fe6  test    byte ptr [rcx+1Ch], 1
0x140026fea  jz      loc_140026C9D
0x140026ff0  cmp     byte ptr [rcx+19h], 2
0x140026ff4  jb      loc_140026C9D
0x140026ffa  mov     edx, 1Ch
0x140026fff  mov     r9d, r14d
0x140027002  jmp     loc_140026CDC
0x140027007  mov     rcx, cs:WPP_GLOBAL_Control
0x14002700e  cmp     rcx, r15
0x140027011  jz      loc_140026C9D
0x140027017  test    byte ptr [rcx+1Ch], 1
0x14002701b  jz      loc_140026C9D
0x140027021  cmp     byte ptr [rcx+19h], 2
0x140027025  jb      loc_140026C9D
0x14002702b  mov     edx, 1Dh
0x140027030  mov     r9d, eax
0x140027033  jmp     loc_140026CDC
0x140027038  mov     rcx, cs:WPP_GLOBAL_Control
0x14002703f  cmp     rcx, r15
0x140027042  jz      loc_140026C9D
0x140027048  test    byte ptr [rcx+1Ch], 1
0x14002704c  jz      loc_140026C9D
0x140027052  cmp     byte ptr [rcx+19h], 2
0x140027056  jb      loc_140026C9D
0x14002705c  mov     edx, 1Eh
0x140027061  jmp     loc_140026CD9
0x140027066  mov     esi, [rsp+0F8h+dwMilliseconds]
0x14002706a  cmp     r12d, esi
0x14002706d  jbe     short loc_140027079
0x14002706f  mov     esi, 5B4h
0x140027074  jmp     loc_140026C9D
0x140027079  mov     rcx, cs:WPP_GLOBAL_Control
0x140027080  lea     rax, WPP_GLOBAL_Control
0x140027087  cmp     rcx, rax
0x14002708a  jz      short loc_1400270AE
0x14002708c  test    byte ptr [rcx+1Ch], 1
0x140027090  jz      short loc_1400270AE
0x140027092  cmp     byte ptr [rcx+19h], 4
0x140027096  jb      short loc_1400270AE
0x140027098  mov     edx, r14d
0x14002709b  mov     r9d, esi
0x14002709e  lea     r8, WPP_dee1fec175ed3bc1a62ebb36f32fb4e0_Traceguids
0x1400270a5  mov     rcx, [rcx+10h]
0x1400270a9  call    WPP_SF_d
0x1400270ae  mov     ecx, 64h ; 'd'; dwMilliseconds
0x1400270b3  call    cs:__imp_Sleep
0x1400270b9  add     r12d, 64h ; 'd'
0x1400270bd  mov     [rsp+0F8h+var_B0], r12d
0x1400270c2  jmp     loc_140026BFA
0x1400270c7  test    rdi, rdi
0x1400270ca  jnz     short loc_140027109
0x1400270cc  test    rbx, rbx
0x1400270cf  jz      short loc_1400270DA
0x1400270d1  mov     rcx, rbx; hSCObject
0x1400270d4  call    cs:__imp_CloseServiceHandle
0x1400270da  mov     eax, esi
0x1400270dc  mov     rcx, [rsp+0F8h+var_38]
0x1400270e4  xor     rcx, rsp; StackCookie
0x1400270e7  call    __security_check_cookie
0x1400270ec  lea     r11, [rsp+0F8h+var_28]
  ... truncated ...
```
