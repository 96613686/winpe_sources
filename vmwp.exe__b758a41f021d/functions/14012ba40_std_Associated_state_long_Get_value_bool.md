# std::_Associated_state<long>::_Get_value(bool)

- ea: `0x14012ba40`
- end: `0x14012bb54`
- name: `?_Get_value@?$_Associated_state@J@std@@UEAAAEAJ_N@Z`
- size: `276`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1400d1ed0`
- `0x1400d210c`
- `0x14011ea40`
- `0x14012ba40`
- `0x14012bb6c`
- `0x14012be20`
- `0x14012c0c0`

## import_xrefs

- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x14012ba96`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x14012bafc`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x14012ba96`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x14012bafc`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x14012bab5`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x14012bb1b`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x14012bab5`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x14012bb1b`
- `msvcp_win!_Cnd_wait` at `0x14012bae4`
- `msvcp_win!_Cnd_wait` at `0x14012bae4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::_Associated_state<long>::_Get_value(__int64 a1, char a2)
{
  _BYTE *v4; // rsi
  __int128 v6; // [rsp+20h] [rbp-38h] BYREF
  _Mtx_t v7[2]; // [rsp+30h] [rbp-28h] BYREF

  *(_OWORD *)v7 = 0;
  std::unique_lock<std::mutex>::unique_lock<std::mutex>(v7, a1 + 32);
  v4 = (_BYTE *)(a1 + 184);
  if ( a2 && *v4 )
    std::_Throw_future_error2(2);
  if ( __ExceptionPtrToBool((const void *)(a1 + 16)) )
  {
    v6 = 0;
    __ExceptionPtrCopy(&v6, (const void *)(a1 + 16));
    std::rethrow_exception(&v6);
    __debugbreak();
  }
  *v4 = 1;
  std::_Associated_state<int>::_Maybe_run_deferred_function(a1, v7);
  while ( !*(_DWORD *)(a1 + 188) )
    _Cnd_wait((_Cnd_t)(a1 + 112), v7[0]);
  if ( __ExceptionPtrToBool((const void *)(a1 + 16)) )
  {
    v6 = 0;
    __ExceptionPtrCopy(&v6, (const void *)(a1 + 16));
    std::rethrow_exception(&v6);
  }
  std::unique_lock<std::mutex>::~unique_lock<std::mutex>(v7);
  return a1 + 12;
}

```

## disassembly

```asm
0x14012ba40  push    rbp
0x14012ba42  push    rbx
0x14012ba43  push    rsi
0x14012ba44  push    rdi
0x14012ba45  mov     rbp, rsp
0x14012ba48  sub     rsp, 58h
0x14012ba4c  mov     rax, cs:__security_cookie
0x14012ba53  xor     rax, rsp
0x14012ba56  mov     [rbp+var_18], rax
0x14012ba5a  mov     bl, dl
0x14012ba5c  mov     rdi, rcx
0x14012ba5f  xorps   xmm0, xmm0
0x14012ba62  movups  xmmword ptr [rbp+var_28], xmm0
0x14012ba66  lea     rdx, [rcx+20h]
0x14012ba6a  lea     rcx, [rbp+var_28]
0x14012ba6e  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x14012ba73  nop
0x14012ba74  lea     rsi, [rdi+0B8h]
0x14012ba7b  test    bl, bl
0x14012ba7d  jz      short loc_14012BA8F
0x14012ba7f  cmp     byte ptr [rsi], 0
0x14012ba82  jz      short loc_14012BA8F
0x14012ba84  mov     ecx, 2
0x14012ba89  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x14012ba8f  lea     rbx, [rdi+10h]
0x14012ba93  mov     rcx, rbx
0x14012ba96  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x14012ba9d  nop     dword ptr [rax+rax+00h]
0x14012baa2  test    al, al
0x14012baa4  jz      short loc_14012BACB
0x14012baa6  xorps   xmm0, xmm0
0x14012baa9  movdqu  [rbp+var_38], xmm0
0x14012baae  mov     rdx, rbx
0x14012bab1  lea     rcx, [rbp+var_38]
0x14012bab5  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x14012babc  nop     dword ptr [rax+rax+00h]
0x14012bac1  lea     rcx, [rbp+var_38]
0x14012bac5  call    ?rethrow_exception@std@@YAXVexception_ptr@1@@Z; std::rethrow_exception(std::exception_ptr)
0x14012baca  int     3; Trap to Debugger
0x14012bacb  mov     byte ptr [rsi], 1
0x14012bace  lea     rdx, [rbp+var_28]
0x14012bad2  mov     rcx, rdi
0x14012bad5  call    ?_Maybe_run_deferred_function@?$_Associated_state@H@std@@IEAAXAEAV?$unique_lock@Vmutex@std@@@2@@Z; std::_Associated_state<int>::_Maybe_run_deferred_function(std::unique_lock<std::mutex> &)
0x14012bada  jmp     short loc_14012BAF0
0x14012badc  mov     rdx, [rbp+var_28]; _Mtx_t
0x14012bae0  lea     rcx, [rdi+70h]; _Cnd_t
0x14012bae4  call    cs:__imp__Cnd_wait
0x14012baeb  nop     dword ptr [rax+rax+00h]
0x14012baf0  cmp     dword ptr [rdi+0BCh], 0
0x14012baf7  jz      short loc_14012BADC
0x14012baf9  mov     rcx, rbx
0x14012bafc  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x14012bb03  nop     dword ptr [rax+rax+00h]
0x14012bb08  test    al, al
0x14012bb0a  jz      short loc_14012BB31
0x14012bb0c  xorps   xmm0, xmm0
0x14012bb0f  movdqu  [rbp+var_38], xmm0
0x14012bb14  mov     rdx, rbx
0x14012bb17  lea     rcx, [rbp+var_38]
0x14012bb1b  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x14012bb22  nop     dword ptr [rax+rax+00h]
0x14012bb27  lea     rcx, [rbp+var_38]
0x14012bb2b  call    ?rethrow_exception@std@@YAXVexception_ptr@1@@Z; std::rethrow_exception(std::exception_ptr)
0x14012bb30  nop
0x14012bb31  lea     rcx, [rbp+var_28]
0x14012bb35  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x14012bb3a  lea     rax, [rdi+0Ch]
0x14012bb3e  mov     rcx, [rbp+var_18]
0x14012bb42  xor     rcx, rsp; StackCookie
0x14012bb45  call    __security_check_cookie
0x14012bb4a  add     rsp, 58h
0x14012bb4e  pop     rdi
0x14012bb4f  pop     rsi
0x14012bb50  pop     rbx
0x14012bb51  pop     rbp
0x14012bb52  retn
```
