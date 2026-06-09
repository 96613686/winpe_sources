# DllCanUnloadNow

- ea: `0x18003a280`
- end: `0x18003a2ec`
- name: `DllCanUnloadNow`
- size: `108`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18003a280`
- `0x1800ca010`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x18003a2d5`
- `RPCRT4!NdrDllCanUnloadNow` at `0x18003a2d5`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18003a29a`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18003a29a`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  HRESULT CanUnloadNow; // ebx

  InitOnceExecuteOnce(
    &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::initOnceInProc_,
    _lambda_5f1dd388c03885d19ee806198d2ac5ef_::_lambda_invoker_cdecl_,
    0,
    0);
  CanUnloadNow = 1;
  byte_180135658 = 1;
  if ( !(*(unsigned int (__fastcall **)(void *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                               + 24LL))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_) )
  {
    CanUnloadNow = NdrDllCanUnloadNow(&gPFactory);
    if ( !CanUnloadNow )
      return Windows::UI::Core::CWindowServerFactory::s_instanceCount != 0;
  }
  return CanUnloadNow;
}

```

## disassembly

```asm
0x18003a280  push    rbx
0x18003a282  sub     rsp, 20h
0x18003a286  xor     r9d, r9d; Context
0x18003a289  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18003a290  xor     r8d, r8d; Parameter
0x18003a293  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x18003a29a  call    cs:__imp_InitOnceExecuteOnce
0x18003a2a0  mov     rax, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18003a2a7  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18003a2ae  mov     ebx, 1
0x18003a2b3  mov     cs:byte_180135658, bl
0x18003a2b9  mov     rax, [rax+18h]
0x18003a2bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a2c2  test    eax, eax
0x18003a2c4  jz      short loc_18003A2CE
0x18003a2c6  mov     eax, ebx
0x18003a2c8  add     rsp, 20h
0x18003a2cc  pop     rbx
0x18003a2cd  retn
0x18003a2ce  lea     rcx, gPFactory; pPSFactoryBuffer
0x18003a2d5  call    cs:__imp_NdrDllCanUnloadNow
0x18003a2db  mov     ebx, eax
0x18003a2dd  test    eax, eax
0x18003a2df  jnz     short loc_18003A2C6
0x18003a2e1  cmp     cs:?s_instanceCount@CWindowServerFactory@Core@UI@Windows@@2JA, eax; long Windows::UI::Core::CWindowServerFactory::s_instanceCount
0x18003a2e7  setnz   bl
0x18003a2ea  jmp     short loc_18003A2C6
```
