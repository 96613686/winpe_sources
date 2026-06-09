# CheckPointerDeviceConfiguration

- ea: `0x140249f80`
- end: `0x14024a15f`
- name: `CheckPointerDeviceConfiguration`
- size: `479`
- prototype: `void()`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1402702c0`

## callees

- `0x1400ae630`
- `0x1400ae730`
- `0x140249f80`
- `0x1402a7958`

## import_xrefs

- `win32kbase!IsPrecisionTouchPadEnabled` at `0x14024a065`
- `win32kbase!IsPrecisionTouchPadEnabled` at `0x14024a065`
- `win32kbase!RIMRevokeConfigurationChange` at `0x14024a07b`
- `win32kbase!RIMRevokeConfigurationChange` at `0x14024a07b`
- `win32kbase!?OnUserLogin@PTPTelemetry@@SAXXZ` at `0x14024a0c7`
- `win32kbase!?OnUserLogin@PTPTelemetry@@SAXXZ` at `0x14024a0c7`
- `win32kbase!RIMConfigureDeviceFeedback` at `0x14024a115`
- `win32kbase!RIMConfigureDeviceFeedback` at `0x14024a115`
- `win32kbase!RIMConfigureTouchpadClickForceSensitivity` at `0x14024a132`
- `win32kbase!RIMConfigureTouchpadClickForceSensitivity` at `0x14024a132`
- `win32kbase!?EnvironmentChanged@CPTPProcessor@@SAXXZ` at `0x140249ff0`
- `win32kbase!?EnvironmentChanged@CPTPProcessor@@SAXXZ` at `0x140249ff0`
- `win32kbase!_GetPrecisionTouchPadConfiguration` at `0x140249fb9`
- `win32kbase!_GetPrecisionTouchPadConfiguration` at `0x140249fb9`
- `win32kbase!AccessPTPEnabledStatus` at `0x140249fce`
- `win32kbase!AccessPTPEnabledStatus` at `0x140249fce`
- `win32kbase!?TmpGetDeviceList@CBaseInput@@QEAAPEAUDEVICEINFO@@XZ` at `0x14024a03b`
- `win32kbase!?TmpGetDeviceList@CBaseInput@@QEAAPEAUDEVICEINFO@@XZ` at `0x14024a03b`
- `win32kbase!?TmpGetLock@CBaseInput@@QEAAAEAVW32_PUSH_LOCK@@XZ` at `0x14024a00f`
- `win32kbase!?TmpGetLock@CBaseInput@@QEAAAEAVW32_PUSH_LOCK@@XZ` at `0x14024a00f`
- `win32kbase!UPDWORDPointer` at `0x140249f8e`
- `win32kbase!UPDWORDPointer` at `0x140249f8e`
- `WIN32K!W32GetUserSessionState` at `0x140249f9c`
- `WIN32K!W32GetUserSessionState` at `0x140249fde`
- `WIN32K!W32GetUserSessionState` at `0x140249ffc`
- `WIN32K!W32GetUserSessionState` at `0x14024a028`
- `WIN32K!W32GetUserSessionState` at `0x14024a0e6`
- `WIN32K!W32GetUserSessionState` at `0x140249f9c`
- `WIN32K!W32GetUserSessionState` at `0x140249fde`
- `WIN32K!W32GetUserSessionState` at `0x140249ffc`
- `WIN32K!W32GetUserSessionState` at `0x14024a028`
- `WIN32K!W32GetUserSessionState` at `0x14024a0e6`

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
  struct _UNICODE_STRING v31; // [rsp+20h] [rbp-38h] BYREF
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
          v31 = (struct _UNICODE_STRING)*((_OWORD *)i + 12);
          ReadTiltCalibrationData(v27, &v31, v24, v25);
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
  W32ReleasePushLockSharedEx(Lock);
}

```

## disassembly

