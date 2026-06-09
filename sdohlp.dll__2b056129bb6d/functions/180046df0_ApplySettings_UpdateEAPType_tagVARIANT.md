# ApplySettings::UpdateEAPType(tagVARIANT &)

- ea: `0x180046df0`
- end: `0x180046f6d`
- name: `?UpdateEAPType@ApplySettings@@AEAAJAEAUtagVARIANT@@@Z`
- size: `381`
- prototype: `int(ApplySettings *__hidden this, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x18004520c`

## callees

- `0x1800435f8`
- `0x180046df0`

## import_xrefs

- `msvcrt!wcstol` at `0x180046e73`
- `msvcrt!wcstol` at `0x180046e73`
- `OLEAUT32!__imp_VariantInit` at `0x180046ec6`
- `OLEAUT32!__imp_VariantInit` at `0x180046ec6`
- `OLEAUT32!__imp_VariantClear` at `0x180046f20`
- `OLEAUT32!__imp_VariantClear` at `0x180046f44`
- `OLEAUT32!__imp_VariantClear` at `0x180046f20`
- `OLEAUT32!__imp_VariantClear` at `0x180046f44`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180046e30`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180046e30`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180046f36`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180046f36`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180046f16`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180046f16`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180046eac`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180046eac`

## pseudocode

```c
__int64 __fastcall ApplySettings::UpdateEAPType(ApplySettings *this, struct tagVARIANT *a2)
{
  LONGLONG llVal; // rax
  __int64 v5; // r14
  __int64 v6; // rbx
  SAFEARRAY *v7; // rsi
  __int64 result; // rax
  LONG v9; // r12d
  __int64 v10; // rax
  const wchar_t *v11; // rcx
  char v12; // r14
  SAFEARRAY *Vector; // r15
  unsigned __int64 i; // rcx
  VARIANTARG pvarg; // [rsp+20h] [rbp-20h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+88h] [rbp+48h] BYREF
  LONG rgIndices; // [rsp+90h] [rbp+50h] BYREF
  int v18; // [rsp+94h] [rbp+54h]
  __int64 v19; // [rsp+98h] [rbp+58h]

  llVal = a2->llVal;
  v5 = *(unsigned int *)(llVal + 24);
  v6 = *(_QWORD *)(llVal + 16);
  rgsabound.cElements = *(_DWORD *)(llVal + 24);
  rgsabound.lLbound = 0;
  v7 = SafeArrayCreate(0xCu, 1u, &rgsabound);
  if ( !v7 )
    return 2147942414LL;
  v9 = 0;
  v10 = v6 + 24 * v5;
  v19 = v10;
  while ( v6 != v10 )
  {
    v11 = *(const wchar_t **)(v6 + 8);
    if ( v11 )
    {
      v12 = wcstol(v11, 0, 10);
      if ( v12 )
      {
        if ( v12 == 4 && !*((_BYTE *)this + 144) )
        {
          EnableEapMD5Support();
          *((_BYTE *)this + 144) = 1;
        }
        Vector = SafeArrayCreateVector(0x11u, 0, 0x10u);
        memset(&pvarg, 0, sizeof(pvarg));
        VariantInit(&pvarg);
        if ( !Vector )
        {
          SafeArrayDestroy(v7);
          return 2147942414LL;
        }
        *(_BYTE *)Vector->pvData = v12;
        for ( i = 1; i < 0x10; ++i )
          *((_BYTE *)Vector->pvData + i) = 0;
        pvarg.llVal = (LONGLONG)Vector;
        pvarg.vt = 8209;
        v18 = 0;
        rgIndices = v9++;
        SafeArrayPutElement(v7, &rgIndices, &pvarg);
        VariantClear(&pvarg);
      }
      v10 = v19;
    }
    v6 += 24;
  }
  VariantClear(a2);
  result = 0;
  a2->vt = 8204;
  a2->llVal = (LONGLONG)v7;
  return result;
}

```

## disassembly

