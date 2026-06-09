# RestrictDomDocument(IXMLDOMDocument *,ulong,ulong)

- ea: `0x180005bc0`
- end: `0x180005de6`
- name: `?RestrictDomDocument@@YAXPEAUIXMLDOMDocument@@KK@Z`
- size: `550`
- prototype: `void __fastcall(struct IXMLDOMDocument *, int)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180005708`
- `0x1800058d4`
- `0x180021444`
- `0x18004d314`

## callees

- `0x180005bc0`
- `0x180059010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180005c4b`
- `OLEAUT32!__imp_SysAllocString` at `0x180005ccf`
- `OLEAUT32!__imp_SysAllocString` at `0x180005d5b`
- `OLEAUT32!__imp_SysAllocString` at `0x180005c4b`
- `OLEAUT32!__imp_SysAllocString` at `0x180005ccf`
- `OLEAUT32!__imp_SysAllocString` at `0x180005d5b`
- `OLEAUT32!__imp_SysFreeString` at `0x180005c9c`
- `OLEAUT32!__imp_SysFreeString` at `0x180005d20`
- `OLEAUT32!__imp_SysFreeString` at `0x180005db4`
- `OLEAUT32!__imp_SysFreeString` at `0x180005c9c`
- `OLEAUT32!__imp_SysFreeString` at `0x180005d20`
- `OLEAUT32!__imp_SysFreeString` at `0x180005db4`
- `OLEAUT32!__imp_SysStringLen` at `0x180005c5d`
- `OLEAUT32!__imp_SysStringLen` at `0x180005ce1`
- `OLEAUT32!__imp_SysStringLen` at `0x180005d6d`
- `OLEAUT32!__imp_SysStringLen` at `0x180005c5d`
- `OLEAUT32!__imp_SysStringLen` at `0x180005ce1`
- `OLEAUT32!__imp_SysStringLen` at `0x180005d6d`
- `OLEAUT32!__imp_VariantInit` at `0x180005c26`
- `OLEAUT32!__imp_VariantInit` at `0x180005c26`
- `OLEAUT32!__imp_VariantClear` at `0x180005cac`
- `OLEAUT32!__imp_VariantClear` at `0x180005d38`
- `OLEAUT32!__imp_VariantClear` at `0x180005cac`
- `OLEAUT32!__imp_VariantClear` at `0x180005d38`

## string_xrefs

- `0x180005d48`: `MaxXMLSize`

## pseudocode

```c
void __fastcall RestrictDomDocument(struct IXMLDOMDocument *a1, int a2)
{
  int v2; // edi
  struct IXMLDOMDocumentVtbl *lpVtbl; // rax
  OLECHAR *v5; // rbx
  __int64 v6; // rdx
  OLECHAR *v7; // rbx
  __int64 v8; // rdx
  OLECHAR *v9; // rbx
  __int64 v10; // rax
  VARIANTARG pvarg; // [rsp+20h] [rbp-40h] BYREF
  VARIANTARG v12; // [rsp+40h] [rbp-20h] BYREF
  __int64 *v13; // [rsp+80h] [rbp+20h] BYREF
  int v14; // [rsp+88h] [rbp+28h]

  v14 = a2;
  v2 = a2;
  ((void (__fastcall *)(struct IXMLDOMDocument *, _QWORD))a1->lpVtbl->put_resolveExternals)(a1, 0);
  lpVtbl = a1->lpVtbl;
  v13 = 0;
  if ( ((__int64 (__fastcall *)(struct IXMLDOMDocument *, GUID *, __int64 **))lpVtbl->QueryInterface)(
         a1,
         &IID_IXMLDOMDocument2,
         &v13) >= 0 )
  {
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    pvarg.vt = 11;
    pvarg.iVal = 1;
    v5 = SysAllocString(L"ProhibitDTD");
    if ( SysStringLen(v5) )
    {
      v6 = *v13;
      v12 = pvarg;
      (*(void (__fastcall **)(__int64 *, OLECHAR *, VARIANTARG *))(v6 + 640))(v13, v5, &v12);
      SysFreeString(v5);
    }
    VariantClear(&pvarg);
    pvarg.lVal = 50;
    pvarg.vt = 22;
    v7 = SysAllocString(L"MaxElementDepth");
    if ( SysStringLen(v7) )
    {
      v8 = *v13;
      v12 = pvarg;
      (*(void (__fastcall **)(__int64 *, OLECHAR *, VARIANTARG *))(v8 + 640))(v13, v7, &v12);
      SysFreeString(v7);
    }
    if ( !v2 )
    {
      LOWORD(v2) = -28672;
      v14 = 102400;
    }
    VariantClear(&pvarg);
    WORD1(pvarg.decVal.Lo64) = HIWORD(v14);
    pvarg.vt = 22;
    pvarg.iVal = v2;
    v9 = SysAllocString(L"MaxXMLSize");
    if ( SysStringLen(v9) )
    {
      v10 = *v13;
      v12 = pvarg;
      (*(void (__fastcall **)(__int64 *, OLECHAR *, VARIANTARG *))(v10 + 640))(v13, v9, &v12);
      SysFreeString(v9);
    }
    (*(void (__fastcall **)(__int64 *))(*v13 + 16))(v13);
  }
}

```

