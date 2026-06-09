# ClusWmi::TaskManager::ProcessNotification(std::shared_ptr<ClusApi::NotificationPayload> const &)

- ea: `0x180020770`
- end: `0x180020922`
- name: `?ProcessNotification@TaskManager@ClusWmi@@AEAAJAEBV?$shared_ptr@UNotificationPayload@ClusApi@@@std@@@Z`
- size: `434`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002a70`
- `0x18000dd74`
- `0x18001a728`
- `0x18001ae60`
- `0x18001b28c`
- `0x18001d5a8`
- `0x18001f368`
- `0x18001f39c`
- `0x180020770`
- `0x180020928`
- `0x180020fb4`
- `0x1800a9010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180020865`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180020865`

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
0x180020770  mov     [rsp+arg_10], rbx
0x180020775  mov     [rsp+arg_18], rbp
0x18002077a  push    rsi
0x18002077b  push    rdi
0x18002077c  push    r12
0x18002077e  push    r14
0x180020780  push    r15
0x180020782  sub     rsp, 0B0h
0x180020789  mov     rax, cs:__security_cookie
0x180020790  xor     rax, rsp
0x180020793  mov     [rsp+0D8h+var_38], rax
0x18002079b  mov     r12, rdx
0x18002079e  mov     rbx, rcx
0x1800207a1  lea     rdx, [rcx+0A8h]; struct cxl::NonReentrantRWLock *
0x1800207a8  lea     rcx, [rsp+0D8h+var_88]; this
0x1800207ad  call    ??0AcquireReadLock@cxl@@QEAA@AEAVNonReentrantRWLock@1@@Z; cxl::AcquireReadLock::AcquireReadLock(cxl::NonReentrantRWLock &)
0x1800207b2  nop
0x1800207b3  mov     rax, [rbx+50h]
0x1800207b7  mov     rax, [rax]
0x1800207ba  mov     [rsp+0D8h+var_A8], rax
0x1800207bf  cmp     byte ptr [rax+19h], 0
0x1800207c3  jnz     loc_1800208EA
0x1800207c9  lea     rbp, [rax+20h]
0x1800207cd  lea     r15, [rbp+20h]
0x1800207d1  mov     rcx, [r15]
0x1800207d4  mov     rax, [rcx]
0x1800207d7  mov     rdx, r12
0x1800207da  mov     rax, [rax+10h]
0x1800207de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800207e3  test    al, al
0x1800207e5  jz      loc_1800208D6
0x1800207eb  lea     r14, [rbx+60h]
0x1800207ef  mov     r8, rbp
0x1800207f2  lea     rdx, [rsp+0D8h+var_A0]
0x1800207f7  mov     rcx, r14
0x1800207fa  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UINotificationWorkItem@ClusWmi@@@2@UCaseInsensitive_LessThan@cxl@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UINotificationWorkItem@ClusWmi@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UINotificationWorkItem@ClusWmi@@@2@@std@@@std@@@std@@@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<ClusWmi::INotificationWorkItem>,cxl::CaseInsensitive_LessThan,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClusWmi::INotificationWorkItem>>>,0>>::find(std::wstring const &)
0x1800207ff  mov     rcx, [r14]
0x180020802  cmp     [rax], rcx
0x180020805  jz      loc_1800208D6
0x18002080b  lea     rdx, [rbx+98h]; struct cxl::NonReentrantRWLock *
0x180020812  lea     rcx, [rsp+0D8h+var_98]; this
0x180020817  call    ??0AcquireReadLock@cxl@@QEAA@AEAVNonReentrantRWLock@1@@Z; cxl::AcquireReadLock::AcquireReadLock(cxl::NonReentrantRWLock &)
0x18002081c  nop
0x18002081d  mov     rdi, [rbx+28h]
0x180020821  mov     rsi, [rbx+30h]
0x180020825  jmp     short loc_180020874
0x180020827  mov     rcx, [rdi]
0x18002082a  mov     rax, [rcx]
0x18002082d  mov     rax, [rax]
0x180020830  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020835  mov     rcx, rax
0x180020838  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002083d  mov     rdx, rax
0x180020840  mov     rcx, rbp
0x180020843  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180020848  mov     [rsp+0D8h+cchCount2], 0FFFFFFFFh; cchCount2
0x180020850  mov     [rsp+0D8h+lpString2], rdx; lpString2
0x180020855  or      r9d, 0FFFFFFFFh; cchCount1
0x180020859  mov     r8, rax; lpString1
0x18002085c  lea     edx, [r9+2]; dwCmpFlags
0x180020860  mov     ecx, 400h; Locale
0x180020865  call    cs:__imp_CompareStringW
0x18002086b  cmp     eax, 2
0x18002086e  jz      short loc_180020879
0x180020870  add     rdi, 10h
0x180020874  cmp     rdi, rsi
0x180020877  jnz     short loc_180020827
0x180020879  cmp     rdi, [rbx+30h]
0x18002087d  jz      short loc_1800208CC
0x18002087f  mov     r8, r15
0x180020882  mov     rdx, rdi
0x180020885  mov     rcx, rbx
0x180020888  call    ?ProcessPendingNotification@TaskManager@ClusWmi@@AEAA_NAEBV?$shared_ptr@VTask@ClusWmi@@@std@@AEBV?$shared_ptr@UINotificationWorkItem@ClusWmi@@@4@@Z; ClusWmi::TaskManager::ProcessPendingNotification(std::shared_ptr<ClusWmi::Task> const &,std::shared_ptr<ClusWmi::INotificationWorkItem> const &)
0x18002088d  test    al, al
0x18002088f  jnz     short loc_1800208CC
0x180020891  mov     rcx, [rdi]
0x180020894  mov     rax, [rcx]
0x180020897  mov     rax, [rax]
0x18002089a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002089f  mov     rdx, rax
0x1800208a2  mov     r8, r15
0x1800208a5  lea     rcx, [rsp+0D8h+var_68]
0x1800208aa  call    ??$make_pair@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV?$shared_ptr@UINotificationWorkItem@ClusWmi@@@2@@std@@YA?AU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UINotificationWorkItem@ClusWmi@@@2@@0@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@AEAV?$shared_ptr@UINotificationWorkItem@ClusWmi@@@0@@Z; std::make_pair<std::wstring const &,std::shared_ptr<ClusWmi::INotificationWorkItem> &>(std::wstring const &,std::shared_ptr<ClusWmi::INotificationWorkItem> &)
0x1800208af  nop
0x1800208b0  mov     r8, rax
0x1800208b3  lea     rdx, [rsp+0D8h+var_78]
0x1800208b8  mov     rcx, r14
0x1800208bb  call    ??$insert@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UINotificationWorkItem@ClusWmi@@@2@@std@@$0A@@?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UINotificationWorkItem@ClusWmi@@@2@UCaseInsensitive_LessThan@cxl@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UINotificationWorkItem@ClusWmi@@@2@@std@@@2@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UINotificationWorkItem@ClusWmi@@@2@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UINotificationWorkItem@ClusWmi@@@2@@1@@Z; std::map<std::wstring,std::shared_ptr<ClusWmi::INotificationWorkItem>,cxl::CaseInsensitive_LessThan,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClusWmi::INotificationWorkItem>>>>::insert<std::pair<std::wstring,std::shared_ptr<ClusWmi::INotificationWorkItem>>,0>(std::pair<std::wstring,std::shared_ptr<ClusWmi::INotificationWorkItem>> &&)
0x1800208c0  nop
0x1800208c1  lea     rcx, [rsp+0D8h+var_68]
0x1800208c6  call    ??1?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UIResource@ClusApi@@@2@@std@@QEAA@XZ; std::pair<std::wstring const,std::shared_ptr<ClusApi::IResource>>::~pair<std::wstring const,std::shared_ptr<ClusApi::IResource>>(void)
0x1800208cb  nop
0x1800208cc  lea     rcx, [rsp+0D8h+var_98]
0x1800208d1  call    ?Release@?$ScopedResOwner@VNonReentrantRWLock@cxl@@V?$AcquireSharedTraits@VNonReentrantRWLock@cxl@@@2@@cxl@@QEBAXXZ; cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireSharedTraits<cxl::NonReentrantRWLock>>::Release(void)
0x1800208d6  lea     rcx, [rsp+0D8h+var_A8]
0x1800208db  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(void)
0x1800208e0  mov     rax, [rsp+0D8h+var_A8]
0x1800208e5  jmp     loc_1800207BF
0x1800208ea  lea     rcx, [rsp+0D8h+var_88]
0x1800208ef  call    ?Release@?$ScopedResOwner@VNonReentrantRWLock@cxl@@V?$AcquireSharedTraits@VNonReentrantRWLock@cxl@@@2@@cxl@@QEBAXXZ; cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireSharedTraits<cxl::NonReentrantRWLock>>::Release(void)
0x1800208f4  xor     eax, eax
0x1800208f6  mov     rcx, [rsp+0D8h+var_38]
0x1800208fe  xor     rcx, rsp; StackCookie
0x180020901  call    __security_check_cookie
0x180020906  lea     r11, [rsp+0D8h+var_28]
0x18002090e  mov     rbx, [r11+40h]
0x180020912  mov     rbp, [r11+48h]
0x180020916  mov     rsp, r11
0x180020919  pop     r15
0x18002091b  pop     r14
0x18002091d  pop     r12
0x18002091f  pop     rdi
0x180020920  pop     rsi
0x180020921  retn
```
