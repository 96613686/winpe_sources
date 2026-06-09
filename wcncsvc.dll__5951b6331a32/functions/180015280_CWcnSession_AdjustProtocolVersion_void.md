# CWcnSession::AdjustProtocolVersion(void)

- ea: `0x180015280`
- end: `0x1800156bf`
- name: `?AdjustProtocolVersion@CWcnSession@@AEAAJXZ`
- size: `1087`
- prototype: `_BOOL8 __fastcall(CWcnSession *this)`
- caller_count: `2`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800157bc`
- `0x180017054`

## callees

- `0x180003044`
- `0x180004f78`
- `0x180004fb8`
- `0x180005014`
- `0x18000c864`
- `0x180015280`
- `0x180019980`
- `0x18001e490`
- `0x180053004`
- `0x180056de6`
- `0x180056e30`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015388`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015388`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015654`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015654`

## pseudocode

```c
_BOOL8 __fastcall CWcnSession::AdjustProtocolVersion(CWcnSession *this)
{
  BOOL v2; // edi
  _BYTE *v3; // r10
  const char *Indent; // rax
  __int64 v5; // r10
  __int64 v6; // rbx
  const char *v7; // rax
  __int64 v8; // r10
  const char *v9; // rax
  __int64 v10; // r10
  __int64 v11; // r8
  char v12; // bl
  int v13; // eax
  __int64 v14; // rbx
  int v15; // eax
  _BYTE *v16; // r10
  unsigned int v17; // eax
  __int64 v18; // r10
  __int64 v19; // r14
  const char *v20; // rax
  __int64 v21; // r10
  _QWORD *v22; // r15
  __int16 v23; // ax
  __int64 v24; // rbx
  unsigned int v25; // eax
  __int64 v26; // r10
  void (__fastcall ***v27)(_QWORD, __int64); // rcx
  int v28; // eax
  unsigned int v29; // eax
  __int64 v30; // r10
  struct _GUID Buf2; // [rsp+30h] [rbp-29h] BYREF
  __int128 Buf1; // [rsp+40h] [rbp-19h] BYREF
  _QWORD v34[2]; // [rsp+50h] [rbp-9h] BYREF
  int v35; // [rsp+60h] [rbp+7h]
  __int64 v36; // [rsp+68h] [rbp+Fh]
  char v37; // [rsp+74h] [rbp+1Bh]
  __int128 v38; // [rsp+78h] [rbp+1Fh]

  v2 = 1;
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v5 + 16), 177, WPP_a137d119f5dc35a130051116e3170526_Traceguids, Indent);
    v3 = WPP_GLOBAL_Control;
  }
  v6 = *((_QWORD *)this + 4);
  if ( v3 != (_BYTE *)&WPP_GLOBAL_Control )
  {
    if ( v3[25] >= 6u )
    {
      v7 = GetIndent(1);
      WPP_SF_s(*(_QWORD *)(v8 + 16), 16, WPP_805ccd1b393d3e4b99a4efc8134fe3a0_Traceguids, v7);
      v3 = WPP_GLOBAL_Control;
    }
    if ( v3 != (_BYTE *)&WPP_GLOBAL_Control && v3[25] >= 6u )
    {
      v9 = GetIndent(-1);
      WPP_SF_s(*(_QWORD *)(v10 + 16), 17, WPP_805ccd1b393d3e4b99a4efc8134fe3a0_Traceguids, v9);
    }
  }
  if ( !*(_DWORD *)(v6 + 132)
    || *(_DWORD *)(v6 + 128) != (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(v6 + 120) + 40LL))(*(_QWORD *)(v6 + 120)) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(*((_QWORD *)this + 4) + 16LL));
    *(_QWORD *)(*((_QWORD *)this + 4) + 112LL) = 0;
    if ( *((_DWORD *)this + 68) )
      goto LABEL_32;
    v35 = 8;
    v36 = 0;
    v37 = 0;
    v38 = 0;
    v34[0] = 0;
    Buf2 = 0;
    Buf1 = 0;
    v11 = *((_QWORD *)this + 4);
    v12 = *(_BYTE *)(v11 + 233);
    if ( v12 )
      Buf2 = *(struct _GUID *)(v11 + 152);
    v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *, __int64, _QWORD, _QWORD))(**(_QWORD **)(v11 + 120) + 16LL))(
            *(_QWORD *)(v11 + 120),
            v34,
            v11,
            *((_QWORD *)this + 36),
            0);
    v2 = v13;
    if ( v13 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          178,
          WPP_a137d119f5dc35a130051116e3170526_Traceguids,
          (unsigned int)v13);
      CWcnMessage::Clear((CWcnMessage *)v34);
