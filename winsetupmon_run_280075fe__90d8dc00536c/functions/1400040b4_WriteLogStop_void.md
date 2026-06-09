# WriteLogStop(void)

- ea: `0x1400040b4`
- end: `0x14000411e`
- name: `?WriteLogStop@@YAXXZ`
- size: `106`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140003554`
- `0x14000362c`

## callees

- `0x140003944`
- `0x1400040b4`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x1400040f4`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400040f4`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400040bf`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400040bf`

## pseudocode

```c
void WriteLogStop(void)
{
  ExAcquireFastMutex(&FastMutex);
  if ( DestinationString.Length )
    WriteLogMessage(1, L"**** SESSION STOP: %wZ ****", &DestinationString);
  ExReleaseFastMutex(&FastMutex);
  WriteLogMessage(1, L"Logging stopped to : %wZ", &String2);
}

```

## disassembly

```asm
0x1400040b4  sub     rsp, 28h
0x1400040b8  lea     rcx, FastMutex; FastMutex
0x1400040bf  call    cs:__imp_ExAcquireFastMutex
0x1400040c6  nop     dword ptr [rax+rax+00h]
0x1400040cb  cmp     cs:DestinationString.Length, 0
0x1400040d3  jbe     short loc_1400040ED
0x1400040d5  lea     r8, DestinationString
0x1400040dc  mov     ecx, 1
0x1400040e1  lea     rdx, aSessionStopWz; "**** SESSION STOP: %wZ ****"
0x1400040e8  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x1400040ed  lea     rcx, FastMutex; FastMutex
0x1400040f4  call    cs:__imp_ExReleaseFastMutex
0x1400040fb  nop     dword ptr [rax+rax+00h]
0x140004100  lea     r8, String2
0x140004107  mov     ecx, 1
0x14000410c  lea     rdx, aLoggingStopped; "Logging stopped to : %wZ"
0x140004113  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x140004118  add     rsp, 28h
0x14000411c  retn
```
