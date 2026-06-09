# CParseTreeNode::SetRuleData(ushort const *,CSPList<IParseTreeNode *,IParseTreeNode *> &)

- ea: `0x18000ee58`
- end: `0x18000ef04`
- name: `?SetRuleData@CParseTreeNode@@QEAAJPEBGAEAV?$CSPList@PEAUIParseTreeNode@@PEAU1@@@@Z`
- size: `172`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c2b8`
- `0x18000c514`

## callees

- `0x18000ee58`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x18000ee74`
- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x18000ee74`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18000eeae`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18000eeae`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18000eedc`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18000eedc`

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
0x18000ee58  mov     [rsp+arg_10], rbx
0x18000ee5d  push    rdi
0x18000ee5e  sub     rsp, 20h
0x18000ee62  mov     byte ptr [rcx+40h], 0
0x18000ee66  mov     rdi, r8
0x18000ee69  mov     rbx, rcx
0x18000ee6c  test    rdx, rdx
0x18000ee6f  jz      short loc_18000EE8A
0x18000ee71  mov     rcx, rdx
0x18000ee74  call    cs:__imp__o__wcsdup
0x18000ee7a  mov     [rbx+50h], rax
0x18000ee7e  test    rax, rax
0x18000ee81  jnz     short loc_18000EE92
0x18000ee83  mov     eax, 8007000Eh
0x18000ee88  jmp     short loc_18000EEF9
0x18000ee8a  mov     qword ptr [rcx+50h], 0
0x18000ee92  mov     eax, [rdi+10h]
0x18000ee95  lea     r8, [rsp+28h+rgsabound]; rgsabound
0x18000ee9a  mov     ecx, 0Dh; vt
0x18000ee9f  mov     [rsp+28h+rgsabound.lLbound], 0
0x18000eea7  mov     [rsp+28h+rgsabound.cElements], eax
0x18000eeab  lea     edx, [rcx-0Ch]; cDims
0x18000eeae  call    cs:__imp_SafeArrayCreate
0x18000eeb4  mov     [rbx+60h], rax
0x18000eeb8  test    rax, rax
0x18000eebb  jz      short loc_18000EE83
0x18000eebd  mov     r8, [rdi]
0x18000eec0  xor     eax, eax
0x18000eec2  mov     [rsp+28h+rgIndices], eax
0x18000eec6  cmp     [rsp+28h+rgsabound.cElements], eax
0x18000eeca  jle     short loc_18000EEF9
0x18000eecc  mov     rdi, [r8]
0x18000eecf  lea     rdx, [rsp+28h+rgIndices]; rgIndices
0x18000eed4  mov     r8, [r8+10h]; pv
0x18000eed8  mov     rcx, [rbx+60h]; psa
0x18000eedc  call    cs:__imp_SafeArrayPutElement
0x18000eee2  test    eax, eax
0x18000eee4  js      short loc_18000EEF9
0x18000eee6  mov     ecx, [rsp+28h+rgIndices]
0x18000eeea  mov     r8, rdi
0x18000eeed  inc     ecx
0x18000eeef  mov     [rsp+28h+rgIndices], ecx
0x18000eef3  cmp     ecx, [rsp+28h+rgsabound.cElements]
0x18000eef7  jl      short loc_18000EECC
0x18000eef9  mov     rbx, [rsp+28h+arg_10]
0x18000eefe  add     rsp, 20h
0x18000ef02  pop     rdi
0x18000ef03  retn
```
