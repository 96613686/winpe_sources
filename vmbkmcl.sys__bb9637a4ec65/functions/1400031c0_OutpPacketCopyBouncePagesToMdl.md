# OutpPacketCopyBouncePagesToMdl

- ea: `0x1400031c0`
- end: `0x140003599`
- name: `OutpPacketCopyBouncePagesToMdl`
- size: `985`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1400026f0`
- `0x14000a248`

## callees

- `0x1400031c0`
- `0x140011f80`
- `0x140012280`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003329`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003329`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003497`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003497`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400033aa`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400033aa`
- `ntoskrnl!KeBugCheckEx` at `0x14000358c`
- `ntoskrnl!KeBugCheckEx` at `0x14000358c`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x1400033cc`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x1400033cc`
- `ntoskrnl!MmUnmapLockedPages` at `0x14000346a`
- `ntoskrnl!MmUnmapLockedPages` at `0x140003513`
- `ntoskrnl!MmUnmapLockedPages` at `0x14000346a`
- `ntoskrnl!MmUnmapLockedPages` at `0x140003513`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000329e`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000329e`
- `ntoskrnl!MmUnmapReservedMapping` at `0x140003451`
- `ntoskrnl!MmUnmapReservedMapping` at `0x140003451`

## pseudocode

```c
void __fastcall OutpPacketCopyBouncePagesToMdl(ULONG_PTR a1, __int64 a2, char a3)
{
  ULONG_PTR v4; // rsi
  __int64 *v5; // r15
  char v6; // al
  __int64 v8; // rbx
  struct _MDL *v9; // rdi
  unsigned int ByteCount; // eax
  char *MappedSystemVa; // rax
  __int64 *v12; // r12
  unsigned int v13; // eax
  unsigned int v14; // r13d
  __int64 v15; // r15
  char *v16; // rdi
  unsigned int v17; // ebx
  __int64 v18; // rbp
  __int64 v19; // rcx
  void *v20; // rax
  __int64 v21; // rcx
  struct _MDL *v22; // rdi
  size_t v23; // rsi
  PVOID v24; // rcx
  char *v25; // r15
  const void *v26; // rdx
  __int64 v27; // rax
  __int64 v28; // rcx
  __int64 v29; // rdi
  unsigned int v30; // ebx
  CSHORT MdlFlags; // [rsp+30h] [rbp-78h]
  unsigned int v32; // [rsp+34h] [rbp-74h]
  char *v33; // [rsp+38h] [rbp-70h]
  struct _MDL *SourceMdl; // [rsp+40h] [rbp-68h]
  char *v35; // [rsp+48h] [rbp-60h]
  char *VirtualAddress; // [rsp+50h] [rbp-58h]
  __int64 *v37; // [rsp+58h] [rbp-50h]
  PVOID MappingAddress; // [rsp+60h] [rbp-48h]
  char v40; // [rsp+B8h] [rbp+10h]
  KIRQL v41; // [rsp+C8h] [rbp+20h]

  v4 = a1;
  if ( *(_BYTE *)(a2 + 61) == 1 )
  {
    v5 = *(__int64 **)(a2 + 80);
    v37 = v5;
    if ( v5 )
    {
      v6 = *(_BYTE *)(a2 + 62);
      if ( a3 ? (v6 & 0x20) == 0 : (v6 & 0x10) == 0 )
      {
        v8 = *(unsigned int *)(a2 + 72);
        v9 = *(struct _MDL **)(a2 + 64);
        SourceMdl = v9;
        v41 = 0;
        v40 = 0;
        do
        {
          ByteCount = v9->ByteCount;
          if ( (unsigned int)v8 < ByteCount )
          {
            MdlFlags = v9->MdlFlags;
            VirtualAddress = (char *)v9->StartVa + v9->ByteOffset + v8;
            if ( (MdlFlags & 5) != 0 )
              MappedSystemVa = (char *)v9->MappedSystemVa;
            else
              MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(v9, 0, MmCached, 0, 0, 0x40000020u);
            v35 = MappedSystemVa;
            if ( MappedSystemVa )
              v33 = &MappedSystemVa[v8];
            else
              v33 = 0;
            v12 = (__int64 *)v5[2];
            v13 = *((_DWORD *)v5 + 2);
            v14 = *((_DWORD *)v5 + 3);
            v32 = v13;
            if ( v12 != v5 + 2 )
            {
              do
              {
                v15 = v12[4];
                if ( v14 && !a3 )
                {
                  memset((void *)v12[4], 0, v14);
                  v13 = v32;
                }
                v16 = v35;
                v17 = 4096 - v14;
                v18 = v13;
                if ( v13 > 4096 - v14 )
                  v18 = v17;
                if ( v35 )
                {
                  v24 = v33;
                  v23 = (unsigned int)v18;
                }
                else
                {
                  if ( !a3 )
                  {
                    v41 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v4 + 256));
                    v40 = 1;
                  }
                  v19 = 760;
                  if ( !a3 )
                    v19 = 648;
                  v20 = *(void **)(v19 + v4);
                  v21 = 768;
                  MappingAddress = v20;
                  if ( !a3 )
                    v21 = 656;
                  v22 = *(struct _MDL **)(v21 + v4);
                  v23 = (unsigned int)v18;
                  v22->Next = 0;
                  v22->MdlFlags = 0;
                  v22->StartVa = 0;
                  v22->ByteOffset = 0;
                  v22->Size = 8 * (((unsigned __int64)(v18 + 4095) >> 12) + 6);
                  v22->ByteCount = v18;
                  IoBuildPartialMdl(SourceMdl, v22, VirtualAddress, v18);
                  v24 = MmMapLockedPagesWithReservedMapping(MappingAddress, 0x636D6B56u, v22, MmCached);
                  if ( !v24 )
                    KeBugCheckEx(0x53495650u, 0x35Eu, a1, (ULONG_PTR)MappingAddress, 0);
                  v16 = 0;
                }
                v25 = (char *)(v14 + v15);
                v14 = 0;
                if ( a3 )
                {
                  v26 = v25;
                }
                else
                {
                  v26 = v24;
                  v24 = v25;
                }
                memmove(v24, v26, v23);
                if ( !v16 )
                {
                  v27 = 768;
                  if ( !a3 )
                    v27 = 656;
                  v28 = 760;
                  v29 = *(_QWORD *)(v27 + a1);
                  if ( !a3 )
                    v28 = 648;
                  MmUnmapReservedMapping(*(PVOID *)(v28 + a1), 0x636D6B56u, (PMDL)v29);
                  if ( (*(_BYTE *)(v29 + 10) & 0x20) != 0 )
                    MmUnmapLockedPages(*(PVOID *)(v29 + 24), (PMDL)v29);
                  if ( v40 )
                  {
                    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 256), v41);
                    v40 = 0;
                  }
                }
                VirtualAddress += v23;
                v13 = v32 - v18;
                v33 += v23;
                v32 -= v18;
                v30 = v17 - v18;
                if ( v30 && !a3 )
                {
                  memset(&v25[v23], 0, v30);
                  v13 = v32;
                }
                v5 = v37;
                v12 = (__int64 *)*v12;
                v4 = a1;
              }
              while ( v12 != v37 + 2 );
              v9 = SourceMdl;
            }
            v8 = 0;
            if ( (MdlFlags & 1) == 0 && (v9->MdlFlags & 1) != 0 )
              MmUnmapLockedPages(v9->MappedSystemVa, v9);
            v5 = (__int64 *)*v5;
            v37 = v5;
          }
          else
          {
            v8 = (unsigned int)v8 - ByteCount;
          }
          v9 = v9->Next;
          SourceMdl = v9;
        }
        while ( v5 );
      }
    }
  }
}

