# ATL::CComBSTR::CComBSTR(int)

- ea: `0x180004eec`
- end: `0x180004f1f`
- name: `??0CComBSTR@ATL@@QEAA@H@Z`
- size: `51`
- prototype: `ATL::CComBSTR *__fastcall(ATL::CComBSTR *this, UINT)`
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003b3c`
- `0x180003de8`
- `0x18000518c`
- `0x180018d00`
- `0x180019168`
- `0x18001abac`
- `0x18001af08`

## callees

- `0x180004eec`
- `0x18001ad3c`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x180004f0b`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180004f0b`

## pseudocode

```c
ATL::CComBSTR *__fastcall ATL::CComBSTR::CComBSTR(ATL::CComBSTR *this, UINT a2)
{
  BSTR v4; // rax
  int v5; // ecx

  if ( a2 )
  {
    v4 = SysAllocStringLen(0, a2);
    *(_QWORD *)this = v4;
    if ( !v4 )
      ATL::PrivateAtlThrow(v5);
  }
  else
  {
    *(_QWORD *)this = 0;
  }
  return this;
}

```

## disassembly

```asm
0x180004eec  push    rbx
0x180004eee  sub     rsp, 20h
0x180004ef2  mov     rbx, rcx
0x180004ef5  test    edx, edx
0x180004ef7  jnz     short loc_180004F09
0x180004ef9  mov     qword ptr [rcx], 0
0x180004f00  mov     rax, rbx
0x180004f03  add     rsp, 20h
0x180004f07  pop     rbx
0x180004f08  retn
0x180004f09  xor     ecx, ecx; strIn
0x180004f0b  call    cs:__imp_SysAllocStringLen
0x180004f11  mov     [rbx], rax
0x180004f14  test    rax, rax
0x180004f17  jnz     short loc_180004F00
0x180004f19  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
```
