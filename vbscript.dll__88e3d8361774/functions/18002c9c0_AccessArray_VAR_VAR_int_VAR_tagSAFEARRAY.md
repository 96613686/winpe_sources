# AccessArray(VAR * *,VAR *,int,VAR *,tagSAFEARRAY * *)

- ea: `0x18002c9c0`
- end: `0x18002cc24`
- name: `?AccessArray@@YAJPEAPEAVVAR@@PEAV1@H1PEAPEAUtagSAFEARRAY@@@Z`
- size: `612`
- prototype: `HRESULT __fastcall(struct VAR **, struct VAR *, int, VARIANTARG *, struct tagSAFEARRAY **)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180021540`
- `0x180023ad0`
- `0x18006b020`

## callees

- `0x18001b960`
- `0x18002c9c0`
- `0x180035ef0`
- `0x1800418d8`
- `0x1800767a0`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayLock` at `0x18002ca54`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18002ca54`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18002cac9`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18002cb3d`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18002cc04`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18002cac9`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18002cb3d`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18002cc04`
- `KERNEL32!TlsGetValue` at `0x18002cb49`
- `KERNEL32!TlsGetValue` at `0x18002cb49`

## pseudocode

```c
HRESULT __fastcall AccessArray(struct VAR **a1, struct VAR *a2, int a3, VARIANTARG *a4, struct tagSAFEARRAY **a5)
{
  __int16 v5; // ax
  int v7; // edi
  struct tagSAFEARRAY **v8; // rsi
  struct tagSAFEARRAY *v9; // rsi
  int cDims; // eax
  HRESULT result; // eax
  int v12; // ebx
  int *i; // rbp
  VARIANTARG *pvarVal; // rdx
  LONG iVal; // eax
  int v16; // eax
  int v17; // ebx
  _QWORD *Value; // rax
  __int64 v19; // rcx
  int v20; // r12d
  CSession *v21; // rcx
  const unsigned __int16 *v22; // r8
  VARIANTARG pvargDest; // [rsp+38h] [rbp-60h] BYREF

  v5 = *(_WORD *)a2;
  v7 = a3;
  if ( *(_WORD *)a2 == 16396 || v5 == 74 )
  {
    a2 = (struct VAR *)*((_QWORD *)a2 + 1);
    v5 = *(_WORD *)a2;
  }
  if ( v5 == 8204 )
  {
    v8 = (struct tagSAFEARRAY **)((char *)a2 + 8);
  }
  else
  {
    if ( *(_WORD *)a2 != 24588 )
      return -2147352571;
    v8 = (struct tagSAFEARRAY **)*((_QWORD *)a2 + 1);
  }
  v9 = *v8;
  if ( !v9 )
    return -2147352565;
  cDims = v9->cDims;
  if ( !(_WORD)cDims || cDims != a3 )
    return -2147352565;
  result = SafeArrayLock(v9);
  if ( result >= 0 )
  {
    v12 = 0;
    for ( i = (int *)v9->rgsabound; ; i += 2 )
    {
      if ( a4->vt == 16396 || a4->vt == 74 )
        pvarVal = a4->pvarVal;
      else
        pvarVal = a4;
      if ( pvarVal->vt == 2 )
      {
        iVal = pvarVal->iVal;
      }
      else if ( pvarVal->vt == 3 )
      {
        iVal = pvarVal->lVal;
      }
      else
      {
        memset(&pvargDest, 0, sizeof(pvargDest));
        v20 = rtVariantChangeTypeEx(&pvargDest, pvarVal, 0x400u, 2u, 3u);
        if ( v20 < 0 )
        {
          SafeArrayUnlock(v9);
          return CScriptRuntime::RecordHr(v20, (struct VAR *)a4, v22);
        }
        iVal = pvargDest.lVal;
      }
      v16 = iVal - i[1];
      if ( v16 < 0 || v16 >= *i )
      {
        SafeArrayUnlock(v9);
        Value = TlsGetValue(g_luTls);
        if ( Value && (v19 = Value[3]) != 0 && (v21 = *(CSession **)(v19 + 640)) != 0 )
          return CSession::RecordHr(v21, -2147352565, (struct VAR *)a4, 0, -1);
        else
          return -2147352565;
      }
      v17 = v16 + v12;
      if ( --v7 <= 0 )
        break;
      v12 = i[2] * v17;
      ++a4;
    }
    result = SafeArrayUnlock(v9);
    if ( result >= 0 )
    {
      *a1 = (struct VAR *)((char *)v9->pvData + v9->cbElements * v17);
      if ( a5 )
        *a5 = v9;
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002c9c0  push    rdi
0x18002c9c2  push    r13
0x18002c9c4  push    r14
0x18002c9c6  push    r15
0x18002c9c8  sub     rsp, 78h
0x18002c9cc  mov     rax, cs:__security_cookie
0x18002c9d3  xor     rax, rsp
0x18002c9d6  mov     [rsp+98h+var_48], rax
0x18002c9db  movzx   eax, word ptr [rdx]
0x18002c9de  mov     r15d, 400Ch
0x18002c9e4  mov     r13, [rsp+98h+arg_20]
0x18002c9ec  mov     r14, r9
0x18002c9ef  mov     [rsp+98h+var_68], rcx
0x18002c9f4  mov     edi, r8d
0x18002c9f7  cmp     ax, r15w
0x18002c9fb  jz      loc_18002CB74
0x18002ca01  cmp     ax, 4Ah ; 'J'
0x18002ca05  jz      loc_18002CB74
0x18002ca0b  mov     ecx, 200Ch
0x18002ca10  mov     [rsp+98h+var_30], rsi
0x18002ca15  cmp     cx, ax
0x18002ca18  jz      loc_18002CB31
0x18002ca1e  mov     eax, 600Ch
0x18002ca23  cmp     ax, [rdx]
0x18002ca26  jnz     loc_18002CC1A
0x18002ca2c  mov     rsi, [rdx+8]
0x18002ca30  mov     rsi, [rsi]
0x18002ca33  test    rsi, rsi
0x18002ca36  jz      loc_18002CB64
0x18002ca3c  movzx   eax, word ptr [rsi]
0x18002ca3f  test    ax, ax
0x18002ca42  jz      loc_18002CB64
0x18002ca48  cmp     eax, r8d
0x18002ca4b  jnz     loc_18002CB64
0x18002ca51  mov     rcx, rsi; psa
0x18002ca54  call    cs:__imp_SafeArrayLock
0x18002ca5a  test    eax, eax
0x18002ca5c  js      loc_18002CB02
0x18002ca62  mov     [rsp+98h+arg_10], rbx
0x18002ca6a  mov     ecx, 2
0x18002ca6f  mov     [rsp+98h+var_28], rbp
0x18002ca74  xor     ebx, ebx
0x18002ca76  lea     rbp, [rsi+18h]
0x18002ca7a  mov     [rsp+98h+var_38], r12
0x18002ca7f  mov     r8d, 3
0x18002ca85  movzx   eax, word ptr [r14]
0x18002ca89  cmp     ax, r15w
0x18002ca8d  jz      loc_18002CB6B
0x18002ca93  cmp     ax, 4Ah ; 'J'
0x18002ca97  jz      loc_18002CB6B
0x18002ca9d  mov     rdx, r14; pvarSrc
0x18002caa0  movzx   eax, word ptr [rdx]
0x18002caa3  cmp     cx, ax
0x18002caa6  jnz     loc_18002CB83
0x18002caac  movsx   eax, word ptr [rdx+8]
0x18002cab0  sub     eax, [rbp+4]
0x18002cab3  js      loc_18002CB3A
0x18002cab9  cmp     eax, [rbp+0]
0x18002cabc  jge     short loc_18002CB3A
0x18002cabe  add     ebx, eax
0x18002cac0  dec     edi
0x18002cac2  test    edi, edi
0x18002cac4  jg      short loc_18002CB20
0x18002cac6  mov     rcx, rsi; psa
0x18002cac9  call    cs:__imp_SafeArrayUnlock
0x18002cacf  test    eax, eax
0x18002cad1  js      short loc_18002CAF0
0x18002cad3  imul    ebx, [rsi+4]
0x18002cad7  mov     rcx, [rsp+98h+var_68]
0x18002cadc  mov     eax, ebx
0x18002cade  add     rax, [rsi+10h]
0x18002cae2  mov     [rcx], rax
0x18002cae5  test    r13, r13
0x18002cae8  jz      short loc_18002CAEE
0x18002caea  mov     [r13+0], rsi
0x18002caee  xor     eax, eax
0x18002caf0  mov     r12, [rsp+98h+var_38]
0x18002caf5  mov     rbx, [rsp+98h+arg_10]
0x18002cafd  mov     rbp, [rsp+98h+var_28]
0x18002cb02  mov     rsi, [rsp+98h+var_30]
0x18002cb07  mov     rcx, [rsp+98h+var_48]
0x18002cb0c  xor     rcx, rsp; StackCookie
0x18002cb0f  call    __security_check_cookie
0x18002cb14  add     rsp, 78h
0x18002cb18  pop     r15
0x18002cb1a  pop     r14
0x18002cb1c  pop     r13
0x18002cb1e  pop     rdi
0x18002cb1f  retn
0x18002cb20  imul    ebx, [rbp+8]
0x18002cb24  add     rbp, 8
0x18002cb28  add     r14, 18h
0x18002cb2c  jmp     loc_18002CA85
0x18002cb31  lea     rsi, [rdx+8]
0x18002cb35  jmp     loc_18002CA30
0x18002cb3a  mov     rcx, rsi; psa
0x18002cb3d  call    cs:__imp_SafeArrayUnlock
0x18002cb43  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x18002cb49  call    cs:__imp_TlsGetValue
0x18002cb4f  test    rax, rax
0x18002cb52  jz      short loc_18002CB5D
0x18002cb54  mov     rcx, [rax+18h]
0x18002cb58  test    rcx, rcx
0x18002cb5b  jnz     short loc_18002CBD4
0x18002cb5d  mov     eax, 8002000Bh
0x18002cb62  jmp     short loc_18002CAF0
0x18002cb64  mov     eax, 8002000Bh
0x18002cb69  jmp     short loc_18002CB02
0x18002cb6b  mov     rdx, [r14+8]
0x18002cb6f  jmp     loc_18002CAA0
0x18002cb74  mov     rax, [rdx+8]
0x18002cb78  mov     rdx, rax
0x18002cb7b  movzx   eax, word ptr [rax]
0x18002cb7e  jmp     loc_18002CA0B
0x18002cb83  cmp     r8w, ax
0x18002cb87  jnz     short loc_18002CB91
0x18002cb89  mov     eax, [rdx+8]
0x18002cb8c  jmp     loc_18002CAB0
0x18002cb91  xorps   xmm0, xmm0
0x18002cb94  mov     [rsp+98h+var_78], r8w; unsigned __int16
0x18002cb9a  xor     eax, eax
0x18002cb9c  mov     r9d, ecx; unsigned __int16
0x18002cb9f  mov     r8d, 400h; unsigned int
0x18002cba5  mov     qword ptr [rsp+98h+pvargDest+10h], rax
0x18002cbaa  lea     rcx, [rsp+98h+pvargDest]; pvargDest
0x18002cbaf  movups  xmmword ptr [rsp+98h+pvargDest], xmm0
0x18002cbb4  call    ?rtVariantChangeTypeEx@@YAJPEAUtagVARIANT@@0KGG@Z; rtVariantChangeTypeEx(tagVARIANT *,tagVARIANT *,ulong,ushort,ushort)
0x18002cbb9  mov     r12d, eax
0x18002cbbc  test    eax, eax
0x18002cbbe  js      short loc_18002CC01
0x18002cbc0  mov     eax, dword ptr [rsp+98h+pvargDest+8]
0x18002cbc4  mov     ecx, 2
0x18002cbc9  mov     r8d, 3
0x18002cbcf  jmp     loc_18002CAB0
0x18002cbd4  mov     rcx, [rcx+280h]; this
0x18002cbdb  test    rcx, rcx
0x18002cbde  jz      loc_18002CB5D
0x18002cbe4  xor     r9d, r9d; unsigned __int16 *
0x18002cbe7  mov     dword ptr [rsp+98h+var_78], 0FFFFFFFFh; int
0x18002cbef  mov     r8, r14; struct VAR *
0x18002cbf2  mov     edx, 8002000Bh; int
0x18002cbf7  call    ?RecordHr@CSession@@QEAAJJPEAVVAR@@PEBGJ@Z; CSession::RecordHr(long,VAR *,ushort const *,long)
0x18002cbfc  jmp     loc_18002CAF0
0x18002cc01  mov     rcx, rsi; psa
0x18002cc04  call    cs:__imp_SafeArrayUnlock
0x18002cc0a  mov     rdx, r14; struct VAR *
0x18002cc0d  mov     ecx, r12d; int
0x18002cc10  call    ?RecordHr@CScriptRuntime@@SAJJPEAVVAR@@PEBG@Z; CScriptRuntime::RecordHr(long,VAR *,ushort const *)
0x18002cc15  jmp     loc_18002CAF0
0x18002cc1a  mov     eax, 80020005h
0x18002cc1f  jmp     loc_18002CB02
```
