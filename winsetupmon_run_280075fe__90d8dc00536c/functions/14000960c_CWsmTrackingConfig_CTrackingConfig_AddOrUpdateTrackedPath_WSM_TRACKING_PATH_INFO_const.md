# CWsmTrackingConfig::CTrackingConfig::AddOrUpdateTrackedPath(_WSM_TRACKING_PATH_INFO * const)

- ea: `0x14000960c`
- end: `0x1400099cd`
- name: `?AddOrUpdateTrackedPath@CTrackingConfig@CWsmTrackingConfig@@QEAAJQEAU_WSM_TRACKING_PATH_INFO@@@Z`
- size: `961`
- prototype: `int(CWsmTrackingConfig::CTrackingConfig *__hidden this, struct _WSM_TRACKING_PATH_INFO *const)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x1400099e0`

## callees

- `0x140008bb0`
- `0x1400091cc`
- `0x14000960c`
- `0x14000a8c4`
- `0x14000c410`
- `0x14000d0a8`
- `0x14000d21c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000970a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009748`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009799`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000982f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000986d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400098ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400098d0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400098e1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009971`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009995`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400099a6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000970a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009748`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009799`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000982f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000986d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400098ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400098d0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400098e1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009971`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009995`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400099a6`
- `ntoskrnl!_wcsicmp` at `0x1400096ad`
- `ntoskrnl!_wcsicmp` at `0x1400096ad`

## pseudocode

