# DllCanUnloadNow

- ea: `0x18000d2b0`
- end: `0x18000d2ea`
- name: `DllCanUnloadNow`
- size: `58`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000d2b0`
- `0x180031010`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x18000d2bb`
- `RPCRT4!NdrDllCanUnloadNow` at `0x18000d2bb`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  HRESULT result; // eax

  result = NdrDllCanUnloadNow(&gPFactory);
  if ( !result )
    return (*(__int64 (__fastcall **)(void *))(qword_18004DA80 + 24LL))(&qword_18004DA80) != 0;
  return result;
}

```

## disassembly

```asm
0x18000d2b0  sub     rsp, 28h
0x18000d2b4  lea     rcx, gPFactory; pPSFactoryBuffer
0x18000d2bb  call    cs:__imp_NdrDllCanUnloadNow
0x18000d2c1  test    eax, eax
0x18000d2c3  jnz     short loc_18000D2E5
0x18000d2c5  mov     rax, cs:qword_18004DA80
0x18000d2cc  lea     rcx, qword_18004DA80
0x18000d2d3  mov     rax, [rax+18h]
0x18000d2d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d2dc  xor     ecx, ecx
0x18000d2de  test    eax, eax
0x18000d2e0  setnz   cl
0x18000d2e3  mov     eax, ecx
0x18000d2e5  add     rsp, 28h
0x18000d2e9  retn
```
