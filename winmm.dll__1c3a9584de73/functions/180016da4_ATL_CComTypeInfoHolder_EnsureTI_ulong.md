# ATL::CComTypeInfoHolder::EnsureTI(ulong)

- ea: `0x180016da4`
- end: `0x180016dc7`
- name: `?EnsureTI@CComTypeInfoHolder@ATL@@QEAAJK@Z`
- size: `35`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001773c`
- `0x180017e80`

## callees

- `0x180016da4`
- `0x18001795c`

## pseudocode

```c
__int64 __fastcall ATL::CComTypeInfoHolder::EnsureTI(ATL::CComTypeInfoHolder *this, LCID a2)
{
  __int64 result; // rax

  if ( !qword_180025078 )
    return ATL::CComTypeInfoHolder::GetTI(this, a2);
  result = 0;
  if ( !qword_180025088 )
    return ATL::CComTypeInfoHolder::GetTI(this, a2);
  return result;
}

```

## disassembly

```asm
0x180016da4  sub     rsp, 28h
0x180016da8  cmp     cs:qword_180025078, 0
0x180016db0  jz      short loc_180016DBD
0x180016db2  xor     eax, eax
0x180016db4  cmp     cs:qword_180025088, rax
0x180016dbb  jnz     short loc_180016DC2
0x180016dbd  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x180016dc2  add     rsp, 28h
0x180016dc6  retn
```
