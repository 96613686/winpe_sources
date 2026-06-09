# CDlpManager::GetTaskIndexByName(ushort const *,ulong *)

- ea: `0x18006000c`
- end: `0x1800601c6`
- name: `?GetTaskIndexByName@CDlpManager@@AEAAJPEBGPEAK@Z`
- size: `442`
- prototype: `int(CDlpManager *__hidden this, const unsigned __int16 *, unsigned int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180050120`
- `0x18005fc80`

## callees

- `0x18000aba4`
- `0x180012f5c`
- `0x18001fd60`
- `0x18006000c`
- `0x180081010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180060088`
- `OLEAUT32!__imp_SysFreeString` at `0x18006011f`
- `OLEAUT32!__imp_SysFreeString` at `0x180060088`
- `OLEAUT32!__imp_SysFreeString` at `0x18006011f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800600ef`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800600ef`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006005b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006005b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180060137`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180060137`

## string_xrefs

- `0x180060197`: `CDlpManager::GetTaskIndexByName`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDlpManager::GetTaskIndexByName(
        struct _RTL_CRITICAL_SECTION *this,
        const unsigned __int16 *a2,
        unsigned int *a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // r15
  OLECHAR *v7; // rax
  unsigned int RecursionCount; // r14d
  signed int v9; // edi
  __int64 v10; // rcx
  int v11; // ebx
  __int64 v13; // rax
  __int64 v14; // rcx
  int v15; // eax
  PCNZWCH lpString2; // [rsp+20h] [rbp-38h]
  __int64 cchCount2; // [rsp+28h] [rbp-30h]
  ULONG_PTR *p_SpinCount; // [rsp+38h] [rbp-20h]
  PCNZWCH v19; // [rsp+A0h] [rbp+48h] BYREF

  p_SpinCount = &this[4].SpinCount;
  v6 = this + 5;
  EnterCriticalSection(this + 5);
  v7 = 0;
  v19 = 0;
  RecursionCount = this[13].RecursionCount;
  v9 = 0;
  if ( !RecursionCount )
  {
LABEL_11:
    v11 = -2147023728;
    goto LABEL_12;
  }
  while ( 1 )
  {
    if ( v7 )
    {
      SysFreeString(v7);
      v19 = 0;
    }
    v10 = *((_QWORD *)this[13].OwningThread + v9);
    v11 = (*(__int64 (__fastcall **)(__int64, PCNZWCH *))(*(_QWORD *)v10 + 200LL))(v10, &v19);
    if ( v11 == -2147023728 )
    {
      v11 = 0;
      goto LABEL_7;
    }
    if ( v11 < 0 )
      break;
LABEL_7:
    v7 = (OLECHAR *)v19;
    if ( v19 )
    {
      if ( CompareStringW(0x409u, 1u, a2, -1, v19, -1) == 2 )
      {
        *a3 = v9;
        goto LABEL_12;
      }
      v7 = (OLECHAR *)v19;
    }
    if ( ++v9 >= RecursionCount )
      goto LABEL_11;
  }
  if ( ((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *))this[2].DebugInfo->ProcessLocksList.Flink)(&this[2]) )
  {
    v13 = ((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *))this[2].DebugInfo->ProcessLocksList.Flink)(&this[2]);
    v14 = 0;
    if ( v13 )
    {
      LODWORD(cchCount2) = v11;
      LODWORD(lpString2) = 2514;
      v15 = CDlpLogT<CEmptyType>::DlpLogFormat(
              v13,
              4,
              L"%s(%d): Result = 0x%X",
              L"CDlpManager::GetTaskIndexByName",
              lpString2,
              cchCount2,
              &CDlpAutoDelayLockT<CDlpAutoExclusiveAcquireLockT<CEmptyType>>::`vftable',
              p_SpinCount);
      v14 = (unsigned int)v15;
      if ( v15 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v15);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v14);
  }
LABEL_12:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v11);
  if ( v19 )
  {
    SysFreeString((BSTR)v19);
    v19 = 0;
  }
  LeaveCriticalSection(v6);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18006000c  push    rbp
