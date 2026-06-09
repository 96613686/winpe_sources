# ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)

- ea: `0x1800248a8`
- end: `0x1800248ca`
- name: `??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ`
- size: `34`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180025e60`
- `0x1800262bc`
- `0x1800278ec`
- `0x180027ef8`
- `0x180055f00`

## callees

- `0x1800248a8`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800248ba`
- `KERNEL32!LeaveCriticalSection` at `0x1800248ba`

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
0x1800248a8  push    rbx
0x1800248aa  sub     rsp, 20h
0x1800248ae  cmp     byte ptr [rcx+8], 0
0x1800248b2  mov     rbx, rcx
0x1800248b5  jz      short loc_1800248C4
0x1800248b7  mov     rcx, [rcx]; lpCriticalSection
0x1800248ba  call    cs:__imp_LeaveCriticalSection
0x1800248c0  mov     byte ptr [rbx+8], 0
0x1800248c4  add     rsp, 20h
0x1800248c8  pop     rbx
0x1800248c9  retn
```
