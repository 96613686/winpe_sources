# GetDefaultAuthTypeVariantArray(tagVARIANT *)

- ea: `0x180034e34`
- end: `0x180034f02`
- name: `?GetDefaultAuthTypeVariantArray@@YAJPEAUtagVARIANT@@@Z`
- size: `206`
- prototype: `__int64 __fastcall(VARIANTARG *pvarg)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180034444`

## callees

- `0x180034e34`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180034e92`
- `OLEAUT32!__imp_VariantInit` at `0x180034eda`
- `OLEAUT32!__imp_VariantInit` at `0x180034e92`
- `OLEAUT32!__imp_VariantInit` at `0x180034eda`
- `OLEAUT32!__imp_VariantClear` at `0x180034ec7`
- `OLEAUT32!__imp_VariantClear` at `0x180034eed`
- `OLEAUT32!__imp_VariantClear` at `0x180034ec7`
- `OLEAUT32!__imp_VariantClear` at `0x180034eed`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180034e77`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180034e77`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180034eb7`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180034eb7`

## pseudocode

```c
__int64 __fastcall GetDefaultAuthTypeVariantArray(VARIANTARG *pvarg)
{
  HRESULT v2; // edi
  SAFEARRAY *v3; // rsi
  int i; // eax
  __m128i si128; // [rsp+20h] [rbp-30h]
  VARIANTARG pvarga; // [rsp+30h] [rbp-20h] BYREF
  LONG rgIndices; // [rsp+78h] [rbp+28h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+80h] [rbp+30h] BYREF

  rgsabound = (SAFEARRAYBOUND)4LL;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v2 = -2147467259;
  memset(&pvarga, 0, sizeof(pvarga));
  v3 = SafeArrayCreate(0xCu, 1u, &rgsabound);
  rgIndices = 0;
  for ( i = 0; i < 4; i = ++rgIndices )
  {
    VariantInit(&pvarga);
    pvarga.vt = 3;
    pvarga.lVal = si128.m128i_i32[rgIndices];
    v2 = SafeArrayPutElement(v3, &rgIndices, &pvarga);
    if ( v2 < 0 )
      goto LABEL_6;
    VariantClear(&pvarga);
  }
  VariantInit(pvarg);
  pvarg->vt = 8204;
  pvarg->llVal = (LONGLONG)v3;
LABEL_6:
  VariantClear(&pvarga);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180034e34  mov     [rsp-18h+arg_0], rbx
0x180034e39  push    rbp
0x180034e3a  push    rsi
0x180034e3b  push    rdi
0x180034e3c  mov     rbp, rsp
0x180034e3f  sub     rsp, 50h
0x180034e43  movdqa  xmm0, cs:__xmm@0000000a000000040000000900000003
0x180034e4b  lea     r8, [rbp+rgsabound]; rgsabound
0x180034e4f  xor     eax, eax
0x180034e51  mov     qword ptr [rbp+rgsabound.cElements], 4
0x180034e59  movdqu  [rbp+var_30], xmm0
0x180034e5e  mov     rbx, rcx
0x180034e61  mov     qword ptr [rbp+pvarg+10h], rax
0x180034e65  xorps   xmm0, xmm0
0x180034e68  mov     edi, 80004005h
0x180034e6d  lea     ecx, [rax+0Ch]; vt
0x180034e70  lea     edx, [rax+1]; cDims
0x180034e73  movups  xmmword ptr [rbp+pvarg], xmm0
0x180034e77  call    cs:__imp_SafeArrayCreate
0x180034e7d  mov     rsi, rax
0x180034e80  mov     [rbp+rgIndices], 0
0x180034e87  xor     eax, eax
0x180034e89  cmp     eax, 4
0x180034e8c  jge     short loc_180034ED7
0x180034e8e  lea     rcx, [rbp+pvarg]; pvarg
0x180034e92  call    cs:__imp_VariantInit
0x180034e98  mov     eax, 3
0x180034e9d  lea     r8, [rbp+pvarg]; pv
0x180034ea1  mov     word ptr [rbp+pvarg], ax
0x180034ea5  lea     rdx, [rbp+rgIndices]; rgIndices
0x180034ea9  movsxd  rax, [rbp+rgIndices]
0x180034ead  mov     ecx, dword ptr [rbp+rax*4+var_30]
0x180034eb1  mov     dword ptr [rbp+pvarg+8], ecx
0x180034eb4  mov     rcx, rsi; psa
0x180034eb7  call    cs:__imp_SafeArrayPutElement
0x180034ebd  mov     edi, eax
0x180034ebf  test    eax, eax
0x180034ec1  js      short loc_180034EE9
0x180034ec3  lea     rcx, [rbp+pvarg]; pvarg
0x180034ec7  call    cs:__imp_VariantClear
0x180034ecd  mov     eax, [rbp+rgIndices]
0x180034ed0  inc     eax
0x180034ed2  mov     [rbp+rgIndices], eax
0x180034ed5  jmp     short loc_180034E89
0x180034ed7  mov     rcx, rbx; pvarg
0x180034eda  call    cs:__imp_VariantInit
0x180034ee0  mov     word ptr [rbx], 200Ch
0x180034ee5  mov     [rbx+8], rsi
0x180034ee9  lea     rcx, [rbp+pvarg]; pvarg
0x180034eed  call    cs:__imp_VariantClear
0x180034ef3  mov     rbx, [rsp+50h+arg_0]
0x180034ef8  mov     eax, edi
0x180034efa  add     rsp, 50h
0x180034efe  pop     rdi
0x180034eff  pop     rsi
0x180034f00  pop     rbp
0x180034f01  retn
```
