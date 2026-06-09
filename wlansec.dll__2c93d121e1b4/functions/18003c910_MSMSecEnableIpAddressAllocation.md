# MSMSecEnableIpAddressAllocation

- ea: `0x18003c910`
- end: `0x18003cc18`
- name: `MSMSecEnableIpAddressAllocation`
- size: `776`
- prototype: `__int64 __fastcall(void *, struct in_addr, unsigned __int8)`
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
- `0x18003c910`
- `0x1800558c0`
- `0x180075a68`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x18003cb67`
- `MobileNetworking!ReleaseWriteLock` at `0x18003cb67`

## pseudocode

```c
__int64 __fastcall MSMSecEnableIpAddressAllocation(void ***a1, struct in_addr a2, unsigned __int8 a3)
{
  unsigned int v6; // eax
  unsigned int v7; // edi
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  struct MSMSEC_INTF_CONTEXT *v10; // rsi
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
  unsigned int v21; // eax
  struct MSMSEC_INTF_CONTEXT *v23; // [rsp+88h] [rbp+20h] BYREF

  v23 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 300, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids);
  v6 = IncThreadCountAndCheckInitializedEx("MSMSecEnableIpAddressAllocation", 2711);
  v7 = v6;
  if ( v6 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      v9 = 301;
LABEL_8:
      WPP_SF_d(v8[7], v9, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v6);
      goto LABEL_40;
    }
    goto LABEL_40;
  }
  if ( !a1 || a3 > 0x1Eu )
  {
    v7 = 87;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 302, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids);
    goto LABEL_40;
  }
  v6 = SecMgrValidateRefAndLockAdapter(a1, &v23);
  v7 = v6;
  if ( !v6 )
  {
    v10 = v23;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0 )
      WPP_SF_Lq(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        304,
        &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids,
        *((unsigned int *)v23 + 624),
        a1);
    if ( !(unsigned int)IsValidIntfSecStateForAction(*((unsigned int *)v10 + 681), 19) )
    {
      v7 = 5023;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        v11 = IntfActionStr(19);
        v14 = IntfSecStateStr(v12, v13, v11);
        WPP_SF_SLSL(
          *(_QWORD *)(v15 + 56),
          305,
          (unsigned int)&WPP_5807585f210c3b3262a513c5e260de7e_Traceguids,
          v14,
          v17,
          v16,
          19);
      }
      goto LABEL_36;
    }
    if ( (unsigned int)IntfIsInAPMode(v10) )
    {
      if ( !*((_QWORD *)v10 + 417) )
      {
        v21 = IpAllocationMgrCreate(a2, a3, (LPCRITICAL_SECTION *)v10 + 417);
        v7 = v21;
        if ( !v21 )
          goto LABEL_36;
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
          goto LABEL_36;
        v19 = 308;
        v20 = v21;
        goto LABEL_35;
      }
      v7 = 5023;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_36;
      v19 = 307;
    }
    else
    {
      v7 = 5023;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_36;
      v19 = 306;
    }
    v20 = *((unsigned int *)v10 + 624);
LABEL_35:
    WPP_SF_d(v18[7], v19, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v20);
LABEL_36:
    TraceAdapterId(*((_DWORD *)v10 + 624), "<<< Unlocking <<<");
    ReleaseWriteLock(v10, (char *)v10 + 2512, "MSMSecEnableIpAddressAllocation", 2760);
    TraceAdapterId(*((_DWORD *)v10 + 624), "<<< Derefing <<<");
    SecMgrDerefAdapterEx(v10, "MSMSecEnableIpAddressAllocation", 2764);
    goto LABEL_40;
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    v9 = 303;
    goto LABEL_8;
  }
LABEL_40:
  DecThreadCountEx("MSMSecEnableIpAddressAllocation", 2766);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 309, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x18003c910  mov     rax, rsp
