# SlbNatIpsCreateSessionForInternalDatagram

- ea: `0x140006f04`
- end: `0x140007601`
- name: `SlbNatIpsCreateSessionForInternalDatagram`
- size: `1789`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x1400020e0`

## callees

- `0x140004094`
- `0x140004d20`
- `0x140004e60`
- `0x140006b74`
- `0x140006f04`
- `0x1400077fc`
- `0x140009b04`
- `0x14000c618`
- `0x14000c87c`
- `0x14000caa0`
- `0x14000d4a4`
- `0x14001432c`
- `0x14001ede0`
- `0x14001ef70`
- `0x14001f440`
- `0x14002d008`
- `0x14002d040`
- `0x14002d3bc`

## pseudocode

```c
__int64 __fastcall SlbNatIpsCreateSessionForInternalDatagram(__int64 a1, __int64 a2, unsigned int a3)
{
  bool v5; // r12
  __int64 v6; // rdx
  __int64 v7; // rcx
  int v8; // esi
  __int64 v9; // r14
  __int64 v10; // rdi
  __int64 v11; // r9
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  int v15; // r15d
  __int64 v16; // rcx
  __int64 v17; // r14
  unsigned int v18; // edi
  __int64 v19; // r9
  __int64 v20; // rdx
  int v21; // r15d
  __int64 v22; // r9
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // rsi
  __int64 v31; // rcx
  __int64 v32; // rax
  char *SessionEntry; // rax
  __int64 v34; // r8
  unsigned __int64 v35; // rcx
  __int64 v36; // rax
  __int64 v38; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v39; // [rsp+68h] [rbp-98h] BYREF
  int v40; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned int v41; // [rsp+70h] [rbp-90h] BYREF
  __int64 v42; // [rsp+78h] [rbp-88h]
  int v43; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v44; // [rsp+84h] [rbp-7Ch]
  __int128 v45; // [rsp+88h] [rbp-78h] BYREF
  __int64 v46; // [rsp+98h] [rbp-68h]
  int *v47; // [rsp+A0h] [rbp-60h]
  _OWORD v48[2]; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v49[10]; // [rsp+D0h] [rbp-30h] BYREF
  _WORD v50[48]; // [rsp+120h] [rbp+20h] BYREF

  v44 = a3;
  v38 = 0;
  v40 = 0;
  v41 = 0;
  memset(v48, 0, 28);
  v39 = 0;
  v42 = 0;
  v5 = 0;
  memset(v49, 0, 0x48u);
  memset(v50, 0, sizeof(v50));
  v8 = 0;
  v9 = *(_QWORD *)(a1 + 40);
  v47 = 0;
  v43 = 0;
  if ( *(_QWORD *)(a1 + 64) )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v7, v6);
  if ( v9 )
  {
    v8 = *(_DWORD *)(v9 + 56);
    if ( v8 )
    {
      v43 = *(_DWORD *)(a2 + 156);
      v47 = &v43;
    }
  }
  if ( (xmmword_1400262E0 & 4) != 0 )
    WPP_SF_d(1026, 24, WPP_2017c49255f13d724299eee942b0d5fe_Traceguids, *(unsigned int *)(a1 + 24));
  v10 = 184;
  v11 = 184;
  if ( *(_WORD *)(a2 + 180) != 2 )
    v11 = 188;
  v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, _DWORD, _QWORD, int, _DWORD, int *, unsigned int *, __int64 *))(*(_QWORD *)(a1 + 16) + 88LL))(
          *(_QWORD *)(a1 + 8),
          *(_QWORD *)(a1 + 48),
          *(unsigned int *)(a1 + 24),
          a2 + v11,
          0,
          0,
          ScopeIdUnspecified,
          0,
          &v40,
          &v41,
          &v38);
  v15 = v12;
  v16 = 25;
  if ( *(_DWORD *)(a1 + 24) == 1 )
  {
    v39 = v41;
  }
  else
  {
    if ( v12 >= 0 )
    {
      if ( *(_WORD *)(a2 + 180) != 2 )
        v10 = 188;
      SlbNatCheckAndLogImproperDefaultRouteEvent(a1, v10 + a2);
      v17 = v42;
      v18 = 18;
      v5 = 1;
      goto LABEL_40;
    }
    if ( v38 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(25, v13);
    if ( v15 != -1073741275 )
    {
      v17 = v42;
      v18 = 12;
LABEL_40:
      if ( v38 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)(a1 + 16) + 104LL))(*(_QWORD *)(a1 + 8));
      if ( v5 )
      {
        v45 = 0;
        LOBYTE(v46) = 0;
        if ( (byte_140026BED & 4) != 0 && *(_WORD *)a1 == 2 )
          SlbNatIpsLogIPv4Datagram(
            *(_DWORD *)(a1 + 24),
            *(_DWORD *)(a1 + 32),
            *(_QWORD *)(a1 + 40),
            0,
            0,
            *(_QWORD *)(a1 + 56),
            2,
            v18);
        *((_QWORD *)&v45 + 1) = *(_QWORD *)(a1 + 56);
        v46 = *((_QWORD *)&v45 + 1);
        LOBYTE(v45) = 0;
        SlbNatAccountChain(&v45, 1);
        (*(void (__fastcall **)(_QWORD, _QWORD, __int128 *))(*(_QWORD *)(a1 + 16) + 40LL))(
          *(_QWORD *)(a1 + 8),
          *(_QWORD *)(a1 + 48),
          &v45);
      }
      else
      {
        LOBYTE(v14) = *(_BYTE *)(a2 + 16);
        SlbNatIpsDropDatagram(a1, *(_QWORD *)(a1 + 56), v14, v18);
      }
      return v17;
    }
    if ( (xmmword_1400262E0 & 4) != 0 )
      WPP_SF_(1026, 25, WPP_2017c49255f13d724299eee942b0d5fe_Traceguids);
    v19 = 4;
    if ( *(_WORD *)(a2 + 180) != 2 )
      v19 = 8;
    v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64, _DWORD, _QWORD, int, _DWORD, int *, unsigned int *, __int64 *))(*(_QWORD *)(a1 + 16) + 88LL))(
            *(_QWORD *)(a1 + 8),
            *(_QWORD *)(a1 + 48),
            1,
            a2 + 180 + v19,
            0,
            0,
            ScopeIdUnspecified,
            0,
            &v40,
            &v39,
            &v38);
  }
  v18 = 0;
  if ( v15 < 0 )
  {
    if ( v38 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v16, v13);
    if ( dword_1400264E8 > 0 && !*(_QWORD *)(a1 + 40) )
    {
      v5 = 1;
      v17 = 0;
      goto LABEL_40;
    }
    goto LABEL_55;
  }
  v20 = v38;
  v21 = 0;
  if ( !v38 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v16, 0);
    v20 = v38;
  }
  (*(void (__fastcall **)(_QWORD, __int64, _OWORD *))(*(_QWORD *)(a1 + 16) + 112LL))(*(_QWORD *)(a1 + 8), v20, v48);
  if ( (xmmword_1400262E0 & 4) != 0 )
    WPP_SF_d(1026, 26, WPP_2017c49255f13d724299eee942b0d5fe_Traceguids, LODWORD(v48[0]));
  if ( !*((_QWORD *)&v48[0] + 1) )
  {
LABEL_38:
    v18 = 15;
    v5 = *(_DWORD *)(a1 + 24) == 1;
LABEL_39:
    v17 = 0;
    goto LABEL_40;
  }
  if ( dword_1400264E8 <= 0 )
  {
    if ( !*(_DWORD *)(*((_QWORD *)&v48[0] + 1) + 40LL) )
      goto LABEL_38;
  }
  else if ( (*(_DWORD *)(*((_QWORD *)&v48[0] + 1) + 24LL) & 4) != 0 )
  {
    goto LABEL_38;
  }
  if ( v8 && v8 != LODWORD(v48[0]) )
  {
    (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)(a1 + 16) + 104LL))(*(_QWORD *)(a1 + 8), v38);
    v22 = 4;
    if ( *(_WORD *)(a2 + 180) != 2 )
      v22 = 8;
    if ( (*(int (__fastcall **)(_QWORD, _QWORD, __int64, __int64, int, int *, int, _DWORD, int *, unsigned int *, __int64 *))(*(_QWORD *)(a1 + 16) + 88LL))(
           *(_QWORD *)(a1 + 8),
           *(_QWORD *)(a1 + 48),
           1,
           a2 + 180 + v22,
           v8,
           v47,
           ScopeIdUnspecified,
           0,
           &v40,
           &v39,
           &v38) < 0 )
    {
      if ( v38 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v24, v23);
LABEL_55:
      v18 = 13;
      goto LABEL_39;
    }
    v25 = v38;
    if ( !v38 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v24, 0);
      v25 = v38;
    }
    (*(void (__fastcall **)(_QWORD, __int64, _OWORD *))(*(_QWORD *)(a1 + 16) + 112LL))(*(_QWORD *)(a1 + 8), v25, v48);
    if ( LODWORD(v48[0]) != v8 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v27, v26);
  }
  RtlAcquireScalableReadLockAtDpcLevel(&SlbNatIpsDataPathState);
  if ( (xmmword_1400262E0 & 4) != 0 )
    WPP_SF_q(v29, v28, v14, v9);
  if ( v9 && (xmmword_1400262E0 & 4) != 0 )
    WPP_SF_d(1026, 28, WPP_2017c49255f13d724299eee942b0d5fe_Traceguids, (*(_DWORD *)(v9 + 24) >> 2) & 1);
  if ( dword_1400264E8 <= 0 )
  {
    v31 = *((_QWORD *)&v48[0] + 1);
  }
  else
  {
    v30 = 0;
    if ( !v9 || (*(_DWORD *)(v9 + 24) & 4) == 0 )
      goto LABEL_74;
    v31 = v9;
  }
  v32 = SlbNatIpsLookupTCAP(v31, *(unsigned int *)(a1 + 24));
  v30 = v32;
  if ( v32 )
  {
    if ( _InterlockedIncrement64((volatile signed __int64 *)(v32 + 336)) <= 1 )
      __fastfail(0xEu);
    v21 = dword_140026840;
  }
