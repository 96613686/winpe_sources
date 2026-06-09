# Microsoft::WRL::ComPtr<com::application_reputation_static>::~ComPtr<com::application_reputation_static>(void)

- ea: `0x18000a860`
- end: `0x18000a888`
- name: `??1?$ComPtr@Vapplication_reputation_static@com@@@WRL@Microsoft@@QEAA@XZ`
- size: `40`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000ce90`
- `0x18000cf81`
- `0x18000cfd1`

## callees

- `0x18000a860`
- `0x18000e010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Microsoft::WRL::ComPtr<com::application_reputation_static>::~ComPtr<com::application_reputation_static>(
        _QWORD *a1)
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
0x18000a860  sub     rsp, 28h
0x18000a864  mov     rax, rcx
0x18000a867  mov     rcx, [rcx]
0x18000a86a  test    rcx, rcx
0x18000a86d  jz      short loc_18000A883
0x18000a86f  mov     qword ptr [rax], 0
0x18000a876  mov     rax, [rcx]
0x18000a879  mov     rax, [rax+10h]
0x18000a87d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a882  nop
0x18000a883  add     rsp, 28h
0x18000a887  retn
```
