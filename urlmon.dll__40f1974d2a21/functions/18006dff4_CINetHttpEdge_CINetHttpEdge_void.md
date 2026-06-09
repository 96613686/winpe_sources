# CINetHttpEdge::~CINetHttpEdge(void)

- ea: `0x18006dff4`
- end: `0x18006e29d`
- name: `??1CINetHttpEdge@@UEAA@XZ`
- size: `681`
- prototype: `void __fastcall(CINetHttpEdge *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18006dd30`
- `0x18006df1c`

## callees

- `0x18006dff4`
- `0x18006e2a4`
- `0x18011c010`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18006e216`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18006e225`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18006e23e`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18006e24d`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18006e216`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18006e225`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18006e23e`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18006e24d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006e1c6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006e1c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e0cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e0e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e0ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e118`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e131`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e14a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e163`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e182`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e0cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e0e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e0ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e118`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e131`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e14a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e163`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e182`
- `OLEAUT32!__imp_SysFreeString` at `0x18006e209`
- `OLEAUT32!__imp_SysFreeString` at `0x18006e209`
- `WININET!HttpCloseDependencyHandle` at `0x18006e28b`
- `WININET!HttpCloseDependencyHandle` at `0x18006e28b`
- `WININET!HttpPushClose` at `0x18006e279`
- `WININET!HttpPushClose` at `0x18006e279`

## pseudocode

```c
void __fastcall CINetHttpEdge::~CINetHttpEdge(CINetHttpEdge *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  __int64 v10; // rcx
  HTTP_PUSH_WAIT_HANDLE v11; // rcx
  void *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r8
  OLECHAR *v15; // rcx
  __int64 v16; // rcx

  *(_QWORD *)this = &CINetHttpEdge::`vftable'{for `IInternetProtocolEx'};
  *((_QWORD *)this + 1) = &CINetHttpSEdge::`vftable'{for `IWinInetHttpInfo'};
  *((_QWORD *)this + 2) = &CINetHttpEdge::`vftable'{for `IWinInetCacheHints2'};
  *((_QWORD *)this + 3) = &CINetFileEdge::`vftable'{for `IInternetThreadSwitch'};
  *((_QWORD *)this + 4) = &CINetHttpEdge::`vftable'{for `IInternetPriority'};
  *((_QWORD *)this + 5) = &CINetHttpSEdge::`vftable'{for `IInternetPriorityInternal'};
  *((_QWORD *)this + 6) = &CINetHttpEdge::`vftable'{for `IPreBindingSupport'};
  *((_QWORD *)this + 7) = &CINetHttpSEdge::`vftable'{for `IBindingExInternal'};
  *((_QWORD *)this + 8) = &CINetHttpEdge::`vftable'{for `IStreamDataNotificationCallback'};
  *((_QWORD *)this + 9) = &CINetHttpSEdge::`vftable'{for `IGetBindHandle'};
  *((_QWORD *)this + 10) = &CINetHttpSEdge::`vftable'{for `INetworkTransportSettings'};
  *((_QWORD *)this + 11) = &CINetHttpSEdge::`vftable'{for `INotificationTransportSync'};
  *((_QWORD *)this + 12) = &CINetHttpEdge::`vftable'{for `IProtocolWebRequestContext'};
  *((_QWORD *)this + 13) = &CINetHttpEdge::`vftable'{for `IWinInetHttpHeaders'};
  *((_QWORD *)this + 14) = &CINetHttpEdge::`vftable'{for `IWebRequestBlockingResponseCallback'};
  if ( *((_QWORD *)this + 47)
    && ((unsigned __int8)IEConfiguration_GetBool(268435482) || (unsigned __int8)IEConfiguration_GetBool(268435481)) )
  {
    __debugbreak();
  }
  if ( *((_QWORD *)this + 46)
    && ((unsigned __int8)IEConfiguration_GetBool(268435482) || (unsigned __int8)IEConfiguration_GetBool(268435481)) )
  {
    __debugbreak();
  }
  v2 = (void *)*((_QWORD *)this + 164);
  if ( v2 )
    CoTaskMemFree(v2);
  v3 = (void *)*((_QWORD *)this + 158);
  *((_QWORD *)this + 164) = 0;
  if ( v3 )
    CoTaskMemFree(v3);
  v4 = (void *)*((_QWORD *)this + 159);
  *((_QWORD *)this + 158) = 0;
  if ( v4 )
    CoTaskMemFree(v4);
  v5 = (void *)*((_QWORD *)this + 167);
  *((_QWORD *)this + 159) = 0;
  if ( v5 )
    CoTaskMemFree(v5);
  v6 = (void *)*((_QWORD *)this + 160);
  *((_QWORD *)this + 167) = 0;
  if ( v6 )
    CoTaskMemFree(v6);
  v7 = (void *)*((_QWORD *)this + 168);
  *((_QWORD *)this + 160) = 0;
  if ( v7 )
    CoTaskMemFree(v7);
  v8 = (void *)*((_QWORD *)this + 169);
  *((_QWORD *)this + 168) = 0;
  if ( v8 )
    CoTaskMemFree(v8);
  v9 = (void *)*((_QWORD *)this + 162);
  *((_QWORD *)this + 169) = 0;
  if ( v9 != (void *)-1LL )
  {
    if ( v9 )
      CoTaskMemFree(v9);
    *((_QWORD *)this + 162) = 0;
  }
  v10 = *((_QWORD *)this + 235);
  if ( v10 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    *((_QWORD *)this + 235) = 0;
  }
  v11 = (HTTP_PUSH_WAIT_HANDLE)*((_QWORD *)this + 241);
  if ( v11 )
  {
    HttpPushClose(v11);
    *((_QWORD *)this + 241) = 0;
  }
  v12 = (void *)*((_QWORD *)this + 247);
  if ( v12 )
  {
    HttpCloseDependencyHandle(v12);
    *((_QWORD *)this + 247) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1376));
  v15 = (OLECHAR *)*((_QWORD *)this + 153);
  if ( v15 )
    SysFreeString(v15);
  v16 = *((_QWORD *)this + 152);
  if ( v16 )
  {
    *((_QWORD *)this + 152) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  }
  CINetEdge::~CINetEdge(this, v13, v14);
}

