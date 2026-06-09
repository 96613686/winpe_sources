# _anonymous_namespace_::etw_open_trace_common__lambda_65c80388bb66a242eddb2a902b106acb___

- ea: `0x1800462cc`
- end: `0x180046704`
- name: `_anonymous_namespace_::etw_open_trace_common__lambda_65c80388bb66a242eddb2a902b106acb___`
- size: `1080`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x18004bc5c`

## callees

- `0x180004510`
- `0x18000491c`
- `0x1800054e4`
- `0x180005508`
- `0x180005520`
- `0x18003af08`
- `0x180041564`
- `0x1800426d4`
- `0x180044a38`
- `0x1800462cc`
- `0x180046f30`
- `0x180047470`
- `0x180047730`
- `0x18004890c`
- `0x180048df8`
- `0x180049674`
- `0x18007917c`
- `0x18009d010`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800466bd`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800466bd`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18004654a`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18004654a`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x1800465e3`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x1800465e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004643c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004643c`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x180046428`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x180046428`

## string_xrefs

- `0x1800466ce`: `etw_open_trace_common`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall anonymous_namespace_::etw_open_trace_common__lambda_65c80388bb66a242eddb2a902b106acb___(
        __int64 a1,
        windiag *a2,
        _QWORD *a3,
        char **a4,
        _BYTE *a5)
{
  __int64 v8; // rax
  __int64 v9; // r9
  __int64 v10; // r8
  __int64 v11; // rdx
  _QWORD *v12; // rdi
  __int64 v13; // rax
  __int64 v14; // rcx
  volatile signed __int32 *v15; // rbx
  char *v16; // rcx
  ULONG v17; // eax
  TRACEHANDLE v18; // rsi
  DWORD LastError; // eax
  unsigned __int64 v20; // rdx
  __int64 v21; // rbx
  volatile signed __int32 *v22; // rbx
  __int64 v23; // r14
  _QWORD *v24; // rax
  windiag *v25; // rdi
  void *v26; // r8
  struct lua_State *v27; // rcx
  int v28; // r8d
  int v29; // eax
  volatile signed __int32 *v30; // rbx
  struct lua_State *v32[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v33; // [rsp+40h] [rbp-C0h]
  _QWORD *v34; // [rsp+48h] [rbp-B8h]
  _BYTE v35[24]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD *v36; // [rsp+68h] [rbp-98h]
  struct lua_State *v37; // [rsp+70h] [rbp-90h]
  int v38; // [rsp+78h] [rbp-88h]
  int v39; // [rsp+7Ch] [rbp-84h]
  windiag *v40; // [rsp+90h] [rbp-70h]
  char **v41; // [rsp+98h] [rbp-68h]
  _QWORD *v42; // [rsp+A0h] [rbp-60h]
  __int64 v43; // [rsp+A8h] [rbp-58h] BYREF
  volatile signed __int32 *v44; // [rsp+B0h] [rbp-50h]
  _QWORD *v45; // [rsp+B8h] [rbp-48h]
  char **v46; // [rsp+C0h] [rbp-40h]
  _BYTE *v47; // [rsp+C8h] [rbp-38h]
  struct _EVENT_TRACE_LOGFILEW Logfile; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v49; // [rsp+290h] [rbp+190h] BYREF
  unsigned __int64 v50; // [rsp+2A0h] [rbp+1A0h]
  __int64 v51; // [rsp+2A8h] [rbp+1A8h]
  _BYTE pExceptionObject[1072]; // [rsp+2B0h] [rbp+1B0h] BYREF

  v41 = a4;
  v40 = a2;
  v45 = a3;
  v46 = a4;
  v47 = a5;
  v33 = (__int64)operator new(0x1E0u);
  v8 = etw_event_filter_t::etw_event_filter_t(v35, a5 + 16);
  LOBYTE(v9) = a5[3];
  LOBYTE(v10) = a5[2];
  LOBYTE(v11) = *a5;
  v12 = (_QWORD *)decoder_context::decoder_context(v33, v11, v10, v9, v8);
  v34 = v12;
  v13 = a3[1];
  if ( v13 )
    _InterlockedIncrement((volatile signed __int32 *)(v13 + 8));
  v14 = a3[1];
  *v12 = *a3;
  v15 = (volatile signed __int32 *)v12[1];
  v12[1] = v14;
  if ( v15 )
  {
    if ( _InterlockedExchangeAdd(v15 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
      if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
    }
  }
  memset_0(&Logfile, 0, sizeof(Logfile));
  v16 = *a4;
  Logfile.LoggerName = (LPWSTR)&(*a4)[*((unsigned int *)*a4 + 29)];
  Logfile.LogFileName = (LPWSTR)&v16[*((unsigned int *)v16 + 28)];
  v17 = *((_DWORD *)v16 + 16) | 0x10000000;
  Logfile.LogFileMode = v17;
  if ( a5[1] )
    Logfile.LogFileMode = v17 | 0x1000;
  Logfile.EventCallback = (PEVENT_CALLBACK)anonymous_namespace_::etw_event_record_callback;
  Logfile.BufferCallback = (PEVENT_TRACE_BUFFER_CALLBACKW)lambda_c86b7ba222448e1bb0d7ba49dcdbda76_::_lambda_invoker_cdecl___EVENT_TRACE_LOGFILEW_;
  Logfile.Context = v12;
  v18 = OpenTraceW(&Logfile);
  v33 = v18;
  if ( v18 == -1 )
  {
    LastError = GetLastError();
    if ( LastError )
    {
LABEL_37:
      windiag::system_exception::system_exception(
        (windiag::system_exception *)pExceptionObject,
        LastError,
        0,
        "[%s:%d] failed; ",
        "etw_open_trace_common",
        541);
      throw (windiag::system_exception *)pExceptionObject;
    }
  }
  v49 = 0;
  v50 = 0;
  v51 = 7;
  LOWORD(v49) = 0;
  if ( Logfile.LoggerName && *Logfile.LoggerName )
  {
    v20 = -1;
    do
      ++v20;
    while ( Logfile.LoggerName[v20] );
    if ( v20 > 7 )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(&v49, v20);
    }
    else
    {
      v50 = v20;
      v21 = 2 * v20;
      memmove_0(&v49, Logfile.LoggerName, 2 * v20);
      *(_WORD *)((char *)&v49 + v21) = 0;
    }
  }
  std::make_shared<etw_trace_state_t,std::wstring>(&v43, &v49);
  v22 = v44;
  if ( v44 )
    _InterlockedIncrement(v44 + 2);
  v23 = v43;
  *(_QWORD *)v35 = v43;
  *(_QWORD *)&v35[8] = v22;
  *(_QWORD *)&v35[16] = v18;
  v34 = 0;
  v36 = v12;
  v24 = operator new(0x20u);
  *v24 = v23;
  v24[1] = v22;
  *(_OWORD *)v35 = 0;
  v24[2] = v18;
  v36 = 0;
  v24[3] = v12;
  v42 = v24;
  v32[0] = (struct lua_State *)_o__beginthreadex(
                                 0,
                                 0,
                                 std::thread::_Invoke_std::tuple__lambda_e4aee9a13df23212e389919ed62ed785____0_,
                                 v24,
                                 0,
                                 &v32[1]);
  if ( !v32[0] )
  {
    LODWORD(v32[1]) = 0;
    std::_Throw_Cpp_error(6);
    goto LABEL_37;
  }
  lambda_e4aee9a13df23212e389919ed62ed785_::__lambda_e4aee9a13df23212e389919ed62ed785_(v35);
  v25 = v40;
  windiag::set_lua_etw_thread(v40, v32[0], v26);
  *(_QWORD *)v35 = v25;
  *(_OWORD *)&v35[8] = 0;
  if ( v22 )
    _InterlockedIncrement(v22 + 2);
  *(_QWORD *)&v35[8] = v23;
  *(_QWORD *)&v35[16] = v22;
  v33 = -1;
  v36 = (_QWORD *)v18;
  v27 = v32[0];
  v28 = (int)v32[1];
  v29 = HIDWORD(v32[1]);
  *(_OWORD *)v32 = 0;
  v37 = v27;
  v38 = v28;
  v39 = v29;
  std::shared_ptr_etw_trace_state_t_::shared_ptr_etw_trace_state_t__etw_trace_state_t__lambda_1151c0638e9fb2361fcb9f5d519a6b3a__0_(
    a1,
    v23,
    v35);
  if ( LODWORD(v32[1]) )
    _o_terminate();
  if ( v22 )
  {
    if ( _InterlockedExchangeAdd(v22 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v22)(v22);
      if ( _InterlockedExchangeAdd(v22 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
    }
  }
  std::wstring::~wstring((char **)&v49);
  v30 = (volatile signed __int32 *)a3[1];
  if ( v30 )
  {
    if ( _InterlockedExchangeAdd(v30 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v30)(v30);
      if ( _InterlockedExchangeAdd(v30 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v30 + 8LL))(v30);
    }
  }
  std::vector<char>::~vector<char>(v41);
  if ( a5[32] )
    std::_Tree<std::_Tmap_traits<_GUID,etw_filter_provider_t,std::less<_GUID>,std::allocator<std::pair<_GUID const,etw_filter_provider_t>>,1>>::~_Tree<std::_Tmap_traits<_GUID,etw_filter_provider_t,std::less<_GUID>,std::allocator<std::pair<_GUID const,etw_filter_provider_t>>,1>>(a5 + 16);
  return a1;
}

```