0x18006000e  push    rbx
0x18006000f  push    rsi
0x180060010  push    rdi
0x180060011  push    r12
0x180060013  push    r13
0x180060015  push    r14
0x180060017  push    r15
0x180060019  mov     rbp, rsp
0x18006001c  sub     rsp, 58h
0x180060020  mov     r12, r8
0x180060023  mov     r13, rdx
0x180060026  mov     rsi, rcx
0x180060029  mov     [rbp+var_10], 0
0x180060031  xorps   xmm0, xmm0
0x180060034  xor     eax, eax
0x180060036  movups  [rbp+var_28], xmm0
0x18006003a  mov     [rbp+var_18], rax
0x18006003e  lea     rax, [rcx+0C0h]
0x180060045  mov     qword ptr [rbp+var_28+8], rax
0x180060049  lea     rcx, ??_7?$CDlpAutoDelayLockT@V?$CDlpAutoExclusiveAcquireLockT@VCEmptyType@@@@@@6B@; const CDlpAutoDelayLockT<CDlpAutoExclusiveAcquireLockT<CEmptyType>>::`vftable'
0x180060050  mov     qword ptr [rbp+var_28], rcx
0x180060054  lea     r15, [rax+8]
0x180060058  mov     rcx, r15; lpCriticalSection
0x18006005b  call    cs:__imp_EnterCriticalSection
0x180060061  mov     dword ptr [rbp+var_18], 1
0x180060068  xor     eax, eax
0x18006006a  mov     [rbp+arg_0], rax
0x18006006e  mov     r14d, [rsi+214h]
0x180060075  xor     edi, edi
0x180060077  test    r14d, r14d
0x18006007a  jz      loc_180060109
0x180060080  test    rax, rax
0x180060083  jz      short loc_180060096
0x180060085  mov     rcx, rax; bstrString
0x180060088  call    cs:__imp_SysFreeString
0x18006008e  mov     [rbp+arg_0], 0
0x180060096  mov     rcx, [rsi+218h]
0x18006009d  movsxd  rax, edi
0x1800600a0  mov     rcx, [rcx+rax*8]
0x1800600a4  mov     rax, [rcx]
0x1800600a7  lea     rdx, [rbp+arg_0]
0x1800600ab  mov     rax, [rax+0C8h]
0x1800600b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800600b7  mov     ebx, eax
0x1800600b9  cmp     eax, 80070490h
0x1800600be  jnz     short loc_1800600C4
0x1800600c0  xor     ebx, ebx
0x1800600c2  jmp     short loc_1800600CC
0x1800600c4  test    ebx, ebx
0x1800600c6  js      loc_18006015D
0x1800600cc  mov     rax, [rbp+arg_0]
0x1800600d0  test    rax, rax
0x1800600d3  jz      short loc_1800600FE
0x1800600d5  or      ecx, 0FFFFFFFFh
0x1800600d8  mov     dword ptr [rsp+58h+cchCount2], ecx; cchCount2
0x1800600dc  mov     [rsp+58h+lpString2], rax; lpString2
0x1800600e1  mov     r9d, ecx; cchCount1
0x1800600e4  mov     r8, r13; lpString1
0x1800600e7  lea     edx, [rcx+2]; dwCmpFlags
0x1800600ea  mov     ecx, 409h; Locale
0x1800600ef  call    cs:__imp_CompareStringW
0x1800600f5  cmp     eax, 2
0x1800600f8  jz      short loc_180060157
0x1800600fa  mov     rax, [rbp+arg_0]
0x1800600fe  inc     edi
0x180060100  cmp     edi, r14d
0x180060103  jb      loc_180060080
0x180060109  mov     ebx, 80070490h
0x18006010e  mov     ecx, ebx
0x180060110  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180060115  nop
0x180060116  mov     rcx, [rbp+arg_0]; bstrString
0x18006011a  test    rcx, rcx
0x18006011d  jz      short loc_18006012D
0x18006011f  call    cs:__imp_SysFreeString
0x180060125  mov     [rbp+arg_0], 0
0x18006012d  mov     edx, dword ptr [rbp+var_18]
0x180060130  test    edx, edx
0x180060132  jz      short loc_180060144
0x180060134  mov     rcx, r15; lpCriticalSection
0x180060137  call    cs:__imp_LeaveCriticalSection
0x18006013d  mov     dword ptr [rbp+var_18], 0
0x180060144  mov     eax, ebx
0x180060146  add     rsp, 58h
0x18006014a  pop     r15
0x18006014c  pop     r14
0x18006014e  pop     r13
0x180060150  pop     r12
0x180060152  pop     rdi
0x180060153  pop     rsi
0x180060154  pop     rbx
0x180060155  pop     rbp
0x180060156  retn
0x180060157  mov     [r12], edi
0x18006015b  jmp     short loc_18006010E
0x18006015d  lea     rdi, [rsi+50h]
0x180060161  mov     rax, [rdi]
0x180060164  mov     rcx, rdi
0x180060167  mov     rax, [rax+10h]
0x18006016b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060170  test    rax, rax
0x180060173  jz      short loc_18006010E
0x180060175  mov     rax, [rdi]
0x180060178  mov     rcx, rdi
0x18006017b  mov     rax, [rax+10h]
0x18006017f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060184  xor     ecx, ecx
0x180060186  test    rax, rax
0x180060189  jz      short loc_1800601BB
0x18006018b  mov     dword ptr [rsp+58h+cchCount2], ebx
0x18006018f  mov     dword ptr [rsp+58h+lpString2], 9D2h
0x180060197  lea     r9, aCdlpmanagerGet_15; "CDlpManager::GetTaskIndexByName"
0x18006019e  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x1800601a5  lea     edx, [rcx+4]
0x1800601a8  mov     rcx, rax
0x1800601ab  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x1800601b0  mov     ecx, eax
0x1800601b2  test    eax, eax
0x1800601b4  jns     short loc_1800601BB
0x1800601b6  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800601bb  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800601c0  jmp     loc_18006010E
```
