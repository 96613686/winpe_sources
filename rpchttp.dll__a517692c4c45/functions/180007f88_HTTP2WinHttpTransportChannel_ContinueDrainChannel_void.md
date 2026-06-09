# HTTP2WinHttpTransportChannel::ContinueDrainChannel(void)

- ea: `0x180007f88`
- end: `0x18000817b`
- name: `?ContinueDrainChannel@HTTP2WinHttpTransportChannel@@QEAAXXZ`
- size: `499`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18000af90`

## callees

- `0x180005428`
- `0x180007f88`
- `0x180009d58`
- `0x18000f048`
- `0x18001e91c`
- `0x180025010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180008126`
- `ntdll!RtlLeaveCriticalSection` at `0x180008134`
- `ntdll!RtlLeaveCriticalSection` at `0x180008126`
- `ntdll!RtlLeaveCriticalSection` at `0x180008134`
- `ntdll!RtlEnterCriticalSection` at `0x1800080be`
- `ntdll!RtlEnterCriticalSection` at `0x1800080be`
- `KERNEL32!CreateEventW` at `0x180007ffe`
- `KERNEL32!CreateEventW` at `0x180007ffe`
- `KERNEL32!WaitForSingleObject` at `0x180008080`
- `KERNEL32!WaitForSingleObject` at `0x180008080`
- `KERNEL32!CloseHandle` at `0x18000809e`
- `KERNEL32!CloseHandle` at `0x18000809e`
- `RPCRT4!I_RpcLogEvent` at `0x180008060`
- `RPCRT4!I_RpcLogEvent` at `0x1800080ea`
- `RPCRT4!I_RpcLogEvent` at `0x180008060`
- `RPCRT4!I_RpcLogEvent` at `0x1800080ea`
- `WINHTTP!WinHttpReadData` at `0x180008074`
- `WINHTTP!WinHttpReadData` at `0x180008074`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x1800080f6`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x1800080f6`

## pseudocode

```c
void __fastcall HTTP2WinHttpTransportChannel::ContinueDrainChannel(unsigned int *pv)
{
  void *v2; // rdi
  unsigned int v3; // esi
  __int64 v4; // rdx
  __int64 v5; // rcx
  HANDLE EventW; // rsi
  __int64 v7; // r8
  __int64 v8; // rdx
  __int64 v9; // rcx
  unsigned int v10; // eax
  unsigned int v11; // [rsp+20h] [rbp-28h]

  if ( !pv[20] )
  {
    if ( (unsigned int)HTTP2WinHttpTransportChannel::IsProxyChallengeDrainSet((HTTP2WinHttpTransportChannel *)pv) )
    {
      pv[21] = -1073606617;
      pv[56] &= ~4u;
    }
    else
    {
      pv[21] = -1073606612;
    }
    goto LABEL_18;
  }
  v2 = (void *)(*(__int64 (__fastcall **)(_QWORD))pRuntimeImportTable)(pv[20]);
  if ( v2 )
  {
    v3 = HTTP2Channel::BeginSimpleSubmitAsync(*((HTTP2Channel **)pv + 3));
    if ( v3 )
    {
      (*((void (__fastcall **)(void *))pRuntimeImportTable + 1))(v2);
      pv[21] = v3;
      goto LABEL_18;
    }
    EventW = CreateEventW(0, 0, 0, 0);
    if ( EventW )
    {
      v7 = *((_QWORD *)pv + 9);
      LOBYTE(v4) = 111;
      LOBYTE(v5) = 50;
      v11 = pv[20];
      pv[45] = 5;
      *((_QWORD *)pv + 21) = EventW;
      I_RpcLogEvent(v5, v4, v7, 25755670, v11, 0, 0);
      WinHttpReadData(*((HINTERNET *)pv + 9), v2, pv[20], 0);
      WaitForSingleObject(EventW, 0xFFFFFFFF);
      pv[45] = 8;
      *((_QWORD *)pv + 21) = 0;
      CloseHandle(EventW);
      (*((void (__fastcall **)(void *))pRuntimeImportTable + 1))(v2);
      RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(pv + 26));
      LOBYTE(v8) = 111;
      LOBYTE(v9) = 50;
      I_RpcLogEvent(v9, v8, *((_QWORD *)pv + 9), 25952278, 0, 0, 0);
      WinHttpQueryDataAvailable(*((HINTERNET *)pv + 9), 0);
      HTTP2Channel::FinishSubmitAsync(*((HTTP2Channel **)pv + 3));
      v10 = pv[21];
      if ( v10 != -1073606612 && v10 != -1073606617 )
      {
        if ( v10 != 1766 && v10 )
        {
          RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(pv + 26));
          goto LABEL_18;
        }
        pv[21] = 1766;
      }
      RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(pv + 26));
      return;
    }
    HTTP2Channel::FinishSubmitAsync(*((HTTP2Channel **)pv + 3));
    (*((void (__fastcall **)(void *))pRuntimeImportTable + 1))(v2);
  }
  pv[21] = 14;
