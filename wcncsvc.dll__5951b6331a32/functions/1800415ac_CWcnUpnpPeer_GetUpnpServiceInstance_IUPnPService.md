# CWcnUpnpPeer::GetUpnpServiceInstance(IUPnPService * *)

- ea: `0x1800415ac`
- end: `0x180041abf`
- name: `?GetUpnpServiceInstance@CWcnUpnpPeer@@QEAAJPEAPEAUIUPnPService@@@Z`
- size: `1299`
- prototype: `__int64 __fastcall(CWcnUpnpPeer *__hidden this, struct IUPnPService **)`
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x18003e6c0`
- `0x18003ef38`
- `0x1800448b0`
- `0x180044b70`

## callees

- `0x180004f78`
- `0x180004fb8`
- `0x180005014`
- `0x180041270`
- `0x1800415ac`
- `0x180043208`
- `0x180043338`
- `0x180053004`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004164d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004164d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180041610`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180041610`
- `OLEAUT32!__imp_SysAllocString` at `0x180041743`
- `OLEAUT32!__imp_SysAllocString` at `0x180041743`
- `OLEAUT32!__imp_SysFreeString` at `0x18004165b`
- `OLEAUT32!__imp_SysFreeString` at `0x18004165b`

## string_xrefs

- `0x18004173c`: `urn:wifialliance-org:serviceId:WFAWLANConfig1`
- `0x180041776`: `bstrWcnService`

## pseudocode

```c
__int64 __fastcall CWcnUpnpPeer::GetUpnpServiceInstance(CWcnUpnpPeer *this, struct IUPnPService **a2)
{
  int v4; // ebx
  OLECHAR *v5; // r15
  const char *Indent; // rax
  __int64 v7; // r10
  CWcnUpnpGit *v8; // rcx
  unsigned int v9; // edx
  unsigned int v10; // eax
  __int64 v11; // r10
  int Item; // eax
  int v14; // eax
  int v15; // eax
  CWcnUpnpGit *v16; // rcx
  int v17; // eax
  int v18; // eax
  int v19; // eax
  __int64 v20; // [rsp+70h] [rbp+40h] BYREF
  struct IUnknown *v21; // [rsp+78h] [rbp+48h] BYREF
  void *v22; // [rsp+80h] [rbp+50h] BYREF

  v4 = 0;
  v5 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v7 + 16), 12, WPP_4c5d7ed532773cfdeb1e352313ec5db9_Traceguids, Indent);
  }
  if ( a2 )
    *a2 = 0;
  AcquireSRWLockExclusive((PSRWLOCK)this + 4);
  if ( !*((_DWORD *)this + 6) )
  {
    v22 = 0;
    v21 = 0;
    v20 = 0;
    v9 = *((_DWORD *)this + 7);
    if ( !v9 )
    {
      v4 = -2147019873;
      goto LABEL_9;
    }
    Item = CWcnUpnpGit::GetItem(v8, v9, &GUID_3d44d0d1_98c9_4889_acd1_f9d674bf2221, &v22);
    v4 = Item;
    if ( Item < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          WPP_4c5d7ed532773cfdeb1e352313ec5db9_Traceguids,
          (unsigned int)Item);
      if ( v20 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      if ( v21 )
        ((void (__fastcall *)(struct IUnknown *))v21->lpVtbl->Release)(v21);
      if ( v22 )
        (*(void (__fastcall **)(void *))(*(_QWORD *)v22 + 16LL))(v22);
      goto LABEL_9;
    }
    v5 = SysAllocString(L"urn:wifialliance-org:serviceId:WFAWLANConfig1");
    if ( !v5 )
    {
      v4 = -2147024882;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          WPP_4c5d7ed532773cfdeb1e352313ec5db9_Traceguids,
          "bstrWcnService");
      if ( v20 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      if ( v21 )
        ((void (__fastcall *)(struct IUnknown *))v21->lpVtbl->Release)(v21);
      if ( v22 )
        (*(void (__fastcall **)(void *))(*(_QWORD *)v22 + 16LL))(v22);
      goto LABEL_9;
    }
    v14 = (*(__int64 (__fastcall **)(void *, __int64 *))(*(_QWORD *)v22 + 200LL))(v22, &v20);
    v4 = v14;
    if ( v14 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          WPP_4c5d7ed532773cfdeb1e352313ec5db9_Traceguids,
          (unsigned int)v14);
      if ( v20 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      if ( v21 )
        ((void (__fastcall *)(struct IUnknown *))v21->lpVtbl->Release)(v21);
      if ( v22 )
        (*(void (__fastcall **)(void *))(*(_QWORD *)v22 + 16LL))(v22);
      goto LABEL_9;
    }
    v15 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, struct IUnknown **))(*(_QWORD *)v20 + 72LL))(v20, v5, &v21);
    v4 = v15;
    if ( v15 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          WPP_4c5d7ed532773cfdeb1e352313ec5db9_Traceguids,
          (unsigned int)v15);
      if ( v20 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      if ( v21 )
        ((void (__fastcall *)(struct IUnknown *))v21->lpVtbl->Release)(v21);
      if ( v22 )
        (*(void (__fastcall **)(void *))(*(_QWORD *)v22 + 16LL))(v22);
      goto LABEL_9;
    }
    v17 = CWcnUpnpGit::PutItem(v16, &GUID_a295019c_dc65_47dd_90dc_7fe918a1ab44, v21, (unsigned int *)this + 6);
    v4 = v17;
    if ( v17 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          WPP_4c5d7ed532773cfdeb1e352313ec5db9_Traceguids,
          (unsigned int)v17);
      if ( v20 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      if ( v21 )
        ((void (__fastcall *)(struct IUnknown *))v21->lpVtbl->Release)(v21);
      if ( v22 )
        (*(void (__fastcall **)(void *))(*(_QWORD *)v22 + 16LL))(v22);
      goto LABEL_9;
    }
    v18 = CWcnUpnpPeer::AttachListenerToService(this);
    v4 = v18;
    if ( v18 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          18,
          WPP_4c5d7ed532773cfdeb1e352313ec5db9_Traceguids,
          (unsigned int)v18);
      if ( v20 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      if ( v21 )
        ((void (__fastcall *)(struct IUnknown *))v21->lpVtbl->Release)(v21);
      if ( v22 )
        (*(void (__fastcall **)(void *))(*(_QWORD *)v22 + 16LL))(v22);
      goto LABEL_9;
    }
    if ( v20 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    if ( v21 )
      ((void (__fastcall *)(struct IUnknown *))v21->lpVtbl->Release)(v21);
    v8 = (CWcnUpnpGit *)v22;
    if ( v22 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v22 + 16LL))(v22);
  }
  if ( a2 )
  {
    v19 = CWcnUpnpGit::GetItem(v8, *((_DWORD *)this + 6), &GUID_a295019c_dc65_47dd_90dc_7fe918a1ab44, (void **)a2);
    v4 = v19;
    if ( v19 < 0 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        WPP_4c5d7ed532773cfdeb1e352313ec5db9_Traceguids,
        (unsigned int)v19);
  }
