# ClusWmi::DataStore::GetCacheKey(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,cxl::Sid &)

- ea: `0x18001b8ec`
- end: `0x18001bbc4`
- name: `?GetCacheKey@DataStore@ClusWmi@@AEAA_NAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVSid@cxl@@@Z`
- size: `728`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001be30`

## callees

- `0x180002a70`
- `0x180005e68`
- `0x18000a6dc`
- `0x18000c284`
- `0x18000d250`
- `0x18000d794`
- `0x180013dd4`
- `0x1800154e0`
- `0x180018ba4`
- `0x180019374`
- `0x18001a080`
- `0x18001a1d0`
- `0x18001a254`
- `0x18001a300`
- `0x18001a728`
- `0x18001a770`
- `0x18001b23c`
- `0x18001b8ec`
- `0x18001bffc`
- `0x18001d550`
- `0x18001d5a8`
- `0x18001e964`
- `0x1800a9010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001b9a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001bb3a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001b9a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001bb3a`

## string_xrefs

- `0x18001bad6`: `Access`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
char __fastcall ClusWmi::DataStore::GetCacheKey(ClusWmi::DataStore *a1, __int64 a2, struct cxl::Sid *a3)
{
  RTL_SRWLOCK *v6; // r13
  __int64 *v7; // r14
  struct _FILETIME *v8; // rbx
  __int64 v9; // rcx
  _QWORD *v10; // rsi
  std::_Ref_count_base *v11; // rbx
  int v12; // edi
  char v13; // bl
  __int64 v15; // rax
  __int64 v16; // rax
  struct _FILETIME *v17; // rbx
  unsigned int v18; // [rsp+20h] [rbp-89h] BYREF
  _LUID v19; // [rsp+28h] [rbp-81h] BYREF
  std::_Ref_count_base *v20[2]; // [rsp+30h] [rbp-79h] BYREF
  void *v21; // [rsp+40h] [rbp-69h] BYREF
  __int64 v22; // [rsp+48h] [rbp-61h]
  struct _FILETIME SystemTimeAsFileTime[2]; // [rsp+50h] [rbp-59h] BYREF
  struct _FILETIME *v24; // [rsp+60h] [rbp-49h]
  _BYTE v25[32]; // [rsp+70h] [rbp-39h] BYREF
  _BYTE v26[32]; // [rsp+90h] [rbp-19h] BYREF
  void **v27; // [rsp+B0h] [rbp+7h]
  struct _FILETIME v28; // [rsp+B8h] [rbp+Fh]

  v22 = 0;
  v19 = 0;
  if ( ClusWmi::DataStore::GetCurrentTokenModifiedIDAndSid(a1, &v21, &v19, a3) )
  {
    *(_OWORD *)v20 = 0;
    v6 = (RTL_SRWLOCK *)((char *)a1 + 64);
    cxl::AcquireReadLock::AcquireReadLock((cxl::AcquireReadLock *)v25, (ClusWmi::DataStore *)((char *)a1 + 64));
    v7 = (__int64 *)((char *)a1 + 80);
    std::_Tree<std::_Tmap_traits<_LUID,std::pair<std::wstring,cxl::DateTime>,ClusWmi::DataStore::LUIDComparer,std::allocator<std::pair<_LUID const,std::pair<std::wstring,cxl::DateTime>>>,0>>::_Find_lower_bound<_LUID>(
      (__int64)a1 + 80,
      SystemTimeAsFileTime,
      (unsigned int *)&v19);
    v8 = v24;
    if ( std::_Tree<std::_Tmap_traits<_LUID,std::pair<std::wstring,cxl::DateTime>,ClusWmi::DataStore::LUIDComparer,std::allocator<std::pair<_LUID const,std::pair<std::wstring,cxl::DateTime>>>,0>>::_Lower_bound_duplicate<_LUID>(
           v9,
           (__int64)v24,
           (unsigned int *)&v19)
      && v8 != (struct _FILETIME *)*v7 )
    {
      std::wstring::operator=(a2);
      SystemTimeAsFileTime[0] = 0;
      GetSystemTimeAsFileTime(SystemTimeAsFileTime);
      v8[10] = SystemTimeAsFileTime[0];
      cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireSharedTraits<cxl::NonReentrantRWLock>>::Release(v25);
LABEL_21:
      v13 = 1;
      goto LABEL_15;
    }
    v10 = (_QWORD *)((char *)a1 + 112);
    std::shared_ptr<ClusWmi::DataStore::CacheObject>::operator=(v20);
    cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireSharedTraits<cxl::NonReentrantRWLock>>::Release(v25);
    v11 = v20[0];
    if ( v20[0] )
      goto LABEL_24;
    *(_OWORD *)&SystemTimeAsFileTime[0].dwLowDateTime = 0;
    v12 = (*(__int64 (__fastcall **)(_QWORD, struct _FILETIME *))(**(_QWORD **)a1 + 48LL))(
            *(_QWORD *)a1,
            SystemTimeAsFileTime);
    if ( v12 >= 0 )
    {
      v12 = (***(__int64 (__fastcall ****)(_QWORD, _QWORD))SystemTimeAsFileTime)(*(_QWORD *)SystemTimeAsFileTime, 0);
      if ( v12 >= 0 )
      {
        std::shared_ptr<ClusWmi::DataStore::CacheObject>::operator=(v20);
        v11 = v20[0];
      }
    }
    if ( SystemTimeAsFileTime[1] )
      std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&SystemTimeAsFileTime[1]);
    if ( v12 >= 0 )
    {
LABEL_24:
      v18 = 0;
      if ( (*(int (__fastcall **)(std::_Ref_count_base *, __int64, unsigned int *))(*(_QWORD *)v11 + 64LL))(
             v11,
             v22,
             &v18) >= 0 )
      {
        v15 = cxl::SidBase::ToString((__int64)a3, (__int64)v25);
        std::wstring::operator=(a2, v15);
        std::wstring::_Tidy_deallocate(v25);
        std::_Integral_to_string<wchar_t,unsigned long>(v25, v18);
        v16 = std::wstring::wstring(v26, L"Access");
        std::operator+<wchar_t>(SystemTimeAsFileTime, v16, v25);
        std::wstring::append(a2);
        std::wstring::_Tidy_deallocate(SystemTimeAsFileTime);
        std::wstring::_Tidy_deallocate(v26);
        std::wstring::_Tidy_deallocate(v25);
        cxl::AcquireWriteLock::AcquireWriteLock((cxl::AcquireWriteLock *)v25, v6);
        SystemTimeAsFileTime[0] = 0;
        GetSystemTimeAsFileTime(SystemTimeAsFileTime);
        std::wstring::wstring(v26);
        v27 = &cxl::DateTime::`vftable';
        v28 = SystemTimeAsFileTime[0];
        v17 = *(struct _FILETIME **)std::map<_LUID,std::pair<std::wstring,cxl::DateTime>,ClusWmi::DataStore::LUIDComparer,std::allocator<std::pair<_LUID const,std::pair<std::wstring,cxl::DateTime>>>>::_Try_emplace<_LUID const &,>(
                                      v7,
                                      (__int64)SystemTimeAsFileTime,
                                      (unsigned int *)&v19);
        std::wstring::operator=(&v17[5], v26);
        v17[10] = v28;
        std::wstring::_Tidy_deallocate(v26);
        if ( !*v10 )
          std::shared_ptr<ClusWmi::DataStore::CacheObject>::operator=(v10);
        cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireExclusiveTraits<cxl::NonReentrantRWLock>>::Release((__int64)v25);
        if ( v20[1] )
          std::_Ref_count_base::_Decref(v20[1]);
        goto LABEL_21;
      }
    }
    if ( v20[1] )
      std::_Ref_count_base::_Decref(v20[1]);
  }
  v13 = 0;
