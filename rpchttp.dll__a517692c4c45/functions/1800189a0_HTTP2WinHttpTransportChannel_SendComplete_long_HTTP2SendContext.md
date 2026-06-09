# HTTP2WinHttpTransportChannel::SendComplete(long,HTTP2SendContext *)

- ea: `0x1800189a0`
- end: `0x180018be4`
- name: `?SendComplete@HTTP2WinHttpTransportChannel@@UEAAJJPEAVHTTP2SendContext@@@Z`
- size: `580`
- prototype: `__int64 __fastcall(HTTP2WinHttpTransportChannel *__hidden this, int, struct HTTP2SendContext *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009620`

## callees

- `0x180005428`
- `0x180009d58`
- `0x180018980`
- `0x1800189a0`
- `0x18001e91c`
- `0x180025010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180018a02`
- `ntdll!RtlLeaveCriticalSection` at `0x180018a7b`
- `ntdll!RtlLeaveCriticalSection` at `0x180018a02`
- `ntdll!RtlLeaveCriticalSection` at `0x180018a7b`
- `ntdll!RtlEnterCriticalSection` at `0x1800189ec`
- `ntdll!RtlEnterCriticalSection` at `0x180018a32`
- `ntdll!RtlEnterCriticalSection` at `0x1800189ec`
- `ntdll!RtlEnterCriticalSection` at `0x180018a32`
- `KERNEL32!GetLastError` at `0x180018b03`
- `KERNEL32!GetLastError` at `0x180018b03`
- `RPCRT4!I_RpcLogEvent` at `0x1800189d4`
- `RPCRT4!I_RpcLogEvent` at `0x180018acf`
- `RPCRT4!I_RpcLogEvent` at `0x180018bd1`
- `RPCRT4!I_RpcLogEvent` at `0x1800189d4`
- `RPCRT4!I_RpcLogEvent` at `0x180018acf`
- `RPCRT4!I_RpcLogEvent` at `0x180018bd1`
- `WINHTTP!WinHttpWriteData` at `0x180018ae4`
- `WINHTTP!WinHttpWriteData` at `0x180018ae4`

## pseudocode

