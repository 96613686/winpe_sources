# CDlpTask::EnqueueAction(IDlpAction *,ulong,ushort const *)

- ea: `0x180053bf0`
- end: `0x18005447c`
- name: `?EnqueueAction@CDlpTask@@UEAAJPEAVIDlpAction@@KPEBG@Z`
- size: `2188`
- prototype: `__int64 __fastcall(CDlpTask *__hidden this, struct IDlpAction *, unsigned int, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x180001ba8`
- `0x180001be8`
- `0x180002898`
- `0x180007bbc`
- `0x18000aba4`
- `0x18000ea20`
- `0x180012f5c`
- `0x18001ce28`
- `0x18001fd60`
- `0x180047440`
- `0x1800475b0`
- `0x180047a78`
- `0x180049d6c`
- `0x180053bf0`
- `0x18007ec9a`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005442e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005442e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005443d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005443d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180053c4b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180053c4b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180054455`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180054455`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800543e2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800543e2`

## string_xrefs

- `0x180053ccd`: `CDlpTask::EnqueueAction`
- `0x180054398`: `CDlpTask::EnqueueAction`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CDlpTask::EnqueueAction(
        CDlpTask *this,
        struct IDlpAction *a2,
        unsigned int a3,
        unsigned __int16 *a4)
{
  struct _RTL_CRITICAL_SECTION *v8; // r15
  int v9; // edi
  __int64 v10; // rax
  __int64 v11; // rcx
  int v12; // eax
  int StringCch; // eax
  _QWORD *v14; // rax
  _QWORD *v15; // rdi
  int v16; // eax
  __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // rax
  __int64 v20; // rcx
  int v21; // eax
  _DWORD *v22; // rbx
  __int64 v23; // rbx
  HANDLE ProcessHeap; // rax
  int v26; // [rsp+20h] [rbp-60h]
  int v27; // [rsp+20h] [rbp-60h]
  int v28; // [rsp+28h] [rbp-58h]
  int v29; // [rsp+28h] [rbp-58h]
  struct _RTL_CRITICAL_SECTION *v30; // [rsp+30h] [rbp-50h]
  void *Block; // [rsp+38h] [rbp-48h] BYREF
  __int64 v32; // [rsp+40h] [rbp-40h] BYREF
  struct IDlpAction *v33; // [rsp+48h] [rbp-38h] BYREF
  _QWORD v34[4]; // [rsp+50h] [rbp-30h] BYREF
  __int64 v35; // [rsp+70h] [rbp-10h]
  __int64 v36; // [rsp+78h] [rbp-8h]
  void *v37; // [rsp+C0h] [rbp+40h] BYREF
  int v38; // [rsp+C8h] [rbp+48h] BYREF

  v36 = 0;
  v34[3] = (char *)this + 424;
  v34[2] = &CDlpAutoDelayLockT<CDlpAutoExclusiveAcquireLockT<CEmptyType>>::`vftable';
  v8 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 432);
  v30 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 432);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 432));
  v35 = 1;
  LODWORD(v37) = 0;
  v38 = 0;
  v32 = 0;
  v34[0] = 0;
  v33 = 0;
  Block = 0;
  v34[1] = 0;
  if ( !a2 )
  {
    v9 = -2147024809;
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176) )
      goto LABEL_79;
    v10 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176);
    v11 = 0;
    if ( !v10 )
      goto LABEL_7;
    v28 = -2147024809;
    v26 = 1313;
    goto LABEL_5;
  }
  v9 = CDlpTask::CheckInitialized(this, (enum WINDLP_STATE *)&v37);
  if ( v9 >= 0 )
  {
    if ( (_DWORD)v37 == 3 )
    {
      v9 = -2147019873;
      if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176) )
        goto LABEL_79;
      v10 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176);
      v11 = 0;
      if ( !v10 )
        goto LABEL_7;
      v28 = -2147019873;
      v26 = 1321;
      goto LABEL_5;
    }
    if ( a4 )
    {
      LODWORD(v37) = 0;
      StringCch = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(a4, &v37);
      v9 = StringCch;
      if ( StringCch < 0
        || (StringCch = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(a4),
            v9 = StringCch,
            StringCch < 0) )
      {
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)StringCch);
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v9);
      if ( v9 < 0 )
      {
        if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176) )
          goto LABEL_79;
        v10 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176);
        v11 = 0;
        if ( !v10 )
          goto LABEL_7;
        v28 = v9;
        v26 = 1327;
        goto LABEL_5;
      }
      if ( (*(unsigned int (__fastcall **)(CDlpTask *, __int64, _QWORD *))(*(_QWORD *)this + 136LL))(this, v32, v34) != -2147023728 )
      {
        v9 = -2147024713;
        if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176) )
          goto LABEL_79;
        v10 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176);
        v11 = 0;
        if ( !v10 )
          goto LABEL_7;
        v28 = -2147024713;
        v26 = 1328;
        goto LABEL_5;
      }
    }
    v9 = (*(__int64 (__fastcall **)(struct IDlpAction *, int *))(*(_QWORD *)a2 + 24LL))(a2, &v38);
    if ( v9 < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176) )
        goto LABEL_79;
      v10 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176);
      v11 = 0;
      if ( !v10 )
        goto LABEL_7;
      v28 = v9;
      v26 = 1333;
      goto LABEL_5;
    }
    if ( v38 != -21037378 && v38 )
    {
      v9 = -2147019873;
      if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176) )
        goto LABEL_79;
      v10 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176);
      v11 = 0;
      if ( !v10 )
        goto LABEL_7;
      v28 = -2147019873;
      v26 = 1335;
      goto LABEL_5;
    }
    v9 = (*(__int64 (__fastcall **)(struct IDlpAction *, CDlpTask *))(*(_QWORD *)a2 + 104LL))(a2, this);
    if ( v9 < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176) )
        goto LABEL_79;
      v10 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176);
      v11 = 0;
      if ( !v10 )
        goto LABEL_7;
      v28 = v9;
      v26 = 1339;
