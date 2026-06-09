# HTTP2ChannelDataOriginator::DirectSendComplete(int *,void * *,uchar * *,uint *)

- ea: `0x180009030`
- end: `0x1800091b0`
- name: `?DirectSendComplete@HTTP2ChannelDataOriginator@@QEAAJPEAHPEAPEAXPEAPEAEPEAI@Z`
- size: `384`
- prototype: `__int64 __usercall@<rax>(HTTP2ChannelDataOriginator *__hidden this@<rcx>, int *@<rdx>, void **@<r8>, unsigned __int8 **@<r9>, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000aee0`

## callees

- `0x180009030`
- `0x180018980`
- `0x18001e91c`
- `0x180025010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x1800090be`
- `ntdll!RtlLeaveCriticalSection` at `0x1800090be`
- `ntdll!RtlEnterCriticalSection` at `0x180009087`
- `ntdll!RtlEnterCriticalSection` at `0x180009087`
- `RPCRT4!I_RpcLogEvent` at `0x180009078`
- `RPCRT4!I_RpcLogEvent` at `0x180009190`
- `RPCRT4!I_RpcLogEvent` at `0x180009078`
- `RPCRT4!I_RpcLogEvent` at `0x180009190`

## pseudocode

```c
__int64 __fastcall HTTP2ChannelDataOriginator::DirectSendComplete(
        HTTP2ChannelDataOriginator *this,
        int *a2,
        char **a3,
        unsigned __int8 **a4,
        unsigned int *a5)
{
  char *v5; // rsi
  int *v8; // rbx
  HTTP2ChannelDataOriginator *v9; // rdi
  HTTP2ChannelDataOriginator *v10; // r8
  char *v11; // rbx
  __int64 v12; // rax
  __int64 v13; // rdx
  char *v14; // rbx
  unsigned int v15; // eax
  char *v16; // r15
  unsigned int v17; // r14d
  BOOL v18; // ebp
  unsigned int v19; // ecx
  unsigned __int8 *v20; // rax
  __int64 v21; // rdx
  __int64 v22; // rcx
  unsigned int v23; // ebx

  v5 = (char *)this + 48;
  v8 = a2;
  v9 = this;
  v10 = this;
  LOBYTE(a2) = 111;
  LOBYTE(this) = 50;
  I_RpcLogEvent(this, a2, v10, 17432592, *(_QWORD *)v5 != (_QWORD)v5, 0, 0);
  *v8 = *((_DWORD *)v9 + 27);
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)v9 + 64));
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
  RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)v9 + 64));
  v13 = *((unsigned int *)v9 + 28);
  v14 = v11 - 72;
  if ( (_DWORD)v13 == -1073606647 )
    v13 = 3221360650LL;
  v15 = HTTP2TransportChannel::SendComplete(v9, v13, (struct HTTP2SendContext *)v14);
  v16 = *(char **)v5;
  v17 = v15;
  v18 = *(_QWORD *)v5 != (_QWORD)v5;
  if ( v15 == -1073606615 )
  {
    v19 = 0;
    v20 = 0;
    v14 = 0;
  }
  else
  {
    if ( *((_DWORD *)v9 + 27) )
      (*((void (__fastcall **)(char *))pRuntimeImportTable + 27))(v14);
    else
      (*((void (__fastcall **)(char *))pRuntimeImportTable + 28))(v14);
    v19 = *((_DWORD *)v14 + 14);
    v20 = (unsigned __int8 *)*((_QWORD *)v14 + 6);
  }
  *a3 = v14;
  *a4 = v20;
  *a5 = v19;
  v23 = (*(__int64 (__fastcall **)(HTTP2ChannelDataOriginator *, _QWORD))(*(_QWORD *)v9 + 80LL))(v9, v17);
  if ( v16 != v5 )
    RPC_THREAD_POOL::TrySubmitWork(HTTP2ChannelDataOriginatorDirectSend, v9);
  LOBYTE(v21) = 111;
  LOBYTE(v22) = 50;
  I_RpcLogEvent(v22, v21, v9, 655376, v18, 0, 0);
  return v23;
}

```

## disassembly

