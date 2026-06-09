# _anonymous_namespace_::etw_open_trace_common__lambda_2128fb03336d189f0f73a287a84f3162___

- ea: `0x180045e94`
- end: `0x1800462c5`
- name: `_anonymous_namespace_::etw_open_trace_common__lambda_2128fb03336d189f0f73a287a84f3162___`
- size: `1073`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x18004dd44`

## callees

- `0x180004510`
- `0x18000491c`
- `0x1800054e4`
- `0x180005508`
- `0x180005520`
- `0x18003af08`
- `0x180041564`
- `0x1800427c4`
- `0x180044a38`
- `0x180045e94`
- `0x180046f30`
- `0x180047470`
- `0x180047730`
- `0x18004890c`
- `0x180048df8`
- `0x18007917c`
- `0x18009d010`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18004627e`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18004627e`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18004610c`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18004610c`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x1800461a8`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x1800461a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045ffc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045ffc`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x180045fe8`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x180045fe8`

## string_xrefs

- `0x18004628f`: `etw_open_trace_common`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall anonymous_namespace_::etw_open_trace_common__lambda_2128fb03336d189f0f73a287a84f3162___(
        __int64 a1,
        windiag *a2,
        _QWORD *a3,
        __int64 a4,
        _BYTE *a5)
{
  __int64 v7; // rax
  __int64 v8; // r9
  __int64 v9; // r8
  __int64 v10; // rdx
  _QWORD *v11; // rsi
  __int64 v12; // rax
  __int64 v13; // rcx
  volatile signed __int32 *v14; // rbx
  WCHAR *v15; // rcx
  TRACEHANDLE v16; // rdi
  __int64 v17; // r8
  DWORD LastError; // eax
  unsigned __int64 v19; // rdx
  __int64 v20; // rbx
  volatile signed __int32 *v21; // rbx
  __int64 v22; // r14
  _QWORD *v23; // rax
  windiag *v24; // rsi
  void *v25; // r8
  struct lua_State *v26; // rcx
  int v27; // r8d
  int v28; // eax
  __int64 v29; // rdi
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
  __int64 v41; // [rsp+98h] [rbp-68h]
  _QWORD *v42; // [rsp+A0h] [rbp-60h]
  __int64 v43; // [rsp+A8h] [rbp-58h] BYREF
  volatile signed __int32 *v44; // [rsp+B0h] [rbp-50h]
  _QWORD *v45; // [rsp+B8h] [rbp-48h]
  _BYTE *v46; // [rsp+C0h] [rbp-40h]
  __int64 v47; // [rsp+C8h] [rbp-38h]
  _EVENT_TRACE_LOGFILEW Logfile; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v49; // [rsp+290h] [rbp+190h] BYREF
  unsigned __int64 v50; // [rsp+2A0h] [rbp+1A0h]
  __int64 v51; // [rsp+2A8h] [rbp+1A8h]
  _BYTE pExceptionObject[1072]; // [rsp+2B0h] [rbp+1B0h] BYREF

  v40 = a2;
  v41 = a1;
  v45 = a3;
  v47 = a4;
  v46 = a5;
  v33 = (__int64)operator new(0x1E0u);
  v7 = etw_event_filter_t::etw_event_filter_t(v35, a5 + 16);
  LOBYTE(v8) = a5[3];
  LOBYTE(v9) = a5[2];
  LOBYTE(v10) = *a5;
  v11 = (_QWORD *)decoder_context::decoder_context(v33, v10, v9, v8, v7);
  v34 = v11;
  v12 = a3[1];
  if ( v12 )
    _InterlockedIncrement((volatile signed __int32 *)(v12 + 8));
  v13 = a3[1];
  *v11 = *a3;
  v14 = (volatile signed __int32 *)v11[1];
  v11[1] = v13;
  if ( v14 )
  {
    if ( _InterlockedExchangeAdd(v14 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
      if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
    }
  }
  memset_0(&Logfile, 0, sizeof(Logfile));
  v15 = (WCHAR *)a4;
  if ( *(_QWORD *)(a4 + 24) > 7u )
    v15 = *(WCHAR **)a4;
  Logfile.LogFileName = v15;
  Logfile.LogFileMode = 0x10000000;
  if ( a5[1] )
    Logfile.LogFileMode = 268439552;
  Logfile.EventCallback = (PEVENT_CALLBACK)anonymous_namespace_::etw_event_record_callback;
  Logfile.BufferCallback = (PEVENT_TRACE_BUFFER_CALLBACKW)lambda_c86b7ba222448e1bb0d7ba49dcdbda76_::_lambda_invoker_cdecl___EVENT_TRACE_LOGFILEW_;
  Logfile.Context = v11;
  v16 = OpenTraceW(&Logfile);
  v33 = v16;
  if ( v16 == -1 )
  {
    LastError = GetLastError();
    if ( LastError )
    {
LABEL_39:
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
    v19 = -1;
    do
      ++v19;
    while ( Logfile.LoggerName[v19] );
    if ( v19 > 7 )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        &v49,
        v19,
        v17,
        Logfile.LoggerName);
    }
    else
    {
      v50 = v19;
      v20 = 2 * v19;
      memmove_0(&v49, Logfile.LoggerName, 2 * v19);
      *(_WORD *)((char *)&v49 + v20) = 0;
    }
  }
  std::make_shared<etw_trace_state_t,std::wstring>(&v43, &v49);
  v21 = v44;
  if ( v44 )
    _InterlockedIncrement(v44 + 2);
  v22 = v43;
  *(_QWORD *)v35 = v43;
  *(_QWORD *)&v35[8] = v21;
  *(_QWORD *)&v35[16] = v16;
  v34 = 0;
  v36 = v11;
  v23 = operator new(0x20u);
  *v23 = v22;
  v23[1] = v21;
  *(_OWORD *)v35 = 0;
  v23[2] = v16;
  v36 = 0;
  v23[3] = v11;
  v42 = v23;
  v32[0] = (struct lua_State *)_o__beginthreadex(
                                 0,
                                 0,
                                 std::thread::_Invoke_std::tuple__lambda_e4aee9a13df23212e389919ed62ed785____0_,
                                 v23,
                                 0,
                                 &v32[1]);
  if ( !v32[0] )
  {
    LODWORD(v32[1]) = 0;
    std::_Throw_Cpp_error(6);
    goto LABEL_39;
  }
  lambda_e4aee9a13df23212e389919ed62ed785_::__lambda_e4aee9a13df23212e389919ed62ed785_(v35);
  v24 = v40;
  windiag::set_lua_etw_thread(v40, v32[0], v25);
  *(_QWORD *)v35 = v24;
  *(_OWORD *)&v35[8] = 0;
  if ( v21 )
    _InterlockedIncrement(v21 + 2);
  *(_QWORD *)&v35[8] = v22;
  *(_QWORD *)&v35[16] = v21;
  v33 = -1;
  v36 = (_QWORD *)v16;
  v26 = v32[0];
  v27 = (int)v32[1];
  v28 = HIDWORD(v32[1]);
  *(_OWORD *)v32 = 0;
  v37 = v26;
  v38 = v27;
  v39 = v28;
  v29 = v41;
  std::shared_ptr_etw_trace_state_t_::shared_ptr_etw_trace_state_t__etw_trace_state_t__lambda_7aeed00cc4298c22832b70bc0bbfba4a__0_(
    v41,
    v22,
    v35);
  if ( LODWORD(v32[1]) )
    _o_terminate();
  if ( v21 )
  {
    if ( _InterlockedExchangeAdd(v21 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v21)(v21);
      if ( _InterlockedExchangeAdd(v21 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
    }
  }
  std::wstring::~wstring(&v49);
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
  std::wstring::~wstring(a4);
  if ( a5[32] )
    std::_Tree<std::_Tmap_traits<_GUID,etw_filter_provider_t,std::less<_GUID>,std::allocator<std::pair<_GUID const,etw_filter_provider_t>>,1>>::~_Tree<std::_Tmap_traits<_GUID,etw_filter_provider_t,std::less<_GUID>,std::allocator<std::pair<_GUID const,etw_filter_provider_t>>,1>>(a5 + 16);
  return v29;
}

```

