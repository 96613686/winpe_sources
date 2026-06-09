# SrvNetCompleteSendData

- ea: `0x1400022d0`
- end: `0x140002648`
- name: `SrvNetCompleteSendData`
- size: `888`
- prototype: ``
- caller_count: `7`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400010f0`
- `0x140002220`
- `0x14000f9c0`
- `0x140012ed8`
- `0x140018680`
- `0x14001a250`
- `0x14001c0d8`

## callees

- `0x140002060`
- `0x1400022d0`
- `0x14000380c`
- `0x14000f390`
- `0x14000f3dc`
- `0x14001056c`
- `0x14001389c`
- `0x1400186dc`
- `0x14002a4c0`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x14000252d`
- `ntoskrnl!IoFreeIrp` at `0x14000252d`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140002494`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140002494`
- `ntoskrnl!MmUnmapLockedPages` at `0x14000237c`
- `ntoskrnl!MmUnmapLockedPages` at `0x14000237c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400024ed`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400024ed`

## pseudocode

```c
__int64 __fastcall SrvNetCompleteSendData(int a1, __int64 a2, __int64 a3)
{
  unsigned int v4; // r15d
  int v6; // eax
  __int64 *v7; // rax
  __int64 *v8; // rbx
  __int64 v9; // rax
  __int64 v10; // rcx
  __int16 v11; // ax
  __int64 v12; // rax
  __int64 v13; // r9
  __int64 v14; // r8
  __int64 v15; // r10
  _QWORD *v16; // rax
  __int64 v17; // rax
  __int64 v18; // rbp
  __int64 v19; // rsi
  __int64 v20; // rbp
  signed int v21; // eax
  signed __int32 v22; // ecx
  int v23; // eax
  __int64 *v24; // rcx
  __int64 v25; // rax
  unsigned __int64 v26; // rax
  __int64 v27; // rbp
  unsigned __int64 v28; // r9
  unsigned __int64 v29; // rbx
  __int64 v30; // rsi
  __int64 v31; // rsi

  v4 = a2;
  if ( a1 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        11,
        WPP_13dfc6c10cd0357b2fe0dd4f6ff3f414_Traceguids,
        (unsigned int)a1);
    }
    v4 = 0;
    SrvNetDisconnectConnectionInternalEx(*(_QWORD *)(a3 + 56), 0);
  }
  v6 = *(_DWORD *)(a3 + 48);
  if ( (v6 & 8) != 0 )
  {
    v7 = *(__int64 **)(a3 + 8);
    v8 = v7 - 18;
    v9 = *v7;
    *(_DWORD *)a3 -= 52;
    *(_QWORD *)(a3 + 8) = v9;
    v10 = v8[10];
    if ( (*(_BYTE *)(v10 + 10) & 0x20) != 0 )
      MmUnmapLockedPages(*(PVOID *)(v10 + 24), (PMDL)v8[10]);
    v11 = *((_WORD *)v8 + 8);
    if ( (v11 & 2) != 0 )
    {
      if ( (v11 & 1) != 0 )
      {
        *(_DWORD *)(v8[7] + 44) += 80;
        *(_QWORD *)(v8[7] + 24) += 80LL;
        *(_DWORD *)(v8[7] + 40) -= 80;
        *(_WORD *)(v8[7] + 10) |= 0x1000u;
        v12 = v8[7];
        v8[3] += 80;
        v13 = v8[10];
        v14 = *(_QWORD *)(v12 + 24);
        v15 = *(unsigned int *)(v12 + 40);
        *(_QWORD *)v13 = 0;
        *(_WORD *)(v13 + 10) = 0;
        *(_DWORD *)(v13 + 40) = v15;
        *(_QWORD *)(v13 + 32) = v14 & 0xFFFFFFFFFFFFF000uLL;
        *(_DWORD *)(v13 + 44) = v14 & 0xFFF;
        *(_WORD *)(v13 + 8) = 8 * ((((unsigned __int64)(v14 & 0xFFF) + v15 + 4095) >> 12) + 6);
        *(_WORD *)(v8[10] + 10) |= 4u;
      }
      v16 = (_QWORD *)v8[7];
      *((_WORD *)v8 + 8) = 0;
      *((_WORD *)v8 + 11) = 0;
      *((_DWORD *)v8 + 9) = 0;
      *((_DWORD *)v8 + 16) = 0;
      v8[9] = 0;
      *v16 = 0;
      *(_QWORD *)v8[10] = 0;
      v17 = *((unsigned __int16 *)v8 + 9);
      v18 = *((unsigned __int16 *)v8 + 10);
      v8[11] = 0;
      *((_DWORD *)v8 + 24) = 0;
      v19 = SrvNetBufferLookasides[v17];
      v20 = v18 << 7;
      if ( !*(_BYTE *)(v20 + v19 + 304) )
        PplpLazyInitializeLookasideList(v19, v20 + v19 + 192);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v20 + v19 + 192), v8);
      if ( SrvDisableNetBufferLookAsideList )
        PplFlushLookasideList(v19);
    }
    else
    {
      v21 = -*((_DWORD *)v8 + 10);
      v22 = v21 + _InterlockedExchangeAdd(&dword_1400365E4, v21);
      if ( v21 > 0 )
      {
        do
          v23 = dword_1400365EC;
        while ( v22 > dword_1400365EC && v23 != _InterlockedCompareExchange(&dword_1400365EC, v22, dword_1400365EC) );
      }
      ExFreePoolWithTag((PVOID)v8[6], 0x3030534Cu);
    }
    *(_DWORD *)(a3 + 48) &= ~8u;
    v6 = *(_DWORD *)(a3 + 48);
  }
  if ( (v6 & 0x10) != 0 )
  {
    v24 = *(__int64 **)(a3 + 8);
    v25 = *v24;
    *(_DWORD *)a3 -= 16;
    *(_QWORD *)(a3 + 8) = v25;
    SrvNetFreeBuffer(v24 - 18);
    *(_DWORD *)(a3 + 48) &= ~0x10u;
    v6 = *(_DWORD *)(a3 + 48);
  }
  if ( (v6 & 1) != 0 )
  {
    IoFreeIrp(*(PIRP *)(a3 + 40));
    *(_DWORD *)(a3 + 48) &= ~1u;
    *(_QWORD *)(a3 + 40) = 0;
  }
  if ( *(_DWORD *)a3 <= 0x100u )
  {
    v26 = *(_QWORD *)(a3 + 64);
    if ( MEMORY[0xFFFFF78000000014] > v26 )
    {
      if ( v26 )
      {
        v27 = *(_QWORD *)(a3 + 56);
        if ( v27 )
        {
          v28 = *(_QWORD *)(v27 + 616);
          v29 = MEMORY[0xFFFFF78000000014] - v26;
          if ( v28 )
          {
            v31 = 8 * v28;
            if ( 8 * v28 < v28
              && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              WPP_SF_i(WPP_GLOBAL_Control->AttachedDevice);
            }
            v30 = (v29 + v31 - *(_QWORD *)(v27 + 616)) >> 3;
          }
          else
          {
            v30 = MEMORY[0xFFFFF78000000014] - v26;
          }
          _InterlockedExchange64((volatile __int64 *)(v27 + 616), v30);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_qiid(
              WPP_GLOBAL_Control->AttachedDevice,
              a2,
              a3,
              *(_QWORD *)(a3 + 56),
              *(_QWORD *)(v27 + 616),
              v29,
              *(_DWORD *)a3);
          }
        }
      }
    }
  }
  return (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(a3 + 16))((unsigned int)a1, v4, a3);
}

