# CTDCArr::setVariant(__int64,__int64,OSPFORMAT,tagVARIANT)

- ea: `0x18000dc40`
- end: `0x18000dd6b`
- name: `?setVariant@CTDCArr@@UEAAJ_J0W4OSPFORMAT@@UtagVARIANT@@@Z`
- size: `299`
- prototype: `__int64 __fastcall(CTDCArr *__hidden this, __int64, __int64, enum OSPFORMAT, VARIANTARG *pvargSrc)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000dc40`
- `0x180015010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18000dcfc`
- `OLEAUT32!__imp_VariantClear` at `0x18000dcfc`
- `OLEAUT32!__imp_VariantCopy` at `0x18000dce0`
- `OLEAUT32!__imp_VariantCopy` at `0x18000dce0`
- `OLEAUT32!__imp_VarBstrFromBool` at `0x18000dd15`
- `OLEAUT32!__imp_VarBstrFromBool` at `0x18000dd15`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x18000dd2f`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x18000dd2f`

## pseudocode

```c
HRESULT __fastcall CTDCArr::setVariant(CTDCArr *this, int a2, int a3, unsigned int a4, VARIANTARG *pvargSrc)
{
  __int64 v8; // rbp
  __int64 v9; // r14
  __int64 v10; // rcx
  HRESULT result; // eax
  VARIANTARG *v12; // r14
  VARTYPE vt; // ax
  __int64 v14; // rcx

  if ( a2 < 0 || a2 > *((_DWORD *)this + 27) || a3 < 1 || a3 > *((_DWORD *)this + 28) || a4 > 2 )
    return -2147024809;
  v8 = *((_QWORD *)this + 22);
  v9 = **(_QWORD **)(*((_QWORD *)this + 19) + 8LL * a2);
  v10 = *((_QWORD *)this + 2);
  if ( !v10 || (result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 40LL))(v10), result >= 0) )
  {
    v12 = (VARIANTARG *)(v9 + 24 * (a3 - 1LL));
    vt = *(_WORD *)(v8 + 8LL * a3 - 8);
    if ( pvargSrc->vt == vt )
    {
      result = VariantCopy(v12, pvargSrc);
    }
    else if ( pvargSrc->vt == 11 && vt == 8 )
    {
      VariantClear(v12);
      v12->vt = 8;
      result = VarBstrFromBool(pvargSrc->iVal, *((_DWORD *)this + 10), 0, &v12->bstrVal);
    }
    else
    {
      result = VariantChangeTypeEx(v12, pvargSrc, *((_DWORD *)this + 10), 0, vt);
    }
    if ( result >= 0 )
    {
      v14 = *((_QWORD *)this + 2);
      if ( v14 )
        result = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v14 + 48LL))(
                   v14,
                   (unsigned int)a2,
                   (unsigned int)a3);
    }
    *((_BYTE *)this + 48) = 1;
  }
  return result;
}

```

## disassembly

```asm
0x18000dc40  push    rbx
0x18000dc42  push    rbp
0x18000dc43  push    rsi
0x18000dc44  push    rdi
0x18000dc45  push    r14
0x18000dc47  push    r15
0x18000dc49  sub     rsp, 38h
0x18000dc4d  mov     rdi, r8
0x18000dc50  mov     rsi, rdx
0x18000dc53  mov     rbx, rcx
0x18000dc56  test    edx, edx
0x18000dc58  js      loc_18000DD59
0x18000dc5e  cmp     esi, [rcx+6Ch]
0x18000dc61  jg      loc_18000DD59
0x18000dc67  cmp     edi, 1
0x18000dc6a  jl      loc_18000DD59
0x18000dc70  cmp     edi, [rcx+70h]
0x18000dc73  jg      loc_18000DD59
0x18000dc79  cmp     r9d, 2
0x18000dc7d  ja      loc_18000DD59
0x18000dc83  mov     rax, [rbx+98h]
0x18000dc8a  mov     rbp, [rbx+0B0h]
0x18000dc91  movsxd  rcx, esi
0x18000dc94  mov     rcx, [rax+rcx*8]
0x18000dc98  mov     r14, [rcx]
0x18000dc9b  mov     rcx, [rbx+10h]
0x18000dc9f  test    rcx, rcx
0x18000dca2  jz      short loc_18000DCB8
0x18000dca4  mov     rax, [rcx]
0x18000dca7  mov     rax, [rax+28h]
0x18000dcab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dcb0  test    eax, eax
0x18000dcb2  js      loc_18000DD5E
0x18000dcb8  mov     r15, [rsp+68h+pvargSrc]
0x18000dcc0  movsxd  rdx, edi
0x18000dcc3  lea     rax, [rdx-1]
0x18000dcc7  lea     rax, [rax+rax*2]
0x18000dccb  lea     r14, [r14+rax*8]
0x18000dccf  movzx   eax, word ptr [rbp+rdx*8-8]
0x18000dcd4  cmp     [r15], ax
0x18000dcd8  jnz     short loc_18000DCE8
0x18000dcda  mov     rdx, r15; pvargSrc
0x18000dcdd  mov     rcx, r14; pvargDest
0x18000dce0  call    cs:__imp_VariantCopy
0x18000dce6  jmp     short loc_18000DD35
0x18000dce8  cmp     word ptr [r15], 0Bh
0x18000dced  jnz     short loc_18000DD1D
0x18000dcef  mov     ebp, 8
0x18000dcf4  cmp     ax, bp
0x18000dcf7  jnz     short loc_18000DD1D
0x18000dcf9  mov     rcx, r14; pvarg
0x18000dcfc  call    cs:__imp_VariantClear
0x18000dd02  mov     [r14], bp
0x18000dd06  lea     r9, [r14+8]; pbstrOut
0x18000dd0a  mov     edx, [rbx+28h]; lcid
0x18000dd0d  xor     r8d, r8d; dwFlags
0x18000dd10  movzx   ecx, word ptr [r15+8]; boolIn
0x18000dd15  call    cs:__imp_VarBstrFromBool
0x18000dd1b  jmp     short loc_18000DD35
0x18000dd1d  mov     r8d, [rbx+28h]; lcid
0x18000dd21  xor     r9d, r9d; wFlags
0x18000dd24  mov     rdx, r15; pvarSrc
0x18000dd27  mov     [rsp+68h+vt], ax; vt
0x18000dd2c  mov     rcx, r14; pvargDest
0x18000dd2f  call    cs:__imp_VariantChangeTypeEx
0x18000dd35  test    eax, eax
0x18000dd37  js      short loc_18000DD53
0x18000dd39  mov     rcx, [rbx+10h]
0x18000dd3d  test    rcx, rcx
0x18000dd40  jz      short loc_18000DD53
0x18000dd42  mov     rax, [rcx]
0x18000dd45  mov     r8d, edi
0x18000dd48  mov     edx, esi
0x18000dd4a  mov     rax, [rax+30h]
0x18000dd4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd53  mov     byte ptr [rbx+30h], 1
0x18000dd57  jmp     short loc_18000DD5E
0x18000dd59  mov     eax, 80070057h
0x18000dd5e  add     rsp, 38h
0x18000dd62  pop     r15
0x18000dd64  pop     r14
0x18000dd66  pop     rdi
0x18000dd67  pop     rsi
0x18000dd68  pop     rbp
0x18000dd69  pop     rbx
0x18000dd6a  retn
```
