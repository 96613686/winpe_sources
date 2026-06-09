# BASE_CONNECTION::ProcessRead(ulong,uchar * *,uint *)

- ea: `0x180010e90`
- end: `0x180010eac`
- name: `?ProcessRead@BASE_CONNECTION@@UEAAJKPEAPEAEPEAI@Z`
- size: `28`
- prototype: `__int64 __fastcall(BASE_CONNECTION *__hidden this, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180025010`

## pseudocode

```c
__int64 __fastcall BASE_CONNECTION::ProcessRead(
        BASE_CONNECTION *this,
        __int64 a2,
        unsigned __int8 **a3,
        unsigned int *a4)
{
  return (*((__int64 (__fastcall **)(BASE_CONNECTION *, __int64, unsigned __int8 **, unsigned int *))pRuntimeImportTable
          + 56))(
           this,
           a2,
           a3,
           a4);
}

```

## disassembly

```asm
0x180010e90  sub     rsp, 38h
0x180010e94  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x180010e9b  mov     rax, [rax+1C0h]
0x180010ea2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ea7  add     rsp, 38h
0x180010eab  retn
```