```

## disassembly

```asm
0x1400031c0  mov     [rsp+BugCheckParameter2], rcx
0x1400031c5  push    rsi
0x1400031c6  push    r14
0x1400031c8  sub     rsp, 98h
0x1400031cf  cmp     byte ptr [rdx+3Dh], 1
0x1400031d3  movzx   r14d, r8b
0x1400031d7  mov     rsi, rcx
0x1400031da  jnz     loc_140003562
0x1400031e0  mov     [rsp+0A8h+var_38], r15
0x1400031e5  mov     r15, [rdx+50h]
0x1400031e9  mov     [rsp+0A8h+var_50], r15
0x1400031ee  test    r15, r15
0x1400031f1  jz      loc_14000355D
0x1400031f7  movzx   eax, byte ptr [rdx+3Eh]
0x1400031fb  test    r8b, r8b
0x1400031fe  jz      short loc_140003204
0x140003200  test    al, 20h
0x140003202  jmp     short loc_140003206
0x140003204  test    al, 10h
0x140003206  jnz     loc_14000355D
0x14000320c  mov     [rsp+0A8h+arg_10], rbx
0x140003214  mov     ebx, [rdx+48h]
0x140003217  mov     [rsp+0A8h+var_18], rbp
0x14000321f  mov     [rsp+0A8h+var_20], rdi
0x140003227  mov     rdi, [rdx+40h]
0x14000322b  mov     [rsp+0A8h+var_28], r12
0x140003233  mov     [rsp+0A8h+SourceMdl], rdi
0x140003238  mov     [rsp+0A8h+var_30], r13
0x14000323d  mov     [rsp+0A8h+arg_18], 0
0x140003245  mov     [rsp+0A8h+arg_8], 0
0x14000324d  nop     dword ptr [rax]
0x140003250  mov     eax, [rdi+28h]
0x140003253  cmp     ebx, eax
0x140003255  jb      short loc_14000325E
0x140003257  sub     ebx, eax
0x140003259  jmp     loc_140003527
0x14000325e  movzx   eax, word ptr [rdi+0Ah]
0x140003262  mov     ecx, [rdi+2Ch]
0x140003265  add     rcx, [rdi+20h]
0x140003269  add     rcx, rbx
0x14000326c  mov     [rsp+0A8h+var_78], ax
0x140003271  mov     [rsp+0A8h+VirtualAddress], rcx
0x140003276  test    al, 5
0x140003278  jz      short loc_140003280
0x14000327a  mov     rax, [rdi+18h]
0x14000327e  jmp     short loc_1400032AA
0x140003280  mov     [rsp+0A8h+Priority], 40000020h; Priority
0x140003288  xor     r9d, r9d; RequestedAddress
0x14000328b  xor     edx, edx; AccessMode
0x14000328d  mov     [rsp+0A8h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140003295  mov     r8d, 1; CacheType
0x14000329b  mov     rcx, rdi; MemoryDescriptorList
0x14000329e  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400032a5  nop     dword ptr [rax+rax+00h]
0x1400032aa  mov     [rsp+0A8h+var_60], rax
0x1400032af  test    rax, rax
0x1400032b2  jnz     short loc_1400032BB
0x1400032b4  mov     [rsp+0A8h+var_70], rax
0x1400032b9  jmp     short loc_1400032C3
0x1400032bb  add     rax, rbx
0x1400032be  mov     [rsp+0A8h+var_70], rax
0x1400032c3  mov     r12, [r15+10h]
0x1400032c7  lea     rcx, [r15+10h]
0x1400032cb  mov     eax, [r15+8]
0x1400032cf  mov     r13d, [r15+0Ch]
0x1400032d3  mov     [rsp+0A8h+var_74], eax
0x1400032d7  cmp     r12, rcx
0x1400032da  jz      loc_1400034FD
0x1400032e0  mov     r15, [r12+20h]
0x1400032e5  test    r13d, r13d
0x1400032e8  jz      short loc_140003300
0x1400032ea  test    r14b, r14b
0x1400032ed  jnz     short loc_140003300
0x1400032ef  mov     r8d, r13d; Size
0x1400032f2  xor     edx, edx; Val
0x1400032f4  mov     rcx, r15; void *
0x1400032f7  call    memset
0x1400032fc  mov     eax, [rsp+0A8h+var_74]
0x140003300  mov     rdi, [rsp+0A8h+var_60]
0x140003305  mov     ebx, 1000h
0x14000330a  sub     ebx, r13d
0x14000330d  mov     ebp, eax
0x14000330f  cmp     eax, ebx
0x140003311  cmova   ebp, ebx
0x140003314  test    rdi, rdi
0x140003317  jnz     loc_1400033EB
0x14000331d  test    r14b, r14b
0x140003320  jnz     short loc_140003344
0x140003322  lea     rcx, [rsi+100h]; SpinLock
0x140003329  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003330  nop     dword ptr [rax+rax+00h]
0x140003335  mov     [rsp+0A8h+arg_18], al
0x14000333c  mov     [rsp+0A8h+arg_8], 1
0x140003344  mov     r8, [rsp+0A8h+VirtualAddress]; VirtualAddress
0x140003349  test    r14b, r14b
0x14000334c  mov     eax, 288h
0x140003351  mov     ecx, 2F8h
0x140003356  cmovz   ecx, eax
0x140003359  mov     r9d, ebp; Length
0x14000335c  mov     rax, [rcx+rsi]
0x140003360  mov     ecx, 300h
0x140003365  mov     [rsp+0A8h+MappingAddress], rax
0x14000336a  mov     eax, 290h
0x14000336f  cmovz   ecx, eax
0x140003372  lea     rax, [rbp+0FFFh]
0x140003379  shr     rax, 0Ch
0x14000337d  add     ax, 6
0x140003381  shl     ax, 3
0x140003385  mov     rdi, [rcx+rsi]
0x140003389  xor     ecx, ecx
0x14000338b  mov     rdx, rdi; TargetMdl
0x14000338e  mov     esi, ebp
0x140003390  mov     [rdi], rcx
0x140003393  mov     [rdi+0Ah], cx
0x140003397  mov     [rdi+20h], rcx
0x14000339b  mov     [rdi+2Ch], ecx
0x14000339e  mov     rcx, [rsp+0A8h+SourceMdl]; SourceMdl
0x1400033a3  mov     [rdi+8], ax
0x1400033a7  mov     [rdi+28h], ebp
0x1400033aa  call    cs:__imp_IoBuildPartialMdl
0x1400033b1  nop     dword ptr [rax+rax+00h]
0x1400033b6  mov     r8, rdi; MemoryDescriptorList
0x1400033b9  mov     r9d, 1; CacheType
0x1400033bf  mov     rdi, [rsp+0A8h+MappingAddress]
0x1400033c4  mov     edx, 636D6B56h; PoolTag
0x1400033c9  mov     rcx, rdi; MappingAddress
0x1400033cc  call    cs:__imp_MmMapLockedPagesWithReservedMapping
0x1400033d3  nop     dword ptr [rax+rax+00h]
0x1400033d8  mov     rcx, rax
0x1400033db  test    rax, rax
0x1400033de  jz      loc_14000356E
0x1400033e4  mov     rdi, [rsp+0A8h+var_60]
0x1400033e9  jmp     short loc_1400033F2
0x1400033eb  mov     rcx, [rsp+0A8h+var_70]
0x1400033f0  mov     esi, ebp
0x1400033f2  mov     eax, r13d
0x1400033f5  mov     r8, rsi; Size
0x1400033f8  add     r15, rax
0x1400033fb  xor     r13d, r13d
0x1400033fe  test    r14b, r14b
0x140003401  jz      short loc_140003408
0x140003403  mov     rdx, r15
0x140003406  jmp     short loc_14000340E
0x140003408  mov     rdx, rcx; Src
0x14000340b  mov     rcx, r15; void *
0x14000340e  call    memmove
0x140003413  test    rdi, rdi
0x140003416  jnz     loc_1400034AB
0x14000341c  mov     r9, [rsp+0A8h+BugCheckParameter2]
0x140003424  test    r14b, r14b
0x140003427  mov     ecx, 290h
0x14000342c  mov     eax, 300h
0x140003431  cmovz   eax, ecx
0x140003434  mov     edx, 636D6B56h; PoolTag
0x140003439  mov     ecx, 2F8h
0x14000343e  mov     rdi, [rax+r9]
0x140003442  mov     eax, 288h
0x140003447  cmovz   ecx, eax
0x14000344a  mov     r8, rdi; MemoryDescriptorList
0x14000344d  mov     rcx, [rcx+r9]; BaseAddress
0x140003451  call    cs:__imp_MmUnmapReservedMapping
0x140003458  nop     dword ptr [rax+rax+00h]
0x14000345d  test    byte ptr [rdi+0Ah], 20h
0x140003461  jz      short loc_140003476
0x140003463  mov     rcx, [rdi+18h]; BaseAddress
0x140003467  mov     rdx, rdi; MemoryDescriptorList
0x14000346a  call    cs:__imp_MmUnmapLockedPages
0x140003471  nop     dword ptr [rax+rax+00h]
0x140003476  cmp     [rsp+0A8h+arg_8], r13b
0x14000347e  jz      short loc_1400034AB
0x140003480  mov     rcx, [rsp+0A8h+BugCheckParameter2]
0x140003488  movzx   edx, [rsp+0A8h+arg_18]; NewIrql
0x140003490  add     rcx, 100h; SpinLock
0x140003497  call    cs:__imp_KeReleaseSpinLock
0x14000349e  nop     dword ptr [rax+rax+00h]
0x1400034a3  mov     [rsp+0A8h+arg_8], r13b
0x1400034ab  mov     eax, [rsp+0A8h+var_74]
0x1400034af  add     [rsp+0A8h+VirtualAddress], rsi
0x1400034b4  sub     eax, ebp
0x1400034b6  add     [rsp+0A8h+var_70], rsi
0x1400034bb  mov     [rsp+0A8h+var_74], eax
0x1400034bf  sub     ebx, ebp
0x1400034c1  jz      short loc_1400034DA
0x1400034c3  test    r14b, r14b
0x1400034c6  jnz     short loc_1400034DA
0x1400034c8  mov     r8d, ebx; Size
0x1400034cb  lea     rcx, [r15+rsi]; void *
0x1400034cf  xor     edx, edx; Val
0x1400034d1  call    memset
0x1400034d6  mov     eax, [rsp+0A8h+var_74]
0x1400034da  mov     r15, [rsp+0A8h+var_50]
0x1400034df  mov     r12, [r12]
0x1400034e3  mov     rsi, [rsp+0A8h+BugCheckParameter2]
0x1400034eb  lea     rcx, [r15+10h]
0x1400034ef  cmp     r12, rcx
0x1400034f2  jnz     loc_1400032E0
0x1400034f8  mov     rdi, [rsp+0A8h+SourceMdl]
0x1400034fd  xor     ebx, ebx
0x1400034ff  test    byte ptr [rsp+0A8h+var_78], 1
0x140003504  jnz     short loc_14000351F
0x140003506  test    byte ptr [rdi+0Ah], 1
0x14000350a  jz      short loc_14000351F
0x14000350c  mov     rcx, [rdi+18h]; BaseAddress
0x140003510  mov     rdx, rdi; MemoryDescriptorList
0x140003513  call    cs:__imp_MmUnmapLockedPages
0x14000351a  nop     dword ptr [rax+rax+00h]
0x14000351f  mov     r15, [r15]
0x140003522  mov     [rsp+0A8h+var_50], r15
0x140003527  mov     rdi, [rdi]
0x14000352a  mov     [rsp+0A8h+SourceMdl], rdi
0x14000352f  test    r15, r15
0x140003532  jnz     loc_140003250
0x140003538  mov     r13, [rsp+0A8h+var_30]
0x14000353d  mov     r12, [rsp+0A8h+var_28]
0x140003545  mov     rdi, [rsp+0A8h+var_20]
0x14000354d  mov     rbp, [rsp+0A8h+var_18]
0x140003555  mov     rbx, [rsp+0A8h+arg_10]
0x14000355d  mov     r15, [rsp+0A8h+var_38]
0x140003562  add     rsp, 98h
0x140003569  pop     r14
0x14000356b  pop     rsi
0x14000356c  retn
0x14000356e  mov     r8, [rsp+0A8h+BugCheckParameter2]; BugCheckParameter2
0x140003576  mov     r9, rdi; BugCheckParameter3
0x140003579  mov     edx, 35Eh; BugCheckParameter1
0x14000357e  mov     qword ptr [rsp+0A8h+BugCheckOnFailure], 0; BugCheckParameter4
0x140003587  mov     ecx, 53495650h; BugCheckCode
0x14000358c  call    cs:__imp_KeBugCheckEx
```
