# CiDeleteCatalogEntry

- ea: `0x180044058`
- end: `0x1800440ce`
- name: `CiDeleteCatalogEntry`
- size: `118`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180011540`

## callees

- `0x180011070`
- `0x18004436c`
- `0x180044444`

## import_xrefs

- `securekernel!SkeEnterCriticalRegion` at `0x180044072`
- `securekernel!SkeEnterCriticalRegion` at `0x180044072`
- `securekernel!SkReleasePushLockExclusive` at `0x18004409d`
- `securekernel!SkReleasePushLockExclusive` at `0x18004409d`
- `securekernel!SkAcquirePushLockExclusive` at `0x180044082`
- `securekernel!SkAcquirePushLockExclusive` at `0x180044082`
- `securekernel!SkeLeaveCriticalRegion` at `0x1800440a9`
- `securekernel!SkeLeaveCriticalRegion` at `0x1800440a9`

## pseudocode

```c
__int64 __fastcall CiDeleteCatalogEntry(__int64 a1)
{
  __int64 CurrentSiloState; // rbx

  CurrentSiloState = CiGetCurrentSiloState();
  SkeEnterCriticalRegion();
  SkAcquirePushLockExclusive(CurrentSiloState + 24);
  CipRemoveCatalogFromTable(a1, CurrentSiloState);
  SkReleasePushLockExclusive(CurrentSiloState + 24);
  SkeLeaveCriticalRegion();
  return CipFreeCatalog(a1);
}

```

## disassembly

```asm
0x180044058  mov     [rsp+arg_0], rbx
0x18004405d  mov     [rsp+arg_8], rsi
0x180044062  push    rdi
0x180044063  sub     rsp, 20h
0x180044067  mov     rsi, rcx
0x18004406a  call    CiGetCurrentSiloState
0x18004406f  mov     rbx, rax
0x180044072  call    cs:__imp_SkeEnterCriticalRegion
0x180044079  nop     dword ptr [rax+rax+00h]
0x18004407e  lea     rcx, [rbx+18h]
0x180044082  call    cs:__imp_SkAcquirePushLockExclusive
0x180044089  nop     dword ptr [rax+rax+00h]
0x18004408e  mov     rdx, rbx
0x180044091  mov     rcx, rsi
0x180044094  call    CipRemoveCatalogFromTable
0x180044099  lea     rcx, [rbx+18h]
0x18004409d  call    cs:__imp_SkReleasePushLockExclusive
0x1800440a4  nop     dword ptr [rax+rax+00h]
0x1800440a9  call    cs:__imp_SkeLeaveCriticalRegion
0x1800440b0  nop     dword ptr [rax+rax+00h]
0x1800440b5  mov     rcx, rsi
0x1800440b8  call    CipFreeCatalog
0x1800440bd  mov     rbx, [rsp+28h+arg_0]
0x1800440c2  mov     rsi, [rsp+28h+arg_8]
0x1800440c7  add     rsp, 20h
0x1800440cb  pop     rdi
0x1800440cc  retn
```
