# DllGetActivationFactory

- ea: `0x1800174d0`
- end: `0x1800174fd`
- name: `DllGetActivationFactory`
- size: `45`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180016e20`
- `0x1800170e8`

## pseudocode

```c
__int64 DllGetActivationFactory()
{
  Microsoft::WRL::Details *v0; // rax

  v0 = (Microsoft::WRL::Details *)Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create();
  return Microsoft::WRL::Details::GetActivationFactory<1>(v0);
}

```

## disassembly

```asm
0x1800174d0  mov     [rsp+arg_0], rbx
0x1800174d5  push    rdi
0x1800174d6  sub     rsp, 20h
0x1800174da  mov     rbx, rdx
0x1800174dd  mov     rdi, rcx
0x1800174e0  call    ?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@23@XZ; Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)
0x1800174e5  mov     r9, rbx
0x1800174e8  mov     r8, rdi
0x1800174eb  mov     rcx, rax; this
0x1800174ee  mov     rbx, [rsp+28h+arg_0]
0x1800174f3  add     rsp, 20h
0x1800174f7  pop     rdi
0x1800174f8  jmp     ??$GetActivationFactory@$00@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBGPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z; Microsoft::WRL::Details::GetActivationFactory<1>(Microsoft::WRL::Details::ModuleBase *,ushort const *,HSTRING__ *,IActivationFactory * *)
```