## disassembly

```asm
0x180005bc0  mov     [rsp-18h+arg_8], edx
0x180005bc4  push    rbp
0x180005bc5  push    rbx
0x180005bc6  push    rdi
0x180005bc7  mov     rbp, rsp
0x180005bca  sub     rsp, 60h
0x180005bce  mov     rax, [rcx]
0x180005bd1  mov     edi, edx
0x180005bd3  xor     edx, edx
0x180005bd5  mov     rbx, rcx
0x180005bd8  mov     rax, [rax+230h]
0x180005bdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005be4  mov     rax, [rbx]
0x180005be7  lea     r8, [rbp+arg_0]
0x180005beb  lea     rdx, IID_IXMLDOMDocument2
0x180005bf2  mov     [rbp+arg_0], 0
0x180005bfa  mov     rcx, rbx
0x180005bfd  mov     rax, [rax]
0x180005c00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c05  test    eax, eax
0x180005c07  js      loc_180005DD0
0x180005c0d  xorps   xmm0, xmm0
0x180005c10  mov     [rsp+60h+arg_10], rsi
0x180005c18  xor     eax, eax
0x180005c1a  lea     rcx, [rbp+pvarg]; pvarg
0x180005c1e  movups  xmmword ptr [rbp+pvarg], xmm0
0x180005c22  mov     qword ptr [rbp+pvarg+10h], rax
0x180005c26  call    cs:__imp_VariantInit
0x180005c2d  nop     dword ptr [rax+rax+00h]
0x180005c32  mov     eax, 0Bh
0x180005c37  lea     rcx, aProhibitdtd; "ProhibitDTD"
0x180005c3e  mov     word ptr [rbp+pvarg], ax
0x180005c42  mov     eax, 1
0x180005c47  mov     word ptr [rbp+pvarg+8], ax
0x180005c4b  call    cs:__imp_SysAllocString
0x180005c52  nop     dword ptr [rax+rax+00h]
0x180005c57  mov     rcx, rax; pbstr
0x180005c5a  mov     rbx, rax
0x180005c5d  call    cs:__imp_SysStringLen
0x180005c64  nop     dword ptr [rax+rax+00h]
0x180005c69  test    eax, eax
0x180005c6b  jz      short loc_180005CA8
0x180005c6d  mov     rcx, [rbp+arg_0]
0x180005c71  lea     r8, [rbp+var_20]
0x180005c75  movups  xmm0, xmmword ptr [rbp+pvarg]
0x180005c79  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x180005c7e  mov     rdx, [rcx]
0x180005c81  movaps  [rbp+var_20], xmm0
0x180005c85  movsd   [rbp+var_10], xmm1
0x180005c8a  mov     rax, [rdx+280h]
0x180005c91  mov     rdx, rbx
0x180005c94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c99  mov     rcx, rbx; bstrString
0x180005c9c  call    cs:__imp_SysFreeString
0x180005ca3  nop     dword ptr [rax+rax+00h]
0x180005ca8  lea     rcx, [rbp+pvarg]; pvarg
0x180005cac  call    cs:__imp_VariantClear
0x180005cb3  nop     dword ptr [rax+rax+00h]
0x180005cb8  mov     esi, 16h
0x180005cbd  mov     dword ptr [rbp+pvarg+8], 32h ; '2'
0x180005cc4  lea     rcx, aMaxelementdept; "MaxElementDepth"
0x180005ccb  mov     word ptr [rbp+pvarg], si
0x180005ccf  call    cs:__imp_SysAllocString
0x180005cd6  nop     dword ptr [rax+rax+00h]
0x180005cdb  mov     rcx, rax; pbstr
0x180005cde  mov     rbx, rax
0x180005ce1  call    cs:__imp_SysStringLen
0x180005ce8  nop     dword ptr [rax+rax+00h]
0x180005ced  test    eax, eax
0x180005cef  jz      short loc_180005D2C
0x180005cf1  mov     rcx, [rbp+arg_0]
0x180005cf5  lea     r8, [rbp+var_20]
0x180005cf9  movups  xmm0, xmmword ptr [rbp+pvarg]
0x180005cfd  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x180005d02  mov     rdx, [rcx]
0x180005d05  movaps  [rbp+var_20], xmm0
0x180005d09  movsd   [rbp+var_10], xmm1
0x180005d0e  mov     rax, [rdx+280h]
0x180005d15  mov     rdx, rbx
0x180005d18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d1d  mov     rcx, rbx; bstrString
0x180005d20  call    cs:__imp_SysFreeString
0x180005d27  nop     dword ptr [rax+rax+00h]
0x180005d2c  test    edi, edi
0x180005d2e  jz      loc_180005DD9
0x180005d34  lea     rcx, [rbp+pvarg]; pvarg
0x180005d38  call    cs:__imp_VariantClear
0x180005d3f  nop     dword ptr [rax+rax+00h]
0x180005d44  movzx   eax, word ptr [rbp+arg_8+2]
0x180005d48  lea     rcx, aMaxxmlsize; "MaxXMLSize"
0x180005d4f  mov     word ptr [rbp+pvarg+0Ah], ax
0x180005d53  mov     word ptr [rbp+pvarg], si
0x180005d57  mov     word ptr [rbp+pvarg+8], di
0x180005d5b  call    cs:__imp_SysAllocString
0x180005d62  nop     dword ptr [rax+rax+00h]
0x180005d67  mov     rcx, rax; pbstr
0x180005d6a  mov     rbx, rax
0x180005d6d  call    cs:__imp_SysStringLen
0x180005d74  nop     dword ptr [rax+rax+00h]
0x180005d79  mov     rsi, [rsp+60h+arg_10]
0x180005d81  test    eax, eax
0x180005d83  jz      short loc_180005DC0
0x180005d85  mov     rcx, [rbp+arg_0]
0x180005d89  lea     r8, [rbp+var_20]
0x180005d8d  movups  xmm0, xmmword ptr [rbp+pvarg]
0x180005d91  mov     rdx, rbx
0x180005d94  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x180005d99  mov     rax, [rcx]
0x180005d9c  movaps  [rbp+var_20], xmm0
0x180005da0  movsd   [rbp+var_10], xmm1
0x180005da5  mov     rax, [rax+280h]
0x180005dac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005db1  mov     rcx, rbx; bstrString
0x180005db4  call    cs:__imp_SysFreeString
0x180005dbb  nop     dword ptr [rax+rax+00h]
0x180005dc0  mov     rcx, [rbp+arg_0]
0x180005dc4  mov     rax, [rcx]
0x180005dc7  mov     rax, [rax+10h]
0x180005dcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005dd0  add     rsp, 60h
0x180005dd4  pop     rdi
0x180005dd5  pop     rbx
0x180005dd6  pop     rbp
0x180005dd7  retn
0x180005dd9  mov     edi, 19000h
0x180005dde  mov     [rbp+arg_8], edi
0x180005de1  jmp     loc_180005D34
```
