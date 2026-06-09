# ParsePacket2(AutoPtr<NtpPeer>,NtpSimplePeer *,NtpPacket *)

- ea: `0x18001b170`
- end: `0x18001b793`
- name: `?ParsePacket2@@YAXV?$AutoPtr@UNtpPeer@@@@PEAUNtpSimplePeer@@PEAUNtpPacket@@@Z`
- size: `1571`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001bdb0`

## callees

- `0x180014774`
- `0x180018138`
- `0x18001b170`
- `0x18001d9a0`
- `0x18003a830`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001b691`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001b691`

## string_xrefs

- `0x18001b5dd`: `Peer %s is Win2K. Setting compat flags.\n`
- `0x18001b61b`: `Peer %s is not Win2K. Setting compat flags.\n`
- `0x18001b6b0`: `Peer %s is not Win2K. Setting compat flags.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall ParsePacket2(volatile signed __int32 **a1, __int64 a2, __int64 a3)
{
  volatile signed __int32 *v6; // rcx
  __int64 v7; // rbp
  int v8; // ebp
  __int64 v9; // rax
  __int64 v10; // rdi
  __int64 v11; // rsi
  __int64 ClockPeriodInFileTimeIncrements; // r8
  __int64 v13; // rsi
  unsigned __int64 v14; // rcx
  unsigned __int64 v15; // rdx
  char v16; // di
  char v17; // si
  int v18; // ecx
  int v19; // eax
  __int64 v20; // rcx
  char v21; // r13
  __int64 v22; // rcx
  char v23; // bp
  char v24; // r12
  unsigned __int64 v25; // rcx
  char v26; // r15
  bool v27; // al
  signed __int32 v28; // eax
  unsigned __int64 v29; // rax
  int v31; // [rsp+20h] [rbp-58h] BYREF
  int v32; // [rsp+24h] [rbp-54h] BYREF
  _QWORD v33[10]; // [rsp+28h] [rbp-50h] BYREF
  unsigned __int8 v34; // [rsp+88h] [rbp+10h]
  unsigned __int8 v35; // [rsp+90h] [rbp+18h] BYREF
  char v36; // [rsp+98h] [rbp+20h] BYREF

  v31 = 0;
  v6 = *a1;
  if ( v6 && (v7 = *((_QWORD *)v6 + 1)) != 0 )
  {
    v8 = *(_DWORD *)(v7 + 60);
  }
  else
  {
    v8 = *((_DWORD *)g_pnpstate + 46);
    if ( !v6 || !*((_QWORD *)v6 + 1) )
      goto LABEL_11;
  }
  if ( (v8 & 0x40000000) != 0 )
  {
    if ( *(_DWORD *)(a3 + 8) == -1431655766 )
    {
      if ( (unsigned __int8)FileLogAllowEntry(113) )
        FileLogAdd(L"Peer %s is Win2K. Setting compat flags.\n", *((_QWORD *)*a1 + 1) + 290LL);
      *(_DWORD *)(*((_QWORD *)*a1 + 1) + 60LL) &= 0x3FFFFFFFu;
      *(_DWORD *)(*((_QWORD *)*a1 + 1) + 60LL) |= 3u;
    }
    else
    {
      if ( (unsigned __int8)FileLogAllowEntry(113) )
        FileLogAdd(L"Peer %s is not Win2K. Setting compat flags.\n", *((_QWORD *)*a1 + 1) + 290LL);
      *(_DWORD *)(*((_QWORD *)*a1 + 1) + 60LL) &= 0x3FFFFFFFu;
    }
    v8 = *(_DWORD *)(*((_QWORD *)*a1 + 1) + 60LL);
  }
  if ( v8 < 0 )
  {
    if ( *(_DWORD *)(*((_QWORD *)*a1 + 1) + 64LL) == *(_DWORD *)(a3 + 8) )
    {
      if ( (unsigned __int8)FileLogAllowEntry(113) )
        FileLogAdd(L"Peer %s may be Win2K. Will verify on next packet.\n", *((_QWORD *)*a1 + 1) + 290LL);
      *(_DWORD *)(*((_QWORD *)*a1 + 1) + 60LL) |= 0x40000000u;
      *(_QWORD *)(*((_QWORD *)*a1 + 1) + 280LL) = 0;
      SetEvent(*((HANDLE *)g_pnpstate + 58));
    }
    else
    {
      if ( (unsigned __int8)FileLogAllowEntry(113) )
        FileLogAdd(L"Peer %s is not Win2K. Setting compat flags.\n", *((_QWORD *)*a1 + 1) + 290LL);
      *(_DWORD *)(*((_QWORD *)*a1 + 1) + 60LL) &= 0x3FFFFFFFu;
    }
    v8 = *(_DWORD *)(*((_QWORD *)*a1 + 1) + 60LL);
  }
LABEL_11:
  if ( (v8 & 1) != 0 )
    *(_QWORD *)(a2 + 24) = gc_toZero;
  v33[0] = 0;
  v36 = 0;
  v35 = 0;
  v32 = 0;
  (*((void (__fastcall **)(__int64, _QWORD *))g_pnpstate + 2))(1, v33);
  (*((void (__fastcall **)(__int64, char *))g_pnpstate + 2))(6, &v36);
  (*((void (__fastcall **)(__int64, unsigned __int8 *))g_pnpstate + 2))(7, &v35);
  (*((void (__fastcall **)(__int64, int *))g_pnpstate + 2))(8, &v32);
  (*((void (__fastcall **)(__int64, int *))g_pnpstate + 2))(2, &v31);
  v9 = *(_QWORD *)(a2 + 72);
  v10 = *(_QWORD *)(a2 + 48);
  v11 = *(_QWORD *)(a2 + 88);
  *(_QWORD *)(a2 + 96) = *(_QWORD *)(a2 + 64) + v11 - v10 - v9;
  *(_QWORD *)(a2 + 104) = (*(_QWORD *)(a2 + 64) + v9 - v11 - v10) / 2;
  ClockPeriodInFileTimeIncrements = (unsigned int)GetClockPeriodInFileTimeIncrements(v33);
  v13 = v11 - v10;
  v14 = -v13;
  if ( v13 > 0 )
    v14 = v13;
  v15 = v14 / 0x15180;
  *(_QWORD *)(a2 + 112) = v14 / 0x15180 + ClockPeriodInFileTimeIncrements;
  if ( *(_DWORD *)a2 == 5 )
  {
    v16 = 1;
    v17 = 1;
  }
  else
  {
    if ( *(_QWORD *)(a2 + 80) == *(_QWORD *)(*((_QWORD *)*a1 + 1) + 816LL) )
    {
      v16 = 0;
      if ( (unsigned __int8)FileLogAllowEntry(104) )
        FileLogAdd(L"Packet test 1 failed (we've seen this response).\n");
    }
    else
    {
      v16 = 1;
    }
    if ( *(_QWORD *)(a2 + 56) == *(_QWORD *)(*((_QWORD *)*a1 + 1) + 808LL) )
    {
      v17 = 1;
    }
    else
    {
      v17 = 0;
      if ( (unsigned __int8)FileLogAllowEntry(104) )
        FileLogAdd(L"Packet test 2 failed (response does not match request).\n");
    }
  }
  if ( gc_toZero == *(_QWORD *)(a3 + 24) || gc_toZero == *(_QWORD *)(a3 + 32) )
  {
    v34 = 0;
    if ( (unsigned __int8)FileLogAllowEntry(104) )
      FileLogAdd(L"Packet test 3 failed (looks like a request).\n");
    LOBYTE(v15) = 0;
  }
  else
  {
    LOBYTE(v15) = 1;
    v34 = 1;
  }
  v18 = v31;
  if ( v31 < *(char *)(a2 + 14) )
  {
    v18 = *(char *)(a2 + 14);
    v31 = v18;
  }
  if ( v18 >= 0 )
    v19 = 20000000 << v18;
  else
    v19 = 20000000 >> -(char)v18;
  v20 = *(_QWORD *)(a2 + 96);
  if ( v20 + v19 < 0 )
    goto LABEL_26;
  v29 = -v20;
  if ( v20 > 0 )
    v29 = *(_QWORD *)(a2 + 96);
  if ( v29 >= 0x9896800 || *(_QWORD *)(a2 + 112) >= 0x9896800u )
  {
LABEL_26:
    v21 = 0;
    if ( (unsigned __int8)FileLogAllowEntry(104) )
      FileLogAdd(L"Packet test 4 failed (bad value for delay or dispersion).\n");
    LODWORD(v15) = v34;
  }
  else
  {
    v21 = 1;
  }
  if ( *(_DWORD *)(a2 + 8) != 3
    && ((v8 & 2) != 0 || *(_QWORD *)(a2 + 40) <= *(_QWORD *)(a2 + 72))
    && ((v22 = *(_QWORD *)(a2 + 40), *(_QWORD *)(a2 + 72) < (unsigned __int64)(v22 + 864000000000LL))
     || v22 == 94354848000000000LL) )
  {
    v23 = 1;
  }
  else
  {
    v23 = 0;
    if ( (unsigned __int8)FileLogAllowEntry(104) )
      FileLogAdd(L"Packet test 6 failed (not syncd or bad interval since last sync).\n");
    LODWORD(v15) = v34;
  }
  if ( (unsigned __int8)(*(_BYTE *)(a2 + 12) - 1) <= 0xDu )
  {
    v24 = 1;
  }
  else
  {
    v24 = 0;
    if ( (unsigned __int8)FileLogAllowEntry(104) )
      FileLogAdd(L"Packet test 7 failed (bad stratum: system - %d, sample - %d).\n", v35, *(unsigned __int8 *)(a2 + 12));
    LODWORD(v15) = v34;
  }
  v25 = -*(_QWORD *)(a2 + 16);
  if ( *(__int64 *)(a2 + 16) > 0 )
    v25 = *(_QWORD *)(a2 + 16);
  if ( v25 >= 0x9896800 || *(_QWORD *)(a2 + 24) >= 0x9896800u )
  {
    v26 = 0;
    if ( (unsigned __int8)FileLogAllowEntry(104) )
      FileLogAdd(L"Packet test 8 failed (bad value for root delay or root dispersion).\n");
    LODWORD(v15) = v34;
  }
  else
  {
    v26 = 1;
  }
  v27 = v16 && v17 && (_BYTE)v15 && v21;
  *(_BYTE *)(a2 + 169) = v27;
  LOBYTE(v28) = v23 && v24 && v26;
  *(_BYTE *)(a2 + 168) = v28;
  *(_BYTE *)(a2 + 160) = v16;
  *(_BYTE *)(a2 + 161) = v17;
  *(_BYTE *)(a2 + 162) = v15;
  *(_BYTE *)(a2 + 163) = v21;
  *(_BYTE *)(a2 + 164) = 1;
  *(_BYTE *)(a2 + 165) = v23;
  *(_BYTE *)(a2 + 166) = v24;
  *(_BYTE *)(a2 + 167) = v26;
  if ( *a1 )
  {
    v28 = _InterlockedExchangeAdd(*a1, 0xFFFFFFFF);
    if ( v28 == 1 )
    {
      if ( *a1 )
        LOBYTE(v28) = (unsigned __int8)Ref<NtpPeer>::`scalar deleting destructor'(*a1, v15);
    }
  }
  return v28;
}

```

## disassembly

```asm
0x18001b170  mov     [rsp+arg_0], rcx
0x18001b175  push    rbx
0x18001b176  push    rbp
0x18001b177  push    rsi
0x18001b178  push    rdi
0x18001b179  push    r12
0x18001b17b  push    r13
0x18001b17d  push    r14
0x18001b17f  push    r15
0x18001b181  sub     rsp, 38h
0x18001b185  mov     r15, r8
0x18001b188  mov     rbx, rdx
0x18001b18b  mov     r14, rcx
0x18001b18e  xor     edi, edi
0x18001b190  mov     [rsp+78h+var_58], edi
0x18001b194  mov     rcx, [rcx]
0x18001b197  test    rcx, rcx
0x18001b19a  jz      loc_18001B468
0x18001b1a0  mov     rbp, [rcx+8]
0x18001b1a4  test    rbp, rbp
0x18001b1a7  jz      loc_18001B468
0x18001b1ad  mov     ebp, [rbp+3Ch]
0x18001b1b0  bt      ebp, 1Eh
0x18001b1b4  jb      loc_18001B5B7
0x18001b1ba  test    ebp, ebp
0x18001b1bc  jns     short loc_18001B1FC
0x18001b1be  mov     rax, [r14]
0x18001b1c1  mov     rdx, [rax+8]
0x18001b1c5  mov     eax, [r15+8]
0x18001b1c9  mov     ecx, 71h ; 'q'
0x18001b1ce  cmp     [rdx+40h], eax
0x18001b1d1  jz      loc_18001B644
0x18001b1d7  call    FileLogAllowEntry
0x18001b1dc  test    al, al
0x18001b1de  jnz     loc_18001B6A2
0x18001b1e4  mov     rax, [r14]
0x18001b1e7  mov     rcx, [rax+8]
0x18001b1eb  and     dword ptr [rcx+3Ch], 3FFFFFFFh
0x18001b1f2  mov     rax, [r14]
0x18001b1f5  mov     rcx, [rax+8]
0x18001b1f9  mov     ebp, [rcx+3Ch]
0x18001b1fc  test    bpl, 1
0x18001b200  jnz     loc_18001B6C1
0x18001b206  mov     [rsp+78h+var_50], rdi
0x18001b20b  mov     [rsp+78h+arg_18], dil
0x18001b213  mov     [rsp+78h+arg_10], dil
0x18001b21b  mov     [rsp+78h+var_54], edi
0x18001b21f  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x18001b226  lea     rdx, [rsp+78h+var_50]
0x18001b22b  mov     ecx, 1
0x18001b230  mov     rax, [rax+10h]
0x18001b234  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b239  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x18001b240  lea     rdx, [rsp+78h+arg_18]
0x18001b248  mov     ecx, 6
0x18001b24d  mov     rax, [rax+10h]
0x18001b251  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b256  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x18001b25d  lea     rdx, [rsp+78h+arg_10]
0x18001b265  mov     ecx, 7
0x18001b26a  mov     rax, [rax+10h]
0x18001b26e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b273  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x18001b27a  lea     rdx, [rsp+78h+var_54]
0x18001b27f  mov     ecx, 8
0x18001b284  mov     rax, [rax+10h]
0x18001b288  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b28d  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x18001b294  lea     rdx, [rsp+78h+var_58]
0x18001b299  mov     ecx, 2
0x18001b29e  mov     rax, [rax+10h]
0x18001b2a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b2a7  mov     rax, [rbx+48h]
0x18001b2ab  mov     rdi, [rbx+30h]
0x18001b2af  mov     rsi, [rbx+58h]
0x18001b2b3  mov     rcx, rsi
0x18001b2b6  sub     rcx, rdi
0x18001b2b9  sub     rcx, rax
0x18001b2bc  add     rcx, [rbx+40h]
0x18001b2c0  mov     [rbx+60h], rcx
0x18001b2c4  sub     rax, rsi
0x18001b2c7  sub     rax, rdi
0x18001b2ca  add     rax, [rbx+40h]
0x18001b2ce  cqo
0x18001b2d0  sub     rax, rdx
0x18001b2d3  sar     rax, 1
0x18001b2d6  mov     [rbx+68h], rax
0x18001b2da  lea     rcx, [rsp+78h+var_50]
0x18001b2df  call    GetClockPeriodInFileTimeIncrements
0x18001b2e4  mov     r8d, eax
0x18001b2e7  sub     rsi, rdi
0x18001b2ea  mov     rcx, rsi
0x18001b2ed  neg     rcx
0x18001b2f0  cmovs   rcx, rsi
0x18001b2f4  mov     rax, 0C22E450672894AB7h
0x18001b2fe  mul     rcx
0x18001b301  shr     rdx, 10h
0x18001b305  add     r8, rdx
0x18001b308  mov     [rbx+70h], r8
0x18001b30c  cmp     dword ptr [rbx], 5
0x18001b30f  jnz     loc_18001B508
0x18001b315  mov     dil, 1
0x18001b318  movzx   esi, dil
0x18001b31c  mov     rax, cs:?gc_toZero@@3UNtTimeOffset@@B; NtTimeOffset const gc_toZero
0x18001b323  cmp     rax, [r15+18h]
0x18001b327  jnz     loc_18001B55D
0x18001b32d  mov     [rsp+78h+arg_8], 0
0x18001b335  mov     ecx, 68h ; 'h'
0x18001b33a  call    FileLogAllowEntry
0x18001b33f  test    al, al
0x18001b341  jz      short loc_18001B34F
0x18001b343  lea     rcx, aPacketTest3Fai; "Packet test 3 failed (looks like a requ"...
0x18001b34a  call    FileLogAdd
0x18001b34f  xor     dl, dl
0x18001b351  movsx   eax, byte ptr [rbx+0Eh]
0x18001b355  mov     ecx, [rsp+78h+var_58]
0x18001b359  cmp     ecx, eax
0x18001b35b  jge     short loc_18001B363
0x18001b35d  mov     ecx, eax
0x18001b35f  mov     [rsp+78h+var_58], eax
0x18001b363  mov     eax, 1312D00h
0x18001b368  test    ecx, ecx
0x18001b36a  jns     loc_18001B48D
0x18001b370  neg     ecx
0x18001b372  sar     eax, cl
0x18001b374  mov     rcx, [rbx+60h]
0x18001b378  cdqe
0x18001b37a  add     rax, rcx
0x18001b37d  jns     loc_18001B575
0x18001b383  xor     r13b, r13b
0x18001b386  mov     ecx, 68h ; 'h'
0x18001b38b  call    FileLogAllowEntry
0x18001b390  test    al, al
0x18001b392  jz      short loc_18001B3A0
0x18001b394  lea     rcx, aPacketTest4Fai; "Packet test 4 failed (bad value for del"...
0x18001b39b  call    FileLogAdd
0x18001b3a0  movzx   edx, [rsp+78h+arg_8]
0x18001b3a8  cmp     dword ptr [rbx+8], 3
0x18001b3ac  jz      loc_18001B721
0x18001b3b2  test    bpl, 2
0x18001b3b6  jz      loc_18001B6FF
0x18001b3bc  mov     rcx, [rbx+28h]
0x18001b3c0  mov     rax, 0C92A69C000h
0x18001b3ca  add     rax, rcx
0x18001b3cd  cmp     [rbx+48h], rax
0x18001b3d1  jnb     loc_18001B70E
0x18001b3d7  mov     bpl, 1
0x18001b3da  movzx   eax, byte ptr [rbx+0Ch]
0x18001b3de  dec     al
0x18001b3e0  cmp     al, 0Dh
0x18001b3e2  jbe     loc_18001B74B
0x18001b3e8  xor     r12b, r12b
0x18001b3eb  mov     ecx, 68h ; 'h'
0x18001b3f0  call    FileLogAllowEntry
0x18001b3f5  test    al, al
0x18001b3f7  jz      short loc_18001B412
0x18001b3f9  movzx   r8d, byte ptr [rbx+0Ch]
0x18001b3fe  movzx   edx, [rsp+78h+arg_10]
0x18001b406  lea     rcx, aPacketTest7Fai; "Packet test 7 failed (bad stratum: syst"...
0x18001b40d  call    FileLogAdd
0x18001b412  movzx   edx, [rsp+78h+arg_8]
0x18001b41a  mov     rcx, [rbx+10h]
0x18001b41e  neg     rcx
0x18001b421  cmovs   rcx, [rbx+10h]
0x18001b426  cmp     rcx, 9896800h
0x18001b42d  jb      loc_18001B5A1
0x18001b433  xor     r15b, r15b
0x18001b436  mov     ecx, 68h ; 'h'
0x18001b43b  call    FileLogAllowEntry
0x18001b440  test    al, al
0x18001b442  jz      short loc_18001B450
0x18001b444  lea     rcx, aPacketTest8Fai; "Packet test 8 failed (bad value for roo"...
0x18001b44b  call    FileLogAdd
0x18001b450  movzx   edx, [rsp+78h+arg_8]
0x18001b458  test    dil, dil
0x18001b45b  jnz     loc_18001B753
0x18001b461  xor     al, al
0x18001b463  jmp     loc_18001B76F
0x18001b468  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x18001b46f  mov     ebp, [rax+0B8h]
0x18001b475  test    rcx, rcx
0x18001b478  jz      loc_18001B1FC
0x18001b47e  cmp     [rcx+8], rdi
0x18001b482  jz      loc_18001B1FC
0x18001b488  jmp     loc_18001B1B0
0x18001b48d  shl     eax, cl
0x18001b48f  jmp     loc_18001B374
0x18001b494  mov     [rbx+0A8h], al
0x18001b49a  mov     [rbx+0A0h], dil
0x18001b4a1  mov     [rbx+0A1h], sil
0x18001b4a8  mov     [rbx+0A2h], dl
0x18001b4ae  mov     [rbx+0A3h], r13b
0x18001b4b5  mov     byte ptr [rbx+0A4h], 1
0x18001b4bc  mov     [rbx+0A5h], bpl
0x18001b4c3  mov     [rbx+0A6h], r12b
0x18001b4ca  mov     [rbx+0A7h], r15b
0x18001b4d1  mov     rcx, [r14]
0x18001b4d4  test    rcx, rcx
0x18001b4d7  jz      short loc_18001B4E7
0x18001b4d9  mov     eax, 0FFFFFFFFh
0x18001b4de  lock xadd [rcx], eax
0x18001b4e2  cmp     eax, 1
0x18001b4e5  jz      short loc_18001B4F9
0x18001b4e7  add     rsp, 38h
0x18001b4eb  pop     r15
0x18001b4ed  pop     r14
0x18001b4ef  pop     r13
0x18001b4f1  pop     r12
0x18001b4f3  pop     rdi
0x18001b4f4  pop     rsi
0x18001b4f5  pop     rbp
0x18001b4f6  pop     rbx
0x18001b4f7  retn
0x18001b4f9  mov     rcx, [r14]; void *
0x18001b4fc  test    rcx, rcx
0x18001b4ff  jz      short loc_18001B4E7
0x18001b501  call    ??_G?$Ref@UNtpPeer@@@@QEAAPEAXI@Z; Ref<NtpPeer>::`scalar deleting destructor'(uint)
0x18001b506  jmp     short loc_18001B4E7
0x18001b508  mov     rax, [r14]
0x18001b50b  mov     rcx, [rax+8]
0x18001b50f  mov     rax, [rcx+330h]
0x18001b516  cmp     [rbx+50h], rax
0x18001b51a  jnz     loc_18001B6D1
0x18001b520  xor     dil, dil
0x18001b523  mov     ecx, 68h ; 'h'
0x18001b528  call    FileLogAllowEntry
0x18001b52d  test    al, al
0x18001b52f  jz      short loc_18001B53D
0x18001b531  lea     rcx, aPacketTest1Fai; "Packet test 1 failed (we've seen this r"...
0x18001b538  call    FileLogAdd
0x18001b53d  mov     rax, [r14]
0x18001b540  mov     rcx, [rax+8]
0x18001b544  mov     rax, [rcx+328h]
0x18001b54b  cmp     [rbx+38h], rax
0x18001b54f  jnz     loc_18001B6D9
0x18001b555  mov     sil, 1
0x18001b558  jmp     loc_18001B31C
0x18001b55d  cmp     rax, [r15+20h]
0x18001b561  jz      loc_18001B32D
0x18001b567  mov     dl, 1
0x18001b569  mov     [rsp+78h+arg_8], dl
0x18001b570  jmp     loc_18001B351
0x18001b575  mov     rax, rcx
0x18001b578  neg     rax
0x18001b57b  cmovs   rax, rcx
0x18001b57f  cmp     rax, 9896800h
0x18001b585  jnb     loc_18001B383
0x18001b58b  cmp     qword ptr [rbx+70h], 9896800h
0x18001b593  jnb     loc_18001B383
0x18001b599  mov     r13b, 1
0x18001b59c  jmp     loc_18001B3A8
0x18001b5a1  cmp     qword ptr [rbx+18h], 9896800h
0x18001b5a9  jnb     loc_18001B433
0x18001b5af  mov     r15b, 1
0x18001b5b2  jmp     loc_18001B458
0x18001b5b7  mov     ecx, 71h ; 'q'
0x18001b5bc  cmp     dword ptr [r8+8], 0AAAAAAAAh
0x18001b5c4  jnz     short loc_18001B604
0x18001b5c6  call    FileLogAllowEntry
0x18001b5cb  test    al, al
0x18001b5cd  jz      short loc_18001B5E9
0x18001b5cf  mov     rax, [r14]
0x18001b5d2  mov     rdx, [rax+8]
0x18001b5d6  add     rdx, 122h
0x18001b5dd  lea     rcx, aPeerSIsWin2kSe; "Peer %s is Win2K. Setting compat flags."...
0x18001b5e4  call    FileLogAdd
0x18001b5e9  mov     rax, [r14]
0x18001b5ec  mov     rcx, [rax+8]
0x18001b5f0  and     dword ptr [rcx+3Ch], 3FFFFFFFh
0x18001b5f7  mov     rax, [r14]
0x18001b5fa  mov     rcx, [rax+8]
0x18001b5fe  or      dword ptr [rcx+3Ch], 3
0x18001b602  jmp     short loc_18001B635
0x18001b604  call    FileLogAllowEntry
0x18001b609  test    al, al
0x18001b60b  jz      short loc_18001B627
0x18001b60d  mov     rax, [r14]
0x18001b610  mov     rdx, [rax+8]
0x18001b614  add     rdx, 122h
0x18001b61b  lea     rcx, aPeerSIsNotWin2; "Peer %s is not Win2K. Setting compat fl"...
0x18001b622  call    FileLogAdd
0x18001b627  mov     rax, [r14]
0x18001b62a  mov     rcx, [rax+8]
0x18001b62e  and     dword ptr [rcx+3Ch], 3FFFFFFFh
0x18001b635  mov     rax, [r14]
0x18001b638  mov     rcx, [rax+8]
0x18001b63c  mov     ebp, [rcx+3Ch]
0x18001b63f  jmp     loc_18001B1BA
0x18001b644  call    FileLogAllowEntry
0x18001b649  test    al, al
0x18001b64b  jz      short loc_18001B667
0x18001b64d  mov     rax, [r14]
0x18001b650  mov     rdx, [rax+8]
0x18001b654  add     rdx, 122h
0x18001b65b  lea     rcx, aPeerSMayBeWin2; "Peer %s may be Win2K. Will verify on ne"...
0x18001b662  call    FileLogAdd
0x18001b667  mov     rax, [r14]
0x18001b66a  mov     rcx, [rax+8]
0x18001b66e  or      dword ptr [rcx+3Ch], 40000000h
0x18001b675  mov     rax, [r14]
  ... truncated ...
```
