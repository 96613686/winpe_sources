# WinSAT::StorageDevice::OverlappedIOManager::~OverlappedIOManager(void)

- ea: `0x140060580`
- end: `0x1400605c5`
- name: `??1OverlappedIOManager@StorageDevice@WinSAT@@QEAA@XZ`
- size: `69`
- prototype: `void __fastcall(void **this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400605cc`
- `0x1401166b5`

## callees

- `0x140060580`

## import_xrefs

- `KERNEL32!InterlockedPopEntrySList` at `0x14006059f`
- `KERNEL32!InterlockedPopEntrySList` at `0x14006059f`
- `msvcrt!_aligned_free` at `0x140060596`
- `msvcrt!_aligned_free` at `0x1400605b2`
- `msvcrt!_aligned_free` at `0x140060596`
- `msvcrt!_aligned_free` at `0x1400605b2`

## pseudocode

```c
void __fastcall WinSAT::StorageDevice::OverlappedIOManager::~OverlappedIOManager(void **this)
{
  union _SLIST_HEADER *v2; // rcx
  PSLIST_ENTRY v3; // rax

  v2 = (union _SLIST_HEADER *)*this;
  if ( v2 )
  {
    while ( 1 )
    {
      v3 = InterlockedPopEntrySList(v2);
      if ( !v3 )
        break;
      _aligned_free(v3);
      v2 = (union _SLIST_HEADER *)*this;
    }
  }
  if ( *this )
  {
    _aligned_free(*this);
    *this = 0;
  }
}

```

## disassembly

```asm
0x140060580  push    rbx
0x140060582  sub     rsp, 20h
0x140060586  mov     rbx, rcx
0x140060589  mov     rcx, [rcx]
0x14006058c  test    rcx, rcx
0x14006058f  jz      short loc_1400605AA
0x140060591  jmp     short loc_14006059F
0x140060593  mov     rcx, rax; Block
0x140060596  call    cs:__imp__aligned_free
0x14006059c  mov     rcx, [rbx]; ListHead
0x14006059f  call    cs:__imp_InterlockedPopEntrySList
0x1400605a5  test    rax, rax
0x1400605a8  jnz     short loc_140060593
0x1400605aa  mov     rcx, [rbx]; Block
0x1400605ad  test    rcx, rcx
0x1400605b0  jz      short loc_1400605BF
0x1400605b2  call    cs:__imp__aligned_free
0x1400605b8  mov     qword ptr [rbx], 0
0x1400605bf  add     rsp, 20h
0x1400605c3  pop     rbx
0x1400605c4  retn
```
