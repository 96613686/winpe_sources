# ResetLastErrors(void)

- ea: `0x180006300`
- end: `0x180006437`
- name: `?ResetLastErrors@@YAXXZ`
- size: `311`
- prototype: `void(void)`
- caller_count: `234`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180001070`
- `0x1800012b0`
- `0x180001370`
- `0x1800015f0`
- `0x180001e14`
- `0x180001f70`
- `0x1800023b0`
- `0x180002610`
- `0x1800031b0`
- `0x180003420`
- `0x180003cb0`
- `0x180004dc0`
- `0x180004e10`
- `0x180004f90`
- `0x1800051d0`
- `0x1800052d0`
- `0x180005f20`
- `0x180008230`
- `0x180008800`
- `0x18000c960`
- `0x18000d3f0`
- `0x180012a30`
- `0x180012c90`
- `0x1800130d0`
- `0x180013310`
- `0x1800134d0`
- `0x180013aa0`
- `0x180014870`
- `0x180014b20`
- `0x180014fe0`
- `0x180015260`
- `0x180015770`
- `0x180015a20`
- `0x180016800`
- `0x1800168a0`
- `0x180016970`
- `0x180016de0`
- `0x180016ea4`
- `0x180017380`
- `0x180017700`
- `0x1800178e0`
- `0x180017c20`
- `0x180017d20`
- `0x180017e60`
- `0x180018ac0`
- `0x180018bf0`
- `0x180018ee0`
- `0x1800191d0`
- `0x1800192e0`
- `0x180019410`

## callees

- `0x180006300`
- `0x180006550`
- `0x180033d68`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800063ef`
- `OLEAUT32!__imp_SysFreeString` at `0x1800063fd`
- `OLEAUT32!__imp_SysFreeString` at `0x18000640b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800063ef`
- `OLEAUT32!__imp_SysFreeString` at `0x1800063fd`
- `OLEAUT32!__imp_SysFreeString` at `0x18000640b`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180006313`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180006313`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000635a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000635a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006376`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006320`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006320`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006332`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006332`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000642a`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000642a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void ResetLastErrors(void)
{
  CWbemErrorCache *v0; // rbx
  DWORD CurrentThreadId; // esi
  void *v2; // rcx
  void *v3; // rdi
  _QWORD *v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  struct _COAUTHIDENTITY *v7; // rcx
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+30h] [rbp+8h] BYREF

  SetErrorInfo(0, 0);
  EnterCriticalSection(&g_csErrorCache);
  v0 = g_pErrorCache;
  if ( g_pErrorCache )
  {
    CurrentThreadId = GetCurrentThreadId();
    CInCritSec::CInCritSec((CInCritSec *)&lpCriticalSection, (struct _RTL_CRITICAL_SECTION *)((char *)v0 + 8));
    v2 = (void *)*((_QWORD *)v0 + 6);
    v3 = v2;
    if ( v2 )
    {
      while ( CurrentThreadId != *((_DWORD *)v3 + 4) )
      {
        v3 = *(void **)v3;
        if ( !v3 )
          goto LABEL_3;
      }
      if ( v3 == v2 )
        *((_QWORD *)v0 + 6) = *(_QWORD *)v3;
      if ( *(_QWORD *)v3 )
        *(_QWORD *)(*(_QWORD *)v3 + 8LL) = *((_QWORD *)v3 + 1);
      v4 = (_QWORD *)*((_QWORD *)v3 + 1);
      if ( v4 )
        *v4 = *(_QWORD *)v3;
      v5 = *((_QWORD *)v3 + 8);
      if ( v5 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
        *((_QWORD *)v3 + 8) = 0;
      }
      v6 = *((_QWORD *)v3 + 7);
      if ( v6 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
        *((_QWORD *)v3 + 7) = 0;
      }
      SysFreeString(*((BSTR *)v3 + 6));
      *((_QWORD *)v3 + 6) = 0;
      SysFreeString(*((BSTR *)v3 + 4));
      *((_QWORD *)v3 + 4) = 0;
      SysFreeString(*((BSTR *)v3 + 5));
      *((_QWORD *)v3 + 5) = 0;
      v7 = (struct _COAUTHIDENTITY *)*((_QWORD *)v3 + 3);
      if ( v7 )
      {
        WbemFreeAuthIdentity(v7);
        *((_QWORD *)v3 + 3) = 0;
      }
      CWin32DefaultArena::WbemMemFree(v3);
    }
LABEL_3:
    LeaveCriticalSection(lpCriticalSection);
  }
  LeaveCriticalSection(&g_csErrorCache);
}

