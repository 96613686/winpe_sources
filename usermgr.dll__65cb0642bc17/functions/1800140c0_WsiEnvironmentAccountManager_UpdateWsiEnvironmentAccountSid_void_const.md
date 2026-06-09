# WsiEnvironmentAccountManager::UpdateWsiEnvironmentAccountSid(void * const)

- ea: `0x1800140c0`
- end: `0x180014216`
- name: `?UpdateWsiEnvironmentAccountSid@WsiEnvironmentAccountManager@@AEAAJQEAX@Z`
- size: `342`
- prototype: `int(WsiEnvironmentAccountManager *__hidden this, void *const)`
- caller_count: `3`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180013b84`
- `0x180066c08`
- `0x1800d7da4`

## callees

- `0x1800138d8`
- `0x180013d30`
- `0x180013e14`
- `0x1800140c0`
- `0x18001421c`
- `0x180014334`
- `0x180014d88`
- `0x180014e9c`
- `0x1800534d0`
- `0x18005fcd4`
- `0x18005fd70`
- `0x180061e1c`
- `0x1800d769c`
- `0x1800de450`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180014141`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180014141`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180014120`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180014120`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014176`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800141dd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014176`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800141dd`

## string_xrefs

- `0x180014152`: `onecore\ds\security\umstartup\wsienvironmentaccountmanager\wsienvironmentaccountmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WsiEnvironmentAccountManager::UpdateWsiEnvironmentAccountSid(
        WsiEnvironmentAccountManager *this,
        void *const a2)
{
  const wchar_t *v4; // rdx
  DWORD LengthSid; // ebx
  PSID v6; // rsi
  const char *v7; // r9
  unsigned int LastError; // ebx
  PSID v9; // rcx
  PSID v11; // rcx
  PSID pDestinationSid[2]; // [rsp+20h] [rbp-E0h] BYREF
  struct tagComCallData v13; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v14[8]; // [rsp+148h] [rbp+48h] BYREF
  _BYTE v15[48]; // [rsp+150h] [rbp+50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  wil::ActivityBase<WsiEnvironmentAccountManagerTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<WsiEnvironmentAccountManagerTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(&v13);
  *(_QWORD *)&v13.dwDispid = &WsiEnvironmentAccountManagerTraceProvider::FunctionCall::`vftable';
  WsiEnvironmentAccountManagerTraceProvider::FunctionCall::StartActivity((WsiEnvironmentAccountManagerTraceProvider::FunctionCall *)&v13);
  WsiEnvironmentAccountManagerTraceProvider::FunctionCall::FunctionName<unsigned short const (&)[31]>((__int64)&v13, v4);
  LengthSid = GetLengthSid(a2);
  wil::make_unique_hlocal<unsigned char [0]>(pDestinationSid);
  v6 = pDestinationSid[0];
  if ( CopySid(LengthSid, pDestinationSid[0], a2) )
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      this,
      v6);
    pDestinationSid[0] = 0;
    wil::ActivityBase<WsiEnvironmentAccountManagerTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v13);
    v11 = pDestinationSid[0];
    pDestinationSid[0] = 0;
    if ( v11 )
      LocalFree(v11);
    WsiEnvironmentAccountManagerTraceProvider::FunctionCall::~FunctionCall((WsiEnvironmentAccountManagerTraceProvider::FunctionCall *)&v13);
    return 0;
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x6B,
                  (unsigned int)"onecore\\ds\\security\\umstartup\\wsienvironmentaccountmanager\\wsienvironmentaccountmanager.cpp",
                  v7);
    v9 = pDestinationSid[0];
    pDestinationSid[0] = 0;
    if ( v9 )
      LocalFree(v9);
    *(_QWORD *)&v13.dwDispid = &WsiEnvironmentAccountManagerTraceProvider::FunctionCall::`vftable';
    wil::ActivityBase<WsiEnvironmentAccountManagerTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v13);
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v15);
    wil::details::shared_object<wil::ActivityBase<WsiEnvironmentAccountManagerTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WsiEnvironmentAccountManagerTraceProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(v14);
    wil::ActivityBase<WsiEnvironmentAccountManagerTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WsiEnvironmentAccountManagerTraceProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<WsiEnvironmentAccountManagerTraceProvider,_TlgReflectorTag_Param0IsProviderType>(&v13.pUserDefined);
    return LastError;
  }
}

```

## disassembly

