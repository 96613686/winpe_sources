# MSMSecSetWcnOneXEnable

- ea: `0x1800552e0`
- end: `0x180055691`
- name: `MSMSecSetWcnOneXEnable`
- size: `945`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `16`
- tags: ``

## callees

- `0x18000431c`
- `0x18000892c`
- `0x180008998`
- `0x18000a26c`
- `0x1800125b0`
- `0x180013bc0`
- `0x1800148d0`
- `0x180014998`
- `0x1800163e0`
- `0x1800169c0`
- `0x180016a08`
- `0x18003c528`
- `0x1800552e0`
- `0x18005585c`
- `0x1800558c0`
- `0x180074d5c`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x180055584`
- `MobileNetworking!ReleaseWriteLock` at `0x1800555e6`
- `MobileNetworking!ReleaseWriteLock` at `0x180055584`
- `MobileNetworking!ReleaseWriteLock` at `0x1800555e6`

## pseudocode

```c
__int64 __fastcall MSMSecSetWcnOneXEnable(void ***a1, unsigned int a2)
{
  unsigned int v4; // eax
  unsigned int v5; // edi
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  unsigned int *v8; // rsi
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // rax
  unsigned int v13; // r10d
  __int64 v14; // rdx
  int v15; // eax
  __int64 v16; // r11
  __int64 v17; // r8
  char v18; // r10
  PVOID *v19; // rcx
  int v20; // ebx
  unsigned int v21; // eax
  PVOID *v22; // rcx
  struct MSMSEC_INTF_CONTEXT *v24; // [rsp+80h] [rbp+18h] BYREF

  v24 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 260, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids);
  v4 = IncThreadCountAndCheckInitializedEx("MSMSecSetWcnOneXEnable", 2300);
  v5 = v4;
  if ( v4 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      v7 = 261;
LABEL_8:
      WPP_SF_d(v6[7], v7, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v4);
      goto LABEL_47;
    }
    goto LABEL_47;
  }
  if ( !a1 )
  {
    v5 = 87;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 262, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids);
    goto LABEL_47;
  }
  v4 = SecMgrValidateRefAndLockAdapter(a1, &v24);
  v5 = v4;
  if ( !v4 )
  {
    v8 = (unsigned int *)v24;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0 )
      WPP_SF_Lqd(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        264,
        &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids,
        *((unsigned int *)v24 + 624),
        a1,
        a2);
    if ( !(unsigned int)IsValidIntfSecStateForAction(v8[681], 14) )
    {
      v5 = 5023;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        v12 = IntfActionStr(14, v9, v10, v11);
        v15 = IntfSecStateStr(v13, v14, v12);
        WPP_SF_SLSL(
          *(_QWORD *)(v16 + 56),
          265,
          (unsigned int)&WPP_5807585f210c3b3262a513c5e260de7e_Traceguids,
          v15,
          v18,
          v17,
          14);
      }
LABEL_36:
      TraceAdapterId(v8[624], "<<< Unlocking <<<");
      ReleaseWriteLock(v8, v8 + 628, "MSMSecSetWcnOneXEnable", 2366);
LABEL_46:
      TraceAdapterId(v8[624], "<<< Derefing <<<");
      SecMgrDerefAdapterEx((struct MSMSEC_INTF_CONTEXT *)v8, "MSMSecSetWcnOneXEnable", 2370);
      goto LABEL_47;
    }
    v19 = (PVOID *)WPP_GLOBAL_Control;
    v20 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0 )
    {
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 266, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, a2, v8[695]);
      v19 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v8[695] == a2 )
    {
      if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 68) & 0x20) != 0 )
        WPP_SF_d(v19[7], 269, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, a2);
    }
    else
    {
      if ( a2 )
      {
        v21 = WpsAuthMgrInitializeWcnOneX();
        v5 = v21;
        v22 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 267, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v21);
          v22 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v5 )
        {
          if ( v22 != &WPP_GLOBAL_Control && (*((_BYTE *)v22 + 68) & 1) != 0 )
            WPP_SF_d(v22[7], 268, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v5);
          goto LABEL_36;
        }
      }
      else
      {
        v20 = 1;
      }
      v8[695] = a2;
    }
    TraceAdapterId(v8[624], "<<< Unlocking <<<");
    ReleaseWriteLock(v8, v8 + 628, "MSMSecSetWcnOneXEnable", 2354);
    if ( v20 )
    {
      WpsAuthMgrDeinitializeWcnOneX();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 270, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids);
    }
    goto LABEL_46;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    v7 = 263;
    goto LABEL_8;
  }
