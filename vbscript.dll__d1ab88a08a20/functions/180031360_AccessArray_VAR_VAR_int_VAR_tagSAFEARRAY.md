# AccessArray(VAR * *,VAR *,int,VAR *,tagSAFEARRAY * *)

- ea: `0x180031360`
- end: `0x1800315ea`
- name: `?AccessArray@@YAJPEAPEAVVAR@@PEAV1@H1PEAPEAUtagSAFEARRAY@@@Z`
- size: `650`
- prototype: `HRESULT __fastcall(struct VAR **, struct VAR *, int, VARIANTARG *, struct tagSAFEARRAY **)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18001cb70`
- `0x18001f0f0`
- `0x18006d184`

## callees

- `0x18001a970`
- `0x180031360`
- `0x180037464`
- `0x180042c7c`
- `0x180079490`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayLock` at `0x1800313f4`
- `OLEAUT32!__imp_SafeArrayLock` at `0x1800313f4`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180031473`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1800314ee`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1800315c4`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180031473`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1800314ee`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1800315c4`
- `KERNEL32!TlsGetValue` at `0x180031500`
- `KERNEL32!TlsGetValue` at `0x180031500`

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
0x180031360  push    rdi
0x180031362  push    r13
0x180031364  push    r14
0x180031366  push    r15
0x180031368  sub     rsp, 78h
0x18003136c  mov     rax, cs:__security_cookie
0x180031373  xor     rax, rsp
0x180031376  mov     [rsp+98h+var_48], rax
0x18003137b  movzx   eax, word ptr [rdx]
0x18003137e  mov     r15d, 400Ch
0x180031384  mov     r13, [rsp+98h+arg_20]
0x18003138c  mov     r14, r9
0x18003138f  mov     [rsp+98h+var_68], rcx
0x180031394  mov     edi, r8d
0x180031397  cmp     ax, r15w
0x18003139b  jz      loc_180031534
0x1800313a1  cmp     ax, 4Ah ; 'J'
0x1800313a5  jz      loc_180031534
0x1800313ab  mov     ecx, 200Ch
0x1800313b0  mov     [rsp+98h+var_30], rsi
0x1800313b5  cmp     cx, ax
0x1800313b8  jz      loc_1800314E2
0x1800313be  mov     eax, 600Ch
0x1800313c3  cmp     ax, [rdx]
0x1800313c6  jnz     loc_1800315E0
0x1800313cc  mov     rsi, [rdx+8]
0x1800313d0  mov     rsi, [rsi]
0x1800313d3  test    rsi, rsi
0x1800313d6  jz      loc_180031524
0x1800313dc  movzx   eax, word ptr [rsi]
0x1800313df  test    ax, ax
0x1800313e2  jz      loc_180031524
0x1800313e8  cmp     eax, r8d
0x1800313eb  jnz     loc_180031524
0x1800313f1  mov     rcx, rsi; psa
0x1800313f4  call    cs:__imp_SafeArrayLock
0x1800313fb  nop     dword ptr [rax+rax+00h]
0x180031400  test    eax, eax
0x180031402  js      loc_1800314B2
0x180031408  mov     [rsp+98h+arg_10], rbx
0x180031410  mov     ecx, 2
0x180031415  mov     [rsp+98h+var_28], rbp
0x18003141a  xor     ebx, ebx
0x18003141c  lea     rbp, [rsi+18h]
0x180031420  mov     [rsp+98h+var_38], r12
0x180031425  mov     r8d, 3
0x18003142b  movzx   eax, word ptr [r14]
0x18003142f  cmp     ax, r15w
0x180031433  jz      loc_18003152B
0x180031439  cmp     ax, 4Ah ; 'J'
0x18003143d  jz      loc_18003152B
0x180031443  mov     rdx, r14; pvarSrc
0x180031446  movzx   eax, word ptr [rdx]
0x180031449  cmp     cx, ax
0x18003144c  jnz     loc_180031543
0x180031452  movsx   eax, word ptr [rdx+8]
0x180031456  sub     eax, [rbp+4]
0x180031459  js      loc_1800314EB
0x18003145f  cmp     eax, [rbp+0]
0x180031462  jge     loc_1800314EB
0x180031468  add     ebx, eax
0x18003146a  dec     edi
0x18003146c  test    edi, edi
0x18003146e  jg      short loc_1800314D1
0x180031470  mov     rcx, rsi; psa
0x180031473  call    cs:__imp_SafeArrayUnlock
0x18003147a  nop     dword ptr [rax+rax+00h]
0x18003147f  test    eax, eax
0x180031481  js      short loc_1800314A0
0x180031483  imul    ebx, [rsi+4]
0x180031487  mov     rcx, [rsp+98h+var_68]
0x18003148c  mov     eax, ebx
0x18003148e  add     rax, [rsi+10h]
0x180031492  mov     [rcx], rax
0x180031495  test    r13, r13
0x180031498  jz      short loc_18003149E
0x18003149a  mov     [r13+0], rsi
0x18003149e  xor     eax, eax
0x1800314a0  mov     r12, [rsp+98h+var_38]
0x1800314a5  mov     rbx, [rsp+98h+arg_10]
0x1800314ad  mov     rbp, [rsp+98h+var_28]
0x1800314b2  mov     rsi, [rsp+98h+var_30]
0x1800314b7  mov     rcx, [rsp+98h+var_48]
0x1800314bc  xor     rcx, rsp; StackCookie
0x1800314bf  call    __security_check_cookie
0x1800314c4  add     rsp, 78h
0x1800314c8  pop     r15
0x1800314ca  pop     r14
0x1800314cc  pop     r13
0x1800314ce  pop     rdi
0x1800314cf  retn
0x1800314d1  imul    ebx, [rbp+8]
0x1800314d5  add     rbp, 8
0x1800314d9  add     r14, 18h
0x1800314dd  jmp     loc_18003142B
0x1800314e2  lea     rsi, [rdx+8]
0x1800314e6  jmp     loc_1800313D0
0x1800314eb  mov     rcx, rsi; psa
0x1800314ee  call    cs:__imp_SafeArrayUnlock
0x1800314f5  nop     dword ptr [rax+rax+00h]
0x1800314fa  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x180031500  call    cs:__imp_TlsGetValue
0x180031507  nop     dword ptr [rax+rax+00h]
0x18003150c  test    rax, rax
0x18003150f  jz      short loc_18003151A
0x180031511  mov     rcx, [rax+18h]
0x180031515  test    rcx, rcx
0x180031518  jnz     short loc_180031594
0x18003151a  mov     eax, 8002000Bh
0x18003151f  jmp     loc_1800314A0
0x180031524  mov     eax, 8002000Bh
0x180031529  jmp     short loc_1800314B2
0x18003152b  mov     rdx, [r14+8]
0x18003152f  jmp     loc_180031446
0x180031534  mov     rax, [rdx+8]
0x180031538  mov     rdx, rax
0x18003153b  movzx   eax, word ptr [rax]
0x18003153e  jmp     loc_1800313AB
0x180031543  cmp     r8w, ax
0x180031547  jnz     short loc_180031551
0x180031549  mov     eax, [rdx+8]
0x18003154c  jmp     loc_180031456
0x180031551  xorps   xmm0, xmm0
0x180031554  mov     [rsp+98h+var_78], r8w; unsigned __int16
0x18003155a  xor     eax, eax
0x18003155c  mov     r9d, ecx; unsigned __int16
0x18003155f  mov     r8d, 400h; unsigned int
0x180031565  mov     qword ptr [rsp+98h+pvargDest+10h], rax
0x18003156a  lea     rcx, [rsp+98h+pvargDest]; pvargDest
0x18003156f  movups  xmmword ptr [rsp+98h+pvargDest], xmm0
0x180031574  call    ?rtVariantChangeTypeEx@@YAJPEAUtagVARIANT@@0KGG@Z; rtVariantChangeTypeEx(tagVARIANT *,tagVARIANT *,ulong,ushort,ushort)
0x180031579  mov     r12d, eax
0x18003157c  test    eax, eax
0x18003157e  js      short loc_1800315C1
0x180031580  mov     eax, dword ptr [rsp+98h+pvargDest+8]
0x180031584  mov     ecx, 2
0x180031589  mov     r8d, 3
0x18003158f  jmp     loc_180031456
0x180031594  mov     rcx, [rcx+280h]; this
0x18003159b  test    rcx, rcx
0x18003159e  jz      loc_18003151A
0x1800315a4  xor     r9d, r9d; unsigned __int16 *
0x1800315a7  mov     dword ptr [rsp+98h+var_78], 0FFFFFFFFh; int
0x1800315af  mov     r8, r14; struct VAR *
0x1800315b2  mov     edx, 8002000Bh; int
0x1800315b7  call    ?RecordHr@CSession@@QEAAJJPEAVVAR@@PEBGJ@Z; CSession::RecordHr(long,VAR *,ushort const *,long)
0x1800315bc  jmp     loc_1800314A0
0x1800315c1  mov     rcx, rsi; psa
0x1800315c4  call    cs:__imp_SafeArrayUnlock
0x1800315cb  nop     dword ptr [rax+rax+00h]
0x1800315d0  mov     rdx, r14; struct VAR *
0x1800315d3  mov     ecx, r12d; int
0x1800315d6  call    ?RecordHr@CScriptRuntime@@SAJJPEAVVAR@@PEBG@Z; CScriptRuntime::RecordHr(long,VAR *,ushort const *)
0x1800315db  jmp     loc_1800314A0
0x1800315e0  mov     eax, 80020005h
0x1800315e5  jmp     loc_1800314B2
```
