# InitializeSCMAfterListen

- ea: `0x1800ecefc`
- end: `0x1800ed0fa`
- name: `InitializeSCMAfterListen`
- size: `510`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800b7d10`

## callees

- `0x180034540`
- `0x18007e3d4`
- `0x1800a1e98`
- `0x1800b27e0`
- `0x1800eca58`
- `0x1800ecefc`

## import_xrefs

- `RPCRT4!RpcMgmtEnableIdleCleanup` at `0x1800ed08f`
- `RPCRT4!RpcMgmtEnableIdleCleanup` at `0x1800ed08f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ecfc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ed000`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ed05f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ecfc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ed000`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ed05f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800ecfb6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800ecfb6`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800ecfd8`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800ecfd8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800ed030`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800ed030`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800ecf77`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800ecf77`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800ed03a`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800ed03a`

## string_xrefs

- `0x1800ed01f`: `onecore\com\combase\rpcss\olescm\scmsvc.cxx`
- `0x1800ed07e`: `onecore\com\combase\rpcss\olescm\scmsvc.cxx`
- `0x1800ed0d1`: `onecore\com\combase\rpcss\olescm\scmsvc.cxx`
- `0x1800ecf90`: `ScmCreatedEvent`
- `0x1800ecfcc`: `ScmCreatedEvent`

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
    else if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
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
  else if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
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
    if ( dword_18014E4B8
      || gfEnableTracing && (result = IsWppLevelEnabled((unsigned int)dword_18014E4B8), (_BYTE)result) )
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
0x1800ecefc  mov     [rsp-8+arg_0], r14
0x1800ecf01  push    rbp
0x1800ecf02  lea     rbp, [rsp-57h]
0x1800ecf07  sub     rsp, 0C0h
0x1800ecf0e  mov     rax, cs:__security_cookie
0x1800ecf15  xor     rax, rsp
0x1800ecf18  mov     [rbp+57h+var_10], rax
0x1800ecf1c  movaps  xmm0, xmmword ptr cs:aDA0x00120001Wd; "D:(A;;0x00120001;;;WD)(A;;0x001C0002;;;"...
0x1800ecf23  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1800ecf27  movaps  xmm1, xmmword ptr cs:aDA0x00120001Wd+10h; "00120001;;;WD)(A;;0x001C0002;;;PS)"
0x1800ecf2e  lea     rcx, [rbp+57h+StringSecurityDescriptor]; StringSecurityDescriptor
0x1800ecf32  movaps  xmmword ptr [rbp+57h+StringSecurityDescriptor], xmm0
0x1800ecf36  xor     r9d, r9d; SecurityDescriptorSize
0x1800ecf39  movaps  xmm0, xmmword ptr cs:aDA0x00120001Wd+20h; ";;;WD)(A;;0x001C0002;;;PS)"
0x1800ecf40  movaps  [rbp+57h+var_60], xmm1
0x1800ecf44  movaps  xmm1, xmmword ptr cs:aDA0x00120001Wd+30h; ";;0x001C0002;;;PS)"
0x1800ecf4b  movaps  [rbp+57h+var_50], xmm0
0x1800ecf4f  lea     edx, [r9+1]; StringSDRevision
0x1800ecf53  movaps  xmm0, xmmword ptr cs:aDA0x00120001Wd+40h; "0002;;;PS)"
0x1800ecf5a  movaps  [rbp+57h+var_40], xmm1
0x1800ecf5e  movsd   xmm1, qword ptr cs:aDA0x00120001Wd+4Eh; "PS)"
0x1800ecf66  movaps  [rbp+57h+var_30], xmm0
0x1800ecf6a  movsd   qword ptr [rbp+57h+var_30+0Eh], xmm1
0x1800ecf6f  mov     [rbp+57h+SecurityDescriptor], 0
0x1800ecf77  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800ecf7d  lea     r14, aWinerror; "%!WINERROR!"
0x1800ecf84  test    eax, eax
0x1800ecf86  jz      loc_1800ED042
0x1800ecf8c  mov     rax, [rbp+57h+SecurityDescriptor]
0x1800ecf90  lea     r9, aScmcreatedeven; "ScmCreatedEvent"
0x1800ecf97  xor     r8d, r8d; bInitialState
0x1800ecf9a  mov     qword ptr [rbp+57h+EventAttributes.nLength], 18h
0x1800ecfa2  lea     rcx, [rbp+57h+EventAttributes]; lpEventAttributes
0x1800ecfa6  mov     qword ptr [rbp+57h+EventAttributes.bInheritHandle], 0
0x1800ecfae  mov     [rbp+57h+EventAttributes.lpSecurityDescriptor], rax
0x1800ecfb2  lea     edx, [r8+1]; bManualReset
0x1800ecfb6  call    cs:__imp_CreateEventW
0x1800ecfbc  test    rax, rax
0x1800ecfbf  jnz     short loc_1800ED02D
0x1800ecfc1  call    cs:__imp_GetLastError
0x1800ecfc7  cmp     eax, 5
0x1800ecfca  jnz     short loc_1800ECFE3
0x1800ecfcc  lea     r8, aScmcreatedeven; "ScmCreatedEvent"
0x1800ecfd3  xor     edx, edx; bInheritHandle
0x1800ecfd5  lea     ecx, [rax-3]; dwDesiredAccess
0x1800ecfd8  call    cs:__imp_OpenEventW
0x1800ecfde  test    rax, rax
0x1800ecfe1  jnz     short loc_1800ED02D
0x1800ecfe3  mov     eax, cs:dword_18014E4B8
0x1800ecfe9  test    eax, eax
0x1800ecfeb  jnz     short loc_1800ED000
0x1800ecfed  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800ecff3  jz      short loc_1800ED036
0x1800ecff5  xor     ecx, ecx
0x1800ecff7  call    IsWppLevelEnabled
0x1800ecffc  test    al, al
0x1800ecffe  jz      short loc_1800ED036
0x1800ed000  call    cs:__imp_GetLastError
0x1800ed006  mov     dword ptr [rsp+0C0h+var_98], eax
0x1800ed00a  xor     r9d, r9d
0x1800ed00d  lea     rdx, aInitializescma; "InitializeSCMAfterListen"
0x1800ed014  mov     [rsp+0C0h+var_A0], r14
0x1800ed019  mov     r8d, 310h
0x1800ed01f  lea     rcx, aOnecoreComComb_99; "onecore\\com\\combase\\rpcss\\olescm\\s"...
0x1800ed026  call    ??$ComTraceMessageT@H@@YAXPEBD0HW4TraceLevel@@PEBGH@Z; ComTraceMessageT<int>(char const *,char const *,int,TraceLevel,ushort const *,int)
0x1800ed02b  jmp     short loc_1800ED036
0x1800ed02d  mov     rcx, rax; hEvent
0x1800ed030  call    cs:__imp_SetEvent
0x1800ed036  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x1800ed03a  call    cs:__imp_LocalFree
0x1800ed040  jmp     short loc_1800ED08A
0x1800ed042  mov     eax, cs:dword_18014E4B8
0x1800ed048  test    eax, eax
0x1800ed04a  jnz     short loc_1800ED05F
0x1800ed04c  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800ed052  jz      short loc_1800ED08A
0x1800ed054  xor     ecx, ecx
0x1800ed056  call    IsWppLevelEnabled
0x1800ed05b  test    al, al
0x1800ed05d  jz      short loc_1800ED08A
0x1800ed05f  call    cs:__imp_GetLastError
0x1800ed065  mov     dword ptr [rsp+0C0h+var_98], eax
0x1800ed069  xor     r9d, r9d
0x1800ed06c  lea     rdx, aInitializescma; "InitializeSCMAfterListen"
0x1800ed073  mov     [rsp+0C0h+var_A0], r14
0x1800ed078  mov     r8d, 318h
0x1800ed07e  lea     rcx, aOnecoreComComb_99; "onecore\\com\\combase\\rpcss\\olescm\\s"...
0x1800ed085  call    ??$ComTraceMessageT@H@@YAXPEBD0HW4TraceLevel@@PEBGH@Z; ComTraceMessageT<int>(char const *,char const *,int,TraceLevel,ushort const *,int)
0x1800ed08a  call    ?InitializeVistaEventIfNeeded@@YAXXZ; InitializeVistaEventIfNeeded(void)
0x1800ed08f  call    cs:__imp_RpcMgmtEnableIdleCleanup
0x1800ed095  mov     r8d, eax
0x1800ed098  test    eax, eax
0x1800ed09a  jz      short loc_1800ED0DD
0x1800ed09c  mov     ecx, cs:dword_18014E4B8
0x1800ed0a2  test    ecx, ecx
0x1800ed0a4  jnz     short loc_1800ED0B7
0x1800ed0a6  cmp     cs:?gfEnableTracing@@3HA, ecx; int gfEnableTracing
0x1800ed0ac  jz      short loc_1800ED0DD
0x1800ed0ae  call    IsWppLevelEnabled
0x1800ed0b3  test    al, al
0x1800ed0b5  jz      short loc_1800ED0DD
0x1800ed0b7  mov     dword ptr [rsp+0C0h+var_98], r8d
0x1800ed0bc  lea     rdx, aInitializescma; "InitializeSCMAfterListen"
0x1800ed0c3  mov     r8d, 324h
0x1800ed0c9  mov     [rsp+0C0h+var_A0], r14
0x1800ed0ce  xor     r9d, r9d
0x1800ed0d1  lea     rcx, aOnecoreComComb_99; "onecore\\com\\combase\\rpcss\\olescm\\s"...
0x1800ed0d8  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x1800ed0dd  mov     rcx, [rbp+57h+var_10]
0x1800ed0e1  xor     rcx, rsp; StackCookie
0x1800ed0e4  call    __security_check_cookie
0x1800ed0e9  mov     r14, [rsp+0C0h+arg_0]
0x1800ed0f1  add     rsp, 0C0h
0x1800ed0f8  pop     rbp
0x1800ed0f9  retn
```