LABEL_5:
      v12 = CDlpLogT<CEmptyType>::DlpLogFormat(v10, 4, L"%s(%d): Result = 0x%X", L"CDlpTask::EnqueueAction", v26, v28);
      v11 = (unsigned int)v12;
      if ( v12 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v12);
      goto LABEL_7;
    }
    if ( *((_DWORD *)this + 295) > *((_DWORD *)this + 95) )
      goto LABEL_59;
    v14 = operator new(0x40u);
    v15 = v14;
    v37 = v14;
    if ( !v14 )
      goto LABEL_56;
    memset_0(v14, 0, 0x40u);
    v15[1] = 0;
    *((_OWORD *)v15 + 1) = 0;
    *((_OWORD *)v15 + 2) = 0;
    *((_OWORD *)v15 + 3) = 0;
    CExclusiveAcquireLock::Init((CExclusiveAcquireLock *)(v15 + 2));
    v16 = CExclusiveAcquireLock::Init((CExclusiveAcquireLock *)(v15 + 2));
    v17 = (unsigned int)v16;
    if ( v16 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v16);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v17);
    if ( !v15 )
    {
LABEL_56:
      Block = 0;
      v9 = -2147024882;
      if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176) )
        goto LABEL_78;
      v19 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176);
      v20 = 0;
      if ( !v19 )
        goto LABEL_77;
      v29 = -2147024882;
      v27 = 1348;
      goto LABEL_75;
    }
    Block = v15;
    v18 = CExclusiveAcquireLock::Init((CExclusiveAcquireLock *)(v15 + 2));
    v9 = v18;
    if ( v18 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v18);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v9);
    if ( v9 < 0 )
    {
      if ( (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176) )
      {
        v19 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176);
        v20 = 0;
        if ( v19 )
        {
          v29 = v9;
          v27 = 1349;
          goto LABEL_75;
        }
LABEL_77:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v20);
      }
