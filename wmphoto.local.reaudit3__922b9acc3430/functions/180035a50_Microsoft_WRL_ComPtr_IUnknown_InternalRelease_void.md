# Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)

- ea: `0x180035a50`
- end: `0x180035a77`
- name: `?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ`
- size: `39`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180035a04`
- `0x180038d0c`
- `0x18003bf08`
- `0x18003bfd0`
- `0x18003d7c0`

## callees

- `0x180035a50`
- `0x180045010`

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
0x180035a50  sub     rsp, 28h
0x180035a54  mov     rdx, rcx
0x180035a57  xor     eax, eax
0x180035a59  mov     rcx, [rcx]
0x180035a5c  test    rcx, rcx
0x180035a5f  jz      short loc_180035A71
0x180035a61  mov     [rdx], rax
0x180035a64  mov     rax, [rcx]
0x180035a67  mov     rax, [rax+10h]
0x180035a6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035a70  nop
0x180035a71  add     rsp, 28h
0x180035a75  retn
```
