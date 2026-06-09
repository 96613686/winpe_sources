# ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)

- ea: `0x1800268b4`
- end: `0x1800268dd`
- name: `??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800269d4`

## callees

- `0x1800268b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800268c6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800268c6`

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
0x1800268b4  push    rbx
0x1800268b6  sub     rsp, 20h
0x1800268ba  cmp     byte ptr [rcx+8], 0
0x1800268be  mov     rbx, rcx
0x1800268c1  jz      short loc_1800268D6
0x1800268c3  mov     rcx, [rcx]; lpCriticalSection
0x1800268c6  call    cs:__imp_LeaveCriticalSection
0x1800268cd  nop     dword ptr [rax+rax+00h]
0x1800268d2  mov     byte ptr [rbx+8], 0
0x1800268d6  add     rsp, 20h
0x1800268da  pop     rbx
0x1800268db  retn
```
