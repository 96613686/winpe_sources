# CUPnPAutomationProxy::Initialize(ushort const *,IUnknown *,ushort *,ushort *,int)

- ea: `0x180035ee0`
- end: `0x1800361c2`
- name: `?Initialize@CUPnPAutomationProxy@@UEAAJPEBGPEAUIUnknown@@PEAG2H@Z`
- size: `738`
- prototype: `__int64 __fastcall(CUPnPAutomationProxy *__hidden this, STRSAFE_PCNZWCH pszSrc, struct IUnknown *, OLECHAR *psz, STRSAFE_PCNZWCH, int)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18000db4c`
- `0x18000e83c`
- `0x18000e8a0`
- `0x18000ee34`
- `0x180013180`
- `0x180020918`
- `0x180026a60`
- `0x180035ee0`
- `0x180039a84`
- `0x180055010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180036126`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180036143`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180036126`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180036143`

## string_xrefs

- `0x180035f35`: `HrIsAllowedCOMCallLocality failed !`
- `0x1800360d1`: `CUPnPAutomationProxy::Initialize - NULL service object!`
- `0x18003607d`: `CUPnPAutomationProxy::Initialize - Unable to allocate service type!`

## pseudocode

```c
__int64 __fastcall CUPnPAutomationProxy::Initialize(
        CUPnPAutomationProxy *this,
        STRSAFE_PCNZWCH pszSrc,
        struct IUnknown *a3,
        OLECHAR *psz,
        STRSAFE_PCNZWCH pszSrca,
        int a6)
{
  int IsAllowedCOMCallLocality; // ebx
  STRSAFE_PCNZWCH v11; // rcx
  int v12; // edx
  const char *v13; // r9
  unsigned __int16 *v14; // rax
  unsigned __int16 *v15; // rax
  __int64 v16; // rcx
  void *v17; // rcx
  void *v18; // rcx

  IsAllowedCOMCallLocality = HrIsAllowedCOMCallLocality(1);
  if ( IsAllowedCOMCallLocality >= 0 )
  {
    if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 20, 1, 0) || !pszSrc || !psz || !pszSrca )
    {
      v11 = WPP_GLOBAL_Control;
      IsAllowedCOMCallLocality = -2147024809;
      if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        return (unsigned int)IsAllowedCOMCallLocality;
      v12 = 11;
LABEL_46:
      v13 = "CUPnPAutomationProxy::Initialize(): Exiting";
      goto LABEL_47;
    }
    if ( !a3 )
    {
      IsAllowedCOMCallLocality = -2147024809;
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          (unsigned int)WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
          (unsigned int)"CUPnPAutomationProxy::Initialize - NULL service object!",
          87);
      goto LABEL_33;
    }
    v14 = WszDupWsz(pszSrca);
    *((_QWORD *)this + 16) = v14;
    if ( v14 )
    {
      IsAllowedCOMCallLocality = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, char *))a3->lpVtbl->QueryInterface)(
                                   a3,
                                   &IID_IDispatch,
                                   (char *)this + 88);
      if ( IsAllowedCOMCallLocality < 0 )
        goto LABEL_26;
      if ( a6 )
      {
        IsAllowedCOMCallLocality = HrCopyProxyIdentity(*((struct IUnknown **)this + 11), a3);
        if ( IsAllowedCOMCallLocality < 0 )
          goto LABEL_26;
      }
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids);
      IsAllowedCOMCallLocality = CUPnPAutomationProxy::HrProcessServiceDescription(this, psz);
      if ( IsAllowedCOMCallLocality < 0 )
        goto LABEL_26;
      v15 = WszDupWsz(pszSrc);
      *((_QWORD *)this + 17) = v15;
      if ( v15 )
      {
        _InterlockedExchange((volatile __int32 *)this + 20, 2);
LABEL_26:
        v11 = WPP_GLOBAL_Control;
        goto LABEL_27;
      }
      IsAllowedCOMCallLocality = -2147024882;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids);
        goto LABEL_26;
      }
    }
    else
    {
      IsAllowedCOMCallLocality = -2147024882;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          (unsigned int)WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
          (unsigned int)"CUPnPAutomationProxy::Initialize - Unable to allocate service type!",
          14);
        goto LABEL_26;
      }
    }
