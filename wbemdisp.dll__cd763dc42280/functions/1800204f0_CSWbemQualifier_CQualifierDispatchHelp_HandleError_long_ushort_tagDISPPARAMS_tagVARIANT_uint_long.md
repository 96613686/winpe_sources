# CSWbemQualifier::CQualifierDispatchHelp::HandleError(long,ushort,tagDISPPARAMS *,tagVARIANT *,uint *,long)

- ea: `0x1800204f0`
- end: `0x180020735`
- name: `?HandleError@CQualifierDispatchHelp@CSWbemQualifier@@UEAAJJGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAIJ@Z`
- size: `581`
- prototype: `__int64 __fastcall(CSWbemQualifier::CQualifierDispatchHelp *__hidden this, int, unsigned __int16, struct tagDISPPARAMS *, VARIANTARG *, unsigned int *, LONG rgIndices)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x1800204f0`
- `0x180024390`
- `0x180025aa4`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18002057a`
- `OLEAUT32!__imp_VariantInit` at `0x1800205bc`
- `OLEAUT32!__imp_VariantInit` at `0x180020603`
- `OLEAUT32!__imp_VariantInit` at `0x180020647`
- `OLEAUT32!__imp_VariantInit` at `0x18002057a`
- `OLEAUT32!__imp_VariantInit` at `0x1800205bc`
- `OLEAUT32!__imp_VariantInit` at `0x180020603`
- `OLEAUT32!__imp_VariantInit` at `0x180020647`
- `OLEAUT32!__imp_VariantClear` at `0x1800206da`
- `OLEAUT32!__imp_VariantClear` at `0x1800206fd`
- `OLEAUT32!__imp_VariantClear` at `0x180020707`
- `OLEAUT32!__imp_VariantClear` at `0x1800206da`
- `OLEAUT32!__imp_VariantClear` at `0x1800206fd`
- `OLEAUT32!__imp_VariantClear` at `0x180020707`
- `OLEAUT32!__imp_VariantCopy` at `0x180020654`
- `OLEAUT32!__imp_VariantCopy` at `0x180020654`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800205db`
- `OLEAUT32!__imp_VariantChangeType` at `0x18002067a`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800205db`
- `OLEAUT32!__imp_VariantChangeType` at `0x18002067a`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180020615`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180020615`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18002069c`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18002069c`

## pseudocode

```c
__int64 __fastcall CSWbemQualifier::CQualifierDispatchHelp::HandleError(
        CSWbemQualifier::CQualifierDispatchHelp *this,
        int a2,
        char a3,
        struct tagDISPPARAMS *a4,
        VARIANTARG *a5,
        unsigned int *a6,
        LONG rgIndices)
{
  unsigned int Element; // ebx
  int (__fastcall ***v10)(_QWORD, GUID *, __int64 *); // rcx
  __int16 v11; // r15
  VARTYPE AcceptableQualType; // ax
  __int64 v14; // [rsp+20h] [rbp-58h] BYREF
  VARIANTARG pvarg; // [rsp+28h] [rbp-50h] BYREF
  VARIANTARG pvarSrc; // [rsp+40h] [rbp-38h] BYREF
  VARIANTARG pvargDest; // [rsp+58h] [rbp-20h] BYREF

  Element = rgIndices;
  if ( a2 || rgIndices != -2147352559 || !a4->cArgs )
    return Element;
  v10 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 5);
  v14 = 0;
  v11 = a3 & 2;
  if ( (**v10)(v10, &IID_ISWbemQualifier, &v14) >= 0 )
  {
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    if ( (*(int (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v14 + 56LL))(v14, &pvarg) < 0
      || (pvarg.vt & 0x2000) == 0 )
    {
      goto LABEL_25;
    }
    memset(&pvargDest, 0, sizeof(pvargDest));
    VariantInit(&pvargDest);
    if ( VariantChangeType(&pvargDest, &a4->rgvarg[v11 == 0], 0, 3u) )
    {
      Element = -2147352571;
      if ( a6 )
        *a6 = v11 == 0;
      goto LABEL_24;
    }
    rgIndices = pvargDest.lVal;
    if ( v11 )
    {
      if ( a4->cArgs == 1 )
      {
        VariantInit(a5);
        Element = SafeArrayGetElement(pvarg.parray, &rgIndices, a5);
LABEL_24:
        VariantClear(&pvargDest);
LABEL_25:
        VariantClear(&pvarg);
        goto LABEL_26;
      }
      goto LABEL_21;
    }
    if ( (a3 & 4) == 0 )
      goto LABEL_24;
    if ( a4->cArgs != 2 )
    {
LABEL_21:
      Element = -2147352562;
      goto LABEL_24;
    }
    memset(&pvarSrc, 0, sizeof(pvarSrc));
    VariantInit(&pvarSrc);
    if ( VariantCopy(&pvarSrc, a4->rgvarg) < 0 )
      goto LABEL_24;
    AcceptableQualType = GetAcceptableQualType(pvarSrc.vt);
    if ( !VariantChangeType(&pvarSrc, &pvarSrc, 0, AcceptableQualType) )
    {
      CheckArrayBounds(pvarg.parray, rgIndices);
      Element = SafeArrayPutElement(pvarg.parray, &rgIndices, &pvarSrc);
      if ( Element )
      {
LABEL_20:
        VariantClear(&pvarSrc);
        goto LABEL_24;
      }
      if ( (*(int (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v14 + 64LL))(v14, &pvarg) >= 0 )
      {
        Element = 0;
        goto LABEL_20;
      }
    }
    Element = -2147352571;
    if ( a6 )
      *a6 = 0;
    goto LABEL_20;
  }
LABEL_26:
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  return Element;
}

```

## disassembly

```asm
0x1800204f0  push    rbp
0x1800204f2  push    rbx
0x1800204f3  push    rsi
0x1800204f4  push    rdi
0x1800204f5  push    r12
0x1800204f7  push    r13
0x1800204f9  push    r14
0x1800204fb  push    r15
0x1800204fd  mov     rbp, rsp
0x180020500  sub     rsp, 78h
0x180020504  mov     ebx, [rbp+rgIndices]
0x180020507  xor     r12d, r12d
0x18002050a  mov     rdi, r9
0x18002050d  movzx   r14d, r8w
0x180020511  test    edx, edx
0x180020513  jnz     loc_180020722
0x180020519  cmp     ebx, 80020011h
0x18002051f  jnz     loc_180020722
0x180020525  cmp     [r9+10h], r12d
0x180020529  jbe     loc_180020722
0x18002052f  mov     rcx, [rcx+28h]
0x180020533  lea     r13d, [r12+2]
0x180020538  movzx   r15d, r8w
0x18002053c  mov     [rbp+var_58], r12
0x180020540  and     r15w, r13w
0x180020544  lea     r8, [rbp+var_58]
0x180020548  mov     esi, r12d
0x18002054b  lea     rdx, IID_ISWbemQualifier
0x180020552  mov     rax, [rcx]
0x180020555  setz    sil
0x180020559  mov     rax, [rax]
0x18002055c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020561  test    eax, eax
0x180020563  js      loc_18002070D
0x180020569  xorps   xmm0, xmm0
0x18002056c  lea     rcx, [rbp+pvarg]; pvarg
0x180020570  xor     eax, eax
0x180020572  movups  xmmword ptr [rbp+pvarg], xmm0
0x180020576  mov     qword ptr [rbp+pvarg+10h], rax
0x18002057a  call    cs:__imp_VariantInit
0x180020580  mov     rcx, [rbp+var_58]
0x180020584  lea     rdx, [rbp+pvarg]
0x180020588  mov     rax, [rcx]
0x18002058b  mov     rax, [rax+38h]
0x18002058f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020594  test    eax, eax
0x180020596  js      loc_180020703
0x18002059c  mov     eax, 2000h
0x1800205a1  test    word ptr [rbp+pvarg], ax
0x1800205a5  jz      loc_180020703
0x1800205ab  xorps   xmm0, xmm0
0x1800205ae  lea     rcx, [rbp+pvargDest]; pvarg
0x1800205b2  xor     eax, eax
0x1800205b4  movups  xmmword ptr [rbp+pvargDest], xmm0
0x1800205b8  mov     qword ptr [rbp+pvargDest+10h], rax
0x1800205bc  call    cs:__imp_VariantInit
0x1800205c2  mov     eax, esi
0x1800205c4  lea     r9d, [r12+3]; vt
0x1800205c9  xor     r8d, r8d; wFlags
0x1800205cc  lea     rcx, [rax+rax*2]
0x1800205d0  mov     rax, [rdi]
0x1800205d3  lea     rdx, [rax+rcx*8]; pvarSrc
0x1800205d7  lea     rcx, [rbp+pvargDest]; pvargDest
0x1800205db  call    cs:__imp_VariantChangeType
0x1800205e1  test    eax, eax
0x1800205e3  jnz     loc_1800206E9
0x1800205e9  mov     eax, dword ptr [rbp+pvargDest+8]
0x1800205ec  mov     [rbp+rgIndices], eax
0x1800205ef  test    r15w, r15w
0x1800205f3  jz      short loc_180020622
0x1800205f5  cmp     dword ptr [rdi+10h], 1
0x1800205f9  jnz     loc_1800206E2
0x1800205ff  mov     rcx, [rbp+arg_20]; pvarg
0x180020603  call    cs:__imp_VariantInit
0x180020609  mov     r8, [rbp+arg_20]; pv
0x18002060d  lea     rdx, [rbp+rgIndices]; rgIndices
0x180020611  mov     rcx, qword ptr [rbp+pvarg+8]; psa
0x180020615  call    cs:__imp_SafeArrayGetElement
0x18002061b  mov     ebx, eax
0x18002061d  jmp     loc_1800206F9
0x180020622  test    r14b, 4
0x180020626  jz      loc_1800206F9
0x18002062c  cmp     [rdi+10h], r13d
0x180020630  jnz     loc_1800206E2
0x180020636  xorps   xmm0, xmm0
0x180020639  lea     rcx, [rbp+pvarSrc]; pvarg
0x18002063d  xor     eax, eax
0x18002063f  movups  xmmword ptr [rbp+pvarSrc], xmm0
0x180020643  mov     qword ptr [rbp+pvarSrc+10h], rax
0x180020647  call    cs:__imp_VariantInit
0x18002064d  mov     rdx, [rdi]; pvargSrc
0x180020650  lea     rcx, [rbp+pvarSrc]; pvargDest
0x180020654  call    cs:__imp_VariantCopy
0x18002065a  test    eax, eax
0x18002065c  js      loc_1800206F9
0x180020662  movzx   ecx, word ptr [rbp+pvarSrc]; unsigned __int16
0x180020666  call    ?GetAcceptableQualType@@YAGG@Z; GetAcceptableQualType(ushort)
0x18002066b  movzx   r9d, ax; vt
0x18002066f  lea     rdx, [rbp+pvarSrc]; pvarSrc
0x180020673  xor     r8d, r8d; wFlags
0x180020676  lea     rcx, [rbp+pvarSrc]; pvargDest
0x18002067a  call    cs:__imp_VariantChangeType
0x180020680  test    eax, eax
0x180020682  jnz     short loc_1800206C5
0x180020684  mov     edx, [rbp+rgIndices]; int
0x180020687  mov     rcx, qword ptr [rbp+pvarg+8]; psa
0x18002068b  call    ?CheckArrayBounds@@YAXPEAUtagSAFEARRAY@@J@Z; CheckArrayBounds(tagSAFEARRAY *,long)
0x180020690  mov     rcx, qword ptr [rbp+pvarg+8]; psa
0x180020694  lea     r8, [rbp+pvarSrc]; pv
0x180020698  lea     rdx, [rbp+rgIndices]; rgIndices
0x18002069c  call    cs:__imp_SafeArrayPutElement
0x1800206a2  mov     ebx, eax
0x1800206a4  test    eax, eax
0x1800206a6  jnz     short loc_1800206D6
0x1800206a8  mov     rcx, [rbp+var_58]
0x1800206ac  lea     rdx, [rbp+pvarg]
0x1800206b0  mov     rax, [rcx]
0x1800206b3  mov     rax, [rax+40h]
0x1800206b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800206bc  test    eax, eax
0x1800206be  js      short loc_1800206C5
0x1800206c0  mov     ebx, r12d
0x1800206c3  jmp     short loc_1800206D6
0x1800206c5  mov     rax, [rbp+arg_28]
0x1800206c9  mov     ebx, 80020005h
0x1800206ce  test    rax, rax
0x1800206d1  jz      short loc_1800206D6
0x1800206d3  mov     [rax], r12d
0x1800206d6  lea     rcx, [rbp+pvarSrc]; pvarg
0x1800206da  call    cs:__imp_VariantClear
0x1800206e0  jmp     short loc_1800206F9
0x1800206e2  mov     ebx, 8002000Eh
0x1800206e7  jmp     short loc_1800206F9
0x1800206e9  mov     rax, [rbp+arg_28]
0x1800206ed  mov     ebx, 80020005h
0x1800206f2  test    rax, rax
0x1800206f5  jz      short loc_1800206F9
0x1800206f7  mov     [rax], esi
0x1800206f9  lea     rcx, [rbp+pvargDest]; pvarg
0x1800206fd  call    cs:__imp_VariantClear
0x180020703  lea     rcx, [rbp+pvarg]; pvarg
0x180020707  call    cs:__imp_VariantClear
0x18002070d  mov     rcx, [rbp+var_58]
0x180020711  test    rcx, rcx
0x180020714  jz      short loc_180020722
0x180020716  mov     rax, [rcx]
0x180020719  mov     rax, [rax+10h]
0x18002071d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020722  mov     eax, ebx
0x180020724  add     rsp, 78h
0x180020728  pop     r15
0x18002072a  pop     r14
0x18002072c  pop     r13
0x18002072e  pop     r12
0x180020730  pop     rdi
0x180020731  pop     rsi
0x180020732  pop     rbx
0x180020733  pop     rbp
0x180020734  retn
```
