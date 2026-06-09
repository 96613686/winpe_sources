# CleanupState(void)

- ea: `0x180033e2c`
- end: `0x180033e83`
- name: `?CleanupState@@YAXXZ`
- size: `87`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180009a80`
- `0x18002b850`

## callees

- `0x180018138`
- `0x18001d9a0`
- `0x180033e2c`

## import_xrefs

- `api-ms-win-core-perfcounters-l1-1-0!PerfStopProvider` at `0x180033e77`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x180033e40`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x180033e40`

## string_xrefs

- `0x180033e5f`: `PerfDeleteInstance failed. Error:0x%08x\n`

## pseudocode

```c
void CleanupState(void)
{
  ULONG v0; // ebx

  v0 = PerfDeleteInstance(hDataSource_W32TimePerfCounters_1, InstanceBlock);
  if ( v0 && (unsigned __int8)FileLogAllowEntry(0) )
    FileLogAdd(L"PerfDeleteInstance failed. Error:0x%08x\n", v0);
  PerfStopProvider(hDataSource_W32TimePerfCounters_1);
}

```

## disassembly

```asm
0x180033e2c  push    rbx
0x180033e2e  sub     rsp, 20h
0x180033e32  mov     rdx, cs:InstanceBlock; InstanceBlock
0x180033e39  mov     rcx, cs:hDataSource_W32TimePerfCounters_1; Provider
0x180033e40  call    cs:__imp_PerfDeleteInstance
0x180033e47  nop     dword ptr [rax+rax+00h]
0x180033e4c  mov     ebx, eax
0x180033e4e  test    eax, eax
0x180033e50  jz      short loc_180033E6B
0x180033e52  xor     ecx, ecx
0x180033e54  call    FileLogAllowEntry
0x180033e59  test    al, al
0x180033e5b  jz      short loc_180033E6B
0x180033e5d  mov     edx, ebx
0x180033e5f  lea     rcx, aPerfdeleteinst; "PerfDeleteInstance failed. Error:0x%08x"...
0x180033e66  call    FileLogAdd
0x180033e6b  mov     rcx, cs:hDataSource_W32TimePerfCounters_1
0x180033e72  add     rsp, 20h
0x180033e76  pop     rbx
0x180033e77  jmp     cs:__imp_PerfStopProvider
```
