# ATL::CComContainedObject<CRecoExt>::QueryInterface(_GUID const &,void * *)

- ea: `0x180007370`
- end: `0x180007389`
- name: `?QueryInterface@?$CComContainedObject@VCRecoExt@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `25`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003320`
- `0x180003330`
- `0x180003340`
- `0x180003350`
- `0x180003360`
- `0x180003370`
- `0x180003380`

## callees

- `0x180010010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CRecoExt>::QueryInterface(__int64 a1)
{
  return (***(__int64 (__fastcall ****)(_QWORD))(a1 + 64))(*(_QWORD *)(a1 + 64));
}

```

## disassembly

```asm
0x180007370  sub     rsp, 28h
0x180007374  mov     rcx, [rcx+40h]
0x180007378  mov     rax, [rcx]
0x18000737b  mov     rax, [rax]
0x18000737e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007383  nop
0x180007384  add     rsp, 28h
0x180007388  retn
```
