# VmsOmDeInitialize

- ea: `0x140105aac`
- end: `0x140105de0`
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
- `0x1400a7180`
- `0x1400f672c`
- `0x1400fc970`
- `0x140105aac`
- `0x1401bb6a4`
- `0x1401bbc40`
- `0x1401bc2c0`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140105b52`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140105c43`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140105b52`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140105c43`
- `NDIS!NdisMSleep` at `0x140105d02`
- `NDIS!NdisMSleep` at `0x140105d02`
- `NDIS!NdisReleaseRWLock` at `0x140105b6a`
- `NDIS!NdisReleaseRWLock` at `0x140105c5b`
- `NDIS!NdisReleaseRWLock` at `0x140105b6a`
- `NDIS!NdisReleaseRWLock` at `0x140105c5b`

## string_xrefs

- `0x140105bf9`: `tempNic->Type != VmsNicProtocol`

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
  if ( byte_1401FA1D8 == 1 )
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
    if ( qword_1401FA1E8 )
    {
      NvIoShutdownWorkerQueue(qword_1401FA1E8);
      qword_1401FA1E8 = 0;
    }
    if ( qword_1401FA1E0 )
    {
      WPP_RECORDER_SF_s(
        VmsIfrLog,
        a2,
        19,
        20,
        (__int64)WPP_b611aa96bbb53e16652f3c6e68c2f217_Traceguids,
        (__int64)"VmsOmCleanupWorkItem == NULL");
      if ( qword_1401FA1E0 )
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
0x140105aac  push    rbp
0x140105aae  push    rbx
0x140105aaf  push    rsi
0x140105ab0  push    rdi
0x140105ab1  push    r12
0x140105ab3  push    r14
0x140105ab5  lea     rbp, [rsp-188h]
0x140105abd  sub     rsp, 288h
0x140105ac4  mov     rax, cs:__security_cookie
0x140105acb  xor     rax, rsp
0x140105ace  mov     [rbp+1B0h+var_40], rax
0x140105ad5  xor     eax, eax
0x140105ad7  cmp     cs:byte_1401FA1D8, 1
0x140105ade  mov     word ptr [rsp+2B0h+LockState.OldIrql], ax
0x140105ae3  mov     [rsp+2B0h+LockState.Flags], al
0x140105ae7  jnz     loc_140105DC0
0x140105aed  xor     esi, esi
0x140105aef  mov     r12d, 0FEh
0x140105af5  mov     edi, esi
0x140105af7  jmp     loc_140105B8F
0x140105afc  mov     r8, r12; Size
0x140105aff  lea     rcx, [rsp+2B0h+var_240]; void *
0x140105b04  xor     edx, edx; Val
0x140105b06  call    memset
0x140105b0b  lea     rax, [rsp+2B0h+var_240]
0x140105b10  mov     qword ptr [rsp+2B0h+DestinationString.Length], 0FE0000h
0x140105b19  xor     r8d, r8d
0x140105b1c  mov     [rsp+2B0h+DestinationString.Buffer], rax
0x140105b21  lea     rdx, [rsp+2B0h+LockState]
0x140105b26  call    VmsUtilLockShared
0x140105b2b  mov     rax, cs:VmsOmSwitchList
0x140105b32  lea     rcx, VmsOmSwitchList
0x140105b39  cmp     rax, rcx
0x140105b3c  jz      short loc_140105B5E
0x140105b3e  cmp     dword ptr [rax+44h], 2
0x140105b42  lea     rdx, [rax+48h]; SourceString
0x140105b46  jnz     short loc_140105B4D
0x140105b48  mov     rax, [rax]
0x140105b4b  jmp     short loc_140105B32
0x140105b4d  lea     rcx, [rsp+2B0h+DestinationString]; DestinationString
0x140105b52  call    cs:__imp_RtlCopyUnicodeString
0x140105b59  nop     dword ptr [rax+rax+00h]
0x140105b5e  mov     rcx, cs:VmsOmObjectListLock; Lock
0x140105b65  lea     rdx, [rsp+2B0h+LockState]; LockState
0x140105b6a  call    cs:__imp_NdisReleaseRWLock
0x140105b71  nop     dword ptr [rax+rax+00h]
0x140105b76  cmp     [rsp+2B0h+DestinationString.Length], si
0x140105b7b  jbe     short loc_140105B9D
0x140105b7d  xor     r9d, r9d
0x140105b80  lea     rcx, [rsp+2B0h+DestinationString]
0x140105b85  xor     r8d, r8d
0x140105b88  xor     edx, edx
0x140105b8a  call    VmsOmSwitchDelete
0x140105b8f  mov     eax, cs:VmsOmSwitchCount
0x140105b95  test    eax, eax
0x140105b97  jg      loc_140105AFC
0x140105b9d  lea     r14, WPP_b611aa96bbb53e16652f3c6e68c2f217_Traceguids
0x140105ba4  jmp     loc_140105C7D
0x140105ba9  mov     r8, r12; Size
0x140105bac  lea     rcx, [rbp+1B0h+var_140]; void *
0x140105bb0  xor     edx, edx; Val
0x140105bb2  call    memset
0x140105bb7  lea     rax, [rbp+1B0h+var_140]
0x140105bbb  mov     qword ptr [rsp+2B0h+var_258.Length], 0FE0000h
0x140105bc4  xor     r8d, r8d
0x140105bc7  mov     [rsp+2B0h+var_258.Buffer], rax
0x140105bcc  lea     rdx, [rsp+2B0h+LockState]
0x140105bd1  call    VmsUtilLockShared
0x140105bd6  mov     rbx, cs:VmsOmNicList
0x140105bdd  lea     rax, VmsOmNicList
0x140105be4  cmp     rbx, rax
0x140105be7  jz      short loc_140105C4F
0x140105be9  cmp     dword ptr [rbx+750h], 2
0x140105bf0  jnz     short loc_140105C26
0x140105bf2  mov     rcx, cs:VmsIfrLog
0x140105bf9  lea     rax, aTempnicTypeVms; "tempNic->Type != VmsNicProtocol"
0x140105c00  mov     r9d, 13h
0x140105c06  mov     [rsp+2B0h+var_288], rax
0x140105c0b  mov     r8d, r9d
0x140105c0e  mov     [rsp+2B0h+var_290], r14
0x140105c13  call    WPP_RECORDER_SF_s
0x140105c18  cmp     dword ptr [rbx+750h], 2
0x140105c1f  jnz     short loc_140105C26
0x140105c21  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "tempNic->Type != VmsNicProtocol")
0x140105c26  cmp     dword ptr [rbx+44h], 2
0x140105c2a  jz      short loc_140105C35
0x140105c2c  cmp     dword ptr [rbx+750h], 1
0x140105c33  jz      short loc_140105C3A
0x140105c35  mov     rbx, [rbx]
0x140105c38  jmp     short loc_140105BDD
0x140105c3a  lea     rdx, [rbx+48h]; SourceString
0x140105c3e  lea     rcx, [rsp+2B0h+var_258]; DestinationString
0x140105c43  call    cs:__imp_RtlCopyUnicodeString
0x140105c4a  nop     dword ptr [rax+rax+00h]
0x140105c4f  mov     rcx, cs:VmsOmObjectListLock; Lock
0x140105c56  lea     rdx, [rsp+2B0h+LockState]; LockState
0x140105c5b  call    cs:__imp_NdisReleaseRWLock
0x140105c62  nop     dword ptr [rax+rax+00h]
0x140105c67  cmp     [rsp+2B0h+var_258.Length], si
0x140105c6c  jbe     short loc_140105C8B
0x140105c6e  xor     r8d, r8d
0x140105c71  lea     rcx, [rsp+2B0h+var_258]
0x140105c76  xor     edx, edx
0x140105c78  call    VmsMpNicDelete
0x140105c7d  mov     eax, cs:VmsOmNicCount
0x140105c83  test    eax, eax
0x140105c85  jg      loc_140105BA9
0x140105c8b  mov     rcx, cs:qword_1401FA1E8; void *
0x140105c92  test    rcx, rcx
0x140105c95  jz      short loc_140105CA3
0x140105c97  call    NvIoShutdownWorkerQueue
0x140105c9c  mov     cs:qword_1401FA1E8, rsi
0x140105ca3  cmp     cs:qword_1401FA1E0, rsi
0x140105caa  mov     ebx, 14h
0x140105caf  jz      short loc_140105CE3
0x140105cb1  mov     rcx, cs:VmsIfrLog
0x140105cb8  lea     rax, aVmsomcleanupwo; "VmsOmCleanupWorkItem == NULL"
0x140105cbf  mov     [rsp+2B0h+var_288], rax
0x140105cc4  lea     r8d, [rbx-1]
0x140105cc8  mov     r9d, ebx
0x140105ccb  mov     [rsp+2B0h+var_290], r14
0x140105cd0  call    WPP_RECORDER_SF_s
0x140105cd5  cmp     cs:qword_1401FA1E0, rsi
0x140105cdc  jz      short loc_140105CE3
0x140105cde  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "VmsOmCleanupWorkItem == ((void *)0)")
0x140105ce3  mov     eax, cs:VmsOmSwitchCount
0x140105ce9  test    eax, eax
0x140105ceb  jg      short loc_140105CFB
0x140105ced  mov     eax, cs:VmsOmNicCount
0x140105cf3  test    eax, eax
0x140105cf5  jle     loc_140105D9F
0x140105cfb  mov     ecx, 61A8h; MicrosecondsToSleep
0x140105d00  inc     edi
0x140105d02  call    cs:__imp_NdisMSleep
0x140105d09  nop     dword ptr [rax+rax+00h]
0x140105d0e  cmp     edi, 0C8h
0x140105d14  jnz     short loc_140105CE3
0x140105d16  mov     eax, cs:VmsOmSwitchCount
0x140105d1c  test    eax, eax
0x140105d1e  jnz     short loc_140105D2A
0x140105d20  mov     eax, cs:VmsOmNicCount
0x140105d26  test    eax, eax
0x140105d28  jz      short loc_140105D6A
0x140105d2a  mov     rcx, cs:VmsIfrLog
0x140105d31  lea     rax, aVmsomswitchcou; "(VmsOmSwitchCount == 0 && VmsOmNicCount"...
0x140105d38  mov     r9d, 15h
0x140105d3e  mov     [rsp+2B0h+var_288], rax
0x140105d43  mov     [rsp+2B0h+var_290], r14
0x140105d48  lea     r8d, [r9-2]
0x140105d4c  call    WPP_RECORDER_SF_s
0x140105d51  mov     eax, cs:VmsOmSwitchCount
0x140105d57  test    eax, eax
0x140105d59  jnz     short loc_140105D65
0x140105d5b  mov     eax, cs:VmsOmNicCount
0x140105d61  test    eax, eax
0x140105d63  jz      short loc_140105D6A
0x140105d65  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "(VmsOmSwitchCount == 0 && VmsOmNicCount == 0)")
0x140105d6a  mov     eax, cs:VmsOmNicCount
0x140105d70  mov     r9d, 16h
0x140105d76  mov     [rsp+2B0h+var_280], eax
0x140105d7a  mov     r8d, ebx
0x140105d7d  mov     eax, cs:VmsOmSwitchCount
0x140105d83  mov     dl, 2
0x140105d85  mov     rcx, cs:VmsIfrLog
0x140105d8c  mov     dword ptr [rsp+2B0h+var_288], eax
0x140105d90  mov     [rsp+2B0h+var_290], r14
0x140105d95  call    WPP_RECORDER_SF_ld
0x140105d9a  jmp     loc_140105CE3
0x140105d9f  cmp     cs:VmsIsUnloadForServicing, sil
0x140105da6  jnz     short loc_140105DC0
0x140105da8  lea     rcx, VmsOmSwitchesConfigKeyStr
0x140105daf  call    VmsCsKeyDeleteByName
0x140105db4  lea     rcx, VmsOmNicListConfigKeyStr
0x140105dbb  call    VmsCsKeyDeleteByName
0x140105dc0  mov     rcx, [rbp+1B0h+var_40]
0x140105dc7  xor     rcx, rsp; StackCookie
0x140105dca  call    __security_check_cookie
0x140105dcf  add     rsp, 288h
0x140105dd6  pop     r14
0x140105dd8  pop     r12
0x140105dda  pop     rdi
0x140105ddb  pop     rsi
0x140105ddc  pop     rbx
0x140105ddd  pop     rbp
0x140105dde  retn
```
