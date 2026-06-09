# IUnknown_SafeReleaseAndNullPtr<CDeviceSettings>(CDeviceSettings * &)

- ea: `0x180003d5c`
- end: `0x180003d83`
- name: `??$IUnknown_SafeReleaseAndNullPtr@VCDeviceSettings@@@@YAXAEAPEAVCDeviceSettings@@@Z`
- size: `39`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180003f94`
- `0x1800040a8`
- `0x18000653c`
- `0x1800069d4`
- `0x1800080cc`
- `0x18000822c`
- `0x1800087c0`
- `0x18000a058`
- `0x18000d9e4`
- `0x18000f430`

## callees

- `0x180003d5c`
- `0x18001e010`

## pseudocode

```c
_QWORD *__fastcall IUnknown_SafeReleaseAndNullPtr<CDeviceSettings>(_QWORD *a1)
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
0x180003d5c  sub     rsp, 28h
0x180003d60  mov     rax, rcx
0x180003d63  mov     rcx, [rcx]
0x180003d66  test    rcx, rcx
0x180003d69  jz      short loc_180003D7E
0x180003d6b  mov     qword ptr [rax], 0
0x180003d72  mov     rax, [rcx]
0x180003d75  mov     rax, [rax+10h]
0x180003d79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d7e  add     rsp, 28h
0x180003d82  retn
```
