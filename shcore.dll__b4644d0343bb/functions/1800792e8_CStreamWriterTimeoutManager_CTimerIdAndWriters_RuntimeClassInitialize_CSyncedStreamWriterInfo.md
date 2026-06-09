# CStreamWriterTimeoutManager::CTimerIdAndWriters::RuntimeClassInitialize(CSyncedStreamWriterInfo *)

- ea: `0x1800792e8`
- end: `0x1800793e4`
- name: `?RuntimeClassInitialize@CTimerIdAndWriters@CStreamWriterTimeoutManager@@QEAAJPEAVCSyncedStreamWriterInfo@@@Z`
- size: `252`
- prototype: `__int64 __fastcall(PVOID pv, struct CSyncedStreamWriterInfo *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800728c8`

## callees

- `0x180014358`
- `0x180023730`
- `0x1800278c0`
- `0x1800792e8`
- `0x18007a0f0`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180079304`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18007933e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180079304`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18007933e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CStreamWriterTimeoutManager::CTimerIdAndWriters::RuntimeClassInitialize(
        PTP_TIMER *pv,
        struct CSyncedStreamWriterInfo *a2)
{
  PTP_TIMER ThreadpoolTimer; // rdi
  int v5; // edi
  PTP_TIMER v6; // rdi
  struct _TP_TIMER *v7; // rdx
  _QWORD *v8; // rdx
  _QWORD v10[7]; // [rsp+20h] [rbp-38h] BYREF

