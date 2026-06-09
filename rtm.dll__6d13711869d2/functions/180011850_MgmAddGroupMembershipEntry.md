# MgmAddGroupMembershipEntry

- ea: `0x180011850`
- end: `0x1800120f4`
- name: `MgmAddGroupMembershipEntry`
- size: `2212`
- prototype: `DWORD __stdcall(HANDLE hProtocol, DWORD dwSourceAddr, DWORD dwSourceMask, DWORD dwGroupAddr, DWORD dwGroupMask, DWORD dwIfIndex, DWORD dwIfNextHopIPAddr, DWORD dwFlags)`
- caller_count: `0`
- callee_count: `23`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180011850`
- `0x180014bfc`
- `0x180014d2c`
- `0x180014f98`
- `0x180015040`
- `0x180015090`
- `0x180015100`
- `0x180015178`
- `0x1800157ec`
- `0x18001958c`
- `0x18001b548`
- `0x18001b588`
- `0x18001b668`
- `0x18001bc4c`
- `0x18001c1a8`
- `0x18001c790`
- `0x18001de20`
- `0x18001de54`
- `0x18001de98`
- `0x18001f7e8`
- `0x18001f952`
- `0x18001f980`
- `0x180020010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180011ab3`
- `KERNEL32!HeapAlloc` at `0x180011ab3`
- `KERNEL32!HeapFree` at `0x180011b77`
- `KERNEL32!HeapFree` at `0x180011b77`
- `rtutils!RouterLogEventA` at `0x18001205f`
- `rtutils!RouterLogEventA` at `0x18001205f`

## string_xrefs

- `0x180011f82`: `Interface %d, %d is not owned by protocol %d, %d`
- `0x180011bc4`: `IGMP join failed because owning protocol entry (%x, %x) not found`
- `0x180011ee1`: `Forward state not updated as no memberships present on interface`

## pseudocode

```c
DWORD __stdcall MgmAddGroupMembershipEntry(
        HANDLE hProtocol,
        DWORD dwSourceAddr,
        DWORD dwSourceMask,
        DWORD dwGroupAddr,
        DWORD dwGroupMask,
        DWORD dwIfIndex,
        DWORD dwIfNextHopIPAddr,
        DWORD dwFlags)
{
  unsigned __int64 ProtocolEntry; // rsi
  DWORD v13; // ebx
  __int64 v14; // rdi
  _WORD *v15; // rdi
  int v16; // ecx
  DWORD v17; // r14d
  char *v18; // rdi
  unsigned int *v19; // r11
  __int16 v20; // r14
  __int16 v21; // r12
  __int64 GroupEntry; // rax
  __int64 v23; // rdi
  __int64 SourceEntry; // rax
  __int64 OutInterfaceEntry; // rax
  char *v26; // r13
  __int64 v27; // rax
  __int16 v28; // r13
  __int64 v29; // rax
  _WORD *v30; // rax
  __int64 v31; // rax
  DWORD v32; // edx
  int v33; // esi
  _WORD *v34; // rax
  int v35; // r8d
  _WORD *v36; // rax
  DWORD plpszSubStringArray; // [rsp+20h] [rbp-E0h]
  int plpszSubStringArraya; // [rsp+20h] [rbp-E0h]
  int dwErrorCode; // [rsp+28h] [rbp-D8h]
  int RefEntry; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v41; // [rsp+58h] [rbp-A8h]
  __int64 v42; // [rsp+60h] [rbp-A0h]
  DWORD v43; // [rsp+68h] [rbp-98h]
  DWORD v44; // [rsp+6Ch] [rbp-94h]
  __int64 v45; // [rsp+70h] [rbp-90h]
  _WORD *v46; // [rsp+78h] [rbp-88h] BYREF
  __int128 v47; // [rsp+80h] [rbp-80h] BYREF
  __int64 v48; // [rsp+90h] [rbp-70h]
  __int64 v49; // [rsp+98h] [rbp-68h] BYREF
  int v50; // [rsp+A0h] [rbp-60h] BYREF
  char v51[2044]; // [rsp+A4h] [rbp-5Ch] BYREF

  RefEntry = 0;
  v50 = 0;
  LODWORD(v41) = dwSourceAddr;
  v44 = dwGroupAddr;
  LODWORD(v45) = dwSourceMask;
  LODWORD(v42) = dwGroupMask;
  v43 = dwIfNextHopIPAddr;
  v47 = 0;
  memset_0(v51, 0, sizeof(v51));
  if ( !(unsigned int)EnterMgmAPI() )
    return 1003;
  if ( qword_18002B8A8 )
  {
    LOWORD(v50) = 0;
    plpszSubStringArray = dwSourceAddr;
    FormatRRASErrorString(
      &v50,
      L"ENTERED MgmAddGroupMembershipEntry : Interface %x, %x : Source : %x, %x : Group : %x, %x",
      dwIfIndex,
      dwIfNextHopIPAddr);
    ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v50);
  }
  AcquireReadLock(&qword_18002B9B8);
  ProtocolEntry = (unsigned __int64)hProtocol ^ 0x474D6300;
  v13 = VerifyProtocolHandle(ProtocolEntry);
  if ( !v13 )
  {
    v14 = 32LL * (dwIfIndex % dword_18002B92C);
    v48 = v14;
    AcquireWriteLock((char *)qword_18002B9E8 + v14 + 16);
    v46 = 0;
    if ( (unsigned int)FindIfEntry((char *)qword_18002B9E8 + v14, dwIfIndex, dwIfNextHopIPAddr, &v46)
      && (v15 = v46) != 0 )
    {
      v16 = *(_DWORD *)(ProtocolEntry + 16);
      v17 = v13 + 1;
      if ( *((_QWORD *)v46 + 3) == *(_QWORD *)(ProtocolEntry + 16) )
      {
        if ( v16 != 10 )
        {
          v17 = 0;
LABEL_11:
          if ( (dwFlags & 1) != 0 )
          {
            *((_QWORD *)&v47 + 1) = &v47;
            *(_QWORD *)&v47 = &v47;
            v13 = AddInterfaceToSourceEntry(
                    ProtocolEntry,
                    dwGroupAddr,
                    v42,
                    v41,
                    v45,
                    dwIfIndex,
                    dwIfNextHopIPAddr,
                    v17,
                    (__int64)&RefEntry,
                    (__int64)&v47);
            if ( !v13 )
              AddSourceToRefList((_DWORD)v15 + 40, v41, v45, dwGroupAddr, v42, v17);
            ReleaseWriteLock((char *)qword_18002B9E8 + v48 + 16);
            InvokeOutstandingCallbacks();
            if ( !v13 && RefEntry )
            {
              v18 = (char *)HeapAlloc(hHeap, 0, 0x38u);
              if ( v18 )
              {
                *(_DWORD *)v18 = v41;
                *((_DWORD *)v18 + 1) = v45;
                *((_DWORD *)v18 + 3) = v42;
                *((_DWORD *)v18 + 2) = dwGroupAddr;
                *((_DWORD *)v18 + 4) = dwIfIndex;
                *((_DWORD *)v18 + 5) = dwIfNextHopIPAddr;
                *((_DWORD *)v18 + 6) = *(_DWORD *)(ProtocolEntry + 16);
                *((_DWORD *)v18 + 7) = *(_DWORD *)(ProtocolEntry + 20);
                *((_DWORD *)v18 + 8) = v17;
                *(_OWORD *)(v18 + 40) = v47;
                *(_QWORD *)(v47 + 8) = v18 + 40;
                **((_QWORD **)&v47 + 1) = v18 + 40;
                v13 = QueueMgmWorker((WORKERCALLBACKFUNC)WorkerFunctionInvokeCreationAlert, v18);
                if ( v13 )
                {
                  if ( qword_18002B8A8 )
                  {
                    LOWORD(v50) = 0;
                    FormatRRASErrorString(&v50, L"Failed to queue WorkerFunctionInvokeCreationAlert", v13);
                    ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(
                      gMgmEtwContext,
                      qword_18002B8A8,
                      &v50);
                  }
                  HeapFree(hHeap, 0, v18);
                  v13 = 0;
                }
              }
              else if ( qword_18002B8A8 )
              {
                LOWORD(v50) = 0;
                FormatRRASErrorString(&v50, L"Failed to allocate %d bytes for work item context", 56);
                ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v50);
              }
            }
          }
          else
          {
            if ( (dwFlags & 2) != 0 && dwGroupAddr && (_DWORD)v41 )
            {
              if ( qword_18002B950 && (unsigned int)qword_18002B950(dwIfIndex, dwGroupAddr) )
              {
                if ( qword_18002B8A8 )
                  ((void (__fastcall *)(__int64, __int64, const wchar_t *))gMgmTemplateFunc)(
                    gMgmEtwContext,
                    qword_18002B8A8,
                    L"Boundary present of group on interface");
              }
              else
              {
                v20 = 0;
                v21 = 0;
                RefEntry = FindRefEntry((int)v15 + 40, 0, 0, 0, plpszSubStringArray, (__int64)&v49);
                if ( RefEntry )
                {
                  AcquireReadLock((char *)qword_18002BA40 + 16);
                  GroupEntry = GetGroupEntry(qword_18002BA40, 0);
                  v23 = GroupEntry;
                  if ( GroupEntry )
                  {
                    AcquireReadLock(GroupEntry + 40);
                    SourceEntry = GetSourceEntry(v23 + 88, 0);
                    if ( SourceEntry )
                    {
                      OutInterfaceEntry = GetOutInterfaceEntry(
                                            (int)SourceEntry + 48,
                                            dwIfIndex,
                                            v43,
                                            *(_DWORD *)(ProtocolEntry + 16),
                                            *(_DWORD *)(ProtocolEntry + 20));
                      if ( OutInterfaceEntry )
                      {
                        v20 = *(_WORD *)(OutInterfaceEntry + 34);
                        v21 = *(_WORD *)(OutInterfaceEntry + 38);
                      }
                    }
                  }
                }
                else
                {
                  v23 = 0;
                }
                v45 = 32LL * (dwGroupAddr % (dword_18002B930 - 1) + 1);
                AcquireReadLock((char *)qword_18002BA40 + v45 + 16);
                v26 = (char *)qword_18002BA40;
                v27 = GetGroupEntry((char *)qword_18002BA40 + v45, v44);
                v42 = v27;
                if ( v27 )
                {
                  v28 = 0;
                  v49 = v27 + 40;
                  AcquireWriteLock(v27 + 40);
                  v29 = GetSourceEntry(v42 + 88, 0);
                  if ( v29 )
                  {
                    v30 = (_WORD *)GetOutInterfaceEntry(
                                     (int)v29 + 48,
                                     dwIfIndex,
                                     v43,
                                     *(_DWORD *)(ProtocolEntry + 16),
                                     *(_DWORD *)(ProtocolEntry + 20));
                    if ( v30 )
                    {
                      v20 |= v30[17];
                      v21 += v30[19];
                      v28 = v30[18];
                    }
                  }
                  v31 = GetSourceEntry(
                          16LL * ((unsigned int)v41 % (dword_18002B934 - 1) + 1) + v42 + 88,
                          (unsigned int)v41);
                  v41 = v31;
                  if ( v31 )
                  {
                    v32 = *(_DWORD *)(ProtocolEntry + 20);
                    v33 = *(_DWORD *)(ProtocolEntry + 16);
                    v44 = v32;
                    v34 = (_WORD *)GetOutInterfaceEntry((int)v31 + 48, dwIfIndex, v43, v33, v32);
                    v46 = v34;
                    if ( v34 )
                    {
                      v20 |= v34[17];
                      v28 += v34[18];
                      v21 += v34[19];
                    }
                    if ( v20 )
                    {
                      AddInterfaceToSourceMfe(v42, v41, dwIfIndex, v35, v33, v44, v33 == 10, (__int64)&v46);
                      v36 = v46;
                      if ( v46 )
                      {
                        v46[17] |= v20;
                        v36[18] = v28;
                        v36[19] = v21;
                      }
                    }
                    else if ( qword_18002B8A8 )
                    {
                      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gMgmTemplateFunc)(
                        gMgmEtwContext,
                        qword_18002B8A8,
                        L"Forward state not updated as no memberships present on interface");
                    }
                  }
                  ReleaseWriteLock(v49);
                  v26 = (char *)qword_18002BA40;
                }
                ReleaseReadLock(&v26[v45 + 16]);
                if ( RefEntry )
                {
                  if ( v23 )
                    ReleaseReadLock(v23 + 40);
                  ReleaseReadLock((char *)qword_18002BA40 + 16);
                }
              }
            }
            ReleaseWriteLock((char *)qword_18002B9E8 + v48 + 16);
          }
          ReleaseReadLock(&qword_18002B9B8);
          if ( !qword_18002B8A8 )
            goto LABEL_74;
          LOWORD(v50) = 0;
          goto LABEL_73;
        }
        goto LABEL_23;
      }
      if ( v16 == 10 && (__int16)v46[16] < 0 )
      {
LABEL_23:
        ProtocolEntry = GetProtocolEntry(&qword_18002B9A8, *((unsigned int *)v46 + 6), *((unsigned int *)v46 + 7));
        if ( ProtocolEntry )
          goto LABEL_11;
        if ( qword_18002B8A8 )
        {
          LOWORD(v50) = 0;
          FormatRRASErrorString(
            &v50,
            L"IGMP join failed because owning protocol entry (%x, %x) not found",
            *((unsigned int *)v15 + 6),
            *v19);
          ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v50);
        }
        v13 = 1003;
        goto LABEL_70;
      }
      if ( qword_18002B8A8 )
      {
        dwErrorCode = *(_DWORD *)(ProtocolEntry + 20);
        plpszSubStringArraya = *(_DWORD *)(ProtocolEntry + 16);
        LOWORD(v50) = 0;
        FormatRRASErrorString(
          &v50,
          L"Interface %d, %d is not owned by protocol %d, %d",
          dwIfIndex,
          dwIfNextHopIPAddr,
          plpszSubStringArraya,
          dwErrorCode);
        ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v50);
      }
      v13 = 87;
      if ( dword_18002BA54 >= v17 )
        RouterLogEventA(qword_18002BA58, v17, 0xC360u, 0, 0, 0x57u);
    }
    else
    {
      if ( qword_18002B8A8 )
      {
        LOWORD(v50) = 0;
        FormatRRASErrorString(&v50, L"Specified interface was not found : %d, %d", dwIfIndex, dwIfNextHopIPAddr);
        ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v50);
      }
      v13 = 87;
      if ( (unsigned int)dword_18002BA54 >= 2 )
        RouterLogEventA(qword_18002BA58, 2u, 0xC35Fu, 0, 0, 0x57u);
    }
