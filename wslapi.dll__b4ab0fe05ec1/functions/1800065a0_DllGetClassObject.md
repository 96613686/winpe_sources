# DllGetClassObject

- ea: `0x1800065a0`
- end: `0x1800065e0`
- name: `DllGetClassObject`
- size: `64`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180005de4`
- `0x18000611c`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  __int64 *v4; // rax

  v4 = Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create();
  return Microsoft::WRL::Details::GetClassObject<1>(
           (Microsoft::WRL::Details *)v4,
           (struct Microsoft::WRL::Details::CreatorMap *)ppv);
}

```

## disassembly

```asm
0x1800065a0  mov     [rsp+arg_0], rbx
0x1800065a5  mov     [rsp+arg_8], rsi
0x1800065aa  push    rdi
0x1800065ab  sub     rsp, 30h
0x1800065af  mov     rbx, r8
0x1800065b2  mov     rdi, rdx
0x1800065b5  mov     rsi, rcx
0x1800065b8  call    ?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@23@XZ; Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)
0x1800065bd  mov     r9, rdi
0x1800065c0  mov     [rsp+38h+var_18], rbx; struct Microsoft::WRL::Details::CreatorMap *
0x1800065c5  mov     r8, rsi
0x1800065c8  mov     rcx, rax; this
0x1800065cb  call    ??$GetClassObject@$00@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBGAEBU_GUID@@2PEAPEAX@Z; Microsoft::WRL::Details::GetClassObject<1>(Microsoft::WRL::Details::ModuleBase *,ushort const *,_GUID const &,_GUID const &,void * *)
0x1800065d0  mov     rbx, [rsp+38h+arg_0]
0x1800065d5  mov     rsi, [rsp+38h+arg_8]
0x1800065da  add     rsp, 30h
0x1800065de  pop     rdi
0x1800065df  retn
```
