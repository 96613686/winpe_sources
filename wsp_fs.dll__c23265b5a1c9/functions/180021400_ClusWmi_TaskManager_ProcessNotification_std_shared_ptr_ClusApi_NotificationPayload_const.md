# ClusWmi::TaskManager::ProcessNotification(std::shared_ptr<ClusApi::NotificationPayload> const &)

- ea: `0x180021400`
- end: `0x1800215b9`
- name: `?ProcessNotification@TaskManager@ClusWmi@@AEAAJAEBV?$shared_ptr@UNotificationPayload@ClusApi@@@std@@@Z`
- size: `441`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002ad0`
- `0x18000e14c`
- `0x18001b148`
- `0x18001b8d0`
- `0x18001bd0c`
- `0x18001e134`
- `0x18001ff90`
- `0x18001ffc4`
- `0x180021400`
- `0x1800215c0`
- `0x180021c5c`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800214f5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800214f5`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ClusWmi::TaskManager::ProcessNotification(__int64 a1, __int64 a2)
{
  __int64 v4; // rax
  __int64 v5; // rbp
  __int64 v6; // r15
  _QWORD *v7; // rdi
  _QWORD *v8; // rsi
  __int64 v9; // rax
  const WCHAR *v10; // rax
  PCNZWCH lpString2; // rdx
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v15; // [rsp+30h] [rbp-A8h] BYREF
  _BYTE v16[8]; // [rsp+38h] [rbp-A0h] BYREF
  _BYTE v17[16]; // [rsp+40h] [rbp-98h] BYREF
  _BYTE v18[16]; // [rsp+50h] [rbp-88h] BYREF
  _BYTE v19[16]; // [rsp+60h] [rbp-78h] BYREF
  _BYTE v20[48]; // [rsp+70h] [rbp-68h] BYREF

  cxl::AcquireReadLock::AcquireReadLock((cxl::AcquireReadLock *)v18, (struct cxl::NonReentrantRWLock *)(a1 + 168));
  v4 = **(_QWORD **)(a1 + 80);
  v15 = v4;
  while ( !*(_BYTE *)(v4 + 25) )
  {
    v5 = v4 + 32;
    v6 = v4 + 64;
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(v4 + 64) + 16LL))(*(_QWORD *)(v4 + 64), a2)
      && *(_QWORD *)std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<ClusWmi::INotificationWorkItem>,cxl::CaseInsensitive_LessThan,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClusWmi::INotificationWorkItem>>>,0>>::find(
                      a1 + 96,
                      v16,
                      v5) != *(_QWORD *)(a1 + 96) )
    {
      cxl::AcquireReadLock::AcquireReadLock((cxl::AcquireReadLock *)v17, (struct cxl::NonReentrantRWLock *)(a1 + 152));
      v7 = *(_QWORD **)(a1 + 40);
      v8 = *(_QWORD **)(a1 + 48);
      while ( v7 != v8 )
      {
        v9 = (**(__int64 (__fastcall ***)(_QWORD))*v7)(*v7);
        std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v9);
        v10 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v5);
        if ( CompareStringW(0x400u, 1u, v10, -1, lpString2, -1) == 2 )
          break;
        v7 += 2;
      }
      if ( v7 != *(_QWORD **)(a1 + 48) && !(unsigned __int8)ClusWmi::TaskManager::ProcessPendingNotification(a1, v7, v6) )
      {
        v12 = (**(__int64 (__fastcall ***)(_QWORD))*v7)(*v7);
        v13 = std::make_pair<std::wstring const &,std::shared_ptr<ClusWmi::INotificationWorkItem> &>(v20, v12, v6);
        std::map<std::wstring,std::shared_ptr<ClusWmi::INotificationWorkItem>,cxl::CaseInsensitive_LessThan,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClusWmi::INotificationWorkItem>>>>::insert<std::pair<std::wstring,std::shared_ptr<ClusWmi::INotificationWorkItem>>,0>(
          a1 + 96,
          v19,
          v13);
        std::pair<std::wstring const,std::shared_ptr<ClusApi::IResource>>::~pair<std::wstring const,std::shared_ptr<ClusApi::IResource>>(v20);
      }
      cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireSharedTraits<cxl::NonReentrantRWLock>>::Release(v17);
    }
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(&v15);
    v4 = v15;
  }
  cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireSharedTraits<cxl::NonReentrantRWLock>>::Release(v18);
  return 0;
}

