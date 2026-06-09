# SampCheckRpcRemoteCallerAccess(void *)

- ea: `0x18008d7f8`
- end: `0x18008db5f`
- name: `?SampCheckRpcRemoteCallerAccess@@YAJPEAX@Z`
- size: `871`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18001be80`

## callees

- `0x180027e24`
- `0x180089cd0`
- `0x18008d7f8`
- `0x18008efe4`
- `0x1800b03d0`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18008daf9`
- `ntdll!RtlFreeUnicodeString` at `0x18008daf9`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18008d94e`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18008d94e`
- `ntdll!RtlMapGenericMask` at `0x18008d894`
- `ntdll!RtlMapGenericMask` at `0x18008d894`
- `ntdll!RtlLeaveCriticalSection` at `0x18008dad8`
- `ntdll!RtlLeaveCriticalSection` at `0x18008dad8`
- `ntdll!RtlEnterCriticalSection` at `0x18008d8b8`
- `ntdll!RtlEnterCriticalSection` at `0x18008d8b8`
- `ntdll!RtlInitUnicodeString` at `0x18008d86b`
- `ntdll!RtlInitUnicodeString` at `0x18008d87c`
- `ntdll!RtlInitUnicodeString` at `0x18008d963`
- `ntdll!RtlInitUnicodeString` at `0x18008d975`
- `ntdll!RtlInitUnicodeString` at `0x18008d86b`
- `ntdll!RtlInitUnicodeString` at `0x18008d87c`
- `ntdll!RtlInitUnicodeString` at `0x18008d963`
- `ntdll!RtlInitUnicodeString` at `0x18008d975`
- `ntdll!NtAccessCheckAndAuditAlarm` at `0x18008d913`
- `ntdll!NtAccessCheckAndAuditAlarm` at `0x18008d913`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008dae1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008daea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008dae1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008daea`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18008d9e6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18008da80`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18008d9e6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18008da80`
- `RPCRT4!RpcImpersonateClient` at `0x18008d89d`
- `RPCRT4!RpcImpersonateClient` at `0x18008d89d`
- `RPCRT4!RpcRevertToSelfEx` at `0x18008db07`
- `RPCRT4!RpcRevertToSelfEx` at `0x18008db07`

## string_xrefs

- `0x18008d817`: `Remote access`

## pseudocode

```c
__int64 __fastcall SampCheckRpcRemoteCallerAccess(RPC_BINDING_HANDLE BindingHandle)
{
  int v2; // r14d
  int v3; // r15d
  PSID v4; // rsi
  WCHAR *v5; // rdi
  unsigned int v6; // ebx
  int v7; // eax
  ULONGLONG TickCount64; // r8
  PUNICODE_STRING v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rdx
  unsigned __int64 v12; // rax
  RPC_STATUS v13; // eax
  DWORD GrantedAccess; // [rsp+60h] [rbp-39h] BYREF
  int v16; // [rsp+64h] [rbp-35h] BYREF
  PSID Sid; // [rsp+68h] [rbp-31h] BYREF
  PCWSTR SourceString; // [rsp+70h] [rbp-29h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+78h] [rbp-21h] BYREF
  struct _UNICODE_STRING v20; // [rsp+88h] [rbp-11h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+98h] [rbp-1h] BYREF
  struct _UNICODE_STRING ObjectTypeName; // [rsp+A8h] [rbp+Fh] BYREF
  unsigned __int8 GenerateOnClose; // [rsp+108h] [rbp+6Fh] BYREF
  DWORD AccessMask; // [rsp+110h] [rbp+77h] BYREF
  int AccessStatus; // [rsp+118h] [rbp+7Fh] BYREF

  AccessStatus = 0;
  AccessMask = 0;
  GrantedAccess = 0;
  GenerateOnClose = 0;
  DestinationString = 0;
  v16 = 0;
  v2 = 0;
  ObjectTypeName = 0;
  v3 = 0;
  Sid = 0;
  v4 = 0;
  SourceString = 0;
  v5 = 0;
  *(_QWORD *)&UnicodeString.Length = 0;
  UnicodeString.Buffer = 0;
  *(_QWORD *)&v20.Length = 0;
  v20.Buffer = 0;
  RtlInitUnicodeString(&DestinationString, L"Remote access");
  RtlInitUnicodeString(&ObjectTypeName, L"SAM RPC endpoint");
  AccessMask = 0x20000;
  RtlMapGenericMask(&AccessMask, &RemoteAccessMapping);
  v6 = RpcImpersonateClient(BindingHandle);
  if ( !v6 )
  {
    v2 = 1;
    RtlEnterCriticalSection(&SampRestrictRemoteSessionAccessLock);
    if ( (!SampRestrictRemoteSessionAccess
       || NtAccessCheckAndAuditAlarm(
            &SampSamSubsystem,
            0,
            &ObjectTypeName,
            &DestinationString,
            SampRestrictRemoteSessionAccess,
            AccessMask,
            &RemoteAccessMapping,
            0,
            &GrantedAccess,
            &AccessStatus,
            &GenerateOnClose) >= 0)
      && !AccessStatus )
    {
      goto LABEL_26;
    }
    v7 = QueryRemoteClientInfo((unsigned __int16 **)&SourceString, &v16, &Sid);
    v4 = Sid;
    v5 = (WCHAR *)SourceString;
    if ( v7 >= 0 )
    {
      if ( RtlConvertSidToUnicodeString(&UnicodeString, Sid, 1u) >= 0 )
        v3 = 1;
      else
        RtlInitUnicodeString(&UnicodeString, L"unable to convert");
      RtlInitUnicodeString(&v20, v5);
    }
    if ( RestrictRemoteSamAuditOnlyMode )
    {
      v6 = 0;
      SampWriteEventLog(SAMMSG_REMOTE_SAM_AUDIT_MODE_ENABLED_ACCESS_NOT_DENIED, L"uu", &UnicodeString, &v20);
      v9 = WPP_GLOBAL_Control;
      if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x40) == 0
        || HIBYTE(WPP_GLOBAL_Control[4].Length) < 3u )
      {
        goto LABEL_26;
      }
      v10 = 83;
    }
    else
    {
      v6 = 5;
      if ( RestrictRemoteSamEventThrottlingWindow && PreviousFlushEventTimer )
      {
        TickCount64 = GetTickCount64();
        v11 = ((TickCount64 - PreviousFlushEventTimer) * (unsigned __int128)0x624DD2F1A9FBE77uLL) >> 64;
        if ( (v11 + ((TickCount64 - PreviousFlushEventTimer - v11) >> 1)) >> 9 <= RestrictRemoteSamEventThrottlingWindow )
        {
          v12 = RestrictRemoteSamEventSuppressedEvents + 1;
        }
        else
        {
          _InterlockedExchange64((volatile __int64 *)&PreviousFlushEventTimer, TickCount64);
          SampWriteEventLog(
            SAMMSG_REMOTE_SAM_SUPPRESSED_MESSAGE_COUNTER,
            L"dd",
            RestrictRemoteSamEventThrottlingWindow,
            ++RestrictRemoteSamEventSuppressedEvents);
          v12 = 0;
        }
        v9 = WPP_GLOBAL_Control;
        RestrictRemoteSamEventSuppressedEvents = v12;
        if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x40) == 0
          || HIBYTE(WPP_GLOBAL_Control[4].Length) < 3u )
        {
          goto LABEL_26;
        }
        v10 = 84;
      }
      else
      {
        PreviousFlushEventTimer = GetTickCount64();
        SampWriteEventLog(SAMMSG_REMOTE_SAM_ACCESS_DENIED, L"uu", &UnicodeString, &v20);
        v9 = WPP_GLOBAL_Control;
        if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x40) == 0
          || HIBYTE(WPP_GLOBAL_Control[4].Length) < 3u )
        {
          goto LABEL_26;
        }
        v10 = 85;
      }
    }
    WPP_SF__sid_S(v9[3].Buffer, v10, TickCount64, v4, v5);
