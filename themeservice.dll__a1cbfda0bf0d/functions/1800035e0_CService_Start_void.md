# CService::Start(void)

- ea: `0x1800035e0`
- end: `0x180003784`
- name: `?Start@CService@@QEAAXXZ`
- size: `420`
- prototype: `void __fastcall(CService *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x18000db00`

## callees

- `0x1800035e0`
- `0x180003790`
- `0x180003ee0`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000376e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000376e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003645`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003645`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180003674`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180003703`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180003674`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180003703`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180003605`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180003605`

## pseudocode

```c
void __fastcall CService::Start(CService *this)
{
  SERVICE_STATUS_HANDLE v2; // rax
  HANDLE v3; // rcx
  CAPIDispatchSync *v4; // rax
  _DWORD *v5; // r14
  SERVICE_STATUS_HANDLE v6; // rcx
  void (__fastcall **v7)(CService *, __int64); // rax
  CAPIDispatchSync *v8; // rax
  __int64 v9; // rax
  SERVICE_STATUS_HANDLE v10; // rcx
  __int64 v11; // rbx
  __int64 v12; // rax
  void *v13; // rcx

  _InterlockedIncrement((volatile signed __int32 *)this + 2);
  v2 = RegisterServiceCtrlHandlerExW(*((LPCWSTR *)this + 8), (LPHANDLER_FUNCTION_EX)CService::CB_HandlerEx, this);
  *((_QWORD *)this + 3) = v2;
  if ( !v2 )
    goto LABEL_5;
  v3 = s_hHeapToUse;
  *((_DWORD *)this + 8) = 32;
  *((_DWORD *)this + 10) = 1;
  v4 = (CAPIDispatchSync *)HeapAlloc(v3, 0, 0x50u);
  if ( !v4 )
  {
    *((_QWORD *)this + 10) = 0;
    v5 = (_DWORD *)((char *)this + 44);
LABEL_4:
    *((_DWORD *)this + 9) = 1;
    v6 = (SERVICE_STATUS_HANDLE)*((_QWORD *)this + 3);
    *v5 = 14;
    SetServiceStatus(v6, (LPSERVICE_STATUS)((char *)this + 32));
    *((_QWORD *)this + 3) = 0;
    goto LABEL_5;
  }
  v8 = CAPIDispatchSync::CAPIDispatchSync(v4);
  *((_QWORD *)this + 10) = v8;
  v5 = (_DWORD *)((char *)this + 44);
  if ( !v8 )
    goto LABEL_4;
  v9 = *(_QWORD *)this;
  *v5 = 0;
  *(_QWORD *)((char *)this + 52) = 0;
  (*(void (__fastcall **)(CService *, __int64))(v9 + 8))(this, 1);
  _InterlockedIncrement((volatile signed __int32 *)this + 2);
  v10 = (SERVICE_STATUS_HANDLE)*((_QWORD *)this + 3);
  *((_DWORD *)this + 9) = 4;
  SetServiceStatus(v10, (LPSERVICE_STATUS)((char *)this + 32));
  v11 = *((_QWORD *)this + 9);
  if ( *(_QWORD *)(v11 + 32) )
  {
    *(_QWORD *)(v11 + 40) = *((_QWORD *)this + 10);
    do
      CAPIConnection::ListenToServerConnectionPort((CAPIConnection *)v11);
    while ( !*(_BYTE *)(v11 + 20) );
  }
  v12 = *((_QWORD *)this + 10);
  if ( v12 )
  {
    v13 = *(void **)(v12 + 72);
    if ( v13 )
    {
      if ( WaitForSingleObject(v13, 0xEA60u) == 258 )
        *v5 = 1460;
    }
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 2, 0xFFFFFFFF) == 1 )
  {
    *((_BYTE *)this + 12) = 1;
    (**(void (__fastcall ***)(CService *, __int64))this)(this, 1);
  }
LABEL_5:
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 2, 0xFFFFFFFF) == 1 )
  {
    v7 = *(void (__fastcall ***)(CService *, __int64))this;
    *((_BYTE *)this + 12) = 1;
    (*v7)(this, 1);
  }
}

```

## disassembly

