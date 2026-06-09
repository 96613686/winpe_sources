# ATL::CComPtrBase<CUICommand>::~CComPtrBase<CUICommand>(void)

- ea: `0x18000d0d0`
- end: `0x18000d0ed`
- name: `??1?$CComPtrBase@VCUICommand@@@ATL@@QEAA@XZ`
- size: `29`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000d0c4`
- `0x18000d60c`
- `0x18000e010`
- `0x18000f770`
- `0x1800105cc`
- `0x180014780`
- `0x18002df94`

## callees

- `0x18000d0d0`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtrBase<CUICommand>::~CComPtrBase<CUICommand>(__int64 *a1)
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
0x18000d0d0  sub     rsp, 28h
0x18000d0d4  mov     rcx, [rcx]
0x18000d0d7  test    rcx, rcx
0x18000d0da  jz      short loc_18000D0E8
0x18000d0dc  mov     rax, [rcx]
0x18000d0df  mov     rax, [rax+10h]
0x18000d0e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d0e8  add     rsp, 28h
0x18000d0ec  retn
```
