# UdfSeqCacheUnReserveFileRegion

- ea: `0x140056cb8`
- end: `0x140056e97`
- name: `UdfSeqCacheUnReserveFileRegion`
- size: `479`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1400010f0`
- `0x140007b90`
- `0x14000b2b0`
- `0x140051d74`

## callees

- `0x140056cb8`

## import_xrefs

- `ntoskrnl!FsRtlLookupLargeMcbEntry` at `0x140056d89`
- `ntoskrnl!FsRtlLookupLargeMcbEntry` at `0x140056e08`
- `ntoskrnl!FsRtlLookupLargeMcbEntry` at `0x140056d89`
- `ntoskrnl!FsRtlLookupLargeMcbEntry` at `0x140056e08`
- `ntoskrnl!ExRaiseStatus` at `0x140056d40`
- `ntoskrnl!ExRaiseStatus` at `0x140056d40`
- `ntoskrnl!ExReleaseResourceLite` at `0x140056e6c`
- `ntoskrnl!ExReleaseResourceLite` at `0x140056e6c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140056d28`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140056d28`
- `ntoskrnl!FsRtlRemoveLargeMcbEntry` at `0x140056dc8`
- `ntoskrnl!FsRtlRemoveLargeMcbEntry` at `0x140056dc8`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140056e39`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140056e39`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140056e59`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140056e59`

## pseudocode

```c
__int64 __fastcall UdfSeqCacheUnReserveFileRegion(__int64 a1, __int64 a2, unsigned int a3, unsigned int a4, char a5)
{
  LONGLONG v5; // r15
  __int64 v7; // rdi
  int v9; // eax
  __int64 v10; // rbp
  unsigned int v11; // esi
  LARGE_MCB *v12; // r13
  BOOLEAN v13; // r12
  unsigned int v14; // ebx
  __int64 SectorCountFromLbn; // [rsp+80h] [rbp+8h] BYREF
  __int64 Lbn; // [rsp+88h] [rbp+10h] BYREF

  v5 = a3;
  Lbn = 0;
  v7 = a2;
  SectorCountFromLbn = 0;
  if ( a2 == -1 )
    return 0;
  v9 = *(_DWORD *)(a2 + 212);
  if ( (v9 & 0x4000000) == 0 )
    return 0;
  v10 = *(_QWORD *)(a1 + 16);
  if ( (v9 & 0x8000000) != 0 )
    v7 = *(_QWORD *)(v10 + 320);
  if ( !ExAcquireResourceExclusiveLite(*(PERESOURCE *)(v7 + 336), (*(_DWORD *)(a1 + 28) & 4) != 0) )
  {
    *(_DWORD *)(a1 + 24) = -1073741608;
    ExRaiseStatus(-1073741608);
  }
  v11 = 0;
  if ( *(_DWORD *)(v7 + 328) )
  {
    v12 = (LARGE_MCB *)(v7 + 344);
    v13 = FsRtlLookupLargeMcbEntry((PLARGE_MCB)(v7 + 344), v5, &Lbn, &SectorCountFromLbn, 0, 0, 0);
    if ( v13 )
    {
      do
      {
        if ( !a4 )
          break;
        v14 = SectorCountFromLbn;
        if ( a4 < (unsigned int)SectorCountFromLbn )
          v14 = a4;
        if ( Lbn != -1 )
        {
          FsRtlRemoveLargeMcbEntry(v12, (unsigned int)v5, v14);
          v11 += v14;
        }
        a4 -= v14;
        LODWORD(v5) = v14 + v5;
        if ( a4 )
          v13 = FsRtlLookupLargeMcbEntry(v12, (unsigned int)v5, &Lbn, &SectorCountFromLbn, 0, 0, 0);
      }
      while ( v13 );
      if ( v11 )
      {
        *(_DWORD *)(v7 + 328) -= v11;
        if ( a5 )
        {
          ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v10 + 1584));
          *(_DWORD *)(v10 + 672) -= v11;
          *(_QWORD *)(v10 + 1640) = 0;
          ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v10 + 1584));
        }
      }
    }
  }
  ExReleaseResourceLite(*(PERESOURCE *)(v7 + 336));
  return v11;
}

```

## disassembly

