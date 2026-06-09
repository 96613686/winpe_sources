# HealthAndOptimizerService::StopWHEService(void)

- ea: `0x18000ba38`
- end: `0x18000bbcd`
- name: `?StopWHEService@HealthAndOptimizerService@@SAXXZ`
- size: `405`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180008bc0`
- `0x18000b380`

## callees

- `0x1800036c8`
- `0x18000435c`
- `0x1800043c4`
- `0x18000ba38`
- `0x18000f410`
- `0x1800142e0`
- `0x1800159c8`
- `0x1800187bc`
- `0x180019890`
- `0x1800236f8`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ba5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ba95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bb61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ba5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ba95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bb61`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ba78`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bab2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bb74`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ba78`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bab2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bb74`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000bb6c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000bb6c`
- `msvcp_win!_Mtx_unlock` at `0x18000bb4a`
- `msvcp_win!_Mtx_unlock` at `0x18000bb4a`
- `msvcp_win!_Mtx_lock` at `0x18000baff`
- `msvcp_win!_Mtx_lock` at `0x18000baff`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000bb0e`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000bb30`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000bb0e`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000bb30`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void HealthAndOptimizerService::StopWHEService(void)
{
  struct OrchestratorSingleton *Instance; // rdi
  void (__fastcall ***v1)(_QWORD, __int64); // rsi
  DWORD LastError; // ebx
  void (__fastcall ***v3)(_QWORD, __int64); // rsi
  DWORD v4; // ebx
  struct AssetLoaderSingleton *v5; // rdi
  HMODULE v6; // rsi
  DWORD v7; // ebx
  PluginManagerSingleton *v8; // rcx

  Instance = OrchestratorSingleton::GetInstance();
  v1 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)Instance + 72);
  if ( v1 )
  {
    LastError = GetLastError();
    (**v1)(v1, 1);
    SetLastError(LastError);
  }
  *((_QWORD *)Instance + 72) = 0;
  v3 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)Instance + 73);
  if ( v3 )
  {
    v4 = GetLastError();
    (**v3)(v3, 1);
    SetLastError(v4);
  }
  *((_QWORD *)Instance + 73) = 0;
  OrchestratorSingleton::Shutdown(Instance);
  ModuleHandler::Shutdown();
  if ( __TSS0__1__GetInstance_PluginManagerSingleton__SAAEAV2_XZ_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                                   + (unsigned int)tls_index)
                                                                                 + 4LL) )
  {
    Init_thread_header(&__TSS0__1__GetInstance_PluginManagerSingleton__SAAEAV2_XZ_4HA);
    if ( __TSS0__1__GetInstance_PluginManagerSingleton__SAAEAV2_XZ_4HA == -1 )
    {
      PluginManagerSingleton::PluginManagerSingleton(v8);
      atexit(`PluginManagerSingleton::GetInstance'::`2'::`dynamic atexit destructor for 'instance'');
      Init_thread_footer(&__TSS0__1__GetInstance_PluginManagerSingleton__SAAEAV2_XZ_4HA);
    }
  }
  if ( _Mtx_lock((_Mtx_t)&qword_1800351D0) )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  if ( dword_18003521C == 0x7FFFFFFF )
  {
    dword_18003521C = 2147483646;
    std::_Throw_Cpp_error(6);
    __debugbreak();
  }
  std::_Hash<std::_Umap_traits<std::wstring,std::unique_ptr<ActionPlugin>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::unique_ptr<ActionPlugin>>>,0>>::clear(&`PluginManagerSingleton::GetInstance'::`2'::instance);
  _Mtx_unlock((_Mtx_t)&qword_1800351D0);
  v5 = AssetLoaderSingleton::GetInstance();
  v6 = *(HMODULE *)v5;
  if ( *(_QWORD *)v5 )
  {
    v7 = GetLastError();
    FreeLibrary(v6);
    SetLastError(v7);
  }
  *(_QWORD *)v5 = 0;
}

