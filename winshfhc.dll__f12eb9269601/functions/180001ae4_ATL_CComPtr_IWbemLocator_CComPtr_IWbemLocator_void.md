# ATL::CComPtr<IWbemLocator>::~CComPtr<IWbemLocator>(void)

- ea: `0x180001ae4`
- end: `0x180001b03`
- name: `??1?$CComPtr@UIWbemLocator@@@ATL@@QEAA@XZ`
- size: `31`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003126`
- `0x180003138`

## callees

- `0x180001ae4`
- `0x180004010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComPtr<IWbemLocator>::~CComPtr<IWbemLocator>(__int64 *a1)
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
0x180001ae4  sub     rsp, 28h
0x180001ae8  mov     rcx, [rcx]
0x180001aeb  test    rcx, rcx
0x180001aee  jz      short loc_180001AFD
0x180001af0  mov     rax, [rcx]
0x180001af3  mov     rax, [rax+10h]
0x180001af7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001afc  nop
0x180001afd  add     rsp, 28h
0x180001b01  retn
```
