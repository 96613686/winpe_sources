# OrchestratorSingleton::QueueHeavyModule(std::unique_ptr<WindiagModuleWrapper,std::default_delete<WindiagModuleWrapper>>,char const *)

- ea: `0x180014f94`
- end: `0x1800152f2`
- name: `?QueueHeavyModule@OrchestratorSingleton@@QEAAJV?$unique_ptr@VWindiagModuleWrapper@@U?$default_delete@VWindiagModuleWrapper@@@std@@@std@@PEBD@Z`
- size: `862`
- prototype: `__int64 __fastcall(__int64, void **, _BYTE *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x1800152f8`

## callees

- `0x180003304`
- `0x18000370c`
- `0x180003be4`
- `0x180004581`
- `0x180009044`
- `0x18000fc50`
- `0x180011578`
- `0x180011904`
- `0x180014f94`
- `0x180016d44`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800151c2`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800151c2`
- `msvcp_win!_Mtx_unlock` at `0x1800151b0`
- `msvcp_win!_Mtx_unlock` at `0x1800151b0`
- `msvcp_win!_Mtx_lock` at `0x1800150e2`
- `msvcp_win!_Mtx_lock` at `0x1800150e2`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800150f1`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001510d`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800150f1`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001510d`

## pseudocode

```c
__int64 __fastcall OrchestratorSingleton::QueueHeavyModule(__int64 a1, void **a2, _BYTE *a3)
{
  char *v6; // rax
  __int64 v7; // r8
  void **v8; // rdi
  char **v9; // rdi
  void *v10; // rax
  char **v11; // rsi
  char *v12; // rcx
  void **v13; // rcx
  size_t v14; // rsi
  void *v15; // r14
  struct _Mtx_internal_imp_t *v16; // r14
  int v17; // eax
  _QWORD *v18; // rsi
  __int64 v19; // rdx
  __int64 v20; // r13
  __int64 v21; // r12
  char **v22; // rdi
  char *v23; // rcx
  __int64 result; // rax
  char **v25; // rdi
  char *v26; // rcx
  char *v27; // rcx
  int v28; // [rsp+20h] [rbp-38h]
  int v29; // [rsp+20h] [rbp-38h]
  int v30; // [rsp+20h] [rbp-38h]
  __int64 v31; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  void **v35; // [rsp+78h] [rbp+20h] BYREF

  v6 = (char *)operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = (void **)v6;
  if ( v6 )
  {
    *(_QWORD *)v6 = 0;
    *(_OWORD *)(v6 + 8) = 0;
    *((_QWORD *)v6 + 3) = 0;
    *((_QWORD *)v6 + 4) = 15;
    v6[8] = 0;
  }
  else
  {
    v8 = 0;
  }
  v35 = v8;
  if ( !v8 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE0,
      (unsigned int)"pcshell\\base\\whesvc\\lib\\orchestrator.cpp",
      (const char *)0x8007000ELL,
      v30);
    std::unique_ptr<OrchestratorSingleton::HeavyModuleData>::~unique_ptr<OrchestratorSingleton::HeavyModuleData>((void **)&v35);
    v9 = (char **)*a2;
    goto LABEL_44;
  }
  v10 = *a2;
  *a2 = 0;
  v11 = (char **)*v8;
  *v8 = v10;
  if ( v11 )
  {
    std::string::~string(v11 + 7);
    std::string::~string(v11 + 3);
    v12 = v11[1];
    if ( v12 )
      operator delete(v12);
    if ( *v11 )
      operator delete(*v11);
    operator delete(v11);
  }
  v13 = v8 + 1;
  v14 = -1;
  do
    ++v14;
  while ( a3[v14] );
  if ( v14 > (unsigned __int64)v8[4] )
  {
    std::string::_Reallocate_for<_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *>(v13, v14, v7, a3);
  }
  else
  {
    if ( (unsigned __int64)v8[4] <= 0xF )
      v15 = v8 + 1;
    else
      v15 = *v13;
    v8[3] = (void *)v14;
    memmove_0(v15, a3, v14);
    *((_BYTE *)v15 + v14) = 0;
  }
  v16 = (struct _Mtx_internal_imp_t *)(a1 + 168);
  v17 = _Mtx_lock((_Mtx_t)(a1 + 168));
  try
  {
    if ( v17 )
      std::_Throw_Cpp_error(5);
    if ( *(_DWORD *)(a1 + 244) == 0x7FFFFFFF )
    {
      *(_DWORD *)(a1 + 244) = 2147483646;
      std::_Throw_Cpp_error(6);
    }
    v18 = (_QWORD *)(a1 + 352);
    if ( ((*(_BYTE *)(a1 + 376) + (unsigned __int8)*(_QWORD *)(a1 + 384)) & 1) == 0
      && *(_QWORD *)(a1 + 368) <= (unsigned __int64)(*(_QWORD *)(a1 + 384) + 2LL) >> 1 )
    {
      std::deque<std::unique_ptr<OrchestratorSingleton::HeavyModuleData>>::_Growmap((_QWORD *)(a1 + 352));
    }
    v19 = *(_QWORD *)(a1 + 368);
    *(_QWORD *)(a1 + 376) &= 2 * v19 - 1;
    v20 = *(_QWORD *)(a1 + 384) + *(_QWORD *)(a1 + 376);
    v31 = (v18[4] + v18[3]) >> 1;
    v21 = v31 & (v19 - 1);
    if ( !*(_QWORD *)(v18[1] + 8 * v21) )
      *(_QWORD *)(v18[1] + 8 * v21) = operator new(0x10u);
    v35 = 0;
    *(_QWORD *)(*(_QWORD *)(v18[1] + 8 * (v31 & (v18[2] - 1LL))) + 8 * (v20 & 1)) = v8;
    ++v18[4];
    _Mtx_unlock(v16);
    SetEvent(*(HANDLE *)(a1 + 264));
    std::unique_ptr<OrchestratorSingleton::HeavyModuleData>::~unique_ptr<OrchestratorSingleton::HeavyModuleData>((void **)&v35);
    v22 = (char **)*a2;
    if ( *a2 )
    {
      std::string::~string(v22 + 7);
      std::string::~string(v22 + 3);
      v23 = v22[1];
      if ( v23 )
        operator delete(v23);
      if ( *v22 )
        operator delete(*v22);
      operator delete(v22);
    }
    result = 0;
  }
  catch ( std::bad_alloc )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF1,
      (unsigned int)"pcshell\\base\\whesvc\\lib\\orchestrator.cpp",
      (const char *)0x8007000ELL,
      v29);
    std::unique_ptr<OrchestratorSingleton::HeavyModuleData>::~unique_ptr<OrchestratorSingleton::HeavyModuleData>((void **)&v35);
    v9 = (char **)*a2;
LABEL_44:
    if ( v9 )
    {
      std::string::~string(v9 + 7);
      std::string::~string(v9 + 3);
      v27 = v9[1];
      if ( v27 )
        operator delete(v27);
      if ( *v9 )
        operator delete(*v9);
      operator delete(v9);
    }
    return 2147942414LL;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF5,
      (unsigned int)"pcshell\\base\\whesvc\\lib\\orchestrator.cpp",
      (const char *)0x80004005LL,
      v28);
    std::unique_ptr<OrchestratorSingleton::HeavyModuleData>::~unique_ptr<OrchestratorSingleton::HeavyModuleData>((void **)&v35);
    v25 = (char **)*a2;
    if ( *a2 )
    {
      std::string::~string(v25 + 7);
      std::string::~string(v25 + 3);
      v26 = v25[1];
      if ( v26 )
        operator delete(v26);
      if ( *v25 )
        operator delete(*v25);
      operator delete(v25);
    }
    return 2147500037LL;
  }
  return result;
}

```

