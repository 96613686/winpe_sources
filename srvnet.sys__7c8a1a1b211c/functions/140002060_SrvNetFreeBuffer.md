# SrvNetFreeBuffer

- ea: `0x140002060`
- end: `0x140002212`
- name: `SrvNetFreeBuffer`
- size: `434`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `11`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400010f0`
- `0x140001d70`
- `0x1400022d0`
- `0x140002650`
- `0x1400027a0`
- `0x14000ab88`
- `0x140017190`
- `0x140017250`
- `0x140017bd4`
- `0x140018de0`
- `0x140053a6c`

## callees

- `0x140002060`
- `0x14000f390`
- `0x14000f3dc`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000219f`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000219f`
- `ntoskrnl!MmUnmapLockedPages` at `0x14000207a`
- `ntoskrnl!MmUnmapLockedPages` at `0x14000207a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400021ff`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400021ff`

## pseudocode

```c
void __fastcall SrvNetFreeBuffer(unsigned __int16 *Entry)
{
  __int64 v2; // rcx
  unsigned __int16 v3; // ax
  __int64 v4; // rax
  __int64 v5; // r9
  __int64 v6; // r8
  __int64 v7; // r10
  _QWORD *v8; // rax
  __int64 v9; // rax
  __int64 v10; // rsi
  unsigned int *v11; // rdi
  __int64 v12; // rsi
  signed int v13; // eax
  signed __int32 v14; // ecx
  int v15; // eax

  v2 = *((_QWORD *)Entry + 10);
  if ( (*(_BYTE *)(v2 + 10) & 0x20) != 0 )
    MmUnmapLockedPages(*(PVOID *)(v2 + 24), (PMDL)v2);
  v3 = Entry[8];
  if ( (v3 & 2) != 0 )
  {
    if ( (v3 & 1) != 0 )
    {
      *(_DWORD *)(*((_QWORD *)Entry + 7) + 44LL) += 80;
      *(_QWORD *)(*((_QWORD *)Entry + 7) + 24LL) += 80LL;
      *(_DWORD *)(*((_QWORD *)Entry + 7) + 40LL) -= 80;
      *(_WORD *)(*((_QWORD *)Entry + 7) + 10LL) |= 0x1000u;
      v4 = *((_QWORD *)Entry + 7);
      *((_QWORD *)Entry + 3) += 80LL;
      v5 = *((_QWORD *)Entry + 10);
      v6 = *(_QWORD *)(v4 + 24);
      v7 = *(unsigned int *)(v4 + 40);
      *(_QWORD *)v5 = 0;
      *(_WORD *)(v5 + 10) = 0;
      *(_DWORD *)(v5 + 40) = v7;
      *(_QWORD *)(v5 + 32) = v6 & 0xFFFFFFFFFFFFF000uLL;
      *(_DWORD *)(v5 + 44) = v6 & 0xFFF;
      *(_WORD *)(v5 + 8) = 8 * ((((unsigned __int64)(v6 & 0xFFF) + v7 + 4095) >> 12) + 6);
      *(_WORD *)(*((_QWORD *)Entry + 10) + 10LL) |= 4u;
    }
    v8 = (_QWORD *)*((_QWORD *)Entry + 7);
    Entry[8] = 0;
    Entry[11] = 0;
    *((_DWORD *)Entry + 9) = 0;
    *((_DWORD *)Entry + 16) = 0;
    *((_QWORD *)Entry + 9) = 0;
    *v8 = 0;
    **((_QWORD **)Entry + 10) = 0;
    v9 = Entry[9];
    v10 = Entry[10];
    *((_QWORD *)Entry + 11) = 0;
    *((_DWORD *)Entry + 24) = 0;
    v11 = (unsigned int *)SrvNetBufferLookasides[v9];
    v12 = v10 << 7;
    if ( !*((_BYTE *)v11 + v12 + 304) )
      PplpLazyInitializeLookasideList((__int64)v11, (__int64)v11 + v12 + 192);
    ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)v11 + v12 + 192), Entry);
    if ( SrvDisableNetBufferLookAsideList )
      PplFlushLookasideList(v11);
  }
  else
  {
    v13 = -*((_DWORD *)Entry + 10);
    v14 = v13 + _InterlockedExchangeAdd(&dword_1400365E4, v13);
    if ( v13 > 0 )
    {
      do
        v15 = dword_1400365EC;
      while ( v14 > dword_1400365EC && v15 != _InterlockedCompareExchange(&dword_1400365EC, v14, dword_1400365EC) );
    }
    ExFreePoolWithTag(*((PVOID *)Entry + 6), 0x3030534Cu);
  }
}

```

## disassembly

