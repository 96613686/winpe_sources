# CINetHttpEdge::~CINetHttpEdge(void)

- ea: `0x180073ba4`
- end: `0x180073ead`
- name: `??1CINetHttpEdge@@UEAA@XZ`
- size: `777`
- prototype: `void __fastcall(CINetHttpEdge *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800738d0`
- `0x180073ac4`

## callees

- `0x180073ba4`
- `0x180073eb4`
- `0x180129010`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180073e02`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180073e17`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180073e36`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180073e4b`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180073e02`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180073e17`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180073e36`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180073e4b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180073da6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180073da6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073c7d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073c9c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073cbb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073cda`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073cf9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073d18`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073d37`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073d5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073c7d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073c9c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073cbb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073cda`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073cf9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073d18`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073d37`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073d5c`
- `OLEAUT32!__imp_SysFreeString` at `0x180073def`
- `OLEAUT32!__imp_SysFreeString` at `0x180073def`
- `WININET!HttpCloseDependencyHandle` at `0x180073e95`
- `WININET!HttpCloseDependencyHandle` at `0x180073e95`
- `WININET!HttpPushClose` at `0x180073e7d`
- `WININET!HttpPushClose` at `0x180073e7d`

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
  OLECHAR *v13; // rcx
  __int64 v14; // rcx

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
  v13 = (OLECHAR *)*((_QWORD *)this + 153);
  if ( v13 )
    SysFreeString(v13);
  v14 = *((_QWORD *)this + 152);
  if ( v14 )
  {
    *((_QWORD *)this + 152) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
  CINetEdge::~CINetEdge(this);
}

