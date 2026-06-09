# ClusWmi::DataStore::GetCacheKey(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,cxl::Sid &)

- ea: `0x18001c3a0`
- end: `0x18001c685`
- name: `?GetCacheKey@DataStore@ClusWmi@@AEAA_NAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVSid@cxl@@@Z`
- size: `741`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001c8f0`

## callees

- `0x180002ad0`
- `0x180005fdc`
- `0x18000aa10`
- `0x18000c5c4`
- `0x18000d5b8`
- `0x18000db2c`
- `0x180014388`
- `0x180015be4`
- `0x1800194ac`
- `0x180019d88`
- `0x18001aa98`
- `0x18001abe8`
- `0x18001ac6c`
- `0x18001ad20`
- `0x18001b148`
- `0x18001b198`
- `0x18001bcbc`
- `0x18001c3a0`
- `0x18001cabc`
- `0x18001e0d0`
- `0x18001e134`
- `0x18001f588`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001c457`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001c5f5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001c457`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001c5f5`

## string_xrefs

- `0x18001c591`: `Access`

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
  __int64 v17; // rax
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
      std::wstring::operator=(a2, &v8[5]);
      SystemTimeAsFileTime[0] = 0;
      GetSystemTimeAsFileTime(SystemTimeAsFileTime);
      v8[10] = SystemTimeAsFileTime[0];
      cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireSharedTraits<cxl::NonReentrantRWLock>>::Release(v26);
