# CommonUtil::CMpCriticalSection::~CMpCriticalSection(void)

- ea: `0x18003f944`
- end: `0x18003f95c`
- name: `??1CMpCriticalSection@CommonUtil@@QEAA@XZ`
- size: `24`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18003f9c0`
- `0x18003fa3c`

## callees

- `0x18003f944`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003f951`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003f951`

## pseudocode

```c
void __fastcall CommonUtil::CMpCriticalSection::~CMpCriticalSection(struct _RTL_CRITICAL_SECTION *this)
{
  if ( this->RecursionCount != 252844334 )
    DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x18003f944  sub     rsp, 28h
0x18003f948  cmp     dword ptr [rcx+0Ch], 0F12192Eh
0x18003f94f  jz      short loc_18003F957
0x18003f951  call    cs:__imp_DeleteCriticalSection
0x18003f957  add     rsp, 28h
0x18003f95b  retn
```
