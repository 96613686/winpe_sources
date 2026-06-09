# MSMSecGetPeerIpAddress

- ea: `0x180052fa0`
- end: `0x1800532b1`
- name: `MSMSecGetPeerIpAddress`
- size: `785`
- prototype: `__int64 __fastcall(void *, unsigned __int8 *, struct in_addr *)`
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
- `0x18003346c`
- `0x180052fa0`
- `0x1800558c0`
- `0x180075c04`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x180053200`
- `MobileNetworking!ReleaseWriteLock` at `0x180053200`

## pseudocode

```c
__int64 __fastcall MSMSecGetPeerIpAddress(void ***a1, unsigned __int8 *a2, struct in_addr *a3)
{
  unsigned int v6; // eax
  unsigned int v7; // ebx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  struct MSMSEC_INTF_CONTEXT *v10; // rdi
  const wchar_t *v11; // rax
  unsigned int v12; // r10d
  __int64 v13; // rdx
  int v14; // eax
  __int64 v15; // r11
  __int64 v16; // r8
  char v17; // r10
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // r9
  struct _RTL_CRITICAL_SECTION *v21; // rcx
  unsigned int AllocatedAddress; // eax
  struct MSMSEC_INTF_CONTEXT *v24; // [rsp+88h] [rbp+20h] BYREF

  v24 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 320, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids);
  v6 = IncThreadCountAndCheckInitializedEx("MSMSecGetPeerIpAddress", 2858);
  v7 = v6;
  if ( v6 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      v9 = 321;
LABEL_8:
      WPP_SF_d(v8[7], v9, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v6);
      goto LABEL_41;
    }
    goto LABEL_41;
  }
  if ( !a1 || !a2 || !a3 )
  {
    v7 = 87;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 322, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids);
    goto LABEL_41;
  }
  v6 = SecMgrValidateRefAndLockAdapter(a1, &v24);
  v7 = v6;
  if ( !v6 )
  {
    v10 = v24;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0 )
      WPP_SF_Lq(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        324,
        &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids,
        *((unsigned int *)v24 + 624),
        a1);
    if ( !(unsigned int)IsValidIntfSecStateForAction(*((unsigned int *)v10 + 681), 20) )
    {
      v7 = 5023;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        v11 = IntfActionStr(20);
        v14 = IntfSecStateStr(v12, v13, v11);
        WPP_SF_SLSL(
          *(_QWORD *)(v15 + 56),
          325,
          (unsigned int)&WPP_5807585f210c3b3262a513c5e260de7e_Traceguids,
          v14,
          v17,
          v16,
          20);
      }
      goto LABEL_37;
    }
    if ( (unsigned int)IntfIsInAPMode(v10) )
    {
      v21 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)v10 + 417);
      if ( v21 )
      {
        AllocatedAddress = IpAllocationMgrGetAllocatedAddress(v21, a2, a3);
        v7 = AllocatedAddress;
        if ( !AllocatedAddress )
          goto LABEL_37;
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
          goto LABEL_37;
        v19 = 328;
        v20 = AllocatedAddress;
        goto LABEL_36;
      }
      v7 = 5023;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_37;
      v19 = 327;
    }
    else
    {
      v7 = 5023;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_37;
      v19 = 326;
    }
    v20 = *((unsigned int *)v10 + 624);
LABEL_36:
    WPP_SF_d(v18[7], v19, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v20);
LABEL_37:
    TraceAdapterId(*((_DWORD *)v10 + 624), "<<< Unlocking <<<");
    ReleaseWriteLock(v10, (char *)v10 + 2512, "MSMSecGetPeerIpAddress", 2907);
    TraceAdapterId(*((_DWORD *)v10 + 624), "<<< Derefing <<<");
    SecMgrDerefAdapterEx(v10, "MSMSecGetPeerIpAddress", 2911);
    goto LABEL_41;
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    v9 = 323;
    goto LABEL_8;
  }
