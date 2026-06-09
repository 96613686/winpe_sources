# CheckPointerDeviceConfiguration

- ea: `0x140248b30`
- end: `0x140248d0f`
- name: `CheckPointerDeviceConfiguration`
- size: `479`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14026cdd0`

## callees

- `0x140098140`
- `0x1400982fc`
- `0x140248b30`
- `0x1402a5518`

## import_xrefs

- `win32kbase!IsPrecisionTouchPadEnabled` at `0x140248c15`
- `win32kbase!IsPrecisionTouchPadEnabled` at `0x140248c15`
- `win32kbase!RIMRevokeConfigurationChange` at `0x140248c2b`
- `win32kbase!RIMRevokeConfigurationChange` at `0x140248c2b`
- `win32kbase!?OnUserLogin@PTPTelemetry@@SAXXZ` at `0x140248c77`
- `win32kbase!?OnUserLogin@PTPTelemetry@@SAXXZ` at `0x140248c77`
- `win32kbase!RIMConfigureDeviceFeedback` at `0x140248cc5`
- `win32kbase!RIMConfigureDeviceFeedback` at `0x140248cc5`
- `win32kbase!RIMConfigureTouchpadClickForceSensitivity` at `0x140248ce2`
- `win32kbase!RIMConfigureTouchpadClickForceSensitivity` at `0x140248ce2`
- `win32kbase!?EnvironmentChanged@CPTPProcessor@@SAXXZ` at `0x140248ba0`
- `win32kbase!?EnvironmentChanged@CPTPProcessor@@SAXXZ` at `0x140248ba0`
- `win32kbase!_GetPrecisionTouchPadConfiguration` at `0x140248b69`
- `win32kbase!_GetPrecisionTouchPadConfiguration` at `0x140248b69`
- `win32kbase!AccessPTPEnabledStatus` at `0x140248b7e`
- `win32kbase!AccessPTPEnabledStatus` at `0x140248b7e`
- `win32kbase!?TmpGetDeviceList@CBaseInput@@QEAAPEAUDEVICEINFO@@XZ` at `0x140248beb`
- `win32kbase!?TmpGetDeviceList@CBaseInput@@QEAAPEAUDEVICEINFO@@XZ` at `0x140248beb`
- `win32kbase!?TmpGetLock@CBaseInput@@QEAAAEAVW32_PUSH_LOCK@@XZ` at `0x140248bbf`
- `win32kbase!?TmpGetLock@CBaseInput@@QEAAAEAVW32_PUSH_LOCK@@XZ` at `0x140248bbf`
- `win32kbase!UPDWORDPointer` at `0x140248b3e`
- `win32kbase!UPDWORDPointer` at `0x140248b3e`
- `WIN32K!W32GetUserSessionState` at `0x140248b4c`
- `WIN32K!W32GetUserSessionState` at `0x140248b8e`
- `WIN32K!W32GetUserSessionState` at `0x140248bac`
- `WIN32K!W32GetUserSessionState` at `0x140248bd8`
- `WIN32K!W32GetUserSessionState` at `0x140248c96`
- `WIN32K!W32GetUserSessionState` at `0x140248b4c`
- `WIN32K!W32GetUserSessionState` at `0x140248b8e`
- `WIN32K!W32GetUserSessionState` at `0x140248bac`
- `WIN32K!W32GetUserSessionState` at `0x140248bd8`
- `WIN32K!W32GetUserSessionState` at `0x140248c96`

## pseudocode

```c
void CheckPointerDeviceConfiguration()
{
  int v0; // ebx
  __int64 v1; // rdx
  __int64 v2; // rcx
  __int64 v3; // r8
  __int64 v4; // r9
  int v5; // ebx
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 UserSessionState; // rax
  struct W32_PUSH_LOCK *Lock; // rbx
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 v20; // rax
  __int64 v21; // rdx
  __int64 v22; // rcx
  struct DEVICEINFO *i; // rdi
  __int64 v24; // r8
  __int64 v25; // r9
  _DWORD *v26; // rsi
  __int64 v27; // rcx
  __int64 v28; // rax
  __int64 v29; // rbp
  __int64 v30; // rdx
  _OWORD v31[3]; // [rsp+20h] [rbp-38h] BYREF
  int v32; // [rsp+60h] [rbp+8h] BYREF

  v0 = *(_DWORD *)UPDWORDPointer(8224);
  *(_DWORD *)(W32GetUserSessionState(v2, v1, v3, v4) + 284) = v0;
  v32 = 1;
  _GetPrecisionTouchPadConfiguration(0);
  AccessPTPEnabledStatus(0, 1, &v32);
  v5 = v32;
  *(_DWORD *)(W32GetUserSessionState(v7, v6, v8, v9) + 280) = v5;
  CPTPProcessor::EnvironmentChanged();
  UserSessionState = W32GetUserSessionState(v11, v10, v12, v13);
  Lock = CBaseInput::TmpGetLock(*(CBaseInput **)(UserSessionState + 16792));
  W32AcquirePushLockSharedEx(Lock, 0);
  v20 = W32GetUserSessionState(v17, v16, v18, v19);
  for ( i = CBaseInput::TmpGetDeviceList(*(CBaseInput **)(v20 + 16792)); i; i = (struct DEVICEINFO *)*((_QWORD *)i + 7) )
  {
    if ( *((_DWORD *)i + 12) == 3 && (*((_DWORD *)i + 42) & 0x800) != 0 && !(unsigned int)IsPrecisionTouchPadEnabled() )
    {
      RIMRevokeConfigurationChange(i, 87);
      v26 = (_DWORD *)((char *)i + 184);
    }
    else
    {
      v26 = (_DWORD *)((char *)i + 184);
      if ( (*((_DWORD *)i + 46) & 0x80u) != 0 )
      {
        v27 = *((_QWORD *)i + 57);
        if ( *(_QWORD *)(v27 + 408) )
        {
          v31[0] = *((_OWORD *)i + 12);
          ReadTiltCalibrationData(v27, v31);
        }
        else
        {
          PTPTelemetry::OnUserLogin();
        }
      }
    }
    if ( (*v26 & 0x80u) != 0 && *(_DWORD *)(*((_QWORD *)i + 57) + 24LL) == 7 )
    {
      v28 = W32GetUserSessionState(v22, v21, v24, v25);
      v29 = v28;
      if ( (*v26 & 0x400) != 0 )
      {
        if ( (*(_DWORD *)(v28 + 16728) & 2) != 0 )
          v30 = *(unsigned int *)(v28 + 16740);
        else
          v30 = 0;
        RIMConfigureDeviceFeedback(i, v30);
      }
      if ( (*v26 & 0x800) != 0 )
        RIMConfigureTouchpadClickForceSensitivity(i, *(unsigned int *)(v29 + 16744));
    }
  }
  W32ReleasePushLockSharedEx(Lock, 0);
}