## disassembly

```asm
0x1800462cc  push    rbp
0x1800462ce  push    rbx
0x1800462cf  push    rsi
0x1800462d0  push    rdi
0x1800462d1  push    r12
0x1800462d3  push    r13
0x1800462d5  push    r14
0x1800462d7  push    r15
0x1800462d9  lea     rbp, [rsp-5F8h]
0x1800462e1  sub     rsp, 6F8h
0x1800462e8  mov     rax, cs:__security_cookie
0x1800462ef  xor     rax, rsp
0x1800462f2  mov     [rbp+630h+var_50], rax
0x1800462f9  mov     r14, r9
0x1800462fc  mov     [rbp+630h+var_698], r9
0x180046300  mov     r15, r8
0x180046303  mov     [rbp+630h+var_6A0], rdx
0x180046307  mov     r13, rcx
0x18004630a  mov     [rsp+730h+var_6F0], rcx
0x18004630f  mov     [rbp+630h+var_678], r8
0x180046313  mov     [rbp+630h+var_670], r9
0x180046317  mov     rsi, [rbp+630h+arg_20]
0x18004631e  mov     [rbp+630h+var_668], rsi
0x180046322  lea     r12, [rsi+10h]
0x180046326  mov     ecx, 1E0h; Size
0x18004632b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180046330  mov     rbx, rax
0x180046333  mov     [rsp+730h+var_6F0], rax
0x180046338  mov     rdx, r12
0x18004633b  lea     rcx, [rsp+730h+var_6E0]
0x180046340  call    ??0etw_event_filter_t@@QEAA@$$QEAU0@@Z; etw_event_filter_t::etw_event_filter_t(etw_event_filter_t &&)
0x180046345  mov     [rsp+730h+var_710], rax
0x18004634a  mov     r9b, [rsi+3]
0x18004634e  mov     r8b, [rsi+2]
0x180046352  mov     dl, [rsi]
0x180046354  mov     rcx, rbx
0x180046357  call    ??0decoder_context@@QEAA@_N00Uetw_event_filter_t@@@Z; decoder_context::decoder_context(bool,bool,bool,etw_event_filter_t)
0x18004635c  mov     rdi, rax
0x18004635f  mov     [rsp+730h+var_6E8], rax
0x180046364  mov     rax, [r15+8]
0x180046368  test    rax, rax
0x18004636b  jz      short loc_180046371
0x18004636d  lock inc dword ptr [rax+8]
0x180046371  mov     rcx, [r15+8]
0x180046375  mov     rax, [r15]
0x180046378  mov     [rdi], rax
0x18004637b  mov     rbx, [rdi+8]
0x18004637f  mov     [rdi+8], rcx
0x180046383  test    rbx, rbx
0x180046386  jz      short loc_1800463BF
0x180046388  or      eax, 0FFFFFFFFh
0x18004638b  lock xadd [rbx+8], eax
0x180046390  cmp     eax, 1
0x180046393  jnz     short loc_1800463BF
0x180046395  mov     rax, [rbx]
0x180046398  mov     rcx, rbx
0x18004639b  mov     rax, [rax]
0x18004639e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800463a3  or      eax, 0FFFFFFFFh
0x1800463a6  lock xadd [rbx+0Ch], eax
0x1800463ab  cmp     eax, 1
0x1800463ae  jnz     short loc_1800463BF
0x1800463b0  mov     rax, [rbx]
0x1800463b3  mov     rcx, rbx
0x1800463b6  mov     rax, [rax+8]
0x1800463ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800463bf  xor     edx, edx; Val
0x1800463c1  mov     r8d, 1C0h; Size
0x1800463c7  lea     rcx, [rbp+630h+Logfile]; void *
0x1800463cb  call    memset_0
0x1800463d0  mov     rcx, [r14]
0x1800463d3  mov     eax, [rcx+74h]
0x1800463d6  add     rax, rcx
0x1800463d9  mov     [rbp+630h+Logfile.LoggerName], rax
0x1800463dd  mov     eax, [rcx+70h]
0x1800463e0  add     rax, rcx
0x1800463e3  mov     [rbp+630h+Logfile.LogFileName], rax
0x1800463e7  mov     eax, [rcx+40h]
0x1800463ea  bts     eax, 1Ch
0x1800463ee  mov     dword ptr [rbp+630h+Logfile.1Ch], eax
0x1800463f1  xor     r14d, r14d
0x1800463f4  cmp     [rsi+1], r14b
0x1800463f8  jz      short loc_180046401
0x1800463fa  bts     eax, 0Ch
0x1800463fe  mov     dword ptr [rbp+630h+Logfile.1Ch], eax
0x180046401  lea     rax, _anonymous_namespace___etw_event_record_callback
0x180046408  mov     qword ptr [rbp+630h+Logfile.1A8h], rax
0x18004640f  lea     rax, _lambda_c86b7ba222448e1bb0d7ba49dcdbda76____lambda_invoker_cdecl___EVENT_TRACE_LOGFILEW_
0x180046416  mov     [rbp+630h+Logfile.BufferCallback], rax
0x18004641d  mov     [rbp+630h+Logfile.Context], rdi
0x180046424  lea     rcx, [rbp+630h+Logfile]; Logfile
0x180046428  call    cs:__imp_OpenTraceW
0x18004642e  mov     rsi, rax
0x180046431  mov     [rsp+730h+var_6F0], rax
0x180046436  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004643a  jnz     short loc_18004644A
0x18004643c  call    cs:__imp_GetLastError
0x180046442  test    eax, eax
0x180046444  jnz     loc_1800466C4
0x18004644a  xorps   xmm0, xmm0
0x18004644d  movups  [rbp+630h+var_4A0], xmm0
0x180046454  mov     [rbp+630h+var_490], r14
0x18004645b  mov     [rbp+630h+var_488], 7
0x180046466  mov     word ptr [rbp+630h+var_4A0], r14w
0x18004646e  mov     r9, [rbp+630h+Logfile.LoggerName]
0x180046472  test    r9, r9
0x180046475  jz      short loc_1800464BE
0x180046477  cmp     [r9], r14w
0x18004647b  jz      short loc_1800464BE
0x18004647d  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180046481  inc     rdx
0x180046484  cmp     [r9+rdx*2], r14w
0x180046489  jnz     short loc_180046481
0x18004648b  lea     rcx, [rbp+630h+var_4A0]; void *
0x180046492  cmp     rdx, 7
0x180046496  ja      short loc_1800464B9
0x180046498  mov     [rbp+630h+var_490], rdx
0x18004649f  lea     rbx, [rdx+rdx]
0x1800464a3  mov     r8, rbx; Size
0x1800464a6  mov     rdx, r9; Src
0x1800464a9  call    memmove_0
0x1800464ae  mov     word ptr [rbp+rbx+630h+var_4A0], r14w
0x1800464b7  jmp     short loc_1800464BE
0x1800464b9  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x1800464be  lea     rdx, [rbp+630h+var_4A0]
0x1800464c5  lea     rcx, [rbp+630h+var_688]
0x1800464c9  call    ??$make_shared@Uetw_trace_state_t@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@YA?AV?$shared_ptr@Uetw_trace_state_t@@@0@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::make_shared<etw_trace_state_t,std::wstring>(std::wstring &&)
0x1800464ce  nop
0x1800464cf  mov     rbx, [rbp+630h+var_680]
0x1800464d3  test    rbx, rbx
0x1800464d6  jz      short loc_1800464DC
0x1800464d8  lock inc dword ptr [rbx+8]
0x1800464dc  mov     r14, [rbp+630h+var_688]
0x1800464e0  mov     qword ptr [rsp+730h+var_6E0], r14
0x1800464e5  mov     qword ptr [rsp+730h+var_6E0+8], rbx
0x1800464ea  mov     [rsp+730h+var_6D0], rsi
0x1800464ef  mov     [rsp+730h+var_6E8], 0
0x1800464f8  mov     [rsp+730h+var_6C8], rdi
0x1800464fd  mov     ecx, 20h ; ' '; Size
0x180046502  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180046507  mov     [rax], r14
0x18004650a  mov     [rax+8], rbx
0x18004650e  xorps   xmm0, xmm0
0x180046511  movdqu  [rsp+730h+var_6E0], xmm0
0x180046517  mov     [rax+10h], rsi
0x18004651b  mov     [rsp+730h+var_6C8], 0
0x180046524  mov     [rax+18h], rdi
0x180046528  mov     [rbp+630h+var_690], rax
0x18004652c  lea     rcx, [rsp+730h+var_700+8]
0x180046531  mov     [rsp+730h+var_708], rcx
0x180046536  xor     edi, edi
0x180046538  mov     dword ptr [rsp+730h+var_710], edi
0x18004653c  mov     r9, rax
0x18004653f  lea     r8, std__thread___Invoke_std__tuple__lambda_e4aee9a13df23212e389919ed62ed785____0_
0x180046546  xor     edx, edx
0x180046548  xor     ecx, ecx
0x18004654a  call    cs:__imp__o__beginthreadex
0x180046550  mov     [rsp+730h+var_700], rax
0x180046555  test    rax, rax
0x180046558  jz      loc_1800466B4
0x18004655e  lea     rcx, [rsp+730h+var_6E0]
0x180046563  call    _lambda_e4aee9a13df23212e389919ed62ed785_____lambda_e4aee9a13df23212e389919ed62ed785_
0x180046568  mov     rdx, [rsp+730h+var_700]; struct lua_State *
0x18004656d  mov     rdi, [rbp+630h+var_6A0]
0x180046571  mov     rcx, rdi; this
0x180046574  call    ?set_lua_etw_thread@windiag@@YAXPEAUlua_State@@PEAX@Z; windiag::set_lua_etw_thread(lua_State *,void *)
0x180046579  mov     qword ptr [rsp+730h+var_6E0], rdi
0x18004657e  xorps   xmm0, xmm0
0x180046581  movdqu  [rsp+730h+var_6E0+8], xmm0
0x180046587  xor     edi, edi
0x180046589  test    rbx, rbx
0x18004658c  jz      short loc_180046592
0x18004658e  lock inc dword ptr [rbx+8]
0x180046592  mov     qword ptr [rsp+730h+var_6E0+8], r14
0x180046597  mov     [rsp+730h+var_6D0], rbx
0x18004659c  mov     [rsp+730h+var_6F0], 0FFFFFFFFFFFFFFFFh
0x1800465a5  mov     [rsp+730h+var_6C8], rsi
0x1800465aa  mov     rcx, [rsp+730h+var_700]
0x1800465af  mov     r8d, dword ptr [rsp+730h+var_700+8]
0x1800465b4  mov     eax, dword ptr [rsp+730h+var_700+0Ch]
0x1800465b8  movdqa  xmmword ptr [rsp+730h+var_700], xmm0
0x1800465be  mov     [rsp+730h+var_6C0], rcx
0x1800465c3  mov     [rsp+730h+var_6B8], r8d
0x1800465c8  mov     [rsp+730h+var_6B4], eax
0x1800465cc  lea     r8, [rsp+730h+var_6E0]
0x1800465d1  mov     rdx, r14
0x1800465d4  mov     rcx, r13
0x1800465d7  call    std__shared_ptr_etw_trace_state_t___shared_ptr_etw_trace_state_t__etw_trace_state_t__lambda_1151c0638e9fb2361fcb9f5d519a6b3a__0_
0x1800465dc  nop
0x1800465dd  cmp     dword ptr [rsp+730h+var_700+8], edi
0x1800465e1  jz      short loc_1800465EA
0x1800465e3  call    cs:__imp__o_terminate
0x1800465e9  nop
0x1800465ea  test    rbx, rbx
0x1800465ed  jz      short loc_180046627
0x1800465ef  or      eax, 0FFFFFFFFh
0x1800465f2  lock xadd [rbx+8], eax
0x1800465f7  cmp     eax, 1
0x1800465fa  jnz     short loc_180046627
0x1800465fc  mov     rax, [rbx]
0x1800465ff  mov     rcx, rbx
0x180046602  mov     rax, [rax]
0x180046605  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004660a  or      eax, 0FFFFFFFFh
0x18004660d  lock xadd [rbx+0Ch], eax
0x180046612  cmp     eax, 1
0x180046615  jnz     short loc_180046627
0x180046617  mov     rax, [rbx]
0x18004661a  mov     rcx, rbx
0x18004661d  mov     rax, [rax+8]
0x180046621  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046626  nop
0x180046627  lea     rcx, [rbp+630h+var_4A0]
0x18004662e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180046633  nop
0x180046634  mov     rbx, [r15+8]
0x180046638  test    rbx, rbx
0x18004663b  jz      short loc_180046675
0x18004663d  or      eax, 0FFFFFFFFh
0x180046640  lock xadd [rbx+8], eax
0x180046645  cmp     eax, 1
0x180046648  jnz     short loc_180046675
0x18004664a  mov     rax, [rbx]
0x18004664d  mov     rcx, rbx
0x180046650  mov     rax, [rax]
0x180046653  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046658  or      eax, 0FFFFFFFFh
0x18004665b  lock xadd [rbx+0Ch], eax
0x180046660  cmp     eax, 1
0x180046663  jnz     short loc_180046675
0x180046665  mov     rax, [rbx]
0x180046668  mov     rcx, rbx
0x18004666b  mov     rax, [rax+8]
0x18004666f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046674  nop
0x180046675  mov     rcx, [rbp+630h+var_698]
0x180046679  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x18004667e  nop
0x18004667f  cmp     [r12+10h], dil
0x180046684  jz      short loc_18004668E
0x180046686  mov     rcx, r12
0x180046689  call    ??1?$_Tree@V?$_Tmap_traits@U_GUID@@Uetw_filter_provider_t@@U?$less@U_GUID@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@Uetw_filter_provider_t@@@std@@@4@$00@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<_GUID,etw_filter_provider_t,std::less<_GUID>,std::allocator<std::pair<_GUID const,etw_filter_provider_t>>,1>>::~_Tree<std::_Tmap_traits<_GUID,etw_filter_provider_t,std::less<_GUID>,std::allocator<std::pair<_GUID const,etw_filter_provider_t>>,1>>(void)
0x18004668e  mov     rax, r13
0x180046691  mov     rcx, [rbp+630h+var_50]
0x180046698  xor     rcx, rsp; StackCookie
0x18004669b  call    __security_check_cookie
0x1800466a0  add     rsp, 6F8h
0x1800466a7  pop     r15
0x1800466a9  pop     r14
0x1800466ab  pop     r13
0x1800466ad  pop     r12
0x1800466af  pop     rdi
0x1800466b0  pop     rsi
0x1800466b1  pop     rbx
0x1800466b2  pop     rbp
0x1800466b3  retn
0x1800466b4  mov     dword ptr [rsp+730h+var_700+8], edi
0x1800466b8  mov     ecx, 6
0x1800466bd  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800466c3  nop
0x1800466c4  mov     edx, eax; __int64
0x1800466c6  mov     dword ptr [rsp+730h+var_708], 21Dh
0x1800466ce  lea     rax, aEtwOpenTraceCo; "etw_open_trace_common"
0x1800466d5  mov     [rsp+730h+var_710], rax
0x1800466da  lea     r9, aSDFailed; "[%s:%d] failed; "
0x1800466e1  xor     r8d, r8d; void *
0x1800466e4  lea     rcx, [rbp+630h+pExceptionObject]; this
0x1800466eb  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x1800466f0  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x1800466f7  lea     rcx, [rbp+630h+pExceptionObject]; pExceptionObject
0x1800466fe  call    _CxxThrowException_0
```
