# ATL::CComPtrBase<ISpPhraseBuilder>::~CComPtrBase<ISpPhraseBuilder>(void)

- ea: `0x180003774`
- end: `0x180003792`
- name: `??1?$CComPtrBase@UISpPhraseBuilder@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003768`
- `0x180003d50`
- `0x18000500c`
- `0x1800052f4`
- `0x180006598`

## callees

- `0x180003774`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtrBase<ISpPhraseBuilder>::~CComPtrBase<ISpPhraseBuilder>(__int64 *a1)
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
0x180003774  sub     rsp, 28h
0x180003778  mov     rcx, [rcx]
0x18000377b  test    rcx, rcx
0x18000377e  jz      short loc_18000378D
0x180003780  mov     rax, [rcx]
0x180003783  mov     rax, [rax+10h]
0x180003787  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000378c  nop
0x18000378d  add     rsp, 28h
0x180003791  retn
```
