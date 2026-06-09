# ClusWmi::TaskManager::ProcessNotification(std::shared_ptr<ClusApi::NotificationPayload> const &)

- ea: `0x18001d520`
- end: `0x18001d6d2`
- name: `?ProcessNotification@TaskManager@ClusWmi@@AEAAJAEBV?$shared_ptr@UNotificationPayload@ClusApi@@@std@@@Z`
- size: `434`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002ae0`
- `0x18000d618`
- `0x180017640`
- `0x180017d78`
- `0x1800181a4`
- `0x18001a4c8`
- `0x18001c198`
- `0x18001c1cc`
- `0x18001d520`
- `0x18001d6d8`
- `0x18001dd64`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001d615`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001d615`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ClusWmi::TaskManager::ProcessNotification(__int64 a1, __int64 a2)
{
  __int64 v4; // rdx
  __int64 v5; // rax
  __int64 v6; // rbp
  __int64 v7; // r15
  __int64 v8; // rdx
  _QWORD *v9; // rdi
  _QWORD *v10; // rsi
  __int64 v11; // rax
  const WCHAR *v12; // rax
  PCNZWCH lpString2; // rdx
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v17; // [rsp+30h] [rbp-A8h] BYREF
  _BYTE v18[8]; // [rsp+38h] [rbp-A0h] BYREF
  _BYTE v19[16]; // [rsp+40h] [rbp-98h] BYREF
  _BYTE v20[16]; // [rsp+50h] [rbp-88h] BYREF
  _BYTE v21[16]; // [rsp+60h] [rbp-78h] BYREF
  _BYTE v22[48]; // [rsp+70h] [rbp-68h] BYREF

  cxl::AcquireReadLock::AcquireReadLock((cxl::AcquireReadLock *)v20, (struct cxl::NonReentrantRWLock *)(a1 + 168));
  v5 = **(_QWORD **)(a1 + 80);
  v17 = v5;
  while ( !*(_BYTE *)(v5 + 25) )
  {
    v6 = v5 + 32;
    v7 = v5 + 64;
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(v5 + 64) + 16LL))(*(_QWORD *)(v5 + 64), a2)
      && *(_QWORD *)std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<ClusWmi::INotificationWorkItem>,cxl::CaseInsensitive_LessThan,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClusWmi::INotificationWorkItem>>>,0>>::find(
                      a1 + 96,
                      v18,
                      v6) != *(_QWORD *)(a1 + 96) )
    {
      cxl::AcquireReadLock::AcquireReadLock((cxl::AcquireReadLock *)v19, (struct cxl::NonReentrantRWLock *)(a1 + 152));
      v9 = *(_QWORD **)(a1 + 40);
      v10 = *(_QWORD **)(a1 + 48);
      while ( v9 != v10 )
      {
        v11 = (**(__int64 (__fastcall ***)(_QWORD))*v9)(*v9);
        std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v11);
        v12 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v6);
        if ( CompareStringW(0x400u, 1u, v12, -1, lpString2, -1) == 2 )
          break;
        v9 += 2;
      }
      if ( v9 != *(_QWORD **)(a1 + 48) && !(unsigned __int8)ClusWmi::TaskManager::ProcessPendingNotification(a1, v9, v7) )
      {
        v14 = (**(__int64 (__fastcall ***)(_QWORD))*v9)(*v9);
        v15 = std::make_pair<std::wstring const &,std::shared_ptr<ClusWmi::INotificationWorkItem> &>(v22, v14, v7);
        std::map<std::wstring,std::shared_ptr<ClusWmi::INotificationWorkItem>,cxl::CaseInsensitive_LessThan,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClusWmi::INotificationWorkItem>>>>::insert<std::pair<std::wstring,std::shared_ptr<ClusWmi::INotificationWorkItem>>,0>(
          a1 + 96,
          v21,
          v15);
        std::pair<std::wstring const,std::shared_ptr<ClusWmi::INotificationWorkItem>>::~pair<std::wstring const,std::shared_ptr<ClusWmi::INotificationWorkItem>>(v22);
      }
      cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireSharedTraits<cxl::NonReentrantRWLock>>::Release(v19, v8);
    }
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(&v17);
    v5 = v17;
  }
  cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireSharedTraits<cxl::NonReentrantRWLock>>::Release(v20, v4);
  return 0;
}

```

## disassembly

