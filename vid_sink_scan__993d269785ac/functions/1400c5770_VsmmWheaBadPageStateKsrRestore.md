# VsmmWheaBadPageStateKsrRestore

- ea: `0x1400c5770`
- end: `0x1400c599f`
- name: `VsmmWheaBadPageStateKsrRestore`
- size: `559`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400cf86c`

## callees

- `0x140021d40`
- `0x14002f524`
- `0x140077fc4`
- `0x1400c5770`

## import_xrefs

- `ntoskrnl!MmUnmapLockedPages` at `0x1400c596a`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400c596a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400c58ff`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400c58ff`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c597b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c597b`
- `ntoskrnl!ExAllocatePool2` at `0x1400c5844`
- `ntoskrnl!ExAllocatePool2` at `0x1400c5844`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrClaimPersistedMemory` at `0x1400c57b3`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrClaimPersistedMemory` at `0x1400c57b3`

## pseudocode

```c
__int64 __fastcall VsmmWheaBadPageStateKsrRestore(__int64 a1, __int64 a2, __int64 a3)
{
  int v4; // ebx
  unsigned int v5; // r10d
  __int64 v6; // rbx
  __int64 i; // rcx
  unsigned __int64 v8; // r9
  unsigned int v9; // edx
  unsigned __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // rax
  __int64 Pool2; // rax
  struct _MDL *v14; // rdi
  PVOID v15; // rax
  void *v16; // rsi
  _QWORD v18[2]; // [rsp+30h] [rbp-48h] BYREF
  _QWORD Src[7]; // [rsp+40h] [rbp-38h] BYREF
  unsigned int v20; // [rsp+80h] [rbp+8h] BYREF
  int v21; // [rsp+84h] [rbp+Ch]

  v21 = HIDWORD(a1);
  v20 = 0;
  v4 = KsrClaimPersistedMemory(VSMM_KSR_GLOBAL_STATE_GUID, a3, v18, 2, 0, &v20);
  if ( v4 >= 0 )
  {
    v5 = v20;
    v6 = 0;
    for ( i = 0; (unsigned int)i < v5; i = (unsigned int)(i + 1) )
    {
      v8 = v18[i];
      v9 = 0;
      v10 = v8 >> 40;
      if ( v8 >> 40 )
      {
        v11 = v8 & 0xFFFFFFFFFFLL;
        do
        {
          v12 = v9++;
          Src[v6++] = v11 + v12;
        }
        while ( v9 < (unsigned int)v10 );
      }
    }
    Pool2 = ExAllocatePool2(64, (unsigned int)(8 * v6 + 48), 1833788502);
    v14 = (struct _MDL *)Pool2;
    if ( Pool2 )
    {
      *(_QWORD *)(Pool2 + 12) = 0;
      *(_QWORD *)(Pool2 + 20) = 0;
      *(_DWORD *)(Pool2 + 28) = 0;
      *(_QWORD *)Pool2 = 0;
      *(_DWORD *)(Pool2 + 40) = (_DWORD)v6 << 12;
      *(_QWORD *)(Pool2 + 32) = 0;
      *(_WORD *)(Pool2 + 8) = 8 * (v6 + 6);
      *(_DWORD *)(Pool2 + 44) = 0;
      *(_WORD *)(Pool2 + 10) = 2;
      memmove((void *)(Pool2 + 48), Src, 8 * v6);
      v15 = MmMapLockedPagesSpecifyCache(v14, 0, MmCached, 0, 0, 0x40000010u);
      v16 = v15;
      if ( v15 )
      {
        v4 = VsmmWheapBadPageTableBuildFromBitmap(a2, v15);
        if ( v4 >= 0 )
        {
          v4 = 0;
          *(_QWORD *)(a2 + 32) = v16;
          *(_QWORD *)(a2 + 40) = v14;
          return (unsigned int)v4;
        }
        VidTraceErrorStatusInternal0("VsmmWheaBadPageStateKsrRestore", "onecore\\vm\\vid\\sys\\vsmm\\vsmmwhea.c", 8328);
        MmUnmapLockedPages(v16, v14);
      }
      else
      {
        v4 = -1073741670;
        VidTraceErrorStatusInternal0("VsmmWheaBadPageStateKsrRestore", "onecore\\vm\\vid\\sys\\vsmm\\vsmmwhea.c", 8321);
      }
      ExFreePoolWithTag(v14, 0);
    }
    else
    {
      v4 = -1073741670;
      VidTraceErrorStatusInternal0("VsmmWheaBadPageStateKsrRestore", "onecore\\vm\\vid\\sys\\vsmm\\vsmmwhea.c", 8304);
    }
  }
  else
  {
    VidTraceErrorStatusInternal0("VsmmWheaBadPageStateKsrRestore", "onecore\\vm\\vid\\sys\\vsmm\\vsmmwhea.c", 8278);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1400c5770  mov     r11, rsp
0x1400c5773  mov     [r11+8], rcx
0x1400c5777  push    rbx
0x1400c5778  push    rbp
0x1400c5779  push    rsi
0x1400c577a  push    rdi
0x1400c577b  sub     rsp, 58h
0x1400c577f  lea     rcx, [r11+8]
0x1400c5783  mov     dword ptr [r11+8], 0
0x1400c578b  mov     rax, r8
0x1400c578e  mov     [r11-50h], rcx
0x1400c5792  mov     rbp, rdx
0x1400c5795  mov     [rsp+78h+BugCheckOnFailure], 0
0x1400c579d  mov     esi, 2
0x1400c57a2  lea     rcx, VSMM_KSR_GLOBAL_STATE_GUID
0x1400c57a9  mov     r9d, esi
0x1400c57ac  lea     r8, [r11-48h]
0x1400c57b0  mov     rdx, rax
0x1400c57b3  call    cs:__imp_KsrClaimPersistedMemory
0x1400c57ba  nop     dword ptr [rax+rax+00h]
0x1400c57bf  mov     ebx, eax
0x1400c57c1  test    eax, eax
0x1400c57c3  jns     short loc_1400C57E6
0x1400c57c5  mov     r9d, eax
0x1400c57c8  lea     rdx, aOnecoreVmVidSy_51; "onecore\\vm\\vid\\sys\\vsmm\\vsmmwhea.c"
0x1400c57cf  mov     r8d, 2056h
0x1400c57d5  lea     rcx, aVsmmwheabadpag_0; "VsmmWheaBadPageStateKsrRestore"
0x1400c57dc  call    VidTraceErrorStatusInternal0
0x1400c57e1  jmp     loc_1400C5993
0x1400c57e6  mov     r10d, [rsp+78h+arg_0]
0x1400c57ee  xor     ebx, ebx
0x1400c57f0  xor     ecx, ecx
0x1400c57f2  test    r10d, r10d
0x1400c57f5  jz      short loc_1400C5832
0x1400c57f7  mov     r9, [rsp+rcx*8+78h+var_48]
0x1400c57fc  xor     edx, edx
0x1400c57fe  mov     r8, r9
0x1400c5801  shr     r8, 28h
0x1400c5805  test    r8d, r8d
0x1400c5808  jz      short loc_1400C582B
0x1400c580a  mov     rax, 0FFFFFFFFFFh
0x1400c5814  and     r9, rax
0x1400c5817  mov     eax, edx
0x1400c5819  inc     edx
0x1400c581b  add     rax, r9
0x1400c581e  mov     [rsp+rbx*8+78h+Src], rax
0x1400c5823  inc     rbx
0x1400c5826  cmp     edx, r8d
0x1400c5829  jb      short loc_1400C5817
0x1400c582b  inc     ecx
0x1400c582d  cmp     ecx, r10d
0x1400c5830  jb      short loc_1400C57F7
0x1400c5832  lea     edx, ds:30h[rbx*8]
0x1400c5839  mov     ecx, 40h ; '@'
0x1400c583e  mov     r8d, 6D4D6456h
0x1400c5844  call    cs:__imp_ExAllocatePool2
0x1400c584b  nop     dword ptr [rax+rax+00h]
0x1400c5850  mov     rdi, rax
0x1400c5853  test    rax, rax
0x1400c5856  jnz     short loc_1400C587F
0x1400c5858  mov     r9d, 0C000009Ah
0x1400c585e  mov     ebx, r9d
0x1400c5861  mov     r8d, 2070h
0x1400c5867  lea     rdx, aOnecoreVmVidSy_51; "onecore\\vm\\vid\\sys\\vsmm\\vsmmwhea.c"
0x1400c586e  lea     rcx, aVsmmwheabadpag_0; "VsmmWheaBadPageStateKsrRestore"
0x1400c5875  call    VidTraceErrorStatusInternal0
0x1400c587a  jmp     loc_1400C5993
0x1400c587f  mov     qword ptr [rax+0Ch], 0
0x1400c5887  lea     r8, ds:0[rbx*8]; Size
0x1400c588f  mov     qword ptr [rax+14h], 0
0x1400c5897  lea     rdx, [rsp+78h+Src]; Src
0x1400c589c  mov     dword ptr [rax+1Ch], 0
0x1400c58a3  mov     rcx, rbx
0x1400c58a6  mov     qword ptr [rax], 0
0x1400c58ad  shl     rcx, 0Ch
0x1400c58b1  mov     rax, rcx
0x1400c58b4  mov     [rdi+28h], ecx
0x1400c58b7  shr     rax, 0Ch
0x1400c58bb  lea     rcx, [rdi+30h]; void *
0x1400c58bf  add     ax, 6
0x1400c58c3  mov     qword ptr [rdi+20h], 0
0x1400c58cb  shl     ax, 3
0x1400c58cf  mov     [rdi+8], ax
0x1400c58d3  mov     dword ptr [rdi+2Ch], 0
0x1400c58da  mov     [rdi+0Ah], si
0x1400c58de  call    memmove
0x1400c58e3  xor     r9d, r9d; RequestedAddress
0x1400c58e6  mov     [rsp+78h+Priority], 40000010h; Priority
0x1400c58ee  xor     edx, edx; AccessMode
0x1400c58f0  mov     [rsp+78h+BugCheckOnFailure], 0; BugCheckOnFailure
0x1400c58f8  mov     rcx, rdi; MemoryDescriptorList
0x1400c58fb  lea     r8d, [r9+1]; CacheType
0x1400c58ff  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400c5906  nop     dword ptr [rax+rax+00h]
0x1400c590b  mov     rsi, rax
0x1400c590e  test    rax, rax
0x1400c5911  jnz     short loc_1400C5937
0x1400c5913  mov     r9d, 0C000009Ah
0x1400c5919  mov     ebx, r9d
0x1400c591c  mov     r8d, 2081h
0x1400c5922  lea     rdx, aOnecoreVmVidSy_51; "onecore\\vm\\vid\\sys\\vsmm\\vsmmwhea.c"
0x1400c5929  lea     rcx, aVsmmwheabadpag_0; "VsmmWheaBadPageStateKsrRestore"
0x1400c5930  call    VidTraceErrorStatusInternal0
0x1400c5935  jmp     short loc_1400C5976
0x1400c5937  mov     rdx, rsi
0x1400c593a  mov     rcx, rbp
0x1400c593d  call    VsmmWheapBadPageTableBuildFromBitmap
0x1400c5942  mov     ebx, eax
0x1400c5944  test    eax, eax
0x1400c5946  jns     short loc_1400C5989
0x1400c5948  mov     r9d, eax
0x1400c594b  lea     rdx, aOnecoreVmVidSy_51; "onecore\\vm\\vid\\sys\\vsmm\\vsmmwhea.c"
0x1400c5952  mov     r8d, 2088h
0x1400c5958  lea     rcx, aVsmmwheabadpag_0; "VsmmWheaBadPageStateKsrRestore"
0x1400c595f  call    VidTraceErrorStatusInternal0
0x1400c5964  mov     rdx, rdi; MemoryDescriptorList
0x1400c5967  mov     rcx, rsi; BaseAddress
0x1400c596a  call    cs:__imp_MmUnmapLockedPages
0x1400c5971  nop     dword ptr [rax+rax+00h]
0x1400c5976  xor     edx, edx; Tag
0x1400c5978  mov     rcx, rdi; P
0x1400c597b  call    cs:__imp_ExFreePoolWithTag
0x1400c5982  nop     dword ptr [rax+rax+00h]
0x1400c5987  jmp     short loc_1400C5993
0x1400c5989  xor     ebx, ebx
0x1400c598b  mov     [rbp+20h], rsi
0x1400c598f  mov     [rbp+28h], rdi
0x1400c5993  mov     eax, ebx
0x1400c5995  add     rsp, 58h
0x1400c5999  pop     rdi
0x1400c599a  pop     rsi
0x1400c599b  pop     rbp
0x1400c599c  pop     rbx
0x1400c599d  retn
```
