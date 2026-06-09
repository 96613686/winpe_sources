# Windows::Internal::ComTaskPoolHandler::_FireCompletion(Windows::Internal::IAsyncFireCompletion *)

- ea: `0x18005ab3c`
- end: `0x18005ac8e`
- name: `?_FireCompletion@ComTaskPoolHandler@Internal@Windows@@SAJPEAUIAsyncFireCompletion@23@@Z`
- size: `338`
- prototype: `__int64 __fastcall(struct Windows::Internal::IAsyncFireCompletion *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18004fbc0`

## callees

- `0x1800160c0`
- `0x180026498`
- `0x18002e374`
- `0x1800471e8`
- `0x18005ab3c`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005abd4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005abd4`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18005abef`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18005abef`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::ComTaskPoolHandler::_FireCompletion(
        struct Windows::Internal::IAsyncFireCompletion *a1)
{
  struct Windows::Internal::IAsyncFireCompletion *v1; // rdi
  __int64 v2; // rdx
  __int64 v3; // rbx
  unsigned int v4; // ebp
  __int64 *v5; // rax
  __int64 v6; // r14
  DWORD CurrentThreadId; // eax
  int v8; // esi
  bool v9; // si
  __int64 v10; // rdx
  __int64 v11; // rcx
  struct Windows::Internal::IAsyncFireCompletion *v13; // [rsp+68h] [rbp+10h] BYREF
  __int64 v14; // [rsp+70h] [rbp+18h] BYREF

  v1 = a1;
  v2 = (unsigned int)tls_index;
  v3 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  if ( !*(_BYTE *)(v3 + 4) )
    ((void (*)(void))_dyn_tls_on_demand_init)();
  if ( *(int *)(v3 + 8) <= 4 )
    goto LABEL_21;
  v4 = 0;
  v13 = v1;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v13);
  v13 = v1;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v13);
  v5 = (__int64 *)Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>,_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>(
                    &v14,
                    &v13);
  v6 = *v5;
  *v5 = 0;
  if ( v14 )
  {
    v14 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release();
  }
  CurrentThreadId = GetCurrentThreadId();
  v8 = SHTaskPoolQueueTask(3, 0, CurrentThreadId);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  v9 = v8 >= 0;
  a1 = v13;
  if ( v13 )
    (*(void (__fastcall **)(struct Windows::Internal::IAsyncFireCompletion *))(*(_QWORD *)v13 + 16LL))(v13);
  if ( v1 )
    (*(void (__fastcall **)(struct Windows::Internal::IAsyncFireCompletion *))(*(_QWORD *)v1 + 16LL))(v1);
  if ( !v9 )
  {
LABEL_21:
    if ( !*(_BYTE *)(v3 + 4) )
      _dyn_tls_on_demand_init(a1, v2);
    ++*(_DWORD *)(v3 + 8);
    v4 = (*(__int64 (__fastcall **)(struct Windows::Internal::IAsyncFireCompletion *))(*(_QWORD *)v1 + 24LL))(v1);
    if ( !*(_BYTE *)(v3 + 4) )
      _dyn_tls_on_demand_init(v11, v10);
    --*(_DWORD *)(v3 + 8);
  }
  return v4;
}

```

## disassembly