```asm
0x140002060  push    rbx
0x140002062  sub     rsp, 20h
0x140002066  mov     rbx, rcx
0x140002069  mov     rcx, [rcx+50h]
0x14000206d  test    byte ptr [rcx+0Ah], 20h
0x140002071  jz      short loc_140002086
0x140002073  mov     rdx, rcx; MemoryDescriptorList
0x140002076  mov     rcx, [rcx+18h]; BaseAddress
0x14000207a  call    cs:__imp_MmUnmapLockedPages
0x140002081  nop     dword ptr [rax+rax+00h]
0x140002086  movzx   eax, word ptr [rbx+10h]
0x14000208a  test    al, 2
0x14000208c  jz      loc_1400021CD
0x140002092  xor     r11d, r11d
0x140002095  mov     [rsp+28h+arg_0], rsi
0x14000209a  mov     [rsp+28h+arg_8], rdi
0x14000209f  test    al, 1
0x1400020a1  jz      loc_140002131
0x1400020a7  mov     rax, [rbx+38h]
0x1400020ab  mov     ecx, 1000h
0x1400020b0  add     dword ptr [rax+2Ch], 50h ; 'P'
0x1400020b4  mov     rax, [rbx+38h]
0x1400020b8  add     qword ptr [rax+18h], 50h ; 'P'
0x1400020bd  mov     rax, [rbx+38h]
0x1400020c1  add     dword ptr [rax+28h], 0FFFFFFB0h
0x1400020c5  mov     rax, [rbx+38h]
0x1400020c9  or      [rax+0Ah], cx
0x1400020cd  mov     rax, [rbx+38h]
0x1400020d1  add     qword ptr [rbx+18h], 50h ; 'P'
0x1400020d6  mov     r9, [rbx+50h]
0x1400020da  mov     r8, [rax+18h]
0x1400020de  mov     r10d, [rax+28h]
0x1400020e2  mov     edx, r8d
0x1400020e5  mov     eax, edx
0x1400020e7  mov     [r9], r11
0x1400020ea  and     eax, 0FFFh
0x1400020ef  mov     [r9+0Ah], r11w
0x1400020f4  and     r8, 0FFFFFFFFFFFFF000h
0x1400020fb  mov     [r9+28h], r10d
0x1400020ff  and     edx, 0FFFh
0x140002105  mov     [r9+20h], r8
0x140002109  mov     [r9+2Ch], edx
0x14000210d  lea     rcx, [r10+0FFFh]
0x140002114  add     rcx, rax
0x140002117  shr     rcx, 0Ch
0x14000211b  add     cx, 6
0x14000211f  shl     cx, 3
0x140002123  mov     [r9+8], cx
0x140002128  mov     rax, [rbx+50h]
0x14000212c  or      word ptr [rax+0Ah], 4
0x140002131  mov     rax, [rbx+38h]
0x140002135  lea     rdi, SrvNetBufferLookasides
0x14000213c  mov     [rbx+10h], r11w
0x140002141  mov     [rbx+16h], r11w
0x140002146  mov     [rbx+24h], r11d
0x14000214a  mov     [rbx+40h], r11d
0x14000214e  mov     [rbx+48h], r11
0x140002152  mov     [rax], r11
0x140002155  mov     rax, [rbx+50h]
0x140002159  mov     [rax], r11
0x14000215c  movzx   eax, word ptr [rbx+12h]
0x140002160  movzx   esi, word ptr [rbx+14h]
0x140002164  mov     [rbx+58h], r11
0x140002168  mov     [rbx+60h], r11d
0x14000216c  mov     rdi, [rdi+rax*8]
0x140002170  shl     rsi, 7
0x140002174  movzx   eax, byte ptr [rsi+rdi+130h]
0x14000217c  test    al, al
0x14000217e  jnz     short loc_140002192
0x140002180  lea     rdx, [rdi+0C0h]
0x140002187  mov     rcx, rdi
0x14000218a  add     rdx, rsi
0x14000218d  call    PplpLazyInitializeLookasideList
0x140002192  lea     rcx, [rsi+0C0h]
0x140002199  mov     rdx, rbx; Entry
0x14000219c  add     rcx, rdi; Lookaside
0x14000219f  call    cs:__imp_ExFreeToLookasideListEx
0x1400021a6  nop     dword ptr [rax+rax+00h]
0x1400021ab  cmp     cs:SrvDisableNetBufferLookAsideList, 0
0x1400021b2  mov     rsi, [rsp+28h+arg_0]
0x1400021b7  jz      short loc_1400021C1
0x1400021b9  mov     rcx, rdi
0x1400021bc  call    PplFlushLookasideList
0x1400021c1  mov     rdi, [rsp+28h+arg_8]
0x1400021c6  add     rsp, 20h
0x1400021ca  pop     rbx
0x1400021cb  retn
0x1400021cd  mov     eax, [rbx+28h]
0x1400021d0  neg     eax
0x1400021d2  mov     ecx, eax
0x1400021d4  lock xadd cs:dword_1400365E4, ecx
0x1400021dc  add     ecx, eax
0x1400021de  test    eax, eax
0x1400021e0  jle     short loc_1400021F6
0x1400021e2  mov     eax, cs:dword_1400365EC
0x1400021e8  cmp     ecx, eax
0x1400021ea  jle     short loc_1400021F6
0x1400021ec  lock cmpxchg cs:dword_1400365EC, ecx
0x1400021f4  jnz     short loc_1400021E2
0x1400021f6  mov     rcx, [rbx+30h]; P
0x1400021fa  mov     edx, 3030534Ch; Tag
0x1400021ff  call    cs:__imp_ExFreePoolWithTag
0x140002206  nop     dword ptr [rax+rax+00h]
0x14000220b  add     rsp, 20h
0x14000220f  pop     rbx
0x140002210  retn
```
