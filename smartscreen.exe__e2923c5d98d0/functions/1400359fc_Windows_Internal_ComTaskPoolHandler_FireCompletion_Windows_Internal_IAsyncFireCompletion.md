# Windows::Internal::ComTaskPoolHandler::_FireCompletion(Windows::Internal::IAsyncFireCompletion *)

- ea: `0x1400359fc`
- end: `0x140035b77`
- name: `?_FireCompletion@ComTaskPoolHandler@Internal@Windows@@SAJPEAUIAsyncFireCompletion@23@@Z`
- size: `379`
- prototype: `__int64 __fastcall(struct Windows::Internal::IAsyncFireCompletion *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140033af0`

## callees

- `0x14001dbbc`
- `0x14001e640`
- `0x14002b254`
- `0x14002fc28`
- `0x1400359fc`
- `0x140068010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140035a93`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140035a93`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x140035aae`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x140035aae`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::ComTaskPoolHandler::_FireCompletion(
        struct Windows::Internal::IAsyncFireCompletion *a1)
{
  unsigned int v2; // ebp
  __int64 *v3; // rax
  __int64 v4; // rsi
  DWORD CurrentThreadId; // eax
  int v6; // edi
  bool v7; // di
  PVOID ThreadLocalStoragePointer; // rax
  PVOID v9; // rcx
  struct Windows::Internal::IAsyncFireCompletion *v11; // [rsp+68h] [rbp+10h] BYREF
  __int64 v12; // [rsp+70h] [rbp+18h] BYREF

  if ( !*(_BYTE *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 8LL) )
    _dyn_tls_on_demand_init();
  if ( *(int *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 12LL) <= 4 )
    goto LABEL_21;
  v2 = 0;
  v11 = a1;
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(&v11);
  v11 = a1;
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(&v11);
  v3 = (__int64 *)Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>,_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>(
                    &v12,
                    &v11);
  v4 = *v3;
  *v3 = 0;
  if ( v12 )
  {
    v12 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release();
  }
  CurrentThreadId = GetCurrentThreadId();
  v6 = SHTaskPoolQueueTask(3, 0, CurrentThreadId, 0, v4, 0);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  v7 = v6 >= 0;
  if ( v11 )
    (*(void (__fastcall **)(struct Windows::Internal::IAsyncFireCompletion *))(*(_QWORD *)v11 + 16LL))(v11);
  if ( a1 )
    (*(void (__fastcall **)(struct Windows::Internal::IAsyncFireCompletion *))(*(_QWORD *)a1 + 16LL))(a1);
  if ( !v7 )
  {
LABEL_21:
    if ( !*(_BYTE *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 8LL) )
      _dyn_tls_on_demand_init();
    ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
    ++*(_DWORD *)(*(_QWORD *)ThreadLocalStoragePointer + 12LL);
    v2 = (*(__int64 (__fastcall **)(struct Windows::Internal::IAsyncFireCompletion *))(*(_QWORD *)a1 + 24LL))(a1);
    if ( !*(_BYTE *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 8LL) )
      _dyn_tls_on_demand_init();
    v9 = NtCurrentTeb()->ThreadLocalStoragePointer;
    --*(_DWORD *)(*(_QWORD *)v9 + 12LL);
  }
  return v2;
}

```

## disassembly

