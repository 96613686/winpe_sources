# DllCanUnloadNow

- ea: `0x180004610`
- end: `0x18000464c`
- name: `DllCanUnloadNow`
- size: `60`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180004610`
- `0x18000c010`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x18000461b`
- `RPCRT4!NdrDllCanUnloadNow` at `0x18000461b`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  __int64 v0; // rcx

  LODWORD(v0) = NdrDllCanUnloadNow(&gPFactory);
  if ( !(_DWORD)v0 )
    return (*(__int64 (__fastcall **)(__int64 *))(_AtlModule + 24))(&_AtlModule) != 0;
  return v0;
}

```

## disassembly

```asm
0x180004610  sub     rsp, 28h
0x180004614  lea     rcx, gPFactory; pPSFactoryBuffer
0x18000461b  call    cs:__imp_NdrDllCanUnloadNow
0x180004621  mov     ecx, eax
0x180004623  test    eax, eax
0x180004625  jnz     short loc_180004645
0x180004627  mov     rax, cs:?_AtlModule@@3VCSecurityCenterUIModule@@A; CSecurityCenterUIModule _AtlModule
0x18000462e  lea     rcx, ?_AtlModule@@3VCSecurityCenterUIModule@@A; CSecurityCenterUIModule _AtlModule
0x180004635  mov     rax, [rax+18h]
0x180004639  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000463e  xor     ecx, ecx
0x180004640  test    eax, eax
0x180004642  setnz   cl
0x180004645  mov     eax, ecx
0x180004647  add     rsp, 28h
0x18000464b  retn
```
