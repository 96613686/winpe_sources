# HTTP2FlowControlSender::DirectSendComplete(int *,int *,void * *,uchar * *,uint *)

- ea: `0x1800091ec`
- end: `0x18000937d`
- name: `?DirectSendComplete@HTTP2FlowControlSender@@QEAAJPEAH0PEAPEAXPEAPEAEPEAI@Z`
- size: `401`
- prototype: `__int64 __usercall@<rax>(HTTP2FlowControlSender *__hidden this@<rcx>, int *@<rdx>, int *@<r8>, void **@<r9>, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b1d0`

## callees

- `0x1800091ec`
- `0x180018980`
- `0x18001e91c`
- `0x180025010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180009289`
- `ntdll!RtlLeaveCriticalSection` at `0x180009289`
- `ntdll!RtlEnterCriticalSection` at `0x18000924a`
- `ntdll!RtlEnterCriticalSection` at `0x18000924a`
- `RPCRT4!I_RpcLogEvent` at `0x180009234`
- `RPCRT4!I_RpcLogEvent` at `0x18000935f`
- `RPCRT4!I_RpcLogEvent` at `0x180009234`
- `RPCRT4!I_RpcLogEvent` at `0x18000935f`

## pseudocode

```c
__int64 __fastcall HTTP2FlowControlSender::DirectSendComplete(
        HTTP2FlowControlSender *this,
        int *a2,
        int *a3,
        char **a4,
        unsigned __int8 **a5,
        unsigned int *a6)
{
  char *v6; // r14
  int *v9; // rbx
  HTTP2FlowControlSender *v10; // rsi
  HTTP2FlowControlSender *v11; // r8
  char *v12; // rbx
  __int64 v13; // rax
  __int64 v14; // rdx
  char *v15; // rbx
  unsigned int v16; // eax
  char *v17; // r15
  unsigned int v18; // ebp
  BOOL v19; // edi
  unsigned int v20; // ecx
  unsigned __int8 *v21; // rdx
  __int64 v22; // rdx
  __int64 v23; // rcx
  unsigned int v24; // ebx

  v6 = (char *)this + 32;
  v9 = a2;
  v10 = this;
  v11 = this;
  LOBYTE(a2) = 111;
  LOBYTE(this) = 50;
  I_RpcLogEvent(this, a2, v11, 17432595, *(_QWORD *)v6 != (_QWORD)v6, 0, 0);
  *v9 = *((unsigned __int8 *)v10 + 120);
  *a3 = *((unsigned __int8 *)v10 + 121);
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)v10 + 48));
  v12 = *(char **)v6;
  if ( *(char **)(*(_QWORD *)v6 + 8LL) != v6 || (v13 = *(_QWORD *)v12, *(char **)(*(_QWORD *)v12 + 8LL) != v12) )
    __fastfail(3u);
  *(_QWORD *)v6 = v13;
  *(_QWORD *)(v13 + 8) = v6;
  if ( v12 != v6 )
  {
    *(_QWORD *)v12 = 0;
    *((_QWORD *)v12 + 1) = 0;
  }
  RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)v10 + 48));
  v14 = *((unsigned int *)v10 + 29);
  v15 = v12 - 72;
  if ( (_DWORD)v14 == -1073606647 )
    v14 = 3221360650LL;
  v16 = HTTP2TransportChannel::SendComplete(v10, v14, (struct HTTP2SendContext *)v15);
  v17 = *(char **)v6;
  v18 = v16;
  v19 = *(_QWORD *)v6 != (_QWORD)v6;
  if ( v16 == -1073606615 || !*((_BYTE *)v10 + 121) )
  {
    v20 = 0;
    v21 = 0;
    v15 = 0;
  }
  else
  {
    if ( *((_BYTE *)v10 + 120) )
      (*((void (__fastcall **)(char *))pRuntimeImportTable + 27))(v15);
    else
      (*((void (__fastcall **)(char *))pRuntimeImportTable + 28))(v15);
    v20 = *((_DWORD *)v15 + 14);
    v21 = (unsigned __int8 *)*((_QWORD *)v15 + 6);
  }
  *a4 = v15;
  *a5 = v21;
  *a6 = v20;
  v24 = (*(__int64 (__fastcall **)(HTTP2FlowControlSender *, _QWORD))(*(_QWORD *)v10 + 80LL))(v10, v18);
  if ( v17 != v6 )
    RPC_THREAD_POOL::TrySubmitWork(HTTP2FlowControlChannelDirectSend, v10);
  LOBYTE(v22) = 111;
  LOBYTE(v23) = 50;
  I_RpcLogEvent(v23, v22, v10, 655379, v19, 0, 0);
  return v24;
}

```

## disassembly

