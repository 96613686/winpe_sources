# SmpGetFirstSessionId

- ea: `0x14000accc`
- end: `0x14000acf8`
- name: `SmpGetFirstSessionId`
- size: `44`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callers

- `0x140005f64`

## callees

- `0x14000accc`

## import_xrefs

- `ntdll!RtlGetCurrentServiceSessionId` at `0x14000ace8`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x14000ace8`
- `ntdll!NtDelayExecution` at `0x14000ace2`
- `ntdll!NtDelayExecution` at `0x14000ace2`

## pseudocode

```c
__int64 SmpGetFirstSessionId()
{
  __int64 result; // rax
  LARGE_INTEGER Interval; // [rsp+30h] [rbp+8h] BYREF

  Interval.QuadPart = -2500000;
  while ( 1 )
  {
    result = RtlGetCurrentServiceSessionId();
    if ( (_DWORD)result != -1 )
      break;
    NtDelayExecution(0, &Interval);
  }
  return result;
}

```

## disassembly

```asm
0x14000accc  sub     rsp, 28h
0x14000acd0  mov     qword ptr [rsp+28h+Interval], 0FFFFFFFFFFD9DA60h
0x14000acd9  jmp     short loc_14000ACE8
0x14000acdb  lea     rdx, [rsp+28h+Interval]; Interval
0x14000ace0  xor     ecx, ecx; Alertable
0x14000ace2  call    cs:__imp_NtDelayExecution
0x14000ace8  call    cs:__imp_RtlGetCurrentServiceSessionId
0x14000acee  cmp     eax, 0FFFFFFFFh
0x14000acf1  jz      short loc_14000ACDB
0x14000acf3  add     rsp, 28h
0x14000acf7  retn
```
