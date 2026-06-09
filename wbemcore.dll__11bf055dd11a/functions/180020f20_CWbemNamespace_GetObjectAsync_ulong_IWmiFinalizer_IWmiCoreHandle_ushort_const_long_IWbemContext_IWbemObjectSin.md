# CWbemNamespace::_GetObjectAsync(ulong,_IWmiFinalizer *,_IWmiCoreHandle *,ushort * const,long,IWbemContext *,IWbemObjectSink *)

- ea: `0x180020f20`
- end: `0x180021517`
- name: `?_GetObjectAsync@CWbemNamespace@@MEAAJKPEAU_IWmiFinalizer@@PEAU_IWmiCoreHandle@@QEAGJPEAUIWbemContext@@PEAUIWbemObjectSink@@@Z`
- size: `1527`
- prototype: `__int64 __fastcall(CWbemNamespace *this, unsigned int, struct _IWmiFinalizer *, struct _IWmiCoreHandle *, unsigned __int16 *const, int, struct IWbemContext *, struct IWbemObjectSink *)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001e9a0`
- `0x180071000`

## callees

- `0x18000ae2c`
- `0x18000b140`
- `0x18000f474`
- `0x180020f20`
- `0x18003cfe0`
- `0x180041d00`
- `0x1800421ac`
- `0x180047ed0`
- `0x1800523c0`
- `0x180062ed0`
- `0x1800903d0`
- `0x1800a093c`
- `0x1800da010`

## import_xrefs

- `wbemcomn!??0WString@@QEAA@PEAGH@Z` at `0x18002130a`
- `wbemcomn!??0WString@@QEAA@PEAGH@Z` at `0x18002130a`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800212ca`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800212ca`
- `wbemcomn!GetMemLogObject` at `0x180020f56`
- `wbemcomn!GetMemLogObject` at `0x180021007`
- `wbemcomn!GetMemLogObject` at `0x180021043`
- `wbemcomn!GetMemLogObject` at `0x1800210c3`
- `wbemcomn!GetMemLogObject` at `0x180021123`
- `wbemcomn!GetMemLogObject` at `0x1800211a2`
- `wbemcomn!GetMemLogObject` at `0x180021263`
- `wbemcomn!GetMemLogObject` at `0x180021338`
- `wbemcomn!GetMemLogObject` at `0x18002139f`
- `wbemcomn!GetMemLogObject` at `0x180021425`
- `wbemcomn!GetMemLogObject` at `0x180021487`
- `wbemcomn!GetMemLogObject` at `0x180020f56`
- `wbemcomn!GetMemLogObject` at `0x180021007`
- `wbemcomn!GetMemLogObject` at `0x180021043`
- `wbemcomn!GetMemLogObject` at `0x1800210c3`
- `wbemcomn!GetMemLogObject` at `0x180021123`
- `wbemcomn!GetMemLogObject` at `0x1800211a2`
- `wbemcomn!GetMemLogObject` at `0x180021263`
- `wbemcomn!GetMemLogObject` at `0x180021338`
- `wbemcomn!GetMemLogObject` at `0x18002139f`
- `wbemcomn!GetMemLogObject` at `0x180021425`
- `wbemcomn!GetMemLogObject` at `0x180021487`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180020f61`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180021015`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180021051`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800210ce`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002112e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800211ad`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002126e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180021348`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800213ab`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180021430`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180021497`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180020f61`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180021015`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180021051`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800210ce`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002112e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800211ad`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002126e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180021348`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800213ab`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180021430`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180021497`

## string_xrefs

