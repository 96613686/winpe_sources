# Windows::Internal::ComTaskPoolHandler::_FireCompletion(Windows::Internal::IAsyncFireCompletion *)

- ea: `0x18007ced4`
- end: `0x18007d026`
- name: `?_FireCompletion@ComTaskPoolHandler@Internal@Windows@@SAJPEAUIAsyncFireCompletion@23@@Z`
- size: `338`
- prototype: `__int64 __fastcall(struct Windows::Internal::IAsyncFireCompletion *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800770d0`

## callees

- `0x180016064`
- `0x180021ee0`
- `0x180060c54`
- `0x180072854`
- `0x18007ced4`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007cf6c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007cf6c`
- `SHCORE!SHTaskPoolQueueTask` at `0x18007cf87`
- `SHCORE!SHTaskPoolQueueTask` at `0x18007cf87`

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
  __int64 v6; // rdx
  __int64 v7; // r14
  __int64 v8; // rcx
  DWORD CurrentThreadId; // eax
  int v10; // esi
  bool v11; // si
  __int64 v12; // rdx
  __int64 v13; // rcx
  struct Windows::Internal::IAsyncFireCompletion *v15; // [rsp+68h] [rbp+10h] BYREF
  __int64 v16; // [rsp+70h] [rbp+18h] BYREF

  v1 = a1;
  v2 = (unsigned int)tls_index;
  v3 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  if ( !*(_BYTE *)(v3 + 8) )
    ((void (*)(void))_dyn_tls_on_demand_init)();
  if ( *(int *)(v3 + 12) <= 4 )
    goto LABEL_21;
  v4 = 0;
  v15 = v1;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v15);
  v15 = v1;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v15);
  v5 = (__int64 *)Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>,_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>(
                    &v16,
                    &v15);
  v7 = *v5;
  *v5 = 0;
  v8 = v16;
  if ( v16 )
  {
    v16 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncActionCompletedHandler>::Release(
      v8,
      v6);
  }
  CurrentThreadId = GetCurrentThreadId();
  v10 = SHTaskPoolQueueTask(3, 0, CurrentThreadId, 0);
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  v11 = v10 >= 0;
  a1 = v15;
  if ( v15 )
    (*(void (__fastcall **)(struct Windows::Internal::IAsyncFireCompletion *))(*(_QWORD *)v15 + 16LL))(v15);
  if ( v1 )
    (*(void (__fastcall **)(struct Windows::Internal::IAsyncFireCompletion *))(*(_QWORD *)v1 + 16LL))(v1);
  if ( !v11 )
  {
LABEL_21:
    if ( !*(_BYTE *)(v3 + 8) )
      _dyn_tls_on_demand_init(a1, v2);
    ++*(_DWORD *)(v3 + 12);
    v4 = (*(__int64 (__fastcall **)(struct Windows::Internal::IAsyncFireCompletion *))(*(_QWORD *)v1 + 24LL))(v1);
    if ( !*(_BYTE *)(v3 + 8) )
      _dyn_tls_on_demand_init(v13, v12);
    --*(_DWORD *)(v3 + 12);
  }
  return v4;
}

```

## disassembly

