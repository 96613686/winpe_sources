# CredProvUtils::GetLogonUIKeyPath(ushort * *)

- ea: `0x1800d9740`
- end: `0x1800d996a`
- name: `?GetLogonUIKeyPath@CredProvUtils@@YAJPEAPEAG@Z`
- size: `554`
- prototype: `__int64 __fastcall(CredProvUtils *__hidden this, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800d9640`
- `0x1800d9a78`

## callees

- `0x1800088e8`
- `0x1800356f8`
- `0x18004a9cc`
- `0x180060524`
- `0x1800d9740`
- `0x1800d9970`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d98d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d98d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d983f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d983f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800d9798`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800d9798`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800d97d7`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800d9896`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800d97d7`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800d9896`

## string_xrefs

- `0x1800d9765`: `onecore\shell\auth\credprovcommon\credprovutils\credprovutils.cpp`
- `0x1800d97ed`: `onecore\shell\auth\credprovcommon\credprovutils\credprovutils.cpp`
- `0x1800d981a`: `onecore\shell\auth\credprovcommon\credprovutils\credprovutils.cpp`
- `0x1800d9859`: `onecore\shell\auth\credprovcommon\credprovutils\credprovutils.cpp`
- `0x1800d98a7`: `onecore\shell\auth\credprovcommon\credprovutils\credprovutils.cpp`
- `0x1800d9927`: `onecore\shell\auth\credprovcommon\credprovutils\credprovutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CredProvUtils::GetLogonUIKeyPath(CredProvUtils *this, unsigned __int16 **a2)
{
  unsigned int v3; // ebx
  unsigned int PersistedRegistryLocationW; // eax
  void *v5; // rbx
  unsigned int v6; // eax
  int v7; // eax
  __int64 v8; // rax
  SIZE_T *p_cb; // [rsp+20h] [rbp-30h]
  __int64 v11; // [rsp+30h] [rbp-20h] BYREF
  __int64 v12; // [rsp+38h] [rbp-18h]
  __int64 v13; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  SIZE_T cb; // [rsp+70h] [rbp+20h] BYREF
  RTL_SRWLOCK *v16; // [rsp+78h] [rbp+28h] BYREF

  if ( this )
  {
    if ( !qword_180148310 || !*(_WORD *)qword_180148310 )
    {
      AcquireSRWLockExclusive(&stru_180148448);
      v16 = &stru_180148448;
      if ( !qword_180148310 || !*(_WORD *)qword_180148310 )
      {
        LODWORD(cb) = 0;
        PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                       L"LogonUI",
                                       L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI",
                                       0,
                                       0);
        if ( !PersistedRegistryLocationW )
        {
          v3 = -2147418113;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x23,
            (unsigned int)"onecore\\shell\\auth\\credprovcommon\\credprovutils\\credprovutils.cpp",
            (const char *)0x8000FFFFLL,
            (int)&cb);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v16);
          return v3;
        }
        if ( PersistedRegistryLocationW != 234 )
        {
          v3 = wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)0x27,
                 (unsigned int)"onecore\\shell\\auth\\credprovcommon\\credprovutils\\credprovutils.cpp",
                 (const char *)PersistedRegistryLocationW,
                 (unsigned int)&cb);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v16);
          return v3;
        }
        v5 = CoTaskMemAlloc((unsigned int)cb);
        if ( !v5 )
        {
          v3 = -2147024882;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2B,
            (unsigned int)"onecore\\shell\\auth\\credprovcommon\\credprovutils\\credprovutils.cpp",
            (const char *)0x8007000ELL,
            (int)&cb);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v16);
          return v3;
        }
        p_cb = &cb;
        v6 = GetPersistedRegistryLocationW(
               L"LogonUI",
               L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI",
               v5,
               (unsigned int)cb);
        if ( v6 )
        {
          v3 = wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)0x32,
                 (unsigned int)"onecore\\shell\\auth\\credprovcommon\\credprovutils\\credprovutils.cpp",
                 (const char *)v6,
                 (unsigned int)&cb);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v16);
          return v3;
        }
        if ( qword_180148310 )
          CoTaskMemFree(qword_180148310);
        qword_180148310 = v5;
        qword_180148320 = -1;
        qword_180148318 = -1;
      }
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v16);
    }
    v11 = 0;
    v12 = 0;
    v13 = 0;
    v7 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(
           &v11,
           &qword_180148310);
    v3 = v7;
    if ( v7 >= 0 )
    {
      v8 = v11;
      v11 = 0;
      v13 = 0;
      v12 = 0;
      *(_QWORD *)this = v8;
      v3 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x39,
        (unsigned int)"onecore\\shell\\auth\\credprovcommon\\credprovutils\\credprovutils.cpp",
        (const char *)(unsigned int)v7,
        (int)p_cb);
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v11);
  }
  else
  {
    v3 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13,
      (unsigned int)"onecore\\shell\\auth\\credprovcommon\\credprovutils\\credprovutils.cpp",
      (const char *)0x80004003LL,
      (int)p_cb);
  }
  return v3;
}

```

