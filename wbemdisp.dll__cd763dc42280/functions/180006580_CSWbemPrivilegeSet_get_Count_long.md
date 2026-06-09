# CSWbemPrivilegeSet::get_Count(long *)

- ea: `0x180006580`
- end: `0x1800066fb`
- name: `?get_Count@CSWbemPrivilegeSet@@UEAAJPEAJ@Z`
- size: `379`
- prototype: `__int64 __fastcall(CSWbemPrivilegeSet *__hidden this, int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x1800050dc`
- `0x180006550`
- `0x180006580`
- `0x180033d68`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800066a3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800066b5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800066c7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800066a3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800066b5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800066c7`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18000659c`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18000659c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800065e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800065f0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800065e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800065f0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800065a9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800065a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800065bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800065bb`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800066ee`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800066ee`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSWbemPrivilegeSet::get_Count(CSWbemPrivilegeSet *this, int *a2)
{
  CWbemErrorCache *v4; // rsi
  DWORD CurrentThreadId; // ebp
  void *v6; // rcx
  void *v7; // r14
  _QWORD *v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  struct _COAUTHIDENTITY *v12; // rcx
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+48h] [rbp+10h] BYREF

  SetErrorInfo(0, 0);
  EnterCriticalSection(&g_csErrorCache);
  v4 = g_pErrorCache;
  if ( g_pErrorCache )
  {
    CurrentThreadId = GetCurrentThreadId();
    CInCritSec::CInCritSec((CInCritSec *)&lpCriticalSection, (struct _RTL_CRITICAL_SECTION *)((char *)v4 + 8));
    v6 = (void *)*((_QWORD *)v4 + 6);
    v7 = v6;
    if ( v6 )
    {
      while ( CurrentThreadId != *((_DWORD *)v7 + 4) )
      {
        v7 = *(void **)v7;
        if ( !v7 )
          goto LABEL_3;
      }
      if ( v7 == v6 )
        *((_QWORD *)v4 + 6) = *(_QWORD *)v7;
      if ( *(_QWORD *)v7 )
        *(_QWORD *)(*(_QWORD *)v7 + 8LL) = *((_QWORD *)v7 + 1);
      v9 = (_QWORD *)*((_QWORD *)v7 + 1);
      if ( v9 )
        *v9 = *(_QWORD *)v7;
      v10 = *((_QWORD *)v7 + 8);
      if ( v10 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
        *((_QWORD *)v7 + 8) = 0;
      }
      v11 = *((_QWORD *)v7 + 7);
      if ( v11 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
        *((_QWORD *)v7 + 7) = 0;
      }
      SysFreeString(*((BSTR *)v7 + 6));
      *((_QWORD *)v7 + 6) = 0;
      SysFreeString(*((BSTR *)v7 + 4));
      *((_QWORD *)v7 + 4) = 0;
      SysFreeString(*((BSTR *)v7 + 5));
      *((_QWORD *)v7 + 5) = 0;
      v12 = (struct _COAUTHIDENTITY *)*((_QWORD *)v7 + 3);
      if ( v12 )
      {
        WbemFreeAuthIdentity(v12);
        *((_QWORD *)v7 + 3) = 0;
      }
      CWin32DefaultArena::WbemMemFree(v7);
    }
LABEL_3:
    LeaveCriticalSection(lpCriticalSection);
  }
  LeaveCriticalSection(&g_csErrorCache);
  if ( a2 )
  {
    *a2 = *((_DWORD *)this + 30);
    return 0;
  }
  else
  {
    CDispatchHelp::RaiseException((CSWbemPrivilegeSet *)((char *)this + 32), -2147467259);
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x180006580  mov     [rsp+arg_0], rbx
0x180006585  mov     [rsp+arg_10], rbp
0x18000658a  push    rsi
0x18000658b  push    rdi
0x18000658c  push    r14
0x18000658e  sub     rsp, 20h
0x180006592  mov     rbx, rdx
0x180006595  mov     rdi, rcx
0x180006598  xor     edx, edx; perrinfo
0x18000659a  xor     ecx, ecx; dwReserved
0x18000659c  call    cs:__imp_SetErrorInfo
0x1800065a2  lea     rcx, ?g_csErrorCache@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800065a9  call    cs:__imp_EnterCriticalSection
0x1800065af  mov     rsi, cs:?g_pErrorCache@@3PEAVCWbemErrorCache@@EA; CWbemErrorCache * g_pErrorCache
0x1800065b6  test    rsi, rsi
0x1800065b9  jz      short loc_1800065E9
0x1800065bb  call    cs:__imp_GetCurrentThreadId
0x1800065c1  mov     ebp, eax
0x1800065c3  lea     rdx, [rsi+8]; struct _RTL_CRITICAL_SECTION *
0x1800065c7  lea     rcx, [rsp+38h+lpCriticalSection]; this
0x1800065cc  call    ??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x1800065d1  nop
0x1800065d2  mov     rcx, [rsi+30h]
0x1800065d6  mov     r14, rcx
0x1800065d9  test    rcx, rcx
0x1800065dc  jnz     short loc_18000662A
0x1800065de  mov     rcx, [rsp+38h+lpCriticalSection]; lpCriticalSection
0x1800065e3  call    cs:__imp_LeaveCriticalSection
0x1800065e9  lea     rcx, ?g_csErrorCache@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800065f0  call    cs:__imp_LeaveCriticalSection
0x1800065f6  test    rbx, rbx
0x1800065f9  jz      short loc_180006615
0x1800065fb  mov     eax, [rdi+78h]
0x1800065fe  mov     [rbx], eax
0x180006600  xor     eax, eax
0x180006602  mov     rbx, [rsp+38h+arg_0]
0x180006607  mov     rbp, [rsp+38h+arg_10]
0x18000660c  add     rsp, 20h
0x180006610  pop     r14
0x180006612  pop     rdi
0x180006613  pop     rsi
0x180006614  retn
0x180006615  lea     rcx, [rdi+20h]; this
0x180006619  mov     edx, 80004005h; int
0x18000661e  call    ?RaiseException@CDispatchHelp@@QEAAXJ@Z; CDispatchHelp::RaiseException(long)
0x180006623  mov     eax, 80004005h
0x180006628  jmp     short loc_180006602
0x18000662a  cmp     ebp, [r14+10h]
0x18000662e  jz      short loc_18000663A
0x180006630  mov     r14, [r14]
0x180006633  test    r14, r14
0x180006636  jnz     short loc_18000662A
0x180006638  jmp     short loc_1800065DE
0x18000663a  cmp     r14, rcx
0x18000663d  jnz     short loc_180006646
0x18000663f  mov     rax, [r14]
0x180006642  mov     [rsi+30h], rax
0x180006646  mov     rcx, [r14]
0x180006649  test    rcx, rcx
0x18000664c  jz      short loc_180006656
0x18000664e  mov     rax, [r14+8]
0x180006652  mov     [rcx+8], rax
0x180006656  mov     rcx, [r14+8]
0x18000665a  test    rcx, rcx
0x18000665d  jz      short loc_180006665
0x18000665f  mov     rax, [r14]
0x180006662  mov     [rcx], rax
0x180006665  mov     rcx, [r14+40h]
0x180006669  test    rcx, rcx
0x18000666c  jz      short loc_180006682
0x18000666e  mov     rax, [rcx]
0x180006671  mov     rax, [rax+10h]
0x180006675  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000667a  mov     qword ptr [r14+40h], 0
0x180006682  mov     rcx, [r14+38h]
0x180006686  test    rcx, rcx
0x180006689  jz      short loc_18000669F
0x18000668b  mov     rax, [rcx]
0x18000668e  mov     rax, [rax+10h]
0x180006692  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006697  mov     qword ptr [r14+38h], 0
0x18000669f  mov     rcx, [r14+30h]; bstrString
0x1800066a3  call    cs:__imp_SysFreeString
0x1800066a9  mov     qword ptr [r14+30h], 0
0x1800066b1  mov     rcx, [r14+20h]; bstrString
0x1800066b5  call    cs:__imp_SysFreeString
0x1800066bb  mov     qword ptr [r14+20h], 0
0x1800066c3  mov     rcx, [r14+28h]; bstrString
0x1800066c7  call    cs:__imp_SysFreeString
0x1800066cd  mov     qword ptr [r14+28h], 0
0x1800066d5  mov     rcx, [r14+18h]; pv
0x1800066d9  test    rcx, rcx
0x1800066dc  jz      short loc_1800066EB
0x1800066de  call    ?WbemFreeAuthIdentity@@YAJPEAU_COAUTHIDENTITY@@@Z; WbemFreeAuthIdentity(_COAUTHIDENTITY *)
0x1800066e3  mov     qword ptr [r14+18h], 0
0x1800066eb  mov     rcx, r14
0x1800066ee  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800066f4  nop
0x1800066f5  jmp     loc_1800065DE
```