LABEL_41:
  DecThreadCountEx("MSMSecGetPeerIpAddress", 2913);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 329, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x180052fa0  mov     rax, rsp
0x180052fa3  mov     [rax+8], rbx
0x180052fa7  mov     [rax+10h], rbp
0x180052fab  push    rsi
0x180052fac  push    rdi
0x180052fad  push    r12
0x180052faf  push    r14
0x180052fb1  push    r15
0x180052fb3  sub     rsp, 40h
0x180052fb7  mov     rbp, r8
0x180052fba  mov     qword ptr [rax+20h], 0
0x180052fc2  mov     r14, rdx
0x180052fc5  mov     rsi, rcx
0x180052fc8  mov     rcx, cs:WPP_GLOBAL_Control
0x180052fcf  lea     r15, WPP_GLOBAL_Control
0x180052fd6  lea     r12, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x180052fdd  cmp     rcx, r15
0x180052fe0  jz      short loc_180052FFC
0x180052fe2  test    dword ptr [rcx+44h], 100h
0x180052fe9  jz      short loc_180052FFC
0x180052feb  mov     rcx, [rcx+38h]
0x180052fef  mov     edx, 140h
0x180052ff4  mov     r8, r12
0x180052ff7  call    WPP_SF_
0x180052ffc  mov     edx, 0B2Ah; int
0x180053001  lea     rcx, aMsmsecgetpeeri_0; "MSMSecGetPeerIpAddress"
0x180053008  call    ?IncThreadCountAndCheckInitializedEx@@YAKPEBDH@Z; IncThreadCountAndCheckInitializedEx(char const *,int)
0x18005300d  mov     ebx, eax
0x18005300f  test    eax, eax
0x180053011  jz      short loc_180053046
0x180053013  mov     rcx, cs:WPP_GLOBAL_Control
0x18005301a  cmp     rcx, r15
0x18005301d  jz      loc_18005325D
0x180053023  test    byte ptr [rcx+44h], 1
0x180053027  jz      loc_18005325D
0x18005302d  mov     edx, 141h
0x180053032  mov     rcx, [rcx+38h]
0x180053036  mov     r9d, eax
0x180053039  mov     r8, r12
0x18005303c  call    WPP_SF_d
0x180053041  jmp     loc_18005325D
0x180053046  test    rsi, rsi
0x180053049  jz      loc_180053235
0x18005304f  test    r14, r14
0x180053052  jz      loc_180053235
0x180053058  test    rbp, rbp
0x18005305b  jz      loc_180053235
0x180053061  lea     rdx, [rsp+68h+arg_18]; struct MSMSEC_INTF_CONTEXT **
0x180053069  mov     rcx, rsi; void *
0x18005306c  call    ?SecMgrValidateRefAndLockAdapter@@YAKPEAXPEAPEAUMSMSEC_INTF_CONTEXT@@@Z; SecMgrValidateRefAndLockAdapter(void *,MSMSEC_INTF_CONTEXT * *)
0x180053071  mov     ebx, eax
0x180053073  test    eax, eax
0x180053075  jz      short loc_180053098
0x180053077  mov     rcx, cs:WPP_GLOBAL_Control
0x18005307e  cmp     rcx, r15
0x180053081  jz      loc_18005325D
0x180053087  test    byte ptr [rcx+44h], 1
0x18005308b  jz      loc_18005325D
0x180053091  mov     edx, 143h
0x180053096  jmp     short loc_180053032
0x180053098  mov     rcx, cs:WPP_GLOBAL_Control
0x18005309f  mov     rdi, [rsp+68h+arg_18]
0x1800530a7  cmp     rcx, r15
0x1800530aa  jz      short loc_1800530CF
0x1800530ac  test    byte ptr [rcx+44h], 20h
0x1800530b0  jz      short loc_1800530CF
0x1800530b2  mov     r9d, [rdi+9C0h]
0x1800530b9  mov     edx, 144h
0x1800530be  mov     rcx, [rcx+38h]
0x1800530c2  mov     r8, r12
0x1800530c5  mov     [rsp+68h+var_48], rsi
0x1800530ca  call    WPP_SF_Lq
0x1800530cf  mov     ecx, [rdi+0AA4h]
0x1800530d5  mov     esi, 14h
0x1800530da  mov     edx, esi
0x1800530dc  call    ?IsValidIntfSecStateForAction@@YAHW4MSMSEC_INTF_SEC_STATE@@W4SECMGR_INTF_ACTION@@@Z; IsValidIntfSecStateForAction(MSMSEC_INTF_SEC_STATE,SECMGR_INTF_ACTION)
0x1800530e1  test    eax, eax
0x1800530e3  jnz     short loc_180053145
0x1800530e5  mov     ebx, 139Fh
0x1800530ea  mov     r11, cs:WPP_GLOBAL_Control
0x1800530f1  cmp     r11, r15
0x1800530f4  jz      loc_1800531D7
0x1800530fa  test    byte ptr [r11+44h], 1
0x1800530ff  jz      loc_1800531D7
0x180053105  mov     r10d, [rdi+0AA4h]
0x18005310c  mov     ecx, esi
0x18005310e  call    ?IntfActionStr@@YAPEBGW4SECMGR_INTF_ACTION@@@Z; IntfActionStr(SECMGR_INTF_ACTION)
0x180053113  mov     ecx, r10d
0x180053116  mov     r8, rax
0x180053119  call    ?IntfSecStateStr@@YAPEBGW4MSMSEC_INTF_SEC_STATE@@@Z; IntfSecStateStr(MSMSEC_INTF_SEC_STATE)
0x18005311e  mov     rcx, [r11+38h]
0x180053122  mov     r9, rax
0x180053125  mov     [rsp+68h+var_38], esi
0x180053129  mov     edx, 145h
0x18005312e  mov     [rsp+68h+var_40], r8
0x180053133  mov     r8, r12
0x180053136  mov     dword ptr [rsp+68h+var_48], r10d
0x18005313b  call    WPP_SF_SLSL
0x180053140  jmp     loc_1800531D7
0x180053145  mov     rcx, rdi; struct MSMSEC_INTF_CONTEXT *
0x180053148  call    ?IntfIsInAPMode@@YAHPEAUMSMSEC_INTF_CONTEXT@@@Z; IntfIsInAPMode(MSMSEC_INTF_CONTEXT *)
0x18005314d  test    eax, eax
0x18005314f  jnz     short loc_180053176
0x180053151  mov     ebx, 139Fh
0x180053156  mov     rcx, cs:WPP_GLOBAL_Control
0x18005315d  cmp     rcx, r15
0x180053160  jz      short loc_1800531D7
0x180053162  test    byte ptr [rcx+44h], 1
0x180053166  jz      short loc_1800531D7
0x180053168  mov     edx, 146h
0x18005316d  mov     r9d, [rdi+9C0h]
0x180053174  jmp     short loc_1800531CB
0x180053176  mov     rcx, [rdi+0D08h]; lpCriticalSection
0x18005317d  test    rcx, rcx
0x180053180  jnz     short loc_1800531A0
0x180053182  mov     ebx, 139Fh
0x180053187  mov     rcx, cs:WPP_GLOBAL_Control
0x18005318e  cmp     rcx, r15
0x180053191  jz      short loc_1800531D7
0x180053193  test    byte ptr [rcx+44h], 1
0x180053197  jz      short loc_1800531D7
0x180053199  mov     edx, 147h
0x18005319e  jmp     short loc_18005316D
0x1800531a0  mov     r8, rbp; struct in_addr *
0x1800531a3  mov     rdx, r14; unsigned __int8 *
0x1800531a6  call    ?IpAllocationMgrGetAllocatedAddress@@YAKPEAU_IP_ALLOCATION_MGR@@QEAEPEAUin_addr@@@Z; IpAllocationMgrGetAllocatedAddress(_IP_ALLOCATION_MGR *,uchar * const,in_addr *)
0x1800531ab  mov     ebx, eax
0x1800531ad  test    eax, eax
0x1800531af  jz      short loc_1800531D7
0x1800531b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800531b8  cmp     rcx, r15
0x1800531bb  jz      short loc_1800531D7
0x1800531bd  test    byte ptr [rcx+44h], 1
0x1800531c1  jz      short loc_1800531D7
0x1800531c3  mov     edx, 148h
0x1800531c8  mov     r9d, eax
0x1800531cb  mov     rcx, [rcx+38h]
0x1800531cf  mov     r8, r12
0x1800531d2  call    WPP_SF_d
0x1800531d7  mov     ecx, [rdi+9C0h]; unsigned int
0x1800531dd  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x1800531e4  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x1800531e9  lea     rdx, [rdi+9D0h]
0x1800531f0  mov     r9d, 0B5Bh
0x1800531f6  lea     r8, aMsmsecgetpeeri_0; "MSMSecGetPeerIpAddress"
0x1800531fd  mov     rcx, rdi
0x180053200  call    cs:__imp_ReleaseWriteLock
0x180053207  nop     dword ptr [rax+rax+00h]
0x18005320c  mov     ecx, [rdi+9C0h]; unsigned int
0x180053212  lea     rdx, aDerefing; "<<< Derefing <<<"
0x180053219  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x18005321e  mov     r8d, 0B5Fh; int
0x180053224  lea     rdx, aMsmsecgetpeeri_0; "MSMSecGetPeerIpAddress"
0x18005322b  mov     rcx, rdi; struct MSMSEC_INTF_CONTEXT *
0x18005322e  call    ?SecMgrDerefAdapterEx@@YAXPEAUMSMSEC_INTF_CONTEXT@@PEBDH@Z; SecMgrDerefAdapterEx(MSMSEC_INTF_CONTEXT *,char const *,int)
0x180053233  jmp     short loc_18005325D
0x180053235  mov     ebx, 57h ; 'W'
0x18005323a  mov     rcx, cs:WPP_GLOBAL_Control
0x180053241  cmp     rcx, r15
0x180053244  jz      short loc_18005325D
0x180053246  test    byte ptr [rcx+44h], 1
0x18005324a  jz      short loc_18005325D
0x18005324c  mov     rcx, [rcx+38h]
0x180053250  mov     edx, 142h
0x180053255  mov     r8, r12
0x180053258  call    WPP_SF_
0x18005325d  mov     edx, 0B61h; int
0x180053262  lea     rcx, aMsmsecgetpeeri_0; "MSMSecGetPeerIpAddress"
0x180053269  call    ?DecThreadCountEx@@YAXPEBDH@Z; DecThreadCountEx(char const *,int)
0x18005326e  mov     rcx, cs:WPP_GLOBAL_Control
0x180053275  cmp     rcx, r15
0x180053278  jz      short loc_180053297
0x18005327a  test    dword ptr [rcx+44h], 100h
0x180053281  jz      short loc_180053297
0x180053283  mov     rcx, [rcx+38h]
0x180053287  mov     edx, 149h
0x18005328c  mov     r9d, ebx
0x18005328f  mov     r8, r12
0x180053292  call    WPP_SF_d
0x180053297  mov     rbp, [rsp+68h+arg_8]
0x18005329c  mov     eax, ebx
0x18005329e  mov     rbx, [rsp+68h+arg_0]
0x1800532a3  add     rsp, 40h
0x1800532a7  pop     r15
0x1800532a9  pop     r14
0x1800532ab  pop     r12
0x1800532ad  pop     rdi
0x1800532ae  pop     rsi
0x1800532af  retn
```
