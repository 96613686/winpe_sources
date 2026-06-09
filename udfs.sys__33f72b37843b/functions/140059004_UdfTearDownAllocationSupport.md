# UdfTearDownAllocationSupport

- ea: `0x140059004`
- end: `0x140059089`
- name: `UdfTearDownAllocationSupport`
- size: `133`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140003148`
- `0x14002c008`
- `0x140052864`

## callees

- `0x14000e5d8`
- `0x14004ce50`
- `0x140059004`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x140059059`
- `ntoskrnl!ExReleaseResourceLite` at `0x140059059`
- `ntoskrnl!ExDeleteResourceLite` at `0x140059068`
- `ntoskrnl!ExDeleteResourceLite` at `0x140059068`

## pseudocode

```c
NTSTATUS __fastcall UdfTearDownAllocationSupport(__int64 a1, __int64 a2)
{
  NTSTATUS result; // eax
  unsigned int i; // esi
  struct _ERESOURCE *v6; // rbx
  __int64 v7; // rcx
  __int64 v8; // rcx

  result = *(_DWORD *)(a2 + 48);
  if ( (result & 0x40) != 0 )
  {
    for ( i = 0; (int)i < 2; ++i )
    {
      v6 = (struct _ERESOURCE *)(a2 + 200LL * i + 552);
      UdfAcquireResource(a1, v6, 0, 0);
      UdfUnpinCurrentBitmapPage(v7, a2, i);
      UdfUnpinCurrentBitmapPage(v8, a2, i);
      ExReleaseResourceLite(v6);
      result = ExDeleteResourceLite(v6);
    }
    *(_DWORD *)(a2 + 48) &= ~0x40u;
  }
  return result;
}

```

## disassembly

```asm
0x140059004  push    rbx
0x140059006  push    rbp
0x140059007  push    rsi
0x140059008  push    rdi
0x140059009  sub     rsp, 28h
0x14005900d  mov     eax, [rdx+30h]
0x140059010  mov     rdi, rdx
0x140059013  mov     rbp, rcx
0x140059016  test    al, 40h
0x140059018  jz      short loc_14005907F
0x14005901a  xor     esi, esi
0x14005901c  mov     eax, esi
0x14005901e  xor     r9d, r9d
0x140059021  imul    rbx, rax, 0C8h
0x140059028  xor     r8d, r8d
0x14005902b  mov     rcx, rbp
0x14005902e  add     rbx, 228h
0x140059035  add     rbx, rdi
0x140059038  mov     rdx, rbx
0x14005903b  call    UdfAcquireResource
0x140059040  mov     r8d, esi
0x140059043  mov     rdx, rdi
0x140059046  call    UdfUnpinCurrentBitmapPage
0x14005904b  mov     r8d, esi
0x14005904e  mov     rdx, rdi
0x140059051  call    UdfUnpinCurrentBitmapPage
0x140059056  mov     rcx, rbx; Resource
0x140059059  call    cs:__imp_ExReleaseResourceLite
0x140059060  nop     dword ptr [rax+rax+00h]
0x140059065  mov     rcx, rbx; Resource
0x140059068  call    cs:__imp_ExDeleteResourceLite
0x14005906f  nop     dword ptr [rax+rax+00h]
0x140059074  inc     esi
0x140059076  cmp     esi, 2
0x140059079  jl      short loc_14005901C
0x14005907b  and     dword ptr [rdi+30h], 0FFFFFFBFh
0x14005907f  add     rsp, 28h
0x140059083  pop     rdi
0x140059084  pop     rsi
0x140059085  pop     rbp
0x140059086  pop     rbx
0x140059087  retn
```
