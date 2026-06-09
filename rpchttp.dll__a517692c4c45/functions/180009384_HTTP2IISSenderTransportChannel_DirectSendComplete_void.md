# HTTP2IISSenderTransportChannel::DirectSendComplete(void)

- ea: `0x180009384`
- end: `0x180009498`
- name: `?DirectSendComplete@HTTP2IISSenderTransportChannel@@QEAAJXZ`
- size: `276`
- prototype: `__int64 __fastcall(HTTP2IISSenderTransportChannel *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b330`

## callees

- `0x180009384`
- `0x180018980`
- `0x180025010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180009410`
- `ntdll!RtlLeaveCriticalSection` at `0x180009410`
- `ntdll!RtlEnterCriticalSection` at `0x1800093cf`
- `ntdll!RtlEnterCriticalSection` at `0x1800093cf`
- `RPCRT4!I_RpcLogEvent` at `0x1800093bf`
- `RPCRT4!I_RpcLogEvent` at `0x18000947e`
- `RPCRT4!I_RpcLogEvent` at `0x1800093bf`
- `RPCRT4!I_RpcLogEvent` at `0x18000947e`

## pseudocode

```c
__int64 __fastcall HTTP2IISSenderTransportChannel::DirectSendComplete(HTTP2IISSenderTransportChannel *this, __int64 a2)
{
  char *v2; // rdi
  HTTP2IISSenderTransportChannel *v3; // r14
  HTTP2IISSenderTransportChannel *v4; // r8
  char *v5; // rsi
  __int64 v6; // rax
  char *v7; // rbx
  __int64 v8; // rdx
  unsigned int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // rcx

  v2 = (char *)this + 104;
  v3 = this;
  v4 = this;
  LOBYTE(a2) = 111;
  LOBYTE(this) = 50;
  I_RpcLogEvent(this, a2, v4, 17432584, *(_QWORD *)v2 != (_QWORD)v2, 0, 0);
  do
  {
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)v3 + 128));
    v5 = *(char **)v2;
    if ( *(char **)(*(_QWORD *)v2 + 8LL) != v2 || (v6 = *(_QWORD *)v5, *(char **)(*(_QWORD *)v5 + 8LL) != v5) )
      __fastfail(3u);
    *(_QWORD *)v2 = v6;
    *(_QWORD *)(v6 + 8) = v2;
    if ( v5 != v2 )
    {
      *(_QWORD *)v5 = 0;
      *((_QWORD *)v5 + 1) = 0;
    }
    v7 = *(char **)v2;
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)v3 + 128));
    v8 = *((unsigned int *)v3 + 42);
    if ( (_DWORD)v8 == -1073606647 )
      v8 = 3221360650LL;
    _InterlockedDecrement((volatile signed __int32 *)v3 + 30);
    v9 = HTTP2TransportChannel::SendComplete(v3, v8, (struct HTTP2SendContext *)(v5 - 72));
    (*(void (__fastcall **)(HTTP2IISSenderTransportChannel *, _QWORD))(*(_QWORD *)v3 + 80LL))(v3, v9);
  }
  while ( v7 != v2 );
  LOBYTE(v10) = 111;
  LOBYTE(v11) = 50;
  I_RpcLogEvent(v11, v10, v3, 655368, 0, 0, 0);
  return 0;
}

```

## disassembly

```asm
0x180009384  push    rbx
0x180009386  push    rbp
0x180009387  push    rsi
0x180009388  push    rdi
0x180009389  push    r14
0x18000938b  sub     rsp, 40h
0x18000938f  xor     eax, eax
0x180009391  mov     [rsp+68h+var_38], 0
0x180009399  lea     rdi, [rcx+68h]
0x18000939d  mov     [rsp+68h+var_40], 0
0x1800093a5  cmp     [rdi], rdi
0x1800093a8  mov     r14, rcx
0x1800093ab  mov     r8, rcx
0x1800093ae  mov     r9d, 10A0008h
0x1800093b4  setnz   al
0x1800093b7  mov     dl, 6Fh ; 'o'
0x1800093b9  mov     cl, 32h ; '2'
0x1800093bb  mov     [rsp+68h+var_48], eax
0x1800093bf  call    cs:__imp_I_RpcLogEvent
0x1800093c5  lea     rbp, [r14+80h]
0x1800093cc  mov     rcx, rbp; CriticalSection
0x1800093cf  call    cs:__imp_RtlEnterCriticalSection
0x1800093d5  mov     rsi, [rdi]
0x1800093d8  cmp     [rsi+8], rdi
0x1800093dc  jnz     loc_180009491
0x1800093e2  mov     rax, [rsi]
0x1800093e5  cmp     [rax+8], rsi
0x1800093e9  jnz     loc_180009491
0x1800093ef  mov     [rdi], rax
0x1800093f2  mov     [rax+8], rdi
0x1800093f6  cmp     rsi, rdi
0x1800093f9  jz      short loc_18000940A
0x1800093fb  mov     qword ptr [rsi], 0
0x180009402  mov     qword ptr [rsi+8], 0
0x18000940a  mov     rbx, [rdi]
0x18000940d  mov     rcx, rbp; CriticalSection
0x180009410  call    cs:__imp_RtlLeaveCriticalSection
0x180009416  mov     edx, [r14+0A8h]
0x18000941d  lea     r8, [rsi-48h]; struct HTTP2SendContext *
0x180009421  cmp     edx, 0C0021009h
0x180009427  mov     eax, 0C002100Ah
0x18000942c  mov     rcx, r14; this
0x18000942f  cmovz   edx, eax; int
0x180009432  lock dec dword ptr [r14+78h]
0x180009437  call    ?SendComplete@HTTP2TransportChannel@@UEAAJJPEAVHTTP2SendContext@@@Z; HTTP2TransportChannel::SendComplete(long,HTTP2SendContext *)
0x18000943c  mov     rcx, [r14]
0x18000943f  mov     edx, eax
0x180009441  mov     r8, [rcx+50h]
0x180009445  mov     rcx, r14
0x180009448  mov     rax, r8
0x18000944b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009450  cmp     rbx, rdi
0x180009453  jnz     loc_1800093CC
0x180009459  mov     [rsp+68h+var_38], 0
0x180009461  mov     r9d, 0A0008h
0x180009467  mov     [rsp+68h+var_40], 0
0x18000946f  mov     r8, r14
0x180009472  mov     dl, 6Fh ; 'o'
0x180009474  mov     [rsp+68h+var_48], 0
0x18000947c  mov     cl, 32h ; '2'
0x18000947e  call    cs:__imp_I_RpcLogEvent
0x180009484  xor     eax, eax
0x180009486  add     rsp, 40h
0x18000948a  pop     r14
0x18000948c  pop     rdi
0x18000948d  pop     rsi
0x18000948e  pop     rbp
0x18000948f  pop     rbx
0x180009490  retn
0x180009491  mov     ecx, 3
0x180009496  int     29h; Win8: RtlFailFast(ecx)
```
