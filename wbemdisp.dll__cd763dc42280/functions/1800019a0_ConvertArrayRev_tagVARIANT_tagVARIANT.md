# ConvertArrayRev(tagVARIANT *,tagVARIANT *)

- ea: `0x1800019a0`
- end: `0x180001b70`
- name: `?ConvertArrayRev@@YAJPEAUtagVARIANT@@0@Z`
- size: `464`
- prototype: `__int64 __fastcall(struct tagVARIANT *, struct tagVARIANT *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180001070`
- `0x180003a10`
- `0x1800051d0`
- `0x1800058c0`
- `0x180024720`

## callees

- `0x1800019a0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180001b24`
- `OLEAUT32!__imp_SysAllocString` at `0x180001b24`
- `OLEAUT32!__imp_SysFreeString` at `0x180001b32`
- `OLEAUT32!__imp_SysFreeString` at `0x180001b32`
- `OLEAUT32!__imp_VariantInit` at `0x180001a9c`
- `OLEAUT32!__imp_VariantInit` at `0x180001a9c`
- `OLEAUT32!__imp_VariantClear` at `0x180001ae5`
- `OLEAUT32!__imp_VariantClear` at `0x180001ae5`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180001a6b`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180001a6b`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1800019e4`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1800019e4`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180001a29`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180001a29`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180001a09`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180001a09`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180001ac4`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180001afa`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180001b16`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180001ac4`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180001afa`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180001b16`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180001ad9`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180001ad9`

## pseudocode

