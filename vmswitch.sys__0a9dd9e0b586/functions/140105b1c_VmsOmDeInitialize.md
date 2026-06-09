# VmsOmDeInitialize

- ea: `0x140105b1c`
- end: `0x140105e50`
- name: `VmsOmDeInitialize`
- size: `820`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1400a37d8`

## callees

- `0x140027a64`
- `0x14002e0f0`
- `0x14006e100`
- `0x14008497c`
- `0x1400a71f0`
- `0x1400f679c`
- `0x1400fc9e0`
- `0x140105b1c`
- `0x1401bb714`
- `0x1401bbcb0`
- `0x1401bc340`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140105bc2`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140105cb3`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140105bc2`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140105cb3`
- `NDIS!NdisMSleep` at `0x140105d72`
- `NDIS!NdisMSleep` at `0x140105d72`
- `NDIS!NdisReleaseRWLock` at `0x140105bda`
- `NDIS!NdisReleaseRWLock` at `0x140105ccb`
- `NDIS!NdisReleaseRWLock` at `0x140105bda`
- `NDIS!NdisReleaseRWLock` at `0x140105ccb`

## string_xrefs

- `0x140105c69`: `tempNic->Type != VmsNicProtocol`

## pseudocode

```c
__int64 __fastcall VmsOmDeInitialize(__int64 a1, int a2)
{
  __int64 result; // rax
  int v3; // edi
  __int64 v4; // rcx
  __int64 i; // rax
  __int64 v6; // rcx
  int v7; // edx
  __int64 j; // rbx
  int v9; // edx
  struct _LOCK_STATE_EX LockState; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-B8h] BYREF
  struct _UNICODE_STRING v12; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v13[256]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v14[256]; // [rsp+170h] [rbp+70h] BYREF

  result = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  if ( byte_1401FA258 == 1 )
  {
    v3 = 0;
    while ( VmsOmSwitchCount > 0 )
    {
      memset(v13, 0, 0xFEu);
      *(_QWORD *)&DestinationString.Length = 16646144;
      DestinationString.Buffer = (wchar_t *)v13;
      VmsUtilLockShared(v4, &LockState, 0);
      for ( i = VmsOmSwitchList; (__int64 *)i != &VmsOmSwitchList; i = *(_QWORD *)i )
      {
        if ( *(_DWORD *)(i + 68) != 2 )
        {
          RtlCopyUnicodeString(&DestinationString, (PCUNICODE_STRING)(i + 72));
          break;
        }
      }
      NdisReleaseRWLock(VmsOmObjectListLock, &LockState);
      if ( !DestinationString.Length )
        break;
      VmsOmSwitchDelete((__int64)&DestinationString, 0, 0, 0);
    }
    while ( VmsOmNicCount > 0 )
    {
      memset(v14, 0, 0xFEu);
      *(_QWORD *)&v12.Length = 16646144;
      v12.Buffer = (wchar_t *)v14;
      VmsUtilLockShared(v6, &LockState, 0);
      for ( j = VmsOmNicList; (__int64 *)j != &VmsOmNicList; j = *(_QWORD *)j )
      {
        if ( *(_DWORD *)(j + 1872) == 2 )
        {
          WPP_RECORDER_SF_s(
            VmsIfrLog,
            v7,
            19,
            19,
            (__int64)WPP_b611aa96bbb53e16652f3c6e68c2f217_Traceguids,
            (__int64)"tempNic->Type != VmsNicProtocol");
          if ( *(_DWORD *)(j + 1872) == 2 )
            MicrosoftTelemetryAssertTriggeredNoArgsKM();
        }
        if ( *(_DWORD *)(j + 68) != 2 && *(_DWORD *)(j + 1872) == 1 )
        {
          RtlCopyUnicodeString(&v12, (PCUNICODE_STRING)(j + 72));
          break;
        }
      }
      NdisReleaseRWLock(VmsOmObjectListLock, &LockState);
      if ( !v12.Length )
        break;
      VmsMpNicDelete(&v12, 0, 0);
    }
    if ( qword_1401FA1E0 )
    {
      NvIoShutdownWorkerQueue(qword_1401FA1E0);
      qword_1401FA1E0 = 0;
    }
    if ( qword_1401FA1D8 )
    {
      WPP_RECORDER_SF_s(
        VmsIfrLog,
        a2,
        19,
        20,
        (__int64)WPP_b611aa96bbb53e16652f3c6e68c2f217_Traceguids,
        (__int64)"VmsOmCleanupWorkItem == NULL");
      if ( qword_1401FA1D8 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
    }
    while ( 1 )
    {
      if ( VmsOmSwitchCount <= 0 )
      {
        result = (unsigned int)VmsOmNicCount;
        if ( VmsOmNicCount <= 0 )
          break;
      }
      ++v3;
      NdisMSleep(0x61A8u);
      if ( v3 == 200 )
      {
        if ( VmsOmSwitchCount || VmsOmNicCount )
        {
          WPP_RECORDER_SF_s(
            VmsIfrLog,
            v9,
            19,
            21,
            (__int64)WPP_b611aa96bbb53e16652f3c6e68c2f217_Traceguids,
            (__int64)"(VmsOmSwitchCount == 0 && VmsOmNicCount == 0)");
          if ( VmsOmSwitchCount || VmsOmNicCount )
            MicrosoftTelemetryAssertTriggeredNoArgsKM();
        }
        LOBYTE(v9) = 2;
        WPP_RECORDER_SF_ld(
          VmsIfrLog,
          v9,
          20,
          22,
          (__int64)WPP_b611aa96bbb53e16652f3c6e68c2f217_Traceguids,
          VmsOmSwitchCount,
          VmsOmNicCount);
      }
    }
    if ( !VmsIsUnloadForServicing )
    {
      VmsCsKeyDeleteByName(&VmsOmSwitchesConfigKeyStr);
      return VmsCsKeyDeleteByName(&VmsOmNicListConfigKeyStr);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140105b1c  push    rbp
0x140105b1e  push    rbx
0x140105b1f  push    rsi
0x140105b20  push    rdi
0x140105b21  push    r12
0x140105b23  push    r14
0x140105b25  lea     rbp, [rsp-188h]
0x140105b2d  sub     rsp, 288h
0x140105b34  mov     rax, cs:__security_cookie
0x140105b3b  xor     rax, rsp
0x140105b3e  mov     [rbp+1B0h+var_40], rax
0x140105b45  xor     eax, eax
0x140105b47  cmp     cs:byte_1401FA258, 1
0x140105b4e  mov     word ptr [rsp+2B0h+LockState.OldIrql], ax
0x140105b53  mov     [rsp+2B0h+LockState.Flags], al
0x140105b57  jnz     loc_140105E30
0x140105b5d  xor     esi, esi
0x140105b5f  mov     r12d, 0FEh
0x140105b65  mov     edi, esi
0x140105b67  jmp     loc_140105BFF
0x140105b6c  mov     r8, r12; Size
0x140105b6f  lea     rcx, [rsp+2B0h+var_240]; void *
0x140105b74  xor     edx, edx; Val
0x140105b76  call    memset
0x140105b7b  lea     rax, [rsp+2B0h+var_240]
0x140105b80  mov     qword ptr [rsp+2B0h+DestinationString.Length], 0FE0000h
0x140105b89  xor     r8d, r8d
0x140105b8c  mov     [rsp+2B0h+DestinationString.Buffer], rax
0x140105b91  lea     rdx, [rsp+2B0h+LockState]
0x140105b96  call    VmsUtilLockShared
0x140105b9b  mov     rax, cs:VmsOmSwitchList
0x140105ba2  lea     rcx, VmsOmSwitchList
0x140105ba9  cmp     rax, rcx
0x140105bac  jz      short loc_140105BCE
0x140105bae  cmp     dword ptr [rax+44h], 2
0x140105bb2  lea     rdx, [rax+48h]; SourceString
0x140105bb6  jnz     short loc_140105BBD
0x140105bb8  mov     rax, [rax]
0x140105bbb  jmp     short loc_140105BA2
0x140105bbd  lea     rcx, [rsp+2B0h+DestinationString]; DestinationString
0x140105bc2  call    cs:__imp_RtlCopyUnicodeString
0x140105bc9  nop     dword ptr [rax+rax+00h]
0x140105bce  mov     rcx, cs:VmsOmObjectListLock; Lock
0x140105bd5  lea     rdx, [rsp+2B0h+LockState]; LockState
0x140105bda  call    cs:__imp_NdisReleaseRWLock
0x140105be1  nop     dword ptr [rax+rax+00h]
0x140105be6  cmp     [rsp+2B0h+DestinationString.Length], si
0x140105beb  jbe     short loc_140105C0D
0x140105bed  xor     r9d, r9d
0x140105bf0  lea     rcx, [rsp+2B0h+DestinationString]
0x140105bf5  xor     r8d, r8d
0x140105bf8  xor     edx, edx
0x140105bfa  call    VmsOmSwitchDelete
0x140105bff  mov     eax, cs:VmsOmSwitchCount
0x140105c05  test    eax, eax
0x140105c07  jg      loc_140105B6C
0x140105c0d  lea     r14, WPP_b611aa96bbb53e16652f3c6e68c2f217_Traceguids
0x140105c14  jmp     loc_140105CED
0x140105c19  mov     r8, r12; Size
0x140105c1c  lea     rcx, [rbp+1B0h+var_140]; void *
0x140105c20  xor     edx, edx; Val
0x140105c22  call    memset
0x140105c27  lea     rax, [rbp+1B0h+var_140]
0x140105c2b  mov     qword ptr [rsp+2B0h+var_258.Length], 0FE0000h
0x140105c34  xor     r8d, r8d
0x140105c37  mov     [rsp+2B0h+var_258.Buffer], rax
0x140105c3c  lea     rdx, [rsp+2B0h+LockState]
0x140105c41  call    VmsUtilLockShared
0x140105c46  mov     rbx, cs:VmsOmNicList
0x140105c4d  lea     rax, VmsOmNicList
0x140105c54  cmp     rbx, rax
0x140105c57  jz      short loc_140105CBF
0x140105c59  cmp     dword ptr [rbx+750h], 2
0x140105c60  jnz     short loc_140105C96
0x140105c62  mov     rcx, cs:VmsIfrLog
0x140105c69  lea     rax, aTempnicTypeVms; "tempNic->Type != VmsNicProtocol"
0x140105c70  mov     r9d, 13h
0x140105c76  mov     [rsp+2B0h+var_288], rax
0x140105c7b  mov     r8d, r9d
0x140105c7e  mov     [rsp+2B0h+var_290], r14
0x140105c83  call    WPP_RECORDER_SF_s
0x140105c88  cmp     dword ptr [rbx+750h], 2
0x140105c8f  jnz     short loc_140105C96
0x140105c91  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "tempNic->Type != VmsNicProtocol")
0x140105c96  cmp     dword ptr [rbx+44h], 2
0x140105c9a  jz      short loc_140105CA5
0x140105c9c  cmp     dword ptr [rbx+750h], 1
0x140105ca3  jz      short loc_140105CAA
0x140105ca5  mov     rbx, [rbx]
0x140105ca8  jmp     short loc_140105C4D
0x140105caa  lea     rdx, [rbx+48h]; SourceString
0x140105cae  lea     rcx, [rsp+2B0h+var_258]; DestinationString
0x140105cb3  call    cs:__imp_RtlCopyUnicodeString
0x140105cba  nop     dword ptr [rax+rax+00h]
0x140105cbf  mov     rcx, cs:VmsOmObjectListLock; Lock
0x140105cc6  lea     rdx, [rsp+2B0h+LockState]; LockState
0x140105ccb  call    cs:__imp_NdisReleaseRWLock
0x140105cd2  nop     dword ptr [rax+rax+00h]
0x140105cd7  cmp     [rsp+2B0h+var_258.Length], si
0x140105cdc  jbe     short loc_140105CFB
0x140105cde  xor     r8d, r8d
0x140105ce1  lea     rcx, [rsp+2B0h+var_258]
0x140105ce6  xor     edx, edx
0x140105ce8  call    VmsMpNicDelete
0x140105ced  mov     eax, cs:VmsOmNicCount
0x140105cf3  test    eax, eax
0x140105cf5  jg      loc_140105C19
0x140105cfb  mov     rcx, cs:qword_1401FA1E0; void *
0x140105d02  test    rcx, rcx
0x140105d05  jz      short loc_140105D13
0x140105d07  call    NvIoShutdownWorkerQueue
0x140105d0c  mov     cs:qword_1401FA1E0, rsi
0x140105d13  cmp     cs:qword_1401FA1D8, rsi
0x140105d1a  mov     ebx, 14h
0x140105d1f  jz      short loc_140105D53
0x140105d21  mov     rcx, cs:VmsIfrLog
0x140105d28  lea     rax, aVmsomcleanupwo; "VmsOmCleanupWorkItem == NULL"
0x140105d2f  mov     [rsp+2B0h+var_288], rax
0x140105d34  lea     r8d, [rbx-1]
0x140105d38  mov     r9d, ebx
0x140105d3b  mov     [rsp+2B0h+var_290], r14
0x140105d40  call    WPP_RECORDER_SF_s
0x140105d45  cmp     cs:qword_1401FA1D8, rsi
0x140105d4c  jz      short loc_140105D53
0x140105d4e  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "VmsOmCleanupWorkItem == ((void *)0)")
0x140105d53  mov     eax, cs:VmsOmSwitchCount
0x140105d59  test    eax, eax
0x140105d5b  jg      short loc_140105D6B
0x140105d5d  mov     eax, cs:VmsOmNicCount
0x140105d63  test    eax, eax
0x140105d65  jle     loc_140105E0F
0x140105d6b  mov     ecx, 61A8h; MicrosecondsToSleep
0x140105d70  inc     edi
0x140105d72  call    cs:__imp_NdisMSleep
0x140105d79  nop     dword ptr [rax+rax+00h]
0x140105d7e  cmp     edi, 0C8h
0x140105d84  jnz     short loc_140105D53
0x140105d86  mov     eax, cs:VmsOmSwitchCount
0x140105d8c  test    eax, eax
0x140105d8e  jnz     short loc_140105D9A
0x140105d90  mov     eax, cs:VmsOmNicCount
0x140105d96  test    eax, eax
0x140105d98  jz      short loc_140105DDA
0x140105d9a  mov     rcx, cs:VmsIfrLog
0x140105da1  lea     rax, aVmsomswitchcou; "(VmsOmSwitchCount == 0 && VmsOmNicCount"...
0x140105da8  mov     r9d, 15h
0x140105dae  mov     [rsp+2B0h+var_288], rax
0x140105db3  mov     [rsp+2B0h+var_290], r14
0x140105db8  lea     r8d, [r9-2]
0x140105dbc  call    WPP_RECORDER_SF_s
0x140105dc1  mov     eax, cs:VmsOmSwitchCount
0x140105dc7  test    eax, eax
0x140105dc9  jnz     short loc_140105DD5
0x140105dcb  mov     eax, cs:VmsOmNicCount
0x140105dd1  test    eax, eax
0x140105dd3  jz      short loc_140105DDA
0x140105dd5  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "(VmsOmSwitchCount == 0 && VmsOmNicCount == 0)")
0x140105dda  mov     eax, cs:VmsOmNicCount
0x140105de0  mov     r9d, 16h
0x140105de6  mov     [rsp+2B0h+var_280], eax
0x140105dea  mov     r8d, ebx
0x140105ded  mov     eax, cs:VmsOmSwitchCount
0x140105df3  mov     dl, 2
0x140105df5  mov     rcx, cs:VmsIfrLog
0x140105dfc  mov     dword ptr [rsp+2B0h+var_288], eax
0x140105e00  mov     [rsp+2B0h+var_290], r14
0x140105e05  call    WPP_RECORDER_SF_ld
0x140105e0a  jmp     loc_140105D53
0x140105e0f  cmp     cs:VmsIsUnloadForServicing, sil
0x140105e16  jnz     short loc_140105E30
0x140105e18  lea     rcx, VmsOmSwitchesConfigKeyStr
0x140105e1f  call    VmsCsKeyDeleteByName
0x140105e24  lea     rcx, VmsOmNicListConfigKeyStr
0x140105e2b  call    VmsCsKeyDeleteByName
0x140105e30  mov     rcx, [rbp+1B0h+var_40]
0x140105e37  xor     rcx, rsp; StackCookie
0x140105e3a  call    __security_check_cookie
0x140105e3f  add     rsp, 288h
0x140105e46  pop     r14
0x140105e48  pop     r12
0x140105e4a  pop     rdi
0x140105e4b  pop     rsi
0x140105e4c  pop     rbx
0x140105e4d  pop     rbp
0x140105e4e  retn
```
