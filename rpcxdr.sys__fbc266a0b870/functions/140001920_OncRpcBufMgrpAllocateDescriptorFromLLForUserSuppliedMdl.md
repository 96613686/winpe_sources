# OncRpcBufMgrpAllocateDescriptorFromLLForUserSuppliedMdl

- ea: `0x140001920`
- end: `0x140001a26`
- name: `OncRpcBufMgrpAllocateDescriptorFromLLForUserSuppliedMdl`
- size: `262`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14000119c`

## callees

- `0x140001920`
- `0x140002060`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140001961`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140001961`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140001986`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140001986`

## pseudocode

```c
__int64 __fastcall OncRpcBufMgrpAllocateDescriptorFromLLForUserSuppliedMdl(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  char *v9; // rdi
  __int64 v11; // rsi
  PVOID v12; // rcx
  __int64 v13; // rcx
  _QWORD *v14; // rdx

  if ( (*(_BYTE *)(a2 + 10) & 5) != 0 )
    v9 = *(char **)(a2 + 24);
  else
    v9 = (char *)MmMapLockedPagesSpecifyCache((PMDL)a2, 0, MmCached, 0, 0, 0x40000010u);
  if ( !v9 )
    return 0;
  v11 = *(unsigned int *)(a2 + 40);
  v12 = ExAllocateFromNPagedLookasideList(&stru_14001A600);
  if ( !v12 )
  {
    ++qword_14001A6A8;
    return 0;
  }
  ++qword_14001A6A0;
  ++dword_14001A6F0;
  ++dword_14001A6FC;
  OncRpcBufpDescriptorInit(v12, a1, a3);
  *(_DWORD *)(v13 + 80) |= 0x22u;
  *(_QWORD *)(v13 + 48) = a5;
  *(_QWORD *)(v13 + 64) = &v9[v11];
  *(_QWORD *)(v13 + 40) = a4;
  *(_QWORD *)(v13 + 88) = a2;
  *(_QWORD *)(v13 + 56) = v9;
  *(_DWORD *)(v13 + 72) = v11;
  *(_DWORD *)(v13 + 76) = v11;
  if ( a4 )
  {
    *(_QWORD *)(v13 + 96) = a2;
    v14 = *(_QWORD **)a2;
    if ( *(_QWORD *)a2 )
    {
      do
      {
        *(_QWORD *)(v13 + 96) = v14;
        v14 = (_QWORD *)*v14;
      }
      while ( v14 );
    }
  }
  else
  {
    *(_QWORD *)(v13 + 96) = 0;
  }
  return v13;
}

```

## disassembly

```asm
0x140001920  push    rbx
0x140001922  push    rbp
0x140001923  push    rsi
0x140001924  push    rdi
0x140001925  push    r14
0x140001927  push    r15
0x140001929  sub     rsp, 38h
0x14000192d  test    byte ptr [rdx+0Ah], 5
0x140001931  mov     rbp, r9
0x140001934  mov     r14, r8
0x140001937  mov     rbx, rdx
0x14000193a  mov     r15, rcx
0x14000193d  jz      short loc_140001945
0x14000193f  mov     rdi, [rdx+18h]
0x140001943  jmp     short loc_140001970
0x140001945  xor     r9d, r9d; RequestedAddress
0x140001948  mov     [rsp+68h+Priority], 40000010h; Priority
0x140001950  xor     edx, edx; AccessMode
0x140001952  mov     [rsp+68h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14000195a  mov     rcx, rbx; MemoryDescriptorList
0x14000195d  lea     r8d, [r9+1]; CacheType
0x140001961  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140001968  nop     dword ptr [rax+rax+00h]
0x14000196d  mov     rdi, rax
0x140001970  test    rdi, rdi
0x140001973  jnz     short loc_14000197C
0x140001975  xor     eax, eax
0x140001977  jmp     loc_140001A18
0x14000197c  mov     esi, [rbx+28h]
0x14000197f  lea     rcx, stru_14001A600; Lookaside
0x140001986  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14000198d  nop     dword ptr [rax+rax+00h]
0x140001992  mov     rcx, rax
0x140001995  test    rax, rax
0x140001998  jnz     short loc_1400019A3
0x14000199a  inc     cs:qword_14001A6A8
0x1400019a1  jmp     short loc_140001975
0x1400019a3  inc     cs:qword_14001A6A0
0x1400019aa  mov     r8, r14
0x1400019ad  inc     cs:dword_14001A6F0
0x1400019b3  mov     rdx, r15
0x1400019b6  inc     cs:dword_14001A6FC
0x1400019bc  call    OncRpcBufpDescriptorInit
0x1400019c1  mov     rax, [rsp+68h+arg_20]
0x1400019c9  or      dword ptr [rcx+50h], 22h
0x1400019cd  mov     [rcx+30h], rax
0x1400019d1  lea     rax, [rdi+rsi]
0x1400019d5  mov     [rcx+40h], rax
0x1400019d9  mov     [rcx+28h], rbp
0x1400019dd  mov     [rcx+58h], rbx
0x1400019e1  mov     [rcx+38h], rdi
0x1400019e5  mov     [rcx+48h], esi
0x1400019e8  mov     [rcx+4Ch], esi
0x1400019eb  test    rbp, rbp
0x1400019ee  jz      short loc_140001A0D
0x1400019f0  mov     [rcx+60h], rbx
0x1400019f4  mov     rdx, [rbx]
0x1400019f7  test    rdx, rdx
0x1400019fa  jz      short loc_140001A15
0x1400019fc  mov     [rcx+60h], rdx
0x140001a00  mov     rax, [rdx]
0x140001a03  mov     rdx, rax
0x140001a06  test    rax, rax
0x140001a09  jnz     short loc_1400019FC
0x140001a0b  jmp     short loc_140001A15
0x140001a0d  mov     qword ptr [rcx+60h], 0
0x140001a15  mov     rax, rcx
0x140001a18  add     rsp, 38h
0x140001a1c  pop     r15
0x140001a1e  pop     r14
0x140001a20  pop     rdi
0x140001a21  pop     rsi
0x140001a22  pop     rbp
0x140001a23  pop     rbx
0x140001a24  retn
```
