# CShareSecurityInformation::Release(void)

- ea: `0x18000be00`
- end: `0x18000be2e`
- name: `?Release@CShareSecurityInformation@@UEAAKXZ`
- size: `46`
- prototype: `__int64 __fastcall(CShareSecurityInformation *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000be00`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall CShareSecurityInformation::Release(CShareSecurityInformation *this)
{
  __int64 result; // rax

  result = (unsigned int)_InterlockedDecrement((volatile signed __int32 *)this + 6);
  if ( !(_DWORD)result )
  {
    if ( this )
      (*(void (__fastcall **)(CShareSecurityInformation *, __int64))(*(_QWORD *)this + 80LL))(this, 1);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000be00  sub     rsp, 28h
0x18000be04  or      eax, 0FFFFFFFFh
0x18000be07  lock xadd [rcx+18h], eax
0x18000be0c  sub     eax, 1
0x18000be0f  jnz     short loc_18000BE29
0x18000be11  test    rcx, rcx
0x18000be14  jz      short loc_18000BE27
0x18000be16  mov     rax, [rcx]
0x18000be19  mov     edx, 1
0x18000be1e  mov     rax, [rax+50h]
0x18000be22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be27  xor     eax, eax
0x18000be29  add     rsp, 28h
0x18000be2d  retn
```