LABEL_78:
      v8 = v30;
      goto LABEL_79;
    }
    v9 = CArray<DP_CPP<CULargeInteger>,DP_CPP<CULargeInteger>,CAdaptorDefault,CPoliciesDefault>::Append(
           (char *)this + 1176,
           &Block);
    if ( v9 >= 0 )
    {
LABEL_59:
      v33 = a2;
      (*(void (__fastcall **)(struct IDlpAction *))(*(_QWORD *)a2 + 8LL))(a2);
      v9 = CArray<DP_COM<IUnknown>,DP_COM<IUnknown>,CAdaptorDefault,CPoliciesDefault>::Append((char *)this + 376, &v33);
      if ( v9 >= 0 )
      {
        v9 = CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::Append((char *)this + 1192, &v32);
        if ( v9 >= 0 )
        {
          v9 = CArray<unsigned long,unsigned long,CAdaptorDefault,CPoliciesDefault>::Append((char *)this + 1208, a3);
          if ( v9 >= 0 )
          {
            v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 163) + 280LL))(
                   *((_QWORD *)this + 163),
                   0);
            if ( v9 >= 0 || !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176) )
              goto LABEL_78;
            v19 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176);
            v20 = 0;
            if ( !v19 )
              goto LABEL_77;
            v29 = v9;
            v27 = 1363;
            goto LABEL_75;
          }
          if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176) )
            goto LABEL_78;
          v19 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176);
          v20 = 0;
          if ( !v19 )
            goto LABEL_77;
          v29 = v9;
          v27 = 1359;
        }
        else
        {
          if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176) )
            goto LABEL_78;
          v19 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176);
          v20 = 0;
          if ( !v19 )
            goto LABEL_77;
          v29 = v9;
          v27 = 1358;
        }
      }
      else
      {
        if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176) )
          goto LABEL_78;
        v19 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176);
        v20 = 0;
        if ( !v19 )
          goto LABEL_77;
        v29 = v9;
        v27 = 1357;
      }
    }
    else
    {
      if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176) )
        goto LABEL_78;
      v19 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176);
      v20 = 0;
      if ( !v19 )
        goto LABEL_77;
      v29 = v9;
      v27 = 1350;
    }
LABEL_75:
    v21 = CDlpLogT<CEmptyType>::DlpLogFormat(v19, 4, L"%s(%d): Result = 0x%X", L"CDlpTask::EnqueueAction", v27, v29);
    v20 = (unsigned int)v21;
    if ( v21 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v21);
    goto LABEL_77;
  }
  if ( (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176) )
  {
    v10 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176);
    v11 = 0;
    if ( v10 )
    {
      v28 = v9;
      v26 = 1317;
      goto LABEL_5;
    }
LABEL_7:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v11);
  }