```

## disassembly

```asm
0x140248b30  push    rbx
0x140248b32  push    rbp
0x140248b33  push    rsi
0x140248b34  push    rdi
0x140248b35  sub     rsp, 38h
0x140248b39  mov     ecx, 2020h
0x140248b3e  call    cs:__imp_UPDWORDPointer
0x140248b45  nop     dword ptr [rax+rax+00h]
0x140248b4a  mov     ebx, [rax]
0x140248b4c  call    cs:__imp_W32GetUserSessionState
0x140248b53  nop     dword ptr [rax+rax+00h]
0x140248b58  xor     ecx, ecx
0x140248b5a  mov     [rax+11Ch], ebx
0x140248b60  mov     ebx, 1
0x140248b65  mov     [rsp+58h+arg_0], ebx
0x140248b69  call    cs:__imp__GetPrecisionTouchPadConfiguration
0x140248b70  nop     dword ptr [rax+rax+00h]
0x140248b75  lea     r8, [rsp+58h+arg_0]
0x140248b7a  mov     edx, ebx
0x140248b7c  xor     ecx, ecx
0x140248b7e  call    cs:__imp_AccessPTPEnabledStatus
0x140248b85  nop     dword ptr [rax+rax+00h]
0x140248b8a  mov     ebx, [rsp+58h+arg_0]
0x140248b8e  call    cs:__imp_W32GetUserSessionState
0x140248b95  nop     dword ptr [rax+rax+00h]
0x140248b9a  mov     [rax+118h], ebx
0x140248ba0  call    cs:__imp_?EnvironmentChanged@CPTPProcessor@@SAXXZ; CPTPProcessor::EnvironmentChanged(void)
0x140248ba7  nop     dword ptr [rax+rax+00h]
0x140248bac  call    cs:__imp_W32GetUserSessionState
0x140248bb3  nop     dword ptr [rax+rax+00h]
0x140248bb8  mov     rcx, [rax+4198h]
0x140248bbf  call    cs:__imp_?TmpGetLock@CBaseInput@@QEAAAEAVW32_PUSH_LOCK@@XZ; CBaseInput::TmpGetLock(void)
0x140248bc6  nop     dword ptr [rax+rax+00h]
0x140248bcb  mov     rcx, rax; struct W32_PUSH_LOCK *
0x140248bce  xor     edx, edx; unsigned int
0x140248bd0  mov     rbx, rax
0x140248bd3  call    ?W32AcquirePushLockSharedEx@@YAXPEAVW32_PUSH_LOCK@@K@Z; W32AcquirePushLockSharedEx(W32_PUSH_LOCK *,ulong)
0x140248bd8  call    cs:__imp_W32GetUserSessionState
0x140248bdf  nop     dword ptr [rax+rax+00h]
0x140248be4  mov     rcx, [rax+4198h]
0x140248beb  call    cs:__imp_?TmpGetDeviceList@CBaseInput@@QEAAPEAUDEVICEINFO@@XZ; CBaseInput::TmpGetDeviceList(void)
0x140248bf2  nop     dword ptr [rax+rax+00h]
0x140248bf7  mov     rdi, rax
0x140248bfa  test    rax, rax
0x140248bfd  jz      loc_140248CFB
0x140248c03  cmp     dword ptr [rdi+30h], 3
0x140248c07  jnz     short loc_140248C40
0x140248c09  test    dword ptr [rdi+0A8h], 800h
0x140248c13  jz      short loc_140248C40
0x140248c15  call    cs:__imp_IsPrecisionTouchPadEnabled
0x140248c1c  nop     dword ptr [rax+rax+00h]
0x140248c21  test    eax, eax
0x140248c23  jnz     short loc_140248C40
0x140248c25  lea     edx, [rax+57h]
0x140248c28  mov     rcx, rdi
0x140248c2b  call    cs:__imp_RIMRevokeConfigurationChange
0x140248c32  nop     dword ptr [rax+rax+00h]
0x140248c37  lea     rsi, [rdi+0B8h]
0x140248c3e  jmp     short loc_140248C83
0x140248c40  lea     rsi, [rdi+0B8h]
0x140248c47  mov     eax, [rsi]
0x140248c49  test    al, al
0x140248c4b  jns     short loc_140248C83
0x140248c4d  mov     rcx, [rdi+1C8h]
0x140248c54  cmp     qword ptr [rcx+198h], 0
0x140248c5c  jz      short loc_140248C77
0x140248c5e  movups  xmm0, xmmword ptr [rdi+0C0h]
0x140248c65  lea     rdx, [rsp+58h+var_38]
0x140248c6a  movdqu  [rsp+58h+var_38], xmm0
0x140248c70  call    ReadTiltCalibrationData
0x140248c75  jmp     short loc_140248C83
0x140248c77  call    cs:__imp_?OnUserLogin@PTPTelemetry@@SAXXZ; PTPTelemetry::OnUserLogin(void)
0x140248c7e  nop     dword ptr [rax+rax+00h]
0x140248c83  mov     eax, [rsi]
0x140248c85  test    al, al
0x140248c87  jns     short loc_140248CEE
0x140248c89  mov     rax, [rdi+1C8h]
0x140248c90  cmp     dword ptr [rax+18h], 7
0x140248c94  jnz     short loc_140248CEE
0x140248c96  call    cs:__imp_W32GetUserSessionState
0x140248c9d  nop     dword ptr [rax+rax+00h]
0x140248ca2  test    dword ptr [rsi], 400h
0x140248ca8  mov     rbp, rax
0x140248cab  jz      short loc_140248CD1
0x140248cad  mov     ecx, [rax+4158h]
0x140248cb3  test    cl, 2
0x140248cb6  jz      short loc_140248CC0
0x140248cb8  mov     edx, [rax+4164h]
0x140248cbe  jmp     short loc_140248CC2
0x140248cc0  xor     edx, edx
0x140248cc2  mov     rcx, rdi
0x140248cc5  call    cs:__imp_RIMConfigureDeviceFeedback
0x140248ccc  nop     dword ptr [rax+rax+00h]
0x140248cd1  test    dword ptr [rsi], 800h
0x140248cd7  jz      short loc_140248CEE
0x140248cd9  mov     edx, [rbp+4168h]
0x140248cdf  mov     rcx, rdi
0x140248ce2  call    cs:__imp_RIMConfigureTouchpadClickForceSensitivity
0x140248ce9  nop     dword ptr [rax+rax+00h]
0x140248cee  mov     rdi, [rdi+38h]
0x140248cf2  test    rdi, rdi
0x140248cf5  jnz     loc_140248C03
0x140248cfb  xor     edx, edx; unsigned int
0x140248cfd  mov     rcx, rbx; struct W32_PUSH_LOCK *
0x140248d00  call    ?W32ReleasePushLockSharedEx@@YAXPEAVW32_PUSH_LOCK@@K@Z; W32ReleasePushLockSharedEx(W32_PUSH_LOCK *,ulong)
0x140248d05  add     rsp, 38h
0x140248d09  pop     rdi
0x140248d0a  pop     rsi
0x140248d0b  pop     rbp
0x140248d0c  pop     rbx
0x140248d0d  retn
```