```

## disassembly

```asm
0x18006dff4  mov     [rsp+arg_0], rbx
0x18006dff9  push    rdi
0x18006dffa  sub     rsp, 20h
0x18006dffe  lea     rax, ??_7CINetHttpEdge@@6BIInternetProtocolEx@@@; const CINetHttpEdge::`vftable'{for `IInternetProtocolEx'}
0x18006e005  xor     edi, edi
0x18006e007  mov     rbx, rcx
0x18006e00a  mov     [rcx], rax
0x18006e00d  lea     rax, ??_7CINetHttpSEdge@@6BIWinInetHttpInfo@@@; const CINetHttpSEdge::`vftable'{for `IWinInetHttpInfo'}
0x18006e014  mov     [rcx+8], rax
0x18006e018  lea     rax, ??_7CINetHttpEdge@@6BIWinInetCacheHints2@@@; const CINetHttpEdge::`vftable'{for `IWinInetCacheHints2'}
0x18006e01f  mov     [rcx+10h], rax
0x18006e023  lea     rax, ??_7CINetFileEdge@@6BIInternetThreadSwitch@@@; const CINetFileEdge::`vftable'{for `IInternetThreadSwitch'}
0x18006e02a  mov     [rcx+18h], rax
0x18006e02e  lea     rax, ??_7CINetHttpEdge@@6BIInternetPriority@@@; const CINetHttpEdge::`vftable'{for `IInternetPriority'}
0x18006e035  mov     [rcx+20h], rax
0x18006e039  lea     rax, ??_7CINetHttpSEdge@@6BIInternetPriorityInternal@@@; const CINetHttpSEdge::`vftable'{for `IInternetPriorityInternal'}
0x18006e040  mov     [rcx+28h], rax
0x18006e044  lea     rax, ??_7CINetHttpEdge@@6BIPreBindingSupport@@@; const CINetHttpEdge::`vftable'{for `IPreBindingSupport'}
0x18006e04b  mov     [rcx+30h], rax
0x18006e04f  lea     rax, ??_7CINetHttpSEdge@@6BIBindingExInternal@@@; const CINetHttpSEdge::`vftable'{for `IBindingExInternal'}
0x18006e056  mov     [rcx+38h], rax
0x18006e05a  lea     rax, ??_7CINetHttpEdge@@6BIStreamDataNotificationCallback@@@; const CINetHttpEdge::`vftable'{for `IStreamDataNotificationCallback'}
0x18006e061  mov     [rcx+40h], rax
0x18006e065  lea     rax, ??_7CINetHttpSEdge@@6BIGetBindHandle@@@; const CINetHttpSEdge::`vftable'{for `IGetBindHandle'}
0x18006e06c  mov     [rcx+48h], rax
0x18006e070  lea     rax, ??_7CINetHttpSEdge@@6BINetworkTransportSettings@@@; const CINetHttpSEdge::`vftable'{for `INetworkTransportSettings'}
0x18006e077  mov     [rcx+50h], rax
0x18006e07b  lea     rax, ??_7CINetHttpSEdge@@6BINotificationTransportSync@@@; const CINetHttpSEdge::`vftable'{for `INotificationTransportSync'}
0x18006e082  mov     [rcx+58h], rax
0x18006e086  lea     rax, ??_7CINetHttpEdge@@6BIProtocolWebRequestContext@@@; const CINetHttpEdge::`vftable'{for `IProtocolWebRequestContext'}
0x18006e08d  mov     [rcx+60h], rax
0x18006e091  lea     rax, ??_7CINetHttpEdge@@6BIWinInetHttpHeaders@@@; const CINetHttpEdge::`vftable'{for `IWinInetHttpHeaders'}
0x18006e098  mov     [rcx+68h], rax
0x18006e09c  lea     rax, ??_7CINetHttpEdge@@6BIWebRequestBlockingResponseCallback@@@; const CINetHttpEdge::`vftable'{for `IWebRequestBlockingResponseCallback'}
0x18006e0a3  mov     [rcx+70h], rax
0x18006e0a7  cmp     [rcx+178h], rdi
0x18006e0ae  jnz     loc_18006E211
0x18006e0b4  cmp     [rbx+170h], rdi
0x18006e0bb  jnz     loc_18006E239
0x18006e0c1  mov     rcx, [rbx+520h]; pv
0x18006e0c8  test    rcx, rcx
0x18006e0cb  jz      short loc_18006E0D3
0x18006e0cd  call    cs:__imp_CoTaskMemFree
0x18006e0d3  mov     rcx, [rbx+4F0h]; pv
0x18006e0da  mov     [rbx+520h], rdi
0x18006e0e1  test    rcx, rcx
0x18006e0e4  jz      short loc_18006E0EC
0x18006e0e6  call    cs:__imp_CoTaskMemFree
0x18006e0ec  mov     rcx, [rbx+4F8h]; pv
0x18006e0f3  mov     [rbx+4F0h], rdi
0x18006e0fa  test    rcx, rcx
0x18006e0fd  jz      short loc_18006E105
0x18006e0ff  call    cs:__imp_CoTaskMemFree
0x18006e105  mov     rcx, [rbx+538h]; pv
0x18006e10c  mov     [rbx+4F8h], rdi
0x18006e113  test    rcx, rcx
0x18006e116  jz      short loc_18006E11E
0x18006e118  call    cs:__imp_CoTaskMemFree
0x18006e11e  mov     rcx, [rbx+500h]; pv
0x18006e125  mov     [rbx+538h], rdi
0x18006e12c  test    rcx, rcx
0x18006e12f  jz      short loc_18006E137
0x18006e131  call    cs:__imp_CoTaskMemFree
0x18006e137  mov     rcx, [rbx+540h]; pv
0x18006e13e  mov     [rbx+500h], rdi
0x18006e145  test    rcx, rcx
0x18006e148  jz      short loc_18006E150
0x18006e14a  call    cs:__imp_CoTaskMemFree
0x18006e150  mov     rcx, [rbx+548h]; pv
0x18006e157  mov     [rbx+540h], rdi
0x18006e15e  test    rcx, rcx
0x18006e161  jz      short loc_18006E169
0x18006e163  call    cs:__imp_CoTaskMemFree
0x18006e169  mov     rcx, [rbx+510h]; pv
0x18006e170  mov     [rbx+548h], rdi
0x18006e177  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18006e17b  jz      short loc_18006E18F
0x18006e17d  test    rcx, rcx
0x18006e180  jz      short loc_18006E188
0x18006e182  call    cs:__imp_CoTaskMemFree
0x18006e188  mov     [rbx+510h], rdi
0x18006e18f  mov     rcx, [rbx+758h]
0x18006e196  test    rcx, rcx
0x18006e199  jnz     loc_18006E261
0x18006e19f  mov     rcx, [rbx+788h]; hWait
0x18006e1a6  test    rcx, rcx
0x18006e1a9  jnz     loc_18006E279
0x18006e1af  mov     rcx, [rbx+7B8h]; hDependencyHandle
0x18006e1b6  test    rcx, rcx
0x18006e1b9  jnz     loc_18006E28B
0x18006e1bf  lea     rcx, [rbx+560h]; lpCriticalSection
0x18006e1c6  call    cs:__imp_DeleteCriticalSection
0x18006e1cc  mov     rcx, [rbx+4C8h]; bstrString
0x18006e1d3  test    rcx, rcx
0x18006e1d6  jnz     short loc_18006E209
0x18006e1d8  mov     rcx, [rbx+4C0h]
0x18006e1df  test    rcx, rcx
0x18006e1e2  jz      short loc_18006E1F7
0x18006e1e4  mov     [rbx+4C0h], rdi
0x18006e1eb  mov     rax, [rcx]
0x18006e1ee  mov     rax, [rax+10h]
0x18006e1f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e1f7  mov     rcx, rbx; this
0x18006e1fa  mov     rbx, [rsp+28h+arg_0]
0x18006e1ff  add     rsp, 20h
0x18006e203  pop     rdi
0x18006e204  jmp     ??1CINetEdge@@UEAA@XZ; CINetEdge::~CINetEdge(void)
0x18006e209  call    cs:__imp_SysFreeString
0x18006e20f  jmp     short loc_18006E1D8
0x18006e211  mov     ecx, 1000001Ah
0x18006e216  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18006e21c  test    al, al
0x18006e21e  jnz     short loc_18006E233
0x18006e220  mov     ecx, 10000019h
0x18006e225  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18006e22b  test    al, al
0x18006e22d  jz      loc_18006E0B4
0x18006e233  int     3; Trap to Debugger
0x18006e234  jmp     loc_18006E0B4
0x18006e239  mov     ecx, 1000001Ah
0x18006e23e  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18006e244  test    al, al
0x18006e246  jnz     short loc_18006E25B
0x18006e248  mov     ecx, 10000019h
0x18006e24d  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18006e253  test    al, al
0x18006e255  jz      loc_18006E0C1
0x18006e25b  int     3; Trap to Debugger
0x18006e25c  jmp     loc_18006E0C1
0x18006e261  mov     rax, [rcx]
0x18006e264  mov     rax, [rax+10h]
0x18006e268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e26d  mov     [rbx+758h], rdi
0x18006e274  jmp     loc_18006E19F
0x18006e279  call    cs:__imp_HttpPushClose
0x18006e27f  mov     [rbx+788h], rdi
0x18006e286  jmp     loc_18006E1AF
0x18006e28b  call    cs:__imp_HttpCloseDependencyHandle
0x18006e291  mov     [rbx+7B8h], rdi
0x18006e298  jmp     loc_18006E1BF
```