LABEL_47:
      *(_QWORD *)(*((_QWORD *)this + 4) + 112LL) = this;
      LeaveCriticalSection((LPCRITICAL_SECTION)(*((_QWORD *)this + 4) + 16LL));
      goto LABEL_48;
    }
    if ( v12 )
    {
      v14 = *((_QWORD *)this + 4);
      Buf1 = *(_OWORD *)(v14 + 152);
      if ( memcmp_0(&Buf1, &Buf2, 0x10u) )
      {
        v15 = CWcnIdentity::SetUuid((CWcnIdentity *)(v14 + 136), &Buf2);
        if ( v15 >= 0 )
          goto LABEL_27;
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        {
          if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
          {
LABEL_28:
            if ( v16 != (_BYTE *)&WPP_GLOBAL_Control && v16[25] >= 3u )
            {
              v17 = (unsigned int)GetIndent(0);
              WPP_SF_s_guid__guid_(
                *(_QWORD *)(v18 + 16),
                180,
                (unsigned int)WPP_a137d119f5dc35a130051116e3170526_Traceguids,
                v17,
                (__int64)&Buf2,
                (__int64)&Buf1);
            }
            goto LABEL_31;
          }
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            179,
            WPP_a137d119f5dc35a130051116e3170526_Traceguids,
            (unsigned int)v15);
LABEL_27:
          v16 = WPP_GLOBAL_Control;
          goto LABEL_28;
        }
      }
    }
LABEL_31:
    CWcnMessage::Clear((CWcnMessage *)v34);
    v2 = 1;
LABEL_32:
    v19 = *((_QWORD *)this + 4);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      v20 = GetIndent(1);
      WPP_SF_s(*(_QWORD *)(v21 + 16), 18, WPP_805ccd1b393d3e4b99a4efc8134fe3a0_Traceguids, v20);
    }
    v22 = (_QWORD *)(v19 + 120);
    if ( *(_DWORD *)(v19 + 128) != (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(v19 + 120) + 40LL))(*(_QWORD *)(v19 + 120)) )
    {
      v23 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v22 + 32LL))(*v22);
      v24 = *v22;
      CWcnService::GetProtocol(g_pWcnService, *(_DWORD *)(v19 + 128) | v23 & 0xFF00u, v19 + 120);
      v2 = v24 == *v22;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      v25 = (unsigned int)GetIndent(-1);
      WPP_SF_sd(*(_QWORD *)(v26 + 16), 19, (unsigned int)WPP_805ccd1b393d3e4b99a4efc8134fe3a0_Traceguids, v25, v2);
    }
    if ( !v2 )
    {
      v27 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 27);
      if ( v27 )
        (**v27)(v27, 1);
      *((_QWORD *)this + 27) = 0;
      v28 = (*(__int64 (__fastcall **)(_QWORD, CWcnSession *, char *))(**(_QWORD **)(*((_QWORD *)this + 4) + 120LL) + 8LL))(
              *(_QWORD *)(*((_QWORD *)this + 4) + 120LL),
              this,
              (char *)this + 216);
      v2 = v28;
      if ( v28 < 0 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          182,
          WPP_a137d119f5dc35a130051116e3170526_Traceguids,
          (unsigned int)v28);
    }
    goto LABEL_47;
  }
  v2 = 0;
LABEL_48:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (v2 < 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u) )
  {
    v29 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v30 + 16), 183, (unsigned int)WPP_a137d119f5dc35a130051116e3170526_Traceguids, v29, v2);
  }
  return v2;
}