LABEL_27:
    if ( IsAllowedCOMCallLocality >= 0 )
    {
      if ( !IsAllowedCOMCallLocality )
        return (unsigned int)IsAllowedCOMCallLocality;
      goto LABEL_40;
    }
LABEL_33:
    v16 = *((_QWORD *)this + 11);
    if ( v16 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      *((_QWORD *)this + 11) = 0;
    }
    CUPnPAutomationProxy::FreeVariableTable(this);
    CUPnPAutomationProxy::FreeActionTable(this);
    v17 = (void *)*((_QWORD *)this + 16);
    if ( v17 )
    {
      free(v17);
      *((_QWORD *)this + 16) = 0;
    }
    v18 = (void *)*((_QWORD *)this + 17);
    if ( v18 )
    {
      free(v18);
      *((_QWORD *)this + 17) = 0;
    }
    _InterlockedExchange((volatile __int32 *)this + 20, 0);
    v11 = WPP_GLOBAL_Control;
LABEL_40:
    if ( v11 == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control || (v11[14] & 1) == 0 )
      return (unsigned int)IsAllowedCOMCallLocality;
    v12 = 16;
    goto LABEL_46;
  }
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v12 = 10;
    v13 = "HrIsAllowedCOMCallLocality failed !";
LABEL_47:
    WPP_SF_sd(
      *((_QWORD *)v11 + 2),
      v12,
      (unsigned int)WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
      (_DWORD)v13,
      IsAllowedCOMCallLocality);
  }
  return (unsigned int)IsAllowedCOMCallLocality;
}

