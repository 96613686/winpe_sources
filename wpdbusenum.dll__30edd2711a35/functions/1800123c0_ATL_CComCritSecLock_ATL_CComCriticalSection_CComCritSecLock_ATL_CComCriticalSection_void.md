# ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)

- ea: `0x1800123c0`
- end: `0x1800123e2`
- name: `??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180012420`

## callees

- `0x1800123c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800123d2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800123d2`

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
0x1800123c0  push    rbx
0x1800123c2  sub     rsp, 20h
0x1800123c6  cmp     byte ptr [rcx+8], 0
0x1800123ca  mov     rbx, rcx
0x1800123cd  jz      short loc_1800123DC
0x1800123cf  mov     rcx, [rcx]; lpCriticalSection
0x1800123d2  call    cs:__imp_LeaveCriticalSection
0x1800123d8  mov     byte ptr [rbx+8], 0
0x1800123dc  add     rsp, 20h
0x1800123e0  pop     rbx
0x1800123e1  retn
```
