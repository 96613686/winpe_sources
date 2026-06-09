# ArchiveStructure::UpdateToLatest(std::shared_ptr<ArchiveStructure> &,wil::basic_zstring_view<ushort>,bool)

- ea: `0x180030350`
- end: `0x180030612`
- name: `?UpdateToLatest@ArchiveStructure@@SAJAEAV?$shared_ptr@VArchiveStructure@@@std@@V?$basic_zstring_view@G@wil@@_N@Z`
- size: `706`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180030618`

## callees

- `0x18000ac9c`
- `0x180020934`
- `0x180020cbc`
- `0x180020cdc`
- `0x18002abd0`
- `0x180030350`
- `0x18003397c`
- `0x180034584`
- `0x180034a8c`
- `0x180036f50`
- `0x180054abc`
- `0x180054fc8`
- `0x1800552f4`
- `0x180071010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003042d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003042d`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800303be`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800304ad`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800303be`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800304ad`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
LONG __fastcall ArchiveStructure::UpdateToLatest(FILETIME **a1, _OWORD *a2)
{
  LONG result; // eax
  volatile signed __int32 *v5; // rbx
  __int64 v6; // r8
  FILETIME **v7; // rbx
  __int64 v8; // r15
  _QWORD *v9; // rsi
  __int64 v10; // rax
  __int64 v11; // rdx
  char v12; // r12
  DWORD dwLowDateTime; // ebx
  __int64 v14; // rcx
  int v15; // esi
  volatile signed __int32 *v16; // rbx
  FILETIME FileTime1; // [rsp+30h] [rbp-68h] BYREF
  FILETIME FileTime2; // [rsp+38h] [rbp-60h] BYREF
  __int64 v19; // [rsp+40h] [rbp-58h] BYREF
  volatile signed __int32 *v20; // [rsp+48h] [rbp-50h]
  FILETIME v21[2]; // [rsp+50h] [rbp-48h] BYREF
  __int128 v22; // [rsp+60h] [rbp-38h]

  FileTime1 = 0;
  *(_OWORD *)&v21[0].dwLowDateTime = *a2;
  result = GetLastWriteTime(v21, &FileTime1);
  if ( result < 0 )
    return result;
  if ( *a1 )
  {
    FileTime2 = (*a1)[4];
    result = CompareFileTime(&FileTime1, &FileTime2);
    if ( !result )
      return result;
    *(_OWORD *)&v21[0].dwLowDateTime = 0;
    std::shared_ptr<ArchiveStructure>::operator=(a1, v21);
    v5 = (volatile signed __int32 *)v21[1];
    if ( v21[1] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v21[1] + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v5)(v5);
        if ( _InterlockedExchangeAdd(v5 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 8LL))(v5);
      }
    }
  }
  AcquireSRWLockExclusive(&ArchiveStructure::s_archiveCacheLock);
  FileTime2 = (FILETIME)&ArchiveStructure::s_archiveCacheLock;
  std::lower_bound_std::_Vector_iterator_std::_Vector_val_std::_Simple_types_std::shared_ptr_ArchiveStructure________wil::basic_zstring_view_unsigned_short___lambda_0f91309c80b9ee4e48dd8285b1aef8a1___(
    v21,
    ArchiveStructure::s_archiveCache,
    *((_QWORD *)&ArchiveStructure::s_archiveCache + 1),
    a2);
  v7 = (FILETIME **)v21[0];
  if ( *(_QWORD *)v21 == *((_QWORD *)&ArchiveStructure::s_archiveCache + 1) )
  {
    v8 = *(_QWORD *)a2;
    v9 = (_QWORD *)a2 + 1;
LABEL_11:
    v12 = 0;
LABEL_17:
    *(_OWORD *)&v21[0].dwLowDateTime = 0;
    v22 = 0;
    std::wstring::_Construct<1,unsigned short const *>(v21, v8, *v9);
    std::make_shared<ArchiveStructure,std::wstring,_FILETIME &>(&v19, v21, &FileTime1);
    std::wstring::_Tidy_deallocate(v21);
    if ( *(int *)(v19 + 40) >= 0 )
      std::shared_ptr<ArchiveStructure>::operator=(a1, &v19);
    v14 = *(unsigned int *)(v19 + 40);
    if ( (int)(v14 + 0x80000000) < 0 || (_DWORD)v14 == -2147018894 || (v14 &= 0x1FFF0000u, (_DWORD)v14 == 9830400) )
    {
      if ( v12 )
        std::shared_ptr<ArchiveStructure>::operator=(v7, &v19);
      else
        std::vector<std::shared_ptr<ArchiveStructure>>::emplace<std::shared_ptr<ArchiveStructure> const &>(
          v14,
          v21,
          v7,
          &v19);
    }
    v15 = *(_DWORD *)(v19 + 40);
    v16 = v20;
    if ( v20 && _InterlockedExchangeAdd(v20 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
      if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&FileTime2);
    return v15;
  }
  v10 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(**(_QWORD **)v21, **(_QWORD **)v21, v6);
  v8 = *(_QWORD *)a2;
  v9 = (_QWORD *)a2 + 1;
  if ( !(unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v10, *(_QWORD *)(v11 + 16), v8, *v9) )
    goto LABEL_11;
  v21[0] = (*v7)[4];
  if ( CompareFileTime(&FileTime1, v21) )
  {
    v12 = 1;
    goto LABEL_17;
  }
  if ( ((*v7)[5].dwLowDateTime & 0x80000000) == 0 )
    std::shared_ptr<ArchiveStructure>::operator=(a1, v7);
  dwLowDateTime = (*v7)[5].dwLowDateTime;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&FileTime2);
  return dwLowDateTime;
}

```

