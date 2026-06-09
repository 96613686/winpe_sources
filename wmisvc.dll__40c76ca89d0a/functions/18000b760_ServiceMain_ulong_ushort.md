# ServiceMain(ulong,ushort * *)

- ea: `0x18000b760`
- end: `0x18000b8e1`
- name: `?ServiceMain@@YAXKPEAPEAG@Z`
- size: `385`
- prototype: `void __fastcall(unsigned int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1800062c8`
- `0x18000a18c`
- `0x18000a214`
- `0x18000a33c`
- `0x18000b760`
- `0x180013170`
- `0x18001d3a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b7ce`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b7ce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b810`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b810`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b806`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b806`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b866`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b866`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000b82d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000b82d`
- `api-ms-win-core-processthreads-l1-1-0!SetProcessShutdownParameters` at `0x18000b89f`
- `api-ms-win-core-processthreads-l1-1-0!SetProcessShutdownParameters` at `0x18000b89f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000b78a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000b78a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b84e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b84e`
- `api-ms-win-core-processthreads-l1-1-3!SetProcessInformation` at `0x18000b844`
- `api-ms-win-core-processthreads-l1-1-3!SetProcessInformation` at `0x18000b844`
- `wbemcomn!GetMemLogObject` at `0x18000b854`
- `wbemcomn!GetMemLogObject` at `0x18000b854`
- `wbemcomn!?SetLogingEnabled@CMemoryLog@@QEAAX_N@Z` at `0x18000b860`
- `wbemcomn!?SetLogingEnabled@CMemoryLog@@QEAAX_N@Z` at `0x18000b860`

## string_xrefs

- `0x18000b793`: `ProcessID`

## pseudocode

```c
void __fastcall ServiceMain(unsigned int a1, unsigned __int16 **a2)
{
  DWORD CurrentProcessId; // eax
  HKEY v5; // rcx
  HANDLE CurrentProcess; // rax
  CMemoryLog *MemLogObject; // rax
  HKEY v8; // rcx
  BYTE Data[4]; // [rsp+30h] [rbp-30h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-2Ch] BYREF
  DWORD Type; // [rsp+38h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-20h] BYREF
  __int64 v13; // [rsp+48h] [rbp-18h] BYREF
  int v14; // [rsp+50h] [rbp-10h]

  *(_DWORD *)Data = 1;
  CurrentProcessId = GetCurrentProcessId();
  RegSetDWORD(v5, L"Software\\Microsoft\\WBEM\\CIMOM", L"ProcessID", CurrentProcessId);
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\WBEM\\CIMOM", 0, 0x20019u, &hKey) )
  {
    Type = 0;
    cbData = 4;
    RegQueryValueExW(hKey, L"EnableEcoQos", 0, &Type, Data, &cbData);
    RegCloseKey(hKey);
  }
  v13 = 0;
  v14 = 0;
  if ( *(_DWORD *)Data )
  {
    v13 = 0x100000001LL;
    v14 = 1;
  }
  CurrentProcess = GetCurrentProcess();
  if ( !(unsigned int)SetProcessInformation(CurrentProcess, 4, &v13) )
    GetLastError();
  MemLogObject = GetMemLogObject();
  CMemoryLog::SetLogingEnabled(MemLogObject, 1);
  dword_180032CDC = GetCurrentThreadId();
  dword_180032A50 = CheckGlobalSetupSwitch();
  if ( dword_180032A50 )
  {
    HIBYTE(word_180032CD8) = 1;
    SetNoShellADAPSwitch();
  }
  dword_180032A54 = CheckNoResyncSwitch();
  SetProcessShutdownParameters(0x400u, 0);
  RegSetDWORD(v8, L"Software\\Microsoft\\WBEM\\CIMOM", L"ThrottleDrege", 1u);
  RunService(a1, a2);
}

