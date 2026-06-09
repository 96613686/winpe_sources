# QueryServiceHeapInformation

- ea: `0x140001120`
- end: `0x140001170`
- name: `QueryServiceHeapInformation`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1400086f8`

## callees

- `0x140001120`
- `0x140001180`
- `0x140001280`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x140001124`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x140001124`

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
0x140001120  sub     rsp, 28h
0x140001124  call    cs:__imp_GetTickCount64
0x14000112b  nop     dword ptr [rax+rax+00h]
0x140001130  mov     rcx, rax
0x140001133  sub     rcx, cs:g_LastQueryHeapInfoTime
0x14000113a  cmp     rcx, 0BB8h
0x140001141  jnb     short loc_14000114E
0x140001143  mov     eax, 80h
0x140001148  add     rsp, 28h
0x14000114c  retn
0x14000114e  cmp     cs:ServiceCount, 1
0x140001155  mov     cs:g_LastQueryHeapInfoTime, rax
0x14000115c  ja      short loc_140001167
0x14000115e  add     rsp, 28h
0x140001162  jmp     QuerySingleServiceHeapInformation
0x140001167  add     rsp, 28h
0x14000116b  jmp     QueryMultipleServicesHeapInformation
```
