# CINetHttp::~CINetHttp(void)

- ea: `0x180052174`
- end: `0x1800523e0`
- name: `??1CINetHttp@@UEAA@XZ`
- size: `620`
- prototype: `void __fastcall(CINetHttp *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180052ac0`
- `0x180052bc8`

## callees

- `0x180050fb8`
- `0x180052174`
- `0x1800523e8`
- `0x1800524bc`
- `0x1800ac8d4`
- `0x180129010`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180052324`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180052339`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180052358`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18005236d`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180052324`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180052339`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180052358`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18005236d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180052301`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180052301`
- `WININET!HttpCloseDependencyHandle` at `0x1800523c8`
- `WININET!HttpCloseDependencyHandle` at `0x1800523c8`
- `WININET!HttpPushClose` at `0x1800523b0`
- `WININET!HttpPushClose` at `0x1800523b0`

## pseudocode

```c
void __fastcall CINetHttp::~CINetHttp(CINetHttp *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  __int64 v9; // rcx
  HTTP_PUSH_WAIT_HANDLE v10; // rcx
  void *v11; // rcx
  unsigned int v12; // edx

  *(_QWORD *)this = &CINetHttp::`vftable'{for `IInternetProtocolEx'};
  *((_QWORD *)this + 1) = &CINetHttp::`vftable'{for `IWinInetHttpInfo'};
  *((_QWORD *)this + 2) = &CINetHttp::`vftable'{for `IWinInetCacheHints2'};
  *((_QWORD *)this + 3) = &CINetSimple::`vftable'{for `IInternetThreadSwitch'};
  *((_QWORD *)this + 4) = &CINetHttp::`vftable'{for `IInternetPriority'};
  *((_QWORD *)this + 5) = &CINetHttp::`vftable'{for `IInternetPriorityInternal'};
  *((_QWORD *)this + 6) = &CINetHttp::`vftable'{for `IPreBindingSupport'};
  *((_QWORD *)this + 7) = &CINetHttpS::`vftable'{for `IBindingExInternal'};
  *((_QWORD *)this + 8) = &CINetHttpS::`vftable'{for `IStreamDataNotificationCallback'};
  *((_QWORD *)this + 9) = &CINetHttpS::`vftable'{for `IGetBindHandle'};
  *((_QWORD *)this + 10) = &CINetHttpS::`vftable'{for `INetworkTransportSettings'};
  *((_QWORD *)this + 11) = &CINetHttpS::`vftable'{for `INotificationTransportSync'};
  if ( *((_QWORD *)this + 44)
    && ((unsigned __int8)IEConfiguration_GetBool(268435482) || (unsigned __int8)IEConfiguration_GetBool(268435481)) )
  {
    __debugbreak();
  }
  if ( *((_QWORD *)this + 43)
    && ((unsigned __int8)IEConfiguration_GetBool(268435482) || (unsigned __int8)IEConfiguration_GetBool(268435481)) )
  {
    __debugbreak();
  }
  operator delete[](*((void **)this + 146));
  v2 = (void *)*((_QWORD *)this + 140);
  *((_QWORD *)this + 146) = 0;
  operator delete[](v2);
  v3 = (void *)*((_QWORD *)this + 141);
  *((_QWORD *)this + 140) = 0;
  operator delete[](v3);
  v4 = (void *)*((_QWORD *)this + 149);
  *((_QWORD *)this + 141) = 0;
  operator delete[](v4);
  v5 = (void *)*((_QWORD *)this + 142);
  *((_QWORD *)this + 149) = 0;
  operator delete[](v5);
  v6 = (void *)*((_QWORD *)this + 150);
  *((_QWORD *)this + 142) = 0;
  operator delete[](v6);
  v7 = (void *)*((_QWORD *)this + 151);
  *((_QWORD *)this + 150) = 0;
  operator delete[](v7);
  v8 = (void *)*((_QWORD *)this + 144);
  *((_QWORD *)this + 151) = 0;
  if ( v8 != (void *)-1LL )
  {
    operator delete[](v8);
    *((_QWORD *)this + 144) = 0;
  }
  v9 = *((_QWORD *)this + 164);
  if ( v9 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    *((_QWORD *)this + 164) = 0;
  }
  v10 = (HTTP_PUSH_WAIT_HANDLE)*((_QWORD *)this + 170);
  if ( v10 )
  {
    HttpPushClose(v10);
    *((_QWORD *)this + 170) = 0;
  }
  v11 = (void *)*((_QWORD *)this + 176);
  if ( v11 )
  {
    HttpCloseDependencyHandle(v11);
    *((_QWORD *)this + 176) = 0;
  }
  CINetHttp::ClearSameSiteCookieInfo(this);
  CList<DelayedProtEntry *,DelayedProtEntry *>::RemoveAll((char *)this + 1416);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1232));
  CINet::~CINet((unsigned __int64)this, v12);
}