```

## disassembly

```asm
0x18000b760  mov     [rsp-18h+arg_10], rbx
0x18000b765  push    rbp
0x18000b766  push    rsi
0x18000b767  push    rdi
0x18000b768  mov     rbp, rsp
0x18000b76b  sub     rsp, 60h
0x18000b76f  mov     rax, cs:__security_cookie
0x18000b776  xor     rax, rsp
0x18000b779  mov     [rbp+var_8], rax
0x18000b77d  mov     esi, 1
0x18000b782  mov     rdi, rdx
0x18000b785  mov     dword ptr [rbp+Data], esi
0x18000b788  mov     ebx, ecx
0x18000b78a  call    cs:__imp_GetCurrentProcessId
0x18000b790  mov     r9d, eax; unsigned int
0x18000b793  lea     r8, aProcessid; "ProcessID"
0x18000b79a  lea     rdx, SubKey; "Software\\Microsoft\\WBEM\\CIMOM"
0x18000b7a1  call    ?RegSetDWORD@@YAKPEAUHKEY__@@PEBG1K@Z; RegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18000b7a6  lea     rax, [rbp+hKey]
0x18000b7aa  mov     [rbp+hKey], 0
0x18000b7b2  mov     r9d, 20019h; samDesired
0x18000b7b8  mov     [rsp+60h+phkResult], rax; phkResult
0x18000b7bd  xor     r8d, r8d; ulOptions
0x18000b7c0  lea     rdx, SubKey; "Software\\Microsoft\\WBEM\\CIMOM"
0x18000b7c7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000b7ce  call    cs:__imp_RegOpenKeyExW
0x18000b7d4  test    eax, eax
0x18000b7d6  jnz     short loc_18000B816
0x18000b7d8  mov     rcx, [rbp+hKey]; hKey
0x18000b7dc  lea     r9, [rbp+Type]; lpType
0x18000b7e0  mov     [rbp+Type], eax
0x18000b7e3  lea     rdx, aEnableecoqos; "EnableEcoQos"
0x18000b7ea  lea     rax, [rbp+cbData]
0x18000b7ee  mov     [rbp+cbData], 4
0x18000b7f5  mov     [rsp+60h+lpcbData], rax; lpcbData
0x18000b7fa  xor     r8d, r8d; lpReserved
0x18000b7fd  lea     rax, [rbp+Data]
0x18000b801  mov     [rsp+60h+phkResult], rax; lpData
0x18000b806  call    cs:__imp_RegQueryValueExW
0x18000b80c  mov     rcx, [rbp+hKey]; hKey
0x18000b810  call    cs:__imp_RegCloseKey
0x18000b816  xor     eax, eax
0x18000b818  mov     [rbp+var_18], rax
0x18000b81c  mov     [rbp+var_10], eax
0x18000b81f  cmp     dword ptr [rbp+Data], eax
0x18000b822  jz      short loc_18000B82D
0x18000b824  mov     dword ptr [rbp+var_18], esi
0x18000b827  mov     dword ptr [rbp+var_18+4], esi
0x18000b82a  mov     [rbp+var_10], esi
0x18000b82d  call    cs:__imp_GetCurrentProcess
0x18000b833  mov     r9d, 0Ch
0x18000b839  lea     r8, [rbp+var_18]
0x18000b83d  mov     rcx, rax
0x18000b840  lea     edx, [r9-8]
0x18000b844  call    cs:__imp_SetProcessInformation
0x18000b84a  test    eax, eax
0x18000b84c  jnz     short loc_18000B854
0x18000b84e  call    cs:__imp_GetLastError
0x18000b854  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000b85a  mov     rcx, rax
0x18000b85d  mov     dl, sil
0x18000b860  call    cs:__imp_?SetLogingEnabled@CMemoryLog@@QEAAX_N@Z; CMemoryLog::SetLogingEnabled(bool)
0x18000b866  call    cs:__imp_GetCurrentThreadId
0x18000b86c  mov     cs:dword_180032CDC, eax
0x18000b872  call    ?CheckGlobalSetupSwitch@@YAHXZ; CheckGlobalSetupSwitch(void)
0x18000b877  mov     cs:dword_180032A50, eax
0x18000b87d  test    eax, eax
0x18000b87f  jz      short loc_18000B88D
0x18000b881  mov     byte ptr cs:word_180032CD8+1, sil
0x18000b888  call    ?SetNoShellADAPSwitch@@YAXXZ; SetNoShellADAPSwitch(void)
0x18000b88d  call    ?CheckNoResyncSwitch@@YAHXZ; CheckNoResyncSwitch(void)
0x18000b892  xor     edx, edx; dwFlags
0x18000b894  mov     cs:dword_180032A54, eax
0x18000b89a  mov     ecx, 400h; dwLevel
0x18000b89f  call    cs:__imp_SetProcessShutdownParameters
0x18000b8a5  mov     r9d, esi; unsigned int
0x18000b8a8  lea     r8, aThrottledrege; "ThrottleDrege"
0x18000b8af  lea     rdx, SubKey; "Software\\Microsoft\\WBEM\\CIMOM"
0x18000b8b6  call    ?RegSetDWORD@@YAKPEAUHKEY__@@PEBG1K@Z; RegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18000b8bb  mov     rdx, rdi; unsigned __int16 **
0x18000b8be  mov     ecx, ebx; unsigned int
0x18000b8c0  call    ?RunService@@YAXKPEAPEAG@Z; RunService(ulong,ushort * *)
0x18000b8c5  mov     rcx, [rbp+var_8]
0x18000b8c9  xor     rcx, rsp; StackCookie
0x18000b8cc  call    __security_check_cookie
0x18000b8d1  mov     rbx, [rsp+60h+arg_10]
0x18000b8d9  add     rsp, 60h
0x18000b8dd  pop     rdi
0x18000b8de  pop     rsi
0x18000b8df  pop     rbp
0x18000b8e0  retn
```
