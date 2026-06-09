# UIRequestWorker(void *)

- ea: `0x1800363c0`
- end: `0x1800366db`
- name: `?UIRequestWorker@@YAKPEAX@Z`
- size: `795`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `18`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000892c`
- `0x180008998`
- `0x18000a26c`
- `0x18000b6dc`
- `0x18000e620`
- `0x1800125b0`
- `0x180013bc0`
- `0x180014998`
- `0x1800163e0`
- `0x1800169c0`
- `0x180016a08`
- `0x18001df24`
- `0x18001df84`
- `0x18002589c`
- `0x18002bb50`
- `0x1800328b0`
- `0x1800363c0`
- `0x1800558c0`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x180036632`
- `MobileNetworking!ReleaseWriteLock` at `0x180036632`

## pseudocode

```c
__int64 __fastcall UIRequestWorker(void ****Parameter, unsigned int a2)
{
  PVOID *v3; // rcx
  unsigned int v4; // ebx
  unsigned int v5; // eax
  unsigned int v6; // ebp
  unsigned int v7; // eax
  struct MSMSEC_INTF_CONTEXT *v8; // rsi
  const wchar_t *v9; // rax
  unsigned int v10; // r10d
  __int64 v11; // rdx
  int v12; // eax
  __int64 v13; // r11
  __int64 v14; // r8
  char v15; // r10
  struct MSMSEC_INTF_CONTEXT *v17; // [rsp+70h] [rbp+8h] BYREF
  void ****v18; // [rsp+78h] [rbp+10h] BYREF

  v17 = 0;
  v3 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 103, &WPP_b56916f94f50376d7382066de30fa1b3_Traceguids);
    v3 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( Parameter )
  {
    v18 = Parameter;
    NetTraceBeginContextActivity(Parameter, a2);
    v5 = MSMUIRequest(
           Parameter[2],
           *((_DWORD *)Parameter + 6),
           (struct MSMSEC_UI_REQUEST *)Parameter[4],
           0,
           0,
           &g_SecurityClsid,
           (unsigned int (*)(void *, struct _GUID *, struct _L2_UI_REQUEST *, int))Parameter[5]);
    v4 = v5;
    if ( v5 )
    {
      v6 = v5;
      v7 = SecMgrValidateRefAndLockAdapter(*Parameter, &v17);
      v4 = v7;
      if ( v7 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 106, &WPP_b56916f94f50376d7382066de30fa1b3_Traceguids, v7);
      }
      else
      {
        v8 = v17;
        if ( Parameter[1] == *((void ****)v17 + 328) )
        {
          if ( (unsigned int)IsValidIntfSecStateForAction(*((unsigned int *)v17 + 681), 8) )
          {
            SecMgrIntfStateTransition(v8, 8, 294913);
            MSMConnectCompletion(
              *((_DWORD *)v8 + 624),
              Parameter[2],
              Parameter[1],
              0x48001u,
              v6,
              *((unsigned int (**)(void *, void *, unsigned int, unsigned int))v8 + 269));
          }
          else
          {
            v4 = 5023;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
            {
              v9 = IntfActionStr(8);
              v12 = IntfSecStateStr(v10, v11, v9);
              WPP_SF_SLSL(
                *(_QWORD *)(v13 + 56),
                108,
                (unsigned int)&WPP_b56916f94f50376d7382066de30fa1b3_Traceguids,
                v12,
                v15,
                v14,
                8);
            }
          }
        }
        else
        {
          v4 = 1223;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
            WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 7), 107, &WPP_b56916f94f50376d7382066de30fa1b3_Traceguids);
        }
        TraceAdapterId(*((_DWORD *)v8 + 624), "<<< Unlocking <<<");
        ReleaseWriteLock(v8, (char *)v8 + 2512, "UIRequestWorker", 1063);
        TraceAdapterId(*((_DWORD *)v8 + 624), "<<< Derefing <<<");
        SecMgrDerefAdapterEx(v8, "UIRequestWorker", 1064);
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 105, &WPP_b56916f94f50376d7382066de30fa1b3_Traceguids);
    }
    NetTraceEndContextActivity(Parameter, 0x13u);
    FreeMSMSecMemory(Parameter + 4);
    FreeMSMSecMemory(&v18);
  }
  else
  {
    v4 = 87;
    if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 68) & 1) != 0 )
      WPP_SF_(v3[7], 104, &WPP_b56916f94f50376d7382066de30fa1b3_Traceguids);
  }
  DecThreadCountEx("UIRequestWorker", 1077);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 109, &WPP_b56916f94f50376d7382066de30fa1b3_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x1800363c0  mov     [rsp+arg_10], rbx
0x1800363c5  mov     [rsp+arg_18], rbp
0x1800363ca  push    rsi
0x1800363cb  push    rdi
0x1800363cc  push    r12
0x1800363ce  push    r13
0x1800363d0  push    r14
0x1800363d2  sub     rsp, 40h
0x1800363d6  mov     rdi, rcx
0x1800363d9  mov     [rsp+68h+arg_0], 0
0x1800363e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800363e9  lea     r12, WPP_GLOBAL_Control
0x1800363f0  lea     r13, WPP_b56916f94f50376d7382066de30fa1b3_Traceguids
0x1800363f7  cmp     rcx, r12
0x1800363fa  jz      short loc_18003641D
0x1800363fc  test    dword ptr [rcx+44h], 100h
0x180036403  jz      short loc_18003641D
0x180036405  mov     rcx, [rcx+38h]
0x180036409  mov     edx, 67h ; 'g'
0x18003640e  mov     r8, r13
0x180036411  call    WPP_SF_
0x180036416  mov     rcx, cs:WPP_GLOBAL_Control
0x18003641d  test    rdi, rdi
0x180036420  jnz     short loc_18003644C
0x180036422  lea     ebx, [rdi+57h]
0x180036425  cmp     rcx, r12
0x180036428  jz      loc_180036685
0x18003642e  test    byte ptr [rcx+44h], 1
0x180036432  jz      loc_180036685
0x180036438  mov     rcx, [rcx+38h]
0x18003643c  lea     edx, [rdi+68h]
0x18003643f  mov     r8, r13
0x180036442  call    WPP_SF_
0x180036447  jmp     loc_180036685
0x18003644c  mov     rcx, rdi; void *
0x18003644f  mov     [rsp+68h+arg_8], rdi
0x180036454  call    ?NetTraceBeginContextActivity@@YAXPEAXI@Z; NetTraceBeginContextActivity(void *,uint)
0x180036459  mov     rax, [rdi+28h]
0x18003645d  xor     r9d, r9d; unsigned int
0x180036460  mov     r8, [rdi+20h]; struct MSMSEC_UI_REQUEST *
0x180036464  mov     edx, [rdi+18h]; unsigned int
0x180036467  mov     rcx, [rdi+10h]; void *
0x18003646b  mov     [rsp+68h+var_38], rax; unsigned int (*)(void *, struct _GUID *, struct _L2_UI_REQUEST *, int)
0x180036470  lea     rax, ?g_SecurityClsid@@3U_GUID@@A; _GUID g_SecurityClsid
0x180036477  mov     [rsp+68h+var_40], rax; struct _GUID *
0x18003647c  mov     [rsp+68h+var_48], 0; int
0x180036484  call    ?MSMUIRequest@@YAKPEAXKPEAUMSMSEC_UI_REQUEST@@KHPEAU_GUID@@P6AK02PEAU_L2_UI_REQUEST@@H@Z@Z; MSMUIRequest(void *,ulong,MSMSEC_UI_REQUEST *,ulong,int,_GUID *,ulong (*)(void *,_GUID *,_L2_UI_REQUEST *,int))
0x180036489  mov     ebx, eax
0x18003648b  test    eax, eax
0x18003648d  jnz     short loc_1800364BD
0x18003648f  mov     rcx, cs:WPP_GLOBAL_Control
0x180036496  cmp     rcx, r12
0x180036499  jz      loc_180036665
0x18003649f  test    byte ptr [rcx+44h], 2
0x1800364a3  jz      loc_180036665
0x1800364a9  mov     rcx, [rcx+38h]
0x1800364ad  lea     edx, [rax+69h]
0x1800364b0  mov     r8, r13
0x1800364b3  call    WPP_SF_
0x1800364b8  jmp     loc_180036665
0x1800364bd  mov     rcx, [rdi]; void *
0x1800364c0  lea     rdx, [rsp+68h+arg_0]; struct MSMSEC_INTF_CONTEXT **
0x1800364c5  mov     ebp, eax
0x1800364c7  call    ?SecMgrValidateRefAndLockAdapter@@YAKPEAXPEAPEAUMSMSEC_INTF_CONTEXT@@@Z; SecMgrValidateRefAndLockAdapter(void *,MSMSEC_INTF_CONTEXT * *)
0x1800364cc  mov     ebx, eax
0x1800364ce  test    eax, eax
0x1800364d0  jz      short loc_180036505
0x1800364d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800364d9  cmp     rcx, r12
0x1800364dc  jz      loc_180036665
0x1800364e2  test    byte ptr [rcx+44h], 1
0x1800364e6  jz      loc_180036665
0x1800364ec  mov     rcx, [rcx+38h]
0x1800364f0  mov     edx, 6Ah ; 'j'
0x1800364f5  mov     r9d, eax
0x1800364f8  mov     r8, r13
0x1800364fb  call    WPP_SF_d
0x180036500  jmp     loc_180036665
0x180036505  mov     rsi, [rsp+68h+arg_0]
0x18003650a  mov     r9, [rdi+8]
0x18003650e  mov     rax, [rsi+0A40h]
0x180036515  cmp     r9, rax
0x180036518  jz      short loc_180036554
0x18003651a  mov     ebx, 4C7h
0x18003651f  mov     rcx, cs:WPP_GLOBAL_Control
0x180036526  cmp     rcx, r12
0x180036529  jz      loc_180036609
0x18003652f  test    byte ptr [rcx+44h], 1
0x180036533  jz      loc_180036609
0x180036539  mov     rcx, [rcx+38h]
0x18003653d  mov     edx, 6Bh ; 'k'
0x180036542  mov     r8, r13
0x180036545  mov     qword ptr [rsp+68h+var_48], rax
0x18003654a  call    WPP_SF_qq
0x18003654f  jmp     loc_180036609
0x180036554  mov     ecx, [rsi+0AA4h]
0x18003655a  mov     edx, 8
0x18003655f  call    ?IsValidIntfSecStateForAction@@YAHW4MSMSEC_INTF_SEC_STATE@@W4SECMGR_INTF_ACTION@@@Z; IsValidIntfSecStateForAction(MSMSEC_INTF_SEC_STATE,SECMGR_INTF_ACTION)
0x180036564  test    eax, eax
0x180036566  jnz     short loc_1800365CA
0x180036568  mov     ebx, 139Fh
0x18003656d  mov     r11, cs:WPP_GLOBAL_Control
0x180036574  cmp     r11, r12
0x180036577  jz      loc_180036609
0x18003657d  test    byte ptr [r11+44h], 1
0x180036582  jz      loc_180036609
0x180036588  mov     r10d, [rsi+0AA4h]
0x18003658f  lea     ecx, [rax+8]
0x180036592  call    ?IntfActionStr@@YAPEBGW4SECMGR_INTF_ACTION@@@Z; IntfActionStr(SECMGR_INTF_ACTION)
0x180036597  mov     ecx, r10d
0x18003659a  mov     r8, rax
0x18003659d  call    ?IntfSecStateStr@@YAPEBGW4MSMSEC_INTF_SEC_STATE@@@Z; IntfSecStateStr(MSMSEC_INTF_SEC_STATE)
0x1800365a2  mov     rcx, [r11+38h]
0x1800365a6  mov     r9, rax
0x1800365a9  mov     dword ptr [rsp+68h+var_38], 8
0x1800365b1  mov     edx, 6Ch ; 'l'
0x1800365b6  mov     [rsp+68h+var_40], r8
0x1800365bb  mov     r8, r13
0x1800365be  mov     [rsp+68h+var_48], r10d
0x1800365c3  call    WPP_SF_SLSL
0x1800365c8  jmp     short loc_180036609
0x1800365ca  mov     r9d, ebp
0x1800365cd  mov     edx, 8
0x1800365d2  mov     r8d, 48001h
0x1800365d8  mov     rcx, rsi
0x1800365db  call    ?SecMgrIntfStateTransition@@YAXPEAUMSMSEC_INTF_CONTEXT@@W4MSMSEC_INTF_SEC_STATE@@KK@Z; SecMgrIntfStateTransition(MSMSEC_INTF_CONTEXT *,MSMSEC_INTF_SEC_STATE,ulong,ulong)
0x1800365e0  mov     rax, [rsi+868h]
0x1800365e7  mov     r9d, 48001h; unsigned int
0x1800365ed  mov     r8, [rdi+8]; void *
0x1800365f1  mov     rdx, [rdi+10h]; void *
0x1800365f5  mov     ecx, [rsi+9C0h]; unsigned int
0x1800365fb  mov     [rsp+68h+var_40], rax; unsigned int (*)(void *, void *, unsigned int, unsigned int)
0x180036600  mov     [rsp+68h+var_48], ebp; unsigned int
0x180036604  call    ?MSMConnectCompletion@@YAKKPEAX0KKP6AK00KK@Z@Z; MSMConnectCompletion(ulong,void *,void *,ulong,ulong,ulong (*)(void *,void *,ulong,ulong))
0x180036609  mov     ecx, [rsi+9C0h]; unsigned int
0x18003660f  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x180036616  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x18003661b  lea     rdx, [rsi+9D0h]
0x180036622  mov     r9d, 427h
0x180036628  lea     r8, aUirequestworke; "UIRequestWorker"
0x18003662f  mov     rcx, rsi
0x180036632  call    cs:__imp_ReleaseWriteLock
0x180036639  nop     dword ptr [rax+rax+00h]
0x18003663e  mov     ecx, [rsi+9C0h]; unsigned int
0x180036644  lea     rdx, aDerefing; "<<< Derefing <<<"
0x18003664b  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180036650  mov     r8d, 428h; int
0x180036656  lea     rdx, aUirequestworke; "UIRequestWorker"
0x18003665d  mov     rcx, rsi; struct MSMSEC_INTF_CONTEXT *
0x180036660  call    ?SecMgrDerefAdapterEx@@YAXPEAUMSMSEC_INTF_CONTEXT@@PEBDH@Z; SecMgrDerefAdapterEx(MSMSEC_INTF_CONTEXT *,char const *,int)
0x180036665  mov     edx, 13h; unsigned int
0x18003666a  mov     rcx, rdi; void *
0x18003666d  call    ?NetTraceEndContextActivity@@YAXPEAXI@Z; NetTraceEndContextActivity(void *,uint)
0x180036672  lea     rcx, [rdi+20h]
0x180036676  call    FreeMSMSecMemory
0x18003667b  lea     rcx, [rsp+68h+arg_8]
0x180036680  call    FreeMSMSecMemory
0x180036685  mov     edx, 435h; int
0x18003668a  lea     rcx, aUirequestworke; "UIRequestWorker"
0x180036691  call    ?DecThreadCountEx@@YAXPEBDH@Z; DecThreadCountEx(char const *,int)
0x180036696  mov     rcx, cs:WPP_GLOBAL_Control
0x18003669d  cmp     rcx, r12
0x1800366a0  jz      short loc_1800366BF
0x1800366a2  test    dword ptr [rcx+44h], 100h
0x1800366a9  jz      short loc_1800366BF
0x1800366ab  mov     rcx, [rcx+38h]
0x1800366af  mov     edx, 6Dh ; 'm'
0x1800366b4  mov     r9d, ebx
0x1800366b7  mov     r8, r13
0x1800366ba  call    WPP_SF_d
0x1800366bf  lea     r11, [rsp+68h+var_28]
0x1800366c4  mov     eax, ebx
0x1800366c6  mov     rbx, [r11+40h]
0x1800366ca  mov     rbp, [r11+48h]
0x1800366ce  mov     rsp, r11
0x1800366d1  pop     r14
0x1800366d3  pop     r13
0x1800366d5  pop     r12
0x1800366d7  pop     rdi
0x1800366d8  pop     rsi
0x1800366d9  retn
```
