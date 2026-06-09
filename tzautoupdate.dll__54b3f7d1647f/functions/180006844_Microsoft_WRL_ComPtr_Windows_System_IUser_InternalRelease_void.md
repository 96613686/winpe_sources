# Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)

- ea: `0x180006844`
- end: `0x18000686a`
- name: `?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ`
- size: `38`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `19`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003348`
- `0x180004210`
- `0x18000bf20`
- `0x18001052c`
- `0x180010b54`
- `0x180010d90`
- `0x180011100`
- `0x18001126c`
- `0x1800116bc`
- `0x1800117d0`
- `0x180011b60`
- `0x180011e5c`
- `0x180011ff0`
- `0x1800140a0`
- `0x180015abc`
- `0x180015b5c`
- `0x180015f68`
- `0x180016880`
- `0x180016bc0`

## callees

- `0x180006844`
- `0x18001d010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(__int64 *a1)
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
0x180006844  sub     rsp, 28h
0x180006848  mov     rdx, rcx
0x18000684b  xor     eax, eax
0x18000684d  mov     rcx, [rcx]
0x180006850  test    rcx, rcx
0x180006853  jz      short loc_180006865
0x180006855  mov     [rdx], rax
0x180006858  mov     rax, [rcx]
0x18000685b  mov     rax, [rax+10h]
0x18000685f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006864  nop
0x180006865  add     rsp, 28h
0x180006869  retn
```
