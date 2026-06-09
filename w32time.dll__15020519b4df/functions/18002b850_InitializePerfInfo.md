# InitializePerfInfo

- ea: `0x18002b850`
- end: `0x18002bb81`
- name: `InitializePerfInfo`
- size: `817`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180039100`

## callees

- `0x180018138`
- `0x18001d9a0`
- `0x18002b850`
- `0x18002bb88`
- `0x180033e2c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ba50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ba50`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x18002b8da`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x18002b8da`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x18002b90b`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x18002b93e`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x18002b971`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x18002b9a4`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x18002b9d7`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x18002ba06`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x18002baec`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x18002b90b`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x18002b93e`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x18002b971`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x18002b9a4`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x18002b9d7`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x18002ba06`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x18002baec`

## string_xrefs

- `0x18002b8c5`: `Windows Time Service`
- `0x18002ba71`: `W32time perf counters failed to create perf instance object. Error:0x%08x\n`

## pseudocode

```c
__int64 InitializePerfInfo()
{
  ULONG LastError; // ebx
  struct _PERF_COUNTERSET_INSTANCE *Instance; // rax

  if ( dword_1800A5288 )
  {
    if ( (unsigned __int8)FileLogAllowEntry(0) )
      FileLogAdd(L"W32time perf counters being initialized a second time.\n");
    return 0xFFFFFFFFLL;
  }
  else
  {
    g_ullComputedTimeOffsetUSec = 0;
    g_dwClockFreqAdjustment = 0;
    g_dwClockFreqAdjustmentPPB = 0;
    g_dwNtpRoundtripDelayUSec = 0;
    g_dwNtpTimeSourceCount = 0;
    g_ullNtpServerIncomingRequestRate = 0;
    g_ullNtpServerOutgoingResponseRate = 0;
    LastError = PerfAutoInitialize();
    if ( LastError )
    {
      if ( (unsigned __int8)FileLogAllowEntry(0) )
        FileLogAdd(L"W32time perf counters failed to initialize. Error:0x%08x\n", LastError);
    }
    else
    {
      Instance = PerfCreateInstance(
                   hDataSource_W32TimePerfCounters_1,
                   &CtrSetGuid_W32TimePerfCounters_1_1,
                   L"Windows Time Service",
                   0x7E0u);
      InstanceBlock = Instance;
      if ( Instance )
      {
        LastError = PerfSetCounterRefValue(
                      hDataSource_W32TimePerfCounters_1,
                      Instance,
                      LastError + 2,
                      &g_ullComputedTimeOffsetUSec);
        if ( LastError )
        {
          if ( (unsigned __int8)FileLogAllowEntry(0) )
            FileLogAdd(L"W32time perf counters failed to set reference value2. Error:0x%08x\n", LastError);
        }
        else
        {
          LastError = PerfSetCounterRefValue(
                        hDataSource_W32TimePerfCounters_1,
                        InstanceBlock,
                        3u,
                        &g_dwClockFreqAdjustment);
          if ( LastError
            || (LastError = PerfSetCounterRefValue(
                              hDataSource_W32TimePerfCounters_1,
                              InstanceBlock,
                              4u,
                              &g_dwClockFreqAdjustmentPPB)) != 0 )
          {
            if ( (unsigned __int8)FileLogAllowEntry(0) )
              FileLogAdd(L"W32time perf counters failed to set reference value3. Error:0x%08x\n", LastError);
          }
          else
          {
            LastError = PerfSetCounterRefValue(
                          hDataSource_W32TimePerfCounters_1,
                          InstanceBlock,
                          0xBu,
                          &g_dwNtpRoundtripDelayUSec);
            if ( LastError )
            {
              if ( (unsigned __int8)FileLogAllowEntry(0) )
                FileLogAdd(L"W32time perf counters failed to set reference value11. Error:0x%08x\n", LastError);
            }
            else
            {
              LastError = PerfSetCounterRefValue(
                            hDataSource_W32TimePerfCounters_1,
                            InstanceBlock,
                            0xCu,
                            &g_dwNtpTimeSourceCount);
              if ( LastError )
              {
                if ( (unsigned __int8)FileLogAllowEntry(0) )
                  FileLogAdd(L"W32time perf counters failed to set reference value12. Error:0x%08x\n", LastError);
              }
              else
              {
                LastError = PerfSetCounterRefValue(
                              hDataSource_W32TimePerfCounters_1,
                              InstanceBlock,
                              0x15u,
                              &g_ullNtpServerIncomingRequestRate);
                if ( LastError )
                {
                  if ( (unsigned __int8)FileLogAllowEntry(0) )
                    FileLogAdd(L"W32time perf counters failed to set reference value21. Error:0x%08x\n", LastError);
                }
                else
                {
                  LastError = PerfSetCounterRefValue(
                                hDataSource_W32TimePerfCounters_1,
                                InstanceBlock,
                                0x16u,
                                &g_ullNtpServerOutgoingResponseRate);
                  if ( LastError )
                  {
                    if ( (unsigned __int8)FileLogAllowEntry(0) )
                      FileLogAdd(L"W32time perf counters failed to set reference value22. Error:0x%08x\n", LastError);
                  }
                  else
                  {
                    if ( (unsigned __int8)FileLogAllowEntry(135) )
                      FileLogAdd(L"W32time perf counters Initialized\n");
                    dword_1800A5288 = 1;
                  }
                }
              }
            }
          }
        }
      }
      else
      {
        LastError = GetLastError();
        if ( (unsigned __int8)FileLogAllowEntry(0) )
          FileLogAdd(L"W32time perf counters failed to create perf instance object. Error:0x%08x\n", LastError);
      }
      if ( LastError )
        CleanupState();
    }
    return LastError;
  }
}

