# CClientOxid::GetInfo(__MIDL_ILocalObjectExporter_0007 *)

- ea: `0x180042640`
- end: `0x180042ca4`
- name: `?GetInfo@CClientOxid@@QEAAJPEAU__MIDL_ILocalObjectExporter_0007@@@Z`
- size: `1636`
- prototype: `__int64 __fastcall(CClientOxid *__hidden this, struct __MIDL_ILocalObjectExporter_0007 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18001cce0`

## callees

- `0x180018344`
- `0x18002834c`
- `0x180034720`
- `0x180042640`
- `0x1800450dc`
- `0x18008e98c`
- `0x1800989b0`
- `0x180098b54`
- `0x1800ab2c8`
- `0x1800c013c`
- `0x1800c1320`
- `0x1800c4468`

## import_xrefs

- `RPCRT4!RpcBindingReset` at `0x180042875`
- `RPCRT4!RpcBindingReset` at `0x180042875`
- `RPCRT4!RpcBindingFree` at `0x18004286b`
- `RPCRT4!RpcBindingFree` at `0x1800428fa`
- `RPCRT4!RpcBindingFree` at `0x18004286b`
- `RPCRT4!RpcBindingFree` at `0x1800428fa`
- `RPCRT4!RpcBindingCopy` at `0x18004284a`
- `RPCRT4!RpcBindingCopy` at `0x18004284a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180042bf3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180042c5d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180042bf3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180042c5d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180042907`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180042969`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004297b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180042907`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180042969`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004297b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800427ab`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800427ab`

## string_xrefs

- `0x1800427ef`: `onecore\com\combase\rpcss\objex\orclnt.cxx`
- `0x1800428ea`: `onecore\com\combase\rpcss\objex\orclnt.cxx`
- `0x180042956`: `onecore\com\combase\rpcss\objex\orclnt.cxx`
- `0x1800429d4`: `onecore\com\combase\rpcss\objex\orclnt.cxx`
- `0x180042a53`: `onecore\com\combase\rpcss\objex\orclnt.cxx`
- `0x180042a8c`: `onecore\com\combase\rpcss\objex\orclnt.cxx`
- `0x180042b33`: `onecore\com\combase\rpcss\objex\orclnt.cxx`
- `0x180042b5e`: `onecore\com\combase\rpcss\objex\orclnt.cxx`
- `0x180042b82`: `onecore\com\combase\rpcss\objex\orclnt.cxx`
- `0x180042c01`: `onecore\com\combase\rpcss\objex\orclnt.cxx`
- `0x180042c30`: `onecore\com\combase\rpcss\objex\orclnt.cxx`
- `0x180042c7d`: `onecore\com\combase\rpcss\objex\orclnt.cxx`

## pseudocode

```c
unsigned int __fastcall CClientOxid::GetInfo(CClientOxid *this, struct __MIDL_ILocalObjectExporter_0007 *a2)
{
  unsigned __int16 *v2; // rbx
  unsigned int v5; // eax
  __int64 v6; // r8
  __int64 v7; // rcx
  char *v8; // r15
  unsigned __int16 *v9; // rbx
  unsigned __int16 *v10; // rcx
  unsigned __int16 *MatchingProtseq; // rax
  __int64 v12; // rcx
  __int64 v13; // rsi
  unsigned int v14; // eax
  unsigned int v15; // edi
  RPC_BINDING_HANDLE *v16; // rcx
  unsigned int v17; // eax
  RPC_BINDING_HANDLE *v18; // rcx
  unsigned int v19; // eax
  RPC_BINDING_HANDLE *v20; // rax
  wil::details::in1diag3 *v21; // rcx
  __int64 v22; // rdx
  __int16 v24; // cx
  unsigned __int16 v25; // ax
  __int64 v26; // rdx
  __int64 v27; // rax
  unsigned int StringBinding; // ebx
  int v29; // eax
  unsigned int v30; // [rsp+28h] [rbp-79h]
  struct tagDUALSTRINGARRAY *v31; // [rsp+50h] [rbp-51h] BYREF
  char v32; // [rsp+58h] [rbp-49h]
  void **v33; // [rsp+68h] [rbp-39h] BYREF
  unsigned int v34; // [rsp+70h] [rbp-31h]
  int v35; // [rsp+80h] [rbp-21h]
  int v36; // [rsp+90h] [rbp-11h]
  __int64 v37; // [rsp+98h] [rbp-9h]
  __int128 v38; // [rsp+A8h] [rbp+7h]
  __int64 v39; // [rsp+B8h] [rbp+17h]
  __int64 v40; // [rsp+C0h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+100h] [rbp+5Fh]
  struct tagDUALSTRINGARRAY *lpMem; // [rsp+108h] [rbp+67h]
  RPC_BINDING_HANDLE DestinationBinding; // [rsp+118h] [rbp+77h] BYREF

  v2 = (unsigned __int16 *)*((_QWORD *)this + 17);
  if ( !v2 )
    return wil::details::in1diag3::Log_Win32(
             retaddr,
             (void *)0xC7,
             (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\orclnt.cxx",
             (const char *)0x776,
             v30);
  v5 = *v2;
  if ( v5 < 4 )
    return wil::details::in1diag3::Log_Win32(
             retaddr,
             (void *)0xC7,
             (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\orclnt.cxx",
             (const char *)0x776,
             v30);
  v6 = v2[1];
  if ( (unsigned int)v6 < 2 || (int)v6 > (int)(v5 - 2) || v2[v6 + 1] || v2[v6] || v2[*v2 + 1] || v2[*v2] )
    return wil::details::in1diag3::Log_Win32(
             retaddr,
             (void *)0xC7,
             (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\orclnt.cxx",
             (const char *)0x776,
             v30);
  v7 = *((unsigned __int16 *)this + 116);
  if ( !(_WORD)v7 )
  {
    v24 = 16;
    goto LABEL_63;
  }
  if ( (_WORD)v7 == 33 )
  {
    v24 = 33;
LABEL_63:
    v25 = v2[2];
    v9 = v2 + 2;
    if ( !v25 )
    {
LABEL_68:
      if ( dword_18014E4B8 || gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v30 = 0;
        ComTraceMessage(0xFFFFFFFFLL, "onecore\\com\\combase\\rpcss\\objex\\orclnt.cxx", "CClientOxid::GetInfo", 210);
      }
      v21 = retaddr;
      v22 = 211;
      return wil::details::in1diag3::Log_Win32(
               v21,
               (void *)v22,
               (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\orclnt.cxx",
               (const char *)0x776,
               v30);
    }
    while ( v25 != v24 )
    {
      for ( ; *v9; ++v9 )
        ;
      v25 = v9[1];
      ++v9;
      if ( !v25 )
        goto LABEL_68;
    }
    if ( !*((_QWORD *)this + 25) )
    {
      v21 = retaddr;
      v22 = 217;
      return wil::details::in1diag3::Log_Win32(
               v21,
               (void *)v22,
               (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\orclnt.cxx",
               (const char *)0x776,
               v30);
    }
    v8 = (char *)this + 136;
    goto LABEL_76;
  }
  if ( *((_QWORD *)this + 25) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v7);
  v8 = (char *)this + 136;
  if ( *((_WORD *)this + 117) != 0xFFFF )
  {
    v9 = (unsigned __int16 *)(*(_QWORD *)v8 + 2 * (*((unsigned __int16 *)this + 117) + 2LL));
    goto LABEL_54;
  }
  v10 = (unsigned __int16 *)*((_QWORD *)this + 30);
  v9 = 0;
  if ( !v10 )
  {
    v12 = *(_QWORD *)v8;
LABEL_19:
    v33 = &CTestBindingPPing::`vftable';
    v34 = 0;
    v40 = v12 + 4;
    v35 = 0;
    v13 = 0;
    v36 = 1722;
    v37 = 0;
    v38 = 0;
    v39 = 0;
    ReleaseSRWLockExclusive(&gpClientLock);
LABEL_20:
    v14 = CParallelPing::Ping((CParallelPing *)&v33);
    v15 = v14;
    if ( gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      v30 = 3;
      ComTraceMessage(v14, "onecore\\com\\combase\\rpcss\\objex\\orclnt.cxx", "CClientOxid::GetInfo", 254);
    }
    if ( v15 == 1717 && !(_DWORD)v13 && v34 )
    {
      while ( 1 )
      {
        DestinationBinding = 0;
        v16 = *((_QWORD *)&v38 + 1) ? *(RPC_BINDING_HANDLE **)(*((_QWORD *)&v38 + 1) + 8 * v13) : 0LL;
        v17 = RpcBindingCopy(*v16, &DestinationBinding);
        if ( v17 )
          break;
        if ( *((_QWORD *)&v38 + 1) )
          v18 = *(RPC_BINDING_HANDLE **)(*((_QWORD *)&v38 + 1) + 8 * v13);
        else
          v18 = 0;
        RpcBindingFree(v18);
        v19 = RpcBindingReset(DestinationBinding);
        if ( v19 )
        {
          if ( dword_18014E4B8 || gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v30 = 0;
            ComTraceMessage(v19, "onecore\\com\\combase\\rpcss\\objex\\orclnt.cxx", "CClientOxid::GetInfo", 273);
          }
          RpcBindingFree(&DestinationBinding);
          AcquireSRWLockExclusive(&gpClientLock);
          goto LABEL_53;
        }
        v20 = (RPC_BINDING_HANDLE *)*((_QWORD *)&v38 + 1);
        if ( *((_QWORD *)&v38 + 1) )
          v20 = *(RPC_BINDING_HANDLE **)(*((_QWORD *)&v38 + 1) + 8 * v13);
        v13 = (unsigned int)(v13 + 1);
        *v20 = DestinationBinding;
        if ( (unsigned int)v13 >= v34 )
        {
          v13 = 1;
          goto LABEL_20;
        }
      }
      if ( dword_18014E4B8 || gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v30 = 0;
        ComTraceMessage(v17, "onecore\\com\\combase\\rpcss\\objex\\orclnt.cxx", "CClientOxid::GetInfo", 265);
      }
      AcquireSRWLockExclusive(&gpClientLock);
    }
    else
    {
      AcquireSRWLockExclusive(&gpClientLock);
      if ( !v15 )
      {
        v9 = *(unsigned __int16 **)(v39 + 16);
        if ( gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          v30 = 3;
          ComTraceMessage(0xFFFFFFFFLL, "onecore\\com\\combase\\rpcss\\objex\\orclnt.cxx", "CClientOxid::GetInfo", 295);
        }
        *((_WORD *)this + 117) = ((unsigned int)((_DWORD)v9 - *(_DWORD *)v8) - 4LL) >> 1;
      }
    }
LABEL_53:
    CParallelPing::Reset((CParallelPing *)&v33);
    CParallelPing::~CParallelPing((CParallelPing *)&v33);
LABEL_54:
    if ( !v9 )
    {
      if ( dword_18014E4B8 || gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v30 = 0;
        ComTraceMessage(0xFFFFFFFFLL, "onecore\\com\\combase\\rpcss\\objex\\orclnt.cxx", "CClientOxid::GetInfo", 306);
      }
      v21 = retaddr;
      v22 = 308;
      return wil::details::in1diag3::Log_Win32(
               v21,
               (void *)v22,
               (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\orclnt.cxx",
               (const char *)0x776,
               v30);
    }
    goto LABEL_76;
  }
  MatchingProtseq = FindMatchingProtseq(v10, *((_WORD *)this + 116), (unsigned __int16 *)(*(_QWORD *)v8 + 4LL));
  v12 = *(_QWORD *)v8;
  v9 = MatchingProtseq;
  if ( !MatchingProtseq )
    goto LABEL_19;
  *((_WORD *)this + 117) = ((__int64)MatchingProtseq - v12 - 4) >> 1;
LABEL_76:
  v26 = *(_QWORD *)v8;
  lpMem = 0;
  v31 = 0;
  v27 = *(unsigned __int16 *)(v26 + 2);
  v32 = 1;
  StringBinding = GetStringBinding(v9, (unsigned __int16 *)(v26 + 2 * v27 + 4), &v31);
  if ( v32 )
    lpMem = v31;
  if ( StringBinding )
  {
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x140,
      (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\orclnt.cxx",
      (const char *)StringBinding,
      v30);
  }
  else
  {
    v29 = CopyOxidInfo((CClientOxid *)((char *)this + 72), a2, 1);
    LOWORD(StringBinding) = v29;
    if ( v29 >= 0 )
    {
      *((_QWORD *)a2 + 8) = lpMem;
      return 0;
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x148,
      (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\orclnt.cxx",
      (const char *)(unsigned int)v29,
      v30);
    StringBinding = (unsigned __int16)StringBinding;
  }
  if ( lpMem )
    HeapFree(g_hHeap, 0, lpMem);
  return StringBinding;
}

```

## disassembly

```asm
0x180042640  mov     r11, rsp
0x180042643  push    rbp
0x180042644  push    rbx
0x180042645  push    r12
0x180042647  push    r13
0x180042649  push    r14
0x18004264b  lea     rbp, [r11-5Fh]
0x18004264f  sub     rsp, 0D0h
0x180042656  mov     rbx, [rcx+88h]
0x18004265d  mov     r13, rdx
0x180042660  mov     r14, rcx
0x180042663  test    rbx, rbx
0x180042666  jz      loc_180042C79
0x18004266c  movzx   eax, word ptr [rbx]
0x18004266f  cmp     eax, 4
0x180042672  jb      loc_180042C79
0x180042678  movzx   r8d, word ptr [rbx+2]
0x18004267d  cmp     r8d, 2
0x180042681  jb      loc_180042C79
0x180042687  mov     edx, eax
0x180042689  add     eax, 0FFFFFFFEh
0x18004268c  cmp     r8d, eax
0x18004268f  jg      loc_180042C79
0x180042695  cmp     word ptr [rbx+r8*2+2], 0
0x18004269c  jnz     loc_180042C79
0x1800426a2  cmp     word ptr [rbx+r8*2], 0
0x1800426a8  jnz     loc_180042C79
0x1800426ae  cmp     word ptr [rbx+rdx*2+2], 0
0x1800426b4  jnz     loc_180042C79
0x1800426ba  cmp     word ptr [rbx+rdx*2], 0
0x1800426bf  jnz     loc_180042C79
0x1800426c5  movzx   ecx, word ptr [rcx+0E8h]
0x1800426cc  mov     [r11-30h], rdi
0x1800426d0  xor     edi, edi
0x1800426d2  mov     [r11-38h], r15
0x1800426d6  cmp     di, cx
0x1800426d9  jz      loc_180042ACA
0x1800426df  cmp     cx, 21h ; '!'
0x1800426e3  jz      loc_180042AC3
0x1800426e9  cmp     [r14+0C8h], rdi
0x1800426f0  jz      short loc_1800426F7
0x1800426f2  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800426f7  movzx   eax, word ptr [r14+0EAh]
0x1800426ff  lea     r15, [r14+88h]
0x180042706  mov     ecx, 0FFFFh
0x18004270b  cmp     ax, cx
0x18004270e  jz      short loc_180042722
0x180042710  mov     ebx, eax
0x180042712  mov     rax, [r15]
0x180042715  add     rbx, 2
0x180042719  lea     rbx, [rax+rbx*2]
0x18004271d  jmp     loc_180042A1D
0x180042722  mov     rcx, [r14+0F0h]; unsigned __int16 *
0x180042729  mov     rbx, rdi
0x18004272c  test    rcx, rcx
0x18004272f  jz      short loc_180042767
0x180042731  mov     r8, [r15]
0x180042734  movzx   edx, word ptr [r14+0E8h]; unsigned __int16
0x18004273c  add     r8, 4; unsigned __int16 *
0x180042740  call    ?FindMatchingProtseq@@YAPEAGPEAGG0@Z; FindMatchingProtseq(ushort *,ushort,ushort *)
0x180042745  mov     rcx, [r15]
0x180042748  mov     rbx, rax
0x18004274b  test    rax, rax
0x18004274e  jz      short loc_18004276A
0x180042750  sub     rax, rcx
0x180042753  sub     rax, 4
0x180042757  sar     rax, 1
0x18004275a  mov     [r14+0EAh], ax
0x180042762  jmp     loc_180042BA0
0x180042767  mov     rcx, [r15]
0x18004276a  lea     rax, ??_7CTestBindingPPing@@6B@; const CTestBindingPPing::`vftable'
0x180042771  mov     [rsp+0F0h+arg_8], rsi
0x180042779  mov     [rbp+57h+var_90], rax
0x18004277d  xorps   xmm0, xmm0
0x180042780  lea     rax, [rcx+4]
0x180042784  mov     [rbp+57h+var_88], edi
0x180042787  lea     rcx, ?gpClientLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18004278e  mov     [rbp+57h+var_38], rax
0x180042792  mov     [rbp+57h+var_78], edi
0x180042795  mov     esi, edi
0x180042797  mov     [rbp+57h+var_68], 6BAh
0x18004279e  mov     [rbp+57h+var_60], rdi
0x1800427a2  movdqa  [rbp+57h+var_50], xmm0
0x1800427a7  mov     [rbp+57h+var_40], rdi
0x1800427ab  call    cs:__imp_ReleaseSRWLockExclusive
0x1800427b1  lea     rcx, [rbp+57h+var_90]; this
0x1800427b5  call    ?Ping@CParallelPing@@QEAAJXZ; CParallelPing::Ping(void)
0x1800427ba  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x1800427c1  mov     edi, eax
0x1800427c3  jz      short loc_180042805
0x1800427c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800427cc  test    byte ptr [rcx+1Ch], 8
0x1800427d0  jz      short loc_180042805
0x1800427d2  mov     dword ptr [rsp+0F0h+var_C0], eax
0x1800427d6  lea     r8, aCclientoxidGet; "CClientOxid::GetInfo"
0x1800427dd  lea     rax, aWinerror; "%!WINERROR!"
0x1800427e4  mov     r9d, 0FEh
0x1800427ea  mov     [rsp+0F0h+var_C8], rax
0x1800427ef  lea     rdx, aOnecoreComComb_0; "onecore\\com\\combase\\rpcss\\objex\\or"...
0x1800427f6  mov     ecx, edi
0x1800427f8  mov     [rsp+0F0h+var_D0], 3
0x180042800  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x180042805  cmp     edi, 6B5h
0x18004280b  jnz     loc_180042974
0x180042811  test    esi, esi
0x180042813  jnz     loc_180042974
0x180042819  cmp     [rbp+57h+var_88], esi
0x18004281c  jbe     loc_180042974
0x180042822  mov     rax, qword ptr [rbp+57h+var_50+8]
0x180042826  lea     rdi, ds:0[rsi*8]
0x18004282e  mov     [rbp+57h+DestinationBinding], 0
0x180042836  test    rax, rax
0x180042839  jz      short loc_180042841
0x18004283b  mov     rcx, [rax+rdi]
0x18004283f  jmp     short loc_180042843
0x180042841  xor     ecx, ecx
0x180042843  mov     rcx, [rcx]; SourceBinding
0x180042846  lea     rdx, [rbp+57h+DestinationBinding]; DestinationBinding
0x18004284a  call    cs:__imp_RpcBindingCopy
0x180042850  mov     ecx, eax
0x180042852  test    eax, eax
0x180042854  jnz     loc_180042912
0x18004285a  mov     rax, qword ptr [rbp+57h+var_50+8]
0x18004285e  test    rax, rax
0x180042861  jz      short loc_180042869
0x180042863  mov     rcx, [rax+rdi]
0x180042867  jmp     short loc_18004286B
0x180042869  xor     ecx, ecx; Binding
0x18004286b  call    cs:__imp_RpcBindingFree
0x180042871  mov     rcx, [rbp+57h+DestinationBinding]; Binding
0x180042875  call    cs:__imp_RpcBindingReset
0x18004287b  mov     ecx, eax
0x18004287d  test    eax, eax
0x18004287f  jnz     short loc_1800428A6
0x180042881  mov     rax, qword ptr [rbp+57h+var_50+8]
0x180042885  mov     rcx, [rbp+57h+DestinationBinding]
0x180042889  test    rax, rax
0x18004288c  jz      short loc_180042892
0x18004288e  mov     rax, [rax+rdi]
0x180042892  inc     esi
0x180042894  mov     [rax], rcx
0x180042897  cmp     esi, [rbp+57h+var_88]
0x18004289a  jb      short loc_180042822
0x18004289c  mov     esi, 1
0x1800428a1  jmp     loc_1800427B1
0x1800428a6  mov     eax, cs:dword_18014E4B8
0x1800428ac  test    eax, eax
0x1800428ae  jnz     short loc_1800428C5
0x1800428b0  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800428b6  jz      short loc_1800428F6
0x1800428b8  mov     rax, cs:WPP_GLOBAL_Control
0x1800428bf  test    byte ptr [rax+1Ch], 1
0x1800428c3  jz      short loc_1800428F6
0x1800428c5  mov     dword ptr [rsp+0F0h+var_C0], ecx
0x1800428c9  lea     rax, aWinerror; "%!WINERROR!"
0x1800428d0  mov     [rsp+0F0h+var_C8], rax
0x1800428d5  lea     r8, aCclientoxidGet; "CClientOxid::GetInfo"
0x1800428dc  mov     r9d, 111h
0x1800428e2  mov     [rsp+0F0h+var_D0], 0
0x1800428ea  lea     rdx, aOnecoreComComb_0; "onecore\\com\\combase\\rpcss\\objex\\or"...
0x1800428f1  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x1800428f6  lea     rcx, [rbp+57h+DestinationBinding]; Binding
0x1800428fa  call    cs:__imp_RpcBindingFree
0x180042900  lea     rcx, ?gpClientLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x180042907  call    cs:__imp_AcquireSRWLockExclusive
0x18004290d  jmp     loc_180042A01
0x180042912  mov     eax, cs:dword_18014E4B8
0x180042918  test    eax, eax
0x18004291a  jnz     short loc_180042931
0x18004291c  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x180042922  jz      short loc_180042962
0x180042924  mov     rax, cs:WPP_GLOBAL_Control
0x18004292b  test    byte ptr [rax+1Ch], 1
0x18004292f  jz      short loc_180042962
0x180042931  mov     dword ptr [rsp+0F0h+var_C0], ecx
0x180042935  lea     rax, aWinerror; "%!WINERROR!"
0x18004293c  mov     [rsp+0F0h+var_C8], rax
0x180042941  lea     r8, aCclientoxidGet; "CClientOxid::GetInfo"
0x180042948  mov     r9d, 109h
0x18004294e  mov     [rsp+0F0h+var_D0], 0
0x180042956  lea     rdx, aOnecoreComComb_0; "onecore\\com\\combase\\rpcss\\objex\\or"...
0x18004295d  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x180042962  lea     rcx, ?gpClientLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x180042969  call    cs:__imp_AcquireSRWLockExclusive
0x18004296f  jmp     loc_180042A01
0x180042974  lea     rcx, ?gpClientLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18004297b  call    cs:__imp_AcquireSRWLockExclusive
0x180042981  test    edi, edi
0x180042983  jnz     loc_180042A01
0x180042989  cmp     cs:?gfEnableTracing@@3HA, edi; int gfEnableTracing
0x18004298f  mov     rax, [rbp+57h+var_40]
0x180042993  mov     rbx, [rax+10h]
0x180042997  jz      short loc_1800429ED
0x180042999  mov     rax, cs:WPP_GLOBAL_Control
0x1800429a0  test    byte ptr [rax+1Ch], 8
0x1800429a4  jz      short loc_1800429ED
0x1800429a6  lea     rax, [rbx+2]
0x1800429aa  test    rbx, rbx
0x1800429ad  jnz     short loc_1800429B6
0x1800429af  lea     rax, Class
0x1800429b6  mov     [rsp+0F0h+var_C0], rax
0x1800429bb  lea     r8, aCclientoxidGet; "CClientOxid::GetInfo"
0x1800429c2  lea     rax, aWinnerWs; "Winner:%ws"
0x1800429c9  mov     r9d, 127h
0x1800429cf  mov     [rsp+0F0h+var_C8], rax
0x1800429d4  lea     rdx, aOnecoreComComb_0; "onecore\\com\\combase\\rpcss\\objex\\or"...
0x1800429db  mov     ecx, 0FFFFFFFFh
0x1800429e0  mov     [rsp+0F0h+var_D0], 3
0x1800429e8  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x1800429ed  mov     eax, ebx
0x1800429ef  sub     eax, [r15]
0x1800429f2  sub     rax, 4
0x1800429f6  sar     rax, 1
0x1800429f9  mov     [r14+0EAh], ax
0x180042a01  lea     rcx, [rbp+57h+var_90]; this
0x180042a05  call    ?Reset@CParallelPing@@QEAAXXZ; CParallelPing::Reset(void)
0x180042a0a  lea     rcx, [rbp+57h+var_90]; this
0x180042a0e  call    ??1CParallelPing@@QEAA@XZ; CParallelPing::~CParallelPing(void)
0x180042a13  mov     rsi, [rsp+0F0h+arg_8]
0x180042a1b  xor     edi, edi
0x180042a1d  test    rbx, rbx
0x180042a20  jnz     loc_180042BA0
0x180042a26  mov     eax, cs:dword_18014E4B8
0x180042a2c  test    eax, eax
0x180042a2e  jnz     short loc_180042A45
0x180042a30  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x180042a36  jz      short loc_180042A88
0x180042a38  mov     rax, cs:WPP_GLOBAL_Control
0x180042a3f  test    byte ptr [rax+1Ch], 1
0x180042a43  jz      short loc_180042A88
0x180042a45  mov     rax, [r15]
0x180042a48  lea     r8, aCclientoxidGet; "CClientOxid::GetInfo"
0x180042a4f  add     rax, 6
0x180042a53  lea     rdx, aOnecoreComComb_0; "onecore\\com\\combase\\rpcss\\objex\\or"...
0x180042a5a  mov     [rsp+38h], rax
0x180042a5f  mov     r9d, 132h
0x180042a65  mov     rax, [r14+18h]
0x180042a69  mov     ecx, 0FFFFFFFFh
0x180042a6e  mov     [rsp+0F0h+var_C0], rax
0x180042a73  lea     rax, aUnableToFindAB; "Unable to find a binding for Client OXI"...
0x180042a7a  mov     [rsp+0F0h+var_C8], rax
0x180042a7f  mov     [rsp+0F0h+var_D0], edi; unsigned int
0x180042a83  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x180042a88  mov     rcx, [rbp+5Fh]; this
0x180042a8c  lea     r8, aOnecoreComComb_0; "onecore\\com\\combase\\rpcss\\objex\\or"...
0x180042a93  mov     r9d, 776h; char *
0x180042a99  mov     edx, 134h; void *
0x180042a9e  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x180042aa3  mov     r15, [rsp+0F0h+var_30]
0x180042aab  mov     rdi, [rsp+0C8h]
0x180042ab3  add     rsp, 0D0h
0x180042aba  pop     r14
0x180042abc  pop     r13
0x180042abe  pop     r12
0x180042ac0  pop     rbx
0x180042ac1  pop     rbp
0x180042ac2  retn
0x180042ac3  mov     ecx, 21h ; '!'
0x180042ac8  jmp     short loc_180042ACF
0x180042aca  mov     ecx, 10h
0x180042acf  movzx   eax, word ptr [rbx+4]
0x180042ad3  add     rbx, 4
0x180042ad7  test    ax, ax
0x180042ada  jz      short loc_180042B06
0x180042adc  nop     dword ptr [rax+00h]
0x180042ae0  cmp     ax, cx
0x180042ae3  jz      loc_180042B75
0x180042ae9  cmp     [rbx], di
0x180042aec  jz      short loc_180042AF9
0x180042aee  xchg    ax, ax
0x180042af0  add     rbx, 2
0x180042af4  cmp     [rbx], di
0x180042af7  jnz     short loc_180042AF0
0x180042af9  movzx   eax, word ptr [rbx+2]
0x180042afd  add     rbx, 2
0x180042b01  test    ax, ax
0x180042b04  jnz     short loc_180042AE0
0x180042b06  mov     eax, cs:dword_18014E4B8
0x180042b0c  test    eax, eax
0x180042b0e  jnz     short loc_180042B25
0x180042b10  cmp     cs:?gfEnableTracing@@3HA, edi; int gfEnableTracing
0x180042b16  jz      short loc_180042B5A
0x180042b18  mov     rax, cs:WPP_GLOBAL_Control
0x180042b1f  test    byte ptr [rax+1Ch], 1
0x180042b23  jz      short loc_180042B5A
0x180042b25  movzx   eax, cx
0x180042b28  lea     r8, aCclientoxidGet; "CClientOxid::GetInfo"
0x180042b2f  mov     dword ptr [rsp+0F0h+var_C0], eax
0x180042b33  lea     rdx, aOnecoreComComb_0; "onecore\\com\\combase\\rpcss\\objex\\or"...
0x180042b3a  lea     rax, aUnableToFindMa; "Unable to find matching protseq for: %d"
0x180042b41  mov     r9d, 0D2h
0x180042b47  mov     [rsp+0F0h+var_C8], rax
0x180042b4c  mov     ecx, 0FFFFFFFFh
0x180042b51  mov     [rsp+0F0h+var_D0], edi
0x180042b55  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x180042b5a  mov     rcx, [rbp+5Fh]
0x180042b5e  lea     r8, aOnecoreComComb_0; "onecore\\com\\combase\\rpcss\\objex\\or"...
0x180042b65  mov     r9d, 776h
0x180042b6b  mov     edx, 0D3h
0x180042b70  jmp     loc_180042A9E
  ... truncated ...
```
