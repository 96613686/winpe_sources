# OrchestratorSingleton::HeavyModuleDequeueThread(void)

- ea: `0x180014398`
- end: `0x1800145c2`
- name: `?HeavyModuleDequeueThread@OrchestratorSingleton@@AEAAKXZ`
- size: `554`
- prototype: `__int64 __fastcall(HANDLE *this)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800145d0`

## callees

- `0x180003be4`
- `0x180009024`
- `0x18001164c`
- `0x180011904`
- `0x180014398`
- `0x180014a14`
- `0x180014bf4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800143bd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800144a9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001456a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800143bd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800144a9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001456a`
- `msvcp_win!_Mtx_unlock` at `0x18001449d`
- `msvcp_win!_Mtx_unlock` at `0x18001449d`
- `msvcp_win!_Mtx_lock` at `0x18001440a`
- `msvcp_win!_Mtx_lock` at `0x18001440a`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800145ab`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800145b7`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800145ab`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800145b7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall OrchestratorSingleton::HeavyModuleDequeueThread(HANDLE *this)
{
  _QWORD *v2; // rax
  _QWORD *v3; // r8
  __int64 v4; // rax
  _QWORD *v5; // rcx
  void *v6; // rcx
  void *v7; // rdx
  void *v8; // rdx
  void *v9; // rdx
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rdi
  const char *v13; // r9
  __int128 v15; // [rsp+20h] [rbp-30h] BYREF
  __int128 v16; // [rsp+30h] [rbp-20h]
  char *v17; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]
  __int64 v19; // [rsp+60h] [rbp+10h] BYREF
  void *v20; // [rsp+68h] [rbp+18h] BYREF

  MarkCurrentThreadAsEcoQoS();
  while ( 1 )
  {
    if ( WaitForSingleObject(this[33], 0xFFFFFFFF) == -1 )
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x16D,
               (unsigned int)"pcshell\\base\\whesvc\\lib\\orchestrator.cpp",
               v13);
    if ( !WaitForSingleObject(this[11], 0) )
      break;
    v15 = 0;
    v16 = 0;
    v17 = 0;
    v2 = operator new(0x10u);
    v2[1] = 0;
    *(_QWORD *)&v15 = v2;
    *v2 = &v15;
    if ( _Mtx_lock((_Mtx_t)(this + 21)) )
    {
      std::_Throw_Cpp_error(5);
      __debugbreak();
    }
    if ( *((_DWORD *)this + 61) == 0x7FFFFFFF )
    {
      *((_DWORD *)this + 61) = 2147483646;
      std::_Throw_Cpp_error(6);
      __debugbreak();
    }
    v3 = this + 44;
    if ( &v15 != (__int128 *)(this + 44) )
    {
      v4 = v15;
      *(_QWORD *)&v15 = *v3;
      v5 = (_QWORD *)v15;
      *v3 = v4;
      if ( v5 )
        *v5 = &v15;
      if ( *v3 )
        *(_QWORD *)*v3 = v3;
      v6 = (void *)*((_QWORD *)&v15 + 1);
      *((_QWORD *)&v15 + 1) = this[45];
      this[45] = v6;
      v7 = (void *)v16;
      *(_QWORD *)&v16 = this[46];
      this[46] = v7;
      v8 = (void *)*((_QWORD *)&v16 + 1);
      *((_QWORD *)&v16 + 1) = this[47];
      this[47] = v8;
      v9 = v17;
      v17 = (char *)this[48];
      this[48] = v9;
    }
    _Mtx_unlock((_Mtx_t)(this + 21));
    while ( WaitForSingleObject(this[11], 0) && v17 )
    {
      v10 = BYTE8(v16) & 1;
      v11 = *(_QWORD *)(*((_QWORD *)&v15 + 1) + 8 * ((v16 - 1) & (*((_QWORD *)&v16 + 1) >> 1)));
      v12 = *(_QWORD *)(v11 + 8 * v10);
      *(_QWORD *)(v11 + 8 * v10) = 0;
      std::unique_ptr<OrchestratorSingleton::HeavyModuleData>::~unique_ptr<OrchestratorSingleton::HeavyModuleData>((void **)(*(_QWORD *)(*((_QWORD *)&v15 + 1) + 8 * ((v16 - 1) & (*((_QWORD *)&v16 + 1) >> 1))) + 8LL * (BYTE8(v16) & 1)));
      if ( --v17 )
        ++*((_QWORD *)&v16 + 1);
      else
        *((_QWORD *)&v16 + 1) = 0;
      v20 = 0;
      v19 = v12;
      OrchestratorSingleton::MaintainHeavyModuleState(this, &v19);
      std::unique_ptr<OrchestratorSingleton::HeavyModuleData>::~unique_ptr<OrchestratorSingleton::HeavyModuleData>(&v20);
    }
    std::deque<std::unique_ptr<OrchestratorSingleton::HeavyModuleData>>::~deque<std::unique_ptr<OrchestratorSingleton::HeavyModuleData>>((__int64)&v15);
  }
  return 0;
}

```