```asm
0x1800091ec  push    rbx
0x1800091ee  push    rbp
0x1800091ef  push    rsi
0x1800091f0  push    rdi
0x1800091f1  push    r12
0x1800091f3  push    r14
0x1800091f5  push    r15
0x1800091f7  sub     rsp, 40h
0x1800091fb  xor     eax, eax
0x1800091fd  mov     [rsp+78h+var_48], 0
0x180009205  lea     r14, [rcx+20h]
0x180009209  mov     [rsp+78h+var_50], 0
0x180009211  cmp     [r14], r14
0x180009214  mov     rdi, r8
0x180009217  mov     r12, r9
0x18000921a  mov     rbx, rdx
0x18000921d  setnz   al
0x180009220  mov     rsi, rcx
0x180009223  mov     r8, rcx
0x180009226  mov     [rsp+78h+var_58], eax
0x18000922a  mov     r9d, 10A0013h
0x180009230  mov     dl, 6Fh ; 'o'
0x180009232  mov     cl, 32h ; '2'
0x180009234  call    cs:__imp_I_RpcLogEvent
0x18000923a  movzx   eax, byte ptr [rsi+78h]
0x18000923e  lea     rcx, [rsi+30h]; CriticalSection
0x180009242  mov     [rbx], eax
0x180009244  movzx   eax, byte ptr [rsi+79h]
0x180009248  mov     [rdi], eax
0x18000924a  call    cs:__imp_RtlEnterCriticalSection
0x180009250  mov     rbx, [r14]
0x180009253  cmp     [rbx+8], r14
0x180009257  jnz     loc_180009376
0x18000925d  mov     rax, [rbx]
0x180009260  cmp     [rax+8], rbx
0x180009264  jnz     loc_180009376
0x18000926a  mov     [r14], rax
0x18000926d  mov     [rax+8], r14
0x180009271  cmp     rbx, r14
0x180009274  jz      short loc_180009285
0x180009276  mov     qword ptr [rbx], 0
0x18000927d  mov     qword ptr [rbx+8], 0
0x180009285  lea     rcx, [rsi+30h]; CriticalSection
0x180009289  call    cs:__imp_RtlLeaveCriticalSection
0x18000928f  mov     edx, [rsi+74h]
0x180009292  add     rbx, 0FFFFFFFFFFFFFFB8h
0x180009296  cmp     edx, 0C0021009h
0x18000929c  mov     eax, 0C002100Ah
0x1800092a1  mov     r8, rbx; struct HTTP2SendContext *
0x1800092a4  mov     rcx, rsi; this
0x1800092a7  cmovz   edx, eax; int
0x1800092aa  call    ?SendComplete@HTTP2TransportChannel@@UEAAJJPEAVHTTP2SendContext@@@Z; HTTP2TransportChannel::SendComplete(long,HTTP2SendContext *)
0x1800092af  mov     r15, [r14]
0x1800092b2  xor     edi, edi
0x1800092b4  cmp     r15, r14
0x1800092b7  mov     ebp, eax
0x1800092b9  setnz   dil
0x1800092bd  cmp     eax, 0C0021029h
0x1800092c2  jz      short loc_1800092F8
0x1800092c4  cmp     byte ptr [rsi+79h], 0
0x1800092c8  jz      short loc_1800092F8
0x1800092ca  cmp     byte ptr [rsi+78h], 0
0x1800092ce  mov     rcx, rbx
0x1800092d1  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x1800092d8  jz      short loc_1800092E3
0x1800092da  mov     rax, [rax+0D8h]
0x1800092e1  jmp     short loc_1800092EA
0x1800092e3  mov     rax, [rax+0E0h]
0x1800092ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092ef  mov     ecx, [rbx+38h]
0x1800092f2  mov     rdx, [rbx+30h]
0x1800092f6  jmp     short loc_1800092FE
0x1800092f8  xor     ecx, ecx
0x1800092fa  xor     edx, edx
0x1800092fc  xor     ebx, ebx
0x1800092fe  mov     rax, [rsp+78h+arg_20]
0x180009306  mov     [r12], rbx
0x18000930a  mov     [rax], rdx
0x18000930d  mov     edx, ebp
0x18000930f  mov     rax, [rsp+78h+arg_28]
0x180009317  mov     [rax], ecx
0x180009319  mov     rcx, rsi
0x18000931c  mov     rax, [rsi]
0x18000931f  mov     rax, [rax+50h]
0x180009323  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009328  mov     ebx, eax
0x18000932a  cmp     r15, r14
0x18000932d  jz      short loc_18000933E
0x18000932f  mov     rdx, rsi; pv
0x180009332  lea     rcx, ?HTTP2FlowControlChannelDirectSend@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x180009339  call    ?TrySubmitWork@RPC_THREAD_POOL@@SAJP6AXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z1@Z; RPC_THREAD_POOL::TrySubmitWork(void (*)(_TP_CALLBACK_INSTANCE *,void *),void *)
0x18000933e  mov     [rsp+78h+var_48], 0
0x180009346  mov     r9d, 0A0013h
0x18000934c  mov     [rsp+78h+var_50], 0
0x180009354  mov     r8, rsi
0x180009357  mov     dl, 6Fh ; 'o'
0x180009359  mov     [rsp+78h+var_58], edi
0x18000935d  mov     cl, 32h ; '2'
0x18000935f  call    cs:__imp_I_RpcLogEvent
0x180009365  mov     eax, ebx
0x180009367  add     rsp, 40h
0x18000936b  pop     r15
0x18000936d  pop     r14
0x18000936f  pop     r12
0x180009371  pop     rdi
0x180009372  pop     rsi
0x180009373  pop     rbp
0x180009374  pop     rbx
0x180009375  retn
0x180009376  mov     ecx, 3
0x18000937b  int     29h; Win8: RtlFailFast(ecx)
```
