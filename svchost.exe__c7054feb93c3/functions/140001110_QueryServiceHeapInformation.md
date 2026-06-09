# QueryServiceHeapInformation

- ea: `0x140001110`
- end: `0x140001159`
- name: `QueryServiceHeapInformation`
- size: `73`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x140008124`

## callees

- `0x140001110`
- `0x140001160`
- `0x140001250`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x140001114`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x140001114`

## pseudocode

```c
__int64 QueryServiceHeapInformation()
{
  ULONGLONG TickCount64; // rax

  TickCount64 = GetTickCount64();
  if ( TickCount64 - g_LastQueryHeapInfoTime < 0xBB8 )
    return 128;
  g_LastQueryHeapInfoTime = TickCount64;
  if ( (unsigned int)ServiceCount > 1 )
    return QueryMultipleServicesHeapInformation();
  else
    return QuerySingleServiceHeapInformation();
}

```

## disassembly

```asm
0x140001110  sub     rsp, 28h
0x140001114  call    cs:__imp_GetTickCount64
0x14000111a  mov     rcx, rax
0x14000111d  sub     rcx, cs:g_LastQueryHeapInfoTime
0x140001124  cmp     rcx, 0BB8h
0x14000112b  jnb     short loc_140001137
0x14000112d  mov     eax, 80h
0x140001132  add     rsp, 28h
0x140001136  retn
0x140001137  cmp     cs:ServiceCount, 1
0x14000113e  mov     cs:g_LastQueryHeapInfoTime, rax
0x140001145  ja      short loc_140001150
0x140001147  add     rsp, 28h
0x14000114b  jmp     QuerySingleServiceHeapInformation
0x140001150  add     rsp, 28h
0x140001154  jmp     QueryMultipleServicesHeapInformation
```
