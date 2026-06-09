# Windows::System::Internal::Implementation::UserProfileManager::CleanupStaleProfiles(uchar)

- ea: `0x1800608d0`
- end: `0x180060d92`
- name: `?CleanupStaleProfiles@UserProfileManager@Implementation@Internal@System@Windows@@UEAAJE@Z`
- size: `1218`
- prototype: `__int64 __fastcall(Windows::System::Internal::Implementation::UserProfileManager *this, char)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000acdc`
- `0x18000ce48`
- `0x180024828`
- `0x180025cd4`
- `0x1800346b8`
- `0x180037e98`
- `0x18003e290`
- `0x1800608d0`
- `0x180060d98`
- `0x1800610f8`
- `0x1800616c0`
- `0x1800c322c`
- `0x1800c35e8`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180060912`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006096c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180060a70`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180060912`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006096c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180060a70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180060c94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180060c94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180060c49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180060cd6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180060c49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180060cd6`

## string_xrefs

- `0x1800609e0`: `onecore\ds\security\umstartup\usermgr\lib\knownusermanager.cpp`
- `0x180060b13`: `onecore\ds\security\umstartup\usermgr\lib\knownusermanager.cpp`
- `0x180060b4c`: `onecore\ds\security\umstartup\usermgr\lib\knownusermanager.cpp`
- `0x180060b8d`: `onecore\ds\security\umstartup\usermgr\lib\knownusermanager.cpp`
- `0x180060c27`: `onecore\ds\security\umstartup\usermgr\lib\knownusermanager.cpp`
- `0x180060c79`: `onecore\ds\security\umstartup\usermgr\lib\knownusermanager.cpp`

## pseudocode

