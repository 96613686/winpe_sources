# CShellExperienceDispatcher::_OnNavigateToView(Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *)

- ea: `0x180041040`
- end: `0x18004131b`
- name: `?_OnNavigateToView@CShellExperienceDispatcher@@AEAAJPEAUIViewWrapper@ViewManagerInterop@Shell@Internal@Windows@@@Z`
- size: `731`
- prototype: `__int64 __fastcall(CShellExperienceDispatcher *__hidden this, struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180061640`

## callees

- `0x180008acc`
- `0x18000ae24`
- `0x18000b838`
- `0x18003c5e4`
- `0x18003f4f0`
- `0x18003fb88`
- `0x180041040`
- `0x18006280c`
- `0x180086d04`
- `0x1800bcb98`
- `0x1800eeae0`
- `0x18014c1ec`
- `0x18014c240`
- `0x18014c290`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180041130`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180041180`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180041130`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180041180`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180041074`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180041074`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800410de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004111e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041218`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004122f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004126c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800410de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004111e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041218`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004122f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004126c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180041243`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180041243`

## string_xrefs

- `0x180041108`: `onecoreuap\shell\onecore\coreexperiencebrokercomponents\shellexperiencedispatcher\lib\shellexperiencedispatcher.cpp`
- `0x180041256`: `onecoreuap\shell\onecore\coreexperiencebrokercomponents\shellexperiencedispatcher\lib\shellexperiencedispatcher.cpp`
- `0x1800412eb`: `onecoreuap\shell\onecore\coreexperiencebrokercomponents\shellexperiencedispatcher\lib\shellexperiencedispatcher.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CShellExperienceDispatcher::_OnNavigateToView(
        RTL_SRWLOCK *this,
        struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *a2)
{
  struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *v2; // rdi
  CShellExperienceDispatcher *v3; // rsi
  struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *v4; // r14
  RTL_SRWLOCK *v5; // r15
  _QWORD *v6; // rax
  __int64 v7; // rcx
  _QWORD *v8; // rax
  __int64 v9; // r8
  HSTRING **v10; // rax
  HSTRING *v11; // rbx
  char v12; // r13
  HSTRING *v13; // r12
  HSTRING v14; // rsi
  __int64 (__fastcall *v15)(HSTRING, HSTRING *); // rdi
  int v16; // eax
  unsigned int v17; // edi
  RTL_SRWLOCK *v19; // rdi
  _QWORD *v20; // rax
  __int64 v21; // rcx
  _QWORD *v22; // rax
  __int64 v23; // r8
  HSTRING **v24; // rax
  _QWORD *v25; // rax
  __int64 v26; // rcx
  _QWORD *v27; // rax
  __int64 v28; // r8
  RTL_SRWLOCK **v29; // rax
  HSTRING *v30; // rdi
  HRESULT v31; // eax
  int v32; // eax
  __int64 v33; // rdx
  int v34; // [rsp+20h] [rbp-48h]
  struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *v35; // [rsp+30h] [rbp-38h] BYREF
  HSTRING *v36; // [rsp+38h] [rbp-30h] BYREF
  RTL_SRWLOCK *v37; // [rsp+40h] [rbp-28h] BYREF
  char v38[8]; // [rsp+48h] [rbp-20h] BYREF
  _BYTE v39[24]; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+40h]
  RTL_SRWLOCK *v41; // [rsp+B0h] [rbp+48h] BYREF
  struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *v42; // [rsp+B8h] [rbp+50h]
  HSTRING string; // [rsp+C0h] [rbp+58h] BYREF
  HSTRING *v44; // [rsp+C8h] [rbp+60h] BYREF

  v42 = a2;
  v41 = this;
  v2 = a2;
  v3 = (CShellExperienceDispatcher *)this;
  v4 = 0;
  v35 = 0;
  v5 = this + 38;
  AcquireSRWLockShared(this + 38);
  v37 = v5;
  v6 = (_QWORD *)std::vector<std::shared_ptr<HostedApplicationExperienceManager::HostedApplicationActivationContext>>::end(
                   (char *)v3 + 240,
                   &string);
  v8 = (_QWORD *)std::_Tree<std::_Tmap_traits<unsigned long,std::unique_ptr<SmartCookie>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::unique_ptr<SmartCookie>>>,0>>::end(
                   v7,
                   &v44,
                   *v6);
  std::find_if<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ShellExperienceView>>>,ShellExperienceViewFindByView>(
    &v36,
    *v8,
    v9,
    v2);
  v10 = (HSTRING **)std::vector<std::shared_ptr<HostedApplicationExperienceManager::HostedApplicationActivationContext>>::end(
                      (char *)v3 + 240,
                      &string);
  v11 = v36;
  if ( v36 == *v10 )
  {
    v12 = 0;
  }
  else
  {
    v12 = 1;
    v13 = v36 + 1;
    if ( !v36[1] )
    {
      string = 0;
      v14 = *v36;
      v15 = *(__int64 (__fastcall **)(HSTRING, HSTRING *))(*(_QWORD *)*v36 + 56LL);
      WindowsDeleteString(0);
      string = 0;
      v16 = v15(v14, &string);
      v17 = v16;
      if ( v16 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x300,
          (unsigned int)"onecoreuap\\shell\\onecore\\coreexperiencebrokercomponents\\shellexperiencedispatcher\\lib\\shel"
                        "lexperiencedispatcher.cpp",
          (const char *)(unsigned int)v16,
          v34);
        WindowsDeleteString(string);
        string = 0;
        if ( v5 )
          ReleaseSRWLockShared(v5);
        return v17;
      }
      v3 = (CShellExperienceDispatcher *)v41;
      v19 = v41 + 27;
      v20 = (_QWORD *)std::vector<std::shared_ptr<HostedApplicationExperienceManager::HostedApplicationActivationContext>>::end(
                        &v41[27],
                        &v41);
      v22 = (_QWORD *)std::_Tree<std::_Tmap_traits<unsigned long,std::unique_ptr<SmartCookie>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::unique_ptr<SmartCookie>>>,0>>::end(
                        v21,
                        v38,
                        *v20);
      std::find_if_std::_Vector_iterator_std::_Vector_val_std::_Simple_types_ShellExperienceListener_______lambda_d98ce7ba9d50f524bf721f54c5296cbc___(
        &v44,
        *v22,
        v23,
        &string);
      v24 = (HSTRING **)std::vector<std::shared_ptr<HostedApplicationExperienceManager::HostedApplicationActivationContext>>::end(
                          v19,
                          &v41);
      if ( v44 != *v24 )
      {
        v25 = (_QWORD *)std::vector<std::shared_ptr<HostedApplicationExperienceManager::HostedApplicationActivationContext>>::end(
                          (char *)v3 + 240,
                          v38);
        v27 = (_QWORD *)std::_Tree<std::_Tmap_traits<unsigned long,std::unique_ptr<SmartCookie>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::unique_ptr<SmartCookie>>>,0>>::end(
                          v26,
                          v39,
                          *v25);
        std::find_if_std::_Vector_iterator_std::_Vector_val_std::_Simple_types_ShellExperienceView_______lambda_0012612325cc5d9ae02f7451c73fbada___(
          &v41,
          *v27,
          v28,
          &v44);
        v29 = (RTL_SRWLOCK **)std::vector<std::shared_ptr<HostedApplicationExperienceManager::HostedApplicationActivationContext>>::end(
                                (char *)v3 + 240,
                                v39);
        if ( v41 == *v29 )
        {
          v30 = v44;
          WindowsDeleteString(*v13);
          *v13 = 0;
          v31 = WindowsDuplicateString(*v30, v11 + 1);
          v17 = v31;
          if ( v31 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x315,
              (unsigned int)"onecoreuap\\shell\\onecore\\coreexperiencebrokercomponents\\shellexperiencedispatcher\\lib\\"
                            "shellexperiencedispatcher.cpp",
              (const char *)(unsigned int)v31,
              v34);
            WindowsDeleteString(string);
            string = 0;
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v37);
LABEL_26:
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
            return v17;
          }
          Microsoft::WRL::ComPtr<CMarshaledInterface::CMarshalStream>::operator=(&v35, v11);
          *(_BYTE *)(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ViewSizePair>>>::operator->(&v36) + 16) = 1;
          v4 = v35;
        }
      }
      WindowsDeleteString(string);
      v2 = v42;
    }
  }
  if ( v5 )
    ReleaseSRWLockShared(v5);
  if ( !v12 )
  {
    v32 = CShellExperienceDispatcher::_OnViewCreated(v3, v2);
    v17 = v32;
    if ( v32 < 0 )
    {
      v33 = 803;
LABEL_25:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v33,
        (unsigned int)"onecoreuap\\shell\\onecore\\coreexperiencebrokercomponents\\shellexperiencedispatcher\\lib\\shelle"
                      "xperiencedispatcher.cpp",
        (const char *)(unsigned int)v32,
        v34);
      goto LABEL_26;
    }
  }
  if ( v4 )
  {
    v32 = CShellExperienceDispatcher::_NotifyListener((__int64)v3, (__int64)v4, 0, 0, 0);
    v17 = v32;
    if ( v32 < 0 )
    {
      v33 = 808;
      goto LABEL_25;
    }
    CShellExperienceDispatcher::_FlushQueuedEvents(v3, v4);
  }
  if ( v4 )
    (*(void (__fastcall **)(struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *))(*(_QWORD *)v4 + 16LL))(v4);
  return 0;
}

```