```

## disassembly

```asm
0x180035ee0  push    rbx
0x180035ee2  push    rsi
0x180035ee3  push    rdi
0x180035ee4  push    r12
0x180035ee6  push    r13
0x180035ee8  push    r14
0x180035eea  push    r15
0x180035eec  sub     rsp, 40h
0x180035ef0  mov     rdi, rcx
0x180035ef3  mov     r13d, 1
0x180035ef9  mov     ecx, r13d
0x180035efc  mov     r15, r9
0x180035eff  mov     r14, r8
0x180035f02  mov     r12, rdx
0x180035f05  call    ?HrIsAllowedCOMCallLocality@@YAJW4CALL_LOCALITY@@@Z; HrIsAllowedCOMCallLocality(CALL_LOCALITY)
0x180035f0a  mov     ebx, eax
0x180035f0c  test    eax, eax
0x180035f0e  jns     short loc_180035F41
0x180035f10  mov     rcx, cs:WPP_GLOBAL_Control
0x180035f17  lea     rsi, WPP_GLOBAL_Control
0x180035f1e  cmp     rcx, rsi
0x180035f21  jz      loc_1800361B0
0x180035f27  test    [rcx+1Ch], r13b
0x180035f2b  jz      loc_1800361B0
0x180035f31  lea     edx, [r13+9]
0x180035f35  lea     r9, aHrisallowedcom; "HrIsAllowedCOMCallLocality failed !"
0x180035f3c  jmp     loc_18003619C
0x180035f41  xor     eax, eax
0x180035f43  lock cmpxchg [rdi+50h], r13d
0x180035f49  jnz     loc_180036172
0x180035f4f  test    r12, r12
0x180035f52  jz      loc_180036172
0x180035f58  test    r15, r15
0x180035f5b  jz      loc_180036172
0x180035f61  mov     rcx, [rsp+78h+pszSrc]; pszSrc
0x180035f69  test    rcx, rcx
0x180035f6c  jz      loc_180036172
0x180035f72  test    r14, r14
0x180035f75  jz      loc_1800360AF
0x180035f7b  call    ?WszDupWsz@@YAPEAGPEBG@Z; WszDupWsz(ushort const *)
0x180035f80  mov     [rdi+80h], rax
0x180035f87  lea     rsi, WPP_GLOBAL_Control
0x180035f8e  test    rax, rax
0x180035f91  jz      loc_180036062
0x180035f97  mov     rax, [r14]
0x180035f9a  lea     r8, [rdi+58h]
0x180035f9e  lea     rdx, IID_IDispatch
0x180035fa5  mov     rcx, r14
0x180035fa8  mov     rax, [rax]
0x180035fab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035fb0  mov     ebx, eax
0x180035fb2  test    eax, eax
0x180035fb4  js      loc_180036099
0x180035fba  cmp     [rsp+78h+arg_28], 0
0x180035fc2  jz      short loc_180035FDA
0x180035fc4  mov     rcx, [rdi+58h]; struct IUnknown *
0x180035fc8  mov     rdx, r14; struct IUnknown *
0x180035fcb  call    ?HrCopyProxyIdentity@@YAJPEAUIUnknown@@0@Z; HrCopyProxyIdentity(IUnknown *,IUnknown *)
0x180035fd0  mov     ebx, eax
0x180035fd2  test    eax, eax
0x180035fd4  js      loc_180036099
0x180035fda  mov     rcx, cs:WPP_GLOBAL_Control
0x180035fe1  cmp     rcx, rsi
0x180035fe4  jz      short loc_180036001
0x180035fe6  test    byte ptr [rcx+1Ch], 40h
0x180035fea  jz      short loc_180036001
0x180035fec  mov     rcx, [rcx+10h]
0x180035ff0  lea     r8, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids
0x180035ff7  mov     edx, 0Ch
0x180035ffc  call    WPP_SF_
0x180036001  mov     rdx, r15; psz
0x180036004  mov     rcx, rdi; this
0x180036007  call    ?HrProcessServiceDescription@CUPnPAutomationProxy@@AEAAJPEAG@Z; CUPnPAutomationProxy::HrProcessServiceDescription(ushort *)
0x18003600c  mov     ebx, eax
0x18003600e  test    eax, eax
0x180036010  js      loc_180036099
0x180036016  mov     rcx, r12; pszSrc
0x180036019  call    ?WszDupWsz@@YAPEAGPEBG@Z; WszDupWsz(ushort const *)
0x18003601e  mov     [rdi+88h], rax
0x180036025  test    rax, rax
0x180036028  jz      short loc_180036034
0x18003602a  mov     eax, 2
0x18003602f  xchg    eax, [rdi+50h]
0x180036032  jmp     short loc_180036099
0x180036034  mov     ebx, 8007000Eh
0x180036039  mov     rcx, cs:WPP_GLOBAL_Control
0x180036040  cmp     rcx, rsi
0x180036043  jz      short loc_1800360A0
0x180036045  test    [rcx+1Ch], r13b
0x180036049  jz      short loc_1800360A0
0x18003604b  mov     rcx, [rcx+10h]
0x18003604f  lea     r8, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids
0x180036056  mov     edx, 0Dh
0x18003605b  call    WPP_SF_
0x180036060  jmp     short loc_180036099
0x180036062  mov     ebx, 8007000Eh
0x180036067  mov     rcx, cs:WPP_GLOBAL_Control
0x18003606e  cmp     rcx, rsi
0x180036071  jz      short loc_1800360A0
0x180036073  test    [rcx+1Ch], r13b
0x180036077  jz      short loc_1800360A0
0x180036079  mov     rcx, [rcx+10h]
0x18003607d  lea     r9, aCupnpautomatio_69; "CUPnPAutomationProxy::Initialize - Unab"...
0x180036084  mov     edx, 0Eh
0x180036089  mov     [rsp+78h+var_58], ebx
0x18003608d  lea     r8, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids
0x180036094  call    WPP_SF_sd
0x180036099  mov     rcx, cs:WPP_GLOBAL_Control
0x1800360a0  test    ebx, ebx
0x1800360a2  js      short loc_1800360ED
0x1800360a4  jz      loc_1800361B0
0x1800360aa  jmp     loc_180036160
0x1800360af  mov     ebx, 80070057h
0x1800360b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800360bb  lea     rsi, WPP_GLOBAL_Control
0x1800360c2  cmp     rcx, rsi
0x1800360c5  jz      short loc_1800360ED
0x1800360c7  test    [rcx+1Ch], r13b
0x1800360cb  jz      short loc_1800360ED
0x1800360cd  mov     rcx, [rcx+10h]
0x1800360d1  lea     r9, aCupnpautomatio_24; "CUPnPAutomationProxy::Initialize - NULL"...
0x1800360d8  mov     edx, 0Fh
0x1800360dd  mov     [rsp+78h+var_58], ebx
0x1800360e1  lea     r8, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids
0x1800360e8  call    WPP_SF_sd
0x1800360ed  mov     rcx, [rdi+58h]
0x1800360f1  test    rcx, rcx
0x1800360f4  jz      short loc_18003610A
0x1800360f6  mov     rax, [rcx]
0x1800360f9  mov     rax, [rax+10h]
0x1800360fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036102  mov     qword ptr [rdi+58h], 0
0x18003610a  mov     rcx, rdi; this
0x18003610d  call    ?FreeVariableTable@CUPnPAutomationProxy@@AEAAXXZ; CUPnPAutomationProxy::FreeVariableTable(void)
0x180036112  mov     rcx, rdi; this
0x180036115  call    ?FreeActionTable@CUPnPAutomationProxy@@AEAAXXZ; CUPnPAutomationProxy::FreeActionTable(void)
0x18003611a  mov     rcx, [rdi+80h]; Block
0x180036121  test    rcx, rcx
0x180036124  jz      short loc_180036137
0x180036126  call    cs:__imp_free
0x18003612c  mov     qword ptr [rdi+80h], 0
0x180036137  mov     rcx, [rdi+88h]; Block
0x18003613e  test    rcx, rcx
0x180036141  jz      short loc_180036154
0x180036143  call    cs:__imp_free
0x180036149  mov     qword ptr [rdi+88h], 0
0x180036154  xor     eax, eax
0x180036156  xchg    eax, [rdi+50h]
0x180036159  mov     rcx, cs:WPP_GLOBAL_Control
0x180036160  cmp     rcx, rsi
0x180036163  jz      short loc_1800361B0
0x180036165  test    [rcx+1Ch], r13b
0x180036169  jz      short loc_1800361B0
0x18003616b  mov     edx, 10h
0x180036170  jmp     short loc_180036195
0x180036172  mov     rcx, cs:WPP_GLOBAL_Control
0x180036179  lea     rsi, WPP_GLOBAL_Control
0x180036180  mov     ebx, 80070057h
0x180036185  cmp     rcx, rsi
0x180036188  jz      short loc_1800361B0
0x18003618a  test    [rcx+1Ch], r13b
0x18003618e  jz      short loc_1800361B0
0x180036190  mov     edx, 0Bh
0x180036195  lea     r9, aCupnpautomatio_23; "CUPnPAutomationProxy::Initialize(): Exi"...
0x18003619c  mov     rcx, [rcx+10h]
0x1800361a0  lea     r8, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids
0x1800361a7  mov     [rsp+78h+var_58], ebx
0x1800361ab  call    WPP_SF_sd
0x1800361b0  mov     eax, ebx
0x1800361b2  add     rsp, 40h
0x1800361b6  pop     r15
0x1800361b8  pop     r14
0x1800361ba  pop     r13
0x1800361bc  pop     r12
0x1800361be  pop     rdi
0x1800361bf  pop     rsi
0x1800361c0  pop     rbx
0x1800361c1  retn
```
