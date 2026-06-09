# ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)

- ea: `0x1800042d0`
- end: `0x1800042f2`
- name: `??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ`
- size: `34`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800043e4`
- `0x180007d24`

## callees

- `0x1800042d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800042e2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800042e2`

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
0x1800042d0  push    rbx
0x1800042d2  sub     rsp, 20h
0x1800042d6  cmp     byte ptr [rcx+8], 0
0x1800042da  mov     rbx, rcx
0x1800042dd  jz      short loc_1800042EC
0x1800042df  mov     rcx, [rcx]; lpCriticalSection
0x1800042e2  call    cs:__imp_LeaveCriticalSection
0x1800042e8  mov     byte ptr [rbx+8], 0
0x1800042ec  add     rsp, 20h
0x1800042f0  pop     rbx
0x1800042f1  retn
```