```

## disassembly

```asm
0x18002b850  push    rbx
0x18002b852  sub     rsp, 30h
0x18002b856  cmp     cs:dword_1800A5288, 0
0x18002b85d  jnz     loc_18002BB5E
0x18002b863  mov     cs:g_ullComputedTimeOffsetUSec, 0
0x18002b86e  mov     cs:g_dwClockFreqAdjustment, 0
0x18002b878  mov     cs:g_dwClockFreqAdjustmentPPB, 0
0x18002b882  mov     cs:g_dwNtpRoundtripDelayUSec, 0
0x18002b88c  mov     cs:g_dwNtpTimeSourceCount, 0
0x18002b896  mov     cs:g_ullNtpServerIncomingRequestRate, 0
0x18002b8a1  mov     cs:g_ullNtpServerOutgoingResponseRate, 0
0x18002b8ac  call    PerfAutoInitialize
0x18002b8b1  mov     ebx, eax
0x18002b8b3  mov     [rsp+38h+var_18], eax
0x18002b8b7  test    eax, eax
0x18002b8b9  jnz     loc_18002BB43
0x18002b8bf  mov     r9d, 7E0h; Id
0x18002b8c5  lea     r8, Name; "Windows Time Service"
0x18002b8cc  lea     rdx, CtrSetGuid_W32TimePerfCounters_1_1; CounterSetGuid
0x18002b8d3  mov     rcx, cs:hDataSource_W32TimePerfCounters_1; ProviderHandle
0x18002b8da  call    cs:__imp_PerfCreateInstance
0x18002b8e1  nop     dword ptr [rax+rax+00h]
0x18002b8e6  mov     cs:InstanceBlock, rax
0x18002b8ed  test    rax, rax
0x18002b8f0  jz      loc_18002BA50
0x18002b8f6  lea     r9, g_ullComputedTimeOffsetUSec; Address
0x18002b8fd  lea     r8d, [rbx+2]; CounterId
0x18002b901  mov     rdx, rax; Instance
0x18002b904  mov     rcx, cs:hDataSource_W32TimePerfCounters_1; Provider
0x18002b90b  call    cs:__imp_PerfSetCounterRefValue
0x18002b912  nop     dword ptr [rax+rax+00h]
0x18002b917  mov     ebx, eax
0x18002b919  mov     [rsp+38h+var_18], eax
0x18002b91d  test    eax, eax
0x18002b91f  jnz     loc_18002BA8D
0x18002b925  lea     r9, g_dwClockFreqAdjustment; Address
0x18002b92c  lea     r8d, [rax+3]; CounterId
0x18002b930  mov     rdx, cs:InstanceBlock; Instance
0x18002b937  mov     rcx, cs:hDataSource_W32TimePerfCounters_1; Provider
0x18002b93e  call    cs:__imp_PerfSetCounterRefValue
0x18002b945  nop     dword ptr [rax+rax+00h]
0x18002b94a  mov     ebx, eax
0x18002b94c  mov     [rsp+38h+var_18], eax
0x18002b950  test    eax, eax
0x18002b952  jnz     loc_18002BAA5
0x18002b958  lea     r9, g_dwClockFreqAdjustmentPPB; Address
0x18002b95f  lea     r8d, [rax+4]; CounterId
0x18002b963  mov     rdx, cs:InstanceBlock; Instance
0x18002b96a  mov     rcx, cs:hDataSource_W32TimePerfCounters_1; Provider
0x18002b971  call    cs:__imp_PerfSetCounterRefValue
0x18002b978  nop     dword ptr [rax+rax+00h]
0x18002b97d  mov     ebx, eax
0x18002b97f  mov     [rsp+38h+var_18], eax
0x18002b983  test    eax, eax
0x18002b985  jnz     loc_18002BAA5
0x18002b98b  lea     r9, g_dwNtpRoundtripDelayUSec; Address
0x18002b992  lea     r8d, [rax+0Bh]; CounterId
0x18002b996  mov     rdx, cs:InstanceBlock; Instance
0x18002b99d  mov     rcx, cs:hDataSource_W32TimePerfCounters_1; Provider
0x18002b9a4  call    cs:__imp_PerfSetCounterRefValue
0x18002b9ab  nop     dword ptr [rax+rax+00h]
0x18002b9b0  mov     ebx, eax
0x18002b9b2  mov     [rsp+38h+var_18], eax
0x18002b9b6  test    eax, eax
0x18002b9b8  jnz     loc_18002BABD
0x18002b9be  lea     r9, g_dwNtpTimeSourceCount; Address
0x18002b9c5  lea     r8d, [rax+0Ch]; CounterId
0x18002b9c9  mov     rdx, cs:InstanceBlock; Instance
0x18002b9d0  mov     rcx, cs:hDataSource_W32TimePerfCounters_1; Provider
0x18002b9d7  call    cs:__imp_PerfSetCounterRefValue
0x18002b9de  nop     dword ptr [rax+rax+00h]
0x18002b9e3  mov     ebx, eax
0x18002b9e5  mov     [rsp+38h+var_18], eax
0x18002b9e9  test    eax, eax
0x18002b9eb  jnz     short loc_18002BA38
0x18002b9ed  lea     r9, g_ullNtpServerIncomingRequestRate; Address
0x18002b9f4  lea     r8d, [rax+15h]; CounterId
0x18002b9f8  mov     rdx, cs:InstanceBlock; Instance
0x18002b9ff  mov     rcx, cs:hDataSource_W32TimePerfCounters_1; Provider
0x18002ba06  call    cs:__imp_PerfSetCounterRefValue
0x18002ba0d  nop     dword ptr [rax+rax+00h]
0x18002ba12  mov     ebx, eax
0x18002ba14  mov     [rsp+38h+var_18], eax
0x18002ba18  test    eax, eax
0x18002ba1a  jz      loc_18002BAD1
0x18002ba20  xor     ecx, ecx
0x18002ba22  call    FileLogAllowEntry
0x18002ba27  test    al, al
0x18002ba29  jz      loc_18002BB36
0x18002ba2f  lea     rcx, aW32timePerfCou_9; "W32time perf counters failed to set ref"...
0x18002ba36  jmp     short loc_18002BA81
0x18002ba38  xor     ecx, ecx
0x18002ba3a  call    FileLogAllowEntry
0x18002ba3f  test    al, al
0x18002ba41  jz      loc_18002BB36
0x18002ba47  lea     rcx, aW32timePerfCou_1; "W32time perf counters failed to set ref"...
0x18002ba4e  jmp     short loc_18002BA81
0x18002ba50  call    cs:__imp_GetLastError
0x18002ba57  nop     dword ptr [rax+rax+00h]
0x18002ba5c  mov     ebx, eax
0x18002ba5e  mov     [rsp+38h+var_18], eax
0x18002ba62  xor     ecx, ecx
0x18002ba64  call    FileLogAllowEntry
0x18002ba69  test    al, al
0x18002ba6b  jz      loc_18002BB36
0x18002ba71  lea     rcx, aW32timePerfCou; "W32time perf counters failed to create "...
0x18002ba78  jmp     short loc_18002BA81
0x18002ba7a  lea     rcx, aW32timePerfCou_2; "W32time perf counters failed to set ref"...
0x18002ba81  mov     edx, ebx
0x18002ba83  call    FileLogAdd
0x18002ba88  jmp     loc_18002BB36
0x18002ba8d  xor     ecx, ecx
0x18002ba8f  call    FileLogAllowEntry
0x18002ba94  test    al, al
0x18002ba96  jz      loc_18002BB36
0x18002ba9c  lea     rcx, aW32timePerfCou_6; "W32time perf counters failed to set ref"...
0x18002baa3  jmp     short loc_18002BA81
0x18002baa5  xor     ecx, ecx
0x18002baa7  call    FileLogAllowEntry
0x18002baac  test    al, al
0x18002baae  jz      loc_18002BB36
0x18002bab4  lea     rcx, aW32timePerfCou_5; "W32time perf counters failed to set ref"...
0x18002babb  jmp     short loc_18002BA81
0x18002babd  xor     ecx, ecx
0x18002babf  call    FileLogAllowEntry
0x18002bac4  test    al, al
0x18002bac6  jz      short loc_18002BB36
0x18002bac8  lea     rcx, aW32timePerfCou_0; "W32time perf counters failed to set ref"...
0x18002bacf  jmp     short loc_18002BA81
0x18002bad1  lea     r9, g_ullNtpServerOutgoingResponseRate; Address
0x18002bad8  mov     r8d, 16h; CounterId
0x18002bade  mov     rdx, cs:InstanceBlock; Instance
0x18002bae5  mov     rcx, cs:hDataSource_W32TimePerfCounters_1; Provider
0x18002baec  call    cs:__imp_PerfSetCounterRefValue
0x18002baf3  nop     dword ptr [rax+rax+00h]
0x18002baf8  mov     ebx, eax
0x18002bafa  mov     [rsp+38h+var_18], eax
0x18002bafe  test    eax, eax
0x18002bb00  jz      short loc_18002BB12
0x18002bb02  xor     ecx, ecx
0x18002bb04  call    FileLogAllowEntry
0x18002bb09  test    al, al
0x18002bb0b  jz      short loc_18002BB36
0x18002bb0d  jmp     loc_18002BA7A
0x18002bb12  mov     ecx, 87h
0x18002bb17  call    FileLogAllowEntry
0x18002bb1c  test    al, al
0x18002bb1e  jz      short loc_18002BB2C
0x18002bb20  lea     rcx, aW32timePerfCou_4; "W32time perf counters Initialized\n"
0x18002bb27  call    FileLogAdd
0x18002bb2c  mov     cs:dword_1800A5288, 1
0x18002bb36  test    ebx, ebx
0x18002bb38  jnz     short loc_18002BB7A
0x18002bb3a  mov     eax, ebx
0x18002bb3c  add     rsp, 30h
0x18002bb40  pop     rbx
0x18002bb41  retn
0x18002bb43  xor     ecx, ecx
0x18002bb45  call    FileLogAllowEntry
0x18002bb4a  test    al, al
0x18002bb4c  jz      short loc_18002BB3A
0x18002bb4e  mov     edx, ebx
0x18002bb50  lea     rcx, aW32timePerfCou_7; "W32time perf counters failed to initial"...
0x18002bb57  call    FileLogAdd
0x18002bb5c  jmp     short loc_18002BB3A
0x18002bb5e  xor     ecx, ecx
0x18002bb60  call    FileLogAllowEntry
0x18002bb65  test    al, al
0x18002bb67  jz      short loc_18002BB75
0x18002bb69  lea     rcx, aW32timePerfCou_3; "W32time perf counters being initialized"...
0x18002bb70  call    FileLogAdd
0x18002bb75  or      eax, 0FFFFFFFFh
0x18002bb78  jmp     short loc_18002BB3C
0x18002bb7a  call    ?CleanupState@@YAXXZ; CleanupState(void)
0x18002bb7f  jmp     short loc_18002BB3A
0x180067672  push    rbp
0x180067674  sub     rsp, 20h
0x180067678  mov     rbp, rdx
0x18006767b  cmp     dword ptr [rbp+20h], 0
0x18006767f  jz      short loc_180067687
0x180067681  call    ?CleanupState@@YAXXZ; CleanupState(void)
0x180067686  nop
0x180067687  add     rsp, 20h
0x18006768b  pop     rbp
0x18006768c  retn
```
