# ParseNtpPacketStep2(AutoPtr<NtpPeer>,NtpSimplePeer *,NtpPacket *)

- ea: `0x18005b38c`
- end: `0x18005b876`
- name: `?ParseNtpPacketStep2@@YAXV?$AutoPtr@UNtpPeer@@@@PEAUNtpSimplePeer@@PEAUNtpPacket@@@Z`
- size: `1258`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180035560`

## callees

- `0x1800164b0`
- `0x180018138`
- `0x18001d9a0`
- `0x18002d518`
- `0x18003a830`
- `0x18005b38c`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005b4d8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005b4d8`

## string_xrefs

- `0x18005b41a`: `Peer %s is Win2K. Setting compat flags.\n`
- `0x18005b454`: `Peer %s is not Win2K. Setting compat flags.\n`
- `0x18005b4f9`: `Peer %s is not Win2K. Setting compat flags.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
volatile signed __int32 *__fastcall ParseNtpPacketStep2(volatile signed __int32 **a1, __int64 a2, __int64 a3)
{
  char v6; // r12
  volatile signed __int32 *v7; // rcx
  __int64 v8; // r14
  int v9; // r14d
  volatile signed __int32 *v10; // rcx
  __int64 v11; // r8
  __int64 v12; // rax
  __int64 v13; // rbx
  __int64 ClockPeriodInFileTimeIncrements; // r8
  __int64 v15; // rbx
  unsigned __int64 v16; // rcx
  char v17; // r13
  int v18; // ecx
  int v19; // eax
  unsigned __int64 v20; // rax
  __int64 v21; // rcx
  char v22; // r15
  char v23; // r14
  unsigned __int64 v24; // rax
  char v25; // bl
  char v26; // al
  bool v27; // cl
  bool v28; // cl
  _BYTE v30[4]; // [rsp+20h] [rbp-28h] BYREF
  int v31; // [rsp+24h] [rbp-24h] BYREF
  int v32; // [rsp+28h] [rbp-20h] BYREF
  _QWORD v33[3]; // [rsp+30h] [rbp-18h] BYREF
  char v34; // [rsp+98h] [rbp+50h]
  __int64 v35; // [rsp+98h] [rbp+50h]
  char v36; // [rsp+A0h] [rbp+58h]
  unsigned __int8 v37; // [rsp+A8h] [rbp+60h] BYREF

  v6 = 0;
  v31 = 0;
  v7 = *a1;
  if ( v7 && (v8 = *((_QWORD *)v7 + 1)) != 0 )
    v9 = *(_DWORD *)(v8 + 60);
  else
    v9 = *((_DWORD *)g_pnpstate + 46);
  if ( (unsigned int)operator!=(v7, a1) )
  {
    if ( (v9 & 0x40000000) != 0 )
    {
      if ( *(_DWORD *)(v11 + 8) == -1431655766 )
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
      v10 = *a1;
      v9 = *(_DWORD *)(*((_QWORD *)*a1 + 1) + 60LL);
    }
    if ( v9 < 0 )
    {
      if ( *(_DWORD *)(*((_QWORD *)v10 + 1) + 64LL) == *(_DWORD *)(a3 + 8) )
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
      v9 = *(_DWORD *)(*((_QWORD *)*a1 + 1) + 60LL);
    }
  }
  if ( (v9 & 1) != 0 )
    *(_QWORD *)(a2 + 24) = gc_toZero;
  v33[0] = 0;
  v30[0] = 0;
  v37 = 0;
  v32 = 0;
  (*((void (__fastcall **)(__int64, _QWORD *))g_pnpstate + 2))(1, v33);
  (*((void (__fastcall **)(__int64, _BYTE *))g_pnpstate + 2))(6, v30);
  (*((void (__fastcall **)(__int64, unsigned __int8 *))g_pnpstate + 2))(7, &v37);
  (*((void (__fastcall **)(__int64, int *))g_pnpstate + 2))(8, &v32);
  (*((void (__fastcall **)(__int64, int *))g_pnpstate + 2))(2, &v31);
  v12 = *(_QWORD *)(a2 + 72);
  v13 = *(_QWORD *)(a2 + 88);
  *(_QWORD *)(a2 + 96) = *(_QWORD *)(a2 + 64) + v13 - *(_QWORD *)(a2 + 48) - v12;
  *(_QWORD *)(a2 + 104) = (*(_QWORD *)(a2 + 64) + v12 - v13 - *(_QWORD *)(a2 + 48)) / 2;
  ClockPeriodInFileTimeIncrements = (unsigned int)GetClockPeriodInFileTimeIncrements(v33);
  v15 = v13 - *(_QWORD *)(a2 + 48);
  v16 = -v15;
  if ( v15 > 0 )
    v16 = v15;
  *(_QWORD *)(a2 + 112) = v16 / 0x15180 + ClockPeriodInFileTimeIncrements;
  if ( *(_DWORD *)a2 == 5 )
  {
    v17 = 1;
    v6 = 1;
  }
  else
  {
    if ( *(_QWORD *)(a2 + 80) == *(_QWORD *)(*((_QWORD *)*a1 + 1) + 816LL) )
    {
      v17 = 0;
      if ( (unsigned __int8)FileLogAllowEntry(104) )
        FileLogAdd(L"Packet test 1 failed (we've seen this response).\n");
    }
    else
    {
      v17 = 1;
    }
    if ( *(_QWORD *)(a2 + 56) == *(_QWORD *)(*((_QWORD *)*a1 + 1) + 808LL) )
    {
      v6 = 1;
    }
    else if ( (unsigned __int8)FileLogAllowEntry(104) )
    {
      FileLogAdd(L"Packet test 2 failed (response does not match request).\n");
    }
  }
  if ( gc_toZero == *(_QWORD *)(a3 + 24) || gc_toZero == *(_QWORD *)(a3 + 32) )
  {
    v36 = 0;
    if ( (unsigned __int8)FileLogAllowEntry(104) )
      FileLogAdd(L"Packet test 3 failed (looks like a request).\n");
  }
  else
  {
    v36 = 1;
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
  if ( *(_QWORD *)(a2 + 96) + v19 < 0LL )
    goto LABEL_54;
  v20 = -*(_QWORD *)(a2 + 96);
  if ( *(__int64 *)(a2 + 96) > 0 )
    v20 = *(_QWORD *)(a2 + 96);
  if ( v20 >= 0x9896800 || *(_QWORD *)(a2 + 112) >= 0x9896800u )
  {
LABEL_54:
    v34 = 0;
    if ( (unsigned __int8)FileLogAllowEntry(104) )
      FileLogAdd(L"Packet test 4 failed (bad value for delay or dispersion).\n");
  }
  else
  {
    v34 = 1;
  }
  if ( *(_DWORD *)(a2 + 8) != 3
    && ((v9 & 2) != 0 || *(_QWORD *)(a2 + 40) <= *(_QWORD *)(a2 + 72))
    && ((v21 = *(_QWORD *)(a2 + 40), *(_QWORD *)(a2 + 72) < (unsigned __int64)(v21 + 864000000000LL))
     || v21 == 94354848000000000LL) )
  {
    v22 = 1;
  }
  else
  {
    v22 = 0;
    if ( (unsigned __int8)FileLogAllowEntry(104) )
      FileLogAdd(L"Packet test 6 failed (not syncd or bad interval since last sync).\n");
  }
  if ( (unsigned __int8)(*(_BYTE *)(a2 + 12) - 1) > 0xDu )
  {
    v23 = 0;
    if ( (unsigned __int8)FileLogAllowEntry(104) )
      FileLogAdd(L"Packet test 7 failed (bad stratum: system - %d, sample - %d).\n", v37, *(unsigned __int8 *)(a2 + 12));
  }
  else
  {
    v23 = 1;
  }
  v24 = -*(_QWORD *)(a2 + 16);
  if ( *(__int64 *)(a2 + 16) > 0 )
    v24 = *(_QWORD *)(a2 + 16);
  if ( v24 >= 0x9896800 || *(_QWORD *)(a2 + 24) >= 0x9896800u )
  {
    v25 = 0;
    if ( (unsigned __int8)FileLogAllowEntry(104) )
      FileLogAdd(L"Packet test 8 failed (bad value for root delay or root dispersion).\n");
  }
  else
  {
    v25 = 1;
  }
  v26 = v34;
  v27 = v17 && v6 && v36 && v34;
  *(_BYTE *)(a2 + 169) = v27;
  v28 = v22 && v23 && v25;
  *(_BYTE *)(a2 + 168) = v28;
  LOBYTE(v35) = v17;
  BYTE1(v35) = v6;
  BYTE2(v35) = v36;
  BYTE3(v35) = v26;
  BYTE4(v35) = 1;
  BYTE5(v35) = v22;
  BYTE6(v35) = v23;
  HIBYTE(v35) = v25;
  *(_QWORD *)(a2 + 160) = v35;
  return AutoPtr<NtpPeer>::~AutoPtr<NtpPeer>(a1);
}

```

