# SampLogLegacyRpcMethodAuditEvent(_UNICODE_STRING *,_UNICODE_STRING *)

- ea: `0x1800a0da0`
- end: `0x1800a0f3c`
- name: `?SampLogLegacyRpcMethodAuditEvent@@YAXPEAU_UNICODE_STRING@@0@Z`
- size: `412`
- prototype: `void __fastcall(struct _UNICODE_STRING *, struct _UNICODE_STRING *)`
- caller_count: `5`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x1800291c0`
- `0x1800a5e40`
- `0x1800a71e0`
- `0x1800a76d0`
- `0x1800a7940`

## callees

- `0x180023ebc`
- `0x180089cd0`
- `0x1800a0da0`
- `0x1800b03d0`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x1800a0f22`
- `ntdll!RtlFreeUnicodeString` at `0x1800a0f22`
- `ntdll!RtlConvertSidToUnicodeString` at `0x1800a0e8d`
- `ntdll!RtlConvertSidToUnicodeString` at `0x1800a0e8d`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a0ef8`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a0ef8`
- `ntdll!RtlEnterCriticalSection` at `0x1800a0dfc`
- `ntdll!RtlEnterCriticalSection` at `0x1800a0dfc`
- `ntdll!RtlInitUnicodeString` at `0x1800a0ea2`
- `ntdll!RtlInitUnicodeString` at `0x1800a0eba`
- `ntdll!RtlInitUnicodeString` at `0x1800a0ea2`
- `ntdll!RtlInitUnicodeString` at `0x1800a0eba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a0f06`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a0f14`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a0f06`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a0f14`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800a0e0a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800a0e0a`

## string_xrefs

- `0x1800a0e97`: `Could not convert SID.`

## pseudocode

```c
void __fastcall SampLogLegacyRpcMethodAuditEvent(struct _UNICODE_STRING *a1, struct _UNICODE_STRING *a2)
{
  PSID v2; // rbx
  WCHAR *v4; // rdi
  int IsClientUsingLRPC; // eax
  int v7; // esi
  ULONGLONG TickCount64; // rax
  int v9; // eax
  PCWSTR SourceString; // [rsp+30h] [rbp-30h] BYREF
  PSID Sid; // [rsp+38h] [rbp-28h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+40h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-10h] BYREF
  int v14; // [rsp+A0h] [rbp+40h] BYREF
  int v15; // [rsp+A8h] [rbp+48h] BYREF

  v2 = 0;
  Sid = 0;
  v15 = 0;
  v4 = 0;
  v14 = 0;
  SourceString = 0;
  UnicodeString = 0;
  DestinationString = 0;
  IsClientUsingLRPC = QueryIsClientUsingLRPC(&v14);
  if ( !v14 && IsClientUsingLRPC >= 0 )
  {
    v7 = 0;
    RtlEnterCriticalSection(&gcsLegacyPwdMethodSettingsLock);
    if ( SamRpcLegacyPwdMethodAudit )
    {
      v9 = QueryRemoteClientInfo((unsigned __int16 **)&SourceString, &v15, &Sid);
      v2 = Sid;
      if ( v9 < 0 )
      {
        v4 = (WCHAR *)SourceString;
      }
      else
      {
        if ( RtlConvertSidToUnicodeString(&UnicodeString, Sid, 1u) >= 0 )
          v7 = 1;
        else
          RtlInitUnicodeString(&UnicodeString, L"Could not convert SID.");
        v4 = (WCHAR *)SourceString;
        RtlInitUnicodeString(&DestinationString, SourceString);
        SampWriteEventLog(SAMMSG_AUDIT_LEGACY_PWD_RPC_METHODS_VERBOSE, L"uuuu", a1, a2);
      }
    }
    else
    {
      TickCount64 = GetTickCount64();
      if ( TickCount64 - SamRpcLegacyPwdMethodFlushEventTimer < 0x36F268 )
      {
        ++SamRpcLegacyPwdMethodSuppressedEvents;
      }
      else
      {
        _InterlockedExchange64((volatile __int64 *)&SamRpcLegacyPwdMethodFlushEventTimer, TickCount64);
        SampWriteEventLog(
          SAMMSG_AUDIT_LEGACY_PWD_RPC_METHODS_SUMMARY,
          L"dd",
          ++SamRpcLegacyPwdMethodSuppressedEvents,
          60);
        SamRpcLegacyPwdMethodSuppressedEvents = 0;
      }
    }
    RtlLeaveCriticalSection(&gcsLegacyPwdMethodSettingsLock);
    if ( v4 )
      LocalFree(v4);
    if ( v2 )
      LocalFree(v2);
    if ( v7 )
      RtlFreeUnicodeString(&UnicodeString);
  }
}

```

