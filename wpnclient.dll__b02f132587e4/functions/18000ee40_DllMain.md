# DllMain

- ea: `0x18000ee40`
- end: `0x18000eebb`
- name: `DllMain`
- size: `123`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001fd74`

## callees

- `0x18000ee40`
- `0x180012260`
- `0x180013620`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000ee57`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000ee57`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000ee71`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000ee92`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000ee71`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000ee92`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  BOOL result; // eax
  Microsoft::WRL::Details *v4; // rax
  struct Microsoft::WRL::Details::ModuleBase *v5; // rdx
  bool v6; // r9

  if ( fdwReason == 1 )
  {
    DisableThreadLibraryCalls(hinstDLL);
    InitOnceExecuteOnce(
      &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::initOnceInProc_,
      _lambda_5f1dd388c03885d19ee806198d2ac5ef_::_lambda_invoker_cdecl_,
      0,
      0);
    byte_180044928 = 1;
    InitOnceExecuteOnce(
      &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::initOnceInProc_,
      _lambda_5f1dd388c03885d19ee806198d2ac5ef_::_lambda_invoker_cdecl_,
      0,
      0);
    result = 1;
    byte_180044928 = 1;
  }
  else
  {
    if ( !fdwReason )
    {
      v4 = (Microsoft::WRL::Details *)Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(
                                        hinstDLL,
                                        fdwReason,
                                        lpvReserved);
      Microsoft::WRL::Details::TerminateMap(v4, v5, 0, v6);
    }
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x18000ee40  sub     rsp, 28h
0x18000ee44  cmp     edx, 1
0x18000ee47  jz      short loc_18000EE57
0x18000ee49  test    edx, edx
0x18000ee4b  jz      short loc_18000EEA9
0x18000ee4d  mov     eax, 1
0x18000ee52  add     rsp, 28h
0x18000ee56  retn
0x18000ee57  call    cs:__imp_DisableThreadLibraryCalls
0x18000ee5d  xor     r9d, r9d; Context
0x18000ee60  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18000ee67  xor     r8d, r8d; Parameter
0x18000ee6a  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x18000ee71  call    cs:__imp_InitOnceExecuteOnce
0x18000ee77  xor     r9d, r9d; Context
0x18000ee7a  mov     cs:byte_180044928, 1
0x18000ee81  xor     r8d, r8d; Parameter
0x18000ee84  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18000ee8b  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x18000ee92  call    cs:__imp_InitOnceExecuteOnce
0x18000ee98  mov     eax, 1
0x18000ee9d  mov     cs:byte_180044928, 1
0x18000eea4  add     rsp, 28h
0x18000eea8  retn
0x18000eea9  call    ?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@23@XZ; Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)
0x18000eeae  xor     r8d, r8d; unsigned __int16 *
0x18000eeb1  mov     rcx, rax; this
0x18000eeb4  call    ?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEBG_N@Z; Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,ushort const *,bool)
0x18000eeb9  jmp     short loc_18000EE4D
```
