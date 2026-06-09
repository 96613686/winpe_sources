# VAR::Clear(void)

- ea: `0x180022b20`
- end: `0x180022cda`
- name: `?Clear@VAR@@QEAAJXZ`
- size: `442`
- prototype: `__int64 __fastcall(VAR *__hidden this)`
- caller_count: `26`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1800040d4`
- `0x1800046b0`
- `0x1800055b0`
- `0x180005e00`
- `0x1800060b0`
- `0x180006550`
- `0x1800083f0`
- `0x180019168`
- `0x180020a50`
- `0x180021160`
- `0x180021540`
- `0x180022f20`
- `0x180023ad0`
- `0x180028230`
- `0x18002b180`
- `0x18002d340`
- `0x180034b40`
- `0x1800385d0`
- `0x1800388b0`
- `0x1800392d0`
- `0x1800416cc`
- `0x18005d5f0`
- `0x180068b70`
- `0x18006c718`
- `0x18006dc90`
- `0x1800753c0`

## callees

- `0x180022b20`
- `0x1800280f4`
- `0x180028150`
- `0x180040cc4`
- `0x180045478`
- `0x1800767a0`
- `0x180077010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180022ba0`
- `OLEAUT32!__imp_VariantClear` at `0x180022c4c`
- `OLEAUT32!__imp_VariantClear` at `0x180022ba0`
- `OLEAUT32!__imp_VariantClear` at `0x180022c4c`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180022c38`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180022c38`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180022bcf`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180022bcf`

## pseudocode

```c
__int64 __fastcall VAR::Clear(VARIANTARG *this)
{
  unsigned int vt; // eax
  HRESULT v3; // edi
  IRecordInfo *pRecInfo; // xmm1_8
  const unsigned __int16 *v5; // r8
  int v6; // r9d
  IRecordInfo *v7; // xmm1_8
  HRESULT v8; // eax
  VAR *v10; // rcx
  HRESULT v11; // esi
  LONGLONG llVal; // rcx
  BSTR bstrVal; // rsi
  VARIANTARG pvarg; // [rsp+20h] [rbp-48h] BYREF

  vt = this->vt;
  if ( vt == 78 )
  {
    v8 = SafeArrayUnlock(this->parray);
    goto LABEL_13;
  }
  v3 = 0;
  if ( vt <= 0x4F )
  {
    if ( vt == 79 )
      goto LABEL_25;
    if ( vt != 73 )
    {
      if ( vt != 76 )
      {
        if ( vt == 77 )
        {
          llVal = this->llVal;
          if ( llVal )
            (*(void (__fastcall **)(LONGLONG))(*(_QWORD *)llVal + 16LL))(llVal);
          goto LABEL_15;
        }
        goto LABEL_7;
      }
LABEL_25:
      (*(void (__fastcall **)(LONGLONG))(*this->pllVal + 8))(this->llVal);
      goto LABEL_15;
    }
    this->vt = 9;
    v8 = VAR::VariantClearWrapper((VAR *)this);
LABEL_13:
    v3 = v8;
    goto LABEL_14;
  }
  if ( vt == 80 )
  {
    bstrVal = this->bstrVal;
    if ( bstrVal )
    {
      VAR::PropertyFuncs::~PropertyFuncs((VAR::PropertyFuncs *)this->llVal);
      operator delete(bstrVal);
    }
    goto LABEL_15;
  }
  if ( vt == 24588 )
  {
    v10 = (VAR *)this->llVal;
    if ( v10 != (VAR *)(&this->decVal + 1) || !*(_QWORD *)v10 )
      goto LABEL_15;
    this->vt = 0;
    *(_WORD *)(*(_QWORD *)v10 + 2LL) &= ~2u;
    v11 = SafeArrayDestroy(*this->pparray);
    if ( this->vt )
    {
      v3 = VariantClear(this);
      if ( v3 < 0 )
        return (unsigned int)v3;
    }
    else if ( v11 < 0 )
    {
      this->vt = 24588;
    }
    v3 = v11;
    goto LABEL_14;
  }
LABEL_7:
  if ( (unsigned __int16)(vt - 8) > 0x40u && vt < 0x51 )
    goto LABEL_15;
  pRecInfo = this->pRecInfo;
  *(_OWORD *)&pvarg.vt = *(_OWORD *)&this->vt;
  this->vt = 0;
  pvarg.pRecInfo = pRecInfo;
  v3 = VariantClear(&pvarg);
  if ( v3 >= 0 && this->vt )
    RaiseErrorHr(-2147418113, (struct VAR *)this, v5, v6);
  v7 = pvarg.pRecInfo;
  *(_OWORD *)&this->vt = *(_OWORD *)&pvarg.vt;
  this->pRecInfo = v7;
LABEL_14:
  if ( v3 >= 0 )
LABEL_15:
    this->vt = 0;
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180022b20  push    rbx
0x180022b22  push    rbp
0x180022b23  push    rsi
0x180022b24  push    rdi
0x180022b25  sub     rsp, 48h
0x180022b29  mov     rax, cs:__security_cookie
0x180022b30  xor     rax, rsp
0x180022b33  mov     [rsp+68h+var_30], rax
0x180022b38  movzx   eax, word ptr [rcx]
0x180022b3b  mov     rbx, rcx
0x180022b3e  cmp     eax, 4Eh ; 'N'
0x180022b41  jz      loc_180022BCB
0x180022b47  xor     edi, edi
0x180022b49  cmp     eax, 4Fh ; 'O'
0x180022b4c  ja      loc_180022BF8
0x180022b52  jz      loc_180022C68
0x180022b58  mov     edx, eax
0x180022b5a  sub     edx, 49h ; 'I'
0x180022b5d  jz      loc_180022CBD
0x180022b63  sub     edx, 3
0x180022b66  jz      loc_180022C68
0x180022b6c  cmp     edx, 1
0x180022b6f  jz      loc_180022C7D
0x180022b75  lea     ecx, [rax-8]
0x180022b78  cmp     cx, 40h ; '@'
0x180022b7c  jbe     short loc_180022B83
0x180022b7e  cmp     eax, 51h ; 'Q'
0x180022b81  jb      short loc_180022BDB
0x180022b83  movups  xmm0, xmmword ptr [rbx]
0x180022b86  lea     rcx, [rsp+68h+pvarg]; pvarg
0x180022b8b  xor     eax, eax
0x180022b8d  movsd   xmm1, qword ptr [rbx+10h]
0x180022b92  movups  xmmword ptr [rsp+68h+pvarg], xmm0
0x180022b97  mov     [rbx], ax
0x180022b9a  movsd   qword ptr [rsp+68h+pvarg+10h], xmm1
0x180022ba0  call    cs:__imp_VariantClear
0x180022ba6  mov     edi, eax
0x180022ba8  test    eax, eax
0x180022baa  js      short loc_180022BB6
0x180022bac  cmp     word ptr [rbx], 0
0x180022bb0  jnz     loc_180022C5A
0x180022bb6  movups  xmm0, xmmword ptr [rsp+68h+pvarg]
0x180022bbb  movsd   xmm1, qword ptr [rsp+68h+pvarg+10h]
0x180022bc1  movups  xmmword ptr [rbx], xmm0
0x180022bc4  movsd   qword ptr [rbx+10h], xmm1
0x180022bc9  jmp     short loc_180022BD7
0x180022bcb  mov     rcx, [rcx+8]; psa
0x180022bcf  call    cs:__imp_SafeArrayUnlock
0x180022bd5  mov     edi, eax
0x180022bd7  test    edi, edi
0x180022bd9  js      short loc_180022BE0
0x180022bdb  xor     eax, eax
0x180022bdd  mov     [rbx], ax
0x180022be0  mov     eax, edi
0x180022be2  mov     rcx, [rsp+68h+var_30]
0x180022be7  xor     rcx, rsp; StackCookie
0x180022bea  call    __security_check_cookie
0x180022bef  add     rsp, 48h
0x180022bf3  pop     rdi
0x180022bf4  pop     rsi
0x180022bf5  pop     rbp
0x180022bf6  pop     rbx
0x180022bf7  retn
0x180022bf8  cmp     eax, 50h ; 'P'
0x180022bfb  jz      loc_180022C9B
0x180022c01  mov     ebp, 600Ch
0x180022c06  cmp     eax, ebp
0x180022c08  jnz     loc_180022B75
0x180022c0e  mov     rcx, [rcx+8]
0x180022c12  lea     rax, [rbx+10h]
0x180022c16  cmp     rcx, rax
0x180022c19  jnz     short loc_180022BDB
0x180022c1b  cmp     [rcx], rdi
0x180022c1e  jz      short loc_180022BDB
0x180022c20  xor     eax, eax
0x180022c22  mov     [rbx], ax
0x180022c25  mov     rax, [rcx]
0x180022c28  mov     ecx, 0FFFDh
0x180022c2d  and     [rax+2], cx
0x180022c31  mov     rcx, [rbx+8]
0x180022c35  mov     rcx, [rcx]; psa
0x180022c38  call    cs:__imp_SafeArrayDestroy
0x180022c3e  mov     esi, eax
0x180022c40  cmp     [rbx], di
0x180022c43  jz      loc_180022CCC
0x180022c49  mov     rcx, rbx; pvarg
0x180022c4c  call    cs:__imp_VariantClear
0x180022c52  mov     edi, eax
0x180022c54  test    eax, eax
0x180022c56  js      short loc_180022BE0
0x180022c58  jmp     short loc_180022CD3
0x180022c5a  mov     rdx, rbx; struct VAR *
0x180022c5d  mov     ecx, 8000FFFFh; int
0x180022c62  call    ?RaiseErrorHr@@YAXJPEAVVAR@@PEBGJ@Z; RaiseErrorHr(long,VAR *,ushort const *,long)
0x180022c68  mov     rcx, [rcx+8]
0x180022c6c  mov     rax, [rcx]
0x180022c6f  mov     rax, [rax+8]
0x180022c73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022c78  jmp     loc_180022BDB
0x180022c7d  mov     rcx, [rcx+8]
0x180022c81  test    rcx, rcx
0x180022c84  jz      loc_180022BDB
0x180022c8a  mov     rax, [rcx]
0x180022c8d  mov     rax, [rax+10h]
0x180022c91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022c96  jmp     loc_180022BDB
0x180022c9b  mov     rsi, [rcx+8]
0x180022c9f  test    rsi, rsi
0x180022ca2  jz      loc_180022BDB
0x180022ca8  mov     rcx, rsi; this
0x180022cab  call    ??1PropertyFuncs@VAR@@QEAA@XZ; VAR::PropertyFuncs::~PropertyFuncs(void)
0x180022cb0  mov     rcx, rsi; Block
0x180022cb3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180022cb8  jmp     loc_180022BDB
0x180022cbd  mov     word ptr [rcx], 9
0x180022cc2  call    ?VariantClearWrapper@VAR@@QEAAJXZ; VAR::VariantClearWrapper(void)
0x180022cc7  jmp     loc_180022BD5
0x180022ccc  test    esi, esi
0x180022cce  jns     short loc_180022CD3
0x180022cd0  mov     [rbx], bp
0x180022cd3  mov     edi, esi
0x180022cd5  jmp     loc_180022BD7
```
