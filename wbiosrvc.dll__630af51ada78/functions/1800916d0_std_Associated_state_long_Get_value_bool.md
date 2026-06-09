# std::_Associated_state<long>::_Get_value(bool)

- ea: `0x1800916d0`
- end: `0x1800917b6`
- name: `?_Get_value@?$_Associated_state@J@std@@UEAAAEAJ_N@Z`
- size: `230`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18000eb50`
- `0x180031288`
- `0x180072dc0`
- `0x1800916d0`
- `0x180091800`

## import_xrefs

- `msvcp_win!_Cnd_wait` at `0x18009175c`
- `msvcp_win!_Cnd_wait` at `0x18009175c`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18009173c`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180091799`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18009173c`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180091799`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180091711`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18009176e`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180091711`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18009176e`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18009172a`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180091787`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18009172a`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180091787`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::_Associated_state<long>::_Get_value(__int64 a1, char a2)
{
  _BYTE *v4; // rsi
  __int128 v6; // [rsp+20h] [rbp-28h] BYREF
  _Mtx_t v7[3]; // [rsp+30h] [rbp-18h] BYREF

  std::unique_lock<std::mutex>::unique_lock<std::mutex>(v7, a1 + 32);
  v4 = (_BYTE *)(a1 + 184);
  if ( a2 && *v4 )
    std::_Throw_future_error2(2);
  if ( __ExceptionPtrToBool((const void *)(a1 + 16)) )
  {
    v6 = 0;
    __ExceptionPtrCopy(&v6, (const void *)(a1 + 16));
    __ExceptionPtrRethrow(&v6);
  }
  *v4 = 1;
  std::_Associated_state<long>::_Maybe_run_deferred_function(a1, v7);
  while ( !*(_DWORD *)(a1 + 188) )
    _Cnd_wait((_Cnd_t)(a1 + 112), v7[0]);
  if ( __ExceptionPtrToBool((const void *)(a1 + 16)) )
  {
    v6 = 0;
    __ExceptionPtrCopy(&v6, (const void *)(a1 + 16));
    __ExceptionPtrRethrow(&v6);
  }
  std::unique_lock<std::mutex>::~unique_lock<std::mutex>(v7);
  return a1 + 12;
}

```

## disassembly

```asm
0x1800916d0  push    rbp
0x1800916d2  push    rbx
0x1800916d3  push    rsi
0x1800916d4  push    rdi
0x1800916d5  mov     rbp, rsp
0x1800916d8  sub     rsp, 48h
0x1800916dc  mov     bl, dl
0x1800916de  mov     rdi, rcx
0x1800916e1  lea     rdx, [rcx+20h]
0x1800916e5  lea     rcx, [rbp+var_18]
0x1800916e9  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x1800916ee  nop
0x1800916ef  lea     rsi, [rdi+0B8h]
0x1800916f6  test    bl, bl
0x1800916f8  jz      short loc_18009170A
0x1800916fa  cmp     byte ptr [rsi], 0
0x1800916fd  jz      short loc_18009170A
0x1800916ff  mov     ecx, 2
0x180091704  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x18009170a  lea     rbx, [rdi+10h]
0x18009170e  mov     rcx, rbx
0x180091711  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x180091717  test    al, al
0x180091719  jz      short loc_180091743
0x18009171b  xorps   xmm0, xmm0
0x18009171e  movdqu  [rbp+var_28], xmm0
0x180091723  mov     rdx, rbx
0x180091726  lea     rcx, [rbp+var_28]
0x18009172a  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180091730  lea     rax, [rbp+var_28]
0x180091734  mov     [rbp+arg_0], rax
0x180091738  lea     rcx, [rbp+var_28]
0x18009173c  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x180091742  nop
0x180091743  mov     byte ptr [rsi], 1
0x180091746  lea     rdx, [rbp+var_18]
0x18009174a  mov     rcx, rdi
0x18009174d  call    ?_Maybe_run_deferred_function@?$_Associated_state@J@std@@IEAAXAEAV?$unique_lock@Vmutex@std@@@2@@Z; std::_Associated_state<long>::_Maybe_run_deferred_function(std::unique_lock<std::mutex> &)
0x180091752  jmp     short loc_180091762
0x180091754  mov     rdx, [rbp+var_18]; _Mtx_t
0x180091758  lea     rcx, [rdi+70h]; _Cnd_t
0x18009175c  call    cs:__imp__Cnd_wait
0x180091762  cmp     dword ptr [rdi+0BCh], 0
0x180091769  jz      short loc_180091754
0x18009176b  mov     rcx, rbx
0x18009176e  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x180091774  test    al, al
0x180091776  jz      short loc_1800917A0
0x180091778  xorps   xmm0, xmm0
0x18009177b  movdqu  [rbp+var_28], xmm0
0x180091780  mov     rdx, rbx
0x180091783  lea     rcx, [rbp+var_28]
0x180091787  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18009178d  lea     rax, [rbp+var_28]
0x180091791  mov     [rbp+arg_0], rax
0x180091795  lea     rcx, [rbp+var_28]
0x180091799  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x18009179f  nop
0x1800917a0  lea     rcx, [rbp+var_18]
0x1800917a4  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x1800917a9  lea     rax, [rdi+0Ch]
0x1800917ad  add     rsp, 48h
0x1800917b1  pop     rdi
0x1800917b2  pop     rsi
0x1800917b3  pop     rbx
0x1800917b4  pop     rbp
0x1800917b5  retn
```
