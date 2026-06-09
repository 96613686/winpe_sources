# std::thread::_Invoke_std::tuple__lambda_e4aee9a13df23212e389919ed62ed785____0_

- ea: `0x180044920`
- end: `0x180044a31`
- name: `std::thread::_Invoke_std::tuple__lambda_e4aee9a13df23212e389919ed62ed785____0_`
- size: `273`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800048e0`
- `0x18000491c`
- `0x180004d74`
- `0x1800425a4`
- `0x180044920`
- `0x180045680`
- `0x18004890c`

## import_xrefs

- `msvcp_win!_Cnd_do_broadcast_at_thread_exit` at `0x180044a09`
- `msvcp_win!_Cnd_do_broadcast_at_thread_exit` at `0x180044a09`
- `msvcp_win!_Mtx_unlock` at `0x1800449f9`
- `msvcp_win!_Mtx_unlock` at `0x1800449f9`
- `msvcp_win!_Mtx_lock` at `0x1800449b5`
- `msvcp_win!_Mtx_lock` at `0x1800449b5`
- `msvcp_win!_Cnd_signal` at `0x180044a03`
- `msvcp_win!_Cnd_signal` at `0x180044a03`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800449c4`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800449df`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800449c4`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800449df`
- `api-ms-win-eventing-consumer-l1-1-0!ProcessTrace` at `0x180044969`
- `api-ms-win-eventing-consumer-l1-1-0!ProcessTrace` at `0x180044969`

## pseudocode

```c
__int64 __fastcall std::thread::_Invoke_std::tuple__lambda_e4aee9a13df23212e389919ed62ed785____0_(ULONG64 *Block)
{
  __int64 v2; // rbx
  ULONG64 v3; // rbx
  void *v4; // rax
  __int64 v5; // rax
  __int64 v6; // rbx
  _QWORD v8[3]; // [rsp+20h] [rbp-18h] BYREF

  v2 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  if ( !*(_BYTE *)(v2 + 8) )
    _dyn_tls_on_demand_init();
  if ( *(_BYTE *)(v2 + 9) )
    ProcessTrace(Block + 2, 1u, 0, 0);
  v3 = Block[3];
  v4 = operator new(0xA8u);
  v5 = std::_Ref_count_obj2<etw_event_summary_t>::_Ref_count_obj2<etw_event_summary_t>(v4, v3 + 272);
  v8[0] = v5 + 16;
  v8[1] = v5;
  std::atomic_store<etw_event_summary_t>(*Block + 32, v8);
  v6 = *(_QWORD *)Block[3];
  if ( _Mtx_lock((_Mtx_t)v6) )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  if ( *(_DWORD *)(v6 + 76) == 0x7FFFFFFF )
  {
    *(_DWORD *)(v6 + 76) = 2147483646;
    std::_Throw_Cpp_error(6);
    __debugbreak();
  }
  if ( !*(_BYTE *)(v6 + 209) )
    *(_BYTE *)(v6 + 208) = 1;
  _Mtx_unlock((_Mtx_t)v6);
  _Cnd_signal((_Cnd_t)(v6 + 80));
  _Cnd_do_broadcast_at_thread_exit();
  lambda_e4aee9a13df23212e389919ed62ed785_::__lambda_e4aee9a13df23212e389919ed62ed785_(Block);
  operator delete(Block);
  return 0;
}

```

## disassembly

```asm
0x180044920  mov     [rsp+arg_0], rbx
0x180044925  push    rdi
0x180044926  sub     rsp, 30h
0x18004492a  mov     rdi, rcx
0x18004492d  mov     edx, cs:_tls_index
0x180044933  mov     rax, gs:58h
0x18004493c  mov     rbx, [rax+rdx*8]
0x180044940  mov     eax, 8
0x180044945  cmp     byte ptr [rax+rbx], 0
0x180044949  jnz     short loc_180044950
0x18004494b  call    __dyn_tls_on_demand_init
0x180044950  mov     eax, 9
0x180044955  cmp     byte ptr [rax+rbx], 0
0x180044959  jz      short loc_18004496F
0x18004495b  lea     rcx, [rdi+10h]; HandleArray
0x18004495f  xor     r9d, r9d; EndTime
0x180044962  xor     r8d, r8d; StartTime
0x180044965  lea     edx, [r9+1]; HandleCount
0x180044969  call    cs:__imp_ProcessTrace
0x18004496f  mov     rbx, [rdi+18h]
0x180044973  mov     ecx, 0A8h; Size
0x180044978  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004497d  lea     rdx, [rbx+110h]
0x180044984  mov     rcx, rax
0x180044987  call    ??$?0Uetw_event_summary_t@@@?$_Ref_count_obj2@Uetw_event_summary_t@@@std@@QEAA@$$QEAUetw_event_summary_t@@@Z; std::_Ref_count_obj2<etw_event_summary_t>::_Ref_count_obj2<etw_event_summary_t>(etw_event_summary_t &&)
0x18004498c  lea     rcx, [rax+10h]
0x180044990  mov     [rsp+38h+var_18], rcx
0x180044995  mov     [rsp+38h+var_10], rax
0x18004499a  mov     rcx, [rdi]
0x18004499d  add     rcx, 20h ; ' '
0x1800449a1  lea     rdx, [rsp+38h+var_18]
0x1800449a6  call    ??$atomic_store@Uetw_event_summary_t@@@std@@YAXPEAV?$shared_ptr@Uetw_event_summary_t@@@0@V10@@Z; std::atomic_store<etw_event_summary_t>(std::shared_ptr<etw_event_summary_t> *,std::shared_ptr<etw_event_summary_t>)
0x1800449ab  mov     rax, [rdi+18h]
0x1800449af  mov     rbx, [rax]
0x1800449b2  mov     rcx, rbx; _Mtx_t
0x1800449b5  call    cs:__imp__Mtx_lock
0x1800449bb  test    eax, eax
0x1800449bd  jz      short loc_1800449CB
0x1800449bf  mov     ecx, 5
0x1800449c4  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800449ca  int     3; Trap to Debugger
0x1800449cb  mov     eax, [rbx+4Ch]
0x1800449ce  cmp     eax, 7FFFFFFFh
0x1800449d3  jnz     short loc_1800449E6
0x1800449d5  dec     eax
0x1800449d7  mov     [rbx+4Ch], eax
0x1800449da  mov     ecx, 6
0x1800449df  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800449e5  int     3; Trap to Debugger
0x1800449e6  cmp     byte ptr [rbx+0D1h], 0
0x1800449ed  jnz     short loc_1800449F6
0x1800449ef  mov     byte ptr [rbx+0D0h], 1
0x1800449f6  mov     rcx, rbx; _Mtx_t
0x1800449f9  call    cs:__imp__Mtx_unlock
0x1800449ff  lea     rcx, [rbx+50h]; _Cnd_t
0x180044a03  call    cs:__imp__Cnd_signal
0x180044a09  call    cs:__imp__Cnd_do_broadcast_at_thread_exit
0x180044a0f  mov     rcx, rdi
0x180044a12  call    _lambda_e4aee9a13df23212e389919ed62ed785_____lambda_e4aee9a13df23212e389919ed62ed785_
0x180044a17  mov     edx, 20h ; ' '
0x180044a1c  mov     rcx, rdi; Block
0x180044a1f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180044a24  xor     eax, eax
0x180044a26  mov     rbx, [rsp+38h+arg_0]
0x180044a2b  add     rsp, 30h
0x180044a2f  pop     rdi
0x180044a30  retn
```
