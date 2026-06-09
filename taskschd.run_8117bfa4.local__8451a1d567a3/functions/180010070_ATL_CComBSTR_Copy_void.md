# ATL::CComBSTR::Copy(void)

- ea: `0x180010070`
- end: `0x1800100a9`
- name: `?Copy@CComBSTR@ATL@@QEBAPEAGXZ`
- size: `57`
- prototype: `unsigned __int16 *__fastcall(ATL::CComBSTR *__hidden this)`
- caller_count: `61`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180001218`
- `0x180001f1c`
- `0x180004800`
- `0x1800060d0`
- `0x18000e070`
- `0x18000e140`
- `0x18000e210`
- `0x18000e2f0`
- `0x18000e4f0`
- `0x18000fa20`
- `0x18000fd40`
- `0x18000fe10`
- `0x18000ff40`
- `0x1800100b0`
- `0x180010180`
- `0x1800102a0`
- `0x180010370`
- `0x180010570`
- `0x180010640`
- `0x180010720`
- `0x1800107f0`
- `0x1800109c0`
- `0x180010a90`
- `0x180010b70`
- `0x180010c38`
- `0x180010d00`
- `0x180010de0`
- `0x180010eb0`
- `0x180010f90`
- `0x180011054`
- `0x180011130`
- `0x18001126c`
- `0x180011340`
- `0x1800114f0`
- `0x180011600`
- `0x1800116d0`
- `0x18001186c`
- `0x180011980`
- `0x180011a70`
- `0x180011bb4`
- `0x180014428`
- `0x1800144f0`
- `0x180037810`
- `0x180037b60`
- `0x180038080`
- `0x180038e20`
- `0x1800395a0`
- `0x180042480`
- `0x180042528`
- `0x1800425cc`

## callees

- `0x180010070`

## import_xrefs

- `OLEAUT32!__imp_SysStringByteLen` at `0x18001008a`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18001008a`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18001009b`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18001009b`

## pseudocode

```c
BSTR __fastcall ATL::CComBSTR::Copy(LPCSTR *this)
{
  CHAR *v2; // rcx
  UINT v4; // eax

  v2 = (CHAR *)*this;
  if ( !v2 )
    return 0;
  v4 = SysStringByteLen((BSTR)v2);
  return SysAllocStringByteLen(*this, v4);
}

```

## disassembly

```asm
0x180010070  push    rbx
0x180010072  sub     rsp, 20h
0x180010076  mov     rbx, rcx
0x180010079  mov     rcx, [rcx]; bstr
0x18001007c  test    rcx, rcx
0x18001007f  jnz     short loc_18001008A
0x180010081  xor     eax, eax
0x180010083  add     rsp, 20h
0x180010087  pop     rbx
0x180010088  retn
0x18001008a  call    cs:__imp_SysStringByteLen
0x180010091  nop     dword ptr [rax+rax+00h]
0x180010096  mov     rcx, [rbx]; psz
0x180010099  mov     edx, eax; len
0x18001009b  call    cs:__imp_SysAllocStringByteLen
0x1800100a2  nop     dword ptr [rax+rax+00h]
0x1800100a7  jmp     short loc_180010083
```
