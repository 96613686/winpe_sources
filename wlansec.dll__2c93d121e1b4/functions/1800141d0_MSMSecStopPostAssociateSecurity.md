# MSMSecStopPostAssociateSecurity

- ea: `0x1800141d0`
- end: `0x1800148bc`
- name: `MSMSecStopPostAssociateSecurity`
- size: `1772`
- prototype: `__int64 __fastcall(void *, unsigned __int8 (*)[6])`
- caller_count: `0`
- callee_count: `21`
- tags: `broker_com_uri`

## callees

- `0x18000892c`
- `0x180008998`
- `0x18000a26c`
- `0x18000b6dc`
- `0x18000bd78`
- `0x1800125b0`
- `0x180013600`
- `0x180013bc0`
- `0x1800141d0`
- `0x1800148d0`
- `0x180014998`
- `0x180016a08`
- `0x180018d40`
- `0x180018dd8`
- `0x18002aa48`
- `0x18002b078`
- `0x18003346c`
- `0x180043a30`
- `0x180050da8`
- `0x1800558c0`
- `0x180055a38`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x1800143e5`
- `MobileNetworking!ReleaseWriteLock` at `0x180014491`
- `MobileNetworking!ReleaseWriteLock` at `0x1800143e5`
- `MobileNetworking!ReleaseWriteLock` at `0x180014491`
- `MobileNetworking!AcquireWriteLock` at `0x180014431`
- `MobileNetworking!AcquireWriteLock` at `0x180014431`

## string_xrefs

- `0x180014240`: `MSMSecStopPostAssociateSecurity`
- `0x180014388`: `MSMSecStopPostAssociateSecurity`
- `0x1800143db`: `MSMSecStopPostAssociateSecurity`
- `0x180014424`: `MSMSecStopPostAssociateSecurity`
- `0x180014487`: `MSMSecStopPostAssociateSecurity`
- `0x1800144c8`: `MSMSecStopPostAssociateSecurity`
- `0x1800144f6`: `MSMSecStopPostAssociateSecurity`
- `0x18001452c`: `MSMSecStopPostAssociateSecurity`

## pseudocode

```c
__int64 __fastcall MSMSecStopPostAssociateSecurity(void *a1, unsigned __int8 (*a2)[6], unsigned int *a3)
{
  struct MSMSEC_PORT_CONTEXT *v3; // rsi
  unsigned int v7; // eax
  unsigned int v8; // ebx
  int v9; // r13d
  struct MSMSEC_INTF_CONTEXT *v10; // rdi
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // r9
  unsigned int v14; // eax
  PVOID *v15; // r11
  int v16; // r8d
  unsigned int v17; // eax
  int v18; // r8d
  PVOID *v19; // rcx
  int v20; // r8d
  PVOID *v21; // rcx
  __int64 v22; // r9
  PVOID *v23; // rcx
  __int64 v25; // rax
  unsigned int v26; // r10d
  __int64 v27; // rdx
  int v28; // eax
  __int64 v29; // r11
  __int64 v30; // r8
  char v31; // r10
  __int64 v32; // rdx
  unsigned int v33; // [rsp+50h] [rbp-49h] BYREF
  struct MSMSEC_PORT_CONTEXT *v34; // [rsp+58h] [rbp-41h] BYREF
  struct MSMSEC_INTF_CONTEXT *v35[10]; // [rsp+60h] [rbp-39h] BYREF

  v3 = 0;
  v35[0] = 0;
  v34 = 0;
  v33 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 94, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids);
  v7 = IncThreadCountAndCheckInitializedEx("MSMSecStopPostAssociateSecurity", 876);
  v8 = v7;
  if ( v7 )
  {
    v21 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_47;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_43;
    v32 = 95;
    goto LABEL_67;
  }
  if ( !a1 || !a2 || !a3 )
  {
    v8 = 87;
    v21 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_47;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_43;
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 96, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids);
    goto LABEL_42;
  }
  v7 = SecMgrValidateRefAndLockAdapter(a1, v35);
  v8 = v7;
  if ( !v7 )
  {
    v9 = 0;
    v10 = v35[0];
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0 )
      WPP_SF_Lq(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        98,
        &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids,
        *((unsigned int *)v35[0] + 624),
        a1);
    if ( (byte_1800AED45 & 1) != 0 )
    {
      LODWORD(v35[0]) = *((_DWORD *)v10 + 624);
      v35[7] = (struct MSMSEC_INTF_CONTEXT *)16;
      v35[4] = (struct MSMSEC_INTF_CONTEXT *)v35;
      v35[5] = (struct MSMSEC_INTF_CONTEXT *)4;
      v35[6] = (struct MSMSEC_INTF_CONTEXT *)((char *)v10 + 32);
      v35[8] = (struct MSMSEC_INTF_CONTEXT *)a2;
      v35[9] = (struct MSMSEC_INTF_CONTEXT *)6;
      McGenEventWrite_EventWriteTransfer(&WLANSVC_EVT_GUID_Context, "'R");
    }
    if ( !(unsigned int)IsValidIntfSecStateForAction(*((unsigned int *)v10 + 681), 5) )
    {
      v8 = 5023;
      v15 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_33;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      {
LABEL_30:
        if ( v15 != &WPP_GLOBAL_Control && (*((_DWORD *)v15 + 17) & 0x100) != 0 )
          WPP_SF_Ls((unsigned int)v15[7], 11, v12, *((_DWORD *)v10 + 624), (__int64)"<<< Unlocking <<<");
        goto LABEL_33;
      }
      v25 = IntfActionStr(5, v11, v12, v13);
      v28 = IntfSecStateStr(v26, v27, v25);
      WPP_SF_SLSL(
        *(_QWORD *)(v29 + 56),
        99,
        (unsigned int)&WPP_5807585f210c3b3262a513c5e260de7e_Traceguids,
        v28,
        v31,
        v30,
        5);
LABEL_29:
      v15 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_30;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0 )
      WPP_SF_LDDDDDD(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        100,
        &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids,
        *((unsigned int *)v10 + 624),
        (*a2)[0],
        (*a2)[1],
        (*a2)[2],
        (*a2)[3],
        (*a2)[4],
        (*a2)[5]);
    v14 = SecMgrValidateAndMovePortOnPortDown(v10, a2, &v34);
    v8 = v14;
    if ( v14 )
    {
      v15 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      {
        v3 = v34;
LABEL_33:
        ReleaseWriteLock(v10, (char *)v10 + 2512, "MSMSecStopPostAssociateSecurity", 960);
        if ( v9 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
            WPP_SF_Ls(*((_QWORD *)WPP_GLOBAL_Control + 7), 12, v20, *((_DWORD *)v3 + 78), (__int64)"<<< Derefing <<<");
          SecMgrDerefPortEx(v3, "MSMSecStopPostAssociateSecurity", 964);
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
          WPP_SF_Ls(*((_QWORD *)WPP_GLOBAL_Control + 7), 11, v20, *((_DWORD *)v10 + 624), (__int64)"<<< Derefing <<<");
        SecMgrDerefAdapterEx(v10, "MSMSecStopPostAssociateSecurity", 968);
        goto LABEL_42;
      }
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      {
        v3 = v34;
        goto LABEL_30;
      }
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 101, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v14);
      v3 = v34;
      goto LABEL_29;
    }
    v3 = v34;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
      WPP_SF_Ls(*((_QWORD *)WPP_GLOBAL_Control + 7), 12, v12, *((_DWORD *)v34 + 78), (__int64)">>> Refing >>>");
    SecMgrRefPortEx(v3, "MSMSecStopPostAssociateSecurity", 928);
    v9 = 1;
    SecMgrIntfStateTransition(v10, 6, 327679);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
      WPP_SF_Ls(*((_QWORD *)WPP_GLOBAL_Control + 7), 11, v16, *((_DWORD *)v10 + 624), (__int64)"<<< Unlocking <<<");
    ReleaseWriteLock(v10, (char *)v10 + 2512, "MSMSecStopPostAssociateSecurity", 935);
    v17 = SecMgrDestroyPort(v3, &v33);
    if ( v17 )
    {
      v19 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      {
LABEL_28:
        AcquireWriteLock(v10, (char *)v10 + 2512, "MSMSecStopPostAssociateSecurity", 946);
        SecMgrIntfStateTransition(v10, 3, 327679);
        *a3 = v33;
        goto LABEL_29;
      }
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      {
LABEL_25:
        if ( v19 != &WPP_GLOBAL_Control && (*((_DWORD *)v19 + 17) & 0x100) != 0 )
          WPP_SF_Ls((unsigned int)v19[7], 11, v18, *((_DWORD *)v10 + 624), (__int64)">>> Locking >>>");
        goto LABEL_28;
      }
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 102, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v17);
    }
    v19 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_25;
  }
  v21 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_47;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    v32 = 97;
