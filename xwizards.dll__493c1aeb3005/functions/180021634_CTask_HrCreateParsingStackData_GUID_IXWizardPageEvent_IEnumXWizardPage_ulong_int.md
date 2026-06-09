# CTask::HrCreateParsingStackData(_GUID *,IXWizardPageEvent * *,IEnumXWizardPage * *,ulong *,int)

- ea: `0x180021634`
- end: `0x180021b13`
- name: `?HrCreateParsingStackData@CTask@@AEAAJPEAU_GUID@@PEAPEAUIXWizardPageEvent@@PEAPEAUIEnumXWizardPage@@PEAKH@Z`
- size: `1247`
- prototype: `__int64 __fastcall(CTask *__hidden this, struct _GUID *, struct IXWizardPageEvent **, struct IEnumXWizardPage **, unsigned int *, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800207c0`
- `0x180020b3c`

## callees

- `0x18000ae04`
- `0x18000de90`
- `0x18002042c`
- `0x180021634`
- `0x18002336c`
- `0x1800291f8`
- `0x18002c0e0`
- `0x18002ea84`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180021860`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180021860`

## pseudocode

```c
__int64 __fastcall CTask::HrCreateParsingStackData(
        CTask *this,
        struct _GUID *a2,
        LPVOID *a3,
        struct IEnumXWizardPage **a4,
        unsigned int *a5,
        int a6)
{
  LPVOID v6; // r14
  __int64 *v8; // rcx
  struct _XWIZARD_PAGE_DATA *v9; // r15
  struct _GUID *v12; // rsi
  __int64 v13; // rax
  int RecycledPage; // eax
  int v15; // ebx
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  unsigned int *v18; // rax
  struct IXWizardPageEvent *v19; // rcx
  BOOL v20; // r8d
  BOOL v21; // r9d
  PVOID *v22; // rcx
  HRESULT Instance; // eax
  struct IMultiObjectElevationFactory **v24; // r8
  unsigned int *v25; // rax
  struct IEnumXWizardPage *v26; // rcx
  int v28; // [rsp+A0h] [rbp+8h] BYREF
  void *v29; // [rsp+A8h] [rbp+10h]
  struct _XWIZARD_PAGE_DATA *ProcessedPage; // [rsp+B0h] [rbp+18h] BYREF
  __int64 v31; // [rsp+B8h] [rbp+20h]

  v6 = *a3;
  v8 = (__int64 *)*((_QWORD *)this + 38);
  v9 = 0;
  v28 = 0;
  v31 = (__int64)*a4;
  v12 = a2;
  v13 = *v8;
  v29 = v6;
  if ( !a2 )
    a2 = (struct _GUID *)((char *)this + 16);
  RecycledPage = (*(__int64 (__fastcall **)(__int64 *, struct _GUID *, int *, unsigned int *))(v13 + 72))(
                   v8,
                   a2,
                   &v28,
                   a5);
  v15 = RecycledPage;
  if ( RecycledPage < 0 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_85;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v17 = 52;
LABEL_83:
      WPP_SF_d(v16[2], v17, &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids, (unsigned int)RecycledPage);
    }
LABEL_84:
    v6 = v29;
LABEL_85:
    *a5 = 0;
    if ( *a3 && !v6 )
    {
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)*a3 + 16LL))(*a3);
      *a3 = 0;
    }
    if ( *a4 && !v31 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a4 + 16LL))(*a4);
      *a4 = 0;
    }
    goto LABEL_91;
  }
  if ( !v12 )
    goto LABEL_62;
  ProcessedPage = CTask::FindProcessedPage(this, v12);
  v9 = ProcessedPage;
  if ( !ProcessedPage )
  {
    RecycledPage = CTask::HrGetRecycledPage(this, v12, &ProcessedPage, 1);
    v15 = RecycledPage;
    if ( RecycledPage < 0 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_84;
      v17 = 53;
      goto LABEL_83;
    }
    v9 = ProcessedPage;
  }
  if ( v29 )
  {
LABEL_62:
    v25 = a5;
    goto LABEL_63;
  }
  v18 = a5;
  if ( (*(_BYTE *)a5 & 2) == 0 || a6 )
  {
    if ( v9 )
    {
      v19 = (struct IXWizardPageEvent *)*((_QWORD *)v9 + 4);
      if ( v19 )
      {
        *a3 = v19;
        (*(void (__fastcall **)(struct IXWizardPageEvent *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 1);
        goto LABEL_59;
      }
    }
  }
  v20 = (*a5 & 0x1000) != 0 || *((_DWORD *)this + 263);
  v21 = (*a5 & 0x100) != 0 || *((_DWORD *)this + 262);
  if ( (*a5 & 0x2000) != 0 )
    _InterlockedAdd((volatile signed __int32 *)this + 263, 1u);
  if ( (*v18 & 0x200) != 0 )
    _InterlockedAdd((volatile signed __int32 *)this + 262, 1u);
  if ( v28 != 2 )
  {
    if ( v28 != 3 )
    {
      v15 = -2147024809;
      v22 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_84;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_56;
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids, 2147942487LL);
      goto LABEL_55;
    }
    if ( v20 )
    {
      v24 = (struct IMultiObjectElevationFactory **)*((_QWORD *)this + 132);
    }
    else
    {
      if ( !v21 )
      {
        Instance = CoCreateInstance(v12, 0, 0x401u, &IID_IXWizardPageEvent, a3);
LABEL_44:
        v15 = Instance;
        goto LABEL_45;
      }
      v24 = 0;
    }
    Instance = CPXWizardPageProxy::HrCreateInstance(
                 *((HWND *)this + 1),
                 v12,
                 v24,
                 *((struct IPXWizardTypeEvent **)this + 36),
                 (struct IXWizardPageEvent **)a3);
    goto LABEL_44;
  }
  v15 = CWTPage::HrCreateInstance(
          *((HWND *)this + 1),
          v12,
          v20,
          v21,
          *((_DWORD *)this + 29) & 0x80,
          *((struct IMultiObjectElevationFactory ***)this + 132),
          *((struct IPXWizardTypeSource **)this + 37),
          *((struct IPXWizardTypeEvent **)this + 36),
          (struct IXWizardPageEvent **)a3);
  if ( v15 < 0 )
  {
LABEL_45:
    if ( v15 == -2147221164 )
    {
      if ( !(unsigned int)IsComponentModuleNameResolved(v12) )
      {
        v22 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            55,
            &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids,
            2147746132LL);
          v22 = (PVOID *)WPP_GLOBAL_Control;
        }
        v15 = 0;
LABEL_51:
        v25 = a5;
        goto LABEL_64;
      }
      goto LABEL_55;
    }
    if ( v15 < 0 )
    {
LABEL_55:
      v22 = (PVOID *)WPP_GLOBAL_Control;
LABEL_56:
      if ( v22 == &WPP_GLOBAL_Control || (*((_BYTE *)v22 + 28) & 4) == 0 )
      {
LABEL_60:
        if ( v15 < 0 )
          goto LABEL_84;
        goto LABEL_51;
      }
      WPP_SF_d(v22[2], 56, &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids, (unsigned int)v15);
LABEL_59:
      v22 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_60;
    }
    goto LABEL_62;
  }
  v25 = a5;
  *a5 |= 0x20u;
LABEL_63:
  v22 = (PVOID *)WPP_GLOBAL_Control;
LABEL_64:
  if ( !v31 )
  {
    if ( ((*(_BYTE *)v25 & 2) == 0 || a6) && v9 && (v26 = (struct IEnumXWizardPage *)*((_QWORD *)v9 + 3)) != 0 )
    {
      *a4 = v26;
      (*(void (__fastcall **)(struct IEnumXWizardPage *))(*(_QWORD *)v26 + 8LL))(v26);
      if ( v15 < 0 )
        goto LABEL_84;
    }
    else
    {
      if ( (*(_BYTE *)v25 & 0x20) == 0 || !v12 )
      {
        if ( !v12 )
          v12 = (struct _GUID *)((char *)this + 16);
        RecycledPage = (*(__int64 (__fastcall **)(_QWORD, struct _GUID *, _QWORD, struct IEnumXWizardPage **))(**((_QWORD **)this + 31) + 152LL))(
                         *((_QWORD *)this + 31),
                         v12,
                         0,
                         a4);
        v15 = RecycledPage;
        if ( RecycledPage >= 0 )
          goto LABEL_91;
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          goto LABEL_84;
        v17 = 58;
        goto LABEL_83;
      }
      RecycledPage = CPEnumXWizardControlPage::HrCreateInstance(0, (const struct IXWizardPageEvent *)*a3, a4);
      v15 = RecycledPage;
      if ( RecycledPage < 0 )
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          goto LABEL_84;
        v17 = 57;
        goto LABEL_83;
      }
    }
LABEL_91:
    v22 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v22 != &WPP_GLOBAL_Control && (*((_BYTE *)v22 + 28) & 0x10) != 0 )
    WPP_SF_d(v22[2], 59, &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids, (unsigned int)v15);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180021634  mov     rax, rsp
0x180021637  push    rbx
0x180021638  push    rbp
0x180021639  push    rsi
0x18002163a  push    rdi
0x18002163b  push    r12
0x18002163d  push    r13
0x18002163f  push    r14
0x180021641  push    r15
0x180021643  sub     rsp, 58h
0x180021647  mov     r14, [r8]
0x18002164a  mov     rdi, rcx
0x18002164d  mov     rcx, [rcx+130h]
0x180021654  xor     r15d, r15d
0x180021657  mov     dword ptr [rax+8], 0
0x18002165e  mov     r13, r9
0x180021661  mov     rax, [r9]
0x180021664  mov     r12, r8
0x180021667  mov     [rsp+98h+arg_18], rax
0x18002166f  mov     rsi, rdx
0x180021672  mov     rax, [rcx]
0x180021675  mov     [rsp+98h+arg_8], r14
0x18002167d  test    rdx, rdx
0x180021680  jnz     short loc_180021686
0x180021682  lea     rdx, [rdi+10h]
0x180021686  mov     r9, [rsp+98h+arg_20]
0x18002168e  lea     r8, [rsp+98h+arg_0]
0x180021696  mov     rax, [rax+48h]
0x18002169a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002169f  mov     ebx, eax
0x1800216a1  test    eax, eax
0x1800216a3  jns     short loc_1800216D3
0x1800216a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800216ac  lea     rbp, WPP_GLOBAL_Control
0x1800216b3  cmp     rcx, rbp
0x1800216b6  jz      loc_180021A82
0x1800216bc  mov     r14b, 4
0x1800216bf  test    [rcx+1Ch], r14b
0x1800216c3  jz      loc_180021A7A
0x1800216c9  mov     edx, 34h ; '4'
0x1800216ce  jmp     loc_180021A67
0x1800216d3  lea     rbp, WPP_GLOBAL_Control
0x1800216da  mov     r14b, 4
0x1800216dd  test    rsi, rsi
0x1800216e0  jz      loc_18002198B
0x1800216e6  mov     rdx, rsi; struct _GUID *
0x1800216e9  mov     rcx, rdi; this
0x1800216ec  call    ?FindProcessedPage@CTask@@AEAAPEAU_XWIZARD_PAGE_DATA@@PEAU_GUID@@@Z; CTask::FindProcessedPage(_GUID *)
0x1800216f1  mov     [rsp+98h+arg_10], rax
0x1800216f9  mov     r15, rax
0x1800216fc  mov     edx, 1
0x180021701  test    rax, rax
0x180021704  jnz     short loc_180021752
0x180021706  mov     r9d, edx; int
0x180021709  lea     r8, [rsp+98h+arg_10]; struct _XWIZARD_PAGE_DATA **
0x180021711  mov     rdx, rsi; struct _GUID *
0x180021714  mov     rcx, rdi; this
0x180021717  call    ?HrGetRecycledPage@CTask@@AEAAJPEAU_GUID@@PEAPEAU_XWIZARD_PAGE_DATA@@H@Z; CTask::HrGetRecycledPage(_GUID *,_XWIZARD_PAGE_DATA * *,int)
0x18002171c  mov     ebx, eax
0x18002171e  test    eax, eax
0x180021720  jns     short loc_180021745
0x180021722  mov     rcx, cs:WPP_GLOBAL_Control
0x180021729  cmp     rcx, rbp
0x18002172c  jz      loc_180021A7A
0x180021732  test    [rcx+1Ch], r14b
0x180021736  jz      loc_180021A7A
0x18002173c  lea     edx, [r15+35h]
0x180021740  jmp     loc_180021A67
0x180021745  mov     r15, [rsp+98h+arg_10]
0x18002174d  mov     edx, 1
0x180021752  cmp     [rsp+98h+arg_8], 0
0x18002175b  jnz     loc_18002198B
0x180021761  mov     rax, [rsp+98h+arg_20]
0x180021769  test    byte ptr [rax], 2
0x18002176c  jz      short loc_180021778
0x18002176e  cmp     [rsp+98h+arg_28], 0
0x180021776  jz      short loc_18002179B
0x180021778  test    r15, r15
0x18002177b  jz      short loc_18002179B
0x18002177d  mov     rcx, [r15+20h]
0x180021781  test    rcx, rcx
0x180021784  jz      short loc_18002179B
0x180021786  mov     [r12], rcx
0x18002178a  mov     rax, [rcx]
0x18002178d  mov     rax, [rax+8]
0x180021791  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021796  jmp     loc_180021977
0x18002179b  test    dword ptr [rax], 1000h
0x1800217a1  jnz     short loc_1800217B1
0x1800217a3  cmp     dword ptr [rdi+41Ch], 0
0x1800217aa  jnz     short loc_1800217B1
0x1800217ac  xor     r8d, r8d
0x1800217af  jmp     short loc_1800217B4
0x1800217b1  mov     r8d, edx; int
0x1800217b4  test    dword ptr [rax], 100h
0x1800217ba  jnz     short loc_1800217CA
0x1800217bc  cmp     dword ptr [rdi+418h], 0
0x1800217c3  jnz     short loc_1800217CA
0x1800217c5  xor     r9d, r9d
0x1800217c8  jmp     short loc_1800217CD
0x1800217ca  mov     r9d, edx; int
0x1800217cd  test    dword ptr [rax], 2000h
0x1800217d3  jz      short loc_1800217DC
0x1800217d5  lock add [rdi+41Ch], edx
0x1800217dc  test    dword ptr [rax], 200h
0x1800217e2  jz      short loc_1800217EB
0x1800217e4  lock add [rdi+418h], edx
0x1800217eb  mov     ecx, [rsp+98h+arg_0]
0x1800217f2  sub     ecx, 2
0x1800217f5  jz      loc_1800218F0
0x1800217fb  cmp     ecx, 1
0x1800217fe  jz      short loc_18002183F
0x180021800  mov     ebx, 80070057h
0x180021805  mov     rcx, cs:WPP_GLOBAL_Control
0x18002180c  cmp     rcx, rbp
0x18002180f  jz      loc_180021A7A
0x180021815  test    [rcx+1Ch], r14b
0x180021819  jz      loc_180021954
0x18002181f  mov     rcx, [rcx+10h]
0x180021823  lea     r8, WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids
0x18002182a  mov     edx, 36h ; '6'
0x18002182f  mov     r9d, 80070057h
0x180021835  call    WPP_SF_d
0x18002183a  jmp     loc_18002194D
0x18002183f  test    r8d, r8d
0x180021842  jnz     short loc_18002186D
0x180021844  test    r9d, r9d
0x180021847  jnz     short loc_180021868
0x180021849  lea     r9, IID_IXWizardPageEvent; riid
0x180021850  mov     [rsp+98h+ppv], r12; ppv
0x180021855  xor     edx, edx; pUnkOuter
0x180021857  mov     r8d, 401h; dwClsContext
0x18002185d  mov     rcx, rsi; rclsid
0x180021860  call    cs:__imp_CoCreateInstance
0x180021866  jmp     short loc_180021891
0x180021868  test    r8d, r8d
0x18002186b  jz      short loc_180021876
0x18002186d  mov     r8, [rdi+420h]
0x180021874  jmp     short loc_180021879
0x180021876  xor     r8d, r8d; struct IMultiObjectElevationFactory **
0x180021879  mov     r9, [rdi+120h]; struct IPXWizardTypeEvent *
0x180021880  mov     rdx, rsi; struct _GUID *
0x180021883  mov     rcx, [rdi+8]; HWND
0x180021887  mov     [rsp+98h+ppv], r12; struct IXWizardPageEvent **
0x18002188c  call    ?HrCreateInstance@CPXWizardPageProxy@@SAJPEAUHWND__@@PEAU_GUID@@PEAPEAUIMultiObjectElevationFactory@@PEAUIPXWizardTypeEvent@@PEAPEAUIXWizardPageEvent@@@Z; CPXWizardPageProxy::HrCreateInstance(HWND__ *,_GUID *,IMultiObjectElevationFactory * *,IPXWizardTypeEvent *,IXWizardPageEvent * *)
0x180021891  mov     ebx, eax
0x180021893  cmp     ebx, 80040154h
0x180021899  jnz     loc_180021949
0x18002189f  mov     rcx, rsi; struct _GUID *
0x1800218a2  call    ?IsComponentModuleNameResolved@@YAHPEBU_GUID@@@Z; IsComponentModuleNameResolved(_GUID const *)
0x1800218a7  test    eax, eax
0x1800218a9  jnz     loc_18002194D
0x1800218af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800218b6  cmp     rcx, rbp
0x1800218b9  jz      short loc_1800218E1
0x1800218bb  test    byte ptr [rcx+1Ch], 8
0x1800218bf  jz      short loc_1800218E1
0x1800218c1  mov     rcx, [rcx+10h]
0x1800218c5  lea     edx, [rax+37h]
0x1800218c8  mov     r9d, 80040154h
0x1800218ce  lea     r8, WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids
0x1800218d5  call    WPP_SF_d
0x1800218da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800218e1  xor     ebx, ebx
0x1800218e3  mov     rax, [rsp+98h+arg_20]
0x1800218eb  jmp     loc_18002199A
0x1800218f0  mov     rax, [rdi+120h]
0x1800218f7  mov     rdx, rsi; struct _GUID *
0x1800218fa  mov     ecx, [rdi+74h]
0x1800218fd  mov     [rsp+98h+var_58], r12; struct IXWizardPageEvent **
0x180021902  and     ecx, 80h
0x180021908  mov     [rsp+98h+var_60], rax; struct IPXWizardTypeEvent *
0x18002190d  mov     rax, [rdi+128h]
0x180021914  mov     [rsp+98h+var_68], rax; struct IPXWizardTypeSource *
0x180021919  mov     rax, [rdi+420h]
0x180021920  mov     [rsp+98h+var_70], rax; struct IMultiObjectElevationFactory **
0x180021925  mov     dword ptr [rsp+98h+ppv], ecx; int
0x180021929  mov     rcx, [rdi+8]; HWND
0x18002192d  call    ?HrCreateInstance@CWTPage@@SAJPEAUHWND__@@PEBU_GUID@@HHHPEAPEAUIMultiObjectElevationFactory@@PEAUIPXWizardTypeSource@@PEAUIPXWizardTypeEvent@@PEAPEAUIXWizardPageEvent@@@Z; CWTPage::HrCreateInstance(HWND__ *,_GUID const *,int,int,int,IMultiObjectElevationFactory * *,IPXWizardTypeSource *,IPXWizardTypeEvent *,IXWizardPageEvent * *)
0x180021932  mov     ebx, eax
0x180021934  test    eax, eax
0x180021936  js      loc_180021893
0x18002193c  mov     rax, [rsp+98h+arg_20]
0x180021944  or      dword ptr [rax], 20h
0x180021947  jmp     short loc_180021993
0x180021949  test    ebx, ebx
0x18002194b  jns     short loc_18002198B
0x18002194d  mov     rcx, cs:WPP_GLOBAL_Control
0x180021954  cmp     rcx, rbp
0x180021957  jz      short loc_18002197E
0x180021959  test    [rcx+1Ch], r14b
0x18002195d  jz      short loc_18002197E
0x18002195f  mov     rcx, [rcx+10h]
0x180021963  lea     r8, WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids
0x18002196a  mov     edx, 38h ; '8'
0x18002196f  mov     r9d, ebx
0x180021972  call    WPP_SF_d
0x180021977  mov     rcx, cs:WPP_GLOBAL_Control
0x18002197e  test    ebx, ebx
0x180021980  js      loc_180021A7A
0x180021986  jmp     loc_1800218E3
0x18002198b  mov     rax, [rsp+98h+arg_20]
0x180021993  mov     rcx, cs:WPP_GLOBAL_Control
0x18002199a  cmp     [rsp+98h+arg_18], 0
0x1800219a3  jnz     loc_180021ADD
0x1800219a9  test    byte ptr [rax], 2
0x1800219ac  jz      short loc_1800219B8
0x1800219ae  cmp     [rsp+98h+arg_28], 0
0x1800219b6  jz      short loc_1800219E3
0x1800219b8  test    r15, r15
0x1800219bb  jz      short loc_1800219E3
0x1800219bd  mov     rcx, [r15+18h]
0x1800219c1  test    rcx, rcx
0x1800219c4  jz      short loc_1800219E3
0x1800219c6  mov     [r13+0], rcx
0x1800219ca  mov     rax, [rcx]
0x1800219cd  mov     rax, [rax+8]
0x1800219d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800219d6  test    ebx, ebx
0x1800219d8  jns     loc_180021AD6
0x1800219de  jmp     loc_180021A7A
0x1800219e3  test    byte ptr [rax], 20h
0x1800219e6  jz      short loc_180021A1E
0x1800219e8  test    rsi, rsi
0x1800219eb  jz      short loc_180021A1E
0x1800219ed  mov     rdx, [r12]; struct IXWizardPageEvent *
0x1800219f1  mov     r8, r13; struct IEnumXWizardPage **
0x1800219f4  xor     ecx, ecx; struct IXWizardTaskEvent *
0x1800219f6  call    ?HrCreateInstance@CPEnumXWizardControlPage@@SAJPEBUIXWizardTaskEvent@@PEBUIXWizardPageEvent@@PEAPEAUIEnumXWizardPage@@@Z; CPEnumXWizardControlPage::HrCreateInstance(IXWizardTaskEvent const *,IXWizardPageEvent const *,IEnumXWizardPage * *)
0x1800219fb  mov     ebx, eax
0x1800219fd  test    eax, eax
0x1800219ff  jns     loc_180021AD6
0x180021a05  mov     rcx, cs:WPP_GLOBAL_Control
0x180021a0c  cmp     rcx, rbp
0x180021a0f  jz      short loc_180021A7A
0x180021a11  test    [rcx+1Ch], r14b
0x180021a15  jz      short loc_180021A7A
0x180021a17  mov     edx, 39h ; '9'
0x180021a1c  jmp     short loc_180021A67
0x180021a1e  mov     rcx, [rdi+0F8h]
0x180021a25  mov     rax, [rcx]
0x180021a28  test    rsi, rsi
0x180021a2b  jnz     short loc_180021A31
0x180021a2d  lea     rsi, [rdi+10h]
0x180021a31  mov     rax, [rax+98h]
0x180021a38  mov     r9, r13
0x180021a3b  xor     r8d, r8d
0x180021a3e  mov     rdx, rsi
0x180021a41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021a46  mov     ebx, eax
0x180021a48  test    eax, eax
0x180021a4a  jns     loc_180021AD6
0x180021a50  mov     rcx, cs:WPP_GLOBAL_Control
0x180021a57  cmp     rcx, rbp
0x180021a5a  jz      short loc_180021A7A
0x180021a5c  test    [rcx+1Ch], r14b
0x180021a60  jz      short loc_180021A7A
0x180021a62  mov     edx, 3Ah ; ':'
0x180021a67  mov     rcx, [rcx+10h]
0x180021a6b  lea     r8, WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids
0x180021a72  mov     r9d, eax
0x180021a75  call    WPP_SF_d
0x180021a7a  mov     r14, [rsp+98h+arg_8]
0x180021a82  mov     rax, [rsp+98h+arg_20]
0x180021a8a  mov     dword ptr [rax], 0
0x180021a90  mov     rcx, [r12]
0x180021a94  test    rcx, rcx
0x180021a97  jz      short loc_180021AAE
0x180021a99  test    r14, r14
0x180021a9c  jnz     short loc_180021AAE
0x180021a9e  mov     rax, [rcx]
0x180021aa1  mov     rax, [rax+10h]
0x180021aa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021aaa  mov     [r12], r14
0x180021aae  mov     rcx, [r13+0]
0x180021ab2  test    rcx, rcx
0x180021ab5  jz      short loc_180021AD6
0x180021ab7  cmp     [rsp+98h+arg_18], 0
0x180021ac0  jnz     short loc_180021AD6
0x180021ac2  mov     rax, [rcx]
0x180021ac5  mov     rax, [rax+10h]
0x180021ac9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ace  mov     qword ptr [r13+0], 0
0x180021ad6  mov     rcx, cs:WPP_GLOBAL_Control
0x180021add  cmp     rcx, rbp
0x180021ae0  jz      short loc_180021B00
0x180021ae2  test    byte ptr [rcx+1Ch], 10h
0x180021ae6  jz      short loc_180021B00
0x180021ae8  mov     rcx, [rcx+10h]
0x180021aec  lea     r8, WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids
0x180021af3  mov     edx, 3Bh ; ';'
0x180021af8  mov     r9d, ebx
0x180021afb  call    WPP_SF_d
0x180021b00  mov     eax, ebx
0x180021b02  add     rsp, 58h
0x180021b06  pop     r15
0x180021b08  pop     r14
0x180021b0a  pop     r13
0x180021b0c  pop     r12
0x180021b0e  pop     rdi
  ... truncated ...
```
