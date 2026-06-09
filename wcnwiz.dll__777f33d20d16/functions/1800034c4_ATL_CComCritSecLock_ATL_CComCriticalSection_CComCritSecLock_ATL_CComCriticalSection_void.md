# ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)

- ea: `0x1800034c4`
- end: `0x1800034e6`
- name: `??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ`
- size: `34`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180004948`
- `0x180006048`
- `0x1800061e4`
- `0x180006380`
- `0x18000651c`
- `0x1800066b8`
- `0x18000af30`
- `0x18000c020`
- `0x18000d070`
- `0x18000e440`

## callees

- `0x1800034c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800034d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800034d6`

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
0x1800034c4  push    rbx
0x1800034c6  sub     rsp, 20h
0x1800034ca  cmp     byte ptr [rcx+8], 0
0x1800034ce  mov     rbx, rcx
0x1800034d1  jz      short loc_1800034E0
0x1800034d3  mov     rcx, [rcx]; lpCriticalSection
0x1800034d6  call    cs:__imp_LeaveCriticalSection
0x1800034dc  mov     byte ptr [rbx+8], 0
0x1800034e0  add     rsp, 20h
0x1800034e4  pop     rbx
0x1800034e5  retn
```
