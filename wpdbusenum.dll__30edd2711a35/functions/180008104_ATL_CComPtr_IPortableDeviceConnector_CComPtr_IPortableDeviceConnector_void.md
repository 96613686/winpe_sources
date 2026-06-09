# ATL::CComPtr<IPortableDeviceConnector>::~CComPtr<IPortableDeviceConnector>(void)

- ea: `0x180008104`
- end: `0x180008122`
- name: `??1?$CComPtr@UIPortableDeviceConnector@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180015650`
- `0x180015670`
- `0x180015849`
- `0x18001585b`

## callees

- `0x180008104`
- `0x180016010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtr<IPortableDeviceConnector>::~CComPtr<IPortableDeviceConnector>(__int64 *a1)
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
0x180008104  sub     rsp, 28h
0x180008108  mov     rcx, [rcx]
0x18000810b  test    rcx, rcx
0x18000810e  jz      short loc_18000811D
0x180008110  mov     rax, [rcx]
0x180008113  mov     rax, [rax+10h]
0x180008117  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000811c  nop
0x18000811d  add     rsp, 28h
0x180008121  retn
```