LABEL_70:
    ReleaseWriteLock((char *)qword_18002B9E8 + v48 + 16);
  }
  ReleaseReadLock(&qword_18002B9B8);
  if ( qword_18002B8A8 )
  {
    LOWORD(v50) = 0;
LABEL_73:
    FormatRRASErrorString(&v50, L"LEAVING MgmAddGroupMembership %x\n", v13);
    ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v50);
  }
LABEL_74:
  LeaveMgmWorker();
  return v13;
}

```

## disassembly

```asm
0x180011850  push    rbp
0x180011852  push    rbx
0x180011853  push    rsi
0x180011854  push    rdi
0x180011855  push    r12
0x180011857  push    r13
0x180011859  push    r14
0x18001185b  push    r15
0x18001185d  lea     rbp, [rsp-7B8h]
0x180011865  sub     rsp, 8B8h
0x18001186c  mov     rax, cs:__security_cookie
0x180011873  xor     rax, rsp
0x180011876  mov     [rbp+7F0h+var_50], rax
0x18001187d  mov     edi, [rbp+7F0h+dwGroupMask]
0x180011883  mov     rsi, rcx
0x180011886  mov     r12d, [rbp+7F0h+dwIfNextHopIPAddr]
0x18001188d  xor     ecx, ecx
0x18001188f  mov     r15d, [rbp+7F0h+dwIfIndex]
0x180011896  mov     ebx, r8d
0x180011899  mov     [rsp+8F0h+var_8A0], ecx
0x18001189d  mov     r14d, edx
0x1800118a0  mov     [rbp+7F0h+var_850], ecx
0x1800118a3  xorps   xmm0, xmm0
0x1800118a6  mov     dword ptr [rsp+8F0h+var_898], edx
0x1800118aa  lea     rcx, [rbp+7F0h+var_84C]; void *
0x1800118ae  xor     edx, edx; Val
0x1800118b0  mov     [rsp+8F0h+var_884], r9d
0x1800118b5  mov     r8d, 7FCh; Size
0x1800118bb  mov     dword ptr [rsp+8F0h+var_880], ebx
0x1800118bf  mov     r13d, r9d
0x1800118c2  mov     dword ptr [rsp+8F0h+var_890], edi
0x1800118c6  mov     [rsp+8F0h+var_888], r12d
0x1800118cb  movups  [rbp+7F0h+var_870], xmm0
0x1800118cf  call    memset_0
0x1800118d4  call    EnterMgmAPI
0x1800118d9  xor     ecx, ecx
0x1800118db  test    eax, eax
0x1800118dd  jnz     short loc_1800118E9
0x1800118df  mov     eax, 3EBh
0x1800118e4  jmp     loc_1800120D1
0x1800118e9  cmp     cs:qword_18002B8A8, rcx
0x1800118f0  jz      short loc_18001193C
0x1800118f2  mov     dword ptr [rsp+8F0h+var_8B8], edi
0x1800118f6  lea     rdx, aEnteredMgmaddg; "ENTERED MgmAddGroupMembershipEntry : In"...
0x1800118fd  mov     [rsp+8F0h+var_8C0], r13d
0x180011902  mov     r9d, r12d
0x180011905  mov     word ptr [rbp+7F0h+var_850], cx
0x180011909  mov     r8d, r15d
0x18001190c  mov     [rsp+8F0h+dwErrorCode], ebx
0x180011910  lea     rcx, [rbp+7F0h+var_850]
0x180011914  mov     dword ptr [rsp+8F0h+plpszSubStringArray], r14d
0x180011919  call    FormatRRASErrorString
0x18001191e  mov     rdx, cs:qword_18002B8A8
0x180011925  lea     r8, [rbp+7F0h+var_850]
0x180011929  mov     rcx, cs:gMgmEtwContext
0x180011930  mov     rax, cs:gMgmTemplateFunc
0x180011937  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001193c  lea     rcx, qword_18002B9B8
0x180011943  call    AcquireReadLock
0x180011948  xor     rsi, 474D6300h
0x18001194f  mov     rcx, rsi
0x180011952  call    VerifyProtocolHandle
0x180011957  xor     r14d, r14d
0x18001195a  mov     ebx, eax
0x18001195c  test    eax, eax
0x18001195e  jnz     loc_18001207F
0x180011964  mov     rcx, cs:qword_18002B9E8
0x18001196b  xor     edx, edx
0x18001196d  mov     eax, r15d
0x180011970  add     rcx, 10h
0x180011974  div     cs:dword_18002B92C
0x18001197a  mov     edi, edx
0x18001197c  shl     rdi, 5
0x180011980  add     rcx, rdi
0x180011983  mov     [rbp+7F0h+var_860], rdi
0x180011987  call    AcquireWriteLock
0x18001198c  mov     rcx, cs:qword_18002B9E8
0x180011993  lea     r9, [rsp+8F0h+var_878]
0x180011998  add     rcx, rdi
0x18001199b  mov     [rsp+8F0h+var_878], r14
0x1800119a0  mov     r8d, r12d
0x1800119a3  mov     edx, r15d
0x1800119a6  call    FindIfEntry
0x1800119ab  xor     r8d, r8d
0x1800119ae  test    eax, eax
0x1800119b0  jz      loc_180011FEE
0x1800119b6  mov     rdi, [rsp+8F0h+var_878]
0x1800119bb  test    rdi, rdi
0x1800119be  jz      loc_180011FEE
0x1800119c4  mov     ecx, [rsi+10h]
0x1800119c7  lea     r14d, [rbx+1]
0x1800119cb  mov     edx, [rdi+18h]
0x1800119ce  lea     r11, [rdi+1Ch]
0x1800119d2  cmp     edx, ecx
0x1800119d4  jnz     loc_180011B84
0x1800119da  mov     eax, [rsi+14h]
0x1800119dd  cmp     [r11], eax
0x1800119e0  jnz     loc_180011B84
0x1800119e6  cmp     ecx, 0Ah
0x1800119e9  jz      loc_180011B98
0x1800119ef  mov     r14d, r8d
0x1800119f2  test    byte ptr [rbp+7F0h+dwFlags], 1
0x1800119f9  jz      loc_180011C4D
0x1800119ff  mov     r9d, dword ptr [rsp+8F0h+var_898]
0x180011a04  lea     rax, [rbp+7F0h+var_870]
0x180011a08  mov     r8d, dword ptr [rsp+8F0h+var_890]
0x180011a0d  mov     edx, r13d
0x180011a10  mov     qword ptr [rbp+7F0h+var_870+8], rax
0x180011a14  mov     rcx, rsi
0x180011a17  lea     rax, [rbp+7F0h+var_870]
0x180011a1b  mov     qword ptr [rbp+7F0h+var_870], rax
0x180011a1f  lea     rax, [rbp+7F0h+var_870]
0x180011a23  mov     [rsp+8F0h+var_8A8], rax
0x180011a28  lea     rax, [rsp+8F0h+var_8A0]
0x180011a2d  mov     [rsp+8F0h+var_8B0], rax
0x180011a32  mov     eax, dword ptr [rsp+8F0h+var_880]
0x180011a36  mov     dword ptr [rsp+8F0h+var_8B8], r14d
0x180011a3b  mov     [rsp+8F0h+var_8C0], r12d
0x180011a40  mov     [rsp+8F0h+dwErrorCode], r15d
0x180011a45  mov     dword ptr [rsp+8F0h+plpszSubStringArray], eax
0x180011a49  call    AddInterfaceToSourceEntry
0x180011a4e  mov     ebx, eax
0x180011a50  test    eax, eax
0x180011a52  jnz     short loc_180011A76
0x180011a54  mov     eax, dword ptr [rsp+8F0h+var_890]
0x180011a58  lea     rcx, [rdi+28h]
0x180011a5c  mov     r8d, dword ptr [rsp+8F0h+var_880]
0x180011a61  mov     r9d, r13d
0x180011a64  mov     edx, dword ptr [rsp+8F0h+var_898]
0x180011a68  mov     [rsp+8F0h+dwErrorCode], r14d
0x180011a6d  mov     dword ptr [rsp+8F0h+plpszSubStringArray], eax
0x180011a71  call    AddSourceToRefList
0x180011a76  mov     rax, cs:qword_18002B9E8
0x180011a7d  mov     rcx, [rbp+7F0h+var_860]
0x180011a81  add     rax, 10h
0x180011a85  add     rcx, rax
0x180011a88  call    ReleaseWriteLock
0x180011a8d  call    InvokeOutstandingCallbacks
0x180011a92  xor     eax, eax
0x180011a94  test    ebx, ebx
0x180011a96  jnz     loc_180011F52
0x180011a9c  cmp     [rsp+8F0h+var_8A0], eax
0x180011aa0  jz      loc_180011F52
0x180011aa6  mov     rcx, cs:hHeap; hHeap
0x180011aad  lea     r8d, [rax+38h]; dwBytes
0x180011ab1  xor     edx, edx; dwFlags
0x180011ab3  call    cs:__imp_HeapAlloc
0x180011ab9  mov     rdi, rax
0x180011abc  xor     eax, eax
0x180011abe  test    rdi, rdi
0x180011ac1  jz      loc_180011C03
0x180011ac7  mov     eax, dword ptr [rsp+8F0h+var_898]
0x180011acb  mov     rdx, rdi; Context
0x180011ace  mov     [rdi], eax
0x180011ad0  mov     eax, dword ptr [rsp+8F0h+var_880]
0x180011ad4  mov     [rdi+4], eax
0x180011ad7  mov     eax, dword ptr [rsp+8F0h+var_890]
0x180011adb  mov     [rdi+0Ch], eax
0x180011ade  mov     [rdi+8], r13d
0x180011ae2  mov     [rdi+10h], r15d
0x180011ae6  mov     [rdi+14h], r12d
0x180011aea  mov     ecx, [rsi+10h]
0x180011aed  mov     [rdi+18h], ecx
0x180011af0  mov     ecx, [rsi+14h]
0x180011af3  mov     [rdi+1Ch], ecx
0x180011af6  lea     rcx, [rdi+28h]
0x180011afa  mov     [rdi+20h], r14d
0x180011afe  movups  xmm0, [rbp+7F0h+var_870]
0x180011b02  movdqu  xmmword ptr [rcx], xmm0
0x180011b06  mov     rax, qword ptr [rbp+7F0h+var_870]
0x180011b0a  mov     [rax+8], rcx
0x180011b0e  mov     rax, qword ptr [rbp+7F0h+var_870+8]
0x180011b12  mov     [rax], rcx
0x180011b15  lea     rcx, WorkerFunctionInvokeCreationAlert; Function
0x180011b1c  call    QueueMgmWorker
0x180011b21  mov     ebx, eax
0x180011b23  xor     eax, eax
0x180011b25  test    ebx, ebx
0x180011b27  jz      loc_180011F52
0x180011b2d  cmp     cs:qword_18002B8A8, rax
0x180011b34  jz      short loc_180011B6B
0x180011b36  mov     r8d, ebx
0x180011b39  mov     word ptr [rbp+7F0h+var_850], ax
0x180011b3d  lea     rdx, aFailedToQueueW_0; "Failed to queue WorkerFunctionInvokeCre"...
0x180011b44  lea     rcx, [rbp+7F0h+var_850]
0x180011b48  call    FormatRRASErrorString
0x180011b4d  mov     rdx, cs:qword_18002B8A8
0x180011b54  lea     r8, [rbp+7F0h+var_850]
0x180011b58  mov     rcx, cs:gMgmEtwContext
0x180011b5f  mov     rax, cs:gMgmTemplateFunc
0x180011b66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b6b  mov     rcx, cs:hHeap; hHeap
0x180011b72  mov     r8, rdi; lpMem
0x180011b75  xor     edx, edx; dwFlags
0x180011b77  call    cs:__imp_HeapFree
0x180011b7d  xor     ebx, ebx
0x180011b7f  jmp     loc_180011F52
0x180011b84  cmp     ecx, 0Ah
0x180011b87  jnz     loc_180011F76
0x180011b8d  cmp     [rdi+20h], r8w
0x180011b92  jge     loc_180011F76
0x180011b98  mov     r8d, [r11]
0x180011b9b  lea     rcx, qword_18002B9A8
0x180011ba2  call    GetProtocolEntry
0x180011ba7  xor     r8d, r8d
0x180011baa  mov     rsi, rax
0x180011bad  test    rax, rax
0x180011bb0  jnz     loc_1800119F2
0x180011bb6  cmp     cs:qword_18002B8A8, r8
0x180011bbd  jz      short loc_180011BF9
0x180011bbf  mov     word ptr [rbp+7F0h+var_850], r8w
0x180011bc4  lea     rdx, aIgmpJoinFailed; "IGMP join failed because owning protoco"...
0x180011bcb  mov     r9d, [r11]
0x180011bce  lea     rcx, [rbp+7F0h+var_850]
0x180011bd2  mov     r8d, [rdi+18h]
0x180011bd6  call    FormatRRASErrorString
0x180011bdb  mov     rdx, cs:qword_18002B8A8
0x180011be2  lea     r8, [rbp+7F0h+var_850]
0x180011be6  mov     rcx, cs:gMgmEtwContext
0x180011bed  mov     rax, cs:gMgmTemplateFunc
0x180011bf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011bf9  mov     ebx, 3EBh
0x180011bfe  jmp     loc_180012065
0x180011c03  cmp     cs:qword_18002B8A8, rax
0x180011c0a  jz      loc_180011F52
0x180011c10  mov     r8d, 38h ; '8'
0x180011c16  mov     word ptr [rbp+7F0h+var_850], ax
0x180011c1a  lea     rdx, aFailedToAlloca_0; "Failed to allocate %d bytes for work it"...
0x180011c21  lea     rcx, [rbp+7F0h+var_850]
0x180011c25  call    FormatRRASErrorString
0x180011c2a  mov     rdx, cs:qword_18002B8A8
0x180011c31  lea     r8, [rbp+7F0h+var_850]
0x180011c35  mov     rcx, cs:gMgmEtwContext
0x180011c3c  mov     rax, cs:gMgmTemplateFunc
0x180011c43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c48  jmp     loc_180011F52
0x180011c4d  test    byte ptr [rbp+7F0h+dwFlags], 2
0x180011c54  jz      loc_180011F3B
0x180011c5a  test    r13d, r13d
0x180011c5d  jz      loc_180011F3B
0x180011c63  cmp     dword ptr [rsp+8F0h+var_898], r8d
0x180011c68  jz      loc_180011F3B
0x180011c6e  mov     rax, cs:qword_18002B950
0x180011c75  test    rax, rax
0x180011c78  jz      short loc_180011CBB
0x180011c7a  mov     edx, r13d
0x180011c7d  mov     ecx, r15d
0x180011c80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c85  xor     r8d, r8d
0x180011c88  test    eax, eax
0x180011c8a  jz      short loc_180011CBB
0x180011c8c  mov     rdx, cs:qword_18002B8A8
0x180011c93  test    rdx, rdx
0x180011c96  jz      loc_180011F3B
0x180011c9c  mov     rcx, cs:gMgmEtwContext
0x180011ca3  lea     r8, aBoundaryPresen; "Boundary present of group on interface"
0x180011caa  mov     rax, cs:gMgmTemplateFunc
0x180011cb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011cb6  jmp     loc_180011F3B
0x180011cbb  lea     rax, [rbp+7F0h+var_858]
0x180011cbf  xor     r9d, r9d
0x180011cc2  lea     rcx, [rdi+28h]
0x180011cc6  mov     qword ptr [rsp+8F0h+dwErrorCode], rax
0x180011ccb  xor     edx, edx
0x180011ccd  mov     r14d, r8d
0x180011cd0  mov     r12d, r8d
0x180011cd3  call    FindRefEntry
0x180011cd8  xor     ecx, ecx
0x180011cda  mov     [rsp+8F0h+var_8A0], eax
0x180011cde  test    eax, eax
0x180011ce0  jz      short loc_180011D4E
0x180011ce2  mov     rcx, cs:qword_18002BA40
0x180011ce9  add     rcx, 10h
0x180011ced  call    AcquireReadLock
0x180011cf2  mov     rcx, cs:qword_18002BA40
0x180011cf9  xor     edx, edx
0x180011cfb  call    GetGroupEntry
0x180011d00  mov     rdi, rax
0x180011d03  test    rax, rax
0x180011d06  jz      short loc_180011D51
0x180011d08  lea     rcx, [rax+28h]
0x180011d0c  call    AcquireReadLock
0x180011d11  lea     rcx, [rdi+58h]
0x180011d15  xor     edx, edx
0x180011d17  call    GetSourceEntry
0x180011d1c  test    rax, rax
0x180011d1f  jz      short loc_180011D51
0x180011d21  mov     edx, [rsi+14h]
0x180011d24  lea     rcx, [rax+30h]
0x180011d28  mov     r9d, [rsi+10h]
0x180011d2c  mov     r8d, [rsp+8F0h+var_888]
0x180011d31  mov     dword ptr [rsp+8F0h+plpszSubStringArray], edx
0x180011d35  mov     edx, r15d
0x180011d38  call    GetOutInterfaceEntry
0x180011d3d  test    rax, rax
0x180011d40  jz      short loc_180011D51
0x180011d42  movzx   r14d, word ptr [rax+22h]
0x180011d47  movzx   r12d, word ptr [rax+26h]
0x180011d4c  jmp     short loc_180011D51
0x180011d4e  mov     rdi, rcx
  ... truncated ...
```
