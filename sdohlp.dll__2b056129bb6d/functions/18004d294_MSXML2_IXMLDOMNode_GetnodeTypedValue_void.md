# MSXML2::IXMLDOMNode::GetnodeTypedValue(void)

- ea: `0x18004d294`
- end: `0x18004d30c`
- name: `?GetnodeTypedValue@IXMLDOMNode@MSXML2@@QEAA?AV_variant_t@@XZ`
- size: `120`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004bdbc`
- `0x18004cef4`
- `0x18004cf60`
- `0x18004d11c`

## callees

- `0x18004115c`
- `0x18004d294`
- `0x180058010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18004d2b8`
- `OLEAUT32!__imp_VariantInit` at `0x18004d2b8`

## pseudocode

```c
__int64 __fastcall MSXML2::IXMLDOMNode::GetnodeTypedValue(struct IUnknown *a1, __int64 a2)
{
  int v4; // eax
  __int64 result; // rax
  IRecordInfo *pRecInfo; // xmm1_8
  VARIANTARG pvarg; // [rsp+28h] [rbp-20h] BYREF

  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v4 = ((__int64 (__fastcall *)(struct IUnknown *, VARIANTARG *))a1->lpVtbl[10].QueryInterface)(a1, &pvarg);
  if ( v4 < 0 )
    _com_issue_errorex(v4, a1, &GUID_2933bf80_7b36_11d2_b20e_00c04f983e60);
  result = a2;
  pRecInfo = pvarg.pRecInfo;
  *(_OWORD *)a2 = *(_OWORD *)&pvarg.vt;
  *(_QWORD *)(a2 + 16) = pRecInfo;
  return result;
}

```

## disassembly

```asm
0x18004d294  mov     [rsp+arg_0], rbx
0x18004d299  push    rdi
0x18004d29a  sub     rsp, 40h
0x18004d29e  mov     rdi, rcx
0x18004d2a1  xorps   xmm0, xmm0
0x18004d2a4  xor     eax, eax
0x18004d2a6  lea     rcx, [rsp+48h+pvarg]; pvarg
0x18004d2ab  movups  xmmword ptr [rsp+48h+pvarg], xmm0
0x18004d2b0  mov     qword ptr [rsp+48h+pvarg+10h], rax
0x18004d2b5  mov     rbx, rdx
0x18004d2b8  call    cs:__imp_VariantInit
0x18004d2be  mov     rax, [rdi]
0x18004d2c1  lea     rdx, [rsp+48h+pvarg]
0x18004d2c6  mov     rcx, rdi
0x18004d2c9  mov     rax, [rax+0F0h]
0x18004d2d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d2d5  test    eax, eax
0x18004d2d7  jns     short loc_18004D2EB
0x18004d2d9  lea     r8, _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60; struct _GUID *
0x18004d2e0  mov     rdx, rdi; struct IUnknown *
0x18004d2e3  mov     ecx, eax; int
0x18004d2e5  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
0x18004d2eb  movups  xmm0, xmmword ptr [rsp+48h+pvarg]
0x18004d2f0  mov     rax, rbx
0x18004d2f3  movsd   xmm1, qword ptr [rsp+48h+pvarg+10h]
0x18004d2f9  movups  xmmword ptr [rbx], xmm0
0x18004d2fc  movsd   qword ptr [rbx+10h], xmm1
0x18004d301  mov     rbx, [rsp+48h+arg_0]
0x18004d306  add     rsp, 40h
0x18004d30a  pop     rdi
0x18004d30b  retn
```
