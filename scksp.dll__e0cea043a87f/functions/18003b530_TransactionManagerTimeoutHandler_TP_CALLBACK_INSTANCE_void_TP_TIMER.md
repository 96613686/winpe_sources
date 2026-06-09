# TransactionManagerTimeoutHandler(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x18003b530`
- end: `0x18003b782`
- name: `?TransactionManagerTimeoutHandler@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `594`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000a408`
- `0x18000d2a8`
- `0x180011fd8`
- `0x180013734`
- `0x180013aac`
- `0x18002eb6c`
- `0x18003ae44`
- `0x18003aec8`
- `0x18003b530`
- `0x18003b920`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003b5ab`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003b5ab`
- `WinSCard!SCardDisconnect` at `0x18003b6da`
- `WinSCard!SCardDisconnect` at `0x18003b6da`

## pseudocode

```c
void __fastcall TransactionManagerTimeoutHandler(__int64 Instance, struct _CARD_STATE *Context, PTP_TIMER Timer)
{
  __int64 v5; // rcx
  int v6; // r9d
  char *v7; // rbx
  __int64 v8; // rcx
  int v9; // eax
  __int64 v10; // rcx
  char v11; // si
  __int64 v12; // rax
  SCARDHANDLE v13; // rsi
  bool v14; // zf
  LONG v15; // eax
  PVOID v16; // rcx
  char v17; // bl
  void **v18; // [rsp+30h] [rbp-48h] BYREF
  __int64 v19; // [rsp+38h] [rbp-40h]

  v19 = 0;
  v18 = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
  WppTraceIndent(Instance, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_c71af58e9db6359151fab6997eb16e5e_Traceguids, WPP_pszIndent);
  }
  SetThreadpoolTimer(Timer, 0, 0, 0);
  if ( *((_QWORD *)Context + 1) )
  {
    v7 = (char *)Context + 624;
    if ( (unsigned int)CspEnterCriticalSection((char *)Context + 624) )
    {
      WppTraceIndent(v8, 2u);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          24,
          WPP_c71af58e9db6359151fab6997eb16e5e_Traceguids,
          WPP_pszIndent);
      }
    }
    else
    {
      Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(&v18, (char *)Context + 624);
      v9 = TransactionManagerForceEndTransaction(Context);
      v11 = v9;
      if ( v9 )
      {
        WppTraceIndent(v10, 2u);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            25,
            (unsigned int)WPP_c71af58e9db6359151fab6997eb16e5e_Traceguids,
            (_DWORD)WPP_pszIndent,
            v11);
        }
      }
    }
  }
  else
  {
    WppTraceIndent(v5, 2u);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_ss(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        (unsigned int)WPP_c71af58e9db6359151fab6997eb16e5e_Traceguids,
        v6,
        (__int64)"pCardState->pCardData");
    }
    v7 = (char *)Context + 624;
  }
  v12 = *((_QWORD *)Context + 1);
  v13 = *(_QWORD *)(v12 + 104);
  *(_QWORD *)(v12 + 104) = 0;
  v14 = v19 == 0;
  *((_DWORD *)Context + 172) = 1;
  if ( !v14 )
  {
    v19 = 0;
    CspLeaveCriticalSection(v7);
  }
  v15 = SCardDisconnect(v13, 0);
  v17 = v15;
  if ( v15 )
  {
    WppTraceIndent((__int64)v16, 2u);
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        26,
        (unsigned int)WPP_c71af58e9db6359151fab6997eb16e5e_Traceguids,
        (_DWORD)WPP_pszIndent,
        v17);
    }
  }
  WppTraceIndent((__int64)v16, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      27,
      (unsigned int)WPP_c71af58e9db6359151fab6997eb16e5e_Traceguids,
      (_DWORD)WPP_pszIndent,
      v17);
  }
  v18 = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(&v18);
}

```

## disassembly