LABEL_9:
  ReleaseSRWLockExclusive((PSRWLOCK)this + 4);
  if ( v5 )
    SysFreeString(v5);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (v4 < 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u) )
  {
    v10 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v11 + 16), 20, (unsigned int)WPP_4c5d7ed532773cfdeb1e352313ec5db9_Traceguids, v10, v4);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800415ac  push    rbp
0x1800415ae  push    rbx
0x1800415af  push    rsi
0x1800415b0  push    rdi
0x1800415b1  push    r12
0x1800415b3  push    r14
0x1800415b5  push    r15
0x1800415b7  mov     rbp, rsp
0x1800415ba  sub     rsp, 30h
0x1800415be  mov     rsi, rdx
0x1800415c1  mov     rdi, rcx
0x1800415c4  xor     ebx, ebx
0x1800415c6  xor     r15d, r15d
0x1800415c9  lea     rax, WPP_GLOBAL_Control
0x1800415d0  mov     r10, cs:WPP_GLOBAL_Control
0x1800415d7  cmp     r10, rax
0x1800415da  jz      short loc_180041601
0x1800415dc  cmp     byte ptr [r10+19h], 6
0x1800415e1  jb      short loc_180041601
0x1800415e3  lea     ecx, [rbx+1]; int
0x1800415e6  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800415eb  lea     edx, [rbx+0Ch]
0x1800415ee  mov     r9, rax
0x1800415f1  lea     r8, WPP_4c5d7ed532773cfdeb1e352313ec5db9_Traceguids
0x1800415f8  mov     rcx, [r10+10h]
0x1800415fc  call    WPP_SF_s
0x180041601  test    rsi, rsi
0x180041604  jz      short loc_180041609
0x180041606  mov     [rsi], rbx
0x180041609  lea     r12, [rdi+20h]
0x18004160d  mov     rcx, r12; SRWLock
0x180041610  call    cs:__imp_AcquireSRWLockExclusive
0x180041616  lea     r14, [rdi+18h]
0x18004161a  cmp     [r14], ebx
0x18004161d  jnz     loc_180041A5C
0x180041623  mov     [rbp+arg_10], rbx
0x180041627  mov     [rbp+arg_8], 0
0x18004162f  mov     [rbp+arg_0], 0
0x180041637  mov     edx, [rdi+1Ch]; unsigned int
0x18004163a  test    edx, edx
0x18004163c  jnz     short loc_1800416AD
0x18004163e  mov     ebx, 8007139Fh
0x180041643  lea     rdi, WPP_GLOBAL_Control
0x18004164a  mov     rcx, r12; SRWLock
0x18004164d  call    cs:__imp_ReleaseSRWLockExclusive
0x180041653  test    r15, r15
0x180041656  jz      short loc_180041661
0x180041658  mov     rcx, r15; bstrString
0x18004165b  call    cs:__imp_SysFreeString
0x180041661  mov     r10, cs:WPP_GLOBAL_Control
0x180041668  cmp     r10, rdi
0x18004166b  jz      short loc_18004169C
0x18004166d  test    ebx, ebx
0x18004166f  js      short loc_180041678
0x180041671  cmp     byte ptr [r10+19h], 6
0x180041676  jb      short loc_18004169C
0x180041678  or      ecx, 0FFFFFFFFh; int
0x18004167b  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180041680  mov     edx, 14h
0x180041685  mov     [rsp+30h+var_10], ebx
0x180041689  mov     r9, rax
0x18004168c  lea     r8, WPP_4c5d7ed532773cfdeb1e352313ec5db9_Traceguids
0x180041693  mov     rcx, [r10+10h]
0x180041697  call    WPP_SF_sd
0x18004169c  mov     eax, ebx
0x18004169e  add     rsp, 30h
0x1800416a2  pop     r15
0x1800416a4  pop     r14
0x1800416a6  pop     r12
0x1800416a8  pop     rdi
0x1800416a9  pop     rsi
0x1800416aa  pop     rbx
0x1800416ab  pop     rbp
0x1800416ac  retn
0x1800416ad  lea     r9, [rbp+arg_10]; void **
0x1800416b1  lea     r8, _GUID_3d44d0d1_98c9_4889_acd1_f9d674bf2221; struct _GUID *
0x1800416b8  call    ?GetItem@CWcnUpnpGit@@QEAAJKAEBU_GUID@@PEAPEAX@Z; CWcnUpnpGit::GetItem(ulong,_GUID const &,void * *)
0x1800416bd  mov     ebx, eax
0x1800416bf  test    eax, eax
0x1800416c1  jns     short loc_18004173C
0x1800416c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800416ca  lea     rdi, WPP_GLOBAL_Control
0x1800416d1  cmp     rcx, rdi
0x1800416d4  jz      short loc_1800416F5
0x1800416d6  cmp     byte ptr [rcx+19h], 2
0x1800416da  jb      short loc_1800416F5
0x1800416dc  mov     edx, 0Dh
0x1800416e1  mov     r9d, eax
0x1800416e4  lea     r8, WPP_4c5d7ed532773cfdeb1e352313ec5db9_Traceguids
0x1800416eb  mov     rcx, [rcx+10h]
0x1800416ef  call    WPP_SF_d
0x1800416f4  nop
0x1800416f5  mov     rcx, [rbp+arg_0]
0x1800416f9  test    rcx, rcx
0x1800416fc  jz      short loc_18004170B
0x1800416fe  mov     rax, [rcx]
0x180041701  mov     rax, [rax+10h]
0x180041705  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004170a  nop
0x18004170b  mov     rcx, [rbp+arg_8]
0x18004170f  test    rcx, rcx
0x180041712  jz      short loc_180041721
0x180041714  mov     rax, [rcx]
0x180041717  mov     rax, [rax+10h]
0x18004171b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041720  nop
0x180041721  mov     rcx, [rbp+arg_10]
0x180041725  test    rcx, rcx
0x180041728  jz      short loc_180041737
0x18004172a  mov     rax, [rcx]
0x18004172d  mov     rax, [rax+10h]
0x180041731  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041736  nop
0x180041737  jmp     loc_18004164A
0x18004173c  lea     rcx, aUrnWifiallianc; "urn:wifialliance-org:serviceId:WFAWLANC"...
0x180041743  call    cs:__imp_SysAllocString
0x180041749  mov     r15, rax
0x18004174c  test    rax, rax
0x18004174f  jnz     loc_1800417D5
0x180041755  mov     ebx, 8007000Eh
0x18004175a  mov     rcx, cs:WPP_GLOBAL_Control
0x180041761  lea     rdi, WPP_GLOBAL_Control
0x180041768  cmp     rcx, rdi
0x18004176b  jz      short loc_18004178E
0x18004176d  cmp     byte ptr [rcx+19h], 2
0x180041771  jb      short loc_18004178E
0x180041773  lea     edx, [rax+0Eh]
0x180041776  lea     r9, aBstrwcnservice; "bstrWcnService"
0x18004177d  lea     r8, WPP_4c5d7ed532773cfdeb1e352313ec5db9_Traceguids
0x180041784  mov     rcx, [rcx+10h]
0x180041788  call    WPP_SF_s
0x18004178d  nop
0x18004178e  mov     rcx, [rbp+arg_0]
0x180041792  test    rcx, rcx
0x180041795  jz      short loc_1800417A4
0x180041797  mov     rax, [rcx]
0x18004179a  mov     rax, [rax+10h]
0x18004179e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800417a3  nop
0x1800417a4  mov     rcx, [rbp+arg_8]
0x1800417a8  test    rcx, rcx
0x1800417ab  jz      short loc_1800417BA
0x1800417ad  mov     rax, [rcx]
0x1800417b0  mov     rax, [rax+10h]
0x1800417b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800417b9  nop
0x1800417ba  mov     rcx, [rbp+arg_10]
0x1800417be  test    rcx, rcx
0x1800417c1  jz      short loc_1800417D0
0x1800417c3  mov     rax, [rcx]
0x1800417c6  mov     rax, [rax+10h]
0x1800417ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800417cf  nop
0x1800417d0  jmp     loc_18004164A
0x1800417d5  mov     rcx, [rbp+arg_10]
0x1800417d9  mov     rax, [rcx]
0x1800417dc  lea     rdx, [rbp+arg_0]
0x1800417e0  mov     rax, [rax+0C8h]
0x1800417e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800417ec  mov     ebx, eax
0x1800417ee  test    eax, eax
0x1800417f0  jns     short loc_18004186B
0x1800417f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800417f9  lea     rdi, WPP_GLOBAL_Control
0x180041800  cmp     rcx, rdi
0x180041803  jz      short loc_180041824
0x180041805  cmp     byte ptr [rcx+19h], 2
0x180041809  jb      short loc_180041824
0x18004180b  mov     edx, 0Fh
0x180041810  mov     r9d, eax
0x180041813  lea     r8, WPP_4c5d7ed532773cfdeb1e352313ec5db9_Traceguids
0x18004181a  mov     rcx, [rcx+10h]
0x18004181e  call    WPP_SF_d
0x180041823  nop
0x180041824  mov     rcx, [rbp+arg_0]
0x180041828  test    rcx, rcx
0x18004182b  jz      short loc_18004183A
0x18004182d  mov     rax, [rcx]
0x180041830  mov     rax, [rax+10h]
0x180041834  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041839  nop
0x18004183a  mov     rcx, [rbp+arg_8]
0x18004183e  test    rcx, rcx
0x180041841  jz      short loc_180041850
0x180041843  mov     rax, [rcx]
0x180041846  mov     rax, [rax+10h]
0x18004184a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004184f  nop
0x180041850  mov     rcx, [rbp+arg_10]
0x180041854  test    rcx, rcx
0x180041857  jz      short loc_180041866
0x180041859  mov     rax, [rcx]
0x18004185c  mov     rax, [rax+10h]
0x180041860  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041865  nop
0x180041866  jmp     loc_18004164A
0x18004186b  mov     rcx, [rbp+arg_0]
0x18004186f  mov     rax, [rcx]
0x180041872  lea     r8, [rbp+arg_8]
0x180041876  mov     rdx, r15
0x180041879  mov     rax, [rax+48h]
0x18004187d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041882  mov     ebx, eax
0x180041884  test    eax, eax
0x180041886  jns     short loc_180041901
0x180041888  mov     rcx, cs:WPP_GLOBAL_Control
0x18004188f  lea     rdi, WPP_GLOBAL_Control
0x180041896  cmp     rcx, rdi
0x180041899  jz      short loc_1800418BA
0x18004189b  cmp     byte ptr [rcx+19h], 2
0x18004189f  jb      short loc_1800418BA
0x1800418a1  mov     edx, 10h
0x1800418a6  mov     r9d, eax
0x1800418a9  lea     r8, WPP_4c5d7ed532773cfdeb1e352313ec5db9_Traceguids
0x1800418b0  mov     rcx, [rcx+10h]
0x1800418b4  call    WPP_SF_d
0x1800418b9  nop
0x1800418ba  mov     rcx, [rbp+arg_0]
0x1800418be  test    rcx, rcx
0x1800418c1  jz      short loc_1800418D0
0x1800418c3  mov     rax, [rcx]
0x1800418c6  mov     rax, [rax+10h]
0x1800418ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800418cf  nop
0x1800418d0  mov     rcx, [rbp+arg_8]
0x1800418d4  test    rcx, rcx
0x1800418d7  jz      short loc_1800418E6
0x1800418d9  mov     rax, [rcx]
0x1800418dc  mov     rax, [rax+10h]
0x1800418e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800418e5  nop
0x1800418e6  mov     rcx, [rbp+arg_10]
0x1800418ea  test    rcx, rcx
0x1800418ed  jz      short loc_1800418FC
0x1800418ef  mov     rax, [rcx]
0x1800418f2  mov     rax, [rax+10h]
0x1800418f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800418fb  nop
0x1800418fc  jmp     loc_18004164A
0x180041901  mov     r9, r14; unsigned int *
0x180041904  mov     r8, [rbp+arg_8]; struct IUnknown *
0x180041908  lea     rdx, _GUID_a295019c_dc65_47dd_90dc_7fe918a1ab44; struct _GUID *
0x18004190f  call    ?PutItem@CWcnUpnpGit@@QEAAJAEBU_GUID@@PEAUIUnknown@@PEAK@Z; CWcnUpnpGit::PutItem(_GUID const &,IUnknown *,ulong *)
0x180041914  mov     ebx, eax
0x180041916  test    eax, eax
0x180041918  jns     short loc_180041993
0x18004191a  mov     rcx, cs:WPP_GLOBAL_Control
0x180041921  lea     rdi, WPP_GLOBAL_Control
0x180041928  cmp     rcx, rdi
0x18004192b  jz      short loc_18004194C
0x18004192d  cmp     byte ptr [rcx+19h], 2
0x180041931  jb      short loc_18004194C
0x180041933  mov     edx, 11h
0x180041938  mov     r9d, eax
0x18004193b  lea     r8, WPP_4c5d7ed532773cfdeb1e352313ec5db9_Traceguids
0x180041942  mov     rcx, [rcx+10h]
0x180041946  call    WPP_SF_d
0x18004194b  nop
0x18004194c  mov     rcx, [rbp+arg_0]
0x180041950  test    rcx, rcx
0x180041953  jz      short loc_180041962
0x180041955  mov     rax, [rcx]
0x180041958  mov     rax, [rax+10h]
0x18004195c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041961  nop
0x180041962  mov     rcx, [rbp+arg_8]
0x180041966  test    rcx, rcx
0x180041969  jz      short loc_180041978
0x18004196b  mov     rax, [rcx]
0x18004196e  mov     rax, [rax+10h]
0x180041972  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041977  nop
0x180041978  mov     rcx, [rbp+arg_10]
0x18004197c  test    rcx, rcx
0x18004197f  jz      short loc_18004198E
0x180041981  mov     rax, [rcx]
0x180041984  mov     rax, [rax+10h]
0x180041988  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004198d  nop
0x18004198e  jmp     loc_18004164A
0x180041993  mov     rcx, rdi; this
0x180041996  call    ?AttachListenerToService@CWcnUpnpPeer@@AEAAJXZ; CWcnUpnpPeer::AttachListenerToService(void)
0x18004199b  mov     ebx, eax
0x18004199d  test    eax, eax
0x18004199f  jns     short loc_180041A1A
0x1800419a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800419a8  lea     rdi, WPP_GLOBAL_Control
0x1800419af  cmp     rcx, rdi
0x1800419b2  jz      short loc_1800419D3
0x1800419b4  cmp     byte ptr [rcx+19h], 2
0x1800419b8  jb      short loc_1800419D3
0x1800419ba  mov     edx, 12h
0x1800419bf  mov     r9d, eax
0x1800419c2  lea     r8, WPP_4c5d7ed532773cfdeb1e352313ec5db9_Traceguids
0x1800419c9  mov     rcx, [rcx+10h]
0x1800419cd  call    WPP_SF_d
0x1800419d2  nop
0x1800419d3  mov     rcx, [rbp+arg_0]
0x1800419d7  test    rcx, rcx
0x1800419da  jz      short loc_1800419E9
  ... truncated ...
```
