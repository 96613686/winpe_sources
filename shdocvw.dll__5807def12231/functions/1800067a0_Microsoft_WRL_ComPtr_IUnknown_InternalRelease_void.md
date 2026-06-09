# Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)

- ea: `0x1800067a0`
- end: `0x1800067cd`
- name: `?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ`
- size: `45`
- prototype: ``
- caller_count: `17`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003660`
- `0x180004d30`
- `0x1800055f0`
- `0x1800144c8`
- `0x180014554`
- `0x180014b8c`
- `0x180014fc0`
- `0x18001566c`
- `0x180015ea0`
- `0x180017084`
- `0x18001794c`
- `0x180018824`
- `0x1800188b0`
- `0x18001d120`
- `0x180020c48`
- `0x180021910`
- `0x180021a50`

## callees

- `0x1800067a0`
- `0x180029010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(__int64 *a1)
{
  __int64 v2; // rcx

  v2 = *a1;
  if ( !v2 )
    return 0;
  *a1 = 0;
  return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
}

```

## disassembly

```asm
0x1800067a0  sub     rsp, 28h
0x1800067a4  mov     rax, rcx
0x1800067a7  xor     edx, edx
0x1800067a9  mov     rcx, [rcx]
0x1800067ac  test    rcx, rcx
0x1800067af  jz      short loc_1800067C6
0x1800067b1  mov     [rax], rdx
0x1800067b4  mov     rax, [rcx]
0x1800067b7  mov     rax, [rax+10h]
0x1800067bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067c0  nop
0x1800067c1  add     rsp, 28h
0x1800067c5  retn
0x1800067c6  mov     eax, edx
0x1800067c8  add     rsp, 28h
0x1800067cc  retn
```
