# CWcnEapSession::Init(CWcnEapTransport *,_DOT11_SSID const *,uchar const * const,_GUID const *,CWcnSession *,ulong)

- ea: `0x180047544`
- end: `0x1800479fb`
- name: `?Init@CWcnEapSession@@QEAAJPEAVCWcnEapTransport@@PEBU_DOT11_SSID@@QEBEPEBU_GUID@@PEAVCWcnSession@@K@Z`
- size: `1207`
- prototype: `__int64 __fastcall(CWcnEapSession *this, struct CWcnEapTransport *, const struct _DOT11_SSID *, const unsigned __int8 *const, struct _GUID *rguid, struct CWcnSession *, unsigned int)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, service_task, installer_update`

## callers

- `0x180048990`

## callees

- `0x180004f2c`
- `0x180004f78`
- `0x180004fb8`
- `0x180005014`
- `0x18000b1f8`
- `0x180018c6c`
- `0x18003cfa4`
- `0x180045f24`
- `0x180046e54`
- `0x180047544`
- `0x180050b38`
- `0x1800510b8`
- `0x180053004`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x1800477b0`
- `RPCRT4!UuidCreate` at `0x1800477b0`
- `wlanapi!WlanRegisterNotification` at `0x180047901`
- `wlanapi!WlanRegisterNotification` at `0x180047901`

## string_xrefs

- `0x1800475cb`: `pSsid`

## pseudocode

```c
__int64 __fastcall CWcnEapSession::Init(
        CWcnEapSession *this,
        struct CWcnEapTransport *a2,
        const struct _DOT11_SSID *a3,
        const unsigned __int8 *const a4,
        struct _GUID *rguid,
        struct CWcnSession *a6,
        unsigned int a7)
{
  _BYTE *v11; // r10
  const char *Indent; // rax
  __int64 v13; // r10
  __int64 v14; // r11
  __int64 v15; // rdx
  const char *v16; // r9
  unsigned int v18; // ebx
  const char *v19; // rax
  __int64 v20; // r10
  __int64 v21; // r11
  const char *v22; // rax
  __int64 v23; // r10
  __int64 v24; // rdx
  __int64 *v25; // r11
  __int64 *v26; // r8
  const char *v27; // rax
  __int64 v28; // r10
  __int64 v29; // r11
  __int16 v30; // ax
  int v31; // eax
  unsigned int v32; // ebx
  unsigned int v33; // ebx
  _QWORD *v34; // r10
  __int64 v35; // rdx
  int MacAddressOfInterface; // eax
  int WorkItem; // eax
  __int64 v38; // rdx
  unsigned int v39; // ebx
  unsigned int v40; // eax
  __int64 v41; // r10

  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v13 + 16), 10, v14, Indent);
    v11 = WPP_GLOBAL_Control;
  }
  if ( !a3 )
  {
    if ( v11 == (_BYTE *)&WPP_GLOBAL_Control || v11[25] < 2u )
      return 2147500035LL;
    v15 = 11;
    v16 = "pSsid";
LABEL_24:
    WPP_SF_s(*((_QWORD *)v11 + 2), v15, WPP_d51b5dd3fd9d3cc4affb2b658910bdd8_Traceguids, v16);
    return 2147500035LL;
  }
  if ( !rguid )
  {
    if ( v11 == (_BYTE *)&WPP_GLOBAL_Control || v11[25] < 2u )
      return 2147500035LL;
    v15 = 12;
    v16 = "pWlanInterface";
    goto LABEL_24;
  }
  if ( !a2 )
  {
    if ( v11 == (_BYTE *)&WPP_GLOBAL_Control || v11[25] < 2u )
      return 2147500035LL;
    v15 = 13;
    v16 = "pEapTransport";
    goto LABEL_24;
  }
  if ( !a6 )
  {
    if ( v11 == (_BYTE *)&WPP_GLOBAL_Control || v11[25] < 2u )
      return 2147500035LL;
    v15 = 14;
    v16 = "pWcnSession";
    goto LABEL_24;
  }
  if ( !a4 )
  {
    if ( v11 == (_BYTE *)&WPP_GLOBAL_Control || v11[25] < 2u )
      return 2147500035LL;
    v15 = 15;
    v16 = "MacAddress";
    goto LABEL_24;
  }
  v18 = a7;
  if ( (a7 & 0x2000) != 0 )
  {
    if ( (a7 & 0x100000) != 0 )
    {
      if ( (*((_BYTE *)a2 + 324) & 1) != 0 )
      {
        if ( v11 != (_BYTE *)&WPP_GLOBAL_Control && v11[25] >= 5u )
        {
          v19 = GetIndent(0);
          WPP_SF_s(*(_QWORD *)(v20 + 16), 16, v21, v19);
        }
        v18 = 4224;
        CWcnSession::UpdateSelfIdentity(a6, 0x1080u);
        goto LABEL_47;
      }
      if ( v11 == (_BYTE *)&WPP_GLOBAL_Control || v11[25] < 5u )
      {
LABEL_44:
        v18 = a7 | 0x20;
        goto LABEL_47;
      }
      v22 = GetIndent(0);
      v24 = 17;
      v26 = v25;
LABEL_43:
      WPP_SF_s(*(_QWORD *)(v23 + 16), v24, v26, v22);
      goto LABEL_44;
    }
    if ( v11 != (_BYTE *)&WPP_GLOBAL_Control && v11[25] >= 5u )
    {
      v27 = GetIndent(0);
      WPP_SF_s(*(_QWORD *)(v28 + 16), 18, v29, v27);
      v11 = WPP_GLOBAL_Control;
    }
    if ( (*((_DWORD *)a2 + 81) & 1) == 0 )
    {
      if ( v11 == (_BYTE *)&WPP_GLOBAL_Control || v11[25] < 5u )
        goto LABEL_44;
      v22 = GetIndent(0);
      v24 = 19;
      v26 = WPP_d51b5dd3fd9d3cc4affb2b658910bdd8_Traceguids;
      goto LABEL_43;
    }
  }
  else
  {
    v18 = a7 | 0x1048;
    if ( (a7 & 0x8000) != 0 )
      v18 = a7 | 0x1049;
  }
