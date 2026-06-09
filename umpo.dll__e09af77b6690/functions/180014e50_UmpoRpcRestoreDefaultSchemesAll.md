# UmpoRpcRestoreDefaultSchemesAll

- ea: `0x180014e50`
- end: `0x180014f70`
- name: `UmpoRpcRestoreDefaultSchemesAll`
- size: `288`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x1800035c0`
- `0x1800036f0`
- `0x180004b80`
- `0x18000f3dc`
- `0x180014e50`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014ee3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014ee3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014f51`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014f51`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014f1d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014f1d`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180014ef8`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180014ef8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014ebd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014ebd`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180014ecb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180014ecb`

## pseudocode

```c
__int64 UmpoRpcRestoreDefaultSchemesAll()
{
  DWORD v0; // edi
  DWORD CurrentThreadId; // ebx
  unsigned int Value; // edi
  unsigned int v3; // ebx

  if ( UmpoIsClientLocal() )
  {
    if ( UmpoPowerPolicyInitialized )
    {
      v0 = UmpoRpcSettingAccessCheck(0, 0x14u, 0, 0x20006u);
      if ( !v0 )
      {
        if ( qword_1800246D0 )
        {
          if ( UmpoUserPowerTlsSlot == -1 )
            MicrosoftTelemetryAssertTriggeredNoArgs();
          CurrentThreadId = GetCurrentThreadId();
          Value = (unsigned int)TlsGetValue(UmpoUserPowerTlsSlot);
          if ( CurrentThreadId != UmpoUserPowerLockThread )
          {
            AcquireSRWLockExclusive(&UmpoUserPowerLock);
            UmpoUserPowerLockThread = CurrentThreadId;
          }
          TlsSetValue(UmpoUserPowerTlsSlot, (LPVOID)(Value + 1));
          v0 = qword_1800246D0();
          if ( (unsigned __int64)UmpoUserPowerRootKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
          {
            RegCloseKey(UmpoUserPowerRootKey);
            UmpoUserPowerRootKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
          }
          v3 = RegOpenKeyExW(
                 HKEY_LOCAL_MACHINE,
                 L"System\\CurrentControlSet\\Control\\Power\\User\\PowerSchemes",
                 0,
                 0x20019u,
                 &UmpoUserPowerRootKey);
          ReleaseUserPowerLock();
          if ( !v0 )
            return v3;
        }
        else
        {
          return 50;
        }
      }
    }
    else
    {
      return 21;
    }
  }
  else
  {
    return 5;
  }
  return v0;
}

```

## disassembly

```asm
0x180014e50  mov     [rsp+arg_0], rbx
0x180014e55  push    rdi
0x180014e56  sub     rsp, 30h
0x180014e5a  call    UmpoIsClientLocal
0x180014e5f  test    eax, eax
0x180014e61  jnz     short loc_180014E6B
0x180014e63  lea     edi, [rax+5]
0x180014e66  jmp     loc_180014F63
0x180014e6b  mov     al, cs:UmpoPowerPolicyInitialized
0x180014e71  test    al, al
0x180014e73  jnz     short loc_180014E7F
0x180014e75  mov     edi, 15h
0x180014e7a  jmp     loc_180014F63
0x180014e7f  xor     r8d, r8d
0x180014e82  mov     r9d, 20006h
0x180014e88  xor     ecx, ecx
0x180014e8a  lea     edx, [r8+14h]
0x180014e8e  call    UmpoRpcSettingAccessCheck
0x180014e93  mov     edi, eax
0x180014e95  test    eax, eax
0x180014e97  jnz     loc_180014F63
0x180014e9d  cmp     cs:qword_1800246D0, 0
0x180014ea5  jnz     short loc_180014EAF
0x180014ea7  lea     edi, [rax+32h]
0x180014eaa  jmp     loc_180014F63
0x180014eaf  cmp     cs:UmpoUserPowerTlsSlot, 0FFFFFFFFh
0x180014eb6  jnz     short loc_180014EBD
0x180014eb8  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180014ebd  call    cs:__imp_GetCurrentThreadId
0x180014ec3  mov     ecx, cs:UmpoUserPowerTlsSlot; dwTlsIndex
0x180014ec9  mov     ebx, eax
0x180014ecb  call    cs:__imp_TlsGetValue
0x180014ed1  cmp     ebx, cs:UmpoUserPowerLockThread
0x180014ed7  mov     rdi, rax
0x180014eda  jz      short loc_180014EEF
0x180014edc  lea     rcx, UmpoUserPowerLock; SRWLock
0x180014ee3  call    cs:__imp_AcquireSRWLockExclusive
0x180014ee9  mov     cs:UmpoUserPowerLockThread, ebx
0x180014eef  mov     ecx, cs:UmpoUserPowerTlsSlot; dwTlsIndex
0x180014ef5  lea     edx, [rdi+1]; lpTlsValue
0x180014ef8  call    cs:__imp_TlsSetValue
0x180014efe  mov     rax, cs:qword_1800246D0
0x180014f05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f0a  mov     rcx, cs:UmpoUserPowerRootKey; hKey
0x180014f11  mov     edi, eax
0x180014f13  lea     rax, [rcx-1]
0x180014f17  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180014f1b  ja      short loc_180014F2E
0x180014f1d  call    cs:__imp_RegCloseKey
0x180014f23  mov     cs:UmpoUserPowerRootKey, 0FFFFFFFFFFFFFFFFh
0x180014f2e  lea     rax, UmpoUserPowerRootKey
0x180014f35  mov     r9d, 20019h; samDesired
0x180014f3b  xor     r8d, r8d; ulOptions
0x180014f3e  mov     [rsp+38h+phkResult], rax; phkResult
0x180014f43  lea     rdx, aSystemCurrentc_4; "System\\CurrentControlSet\\Control\\Pow"...
0x180014f4a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180014f51  call    cs:__imp_RegOpenKeyExW
0x180014f57  mov     ebx, eax
0x180014f59  call    ReleaseUserPowerLock
0x180014f5e  test    edi, edi
0x180014f60  cmovz   edi, ebx
0x180014f63  mov     rbx, [rsp+38h+arg_0]
0x180014f68  mov     eax, edi
0x180014f6a  add     rsp, 30h
0x180014f6e  pop     rdi
0x180014f6f  retn
```
