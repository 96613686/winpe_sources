# ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)

- ea: `0x180011e04`
- end: `0x180011e26`
- name: `??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001e922`

## callees

- `0x180011e04`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011e16`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011e16`

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
0x180011e04  push    rbx
0x180011e06  sub     rsp, 20h
0x180011e0a  mov     rbx, rcx
0x180011e0d  cmp     byte ptr [rcx+8], 0
0x180011e11  jz      short loc_180011E20
0x180011e13  mov     rcx, [rcx]; lpCriticalSection
0x180011e16  call    cs:__imp_LeaveCriticalSection
0x180011e1c  mov     byte ptr [rbx+8], 0
0x180011e20  add     rsp, 20h
0x180011e24  pop     rbx
0x180011e25  retn
```
