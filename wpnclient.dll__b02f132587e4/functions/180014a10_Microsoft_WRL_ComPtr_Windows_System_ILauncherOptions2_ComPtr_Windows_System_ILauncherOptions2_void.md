# Microsoft::WRL::ComPtr<Windows::System::ILauncherOptions2>::~ComPtr<Windows::System::ILauncherOptions2>(void)

- ea: `0x180014a10`
- end: `0x180014a38`
- name: `??1?$ComPtr@UILauncherOptions2@System@Windows@@@WRL@Microsoft@@QEAA@XZ`
- size: `40`
- prototype: ``
- caller_count: `23`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180030850`
- `0x180030870`
- `0x180030890`
- `0x1800308b0`
- `0x1800308d0`
- `0x180030930`
- `0x180030970`
- `0x180030990`
- `0x1800309b0`
- `0x1800309d0`
- `0x1800309f0`
- `0x180030a10`
- `0x180030b60`
- `0x180030bc0`
- `0x180030c60`
- `0x180030dc0`
- `0x180030e20`
- `0x180030e80`
- `0x180030ea0`
- `0x180030eee`
- `0x180030f24`
- `0x180030f50`
- `0x18003171e`

## callees

- `0x180014a10`
- `0x180032010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Microsoft::WRL::ComPtr<Windows::System::ILauncherOptions2>::~ComPtr<Windows::System::ILauncherOptions2>(
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
0x180014a10  sub     rsp, 28h
0x180014a14  mov     rax, rcx
0x180014a17  mov     rcx, [rcx]
0x180014a1a  test    rcx, rcx
0x180014a1d  jz      short loc_180014A33
0x180014a1f  mov     qword ptr [rax], 0
0x180014a26  mov     rax, [rcx]
0x180014a29  mov     rax, [rax+10h]
0x180014a2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a32  nop
0x180014a33  add     rsp, 28h
0x180014a37  retn
```
