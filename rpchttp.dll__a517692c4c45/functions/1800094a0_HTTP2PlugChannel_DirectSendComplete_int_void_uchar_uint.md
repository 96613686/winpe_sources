# HTTP2PlugChannel::DirectSendComplete(int *,void * *,uchar * *,uint *)

- ea: `0x1800094a0`
- end: `0x1800095e1`
- name: `?DirectSendComplete@HTTP2PlugChannel@@UEAAJPEAHPEAPEAXPEAPEAEPEAI@Z`
- size: `321`
- prototype: `__int64 __usercall@<rax>(HTTP2PlugChannel *__hidden this@<rcx>, int *@<rdx>, void **@<r8>, unsigned __int8 **@<r9>, unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800091c0`
- `0x1800095f0`

## callees

- `0x1800094a0`
- `0x180018980`
- `0x18001e91c`
- `0x180025010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18000953a`
- `ntdll!RtlLeaveCriticalSection` at `0x18000953a`
- `ntdll!RtlEnterCriticalSection` at `0x1800094f8`
- `ntdll!RtlEnterCriticalSection` at `0x1800094f8`
- `RPCRT4!I_RpcLogEvent` at `0x1800094e8`
- `RPCRT4!I_RpcLogEvent` at `0x1800095c3`
- `RPCRT4!I_RpcLogEvent` at `0x1800094e8`
- `RPCRT4!I_RpcLogEvent` at `0x1800095c3`

## pseudocode

