# ClusWmi::TaskManager::ProcessNotification(std::shared_ptr<ClusApi::NotificationPayload> const &)

- ea: `0x18001e0c0`
- end: `0x18001e279`
- name: `?ProcessNotification@TaskManager@ClusWmi@@AEAAJAEBV?$shared_ptr@UNotificationPayload@ClusApi@@@std@@@Z`
- size: `441`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002b50`
- `0x18000da34`
- `0x180017f7c`
- `0x180018704`
- `0x180018b40`
- `0x18001af54`
- `0x18001ccc0`
- `0x18001ccf4`
- `0x18001e0c0`
- `0x18001e280`
- `0x18001e91c`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001e1b5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001e1b5`

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
        std::pair<std::wstring const,std::shared_ptr<ClusWmi::INotificationWorkItem>>::~pair<std::wstring const,std::shared_ptr<ClusWmi::INotificationWorkItem>>(v20);
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
0x18001e0c0  mov     [rsp+arg_10], rbx
0x18001e0c5  mov     [rsp+arg_18], rbp
0x18001e0ca  push    rsi
0x18001e0cb  push    rdi
0x18001e0cc  push    r12
0x18001e0ce  push    r14
0x18001e0d0  push    r15
0x18001e0d2  sub     rsp, 0B0h
0x18001e0d9  mov     rax, cs:__security_cookie
0x18001e0e0  xor     rax, rsp
0x18001e0e3  mov     [rsp+0D8h+var_38], rax
0x18001e0eb  mov     r12, rdx
0x18001e0ee  mov     rbx, rcx
0x18001e0f1  lea     rdx, [rcx+0A8h]; struct cxl::NonReentrantRWLock *
0x18001e0f8  lea     rcx, [rsp+0D8h+var_88]; this
0x18001e0fd  call    ??0AcquireReadLock@cxl@@QEAA@AEAVNonReentrantRWLock@1@@Z; cxl::AcquireReadLock::AcquireReadLock(cxl::NonReentrantRWLock &)
0x18001e102  nop
0x18001e103  mov     rax, [rbx+50h]
0x18001e107  mov     rax, [rax]
0x18001e10a  mov     [rsp+0D8h+var_A8], rax
0x18001e10f  cmp     byte ptr [rax+19h], 0
0x18001e113  jnz     loc_18001E240
0x18001e119  lea     rbp, [rax+20h]
0x18001e11d  lea     r15, [rbp+20h]
0x18001e121  mov     rcx, [r15]
0x18001e124  mov     rax, [rcx]
0x18001e127  mov     rdx, r12
0x18001e12a  mov     rax, [rax+10h]
0x18001e12e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e133  test    al, al
0x18001e135  jz      loc_18001E22C
0x18001e13b  lea     r14, [rbx+60h]
0x18001e13f  mov     r8, rbp
0x18001e142  lea     rdx, [rsp+0D8h+var_A0]
0x18001e147  mov     rcx, r14
0x18001e14a  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UINotificationWorkItem@ClusWmi@@@2@UCaseInsensitive_LessThan@cxl@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UINotificationWorkItem@ClusWmi@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UINotificationWorkItem@ClusWmi@@@2@@std@@@std@@@std@@@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<ClusWmi::INotificationWorkItem>,cxl::CaseInsensitive_LessThan,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClusWmi::INotificationWorkItem>>>,0>>::find(std::wstring const &)
0x18001e14f  mov     rcx, [r14]
0x18001e152  cmp     [rax], rcx
0x18001e155  jz      loc_18001E22C
0x18001e15b  lea     rdx, [rbx+98h]; struct cxl::NonReentrantRWLock *
0x18001e162  lea     rcx, [rsp+0D8h+var_98]; this
0x18001e167  call    ??0AcquireReadLock@cxl@@QEAA@AEAVNonReentrantRWLock@1@@Z; cxl::AcquireReadLock::AcquireReadLock(cxl::NonReentrantRWLock &)
0x18001e16c  nop
0x18001e16d  mov     rdi, [rbx+28h]
0x18001e171  mov     rsi, [rbx+30h]
0x18001e175  jmp     short loc_18001E1CA
0x18001e177  mov     rcx, [rdi]
0x18001e17a  mov     rax, [rcx]
0x18001e17d  mov     rax, [rax]
0x18001e180  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e185  mov     rcx, rax
0x18001e188  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001e18d  mov     rdx, rax
0x18001e190  mov     rcx, rbp
0x18001e193  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001e198  mov     [rsp+0D8h+cchCount2], 0FFFFFFFFh; cchCount2
0x18001e1a0  mov     [rsp+0D8h+lpString2], rdx; lpString2
0x18001e1a5  or      r9d, 0FFFFFFFFh; cchCount1
0x18001e1a9  mov     r8, rax; lpString1
0x18001e1ac  lea     edx, [r9+2]; dwCmpFlags
0x18001e1b0  mov     ecx, 400h; Locale
0x18001e1b5  call    cs:__imp_CompareStringW
0x18001e1bc  nop     dword ptr [rax+rax+00h]
0x18001e1c1  cmp     eax, 2
0x18001e1c4  jz      short loc_18001E1CF
0x18001e1c6  add     rdi, 10h
0x18001e1ca  cmp     rdi, rsi
0x18001e1cd  jnz     short loc_18001E177
0x18001e1cf  cmp     rdi, [rbx+30h]
0x18001e1d3  jz      short loc_18001E222
0x18001e1d5  mov     r8, r15
0x18001e1d8  mov     rdx, rdi
0x18001e1db  mov     rcx, rbx
0x18001e1de  call    ?ProcessPendingNotification@TaskManager@ClusWmi@@AEAA_NAEBV?$shared_ptr@VTask@ClusWmi@@@std@@AEBV?$shared_ptr@UINotificationWorkItem@ClusWmi@@@4@@Z; ClusWmi::TaskManager::ProcessPendingNotification(std::shared_ptr<ClusWmi::Task> const &,std::shared_ptr<ClusWmi::INotificationWorkItem> const &)
0x18001e1e3  test    al, al
0x18001e1e5  jnz     short loc_18001E222
0x18001e1e7  mov     rcx, [rdi]
0x18001e1ea  mov     rax, [rcx]
0x18001e1ed  mov     rax, [rax]
0x18001e1f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1f5  mov     rdx, rax
0x18001e1f8  mov     r8, r15
0x18001e1fb  lea     rcx, [rsp+0D8h+var_68]
0x18001e200  call    ??$make_pair@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV?$shared_ptr@UINotificationWorkItem@ClusWmi@@@2@@std@@YA?AU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UINotificationWorkItem@ClusWmi@@@2@@0@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@AEAV?$shared_ptr@UINotificationWorkItem@ClusWmi@@@0@@Z; std::make_pair<std::wstring const &,std::shared_ptr<ClusWmi::INotificationWorkItem> &>(std::wstring const &,std::shared_ptr<ClusWmi::INotificationWorkItem> &)
0x18001e205  nop
0x18001e206  mov     r8, rax
0x18001e209  lea     rdx, [rsp+0D8h+var_78]
0x18001e20e  mov     rcx, r14
0x18001e211  call    ??$insert@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UINotificationWorkItem@ClusWmi@@@2@@std@@$0A@@?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UINotificationWorkItem@ClusWmi@@@2@UCaseInsensitive_LessThan@cxl@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UINotificationWorkItem@ClusWmi@@@2@@std@@@2@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UINotificationWorkItem@ClusWmi@@@2@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UINotificationWorkItem@ClusWmi@@@2@@1@@Z; std::map<std::wstring,std::shared_ptr<ClusWmi::INotificationWorkItem>,cxl::CaseInsensitive_LessThan,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClusWmi::INotificationWorkItem>>>>::insert<std::pair<std::wstring,std::shared_ptr<ClusWmi::INotificationWorkItem>>,0>(std::pair<std::wstring,std::shared_ptr<ClusWmi::INotificationWorkItem>> &&)
0x18001e216  nop
0x18001e217  lea     rcx, [rsp+0D8h+var_68]
0x18001e21c  call    ??1?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UINotificationWorkItem@ClusWmi@@@2@@std@@QEAA@XZ; std::pair<std::wstring const,std::shared_ptr<ClusWmi::INotificationWorkItem>>::~pair<std::wstring const,std::shared_ptr<ClusWmi::INotificationWorkItem>>(void)
0x18001e221  nop
0x18001e222  lea     rcx, [rsp+0D8h+var_98]
0x18001e227  call    ?Release@?$ScopedResOwner@VNonReentrantRWLock@cxl@@V?$AcquireSharedTraits@VNonReentrantRWLock@cxl@@@2@@cxl@@QEBAXXZ; cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireSharedTraits<cxl::NonReentrantRWLock>>::Release(void)
0x18001e22c  lea     rcx, [rsp+0D8h+var_A8]
0x18001e231  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(void)
0x18001e236  mov     rax, [rsp+0D8h+var_A8]
0x18001e23b  jmp     loc_18001E10F
0x18001e240  lea     rcx, [rsp+0D8h+var_88]
0x18001e245  call    ?Release@?$ScopedResOwner@VNonReentrantRWLock@cxl@@V?$AcquireSharedTraits@VNonReentrantRWLock@cxl@@@2@@cxl@@QEBAXXZ; cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireSharedTraits<cxl::NonReentrantRWLock>>::Release(void)
0x18001e24a  xor     eax, eax
0x18001e24c  mov     rcx, [rsp+0D8h+var_38]
0x18001e254  xor     rcx, rsp; StackCookie
0x18001e257  call    __security_check_cookie
0x18001e25c  lea     r11, [rsp+0D8h+var_28]
0x18001e264  mov     rbx, [r11+40h]
0x18001e268  mov     rbp, [r11+48h]
0x18001e26c  mov     rsp, r11
0x18001e26f  pop     r15
0x18001e271  pop     r14
0x18001e273  pop     r12
0x18001e275  pop     rdi
0x18001e276  pop     rsi
0x18001e277  retn
```