```asm
0x180009030  push    rbx
0x180009032  push    rbp
0x180009033  push    rsi
0x180009034  push    rdi
0x180009035  push    r12
0x180009037  push    r13
0x180009039  push    r14
0x18000903b  push    r15
0x18000903d  sub     rsp, 48h
0x180009041  xor     r14d, r14d
0x180009044  lea     rsi, [rcx+30h]
0x180009048  cmp     [rsi], rsi
0x18000904b  mov     eax, r14d
0x18000904e  mov     r13, r8
0x180009051  mov     [rsp+88h+var_58], r14d
0x180009056  setnz   al
0x180009059  mov     [rsp+88h+var_60], r14d
0x18000905e  mov     r12, r9
0x180009061  mov     [rsp+88h+var_68], eax
0x180009065  mov     rbx, rdx
0x180009068  mov     rdi, rcx
0x18000906b  mov     r8, rcx
0x18000906e  mov     r9d, 10A0010h
0x180009074  mov     dl, 6Fh ; 'o'
0x180009076  mov     cl, 32h ; '2'
0x180009078  call    cs:__imp_I_RpcLogEvent
0x18000907e  mov     eax, [rdi+6Ch]
0x180009081  lea     rcx, [rdi+40h]; CriticalSection
0x180009085  mov     [rbx], eax
0x180009087  call    cs:__imp_RtlEnterCriticalSection
0x18000908d  mov     rbx, [rsi]
0x180009090  cmp     [rbx+8], rsi
0x180009094  jnz     loc_1800091A9
0x18000909a  mov     rax, [rbx]
0x18000909d  cmp     [rax+8], rbx
0x1800090a1  jnz     loc_1800091A9
0x1800090a7  mov     [rsi], rax
0x1800090aa  mov     [rax+8], rsi
0x1800090ae  cmp     rbx, rsi
0x1800090b1  jz      short loc_1800090BA
0x1800090b3  mov     [rbx], r14
0x1800090b6  mov     [rbx+8], r14
0x1800090ba  lea     rcx, [rdi+40h]; CriticalSection
0x1800090be  call    cs:__imp_RtlLeaveCriticalSection
0x1800090c4  mov     edx, [rdi+70h]
0x1800090c7  add     rbx, 0FFFFFFFFFFFFFFB8h
0x1800090cb  cmp     edx, 0C0021009h
0x1800090d1  mov     eax, 0C002100Ah
0x1800090d6  mov     r8, rbx; struct HTTP2SendContext *
0x1800090d9  mov     rcx, rdi; this
0x1800090dc  cmovz   edx, eax; int
0x1800090df  call    ?SendComplete@HTTP2TransportChannel@@UEAAJJPEAVHTTP2SendContext@@@Z; HTTP2TransportChannel::SendComplete(long,HTTP2SendContext *)
0x1800090e4  mov     r15, [rsi]
0x1800090e7  xor     ebp, ebp
0x1800090e9  cmp     r15, rsi
0x1800090ec  mov     r14d, eax
0x1800090ef  setnz   bpl
0x1800090f3  cmp     eax, 0C0021029h
0x1800090f8  jz      short loc_18000912F
0x1800090fa  cmp     dword ptr [rdi+6Ch], 0
0x1800090fe  jz      short loc_180009110
0x180009100  mov     rcx, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x180009107  mov     rax, [rcx+0D8h]
0x18000910e  jmp     short loc_18000911E
0x180009110  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x180009117  mov     rax, [rax+0E0h]
0x18000911e  mov     rcx, rbx
0x180009121  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009126  mov     ecx, [rbx+38h]
0x180009129  mov     rax, [rbx+30h]
0x18000912d  jmp     short loc_180009135
0x18000912f  xor     ecx, ecx
0x180009131  xor     eax, eax
0x180009133  xor     ebx, ebx
0x180009135  mov     [r13+0], rbx
0x180009139  mov     edx, r14d
0x18000913c  mov     [r12], rax
0x180009140  mov     rax, [rsp+88h+arg_20]
0x180009148  mov     [rax], ecx
0x18000914a  mov     rcx, rdi
0x18000914d  mov     rax, [rdi]
0x180009150  mov     rax, [rax+50h]
0x180009154  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009159  mov     ebx, eax
0x18000915b  cmp     r15, rsi
0x18000915e  jz      short loc_18000916F
0x180009160  mov     rdx, rdi; pv
0x180009163  lea     rcx, ?HTTP2ChannelDataOriginatorDirectSend@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x18000916a  call    ?TrySubmitWork@RPC_THREAD_POOL@@SAJP6AXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z1@Z; RPC_THREAD_POOL::TrySubmitWork(void (*)(_TP_CALLBACK_INSTANCE *,void *),void *)
0x18000916f  mov     [rsp+88h+var_58], 0
0x180009177  mov     r9d, 0A0010h
0x18000917d  mov     [rsp+88h+var_60], 0
0x180009185  mov     r8, rdi
0x180009188  mov     dl, 6Fh ; 'o'
0x18000918a  mov     [rsp+88h+var_68], ebp
0x18000918e  mov     cl, 32h ; '2'
0x180009190  call    cs:__imp_I_RpcLogEvent
0x180009196  mov     eax, ebx
0x180009198  add     rsp, 48h
0x18000919c  pop     r15
0x18000919e  pop     r14
0x1800091a0  pop     r13
0x1800091a2  pop     r12
0x1800091a4  pop     rdi
0x1800091a5  pop     rsi
0x1800091a6  pop     rbp
0x1800091a7  pop     rbx
0x1800091a8  retn
0x1800091a9  mov     ecx, 3
0x1800091ae  int     29h; Win8: RtlFailFast(ecx)
```
