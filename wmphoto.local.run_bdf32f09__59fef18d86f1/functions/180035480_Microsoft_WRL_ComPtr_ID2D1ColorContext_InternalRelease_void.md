# Microsoft::WRL::ComPtr<ID2D1ColorContext>::InternalRelease(void)

- ea: `0x180035480`
- end: `0x1800354a6`
- name: `?InternalRelease@?$ComPtr@UID2D1ColorContext@@@WRL@Microsoft@@IEAAKXZ`
- size: `38`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180035434`
- `0x1800386a8`
- `0x18003b6e0`
- `0x18003d050`

## callees

- `0x180035480`
- `0x180044010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<ID2D1ColorContext>::InternalRelease(__int64 *a1)
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
0x180035480  sub     rsp, 28h
0x180035484  mov     rdx, rcx
0x180035487  xor     eax, eax
0x180035489  mov     rcx, [rcx]
0x18003548c  test    rcx, rcx
0x18003548f  jz      short loc_1800354A1
0x180035491  mov     [rdx], rax
0x180035494  mov     rax, [rcx]
0x180035497  mov     rax, [rax+10h]
0x18003549b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800354a0  nop
0x1800354a1  add     rsp, 28h
0x1800354a5  retn
```