```c
__int64 __fastcall Windows::System::Internal::Implementation::UserProfileManager::CleanupStaleProfiles(
        Windows::System::Internal::Implementation::UserProfileManager *this,
        char a2)
{
  char v2; // r14
  struct _RTL_CRITICAL_SECTION *v4; // r12
  __int64 *v5; // rsi
  _DWORD *j; // rbx
  __int64 *v7; // rdi
  __int64 v8; // rbx
  unsigned int *m; // rbx
  const char *v10; // r9
  __int64 result; // rax
  int v12; // eax
  __int64 k; // rax
  _QWORD *v14; // rsi
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  __int64 v19; // r14
  __int64 (__fastcall *v20)(__int64, HSTRING *); // rsi
  int v21; // eax
  _DWORD *v22; // rdi
  __int64 i; // rax
  __int64 v24; // rbx
  int v25[2]; // [rsp+20h] [rbp-98h] BYREF
  HSTRING string; // [rsp+28h] [rbp-90h] BYREF
  __int64 v27; // [rsp+30h] [rbp-88h] BYREF
  __int64 v28; // [rsp+38h] [rbp-80h] BYREF
  __int128 v29; // [rsp+40h] [rbp-78h] BYREF
  _DWORD *v30; // [rsp+50h] [rbp-68h]
  __int128 v31; // [rsp+58h] [rbp-60h] BYREF
  __int64 v32; // [rsp+68h] [rbp-50h]
  _QWORD v33[9]; // [rsp+70h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]
  struct _RTL_CRITICAL_SECTION *v35; // [rsp+C0h] [rbp+8h] BYREF
  char v36; // [rsp+C8h] [rbp+10h]
  char *v37; // [rsp+D0h] [rbp+18h] BYREF
  struct _RTL_CRITICAL_SECTION *v38; // [rsp+D8h] [rbp+20h] BYREF

  v36 = a2;
  v2 = a2;
  v31 = 0;
  v32 = 0;
  v29 = 0;
  v30 = 0;
  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 64);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  v35 = v4;
  try
  {
    std::vector<unsigned int>::resize();
    v5 = (__int64 *)*((_QWORD *)this + 13);
    v24 = *v5;
    v22 = (_DWORD *)*((_QWORD *)&v29 + 1);
    while ( (__int64 *)v24 != v5 )
    {
      if ( v22 == v30 )
      {
        std::vector<unsigned int>::_Reserve(&v29, 1);
        v22 = (_DWORD *)*((_QWORD *)&v29 + 1);
      }
      *v22++ = *(_DWORD *)(v24 + 32);
      *((_QWORD *)&v29 + 1) = v22;
      if ( !*(_BYTE *)(v24 + 25) )
      {
        if ( *(_BYTE *)(*(_QWORD *)(v24 + 16) + 25LL) )
        {
          for ( i = *(_QWORD *)(v24 + 8); !*(_BYTE *)(i + 25) && v24 == *(_QWORD *)(i + 16); i = *(_QWORD *)(i + 8) )
            v24 = i;
        }
        else
        {
          i = std::_Tree_val<std::_Tree_simple_types<std::pair<HSTRING__ * const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>>::_Min();
        }
        v24 = i;
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v35);
    for ( j = (_DWORD *)v29; ; ++j )
    {
      if ( j == v22 )
      {
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
        v37 = (char *)this + 136;
        v7 = (__int64 *)*((_QWORD *)this + 22);
        v8 = *v7;
        while ( (__int64 *)v8 != v7 )
        {
          LODWORD(v35) = 0;
          (*(void (__fastcall **)(_QWORD, struct _RTL_CRITICAL_SECTION **))(**(_QWORD **)(v8 + 40) + 48LL))(
            *(_QWORD *)(v8 + 40),
            &v35);
          std::vector<unsigned int>::push_back(&v31, &v35);
          if ( !*(_BYTE *)(v8 + 25) )
          {
            if ( *(_BYTE *)(*(_QWORD *)(v8 + 16) + 25LL) )
            {
              for ( k = *(_QWORD *)(v8 + 8); !*(_BYTE *)(k + 25) && v8 == *(_QWORD *)(k + 16); k = *(_QWORD *)(k + 8) )
                v8 = k;
            }
            else
            {
              k = std::_Tree_val<std::_Tree_simple_types<std::pair<HSTRING__ * const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>>::_Min();
            }
            v8 = k;
          }
        }
        wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v37);
        for ( m = (unsigned int *)v31; m != *((unsigned int **)&v31 + 1); ++m )
        {
          v12 = (*(__int64 (__fastcall **)(Windows::System::Internal::Implementation::UserProfileManager *, _QWORD))(*(_QWORD *)this + 88LL))(
                  this,
                  *m);
          if ( v12 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x1E1,
              (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\knownusermanager.cpp",
              (const char *)(unsigned int)v12,
              v25[0]);
        }
        std::vector<unsigned short>::_Tidy(&v29);
        std::vector<unsigned short>::_Tidy(&v31);
        return 0;
      }
      *(_QWORD *)v25 = 0;
      EnterCriticalSection(v4);
      v38 = v4;
      std::_Tree<std::_Tmap_traits<unsigned int,Windows::System::Internal::Implementation::SignOutProgress *,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,Windows::System::Internal::Implementation::SignOutProgress *>>,0>>::find(
        (char *)this + 104,
        v33,
        j);
      if ( v33[0] == *((_QWORD *)this + 13) )
        break;
      v14 = (_QWORD *)(v33[0] + 40LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v25);
      Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(v14);
      *(_QWORD *)v25 = *v14;
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v38);
      v27 = 0;
      v28 = 0;
      LOBYTE(v35) = 0;
      v15 = Microsoft::WRL::ComPtr<Windows::System::Internal::IUserProfile>::As<Windows::System::Internal::Implementation::IUserProfileInternal>(
              v25,
              &v27);
      if ( v15 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1B8,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\knownusermanager.cpp",
          (const char *)(unsigned int)v15,
          v25[0]);
      v16 = (*(__int64 (__fastcall **)(__int64, struct _RTL_CRITICAL_SECTION **))(*(_QWORD *)v27 + 64LL))(v27, &v35);
      if ( v16 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1B9,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\knownusermanager.cpp",
          (const char *)(unsigned int)v16,
          v25[0]);
      LOBYTE(v37) = 0;
      v17 = (*(__int64 (__fastcall **)(__int64, char **))(*(_QWORD *)v27 + 72LL))(v27, &v37);
      if ( v17 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1BB,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\knownusermanager.cpp",
          (const char *)(unsigned int)v17,
          v25[0]);
      if ( (_BYTE)v35 && v2 || (_BYTE)v37 )
      {
        LODWORD(v38) = 0;
        (*(void (__fastcall **)(_QWORD, struct _RTL_CRITICAL_SECTION **))(**(_QWORD **)v25 + 48LL))(
          *(_QWORD *)v25,
          &v38);
        std::vector<unsigned int>::push_back(&v31, &v38);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
        goto LABEL_23;
      }
      string = 0;
      v18 = Microsoft::WRL::ComPtr<Windows::System::Internal::IUserProfile>::As<Windows::System::Internal::IUserProfile2>(
              v25,
              &v28);
      if ( v18 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1CA,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\knownusermanager.cpp",
          (const char *)(unsigned int)v18,
          v25[0]);
      v19 = v28;
      v20 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v28 + 56LL);
      WindowsDeleteString(string);
      string = 0;
      v21 = v20(v19, &string);
      if ( v21 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1CB,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\knownusermanager.cpp",
          (const char *)(unsigned int)v21,
          v25[0]);
      if ( !string || !WindowsGetStringLen(string) )
      {
        LODWORD(v38) = 0;
        (*(void (__fastcall **)(_QWORD, struct _RTL_CRITICAL_SECTION **))(**(_QWORD **)v25 + 48LL))(
          *(_QWORD *)v25,
          &v38);
        std::vector<unsigned int>::push_back(&v31, &v38);
      }
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v25);
      v2 = v36;
LABEL_42:
      ;
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v38);
LABEL_23:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v25);
    goto LABEL_42;
  }
  catch ( ... )
  {
    LODWORD(v35) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x1E6,
                     (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\knownusermanager.cpp",
                     v10);
    return (unsigned int)v35;
  }
  return result;
}

```

