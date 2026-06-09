# AssignVar(CSession *,VAR *,VAR *,ulong)

- ea: `0x18001b9e0`
- end: `0x18001c021`
- name: `?AssignVar@@YAJPEAVCSession@@PEAVVAR@@1K@Z`
- size: `1601`
- prototype: `int(struct CSession *, struct VAR *, struct VAR *, unsigned int)`
- caller_count: `12`
- callee_count: `18`
- tags: `file_ops`

## callers

- `0x180006490`
- `0x18001aeb0`
- `0x18001b5f0`
- `0x18001cb70`
- `0x18001f0f0`
- `0x18003bb30`
- `0x180043490`
- `0x18005e1e0`
- `0x18006ba64`
- `0x18006ca7c`
- `0x18006cd20`
- `0x18006d184`

## callees

- `0x1800019d4`
- `0x180001a30`
- `0x180011650`
- `0x18001b340`
- `0x18001b5d0`
- `0x18001b9e0`
- `0x18001c028`
- `0x18001c358`
- `0x18001c8ac`
- `0x18001ed10`
- `0x180037464`
- `0x18003c860`
- `0x18004237c`
- `0x180042f8c`
- `0x18004686c`
- `0x18007941e`
- `0x180079490`
- `0x18007a010`

## import_xrefs

