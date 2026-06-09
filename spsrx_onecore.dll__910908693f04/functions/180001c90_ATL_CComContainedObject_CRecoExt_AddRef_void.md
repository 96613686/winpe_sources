# ATL::CComContainedObject<CRecoExt>::AddRef(void)

- ea: `0x180001c90`
- end: `0x180001caa`
- name: `?AddRef@?$CComContainedObject@VCRecoExt@@@ATL@@UEAAKXZ`
- size: `26`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003240`
- `0x180003250`
- `0x180003260`
- `0x180003270`
- `0x180003280`
- `0x180003290`
- `0x1800032a0`

## callees

- `0x180010010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CRecoExt>::AddRef(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 64) + 8LL))(*(_QWORD *)(a1 + 64));
}

```

## disassembly

```asm
0x180001c90  sub     rsp, 28h
0x180001c94  mov     rcx, [rcx+40h]
0x180001c98  mov     rax, [rcx]
0x180001c9b  mov     rax, [rax+8]
0x180001c9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ca4  nop
0x180001ca5  add     rsp, 28h
0x180001ca9  retn
```
