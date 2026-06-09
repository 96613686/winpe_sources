# CASFLonghandObject::Release(void)

- ea: `0x18001fbac`
- end: `0x18001fbdb`
- name: `?Release@CASFLonghandObject@@QEAAKXZ`
- size: `47`
- prototype: `unsigned int __fastcall(CASFLonghandObject *__hidden this)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x180004ed0`
- `0x1800087a0`
- `0x180008cc0`
- `0x180009d80`
- `0x18000b780`
- `0x18000bddc`
- `0x18000c2a0`
- `0x180011dc4`
- `0x18001326c`
- `0x18001383c`

## callees

- `0x18001fbac`
- `0x18002b010`

## pseudocode

```c
__int64 __fastcall CASFLonghandObject::Release(CASFLonghandObject *this)
{
  __int64 result; // rax

  result = (unsigned int)_InterlockedDecrement((volatile signed __int32 *)this + 12);
  if ( !(_DWORD)result )
  {
    if ( *((_QWORD *)this + 5) )
      (**(void (__fastcall ***)(CASFLonghandObject *, __int64))this)(this, 1);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001fbac  sub     rsp, 28h
0x18001fbb0  or      eax, 0FFFFFFFFh
0x18001fbb3  lock xadd [rcx+30h], eax
0x18001fbb8  sub     eax, 1
0x18001fbbb  jnz     short loc_18001FBD6
0x18001fbbd  cmp     qword ptr [rcx+28h], 0
0x18001fbc2  jz      short loc_18001FBD4
0x18001fbc4  mov     rax, [rcx]
0x18001fbc7  mov     edx, 1
0x18001fbcc  mov     rax, [rax]
0x18001fbcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fbd4  xor     eax, eax
0x18001fbd6  add     rsp, 28h
0x18001fbda  retn
```
