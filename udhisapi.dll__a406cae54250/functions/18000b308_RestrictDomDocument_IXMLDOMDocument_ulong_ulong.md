# RestrictDomDocument(IXMLDOMDocument *,ulong,ulong)

- ea: `0x18000b308`
- end: `0x18000b4c0`
- name: `?RestrictDomDocument@@YAXPEAUIXMLDOMDocument@@KK@Z`
- size: `440`
- prototype: `void __fastcall(struct IXMLDOMDocument *, LONG)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180005e60`

## callees

- `0x18000b308`
- `0x18000c010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000b383`
- `OLEAUT32!__imp_SysAllocString` at `0x18000b3ef`
- `OLEAUT32!__imp_SysAllocString` at `0x18000b45c`
- `OLEAUT32!__imp_SysAllocString` at `0x18000b383`
- `OLEAUT32!__imp_SysAllocString` at `0x18000b3ef`
- `OLEAUT32!__imp_SysAllocString` at `0x18000b45c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b3c8`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b434`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b4a1`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b3c8`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b434`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b4a1`
- `OLEAUT32!__imp_SysStringLen` at `0x18000b38f`
- `OLEAUT32!__imp_SysStringLen` at `0x18000b3fb`
- `OLEAUT32!__imp_SysStringLen` at `0x18000b468`
- `OLEAUT32!__imp_SysStringLen` at `0x18000b38f`
- `OLEAUT32!__imp_SysStringLen` at `0x18000b3fb`
- `OLEAUT32!__imp_SysStringLen` at `0x18000b468`
- `OLEAUT32!__imp_VariantInit` at `0x18000b364`
- `OLEAUT32!__imp_VariantInit` at `0x18000b364`
- `OLEAUT32!__imp_VariantClear` at `0x18000b3d2`
- `OLEAUT32!__imp_VariantClear` at `0x18000b43e`
- `OLEAUT32!__imp_VariantClear` at `0x18000b3d2`
- `OLEAUT32!__imp_VariantClear` at `0x18000b43e`

## string_xrefs

- `0x18000b44f`: `MaxXMLSize`

## pseudocode

```c
void __fastcall RestrictDomDocument(struct IXMLDOMDocument *a1, LONG a2)
{
  struct IXMLDOMDocumentVtbl *lpVtbl; // rax
  OLECHAR *v5; // rbx
  __int64 v6; // rdx
  OLECHAR *v7; // rbx
  __int64 v8; // rdx
  LONG v9; // eax
  OLECHAR *v10; // rbx
  __int64 v11; // rdx
  VARIANTARG pvarg; // [rsp+20h] [rbp-48h] BYREF
  VARIANTARG v13; // [rsp+40h] [rbp-28h] BYREF
  __int64 *v14; // [rsp+90h] [rbp+28h] BYREF

  ((void (__fastcall *)(struct IXMLDOMDocument *, _QWORD))a1->lpVtbl->put_resolveExternals)(a1, 0);
  lpVtbl = a1->lpVtbl;
  v14 = 0;
  if ( ((__int64 (__fastcall *)(struct IXMLDOMDocument *, GUID *, __int64 **))lpVtbl->QueryInterface)(
         a1,
         &IID_IXMLDOMDocument2,
         &v14) >= 0 )
  {
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    pvarg.vt = 11;
    pvarg.iVal = 1;
    v5 = SysAllocString(L"ProhibitDTD");
    if ( SysStringLen(v5) )
    {
      v6 = *v14;
      v13 = pvarg;
      (*(void (__fastcall **)(__int64 *, OLECHAR *, VARIANTARG *))(v6 + 640))(v14, v5, &v13);
      SysFreeString(v5);
    }
    VariantClear(&pvarg);
    pvarg.lVal = 50;
    pvarg.vt = 22;
    v7 = SysAllocString(L"MaxElementDepth");
    if ( SysStringLen(v7) )
    {
      v8 = *v14;
      v13 = pvarg;
      (*(void (__fastcall **)(__int64 *, OLECHAR *, VARIANTARG *))(v8 + 640))(v14, v7, &v13);
      SysFreeString(v7);
    }
    VariantClear(&pvarg);
    v9 = 102400;
    pvarg.vt = 22;
    if ( a2 )
      v9 = a2;
    pvarg.lVal = v9;
    v10 = SysAllocString(L"MaxXMLSize");
    if ( SysStringLen(v10) )
    {
      v11 = *v14;
      v13 = pvarg;
      (*(void (__fastcall **)(__int64 *, OLECHAR *, VARIANTARG *))(v11 + 640))(v14, v10, &v13);
      SysFreeString(v10);
    }
    (*(void (__fastcall **)(__int64 *))(*v14 + 16))(v14);
  }
}

