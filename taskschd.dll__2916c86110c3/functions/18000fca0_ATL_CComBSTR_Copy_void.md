# ATL::CComBSTR::Copy(void)

- ea: `0x18000fca0`
- end: `0x18000fccc`
- name: `?Copy@CComBSTR@ATL@@QEBAPEAGXZ`
- size: `44`
- prototype: `unsigned __int16 *__fastcall(ATL::CComBSTR *__hidden this)`
- caller_count: `61`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800011f8`
- `0x180001e60`
- `0x180004570`
- `0x180005e20`
- `0x18000df30`
- `0x18000e030`
- `0x18000e0e0`
- `0x18000e190`
- `0x18000e250`
- `0x18000e310`
- `0x18000e4d0`
- `0x18000f6f4`
- `0x18000f9e0`
- `0x18000faa0`
- `0x18000fba0`
- `0x18000fce0`
- `0x18000fd90`
- `0x18000ff40`
- `0x180010000`
- `0x1800100c0`
- `0x180010170`
- `0x180010300`
- `0x1800103c0`
- `0x180010490`
- `0x180010544`
- `0x180010600`
- `0x1800106c0`
- `0x180010770`
- `0x180010830`
- `0x1800108e0`
- `0x180010990`
- `0x180010a98`
- `0x180010b50`
- `0x180010cc0`
- `0x180010dfc`
- `0x180010eb0`
- `0x180011018`
- `0x1800110d0`
- `0x1800111a0`
- `0x1800112a8`
- `0x180013570`
- `0x180013620`
- `0x1800348c0`
- `0x180034ce0`
- `0x180035150`
- `0x180035ed0`
- `0x180036560`
- `0x18003eef0`
- `0x18003ef94`
- `0x18003f030`

## callees

- `0x18000fca0`

## import_xrefs

- `OLEAUT32!__imp_SysStringByteLen` at `0x18000fcb9`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18000fcb9`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18000fcc4`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18000fcc4`

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
0x18000fca0  push    rbx
0x18000fca2  sub     rsp, 20h
0x18000fca6  mov     rbx, rcx
0x18000fca9  mov     rcx, [rcx]; bstr
0x18000fcac  test    rcx, rcx
0x18000fcaf  jnz     short loc_18000FCB9
0x18000fcb1  xor     eax, eax
0x18000fcb3  add     rsp, 20h
0x18000fcb7  pop     rbx
0x18000fcb8  retn
0x18000fcb9  call    cs:__imp_SysStringByteLen
0x18000fcbf  mov     rcx, [rbx]; psz
0x18000fcc2  mov     edx, eax; len
0x18000fcc4  call    cs:__imp_SysAllocStringByteLen
0x18000fcca  jmp     short loc_18000FCB3
```
