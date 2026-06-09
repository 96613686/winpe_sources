# CComBase::NDRelease(void)

- ea: `0x1800146b0`
- end: `0x1800146e1`
- name: `?NDRelease@CComBase@@UEAAKXZ`
- size: `49`
- prototype: `unsigned int __fastcall(CComBase *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800146b0`
- `0x180016010`

## pseudocode

```c
__int64 __fastcall CComBase::NDRelease(CComBase *this)
{
  __int64 result; // rax

  result = (unsigned int)_InterlockedDecrement((volatile signed __int32 *)this + 4);
  if ( !(_DWORD)result )
  {
    ++*((_DWORD *)this + 4);
    (*(void (__fastcall **)(CComBase *))(*(_QWORD *)this + 24LL))(this);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800146b0  sub     rsp, 28h
0x1800146b4  or      eax, 0FFFFFFFFh
0x1800146b7  lock xadd [rcx+10h], eax
0x1800146bc  sub     eax, 1
0x1800146bf  jnz     short loc_1800146DC
0x1800146c1  mov     eax, [rcx+10h]
0x1800146c4  mov     edx, 1
0x1800146c9  add     eax, edx
0x1800146cb  mov     [rcx+10h], eax
0x1800146ce  mov     rax, [rcx]
0x1800146d1  mov     rax, [rax+18h]
0x1800146d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800146da  xor     eax, eax
0x1800146dc  add     rsp, 28h
0x1800146e0  retn
```
