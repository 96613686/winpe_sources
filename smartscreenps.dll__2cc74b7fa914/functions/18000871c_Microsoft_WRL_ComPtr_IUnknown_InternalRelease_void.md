# Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)

- ea: `0x18000871c`
- end: `0x180008742`
- name: `?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ`
- size: `38`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `9`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a160`
- `0x18000a298`
- `0x18000a3d0`
- `0x18000a668`
- `0x18000a710`
- `0x18000a854`
- `0x18000a940`
- `0x18000aa00`
- `0x18000ac00`

## callees

- `0x18000871c`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(__int64 *a1)
{
  __int64 result; // rax
  __int64 v3; // rcx

  result = 0;
  v3 = *a1;
  if ( v3 )
  {
    *a1 = 0;
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  return result;
}

```

## disassembly

```asm
0x18000871c  sub     rsp, 28h
0x180008720  mov     rdx, rcx
0x180008723  xor     eax, eax
0x180008725  mov     rcx, [rcx]
0x180008728  test    rcx, rcx
0x18000872b  jz      short loc_18000873D
0x18000872d  mov     [rdx], rax
0x180008730  mov     rax, [rcx]
0x180008733  mov     rax, [rax+10h]
0x180008737  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000873c  nop
0x18000873d  add     rsp, 28h
0x180008741  retn
```