```

## disassembly

```asm
0x180021400  mov     [rsp+arg_10], rbx
0x180021405  mov     [rsp+arg_18], rbp
0x18002140a  push    rsi
0x18002140b  push    rdi
0x18002140c  push    r12
0x18002140e  push    r14
0x180021410  push    r15
0x180021412  sub     rsp, 0B0h
0x180021419  mov     rax, cs:__security_cookie
0x180021420  xor     rax, rsp
0x180021423  mov     [rsp+0D8h+var_38], rax
0x18002142b  mov     r12, rdx
0x18002142e  mov     rbx, rcx
0x180021431  lea     rdx, [rcx+0A8h]; struct cxl::NonReentrantRWLock *
0x180021438  lea     rcx, [rsp+0D8h+var_88]; this
0x18002143d  call    ??0AcquireReadLock@cxl@@QEAA@AEAVNonReentrantRWLock@1@@Z; cxl::AcquireReadLock::AcquireReadLock(cxl::NonReentrantRWLock &)
0x180021442  nop
0x180021443  mov     rax, [rbx+50h]
0x180021447  mov     rax, [rax]
0x18002144a  mov     [rsp+0D8h+var_A8], rax
0x18002144f  cmp     byte ptr [rax+19h], 0
0x180021453  jnz     loc_180021580
0x180021459  lea     rbp, [rax+20h]
0x18002145d  lea     r15, [rbp+20h]
0x180021461  mov     rcx, [r15]
0x180021464  mov     rax, [rcx]
0x180021467  mov     rdx, r12
0x18002146a  mov     rax, [rax+10h]
0x18002146e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021473  test    al, al
0x180021475  jz      loc_18002156C
0x18002147b  lea     r14, [rbx+60h]
0x18002147f  mov     r8, rbp
0x180021482  lea     rdx, [rsp+0D8h+var_A0]
0x180021487  mov     rcx, r14
0x18002148a  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UINotificationWorkItem@ClusWmi@@@2@UCaseInsensitive_LessThan@cxl@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UINotificationWorkItem@ClusWmi@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UINotificationWorkItem@ClusWmi@@@2@@std@@@std@@@std@@@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<ClusWmi::INotificationWorkItem>,cxl::CaseInsensitive_LessThan,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClusWmi::INotificationWorkItem>>>,0>>::find(std::wstring const &)
0x18002148f  mov     rcx, [r14]
0x180021492  cmp     [rax], rcx
0x180021495  jz      loc_18002156C
0x18002149b  lea     rdx, [rbx+98h]; struct cxl::NonReentrantRWLock *
0x1800214a2  lea     rcx, [rsp+0D8h+var_98]; this
0x1800214a7  call    ??0AcquireReadLock@cxl@@QEAA@AEAVNonReentrantRWLock@1@@Z; cxl::AcquireReadLock::AcquireReadLock(cxl::NonReentrantRWLock &)
0x1800214ac  nop
0x1800214ad  mov     rdi, [rbx+28h]
0x1800214b1  mov     rsi, [rbx+30h]
0x1800214b5  jmp     short loc_18002150A
0x1800214b7  mov     rcx, [rdi]
0x1800214ba  mov     rax, [rcx]
0x1800214bd  mov     rax, [rax]
0x1800214c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800214c5  mov     rcx, rax
0x1800214c8  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800214cd  mov     rdx, rax
0x1800214d0  mov     rcx, rbp
0x1800214d3  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800214d8  mov     [rsp+0D8h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800214e0  mov     [rsp+0D8h+lpString2], rdx; lpString2
0x1800214e5  or      r9d, 0FFFFFFFFh; cchCount1
0x1800214e9  mov     r8, rax; lpString1
0x1800214ec  lea     edx, [r9+2]; dwCmpFlags
0x1800214f0  mov     ecx, 400h; Locale
0x1800214f5  call    cs:__imp_CompareStringW
0x1800214fc  nop     dword ptr [rax+rax+00h]
0x180021501  cmp     eax, 2
0x180021504  jz      short loc_18002150F
0x180021506  add     rdi, 10h
0x18002150a  cmp     rdi, rsi
0x18002150d  jnz     short loc_1800214B7
0x18002150f  cmp     rdi, [rbx+30h]
0x180021513  jz      short loc_180021562
0x180021515  mov     r8, r15
0x180021518  mov     rdx, rdi
0x18002151b  mov     rcx, rbx
0x18002151e  call    ?ProcessPendingNotification@TaskManager@ClusWmi@@AEAA_NAEBV?$shared_ptr@VTask@ClusWmi@@@std@@AEBV?$shared_ptr@UINotificationWorkItem@ClusWmi@@@4@@Z; ClusWmi::TaskManager::ProcessPendingNotification(std::shared_ptr<ClusWmi::Task> const &,std::shared_ptr<ClusWmi::INotificationWorkItem> const &)
0x180021523  test    al, al
0x180021525  jnz     short loc_180021562
0x180021527  mov     rcx, [rdi]
0x18002152a  mov     rax, [rcx]
0x18002152d  mov     rax, [rax]
0x180021530  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021535  mov     rdx, rax
0x180021538  mov     r8, r15
0x18002153b  lea     rcx, [rsp+0D8h+var_68]
0x180021540  call    ??$make_pair@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV?$shared_ptr@UINotificationWorkItem@ClusWmi@@@2@@std@@YA?AU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UINotificationWorkItem@ClusWmi@@@2@@0@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@AEAV?$shared_ptr@UINotificationWorkItem@ClusWmi@@@0@@Z; std::make_pair<std::wstring const &,std::shared_ptr<ClusWmi::INotificationWorkItem> &>(std::wstring const &,std::shared_ptr<ClusWmi::INotificationWorkItem> &)
0x180021545  nop
0x180021546  mov     r8, rax
0x180021549  lea     rdx, [rsp+0D8h+var_78]
0x18002154e  mov     rcx, r14
0x180021551  call    ??$insert@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UINotificationWorkItem@ClusWmi@@@2@@std@@$0A@@?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UINotificationWorkItem@ClusWmi@@@2@UCaseInsensitive_LessThan@cxl@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UINotificationWorkItem@ClusWmi@@@2@@std@@@2@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UINotificationWorkItem@ClusWmi@@@2@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UINotificationWorkItem@ClusWmi@@@2@@1@@Z; std::map<std::wstring,std::shared_ptr<ClusWmi::INotificationWorkItem>,cxl::CaseInsensitive_LessThan,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClusWmi::INotificationWorkItem>>>>::insert<std::pair<std::wstring,std::shared_ptr<ClusWmi::INotificationWorkItem>>,0>(std::pair<std::wstring,std::shared_ptr<ClusWmi::INotificationWorkItem>> &&)
0x180021556  nop
0x180021557  lea     rcx, [rsp+0D8h+var_68]
0x18002155c  call    ??1?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UIResource@ClusApi@@@2@@std@@QEAA@XZ; std::pair<std::wstring const,std::shared_ptr<ClusApi::IResource>>::~pair<std::wstring const,std::shared_ptr<ClusApi::IResource>>(void)
0x180021561  nop
0x180021562  lea     rcx, [rsp+0D8h+var_98]
0x180021567  call    ?Release@?$ScopedResOwner@VNonReentrantRWLock@cxl@@V?$AcquireSharedTraits@VNonReentrantRWLock@cxl@@@2@@cxl@@QEBAXXZ; cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireSharedTraits<cxl::NonReentrantRWLock>>::Release(void)
0x18002156c  lea     rcx, [rsp+0D8h+var_A8]
0x180021571  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(void)
0x180021576  mov     rax, [rsp+0D8h+var_A8]
0x18002157b  jmp     loc_18002144F
0x180021580  lea     rcx, [rsp+0D8h+var_88]
0x180021585  call    ?Release@?$ScopedResOwner@VNonReentrantRWLock@cxl@@V?$AcquireSharedTraits@VNonReentrantRWLock@cxl@@@2@@cxl@@QEBAXXZ; cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireSharedTraits<cxl::NonReentrantRWLock>>::Release(void)
0x18002158a  xor     eax, eax
0x18002158c  mov     rcx, [rsp+0D8h+var_38]
0x180021594  xor     rcx, rsp; StackCookie
0x180021597  call    __security_check_cookie
0x18002159c  lea     r11, [rsp+0D8h+var_28]
0x1800215a4  mov     rbx, [r11+40h]
0x1800215a8  mov     rbp, [r11+48h]
0x1800215ac  mov     rsp, r11
0x1800215af  pop     r15
0x1800215b1  pop     r14
0x1800215b3  pop     r12
0x1800215b5  pop     rdi
0x1800215b6  pop     rsi
0x1800215b7  retn
```
