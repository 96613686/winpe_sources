# ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)

- ea: `0x180002b4c`
- end: `0x180002b75`
- name: `??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ`
- size: `41`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000367c`
- `0x180006b88`
- `0x180007044`
- `0x18001f0f6`

## callees

- `0x180002b4c`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180002b5e`
- `KERNEL32!LeaveCriticalSection` at `0x180002b5e`

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
0x180002b4c  push    rbx
0x180002b4e  sub     rsp, 20h
0x180002b52  cmp     byte ptr [rcx+8], 0
0x180002b56  mov     rbx, rcx
0x180002b59  jz      short loc_180002B6E
0x180002b5b  mov     rcx, [rcx]; lpCriticalSection
0x180002b5e  call    cs:__imp_LeaveCriticalSection
0x180002b65  nop     dword ptr [rax+rax+00h]
0x180002b6a  mov     byte ptr [rbx+8], 0
0x180002b6e  add     rsp, 20h
0x180002b72  pop     rbx
0x180002b73  retn
```