- `0x18002118d`: `IWbemServices::GetObject`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWbemNamespace::_GetObjectAsync(
        CWbemNamespace *this,
        unsigned int a2,
        struct _IWmiFinalizer *a3,
        struct _IWmiCoreHandle *a4,
        unsigned __int16 *const a5,
        int a6,
        struct IWbemContext *a7,
        struct IWbemObjectSink *a8)
{
  struct _IWmiFinalizer *v8; // r14
  int v10; // esi
  int v11; // r8d
  CMemoryLog *MemLogObject; // rax
  CClientCnt *v13; // rcx
  __int64 v14; // rdx
  struct IWbemObjectSink *v15; // r12
  int v16; // r13d
  CMemoryLog *v17; // rax
  CClientCnt *v18; // rcx
  __int64 v19; // rdx
  CMemoryLog *v20; // rax
  CMemoryLog *v22; // rax
  CMemoryLog *v23; // rax
  CMemoryLog *v24; // rax
  CClientCnt *v25; // rcx
  __int64 v26; // rdx
  const wchar_t *v27; // r8
  CMemoryLog *v28; // rax
  CNamespaceReq *v29; // rax
  CNamespaceReq *v30; // rsi
  struct IWbemContext *v31; // rax
  CMemoryLog *v32; // rax
  CClientCnt *v33; // rcx
  __int64 v34; // rdx
  int inited; // r15d
  CMemoryLog *v36; // rax
  CMemoryLog *v37; // rax
  __int64 v38; // r9
  CMemoryLog *v39; // rax
  struct IWbemObjectSink **v40; // [rsp+20h] [rbp-60h]
  struct IWbemObjectSink *v41; // [rsp+28h] [rbp-58h]
  __int64 v42; // [rsp+30h] [rbp-50h]
  CAsyncReq_GetObjectAsync *v43; // [rsp+40h] [rbp-40h] BYREF
  struct IWbemObjectSink *v44; // [rsp+48h] [rbp-38h] BYREF
  struct IWbemObjectSinkEx *v45; // [rsp+50h] [rbp-30h] BYREF
  struct IWbemObjectSinkEx *v46; // [rsp+58h] [rbp-28h] BYREF
  struct IWbemObjectSink *v47; // [rsp+60h] [rbp-20h] BYREF
  _QWORD v48[3]; // [rsp+68h] [rbp-18h] BYREF
  struct _IWmiFinalizer *v50; // [rsp+C0h] [rbp+40h] BYREF

  v50 = a3;
  v8 = a3;
  v10 = CWbemNamespace::CheckNs(this);
  if ( v10 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v10);
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)v10;
    }
    v14 = 684;
    goto LABEL_6;
  }
  v15 = a8;
  v16 = a6;
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_Sdql(*((_QWORD *)WPP_GLOBAL_Control + 2), 685, v11, (_DWORD)a5, a6, (char)a8, *((_DWORD *)this + 76));
  }
  if ( !v8 && !v15 )
  {
    v17 = GetMemLogObject();
    CMemoryLog::Write(v17, -2147217400);
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 2147749896LL;
    }
    v19 = 686;
LABEL_22:
    WPP_SF_d(*((_QWORD *)v18 + 2), v19, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749896LL);
    return 2147749896LL;
  }
  if ( (v16 & 0xFFFDFD7F) != 0 )
  {
    v20 = GetMemLogObject();
    CMemoryLog::Write(v20, -2147217400);
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 2147749896LL;
    }
    v19 = 687;
    goto LABEL_22;
  }
  v44 = 0;
  if ( !v8 )
  {
    v10 = CWbemNamespace::CreateAsyncFinalizer(this, a7, v15, &v50, &v44);
    if ( v10 < 0 )
    {
      v22 = GetMemLogObject();
      CMemoryLog::Write(v22, v10);
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return (unsigned int)v10;
      }
      v14 = 688;
      goto LABEL_6;
    }
    v8 = v50;
LABEL_37:
    v47 = v44;
    v48[0] = v8;
    v10 = CWbemNamespace::PublishInfo(this, L"IWbemServices::GetObject", a5, v8, a7);
    if ( v10 < 0 )
    {
      v24 = GetMemLogObject();
      CMemoryLog::Write(v24, v10);
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_85;
      }
      v26 = 690;
      goto LABEL_52;
    }
    if ( *((_DWORD *)this + 76) != -1 && g_cntWinmgmtTraceLogging )
    {
      v27 = L"Async";
      if ( !v15 )
        v27 = L"(Semi)Sync";
      LODWORD(v42) = *((_DWORD *)this + 76);
      LODWORD(v41) = *((_DWORD *)this + 95);
      LODWORD(v40) = v16;
      WinmgmtTelemetrylogging(*((_DWORD *)v8 + 181), 0, v27, a5, v40, v41, v42, *((_QWORD *)this + 11));
    }
    v45 = 0;
    v10 = ((__int64 (__fastcall *)(struct IWbemObjectSink *, GUID *, struct IWbemObjectSinkEx **))v44->lpVtbl->QueryInterface)(
            v44,
            &IID_IWbemObjectSinkEx,
            &v45);
    if ( v10 < 0 )
    {
      v28 = GetMemLogObject();
      CMemoryLog::Write(v28, v10);
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_85;
      }
      v26 = 691;
