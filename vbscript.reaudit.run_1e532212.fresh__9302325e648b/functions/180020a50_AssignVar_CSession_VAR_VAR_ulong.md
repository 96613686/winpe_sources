# AssignVar(CSession *,VAR *,VAR *,ulong)

- ea: `0x180020a50`
- end: `0x180021065`
- name: `?AssignVar@@YAJPEAVCSession@@PEAVVAR@@1K@Z`
- size: `1557`
- prototype: `int(struct CSession *, struct VAR *, struct VAR *, unsigned int)`
- caller_count: `12`
- callee_count: `17`
- tags: `file_ops`

## callers

- `0x1800083f0`
- `0x180020060`
- `0x180021160`
- `0x180021540`
- `0x180023ad0`
- `0x18003a180`
- `0x180041e64`
- `0x18005c640`
- `0x180069914`
- `0x18006a92c`
- `0x18006abd0`
- `0x18006b020`

## callees

- `0x180020150`
- `0x1800203e0`
- `0x1800204f0`
- `0x18002055c`
- `0x180020a50`
- `0x180022b20`
- `0x1800280f4`
- `0x180028150`
- `0x180035154`
- `0x180035ef0`
- `0x18003b10c`
- `0x180040cc4`
- `0x180041c00`
- `0x180045478`
- `0x18007672e`
- `0x1800767a0`
- `0x180077010`

## import_xrefs

- `msvcrt!free` at `0x180020feb`
- `msvcrt!free` at `0x180020feb`
- `OLEAUT32!__imp_SysFreeString` at `0x180020fde`
- `OLEAUT32!__imp_SysFreeString` at `0x180020fde`
- `OLEAUT32!__imp_SysStringLen` at `0x180020f65`
- `OLEAUT32!__imp_SysStringLen` at `0x180020f65`
- `OLEAUT32!__imp_VariantClear` at `0x180020bf4`
- `OLEAUT32!__imp_VariantClear` at `0x180020cea`
- `OLEAUT32!__imp_VariantClear` at `0x180020bf4`
- `OLEAUT32!__imp_VariantClear` at `0x180020cea`
- `OLEAUT32!__imp_VariantCopyInd` at `0x180020b78`
- `OLEAUT32!__imp_VariantCopyInd` at `0x180020b78`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180020cd8`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180020cd8`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180020c20`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180020c20`
- `KERNEL32!GetUserDefaultLCID` at `0x180020f3a`
- `KERNEL32!GetUserDefaultLCID` at `0x180020f3a`

## pseudocode