```asm
0x140056cb8  mov     rax, rsp
0x140056cbb  mov     [rax+18h], rbx
0x140056cbf  push    rbp
0x140056cc0  push    rsi
0x140056cc1  push    rdi
0x140056cc2  push    r12
0x140056cc4  push    r13
0x140056cc6  push    r14
0x140056cc8  push    r15
0x140056cca  sub     rsp, 40h
0x140056cce  mov     r15d, r8d
0x140056cd1  mov     r14d, r9d
0x140056cd4  mov     qword ptr [rax+10h], 0
0x140056cdc  mov     rdi, rdx
0x140056cdf  mov     qword ptr [rax+8], 0
0x140056ce7  mov     rbx, rcx
0x140056cea  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x140056cee  jz      loc_140056E7C
0x140056cf4  mov     eax, [rdx+0D4h]
0x140056cfa  bt      eax, 1Ah
0x140056cfe  jnb     loc_140056E7C
0x140056d04  mov     rbp, [rcx+10h]
0x140056d08  bt      eax, 1Bh
0x140056d0c  jnb     short loc_140056D15
0x140056d0e  mov     rdi, [rbp+140h]
0x140056d15  mov     edx, [rcx+1Ch]
0x140056d18  mov     r13, rdi
0x140056d1b  mov     rcx, [rdi+150h]; Resource
0x140056d22  shr     edx, 2
0x140056d25  and     dl, 1; Wait
0x140056d28  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140056d2f  nop     dword ptr [rax+rax+00h]
0x140056d34  test    al, al
0x140056d36  jnz     short loc_140056D4D
0x140056d38  mov     ecx, 0C00000D8h; Status
0x140056d3d  mov     [rbx+18h], ecx
0x140056d40  call    cs:__imp_ExRaiseStatus
0x140056d4d  xor     ebx, ebx
0x140056d4f  mov     esi, ebx
0x140056d51  cmp     [rdi+148h], ebx
0x140056d57  jbe     loc_140056E65
0x140056d5d  mov     [rsp+78h+Index], rbx; Index
0x140056d62  lea     r9, [rsp+78h+SectorCountFromLbn]; SectorCountFromLbn
0x140056d6a  add     r13, 158h
0x140056d71  mov     [rsp+78h+SectorCountFromStartingLbn], rbx; SectorCountFromStartingLbn
0x140056d76  mov     rcx, r13; Mcb
0x140056d79  mov     [rsp+78h+StartingLbn], rbx; StartingLbn
0x140056d7e  mov     rdx, r15; Vbn
0x140056d81  lea     r8, [rsp+78h+Lbn]; Lbn
0x140056d89  call    cs:__imp_FsRtlLookupLargeMcbEntry
0x140056d90  nop     dword ptr [rax+rax+00h]
0x140056d95  mov     r12b, al
0x140056d98  test    al, al
0x140056d9a  jz      loc_140056E65
0x140056da0  test    r14d, r14d
0x140056da3  jz      short loc_140056E1C
0x140056da5  mov     rbx, [rsp+78h+SectorCountFromLbn]
0x140056dad  cmp     r14d, ebx
0x140056db0  cmovb   ebx, r14d
0x140056db4  cmp     [rsp+78h+Lbn], 0FFFFFFFFFFFFFFFFh
0x140056dbd  jz      short loc_140056DD6
0x140056dbf  mov     r8d, ebx; SectorCount
0x140056dc2  mov     rcx, r13; Mcb
0x140056dc5  mov     edx, r15d; Vbn
0x140056dc8  call    cs:__imp_FsRtlRemoveLargeMcbEntry
0x140056dcf  nop     dword ptr [rax+rax+00h]
0x140056dd4  add     esi, ebx
0x140056dd6  sub     r14d, ebx
0x140056dd9  add     r15d, ebx
0x140056ddc  xor     ebx, ebx
0x140056dde  test    r14d, r14d
0x140056de1  jz      short loc_140056E17
0x140056de3  mov     [rsp+78h+Index], rbx; Index
0x140056de8  lea     r9, [rsp+78h+SectorCountFromLbn]; SectorCountFromLbn
0x140056df0  mov     [rsp+78h+SectorCountFromStartingLbn], rbx; SectorCountFromStartingLbn
0x140056df5  lea     r8, [rsp+78h+Lbn]; Lbn
0x140056dfd  mov     edx, r15d; Vbn
0x140056e00  mov     rcx, r13; Mcb
0x140056e03  mov     [rsp+78h+StartingLbn], rbx; StartingLbn
0x140056e08  call    cs:__imp_FsRtlLookupLargeMcbEntry
0x140056e0f  nop     dword ptr [rax+rax+00h]
0x140056e14  mov     r12b, al
0x140056e17  test    r12b, r12b
0x140056e1a  jnz     short loc_140056DA0
0x140056e1c  test    esi, esi
0x140056e1e  jz      short loc_140056E65
0x140056e20  sub     [rdi+148h], esi
0x140056e26  cmp     [rsp+78h+arg_20], bl
0x140056e2d  jz      short loc_140056E65
0x140056e2f  lea     rbx, [rbp+630h]
0x140056e36  mov     rcx, rbx; FastMutex
0x140056e39  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140056e40  nop     dword ptr [rax+rax+00h]
0x140056e45  sub     [rbp+2A0h], esi
0x140056e4b  mov     rcx, rbx; FastMutex
0x140056e4e  mov     qword ptr [rbp+668h], 0
0x140056e59  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140056e60  nop     dword ptr [rax+rax+00h]
0x140056e65  mov     rcx, [rdi+150h]; Resource
0x140056e6c  call    cs:__imp_ExReleaseResourceLite
0x140056e73  nop     dword ptr [rax+rax+00h]
0x140056e78  mov     eax, esi
0x140056e7a  jmp     short loc_140056E7E
0x140056e7c  xor     eax, eax
0x140056e7e  mov     rbx, [rsp+78h+arg_10]
0x140056e86  add     rsp, 40h
0x140056e8a  pop     r15
0x140056e8c  pop     r14
0x140056e8e  pop     r13
0x140056e90  pop     r12
0x140056e92  pop     rdi
0x140056e93  pop     rsi
0x140056e94  pop     rbp
0x140056e95  retn
```