```

## disassembly

```asm
0x1400022d0  push    rdi
0x1400022d2  push    r13
0x1400022d4  push    r14
0x1400022d6  push    r15
0x1400022d8  sub     rsp, 48h
0x1400022dc  mov     [rsp+68h+var_28], r12
0x1400022e1  lea     r13, WPP_GLOBAL_Control
0x1400022e8  xor     r12d, r12d
0x1400022eb  mov     rdi, r8
0x1400022ee  mov     r15d, edx
0x1400022f1  mov     r14d, ecx
0x1400022f4  test    ecx, ecx
0x1400022f6  jns     short loc_140002339
0x1400022f8  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400022ff  cmp     rcx, r13
0x140002302  jz      short loc_14000232B
0x140002304  test    dword ptr [rcx+2Ch], 2000h
0x14000230b  jz      short loc_14000232B
0x14000230d  cmp     byte ptr [rcx+29h], 1
0x140002311  jb      short loc_14000232B
0x140002313  mov     rcx, [rcx+18h]
0x140002317  lea     r8, WPP_13dfc6c10cd0357b2fe0dd4f6ff3f414_Traceguids
0x14000231e  mov     edx, 0Bh
0x140002323  mov     r9d, r14d
0x140002326  call    WPP_SF_d
0x14000232b  mov     rcx, [rdi+38h]
0x14000232f  xor     edx, edx
0x140002331  mov     r15d, r12d
0x140002334  call    SrvNetDisconnectConnectionInternalEx
0x140002339  mov     eax, [rdi+30h]
0x14000233c  mov     [rsp+68h+arg_0], rbx
0x140002341  mov     [rsp+68h+arg_8], rbp
0x140002346  mov     [rsp+68h+arg_10], rsi
0x14000234e  test    al, 8
0x140002350  jz      loc_140002500
0x140002356  mov     rax, [rdi+8]
0x14000235a  lea     rbx, [rax-90h]
0x140002361  mov     rax, [rax]
0x140002364  add     dword ptr [rdi], 0FFFFFFCCh
0x140002367  mov     [rdi+8], rax
0x14000236b  mov     rcx, [rbx+50h]
0x14000236f  test    byte ptr [rcx+0Ah], 20h
0x140002373  jz      short loc_140002388
0x140002375  mov     rdx, rcx; MemoryDescriptorList
0x140002378  mov     rcx, [rcx+18h]; BaseAddress
0x14000237c  call    cs:__imp_MmUnmapLockedPages
0x140002383  nop     dword ptr [rax+rax+00h]
0x140002388  movzx   eax, word ptr [rbx+10h]
0x14000238c  test    al, 2
0x14000238e  jz      loc_1400024B3
0x140002394  test    al, 1
0x140002396  jz      loc_140002426
0x14000239c  mov     rax, [rbx+38h]
0x1400023a0  mov     ecx, 1000h
0x1400023a5  add     dword ptr [rax+2Ch], 50h ; 'P'
0x1400023a9  mov     rax, [rbx+38h]
0x1400023ad  add     qword ptr [rax+18h], 50h ; 'P'
0x1400023b2  mov     rax, [rbx+38h]
0x1400023b6  add     dword ptr [rax+28h], 0FFFFFFB0h
0x1400023ba  mov     rax, [rbx+38h]
0x1400023be  or      [rax+0Ah], cx
0x1400023c2  mov     rax, [rbx+38h]
0x1400023c6  add     qword ptr [rbx+18h], 50h ; 'P'
0x1400023cb  mov     r9, [rbx+50h]
0x1400023cf  mov     r8, [rax+18h]
0x1400023d3  mov     r10d, [rax+28h]
0x1400023d7  mov     edx, r8d
0x1400023da  mov     eax, edx
0x1400023dc  mov     [r9], r12
0x1400023df  and     eax, 0FFFh
0x1400023e4  mov     [r9+0Ah], r12w
0x1400023e9  and     r8, 0FFFFFFFFFFFFF000h
0x1400023f0  mov     [r9+28h], r10d
0x1400023f4  and     edx, 0FFFh
0x1400023fa  mov     [r9+20h], r8
0x1400023fe  mov     [r9+2Ch], edx
0x140002402  lea     rcx, [r10+0FFFh]
0x140002409  add     rcx, rax
0x14000240c  shr     rcx, 0Ch
0x140002410  add     cx, 6
0x140002414  shl     cx, 3
0x140002418  mov     [r9+8], cx
0x14000241d  mov     rax, [rbx+50h]
0x140002421  or      word ptr [rax+0Ah], 4
0x140002426  mov     rax, [rbx+38h]
0x14000242a  lea     rsi, SrvNetBufferLookasides
0x140002431  mov     [rbx+10h], r12w
0x140002436  mov     [rbx+16h], r12w
0x14000243b  mov     [rbx+24h], r12d
0x14000243f  mov     [rbx+40h], r12d
0x140002443  mov     [rbx+48h], r12
0x140002447  mov     [rax], r12
0x14000244a  mov     rax, [rbx+50h]
0x14000244e  mov     [rax], r12
0x140002451  movzx   eax, word ptr [rbx+12h]
0x140002455  movzx   ebp, word ptr [rbx+14h]
0x140002459  mov     [rbx+58h], r12
0x14000245d  mov     [rbx+60h], r12d
0x140002461  mov     rsi, [rsi+rax*8]
0x140002465  shl     rbp, 7
0x140002469  movzx   eax, byte ptr [rbp+rsi+130h]
0x140002471  test    al, al
0x140002473  jnz     short loc_140002487
0x140002475  lea     rdx, [rsi+0C0h]
0x14000247c  mov     rcx, rsi
0x14000247f  add     rdx, rbp
0x140002482  call    PplpLazyInitializeLookasideList
0x140002487  lea     rcx, [rsi+0C0h]
0x14000248e  mov     rdx, rbx; Entry
0x140002491  add     rcx, rbp; Lookaside
0x140002494  call    cs:__imp_ExFreeToLookasideListEx
0x14000249b  nop     dword ptr [rax+rax+00h]
0x1400024a0  cmp     cs:SrvDisableNetBufferLookAsideList, r12b
0x1400024a7  jz      short loc_1400024F9
0x1400024a9  mov     rcx, rsi
0x1400024ac  call    PplFlushLookasideList
0x1400024b1  jmp     short loc_1400024F9
0x1400024b3  mov     eax, [rbx+28h]
0x1400024b6  neg     eax
0x1400024b8  mov     ecx, eax
0x1400024ba  lock xadd cs:dword_1400365E4, ecx
0x1400024c2  add     ecx, eax
0x1400024c4  test    eax, eax
0x1400024c6  jle     short loc_1400024E4
0x1400024c8  nop     dword ptr [rax+rax+00000000h]
0x1400024d0  mov     eax, cs:dword_1400365EC
0x1400024d6  cmp     ecx, eax
0x1400024d8  jle     short loc_1400024E4
0x1400024da  lock cmpxchg cs:dword_1400365EC, ecx
0x1400024e2  jnz     short loc_1400024D0
0x1400024e4  mov     rcx, [rbx+30h]; P
0x1400024e8  mov     edx, 3030534Ch; Tag
0x1400024ed  call    cs:__imp_ExFreePoolWithTag
0x1400024f4  nop     dword ptr [rax+rax+00h]
0x1400024f9  and     dword ptr [rdi+30h], 0FFFFFFF7h
0x1400024fd  mov     eax, [rdi+30h]
0x140002500  test    al, 10h
0x140002502  jz      short loc_140002525
0x140002504  mov     rcx, [rdi+8]
0x140002508  mov     rax, [rcx]
0x14000250b  add     rcx, 0FFFFFFFFFFFFFF70h; Entry
0x140002512  add     dword ptr [rdi], 0FFFFFFF0h
0x140002515  mov     [rdi+8], rax
0x140002519  call    SrvNetFreeBuffer
0x14000251e  and     dword ptr [rdi+30h], 0FFFFFFEFh
0x140002522  mov     eax, [rdi+30h]
0x140002525  test    al, 1
0x140002527  jz      short loc_140002541
0x140002529  mov     rcx, [rdi+28h]; Irp
0x14000252d  call    cs:__imp_IoFreeIrp
0x140002534  nop     dword ptr [rax+rax+00h]
0x140002539  and     dword ptr [rdi+30h], 0FFFFFFFEh
0x14000253d  mov     [rdi+28h], r12
0x140002541  cmp     dword ptr [rdi], 100h
0x140002547  mov     r12, [rsp+68h+var_28]
0x14000254c  ja      loc_140002617
0x140002552  mov     rbx, 0FFFFF78000000014h
0x14000255c  mov     rbx, [rbx]
0x14000255f  mov     rax, [rdi+40h]
0x140002563  cmp     rbx, rax
0x140002566  jbe     loc_140002617
0x14000256c  test    rax, rax
0x14000256f  jz      loc_140002617
0x140002575  mov     rbp, [rdi+38h]
0x140002579  test    rbp, rbp
0x14000257c  jz      loc_140002617
0x140002582  mov     r9, [rbp+268h]
0x140002589  sub     rbx, rax
0x14000258c  test    r9, r9
0x14000258f  jnz     short loc_140002596
0x140002591  mov     rsi, rbx
0x140002594  jmp     short loc_1400025D3
0x140002596  lea     rsi, ds:0[r9*8]
0x14000259e  cmp     rsi, r9
0x1400025a1  jnb     short loc_1400025C5
0x1400025a3  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400025aa  cmp     rcx, r13
0x1400025ad  jz      short loc_1400025C5
0x1400025af  mov     eax, [rcx+2Ch]
0x1400025b2  test    al, 10h
0x1400025b4  jz      short loc_1400025C5
0x1400025b6  cmp     byte ptr [rcx+29h], 2
0x1400025ba  jb      short loc_1400025C5
0x1400025bc  mov     rcx, [rcx+18h]
0x1400025c0  call    WPP_SF_i
0x1400025c5  sub     rsi, [rbp+268h]
0x1400025cc  add     rsi, rbx
0x1400025cf  shr     rsi, 3
0x1400025d3  xchg    rsi, [rbp+268h]; __annotation("TMF:",
0x1400025da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400025e1  cmp     rcx, r13
0x1400025e4  jz      short loc_140002617
0x1400025e6  mov     eax, [rcx+2Ch]
0x1400025e9  test    al, 10h
0x1400025eb  jz      short loc_140002617
0x1400025ed  cmp     byte ptr [rcx+29h], 4
0x1400025f1  jb      short loc_140002617
0x1400025f3  mov     eax, [rdi]
0x1400025f5  mov     r9, [rdi+38h]
0x1400025f9  mov     rcx, [rcx+18h]
0x1400025fd  mov     [rsp+68h+var_38], eax
0x140002601  mov     rax, [rbp+268h]
0x140002608  mov     [rsp+68h+var_40], rbx
0x14000260d  mov     [rsp+68h+var_48], rax
0x140002612  call    WPP_SF_qiid
0x140002617  mov     rax, [rdi+10h]
0x14000261b  mov     r8, rdi
0x14000261e  mov     edx, r15d
0x140002621  mov     ecx, r14d
0x140002624  call    _guard_dispatch_icall
0x140002629  mov     rsi, [rsp+68h+arg_10]
0x140002631  mov     rbp, [rsp+68h+arg_8]
0x140002636  mov     rbx, [rsp+68h+arg_0]
0x14000263b  add     rsp, 48h
0x14000263f  pop     r15
0x140002641  pop     r14
0x140002643  pop     r13
0x140002645  pop     rdi
0x140002646  retn
```
