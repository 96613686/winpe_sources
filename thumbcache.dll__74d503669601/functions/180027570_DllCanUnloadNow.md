# DllCanUnloadNow

- ea: `0x180027570`
- end: `0x1800275ae`
- name: `DllCanUnloadNow`
- size: `62`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180027570`
- `0x1800275c0`
- `0x180049010`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x18002757b`
- `RPCRT4!NdrDllCanUnloadNow` at `0x18002757b`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  __int64 v0; // rax
  HRESULT result; // eax

  result = 1;
  if ( !NdrDllCanUnloadNow(&gPFactory) )
  {
    v0 = Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create();
    if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v0 + 24LL))(v0) )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180027570  sub     rsp, 28h
0x180027574  lea     rcx, gPFactory; pPSFactoryBuffer
0x18002757b  call    cs:__imp_NdrDllCanUnloadNow
0x180027581  test    eax, eax
0x180027583  jnz     short loc_1800275A0
0x180027585  call    ?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@23@XZ; Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)
0x18002758a  mov     rdx, rax
0x18002758d  mov     rcx, [rax]
0x180027590  mov     rax, [rcx+18h]
0x180027594  mov     rcx, rdx
0x180027597  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002759c  test    eax, eax
0x18002759e  jz      short loc_1800275AA
0x1800275a0  mov     eax, 1
0x1800275a5  add     rsp, 28h
0x1800275a9  retn
0x1800275aa  xor     eax, eax
0x1800275ac  jmp     short loc_1800275A5
```
