# VbsArray(VAR *,int,VAR *)

- ea: `0x180073ea0`
- end: `0x180073f5d`
- name: `?VbsArray@@YAJPEAVVAR@@H0@Z`
- size: `189`
- prototype: `__int64 __fastcall(struct VAR *, int, struct VAR *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180002e60`
- `0x180019650`
- `0x1800261b8`
- `0x180073ea0`

## import_xrefs

- `OLEAUT32!__imp_VariantCopyInd` at `0x180073ef7`
- `OLEAUT32!__imp_VariantCopyInd` at `0x180073ef7`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180073f28`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180073f28`

## pseudocode

```c
__int64 __fastcall VbsArray(struct VAR *a1, int a2, struct VAR *a3)
{
  struct tagSAFEARRAY *OneDim; // rax
  SAFEARRAY *v7; // rsi
  HRESULT v8; // ebx
  VARIANT *pvData; // r15
  int i; // edi
  const VARIANTARG *v11; // rax
  struct VAR *v12; // rax
  __int64 result; // rax

  *(_WORD *)a1 = 1;
  OneDim = psaMakeOneDim(a2);
  v7 = OneDim;
  if ( OneDim )
  {
    pvData = (VARIANT *)OneDim->pvData;
    for ( i = a2 - 1; i >= 0; --i )
    {
      v11 = (const VARIANTARG *)VAR::PvarCutAll(a3);
      v8 = VariantCopyInd(&pvData[i], v11);
      if ( v8 < 0 )
        goto LABEL_9;
      a3 = (struct VAR *)((char *)a3 + 24);
    }
    v12 = PvarAlloc();
    *((_QWORD *)a1 + 1) = v12;
    if ( !v12 )
    {
      v8 = -2146828281;
LABEL_9:
      SafeArrayDestroy(v7);
      return (unsigned int)v8;
    }
    *(_WORD *)v12 = 8204;
    *(_QWORD *)(*((_QWORD *)a1 + 1) + 8LL) = v7;
    result = 0;
    *(_WORD *)a1 = 74;
  }
  else
  {
    return (unsigned int)-2146828281;
  }
  return result;
}

```

## disassembly

```asm
0x180073ea0  push    rbx
0x180073ea2  push    rbp
0x180073ea3  push    rsi
0x180073ea4  push    rdi
0x180073ea5  push    r12
0x180073ea7  push    r14
0x180073ea9  push    r15
0x180073eab  sub     rsp, 20h
0x180073eaf  mov     r14, rcx
0x180073eb2  mov     r12d, 1
0x180073eb8  mov     [rcx], r12w
0x180073ebc  mov     rbp, r8
0x180073ebf  mov     ecx, edx; int
0x180073ec1  mov     edi, edx
0x180073ec3  call    ?psaMakeOneDim@@YAPEAUtagSAFEARRAY@@J@Z; psaMakeOneDim(long)
0x180073ec8  mov     rsi, rax
0x180073ecb  test    rax, rax
0x180073ece  jnz     short loc_180073ED7
0x180073ed0  mov     ebx, 800A0007h
0x180073ed5  jmp     short loc_180073F34
0x180073ed7  mov     r15, [rax+10h]
0x180073edb  dec     edi
0x180073edd  test    edi, edi
0x180073edf  js      short loc_180073F12
0x180073ee1  mov     rcx, rbp; this
0x180073ee4  call    ?PvarCutAll@VAR@@QEAAPEAV1@XZ; VAR::PvarCutAll(void)
0x180073ee9  mov     rdx, rax; pvargSrc
0x180073eec  movsxd  rax, edi
0x180073eef  lea     rcx, [rax+rax*2]
0x180073ef3  lea     rcx, [r15+rcx*8]; pvarDest
0x180073ef7  call    cs:__imp_VariantCopyInd
0x180073efe  nop     dword ptr [rax+rax+00h]
0x180073f03  mov     ebx, eax
0x180073f05  test    eax, eax
0x180073f07  js      short loc_180073F25
0x180073f09  add     rbp, 18h
0x180073f0d  sub     edi, r12d
0x180073f10  jmp     short loc_180073EDD
0x180073f12  call    ?PvarAlloc@@YAPEAVVAR@@XZ; PvarAlloc(void)
0x180073f17  mov     [r14+8], rax
0x180073f1b  test    rax, rax
0x180073f1e  jnz     short loc_180073F38
0x180073f20  mov     ebx, 800A0007h
0x180073f25  mov     rcx, rsi; psa
0x180073f28  call    cs:__imp_SafeArrayDestroy
0x180073f2f  nop     dword ptr [rax+rax+00h]
0x180073f34  mov     eax, ebx
0x180073f36  jmp     short loc_180073F4D
0x180073f38  mov     word ptr [rax], 200Ch
0x180073f3d  mov     rax, [r14+8]
0x180073f41  mov     [rax+8], rsi
0x180073f45  xor     eax, eax
0x180073f47  mov     word ptr [r14], 4Ah ; 'J'
0x180073f4d  add     rsp, 20h
0x180073f51  pop     r15
0x180073f53  pop     r14
0x180073f55  pop     r12
0x180073f57  pop     rdi
0x180073f58  pop     rsi
0x180073f59  pop     rbp
0x180073f5a  pop     rbx
0x180073f5b  retn
```
