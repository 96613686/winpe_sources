# p9fs::CancelToken::~CancelToken(void)

- ea: `0x18000e334`
- end: `0x18000e3b8`
- name: `??1CancelToken@p9fs@@QEAA@XZ`
- size: `132`
- prototype: `void __fastcall(p9fs::CancelToken *__hidden this)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x1800183c0`
- `0x180020600`
- `0x1800221d0`
- `0x1800245d4`
- `0x18002f579`
- `0x1800317f4`
- `0x180031825`
- `0x180031856`
- `0x1800321a1`
- `0x180032408`
- `0x180032646`
- `0x1800326f8`

## callees

- `0x18000e334`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000e35c`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000e378`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000e35c`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000e378`
- `msvcp_win!_Mtx_lock` at `0x18000e34d`
- `msvcp_win!_Mtx_lock` at `0x18000e34d`
- `msvcp_win!_Mtx_unlock` at `0x18000e39f`
- `msvcp_win!_Mtx_unlock` at `0x18000e39f`

## pseudocode

```c
void __fastcall p9fs::CancelToken::~CancelToken(p9fs::CancelToken *this)
{
  __int64 v2; // rbx
  p9fs::CancelToken **v3; // rdx
  p9fs::CancelToken **v4; // rcx

  v2 = *((_QWORD *)this + 12);
  if ( v2 )
  {
    if ( _Mtx_lock(*((_Mtx_t *)this + 12)) )
    {
      std::_Throw_Cpp_error(5);
      __debugbreak();
    }
    if ( *(_DWORD *)(v2 + 76) == 0x7FFFFFFF )
    {
      *(_DWORD *)(v2 + 76) = 2147483646;
      std::_Throw_Cpp_error(6);
      __debugbreak();
    }
    v3 = (p9fs::CancelToken **)*((_QWORD *)this + 15);
    if ( v3[1] != (p9fs::CancelToken *)((char *)this + 120)
      || (v4 = (p9fs::CancelToken **)*((_QWORD *)this + 16), *v4 != (p9fs::CancelToken *)((char *)this + 120)) )
    {
      __fastfail(3u);
    }
    *v4 = (p9fs::CancelToken *)v3;
    v3[1] = (p9fs::CancelToken *)v4;
    _Mtx_unlock((_Mtx_t)v2);
  }
}

```

## disassembly

```asm
0x18000e334  mov     [rsp+arg_0], rbx
0x18000e339  push    rdi
0x18000e33a  sub     rsp, 20h
0x18000e33e  mov     rdi, rcx
0x18000e341  mov     rbx, [rcx+60h]
0x18000e345  test    rbx, rbx
0x18000e348  jz      short loc_18000E3A6
0x18000e34a  mov     rcx, rbx; _Mtx_t
0x18000e34d  call    cs:__imp__Mtx_lock
0x18000e353  test    eax, eax
0x18000e355  jz      short loc_18000E363
0x18000e357  mov     ecx, 5
0x18000e35c  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18000e362  int     3; Trap to Debugger
0x18000e363  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x18000e36a  jnz     short loc_18000E37F
0x18000e36c  mov     dword ptr [rbx+4Ch], 7FFFFFFEh
0x18000e373  mov     ecx, 6
0x18000e378  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18000e37e  int     3; Trap to Debugger
0x18000e37f  lea     rax, [rdi+78h]
0x18000e383  mov     rdx, [rax]
0x18000e386  cmp     [rdx+8], rax
0x18000e38a  jnz     short loc_18000E3B1
0x18000e38c  mov     rcx, [rax+8]
0x18000e390  cmp     [rcx], rax
0x18000e393  jnz     short loc_18000E3B1
0x18000e395  mov     [rcx], rdx
0x18000e398  mov     [rdx+8], rcx
0x18000e39c  mov     rcx, rbx; _Mtx_t
0x18000e39f  call    cs:__imp__Mtx_unlock
0x18000e3a5  nop
0x18000e3a6  mov     rbx, [rsp+28h+arg_0]
0x18000e3ab  add     rsp, 20h
0x18000e3af  pop     rdi
0x18000e3b0  retn
0x18000e3b1  mov     ecx, 3
0x18000e3b6  int     29h; Win8: RtlFailFast(ecx)
```
