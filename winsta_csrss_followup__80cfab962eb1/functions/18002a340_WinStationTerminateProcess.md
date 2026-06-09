# WinStationTerminateProcess

- ea: `0x18002a340`
- end: `0x18002a4e9`
- name: `WinStationTerminateProcess`
- size: `425`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180005b40`
- `0x18000a784`
- `0x180014744`
- `0x180026824`
- `0x18002a340`
- `0x18002f9e0`

## import_xrefs

- `ntdll!NtTerminateProcess` at `0x18002a469`
- `ntdll!NtTerminateProcess` at `0x18002a469`
- `ntdll!RtlNtStatusToDosError` at `0x18002a4aa`
- `ntdll!RtlNtStatusToDosError` at `0x18002a4aa`
- `ntdll!RtlAdjustPrivilege` at `0x18002a3cb`
- `ntdll!RtlAdjustPrivilege` at `0x18002a3cb`
- `ntdll!NtClose` at `0x18002a498`
- `ntdll!NtClose` at `0x18002a498`
- `ntdll!NtOpenProcess` at `0x18002a448`
- `ntdll!NtOpenProcess` at `0x18002a448`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a4b8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a4b8`

## string_xrefs

- `0x18002a39c`: `CPrivilegeEnable::CPrivilegeEnable`
- `0x18002a3a6`: `ImpersonationCheck failed: 0x%x in %s`
- `0x18002a45a`: `NtOpenProcess failed: 0x%x`

## pseudocode

```c
unsigned __int8 __fastcall WinStationTerminateProcess(void *a1, int a2, unsigned int a3)
{
  void *v3; // r14
  int v6; // eax
  unsigned __int8 v7; // di
  char v8; // al
  CPublicBinding *v9; // rcx
  NTSTATUS v10; // eax
  NTSTATUS v11; // ebx
  NTSTATUS v12; // eax
  DWORD v13; // eax
  int v15; // [rsp+20h] [rbp-50h] BYREF
  __int16 v16; // [rsp+24h] [rbp-4Ch]
  void *ProcessHandle; // [rsp+28h] [rbp-48h] BYREF
  struct _CLIENT_ID ClientId; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  unsigned __int8 OldValue; // [rsp+A8h] [rbp+38h] BYREF

  v3 = (void *)a2;
  ProcessHandle = 0;
  v15 = 20;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v16 = 0;
  OldValue = 0;
  ClientId = 0;
  v6 = CPrivilegeEnable::ImpersonationCheck((CPrivilegeEnable *)&v15);
  v7 = 1;
  if ( v6 >= 0 )
  {
    if ( RtlAdjustPrivilege(0x14u, 1u, HIBYTE(v16) != 0, &OldValue) >= 0 )
    {
      v8 = v16;
      if ( !OldValue )
        v8 = 1;
      LOBYTE(v16) = v8;
    }
  }
  else
  {
    _DbgPrintMessage(8, "ImpersonationCheck failed: 0x%x in %s", v6, "CPrivilegeEnable::CPrivilegeEnable");
  }
  if ( (unsigned int)IsLocalServer(a1) )
  {
    ClientId.UniqueThread = 0;
    ClientId.UniqueProcess = v3;
    ObjectAttributes.Length = 48;
    memset(&ObjectAttributes.RootDirectory, 0, 20);
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v10 = NtOpenProcess(&ProcessHandle, 1u, &ObjectAttributes, &ClientId);
    v11 = v10;
    if ( v10 >= 0 )
    {
      v12 = NtTerminateProcess(ProcessHandle, a3);
      v11 = v12;
      if ( v12 < 0 )
        _DbgPrintMessage(8, "NtTerminateProcess failed: 0x%x", (unsigned int)v12);
    }
    else
    {
      _DbgPrintMessage(8, "NtOpenProcess failed: 0x%x", (unsigned int)v10);
    }
    if ( ProcessHandle )
      NtClose(ProcessHandle);
    if ( v11 < 0 )
    {
      v13 = RtlNtStatusToDosError(v11);
      SetLastError(v13);
      v7 = 0;
    }
  }
  else
  {
    v7 = Legacy_WinStationTerminateProcess(v9, (unsigned int)v3, a3);
  }
  CPrivilegeEnable::~CPrivilegeEnable((CPrivilegeEnable *)&v15);
  return v7;
}

```

## disassembly

