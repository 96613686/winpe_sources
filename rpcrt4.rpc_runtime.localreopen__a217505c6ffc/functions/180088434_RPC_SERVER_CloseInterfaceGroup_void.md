# RPC_SERVER::CloseInterfaceGroup(void *)

- ea: `0x180088434`
- end: `0x1800885cf`
- name: `?CloseInterfaceGroup@RPC_SERVER@@QEAAJPEAX@Z`
- size: `411`
- prototype: `int(RPC_SERVER *__hidden this, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180088400`

## callees

- `0x180022e80`
- `0x180087ec4`
- `0x180088434`
- `0x1800885d8`
- `0x180088bb0`
- `0x1800b836c`
- `0x1800d7010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18008849e`
- `ntdll!RtlLeaveCriticalSection` at `0x1800884fa`
- `ntdll!RtlLeaveCriticalSection` at `0x180088509`
- `ntdll!RtlLeaveCriticalSection` at `0x180088546`
- `ntdll!RtlLeaveCriticalSection` at `0x18008849e`
- `ntdll!RtlLeaveCriticalSection` at `0x1800884fa`
- `ntdll!RtlLeaveCriticalSection` at `0x180088509`
- `ntdll!RtlLeaveCriticalSection` at `0x180088546`
- `ntdll!RtlEnterCriticalSection` at `0x180088455`
- `ntdll!RtlEnterCriticalSection` at `0x1800884c6`
- `ntdll!RtlEnterCriticalSection` at `0x180088537`
- `ntdll!RtlEnterCriticalSection` at `0x180088455`
- `ntdll!RtlEnterCriticalSection` at `0x1800884c6`
- `ntdll!RtlEnterCriticalSection` at `0x180088537`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18008856c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18008856c`

## pseudocode

```c
__int64 __fastcall RPC_SERVER::CloseInterfaceGroup(RPC_SERVER *this, char *a2)
{
  RPC_SERVER *v2; // r14
  struct _RTL_CRITICAL_SECTION *v3; // rbp
  int v5; // eax
  BOOL v6; // esi
  unsigned int v7; // ebx
  char **v8; // rdx
  void **v9; // rcx
  PTP_WORK *v10; // rcx
  unsigned int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rcx
  int v15; // [rsp+28h] [rbp-50h]
  int v16; // [rsp+30h] [rbp-48h]

  v2 = (RPC_SERVER *)GlobalRpcServer;
  v3 = (struct _RTL_CRITICAL_SECTION *)(a2 + 176);
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(a2 + 176));
  if ( *((_DWORD *)a2 + 10) != 667022880 )
  {
    v7 = 87;
    goto LABEL_4;
  }
  v5 = *((_DWORD *)a2 + 58);
  v6 = 0;
  if ( v5 == 1 )
  {
    v7 = RPC_SERVER::DeactivateInterfaceGroup(v2, (struct RPCP_INTERFACE_GROUP *)a2, 0, 1, 1);
    if ( v7 )
    {
LABEL_4:
      RtlLeaveCriticalSection(v3);
      return v7;
    }
  }
  else
  {
    v6 = v5 == 2;
  }
  _InterlockedExchange((volatile __int32 *)a2 + 58, 3);
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)v2);
  v8 = (char **)*((_QWORD *)a2 + 3);
  if ( v8[1] != a2 + 24 || (v9 = (void **)*((_QWORD *)a2 + 4), *v9 != a2 + 24) )
    __fastfail(3u);
  *v9 = v8;
  v8[1] = (char *)v9;
  RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)v2);
  RtlLeaveCriticalSection(v3);
  LogEvent(0x67u, 0x44u, a2, 0, 0, v15, v16);
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)a2 + 6);
  RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)a2 + 6);
  RPCP_INTERFACE_GROUP::CancelIdleTimer((RPCP_INTERFACE_GROUP *)a2);
  v10 = (PTP_WORK *)*((_QWORD *)a2 + 21);
  if ( v10 )
    WaitForThreadpoolWorkCallbacks(*v10, 1);
  if ( v6 )
  {
    v12 = RpcpEpReRaiseTriggers(*((unsigned int *)a2 + 14), *((_QWORD *)a2 + 6));
    if ( v12 )
    {
      if ( (Microsoft_Windows_RPCEnableBits & 2) != 0 )
        McTemplateU0d_EtwEventWriteTransfer(v14, v13, v12);
    }
  }
  v7 = 0;
  (*(void (__fastcall **)(char *))(*(_QWORD *)a2 + 32LL))(a2);
  return v7;
}