```

## disassembly

```asm
0x18000b308  push    rbp
0x18000b30a  push    rbx
0x18000b30b  push    rsi
0x18000b30c  push    rdi
0x18000b30d  mov     rbp, rsp
0x18000b310  sub     rsp, 68h
0x18000b314  mov     rax, [rcx]
0x18000b317  mov     edi, edx
0x18000b319  xor     edx, edx
0x18000b31b  mov     rbx, rcx
0x18000b31e  mov     rax, [rax+230h]
0x18000b325  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b32a  mov     rax, [rbx]
0x18000b32d  lea     r8, [rbp+arg_0]
0x18000b331  lea     rdx, IID_IXMLDOMDocument2
0x18000b338  mov     [rbp+arg_0], 0
0x18000b340  mov     rcx, rbx
0x18000b343  mov     rax, [rax]
0x18000b346  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b34b  test    eax, eax
0x18000b34d  js      loc_18000B4B7
0x18000b353  xorps   xmm0, xmm0
0x18000b356  lea     rcx, [rbp+pvarg]; pvarg
0x18000b35a  xor     eax, eax
0x18000b35c  movups  xmmword ptr [rbp+pvarg], xmm0
0x18000b360  mov     qword ptr [rbp+pvarg+10h], rax
0x18000b364  call    cs:__imp_VariantInit
0x18000b36a  mov     eax, 0Bh
0x18000b36f  lea     rcx, aProhibitdtd; "ProhibitDTD"
0x18000b376  mov     word ptr [rbp+pvarg], ax
0x18000b37a  mov     eax, 1
0x18000b37f  mov     word ptr [rbp+pvarg+8], ax
0x18000b383  call    cs:__imp_SysAllocString
0x18000b389  mov     rcx, rax; pbstr
0x18000b38c  mov     rbx, rax
0x18000b38f  call    cs:__imp_SysStringLen
0x18000b395  test    eax, eax
0x18000b397  jz      short loc_18000B3CE
0x18000b399  mov     rcx, [rbp+arg_0]
0x18000b39d  lea     r8, [rbp+var_28]
0x18000b3a1  movups  xmm0, xmmword ptr [rbp+pvarg]
0x18000b3a5  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x18000b3aa  mov     rdx, [rcx]
0x18000b3ad  movaps  [rbp+var_28], xmm0
0x18000b3b1  movsd   [rbp+var_18], xmm1
0x18000b3b6  mov     rax, [rdx+280h]
0x18000b3bd  mov     rdx, rbx
0x18000b3c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3c5  mov     rcx, rbx; bstrString
0x18000b3c8  call    cs:__imp_SysFreeString
0x18000b3ce  lea     rcx, [rbp+pvarg]; pvarg
0x18000b3d2  call    cs:__imp_VariantClear
0x18000b3d8  mov     esi, 16h
0x18000b3dd  mov     dword ptr [rbp+pvarg+8], 32h ; '2'
0x18000b3e4  lea     rcx, aMaxelementdept; "MaxElementDepth"
0x18000b3eb  mov     word ptr [rbp+pvarg], si
0x18000b3ef  call    cs:__imp_SysAllocString
0x18000b3f5  mov     rcx, rax; pbstr
0x18000b3f8  mov     rbx, rax
0x18000b3fb  call    cs:__imp_SysStringLen
0x18000b401  test    eax, eax
0x18000b403  jz      short loc_18000B43A
0x18000b405  mov     rcx, [rbp+arg_0]
0x18000b409  lea     r8, [rbp+var_28]
0x18000b40d  movups  xmm0, xmmword ptr [rbp+pvarg]
0x18000b411  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x18000b416  mov     rdx, [rcx]
0x18000b419  movaps  [rbp+var_28], xmm0
0x18000b41d  movsd   [rbp+var_18], xmm1
0x18000b422  mov     rax, [rdx+280h]
0x18000b429  mov     rdx, rbx
0x18000b42c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b431  mov     rcx, rbx; bstrString
0x18000b434  call    cs:__imp_SysFreeString
0x18000b43a  lea     rcx, [rbp+pvarg]; pvarg
0x18000b43e  call    cs:__imp_VariantClear
0x18000b444  mov     eax, 19000h
0x18000b449  mov     word ptr [rbp+pvarg], si
0x18000b44d  test    edi, edi
0x18000b44f  lea     rcx, aMaxxmlsize; "MaxXMLSize"
0x18000b456  cmovnz  eax, edi
0x18000b459  mov     dword ptr [rbp+pvarg+8], eax
0x18000b45c  call    cs:__imp_SysAllocString
0x18000b462  mov     rcx, rax; pbstr
0x18000b465  mov     rbx, rax
0x18000b468  call    cs:__imp_SysStringLen
0x18000b46e  test    eax, eax
0x18000b470  jz      short loc_18000B4A7
0x18000b472  mov     rcx, [rbp+arg_0]
0x18000b476  lea     r8, [rbp+var_28]
0x18000b47a  movups  xmm0, xmmword ptr [rbp+pvarg]
0x18000b47e  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x18000b483  mov     rdx, [rcx]
0x18000b486  movaps  [rbp+var_28], xmm0
0x18000b48a  movsd   [rbp+var_18], xmm1
0x18000b48f  mov     rax, [rdx+280h]
0x18000b496  mov     rdx, rbx
0x18000b499  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b49e  mov     rcx, rbx; bstrString
0x18000b4a1  call    cs:__imp_SysFreeString
0x18000b4a7  mov     rcx, [rbp+arg_0]
0x18000b4ab  mov     rax, [rcx]
0x18000b4ae  mov     rax, [rax+10h]
0x18000b4b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4b7  add     rsp, 68h
0x18000b4bb  pop     rdi
0x18000b4bc  pop     rsi
0x18000b4bd  pop     rbx
0x18000b4be  pop     rbp
0x18000b4bf  retn
```