  ThreadpoolTimer = CreateThreadpoolTimer(CStreamWriterTimeoutManager::s_OnTimeout, pv, 0);
  CAutoThreadpoolTimer::_Clear(pv + 8);
  pv[8] = ThreadpoolTimer;
  v5 = ResultFromWin32Bool(ThreadpoolTimer != 0);
  if ( v5 >= 0 )
  {
    v6 = CreateThreadpoolTimer(CStreamWriterTimeoutManager::s_OnTimeout, pv, 0);
    CAutoThreadpoolTimer::_Clear(pv + 9);
    pv[9] = v6;
    v5 = ResultFromWin32Bool(v6 != 0);
    if ( v5 >= 0 )
    {
      v10[0] = a2;
      Microsoft::WRL::ComPtr<CSyncedStreamWriterInfo>::InternalAddRef(v10);
      v5 = 0;
      v7 = pv[11];
      if ( v7 != pv[13]
        || (v5 = CTSimpleArray<Microsoft::WRL::ComPtr<ICurrentWindowChangeListener>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<ICurrentWindowChangeListener>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<ICurrentWindowChangeListener>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<ICurrentWindowChangeListener>>>::_EnsureCapacity(
                   pv + 10,
                   (char *)v7 + 1),
            v5 >= 0) )
      {
        pv[11] = (PTP_TIMER)((char *)pv[11] + 1);
        v8 = (_QWORD *)((char *)pv[10] + 8 * ((_QWORD)pv[11] - 1));
        if ( v8 )
        {
          *v8 = 0;
          if ( v8 != v10 )
          {
            *v8 = a2;
            a2 = 0;
          }
        }
      }
      if ( a2 )
        (*(void (__fastcall **)(char *))(*((_QWORD *)a2 + 10) + 16LL))((char *)a2 + 80);
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800792e8  push    rbx
0x1800792ea  push    rbp
0x1800792eb  push    rsi
0x1800792ec  push    rdi
0x1800792ed  sub     rsp, 38h
0x1800792f1  mov     rsi, rdx
0x1800792f4  mov     rbp, rcx
0x1800792f7  xor     r8d, r8d; pcbe
0x1800792fa  mov     rdx, rcx; pv
0x1800792fd  lea     rcx, ?s_OnTimeout@CStreamWriterTimeoutManager@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180079304  call    cs:__imp_CreateThreadpoolTimer
0x18007930a  mov     rdi, rax
0x18007930d  lea     rcx, [rbp+40h]; this
0x180079311  call    ?_Clear@CAutoThreadpoolTimer@@AEAAXXZ; CAutoThreadpoolTimer::_Clear(void)
0x180079316  mov     [rbp+40h], rdi
0x18007931a  xor     ecx, ecx
0x18007931c  test    rdi, rdi
0x18007931f  setnz   cl; int
0x180079322  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180079327  mov     edi, eax
0x180079329  test    eax, eax
0x18007932b  js      loc_1800793D9
0x180079331  xor     r8d, r8d; pcbe
0x180079334  mov     rdx, rbp; pv
0x180079337  lea     rcx, ?s_OnTimeout@CStreamWriterTimeoutManager@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18007933e  call    cs:__imp_CreateThreadpoolTimer
0x180079344  mov     rdi, rax
0x180079347  lea     rcx, [rbp+48h]; this
0x18007934b  call    ?_Clear@CAutoThreadpoolTimer@@AEAAXXZ; CAutoThreadpoolTimer::_Clear(void)
0x180079350  mov     [rbp+48h], rdi
0x180079354  xor     ecx, ecx
0x180079356  test    rdi, rdi
0x180079359  setnz   cl; int
0x18007935c  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180079361  mov     edi, eax
0x180079363  test    eax, eax
0x180079365  js      short loc_1800793D9
0x180079367  mov     [rsp+58h+var_38], rsi
0x18007936c  lea     rcx, [rsp+58h+var_38]
0x180079371  call    ?InternalAddRef@?$ComPtr@VCSyncedStreamWriterInfo@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<CSyncedStreamWriterInfo>::InternalAddRef(void)
0x180079376  nop
0x180079377  xor     edi, edi
0x180079379  mov     rdx, [rbp+58h]
0x18007937d  cmp     rdx, [rbp+68h]
0x180079381  jnz     short loc_180079395
0x180079383  inc     rdx
0x180079386  lea     rcx, [rbp+50h]
0x18007938a  call    ?_EnsureCapacity@?$CTSimpleArray@V?$ComPtr@UICurrentWindowChangeListener@@@WRL@Microsoft@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@V?$ComPtr@UICurrentWindowChangeListener@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardCompareHelper@V?$ComPtr@UICurrentWindowChangeListener@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardMergeHelper@V?$ComPtr@UICurrentWindowChangeListener@@@WRL@Microsoft@@@@@@QEAAJ_K0@Z; CTSimpleArray<Microsoft::WRL::ComPtr<ICurrentWindowChangeListener>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<ICurrentWindowChangeListener>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<ICurrentWindowChangeListener>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<ICurrentWindowChangeListener>>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x18007938f  mov     edi, eax
0x180079391  test    eax, eax
0x180079393  js      short loc_1800793C3
0x180079395  inc     qword ptr [rbp+58h]
0x180079399  mov     rdx, [rbp+58h]
0x18007939d  mov     rax, [rbp+50h]
0x1800793a1  dec     rdx
0x1800793a4  lea     rdx, [rax+rdx*8]
0x1800793a8  test    rdx, rdx
0x1800793ab  jz      short loc_1800793C3
0x1800793ad  mov     qword ptr [rdx], 0
0x1800793b4  lea     rax, [rsp+58h+var_38]
0x1800793b9  cmp     rdx, rax
0x1800793bc  jz      short loc_1800793C3
0x1800793be  mov     [rdx], rsi
0x1800793c1  xor     esi, esi
0x1800793c3  test    rsi, rsi
0x1800793c6  jz      short loc_1800793D9
0x1800793c8  lea     rcx, [rsi+50h]
0x1800793cc  mov     rax, [rcx]
0x1800793cf  mov     rax, [rax+10h]
0x1800793d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800793d8  nop
0x1800793d9  mov     eax, edi
0x1800793db  add     rsp, 38h
0x1800793df  pop     rdi
0x1800793e0  pop     rsi
0x1800793e1  pop     rbp
0x1800793e2  pop     rbx
0x1800793e3  retn
```
