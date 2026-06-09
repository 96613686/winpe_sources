# InvokeOutstandingCallbacks

- ea: `0x18001958c`
- end: `0x180019a15`
- name: `InvokeOutstandingCallbacks`
- size: `1161`
- prototype: ``
- caller_count: `5`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x180011850`
- `0x180012800`
- `0x180014580`
- `0x180019de0`
- `0x18001a360`

## callees

- `0x180007110`
- `0x180007220`
- `0x1800072f0`
- `0x18000a670`
- `0x180014bfc`
- `0x180014d2c`
- `0x180015100`
- `0x180015178`
- `0x1800165d4`
- `0x18001958c`
- `0x18001b548`
- `0x18001bc4c`
- `0x18001f7e8`
- `0x18001f952`
- `0x18001f980`
- `0x180020010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180019904`
- `KERNEL32!HeapFree` at `0x180019904`

## string_xrefs

- `0x180019887`: `Invoked Prune Alert for protocol %x, %x`
- `0x18001981f`: `Invoked Join Alert for protocol %x, %x`

## pseudocode

```c
__int64 InvokeOutstandingCallbacks()
{
  ULONG v0; // r12d
  _DWORD *v1; // rdi
  __int64 v2; // rax
  __int64 result; // rax
  int v4; // r15d
  DWORD MostSpecificDestination; // eax
  int v6; // r14d
  void *v7; // rax
  __int64 v8; // r8
  const wchar_t *v9; // rdx
  DWORD v10; // eax
  ULONG InterfaceIndex; // esi
  __int64 v12; // rbx
  int IfEntry; // eax
  __int64 ProtocolEntry; // rax
  __int64 v15; // rbx
  DWORD v16; // eax
  DWORD v17; // eax
  _DWORD *v18; // [rsp+50h] [rbp-B0h] BYREF
  struct _RTM_NEXTHOP_INFO NextHopInfo; // [rsp+58h] [rbp-A8h] BYREF
  struct _RTM_NET_ADDRESS DestAddress; // [rsp+90h] [rbp-70h] BYREF
  struct _RTM_DEST_INFO DestInfo; // [rsp+B0h] [rbp-50h] BYREF
  int v22; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v23[2044]; // [rsp+114h] [rbp+14h] BYREF

  v18 = 0;
  v0 = 0;
  *(_QWORD *)&DestAddress.AddrBits[4] = 0;
  *(_DWORD *)&DestAddress.AddrBits[12] = 0;
  memset_0(&DestInfo, 0, sizeof(DestInfo));
  v22 = 0;
  memset(&NextHopInfo, 0, 52);
  memset_0(v23, 0, sizeof(v23));
  while ( 1 )
  {
    AcquireWriteLock(&qword_18002B9D8);
    v1 = qword_18002B9C8;
    if ( qword_18002B9C8 == &qword_18002B9C8 )
    {
      v1 = 0;
    }
    else
    {
      if ( *((LPVOID **)qword_18002B9C8 + 1) != &qword_18002B9C8
        || (v2 = *(_QWORD *)qword_18002B9C8, *(LPVOID *)(*(_QWORD *)qword_18002B9C8 + 8LL) != qword_18002B9C8) )
      {
        __fastfail(3u);
      }
      qword_18002B9C8 = *(LPVOID *)qword_18002B9C8;
      *(_QWORD *)(v2 + 8) = &qword_18002B9C8;
    }
    result = ReleaseWriteLock(&qword_18002B9D8);
    if ( !v1 )
      return result;
    *(_DWORD *)DestAddress.AddrBits = v1[4];
    *(_DWORD *)&DestAddress.AddressFamily = 2097154;
    v4 = 0;
    MostSpecificDestination = RtmGetMostSpecificDestination(g_hRtmHandle, &DestAddress, 0, 2u, &DestInfo);
    if ( MostSpecificDestination )
    {
      if ( qword_18002B8A8 )
      {
        LOWORD(v22) = 0;
        FormatRRASErrorString(
          &v22,
          L"InvokeOutstandingCallbacks : Failed to lookup route : %x",
          MostSpecificDestination);
        ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v22);
      }
      v6 = 0;
    }
    else
    {
      v6 = 1;
      v7 = (void *)SelectNextHop(&DestInfo);
      if ( !v7 )
      {
        if ( !qword_18002B8A8 )
          goto LABEL_34;
        v8 = 0;
        v9 = L"InvokeOutstandingCallbacks : Failed to select next hop : %x";
        goto LABEL_15;
      }
      v10 = RtmGetNextHopInfo(g_hRtmHandle, v7, &NextHopInfo);
      if ( v10 )
      {
        if ( qword_18002B8A8 )
        {
          v8 = v10;
          v9 = L"InvokeOutstandingCallbacks : Failed to get next hop info : %x";
LABEL_15:
          LOWORD(v22) = 0;
          FormatRRASErrorString(&v22, v9, v8);
          ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v22);
        }
      }
      else
      {
        InterfaceIndex = NextHopInfo.InterfaceIndex;
        v4 = 1;
        v12 = 32LL * (NextHopInfo.InterfaceIndex % dword_18002B92C);
        v0 = NextHopInfo.InterfaceIndex % dword_18002B92C;
        AcquireReadLock((char *)qword_18002B9E8 + v12 + 16);
        IfEntry = FindIfEntry((char *)qword_18002B9E8 + v12, InterfaceIndex, 0, &v18);
        if ( v18 && (IfEntry || v18[4] == InterfaceIndex) && (v1[8] != v18[4] || v1[9] != v18[5]) )
        {
          ProtocolEntry = GetProtocolEntry(&qword_18002B9A8, (unsigned int)v18[6], (unsigned int)v18[7]);
          v15 = ProtocolEntry;
          if ( ProtocolEntry )
          {
            if ( v1[10] )
            {
              if ( *(_QWORD *)(ProtocolEntry + 64) )
              {
                if ( qword_18002B8A8 )
                {
                  LOWORD(v22) = 0;
                  FormatRRASErrorString(
                    &v22,
                    L"Invoked Join Alert for protocol %x, %x",
                    *(unsigned int *)(ProtocolEntry + 16),
                    *(unsigned int *)(ProtocolEntry + 20));
                  ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(
                    gMgmEtwContext,
                    qword_18002B8A8,
                    &v22);
                }
                (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, int))(v15 + 64))(
                  (unsigned int)v1[4],
                  (unsigned int)v1[5],
                  (unsigned int)v1[6],
                  (unsigned int)v1[7],
                  1);
              }
            }
            else if ( *(_QWORD *)(ProtocolEntry + 56) )
            {
              if ( qword_18002B8A8 )
              {
                LOWORD(v22) = 0;
                FormatRRASErrorString(
                  &v22,
                  L"Invoked Prune Alert for protocol %x, %x",
                  *(unsigned int *)(ProtocolEntry + 16),
                  *(unsigned int *)(ProtocolEntry + 20));
                ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v22);
              }
              (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, int, _QWORD))(v15 + 56))(
                (unsigned int)v1[4],
                (unsigned int)v1[5],
                (unsigned int)v1[6],
                (unsigned int)v1[7],
                v1[8],
                v1[9],
                1,
                0);
            }
          }
        }
      }
    }
