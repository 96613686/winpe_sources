# Microsoft::WRL::ComPtr<IWsPlatform>::~ComPtr<IWsPlatform>(void)

- ea: `0x180004af8`
- end: `0x180004b20`
- name: `??1?$ComPtr@UIWsPlatform@@@WRL@Microsoft@@QEAA@XZ`
- size: `40`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000dcaa`
- `0x18000dcbc`
- `0x18000dce0`
- `0x18000dcf2`

## callees

- `0x180004af8`
- `0x18000f010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Microsoft::WRL::ComPtr<IWsPlatform>::~ComPtr<IWsPlatform>(_QWORD *a1)
{
  _QWORD *result; // rax
  __int64 v2; // rcx

  result = a1;
  v2 = *a1;
  if ( v2 )
  {
    *result = 0;
    return (_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  return result;
}

```

## disassembly

```asm
0x180004af8  sub     rsp, 28h
0x180004afc  mov     rax, rcx
0x180004aff  mov     rcx, [rcx]
0x180004b02  test    rcx, rcx
0x180004b05  jz      short loc_180004B1B
0x180004b07  mov     qword ptr [rax], 0
0x180004b0e  mov     rax, [rcx]
0x180004b11  mov     rax, [rax+10h]
0x180004b15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b1a  nop
0x180004b1b  add     rsp, 28h
0x180004b1f  retn
```