LABEL_47:
  *((_DWORD *)this + 29) = *(_DWORD *)a4;
  v30 = *((_WORD *)a4 + 2);
  *((_QWORD *)this + 19) = a2;
  *((_WORD *)this + 60) = v30;
  *((struct _GUID *)this + 4) = *rguid;
  *((_OWORD *)this + 5) = *(_OWORD *)&a3->uSSIDLength;
  *((_OWORD *)this + 6) = *(_OWORD *)&a3->ucSSID[12];
  *((_DWORD *)this + 28) = *(_DWORD *)&a3->ucSSID[28];
  *((_QWORD *)this + 2) = a6;
  *((_BYTE *)this + 344) = 0;
  *((_DWORD *)this + 6) = v18;
  *((_DWORD *)this + 35) = v18;
  v31 = UuidCreate((UUID *)((char *)this + 124));
  if ( v31 )
  {
    if ( v31 > 0 )
      v32 = (unsigned __int16)v31 | 0x80070000;
    else
      v32 = v31;
    v33 = v32 | 0x80000000;
    v34 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v33;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_84;
    v35 = 20;
LABEL_54:
    WPP_SF_Dd(v34[2], v35, WPP_d51b5dd3fd9d3cc4affb2b658910bdd8_Traceguids, (unsigned int)v31, v33);
LABEL_83:
    v34 = WPP_GLOBAL_Control;
    goto LABEL_84;
  }
  MacAddressOfInterface = WcnWlanGetMacAddressOfInterface(rguid, (unsigned __int8 (*)[6])((char *)this + 8));
  v33 = MacAddressOfInterface;
  if ( MacAddressOfInterface >= 0 )
  {
    WorkItem = CWcnScheduler::CreateWorkItem(
                 (CWcnScheduler *)(*((_QWORD *)g_pWcnService + 7) + 320LL),
                 (void (__stdcall *)(PTP_CALLBACK_INSTANCE, PVOID, PTP_WORK))CWcnEapSession::RealDisconnectThunk,
                 this,
                 (struct _TP_WORK **)this + 20);
    v33 = WorkItem;
    if ( WorkItem >= 0 )
    {
      WorkItem = WcnWlanOpenHandle((PHANDLE)this + 7);
      v33 = WorkItem;
      if ( WorkItem >= 0 )
      {
        v31 = WlanRegisterNotification(
                *((HANDLE *)this + 7),
                8u,
                0,
                CWcnEapSession::WlanNotificationCallbackThunk,
                this,
                0,
                0);
        if ( v31 )
        {
          if ( v31 > 0 )
            v39 = (unsigned __int16)v31 | 0x80070000;
          else
            v39 = v31;
          v33 = v39 | 0x80000000;
          v34 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
            return v33;
          if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            goto LABEL_84;
          v35 = 24;
          goto LABEL_54;
        }
        WorkItem = CWcnEapTransport::NotifySessionCreated(*((CWcnEapTransport **)this + 19), this);
        v33 = WorkItem;
        if ( WorkItem >= 0 )
        {
          WorkItem = CWcnEapSession::Connect(this);
          v33 = WorkItem;
          if ( WorkItem >= 0 )
            goto LABEL_83;
          v34 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
            return v33;
          if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            goto LABEL_84;
          v38 = 26;
        }
        else
        {
          v34 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
            return v33;
          if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            goto LABEL_84;
          v38 = 25;
        }
      }
      else
      {
        v34 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return v33;
        if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_84;
        v38 = 23;
      }
    }
    else
    {
      v34 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v33;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_84;
      v38 = 22;
    }
    WPP_SF_d(v34[2], v38, WPP_d51b5dd3fd9d3cc4affb2b658910bdd8_Traceguids, (unsigned int)WorkItem);
    goto LABEL_83;
  }
  v34 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF__guid_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        WPP_d51b5dd3fd9d3cc4affb2b658910bdd8_Traceguids,
        rguid,
        MacAddressOfInterface);
      goto LABEL_83;
    }