## disassembly

```asm
0x1800a0da0  mov     [rsp-28h+arg_0], rbx
0x1800a0da5  push    rbp
0x1800a0da6  push    rsi
0x1800a0da7  push    rdi
0x1800a0da8  push    r14
0x1800a0daa  push    r15
0x1800a0dac  mov     rbp, rsp
0x1800a0daf  sub     rsp, 60h
0x1800a0db3  xor     ebx, ebx
0x1800a0db5  mov     r15, rcx
0x1800a0db8  xorps   xmm0, xmm0
0x1800a0dbb  mov     [rbp+Sid], rbx
0x1800a0dbf  xorps   xmm1, xmm1
0x1800a0dc2  mov     [rbp+arg_18], ebx
0x1800a0dc5  xor     edi, edi
0x1800a0dc7  mov     [rbp+arg_10], ebx
0x1800a0dca  lea     rcx, [rbp+arg_10]; int *
0x1800a0dce  mov     [rbp+SourceString], rdi
0x1800a0dd2  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x1800a0dd6  mov     r14, rdx
0x1800a0dd9  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x1800a0ddd  call    ?QueryIsClientUsingLRPC@@YAJPEAH@Z; QueryIsClientUsingLRPC(int *)
0x1800a0de2  cmp     [rbp+arg_10], ebx
0x1800a0de5  jnz     loc_1800A0F28
0x1800a0deb  test    eax, eax
0x1800a0ded  js      loc_1800A0F28
0x1800a0df3  lea     rcx, ?gcsLegacyPwdMethodSettingsLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x1800a0dfa  xor     esi, esi
0x1800a0dfc  call    cs:__imp_RtlEnterCriticalSection
0x1800a0e02  cmp     cs:?SamRpcLegacyPwdMethodAudit@@3EA, bl; uchar SamRpcLegacyPwdMethodAudit
0x1800a0e08  jnz     short loc_1800A0E6A
0x1800a0e0a  call    cs:__imp_GetTickCount64
0x1800a0e10  mov     rcx, rax
0x1800a0e13  sub     rcx, cs:?SamRpcLegacyPwdMethodFlushEventTimer@@3_KA; unsigned __int64 SamRpcLegacyPwdMethodFlushEventTimer
0x1800a0e1a  cmp     rcx, 36F268h
0x1800a0e21  jb      short loc_1800A0E5E
0x1800a0e23  xchg    rax, cs:?SamRpcLegacyPwdMethodFlushEventTimer@@3_KA; unsigned __int64 SamRpcLegacyPwdMethodFlushEventTimer
0x1800a0e2a  mov     r8, cs:?SamRpcLegacyPwdMethodSuppressedEvents@@3_KA; unsigned __int64 SamRpcLegacyPwdMethodSuppressedEvents
0x1800a0e31  lea     r9d, [rdi+3Ch]
0x1800a0e35  inc     r8
0x1800a0e38  lea     rdx, aDd; "dd"
0x1800a0e3f  lea     rcx, SAMMSG_AUDIT_LEGACY_PWD_RPC_METHODS_SUMMARY
0x1800a0e46  mov     cs:?SamRpcLegacyPwdMethodSuppressedEvents@@3_KA, r8; unsigned __int64 SamRpcLegacyPwdMethodSuppressedEvents
0x1800a0e4d  call    SampWriteEventLog
0x1800a0e52  mov     cs:?SamRpcLegacyPwdMethodSuppressedEvents@@3_KA, rbx; unsigned __int64 SamRpcLegacyPwdMethodSuppressedEvents
0x1800a0e59  jmp     loc_1800A0EF1
0x1800a0e5e  inc     cs:?SamRpcLegacyPwdMethodSuppressedEvents@@3_KA; unsigned __int64 SamRpcLegacyPwdMethodSuppressedEvents
0x1800a0e65  jmp     loc_1800A0EF1
0x1800a0e6a  lea     r8, [rbp+Sid]; void **
0x1800a0e6e  lea     rdx, [rbp+arg_18]; int *
0x1800a0e72  lea     rcx, [rbp+SourceString]; unsigned __int16 **
0x1800a0e76  call    ?QueryRemoteClientInfo@@YAJPEAPEAGPEAHPEAPEAX@Z; QueryRemoteClientInfo(ushort * *,int *,void * *)
0x1800a0e7b  mov     rbx, [rbp+Sid]
0x1800a0e7f  test    eax, eax
0x1800a0e81  js      short loc_1800A0EED
0x1800a0e83  mov     r8b, 1; AllocateDestinationString
0x1800a0e86  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x1800a0e8a  mov     rdx, rbx; Sid
0x1800a0e8d  call    cs:__imp_RtlConvertSidToUnicodeString
0x1800a0e93  test    eax, eax
0x1800a0e95  jns     short loc_1800A0EAA
0x1800a0e97  lea     rdx, aCouldNotConver; "Could not convert SID."
0x1800a0e9e  lea     rcx, [rbp+UnicodeString]; DestinationString
0x1800a0ea2  call    cs:__imp_RtlInitUnicodeString
0x1800a0ea8  jmp     short loc_1800A0EAF
0x1800a0eaa  mov     esi, 1
0x1800a0eaf  mov     rdi, [rbp+SourceString]
0x1800a0eb3  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800a0eb7  mov     rdx, rdi; SourceString
0x1800a0eba  call    cs:__imp_RtlInitUnicodeString
0x1800a0ec0  lea     rax, [rbp+DestinationString]
0x1800a0ec4  mov     r9, r14
0x1800a0ec7  mov     [rsp+60h+var_38], rax
0x1800a0ecc  lea     rdx, aUuuu; "uuuu"
0x1800a0ed3  lea     rax, [rbp+UnicodeString]
0x1800a0ed7  mov     r8, r15
0x1800a0eda  lea     rcx, SAMMSG_AUDIT_LEGACY_PWD_RPC_METHODS_VERBOSE
0x1800a0ee1  mov     [rsp+60h+var_40], rax
0x1800a0ee6  call    SampWriteEventLog
0x1800a0eeb  jmp     short loc_1800A0EF1
0x1800a0eed  mov     rdi, [rbp+SourceString]
0x1800a0ef1  lea     rcx, ?gcsLegacyPwdMethodSettingsLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x1800a0ef8  call    cs:__imp_RtlLeaveCriticalSection
0x1800a0efe  test    rdi, rdi
0x1800a0f01  jz      short loc_1800A0F0C
0x1800a0f03  mov     rcx, rdi; hMem
0x1800a0f06  call    cs:__imp_LocalFree
0x1800a0f0c  test    rbx, rbx
0x1800a0f0f  jz      short loc_1800A0F1A
0x1800a0f11  mov     rcx, rbx; hMem
0x1800a0f14  call    cs:__imp_LocalFree
0x1800a0f1a  test    esi, esi
0x1800a0f1c  jz      short loc_1800A0F28
0x1800a0f1e  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x1800a0f22  call    cs:__imp_RtlFreeUnicodeString
0x1800a0f28  mov     rbx, [rsp+60h+arg_0]
0x1800a0f30  add     rsp, 60h
0x1800a0f34  pop     r15
0x1800a0f36  pop     r14
0x1800a0f38  pop     rdi
0x1800a0f39  pop     rsi
0x1800a0f3a  pop     rbp
0x1800a0f3b  retn
```
