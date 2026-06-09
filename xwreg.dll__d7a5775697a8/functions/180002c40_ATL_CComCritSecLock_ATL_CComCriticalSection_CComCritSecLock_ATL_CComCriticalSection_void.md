# ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)

- ea: `0x180002c40`
- end: `0x180002c62`
- name: `??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ`
- size: `34`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003a30`
- `0x18000478c`

## callees

- `0x180002c40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002c52`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002c52`

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
0x180002c40  push    rbx
0x180002c42  sub     rsp, 20h
0x180002c46  cmp     byte ptr [rcx+8], 0
0x180002c4a  mov     rbx, rcx
0x180002c4d  jz      short loc_180002C5C
0x180002c4f  mov     rcx, [rcx]; lpCriticalSection
0x180002c52  call    cs:__imp_LeaveCriticalSection
0x180002c58  mov     byte ptr [rbx+8], 0
0x180002c5c  add     rsp, 20h
0x180002c60  pop     rbx
0x180002c61  retn
```
