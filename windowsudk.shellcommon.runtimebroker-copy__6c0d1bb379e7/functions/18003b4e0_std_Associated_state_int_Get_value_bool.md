# std::_Associated_state<int>::_Get_value(bool)

- ea: `0x18003b4e0`
- end: `0x18003b5e9`
- name: `?_Get_value@?$_Associated_state@H@std@@UEAAAEAH_N@Z`
- size: `265`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18003b4e0`
- `0x18003b61c`
- `0x180433a30`
- `0x1804a2010`

## import_xrefs

- `msvcp_win!_Cnd_wait` at `0x18003b586`
- `msvcp_win!_Cnd_wait` at `0x18003b586`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18003b51d`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18003b558`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18003b51d`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18003b558`
- `msvcp_win!_Mtx_unlock` at `0x18003b56b`
- `msvcp_win!_Mtx_unlock` at `0x18003b56b`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18003b5ba`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18003b5e2`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18003b5ba`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18003b5e2`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18003b5a8`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18003b5d0`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18003b5a8`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18003b5d0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::_Associated_state<int>::_Get_value(__int64 a1, char a2)
{
  _BYTE *v4; // rsi
  _Mtx_t v6; // [rsp+20h] [rbp-28h] BYREF
  char v7; // [rsp+28h] [rbp-20h]
  __int128 v8; // [rsp+30h] [rbp-18h] BYREF

  v6 = (_Mtx_t)(a1 + 32);
  std::_Mutex_base::lock((std::_Mutex_base *)(a1 + 32));
  v7 = 1;
  v4 = (_BYTE *)(a1 + 184);
  if ( a2 && *v4 )
    std::_Throw_future_error2(2);
  if ( __ExceptionPtrToBool((const void *)(a1 + 16)) )
  {
    v8 = 0;
    __ExceptionPtrCopy(&v8, (const void *)(a1 + 16));
    __ExceptionPtrRethrow(&v8);
    goto LABEL_14;
  }
  *v4 = 1;
  if ( !*(_BYTE *)(a1 + 194) )
  {
    *(_BYTE *)(a1 + 194) = 1;
    (*(void (__fastcall **)(__int64, _Mtx_t *))(*(_QWORD *)a1 + 32LL))(a1, &v6);
  }
  while ( !*(_DWORD *)(a1 + 188) )
    _Cnd_wait((_Cnd_t)(a1 + 112), v6);
  if ( __ExceptionPtrToBool((const void *)(a1 + 16)) )
  {
LABEL_14:
    v8 = 0;
    __ExceptionPtrCopy(&v8, (const void *)(a1 + 16));
    __ExceptionPtrRethrow(&v8);
    JUMPOUT(0x18003B5E8LL);
  }
  if ( v7 )
    _Mtx_unlock(v6);
  return a1 + 12;
}

```

## disassembly

```asm
0x18003b4e0  push    rbp
0x18003b4e2  push    rbx
0x18003b4e3  push    rsi
0x18003b4e4  push    rdi
0x18003b4e5  mov     rbp, rsp
0x18003b4e8  sub     rsp, 48h
0x18003b4ec  mov     bl, dl
0x18003b4ee  mov     rdi, rcx
0x18003b4f1  add     rcx, 20h ; ' '; this
0x18003b4f5  mov     [rbp+var_28], rcx
0x18003b4f9  mov     [rbp+var_20], 0
0x18003b4fd  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18003b502  mov     [rbp+var_20], 1
0x18003b506  lea     rsi, [rdi+0B8h]
0x18003b50d  test    bl, bl
0x18003b50f  jz      short loc_18003B516
0x18003b511  cmp     byte ptr [rsi], 0
0x18003b514  jnz     short loc_18003B58E
0x18003b516  lea     rbx, [rdi+10h]
0x18003b51a  mov     rcx, rbx
0x18003b51d  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x18003b523  test    al, al
0x18003b525  jnz     short loc_18003B599
0x18003b527  mov     byte ptr [rsi], 1
0x18003b52a  cmp     [rdi+0C2h], al
0x18003b530  jnz     short loc_18003B54C
0x18003b532  mov     byte ptr [rdi+0C2h], 1
0x18003b539  mov     rax, [rdi]
0x18003b53c  lea     rdx, [rbp+var_28]
0x18003b540  mov     rcx, rdi
0x18003b543  mov     rax, [rax+20h]
0x18003b547  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b54c  cmp     dword ptr [rdi+0BCh], 0
0x18003b553  jz      short loc_18003B57E
0x18003b555  mov     rcx, rbx
0x18003b558  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x18003b55e  test    al, al
0x18003b560  jnz     short loc_18003B5C1
0x18003b562  cmp     [rbp+var_20], al
0x18003b565  jz      short loc_18003B571
0x18003b567  mov     rcx, [rbp+var_28]; _Mtx_t
0x18003b56b  call    cs:__imp__Mtx_unlock
0x18003b571  lea     rax, [rdi+0Ch]
0x18003b575  add     rsp, 48h
0x18003b579  pop     rdi
0x18003b57a  pop     rsi
0x18003b57b  pop     rbx
0x18003b57c  pop     rbp
0x18003b57d  retn
0x18003b57e  mov     rdx, [rbp+var_28]; _Mtx_t
0x18003b582  lea     rcx, [rdi+70h]; _Cnd_t
0x18003b586  call    cs:__imp__Cnd_wait
0x18003b58c  jmp     short loc_18003B54C
0x18003b58e  mov     ecx, 2
0x18003b593  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x18003b599  xorps   xmm0, xmm0
0x18003b59c  movdqu  [rbp+var_18], xmm0
0x18003b5a1  mov     rdx, rbx
0x18003b5a4  lea     rcx, [rbp+var_18]
0x18003b5a8  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18003b5ae  lea     rax, [rbp+var_18]
0x18003b5b2  mov     [rbp+arg_0], rax
0x18003b5b6  lea     rcx, [rbp+var_18]
0x18003b5ba  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x18003b5c0  nop
0x18003b5c1  xorps   xmm0, xmm0
0x18003b5c4  movdqu  [rbp+var_18], xmm0
0x18003b5c9  mov     rdx, rbx
0x18003b5cc  lea     rcx, [rbp+var_18]
0x18003b5d0  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18003b5d6  lea     rax, [rbp+var_18]
0x18003b5da  mov     [rbp+arg_0], rax
0x18003b5de  lea     rcx, [rbp+var_18]
0x18003b5e2  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
```
