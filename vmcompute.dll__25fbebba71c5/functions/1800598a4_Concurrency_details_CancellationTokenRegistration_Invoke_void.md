# Concurrency::details::_CancellationTokenRegistration::_Invoke(void)

- ea: `0x1800598a4`
- end: `0x18005998a`
- name: `?_Invoke@_CancellationTokenRegistration@details@Concurrency@@AEAAXXZ`
- size: `230`
- prototype: `void __fastcall(Concurrency::details::_CancellationTokenRegistration *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180059a20`

## callees

- `0x1800598a4`
- `0x180086010`

## import_xrefs

- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x1800598b1`
- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x1800598b1`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180059906`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18005992e`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180059906`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18005992e`
- `msvcp_win!_Mtx_lock` at `0x1800598f3`
- `msvcp_win!_Mtx_lock` at `0x1800598f3`
- `msvcp_win!_Mtx_unlock` at `0x180059946`
- `msvcp_win!_Mtx_unlock` at `0x180059946`
- `msvcp_win!_Cnd_broadcast` at `0x180059956`
- `msvcp_win!_Cnd_broadcast` at `0x180059956`

## pseudocode

```c
void __fastcall Concurrency::details::_CancellationTokenRegistration::_Invoke(
        Concurrency::details::_CancellationTokenRegistration *this)
{
  signed __int32 CurrentThreadId; // edi
  signed __int32 v3; // eax

  CurrentThreadId = Concurrency::details::platform::GetCurrentThreadId(this);
  if ( !_InterlockedCompareExchange((volatile signed __int32 *)this + 4, CurrentThreadId, 0) )
  {
    (*(void (__fastcall **)(Concurrency::details::_CancellationTokenRegistration *))(*(_QWORD *)this + 16LL))(this);
    v3 = _InterlockedCompareExchange((volatile signed __int32 *)this + 4, 3, CurrentThreadId);
    if ( CurrentThreadId != v3 )
      CurrentThreadId = v3;
    if ( CurrentThreadId == 2 )
    {
      if ( _Mtx_lock((Concurrency::details::_CancellationTokenRegistration *)((char *)this + 96)) )
      {
        std::_Throw_Cpp_error(5);
        __debugbreak();
      }
      if ( *((_DWORD *)this + 43) == 0x7FFFFFFF )
      {
        *((_DWORD *)this + 43) = 2147483646;
        std::_Throw_Cpp_error(6);
        __debugbreak();
      }
      *((_BYTE *)this + 176) = 1;
      _Mtx_unlock((Concurrency::details::_CancellationTokenRegistration *)((char *)this + 96));
      _Cnd_broadcast((Concurrency::details::_CancellationTokenRegistration *)((char *)this + 24));
    }
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 2, 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(Concurrency::details::_CancellationTokenRegistration *))(*(_QWORD *)this + 8LL))(this);
}

```

## disassembly

```asm
0x1800598a4  mov     [rsp+arg_8], rbx
0x1800598a9  push    rdi
0x1800598aa  sub     rsp, 20h
0x1800598ae  mov     rbx, rcx
0x1800598b1  call    cs:__imp_?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ; Concurrency::details::platform::GetCurrentThreadId(void)
0x1800598b8  nop     dword ptr [rax+rax+00h]
0x1800598bd  mov     edi, eax
0x1800598bf  xor     eax, eax
0x1800598c1  lock cmpxchg [rbx+10h], edi
0x1800598c6  jnz     loc_180059962
0x1800598cc  mov     rax, [rbx]
0x1800598cf  mov     rcx, rbx
0x1800598d2  mov     rax, [rax+10h]
0x1800598d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800598db  mov     ecx, 3
0x1800598e0  mov     eax, edi
0x1800598e2  lock cmpxchg [rbx+10h], ecx
0x1800598e7  cmovnz  edi, eax
0x1800598ea  cmp     edi, 2
0x1800598ed  jnz     short loc_180059962
0x1800598ef  lea     rcx, [rbx+60h]; _Mtx_t
0x1800598f3  call    cs:__imp__Mtx_lock
0x1800598fa  nop     dword ptr [rax+rax+00h]
0x1800598ff  test    eax, eax
0x180059901  jz      short loc_180059913
0x180059903  lea     ecx, [rdi+3]
0x180059906  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18005990d  nop     dword ptr [rax+rax+00h]
0x180059912  int     3; Trap to Debugger
0x180059913  cmp     dword ptr [rbx+0ACh], 7FFFFFFFh
0x18005991d  jnz     short loc_18005993B
0x18005991f  mov     ecx, 6
0x180059924  mov     dword ptr [rbx+0ACh], 7FFFFFFEh
0x18005992e  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180059935  nop     dword ptr [rax+rax+00h]
0x18005993a  int     3; Trap to Debugger
0x18005993b  lea     rcx, [rbx+60h]; _Mtx_t
0x18005993f  mov     byte ptr [rbx+0B0h], 1
0x180059946  call    cs:__imp__Mtx_unlock
0x18005994d  nop     dword ptr [rax+rax+00h]
0x180059952  lea     rcx, [rbx+18h]; _Cnd_t
0x180059956  call    cs:__imp__Cnd_broadcast
0x18005995d  nop     dword ptr [rax+rax+00h]
0x180059962  or      eax, 0FFFFFFFFh
0x180059965  lock xadd [rbx+8], eax
0x18005996a  cmp     eax, 1
0x18005996d  jnz     short loc_18005997E
0x18005996f  mov     rax, [rbx]
0x180059972  mov     rcx, rbx
0x180059975  mov     rax, [rax+8]
0x180059979  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005997e  mov     rbx, [rsp+28h+arg_8]
0x180059983  add     rsp, 20h
0x180059987  pop     rdi
0x180059988  retn
```
