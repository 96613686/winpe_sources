# BaseClientNotifyHandler::DeleteFromList(utl::unique_lock<utl::recursive_mutex> &,BaseClientNotifyHandler *)

- ea: `0x180022c34`
- end: `0x180022d22`
- name: `?DeleteFromList@BaseClientNotifyHandler@@SAXAEAV?$unique_lock@Vrecursive_mutex@utl@@@utl@@PEAV1@@Z`
- size: `238`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180022920`
- `0x180062c50`

## callees

- `0x180022c34`
- `0x18002993c`
- `0x1800742ac`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022cb4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022cb4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180022c49`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180022c49`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180022cc6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180022cc6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180022c9f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180022c9f`

## pseudocode

```c
_QWORD *__fastcall BaseClientNotifyHandler::DeleteFromList(__int64 a1, __int64 a2)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  _QWORD *result; // rax
  __int64 v7; // rdx
  _QWORD *v8; // rcx
  PTP_WAIT *v9; // rdi
  struct _TP_WAIT *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx

  if ( LODWORD(g_clientNotifyLock.OwningThread) != GetCurrentThreadId() )
    Log_AssertionEvent_8(v5, v4, 51);
  result = (_QWORD *)(a2 + 48);
  v7 = *(_QWORD *)(a2 + 48);
  if ( *(_QWORD *)(v7 + 8) != a2 + 48 || (v8 = *(_QWORD **)(a2 + 56), (_QWORD *)*v8 != result) )
    __fastfail(3u);
  *v8 = v7;
  v9 = (PTP_WAIT *)(a2 + 32);
  *(_QWORD *)(v7 + 8) = v8;
  *(_QWORD *)(a2 + 56) = a2 + 48;
  *result = result;
  v10 = *(struct _TP_WAIT **)(a2 + 32);
  if ( v10 )
  {
    SetThreadpoolWait(v10, 0, 0);
    if ( *(_DWORD *)(a2 + 68) )
    {
      if ( !*(_BYTE *)(a1 + 8) )
        __int2c();
      LeaveCriticalSection(*(LPCRITICAL_SECTION *)a1);
      *(_BYTE *)(a1 + 8) = 0;
      WaitForThreadpoolWaitCallbacks(*v9, 1);
      if ( *(_DWORD *)(a2 + 64) )
        Log_AssertionEvent_8(v12, v11, 76);
    }
    result = (_QWORD *)tlx::auto_xxx<_TP_WAIT *,void (*)(_TP_WAIT *),&void CloseThreadpoolWait(_TP_WAIT *),0>::_Delete(a2 + 32);
    *v9 = 0;
  }
  if ( !*(_DWORD *)(a2 + 64) )
    return (_QWORD *)(**(__int64 (__fastcall ***)(__int64, __int64))a2)(a2, 1);
  return result;
}

```

## disassembly

```asm
0x180022c34  mov     [rsp+arg_0], rbx
0x180022c39  mov     [rsp+arg_8], rsi
0x180022c3e  push    rdi
0x180022c3f  sub     rsp, 20h
0x180022c43  mov     rbx, rdx
0x180022c46  mov     rsi, rcx
0x180022c49  call    cs:__imp_GetCurrentThreadId
0x180022c4f  cmp     dword ptr cs:?g_clientNotifyLock@@3Vrecursive_mutex@utl@@A.OwningThread, eax; utl::recursive_mutex g_clientNotifyLock ...
0x180022c55  jz      short loc_180022C62
0x180022c57  mov     r8d, 33h ; '3'
0x180022c5d  call    Log_AssertionEvent_8
0x180022c62  lea     rax, [rbx+30h]
0x180022c66  mov     rdx, [rax]
0x180022c69  cmp     [rdx+8], rax
0x180022c6d  jnz     loc_180022D1B
0x180022c73  mov     rcx, [rax+8]
0x180022c77  cmp     [rcx], rax
0x180022c7a  jnz     loc_180022D1B
0x180022c80  mov     [rcx], rdx
0x180022c83  lea     rdi, [rbx+20h]
0x180022c87  mov     [rdx+8], rcx
0x180022c8b  mov     [rax+8], rax
0x180022c8f  mov     [rax], rax
0x180022c92  mov     rcx, [rdi]; pwa
0x180022c95  test    rcx, rcx
0x180022c98  jz      short loc_180022CE1
0x180022c9a  xor     r8d, r8d; pftTimeout
0x180022c9d  xor     edx, edx; h
0x180022c9f  call    cs:__imp_SetThreadpoolWait
0x180022ca5  cmp     dword ptr [rbx+44h], 0
0x180022ca9  jz      short loc_180022CD2
0x180022cab  cmp     byte ptr [rsi+8], 0
0x180022caf  jz      short loc_180022D17
0x180022cb1  mov     rcx, [rsi]; lpCriticalSection
0x180022cb4  call    cs:__imp_LeaveCriticalSection
0x180022cba  mov     byte ptr [rsi+8], 0
0x180022cbe  mov     edx, 1; fCancelPendingCallbacks
0x180022cc3  mov     rcx, [rdi]; pwa
0x180022cc6  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180022ccc  cmp     dword ptr [rbx+40h], 0
0x180022cd0  jnz     short loc_180022D0A
0x180022cd2  mov     rcx, rdi
0x180022cd5  call    ?_Delete@?$auto_xxx@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?CloseThreadpoolWait@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<_TP_WAIT *,void (*)(_TP_WAIT *),&CloseThreadpoolWait(_TP_WAIT *),0>::_Delete(void)
0x180022cda  mov     qword ptr [rdi], 0
0x180022ce1  cmp     dword ptr [rbx+40h], 0
0x180022ce5  jnz     short loc_180022CFA
0x180022ce7  mov     rax, [rbx]
0x180022cea  mov     edx, 1
0x180022cef  mov     rcx, rbx
0x180022cf2  mov     rax, [rax]
0x180022cf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022cfa  mov     rbx, [rsp+28h+arg_0]
0x180022cff  mov     rsi, [rsp+28h+arg_8]
0x180022d04  add     rsp, 20h
0x180022d08  pop     rdi
0x180022d09  retn
0x180022d0a  mov     r8d, 4Ch ; 'L'
0x180022d10  call    Log_AssertionEvent_8
0x180022d15  jmp     short loc_180022CD2
0x180022d17  int     2Ch; Windows NT - assertion failure
0x180022d19  jmp     short loc_180022CB1
0x180022d1b  mov     ecx, 3
0x180022d20  int     29h; Win8: RtlFailFast(ecx)
```