## disassembly

```asm
0x180041040  mov     [rsp-40h+arg_8], rdx
0x180041045  mov     [rsp-40h+arg_0], rcx
0x18004104a  push    rbp
0x18004104b  push    rbx
0x18004104c  push    rsi
0x18004104d  push    rdi
0x18004104e  push    r12
0x180041050  push    r13
0x180041052  push    r14
0x180041054  push    r15
0x180041056  mov     rbp, rsp
0x180041059  sub     rsp, 68h
0x18004105d  mov     rdi, rdx
0x180041060  mov     rsi, rcx
0x180041063  xor     r14d, r14d
0x180041066  mov     [rbp+var_38], r14
0x18004106a  lea     r15, [rcx+130h]
0x180041071  mov     rcx, r15; SRWLock
0x180041074  call    cs:__imp_AcquireSRWLockShared
0x18004107a  mov     [rbp+var_28], r15
0x18004107e  lea     rbx, [rsi+0F0h]
0x180041085  lea     rdx, [rbp+string]
0x180041089  mov     rcx, rbx
0x18004108c  call    ?end@?$vector@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@V?$allocator@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@@2@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@@std@@@std@@@2@XZ; std::vector<std::shared_ptr<HostedApplicationExperienceManager::HostedApplicationActivationContext>>::end(void)
0x180041091  mov     r8, [rax]
0x180041094  lea     rdx, [rbp+arg_18]
0x180041098  call    ?end@?$_Tree@V?$_Tmap_traits@KV?$unique_ptr@VSmartCookie@@U?$default_delete@VSmartCookie@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$unique_ptr@VSmartCookie@@U?$default_delete@VSmartCookie@@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$unique_ptr@VSmartCookie@@U?$default_delete@VSmartCookie@@@std@@@std@@@std@@@std@@@std@@@2@XZ; std::_Tree<std::_Tmap_traits<ulong,std::unique_ptr<SmartCookie>,std::less<ulong>,std::allocator<std::pair<ulong const,std::unique_ptr<SmartCookie>>>,0>>::end(void)
0x18004109d  mov     r9, rdi
0x1800410a0  mov     rdx, [rax]
0x1800410a3  lea     rcx, [rbp+var_30]
0x1800410a7  call    ??$find_if@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UShellExperienceView@@@std@@@std@@@std@@VShellExperienceViewFindByView@@@std@@YA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UShellExperienceView@@@std@@@std@@@0@V10@V10@VShellExperienceViewFindByView@@@Z; std::find_if<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ShellExperienceView>>>,ShellExperienceViewFindByView>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ShellExperienceView>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ShellExperienceView>>>,ShellExperienceViewFindByView)
0x1800410ac  lea     rdx, [rbp+string]
0x1800410b0  mov     rcx, rbx
0x1800410b3  call    ?end@?$vector@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@V?$allocator@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@@2@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@@std@@@std@@@2@XZ; std::vector<std::shared_ptr<HostedApplicationExperienceManager::HostedApplicationActivationContext>>::end(void)
0x1800410b8  mov     rbx, [rbp+var_30]
0x1800410bc  cmp     rbx, [rax]
0x1800410bf  jz      short loc_18004113B
0x1800410c1  mov     r13b, 1
0x1800410c4  lea     r12, [rbx+8]
0x1800410c8  cmp     [r12], r14
0x1800410cc  jnz     short loc_18004113E
0x1800410ce  mov     [rbp+string], r14
0x1800410d2  mov     rsi, [rbx]
0x1800410d5  mov     rax, [rsi]
0x1800410d8  mov     rdi, [rax+38h]
0x1800410dc  xor     ecx, ecx; string
0x1800410de  call    cs:__imp_WindowsDeleteString
0x1800410e4  mov     [rbp+string], r14
0x1800410e8  lea     rdx, [rbp+string]
0x1800410ec  mov     rcx, rsi
0x1800410ef  mov     rax, rdi
0x1800410f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800410f7  mov     edi, eax
0x1800410f9  test    eax, eax
0x1800410fb  jns     loc_180041188
0x180041101  mov     rcx, [rbp+40h]; this
0x180041105  mov     r9d, eax; char *
0x180041108  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\onecore\\coreexperie"...
0x18004110f  mov     edx, 300h; void *
0x180041114  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041119  nop
0x18004111a  mov     rcx, [rbp+string]; string
0x18004111e  call    cs:__imp_WindowsDeleteString
0x180041124  mov     [rbp+string], r14
0x180041128  test    r15, r15
0x18004112b  jz      short loc_180041137
0x18004112d  mov     rcx, r15; SRWLock
0x180041130  call    cs:__imp_ReleaseSRWLockShared
0x180041136  nop
0x180041137  mov     eax, edi
0x180041139  jmp     short loc_18004116C
0x18004113b  xor     r13b, r13b
0x18004113e  test    r15, r15
0x180041141  jnz     short loc_18004117D
0x180041143  test    r13b, r13b
0x180041146  jz      loc_1800412A7
0x18004114c  test    r14, r14
0x18004114f  jnz     loc_1800412C3
0x180041155  test    r14, r14
0x180041158  jz      short loc_18004116A
0x18004115a  mov     rax, [r14]
0x18004115d  mov     rcx, r14
0x180041160  mov     rax, [rax+10h]
0x180041164  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041169  nop
0x18004116a  xor     eax, eax
0x18004116c  add     rsp, 68h
0x180041170  pop     r15
0x180041172  pop     r14
0x180041174  pop     r13
0x180041176  pop     r12
0x180041178  pop     rdi
0x180041179  pop     rsi
0x18004117a  pop     rbx
0x18004117b  pop     rbp
0x18004117c  retn
0x18004117d  mov     rcx, r15; SRWLock
0x180041180  call    cs:__imp_ReleaseSRWLockShared
0x180041186  jmp     short loc_180041143
0x180041188  mov     rsi, [rbp+arg_0]
0x18004118c  lea     rdi, [rsi+0D8h]
0x180041193  lea     rdx, [rbp+arg_0]
0x180041197  mov     rcx, rdi
0x18004119a  call    ?end@?$vector@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@V?$allocator@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@@2@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@@std@@@std@@@2@XZ; std::vector<std::shared_ptr<HostedApplicationExperienceManager::HostedApplicationActivationContext>>::end(void)
0x18004119f  mov     r8, [rax]
0x1800411a2  lea     rdx, [rbp+var_20]
0x1800411a6  call    ?end@?$_Tree@V?$_Tmap_traits@KV?$unique_ptr@VSmartCookie@@U?$default_delete@VSmartCookie@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$unique_ptr@VSmartCookie@@U?$default_delete@VSmartCookie@@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$unique_ptr@VSmartCookie@@U?$default_delete@VSmartCookie@@@std@@@std@@@std@@@std@@@std@@@2@XZ; std::_Tree<std::_Tmap_traits<ulong,std::unique_ptr<SmartCookie>,std::less<ulong>,std::allocator<std::pair<ulong const,std::unique_ptr<SmartCookie>>>,0>>::end(void)
0x1800411ab  lea     r9, [rbp+string]
0x1800411af  mov     rdx, [rax]
0x1800411b2  lea     rcx, [rbp+arg_18]
0x1800411b6  call    std__find_if_std___Vector_iterator_std___Vector_val_std___Simple_types_ShellExperienceListener_______lambda_d98ce7ba9d50f524bf721f54c5296cbc___
0x1800411bb  lea     rdx, [rbp+arg_0]
0x1800411bf  mov     rcx, rdi
0x1800411c2  call    ?end@?$vector@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@V?$allocator@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@@2@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@@std@@@std@@@2@XZ; std::vector<std::shared_ptr<HostedApplicationExperienceManager::HostedApplicationActivationContext>>::end(void)
0x1800411c7  mov     rcx, [rax]
0x1800411ca  cmp     [rbp+arg_18], rcx
0x1800411ce  jz      short loc_180041214
0x1800411d0  lea     rdx, [rbp+var_20]
0x1800411d4  lea     rdi, [rsi+0F0h]
0x1800411db  mov     rcx, rdi
0x1800411de  call    ?end@?$vector@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@V?$allocator@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@@2@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@@std@@@std@@@2@XZ; std::vector<std::shared_ptr<HostedApplicationExperienceManager::HostedApplicationActivationContext>>::end(void)
0x1800411e3  mov     r8, [rax]
0x1800411e6  lea     rdx, [rbp+var_18]
0x1800411ea  call    ?end@?$_Tree@V?$_Tmap_traits@KV?$unique_ptr@VSmartCookie@@U?$default_delete@VSmartCookie@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$unique_ptr@VSmartCookie@@U?$default_delete@VSmartCookie@@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$unique_ptr@VSmartCookie@@U?$default_delete@VSmartCookie@@@std@@@std@@@std@@@std@@@std@@@2@XZ; std::_Tree<std::_Tmap_traits<ulong,std::unique_ptr<SmartCookie>,std::less<ulong>,std::allocator<std::pair<ulong const,std::unique_ptr<SmartCookie>>>,0>>::end(void)
0x1800411ef  lea     r9, [rbp+arg_18]
0x1800411f3  mov     rdx, [rax]
0x1800411f6  lea     rcx, [rbp+arg_0]
0x1800411fa  call    std__find_if_std___Vector_iterator_std___Vector_val_std___Simple_types_ShellExperienceView_______lambda_0012612325cc5d9ae02f7451c73fbada___
0x1800411ff  lea     rdx, [rbp+var_18]
0x180041203  mov     rcx, rdi
0x180041206  call    ?end@?$vector@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@V?$allocator@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@@2@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@@std@@@std@@@2@XZ; std::vector<std::shared_ptr<HostedApplicationExperienceManager::HostedApplicationActivationContext>>::end(void)
0x18004120b  mov     rcx, [rax]
0x18004120e  cmp     [rbp+arg_0], rcx
0x180041212  jz      short loc_180041227
0x180041214  mov     rcx, [rbp+string]; string
0x180041218  call    cs:__imp_WindowsDeleteString
0x18004121e  mov     rdi, [rbp+arg_8]
0x180041222  jmp     loc_18004113E
0x180041227  mov     rdi, [rbp+arg_18]
0x18004122b  mov     rcx, [r12]; string
0x18004122f  call    cs:__imp_WindowsDeleteString
0x180041235  mov     qword ptr [r12], 0
0x18004123d  mov     rdx, r12; newString
0x180041240  mov     rcx, [rdi]; string
0x180041243  call    cs:__imp_WindowsDuplicateString
0x180041249  mov     edi, eax
0x18004124b  test    eax, eax
0x18004124d  jns     short loc_180041285
0x18004124f  mov     rcx, [rbp+40h]; this
0x180041253  mov     r9d, eax; char *
0x180041256  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\onecore\\coreexperie"...
0x18004125d  mov     edx, 315h; void *
0x180041262  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041267  nop
0x180041268  mov     rcx, [rbp+string]; string
0x18004126c  call    cs:__imp_WindowsDeleteString
0x180041272  mov     [rbp+string], 0
0x18004127a  lea     rcx, [rbp+var_28]
0x18004127e  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x180041283  jmp     short loc_1800412FC
0x180041285  mov     rdx, rbx
0x180041288  lea     rcx, [rbp+var_38]
0x18004128c  call    ??4?$ComPtr@VCMarshalStream@CMarshaledInterface@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<CMarshaledInterface::CMarshalStream>::operator=(Microsoft::WRL::ComPtr<CMarshaledInterface::CMarshalStream> const &)
0x180041291  lea     rcx, [rbp+var_30]
0x180041295  call    ??C?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UViewSizePair@@@std@@@std@@@std@@QEBAPEAUViewSizePair@@XZ; std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ViewSizePair>>>::operator->(void)
0x18004129a  mov     [rax+10h], r13b
0x18004129e  mov     r14, [rbp+var_38]
0x1800412a2  jmp     loc_180041214
0x1800412a7  mov     rdx, rdi; struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *
0x1800412aa  mov     rcx, rsi; this
0x1800412ad  call    ?_OnViewCreated@CShellExperienceDispatcher@@AEAAJPEAUIViewWrapper@ViewManagerInterop@Shell@Internal@Windows@@@Z; CShellExperienceDispatcher::_OnViewCreated(Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *)
0x1800412b2  mov     edi, eax
0x1800412b4  test    eax, eax
0x1800412b6  jns     loc_18004114C
0x1800412bc  mov     edx, 323h
0x1800412c1  jmp     short loc_1800412E8
0x1800412c3  mov     qword ptr [rsp+68h+var_48], 0; int
0x1800412cc  xor     r9d, r9d
0x1800412cf  xor     r8d, r8d
0x1800412d2  mov     rdx, r14
0x1800412d5  mov     rcx, rsi
0x1800412d8  call    ?_NotifyListener@CShellExperienceDispatcher@@AEAAJPEAUIViewWrapper@ViewManagerInterop@Shell@Internal@Windows@@W4ShellExperienceViewState@Experience@456@PEAUHSTRING__@@PEAUIPropertySet@Collections@Foundation@6@@Z; CShellExperienceDispatcher::_NotifyListener(Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *,Windows::Internal::Shell::Experience::ShellExperienceViewState,HSTRING__ *,Windows::Foundation::Collections::IPropertySet *)
0x1800412dd  mov     edi, eax
0x1800412df  test    eax, eax
0x1800412e1  jns     short loc_18004130A
0x1800412e3  mov     edx, 328h; void *
0x1800412e8  mov     r9d, eax; char *
0x1800412eb  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\onecore\\coreexperie"...
0x1800412f2  mov     rcx, [rbp+40h]; this
0x1800412f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800412fb  nop
0x1800412fc  lea     rcx, [rbp+var_38]
0x180041300  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180041305  jmp     loc_180041137
0x18004130a  mov     rdx, r14; struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *
0x18004130d  mov     rcx, rsi; this
0x180041310  call    ?_FlushQueuedEvents@CShellExperienceDispatcher@@AEAAJPEAUIViewWrapper@ViewManagerInterop@Shell@Internal@Windows@@@Z; CShellExperienceDispatcher::_FlushQueuedEvents(Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *)
0x180041315  jmp     loc_180041155
```