LABEL_15:
  cxl::Token::Clear((cxl::Token *)&v21);
  return v13;
}

```

## disassembly

```asm
0x18001b8ec  mov     [rsp-8+arg_18], rbx
0x18001b8f1  push    rbp
0x18001b8f2  push    rsi
0x18001b8f3  push    rdi
0x18001b8f4  push    r12
0x18001b8f6  push    r13
0x18001b8f8  push    r14
0x18001b8fa  push    r15
0x18001b8fc  lea     rbp, [rsp-27h]
0x18001b901  sub     rsp, 0D0h
0x18001b908  mov     rax, cs:__security_cookie
0x18001b90f  xor     rax, rsp
0x18001b912  mov     [rbp+57h+var_40], rax
0x18001b916  mov     r12, r8
0x18001b919  mov     r15, rdx
0x18001b91c  mov     rdi, rcx
0x18001b91f  xor     eax, eax
0x18001b921  mov     [rbp+57h+var_B8], rax
0x18001b925  mov     qword ptr [rsp+100h+var_D8.LowPart], rax
0x18001b92a  mov     r9, r8; struct cxl::Sid *
0x18001b92d  lea     r8, [rsp+100h+var_D8]; struct _LUID *
0x18001b932  lea     rdx, [rbp+57h+var_C0]; struct cxl::Token *
0x18001b936  call    ?GetCurrentTokenModifiedIDAndSid@DataStore@ClusWmi@@AEAA_NAEAVToken@cxl@@PEAU_LUID@@PEAVSid@4@@Z; ClusWmi::DataStore::GetCurrentTokenModifiedIDAndSid(cxl::Token &,_LUID *,cxl::Sid *)
0x18001b93b  test    al, al
0x18001b93d  jz      loc_18001BA50
0x18001b943  xorps   xmm0, xmm0
0x18001b946  movdqu  xmmword ptr [rbp+57h+var_D0], xmm0
0x18001b94b  lea     r13, [rdi+40h]
0x18001b94f  mov     rdx, r13; struct cxl::NonReentrantRWLock *
0x18001b952  lea     rcx, [rbp+57h+var_90]; this
0x18001b956  call    ??0AcquireReadLock@cxl@@QEAA@AEAVNonReentrantRWLock@1@@Z; cxl::AcquireReadLock::AcquireReadLock(cxl::NonReentrantRWLock &)
0x18001b95b  nop
0x18001b95c  lea     r14, [rdi+50h]
0x18001b960  lea     r8, [rsp+100h+var_D8]
0x18001b965  lea     rdx, [rbp+57h+SystemTimeAsFileTime]
0x18001b969  mov     rcx, r14
0x18001b96c  call    ??$_Find_lower_bound@U_LUID@@@?$_Tree@V?$_Tmap_traits@U_LUID@@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDateTime@cxl@@@std@@ULUIDComparer@DataStore@ClusWmi@@V?$allocator@U?$pair@$$CBU_LUID@@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDateTime@cxl@@@std@@@std@@@3@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBU_LUID@@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDateTime@cxl@@@std@@@std@@PEAX@std@@@1@AEBU_LUID@@@Z; std::_Tree<std::_Tmap_traits<_LUID,std::pair<std::wstring,cxl::DateTime>,ClusWmi::DataStore::LUIDComparer,std::allocator<std::pair<_LUID const,std::pair<std::wstring,cxl::DateTime>>>,0>>::_Find_lower_bound<_LUID>(_LUID const &)
0x18001b971  lea     r8, [rsp+100h+var_D8]
0x18001b976  mov     rbx, [rbp+57h+var_A0]
0x18001b97a  mov     rdx, rbx
0x18001b97d  call    ??$_Lower_bound_duplicate@U_LUID@@@?$_Tree@V?$_Tmap_traits@U_LUID@@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDateTime@cxl@@@std@@ULUIDComparer@DataStore@ClusWmi@@V?$allocator@U?$pair@$$CBU_LUID@@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDateTime@cxl@@@std@@@std@@@3@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBU_LUID@@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDateTime@cxl@@@std@@@std@@PEAX@1@AEBU_LUID@@@Z; std::_Tree<std::_Tmap_traits<_LUID,std::pair<std::wstring,cxl::DateTime>,ClusWmi::DataStore::LUIDComparer,std::allocator<std::pair<_LUID const,std::pair<std::wstring,cxl::DateTime>>>,0>>::_Lower_bound_duplicate<_LUID>(std::_Tree_node<std::pair<_LUID const,std::pair<std::wstring,cxl::DateTime>>,void *> * const,_LUID const &)
0x18001b982  test    al, al
0x18001b984  jz      short loc_18001B9C0
0x18001b986  cmp     rbx, [r14]
0x18001b989  jz      short loc_18001B9C0
0x18001b98b  lea     rdx, [rbx+28h]
0x18001b98f  mov     rcx, r15
0x18001b992  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18001b997  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18001b99f  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001b9a3  call    cs:__imp_GetSystemTimeAsFileTime
0x18001b9a9  mov     rax, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x18001b9ad  mov     [rbx+50h], rax
0x18001b9b1  lea     rcx, [rbp+57h+var_90]
0x18001b9b5  call    ?Release@?$ScopedResOwner@VNonReentrantRWLock@cxl@@V?$AcquireSharedTraits@VNonReentrantRWLock@cxl@@@2@@cxl@@QEBAXXZ; cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireSharedTraits<cxl::NonReentrantRWLock>>::Release(void)
0x18001b9ba  nop
0x18001b9bb  jmp     loc_18001BBBC
0x18001b9c0  lea     rsi, [rdi+70h]
0x18001b9c4  mov     rdx, rsi
0x18001b9c7  lea     rcx, [rbp+57h+var_D0]
0x18001b9cb  call    ??4?$shared_ptr@VCacheObject@DataStore@ClusWmi@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<ClusWmi::DataStore::CacheObject>::operator=(std::shared_ptr<ClusWmi::DataStore::CacheObject> const &)
0x18001b9d0  nop
0x18001b9d1  lea     rcx, [rbp+57h+var_90]
0x18001b9d5  call    ?Release@?$ScopedResOwner@VNonReentrantRWLock@cxl@@V?$AcquireSharedTraits@VNonReentrantRWLock@cxl@@@2@@cxl@@QEBAXXZ; cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireSharedTraits<cxl::NonReentrantRWLock>>::Release(void)
0x18001b9da  mov     rbx, [rbp+57h+var_D0]
0x18001b9de  test    rbx, rbx
0x18001b9e1  jnz     loc_18001BA84
0x18001b9e7  xorps   xmm0, xmm0
0x18001b9ea  movdqu  xmmword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], xmm0
0x18001b9ef  mov     rcx, [rdi]
0x18001b9f2  mov     rax, [rcx]
0x18001b9f5  lea     rdx, [rbp+57h+SystemTimeAsFileTime]
0x18001b9f9  mov     rax, [rax+30h]
0x18001b9fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba02  mov     edi, eax
0x18001ba04  test    eax, eax
0x18001ba06  js      short loc_18001BA30
0x18001ba08  mov     rcx, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x18001ba0c  mov     rax, [rcx]
0x18001ba0f  xor     edx, edx
0x18001ba11  mov     rax, [rax]
0x18001ba14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba19  mov     edi, eax
0x18001ba1b  test    eax, eax
0x18001ba1d  js      short loc_18001BA30
0x18001ba1f  lea     rdx, [rbp+57h+SystemTimeAsFileTime]
0x18001ba23  lea     rcx, [rbp+57h+var_D0]
0x18001ba27  call    ??4?$shared_ptr@VCacheObject@DataStore@ClusWmi@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<ClusWmi::DataStore::CacheObject>::operator=(std::shared_ptr<ClusWmi::DataStore::CacheObject> const &)
0x18001ba2c  mov     rbx, [rbp+57h+var_D0]
0x18001ba30  mov     rcx, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime+8]; this
0x18001ba34  test    rcx, rcx
0x18001ba37  jz      short loc_18001BA3E
0x18001ba39  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001ba3e  test    edi, edi
0x18001ba40  jns     short loc_18001BA84
0x18001ba42  mov     rcx, [rbp+57h+var_D0+8]; this
0x18001ba46  test    rcx, rcx
0x18001ba49  jz      short loc_18001BA50
0x18001ba4b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001ba50  xor     ebx, ebx
0x18001ba52  lea     rcx, [rbp+57h+var_C0]; this
0x18001ba56  call    ?Clear@Token@cxl@@QEAAXXZ; cxl::Token::Clear(void)
0x18001ba5b  mov     al, bl
0x18001ba5d  mov     rcx, [rbp+57h+var_40]
0x18001ba61  xor     rcx, rsp; StackCookie
0x18001ba64  call    __security_check_cookie
0x18001ba69  mov     rbx, [rsp+100h+arg_18]
0x18001ba71  add     rsp, 0D0h
0x18001ba78  pop     r15
0x18001ba7a  pop     r14
0x18001ba7c  pop     r13
0x18001ba7e  pop     r12
0x18001ba80  pop     rdi
0x18001ba81  pop     rsi
0x18001ba82  pop     rbp
0x18001ba83  retn
0x18001ba84  mov     [rsp+100h+var_E0], 0
0x18001ba8c  mov     rax, [rbx]
0x18001ba8f  lea     r8, [rsp+100h+var_E0]
0x18001ba94  mov     rdx, [rbp+57h+var_B8]
0x18001ba98  mov     rcx, rbx
0x18001ba9b  mov     rax, [rax+40h]
0x18001ba9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001baa4  test    eax, eax
0x18001baa6  js      short loc_18001BA42
0x18001baa8  lea     rdx, [rbp+57h+var_90]
0x18001baac  mov     rcx, r12
0x18001baaf  call    ?ToString@SidBase@cxl@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; cxl::SidBase::ToString(void)
0x18001bab4  mov     rdx, rax
0x18001bab7  mov     rcx, r15
0x18001baba  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001babf  lea     rcx, [rbp+57h+var_90]
0x18001bac3  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001bac8  mov     edx, [rsp+100h+var_E0]
0x18001bacc  lea     rcx, [rbp+57h+var_90]
0x18001bad0  call    ??$_Integral_to_string@_WK@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@K@Z; std::_Integral_to_string<wchar_t,ulong>(ulong)
0x18001bad5  nop
0x18001bad6  lea     rdx, aAccess; "Access"
0x18001badd  lea     rcx, [rbp+57h+var_70]
0x18001bae1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001bae6  nop
0x18001bae7  lea     r8, [rbp+57h+var_90]
0x18001baeb  mov     rdx, rax
0x18001baee  lea     rcx, [rbp+57h+SystemTimeAsFileTime]
0x18001baf2  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@0@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring &&)
0x18001baf7  nop
0x18001baf8  mov     rdx, rax
0x18001bafb  mov     rcx, r15
0x18001bafe  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18001bb03  nop
0x18001bb04  lea     rcx, [rbp+57h+SystemTimeAsFileTime]
0x18001bb08  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001bb0d  nop
0x18001bb0e  lea     rcx, [rbp+57h+var_70]
0x18001bb12  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001bb17  nop
0x18001bb18  lea     rcx, [rbp+57h+var_90]
0x18001bb1c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001bb21  mov     rdx, r13; struct cxl::NonReentrantRWLock *
0x18001bb24  lea     rcx, [rbp+57h+var_90]; this
0x18001bb28  call    ??0AcquireWriteLock@cxl@@QEAA@AEAVNonReentrantRWLock@1@@Z; cxl::AcquireWriteLock::AcquireWriteLock(cxl::NonReentrantRWLock &)
0x18001bb2d  nop
0x18001bb2e  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18001bb36  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001bb3a  call    cs:__imp_GetSystemTimeAsFileTime
0x18001bb40  mov     rdx, r15
0x18001bb43  lea     rcx, [rbp+57h+var_70]
0x18001bb47  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001bb4c  lea     rax, ??_7DateTime@cxl@@6B@; const cxl::DateTime::`vftable'
0x18001bb53  mov     [rbp+57h+var_50], rax
0x18001bb57  mov     rax, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x18001bb5b  mov     [rbp+57h+var_48], rax
0x18001bb5f  lea     r8, [rsp+100h+var_D8]
0x18001bb64  lea     rdx, [rbp+57h+SystemTimeAsFileTime]
0x18001bb68  mov     rcx, r14
0x18001bb6b  call    ??$_Try_emplace@AEBU_LUID@@$$V@?$map@U_LUID@@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDateTime@cxl@@@std@@ULUIDComparer@DataStore@ClusWmi@@V?$allocator@U?$pair@$$CBU_LUID@@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDateTime@cxl@@@std@@@std@@@3@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBU_LUID@@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDateTime@cxl@@@std@@@std@@PEAX@std@@_N@1@AEBU_LUID@@@Z; std::map<_LUID,std::pair<std::wstring,cxl::DateTime>,ClusWmi::DataStore::LUIDComparer,std::allocator<std::pair<_LUID const,std::pair<std::wstring,cxl::DateTime>>>>::_Try_emplace<_LUID const &,>(_LUID const &)
0x18001bb70  mov     rbx, [rax]
0x18001bb73  lea     rdx, [rbp+57h+var_70]
0x18001bb77  lea     rcx, [rbx+28h]
0x18001bb7b  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001bb80  mov     rax, [rbp+57h+var_48]
0x18001bb84  mov     [rbx+50h], rax
0x18001bb88  lea     rcx, [rbp+57h+var_70]
0x18001bb8c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001bb91  cmp     qword ptr [rsi], 0
0x18001bb95  jnz     short loc_18001BBA4
0x18001bb97  lea     rdx, [rbp+57h+var_D0]
0x18001bb9b  mov     rcx, rsi
0x18001bb9e  call    ??4?$shared_ptr@VCacheObject@DataStore@ClusWmi@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<ClusWmi::DataStore::CacheObject>::operator=(std::shared_ptr<ClusWmi::DataStore::CacheObject> const &)
0x18001bba3  nop
0x18001bba4  lea     rcx, [rbp+57h+var_90]
0x18001bba8  call    ?Release@?$ScopedResOwner@VNonReentrantRWLock@cxl@@V?$AcquireExclusiveTraits@VNonReentrantRWLock@cxl@@@2@@cxl@@QEBAXXZ; cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireExclusiveTraits<cxl::NonReentrantRWLock>>::Release(void)
0x18001bbad  nop
0x18001bbae  mov     rcx, [rbp+57h+var_D0+8]; this
0x18001bbb2  test    rcx, rcx
0x18001bbb5  jz      short loc_18001BBBC
0x18001bbb7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001bbbc  mov     bl, 1
0x18001bbbe  jmp     loc_18001BA52
```
