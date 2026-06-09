# ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)

- ea: `0x180024cac`
- end: `0x180024cca`
- name: `??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `74`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180024ca0`
- `0x1800255e0`
- `0x18002637c`
- `0x1800266c0`
- `0x1800279f8`
- `0x180027ef8`
- `0x18002974c`
- `0x18002d18c`
- `0x18002d420`
- `0x18002d770`
- `0x18002da80`
- `0x18002e770`
- `0x18002e970`
- `0x18002eac0`
- `0x18002ee80`
- `0x18002f1f4`
- `0x18002f458`
- `0x18002fe74`
- `0x18002fed0`
- `0x180030134`
- `0x180030328`
- `0x1800303c0`
- `0x1800308e8`
- `0x180030b00`
- `0x180030e10`
- `0x180030f40`
- `0x180031140`
- `0x180031200`
- `0x180031570`
- `0x1800317ec`
- `0x180031a60`
- `0x180032104`
- `0x18003233c`
- `0x1800325c0`
- `0x18003277c`
- `0x180033010`
- `0x1800336d0`
- `0x180033ea0`
- `0x180034444`
- `0x180034f44`
- `0x180035214`
- `0x180035480`
- `0x1800357c0`
- `0x1800360c0`
- `0x180036a80`
- `0x180036eec`
- `0x180037080`
- `0x180037180`
- `0x180037d78`
- `0x180037e30`

## callees

- `0x180024cac`
- `0x180058010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(__int64 *a1)
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
0x180024cac  sub     rsp, 28h
0x180024cb0  mov     rcx, [rcx]
0x180024cb3  test    rcx, rcx
0x180024cb6  jz      short loc_180024CC5
0x180024cb8  mov     rax, [rcx]
0x180024cbb  mov     rax, [rax+10h]
0x180024cbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024cc4  nop
0x180024cc5  add     rsp, 28h
0x180024cc9  retn
```
