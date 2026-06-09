# DllCanUnloadNow

- ea: `0x1800174a0`
- end: `0x1800174bf`
- name: `DllCanUnloadNow`
- size: `31`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800170e8`
- `0x180017364`

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
0x1800174a0  sub     rsp, 28h
0x1800174a4  call    ?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@23@XZ; Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)
0x1800174a9  xor     r8d, r8d; unsigned __int16 *
0x1800174ac  mov     rcx, rax; this
0x1800174af  call    ?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEBG_N@Z; Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,ushort const *,bool)
0x1800174b4  movzx   eax, al
0x1800174b7  xor     eax, 1
0x1800174ba  add     rsp, 28h
0x1800174be  retn
```
