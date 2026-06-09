# ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)

- ea: `0x180015540`
- end: `0x180015562`
- name: `??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(__int64)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000c4e0`
- `0x180016908`
- `0x180016c40`
- `0x1800189a0`
- `0x18002fa49`

## callees

- `0x180015540`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015552`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015552`

## pseudocode

```c
void __fastcall ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(__int64 a1)
{
  if ( *(_BYTE *)(a1 + 8) )
  {
    LeaveCriticalSection(*(LPCRITICAL_SECTION *)a1);
    *(_BYTE *)(a1 + 8) = 0;
  }
}

```

## disassembly

```asm
0x180015540  push    rbx
0x180015542  sub     rsp, 20h
0x180015546  cmp     byte ptr [rcx+8], 0
0x18001554a  mov     rbx, rcx
0x18001554d  jz      short loc_18001555C
0x18001554f  mov     rcx, [rcx]; lpCriticalSection
0x180015552  call    cs:__imp_LeaveCriticalSection
0x180015558  mov     byte ptr [rbx+8], 0
0x18001555c  add     rsp, 20h
0x180015560  pop     rbx
0x180015561  retn
```