```

## disassembly

```asm
0x180006300  mov     [rsp+arg_8], rbx
0x180006305  mov     [rsp+arg_10], rsi
0x18000630a  push    rdi
0x18000630b  sub     rsp, 20h
0x18000630f  xor     edx, edx; perrinfo
0x180006311  xor     ecx, ecx; dwReserved
0x180006313  call    cs:__imp_SetErrorInfo
0x180006319  lea     rcx, ?g_csErrorCache@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180006320  call    cs:__imp_EnterCriticalSection
0x180006326  mov     rbx, cs:?g_pErrorCache@@3PEAVCWbemErrorCache@@EA; CWbemErrorCache * g_pErrorCache
0x18000632d  test    rbx, rbx
0x180006330  jz      short loc_180006360
0x180006332  call    cs:__imp_GetCurrentThreadId
0x180006338  mov     esi, eax
0x18000633a  lea     rdx, [rbx+8]; struct _RTL_CRITICAL_SECTION *
0x18000633e  lea     rcx, [rsp+28h+lpCriticalSection]; this
0x180006343  call    ??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x180006348  nop
0x180006349  mov     rcx, [rbx+30h]
0x18000634d  mov     rdi, rcx
0x180006350  test    rcx, rcx
0x180006353  jnz     short loc_18000637D
0x180006355  mov     rcx, [rsp+28h+lpCriticalSection]; lpCriticalSection
0x18000635a  call    cs:__imp_LeaveCriticalSection
0x180006360  lea     rcx, ?g_csErrorCache@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_csErrorCache
0x180006367  mov     rbx, [rsp+28h+arg_8]
0x18000636c  mov     rsi, [rsp+28h+arg_10]
0x180006371  add     rsp, 20h
0x180006375  pop     rdi
0x180006376  jmp     cs:__imp_LeaveCriticalSection
0x18000637d  cmp     esi, [rdi+10h]
0x180006380  jz      short loc_18000638C
0x180006382  mov     rdi, [rdi]
0x180006385  test    rdi, rdi
0x180006388  jnz     short loc_18000637D
0x18000638a  jmp     short loc_180006355
0x18000638c  cmp     rdi, rcx
0x18000638f  jnz     short loc_180006398
0x180006391  mov     rax, [rdi]
0x180006394  mov     [rbx+30h], rax
0x180006398  mov     rcx, [rdi]
0x18000639b  test    rcx, rcx
0x18000639e  jz      short loc_1800063A8
0x1800063a0  mov     rax, [rdi+8]
0x1800063a4  mov     [rcx+8], rax
0x1800063a8  mov     rcx, [rdi+8]
0x1800063ac  test    rcx, rcx
0x1800063af  jz      short loc_1800063B7
0x1800063b1  mov     rax, [rdi]
0x1800063b4  mov     [rcx], rax
0x1800063b7  mov     rcx, [rdi+40h]
0x1800063bb  xor     ebx, ebx
0x1800063bd  test    rcx, rcx
0x1800063c0  jz      short loc_1800063D2
0x1800063c2  mov     rax, [rcx]
0x1800063c5  mov     rax, [rax+10h]
0x1800063c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063ce  mov     [rdi+40h], rbx
0x1800063d2  mov     rcx, [rdi+38h]
0x1800063d6  test    rcx, rcx
0x1800063d9  jz      short loc_1800063EB
0x1800063db  mov     rax, [rcx]
0x1800063de  mov     rax, [rax+10h]
0x1800063e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063e7  mov     [rdi+38h], rbx
0x1800063eb  mov     rcx, [rdi+30h]; bstrString
0x1800063ef  call    cs:__imp_SysFreeString
0x1800063f5  mov     [rdi+30h], rbx
0x1800063f9  mov     rcx, [rdi+20h]; bstrString
0x1800063fd  call    cs:__imp_SysFreeString
0x180006403  mov     [rdi+20h], rbx
0x180006407  mov     rcx, [rdi+28h]; bstrString
0x18000640b  call    cs:__imp_SysFreeString
0x180006411  mov     [rdi+28h], rbx
0x180006415  mov     rcx, [rdi+18h]; pv
0x180006419  test    rcx, rcx
0x18000641c  jz      short loc_180006427
0x18000641e  call    ?WbemFreeAuthIdentity@@YAJPEAU_COAUTHIDENTITY@@@Z; WbemFreeAuthIdentity(_COAUTHIDENTITY *)
0x180006423  mov     [rdi+18h], rbx
0x180006427  mov     rcx, rdi
0x18000642a  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180006430  nop
0x180006431  jmp     loc_180006355
```