```asm
0x140249f80  push    rbx
0x140249f82  push    rbp
0x140249f83  push    rsi
0x140249f84  push    rdi
0x140249f85  sub     rsp, 38h
0x140249f89  mov     ecx, 2020h
0x140249f8e  call    cs:__imp_UPDWORDPointer
0x140249f95  nop     dword ptr [rax+rax+00h]
0x140249f9a  mov     ebx, [rax]
0x140249f9c  call    cs:__imp_W32GetUserSessionState
0x140249fa3  nop     dword ptr [rax+rax+00h]
0x140249fa8  xor     ecx, ecx
0x140249faa  mov     [rax+11Ch], ebx
0x140249fb0  mov     ebx, 1
0x140249fb5  mov     [rsp+58h+arg_0], ebx
0x140249fb9  call    cs:__imp__GetPrecisionTouchPadConfiguration
0x140249fc0  nop     dword ptr [rax+rax+00h]
0x140249fc5  lea     r8, [rsp+58h+arg_0]
0x140249fca  mov     edx, ebx
0x140249fcc  xor     ecx, ecx
0x140249fce  call    cs:__imp_AccessPTPEnabledStatus
0x140249fd5  nop     dword ptr [rax+rax+00h]
0x140249fda  mov     ebx, [rsp+58h+arg_0]
0x140249fde  call    cs:__imp_W32GetUserSessionState
0x140249fe5  nop     dword ptr [rax+rax+00h]
0x140249fea  mov     [rax+118h], ebx
0x140249ff0  call    cs:__imp_?EnvironmentChanged@CPTPProcessor@@SAXXZ; CPTPProcessor::EnvironmentChanged(void)
0x140249ff7  nop     dword ptr [rax+rax+00h]
0x140249ffc  call    cs:__imp_W32GetUserSessionState
0x14024a003  nop     dword ptr [rax+rax+00h]
0x14024a008  mov     rcx, [rax+4198h]
0x14024a00f  call    cs:__imp_?TmpGetLock@CBaseInput@@QEAAAEAVW32_PUSH_LOCK@@XZ; CBaseInput::TmpGetLock(void)
0x14024a016  nop     dword ptr [rax+rax+00h]
0x14024a01b  mov     rcx, rax; struct W32_PUSH_LOCK *
0x14024a01e  xor     edx, edx; unsigned int
0x14024a020  mov     rbx, rax
0x14024a023  call    ?W32AcquirePushLockSharedEx@@YAXPEAVW32_PUSH_LOCK@@K@Z; W32AcquirePushLockSharedEx(W32_PUSH_LOCK *,ulong)
0x14024a028  call    cs:__imp_W32GetUserSessionState
0x14024a02f  nop     dword ptr [rax+rax+00h]
0x14024a034  mov     rcx, [rax+4198h]
0x14024a03b  call    cs:__imp_?TmpGetDeviceList@CBaseInput@@QEAAPEAUDEVICEINFO@@XZ; CBaseInput::TmpGetDeviceList(void)
0x14024a042  nop     dword ptr [rax+rax+00h]
0x14024a047  mov     rdi, rax
0x14024a04a  test    rax, rax
0x14024a04d  jz      loc_14024A14B
0x14024a053  cmp     dword ptr [rdi+30h], 3
0x14024a057  jnz     short loc_14024A090
0x14024a059  test    dword ptr [rdi+0A8h], 800h
0x14024a063  jz      short loc_14024A090
0x14024a065  call    cs:__imp_IsPrecisionTouchPadEnabled
0x14024a06c  nop     dword ptr [rax+rax+00h]
0x14024a071  test    eax, eax
0x14024a073  jnz     short loc_14024A090
0x14024a075  lea     edx, [rax+57h]
0x14024a078  mov     rcx, rdi
0x14024a07b  call    cs:__imp_RIMRevokeConfigurationChange
0x14024a082  nop     dword ptr [rax+rax+00h]
0x14024a087  lea     rsi, [rdi+0B8h]
0x14024a08e  jmp     short loc_14024A0D3
0x14024a090  lea     rsi, [rdi+0B8h]
0x14024a097  mov     eax, [rsi]
0x14024a099  test    al, al
0x14024a09b  jns     short loc_14024A0D3
0x14024a09d  mov     rcx, [rdi+1C8h]
0x14024a0a4  cmp     qword ptr [rcx+198h], 0
0x14024a0ac  jz      short loc_14024A0C7
0x14024a0ae  movups  xmm0, xmmword ptr [rdi+0C0h]
0x14024a0b5  lea     rdx, [rsp+58h+var_38]
0x14024a0ba  movdqu  [rsp+58h+var_38], xmm0
0x14024a0c0  call    ReadTiltCalibrationData
0x14024a0c5  jmp     short loc_14024A0D3
0x14024a0c7  call    cs:__imp_?OnUserLogin@PTPTelemetry@@SAXXZ; PTPTelemetry::OnUserLogin(void)
0x14024a0ce  nop     dword ptr [rax+rax+00h]
0x14024a0d3  mov     eax, [rsi]
0x14024a0d5  test    al, al
0x14024a0d7  jns     short loc_14024A13E
0x14024a0d9  mov     rax, [rdi+1C8h]
0x14024a0e0  cmp     dword ptr [rax+18h], 7
0x14024a0e4  jnz     short loc_14024A13E
0x14024a0e6  call    cs:__imp_W32GetUserSessionState
0x14024a0ed  nop     dword ptr [rax+rax+00h]
0x14024a0f2  test    dword ptr [rsi], 400h
0x14024a0f8  mov     rbp, rax
0x14024a0fb  jz      short loc_14024A121
0x14024a0fd  mov     ecx, [rax+4158h]
0x14024a103  test    cl, 2
0x14024a106  jz      short loc_14024A110
0x14024a108  mov     edx, [rax+4164h]
0x14024a10e  jmp     short loc_14024A112
0x14024a110  xor     edx, edx
0x14024a112  mov     rcx, rdi
0x14024a115  call    cs:__imp_RIMConfigureDeviceFeedback
0x14024a11c  nop     dword ptr [rax+rax+00h]
0x14024a121  test    dword ptr [rsi], 800h
0x14024a127  jz      short loc_14024A13E
0x14024a129  mov     edx, [rbp+4168h]
0x14024a12f  mov     rcx, rdi
0x14024a132  call    cs:__imp_RIMConfigureTouchpadClickForceSensitivity
0x14024a139  nop     dword ptr [rax+rax+00h]
0x14024a13e  mov     rdi, [rdi+38h]
0x14024a142  test    rdi, rdi
0x14024a145  jnz     loc_14024A053
0x14024a14b  xor     edx, edx; unsigned int
0x14024a14d  mov     rcx, rbx; struct W32_PUSH_LOCK *
0x14024a150  call    ?W32ReleasePushLockSharedEx@@YAXPEAVW32_PUSH_LOCK@@K@Z; W32ReleasePushLockSharedEx(W32_PUSH_LOCK *,ulong)
0x14024a155  add     rsp, 38h
0x14024a159  pop     rdi
0x14024a15a  pop     rsi
0x14024a15b  pop     rbp
0x14024a15c  pop     rbx
0x14024a15d  retn
```
