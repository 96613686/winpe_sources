# MSMSecDisableIpAddressAllocation

- ea: `0x180035ed0`
- end: `0x1800361c5`
- name: `MSMSecDisableIpAddressAllocation`
- size: `757`
- prototype: `__int64 __fastcall(void *)`
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
- `0x180035ed0`
- `0x1800361cc`
- `0x1800558c0`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x180036142`
- `MobileNetworking!ReleaseWriteLock` at `0x180036142`

## pseudocode

```c
__int64 __fastcall MSMSecDisableIpAddressAllocation(void ***a1)
{
  unsigned int v2; // eax
  unsigned int v3; // ebx
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  struct MSMSEC_INTF_CONTEXT *v6; // rdi
  const wchar_t *v7; // rax
  unsigned int v8; // r10d
  __int64 v9; // rdx
  int v10; // eax
  __int64 v11; // r11
  __int64 v12; // r8
  char v13; // r10
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r9
  struct _RTL_CRITICAL_SECTION *v17; // rcx
  unsigned int v18; // eax
  struct MSMSEC_INTF_CONTEXT *v20; // [rsp+68h] [rbp+10h] BYREF

  v20 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 310, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids);
  v2 = IncThreadCountAndCheckInitializedEx("MSMSecDisableIpAddressAllocation", 2784);
  v3 = v2;
  if ( v2 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      v5 = 311;
LABEL_8:
      WPP_SF_d(v4[7], v5, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v2);
      goto LABEL_39;
    }
    goto LABEL_39;
  }
  if ( !a1 )
  {
    v3 = 87;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 312, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids);
    goto LABEL_39;
  }
  v2 = SecMgrValidateRefAndLockAdapter(a1, &v20);
  v3 = v2;
  if ( !v2 )
  {
    v6 = v20;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0 )
      WPP_SF_Lq(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        314,
        &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids,
        *((unsigned int *)v20 + 624),
        a1);
    if ( !(unsigned int)IsValidIntfSecStateForAction(*((unsigned int *)v6 + 681), 19) )
    {
      v3 = 5023;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        v7 = IntfActionStr(19);
        v10 = IntfSecStateStr(v8, v9, v7);
        WPP_SF_SLSL(
          *(_QWORD *)(v11 + 56),
          315,
          (unsigned int)&WPP_5807585f210c3b3262a513c5e260de7e_Traceguids,
          v10,
          v13,
          v12,
          19);
      }
      goto LABEL_38;
    }
    if ( (unsigned int)IntfIsInAPMode(v6) )
    {
      v17 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)v6 + 417);
      if ( v17 )
      {
        v18 = IpAllocationMgrDestroy(v17);
        *((_QWORD *)v6 + 417) = 0;
        v3 = v18;
        if ( !v18 )
          goto LABEL_38;
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
          goto LABEL_38;
        v15 = 318;
        v16 = v18;
        goto LABEL_37;
      }
      v3 = 5023;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_38;
      v15 = 317;
    }
    else
    {
      v3 = 5023;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_38;
      v15 = 316;
    }
    v16 = *((unsigned int *)v6 + 624);
LABEL_37:
    WPP_SF_d(v14[7], v15, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v16);
LABEL_38:
    TraceAdapterId(*((_DWORD *)v6 + 624), "<<< Unlocking <<<");
    ReleaseWriteLock(v6, (char *)v6 + 2512, "MSMSecDisableIpAddressAllocation", 2834);
    TraceAdapterId(*((_DWORD *)v6 + 624), "<<< Derefing <<<");
    SecMgrDerefAdapterEx(v6, "MSMSecDisableIpAddressAllocation", 2838);
    goto LABEL_39;
  }
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    v5 = 313;
    goto LABEL_8;
  }
LABEL_39:
  DecThreadCountEx("MSMSecDisableIpAddressAllocation", 2840);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 319, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x180035ed0  mov     [rsp+arg_0], rbx