LABEL_67:
    WPP_SF_d(v21[7], v32, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v7);
LABEL_42:
    v21 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_43:
  if ( v21 != &WPP_GLOBAL_Control && (*((_DWORD *)v21 + 17) & 0x400) != 0 )
    WPP_SF_sd(
      (unsigned int)v21[7],
      24,
      (unsigned int)&WPP_0c0bf6275506325847d38564a7df1e9a_Traceguids,
      (unsigned int)"MSMSecStopPostAssociateSecurity",
      202);
LABEL_47:
  v22 = (unsigned int)_InterlockedDecrement(&dword_1800AEF94);
  v23 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x400) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 25, &WPP_0c0bf6275506325847d38564a7df1e9a_Traceguids, v22);
      v23 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v23 != &WPP_GLOBAL_Control && (*((_DWORD *)v23 + 17) & 0x100) != 0 )
      WPP_SF_d(v23[7], 103, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v8);
  }
  return v8;
}

```

## disassembly

```asm
0x1800141d0  mov     [rsp-8+arg_18], rbx
0x1800141d5  push    rbp
0x1800141d6  push    rsi
0x1800141d7  push    rdi
0x1800141d8  push    r12
0x1800141da  push    r13
0x1800141dc  push    r14
0x1800141de  push    r15
0x1800141e0  lea     rbp, [rsp-27h]
0x1800141e5  sub     rsp, 0C0h
0x1800141ec  mov     rax, cs:__security_cookie
0x1800141f3  xor     rax, rsp
0x1800141f6  mov     [rbp+57h+var_40], rax
0x1800141fa  xor     esi, esi
0x1800141fc  mov     [rbp+57h+var_90], 0
0x180014204  mov     [rbp+57h+var_98], rsi
0x180014208  mov     r12, r8
0x18001420b  mov     [rbp+57h+var_A0], esi
0x18001420e  mov     r14, rdx
0x180014211  mov     r15, rcx
0x180014214  mov     rcx, cs:WPP_GLOBAL_Control
0x18001421b  lea     rdi, WPP_GLOBAL_Control
0x180014222  lea     r13, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x180014229  cmp     rcx, rdi
0x18001422c  jz      short loc_18001423B
0x18001422e  test    dword ptr [rcx+44h], 100h
0x180014235  jnz     loc_18001473D
0x18001423b  mov     edx, 36Ch; int
0x180014240  lea     rcx, aMsmsecstoppost_0; "MSMSecStopPostAssociateSecurity"
0x180014247  call    ?IncThreadCountAndCheckInitializedEx@@YAKPEBDH@Z; IncThreadCountAndCheckInitializedEx(char const *,int)
0x18001424c  mov     ebx, eax
0x18001424e  test    eax, eax
0x180014250  jnz     loc_18001454E
0x180014256  test    r15, r15
0x180014259  jz      loc_1800145B6
0x18001425f  test    r14, r14
0x180014262  jz      loc_1800145B6
0x180014268  test    r12, r12
0x18001426b  jz      loc_1800145B6
0x180014271  lea     rdx, [rbp+57h+var_90]; struct MSMSEC_INTF_CONTEXT **
0x180014275  mov     rcx, r15; void *
0x180014278  call    ?SecMgrValidateRefAndLockAdapter@@YAKPEAXPEAPEAUMSMSEC_INTF_CONTEXT@@@Z; SecMgrValidateRefAndLockAdapter(void *,MSMSEC_INTF_CONTEXT * *)
0x18001427d  mov     ebx, eax
0x18001427f  test    eax, eax
0x180014281  jnz     loc_18001470A
0x180014287  xor     r13d, r13d
0x18001428a  mov     rcx, cs:WPP_GLOBAL_Control
0x180014291  lea     rax, WPP_GLOBAL_Control
0x180014298  mov     rdi, [rbp+57h+var_90]
0x18001429c  cmp     rcx, rax
0x18001429f  jnz     loc_180014604
0x1800142a5  test    cs:byte_1800AED45, 1
0x1800142ac  jz      short loc_180014301
0x1800142ae  mov     eax, [rdi+9C0h]
0x1800142b4  lea     rdx, MsmSecPortDown; "'R"
0x1800142bb  mov     dword ptr [rbp+57h+var_90], eax
0x1800142be  lea     rcx, WLANSVC_EVT_GUID_Context
0x1800142c5  lea     rax, [rbp+57h+var_90]
0x1800142c9  mov     [rbp+57h+var_58], 10h
0x1800142d1  mov     [rbp+57h+var_70], rax
0x1800142d5  mov     r9d, 4
0x1800142db  lea     rax, [rdi+20h]
0x1800142df  mov     [rbp+57h+var_68], r9
0x1800142e3  mov     [rbp+57h+var_60], rax
0x1800142e7  lea     rax, [rbp+57h+var_80]
0x1800142eb  mov     [rsp+0F0h+var_D0], rax
0x1800142f0  mov     [rbp+57h+var_50], r14
0x1800142f4  mov     [rbp+57h+var_48], 6
0x1800142fc  call    McGenEventWrite_EventWriteTransfer
0x180014301  mov     ecx, [rdi+0AA4h]
0x180014307  mov     edx, 5
0x18001430c  call    ?IsValidIntfSecStateForAction@@YAHW4MSMSEC_INTF_SEC_STATE@@W4SECMGR_INTF_ACTION@@@Z; IsValidIntfSecStateForAction(MSMSEC_INTF_SEC_STATE,SECMGR_INTF_ACTION)
0x180014311  lea     rcx, aUnlocking; "<<< Unlocking <<<"
0x180014318  test    eax, eax
0x18001431a  jz      loc_180014698
0x180014320  mov     rcx, cs:WPP_GLOBAL_Control
0x180014327  lea     r15, WPP_GLOBAL_Control
0x18001432e  cmp     rcx, r15
0x180014331  jnz     loc_180014634
0x180014337  lea     r8, [rbp+57h+var_98]; struct MSMSEC_PORT_CONTEXT **
0x18001433b  mov     rdx, r14; unsigned __int8 (*)[6]
0x18001433e  mov     rcx, rdi; struct MSMSEC_INTF_CONTEXT *
0x180014341  call    ?SecMgrValidateAndMovePortOnPortDown@@YAKPEAUMSMSEC_INTF_CONTEXT@@PEAY05EPEAPEAUMSMSEC_PORT_CONTEXT@@@Z; SecMgrValidateAndMovePortOnPortDown(MSMSEC_INTF_CONTEXT *,uchar (*)[6],MSMSEC_PORT_CONTEXT * *)
0x180014346  mov     ebx, eax
0x180014348  test    eax, eax
0x18001434a  jz      short loc_180014365
0x18001434c  mov     r11, cs:WPP_GLOBAL_Control
0x180014353  cmp     r11, r15
0x180014356  jnz     loc_180014764
0x18001435c  mov     rsi, [rbp+57h+var_98]
0x180014360  jmp     loc_18001447A
0x180014365  mov     rcx, cs:WPP_GLOBAL_Control
0x18001436c  mov     rsi, [rbp+57h+var_98]
0x180014370  cmp     rcx, r15
0x180014373  jz      short loc_180014382
0x180014375  test    dword ptr [rcx+44h], 100h
0x18001437c  jnz     loc_180014795
0x180014382  mov     r8d, 3A0h; int
0x180014388  lea     rdx, aMsmsecstoppost_0; "MSMSecStopPostAssociateSecurity"
0x18001438f  mov     rcx, rsi; struct MSMSEC_PORT_CONTEXT *
0x180014392  call    ?SecMgrRefPortEx@@YAXPEAUMSMSEC_PORT_CONTEXT@@PEBDH@Z; SecMgrRefPortEx(MSMSEC_PORT_CONTEXT *,char const *,int)
0x180014397  mov     r13d, 1
0x18001439d  xor     r9d, r9d
0x1800143a0  mov     r8d, 4FFFFh
0x1800143a6  mov     rcx, rdi
0x1800143a9  lea     edx, [r13+5]
0x1800143ad  call    ?SecMgrIntfStateTransition@@YAXPEAUMSMSEC_INTF_CONTEXT@@W4MSMSEC_INTF_SEC_STATE@@KK@Z; SecMgrIntfStateTransition(MSMSEC_INTF_CONTEXT *,MSMSEC_INTF_SEC_STATE,ulong,ulong)
0x1800143b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800143b9  cmp     rcx, r15
0x1800143bc  jz      short loc_1800143CB
0x1800143be  test    dword ptr [rcx+44h], 100h
0x1800143c5  jnz     loc_1800147BB
0x1800143cb  lea     r14, [rdi+9D0h]
0x1800143d2  mov     r9d, 3A7h
0x1800143d8  mov     rdx, r14
0x1800143db  lea     r8, aMsmsecstoppost_0; "MSMSecStopPostAssociateSecurity"
0x1800143e2  mov     rcx, rdi
0x1800143e5  call    cs:__imp_ReleaseWriteLock
0x1800143ec  nop     dword ptr [rax+rax+00h]
0x1800143f1  lea     rdx, [rbp+57h+var_A0]; unsigned int *
0x1800143f5  mov     rcx, rsi; struct MSMSEC_PORT_CONTEXT *
0x1800143f8  call    ?SecMgrDestroyPort@@YAKPEAUMSMSEC_PORT_CONTEXT@@PEAK@Z; SecMgrDestroyPort(MSMSEC_PORT_CONTEXT *,ulong *)
0x1800143fd  test    eax, eax
0x1800143ff  jnz     loc_1800147E1
0x180014405  mov     rcx, cs:WPP_GLOBAL_Control
0x18001440c  cmp     rcx, r15
0x18001440f  jz      short loc_18001441E
0x180014411  test    dword ptr [rcx+44h], 100h
0x180014418  jnz     loc_180014818
0x18001441e  mov     r9d, 3B2h
0x180014424  lea     r8, aMsmsecstoppost_0; "MSMSecStopPostAssociateSecurity"
0x18001442b  mov     rdx, r14
0x18001442e  mov     rcx, rdi
0x180014431  call    cs:__imp_AcquireWriteLock
0x180014438  nop     dword ptr [rax+rax+00h]
0x18001443d  xor     r9d, r9d
0x180014440  mov     r8d, 4FFFFh
0x180014446  mov     rcx, rdi
0x180014449  lea     edx, [r9+3]
0x18001444d  call    ?SecMgrIntfStateTransition@@YAXPEAUMSMSEC_INTF_CONTEXT@@W4MSMSEC_INTF_SEC_STATE@@KK@Z; SecMgrIntfStateTransition(MSMSEC_INTF_CONTEXT *,MSMSEC_INTF_SEC_STATE,ulong,ulong)
0x180014452  mov     eax, [rbp+57h+var_A0]
0x180014455  mov     [r12], eax
0x180014459  mov     r11, cs:WPP_GLOBAL_Control
0x180014460  lea     rcx, aUnlocking; "<<< Unlocking <<<"
0x180014467  cmp     r11, r15
0x18001446a  jz      short loc_18001447A
0x18001446c  test    dword ptr [r11+44h], 100h
0x180014474  jnz     loc_18001483E
0x18001447a  lea     rdx, [rdi+9D0h]
0x180014481  mov     r9d, 3C0h
0x180014487  lea     r8, aMsmsecstoppost_0; "MSMSecStopPostAssociateSecurity"
0x18001448e  mov     rcx, rdi
0x180014491  call    cs:__imp_ReleaseWriteLock
0x180014498  nop     dword ptr [rax+rax+00h]
0x18001449d  lea     r14, aDerefing; "<<< Derefing <<<"
0x1800144a4  test    r13d, r13d
0x1800144a7  jz      short loc_1800144D7
0x1800144a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800144b0  cmp     rcx, r15
0x1800144b3  jz      short loc_1800144C2
0x1800144b5  test    dword ptr [rcx+44h], 100h
0x1800144bc  jnz     loc_18001485D
0x1800144c2  mov     r8d, 3C4h; int
0x1800144c8  lea     rdx, aMsmsecstoppost_0; "MSMSecStopPostAssociateSecurity"
0x1800144cf  mov     rcx, rsi; struct MSMSEC_PORT_CONTEXT *
0x1800144d2  call    ?SecMgrDerefPortEx@@YAXPEAUMSMSEC_PORT_CONTEXT@@PEBDH@Z; SecMgrDerefPortEx(MSMSEC_PORT_CONTEXT *,char const *,int)
0x1800144d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800144de  cmp     rcx, r15
0x1800144e1  jz      short loc_1800144F0
0x1800144e3  test    dword ptr [rcx+44h], 100h
0x1800144ea  jnz     loc_18001487C
0x1800144f0  mov     r8d, 3C8h; int
0x1800144f6  lea     rdx, aMsmsecstoppost_0; "MSMSecStopPostAssociateSecurity"
0x1800144fd  mov     rcx, rdi; struct MSMSEC_INTF_CONTEXT *
0x180014500  call    ?SecMgrDerefAdapterEx@@YAXPEAUMSMSEC_INTF_CONTEXT@@PEBDH@Z; SecMgrDerefAdapterEx(MSMSEC_INTF_CONTEXT *,char const *,int)
0x180014505  lea     rdi, WPP_GLOBAL_Control
0x18001450c  lea     r13, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x180014513  mov     rcx, cs:WPP_GLOBAL_Control
0x18001451a  cmp     rcx, rdi
0x18001451d  jz      short loc_18001455E
0x18001451f  test    dword ptr [rcx+44h], 400h
0x180014526  jz      short loc_18001455E
0x180014528  mov     rcx, [rcx+38h]
0x18001452c  lea     r9, aMsmsecstoppost_0; "MSMSecStopPostAssociateSecurity"
0x180014533  mov     edx, 18h
0x180014538  mov     dword ptr [rsp+0F0h+var_D0], 3CAh
0x180014540  lea     r8, WPP_0c0bf6275506325847d38564a7df1e9a_Traceguids
0x180014547  call    WPP_SF_sd
0x18001454c  jmp     short loc_18001455E
0x18001454e  mov     rcx, cs:WPP_GLOBAL_Control
0x180014555  cmp     rcx, rdi
0x180014558  jnz     loc_180014753
0x18001455e  or      r9d, 0FFFFFFFFh
0x180014562  lock xadd cs:dword_1800AEF94, r9d
0x18001456b  dec     r9d
0x18001456e  mov     rcx, cs:WPP_GLOBAL_Control
0x180014575  cmp     rcx, rdi
0x180014578  jz      short loc_18001458C
0x18001457a  test    dword ptr [rcx+44h], 400h
0x180014581  jnz     loc_18001489B
0x180014587  cmp     rcx, rdi
0x18001458a  jnz     short loc_1800145E5
0x18001458c  mov     eax, ebx
0x18001458e  mov     rcx, [rbp+57h+var_40]
0x180014592  xor     rcx, rsp; StackCookie
0x180014595  call    __security_check_cookie
0x18001459a  mov     rbx, [rsp+0F0h+arg_18]
0x1800145a2  add     rsp, 0C0h
0x1800145a9  pop     r15
0x1800145ab  pop     r14
0x1800145ad  pop     r13
0x1800145af  pop     r12
0x1800145b1  pop     rdi
0x1800145b2  pop     rsi
0x1800145b3  pop     rbp
0x1800145b4  retn
0x1800145b6  mov     ebx, 57h ; 'W'
0x1800145bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800145c2  cmp     rcx, rdi
0x1800145c5  jz      short loc_18001455E
0x1800145c7  test    byte ptr [rcx+44h], 1
0x1800145cb  jz      loc_18001451A
0x1800145d1  mov     rcx, [rcx+38h]
0x1800145d5  lea     edx, [rbx+9]
0x1800145d8  mov     r8, r13
0x1800145db  call    WPP_SF_
0x1800145e0  jmp     loc_180014513
0x1800145e5  test    dword ptr [rcx+44h], 100h
0x1800145ec  jz      short loc_18001458C
0x1800145ee  mov     rcx, [rcx+38h]
0x1800145f2  mov     edx, 67h ; 'g'
0x1800145f7  mov     r9d, ebx
0x1800145fa  mov     r8, r13
0x1800145fd  call    WPP_SF_d
0x180014602  jmp     short loc_18001458C
0x180014604  test    byte ptr [rcx+44h], 20h
0x180014608  jz      loc_1800142A5
0x18001460e  mov     r9d, [rdi+9C0h]
0x180014615  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x18001461c  mov     rcx, [rcx+38h]
0x180014620  mov     edx, 62h ; 'b'
0x180014625  mov     [rsp+0F0h+var_D0], r15
0x18001462a  call    WPP_SF_Lq
0x18001462f  jmp     loc_1800142A5
0x180014634  test    byte ptr [rcx+44h], 20h
0x180014638  jz      loc_180014337
0x18001463e  movzx   r8d, byte ptr [r14+4]
0x180014643  mov     edx, 64h ; 'd'
0x180014648  movzx   r9d, byte ptr [r14+3]
0x18001464d  movzx   eax, byte ptr [r14+5]
0x180014652  movzx   r10d, byte ptr [r14+2]
0x180014657  movzx   r11d, byte ptr [r14+1]
0x18001465c  movzx   ebx, byte ptr [r14]
0x180014660  mov     rcx, [rcx+38h]
0x180014664  mov     [rsp+0F0h+var_A8], eax
0x180014668  mov     [rsp+0F0h+var_B0], r8d
0x18001466d  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x180014674  mov     [rsp+0F0h+var_B8], r9d
0x180014679  mov     r9d, [rdi+9C0h]
0x180014680  mov     [rsp+0F0h+var_C0], r10d
0x180014685  mov     dword ptr [rsp+0F0h+var_C8], r11d
0x18001468a  mov     dword ptr [rsp+0F0h+var_D0], ebx
0x18001468e  call    WPP_SF_LDDDDDD
0x180014693  jmp     loc_180014337
0x180014698  mov     ebx, 139Fh
0x18001469d  mov     r11, cs:WPP_GLOBAL_Control
0x1800146a4  lea     r15, WPP_GLOBAL_Control
0x1800146ab  cmp     r11, r15
0x1800146ae  jz      loc_18001447A
0x1800146b4  test    byte ptr [r11+44h], 1
0x1800146b9  jz      loc_180014467
0x1800146bf  mov     r10d, [rdi+0AA4h]
0x1800146c6  mov     r14d, 5
0x1800146cc  mov     ecx, r14d
0x1800146cf  call    ?IntfActionStr@@YAPEBGW4SECMGR_INTF_ACTION@@@Z; IntfActionStr(SECMGR_INTF_ACTION)
0x1800146d4  mov     ecx, r10d
0x1800146d7  mov     r8, rax
0x1800146da  call    ?IntfSecStateStr@@YAPEBGW4MSMSEC_INTF_SEC_STATE@@@Z; IntfSecStateStr(MSMSEC_INTF_SEC_STATE)
0x1800146df  mov     rcx, [r11+38h]
0x1800146e3  lea     edx, [r14+5Eh]
0x1800146e7  mov     [rsp+0F0h+var_C0], r14d
0x1800146ec  mov     r9, rax
0x1800146ef  mov     [rsp+0F0h+var_C8], r8
0x1800146f4  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x1800146fb  mov     dword ptr [rsp+0F0h+var_D0], r10d
0x180014700  call    WPP_SF_SLSL
0x180014705  jmp     loc_180014459
0x18001470a  mov     rcx, cs:WPP_GLOBAL_Control
0x180014711  cmp     rcx, rdi
0x180014714  jz      loc_18001455E
0x18001471a  test    byte ptr [rcx+44h], 1
0x18001471e  jz      loc_18001451A
0x180014724  mov     edx, 61h ; 'a'
0x180014729  mov     rcx, [rcx+38h]
0x18001472d  mov     r9d, eax
0x180014730  mov     r8, r13
0x180014733  call    WPP_SF_d
0x180014738  jmp     loc_180014513
0x18001473d  mov     rcx, [rcx+38h]
0x180014741  mov     edx, 5Eh ; '^'
  ... truncated ...
```