LABEL_26:
    RtlLeaveCriticalSection(&SampRestrictRemoteSessionAccessLock);
  }
  LocalFree(v5);
  LocalFree(v4);
  if ( v3 )
    RtlFreeUnicodeString(&UnicodeString);
  if ( v2 )
  {
    v13 = RpcRevertToSelfEx(BindingHandle);
    if ( v13 )
    {
      if ( !v6 )
        v6 = v13;
    }
  }
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 86, WPP_5505de3e48bd33375e96ca021b170945_Traceguids, v6, v6);
  return v6;
}

```

## disassembly

```asm
0x18008d7f8  mov     [rsp-8+arg_0], rbx
0x18008d7fd  push    rbp
0x18008d7fe  push    rsi
0x18008d7ff  push    rdi
0x18008d800  push    r12
0x18008d802  push    r13
0x18008d804  push    r14
0x18008d806  push    r15
0x18008d808  lea     rbp, [rsp-27h]
0x18008d80d  sub     rsp, 0C0h
0x18008d814  xor     r13d, r13d
0x18008d817  lea     rdx, aRemoteAccess; "Remote access"
0x18008d81e  mov     r12, rcx
0x18008d821  mov     [rbp+57h+arg_18], r13d
0x18008d825  xorps   xmm0, xmm0
0x18008d828  mov     [rbp+57h+AccessMask], r13d
0x18008d82c  xorps   xmm1, xmm1
0x18008d82f  mov     [rbp+57h+var_90], r13d
0x18008d833  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18008d837  mov     [rbp+57h+arg_8], r13b
0x18008d83b  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18008d83f  mov     [rbp+57h+var_8C], r13d
0x18008d843  mov     r14d, r13d
0x18008d846  movups  xmmword ptr [rbp+57h+ObjectTypeName.Length], xmm1
0x18008d84a  mov     r15d, r13d
0x18008d84d  mov     [rbp+57h+Sid], r13
0x18008d851  mov     esi, r13d
0x18008d854  mov     [rbp+57h+SourceString], r13
0x18008d858  mov     edi, r13d
0x18008d85b  mov     qword ptr [rbp+57h+UnicodeString.Length], r13
0x18008d85f  mov     [rbp+57h+UnicodeString.Buffer], r13
0x18008d863  mov     qword ptr [rbp+57h+var_68.Length], r13
0x18008d867  mov     [rbp+57h+var_68.Buffer], r13
0x18008d86b  call    cs:__imp_RtlInitUnicodeString
0x18008d871  lea     rdx, aSamRpcEndpoint; "SAM RPC endpoint"
0x18008d878  lea     rcx, [rbp+57h+ObjectTypeName]; DestinationString
0x18008d87c  call    cs:__imp_RtlInitUnicodeString
0x18008d882  lea     rdx, ?RemoteAccessMapping@@3U_GENERIC_MAPPING@@A; GenericMapping
0x18008d889  mov     [rbp+57h+AccessMask], 20000h
0x18008d890  lea     rcx, [rbp+57h+AccessMask]; AccessMask
0x18008d894  call    cs:__imp_RtlMapGenericMask
0x18008d89a  mov     rcx, r12; BindingHandle
0x18008d89d  call    cs:__imp_RpcImpersonateClient
0x18008d8a3  mov     ebx, eax
0x18008d8a5  test    eax, eax
0x18008d8a7  jnz     loc_18008DADE
0x18008d8ad  lea     rcx, ?SampRestrictRemoteSessionAccessLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18008d8b4  lea     r14d, [r13+1]
0x18008d8b8  call    cs:__imp_RtlEnterCriticalSection
0x18008d8be  mov     rcx, cs:?SampRestrictRemoteSessionAccess@@3PEAXEA; void * SampRestrictRemoteSessionAccess
0x18008d8c5  test    rcx, rcx
0x18008d8c8  jz      short loc_18008D91D
0x18008d8ca  lea     rax, [rbp+57h+arg_8]
0x18008d8ce  xor     edx, edx; HandleId
0x18008d8d0  mov     [rsp+0F0h+GenerateOnClose], rax; GenerateOnClose
0x18008d8d5  lea     r9, [rbp+57h+DestinationString]; ObjectName
0x18008d8d9  lea     rax, [rbp+57h+arg_18]
0x18008d8dd  mov     [rsp+0F0h+AccessStatus], rax; AccessStatus
0x18008d8e2  lea     r8, [rbp+57h+ObjectTypeName]; ObjectTypeName
0x18008d8e6  lea     rax, [rbp+57h+var_90]
0x18008d8ea  mov     [rsp+0F0h+GrantedAccess], rax; GrantedAccess
0x18008d8ef  lea     rax, ?RemoteAccessMapping@@3U_GENERIC_MAPPING@@A; _GENERIC_MAPPING RemoteAccessMapping
0x18008d8f6  mov     [rsp+0F0h+ObjectCreation], r13b; ObjectCreation
0x18008d8fb  mov     [rsp+0F0h+GenericMapping], rax; GenericMapping
0x18008d900  mov     eax, [rbp+57h+AccessMask]
0x18008d903  mov     [rsp+0F0h+DesiredAccess], eax; DesiredAccess
0x18008d907  mov     [rsp+0F0h+SecurityDescriptor], rcx; SecurityDescriptor
0x18008d90c  lea     rcx, ?SampSamSubsystem@@3U_UNICODE_STRING@@A; SubsystemName
0x18008d913  call    cs:__imp_NtAccessCheckAndAuditAlarm
0x18008d919  test    eax, eax
0x18008d91b  js      short loc_18008D927
0x18008d91d  cmp     [rbp+57h+arg_18], r13d
0x18008d921  jz      loc_18008DAD1
0x18008d927  lea     r8, [rbp+57h+Sid]; void **
0x18008d92b  lea     rdx, [rbp+57h+var_8C]; int *
0x18008d92f  lea     rcx, [rbp+57h+SourceString]; unsigned __int16 **
0x18008d933  call    ?QueryRemoteClientInfo@@YAJPEAPEAGPEAHPEAPEAX@Z; QueryRemoteClientInfo(ushort * *,int *,void * *)
0x18008d938  mov     rsi, [rbp+57h+Sid]
0x18008d93c  mov     rdi, [rbp+57h+SourceString]
0x18008d940  test    eax, eax
0x18008d942  js      short loc_18008D97B
0x18008d944  mov     r8b, r14b; AllocateDestinationString
0x18008d947  lea     rcx, [rbp+57h+UnicodeString]; UnicodeString
0x18008d94b  mov     rdx, rsi; Sid
0x18008d94e  call    cs:__imp_RtlConvertSidToUnicodeString
0x18008d954  test    eax, eax
0x18008d956  jns     short loc_18008D96B
0x18008d958  lea     rdx, aUnableToConver; "unable to convert"
0x18008d95f  lea     rcx, [rbp+57h+UnicodeString]; DestinationString
0x18008d963  call    cs:__imp_RtlInitUnicodeString
0x18008d969  jmp     short loc_18008D96E
0x18008d96b  mov     r15d, r14d
0x18008d96e  mov     rdx, rdi; SourceString
0x18008d971  lea     rcx, [rbp+57h+var_68]; DestinationString
0x18008d975  call    cs:__imp_RtlInitUnicodeString
0x18008d97b  cmp     cs:?RestrictRemoteSamAuditOnlyMode@@3EA, r13b; uchar RestrictRemoteSamAuditOnlyMode
0x18008d982  jz      short loc_18008D9C7
0x18008d984  lea     r9, [rbp+57h+var_68]
0x18008d988  mov     ebx, r13d
0x18008d98b  lea     r8, [rbp+57h+UnicodeString]
0x18008d98f  lea     rdx, aUu; "uu"
0x18008d996  lea     rcx, SAMMSG_REMOTE_SAM_AUDIT_MODE_ENABLED_ACCESS_NOT_DENIED
0x18008d99d  call    SampWriteEventLog
0x18008d9a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18008d9a9  test    byte ptr [rcx+44h], 40h
0x18008d9ad  jz      loc_18008DAD1
0x18008d9b3  cmp     byte ptr [rcx+41h], 3
0x18008d9b7  jb      loc_18008DAD1
0x18008d9bd  mov     edx, 53h ; 'S'
0x18008d9c2  jmp     loc_18008DAC0
0x18008d9c7  cmp     cs:?RestrictRemoteSamEventThrottlingWindow@@3KA, r13d; ulong RestrictRemoteSamEventThrottlingWindow
0x18008d9ce  mov     ebx, 5
0x18008d9d3  jbe     loc_18008DA80
0x18008d9d9  cmp     cs:?PreviousFlushEventTimer@@3_KA, r13; unsigned __int64 PreviousFlushEventTimer
0x18008d9e0  jbe     loc_18008DA80
0x18008d9e6  call    cs:__imp_GetTickCount64
0x18008d9ec  mov     rcx, rax
0x18008d9ef  mov     r8, rax
0x18008d9f2  sub     rcx, cs:?PreviousFlushEventTimer@@3_KA; unsigned __int64 PreviousFlushEventTimer
0x18008d9f9  mov     rax, 624DD2F1A9FBE77h
0x18008da03  mul     rcx
0x18008da06  mov     eax, cs:?RestrictRemoteSamEventThrottlingWindow@@3KA; ulong RestrictRemoteSamEventThrottlingWindow
0x18008da0c  sub     rcx, rdx
0x18008da0f  shr     rcx, 1
0x18008da12  add     rcx, rdx
0x18008da15  shr     rcx, 9
0x18008da19  cmp     rcx, rax
0x18008da1c  jbe     short loc_18008DA55
0x18008da1e  xchg    r8, cs:?PreviousFlushEventTimer@@3_KA; unsigned __int64 PreviousFlushEventTimer
0x18008da25  mov     r9, cs:?RestrictRemoteSamEventSuppressedEvents@@3_KA; unsigned __int64 RestrictRemoteSamEventSuppressedEvents
0x18008da2c  lea     rdx, aDd; "dd"
0x18008da33  mov     r8d, cs:?RestrictRemoteSamEventThrottlingWindow@@3KA; ulong RestrictRemoteSamEventThrottlingWindow
0x18008da3a  lea     rcx, SAMMSG_REMOTE_SAM_SUPPRESSED_MESSAGE_COUNTER
0x18008da41  add     r9, r14
0x18008da44  mov     cs:?RestrictRemoteSamEventSuppressedEvents@@3_KA, r9; unsigned __int64 RestrictRemoteSamEventSuppressedEvents
0x18008da4b  call    SampWriteEventLog
0x18008da50  mov     rax, r13
0x18008da53  jmp     short loc_18008DA5F
0x18008da55  mov     rax, cs:?RestrictRemoteSamEventSuppressedEvents@@3_KA; unsigned __int64 RestrictRemoteSamEventSuppressedEvents
0x18008da5c  inc     rax
0x18008da5f  mov     rcx, cs:WPP_GLOBAL_Control
0x18008da66  mov     cs:?RestrictRemoteSamEventSuppressedEvents@@3_KA, rax; unsigned __int64 RestrictRemoteSamEventSuppressedEvents
0x18008da6d  test    byte ptr [rcx+44h], 40h
0x18008da71  jz      short loc_18008DAD1
0x18008da73  cmp     byte ptr [rcx+41h], 3
0x18008da77  jb      short loc_18008DAD1
0x18008da79  mov     edx, 54h ; 'T'
0x18008da7e  jmp     short loc_18008DAC0
0x18008da80  call    cs:__imp_GetTickCount64
0x18008da86  lea     r9, [rbp+57h+var_68]
0x18008da8a  mov     cs:?PreviousFlushEventTimer@@3_KA, rax; unsigned __int64 PreviousFlushEventTimer
0x18008da91  lea     r8, [rbp+57h+UnicodeString]
0x18008da95  lea     rdx, aUu; "uu"
0x18008da9c  lea     rcx, SAMMSG_REMOTE_SAM_ACCESS_DENIED
0x18008daa3  call    SampWriteEventLog
0x18008daa8  mov     rcx, cs:WPP_GLOBAL_Control
0x18008daaf  test    byte ptr [rcx+44h], 40h
0x18008dab3  jz      short loc_18008DAD1
0x18008dab5  cmp     byte ptr [rcx+41h], 3
0x18008dab9  jb      short loc_18008DAD1
0x18008dabb  mov     edx, 55h ; 'U'
0x18008dac0  mov     rcx, [rcx+38h]
0x18008dac4  mov     r9, rsi
0x18008dac7  mov     [rsp+0F0h+SecurityDescriptor], rdi
0x18008dacc  call    WPP_SF__sid_S
0x18008dad1  lea     rcx, ?SampRestrictRemoteSessionAccessLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18008dad8  call    cs:__imp_RtlLeaveCriticalSection
0x18008dade  mov     rcx, rdi; hMem
0x18008dae1  call    cs:__imp_LocalFree
0x18008dae7  mov     rcx, rsi; hMem
0x18008daea  call    cs:__imp_LocalFree
0x18008daf0  test    r15d, r15d
0x18008daf3  jz      short loc_18008DAFF
0x18008daf5  lea     rcx, [rbp+57h+UnicodeString]; UnicodeString
0x18008daf9  call    cs:__imp_RtlFreeUnicodeString
0x18008daff  test    r14d, r14d
0x18008db02  jz      short loc_18008DB16
0x18008db04  mov     rcx, r12; BindingHandle
0x18008db07  call    cs:__imp_RpcRevertToSelfEx
0x18008db0d  test    eax, eax
0x18008db0f  jz      short loc_18008DB16
0x18008db11  test    ebx, ebx
0x18008db13  cmovz   ebx, eax
0x18008db16  mov     rcx, cs:WPP_GLOBAL_Control
0x18008db1d  test    dword ptr [rcx+44h], 20000h
0x18008db24  jz      short loc_18008DB42
0x18008db26  mov     rcx, [rcx+38h]
0x18008db2a  lea     r8, WPP_5505de3e48bd33375e96ca021b170945_Traceguids
0x18008db31  mov     edx, 56h ; 'V'
0x18008db36  mov     dword ptr [rsp+0F0h+SecurityDescriptor], ebx
0x18008db3a  mov     r9d, ebx
0x18008db3d  call    WPP_SF_Dd
0x18008db42  mov     eax, ebx
0x18008db44  mov     rbx, [rsp+0F0h+arg_0]
0x18008db4c  add     rsp, 0C0h
0x18008db53  pop     r15
0x18008db55  pop     r14
0x18008db57  pop     r13
0x18008db59  pop     r12
0x18008db5b  pop     rdi
0x18008db5c  pop     rsi
0x18008db5d  pop     rbp
0x18008db5e  retn
```
