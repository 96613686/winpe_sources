# CSubscriptionMgr::CreateSubscriptionNoSummary(HWND__ *,ushort const *,ushort const *,ulong,SUBSCRIPTIONTYPE,_tagSubscriptionInfo *)

- ea: `0x1800170c8`
- end: `0x1800173e7`
- name: `?CreateSubscriptionNoSummary@CSubscriptionMgr@@IEAAJPEAUHWND__@@PEBG1KW4SUBSCRIPTIONTYPE@@PEAU_tagSubscriptionInfo@@@Z`
- size: `799`
- prototype: `__int64 __fastcall(CSubscriptionMgr *__hidden this, HWND, const unsigned __int16 *, const unsigned __int16 *, char, enum SUBSCRIPTIONTYPE, struct _tagSubscriptionInfo *)`
- caller_count: `3`
- callee_count: `15`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180016e18`
- `0x180016f80`
- `0x1800182c0`

## callees

- `0x180003950`
- `0x18000b514`
- `0x18000bb8c`
- `0x18000cc84`
- `0x180016af0`
- `0x180016ce4`
- `0x1800170c8`
- `0x1800185b4`
- `0x18001be60`
- `0x18001cd88`
- `0x18001d420`
- `0x180022ba0`
- `0x180029280`
- `0x180029310`
- `0x18002a010`

## import_xrefs

- `IEFRAME!__imp_SHRestricted2W` at `0x180017203`
- `IEFRAME!__imp_SHRestricted2W` at `0x18001721e`
- `IEFRAME!__imp_SHRestricted2W` at `0x1800172ee`
- `IEFRAME!__imp_SHRestricted2W` at `0x180017203`
- `IEFRAME!__imp_SHRestricted2W` at `0x18001721e`
- `IEFRAME!__imp_SHRestricted2W` at `0x1800172ee`
- `ole32!CoTaskMemFree` at `0x180017376`
- `ole32!CoTaskMemFree` at `0x180017376`

## pseudocode

```c
__int64 __fastcall CSubscriptionMgr::CreateSubscriptionNoSummary(
        CSubscriptionMgr *this,
        HWND a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        char a5,
        enum SUBSCRIPTIONTYPE a6,
        struct _tagSubscriptionInfo *a7)
{
  int SubscriptionFromOOEBuf; // edi
  _WORD *pTrigger; // rax
  __int64 v13; // rax
  unsigned int v14; // eax
  unsigned int v15; // edi
  CSubscriptionMgr *v16; // rcx
  LPCITEMIDLIST *v17; // rbx
  void *v18; // rcx
  __int64 v19; // rcx
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  unsigned int v21; // [rsp+24h] [rbp-DCh] BYREF
  unsigned __int16 *v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v24; // [rsp+34h] [rbp-CCh]
  __int64 v25; // [rsp+3Ch] [rbp-C4h]
  int v26; // [rsp+6Ch] [rbp-94h]
  GUID iid; // [rsp+A4h] [rbp-5Ch] BYREF
  __int16 v28; // [rsp+DCh] [rbp-24h]
  __int16 v29; // [rsp+1DCh] [rbp+DCh]
  unsigned __int16 v30[2085]; // [rsp+25Ch] [rbp+15Ch] BYREF
  unsigned __int16 v31[389]; // [rsp+12A6h] [rbp+11A6h] BYREF
  int v32; // [rsp+15B0h] [rbp+14B0h]

