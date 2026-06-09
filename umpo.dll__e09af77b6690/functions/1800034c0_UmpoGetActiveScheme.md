# UmpoGetActiveScheme

- ea: `0x1800034c0`
- end: `0x18000354f`
- name: `UmpoGetActiveScheme`
- size: `143`
- prototype: `__int64 __fastcall(UUID *Uuid, __int64)`
- caller_count: `9`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800012a0`
- `0x180001580`
- `0x180002420`
- `0x180002530`
- `0x180002bc0`
- `0x180003640`
- `0x180004830`
- `0x180011f4c`
- `0x1800165a8`

## callees

- `0x180003270`
- `0x180003440`
- `0x1800034c0`
- `0x180003560`
- `0x1800035c0`
- `0x18000f3dc`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall UmpoGetActiveScheme(UUID *Uuid, __int64 a2)
{
  HKEY v3; // rbx
  unsigned int KeyValueGuid; // edi

  if ( !Uuid )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !qword_1800246A8 || (v3 = 0, (KeyValueGuid = qword_1800246A8(Uuid)) != 0) )
  {
    AcquireUserPowerLockShared((__int64)Uuid, a2);
    v3 = UmpoUserPowerRootKey;
    if ( (unsigned __int64)UmpoUserPowerRootKey - 1 > 0xFFFFFFFFFFFFFFFDuLL )
    {
      v3 = 0;
      MicrosoftTelemetryAssertTriggeredNoArgs();
      ReleaseUserPowerLock();
      KeyValueGuid = 87;
    }
    else
    {
      KeyValueGuid = UmpoInternalGetKeyValueGuid(UmpoUserPowerRootKey, L"ActivePowerScheme", Uuid);
    }
  }
  UmpoInternalCloseUserPowerKey(v3);
  return KeyValueGuid;
}

```

## disassembly

```asm
0x1800034c0  mov     [rsp+arg_8], rbx
0x1800034c5  mov     [rsp+arg_10], rsi
0x1800034ca  push    rdi
0x1800034cb  sub     rsp, 20h
0x1800034cf  mov     rsi, rcx
0x1800034d2  test    rcx, rcx
0x1800034d5  jz      short loc_180003537
0x1800034d7  mov     rax, cs:qword_1800246A8
0x1800034de  test    rax, rax
0x1800034e1  jz      short loc_1800034F3
0x1800034e3  mov     rcx, rsi
0x1800034e6  xor     ebx, ebx
0x1800034e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034ed  mov     edi, eax
0x1800034ef  test    eax, eax
0x1800034f1  jz      short loc_18000351D
0x1800034f3  call    AcquireUserPowerLockShared
0x1800034f8  mov     rbx, cs:UmpoUserPowerRootKey
0x1800034ff  lea     rax, [rbx-1]
0x180003503  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180003507  ja      short loc_18000353E
0x180003509  mov     r8, rsi; Uuid
0x18000350c  lea     rdx, ValueName; "ActivePowerScheme"
0x180003513  mov     rcx, rbx; hKey
0x180003516  call    UmpoInternalGetKeyValueGuid
0x18000351b  mov     edi, eax
0x18000351d  mov     rcx, rbx
0x180003520  call    UmpoInternalCloseUserPowerKey
0x180003525  mov     rbx, [rsp+28h+arg_8]
0x18000352a  mov     eax, edi
0x18000352c  mov     rsi, [rsp+28h+arg_10]
0x180003531  add     rsp, 20h
0x180003535  pop     rdi
0x180003536  retn
0x180003537  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000353c  jmp     short loc_1800034D7
0x18000353e  xor     ebx, ebx
0x180003540  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180003545  call    ReleaseUserPowerLock
0x18000354a  lea     edi, [rbx+57h]
0x18000354d  jmp     short loc_18000351D
```
