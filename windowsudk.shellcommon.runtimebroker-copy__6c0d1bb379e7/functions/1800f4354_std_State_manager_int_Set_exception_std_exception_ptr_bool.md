# std::_State_manager<int>::_Set_exception(std::exception_ptr,bool)

- ea: `0x1800f4354`
- end: `0x1800f444d`
- name: `?_Set_exception@?$_State_manager@H@std@@QEAAXVexception_ptr@2@_N@Z`
- size: `249`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18003b23c`
- `0x1800f42f8`

## callees

- `0x18003b61c`
- `0x18003b73c`
- `0x1800f4354`
- `0x180433a30`
- `0x1804a2010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x1800f4420`
- `msvcp_win!_Mtx_unlock` at `0x1800f4420`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800f4391`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800f43c4`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800f4391`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800f43c4`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x1800f43ee`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x1800f43ee`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800f440f`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800f442b`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800f440f`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800f442b`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800f4446`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall std::_State_manager<int>::_Set_exception(__int64 a1, void *a2)
{
  const void *v3; // rdx
  __int64 *v4; // rcx
  __int64 v5; // rdi
  __int128 v6; // [rsp+28h] [rbp-38h] BYREF
  _Mtx_t v7; // [rsp+38h] [rbp-28h] BYREF
  char v8; // [rsp+40h] [rbp-20h]
  __int128 v9; // [rsp+48h] [rbp-18h] BYREF

  if ( !(unsigned __int8)std::_State_manager<int>::valid() )
    std::_Throw_future_error2(4);
  v5 = *v4;
  v9 = 0;
  __ExceptionPtrCopy(&v9, v3);
  v7 = (_Mtx_t)(v5 + 32);
  std::_Mutex_base::lock((std::_Mutex_base *)(v5 + 32));
  v8 = 1;
  v6 = 0;
  __ExceptionPtrCopy(&v6, &v9);
  if ( *(_BYTE *)(v5 + 193) )
    std::_Throw_future_error2(3);
  __ExceptionPtrAssign((void *)(v5 + 16), &v6);
  (*(void (__fastcall **)(__int64, _Mtx_t *, _QWORD))(*(_QWORD *)v5 + 40LL))(v5, &v7, 0);
  __ExceptionPtrDestroy(&v6);
  if ( v8 )
    _Mtx_unlock(v7);
  __ExceptionPtrDestroy(&v9);
  __ExceptionPtrDestroy(a2);
}

```

## disassembly

```asm
0x1800f4354  mov     [rsp-8+arg_0], rbx
0x1800f4359  mov     [rsp-8+arg_10], rdi
0x1800f435e  mov     [rsp-8+arg_8], rdx
0x1800f4363  push    rbp
0x1800f4364  mov     rbp, rsp
0x1800f4367  sub     rsp, 60h
0x1800f436b  mov     rbx, rdx
0x1800f436e  call    ?valid@?$_State_manager@H@std@@QEBA_NXZ; std::_State_manager<int>::valid(void)
0x1800f4373  test    al, al
0x1800f4375  jnz     short loc_1800F4382
0x1800f4377  mov     ecx, 4
0x1800f437c  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x1800f4382  mov     rdi, [rcx]
0x1800f4385  xorps   xmm0, xmm0
0x1800f4388  movdqu  [rbp+var_18], xmm0
0x1800f438d  lea     rcx, [rbp+var_18]
0x1800f4391  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x1800f4397  lea     rax, [rbp+var_18]
0x1800f439b  mov     [rbp+arg_18], rax
0x1800f439f  lea     rcx, [rdi+20h]; this
0x1800f43a3  mov     [rbp+var_28], rcx
0x1800f43a7  mov     [rbp+var_20], 0
0x1800f43ab  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1800f43b0  mov     [rbp+var_20], 1
0x1800f43b4  xorps   xmm0, xmm0
0x1800f43b7  movdqu  [rbp+var_38], xmm0
0x1800f43bc  lea     rdx, [rbp+var_18]
0x1800f43c0  lea     rcx, [rbp+var_38]
0x1800f43c4  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x1800f43ca  lea     rax, [rbp+var_38]
0x1800f43ce  mov     [rbp+var_40], rax
0x1800f43d2  cmp     byte ptr [rdi+0C1h], 0
0x1800f43d9  jz      short loc_1800F43E6
0x1800f43db  mov     ecx, 3
0x1800f43e0  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x1800f43e6  lea     rcx, [rdi+10h]
0x1800f43ea  lea     rdx, [rbp+var_38]
0x1800f43ee  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x1800f43f4  mov     rax, [rdi]
0x1800f43f7  xor     r8d, r8d
0x1800f43fa  lea     rdx, [rbp+var_28]
0x1800f43fe  mov     rcx, rdi
0x1800f4401  mov     rax, [rax+28h]
0x1800f4405  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f440a  nop
0x1800f440b  lea     rcx, [rbp+var_38]
0x1800f440f  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1800f4415  nop
0x1800f4416  cmp     [rbp+var_20], 0
0x1800f441a  jz      short loc_1800F4427
0x1800f441c  mov     rcx, [rbp+var_28]; _Mtx_t
0x1800f4420  call    cs:__imp__Mtx_unlock
0x1800f4426  nop
0x1800f4427  lea     rcx, [rbp+var_18]
0x1800f442b  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1800f4431  nop
0x1800f4432  mov     rcx, rbx
0x1800f4435  lea     r11, [rsp+60h+var_s0]
0x1800f443a  mov     rbx, [r11+10h]
0x1800f443e  mov     rdi, [r11+20h]
0x1800f4442  mov     rsp, r11
0x1800f4445  pop     rbp
0x1800f4446  jmp     cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
```
