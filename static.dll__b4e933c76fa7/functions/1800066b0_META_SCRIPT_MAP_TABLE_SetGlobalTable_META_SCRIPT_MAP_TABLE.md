# META_SCRIPT_MAP_TABLE::SetGlobalTable(META_SCRIPT_MAP_TABLE * *)

- ea: `0x1800066b0`
- end: `0x180006730`
- name: `?SetGlobalTable@META_SCRIPT_MAP_TABLE@@SAXPEAPEAV1@@Z`
- size: `128`
- prototype: `void __fastcall(struct META_SCRIPT_MAP_TABLE **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000439c`
- `0x180005e30`

## callees

- `0x180004528`
- `0x1800066b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800066c0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800066c0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006729`

## pseudocode

```c
void __fastcall META_SCRIPT_MAP_TABLE::SetGlobalTable(struct META_SCRIPT_MAP_TABLE **a1)
{
  AcquireSRWLockExclusive(&META_SCRIPT_MAP_TABLE::sm_GlobalLock);
  if ( a1 )
  {
    if ( META_SCRIPT_MAP_TABLE::sm_pGlobalTable )
    {
      META_SCRIPT_MAP_TABLE::Dereference(*a1);
      _InterlockedIncrement((volatile signed __int32 *)META_SCRIPT_MAP_TABLE::sm_pGlobalTable);
      *a1 = META_SCRIPT_MAP_TABLE::sm_pGlobalTable;
    }
    else
    {
      _InterlockedIncrement((volatile signed __int32 *)*a1);
      META_SCRIPT_MAP_TABLE::sm_pGlobalTable = *a1;
    }
  }
  else if ( META_SCRIPT_MAP_TABLE::sm_pGlobalTable )
  {
    META_SCRIPT_MAP_TABLE::Dereference(META_SCRIPT_MAP_TABLE::sm_pGlobalTable);
    META_SCRIPT_MAP_TABLE::sm_pGlobalTable = 0;
  }
  ReleaseSRWLockExclusive(&META_SCRIPT_MAP_TABLE::sm_GlobalLock);
}

```

## disassembly

```asm
0x1800066b0  push    rbx
0x1800066b2  sub     rsp, 20h
0x1800066b6  mov     rbx, rcx
0x1800066b9  lea     rcx, ?sm_GlobalLock@META_SCRIPT_MAP_TABLE@@0U_RTL_SRWLOCK@@A; SRWLock
0x1800066c0  call    cs:__imp_AcquireSRWLockExclusive
0x1800066c6  test    rbx, rbx
0x1800066c9  jnz     short loc_1800066E5
0x1800066cb  mov     rcx, cs:?sm_pGlobalTable@META_SCRIPT_MAP_TABLE@@0PEAV1@EA; this
0x1800066d2  test    rcx, rcx
0x1800066d5  jz      short loc_18000671D
0x1800066d7  call    ?Dereference@META_SCRIPT_MAP_TABLE@@QEAAXXZ; META_SCRIPT_MAP_TABLE::Dereference(void)
0x1800066dc  mov     cs:?sm_pGlobalTable@META_SCRIPT_MAP_TABLE@@0PEAV1@EA, rbx; META_SCRIPT_MAP_TABLE * META_SCRIPT_MAP_TABLE::sm_pGlobalTable
0x1800066e3  jmp     short loc_18000671D
0x1800066e5  cmp     cs:?sm_pGlobalTable@META_SCRIPT_MAP_TABLE@@0PEAV1@EA, 0; META_SCRIPT_MAP_TABLE * META_SCRIPT_MAP_TABLE::sm_pGlobalTable
0x1800066ed  mov     rax, [rbx]
0x1800066f0  jz      short loc_180006710
0x1800066f2  mov     rcx, rax; this
0x1800066f5  call    ?Dereference@META_SCRIPT_MAP_TABLE@@QEAAXXZ; META_SCRIPT_MAP_TABLE::Dereference(void)
0x1800066fa  mov     rax, cs:?sm_pGlobalTable@META_SCRIPT_MAP_TABLE@@0PEAV1@EA; META_SCRIPT_MAP_TABLE * META_SCRIPT_MAP_TABLE::sm_pGlobalTable
0x180006701  lock inc dword ptr [rax]
0x180006704  mov     rax, cs:?sm_pGlobalTable@META_SCRIPT_MAP_TABLE@@0PEAV1@EA; META_SCRIPT_MAP_TABLE * META_SCRIPT_MAP_TABLE::sm_pGlobalTable
0x18000670b  mov     [rbx], rax
0x18000670e  jmp     short loc_18000671D
0x180006710  lock inc dword ptr [rax]
0x180006713  mov     rax, [rbx]
0x180006716  mov     cs:?sm_pGlobalTable@META_SCRIPT_MAP_TABLE@@0PEAV1@EA, rax; META_SCRIPT_MAP_TABLE * META_SCRIPT_MAP_TABLE::sm_pGlobalTable
0x18000671d  lea     rcx, ?sm_GlobalLock@META_SCRIPT_MAP_TABLE@@0U_RTL_SRWLOCK@@A; _RTL_SRWLOCK META_SCRIPT_MAP_TABLE::sm_GlobalLock
0x180006724  add     rsp, 20h
0x180006728  pop     rbx
0x180006729  jmp     cs:__imp_ReleaseSRWLockExclusive
```