```c
__int64 __fastcall HTTP2WinHttpTransportChannel::SendComplete(
        HTTP2WinHttpTransportChannel *this,
        __int64 a2,
        struct HTTP2SendContext *a3)
{
  int v4; // edi
  HTTP2WinHttpTransportChannel *v5; // rsi
  HTTP2WinHttpTransportChannel *v6; // r8
  int v7; // r14d
  unsigned int v8; // eax
  unsigned int v9; // edi
  _QWORD *v10; // r8
  _QWORD *v11; // rdx
  __int64 v12; // rax
  _QWORD *v13; // rbx
  HTTP2Channel *v14; // rcx
  int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // rcx
  BOOL v18; // ebx
  __int64 v19; // rdx
  __int64 v20; // rcx
  int v21; // ebx
  int v23; // [rsp+20h] [rbp-48h]

  v4 = a2;
  v23 = a2;
  v5 = this;
  v6 = this;
  LOBYTE(a2) = 111;
  LOBYTE(this) = 50;
  I_RpcLogEvent(this, a2, v6, 17104917, v23, 0, 0);
  *((_QWORD *)v5 + 23) = 0;
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)v5 + 104));
  v7 = --*((_DWORD *)v5 + 48);
  RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)v5 + 104));
  v8 = HTTP2TransportChannel::SendComplete(v5, v4, a3);
  v9 = v8;
  if ( (!v8 || v8 == -1073606615) && v7 )
  {
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)v5 + 104));
    v10 = (_QWORD *)((char *)v5 + 144);
    v11 = (_QWORD *)*((_QWORD *)v5 + 18);
    if ( (HTTP2WinHttpTransportChannel *)v11[1] != (HTTP2WinHttpTransportChannel *)((char *)v5 + 144)
      || (v12 = *v11, *(_QWORD **)(*v11 + 8LL) != v11) )
    {
      __fastfail(3u);
    }
    *v10 = v12;
    *(_QWORD *)(v12 + 8) = v10;
    if ( v11 != v10 )
    {
      *v11 = 0;
      v11[1] = 0;
    }
    v13 = v11 - 9;
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)v5 + 104));
    if ( v13 )
    {
      v14 = (HTTP2Channel *)*((_QWORD *)v5 + 3);
      *((_DWORD *)v5 + 45) = 6;
      v15 = HTTP2Channel::BeginSimpleSubmitAsync(v14);
      *((_QWORD *)v5 + 23) = v13;
      v17 = *((unsigned int *)v13 + 14);
      *((_DWORD *)v5 + 20) = v17;
      if ( v15 )
      {
        *((_DWORD *)v5 + 45) = 3;
        goto LABEL_12;
      }
      LOBYTE(v16) = 111;
      LOBYTE(v17) = 50;
      I_RpcLogEvent(v17, v16, *((_QWORD *)v5 + 9), 25624598, *((_DWORD *)v13 + 14), 0, 0);
      v18 = WinHttpWriteData(*((HINTERNET *)v5 + 9), (LPCVOID)v13[6], *((_DWORD *)v13 + 14), 0);
      HTTP2Channel::FinishSubmitAsync(*((HTTP2Channel **)v5 + 3));
      if ( !v18 )
      {
        *((_DWORD *)v5 + 45) = 3;
        GetLastError();
LABEL_12:
        *((_DWORD *)v5 + 21) = -1073606646;
        RPC_THREAD_POOL::TrySubmitWork(HTTP2WinHttpDirectSend, v5);
      }
    }
  }
  v19 = *((unsigned int *)v5 + 44);
  v20 = 2;
  if ( (unsigned int)(v19 - 5) <= 2 && !v7 )
  {
    if ( (_DWORD)v19 == 5 )
    {
      *((_DWORD *)v5 + 44) = 1;
    }
    else
    {
      if ( (_DWORD)v19 == 7 )
        LODWORD(v20) = 4;
      *((_DWORD *)v5 + 44) = v20;
    }
    v21 = HTTP2Channel::BeginSimpleSubmitAsync(*((HTTP2Channel **)v5 + 3));
    if ( v21
      || (v21 = (*(__int64 (__fastcall **)(HTTP2WinHttpTransportChannel *, _QWORD))(*(_QWORD *)v5 + 16LL))(
                  v5,
                  *((unsigned int *)v5 + 44)),
          HTTP2Channel::FinishSubmitAsync(*((HTTP2Channel **)v5 + 3)),
          v21) )
    {
      *((_DWORD *)v5 + 21) = v21;
      RPC_THREAD_POOL::TrySubmitWork(HTTP2WinHttpDirectReceive, v5);
    }
  }
  LOBYTE(v19) = 111;
  LOBYTE(v20) = 50;
  I_RpcLogEvent(v20, v19, v5, 327701, v9, 0, 0);
  return v9;
}

```

## disassembly