  v22 = a4;
  if ( (unsigned int)a6 > SUBSTYPE_DESKTOPURL && a6 != SUBSTYPE_DESKTOPCHANNEL )
    return 2147942487LL;
  SubscriptionFromOOEBuf = 0;
  if ( !a3 || !a4 )
    return 2147942487LL;
  if ( a7 )
  {
    if ( a7->cbSize != 112 )
      return 2147942487LL;
    if ( (a7->fUpdateFlags & 0xFFFF1080) != 0 )
      return 2147942487LL;
    pTrigger = a7->pTrigger;
    if ( pTrigger )
    {
      if ( *pTrigger && (a6 & 0xFFFFFFFD) == 0 )
        return 2147942487LL;
    }
    if ( (a7->fUpdateFlags & 1) != 0 )
    {
      if ( a7->schedule > SUBSSCHED_MANUAL )
        return 2147942487LL;
      if ( a7->schedule == SUBSSCHED_CUSTOM )
      {
        v13 = *(_QWORD *)&a7->customGroupCookie.Data1 - *(_QWORD *)&GUID_NULL.Data1;
        if ( !v13 )
          v13 = *(_QWORD *)a7->customGroupCookie.Data4 - *(_QWORD *)GUID_NULL.Data4;
        if ( !v13 )
          return 2147942487LL;
      }
    }
  }
  else if ( (a5 & 8) != 0 )
  {
    return 2147942487LL;
  }
  v20 = 0;
  if ( ((*(int (__fastcall **)(char *, const unsigned __int16 *, int *))(*((_QWORD *)this + 2) + 48LL))(
          (char *)this + 16,
          a3,
          &v20) < 0
     || v20)
    && (a5 & 0xC) == 0 )
  {
    return 2147500037LL;
  }
  if ( a6 == SUBSTYPE_URL )
  {
    v14 = SHRestricted2W(1342177298, 0, 0);
    v21 = 0;
    v15 = v14;
    if ( (unsigned int)SHRestricted2W(1342177285, a3, 0)
      || v15 && (int)CSubscriptionMgr::CountSubscriptions(this, SUBSTYPE_URL, &v21) >= 0 && v21 >= v15 )
    {
      if ( (a5 & 4) == 0 )
        SGMessageBox(a2, 0x1FBCu, 0);
      return 2147942405LL;
    }
    SubscriptionFromOOEBuf = 0;
  }
  v24 = 0;
  v25 = 0;
  GetDefaultOOEBuf((struct OOEBuf *)&v23, a6);
  StringCchCopyW(v30, 0x824u, a3);
  if ( !(unsigned int)IsHTTPPrefixed(v30) )
    return 2147942487LL;
  if ( a7 )
  {
    CSubscriptionMgr::ChangeSubscriptionValues(v16, (struct OOEBuf *)&v23, a7);
    if ( v20 )
    {
      ReadCookieFromInetDB(v30, &iid);
      v32 |= 0x10u;
    }
  }
  if ( (unsigned int)SHRestricted2W(1342177305, 0, 0) )
  {
    v26 = 0;
    v23 &= 0xFFFFFE7F;
    v28 = 0;
    v29 = 0;
  }
  StringCchCopyW(v30, 0x824u, a3);
  StringCchCopyW(v31, 0x104u, v22);
  if ( (a5 & 4) != 0
    || (SubscriptionFromOOEBuf = CreateWizard(a2, a6, (struct OOEBuf *)&v23), SubscriptionFromOOEBuf >= 0) )
  {
    if ( (a5 & 8) != 0 )
    {
      if ( !SubscriptionFromOOEBuf )
      {
        a7->fUpdateFlags = 61311;
        UpdateSubsInfoFromOOE(a7, (struct OOEBuf *)&v23);
      }
    }
    else
    {
      v17 = (LPCITEMIDLIST *)((char *)this + 40);
      v18 = (void *)*((_QWORD *)this + 5);
      if ( v18 )
      {
        CoTaskMemFree(v18);
        v19 = *((_QWORD *)this + 660);
        *v17 = 0;
        if ( v19 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
          *((_QWORD *)this + 660) = 0;
        }
      }
      SubscriptionFromOOEBuf = CreateSubscriptionFromOOEBuf((struct OOEBuf *)&v23, (LPVOID *)this + 5);
      if ( SubscriptionFromOOEBuf >= 0 )
        GenerateEvent(2, *v17);
    }
  }
  return (unsigned int)SubscriptionFromOOEBuf;
}