```c
__int64 __fastcall HTTP2PlugChannel::DirectSendComplete(
        HTTP2PlugChannel *this,
        int *a2,
        void **a3,
        unsigned __int8 **a4,
        unsigned int *a5)
{
  char *v5; // rsi
  int *v8; // rbx
  HTTP2PlugChannel *v9; // r14
  HTTP2PlugChannel *v10; // r8
  char *v11; // rdi
  __int64 v12; // rax
  char *v13; // rbx
  __int64 v14; // rdx
  __int64 v15; // rdi
  __int64 v16; // rdx
  __int64 v17; // rcx

  v5 = (char *)this + 40;
  v8 = a2;
  v9 = this;
  v10 = this;
  LOBYTE(a2) = 111;
  LOBYTE(this) = 50;
  I_RpcLogEvent(this, a2, v10, 17432586, *(_QWORD *)v5 != (_QWORD)v5, 0, 0);
  *v8 = 0;
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)v9 + 56));
  v11 = *(char **)v5;
  if ( *(char **)(*(_QWORD *)v5 + 8LL) != v5 || (v12 = *(_QWORD *)v11, *(char **)(*(_QWORD *)v11 + 8LL) != v11) )
    __fastfail(3u);
  *(_QWORD *)v5 = v12;
  *(_QWORD *)(v12 + 8) = v5;
  if ( v11 != v5 )
  {
    *(_QWORD *)v11 = 0;
    *((_QWORD *)v11 + 1) = 0;
  }
  v13 = *(char **)v5;
  RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)v9 + 56));
  *a3 = v11 - 72;
  *a4 = (unsigned __int8 *)*((_QWORD *)v11 - 3);
  *a5 = *((_DWORD *)v11 - 4);
  v14 = *((unsigned int *)v9 + 24);
  if ( (_DWORD)v14 == -1073606647 )
    v14 = 3221360650LL;
  v15 = (unsigned int)HTTP2TransportChannel::SendComplete(v9, v14, (struct HTTP2SendContext *)(v11 - 72));
  (*(void (__fastcall **)(HTTP2PlugChannel *, __int64))(*(_QWORD *)v9 + 80LL))(v9, v15);
  if ( v13 != v5 )
    RPC_THREAD_POOL::TrySubmitWork((PTP_SIMPLE_CALLBACK)HTTP2PlugChannelDirectSend, v9);
  LOBYTE(v16) = 111;
  LOBYTE(v17) = 50;
  I_RpcLogEvent(v17, v16, v9, 655370, 0, 0, 0);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1800094a0  push    rbx
0x1800094a2  push    rbp
0x1800094a3  push    rsi
0x1800094a4  push    rdi
0x1800094a5  push    r12
0x1800094a7  push    r14
0x1800094a9  push    r15
0x1800094ab  sub     rsp, 40h
0x1800094af  xor     eax, eax
0x1800094b1  mov     [rsp+78h+var_48], 0
0x1800094b9  lea     rsi, [rcx+28h]
0x1800094bd  mov     [rsp+78h+var_50], 0
0x1800094c5  cmp     [rsi], rsi
0x1800094c8  mov     r12, r8
0x1800094cb  mov     r15, r9
0x1800094ce  mov     rbx, rdx
0x1800094d1  setnz   al
0x1800094d4  mov     r14, rcx
0x1800094d7  mov     r8, rcx
0x1800094da  mov     [rsp+78h+var_58], eax
0x1800094de  mov     r9d, 10A000Ah
0x1800094e4  mov     dl, 6Fh ; 'o'
0x1800094e6  mov     cl, 32h ; '2'
0x1800094e8  call    cs:__imp_I_RpcLogEvent
0x1800094ee  lea     rcx, [r14+38h]; CriticalSection
0x1800094f2  mov     dword ptr [rbx], 0
0x1800094f8  call    cs:__imp_RtlEnterCriticalSection
0x1800094fe  mov     rdi, [rsi]
0x180009501  cmp     [rdi+8], rsi
0x180009505  jnz     loc_1800095DA
0x18000950b  mov     rax, [rdi]
0x18000950e  cmp     [rax+8], rdi
0x180009512  jnz     loc_1800095DA
0x180009518  mov     [rsi], rax
0x18000951b  mov     [rax+8], rsi
0x18000951f  cmp     rdi, rsi
0x180009522  jz      short loc_180009533
0x180009524  mov     qword ptr [rdi], 0
0x18000952b  mov     qword ptr [rdi+8], 0
0x180009533  mov     rbx, [rsi]
0x180009536  lea     rcx, [r14+38h]; CriticalSection
0x18000953a  call    cs:__imp_RtlLeaveCriticalSection
0x180009540  lea     r8, [rdi-48h]; struct HTTP2SendContext *
0x180009544  mov     [r12], r8
0x180009548  mov     rax, [r8+30h]
0x18000954c  mov     [r15], rax
0x18000954f  mov     rax, [rsp+78h+arg_20]
0x180009557  mov     ecx, [r8+38h]
0x18000955b  mov     [rax], ecx
0x18000955d  mov     eax, 0C002100Ah
0x180009562  mov     edx, [r14+60h]
0x180009566  mov     rcx, r14; this
0x180009569  cmp     edx, 0C0021009h
0x18000956f  cmovz   edx, eax; int
0x180009572  call    ?SendComplete@HTTP2TransportChannel@@UEAAJJPEAVHTTP2SendContext@@@Z; HTTP2TransportChannel::SendComplete(long,HTTP2SendContext *)
0x180009577  mov     rcx, [r14]
0x18000957a  mov     edi, eax
0x18000957c  mov     edx, edi
0x18000957e  mov     rax, [rcx+50h]
0x180009582  mov     rcx, r14
0x180009585  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000958a  cmp     rbx, rsi
0x18000958d  jz      short loc_18000959E
0x18000958f  mov     rdx, r14; pv
0x180009592  lea     rcx, ?HTTP2PlugChannelDirectSend@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x180009599  call    ?TrySubmitWork@RPC_THREAD_POOL@@SAJP6AXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z1@Z; RPC_THREAD_POOL::TrySubmitWork(void (*)(_TP_CALLBACK_INSTANCE *,void *),void *)
0x18000959e  mov     [rsp+78h+var_48], 0
0x1800095a6  mov     r9d, 0A000Ah
0x1800095ac  mov     [rsp+78h+var_50], 0
0x1800095b4  mov     r8, r14
0x1800095b7  mov     dl, 6Fh ; 'o'
0x1800095b9  mov     [rsp+78h+var_58], 0
0x1800095c1  mov     cl, 32h ; '2'
0x1800095c3  call    cs:__imp_I_RpcLogEvent
0x1800095c9  mov     eax, edi
0x1800095cb  add     rsp, 40h
0x1800095cf  pop     r15
0x1800095d1  pop     r14
0x1800095d3  pop     r12
0x1800095d5  pop     rdi
0x1800095d6  pop     rsi
0x1800095d7  pop     rbp
0x1800095d8  pop     rbx
0x1800095d9  retn
0x1800095da  mov     ecx, 3
0x1800095df  int     29h; Win8: RtlFailFast(ecx)
```
