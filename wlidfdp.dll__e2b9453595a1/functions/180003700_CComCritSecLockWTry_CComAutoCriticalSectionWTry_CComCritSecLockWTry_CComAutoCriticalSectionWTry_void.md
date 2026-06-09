# CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>(void)

- ea: `0x180003700`
- end: `0x180003722`
- name: `??1?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(__int64)`
- caller_count: `17`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800037c0`
- `0x180006410`
- `0x180007b00`
- `0x18000a26c`
- `0x18000a3e8`
- `0x18000a998`
- `0x18000ab84`
- `0x18000aec0`
- `0x18000b5b4`
- `0x18000b700`
- `0x18000bbf8`
- `0x18000bc8c`
- `0x18000bfd0`
- `0x1800108a6`
- `0x180010b19`
- `0x1800110c7`
- `0x1800110eb`

## callees

- `0x180003700`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003712`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003712`

## pseudocode

```c
void __fastcall CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>(
        __int64 a1)
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
0x180003700  push    rbx
0x180003702  sub     rsp, 20h
0x180003706  cmp     byte ptr [rcx+8], 0
0x18000370a  mov     rbx, rcx
0x18000370d  jz      short loc_18000371C
0x18000370f  mov     rcx, [rcx]; lpCriticalSection
0x180003712  call    cs:__imp_LeaveCriticalSection
0x180003718  mov     byte ptr [rbx+8], 0
0x18000371c  add     rsp, 20h
0x180003720  pop     rbx
0x180003721  retn
```
