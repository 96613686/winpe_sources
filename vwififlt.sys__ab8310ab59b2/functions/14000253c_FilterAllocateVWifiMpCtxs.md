# FilterAllocateVWifiMpCtxs

- ea: `0x14000253c`
- end: `0x140002708`
- name: `FilterAllocateVWifiMpCtxs`
- size: `460`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140002710`

## callees

- `0x14000253c`
- `0x140007d00`
- `0x14000cd98`
- `0x14000d8ec`
- `0x14000d91c`

## string_xrefs

- `0x1400025c8`: `DOT11_VWIFI_COMBINATION_REVISION_3 == Combinations->Header.Revision`

## pseudocode

```c
__int64 __fastcall FilterAllocateVWifiMpCtxs(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v3; // r14d
  unsigned int v4; // ebx
  char v5; // r15
  __int64 v6; // rdi
  char v7; // r12
  __int64 v9; // r13
  unsigned int v10; // r11d
  __int64 v11; // r9
  int v12; // r10d
  int v13; // edx
  unsigned int v14; // eax
  unsigned int v15; // ebx

  v3 = *(_DWORD *)(a2 + 4);
  v4 = 0;
  v5 = 0;
  v6 = a3;
  v7 = 0;
  v9 = a1;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 104, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
  if ( *(_DWORD *)(v6 + 2692) != 16 )
    TraceAssert("IS_FILTER_MINIPORT_MEDIA_TYPE_802_11(pFilter)", "onecoreuap\\net\\vwifi\\filter\\filter.c", 1752);
  if ( *(_BYTE *)(a2 + 9) != 3 )
    TraceAssert(
      "DOT11_VWIFI_COMBINATION_REVISION_3 == Combinations->Header.Revision",
      "onecoreuap\\net\\vwifi\\filter\\filter.c",
      1753);
  v10 = 0;
  if ( v3 )
  {
    v11 = 0;
    do
    {
      a3 = 3;
      v12 = *(_DWORD *)(a2 + 24 * v11 + 28);
      if ( v12 )
      {
        a3 = (unsigned int)(v12 + 4);
        v7 = 1;
      }
      v13 = *(_DWORD *)(a2 + 24 * v11 + 24);
      if ( v13 )
        v5 = 1;
      *(_DWORD *)(v6 + 4 * ((v13 != 0 ? 2 : 0) | (unsigned __int64)(*(_DWORD *)(a2 + 24 * v11 + 20) != 0)) + 2660) = v12;
      v14 = *(_DWORD *)(a2 + 24 * v11 + 28);
      if ( *(_DWORD *)(v6 + 2676) < v14 )
        *(_DWORD *)(v6 + 2676) = v14;
      if ( (unsigned int)a3 <= v4 )
        a3 = v4;
      ++v10;
      ++v11;
      v4 = a3;
    }
    while ( v10 < v3 );
    v9 = a1;
  }
  *(_DWORD *)(v6 + 2684) = v4;
  *(_BYTE *)(v6 + 2657) = v5;
  *(_BYTE *)(v6 + 2659) = v7;
  v15 = AllocMem(v9, 144 * v4, a3, v6 + 3120);
  if ( v15 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return v15;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 105, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 106, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
  return v15;
}

```

## disassembly

```asm
0x14000253c  mov     [rsp+arg_0], rcx
0x140002541  push    rbx
0x140002542  push    rbp
0x140002543  push    rsi
0x140002544  push    rdi
0x140002545  push    r12
0x140002547  push    r13
0x140002549  push    r14
0x14000254b  push    r15
0x14000254d  sub     rsp, 28h
0x140002551  mov     r14d, [rdx+4]
0x140002555  xor     ebx, ebx
0x140002557  xor     r15b, r15b
0x14000255a  mov     rdi, r8
0x14000255d  xor     r12b, r12b
0x140002560  mov     rsi, rdx
0x140002563  mov     r13, rcx
0x140002566  mov     rcx, cs:WPP_GLOBAL_Control
0x14000256d  lea     rax, WPP_GLOBAL_Control
0x140002574  cmp     rcx, rax
0x140002577  jz      short loc_140002593
0x140002579  mov     eax, [rcx+2Ch]
0x14000257c  test    al, 20h
0x14000257e  jz      short loc_140002593
0x140002580  mov     rcx, [rcx+18h]
0x140002584  lea     edx, [rbx+68h]
0x140002587  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x14000258e  call    WPP_SF_
0x140002593  cmp     dword ptr [rdi+0A84h], 10h
0x14000259a  jz      short loc_1400025B5
0x14000259c  mov     r8d, 6D8h
0x1400025a2  lea     rdx, aOnecoreuapNetV_1; "onecoreuap\\net\\vwifi\\filter\\filter."...
0x1400025a9  lea     rcx, aIsFilterMinipo; "IS_FILTER_MINIPORT_MEDIA_TYPE_802_11(pF"...
0x1400025b0  call    TraceAssert
0x1400025b5  cmp     byte ptr [rsi+9], 3
0x1400025b9  jz      short loc_1400025D4
0x1400025bb  mov     r8d, 6D9h
0x1400025c1  lea     rdx, aOnecoreuapNetV_1; "onecoreuap\\net\\vwifi\\filter\\filter."...
0x1400025c8  lea     rcx, aDot11VwifiComb; "DOT11_VWIFI_COMBINATION_REVISION_3 == C"...
0x1400025cf  call    TraceAssert
0x1400025d4  xor     r11d, r11d
0x1400025d7  lea     ebp, [r11+1]
0x1400025db  test    r14d, r14d
0x1400025de  jz      short loc_14000265E
0x1400025e0  xor     r9d, r9d
0x1400025e3  mov     r13d, ebp
0x1400025e6  lea     rbp, [r9+r9*2]
0x1400025ea  mov     r8d, 3
0x1400025f0  mov     r10d, [rsi+rbp*8+1Ch]
0x1400025f5  test    r10d, r10d
0x1400025f8  jz      short loc_140002601
0x1400025fa  lea     r8d, [r10+4]
0x1400025fe  mov     r12b, r13b
0x140002601  mov     edx, [rsi+rbp*8+18h]
0x140002605  test    edx, edx
0x140002607  movzx   r15d, r15b
0x14000260b  cmovnz  r15d, r13d
0x14000260f  xor     ecx, ecx
0x140002611  cmp     [rsi+rbp*8+14h], ecx
0x140002615  setnbe  cl
0x140002618  xor     eax, eax
0x14000261a  cmp     eax, edx
0x14000261c  sbb     rax, rax
0x14000261f  and     eax, 2
0x140002622  or      rcx, rax
0x140002625  mov     [rdi+rcx*4+0A64h], r10d
0x14000262d  mov     eax, [rsi+rbp*8+1Ch]
0x140002631  cmp     [rdi+0A74h], eax
0x140002637  jnb     short loc_14000263F
0x140002639  mov     [rdi+0A74h], eax
0x14000263f  cmp     r8d, ebx
0x140002642  cmovbe  r8d, ebx
0x140002646  add     r11d, r13d
0x140002649  add     r9, r13
0x14000264c  mov     ebx, r8d
0x14000264f  cmp     r11d, r14d
0x140002652  jb      short loc_1400025E6
0x140002654  mov     r13, [rsp+68h+arg_0]
0x140002659  mov     ebp, 1
0x14000265e  lea     edx, [rbx+rbx*8]
0x140002661  mov     [rdi+0A7Ch], ebx
0x140002667  shl     edx, 4
0x14000266a  lea     r9, [rdi+0C30h]
0x140002671  mov     rcx, r13
0x140002674  mov     [rdi+0A61h], r15b
0x14000267b  mov     [rdi+0A63h], r12b
0x140002682  call    AllocMem
0x140002687  mov     ebx, eax
0x140002689  test    eax, eax
0x14000268b  jz      short loc_1400026C2
0x14000268d  mov     rcx, cs:WPP_GLOBAL_Control
0x140002694  lea     rdi, WPP_GLOBAL_Control
0x14000269b  cmp     rcx, rdi
0x14000269e  jz      short loc_1400026F4
0x1400026a0  mov     edx, [rcx+2Ch]
0x1400026a3  test    bpl, dl
0x1400026a6  jz      short loc_1400026C9
0x1400026a8  mov     rcx, [rcx+18h]
0x1400026ac  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x1400026b3  mov     edx, 69h ; 'i'
0x1400026b8  mov     r9d, eax
0x1400026bb  call    WPP_SF_d
0x1400026c0  jmp     short loc_1400026C9
0x1400026c2  lea     rdi, WPP_GLOBAL_Control
0x1400026c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400026d0  cmp     rcx, rdi
0x1400026d3  jz      short loc_1400026F4
0x1400026d5  mov     eax, [rcx+2Ch]
0x1400026d8  test    al, 20h
0x1400026da  jz      short loc_1400026F4
0x1400026dc  mov     rcx, [rcx+18h]
0x1400026e0  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x1400026e7  mov     edx, 6Ah ; 'j'
0x1400026ec  mov     r9d, ebx
0x1400026ef  call    WPP_SF_d
0x1400026f4  mov     eax, ebx
0x1400026f6  add     rsp, 28h
0x1400026fa  pop     r15
0x1400026fc  pop     r14
0x1400026fe  pop     r13
0x140002700  pop     r12
0x140002702  pop     rdi
0x140002703  pop     rsi
0x140002704  pop     rbp
0x140002705  pop     rbx
0x140002706  retn
```
