# CTDCArr::getVariant(__int64,__int64,OSPFORMAT,tagVARIANT *)

- ea: `0x18000d8a0`
- end: `0x18000d99e`
- name: `?getVariant@CTDCArr@@UEAAJ_J0W4OSPFORMAT@@PEAUtagVARIANT@@@Z`
- size: `254`
- prototype: `__int64 __fastcall(CTDCArr *__hidden this, __int64, __int64, enum OSPFORMAT, VARIANTARG *pvargDest)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000d8a0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000d980`
- `OLEAUT32!__imp_SysAllocString` at `0x18000d980`
- `OLEAUT32!__imp_VariantClear` at `0x18000d928`
- `OLEAUT32!__imp_VariantClear` at `0x18000d970`
- `OLEAUT32!__imp_VariantClear` at `0x18000d928`
- `OLEAUT32!__imp_VariantClear` at `0x18000d970`
- `OLEAUT32!__imp_VariantCopy` at `0x18000d900`
- `OLEAUT32!__imp_VariantCopy` at `0x18000d900`
- `OLEAUT32!__imp_VarBstrFromBool` at `0x18000d944`
- `OLEAUT32!__imp_VarBstrFromBool` at `0x18000d944`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x18000d961`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x18000d961`

## pseudocode

```c
__int64 __fastcall CTDCArr::getVariant(CTDCArr *this, int a2, int a3, enum OSPFORMAT a4, VARIANTARG *pvargDest)
{
  __int64 v6; // rsi
  unsigned int v7; // ebx
  HRESULT v8; // eax

  if ( a2 < 0 || a2 > *((_DWORD *)this + 27) || a3 < 1 || a3 > *((_DWORD *)this + 28) )
    return (unsigned int)-2147024809;
  v6 = **(_QWORD **)(*((_QWORD *)this + 19) + 8LL * a2) + 24LL * a3;
  if ( a4 == OSPFORMAT_RAW )
    return (unsigned int)VariantCopy(pvargDest, (const VARIANTARG *)(v6 - 24));
  if ( (unsigned int)(a4 - 1) > 1 )
    return (unsigned int)-2147024809;
  if ( *(_WORD *)(v6 - 24) == 11 )
  {
    VariantClear(pvargDest);
    pvargDest->vt = 8;
    v8 = VarBstrFromBool(*(_WORD *)(v6 - 16), *((_DWORD *)this + 10), 0, &pvargDest->bstrVal);
  }
  else
  {
    v8 = VariantChangeTypeEx(pvargDest, (const VARIANTARG *)(v6 - 24), *((_DWORD *)this + 10), 0, 8u);
  }
  v7 = v8;
  if ( v8 < 0 )
  {
    VariantClear(pvargDest);
    pvargDest->vt = 8;
    pvargDest->llVal = (LONGLONG)SysAllocString(L"#Error");
  }
  return v7;
}

```

## disassembly

```asm
0x18000d8a0  push    rbx
0x18000d8a2  push    rbp
0x18000d8a3  push    rsi
0x18000d8a4  push    rdi
0x18000d8a5  push    r14
0x18000d8a7  sub     rsp, 30h
0x18000d8ab  mov     rbx, rcx
0x18000d8ae  test    edx, edx
0x18000d8b0  js      loc_18000D98C
0x18000d8b6  cmp     edx, [rcx+6Ch]
0x18000d8b9  jg      loc_18000D98C
0x18000d8bf  cmp     r8d, 1
0x18000d8c3  jl      loc_18000D98C
0x18000d8c9  cmp     r8d, [rcx+70h]
0x18000d8cd  jg      loc_18000D98C
0x18000d8d3  mov     rax, [rbx+98h]
0x18000d8da  movsxd  rcx, edx
0x18000d8dd  mov     rdx, [rax+rcx*8]
0x18000d8e1  movsxd  rax, r8d
0x18000d8e4  lea     rcx, [rax+rax*2]
0x18000d8e8  mov     rax, [rdx]
0x18000d8eb  lea     rsi, [rax+rcx*8]
0x18000d8ef  test    r9d, r9d
0x18000d8f2  jnz     short loc_18000D90D
0x18000d8f4  mov     rcx, [rsp+58h+pvargDest]; pvargDest
0x18000d8fc  lea     rdx, [rsi-18h]; pvargSrc
0x18000d900  call    cs:__imp_VariantCopy
0x18000d906  mov     ebx, eax
0x18000d908  jmp     loc_18000D991
0x18000d90d  lea     eax, [r9-1]
0x18000d911  cmp     eax, 1
0x18000d914  ja      short loc_18000D98C
0x18000d916  cmp     word ptr [rsi-18h], 0Bh
0x18000d91b  mov     rdi, [rsp+58h+pvargDest]
0x18000d923  mov     rcx, rdi; pvargDest
0x18000d926  jnz     short loc_18000D94C
0x18000d928  call    cs:__imp_VariantClear
0x18000d92e  mov     ebp, 8
0x18000d933  lea     r9, [rdi+8]; pbstrOut
0x18000d937  mov     [rdi], bp
0x18000d93a  xor     r8d, r8d; dwFlags
0x18000d93d  mov     edx, [rbx+28h]; lcid
0x18000d940  movzx   ecx, word ptr [rsi-10h]; boolIn
0x18000d944  call    cs:__imp_VarBstrFromBool
0x18000d94a  jmp     short loc_18000D967
0x18000d94c  mov     r8d, [rbx+28h]; lcid
0x18000d950  lea     rdx, [rsi-18h]; pvarSrc
0x18000d954  mov     ebp, 8
0x18000d959  xor     r9d, r9d; wFlags
0x18000d95c  mov     [rsp+58h+vt], bp; vt
0x18000d961  call    cs:__imp_VariantChangeTypeEx
0x18000d967  mov     ebx, eax
0x18000d969  test    eax, eax
0x18000d96b  jns     short loc_18000D991
0x18000d96d  mov     rcx, rdi; pvarg
0x18000d970  call    cs:__imp_VariantClear
0x18000d976  lea     rcx, aError; "#Error"
0x18000d97d  mov     [rdi], bp
0x18000d980  call    cs:__imp_SysAllocString
0x18000d986  mov     [rdi+8], rax
0x18000d98a  jmp     short loc_18000D991
0x18000d98c  mov     ebx, 80070057h
0x18000d991  mov     eax, ebx
0x18000d993  add     rsp, 30h
0x18000d997  pop     r14
0x18000d999  pop     rdi
0x18000d99a  pop     rsi
0x18000d99b  pop     rbp
0x18000d99c  pop     rbx
0x18000d99d  retn
```
