# CWbemErrorCache::~CWbemErrorCache(void)

- ea: `0x1800186bc`
- end: `0x180018799`
- name: `??1CWbemErrorCache@@UEAA@XZ`
- size: `221`
- prototype: `void __fastcall(CWbemErrorCache *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180018680`

## callees

- `0x1800186bc`
- `0x180033d68`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180018721`
- `OLEAUT32!__imp_SysFreeString` at `0x180018733`
- `OLEAUT32!__imp_SysFreeString` at `0x180018745`
- `OLEAUT32!__imp_SysFreeString` at `0x180018721`
- `OLEAUT32!__imp_SysFreeString` at `0x180018733`
- `OLEAUT32!__imp_SysFreeString` at `0x180018745`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180018792`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180018770`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180018770`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CWbemErrorCache::~CWbemErrorCache(CWbemErrorCache *this)
{
  void *v2; // rbx
  __int64 v3; // rcx
  __int64 v4; // rcx
  struct _COAUTHIDENTITY *v5; // rcx
  void *v6; // rcx

  *(_QWORD *)this = &CWbemErrorCache::`vftable';
  v2 = (void *)*((_QWORD *)this + 6);
  while ( v2 )
  {
    *((_QWORD *)this + 6) = *(_QWORD *)v2;
    v3 = *((_QWORD *)v2 + 8);
    if ( v3 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
      *((_QWORD *)v2 + 8) = 0;
    }
    v4 = *((_QWORD *)v2 + 7);
    if ( v4 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
      *((_QWORD *)v2 + 7) = 0;
    }
    SysFreeString(*((BSTR *)v2 + 6));
    *((_QWORD *)v2 + 6) = 0;
    SysFreeString(*((BSTR *)v2 + 4));
    *((_QWORD *)v2 + 4) = 0;
    SysFreeString(*((BSTR *)v2 + 5));
    *((_QWORD *)v2 + 5) = 0;
    v5 = (struct _COAUTHIDENTITY *)*((_QWORD *)v2 + 3);
    if ( v5 )
    {
      WbemFreeAuthIdentity(v5);
      *((_QWORD *)v2 + 3) = 0;
    }
    v6 = v2;
    v2 = (void *)*((_QWORD *)this + 6);
    CWin32DefaultArena::WbemMemFree(v6);
  }
  *((_QWORD *)this + 6) = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x1800186bc  mov     [rsp+arg_0], rbx
0x1800186c1  push    rdi
0x1800186c2  sub     rsp, 20h
0x1800186c6  mov     rdi, rcx
0x1800186c9  lea     rax, ??_7CWbemErrorCache@@6B@; const CWbemErrorCache::`vftable'
0x1800186d0  mov     [rcx], rax
0x1800186d3  mov     rbx, [rcx+30h]
0x1800186d7  jmp     loc_180018777
0x1800186dc  mov     rax, [rbx]
0x1800186df  mov     [rdi+30h], rax
0x1800186e3  mov     rcx, [rbx+40h]
0x1800186e7  test    rcx, rcx
0x1800186ea  jz      short loc_180018700
0x1800186ec  mov     rax, [rcx]
0x1800186ef  mov     rax, [rax+10h]
0x1800186f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800186f8  mov     qword ptr [rbx+40h], 0
0x180018700  mov     rcx, [rbx+38h]
0x180018704  test    rcx, rcx
0x180018707  jz      short loc_18001871D
0x180018709  mov     rax, [rcx]
0x18001870c  mov     rax, [rax+10h]
0x180018710  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018715  mov     qword ptr [rbx+38h], 0
0x18001871d  mov     rcx, [rbx+30h]; bstrString
0x180018721  call    cs:__imp_SysFreeString
0x180018727  mov     qword ptr [rbx+30h], 0
0x18001872f  mov     rcx, [rbx+20h]; bstrString
0x180018733  call    cs:__imp_SysFreeString
0x180018739  mov     qword ptr [rbx+20h], 0
0x180018741  mov     rcx, [rbx+28h]; bstrString
0x180018745  call    cs:__imp_SysFreeString
0x18001874b  mov     qword ptr [rbx+28h], 0
0x180018753  mov     rcx, [rbx+18h]; pv
0x180018757  test    rcx, rcx
0x18001875a  jz      short loc_180018769
0x18001875c  call    ?WbemFreeAuthIdentity@@YAJPEAU_COAUTHIDENTITY@@@Z; WbemFreeAuthIdentity(_COAUTHIDENTITY *)
0x180018761  mov     qword ptr [rbx+18h], 0
0x180018769  mov     rcx, rbx
0x18001876c  mov     rbx, [rdi+30h]
0x180018770  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180018776  nop
0x180018777  test    rbx, rbx
0x18001877a  jnz     loc_1800186DC
0x180018780  mov     [rdi+30h], rbx
0x180018784  lea     rcx, [rdi+8]
0x180018788  mov     rbx, [rsp+28h+arg_0]
0x18001878d  add     rsp, 20h
0x180018791  pop     rdi
0x180018792  jmp     cs:__imp_DeleteCriticalSection
```
