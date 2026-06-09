# DemotePeer(AutoPtr<NtpPeer>)

- ea: `0x18003a900`
- end: `0x18003ac49`
- name: `?DemotePeer@@YAJV?$AutoPtr@UNtpPeer@@@@@Z`
- size: `841`
- prototype: `__int64 __fastcall(volatile signed __int32 **)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x180016960`

## callees

- `0x1800144ac`
- `0x1800164b0`
- `0x180018138`
- `0x18001a714`
- `0x18001bbe0`
- `0x18001d9a0`
- `0x18002f498`
- `0x180030d18`
- `0x180034c08`
- `0x180038424`
- `0x18003a900`
- `0x18003ac50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ac26`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ac26`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003a92e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003a92e`

## string_xrefs

- `0x18003abab`: `*** DomHier Peer timed out - other paths remain.\n`
- `0x18003abc4`: `*** Manual Peer timed out - other paths remain.\n`

## pseudocode

```c
__int64 __fastcall DemotePeer(volatile signed __int32 **a1)
{
  _NtpProvState *v2; // rsi
  _QWORD *v3; // r14
  volatile signed __int32 *v4; // rax
  int v5; // edi
  __int64 v6; // rcx
  __int64 v7; // rdx
  volatile signed __int32 *v8; // rax
  char v9; // di
  __int64 v10; // rcx
  __int64 v11; // rdx
  volatile signed __int32 *v12; // rax
  __int64 v13; // rdx
  volatile signed __int32 *v14; // rax
  int v15; // eax
  __int64 v16; // rcx
  int v17; // eax
  volatile signed __int32 *v19; // [rsp+20h] [rbp-20h] BYREF
  volatile signed __int32 **v20; // [rsp+28h] [rbp-18h]
  volatile signed __int32 **v21; // [rsp+30h] [rbp-10h]
  __int64 v22; // [rsp+78h] [rbp+38h] BYREF
  volatile signed __int32 *v23; // [rsp+80h] [rbp+40h] BYREF
  volatile signed __int32 *v24; // [rsp+88h] [rbp+48h] BYREF

  LOBYTE(v22) = 0;
  v2 = g_pnpstate;
  v3 = (_QWORD *)((char *)g_pnpstate + 408);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_pnpstate + 328));
  v24 = (volatile signed __int32 *)&v23;
  v4 = *a1;
  v23 = v4;
  if ( v4 )
    _InterlockedIncrement(v4);
  v5 = Reachability_RemovePeer(&v23, &v22);
  if ( v5 >= 0 )
  {
    if ( *((_BYTE *)g_pnpstate + 50) && (v6 = *((_QWORD *)*a1 + 1), *(_DWORD *)(v6 + 48) == 4) )
    {
      v5 = AddNewPendingNtsNtpPeer(*(const unsigned __int16 **)(v6 + 72), gc_toZero, *(_QWORD *)(v6 + 832));
      if ( v5 < 0 )
        goto LABEL_45;
      v7 = *(_QWORD *)(*((_QWORD *)v2 + 54) + 8 * ((__int64)(*((_QWORD *)v2 + 55) - *((_QWORD *)v2 + 54)) >> 3) - 8);
      v19 = (volatile signed __int32 *)v7;
      if ( v7 )
        _InterlockedIncrement((volatile signed __int32 *)v7);
      *(_DWORD *)(*(_QWORD *)(v7 + 8) + 848LL) = *(_DWORD *)(*((_QWORD *)*a1 + 1) + 848LL);
      v20 = (volatile signed __int32 **)&v22;
      v22 = v7;
      if ( v7 )
        _InterlockedIncrement((volatile signed __int32 *)v7);
      v21 = &v24;
      v8 = *a1;
      v24 = v8;
      if ( v8 )
        _InterlockedIncrement(v8);
      PerformBackoffOnNewPendingPeer(&v24, &v22);
      v9 = 0;
      AutoPtr<NtpPeer>::~AutoPtr<NtpPeer>(&v19);
    }
    else
    {
      v9 = v22;
    }
    v10 = *((_QWORD *)*a1 + 1);
    if ( !v9 )
    {
      v15 = *(_DWORD *)(v10 + 48);
      if ( v15 == 1 )
      {
        if ( (unsigned __int8)FileLogAllowEntry(52) )
          FileLogAdd(L"*** DomHier Peer timed out - other paths remain.\n");
      }
      else if ( !v15 && (unsigned __int8)FileLogAllowEntry(50) )
      {
        FileLogAdd(L"*** Manual Peer timed out - other paths remain.\n");
      }
      goto LABEL_40;
    }
    if ( *(_DWORD *)(v10 + 48) == 1 )
    {
      v5 = AddNewPendingDomHierPeer(*(const unsigned __int16 **)(v10 + 88));
      if ( v5 < 0 )
        goto LABEL_45;
      v11 = *(_QWORD *)(*((_QWORD *)v2 + 54) + 8 * ((__int64)(*((_QWORD *)v2 + 55) - *((_QWORD *)v2 + 54)) >> 3) - 8);
      v19 = (volatile signed __int32 *)v11;
      if ( v11 )
        _InterlockedIncrement((volatile signed __int32 *)v11);
      *(_DWORD *)(*(_QWORD *)(v11 + 8) + 112LL) = *(_DWORD *)(*((_QWORD *)*a1 + 1) + 112LL);
      *(_DWORD *)(*(_QWORD *)(v11 + 8) + 848LL) = *(_DWORD *)(*((_QWORD *)*a1 + 1) + 848LL);
      v21 = (volatile signed __int32 **)&v22;
      v22 = v11;
      if ( v11 )
        _InterlockedIncrement((volatile signed __int32 *)v11);
      v20 = &v24;
      v12 = *a1;
      v24 = v12;
      if ( v12 )
        _InterlockedIncrement(v12);
    }
    else
    {
      if ( *(_DWORD *)(v10 + 48) )
      {
LABEL_40:
        std::find<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<AutoPtr<NtpPeer>>>>,AutoPtr<NtpPeer>>(
          &v22,
          *v3,
          v3[1],
          a1,
          v19,
          v20,
          v21);
        if ( v3[1] != v22 )
          std::vector<AutoPtr<NtpPeer>,MyThrowingAllocator<AutoPtr<NtpPeer>>>::erase(v3, &v22);
        LogThrottledTimeSourceChangeEvent();
        v16 = (__int64)(v3[1] - *v3) >> 3;
        v17 = -(int)v16;
        if ( (int)v16 > 0 )
          v17 = v16;
        g_dwNtpTimeSourceCount = v17;
        v5 = 0;
        goto LABEL_45;
      }
      v5 = AddNewPendingManualPeer(*(_QWORD *)(v10 + 72), gc_toZero, *(_QWORD *)(v10 + 832));
      if ( v5 < 0 )
        goto LABEL_45;
      v13 = *(_QWORD *)(*((_QWORD *)v2 + 54) + 8 * ((__int64)(*((_QWORD *)v2 + 55) - *((_QWORD *)v2 + 54)) >> 3) - 8);
      v19 = (volatile signed __int32 *)v13;
      if ( v13 )
        _InterlockedIncrement((volatile signed __int32 *)v13);
      *(_DWORD *)(*(_QWORD *)(v13 + 8) + 848LL) = *(_DWORD *)(*((_QWORD *)*a1 + 1) + 848LL);
      v21 = (volatile signed __int32 **)&v22;
      v22 = v13;
      if ( v13 )
        _InterlockedIncrement((volatile signed __int32 *)v13);
      v20 = &v24;
      v14 = *a1;
      v24 = v14;
      if ( v14 )
        _InterlockedIncrement(v14);
    }
    PerformBackoffOnNewPendingPeer(&v24, &v22);
    AutoPtr<NtpPeer>::~AutoPtr<NtpPeer>(&v19);
    goto LABEL_40;
  }
LABEL_45:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)g_pnpstate + 328));
  AutoPtr<NtpPeer>::~AutoPtr<NtpPeer>(a1);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18003a900  mov     [rsp-28h+arg_0], rcx
0x18003a905  push    rbp
0x18003a906  push    rbx
0x18003a907  push    rsi
0x18003a908  push    rdi
0x18003a909  push    r14
0x18003a90b  mov     rbp, rsp
0x18003a90e  sub     rsp, 40h
0x18003a912  mov     rbx, rcx
0x18003a915  mov     byte ptr [rbp+arg_8], 0
0x18003a919  mov     rsi, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x18003a920  lea     r14, [rsi+198h]
0x18003a927  lea     rcx, [rsi+148h]; lpCriticalSection
0x18003a92e  call    cs:__imp_EnterCriticalSection
0x18003a935  nop     dword ptr [rax+rax+00h]
0x18003a93a  lea     rax, [rbp+arg_10]
0x18003a93e  mov     [rbp+arg_18], rax
0x18003a942  mov     rax, [rbx]
0x18003a945  mov     [rbp+arg_10], rax
0x18003a949  test    rax, rax
0x18003a94c  jz      short loc_18003A951
0x18003a94e  lock inc dword ptr [rax]
0x18003a951  lea     rdx, [rbp+arg_8]
0x18003a955  lea     rcx, [rbp+arg_10]
0x18003a959  call    ?Reachability_RemovePeer@@YAJV?$AutoPtr@UNtpPeer@@@@PEA_N_N@Z; Reachability_RemovePeer(AutoPtr<NtpPeer>,bool *,bool)
0x18003a95e  mov     edi, eax
0x18003a960  test    eax, eax
0x18003a962  js      loc_18003AC18
0x18003a968  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x18003a96f  cmp     byte ptr [rax+32h], 0
0x18003a973  jz      loc_18003AA2E
0x18003a979  mov     rax, [rbx]
0x18003a97c  mov     rcx, [rax+8]
0x18003a980  cmp     dword ptr [rcx+30h], 4
0x18003a984  jnz     loc_18003AA2E
0x18003a98a  mov     r8, [rcx+340h]
0x18003a991  mov     rdx, cs:?gc_toZero@@3UNtTimeOffset@@B; NtTimeOffset const gc_toZero
0x18003a998  mov     rcx, [rcx+48h]
0x18003a99c  call    ?AddNewPendingNtsNtpPeer@@YAJPEBGUNtTimePeriod@@UNtTimeEpoch@@@Z; AddNewPendingNtsNtpPeer(ushort const *,NtTimePeriod,NtTimeEpoch)
0x18003a9a1  mov     edi, eax
0x18003a9a3  test    eax, eax
0x18003a9a5  js      loc_18003AC18
0x18003a9ab  mov     rcx, [rsi+1B0h]
0x18003a9b2  mov     rax, [rsi+1B8h]
0x18003a9b9  sub     rax, rcx
0x18003a9bc  sar     rax, 3
0x18003a9c0  mov     rdx, [rcx+rax*8-8]
0x18003a9c5  mov     [rbp+var_20], rdx
0x18003a9c9  test    rdx, rdx
0x18003a9cc  jz      short loc_18003A9D1
0x18003a9ce  lock inc dword ptr [rdx]
0x18003a9d1  mov     rax, [rbx]
0x18003a9d4  mov     rax, [rax+8]
0x18003a9d8  mov     rcx, [rdx+8]
0x18003a9dc  mov     eax, [rax+350h]
0x18003a9e2  mov     [rcx+350h], eax
0x18003a9e8  lea     rax, [rbp+arg_8]
0x18003a9ec  mov     [rbp+var_18], rax
0x18003a9f0  mov     [rbp+arg_8], rdx
0x18003a9f4  test    rdx, rdx
0x18003a9f7  jz      short loc_18003A9FC
0x18003a9f9  lock inc dword ptr [rdx]
0x18003a9fc  lea     rax, [rbp+arg_18]
0x18003aa00  mov     [rbp+var_10], rax
0x18003aa04  mov     rax, [rbx]
0x18003aa07  mov     [rbp+arg_18], rax
0x18003aa0b  test    rax, rax
0x18003aa0e  jz      short loc_18003AA13
0x18003aa10  lock inc dword ptr [rax]
0x18003aa13  lea     rdx, [rbp+arg_8]
0x18003aa17  lea     rcx, [rbp+arg_18]
0x18003aa1b  call    ?PerformBackoffOnNewPendingPeer@@YAXV?$AutoPtr@UNtpPeer@@@@0@Z; PerformBackoffOnNewPendingPeer(AutoPtr<NtpPeer>,AutoPtr<NtpPeer>)
0x18003aa20  xor     dil, dil
0x18003aa23  lea     rcx, [rbp+var_20]
0x18003aa27  call    ??1?$AutoPtr@UNtpPeer@@@@QEAA@XZ; AutoPtr<NtpPeer>::~AutoPtr<NtpPeer>(void)
0x18003aa2c  jmp     short loc_18003AA32
0x18003aa2e  mov     dil, byte ptr [rbp+arg_8]
0x18003aa32  mov     rax, [rbx]
0x18003aa35  mov     rcx, [rax+8]
0x18003aa39  test    dil, dil
0x18003aa3c  jz      loc_18003AB97
0x18003aa42  cmp     dword ptr [rcx+30h], 1
0x18003aa46  jnz     loc_18003AAEB
0x18003aa4c  mov     rcx, [rcx+58h]; unsigned __int16 *
0x18003aa50  call    ?AddNewPendingDomHierPeer@@YAJPEBG@Z; AddNewPendingDomHierPeer(ushort const *)
0x18003aa55  mov     edi, eax
0x18003aa57  test    eax, eax
0x18003aa59  js      loc_18003AC18
0x18003aa5f  mov     rcx, [rsi+1B0h]
0x18003aa66  mov     rax, [rsi+1B8h]
0x18003aa6d  sub     rax, rcx
0x18003aa70  sar     rax, 3
0x18003aa74  mov     rdx, [rcx+rax*8-8]
0x18003aa79  mov     [rbp+var_20], rdx
0x18003aa7d  test    rdx, rdx
0x18003aa80  jz      short loc_18003AA85
0x18003aa82  lock inc dword ptr [rdx]
0x18003aa85  mov     rax, [rbx]
0x18003aa88  mov     rax, [rax+8]
0x18003aa8c  mov     rcx, [rdx+8]
0x18003aa90  mov     eax, [rax+70h]
0x18003aa93  mov     [rcx+70h], eax
0x18003aa96  mov     rax, [rbx]
0x18003aa99  mov     rax, [rax+8]
0x18003aa9d  mov     rcx, [rdx+8]
0x18003aaa1  mov     eax, [rax+350h]
0x18003aaa7  mov     [rcx+350h], eax
0x18003aaad  lea     rax, [rbp+arg_8]
0x18003aab1  mov     [rbp+var_10], rax
0x18003aab5  mov     [rbp+arg_8], rdx
0x18003aab9  test    rdx, rdx
0x18003aabc  jz      short loc_18003AAC1
0x18003aabe  lock inc dword ptr [rdx]
0x18003aac1  lea     rax, [rbp+arg_18]
0x18003aac5  mov     [rbp+var_18], rax
0x18003aac9  mov     rax, [rbx]
0x18003aacc  mov     [rbp+arg_18], rax
0x18003aad0  test    rax, rax
0x18003aad3  jz      short loc_18003AAD8
0x18003aad5  lock inc dword ptr [rax]
0x18003aad8  lea     rdx, [rbp+arg_8]
0x18003aadc  lea     rcx, [rbp+arg_18]
0x18003aae0  call    ?PerformBackoffOnNewPendingPeer@@YAXV?$AutoPtr@UNtpPeer@@@@0@Z; PerformBackoffOnNewPendingPeer(AutoPtr<NtpPeer>,AutoPtr<NtpPeer>)
0x18003aae5  nop
0x18003aae6  jmp     loc_18003AB8C
0x18003aaeb  cmp     dword ptr [rcx+30h], 0
0x18003aaef  jnz     loc_18003ABD0
0x18003aaf5  mov     r8, [rcx+340h]
0x18003aafc  mov     rdx, cs:?gc_toZero@@3UNtTimeOffset@@B; NtTimeOffset const gc_toZero
0x18003ab03  mov     rcx, [rcx+48h]
0x18003ab07  call    ?AddNewPendingManualPeer@@YAJPEBGUNtTimePeriod@@UNtTimeEpoch@@@Z; AddNewPendingManualPeer(ushort const *,NtTimePeriod,NtTimeEpoch)
0x18003ab0c  mov     edi, eax
0x18003ab0e  test    eax, eax
0x18003ab10  js      loc_18003AC18
0x18003ab16  mov     rcx, [rsi+1B0h]
0x18003ab1d  mov     rax, [rsi+1B8h]
0x18003ab24  sub     rax, rcx
0x18003ab27  sar     rax, 3
0x18003ab2b  mov     rdx, [rcx+rax*8-8]
0x18003ab30  mov     [rbp+var_20], rdx
0x18003ab34  test    rdx, rdx
0x18003ab37  jz      short loc_18003AB3C
0x18003ab39  lock inc dword ptr [rdx]
0x18003ab3c  mov     rax, [rbx]
0x18003ab3f  mov     rax, [rax+8]
0x18003ab43  mov     rcx, [rdx+8]
0x18003ab47  mov     eax, [rax+350h]
0x18003ab4d  mov     [rcx+350h], eax
0x18003ab53  lea     rax, [rbp+arg_8]
0x18003ab57  mov     [rbp+var_10], rax
0x18003ab5b  mov     [rbp+arg_8], rdx
0x18003ab5f  test    rdx, rdx
0x18003ab62  jz      short loc_18003AB67
0x18003ab64  lock inc dword ptr [rdx]
0x18003ab67  lea     rax, [rbp+arg_18]
0x18003ab6b  mov     [rbp+var_18], rax
0x18003ab6f  mov     rax, [rbx]
0x18003ab72  mov     [rbp+arg_18], rax
0x18003ab76  test    rax, rax
0x18003ab79  jz      short loc_18003AB7E
0x18003ab7b  lock inc dword ptr [rax]
0x18003ab7e  lea     rdx, [rbp+arg_8]
0x18003ab82  lea     rcx, [rbp+arg_18]
0x18003ab86  call    ?PerformBackoffOnNewPendingPeer@@YAXV?$AutoPtr@UNtpPeer@@@@0@Z; PerformBackoffOnNewPendingPeer(AutoPtr<NtpPeer>,AutoPtr<NtpPeer>)
0x18003ab8b  nop
0x18003ab8c  lea     rcx, [rbp+var_20]
0x18003ab90  call    ??1?$AutoPtr@UNtpPeer@@@@QEAA@XZ; AutoPtr<NtpPeer>::~AutoPtr<NtpPeer>(void)
0x18003ab95  jmp     short loc_18003ABD0
0x18003ab97  mov     eax, [rcx+30h]
0x18003ab9a  cmp     eax, 1
0x18003ab9d  jnz     short loc_18003ABB4
0x18003ab9f  lea     ecx, [rax+33h]
0x18003aba2  call    FileLogAllowEntry
0x18003aba7  test    al, al
0x18003aba9  jz      short loc_18003ABD0
0x18003abab  lea     rcx, aDomhierPeerTim; "*** DomHier Peer timed out - other path"...
0x18003abb2  jmp     short loc_18003ABCB
0x18003abb4  test    eax, eax
0x18003abb6  jnz     short loc_18003ABD0
0x18003abb8  lea     ecx, [rax+32h]
0x18003abbb  call    FileLogAllowEntry
0x18003abc0  test    al, al
0x18003abc2  jz      short loc_18003ABD0
0x18003abc4  lea     rcx, aManualPeerTime; "*** Manual Peer timed out - other paths"...
0x18003abcb  call    FileLogAdd
0x18003abd0  mov     r9, rbx
0x18003abd3  mov     r8, [r14+8]
0x18003abd7  mov     rdx, [r14]
0x18003abda  lea     rcx, [rbp+arg_8]
0x18003abde  call    ??$find@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$AutoPtr@UNtpPeer@@@@@std@@@std@@@std@@V?$AutoPtr@UNtpPeer@@@@@std@@YA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$AutoPtr@UNtpPeer@@@@@std@@@std@@@0@V10@V10@AEBV?$AutoPtr@UNtpPeer@@@@@Z; std::find<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<AutoPtr<NtpPeer>>>>,AutoPtr<NtpPeer>>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<AutoPtr<NtpPeer>>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<AutoPtr<NtpPeer>>>>,AutoPtr<NtpPeer> const &)
0x18003abe3  mov     r8, [rbp+arg_8]
0x18003abe7  cmp     [r14+8], r8
0x18003abeb  jz      short loc_18003ABF9
0x18003abed  lea     rdx, [rbp+arg_8]
0x18003abf1  mov     rcx, r14
0x18003abf4  call    ?erase@?$vector@V?$AutoPtr@UNtpPeer@@@@V?$MyThrowingAllocator@V?$AutoPtr@UNtpPeer@@@@@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$AutoPtr@UNtpPeer@@@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$AutoPtr@UNtpPeer@@@@@std@@@std@@@2@@Z; std::vector<AutoPtr<NtpPeer>,MyThrowingAllocator<AutoPtr<NtpPeer>>>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<AutoPtr<NtpPeer>>>>)
0x18003abf9  call    ?LogThrottledTimeSourceChangeEvent@@YAXXZ; LogThrottledTimeSourceChangeEvent(void)
0x18003abfe  mov     rcx, [r14+8]
0x18003ac02  sub     rcx, [r14]
0x18003ac05  sar     rcx, 3
0x18003ac09  mov     eax, ecx
0x18003ac0b  neg     eax
0x18003ac0d  cmovs   eax, ecx
0x18003ac10  mov     cs:g_dwNtpTimeSourceCount, eax
0x18003ac16  xor     edi, edi
0x18003ac18  mov     rcx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x18003ac1f  add     rcx, 148h; lpCriticalSection
0x18003ac26  call    cs:__imp_LeaveCriticalSection
0x18003ac2d  nop     dword ptr [rax+rax+00h]
0x18003ac32  nop
0x18003ac33  mov     rcx, rbx
0x18003ac36  call    ??1?$AutoPtr@UNtpPeer@@@@QEAA@XZ; AutoPtr<NtpPeer>::~AutoPtr<NtpPeer>(void)
0x18003ac3b  mov     eax, edi
0x18003ac3d  add     rsp, 40h
0x18003ac41  pop     r14
0x18003ac43  pop     rdi
0x18003ac44  pop     rsi
0x18003ac45  pop     rbx
0x18003ac46  pop     rbp
0x18003ac47  retn
```
