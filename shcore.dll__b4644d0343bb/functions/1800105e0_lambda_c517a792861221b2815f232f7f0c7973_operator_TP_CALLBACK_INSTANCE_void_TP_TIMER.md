# _lambda_c517a792861221b2815f232f7f0c7973_::operator()(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x1800105e0`
- end: `0x18001067c`
- name: `??R_lambda_c517a792861221b2815f232f7f0c7973_@@QEBA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800105d0`

## callees

- `0x18000a6a0`
- `0x18000d6bc`
- `0x18000fe30`
- `0x1800105e0`
- `0x18001a0a4`
- `0x18001e800`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001065f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001065f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010673`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010673`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001060c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001060c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001066b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001066b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 _lambda_c517a792861221b2815f232f7f0c7973_::operator()(__int64 a1, volatile int *a2, __int64 a3, ...)
{
  struct _TP_TIMER *v4; // rbx
  __int64 v5; // rax
  DWORD LastError; // edi
  va_list va; // [rsp+58h] [rbp+20h] BYREF

  va_start(va, a3);
  if ( a3 )
    Microsoft::WRL::Details::SafeUnknownIncrementReference((Microsoft::WRL::Details *)(a3 + 20), a2);
  *(_DWORD *)(a3 + 48) = GetCurrentThreadId();
  v4 = (struct _TP_TIMER *)_InterlockedExchange64((volatile __int64 *)(a3 + 24), 0);
  if ( v4 )
  {
    LastError = GetLastError();
    CloseThreadpoolTimer(v4);
    SetLastError(LastError);
  }
  v5 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(va, a3 + 32);
  WorkThreadManager::s_AttachAndRecoverTask(v5);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a3 + 40);
  *(_DWORD *)(a3 + 48) = 0;
  return Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IDelayedTask,IUnknown>::Release(a3);
}

```

## disassembly

```asm
0x1800105e0  mov     rax, rsp
0x1800105e3  mov     [rax+20h], r9
0x1800105e7  mov     [rax+10h], rdx
0x1800105eb  mov     [rax+8], rcx
0x1800105ef  push    rbx
0x1800105f0  push    rsi
0x1800105f1  push    rdi
0x1800105f2  sub     rsp, 20h
0x1800105f6  mov     rsi, r8
0x1800105f9  mov     [rax+10h], r8
0x1800105fd  test    r8, r8
0x180010600  jz      short loc_18001060C
0x180010602  lea     rcx, [r8+14h]; this
0x180010606  call    ?SafeUnknownIncrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownIncrementReference(long volatile &)
0x18001060b  nop
0x18001060c  call    cs:__imp_GetCurrentThreadId
0x180010612  mov     [rsi+30h], eax
0x180010615  xor     ebx, ebx
0x180010617  xchg    rbx, [rsi+18h]
0x18001061b  test    rbx, rbx
0x18001061e  jnz     short loc_18001065F
0x180010620  mov     [rsp+38h+arg_0], 0
0x180010629  lea     rdx, [rsi+20h]
0x18001062d  lea     rcx, [rsp+38h+arg_18]
0x180010632  call    ??0?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@$$QEAV01@@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(wistd::unique_ptr<void,wil::process_heap_deleter> &&)
0x180010637  mov     rcx, rax
0x18001063a  call    ?s_AttachAndRecoverTask@WorkThreadManager@@CAXV?$unique_ptr@UTaskData@WorkThreadManager@@U?$default_delete@UTaskData@WorkThreadManager@@@wistd@@@wistd@@@Z; WorkThreadManager::s_AttachAndRecoverTask(wistd::unique_ptr<WorkThreadManager::TaskData,wistd::default_delete<WorkThreadManager::TaskData>>)
0x18001063f  lea     rcx, [rsi+28h]
0x180010643  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180010648  nop
0x180010649  mov     dword ptr [rsi+30h], 0
0x180010650  mov     rcx, rsi
0x180010653  add     rsp, 20h
0x180010657  pop     rdi
0x180010658  pop     rsi
0x180010659  pop     rbx
0x18001065a  jmp     ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIDelayedTask@@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IDelayedTask,IUnknown>::Release(void)
0x18001065f  call    cs:__imp_GetLastError
0x180010665  nop
0x180010666  mov     edi, eax
0x180010668  mov     rcx, rbx; pti
0x18001066b  call    cs:__imp_CloseThreadpoolTimer
0x180010671  mov     ecx, edi; dwErrCode
0x180010673  call    cs:__imp_SetLastError
0x180010679  jmp     short loc_180010620
```