```asm
0x1800140c0  mov     [rsp-8+arg_10], rbx
0x1800140c5  push    rbp
0x1800140c6  push    rsi
0x1800140c7  push    rdi
0x1800140c8  push    r12
0x1800140ca  push    r14
0x1800140cc  lea     rbp, [rsp-90h]
0x1800140d4  sub     rsp, 190h
0x1800140db  mov     rax, cs:__security_cookie
0x1800140e2  xor     rax, rsp
0x1800140e5  mov     [rbp+0B0h+var_30], rax
0x1800140ec  mov     rdi, rdx
0x1800140ef  mov     r14, rcx
0x1800140f2  lea     rcx, [rsp+1B0h+var_180]
0x1800140f7  call    ??0?$ActivityBase@VWsiEnvironmentAccountManagerTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<WsiEnvironmentAccountManagerTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<WsiEnvironmentAccountManagerTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800140fc  lea     r12, ??_7FunctionCall@WsiEnvironmentAccountManagerTraceProvider@@6B@; const WsiEnvironmentAccountManagerTraceProvider::FunctionCall::`vftable'
0x180014103  mov     qword ptr [rsp+1B0h+var_180.dwDispid], r12
0x180014108  lea     rcx, [rsp+1B0h+var_180]; this
0x18001410d  call    ?StartActivity@FunctionCall@WsiEnvironmentAccountManagerTraceProvider@@QEAAXXZ; WsiEnvironmentAccountManagerTraceProvider::FunctionCall::StartActivity(void)
0x180014112  nop
0x180014113  lea     rcx, [rsp+1B0h+var_180]
0x180014118  call    ??$FunctionName@AEAY0BP@$$CBG@FunctionCall@WsiEnvironmentAccountManagerTraceProvider@@QEAAXAEAY0BP@$$CBG@Z; WsiEnvironmentAccountManagerTraceProvider::FunctionCall::FunctionName<ushort const (&)[31]>(ushort const (&)[31])
0x18001411d  mov     rcx, rdi; pSid
0x180014120  call    cs:__imp_GetLengthSid
0x180014126  mov     ebx, eax
0x180014128  mov     edx, eax
0x18001412a  lea     rcx, [rsp+1B0h+pDestinationSid]
0x18001412f  call    ??$make_unique_hlocal@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<uchar [0]>(unsigned __int64)
0x180014134  mov     rsi, [rsp+1B0h+pDestinationSid]
0x180014139  mov     r8, rdi; pSourceSid
0x18001413c  mov     rdx, rsi; pDestinationSid
0x18001413f  mov     ecx, ebx; nDestinationSidLength
0x180014141  call    cs:__imp_CopySid
0x180014147  test    eax, eax
0x180014149  jnz     short loc_1800141AC
0x18001414b  mov     rcx, [rbp+0B8h]; this
0x180014152  lea     r8, aOnecoreDsSecur_42; "onecore\\ds\\security\\umstartup\\wsien"...
0x180014159  lea     edx, [rax+6Bh]; void *
0x18001415c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180014161  mov     ebx, eax
0x180014163  mov     rcx, [rsp+1B0h+pDestinationSid]; hMem
0x180014168  mov     [rsp+1B0h+pDestinationSid], 0
0x180014171  test    rcx, rcx
0x180014174  jz      short loc_18001417D
0x180014176  call    cs:__imp_LocalFree
0x18001417c  nop
0x18001417d  mov     qword ptr [rsp+1B0h+var_180.dwDispid], r12
0x180014182  lea     rcx, [rsp+1B0h+var_180]; struct tagComCallData *
0x180014187  call    ?Destroy@?$ActivityBase@VWsiEnvironmentAccountManagerTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<WsiEnvironmentAccountManagerTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001418c  lea     rcx, [rbp+0B0h+var_60]; this
0x180014190  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180014195  lea     rcx, [rbp+0B0h+var_68]
0x180014199  call    ?reset@?$shared_object@V?$ActivityData@VWsiEnvironmentAccountManagerTraceProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VWsiEnvironmentAccountManagerTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<WsiEnvironmentAccountManagerTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WsiEnvironmentAccountManagerTraceProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x18001419e  lea     rcx, [rsp+1B0h+var_180.pUserDefined]
0x1800141a3  call    ??1?$ActivityData@VWsiEnvironmentAccountManagerTraceProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VWsiEnvironmentAccountManagerTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<WsiEnvironmentAccountManagerTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WsiEnvironmentAccountManagerTraceProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<WsiEnvironmentAccountManagerTraceProvider,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800141a8  mov     eax, ebx
0x1800141aa  jmp     short loc_1800141F0
0x1800141ac  mov     rdx, rsi
0x1800141af  mov     rcx, r14
0x1800141b2  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AJPEAX@Z$1?CamFreeBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800141b7  mov     [rsp+1B0h+pDestinationSid], 0
0x1800141c0  lea     rcx, [rsp+1B0h+var_180]
0x1800141c5  call    ?Stop@?$ActivityBase@VWsiEnvironmentAccountManagerTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<WsiEnvironmentAccountManagerTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800141ca  mov     rcx, [rsp+1B0h+pDestinationSid]; hMem
0x1800141cf  mov     [rsp+1B0h+pDestinationSid], 0
0x1800141d8  test    rcx, rcx
0x1800141db  jz      short loc_1800141E4
0x1800141dd  call    cs:__imp_LocalFree
0x1800141e3  nop
0x1800141e4  lea     rcx, [rsp+1B0h+var_180]; this
0x1800141e9  call    ??1FunctionCall@WsiEnvironmentAccountManagerTraceProvider@@QEAA@XZ; WsiEnvironmentAccountManagerTraceProvider::FunctionCall::~FunctionCall(void)
0x1800141ee  xor     eax, eax
0x1800141f0  mov     rcx, [rbp+0B0h+var_30]
0x1800141f7  xor     rcx, rsp; StackCookie
0x1800141fa  call    __security_check_cookie
0x1800141ff  mov     rbx, [rsp+1B0h+arg_10]
0x180014207  add     rsp, 190h
0x18001420e  pop     r14
0x180014210  pop     r12
0x180014212  pop     rdi
0x180014213  pop     rsi
0x180014214  pop     rbp
0x180014215  retn
```