```asm
0x18007ced4  mov     [rsp+arg_0], rbx
0x18007ced9  mov     [rsp+arg_18], rbp
0x18007cede  push    rsi
0x18007cedf  push    rdi
0x18007cee0  push    r12
0x18007cee2  push    r13
0x18007cee4  push    r14
0x18007cee6  sub     rsp, 30h
0x18007ceea  mov     rdi, rcx
0x18007ceed  mov     edx, cs:_tls_index
0x18007cef3  mov     rax, gs:58h
0x18007cefc  mov     rbx, [rax+rdx*8]
0x18007cf00  mov     r13d, 8
0x18007cf06  cmp     byte ptr [rbx+r13], 0
0x18007cf0b  jnz     short loc_18007CF12
0x18007cf0d  call    __dyn_tls_on_demand_init
0x18007cf12  mov     r12d, 0Ch
0x18007cf18  cmp     dword ptr [r12+rbx], 4
0x18007cf1d  jle     loc_18007CFDC
0x18007cf23  xor     ebp, ebp
0x18007cf25  mov     [rsp+58h+arg_8], rdi
0x18007cf2a  lea     rcx, [rsp+58h+arg_8]
0x18007cf2f  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18007cf34  mov     [rsp+58h+arg_8], rdi
0x18007cf39  lea     rcx, [rsp+58h+arg_8]
0x18007cf3e  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18007cf43  lea     rdx, [rsp+58h+arg_8]
0x18007cf48  lea     rcx, [rsp+58h+arg_10]
0x18007cf4d  call    ??$Make@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@@12@$$QEAV_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>,_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>(_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_ &&)
0x18007cf52  mov     r14, [rax]
0x18007cf55  mov     [rax], rbp
0x18007cf58  mov     rcx, [rsp+58h+arg_10]
0x18007cf5d  test    rcx, rcx
0x18007cf60  jz      short loc_18007CF6C
0x18007cf62  mov     [rsp+58h+arg_10], rbp
0x18007cf67  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIAsyncActionCompletedHandler@Foundation@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncActionCompletedHandler>::Release(void)
0x18007cf6c  call    cs:__imp_GetCurrentThreadId
0x18007cf72  mov     [rsp+58h+var_30], rbp
0x18007cf77  mov     [rsp+58h+var_38], r14
0x18007cf7c  xor     r9d, r9d
0x18007cf7f  mov     r8d, eax
0x18007cf82  xor     edx, edx
0x18007cf84  lea     ecx, [rdx+3]
0x18007cf87  call    cs:__imp_SHTaskPoolQueueTask
0x18007cf8d  mov     esi, eax
0x18007cf8f  test    r14, r14
0x18007cf92  jz      short loc_18007CFA4
0x18007cf94  mov     rax, [r14]
0x18007cf97  mov     rcx, r14
0x18007cf9a  mov     rax, [rax+10h]
0x18007cf9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cfa3  nop
0x18007cfa4  shr     esi, 1Fh
0x18007cfa7  xor     sil, 1
0x18007cfab  mov     rcx, [rsp+58h+arg_8]
0x18007cfb0  test    rcx, rcx
0x18007cfb3  jz      short loc_18007CFC2
0x18007cfb5  mov     rax, [rcx]
0x18007cfb8  mov     rax, [rax+10h]
0x18007cfbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cfc1  nop
0x18007cfc2  test    rdi, rdi
0x18007cfc5  jz      short loc_18007CFD7
0x18007cfc7  mov     rax, [rdi]
0x18007cfca  mov     rcx, rdi
0x18007cfcd  mov     rax, [rax+10h]
0x18007cfd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cfd6  nop
0x18007cfd7  test    sil, sil
0x18007cfda  jnz     short loc_18007D00D
0x18007cfdc  cmp     byte ptr [rbx+r13], 0
0x18007cfe1  jnz     short loc_18007CFE8
0x18007cfe3  call    __dyn_tls_on_demand_init
0x18007cfe8  inc     dword ptr [r12+rbx]
0x18007cfec  mov     rax, [rdi]
0x18007cfef  mov     rcx, rdi
0x18007cff2  mov     rax, [rax+18h]
0x18007cff6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cffb  mov     ebp, eax
0x18007cffd  cmp     byte ptr [rbx+r13], 0
0x18007d002  jnz     short loc_18007D009
0x18007d004  call    __dyn_tls_on_demand_init
0x18007d009  dec     dword ptr [r12+rbx]
0x18007d00d  mov     eax, ebp
0x18007d00f  mov     rbx, [rsp+58h+arg_0]
0x18007d014  mov     rbp, [rsp+58h+arg_18]
0x18007d019  add     rsp, 30h
0x18007d01d  pop     r14
0x18007d01f  pop     r13
0x18007d021  pop     r12
0x18007d023  pop     rdi
0x18007d024  pop     rsi
0x18007d025  retn
```
