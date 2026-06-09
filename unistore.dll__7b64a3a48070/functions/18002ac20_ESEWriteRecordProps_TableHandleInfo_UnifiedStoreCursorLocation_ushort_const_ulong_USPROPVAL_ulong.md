# ESEWriteRecordProps(TableHandleInfo *,UnifiedStoreCursorLocation &,ushort const *,ulong,_USPROPVAL *,ulong *)

- ea: `0x18002ac20`
- end: `0x18002b4a3`
- name: `?ESEWriteRecordProps@@YAJPEAUTableHandleInfo@@AEAVUnifiedStoreCursorLocation@@PEBGKPEAU_USPROPVAL@@PEAK@Z`
- size: `2179`
- prototype: `int(struct TableHandleInfo *, struct UnifiedStoreCursorLocation *, const unsigned __int16 *, unsigned int, struct _USPROPVAL *, unsigned int *)`
- caller_count: `2`
- callee_count: `19`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180003598`
- `0x180029c10`

## callees

- `0x180004464`
- `0x1800068f0`
- `0x18000f880`
- `0x1800125d0`
- `0x18001abf4`
- `0x180029b8c`
- `0x18002ac20`
- `0x18002b4b0`
- `0x180050f70`
- `0x18005160c`
- `0x180066290`
- `0x18006c710`
- `0x18006c7f4`
- `0x18006f180`
- `0x180073300`
- `0x180078a40`
- `0x180079030`
- `0x1800969b8`
- `0x1800c5092`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002ac4d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002b028`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002ac4d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002b028`

## string_xrefs

- `0x18002b067`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x18002b0e3`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x18002b136`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x18002b150`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x18002b246`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x18002b285`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x18002b339`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x18002b38b`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x18002b404`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`

## pseudocode