## disassembly

```asm
0x180030350  mov     r11, rsp
0x180030353  mov     [r11+18h], rbx
0x180030357  mov     [r11+20h], rsi
0x18003035b  push    r12
0x18003035d  push    r14
0x18003035f  push    r15
0x180030361  sub     rsp, 80h
0x180030368  mov     rax, cs:__security_cookie
0x18003036f  xor     rax, rsp
0x180030372  mov     [rsp+98h+var_28], rax
0x180030377  mov     rsi, rdx
0x18003037a  mov     r14, rcx
0x18003037d  mov     qword ptr [r11-68h], 0
0x180030385  movaps  xmm0, xmmword ptr [rdx]
0x180030388  movdqa  xmmword ptr [rsp+98h+var_48.dwLowDateTime], xmm0
0x18003038e  lea     rdx, [r11-68h]
0x180030392  lea     rcx, [r11-48h]
0x180030396  call    GetLastWriteTime
0x18003039b  test    eax, eax
0x18003039d  js      loc_1800305EA
0x1800303a3  mov     rax, [r14]
0x1800303a6  test    rax, rax
0x1800303a9  jz      short loc_180030423
0x1800303ab  mov     rax, [rax+20h]
0x1800303af  mov     qword ptr [rsp+98h+FileTime2.dwLowDateTime], rax
0x1800303b4  lea     rdx, [rsp+98h+FileTime2]; lpFileTime2
0x1800303b9  lea     rcx, [rsp+98h+FileTime1]; lpFileTime1
0x1800303be  call    cs:__imp_CompareFileTime
0x1800303c4  test    eax, eax
0x1800303c6  jz      loc_1800305EA
0x1800303cc  xorps   xmm0, xmm0
0x1800303cf  movdqu  xmmword ptr [rsp+98h+var_48.dwLowDateTime], xmm0
0x1800303d5  lea     rdx, [rsp+98h+var_48]
0x1800303da  mov     rcx, r14
0x1800303dd  call    ??4?$shared_ptr@VArchiveStructure@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<ArchiveStructure>::operator=(std::shared_ptr<ArchiveStructure> &&)
0x1800303e2  mov     rbx, qword ptr [rsp+98h+var_48.dwLowDateTime+8]
0x1800303e7  test    rbx, rbx
0x1800303ea  jz      short loc_180030423
0x1800303ec  or      eax, 0FFFFFFFFh
0x1800303ef  lock xadd [rbx+8], eax
0x1800303f4  cmp     eax, 1
0x1800303f7  jnz     short loc_180030423
0x1800303f9  mov     rax, [rbx]
0x1800303fc  mov     rcx, rbx
0x1800303ff  mov     rax, [rax]
0x180030402  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030407  or      eax, 0FFFFFFFFh
0x18003040a  lock xadd [rbx+0Ch], eax
0x18003040f  cmp     eax, 1
0x180030412  jnz     short loc_180030423
0x180030414  mov     rax, [rbx]
0x180030417  mov     rcx, rbx
0x18003041a  mov     rax, [rax+8]
0x18003041e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030423  lea     rbx, ?s_archiveCacheLock@ArchiveStructure@@0Vsrwlock@wil@@A; wil::srwlock ArchiveStructure::s_archiveCacheLock
0x18003042a  mov     rcx, rbx; SRWLock
0x18003042d  call    cs:__imp_AcquireSRWLockExclusive
0x180030433  mov     qword ptr [rsp+98h+FileTime2.dwLowDateTime], rbx
0x180030438  mov     r9, rsi
0x18003043b  mov     r8, qword ptr cs:?s_archiveCache@ArchiveStructure@@0V?$vector@V?$shared_ptr@VArchiveStructure@@@std@@V?$allocator@V?$shared_ptr@VArchiveStructure@@@std@@@2@@std@@A+8; std::vector<std::shared_ptr<ArchiveStructure>> ArchiveStructure::s_archiveCache
0x180030442  mov     rdx, qword ptr cs:?s_archiveCache@ArchiveStructure@@0V?$vector@V?$shared_ptr@VArchiveStructure@@@std@@V?$allocator@V?$shared_ptr@VArchiveStructure@@@std@@@2@@std@@A; std::vector<std::shared_ptr<ArchiveStructure>> ArchiveStructure::s_archiveCache
0x180030449  lea     rcx, [rsp+98h+var_48]
0x18003044e  call    std__lower_bound_std___Vector_iterator_std___Vector_val_std___Simple_types_std__shared_ptr_ArchiveStructure________wil__basic_zstring_view_unsigned_short___lambda_0f91309c80b9ee4e48dd8285b1aef8a1___
0x180030453  mov     rbx, qword ptr [rsp+98h+var_48.dwLowDateTime]
0x180030458  cmp     rbx, qword ptr cs:?s_archiveCache@ArchiveStructure@@0V?$vector@V?$shared_ptr@VArchiveStructure@@@std@@V?$allocator@V?$shared_ptr@VArchiveStructure@@@std@@@2@@std@@A+8; std::vector<std::shared_ptr<ArchiveStructure>> ArchiveStructure::s_archiveCache
0x18003045f  jnz     short loc_18003046A
0x180030461  mov     r15, [rsi]
0x180030464  add     rsi, 8
0x180030468  jmp     short loc_180030492
0x18003046a  mov     rdx, [rbx]
0x18003046d  mov     rcx, rdx
0x180030470  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180030475  mov     r15, [rsi]
0x180030478  add     rsi, 8
0x18003047c  mov     r9, [rsi]
0x18003047f  mov     r8, r15
0x180030482  mov     rdx, [rdx+10h]
0x180030486  mov     rcx, rax
0x180030489  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18003048e  test    al, al
0x180030490  jnz     short loc_180030497
0x180030492  xor     r12b, r12b
0x180030495  jmp     short loc_1800304E5
0x180030497  mov     rax, [rbx]
0x18003049a  mov     rcx, [rax+20h]
0x18003049e  mov     qword ptr [rsp+98h+var_48.dwLowDateTime], rcx
0x1800304a3  lea     rdx, [rsp+98h+var_48]; lpFileTime2
0x1800304a8  lea     rcx, [rsp+98h+FileTime1]; lpFileTime1
0x1800304ad  call    cs:__imp_CompareFileTime
0x1800304b3  test    eax, eax
0x1800304b5  jnz     short loc_1800304E2
0x1800304b7  mov     rax, [rbx]
0x1800304ba  cmp     dword ptr [rax+28h], 0
0x1800304be  jl      short loc_1800304CB
0x1800304c0  mov     rdx, rbx
0x1800304c3  mov     rcx, r14
0x1800304c6  call    ??4?$shared_ptr@VArchiveStructure@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<ArchiveStructure>::operator=(std::shared_ptr<ArchiveStructure> const &)
0x1800304cb  mov     rax, [rbx]
0x1800304ce  mov     ebx, [rax+28h]
0x1800304d1  lea     rcx, [rsp+98h+FileTime2]
0x1800304d6  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800304db  mov     eax, ebx
0x1800304dd  jmp     loc_1800305EA
0x1800304e2  mov     r12b, 1
0x1800304e5  xorps   xmm0, xmm0
0x1800304e8  movups  xmmword ptr [rsp+98h+var_48.dwLowDateTime], xmm0
0x1800304ed  xorps   xmm1, xmm1
0x1800304f0  movdqu  [rsp+98h+var_38], xmm1
0x1800304f6  mov     r8, [rsi]
0x1800304f9  mov     rdx, r15
0x1800304fc  lea     rcx, [rsp+98h+var_48]
0x180030501  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180030506  nop
0x180030507  lea     r8, [rsp+98h+FileTime1]
0x18003050c  lea     rdx, [rsp+98h+var_48]
0x180030511  lea     rcx, [rsp+98h+var_58]
0x180030516  call    ??$make_shared@VArchiveStructure@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAU_FILETIME@@@std@@YA?AV?$shared_ptr@VArchiveStructure@@@0@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEAU_FILETIME@@@Z; std::make_shared<ArchiveStructure,std::wstring,_FILETIME &>(std::wstring &&,_FILETIME &)
0x18003051b  nop
0x18003051c  lea     rcx, [rsp+98h+var_48]
0x180030521  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180030526  mov     rax, [rsp+98h+var_58]
0x18003052b  cmp     dword ptr [rax+28h], 0
0x18003052f  jl      short loc_18003053E
0x180030531  lea     rdx, [rsp+98h+var_58]
0x180030536  mov     rcx, r14
0x180030539  call    ??4?$shared_ptr@VArchiveStructure@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<ArchiveStructure>::operator=(std::shared_ptr<ArchiveStructure> const &)
0x18003053e  mov     rax, [rsp+98h+var_58]
0x180030543  mov     ecx, [rax+28h]
0x180030546  mov     edx, 80000000h
0x18003054b  lea     eax, [rcx+rdx]
0x18003054e  test    edx, eax
0x180030550  jnz     short loc_180030568
0x180030552  cmp     ecx, 80071772h
0x180030558  jz      short loc_180030568
0x18003055a  and     ecx, 1FFF0000h
0x180030560  cmp     ecx, 960000h
0x180030566  jnz     short loc_18003058E
0x180030568  test    r12b, r12b
0x18003056b  jz      short loc_18003057C
0x18003056d  lea     rdx, [rsp+98h+var_58]
0x180030572  mov     rcx, rbx
0x180030575  call    ??4?$shared_ptr@VArchiveStructure@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<ArchiveStructure>::operator=(std::shared_ptr<ArchiveStructure> const &)
0x18003057a  jmp     short loc_18003058E
0x18003057c  lea     r9, [rsp+98h+var_58]
0x180030581  mov     r8, rbx
0x180030584  lea     rdx, [rsp+98h+var_48]
0x180030589  call    ??$emplace@AEBV?$shared_ptr@VArchiveStructure@@@std@@@?$vector@V?$shared_ptr@VArchiveStructure@@@std@@V?$allocator@V?$shared_ptr@VArchiveStructure@@@std@@@2@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$shared_ptr@VArchiveStructure@@@std@@@std@@@std@@@1@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$shared_ptr@VArchiveStructure@@@std@@@std@@@std@@@1@AEBV?$shared_ptr@VArchiveStructure@@@1@@Z; std::vector<std::shared_ptr<ArchiveStructure>>::emplace<std::shared_ptr<ArchiveStructure> const &>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::shared_ptr<ArchiveStructure>>>>,std::shared_ptr<ArchiveStructure> const &)
0x18003058e  mov     rax, [rsp+98h+var_58]
0x180030593  mov     esi, [rax+28h]
0x180030596  mov     rbx, [rsp+98h+var_50]
0x18003059b  test    rbx, rbx
0x18003059e  jz      short loc_1800305D8
0x1800305a0  or      eax, 0FFFFFFFFh
0x1800305a3  lock xadd [rbx+8], eax
0x1800305a8  cmp     eax, 1
0x1800305ab  jnz     short loc_1800305D8
0x1800305ad  mov     rax, [rbx]
0x1800305b0  mov     rcx, rbx
0x1800305b3  mov     rax, [rax]
0x1800305b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800305bb  or      edx, 0FFFFFFFFh
0x1800305be  lock xadd [rbx+0Ch], edx
0x1800305c3  cmp     edx, 1
0x1800305c6  jnz     short loc_1800305D8
0x1800305c8  mov     rdx, [rbx]
0x1800305cb  mov     rcx, rbx
0x1800305ce  mov     rax, [rdx+8]
0x1800305d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800305d7  nop
0x1800305d8  lea     rcx, [rsp+98h+FileTime2]
0x1800305dd  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800305e2  mov     eax, esi
0x1800305e4  jmp     short loc_1800305EA
0x1800305e6  mov     eax, [rsp+98h+FileTime1.dwLowDateTime]
0x1800305ea  mov     rcx, [rsp+98h+var_28]
0x1800305ef  xor     rcx, rsp; StackCookie
0x1800305f2  call    __security_check_cookie
0x1800305f7  lea     r11, [rsp+98h+var_18]
0x1800305ff  mov     rbx, [r11+30h]
0x180030603  mov     rsi, [r11+38h]
0x180030607  mov     rsp, r11
0x18003060a  pop     r15
0x18003060c  pop     r14
0x18003060e  pop     r12
0x180030610  retn
```
