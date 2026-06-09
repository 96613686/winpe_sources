# UmpoInternalOpenUserPowerKey

- ea: `0x180003370`
- end: `0x180003433`
- name: `UmpoInternalOpenUserPowerKey`
- size: `195`
- prototype: `LSTATUS __fastcall(PHKEY phkResult, __int64 samDesired, int)`
- caller_count: `7`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001980`
- `0x180005cb4`
- `0x18000b9b8`
- `0x180011f4c`
- `0x180012254`
- `0x180014300`
- `0x180014810`

## callees

- `0x180003370`
- `0x180003440`
- `0x1800035c0`
- `0x18000f3dc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800033e6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800033e6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003404`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003404`

## pseudocode

```c
LSTATUS __fastcall UmpoInternalOpenUserPowerKey(PHKEY phkResult, __int64 samDesired, int a3)
{
  if ( phkResult )
  {
    *phkResult = 0;
    if ( (_DWORD)samDesired == 131097 )
    {
      if ( !a3 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      AcquireUserPowerLockShared((__int64)phkResult, samDesired);
      if ( (unsigned __int64)UmpoUserPowerRootKey - 1 > 0xFFFFFFFFFFFFFFFDuLL )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
        ReleaseUserPowerLock();
        return 87;
      }
      else
      {
        *phkResult = UmpoUserPowerRootKey;
        return 0;
      }
    }
    else if ( a3 )
    {
      return RegOpenKeyExW(
               HKEY_LOCAL_MACHINE,
               L"System\\CurrentControlSet\\Control\\Power\\User\\PowerSchemes",
               0,
               samDesired,
               phkResult);
    }
    else
    {
      return RegCreateKeyExW(
               HKEY_LOCAL_MACHINE,
               L"System\\CurrentControlSet\\Control\\Power\\User\\PowerSchemes",
               0,
               0,
               0,
               samDesired,
               0,
               phkResult,
               0);
    }
  }
  else
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    return 87;
  }
}

```

## disassembly

```asm
0x180003370  push    rbx
0x180003372  sub     rsp, 50h
0x180003376  mov     rbx, rcx
0x180003379  test    rcx, rcx
0x18000337c  jz      loc_18000340C
0x180003382  xor     eax, eax
0x180003384  mov     [rcx], rax
0x180003387  cmp     edx, 20019h
0x18000338d  jnz     short loc_1800033B9
0x18000338f  test    r8d, r8d
0x180003392  jz      loc_180003418
0x180003398  call    AcquireUserPowerLockShared
0x18000339d  mov     rcx, cs:UmpoUserPowerRootKey
0x1800033a4  lea     rax, [rcx-1]
0x1800033a8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800033ac  ja      short loc_180003422
0x1800033ae  mov     [rbx], rcx
0x1800033b1  xor     eax, eax
0x1800033b3  add     rsp, 50h
0x1800033b7  pop     rbx
0x1800033b8  retn
0x1800033b9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800033c0  test    r8d, r8d
0x1800033c3  jnz     short loc_1800033F2
0x1800033c5  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x1800033ca  xor     r9d, r9d; lpClass
0x1800033cd  mov     [rsp+58h+phkResult], rbx; phkResult
0x1800033d2  mov     [rsp+58h+lpSecurityAttributes], rax; lpSecurityAttributes
0x1800033d7  mov     [rsp+58h+samDesired], edx; samDesired
0x1800033db  lea     rdx, aSystemCurrentc_4; "System\\CurrentControlSet\\Control\\Pow"...
0x1800033e2  mov     [rsp+58h+dwOptions], eax; dwOptions
0x1800033e6  call    cs:__imp_RegCreateKeyExW
0x1800033ec  add     rsp, 50h
0x1800033f0  pop     rbx
0x1800033f1  retn
0x1800033f2  mov     r9d, edx; samDesired
0x1800033f5  mov     qword ptr [rsp+58h+dwOptions], rbx; phkResult
0x1800033fa  lea     rdx, aSystemCurrentc_4; "System\\CurrentControlSet\\Control\\Pow"...
0x180003401  xor     r8d, r8d; ulOptions
0x180003404  call    cs:__imp_RegOpenKeyExW
0x18000340a  jmp     short loc_1800033B3
0x18000340c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180003411  mov     eax, 57h ; 'W'
0x180003416  jmp     short loc_1800033B3
0x180003418  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000341d  jmp     loc_180003398
0x180003422  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180003427  call    ReleaseUserPowerLock
0x18000342c  mov     eax, 57h ; 'W'
0x180003431  jmp     short loc_1800033B3
```
