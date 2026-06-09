# DBManager::OpenTable(US_TABLEID,ulong,ulong,US_SORTSPEC *,_USRestriction const *,IDBTable * *,ulong *)

- ea: `0x180042580`
- end: `0x1800429a6`
- name: `?OpenTable@DBManager@@UEAAJW4US_TABLEID@@KKPEAUUS_SORTSPEC@@PEBU_USRestriction@@PEAPEAVIDBTable@@PEAK@Z`
- size: `1062`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004440`
- `0x1800068f0`
- `0x180028ef4`
- `0x1800396c8`
- `0x180039898`
- `0x180042580`
- `0x1800429b0`
- `0x180043c3c`
- `0x180043cdc`
- `0x18006f180`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800426b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004293a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800426b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004293a`

## string_xrefs

- `0x180042708`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180042791`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x1800427a2`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180042830`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`

## pseudocode

```c
__int64 __fastcall DBManager::OpenTable(
        DBManager *a1,
        unsigned int a2,
        int a3,
        unsigned int a4,
        __int64 a5,
        struct _USRestriction *a6,
        _QWORD *a7,
        unsigned int *a8)
{
  __int64 v8; // rax
  int v9; // r12d
  __int64 (__fastcall *v12)(DBManager *, __int64 *); // rax
  int v15; // eax
  unsigned int v16; // ebx
  struct _USRestriction *v17; // r15
  int v18; // eax
  __int64 v19; // rcx
  unsigned int v20; // r14d
  HLOCAL v21; // rbx
  unsigned int v22; // r14d
  int v23; // esi
  __int64 v24; // rcx
  __int64 v26; // rcx
  __int64 v27; // r9
  __int64 v28; // r9
  void *v29; // rax
  unsigned int v30; // [rsp+28h] [rbp-58h]
  unsigned int v31; // [rsp+50h] [rbp-30h] BYREF
  __int64 v32; // [rsp+58h] [rbp-28h] BYREF
  __int64 v33; // [rsp+60h] [rbp-20h] BYREF
  HLOCAL hMem; // [rsp+68h] [rbp-18h] BYREF
  _QWORD v35[2]; // [rsp+70h] [rbp-10h] BYREF
  unsigned int v36; // [rsp+C0h] [rbp+40h] BYREF
  unsigned int v37; // [rsp+D8h] [rbp+58h]

  v37 = a4;
  v8 = *(_QWORD *)a1;
  v9 = 0;
  v31 = 0;
  v33 = 0;
  v32 = 0;
  v12 = *(__int64 (__fastcall **)(DBManager *, __int64 *))(v8 + 48);
  v36 = 0;
  v35[0] = 0;
  v15 = v12(a1, &v33);
  v16 = v15;
  if ( v15 < 0 )
  {
    Log_UnistoreHREvent_0(
      (unsigned int)v15,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      1516);
    if ( v33 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    return v16;
  }
  v17 = a6;
  hMem = 0;
  v18 = DBManager::SelectTableSortIndex(
          a1,
          a2,
          a4,
          a5,
          a6,
          (unsigned int **)&hMem,
          (struct _USRestriction *)&v31,
          (int *)&v36,
          v35);
  if ( v18 >= 0 )
  {
    v9 = 1;
    goto LABEL_4;
  }
  v16 = -2147221292;
  if ( v18 == -2147221292 )
  {
LABEL_48:
    auto_local_array_ptr<unsigned char>::~auto_local_array_ptr<unsigned char>(&hMem);
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v32);
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v33);
    return v16;
  }
  if ( !v17 )
  {
LABEL_47:
    v16 = -2147024809;
    goto LABEL_48;
  }
  if ( hMem )
    auto_local_array_ptr<unsigned char>::~auto_local_array_ptr<unsigned char>(&hMem);
  hMem = 0;
  if ( (int)DBManager::SelectTableSortIndex(
              a1,
              a2,
              v37,
              a5,
              0,
              (unsigned int **)&hMem,
              (struct _USRestriction *)&v31,
              (int *)&v36,
              v35) < 0 )
  {
    if ( (Microsoft_Windows_UserDataAccess_UnifiedStoreEnableBits & 0x20) != 0 )
    {
      v29 = _t_address();
      EtwTraceMessage(&ETWMESSAGE, v29, 0);
    }
    goto LABEL_47;
  }
LABEL_4:
  v20 = v36;
  if ( (a3 & 0x1000000) != 0 )
    v20 = v36 | 4;
  v21 = hMem;
  if ( (a3 & 0x2000000) != 0 )
  {
    if ( v9 && (!hMem || (a3 & 0x4000000) != 0 && v35[0] == 1) )
      goto LABEL_8;
    if ( (a3 & 0x8000000) != 0 )
    {
      v16 = -2147221297;
    }
    else
    {
      if ( (Microsoft_Windows_UserDataAccess_UnifiedStoreEnableBits & 0x100) != 0 )
        McTemplateU0q_EventWriteTransfer(v19, UnifiedStore_Opening_Unindexed, a2);
      LogRestriction(v17);
      Log_AssertionEvent(
        v26,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
        1587);
      v16 = -2147221297;
      Log_UnistoreHREvent_0(
        2147745999LL,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
        1588);
    }
    goto LABEL_48;
  }
  if ( !v9 )
  {
    if ( a2 && (a3 & 0x8000000) == 0 )
    {
      if ( (Microsoft_Windows_UserDataAccess_UnifiedStoreEnableBits & 0x100) != 0 )
        McTemplateU0q_EventWriteTransfer(v19, UnifiedStore_Opening_Unindexed, a2);
      LogRestriction(v17);
    }
    v27 = v20;
    v22 = v31;
    v23 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64, __int64 *))(*(_QWORD *)v33 + 32LL))(
            v33,
            a2,
            v31,
            v27,
            &v32);
    if ( v23 < 0 )
    {
      v28 = 1604;
    }
    else
    {
      if ( !v17 )
        goto LABEL_9;
      v23 = (*(__int64 (__fastcall **)(__int64, struct _USRestriction *, _QWORD))(*(_QWORD *)v32 + 160LL))(v32, v17, 0);
      if ( v23 >= 0 )
        goto LABEL_9;
      v28 = 1609;
    }
    goto LABEL_33;
  }
LABEL_8:
  v30 = v20;
  v22 = v31;
  v23 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, struct _USRestriction *, HLOCAL, unsigned int, __int64 *))(*(_QWORD *)v33 + 40LL))(
          v33,
          a2,
          v31,
          v17,
          hMem,
          v30,
          &v32);
  if ( v23 >= 0 )
  {
LABEL_9:
    if ( a8 )
      *a8 = v22;
    v24 = v32;
    v32 = 0;
    *a7 = v24;
    if ( v21 )
    {
      LocalFree(v21);
      if ( v32 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    }
    if ( v33 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    return 0;
  }
  v28 = 1615;
LABEL_33:
  Log_UnistoreHREvent_0(
    (unsigned int)v23,
    1,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
    v28);
  if ( v21 )
    LocalFree(v21);
  if ( v32 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  if ( v33 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  return (unsigned int)v23;
}

```

