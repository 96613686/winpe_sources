# MSMSecQueryAPPeerPSKIndex

- ea: `0x1800536d0`
- end: `0x1800539df`
- name: `MSMSecQueryAPPeerPSKIndex`
- size: `783`
- prototype: `__int64 __fastcall(void *, unsigned __int8 (*)[6])`
- caller_count: `0`
- callee_count: `15`
- tags: ``

## callees

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
- `0x18001a23c`
- `0x180030fec`
- `0x1800536d0`
- `0x1800558c0`
- `0x180056db8`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x18005392c`
- `MobileNetworking!ReleaseWriteLock` at `0x18005392c`

## pseudocode

```c
__int64 __fastcall MSMSecQueryAPPeerPSKIndex(void ***a1, unsigned __int8 (*a2)[6], unsigned int *a3)
{
  unsigned int v6; // eax
  unsigned int PortSendKeyIndex; // ebx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  unsigned int *v10; // rdi
  const wchar_t *v11; // rax
  unsigned int v12; // r10d
  __int64 v13; // rdx
  int v14; // eax
  __int64 v15; // r11
  __int64 v16; // r8
  char v17; // r10
  struct MSMSEC_INTF_CONTEXT *v18; // rcx
  struct MSMSEC_INTF_CONTEXT *v20; // [rsp+60h] [rbp-38h] BYREF
  unsigned int v21; // [rsp+B8h] [rbp+20h] BYREF

  v20 = 0;
  v21 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 292, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids);
  v6 = IncThreadCountAndCheckInitializedEx("MSMSecQueryAPPeerPSKIndex", 2632);
  PortSendKeyIndex = v6;
  if ( v6 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      v9 = 293;
LABEL_8:
      WPP_SF_d(v8[7], v9, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v6);
    }
  }
  else if ( a1 && a2 && a3 )
  {
    v6 = SecMgrValidateRefAndLockAdapter(a1, &v20);
    PortSendKeyIndex = v6;
    if ( v6 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        v9 = 295;
        goto LABEL_8;
      }
    }
    else
    {
      v10 = (unsigned int *)v20;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0 )
        WPP_SF_LqDDDDDD(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          296,
          &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids,
          *((unsigned int *)v20 + 624),
          a1,
          (*a2)[0],
          (*a2)[1],
          (*a2)[2],
          (*a2)[3],
          (*a2)[4],
          (*a2)[5]);
      if ( (unsigned int)IsValidIntfSecStateForAction(v10[681], 18) )
      {
        if ( (unsigned int)IntfIsInAPMode((struct MSMSEC_INTF_CONTEXT *)v10) )
        {
          PortSendKeyIndex = SecMgrGetPortSendKeyIndex(v18, a2, &v21);
          *a3 = v21;
        }
        else
        {
          PortSendKeyIndex = 5023;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 7),
              298,
              &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids,
              v10[624]);
        }
      }
      else
      {
        PortSendKeyIndex = 5023;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        {
          v11 = IntfActionStr(18);
          v14 = IntfSecStateStr(v12, v13, v11);
          WPP_SF_SLSL(
            *(_QWORD *)(v15 + 56),
            297,
            (unsigned int)&WPP_5807585f210c3b3262a513c5e260de7e_Traceguids,
            v14,
            v17,
            v16,
            18);
        }
      }
      TraceAdapterId(v10[624], "<<< Unlocking <<<");
      ReleaseWriteLock(v10, v10 + 628, "MSMSecQueryAPPeerPSKIndex", 2688);
      TraceAdapterId(v10[624], "<<< Derefing <<<");
      SecMgrDerefAdapterEx((struct MSMSEC_INTF_CONTEXT *)v10, "MSMSecQueryAPPeerPSKIndex", 2692);
    }
  }
  else
  {
    PortSendKeyIndex = 87;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 294, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids);
  }
  DecThreadCountEx("MSMSecQueryAPPeerPSKIndex", 2694);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      299,
      &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids,
      PortSendKeyIndex);
  return PortSendKeyIndex;
}

