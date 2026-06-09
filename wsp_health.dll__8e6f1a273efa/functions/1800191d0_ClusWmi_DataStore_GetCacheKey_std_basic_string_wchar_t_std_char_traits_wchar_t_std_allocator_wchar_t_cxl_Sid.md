# ClusWmi::DataStore::GetCacheKey(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,cxl::Sid &)

- ea: `0x1800191d0`
- end: `0x1800194b6`
- name: `?GetCacheKey@DataStore@ClusWmi@@AEAA_NAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVSid@cxl@@@Z`
- size: `742`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180019720`

## callees

- `0x180002b50`
- `0x18000bc64`
- `0x18000cd54`
- `0x18000cd9c`
- `0x18000d390`
- `0x18000daf8`
- `0x180012f5c`
- `0x180014620`
- `0x18001633c`
- `0x18001791c`
- `0x180017a6c`
- `0x180017af0`
- `0x180017b54`
- `0x180017dc0`
- `0x180017f7c`
- `0x180017fcc`
- `0x180018af0`
- `0x1800191d0`
- `0x1800198ec`
- `0x18001aef0`
- `0x18001af54`
- `0x18001c318`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180019287`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180019426`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180019287`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180019426`

## string_xrefs

- `0x1800193c1`: `Access`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
char __fastcall ClusWmi::DataStore::GetCacheKey(ClusWmi::DataStore *a1, __int64 a2, struct cxl::Sid *a3)
{
  RTL_SRWLOCK *v6; // r13
  struct _FILETIME **v7; // r14
  struct _FILETIME *v8; // rbx
  __int64 v9; // rcx
  _QWORD *v10; // rsi
  std::_Ref_count_base *v11; // rbx
  int v12; // edi
  char v13; // bl
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rdx
  struct _FILETIME *v18; // rbx
  unsigned int v19; // [rsp+20h] [rbp-89h] BYREF
  _LUID v20; // [rsp+28h] [rbp-81h] BYREF
  std::_Ref_count_base *v21[2]; // [rsp+30h] [rbp-79h] BYREF
  void *v22; // [rsp+40h] [rbp-69h] BYREF
  __int64 v23; // [rsp+48h] [rbp-61h]
  struct _FILETIME SystemTimeAsFileTime[2]; // [rsp+50h] [rbp-59h] BYREF
  struct _FILETIME *v25; // [rsp+60h] [rbp-49h]
  _BYTE v26[32]; // [rsp+70h] [rbp-39h] BYREF
  _BYTE v27[32]; // [rsp+90h] [rbp-19h] BYREF
  void **v28; // [rsp+B0h] [rbp+7h]
  struct _FILETIME v29; // [rsp+B8h] [rbp+Fh]

  v23 = 0;
  v20 = 0;
  if ( ClusWmi::DataStore::GetCurrentTokenModifiedIDAndSid(a1, &v22, &v20, a3) )
  {
    *(_OWORD *)v21 = 0;
    v6 = (RTL_SRWLOCK *)((char *)a1 + 64);
    cxl::AcquireReadLock::AcquireReadLock((cxl::AcquireReadLock *)v26, (ClusWmi::DataStore *)((char *)a1 + 64));
    v7 = (struct _FILETIME **)((char *)a1 + 80);
    std::_Tree<std::_Tmap_traits<_LUID,std::pair<std::wstring,cxl::DateTime>,ClusWmi::DataStore::LUIDComparer,std::allocator<std::pair<_LUID const,std::pair<std::wstring,cxl::DateTime>>>,0>>::_Find_lower_bound<_LUID>(
      (char *)a1 + 80,
      SystemTimeAsFileTime,
      &v20);
    v8 = v25;
    if ( (unsigned __int8)std::_Tree<std::_Tmap_traits<_LUID,std::pair<std::wstring,cxl::DateTime>,ClusWmi::DataStore::LUIDComparer,std::allocator<std::pair<_LUID const,std::pair<std::wstring,cxl::DateTime>>>,0>>::_Lower_bound_duplicate<_LUID>(
                            v9,
                            v25,
                            &v20)
      && v8 != *v7 )
    {
      std::wstring::operator=(a2);
      SystemTimeAsFileTime[0] = 0;
      GetSystemTimeAsFileTime(SystemTimeAsFileTime);
      v8[10] = SystemTimeAsFileTime[0];
      cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireSharedTraits<cxl::NonReentrantRWLock>>::Release(v26);
LABEL_21:
      v13 = 1;
      goto LABEL_15;
    }
    v10 = (_QWORD *)((char *)a1 + 112);
    std::shared_ptr<ClusWmi::DataStore::CacheObject>::operator=(v21, (char *)a1 + 112);
    cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireSharedTraits<cxl::NonReentrantRWLock>>::Release(v26);
    v11 = v21[0];
    if ( v21[0] )
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
        std::shared_ptr<ClusWmi::DataStore::CacheObject>::operator=(v21, SystemTimeAsFileTime);
        v11 = v21[0];
      }
    }
    if ( SystemTimeAsFileTime[1] )
      std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&SystemTimeAsFileTime[1]);
    if ( v12 >= 0 )
    {
LABEL_24:
      v19 = 0;
      if ( (*(int (__fastcall **)(std::_Ref_count_base *, __int64, unsigned int *))(*(_QWORD *)v11 + 64LL))(
             v11,
             v23,
             &v19) >= 0 )
      {
        v15 = cxl::SidBase::ToString((__int64)a3, (__int64)v26);
        std::wstring::operator=(a2, v15);
        std::wstring::_Tidy_deallocate(v26);
        std::_Integral_to_string<wchar_t,unsigned long>(SystemTimeAsFileTime, v19);
        v16 = std::wstring::wstring(v27, L"Access");
        std::wstring::wstring(v26, v17, v16, SystemTimeAsFileTime);
        std::wstring::append(a2, v26);
        std::wstring::_Tidy_deallocate(v26);
        std::wstring::_Tidy_deallocate(v27);
        std::wstring::_Tidy_deallocate(SystemTimeAsFileTime);
        cxl::AcquireWriteLock::AcquireWriteLock((cxl::AcquireWriteLock *)v26, v6);
        SystemTimeAsFileTime[0] = 0;
        GetSystemTimeAsFileTime(SystemTimeAsFileTime);
        std::wstring::wstring(v27, a2);
        v28 = &cxl::DateTime::`vftable';
        v29 = SystemTimeAsFileTime[0];
        v18 = *(struct _FILETIME **)std::map<_LUID,std::pair<std::wstring,cxl::DateTime>,ClusWmi::DataStore::LUIDComparer,std::allocator<std::pair<_LUID const,std::pair<std::wstring,cxl::DateTime>>>>::_Try_emplace<_LUID const &,>(
                                      v7,
                                      SystemTimeAsFileTime,
                                      &v20);
        std::wstring::operator=(&v18[5], v27);
        v18[10] = v29;
        std::wstring::_Tidy_deallocate(v27);
        if ( !*v10 )
          std::shared_ptr<ClusWmi::DataStore::CacheObject>::operator=(v10, v21);
        cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireExclusiveTraits<cxl::NonReentrantRWLock>>::Release((__int64)v26);
        if ( v21[1] )
          std::_Ref_count_base::_Decref(v21[1]);
        goto LABEL_21;
      }
    }
    if ( v21[1] )
      std::_Ref_count_base::_Decref(v21[1]);
  }
  v13 = 0;