```

## disassembly

```asm
0x18000ba38  mov     [rsp+arg_0], rbx
0x18000ba3d  mov     [rsp+arg_8], rsi
0x18000ba42  push    rdi
0x18000ba43  sub     rsp, 20h
0x18000ba47  call    ?GetInstance@OrchestratorSingleton@@SAAEAV1@XZ; OrchestratorSingleton::GetInstance(void)
0x18000ba4c  mov     rdi, rax
0x18000ba4f  mov     rsi, [rax+240h]
0x18000ba56  test    rsi, rsi
0x18000ba59  jz      short loc_18000BA7E
0x18000ba5b  call    cs:__imp_GetLastError
0x18000ba61  mov     ebx, eax
0x18000ba63  mov     rdx, [rsi]
0x18000ba66  mov     rax, [rdx]
0x18000ba69  mov     edx, 1
0x18000ba6e  mov     rcx, rsi
0x18000ba71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba76  mov     ecx, ebx; dwErrCode
0x18000ba78  call    cs:__imp_SetLastError
0x18000ba7e  mov     qword ptr [rdi+240h], 0
0x18000ba89  mov     rsi, [rdi+248h]
0x18000ba90  test    rsi, rsi
0x18000ba93  jz      short loc_18000BAB8
0x18000ba95  call    cs:__imp_GetLastError
0x18000ba9b  mov     ebx, eax
0x18000ba9d  mov     r8, [rsi]
0x18000baa0  mov     edx, 1
0x18000baa5  mov     rcx, rsi
0x18000baa8  mov     rax, [r8]
0x18000baab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bab0  mov     ecx, ebx; dwErrCode
0x18000bab2  call    cs:__imp_SetLastError
0x18000bab8  mov     qword ptr [rdi+248h], 0
0x18000bac3  mov     rcx, rdi; this
0x18000bac6  call    ?Shutdown@OrchestratorSingleton@@QEAAXXZ; OrchestratorSingleton::Shutdown(void)
0x18000bacb  call    ?Shutdown@ModuleHandler@@SAXXZ; ModuleHandler::Shutdown(void)
0x18000bad0  nop
0x18000bad1  mov     ecx, cs:_tls_index
0x18000bad7  mov     rax, gs:58h
0x18000bae0  mov     edx, 4
0x18000bae5  mov     rax, [rax+rcx*8]
0x18000bae9  mov     eax, [rdx+rax]
0x18000baec  cmp     cs:?$TSS0@?1??GetInstance@PluginManagerSingleton@@SAAEAV2@XZ@4HA, eax
0x18000baf2  jg      loc_18000BB91
0x18000baf8  lea     rcx, qword_1800351D0; _Mtx_t
0x18000baff  call    cs:__imp__Mtx_lock
0x18000bb05  test    eax, eax
0x18000bb07  jz      short loc_18000BB15
0x18000bb09  mov     ecx, 5
0x18000bb0e  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18000bb14  int     3; Trap to Debugger
0x18000bb15  cmp     cs:dword_18003521C, 7FFFFFFFh
0x18000bb1f  jnz     short loc_18000BB37
0x18000bb21  mov     cs:dword_18003521C, 7FFFFFFEh
0x18000bb2b  mov     ecx, 6
0x18000bb30  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18000bb36  int     3; Trap to Debugger
0x18000bb37  lea     rcx, ?instance@?1??GetInstance@PluginManagerSingleton@@SAAEAV2@XZ@4V2@A; PluginManagerSingleton `PluginManagerSingleton::GetInstance(void)'::`2'::instance
0x18000bb3e  call    ?clear@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VActionPlugin@@U?$default_delete@VActionPlugin@@@std@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VActionPlugin@@U?$default_delete@VActionPlugin@@@std@@@2@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Hash<std::_Umap_traits<std::wstring,std::unique_ptr<ActionPlugin>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::unique_ptr<ActionPlugin>>>,0>>::clear(void)
0x18000bb43  lea     rcx, qword_1800351D0; _Mtx_t
0x18000bb4a  call    cs:__imp__Mtx_unlock
0x18000bb50  nop
0x18000bb51  call    ?GetInstance@AssetLoaderSingleton@@SAAEAV1@XZ; AssetLoaderSingleton::GetInstance(void)
0x18000bb56  mov     rdi, rax
0x18000bb59  mov     rsi, [rax]
0x18000bb5c  test    rsi, rsi
0x18000bb5f  jz      short loc_18000BB7A
0x18000bb61  call    cs:__imp_GetLastError
0x18000bb67  mov     ebx, eax
0x18000bb69  mov     rcx, rsi; hLibModule
0x18000bb6c  call    cs:__imp_FreeLibrary
0x18000bb72  mov     ecx, ebx; dwErrCode
0x18000bb74  call    cs:__imp_SetLastError
0x18000bb7a  mov     qword ptr [rdi], 0
0x18000bb81  mov     rbx, [rsp+28h+arg_0]
0x18000bb86  mov     rsi, [rsp+28h+arg_8]
0x18000bb8b  add     rsp, 20h
0x18000bb8f  pop     rdi
0x18000bb90  retn
0x18000bb91  lea     rcx, ?$TSS0@?1??GetInstance@PluginManagerSingleton@@SAAEAV2@XZ@4HA
0x18000bb98  call    _Init_thread_header
0x18000bb9d  cmp     cs:?$TSS0@?1??GetInstance@PluginManagerSingleton@@SAAEAV2@XZ@4HA, 0FFFFFFFFh
0x18000bba4  jnz     loc_18000BAF8
0x18000bbaa  call    ??0PluginManagerSingleton@@QEAA@XZ; PluginManagerSingleton::PluginManagerSingleton(void)
0x18000bbaf  lea     rcx, ??__Finstance@?1??GetInstance@PluginManagerSingleton@@SAAEAV1@XZ@YAXXZ; void (__cdecl *)()
0x18000bbb6  call    atexit
0x18000bbbb  lea     rcx, ?$TSS0@?1??GetInstance@PluginManagerSingleton@@SAAEAV2@XZ@4HA
0x18000bbc2  call    _Init_thread_footer
0x18000bbc7  jmp     loc_18000BAF8
```