```

## disassembly

```asm
0x1800536d0  mov     rax, rsp
0x1800536d3  mov     [rax+8], rbx
0x1800536d7  mov     [rax+10h], rbp
0x1800536db  push    rsi
0x1800536dc  push    rdi
0x1800536dd  push    r12
0x1800536df  push    r14
0x1800536e1  push    r15
0x1800536e3  sub     rsp, 70h
0x1800536e7  mov     r14, r8
0x1800536ea  mov     qword ptr [rax-38h], 0
0x1800536f2  mov     rsi, rdx
0x1800536f5  mov     dword ptr [rax+20h], 0
0x1800536fc  mov     rbp, rcx
0x1800536ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180053706  lea     r15, WPP_GLOBAL_Control
0x18005370d  lea     r12, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x180053714  cmp     rcx, r15
0x180053717  jz      short loc_180053733
0x180053719  test    dword ptr [rcx+44h], 100h
0x180053720  jz      short loc_180053733
0x180053722  mov     rcx, [rcx+38h]
0x180053726  mov     edx, 124h
0x18005372b  mov     r8, r12
0x18005372e  call    WPP_SF_
0x180053733  mov     edx, 0A48h; int
0x180053738  lea     rcx, aMsmsecqueryapp_0; "MSMSecQueryAPPeerPSKIndex"
0x18005373f  call    ?IncThreadCountAndCheckInitializedEx@@YAKPEBDH@Z; IncThreadCountAndCheckInitializedEx(char const *,int)
0x180053744  mov     ebx, eax
0x180053746  test    eax, eax
0x180053748  jz      short loc_18005377D
0x18005374a  mov     rcx, cs:WPP_GLOBAL_Control
0x180053751  cmp     rcx, r15
0x180053754  jz      loc_180053989
0x18005375a  test    byte ptr [rcx+44h], 1
0x18005375e  jz      loc_180053989
0x180053764  mov     edx, 125h
0x180053769  mov     rcx, [rcx+38h]
0x18005376d  mov     r9d, eax
0x180053770  mov     r8, r12
0x180053773  call    WPP_SF_d
0x180053778  jmp     loc_180053989
0x18005377d  test    rbp, rbp
0x180053780  jz      loc_180053961
0x180053786  test    rsi, rsi
0x180053789  jz      loc_180053961
0x18005378f  test    r14, r14
0x180053792  jz      loc_180053961
0x180053798  lea     rdx, [rsp+98h+var_38]; struct MSMSEC_INTF_CONTEXT **
0x18005379d  mov     rcx, rbp; void *
0x1800537a0  call    ?SecMgrValidateRefAndLockAdapter@@YAKPEAXPEAPEAUMSMSEC_INTF_CONTEXT@@@Z; SecMgrValidateRefAndLockAdapter(void *,MSMSEC_INTF_CONTEXT * *)
0x1800537a5  mov     ebx, eax
0x1800537a7  test    eax, eax
0x1800537a9  jz      short loc_1800537CC
0x1800537ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800537b2  cmp     rcx, r15
0x1800537b5  jz      loc_180053989
0x1800537bb  test    byte ptr [rcx+44h], 1
0x1800537bf  jz      loc_180053989
0x1800537c5  mov     edx, 127h
0x1800537ca  jmp     short loc_180053769
0x1800537cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800537d3  mov     rdi, [rsp+98h+var_38]
0x1800537d8  cmp     rcx, r15
0x1800537db  jz      short loc_180053837
0x1800537dd  test    byte ptr [rcx+44h], 20h
0x1800537e1  jz      short loc_180053837
0x1800537e3  movzx   r8d, byte ptr [rsi+4]
0x1800537e8  mov     edx, 128h
0x1800537ed  movzx   r9d, byte ptr [rsi+3]
0x1800537f2  movzx   eax, byte ptr [rsi+5]
0x1800537f6  movzx   r10d, byte ptr [rsi+2]
0x1800537fb  movzx   r11d, byte ptr [rsi+1]
0x180053800  movzx   ebx, byte ptr [rsi]
0x180053803  mov     rcx, [rcx+38h]
0x180053807  mov     [rsp+98h+var_48], eax
0x18005380b  mov     [rsp+98h+var_50], r8d
0x180053810  mov     r8, r12
0x180053813  mov     [rsp+98h+var_58], r9d
0x180053818  mov     r9d, [rdi+9C0h]
0x18005381f  mov     [rsp+98h+var_60], r10d
0x180053824  mov     [rsp+98h+var_68], r11d
0x180053829  mov     dword ptr [rsp+98h+var_70], ebx
0x18005382d  mov     [rsp+98h+var_78], rbp
0x180053832  call    WPP_SF_LqDDDDDD
0x180053837  mov     ecx, [rdi+0AA4h]
0x18005383d  mov     ebp, 12h
0x180053842  mov     edx, ebp
0x180053844  call    ?IsValidIntfSecStateForAction@@YAHW4MSMSEC_INTF_SEC_STATE@@W4SECMGR_INTF_ACTION@@@Z; IsValidIntfSecStateForAction(MSMSEC_INTF_SEC_STATE,SECMGR_INTF_ACTION)
0x180053849  test    eax, eax
0x18005384b  jnz     short loc_1800538AA
0x18005384d  mov     ebx, 139Fh
0x180053852  mov     r11, cs:WPP_GLOBAL_Control
0x180053859  cmp     r11, r15
0x18005385c  jz      loc_180053903
0x180053862  test    byte ptr [r11+44h], 1
0x180053867  jz      loc_180053903
0x18005386d  mov     r10d, [rdi+0AA4h]
0x180053874  mov     ecx, ebp
0x180053876  call    ?IntfActionStr@@YAPEBGW4SECMGR_INTF_ACTION@@@Z; IntfActionStr(SECMGR_INTF_ACTION)
0x18005387b  mov     ecx, r10d
0x18005387e  mov     r8, rax
0x180053881  call    ?IntfSecStateStr@@YAPEBGW4MSMSEC_INTF_SEC_STATE@@@Z; IntfSecStateStr(MSMSEC_INTF_SEC_STATE)
0x180053886  mov     rcx, [r11+38h]
0x18005388a  mov     r9, rax
0x18005388d  mov     [rsp+98h+var_68], ebp
0x180053891  mov     edx, 129h
0x180053896  mov     [rsp+98h+var_70], r8
0x18005389b  mov     r8, r12
0x18005389e  mov     dword ptr [rsp+98h+var_78], r10d
0x1800538a3  call    WPP_SF_SLSL
0x1800538a8  jmp     short loc_180053903
0x1800538aa  mov     rcx, rdi; struct MSMSEC_INTF_CONTEXT *
0x1800538ad  call    ?IntfIsInAPMode@@YAHPEAUMSMSEC_INTF_CONTEXT@@@Z; IntfIsInAPMode(MSMSEC_INTF_CONTEXT *)
0x1800538b2  test    eax, eax
0x1800538b4  jnz     short loc_1800538E7
0x1800538b6  mov     ebx, 139Fh
0x1800538bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800538c2  cmp     rcx, r15
0x1800538c5  jz      short loc_180053903
0x1800538c7  test    byte ptr [rcx+44h], 1
0x1800538cb  jz      short loc_180053903
0x1800538cd  mov     r9d, [rdi+9C0h]
0x1800538d4  mov     edx, 12Ah
0x1800538d9  mov     rcx, [rcx+38h]
0x1800538dd  mov     r8, r12
0x1800538e0  call    WPP_SF_d
0x1800538e5  jmp     short loc_180053903
0x1800538e7  lea     r8, [rsp+98h+arg_18]; unsigned int *
0x1800538ef  mov     rdx, rsi; unsigned __int8 (*)[6]
0x1800538f2  call    ?SecMgrGetPortSendKeyIndex@@YAKPEAUMSMSEC_INTF_CONTEXT@@PEAY05EPEAK@Z; SecMgrGetPortSendKeyIndex(MSMSEC_INTF_CONTEXT *,uchar (*)[6],ulong *)
0x1800538f7  mov     ebx, eax
0x1800538f9  mov     eax, [rsp+98h+arg_18]
0x180053900  mov     [r14], eax
0x180053903  mov     ecx, [rdi+9C0h]; unsigned int
0x180053909  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x180053910  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180053915  lea     rdx, [rdi+9D0h]
0x18005391c  mov     r9d, 0A80h
0x180053922  lea     r8, aMsmsecqueryapp_0; "MSMSecQueryAPPeerPSKIndex"
0x180053929  mov     rcx, rdi
0x18005392c  call    cs:__imp_ReleaseWriteLock
0x180053933  nop     dword ptr [rax+rax+00h]
0x180053938  mov     ecx, [rdi+9C0h]; unsigned int
0x18005393e  lea     rdx, aDerefing; "<<< Derefing <<<"
0x180053945  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x18005394a  mov     r8d, 0A84h; int
0x180053950  lea     rdx, aMsmsecqueryapp_0; "MSMSecQueryAPPeerPSKIndex"
0x180053957  mov     rcx, rdi; struct MSMSEC_INTF_CONTEXT *
0x18005395a  call    ?SecMgrDerefAdapterEx@@YAXPEAUMSMSEC_INTF_CONTEXT@@PEBDH@Z; SecMgrDerefAdapterEx(MSMSEC_INTF_CONTEXT *,char const *,int)
0x18005395f  jmp     short loc_180053989
0x180053961  mov     ebx, 57h ; 'W'
0x180053966  mov     rcx, cs:WPP_GLOBAL_Control
0x18005396d  cmp     rcx, r15
0x180053970  jz      short loc_180053989
0x180053972  test    byte ptr [rcx+44h], 1
0x180053976  jz      short loc_180053989
0x180053978  mov     rcx, [rcx+38h]
0x18005397c  mov     edx, 126h
0x180053981  mov     r8, r12
0x180053984  call    WPP_SF_
0x180053989  mov     edx, 0A86h; int
0x18005398e  lea     rcx, aMsmsecqueryapp_0; "MSMSecQueryAPPeerPSKIndex"
0x180053995  call    ?DecThreadCountEx@@YAXPEBDH@Z; DecThreadCountEx(char const *,int)
0x18005399a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800539a1  cmp     rcx, r15
0x1800539a4  jz      short loc_1800539C3
0x1800539a6  test    dword ptr [rcx+44h], 100h
0x1800539ad  jz      short loc_1800539C3
0x1800539af  mov     rcx, [rcx+38h]
0x1800539b3  mov     edx, 12Bh
0x1800539b8  mov     r9d, ebx
0x1800539bb  mov     r8, r12
0x1800539be  call    WPP_SF_d
0x1800539c3  lea     r11, [rsp+98h+var_28]
0x1800539c8  mov     eax, ebx
0x1800539ca  mov     rbx, [r11+30h]
0x1800539ce  mov     rbp, [r11+38h]
0x1800539d2  mov     rsp, r11
0x1800539d5  pop     r15
0x1800539d7  pop     r14
0x1800539d9  pop     r12
0x1800539db  pop     rdi
0x1800539dc  pop     rsi
0x1800539dd  retn
```
