# VAR::Clear(void)

- ea: `0x18001ed10`
- end: `0x18001eee7`
- name: `?Clear@VAR@@QEAAJXZ`
- size: `471`
- prototype: `__int64 __fastcall(VAR *__hidden this)`
- caller_count: `26`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180001cb0`
- `0x1800033b0`
- `0x180003c40`
- `0x180003f00`
- `0x180004400`
- `0x180006490`
- `0x180013d7c`
- `0x18001b5f0`
- `0x18001b9e0`
- `0x18001cb70`
- `0x18001e410`
- `0x18001f0f0`
- `0x1800252c0`
- `0x18002d230`
- `0x18002d710`
- `0x1800302d4`
- `0x180031e20`
- `0x180036018`
- `0x18003aa20`
- `0x18003b1b0`
- `0x180042a10`
- `0x18005f1bc`
- `0x18006aca0`
- `0x18006e88c`
- `0x18006fe80`
- `0x180077f90`

## callees

- `0x1800019d4`
- `0x180001a30`
- `0x18001ed10`
- `0x18004237c`
- `0x18004686c`
- `0x180079490`
- `0x18007a010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18001ed90`
- `OLEAUT32!__imp_VariantClear` at `0x18001ee4f`
- `OLEAUT32!__imp_VariantClear` at `0x18001ed90`
- `OLEAUT32!__imp_VariantClear` at `0x18001ee4f`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18001ee35`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18001ee35`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18001edc5`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18001edc5`

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
0x18001ed10  push    rbx
0x18001ed12  push    rbp
0x18001ed13  push    rsi
0x18001ed14  push    rdi
0x18001ed15  sub     rsp, 48h
0x18001ed19  mov     rax, cs:__security_cookie
0x18001ed20  xor     rax, rsp
0x18001ed23  mov     [rsp+68h+var_30], rax
0x18001ed28  movzx   eax, word ptr [rcx]
0x18001ed2b  mov     rbx, rcx
0x18001ed2e  cmp     eax, 4Eh ; 'N'
0x18001ed31  jz      loc_18001EDC1
0x18001ed37  xor     edi, edi
0x18001ed39  cmp     eax, 4Fh ; 'O'
0x18001ed3c  ja      loc_18001EDF5
0x18001ed42  jz      loc_18001EE75
0x18001ed48  mov     edx, eax
0x18001ed4a  sub     edx, 49h ; 'I'
0x18001ed4d  jz      loc_18001EECA
0x18001ed53  sub     edx, 3
0x18001ed56  jz      loc_18001EE75
0x18001ed5c  cmp     edx, 1
0x18001ed5f  jz      loc_18001EE8A
0x18001ed65  lea     ecx, [rax-8]
0x18001ed68  cmp     cx, 40h ; '@'
0x18001ed6c  jbe     short loc_18001ED73
0x18001ed6e  cmp     eax, 51h ; 'Q'
0x18001ed71  jb      short loc_18001EDD7
0x18001ed73  movups  xmm0, xmmword ptr [rbx]
0x18001ed76  lea     rcx, [rsp+68h+pvarg]; pvarg
0x18001ed7b  xor     eax, eax
0x18001ed7d  movsd   xmm1, qword ptr [rbx+10h]
0x18001ed82  movups  xmmword ptr [rsp+68h+pvarg], xmm0
0x18001ed87  mov     [rbx], ax
0x18001ed8a  movsd   qword ptr [rsp+68h+pvarg+10h], xmm1
0x18001ed90  call    cs:__imp_VariantClear
0x18001ed97  nop     dword ptr [rax+rax+00h]
0x18001ed9c  mov     edi, eax
0x18001ed9e  test    eax, eax
0x18001eda0  js      short loc_18001EDAC
0x18001eda2  cmp     word ptr [rbx], 0
0x18001eda6  jnz     loc_18001EE67
0x18001edac  movups  xmm0, xmmword ptr [rsp+68h+pvarg]
0x18001edb1  movsd   xmm1, qword ptr [rsp+68h+pvarg+10h]
0x18001edb7  movups  xmmword ptr [rbx], xmm0
0x18001edba  movsd   qword ptr [rbx+10h], xmm1
0x18001edbf  jmp     short loc_18001EDD3
0x18001edc1  mov     rcx, [rcx+8]; psa
0x18001edc5  call    cs:__imp_SafeArrayUnlock
0x18001edcc  nop     dword ptr [rax+rax+00h]
0x18001edd1  mov     edi, eax
0x18001edd3  test    edi, edi
0x18001edd5  js      short loc_18001EDDC
0x18001edd7  xor     eax, eax
0x18001edd9  mov     [rbx], ax
0x18001eddc  mov     eax, edi
0x18001edde  mov     rcx, [rsp+68h+var_30]
0x18001ede3  xor     rcx, rsp; StackCookie
0x18001ede6  call    __security_check_cookie
0x18001edeb  add     rsp, 48h
0x18001edef  pop     rdi
0x18001edf0  pop     rsi
0x18001edf1  pop     rbp
0x18001edf2  pop     rbx
0x18001edf3  retn
0x18001edf5  cmp     eax, 50h ; 'P'
0x18001edf8  jz      loc_18001EEA8
0x18001edfe  mov     ebp, 600Ch
0x18001ee03  cmp     eax, ebp
0x18001ee05  jnz     loc_18001ED65
0x18001ee0b  mov     rcx, [rcx+8]
0x18001ee0f  lea     rax, [rbx+10h]
0x18001ee13  cmp     rcx, rax
0x18001ee16  jnz     short loc_18001EDD7
0x18001ee18  cmp     [rcx], rdi
0x18001ee1b  jz      short loc_18001EDD7
0x18001ee1d  xor     eax, eax
0x18001ee1f  mov     [rbx], ax
0x18001ee22  mov     rax, [rcx]
0x18001ee25  mov     ecx, 0FFFDh
0x18001ee2a  and     [rax+2], cx
0x18001ee2e  mov     rcx, [rbx+8]
0x18001ee32  mov     rcx, [rcx]; psa
0x18001ee35  call    cs:__imp_SafeArrayDestroy
0x18001ee3c  nop     dword ptr [rax+rax+00h]
0x18001ee41  mov     esi, eax
0x18001ee43  cmp     [rbx], di
0x18001ee46  jz      loc_18001EED9
0x18001ee4c  mov     rcx, rbx; pvarg
0x18001ee4f  call    cs:__imp_VariantClear
0x18001ee56  nop     dword ptr [rax+rax+00h]
0x18001ee5b  mov     edi, eax
0x18001ee5d  test    eax, eax
0x18001ee5f  js      loc_18001EDDC
0x18001ee65  jmp     short loc_18001EEE0
0x18001ee67  mov     rdx, rbx; struct VAR *
0x18001ee6a  mov     ecx, 8000FFFFh; int
0x18001ee6f  call    ?RaiseErrorHr@@YAXJPEAVVAR@@PEBGJ@Z; RaiseErrorHr(long,VAR *,ushort const *,long)
0x18001ee75  mov     rcx, [rcx+8]
0x18001ee79  mov     rax, [rcx]
0x18001ee7c  mov     rax, [rax+8]
0x18001ee80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee85  jmp     loc_18001EDD7
0x18001ee8a  mov     rcx, [rcx+8]
0x18001ee8e  test    rcx, rcx
0x18001ee91  jz      loc_18001EDD7
0x18001ee97  mov     rax, [rcx]
0x18001ee9a  mov     rax, [rax+10h]
0x18001ee9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eea3  jmp     loc_18001EDD7
0x18001eea8  mov     rsi, [rcx+8]
0x18001eeac  test    rsi, rsi
0x18001eeaf  jz      loc_18001EDD7
0x18001eeb5  mov     rcx, rsi; this
0x18001eeb8  call    ??1PropertyFuncs@VAR@@QEAA@XZ; VAR::PropertyFuncs::~PropertyFuncs(void)
0x18001eebd  mov     rcx, rsi; Block
0x18001eec0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001eec5  jmp     loc_18001EDD7
0x18001eeca  mov     word ptr [rcx], 9
0x18001eecf  call    ?VariantClearWrapper@VAR@@QEAAJXZ; VAR::VariantClearWrapper(void)
0x18001eed4  jmp     loc_18001EDD1
0x18001eed9  test    esi, esi
0x18001eedb  jns     short loc_18001EEE0
0x18001eedd  mov     [rbx], bp
0x18001eee0  mov     edi, esi
0x18001eee2  jmp     loc_18001EDD3
```
