# CINet::~CINet(void)

- ea: `0x18005e230`
- end: `0x18005e6e6`
- name: `??1CINet@@UEAA@XZ`
- size: `1206`
- prototype: `void __fastcall(unsigned __int64 this, unsigned int)`
- caller_count: `5`
- callee_count: `7`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18005d568`
- `0x18005defc`
- `0x1800d5230`
- `0x1800d7d60`
- `0x1800dbba8`

## callees

- `0x180030880`
- `0x18005e230`
- `0x18005ea78`
- `0x18005f7a8`
- `0x180084874`
- `0x1800d529c`
- `0x18011c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005e3d8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005e3d8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005e376`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005e376`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005e3f4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005e40f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005e3f4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005e40f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005e2cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005e2e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005e2f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005e2cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005e2e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005e2f3`
- `OLEAUT32!__imp_SysFreeString` at `0x18005e69e`
- `OLEAUT32!__imp_SysFreeString` at `0x18005e6b0`
- `OLEAUT32!__imp_SysFreeString` at `0x18005e6c2`
- `OLEAUT32!__imp_SysFreeString` at `0x18005e6d4`
- `OLEAUT32!__imp_SysFreeString` at `0x18005e69e`
- `OLEAUT32!__imp_SysFreeString` at `0x18005e6b0`
- `OLEAUT32!__imp_SysFreeString` at `0x18005e6c2`
- `OLEAUT32!__imp_SysFreeString` at `0x18005e6d4`

## pseudocode

```c
void __fastcall CINet::~CINet(unsigned __int64 this, unsigned int a2)
{
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  CSecureStr *v6; // rcx
  void *v7; // rcx
  CSecureStr *v8; // rcx
  void *v9; // rcx
  __int64 v10; // rcx
  struct CHttpProtocolListenerManager *v11; // rcx
  struct CINetManager *GlobalINetManager; // rdi
  unsigned int v13; // r10d
  unsigned __int64 v14; // r9
  __int64 *v15; // rcx
  __int64 v16; // r8
  __int64 v17; // rdi
  OLECHAR *v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rdi
  OLECHAR *v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rdi
  OLECHAR *v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rdi
  OLECHAR *v27; // rcx
  __int64 v28; // rcx
  int v29; // edx
  unsigned int v30; // eax

  *(_QWORD *)this = &CINet::`vftable'{for `IInternetProtocolEx'};
  *(_QWORD *)(this + 8) = &CINetHttp::`vftable'{for `IWinInetHttpInfo'};
  *(_QWORD *)(this + 16) = &CINetHttp::`vftable'{for `IWinInetCacheHints2'};
  *(_QWORD *)(this + 24) = &CINetSimple::`vftable'{for `IInternetThreadSwitch'};
  *(_QWORD *)(this + 32) = &CINetStream::`vftable'{for `IInternetPriority'};
  *(_QWORD *)(this + 40) = &CINetFtp::`vftable'{for `IInternetPriorityInternal'};
  *(_QWORD *)(this + 48) = &CINetFile::`vftable'{for `IPreBindingSupport'};
  *(_QWORD *)(this + 56) = &CINetSimple::`vftable'{for `IBindingExInternal'};
  *(_QWORD *)(this + 64) = &CINetFtp::`vftable'{for `IStreamDataNotificationCallback'};
  *(_QWORD *)(this + 72) = &CINetStream::`vftable'{for `IGetBindHandle'};
  *(_QWORD *)(this + 80) = &CINet::`vftable'{for `INetworkTransportSettings'};
  *(_QWORD *)(this + 88) = &CINetFtp::`vftable'{for `INotificationTransportSync'};
  v3 = *(void **)(this + 336);
  if ( v3 )
    CoTaskMemFree(v3);
  v4 = *(void **)(this + 328);
  if ( v4 )
    CoTaskMemFree(v4);
  v5 = *(void **)(this + 320);
  if ( v5 )
    CoTaskMemFree(v5);
  v6 = *(CSecureStr **)(this + 968);
  if ( v6 )
  {
    CSecureStr::`scalar deleting destructor'(v6, a2);
    *(_QWORD *)(this + 968) = 0;
  }
  v7 = *(void **)(this + 960);
  if ( v7 )
  {
    operator delete(v7);
    *(_QWORD *)(this + 960) = 0;
  }
  v8 = *(CSecureStr **)(this + 984);
  if ( v8 )
  {
    CSecureStr::`scalar deleting destructor'(v8, a2);
    *(_QWORD *)(this + 984) = 0;
  }
  v9 = *(void **)(this + 976);
  if ( v9 )
  {
    operator delete(v9);
    *(_QWORD *)(this + 976) = 0;
  }
  v10 = *(_QWORD *)(this + 112);
  if ( v10 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    *(_QWORD *)(this + 112) = 0;
  }
  v11 = *(struct CHttpProtocolListenerManager **)(this + 1008);
  if ( v11 )
  {
    CHttpProtocolListenerManager::ReleaseInstance(v11);
    *(_QWORD *)(this + 1008) = 0;
  }
  GlobalINetManager = GetGlobalINetManager();
  if ( GlobalINetManager )
  {
    EnterCriticalSection(&g_mxsCINetMgr);
    v13 = *((_DWORD *)GlobalINetManager + 6);
    v14 = this % v13;
    v15 = (__int64 *)(*(_QWORD *)GlobalINetManager + 16LL * (unsigned int)v14);
    v16 = *v15;
    if ( this != (*v15 & 0xFFFFFFFFFFFFFFFEuLL) )
    {
      if ( (v16 & 1) == 0 )
      {
LABEL_25:
        --*((_DWORD *)GlobalINetManager + 14);
        LeaveCriticalSection(&g_mxsCINetMgr);
        goto LABEL_26;
      }
      v29 = (*((_DWORD *)GlobalINetManager + 7) & (this >> 2)) + 1;
      while ( 1 )
      {
        v30 = v29 + v14 - v13;
        if ( v29 + (int)v14 < v13 )
          v30 = v29 + v14;
        v15 = (__int64 *)(*(_QWORD *)GlobalINetManager + 16LL * v30);
        LODWORD(v14) = v30;
        v16 = *v15;
        if ( this == (*v15 & 0xFFFFFFFFFFFFFFFEuLL) )
          break;
        if ( (v16 & 1) == 0 )
          goto LABEL_25;
      }
    }
    if ( (v16 & 1) != 0 )
    {
      *v15 = 1;
      ++*((_DWORD *)GlobalINetManager + 3);
    }
    else
    {
      *v15 = 0;
    }
    v15[1] = 0;
    if ( --*((_DWORD *)GlobalINetManager + 2) < *((_DWORD *)GlobalINetManager + 5) )
      CHtPvPvBaseT<&int nullCompare(void const *,void const *,void const *,bool),HashTableEntry>::Shrink((void **)GlobalINetManager);
    goto LABEL_25;
  }
LABEL_26:
  if ( g_cRef > 0 )
    _InterlockedDecrement((volatile signed __int32 *)&g_cRef);
  DeleteCriticalSection((LPCRITICAL_SECTION)(this + 1048));
  *(_QWORD *)(this + 1024) = &CINet::CPrivUnknown::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)(this + 488));
  v17 = *(_QWORD *)(this + 280);
  *(_QWORD *)(this + 272) = &CUString::`vftable';
  if ( v17 || *(_DWORD *)(this + 288) != 11 )
  {
    v18 = *(OLECHAR **)(this + 296);
    if ( v18 )
    {
      SysFreeString(v18);
      *(_QWORD *)(this + 296) = 0;
    }
    *(_QWORD *)(this + 304) = 0;
    *(_DWORD *)(this + 312) = 0;
    if ( v17 )
    {
      v19 = *(_QWORD *)(this + 280);
      if ( v19 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
        *(_QWORD *)(this + 280) = 0;
      }
    }
  }
  *(_DWORD *)(this + 288) = 11;
  v20 = *(_QWORD *)(this + 232);
  *(_QWORD *)(this + 224) = &CUString::`vftable';
  if ( v20 || *(_DWORD *)(this + 240) != 11 )
  {
    v21 = *(OLECHAR **)(this + 248);
    if ( v21 )
    {
      SysFreeString(v21);
      *(_QWORD *)(this + 248) = 0;
    }
    *(_QWORD *)(this + 256) = 0;
    *(_DWORD *)(this + 264) = 0;
    if ( v20 )
    {
      v22 = *(_QWORD *)(this + 232);
      if ( v22 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
        *(_QWORD *)(this + 232) = 0;
      }
    }
  }
  *(_DWORD *)(this + 240) = 11;
  v23 = *(_QWORD *)(this + 184);
  *(_QWORD *)(this + 176) = &CUString::`vftable';
  if ( v23 || *(_DWORD *)(this + 192) != 11 )
  {
    v24 = *(OLECHAR **)(this + 200);
    if ( v24 )
    {
      SysFreeString(v24);
      *(_QWORD *)(this + 200) = 0;
    }
    *(_QWORD *)(this + 208) = 0;
    *(_DWORD *)(this + 216) = 0;
    if ( v23 )
    {
      v25 = *(_QWORD *)(this + 184);
      if ( v25 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
        *(_QWORD *)(this + 184) = 0;
      }
    }
  }
  *(_DWORD *)(this + 192) = 11;
  v26 = *(_QWORD *)(this + 136);
  *(_QWORD *)(this + 128) = &CUString::`vftable';
  if ( v26 || *(_DWORD *)(this + 144) != 11 )
  {
    v27 = *(OLECHAR **)(this + 152);
    if ( v27 )
    {
      SysFreeString(v27);
      *(_QWORD *)(this + 152) = 0;
    }
    *(_QWORD *)(this + 160) = 0;
    *(_DWORD *)(this + 168) = 0;
    if ( v26 )
    {
      v28 = *(_QWORD *)(this + 136);
      if ( v28 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
        *(_QWORD *)(this + 136) = 0;
      }
    }
  }
  *(_DWORD *)(this + 144) = 11;
}