LABEL_15:
  cxl::Token::Clear((cxl::Token *)&v22);
  return v13;
}

```

## disassembly

```asm
0x1800191d0  mov     [rsp-8+arg_18], rbx
0x1800191d5  push    rbp
0x1800191d6  push    rsi
0x1800191d7  push    rdi
0x1800191d8  push    r12
0x1800191da  push    r13
0x1800191dc  push    r14
0x1800191de  push    r15
0x1800191e0  lea     rbp, [rsp-27h]
0x1800191e5  sub     rsp, 0D0h
0x1800191ec  mov     rax, cs:__security_cookie
0x1800191f3  xor     rax, rsp
0x1800191f6  mov     [rbp+57h+var_40], rax
0x1800191fa  mov     r12, r8
0x1800191fd  mov     r15, rdx
0x180019200  mov     rdi, rcx
0x180019203  xor     eax, eax
0x180019205  mov     [rbp+57h+var_B8], rax
0x180019209  mov     qword ptr [rsp+100h+var_D8.LowPart], rax
0x18001920e  mov     r9, r8; struct cxl::Sid *
0x180019211  lea     r8, [rsp+100h+var_D8]; struct _LUID *
0x180019216  lea     rdx, [rbp+57h+var_C0]; struct cxl::Token *
0x18001921a  call    ?GetCurrentTokenModifiedIDAndSid@DataStore@ClusWmi@@AEAA_NAEAVToken@cxl@@PEAU_LUID@@PEAVSid@4@@Z; ClusWmi::DataStore::GetCurrentTokenModifiedIDAndSid(cxl::Token &,_LUID *,cxl::Sid *)
0x18001921f  test    al, al
0x180019221  jz      loc_18001933A
0x180019227  xorps   xmm0, xmm0
0x18001922a  movdqu  xmmword ptr [rbp+57h+var_D0], xmm0
0x18001922f  lea     r13, [rdi+40h]
0x180019233  mov     rdx, r13; struct cxl::NonReentrantRWLock *
0x180019236  lea     rcx, [rbp+57h+var_90]; this
0x18001923a  call    ??0AcquireReadLock@cxl@@QEAA@AEAVNonReentrantRWLock@1@@Z; cxl::AcquireReadLock::AcquireReadLock(cxl::NonReentrantRWLock &)
0x18001923f  nop
0x180019240  lea     r14, [rdi+50h]
0x180019244  lea     r8, [rsp+100h+var_D8]
0x180019249  lea     rdx, [rbp+57h+SystemTimeAsFileTime]
0x18001924d  mov     rcx, r14
0x180019250  call    ??$_Find_lower_bound@U_LUID@@@?$_Tree@V?$_Tmap_traits@U_LUID@@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDateTime@cxl@@@std@@ULUIDComparer@DataStore@ClusWmi@@V?$allocator@U?$pair@$$CBU_LUID@@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDateTime@cxl@@@std@@@std@@@3@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBU_LUID@@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDateTime@cxl@@@std@@@std@@PEAX@std@@@1@AEBU_LUID@@@Z; std::_Tree<std::_Tmap_traits<_LUID,std::pair<std::wstring,cxl::DateTime>,ClusWmi::DataStore::LUIDComparer,std::allocator<std::pair<_LUID const,std::pair<std::wstring,cxl::DateTime>>>,0>>::_Find_lower_bound<_LUID>(_LUID const &)
0x180019255  lea     r8, [rsp+100h+var_D8]
0x18001925a  mov     rbx, [rbp+57h+var_A0]
0x18001925e  mov     rdx, rbx
0x180019261  call    ??$_Lower_bound_duplicate@U_LUID@@@?$_Tree@V?$_Tmap_traits@U_LUID@@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDateTime@cxl@@@std@@ULUIDComparer@DataStore@ClusWmi@@V?$allocator@U?$pair@$$CBU_LUID@@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDateTime@cxl@@@std@@@std@@@3@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBU_LUID@@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDateTime@cxl@@@std@@@std@@PEAX@1@AEBU_LUID@@@Z; std::_Tree<std::_Tmap_traits<_LUID,std::pair<std::wstring,cxl::DateTime>,ClusWmi::DataStore::LUIDComparer,std::allocator<std::pair<_LUID const,std::pair<std::wstring,cxl::DateTime>>>,0>>::_Lower_bound_duplicate<_LUID>(std::_Tree_node<std::pair<_LUID const,std::pair<std::wstring,cxl::DateTime>>,void *> * const,_LUID const &)
0x180019266  test    al, al
0x180019268  jz      short loc_1800192AA
0x18001926a  cmp     rbx, [r14]
0x18001926d  jz      short loc_1800192AA
0x18001926f  lea     rdx, [rbx+28h]
0x180019273  mov     rcx, r15
0x180019276  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18001927b  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180019283  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180019287  call    cs:__imp_GetSystemTimeAsFileTime
0x18001928e  nop     dword ptr [rax+rax+00h]
0x180019293  mov     rax, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x180019297  mov     [rbx+50h], rax
0x18001929b  lea     rcx, [rbp+57h+var_90]
0x18001929f  call    ?Release@?$ScopedResOwner@VNonReentrantRWLock@cxl@@V?$AcquireSharedTraits@VNonReentrantRWLock@cxl@@@2@@cxl@@QEBAXXZ; cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireSharedTraits<cxl::NonReentrantRWLock>>::Release(void)
0x1800192a4  nop
0x1800192a5  jmp     loc_1800194AE
0x1800192aa  lea     rsi, [rdi+70h]
0x1800192ae  mov     rdx, rsi
0x1800192b1  lea     rcx, [rbp+57h+var_D0]
0x1800192b5  call    ??4?$shared_ptr@VCacheObject@DataStore@ClusWmi@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<ClusWmi::DataStore::CacheObject>::operator=(std::shared_ptr<ClusWmi::DataStore::CacheObject> const &)
0x1800192ba  nop
0x1800192bb  lea     rcx, [rbp+57h+var_90]
0x1800192bf  call    ?Release@?$ScopedResOwner@VNonReentrantRWLock@cxl@@V?$AcquireSharedTraits@VNonReentrantRWLock@cxl@@@2@@cxl@@QEBAXXZ; cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireSharedTraits<cxl::NonReentrantRWLock>>::Release(void)
0x1800192c4  mov     rbx, [rbp+57h+var_D0]
0x1800192c8  test    rbx, rbx
0x1800192cb  jnz     loc_18001936F
0x1800192d1  xorps   xmm0, xmm0
0x1800192d4  movdqu  xmmword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], xmm0
0x1800192d9  mov     rcx, [rdi]
0x1800192dc  mov     rax, [rcx]
0x1800192df  lea     rdx, [rbp+57h+SystemTimeAsFileTime]
0x1800192e3  mov     rax, [rax+30h]
0x1800192e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800192ec  mov     edi, eax
0x1800192ee  test    eax, eax
0x1800192f0  js      short loc_18001931A
0x1800192f2  mov     rcx, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x1800192f6  mov     rax, [rcx]
0x1800192f9  xor     edx, edx
0x1800192fb  mov     rax, [rax]
0x1800192fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019303  mov     edi, eax
0x180019305  test    eax, eax
0x180019307  js      short loc_18001931A
0x180019309  lea     rdx, [rbp+57h+SystemTimeAsFileTime]
0x18001930d  lea     rcx, [rbp+57h+var_D0]
0x180019311  call    ??4?$shared_ptr@VCacheObject@DataStore@ClusWmi@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<ClusWmi::DataStore::CacheObject>::operator=(std::shared_ptr<ClusWmi::DataStore::CacheObject> const &)
0x180019316  mov     rbx, [rbp+57h+var_D0]
0x18001931a  mov     rcx, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime+8]; this
0x18001931e  test    rcx, rcx
0x180019321  jz      short loc_180019328
0x180019323  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180019328  test    edi, edi
0x18001932a  jns     short loc_18001936F
0x18001932c  mov     rcx, [rbp+57h+var_D0+8]; this
0x180019330  test    rcx, rcx
0x180019333  jz      short loc_18001933A
0x180019335  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001933a  xor     ebx, ebx
0x18001933c  lea     rcx, [rbp+57h+var_C0]; this
0x180019340  call    ?Clear@Token@cxl@@QEAAXXZ; cxl::Token::Clear(void)
0x180019345  mov     al, bl
0x180019347  mov     rcx, [rbp+57h+var_40]
0x18001934b  xor     rcx, rsp; StackCookie
0x18001934e  call    __security_check_cookie
0x180019353  mov     rbx, [rsp+100h+arg_18]
0x18001935b  add     rsp, 0D0h
0x180019362  pop     r15
0x180019364  pop     r14
0x180019366  pop     r13
0x180019368  pop     r12
0x18001936a  pop     rdi
0x18001936b  pop     rsi
0x18001936c  pop     rbp
0x18001936d  retn
0x18001936f  mov     [rsp+100h+var_E0], 0
0x180019377  mov     rax, [rbx]
0x18001937a  lea     r8, [rsp+100h+var_E0]
0x18001937f  mov     rdx, [rbp+57h+var_B8]
0x180019383  mov     rcx, rbx
0x180019386  mov     rax, [rax+40h]
0x18001938a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001938f  test    eax, eax
0x180019391  js      short loc_18001932C
0x180019393  lea     rdx, [rbp+57h+var_90]
0x180019397  mov     rcx, r12
0x18001939a  call    ?ToString@SidBase@cxl@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; cxl::SidBase::ToString(void)
0x18001939f  mov     rdx, rax
0x1800193a2  mov     rcx, r15
0x1800193a5  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800193aa  lea     rcx, [rbp+57h+var_90]
0x1800193ae  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800193b3  mov     edx, [rsp+100h+var_E0]
0x1800193b7  lea     rcx, [rbp+57h+SystemTimeAsFileTime]
0x1800193bb  call    ??$_Integral_to_string@_WK@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@K@Z; std::_Integral_to_string<wchar_t,ulong>(ulong)
0x1800193c0  nop
0x1800193c1  lea     rdx, aAccess; "Access"
0x1800193c8  lea     rcx, [rbp+57h+var_70]
0x1800193cc  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800193d1  nop
0x1800193d2  lea     r9, [rbp+57h+SystemTimeAsFileTime]
0x1800193d6  mov     r8, rax
0x1800193d9  lea     rcx, [rbp+57h+var_90]
0x1800193dd  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring &,std::wstring &)
0x1800193e2  nop
0x1800193e3  lea     rdx, [rbp+57h+var_90]
0x1800193e7  mov     rcx, r15
0x1800193ea  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x1800193ef  nop
0x1800193f0  lea     rcx, [rbp+57h+var_90]
0x1800193f4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800193f9  nop
0x1800193fa  lea     rcx, [rbp+57h+var_70]
0x1800193fe  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019403  nop
0x180019404  lea     rcx, [rbp+57h+SystemTimeAsFileTime]
0x180019408  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001940d  mov     rdx, r13; struct cxl::NonReentrantRWLock *
0x180019410  lea     rcx, [rbp+57h+var_90]; this
0x180019414  call    ??0AcquireWriteLock@cxl@@QEAA@AEAVNonReentrantRWLock@1@@Z; cxl::AcquireWriteLock::AcquireWriteLock(cxl::NonReentrantRWLock &)
0x180019419  nop
0x18001941a  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180019422  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180019426  call    cs:__imp_GetSystemTimeAsFileTime
0x18001942d  nop     dword ptr [rax+rax+00h]
0x180019432  mov     rdx, r15
0x180019435  lea     rcx, [rbp+57h+var_70]
0x180019439  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001943e  lea     rax, ??_7DateTime@cxl@@6B@; const cxl::DateTime::`vftable'
0x180019445  mov     [rbp+57h+var_50], rax
0x180019449  mov     rax, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x18001944d  mov     [rbp+57h+var_48], rax
0x180019451  lea     r8, [rsp+100h+var_D8]
0x180019456  lea     rdx, [rbp+57h+SystemTimeAsFileTime]
0x18001945a  mov     rcx, r14
0x18001945d  call    ??$_Try_emplace@AEBU_LUID@@$$V@?$map@U_LUID@@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDateTime@cxl@@@std@@ULUIDComparer@DataStore@ClusWmi@@V?$allocator@U?$pair@$$CBU_LUID@@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDateTime@cxl@@@std@@@std@@@3@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBU_LUID@@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDateTime@cxl@@@std@@@std@@PEAX@std@@_N@1@AEBU_LUID@@@Z; std::map<_LUID,std::pair<std::wstring,cxl::DateTime>,ClusWmi::DataStore::LUIDComparer,std::allocator<std::pair<_LUID const,std::pair<std::wstring,cxl::DateTime>>>>::_Try_emplace<_LUID const &,>(_LUID const &)
0x180019462  mov     rbx, [rax]
0x180019465  lea     rdx, [rbp+57h+var_70]
0x180019469  lea     rcx, [rbx+28h]
0x18001946d  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180019472  mov     rax, [rbp+57h+var_48]
0x180019476  mov     [rbx+50h], rax
0x18001947a  lea     rcx, [rbp+57h+var_70]
0x18001947e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019483  cmp     qword ptr [rsi], 0
0x180019487  jnz     short loc_180019496
0x180019489  lea     rdx, [rbp+57h+var_D0]
0x18001948d  mov     rcx, rsi
0x180019490  call    ??4?$shared_ptr@VCacheObject@DataStore@ClusWmi@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<ClusWmi::DataStore::CacheObject>::operator=(std::shared_ptr<ClusWmi::DataStore::CacheObject> const &)
0x180019495  nop
0x180019496  lea     rcx, [rbp+57h+var_90]
0x18001949a  call    ?Release@?$ScopedResOwner@VNonReentrantRWLock@cxl@@V?$AcquireExclusiveTraits@VNonReentrantRWLock@cxl@@@2@@cxl@@QEBAXXZ; cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireExclusiveTraits<cxl::NonReentrantRWLock>>::Release(void)
0x18001949f  nop
0x1800194a0  mov     rcx, [rbp+57h+var_D0+8]; this
0x1800194a4  test    rcx, rcx
0x1800194a7  jz      short loc_1800194AE
0x1800194a9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800194ae  mov     bl, 1
0x1800194b0  jmp     loc_18001933C
```
