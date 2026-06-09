# ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)

- ea: `0x180016630`
- end: `0x180016653`
- name: `??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ`
- size: `35`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180016ab4`
- `0x18001795c`
- `0x18001ac04`

## callees

- `0x180016630`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016642`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016642`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180016630  push    rbx
0x180016632  sub     rsp, 20h
0x180016636  mov     rbx, rcx
0x180016639  cmp     byte ptr [rcx+8], 0
0x18001663d  jz      short loc_18001664D
0x18001663f  mov     rcx, [rcx]; lpCriticalSection
0x180016642  call    cs:__imp_LeaveCriticalSection
0x180016648  nop
0x180016649  mov     byte ptr [rbx+8], 0
0x18001664d  add     rsp, 20h
0x180016651  pop     rbx
0x180016652  retn
```