```c
__int64 __fastcall CWsmTrackingConfig::CTrackingConfig::AddOrUpdateTrackedPath(
        CWsmTrackingConfig::CTrackingConfig *this,
        struct _WSM_TRACKING_PATH_INFO *const a2)
{
  struct _WSM_TRACKING_PATH_INFO *v2; // r12
  const WCHAR *v3; // rdx
  int v5; // eax
  CWsmTrackingConfig::CTrackingPathInfo **v6; // rbx
  int Instance; // esi
  CWsmTrackingConfig::CTrackingPathInfo *v8; // rcx
  bool v9; // zf
  __int64 v10; // r15
  const wchar_t *v11; // rdx
  struct CWsmTrackingConfig::CTrackingPathInfo **v12; // rax
  CWsmTrackingConfig::CTrackingPathInfo *v13; // r12
  __int64 v14; // rax
  PVOID v15; // rdx
  CWsmTrackingConfig::CTrackingPathInfo *v16; // r12
  __int64 v17; // rcx
  __int64 v18; // rax
  __int128 v19; // xmm0
  __int64 v20; // xmm1_8
  __int64 v21; // rcx
  char v22; // al
  PVOID v23; // r12
  struct CWsmTrackingConfig::CTrackingPathInfo **v24; // rax
  CWsmTrackingConfig::CTrackingPathInfo *v25; // r15
  __int64 v26; // rdx
  PVOID v27; // rax
  CWsmTrackingConfig::CTrackingPathInfo *v28; // r15
  __int64 *v29; // r15
  PVOID v30; // rsi
  CWsmTrackingConfig::CTrackingPathInfo *v31; // rcx
  CWsmTrackingConfig::CTrackingPathInfo *v33; // r14
  __int64 v34; // r8
  unsigned __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rax
  __int128 v38; // xmm0
  __int64 v39; // xmm1_8
  __int64 v40; // rcx
  void **v41; // [rsp+20h] [rbp-20h] BYREF
  PVOID v42; // [rsp+28h] [rbp-18h]
  PVOID v44; // [rsp+90h] [rbp+50h] BYREF
  PVOID P; // [rsp+98h] [rbp+58h] BYREF

  v2 = a2;
  v42 = 0;
  v3 = *(const WCHAR **)a2;
  v41 = &wsm_stable_path::`vftable';
  v5 = wsm_stable_path::assign((wsm_stable_path *)&v41, v3);
  v6 = (CWsmTrackingConfig::CTrackingPathInfo **)v42;
  Instance = v5;
  if ( v5 < 0 )
  {
    if ( !v42 )
      return (unsigned int)Instance;
    v8 = *(CWsmTrackingConfig::CTrackingPathInfo **)v42;
    v9 = *(_QWORD *)v42 == (_QWORD)v42 + 16;
LABEL_46:
    if ( !v9 )
    {
      if ( v8 )
        ExFreePoolWithTag(v8, 0x6E6D7377u);
    }
    ExFreePoolWithTag(v6, 0x6E6D7377u);
    return (unsigned int)Instance;
  }
  v10 = 0;
  LOBYTE(v44) = 0;
  if ( *((_DWORD *)this + 26) )
  {
    do
    {
      if ( v6 )
        v11 = (const wchar_t *)*v6;
      else
        v11 = 0;
      if ( _wcsicmp(*(const wchar_t **)(*((_QWORD *)this + 14) + 8 * ((unsigned int)v10 + 2 * v10)), v11) )
      {
        v22 = (char)v44;
      }
      else
      {
        P = 0;
        v12 = (struct CWsmTrackingConfig::CTrackingPathInfo **)utl::out_ptr<void,utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>,>(
                                                                 &v41,
                                                                 &P);
        Instance = CWsmTrackingConfig::CTrackingPathInfo::CreateInstance(v2, 0, v12);
        if ( v41 )
        {
          v13 = *(CWsmTrackingConfig::CTrackingPathInfo **)v42;
          *(_QWORD *)v42 = v41;
          if ( v13 )
          {
            CWsmTrackingConfig::CTrackingPathInfo::~CTrackingPathInfo(v13);
            ExFreePoolWithTag(v13, 0x6E6D7377u);
          }
        }
        if ( Instance < 0 )
        {
          v33 = (CWsmTrackingConfig::CTrackingPathInfo *)P;
          goto LABEL_42;
        }
        v14 = *((_QWORD *)this + 1);
        v15 = P;
        P = 0;
        v16 = *(CWsmTrackingConfig::CTrackingPathInfo **)(v14 + 8 * v10);
        *(_QWORD *)(v14 + 8 * v10) = v15;
        if ( v16 )
        {
          CWsmTrackingConfig::CTrackingPathInfo::~CTrackingPathInfo(v16);
          ExFreePoolWithTag(v16, 0x6E6D7377u);
        }
        v17 = *(_QWORD *)(*((_QWORD *)this + 1) + 8 * v10);
        v18 = *((_QWORD *)this + 4);
        v19 = *(_OWORD *)(v17 + 72);
        v20 = *(_QWORD *)(v17 + 88);
        v21 = (unsigned int)v10 + 2 * v10;
        *(_OWORD *)(v18 + 8 * v21) = v19;
        *(_QWORD *)(v18 + 8 * v21 + 16) = v20;
        v22 = 1;
        v23 = P;
        LOBYTE(v44) = 1;
        if ( P )
        {
          CWsmTrackingConfig::CTrackingPathInfo::~CTrackingPathInfo((CWsmTrackingConfig::CTrackingPathInfo *)P);
          ExFreePoolWithTag(v23, 0x6E6D7377u);
          v22 = (char)v44;
        }
        v2 = a2;
      }
      v10 = (unsigned int)(v10 + 1);
    }
    while ( (unsigned int)v10 < *((_DWORD *)this + 26) );
    if ( v22 )
      goto LABEL_44;
  }
  if ( (unsigned __int8)utl::vector<utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>,utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>>>::resize(
                          (char *)this + 8,
                          ((__int64)(*((_QWORD *)this + 2) - *((_QWORD *)this + 1)) >> 3) + 1) )
  {
    v44 = 0;
    v24 = (struct CWsmTrackingConfig::CTrackingPathInfo **)utl::out_ptr<void,utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>,>(
                                                             &v41,
                                                             &v44);
    Instance = CWsmTrackingConfig::CTrackingPathInfo::CreateInstance(a2, 0, v24);
    if ( v41 )
    {
      v25 = *(CWsmTrackingConfig::CTrackingPathInfo **)v42;
      *(_QWORD *)v42 = v41;
      if ( v25 )
      {
        CWsmTrackingConfig::CTrackingPathInfo::~CTrackingPathInfo(v25);
        ExFreePoolWithTag(v25, 0x6E6D7377u);
      }
    }
    if ( Instance >= 0 )
    {
      v26 = *((_QWORD *)this + 2);
      v27 = v44;
      v44 = 0;
      v28 = *(CWsmTrackingConfig::CTrackingPathInfo **)(v26 - 8);
      *(_QWORD *)(v26 - 8) = v27;
      if ( v28 )
      {
        CWsmTrackingConfig::CTrackingPathInfo::~CTrackingPathInfo(v28);
        ExFreePoolWithTag(v28, 0x6E6D7377u);
      }
      v29 = (__int64 *)((char *)this + 32);
      if ( !(unsigned __int8)utl::vector<_WSM_TRACKING_PATH_INFO,utl::allocator<_WSM_TRACKING_PATH_INFO>>::resize(
                               (char *)this + 32,
                               (__int64)(*((_QWORD *)this + 2) - *((_QWORD *)this + 1)) >> 3) )
      {
        v30 = v44;
        if ( v44 )
        {
          CWsmTrackingConfig::CTrackingPathInfo::~CTrackingPathInfo((CWsmTrackingConfig::CTrackingPathInfo *)v44);
          ExFreePoolWithTag(v30, 0x6E6D7377u);
        }
        goto LABEL_30;
      }
      v34 = 0;
      v35 = 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)this + 5) - *((_QWORD *)this + 4)) >> 3);
      *((_DWORD *)this + 26) = v35;
      if ( (_DWORD)v35 )
      {
        do
        {
          v36 = *(_QWORD *)(*((_QWORD *)this + 1) + 8 * v34);
          v37 = *v29;
          v38 = *(_OWORD *)(v36 + 72);
          v39 = *(_QWORD *)(v36 + 88);
          v40 = 3 * v34;
          *(_OWORD *)(v37 + 8 * v40) = v38;
          v34 = (unsigned int)(v34 + 1);
          *(_QWORD *)(v37 + 8 * v40 + 16) = v39;
        }
        while ( (unsigned int)v34 < *((_DWORD *)this + 26) );
      }
      *((_QWORD *)this + 14) = *v29;
    }
    v33 = (CWsmTrackingConfig::CTrackingPathInfo *)v44;