```asm
0x1800189a0  push    rbx
0x1800189a2  push    rbp
0x1800189a3  push    rsi
0x1800189a4  push    rdi
0x1800189a5  push    r14
0x1800189a7  sub     rsp, 40h
0x1800189ab  mov     [rsp+68h+var_38], 0
0x1800189b3  mov     rbx, r8
0x1800189b6  mov     edi, edx
0x1800189b8  mov     [rsp+68h+var_40], 0
0x1800189c0  mov     [rsp+68h+var_48], edx
0x1800189c4  mov     rsi, rcx
0x1800189c7  mov     r8, rcx
0x1800189ca  mov     dl, 6Fh ; 'o'
0x1800189cc  mov     r9d, 1050015h
0x1800189d2  mov     cl, 32h ; '2'
0x1800189d4  call    cs:__imp_I_RpcLogEvent
0x1800189da  lea     rbp, [rsi+68h]
0x1800189de  mov     qword ptr [rsi+0B8h], 0
0x1800189e9  mov     rcx, rbp; CriticalSection
0x1800189ec  call    cs:__imp_RtlEnterCriticalSection
0x1800189f2  dec     dword ptr [rsi+0C0h]
0x1800189f8  mov     rcx, rbp; CriticalSection
0x1800189fb  mov     r14d, [rsi+0C0h]
0x180018a02  call    cs:__imp_RtlLeaveCriticalSection
0x180018a08  mov     r8, rbx; struct HTTP2SendContext *
0x180018a0b  mov     edx, edi; int
0x180018a0d  mov     rcx, rsi; this
0x180018a10  call    ?SendComplete@HTTP2TransportChannel@@UEAAJJPEAVHTTP2SendContext@@@Z; HTTP2TransportChannel::SendComplete(long,HTTP2SendContext *)
0x180018a15  mov     edi, eax
0x180018a17  test    eax, eax
0x180018a19  jz      short loc_180018A26
0x180018a1b  cmp     eax, 0C0021029h
0x180018a20  jnz     loc_180018B1F
0x180018a26  test    r14d, r14d
0x180018a29  jz      loc_180018B1F
0x180018a2f  mov     rcx, rbp; CriticalSection
0x180018a32  call    cs:__imp_RtlEnterCriticalSection
0x180018a38  lea     r8, [rsi+90h]
0x180018a3f  mov     rdx, [r8]
0x180018a42  cmp     [rdx+8], r8
0x180018a46  jnz     loc_180018B53
0x180018a4c  mov     rax, [rdx]
0x180018a4f  cmp     [rax+8], rdx
0x180018a53  jnz     loc_180018B53
0x180018a59  mov     [r8], rax
0x180018a5c  mov     [rax+8], r8
0x180018a60  cmp     rdx, r8
0x180018a63  jz      short loc_180018A74
0x180018a65  mov     qword ptr [rdx], 0
0x180018a6c  mov     qword ptr [rdx+8], 0
0x180018a74  mov     rcx, rbp; CriticalSection
0x180018a77  lea     rbx, [rdx-48h]
0x180018a7b  call    cs:__imp_RtlLeaveCriticalSection
0x180018a81  test    rbx, rbx
0x180018a84  jz      loc_180018B1F
0x180018a8a  mov     rcx, [rsi+18h]; this
0x180018a8e  mov     dword ptr [rsi+0B4h], 6
0x180018a98  call    ?BeginSimpleSubmitAsync@HTTP2Channel@@QEAAJXZ; HTTP2Channel::BeginSimpleSubmitAsync(void)
0x180018a9d  mov     [rsi+0B8h], rbx
0x180018aa4  mov     ecx, [rbx+38h]
0x180018aa7  mov     [rsi+50h], ecx
0x180018aaa  test    eax, eax
0x180018aac  jnz     loc_180018B47
0x180018ab2  mov     r8, [rsi+48h]
0x180018ab6  mov     r9d, 1870016h
0x180018abc  mov     [rsp+68h+var_38], eax
0x180018ac0  mov     dl, 6Fh ; 'o'
0x180018ac2  mov     [rsp+68h+var_40], eax
0x180018ac6  mov     cl, 32h ; '2'
0x180018ac8  mov     eax, [rbx+38h]
0x180018acb  mov     [rsp+68h+var_48], eax
0x180018acf  call    cs:__imp_I_RpcLogEvent
0x180018ad5  mov     r8d, [rbx+38h]; dwNumberOfBytesToWrite
0x180018ad9  xor     r9d, r9d; lpdwNumberOfBytesWritten
0x180018adc  mov     rdx, [rbx+30h]; lpBuffer
0x180018ae0  mov     rcx, [rsi+48h]; hRequest
0x180018ae4  call    cs:__imp_WinHttpWriteData
0x180018aea  mov     rcx, [rsi+18h]; this
0x180018aee  mov     ebx, eax
0x180018af0  call    ?FinishSubmitAsync@HTTP2Channel@@QEAAXXZ; HTTP2Channel::FinishSubmitAsync(void)
0x180018af5  test    ebx, ebx
0x180018af7  jnz     short loc_180018B1F
0x180018af9  mov     dword ptr [rsi+0B4h], 3
0x180018b03  call    cs:__imp_GetLastError
0x180018b09  mov     rdx, rsi; pv
0x180018b0c  mov     dword ptr [rsi+54h], 0C002100Ah
0x180018b13  lea     rcx, ?HTTP2WinHttpDirectSend@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x180018b1a  call    ?TrySubmitWork@RPC_THREAD_POOL@@SAJP6AXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z1@Z; RPC_THREAD_POOL::TrySubmitWork(void (*)(_TP_CALLBACK_INSTANCE *,void *),void *)
0x180018b1f  mov     edx, [rsi+0B0h]
0x180018b25  mov     ecx, 2
0x180018b2a  lea     eax, [rdx-5]
0x180018b2d  cmp     eax, ecx
0x180018b2f  ja      short loc_180018BB0
0x180018b31  test    r14d, r14d
0x180018b34  jnz     short loc_180018BB0
0x180018b36  cmp     edx, 5
0x180018b39  jnz     short loc_180018B5A
0x180018b3b  mov     dword ptr [rsi+0B0h], 1
0x180018b45  jmp     short loc_180018B6B
0x180018b47  mov     dword ptr [rsi+0B4h], 3
0x180018b51  jmp     short loc_180018B09
0x180018b53  mov     ecx, 3
0x180018b58  int     29h; Win8: RtlFailFast(ecx)
0x180018b5a  cmp     edx, 7
0x180018b5d  mov     eax, 4
0x180018b62  cmovz   ecx, eax
0x180018b65  mov     [rsi+0B0h], ecx
0x180018b6b  mov     rcx, [rsi+18h]; this
0x180018b6f  call    ?BeginSimpleSubmitAsync@HTTP2Channel@@QEAAJXZ; HTTP2Channel::BeginSimpleSubmitAsync(void)
0x180018b74  mov     ebx, eax
0x180018b76  test    eax, eax
0x180018b78  jnz     short loc_180018B9E
0x180018b7a  mov     rax, [rsi]
0x180018b7d  mov     rcx, rsi
0x180018b80  mov     edx, [rsi+0B0h]
0x180018b86  mov     rax, [rax+10h]
0x180018b8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018b8f  mov     rcx, [rsi+18h]; this
0x180018b93  mov     ebx, eax
0x180018b95  call    ?FinishSubmitAsync@HTTP2Channel@@QEAAXXZ; HTTP2Channel::FinishSubmitAsync(void)
0x180018b9a  test    ebx, ebx
0x180018b9c  jz      short loc_180018BB0
0x180018b9e  mov     rdx, rsi; pv
0x180018ba1  mov     [rsi+54h], ebx
0x180018ba4  lea     rcx, ?HTTP2WinHttpDirectReceive@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x180018bab  call    ?TrySubmitWork@RPC_THREAD_POOL@@SAJP6AXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z1@Z; RPC_THREAD_POOL::TrySubmitWork(void (*)(_TP_CALLBACK_INSTANCE *,void *),void *)
0x180018bb0  mov     [rsp+68h+var_38], 0
0x180018bb8  mov     r9d, 50015h
0x180018bbe  mov     [rsp+68h+var_40], 0
0x180018bc6  mov     r8, rsi
0x180018bc9  mov     dl, 6Fh ; 'o'
0x180018bcb  mov     [rsp+68h+var_48], edi
0x180018bcf  mov     cl, 32h ; '2'
0x180018bd1  call    cs:__imp_I_RpcLogEvent
0x180018bd7  mov     eax, edi
0x180018bd9  add     rsp, 40h
0x180018bdd  pop     r14
0x180018bdf  pop     rdi
0x180018be0  pop     rsi
0x180018be1  pop     rbp
0x180018be2  pop     rbx
0x180018be3  retn
```