LABEL_74:
  _InterlockedDecrement((volatile signed __int32 *)&qword_140026740[8 * (unsigned __int64)(dword_140026708 & v44)]);
  if ( !v30 )
  {
    v5 = *(_DWORD *)(a1 + 24) == 1;
    if ( (xmmword_1400262E0 & 4) != 0 )
      WPP_SF_(1026, 29, WPP_2017c49255f13d724299eee942b0d5fe_Traceguids);
    v18 = 16;
    if ( dword_1400264E8 > 0 )
      v18 = 25;
    goto LABEL_39;
  }
  LODWORD(v49[0]) = *(_DWORD *)(a1 + 24);
  v49[1] = __PAIR64__(v39, v41);
  v49[3] = v38;
  HIDWORD(v49[0]) = v21;
  LOBYTE(v49[8]) = v49[8] & 0xFE | v40 & 1;
  v49[5] = SlbNatIpsSessionCleanupRoutine;
  v49[6] = *(_QWORD *)(a1 + 72);
  LODWORD(v49[7]) = v48[0];
  HIDWORD(v49[7]) = *(_DWORD *)(a1 + 32);
  SessionEntry = WinNatCreateSessionEntry(
                   (__int64)qword_1400263D8,
                   v30,
                   (__int16 *)(a2 + 152),
                   (__int16 *)(a2 + 180),
                   0,
                   0,
                   0,
                   *(_BYTE *)(a2 + 16),
                   0,
                   (int *)v49,
                   (__int64)v50);
  v35 = (unsigned __int64)(SessionEntry + 8);
  v36 = -(__int64)SessionEntry;
  v17 = v35 & -(__int64)(v36 != 0);
  if ( v17 )
  {
    SlbNatIpsCheckHairpinning(v35 & -(__int64)(v36 != 0), 1, a1, a2);
  }
  else
  {
    if ( v50[0] )
    {
      LOBYTE(v34) = *(_BYTE *)(a2 + 16) == 6;
      SlbNatCreateExternalAddressForPortFail(v50, LODWORD(v48[0]), v34);
    }
    v18 = 14;
  }
  WinNatLibDereferenceAddressPool(v30);
  if ( !v17 )
    goto LABEL_40;
  return v17;
}

