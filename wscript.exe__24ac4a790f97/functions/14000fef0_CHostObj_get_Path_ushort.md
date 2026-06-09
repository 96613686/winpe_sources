# CHostObj::get_Path(ushort * *)

- ea: `0x14000fef0`
- end: `0x14000ff27`
- name: `?get_Path@CHostObj@@UEAAJPEAPEAG@Z`
- size: `55`
- prototype: `__int64 __fastcall(CHostObj *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x14000fef0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x14000ff09`
- `OLEAUT32!__imp_SysAllocString` at `0x14000ff09`

## pseudocode

```c
__int64 __fastcall CHostObj::get_Path(const OLECHAR **this, unsigned __int16 **a2)
{
  unsigned __int16 *v4; // rax
  unsigned int v5; // ecx

  if ( !a2 )
    return 2147500035LL;
  v4 = SysAllocString(this[11]);
  v5 = 0;
  *a2 = v4;
  if ( !v4 )
    return (unsigned int)-2147024882;
  return v5;
}

```

## disassembly

```asm
0x14000fef0  push    rbx
0x14000fef2  sub     rsp, 20h
0x14000fef6  mov     rbx, rdx
0x14000fef9  test    rdx, rdx
0x14000fefc  jnz     short loc_14000FF05
0x14000fefe  mov     eax, 80004003h
0x14000ff03  jmp     short loc_14000FF21
0x14000ff05  mov     rcx, [rcx+58h]; psz
0x14000ff09  call    cs:__imp_SysAllocString
0x14000ff0f  xor     ecx, ecx
0x14000ff11  mov     edx, 8007000Eh
0x14000ff16  test    rax, rax
0x14000ff19  mov     [rbx], rax
0x14000ff1c  cmovz   ecx, edx
0x14000ff1f  mov     eax, ecx
0x14000ff21  add     rsp, 20h
0x14000ff25  pop     rbx
0x14000ff26  retn
```
