# CClientOxid::GetInfo(__MIDL_ILocalObjectExporter_0007 *)

- ea: `0x180052540`
- end: `0x180052be1`
- name: `?GetInfo@CClientOxid@@QEAAJPEAU__MIDL_ILocalObjectExporter_0007@@@Z`
- size: `1697`
- prototype: `int(CClientOxid *__hidden this, struct __MIDL_ILocalObjectExporter_0007 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180031be0`

## callees

- `0x18001c624`
- `0x180035b70`
- `0x1800366bc`
- `0x1800375e0`
- `0x1800405c0`
- `0x180052540`
- `0x180095c0c`
- `0x18009dfb4`
- `0x18009e160`
- `0x1800b023c`
- `0x1800c6e78`
- `0x1800ca28c`

## import_xrefs

- `RPCRT4!RpcBindingReset` at `0x18005278f`
- `RPCRT4!RpcBindingReset` at `0x18005278f`
- `RPCRT4!RpcBindingFree` at `0x18005277f`
- `RPCRT4!RpcBindingFree` at `0x18005281e`
- `RPCRT4!RpcBindingFree` at `0x18005277f`
- `RPCRT4!RpcBindingFree` at `0x18005281e`
- `RPCRT4!RpcBindingCopy` at `0x180052758`
- `RPCRT4!RpcBindingCopy` at `0x180052758`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180052b23`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180052b93`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180052b23`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180052b93`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180052883`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005289b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180052883`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005289b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800526ab`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800526ab`

## string_xrefs

