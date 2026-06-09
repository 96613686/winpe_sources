# Promise<void>::~Promise<void>(void)

- ea: `0x14003e4a0`
- end: `0x14003e5d6`
- name: `??1?$Promise@X@@QEAA@XZ`
- size: `310`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140041140`

## callees

- `0x1400061a6`
- `0x14003e4a0`
- `0x140060f58`
- `0x1400675f4`
- `0x1400a8010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x14003e510`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x14003e510`
- `msvcp_win!?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z` at `0x14003e525`
- `msvcp_win!?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z` at `0x14003e525`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x14003e54c`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x14003e54c`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x14003e4e2`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x14003e4e2`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x14003e557`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x14003e557`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Promise<void>::~Promise<void>(__int64 *a1)
{
  __int64 v2; // rcx
  ErrorCodeException *v3; // rbx
  Threading::Event *v4; // rcx
  volatile signed __int32 *v5; // rbx
  __int128 v6; // [rsp+20h] [rbp-58h] BYREF
  __int64 v7; // [rsp+30h] [rbp-48h] BYREF
  _QWORD *v8; // [rsp+38h] [rbp-40h]
  _BYTE v9[48]; // [rsp+48h] [rbp-30h] BYREF

  v2 = *a1;
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)(v2 + 8) + 48LL))(v2 + 8, &v7);
    if ( !v8[7] && !__ExceptionPtrToBool(v8 + 4) )
    {
      v3 = ErrorCodeException::ErrorCodeException((ErrorCodeException *)v9, -2147467259);
      v6 = 0;
      __ExceptionPtrCreate(&v6);
      __ExceptionPtrCopyException(&v6, v3, &TI2_AVErrorCodeException__);
      *(_QWORD *)v3 = &std::exception::`vftable';
      o___std_exception_destroy_0((char *)v3 + 8);
      __ExceptionPtrAssign(v8 + 4, &v6);
      __ExceptionPtrDestroy(&v6);
      v4 = (Threading::Event *)v8[3];
      if ( v4 )
        Threading::Event::Set(v4);
    }
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 24LL))(v7);
  }
  v5 = (volatile signed __int32 *)a1[1];
  if ( v5 && _InterlockedExchangeAdd(v5 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v5)(v5);
    if ( !_InterlockedDecrement(v5 + 3) )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 8LL))(v5);
  }
}

```

## disassembly

```asm
0x14003e4a0  mov     [rsp+arg_8], rbx
0x14003e4a5  push    rdi
0x14003e4a6  sub     rsp, 70h
0x14003e4aa  mov     rdi, rcx
0x14003e4ad  mov     rcx, [rcx]
0x14003e4b0  test    rcx, rcx
0x14003e4b3  jz      loc_14003E588
0x14003e4b9  add     rcx, 8
0x14003e4bd  mov     rax, [rcx]
0x14003e4c0  lea     rdx, [rsp+78h+var_48]
0x14003e4c5  mov     rax, [rax+30h]
0x14003e4c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003e4ce  mov     rcx, [rsp+78h+var_40]
0x14003e4d3  cmp     qword ptr [rcx+38h], 0
0x14003e4d8  jnz     loc_14003E571
0x14003e4de  add     rcx, 20h ; ' '
0x14003e4e2  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x14003e4e8  test    al, al
0x14003e4ea  jnz     loc_14003E571
0x14003e4f0  mov     edx, 80004005h; int
0x14003e4f5  lea     rcx, [rsp+78h+var_30]; this
0x14003e4fa  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x14003e4ff  mov     rbx, rax
0x14003e502  xorps   xmm0, xmm0
0x14003e505  movdqu  [rsp+78h+var_58], xmm0
0x14003e50b  lea     rcx, [rsp+78h+var_58]
0x14003e510  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x14003e516  lea     r8, _TI2?AVErrorCodeException@@; throw info for 'class ErrorCodeException'
0x14003e51d  mov     rdx, rbx
0x14003e520  lea     rcx, [rsp+78h+var_58]
0x14003e525  call    cs:__imp_?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z; __ExceptionPtrCopyException(void *,void const *,void const *)
0x14003e52b  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x14003e532  mov     [rbx], rax
0x14003e535  lea     rcx, [rbx+8]
0x14003e539  call    _o___std_exception_destroy_0
0x14003e53e  mov     rcx, [rsp+78h+var_40]
0x14003e543  add     rcx, 20h ; ' '
0x14003e547  lea     rdx, [rsp+78h+var_58]
0x14003e54c  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x14003e552  lea     rcx, [rsp+78h+var_58]
0x14003e557  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x14003e55d  mov     rax, [rsp+78h+var_40]
0x14003e562  mov     rcx, [rax+18h]; this
0x14003e566  test    rcx, rcx
0x14003e569  jz      short loc_14003E571
0x14003e56b  call    ?Set@Event@Threading@@QEAAXXZ; Threading::Event::Set(void)
0x14003e570  nop
0x14003e571  mov     rcx, [rsp+78h+var_48]
0x14003e576  test    rcx, rcx
0x14003e579  jz      short loc_14003E588
0x14003e57b  mov     rax, [rcx]
0x14003e57e  mov     rax, [rax+18h]
0x14003e582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003e587  nop
0x14003e588  mov     rbx, [rdi+8]
0x14003e58c  test    rbx, rbx
0x14003e58f  jz      short loc_14003E5C8
0x14003e591  or      edi, 0FFFFFFFFh
0x14003e594  mov     eax, edi
0x14003e596  lock xadd [rbx+8], eax
0x14003e59b  add     eax, edi
0x14003e59d  jnz     short loc_14003E5C8
0x14003e59f  mov     rax, [rbx]
0x14003e5a2  mov     rcx, rbx
0x14003e5a5  mov     rax, [rax]
0x14003e5a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003e5ad  mov     eax, edi
0x14003e5af  lock xadd [rbx+0Ch], eax
0x14003e5b4  add     eax, edi
0x14003e5b6  jnz     short loc_14003E5C8
0x14003e5b8  mov     rax, [rbx]
0x14003e5bb  mov     rcx, rbx
0x14003e5be  mov     rax, [rax+8]
0x14003e5c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003e5c7  nop
0x14003e5c8  mov     rbx, [rsp+78h+arg_8]
0x14003e5d0  add     rsp, 70h
0x14003e5d4  pop     rdi
0x14003e5d5  retn
```
