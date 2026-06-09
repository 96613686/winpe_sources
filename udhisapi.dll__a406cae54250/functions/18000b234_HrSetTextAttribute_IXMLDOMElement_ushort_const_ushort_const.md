# HrSetTextAttribute(IXMLDOMElement *,ushort const *,ushort const *)

- ea: `0x18000b234`
- end: `0x18000b300`
- name: `?HrSetTextAttribute@@YAJPEAUIXMLDOMElement@@PEBG1@Z`
- size: `204`
- prototype: `__int64 __fastcall(struct IXMLDOMElement *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800063e0`

## callees

- `0x18000b234`
- `0x18000c010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000b25c`
- `OLEAUT32!__imp_SysAllocString` at `0x18000b271`
- `OLEAUT32!__imp_SysAllocString` at `0x18000b25c`
- `OLEAUT32!__imp_SysAllocString` at `0x18000b271`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b287`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b2de`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b287`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b2de`
- `OLEAUT32!__imp_VariantInit` at `0x18000b294`
- `OLEAUT32!__imp_VariantInit` at `0x18000b294`

## string_xrefs

- `0x18000b24b`: `http://schemas.xmlsoap.org/soap/encoding/`

## pseudocode

```c
__int64 __fastcall HrSetTextAttribute(
        struct IXMLDOMElement *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  OLECHAR *v4; // rdi
  BSTR v5; // rsi
  unsigned int v6; // ebx
  OLECHAR *v7; // rcx
  struct IXMLDOMElementVtbl *lpVtbl; // rax
  HRESULT (__stdcall *setAttribute)(IXMLDOMElement *, BSTR, VARIANT); // rax
  VARIANTARG pvarg; // [rsp+20h] [rbp-48h] BYREF
  __int128 v12; // [rsp+40h] [rbp-28h] BYREF
  IRecordInfo *pRecInfo; // [rsp+50h] [rbp-18h]

  memset(&pvarg, 0, sizeof(pvarg));
  v4 = SysAllocString(L"http://schemas.xmlsoap.org/soap/encoding/");
  if ( v4 )
  {
    v5 = SysAllocString(L"SOAP-ENV:encodingStyle");
    if ( v5 )
    {
      VariantInit(&pvarg);
      pvarg.llVal = (LONGLONG)v4;
      pvarg.vt = 8;
      lpVtbl = a1->lpVtbl;
      pRecInfo = pvarg.pRecInfo;
      setAttribute = lpVtbl->setAttribute;
      v12 = *(_OWORD *)&pvarg.vt;
      v6 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, BSTR, __int128 *))setAttribute)(a1, v5, &v12);
      SysFreeString(v4);
      v7 = v5;
    }
    else
    {
      v6 = -2147024882;
      v7 = v4;
    }
    SysFreeString(v7);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v6;
}

```

## disassembly

```asm
0x18000b234  mov     [rsp+arg_0], rbx
0x18000b239  mov     [rsp+arg_8], rsi
0x18000b23e  push    rdi
0x18000b23f  sub     rsp, 60h
0x18000b243  mov     rbx, rcx
0x18000b246  xorps   xmm0, xmm0
0x18000b249  xor     eax, eax
0x18000b24b  lea     rcx, aHttpSchemasXml; "http://schemas.xmlsoap.org/soap/encodin"...
0x18000b252  movups  xmmword ptr [rsp+68h+pvarg], xmm0
0x18000b257  mov     qword ptr [rsp+68h+pvarg+10h], rax
0x18000b25c  call    cs:__imp_SysAllocString
0x18000b262  mov     rdi, rax
0x18000b265  test    rax, rax
0x18000b268  jz      short loc_18000B2E9
0x18000b26a  lea     rcx, aSoapEnvEncodin; "SOAP-ENV:encodingStyle"
0x18000b271  call    cs:__imp_SysAllocString
0x18000b277  mov     rsi, rax
0x18000b27a  test    rax, rax
0x18000b27d  jnz     short loc_18000B28F
0x18000b27f  mov     ebx, 8007000Eh
0x18000b284  mov     rcx, rdi; bstrString
0x18000b287  call    cs:__imp_SysFreeString
0x18000b28d  jmp     short loc_18000B2EE
0x18000b28f  lea     rcx, [rsp+68h+pvarg]; pvarg
0x18000b294  call    cs:__imp_VariantInit
0x18000b29a  movsd   xmm1, qword ptr [rsp+68h+pvarg+10h]
0x18000b2a0  lea     r8, [rsp+68h+var_28]
0x18000b2a5  mov     eax, 8
0x18000b2aa  mov     qword ptr [rsp+68h+pvarg+8], rdi
0x18000b2af  mov     word ptr [rsp+68h+pvarg], ax
0x18000b2b4  mov     rdx, rsi
0x18000b2b7  mov     rax, [rbx]
0x18000b2ba  mov     rcx, rbx
0x18000b2bd  movups  xmm0, xmmword ptr [rsp+68h+pvarg]
0x18000b2c2  movsd   [rsp+68h+var_18], xmm1
0x18000b2c8  mov     rax, [rax+168h]
0x18000b2cf  movaps  [rsp+68h+var_28], xmm0
0x18000b2d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2d9  mov     rcx, rdi; bstrString
0x18000b2dc  mov     ebx, eax
0x18000b2de  call    cs:__imp_SysFreeString
0x18000b2e4  mov     rcx, rsi
0x18000b2e7  jmp     short loc_18000B287
0x18000b2e9  mov     ebx, 8007000Eh
0x18000b2ee  mov     rsi, [rsp+68h+arg_8]
0x18000b2f3  mov     eax, ebx
0x18000b2f5  mov     rbx, [rsp+68h+arg_0]
0x18000b2fa  add     rsp, 60h
0x18000b2fe  pop     rdi
0x18000b2ff  retn
```
