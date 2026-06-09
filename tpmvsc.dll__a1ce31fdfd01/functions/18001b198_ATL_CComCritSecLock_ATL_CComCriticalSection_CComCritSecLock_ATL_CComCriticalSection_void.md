# ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)

- ea: `0x18001b198`
- end: `0x18001b1ba`
- name: `??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001b490`

## callees

- `0x18001b198`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b1aa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b1aa`

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
0x18001b198  push    rbx
0x18001b19a  sub     rsp, 20h
0x18001b19e  cmp     byte ptr [rcx+8], 0
0x18001b1a2  mov     rbx, rcx
0x18001b1a5  jz      short loc_18001B1B4
0x18001b1a7  mov     rcx, [rcx]; lpCriticalSection
0x18001b1aa  call    cs:__imp_LeaveCriticalSection
0x18001b1b0  mov     byte ptr [rbx+8], 0
0x18001b1b4  add     rsp, 20h
0x18001b1b8  pop     rbx
0x18001b1b9  retn
```
