# VbsArray(VAR *,int,VAR *)

- ea: `0x180071970`
- end: `0x180071a20`
- name: `?VbsArray@@YAJPEAVVAR@@H0@Z`
- size: `176`
- prototype: `int(struct VAR *, int, struct VAR *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18001bd20`
- `0x18001f2b0`
- `0x180036c90`
- `0x180071970`

## import_xrefs

- `OLEAUT32!__imp_VariantCopyInd` at `0x1800719c7`
- `OLEAUT32!__imp_VariantCopyInd` at `0x1800719c7`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800719f2`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800719f2`

## pseudocode

```c
__int64 __fastcall VbsArray(struct VAR *a1, ULONG a2, struct VAR *a3)
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
0x180071970  push    rbx
0x180071972  push    rbp
0x180071973  push    rsi
0x180071974  push    rdi
0x180071975  push    r12
0x180071977  push    r14
0x180071979  push    r15
0x18007197b  sub     rsp, 20h
0x18007197f  mov     r14, rcx
0x180071982  mov     r12d, 1
0x180071988  mov     [rcx], r12w
0x18007198c  mov     rbp, r8
0x18007198f  mov     ecx, edx; int
0x180071991  mov     edi, edx
0x180071993  call    ?psaMakeOneDim@@YAPEAUtagSAFEARRAY@@J@Z; psaMakeOneDim(long)
0x180071998  mov     rsi, rax
0x18007199b  test    rax, rax
0x18007199e  jnz     short loc_1800719A7
0x1800719a0  mov     ebx, 800A0007h
0x1800719a5  jmp     short loc_1800719F8
0x1800719a7  mov     r15, [rax+10h]
0x1800719ab  dec     edi
0x1800719ad  test    edi, edi
0x1800719af  js      short loc_1800719DC
0x1800719b1  mov     rcx, rbp; this
0x1800719b4  call    ?PvarCutAll@VAR@@QEAAPEAV1@XZ; VAR::PvarCutAll(void)
0x1800719b9  mov     rdx, rax; pvargSrc
0x1800719bc  movsxd  rax, edi
0x1800719bf  lea     rcx, [rax+rax*2]
0x1800719c3  lea     rcx, [r15+rcx*8]; pvarDest
0x1800719c7  call    cs:__imp_VariantCopyInd
0x1800719cd  mov     ebx, eax
0x1800719cf  test    eax, eax
0x1800719d1  js      short loc_1800719EF
0x1800719d3  add     rbp, 18h
0x1800719d7  sub     edi, r12d
0x1800719da  jmp     short loc_1800719AD
0x1800719dc  call    ?PvarAlloc@@YAPEAVVAR@@XZ; PvarAlloc(void)
0x1800719e1  mov     [r14+8], rax
0x1800719e5  test    rax, rax
0x1800719e8  jnz     short loc_1800719FC
0x1800719ea  mov     ebx, 800A0007h
0x1800719ef  mov     rcx, rsi; psa
0x1800719f2  call    cs:__imp_SafeArrayDestroy
0x1800719f8  mov     eax, ebx
0x1800719fa  jmp     short loc_180071A11
0x1800719fc  mov     word ptr [rax], 200Ch
0x180071a01  mov     rax, [r14+8]
0x180071a05  mov     [rax+8], rsi
0x180071a09  xor     eax, eax
0x180071a0b  mov     word ptr [r14], 4Ah ; 'J'
0x180071a11  add     rsp, 20h
0x180071a15  pop     r15
0x180071a17  pop     r14
0x180071a19  pop     r12
0x180071a1b  pop     rdi
0x180071a1c  pop     rsi
0x180071a1d  pop     rbp
0x180071a1e  pop     rbx
0x180071a1f  retn
```