```

## disassembly

```asm
0x180015280  mov     [rsp-8+arg_8], rbx
0x180015285  mov     [rsp-8+arg_10], rsi
0x18001528a  push    rbp
0x18001528b  push    rdi
0x18001528c  push    r13
0x18001528e  push    r14
0x180015290  push    r15
0x180015292  lea     rbp, [rsp-37h]
0x180015297  sub     rsp, 90h
0x18001529e  mov     rax, cs:__security_cookie
0x1800152a5  xor     rax, rsp
0x1800152a8  mov     [rbp+57h+var_28], rax
0x1800152ac  mov     rsi, rcx
0x1800152af  lea     r13, WPP_GLOBAL_Control
0x1800152b6  mov     edi, 1
0x1800152bb  lea     r14, WPP_a137d119f5dc35a130051116e3170526_Traceguids
0x1800152c2  mov     r10, cs:WPP_GLOBAL_Control
0x1800152c9  cmp     r10, r13
0x1800152cc  jz      short loc_1800152F7
0x1800152ce  cmp     byte ptr [r10+19h], 6
0x1800152d3  jb      short loc_1800152F7
0x1800152d5  mov     ecx, edi; int
0x1800152d7  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800152dc  mov     edx, 0B1h
0x1800152e1  mov     r9, rax
0x1800152e4  mov     r8, r14
0x1800152e7  mov     rcx, [r10+10h]
0x1800152eb  call    WPP_SF_s
0x1800152f0  mov     r10, cs:WPP_GLOBAL_Control
0x1800152f7  mov     rbx, [rsi+20h]
0x1800152fb  lea     r15, WPP_805ccd1b393d3e4b99a4efc8134fe3a0_Traceguids
0x180015302  cmp     r10, r13
0x180015305  jz      short loc_180015358
0x180015307  cmp     byte ptr [r10+19h], 6
0x18001530c  jb      short loc_180015330
0x18001530e  mov     ecx, edi; int
0x180015310  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180015315  mov     edx, 10h
0x18001531a  mov     r9, rax
0x18001531d  mov     r8, r15
0x180015320  mov     rcx, [r10+10h]
0x180015324  call    WPP_SF_s
0x180015329  mov     r10, cs:WPP_GLOBAL_Control
0x180015330  cmp     r10, r13
0x180015333  jz      short loc_180015358
0x180015335  cmp     byte ptr [r10+19h], 6
0x18001533a  jb      short loc_180015358
0x18001533c  or      ecx, 0FFFFFFFFh; int
0x18001533f  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180015344  mov     edx, 11h
0x180015349  mov     r9, rax
0x18001534c  mov     r8, r15
0x18001534f  mov     rcx, [r10+10h]
0x180015353  call    WPP_SF_s
0x180015358  cmp     dword ptr [rbx+84h], 0
0x18001535f  jz      short loc_180015380
0x180015361  mov     rcx, [rbx+78h]
0x180015365  mov     rax, [rcx]
0x180015368  mov     rax, [rax+28h]
0x18001536c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015371  cmp     [rbx+80h], eax
0x180015377  jnz     short loc_180015380
0x180015379  xor     edi, edi
0x18001537b  jmp     loc_18001565A
0x180015380  mov     rcx, [rsi+20h]
0x180015384  add     rcx, 10h; lpCriticalSection
0x180015388  call    cs:__imp_EnterCriticalSection
0x18001538e  mov     rax, [rsi+20h]
0x180015392  mov     qword ptr [rax+70h], 0
0x18001539a  cmp     dword ptr [rsi+110h], 0
0x1800153a1  jnz     loc_180015509
0x1800153a7  mov     [rbp+57h+var_50], 8
0x1800153ae  mov     [rbp+57h+var_48], 0
0x1800153b6  mov     [rbp+57h+var_3C], 0
0x1800153ba  xorps   xmm0, xmm0
0x1800153bd  movdqu  [rbp+57h+var_38], xmm0
0x1800153c2  mov     [rbp+57h+var_60], 0
0x1800153ca  movups  [rbp+57h+Buf2], xmm0
0x1800153ce  xorps   xmm1, xmm1
0x1800153d1  movups  [rbp+57h+Buf1], xmm1
0x1800153d5  mov     r8, [rsi+20h]
0x1800153d9  mov     bl, [r8+0E9h]
0x1800153e0  test    bl, bl
0x1800153e2  jz      short loc_1800153F1
0x1800153e4  movups  xmm0, xmmword ptr [r8+98h]
0x1800153ec  movdqu  [rbp+57h+Buf2], xmm0
0x1800153f1  mov     rcx, [r8+78h]
0x1800153f5  mov     rax, [rcx]
0x1800153f8  mov     [rsp+0B0h+var_90], 0
0x180015401  mov     r9, [rsi+120h]
0x180015408  lea     rdx, [rbp+57h+var_60]
0x18001540c  mov     rax, [rax+10h]
0x180015410  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015415  mov     edi, eax
0x180015417  test    eax, eax
0x180015419  jns     short loc_180015450
0x18001541b  mov     rcx, cs:WPP_GLOBAL_Control
0x180015422  cmp     rcx, r13
0x180015425  jz      short loc_180015442
0x180015427  cmp     byte ptr [rcx+19h], 2
0x18001542b  jb      short loc_180015442
0x18001542d  mov     edx, 0B2h
0x180015432  mov     r9d, eax
0x180015435  mov     r8, r14
0x180015438  mov     rcx, [rcx+10h]
0x18001543c  call    WPP_SF_d
0x180015441  nop
0x180015442  lea     rcx, [rbp+57h+var_60]; this
0x180015446  call    ?Clear@CWcnMessage@@QEAAXXZ; CWcnMessage::Clear(void)
0x18001544b  jmp     loc_180015644
0x180015450  test    bl, bl
0x180015452  jz      loc_1800154FB
0x180015458  mov     rbx, [rsi+20h]
0x18001545c  movups  xmm0, xmmword ptr [rbx+98h]
0x180015463  movdqu  [rbp+57h+Buf1], xmm0
0x180015468  mov     r8d, 10h; Size
0x18001546e  lea     rdx, [rbp+57h+Buf2]; Buf2
0x180015472  lea     rcx, [rbp+57h+Buf1]; Buf1
0x180015476  call    memcmp_0
0x18001547b  test    eax, eax
0x18001547d  jz      short loc_1800154FB
0x18001547f  lea     rcx, [rbx+88h]; this
0x180015486  lea     rdx, [rbp+57h+Buf2]; struct _GUID *
0x18001548a  call    ?SetUuid@CWcnIdentity@@QEAAJPEBU_GUID@@@Z; CWcnIdentity::SetUuid(_GUID const *)
0x18001548f  test    eax, eax
0x180015491  jns     short loc_1800154BA
0x180015493  mov     r10, cs:WPP_GLOBAL_Control
0x18001549a  cmp     r10, r13
0x18001549d  jz      short loc_1800154FB
0x18001549f  cmp     byte ptr [r10+19h], 3
0x1800154a4  jb      short loc_1800154C1
0x1800154a6  mov     edx, 0B3h
0x1800154ab  mov     r9d, eax
0x1800154ae  mov     r8, r14
0x1800154b1  mov     rcx, [r10+10h]
0x1800154b5  call    WPP_SF_d
0x1800154ba  mov     r10, cs:WPP_GLOBAL_Control
0x1800154c1  cmp     r10, r13
0x1800154c4  jz      short loc_1800154FB
0x1800154c6  cmp     byte ptr [r10+19h], 3
0x1800154cb  jb      short loc_1800154FB
0x1800154cd  xor     ecx, ecx; int
0x1800154cf  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800154d4  mov     edx, 0B4h
0x1800154d9  lea     rcx, [rbp+57h+Buf1]
0x1800154dd  mov     [rsp+0B0h+var_88], rcx
0x1800154e2  lea     rcx, [rbp+57h+Buf2]
0x1800154e6  mov     [rsp+0B0h+var_90], rcx
0x1800154eb  mov     r9, rax
0x1800154ee  mov     r8, r14
0x1800154f1  mov     rcx, [r10+10h]
0x1800154f5  call    WPP_SF_s_guid__guid_
0x1800154fa  nop
0x1800154fb  lea     rcx, [rbp+57h+var_60]; this
0x1800154ff  call    ?Clear@CWcnMessage@@QEAAXXZ; CWcnMessage::Clear(void)
0x180015504  mov     edi, 1
0x180015509  mov     r14, [rsi+20h]
0x18001550d  mov     r10, cs:WPP_GLOBAL_Control
0x180015514  cmp     r10, r13
0x180015517  jz      short loc_18001553B
0x180015519  cmp     byte ptr [r10+19h], 6
0x18001551e  jb      short loc_18001553B
0x180015520  mov     ecx, edi; int
0x180015522  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180015527  mov     edx, 12h
0x18001552c  mov     r9, rax
0x18001552f  mov     r8, r15
0x180015532  mov     rcx, [r10+10h]
0x180015536  call    WPP_SF_s
0x18001553b  lea     r15, [r14+78h]
0x18001553f  mov     rcx, [r15]
0x180015542  mov     rax, [rcx]
0x180015545  mov     rax, [rax+28h]
0x180015549  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001554e  cmp     [r14+80h], eax
0x180015555  jnz     short loc_18001555F
0x180015557  mov     r14d, 1
0x18001555d  jmp     short loc_18001559B
0x18001555f  xor     edi, edi
0x180015561  mov     rcx, [r15]
0x180015564  mov     rax, [rcx]
0x180015567  mov     rax, [rax+20h]
0x18001556b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015570  and     eax, 0FF00h
0x180015575  mov     rbx, [r15]
0x180015578  or      eax, [r14+80h]
0x18001557f  mov     r8, r15
0x180015582  mov     edx, eax
0x180015584  mov     rcx, cs:?g_pWcnService@@3PEAVCWcnService@@EA; CWcnService * g_pWcnService
0x18001558b  call    ?GetProtocol@CWcnService@@QEAAJW4tagWCN_PROTOCOL_VERSION@@PEAPEAVIWcnProtocol@@@Z; CWcnService::GetProtocol(tagWCN_PROTOCOL_VERSION,IWcnProtocol * *)
0x180015590  cmp     rbx, [r15]
0x180015593  lea     r14d, [rdi+1]
0x180015597  cmovz   edi, r14d
0x18001559b  mov     r10, cs:WPP_GLOBAL_Control
0x1800155a2  cmp     r10, r13
0x1800155a5  jz      short loc_1800155D2
0x1800155a7  cmp     byte ptr [r10+19h], 6
0x1800155ac  jb      short loc_1800155D2
0x1800155ae  or      ecx, 0FFFFFFFFh; int
0x1800155b1  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800155b6  mov     edx, 13h
0x1800155bb  mov     dword ptr [rsp+0B0h+var_90], edi
0x1800155bf  mov     r9, rax
0x1800155c2  lea     r8, WPP_805ccd1b393d3e4b99a4efc8134fe3a0_Traceguids
0x1800155c9  mov     rcx, [r10+10h]
0x1800155cd  call    WPP_SF_sd
0x1800155d2  test    edi, edi
0x1800155d4  jnz     short loc_180015644
0x1800155d6  lea     rbx, [rsi+0D8h]
0x1800155dd  mov     rcx, [rbx]
0x1800155e0  test    rcx, rcx
0x1800155e3  jz      short loc_1800155F3
0x1800155e5  mov     rax, [rcx]
0x1800155e8  mov     edx, r14d
0x1800155eb  mov     rax, [rax]
0x1800155ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800155f3  mov     qword ptr [rbx], 0
0x1800155fa  mov     rax, [rsi+20h]
0x1800155fe  mov     rcx, [rax+78h]
0x180015602  mov     rax, [rcx]
0x180015605  mov     r8, rbx
0x180015608  mov     rdx, rsi
0x18001560b  mov     rax, [rax+8]
0x18001560f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015614  mov     edi, eax
0x180015616  test    eax, eax
0x180015618  jns     short loc_180015644
0x18001561a  mov     rcx, cs:WPP_GLOBAL_Control
0x180015621  cmp     rcx, r13
0x180015624  jz      short loc_180015644
0x180015626  cmp     byte ptr [rcx+19h], 2
0x18001562a  jb      short loc_180015644
0x18001562c  mov     edx, 0B6h
0x180015631  mov     r9d, eax
0x180015634  lea     r8, WPP_a137d119f5dc35a130051116e3170526_Traceguids
0x18001563b  mov     rcx, [rcx+10h]
0x18001563f  call    WPP_SF_d
0x180015644  mov     rax, [rsi+20h]
0x180015648  mov     [rax+70h], rsi
0x18001564c  mov     rcx, [rsi+20h]
0x180015650  add     rcx, 10h; lpCriticalSection
0x180015654  call    cs:__imp_LeaveCriticalSection
0x18001565a  mov     r10, cs:WPP_GLOBAL_Control
0x180015661  cmp     r10, r13
0x180015664  jz      short loc_180015695
0x180015666  test    edi, edi
0x180015668  js      short loc_180015671
0x18001566a  cmp     byte ptr [r10+19h], 6
0x18001566f  jb      short loc_180015695
0x180015671  or      ecx, 0FFFFFFFFh; int
0x180015674  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180015679  mov     edx, 0B7h
0x18001567e  mov     dword ptr [rsp+0B0h+var_90], edi
0x180015682  mov     r9, rax
0x180015685  lea     r8, WPP_a137d119f5dc35a130051116e3170526_Traceguids
0x18001568c  mov     rcx, [r10+10h]
0x180015690  call    WPP_SF_sd
0x180015695  mov     eax, edi
0x180015697  mov     rcx, [rbp+57h+var_28]
0x18001569b  xor     rcx, rsp; StackCookie
0x18001569e  call    __security_check_cookie
0x1800156a3  lea     r11, [rsp+0B0h+var_20]
0x1800156ab  mov     rbx, [r11+38h]
0x1800156af  mov     rsi, [r11+40h]
0x1800156b3  mov     rsp, r11
0x1800156b6  pop     r15
0x1800156b8  pop     r14
0x1800156ba  pop     r13
0x1800156bc  pop     rdi
0x1800156bd  pop     rbp
0x1800156be  retn
```
