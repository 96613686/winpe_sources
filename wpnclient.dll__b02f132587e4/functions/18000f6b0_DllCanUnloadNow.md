# DllCanUnloadNow

- ea: `0x18000f6b0`
- end: `0x18000f70c`
- name: `DllCanUnloadNow`
- size: `92`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000f6b0`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000f6c8`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000f6c8`
- `RPCRT4!NdrDllCanUnloadNow` at `0x18000f705`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  InitOnceExecuteOnce(
    &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::initOnceInProc_,
    _lambda_5f1dd388c03885d19ee806198d2ac5ef_::_lambda_invoker_cdecl_,
    0,
    0);
  byte_180044928 = 1;
  if ( (*(unsigned int (__fastcall **)(__int64 *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                                 + 24))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_) )
    return 1;
  else
    return NdrDllCanUnloadNow(&gPFactory);
}

```

## disassembly

```asm
0x18000f6b0  sub     rsp, 28h
0x18000f6b4  xor     r9d, r9d; Context
0x18000f6b7  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18000f6be  xor     r8d, r8d; Parameter
0x18000f6c1  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x18000f6c8  call    cs:__imp_InitOnceExecuteOnce
0x18000f6ce  mov     rax, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000f6d5  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000f6dc  mov     cs:byte_180044928, 1
0x18000f6e3  mov     rax, [rax+18h]
0x18000f6e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f6ec  test    eax, eax
0x18000f6ee  jz      short loc_18000F6FA
0x18000f6f0  mov     eax, 1
0x18000f6f5  add     rsp, 28h
0x18000f6f9  retn
0x18000f6fa  lea     rcx, gPFactory
0x18000f701  add     rsp, 28h
0x18000f705  jmp     cs:__imp_NdrDllCanUnloadNow
```