LABEL_21:
      v13 = 1;
      goto LABEL_15;
    }
    v10 = (_QWORD *)((char *)a1 + 112);
    std::shared_ptr<ClusWmi::DataStore::CacheObject>::operator=(v21);
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
        std::shared_ptr<ClusWmi::DataStore::CacheObject>::operator=(v21);
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
        std::_Integral_to_string<wchar_t,unsigned long>(v26, v19);
        v16 = std::wstring::wstring(v27, L"Access");
        v17 = std::operator+<wchar_t>(SystemTimeAsFileTime, v16, v26);
        std::wstring::append(a2, v17);
        std::wstring::_Tidy_deallocate(SystemTimeAsFileTime);
        std::wstring::_Tidy_deallocate(v27);
        std::wstring::_Tidy_deallocate(v26);
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
          std::shared_ptr<ClusWmi::DataStore::CacheObject>::operator=(v10);
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
0x18001c3a0  mov     [rsp-8+arg_18], rbx
0x18001c3a5  push    rbp
0x18001c3a6  push    rsi
0x18001c3a7  push    rdi
0x18001c3a8  push    r12
0x18001c3aa  push    r13
0x18001c3ac  push    r14
0x18001c3ae  push    r15
0x18001c3b0  lea     rbp, [rsp-27h]
0x18001c3b5  sub     rsp, 0D0h
0x18001c3bc  mov     rax, cs:__security_cookie
0x18001c3c3  xor     rax, rsp
0x18001c3c6  mov     [rbp+57h+var_40], rax
0x18001c3ca  mov     r12, r8
0x18001c3cd  mov     r15, rdx
0x18001c3d0  mov     rdi, rcx
0x18001c3d3  xor     eax, eax
0x18001c3d5  mov     [rbp+57h+var_B8], rax
0x18001c3d9  mov     qword ptr [rsp+100h+var_D8.LowPart], rax
0x18001c3de  mov     r9, r8; struct cxl::Sid *
0x18001c3e1  lea     r8, [rsp+100h+var_D8]; struct _LUID *
0x18001c3e6  lea     rdx, [rbp+57h+var_C0]; struct cxl::Token *
0x18001c3ea  call    ?GetCurrentTokenModifiedIDAndSid@DataStore@ClusWmi@@AEAA_NAEAVToken@cxl@@PEAU_LUID@@PEAVSid@4@@Z; ClusWmi::DataStore::GetCurrentTokenModifiedIDAndSid(cxl::Token &,_LUID *,cxl::Sid *)
0x18001c3ef  test    al, al
0x18001c3f1  jz      loc_18001C50A
0x18001c3f7  xorps   xmm0, xmm0
0x18001c3fa  movdqu  xmmword ptr [rbp+57h+var_D0], xmm0
0x18001c3ff  lea     r13, [rdi+40h]
0x18001c403  mov     rdx, r13; struct cxl::NonReentrantRWLock *
0x18001c406  lea     rcx, [rbp+57h+var_90]; this
0x18001c40a  call    ??0AcquireReadLock@cxl@@QEAA@AEAVNonReentrantRWLock@1@@Z; cxl::AcquireReadLock::AcquireReadLock(cxl::NonReentrantRWLock &)
0x18001c40f  nop
0x18001c410  lea     r14, [rdi+50h]
0x18001c414  lea     r8, [rsp+100h+var_D8]
0x18001c419  lea     rdx, [rbp+57h+SystemTimeAsFileTime]
0x18001c41d  mov     rcx, r14
0x18001c420  call    ??$_Find_lower_bound@U_LUID@@@?$_Tree@V?$_Tmap_traits@U_LUID@@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDateTime@cxl@@@std@@ULUIDComparer@DataStore@ClusWmi@@V?$allocator@U?$pair@$$CBU_LUID@@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDateTime@cxl@@@std@@@std@@@3@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBU_LUID@@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDateTime@cxl@@@std@@@std@@PEAX@std@@@1@AEBU_LUID@@@Z; std::_Tree<std::_Tmap_traits<_LUID,std::pair<std::wstring,cxl::DateTime>,ClusWmi::DataStore::LUIDComparer,std::allocator<std::pair<_LUID const,std::pair<std::wstring,cxl::DateTime>>>,0>>::_Find_lower_bound<_LUID>(_LUID const &)
0x18001c425  lea     r8, [rsp+100h+var_D8]
0x18001c42a  mov     rbx, [rbp+57h+var_A0]
0x18001c42e  mov     rdx, rbx
0x18001c431  call    ??$_Lower_bound_duplicate@U_LUID@@@?$_Tree@V?$_Tmap_traits@U_LUID@@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDateTime@cxl@@@std@@ULUIDComparer@DataStore@ClusWmi@@V?$allocator@U?$pair@$$CBU_LUID@@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDateTime@cxl@@@std@@@std@@@3@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBU_LUID@@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDateTime@cxl@@@std@@@std@@PEAX@1@AEBU_LUID@@@Z; std::_Tree<std::_Tmap_traits<_LUID,std::pair<std::wstring,cxl::DateTime>,ClusWmi::DataStore::LUIDComparer,std::allocator<std::pair<_LUID const,std::pair<std::wstring,cxl::DateTime>>>,0>>::_Lower_bound_duplicate<_LUID>(std::_Tree_node<std::pair<_LUID const,std::pair<std::wstring,cxl::DateTime>>,void *> * const,_LUID const &)
0x18001c436  test    al, al
0x18001c438  jz      short loc_18001C47A
0x18001c43a  cmp     rbx, [r14]
0x18001c43d  jz      short loc_18001C47A
0x18001c43f  lea     rdx, [rbx+28h]
0x18001c443  mov     rcx, r15
0x18001c446  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18001c44b  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18001c453  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001c457  call    cs:__imp_GetSystemTimeAsFileTime
0x18001c45e  nop     dword ptr [rax+rax+00h]
0x18001c463  mov     rax, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x18001c467  mov     [rbx+50h], rax
0x18001c46b  lea     rcx, [rbp+57h+var_90]
0x18001c46f  call    ?Release@?$ScopedResOwner@VNonReentrantRWLock@cxl@@V?$AcquireSharedTraits@VNonReentrantRWLock@cxl@@@2@@cxl@@QEBAXXZ; cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireSharedTraits<cxl::NonReentrantRWLock>>::Release(void)
0x18001c474  nop
0x18001c475  jmp     loc_18001C67D
0x18001c47a  lea     rsi, [rdi+70h]
0x18001c47e  mov     rdx, rsi
0x18001c481  lea     rcx, [rbp+57h+var_D0]
0x18001c485  call    ??4?$shared_ptr@VCacheObject@DataStore@ClusWmi@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<ClusWmi::DataStore::CacheObject>::operator=(std::shared_ptr<ClusWmi::DataStore::CacheObject> const &)
0x18001c48a  nop
0x18001c48b  lea     rcx, [rbp+57h+var_90]
0x18001c48f  call    ?Release@?$ScopedResOwner@VNonReentrantRWLock@cxl@@V?$AcquireSharedTraits@VNonReentrantRWLock@cxl@@@2@@cxl@@QEBAXXZ; cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireSharedTraits<cxl::NonReentrantRWLock>>::Release(void)
0x18001c494  mov     rbx, [rbp+57h+var_D0]
0x18001c498  test    rbx, rbx
0x18001c49b  jnz     loc_18001C53F
0x18001c4a1  xorps   xmm0, xmm0
0x18001c4a4  movdqu  xmmword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], xmm0
0x18001c4a9  mov     rcx, [rdi]
0x18001c4ac  mov     rax, [rcx]
0x18001c4af  lea     rdx, [rbp+57h+SystemTimeAsFileTime]
0x18001c4b3  mov     rax, [rax+30h]
0x18001c4b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c4bc  mov     edi, eax
0x18001c4be  test    eax, eax
0x18001c4c0  js      short loc_18001C4EA
0x18001c4c2  mov     rcx, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x18001c4c6  mov     rax, [rcx]
0x18001c4c9  xor     edx, edx
0x18001c4cb  mov     rax, [rax]
0x18001c4ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c4d3  mov     edi, eax
0x18001c4d5  test    eax, eax
0x18001c4d7  js      short loc_18001C4EA
0x18001c4d9  lea     rdx, [rbp+57h+SystemTimeAsFileTime]
0x18001c4dd  lea     rcx, [rbp+57h+var_D0]
0x18001c4e1  call    ??4?$shared_ptr@VCacheObject@DataStore@ClusWmi@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<ClusWmi::DataStore::CacheObject>::operator=(std::shared_ptr<ClusWmi::DataStore::CacheObject> const &)
0x18001c4e6  mov     rbx, [rbp+57h+var_D0]
0x18001c4ea  mov     rcx, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime+8]; this
0x18001c4ee  test    rcx, rcx
0x18001c4f1  jz      short loc_18001C4F8
0x18001c4f3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001c4f8  test    edi, edi
0x18001c4fa  jns     short loc_18001C53F
0x18001c4fc  mov     rcx, [rbp+57h+var_D0+8]; this
0x18001c500  test    rcx, rcx
0x18001c503  jz      short loc_18001C50A
0x18001c505  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001c50a  xor     ebx, ebx
0x18001c50c  lea     rcx, [rbp+57h+var_C0]; this
0x18001c510  call    ?Clear@Token@cxl@@QEAAXXZ; cxl::Token::Clear(void)
0x18001c515  mov     al, bl
0x18001c517  mov     rcx, [rbp+57h+var_40]
0x18001c51b  xor     rcx, rsp; StackCookie
0x18001c51e  call    __security_check_cookie
0x18001c523  mov     rbx, [rsp+100h+arg_18]
0x18001c52b  add     rsp, 0D0h
0x18001c532  pop     r15
0x18001c534  pop     r14
0x18001c536  pop     r13
0x18001c538  pop     r12
0x18001c53a  pop     rdi
0x18001c53b  pop     rsi
0x18001c53c  pop     rbp
0x18001c53d  retn
0x18001c53f  mov     [rsp+100h+var_E0], 0
0x18001c547  mov     rax, [rbx]
0x18001c54a  lea     r8, [rsp+100h+var_E0]
0x18001c54f  mov     rdx, [rbp+57h+var_B8]
0x18001c553  mov     rcx, rbx
0x18001c556  mov     rax, [rax+40h]
0x18001c55a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c55f  test    eax, eax
0x18001c561  js      short loc_18001C4FC
0x18001c563  lea     rdx, [rbp+57h+var_90]
0x18001c567  mov     rcx, r12
0x18001c56a  call    ?ToString@SidBase@cxl@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; cxl::SidBase::ToString(void)
0x18001c56f  mov     rdx, rax
0x18001c572  mov     rcx, r15
0x18001c575  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001c57a  lea     rcx, [rbp+57h+var_90]
0x18001c57e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001c583  mov     edx, [rsp+100h+var_E0]
0x18001c587  lea     rcx, [rbp+57h+var_90]
0x18001c58b  call    ??$_Integral_to_string@_WK@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@K@Z; std::_Integral_to_string<wchar_t,ulong>(ulong)
0x18001c590  nop
0x18001c591  lea     rdx, aAccess; "Access"
0x18001c598  lea     rcx, [rbp+57h+var_70]
0x18001c59c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001c5a1  nop
0x18001c5a2  lea     r8, [rbp+57h+var_90]
0x18001c5a6  mov     rdx, rax
0x18001c5a9  lea     rcx, [rbp+57h+SystemTimeAsFileTime]
0x18001c5ad  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@0@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring &&)
0x18001c5b2  nop
0x18001c5b3  mov     rdx, rax
0x18001c5b6  mov     rcx, r15
0x18001c5b9  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18001c5be  nop
0x18001c5bf  lea     rcx, [rbp+57h+SystemTimeAsFileTime]
0x18001c5c3  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001c5c8  nop
0x18001c5c9  lea     rcx, [rbp+57h+var_70]
0x18001c5cd  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001c5d2  nop
0x18001c5d3  lea     rcx, [rbp+57h+var_90]
0x18001c5d7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001c5dc  mov     rdx, r13; struct cxl::NonReentrantRWLock *
0x18001c5df  lea     rcx, [rbp+57h+var_90]; this
0x18001c5e3  call    ??0AcquireWriteLock@cxl@@QEAA@AEAVNonReentrantRWLock@1@@Z; cxl::AcquireWriteLock::AcquireWriteLock(cxl::NonReentrantRWLock &)
0x18001c5e8  nop
0x18001c5e9  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18001c5f1  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001c5f5  call    cs:__imp_GetSystemTimeAsFileTime
0x18001c5fc  nop     dword ptr [rax+rax+00h]
0x18001c601  mov     rdx, r15
0x18001c604  lea     rcx, [rbp+57h+var_70]
0x18001c608  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001c60d  lea     rax, ??_7DateTime@cxl@@6B@; const cxl::DateTime::`vftable'
0x18001c614  mov     [rbp+57h+var_50], rax
0x18001c618  mov     rax, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x18001c61c  mov     [rbp+57h+var_48], rax
0x18001c620  lea     r8, [rsp+100h+var_D8]
0x18001c625  lea     rdx, [rbp+57h+SystemTimeAsFileTime]
0x18001c629  mov     rcx, r14
0x18001c62c  call    ??$_Try_emplace@AEBU_LUID@@$$V@?$map@U_LUID@@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDateTime@cxl@@@std@@ULUIDComparer@DataStore@ClusWmi@@V?$allocator@U?$pair@$$CBU_LUID@@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDateTime@cxl@@@std@@@std@@@3@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBU_LUID@@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDateTime@cxl@@@std@@@std@@PEAX@std@@_N@1@AEBU_LUID@@@Z; std::map<_LUID,std::pair<std::wstring,cxl::DateTime>,ClusWmi::DataStore::LUIDComparer,std::allocator<std::pair<_LUID const,std::pair<std::wstring,cxl::DateTime>>>>::_Try_emplace<_LUID const &,>(_LUID const &)
0x18001c631  mov     rbx, [rax]
0x18001c634  lea     rdx, [rbp+57h+var_70]
0x18001c638  lea     rcx, [rbx+28h]
0x18001c63c  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001c641  mov     rax, [rbp+57h+var_48]
0x18001c645  mov     [rbx+50h], rax
0x18001c649  lea     rcx, [rbp+57h+var_70]
0x18001c64d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001c652  cmp     qword ptr [rsi], 0
0x18001c656  jnz     short loc_18001C665
0x18001c658  lea     rdx, [rbp+57h+var_D0]
0x18001c65c  mov     rcx, rsi
0x18001c65f  call    ??4?$shared_ptr@VCacheObject@DataStore@ClusWmi@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<ClusWmi::DataStore::CacheObject>::operator=(std::shared_ptr<ClusWmi::DataStore::CacheObject> const &)
0x18001c664  nop
0x18001c665  lea     rcx, [rbp+57h+var_90]
0x18001c669  call    ?Release@?$ScopedResOwner@VNonReentrantRWLock@cxl@@V?$AcquireExclusiveTraits@VNonReentrantRWLock@cxl@@@2@@cxl@@QEBAXXZ; cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireExclusiveTraits<cxl::NonReentrantRWLock>>::Release(void)
0x18001c66e  nop
0x18001c66f  mov     rcx, [rbp+57h+var_D0+8]; this
0x18001c673  test    rcx, rcx
0x18001c676  jz      short loc_18001C67D
0x18001c678  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001c67d  mov     bl, 1
0x18001c67f  jmp     loc_18001C50C
```