```

## disassembly

```asm
0x1800170c8  push    rbp
0x1800170ca  push    rbx
0x1800170cb  push    rdi
0x1800170cc  push    r12
0x1800170ce  push    r13
0x1800170d0  push    r15
0x1800170d2  lea     rbp, [rsp-14D8h]
0x1800170da  mov     eax, 15D8h
0x1800170df  call    _alloca_probe
0x1800170e4  sub     rsp, rax
0x1800170e7  mov     rax, cs:__security_cookie
0x1800170ee  xor     rax, rsp
0x1800170f1  mov     [rbp+1500h+var_40], rax
0x1800170f8  cmp     [rbp+1500h+arg_28], 2
0x1800170ff  mov     rax, r9
0x180017102  mov     rbx, [rbp+1500h+arg_30]
0x180017109  mov     r12, r8
0x18001710c  mov     [rsp+1600h+var_15D8], rax
0x180017111  mov     r13, rdx
0x180017114  mov     r15, rcx
0x180017117  jbe     short loc_180017122
0x180017119  cmp     [rbp+1500h+arg_28], 4
0x180017120  jnz     short loc_18001713C
0x180017122  xor     edi, edi
0x180017124  test    r12, r12
0x180017127  jz      short loc_18001713C
0x180017129  test    rax, rax
0x18001712c  jz      short loc_18001713C
0x18001712e  test    rbx, rbx
0x180017131  jnz     short loc_180017161
0x180017133  test    [rbp+1500h+arg_20], 8
0x18001713a  jz      short loc_1800171B8
0x18001713c  mov     eax, 80070057h
0x180017141  mov     rcx, [rbp+1500h+var_40]
0x180017148  xor     rcx, rsp; StackCookie
0x18001714b  call    __security_check_cookie
0x180017150  add     rsp, 15D8h
0x180017157  pop     r15
0x180017159  pop     r13
0x18001715b  pop     r12
0x18001715d  pop     rdi
0x18001715e  pop     rbx
0x18001715f  pop     rbp
0x180017160  retn
0x180017161  cmp     dword ptr [rbx], 70h ; 'p'
0x180017164  jnz     short loc_18001713C
0x180017166  test    dword ptr [rbx+4], 0FFFF1080h
0x18001716d  jnz     short loc_18001713C
0x18001716f  mov     rax, [rbx+20h]
0x180017173  test    rax, rax
0x180017176  jz      short loc_180017189
0x180017178  cmp     [rax], di
0x18001717b  jz      short loc_180017189
0x18001717d  test    [rbp+1500h+arg_28], 0FFFFFFFDh
0x180017187  jz      short loc_18001713C
0x180017189  test    byte ptr [rbx+4], 1
0x18001718d  jz      short loc_1800171B8
0x18001718f  cmp     dword ptr [rbx+8], 4
0x180017193  jg      short loc_18001713C
0x180017195  cmp     dword ptr [rbx+8], 3
0x180017199  jnz     short loc_1800171B8
0x18001719b  mov     rax, [rbx+0Ch]
0x18001719f  sub     rax, qword ptr cs:GUID_NULL.Data1
0x1800171a6  jnz     short loc_1800171B3
0x1800171a8  mov     rax, [rbx+14h]
0x1800171ac  sub     rax, qword ptr cs:GUID_NULL.Data4
0x1800171b3  test    rax, rax
0x1800171b6  jz      short loc_18001713C
0x1800171b8  add     rcx, 10h
0x1800171bc  mov     [rsp+1600h+var_15E0], edi
0x1800171c0  lea     r8, [rsp+1600h+var_15E0]
0x1800171c5  mov     rdx, r12
0x1800171c8  mov     rax, [rcx]
0x1800171cb  mov     rax, [rax+30h]
0x1800171cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171d4  test    eax, eax
0x1800171d6  js      short loc_1800171DE
0x1800171d8  cmp     [rsp+1600h+var_15E0], edi
0x1800171dc  jz      short loc_1800171F1
0x1800171de  test    [rbp+1500h+arg_20], 0Ch
0x1800171e5  jnz     short loc_1800171F1
0x1800171e7  mov     eax, 80004005h
0x1800171ec  jmp     loc_180017141
0x1800171f1  cmp     [rbp+1500h+arg_28], edi
0x1800171f7  jnz     short loc_18001726A
0x1800171f9  xor     r8d, r8d
0x1800171fc  xor     edx, edx
0x1800171fe  mov     ecx, 50000012h
0x180017203  call    cs:__imp_SHRestricted2W
0x180017209  xor     r8d, r8d
0x18001720c  mov     [rsp+1600h+var_15DC], 0
0x180017214  mov     rdx, r12
0x180017217  mov     ecx, 50000005h
0x18001721c  mov     edi, eax
0x18001721e  call    cs:__imp_SHRestricted2W
0x180017224  test    eax, eax
0x180017226  jnz     short loc_180017245
0x180017228  test    edi, edi
0x18001722a  jz      short loc_180017268
0x18001722c  lea     r8, [rsp+1600h+var_15DC]; unsigned int *
0x180017231  xor     edx, edx; enum SUBSCRIPTIONTYPE
0x180017233  mov     rcx, r15; this
0x180017236  call    ?CountSubscriptions@CSubscriptionMgr@@QEAAJW4SUBSCRIPTIONTYPE@@PEAK@Z; CSubscriptionMgr::CountSubscriptions(SUBSCRIPTIONTYPE,ulong *)
0x18001723b  test    eax, eax
0x18001723d  js      short loc_180017268
0x18001723f  cmp     [rsp+1600h+var_15DC], edi
0x180017243  jb      short loc_180017268
0x180017245  test    [rbp+1500h+arg_20], 4
0x18001724c  jnz     short loc_18001725E
0x18001724e  xor     r8d, r8d; unsigned int
0x180017251  mov     edx, 1FBCh; unsigned int
0x180017256  mov     rcx, r13; hWnd
0x180017259  call    ?SGMessageBox@@YAHPEAUHWND__@@II@Z; SGMessageBox(HWND__ *,uint,uint)
0x18001725e  mov     eax, 80070005h
0x180017263  jmp     loc_180017141
0x180017268  xor     edi, edi
0x18001726a  mov     edx, [rbp+1500h+arg_28]; enum SUBSCRIPTIONTYPE
0x180017270  lea     rcx, [rsp+1600h+var_15D0]; struct OOEBuf *
0x180017275  mov     [rsp+1600h+var_15CC], 0
0x18001727e  mov     [rsp+1600h+var_15C4], 0
0x180017287  call    ?GetDefaultOOEBuf@@YAJPEAUOOEBuf@@W4SUBSCRIPTIONTYPE@@@Z; GetDefaultOOEBuf(OOEBuf *,SUBSCRIPTIONTYPE)
0x18001728c  mov     r8, r12; unsigned __int16 *
0x18001728f  lea     rcx, [rbp+1500h+var_13A4]; unsigned __int16 *
0x180017296  mov     edx, 824h; unsigned __int64
0x18001729b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800172a0  lea     rcx, [rbp+1500h+var_13A4]
0x1800172a7  call    IsHTTPPrefixed
0x1800172ac  test    eax, eax
0x1800172ae  jz      loc_18001713C
0x1800172b4  test    rbx, rbx
0x1800172b7  jz      short loc_1800172E4
0x1800172b9  mov     r8, rbx; struct _tagSubscriptionInfo *
0x1800172bc  lea     rdx, [rsp+1600h+var_15D0]; struct OOEBuf *
0x1800172c1  call    ?ChangeSubscriptionValues@CSubscriptionMgr@@IEAAXPEAUOOEBuf@@PEAU_tagSubscriptionInfo@@@Z; CSubscriptionMgr::ChangeSubscriptionValues(OOEBuf *,_tagSubscriptionInfo *)
0x1800172c6  cmp     [rsp+1600h+var_15E0], 0
0x1800172cb  jz      short loc_1800172E4
0x1800172cd  lea     rdx, [rbp+1500h+iid]; lpiid
0x1800172d1  lea     rcx, [rbp+1500h+var_13A4]; unsigned __int16 *
0x1800172d8  call    ?ReadCookieFromInetDB@@YAJPEBGPEAU_GUID@@@Z; ReadCookieFromInetDB(ushort const *,_GUID *)
0x1800172dd  or      [rbp+1500h+var_50], 10h
0x1800172e4  xor     r8d, r8d
0x1800172e7  xor     edx, edx
0x1800172e9  mov     ecx, 50000019h
0x1800172ee  call    cs:__imp_SHRestricted2W
0x1800172f4  test    eax, eax
0x1800172f6  jz      short loc_180017315
0x1800172f8  xor     eax, eax
0x1800172fa  mov     [rsp+1600h+var_1594], 0
0x180017302  and     [rsp+1600h+var_15D0], 0FFFFFE7Fh
0x18001730a  mov     [rbp+1500h+var_1524], ax
0x18001730e  mov     [rbp+1500h+var_1424], ax
0x180017315  mov     r8, r12; unsigned __int16 *
0x180017318  lea     rcx, [rbp+1500h+var_13A4]; unsigned __int16 *
0x18001731f  mov     edx, 824h; unsigned __int64
0x180017324  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180017329  mov     r8, [rsp+1600h+var_15D8]; unsigned __int16 *
0x18001732e  lea     rcx, [rbp+1500h+var_35A]; unsigned __int16 *
0x180017335  mov     edx, 104h; unsigned __int64
0x18001733a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001733f  test    [rbp+1500h+arg_20], 4
0x180017346  jnz     short loc_180017361
0x180017348  mov     edx, [rbp+1500h+arg_28]; enum SUBSCRIPTIONTYPE
0x18001734e  lea     r8, [rsp+1600h+var_15D0]; struct OOEBuf *
0x180017353  mov     rcx, r13; HWND
0x180017356  call    ?CreateWizard@@YAJPEAUHWND__@@W4SUBSCRIPTIONTYPE@@PEAUOOEBuf@@@Z; CreateWizard(HWND__ *,SUBSCRIPTIONTYPE,OOEBuf *)
0x18001735b  mov     edi, eax
0x18001735d  test    eax, eax
0x18001735f  js      short loc_1800173E0
0x180017361  test    [rbp+1500h+arg_20], 8
0x180017368  jnz     short loc_1800173C8
0x18001736a  lea     rbx, [r15+28h]
0x18001736e  mov     rcx, [rbx]; pv
0x180017371  test    rcx, rcx
0x180017374  jz      short loc_1800173A6
0x180017376  call    cs:__imp_CoTaskMemFree
0x18001737c  mov     rcx, [r15+14A0h]
0x180017383  mov     qword ptr [rbx], 0
0x18001738a  test    rcx, rcx
0x18001738d  jz      short loc_1800173A6
0x18001738f  mov     rax, [rcx]
0x180017392  mov     rax, [rax+10h]
0x180017396  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001739b  mov     qword ptr [r15+14A0h], 0
0x1800173a6  mov     rdx, rbx; struct MYPIDL **
0x1800173a9  lea     rcx, [rsp+1600h+var_15D0]; struct OOEBuf *
0x1800173ae  call    ?CreateSubscriptionFromOOEBuf@@YAJPEAUOOEBuf@@PEAPEFAUMYPIDL@@@Z; CreateSubscriptionFromOOEBuf(OOEBuf *,MYPIDL * *)
0x1800173b3  mov     edi, eax
0x1800173b5  test    eax, eax
0x1800173b7  js      short loc_1800173E0
0x1800173b9  mov     rdx, [rbx]; pidl2
0x1800173bc  mov     ecx, 2; wEventId
0x1800173c1  call    _GenerateEvent
0x1800173c6  jmp     short loc_1800173E0
0x1800173c8  test    edi, edi
0x1800173ca  jnz     short loc_1800173E0
0x1800173cc  lea     rdx, [rsp+1600h+var_15D0]; struct OOEBuf *
0x1800173d1  mov     dword ptr [rbx+4], 0EF7Fh
0x1800173d8  mov     rcx, rbx; struct _tagSubscriptionInfo *
0x1800173db  call    ?UpdateSubsInfoFromOOE@@YAXPEAU_tagSubscriptionInfo@@PEAUOOEBuf@@@Z; UpdateSubsInfoFromOOE(_tagSubscriptionInfo *,OOEBuf *)
0x1800173e0  mov     eax, edi
0x1800173e2  jmp     loc_180017141
```