- `msvcrt!free` at `0x18001bfa1`
- `msvcrt!free` at `0x18001bfa1`
- `OLEAUT32!__imp_SysFreeString` at `0x18001bf8e`
- `OLEAUT32!__imp_SysFreeString` at `0x18001bf8e`
- `OLEAUT32!__imp_SysStringLen` at `0x18001bf0f`
- `OLEAUT32!__imp_SysStringLen` at `0x18001bf0f`
- `OLEAUT32!__imp_VariantClear` at `0x18001bb8e`
- `OLEAUT32!__imp_VariantClear` at `0x18001bc97`
- `OLEAUT32!__imp_VariantClear` at `0x18001bb8e`
- `OLEAUT32!__imp_VariantClear` at `0x18001bc97`
- `OLEAUT32!__imp_VariantCopyInd` at `0x18001bb08`
- `OLEAUT32!__imp_VariantCopyInd` at `0x18001bb08`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18001bc7f`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18001bc7f`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18001bbc0`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18001bbc0`
- `KERNEL32!GetUserDefaultLCID` at `0x18001bede`
- `KERNEL32!GetUserDefaultLCID` at `0x18001bede`

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
  struct RuntimeScriptException *v18; // rdi
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
    v18 = CSession::PseGet(a1);
    RuntimeScriptException::Free(v18);
    *((_DWORD *)v18 + 16) = -2147352571;
    *((_DWORD *)v18 + 16) = MapHr(-2147352571);
    *((_QWORD *)v18 + 7) = ExcepInfoDeferredFillIn;
    v19 = *((_QWORD *)a1 + 4);
    if ( v19 )
      v20 = *(_DWORD *)(v19 + 184);
    else
      LOWORD(v20) = GetUserDefaultLCID();
    *((_WORD *)v18 + 5) = v20;
    v21 = (CScriptRuntime *)*((_QWORD *)a1 + 9);
    if ( v21 )
    {
      CScriptRuntime::RecordErrorContext(v21, v18);
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
            v31[v33 + 2] = asc_180083F10[2];
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
        goto LABEL_69;
      case 'I':
        psa.vt = 9;
        result = VAR::VariantClearWrapper((VAR *)&psa);
        goto LABEL_33;
      case 'L':
LABEL_69:
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
0x18001b9e0  push    rbp
0x18001b9e2  push    rbx
0x18001b9e3  push    rdi
0x18001b9e4  push    r13
0x18001b9e6  push    r15
0x18001b9e8  lea     rbp, [rsp-37h]
0x18001b9ed  sub     rsp, 0C0h
0x18001b9f4  mov     rax, cs:__security_cookie
0x18001b9fb  xor     rax, rsp
0x18001b9fe  mov     [rbp+57h+var_40], rax
0x18001ba02  xor     eax, eax
0x18001ba04  xorps   xmm0, xmm0
0x18001ba07  mov     [rbp+57h+var_48], rax
0x18001ba0b  xorps   xmm1, xmm1
0x18001ba0e  mov     qword ptr [rbp+57h+pvarDest+10h], rax
0x18001ba12  mov     rdi, r8
0x18001ba15  mov     eax, 400Ch
0x18001ba1a  mov     rbx, rdx
0x18001ba1d  mov     r13, rcx
0x18001ba20  movups  [rbp+57h+var_58], xmm0
0x18001ba24  movups  xmmword ptr [rbp+57h+pvarDest], xmm1
0x18001ba28  cmp     [rdx], ax
0x18001ba2b  jz      loc_18001BED5
0x18001ba31  cmp     [r8], ax
0x18001ba35  jz      loc_18001BBB3
0x18001ba3b  movzx   eax, word ptr [rbx]
0x18001ba3e  mov     r15d, 600Ch
0x18001ba44  mov     [rsp+0E0h+arg_18], rsi
0x18001ba4c  mov     [rsp+0E0h+var_30], r14
0x18001ba54  cmp     ax, r15w
0x18001ba58  jz      loc_18001BD24
0x18001ba5e  cmp     rbx, rdi
0x18001ba61  jz      short loc_18001BA80
0x18001ba63  mov     ecx, 200Ch
0x18001ba68  cmp     ax, cx
0x18001ba6b  jnz     short loc_18001BA80
0x18001ba6d  mov     rax, [rbx+8]
0x18001ba71  test    rax, rax
0x18001ba74  jz      short loc_18001BA80
0x18001ba76  cmp     dword ptr [rax+8], 0
0x18001ba7a  ja      loc_18001BE62
0x18001ba80  test    r9b, 2
0x18001ba84  jnz     loc_18001BCB2
0x18001ba8a  xor     esi, esi
0x18001ba8c  mov     r14d, 9
0x18001ba92  test    r9b, 1
0x18001ba96  jz      short loc_18001BAB3
0x18001ba98  movzx   eax, word ptr [rdi]
0x18001ba9b  cmp     r14w, ax
0x18001ba9f  jz      loc_18001BC2B
0x18001baa5  mov     ecx, 4Ah ; 'J'
0x18001baaa  cmp     cx, ax
0x18001baad  jz      loc_18001BC1A
0x18001bab3  movups  xmm0, xmmword ptr [rbx]
0x18001bab6  movups  xmmword ptr [rbp+57h+psa], xmm0
0x18001baba  movsd   xmm1, qword ptr [rbx+10h]
0x18001babf  movsd   [rbp+57h+var_90], xmm1
0x18001bac4  movzx   eax, word ptr [rdi]
0x18001bac7  sub     eax, 4Ah ; 'J'
0x18001baca  jz      loc_18001BBFE
0x18001bad0  sub     eax, 1
0x18001bad3  jz      loc_18001C003
0x18001bad9  sub     eax, 1
0x18001badc  jz      loc_18001BE00
0x18001bae2  sub     eax, 3
0x18001bae5  jz      loc_18001BE00
0x18001baeb  cmp     eax, 1
0x18001baee  jz      loc_18001BE42
0x18001baf4  cmp     rdi, rbx
0x18001baf7  jz      loc_18001BBD0
0x18001bafd  mov     rdx, rdi; pvargSrc
0x18001bb00  mov     word ptr [rbp+57h+pvarDest], si
0x18001bb04  lea     rcx, [rbp+57h+pvarDest]; pvarDest
0x18001bb08  call    cs:__imp_VariantCopyInd
0x18001bb0f  nop     dword ptr [rax+rax+00h]
0x18001bb14  test    eax, eax
0x18001bb16  js      loc_18001BFE6
0x18001bb1c  movups  xmm0, xmmword ptr [rbp+57h+pvarDest]
0x18001bb20  movups  xmmword ptr [rbx], xmm0
0x18001bb23  movsd   xmm1, qword ptr [rbp+57h+pvarDest+10h]
0x18001bb28  movsd   qword ptr [rbx+10h], xmm1
0x18001bb2d  movzx   edx, word ptr [rbp+57h+psa]
0x18001bb31  mov     ecx, edx
0x18001bb33  cmp     edx, 4Eh ; 'N'
0x18001bb36  jz      loc_18001BBBC
0x18001bb3c  cmp     edx, 4Fh ; 'O'
0x18001bb3f  ja      loc_18001BC3C
0x18001bb45  jz      loc_18001BE2D
0x18001bb4b  sub     ecx, 49h ; 'I'
0x18001bb4e  jz      loc_18001BEC2
0x18001bb54  sub     ecx, 3
0x18001bb57  jz      loc_18001BE2D
0x18001bb5d  cmp     ecx, 1
0x18001bb60  jz      loc_18001BE82
0x18001bb66  lea     eax, [rdx-8]
0x18001bb69  cmp     ax, 40h ; '@'
0x18001bb6d  jbe     short loc_18001BB74
0x18001bb6f  cmp     edx, 51h ; 'Q'
0x18001bb72  jb      short loc_18001BBD0
0x18001bb74  movups  xmm0, xmmword ptr [rbp+57h+psa]
0x18001bb78  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18001bb7c  mov     word ptr [rbp+57h+psa], si
0x18001bb80  movsd   xmm1, [rbp+57h+var_90]
0x18001bb85  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18001bb89  movsd   qword ptr [rbp+57h+pvarg+10h], xmm1
0x18001bb8e  call    cs:__imp_VariantClear
0x18001bb95  nop     dword ptr [rax+rax+00h]
0x18001bb9a  test    eax, eax
0x18001bb9c  js      short loc_18001BBD2
0x18001bb9e  cmp     word ptr [rbp+57h+psa], si
0x18001bba2  jz      short loc_18001BBCC
0x18001bba4  lea     rdx, [rbp+57h+psa]; struct VAR *
0x18001bba8  mov     ecx, 8000FFFFh; int
0x18001bbad  call    ?RaiseErrorHr@@YAXJPEAVVAR@@PEBGJ@Z; RaiseErrorHr(long,VAR *,ushort const *,long)
0x18001bbb3  mov     rdi, [r8+8]
0x18001bbb7  jmp     loc_18001BA3B
0x18001bbbc  mov     rcx, [rbp+57h+psa+8]; psa
0x18001bbc0  call    cs:__imp_SafeArrayUnlock
0x18001bbc7  nop     dword ptr [rax+rax+00h]
0x18001bbcc  test    eax, eax
0x18001bbce  js      short loc_18001BBD2
0x18001bbd0  xor     eax, eax
0x18001bbd2  mov     r14, [rsp+0E0h+var_30]
0x18001bbda  mov     rsi, [rsp+0E0h+arg_18]
0x18001bbe2  mov     rcx, [rbp+57h+var_40]
0x18001bbe6  xor     rcx, rsp; StackCookie
0x18001bbe9  call    __security_check_cookie
0x18001bbee  add     rsp, 0C0h
0x18001bbf5  pop     r15
0x18001bbf7  pop     r13
0x18001bbf9  pop     rdi
0x18001bbfa  pop     rbx
0x18001bbfb  pop     rbp
0x18001bbfc  retn
0x18001bbfe  mov     rax, [rdi+8]
0x18001bc02  movups  xmm0, xmmword ptr [rax]
0x18001bc05  movups  xmmword ptr [rbx], xmm0
0x18001bc08  movsd   xmm1, qword ptr [rax+10h]
0x18001bc0d  movsd   qword ptr [rbx+10h], xmm1
0x18001bc12  mov     [rax], si
0x18001bc15  jmp     loc_18001BB2D
0x18001bc1a  mov     rax, [rdi+8]
0x18001bc1e  cmp     r14w, [rax]
0x18001bc22  jnz     loc_18001BAB3
0x18001bc28  mov     rdi, rax
0x18001bc2b  cmp     [rdi+8], rsi
0x18001bc2f  jnz     loc_18001BFB2
0x18001bc35  mov     eax, 800A005Bh
0x18001bc3a  jmp     short loc_18001BBD2
0x18001bc3c  cmp     ecx, 50h ; 'P'
0x18001bc3f  jz      loc_18001BEA0
0x18001bc45  cmp     ecx, r15d
0x18001bc48  jnz     loc_18001BB66
0x18001bc4e  mov     rax, [rbp+57h+psa+8]
0x18001bc52  lea     rcx, [rbp+57h+var_90]
0x18001bc56  cmp     rax, rcx
0x18001bc59  jnz     loc_18001BBD0
0x18001bc5f  cmp     [rax], rsi
0x18001bc62  jz      loc_18001BBD0
0x18001bc68  mov     word ptr [rbp+57h+psa], si
0x18001bc6c  mov     ecx, 0FFFDh
0x18001bc71  mov     rax, [rax]
0x18001bc74  and     [rax+2], cx
0x18001bc78  mov     rcx, [rbp+57h+psa+8]
0x18001bc7c  mov     rcx, [rcx]; psa
0x18001bc7f  call    cs:__imp_SafeArrayDestroy
0x18001bc86  nop     dword ptr [rax+rax+00h]
0x18001bc8b  mov     ebx, eax
0x18001bc8d  cmp     word ptr [rbp+57h+psa], si
0x18001bc91  jz      short loc_18001BCAB
0x18001bc93  lea     rcx, [rbp+57h+psa]; pvarg
0x18001bc97  call    cs:__imp_VariantClear
0x18001bc9e  nop     dword ptr [rax+rax+00h]
0x18001bca3  test    eax, eax
0x18001bca5  js      loc_18001BBD2
0x18001bcab  mov     eax, ebx
0x18001bcad  jmp     loc_18001BBCC
0x18001bcb2  movzx   eax, word ptr [rdi]
0x18001bcb5  cmp     ax, 4Ah ; 'J'
0x18001bcb9  jnz     short loc_18001BCC5
0x18001bcbb  mov     rax, [rdi+8]
0x18001bcbf  mov     rdi, rax
0x18001bcc2  movzx   eax, word ptr [rax]
0x18001bcc5  cmp     ax, 9
0x18001bcc9  jnz     loc_18001BDD6
0x18001bccf  cmp     rbx, rdi
0x18001bcd2  jz      loc_18001BBD0
0x18001bcd8  movups  xmm0, xmmword ptr [rbx]
0x18001bcdb  movsd   xmm1, qword ptr [rbx+10h]
0x18001bce0  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18001bce4  movups  xmm0, xmmword ptr [rdi]
0x18001bce7  movsd   qword ptr [rbp+57h+pvarg+10h], xmm1
0x18001bcec  movups  xmmword ptr [rbx], xmm0
0x18001bcef  movsd   xmm1, qword ptr [rdi+10h]
0x18001bcf4  movsd   qword ptr [rbx+10h], xmm1
0x18001bcf9  mov     rcx, [rbx+8]
0x18001bcfd  test    rcx, rcx
0x18001bd00  jz      short loc_18001BD0E
0x18001bd02  mov     rax, [rcx]
0x18001bd05  mov     rax, [rax+8]
0x18001bd09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bd0e  lea     rcx, [rbp+57h+pvarg]; this
0x18001bd12  call    ?Clear@VAR@@QEAAJXZ; VAR::Clear(void)
0x18001bd17  test    eax, eax
0x18001bd19  js      loc_18001BBD2
0x18001bd1f  jmp     loc_18001BBD0
0x18001bd24  call    ?PseGet@CSession@@QEAAPEAVRuntimeScriptException@@XZ; CSession::PseGet(void)
0x18001bd29  mov     rcx, rax; this
0x18001bd2c  mov     rdi, rax
0x18001bd2f  call    ?Free@RuntimeScriptException@@QEAAXXZ; RuntimeScriptException::Free(void)
0x18001bd34  mov     ecx, 80020005h; int
0x18001bd39  mov     dword ptr [rdi+40h], 80020005h
0x18001bd40  call    ?MapHr@@YAJJ@Z; MapHr(long)
0x18001bd45  mov     [rdi+40h], eax
0x18001bd48  lea     rax, ExcepInfoDeferredFillIn
0x18001bd4f  mov     [rdi+38h], rax
0x18001bd53  mov     rax, [r13+20h]
0x18001bd57  test    rax, rax
0x18001bd5a  jz      loc_18001BEDE
0x18001bd60  mov     eax, [rax+0B8h]
0x18001bd66  mov     [rdi+0Ah], ax
0x18001bd6a  mov     rcx, [r13+48h]; this
0x18001bd6e  test    rcx, rcx
0x18001bd71  jz      short loc_18001BD7F
0x18001bd73  mov     rdx, rdi; struct RuntimeScriptException *
0x18001bd76  call    ?RecordErrorContext@CScriptRuntime@@QEAAXPEAVRuntimeScriptException@@@Z; CScriptRuntime::RecordErrorContext(RuntimeScriptException *)
0x18001bd7b  mov     rcx, [r13+48h]; this
0x18001bd7f  mov     r14, [r13+0B0h]
0x18001bd86  test    r14, r14
0x18001bd89  jnz     short loc_18001BD96
0x18001bd8b  mov     r14, [r13+0B8h]
0x18001bd92  add     r14, 10h
0x18001bd96  test    rcx, rcx
0x18001bd99  jz      short loc_18001BDCC
0x18001bd9b  mov     r15, 0FFFFFFFFFFFFFFFFh
0x18001bda2  mov     [rsp+0E0h+var_28], r12
0x18001bdaa  mov     r9d, r15d; int
0x18001bdad  xor     r8d, r8d; Src
0x18001bdb0  mov     rdx, rbx; pvarSrc
0x18001bdb3  call    ?PszGetVarName@CScriptRuntime@@QEAAPEAGPEAVVAR@@PEBGJ@Z; CScriptRuntime::PszGetVarName(VAR *,ushort const *,long)
0x18001bdb8  mov     r12, rax
0x18001bdbb  test    rax, rax
0x18001bdbe  jnz     loc_18001BEEF
0x18001bdc4  mov     r12, [rsp+0E0h+var_28]
0x18001bdcc  mov     eax, 86664004h
0x18001bdd1  jmp     loc_18001BBD2
0x18001bdd6  cmp     word ptr [rdi], 0Dh
0x18001bdda  jz      loc_18001BCCF
0x18001bde0  xor     r9d, r9d; unsigned __int16 *
0x18001bde3  mov     dword ptr [rsp+0E0h+var_C0], 0FFFFFFFFh; int
0x18001bdeb  mov     r8, rdi; struct VAR *
0x18001bdee  mov     edx, 800A01A8h; int
0x18001bdf3  mov     rcx, r13; this
0x18001bdf6  call    ?RecordHr@CSession@@QEAAJJPEAVVAR@@PEBGJ@Z; CSession::RecordHr(long,VAR *,ushort const *,long)
0x18001bdfb  jmp     loc_18001BBD2
0x18001be00  cmp     rdi, rbx
0x18001be03  jz      loc_18001BBD0
0x18001be09  movups  xmm0, xmmword ptr [rdi]
0x18001be0c  movups  xmmword ptr [rbx], xmm0
0x18001be0f  movsd   xmm1, qword ptr [rdi+10h]
0x18001be14  movsd   qword ptr [rbx+10h], xmm1
0x18001be19  mov     rcx, [rbx+8]
0x18001be1d  mov     rax, [rcx]
0x18001be20  mov     rax, [rax]
0x18001be23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be28  jmp     loc_18001BB2D
0x18001be2d  mov     rcx, [rbp+57h+psa+8]
0x18001be31  mov     rax, [rcx]
0x18001be34  mov     rax, [rax+8]
0x18001be38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be3d  jmp     loc_18001BBD0
0x18001be42  cmp     rdi, rbx
0x18001be45  jz      loc_18001BBD0
0x18001be4b  mov     rdx, rdi; struct VAR *
0x18001be4e  mov     rcx, rbx; this
0x18001be51  call    ?CopyProperty@VAR@@QEAAJPEAV1@@Z; VAR::CopyProperty(VAR *)
0x18001be56  test    eax, eax
0x18001be58  cmovs   esi, eax
0x18001be5b  mov     eax, esi
0x18001be5d  jmp     loc_18001BBD2
0x18001be62  xor     r9d, r9d; unsigned __int16 *
0x18001be65  mov     dword ptr [rsp+0E0h+var_C0], 0FFFFFFFFh; int
0x18001be6d  mov     r8, rbx; struct VAR *
0x18001be70  mov     edx, 0Ah; int
0x18001be75  mov     rcx, r13; this
0x18001be78  call    ?RecordHr@CSession@@QEAAJJPEAVVAR@@PEBGJ@Z; CSession::RecordHr(long,VAR *,ushort const *,long)
0x18001be7d  jmp     loc_18001BBD2
0x18001be82  mov     rcx, [rbp+57h+psa+8]
0x18001be86  test    rcx, rcx
0x18001be89  jz      loc_18001BBD0
0x18001be8f  mov     rax, [rcx]
0x18001be92  mov     rax, [rax+10h]
0x18001be96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be9b  jmp     loc_18001BBD0
0x18001bea0  mov     rbx, [rbp+57h+psa+8]
0x18001bea4  test    rbx, rbx
0x18001bea7  jz      loc_18001BBD0
0x18001bead  mov     rcx, rbx; this
0x18001beb0  call    ??1PropertyFuncs@VAR@@QEAA@XZ; VAR::PropertyFuncs::~PropertyFuncs(void)
0x18001beb5  mov     rcx, rbx; Block
  ... truncated ...
```
