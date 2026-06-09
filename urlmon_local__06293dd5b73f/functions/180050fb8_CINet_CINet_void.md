# CINet::~CINet(void)

- ea: `0x180050fb8`
- end: `0x1800514b1`
- name: `??1CINet@@UEAA@XZ`
- size: `1273`
- prototype: `void __fastcall(CINet *__hidden this)`
- caller_count: `5`
- callee_count: `7`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180050a54`
- `0x180052174`
- `0x1800de340`
- `0x1800e101c`
- `0x1800e5018`

## callees

- `0x18002fee0`
- `0x180050fb8`
- `0x180051864`
- `0x180052994`
- `0x18008a4f0`
- `0x1800de3b0`
- `0x180129010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180051178`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180051178`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180051110`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180051110`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005119a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800511bb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005119a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800511bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051057`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005106f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051087`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051057`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005106f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051087`
- `OLEAUT32!__imp_SysFreeString` at `0x180051451`
- `OLEAUT32!__imp_SysFreeString` at `0x180051469`
- `OLEAUT32!__imp_SysFreeString` at `0x180051481`
- `OLEAUT32!__imp_SysFreeString` at `0x180051499`
- `OLEAUT32!__imp_SysFreeString` at `0x180051451`
- `OLEAUT32!__imp_SysFreeString` at `0x180051469`
- `OLEAUT32!__imp_SysFreeString` at `0x180051481`
- `OLEAUT32!__imp_SysFreeString` at `0x180051499`

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
0x180050fb8  push    rbx
0x180050fba  push    rbp
0x180050fbb  push    rsi
0x180050fbc  push    rdi
0x180050fbd  push    r14
0x180050fbf  sub     rsp, 20h
0x180050fc3  lea     rax, ??_7CINet@@6BIInternetProtocolEx@@@; const CINet::`vftable'{for `IInternetProtocolEx'}
0x180050fca  mov     rbx, rcx
0x180050fcd  mov     [rcx], rax
0x180050fd0  xor     esi, esi
0x180050fd2  lea     rax, ??_7CINetHttp@@6BIWinInetHttpInfo@@@; const CINetHttp::`vftable'{for `IWinInetHttpInfo'}
0x180050fd9  mov     [rcx+8], rax
0x180050fdd  lea     rax, ??_7CINetHttp@@6BIWinInetCacheHints2@@@; const CINetHttp::`vftable'{for `IWinInetCacheHints2'}
0x180050fe4  mov     [rcx+10h], rax
0x180050fe8  lea     rax, ??_7CINetSimple@@6BIInternetThreadSwitch@@@; const CINetSimple::`vftable'{for `IInternetThreadSwitch'}
0x180050fef  mov     [rcx+18h], rax
0x180050ff3  lea     rax, ??_7CINetStream@@6BIInternetPriority@@@; const CINetStream::`vftable'{for `IInternetPriority'}
0x180050ffa  mov     [rcx+20h], rax
0x180050ffe  lea     rax, ??_7CINetFtp@@6BIInternetPriorityInternal@@@; const CINetFtp::`vftable'{for `IInternetPriorityInternal'}
0x180051005  mov     [rcx+28h], rax
0x180051009  lea     rax, ??_7CINetFile@@6BIPreBindingSupport@@@; const CINetFile::`vftable'{for `IPreBindingSupport'}
0x180051010  mov     [rcx+30h], rax
0x180051014  lea     rax, ??_7CINetSimple@@6BIBindingExInternal@@@; const CINetSimple::`vftable'{for `IBindingExInternal'}
0x18005101b  mov     [rcx+38h], rax
0x18005101f  lea     rax, ??_7CINetFtp@@6BIStreamDataNotificationCallback@@@; const CINetFtp::`vftable'{for `IStreamDataNotificationCallback'}
0x180051026  mov     [rcx+40h], rax
0x18005102a  lea     rax, ??_7CINetStream@@6BIGetBindHandle@@@; const CINetStream::`vftable'{for `IGetBindHandle'}
0x180051031  mov     [rcx+48h], rax
0x180051035  lea     rax, ??_7CINet@@6BINetworkTransportSettings@@@; const CINet::`vftable'{for `INetworkTransportSettings'}
0x18005103c  mov     [rcx+50h], rax
0x180051040  lea     rax, ??_7CINetFtp@@6BINotificationTransportSync@@@; const CINetFtp::`vftable'{for `INotificationTransportSync'}
0x180051047  mov     [rcx+58h], rax
0x18005104b  mov     rcx, [rcx+150h]; pv
0x180051052  test    rcx, rcx
0x180051055  jz      short loc_180051063
0x180051057  call    cs:__imp_CoTaskMemFree
0x18005105e  nop     dword ptr [rax+rax+00h]
0x180051063  mov     rcx, [rbx+148h]; pv
0x18005106a  test    rcx, rcx
0x18005106d  jz      short loc_18005107B
0x18005106f  call    cs:__imp_CoTaskMemFree
0x180051076  nop     dword ptr [rax+rax+00h]
0x18005107b  mov     rcx, [rbx+140h]; pv
0x180051082  test    rcx, rcx
0x180051085  jz      short loc_180051093
0x180051087  call    cs:__imp_CoTaskMemFree
0x18005108e  nop     dword ptr [rax+rax+00h]
0x180051093  mov     rcx, [rbx+3C8h]; this
0x18005109a  test    rcx, rcx
0x18005109d  jnz     loc_1800513EF
0x1800510a3  mov     rcx, [rbx+3C0h]; void *
0x1800510aa  test    rcx, rcx
0x1800510ad  jnz     loc_180051400
0x1800510b3  mov     rcx, [rbx+3D8h]; this
0x1800510ba  test    rcx, rcx
0x1800510bd  jnz     loc_180051411
0x1800510c3  mov     rcx, [rbx+3D0h]; void *
0x1800510ca  test    rcx, rcx
0x1800510cd  jnz     loc_180051422
0x1800510d3  mov     rcx, [rbx+70h]
0x1800510d7  test    rcx, rcx
0x1800510da  jz      short loc_1800510EC
0x1800510dc  mov     rax, [rcx]
0x1800510df  mov     rax, [rax+10h]
0x1800510e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800510e8  mov     [rbx+70h], rsi
0x1800510ec  mov     rcx, [rbx+3F0h]; this
0x1800510f3  test    rcx, rcx
0x1800510f6  jnz     loc_180051433
0x1800510fc  call    ?GetGlobalINetManager@@YAPEAVCINetManager@@XZ; GetGlobalINetManager(void)
0x180051101  mov     rdi, rax
0x180051104  test    rax, rax
0x180051107  jz      short loc_180051184
0x180051109  lea     rcx, ?g_mxsCINetMgr@@3VCMutexSem@@A; lpCriticalSection
0x180051110  call    cs:__imp_EnterCriticalSection
0x180051117  nop     dword ptr [rax+rax+00h]
0x18005111c  mov     r10d, [rdi+18h]
0x180051120  xor     edx, edx
0x180051122  mov     r11, [rdi]
0x180051125  mov     rax, rbx
0x180051128  div     r10
0x18005112b  mov     ebp, 1
0x180051130  mov     ecx, edx
0x180051132  mov     r9, rdx
0x180051135  shl     rcx, 4
0x180051139  add     rcx, r11
0x18005113c  mov     r8, [rcx]
0x18005113f  mov     rax, r8
0x180051142  and     rax, 0FFFFFFFFFFFFFFFEh
0x180051146  cmp     rbx, rax
0x180051149  jnz     loc_1800513A2
0x18005114f  test    bpl, r8b
0x180051152  jnz     loc_180051397
0x180051158  mov     [rcx], rsi
0x18005115b  mov     [rcx+8], rsi
0x18005115f  dec     dword ptr [rdi+8]
0x180051162  mov     eax, [rdi+8]
0x180051165  cmp     eax, [rdi+14h]
0x180051168  jb      loc_180051444
0x18005116e  dec     dword ptr [rdi+38h]
0x180051171  lea     rcx, ?g_mxsCINetMgr@@3VCMutexSem@@A; lpCriticalSection
0x180051178  call    cs:__imp_LeaveCriticalSection
0x18005117f  nop     dword ptr [rax+rax+00h]
0x180051184  cmp     cs:?g_cRef@@3VCRefCount@@A, esi; CRefCount g_cRef
0x18005118a  jle     short loc_180051193
0x18005118c  lock dec cs:?g_cRef@@3VCRefCount@@A; CRefCount g_cRef
0x180051193  lea     rcx, [rbx+418h]; lpCriticalSection
0x18005119a  call    cs:__imp_DeleteCriticalSection
0x1800511a1  nop     dword ptr [rax+rax+00h]
0x1800511a6  lea     rax, ??_7CPrivUnknown@CINet@@6B@; const CINet::CPrivUnknown::`vftable'
0x1800511ad  lea     rcx, [rbx+1E8h]; lpCriticalSection
0x1800511b4  mov     [rbx+400h], rax
0x1800511bb  call    cs:__imp_DeleteCriticalSection
0x1800511c2  nop     dword ptr [rax+rax+00h]
0x1800511c7  mov     rdi, [rbx+118h]
0x1800511ce  lea     r14, ??_7CUString@@6B@; const CUString::`vftable'
0x1800511d5  mov     [rbx+110h], r14
0x1800511dc  mov     ebp, 0Bh
0x1800511e1  test    rdi, rdi
0x1800511e4  jz      loc_180051357
0x1800511ea  mov     rcx, [rbx+128h]; bstrString
0x1800511f1  test    rcx, rcx
0x1800511f4  jnz     loc_180051451
0x1800511fa  mov     [rbx+130h], rsi
0x180051201  mov     [rbx+138h], esi
0x180051207  test    rdi, rdi
0x18005120a  jz      short loc_18005122B
0x18005120c  mov     rcx, [rbx+118h]
0x180051213  test    rcx, rcx
0x180051216  jz      short loc_18005122B
0x180051218  mov     rax, [rcx]
0x18005121b  mov     rax, [rax+10h]
0x18005121f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051224  mov     [rbx+118h], rsi
0x18005122b  mov     [rbx+120h], ebp
0x180051231  mov     rdi, [rbx+0E8h]
0x180051238  mov     [rbx+0E0h], r14
0x18005123f  test    rdi, rdi
0x180051242  jz      loc_180051368
0x180051248  mov     rcx, [rbx+0F8h]; bstrString
0x18005124f  test    rcx, rcx
0x180051252  jnz     loc_180051469
0x180051258  mov     [rbx+100h], rsi
0x18005125f  mov     [rbx+108h], esi
0x180051265  test    rdi, rdi
0x180051268  jz      short loc_180051289
0x18005126a  mov     rcx, [rbx+0E8h]
0x180051271  test    rcx, rcx
0x180051274  jz      short loc_180051289
0x180051276  mov     rax, [rcx]
0x180051279  mov     rax, [rax+10h]
0x18005127d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051282  mov     [rbx+0E8h], rsi
0x180051289  mov     [rbx+0F0h], ebp
0x18005128f  mov     rdi, [rbx+0B8h]
0x180051296  mov     [rbx+0B0h], r14
0x18005129d  test    rdi, rdi
0x1800512a0  jz      loc_180051379
0x1800512a6  mov     rcx, [rbx+0C8h]; bstrString
0x1800512ad  test    rcx, rcx
0x1800512b0  jnz     loc_180051481
0x1800512b6  mov     [rbx+0D0h], rsi
0x1800512bd  mov     [rbx+0D8h], esi
0x1800512c3  test    rdi, rdi
0x1800512c6  jz      short loc_1800512E7
0x1800512c8  mov     rcx, [rbx+0B8h]
0x1800512cf  test    rcx, rcx
0x1800512d2  jz      short loc_1800512E7
0x1800512d4  mov     rax, [rcx]
0x1800512d7  mov     rax, [rax+10h]
0x1800512db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800512e0  mov     [rbx+0B8h], rsi
0x1800512e7  mov     [rbx+0C0h], ebp
0x1800512ed  mov     rdi, [rbx+88h]
0x1800512f4  mov     [rbx+80h], r14
0x1800512fb  test    rdi, rdi
0x1800512fe  jz      loc_18005138A
0x180051304  mov     rcx, [rbx+98h]; bstrString
0x18005130b  test    rcx, rcx
0x18005130e  jnz     loc_180051499
0x180051314  mov     [rbx+0A0h], rsi
0x18005131b  mov     [rbx+0A8h], esi
0x180051321  test    rdi, rdi
0x180051324  jz      short loc_180051345
0x180051326  mov     rcx, [rbx+88h]
0x18005132d  test    rcx, rcx
0x180051330  jz      short loc_180051345
0x180051332  mov     rax, [rcx]
0x180051335  mov     rax, [rax+10h]
0x180051339  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005133e  mov     [rbx+88h], rsi
0x180051345  mov     [rbx+90h], ebp
0x18005134b  add     rsp, 20h
0x18005134f  pop     r14
0x180051351  pop     rdi
0x180051352  pop     rsi
0x180051353  pop     rbp
0x180051354  pop     rbx
0x180051355  retn
0x180051357  cmp     [rbx+120h], ebp
0x18005135d  jz      loc_18005122B
0x180051363  jmp     loc_1800511EA
0x180051368  cmp     [rbx+0F0h], ebp
0x18005136e  jz      loc_180051289
0x180051374  jmp     loc_180051248
0x180051379  cmp     [rbx+0C0h], ebp
0x18005137f  jz      loc_1800512E7
0x180051385  jmp     loc_1800512A6
0x18005138a  cmp     [rbx+90h], ebp
0x180051390  jz      short loc_180051345
0x180051392  jmp     loc_180051304
0x180051397  mov     [rcx], rbp
0x18005139a  add     [rdi+0Ch], ebp
0x18005139d  jmp     loc_18005115B
0x1800513a2  test    bpl, r8b
0x1800513a5  jz      loc_18005116E
0x1800513ab  mov     rdx, rbx
0x1800513ae  shr     rdx, 2
0x1800513b2  and     edx, [rdi+1Ch]
0x1800513b5  add     edx, ebp
0x1800513b7  lea     ecx, [rdx+r9]
0x1800513bb  mov     eax, ecx
0x1800513bd  sub     eax, r10d
0x1800513c0  cmp     ecx, r10d
0x1800513c3  cmovb   eax, ecx
0x1800513c6  mov     ecx, eax
0x1800513c8  shl     rcx, 4
0x1800513cc  add     rcx, r11
0x1800513cf  mov     r9d, eax
0x1800513d2  mov     r8, [rcx]
0x1800513d5  mov     rax, r8
0x1800513d8  and     rax, 0FFFFFFFFFFFFFFFEh
0x1800513dc  cmp     rbx, rax
0x1800513df  jz      loc_18005114F
0x1800513e5  test    bpl, r8b
0x1800513e8  jnz     short loc_1800513B7
0x1800513ea  jmp     loc_18005116E
0x1800513ef  call    ??_GCSecureStr@@QEAAPEAXI@Z; CSecureStr::`scalar deleting destructor'(uint)
0x1800513f4  mov     [rbx+3C8h], rsi
0x1800513fb  jmp     loc_1800510A3
0x180051400  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180051405  mov     [rbx+3C0h], rsi
0x18005140c  jmp     loc_1800510B3
0x180051411  call    ??_GCSecureStr@@QEAAPEAXI@Z; CSecureStr::`scalar deleting destructor'(uint)
0x180051416  mov     [rbx+3D8h], rsi
0x18005141d  jmp     loc_1800510C3
0x180051422  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180051427  mov     [rbx+3D0h], rsi
0x18005142e  jmp     loc_1800510D3
0x180051433  call    ?ReleaseInstance@CHttpProtocolListenerManager@@SAXPEAV1@@Z; CHttpProtocolListenerManager::ReleaseInstance(CHttpProtocolListenerManager *)
0x180051438  mov     [rbx+3F0h], rsi
0x18005143f  jmp     loc_1800510FC
0x180051444  mov     rcx, rdi; void **
0x180051447  call    ?Shrink@?$CHtPvPvBaseT@$1?nullCompare@@YAHPEBX00_N@ZUHashTableEntry@@@@AEAAXXZ; CHtPvPvBaseT<&nullCompare(void const *,void const *,void const *,bool),HashTableEntry>::Shrink(void)
0x18005144c  jmp     loc_18005116E
0x180051451  call    cs:__imp_SysFreeString
0x180051458  nop     dword ptr [rax+rax+00h]
0x18005145d  mov     [rbx+128h], rsi
0x180051464  jmp     loc_1800511FA
0x180051469  call    cs:__imp_SysFreeString
0x180051470  nop     dword ptr [rax+rax+00h]
0x180051475  mov     [rbx+0F8h], rsi
0x18005147c  jmp     loc_180051258
0x180051481  call    cs:__imp_SysFreeString
0x180051488  nop     dword ptr [rax+rax+00h]
0x18005148d  mov     [rbx+0C8h], rsi
0x180051494  jmp     loc_1800512B6
0x180051499  call    cs:__imp_SysFreeString
0x1800514a0  nop     dword ptr [rax+rax+00h]
0x1800514a5  mov     [rbx+98h], rsi
0x1800514ac  jmp     loc_180051314
```