## disassembly

```asm
0x1800d9740  mov     [rsp-18h+arg_10], rbx
0x1800d9745  push    rbp
0x1800d9746  push    rsi
0x1800d9747  push    rdi
0x1800d9748  mov     rbp, rsp
0x1800d974b  sub     rsp, 50h
0x1800d974f  mov     rdi, rcx
0x1800d9752  xor     esi, esi
0x1800d9754  test    rcx, rcx
0x1800d9757  jnz     short loc_1800D9779
0x1800d9759  mov     rcx, [rbp+18h]; this
0x1800d975d  mov     ebx, 80004003h
0x1800d9762  mov     r9d, ebx; char *
0x1800d9765  lea     r8, aOnecoreShellAu; "onecore\\shell\\auth\\credprovcommon\\c"...
0x1800d976c  lea     edx, [rdi+13h]; void *
0x1800d976f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d9774  jmp     loc_1800D9958
0x1800d9779  mov     rax, cs:qword_180148310
0x1800d9780  test    rax, rax
0x1800d9783  jz      short loc_1800D978E
0x1800d9785  cmp     [rax], si
0x1800d9788  jnz     loc_1800D98FE
0x1800d978e  lea     rbx, stru_180148448
0x1800d9795  mov     rcx, rbx; SRWLock
0x1800d9798  call    cs:__imp_AcquireSRWLockExclusive
0x1800d979e  mov     [rbp+arg_8], rbx
0x1800d97a2  mov     rax, cs:qword_180148310
0x1800d97a9  test    rax, rax
0x1800d97ac  jz      short loc_1800D97B7
0x1800d97ae  cmp     [rax], si
0x1800d97b1  jnz     loc_1800D98F4
0x1800d97b7  mov     dword ptr [rbp+cb], esi
0x1800d97ba  lea     rax, [rbp+cb]
0x1800d97be  mov     qword ptr [rsp+50h+var_30], rax; int
0x1800d97c3  xor     r9d, r9d
0x1800d97c6  xor     r8d, r8d
0x1800d97c9  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800d97d0  lea     rcx, aLogonui; "LogonUI"
0x1800d97d7  call    cs:__imp_GetPersistedRegistryLocationW
0x1800d97dd  test    eax, eax
0x1800d97df  jnz     short loc_1800D980C
0x1800d97e1  mov     rcx, [rbp+18h]; this
0x1800d97e5  mov     ebx, 8000FFFFh
0x1800d97ea  mov     r9d, ebx; char *
0x1800d97ed  lea     r8, aOnecoreShellAu; "onecore\\shell\\auth\\credprovcommon\\c"...
0x1800d97f4  lea     edx, [rax+23h]; void *
0x1800d97f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d97fc  nop
0x1800d97fd  lea     rcx, [rbp+arg_8]
0x1800d9801  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x1800d9806  nop
0x1800d9807  jmp     loc_1800D9958
0x1800d980c  cmp     eax, 0EAh
0x1800d9811  jz      short loc_1800D983C
0x1800d9813  mov     rcx, [rbp+18h]; this
0x1800d9817  mov     r9d, eax; char *
0x1800d981a  lea     r8, aOnecoreShellAu; "onecore\\shell\\auth\\credprovcommon\\c"...
0x1800d9821  mov     edx, 27h ; '''; void *
0x1800d9826  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800d982b  mov     ebx, eax
0x1800d982d  lea     rcx, [rbp+arg_8]
0x1800d9831  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x1800d9836  nop
0x1800d9837  jmp     loc_1800D9958
0x1800d983c  mov     ecx, dword ptr [rbp+cb]; cb
0x1800d983f  call    cs:__imp_CoTaskMemAlloc
0x1800d9845  mov     rbx, rax
0x1800d9848  test    rax, rax
0x1800d984b  jnz     short loc_1800D9878
0x1800d984d  mov     rcx, [rbp+18h]; this
0x1800d9851  mov     ebx, 8007000Eh
0x1800d9856  mov     r9d, ebx; char *
0x1800d9859  lea     r8, aOnecoreShellAu; "onecore\\shell\\auth\\credprovcommon\\c"...
0x1800d9860  lea     edx, [rax+2Bh]; void *
0x1800d9863  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d9868  nop
0x1800d9869  lea     rcx, [rbp+arg_8]
0x1800d986d  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x1800d9872  nop
0x1800d9873  jmp     loc_1800D9958
0x1800d9878  lea     rax, [rbp+cb]
0x1800d987c  mov     qword ptr [rsp+50h+var_30], rax; int
0x1800d9881  mov     r9d, dword ptr [rbp+cb]
0x1800d9885  mov     r8, rbx
0x1800d9888  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800d988f  lea     rcx, aLogonui; "LogonUI"
0x1800d9896  call    cs:__imp_GetPersistedRegistryLocationW
0x1800d989c  test    eax, eax
0x1800d989e  jz      short loc_1800D98C9
0x1800d98a0  mov     rcx, [rbp+18h]; this
0x1800d98a4  mov     r9d, eax; char *
0x1800d98a7  lea     r8, aOnecoreShellAu; "onecore\\shell\\auth\\credprovcommon\\c"...
0x1800d98ae  mov     edx, 32h ; '2'; void *
0x1800d98b3  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800d98b8  mov     ebx, eax
0x1800d98ba  lea     rcx, [rbp+arg_8]
0x1800d98be  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x1800d98c3  nop
0x1800d98c4  jmp     loc_1800D9958
0x1800d98c9  mov     rcx, cs:qword_180148310; pv
0x1800d98d0  test    rcx, rcx
0x1800d98d3  jz      short loc_1800D98DB
0x1800d98d5  call    cs:__imp_CoTaskMemFree
0x1800d98db  mov     cs:qword_180148310, rbx
0x1800d98e2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800d98e6  mov     cs:qword_180148320, rax
0x1800d98ed  mov     cs:qword_180148318, rax
0x1800d98f4  lea     rcx, [rbp+arg_8]
0x1800d98f8  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x1800d98fd  nop
0x1800d98fe  mov     [rbp+var_20], rsi
0x1800d9902  mov     [rbp+var_18], rsi
0x1800d9906  mov     [rbp+var_10], rsi
0x1800d990a  lea     rdx, qword_180148310
0x1800d9911  lea     rcx, [rbp+var_20]
0x1800d9915  call    ?Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJAEBV123@@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Initialize(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> const &)
0x1800d991a  mov     ebx, eax
0x1800d991c  test    eax, eax
0x1800d991e  jns     short loc_1800D993A
0x1800d9920  mov     rcx, [rbp+18h]; this
0x1800d9924  mov     r9d, eax; char *
0x1800d9927  lea     r8, aOnecoreShellAu; "onecore\\shell\\auth\\credprovcommon\\c"...
0x1800d992e  mov     edx, 39h ; '9'; void *
0x1800d9933  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d9938  jmp     short loc_1800D994F
0x1800d993a  mov     rax, [rbp+var_20]
0x1800d993e  mov     [rbp+var_20], rsi
0x1800d9942  mov     [rbp+var_10], rsi
0x1800d9946  mov     [rbp+var_18], rsi
0x1800d994a  mov     [rdi], rax
0x1800d994d  mov     ebx, esi
0x1800d994f  lea     rcx, [rbp+var_20]
0x1800d9953  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800d9958  mov     eax, ebx
0x1800d995a  mov     rbx, [rsp+50h+arg_10]
0x1800d9962  add     rsp, 50h
0x1800d9966  pop     rdi
0x1800d9967  pop     rsi
0x1800d9968  pop     rbp
0x1800d9969  retn
```