```

## disassembly

```asm
0x180088434  push    rbx
0x180088436  push    rbp
0x180088437  push    rsi
0x180088438  push    rdi
0x180088439  push    r14
0x18008843b  push    r15
0x18008843d  sub     rsp, 48h
0x180088441  mov     r14, cs:?GlobalRpcServer@@3PEAVRPC_SERVER@@EA; RPC_SERVER * GlobalRpcServer
0x180088448  lea     rbp, [rdx+0B0h]
0x18008844f  mov     rcx, rbp; CriticalSection
0x180088452  mov     rdi, rdx
0x180088455  call    cs:__imp_RtlEnterCriticalSection
0x18008845c  nop     dword ptr [rax+rax+00h]
0x180088461  cmp     dword ptr [rdi+28h], 27C1F620h
0x180088468  jnz     loc_1800885C5
0x18008846e  mov     eax, [rdi+0E8h]
0x180088474  xor     esi, esi
0x180088476  lea     r15d, [rsi+1]
0x18008847a  cmp     eax, r15d
0x18008847d  jnz     short loc_1800884AF
0x18008847f  mov     r9d, r15d; int
0x180088482  mov     dword ptr [rsp+78h+var_58], r15d; int
0x180088487  xor     r8d, r8d; int
0x18008848a  mov     rdx, rdi; struct RPCP_INTERFACE_GROUP *
0x18008848d  mov     rcx, r14; this
0x180088490  call    ?DeactivateInterfaceGroup@RPC_SERVER@@QEAAJPEAXHHH@Z; RPC_SERVER::DeactivateInterfaceGroup(void *,int,int,int)
0x180088495  mov     ebx, eax
0x180088497  test    eax, eax
0x180088499  jz      short loc_1800884B6
0x18008849b  mov     rcx, rbp; CriticalSection
0x18008849e  call    cs:__imp_RtlLeaveCriticalSection
0x1800884a5  nop     dword ptr [rax+rax+00h]
0x1800884aa  jmp     loc_18008858D
0x1800884af  cmp     eax, 2
0x1800884b2  cmovz   esi, r15d
0x1800884b6  mov     ebx, 3
0x1800884bb  mov     rcx, r14; CriticalSection
0x1800884be  mov     eax, ebx
0x1800884c0  xchg    eax, [rdi+0E8h]
0x1800884c6  call    cs:__imp_RtlEnterCriticalSection
0x1800884cd  nop     dword ptr [rax+rax+00h]
0x1800884d2  lea     rax, [rdi+18h]
0x1800884d6  mov     rdx, [rax]
0x1800884d9  cmp     [rdx+8], rax
0x1800884dd  jnz     loc_1800885C0
0x1800884e3  mov     rcx, [rax+8]
0x1800884e7  cmp     [rcx], rax
0x1800884ea  jnz     loc_1800885C0
0x1800884f0  mov     [rcx], rdx
0x1800884f3  mov     [rdx+8], rcx
0x1800884f7  mov     rcx, r14; CriticalSection
0x1800884fa  call    cs:__imp_RtlLeaveCriticalSection
0x180088501  nop     dword ptr [rax+rax+00h]
0x180088506  mov     rcx, rbp; CriticalSection
0x180088509  call    cs:__imp_RtlLeaveCriticalSection
0x180088510  nop     dword ptr [rax+rax+00h]
0x180088515  xor     r9d, r9d; void *
0x180088518  mov     [rsp+78h+var_58], 0; unsigned __int64
0x180088521  mov     r8, rdi; void *
0x180088524  mov     dl, 44h ; 'D'; unsigned __int8
0x180088526  mov     cl, 67h ; 'g'; unsigned __int8
0x180088528  call    ?LogEvent@@YAXEEPEAX0_KHH@Z; LogEvent(uchar,uchar,void *,void *,unsigned __int64,int,int)
0x18008852d  lea     rbx, [rdi+0F0h]
0x180088534  mov     rcx, rbx; CriticalSection
0x180088537  call    cs:__imp_RtlEnterCriticalSection
0x18008853e  nop     dword ptr [rax+rax+00h]
0x180088543  mov     rcx, rbx; CriticalSection
0x180088546  call    cs:__imp_RtlLeaveCriticalSection
0x18008854d  nop     dword ptr [rax+rax+00h]
0x180088552  mov     rcx, rdi; this
0x180088555  call    ?CancelIdleTimer@RPCP_INTERFACE_GROUP@@QEAAXXZ; RPCP_INTERFACE_GROUP::CancelIdleTimer(void)
0x18008855a  mov     rcx, [rdi+0A8h]
0x180088561  test    rcx, rcx
0x180088564  jz      short loc_180088578
0x180088566  mov     rcx, [rcx]; pwk
0x180088569  mov     edx, r15d; fCancelPendingCallbacks
0x18008856c  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180088573  nop     dword ptr [rax+rax+00h]
0x180088578  test    esi, esi
0x18008857a  jnz     short loc_18008859D
0x18008857c  xor     ebx, ebx
0x18008857e  mov     rax, [rdi]
0x180088581  mov     rcx, rdi
0x180088584  mov     rax, [rax+20h]
0x180088588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008858d  mov     eax, ebx
0x18008858f  add     rsp, 48h
0x180088593  pop     r15
0x180088595  pop     r14
0x180088597  pop     rdi
0x180088598  pop     rsi
0x180088599  pop     rbp
0x18008859a  pop     rbx
0x18008859b  retn
0x18008859d  mov     rdx, [rdi+30h]
0x1800885a1  mov     ecx, [rdi+38h]
0x1800885a4  call    RpcpEpReRaiseTriggers
0x1800885a9  test    eax, eax
0x1800885ab  jz      short loc_18008857C
0x1800885ad  test    cs:Microsoft_Windows_RPCEnableBits, 2
0x1800885b4  jz      short loc_18008857C
0x1800885b6  mov     r8d, eax
0x1800885b9  call    McTemplateU0d_EtwEventWriteTransfer
0x1800885be  jmp     short loc_18008857C
0x1800885c0  mov     rcx, rbx
0x1800885c3  int     29h; Win8: RtlFailFast(ecx)
0x1800885c5  mov     ebx, 57h ; 'W'
0x1800885ca  jmp     loc_18008849B
```