```c
HRESULT __fastcall ConvertArrayRev(struct tagVARIANT *a1, struct tagVARIANT *a2)
{
  SAFEARRAY *parray; // rcx
  HRESULT result; // eax
  HRESULT v6; // ebx
  VARTYPE v7; // di
  SAFEARRAY *v8; // rax
  LONG v9; // ecx
  SAFEARRAY *v10; // r14
  SAFEARRAY *v11; // rcx
  OLECHAR *pv; // [rsp+20h] [rbp-48h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+28h] [rbp-40h] BYREF
  VARIANTARG pvarg; // [rsp+30h] [rbp-38h] BYREF
  LONG plLbound; // [rsp+98h] [rbp+30h] BYREF
  LONG plUbound; // [rsp+A0h] [rbp+38h] BYREF
  __int64 rgIndices; // [rsp+A8h] [rbp+40h] BYREF

  if ( !a2 || !a1 || (a2->vt & 0x2000) == 0 || SafeArrayGetDim(a2->parray) != 1 )
    return -2147217407;
  parray = a2->parray;
  rgIndices = 0;
  plLbound = 0;
  plUbound = 0;
  result = SafeArrayGetLBound(parray, 1u, &plLbound);
  if ( !result )
  {
    result = SafeArrayGetUBound(a2->parray, 1u, &plUbound);
    v6 = result;
    if ( !result )
    {
      v7 = a2->vt & 0xDFFF;
      rgsabound.lLbound = 0;
      rgsabound.cElements = plUbound - plLbound + 1;
      v8 = SafeArrayCreate(0xCu, 1u, &rgsabound);
      v9 = plLbound;
      v10 = v8;
      while ( 1 )
      {
        LODWORD(rgIndices) = v9;
        if ( v9 > plUbound || v6 )
          break;
        memset(&pvarg, 0, sizeof(pvarg));
        VariantInit(&pvarg);
        v11 = a2->parray;
        pvarg.vt = v7;
        if ( v7 == 8 )
        {
          pv = 0;
          result = SafeArrayGetElement(v11, (LONG *)&rgIndices, &pv);
          if ( result )
            return result;
          pvarg.llVal = (LONGLONG)SysAllocString(pv);
          SysFreeString(pv);
        }
        else if ( v7 == 9 || v7 == 13 )
        {
          pv = 0;
          result = SafeArrayGetElement(v11, (LONG *)&rgIndices, &pv);
          if ( result )
            return result;
          pvarg.llVal = (LONGLONG)pv;
        }
        else
        {
          result = SafeArrayGetElement(v11, (LONG *)&rgIndices, &pvarg.decVal.8);
          if ( result )
            return result;
        }
        v6 = SafeArrayPutElement(v10, (LONG *)&rgIndices, &pvarg);
        VariantClear(&pvarg);
        v9 = rgIndices + 1;
      }
      a1->vt = 8204;
      result = 0;
      a1->llVal = (LONGLONG)v10;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800019a0  push    rbp
0x1800019a2  push    rsi
0x1800019a3  push    r12
0x1800019a5  push    r15
0x1800019a7  mov     rbp, rsp
0x1800019aa  sub     rsp, 68h
0x1800019ae  mov     rsi, rdx
0x1800019b1  mov     r15, rcx
0x1800019b4  test    rdx, rdx
0x1800019b7  jz      loc_180001B60
0x1800019bd  test    rcx, rcx
0x1800019c0  jz      loc_180001B60
0x1800019c6  movzx   r8d, word ptr [rdx]
0x1800019ca  mov     eax, 2000h
0x1800019cf  and     r8w, ax
0x1800019d3  xor     r12d, r12d
0x1800019d6  cmp     r12w, r8w
0x1800019da  jz      loc_180001B60
0x1800019e0  mov     rcx, [rdx+8]; psa
0x1800019e4  call    cs:__imp_SafeArrayGetDim
0x1800019ea  cmp     eax, 1
0x1800019ed  jnz     loc_180001B60
0x1800019f3  mov     rcx, [rsi+8]; psa
0x1800019f7  lea     r8, [rbp+plLbound]; plLbound
0x1800019fb  mov     edx, eax; nDim
0x1800019fd  mov     [rbp+rgIndices], r12
0x180001a01  mov     [rbp+plLbound], r12d
0x180001a05  mov     [rbp+plUbound], r12d
0x180001a09  call    cs:__imp_SafeArrayGetLBound
0x180001a0f  test    eax, eax
0x180001a11  jnz     loc_180001B55
0x180001a17  mov     rcx, [rsi+8]; psa
0x180001a1b  lea     r8, [rbp+plUbound]; plUbound
0x180001a1f  mov     edx, 1; nDim
0x180001a24  mov     [rsp+68h+var_8], rbx
0x180001a29  call    cs:__imp_SafeArrayGetUBound
0x180001a2f  mov     ebx, eax
0x180001a31  test    eax, eax
0x180001a33  jnz     loc_180001B50
0x180001a39  mov     [rsp+68h+var_10], rdi
0x180001a3e  lea     r8, [rbp+rgsabound]; rgsabound
0x180001a42  movzx   edi, word ptr [rsi]
0x180001a45  mov     eax, 0DFFFh
0x180001a4a  and     di, ax
0x180001a4d  mov     [rsp+68h+var_18], r14
0x180001a52  mov     eax, [rbp+plUbound]
0x180001a55  mov     ecx, 0Ch; vt
0x180001a5a  sub     eax, [rbp+plLbound]
0x180001a5d  mov     edx, 1; cDims
0x180001a62  inc     eax
0x180001a64  mov     [rbp+rgsabound.lLbound], r12d
0x180001a68  mov     [rbp+rgsabound.cElements], eax
0x180001a6b  call    cs:__imp_SafeArrayCreate
0x180001a71  mov     ecx, [rbp+plLbound]
0x180001a74  mov     r14, rax
0x180001a77  mov     dword ptr [rbp+rgIndices], ecx
0x180001a7a  cmp     ecx, [rbp+plUbound]
0x180001a7d  jg      loc_180001B3A
0x180001a83  test    ebx, ebx
0x180001a85  jnz     loc_180001B3A
0x180001a8b  xorps   xmm0, xmm0
0x180001a8e  lea     rcx, [rbp+pvarg]; pvarg
0x180001a92  xor     eax, eax
0x180001a94  movups  xmmword ptr [rbp+pvarg], xmm0
0x180001a98  mov     qword ptr [rbp+pvarg+10h], rax
0x180001a9c  call    cs:__imp_VariantInit
0x180001aa2  mov     rcx, [rsi+8]; psa
0x180001aa6  lea     rdx, [rbp+rgIndices]; rgIndices
0x180001aaa  movzx   eax, di
0x180001aad  mov     word ptr [rbp+pvarg], di
0x180001ab1  sub     eax, 8
0x180001ab4  jz      short loc_180001B0E
0x180001ab6  sub     eax, 1
0x180001ab9  jz      short loc_180001AF2
0x180001abb  cmp     eax, 4
0x180001abe  jz      short loc_180001AF2
0x180001ac0  lea     r8, [rbp+pvarg+8]; pv
0x180001ac4  call    cs:__imp_SafeArrayGetElement
0x180001aca  test    eax, eax
0x180001acc  jnz     short loc_180001B46
0x180001ace  lea     r8, [rbp+pvarg]; pv
0x180001ad2  mov     rcx, r14; psa
0x180001ad5  lea     rdx, [rbp+rgIndices]; rgIndices
0x180001ad9  call    cs:__imp_SafeArrayPutElement
0x180001adf  lea     rcx, [rbp+pvarg]; pvarg
0x180001ae3  mov     ebx, eax
0x180001ae5  call    cs:__imp_VariantClear
0x180001aeb  mov     ecx, dword ptr [rbp+rgIndices]
0x180001aee  inc     ecx
0x180001af0  jmp     short loc_180001A77
0x180001af2  lea     r8, [rbp+pv]; pv
0x180001af6  mov     [rbp+pv], r12
0x180001afa  call    cs:__imp_SafeArrayGetElement
0x180001b00  test    eax, eax
0x180001b02  jnz     short loc_180001B46
0x180001b04  mov     rax, [rbp+pv]
0x180001b08  mov     qword ptr [rbp+pvarg+8], rax
0x180001b0c  jmp     short loc_180001ACE
0x180001b0e  lea     r8, [rbp+pv]; pv
0x180001b12  mov     [rbp+pv], r12
0x180001b16  call    cs:__imp_SafeArrayGetElement
0x180001b1c  test    eax, eax
0x180001b1e  jnz     short loc_180001B46
0x180001b20  mov     rcx, [rbp+pv]; psz
0x180001b24  call    cs:__imp_SysAllocString
0x180001b2a  mov     rcx, [rbp+pv]; bstrString
0x180001b2e  mov     qword ptr [rbp+pvarg+8], rax
0x180001b32  call    cs:__imp_SysFreeString
0x180001b38  jmp     short loc_180001ACE
0x180001b3a  mov     word ptr [r15], 200Ch
0x180001b40  xor     eax, eax
0x180001b42  mov     [r15+8], r14
0x180001b46  mov     rdi, [rsp+68h+var_10]
0x180001b4b  mov     r14, [rsp+68h+var_18]
0x180001b50  mov     rbx, [rsp+68h+var_8]
0x180001b55  add     rsp, 68h
0x180001b59  pop     r15
0x180001b5b  pop     r12
0x180001b5d  pop     rsi
0x180001b5e  pop     rbp
0x180001b5f  retn
0x180001b60  mov     eax, 80041001h
0x180001b65  add     rsp, 68h
0x180001b69  pop     r15
0x180001b6b  pop     r12
0x180001b6d  pop     rsi
0x180001b6e  pop     rbp
0x180001b6f  retn
```