LABEL_79:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v9);
  v22 = Block;
  if ( Block )
  {
    if ( *((_DWORD *)Block + 14) )
    {
      DeleteCriticalSection((LPCRITICAL_SECTION)((char *)Block + 16));
      v22[14] = 0;
    }
    operator delete(v22);
  }
  if ( v33 )
    (*(void (__fastcall **)(struct IDlpAction *))(*(_QWORD *)v33 + 16LL))(v33);
  if ( v34[0] )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v34[0] + 16LL))(v34[0]);
    v34[0] = 0;
  }
  v23 = v32;
  if ( v32 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(v23 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( (_DWORD)v35 )
  {
    LeaveCriticalSection(v8);
    LODWORD(v35) = 0;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180053bf0  mov     [rsp-38h+arg_10], rbx
0x180053bf5  push    rbp
0x180053bf6  push    rsi
0x180053bf7  push    rdi
0x180053bf8  push    r12
0x180053bfa  push    r13
0x180053bfc  push    r14
0x180053bfe  push    r15
0x180053c00  mov     rbp, rsp
0x180053c03  sub     rsp, 80h
0x180053c0a  mov     rbx, r9
0x180053c0d  mov     r12d, r8d
0x180053c10  mov     r14, rdx
0x180053c13  mov     rsi, rcx
0x180053c16  xor     r13d, r13d
0x180053c19  mov     [rbp+var_8], r13
0x180053c1d  xorps   xmm0, xmm0
0x180053c20  xor     eax, eax
0x180053c22  movups  [rbp+var_20], xmm0
0x180053c26  mov     [rbp+var_10], rax
0x180053c2a  lea     rax, [rcx+1A8h]
0x180053c31  mov     qword ptr [rbp+var_20+8], rax
0x180053c35  lea     rcx, ??_7?$CDlpAutoDelayLockT@V?$CDlpAutoExclusiveAcquireLockT@VCEmptyType@@@@@@6B@; const CDlpAutoDelayLockT<CDlpAutoExclusiveAcquireLockT<CEmptyType>>::`vftable'
0x180053c3c  mov     qword ptr [rbp+var_20], rcx
0x180053c40  lea     r15, [rax+8]
0x180053c44  mov     [rbp+var_50], r15
0x180053c48  mov     rcx, r15; lpCriticalSection
0x180053c4b  call    cs:__imp_EnterCriticalSection
0x180053c51  mov     dword ptr [rbp+var_10], 1
0x180053c58  mov     dword ptr [rbp+arg_0], r13d
0x180053c5c  mov     [rbp+arg_8], r13d
0x180053c60  mov     [rbp+var_40], r13
0x180053c64  mov     [rbp+var_30], r13
0x180053c68  mov     [rbp+var_38], r13
0x180053c6c  mov     [rbp+Block], r13
0x180053c70  mov     [rbp+var_28], r13
0x180053c74  test    r14, r14
0x180053c77  jnz     loc_180053CFD
0x180053c7d  mov     edi, 80070057h
0x180053c82  mov     rax, [rsi+0B0h]
0x180053c89  lea     rcx, [rsi+0B0h]
0x180053c90  mov     rax, [rax+10h]
0x180053c94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053c99  test    rax, rax
0x180053c9c  jz      loc_1800543C7
0x180053ca2  mov     rax, [rsi+0B0h]
0x180053ca9  lea     rcx, [rsi+0B0h]
0x180053cb0  mov     rax, [rax+10h]
0x180053cb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053cb9  mov     ecx, r13d
0x180053cbc  test    rax, rax
0x180053cbf  jz      short loc_180053CF3
0x180053cc1  mov     [rsp+80h+var_58], edi
0x180053cc5  mov     [rsp+80h+var_60], 521h
0x180053ccd  lea     r9, aCdlptaskEnqueu; "CDlpTask::EnqueueAction"
0x180053cd4  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180053cdb  mov     edx, 4
0x180053ce0  mov     rcx, rax
0x180053ce3  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180053ce8  test    eax, eax
0x180053cea  mov     ecx, eax
0x180053cec  jns     short loc_180053CF3
0x180053cee  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180053cf3  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180053cf8  jmp     loc_1800543C7
0x180053cfd  lea     rdx, [rbp+arg_0]; enum WINDLP_STATE *
0x180053d01  mov     rcx, rsi; this
0x180053d04  call    ?CheckInitialized@CDlpTask@@AEAAJPEAW4WINDLP_STATE@@@Z; CDlpTask::CheckInitialized(WINDLP_STATE *)
0x180053d09  mov     edi, eax
0x180053d0b  test    eax, eax
0x180053d0d  jns     short loc_180053D5F
0x180053d0f  mov     rdx, [rsi+0B0h]
0x180053d16  lea     rcx, [rsi+0B0h]
0x180053d1d  mov     rax, [rdx+10h]
0x180053d21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053d26  test    rax, rax
0x180053d29  jz      loc_1800543C7
0x180053d2f  mov     rax, [rsi+0B0h]
0x180053d36  lea     rcx, [rsi+0B0h]
0x180053d3d  mov     rax, [rax+10h]
0x180053d41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053d46  mov     ecx, r13d
0x180053d49  test    rax, rax
0x180053d4c  jz      short loc_180053CF3
0x180053d4e  mov     [rsp+80h+var_58], edi
0x180053d52  mov     [rsp+80h+var_60], 525h
0x180053d5a  jmp     loc_180053CCD
0x180053d5f  cmp     dword ptr [rbp+arg_0], 3
0x180053d63  jnz     short loc_180053DC0
0x180053d65  mov     ebx, 8007139Fh
0x180053d6a  mov     edi, ebx
0x180053d6c  mov     rax, [rsi+0B0h]
0x180053d73  lea     rcx, [rsi+0B0h]
0x180053d7a  mov     rax, [rax+10h]
0x180053d7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053d83  test    rax, rax
0x180053d86  jz      loc_1800543C7
0x180053d8c  mov     rax, [rsi+0B0h]
0x180053d93  lea     rcx, [rsi+0B0h]
0x180053d9a  mov     rax, [rax+10h]
0x180053d9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053da3  mov     ecx, r13d
0x180053da6  test    rax, rax
0x180053da9  jz      loc_180053CF3
0x180053daf  mov     [rsp+80h+var_58], ebx
0x180053db3  mov     [rsp+80h+var_60], 529h
0x180053dbb  jmp     loc_180053CCD
0x180053dc0  test    rbx, rbx
0x180053dc3  jz      loc_180053ED4
0x180053dc9  mov     dword ptr [rbp+arg_0], r13d
0x180053dcd  lea     rdx, [rbp+arg_0]
0x180053dd1  mov     rcx, rbx
0x180053dd4  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEBGPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(ushort const *,ulong *,ulong)
0x180053dd9  mov     edi, eax
0x180053ddb  test    eax, eax
0x180053ddd  js      short loc_180053DF4
0x180053ddf  lea     r8, [rbp+var_40]
0x180053de3  mov     edx, dword ptr [rbp+arg_0]
0x180053de6  mov     rcx, rbx; Src
0x180053de9  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x180053dee  mov     edi, eax
0x180053df0  test    eax, eax
0x180053df2  jns     short loc_180053DFB
0x180053df4  mov     ecx, eax
0x180053df6  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180053dfb  mov     ecx, edi
0x180053dfd  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180053e02  test    edi, edi
0x180053e04  jns     short loc_180053E5A
0x180053e06  mov     rax, [rsi+0B0h]
0x180053e0d  lea     rcx, [rsi+0B0h]
0x180053e14  mov     rax, [rax+10h]
0x180053e18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053e1d  test    rax, rax
0x180053e20  jz      loc_1800543C7
0x180053e26  mov     rax, [rsi+0B0h]
0x180053e2d  lea     rcx, [rsi+0B0h]
0x180053e34  mov     rax, [rax+10h]
0x180053e38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053e3d  mov     ecx, r13d
0x180053e40  test    rax, rax
0x180053e43  jz      loc_180053CF3
0x180053e49  mov     [rsp+80h+var_58], edi
0x180053e4d  mov     [rsp+80h+var_60], 52Fh
0x180053e55  jmp     loc_180053CCD
0x180053e5a  mov     rax, [rsi]
0x180053e5d  lea     r8, [rbp+var_30]
0x180053e61  mov     rdx, [rbp+var_40]
0x180053e65  mov     rcx, rsi
0x180053e68  mov     rax, [rax+88h]
0x180053e6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053e74  cmp     eax, 80070490h
0x180053e79  jz      short loc_180053ED4
0x180053e7b  mov     edi, 800700B7h
0x180053e80  mov     rax, [rsi+0B0h]
0x180053e87  lea     rcx, [rsi+0B0h]
0x180053e8e  mov     rax, [rax+10h]
0x180053e92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053e97  test    rax, rax
0x180053e9a  jz      loc_1800543C7
0x180053ea0  mov     rax, [rsi+0B0h]
0x180053ea7  lea     rcx, [rsi+0B0h]
0x180053eae  mov     rax, [rax+10h]
0x180053eb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053eb7  mov     ecx, r13d
0x180053eba  test    rax, rax
0x180053ebd  jz      loc_180053CF3
0x180053ec3  mov     [rsp+80h+var_58], edi
0x180053ec7  mov     [rsp+80h+var_60], 530h
0x180053ecf  jmp     loc_180053CCD
0x180053ed4  mov     rax, [r14]
0x180053ed7  lea     rdx, [rbp+arg_8]
0x180053edb  mov     rcx, r14
0x180053ede  mov     rax, [rax+18h]
0x180053ee2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053ee7  mov     edi, eax
0x180053ee9  test    eax, eax
0x180053eeb  jns     short loc_180053F41
0x180053eed  mov     rax, [rsi+0B0h]
0x180053ef4  lea     rcx, [rsi+0B0h]
0x180053efb  mov     rax, [rax+10h]
0x180053eff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053f04  test    rax, rax
0x180053f07  jz      loc_1800543C7
0x180053f0d  mov     rax, [rsi+0B0h]
0x180053f14  lea     rcx, [rsi+0B0h]
0x180053f1b  mov     rax, [rax+10h]
0x180053f1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053f24  mov     ecx, r13d
0x180053f27  test    rax, rax
0x180053f2a  jz      loc_180053CF3
0x180053f30  mov     [rsp+80h+var_58], edi
0x180053f34  mov     [rsp+80h+var_60], 535h
0x180053f3c  jmp     loc_180053CCD
0x180053f41  mov     eax, [rbp+arg_8]
0x180053f44  cmp     eax, 0FEBEFEBEh
0x180053f49  jz      short loc_180053FAA
0x180053f4b  test    eax, eax
0x180053f4d  jz      short loc_180053FAA
0x180053f4f  mov     ebx, 8007139Fh
0x180053f54  mov     edi, ebx
0x180053f56  mov     rax, [rsi+0B0h]
0x180053f5d  lea     rcx, [rsi+0B0h]
0x180053f64  mov     rax, [rax+10h]
0x180053f68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053f6d  test    rax, rax
0x180053f70  jz      loc_1800543C7
0x180053f76  mov     rax, [rsi+0B0h]
0x180053f7d  lea     rcx, [rsi+0B0h]
0x180053f84  mov     rax, [rax+10h]
0x180053f88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053f8d  mov     ecx, r13d
0x180053f90  test    rax, rax
0x180053f93  jz      loc_180053CF3
0x180053f99  mov     [rsp+80h+var_58], ebx
0x180053f9d  mov     [rsp+80h+var_60], 537h
0x180053fa5  jmp     loc_180053CCD
0x180053faa  mov     rax, [r14]
0x180053fad  mov     rdx, rsi
0x180053fb0  mov     rcx, r14
0x180053fb3  mov     rax, [rax+68h]
0x180053fb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053fbc  mov     edi, eax
0x180053fbe  test    eax, eax
0x180053fc0  jns     short loc_180054016
0x180053fc2  mov     rax, [rsi+0B0h]
0x180053fc9  lea     rcx, [rsi+0B0h]
0x180053fd0  mov     rax, [rax+10h]
0x180053fd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053fd9  test    rax, rax
0x180053fdc  jz      loc_1800543C7
0x180053fe2  mov     rax, [rsi+0B0h]
0x180053fe9  lea     rcx, [rsi+0B0h]
0x180053ff0  mov     rax, [rax+10h]
0x180053ff4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053ff9  mov     ecx, r13d
0x180053ffc  test    rax, rax
0x180053fff  jz      loc_180053CF3
0x180054005  mov     [rsp+80h+var_58], edi
0x180054009  mov     [rsp+80h+var_60], 53Bh
0x180054011  jmp     loc_180053CCD
0x180054016  lea     r13, [rsi+178h]
0x18005401d  lea     r15, [rsi+498h]
0x180054024  mov     eax, [r13+4]
0x180054028  cmp     [r15+4], eax
0x18005402c  jg      loc_1800541E7
0x180054032  mov     ebx, 40h ; '@'
0x180054037  mov     ecx, ebx; Size
0x180054039  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005403e  mov     rdi, rax
0x180054041  mov     [rbp+arg_0], rax
0x180054045  test    rax, rax
0x180054048  jz      loc_180054187
0x18005404e  mov     r8d, ebx; Size
0x180054051  xor     edx, edx; Val
0x180054053  mov     rcx, rax; void *
0x180054056  call    memset_0
0x18005405b  mov     qword ptr [rdi+8], 0
0x180054063  lea     rbx, [rdi+10h]
0x180054067  xorps   xmm0, xmm0
0x18005406a  movups  xmmword ptr [rbx], xmm0
0x18005406d  movups  xmmword ptr [rbx+10h], xmm0
0x180054071  movups  xmmword ptr [rbx+20h], xmm0
0x180054075  mov     rcx, rbx; this
0x180054078  call    ?Init@CExclusiveAcquireLock@@QEAAJXZ; CExclusiveAcquireLock::Init(void)
0x18005407d  mov     rcx, rbx; this
0x180054080  call    ?Init@CExclusiveAcquireLock@@QEAAJXZ; CExclusiveAcquireLock::Init(void)
0x180054085  mov     ecx, eax
0x180054087  test    eax, eax
0x180054089  jns     short loc_180054090
0x18005408b  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180054090  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180054095  test    rdi, rdi
0x180054098  jz      loc_180054187
0x18005409e  mov     [rbp+Block], rdi
0x1800540a2  lea     rcx, [rdi+10h]; this
0x1800540a6  call    ?Init@CExclusiveAcquireLock@@QEAAJXZ; CExclusiveAcquireLock::Init(void)
0x1800540ab  mov     edi, eax
0x1800540ad  test    eax, eax
0x1800540af  jns     short loc_1800540B8
0x1800540b1  mov     ecx, eax
0x1800540b3  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800540b8  mov     ecx, edi
0x1800540ba  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800540bf  test    edi, edi
0x1800540c1  jns     short loc_18005411A
0x1800540c3  mov     rax, [rsi+0B0h]
0x1800540ca  lea     rcx, [rsi+0B0h]
0x1800540d1  mov     rax, [rax+10h]
0x1800540d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800540da  xor     r13d, r13d
0x1800540dd  test    rax, rax
0x1800540e0  jz      loc_1800543C3
0x1800540e6  mov     rax, [rsi+0B0h]
0x1800540ed  lea     rcx, [rsi+0B0h]
0x1800540f4  mov     rax, [rax+10h]
0x1800540f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800540fd  mov     ecx, r13d
0x180054100  test    rax, rax
0x180054103  jz      loc_1800543BE
  ... truncated ...
```