LABEL_34:
    HeapFree(hHeap, 0, v1);
    if ( v4 )
      ReleaseReadLock((char *)qword_18002B9E8 + 32 * v0 + 16);
    if ( v6 )
    {
      v16 = RtmReleaseDestInfo(g_hRtmHandle, &DestInfo);
      if ( v16 )
      {
        if ( qword_18002B8A8 )
        {
          LOWORD(v22) = 0;
          FormatRRASErrorString(&v22, L"Failed to release dest info : %x", v16);
          ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v22);
        }
      }
    }
    if ( v4 )
    {
      v17 = RtmReleaseNextHopInfo(g_hRtmHandle, &NextHopInfo);
      if ( v17 )
      {
        if ( qword_18002B8A8 )
        {
          LOWORD(v22) = 0;
          FormatRRASErrorString(&v22, L"Failed to release dest info : %x", v17);
          ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v22);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x18001958c  push    rbp
0x18001958e  push    rbx
0x18001958f  push    rsi
0x180019590  push    rdi
0x180019591  push    r12
0x180019593  push    r13
0x180019595  push    r14
0x180019597  push    r15
0x180019599  lea     rbp, [rsp-828h]
0x1800195a1  sub     rsp, 928h
0x1800195a8  mov     rax, cs:__security_cookie
0x1800195af  xor     rax, rsp
0x1800195b2  mov     [rbp+860h+var_50], rax
0x1800195b9  xor     r13d, r13d
0x1800195bc  lea     rcx, [rbp+860h+var_8B0]; void *
0x1800195c0  xor     edx, edx; Val
0x1800195c2  mov     [rsp+960h+var_910], r13
0x1800195c7  mov     r12d, r13d
0x1800195ca  mov     qword ptr [rbp+860h+DestAddress.AddrBits+4], r13
0x1800195ce  mov     dword ptr [rbp+860h+DestAddress.AddrBits+0Ch], r13d
0x1800195d2  lea     r8d, [r13+58h]; Size
0x1800195d6  call    memset_0
0x1800195db  xorps   xmm0, xmm0
0x1800195de  mov     [rbp+860h+var_850], r13d
0x1800195e2  xor     eax, eax
0x1800195e4  lea     rcx, [rbp+860h+var_84C]; void *
0x1800195e8  xor     edx, edx; Val
0x1800195ea  mov     dword ptr [rbp+860h+NextHopInfo.RemoteNextHop], eax
0x1800195ed  mov     r8d, 7FCh; Size
0x1800195f3  movups  xmmword ptr [rsp+960h+NextHopInfo.NextHopAddress.AddressFamily], xmm0
0x1800195f8  movups  xmmword ptr [rsp+960h+NextHopInfo.NextHopAddress.AddrBits+0Ch], xmm0
0x1800195fd  movups  xmmword ptr [rsp+960h+NextHopInfo.InterfaceIndex], xmm0
0x180019602  call    memset_0
0x180019607  lea     rbx, qword_18002B9C8
0x18001960e  lea     esi, [r13+2]
0x180019612  lea     rcx, qword_18002B9D8
0x180019619  call    AcquireWriteLock
0x18001961e  mov     rdi, cs:qword_18002B9C8
0x180019625  cmp     rdi, rbx
0x180019628  jnz     short loc_18001962F
0x18001962a  mov     rdi, r13
0x18001962d  jmp     short loc_180019651
0x18001962f  cmp     [rdi+8], rbx
0x180019633  jnz     loc_1800199EB
0x180019639  mov     rax, [rdi]
0x18001963c  cmp     [rax+8], rdi
0x180019640  jnz     loc_1800199EB
0x180019646  mov     cs:qword_18002B9C8, rax
0x18001964d  mov     [rax+8], rbx
0x180019651  lea     rcx, qword_18002B9D8
0x180019658  call    ReleaseWriteLock
0x18001965d  test    rdi, rdi
0x180019660  jz      loc_1800199F2
0x180019666  mov     eax, [rdi+10h]
0x180019669  lea     rdx, [rbp+860h+DestAddress]; DestAddress
0x18001966d  mov     rcx, cs:g_hRtmHandle; RtmRegHandle
0x180019674  mov     r9d, esi; TargetViews
0x180019677  mov     dword ptr [rbp+860h+DestAddress.AddrBits], eax
0x18001967a  xor     r8d, r8d; ProtocolId
0x18001967d  lea     rax, [rbp+860h+var_8B0]
0x180019681  mov     dword ptr [rbp+860h+DestAddress.AddressFamily], 200002h
0x180019688  mov     [rsp+960h+DestInfo], rax; DestInfo
0x18001968d  mov     r15d, r13d
0x180019690  call    RtmGetMostSpecificDestination
0x180019695  test    eax, eax
0x180019697  jz      short loc_1800196E0
0x180019699  cmp     cs:qword_18002B8A8, r13
0x1800196a0  jz      short loc_1800196D8
0x1800196a2  mov     r8d, eax
0x1800196a5  mov     word ptr [rbp+860h+var_850], r13w
0x1800196aa  lea     rdx, aInvokeoutstand_1; "InvokeOutstandingCallbacks : Failed to "...
0x1800196b1  lea     rcx, [rbp+860h+var_850]
0x1800196b5  call    FormatRRASErrorString
0x1800196ba  mov     rdx, cs:qword_18002B8A8
0x1800196c1  lea     r8, [rbp+860h+var_850]
0x1800196c5  mov     rcx, cs:gMgmEtwContext
0x1800196cc  mov     rax, cs:gMgmTemplateFunc
0x1800196d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800196d8  mov     r14d, r13d
0x1800196db  jmp     loc_1800198F8
0x1800196e0  lea     rcx, [rbp+860h+var_8B0]
0x1800196e4  mov     r14d, 1
0x1800196ea  call    SelectNextHop
0x1800196ef  test    rax, rax
0x1800196f2  jnz     short loc_18001973C
0x1800196f4  cmp     cs:qword_18002B8A8, r13
0x1800196fb  jz      loc_1800198F8
0x180019701  xor     r8d, r8d
0x180019704  lea     rdx, aInvokeoutstand; "InvokeOutstandingCallbacks : Failed to "...
0x18001970b  lea     rcx, [rbp+860h+var_850]
0x18001970f  mov     word ptr [rbp+860h+var_850], r13w
0x180019714  call    FormatRRASErrorString
0x180019719  mov     rdx, cs:qword_18002B8A8
0x180019720  lea     r8, [rbp+860h+var_850]
0x180019724  mov     rcx, cs:gMgmEtwContext
0x18001972b  mov     rax, cs:gMgmTemplateFunc
0x180019732  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019737  jmp     loc_1800198F8
0x18001973c  mov     rcx, cs:g_hRtmHandle; RtmRegHandle
0x180019743  lea     r8, [rsp+960h+NextHopInfo]; NextHopInfo
0x180019748  mov     rdx, rax; NextHopHandle
0x18001974b  call    RtmGetNextHopInfo
0x180019750  test    eax, eax
0x180019752  jz      short loc_18001976D
0x180019754  cmp     cs:qword_18002B8A8, r13
0x18001975b  jz      loc_1800198F8
0x180019761  mov     r8d, eax
0x180019764  lea     rdx, aInvokeoutstand_0; "InvokeOutstandingCallbacks : Failed to "...
0x18001976b  jmp     short loc_18001970B
0x18001976d  mov     esi, [rsp+960h+NextHopInfo.InterfaceIndex]
0x180019771  xor     edx, edx
0x180019773  mov     rcx, cs:qword_18002B9E8
0x18001977a  mov     eax, esi
0x18001977c  div     cs:dword_18002B92C
0x180019782  add     rcx, 10h
0x180019786  mov     r15d, r14d
0x180019789  mov     ebx, edx
0x18001978b  shl     rbx, 5
0x18001978f  add     rcx, rbx
0x180019792  mov     r12d, edx
0x180019795  call    AcquireReadLock
0x18001979a  mov     rcx, cs:qword_18002B9E8
0x1800197a1  lea     r9, [rsp+960h+var_910]
0x1800197a6  add     rcx, rbx
0x1800197a9  xor     r8d, r8d
0x1800197ac  mov     edx, esi
0x1800197ae  call    FindIfEntry
0x1800197b3  mov     rdx, [rsp+960h+var_910]
0x1800197b8  test    rdx, rdx
0x1800197bb  jz      loc_1800198EC
0x1800197c1  test    eax, eax
0x1800197c3  jnz     short loc_1800197CE
0x1800197c5  cmp     [rdx+10h], esi
0x1800197c8  jnz     loc_1800198EC
0x1800197ce  mov     eax, [rdx+10h]
0x1800197d1  cmp     [rdi+20h], eax
0x1800197d4  jnz     short loc_1800197E2
0x1800197d6  mov     eax, [rdx+14h]
0x1800197d9  cmp     [rdi+24h], eax
0x1800197dc  jz      loc_1800198EC
0x1800197e2  mov     r8d, [rdx+1Ch]
0x1800197e6  lea     rcx, qword_18002B9A8
0x1800197ed  mov     edx, [rdx+18h]
0x1800197f0  call    GetProtocolEntry
0x1800197f5  mov     rbx, rax
0x1800197f8  test    rax, rax
0x1800197fb  jz      loc_1800198EC
0x180019801  cmp     [rdi+28h], r13d
0x180019805  jz      short loc_180019873
0x180019807  cmp     [rax+40h], r13
0x18001980b  jz      loc_1800198EC
0x180019811  cmp     cs:qword_18002B8A8, r13
0x180019818  jz      short loc_180019855
0x18001981a  mov     word ptr [rbp+860h+var_850], r13w
0x18001981f  lea     rdx, aInvokedJoinAle; "Invoked Join Alert for protocol %x, %x"
0x180019826  mov     r9d, [rax+14h]
0x18001982a  lea     rcx, [rbp+860h+var_850]
0x18001982e  mov     r8d, [rax+10h]
0x180019832  call    FormatRRASErrorString
0x180019837  mov     rdx, cs:qword_18002B8A8
0x18001983e  lea     r8, [rbp+860h+var_850]
0x180019842  mov     rcx, cs:gMgmEtwContext
0x180019849  mov     rax, cs:gMgmTemplateFunc
0x180019850  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019855  mov     r9d, [rdi+1Ch]
0x180019859  mov     r8d, [rdi+18h]
0x18001985d  mov     edx, [rdi+14h]
0x180019860  mov     ecx, [rdi+10h]
0x180019863  mov     rax, [rbx+40h]
0x180019867  mov     dword ptr [rsp+960h+DestInfo], r14d
0x18001986c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019871  jmp     short loc_1800198EC
0x180019873  cmp     [rax+38h], r13
0x180019877  jz      short loc_1800198EC
0x180019879  cmp     cs:qword_18002B8A8, r13
0x180019880  jz      short loc_1800198BD
0x180019882  mov     word ptr [rbp+860h+var_850], r13w
0x180019887  lea     rdx, aInvokedPruneAl; "Invoked Prune Alert for protocol %x, %x"
0x18001988e  mov     r9d, [rax+14h]
0x180019892  lea     rcx, [rbp+860h+var_850]
0x180019896  mov     r8d, [rax+10h]
0x18001989a  call    FormatRRASErrorString
0x18001989f  mov     rdx, cs:qword_18002B8A8
0x1800198a6  lea     r8, [rbp+860h+var_850]
0x1800198aa  mov     rcx, cs:gMgmEtwContext
0x1800198b1  mov     rax, cs:gMgmTemplateFunc
0x1800198b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800198bd  mov     ecx, [rdi+24h]
0x1800198c0  mov     r9d, [rdi+1Ch]
0x1800198c4  mov     r8d, [rdi+18h]
0x1800198c8  mov     edx, [rdi+14h]
0x1800198cb  mov     rax, [rbx+38h]
0x1800198cf  mov     [rsp+960h+var_928], r13
0x1800198d4  mov     [rsp+960h+var_930], r14d
0x1800198d9  mov     [rsp+960h+var_938], ecx
0x1800198dd  mov     ecx, [rdi+20h]
0x1800198e0  mov     dword ptr [rsp+960h+DestInfo], ecx
0x1800198e4  mov     ecx, [rdi+10h]
0x1800198e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800198ec  lea     rbx, qword_18002B9C8
0x1800198f3  mov     esi, 2
0x1800198f8  mov     rcx, cs:hHeap; hHeap
0x1800198ff  mov     r8, rdi; lpMem
0x180019902  xor     edx, edx; dwFlags
0x180019904  call    cs:__imp_HeapFree
0x18001990a  test    r15d, r15d
0x18001990d  jz      short loc_180019929
0x18001990f  mov     rax, cs:qword_18002B9E8
0x180019916  add     rax, 10h
0x18001991a  mov     ecx, r12d
0x18001991d  shl     rcx, 5
0x180019921  add     rcx, rax
0x180019924  call    ReleaseReadLock
0x180019929  test    r14d, r14d
0x18001992c  jz      short loc_180019981
0x18001992e  mov     rcx, cs:g_hRtmHandle; RtmRegHandle
0x180019935  lea     rdx, [rbp+860h+var_8B0]; DestInfo
0x180019939  call    RtmReleaseDestInfo
0x18001993e  test    eax, eax
0x180019940  jz      short loc_180019981
0x180019942  cmp     cs:qword_18002B8A8, r13
0x180019949  jz      short loc_180019981
0x18001994b  mov     r8d, eax
0x18001994e  mov     word ptr [rbp+860h+var_850], r13w
0x180019953  lea     rdx, aFailedToReleas_3; "Failed to release dest info : %x"
0x18001995a  lea     rcx, [rbp+860h+var_850]
0x18001995e  call    FormatRRASErrorString
0x180019963  mov     rdx, cs:qword_18002B8A8
0x18001996a  lea     r8, [rbp+860h+var_850]
0x18001996e  mov     rcx, cs:gMgmEtwContext
0x180019975  mov     rax, cs:gMgmTemplateFunc
0x18001997c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019981  test    r15d, r15d
0x180019984  jz      loc_180019612
0x18001998a  mov     rcx, cs:g_hRtmHandle; RtmRegHandle
0x180019991  lea     rdx, [rsp+960h+NextHopInfo]; NextHopInfo
0x180019996  call    RtmReleaseNextHopInfo
0x18001999b  test    eax, eax
0x18001999d  jz      loc_180019612
0x1800199a3  cmp     cs:qword_18002B8A8, r13
0x1800199aa  jz      loc_180019612
0x1800199b0  mov     r8d, eax
0x1800199b3  mov     word ptr [rbp+860h+var_850], r13w
0x1800199b8  lea     rdx, aFailedToReleas_3; "Failed to release dest info : %x"
0x1800199bf  lea     rcx, [rbp+860h+var_850]
0x1800199c3  call    FormatRRASErrorString
0x1800199c8  mov     rdx, cs:qword_18002B8A8
0x1800199cf  lea     r8, [rbp+860h+var_850]
0x1800199d3  mov     rcx, cs:gMgmEtwContext
0x1800199da  mov     rax, cs:gMgmTemplateFunc
0x1800199e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800199e6  jmp     loc_180019612
0x1800199eb  mov     ecx, 3
0x1800199f0  int     29h; Win8: RtlFailFast(ecx)
0x1800199f2  mov     rcx, [rbp+860h+var_50]
0x1800199f9  xor     rcx, rsp; StackCookie
0x1800199fc  call    __security_check_cookie
0x180019a01  add     rsp, 928h
0x180019a08  pop     r15
0x180019a0a  pop     r14
0x180019a0c  pop     r13
0x180019a0e  pop     r12
0x180019a10  pop     rdi
0x180019a11  pop     rsi
0x180019a12  pop     rbx
0x180019a13  pop     rbp
0x180019a14  retn
```
