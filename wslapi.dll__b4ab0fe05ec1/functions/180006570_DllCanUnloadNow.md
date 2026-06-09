# DllCanUnloadNow

- ea: `0x180006570`
- end: `0x18000658f`
- name: `DllCanUnloadNow`
- size: `31`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000611c`
- `0x1800063e4`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  __int64 *v0; // rax
  struct Microsoft::WRL::Details::ModuleBase *v1; // rdx
  bool v2; // r9

  v0 = Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create();
  return !Microsoft::WRL::Details::TerminateMap((Microsoft::WRL::Details *)v0, v1, 0, v2);
}

```

## disassembly

```asm
0x180006570  sub     rsp, 28h
0x180006574  call    ?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@23@XZ; Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)
0x180006579  xor     r8d, r8d; unsigned __int16 *
0x18000657c  mov     rcx, rax; this
0x18000657f  call    ?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEBG_N@Z; Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,ushort const *,bool)
0x180006584  movzx   eax, al
0x180006587  xor     eax, 1
0x18000658a  add     rsp, 28h
0x18000658e  retn
```