```c
__int64 __fastcall ESEWriteRecordProps(
        struct TableHandleInfo *a1,
        void **a2,
        unsigned __int16 *a3,
        unsigned int a4,
        struct _USPROPVAL *a5,
        unsigned int *a6)
{
  unsigned __int64 v6; // rsi
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // r8
  unsigned int v15; // edx
  unsigned __int64 v16; // rcx
  __int64 v17; // rax
  unsigned __int64 v18; // rcx
  unsigned __int64 v19; // rax
  __int64 v20; // r14
  char *v21; // rax
  char *v22; // rdi
  char *v23; // r14
  char *v24; // r15
  unsigned __int64 v25; // rax
  __int64 v26; // rcx
  unsigned __int64 v27; // rax
  unsigned __int64 v28; // rcx
  __int64 v29; // rdi
  char *v30; // rax
  char *v31; // rbx
  char *v32; // rdi
  char *v33; // r14
  unsigned __int16 v34; // di
  struct _USPROPVAL *v35; // r13
  DPHelper *v36; // rcx
  unsigned int v37; // r12d
  int v38; // r14d
  int v39; // eax
  unsigned int v40; // r12d
  int DataFromUSPropVal; // eax
  unsigned int v42; // r14d
  char *v43; // rax
  __int128 v44; // xmm1
  __int64 v45; // xmm0_8
  int v46; // eax
  __int64 v47; // rcx
  unsigned int v48; // ebx
  void *v49; // rbx
  int v50; // eax
  __int64 v52; // r9
  __int64 v53; // rcx
  void *v54; // rbx
  _OWORD *v55; // rax
  unsigned int *v56; // r8
  int ProtectedPropIdByOrgPropId; // eax
  unsigned int v58; // r14d
  int ProtectedDataFromUSPropVal; // eax
  unsigned int v60; // r14d
  __int128 v61; // xmm1
  __int64 v62; // xmm0_8
  unsigned __int32 v63; // edx
  int v64; // eax
  void *Block; // [rsp+40h] [rbp-C0h] BYREF
  char *v66; // [rsp+48h] [rbp-B8h]
  char *v67; // [rsp+50h] [rbp-B0h]
  void *Src; // [rsp+58h] [rbp-A8h] BYREF
  char *v69; // [rsp+60h] [rbp-A0h]
  char *v70; // [rsp+68h] [rbp-98h]
  void *v71; // [rsp+70h] [rbp-90h] BYREF
  _OWORD *v72; // [rsp+78h] [rbp-88h]
  _OWORD *v73; // [rsp+80h] [rbp-80h]
  ULONGLONG TickCount64; // [rsp+88h] [rbp-78h] BYREF
  int v75; // [rsp+90h] [rbp-70h]
  void *v76; // [rsp+98h] [rbp-68h] BYREF
  __int64 v77; // [rsp+A0h] [rbp-60h]
  void *v78[2]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v79[4]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v80; // [rsp+D0h] [rbp-30h]
  __int64 v81; // [rsp+D8h] [rbp-28h] BYREF
  int v82; // [rsp+E0h] [rbp-20h]
  unsigned int v86; // [rsp+158h] [rbp+58h] BYREF

  v6 = a4;
  v75 = 21;
  TickCount64 = GetTickCount64();
  utl::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>>>::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>>>(
    &v71,
    v7,
    v8);
  utl::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>>>::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>>>(
    &Src,
    v9,
    v10);
  utl::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>>>::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>>>(
    &Block,
    v11,
    v12);
  utl::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>>>::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>>>(
    &v76,
    v13,
    v14);
  v16 = 0xCCCCCCCCCCCCCCCDuLL * ((v70 - (_BYTE *)Src) >> 3);
  if ( v6 > v16 )
  {
    v17 = 7 * (v16 >> 2);
    v18 = (unsigned int)v6;
    v19 = v17 + 8;
    if ( v19 >= (unsigned int)v6 )
      v18 = v19;
    if ( v18 > 0x333333333333333LL )
      v18 = 0x333333333333333LL;
    if ( (unsigned int)v6 > v18
      || (v20 = 40 * v18,
          v21 = (char *)operator new(40 * v18, (const struct std::nothrow_t *)&std::nothrow),
          v22 = v21,
          (unsigned __int64)(v21 - 1) > 0xFFFFFFFFFFFFFFFDuLL) )
    {
      v52 = 1633;
LABEL_48:
      Log_UnistoreHREvent_0(
        2147942414LL,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
        v52);
      utl::vector<tlx::auto_ptr<DPBuffer,&void tlx::_delete<DPBuffer>(DPBuffer *)>,utl::allocator<tlx::auto_ptr<DPBuffer,&void tlx::_delete<DPBuffer>(DPBuffer *)>>>::_Uninit(&v76);
      utl::vector<AppRevisionRecord,utl::allocator<AppRevisionRecord>>::_Uninit(&Block);
      utl::vector<AppRevisionRecord,utl::allocator<AppRevisionRecord>>::_Uninit(&Src);
      utl::vector<AppRevisionRecord,utl::allocator<AppRevisionRecord>>::_Uninit(&v71);
      PerfAutoStartStopTimeCounter::~PerfAutoStartStopTimeCounter((PerfAutoStartStopTimeCounter *)&TickCount64);
      return 2147942414LL;
    }
    v23 = &v21[v20];
    memcpy_0(v21, Src, 8 * ((v69 - (_BYTE *)Src) >> 3));
    v24 = &v22[8 * ((v69 - (_BYTE *)Src) >> 3)];
    if ( Src != (void *)-1LL )
    {
      v69 = (char *)Src;
      operator delete(Src);
    }
    Src = v22;
    v69 = v24;
    v70 = v23;
  }
  v25 = (v67 - (_BYTE *)Block) >> 2;
  if ( (unsigned int)v6 <= v25 )
    goto LABEL_21;
  v26 = 7 * (v25 >> 2);
  v27 = (unsigned int)v6;
  v28 = v26 + 8;
  if ( v28 >= (unsigned int)v6 )
    v27 = v28;
  if ( v27 > 0x1FFFFFFFFFFFFFFFLL )
    v27 = 0x1FFFFFFFFFFFFFFFLL;
  if ( (unsigned int)v6 > v27
    || (v29 = 4 * v27,
        v30 = (char *)operator new(4 * v27, (const struct std::nothrow_t *)&std::nothrow),
        v31 = v30,
        (unsigned __int64)(v30 - 1) > 0xFFFFFFFFFFFFFFFDuLL) )
  {
    v52 = 1634;
    goto LABEL_48;
  }
  v32 = &v30[v29];
  memcpy_0(v30, Block, (v66 - (_BYTE *)Block) & 0xFFFFFFFFFFFFFFFCuLL);
  v33 = &v31[4 * ((v66 - (_BYTE *)Block) >> 2)];
  if ( Block != (void *)-1LL )
  {
    v66 = (char *)Block;
    operator delete(Block);
  }
  Block = v31;
  v66 = v33;
  v67 = v32;
LABEL_21:
  v34 = 0;
  v35 = a5;
  while ( v34 < (unsigned int)v6 )
  {
    v80 = 0;
    v81 = 0;
    v82 = 0;
    *(_OWORD *)v78 = 0;
    *(_OWORD *)v79 = 0;
    v36 = (DPHelper *)(3LL * v34);
    v37 = *((_DWORD *)v35 + 6 * v34);
    v86 = v37;
    if ( a3 && (unsigned int)DPHelper::DoesPropertyRequireProtection((DPHelper *)v37, v15) )
    {
      ProtectedPropIdByOrgPropId = DPHelper::GetProtectedPropIdByOrgPropId(v36, (unsigned int)&v86, v56);
      v58 = ProtectedPropIdByOrgPropId;
      if ( ProtectedPropIdByOrgPropId < 0 )
      {
        Log_UnistoreHREvent_0(
          (unsigned int)ProtectedPropIdByOrgPropId,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
          1649);
        utl::vector<tlx::auto_ptr<DPBuffer,&void tlx::_delete<DPBuffer>(DPBuffer *)>,utl::allocator<tlx::auto_ptr<DPBuffer,&void tlx::_delete<DPBuffer>(DPBuffer *)>>>::_Uninit(&v76);
        utl::vector<AppRevisionRecord,utl::allocator<AppRevisionRecord>>::_Uninit(&Block);
        utl::vector<AppRevisionRecord,utl::allocator<AppRevisionRecord>>::_Uninit(&Src);
        utl::vector<AppRevisionRecord,utl::allocator<AppRevisionRecord>>::_Uninit(&v71);
        PerfAutoStartStopTimeCounter::~PerfAutoStartStopTimeCounter((PerfAutoStartStopTimeCounter *)&TickCount64);
        return v58;
      }
      v37 = v86;
      v38 = 1;
      if ( (_WORD)v86 != 65 )
        Log_AssertionEvent(
          v36,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
          1650);
    }
    else
    {
      v38 = 0;
    }
    v86 = 0;
    v39 = ColumnIdMappings::PropIdToColumnId(v36, *(unsigned int *)a1, v37, 0, 1, &v81, &v86);
    v40 = v39;
    if ( v39 < 0 )
    {
      Log_UnistoreHREvent_0(
        (unsigned int)v39,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
        1298);
      Log_UnistoreHREvent_0(
        v40,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
        1653);
      v54 = v76;
      if ( v76 != (void *)-1LL )
      {
        utl::_RangeDestroyApc<utl::allocator<tlx::auto_ptr<DPBuffer,&void tlx::_delete<DPBuffer>(DPBuffer *)>>>(
          v53,
          (__int64)v76,
          (v77 - (__int64)v76) >> 3);
        operator delete(v54);
      }
      if ( Block != (void *)-1LL )
      {
        v66 = (char *)Block;
        operator delete(Block);
      }
      if ( Src != (void *)-1LL )
      {
        v69 = (char *)Src;
        operator delete(Src);
      }
      if ( v71 != (void *)-1LL )
      {
        v72 = v71;
        operator delete(v71);
      }
      PerfAutoStartStopTimeCounter::~PerfAutoStartStopTimeCounter((PerfAutoStartStopTimeCounter *)&TickCount64);
      return v40;
    }
    if ( v38 )
    {
      ProtectedDataFromUSPropVal = GetProtectedDataFromUSPropVal(a3, v79);
      v60 = ProtectedDataFromUSPropVal;
      if ( ProtectedDataFromUSPropVal < 0 )
      {
        Log_UnistoreHREvent_0(
          (unsigned int)ProtectedDataFromUSPropVal,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
          1659);
        utl::vector<tlx::auto_ptr<DPBuffer,&void tlx::_delete<DPBuffer>(DPBuffer *)>,utl::allocator<tlx::auto_ptr<DPBuffer,&void tlx::_delete<DPBuffer>(DPBuffer *)>>>::_Uninit(&v76);
        utl::vector<AppRevisionRecord,utl::allocator<AppRevisionRecord>>::_Uninit(&Block);
        utl::vector<AppRevisionRecord,utl::allocator<AppRevisionRecord>>::_Uninit(&Src);
        utl::vector<AppRevisionRecord,utl::allocator<AppRevisionRecord>>::_Uninit(&v71);
        PerfAutoStartStopTimeCounter::~PerfAutoStartStopTimeCounter((PerfAutoStartStopTimeCounter *)&TickCount64);
        return v60;
      }
    }
    else
    {
      DataFromUSPropVal = GetDataFromUSPropVal(
                            (struct _USPROPVAL *)((char *)v35 + 24 * v34),
                            (const void **)&v78[1],
                            v79);
      v42 = DataFromUSPropVal;
      if ( DataFromUSPropVal < 0 )
      {
        Log_UnistoreHREvent_0(
          (unsigned int)DataFromUSPropVal,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
          1663);
        utl::vector<tlx::auto_ptr<DPBuffer,&void tlx::_delete<DPBuffer>(DPBuffer *)>,utl::allocator<tlx::auto_ptr<DPBuffer,&void tlx::_delete<DPBuffer>(DPBuffer *)>>>::_Uninit(&v76);
        utl::vector<AppRevisionRecord,utl::allocator<AppRevisionRecord>>::_Uninit(&Block);
        utl::vector<AppRevisionRecord,utl::allocator<AppRevisionRecord>>::_Uninit(&Src);
        utl::vector<AppRevisionRecord,utl::allocator<AppRevisionRecord>>::_Uninit(&v71);
        PerfAutoStartStopTimeCounter::~PerfAutoStartStopTimeCounter((PerfAutoStartStopTimeCounter *)&TickCount64);
        return v42;
      }
    }
    if ( (v81 & 0x40000000000LL) != 0 && v78[1] )
    {
      v79[3] = 0;
      v79[1] = 128;
    }
    else
    {
      v79[3] = 1;
    }
    LODWORD(v78[0]) = v81;
    if ( (v81 & 0x80000000000LL) != 0 )
    {
      v55 = v72;
      if ( v72 == v73 )
      {
        if ( !(unsigned __int8)utl::vector<JET_SETCOLUMN,utl::allocator<JET_SETCOLUMN>>::_PushBackOne2<JET_SETCOLUMN const &>(
                                 &v71,
                                 v78) )
        {
          v52 = 1681;
          goto LABEL_48;
        }
      }
      else
      {
        v61 = *(_OWORD *)v79;
        *v72 = *(_OWORD *)v78;
        v62 = v80;
        v55[1] = v61;
        *((_QWORD *)v55 + 4) = v62;
        v72 = (_OWORD *)((char *)v72 + 40);
      }
    }
    else
    {
      v43 = v69;
      if ( v69 == v70 )
      {
        if ( !(unsigned __int8)utl::vector<JET_SETCOLUMN,utl::allocator<JET_SETCOLUMN>>::_PushBackOne2<JET_SETCOLUMN const &>(
                                 &Src,
                                 v78) )
        {
          v52 = 1685;
          goto LABEL_48;
        }
      }
      else
      {
        v44 = *(_OWORD *)v79;
        *(_OWORD *)v69 = *(_OWORD *)v78;
        v45 = v80;
        *((_OWORD *)v43 + 1) = v44;
        *((_QWORD *)v43 + 4) = v45;
        v69 += 40;
      }
      v86 = v34;
      if ( v66 == v67 )
      {
        if ( !(unsigned __int8)utl::vector<unsigned long,utl::allocator<unsigned long>>::_PushBackOne2<unsigned long>(
                                 &Block,
                                 &v86) )
        {
          v52 = 1686;
          goto LABEL_48;
        }
      }
      else
      {
        *(_DWORD *)v66 = v34;
        v66 += 4;
      }
    }
    ++v34;
  }
  v46 = ESEWriteRecordPropData(a1, a2, &Src, &v71, &Block, v6, a6);
  v48 = v46;
  if ( v46 < 0 )
  {
    Log_UnistoreHREvent_0(
      (unsigned int)v46,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
      1697);
    utl::vector<tlx::auto_ptr<DPBuffer,&void tlx::_delete<DPBuffer>(DPBuffer *)>,utl::allocator<tlx::auto_ptr<DPBuffer,&void tlx::_delete<DPBuffer>(DPBuffer *)>>>::_Uninit(&v76);
    utl::vector<AppRevisionRecord,utl::allocator<AppRevisionRecord>>::_Uninit(&Block);
    utl::vector<AppRevisionRecord,utl::allocator<AppRevisionRecord>>::_Uninit(&Src);
    utl::vector<AppRevisionRecord,utl::allocator<AppRevisionRecord>>::_Uninit(&v71);
    PerfAutoStartStopTimeCounter::~PerfAutoStartStopTimeCounter((PerfAutoStartStopTimeCounter *)&TickCount64);
    return v48;
  }
  else
  {
    v49 = v76;
    if ( v76 != (void *)-1LL )
    {
      utl::_RangeDestroyApc<utl::allocator<tlx::auto_ptr<DPBuffer,&void tlx::_delete<DPBuffer>(DPBuffer *)>>>(
        v47,
        (__int64)v76,
        (v77 - (__int64)v76) >> 3);
      operator delete(v49);
    }
    if ( Block != (void *)-1LL )
    {
      v66 = (char *)Block;
      operator delete(Block);
    }
    if ( Src != (void *)-1LL )
    {
      v69 = (char *)Src;
      operator delete(Src);
    }
    if ( v71 != (void *)-1LL )
    {
      v72 = v71;
      operator delete(v71);
    }
    v50 = GetTickCount64();
    if ( g_perfStatEnabled )
    {
      v63 = v50 - TickCount64;
      _InterlockedIncrement(&dword_18010DB04);
      _InterlockedAdd(&dword_18010DAFC, v50 - TickCount64);
      do
        v64 = dword_18010DB00;
      while ( dword_18010DB00 < v63 && v64 != _InterlockedCompareExchange(&dword_18010DB00, v63, dword_18010DB00) );
    }
    return 0;
  }
}

```