- `0x1800526f5`: `onecore\com\combase\rpcss\objex\orclnt.cxx`
- `0x18005280e`: `onecore\com\combase\rpcss\objex\orclnt.cxx`
- `0x180052870`: `onecore\com\combase\rpcss\objex\orclnt.cxx`
- `0x1800528f6`: `onecore\com\combase\rpcss\objex\orclnt.cxx`
- `0x180052982`: `onecore\com\combase\rpcss\objex\orclnt.cxx`
- `0x1800529bb`: `onecore\com\combase\rpcss\objex\orclnt.cxx`
- `0x180052a63`: `onecore\com\combase\rpcss\objex\orclnt.cxx`
- `0x180052a8e`: `onecore\com\combase\rpcss\objex\orclnt.cxx`
- `0x180052ab2`: `onecore\com\combase\rpcss\objex\orclnt.cxx`
- `0x180052b37`: `onecore\com\combase\rpcss\objex\orclnt.cxx`
- `0x180052b66`: `onecore\com\combase\rpcss\objex\orclnt.cxx`
- `0x180052bb9`: `onecore\com\combase\rpcss\objex\orclnt.cxx`

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
  unsigned int v14; // edi
  RPC_BINDING_HANDLE *v15; // rcx
  unsigned int v16; // eax
  RPC_BINDING_HANDLE *v17; // rcx
  unsigned int v18; // eax
  RPC_BINDING_HANDLE *v19; // rax
  const WCHAR *v20; // rax
  wil::details::in1diag3 *v21; // rcx
  __int64 v22; // rdx
  unsigned __int16 v24; // cx
  unsigned __int16 v25; // ax
  __int64 v26; // rdx
  __int64 v27; // rax
  unsigned int StringBinding; // ebx
  int v29; // eax
  unsigned int v30[2]; // [rsp+28h] [rbp-79h]
  struct tagDUALSTRINGARRAY *v31; // [rsp+50h] [rbp-51h] BYREF
  char v32; // [rsp+58h] [rbp-49h]
  void **v33; // [rsp+68h] [rbp-39h] BYREF
  unsigned int v34; // [rsp+70h] [rbp-31h]
  int v35; // [rsp+80h] [rbp-21h]
  int v36; // [rsp+90h] [rbp-11h]
  __int64 v37; // [rsp+98h] [rbp-9h] BYREF
  __int128 v38; // [rsp+A8h] [rbp+7h] BYREF
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
             v30[0]);
  v5 = *v2;
  if ( v5 < 4 )
    return wil::details::in1diag3::Log_Win32(
             retaddr,
             (void *)0xC7,
             (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\orclnt.cxx",
             (const char *)0x776,
             v30[0]);
  v6 = v2[1];
  if ( (unsigned int)v6 < 2 || (int)v6 > (int)(v5 - 2) || v2[v6 + 1] || v2[v6] || v2[*v2 + 1] || v2[*v2] )
    return wil::details::in1diag3::Log_Win32(
             retaddr,
             (void *)0xC7,
             (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\orclnt.cxx",
             (const char *)0x776,
             v30[0]);
  v7 = *((unsigned __int16 *)this + 116);
  if ( !(_WORD)v7 )
  {
    v24 = 16;
    goto LABEL_65;
  }
  if ( (_WORD)v7 == 33 )
  {
    v24 = 33;
LABEL_65:
    v25 = v2[2];
    v9 = v2 + 2;
    if ( !v25 )
    {
LABEL_70:
      if ( dword_1801574B8 || gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v30[0] = 0;
        ComTraceMessage(
          0xFFFFFFFFLL,
          "onecore\\com\\combase\\rpcss\\objex\\orclnt.cxx",
          "CClientOxid::GetInfo",
          210,
          *(_QWORD *)v30,
          L"Unable to find matching protseq for: %d",
          v24);
      }
      v21 = retaddr;
      v22 = 211;
      return wil::details::in1diag3::Log_Win32(
               v21,
               (void *)v22,
               (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\orclnt.cxx",
               (const char *)0x776,
               v30[0]);
    }
    while ( v25 != v24 )
    {
      for ( ; *v9; ++v9 )
        ;
      v25 = v9[1];
      ++v9;
      if ( !v25 )
        goto LABEL_70;
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
               v30[0]);
    }
    v8 = (char *)this + 136;
    goto LABEL_78;
  }
  if ( *((_QWORD *)this + 25) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v7);
  v8 = (char *)this + 136;
  if ( *((_WORD *)this + 117) != 0xFFFF )
  {
    v9 = (unsigned __int16 *)(*(_QWORD *)v8 + 2 * (*((unsigned __int16 *)this + 117) + 2LL));
    goto LABEL_56;
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
    if ( gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      v30[0] = 3;
      ComTraceMessage(
        v14,
        "onecore\\com\\combase\\rpcss\\objex\\orclnt.cxx",
        "CClientOxid::GetInfo",
        254,
        *(_QWORD *)v30,
        L"%!WINERROR!");
    }
    if ( v14 == 1717 && !(_DWORD)v13 && v34 )
    {
      while ( 1 )
      {
        DestinationBinding = 0;
        v15 = *((_QWORD *)&v38 + 1) ? *(RPC_BINDING_HANDLE **)(*((_QWORD *)&v38 + 1) + 8 * v13) : 0LL;
        v16 = RpcBindingCopy(*v15, &DestinationBinding);
        if ( v16 )
          break;
        if ( *((_QWORD *)&v38 + 1) )
          v17 = *(RPC_BINDING_HANDLE **)(*((_QWORD *)&v38 + 1) + 8 * v13);
        else
          v17 = 0;
        RpcBindingFree(v17);
        v18 = RpcBindingReset(DestinationBinding);
        if ( v18 )
        {
          if ( dword_1801574B8 || gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v30[0] = 0;
            ComTraceMessage(
              v18,
              "onecore\\com\\combase\\rpcss\\objex\\orclnt.cxx",
              "CClientOxid::GetInfo",
              273,
              *(_QWORD *)v30,
              L"%!WINERROR!",
              v18);
          }
          RpcBindingFree(&DestinationBinding);
          goto LABEL_47;
        }
        v19 = (RPC_BINDING_HANDLE *)*((_QWORD *)&v38 + 1);
        if ( *((_QWORD *)&v38 + 1) )
          v19 = *(RPC_BINDING_HANDLE **)(*((_QWORD *)&v38 + 1) + 8 * v13);
        v13 = (unsigned int)(v13 + 1);
        *v19 = DestinationBinding;
        if ( (unsigned int)v13 >= v34 )
        {
          v13 = 1;
          goto LABEL_20;
        }
      }
      if ( dword_1801574B8 || gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v30[0] = 0;
        ComTraceMessage(
          v16,
          "onecore\\com\\combase\\rpcss\\objex\\orclnt.cxx",
          "CClientOxid::GetInfo",
          265,
          *(_QWORD *)v30,
          L"%!WINERROR!",
          v16);
      }
LABEL_47:
      AcquireSRWLockExclusive(&gpClientLock);
    }
    else
    {
      AcquireSRWLockExclusive(&gpClientLock);
      if ( !v14 )
      {
        v9 = *(unsigned __int16 **)(v39 + 16);
        if ( gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          v20 = v9 + 1;
          if ( !v9 )
            v20 = &Class;
          v30[0] = 3;
          ComTraceMessage(
            0xFFFFFFFFLL,
            "onecore\\com\\combase\\rpcss\\objex\\orclnt.cxx",
            "CClientOxid::GetInfo",
            295,
            *(_QWORD *)v30,
            L"Winner:%ws",
            v20);
        }
        *((_WORD *)this + 117) = ((unsigned int)((_DWORD)v9 - *(_DWORD *)v8) - 4LL) >> 1;
      }
    }
    CParallelPing::Reset((CParallelPing *)&v33);
    wistd::unique_ptr<tagDUALSTRINGARRAY,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>::reset(
      &v38,
      0);
    wistd::unique_ptr<tagDUALSTRINGARRAY,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>::reset(
      &v37,
      0);
LABEL_56:
    if ( !v9 )
    {
      if ( dword_1801574B8 || gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v30[0] = 0;
        ComTraceMessage(
          0xFFFFFFFFLL,
          "onecore\\com\\combase\\rpcss\\objex\\orclnt.cxx",
          "CClientOxid::GetInfo",
          306,
          *(_QWORD *)v30,
          L"Unable to find a binding for Client OXID:%I64X (to %ws)",
          *((_QWORD *)this + 3),
          *(_QWORD *)v8 + 6LL);
      }
      v21 = retaddr;
      v22 = 308;
      return wil::details::in1diag3::Log_Win32(
               v21,
               (void *)v22,
               (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\orclnt.cxx",
               (const char *)0x776,
               v30[0]);
    }
    goto LABEL_78;
  }
  MatchingProtseq = FindMatchingProtseq(v10, *((_WORD *)this + 116), (unsigned __int16 *)(*(_QWORD *)v8 + 4LL));
  v12 = *(_QWORD *)v8;
  v9 = MatchingProtseq;
  if ( !MatchingProtseq )
    goto LABEL_19;
  *((_WORD *)this + 117) = ((__int64)MatchingProtseq - v12 - 4) >> 1;
LABEL_78:
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
      v30[0]);
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
      v30[0]);
    StringBinding = (unsigned __int16)StringBinding;
  }
  if ( lpMem )
    HeapFree(g_hHeap, 0, lpMem);
  return StringBinding;
}