```c
HRESULT __fastcall AssignVar(struct CSession *a1, VARIANTARG *a2, struct VAR **a3, char a4)
{
  struct VAR *v4; // rdi
  VARIANTARG *pvarVal; // rbx
  LONGLONG llVal; // rax
  int v8; // esi
  HRESULT v9; // eax
  __int128 v10; // xmm0
  HRESULT result; // eax
  __int64 v12; // rax
  HRESULT v13; // ebx
  __int16 v14; // ax
  IRecordInfo *pRecInfo; // xmm1_8
  __int128 v16; // xmm0
  LONGLONG v17; // rcx
  __int64 v18; // rdi
  __int64 v19; // rax
  int v20; // eax
  CScriptRuntime *v21; // rcx
  __int64 v22; // r14
  __int64 v23; // r15
  unsigned __int16 *VarName; // r12
  int v25; // eax
  OLECHAR *v26; // rcx
  signed int v27; // eax
  size_t v28; // rbx
  int v29; // r13d
  unsigned __int16 *v30; // rax
  unsigned __int16 *v31; // rsi
  size_t v32; // rdi
  size_t v33; // rbx
  VARIANTARG psa; // [rsp+40h] [rbp-49h] BYREF
  VARIANT pvarDest; // [rsp+58h] [rbp-31h] BYREF
  VARIANTARG pvarg; // [rsp+70h] [rbp-19h] BYREF
  __int128 v37; // [rsp+88h] [rbp-1h] BYREF
  __int64 v38; // [rsp+98h] [rbp+Fh]

  v38 = 0;
  v4 = (struct VAR *)a3;
  pvarVal = a2;
  v37 = 0;
  memset(&pvarDest, 0, sizeof(pvarDest));
  if ( a2->vt == 16396 )
    pvarVal = a2->pvarVal;
  if ( *(_WORD *)a3 == 16396 )
    v4 = a3[1];
  if ( pvarVal->vt == 24588 )
  {
    v18 = *((_QWORD *)a1 + 22);
    if ( !v18 )
      v18 = *((_QWORD *)a1 + 23) + 16LL;
    RuntimeScriptException::Free((RuntimeScriptException *)v18);
    *(_DWORD *)(v18 + 64) = -2147352571;
    *(_DWORD *)(v18 + 64) = MapHr(-2147352571);
    *(_QWORD *)(v18 + 56) = ExcepInfoDeferredFillIn;
    v19 = *((_QWORD *)a1 + 4);
    if ( v19 )
      v20 = *(_DWORD *)(v19 + 184);
    else
      LOWORD(v20) = GetUserDefaultLCID();
    *(_WORD *)(v18 + 10) = v20;
    v21 = (CScriptRuntime *)*((_QWORD *)a1 + 9);
    if ( v21 )
    {
      CScriptRuntime::RecordErrorContext(v21, (struct RuntimeScriptException *)v18);
      v21 = (CScriptRuntime *)*((_QWORD *)a1 + 9);
    }
    v22 = *((_QWORD *)a1 + 22);
    if ( !v22 )
      v22 = *((_QWORD *)a1 + 23) + 16LL;
    if ( v21 )
    {
      v23 = -1;
      VarName = CScriptRuntime::PszGetVarName(v21, pvarVal, 0, -1);
      if ( VarName )
      {
        (*(void (__fastcall **)(__int64))(v22 + 56))(v22 + 8);
        v26 = *(OLECHAR **)(v22 + 24);
        *(_QWORD *)(v22 + 56) = 0;
        if ( v26 )
        {
          v27 = SysStringLen(v26);
          v28 = v27;
          do
            ++v23;
          while ( VarName[v23] );
          v29 = v27 + v23;
          v30 = _SysAllocStringLen(0, v27 + (int)v23 + 4);
          v31 = v30;
          if ( v30 )
          {
            v32 = v28;
            v33 = v28;
            memcpy_0(v30, *(const void **)(v22 + 24), v33 * 2);
            *(_DWORD *)&v31[v33] = *(_DWORD *)L": '";
            v31[v33 + 2] = asc_180080F28[2];
            memcpy_0(&v31[v32 + 3], VarName, 2LL * (int)v23);
            v31[v29 + 3] = 39;
            SysFreeString(*(BSTR *)(v22 + 24));
            *(_QWORD *)(v22 + 24) = v31;
          }
        }
        free(VarName);
      }
    }
    return -2040119292;
  }
  if ( pvarVal != (VARIANTARG *)v4 && pvarVal->vt == 8204 )
  {
    llVal = pvarVal->llVal;
    if ( llVal )
    {
      if ( *(_DWORD *)(llVal + 8) )
        return CSession::RecordHr(a1, 10, (struct VAR *)pvarVal, 0, -1);
    }
  }
  if ( (a4 & 2) != 0 )
  {
    v14 = *(_WORD *)v4;
    if ( *(_WORD *)v4 == 74 )
    {
      v4 = (struct VAR *)*((_QWORD *)v4 + 1);
      v14 = *(_WORD *)v4;
    }
    if ( v14 != 9 && *(_WORD *)v4 != 13 )
      return CSession::RecordHr(a1, -2146827864, v4, 0, -1);
    if ( pvarVal == (VARIANTARG *)v4 )
      return 0;
    pRecInfo = pvarVal->pRecInfo;
    *(_OWORD *)&pvarg.vt = *(_OWORD *)&pvarVal->vt;
    v16 = *(_OWORD *)v4;
    pvarg.pRecInfo = pRecInfo;
    *(_OWORD *)&pvarVal->vt = v16;
    pvarVal->pRecInfo = (IRecordInfo *)*((_QWORD *)v4 + 2);
    v17 = pvarVal->llVal;
    if ( v17 )
      (*(void (__fastcall **)(LONGLONG))(*(_QWORD *)v17 + 8LL))(v17);
    result = VAR::Clear((VAR *)&pvarg);
    if ( result >= 0 )
      return 0;
    return result;
  }
  v8 = 0;
  if ( (a4 & 1) != 0 )
  {
    if ( *(_WORD *)v4 != 9 )
    {
      if ( *(_WORD *)v4 != 74 || **((_WORD **)v4 + 1) != 9 )
        goto LABEL_14;
      v4 = (struct VAR *)*((_QWORD *)v4 + 1);
    }
    if ( !*((_QWORD *)v4 + 1) )
      return -2146828197;
    result = VAR::InvokeByDispID(v4, a1, (int)a3, 3u, (struct VAR *)&v37, 0, 0);
    if ( result < 0 )
      return result;
    v4 = (struct VAR *)&v37;
  }
LABEL_14:
  psa = *pvarVal;
  switch ( *(_WORD *)v4 )
  {
    case 'J':
      v12 = *((_QWORD *)v4 + 1);
      *(_OWORD *)&pvarVal->vt = *(_OWORD *)v12;
      pvarVal->pRecInfo = *(IRecordInfo **)(v12 + 16);
      *(_WORD *)v12 = 0;
      break;
    case 'K':
      if ( v4 == (struct VAR *)pvarVal )
        return 0;
      *(_OWORD *)&pvarVal->vt = *(_OWORD *)v4;
      pvarVal->pRecInfo = (IRecordInfo *)*((_QWORD *)v4 + 2);
      break;
    case 'L':
    case 'O':
      if ( v4 == (struct VAR *)pvarVal )
        return 0;
      *(_OWORD *)&pvarVal->vt = *(_OWORD *)v4;
      pvarVal->pRecInfo = (IRecordInfo *)*((_QWORD *)v4 + 2);
      (**(void (__fastcall ***)(LONGLONG))pvarVal->llVal)(pvarVal->llVal);
      break;
    case 'P':
      if ( v4 == (struct VAR *)pvarVal )
        return 0;
      v25 = VAR::CopyProperty((VAR *)pvarVal, v4);
      if ( v25 < 0 )
        return v25;
      return v8;
    default:
      if ( v4 == (struct VAR *)pvarVal )
        return 0;
      pvarDest.vt = 0;
      v9 = VariantCopyInd(&pvarDest, (const VARIANTARG *)v4);
      if ( v9 < 0 )
        return CSession::RecordHr(a1, v9, v4, 0, -1);
      *pvarVal = pvarDest;
      break;
  }
  if ( psa.vt == 78 )
  {
    result = SafeArrayUnlock(psa.parray);
    goto LABEL_33;
  }
  if ( psa.vt <= 0x4Fu )
  {
    switch ( psa.vt )
    {
      case 'O':
        goto LABEL_71;
      case 'I':
        psa.vt = 9;
        result = VAR::VariantClearWrapper((VAR *)&psa);
        goto LABEL_33;
      case 'L':
LABEL_71:
        (*(void (__fastcall **)(LONGLONG))(*psa.pllVal + 8))(psa.llVal);
        return 0;
      case 'M':
        if ( psa.llVal )
          (*(void (__fastcall **)(LONGLONG))(*psa.pllVal + 16))(psa.llVal);
        return 0;
    }
    goto LABEL_28;
  }
  if ( psa.vt == 80 )
  {
    if ( psa.llVal )
    {
      VAR::PropertyFuncs::~PropertyFuncs((VAR::PropertyFuncs *)psa.llVal);
      operator delete(psa.bstrVal);
    }
    return 0;
  }
  if ( psa.vt != 24588 )
  {
LABEL_28:
    if ( (unsigned __int16)(psa.vt - 8) <= 0x40u || psa.vt >= 0x51u )
    {
      v10 = *(_OWORD *)&psa.vt;
      psa.vt = 0;
      *(_OWORD *)&pvarg.vt = v10;
      pvarg.pRecInfo = psa.pRecInfo;
      result = VariantClear(&pvarg);
      if ( result < 0 )
        return result;
LABEL_33:
      if ( result < 0 )
        return result;
    }
    return 0;
  }
  if ( psa.pvarVal != (VARIANT *)(&psa.decVal + 1) || !*psa.pllVal )
    return 0;
  psa.vt = 0;
  *(_WORD *)(*psa.pllVal + 2) &= ~2u;
  v13 = SafeArrayDestroy(*psa.pparray);
  if ( !psa.vt || (result = VariantClear(&psa), result >= 0) )
  {
    result = v13;
    goto LABEL_33;
  }
  return result;
}

```

