# WinStationTerminateProcess

- ea: `0x180028790`
- end: `0x180028914`
- name: `WinStationTerminateProcess`
- size: `388`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180004554`
- `0x180007890`
- `0x180013800`
- `0x180024f00`
- `0x180028790`
- `0x18002d57c`

## import_xrefs

- `ntdll!NtTerminateProcess` at `0x1800288ad`
- `ntdll!NtTerminateProcess` at `0x1800288ad`
- `ntdll!RtlNtStatusToDosError` at `0x1800288e2`
- `ntdll!RtlNtStatusToDosError` at `0x1800288e2`
- `ntdll!RtlAdjustPrivilege` at `0x18002881b`
- `ntdll!RtlAdjustPrivilege` at `0x18002881b`
- `ntdll!NtClose` at `0x1800288d6`
- `ntdll!NtClose` at `0x1800288d6`
- `ntdll!NtOpenProcess` at `0x180028892`
- `ntdll!NtOpenProcess` at `0x180028892`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800288ea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800288ea`

## string_xrefs

- `0x1800287ec`: `CPrivilegeEnable::CPrivilegeEnable`
- `0x1800287f6`: `ImpersonationCheck failed: 0x%x in %s`
- `0x18002889e`: `NtOpenProcess failed: 0x%x`

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
  ULONG v13; // eax
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
0x180028790  mov     [rsp-18h+arg_0], rbx
0x180028795  mov     [rsp-18h+arg_8], rsi
0x18002879a  push    rbp
0x18002879b  push    rdi
0x18002879c  push    r14
0x18002879e  mov     rbp, rsp
0x1800287a1  sub     rsp, 70h
0x1800287a5  xorps   xmm0, xmm0
0x1800287a8  movsxd  r14, edx
0x1800287ab  mov     rbx, rcx
0x1800287ae  mov     [rbp+ProcessHandle], 0
0x1800287b6  lea     rcx, [rbp+var_50]; this
0x1800287ba  mov     [rbp+var_50], 14h
0x1800287c1  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1800287c5  mov     esi, r8d
0x1800287c8  mov     [rbp+var_4C], 0
0x1800287ce  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1800287d2  mov     [rbp+OldValue], 0
0x1800287d6  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800287da  movups  xmmword ptr [rbp+ClientId.UniqueProcess], xmm0
0x1800287de  call    ?ImpersonationCheck@CPrivilegeEnable@@AEAAJXZ; CPrivilegeEnable::ImpersonationCheck(void)
0x1800287e3  mov     edi, 1
0x1800287e8  test    eax, eax
0x1800287ea  jns     short loc_180028807
0x1800287ec  lea     r9, aCprivilegeenab; "CPrivilegeEnable::CPrivilegeEnable"
0x1800287f3  mov     r8d, eax
0x1800287f6  lea     rdx, aImpersonationc; "ImpersonationCheck failed: 0x%x in %s"
0x1800287fd  lea     ecx, [rdi+7]; int
0x180028800  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180028805  jmp     short loc_180028833
0x180028807  cmp     byte ptr [rbp+var_4C+1], 0
0x18002880b  lea     r9, [rbp+OldValue]; OldValue
0x18002880f  mov     dl, dil; NewValue
0x180028812  mov     ecx, 14h; Privilege
0x180028817  setnz   r8b; ForThread
0x18002881b  call    cs:__imp_RtlAdjustPrivilege
0x180028821  test    eax, eax
0x180028823  js      short loc_180028833
0x180028825  movzx   eax, byte ptr [rbp+var_4C]
0x180028829  cmp     [rbp+OldValue], 0
0x18002882d  cmovz   eax, edi
0x180028830  mov     byte ptr [rbp+var_4C], al
0x180028833  mov     rcx, rbx; void *
0x180028836  call    ?IsLocalServer@@YAHPEAX@Z; IsLocalServer(void *)
0x18002883b  test    eax, eax
0x18002883d  jnz     short loc_180028852
0x18002883f  mov     r8d, esi; unsigned int
0x180028842  mov     edx, r14d; unsigned int
0x180028845  call    ?Legacy_WinStationTerminateProcess@@YAEPEAXKK@Z; Legacy_WinStationTerminateProcess(void *,ulong,ulong)
0x18002884a  mov     dil, al
0x18002884d  jmp     loc_1800288F3
0x180028852  xorps   xmm0, xmm0
0x180028855  mov     [rbp+ClientId.UniqueThread], 0
0x18002885d  lea     r9, [rbp+ClientId]; ClientId
0x180028861  mov     [rbp+ClientId.UniqueProcess], r14
0x180028865  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180028869  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180028870  mov     edx, edi; DesiredAccess
0x180028872  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x18002887a  lea     rcx, [rbp+ProcessHandle]; ProcessHandle
0x18002887e  mov     [rbp+ObjectAttributes.Attributes], 0
0x180028885  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18002888a  mov     [rbp+ObjectAttributes.ObjectName], 0
0x180028892  call    cs:__imp_NtOpenProcess
0x180028898  mov     ebx, eax
0x18002889a  test    eax, eax
0x18002889c  jns     short loc_1800288A7
0x18002889e  lea     rdx, aNtopenprocessF_0; "NtOpenProcess failed: 0x%x"
0x1800288a5  jmp     short loc_1800288C0
0x1800288a7  mov     rcx, [rbp+ProcessHandle]; ProcessHandle
0x1800288ab  mov     edx, esi; ExitStatus
0x1800288ad  call    cs:__imp_NtTerminateProcess
0x1800288b3  mov     ebx, eax
0x1800288b5  test    eax, eax
0x1800288b7  jns     short loc_1800288CD
0x1800288b9  lea     rdx, aNtterminatepro; "NtTerminateProcess failed: 0x%x"
0x1800288c0  mov     r8d, eax
0x1800288c3  mov     ecx, 8; int
0x1800288c8  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800288cd  mov     rcx, [rbp+ProcessHandle]; Handle
0x1800288d1  test    rcx, rcx
0x1800288d4  jz      short loc_1800288DC
0x1800288d6  call    cs:__imp_NtClose
0x1800288dc  test    ebx, ebx
0x1800288de  jns     short loc_1800288F3
0x1800288e0  mov     ecx, ebx; Status
0x1800288e2  call    cs:__imp_RtlNtStatusToDosError
0x1800288e8  mov     ecx, eax; dwErrCode
0x1800288ea  call    cs:__imp_SetLastError
0x1800288f0  xor     dil, dil
0x1800288f3  lea     rcx, [rbp+var_50]; this
0x1800288f7  call    ??1CPrivilegeEnable@@QEAA@XZ; CPrivilegeEnable::~CPrivilegeEnable(void)
0x1800288fc  lea     r11, [rsp+70h+var_s0]
0x180028901  mov     al, dil
0x180028904  mov     rbx, [r11+20h]
0x180028908  mov     rsi, [r11+28h]
0x18002890c  mov     rsp, r11
0x18002890f  pop     r14
0x180028911  pop     rdi
0x180028912  pop     rbp
0x180028913  retn
```
