# SmpAsyncMemoryConfiguration

- ea: `0x14000f120`
- end: `0x14000f279`
- name: `SmpAsyncMemoryConfiguration`
- size: `345`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x14000d418`
- `0x14000d4c0`
- `0x14000d6f8`
- `0x14000f120`
- `0x14000fcf8`
- `0x1400108cc`
- `0x140010c5c`
- `0x140010dc8`

## import_xrefs

- `ntdll!NtClose` at `0x14000f268`
- `ntdll!NtClose` at `0x14000f268`
- `ntdll!NtSetSystemInformation` at `0x14000f181`
- `ntdll!NtSetSystemInformation` at `0x14000f181`
- `ntdll!NtInitializeRegistry` at `0x14000f256`
- `ntdll!NtInitializeRegistry` at `0x14000f256`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x14000f246`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x14000f246`

## string_xrefs

- `0x14000f149`: `SmpAsyncMemoryConfiguration`
- `0x14000f18e`: `SmpAsyncMemoryConfiguration`
- `0x14000f1d0`: `SmpAsyncMemoryConfiguration`

## pseudocode

```c
NTSTATUS SmpAsyncMemoryConfiguration()
{
  NTSTATUS result; // eax
  char v1; // bl
  _DWORD SystemInformation[6]; // [rsp+40h] [rbp-18h] BYREF
  char v3; // [rsp+78h] [rbp+20h] BYREF

  SystemInformation[0] = 0;
  result = SmpPagefileInitialize();
  if ( result >= 0 )
  {
    result = SmpNtSerializeBoot();
    if ( result < 0 )
      result = SmpLogFailure("SmpAsyncMemoryConfiguration", 4716, (unsigned int)result);
    if ( !SmpHostSmss )
      goto LABEL_9;
    v1 = 1;
    if ( !SmpUseDedicatedDumpFile )
    {
      SystemInformation[0] = 0;
      result = NtSetSystemInformation(SystemCrashDumpStateInformation, SystemInformation, 4u);
      if ( result < 0 )
        result = SmpLogFailure("SmpAsyncMemoryConfiguration", 4735, (unsigned int)result);
    }
    if ( !SmpHostSmss )
    {
LABEL_9:
      v1 = 0;
      SmpPagefileOnOsVolume = 0;
    }
    if ( SmpMiniNTBoot == 1 )
    {
      v3 = 0;
      result = SmpIsRamdiskBoot(&v3);
      if ( result < 0 )
        result = SmpLogFailure("SmpAsyncMemoryConfiguration", 4767, (unsigned int)result);
      if ( v3 == 1 )
        v1 = 0;
      else
        SmpPagefileOnOsVolume = 1;
    }
    if ( !SmpMiniNTBoot )
      result = SmpCheckMemoryCoolingCompatibility();
    if ( v1 == 1 )
    {
      if ( !SmpMiniNTBoot )
      {
        SmpEnableCachingOnDedicatedMemoryWorker();
        RtlSubscribeWnfStateChangeNotification(
          &SmpPhysicalMemoryChangeSubscription,
          WNF_MM_PHYSICAL_MEMORY_CHANGE,
          0,
          SmpDedicatedMemoryCachingCallback,
          0,
          0,
          0,
          1);
      }
      SmpCreatePagingFiles();
      result = NtInitializeRegistry(2u);
    }
    if ( SmpCrashDumpKey )
      return NtClose(SmpCrashDumpKey);
  }
  return result;
}