LABEL_18:
  RPC_THREAD_POOL::TrySubmitWork(HTTP2WinHttpDirectReceive, pv);
}

```

## disassembly

```asm
0x180007f88  mov     [rsp+arg_0], rbx
0x180007f8d  mov     [rsp+arg_8], rsi
0x180007f92  push    rdi
0x180007f93  sub     rsp, 40h
0x180007f97  cmp     dword ptr [rcx+50h], 0
0x180007f9b  mov     rbx, rcx
0x180007f9e  jbe     loc_18000813C
0x180007fa4  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x180007fab  mov     ecx, [rcx+50h]
0x180007fae  mov     rax, [rax]
0x180007fb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fb6  mov     rdi, rax
0x180007fb9  test    rax, rax
0x180007fbc  jnz     short loc_180007FCA
0x180007fbe  mov     dword ptr [rbx+54h], 0Eh
0x180007fc5  jmp     loc_18000815C
0x180007fca  mov     rcx, [rbx+18h]; this
0x180007fce  call    ?BeginSimpleSubmitAsync@HTTP2Channel@@QEAAJXZ; HTTP2Channel::BeginSimpleSubmitAsync(void)
0x180007fd3  mov     esi, eax
0x180007fd5  test    eax, eax
0x180007fd7  jz      short loc_180007FF4
0x180007fd9  mov     rcx, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x180007fe0  mov     rax, [rcx+8]
0x180007fe4  mov     rcx, rdi
0x180007fe7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fec  mov     [rbx+54h], esi
0x180007fef  jmp     loc_18000815C
0x180007ff4  xor     r9d, r9d; lpName
0x180007ff7  xor     r8d, r8d; bInitialState
0x180007ffa  xor     edx, edx; bManualReset
0x180007ffc  xor     ecx, ecx; lpEventAttributes
0x180007ffe  call    cs:__imp_CreateEventW
0x180008004  mov     rsi, rax
0x180008007  test    rax, rax
0x18000800a  jnz     short loc_18000802A
0x18000800c  mov     rcx, [rbx+18h]; this
0x180008010  call    ?FinishSubmitAsync@HTTP2Channel@@QEAAXXZ; HTTP2Channel::FinishSubmitAsync(void)
0x180008015  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x18000801c  mov     rcx, rdi
0x18000801f  mov     rax, [rax+8]
0x180008023  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008028  jmp     short loc_180007FBE
0x18000802a  mov     eax, [rbx+50h]
0x18000802d  mov     r9d, 1890016h
0x180008033  mov     r8, [rbx+48h]
0x180008037  mov     dl, 6Fh ; 'o'
0x180008039  mov     [rsp+48h+var_18], 0
0x180008041  mov     cl, 32h ; '2'
0x180008043  mov     [rsp+48h+var_20], 0
0x18000804b  mov     [rsp+48h+var_28], eax
0x18000804f  mov     dword ptr [rbx+0B4h], 5
0x180008059  mov     [rbx+0A8h], rsi
0x180008060  call    cs:__imp_I_RpcLogEvent
0x180008066  mov     r8d, [rbx+50h]; dwNumberOfBytesToRead
0x18000806a  xor     r9d, r9d; lpdwNumberOfBytesRead
0x18000806d  mov     rcx, [rbx+48h]; hRequest
0x180008071  mov     rdx, rdi; lpBuffer
0x180008074  call    cs:__imp_WinHttpReadData
0x18000807a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000807d  mov     rcx, rsi; hHandle
0x180008080  call    cs:__imp_WaitForSingleObject
0x180008086  mov     rcx, rsi; hObject
0x180008089  mov     dword ptr [rbx+0B4h], 8
0x180008093  mov     qword ptr [rbx+0A8h], 0
0x18000809e  call    cs:__imp_CloseHandle
0x1800080a4  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x1800080ab  mov     rcx, rdi
0x1800080ae  mov     rax, [rax+8]
0x1800080b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080b7  lea     rdi, [rbx+68h]
0x1800080bb  mov     rcx, rdi; CriticalSection
0x1800080be  call    cs:__imp_RtlEnterCriticalSection
0x1800080c4  mov     r8, [rbx+48h]
0x1800080c8  mov     r9d, 18C0016h
0x1800080ce  mov     [rsp+48h+var_18], 0
0x1800080d6  mov     dl, 6Fh ; 'o'
0x1800080d8  mov     [rsp+48h+var_20], 0
0x1800080e0  mov     cl, 32h ; '2'
0x1800080e2  mov     [rsp+48h+var_28], 0
0x1800080ea  call    cs:__imp_I_RpcLogEvent
0x1800080f0  mov     rcx, [rbx+48h]; hRequest
0x1800080f4  xor     edx, edx; lpdwNumberOfBytesAvailable
0x1800080f6  call    cs:__imp_WinHttpQueryDataAvailable
0x1800080fc  mov     rcx, [rbx+18h]; this
0x180008100  call    ?FinishSubmitAsync@HTTP2Channel@@QEAAXXZ; HTTP2Channel::FinishSubmitAsync(void)
0x180008105  mov     eax, [rbx+54h]
0x180008108  cmp     eax, 0C002102Ch
0x18000810d  jz      short loc_180008131
0x18000810f  cmp     eax, 0C0021027h
0x180008114  jz      short loc_180008131
0x180008116  mov     ecx, 6E6h
0x18000811b  cmp     eax, ecx
0x18000811d  jz      short loc_18000812E
0x18000811f  test    eax, eax
0x180008121  jz      short loc_18000812E
0x180008123  mov     rcx, rdi; CriticalSection
0x180008126  call    cs:__imp_RtlLeaveCriticalSection
0x18000812c  jmp     short loc_18000815C
0x18000812e  mov     [rbx+54h], ecx
0x180008131  mov     rcx, rdi; CriticalSection
0x180008134  call    cs:__imp_RtlLeaveCriticalSection
0x18000813a  jmp     short loc_18000816B
0x18000813c  call    ?IsProxyChallengeDrainSet@HTTP2WinHttpTransportChannel@@AEAAHXZ; HTTP2WinHttpTransportChannel::IsProxyChallengeDrainSet(void)
0x180008141  test    eax, eax
0x180008143  jz      short loc_180008155
0x180008145  mov     dword ptr [rbx+54h], 0C0021027h
0x18000814c  and     dword ptr [rbx+0E0h], 0FFFFFFFBh
0x180008153  jmp     short loc_18000815C
0x180008155  mov     dword ptr [rbx+54h], 0C002102Ch
0x18000815c  mov     rdx, rbx; pv
0x18000815f  lea     rcx, ?HTTP2WinHttpDirectReceive@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x180008166  call    ?TrySubmitWork@RPC_THREAD_POOL@@SAJP6AXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z1@Z; RPC_THREAD_POOL::TrySubmitWork(void (*)(_TP_CALLBACK_INSTANCE *,void *),void *)
0x18000816b  mov     rbx, [rsp+48h+arg_0]
0x180008170  mov     rsi, [rsp+48h+arg_8]
0x180008175  add     rsp, 40h
0x180008179  pop     rdi
0x18000817a  retn
```