```

## disassembly

```asm
0x180052174  mov     [rsp+arg_0], rbx
0x180052179  push    rdi
0x18005217a  sub     rsp, 20h
0x18005217e  lea     rax, ??_7CINetHttp@@6BIInternetProtocolEx@@@; const CINetHttp::`vftable'{for `IInternetProtocolEx'}
0x180052185  xor     edi, edi
0x180052187  mov     rbx, rcx
0x18005218a  mov     [rcx], rax
0x18005218d  lea     rax, ??_7CINetHttp@@6BIWinInetHttpInfo@@@; const CINetHttp::`vftable'{for `IWinInetHttpInfo'}
0x180052194  mov     [rcx+8], rax
0x180052198  lea     rax, ??_7CINetHttp@@6BIWinInetCacheHints2@@@; const CINetHttp::`vftable'{for `IWinInetCacheHints2'}
0x18005219f  mov     [rcx+10h], rax
0x1800521a3  lea     rax, ??_7CINetSimple@@6BIInternetThreadSwitch@@@; const CINetSimple::`vftable'{for `IInternetThreadSwitch'}
0x1800521aa  mov     [rcx+18h], rax
0x1800521ae  lea     rax, ??_7CINetHttp@@6BIInternetPriority@@@; const CINetHttp::`vftable'{for `IInternetPriority'}
0x1800521b5  mov     [rcx+20h], rax
0x1800521b9  lea     rax, ??_7CINetHttp@@6BIInternetPriorityInternal@@@; const CINetHttp::`vftable'{for `IInternetPriorityInternal'}
0x1800521c0  mov     [rcx+28h], rax
0x1800521c4  lea     rax, ??_7CINetHttp@@6BIPreBindingSupport@@@; const CINetHttp::`vftable'{for `IPreBindingSupport'}
0x1800521cb  mov     [rcx+30h], rax
0x1800521cf  lea     rax, ??_7CINetHttpS@@6BIBindingExInternal@@@; const CINetHttpS::`vftable'{for `IBindingExInternal'}
0x1800521d6  mov     [rcx+38h], rax
0x1800521da  lea     rax, ??_7CINetHttpS@@6BIStreamDataNotificationCallback@@@; const CINetHttpS::`vftable'{for `IStreamDataNotificationCallback'}
0x1800521e1  mov     [rcx+40h], rax
0x1800521e5  lea     rax, ??_7CINetHttpS@@6BIGetBindHandle@@@; const CINetHttpS::`vftable'{for `IGetBindHandle'}
0x1800521ec  mov     [rcx+48h], rax
0x1800521f0  lea     rax, ??_7CINetHttpS@@6BINetworkTransportSettings@@@; const CINetHttpS::`vftable'{for `INetworkTransportSettings'}
0x1800521f7  mov     [rcx+50h], rax
0x1800521fb  lea     rax, ??_7CINetHttpS@@6BINotificationTransportSync@@@; const CINetHttpS::`vftable'{for `INotificationTransportSync'}
0x180052202  mov     [rcx+58h], rax
0x180052206  cmp     [rcx+160h], rdi
0x18005220d  jnz     loc_18005231F
0x180052213  cmp     [rbx+158h], rdi
0x18005221a  jnz     loc_180052353
0x180052220  mov     rcx, [rbx+490h]; void *
0x180052227  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18005222c  mov     rcx, [rbx+460h]; void *
0x180052233  mov     [rbx+490h], rdi
0x18005223a  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18005223f  mov     rcx, [rbx+468h]; void *
0x180052246  mov     [rbx+460h], rdi
0x18005224d  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180052252  mov     rcx, [rbx+4A8h]; void *
0x180052259  mov     [rbx+468h], rdi
0x180052260  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180052265  mov     rcx, [rbx+470h]; void *
0x18005226c  mov     [rbx+4A8h], rdi
0x180052273  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180052278  mov     rcx, [rbx+4B0h]; void *
0x18005227f  mov     [rbx+470h], rdi
0x180052286  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18005228b  mov     rcx, [rbx+4B8h]; void *
0x180052292  mov     [rbx+4B0h], rdi
0x180052299  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18005229e  mov     rcx, [rbx+480h]; void *
0x1800522a5  mov     [rbx+4B8h], rdi
0x1800522ac  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800522b0  jnz     loc_180052387
0x1800522b6  mov     rcx, [rbx+520h]
0x1800522bd  test    rcx, rcx
0x1800522c0  jnz     loc_180052398
0x1800522c6  mov     rcx, [rbx+550h]; hWait
0x1800522cd  test    rcx, rcx
0x1800522d0  jnz     loc_1800523B0
0x1800522d6  mov     rcx, [rbx+580h]; hDependencyHandle
0x1800522dd  test    rcx, rcx
0x1800522e0  jnz     loc_1800523C8
0x1800522e6  mov     rcx, rbx; this
0x1800522e9  call    ?ClearSameSiteCookieInfo@CINetHttp@@AEAAXXZ; CINetHttp::ClearSameSiteCookieInfo(void)
0x1800522ee  lea     rcx, [rbx+588h]
0x1800522f5  call    ?RemoveAll@?$CList@PEAVDelayedProtEntry@@PEAV1@@@QEAAXXZ; CList<DelayedProtEntry *,DelayedProtEntry *>::RemoveAll(void)
0x1800522fa  lea     rcx, [rbx+4D0h]; lpCriticalSection
0x180052301  call    cs:__imp_DeleteCriticalSection
0x180052308  nop     dword ptr [rax+rax+00h]
0x18005230d  mov     rcx, rbx; this
0x180052310  mov     rbx, [rsp+28h+arg_0]
0x180052315  add     rsp, 20h
0x180052319  pop     rdi
0x18005231a  jmp     ??1CINet@@UEAA@XZ; CINet::~CINet(void)
0x18005231f  mov     ecx, 1000001Ah
0x180052324  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18005232b  nop     dword ptr [rax+rax+00h]
0x180052330  test    al, al
0x180052332  jnz     short loc_18005234D
0x180052334  mov     ecx, 10000019h
0x180052339  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180052340  nop     dword ptr [rax+rax+00h]
0x180052345  test    al, al
0x180052347  jz      loc_180052213
0x18005234d  int     3; Trap to Debugger
0x18005234e  jmp     loc_180052213
0x180052353  mov     ecx, 1000001Ah
0x180052358  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18005235f  nop     dword ptr [rax+rax+00h]
0x180052364  test    al, al
0x180052366  jnz     short loc_180052381
0x180052368  mov     ecx, 10000019h
0x18005236d  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180052374  nop     dword ptr [rax+rax+00h]
0x180052379  test    al, al
0x18005237b  jz      loc_180052220
0x180052381  int     3; Trap to Debugger
0x180052382  jmp     loc_180052220
0x180052387  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18005238c  mov     [rbx+480h], rdi
0x180052393  jmp     loc_1800522B6
0x180052398  mov     rax, [rcx]
0x18005239b  mov     rax, [rax+10h]
0x18005239f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800523a4  mov     [rbx+520h], rdi
0x1800523ab  jmp     loc_1800522C6
0x1800523b0  call    cs:__imp_HttpPushClose
0x1800523b7  nop     dword ptr [rax+rax+00h]
0x1800523bc  mov     [rbx+550h], rdi
0x1800523c3  jmp     loc_1800522D6
0x1800523c8  call    cs:__imp_HttpCloseDependencyHandle
0x1800523cf  nop     dword ptr [rax+rax+00h]
0x1800523d4  mov     [rbx+580h], rdi
0x1800523db  jmp     loc_1800522E6
```
