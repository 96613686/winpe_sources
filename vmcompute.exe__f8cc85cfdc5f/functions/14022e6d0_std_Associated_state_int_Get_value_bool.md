# std::_Associated_state<int>::_Get_value(bool)

- ea: `0x14022e6d0`
- end: `0x14022e802`
- name: `?_Get_value@?$_Associated_state@H@std@@UEAAAEAH_N@Z`
- size: `306`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1400e801c`
- `0x140105848`
- `0x1401332f0`
- `0x14022e6d0`
- `0x14022e808`
- `0x14022ea18`

## import_xrefs

- `msvcp_win!_Cnd_wait` at `0x14022e783`
- `msvcp_win!_Cnd_wait` at `0x14022e783`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x14022e726`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x14022e79b`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x14022e726`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x14022e79b`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x14022e75d`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x14022e7d2`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x14022e75d`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x14022e7d2`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x14022e745`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x14022e7ba`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x14022e745`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x14022e7ba`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::_Associated_state<int>::_Get_value(__int64 a1, char a2)
{
  _BYTE *v4; // rsi
  __int128 v6; // [rsp+20h] [rbp-38h] BYREF
  __int128 *v7; // [rsp+30h] [rbp-28h]
  _Mtx_t v8[2]; // [rsp+38h] [rbp-20h] BYREF

  *(_OWORD *)v8 = 0;
  std::unique_lock<std::mutex>::unique_lock<std::mutex>(v8, a1 + 32);
  v4 = (_BYTE *)(a1 + 184);
  if ( a2 && *v4 )
    std::_Throw_future_error2(2);
  if ( __ExceptionPtrToBool((const void *)(a1 + 16)) )
  {
    v6 = 0;
    __ExceptionPtrCopy(&v6, (const void *)(a1 + 16));
    v7 = &v6;
    __ExceptionPtrRethrow(&v6);
  }
  *v4 = 1;
  std::_Associated_state<int>::_Maybe_run_deferred_function(a1, v8);
  while ( !*(_DWORD *)(a1 + 188) )
    _Cnd_wait((_Cnd_t)(a1 + 112), v8[0]);
  if ( __ExceptionPtrToBool((const void *)(a1 + 16)) )
  {
    v6 = 0;
    __ExceptionPtrCopy(&v6, (const void *)(a1 + 16));
    v7 = &v6;
    __ExceptionPtrRethrow(&v6);
  }
  std::unique_lock<std::mutex>::~unique_lock<std::mutex>(v8);
  return a1 + 12;
}

```

## disassembly

```asm
0x14022e6d0  push    rbp
0x14022e6d2  push    rbx
0x14022e6d3  push    rsi
0x14022e6d4  push    rdi
0x14022e6d5  mov     rbp, rsp
0x14022e6d8  sub     rsp, 58h
0x14022e6dc  mov     rax, cs:__security_cookie
0x14022e6e3  xor     rax, rsp
0x14022e6e6  mov     [rbp+var_10], rax
0x14022e6ea  mov     bl, dl
0x14022e6ec  mov     rdi, rcx
0x14022e6ef  xorps   xmm0, xmm0
0x14022e6f2  movups  xmmword ptr [rbp+var_20], xmm0
0x14022e6f6  lea     rdx, [rcx+20h]
0x14022e6fa  lea     rcx, [rbp+var_20]
0x14022e6fe  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x14022e703  nop
0x14022e704  lea     rsi, [rdi+0B8h]
0x14022e70b  test    bl, bl
0x14022e70d  jz      short loc_14022E71F
0x14022e70f  cmp     byte ptr [rsi], 0
0x14022e712  jz      short loc_14022E71F
0x14022e714  mov     ecx, 2
0x14022e719  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x14022e71f  lea     rbx, [rdi+10h]
0x14022e723  mov     rcx, rbx
0x14022e726  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x14022e72d  nop     dword ptr [rax+rax+00h]
0x14022e732  test    al, al
0x14022e734  jz      short loc_14022E76A
0x14022e736  xorps   xmm0, xmm0
0x14022e739  movdqu  [rbp+var_38], xmm0
0x14022e73e  mov     rdx, rbx
0x14022e741  lea     rcx, [rbp+var_38]
0x14022e745  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x14022e74c  nop     dword ptr [rax+rax+00h]
0x14022e751  lea     rax, [rbp+var_38]
0x14022e755  mov     [rbp+var_28], rax
0x14022e759  lea     rcx, [rbp+var_38]
0x14022e75d  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x14022e764  nop     dword ptr [rax+rax+00h]
0x14022e769  nop
0x14022e76a  mov     byte ptr [rsi], 1
0x14022e76d  lea     rdx, [rbp+var_20]
0x14022e771  mov     rcx, rdi
0x14022e774  call    ?_Maybe_run_deferred_function@?$_Associated_state@H@std@@IEAAXAEAV?$unique_lock@Vmutex@std@@@2@@Z; std::_Associated_state<int>::_Maybe_run_deferred_function(std::unique_lock<std::mutex> &)
0x14022e779  jmp     short loc_14022E78F
0x14022e77b  mov     rdx, [rbp+var_20]; _Mtx_t
0x14022e77f  lea     rcx, [rdi+70h]; _Cnd_t
0x14022e783  call    cs:__imp__Cnd_wait
0x14022e78a  nop     dword ptr [rax+rax+00h]
0x14022e78f  cmp     dword ptr [rdi+0BCh], 0
0x14022e796  jz      short loc_14022E77B
0x14022e798  mov     rcx, rbx
0x14022e79b  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x14022e7a2  nop     dword ptr [rax+rax+00h]
0x14022e7a7  test    al, al
0x14022e7a9  jz      short loc_14022E7DF
0x14022e7ab  xorps   xmm0, xmm0
0x14022e7ae  movdqu  [rbp+var_38], xmm0
0x14022e7b3  mov     rdx, rbx
0x14022e7b6  lea     rcx, [rbp+var_38]
0x14022e7ba  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x14022e7c1  nop     dword ptr [rax+rax+00h]
0x14022e7c6  lea     rax, [rbp+var_38]
0x14022e7ca  mov     [rbp+var_28], rax
0x14022e7ce  lea     rcx, [rbp+var_38]
0x14022e7d2  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x14022e7d9  nop     dword ptr [rax+rax+00h]
0x14022e7de  nop
0x14022e7df  lea     rcx, [rbp+var_20]
0x14022e7e3  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x14022e7e8  lea     rax, [rdi+0Ch]
0x14022e7ec  mov     rcx, [rbp+var_10]
0x14022e7f0  xor     rcx, rsp; StackCookie
0x14022e7f3  call    __security_check_cookie
0x14022e7f8  add     rsp, 58h
0x14022e7fc  pop     rdi
0x14022e7fd  pop     rsi
0x14022e7fe  pop     rbx
0x14022e7ff  pop     rbp
0x14022e800  retn
```
