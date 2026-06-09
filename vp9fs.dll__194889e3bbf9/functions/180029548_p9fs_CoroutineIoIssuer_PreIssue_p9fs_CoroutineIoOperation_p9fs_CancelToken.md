# p9fs::CoroutineIoIssuer::PreIssue(p9fs::CoroutineIoOperation &,p9fs::CancelToken &)

- ea: `0x180029548`
- end: `0x1800295e6`
- name: `?PreIssue@CoroutineIoIssuer@p9fs@@AEAA_NAEAUCoroutineIoOperation@2@AEAVCancelToken@2@@Z`
- size: `158`
- prototype: `bool(p9fs::CoroutineIoIssuer *__hidden this, struct p9fs::CoroutineIoOperation *, struct p9fs::CancelToken *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180028b60`
- `0x180028c38`
- `0x180028d20`
- `0x180028e10`
- `0x180028ef4`

## callees

- `0x180029548`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18002957e`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18002959a`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18002957e`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18002959a`
- `msvcp_win!_Mtx_lock` at `0x18002956f`
- `msvcp_win!_Mtx_lock` at `0x18002956f`
- `msvcp_win!_Mtx_unlock` at `0x1800295ac`
- `msvcp_win!_Mtx_unlock` at `0x1800295ca`
- `msvcp_win!_Mtx_unlock` at `0x1800295ac`
- `msvcp_win!_Mtx_unlock` at `0x1800295ca`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1800295d3`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1800295d3`

## pseudocode

```c
__int64 __fastcall p9fs::CoroutineIoIssuer::PreIssue(
        p9fs::CoroutineIoIssuer *this,
        struct p9fs::CoroutineIoOperation *a2,
        struct p9fs::CancelToken *a3)
{
  __int64 result; // rax

  *((_QWORD *)a2 + 1) = *((_QWORD *)this + 1);
  *((_OWORD *)a2 + 1) = 0;
  *((_OWORD *)a2 + 2) = 0;
  if ( _Mtx_lock(a3) )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  if ( *((_DWORD *)a3 + 19) == 0x7FFFFFFF )
  {
    *((_DWORD *)a3 + 19) = 2147483646;
    std::_Throw_Cpp_error(6);
    __debugbreak();
  }
  if ( *((_BYTE *)a3 + 88) )
  {
    _Mtx_unlock(a3);
    result = 0;
    *((_QWORD *)a2 + 6) = 995;
    *((_BYTE *)a2 + 64) = 1;
  }
  else
  {
    *((_QWORD *)a3 + 10) = a2;
    _Mtx_unlock(a3);
    StartThreadpoolIo(*(PTP_IO *)this);
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x180029548  push    rbx
0x18002954a  push    rsi
0x18002954b  push    rdi
0x18002954c  sub     rsp, 20h
0x180029550  mov     rax, [rcx+8]
0x180029554  xorps   xmm0, xmm0
0x180029557  mov     rsi, rcx
0x18002955a  mov     [rdx+8], rax
0x18002955e  movups  xmmword ptr [rdx+10h], xmm0
0x180029562  mov     rcx, r8; _Mtx_t
0x180029565  mov     rbx, r8
0x180029568  movups  xmmword ptr [rdx+20h], xmm0
0x18002956c  mov     rdi, rdx
0x18002956f  call    cs:__imp__Mtx_lock
0x180029575  test    eax, eax
0x180029577  jz      short loc_180029585
0x180029579  mov     ecx, 5
0x18002957e  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180029584  int     3; Trap to Debugger
0x180029585  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x18002958c  jnz     short loc_1800295A1
0x18002958e  mov     ecx, 6
0x180029593  mov     dword ptr [rbx+4Ch], 7FFFFFFEh
0x18002959a  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800295a0  int     3; Trap to Debugger
0x1800295a1  mov     al, [rbx+58h]
0x1800295a4  mov     rcx, rbx; _Mtx_t
0x1800295a7  nop
0x1800295a8  test    al, al
0x1800295aa  jz      short loc_1800295C6
0x1800295ac  call    cs:__imp__Mtx_unlock
0x1800295b2  mov     eax, 1
0x1800295b7  mov     qword ptr [rdi+30h], 3E3h
0x1800295bf  xchg    al, [rdi+40h]
0x1800295c2  xor     al, al
0x1800295c4  jmp     short loc_1800295DE
0x1800295c6  mov     [rbx+50h], rdi
0x1800295ca  call    cs:__imp__Mtx_unlock
0x1800295d0  mov     rcx, [rsi]; pio
0x1800295d3  call    cs:__imp_StartThreadpoolIo
0x1800295d9  mov     eax, 1
0x1800295de  add     rsp, 20h
0x1800295e2  pop     rdi
0x1800295e3  pop     rsi
0x1800295e4  pop     rbx
0x1800295e5  retn
```