## disassembly

```asm
0x18002ac20  mov     [rsp-8+arg_10], r8
0x18002ac25  mov     [rsp-8+arg_8], rdx
0x18002ac2a  mov     [rsp-8+arg_0], rcx
0x18002ac2f  push    rbp
0x18002ac30  push    rbx
0x18002ac31  push    rsi
0x18002ac32  push    rdi
0x18002ac33  push    r14
0x18002ac35  push    r15
0x18002ac37  lea     rbp, [rsp-8]
0x18002ac3c  sub     rsp, 108h
0x18002ac43  mov     esi, r9d
0x18002ac46  mov     [rbp+30h+var_A0], 15h
0x18002ac4d  call    cs:__imp_GetTickCount64
0x18002ac53  lea     rcx, [rsp+130h+var_C0]
0x18002ac58  mov     [rbp+30h+var_A8], rax
0x18002ac5c  call    ??0?$vector@V?$auto_xxx@PEAU_USPROPVAL@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@V?$allocator@V?$auto_xxx@PEAU_USPROPVAL@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@utl@@@utl@@QEAA@XZ; utl::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>>>::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>>>(void)
0x18002ac61  lea     rcx, [rsp+130h+Src]
0x18002ac66  call    ??0?$vector@V?$auto_xxx@PEAU_USPROPVAL@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@V?$allocator@V?$auto_xxx@PEAU_USPROPVAL@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@utl@@@utl@@QEAA@XZ; utl::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>>>::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>>>(void)
0x18002ac6b  lea     rcx, [rsp+130h+Block]
0x18002ac70  call    ??0?$vector@V?$auto_xxx@PEAU_USPROPVAL@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@V?$allocator@V?$auto_xxx@PEAU_USPROPVAL@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@utl@@@utl@@QEAA@XZ; utl::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>>>::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>>>(void)
0x18002ac75  lea     rcx, [rbp+30h+var_98]
0x18002ac79  call    ??0?$vector@V?$auto_xxx@PEAU_USPROPVAL@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@V?$allocator@V?$auto_xxx@PEAU_USPROPVAL@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@utl@@@utl@@QEAA@XZ; utl::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>>>::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>>>(void)
0x18002ac7e  mov     rcx, [rsp+130h+var_C8]
0x18002ac83  mov     r15, 0CCCCCCCCCCCCCCCDh
0x18002ac8d  sub     rcx, [rsp+130h+Src]
0x18002ac92  mov     ebx, esi
0x18002ac94  sar     rcx, 3
0x18002ac98  imul    rcx, r15
0x18002ac9c  cmp     rsi, rcx
0x18002ac9f  jbe     loc_18002AD7E
0x18002aca5  shr     rcx, 2
0x18002aca9  imul    rax, rcx, 7
0x18002acad  mov     ecx, ebx
0x18002acaf  add     rax, 8
0x18002acb3  cmp     rax, rbx
0x18002acb6  cmovnb  rcx, rax
0x18002acba  mov     rax, 333333333333333h
0x18002acc4  cmp     rcx, rax
0x18002acc7  cmova   rcx, rax
0x18002accb  cmp     rbx, rcx
0x18002acce  ja      loc_18002B061
0x18002acd4  mov     rax, 666666666666666h
0x18002acde  cmp     rcx, rax
0x18002ace1  ja      loc_18002B061
0x18002ace7  lea     rax, [rcx+rcx*4]
0x18002aceb  lea     r14, ds:0[rax*8]
0x18002acf3  mov     rcx, r14; unsigned __int64
0x18002acf6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002acfd  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002ad02  mov     rdi, rax
0x18002ad05  lea     rcx, [rax-1]
0x18002ad09  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18002ad0d  ja      loc_18002B061
0x18002ad13  mov     rcx, [rsp+130h+var_D0]
0x18002ad18  add     r14, rax
0x18002ad1b  mov     rdx, [rsp+130h+Src]; Src
0x18002ad20  sub     rcx, rdx
0x18002ad23  sar     rcx, 3
0x18002ad27  imul    rcx, r15
0x18002ad2b  lea     r8, [rcx+rcx*4]
0x18002ad2f  mov     rcx, rax; void *
0x18002ad32  shl     r8, 3; Size
0x18002ad36  call    memcpy_0
0x18002ad3b  mov     rcx, [rsp+130h+Src]; Block
0x18002ad40  mov     rax, [rsp+130h+var_D0]
0x18002ad45  sub     rax, rcx
0x18002ad48  sar     rax, 3
0x18002ad4c  imul    rax, r15
0x18002ad50  lea     rax, [rax+rax*4]
0x18002ad54  lea     r15, [rdi+rax*8]
0x18002ad58  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18002ad5c  jz      short loc_18002AD6F
0x18002ad5e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18002ad65  mov     [rsp+130h+var_D0], rcx
0x18002ad6a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002ad6f  mov     [rsp+130h+Src], rdi
0x18002ad74  mov     [rsp+130h+var_D0], r15
0x18002ad79  mov     [rsp+130h+var_C8], r14
0x18002ad7e  mov     rax, [rsp+130h+var_E0]
0x18002ad83  sub     rax, [rsp+130h+Block]
0x18002ad88  sar     rax, 2
0x18002ad8c  cmp     rbx, rax
0x18002ad8f  jbe     loc_18002AE57
0x18002ad95  shr     rax, 2
0x18002ad99  imul    rcx, rax, 7
0x18002ad9d  mov     rax, rbx
0x18002ada0  add     rcx, 8
0x18002ada4  cmp     rcx, rbx
0x18002ada7  cmovnb  rax, rcx
0x18002adab  mov     rcx, 1FFFFFFFFFFFFFFFh
0x18002adb5  cmp     rax, rcx
0x18002adb8  cmova   rax, rcx
0x18002adbc  cmp     rbx, rax
0x18002adbf  ja      loc_18002B0BF
0x18002adc5  mov     rcx, 3FFFFFFFFFFFFFFFh
0x18002adcf  cmp     rax, rcx
0x18002add2  ja      loc_18002B0BF
0x18002add8  lea     rdi, ds:0[rax*4]
0x18002ade0  mov     rcx, rdi; unsigned __int64
0x18002ade3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002adea  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002adef  mov     rbx, rax
0x18002adf2  lea     rcx, [rax-1]
0x18002adf6  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18002adfa  ja      loc_18002B0BF
0x18002ae00  mov     r8, [rsp+130h+var_E8]
0x18002ae05  mov     rcx, rax; void *
0x18002ae08  mov     rdx, [rsp+130h+Block]; Src
0x18002ae0d  add     rdi, rax
0x18002ae10  sub     r8, rdx
0x18002ae13  and     r8, 0FFFFFFFFFFFFFFFCh; Size
0x18002ae17  call    memcpy_0
0x18002ae1c  mov     rcx, [rsp+130h+Block]; Block
0x18002ae21  mov     rax, [rsp+130h+var_E8]
0x18002ae26  sub     rax, rcx
0x18002ae29  sar     rax, 2
0x18002ae2d  lea     r14, [rbx+rax*4]
0x18002ae31  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18002ae35  jz      short loc_18002AE48
0x18002ae37  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18002ae3e  mov     [rsp+130h+var_E8], rcx
0x18002ae43  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002ae48  mov     [rsp+130h+Block], rbx
0x18002ae4d  mov     [rsp+130h+var_E8], r14
0x18002ae52  mov     [rsp+130h+var_E0], rdi
0x18002ae57  mov     [rsp+130h+var_38], r13
0x18002ae5f  xor     edi, edi
0x18002ae61  mov     r13, [rbp+30h+arg_20]
0x18002ae65  mov     [rsp+130h+var_30], r12
0x18002ae6d  movzx   ebx, di
0x18002ae70  cmp     ebx, esi
0x18002ae72  jnb     loc_18002AF8E
0x18002ae78  xor     eax, eax
0x18002ae7a  xorps   xmm0, xmm0
0x18002ae7d  mov     [rbp+30h+var_60], rax
0x18002ae81  mov     [rbp+30h+var_58], rax
0x18002ae85  mov     [rbp+30h+var_50], eax
0x18002ae88  movzx   eax, di
0x18002ae8b  movups  xmmword ptr [rbp+30h+var_80], xmm0
0x18002ae8f  movups  xmmword ptr [rbp+30h+var_70], xmm0
0x18002ae93  lea     rcx, [rax+rax*2]
0x18002ae97  lea     r15, ds:0[rcx*8]
0x18002ae9f  add     r15, r13
0x18002aea2  cmp     [rbp+30h+arg_10], 0
0x18002aea7  mov     r12d, [r15]
0x18002aeaa  mov     [rbp+30h+arg_18], r12d
0x18002aeae  jnz     loc_18002B207
0x18002aeb4  xor     r14d, r14d
0x18002aeb7  lea     rax, [rbp+30h+arg_18]
0x18002aebb  mov     [rbp+30h+arg_18], 0
0x18002aec2  mov     [rsp+130h+var_100], rax
0x18002aec7  xor     r9d, r9d
0x18002aeca  lea     rax, [rbp+30h+var_58]
0x18002aece  mov     r8d, r12d
0x18002aed1  mov     qword ptr [rsp+130h+var_108], rax
0x18002aed6  mov     rax, [rbp+30h+arg_0]
0x18002aeda  mov     dword ptr [rsp+130h+var_110], 1
0x18002aee2  mov     edx, [rax]
0x18002aee4  call    ?PropIdToColumnId@ColumnIdMappings@@QEAAJW4US_TABLEID@@KKHPEAUColumnDetails@@PEAH@Z; ColumnIdMappings::PropIdToColumnId(US_TABLEID,ulong,ulong,int,ColumnDetails *,int *)
0x18002aee9  mov     r12d, eax
0x18002aeec  test    eax, eax
0x18002aeee  js      loc_18002B130
0x18002aef4  test    r14d, r14d
0x18002aef7  jnz     loc_18002B257
0x18002aefd  lea     r8, [rbp+30h+var_70]; unsigned int *
0x18002af01  mov     rcx, r15; struct _USPROPVAL *
0x18002af04  lea     rdx, [rbp+30h+var_80+8]; void **
0x18002af08  call    ?GetDataFromUSPropVal@@YAJPEBU_USPROPVAL@@PEAPEBXPEAK@Z; GetDataFromUSPropVal(_USPROPVAL const *,void const * *,ulong *)
0x18002af0d  mov     r14d, eax
0x18002af10  test    eax, eax
0x18002af12  js      loc_18002B385
0x18002af18  mov     ecx, dword ptr [rbp+30h+var_58+4]
0x18002af1b  bt      ecx, 0Ah
0x18002af1f  jb      loc_18002B2D0
0x18002af25  mov     [rbp+30h+var_70+0Ch], 1
0x18002af2c  mov     eax, dword ptr [rbp+30h+var_58]
0x18002af2f  mov     dword ptr [rbp+30h+var_80], eax
0x18002af32  bt      ecx, 0Bh
0x18002af36  jb      loc_18002B1D7
0x18002af3c  mov     rax, [rsp+130h+var_D0]
0x18002af41  cmp     rax, [rsp+130h+var_C8]
0x18002af46  jz      loc_18002B0C7
0x18002af4c  movups  xmm0, xmmword ptr [rbp+30h+var_80]
0x18002af50  movups  xmm1, xmmword ptr [rbp+30h+var_70]
0x18002af54  movups  xmmword ptr [rax], xmm0
0x18002af57  movsd   xmm0, [rbp+30h+var_60]
0x18002af5c  movups  xmmword ptr [rax+10h], xmm1
0x18002af60  movsd   qword ptr [rax+20h], xmm0
0x18002af65  add     [rsp+130h+var_D0], 28h ; '('
0x18002af6b  mov     rax, [rsp+130h+var_E8]
0x18002af70  mov     [rbp+30h+arg_18], ebx
0x18002af73  cmp     rax, [rsp+130h+var_E0]
0x18002af78  jz      loc_18002B312
0x18002af7e  mov     [rax], ebx
0x18002af80  add     [rsp+130h+var_E8], 4
0x18002af86  inc     di
0x18002af89  jmp     loc_18002AE6D
0x18002af8e  mov     rax, [rbp+30h+arg_28]
0x18002af92  lea     r9, [rsp+130h+var_C0]
0x18002af97  mov     rdx, [rbp+30h+arg_8]; this
0x18002af9b  lea     r8, [rsp+130h+Src]
0x18002afa0  mov     rcx, [rbp+30h+arg_0]; struct TableHandleInfo *
0x18002afa4  mov     [rsp+130h+var_100], rax; __int64
0x18002afa9  lea     rax, [rsp+130h+Block]
0x18002afae  mov     [rsp+130h+var_108], esi; int
0x18002afb2  mov     [rsp+130h+var_110], rax; __int64
0x18002afb7  call    ?ESEWriteRecordPropData@@YAJPEAUTableHandleInfo@@AEAVUnifiedStoreCursorLocation@@AEAV?$vector@UJET_SETCOLUMN@@V?$allocator@UJET_SETCOLUMN@@@utl@@@utl@@2AEBV?$vector@KV?$allocator@K@utl@@@4@KPEAK@Z; ESEWriteRecordPropData(TableHandleInfo *,UnifiedStoreCursorLocation &,utl::vector<JET_SETCOLUMN,utl::allocator<JET_SETCOLUMN>> &,utl::vector<JET_SETCOLUMN,utl::allocator<JET_SETCOLUMN>> &,utl::vector<ulong,utl::allocator<ulong>> const &,ulong,ulong *)
0x18002afbc  mov     ebx, eax
0x18002afbe  test    eax, eax
0x18002afc0  js      loc_18002B3FE
0x18002afc6  mov     rbx, [rbp+30h+var_98]
0x18002afca  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18002afce  jnz     loc_18002B44E
0x18002afd4  mov     rcx, [rsp+130h+Block]; Block
0x18002afd9  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18002afdd  jz      short loc_18002AFF0
0x18002afdf  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18002afe6  mov     [rsp+130h+var_E8], rcx
0x18002afeb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002aff0  mov     rcx, [rsp+130h+Src]; Block
0x18002aff5  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18002aff9  jz      short loc_18002B00C
0x18002affb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18002b002  mov     [rsp+130h+var_D0], rcx
0x18002b007  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002b00c  mov     rcx, [rsp+130h+var_C0]; Block
0x18002b011  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18002b015  jz      short loc_18002B028
0x18002b017  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18002b01e  mov     [rsp+130h+var_B8], rcx
0x18002b023  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002b028  call    cs:__imp_GetTickCount64
0x18002b02e  mov     ecx, cs:?g_perfStatEnabled@@3KC; ulong volatile g_perfStatEnabled
0x18002b034  mov     rdx, rax
0x18002b037  test    ecx, ecx
0x18002b039  jnz     loc_18002B475
0x18002b03f  xor     eax, eax
0x18002b041  mov     r12, [rsp+130h+var_30]
0x18002b049  mov     r13, [rsp+130h+var_38]
0x18002b051  add     rsp, 108h
0x18002b058  pop     r15
0x18002b05a  pop     r14
0x18002b05c  pop     rdi
0x18002b05d  pop     rsi
0x18002b05e  pop     rbx
0x18002b05f  pop     rbp
0x18002b060  retn
0x18002b061  mov     r9d, 661h
0x18002b067  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18002b06e  xor     edx, edx
0x18002b070  mov     ecx, 8007000Eh
0x18002b075  call    Log_UnistoreHREvent_0
0x18002b07a  lea     rcx, [rbp+30h+var_98]
0x18002b07e  call    ?_Uninit@?$vector@V?$auto_ptr@VDPBuffer@@$1??$_delete@VDPBuffer@@@tlx@@YAXPEAV1@@Z@tlx@@V?$allocator@V?$auto_ptr@VDPBuffer@@$1??$_delete@VDPBuffer@@@tlx@@YAXPEAV1@@Z@tlx@@@utl@@@utl@@AEAAXXZ; utl::vector<tlx::auto_ptr<DPBuffer,&tlx::_delete<DPBuffer>(DPBuffer *)>,utl::allocator<tlx::auto_ptr<DPBuffer,&tlx::_delete<DPBuffer>(DPBuffer *)>>>::_Uninit(void)
0x18002b083  lea     rcx, [rsp+130h+Block]
0x18002b088  call    ?_Uninit@?$vector@UAppRevisionRecord@@V?$allocator@UAppRevisionRecord@@@utl@@@utl@@AEAAXXZ; utl::vector<AppRevisionRecord,utl::allocator<AppRevisionRecord>>::_Uninit(void)
0x18002b08d  lea     rcx, [rsp+130h+Src]
0x18002b092  call    ?_Uninit@?$vector@UAppRevisionRecord@@V?$allocator@UAppRevisionRecord@@@utl@@@utl@@AEAAXXZ; utl::vector<AppRevisionRecord,utl::allocator<AppRevisionRecord>>::_Uninit(void)
0x18002b097  lea     rcx, [rsp+130h+var_C0]
0x18002b09c  call    ?_Uninit@?$vector@UAppRevisionRecord@@V?$allocator@UAppRevisionRecord@@@utl@@@utl@@AEAAXXZ; utl::vector<AppRevisionRecord,utl::allocator<AppRevisionRecord>>::_Uninit(void)
0x18002b0a1  lea     rcx, [rbp+30h+var_A8]; this
0x18002b0a5  call    ??1PerfAutoStartStopTimeCounter@@QEAA@XZ; PerfAutoStartStopTimeCounter::~PerfAutoStartStopTimeCounter(void)
0x18002b0aa  mov     eax, 8007000Eh
0x18002b0af  add     rsp, 108h
0x18002b0b6  pop     r15
0x18002b0b8  pop     r14
0x18002b0ba  pop     rdi
0x18002b0bb  pop     rsi
0x18002b0bc  pop     rbx
0x18002b0bd  pop     rbp
0x18002b0be  retn
0x18002b0bf  mov     r9d, 662h
0x18002b0c5  jmp     short loc_18002B067
0x18002b0c7  lea     rdx, [rbp+30h+var_80]
0x18002b0cb  lea     rcx, [rsp+130h+Src]
0x18002b0d0  call    ??$_PushBackOne2@AEBUJET_SETCOLUMN@@@?$vector@UJET_SETCOLUMN@@V?$allocator@UJET_SETCOLUMN@@@utl@@@utl@@AEAA_NAEBUJET_SETCOLUMN@@@Z; utl::vector<JET_SETCOLUMN,utl::allocator<JET_SETCOLUMN>>::_PushBackOne2<JET_SETCOLUMN const &>(JET_SETCOLUMN const &)
0x18002b0d5  test    al, al
0x18002b0d7  jnz     loc_18002AF6B
0x18002b0dd  mov     r9d, 695h
0x18002b0e3  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18002b0ea  xor     edx, edx
0x18002b0ec  mov     ecx, 8007000Eh
0x18002b0f1  call    Log_UnistoreHREvent_0
0x18002b0f6  lea     rcx, [rbp+30h+var_98]
0x18002b0fa  call    ?_Uninit@?$vector@V?$auto_ptr@VDPBuffer@@$1??$_delete@VDPBuffer@@@tlx@@YAXPEAV1@@Z@tlx@@V?$allocator@V?$auto_ptr@VDPBuffer@@$1??$_delete@VDPBuffer@@@tlx@@YAXPEAV1@@Z@tlx@@@utl@@@utl@@AEAAXXZ; utl::vector<tlx::auto_ptr<DPBuffer,&tlx::_delete<DPBuffer>(DPBuffer *)>,utl::allocator<tlx::auto_ptr<DPBuffer,&tlx::_delete<DPBuffer>(DPBuffer *)>>>::_Uninit(void)
0x18002b0ff  lea     rcx, [rsp+130h+Block]
0x18002b104  call    ?_Uninit@?$vector@UAppRevisionRecord@@V?$allocator@UAppRevisionRecord@@@utl@@@utl@@AEAAXXZ; utl::vector<AppRevisionRecord,utl::allocator<AppRevisionRecord>>::_Uninit(void)
0x18002b109  lea     rcx, [rsp+130h+Src]
0x18002b10e  call    ?_Uninit@?$vector@UAppRevisionRecord@@V?$allocator@UAppRevisionRecord@@@utl@@@utl@@AEAAXXZ; utl::vector<AppRevisionRecord,utl::allocator<AppRevisionRecord>>::_Uninit(void)
0x18002b113  lea     rcx, [rsp+130h+var_C0]
0x18002b118  call    ?_Uninit@?$vector@UAppRevisionRecord@@V?$allocator@UAppRevisionRecord@@@utl@@@utl@@AEAAXXZ; utl::vector<AppRevisionRecord,utl::allocator<AppRevisionRecord>>::_Uninit(void)
0x18002b11d  lea     rcx, [rbp+30h+var_A8]; this
0x18002b121  call    ??1PerfAutoStartStopTimeCounter@@QEAA@XZ; PerfAutoStartStopTimeCounter::~PerfAutoStartStopTimeCounter(void)
0x18002b126  mov     eax, 8007000Eh
0x18002b12b  jmp     loc_18002B041
0x18002b130  mov     r9d, 512h
0x18002b136  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18002b13d  mov     edx, 1
0x18002b142  mov     ecx, r12d
  ... truncated ...
```
