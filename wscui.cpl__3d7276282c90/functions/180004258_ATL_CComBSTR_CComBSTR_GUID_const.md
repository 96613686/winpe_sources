# ATL::CComBSTR::CComBSTR(_GUID const &)

- ea: `0x180004258`
- end: `0x1800042c7`
- name: `??0CComBSTR@ATL@@QEAA@AEBU_GUID@@@Z`
- size: `111`
- prototype: `_QWORD(ATL::CComBSTR *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180004660`

## callees

- `0x180004258`
- `0x1800044f8`
- `0x18000a640`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180004292`
- `OLEAUT32!__imp_SysAllocString` at `0x180004292`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180004287`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180004287`

## pseudocode

```c
ATL::CComBSTR *__fastcall ATL::CComBSTR::CComBSTR(ATL::CComBSTR *this, const struct _GUID *a2)
{
  BSTR v3; // rax
  OLECHAR sz[64]; // [rsp+20h] [rbp-98h] BYREF

  StringFromGUID2(a2, sz, 64);
  v3 = SysAllocString(sz);
  *(_QWORD *)this = v3;
  if ( !v3 )
    ATL::AtlThrowImpl(-2147024882);
  return this;
}

```

## disassembly

```asm
0x180004258  push    rbx
0x18000425a  sub     rsp, 0B0h
0x180004261  mov     rax, cs:__security_cookie
0x180004268  xor     rax, rsp
0x18000426b  mov     [rsp+0B8h+var_18], rax
0x180004273  mov     rax, rdx
0x180004276  mov     rbx, rcx
0x180004279  mov     rcx, rax; rguid
0x18000427c  lea     rdx, [rsp+0B8h+sz]; lpsz
0x180004281  mov     r8d, 40h ; '@'; cchMax
0x180004287  call    cs:__imp_StringFromGUID2
0x18000428d  lea     rcx, [rsp+0B8h+sz]; psz
0x180004292  call    cs:__imp_SysAllocString
0x180004298  mov     [rbx], rax
0x18000429b  test    rax, rax
0x18000429e  jnz     short loc_1800042AB
0x1800042a0  mov     ecx, 8007000Eh; int
0x1800042a5  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800042ab  mov     rax, rbx
0x1800042ae  mov     rcx, [rsp+0B8h+var_18]
0x1800042b6  xor     rcx, rsp; StackCookie
0x1800042b9  call    __security_check_cookie
0x1800042be  add     rsp, 0B0h
0x1800042c5  pop     rbx
0x1800042c6  retn
```
