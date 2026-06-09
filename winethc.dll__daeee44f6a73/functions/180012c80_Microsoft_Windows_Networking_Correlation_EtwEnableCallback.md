# Microsoft_Windows_Networking_Correlation_EtwEnableCallback

- ea: `0x180012c80`
- end: `0x180012c96`
- name: `Microsoft_Windows_Networking_Correlation_EtwEnableCallback`
- size: `22`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
void __fastcall Microsoft_Windows_Networking_Correlation_EtwEnableCallback(
        LPCGUID SourceId,
        __int32 IsEnabled,
        UCHAR Level,
        ULONGLONG MatchAnyKeyword)
{
  _InterlockedExchange(&Microsoft_Windows_Networking_CorrelationEnabled, IsEnabled);
  _InterlockedExchange(&Microsoft_Windows_Networking_CorrelationTraceActivityPayload, (MatchAnyKeyword >> 3) & 1);
}

```

## disassembly

```asm
0x180012c80  xchg    edx, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x180012c86  shr     r9, 3
0x180012c8a  and     r9d, 1
0x180012c8e  xchg    r9d, cs:Microsoft_Windows_Networking_CorrelationTraceActivityPayload
0x180012c95  retn
```
