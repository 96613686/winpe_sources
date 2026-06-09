# UI1VectorToVariant(tagPROPVARIANT const *,tagVARIANT *)

- ea: `0x1800462a0`
- end: `0x18004635d`
- name: `?UI1VectorToVariant@@YAJPEBUtagPROPVARIANT@@PEAUtagVARIANT@@@Z`
- size: `189`
- prototype: `__int64 __fastcall(const struct tagPROPVARIANT *, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180014d60`

## callees

- `0x180036f50`
- `0x1800390fd`
- `0x1800462a0`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800462de`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800462de`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18004633a`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18004633a`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180046304`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180046304`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18004632f`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18004632f`

## pseudocode

```c
__int64 __fastcall UI1VectorToVariant(const struct tagPROPVARIANT *a1, struct tagVARIANT *a2)
{
  ULONG ulVal; // eax
  SAFEARRAY *v5; // rax
  SAFEARRAY *v6; // rdi
  HRESULT v7; // ebx
  void *ppvData; // [rsp+20h] [rbp-38h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+28h] [rbp-30h] BYREF

  ulVal = a1->ulVal;
  rgsabound.lLbound = 0;
  rgsabound.cElements = ulVal;
  v5 = SafeArrayCreate(0x11u, 1u, &rgsabound);
  v6 = v5;
  if ( v5 )
  {
    ppvData = 0;
    v7 = SafeArrayAccessData(v5, &ppvData);
    if ( v7 < 0 )
    {
      SafeArrayDestroy(v6);
    }
    else
    {
      memcpy_0(ppvData, a1->bstrblobVal.pData, a1->ulVal);
      a2->vt = 8209;
      a2->llVal = (LONGLONG)v6;
      SafeArrayUnaccessData(v6);
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800462a0  mov     [rsp+arg_10], rbx
0x1800462a5  push    rsi
0x1800462a6  push    rdi
0x1800462a7  push    r14
0x1800462a9  sub     rsp, 40h
0x1800462ad  mov     rax, cs:__security_cookie
0x1800462b4  xor     rax, rsp
0x1800462b7  mov     [rsp+58h+var_28], rax
0x1800462bc  mov     eax, [rcx+8]
0x1800462bf  lea     r8, [rsp+58h+rgsabound]; rgsabound
0x1800462c4  mov     rsi, rcx
0x1800462c7  mov     [rsp+58h+rgsabound.lLbound], 0
0x1800462cf  mov     ecx, 11h; vt
0x1800462d4  mov     [rsp+58h+rgsabound.cElements], eax
0x1800462d8  mov     r14, rdx
0x1800462db  lea     edx, [rcx-10h]; cDims
0x1800462de  call    cs:__imp_SafeArrayCreate
0x1800462e4  mov     rdi, rax
0x1800462e7  test    rax, rax
0x1800462ea  jnz     short loc_1800462F3
0x1800462ec  mov     ebx, 8007000Eh
0x1800462f1  jmp     short loc_180046340
0x1800462f3  lea     rdx, [rsp+58h+ppvData]; ppvData
0x1800462f8  mov     [rsp+58h+ppvData], 0
0x180046301  mov     rcx, rdi; psa
0x180046304  call    cs:__imp_SafeArrayAccessData
0x18004630a  mov     ebx, eax
0x18004630c  test    eax, eax
0x18004630e  js      short loc_180046337
0x180046310  mov     r8d, [rsi+8]; Size
0x180046314  mov     rdx, [rsi+10h]; Src
0x180046318  mov     rcx, [rsp+58h+ppvData]; void *
0x18004631d  call    memcpy_0
0x180046322  mov     rcx, rdi; psa
0x180046325  mov     word ptr [r14], 2011h
0x18004632b  mov     [r14+8], rdi
0x18004632f  call    cs:__imp_SafeArrayUnaccessData
0x180046335  jmp     short loc_180046340
0x180046337  mov     rcx, rdi; psa
0x18004633a  call    cs:__imp_SafeArrayDestroy
0x180046340  mov     eax, ebx
0x180046342  mov     rcx, [rsp+58h+var_28]
0x180046347  xor     rcx, rsp; StackCookie
0x18004634a  call    __security_check_cookie
0x18004634f  mov     rbx, [rsp+58h+arg_10]
0x180046354  add     rsp, 40h
0x180046358  pop     r14
0x18004635a  pop     rdi
0x18004635b  pop     rsi
0x18004635c  retn
```