## disassembly

```asm
0x180045e94  push    rbp
0x180045e96  push    rbx
0x180045e97  push    rsi
0x180045e98  push    rdi
0x180045e99  push    r12
0x180045e9b  push    r13
0x180045e9d  push    r14
0x180045e9f  push    r15
0x180045ea1  lea     rbp, [rsp-5F8h]
0x180045ea9  sub     rsp, 6F8h
0x180045eb0  mov     rax, cs:__security_cookie
0x180045eb7  xor     rax, rsp
0x180045eba  mov     [rbp+630h+var_50], rax
0x180045ec1  mov     r15, r9
0x180045ec4  mov     r12, r8
0x180045ec7  mov     [rbp+630h+var_6A0], rdx
0x180045ecb  mov     [rbp+630h+var_698], rcx
0x180045ecf  mov     [rsp+730h+var_6F0], rcx
0x180045ed4  mov     [rbp+630h+var_678], r8
0x180045ed8  mov     [rbp+630h+var_668], r9
0x180045edc  mov     rdi, [rbp+630h+arg_20]
0x180045ee3  mov     [rbp+630h+var_670], rdi
0x180045ee7  xor     r14d, r14d
0x180045eea  lea     r13, [rdi+10h]
0x180045eee  mov     ecx, 1E0h; Size
0x180045ef3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180045ef8  mov     rbx, rax
0x180045efb  mov     [rsp+730h+var_6F0], rax
0x180045f00  mov     rdx, r13
0x180045f03  lea     rcx, [rsp+730h+var_6E0]
0x180045f08  call    ??0etw_event_filter_t@@QEAA@$$QEAU0@@Z; etw_event_filter_t::etw_event_filter_t(etw_event_filter_t &&)
0x180045f0d  mov     [rsp+730h+var_710], rax
0x180045f12  mov     r9b, [rdi+3]
0x180045f16  mov     r8b, [rdi+2]
0x180045f1a  mov     dl, [rdi]
0x180045f1c  mov     rcx, rbx
0x180045f1f  call    ??0decoder_context@@QEAA@_N00Uetw_event_filter_t@@@Z; decoder_context::decoder_context(bool,bool,bool,etw_event_filter_t)
0x180045f24  mov     rsi, rax
0x180045f27  mov     [rsp+730h+var_6E8], rax
0x180045f2c  mov     rax, [r12+8]
0x180045f31  test    rax, rax
0x180045f34  jz      short loc_180045F3A
0x180045f36  lock inc dword ptr [rax+8]
0x180045f3a  mov     rcx, [r12+8]
0x180045f3f  mov     rax, [r12]
0x180045f43  mov     [rsi], rax
0x180045f46  mov     rbx, [rsi+8]
0x180045f4a  mov     [rsi+8], rcx
0x180045f4e  test    rbx, rbx
0x180045f51  jz      short loc_180045F8A
0x180045f53  or      eax, 0FFFFFFFFh
0x180045f56  lock xadd [rbx+8], eax
0x180045f5b  cmp     eax, 1
0x180045f5e  jnz     short loc_180045F8A
0x180045f60  mov     rax, [rbx]
0x180045f63  mov     rcx, rbx
0x180045f66  mov     rax, [rax]
0x180045f69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045f6e  or      eax, 0FFFFFFFFh
0x180045f71  lock xadd [rbx+0Ch], eax
0x180045f76  cmp     eax, 1
0x180045f79  jnz     short loc_180045F8A
0x180045f7b  mov     rax, [rbx]
0x180045f7e  mov     rcx, rbx
0x180045f81  mov     rax, [rax+8]
0x180045f85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045f8a  xor     edx, edx; Val
0x180045f8c  mov     r8d, 1C0h; Size
0x180045f92  lea     rcx, [rbp+630h+Logfile]; void *
0x180045f96  call    memset_0
0x180045f9b  mov     eax, 10000000h
0x180045fa0  cmp     qword ptr [r15+18h], 7
0x180045fa5  mov     rcx, r15
0x180045fa8  jbe     short loc_180045FAD
0x180045faa  mov     rcx, [r15]
0x180045fad  mov     [rbp+630h+Logfile.LogFileName], rcx
0x180045fb1  mov     dword ptr [rbp+630h+Logfile.1Ch], eax
0x180045fb4  cmp     [rdi+1], r14b
0x180045fb8  jz      short loc_180045FC1
0x180045fba  bts     eax, 0Ch
0x180045fbe  mov     dword ptr [rbp+630h+Logfile.1Ch], eax
0x180045fc1  lea     rax, _anonymous_namespace___etw_event_record_callback
0x180045fc8  mov     qword ptr [rbp+630h+Logfile.1A8h], rax
0x180045fcf  lea     rax, _lambda_c86b7ba222448e1bb0d7ba49dcdbda76____lambda_invoker_cdecl___EVENT_TRACE_LOGFILEW_
0x180045fd6  mov     [rbp+630h+Logfile.BufferCallback], rax
0x180045fdd  mov     [rbp+630h+Logfile.Context], rsi
0x180045fe4  lea     rcx, [rbp+630h+Logfile]; Logfile
0x180045fe8  call    cs:__imp_OpenTraceW
0x180045fee  mov     rdi, rax
0x180045ff1  mov     [rsp+730h+var_6F0], rax
0x180045ff6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180045ffa  jnz     short loc_18004600A
0x180045ffc  call    cs:__imp_GetLastError
0x180046002  test    eax, eax
0x180046004  jnz     loc_180046285
0x18004600a  xorps   xmm0, xmm0
0x18004600d  movups  [rbp+630h+var_4A0], xmm0
0x180046014  mov     [rbp+630h+var_490], r14
0x18004601b  mov     [rbp+630h+var_488], 7
0x180046026  mov     word ptr [rbp+630h+var_4A0], r14w
0x18004602e  mov     r9, [rbp+630h+Logfile.LoggerName]
0x180046032  test    r9, r9
0x180046035  jz      short loc_18004607E
0x180046037  cmp     [r9], r14w
0x18004603b  jz      short loc_18004607E
0x18004603d  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180046041  inc     rdx
0x180046044  cmp     [r9+rdx*2], r14w
0x180046049  jnz     short loc_180046041
0x18004604b  lea     rcx, [rbp+630h+var_4A0]; void *
0x180046052  cmp     rdx, 7
0x180046056  ja      short loc_180046079
0x180046058  mov     [rbp+630h+var_490], rdx
0x18004605f  lea     rbx, [rdx+rdx]
0x180046063  mov     r8, rbx; Size
0x180046066  mov     rdx, r9; Src
0x180046069  call    memmove_0
0x18004606e  mov     word ptr [rbp+rbx+630h+var_4A0], r14w
0x180046077  jmp     short loc_18004607E
0x180046079  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18004607e  lea     rdx, [rbp+630h+var_4A0]
0x180046085  lea     rcx, [rbp+630h+var_688]
0x180046089  call    ??$make_shared@Uetw_trace_state_t@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@YA?AV?$shared_ptr@Uetw_trace_state_t@@@0@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::make_shared<etw_trace_state_t,std::wstring>(std::wstring &&)
0x18004608e  nop
0x18004608f  mov     rbx, [rbp+630h+var_680]
0x180046093  test    rbx, rbx
0x180046096  jz      short loc_18004609C
0x180046098  lock inc dword ptr [rbx+8]
0x18004609c  mov     r14, [rbp+630h+var_688]
0x1800460a0  mov     qword ptr [rsp+730h+var_6E0], r14
0x1800460a5  mov     qword ptr [rsp+730h+var_6E0+8], rbx
0x1800460aa  mov     [rsp+730h+var_6D0], rdi
0x1800460af  mov     [rsp+730h+var_6E8], 0
0x1800460b8  mov     [rsp+730h+var_6C8], rsi
0x1800460bd  mov     ecx, 20h ; ' '; Size
0x1800460c2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800460c7  mov     [rax], r14
0x1800460ca  mov     [rax+8], rbx
0x1800460ce  xorps   xmm0, xmm0
0x1800460d1  movdqu  [rsp+730h+var_6E0], xmm0
0x1800460d7  mov     [rax+10h], rdi
0x1800460db  mov     [rsp+730h+var_6C8], 0
0x1800460e4  mov     [rax+18h], rsi
0x1800460e8  mov     [rbp+630h+var_690], rax
0x1800460ec  lea     rcx, [rsp+730h+var_700+8]
0x1800460f1  mov     [rsp+730h+var_708], rcx
0x1800460f6  mov     dword ptr [rsp+730h+var_710], 0
0x1800460fe  mov     r9, rax
0x180046101  lea     r8, std__thread___Invoke_std__tuple__lambda_e4aee9a13df23212e389919ed62ed785____0_
0x180046108  xor     edx, edx
0x18004610a  xor     ecx, ecx
0x18004610c  call    cs:__imp__o__beginthreadex
0x180046112  mov     [rsp+730h+var_700], rax
0x180046117  test    rax, rax
0x18004611a  jz      loc_180046271
0x180046120  lea     rcx, [rsp+730h+var_6E0]
0x180046125  call    _lambda_e4aee9a13df23212e389919ed62ed785_____lambda_e4aee9a13df23212e389919ed62ed785_
0x18004612a  mov     rdx, [rsp+730h+var_700]; struct lua_State *
0x18004612f  mov     rsi, [rbp+630h+var_6A0]
0x180046133  mov     rcx, rsi; this
0x180046136  call    ?set_lua_etw_thread@windiag@@YAXPEAUlua_State@@PEAX@Z; windiag::set_lua_etw_thread(lua_State *,void *)
0x18004613b  mov     qword ptr [rsp+730h+var_6E0], rsi
0x180046140  xorps   xmm0, xmm0
0x180046143  movdqu  [rsp+730h+var_6E0+8], xmm0
0x180046149  test    rbx, rbx
0x18004614c  jz      short loc_180046152
0x18004614e  lock inc dword ptr [rbx+8]
0x180046152  mov     qword ptr [rsp+730h+var_6E0+8], r14
0x180046157  mov     [rsp+730h+var_6D0], rbx
0x18004615c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180046160  mov     [rsp+730h+var_6F0], rsi
0x180046165  mov     [rsp+730h+var_6C8], rdi
0x18004616a  mov     rcx, [rsp+730h+var_700]
0x18004616f  mov     r8d, dword ptr [rsp+730h+var_700+8]
0x180046174  mov     eax, dword ptr [rsp+730h+var_700+0Ch]
0x180046178  movdqa  xmmword ptr [rsp+730h+var_700], xmm0
0x18004617e  mov     [rsp+730h+var_6C0], rcx
0x180046183  mov     [rsp+730h+var_6B8], r8d
0x180046188  mov     [rsp+730h+var_6B4], eax
0x18004618c  lea     r8, [rsp+730h+var_6E0]
0x180046191  mov     rdx, r14
0x180046194  mov     rdi, [rbp+630h+var_698]
0x180046198  mov     rcx, rdi
0x18004619b  call    std__shared_ptr_etw_trace_state_t___shared_ptr_etw_trace_state_t__etw_trace_state_t__lambda_7aeed00cc4298c22832b70bc0bbfba4a__0_
0x1800461a0  nop
0x1800461a1  cmp     dword ptr [rsp+730h+var_700+8], 0
0x1800461a6  jz      short loc_1800461AF
0x1800461a8  call    cs:__imp__o_terminate
0x1800461ae  nop
0x1800461af  test    rbx, rbx
0x1800461b2  jz      short loc_1800461E8
0x1800461b4  mov     eax, esi
0x1800461b6  lock xadd [rbx+8], eax
0x1800461bb  add     eax, esi
0x1800461bd  jnz     short loc_1800461E8
0x1800461bf  mov     rax, [rbx]
0x1800461c2  mov     rcx, rbx
0x1800461c5  mov     rax, [rax]
0x1800461c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800461cd  mov     eax, esi
0x1800461cf  lock xadd [rbx+0Ch], eax
0x1800461d4  add     eax, esi
0x1800461d6  jnz     short loc_1800461E8
0x1800461d8  mov     rax, [rbx]
0x1800461db  mov     rcx, rbx
0x1800461de  mov     rax, [rax+8]
0x1800461e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800461e7  nop
0x1800461e8  lea     rcx, [rbp+630h+var_4A0]
0x1800461ef  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800461f4  nop
0x1800461f5  mov     rbx, [r12+8]
0x1800461fa  test    rbx, rbx
0x1800461fd  jz      short loc_180046233
0x1800461ff  mov     eax, esi
0x180046201  lock xadd [rbx+8], eax
0x180046206  add     eax, esi
0x180046208  jnz     short loc_180046233
0x18004620a  mov     rax, [rbx]
0x18004620d  mov     rcx, rbx
0x180046210  mov     rax, [rax]
0x180046213  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046218  mov     eax, esi
0x18004621a  lock xadd [rbx+0Ch], eax
0x18004621f  add     eax, esi
0x180046221  jnz     short loc_180046233
0x180046223  mov     rax, [rbx]
0x180046226  mov     rcx, rbx
0x180046229  mov     rax, [rax+8]
0x18004622d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046232  nop
0x180046233  mov     rcx, r15
0x180046236  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004623b  nop
0x18004623c  cmp     byte ptr [r13+10h], 0
0x180046241  jz      short loc_18004624B
0x180046243  mov     rcx, r13
0x180046246  call    ??1?$_Tree@V?$_Tmap_traits@U_GUID@@Uetw_filter_provider_t@@U?$less@U_GUID@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@Uetw_filter_provider_t@@@std@@@4@$00@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<_GUID,etw_filter_provider_t,std::less<_GUID>,std::allocator<std::pair<_GUID const,etw_filter_provider_t>>,1>>::~_Tree<std::_Tmap_traits<_GUID,etw_filter_provider_t,std::less<_GUID>,std::allocator<std::pair<_GUID const,etw_filter_provider_t>>,1>>(void)
0x18004624b  mov     rax, rdi
0x18004624e  mov     rcx, [rbp+630h+var_50]
0x180046255  xor     rcx, rsp; StackCookie
0x180046258  call    __security_check_cookie
0x18004625d  add     rsp, 6F8h
0x180046264  pop     r15
0x180046266  pop     r14
0x180046268  pop     r13
0x18004626a  pop     r12
0x18004626c  pop     rdi
0x18004626d  pop     rsi
0x18004626e  pop     rbx
0x18004626f  pop     rbp
0x180046270  retn
0x180046271  mov     dword ptr [rsp+730h+var_700+8], 0
0x180046279  mov     ecx, 6
0x18004627e  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180046284  nop
0x180046285  mov     edx, eax; __int64
0x180046287  mov     dword ptr [rsp+730h+var_708], 21Dh
0x18004628f  lea     rax, aEtwOpenTraceCo; "etw_open_trace_common"
0x180046296  mov     [rsp+730h+var_710], rax
0x18004629b  lea     r9, aSDFailed; "[%s:%d] failed; "
0x1800462a2  xor     r8d, r8d; void *
0x1800462a5  lea     rcx, [rbp+630h+pExceptionObject]; this
0x1800462ac  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x1800462b1  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x1800462b8  lea     rcx, [rbp+630h+pExceptionObject]; pExceptionObject
0x1800462bf  call    _CxxThrowException_0
```
