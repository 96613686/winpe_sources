# MIME_MAP_TABLE::SetGlobalTable(MIME_MAP_TABLE * *)

- ea: `0x180005700`
- end: `0x180005788`
- name: `?SetGlobalTable@MIME_MAP_TABLE@@SAXPEAPEAV1@@Z`
- size: `136`
- prototype: `void __fastcall(struct MIME_MAP_TABLE **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800043d4`
- `0x1800054f0`

## callees

- `0x18000455c`
- `0x180005700`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005710`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005710`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005781`

## pseudocode

```c
void __fastcall MIME_MAP_TABLE::SetGlobalTable(struct MIME_MAP_TABLE **a1)
{
  AcquireSRWLockExclusive(&MIME_MAP_TABLE::sm_GlobalLock);
  if ( a1 )
  {
    if ( MIME_MAP_TABLE::sm_pGlobalTable )
    {
      MIME_MAP_TABLE::Dereference(*a1);
      _InterlockedIncrement((volatile signed __int32 *)MIME_MAP_TABLE::sm_pGlobalTable + 266);
      *a1 = MIME_MAP_TABLE::sm_pGlobalTable;
    }
    else
    {
      _InterlockedIncrement((volatile signed __int32 *)*a1 + 266);
      MIME_MAP_TABLE::sm_pGlobalTable = *a1;
    }
  }
  else if ( MIME_MAP_TABLE::sm_pGlobalTable )
  {
    MIME_MAP_TABLE::Dereference(MIME_MAP_TABLE::sm_pGlobalTable);
    MIME_MAP_TABLE::sm_pGlobalTable = 0;
  }
  ReleaseSRWLockExclusive(&MIME_MAP_TABLE::sm_GlobalLock);
}

```

## disassembly

```asm
0x180005700  push    rbx
0x180005702  sub     rsp, 20h
0x180005706  mov     rbx, rcx
0x180005709  lea     rcx, ?sm_GlobalLock@MIME_MAP_TABLE@@0U_RTL_SRWLOCK@@A; SRWLock
0x180005710  call    cs:__imp_AcquireSRWLockExclusive
0x180005716  test    rbx, rbx
0x180005719  jnz     short loc_180005735
0x18000571b  mov     rcx, cs:?sm_pGlobalTable@MIME_MAP_TABLE@@0PEAV1@EA; this
0x180005722  test    rcx, rcx
0x180005725  jz      short loc_180005775
0x180005727  call    ?Dereference@MIME_MAP_TABLE@@QEAAXXZ; MIME_MAP_TABLE::Dereference(void)
0x18000572c  mov     cs:?sm_pGlobalTable@MIME_MAP_TABLE@@0PEAV1@EA, rbx; MIME_MAP_TABLE * MIME_MAP_TABLE::sm_pGlobalTable
0x180005733  jmp     short loc_180005775
0x180005735  cmp     cs:?sm_pGlobalTable@MIME_MAP_TABLE@@0PEAV1@EA, 0; MIME_MAP_TABLE * MIME_MAP_TABLE::sm_pGlobalTable
0x18000573d  mov     rax, [rbx]
0x180005740  jz      short loc_180005764
0x180005742  mov     rcx, rax; this
0x180005745  call    ?Dereference@MIME_MAP_TABLE@@QEAAXXZ; MIME_MAP_TABLE::Dereference(void)
0x18000574a  mov     rax, cs:?sm_pGlobalTable@MIME_MAP_TABLE@@0PEAV1@EA; MIME_MAP_TABLE * MIME_MAP_TABLE::sm_pGlobalTable
0x180005751  lock inc dword ptr [rax+428h]
0x180005758  mov     rax, cs:?sm_pGlobalTable@MIME_MAP_TABLE@@0PEAV1@EA; MIME_MAP_TABLE * MIME_MAP_TABLE::sm_pGlobalTable
0x18000575f  mov     [rbx], rax
0x180005762  jmp     short loc_180005775
0x180005764  lock inc dword ptr [rax+428h]
0x18000576b  mov     rax, [rbx]
0x18000576e  mov     cs:?sm_pGlobalTable@MIME_MAP_TABLE@@0PEAV1@EA, rax; MIME_MAP_TABLE * MIME_MAP_TABLE::sm_pGlobalTable
0x180005775  lea     rcx, ?sm_GlobalLock@MIME_MAP_TABLE@@0U_RTL_SRWLOCK@@A; _RTL_SRWLOCK MIME_MAP_TABLE::sm_GlobalLock
0x18000577c  add     rsp, 20h
0x180005780  pop     rbx
0x180005781  jmp     cs:__imp_ReleaseSRWLockExclusive
```