```

## disassembly

```asm
0x18005e230  push    rbx
0x18005e232  push    rbp
0x18005e233  push    rsi
0x18005e234  push    rdi
0x18005e235  push    r14
0x18005e237  sub     rsp, 20h
0x18005e23b  lea     rax, ??_7CINet@@6BIInternetProtocolEx@@@; const CINet::`vftable'{for `IInternetProtocolEx'}
0x18005e242  mov     rbx, rcx
0x18005e245  mov     [rcx], rax
0x18005e248  xor     esi, esi
0x18005e24a  lea     rax, ??_7CINetHttp@@6BIWinInetHttpInfo@@@; const CINetHttp::`vftable'{for `IWinInetHttpInfo'}
0x18005e251  mov     [rcx+8], rax
0x18005e255  lea     rax, ??_7CINetHttp@@6BIWinInetCacheHints2@@@; const CINetHttp::`vftable'{for `IWinInetCacheHints2'}
0x18005e25c  mov     [rcx+10h], rax
0x18005e260  lea     rax, ??_7CINetSimple@@6BIInternetThreadSwitch@@@; const CINetSimple::`vftable'{for `IInternetThreadSwitch'}
0x18005e267  mov     [rcx+18h], rax
0x18005e26b  lea     rax, ??_7CINetStream@@6BIInternetPriority@@@; const CINetStream::`vftable'{for `IInternetPriority'}
0x18005e272  mov     [rcx+20h], rax
0x18005e276  lea     rax, ??_7CINetFtp@@6BIInternetPriorityInternal@@@; const CINetFtp::`vftable'{for `IInternetPriorityInternal'}
0x18005e27d  mov     [rcx+28h], rax
0x18005e281  lea     rax, ??_7CINetFile@@6BIPreBindingSupport@@@; const CINetFile::`vftable'{for `IPreBindingSupport'}
0x18005e288  mov     [rcx+30h], rax
0x18005e28c  lea     rax, ??_7CINetSimple@@6BIBindingExInternal@@@; const CINetSimple::`vftable'{for `IBindingExInternal'}
0x18005e293  mov     [rcx+38h], rax
0x18005e297  lea     rax, ??_7CINetFtp@@6BIStreamDataNotificationCallback@@@; const CINetFtp::`vftable'{for `IStreamDataNotificationCallback'}
0x18005e29e  mov     [rcx+40h], rax
0x18005e2a2  lea     rax, ??_7CINetStream@@6BIGetBindHandle@@@; const CINetStream::`vftable'{for `IGetBindHandle'}
0x18005e2a9  mov     [rcx+48h], rax
0x18005e2ad  lea     rax, ??_7CINet@@6BINetworkTransportSettings@@@; const CINet::`vftable'{for `INetworkTransportSettings'}
0x18005e2b4  mov     [rcx+50h], rax
0x18005e2b8  lea     rax, ??_7CINetFtp@@6BINotificationTransportSync@@@; const CINetFtp::`vftable'{for `INotificationTransportSync'}
0x18005e2bf  mov     [rcx+58h], rax
0x18005e2c3  mov     rcx, [rcx+150h]; pv
0x18005e2ca  test    rcx, rcx
0x18005e2cd  jz      short loc_18005E2D5
0x18005e2cf  call    cs:__imp_CoTaskMemFree
0x18005e2d5  mov     rcx, [rbx+148h]; pv
0x18005e2dc  test    rcx, rcx
0x18005e2df  jz      short loc_18005E2E7
0x18005e2e1  call    cs:__imp_CoTaskMemFree
0x18005e2e7  mov     rcx, [rbx+140h]; pv
0x18005e2ee  test    rcx, rcx
0x18005e2f1  jz      short loc_18005E2F9
0x18005e2f3  call    cs:__imp_CoTaskMemFree
0x18005e2f9  mov     rcx, [rbx+3C8h]; this
0x18005e300  test    rcx, rcx
0x18005e303  jnz     loc_18005E63C
0x18005e309  mov     rcx, [rbx+3C0h]; void *
0x18005e310  test    rcx, rcx
0x18005e313  jnz     loc_18005E64D
0x18005e319  mov     rcx, [rbx+3D8h]; this
0x18005e320  test    rcx, rcx
0x18005e323  jnz     loc_18005E65E
0x18005e329  mov     rcx, [rbx+3D0h]; void *
0x18005e330  test    rcx, rcx
0x18005e333  jnz     loc_18005E66F
0x18005e339  mov     rcx, [rbx+70h]
0x18005e33d  test    rcx, rcx
0x18005e340  jz      short loc_18005E352
0x18005e342  mov     rax, [rcx]
0x18005e345  mov     rax, [rax+10h]
0x18005e349  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e34e  mov     [rbx+70h], rsi
0x18005e352  mov     rcx, [rbx+3F0h]; this
0x18005e359  test    rcx, rcx
0x18005e35c  jnz     loc_18005E680
0x18005e362  call    ?GetGlobalINetManager@@YAPEAVCINetManager@@XZ; GetGlobalINetManager(void)
0x18005e367  mov     rdi, rax
0x18005e36a  test    rax, rax
0x18005e36d  jz      short loc_18005E3DE
0x18005e36f  lea     rcx, ?g_mxsCINetMgr@@3VCMutexSem@@A; lpCriticalSection
0x18005e376  call    cs:__imp_EnterCriticalSection
0x18005e37c  mov     r10d, [rdi+18h]
0x18005e380  xor     edx, edx
0x18005e382  mov     r11, [rdi]
0x18005e385  mov     rax, rbx
0x18005e388  div     r10
0x18005e38b  mov     ebp, 1
0x18005e390  mov     ecx, edx
0x18005e392  mov     r9, rdx
0x18005e395  shl     rcx, 4
0x18005e399  add     rcx, r11
0x18005e39c  mov     r8, [rcx]
0x18005e39f  mov     rax, r8
0x18005e3a2  and     rax, 0FFFFFFFFFFFFFFFEh
0x18005e3a6  cmp     rbx, rax
0x18005e3a9  jnz     loc_18005E5EF
0x18005e3af  test    bpl, r8b
0x18005e3b2  jnz     loc_18005E5E4
0x18005e3b8  mov     [rcx], rsi
0x18005e3bb  mov     [rcx+8], rsi
0x18005e3bf  dec     dword ptr [rdi+8]
0x18005e3c2  mov     eax, [rdi+8]
0x18005e3c5  cmp     eax, [rdi+14h]
0x18005e3c8  jb      loc_18005E691
0x18005e3ce  dec     dword ptr [rdi+38h]
0x18005e3d1  lea     rcx, ?g_mxsCINetMgr@@3VCMutexSem@@A; lpCriticalSection
0x18005e3d8  call    cs:__imp_LeaveCriticalSection
0x18005e3de  cmp     cs:?g_cRef@@3VCRefCount@@A, esi; CRefCount g_cRef
0x18005e3e4  jle     short loc_18005E3ED
0x18005e3e6  lock dec cs:?g_cRef@@3VCRefCount@@A; CRefCount g_cRef
0x18005e3ed  lea     rcx, [rbx+418h]; lpCriticalSection
0x18005e3f4  call    cs:__imp_DeleteCriticalSection
0x18005e3fa  lea     rax, ??_7CPrivUnknown@CINet@@6B@; const CINet::CPrivUnknown::`vftable'
0x18005e401  lea     rcx, [rbx+1E8h]; lpCriticalSection
0x18005e408  mov     [rbx+400h], rax
0x18005e40f  call    cs:__imp_DeleteCriticalSection
0x18005e415  mov     rdi, [rbx+118h]
0x18005e41c  lea     r14, ??_7CUString@@6B@; const CUString::`vftable'
0x18005e423  mov     [rbx+110h], r14
0x18005e42a  mov     ebp, 0Bh
0x18005e42f  test    rdi, rdi
0x18005e432  jz      loc_18005E5A4
0x18005e438  mov     rcx, [rbx+128h]; bstrString
0x18005e43f  test    rcx, rcx
0x18005e442  jnz     loc_18005E69E
0x18005e448  mov     [rbx+130h], rsi
0x18005e44f  mov     [rbx+138h], esi
0x18005e455  test    rdi, rdi
0x18005e458  jz      short loc_18005E479
0x18005e45a  mov     rcx, [rbx+118h]
0x18005e461  test    rcx, rcx
0x18005e464  jz      short loc_18005E479
0x18005e466  mov     rax, [rcx]
0x18005e469  mov     rax, [rax+10h]
0x18005e46d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e472  mov     [rbx+118h], rsi
0x18005e479  mov     [rbx+120h], ebp
0x18005e47f  mov     rdi, [rbx+0E8h]
0x18005e486  mov     [rbx+0E0h], r14
0x18005e48d  test    rdi, rdi
0x18005e490  jz      loc_18005E5B5
0x18005e496  mov     rcx, [rbx+0F8h]; bstrString
0x18005e49d  test    rcx, rcx
0x18005e4a0  jnz     loc_18005E6B0
0x18005e4a6  mov     [rbx+100h], rsi
0x18005e4ad  mov     [rbx+108h], esi
0x18005e4b3  test    rdi, rdi
0x18005e4b6  jz      short loc_18005E4D7
0x18005e4b8  mov     rcx, [rbx+0E8h]
0x18005e4bf  test    rcx, rcx
0x18005e4c2  jz      short loc_18005E4D7
0x18005e4c4  mov     rax, [rcx]
0x18005e4c7  mov     rax, [rax+10h]
0x18005e4cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e4d0  mov     [rbx+0E8h], rsi
0x18005e4d7  mov     [rbx+0F0h], ebp
0x18005e4dd  mov     rdi, [rbx+0B8h]
0x18005e4e4  mov     [rbx+0B0h], r14
0x18005e4eb  test    rdi, rdi
0x18005e4ee  jz      loc_18005E5C6
0x18005e4f4  mov     rcx, [rbx+0C8h]; bstrString
0x18005e4fb  test    rcx, rcx
0x18005e4fe  jnz     loc_18005E6C2
0x18005e504  mov     [rbx+0D0h], rsi
0x18005e50b  mov     [rbx+0D8h], esi
0x18005e511  test    rdi, rdi
0x18005e514  jz      short loc_18005E535
0x18005e516  mov     rcx, [rbx+0B8h]
0x18005e51d  test    rcx, rcx
0x18005e520  jz      short loc_18005E535
0x18005e522  mov     rax, [rcx]
0x18005e525  mov     rax, [rax+10h]
0x18005e529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e52e  mov     [rbx+0B8h], rsi
0x18005e535  mov     [rbx+0C0h], ebp
0x18005e53b  mov     rdi, [rbx+88h]
0x18005e542  mov     [rbx+80h], r14
0x18005e549  test    rdi, rdi
0x18005e54c  jz      loc_18005E5D7
0x18005e552  mov     rcx, [rbx+98h]; bstrString
0x18005e559  test    rcx, rcx
0x18005e55c  jnz     loc_18005E6D4
0x18005e562  mov     [rbx+0A0h], rsi
0x18005e569  mov     [rbx+0A8h], esi
0x18005e56f  test    rdi, rdi
0x18005e572  jz      short loc_18005E593
0x18005e574  mov     rcx, [rbx+88h]
0x18005e57b  test    rcx, rcx
0x18005e57e  jz      short loc_18005E593
0x18005e580  mov     rax, [rcx]
0x18005e583  mov     rax, [rax+10h]
0x18005e587  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e58c  mov     [rbx+88h], rsi
0x18005e593  mov     [rbx+90h], ebp
0x18005e599  add     rsp, 20h
0x18005e59d  pop     r14
0x18005e59f  pop     rdi
0x18005e5a0  pop     rsi
0x18005e5a1  pop     rbp
0x18005e5a2  pop     rbx
0x18005e5a3  retn
0x18005e5a4  cmp     [rbx+120h], ebp
0x18005e5aa  jz      loc_18005E479
0x18005e5b0  jmp     loc_18005E438
0x18005e5b5  cmp     [rbx+0F0h], ebp
0x18005e5bb  jz      loc_18005E4D7
0x18005e5c1  jmp     loc_18005E496
0x18005e5c6  cmp     [rbx+0C0h], ebp
0x18005e5cc  jz      loc_18005E535
0x18005e5d2  jmp     loc_18005E4F4
0x18005e5d7  cmp     [rbx+90h], ebp
0x18005e5dd  jz      short loc_18005E593
0x18005e5df  jmp     loc_18005E552
0x18005e5e4  mov     [rcx], rbp
0x18005e5e7  add     [rdi+0Ch], ebp
0x18005e5ea  jmp     loc_18005E3BB
0x18005e5ef  test    bpl, r8b
0x18005e5f2  jz      loc_18005E3CE
0x18005e5f8  mov     rdx, rbx
0x18005e5fb  shr     rdx, 2
0x18005e5ff  and     edx, [rdi+1Ch]
0x18005e602  add     edx, ebp
0x18005e604  lea     ecx, [rdx+r9]
0x18005e608  mov     eax, ecx
0x18005e60a  sub     eax, r10d
0x18005e60d  cmp     ecx, r10d
0x18005e610  cmovb   eax, ecx
0x18005e613  mov     ecx, eax
0x18005e615  shl     rcx, 4
0x18005e619  add     rcx, r11
0x18005e61c  mov     r9d, eax
0x18005e61f  mov     r8, [rcx]
0x18005e622  mov     rax, r8
0x18005e625  and     rax, 0FFFFFFFFFFFFFFFEh
0x18005e629  cmp     rbx, rax
0x18005e62c  jz      loc_18005E3AF
0x18005e632  test    bpl, r8b
0x18005e635  jnz     short loc_18005E604
0x18005e637  jmp     loc_18005E3CE
0x18005e63c  call    ??_GCSecureStr@@QEAAPEAXI@Z; CSecureStr::`scalar deleting destructor'(uint)
0x18005e641  mov     [rbx+3C8h], rsi
0x18005e648  jmp     loc_18005E309
0x18005e64d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005e652  mov     [rbx+3C0h], rsi
0x18005e659  jmp     loc_18005E319
0x18005e65e  call    ??_GCSecureStr@@QEAAPEAXI@Z; CSecureStr::`scalar deleting destructor'(uint)
0x18005e663  mov     [rbx+3D8h], rsi
0x18005e66a  jmp     loc_18005E329
0x18005e66f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005e674  mov     [rbx+3D0h], rsi
0x18005e67b  jmp     loc_18005E339
0x18005e680  call    ?ReleaseInstance@CHttpProtocolListenerManager@@SAXPEAV1@@Z; CHttpProtocolListenerManager::ReleaseInstance(CHttpProtocolListenerManager *)
0x18005e685  mov     [rbx+3F0h], rsi
0x18005e68c  jmp     loc_18005E362
0x18005e691  mov     rcx, rdi; void **
0x18005e694  call    ?Shrink@?$CHtPvPvBaseT@$1?nullCompare@@YAHPEBX00_N@ZUHashTableEntry@@@@AEAAXXZ; CHtPvPvBaseT<&nullCompare(void const *,void const *,void const *,bool),HashTableEntry>::Shrink(void)
0x18005e699  jmp     loc_18005E3CE
0x18005e69e  call    cs:__imp_SysFreeString
0x18005e6a4  mov     [rbx+128h], rsi
0x18005e6ab  jmp     loc_18005E448
0x18005e6b0  call    cs:__imp_SysFreeString
0x18005e6b6  mov     [rbx+0F8h], rsi
0x18005e6bd  jmp     loc_18005E4A6
0x18005e6c2  call    cs:__imp_SysFreeString
0x18005e6c8  mov     [rbx+0C8h], rsi
0x18005e6cf  jmp     loc_18005E504
0x18005e6d4  call    cs:__imp_SysFreeString
0x18005e6da  mov     [rbx+98h], rsi
0x18005e6e1  jmp     loc_18005E562
```
