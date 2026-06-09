# UmpoNotifyKernelAllPowerPolicyChanged

- ea: `0x180002bc0`
- end: `0x180002d83`
- name: `UmpoNotifyKernelAllPowerPolicyChanged`
- size: `451`
- prototype: `__int64 __fastcall(void *, __int64)`
- caller_count: `7`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180002530`
- `0x18000a680`
- `0x18000d9f0`
- `0x18000e360`
- `0x18000e750`
- `0x18000ed10`
- `0x18000f4f4`

## callees

- `0x180002bc0`
- `0x180002d8c`
- `0x1800034c0`
- `0x180004380`
- `0x1800061d0`
- `0x18000f3dc`
- `0x180010070`
- `0x1800132cc`
- `0x18001337c`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180002c65`
- `ntdll!RtlAllocateHeap` at `0x180002c65`
- `ntdll!RtlFreeHeap` at `0x180002cd8`
- `ntdll!RtlFreeHeap` at `0x180002cd8`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180002c23`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180002c23`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180002c36`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180002c36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002c40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002d21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002c40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002d21`

## pseudocode

```c
__int64 __fastcall UmpoNotifyKernelAllPowerPolicyChanged(void *a1, __int64 a2)
{
  char v2; // si
  __int64 v3; // rdx
  unsigned int ActiveScheme; // ebx
  __int64 v5; // r8
  char *Heap; // rax
  _DWORD *v8; // rdi
  UUID v9; // xmm0
  __int64 v10; // rdx
  unsigned int SuspensionPowerMode; // eax
  _BYTE v12[8]; // [rsp+20h] [rbp-48h] BYREF
  __int128 v13; // [rsp+28h] [rbp-40h] BYREF
  UUID v14; // [rsp+38h] [rbp-30h] BYREF
  UUID Uuid; // [rsp+48h] [rbp-20h] BYREF

  v2 = 0;
  Uuid = 0;
  v14 = 0;
  v13 = 0;
  if ( a1 )
  {
    if ( !ImpersonateLoggedOnUser(a1) )
      return GetLastError();
    v2 = 1;
  }
  ActiveScheme = UmpoGetActiveScheme(&v14, a2);
  if ( !ActiveScheme )
  {
    v12[0] = 0;
    if ( (_DWORD)UmpoOverlaySchemeSuspendMask )
    {
      ActiveScheme = UmpoInternalGetPowerModeSchema(v12, v3, v5);
      if ( ActiveScheme )
        goto LABEL_3;
      LOBYTE(v10) = v12[0];
      SuspensionPowerMode = UmpoInternalGetSuspensionPowerMode((int)UmpoOverlaySchemeSuspendMask, v10, &Uuid);
    }
    else
    {
      LOBYTE(v3) = UmpoOnAcPower;
      SuspensionPowerMode = UmpoGetActualOverlayScheme(&Uuid, v3);
    }
    ActiveScheme = SuspensionPowerMode;
    if ( !SuspensionPowerMode )
    {
      Heap = (char *)RtlAllocateHeap(UmpoHeapHandle, 8u, 0x58u);
      v8 = Heap;
      if ( Heap )
      {
        *(_DWORD *)Heap = 4;
        *((_DWORD *)Heap + 2) = 1;
        *(GUID *)(Heap + 12) = GUID_POWER_POLICY_PROFILE_DEFAULT;
        *(GUID *)(Heap + 28) = GUID_ACTIVE_POWERSCHEME;
        *(GUID *)(Heap + 44) = NO_SUBGROUP_GUID;
        v9 = v14;
        *((_DWORD *)Heap + 16) = 16;
        *((_DWORD *)Heap + 15) = 0;
        *(UUID *)(Heap + 68) = v9;
        ActiveScheme = UmpoAlpcSendPowerMessage(Heap, 0x58u);
        if ( !ActiveScheme )
        {
          v8[15] = 1;
          ActiveScheme = UmpoAlpcSendPowerMessage(v8, 0x58u);
          if ( !ActiveScheme )
          {
            *(_QWORD *)&v13 = &v14;
            *((_QWORD *)&v13 + 1) = &Uuid;
            UmpoEnumeratePowerSettings(
              0,
              (__int64 (__fastcall *)(UUID *, UUID *, __int64))UmpoNotifyKernelPowerSettingChangedCallback,
              (__int64)&v13);
          }
        }
        RtlFreeHeap(UmpoHeapHandle, 0, v8);
      }
      else
      {
        ActiveScheme = 14;
      }
    }
  }
LABEL_3:
  if ( v2 && !RevertToSelf() && GetLastError() )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  return ActiveScheme;
}

```

## disassembly