## disassembly

```asm
0x180042580  mov     [rsp-38h+arg_8], rbx
0x180042585  mov     [rsp-38h+arg_18], r9d
0x18004258a  push    rbp
0x18004258b  push    rsi
0x18004258c  push    rdi
0x18004258d  push    r12
0x18004258f  push    r13
0x180042591  push    r14
0x180042593  push    r15
0x180042595  mov     rbp, rsp
0x180042598  sub     rsp, 80h
0x18004259f  mov     rax, [rcx]
0x1800425a2  xor     r12d, r12d
0x1800425a5  mov     r13d, edx
0x1800425a8  mov     [rbp+var_30], r12d
0x1800425ac  lea     rdx, [rbp+var_20]
0x1800425b0  mov     [rbp+var_20], r12
0x1800425b4  mov     edi, r9d
0x1800425b7  mov     [rbp+var_28], r12
0x1800425bb  mov     rax, [rax+30h]
0x1800425bf  mov     esi, r8d
0x1800425c2  mov     r14, rcx
0x1800425c5  mov     [rbp+arg_0], r12d
0x1800425c9  mov     [rbp+var_10], r12
0x1800425cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800425d2  mov     ebx, eax
0x1800425d4  test    eax, eax
0x1800425d6  js      loc_180042702
0x1800425dc  mov     r15, [rbp+arg_28]
0x1800425e0  lea     rax, [rbp+var_10]
0x1800425e4  mov     r9, [rbp+arg_20]
0x1800425e8  mov     r8d, edi
0x1800425eb  mov     [rsp+80h+var_40], rax
0x1800425f0  mov     edx, r13d
0x1800425f3  lea     rax, [rbp+arg_0]
0x1800425f7  mov     [rbp+hMem], r12
0x1800425fb  mov     [rsp+80h+var_48], rax
0x180042600  mov     rcx, r14
0x180042603  lea     rax, [rbp+var_30]
0x180042607  mov     [rsp+80h+var_50], rax
0x18004260c  lea     rax, [rbp+hMem]
0x180042610  mov     [rsp+80h+var_58], rax
0x180042615  mov     [rsp+80h+var_60], r15
0x18004261a  call    ?SelectTableSortIndex@DBManager@@IEAAJW4US_TABLEID@@KPEAUUS_SORTSPEC@@PEBU_USRestriction@@PEAPEAU4@PEAK4PEA_K@Z; DBManager::SelectTableSortIndex(US_TABLEID,ulong,US_SORTSPEC *,_USRestriction const *,_USRestriction * *,ulong *,ulong *,unsigned __int64 *)
0x18004261f  lea     edi, [r12+1]
0x180042624  test    eax, eax
0x180042626  js      loc_18004287A
0x18004262c  mov     r12d, edi
0x18004262f  mov     r14d, [rbp+arg_0]
0x180042633  bt      esi, 18h
0x180042637  jnb     short loc_18004263D
0x180042639  or      r14d, 4
0x18004263d  mov     rbx, [rbp+hMem]
0x180042641  bt      esi, 19h
0x180042645  jb      loc_180042749
0x18004264b  test    r12d, r12d
0x18004264e  jz      loc_1800427BD
0x180042654  mov     rcx, [rbp+var_20]
0x180042658  lea     rdx, [rbp+var_28]
0x18004265c  mov     [rsp+80h+var_50], rdx
0x180042661  mov     r9, r15
0x180042664  mov     dword ptr [rsp+80h+var_58], r14d
0x180042669  mov     edx, r13d
0x18004266c  mov     r14d, [rbp+var_30]
0x180042670  mov     r8d, r14d
0x180042673  mov     rax, [rcx]
0x180042676  mov     [rsp+80h+var_60], rbx
0x18004267b  mov     rax, [rax+28h]
0x18004267f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042684  mov     esi, eax
0x180042686  test    eax, eax
0x180042688  js      loc_18004282A
0x18004268e  mov     rax, [rbp+arg_38]
0x180042692  test    rax, rax
0x180042695  jz      short loc_18004269A
0x180042697  mov     [rax], r14d
0x18004269a  mov     rcx, [rbp+var_28]
0x18004269e  mov     rax, [rbp+arg_30]
0x1800426a2  mov     [rbp+var_28], 0
0x1800426aa  mov     [rax], rcx
0x1800426ad  test    rbx, rbx
0x1800426b0  jz      short loc_1800426D0
0x1800426b2  mov     rcx, rbx; hMem
0x1800426b5  call    cs:__imp_LocalFree
0x1800426bb  mov     rcx, [rbp+var_28]
0x1800426bf  test    rcx, rcx
0x1800426c2  jz      short loc_1800426D0
0x1800426c4  mov     rax, [rcx]
0x1800426c7  mov     rax, [rax+10h]
0x1800426cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800426d0  mov     rcx, [rbp+var_20]
0x1800426d4  test    rcx, rcx
0x1800426d7  jz      short loc_1800426E5
0x1800426d9  mov     rax, [rcx]
0x1800426dc  mov     rax, [rax+10h]
0x1800426e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800426e5  xor     eax, eax
0x1800426e7  mov     rbx, [rsp+80h+arg_8]
0x1800426ef  add     rsp, 80h
0x1800426f6  pop     r15
0x1800426f8  pop     r14
0x1800426fa  pop     r13
0x1800426fc  pop     r12
0x1800426fe  pop     rdi
0x1800426ff  pop     rsi
0x180042700  pop     rbp
0x180042701  retn
0x180042702  mov     r9d, 5ECh
0x180042708  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18004270f  mov     edx, 1
0x180042714  mov     ecx, ebx
0x180042716  call    Log_UnistoreHREvent_0
0x18004271b  mov     rcx, [rbp+var_28]
0x18004271f  test    rcx, rcx
0x180042722  jz      short loc_180042730
0x180042724  mov     rax, [rcx]
0x180042727  mov     rax, [rax+10h]
0x18004272b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042730  mov     rcx, [rbp+var_20]
0x180042734  test    rcx, rcx
0x180042737  jz      short loc_180042745
0x180042739  mov     rax, [rcx]
0x18004273c  mov     rax, [rax+10h]
0x180042740  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042745  mov     eax, ebx
0x180042747  jmp     short loc_1800426E7
0x180042749  test    r12d, r12d
0x18004274c  jz      short loc_180042761
0x18004274e  test    rbx, rbx
0x180042751  jz      loc_180042654
0x180042757  bt      esi, 1Ah
0x18004275b  jb      loc_18004298D
0x180042761  bt      esi, 1Bh
0x180042765  jb      loc_18004299C
0x18004276b  test    byte ptr cs:Microsoft_Windows_UserDataAccess_UnifiedStoreEnableBits+1, dil
0x180042772  jz      short loc_180042783
0x180042774  mov     r8d, r13d
0x180042777  lea     rdx, UnifiedStore_Opening_Unindexed
0x18004277e  call    McTemplateU0q_EventWriteTransfer
0x180042783  mov     rcx, r15
0x180042786  call    LogRestriction
0x18004278b  mov     r8d, 633h
0x180042791  lea     rdx, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180042798  call    Log_AssertionEvent
0x18004279d  mov     ebx, 800400CFh
0x1800427a2  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800427a9  mov     ecx, ebx
0x1800427ab  mov     r9d, 634h
0x1800427b1  mov     edx, edi
0x1800427b3  call    Log_UnistoreHREvent_0
0x1800427b8  jmp     loc_180042917
0x1800427bd  test    r13d, r13d
0x1800427c0  jnz     loc_180042945
0x1800427c6  mov     rcx, [rbp+var_20]
0x1800427ca  lea     rdx, [rbp+var_28]
0x1800427ce  mov     r9d, r14d
0x1800427d1  mov     [rsp+80h+var_60], rdx
0x1800427d6  mov     r14d, [rbp+var_30]
0x1800427da  mov     edx, r13d
0x1800427dd  mov     r8d, r14d
0x1800427e0  mov     rax, [rcx]
0x1800427e3  mov     rax, [rax+20h]
0x1800427e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800427ec  mov     esi, eax
0x1800427ee  test    eax, eax
0x1800427f0  js      loc_180042974
0x1800427f6  test    r15, r15
0x1800427f9  jz      loc_18004268E
0x1800427ff  mov     rcx, [rbp+var_28]
0x180042803  xor     r8d, r8d
0x180042806  mov     rdx, r15
0x180042809  mov     rax, [rcx]
0x18004280c  mov     rax, [rax+0A0h]
0x180042813  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042818  mov     esi, eax
0x18004281a  test    eax, eax
0x18004281c  jns     loc_18004268E
0x180042822  mov     r9d, 649h
0x180042828  jmp     short loc_180042830
0x18004282a  mov     r9d, 64Fh
0x180042830  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180042837  mov     edx, edi
0x180042839  mov     ecx, esi
0x18004283b  call    Log_UnistoreHREvent_0
0x180042840  test    rbx, rbx
0x180042843  jnz     loc_180042937
0x180042849  mov     rcx, [rbp+var_28]
0x18004284d  test    rcx, rcx
0x180042850  jz      short loc_18004285E
0x180042852  mov     rax, [rcx]
0x180042855  mov     rax, [rax+10h]
0x180042859  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004285e  mov     rcx, [rbp+var_20]
0x180042862  test    rcx, rcx
0x180042865  jz      short loc_180042873
0x180042867  mov     rax, [rcx]
0x18004286a  mov     rax, [rax+10h]
0x18004286e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042873  mov     eax, esi
0x180042875  jmp     loc_1800426E7
0x18004287a  mov     ebx, 800400D4h
0x18004287f  cmp     eax, ebx
0x180042881  jz      loc_180042917
0x180042887  test    r15, r15
0x18004288a  jz      loc_180042912
0x180042890  xor     ebx, ebx
0x180042892  cmp     [rbp+hMem], rbx
0x180042896  jnz     loc_18004297F
0x18004289c  mov     r9, [rbp+arg_20]
0x1800428a0  lea     rax, [rbp+var_10]
0x1800428a4  mov     r8d, [rbp+arg_18]
0x1800428a8  mov     edx, r13d
0x1800428ab  mov     [rsp+80h+var_40], rax
0x1800428b0  mov     rcx, r14
0x1800428b3  lea     rax, [rbp+arg_0]
0x1800428b7  mov     [rbp+hMem], rbx
0x1800428bb  mov     [rsp+80h+var_48], rax
0x1800428c0  lea     rax, [rbp+var_30]
0x1800428c4  mov     [rsp+80h+var_50], rax
0x1800428c9  lea     rax, [rbp+hMem]
0x1800428cd  mov     [rsp+80h+var_58], rax
0x1800428d2  mov     [rsp+80h+var_60], rbx
0x1800428d7  call    ?SelectTableSortIndex@DBManager@@IEAAJW4US_TABLEID@@KPEAUUS_SORTSPEC@@PEBU_USRestriction@@PEAPEAU4@PEAK4PEA_K@Z; DBManager::SelectTableSortIndex(US_TABLEID,ulong,US_SORTSPEC *,_USRestriction const *,_USRestriction * *,ulong *,ulong *,unsigned __int64 *)
0x1800428dc  test    eax, eax
0x1800428de  jns     loc_18004262F
0x1800428e4  test    byte ptr cs:Microsoft_Windows_UserDataAccess_UnifiedStoreEnableBits, 20h
0x1800428eb  jz      short loc_180042912
0x1800428ed  call    ?_t_address@@YAPEAXXZ; _t_address(void)
0x1800428f2  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800428f6  lea     rcx, _ETWMESSAGE; EventDescriptor
0x1800428fd  mov     [rsp+80h+var_58], r9
0x180042902  mov     rdx, rax; void *
0x180042905  xor     r8d, r8d
0x180042908  mov     [rsp+80h+var_60], rbx
0x18004290d  call    ?EtwTraceMessage@@YAXPEBU_EVENT_DESCRIPTOR@@PEAXZZ; EtwTraceMessage(_EVENT_DESCRIPTOR const *,void *,...)
0x180042912  mov     ebx, 80070057h
0x180042917  lea     rcx, [rbp+hMem]
0x18004291b  call    ??1?$auto_local_array_ptr@E@@QEAA@XZ; auto_local_array_ptr<uchar>::~auto_local_array_ptr<uchar>(void)
0x180042920  lea     rcx, [rbp+var_28]; void *
0x180042924  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x180042929  lea     rcx, [rbp+var_20]; void *
0x18004292d  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x180042932  jmp     loc_180042745
0x180042937  mov     rcx, rbx; hMem
0x18004293a  call    cs:__imp_LocalFree
0x180042940  jmp     loc_180042849
0x180042945  bt      esi, 1Bh
0x180042949  jb      loc_1800427C6
0x18004294f  test    byte ptr cs:Microsoft_Windows_UserDataAccess_UnifiedStoreEnableBits+1, dil
0x180042956  jz      short loc_180042967
0x180042958  mov     r8d, r13d
0x18004295b  lea     rdx, UnifiedStore_Opening_Unindexed
0x180042962  call    McTemplateU0q_EventWriteTransfer
0x180042967  mov     rcx, r15
0x18004296a  call    LogRestriction
0x18004296f  jmp     loc_1800427C6
0x180042974  mov     r9d, 644h
0x18004297a  jmp     loc_180042830
0x18004297f  lea     rcx, [rbp+hMem]
0x180042983  call    ??1?$auto_local_array_ptr@E@@QEAA@XZ; auto_local_array_ptr<uchar>::~auto_local_array_ptr<uchar>(void)
0x180042988  jmp     loc_18004289C
0x18004298d  cmp     [rbp+var_10], rdi
0x180042991  jz      loc_180042654
0x180042997  jmp     loc_180042761
0x18004299c  mov     ebx, 800400CFh
0x1800429a1  jmp     loc_180042917
```