## disassembly

```asm
0x18005b38c  mov     [rsp-40h+arg_0], rcx
0x18005b391  push    rbp
0x18005b392  push    rbx
0x18005b393  push    rsi
0x18005b394  push    rdi
0x18005b395  push    r12
0x18005b397  push    r13
0x18005b399  push    r14
0x18005b39b  push    r15
0x18005b39d  mov     rbp, rsp
0x18005b3a0  sub     rsp, 48h
0x18005b3a4  mov     r15, r8
0x18005b3a7  mov     rdi, rdx
0x18005b3aa  mov     rsi, rcx
0x18005b3ad  xor     r12d, r12d
0x18005b3b0  mov     [rbp+var_24], r12d
0x18005b3b4  mov     rcx, [rcx]
0x18005b3b7  test    rcx, rcx
0x18005b3ba  jz      short loc_18005B3CB
0x18005b3bc  mov     r14, [rcx+8]
0x18005b3c0  test    r14, r14
0x18005b3c3  jz      short loc_18005B3CB
0x18005b3c5  mov     r14d, [r14+3Ch]
0x18005b3c9  jmp     short loc_18005B3D9
0x18005b3cb  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x18005b3d2  mov     r14d, [rax+0B8h]
0x18005b3d9  mov     rdx, rsi
0x18005b3dc  call    ??9@YAHPEBXAEBV?$AutoPtr@UNtpPeer@@@@@Z; operator!=(void const *,AutoPtr<NtpPeer> const &)
0x18005b3e1  test    eax, eax
0x18005b3e3  jz      loc_18005B51E
0x18005b3e9  mov     ebx, 71h ; 'q'
0x18005b3ee  mov     r13d, 122h
0x18005b3f4  bt      r14d, 1Eh
0x18005b3f9  jnb     short loc_18005B479
0x18005b3fb  mov     ecx, ebx
0x18005b3fd  cmp     dword ptr [r8+8], 0AAAAAAAAh
0x18005b405  jnz     short loc_18005B441
0x18005b407  call    FileLogAllowEntry
0x18005b40c  test    al, al
0x18005b40e  jz      short loc_18005B426
0x18005b410  mov     rax, [rsi]
0x18005b413  mov     rdx, [rax+8]
0x18005b417  add     rdx, r13
0x18005b41a  lea     rcx, aPeerSIsWin2kSe; "Peer %s is Win2K. Setting compat flags."...
0x18005b421  call    FileLogAdd
0x18005b426  mov     rax, [rsi]
0x18005b429  mov     rcx, [rax+8]
0x18005b42d  and     dword ptr [rcx+3Ch], 3FFFFFFFh
0x18005b434  mov     rax, [rsi]
0x18005b437  mov     rcx, [rax+8]
0x18005b43b  or      dword ptr [rcx+3Ch], 3
0x18005b43f  jmp     short loc_18005B46E
0x18005b441  call    FileLogAllowEntry
0x18005b446  test    al, al
0x18005b448  jz      short loc_18005B460
0x18005b44a  mov     rax, [rsi]
0x18005b44d  mov     rdx, [rax+8]
0x18005b451  add     rdx, r13
0x18005b454  lea     rcx, aPeerSIsNotWin2; "Peer %s is not Win2K. Setting compat fl"...
0x18005b45b  call    FileLogAdd
0x18005b460  mov     rax, [rsi]
0x18005b463  mov     rcx, [rax+8]
0x18005b467  and     dword ptr [rcx+3Ch], 3FFFFFFFh
0x18005b46e  mov     rcx, [rsi]
0x18005b471  mov     rax, [rcx+8]
0x18005b475  mov     r14d, [rax+3Ch]
0x18005b479  test    r14d, r14d
0x18005b47c  jns     loc_18005B51E
0x18005b482  mov     rdx, [rcx+8]
0x18005b486  mov     eax, [r15+8]
0x18005b48a  mov     ecx, ebx
0x18005b48c  cmp     [rdx+40h], eax
0x18005b48f  jnz     short loc_18005B4E6
0x18005b491  call    FileLogAllowEntry
0x18005b496  test    al, al
0x18005b498  jz      short loc_18005B4B0
0x18005b49a  mov     rax, [rsi]
0x18005b49d  mov     rdx, [rax+8]
0x18005b4a1  add     rdx, r13
0x18005b4a4  lea     rcx, aPeerSMayBeWin2; "Peer %s may be Win2K. Will verify on ne"...
0x18005b4ab  call    FileLogAdd
0x18005b4b0  mov     rax, [rsi]
0x18005b4b3  mov     rcx, [rax+8]
0x18005b4b7  bts     dword ptr [rcx+3Ch], 1Eh
0x18005b4bc  mov     rax, [rsi]
0x18005b4bf  mov     rcx, [rax+8]
0x18005b4c3  mov     [rcx+118h], r12
0x18005b4ca  mov     rcx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x18005b4d1  mov     rcx, [rcx+1D0h]; hEvent
0x18005b4d8  call    cs:__imp_SetEvent
0x18005b4df  nop     dword ptr [rax+rax+00h]
0x18005b4e4  jmp     short loc_18005B513
0x18005b4e6  call    FileLogAllowEntry
0x18005b4eb  test    al, al
0x18005b4ed  jz      short loc_18005B505
0x18005b4ef  mov     rax, [rsi]
0x18005b4f2  mov     rdx, [rax+8]
0x18005b4f6  add     rdx, r13
0x18005b4f9  lea     rcx, aPeerSIsNotWin2; "Peer %s is not Win2K. Setting compat fl"...
0x18005b500  call    FileLogAdd
0x18005b505  mov     rax, [rsi]
0x18005b508  mov     rcx, [rax+8]
0x18005b50c  and     dword ptr [rcx+3Ch], 3FFFFFFFh
0x18005b513  mov     rax, [rsi]
0x18005b516  mov     rcx, [rax+8]
0x18005b51a  mov     r14d, [rcx+3Ch]
0x18005b51e  test    r14b, 1
0x18005b522  jz      short loc_18005B52F
0x18005b524  mov     rax, cs:?gc_toZero@@3UNtTimeOffset@@B; NtTimeOffset const gc_toZero
0x18005b52b  mov     [rdi+18h], rax
0x18005b52f  mov     [rbp+var_18], r12
0x18005b533  mov     [rbp+var_28], r12b
0x18005b537  mov     [rbp+arg_18], r12b
0x18005b53b  mov     [rbp+var_20], r12d
0x18005b53f  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x18005b546  lea     rdx, [rbp+var_18]
0x18005b54a  mov     ecx, 1
0x18005b54f  mov     rax, [rax+10h]
0x18005b553  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b558  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x18005b55f  lea     rdx, [rbp+var_28]
0x18005b563  mov     ecx, 6
0x18005b568  mov     rax, [rax+10h]
0x18005b56c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b571  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x18005b578  lea     rdx, [rbp+arg_18]
0x18005b57c  mov     ecx, 7
0x18005b581  mov     rax, [rax+10h]
0x18005b585  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b58a  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x18005b591  lea     rdx, [rbp+var_20]
0x18005b595  mov     ecx, 8
0x18005b59a  mov     rax, [rax+10h]
0x18005b59e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b5a3  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x18005b5aa  lea     rdx, [rbp+var_24]
0x18005b5ae  mov     r13d, 2
0x18005b5b4  mov     ecx, r13d
0x18005b5b7  mov     rax, [rax+10h]
0x18005b5bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b5c0  mov     rax, [rdi+48h]
0x18005b5c4  mov     rbx, [rdi+58h]
0x18005b5c8  mov     rcx, rbx
0x18005b5cb  sub     rcx, [rdi+30h]
0x18005b5cf  sub     rcx, rax
0x18005b5d2  add     rcx, [rdi+40h]
0x18005b5d6  mov     [rdi+60h], rcx
0x18005b5da  sub     rax, rbx
0x18005b5dd  sub     rax, [rdi+30h]
0x18005b5e1  add     rax, [rdi+40h]
0x18005b5e5  cqo
0x18005b5e7  idiv    r13
0x18005b5ea  mov     [rdi+68h], rax
0x18005b5ee  lea     rcx, [rbp+var_18]
0x18005b5f2  call    GetClockPeriodInFileTimeIncrements
0x18005b5f7  mov     r8d, eax
0x18005b5fa  sub     rbx, [rdi+30h]
0x18005b5fe  mov     rcx, rbx
0x18005b601  neg     rcx
0x18005b604  cmovs   rcx, rbx
0x18005b608  mov     rax, 0C22E450672894AB7h
0x18005b612  mul     rcx
0x18005b615  shr     rdx, 10h
0x18005b619  add     r8, rdx
0x18005b61c  mov     [rdi+70h], r8
0x18005b620  lea     ebx, [r13+66h]
0x18005b624  cmp     dword ptr [rdi], 5
0x18005b627  jz      short loc_18005B68E
0x18005b629  mov     rax, [rsi]
0x18005b62c  mov     rcx, [rax+8]
0x18005b630  mov     rax, [rcx+330h]
0x18005b637  cmp     [rdi+50h], rax
0x18005b63b  jz      short loc_18005B642
0x18005b63d  mov     r13b, 1
0x18005b640  jmp     short loc_18005B65C
0x18005b642  mov     r13b, r12b
0x18005b645  mov     ecx, ebx
0x18005b647  call    FileLogAllowEntry
0x18005b64c  test    al, al
0x18005b64e  jz      short loc_18005B65C
0x18005b650  lea     rcx, aPacketTest1Fai; "Packet test 1 failed (we've seen this r"...
0x18005b657  call    FileLogAdd
0x18005b65c  mov     rax, [rsi]
0x18005b65f  mov     rcx, [rax+8]
0x18005b663  mov     rax, [rcx+328h]
0x18005b66a  cmp     [rdi+38h], rax
0x18005b66e  jnz     short loc_18005B675
0x18005b670  mov     r12b, 1
0x18005b673  jmp     short loc_18005B694
0x18005b675  mov     ecx, ebx
0x18005b677  call    FileLogAllowEntry
0x18005b67c  test    al, al
0x18005b67e  jz      short loc_18005B694
0x18005b680  lea     rcx, aPacketTest2Fai; "Packet test 2 failed (response does not"...
0x18005b687  call    FileLogAdd
0x18005b68c  jmp     short loc_18005B694
0x18005b68e  mov     r13b, 1
0x18005b691  mov     r12b, r13b
0x18005b694  mov     rax, cs:?gc_toZero@@3UNtTimeOffset@@B; NtTimeOffset const gc_toZero
0x18005b69b  cmp     rax, [r15+18h]
0x18005b69f  jz      short loc_18005B6AD
0x18005b6a1  cmp     rax, [r15+20h]
0x18005b6a5  jz      short loc_18005B6AD
0x18005b6a7  mov     [rbp+arg_10], 1
0x18005b6ab  jmp     short loc_18005B6C8
0x18005b6ad  mov     [rbp+arg_10], 0
0x18005b6b1  mov     ecx, ebx
0x18005b6b3  call    FileLogAllowEntry
0x18005b6b8  test    al, al
0x18005b6ba  jz      short loc_18005B6C8
0x18005b6bc  lea     rcx, aPacketTest3Fai; "Packet test 3 failed (looks like a requ"...
0x18005b6c3  call    FileLogAdd
0x18005b6c8  movsx   eax, byte ptr [rdi+0Eh]
0x18005b6cc  mov     ecx, [rbp+var_24]
0x18005b6cf  cmp     ecx, eax
0x18005b6d1  jge     short loc_18005B6D8
0x18005b6d3  mov     ecx, eax
0x18005b6d5  mov     [rbp+var_24], eax
0x18005b6d8  mov     eax, 1312D00h
0x18005b6dd  test    ecx, ecx
0x18005b6df  jns     short loc_18005B6E7
0x18005b6e1  neg     ecx
0x18005b6e3  sar     eax, cl
0x18005b6e5  jmp     short loc_18005B6E9
0x18005b6e7  shl     eax, cl
0x18005b6e9  cdqe
0x18005b6eb  mov     ecx, 9896800h
0x18005b6f0  add     rax, [rdi+60h]
0x18005b6f4  js      short loc_18005B713
0x18005b6f6  mov     rax, [rdi+60h]
0x18005b6fa  neg     rax
0x18005b6fd  cmovs   rax, [rdi+60h]
0x18005b702  cmp     rax, rcx
0x18005b705  jnb     short loc_18005B713
0x18005b707  cmp     [rdi+70h], rcx
0x18005b70b  jnb     short loc_18005B713
0x18005b70d  mov     byte ptr [rbp+arg_8], 1
0x18005b711  jmp     short loc_18005B72E
0x18005b713  mov     byte ptr [rbp+arg_8], 0
0x18005b717  mov     ecx, ebx
0x18005b719  call    FileLogAllowEntry
0x18005b71e  test    al, al
0x18005b720  jz      short loc_18005B72E
0x18005b722  lea     rcx, aPacketTest4Fai; "Packet test 4 failed (bad value for del"...
0x18005b729  call    FileLogAdd
0x18005b72e  cmp     dword ptr [rdi+8], 3
0x18005b732  jz      short loc_18005B76F
0x18005b734  test    r14b, 2
0x18005b738  jnz     short loc_18005B744
0x18005b73a  mov     rax, [rdi+48h]
0x18005b73e  cmp     [rdi+28h], rax
0x18005b742  ja      short loc_18005B76F
0x18005b744  mov     rcx, [rdi+28h]
0x18005b748  mov     rax, 0C92A69C000h
0x18005b752  add     rax, rcx
0x18005b755  cmp     [rdi+48h], rax
0x18005b759  jb      short loc_18005B76A
0x18005b75b  mov     rax, 14F373BFDE04000h
0x18005b765  cmp     rcx, rax
0x18005b768  jnz     short loc_18005B76F
0x18005b76a  mov     r15b, 1
0x18005b76d  jmp     short loc_18005B789
0x18005b76f  xor     r15b, r15b
0x18005b772  mov     ecx, ebx
0x18005b774  call    FileLogAllowEntry
0x18005b779  test    al, al
0x18005b77b  jz      short loc_18005B789
0x18005b77d  lea     rcx, aPacketTest6Fai; "Packet test 6 failed (not syncd or bad "...
0x18005b784  call    FileLogAdd
0x18005b789  mov     al, [rdi+0Ch]
0x18005b78c  dec     al
0x18005b78e  cmp     al, 0Dh
0x18005b790  ja      short loc_18005B797
0x18005b792  mov     r14b, 1
0x18005b795  jmp     short loc_18005B7BA
0x18005b797  xor     r14b, r14b
0x18005b79a  mov     ecx, ebx
0x18005b79c  call    FileLogAllowEntry
0x18005b7a1  test    al, al
0x18005b7a3  jz      short loc_18005B7BA
0x18005b7a5  movzx   r8d, byte ptr [rdi+0Ch]
0x18005b7aa  movzx   edx, [rbp+arg_18]
0x18005b7ae  lea     rcx, aPacketTest7Fai; "Packet test 7 failed (bad stratum: syst"...
0x18005b7b5  call    FileLogAdd
0x18005b7ba  mov     rax, [rdi+10h]
0x18005b7be  neg     rax
0x18005b7c1  cmovs   rax, [rdi+10h]
0x18005b7c6  mov     ecx, 9896800h
0x18005b7cb  cmp     rax, rcx
0x18005b7ce  jnb     short loc_18005B7DA
0x18005b7d0  cmp     [rdi+18h], rcx
0x18005b7d4  jnb     short loc_18005B7DA
0x18005b7d6  mov     bl, 1
0x18005b7d8  jmp     short loc_18005B7F6
0x18005b7da  xor     bl, bl
0x18005b7dc  mov     ecx, 68h ; 'h'
0x18005b7e1  call    FileLogAllowEntry
0x18005b7e6  test    al, al
0x18005b7e8  jz      short loc_18005B7F6
0x18005b7ea  lea     rcx, aPacketTest8Fai; "Packet test 8 failed (bad value for roo"...
  ... truncated ...
```