LABEL_42:
    if ( v33 )
    {
      CWsmTrackingConfig::CTrackingPathInfo::~CTrackingPathInfo(v33);
      ExFreePoolWithTag(v33, 0x6E6D7377u);
    }
LABEL_44:
    if ( !v6 )
      return (unsigned int)Instance;
    v8 = *v6;
    v9 = *v6 == (CWsmTrackingConfig::CTrackingPathInfo *)(v6 + 2);
    goto LABEL_46;
  }
LABEL_30:
  if ( v6 )
  {
    v31 = *v6;
    if ( *v6 != (CWsmTrackingConfig::CTrackingPathInfo *)(v6 + 2) && v31 )
      ExFreePoolWithTag(v31, 0x6E6D7377u);
    ExFreePoolWithTag(v6, 0x6E6D7377u);
  }
  return 3221225626LL;
}

```

## disassembly

```asm
0x14000960c  mov     [rsp-38h+arg_0], rbx
0x140009611  mov     [rsp-38h+arg_8], rdx
0x140009616  push    rbp
0x140009617  push    rsi
0x140009618  push    rdi
0x140009619  push    r12
0x14000961b  push    r13
0x14000961d  push    r14
0x14000961f  push    r15
0x140009621  mov     rbp, rsp
0x140009624  sub     rsp, 40h
0x140009628  mov     r12, rdx
0x14000962b  mov     [rbp+var_18], 0
0x140009633  mov     rdx, [rdx]; SourceString
0x140009636  lea     rax, ??_7wsm_stable_path@@6B@; const wsm_stable_path::`vftable'
0x14000963d  mov     r14, rcx
0x140009640  mov     [rbp+var_20], rax
0x140009644  lea     rcx, [rbp+var_20]; this
0x140009648  call    ?assign@wsm_stable_path@@UEAAJPEBG@Z; wsm_stable_path::assign(ushort const *)
0x14000964d  mov     rbx, [rbp+var_18]
0x140009651  mov     esi, eax
0x140009653  test    eax, eax
0x140009655  jns     short loc_140009674
0x140009657  test    rbx, rbx
0x14000965a  jz      loc_1400099B2
0x140009660  mov     rcx, [rbx]
0x140009663  lea     r8, [rbx+10h]
0x140009667  cmp     rcx, r8
0x14000966a  mov     edi, 6E6D7377h
0x14000966f  jmp     loc_14000998C
0x140009674  xor     al, al
0x140009676  xor     r15d, r15d
0x140009679  mov     edi, 6E6D7377h
0x14000967e  mov     byte ptr [rbp+arg_10], al
0x140009681  cmp     [r14+68h], r15d
0x140009685  jbe     loc_1400097C1
0x14000968b  test    rbx, rbx
0x14000968e  jz      short loc_140009695
0x140009690  mov     rdx, [rbx]
0x140009693  jmp     short loc_140009697
0x140009695  xor     edx, edx; Str2
0x140009697  mov     rcx, [r14+70h]
0x14000969b  lea     rax, ds:0[r15*2]
0x1400096a3  mov     r13d, r15d
0x1400096a6  add     rax, r13
0x1400096a9  mov     rcx, [rcx+rax*8]; Str1
0x1400096ad  call    cs:__imp__wcsicmp
0x1400096b4  nop     dword ptr [rax+rax+00h]
0x1400096b9  test    eax, eax
0x1400096bb  jnz     loc_1400098F7
0x1400096c1  lea     rdx, [rbp+P]
0x1400096c5  mov     [rbp+P], 0
0x1400096cd  lea     rcx, [rbp+var_20]
0x1400096d1  call    ??$out_ptr@XV?$unique_ptr@VCTrackingPathInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingPathInfo@CWsmTrackingConfig@@@utl@@@utl@@$$V@utl@@YA?A_PAEAV?$unique_ptr@VCTrackingPathInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingPathInfo@CWsmTrackingConfig@@@utl@@@0@@Z
0x1400096d6  mov     r8, rax; struct CWsmTrackingConfig::CTrackingPathInfo **
0x1400096d9  xor     edx, edx; bool
0x1400096db  mov     rcx, r12; struct _WSM_TRACKING_PATH_INFO *
0x1400096de  call    ?CreateInstance@CTrackingPathInfo@CWsmTrackingConfig@@SAJQEAU_WSM_TRACKING_PATH_INFO@@_NPEAPEAV12@@Z; CWsmTrackingConfig::CTrackingPathInfo::CreateInstance(_WSM_TRACKING_PATH_INFO * const,bool,CWsmTrackingConfig::CTrackingPathInfo * *)
0x1400096e3  mov     rcx, [rbp+var_20]
0x1400096e7  mov     esi, eax
0x1400096e9  test    rcx, rcx
0x1400096ec  jz      short loc_140009716
0x1400096ee  mov     rax, [rbp+var_18]
0x1400096f2  mov     r12, [rax]
0x1400096f5  mov     [rax], rcx
0x1400096f8  test    r12, r12
0x1400096fb  jz      short loc_140009716
0x1400096fd  mov     rcx, r12; this
0x140009700  call    ??1CTrackingPathInfo@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingPathInfo::~CTrackingPathInfo(void)
0x140009705  mov     edx, edi; Tag
0x140009707  mov     rcx, r12; P
0x14000970a  call    cs:__imp_ExFreePoolWithTag
0x140009711  nop     dword ptr [rax+rax+00h]
0x140009716  test    esi, esi
0x140009718  js      loc_1400098FF
0x14000971e  mov     rax, [r14+8]
0x140009722  mov     rdx, [rbp+P]
0x140009726  mov     [rbp+P], 0
0x14000972e  mov     r12, [rax+r15*8]
0x140009732  mov     [rax+r15*8], rdx
0x140009736  test    r12, r12
0x140009739  jz      short loc_140009754
0x14000973b  mov     rcx, r12; this
0x14000973e  call    ??1CTrackingPathInfo@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingPathInfo::~CTrackingPathInfo(void)
0x140009743  mov     edx, edi; Tag
0x140009745  mov     rcx, r12; P
0x140009748  call    cs:__imp_ExFreePoolWithTag
0x14000974f  nop     dword ptr [rax+rax+00h]
0x140009754  mov     rax, [r14+8]
0x140009758  mov     rcx, [rax+r15*8]
0x14000975c  mov     rax, [r14+20h]
0x140009760  movups  xmm0, xmmword ptr [rcx+48h]
0x140009764  movsd   xmm1, qword ptr [rcx+58h]
0x140009769  lea     rcx, ds:0[r15*2]
0x140009771  add     rcx, r13
0x140009774  movups  xmmword ptr [rax+rcx*8], xmm0
0x140009778  movsd   qword ptr [rax+rcx*8+10h], xmm1
0x14000977e  mov     al, 1
0x140009780  mov     r12, [rbp+P]
0x140009784  mov     byte ptr [rbp+arg_10], al
0x140009787  test    r12, r12
0x14000978a  jz      short loc_1400097A8
0x14000978c  mov     rcx, r12; this
0x14000978f  call    ??1CTrackingPathInfo@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingPathInfo::~CTrackingPathInfo(void)
0x140009794  mov     edx, edi; Tag
0x140009796  mov     rcx, r12; P
0x140009799  call    cs:__imp_ExFreePoolWithTag
0x1400097a0  nop     dword ptr [rax+rax+00h]
0x1400097a5  mov     al, byte ptr [rbp+arg_10]
0x1400097a8  mov     r12, [rbp+arg_8]
0x1400097ac  inc     r15d
0x1400097af  cmp     r15d, [r14+68h]
0x1400097b3  jb      loc_14000968B
0x1400097b9  test    al, al
0x1400097bb  jnz     loc_14000997D
0x1400097c1  lea     r12, [r14+8]
0x1400097c5  mov     rdx, [r12+8]
0x1400097ca  mov     rcx, r12
0x1400097cd  sub     rdx, [r12]
0x1400097d1  sar     rdx, 3
0x1400097d5  inc     rdx
0x1400097d8  call    ?resize@?$vector@V?$unique_ptr@VCTrackingPathInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingPathInfo@CWsmTrackingConfig@@@utl@@@utl@@V?$allocator@V?$unique_ptr@VCTrackingPathInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingPathInfo@CWsmTrackingConfig@@@utl@@@utl@@@2@@utl@@QEAA_N_K@Z; utl::vector<utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>,utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>>>::resize(unsigned __int64)
0x1400097dd  test    al, al
0x1400097df  jz      loc_1400098B8
0x1400097e5  lea     rdx, [rbp+arg_10]
0x1400097e9  mov     [rbp+arg_10], 0
0x1400097f1  lea     rcx, [rbp+var_20]
0x1400097f5  call    ??$out_ptr@XV?$unique_ptr@VCTrackingPathInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingPathInfo@CWsmTrackingConfig@@@utl@@@utl@@$$V@utl@@YA?A_PAEAV?$unique_ptr@VCTrackingPathInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingPathInfo@CWsmTrackingConfig@@@utl@@@0@@Z
0x1400097fa  mov     rcx, [rbp+arg_8]; struct _WSM_TRACKING_PATH_INFO *
0x1400097fe  mov     r8, rax; struct CWsmTrackingConfig::CTrackingPathInfo **
0x140009801  xor     edx, edx; bool
0x140009803  call    ?CreateInstance@CTrackingPathInfo@CWsmTrackingConfig@@SAJQEAU_WSM_TRACKING_PATH_INFO@@_NPEAPEAV12@@Z; CWsmTrackingConfig::CTrackingPathInfo::CreateInstance(_WSM_TRACKING_PATH_INFO * const,bool,CWsmTrackingConfig::CTrackingPathInfo * *)
0x140009808  mov     rcx, [rbp+var_20]
0x14000980c  mov     esi, eax
0x14000980e  test    rcx, rcx
0x140009811  jz      short loc_14000983B
0x140009813  mov     rax, [rbp+var_18]
0x140009817  mov     r15, [rax]
0x14000981a  mov     [rax], rcx
0x14000981d  test    r15, r15
0x140009820  jz      short loc_14000983B
0x140009822  mov     rcx, r15; this
0x140009825  call    ??1CTrackingPathInfo@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingPathInfo::~CTrackingPathInfo(void)
0x14000982a  mov     edx, edi; Tag
0x14000982c  mov     rcx, r15; P
0x14000982f  call    cs:__imp_ExFreePoolWithTag
0x140009836  nop     dword ptr [rax+rax+00h]
0x14000983b  test    esi, esi
0x14000983d  js      loc_14000995B
0x140009843  mov     rdx, [r14+10h]
0x140009847  mov     rax, [rbp+arg_10]
0x14000984b  mov     [rbp+arg_10], 0
0x140009853  mov     r15, [rdx-8]
0x140009857  mov     [rdx-8], rax
0x14000985b  test    r15, r15
0x14000985e  jz      short loc_140009879
0x140009860  mov     rcx, r15; this
0x140009863  call    ??1CTrackingPathInfo@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingPathInfo::~CTrackingPathInfo(void)
0x140009868  mov     edx, edi; Tag
0x14000986a  mov     rcx, r15; P
0x14000986d  call    cs:__imp_ExFreePoolWithTag
0x140009874  nop     dword ptr [rax+rax+00h]
0x140009879  mov     rdx, [r12+8]
0x14000987e  lea     r15, [r14+20h]
0x140009882  sub     rdx, [r12]
0x140009886  mov     rcx, r15
0x140009889  sar     rdx, 3
0x14000988d  call    ?resize@?$vector@U_WSM_TRACKING_PATH_INFO@@V?$allocator@U_WSM_TRACKING_PATH_INFO@@@utl@@@utl@@QEAA_N_K@Z; utl::vector<_WSM_TRACKING_PATH_INFO,utl::allocator<_WSM_TRACKING_PATH_INFO>>::resize(unsigned __int64)
0x140009892  test    al, al
0x140009894  jnz     short loc_140009905
0x140009896  mov     rsi, [rbp+arg_10]
0x14000989a  test    rsi, rsi
0x14000989d  jz      short loc_1400098B8
0x14000989f  mov     rcx, rsi; this
0x1400098a2  call    ??1CTrackingPathInfo@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingPathInfo::~CTrackingPathInfo(void)
0x1400098a7  mov     edx, edi; Tag
0x1400098a9  mov     rcx, rsi; P
0x1400098ac  call    cs:__imp_ExFreePoolWithTag
0x1400098b3  nop     dword ptr [rax+rax+00h]
0x1400098b8  test    rbx, rbx
0x1400098bb  jz      short loc_1400098ED
0x1400098bd  mov     rcx, [rbx]; P
0x1400098c0  lea     rax, [rbx+10h]
0x1400098c4  cmp     rcx, rax
0x1400098c7  jz      short loc_1400098DC
0x1400098c9  test    rcx, rcx
0x1400098cc  jz      short loc_1400098DC
0x1400098ce  mov     edx, edi; Tag
0x1400098d0  call    cs:__imp_ExFreePoolWithTag
0x1400098d7  nop     dword ptr [rax+rax+00h]
0x1400098dc  mov     edx, edi; Tag
0x1400098de  mov     rcx, rbx; P
0x1400098e1  call    cs:__imp_ExFreePoolWithTag
0x1400098e8  nop     dword ptr [rax+rax+00h]
0x1400098ed  mov     eax, 0C000009Ah
0x1400098f2  jmp     loc_1400099B4
0x1400098f7  mov     al, byte ptr [rbp+arg_10]
0x1400098fa  jmp     loc_1400097AC
0x1400098ff  mov     r14, [rbp+P]
0x140009903  jmp     short loc_14000995F
0x140009905  mov     rcx, [r15+8]
0x140009909  mov     rax, 0AAAAAAAAAAAAAAABh
0x140009913  sub     rcx, [r15]
0x140009916  xor     r8d, r8d
0x140009919  sar     rcx, 3
0x14000991d  imul    rcx, rax
0x140009921  mov     [r14+68h], ecx
0x140009925  test    ecx, ecx
0x140009927  jz      short loc_140009954
0x140009929  mov     rax, [r12]
0x14000992d  mov     rcx, [rax+r8*8]
0x140009931  mov     rax, [r15]
0x140009934  movups  xmm0, xmmword ptr [rcx+48h]
0x140009938  movsd   xmm1, qword ptr [rcx+58h]
0x14000993d  lea     rcx, [r8+r8*2]
0x140009941  movups  xmmword ptr [rax+rcx*8], xmm0
0x140009945  inc     r8d
0x140009948  movsd   qword ptr [rax+rcx*8+10h], xmm1
0x14000994e  cmp     r8d, [r14+68h]
0x140009952  jb      short loc_140009929
0x140009954  mov     rax, [r15]
0x140009957  mov     [r14+70h], rax
0x14000995b  mov     r14, [rbp+arg_10]
0x14000995f  test    r14, r14
0x140009962  jz      short loc_14000997D
0x140009964  mov     rcx, r14; this
0x140009967  call    ??1CTrackingPathInfo@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingPathInfo::~CTrackingPathInfo(void)
0x14000996c  mov     edx, edi; Tag
0x14000996e  mov     rcx, r14; P
0x140009971  call    cs:__imp_ExFreePoolWithTag
0x140009978  nop     dword ptr [rax+rax+00h]
0x14000997d  test    rbx, rbx
0x140009980  jz      short loc_1400099B2
0x140009982  mov     rcx, [rbx]; P
0x140009985  lea     rax, [rbx+10h]
0x140009989  cmp     rcx, rax
0x14000998c  jz      short loc_1400099A1
0x14000998e  test    rcx, rcx
0x140009991  jz      short loc_1400099A1
0x140009993  mov     edx, edi; Tag
0x140009995  call    cs:__imp_ExFreePoolWithTag
0x14000999c  nop     dword ptr [rax+rax+00h]
0x1400099a1  mov     edx, edi; Tag
0x1400099a3  mov     rcx, rbx; P
0x1400099a6  call    cs:__imp_ExFreePoolWithTag
0x1400099ad  nop     dword ptr [rax+rax+00h]
0x1400099b2  mov     eax, esi
0x1400099b4  mov     rbx, [rsp+40h+arg_0]
0x1400099bc  add     rsp, 40h
0x1400099c0  pop     r15
0x1400099c2  pop     r14
0x1400099c4  pop     r13
0x1400099c6  pop     r12
0x1400099c8  pop     rdi
0x1400099c9  pop     rsi
0x1400099ca  pop     rbp
0x1400099cb  retn
```
