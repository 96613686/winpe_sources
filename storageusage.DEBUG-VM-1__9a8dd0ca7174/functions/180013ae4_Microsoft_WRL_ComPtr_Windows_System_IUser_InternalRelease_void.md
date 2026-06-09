# Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)

- ea: `0x180013ae4`
- end: `0x180013b0a`
- name: `?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ`
- size: `38`
- prototype: ``
- caller_count: `15`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000dd98`
- `0x18000e840`
- `0x18000fc14`
- `0x1800100c0`
- `0x1800105e4`
- `0x180010b60`
- `0x1800113b0`
- `0x1800116b4`
- `0x180012340`
- `0x1800130b0`
- `0x1800180a0`
- `0x1800191dc`
- `0x180019674`
- `0x180019edc`
- `0x18001d1b0`

## callees

- `0x180013ae4`
- `0x18002c010`

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
0x180013ae4  sub     rsp, 28h
0x180013ae8  mov     rdx, rcx
0x180013aeb  xor     eax, eax
0x180013aed  mov     rcx, [rcx]
0x180013af0  test    rcx, rcx
0x180013af3  jz      short loc_180013B05
0x180013af5  mov     [rdx], rax
0x180013af8  mov     rax, [rcx]
0x180013afb  mov     rax, [rax+10h]
0x180013aff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b04  nop
0x180013b05  add     rsp, 28h
0x180013b09  retn
```