```asm
0x18003b530  push    rbx
0x18003b532  push    rbp
0x18003b533  push    rsi
0x18003b534  push    rdi
0x18003b535  push    r12
0x18003b537  push    r13
0x18003b539  sub     rsp, 48h
0x18003b53d  mov     rdi, rdx
0x18003b540  mov     [rsp+78h+var_40], 0
0x18003b549  lea     rax, ??_7?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable'
0x18003b550  xor     edx, edx
0x18003b552  mov     [rsp+78h+var_48], rax
0x18003b557  mov     rbx, r8
0x18003b55a  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18003b55f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b566  lea     r12, WPP_GLOBAL_Control
0x18003b56d  lea     r13, WPP_c71af58e9db6359151fab6997eb16e5e_Traceguids
0x18003b574  mov     ebp, 2
0x18003b579  cmp     rcx, r12
0x18003b57c  jz      short loc_18003B5A0
0x18003b57e  test    [rcx+1Ch], bpl
0x18003b582  jz      short loc_18003B5A0
0x18003b584  cmp     byte ptr [rcx+19h], 5
0x18003b588  jb      short loc_18003B5A0
0x18003b58a  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18003b591  lea     edx, [rbp+14h]
0x18003b594  mov     rcx, [rcx+10h]
0x18003b598  mov     r8, r13
0x18003b59b  call    WPP_SF_s
0x18003b5a0  xor     r9d, r9d; msWindowLength
0x18003b5a3  xor     r8d, r8d; msPeriod
0x18003b5a6  xor     edx, edx; pftDueTime
0x18003b5a8  mov     rcx, rbx; pti
0x18003b5ab  call    cs:__imp_SetThreadpoolTimer
0x18003b5b1  cmp     qword ptr [rdi+8], 0
0x18003b5b6  jnz     short loc_18003B600
0x18003b5b8  mov     edx, ebp
0x18003b5ba  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18003b5bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b5c6  cmp     rcx, r12
0x18003b5c9  jz      short loc_18003B5F4
0x18003b5cb  test    byte ptr [rcx+1Ch], 1
0x18003b5cf  jz      short loc_18003B5F4
0x18003b5d1  cmp     [rcx+19h], bpl
0x18003b5d5  jb      short loc_18003B5F4
0x18003b5d7  mov     rcx, [rcx+10h]
0x18003b5db  lea     rax, aPcardstatePcar; "pCardState->pCardData"
0x18003b5e2  mov     edx, 17h
0x18003b5e7  mov     [rsp+78h+var_58], rax
0x18003b5ec  mov     r8, r13
0x18003b5ef  call    WPP_SF_ss
0x18003b5f4  lea     rbx, [rdi+270h]
0x18003b5fb  jmp     loc_18003B6A2
0x18003b600  lea     rbx, [rdi+270h]
0x18003b607  mov     rcx, rbx
0x18003b60a  call    CspEnterCriticalSection
0x18003b60f  test    eax, eax
0x18003b611  jz      short loc_18003B64C
0x18003b613  mov     edx, ebp
0x18003b615  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18003b61a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b621  cmp     rcx, r12
0x18003b624  jz      short loc_18003B6A2
0x18003b626  test    byte ptr [rcx+1Ch], 1
0x18003b62a  jz      short loc_18003B6A2
0x18003b62c  cmp     [rcx+19h], bpl
0x18003b630  jb      short loc_18003B6A2
0x18003b632  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18003b639  mov     edx, 18h
0x18003b63e  mov     rcx, [rcx+10h]
0x18003b642  mov     r8, r13
0x18003b645  call    WPP_SF_s
0x18003b64a  jmp     short loc_18003B6A2
0x18003b64c  mov     rdx, rbx
0x18003b64f  lea     rcx, [rsp+78h+var_48]
0x18003b654  call    ?Attach@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(_RTL_CRITICAL_SECTION *)
0x18003b659  mov     rcx, rdi; struct _CARD_STATE *
0x18003b65c  call    TransactionManagerForceEndTransaction
0x18003b661  mov     esi, eax
0x18003b663  test    eax, eax
0x18003b665  jz      short loc_18003B6A2
0x18003b667  mov     edx, ebp
0x18003b669  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18003b66e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b675  cmp     rcx, r12
0x18003b678  jz      short loc_18003B6A2
0x18003b67a  test    byte ptr [rcx+1Ch], 1
0x18003b67e  jz      short loc_18003B6A2
0x18003b680  cmp     [rcx+19h], bpl
0x18003b684  jb      short loc_18003B6A2
0x18003b686  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18003b68d  mov     edx, 19h
0x18003b692  mov     rcx, [rcx+10h]
0x18003b696  mov     r8, r13
0x18003b699  mov     dword ptr [rsp+78h+var_58], esi
0x18003b69d  call    WPP_SF_sd
0x18003b6a2  mov     rax, [rdi+8]
0x18003b6a6  mov     rsi, [rax+68h]
0x18003b6aa  mov     qword ptr [rax+68h], 0
0x18003b6b2  cmp     [rsp+78h+var_40], 0
0x18003b6b8  mov     dword ptr [rdi+2B0h], 1
0x18003b6c2  jz      short loc_18003B6D5
0x18003b6c4  mov     rcx, rbx
0x18003b6c7  mov     [rsp+78h+var_40], 0
0x18003b6d0  call    CspLeaveCriticalSection
0x18003b6d5  xor     edx, edx; dwDisposition
0x18003b6d7  mov     rcx, rsi; hCard
0x18003b6da  call    cs:__imp_SCardDisconnect
0x18003b6e0  mov     ebx, eax
0x18003b6e2  test    eax, eax
0x18003b6e4  jz      short loc_18003B721
0x18003b6e6  mov     edx, ebp
0x18003b6e8  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18003b6ed  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b6f4  cmp     rcx, r12
0x18003b6f7  jz      short loc_18003B721
0x18003b6f9  test    byte ptr [rcx+1Ch], 1
0x18003b6fd  jz      short loc_18003B721
0x18003b6ff  cmp     [rcx+19h], bpl
0x18003b703  jb      short loc_18003B721
0x18003b705  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18003b70c  mov     edx, 1Ah
0x18003b711  mov     rcx, [rcx+10h]
0x18003b715  mov     r8, r13
0x18003b718  mov     dword ptr [rsp+78h+var_58], ebx
0x18003b71c  call    WPP_SF_sd
0x18003b721  mov     edx, 1
0x18003b726  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18003b72b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b732  cmp     rcx, r12
0x18003b735  jz      short loc_18003B75F
0x18003b737  test    [rcx+1Ch], bpl
0x18003b73b  jz      short loc_18003B75F
0x18003b73d  cmp     byte ptr [rcx+19h], 5
0x18003b741  jb      short loc_18003B75F
0x18003b743  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18003b74a  mov     edx, 1Bh
0x18003b74f  mov     rcx, [rcx+10h]
0x18003b753  mov     r8, r13
0x18003b756  mov     dword ptr [rsp+78h+var_58], ebx
0x18003b75a  call    WPP_SF_sd
0x18003b75f  lea     rax, ??_7?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable'
0x18003b766  lea     rcx, [rsp+78h+var_48]
0x18003b76b  mov     [rsp+78h+var_48], rax
0x18003b770  call    ?Close@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(void)
0x18003b775  add     rsp, 48h
0x18003b779  pop     r13
0x18003b77b  pop     r12
0x18003b77d  pop     rdi
0x18003b77e  pop     rsi
0x18003b77f  pop     rbp
0x18003b780  pop     rbx
0x18003b781  retn
```
