# DirectLaunch::DirectLaunchManager::OnDefaultAssociationChanged(void)

- ea: `0x1800414dc`
- end: `0x1800416db`
- name: `?OnDefaultAssociationChanged@DirectLaunchManager@DirectLaunch@@AEAAXXZ`
- size: `511`
- prototype: `void __fastcall(DirectLaunch::DirectLaunchManager *__hidden this)`
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x1800434b0`
- `0x180043520`

## callees

- `0x180019534`
- `0x180020f9c`
- `0x180025404`
- `0x18002b1b0`
- `0x1800336b8`
- `0x18003b0e0`
- `0x18003b1a8`
- `0x18003ba88`
- `0x18003d54c`
- `0x18003e878`
- `0x18003f180`
- `0x180041064`
- `0x1800414dc`
- `0x180042004`
- `0x180043e70`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18004159d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18004159d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180041585`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180041585`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall DirectLaunch::DirectLaunchManager::OnDefaultAssociationChanged(DirectLaunch::DirectLaunchManager *this)
{
  __int64 v2; // rdx
  __int64 v3; // rbx
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // r9
  char IsSchemeRegistrationAllowed; // r14
  char *v8; // rax
  _QWORD *v9; // rcx
  _QWORD *v10; // rax
  _QWORD *v11; // rbx
  _QWORD *v12; // rsi
  char v13; // [rsp+20h] [rbp-49h]
  char *v14; // [rsp+28h] [rbp-41h] BYREF
  __int64 v15; // [rsp+30h] [rbp-39h] BYREF
  _QWORD *v16; // [rsp+38h] [rbp-31h] BYREF
  __int128 v17; // [rsp+40h] [rbp-29h] BYREF
  __int128 v18; // [rsp+50h] [rbp-19h] BYREF
  DWORD dwProcessId; // [rsp+60h] [rbp-9h] BYREF
  __int128 v20; // [rsp+68h] [rbp-1h] BYREF
  __int64 v21; // [rsp+78h] [rbp+Fh]
  _QWORD v22[3]; // [rsp+80h] [rbp+17h] BYREF
  unsigned __int64 v23; // [rsp+98h] [rbp+2Fh]

  v18 = 0;
  std::unique_lock<std::shared_mutex>::unique_lock<std::shared_mutex>(&v18, (char *)this + 16);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_61155835>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_61155835>::GetImpl'::`2'::impl) )
  {
    dwProcessId = *((_DWORD *)this + 8);
    DirectLaunch::details::DirectLaunchTelemetry::DefaultAssociationChangeReceived<unsigned int>(&dwProcessId);
  }
  v20 = 0;
  v21 = 0;
  v3 = **((_QWORD **)this + 3);
  v15 = v3;
  while ( v3 != *((_QWORD *)this + 3) )
  {
    std::wstring::wstring(v22, v3 + 32);
    if ( !*(_DWORD *)(v3 + 64) )
    {
      dwProcessId = 0;
      if ( !GetWindowThreadProcessId(*(HWND *)(v3 + 72), &dwProcessId) )
        goto LABEL_28;
      IsSchemeRegistrationAllowed = 0;
      v8 = (char *)OpenProcess(0x1000u, 0, dwProcessId);
      v14 = v8;
      if ( (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        v9 = v22;
        if ( v23 > 7 )
          v9 = (_QWORD *)v22[0];
        *(_QWORD *)&v17 = v9;
        *((_QWORD *)&v17 + 1) = v22[2];
        IsSchemeRegistrationAllowed = DirectLaunch::details::IsSchemeRegistrationAllowed(v8, &v17, *(HWND *)(v3 + 72));
      }
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v14);
      if ( !IsSchemeRegistrationAllowed )
      {
LABEL_28:
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_61155835>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_61155835>::GetImpl'::`2'::impl) )
        {
          LODWORD(v14) = *(_DWORD *)(v3 + 72);
          v10 = v22;
          if ( v23 > 7 )
            v10 = (_QWORD *)v22[0];
          v16 = v10;
          DirectLaunch::details::DirectLaunchTelemetry::HandlerRemovedDueToAssociationChange<unsigned short const *,unsigned long>(
            &v16,
            &v14);
        }
        v4 = *((_QWORD *)&v20 + 1);
        if ( *((_QWORD *)&v20 + 1) == v21 )
        {
          std::vector<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,DirectLaunch::DirectLaunchManager::HandlerEntry>>>>>::_Emplace_reallocate<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,DirectLaunch::DirectLaunchManager::HandlerEntry>>>> const &>(
            &v20,
            *((_QWORD *)&v20 + 1),
            &v15);
        }
        else
        {
          **((_QWORD **)&v20 + 1) = v3;
          *((_QWORD *)&v20 + 1) += 8LL;
        }
      }
    }
    std::wstring::_Tidy_deallocate(v22, v4, v5, v6);
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,DirectLaunch::DirectLaunchManager::HandlerEntry>>>,std::_Iterator_base0>::operator++(&v15);
    v3 = v15;
  }
  v12 = (_QWORD *)*((_QWORD *)&v20 + 1);
  v11 = (_QWORD *)v20;
  if ( (_QWORD)v20 != *((_QWORD *)&v20 + 1) )
  {
    do
    {
      LOBYTE(v2) = v13;
      DirectLaunch::DirectLaunchManager::RemoveHandlerEntry(this, v2, *v11++);
    }
    while ( v11 != v12 );
    v11 = (_QWORD *)v20;
  }
  if ( v11 )
  {
    std::_Deallocate<16>(v11, (v21 - (_QWORD)v11) & 0xFFFFFFFFFFFFFFF8uLL);
    v20 = 0;
    v21 = 0;
  }
  std::unique_lock<std::shared_mutex>::~unique_lock<std::shared_mutex>(&v18);
}

