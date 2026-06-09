# DllCanUnloadNow

- ea: `0x18000b970`
- end: `0x18000b9a4`
- name: `DllCanUnloadNow`
- size: `52`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000ae84`
- `0x18000b670`
- `0x18000b970`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x18000b993`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  Microsoft::WRL::Details *v0; // rax
  struct Microsoft::WRL::Details::ModuleBase *v1; // rdx
  bool v2; // r9

  v0 = (Microsoft::WRL::Details *)Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create();
  if ( Microsoft::WRL::Details::TerminateMap(v0, v1, 0, v2) )
    return NdrDllCanUnloadNow(&gPFactory);
  else
    return 1;
}

```

## disassembly

```asm
0x18000b970  sub     rsp, 28h
0x18000b974  call    ?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@23@XZ; Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)
0x18000b979  xor     r8d, r8d; unsigned __int16 *
0x18000b97c  mov     rcx, rax; this
0x18000b97f  call    ?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEBG_N@Z; Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,ushort const *,bool)
0x18000b984  test    al, al
0x18000b986  jz      short loc_18000B99A
0x18000b988  lea     rcx, gPFactory
0x18000b98f  add     rsp, 28h
0x18000b993  jmp     cs:__imp_NdrDllCanUnloadNow
0x18000b99a  mov     eax, 1
0x18000b99f  add     rsp, 28h
0x18000b9a3  retn
```