0x18003c913  mov     [rax+8], rbx
0x18003c917  mov     [rax+10h], rbp
0x18003c91b  push    rsi
0x18003c91c  push    rdi
0x18003c91d  push    r12
0x18003c91f  push    r14
0x18003c921  push    r15
0x18003c923  sub     rsp, 40h
0x18003c927  mov     r14b, r8b
0x18003c92a  mov     qword ptr [rax+20h], 0
0x18003c932  mov     ebx, edx
0x18003c934  mov     rbp, rcx
0x18003c937  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c93e  lea     r15, WPP_GLOBAL_Control
0x18003c945  lea     r12, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x18003c94c  cmp     rcx, r15
0x18003c94f  jz      short loc_18003C96B
0x18003c951  test    dword ptr [rcx+44h], 100h
0x18003c958  jz      short loc_18003C96B
0x18003c95a  mov     rcx, [rcx+38h]
0x18003c95e  mov     edx, 12Ch
0x18003c963  mov     r8, r12
0x18003c966  call    WPP_SF_
0x18003c96b  mov     edx, 0A97h; int
0x18003c970  lea     rcx, aMsmsecenableip_0; "MSMSecEnableIpAddressAllocation"
0x18003c977  call    ?IncThreadCountAndCheckInitializedEx@@YAKPEBDH@Z; IncThreadCountAndCheckInitializedEx(char const *,int)
0x18003c97c  mov     edi, eax
0x18003c97e  test    eax, eax
0x18003c980  jz      short loc_18003C9B5
0x18003c982  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c989  cmp     rcx, r15
0x18003c98c  jz      loc_18003CBC4
0x18003c992  test    byte ptr [rcx+44h], 1
0x18003c996  jz      loc_18003CBC4
0x18003c99c  mov     edx, 12Dh
0x18003c9a1  mov     rcx, [rcx+38h]
0x18003c9a5  mov     r9d, eax
0x18003c9a8  mov     r8, r12
0x18003c9ab  call    WPP_SF_d
0x18003c9b0  jmp     loc_18003CBC4
0x18003c9b5  test    rbp, rbp
0x18003c9b8  jz      loc_18003CB9C
0x18003c9be  cmp     r14b, 1Eh
0x18003c9c2  ja      loc_18003CB9C
0x18003c9c8  lea     rdx, [rsp+68h+arg_18]; struct MSMSEC_INTF_CONTEXT **
0x18003c9d0  mov     rcx, rbp; void *
0x18003c9d3  call    ?SecMgrValidateRefAndLockAdapter@@YAKPEAXPEAPEAUMSMSEC_INTF_CONTEXT@@@Z; SecMgrValidateRefAndLockAdapter(void *,MSMSEC_INTF_CONTEXT * *)
0x18003c9d8  mov     edi, eax
0x18003c9da  test    eax, eax
0x18003c9dc  jz      short loc_18003C9FF
0x18003c9de  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c9e5  cmp     rcx, r15
0x18003c9e8  jz      loc_18003CBC4
0x18003c9ee  test    byte ptr [rcx+44h], 1
0x18003c9f2  jz      loc_18003CBC4
0x18003c9f8  mov     edx, 12Fh
0x18003c9fd  jmp     short loc_18003C9A1
0x18003c9ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ca06  mov     rsi, [rsp+68h+arg_18]
0x18003ca0e  cmp     rcx, r15
0x18003ca11  jz      short loc_18003CA36
0x18003ca13  test    byte ptr [rcx+44h], 20h
0x18003ca17  jz      short loc_18003CA36
0x18003ca19  mov     r9d, [rsi+9C0h]
0x18003ca20  mov     edx, 130h
0x18003ca25  mov     rcx, [rcx+38h]
0x18003ca29  mov     r8, r12
0x18003ca2c  mov     [rsp+68h+var_48], rbp
0x18003ca31  call    WPP_SF_Lq
0x18003ca36  mov     ecx, [rsi+0AA4h]
0x18003ca3c  mov     ebp, 13h
0x18003ca41  mov     edx, ebp
0x18003ca43  call    ?IsValidIntfSecStateForAction@@YAHW4MSMSEC_INTF_SEC_STATE@@W4SECMGR_INTF_ACTION@@@Z; IsValidIntfSecStateForAction(MSMSEC_INTF_SEC_STATE,SECMGR_INTF_ACTION)
0x18003ca48  test    eax, eax
0x18003ca4a  jnz     short loc_18003CAAC
0x18003ca4c  mov     edi, 139Fh
0x18003ca51  mov     r11, cs:WPP_GLOBAL_Control
0x18003ca58  cmp     r11, r15
0x18003ca5b  jz      loc_18003CB3E
0x18003ca61  test    byte ptr [r11+44h], 1
0x18003ca66  jz      loc_18003CB3E
0x18003ca6c  mov     r10d, [rsi+0AA4h]
0x18003ca73  mov     ecx, ebp
0x18003ca75  call    ?IntfActionStr@@YAPEBGW4SECMGR_INTF_ACTION@@@Z; IntfActionStr(SECMGR_INTF_ACTION)
0x18003ca7a  mov     ecx, r10d
0x18003ca7d  mov     r8, rax
0x18003ca80  call    ?IntfSecStateStr@@YAPEBGW4MSMSEC_INTF_SEC_STATE@@@Z; IntfSecStateStr(MSMSEC_INTF_SEC_STATE)
0x18003ca85  mov     rcx, [r11+38h]
0x18003ca89  mov     r9, rax
0x18003ca8c  mov     [rsp+68h+var_38], ebp
0x18003ca90  mov     edx, 131h
0x18003ca95  mov     [rsp+68h+var_40], r8
0x18003ca9a  mov     r8, r12
0x18003ca9d  mov     dword ptr [rsp+68h+var_48], r10d
0x18003caa2  call    WPP_SF_SLSL
0x18003caa7  jmp     loc_18003CB3E
0x18003caac  mov     rcx, rsi; struct MSMSEC_INTF_CONTEXT *
0x18003caaf  call    ?IntfIsInAPMode@@YAHPEAUMSMSEC_INTF_CONTEXT@@@Z; IntfIsInAPMode(MSMSEC_INTF_CONTEXT *)
0x18003cab4  test    eax, eax
0x18003cab6  jnz     short loc_18003CADD
0x18003cab8  mov     edi, 139Fh
0x18003cabd  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cac4  cmp     rcx, r15
0x18003cac7  jz      short loc_18003CB3E
0x18003cac9  test    byte ptr [rcx+44h], 1
0x18003cacd  jz      short loc_18003CB3E
0x18003cacf  mov     edx, 132h
0x18003cad4  mov     r9d, [rsi+9C0h]
0x18003cadb  jmp     short loc_18003CB32
0x18003cadd  lea     r8, [rsi+0D08h]; struct _IP_ALLOCATION_MGR **
0x18003cae4  cmp     qword ptr [r8], 0
0x18003cae8  jz      short loc_18003CB08
0x18003caea  mov     edi, 139Fh
0x18003caef  mov     rcx, cs:WPP_GLOBAL_Control
0x18003caf6  cmp     rcx, r15
0x18003caf9  jz      short loc_18003CB3E
0x18003cafb  test    byte ptr [rcx+44h], 1
0x18003caff  jz      short loc_18003CB3E
0x18003cb01  mov     edx, 133h
0x18003cb06  jmp     short loc_18003CAD4
0x18003cb08  mov     dl, r14b; unsigned __int8
0x18003cb0b  mov     ecx, ebx; struct in_addr
0x18003cb0d  call    ?IpAllocationMgrCreate@@YAKUin_addr@@EPEAPEAU_IP_ALLOCATION_MGR@@@Z; IpAllocationMgrCreate(in_addr,uchar,_IP_ALLOCATION_MGR * *)
0x18003cb12  mov     edi, eax
0x18003cb14  test    eax, eax
0x18003cb16  jz      short loc_18003CB3E
0x18003cb18  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cb1f  cmp     rcx, r15
0x18003cb22  jz      short loc_18003CB3E
0x18003cb24  test    byte ptr [rcx+44h], 1
0x18003cb28  jz      short loc_18003CB3E
0x18003cb2a  mov     edx, 134h
0x18003cb2f  mov     r9d, eax
0x18003cb32  mov     rcx, [rcx+38h]
0x18003cb36  mov     r8, r12
0x18003cb39  call    WPP_SF_d
0x18003cb3e  mov     ecx, [rsi+9C0h]; unsigned int
0x18003cb44  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x18003cb4b  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x18003cb50  lea     rdx, [rsi+9D0h]
0x18003cb57  mov     r9d, 0AC8h
0x18003cb5d  lea     r8, aMsmsecenableip_0; "MSMSecEnableIpAddressAllocation"
0x18003cb64  mov     rcx, rsi
0x18003cb67  call    cs:__imp_ReleaseWriteLock
0x18003cb6e  nop     dword ptr [rax+rax+00h]
0x18003cb73  mov     ecx, [rsi+9C0h]; unsigned int
0x18003cb79  lea     rdx, aDerefing; "<<< Derefing <<<"
0x18003cb80  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x18003cb85  mov     r8d, 0ACCh; int
0x18003cb8b  lea     rdx, aMsmsecenableip_0; "MSMSecEnableIpAddressAllocation"
0x18003cb92  mov     rcx, rsi; struct MSMSEC_INTF_CONTEXT *
0x18003cb95  call    ?SecMgrDerefAdapterEx@@YAXPEAUMSMSEC_INTF_CONTEXT@@PEBDH@Z; SecMgrDerefAdapterEx(MSMSEC_INTF_CONTEXT *,char const *,int)
0x18003cb9a  jmp     short loc_18003CBC4
0x18003cb9c  mov     edi, 57h ; 'W'
0x18003cba1  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cba8  cmp     rcx, r15
0x18003cbab  jz      short loc_18003CBC4
0x18003cbad  test    byte ptr [rcx+44h], 1
0x18003cbb1  jz      short loc_18003CBC4
0x18003cbb3  mov     rcx, [rcx+38h]
0x18003cbb7  mov     edx, 12Eh
0x18003cbbc  mov     r8, r12
0x18003cbbf  call    WPP_SF_
0x18003cbc4  mov     edx, 0ACEh; int
0x18003cbc9  lea     rcx, aMsmsecenableip_0; "MSMSecEnableIpAddressAllocation"
0x18003cbd0  call    ?DecThreadCountEx@@YAXPEBDH@Z; DecThreadCountEx(char const *,int)
0x18003cbd5  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cbdc  cmp     rcx, r15
0x18003cbdf  jz      short loc_18003CBFE
0x18003cbe1  test    dword ptr [rcx+44h], 100h
0x18003cbe8  jz      short loc_18003CBFE
0x18003cbea  mov     rcx, [rcx+38h]
0x18003cbee  mov     edx, 135h
0x18003cbf3  mov     r9d, edi
0x18003cbf6  mov     r8, r12
0x18003cbf9  call    WPP_SF_d
0x18003cbfe  mov     rbx, [rsp+68h+arg_0]
0x18003cc03  mov     eax, edi
0x18003cc05  mov     rbp, [rsp+68h+arg_8]
0x18003cc0a  add     rsp, 40h
0x18003cc0e  pop     r15
0x18003cc10  pop     r14
0x18003cc12  pop     r12
0x18003cc14  pop     rdi
0x18003cc15  pop     rsi
0x18003cc16  retn
```
