# TransportRelay::~TransportRelay(void)

- ea: `0x1400ee6d8`
- end: `0x1400ee91d`
- name: `??1TransportRelay@@QEAA@XZ`
- size: `581`
- prototype: `void __fastcall(TransportRelay *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1400f2350`
- `0x1400fd343`

## callees

- `0x140008760`
- `0x14000ea44`
- `0x1400ee6d8`
- `0x1400eff44`
- `0x1400fe010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1400ee747`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1400ee747`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400ee713`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400ee72d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400ee713`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400ee72d`

## string_xrefs

- `0x1400ee8f4`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1400ee90b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall TransportRelay::~TransportRelay(TransportRelay *this)
{
  void *v2; // rcx
  const char *v3; // r9
  void *v4; // rcx
  const char *v5; // r9
  struct _TP_WORK *v6; // rcx
  volatile signed __int32 *v7; // rdi
  volatile signed __int32 *v8; // rdi
  volatile signed __int32 *v9; // rcx
  volatile signed __int32 *v10; // rdi
  volatile signed __int32 *v11; // rdi
  volatile signed __int32 *v12; // rdi
  volatile signed __int32 *v13; // rbx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *(_QWORD *)this = &TransportRelay::`vftable';
  TransportRelay::Stop(this, 0);
  std::wstring::~wstring((char *)this + 200);
  v2 = (void *)*((_QWORD *)this + 24);
  if ( v2 && !CloseHandle(v2) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v3);
  v4 = (void *)*((_QWORD *)this + 23);
  if ( v4 && !CloseHandle(v4) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v5);
  v6 = (struct _TP_WORK *)*((_QWORD *)this + 22);
  if ( v6 )
    CloseThreadpoolWork(v6);
  v7 = (volatile signed __int32 *)*((_QWORD *)this + 21);
  if ( v7 )
  {
    if ( !_InterlockedDecrement(v7 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
      if ( !_InterlockedDecrement(v7 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
    }
  }
  v8 = (volatile signed __int32 *)*((_QWORD *)this + 19);
  if ( v8 )
  {
    if ( !_InterlockedDecrement(v8 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
      if ( !_InterlockedDecrement(v8 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
    }
  }
  v9 = (volatile signed __int32 *)*((_QWORD *)this + 10);
  if ( v9 && !_InterlockedDecrement(v9 + 3) )
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
  v10 = (volatile signed __int32 *)*((_QWORD *)this + 8);
  if ( v10 )
  {
    if ( !_InterlockedDecrement(v10 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
      if ( !_InterlockedDecrement(v10 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
    }
  }
  v11 = (volatile signed __int32 *)*((_QWORD *)this + 6);
  if ( v11 )
  {
    if ( !_InterlockedDecrement(v11 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
      if ( !_InterlockedDecrement(v11 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
    }
  }
  v12 = (volatile signed __int32 *)*((_QWORD *)this + 4);
  if ( v12 )
  {
    if ( !_InterlockedDecrement(v12 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
      if ( !_InterlockedDecrement(v12 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
    }
  }
  v13 = (volatile signed __int32 *)*((_QWORD *)this + 2);
  if ( v13 && !_InterlockedDecrement(v13 + 2) )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
    if ( !_InterlockedDecrement(v13 + 3) )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
  }
}

```

## disassembly

```asm
0x1400ee6d8  mov     [rsp+arg_0], rbx
0x1400ee6dd  mov     [rsp+arg_8], rsi
0x1400ee6e2  push    rdi
0x1400ee6e3  sub     rsp, 20h
0x1400ee6e7  mov     rbx, rcx
0x1400ee6ea  lea     rax, ??_7TransportRelay@@6B@; const TransportRelay::`vftable'
0x1400ee6f1  mov     [rcx], rax
0x1400ee6f4  xor     edx, edx; bool
0x1400ee6f6  call    ?Stop@TransportRelay@@QEAAX_N@Z; TransportRelay::Stop(bool)
0x1400ee6fb  lea     rcx, [rbx+0C8h]; void *
0x1400ee702  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400ee707  mov     rcx, [rbx+0C0h]; hObject
0x1400ee70e  test    rcx, rcx
0x1400ee711  jz      short loc_1400EE721
0x1400ee713  call    cs:__imp_CloseHandle
0x1400ee719  test    eax, eax
0x1400ee71b  jz      loc_1400EE906
0x1400ee721  mov     rcx, [rbx+0B8h]; hObject
0x1400ee728  test    rcx, rcx
0x1400ee72b  jz      short loc_1400EE73B
0x1400ee72d  call    cs:__imp_CloseHandle
0x1400ee733  test    eax, eax
0x1400ee735  jz      loc_1400EE8EF
0x1400ee73b  mov     rcx, [rbx+0B0h]; pwk
0x1400ee742  test    rcx, rcx
0x1400ee745  jz      short loc_1400EE74D
0x1400ee747  call    cs:__imp_CloseThreadpoolWork
0x1400ee74d  mov     rdi, [rbx+0A8h]
0x1400ee754  or      esi, 0FFFFFFFFh
0x1400ee757  test    rdi, rdi
0x1400ee75a  jz      short loc_1400EE78F
0x1400ee75c  mov     eax, esi
0x1400ee75e  lock xadd [rdi+8], eax
0x1400ee763  add     eax, esi
0x1400ee765  jnz     short loc_1400EE78F
0x1400ee767  mov     rax, [rdi]
0x1400ee76a  mov     rcx, rdi
0x1400ee76d  mov     rax, [rax]
0x1400ee770  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400ee775  mov     eax, esi
0x1400ee777  lock xadd [rdi+0Ch], eax
0x1400ee77c  add     eax, esi
0x1400ee77e  jnz     short loc_1400EE78F
0x1400ee780  mov     rax, [rdi]
0x1400ee783  mov     rcx, rdi
0x1400ee786  mov     rax, [rax+8]
0x1400ee78a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400ee78f  mov     rdi, [rbx+98h]
0x1400ee796  test    rdi, rdi
0x1400ee799  jz      short loc_1400EE7CE
0x1400ee79b  mov     eax, esi
0x1400ee79d  lock xadd [rdi+8], eax
0x1400ee7a2  add     eax, esi
0x1400ee7a4  jnz     short loc_1400EE7CE
0x1400ee7a6  mov     rax, [rdi]
0x1400ee7a9  mov     rcx, rdi
0x1400ee7ac  mov     rax, [rax]
0x1400ee7af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400ee7b4  mov     eax, esi
0x1400ee7b6  lock xadd [rdi+0Ch], eax
0x1400ee7bb  add     eax, esi
0x1400ee7bd  jnz     short loc_1400EE7CE
0x1400ee7bf  mov     rax, [rdi]
0x1400ee7c2  mov     rcx, rdi
0x1400ee7c5  mov     rax, [rax+8]
0x1400ee7c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400ee7ce  mov     rcx, [rbx+50h]
0x1400ee7d2  test    rcx, rcx
0x1400ee7d5  jz      short loc_1400EE7EE
0x1400ee7d7  mov     eax, esi
0x1400ee7d9  lock xadd [rcx+0Ch], eax
0x1400ee7de  add     eax, esi
0x1400ee7e0  jnz     short loc_1400EE7EE
0x1400ee7e2  mov     rax, [rcx]
0x1400ee7e5  mov     rax, [rax+8]
0x1400ee7e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400ee7ee  mov     rdi, [rbx+40h]
0x1400ee7f2  test    rdi, rdi
0x1400ee7f5  jz      short loc_1400EE82A
0x1400ee7f7  mov     eax, esi
0x1400ee7f9  lock xadd [rdi+8], eax
0x1400ee7fe  add     eax, esi
0x1400ee800  jnz     short loc_1400EE82A
0x1400ee802  mov     rax, [rdi]
0x1400ee805  mov     rcx, rdi
0x1400ee808  mov     rax, [rax]
0x1400ee80b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400ee810  mov     eax, esi
0x1400ee812  lock xadd [rdi+0Ch], eax
0x1400ee817  add     eax, esi
0x1400ee819  jnz     short loc_1400EE82A
0x1400ee81b  mov     rax, [rdi]
0x1400ee81e  mov     rcx, rdi
0x1400ee821  mov     rax, [rax+8]
0x1400ee825  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400ee82a  mov     rdi, [rbx+30h]
0x1400ee82e  test    rdi, rdi
0x1400ee831  jz      short loc_1400EE866
0x1400ee833  mov     eax, esi
0x1400ee835  lock xadd [rdi+8], eax
0x1400ee83a  add     eax, esi
0x1400ee83c  jnz     short loc_1400EE866
0x1400ee83e  mov     rax, [rdi]
0x1400ee841  mov     rcx, rdi
0x1400ee844  mov     rax, [rax]
0x1400ee847  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400ee84c  mov     eax, esi
0x1400ee84e  lock xadd [rdi+0Ch], eax
0x1400ee853  add     eax, esi
0x1400ee855  jnz     short loc_1400EE866
0x1400ee857  mov     rax, [rdi]
0x1400ee85a  mov     rcx, rdi
0x1400ee85d  mov     rax, [rax+8]
0x1400ee861  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400ee866  mov     rdi, [rbx+20h]
0x1400ee86a  test    rdi, rdi
0x1400ee86d  jz      short loc_1400EE8A2
0x1400ee86f  mov     eax, esi
0x1400ee871  lock xadd [rdi+8], eax
0x1400ee876  add     eax, esi
0x1400ee878  jnz     short loc_1400EE8A2
0x1400ee87a  mov     rax, [rdi]
0x1400ee87d  mov     rcx, rdi
0x1400ee880  mov     rax, [rax]
0x1400ee883  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400ee888  mov     eax, esi
0x1400ee88a  lock xadd [rdi+0Ch], eax
0x1400ee88f  add     eax, esi
0x1400ee891  jnz     short loc_1400EE8A2
0x1400ee893  mov     rax, [rdi]
0x1400ee896  mov     rcx, rdi
0x1400ee899  mov     rax, [rax+8]
0x1400ee89d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400ee8a2  mov     rbx, [rbx+10h]
0x1400ee8a6  test    rbx, rbx
0x1400ee8a9  jz      short loc_1400EE8DF
0x1400ee8ab  mov     eax, esi
0x1400ee8ad  lock xadd [rbx+8], eax
0x1400ee8b2  add     eax, esi
0x1400ee8b4  jnz     short loc_1400EE8DF
0x1400ee8b6  mov     rax, [rbx]
0x1400ee8b9  mov     rcx, rbx
0x1400ee8bc  mov     rax, [rax]
0x1400ee8bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400ee8c4  mov     eax, esi
0x1400ee8c6  lock xadd [rbx+0Ch], eax
0x1400ee8cb  add     eax, esi
0x1400ee8cd  jnz     short loc_1400EE8DF
0x1400ee8cf  mov     rax, [rbx]
0x1400ee8d2  mov     rcx, rbx
0x1400ee8d5  mov     rax, [rax+8]
0x1400ee8d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400ee8de  nop
0x1400ee8df  mov     rbx, [rsp+28h+arg_0]
0x1400ee8e4  mov     rsi, [rsp+28h+arg_8]
0x1400ee8e9  add     rsp, 20h
0x1400ee8ed  pop     rdi
0x1400ee8ee  retn
0x1400ee8ef  mov     rcx, [rsp+28h]; this
0x1400ee8f4  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400ee8fb  mov     edx, 0A0Bh; void *
0x1400ee900  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400ee906  mov     rcx, [rsp+28h]; this
0x1400ee90b  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400ee912  mov     edx, 0A0Bh; void *
0x1400ee917  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