```

## disassembly

```asm
0x140006f04  mov     [rsp-8+arg_18], rbx
0x140006f09  push    rbp
0x140006f0a  push    rsi
0x140006f0b  push    rdi
0x140006f0c  push    r12
0x140006f0e  push    r13
0x140006f10  push    r14
0x140006f12  push    r15
0x140006f14  lea     rbp, [rsp-90h]
0x140006f1c  sub     rsp, 190h
0x140006f23  mov     rax, cs:__security_cookie
0x140006f2a  xor     rax, rsp
0x140006f2d  mov     [rbp+0C0h+var_40], rax
0x140006f34  xor     r15d, r15d
0x140006f37  mov     [rbp+0C0h+var_13C], r8d
0x140006f3b  xorps   xmm0, xmm0
0x140006f3e  mov     [rsp+1C0h+var_160], r15
0x140006f43  mov     r13, rdx
0x140006f46  mov     [rsp+1C0h+var_154], r15d
0x140006f4b  mov     rbx, rcx
0x140006f4e  mov     [rsp+1C0h+var_150], r15d
0x140006f53  movups  [rbp+0C0h+var_118], xmm0
0x140006f57  lea     r8d, [r15+48h]; Size
0x140006f5b  mov     [rsp+1C0h+var_158], r15d
0x140006f60  xor     eax, eax
0x140006f62  mov     [rsp+1C0h+var_148], r15
0x140006f67  xor     edx, edx; Val
0x140006f69  lea     rcx, [rbp+0C0h+var_F0]; void *
0x140006f6d  movups  [rbp+0C0h+var_118+0Ch], xmm0
0x140006f71  mov     r12b, r15b
0x140006f74  call    memset
0x140006f79  xor     edx, edx; Val
0x140006f7b  lea     r8d, [r15+60h]; Size
0x140006f7f  lea     rcx, [rbp+0C0h+var_A0]; void *
0x140006f83  call    memset
0x140006f88  mov     esi, r15d
0x140006f8b  mov     r14, [rbx+28h]
0x140006f8f  mov     [rbp+0C0h+var_120], r15
0x140006f93  mov     [rbp+0C0h+var_140], r15d
0x140006f97  cmp     [rbx+40h], r15
0x140006f9b  jz      short loc_140006FA2
0x140006f9d  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140006fa2  test    r14, r14
0x140006fa5  jz      short loc_140006FC1
0x140006fa7  mov     esi, [r14+38h]
0x140006fab  test    esi, esi
0x140006fad  jz      short loc_140006FC1
0x140006faf  mov     eax, [r13+9Ch]
0x140006fb6  mov     [rbp+0C0h+var_140], eax
0x140006fb9  lea     rax, [rbp+0C0h+var_140]
0x140006fbd  mov     [rbp+0C0h+var_120], rax
0x140006fc1  test    byte ptr cs:xmmword_1400262E0, 4
0x140006fc8  jz      short loc_140006FE4
0x140006fca  mov     r9d, [rbx+18h]
0x140006fce  lea     r8, WPP_2017c49255f13d724299eee942b0d5fe_Traceguids
0x140006fd5  mov     edx, 18h
0x140006fda  mov     ecx, 402h
0x140006fdf  call    WPP_SF_d
0x140006fe4  mov     rax, [rbx+10h]
0x140006fe8  mov     edi, 0B8h
0x140006fed  mov     r8d, [rbx+18h]
0x140006ff1  mov     edx, 2
0x140006ff6  cmp     [r13+0B4h], dx
0x140006ffe  mov     r9d, edi
0x140007001  mov     rdx, [rbx+30h]
0x140007005  mov     r10, [rax+58h]
0x140007009  lea     ecx, [rdi+4]
0x14000700c  cmovnz  r9d, ecx
0x140007010  lea     rax, [rsp+1C0h+var_160]
0x140007015  mov     rcx, [rbx+8]
0x140007019  add     r9, r13
0x14000701c  mov     [rsp+1C0h+var_170], rax
0x140007021  lea     rax, [rsp+1C0h+var_150]
0x140007026  mov     [rsp+1C0h+var_178], rax
0x14000702b  lea     rax, [rsp+1C0h+var_154]
0x140007030  mov     [rsp+1C0h+var_180], rax
0x140007035  mov     eax, cs:ScopeIdUnspecified
0x14000703b  mov     [rsp+1C0h+var_188], r15d
0x140007040  mov     dword ptr [rsp+1C0h+var_190], eax
0x140007044  mov     rax, r10
0x140007047  mov     [rsp+1C0h+var_198], r15
0x14000704c  mov     dword ptr [rsp+1C0h+var_1A0], r15d
0x140007051  call    _guard_dispatch_icall
0x140007056  cmp     dword ptr [rbx+18h], 1
0x14000705a  mov     r15d, eax
0x14000705d  mov     ecx, 19h
0x140007062  jz      loc_140007170
0x140007068  test    eax, eax
0x14000706a  js      short loc_14000709C
0x14000706c  lea     esi, [rcx-17h]
0x14000706f  mov     rcx, rbx
0x140007072  cmp     [r13+0B4h], si
0x14000707a  lea     eax, [rdi+4]
0x14000707d  cmovnz  edi, eax
0x140007080  lea     rdx, [rdi+r13]
0x140007084  call    SlbNatCheckAndLogImproperDefaultRouteEvent
0x140007089  mov     r14, [rsp+1C0h+var_148]
0x14000708e  lea     edi, [rsi+10h]
0x140007091  xor     r15d, r15d
0x140007094  mov     r12b, 1
0x140007097  jmp     loc_140007235
0x14000709c  cmp     [rsp+1C0h+var_160], 0
0x1400070a2  jz      short loc_1400070AE
0x1400070a4  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400070a9  mov     ecx, 19h
0x1400070ae  cmp     r15d, 0C0000225h
0x1400070b5  jnz     loc_14000715E
0x1400070bb  test    byte ptr cs:xmmword_1400262E0, 4
0x1400070c2  jz      short loc_1400070D7
0x1400070c4  mov     edx, ecx
0x1400070c6  lea     r8, WPP_2017c49255f13d724299eee942b0d5fe_Traceguids
0x1400070cd  mov     ecx, 402h
0x1400070d2  call    WPP_SF_
0x1400070d7  mov     rax, [rbx+10h]
0x1400070db  mov     ecx, 2
0x1400070e0  cmp     [r13+0B4h], cx
0x1400070e8  mov     r8d, 1
0x1400070ee  mov     rdx, [rbx+30h]
0x1400070f2  mov     r10, [rax+58h]
0x1400070f6  lea     r9d, [rcx+2]
0x1400070fa  lea     ecx, [r9+4]
0x1400070fe  cmovnz  r9d, ecx
0x140007102  lea     rax, [rsp+1C0h+var_160]
0x140007107  mov     [rsp+1C0h+var_170], rax
0x14000710c  lea     rcx, [r13+0B4h]
0x140007113  lea     rax, [rsp+1C0h+var_158]
0x140007118  add     r9, rcx
0x14000711b  mov     rcx, [rbx+8]
0x14000711f  mov     [rsp+1C0h+var_178], rax
0x140007124  lea     rax, [rsp+1C0h+var_154]
0x140007129  mov     [rsp+1C0h+var_180], rax
0x14000712e  mov     eax, cs:ScopeIdUnspecified
0x140007134  mov     [rsp+1C0h+var_188], 0
0x14000713c  mov     dword ptr [rsp+1C0h+var_190], eax
0x140007140  mov     rax, r10
0x140007143  mov     [rsp+1C0h+var_198], 0
0x14000714c  mov     dword ptr [rsp+1C0h+var_1A0], 0
0x140007154  call    _guard_dispatch_icall
0x140007159  mov     r15d, eax
0x14000715c  jmp     short loc_140007178
0x14000715e  mov     r14, [rsp+1C0h+var_148]
0x140007163  mov     edi, 0Ch
0x140007168  xor     r15d, r15d
0x14000716b  jmp     loc_140007230
0x140007170  mov     eax, [rsp+1C0h+var_150]
0x140007174  mov     [rsp+1C0h+var_158], eax
0x140007178  xor     edi, edi
0x14000717a  test    r15d, r15d
0x14000717d  jns     short loc_1400071B0
0x14000717f  xor     r15d, r15d
0x140007182  cmp     [rsp+1C0h+var_160], r15
0x140007187  jz      short loc_14000718E
0x140007189  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14000718e  cmp     cs:dword_1400264E8, r15d
0x140007195  jle     loc_14000738D
0x14000719b  cmp     [rbx+28h], r15
0x14000719f  jnz     loc_14000738D
0x1400071a5  mov     r12b, 1
0x1400071a8  mov     r14, rdi
0x1400071ab  jmp     loc_140007230
0x1400071b0  mov     rdx, [rsp+1C0h+var_160]
0x1400071b5  xor     r15d, r15d
0x1400071b8  test    rdx, rdx
0x1400071bb  jnz     short loc_1400071C7
0x1400071bd  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400071c2  mov     rdx, [rsp+1C0h+var_160]
0x1400071c7  mov     rax, [rbx+10h]
0x1400071cb  lea     r8, [rbp+0C0h+var_118]
0x1400071cf  mov     rcx, [rbx+8]
0x1400071d3  mov     rax, [rax+70h]
0x1400071d7  call    _guard_dispatch_icall
0x1400071dc  test    byte ptr cs:xmmword_1400262E0, 4
0x1400071e3  jz      short loc_1400071FF
0x1400071e5  mov     r9d, dword ptr [rbp+0C0h+var_118]
0x1400071e9  lea     r8, WPP_2017c49255f13d724299eee942b0d5fe_Traceguids
0x1400071f0  mov     edx, 1Ah
0x1400071f5  mov     ecx, 402h
0x1400071fa  call    WPP_SF_d
0x1400071ff  mov     rax, qword ptr [rbp+0C0h+var_118+8]
0x140007203  test    rax, rax
0x140007206  jz      short loc_140007220
0x140007208  cmp     cs:dword_1400264E8, r15d
0x14000720f  jle     loc_1400072D7
0x140007215  mov     eax, [rax+18h]
0x140007218  test    al, 4
0x14000721a  jz      loc_1400072E1
0x140007220  cmp     dword ptr [rbx+18h], 1
0x140007224  mov     edi, 0Fh
0x140007229  setz    r12b
0x14000722d  mov     r14, r15
0x140007230  mov     esi, 2
0x140007235  mov     rdx, [rsp+1C0h+var_160]
0x14000723a  test    rdx, rdx
0x14000723d  jz      short loc_140007250
0x14000723f  mov     rax, [rbx+10h]
0x140007243  mov     rcx, [rbx+8]
0x140007247  mov     rax, [rax+68h]
0x14000724b  call    _guard_dispatch_icall
0x140007250  test    r12b, r12b
0x140007253  jz      loc_1400075C0
0x140007259  xor     eax, eax
0x14000725b  xorps   xmm0, xmm0
0x14000725e  test    cs:byte_140026BED, 4
0x140007265  movups  [rbp+0C0h+var_138], xmm0
0x140007269  mov     byte ptr [rbp+0C0h+var_128], al
0x14000726c  jz      short loc_14000729B
0x14000726e  cmp     [rbx], si
0x140007271  jnz     short loc_14000729B
0x140007273  mov     rax, [rbx+38h]
0x140007277  xor     r9d, r9d
0x14000727a  mov     r8, [rbx+28h]
0x14000727e  mov     edx, [rbx+20h]
0x140007281  mov     ecx, [rbx+18h]
0x140007284  mov     [rsp+1C0h+var_188], edi
0x140007288  mov     dword ptr [rsp+1C0h+var_190], esi
0x14000728c  mov     [rsp+1C0h+var_198], rax
0x140007291  mov     dword ptr [rsp+1C0h+var_1A0], r15d
0x140007296  call    SlbNatIpsLogIPv4Datagram
0x14000729b  mov     rax, [rbx+38h]
0x14000729f  lea     rcx, [rbp+0C0h+var_138]
0x1400072a3  mov     edx, 1
0x1400072a8  mov     qword ptr [rbp+0C0h+var_138+8], rax
0x1400072ac  mov     [rbp+0C0h+var_128], rax
0x1400072b0  mov     byte ptr [rbp+0C0h+var_138], r15b
0x1400072b4  call    SlbNatAccountChain
0x1400072b9  mov     rax, [rbx+10h]
0x1400072bd  lea     r8, [rbp+0C0h+var_138]
0x1400072c1  mov     rdx, [rbx+30h]
0x1400072c5  mov     rcx, [rbx+8]
0x1400072c9  mov     rax, [rax+28h]
0x1400072cd  call    _guard_dispatch_icall
0x1400072d2  jmp     loc_1400075D3
0x1400072d7  cmp     [rax+28h], r15d
0x1400072db  jz      loc_140007220
0x1400072e1  test    esi, esi
0x1400072e3  jz      loc_1400073CA
0x1400072e9  cmp     esi, dword ptr [rbp+0C0h+var_118]
0x1400072ec  jz      loc_1400073CA
0x1400072f2  mov     rax, [rbx+10h]
0x1400072f6  mov     rdx, [rsp+1C0h+var_160]
0x1400072fb  mov     rcx, [rbx+8]
0x1400072ff  mov     rax, [rax+68h]
0x140007303  call    _guard_dispatch_icall
0x140007308  mov     rax, [rbx+10h]
0x14000730c  lea     rcx, [r13+0B4h]
0x140007313  mov     r9d, 4
0x140007319  mov     r10, [rax+58h]
0x14000731d  lea     rax, [rsp+1C0h+var_160]
0x140007322  mov     [rsp+1C0h+var_170], rax
0x140007327  lea     edx, [r9-2]
0x14000732b  cmp     [rcx], dx
0x14000732e  lea     rax, [rsp+1C0h+var_158]
0x140007333  mov     [rsp+1C0h+var_178], rax
0x140007338  lea     edx, [r9+4]
0x14000733c  lea     rax, [rsp+1C0h+var_154]
0x140007341  cmovnz  r9d, edx
0x140007345  mov     [rsp+1C0h+var_180], rax
0x14000734a  lea     r8d, [rdx-7]
0x14000734e  mov     eax, cs:ScopeIdUnspecified
0x140007354  add     r9, rcx
0x140007357  mov     rdx, [rbx+30h]
0x14000735b  mov     rcx, [rbx+8]
0x14000735f  mov     [rsp+1C0h+var_188], r15d
0x140007364  mov     dword ptr [rsp+1C0h+var_190], eax
0x140007368  mov     rax, [rbp+0C0h+var_120]
0x14000736c  mov     [rsp+1C0h+var_198], rax
0x140007371  mov     rax, r10
0x140007374  mov     dword ptr [rsp+1C0h+var_1A0], esi
0x140007378  call    _guard_dispatch_icall
0x14000737d  test    eax, eax
0x14000737f  jns     short loc_140007397
0x140007381  cmp     [rsp+1C0h+var_160], r15
0x140007386  jz      short loc_14000738D
0x140007388  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14000738d  mov     edi, 0Dh
0x140007392  jmp     loc_14000722D
0x140007397  mov     rdx, [rsp+1C0h+var_160]
0x14000739c  test    rdx, rdx
0x14000739f  jnz     short loc_1400073AB
0x1400073a1  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400073a6  mov     rdx, [rsp+1C0h+var_160]
0x1400073ab  mov     rax, [rbx+10h]
0x1400073af  lea     r8, [rbp+0C0h+var_118]
0x1400073b3  mov     rcx, [rbx+8]
0x1400073b7  mov     rax, [rax+70h]
0x1400073bb  call    _guard_dispatch_icall
0x1400073c0  cmp     dword ptr [rbp+0C0h+var_118], esi
0x1400073c3  jz      short loc_1400073CA
0x1400073c5  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400073ca  mov     edx, [rbp+0C0h+var_13C]
0x1400073cd  lea     rcx, SlbNatIpsDataPathState; SpinLock
0x1400073d4  call    RtlAcquireScalableReadLockAtDpcLevel
0x1400073d9  test    byte ptr cs:xmmword_1400262E0, 4
0x1400073e0  jz      short loc_1400073EA
0x1400073e2  mov     r9, r14
0x1400073e5  call    WPP_SF_q
0x1400073ea  test    r14, r14
0x1400073ed  jz      short loc_14000741A
0x1400073ef  test    byte ptr cs:xmmword_1400262E0, 4
0x1400073f6  jz      short loc_14000741A
  ... truncated ...
```
