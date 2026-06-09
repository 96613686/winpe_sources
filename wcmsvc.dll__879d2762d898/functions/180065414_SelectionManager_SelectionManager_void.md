# SelectionManager::~SelectionManager(void)

- ea: `0x180065414`
- end: `0x180065550`
- name: `??1SelectionManager@@UEAA@XZ`
- size: `316`
- prototype: `void __fastcall(SelectionManager *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800cd420`

## callees

- `0x180010080`
- `0x18006514c`
- `0x180065414`
- `0x1800664ec`
- `0x18009a24c`
- `0x1800cb0f8`
- `0x1800cd4d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180065441`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180065441`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800654cc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180065527`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800654cc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180065527`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180065549`

## pseudocode

```c
void __fastcall SelectionManager::~SelectionManager(SelectionManager *this)
{
  InterfaceLifetimeTracking *v2; // rcx
  _QWORD **v3; // rcx
  _QWORD *v4; // rdi
  std::_Ref_count_base *v5; // rcx
  _QWORD *v6; // rsi

  *(_QWORD *)this = &SelectionManager::`vftable';
  SelectionManager::InternalDeinitialize(this);
  if ( g_selectionManagerExitHandle )
    SetEvent(g_selectionManagerExitHandle);
  WcmCommon::ThreadPoolProcessLatestWorkItem<1>::~ThreadPoolProcessLatestWorkItem<1>((char *)this + 232);
  v2 = (InterfaceLifetimeTracking *)*((_QWORD *)this + 26);
  if ( v2 )
  {
    std::_Destroy_range<std::allocator<InterfaceLifetimeTracking>>(v2);
    std::_Deallocate<16>(
      *((void **)this + 26),
      (struct std::nothrow_t *)(24 * ((*((_QWORD *)this + 28) - *((_QWORD *)this + 26)) / 24LL)));
    *((_QWORD *)this + 26) = 0;
    *((_QWORD *)this + 27) = 0;
    *((_QWORD *)this + 28) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 168));
  v3 = (_QWORD **)*((_QWORD *)this + 19);
  *v3[1] = 0;
  v4 = *v3;
  if ( *v3 )
  {
    do
    {
      v5 = (std::_Ref_count_base *)v4[3];
      v6 = (_QWORD *)*v4;
      if ( v5 )
        std::_Ref_count_base::_Decref(v5);
      std::_Deallocate<16>(v4, (struct std::nothrow_t *)0x20);
      v4 = v6;
    }
    while ( v6 );
  }
  std::_Deallocate<16>(*((void **)this + 19), (struct std::nothrow_t *)0x20);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  std::_Hash<std::_Umap_traits<std::wstring,ConnectoidConfig,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,ConnectoidConfig>>,1>>::~_Hash<std::_Umap_traits<std::wstring,ConnectoidConfig,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,ConnectoidConfig>>,1>>((char *)this + 48);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x180065414  mov     [rsp+arg_0], rbx
0x180065419  mov     [rsp+arg_8], rsi
0x18006541e  push    rdi
0x18006541f  sub     rsp, 20h
0x180065423  lea     rax, ??_7SelectionManager@@6B@; const SelectionManager::`vftable'
0x18006542a  mov     rbx, rcx
0x18006542d  mov     [rcx], rax
0x180065430  call    ?InternalDeinitialize@SelectionManager@@IEAAXXZ; SelectionManager::InternalDeinitialize(void)
0x180065435  mov     rcx, cs:?g_selectionManagerExitHandle@@3PEAXEA; hEvent
0x18006543c  test    rcx, rcx
0x18006543f  jz      short loc_180065447
0x180065441  call    cs:__imp_SetEvent
0x180065447  lea     rcx, [rbx+0E8h]
0x18006544e  call    ??1?$ThreadPoolProcessLatestWorkItem@$00@WcmCommon@@QEAA@XZ; WcmCommon::ThreadPoolProcessLatestWorkItem<1>::~ThreadPoolProcessLatestWorkItem<1>(void)
0x180065453  mov     rcx, [rbx+0D0h]; this
0x18006545a  test    rcx, rcx
0x18006545d  jz      short loc_1800654C5
0x18006545f  mov     rdx, [rbx+0D8h]
0x180065466  call    ??$_Destroy_range@V?$allocator@VInterfaceLifetimeTracking@@@std@@@std@@YAXPEAVInterfaceLifetimeTracking@@QEAV1@AEAV?$allocator@VInterfaceLifetimeTracking@@@0@@Z; std::_Destroy_range<std::allocator<InterfaceLifetimeTracking>>(InterfaceLifetimeTracking *,InterfaceLifetimeTracking * const,std::allocator<InterfaceLifetimeTracking> &)
0x18006546b  mov     rcx, [rbx+0D0h]
0x180065472  mov     rax, 2AAAAAAAAAAAAAABh
0x18006547c  mov     rdx, [rbx+0E0h]
0x180065483  sub     rdx, rcx
0x180065486  imul    rdx
0x180065489  sar     rdx, 2
0x18006548d  mov     rax, rdx
0x180065490  shr     rax, 3Fh
0x180065494  add     rdx, rax
0x180065497  lea     rdx, [rdx+rdx*2]
0x18006549b  shl     rdx, 3
0x18006549f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800654a4  mov     qword ptr [rbx+0D0h], 0
0x1800654af  mov     qword ptr [rbx+0D8h], 0
0x1800654ba  mov     qword ptr [rbx+0E0h], 0
0x1800654c5  lea     rcx, [rbx+0A8h]; lpCriticalSection
0x1800654cc  call    cs:__imp_DeleteCriticalSection
0x1800654d2  mov     rcx, [rbx+98h]
0x1800654d9  mov     rax, [rcx+8]
0x1800654dd  mov     qword ptr [rax], 0
0x1800654e4  mov     rdi, [rcx]
0x1800654e7  test    rdi, rdi
0x1800654ea  jz      short loc_180065512
0x1800654ec  mov     rcx, [rdi+18h]; this
0x1800654f0  mov     rsi, [rdi]
0x1800654f3  test    rcx, rcx
0x1800654f6  jz      short loc_1800654FD
0x1800654f8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800654fd  mov     edx, 20h ; ' '
0x180065502  mov     rcx, rdi
0x180065505  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18006550a  mov     rdi, rsi
0x18006550d  test    rsi, rsi
0x180065510  jnz     short loc_1800654EC
0x180065512  mov     rcx, [rbx+98h]
0x180065519  mov     edx, 20h ; ' '
0x18006551e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180065523  lea     rcx, [rbx+70h]; lpCriticalSection
0x180065527  call    cs:__imp_DeleteCriticalSection
0x18006552d  lea     rcx, [rbx+30h]
0x180065531  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UConnectoidConfig@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UConnectoidConfig@@@std@@@2@$00@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,ConnectoidConfig,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,ConnectoidConfig>>,1>>::~_Hash<std::_Umap_traits<std::wstring,ConnectoidConfig,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,ConnectoidConfig>>,1>>(void)
0x180065536  lea     rcx, [rbx+8]
0x18006553a  mov     rbx, [rsp+28h+arg_0]
0x18006553f  mov     rsi, [rsp+28h+arg_8]
0x180065544  add     rsp, 20h
0x180065548  pop     rdi
0x180065549  jmp     cs:__imp_DeleteCriticalSection
```