## disassembly

```asm
0x180014f94  mov     [rsp+arg_10], rsi
0x180014f99  mov     [rsp+arg_8], rdx
0x180014f9e  mov     [rsp+arg_0], rcx
0x180014fa3  push    rdi
0x180014fa4  push    r12
0x180014fa6  push    r13
0x180014fa8  push    r14
0x180014faa  push    r15
0x180014fac  sub     rsp, 30h
0x180014fb0  mov     r12, r8
0x180014fb3  mov     r15, rdx
0x180014fb6  mov     r13, rcx
0x180014fb9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180014fc0  mov     ecx, 28h ; '('; unsigned __int64
0x180014fc5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180014fca  mov     rdi, rax
0x180014fcd  test    rax, rax
0x180014fd0  jz      short loc_180014FF6
0x180014fd2  mov     qword ptr [rax], 0
0x180014fd9  xorps   xmm0, xmm0
0x180014fdc  movups  xmmword ptr [rax+8], xmm0
0x180014fe0  mov     qword ptr [rax+18h], 0
0x180014fe8  mov     qword ptr [rax+20h], 0Fh
0x180014ff0  mov     byte ptr [rax+8], 0
0x180014ff4  jmp     short loc_180014FF8
0x180014ff6  xor     edi, edi
0x180014ff8  mov     [rsp+58h+arg_18], rdi
0x180014ffd  test    rdi, rdi
0x180015000  jnz     short loc_180015032
0x180015002  mov     rcx, [rsp+58h]; this
0x180015007  mov     r9d, 8007000Eh; char *
0x18001500d  lea     r8, aPcshellBaseWhe_0; "pcshell\\base\\whesvc\\lib\\orchestrato"...
0x180015014  mov     edx, 0E0h; void *
0x180015019  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001501e  nop
0x18001501f  lea     rcx, [rsp+58h+arg_18]
0x180015024  call    ??1?$unique_ptr@UHeavyModuleData@OrchestratorSingleton@@U?$default_delete@UHeavyModuleData@OrchestratorSingleton@@@std@@@std@@QEAA@XZ; std::unique_ptr<OrchestratorSingleton::HeavyModuleData>::~unique_ptr<OrchestratorSingleton::HeavyModuleData>(void)
0x180015029  nop
0x18001502a  mov     rdi, [r15]
0x18001502d  jmp     loc_180015295
0x180015032  mov     rax, [r15]
0x180015035  mov     qword ptr [r15], 0
0x18001503c  mov     rsi, [rdi]
0x18001503f  mov     [rdi], rax
0x180015042  test    rsi, rsi
0x180015045  jz      short loc_180015087
0x180015047  lea     rcx, [rsi+38h]
0x18001504b  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180015050  lea     rcx, [rsi+18h]
0x180015054  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180015059  mov     rcx, [rsi+8]; void *
0x18001505d  test    rcx, rcx
0x180015060  jz      short loc_180015067
0x180015062  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180015067  cmp     qword ptr [rsi], 0
0x18001506b  jz      short loc_18001507A
0x18001506d  mov     edx, 18h; unsigned __int64
0x180015072  mov     rcx, [rsi]; void *
0x180015075  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001507a  mov     edx, 58h ; 'X'; unsigned __int64
0x18001507f  mov     rcx, rsi; void *
0x180015082  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180015087  lea     rcx, [rdi+8]
0x18001508b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001508f  inc     rsi
0x180015092  cmp     byte ptr [r12+rsi], 0
0x180015097  jnz     short loc_18001508F
0x180015099  cmp     rsi, [rcx+18h]
0x18001509d  ja      short loc_1800150C7
0x18001509f  cmp     qword ptr [rcx+18h], 0Fh
0x1800150a4  jbe     short loc_1800150AB
0x1800150a6  mov     r14, [rcx]
0x1800150a9  jmp     short loc_1800150AE
0x1800150ab  mov     r14, rcx
0x1800150ae  mov     [rcx+10h], rsi
0x1800150b2  mov     r8, rsi; Size
0x1800150b5  mov     rdx, r12; Src
0x1800150b8  mov     rcx, r14; void *
0x1800150bb  call    memmove_0
0x1800150c0  mov     byte ptr [rsi+r14], 0
0x1800150c5  jmp     short loc_1800150D3
0x1800150c7  mov     r9, r12
0x1800150ca  mov     rdx, rsi
0x1800150cd  call    ??$_Reallocate_for@V_lambda_a132b9f505f015b07a26cb4edca31da2_@@PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_a132b9f505f015b07a26cb4edca31da2_@@PEBD@Z; std::string::_Reallocate_for<_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *>(unsigned __int64,_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *)
0x1800150d2  nop
0x1800150d3  lea     r14, [r13+0A8h]
0x1800150da  mov     [rsp+58h+var_30], r14
0x1800150df  mov     rcx, r14; _Mtx_t
0x1800150e2  call    cs:__imp__Mtx_lock
0x1800150e8  test    eax, eax
0x1800150ea  jz      short loc_1800150F7
0x1800150ec  mov     ecx, 5
0x1800150f1  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800150f7  mov     eax, [r14+4Ch]
0x1800150fb  cmp     eax, 7FFFFFFFh
0x180015100  jnz     short loc_180015114
0x180015102  dec     eax
0x180015104  mov     [r14+4Ch], eax
0x180015108  mov     ecx, 6
0x18001510d  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180015113  nop
0x180015114  lea     rsi, [r13+160h]
0x18001511b  mov     rcx, [rsi+20h]
0x18001511f  mov     al, cl
0x180015121  add     al, [rsi+18h]
0x180015124  test    al, 1
0x180015126  jnz     short loc_18001513D
0x180015128  lea     rax, [rcx+2]
0x18001512c  shr     rax, 1
0x18001512f  cmp     [rsi+10h], rax
0x180015133  ja      short loc_18001513D
0x180015135  mov     rcx, rsi
0x180015138  call    ?_Growmap@?$deque@V?$unique_ptr@UHeavyModuleData@OrchestratorSingleton@@U?$default_delete@UHeavyModuleData@OrchestratorSingleton@@@std@@@std@@V?$allocator@V?$unique_ptr@UHeavyModuleData@OrchestratorSingleton@@U?$default_delete@UHeavyModuleData@OrchestratorSingleton@@@std@@@std@@@2@@std@@AEAAX_K@Z; std::deque<std::unique_ptr<OrchestratorSingleton::HeavyModuleData>>::_Growmap(unsigned __int64)
0x18001513d  mov     rdx, [rsi+10h]
0x180015141  lea     rax, ds:0FFFFFFFFFFFFFFFFh[rdx*2]
0x180015149  and     [rsi+18h], rax
0x18001514d  mov     r13, [rsi+18h]
0x180015151  add     r13, [rsi+20h]
0x180015155  mov     rax, r13
0x180015158  shr     rax, 1
0x18001515b  mov     [rsp+58h+var_38], rax
0x180015160  lea     r12, [rdx-1]
0x180015164  and     r12, rax
0x180015167  mov     rax, [rsi+8]
0x18001516b  cmp     qword ptr [rax+r12*8], 0
0x180015170  jnz     short loc_180015184
0x180015172  mov     ecx, 10h; Size
0x180015177  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001517c  mov     rcx, [rsi+8]
0x180015180  mov     [rcx+r12*8], rax
0x180015184  mov     [rsp+58h+arg_18], 0
0x18001518d  mov     rdx, [rsi+10h]
0x180015191  dec     rdx
0x180015194  and     rdx, [rsp+58h+var_38]
0x180015199  mov     rax, [rsi+8]
0x18001519d  and     r13d, 1
0x1800151a1  mov     rax, [rax+rdx*8]
0x1800151a5  mov     [rax+r13*8], rdi
0x1800151a9  inc     qword ptr [rsi+20h]
0x1800151ad  mov     rcx, r14; _Mtx_t
0x1800151b0  call    cs:__imp__Mtx_unlock
0x1800151b6  mov     rcx, [rsp+58h+arg_0]
0x1800151bb  mov     rcx, [rcx+108h]; hEvent
0x1800151c2  call    cs:__imp_SetEvent
0x1800151c8  nop
0x1800151c9  lea     rcx, [rsp+58h+arg_18]
0x1800151ce  call    ??1?$unique_ptr@UHeavyModuleData@OrchestratorSingleton@@U?$default_delete@UHeavyModuleData@OrchestratorSingleton@@@std@@@std@@QEAA@XZ; std::unique_ptr<OrchestratorSingleton::HeavyModuleData>::~unique_ptr<OrchestratorSingleton::HeavyModuleData>(void)
0x1800151d3  nop
0x1800151d4  mov     rdi, [r15]
0x1800151d7  test    rdi, rdi
0x1800151da  jz      short loc_18001521C
0x1800151dc  lea     rcx, [rdi+38h]
0x1800151e0  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800151e5  lea     rcx, [rdi+18h]
0x1800151e9  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800151ee  mov     rcx, [rdi+8]; void *
0x1800151f2  test    rcx, rcx
0x1800151f5  jz      short loc_1800151FC
0x1800151f7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800151fc  cmp     qword ptr [rdi], 0
0x180015200  jz      short loc_18001520F
0x180015202  mov     edx, 18h; unsigned __int64
0x180015207  mov     rcx, [rdi]; void *
0x18001520a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001520f  mov     edx, 58h ; 'X'; unsigned __int64
0x180015214  mov     rcx, rdi; void *
0x180015217  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001521c  xor     eax, eax
0x18001521e  jmp     loc_1800152DF
0x180015223  lea     rcx, [rsp+58h+arg_18]
0x180015228  call    ??1?$unique_ptr@UHeavyModuleData@OrchestratorSingleton@@U?$default_delete@UHeavyModuleData@OrchestratorSingleton@@@std@@@std@@QEAA@XZ; std::unique_ptr<OrchestratorSingleton::HeavyModuleData>::~unique_ptr<OrchestratorSingleton::HeavyModuleData>(void)
0x18001522d  nop
0x18001522e  mov     rax, [rsp+58h+arg_8]
0x180015233  mov     rdi, [rax]
0x180015236  test    rdi, rdi
0x180015239  jz      short loc_18001527B
0x18001523b  lea     rcx, [rdi+38h]
0x18001523f  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180015244  lea     rcx, [rdi+18h]
0x180015248  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18001524d  mov     rcx, [rdi+8]; void *
0x180015251  test    rcx, rcx
0x180015254  jz      short loc_18001525B
0x180015256  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001525b  cmp     qword ptr [rdi], 0
0x18001525f  jz      short loc_18001526E
0x180015261  mov     edx, 18h; unsigned __int64
0x180015266  mov     rcx, [rdi]; void *
0x180015269  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001526e  mov     edx, 58h ; 'X'; unsigned __int64
0x180015273  mov     rcx, rdi; void *
0x180015276  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001527b  mov     eax, 80004005h
0x180015280  jmp     short loc_1800152DF
0x180015282  lea     rcx, [rsp+58h+arg_18]
0x180015287  call    ??1?$unique_ptr@UHeavyModuleData@OrchestratorSingleton@@U?$default_delete@UHeavyModuleData@OrchestratorSingleton@@@std@@@std@@QEAA@XZ; std::unique_ptr<OrchestratorSingleton::HeavyModuleData>::~unique_ptr<OrchestratorSingleton::HeavyModuleData>(void)
0x18001528c  nop
0x18001528d  mov     rax, [rsp+58h+arg_8]
0x180015292  mov     rdi, [rax]
0x180015295  test    rdi, rdi
0x180015298  jz      short loc_1800152DA
0x18001529a  lea     rcx, [rdi+38h]
0x18001529e  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800152a3  lea     rcx, [rdi+18h]
0x1800152a7  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800152ac  mov     rcx, [rdi+8]; void *
0x1800152b0  test    rcx, rcx
0x1800152b3  jz      short loc_1800152BA
0x1800152b5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800152ba  cmp     qword ptr [rdi], 0
0x1800152be  jz      short loc_1800152CD
0x1800152c0  mov     edx, 18h; unsigned __int64
0x1800152c5  mov     rcx, [rdi]; void *
0x1800152c8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800152cd  mov     edx, 58h ; 'X'; unsigned __int64
0x1800152d2  mov     rcx, rdi; void *
0x1800152d5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800152da  mov     eax, 8007000Eh
0x1800152df  mov     rsi, [rsp+58h+arg_10]
0x1800152e4  add     rsp, 30h
0x1800152e8  pop     r15
0x1800152ea  pop     r14
0x1800152ec  pop     r13
0x1800152ee  pop     r12
0x1800152f0  pop     rdi
0x1800152f1  retn
```