## disassembly

```asm
0x180014398  mov     [rsp-8+arg_10], rbx
0x18001439d  mov     [rsp-8+arg_18], rdi
0x1800143a2  push    rbp
0x1800143a3  mov     rbp, rsp
0x1800143a6  sub     rsp, 50h
0x1800143aa  mov     rbx, rcx
0x1800143ad  call    ?MarkCurrentThreadAsEcoQoS@@YAXXZ; MarkCurrentThreadAsEcoQoS(void)
0x1800143b2  jmp     loc_180014560
0x1800143b7  xor     edx, edx; dwMilliseconds
0x1800143b9  mov     rcx, [rbx+58h]; hHandle
0x1800143bd  call    cs:__imp_WaitForSingleObject
0x1800143c3  test    eax, eax
0x1800143c5  jz      loc_1800145BE
0x1800143cb  xorps   xmm0, xmm0
0x1800143ce  movdqu  [rbp+var_30], xmm0
0x1800143d3  xorps   xmm1, xmm1
0x1800143d6  movdqu  [rbp+var_20], xmm1
0x1800143db  mov     [rbp+var_10], 0
0x1800143e3  mov     ecx, 10h; Size
0x1800143e8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800143ed  mov     qword ptr [rax+8], 0
0x1800143f5  mov     qword ptr [rbp+var_30], rax
0x1800143f9  lea     rcx, [rbp+var_30]
0x1800143fd  mov     [rax], rcx
0x180014400  lea     rdi, [rbx+0A8h]
0x180014407  mov     rcx, rdi; _Mtx_t
0x18001440a  call    cs:__imp__Mtx_lock
0x180014410  test    eax, eax
0x180014412  jnz     loc_1800145B2
0x180014418  cmp     dword ptr [rdi+4Ch], 7FFFFFFFh
0x18001441f  jz      loc_18001459F
0x180014425  lea     r8, [rbx+160h]
0x18001442c  lea     rax, [rbp+var_30]
0x180014430  cmp     rax, r8
0x180014433  jz      short loc_18001449A
0x180014435  mov     rax, qword ptr [rbp+var_30]
0x180014439  mov     rcx, [r8]
0x18001443c  mov     qword ptr [rbp+var_30], rcx
0x180014440  mov     [r8], rax
0x180014443  test    rcx, rcx
0x180014446  jz      short loc_18001444F
0x180014448  lea     rax, [rbp+var_30]
0x18001444c  mov     [rcx], rax
0x18001444f  mov     rax, [r8]
0x180014452  test    rax, rax
0x180014455  jz      short loc_18001445A
0x180014457  mov     [rax], r8
0x18001445a  mov     rcx, qword ptr [rbp+var_30+8]
0x18001445e  mov     rax, [r8+8]
0x180014462  mov     qword ptr [rbp+var_30+8], rax
0x180014466  mov     [r8+8], rcx
0x18001446a  mov     rdx, qword ptr [rbp+var_20]
0x18001446e  mov     rax, [r8+10h]
0x180014472  mov     qword ptr [rbp+var_20], rax
0x180014476  mov     [r8+10h], rdx
0x18001447a  mov     rdx, qword ptr [rbp+var_20+8]
0x18001447e  mov     rax, [r8+18h]
0x180014482  mov     qword ptr [rbp+var_20+8], rax
0x180014486  mov     [r8+18h], rdx
0x18001448a  mov     rdx, [rbp+var_10]
0x18001448e  mov     rax, [r8+20h]
0x180014492  mov     [rbp+var_10], rax
0x180014496  mov     [r8+20h], rdx
0x18001449a  mov     rcx, rdi; _Mtx_t
0x18001449d  call    cs:__imp__Mtx_unlock
0x1800144a3  xor     edx, edx; dwMilliseconds
0x1800144a5  mov     rcx, [rbx+58h]; hHandle
0x1800144a9  call    cs:__imp_WaitForSingleObject
0x1800144af  test    eax, eax
0x1800144b1  jz      loc_180014557
0x1800144b7  cmp     [rbp+var_10], 0
0x1800144bc  jz      loc_180014557
0x1800144c2  mov     rdx, qword ptr [rbp+var_20+8]
0x1800144c6  mov     rcx, rdx
0x1800144c9  shr     rcx, 1
0x1800144cc  mov     rax, qword ptr [rbp+var_20]
0x1800144d0  dec     rax
0x1800144d3  and     rcx, rax
0x1800144d6  and     edx, 1
0x1800144d9  mov     rax, qword ptr [rbp+var_30+8]
0x1800144dd  mov     rcx, [rax+rcx*8]
0x1800144e1  mov     rdi, [rcx+rdx*8]
0x1800144e5  mov     qword ptr [rcx+rdx*8], 0
0x1800144ed  mov     rdx, qword ptr [rbp+var_20+8]
0x1800144f1  mov     rcx, rdx
0x1800144f4  shr     rcx, 1
0x1800144f7  mov     rax, qword ptr [rbp+var_20]
0x1800144fb  dec     rax
0x1800144fe  and     rcx, rax
0x180014501  and     edx, 1
0x180014504  mov     rax, qword ptr [rbp+var_30+8]
0x180014508  mov     rcx, [rax+rcx*8]
0x18001450c  lea     rcx, [rcx+rdx*8]
0x180014510  call    ??1?$unique_ptr@UHeavyModuleData@OrchestratorSingleton@@U?$default_delete@UHeavyModuleData@OrchestratorSingleton@@@std@@@std@@QEAA@XZ; std::unique_ptr<OrchestratorSingleton::HeavyModuleData>::~unique_ptr<OrchestratorSingleton::HeavyModuleData>(void)
0x180014515  mov     rax, [rbp+var_10]
0x180014519  sub     rax, 1
0x18001451d  mov     [rbp+var_10], rax
0x180014521  jnz     short loc_18001452D
0x180014523  mov     qword ptr [rbp+var_20+8], 0
0x18001452b  jmp     short loc_180014531
0x18001452d  inc     qword ptr [rbp+var_20+8]
0x180014531  mov     [rbp+arg_8], 0
0x180014539  mov     [rbp+arg_0], rdi
0x18001453d  lea     rdx, [rbp+arg_0]
0x180014541  mov     rcx, rbx
0x180014544  call    ?MaintainHeavyModuleState@OrchestratorSingleton@@AEAAXV?$unique_ptr@UHeavyModuleData@OrchestratorSingleton@@U?$default_delete@UHeavyModuleData@OrchestratorSingleton@@@std@@@std@@@Z; OrchestratorSingleton::MaintainHeavyModuleState(std::unique_ptr<OrchestratorSingleton::HeavyModuleData>)
0x180014549  lea     rcx, [rbp+arg_8]
0x18001454d  call    ??1?$unique_ptr@UHeavyModuleData@OrchestratorSingleton@@U?$default_delete@UHeavyModuleData@OrchestratorSingleton@@@std@@@std@@QEAA@XZ; std::unique_ptr<OrchestratorSingleton::HeavyModuleData>::~unique_ptr<OrchestratorSingleton::HeavyModuleData>(void)
0x180014552  jmp     loc_1800144A3
0x180014557  lea     rcx, [rbp+var_30]
0x18001455b  call    ??1?$deque@V?$unique_ptr@UHeavyModuleData@OrchestratorSingleton@@U?$default_delete@UHeavyModuleData@OrchestratorSingleton@@@std@@@std@@V?$allocator@V?$unique_ptr@UHeavyModuleData@OrchestratorSingleton@@U?$default_delete@UHeavyModuleData@OrchestratorSingleton@@@std@@@std@@@2@@std@@QEAA@XZ; std::deque<std::unique_ptr<OrchestratorSingleton::HeavyModuleData>>::~deque<std::unique_ptr<OrchestratorSingleton::HeavyModuleData>>(void)
0x180014560  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180014563  mov     rcx, [rbx+108h]; hHandle
0x18001456a  call    cs:__imp_WaitForSingleObject
0x180014570  cmp     eax, 0FFFFFFFFh
0x180014573  jnz     loc_1800143B7
0x180014579  mov     rcx, [rbp+8]; this
0x18001457d  lea     r8, aPcshellBaseWhe_0; "pcshell\\base\\whesvc\\lib\\orchestrato"...
0x180014584  mov     edx, 16Dh; void *
0x180014589  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001458e  nop
0x18001458f  mov     rbx, [rsp+50h+arg_10]
0x180014594  mov     rdi, [rsp+50h+arg_18]
0x180014599  add     rsp, 50h
0x18001459d  pop     rbp
0x18001459e  retn
0x18001459f  mov     dword ptr [rdi+4Ch], 7FFFFFFEh
0x1800145a6  mov     ecx, 6
0x1800145ab  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800145b1  int     3; Trap to Debugger
0x1800145b2  mov     ecx, 5
0x1800145b7  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800145bd  int     3; Trap to Debugger
0x1800145be  xor     eax, eax
0x1800145c0  jmp     short loc_18001458F
```
