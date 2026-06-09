# CUPnPAutomationProxy::Initialize(ushort const *,IUnknown *,ushort *,ushort *,int)

- ea: `0x180038280`
- end: `0x18003856f`
- name: `?Initialize@CUPnPAutomationProxy@@UEAAJPEBGPEAUIUnknown@@PEAG2H@Z`
- size: `751`
- prototype: `__int64 __fastcall(CUPnPAutomationProxy *__hidden this, STRSAFE_PCNZWCH pszSrc, struct IUnknown *, OLECHAR *psz, STRSAFE_PCNZWCH, int)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1800071c0`
- `0x180015a9c`
- `0x1800200f4`
- `0x180020e30`
- `0x180020e94`
- `0x180021444`
- `0x180027b60`
- `0x180038280`
- `0x18003c018`
- `0x180059010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800384c6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800384e9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800384c6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800384e9`

## string_xrefs

- `0x1800382d5`: `HrIsAllowedCOMCallLocality failed !`
- `0x180038471`: `CUPnPAutomationProxy::Initialize - NULL service object!`
- `0x18003841d`: `CUPnPAutomationProxy::Initialize - Unable to allocate service type!`

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
0x180038280  push    rbx
0x180038282  push    rsi
0x180038283  push    rdi
0x180038284  push    r12
0x180038286  push    r13
0x180038288  push    r14
0x18003828a  push    r15
0x18003828c  sub     rsp, 40h
0x180038290  mov     rdi, rcx
0x180038293  mov     r13d, 1
0x180038299  mov     ecx, r13d
0x18003829c  mov     r15, r9
0x18003829f  mov     r14, r8
0x1800382a2  mov     r12, rdx
0x1800382a5  call    ?HrIsAllowedCOMCallLocality@@YAJW4CALL_LOCALITY@@@Z; HrIsAllowedCOMCallLocality(CALL_LOCALITY)
0x1800382aa  mov     ebx, eax
0x1800382ac  test    eax, eax
0x1800382ae  jns     short loc_1800382E1
0x1800382b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800382b7  lea     rsi, WPP_GLOBAL_Control
0x1800382be  cmp     rcx, rsi
0x1800382c1  jz      loc_18003855C
0x1800382c7  test    [rcx+1Ch], r13b
0x1800382cb  jz      loc_18003855C
0x1800382d1  lea     edx, [r13+9]
0x1800382d5  lea     r9, aHrisallowedcom; "HrIsAllowedCOMCallLocality failed !"
0x1800382dc  jmp     loc_180038548
0x1800382e1  xor     eax, eax
0x1800382e3  lock cmpxchg [rdi+50h], r13d
0x1800382e9  jnz     loc_18003851E
0x1800382ef  test    r12, r12
0x1800382f2  jz      loc_18003851E
0x1800382f8  test    r15, r15
0x1800382fb  jz      loc_18003851E
0x180038301  mov     rcx, [rsp+78h+pszSrc]; pszSrc
0x180038309  test    rcx, rcx
0x18003830c  jz      loc_18003851E
0x180038312  test    r14, r14
0x180038315  jz      loc_18003844F
0x18003831b  call    ?WszDupWsz@@YAPEAGPEBG@Z; WszDupWsz(ushort const *)
0x180038320  mov     [rdi+80h], rax
0x180038327  lea     rsi, WPP_GLOBAL_Control
0x18003832e  test    rax, rax
0x180038331  jz      loc_180038402
0x180038337  mov     rax, [r14]
0x18003833a  lea     r8, [rdi+58h]
0x18003833e  lea     rdx, IID_IDispatch
0x180038345  mov     rcx, r14
0x180038348  mov     rax, [rax]
0x18003834b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038350  mov     ebx, eax
0x180038352  test    eax, eax
0x180038354  js      loc_180038439
0x18003835a  cmp     [rsp+78h+arg_28], 0
0x180038362  jz      short loc_18003837A
0x180038364  mov     rcx, [rdi+58h]; struct IUnknown *
0x180038368  mov     rdx, r14; struct IUnknown *
0x18003836b  call    ?HrCopyProxyIdentity@@YAJPEAUIUnknown@@0@Z; HrCopyProxyIdentity(IUnknown *,IUnknown *)
0x180038370  mov     ebx, eax
0x180038372  test    eax, eax
0x180038374  js      loc_180038439
0x18003837a  mov     rcx, cs:WPP_GLOBAL_Control
0x180038381  cmp     rcx, rsi
0x180038384  jz      short loc_1800383A1
0x180038386  test    byte ptr [rcx+1Ch], 40h
0x18003838a  jz      short loc_1800383A1
0x18003838c  mov     rcx, [rcx+10h]
0x180038390  lea     r8, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids
0x180038397  mov     edx, 0Ch
0x18003839c  call    WPP_SF_
0x1800383a1  mov     rdx, r15; psz
0x1800383a4  mov     rcx, rdi; this
0x1800383a7  call    ?HrProcessServiceDescription@CUPnPAutomationProxy@@AEAAJPEAG@Z; CUPnPAutomationProxy::HrProcessServiceDescription(ushort *)
0x1800383ac  mov     ebx, eax
0x1800383ae  test    eax, eax
0x1800383b0  js      loc_180038439
0x1800383b6  mov     rcx, r12; pszSrc
0x1800383b9  call    ?WszDupWsz@@YAPEAGPEBG@Z; WszDupWsz(ushort const *)
0x1800383be  mov     [rdi+88h], rax
0x1800383c5  test    rax, rax
0x1800383c8  jz      short loc_1800383D4
0x1800383ca  mov     eax, 2
0x1800383cf  xchg    eax, [rdi+50h]
0x1800383d2  jmp     short loc_180038439
0x1800383d4  mov     ebx, 8007000Eh
0x1800383d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800383e0  cmp     rcx, rsi
0x1800383e3  jz      short loc_180038440
0x1800383e5  test    [rcx+1Ch], r13b
0x1800383e9  jz      short loc_180038440
0x1800383eb  mov     rcx, [rcx+10h]
0x1800383ef  lea     r8, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids
0x1800383f6  mov     edx, 0Dh
0x1800383fb  call    WPP_SF_
0x180038400  jmp     short loc_180038439
0x180038402  mov     ebx, 8007000Eh
0x180038407  mov     rcx, cs:WPP_GLOBAL_Control
0x18003840e  cmp     rcx, rsi
0x180038411  jz      short loc_180038440
0x180038413  test    [rcx+1Ch], r13b
0x180038417  jz      short loc_180038440
0x180038419  mov     rcx, [rcx+10h]
0x18003841d  lea     r9, aCupnpautomatio_69; "CUPnPAutomationProxy::Initialize - Unab"...
0x180038424  mov     edx, 0Eh
0x180038429  mov     [rsp+78h+var_58], ebx
0x18003842d  lea     r8, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids
0x180038434  call    WPP_SF_sd
0x180038439  mov     rcx, cs:WPP_GLOBAL_Control
0x180038440  test    ebx, ebx
0x180038442  js      short loc_18003848D
0x180038444  jz      loc_18003855C
0x18003844a  jmp     loc_18003850C
0x18003844f  mov     ebx, 80070057h
0x180038454  mov     rcx, cs:WPP_GLOBAL_Control
0x18003845b  lea     rsi, WPP_GLOBAL_Control
0x180038462  cmp     rcx, rsi
0x180038465  jz      short loc_18003848D
0x180038467  test    [rcx+1Ch], r13b
0x18003846b  jz      short loc_18003848D
0x18003846d  mov     rcx, [rcx+10h]
0x180038471  lea     r9, aCupnpautomatio_24; "CUPnPAutomationProxy::Initialize - NULL"...
0x180038478  mov     edx, 0Fh
0x18003847d  mov     [rsp+78h+var_58], ebx
0x180038481  lea     r8, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids
0x180038488  call    WPP_SF_sd
0x18003848d  mov     rcx, [rdi+58h]
0x180038491  test    rcx, rcx
0x180038494  jz      short loc_1800384AA
0x180038496  mov     rax, [rcx]
0x180038499  mov     rax, [rax+10h]
0x18003849d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800384a2  mov     qword ptr [rdi+58h], 0
0x1800384aa  mov     rcx, rdi; this
0x1800384ad  call    ?FreeVariableTable@CUPnPAutomationProxy@@AEAAXXZ; CUPnPAutomationProxy::FreeVariableTable(void)
0x1800384b2  mov     rcx, rdi; this
0x1800384b5  call    ?FreeActionTable@CUPnPAutomationProxy@@AEAAXXZ; CUPnPAutomationProxy::FreeActionTable(void)
0x1800384ba  mov     rcx, [rdi+80h]; Block
0x1800384c1  test    rcx, rcx
0x1800384c4  jz      short loc_1800384DD
0x1800384c6  call    cs:__imp_free
0x1800384cd  nop     dword ptr [rax+rax+00h]
0x1800384d2  mov     qword ptr [rdi+80h], 0
0x1800384dd  mov     rcx, [rdi+88h]; Block
0x1800384e4  test    rcx, rcx
0x1800384e7  jz      short loc_180038500
0x1800384e9  call    cs:__imp_free
0x1800384f0  nop     dword ptr [rax+rax+00h]
0x1800384f5  mov     qword ptr [rdi+88h], 0
0x180038500  xor     eax, eax
0x180038502  xchg    eax, [rdi+50h]
0x180038505  mov     rcx, cs:WPP_GLOBAL_Control
0x18003850c  cmp     rcx, rsi
0x18003850f  jz      short loc_18003855C
0x180038511  test    [rcx+1Ch], r13b
0x180038515  jz      short loc_18003855C
0x180038517  mov     edx, 10h
0x18003851c  jmp     short loc_180038541
0x18003851e  mov     rcx, cs:WPP_GLOBAL_Control
0x180038525  lea     rsi, WPP_GLOBAL_Control
0x18003852c  mov     ebx, 80070057h
0x180038531  cmp     rcx, rsi
0x180038534  jz      short loc_18003855C
0x180038536  test    [rcx+1Ch], r13b
0x18003853a  jz      short loc_18003855C
0x18003853c  mov     edx, 0Bh
0x180038541  lea     r9, aCupnpautomatio_23; "CUPnPAutomationProxy::Initialize(): Exi"...
0x180038548  mov     rcx, [rcx+10h]
0x18003854c  lea     r8, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids
0x180038553  mov     [rsp+78h+var_58], ebx
0x180038557  call    WPP_SF_sd
0x18003855c  mov     eax, ebx
0x18003855e  add     rsp, 40h
0x180038562  pop     r15
0x180038564  pop     r14
0x180038566  pop     r13
0x180038568  pop     r12
0x18003856a  pop     rdi
0x18003856b  pop     rsi
0x18003856c  pop     rbx
0x18003856d  retn
```
