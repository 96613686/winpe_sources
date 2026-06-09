# UmpoInternalCloseUserPowerKey

- ea: `0x180003560`
- end: `0x1800035b0`
- name: `UmpoInternalCloseUserPowerKey`
- size: `80`
- prototype: `void __fastcall(HKEY)`
- caller_count: `10`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001980`
- `0x1800027d4`
- `0x180002d8c`
- `0x1800034c0`
- `0x180005cb4`
- `0x18000b9b8`
- `0x180011f4c`
- `0x180012254`
- `0x180014300`
- `0x180014810`

## callees

- `0x180003560`
- `0x1800035c0`
- `0x18000f3dc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800035a2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180003573`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180003573`

## pseudocode

```c
void __fastcall UmpoInternalCloseUserPowerKey(HKEY a1)
{
  if ( UmpoUserPowerRootKey == a1 )
  {
    if ( !(unsigned int)TlsGetValue(UmpoUserPowerTlsSlot) || UmpoUserPowerLockThread )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    ReleaseUserPowerLock();
  }
  else if ( (unsigned __int64)a1 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(a1);
  }
}

```

## disassembly

```asm
0x180003560  sub     rsp, 28h
0x180003564  cmp     cs:UmpoUserPowerRootKey, rcx
0x18000356b  jnz     short loc_180003594
0x18000356d  mov     ecx, cs:UmpoUserPowerTlsSlot; dwTlsIndex
0x180003573  call    cs:__imp_TlsGetValue
0x180003579  test    eax, eax
0x18000357b  jz      short loc_1800035A9
0x18000357d  cmp     cs:UmpoUserPowerLockThread, 0
0x180003584  jnz     short loc_1800035A9
0x180003586  add     rsp, 28h
0x18000358a  jmp     ReleaseUserPowerLock
0x18000358f  add     rsp, 28h
0x180003593  retn
0x180003594  lea     rax, [rcx-1]
0x180003598  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000359c  ja      short loc_18000358F
0x18000359e  add     rsp, 28h
0x1800035a2  jmp     cs:__imp_RegCloseKey
0x1800035a9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800035ae  jmp     short loc_180003586
```
