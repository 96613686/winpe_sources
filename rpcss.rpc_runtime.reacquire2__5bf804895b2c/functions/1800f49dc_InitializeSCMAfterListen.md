# InitializeSCMAfterListen

- ea: `0x1800f49dc`
- end: `0x1800f4c11`
- name: `InitializeSCMAfterListen`
- size: `565`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800bd340`

## callees

- `0x180034260`
- `0x18008172c`
- `0x1800a7388`
- `0x1800b7ac0`
- `0x1800f44dc`
- `0x1800f49dc`

## import_xrefs

- `RPCRT4!RpcMgmtEnableIdleCleanup` at `0x1800f4b9f`
- `RPCRT4!RpcMgmtEnableIdleCleanup` at `0x1800f4b9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f4aad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f4af8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f4b69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f4aad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f4af8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f4b69`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800f4a9c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800f4a9c`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800f4aca`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800f4aca`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800f4b2e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800f4b2e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800f4a57`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800f4a57`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800f4b3e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800f4b3e`

## string_xrefs

- `0x1800f4b1d`: `onecore\com\combase\rpcss\olescm\scmsvc.cxx`
- `0x1800f4b8e`: `onecore\com\combase\rpcss\olescm\scmsvc.cxx`
- `0x1800f4be7`: `onecore\com\combase\rpcss\olescm\scmsvc.cxx`
- `0x1800f4a76`: `ScmCreatedEvent`
- `0x1800f4abe`: `ScmCreatedEvent`

## pseudocode

```c
RPC_STATUS InitializeSCMAfterListen()
{
  HANDLE v0; // rax
  RPC_STATUS result; // eax
  RPC_STATUS v2; // r8d
  __int64 v3; // [rsp+28h] [rbp-41h]
  DWORD LastError; // [rsp+28h] [rbp-41h]
  DWORD v5; // [rsp+28h] [rbp-41h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+30h] [rbp-39h] BYREF
  struct _SECURITY_ATTRIBUTES EventAttributes; // [rsp+38h] [rbp-31h] BYREF
  WCHAR StringSecurityDescriptor[48]; // [rsp+50h] [rbp-19h] BYREF

  wcscpy(StringSecurityDescriptor, L"D:(A;;0x00120001;;;WD)(A;;0x001C0002;;PS)");
  SecurityDescriptor = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &SecurityDescriptor, 0) )
  {
    *(_QWORD *)&EventAttributes.nLength = 24;
    *(_QWORD *)&EventAttributes.bInheritHandle = 0;
    EventAttributes.lpSecurityDescriptor = SecurityDescriptor;
    v0 = CreateEventW(&EventAttributes, 1, 0, L"ScmCreatedEvent");
    if ( v0 || GetLastError() == 5 && (v0 = OpenEventW(2u, 0, L"ScmCreatedEvent")) != 0 )
    {
      SetEvent(v0);
    }
    else if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
    {
      LastError = GetLastError();
      ComTraceMessageT<int>(
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\scmsvc.cxx",
        (unsigned int)"InitializeSCMAfterListen",
        784,
        0,
        (__int64)L"%!WINERROR!",
        LastError);
    }
    LocalFree(SecurityDescriptor);
  }
  else if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
  {
    v5 = GetLastError();
    ComTraceMessageT<int>(
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\scmsvc.cxx",
      (unsigned int)"InitializeSCMAfterListen",
      792,
      0,
      (__int64)L"%!WINERROR!",
      v5);
  }
  InitializeVistaEventIfNeeded();
  result = RpcMgmtEnableIdleCleanup();
  v2 = result;
  if ( result )
  {
    if ( dword_1801574B8
      || gfEnableTracing && (result = IsWppLevelEnabled((unsigned int)dword_1801574B8), (_BYTE)result) )
    {
      LODWORD(v3) = v2;
      return ComTraceMessageT<long>(
               (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\scmsvc.cxx",
               (unsigned int)"InitializeSCMAfterListen",
               804,
               0,
               (__int64)L"%!WINERROR!",
               v3);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800f49dc  mov     [rsp-8+arg_0], r14
0x1800f49e1  push    rbp
0x1800f49e2  lea     rbp, [rsp-57h]
0x1800f49e7  sub     rsp, 0C0h
0x1800f49ee  mov     rax, cs:__security_cookie
0x1800f49f5  xor     rax, rsp
0x1800f49f8  mov     [rbp+57h+var_10], rax
0x1800f49fc  movaps  xmm0, xmmword ptr cs:aDA0x00120001Wd; "D:(A;;0x00120001;;;WD)(A;;0x001C0002;;;"...
0x1800f4a03  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1800f4a07  movaps  xmm1, xmmword ptr cs:aDA0x00120001Wd+10h; "00120001;;;WD)(A;;0x001C0002;;;PS)"
0x1800f4a0e  lea     rcx, [rbp+57h+StringSecurityDescriptor]; StringSecurityDescriptor
0x1800f4a12  movaps  xmmword ptr [rbp+57h+StringSecurityDescriptor], xmm0
0x1800f4a16  xor     r9d, r9d; SecurityDescriptorSize
0x1800f4a19  movaps  xmm0, xmmword ptr cs:aDA0x00120001Wd+20h; ";;;WD)(A;;0x001C0002;;;PS)"
0x1800f4a20  movaps  [rbp+57h+var_60], xmm1
0x1800f4a24  movaps  xmm1, xmmword ptr cs:aDA0x00120001Wd+30h; ";;0x001C0002;;;PS)"
0x1800f4a2b  movaps  [rbp+57h+var_50], xmm0
0x1800f4a2f  lea     edx, [r9+1]; StringSDRevision
0x1800f4a33  movaps  xmm0, xmmword ptr cs:aDA0x00120001Wd+40h; "0002;;;PS)"
0x1800f4a3a  movaps  [rbp+57h+var_40], xmm1
0x1800f4a3e  movsd   xmm1, qword ptr cs:aDA0x00120001Wd+4Eh; "PS)"
0x1800f4a46  movaps  [rbp+57h+var_30], xmm0
0x1800f4a4a  movsd   qword ptr [rbp+57h+var_30+0Eh], xmm1
0x1800f4a4f  mov     [rbp+57h+SecurityDescriptor], 0
0x1800f4a57  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800f4a5e  nop     dword ptr [rax+rax+00h]
0x1800f4a63  lea     r14, aWinerror; "%!WINERROR!"
0x1800f4a6a  test    eax, eax
0x1800f4a6c  jz      loc_1800F4B4C
0x1800f4a72  mov     rax, [rbp+57h+SecurityDescriptor]
0x1800f4a76  lea     r9, aScmcreatedeven; "ScmCreatedEvent"
0x1800f4a7d  xor     r8d, r8d; bInitialState
0x1800f4a80  mov     qword ptr [rbp+57h+EventAttributes.nLength], 18h
0x1800f4a88  lea     rcx, [rbp+57h+EventAttributes]; lpEventAttributes
0x1800f4a8c  mov     qword ptr [rbp+57h+EventAttributes.bInheritHandle], 0
0x1800f4a94  mov     [rbp+57h+EventAttributes.lpSecurityDescriptor], rax
0x1800f4a98  lea     edx, [r8+1]; bManualReset
0x1800f4a9c  call    cs:__imp_CreateEventW
0x1800f4aa3  nop     dword ptr [rax+rax+00h]
0x1800f4aa8  test    rax, rax
0x1800f4aab  jnz     short loc_1800F4B2B
0x1800f4aad  call    cs:__imp_GetLastError
0x1800f4ab4  nop     dword ptr [rax+rax+00h]
0x1800f4ab9  cmp     eax, 5
0x1800f4abc  jnz     short loc_1800F4ADB
0x1800f4abe  lea     r8, aScmcreatedeven; "ScmCreatedEvent"
0x1800f4ac5  xor     edx, edx; bInheritHandle
0x1800f4ac7  lea     ecx, [rax-3]; dwDesiredAccess
0x1800f4aca  call    cs:__imp_OpenEventW
0x1800f4ad1  nop     dword ptr [rax+rax+00h]
0x1800f4ad6  test    rax, rax
0x1800f4ad9  jnz     short loc_1800F4B2B
0x1800f4adb  mov     eax, cs:dword_1801574B8
0x1800f4ae1  test    eax, eax
0x1800f4ae3  jnz     short loc_1800F4AF8
0x1800f4ae5  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800f4aeb  jz      short loc_1800F4B3A
0x1800f4aed  xor     ecx, ecx
0x1800f4aef  call    IsWppLevelEnabled
0x1800f4af4  test    al, al
0x1800f4af6  jz      short loc_1800F4B3A
0x1800f4af8  call    cs:__imp_GetLastError
0x1800f4aff  nop     dword ptr [rax+rax+00h]
0x1800f4b04  mov     dword ptr [rsp+0C0h+var_98], eax
0x1800f4b08  xor     r9d, r9d
0x1800f4b0b  lea     rdx, aInitializescma; "InitializeSCMAfterListen"
0x1800f4b12  mov     [rsp+0C0h+var_A0], r14
0x1800f4b17  mov     r8d, 310h
0x1800f4b1d  lea     rcx, aOnecoreComComb_99; "onecore\\com\\combase\\rpcss\\olescm\\s"...
0x1800f4b24  call    ??$ComTraceMessageT@H@@YAXPEBD0HW4TraceLevel@@PEBGH@Z; ComTraceMessageT<int>(char const *,char const *,int,TraceLevel,ushort const *,int)
0x1800f4b29  jmp     short loc_1800F4B3A
0x1800f4b2b  mov     rcx, rax; hEvent
0x1800f4b2e  call    cs:__imp_SetEvent
0x1800f4b35  nop     dword ptr [rax+rax+00h]
0x1800f4b3a  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x1800f4b3e  call    cs:__imp_LocalFree
0x1800f4b45  nop     dword ptr [rax+rax+00h]
0x1800f4b4a  jmp     short loc_1800F4B9A
0x1800f4b4c  mov     eax, cs:dword_1801574B8
0x1800f4b52  test    eax, eax
0x1800f4b54  jnz     short loc_1800F4B69
0x1800f4b56  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800f4b5c  jz      short loc_1800F4B9A
0x1800f4b5e  xor     ecx, ecx
0x1800f4b60  call    IsWppLevelEnabled
0x1800f4b65  test    al, al
0x1800f4b67  jz      short loc_1800F4B9A
0x1800f4b69  call    cs:__imp_GetLastError
0x1800f4b70  nop     dword ptr [rax+rax+00h]
0x1800f4b75  mov     dword ptr [rsp+0C0h+var_98], eax
0x1800f4b79  xor     r9d, r9d
0x1800f4b7c  lea     rdx, aInitializescma; "InitializeSCMAfterListen"
0x1800f4b83  mov     [rsp+0C0h+var_A0], r14
0x1800f4b88  mov     r8d, 318h
0x1800f4b8e  lea     rcx, aOnecoreComComb_99; "onecore\\com\\combase\\rpcss\\olescm\\s"...
0x1800f4b95  call    ??$ComTraceMessageT@H@@YAXPEBD0HW4TraceLevel@@PEBGH@Z; ComTraceMessageT<int>(char const *,char const *,int,TraceLevel,ushort const *,int)
0x1800f4b9a  call    ?InitializeVistaEventIfNeeded@@YAXXZ; InitializeVistaEventIfNeeded(void)
0x1800f4b9f  call    cs:__imp_RpcMgmtEnableIdleCleanup
0x1800f4ba6  nop     dword ptr [rax+rax+00h]
0x1800f4bab  mov     r8d, eax
0x1800f4bae  test    eax, eax
0x1800f4bb0  jz      short loc_1800F4BF3
0x1800f4bb2  mov     ecx, cs:dword_1801574B8
0x1800f4bb8  test    ecx, ecx
0x1800f4bba  jnz     short loc_1800F4BCD
0x1800f4bbc  cmp     cs:?gfEnableTracing@@3HA, ecx; int gfEnableTracing
0x1800f4bc2  jz      short loc_1800F4BF3
0x1800f4bc4  call    IsWppLevelEnabled
0x1800f4bc9  test    al, al
0x1800f4bcb  jz      short loc_1800F4BF3
0x1800f4bcd  mov     dword ptr [rsp+0C0h+var_98], r8d
0x1800f4bd2  lea     rdx, aInitializescma; "InitializeSCMAfterListen"
0x1800f4bd9  mov     r8d, 324h
0x1800f4bdf  mov     [rsp+0C0h+var_A0], r14
0x1800f4be4  xor     r9d, r9d
0x1800f4be7  lea     rcx, aOnecoreComComb_99; "onecore\\com\\combase\\rpcss\\olescm\\s"...
0x1800f4bee  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x1800f4bf3  mov     rcx, [rbp+57h+var_10]
0x1800f4bf7  xor     rcx, rsp; StackCookie
0x1800f4bfa  call    __security_check_cookie
0x1800f4bff  mov     r14, [rsp+0C0h+arg_0]
0x1800f4c07  add     rsp, 0C0h
0x1800f4c0e  pop     rbp
0x1800f4c0f  retn
```