0x180035ed5  mov     [rsp+arg_10], rbp
0x180035eda  push    rsi
0x180035edb  push    rdi
0x180035edc  push    r14
0x180035ede  sub     rsp, 40h
0x180035ee2  mov     rsi, rcx
0x180035ee5  mov     [rsp+58h+arg_8], 0
0x180035eee  mov     rcx, cs:WPP_GLOBAL_Control
0x180035ef5  lea     rbp, WPP_GLOBAL_Control
0x180035efc  lea     r14, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x180035f03  cmp     rcx, rbp
0x180035f06  jz      short loc_180035F22
0x180035f08  test    dword ptr [rcx+44h], 100h
0x180035f0f  jz      short loc_180035F22
0x180035f11  mov     rcx, [rcx+38h]
0x180035f15  mov     edx, 136h
0x180035f1a  mov     r8, r14
0x180035f1d  call    WPP_SF_
0x180035f22  mov     edx, 0AE0h; int
0x180035f27  lea     rcx, aMsmsecdisablei_0; "MSMSecDisableIpAddressAllocation"
0x180035f2e  call    ?IncThreadCountAndCheckInitializedEx@@YAKPEBDH@Z; IncThreadCountAndCheckInitializedEx(char const *,int)
0x180035f33  mov     ebx, eax
0x180035f35  test    eax, eax
0x180035f37  jz      short loc_180035F6C
0x180035f39  mov     rcx, cs:WPP_GLOBAL_Control
0x180035f40  cmp     rcx, rbp
0x180035f43  jz      loc_180036175
0x180035f49  test    byte ptr [rcx+44h], 1
0x180035f4d  jz      loc_180036175
0x180035f53  mov     edx, 137h
0x180035f58  mov     rcx, [rcx+38h]
0x180035f5c  mov     r9d, eax
0x180035f5f  mov     r8, r14
0x180035f62  call    WPP_SF_d
0x180035f67  jmp     loc_180036175
0x180035f6c  test    rsi, rsi
0x180035f6f  jnz     short loc_180035FA4
0x180035f71  lea     ebx, [rsi+57h]
0x180035f74  mov     rcx, cs:WPP_GLOBAL_Control
0x180035f7b  cmp     rcx, rbp
0x180035f7e  jz      loc_180036175
0x180035f84  test    byte ptr [rcx+44h], 1
0x180035f88  jz      loc_180036175
0x180035f8e  mov     rcx, [rcx+38h]
0x180035f92  mov     edx, 138h
0x180035f97  mov     r8, r14
0x180035f9a  call    WPP_SF_
0x180035f9f  jmp     loc_180036175
0x180035fa4  lea     rdx, [rsp+58h+arg_8]; struct MSMSEC_INTF_CONTEXT **
0x180035fa9  mov     rcx, rsi; void *
0x180035fac  call    ?SecMgrValidateRefAndLockAdapter@@YAKPEAXPEAPEAUMSMSEC_INTF_CONTEXT@@@Z; SecMgrValidateRefAndLockAdapter(void *,MSMSEC_INTF_CONTEXT * *)
0x180035fb1  mov     ebx, eax
0x180035fb3  test    eax, eax
0x180035fb5  jz      short loc_180035FD8
0x180035fb7  mov     rcx, cs:WPP_GLOBAL_Control
0x180035fbe  cmp     rcx, rbp
0x180035fc1  jz      loc_180036175
0x180035fc7  test    byte ptr [rcx+44h], 1
0x180035fcb  jz      loc_180036175
0x180035fd1  mov     edx, 139h
0x180035fd6  jmp     short loc_180035F58
0x180035fd8  mov     rcx, cs:WPP_GLOBAL_Control
0x180035fdf  mov     rdi, [rsp+58h+arg_8]
0x180035fe4  cmp     rcx, rbp
0x180035fe7  jz      short loc_18003600C
0x180035fe9  test    byte ptr [rcx+44h], 20h
0x180035fed  jz      short loc_18003600C
0x180035fef  mov     r9d, [rdi+9C0h]
0x180035ff6  mov     edx, 13Ah
0x180035ffb  mov     rcx, [rcx+38h]
0x180035fff  mov     r8, r14
0x180036002  mov     [rsp+58h+var_38], rsi
0x180036007  call    WPP_SF_Lq
0x18003600c  mov     ecx, [rdi+0AA4h]
0x180036012  mov     esi, 13h
0x180036017  mov     edx, esi
0x180036019  call    ?IsValidIntfSecStateForAction@@YAHW4MSMSEC_INTF_SEC_STATE@@W4SECMGR_INTF_ACTION@@@Z; IsValidIntfSecStateForAction(MSMSEC_INTF_SEC_STATE,SECMGR_INTF_ACTION)
0x18003601e  test    eax, eax
0x180036020  jnz     short loc_180036082
0x180036022  mov     ebx, 139Fh
0x180036027  mov     r11, cs:WPP_GLOBAL_Control
0x18003602e  cmp     r11, rbp
0x180036031  jz      loc_180036119
0x180036037  test    byte ptr [r11+44h], 1
0x18003603c  jz      loc_180036119
0x180036042  mov     r10d, [rdi+0AA4h]
0x180036049  mov     ecx, esi
0x18003604b  call    ?IntfActionStr@@YAPEBGW4SECMGR_INTF_ACTION@@@Z; IntfActionStr(SECMGR_INTF_ACTION)
0x180036050  mov     ecx, r10d
0x180036053  mov     r8, rax
0x180036056  call    ?IntfSecStateStr@@YAPEBGW4MSMSEC_INTF_SEC_STATE@@@Z; IntfSecStateStr(MSMSEC_INTF_SEC_STATE)
0x18003605b  mov     rcx, [r11+38h]
0x18003605f  mov     r9, rax
0x180036062  mov     [rsp+58h+var_28], esi
0x180036066  mov     edx, 13Bh
0x18003606b  mov     [rsp+58h+var_30], r8
0x180036070  mov     r8, r14
0x180036073  mov     dword ptr [rsp+58h+var_38], r10d
0x180036078  call    WPP_SF_SLSL
0x18003607d  jmp     loc_180036119
0x180036082  mov     rcx, rdi; struct MSMSEC_INTF_CONTEXT *
0x180036085  call    ?IntfIsInAPMode@@YAHPEAUMSMSEC_INTF_CONTEXT@@@Z; IntfIsInAPMode(MSMSEC_INTF_CONTEXT *)
0x18003608a  test    eax, eax
0x18003608c  jnz     short loc_1800360B3
0x18003608e  mov     ebx, 139Fh
0x180036093  mov     rcx, cs:WPP_GLOBAL_Control
0x18003609a  cmp     rcx, rbp
0x18003609d  jz      short loc_180036119
0x18003609f  test    byte ptr [rcx+44h], 1
0x1800360a3  jz      short loc_180036119
0x1800360a5  mov     edx, 13Ch
0x1800360aa  mov     r9d, [rdi+9C0h]
0x1800360b1  jmp     short loc_18003610D
0x1800360b3  mov     rcx, [rdi+0D08h]; lpCriticalSection
0x1800360ba  test    rcx, rcx
0x1800360bd  jnz     short loc_1800360DD
0x1800360bf  mov     ebx, 139Fh
0x1800360c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800360cb  cmp     rcx, rbp
0x1800360ce  jz      short loc_180036119
0x1800360d0  test    byte ptr [rcx+44h], 1
0x1800360d4  jz      short loc_180036119
0x1800360d6  mov     edx, 13Dh
0x1800360db  jmp     short loc_1800360AA
0x1800360dd  call    ?IpAllocationMgrDestroy@@YAKPEAU_IP_ALLOCATION_MGR@@@Z; IpAllocationMgrDestroy(_IP_ALLOCATION_MGR *)
0x1800360e2  mov     qword ptr [rdi+0D08h], 0
0x1800360ed  mov     ebx, eax
0x1800360ef  test    eax, eax
0x1800360f1  jz      short loc_180036119
0x1800360f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800360fa  cmp     rcx, rbp
0x1800360fd  jz      short loc_180036119
0x1800360ff  test    byte ptr [rcx+44h], 1
0x180036103  jz      short loc_180036119
0x180036105  mov     edx, 13Eh
0x18003610a  mov     r9d, eax
0x18003610d  mov     rcx, [rcx+38h]
0x180036111  mov     r8, r14
0x180036114  call    WPP_SF_d
0x180036119  mov     ecx, [rdi+9C0h]; unsigned int
0x18003611f  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x180036126  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x18003612b  lea     rdx, [rdi+9D0h]
0x180036132  mov     r9d, 0B12h
0x180036138  lea     r8, aMsmsecdisablei_0; "MSMSecDisableIpAddressAllocation"
0x18003613f  mov     rcx, rdi
0x180036142  call    cs:__imp_ReleaseWriteLock
0x180036149  nop     dword ptr [rax+rax+00h]
0x18003614e  mov     ecx, [rdi+9C0h]; unsigned int
0x180036154  lea     rdx, aDerefing; "<<< Derefing <<<"
0x18003615b  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180036160  mov     r8d, 0B16h; int
0x180036166  lea     rdx, aMsmsecdisablei_0; "MSMSecDisableIpAddressAllocation"
0x18003616d  mov     rcx, rdi; struct MSMSEC_INTF_CONTEXT *
0x180036170  call    ?SecMgrDerefAdapterEx@@YAXPEAUMSMSEC_INTF_CONTEXT@@PEBDH@Z; SecMgrDerefAdapterEx(MSMSEC_INTF_CONTEXT *,char const *,int)
0x180036175  mov     edx, 0B18h; int
0x18003617a  lea     rcx, aMsmsecdisablei_0; "MSMSecDisableIpAddressAllocation"
0x180036181  call    ?DecThreadCountEx@@YAXPEBDH@Z; DecThreadCountEx(char const *,int)
0x180036186  mov     rcx, cs:WPP_GLOBAL_Control
0x18003618d  cmp     rcx, rbp
0x180036190  jz      short loc_1800361AF
0x180036192  test    dword ptr [rcx+44h], 100h
0x180036199  jz      short loc_1800361AF
0x18003619b  mov     rcx, [rcx+38h]
0x18003619f  mov     edx, 13Fh
0x1800361a4  mov     r9d, ebx
0x1800361a7  mov     r8, r14
0x1800361aa  call    WPP_SF_d
0x1800361af  mov     rbp, [rsp+58h+arg_10]
0x1800361b4  mov     eax, ebx
0x1800361b6  mov     rbx, [rsp+58h+arg_0]
0x1800361bb  add     rsp, 40h
0x1800361bf  pop     r14
0x1800361c1  pop     rdi
0x1800361c2  pop     rsi
0x1800361c3  retn
```
