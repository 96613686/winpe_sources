# VsmmDaxFileFlushMdl

- ea: `0x1400b98f8`
- end: `0x1400b9998`
- name: `VsmmDaxFileFlushMdl`
- size: `160`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140026e00`
- `0x1400b99a0`

## callees

- `0x140038630`
- `0x1400b98f8`
- `0x1400b9fc8`

## import_xrefs

- `ntoskrnl!MmUnmapLockedPages` at `0x1400b9980`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400b9980`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400b9932`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400b9932`

## pseudocode

```c
__int64 __fastcall VsmmDaxFileFlushMdl(__int64 a1, __int64 a2, unsigned int a3)
{
  PVOID v6; // rsi
  unsigned int v7; // ebx

  if ( (*(_BYTE *)(a2 + 10) & 5) != 0 )
    v6 = *(PVOID *)(a2 + 24);
  else
    v6 = MmMapLockedPagesSpecifyCache((PMDL)a2, 0, MmCached, 0, 0, 0x40000010u);
  if ( v6 )
  {
    v7 = VsmmDaxFileFlushVaRange(a1, v6, *(unsigned int *)(a2 + 40), a3);
    MmUnmapLockedPages(v6, (PMDL)a2);
  }
  else
  {
    v7 = -1073741801;
    VidTraceErrorInternal0("VsmmDaxFileFlushMdl", "onecore\\vm\\vid\\sys\\vsmm\\vsmmdaxfile.c", 3464);
  }
  return v7;
}

```

## disassembly

```asm
0x1400b98f8  push    rbx
0x1400b98fa  push    rbp
0x1400b98fb  push    rsi
0x1400b98fc  push    rdi
0x1400b98fd  sub     rsp, 38h
0x1400b9901  test    byte ptr [rdx+0Ah], 5
0x1400b9905  mov     ebx, r8d
0x1400b9908  mov     rdi, rdx
0x1400b990b  mov     rbp, rcx
0x1400b990e  jz      short loc_1400B9916
0x1400b9910  mov     rsi, [rdx+18h]
0x1400b9914  jmp     short loc_1400B9941
0x1400b9916  xor     r9d, r9d; RequestedAddress
0x1400b9919  mov     [rsp+58h+Priority], 40000010h; Priority
0x1400b9921  xor     edx, edx; AccessMode
0x1400b9923  mov     [rsp+58h+BugCheckOnFailure], 0; BugCheckOnFailure
0x1400b992b  mov     rcx, rdi; MemoryDescriptorList
0x1400b992e  lea     r8d, [r9+1]; CacheType
0x1400b9932  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400b9939  nop     dword ptr [rax+rax+00h]
0x1400b993e  mov     rsi, rax
0x1400b9941  test    rsi, rsi
0x1400b9944  jnz     short loc_1400B9966
0x1400b9946  mov     ebx, 0C0000017h
0x1400b994b  mov     r8d, 0D88h
0x1400b9951  lea     rdx, aOnecoreVmVidSy_71; "onecore\\vm\\vid\\sys\\vsmm\\vsmmdaxfil"...
0x1400b9958  lea     rcx, aVsmmdaxfileflu_0; "VsmmDaxFileFlushMdl"
0x1400b995f  call    VidTraceErrorInternal0
0x1400b9964  jmp     short loc_1400B998C
0x1400b9966  mov     r8d, [rdi+28h]
0x1400b996a  mov     r9d, ebx
0x1400b996d  mov     rdx, rsi
0x1400b9970  mov     rcx, rbp
0x1400b9973  call    VsmmDaxFileFlushVaRange
0x1400b9978  mov     ebx, eax
0x1400b997a  mov     rdx, rdi; MemoryDescriptorList
0x1400b997d  mov     rcx, rsi; BaseAddress
0x1400b9980  call    cs:__imp_MmUnmapLockedPages
0x1400b9987  nop     dword ptr [rax+rax+00h]
0x1400b998c  mov     eax, ebx
0x1400b998e  add     rsp, 38h
0x1400b9992  pop     rdi
0x1400b9993  pop     rsi
0x1400b9994  pop     rbp
0x1400b9995  pop     rbx
0x1400b9996  retn
```
