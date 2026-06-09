# DllCanUnloadNow

- ea: `0x180016770`
- end: `0x1800167ab`
- name: `DllCanUnloadNow`
- size: `59`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1800143bc`
- `0x180016770`
- `0x18001c010`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x18001679a`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  __int64 v0; // rax

  v0 = sub_1800143BC();
  if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v0 + 24LL))(v0) )
    return 1;
  else
    return NdrDllCanUnloadNow(&pPSFactoryBuffer);
}

```

## disassembly

```asm
0x180016770  sub     rsp, 28h
0x180016774  call    sub_1800143BC
0x180016779  mov     rdx, rax
0x18001677c  mov     rcx, [rax]
0x18001677f  mov     rax, [rcx+18h]
0x180016783  mov     rcx, rdx
0x180016786  call    j__guard_dispatch_icall
0x18001678b  test    eax, eax
0x18001678d  jnz     short loc_1800167A1
0x18001678f  lea     rcx, pPSFactoryBuffer
0x180016796  add     rsp, 28h
0x18001679a  jmp     cs:NdrDllCanUnloadNow
0x1800167a1  mov     eax, 1
0x1800167a6  add     rsp, 28h
0x1800167aa  retn
```