```

## disassembly

```asm
0x1800414dc  mov     [rsp-8+arg_8], rbx
0x1800414e1  mov     [rsp-8+arg_10], rsi
0x1800414e6  push    rbp
0x1800414e7  push    rdi
0x1800414e8  push    r14
0x1800414ea  lea     rbp, [rsp-47h]
0x1800414ef  sub     rsp, 0B0h
0x1800414f6  mov     rax, cs:__security_cookie
0x1800414fd  xor     rax, rsp
0x180041500  mov     [rbp+57h+var_20], rax
0x180041504  mov     rdi, rcx
0x180041507  xorps   xmm0, xmm0
0x18004150a  movups  [rbp+57h+var_70], xmm0
0x18004150e  lea     rdx, [rcx+10h]
0x180041512  lea     rcx, [rbp+57h+var_70]
0x180041516  call    ??0?$unique_lock@Vshared_mutex@std@@@std@@QEAA@AEAVshared_mutex@1@@Z; std::unique_lock<std::shared_mutex>::unique_lock<std::shared_mutex>(std::shared_mutex &)
0x18004151b  nop
0x18004151c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_61155835@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_61155835@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_61155835> `wil::Feature<__WilFeatureTraits_Feature_61155835>::GetImpl(void)'::`2'::impl
0x180041523  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_61155835@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_61155835>::__private_IsEnabled(void)
0x180041528  test    al, al
0x18004152a  jz      short loc_18004153B
0x18004152c  mov     eax, [rdi+20h]
0x18004152f  mov     [rbp+57h+dwProcessId], eax
0x180041532  lea     rcx, [rbp+57h+dwProcessId]
0x180041536  call    ??$DefaultAssociationChangeReceived@I@DirectLaunchTelemetry@details@DirectLaunch@@SAX$$QEAI@Z; DirectLaunch::details::DirectLaunchTelemetry::DefaultAssociationChangeReceived<uint>(uint &&)
0x18004153b  xor     eax, eax
0x18004153d  xorps   xmm1, xmm1
0x180041540  movdqu  [rbp+57h+var_58], xmm1
0x180041545  mov     [rbp+57h+var_48], rax
0x180041549  mov     rbx, [rdi+18h]
0x18004154d  mov     rbx, [rbx]
0x180041550  mov     [rbp+57h+var_90], rbx
0x180041554  cmp     rbx, [rdi+18h]
0x180041558  jz      loc_18004165E
0x18004155e  lea     rdx, [rbx+20h]
0x180041562  lea     rcx, [rbp+57h+var_40]
0x180041566  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004156b  nop
0x18004156c  cmp     dword ptr [rbx+40h], 0
0x180041570  jnz     loc_180041643
0x180041576  mov     [rbp+57h+dwProcessId], 0
0x18004157d  lea     rdx, [rbp+57h+dwProcessId]; lpdwProcessId
0x180041581  mov     rcx, [rbx+48h]; hWnd
0x180041585  call    cs:__imp_GetWindowThreadProcessId
0x18004158b  test    eax, eax
0x18004158d  jz      short loc_1800415EC
0x18004158f  xor     r14b, r14b
0x180041592  mov     r8d, [rbp+57h+dwProcessId]; dwProcessId
0x180041596  xor     edx, edx; bInheritHandle
0x180041598  mov     ecx, 1000h; dwDesiredAccess
0x18004159d  call    cs:__imp_OpenProcess
0x1800415a3  mov     [rbp+57h+var_98], rax
0x1800415a7  lea     rcx, [rax-1]
0x1800415ab  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800415af  ja      short loc_1800415DE
0x1800415b1  mov     rdx, [rbp+57h+var_30]
0x1800415b5  lea     rcx, [rbp+57h+var_40]
0x1800415b9  cmp     [rbp+57h+var_28], 7
0x1800415be  cmova   rcx, [rbp+57h+var_40]
0x1800415c3  mov     [rbp+57h+var_80], rcx
0x1800415c7  mov     [rbp+57h+var_78], rdx
0x1800415cb  mov     r8, [rbx+48h]
0x1800415cf  lea     rdx, [rbp+57h+var_80]
0x1800415d3  mov     rcx, rax; hProcess
0x1800415d6  call    ?IsSchemeRegistrationAllowed@details@DirectLaunch@@YA_NPEAXV?$basic_zstring_view@G@wil@@PEAUHWND__@@@Z; DirectLaunch::details::IsSchemeRegistrationAllowed(void *,wil::basic_zstring_view<ushort>,HWND__ *)
0x1800415db  mov     r14b, al
0x1800415de  lea     rcx, [rbp+57h+var_98]
0x1800415e2  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800415e7  test    r14b, r14b
0x1800415ea  jnz     short loc_180041643
0x1800415ec  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_61155835@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_61155835@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_61155835> `wil::Feature<__WilFeatureTraits_Feature_61155835>::GetImpl(void)'::`2'::impl
0x1800415f3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_61155835@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_61155835>::__private_IsEnabled(void)
0x1800415f8  test    al, al
0x1800415fa  jz      short loc_180041621
0x1800415fc  mov     eax, [rbx+48h]
0x1800415ff  mov     dword ptr [rbp+57h+var_98], eax
0x180041602  lea     rax, [rbp+57h+var_40]
0x180041606  cmp     [rbp+57h+var_28], 7
0x18004160b  cmova   rax, [rbp+57h+var_40]
0x180041610  mov     [rbp+57h+var_88], rax
0x180041614  lea     rdx, [rbp+57h+var_98]
0x180041618  lea     rcx, [rbp+57h+var_88]
0x18004161c  call    ??$HandlerRemovedDueToAssociationChange@PEBGK@DirectLaunchTelemetry@details@DirectLaunch@@SAX$$QEAPEBG$$QEAK@Z; DirectLaunch::details::DirectLaunchTelemetry::HandlerRemovedDueToAssociationChange<ushort const *,ulong>(ushort const * &&,ulong &&)
0x180041621  mov     rdx, qword ptr [rbp+57h+var_58+8]
0x180041625  cmp     rdx, [rbp+57h+var_48]
0x180041629  jz      short loc_180041635
0x18004162b  mov     [rdx], rbx
0x18004162e  add     qword ptr [rbp+57h+var_58+8], 8
0x180041633  jmp     short loc_180041643
0x180041635  lea     r8, [rbp+57h+var_90]
0x180041639  lea     rcx, [rbp+57h+var_58]
0x18004163d  call    ??$_Emplace_reallocate@AEBV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UHandlerEntry@DirectLaunchManager@DirectLaunch@@@std@@@std@@@std@@@std@@@?$vector@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UHandlerEntry@DirectLaunchManager@DirectLaunch@@@std@@@std@@@std@@@std@@V?$allocator@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UHandlerEntry@DirectLaunchManager@DirectLaunch@@@std@@@std@@@std@@@std@@@2@@std@@AEAAPEAV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UHandlerEntry@DirectLaunchManager@DirectLaunch@@@std@@@std@@@std@@@1@QEAV21@AEBV21@@Z; std::vector<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,DirectLaunch::DirectLaunchManager::HandlerEntry>>>>>::_Emplace_reallocate<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,DirectLaunch::DirectLaunchManager::HandlerEntry>>>> const &>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,DirectLaunch::DirectLaunchManager::HandlerEntry>>>> * const,std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,DirectLaunch::DirectLaunchManager::HandlerEntry>>>> const &)
0x180041642  nop
0x180041643  lea     rcx, [rbp+57h+var_40]
0x180041647  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004164c  lea     rcx, [rbp+57h+var_90]
0x180041650  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UHandlerEntry@DirectLaunchManager@DirectLaunch@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,DirectLaunch::DirectLaunchManager::HandlerEntry>>>,std::_Iterator_base0>::operator++(void)
0x180041655  mov     rbx, [rbp+57h+var_90]
0x180041659  jmp     loc_180041554
0x18004165e  mov     rbx, qword ptr [rbp+57h+var_58]
0x180041662  mov     rsi, qword ptr [rbp+57h+var_58+8]
0x180041666  cmp     rbx, rsi
0x180041669  jz      short loc_180041686
0x18004166b  mov     r8, [rbx]
0x18004166e  mov     dl, [rbp+57h+var_A0]
0x180041671  mov     rcx, rdi
0x180041674  call    ?RemoveHandlerEntry@DirectLaunchManager@DirectLaunch@@AEAAXUwrite_lock_required@wil@@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UHandlerEntry@DirectLaunchManager@DirectLaunch@@@std@@@std@@@std@@@std@@@Z; DirectLaunch::DirectLaunchManager::RemoveHandlerEntry(wil::write_lock_required,std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,DirectLaunch::DirectLaunchManager::HandlerEntry>>>>)
0x180041679  add     rbx, 8
0x18004167d  cmp     rbx, rsi
0x180041680  jnz     short loc_18004166B
0x180041682  mov     rbx, qword ptr [rbp+57h+var_58]
0x180041686  test    rbx, rbx
0x180041689  jz      short loc_1800416AE
0x18004168b  mov     rdx, [rbp+57h+var_48]
0x18004168f  sub     rdx, rbx
0x180041692  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180041696  mov     rcx, rbx
0x180041699  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18004169e  xorps   xmm0, xmm0
0x1800416a1  movdqu  [rbp+57h+var_58], xmm0
0x1800416a6  mov     [rbp+57h+var_48], 0
0x1800416ae  lea     rcx, [rbp+57h+var_70]
0x1800416b2  call    ??1?$unique_lock@Vshared_mutex@std@@@std@@QEAA@XZ; std::unique_lock<std::shared_mutex>::~unique_lock<std::shared_mutex>(void)
0x1800416b7  mov     rcx, [rbp+57h+var_20]
0x1800416bb  xor     rcx, rsp; StackCookie
0x1800416be  call    __security_check_cookie
0x1800416c3  lea     r11, [rsp+0C0h+var_10]
0x1800416cb  mov     rbx, [r11+28h]
0x1800416cf  mov     rsi, [r11+30h]
0x1800416d3  mov     rsp, r11
0x1800416d6  pop     r14
0x1800416d8  pop     rdi
0x1800416d9  pop     rbp
0x1800416da  retn
```