## disassembly

```asm
0x180020a50  push    rbp
0x180020a52  push    rbx
0x180020a53  push    rdi
0x180020a54  push    r13
0x180020a56  push    r15
0x180020a58  lea     rbp, [rsp-37h]
0x180020a5d  sub     rsp, 0C0h
0x180020a64  mov     rax, cs:__security_cookie
0x180020a6b  xor     rax, rsp
0x180020a6e  mov     [rbp+57h+var_40], rax
0x180020a72  xor     eax, eax
0x180020a74  xorps   xmm0, xmm0
0x180020a77  mov     [rbp+57h+var_48], rax
0x180020a7b  xorps   xmm1, xmm1
0x180020a7e  mov     qword ptr [rbp+57h+pvarDest+10h], rax
0x180020a82  mov     rdi, r8
0x180020a85  mov     eax, 400Ch
0x180020a8a  mov     rbx, rdx
0x180020a8d  mov     r13, rcx
0x180020a90  movups  [rbp+57h+var_58], xmm0
0x180020a94  movups  xmmword ptr [rbp+57h+pvarDest], xmm1
0x180020a98  cmp     [rdx], ax
0x180020a9b  jz      loc_180020F31
0x180020aa1  cmp     [r8], ax
0x180020aa5  jz      loc_180020C13
0x180020aab  movzx   eax, word ptr [rbx]
0x180020aae  mov     r15d, 600Ch
0x180020ab4  mov     [rsp+0E0h+arg_18], rsi
0x180020abc  mov     [rsp+0E0h+var_30], r14
0x180020ac4  cmp     ax, r15w
0x180020ac8  jz      loc_180020D71
0x180020ace  cmp     rbx, rdi
0x180020ad1  jz      short loc_180020AF0
0x180020ad3  mov     ecx, 200Ch
0x180020ad8  cmp     ax, cx
0x180020adb  jnz     short loc_180020AF0
0x180020add  mov     rax, [rbx+8]
0x180020ae1  test    rax, rax
0x180020ae4  jz      short loc_180020AF0
0x180020ae6  cmp     dword ptr [rax+8], 0
0x180020aea  ja      loc_180020EBE
0x180020af0  test    r9b, 2
0x180020af4  jnz     loc_180020CFF
0x180020afa  xor     esi, esi
0x180020afc  mov     r14d, 9
0x180020b02  test    r9b, 1
0x180020b06  jz      short loc_180020B23
0x180020b08  movzx   eax, word ptr [rdi]
0x180020b0b  cmp     r14w, ax
0x180020b0f  jz      loc_180020C84
0x180020b15  mov     ecx, 4Ah ; 'J'
0x180020b1a  cmp     cx, ax
0x180020b1d  jz      loc_180020C73
0x180020b23  movups  xmm0, xmmword ptr [rbx]
0x180020b26  movups  xmmword ptr [rbp+57h+psa], xmm0
0x180020b2a  movsd   xmm1, qword ptr [rbx+10h]
0x180020b2f  movsd   [rbp+57h+var_90], xmm1
0x180020b34  movzx   eax, word ptr [rdi]
0x180020b37  sub     eax, 4Ah ; 'J'
0x180020b3a  jz      loc_180020C57
0x180020b40  sub     eax, 1
0x180020b43  jz      loc_180021047
0x180020b49  sub     eax, 1
0x180020b4c  jz      loc_180020E5C
0x180020b52  sub     eax, 3
0x180020b55  jz      loc_180020E5C
0x180020b5b  cmp     eax, 1
0x180020b5e  jz      loc_180020E9E
0x180020b64  cmp     rdi, rbx
0x180020b67  jz      loc_180020C2A
0x180020b6d  mov     rdx, rdi; pvargSrc
0x180020b70  mov     word ptr [rbp+57h+pvarDest], si
0x180020b74  lea     rcx, [rbp+57h+pvarDest]; pvarDest
0x180020b78  call    cs:__imp_VariantCopyInd
0x180020b7e  test    eax, eax
0x180020b80  js      loc_18002102A
0x180020b86  movups  xmm0, xmmword ptr [rbp+57h+pvarDest]
0x180020b8a  movups  xmmword ptr [rbx], xmm0
0x180020b8d  movsd   xmm1, qword ptr [rbp+57h+pvarDest+10h]
0x180020b92  movsd   qword ptr [rbx+10h], xmm1
0x180020b97  movzx   edx, word ptr [rbp+57h+psa]
0x180020b9b  mov     ecx, edx
0x180020b9d  cmp     edx, 4Eh ; 'N'
0x180020ba0  jz      short loc_180020C1C
0x180020ba2  cmp     edx, 4Fh ; 'O'
0x180020ba5  ja      loc_180020C95
0x180020bab  jz      loc_180020E89
0x180020bb1  sub     ecx, 49h ; 'I'
0x180020bb4  jz      loc_180020F1E
0x180020bba  sub     ecx, 3
0x180020bbd  jz      loc_180020E89
0x180020bc3  cmp     ecx, 1
0x180020bc6  jz      loc_180020EDE
0x180020bcc  lea     eax, [rdx-8]
0x180020bcf  cmp     ax, 40h ; '@'
0x180020bd3  jbe     short loc_180020BDA
0x180020bd5  cmp     edx, 51h ; 'Q'
0x180020bd8  jb      short loc_180020C2A
0x180020bda  movups  xmm0, xmmword ptr [rbp+57h+psa]
0x180020bde  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180020be2  mov     word ptr [rbp+57h+psa], si
0x180020be6  movsd   xmm1, [rbp+57h+var_90]
0x180020beb  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180020bef  movsd   qword ptr [rbp+57h+pvarg+10h], xmm1
0x180020bf4  call    cs:__imp_VariantClear
0x180020bfa  test    eax, eax
0x180020bfc  js      short loc_180020C2C
0x180020bfe  cmp     word ptr [rbp+57h+psa], si
0x180020c02  jz      short loc_180020C26
0x180020c04  lea     rdx, [rbp+57h+psa]; struct VAR *
0x180020c08  mov     ecx, 8000FFFFh; int
0x180020c0d  call    ?RaiseErrorHr@@YAXJPEAVVAR@@PEBGJ@Z; RaiseErrorHr(long,VAR *,ushort const *,long)
0x180020c13  mov     rdi, [r8+8]
0x180020c17  jmp     loc_180020AAB
0x180020c1c  mov     rcx, [rbp+57h+psa+8]; psa
0x180020c20  call    cs:__imp_SafeArrayUnlock
0x180020c26  test    eax, eax
0x180020c28  js      short loc_180020C2C
0x180020c2a  xor     eax, eax
0x180020c2c  mov     r14, [rsp+0E0h+var_30]
0x180020c34  mov     rsi, [rsp+0E0h+arg_18]
0x180020c3c  mov     rcx, [rbp+57h+var_40]
0x180020c40  xor     rcx, rsp; StackCookie
0x180020c43  call    __security_check_cookie
0x180020c48  add     rsp, 0C0h
0x180020c4f  pop     r15
0x180020c51  pop     r13
0x180020c53  pop     rdi
0x180020c54  pop     rbx
0x180020c55  pop     rbp
0x180020c56  retn
0x180020c57  mov     rax, [rdi+8]
0x180020c5b  movups  xmm0, xmmword ptr [rax]
0x180020c5e  movups  xmmword ptr [rbx], xmm0
0x180020c61  movsd   xmm1, qword ptr [rax+10h]
0x180020c66  movsd   qword ptr [rbx+10h], xmm1
0x180020c6b  mov     [rax], si
0x180020c6e  jmp     loc_180020B97
0x180020c73  mov     rax, [rdi+8]
0x180020c77  cmp     r14w, [rax]
0x180020c7b  jnz     loc_180020B23
0x180020c81  mov     rdi, rax
0x180020c84  cmp     [rdi+8], rsi
0x180020c88  jnz     loc_180020FF6
0x180020c8e  mov     eax, 800A005Bh
0x180020c93  jmp     short loc_180020C2C
0x180020c95  cmp     ecx, 50h ; 'P'
0x180020c98  jz      loc_180020EFC
0x180020c9e  cmp     ecx, r15d
0x180020ca1  jnz     loc_180020BCC
0x180020ca7  mov     rax, [rbp+57h+psa+8]
0x180020cab  lea     rcx, [rbp+57h+var_90]
0x180020caf  cmp     rax, rcx
0x180020cb2  jnz     loc_180020C2A
0x180020cb8  cmp     [rax], rsi
0x180020cbb  jz      loc_180020C2A
0x180020cc1  mov     word ptr [rbp+57h+psa], si
0x180020cc5  mov     ecx, 0FFFDh
0x180020cca  mov     rax, [rax]
0x180020ccd  and     [rax+2], cx
0x180020cd1  mov     rcx, [rbp+57h+psa+8]
0x180020cd5  mov     rcx, [rcx]; psa
0x180020cd8  call    cs:__imp_SafeArrayDestroy
0x180020cde  mov     ebx, eax
0x180020ce0  cmp     word ptr [rbp+57h+psa], si
0x180020ce4  jz      short loc_180020CF8
0x180020ce6  lea     rcx, [rbp+57h+psa]; pvarg
0x180020cea  call    cs:__imp_VariantClear
0x180020cf0  test    eax, eax
0x180020cf2  js      loc_180020C2C
0x180020cf8  mov     eax, ebx
0x180020cfa  jmp     loc_180020C26
0x180020cff  movzx   eax, word ptr [rdi]
0x180020d02  cmp     ax, 4Ah ; 'J'
0x180020d06  jnz     short loc_180020D12
0x180020d08  mov     rax, [rdi+8]
0x180020d0c  mov     rdi, rax
0x180020d0f  movzx   eax, word ptr [rax]
0x180020d12  cmp     ax, 9
0x180020d16  jnz     loc_180020E32
0x180020d1c  cmp     rbx, rdi
0x180020d1f  jz      loc_180020C2A
0x180020d25  movups  xmm0, xmmword ptr [rbx]
0x180020d28  movsd   xmm1, qword ptr [rbx+10h]
0x180020d2d  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180020d31  movups  xmm0, xmmword ptr [rdi]
0x180020d34  movsd   qword ptr [rbp+57h+pvarg+10h], xmm1
0x180020d39  movups  xmmword ptr [rbx], xmm0
0x180020d3c  movsd   xmm1, qword ptr [rdi+10h]
0x180020d41  movsd   qword ptr [rbx+10h], xmm1
0x180020d46  mov     rcx, [rbx+8]
0x180020d4a  test    rcx, rcx
0x180020d4d  jz      short loc_180020D5B
0x180020d4f  mov     rax, [rcx]
0x180020d52  mov     rax, [rax+8]
0x180020d56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d5b  lea     rcx, [rbp+57h+pvarg]; this
0x180020d5f  call    ?Clear@VAR@@QEAAJXZ; VAR::Clear(void)
0x180020d64  test    eax, eax
0x180020d66  js      loc_180020C2C
0x180020d6c  jmp     loc_180020C2A
0x180020d71  mov     rdi, [rcx+0B0h]
0x180020d78  test    rdi, rdi
0x180020d7b  jnz     short loc_180020D88
0x180020d7d  mov     rdi, [rcx+0B8h]
0x180020d84  add     rdi, 10h
0x180020d88  mov     rcx, rdi; this
0x180020d8b  call    ?Free@RuntimeScriptException@@QEAAXXZ; RuntimeScriptException::Free(void)
0x180020d90  mov     ecx, 80020005h; int
0x180020d95  mov     dword ptr [rdi+40h], 80020005h
0x180020d9c  call    ?MapHr@@YAJJ@Z; MapHr(long)
0x180020da1  mov     [rdi+40h], eax
0x180020da4  lea     rax, ExcepInfoDeferredFillIn
0x180020dab  mov     [rdi+38h], rax
0x180020daf  mov     rax, [r13+20h]
0x180020db3  test    rax, rax
0x180020db6  jz      loc_180020F3A
0x180020dbc  mov     eax, [rax+0B8h]
0x180020dc2  mov     [rdi+0Ah], ax
0x180020dc6  mov     rcx, [r13+48h]; this
0x180020dca  test    rcx, rcx
0x180020dcd  jz      short loc_180020DDB
0x180020dcf  mov     rdx, rdi; struct RuntimeScriptException *
0x180020dd2  call    ?RecordErrorContext@CScriptRuntime@@QEAAXPEAVRuntimeScriptException@@@Z; CScriptRuntime::RecordErrorContext(RuntimeScriptException *)
0x180020dd7  mov     rcx, [r13+48h]; this
0x180020ddb  mov     r14, [r13+0B0h]
0x180020de2  test    r14, r14
0x180020de5  jnz     short loc_180020DF2
0x180020de7  mov     r14, [r13+0B8h]
0x180020dee  add     r14, 10h
0x180020df2  test    rcx, rcx
0x180020df5  jz      short loc_180020E28
0x180020df7  mov     r15, 0FFFFFFFFFFFFFFFFh
0x180020dfe  mov     [rsp+0E0h+var_28], r12
0x180020e06  mov     r9d, r15d; int
0x180020e09  xor     r8d, r8d; Src
0x180020e0c  mov     rdx, rbx; pvarSrc
0x180020e0f  call    ?PszGetVarName@CScriptRuntime@@QEAAPEAGPEAVVAR@@PEBGJ@Z; CScriptRuntime::PszGetVarName(VAR *,ushort const *,long)
0x180020e14  mov     r12, rax
0x180020e17  test    rax, rax
0x180020e1a  jnz     loc_180020F45
0x180020e20  mov     r12, [rsp+0E0h+var_28]
0x180020e28  mov     eax, 86664004h
0x180020e2d  jmp     loc_180020C2C
0x180020e32  cmp     word ptr [rdi], 0Dh
0x180020e36  jz      loc_180020D1C
0x180020e3c  xor     r9d, r9d; unsigned __int16 *
0x180020e3f  mov     dword ptr [rsp+0E0h+var_C0], 0FFFFFFFFh; int
0x180020e47  mov     r8, rdi; struct VAR *
0x180020e4a  mov     edx, 800A01A8h; int
0x180020e4f  mov     rcx, r13; this
0x180020e52  call    ?RecordHr@CSession@@QEAAJJPEAVVAR@@PEBGJ@Z; CSession::RecordHr(long,VAR *,ushort const *,long)
0x180020e57  jmp     loc_180020C2C
0x180020e5c  cmp     rdi, rbx
0x180020e5f  jz      loc_180020C2A
0x180020e65  movups  xmm0, xmmword ptr [rdi]
0x180020e68  movups  xmmword ptr [rbx], xmm0
0x180020e6b  movsd   xmm1, qword ptr [rdi+10h]
0x180020e70  movsd   qword ptr [rbx+10h], xmm1
0x180020e75  mov     rcx, [rbx+8]
0x180020e79  mov     rax, [rcx]
0x180020e7c  mov     rax, [rax]
0x180020e7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020e84  jmp     loc_180020B97
0x180020e89  mov     rcx, [rbp+57h+psa+8]
0x180020e8d  mov     rax, [rcx]
0x180020e90  mov     rax, [rax+8]
0x180020e94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020e99  jmp     loc_180020C2A
0x180020e9e  cmp     rdi, rbx
0x180020ea1  jz      loc_180020C2A
0x180020ea7  mov     rdx, rdi; struct VAR *
0x180020eaa  mov     rcx, rbx; this
0x180020ead  call    ?CopyProperty@VAR@@QEAAJPEAV1@@Z; VAR::CopyProperty(VAR *)
0x180020eb2  test    eax, eax
0x180020eb4  cmovs   esi, eax
0x180020eb7  mov     eax, esi
0x180020eb9  jmp     loc_180020C2C
0x180020ebe  xor     r9d, r9d; unsigned __int16 *
0x180020ec1  mov     dword ptr [rsp+0E0h+var_C0], 0FFFFFFFFh; int
0x180020ec9  mov     r8, rbx; struct VAR *
0x180020ecc  mov     edx, 0Ah; int
0x180020ed1  mov     rcx, r13; this
0x180020ed4  call    ?RecordHr@CSession@@QEAAJJPEAVVAR@@PEBGJ@Z; CSession::RecordHr(long,VAR *,ushort const *,long)
0x180020ed9  jmp     loc_180020C2C
0x180020ede  mov     rcx, [rbp+57h+psa+8]
0x180020ee2  test    rcx, rcx
0x180020ee5  jz      loc_180020C2A
0x180020eeb  mov     rax, [rcx]
0x180020eee  mov     rax, [rax+10h]
0x180020ef2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ef7  jmp     loc_180020C2A
0x180020efc  mov     rbx, [rbp+57h+psa+8]
0x180020f00  test    rbx, rbx
0x180020f03  jz      loc_180020C2A
0x180020f09  mov     rcx, rbx; this
0x180020f0c  call    ??1PropertyFuncs@VAR@@QEAA@XZ; VAR::PropertyFuncs::~PropertyFuncs(void)
0x180020f11  mov     rcx, rbx; Block
0x180020f14  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180020f19  jmp     loc_180020C2A
  ... truncated ...
```
