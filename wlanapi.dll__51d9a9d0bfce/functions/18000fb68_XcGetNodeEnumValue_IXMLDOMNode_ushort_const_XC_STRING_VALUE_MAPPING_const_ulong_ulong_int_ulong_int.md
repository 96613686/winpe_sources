# XcGetNodeEnumValue(IXMLDOMNode *,ushort const *,_XC_STRING_VALUE_MAPPING const *,ulong,ulong *,int,ulong,int *)

- ea: `0x18000fb68`
- end: `0x18000fc40`
- name: `?XcGetNodeEnumValue@@YAKPEAUIXMLDOMNode@@PEBGPEBU_XC_STRING_VALUE_MAPPING@@KPEAKHKPEAH@Z`
- size: `216`
- prototype: `unsigned int __usercall@<eax>(struct IXMLDOMNode *@<rcx>, const unsigned __int16 *@<rdx>, const struct _XC_STRING_VALUE_MAPPING *@<r8>, unsigned int@<r9d>, unsigned int *, int, unsigned int, int *)`
- caller_count: `18`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000d660`
- `0x18000dafc`
- `0x18000df08`
- `0x1800461b0`
- `0x180046490`
- `0x180046614`
- `0x1800468c8`
- `0x180046c64`
- `0x1800479d0`
- `0x180047f94`
- `0x18004844c`
- `0x1800488ec`
- `0x180048a0c`
- `0x180048e00`
- `0x1800490d4`
- `0x1800493ac`
- `0x18004f200`
- `0x18004fc68`

## callees

- `0x18000fb68`
- `0x18000fc48`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000fbc2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000fbc2`
- `OLEAUT32!__imp_VariantInit` at `0x18000fb84`
- `OLEAUT32!__imp_VariantInit` at `0x18000fb84`
- `OLEAUT32!__imp_VariantClear` at `0x18000fbf8`
- `OLEAUT32!__imp_VariantClear` at `0x18000fbf8`

## pseudocode

```c
__int64 __fastcall XcGetNodeEnumValue(
        struct IXMLDOMNode *a1,
        const unsigned __int16 *a2,
        const struct _XC_STRING_VALUE_MAPPING *a3,
        unsigned int a4,
        unsigned int *a5,
        int a6,
        unsigned int a7,
        int *a8)
{
  unsigned int NodeTypedValue; // eax
  unsigned int v13; // ebx
  unsigned int i; // edi
  VARIANTARG pvarg; // [rsp+20h] [rbp-48h] BYREF

  VariantInit(&pvarg);
  NodeTypedValue = XcGetNodeTypedValue(a1, a2, &pvarg);
  v13 = NodeTypedValue;
  if ( NodeTypedValue == 1168 )
  {
    if ( a6 )
    {
      v13 = 0;
      *a5 = a7;
      if ( a8 )
        *a8 = 0;
    }
    else
    {
      v13 = 1206;
    }
  }
  else if ( !NodeTypedValue )
  {
    v13 = 1206;
    for ( i = 0; i < a4; ++i )
    {
      if ( !lstrcmpW(*((LPCWSTR *)a3 + 2 * i), pvarg.bstrVal) )
      {
        v13 = 0;
        *a5 = *((_DWORD *)a3 + 4 * i + 2);
        if ( a8 )
          *a8 = 1;
        break;
      }
    }
  }
  VariantClear(&pvarg);
  return v13;
}

```

## disassembly

```asm
0x18000fb68  push    rbx
0x18000fb6a  push    rbp
0x18000fb6b  push    rsi
0x18000fb6c  push    rdi
0x18000fb6d  push    r14
0x18000fb6f  sub     rsp, 40h
0x18000fb73  mov     rdi, rcx
0x18000fb76  mov     r14d, r9d
0x18000fb79  lea     rcx, [rsp+68h+pvarg]; pvarg
0x18000fb7e  mov     rbp, r8
0x18000fb81  mov     rbx, rdx
0x18000fb84  call    cs:__imp_VariantInit
0x18000fb8a  lea     r8, [rsp+68h+pvarg]; struct tagVARIANT *
0x18000fb8f  mov     rdx, rbx; unsigned __int16 *
0x18000fb92  mov     rcx, rdi; struct IXMLDOMNode *
0x18000fb95  call    ?XcGetNodeTypedValue@@YAKPEAUIXMLDOMNode@@PEBGPEAUtagVARIANT@@@Z; XcGetNodeTypedValue(IXMLDOMNode *,ushort const *,tagVARIANT *)
0x18000fb9a  mov     ebx, eax
0x18000fb9c  cmp     eax, 490h
0x18000fba1  jz      short loc_18000FC0B
0x18000fba3  test    eax, eax
0x18000fba5  jnz     short loc_18000FBF3
0x18000fba7  mov     ebx, 4B6h
0x18000fbac  xor     edi, edi
0x18000fbae  cmp     edi, r14d
0x18000fbb1  jnb     short loc_18000FBF3
0x18000fbb3  mov     rdx, qword ptr [rsp+68h+pvarg+8]; lpString2
0x18000fbb8  mov     esi, edi
0x18000fbba  add     rsi, rsi
0x18000fbbd  mov     rcx, [rbp+rsi*8+0]; lpString1
0x18000fbc2  call    cs:__imp_lstrcmpW
0x18000fbc8  test    eax, eax
0x18000fbca  jz      short loc_18000FBD0
0x18000fbcc  inc     edi
0x18000fbce  jmp     short loc_18000FBAE
0x18000fbd0  mov     rax, [rsp+68h+arg_20]
0x18000fbd8  xor     ebx, ebx
0x18000fbda  mov     ecx, [rbp+rsi*8+8]
0x18000fbde  mov     [rax], ecx
0x18000fbe0  mov     rax, [rsp+68h+arg_38]
0x18000fbe8  test    rax, rax
0x18000fbeb  jz      short loc_18000FBF3
0x18000fbed  mov     dword ptr [rax], 1
0x18000fbf3  lea     rcx, [rsp+68h+pvarg]; pvarg
0x18000fbf8  call    cs:__imp_VariantClear
0x18000fbfe  mov     eax, ebx
0x18000fc00  add     rsp, 40h
0x18000fc04  pop     r14
0x18000fc06  pop     rdi
0x18000fc07  pop     rsi
0x18000fc08  pop     rbp
0x18000fc09  pop     rbx
0x18000fc0a  retn
0x18000fc0b  cmp     [rsp+68h+arg_28], 0
0x18000fc13  jz      short loc_18000FC39
0x18000fc15  mov     rax, [rsp+68h+arg_20]
0x18000fc1d  xor     ebx, ebx
0x18000fc1f  mov     ecx, [rsp+68h+arg_30]
0x18000fc26  mov     [rax], ecx
0x18000fc28  mov     rax, [rsp+68h+arg_38]
0x18000fc30  test    rax, rax
0x18000fc33  jz      short loc_18000FBF3
0x18000fc35  mov     [rax], ebx
0x18000fc37  jmp     short loc_18000FBF3
0x18000fc39  mov     ebx, 4B6h
0x18000fc3e  jmp     short loc_18000FBF3
```
