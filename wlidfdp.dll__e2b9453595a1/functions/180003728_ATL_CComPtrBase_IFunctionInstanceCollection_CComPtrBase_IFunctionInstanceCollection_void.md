# ATL::CComPtrBase<IFunctionInstanceCollection>::~CComPtrBase<IFunctionInstanceCollection>(void)

- ea: `0x180003728`
- end: `0x180003746`
- name: `??1?$CComPtrBase@UIFunctionInstanceCollection@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `9`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003ae0`
- `0x180003e18`
- `0x180003fcc`
- `0x1800054bc`
- `0x18000579c`
- `0x180005d3c`
- `0x180007b00`
- `0x180009eb8`
- `0x18000a3e8`

## callees

- `0x180003728`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtrBase<IFunctionInstanceCollection>::~CComPtrBase<IFunctionInstanceCollection>(
        __int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
  return result;
}

```

## disassembly

```asm
0x180003728  sub     rsp, 28h
0x18000372c  mov     rcx, [rcx]
0x18000372f  test    rcx, rcx
0x180003732  jz      short loc_180003741
0x180003734  mov     rax, [rcx]
0x180003737  mov     rax, [rax+10h]
0x18000373b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003740  nop
0x180003741  add     rsp, 28h
0x180003745  retn
```
