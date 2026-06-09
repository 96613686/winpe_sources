# DllCanUnloadNow

- ea: `0x180027bc0`
- end: `0x180027bfb`
- name: `DllCanUnloadNow`
- size: `59`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180025c24`
- `0x180027bc0`
- `0x18002d010`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x180027bea`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  __int64 v0; // rax

  v0 = sub_180025C24();
  if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v0 + 24LL))(v0) )
    return 1;
  else
    return NdrDllCanUnloadNow(&pPSFactoryBuffer);
}

```

## disassembly

```asm
0x180027bc0  sub     rsp, 28h
0x180027bc4  call    sub_180025C24
0x180027bc9  mov     rdx, rax
0x180027bcc  mov     rcx, [rax]
0x180027bcf  mov     rax, [rcx+18h]
0x180027bd3  mov     rcx, rdx
0x180027bd6  call    j__guard_dispatch_icall
0x180027bdb  test    eax, eax
0x180027bdd  jnz     short loc_180027BF1
0x180027bdf  lea     rcx, pPSFactoryBuffer
0x180027be6  add     rsp, 28h
0x180027bea  jmp     cs:NdrDllCanUnloadNow
0x180027bf1  mov     eax, 1
0x180027bf6  add     rsp, 28h
0x180027bfa  retn
```