```asm
0x1400359fc  mov     [rsp+arg_0], rbx
0x140035a01  push    rbp
0x140035a02  push    rsi
0x140035a03  push    rdi
0x140035a04  push    r12
0x140035a06  push    r15
0x140035a08  sub     rsp, 30h
0x140035a0c  mov     rbx, rcx
0x140035a0f  mov     r12d, 8
0x140035a15  mov     rax, gs:58h
0x140035a1e  mov     rdx, [rax]
0x140035a21  cmp     byte ptr [r12+rdx], 0
0x140035a26  jnz     short loc_140035A2D
0x140035a28  call    __dyn_tls_on_demand_init
0x140035a2d  mov     r15d, 0Ch
0x140035a33  mov     rax, gs:58h
0x140035a3c  mov     rdx, [rax]
0x140035a3f  cmp     dword ptr [r15+rdx], 4
0x140035a44  jle     loc_140035B03
0x140035a4a  xor     ebp, ebp
0x140035a4c  mov     [rsp+58h+arg_8], rbx
0x140035a51  lea     rcx, [rsp+58h+arg_8]
0x140035a56  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x140035a5b  mov     [rsp+58h+arg_8], rbx
0x140035a60  lea     rcx, [rsp+58h+arg_8]
0x140035a65  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x140035a6a  lea     rdx, [rsp+58h+arg_8]
0x140035a6f  lea     rcx, [rsp+58h+arg_10]
0x140035a74  call    ??$Make@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@@12@$$QEAV_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>,_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>(_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_ &&)
0x140035a79  mov     rsi, [rax]
0x140035a7c  mov     [rax], rbp
0x140035a7f  mov     rcx, [rsp+58h+arg_10]
0x140035a84  test    rcx, rcx
0x140035a87  jz      short loc_140035A93
0x140035a89  mov     [rsp+58h+arg_10], rbp
0x140035a8e  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x140035a93  call    cs:__imp_GetCurrentThreadId
0x140035a99  mov     [rsp+58h+var_30], rbp
0x140035a9e  mov     [rsp+58h+var_38], rsi
0x140035aa3  xor     r9d, r9d
0x140035aa6  mov     r8d, eax
0x140035aa9  xor     edx, edx
0x140035aab  lea     ecx, [rdx+3]
0x140035aae  call    cs:__imp_SHTaskPoolQueueTask
0x140035ab4  mov     edi, eax
0x140035ab6  test    rsi, rsi
0x140035ab9  jz      short loc_140035ACB
0x140035abb  mov     rax, [rsi]
0x140035abe  mov     rcx, rsi
0x140035ac1  mov     rax, [rax+10h]
0x140035ac5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140035aca  nop
0x140035acb  shr     edi, 1Fh
0x140035ace  xor     dil, 1
0x140035ad2  mov     rcx, [rsp+58h+arg_8]
0x140035ad7  test    rcx, rcx
0x140035ada  jz      short loc_140035AE9
0x140035adc  mov     rax, [rcx]
0x140035adf  mov     rax, [rax+10h]
0x140035ae3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140035ae8  nop
0x140035ae9  test    rbx, rbx
0x140035aec  jz      short loc_140035AFE
0x140035aee  mov     rax, [rbx]
0x140035af1  mov     rcx, rbx
0x140035af4  mov     rax, [rax+10h]
0x140035af8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140035afd  nop
0x140035afe  test    dil, dil
0x140035b01  jnz     short loc_140035B64
0x140035b03  mov     rax, gs:58h
0x140035b0c  mov     rcx, [rax]
0x140035b0f  cmp     byte ptr [r12+rcx], 0
0x140035b14  jnz     short loc_140035B1B
0x140035b16  call    __dyn_tls_on_demand_init
0x140035b1b  mov     rax, gs:58h
0x140035b24  mov     rcx, [rax]
0x140035b27  inc     dword ptr [rcx+r15]
0x140035b2b  mov     rax, [rbx]
0x140035b2e  mov     rcx, rbx
0x140035b31  mov     rax, [rax+18h]
0x140035b35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140035b3a  mov     ebp, eax
0x140035b3c  mov     rcx, gs:58h
0x140035b45  mov     rdx, [rcx]
0x140035b48  cmp     byte ptr [r12+rdx], 0
0x140035b4d  jnz     short loc_140035B54
0x140035b4f  call    __dyn_tls_on_demand_init
0x140035b54  mov     rcx, gs:58h
0x140035b5d  mov     rdx, [rcx]
0x140035b60  dec     dword ptr [rdx+r15]
0x140035b64  mov     eax, ebp
0x140035b66  mov     rbx, [rsp+58h+arg_0]
0x140035b6b  add     rsp, 30h
0x140035b6f  pop     r15
0x140035b71  pop     r12
0x140035b73  pop     rdi
0x140035b74  pop     rsi
0x140035b75  pop     rbp
0x140035b76  retn
```