```asm
0x1800035e0  push    rsi
0x1800035e2  sub     rsp, 30h
0x1800035e6  mov     [rsp+38h+arg_8], rbp
0x1800035eb  mov     rsi, rcx
0x1800035ee  mov     [rsp+38h+arg_10], rdi
0x1800035f3  lock inc dword ptr [rcx+8]
0x1800035f7  mov     r8, rcx; lpContext
0x1800035fa  lea     rdx, ?CB_HandlerEx@CService@@CAKKKPEAX0@Z; lpHandlerProc
0x180003601  mov     rcx, [rcx+40h]; lpServiceName
0x180003605  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18000360b  mov     [rsi+18h], rax
0x18000360f  mov     ebp, 0FFFFFFFFh
0x180003614  test    rax, rax
0x180003617  jz      short loc_18000368D
0x180003619  mov     rcx, cs:?s_hHeapToUse@@3PEAXEA; hHeap
0x180003620  xor     edx, edx; dwFlags
0x180003622  mov     [rsp+38h+arg_0], rbx
0x180003627  mov     r8d, 50h ; 'P'; dwBytes
0x18000362d  mov     [rsp+38h+var_18], r15
0x180003632  mov     [rsp+38h+var_10], r14
0x180003637  mov     dword ptr [rsi+20h], 20h ; ' '
0x18000363e  mov     dword ptr [rsi+28h], 1
0x180003645  call    cs:__imp_HeapAlloc
0x18000364b  xor     r15d, r15d
0x18000364e  test    rax, rax
0x180003651  jnz     short loc_1800036C0
0x180003653  mov     [rsi+50h], r15
0x180003657  lea     r14, [rsi+2Ch]
0x18000365b  lea     rcx, [rsi+18h]
0x18000365f  mov     dword ptr [rsi+24h], 1
0x180003666  mov     rcx, [rcx]; hServiceStatus
0x180003669  lea     rdx, [rsi+20h]; lpServiceStatus
0x18000366d  mov     dword ptr [r14], 0Eh
0x180003674  call    cs:__imp_SetServiceStatus
0x18000367a  mov     [rsi+18h], r15
0x18000367e  mov     r14, [rsp+38h+var_10]
0x180003683  mov     rbx, [rsp+38h+arg_0]
0x180003688  mov     r15, [rsp+38h+var_18]
0x18000368d  lock xadd [rsi+8], ebp
0x180003692  mov     rdi, [rsp+38h+arg_10]
0x180003697  cmp     ebp, 1
0x18000369a  mov     rbp, [rsp+38h+arg_8]
0x18000369f  jz      short loc_1800036A7
0x1800036a1  add     rsp, 30h
0x1800036a5  pop     rsi
0x1800036a6  retn
0x1800036a7  mov     rax, [rsi]
0x1800036aa  mov     edx, 1
0x1800036af  mov     rcx, rsi
0x1800036b2  mov     byte ptr [rsi+0Ch], 1
0x1800036b6  mov     rax, [rax]
0x1800036b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036be  jmp     short loc_1800036A1
0x1800036c0  mov     rcx, rax; this
0x1800036c3  call    ??0CAPIDispatchSync@@QEAA@XZ; CAPIDispatchSync::CAPIDispatchSync(void)
0x1800036c8  mov     [rsi+50h], rax
0x1800036cc  lea     r14, [rsi+2Ch]
0x1800036d0  test    rax, rax
0x1800036d3  jz      short loc_18000365B
0x1800036d5  mov     rax, [rsi]
0x1800036d8  mov     edx, 1
0x1800036dd  mov     rcx, rsi
0x1800036e0  mov     [r14], r15d
0x1800036e3  mov     [rsi+34h], r15
0x1800036e7  mov     rax, [rax+8]
0x1800036eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036f0  lock inc dword ptr [rsi+8]
0x1800036f4  mov     rcx, [rsi+18h]; hServiceStatus
0x1800036f8  lea     rdx, [rsi+20h]; lpServiceStatus
0x1800036fc  mov     dword ptr [rsi+24h], 4
0x180003703  call    cs:__imp_SetServiceStatus
0x180003709  mov     rbx, [rsi+48h]
0x18000370d  cmp     [rbx+20h], r15
0x180003711  jnz     short loc_180003747
0x180003713  mov     rax, [rsi+50h]
0x180003717  test    rax, rax
0x18000371a  jnz     short loc_180003760
0x18000371c  mov     eax, ebp
0x18000371e  lock xadd [rsi+8], eax
0x180003723  cmp     eax, 1
0x180003726  jnz     loc_18000367E
0x18000372c  mov     [rsi+0Ch], al
0x18000372f  mov     edx, 1
0x180003734  mov     rax, [rsi]
0x180003737  mov     rcx, rsi
0x18000373a  mov     rax, [rax]
0x18000373d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003742  jmp     loc_18000367E
0x180003747  mov     rax, [rsi+50h]
0x18000374b  mov     [rbx+28h], rax
0x18000374f  nop
0x180003750  mov     rcx, rbx; this
0x180003753  call    ?ListenToServerConnectionPort@CAPIConnection@@AEAAJXZ; CAPIConnection::ListenToServerConnectionPort(void)
0x180003758  cmp     [rbx+14h], r15b
0x18000375c  jz      short loc_180003750
0x18000375e  jmp     short loc_180003713
0x180003760  mov     rcx, [rax+48h]; hHandle
0x180003764  test    rcx, rcx
0x180003767  jz      short loc_18000371C
0x180003769  mov     edx, 0EA60h; dwMilliseconds
0x18000376e  call    cs:__imp_WaitForSingleObject
0x180003774  cmp     eax, 102h
0x180003779  jnz     short loc_18000371C
0x18000377b  mov     dword ptr [r14], 5B4h
0x180003782  jmp     short loc_18000371C
```