```

## disassembly

```asm
0x180073ba4  mov     [rsp+arg_0], rbx
0x180073ba9  push    rdi
0x180073baa  sub     rsp, 20h
0x180073bae  lea     rax, ??_7CINetHttpEdge@@6BIInternetProtocolEx@@@; const CINetHttpEdge::`vftable'{for `IInternetProtocolEx'}
0x180073bb5  xor     edi, edi
0x180073bb7  mov     rbx, rcx
0x180073bba  mov     [rcx], rax
0x180073bbd  lea     rax, ??_7CINetHttpSEdge@@6BIWinInetHttpInfo@@@; const CINetHttpSEdge::`vftable'{for `IWinInetHttpInfo'}
0x180073bc4  mov     [rcx+8], rax
0x180073bc8  lea     rax, ??_7CINetHttpEdge@@6BIWinInetCacheHints2@@@; const CINetHttpEdge::`vftable'{for `IWinInetCacheHints2'}
0x180073bcf  mov     [rcx+10h], rax
0x180073bd3  lea     rax, ??_7CINetFileEdge@@6BIInternetThreadSwitch@@@; const CINetFileEdge::`vftable'{for `IInternetThreadSwitch'}
0x180073bda  mov     [rcx+18h], rax
0x180073bde  lea     rax, ??_7CINetHttpEdge@@6BIInternetPriority@@@; const CINetHttpEdge::`vftable'{for `IInternetPriority'}
0x180073be5  mov     [rcx+20h], rax
0x180073be9  lea     rax, ??_7CINetHttpSEdge@@6BIInternetPriorityInternal@@@; const CINetHttpSEdge::`vftable'{for `IInternetPriorityInternal'}
0x180073bf0  mov     [rcx+28h], rax
0x180073bf4  lea     rax, ??_7CINetHttpEdge@@6BIPreBindingSupport@@@; const CINetHttpEdge::`vftable'{for `IPreBindingSupport'}
0x180073bfb  mov     [rcx+30h], rax
0x180073bff  lea     rax, ??_7CINetHttpSEdge@@6BIBindingExInternal@@@; const CINetHttpSEdge::`vftable'{for `IBindingExInternal'}
0x180073c06  mov     [rcx+38h], rax
0x180073c0a  lea     rax, ??_7CINetHttpEdge@@6BIStreamDataNotificationCallback@@@; const CINetHttpEdge::`vftable'{for `IStreamDataNotificationCallback'}
0x180073c11  mov     [rcx+40h], rax
0x180073c15  lea     rax, ??_7CINetHttpSEdge@@6BIGetBindHandle@@@; const CINetHttpSEdge::`vftable'{for `IGetBindHandle'}
0x180073c1c  mov     [rcx+48h], rax
0x180073c20  lea     rax, ??_7CINetHttpSEdge@@6BINetworkTransportSettings@@@; const CINetHttpSEdge::`vftable'{for `INetworkTransportSettings'}
0x180073c27  mov     [rcx+50h], rax
0x180073c2b  lea     rax, ??_7CINetHttpSEdge@@6BINotificationTransportSync@@@; const CINetHttpSEdge::`vftable'{for `INotificationTransportSync'}
0x180073c32  mov     [rcx+58h], rax
0x180073c36  lea     rax, ??_7CINetHttpEdge@@6BIProtocolWebRequestContext@@@; const CINetHttpEdge::`vftable'{for `IProtocolWebRequestContext'}
0x180073c3d  mov     [rcx+60h], rax
0x180073c41  lea     rax, ??_7CINetHttpEdge@@6BIWinInetHttpHeaders@@@; const CINetHttpEdge::`vftable'{for `IWinInetHttpHeaders'}
0x180073c48  mov     [rcx+68h], rax
0x180073c4c  lea     rax, ??_7CINetHttpEdge@@6BIWebRequestBlockingResponseCallback@@@; const CINetHttpEdge::`vftable'{for `IWebRequestBlockingResponseCallback'}
0x180073c53  mov     [rcx+70h], rax
0x180073c57  cmp     [rcx+178h], rdi
0x180073c5e  jnz     loc_180073DFD
0x180073c64  cmp     [rbx+170h], rdi
0x180073c6b  jnz     loc_180073E31
0x180073c71  mov     rcx, [rbx+520h]; pv
0x180073c78  test    rcx, rcx
0x180073c7b  jz      short loc_180073C89
0x180073c7d  call    cs:__imp_CoTaskMemFree
0x180073c84  nop     dword ptr [rax+rax+00h]
0x180073c89  mov     rcx, [rbx+4F0h]; pv
0x180073c90  mov     [rbx+520h], rdi
0x180073c97  test    rcx, rcx
0x180073c9a  jz      short loc_180073CA8
0x180073c9c  call    cs:__imp_CoTaskMemFree
0x180073ca3  nop     dword ptr [rax+rax+00h]
0x180073ca8  mov     rcx, [rbx+4F8h]; pv
0x180073caf  mov     [rbx+4F0h], rdi
0x180073cb6  test    rcx, rcx
0x180073cb9  jz      short loc_180073CC7
0x180073cbb  call    cs:__imp_CoTaskMemFree
0x180073cc2  nop     dword ptr [rax+rax+00h]
0x180073cc7  mov     rcx, [rbx+538h]; pv
0x180073cce  mov     [rbx+4F8h], rdi
0x180073cd5  test    rcx, rcx
0x180073cd8  jz      short loc_180073CE6
0x180073cda  call    cs:__imp_CoTaskMemFree
0x180073ce1  nop     dword ptr [rax+rax+00h]
0x180073ce6  mov     rcx, [rbx+500h]; pv
0x180073ced  mov     [rbx+538h], rdi
0x180073cf4  test    rcx, rcx
0x180073cf7  jz      short loc_180073D05
0x180073cf9  call    cs:__imp_CoTaskMemFree
0x180073d00  nop     dword ptr [rax+rax+00h]
0x180073d05  mov     rcx, [rbx+540h]; pv
0x180073d0c  mov     [rbx+500h], rdi
0x180073d13  test    rcx, rcx
0x180073d16  jz      short loc_180073D24
0x180073d18  call    cs:__imp_CoTaskMemFree
0x180073d1f  nop     dword ptr [rax+rax+00h]
0x180073d24  mov     rcx, [rbx+548h]; pv
0x180073d2b  mov     [rbx+540h], rdi
0x180073d32  test    rcx, rcx
0x180073d35  jz      short loc_180073D43
0x180073d37  call    cs:__imp_CoTaskMemFree
0x180073d3e  nop     dword ptr [rax+rax+00h]
0x180073d43  mov     rcx, [rbx+510h]; pv
0x180073d4a  mov     [rbx+548h], rdi
0x180073d51  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180073d55  jz      short loc_180073D6F
0x180073d57  test    rcx, rcx
0x180073d5a  jz      short loc_180073D68
0x180073d5c  call    cs:__imp_CoTaskMemFree
0x180073d63  nop     dword ptr [rax+rax+00h]
0x180073d68  mov     [rbx+510h], rdi
0x180073d6f  mov     rcx, [rbx+758h]
0x180073d76  test    rcx, rcx
0x180073d79  jnz     loc_180073E65
0x180073d7f  mov     rcx, [rbx+788h]; hWait
0x180073d86  test    rcx, rcx
0x180073d89  jnz     loc_180073E7D
0x180073d8f  mov     rcx, [rbx+7B8h]; hDependencyHandle
0x180073d96  test    rcx, rcx
0x180073d99  jnz     loc_180073E95
0x180073d9f  lea     rcx, [rbx+560h]; lpCriticalSection
0x180073da6  call    cs:__imp_DeleteCriticalSection
0x180073dad  nop     dword ptr [rax+rax+00h]
0x180073db2  mov     rcx, [rbx+4C8h]; bstrString
0x180073db9  test    rcx, rcx
0x180073dbc  jnz     short loc_180073DEF
0x180073dbe  mov     rcx, [rbx+4C0h]
0x180073dc5  test    rcx, rcx
0x180073dc8  jz      short loc_180073DDD
0x180073dca  mov     [rbx+4C0h], rdi
0x180073dd1  mov     rax, [rcx]
0x180073dd4  mov     rax, [rax+10h]
0x180073dd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073ddd  mov     rcx, rbx; this
0x180073de0  mov     rbx, [rsp+28h+arg_0]
0x180073de5  add     rsp, 20h
0x180073de9  pop     rdi
0x180073dea  jmp     ??1CINetEdge@@UEAA@XZ; CINetEdge::~CINetEdge(void)
0x180073def  call    cs:__imp_SysFreeString
0x180073df6  nop     dword ptr [rax+rax+00h]
0x180073dfb  jmp     short loc_180073DBE
0x180073dfd  mov     ecx, 1000001Ah
0x180073e02  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180073e09  nop     dword ptr [rax+rax+00h]
0x180073e0e  test    al, al
0x180073e10  jnz     short loc_180073E2B
0x180073e12  mov     ecx, 10000019h
0x180073e17  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180073e1e  nop     dword ptr [rax+rax+00h]
0x180073e23  test    al, al
0x180073e25  jz      loc_180073C64
0x180073e2b  int     3; Trap to Debugger
0x180073e2c  jmp     loc_180073C64
0x180073e31  mov     ecx, 1000001Ah
0x180073e36  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180073e3d  nop     dword ptr [rax+rax+00h]
0x180073e42  test    al, al
0x180073e44  jnz     short loc_180073E5F
0x180073e46  mov     ecx, 10000019h
0x180073e4b  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180073e52  nop     dword ptr [rax+rax+00h]
0x180073e57  test    al, al
0x180073e59  jz      loc_180073C71
0x180073e5f  int     3; Trap to Debugger
0x180073e60  jmp     loc_180073C71
0x180073e65  mov     rax, [rcx]
0x180073e68  mov     rax, [rax+10h]
0x180073e6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073e71  mov     [rbx+758h], rdi
0x180073e78  jmp     loc_180073D7F
0x180073e7d  call    cs:__imp_HttpPushClose
0x180073e84  nop     dword ptr [rax+rax+00h]
0x180073e89  mov     [rbx+788h], rdi
0x180073e90  jmp     loc_180073D8F
0x180073e95  call    cs:__imp_HttpCloseDependencyHandle
0x180073e9c  nop     dword ptr [rax+rax+00h]
0x180073ea1  mov     [rbx+7B8h], rdi
0x180073ea8  jmp     loc_180073D9F
```
