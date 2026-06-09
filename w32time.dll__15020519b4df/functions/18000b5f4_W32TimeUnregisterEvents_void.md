# W32TimeUnregisterEvents(void)

- ea: `0x18000b5f4`
- end: `0x18000b659`
- name: `?W32TimeUnregisterEvents@@YAXXZ`
- size: `101`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x180009a80`
- `0x18000be58`

## callees

- `0x18000b5f4`
- `0x18000bc88`
- `0x18000c23c`
- `0x18003d2d8`

## import_xrefs

- `ntdll!RtlDeleteResource` at `0x18000b644`
- `ntdll!RtlDeleteResource` at `0x18000b644`

## pseudocode

```c
void W32TimeUnregisterEvents(void)
{
  void *v0; // rbx

  UninitializeEvents();
  v0 = _pscvec;
  if ( _pscvec )
  {
    std::vector<AutoPtr<SourceChangeLogEntry>,MyThrowingAllocator<AutoPtr<SourceChangeLogEntry>>>::~vector<AutoPtr<SourceChangeLogEntry>,MyThrowingAllocator<AutoPtr<SourceChangeLogEntry>>>(_pscvec);
    operator delete(v0);
    _pscvec = 0;
  }
  if ( _bIsCsStateInitialized )
  {
    RtlDeleteResource(&_csState);
    _bIsCsStateInitialized = 0;
  }
}

```

## disassembly

```asm
0x18000b5f4  push    rbx
0x18000b5f6  sub     rsp, 20h
0x18000b5fa  call    UninitializeEvents
0x18000b5ff  mov     rbx, cs:?_pscvec@@3PEAV?$vector@V?$AutoPtr@VSourceChangeLogEntry@@@@V?$MyThrowingAllocator@V?$AutoPtr@VSourceChangeLogEntry@@@@@@@std@@EA; std::vector<AutoPtr<SourceChangeLogEntry>,MyThrowingAllocator<AutoPtr<SourceChangeLogEntry>>> * _pscvec
0x18000b606  test    rbx, rbx
0x18000b609  jnz     short loc_18000B61B
0x18000b60b  cmp     cs:?_bIsCsStateInitialized@@3_NA, 0; bool _bIsCsStateInitialized
0x18000b612  jnz     short loc_18000B63D
0x18000b614  add     rsp, 20h
0x18000b618  pop     rbx
0x18000b619  retn
0x18000b61b  mov     rcx, rbx
0x18000b61e  call    ??1?$vector@V?$AutoPtr@VSourceChangeLogEntry@@@@V?$MyThrowingAllocator@V?$AutoPtr@VSourceChangeLogEntry@@@@@@@std@@QEAA@XZ; std::vector<AutoPtr<SourceChangeLogEntry>,MyThrowingAllocator<AutoPtr<SourceChangeLogEntry>>>::~vector<AutoPtr<SourceChangeLogEntry>,MyThrowingAllocator<AutoPtr<SourceChangeLogEntry>>>(void)
0x18000b623  mov     edx, 18h; unsigned __int64
0x18000b628  mov     rcx, rbx; void *
0x18000b62b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000b630  mov     cs:?_pscvec@@3PEAV?$vector@V?$AutoPtr@VSourceChangeLogEntry@@@@V?$MyThrowingAllocator@V?$AutoPtr@VSourceChangeLogEntry@@@@@@@std@@EA, 0; std::vector<AutoPtr<SourceChangeLogEntry>,MyThrowingAllocator<AutoPtr<SourceChangeLogEntry>>> * _pscvec
0x18000b63b  jmp     short loc_18000B60B
0x18000b63d  lea     rcx, ?_csState@@3U_RTL_RESOURCE@@A; Resource
0x18000b644  call    cs:__imp_RtlDeleteResource
0x18000b64b  nop     dword ptr [rax+rax+00h]
0x18000b650  mov     cs:?_bIsCsStateInitialized@@3_NA, 0; bool _bIsCsStateInitialized
0x18000b657  jmp     short loc_18000B614
```
