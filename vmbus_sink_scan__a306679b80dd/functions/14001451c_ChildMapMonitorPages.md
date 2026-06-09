# ChildMapMonitorPages

- ea: `0x14001451c`
- end: `0x140014672`
- name: `ChildMapMonitorPages`
- size: `342`
- prototype: `__int64 __fastcall(__int64, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140014860`

## callees

- `0x14000389c`
- `0x1400144a8`
- `0x14001451c`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400145f4`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400145f4`

## pseudocode

```c
__int64 __fastcall ChildMapMonitorPages(__int64 a1, unsigned __int64 *a2)
{
  unsigned __int64 v4; // rdx
  unsigned __int64 v5; // rax
  unsigned __int64 v6; // rax
  char *v7; // rax
  bool v9; // zf

  ChildFreeMonitorPages();
  if ( dword_140020870 == 2 && (a2[1] < qword_140020868 || *a2 && *a2 < qword_140020868) )
    __fastfail(0x3Au);
  v4 = *a2;
  v5 = *a2;
  *(_QWORD *)(a1 + 912) = 0;
  *(_WORD *)(a1 + 922) = 0;
  *(_QWORD *)(a1 + 944) = 0;
  *(_DWORD *)(a1 + 956) = 0;
  *(_WORD *)(a1 + 920) = v5 != 0 ? 64 : 56;
  v6 = a2[1] >> 12;
  *(_DWORD *)(a1 + 952) = v4 != 0 ? 0x2000 : 4096;
  *(_QWORD *)(a1 + 960) = v6;
  if ( v4 )
    *(_QWORD *)(a1 + 968) = v4 >> 12;
  *(_WORD *)(a1 + 922) |= 0x2002u;
  if ( (*(_WORD *)(a1 + 922) & 5) != 0 )
    v7 = *(char **)(a1 + 936);
  else
    v7 = (char *)MmMapLockedPagesSpecifyCache((PMDL)(a1 + 912), 0, MmCached, 0, 0, 0x40000010u);
  if ( v7 )
  {
    v9 = *a2 == 0;
    *(_QWORD *)(a1 + 872) = v7;
    *(_QWORD *)(a1 + 880) = v7;
    if ( !v9 )
      *(_QWORD *)(a1 + 888) = v7 + 4096;
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_97df64ee0825388b346f901fe4767427_Traceguids);
    }
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x14001451c  mov     [rsp+arg_0], rbx
0x140014521  push    rdi
0x140014522  sub     rsp, 30h
0x140014526  mov     rdi, rdx
0x140014529  mov     rbx, rcx
0x14001452c  call    ChildFreeMonitorPages
0x140014531  cmp     cs:dword_140020870, 2
0x140014538  jnz     short loc_14001455B
0x14001453a  mov     rax, cs:qword_140020868
0x140014541  cmp     [rdi+8], rax
0x140014545  jb      short loc_140014554
0x140014547  mov     rcx, [rdi]
0x14001454a  test    rcx, rcx
0x14001454d  jz      short loc_14001455B
0x14001454f  cmp     rcx, rax
0x140014552  jnb     short loc_14001455B
0x140014554  mov     ecx, 3Ah ; ':'
0x140014559  int     29h; Win8: RtlFailFast(ecx)
0x14001455b  mov     rdx, [rdi]
0x14001455e  lea     r10, [rbx+390h]
0x140014565  mov     rax, rdx
0x140014568  mov     qword ptr [r10], 0
0x14001456f  neg     rax
0x140014572  sbb     cx, cx
0x140014575  xor     eax, eax
0x140014577  and     cx, 8
0x14001457b  mov     [r10+0Ah], ax
0x140014580  add     cx, 38h ; '8'
0x140014584  mov     [r10+20h], rax
0x140014588  mov     [r10+2Ch], eax
0x14001458c  mov     rax, rdx
0x14001458f  neg     rax
0x140014592  mov     [r10+8], cx
0x140014597  mov     eax, 1000h
0x14001459c  sbb     ecx, ecx
0x14001459e  and     ecx, eax
0x1400145a0  add     ecx, eax
0x1400145a2  mov     rax, [rdi+8]
0x1400145a6  shr     rax, 0Ch
0x1400145aa  mov     [r10+28h], ecx
0x1400145ae  mov     [r10+30h], rax
0x1400145b2  test    rdx, rdx
0x1400145b5  jz      short loc_1400145BF
0x1400145b7  shr     rdx, 0Ch
0x1400145bb  mov     [r10+38h], rdx
0x1400145bf  mov     eax, 2002h
0x1400145c4  or      [r10+0Ah], ax
0x1400145c9  movzx   eax, word ptr [r10+0Ah]
0x1400145ce  test    al, 5
0x1400145d0  jz      short loc_1400145D8
0x1400145d2  mov     rax, [r10+18h]
0x1400145d6  jmp     short loc_140014600
0x1400145d8  xor     r9d, r9d; RequestedAddress
0x1400145db  mov     [rsp+38h+Priority], 40000010h; Priority
0x1400145e3  xor     edx, edx; AccessMode
0x1400145e5  mov     [rsp+38h+BugCheckOnFailure], 0; BugCheckOnFailure
0x1400145ed  mov     rcx, r10; MemoryDescriptorList
0x1400145f0  lea     r8d, [r9+1]; CacheType
0x1400145f4  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400145fb  nop     dword ptr [rax+rax+00h]
0x140014600  test    rax, rax
0x140014603  jnz     short loc_140014643
0x140014605  mov     rcx, cs:WPP_GLOBAL_Control
0x14001460c  lea     rax, WPP_GLOBAL_Control
0x140014613  cmp     rcx, rax
0x140014616  jz      short loc_14001463C
0x140014618  test    dword ptr [rcx+2Ch], 1000000h
0x14001461f  jz      short loc_14001463C
0x140014621  cmp     byte ptr [rcx+29h], 2
0x140014625  jb      short loc_14001463C
0x140014627  mov     rcx, [rcx+18h]
0x14001462b  lea     r8, WPP_97df64ee0825388b346f901fe4767427_Traceguids
0x140014632  mov     edx, 0Bh
0x140014637  call    WPP_SF_
0x14001463c  mov     eax, 0C000009Ah
0x140014641  jmp     short loc_140014666
0x140014643  cmp     qword ptr [rdi], 0
0x140014647  mov     [rbx+368h], rax
0x14001464e  mov     [rbx+370h], rax
0x140014655  jz      short loc_140014664
0x140014657  add     rax, 1000h
0x14001465d  mov     [rbx+378h], rax
0x140014664  xor     eax, eax
0x140014666  mov     rbx, [rsp+38h+arg_0]
0x14001466b  add     rsp, 30h
0x14001466f  pop     rdi
0x140014670  retn
```