## disassembly

```asm
0x1800608d0  mov     rax, rsp
0x1800608d3  mov     [rax+10h], dl
0x1800608d6  push    rbx
0x1800608d7  push    rsi
0x1800608d8  push    rdi
0x1800608d9  push    r12
0x1800608db  push    r13
0x1800608dd  push    r14
0x1800608df  push    r15
0x1800608e1  sub     rsp, 80h
0x1800608e8  mov     r14b, dl
0x1800608eb  mov     r15, rcx
0x1800608ee  xorps   xmm0, xmm0
0x1800608f1  movdqu  xmmword ptr [rax-60h], xmm0
0x1800608f6  mov     qword ptr [rax-50h], 0
0x1800608fe  movdqu  xmmword ptr [rax-78h], xmm0
0x180060903  mov     qword ptr [rax-68h], 0
0x18006090b  lea     r12, [rcx+40h]
0x18006090f  mov     rcx, r12; lpCriticalSection
0x180060912  call    cs:__imp_EnterCriticalSection
0x180060918  mov     [rsp+0B8h+arg_0], r12
0x180060920  mov     rdx, [r15+70h]
0x180060924  lea     rcx, [rsp+0B8h+var_78]
0x180060929  call    ?resize@?$vector@IV?$allocator@I@std@@@std@@QEAAX_K@Z; std::vector<uint>::resize(unsigned __int64)
0x18006092e  lea     r13, [r15+68h]
0x180060932  mov     rsi, [r13+0]
0x180060936  mov     rbx, [rsi]
0x180060939  mov     rdi, [rsp+0B8h+var_70]
0x18006093e  cmp     rbx, rsi
0x180060941  jnz     loc_180060D12
0x180060947  lea     rcx, [rsp+0B8h+arg_0]
0x18006094f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180060954  mov     rbx, [rsp+0B8h+var_78]
0x180060959  cmp     rbx, rdi
0x18006095c  jnz     loc_180060A64
0x180060962  lea     rbx, [r15+88h]
0x180060969  mov     rcx, rbx; lpCriticalSection
0x18006096c  call    cs:__imp_EnterCriticalSection
0x180060972  mov     [rsp+0B8h+arg_10], rbx
0x18006097a  mov     rdi, [r15+0B0h]
0x180060981  mov     rbx, [rdi]
0x180060984  xor     esi, esi
0x180060986  cmp     rbx, rdi
0x180060989  jnz     short loc_1800609F7
0x18006098b  lea     rcx, [rsp+0B8h+arg_10]
0x180060993  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180060998  mov     rbx, [rsp+0B8h+var_60]
0x18006099d  cmp     rbx, [rsp+0B8h+var_58]
0x1800609a2  jnz     short loc_1800609C0
0x1800609a4  lea     rcx, [rsp+0B8h+var_78]
0x1800609a9  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@IEAAXXZ; std::vector<ushort>::_Tidy(void)
0x1800609ae  nop
0x1800609af  lea     rcx, [rsp+0B8h+var_60]
0x1800609b4  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@IEAAXXZ; std::vector<ushort>::_Tidy(void)
0x1800609b9  xor     eax, eax
0x1800609bb  jmp     loc_180060D7E
0x1800609c0  mov     rax, [r15]
0x1800609c3  mov     edx, [rbx]
0x1800609c5  mov     rcx, r15
0x1800609c8  mov     rax, [rax+58h]
0x1800609cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800609d1  mov     rcx, [rsp+0B8h]; this
0x1800609d9  test    eax, eax
0x1800609db  jns     short loc_1800609F1
0x1800609dd  mov     r9d, eax; char *
0x1800609e0  lea     r8, aOnecoreDsSecur_60; "onecore\\ds\\security\\umstartup\\userm"...
0x1800609e7  mov     edx, 1E1h; void *
0x1800609ec  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800609f1  add     rbx, 4
0x1800609f5  jmp     short loc_18006099D
0x1800609f7  mov     dword ptr [rsp+0B8h+arg_0], esi
0x1800609fe  mov     rcx, [rbx+28h]
0x180060a02  mov     rax, [rcx]
0x180060a05  lea     rdx, [rsp+0B8h+arg_0]
0x180060a0d  mov     rax, [rax+30h]
0x180060a11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060a16  lea     rdx, [rsp+0B8h+arg_0]
0x180060a1e  lea     rcx, [rsp+0B8h+var_60]
0x180060a23  call    ?push_back@?$vector@IV?$allocator@I@std@@@std@@QEAAXAEBI@Z; std::vector<uint>::push_back(uint const &)
0x180060a28  cmp     [rbx+19h], sil
0x180060a2c  jnz     loc_180060986
0x180060a32  mov     rcx, [rbx+10h]
0x180060a36  cmp     [rcx+19h], sil
0x180060a3a  jnz     short loc_180060A43
0x180060a3c  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAUHSTRING__@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@QEAUHSTRING__@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<HSTRING__ * const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>>::_Min(std::_Tree_node<std::pair<HSTRING__ * const,Microsoft::WRL::ComPtr<Windows::System::IUser>>,void *> *)
0x180060a41  jmp     short loc_180060A5C
0x180060a43  mov     rax, [rbx+8]
0x180060a47  jmp     short loc_180060A56
0x180060a49  cmp     rbx, [rax+10h]
0x180060a4d  jnz     short loc_180060A5C
0x180060a4f  mov     rbx, rax
0x180060a52  mov     rax, [rax+8]
0x180060a56  cmp     [rax+19h], sil
0x180060a5a  jz      short loc_180060A49
0x180060a5c  mov     rbx, rax
0x180060a5f  jmp     loc_180060986
0x180060a64  mov     qword ptr [rsp+0B8h+var_98], 0
0x180060a6d  mov     rcx, r12; lpCriticalSection
0x180060a70  call    cs:__imp_EnterCriticalSection
0x180060a76  mov     [rsp+0B8h+arg_18], r12
0x180060a7e  mov     r8, rbx
0x180060a81  lea     rdx, [rsp+0B8h+var_48]
0x180060a86  mov     rcx, r13
0x180060a89  call    ?find@?$_Tree@V?$_Tmap_traits@IPEAVSignOutProgress@Implementation@Internal@System@Windows@@U?$less@I@std@@V?$allocator@U?$pair@$$CBIPEAVSignOutProgress@Implementation@Internal@System@Windows@@@std@@@7@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBIPEAVSignOutProgress@Implementation@Internal@System@Windows@@@std@@@std@@@std@@@2@AEBI@Z; std::_Tree<std::_Tmap_traits<uint,Windows::System::Internal::Implementation::SignOutProgress *,std::less<uint>,std::allocator<std::pair<uint const,Windows::System::Internal::Implementation::SignOutProgress *>>,0>>::find(uint const &)
0x180060a8e  mov     rdx, [rsp+0B8h+var_48]
0x180060a93  cmp     rdx, [r13+0]
0x180060a97  jnz     short loc_180060AB6
0x180060a99  lea     rcx, [rsp+0B8h+arg_18]
0x180060aa1  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180060aa6  nop
0x180060aa7  lea     rcx, [rsp+0B8h+var_98]
0x180060aac  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180060ab1  jmp     loc_180060D09
0x180060ab6  lea     rsi, [rdx+28h]
0x180060aba  lea     rcx, [rsp+0B8h+var_98]
0x180060abf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180060ac4  mov     rcx, rsi
0x180060ac7  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180060acc  mov     rax, [rsi]
0x180060acf  mov     qword ptr [rsp+0B8h+var_98], rax; int
0x180060ad4  lea     rcx, [rsp+0B8h+arg_18]
0x180060adc  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180060ae1  xor     esi, esi
0x180060ae3  mov     [rsp+0B8h+var_88], rsi
0x180060ae8  mov     [rsp+0B8h+var_80], rsi
0x180060aed  mov     byte ptr [rsp+0B8h+arg_0], sil
0x180060af5  lea     rdx, [rsp+0B8h+var_88]
0x180060afa  lea     rcx, [rsp+0B8h+var_98]
0x180060aff  call    ??$As@UIUserProfileInternal@Implementation@Internal@System@Windows@@@?$ComPtr@UIUserProfile@Internal@System@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIUserProfileInternal@Implementation@Internal@System@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::System::Internal::IUserProfile>::As<Windows::System::Internal::Implementation::IUserProfileInternal>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::Implementation::IUserProfileInternal>>)
0x180060b04  mov     rcx, [rsp+0B8h]; this
0x180060b0c  test    eax, eax
0x180060b0e  jns     short loc_180060B24
0x180060b10  mov     r9d, eax; char *
0x180060b13  lea     r8, aOnecoreDsSecur_60; "onecore\\ds\\security\\umstartup\\userm"...
0x180060b1a  mov     edx, 1B8h; void *
0x180060b1f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180060b24  mov     rcx, [rsp+0B8h+var_88]
0x180060b29  mov     rax, [rcx]
0x180060b2c  lea     rdx, [rsp+0B8h+arg_0]
0x180060b34  mov     rax, [rax+40h]
0x180060b38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060b3d  mov     rcx, [rsp+0B8h]; this
0x180060b45  test    eax, eax
0x180060b47  jns     short loc_180060B5D
0x180060b49  mov     r9d, eax; char *
0x180060b4c  lea     r8, aOnecoreDsSecur_60; "onecore\\ds\\security\\umstartup\\userm"...
0x180060b53  mov     edx, 1B9h; void *
0x180060b58  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180060b5d  mov     byte ptr [rsp+0B8h+arg_10], sil
0x180060b65  mov     rcx, [rsp+0B8h+var_88]
0x180060b6a  mov     rax, [rcx]
0x180060b6d  lea     rdx, [rsp+0B8h+arg_10]
0x180060b75  mov     rax, [rax+48h]
0x180060b79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060b7e  mov     rcx, [rsp+0B8h]; this
0x180060b86  test    eax, eax
0x180060b88  jns     short loc_180060B9E
0x180060b8a  mov     r9d, eax; char *
0x180060b8d  lea     r8, aOnecoreDsSecur_60; "onecore\\ds\\security\\umstartup\\userm"...
0x180060b94  mov     edx, 1BBh; void *
0x180060b99  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180060b9e  cmp     byte ptr [rsp+0B8h+arg_0], sil
0x180060ba6  jz      short loc_180060BAD
0x180060ba8  test    r14b, r14b
0x180060bab  jnz     short loc_180060BB7
0x180060bad  cmp     byte ptr [rsp+0B8h+arg_10], sil
0x180060bb5  jz      short loc_180060C04
0x180060bb7  mov     dword ptr [rsp+0B8h+arg_18], esi
0x180060bbe  mov     rcx, qword ptr [rsp+0B8h+var_98]
0x180060bc3  mov     rax, [rcx]
0x180060bc6  lea     rdx, [rsp+0B8h+arg_18]
0x180060bce  mov     rax, [rax+30h]
0x180060bd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060bd7  lea     rdx, [rsp+0B8h+arg_18]
0x180060bdf  lea     rcx, [rsp+0B8h+var_60]
0x180060be4  call    ?push_back@?$vector@IV?$allocator@I@std@@@std@@QEAAXAEBI@Z; std::vector<uint>::push_back(uint const &)
0x180060be9  nop
0x180060bea  lea     rcx, [rsp+0B8h+var_80]
0x180060bef  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180060bf4  nop
0x180060bf5  lea     rcx, [rsp+0B8h+var_88]
0x180060bfa  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180060bff  jmp     loc_180060AA7
0x180060c04  mov     [rsp+0B8h+string], rsi
0x180060c09  lea     rdx, [rsp+0B8h+var_80]
0x180060c0e  lea     rcx, [rsp+0B8h+var_98]
0x180060c13  call    ??$As@UIUserProfile2@Internal@System@Windows@@@?$ComPtr@UIUserProfile@Internal@System@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIUserProfile2@Internal@System@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::System::Internal::IUserProfile>::As<Windows::System::Internal::IUserProfile2>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::IUserProfile2>>)
0x180060c18  mov     rcx, [rsp+0B8h]; this
0x180060c20  test    eax, eax
0x180060c22  jns     short loc_180060C38
0x180060c24  mov     r9d, eax; char *
0x180060c27  lea     r8, aOnecoreDsSecur_60; "onecore\\ds\\security\\umstartup\\userm"...
0x180060c2e  mov     edx, 1CAh; void *
0x180060c33  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180060c38  mov     r14, [rsp+0B8h+var_80]
0x180060c3d  mov     rax, [r14]
0x180060c40  mov     rsi, [rax+38h]
0x180060c44  mov     rcx, [rsp+0B8h+string]; string
0x180060c49  call    cs:__imp_WindowsDeleteString
0x180060c4f  mov     [rsp+0B8h+string], 0
0x180060c58  lea     rdx, [rsp+0B8h+string]
0x180060c5d  mov     rcx, r14
0x180060c60  mov     rax, rsi
0x180060c63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060c68  mov     rcx, [rsp+0B8h]; this
0x180060c70  xor     esi, esi
0x180060c72  test    eax, eax
0x180060c74  jns     short loc_180060C8A
0x180060c76  mov     r9d, eax; char *
0x180060c79  lea     r8, aOnecoreDsSecur_60; "onecore\\ds\\security\\umstartup\\userm"...
0x180060c80  mov     edx, 1CBh; void *
0x180060c85  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180060c8a  mov     rcx, [rsp+0B8h+string]; string
0x180060c8f  test    rcx, rcx
0x180060c92  jz      short loc_180060C9E
0x180060c94  call    cs:__imp_WindowsGetStringLen
0x180060c9a  test    eax, eax
0x180060c9c  jnz     short loc_180060CD1
0x180060c9e  mov     dword ptr [rsp+0B8h+arg_18], esi
0x180060ca5  mov     rcx, qword ptr [rsp+0B8h+var_98]
0x180060caa  mov     rax, [rcx]
0x180060cad  lea     rdx, [rsp+0B8h+arg_18]
0x180060cb5  mov     rax, [rax+30h]
0x180060cb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060cbe  lea     rdx, [rsp+0B8h+arg_18]
0x180060cc6  lea     rcx, [rsp+0B8h+var_60]
0x180060ccb  call    ?push_back@?$vector@IV?$allocator@I@std@@@std@@QEAAXAEBI@Z; std::vector<uint>::push_back(uint const &)
0x180060cd0  nop
0x180060cd1  mov     rcx, [rsp+0B8h+string]; string
0x180060cd6  call    cs:__imp_WindowsDeleteString
0x180060cdc  mov     [rsp+0B8h+string], rsi
0x180060ce1  lea     rcx, [rsp+0B8h+var_80]
0x180060ce6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180060ceb  nop
0x180060cec  lea     rcx, [rsp+0B8h+var_88]
0x180060cf1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180060cf6  nop
0x180060cf7  lea     rcx, [rsp+0B8h+var_98]
0x180060cfc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180060d01  mov     r14b, [rsp+0B8h+arg_8]
0x180060d09  add     rbx, 4
0x180060d0d  jmp     loc_180060959
0x180060d12  cmp     rdi, [rsp+0B8h+var_68]
0x180060d17  jnz     short loc_180060D2D
0x180060d19  mov     edx, 1
0x180060d1e  lea     rcx, [rsp+0B8h+var_78]
0x180060d23  call    ?_Reserve@?$vector@IV?$allocator@I@std@@@std@@IEAAX_K@Z; std::vector<uint>::_Reserve(unsigned __int64)
0x180060d28  mov     rdi, [rsp+0B8h+var_70]
0x180060d2d  mov     eax, [rbx+20h]
0x180060d30  mov     [rdi], eax
0x180060d32  add     rdi, 4
0x180060d36  mov     [rsp+0B8h+var_70], rdi
0x180060d3b  cmp     byte ptr [rbx+19h], 0
0x180060d3f  jnz     loc_18006093E
0x180060d45  mov     rcx, [rbx+10h]
0x180060d49  cmp     byte ptr [rcx+19h], 0
0x180060d4d  jnz     short loc_180060D56
0x180060d4f  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAUHSTRING__@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@QEAUHSTRING__@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<HSTRING__ * const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>>::_Min(std::_Tree_node<std::pair<HSTRING__ * const,Microsoft::WRL::ComPtr<Windows::System::IUser>>,void *> *)
0x180060d54  jmp     short loc_180060D6F
0x180060d56  mov     rax, [rbx+8]
0x180060d5a  jmp     short loc_180060D69
0x180060d5c  cmp     rbx, [rax+10h]
0x180060d60  jnz     short loc_180060D6F
0x180060d62  mov     rbx, rax
0x180060d65  mov     rax, [rax+8]
0x180060d69  cmp     byte ptr [rax+19h], 0
0x180060d6d  jz      short loc_180060D5C
0x180060d6f  mov     rbx, rax
0x180060d72  jmp     loc_18006093E
0x180060d77  mov     eax, dword ptr [rsp+0B8h+arg_0]
0x180060d7e  add     rsp, 80h
0x180060d85  pop     r15
0x180060d87  pop     r14
0x180060d89  pop     r13
0x180060d8b  pop     r12
0x180060d8d  pop     rdi
0x180060d8e  pop     rsi
0x180060d8f  pop     rbx
0x180060d90  retn
```
