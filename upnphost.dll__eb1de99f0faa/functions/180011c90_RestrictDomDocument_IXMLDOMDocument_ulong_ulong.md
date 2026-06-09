# RestrictDomDocument(IXMLDOMDocument *,ulong,ulong)

- ea: `0x180011c90`
- end: `0x180011e6d`
- name: `?RestrictDomDocument@@YAXPEAUIXMLDOMDocument@@KK@Z`
- size: `477`
- prototype: `void __fastcall(struct IXMLDOMDocument *, unsigned int, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000ee34`
- `0x1800117e8`
- `0x1800119b4`
- `0x18004a130`

## callees

- `0x180011c90`
- `0x180055010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180011d15`
- `OLEAUT32!__imp_SysAllocString` at `0x180011d81`
- `OLEAUT32!__imp_SysAllocString` at `0x180011df5`
- `OLEAUT32!__imp_SysAllocString` at `0x180011d15`
- `OLEAUT32!__imp_SysAllocString` at `0x180011d81`
- `OLEAUT32!__imp_SysAllocString` at `0x180011df5`
- `OLEAUT32!__imp_SysFreeString` at `0x180011d5a`
- `OLEAUT32!__imp_SysFreeString` at `0x180011dc6`
- `OLEAUT32!__imp_SysFreeString` at `0x180011e42`
- `OLEAUT32!__imp_SysFreeString` at `0x180011d5a`
- `OLEAUT32!__imp_SysFreeString` at `0x180011dc6`
- `OLEAUT32!__imp_SysFreeString` at `0x180011e42`
- `OLEAUT32!__imp_SysStringLen` at `0x180011d21`
- `OLEAUT32!__imp_SysStringLen` at `0x180011d8d`
- `OLEAUT32!__imp_SysStringLen` at `0x180011e01`
- `OLEAUT32!__imp_SysStringLen` at `0x180011d21`
- `OLEAUT32!__imp_SysStringLen` at `0x180011d8d`
- `OLEAUT32!__imp_SysStringLen` at `0x180011e01`
- `OLEAUT32!__imp_VariantInit` at `0x180011cf6`
- `OLEAUT32!__imp_VariantInit` at `0x180011cf6`
- `OLEAUT32!__imp_VariantClear` at `0x180011d64`
- `OLEAUT32!__imp_VariantClear` at `0x180011dd8`
- `OLEAUT32!__imp_VariantClear` at `0x180011d64`
- `OLEAUT32!__imp_VariantClear` at `0x180011dd8`

## string_xrefs