LABEL_47:
  DecThreadCountEx("MSMSecSetWcnOneXEnable", 2372);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 271, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x1800552e0  mov     rax, rsp
0x1800552e3  mov     [rax+8], rbx
0x1800552e7  mov     [rax+10h], rbp
0x1800552eb  push    rsi
0x1800552ec  push    rdi
0x1800552ed  push    r13
0x1800552ef  push    r14
0x1800552f1  push    r15
0x1800552f3  sub     rsp, 40h
0x1800552f7  mov     ebp, edx
0x1800552f9  mov     qword ptr [rax+18h], 0
0x180055301  mov     rbx, rcx
0x180055304  mov     rcx, cs:WPP_GLOBAL_Control
0x18005530b  lea     r14, WPP_GLOBAL_Control
0x180055312  lea     r15, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x180055319  cmp     rcx, r14
0x18005531c  jz      short loc_180055338
0x18005531e  test    dword ptr [rcx+44h], 100h
0x180055325  jz      short loc_180055338
0x180055327  mov     rcx, [rcx+38h]
0x18005532b  mov     edx, 104h
0x180055330  mov     r8, r15
0x180055333  call    WPP_SF_
0x180055338  lea     r13, aMsmsecsetwcnon_0; "MSMSecSetWcnOneXEnable"
0x18005533f  mov     edx, 8FCh; int
0x180055344  mov     rcx, r13; char *
0x180055347  call    ?IncThreadCountAndCheckInitializedEx@@YAKPEBDH@Z; IncThreadCountAndCheckInitializedEx(char const *,int)
0x18005534c  mov     edi, eax
0x18005534e  test    eax, eax
0x180055350  jz      short loc_180055389
0x180055352  mov     rcx, cs:WPP_GLOBAL_Control
0x180055359  cmp     rcx, r14
0x18005535c  jz      loc_180055641
0x180055362  mov     ebx, 1
0x180055367  test    [rcx+44h], bl
0x18005536a  jz      loc_180055641
0x180055370  mov     edx, 105h
0x180055375  mov     rcx, [rcx+38h]
0x180055379  mov     r9d, eax
0x18005537c  mov     r8, r15
0x18005537f  call    WPP_SF_d
0x180055384  jmp     loc_180055641
0x180055389  test    rbx, rbx
0x18005538c  jnz     short loc_1800553C3
0x18005538e  lea     edi, [rbx+57h]
0x180055391  mov     rcx, cs:WPP_GLOBAL_Control
0x180055398  cmp     rcx, r14
0x18005539b  jz      loc_180055641
0x1800553a1  lea     ebx, [rdi-56h]
0x1800553a4  test    [rcx+44h], bl
0x1800553a7  jz      loc_180055641
0x1800553ad  mov     rcx, [rcx+38h]
0x1800553b1  mov     edx, 106h
0x1800553b6  mov     r8, r15
0x1800553b9  call    WPP_SF_
0x1800553be  jmp     loc_180055641
0x1800553c3  lea     rdx, [rsp+68h+arg_10]; struct MSMSEC_INTF_CONTEXT **
0x1800553cb  mov     rcx, rbx; void *
0x1800553ce  call    ?SecMgrValidateRefAndLockAdapter@@YAKPEAXPEAPEAUMSMSEC_INTF_CONTEXT@@@Z; SecMgrValidateRefAndLockAdapter(void *,MSMSEC_INTF_CONTEXT * *)
0x1800553d3  mov     edi, eax
0x1800553d5  test    eax, eax
0x1800553d7  jz      short loc_180055401
0x1800553d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800553e0  cmp     rcx, r14
0x1800553e3  jz      loc_180055641
0x1800553e9  mov     ebx, 1
0x1800553ee  test    [rcx+44h], bl
0x1800553f1  jz      loc_180055641
0x1800553f7  mov     edx, 107h
0x1800553fc  jmp     loc_180055375
0x180055401  mov     rcx, cs:WPP_GLOBAL_Control
0x180055408  mov     rsi, [rsp+68h+arg_10]
0x180055410  cmp     rcx, r14
0x180055413  jz      short loc_18005543C
0x180055415  test    byte ptr [rcx+44h], 20h
0x180055419  jz      short loc_18005543C
0x18005541b  mov     r9d, [rsi+9C0h]
0x180055422  mov     edx, 108h
0x180055427  mov     rcx, [rcx+38h]
0x18005542b  mov     r8, r15
0x18005542e  mov     dword ptr [rsp+68h+var_40], ebp
0x180055432  mov     [rsp+68h+var_48], rbx
0x180055437  call    WPP_SF_Lqd
0x18005543c  mov     ecx, [rsi+0AA4h]
0x180055442  mov     edx, 0Eh
0x180055447  call    ?IsValidIntfSecStateForAction@@YAHW4MSMSEC_INTF_SEC_STATE@@W4SECMGR_INTF_ACTION@@@Z; IsValidIntfSecStateForAction(MSMSEC_INTF_SEC_STATE,SECMGR_INTF_ACTION)
0x18005544c  test    eax, eax
0x18005544e  jnz     short loc_1800554B7
0x180055450  mov     edi, 139Fh
0x180055455  mov     r11, cs:WPP_GLOBAL_Control
0x18005545c  cmp     r11, r14
0x18005545f  jz      loc_18005555F
0x180055465  lea     ebx, [rax+1]
0x180055468  test    [r11+44h], bl
0x18005546c  jz      loc_18005555F
0x180055472  mov     r10d, [rsi+0AA4h]
0x180055479  lea     ecx, [rax+0Eh]
0x18005547c  call    ?IntfActionStr@@YAPEBGW4SECMGR_INTF_ACTION@@@Z; IntfActionStr(SECMGR_INTF_ACTION)
0x180055481  mov     ecx, r10d
0x180055484  mov     r8, rax
0x180055487  call    ?IntfSecStateStr@@YAPEBGW4MSMSEC_INTF_SEC_STATE@@@Z; IntfSecStateStr(MSMSEC_INTF_SEC_STATE)
0x18005548c  mov     rcx, [r11+38h]
0x180055490  mov     r9, rax
0x180055493  mov     [rsp+68h+var_38], 0Eh
0x18005549b  mov     edx, 109h
0x1800554a0  mov     [rsp+68h+var_40], r8
0x1800554a5  mov     r8, r15
0x1800554a8  mov     dword ptr [rsp+68h+var_48], r10d
0x1800554ad  call    WPP_SF_SLSL
0x1800554b2  jmp     loc_18005555F
0x1800554b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800554be  xor     ebx, ebx
0x1800554c0  cmp     rcx, r14
0x1800554c3  jz      short loc_1800554F0
0x1800554c5  test    byte ptr [rcx+44h], 2
0x1800554c9  jz      short loc_1800554F0
0x1800554cb  mov     eax, [rsi+0ADCh]
0x1800554d1  mov     edx, 10Ah
0x1800554d6  mov     rcx, [rcx+38h]
0x1800554da  mov     r9d, ebp
0x1800554dd  mov     r8, r15
0x1800554e0  mov     dword ptr [rsp+68h+var_48], eax
0x1800554e4  call    WPP_SF_dd
0x1800554e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800554f0  cmp     [rsi+0ADCh], ebp
0x1800554f6  jz      loc_1800555A2
0x1800554fc  test    ebp, ebp
0x1800554fe  jz      loc_180055595
0x180055504  call    ?WpsAuthMgrInitializeWcnOneX@@YAKXZ; WpsAuthMgrInitializeWcnOneX(void)
0x180055509  mov     edi, eax
0x18005550b  mov     rcx, cs:WPP_GLOBAL_Control
0x180055512  cmp     rcx, r14
0x180055515  jz      short loc_180055538
0x180055517  test    byte ptr [rcx+44h], 2
0x18005551b  jz      short loc_180055538
0x18005551d  mov     rcx, [rcx+38h]
0x180055521  mov     edx, 10Bh
0x180055526  mov     r9d, eax
0x180055529  mov     r8, r15
0x18005552c  call    WPP_SF_d
0x180055531  mov     rcx, cs:WPP_GLOBAL_Control
0x180055538  test    edi, edi
0x18005553a  jz      short loc_18005559A
0x18005553c  cmp     rcx, r14
0x18005553f  jz      short loc_18005555F
0x180055541  mov     ebx, 1
0x180055546  test    [rcx+44h], bl
0x180055549  jz      short loc_18005555F
0x18005554b  mov     rcx, [rcx+38h]
0x18005554f  mov     edx, 10Ch
0x180055554  mov     r9d, edi
0x180055557  mov     r8, r15
0x18005555a  call    WPP_SF_d
0x18005555f  mov     ecx, [rsi+9C0h]; unsigned int
0x180055565  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x18005556c  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180055571  lea     rdx, [rsi+9D0h]
0x180055578  mov     r9d, 93Eh
0x18005557e  mov     r8, r13
0x180055581  mov     rcx, rsi
0x180055584  call    cs:__imp_ReleaseWriteLock
0x18005558b  nop     dword ptr [rax+rax+00h]
0x180055590  jmp     loc_18005561E
0x180055595  mov     ebx, 1
0x18005559a  mov     [rsi+0ADCh], ebp
0x1800555a0  jmp     short loc_1800555C1
0x1800555a2  cmp     rcx, r14
0x1800555a5  jz      short loc_1800555C1
0x1800555a7  test    byte ptr [rcx+44h], 20h
0x1800555ab  jz      short loc_1800555C1
0x1800555ad  mov     rcx, [rcx+38h]
0x1800555b1  mov     edx, 10Dh
0x1800555b6  mov     r9d, ebp
0x1800555b9  mov     r8, r15
0x1800555bc  call    WPP_SF_d
0x1800555c1  mov     ecx, [rsi+9C0h]; unsigned int
0x1800555c7  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x1800555ce  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x1800555d3  lea     rdx, [rsi+9D0h]
0x1800555da  mov     r9d, 932h
0x1800555e0  mov     r8, r13
0x1800555e3  mov     rcx, rsi
0x1800555e6  call    cs:__imp_ReleaseWriteLock
0x1800555ed  nop     dword ptr [rax+rax+00h]
0x1800555f2  test    ebx, ebx
0x1800555f4  jz      short loc_18005561E
0x1800555f6  call    ?WpsAuthMgrDeinitializeWcnOneX@@YAXXZ; WpsAuthMgrDeinitializeWcnOneX(void)
0x1800555fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180055602  cmp     rcx, r14
0x180055605  jz      short loc_18005561E
0x180055607  test    byte ptr [rcx+44h], 2
0x18005560b  jz      short loc_18005561E
0x18005560d  mov     rcx, [rcx+38h]
0x180055611  mov     edx, 10Eh
0x180055616  mov     r8, r15
0x180055619  call    WPP_SF_
0x18005561e  mov     ecx, [rsi+9C0h]; unsigned int
0x180055624  lea     rdx, aDerefing; "<<< Derefing <<<"
0x18005562b  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180055630  mov     r8d, 942h; int
0x180055636  mov     rdx, r13; char *
0x180055639  mov     rcx, rsi; struct MSMSEC_INTF_CONTEXT *
0x18005563c  call    ?SecMgrDerefAdapterEx@@YAXPEAUMSMSEC_INTF_CONTEXT@@PEBDH@Z; SecMgrDerefAdapterEx(MSMSEC_INTF_CONTEXT *,char const *,int)
0x180055641  mov     edx, 944h; int
0x180055646  mov     rcx, r13; char *
0x180055649  call    ?DecThreadCountEx@@YAXPEBDH@Z; DecThreadCountEx(char const *,int)
0x18005564e  mov     rcx, cs:WPP_GLOBAL_Control
0x180055655  cmp     rcx, r14
0x180055658  jz      short loc_180055677
0x18005565a  test    dword ptr [rcx+44h], 100h
0x180055661  jz      short loc_180055677
0x180055663  mov     rcx, [rcx+38h]
0x180055667  mov     edx, 10Fh
0x18005566c  mov     r9d, edi
0x18005566f  mov     r8, r15
0x180055672  call    WPP_SF_d
0x180055677  mov     rbx, [rsp+68h+arg_0]
0x18005567c  mov     eax, edi
0x18005567e  mov     rbp, [rsp+68h+arg_8]
0x180055683  add     rsp, 40h
0x180055687  pop     r15
0x180055689  pop     r14
0x18005568b  pop     r13
0x18005568d  pop     rdi
0x18005568e  pop     rsi
0x18005568f  retn
```