```

## disassembly

```asm
0x180052540  mov     r11, rsp
0x180052543  push    rbp
0x180052544  push    rbx
0x180052545  push    r12
0x180052547  push    r13
0x180052549  push    r14
0x18005254b  lea     rbp, [r11-5Fh]
0x18005254f  sub     rsp, 0D0h
0x180052556  mov     rbx, [rcx+88h]
0x18005255d  mov     r13, rdx
0x180052560  mov     r14, rcx
0x180052563  test    rbx, rbx
0x180052566  jz      loc_180052BB5
0x18005256c  movzx   eax, word ptr [rbx]
0x18005256f  cmp     eax, 4
0x180052572  jb      loc_180052BB5
0x180052578  movzx   r8d, word ptr [rbx+2]
0x18005257d  cmp     r8d, 2
0x180052581  jb      loc_180052BB5
0x180052587  mov     edx, eax
0x180052589  add     eax, 0FFFFFFFEh
0x18005258c  cmp     r8d, eax
0x18005258f  jg      loc_180052BB5
0x180052595  cmp     word ptr [rbx+r8*2+2], 0
0x18005259c  jnz     loc_180052BB5
0x1800525a2  cmp     word ptr [rbx+r8*2], 0
0x1800525a8  jnz     loc_180052BB5
0x1800525ae  cmp     word ptr [rbx+rdx*2+2], 0
0x1800525b4  jnz     loc_180052BB5
0x1800525ba  cmp     word ptr [rbx+rdx*2], 0
0x1800525bf  jnz     loc_180052BB5
0x1800525c5  movzx   ecx, word ptr [rcx+0E8h]
0x1800525cc  mov     [r11-30h], rdi
0x1800525d0  xor     edi, edi
0x1800525d2  mov     [r11-38h], r15
0x1800525d6  cmp     di, cx
0x1800525d9  jz      loc_1800529FA
0x1800525df  cmp     cx, 21h ; '!'
0x1800525e3  jz      loc_1800529F3
0x1800525e9  cmp     [r14+0C8h], rdi
0x1800525f0  jz      short loc_1800525F7
0x1800525f2  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800525f7  movzx   eax, word ptr [r14+0EAh]
0x1800525ff  lea     r15, [r14+88h]
0x180052606  mov     ecx, 0FFFFh
0x18005260b  cmp     ax, cx
0x18005260e  jz      short loc_180052622
0x180052610  mov     ebx, eax
0x180052612  mov     rax, [r15]
0x180052615  add     rbx, 2
0x180052619  lea     rbx, [rax+rbx*2]
0x18005261d  jmp     loc_18005294C
0x180052622  mov     rcx, [r14+0F0h]; unsigned __int16 *
0x180052629  mov     rbx, rdi
0x18005262c  test    rcx, rcx
0x18005262f  jz      short loc_180052667
0x180052631  mov     r8, [r15]
0x180052634  movzx   edx, word ptr [r14+0E8h]; unsigned __int16
0x18005263c  add     r8, 4; unsigned __int16 *
0x180052640  call    ?FindMatchingProtseq@@YAPEAGPEAGG0@Z; FindMatchingProtseq(ushort *,ushort,ushort *)
0x180052645  mov     rcx, [r15]
0x180052648  mov     rbx, rax
0x18005264b  test    rax, rax
0x18005264e  jz      short loc_18005266A
0x180052650  sub     rax, rcx
0x180052653  sub     rax, 4
0x180052657  sar     rax, 1
0x18005265a  mov     [r14+0EAh], ax
0x180052662  jmp     loc_180052AD0
0x180052667  mov     rcx, [r15]
0x18005266a  lea     rax, ??_7CTestBindingPPing@@6B@; const CTestBindingPPing::`vftable'
0x180052671  mov     [rsp+0F0h+arg_8], rsi
0x180052679  mov     [rbp+57h+var_90], rax
0x18005267d  xorps   xmm0, xmm0
0x180052680  lea     rax, [rcx+4]
0x180052684  mov     [rbp+57h+var_88], edi
0x180052687  lea     rcx, ?gpClientLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18005268e  mov     [rbp+57h+var_38], rax
0x180052692  mov     [rbp+57h+var_78], edi
0x180052695  mov     esi, edi
0x180052697  mov     [rbp+57h+var_68], 6BAh
0x18005269e  mov     [rbp+57h+var_60], rdi
0x1800526a2  movdqa  [rbp+57h+var_50], xmm0
0x1800526a7  mov     [rbp+57h+var_40], rdi
0x1800526ab  call    cs:__imp_ReleaseSRWLockExclusive
0x1800526b2  nop     dword ptr [rax+rax+00h]
0x1800526b7  lea     rcx, [rbp+57h+var_90]; this
0x1800526bb  call    ?Ping@CParallelPing@@QEAAJXZ; CParallelPing::Ping(void)
0x1800526c0  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x1800526c7  mov     edi, eax
0x1800526c9  jz      short loc_18005270B
0x1800526cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800526d2  test    byte ptr [rcx+1Ch], 8
0x1800526d6  jz      short loc_18005270B
0x1800526d8  mov     dword ptr [rsp+0F0h+var_C0], eax
0x1800526dc  lea     r8, aCclientoxidGet; "CClientOxid::GetInfo"
0x1800526e3  lea     rax, aWinerror; "%!WINERROR!"
0x1800526ea  mov     r9d, 0FEh
0x1800526f0  mov     [rsp+0F0h+var_C8], rax
0x1800526f5  lea     rdx, aOnecoreComComb_0; "onecore\\com\\combase\\rpcss\\objex\\or"...
0x1800526fc  mov     ecx, edi
0x1800526fe  mov     [rsp+0F0h+var_D0], 3
0x180052706  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x18005270b  cmp     edi, 6B5h
0x180052711  jnz     loc_180052894
0x180052717  test    esi, esi
0x180052719  jnz     loc_180052894
0x18005271f  cmp     [rbp+57h+var_88], esi
0x180052722  jbe     loc_180052894
0x180052728  nop     dword ptr [rax+rax+00000000h]
0x180052730  mov     rax, qword ptr [rbp+57h+var_50+8]
0x180052734  lea     rdi, ds:0[rsi*8]
0x18005273c  mov     [rbp+57h+DestinationBinding], 0
0x180052744  test    rax, rax
0x180052747  jz      short loc_18005274F
0x180052749  mov     rcx, [rax+rdi]
0x18005274d  jmp     short loc_180052751
0x18005274f  xor     ecx, ecx
0x180052751  mov     rcx, [rcx]; SourceBinding
0x180052754  lea     rdx, [rbp+57h+DestinationBinding]; DestinationBinding
0x180052758  call    cs:__imp_RpcBindingCopy
0x18005275f  nop     dword ptr [rax+rax+00h]
0x180052764  mov     ecx, eax
0x180052766  test    eax, eax
0x180052768  jnz     loc_18005282C
0x18005276e  mov     rax, qword ptr [rbp+57h+var_50+8]
0x180052772  test    rax, rax
0x180052775  jz      short loc_18005277D
0x180052777  mov     rcx, [rax+rdi]
0x18005277b  jmp     short loc_18005277F
0x18005277d  xor     ecx, ecx; Binding
0x18005277f  call    cs:__imp_RpcBindingFree
0x180052786  nop     dword ptr [rax+rax+00h]
0x18005278b  mov     rcx, [rbp+57h+DestinationBinding]; Binding
0x18005278f  call    cs:__imp_RpcBindingReset
0x180052796  nop     dword ptr [rax+rax+00h]
0x18005279b  mov     ecx, eax
0x18005279d  test    eax, eax
0x18005279f  jnz     short loc_1800527CA
0x1800527a1  mov     rax, qword ptr [rbp+57h+var_50+8]
0x1800527a5  mov     rcx, [rbp+57h+DestinationBinding]
0x1800527a9  test    rax, rax
0x1800527ac  jz      short loc_1800527B2
0x1800527ae  mov     rax, [rax+rdi]
0x1800527b2  inc     esi
0x1800527b4  mov     [rax], rcx
0x1800527b7  cmp     esi, [rbp+57h+var_88]
0x1800527ba  jb      loc_180052730
0x1800527c0  mov     esi, 1
0x1800527c5  jmp     loc_1800526B7
0x1800527ca  mov     eax, cs:dword_1801574B8
0x1800527d0  test    eax, eax
0x1800527d2  jnz     short loc_1800527E9
0x1800527d4  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800527da  jz      short loc_18005281A
0x1800527dc  mov     rax, cs:WPP_GLOBAL_Control
0x1800527e3  test    byte ptr [rax+1Ch], 1
0x1800527e7  jz      short loc_18005281A
0x1800527e9  mov     dword ptr [rsp+0F0h+var_C0], ecx
0x1800527ed  lea     rax, aWinerror; "%!WINERROR!"
0x1800527f4  mov     [rsp+0F0h+var_C8], rax
0x1800527f9  lea     r8, aCclientoxidGet; "CClientOxid::GetInfo"
0x180052800  mov     r9d, 111h
0x180052806  mov     [rsp+0F0h+var_D0], 0
0x18005280e  lea     rdx, aOnecoreComComb_0; "onecore\\com\\combase\\rpcss\\objex\\or"...
0x180052815  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x18005281a  lea     rcx, [rbp+57h+DestinationBinding]; Binding
0x18005281e  call    cs:__imp_RpcBindingFree
0x180052825  nop     dword ptr [rax+rax+00h]
0x18005282a  jmp     short loc_18005287C
0x18005282c  mov     eax, cs:dword_1801574B8
0x180052832  test    eax, eax
0x180052834  jnz     short loc_18005284B
0x180052836  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x18005283c  jz      short loc_18005287C
0x18005283e  mov     rax, cs:WPP_GLOBAL_Control
0x180052845  test    byte ptr [rax+1Ch], 1
0x180052849  jz      short loc_18005287C
0x18005284b  mov     dword ptr [rsp+0F0h+var_C0], ecx
0x18005284f  lea     rax, aWinerror; "%!WINERROR!"
0x180052856  mov     [rsp+0F0h+var_C8], rax
0x18005285b  lea     r8, aCclientoxidGet; "CClientOxid::GetInfo"
0x180052862  mov     r9d, 109h
0x180052868  mov     [rsp+0F0h+var_D0], 0
0x180052870  lea     rdx, aOnecoreComComb_0; "onecore\\com\\combase\\rpcss\\objex\\or"...
0x180052877  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x18005287c  lea     rcx, ?gpClientLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x180052883  call    cs:__imp_AcquireSRWLockExclusive
0x18005288a  nop     dword ptr [rax+rax+00h]
0x18005288f  jmp     loc_180052923
0x180052894  lea     rcx, ?gpClientLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18005289b  call    cs:__imp_AcquireSRWLockExclusive
0x1800528a2  nop     dword ptr [rax+rax+00h]
0x1800528a7  test    edi, edi
0x1800528a9  jnz     short loc_180052923
0x1800528ab  cmp     cs:?gfEnableTracing@@3HA, edi; int gfEnableTracing
0x1800528b1  mov     rax, [rbp+57h+var_40]
0x1800528b5  mov     rbx, [rax+10h]
0x1800528b9  jz      short loc_18005290F
0x1800528bb  mov     rax, cs:WPP_GLOBAL_Control
0x1800528c2  test    byte ptr [rax+1Ch], 8
0x1800528c6  jz      short loc_18005290F
0x1800528c8  lea     rax, [rbx+2]
0x1800528cc  test    rbx, rbx
0x1800528cf  jnz     short loc_1800528D8
0x1800528d1  lea     rax, Class
0x1800528d8  mov     [rsp+0F0h+var_C0], rax
0x1800528dd  lea     r8, aCclientoxidGet; "CClientOxid::GetInfo"
0x1800528e4  lea     rax, aWinnerWs; "Winner:%ws"
0x1800528eb  mov     r9d, 127h
0x1800528f1  mov     [rsp+0F0h+var_C8], rax
0x1800528f6  lea     rdx, aOnecoreComComb_0; "onecore\\com\\combase\\rpcss\\objex\\or"...
0x1800528fd  mov     ecx, 0FFFFFFFFh
0x180052902  mov     [rsp+0F0h+var_D0], 3
0x18005290a  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x18005290f  mov     eax, ebx
0x180052911  sub     eax, [r15]
0x180052914  sub     rax, 4
0x180052918  sar     rax, 1
0x18005291b  mov     [r14+0EAh], ax
0x180052923  lea     rcx, [rbp+57h+var_90]; this
0x180052927  call    ?Reset@CParallelPing@@QEAAXXZ; CParallelPing::Reset(void)
0x18005292c  xor     edx, edx
0x18005292e  lea     rcx, [rbp+57h+var_50]
0x180052932  call    ?reset@?$unique_ptr@UtagDUALSTRINGARRAY@@U?$function_deleter@P6AXPEAX@Z$1?MIDL_user_free@@YAX0@Z@wil@@@wistd@@QEAAXPEAUtagDUALSTRINGARRAY@@@Z; wistd::unique_ptr<tagDUALSTRINGARRAY,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>::reset(tagDUALSTRINGARRAY *)
0x180052937  xor     edx, edx
0x180052939  lea     rcx, [rbp+57h+var_60]
0x18005293d  call    ?reset@?$unique_ptr@UtagDUALSTRINGARRAY@@U?$function_deleter@P6AXPEAX@Z$1?MIDL_user_free@@YAX0@Z@wil@@@wistd@@QEAAXPEAUtagDUALSTRINGARRAY@@@Z; wistd::unique_ptr<tagDUALSTRINGARRAY,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>::reset(tagDUALSTRINGARRAY *)
0x180052942  mov     rsi, [rsp+0F0h+arg_8]
0x18005294a  xor     edi, edi
0x18005294c  test    rbx, rbx
0x18005294f  jnz     loc_180052AD0
0x180052955  mov     eax, cs:dword_1801574B8
0x18005295b  test    eax, eax
0x18005295d  jnz     short loc_180052974
0x18005295f  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x180052965  jz      short loc_1800529B7
0x180052967  mov     rax, cs:WPP_GLOBAL_Control
0x18005296e  test    byte ptr [rax+1Ch], 1
0x180052972  jz      short loc_1800529B7
0x180052974  mov     rax, [r15]
0x180052977  lea     r8, aCclientoxidGet; "CClientOxid::GetInfo"
0x18005297e  add     rax, 6
0x180052982  lea     rdx, aOnecoreComComb_0; "onecore\\com\\combase\\rpcss\\objex\\or"...
0x180052989  mov     [rsp+38h], rax
0x18005298e  mov     r9d, 132h
0x180052994  mov     rax, [r14+18h]
0x180052998  mov     ecx, 0FFFFFFFFh
0x18005299d  mov     [rsp+0F0h+var_C0], rax
0x1800529a2  lea     rax, aUnableToFindAB; "Unable to find a binding for Client OXI"...
0x1800529a9  mov     [rsp+0F0h+var_C8], rax
0x1800529ae  mov     [rsp+0F0h+var_D0], edi; unsigned int
0x1800529b2  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x1800529b7  mov     rcx, [rbp+5Fh]; this
0x1800529bb  lea     r8, aOnecoreComComb_0; "onecore\\com\\combase\\rpcss\\objex\\or"...
0x1800529c2  mov     r9d, 776h; char *
0x1800529c8  mov     edx, 134h; void *
0x1800529cd  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x1800529d2  mov     r15, [rsp+0F0h+var_30]
0x1800529da  mov     rdi, [rsp+0C8h]
0x1800529e2  add     rsp, 0D0h
0x1800529e9  pop     r14
0x1800529eb  pop     r13
0x1800529ed  pop     r12
0x1800529ef  pop     rbx
0x1800529f0  pop     rbp
0x1800529f1  retn
0x1800529f3  mov     ecx, 21h ; '!'
0x1800529f8  jmp     short loc_1800529FF
0x1800529fa  mov     ecx, 10h
0x1800529ff  movzx   eax, word ptr [rbx+4]
0x180052a03  add     rbx, 4
0x180052a07  test    ax, ax
0x180052a0a  jz      short loc_180052A36
0x180052a0c  nop     dword ptr [rax+00h]
0x180052a10  cmp     ax, cx
0x180052a13  jz      loc_180052AA5
0x180052a19  cmp     [rbx], di
0x180052a1c  jz      short loc_180052A29
0x180052a1e  xchg    ax, ax
0x180052a20  add     rbx, 2
0x180052a24  cmp     [rbx], di
0x180052a27  jnz     short loc_180052A20
0x180052a29  movzx   eax, word ptr [rbx+2]
0x180052a2d  add     rbx, 2
0x180052a31  test    ax, ax
0x180052a34  jnz     short loc_180052A10
0x180052a36  mov     eax, cs:dword_1801574B8
0x180052a3c  test    eax, eax
0x180052a3e  jnz     short loc_180052A55
0x180052a40  cmp     cs:?gfEnableTracing@@3HA, edi; int gfEnableTracing
0x180052a46  jz      short loc_180052A8A
0x180052a48  mov     rax, cs:WPP_GLOBAL_Control
0x180052a4f  test    byte ptr [rax+1Ch], 1
0x180052a53  jz      short loc_180052A8A
0x180052a55  movzx   eax, cx
0x180052a58  lea     r8, aCclientoxidGet; "CClientOxid::GetInfo"
0x180052a5f  mov     dword ptr [rsp+0F0h+var_C0], eax
0x180052a63  lea     rdx, aOnecoreComComb_0; "onecore\\com\\combase\\rpcss\\objex\\or"...
0x180052a6a  lea     rax, aUnableToFindMa; "Unable to find matching protseq for: %d"
  ... truncated ...
```