- `0x180011de2`: `MaxXMLSize`

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
0x180011c90  mov     [rsp-18h+arg_8], edx
0x180011c94  push    rbp
0x180011c95  push    rbx
0x180011c96  push    rdi
0x180011c97  mov     rbp, rsp
0x180011c9a  sub     rsp, 60h
0x180011c9e  mov     rax, [rcx]
0x180011ca1  mov     edi, edx
0x180011ca3  xor     edx, edx
0x180011ca5  mov     rbx, rcx
0x180011ca8  mov     rax, [rax+230h]
0x180011caf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011cb4  mov     rax, [rbx]
0x180011cb7  lea     r8, [rbp+arg_0]
0x180011cbb  lea     rdx, IID_IXMLDOMDocument2
0x180011cc2  mov     [rbp+arg_0], 0
0x180011cca  mov     rcx, rbx
0x180011ccd  mov     rax, [rax]
0x180011cd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011cd5  test    eax, eax
0x180011cd7  js      loc_180011E58
0x180011cdd  xorps   xmm0, xmm0
0x180011ce0  mov     [rsp+60h+arg_10], rsi
0x180011ce8  xor     eax, eax
0x180011cea  lea     rcx, [rbp+pvarg]; pvarg
0x180011cee  movups  xmmword ptr [rbp+pvarg], xmm0
0x180011cf2  mov     qword ptr [rbp+pvarg+10h], rax
0x180011cf6  call    cs:__imp_VariantInit
0x180011cfc  mov     eax, 0Bh
0x180011d01  lea     rcx, aProhibitdtd; "ProhibitDTD"
0x180011d08  mov     word ptr [rbp+pvarg], ax
0x180011d0c  mov     eax, 1
0x180011d11  mov     word ptr [rbp+pvarg+8], ax
0x180011d15  call    cs:__imp_SysAllocString
0x180011d1b  mov     rcx, rax; pbstr
0x180011d1e  mov     rbx, rax
0x180011d21  call    cs:__imp_SysStringLen
0x180011d27  test    eax, eax
0x180011d29  jz      short loc_180011D60
0x180011d2b  mov     rcx, [rbp+arg_0]
0x180011d2f  lea     r8, [rbp+var_20]
0x180011d33  movups  xmm0, xmmword ptr [rbp+pvarg]
0x180011d37  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x180011d3c  mov     rdx, [rcx]
0x180011d3f  movaps  [rbp+var_20], xmm0
0x180011d43  movsd   [rbp+var_10], xmm1
0x180011d48  mov     rax, [rdx+280h]
0x180011d4f  mov     rdx, rbx
0x180011d52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d57  mov     rcx, rbx; bstrString
0x180011d5a  call    cs:__imp_SysFreeString
0x180011d60  lea     rcx, [rbp+pvarg]; pvarg
0x180011d64  call    cs:__imp_VariantClear
0x180011d6a  mov     esi, 16h
0x180011d6f  mov     dword ptr [rbp+pvarg+8], 32h ; '2'
0x180011d76  lea     rcx, aMaxelementdept; "MaxElementDepth"
0x180011d7d  mov     word ptr [rbp+pvarg], si
0x180011d81  call    cs:__imp_SysAllocString
0x180011d87  mov     rcx, rax; pbstr
0x180011d8a  mov     rbx, rax
0x180011d8d  call    cs:__imp_SysStringLen
0x180011d93  test    eax, eax
0x180011d95  jz      short loc_180011DCC
0x180011d97  mov     rcx, [rbp+arg_0]
0x180011d9b  lea     r8, [rbp+var_20]
0x180011d9f  movups  xmm0, xmmword ptr [rbp+pvarg]
0x180011da3  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x180011da8  mov     rdx, [rcx]
0x180011dab  movaps  [rbp+var_20], xmm0
0x180011daf  movsd   [rbp+var_10], xmm1
0x180011db4  mov     rax, [rdx+280h]
0x180011dbb  mov     rdx, rbx
0x180011dbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011dc3  mov     rcx, rbx; bstrString
0x180011dc6  call    cs:__imp_SysFreeString
0x180011dcc  test    edi, edi
0x180011dce  jz      loc_180011E60
0x180011dd4  lea     rcx, [rbp+pvarg]; pvarg
0x180011dd8  call    cs:__imp_VariantClear
0x180011dde  movzx   eax, word ptr [rbp+arg_8+2]
0x180011de2  lea     rcx, aMaxxmlsize; "MaxXMLSize"
0x180011de9  mov     word ptr [rbp+pvarg+0Ah], ax
0x180011ded  mov     word ptr [rbp+pvarg], si
0x180011df1  mov     word ptr [rbp+pvarg+8], di
0x180011df5  call    cs:__imp_SysAllocString
0x180011dfb  mov     rcx, rax; pbstr
0x180011dfe  mov     rbx, rax
0x180011e01  call    cs:__imp_SysStringLen
0x180011e07  mov     rsi, [rsp+60h+arg_10]
0x180011e0f  test    eax, eax
0x180011e11  jz      short loc_180011E48
0x180011e13  mov     rcx, [rbp+arg_0]
0x180011e17  lea     r8, [rbp+var_20]
0x180011e1b  movups  xmm0, xmmword ptr [rbp+pvarg]
0x180011e1f  mov     rdx, rbx
0x180011e22  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x180011e27  mov     rax, [rcx]
0x180011e2a  movaps  [rbp+var_20], xmm0
0x180011e2e  movsd   [rbp+var_10], xmm1
0x180011e33  mov     rax, [rax+280h]
0x180011e3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e3f  mov     rcx, rbx; bstrString
0x180011e42  call    cs:__imp_SysFreeString
0x180011e48  mov     rcx, [rbp+arg_0]
0x180011e4c  mov     rax, [rcx]
0x180011e4f  mov     rax, [rax+10h]
0x180011e53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e58  add     rsp, 60h
0x180011e5c  pop     rdi
0x180011e5d  pop     rbx
0x180011e5e  pop     rbp
0x180011e5f  retn
0x180011e60  mov     edi, 19000h
0x180011e65  mov     [rbp+arg_8], edi
0x180011e68  jmp     loc_180011DD4
```
