# OrchestratorSingleton::CleanupThread(void)

- ea: `0x180012434`
- end: `0x1800125d9`
- name: `?CleanupThread@OrchestratorSingleton@@AEAAKXZ`
- size: `421`
- prototype: `__int64 __fastcall(char *this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800125e0`

## callees

- `0x180011a6c`
- `0x180012434`
- `0x180014bf4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180012498`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180012515`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180012543`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180012498`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180012515`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180012543`
- `msvcp_win!_Cnd_wait` at `0x1800124b3`
- `msvcp_win!_Cnd_wait` at `0x1800124b3`
- `msvcp_win!_Mtx_unlock` at `0x180012503`
- `msvcp_win!_Mtx_unlock` at `0x180012566`
- `msvcp_win!_Mtx_unlock` at `0x1800125a5`
- `msvcp_win!_Mtx_unlock` at `0x180012503`
- `msvcp_win!_Mtx_unlock` at `0x180012566`
- `msvcp_win!_Mtx_unlock` at `0x1800125a5`
- `msvcp_win!_Mtx_lock` at `0x180012461`
- `msvcp_win!_Mtx_lock` at `0x180012527`
- `msvcp_win!_Mtx_lock` at `0x180012588`
- `msvcp_win!_Mtx_lock` at `0x180012461`
- `msvcp_win!_Mtx_lock` at `0x180012527`
- `msvcp_win!_Mtx_lock` at `0x180012588`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001259b`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800125d2`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001259b`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800125d2`

## pseudocode

```c
__int64 __fastcall OrchestratorSingleton::CleanupThread(char *this)
{
  HANDLE *v2; // r15
  __int128 *v3; // rsi
  __int64 v4; // rdi
  __int64 v5; // r14
  __int64 v6; // rax
  __int128 v8; // [rsp+20h] [rbp-20h] BYREF
  __int64 v9; // [rsp+30h] [rbp-10h]

  MarkCurrentThreadAsEcoQoS();
  v8 = 0;
  v9 = 0;
  if ( _Mtx_lock((_Mtx_t)this) )
  {
LABEL_21:
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  v2 = (HANDLE *)(this + 88);
  while ( 1 )
  {
    if ( *((_DWORD *)this + 19) == 0x7FFFFFFF )
    {
LABEL_23:
      *((_DWORD *)this + 19) = 2147483646;
      std::_Throw_Cpp_error(6);
      JUMPOUT(0x1800125D8LL);
    }
    v3 = (__int128 *)(this + 392);
    while ( *(_QWORD *)v3 == *((_QWORD *)this + 50) && (WaitForSingleObject(*v2, 0) || *((_QWORD *)this + 38)) )
    {
      _Cnd_wait((_Cnd_t)(this + 96), (_Mtx_t)this);
      v2 = (HANDLE *)(this + 88);
    }
    if ( v3 == &v8 )
    {
      v5 = *((_QWORD *)&v8 + 1);
      v4 = v8;
    }
    else
    {
      v4 = *(_QWORD *)v3;
      *(_QWORD *)v3 = 0;
      *(_QWORD *)&v8 = v4;
      v5 = *((_QWORD *)this + 50);
      *((_QWORD *)this + 50) = 0;
      *((_QWORD *)&v8 + 1) = v5;
      v6 = *((_QWORD *)this + 51);
      *((_QWORD *)this + 51) = 0;
      v9 = v6;
    }
    _Mtx_unlock((_Mtx_t)this);
    while ( v4 != v5 )
    {
      WaitForSingleObject(*(HANDLE *)(*(_QWORD *)v4 + 8LL), 0xFFFFFFFF);
      v4 += 8;
    }
    if ( _Mtx_lock((_Mtx_t)this) )
      goto LABEL_21;
    if ( *((_DWORD *)this + 19) == 0x7FFFFFFF )
      goto LABEL_23;
    if ( !WaitForSingleObject(*v2, 0) && !*((_QWORD *)this + 38) && *(_QWORD *)v3 == *((_QWORD *)this + 50) )
      break;
    _Mtx_unlock((_Mtx_t)this);
    std::vector<std::unique_ptr<OrchestratorSingleton::ModuleThreadData>>::~vector<std::unique_ptr<OrchestratorSingleton::ModuleThreadData>>((__int64)&v8);
    v8 = 0;
    v9 = 0;
    if ( _Mtx_lock((_Mtx_t)this) )
      goto LABEL_21;
  }
  _Mtx_unlock((_Mtx_t)this);
  std::vector<std::unique_ptr<OrchestratorSingleton::ModuleThreadData>>::~vector<std::unique_ptr<OrchestratorSingleton::ModuleThreadData>>((__int64)&v8);
  return 0;
}

```

## disassembly

```asm
0x180012434  push    rbp
0x180012436  push    rbx
0x180012437  push    rsi
0x180012438  push    rdi
0x180012439  push    r12
0x18001243b  push    r14
0x18001243d  push    r15
0x18001243f  mov     rbp, rsp
0x180012442  sub     rsp, 40h
0x180012446  mov     rbx, rcx
0x180012449  call    ?MarkCurrentThreadAsEcoQoS@@YAXXZ; MarkCurrentThreadAsEcoQoS(void)
0x18001244e  xorps   xmm0, xmm0
0x180012451  movdqu  [rbp+var_20], xmm0
0x180012456  mov     [rbp+var_10], 0
0x18001245e  mov     rcx, rbx; _Mtx_t
0x180012461  call    cs:__imp__Mtx_lock
0x180012467  test    eax, eax
0x180012469  jnz     loc_180012596
0x18001246f  lea     r15, [rbx+58h]
0x180012473  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x18001247a  jz      loc_1800125C5
0x180012480  lea     rsi, [rbx+188h]
0x180012487  mov     rax, [rbx+190h]
0x18001248e  cmp     [rsi], rax
0x180012491  jnz     short loc_1800124BF
0x180012493  xor     edx, edx; dwMilliseconds
0x180012495  mov     rcx, [r15]; hHandle
0x180012498  call    cs:__imp_WaitForSingleObject
0x18001249e  test    eax, eax
0x1800124a0  jnz     short loc_1800124AC
0x1800124a2  cmp     qword ptr [rbx+130h], 0
0x1800124aa  jz      short loc_1800124BF
0x1800124ac  lea     rcx, [rbx+60h]; _Cnd_t
0x1800124b0  mov     rdx, rbx; _Mtx_t
0x1800124b3  call    cs:__imp__Cnd_wait
0x1800124b9  lea     r15, [rbx+58h]
0x1800124bd  jmp     short loc_180012487
0x1800124bf  lea     rax, [rbp+var_20]
0x1800124c3  cmp     rsi, rax
0x1800124c6  jz      short loc_1800124F8
0x1800124c8  mov     rdi, [rsi]
0x1800124cb  mov     qword ptr [rsi], 0
0x1800124d2  mov     qword ptr [rbp+var_20], rdi
0x1800124d6  mov     r14, [rsi+8]
0x1800124da  mov     qword ptr [rsi+8], 0
0x1800124e2  mov     qword ptr [rbp+var_20+8], r14
0x1800124e6  mov     rax, [rsi+10h]
0x1800124ea  mov     qword ptr [rsi+10h], 0
0x1800124f2  mov     [rbp+var_10], rax
0x1800124f6  jmp     short loc_180012500
0x1800124f8  mov     r14, qword ptr [rbp+var_20+8]
0x1800124fc  mov     rdi, qword ptr [rbp+var_20]
0x180012500  mov     rcx, rbx; _Mtx_t
0x180012503  call    cs:__imp__Mtx_unlock
0x180012509  jmp     short loc_18001251F
0x18001250b  mov     rcx, [rdi]
0x18001250e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180012511  mov     rcx, [rcx+8]; hHandle
0x180012515  call    cs:__imp_WaitForSingleObject
0x18001251b  add     rdi, 8
0x18001251f  cmp     rdi, r14
0x180012522  jnz     short loc_18001250B
0x180012524  mov     rcx, rbx; _Mtx_t
0x180012527  call    cs:__imp__Mtx_lock
0x18001252d  test    eax, eax
0x18001252f  jnz     short loc_180012596
0x180012531  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x180012538  jz      loc_1800125C5
0x18001253e  xor     edx, edx; dwMilliseconds
0x180012540  mov     rcx, [r15]; hHandle
0x180012543  call    cs:__imp_WaitForSingleObject
0x180012549  test    eax, eax
0x18001254b  jnz     short loc_180012563
0x18001254d  cmp     qword ptr [rbx+130h], 0
0x180012555  jnz     short loc_180012563
0x180012557  mov     rax, [rbx+190h]
0x18001255e  cmp     [rsi], rax
0x180012561  jz      short loc_1800125A2
0x180012563  mov     rcx, rbx; _Mtx_t
0x180012566  call    cs:__imp__Mtx_unlock
0x18001256c  lea     rcx, [rbp+var_20]
0x180012570  call    ??1?$vector@V?$unique_ptr@UModuleThreadData@OrchestratorSingleton@@U?$default_delete@UModuleThreadData@OrchestratorSingleton@@@std@@@std@@V?$allocator@V?$unique_ptr@UModuleThreadData@OrchestratorSingleton@@U?$default_delete@UModuleThreadData@OrchestratorSingleton@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<OrchestratorSingleton::ModuleThreadData>>::~vector<std::unique_ptr<OrchestratorSingleton::ModuleThreadData>>(void)
0x180012575  xorps   xmm0, xmm0
0x180012578  movdqu  [rbp+var_20], xmm0
0x18001257d  mov     [rbp+var_10], 0
0x180012585  mov     rcx, rbx; _Mtx_t
0x180012588  call    cs:__imp__Mtx_lock
0x18001258e  test    eax, eax
0x180012590  jz      loc_180012473
0x180012596  mov     ecx, 5
0x18001259b  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800125a1  int     3; Trap to Debugger
0x1800125a2  mov     rcx, rbx; _Mtx_t
0x1800125a5  call    cs:__imp__Mtx_unlock
0x1800125ab  lea     rcx, [rbp+var_20]
0x1800125af  call    ??1?$vector@V?$unique_ptr@UModuleThreadData@OrchestratorSingleton@@U?$default_delete@UModuleThreadData@OrchestratorSingleton@@@std@@@std@@V?$allocator@V?$unique_ptr@UModuleThreadData@OrchestratorSingleton@@U?$default_delete@UModuleThreadData@OrchestratorSingleton@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<OrchestratorSingleton::ModuleThreadData>>::~vector<std::unique_ptr<OrchestratorSingleton::ModuleThreadData>>(void)
0x1800125b4  xor     eax, eax
0x1800125b6  add     rsp, 40h
0x1800125ba  pop     r15
0x1800125bc  pop     r14
0x1800125be  pop     r12
0x1800125c0  pop     rdi
0x1800125c1  pop     rsi
0x1800125c2  pop     rbx
0x1800125c3  pop     rbp
0x1800125c4  retn
0x1800125c5  mov     eax, 7FFFFFFEh
0x1800125ca  mov     [rbx+4Ch], eax
0x1800125cd  mov     ecx, 6
0x1800125d2  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
