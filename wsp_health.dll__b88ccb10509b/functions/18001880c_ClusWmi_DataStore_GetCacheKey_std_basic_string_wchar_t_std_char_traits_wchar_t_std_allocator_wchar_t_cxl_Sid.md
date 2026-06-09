# ClusWmi::DataStore::GetCacheKey(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,cxl::Sid &)

- ea: `0x18001880c`
- end: `0x180018ae5`
- name: `?GetCacheKey@DataStore@ClusWmi@@AEAA_NAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVSid@cxl@@@Z`
- size: `729`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180018d50`

## callees

- `0x180002ae0`
- `0x18000b8e4`
- `0x18000c9a8`
- `0x18000c9f0`
- `0x18000cfb4`
- `0x18000d6dc`
- `0x18001293c`
- `0x180013ec0`
- `0x180015b24`
- `0x180016fe4`
- `0x180017134`
- `0x1800171b8`
- `0x180017218`
- `0x180017484`
- `0x180017640`
- `0x180017688`
- `0x180018154`
- `0x18001880c`
- `0x180018f1c`
- `0x18001a470`
- `0x18001a4c8`
- `0x18001b7f4`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800188c3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180018a5b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800188c3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180018a5b`

## string_xrefs

- `0x1800189f6`: `Access`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
char __fastcall ClusWmi::DataStore::GetCacheKey(ClusWmi::DataStore *a1, __int64 a2, struct cxl::Sid *a3)
{
  RTL_SRWLOCK *v6; // r13
  __int64 *v7; // r14
  struct _FILETIME *v8; // rbx
  __int64 v9; // rcx
  __int64 v10; // rdx
  _QWORD *v11; // rsi
  __int64 v12; // rdx
  std::_Ref_count_base *v13; // rbx
  int v14; // edi
  char v15; // bl
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rdx
  struct _FILETIME *v20; // rbx
  unsigned int v21; // [rsp+20h] [rbp-89h] BYREF
  _LUID v22; // [rsp+28h] [rbp-81h] BYREF
  std::_Ref_count_base *v23[2]; // [rsp+30h] [rbp-79h] BYREF
  void *v24; // [rsp+40h] [rbp-69h] BYREF
  __int64 v25; // [rsp+48h] [rbp-61h]
  struct _FILETIME SystemTimeAsFileTime[2]; // [rsp+50h] [rbp-59h] BYREF
  struct _FILETIME *v27; // [rsp+60h] [rbp-49h]
  _BYTE v28[32]; // [rsp+70h] [rbp-39h] BYREF
  _BYTE v29[32]; // [rsp+90h] [rbp-19h] BYREF
  void **v30; // [rsp+B0h] [rbp+7h]
  struct _FILETIME v31; // [rsp+B8h] [rbp+Fh]

  v25 = 0;
  v22 = 0;
  if ( ClusWmi::DataStore::GetCurrentTokenModifiedIDAndSid(a1, &v24, &v22, a3) )
  {
    *(_OWORD *)v23 = 0;
    v6 = (RTL_SRWLOCK *)((char *)a1 + 64);
    cxl::AcquireReadLock::AcquireReadLock((cxl::AcquireReadLock *)v28, (ClusWmi::DataStore *)((char *)a1 + 64));
    v7 = (__int64 *)((char *)a1 + 80);
    std::_Tree<std::_Tmap_traits<_LUID,std::pair<std::wstring,cxl::DateTime>,ClusWmi::DataStore::LUIDComparer,std::allocator<std::pair<_LUID const,std::pair<std::wstring,cxl::DateTime>>>,0>>::_Find_lower_bound<_LUID>(
      (__int64)a1 + 80,
      SystemTimeAsFileTime,
      (unsigned int *)&v22);
    v8 = v27;
    if ( std::_Tree<std::_Tmap_traits<_LUID,std::pair<std::wstring,cxl::DateTime>,ClusWmi::DataStore::LUIDComparer,std::allocator<std::pair<_LUID const,std::pair<std::wstring,cxl::DateTime>>>,0>>::_Lower_bound_duplicate<_LUID>(
           v9,
           (__int64)v27,
           (unsigned int *)&v22)
      && v8 != (struct _FILETIME *)*v7 )
    {
      std::wstring::operator=(a2, &v8[5]);
      SystemTimeAsFileTime[0] = 0;
      GetSystemTimeAsFileTime(SystemTimeAsFileTime);
      v8[10] = SystemTimeAsFileTime[0];
      cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireSharedTraits<cxl::NonReentrantRWLock>>::Release(v28, v10);
LABEL_21:
      v15 = 1;
      goto LABEL_15;
    }
    v11 = (_QWORD *)((char *)a1 + 112);
    std::shared_ptr<ClusWmi::DataStore::CacheObject>::operator=(v23, (char *)a1 + 112);
    cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireSharedTraits<cxl::NonReentrantRWLock>>::Release(v28, v12);
    v13 = v23[0];
    if ( v23[0] )
      goto LABEL_24;
    *(_OWORD *)&SystemTimeAsFileTime[0].dwLowDateTime = 0;
    v14 = (*(__int64 (__fastcall **)(_QWORD, struct _FILETIME *))(**(_QWORD **)a1 + 48LL))(
            *(_QWORD *)a1,
            SystemTimeAsFileTime);
    if ( v14 >= 0 )
    {
      v14 = (***(__int64 (__fastcall ****)(_QWORD, _QWORD))SystemTimeAsFileTime)(*(_QWORD *)SystemTimeAsFileTime, 0);
      if ( v14 >= 0 )
      {
        std::shared_ptr<ClusWmi::DataStore::CacheObject>::operator=(v23, SystemTimeAsFileTime);
        v13 = v23[0];
      }
    }
    if ( SystemTimeAsFileTime[1] )
      std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&SystemTimeAsFileTime[1]);
    if ( v14 >= 0 )
    {
LABEL_24:
      v21 = 0;
      if ( (*(int (__fastcall **)(std::_Ref_count_base *, __int64, unsigned int *))(*(_QWORD *)v13 + 64LL))(
             v13,
             v25,
             &v21) >= 0 )
      {
        v17 = cxl::SidBase::ToString((__int64)a3, (__int64)v28);
        std::wstring::operator=(a2, v17);
        std::wstring::_Tidy_deallocate(v28);
        std::_Integral_to_string<wchar_t,unsigned long>(SystemTimeAsFileTime, v21);
        v18 = std::wstring::wstring(v29, L"Access");
        std::wstring::wstring(v28, v19, v18, SystemTimeAsFileTime);
        std::wstring::append(a2, v28);
        std::wstring::_Tidy_deallocate(v28);
        std::wstring::_Tidy_deallocate(v29);
        std::wstring::_Tidy_deallocate(SystemTimeAsFileTime);
        cxl::AcquireWriteLock::AcquireWriteLock((cxl::AcquireWriteLock *)v28, v6);
        SystemTimeAsFileTime[0] = 0;
        GetSystemTimeAsFileTime(SystemTimeAsFileTime);
        std::wstring::wstring(v29, a2);
        v30 = &cxl::DateTime::`vftable';
        v31 = SystemTimeAsFileTime[0];
        v20 = *(struct _FILETIME **)std::map<_LUID,std::pair<std::wstring,cxl::DateTime>,ClusWmi::DataStore::LUIDComparer,std::allocator<std::pair<_LUID const,std::pair<std::wstring,cxl::DateTime>>>>::_Try_emplace<_LUID const &,>(
                                      v7,
                                      (__int64)SystemTimeAsFileTime,
                                      (unsigned int *)&v22);
        std::wstring::operator=(&v20[5], v29);
        v20[10] = v31;
        std::wstring::_Tidy_deallocate(v29);
        if ( !*v11 )
          std::shared_ptr<ClusWmi::DataStore::CacheObject>::operator=(v11, v23);
        cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireExclusiveTraits<cxl::NonReentrantRWLock>>::Release((__int64)v28);
        if ( v23[1] )
          std::_Ref_count_base::_Decref(v23[1]);
        goto LABEL_21;
      }
    }
    if ( v23[1] )
      std::_Ref_count_base::_Decref(v23[1]);
  }
  v15 = 0;
LABEL_15:
  cxl::Token::Clear((cxl::Token *)&v24);
  return v15;
}

```

## disassembly

```asm
0x18001880c  mov     [rsp-8+arg_18], rbx
0x180018811  push    rbp
0x180018812  push    rsi
0x180018813  push    rdi
0x180018814  push    r12
0x180018816  push    r13
0x180018818  push    r14
0x18001881a  push    r15
0x18001881c  lea     rbp, [rsp-27h]
0x180018821  sub     rsp, 0D0h
0x180018828  mov     rax, cs:__security_cookie
0x18001882f  xor     rax, rsp
0x180018832  mov     [rbp+57h+var_40], rax
0x180018836  mov     r12, r8
0x180018839  mov     r15, rdx
0x18001883c  mov     rdi, rcx
0x18001883f  xor     eax, eax
0x180018841  mov     [rbp+57h+var_B8], rax
0x180018845  mov     qword ptr [rsp+100h+var_D8.LowPart], rax
0x18001884a  mov     r9, r8; struct cxl::Sid *
0x18001884d  lea     r8, [rsp+100h+var_D8]; struct _LUID *
0x180018852  lea     rdx, [rbp+57h+var_C0]; struct cxl::Token *
0x180018856  call    ?GetCurrentTokenModifiedIDAndSid@DataStore@ClusWmi@@AEAA_NAEAVToken@cxl@@PEAU_LUID@@PEAVSid@4@@Z; ClusWmi::DataStore::GetCurrentTokenModifiedIDAndSid(cxl::Token &,_LUID *,cxl::Sid *)
0x18001885b  test    al, al
0x18001885d  jz      loc_180018970
0x180018863  xorps   xmm0, xmm0
0x180018866  movdqu  xmmword ptr [rbp+57h+var_D0], xmm0
0x18001886b  lea     r13, [rdi+40h]
0x18001886f  mov     rdx, r13; struct cxl::NonReentrantRWLock *
0x180018872  lea     rcx, [rbp+57h+var_90]; this
0x180018876  call    ??0AcquireReadLock@cxl@@QEAA@AEAVNonReentrantRWLock@1@@Z; cxl::AcquireReadLock::AcquireReadLock(cxl::NonReentrantRWLock &)
0x18001887b  nop
0x18001887c  lea     r14, [rdi+50h]
0x180018880  lea     r8, [rsp+100h+var_D8]
0x180018885  lea     rdx, [rbp+57h+SystemTimeAsFileTime]
0x180018889  mov     rcx, r14
0x18001888c  call    ??$_Find_lower_bound@U_LUID@@@?$_Tree@V?$_Tmap_traits@U_LUID@@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDateTime@cxl@@@std@@ULUIDComparer@DataStore@ClusWmi@@V?$allocator@U?$pair@$$CBU_LUID@@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDateTime@cxl@@@std@@@std@@@3@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBU_LUID@@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDateTime@cxl@@@std@@@std@@PEAX@std@@@1@AEBU_LUID@@@Z; std::_Tree<std::_Tmap_traits<_LUID,std::pair<std::wstring,cxl::DateTime>,ClusWmi::DataStore::LUIDComparer,std::allocator<std::pair<_LUID const,std::pair<std::wstring,cxl::DateTime>>>,0>>::_Find_lower_bound<_LUID>(_LUID const &)
0x180018891  lea     r8, [rsp+100h+var_D8]
0x180018896  mov     rbx, [rbp+57h+var_A0]
0x18001889a  mov     rdx, rbx
0x18001889d  call    ??$_Lower_bound_duplicate@U_LUID@@@?$_Tree@V?$_Tmap_traits@U_LUID@@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDateTime@cxl@@@std@@ULUIDComparer@DataStore@ClusWmi@@V?$allocator@U?$pair@$$CBU_LUID@@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDateTime@cxl@@@std@@@std@@@3@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBU_LUID@@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDateTime@cxl@@@std@@@std@@PEAX@1@AEBU_LUID@@@Z; std::_Tree<std::_Tmap_traits<_LUID,std::pair<std::wstring,cxl::DateTime>,ClusWmi::DataStore::LUIDComparer,std::allocator<std::pair<_LUID const,std::pair<std::wstring,cxl::DateTime>>>,0>>::_Lower_bound_duplicate<_LUID>(std::_Tree_node<std::pair<_LUID const,std::pair<std::wstring,cxl::DateTime>>,void *> * const,_LUID const &)
0x1800188a2  test    al, al
0x1800188a4  jz      short loc_1800188E0
0x1800188a6  cmp     rbx, [r14]
0x1800188a9  jz      short loc_1800188E0
0x1800188ab  lea     rdx, [rbx+28h]
0x1800188af  mov     rcx, r15
0x1800188b2  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800188b7  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800188bf  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800188c3  call    cs:__imp_GetSystemTimeAsFileTime
0x1800188c9  mov     rax, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x1800188cd  mov     [rbx+50h], rax
0x1800188d1  lea     rcx, [rbp+57h+var_90]
0x1800188d5  call    ?Release@?$ScopedResOwner@VNonReentrantRWLock@cxl@@V?$AcquireSharedTraits@VNonReentrantRWLock@cxl@@@2@@cxl@@QEBAXXZ; cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireSharedTraits<cxl::NonReentrantRWLock>>::Release(void)
0x1800188da  nop
0x1800188db  jmp     loc_180018ADD
0x1800188e0  lea     rsi, [rdi+70h]
0x1800188e4  mov     rdx, rsi
0x1800188e7  lea     rcx, [rbp+57h+var_D0]
0x1800188eb  call    ??4?$shared_ptr@VCacheObject@DataStore@ClusWmi@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<ClusWmi::DataStore::CacheObject>::operator=(std::shared_ptr<ClusWmi::DataStore::CacheObject> const &)
0x1800188f0  nop
0x1800188f1  lea     rcx, [rbp+57h+var_90]
0x1800188f5  call    ?Release@?$ScopedResOwner@VNonReentrantRWLock@cxl@@V?$AcquireSharedTraits@VNonReentrantRWLock@cxl@@@2@@cxl@@QEBAXXZ; cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireSharedTraits<cxl::NonReentrantRWLock>>::Release(void)
0x1800188fa  mov     rbx, [rbp+57h+var_D0]
0x1800188fe  test    rbx, rbx
0x180018901  jnz     loc_1800189A4
0x180018907  xorps   xmm0, xmm0
0x18001890a  movdqu  xmmword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], xmm0
0x18001890f  mov     rcx, [rdi]
0x180018912  mov     rax, [rcx]
0x180018915  lea     rdx, [rbp+57h+SystemTimeAsFileTime]
0x180018919  mov     rax, [rax+30h]
0x18001891d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018922  mov     edi, eax
0x180018924  test    eax, eax
0x180018926  js      short loc_180018950
0x180018928  mov     rcx, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x18001892c  mov     rax, [rcx]
0x18001892f  xor     edx, edx
0x180018931  mov     rax, [rax]
0x180018934  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018939  mov     edi, eax
0x18001893b  test    eax, eax
0x18001893d  js      short loc_180018950
0x18001893f  lea     rdx, [rbp+57h+SystemTimeAsFileTime]
0x180018943  lea     rcx, [rbp+57h+var_D0]
0x180018947  call    ??4?$shared_ptr@VCacheObject@DataStore@ClusWmi@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<ClusWmi::DataStore::CacheObject>::operator=(std::shared_ptr<ClusWmi::DataStore::CacheObject> const &)
0x18001894c  mov     rbx, [rbp+57h+var_D0]
0x180018950  mov     rcx, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime+8]; this
0x180018954  test    rcx, rcx
0x180018957  jz      short loc_18001895E
0x180018959  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001895e  test    edi, edi
0x180018960  jns     short loc_1800189A4
0x180018962  mov     rcx, [rbp+57h+var_D0+8]; this
0x180018966  test    rcx, rcx
0x180018969  jz      short loc_180018970
0x18001896b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180018970  xor     ebx, ebx
0x180018972  lea     rcx, [rbp+57h+var_C0]; this
0x180018976  call    ?Clear@Token@cxl@@QEAAXXZ; cxl::Token::Clear(void)
0x18001897b  mov     al, bl
0x18001897d  mov     rcx, [rbp+57h+var_40]
0x180018981  xor     rcx, rsp; StackCookie
0x180018984  call    __security_check_cookie
0x180018989  mov     rbx, [rsp+100h+arg_18]
0x180018991  add     rsp, 0D0h
0x180018998  pop     r15
0x18001899a  pop     r14
0x18001899c  pop     r13
0x18001899e  pop     r12
0x1800189a0  pop     rdi
0x1800189a1  pop     rsi
0x1800189a2  pop     rbp
0x1800189a3  retn
0x1800189a4  mov     [rsp+100h+var_E0], 0
0x1800189ac  mov     rax, [rbx]
0x1800189af  lea     r8, [rsp+100h+var_E0]
0x1800189b4  mov     rdx, [rbp+57h+var_B8]
0x1800189b8  mov     rcx, rbx
0x1800189bb  mov     rax, [rax+40h]
0x1800189bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800189c4  test    eax, eax
0x1800189c6  js      short loc_180018962
0x1800189c8  lea     rdx, [rbp+57h+var_90]
0x1800189cc  mov     rcx, r12
0x1800189cf  call    ?ToString@SidBase@cxl@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; cxl::SidBase::ToString(void)
0x1800189d4  mov     rdx, rax
0x1800189d7  mov     rcx, r15
0x1800189da  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800189df  lea     rcx, [rbp+57h+var_90]
0x1800189e3  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800189e8  mov     edx, [rsp+100h+var_E0]
0x1800189ec  lea     rcx, [rbp+57h+SystemTimeAsFileTime]
0x1800189f0  call    ??$_Integral_to_string@_WK@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@K@Z; std::_Integral_to_string<wchar_t,ulong>(ulong)
0x1800189f5  nop
0x1800189f6  lea     rdx, aAccess; "Access"
0x1800189fd  lea     rcx, [rbp+57h+var_70]
0x180018a01  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180018a06  nop
0x180018a07  lea     r9, [rbp+57h+SystemTimeAsFileTime]
0x180018a0b  mov     r8, rax
0x180018a0e  lea     rcx, [rbp+57h+var_90]
0x180018a12  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring &,std::wstring &)
0x180018a17  nop
0x180018a18  lea     rdx, [rbp+57h+var_90]
0x180018a1c  mov     rcx, r15
0x180018a1f  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x180018a24  nop
0x180018a25  lea     rcx, [rbp+57h+var_90]
0x180018a29  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180018a2e  nop
0x180018a2f  lea     rcx, [rbp+57h+var_70]
0x180018a33  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180018a38  nop
0x180018a39  lea     rcx, [rbp+57h+SystemTimeAsFileTime]
0x180018a3d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180018a42  mov     rdx, r13; struct cxl::NonReentrantRWLock *
0x180018a45  lea     rcx, [rbp+57h+var_90]; this
0x180018a49  call    ??0AcquireWriteLock@cxl@@QEAA@AEAVNonReentrantRWLock@1@@Z; cxl::AcquireWriteLock::AcquireWriteLock(cxl::NonReentrantRWLock &)
0x180018a4e  nop
0x180018a4f  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180018a57  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180018a5b  call    cs:__imp_GetSystemTimeAsFileTime
0x180018a61  mov     rdx, r15
0x180018a64  lea     rcx, [rbp+57h+var_70]
0x180018a68  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180018a6d  lea     rax, ??_7DateTime@cxl@@6B@; const cxl::DateTime::`vftable'
0x180018a74  mov     [rbp+57h+var_50], rax
0x180018a78  mov     rax, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x180018a7c  mov     [rbp+57h+var_48], rax
0x180018a80  lea     r8, [rsp+100h+var_D8]
0x180018a85  lea     rdx, [rbp+57h+SystemTimeAsFileTime]
0x180018a89  mov     rcx, r14
0x180018a8c  call    ??$_Try_emplace@AEBU_LUID@@$$V@?$map@U_LUID@@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDateTime@cxl@@@std@@ULUIDComparer@DataStore@ClusWmi@@V?$allocator@U?$pair@$$CBU_LUID@@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDateTime@cxl@@@std@@@std@@@3@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBU_LUID@@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDateTime@cxl@@@std@@@std@@PEAX@std@@_N@1@AEBU_LUID@@@Z; std::map<_LUID,std::pair<std::wstring,cxl::DateTime>,ClusWmi::DataStore::LUIDComparer,std::allocator<std::pair<_LUID const,std::pair<std::wstring,cxl::DateTime>>>>::_Try_emplace<_LUID const &,>(_LUID const &)
0x180018a91  mov     rbx, [rax]
0x180018a94  lea     rdx, [rbp+57h+var_70]
0x180018a98  lea     rcx, [rbx+28h]
0x180018a9c  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180018aa1  mov     rax, [rbp+57h+var_48]
0x180018aa5  mov     [rbx+50h], rax
0x180018aa9  lea     rcx, [rbp+57h+var_70]
0x180018aad  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180018ab2  cmp     qword ptr [rsi], 0
0x180018ab6  jnz     short loc_180018AC5
0x180018ab8  lea     rdx, [rbp+57h+var_D0]
0x180018abc  mov     rcx, rsi
0x180018abf  call    ??4?$shared_ptr@VCacheObject@DataStore@ClusWmi@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<ClusWmi::DataStore::CacheObject>::operator=(std::shared_ptr<ClusWmi::DataStore::CacheObject> const &)
0x180018ac4  nop
0x180018ac5  lea     rcx, [rbp+57h+var_90]
0x180018ac9  call    ?Release@?$ScopedResOwner@VNonReentrantRWLock@cxl@@V?$AcquireExclusiveTraits@VNonReentrantRWLock@cxl@@@2@@cxl@@QEBAXXZ; cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireExclusiveTraits<cxl::NonReentrantRWLock>>::Release(void)
0x180018ace  nop
0x180018acf  mov     rcx, [rbp+57h+var_D0+8]; this
0x180018ad3  test    rcx, rcx
0x180018ad6  jz      short loc_180018ADD
0x180018ad8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180018add  mov     bl, 1
0x180018adf  jmp     loc_180018972
```