```asm
0x180002bc0  push    rbp
0x180002bc2  push    rbx
0x180002bc3  push    rsi
0x180002bc4  push    rdi
0x180002bc5  mov     rbp, rsp
0x180002bc8  sub     rsp, 68h
0x180002bcc  mov     rax, cs:__security_cookie
0x180002bd3  xor     rax, rsp
0x180002bd6  mov     [rbp+var_10], rax
0x180002bda  xorps   xmm0, xmm0
0x180002bdd  xor     sil, sil
0x180002be0  xorps   xmm1, xmm1
0x180002be3  movups  xmmword ptr [rbp+Uuid.Data1], xmm0
0x180002be7  movups  xmmword ptr [rbp+var_30.Data1], xmm1
0x180002beb  movups  [rbp+var_40], xmm0
0x180002bef  test    rcx, rcx
0x180002bf2  jnz     short loc_180002C23
0x180002bf4  lea     rcx, [rbp+var_30]; Uuid
0x180002bf8  call    UmpoGetActiveScheme
0x180002bfd  mov     ebx, eax
0x180002bff  test    eax, eax
0x180002c01  jz      loc_180002D2E
0x180002c07  test    sil, sil
0x180002c0a  jnz     short loc_180002C36
0x180002c0c  mov     eax, ebx
0x180002c0e  mov     rcx, [rbp+var_10]
0x180002c12  xor     rcx, rsp; StackCookie
0x180002c15  call    __security_check_cookie
0x180002c1a  add     rsp, 68h
0x180002c1e  pop     rdi
0x180002c1f  pop     rsi
0x180002c20  pop     rbx
0x180002c21  pop     rbp
0x180002c22  retn
0x180002c23  call    cs:__imp_ImpersonateLoggedOnUser
0x180002c29  test    eax, eax
0x180002c2b  jz      loc_180002D21
0x180002c31  mov     sil, 1
0x180002c34  jmp     short loc_180002BF4
0x180002c36  call    cs:__imp_RevertToSelf
0x180002c3c  test    eax, eax
0x180002c3e  jnz     short loc_180002C0C
0x180002c40  call    cs:__imp_GetLastError
0x180002c46  test    eax, eax
0x180002c48  jz      short loc_180002C0C
0x180002c4a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180002c4f  jmp     short loc_180002C0C
0x180002c51  mov     ebx, eax
0x180002c53  test    eax, eax
0x180002c55  jnz     short loc_180002C07
0x180002c57  mov     rcx, cs:UmpoHeapHandle; HeapHandle
0x180002c5e  lea     edx, [rax+8]; Flags
0x180002c61  lea     r8d, [rax+58h]; Size
0x180002c65  call    cs:__imp_RtlAllocateHeap
0x180002c6b  mov     rdi, rax
0x180002c6e  test    rax, rax
0x180002c71  jz      loc_180002D79
0x180002c77  mov     dword ptr [rax], 4
0x180002c7d  lea     edx, [rbx+58h]
0x180002c80  mov     dword ptr [rax+8], 1
0x180002c87  mov     rcx, rax
0x180002c8a  movups  xmm0, xmmword ptr cs:GUID_POWER_POLICY_PROFILE_DEFAULT.Data1
0x180002c91  movdqu  xmmword ptr [rax+0Ch], xmm0
0x180002c96  movups  xmm1, xmmword ptr cs:GUID_ACTIVE_POWERSCHEME.Data1
0x180002c9d  movdqu  xmmword ptr [rax+1Ch], xmm1
0x180002ca2  movups  xmm0, xmmword ptr cs:NO_SUBGROUP_GUID.Data1
0x180002ca9  movdqu  xmmword ptr [rax+2Ch], xmm0
0x180002cae  movups  xmm0, xmmword ptr [rbp+var_30.Data1]
0x180002cb2  mov     dword ptr [rax+40h], 10h
0x180002cb9  mov     [rax+3Ch], ebx
0x180002cbc  movdqu  xmmword ptr [rax+44h], xmm0
0x180002cc1  call    UmpoAlpcSendPowerMessage
0x180002cc6  mov     ebx, eax
0x180002cc8  test    eax, eax
0x180002cca  jz      short loc_180002CE3
0x180002ccc  mov     rcx, cs:UmpoHeapHandle; HeapHandle
0x180002cd3  mov     r8, rdi; P
0x180002cd6  xor     edx, edx; Flags
0x180002cd8  call    cs:__imp_RtlFreeHeap
0x180002cde  jmp     loc_180002C07
0x180002ce3  mov     edx, 58h ; 'X'
0x180002ce8  mov     dword ptr [rdi+3Ch], 1
0x180002cef  mov     rcx, rdi
0x180002cf2  call    UmpoAlpcSendPowerMessage
0x180002cf7  mov     ebx, eax
0x180002cf9  test    eax, eax
0x180002cfb  jnz     short loc_180002CCC
0x180002cfd  lea     rax, [rbp+var_30]
0x180002d01  xor     ecx, ecx
0x180002d03  mov     qword ptr [rbp+var_40], rax
0x180002d07  lea     r8, [rbp+var_40]
0x180002d0b  lea     rax, [rbp+Uuid]
0x180002d0f  lea     rdx, UmpoNotifyKernelPowerSettingChangedCallback
0x180002d16  mov     qword ptr [rbp+var_40+8], rax
0x180002d1a  call    UmpoEnumeratePowerSettings
0x180002d1f  jmp     short loc_180002CCC
0x180002d21  call    cs:__imp_GetLastError
0x180002d27  mov     ebx, eax
0x180002d29  jmp     loc_180002C0C
0x180002d2e  cmp     cs:UmpoOverlaySchemeSuspendMask, 0
0x180002d35  mov     [rbp+var_48], 0
0x180002d39  jz      short loc_180002D65
0x180002d3b  lea     rcx, [rbp+var_48]
0x180002d3f  call    UmpoInternalGetPowerModeSchema
0x180002d44  mov     ebx, eax
0x180002d46  test    eax, eax
0x180002d48  jnz     loc_180002C07
0x180002d4e  mov     dl, [rbp+var_48]
0x180002d51  lea     r8, [rbp+Uuid]
0x180002d55  mov     ecx, cs:UmpoOverlaySchemeSuspendMask
0x180002d5b  call    UmpoInternalGetSuspensionPowerMode
0x180002d60  jmp     loc_180002C51
0x180002d65  mov     dl, cs:UmpoOnAcPower
0x180002d6b  lea     rcx, [rbp+Uuid]; Uuid
0x180002d6f  call    UmpoGetActualOverlayScheme
0x180002d74  jmp     loc_180002C51
0x180002d79  mov     ebx, 0Eh
0x180002d7e  jmp     loc_180002C07
```