```

## disassembly

```asm
0x14000f120  mov     [rsp+arg_0], rbx
0x14000f125  push    rdi
0x14000f126  sub     rsp, 50h
0x14000f12a  xor     edi, edi
0x14000f12c  mov     [rsp+58h+SystemInformation], edi
0x14000f130  call    SmpPagefileInitialize
0x14000f135  test    eax, eax
0x14000f137  js      loc_14000F26E
0x14000f13d  call    SmpNtSerializeBoot
0x14000f142  test    eax, eax
0x14000f144  jns     short loc_14000F15A
0x14000f146  mov     r8d, eax
0x14000f149  lea     rcx, aSmpasyncmemory; "SmpAsyncMemoryConfiguration"
0x14000f150  mov     edx, 126Ch
0x14000f155  call    SmpLogFailure
0x14000f15a  cmp     cs:SmpHostSmss, dil
0x14000f161  jz      short loc_14000F1A8
0x14000f163  cmp     cs:SmpUseDedicatedDumpFile, dil
0x14000f16a  mov     bl, 1
0x14000f16c  jnz     short loc_14000F19F
0x14000f16e  mov     r8d, 4; SystemInformationLength
0x14000f174  mov     [rsp+58h+SystemInformation], edi
0x14000f178  lea     rdx, [rsp+58h+SystemInformation]; SystemInformation
0x14000f17d  lea     ecx, [r8+1Eh]; SystemInformationClass
0x14000f181  call    cs:__imp_NtSetSystemInformation
0x14000f187  test    eax, eax
0x14000f189  jns     short loc_14000F19F
0x14000f18b  mov     r8d, eax
0x14000f18e  lea     rcx, aSmpasyncmemory; "SmpAsyncMemoryConfiguration"
0x14000f195  mov     edx, 127Fh
0x14000f19a  call    SmpLogFailure
0x14000f19f  cmp     cs:SmpHostSmss, dil
0x14000f1a6  jnz     short loc_14000F1B1
0x14000f1a8  mov     bl, dil
0x14000f1ab  mov     cs:SmpPagefileOnOsVolume, edi
0x14000f1b1  cmp     cs:SmpMiniNTBoot, 1
0x14000f1b8  jnz     short loc_14000F1F7
0x14000f1ba  lea     rcx, [rsp+58h+arg_18]
0x14000f1bf  mov     [rsp+58h+arg_18], dil
0x14000f1c4  call    SmpIsRamdiskBoot
0x14000f1c9  test    eax, eax
0x14000f1cb  jns     short loc_14000F1E1
0x14000f1cd  mov     r8d, eax
0x14000f1d0  lea     rcx, aSmpasyncmemory; "SmpAsyncMemoryConfiguration"
0x14000f1d7  mov     edx, 129Fh
0x14000f1dc  call    SmpLogFailure
0x14000f1e1  cmp     [rsp+58h+arg_18], 1
0x14000f1e6  jnz     short loc_14000F1ED
0x14000f1e8  mov     bl, dil
0x14000f1eb  jmp     short loc_14000F1F7
0x14000f1ed  mov     cs:SmpPagefileOnOsVolume, 1
0x14000f1f7  cmp     cs:SmpMiniNTBoot, dil
0x14000f1fe  jnz     short loc_14000F205
0x14000f200  call    SmpCheckMemoryCoolingCompatibility
0x14000f205  cmp     bl, 1
0x14000f208  jnz     short loc_14000F25C
0x14000f20a  cmp     cs:SmpMiniNTBoot, dil
0x14000f211  jnz     short loc_14000F24C
0x14000f213  call    SmpEnableCachingOnDedicatedMemoryWorker
0x14000f218  mov     rdx, cs:WNF_MM_PHYSICAL_MEMORY_CHANGE
0x14000f21f  lea     r9, SmpDedicatedMemoryCachingCallback
0x14000f226  mov     [rsp+58h+var_20], 1
0x14000f22e  lea     rcx, SmpPhysicalMemoryChangeSubscription
0x14000f235  mov     [rsp+58h+var_28], edi
0x14000f239  xor     r8d, r8d
0x14000f23c  mov     [rsp+58h+var_30], rdi
0x14000f241  mov     [rsp+58h+var_38], rdi
0x14000f246  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x14000f24c  call    SmpCreatePagingFiles
0x14000f251  mov     ecx, 2; Flag
0x14000f256  call    cs:__imp_NtInitializeRegistry
0x14000f25c  mov     rcx, cs:SmpCrashDumpKey; Handle
0x14000f263  test    rcx, rcx
0x14000f266  jz      short loc_14000F26E
0x14000f268  call    cs:__imp_NtClose
0x14000f26e  mov     rbx, [rsp+58h+arg_0]
0x14000f273  add     rsp, 50h
0x14000f277  pop     rdi
0x14000f278  retn
```
