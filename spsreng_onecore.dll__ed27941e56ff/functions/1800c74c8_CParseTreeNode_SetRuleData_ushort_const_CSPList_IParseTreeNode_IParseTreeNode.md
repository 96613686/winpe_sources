# CParseTreeNode::SetRuleData(ushort const *,CSPList<IParseTreeNode *,IParseTreeNode *> &)

- ea: `0x1800c74c8`
- end: `0x1800c7574`
- name: `?SetRuleData@CParseTreeNode@@QEAAJPEBGAEAV?$CSPList@PEAUIParseTreeNode@@PEAU1@@@@Z`
- size: `172`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800be8e4`
- `0x1800beb30`

## callees

- `0x1800c74c8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x1800c74e4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x1800c74e4`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800c751e`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800c751e`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1800c754c`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1800c754c`

## pseudocode

```c
HRESULT __fastcall CParseTreeNode::SetRuleData(__int64 a1, __int64 a2, __int64 **a3)
{
  __int64 v5; // rax
  HRESULT result; // eax
  ULONG v7; // eax
  SAFEARRAY *v8; // rax
  __int64 **v9; // r8
  __int64 *v10; // rdi
  LONG rgIndices; // [rsp+30h] [rbp+8h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+38h] [rbp+10h] BYREF

  *(_BYTE *)(a1 + 64) = 0;
  if ( a2 )
  {
    v5 = _o__wcsdup(a2);
    *(_QWORD *)(a1 + 80) = v5;
    if ( !v5 )
      return -2147024882;
  }
  else
  {
    *(_QWORD *)(a1 + 80) = 0;
  }
  v7 = *((_DWORD *)a3 + 4);
  rgsabound.lLbound = 0;
  rgsabound.cElements = v7;
  v8 = SafeArrayCreate(0xDu, 1u, &rgsabound);
  *(_QWORD *)(a1 + 96) = v8;
  if ( !v8 )
    return -2147024882;
  v9 = (__int64 **)*a3;
  result = 0;
  for ( rgIndices = 0; rgIndices < (int)rgsabound.cElements; ++rgIndices )
  {
    v10 = *v9;
    result = SafeArrayPutElement(*(SAFEARRAY **)(a1 + 96), &rgIndices, v9[2]);
    if ( result < 0 )
      break;
    v9 = (__int64 **)v10;
  }
  return result;
}

```

## disassembly

```asm
0x1800c74c8  mov     [rsp+arg_10], rbx
0x1800c74cd  push    rdi
0x1800c74ce  sub     rsp, 20h
0x1800c74d2  mov     byte ptr [rcx+40h], 0
0x1800c74d6  mov     rdi, r8
0x1800c74d9  mov     rbx, rcx
0x1800c74dc  test    rdx, rdx
0x1800c74df  jz      short loc_1800C74FA
0x1800c74e1  mov     rcx, rdx
0x1800c74e4  call    cs:__imp__o__wcsdup
0x1800c74ea  mov     [rbx+50h], rax
0x1800c74ee  test    rax, rax
0x1800c74f1  jnz     short loc_1800C7502
0x1800c74f3  mov     eax, 8007000Eh
0x1800c74f8  jmp     short loc_1800C7569
0x1800c74fa  mov     qword ptr [rcx+50h], 0
0x1800c7502  mov     eax, [rdi+10h]
0x1800c7505  lea     r8, [rsp+28h+rgsabound]; rgsabound
0x1800c750a  mov     ecx, 0Dh; vt
0x1800c750f  mov     [rsp+28h+rgsabound.lLbound], 0
0x1800c7517  mov     [rsp+28h+rgsabound.cElements], eax
0x1800c751b  lea     edx, [rcx-0Ch]; cDims
0x1800c751e  call    cs:__imp_SafeArrayCreate
0x1800c7524  mov     [rbx+60h], rax
0x1800c7528  test    rax, rax
0x1800c752b  jz      short loc_1800C74F3
0x1800c752d  mov     r8, [rdi]
0x1800c7530  xor     eax, eax
0x1800c7532  mov     [rsp+28h+rgIndices], eax
0x1800c7536  cmp     [rsp+28h+rgsabound.cElements], eax
0x1800c753a  jle     short loc_1800C7569
0x1800c753c  mov     rdi, [r8]
0x1800c753f  lea     rdx, [rsp+28h+rgIndices]; rgIndices
0x1800c7544  mov     r8, [r8+10h]; pv
0x1800c7548  mov     rcx, [rbx+60h]; psa
0x1800c754c  call    cs:__imp_SafeArrayPutElement
0x1800c7552  test    eax, eax
0x1800c7554  js      short loc_1800C7569
0x1800c7556  mov     ecx, [rsp+28h+rgIndices]
0x1800c755a  mov     r8, rdi
0x1800c755d  inc     ecx
0x1800c755f  mov     [rsp+28h+rgIndices], ecx
0x1800c7563  cmp     ecx, [rsp+28h+rgsabound.cElements]
0x1800c7567  jl      short loc_1800C753C
0x1800c7569  mov     rbx, [rsp+28h+arg_10]
0x1800c756e  add     rsp, 20h
0x1800c7572  pop     rdi
0x1800c7573  retn
```
