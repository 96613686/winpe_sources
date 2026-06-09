# std::_Associated_state<long>::_Get_value(bool)

- ea: `0x14013f960`
- end: `0x14013fa74`
- name: `?_Get_value@?$_Associated_state@J@std@@UEAAAEAJ_N@Z`
- size: `276`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1400e1620`
- `0x1400e185c`
- `0x140132960`
- `0x14013f960`
- `0x14013fa8c`
- `0x14013fd40`
- `0x14013ffe0`

## import_xrefs

- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x14013f9b6`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x14013fa1c`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x14013f9b6`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x14013fa1c`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x14013f9d5`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x14013fa3b`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x14013f9d5`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x14013fa3b`
- `msvcp_win!_Cnd_wait` at `0x14013fa04`
- `msvcp_win!_Cnd_wait` at `0x14013fa04`

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
0x14013f960  push    rbp
0x14013f962  push    rbx
0x14013f963  push    rsi
0x14013f964  push    rdi
0x14013f965  mov     rbp, rsp
0x14013f968  sub     rsp, 58h
0x14013f96c  mov     rax, cs:__security_cookie
0x14013f973  xor     rax, rsp
0x14013f976  mov     [rbp+var_18], rax
0x14013f97a  mov     bl, dl
0x14013f97c  mov     rdi, rcx
0x14013f97f  xorps   xmm0, xmm0
0x14013f982  movups  xmmword ptr [rbp+var_28], xmm0
0x14013f986  lea     rdx, [rcx+20h]
0x14013f98a  lea     rcx, [rbp+var_28]
0x14013f98e  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x14013f993  nop
0x14013f994  lea     rsi, [rdi+0B8h]
0x14013f99b  test    bl, bl
0x14013f99d  jz      short loc_14013F9AF
0x14013f99f  cmp     byte ptr [rsi], 0
0x14013f9a2  jz      short loc_14013F9AF
0x14013f9a4  mov     ecx, 2
0x14013f9a9  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x14013f9af  lea     rbx, [rdi+10h]
0x14013f9b3  mov     rcx, rbx
0x14013f9b6  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x14013f9bd  nop     dword ptr [rax+rax+00h]
0x14013f9c2  test    al, al
0x14013f9c4  jz      short loc_14013F9EB
0x14013f9c6  xorps   xmm0, xmm0
0x14013f9c9  movdqu  [rbp+var_38], xmm0
0x14013f9ce  mov     rdx, rbx
0x14013f9d1  lea     rcx, [rbp+var_38]
0x14013f9d5  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x14013f9dc  nop     dword ptr [rax+rax+00h]
0x14013f9e1  lea     rcx, [rbp+var_38]
0x14013f9e5  call    ?rethrow_exception@std@@YAXVexception_ptr@1@@Z; std::rethrow_exception(std::exception_ptr)
0x14013f9ea  int     3; Trap to Debugger
0x14013f9eb  mov     byte ptr [rsi], 1
0x14013f9ee  lea     rdx, [rbp+var_28]
0x14013f9f2  mov     rcx, rdi
0x14013f9f5  call    ?_Maybe_run_deferred_function@?$_Associated_state@H@std@@IEAAXAEAV?$unique_lock@Vmutex@std@@@2@@Z; std::_Associated_state<int>::_Maybe_run_deferred_function(std::unique_lock<std::mutex> &)
0x14013f9fa  jmp     short loc_14013FA10
0x14013f9fc  mov     rdx, [rbp+var_28]; _Mtx_t
0x14013fa00  lea     rcx, [rdi+70h]; _Cnd_t
0x14013fa04  call    cs:__imp__Cnd_wait
0x14013fa0b  nop     dword ptr [rax+rax+00h]
0x14013fa10  cmp     dword ptr [rdi+0BCh], 0
0x14013fa17  jz      short loc_14013F9FC
0x14013fa19  mov     rcx, rbx
0x14013fa1c  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x14013fa23  nop     dword ptr [rax+rax+00h]
0x14013fa28  test    al, al
0x14013fa2a  jz      short loc_14013FA51
0x14013fa2c  xorps   xmm0, xmm0
0x14013fa2f  movdqu  [rbp+var_38], xmm0
0x14013fa34  mov     rdx, rbx
0x14013fa37  lea     rcx, [rbp+var_38]
0x14013fa3b  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x14013fa42  nop     dword ptr [rax+rax+00h]
0x14013fa47  lea     rcx, [rbp+var_38]
0x14013fa4b  call    ?rethrow_exception@std@@YAXVexception_ptr@1@@Z; std::rethrow_exception(std::exception_ptr)
0x14013fa50  nop
0x14013fa51  lea     rcx, [rbp+var_28]
0x14013fa55  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x14013fa5a  lea     rax, [rdi+0Ch]
0x14013fa5e  mov     rcx, [rbp+var_18]
0x14013fa62  xor     rcx, rsp; StackCookie
0x14013fa65  call    __security_check_cookie
0x14013fa6a  add     rsp, 58h
0x14013fa6e  pop     rdi
0x14013fa6f  pop     rsi
0x14013fa70  pop     rbx
0x14013fa71  pop     rbp
0x14013fa72  retn
```