```asm
0x18001d520  mov     [rsp+arg_10], rbx
0x18001d525  mov     [rsp+arg_18], rbp
0x18001d52a  push    rsi
0x18001d52b  push    rdi
0x18001d52c  push    r12
0x18001d52e  push    r14
0x18001d530  push    r15
0x18001d532  sub     rsp, 0B0h
0x18001d539  mov     rax, cs:__security_cookie
0x18001d540  xor     rax, rsp
0x18001d543  mov     [rsp+0D8h+var_38], rax
0x18001d54b  mov     r12, rdx
0x18001d54e  mov     rbx, rcx
0x18001d551  lea     rdx, [rcx+0A8h]; struct cxl::NonReentrantRWLock *
0x18001d558  lea     rcx, [rsp+0D8h+var_88]; this
0x18001d55d  call    ??0AcquireReadLock@cxl@@QEAA@AEAVNonReentrantRWLock@1@@Z; cxl::AcquireReadLock::AcquireReadLock(cxl::NonReentrantRWLock &)
0x18001d562  nop
0x18001d563  mov     rax, [rbx+50h]
0x18001d567  mov     rax, [rax]
0x18001d56a  mov     [rsp+0D8h+var_A8], rax
0x18001d56f  cmp     byte ptr [rax+19h], 0
0x18001d573  jnz     loc_18001D69A
0x18001d579  lea     rbp, [rax+20h]
0x18001d57d  lea     r15, [rbp+20h]
0x18001d581  mov     rcx, [r15]
0x18001d584  mov     rax, [rcx]
0x18001d587  mov     rdx, r12
0x18001d58a  mov     rax, [rax+10h]
0x18001d58e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d593  test    al, al
0x18001d595  jz      loc_18001D686
0x18001d59b  lea     r14, [rbx+60h]
0x18001d59f  mov     r8, rbp
0x18001d5a2  lea     rdx, [rsp+0D8h+var_A0]
0x18001d5a7  mov     rcx, r14
0x18001d5aa  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UINotificationWorkItem@ClusWmi@@@2@UCaseInsensitive_LessThan@cxl@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UINotificationWorkItem@ClusWmi@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UINotificationWorkItem@ClusWmi@@@2@@std@@@std@@@std@@@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<ClusWmi::INotificationWorkItem>,cxl::CaseInsensitive_LessThan,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClusWmi::INotificationWorkItem>>>,0>>::find(std::wstring const &)
0x18001d5af  mov     rcx, [r14]
0x18001d5b2  cmp     [rax], rcx
0x18001d5b5  jz      loc_18001D686
0x18001d5bb  lea     rdx, [rbx+98h]; struct cxl::NonReentrantRWLock *
0x18001d5c2  lea     rcx, [rsp+0D8h+var_98]; this
0x18001d5c7  call    ??0AcquireReadLock@cxl@@QEAA@AEAVNonReentrantRWLock@1@@Z; cxl::AcquireReadLock::AcquireReadLock(cxl::NonReentrantRWLock &)
0x18001d5cc  nop
0x18001d5cd  mov     rdi, [rbx+28h]
0x18001d5d1  mov     rsi, [rbx+30h]
0x18001d5d5  jmp     short loc_18001D624
0x18001d5d7  mov     rcx, [rdi]
0x18001d5da  mov     rax, [rcx]
0x18001d5dd  mov     rax, [rax]
0x18001d5e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d5e5  mov     rcx, rax
0x18001d5e8  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001d5ed  mov     rdx, rax
0x18001d5f0  mov     rcx, rbp
0x18001d5f3  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001d5f8  mov     [rsp+0D8h+cchCount2], 0FFFFFFFFh; cchCount2
0x18001d600  mov     [rsp+0D8h+lpString2], rdx; lpString2
0x18001d605  or      r9d, 0FFFFFFFFh; cchCount1
0x18001d609  mov     r8, rax; lpString1
0x18001d60c  lea     edx, [r9+2]; dwCmpFlags
0x18001d610  mov     ecx, 400h; Locale
0x18001d615  call    cs:__imp_CompareStringW
0x18001d61b  cmp     eax, 2
0x18001d61e  jz      short loc_18001D629
0x18001d620  add     rdi, 10h
0x18001d624  cmp     rdi, rsi
0x18001d627  jnz     short loc_18001D5D7
0x18001d629  cmp     rdi, [rbx+30h]
0x18001d62d  jz      short loc_18001D67C
0x18001d62f  mov     r8, r15
0x18001d632  mov     rdx, rdi
0x18001d635  mov     rcx, rbx
0x18001d638  call    ?ProcessPendingNotification@TaskManager@ClusWmi@@AEAA_NAEBV?$shared_ptr@VTask@ClusWmi@@@std@@AEBV?$shared_ptr@UINotificationWorkItem@ClusWmi@@@4@@Z; ClusWmi::TaskManager::ProcessPendingNotification(std::shared_ptr<ClusWmi::Task> const &,std::shared_ptr<ClusWmi::INotificationWorkItem> const &)
0x18001d63d  test    al, al
0x18001d63f  jnz     short loc_18001D67C
0x18001d641  mov     rcx, [rdi]
0x18001d644  mov     rax, [rcx]
0x18001d647  mov     rax, [rax]
0x18001d64a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d64f  mov     rdx, rax
0x18001d652  mov     r8, r15
0x18001d655  lea     rcx, [rsp+0D8h+var_68]
0x18001d65a  call    ??$make_pair@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV?$shared_ptr@UINotificationWorkItem@ClusWmi@@@2@@std@@YA?AU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UINotificationWorkItem@ClusWmi@@@2@@0@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@AEAV?$shared_ptr@UINotificationWorkItem@ClusWmi@@@0@@Z; std::make_pair<std::wstring const &,std::shared_ptr<ClusWmi::INotificationWorkItem> &>(std::wstring const &,std::shared_ptr<ClusWmi::INotificationWorkItem> &)
0x18001d65f  nop
0x18001d660  mov     r8, rax
0x18001d663  lea     rdx, [rsp+0D8h+var_78]
0x18001d668  mov     rcx, r14
0x18001d66b  call    ??$insert@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UINotificationWorkItem@ClusWmi@@@2@@std@@$0A@@?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UINotificationWorkItem@ClusWmi@@@2@UCaseInsensitive_LessThan@cxl@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UINotificationWorkItem@ClusWmi@@@2@@std@@@2@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UINotificationWorkItem@ClusWmi@@@2@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UINotificationWorkItem@ClusWmi@@@2@@1@@Z; std::map<std::wstring,std::shared_ptr<ClusWmi::INotificationWorkItem>,cxl::CaseInsensitive_LessThan,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClusWmi::INotificationWorkItem>>>>::insert<std::pair<std::wstring,std::shared_ptr<ClusWmi::INotificationWorkItem>>,0>(std::pair<std::wstring,std::shared_ptr<ClusWmi::INotificationWorkItem>> &&)
0x18001d670  nop
0x18001d671  lea     rcx, [rsp+0D8h+var_68]
0x18001d676  call    ??1?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UINotificationWorkItem@ClusWmi@@@2@@std@@QEAA@XZ; std::pair<std::wstring const,std::shared_ptr<ClusWmi::INotificationWorkItem>>::~pair<std::wstring const,std::shared_ptr<ClusWmi::INotificationWorkItem>>(void)
0x18001d67b  nop
0x18001d67c  lea     rcx, [rsp+0D8h+var_98]
0x18001d681  call    ?Release@?$ScopedResOwner@VNonReentrantRWLock@cxl@@V?$AcquireSharedTraits@VNonReentrantRWLock@cxl@@@2@@cxl@@QEBAXXZ; cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireSharedTraits<cxl::NonReentrantRWLock>>::Release(void)
0x18001d686  lea     rcx, [rsp+0D8h+var_A8]
0x18001d68b  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(void)
0x18001d690  mov     rax, [rsp+0D8h+var_A8]
0x18001d695  jmp     loc_18001D56F
0x18001d69a  lea     rcx, [rsp+0D8h+var_88]
0x18001d69f  call    ?Release@?$ScopedResOwner@VNonReentrantRWLock@cxl@@V?$AcquireSharedTraits@VNonReentrantRWLock@cxl@@@2@@cxl@@QEBAXXZ; cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireSharedTraits<cxl::NonReentrantRWLock>>::Release(void)
0x18001d6a4  xor     eax, eax
0x18001d6a6  mov     rcx, [rsp+0D8h+var_38]
0x18001d6ae  xor     rcx, rsp; StackCookie
0x18001d6b1  call    __security_check_cookie
0x18001d6b6  lea     r11, [rsp+0D8h+var_28]
0x18001d6be  mov     rbx, [r11+40h]
0x18001d6c2  mov     rbp, [r11+48h]
0x18001d6c6  mov     rsp, r11
0x18001d6c9  pop     r15
0x18001d6cb  pop     r14
0x18001d6cd  pop     r12
0x18001d6cf  pop     rdi
0x18001d6d0  pop     rsi
0x18001d6d1  retn
```