LABEL_52:
      WPP_SF_d(*((_QWORD *)v25 + 2), v26, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, (unsigned int)v10);
LABEL_85:
      CReleaseMe::release((CReleaseMe *)v48);
      CReleaseMe::release((CReleaseMe *)&v47);
      return (unsigned int)v10;
    }
    v46 = v45;
    v43 = 0;
    v29 = (CNamespaceReq *)CWin32DefaultArena::WbemMemAlloc(0x70u);
    v30 = v29;
    v48[1] = v29;
    if ( v29 )
    {
      CNamespaceReq::CNamespaceReq(v29, this, v45, a7, 0);
      *(_QWORD *)v30 = &CAsyncReq_GetObjectAsync::`vftable';
      WString::WString((CNamespaceReq *)((char *)v30 + 96), a5, 0);
      *((_DWORD *)v30 + 26) = v16;
    }
    else
    {
      v30 = 0;
    }
    if ( v30 )
    {
      std::unique_ptr<CAsyncReq_CreateClassEnumAsync>::_Delete(&v43);
      v43 = v30;
      v31 = (struct IWbemContext *)*((_QWORD *)v30 + 5);
      if ( v31 )
      {
        inited = CWbemNamespace::InitNewTask(this, v30, v8, a2, v31, v15);
        if ( inited < 0 )
        {
          v36 = GetMemLogObject();
          CMemoryLog::Write(v36, inited);
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              694,
              WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
              (unsigned int)inited);
          }
          std::unique_ptr<CAsyncReq_CreateClassEnumAsync>::_Delete(&v43);
          CReleaseMe::release((CReleaseMe *)&v46);
          v10 = inited;
          goto LABEL_85;
        }
        CReleaseMe::release((CReleaseMe *)&v47);
        v10 = ConfigMgr::EnqueueRequest(v30);
        if ( v10 >= 0 )
        {
          v43 = 0;
          v33 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_84;
          }
          v34 = 696;
        }
        else
        {
          (*(void (__fastcall **)(struct _IWmiFinalizer *, _QWORD))(*(_QWORD *)v8 + 112LL))(v8, 0);
          v37 = GetMemLogObject();
          CMemoryLog::Write(v37, v10);
          v33 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_84;
          }
          v34 = 695;
        }
        v38 = (unsigned int)v10;
        goto LABEL_83;
      }
      v32 = GetMemLogObject();
      v10 = -2147217402;
      CMemoryLog::Write(v32, -2147217402);
      v33 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_84;
      }
      v34 = 693;
    }
    else
    {
      v39 = GetMemLogObject();
      v10 = -2147217402;
      CMemoryLog::Write(v39, -2147217402);
      v33 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_84;
      }
      v34 = 692;
    }
    v38 = 2147749894LL;
LABEL_83:
    WPP_SF_d(*((_QWORD *)v33 + 2), v34, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, v38);
LABEL_84:
    std::unique_ptr<CAsyncReq_CreateClassEnumAsync>::_Delete(&v43);
    CReleaseMe::release((CReleaseMe *)&v46);
    goto LABEL_85;
  }
  v10 = (*(__int64 (__fastcall **)(struct _IWmiFinalizer *, _QWORD, struct IWbemObjectSink **))(*(_QWORD *)v8 + 64LL))(
          v8,
          0,
          &v44);
  if ( v10 >= 0 )
  {
    (*(void (__fastcall **)(struct _IWmiFinalizer *))(*(_QWORD *)v8 + 8LL))(v8);
    goto LABEL_37;
  }
  v23 = GetMemLogObject();
  CMemoryLog::Write(v23, v10);
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
  {
    return (unsigned int)v10;
  }
  v14 = 689;
LABEL_6:
  WPP_SF_d(*((_QWORD *)v13 + 2), v14, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, (unsigned int)v10);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180020f20  mov     rax, rsp
0x180020f23  mov     [rax+8], rsi
0x180020f27  mov     [rax+20h], rdi
0x180020f2b  mov     [rax+18h], r8
0x180020f2f  mov     [rax+10h], edx
0x180020f32  push    rbp
0x180020f33  push    r12
0x180020f35  push    r13
0x180020f37  push    r14
0x180020f39  push    r15
0x180020f3b  mov     rbp, rsp
0x180020f3e  sub     rsp, 80h
0x180020f45  mov     r14, r8
0x180020f48  mov     r15, rcx
0x180020f4b  call    ?CheckNs@CWbemNamespace@@QEAAJXZ; CWbemNamespace::CheckNs(void)
0x180020f50  mov     esi, eax
0x180020f52  test    eax, eax
0x180020f54  jns     short loc_180020FAF
0x180020f56  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180020f5c  mov     edx, esi
0x180020f5e  mov     rcx, rax
0x180020f61  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180020f67  lea     rdi, WPP_GLOBAL_Control
0x180020f6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180020f75  cmp     rcx, rdi
0x180020f78  jz      loc_1800214F8
0x180020f7e  test    byte ptr [rcx+1Ch], 1
0x180020f82  jz      loc_1800214F8
0x180020f88  cmp     byte ptr [rcx+19h], 2
0x180020f8c  jb      loc_1800214F8
0x180020f92  mov     edx, 2ACh
0x180020f97  mov     r9d, esi
0x180020f9a  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x180020fa1  mov     rcx, [rcx+10h]
0x180020fa5  call    WPP_SF_d
0x180020faa  jmp     loc_1800214F8
0x180020faf  lea     rdi, WPP_GLOBAL_Control
0x180020fb6  mov     r12, [rbp+arg_38]
0x180020fba  mov     r13d, [rbp+arg_28]
0x180020fbe  mov     rcx, cs:WPP_GLOBAL_Control
0x180020fc5  cmp     rcx, rdi
0x180020fc8  jz      short loc_180020FFD
0x180020fca  test    byte ptr [rcx+1Ch], 1
0x180020fce  jz      short loc_180020FFD
0x180020fd0  cmp     byte ptr [rcx+19h], 5
0x180020fd4  jb      short loc_180020FFD
0x180020fd6  mov     edx, 2ADh
0x180020fdb  mov     eax, [r15+130h]
0x180020fe2  mov     dword ptr [rsp+80h+var_50], eax
0x180020fe6  mov     [rsp+80h+var_58], r12
0x180020feb  mov     dword ptr [rsp+80h+var_60], r13d
0x180020ff0  mov     r9, [rbp+arg_20]
0x180020ff4  mov     rcx, [rcx+10h]
0x180020ff8  call    WPP_SF_Sdql
0x180020ffd  test    r14, r14
0x180021000  jnz     short loc_18002103A
0x180021002  test    r12, r12
0x180021005  jnz     short loc_18002103A
0x180021007  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002100d  mov     edx, 80041008h
0x180021012  mov     rcx, rax
0x180021015  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002101b  mov     rcx, cs:WPP_GLOBAL_Control
0x180021022  cmp     rcx, rdi
0x180021025  jz      short loc_18002108A
0x180021027  test    byte ptr [rcx+1Ch], 1
0x18002102b  jz      short loc_18002108A
0x18002102d  cmp     byte ptr [rcx+19h], 2
0x180021031  jb      short loc_18002108A
0x180021033  mov     edx, 2AEh
0x180021038  jmp     short loc_180021074
0x18002103a  test    r13d, 0FFFDFD7Fh
0x180021041  jz      short loc_180021094
0x180021043  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180021049  mov     edx, 80041008h
0x18002104e  mov     rcx, rax
0x180021051  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180021057  mov     rcx, cs:WPP_GLOBAL_Control
0x18002105e  cmp     rcx, rdi
0x180021061  jz      short loc_18002108A
0x180021063  test    byte ptr [rcx+1Ch], 1
0x180021067  jz      short loc_18002108A
0x180021069  cmp     byte ptr [rcx+19h], 2
0x18002106d  jb      short loc_18002108A
0x18002106f  mov     edx, 2AFh
0x180021074  mov     r9d, 80041008h
0x18002107a  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x180021081  mov     rcx, [rcx+10h]
0x180021085  call    WPP_SF_d
0x18002108a  mov     eax, 80041008h
0x18002108f  jmp     loc_1800214FA
0x180021094  mov     [rbp+var_38], 0
0x18002109c  test    r14, r14
0x18002109f  jnz     short loc_180021108
0x1800210a1  lea     rax, [rbp+var_38]
0x1800210a5  mov     [rsp+80h+var_60], rax; struct IWbemObjectSink **
0x1800210aa  lea     r9, [rbp+arg_10]; struct _IWmiFinalizer **
0x1800210ae  mov     r8, r12; struct IWbemObjectSink *
0x1800210b1  mov     rdx, [rbp+arg_30]; struct IWbemContext *
0x1800210b5  mov     rcx, r15; this
0x1800210b8  call    ?CreateAsyncFinalizer@CWbemNamespace@@QEAAJPEAUIWbemContext@@PEAUIWbemObjectSink@@PEAPEAU_IWmiFinalizer@@PEAPEAU3@@Z; CWbemNamespace::CreateAsyncFinalizer(IWbemContext *,IWbemObjectSink *,_IWmiFinalizer * *,IWbemObjectSink * *)
0x1800210bd  mov     esi, eax
0x1800210bf  test    eax, eax
0x1800210c1  jns     short loc_180021102
0x1800210c3  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800210c9  mov     edx, esi
0x1800210cb  mov     rcx, rax
0x1800210ce  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800210d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800210db  cmp     rcx, rdi
0x1800210de  jz      loc_1800214F8
0x1800210e4  test    byte ptr [rcx+1Ch], 1
0x1800210e8  jz      loc_1800214F8
0x1800210ee  cmp     byte ptr [rcx+19h], 2
0x1800210f2  jb      loc_1800214F8
0x1800210f8  mov     edx, 2B0h
0x1800210fd  jmp     loc_180020F97
0x180021102  mov     r14, [rbp+arg_10]
0x180021106  jmp     short loc_180021171
0x180021108  mov     rax, [r14]
0x18002110b  lea     r8, [rbp+var_38]
0x18002110f  xor     edx, edx
0x180021111  mov     rcx, r14
0x180021114  mov     rax, [rax+40h]
0x180021118  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002111d  mov     esi, eax
0x18002111f  test    eax, eax
0x180021121  jns     short loc_180021162
0x180021123  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180021129  mov     edx, esi
0x18002112b  mov     rcx, rax
0x18002112e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180021134  mov     rcx, cs:WPP_GLOBAL_Control
0x18002113b  cmp     rcx, rdi
0x18002113e  jz      loc_1800214F8
0x180021144  test    byte ptr [rcx+1Ch], 1
0x180021148  jz      loc_1800214F8
0x18002114e  cmp     byte ptr [rcx+19h], 2
0x180021152  jb      loc_1800214F8
0x180021158  mov     edx, 2B1h
0x18002115d  jmp     loc_180020F97
0x180021162  mov     rax, [r14]
0x180021165  mov     rcx, r14
0x180021168  mov     rax, [rax+8]
0x18002116c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021171  mov     rax, [rbp+var_38]
0x180021175  mov     [rbp+var_20], rax
0x180021179  mov     [rbp+var_18], r14
0x18002117d  mov     rax, [rbp+arg_30]
0x180021181  mov     [rsp+80h+var_60], rax; struct IWbemContext *
0x180021186  mov     r9, r14; struct _IWmiFinalizer *
0x180021189  mov     r8, [rbp+arg_20]; unsigned __int16 *
0x18002118d  lea     rdx, aIwbemservicesG; "IWbemServices::GetObject"
0x180021194  mov     rcx, r15; this
0x180021197  call    ?PublishInfo@CWbemNamespace@@QEAAJPEBG0PEAU_IWmiFinalizer@@PEAUIWbemContext@@@Z; CWbemNamespace::PublishInfo(ushort const *,ushort const *,_IWmiFinalizer *,IWbemContext *)
0x18002119c  mov     esi, eax
0x18002119e  test    eax, eax
0x1800211a0  jns     short loc_1800211E1
0x1800211a2  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800211a8  mov     edx, esi
0x1800211aa  mov     rcx, rax
0x1800211ad  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800211b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800211ba  cmp     rcx, rdi
0x1800211bd  jz      loc_1800214E5
0x1800211c3  test    byte ptr [rcx+1Ch], 1
0x1800211c7  jz      loc_1800214E5
0x1800211cd  cmp     byte ptr [rcx+19h], 2
0x1800211d1  jb      loc_1800214E5
0x1800211d7  mov     edx, 2B2h
0x1800211dc  jmp     loc_18002129D
0x1800211e1  mov     ecx, [r15+130h]
0x1800211e8  cmp     ecx, 0FFFFFFFFh
0x1800211eb  jz      short loc_18002123B
0x1800211ed  cmp     cs:?g_cntWinmgmtTraceLogging@@3_JA, 0; __int64 g_cntWinmgmtTraceLogging
0x1800211f5  jz      short loc_18002123B
0x1800211f7  lea     rax, aSemiSync; "(Semi)Sync"
0x1800211fe  lea     r8, aAsync; "Async"
0x180021205  test    r12, r12
0x180021208  cmovz   r8, rax
0x18002120c  mov     rax, [r15+58h]
0x180021210  mov     [rsp+80h+var_48], rax
0x180021215  mov     dword ptr [rsp+80h+var_50], ecx
0x180021219  mov     eax, [r15+17Ch]
0x180021220  mov     dword ptr [rsp+80h+var_58], eax
0x180021224  mov     dword ptr [rsp+80h+var_60], r13d
0x180021229  mov     r9, [rbp+arg_20]
0x18002122d  xor     edx, edx
0x18002122f  mov     ecx, [r14+2D4h]; unsigned int
0x180021236  call    ?WinmgmtTelemetrylogging@@YAXKZZ; WinmgmtTelemetrylogging(ulong,...)
0x18002123b  mov     [rbp+var_30], 0
0x180021243  mov     rcx, [rbp+var_38]
0x180021247  mov     rax, [rcx]
0x18002124a  lea     r8, [rbp+var_30]
0x18002124e  lea     rdx, IID_IWbemObjectSinkEx
0x180021255  mov     rax, [rax]
0x180021258  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002125d  mov     esi, eax
0x18002125f  test    eax, eax
0x180021261  jns     short loc_1800212B5
0x180021263  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180021269  mov     edx, esi
0x18002126b  mov     rcx, rax
0x18002126e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180021274  mov     rcx, cs:WPP_GLOBAL_Control
0x18002127b  cmp     rcx, rdi
0x18002127e  jz      loc_1800214E5
0x180021284  test    byte ptr [rcx+1Ch], 1
0x180021288  jz      loc_1800214E5
0x18002128e  cmp     byte ptr [rcx+19h], 2
0x180021292  jb      loc_1800214E5
0x180021298  mov     edx, 2B3h
0x18002129d  mov     r9d, esi
0x1800212a0  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x1800212a7  mov     rcx, [rcx+10h]
0x1800212ab  call    WPP_SF_d
0x1800212b0  jmp     loc_1800214E5
0x1800212b5  mov     rax, [rbp+var_30]
0x1800212b9  mov     [rbp+var_28], rax
0x1800212bd  mov     [rbp+var_40], 0
0x1800212c5  mov     ecx, 70h ; 'p'
0x1800212ca  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800212d0  mov     rsi, rax
0x1800212d3  mov     [rbp+var_10], rax
0x1800212d7  test    rax, rax
0x1800212da  jz      short loc_180021317
0x1800212dc  mov     byte ptr [rsp+80h+var_60], 0; bool
0x1800212e1  mov     r9, [rbp+arg_30]; struct IWbemContext *
0x1800212e5  mov     r8, [rbp+var_30]; struct IWbemObjectSinkEx *
0x1800212e9  mov     rdx, r15; struct CWbemNamespace *
0x1800212ec  mov     rcx, rax; this
0x1800212ef  call    ??0CNamespaceReq@@QEAA@PEAVCWbemNamespace@@PEAUIWbemObjectSinkEx@@PEAUIWbemContext@@_N@Z; CNamespaceReq::CNamespaceReq(CWbemNamespace *,IWbemObjectSinkEx *,IWbemContext *,bool)
0x1800212f4  nop
0x1800212f5  lea     rax, ??_7CAsyncReq_GetObjectAsync@@6B@; const CAsyncReq_GetObjectAsync::`vftable'
0x1800212fc  mov     [rsi], rax
0x1800212ff  lea     rcx, [rsi+60h]
0x180021303  xor     r8d, r8d
0x180021306  mov     rdx, [rbp+arg_20]
0x18002130a  call    cs:__imp_??0WString@@QEAA@PEAGH@Z; WString::WString(ushort *,int)
0x180021310  nop
0x180021311  mov     [rsi+68h], r13d
0x180021315  jmp     short loc_180021319
0x180021317  xor     esi, esi
0x180021319  test    rsi, rsi
0x18002131c  jz      loc_180021487
0x180021322  lea     rcx, [rbp+var_40]
0x180021326  call    ?_Delete@?$unique_ptr@VCAsyncReq_CreateClassEnumAsync@@U?$default_delete@VCAsyncReq_CreateClassEnumAsync@@@std@@@std@@AEAAXXZ; std::unique_ptr<CAsyncReq_CreateClassEnumAsync>::_Delete(void)
0x18002132b  mov     [rbp+var_40], rsi
0x18002132f  mov     rax, [rsi+28h]
0x180021333  test    rax, rax
0x180021336  jnz     short loc_18002137C
0x180021338  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002133e  mov     esi, 80041006h
0x180021343  mov     edx, esi
0x180021345  mov     rcx, rax
0x180021348  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002134e  mov     rcx, cs:WPP_GLOBAL_Control
0x180021355  cmp     rcx, rdi
0x180021358  jz      loc_1800214D1
0x18002135e  test    byte ptr [rcx+1Ch], 1
0x180021362  jz      loc_1800214D1
0x180021368  cmp     byte ptr [rcx+19h], 2
0x18002136c  jb      loc_1800214D1
0x180021372  mov     edx, 2B5h
0x180021377  jmp     loc_1800214BA
0x18002137c  mov     [rsp+80h+var_58], r12; struct IWbemObjectSink *
0x180021381  mov     [rsp+80h+var_60], rax; struct IWbemContext *
0x180021386  mov     r9d, [rbp+arg_8]; unsigned int
0x18002138a  mov     r8, r14; struct _IWmiFinalizer *
0x18002138d  mov     rdx, rsi; struct CAsyncReq *
0x180021390  mov     rcx, r15; this
0x180021393  call    ?InitNewTask@CWbemNamespace@@QEAAJPEAVCAsyncReq@@PEAU_IWmiFinalizer@@KPEAUIWbemContext@@PEAUIWbemObjectSink@@@Z; CWbemNamespace::InitNewTask(CAsyncReq *,_IWmiFinalizer *,ulong,IWbemContext *,IWbemObjectSink *)
0x180021398  mov     r15d, eax
0x18002139b  test    eax, eax
0x18002139d  jns     short loc_1800213FD
0x18002139f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800213a5  mov     edx, r15d
0x1800213a8  mov     rcx, rax
0x1800213ab  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800213b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800213b8  cmp     rcx, rdi
0x1800213bb  jz      short loc_1800213E2
0x1800213bd  test    byte ptr [rcx+1Ch], 1
0x1800213c1  jz      short loc_1800213E2
0x1800213c3  cmp     byte ptr [rcx+19h], 2
0x1800213c7  jb      short loc_1800213E2
0x1800213c9  mov     edx, 2B6h
0x1800213ce  mov     r9d, r15d
0x1800213d1  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x1800213d8  mov     rcx, [rcx+10h]
0x1800213dc  call    WPP_SF_d
0x1800213e1  nop
0x1800213e2  lea     rcx, [rbp+var_40]
0x1800213e6  call    ?_Delete@?$unique_ptr@VCAsyncReq_CreateClassEnumAsync@@U?$default_delete@VCAsyncReq_CreateClassEnumAsync@@@std@@@std@@AEAAXXZ; std::unique_ptr<CAsyncReq_CreateClassEnumAsync>::_Delete(void)
0x1800213eb  nop
0x1800213ec  lea     rcx, [rbp+var_28]; this
0x1800213f0  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x1800213f5  mov     esi, r15d
0x1800213f8  jmp     loc_1800214E5
0x1800213fd  lea     rcx, [rbp+var_20]; this
  ... truncated ...
```
