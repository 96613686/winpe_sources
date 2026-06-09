# CWbemErrorCache::ResetCurrentThreadError(void)

- ea: `0x180006440`
- end: `0x18000654a`
- name: `?ResetCurrentThreadError@CWbemErrorCache@@QEAAXXZ`
- size: `266`
- prototype: `void __fastcall(CWbemErrorCache *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800077d0`
- `0x1800079e0`
- `0x180012c90`

## callees

- `0x180006440`
- `0x180006550`
- `0x180033d68`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180006502`
- `OLEAUT32!__imp_SysFreeString` at `0x180006510`
- `OLEAUT32!__imp_SysFreeString` at `0x18000651e`
- `OLEAUT32!__imp_SysFreeString` at `0x180006502`
- `OLEAUT32!__imp_SysFreeString` at `0x180006510`
- `OLEAUT32!__imp_SysFreeString` at `0x18000651e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006489`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006452`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006452`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000653d`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000653d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CWbemErrorCache::ResetCurrentThreadError(CWbemErrorCache *this)
{
  DWORD CurrentThreadId; // esi
  void *v3; // rcx
  void *v4; // rdi
  _QWORD *v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  struct _COAUTHIDENTITY *v8; // rcx
  LPCRITICAL_SECTION v9; // [rsp+30h] [rbp+8h] BYREF

  CurrentThreadId = GetCurrentThreadId();
  CInCritSec::CInCritSec((CInCritSec *)&v9, (struct _RTL_CRITICAL_SECTION *)((char *)this + 8));
  v3 = (void *)*((_QWORD *)this + 6);
  v4 = v3;
  if ( v3 )
  {
    while ( CurrentThreadId != *((_DWORD *)v4 + 4) )
    {
      v4 = *(void **)v4;
      if ( !v4 )
        goto LABEL_2;
    }
    if ( v4 == v3 )
      *((_QWORD *)this + 6) = *(_QWORD *)v4;
    if ( *(_QWORD *)v4 )
      *(_QWORD *)(*(_QWORD *)v4 + 8LL) = *((_QWORD *)v4 + 1);
    v5 = (_QWORD *)*((_QWORD *)v4 + 1);
    if ( v5 )
      *v5 = *(_QWORD *)v4;
    v6 = *((_QWORD *)v4 + 8);
    if ( v6 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
      *((_QWORD *)v4 + 8) = 0;
    }
    v7 = *((_QWORD *)v4 + 7);
    if ( v7 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      *((_QWORD *)v4 + 7) = 0;
    }
    SysFreeString(*((BSTR *)v4 + 6));
    *((_QWORD *)v4 + 6) = 0;
    SysFreeString(*((BSTR *)v4 + 4));
    *((_QWORD *)v4 + 4) = 0;
    SysFreeString(*((BSTR *)v4 + 5));
    *((_QWORD *)v4 + 5) = 0;
    v8 = (struct _COAUTHIDENTITY *)*((_QWORD *)v4 + 3);
    if ( v8 )
    {
      WbemFreeAuthIdentity(v8);
      *((_QWORD *)v4 + 3) = 0;
    }
    CWin32DefaultArena::WbemMemFree(v4);
  }
LABEL_2:
  LeaveCriticalSection(v9);
}

```

## disassembly

```asm
0x180006440  mov     [rsp+arg_8], rbx
0x180006445  mov     [rsp+arg_10], rsi
0x18000644a  push    rdi
0x18000644b  sub     rsp, 20h
0x18000644f  mov     rbx, rcx
0x180006452  call    cs:__imp_GetCurrentThreadId
0x180006458  mov     esi, eax
0x18000645a  lea     rdx, [rbx+8]; struct _RTL_CRITICAL_SECTION *
0x18000645e  lea     rcx, [rsp+28h+arg_0]; this
0x180006463  call    ??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x180006468  nop
0x180006469  mov     rcx, [rbx+30h]
0x18000646d  mov     rdi, rcx
0x180006470  test    rcx, rcx
0x180006473  jnz     short loc_180006490
0x180006475  mov     rcx, [rsp+28h+arg_0]
0x18000647a  mov     rbx, [rsp+28h+arg_8]
0x18000647f  mov     rsi, [rsp+28h+arg_10]
0x180006484  add     rsp, 20h
0x180006488  pop     rdi
0x180006489  jmp     cs:__imp_LeaveCriticalSection
0x180006490  cmp     esi, [rdi+10h]
0x180006493  jz      short loc_18000649F
0x180006495  mov     rdi, [rdi]
0x180006498  test    rdi, rdi
0x18000649b  jnz     short loc_180006490
0x18000649d  jmp     short loc_180006475
0x18000649f  cmp     rdi, rcx
0x1800064a2  jnz     short loc_1800064AB
0x1800064a4  mov     rax, [rdi]
0x1800064a7  mov     [rbx+30h], rax
0x1800064ab  mov     rcx, [rdi]
0x1800064ae  test    rcx, rcx
0x1800064b1  jz      short loc_1800064BB
0x1800064b3  mov     rax, [rdi+8]
0x1800064b7  mov     [rcx+8], rax
0x1800064bb  mov     rcx, [rdi+8]
0x1800064bf  test    rcx, rcx
0x1800064c2  jz      short loc_1800064CA
0x1800064c4  mov     rax, [rdi]
0x1800064c7  mov     [rcx], rax
0x1800064ca  mov     rcx, [rdi+40h]
0x1800064ce  xor     ebx, ebx
0x1800064d0  test    rcx, rcx
0x1800064d3  jz      short loc_1800064E5
0x1800064d5  mov     rax, [rcx]
0x1800064d8  mov     rax, [rax+10h]
0x1800064dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064e1  mov     [rdi+40h], rbx
0x1800064e5  mov     rcx, [rdi+38h]
0x1800064e9  test    rcx, rcx
0x1800064ec  jz      short loc_1800064FE
0x1800064ee  mov     rax, [rcx]
0x1800064f1  mov     rax, [rax+10h]
0x1800064f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064fa  mov     [rdi+38h], rbx
0x1800064fe  mov     rcx, [rdi+30h]; bstrString
0x180006502  call    cs:__imp_SysFreeString
0x180006508  mov     [rdi+30h], rbx
0x18000650c  mov     rcx, [rdi+20h]; bstrString
0x180006510  call    cs:__imp_SysFreeString
0x180006516  mov     [rdi+20h], rbx
0x18000651a  mov     rcx, [rdi+28h]; bstrString
0x18000651e  call    cs:__imp_SysFreeString
0x180006524  mov     [rdi+28h], rbx
0x180006528  mov     rcx, [rdi+18h]; pv
0x18000652c  test    rcx, rcx
0x18000652f  jz      short loc_18000653A
0x180006531  call    ?WbemFreeAuthIdentity@@YAJPEAU_COAUTHIDENTITY@@@Z; WbemFreeAuthIdentity(_COAUTHIDENTITY *)
0x180006536  mov     [rdi+18h], rbx
0x18000653a  mov     rcx, rdi
0x18000653d  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180006543  nop
0x180006544  jmp     loc_180006475
```