LABEL_84:
    if ( v34 != &WPP_GLOBAL_Control && ((v33 & 0x80000000) != 0 || *((_BYTE *)v34 + 25) >= 6u) )
    {
      v40 = (unsigned int)GetIndent(-1);
      WPP_SF_sd(*(_QWORD *)(v41 + 16), 27, (unsigned int)WPP_d51b5dd3fd9d3cc4affb2b658910bdd8_Traceguids, v40, v33);
    }
  }
  return v33;
}

```

## disassembly

```asm
0x180047544  push    rbx
0x180047546  push    rbp
0x180047547  push    rsi
0x180047548  push    rdi
0x180047549  push    r12
0x18004754b  push    r13
0x18004754d  push    r14
0x18004754f  push    r15
0x180047551  sub     rsp, 48h
0x180047555  mov     r12, r9
0x180047558  mov     r15, r8
0x18004755b  mov     rbp, rdx
0x18004755e  mov     rdi, rcx
0x180047561  mov     r10, cs:WPP_GLOBAL_Control
0x180047568  lea     r13, WPP_GLOBAL_Control
0x18004756f  lea     r11, WPP_d51b5dd3fd9d3cc4affb2b658910bdd8_Traceguids
0x180047576  cmp     r10, r13
0x180047579  jz      short loc_1800475AE
0x18004757b  cmp     byte ptr [r10+19h], 6
0x180047580  jb      short loc_1800475AE
0x180047582  mov     ecx, 1; int
0x180047587  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18004758c  mov     rcx, [r10+10h]
0x180047590  mov     edx, 0Ah
0x180047595  mov     r9, rax
0x180047598  mov     r8, r11
0x18004759b  call    WPP_SF_s
0x1800475a0  mov     r10, cs:WPP_GLOBAL_Control
0x1800475a7  lea     r11, WPP_d51b5dd3fd9d3cc4affb2b658910bdd8_Traceguids
0x1800475ae  test    r15, r15
0x1800475b1  jnz     short loc_1800475D7
0x1800475b3  cmp     r10, r13
0x1800475b6  jz      loc_180047668
0x1800475bc  cmp     byte ptr [r10+19h], 2
0x1800475c1  jb      loc_180047668
0x1800475c7  lea     edx, [r15+0Bh]
0x1800475cb  lea     r9, aPssid; "pSsid"
0x1800475d2  jmp     loc_18004765C
0x1800475d7  mov     rsi, [rsp+88h+rguid]
0x1800475df  test    rsi, rsi
0x1800475e2  jnz     short loc_1800475FC
0x1800475e4  cmp     r10, r13
0x1800475e7  jz      short loc_180047668
0x1800475e9  cmp     byte ptr [r10+19h], 2
0x1800475ee  jb      short loc_180047668
0x1800475f0  lea     edx, [rsi+0Ch]
0x1800475f3  lea     r9, aPwlaninterface_0; "pWlanInterface"
0x1800475fa  jmp     short loc_18004765C
0x1800475fc  test    rbp, rbp
0x1800475ff  jnz     short loc_180047619
0x180047601  cmp     r10, r13
0x180047604  jz      short loc_180047668
0x180047606  cmp     byte ptr [r10+19h], 2
0x18004760b  jb      short loc_180047668
0x18004760d  lea     edx, [rbp+0Dh]
0x180047610  lea     r9, aPeaptransport; "pEapTransport"
0x180047617  jmp     short loc_18004765C
0x180047619  mov     r14, [rsp+88h+arg_28]
0x180047621  test    r14, r14
0x180047624  jnz     short loc_18004763F
0x180047626  cmp     r10, r13
0x180047629  jz      short loc_180047668
0x18004762b  cmp     byte ptr [r10+19h], 2
0x180047630  jb      short loc_180047668
0x180047632  lea     edx, [r14+0Eh]
0x180047636  lea     r9, aPwcnsession; "pWcnSession"
0x18004763d  jmp     short loc_18004765C
0x18004763f  test    r12, r12
0x180047642  jnz     short loc_180047672
0x180047644  cmp     r10, r13
0x180047647  jz      short loc_180047668
0x180047649  cmp     byte ptr [r10+19h], 2
0x18004764e  jb      short loc_180047668
0x180047650  lea     edx, [r12+0Fh]
0x180047655  lea     r9, aMacaddress; "MacAddress"
0x18004765c  mov     rcx, [r10+10h]
0x180047660  mov     r8, r11
0x180047663  call    WPP_SF_s
0x180047668  mov     eax, 80004003h
0x18004766d  jmp     loc_1800479EA
0x180047672  mov     ebx, [rsp+88h+arg_30]
0x180047679  bt      ebx, 0Dh
0x18004767d  jnb     loc_180047752
0x180047683  bt      ebx, 14h
0x180047687  jnb     short loc_1800476EA
0x180047689  test    byte ptr [rbp+144h], 1
0x180047690  jz      short loc_1800476CD
0x180047692  cmp     r10, r13
0x180047695  jz      short loc_1800476B9
0x180047697  cmp     byte ptr [r10+19h], 5
0x18004769c  jb      short loc_1800476B9
0x18004769e  xor     ecx, ecx; int
0x1800476a0  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800476a5  mov     rcx, [r10+10h]
0x1800476a9  mov     edx, 10h
0x1800476ae  mov     r9, rax
0x1800476b1  mov     r8, r11
0x1800476b4  call    WPP_SF_s
0x1800476b9  mov     ebx, 1080h
0x1800476be  mov     rcx, r14; this
0x1800476c1  mov     edx, ebx; unsigned int
0x1800476c3  call    ?UpdateSelfIdentity@CWcnSession@@QEAAJK@Z; CWcnSession::UpdateSelfIdentity(ulong)
0x1800476c8  jmp     loc_180047761
0x1800476cd  cmp     r10, r13
0x1800476d0  jz      short loc_18004774D
0x1800476d2  cmp     byte ptr [r10+19h], 5
0x1800476d7  jb      short loc_18004774D
0x1800476d9  xor     ecx, ecx; int
0x1800476db  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800476e0  mov     edx, 11h
0x1800476e5  mov     r8, r11
0x1800476e8  jmp     short loc_180047741
0x1800476ea  cmp     r10, r13
0x1800476ed  jz      short loc_180047718
0x1800476ef  cmp     byte ptr [r10+19h], 5
0x1800476f4  jb      short loc_180047718
0x1800476f6  xor     ecx, ecx; int
0x1800476f8  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800476fd  mov     rcx, [r10+10h]
0x180047701  mov     edx, 12h
0x180047706  mov     r9, rax
0x180047709  mov     r8, r11
0x18004770c  call    WPP_SF_s
0x180047711  mov     r10, cs:WPP_GLOBAL_Control
0x180047718  mov     eax, [rbp+144h]
0x18004771e  test    al, 1
0x180047720  jnz     short loc_180047761
0x180047722  cmp     r10, r13
0x180047725  jz      short loc_18004774D
0x180047727  cmp     byte ptr [r10+19h], 5
0x18004772c  jb      short loc_18004774D
0x18004772e  xor     ecx, ecx; int
0x180047730  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180047735  mov     edx, 13h
0x18004773a  lea     r8, WPP_d51b5dd3fd9d3cc4affb2b658910bdd8_Traceguids
0x180047741  mov     rcx, [r10+10h]
0x180047745  mov     r9, rax
0x180047748  call    WPP_SF_s
0x18004774d  or      ebx, 20h
0x180047750  jmp     short loc_180047761
0x180047752  or      ebx, 1048h
0x180047758  bt      ebx, 0Fh
0x18004775c  jnb     short loc_180047761
0x18004775e  or      ebx, 1
0x180047761  mov     eax, [r12]
0x180047765  lea     rcx, [rdi+7Ch]; Uuid
0x180047769  mov     [rdi+74h], eax
0x18004776c  movzx   eax, word ptr [r12+4]
0x180047772  mov     [rdi+98h], rbp
0x180047779  xor     ebp, ebp
0x18004777b  mov     [rdi+78h], ax
0x18004777f  movups  xmm0, xmmword ptr [rsi]
0x180047782  movdqu  xmmword ptr [rdi+40h], xmm0
0x180047787  movups  xmm0, xmmword ptr [r15]
0x18004778b  movups  xmmword ptr [rdi+50h], xmm0
0x18004778f  movups  xmm1, xmmword ptr [r15+10h]
0x180047794  movups  xmmword ptr [rdi+60h], xmm1
0x180047798  mov     eax, [r15+20h]
0x18004779c  mov     [rdi+70h], eax
0x18004779f  mov     [rdi+10h], r14
0x1800477a3  mov     [rdi+158h], bpl
0x1800477aa  mov     [rdi+18h], ebx
0x1800477ad  mov     [rcx+10h], ebx
0x1800477b0  call    cs:__imp_UuidCreate
0x1800477b6  test    eax, eax
0x1800477b8  jz      short loc_18004780B
0x1800477ba  jg      short loc_1800477C0
0x1800477bc  mov     ebx, eax
0x1800477be  jmp     short loc_1800477C9
0x1800477c0  movzx   ebx, ax
0x1800477c3  or      ebx, 80070000h
0x1800477c9  or      ebx, 80000000h
0x1800477cf  mov     r10, cs:WPP_GLOBAL_Control
0x1800477d6  cmp     r10, r13
0x1800477d9  jz      loc_1800479E8
0x1800477df  cmp     byte ptr [r10+19h], 2
0x1800477e4  jb      loc_1800479B4
0x1800477ea  mov     edx, 14h
0x1800477ef  mov     rcx, [r10+10h]
0x1800477f3  lea     r8, WPP_d51b5dd3fd9d3cc4affb2b658910bdd8_Traceguids
0x1800477fa  mov     r9d, eax
0x1800477fd  mov     dword ptr [rsp+88h+pCallbackContext], ebx
0x180047801  call    WPP_SF_Dd
0x180047806  jmp     loc_1800479AD
0x18004780b  lea     rdx, [rdi+8]; unsigned __int8 (*)[6]
0x18004780f  mov     rcx, rsi; rguid
0x180047812  call    ?WcnWlanGetMacAddressOfInterface@@YAJPEBU_GUID@@PEAY05E@Z; WcnWlanGetMacAddressOfInterface(_GUID const *,uchar (*)[6])
0x180047817  mov     ebx, eax
0x180047819  test    eax, eax
0x18004781b  jns     short loc_180047859
0x18004781d  mov     r10, cs:WPP_GLOBAL_Control
0x180047824  cmp     r10, r13
0x180047827  jz      loc_1800479E8
0x18004782d  cmp     byte ptr [r10+19h], 2
0x180047832  jb      loc_1800479B4
0x180047838  mov     rcx, [r10+10h]
0x18004783c  lea     r8, WPP_d51b5dd3fd9d3cc4affb2b658910bdd8_Traceguids
0x180047843  mov     edx, 15h
0x180047848  mov     dword ptr [rsp+88h+pCallbackContext], eax
0x18004784c  mov     r9, rsi
0x18004784f  call    WPP_SF__guid_d
0x180047854  jmp     loc_1800479AD
0x180047859  mov     rax, cs:?g_pWcnService@@3PEAVCWcnService@@EA; CWcnService * g_pWcnService
0x180047860  lea     r9, [rdi+0A0h]; struct _TP_WORK **
0x180047867  mov     r8, rdi; void *
0x18004786a  lea     rdx, ?RealDisconnectThunk@CWcnEapSession@@CAXPEAX00@Z; void (*)(void *, void *, void *)
0x180047871  mov     rcx, [rax+38h]
0x180047875  add     rcx, 140h; this
0x18004787c  call    ?CreateWorkItem@CWcnScheduler@@QEAAJP6AXPEAX00@Z0PEAPEAU_TP_WORK@@@Z; CWcnScheduler::CreateWorkItem(void (*)(void *,void *,void *),void *,_TP_WORK * *)
0x180047881  mov     ebx, eax
0x180047883  test    eax, eax
0x180047885  jns     short loc_1800478AC
0x180047887  mov     r10, cs:WPP_GLOBAL_Control
0x18004788e  cmp     r10, r13
0x180047891  jz      loc_1800479E8
0x180047897  cmp     byte ptr [r10+19h], 2
0x18004789c  jb      loc_1800479B4
0x1800478a2  mov     edx, 16h
0x1800478a7  jmp     loc_18004799A
0x1800478ac  lea     rcx, [rdi+38h]; phClientHandle
0x1800478b0  call    ?WcnWlanOpenHandle@@YAJPEAPEAX@Z; WcnWlanOpenHandle(void * *)
0x1800478b5  mov     ebx, eax
0x1800478b7  test    eax, eax
0x1800478b9  jns     short loc_1800478E0
0x1800478bb  mov     r10, cs:WPP_GLOBAL_Control
0x1800478c2  cmp     r10, r13
0x1800478c5  jz      loc_1800479E8
0x1800478cb  cmp     byte ptr [r10+19h], 2
0x1800478d0  jb      loc_1800479B4
0x1800478d6  mov     edx, 17h
0x1800478db  jmp     loc_18004799A
0x1800478e0  mov     rcx, [rdi+38h]; hClientHandle
0x1800478e4  lea     r9, ?WlanNotificationCallbackThunk@CWcnEapSession@@SAXPEAU_L2_NOTIFICATION_DATA@@PEAX@Z; funcCallback
0x1800478eb  xor     r8d, r8d; bIgnoreDuplicate
0x1800478ee  mov     [rsp+88h+pdwPrevNotifSource], rbp; pdwPrevNotifSource
0x1800478f3  mov     [rsp+88h+pReserved], rbp; pReserved
0x1800478f8  mov     [rsp+88h+pCallbackContext], rdi; pCallbackContext
0x1800478fd  lea     edx, [r8+8]; dwNotifSource
0x180047901  call    cs:__imp_WlanRegisterNotification
0x180047907  test    eax, eax
0x180047909  jz      short loc_180047941
0x18004790b  jg      short loc_180047911
0x18004790d  mov     ebx, eax
0x18004790f  jmp     short loc_18004791A
0x180047911  movzx   ebx, ax
0x180047914  or      ebx, 80070000h
0x18004791a  or      ebx, 80000000h
0x180047920  mov     r10, cs:WPP_GLOBAL_Control
0x180047927  cmp     r10, r13
0x18004792a  jz      loc_1800479E8
0x180047930  cmp     byte ptr [r10+19h], 2
0x180047935  jb      short loc_1800479B4
0x180047937  mov     edx, 18h
0x18004793c  jmp     loc_1800477EF
0x180047941  mov     rcx, [rdi+98h]; this
0x180047948  mov     rdx, rdi; struct CWcnEapSession *
0x18004794b  call    ?NotifySessionCreated@CWcnEapTransport@@QEAAJPEAVCWcnEapSession@@@Z; CWcnEapTransport::NotifySessionCreated(CWcnEapSession *)
0x180047950  mov     ebx, eax
0x180047952  test    eax, eax
0x180047954  jns     short loc_180047974
0x180047956  mov     r10, cs:WPP_GLOBAL_Control
0x18004795d  cmp     r10, r13
0x180047960  jz      loc_1800479E8
0x180047966  cmp     byte ptr [r10+19h], 2
0x18004796b  jb      short loc_1800479B4
0x18004796d  mov     edx, 19h
0x180047972  jmp     short loc_18004799A
0x180047974  mov     rcx, rdi; this
0x180047977  call    ?Connect@CWcnEapSession@@AEAAJXZ; CWcnEapSession::Connect(void)
0x18004797c  mov     ebx, eax
0x18004797e  test    eax, eax
0x180047980  jns     short loc_1800479AD
0x180047982  mov     r10, cs:WPP_GLOBAL_Control
0x180047989  cmp     r10, r13
0x18004798c  jz      short loc_1800479E8
0x18004798e  cmp     byte ptr [r10+19h], 2
0x180047993  jb      short loc_1800479B4
0x180047995  mov     edx, 1Ah
0x18004799a  mov     rcx, [r10+10h]
0x18004799e  lea     r8, WPP_d51b5dd3fd9d3cc4affb2b658910bdd8_Traceguids
0x1800479a5  mov     r9d, eax
0x1800479a8  call    WPP_SF_d
0x1800479ad  mov     r10, cs:WPP_GLOBAL_Control
0x1800479b4  cmp     r10, r13
0x1800479b7  jz      short loc_1800479E8
0x1800479b9  test    ebx, ebx
0x1800479bb  js      short loc_1800479C4
0x1800479bd  cmp     byte ptr [r10+19h], 6
0x1800479c2  jb      short loc_1800479E8
0x1800479c4  or      ecx, 0FFFFFFFFh; int
0x1800479c7  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800479cc  mov     rcx, [r10+10h]
0x1800479d0  lea     r8, WPP_d51b5dd3fd9d3cc4affb2b658910bdd8_Traceguids
0x1800479d7  mov     edx, 1Bh
0x1800479dc  mov     dword ptr [rsp+88h+pCallbackContext], ebx
0x1800479e0  mov     r9, rax
0x1800479e3  call    WPP_SF_sd
0x1800479e8  mov     eax, ebx
0x1800479ea  add     rsp, 48h
0x1800479ee  pop     r15
  ... truncated ...
```