```asm
0x180046df0  mov     [rsp-38h+arg_0], rbx
0x180046df5  push    rbp
0x180046df6  push    rsi
0x180046df7  push    rdi
0x180046df8  push    r12
0x180046dfa  push    r13
0x180046dfc  push    r14
0x180046dfe  push    r15
0x180046e00  mov     rbp, rsp
0x180046e03  sub     rsp, 40h
0x180046e07  mov     rax, [rdx+8]
0x180046e0b  lea     r8, [rbp+rgsabound]; rgsabound
0x180046e0f  mov     r13, rcx
0x180046e12  mov     rdi, rdx
0x180046e15  mov     ecx, 0Ch; vt
0x180046e1a  mov     r14d, [rax+18h]
0x180046e1e  mov     rbx, [rax+10h]
0x180046e22  lea     edx, [rcx-0Bh]; cDims
0x180046e25  mov     [rbp+rgsabound.cElements], r14d
0x180046e29  mov     [rbp+rgsabound.lLbound], 0
0x180046e30  call    cs:__imp_SafeArrayCreate
0x180046e36  mov     rsi, rax
0x180046e39  test    rax, rax
0x180046e3c  jnz     short loc_180046E48
0x180046e3e  mov     eax, 8007000Eh
0x180046e43  jmp     loc_180046F55
0x180046e48  lea     rcx, [r14+r14*2]
0x180046e4c  xor     r12d, r12d
0x180046e4f  lea     rax, [rbx+rcx*8]
0x180046e53  mov     [rbp+arg_18], rax
0x180046e57  cmp     rbx, rax
0x180046e5a  jz      loc_180046F41
0x180046e60  mov     rcx, [rbx+8]; String
0x180046e64  test    rcx, rcx
0x180046e67  jz      loc_180046F2A
0x180046e6d  xor     edx, edx; EndPtr
0x180046e6f  lea     r8d, [rdx+0Ah]; Radix
0x180046e73  call    cs:__imp_wcstol
0x180046e79  mov     r14d, eax
0x180046e7c  test    al, al
0x180046e7e  jz      loc_180046F26
0x180046e84  cmp     r14b, 4
0x180046e88  jnz     short loc_180046EA1
0x180046e8a  cmp     byte ptr [r13+90h], 0
0x180046e92  jnz     short loc_180046EA1
0x180046e94  call    EnableEapMD5Support
0x180046e99  mov     byte ptr [r13+90h], 1
0x180046ea1  mov     ecx, 11h; vt
0x180046ea6  xor     edx, edx; lLbound
0x180046ea8  lea     r8d, [rcx-1]; cElements
0x180046eac  call    cs:__imp_SafeArrayCreateVector
0x180046eb2  xorps   xmm0, xmm0
0x180046eb5  lea     rcx, [rbp+pvarg]; pvarg
0x180046eb9  mov     r15, rax
0x180046ebc  xor     eax, eax
0x180046ebe  mov     qword ptr [rbp+pvarg+10h], rax
0x180046ec2  movups  xmmword ptr [rbp+pvarg], xmm0
0x180046ec6  call    cs:__imp_VariantInit
0x180046ecc  test    r15, r15
0x180046ecf  jz      short loc_180046F33
0x180046ed1  mov     rcx, [r15+10h]
0x180046ed5  mov     [rcx], r14b
0x180046ed8  mov     ecx, 1
0x180046edd  mov     rax, [r15+10h]
0x180046ee1  mov     byte ptr [rcx+rax], 0
0x180046ee5  inc     rcx
0x180046ee8  cmp     rcx, 10h
0x180046eec  jb      short loc_180046EDD
0x180046eee  mov     eax, 2011h
0x180046ef3  mov     qword ptr [rbp+pvarg+8], r15
0x180046ef7  mov     word ptr [rbp+pvarg], ax
0x180046efb  lea     r8, [rbp+pvarg]; pv
0x180046eff  mov     eax, r12d
0x180046f02  mov     [rbp+arg_14], 0
0x180046f09  lea     rdx, [rbp+rgIndices]; rgIndices
0x180046f0d  mov     [rbp+rgIndices], eax
0x180046f10  mov     rcx, rsi; psa
0x180046f13  inc     r12d
0x180046f16  call    cs:__imp_SafeArrayPutElement
0x180046f1c  lea     rcx, [rbp+pvarg]; pvarg
0x180046f20  call    cs:__imp_VariantClear
0x180046f26  mov     rax, [rbp+arg_18]
0x180046f2a  add     rbx, 18h
0x180046f2e  jmp     loc_180046E57
0x180046f33  mov     rcx, rsi; psa
0x180046f36  call    cs:__imp_SafeArrayDestroy
0x180046f3c  jmp     loc_180046E3E
0x180046f41  mov     rcx, rdi; pvarg
0x180046f44  call    cs:__imp_VariantClear
0x180046f4a  xor     eax, eax
0x180046f4c  mov     word ptr [rdi], 200Ch
0x180046f51  mov     [rdi+8], rsi
0x180046f55  mov     rbx, [rsp+40h+arg_0]
0x180046f5d  add     rsp, 40h
0x180046f61  pop     r15
0x180046f63  pop     r14
0x180046f65  pop     r13
0x180046f67  pop     r12
0x180046f69  pop     rdi
0x180046f6a  pop     rsi
0x180046f6b  pop     rbp
0x180046f6c  retn
```