```asm
0x18005ab3c  mov     [rsp+arg_0], rbx
0x18005ab41  mov     [rsp+arg_18], rbp
0x18005ab46  push    rsi
0x18005ab47  push    rdi
0x18005ab48  push    r12
0x18005ab4a  push    r13
0x18005ab4c  push    r14
0x18005ab4e  sub     rsp, 30h
0x18005ab52  mov     rdi, rcx
0x18005ab55  mov     edx, cs:_tls_index
0x18005ab5b  mov     rax, gs:58h
0x18005ab64  mov     rbx, [rax+rdx*8]
0x18005ab68  mov     r13d, 4
0x18005ab6e  cmp     byte ptr [rbx+r13], 0
0x18005ab73  jnz     short loc_18005AB7A
0x18005ab75  call    __dyn_tls_on_demand_init
0x18005ab7a  mov     r12d, 8
0x18005ab80  cmp     dword ptr [r12+rbx], 4
0x18005ab85  jle     loc_18005AC44
0x18005ab8b  xor     ebp, ebp
0x18005ab8d  mov     [rsp+58h+arg_8], rdi
0x18005ab92  lea     rcx, [rsp+58h+arg_8]
0x18005ab97  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18005ab9c  mov     [rsp+58h+arg_8], rdi
0x18005aba1  lea     rcx, [rsp+58h+arg_8]
0x18005aba6  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18005abab  lea     rdx, [rsp+58h+arg_8]
0x18005abb0  lea     rcx, [rsp+58h+arg_10]
0x18005abb5  call    ??$Make@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@@12@$$QEAV_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>,_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>(_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_ &&)
0x18005abba  mov     r14, [rax]
0x18005abbd  mov     [rax], rbp
0x18005abc0  mov     rcx, [rsp+58h+arg_10]
0x18005abc5  test    rcx, rcx
0x18005abc8  jz      short loc_18005ABD4
0x18005abca  mov     [rsp+58h+arg_10], rbp
0x18005abcf  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x18005abd4  call    cs:__imp_GetCurrentThreadId
0x18005abda  mov     [rsp+58h+var_30], rbp
0x18005abdf  mov     [rsp+58h+var_38], r14
0x18005abe4  xor     r9d, r9d
0x18005abe7  mov     r8d, eax
0x18005abea  xor     edx, edx
0x18005abec  lea     ecx, [rdx+3]
0x18005abef  call    cs:__imp_SHTaskPoolQueueTask
0x18005abf5  mov     esi, eax
0x18005abf7  test    r14, r14
0x18005abfa  jz      short loc_18005AC0C
0x18005abfc  mov     rax, [r14]
0x18005abff  mov     rcx, r14
0x18005ac02  mov     rax, [rax+10h]
0x18005ac06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ac0b  nop
0x18005ac0c  shr     esi, 1Fh
0x18005ac0f  xor     sil, 1
0x18005ac13  mov     rcx, [rsp+58h+arg_8]
0x18005ac18  test    rcx, rcx
0x18005ac1b  jz      short loc_18005AC2A
0x18005ac1d  mov     rax, [rcx]
0x18005ac20  mov     rax, [rax+10h]
0x18005ac24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ac29  nop
0x18005ac2a  test    rdi, rdi
0x18005ac2d  jz      short loc_18005AC3F
0x18005ac2f  mov     rax, [rdi]
0x18005ac32  mov     rcx, rdi
0x18005ac35  mov     rax, [rax+10h]
0x18005ac39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ac3e  nop
0x18005ac3f  test    sil, sil
0x18005ac42  jnz     short loc_18005AC75
0x18005ac44  cmp     byte ptr [rbx+r13], 0
0x18005ac49  jnz     short loc_18005AC50
0x18005ac4b  call    __dyn_tls_on_demand_init
0x18005ac50  inc     dword ptr [r12+rbx]
0x18005ac54  mov     rax, [rdi]
0x18005ac57  mov     rcx, rdi
0x18005ac5a  mov     rax, [rax+18h]
0x18005ac5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ac63  mov     ebp, eax
0x18005ac65  cmp     byte ptr [rbx+r13], 0
0x18005ac6a  jnz     short loc_18005AC71
0x18005ac6c  call    __dyn_tls_on_demand_init
0x18005ac71  dec     dword ptr [r12+rbx]
0x18005ac75  mov     eax, ebp
0x18005ac77  mov     rbx, [rsp+58h+arg_0]
0x18005ac7c  mov     rbp, [rsp+58h+arg_18]
0x18005ac81  add     rsp, 30h
0x18005ac85  pop     r14
0x18005ac87  pop     r13
0x18005ac89  pop     r12
0x18005ac8b  pop     rdi
0x18005ac8c  pop     rsi
0x18005ac8d  retn
```