```asm
0x18002a340  mov     [rsp-18h+arg_0], rbx
0x18002a345  mov     [rsp-18h+arg_8], rsi
0x18002a34a  push    rbp
0x18002a34b  push    rdi
0x18002a34c  push    r14
0x18002a34e  mov     rbp, rsp
0x18002a351  sub     rsp, 70h
0x18002a355  xorps   xmm0, xmm0
0x18002a358  movsxd  r14, edx
0x18002a35b  mov     rbx, rcx
0x18002a35e  mov     [rbp+ProcessHandle], 0
0x18002a366  lea     rcx, [rbp+var_50]; this
0x18002a36a  mov     [rbp+var_50], 14h
0x18002a371  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18002a375  mov     esi, r8d
0x18002a378  mov     [rbp+var_4C], 0
0x18002a37e  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18002a382  mov     [rbp+OldValue], 0
0x18002a386  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18002a38a  movups  xmmword ptr [rbp+ClientId.UniqueProcess], xmm0
0x18002a38e  call    ?ImpersonationCheck@CPrivilegeEnable@@AEAAJXZ; CPrivilegeEnable::ImpersonationCheck(void)
0x18002a393  mov     edi, 1
0x18002a398  test    eax, eax
0x18002a39a  jns     short loc_18002A3B7
0x18002a39c  lea     r9, aCprivilegeenab; "CPrivilegeEnable::CPrivilegeEnable"
0x18002a3a3  mov     r8d, eax
0x18002a3a6  lea     rdx, aImpersonationc; "ImpersonationCheck failed: 0x%x in %s"
0x18002a3ad  lea     ecx, [rdi+7]; int
0x18002a3b0  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002a3b5  jmp     short loc_18002A3E9
0x18002a3b7  cmp     byte ptr [rbp+var_4C+1], 0
0x18002a3bb  lea     r9, [rbp+OldValue]; OldValue
0x18002a3bf  mov     dl, dil; NewValue
0x18002a3c2  mov     ecx, 14h; Privilege
0x18002a3c7  setnz   r8b; ForThread
0x18002a3cb  call    cs:__imp_RtlAdjustPrivilege
0x18002a3d2  nop     dword ptr [rax+rax+00h]
0x18002a3d7  test    eax, eax
0x18002a3d9  js      short loc_18002A3E9
0x18002a3db  movzx   eax, byte ptr [rbp+var_4C]
0x18002a3df  cmp     [rbp+OldValue], 0
0x18002a3e3  cmovz   eax, edi
0x18002a3e6  mov     byte ptr [rbp+var_4C], al
0x18002a3e9  mov     rcx, rbx; void *
0x18002a3ec  call    ?IsLocalServer@@YAHPEAX@Z; IsLocalServer(void *)
0x18002a3f1  test    eax, eax
0x18002a3f3  jnz     short loc_18002A408
0x18002a3f5  mov     r8d, esi; unsigned int
0x18002a3f8  mov     edx, r14d; unsigned int
0x18002a3fb  call    ?Legacy_WinStationTerminateProcess@@YAEPEAXKK@Z; Legacy_WinStationTerminateProcess(void *,ulong,ulong)
0x18002a400  mov     dil, al
0x18002a403  jmp     loc_18002A4C7
0x18002a408  xorps   xmm0, xmm0
0x18002a40b  mov     [rbp+ClientId.UniqueThread], 0
0x18002a413  lea     r9, [rbp+ClientId]; ClientId
0x18002a417  mov     [rbp+ClientId.UniqueProcess], r14
0x18002a41b  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18002a41f  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18002a426  mov     edx, edi; DesiredAccess
0x18002a428  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x18002a430  lea     rcx, [rbp+ProcessHandle]; ProcessHandle
0x18002a434  mov     [rbp+ObjectAttributes.Attributes], 0
0x18002a43b  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18002a440  mov     [rbp+ObjectAttributes.ObjectName], 0
0x18002a448  call    cs:__imp_NtOpenProcess
0x18002a44f  nop     dword ptr [rax+rax+00h]
0x18002a454  mov     ebx, eax
0x18002a456  test    eax, eax
0x18002a458  jns     short loc_18002A463
0x18002a45a  lea     rdx, aNtopenprocessF_0; "NtOpenProcess failed: 0x%x"
0x18002a461  jmp     short loc_18002A482
0x18002a463  mov     rcx, [rbp+ProcessHandle]; ProcessHandle
0x18002a467  mov     edx, esi; ExitStatus
0x18002a469  call    cs:__imp_NtTerminateProcess
0x18002a470  nop     dword ptr [rax+rax+00h]
0x18002a475  mov     ebx, eax
0x18002a477  test    eax, eax
0x18002a479  jns     short loc_18002A48F
0x18002a47b  lea     rdx, aNtterminatepro; "NtTerminateProcess failed: 0x%x"
0x18002a482  mov     r8d, eax
0x18002a485  mov     ecx, 8; int
0x18002a48a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002a48f  mov     rcx, [rbp+ProcessHandle]; Handle
0x18002a493  test    rcx, rcx
0x18002a496  jz      short loc_18002A4A4
0x18002a498  call    cs:__imp_NtClose
0x18002a49f  nop     dword ptr [rax+rax+00h]
0x18002a4a4  test    ebx, ebx
0x18002a4a6  jns     short loc_18002A4C7
0x18002a4a8  mov     ecx, ebx; Status
0x18002a4aa  call    cs:__imp_RtlNtStatusToDosError
0x18002a4b1  nop     dword ptr [rax+rax+00h]
0x18002a4b6  mov     ecx, eax; dwErrCode
0x18002a4b8  call    cs:__imp_SetLastError
0x18002a4bf  nop     dword ptr [rax+rax+00h]
0x18002a4c4  xor     dil, dil
0x18002a4c7  lea     rcx, [rbp+var_50]; this
0x18002a4cb  call    ??1CPrivilegeEnable@@QEAA@XZ; CPrivilegeEnable::~CPrivilegeEnable(void)
0x18002a4d0  lea     r11, [rsp+70h+var_s0]
0x18002a4d5  mov     al, dil
0x18002a4d8  mov     rbx, [r11+20h]
0x18002a4dc  mov     rsi, [r11+28h]
0x18002a4e0  mov     rsp, r11
0x18002a4e3  pop     r14
0x18002a4e5  pop     rdi
0x18002a4e6  pop     rbp
0x18002a4e7  retn
```
