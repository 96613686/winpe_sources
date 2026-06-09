# StripSignature

- ea: `0x1800021d0`
- end: `0x180002358`
- name: `StripSignature`
- size: `392`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int, OLECHAR **, _DWORD *)`
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x180001010`
- `0x1800093c0`
- `0x180009be0`

## callees

- `0x1800021d0`
- `0x180002360`
- `0x1800023d0`
- `0x180002450`
- `0x1800024f0`
- `0x1800098d0`
- `0x18000d172`

## import_xrefs

- `msvcrt!free` at `0x1800022b3`
- `msvcrt!free` at `0x1800022b3`
- `KERNEL32!SetLastError` at `0x180002317`
- `KERNEL32!SetLastError` at `0x180002317`
- `OLEAUT32!__imp_SysAllocString` at `0x1800022f9`
- `OLEAUT32!__imp_SysAllocString` at `0x1800022f9`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800022a2`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800022a2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800022d1`
- `OLEAUT32!__imp_SysFreeString` at `0x18000230f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800022d1`
- `OLEAUT32!__imp_SysFreeString` at `0x18000230f`

## pseudocode

```c
__int64 __fastcall StripSignature(unsigned __int16 *a1, unsigned int a2, OLECHAR **a3, _DWORD *a4)
{
  wchar_t *LastSignatureBlockBegin; // rax
  wchar_t *v9; // rdi
  __int64 v10; // rbp
  __int64 SignatureBlockEnd; // rax
  const void *v12; // rsi
  __int64 v13; // rbx
  OLECHAR *v14; // r14
  int v15; // edi
  OLECHAR *v16; // rbx
  BSTR v18; // rax
  DWORD v19; // edi
  __int64 Insertion; // rax
  OLECHAR *strIn; // [rsp+20h] [rbp-48h] BYREF
  __int64 v22; // [rsp+28h] [rbp-40h]
  int v23; // [rsp+30h] [rbp-38h]

  strIn = 0;
  v22 = 0;
  v23 = 0;
  LastSignatureBlockBegin = FindLastSignatureBlockBegin(a1, a2);
  v9 = LastSignatureBlockBegin;
  if ( LastSignatureBlockBegin )
  {
    v10 = LastSignatureBlockBegin - a1;
    BuildString::AppendSz((BuildString *)&strIn, a1, v10);
    SignatureBlockEnd = FindSignatureBlockEnd(v9);
    v12 = (const void *)SignatureBlockEnd;
    v13 = -1;
    do
      ++v13;
    while ( *(_WORD *)(SignatureBlockEnd + 2 * v13) );
    BuildString::EnsureSpace((BuildString *)&strIn, v13 + HIDWORD(v22));
    v14 = strIn;
    if ( v23 )
    {
      v16 = 0;
    }
    else
    {
      v15 = HIDWORD(v22);
      memcpy_0(&strIn[SHIDWORD(v22)], v12, 2LL * (int)v13);
      v14[(int)v13 + v15] = 0;
      v16 = SysAllocStringLen(v14, (int)v13 + v15);
    }
    if ( v14 )
      free(v14);
    if ( v16 )
    {
      if ( a4 )
        *a4 = v10;
      goto LABEL_11;
    }
  }
  else
  {
    v18 = SysAllocString(a1);
    v16 = v18;
    if ( v18 )
    {
      if ( a4 )
      {
        Insertion = FindInsertion(a2, v18);
        if ( !Insertion )
        {
          v19 = 11;
          goto LABEL_14;
        }
        *a4 = ((__int64)v16 - Insertion) >> 1;
      }
LABEL_11:
      *a3 = v16;
      SysFreeString(0);
      return 1;
    }
  }
  v19 = 8;
LABEL_14:
  SysFreeString(v16);
  SetLastError(v19);
  return 0;
}

```

## disassembly

```asm
0x1800021d0  mov     [rsp+arg_8], rbx
0x1800021d5  mov     [rsp+arg_10], rbp
0x1800021da  push    rsi
0x1800021db  push    rdi
0x1800021dc  push    r12
0x1800021de  push    r13
0x1800021e0  push    r15
0x1800021e2  sub     rsp, 40h
0x1800021e6  xor     eax, eax
0x1800021e8  mov     r15, r9
0x1800021eb  mov     [rsp+68h+strIn], rax
0x1800021f0  mov     r13d, eax
0x1800021f3  mov     [rsp+68h+var_40], rax
0x1800021f8  mov     r12, r8
0x1800021fb  mov     [rsp+68h+var_38], eax
0x1800021ff  mov     esi, edx
0x180002201  mov     rbx, rcx
0x180002204  call    FindLastSignatureBlockBegin
0x180002209  mov     rdi, rax
0x18000220c  test    rax, rax
0x18000220f  jz      loc_1800022F6
0x180002215  mov     rbp, rax
0x180002218  mov     [rsp+68h+arg_0], r14
0x18000221d  sub     rbp, rbx
0x180002220  lea     rcx, [rsp+68h+strIn]; this
0x180002225  sar     rbp, 1
0x180002228  mov     rdx, rbx; unsigned __int16 *
0x18000222b  mov     r8d, ebp; int
0x18000222e  call    ?AppendSz@BuildString@@QEAAXPEBGJ@Z; BuildString::AppendSz(ushort const *,long)
0x180002233  mov     edx, esi
0x180002235  mov     rcx, rdi; String1
0x180002238  call    FindSignatureBlockEnd
0x18000223d  mov     rsi, rax
0x180002240  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180002247  nop     word ptr [rax+rax+00000000h]
0x180002250  inc     rbx
0x180002253  cmp     [rax+rbx*2], r13w
0x180002258  jnz     short loc_180002250
0x18000225a  mov     edx, dword ptr [rsp+68h+var_40+4]
0x18000225e  lea     rcx, [rsp+68h+strIn]; this
0x180002263  add     edx, ebx; int
0x180002265  call    ?EnsureSpace@BuildString@@AEAAXJ@Z; BuildString::EnsureSpace(long)
0x18000226a  mov     r14, [rsp+68h+strIn]
0x18000226f  cmp     [rsp+68h+var_38], r13d
0x180002274  jnz     loc_180002351
0x18000227a  movsxd  rdi, dword ptr [rsp+68h+var_40+4]
0x18000227f  mov     rdx, rsi; Src
0x180002282  movsxd  r8, ebx
0x180002285  add     r8, r8; Size
0x180002288  lea     rcx, [r14+rdi*2]; void *
0x18000228c  call    memcpy_0
0x180002291  add     edi, ebx
0x180002293  xor     eax, eax
0x180002295  movsxd  rcx, edi
0x180002298  mov     edx, edi; ui
0x18000229a  mov     [r14+rcx*2], ax
0x18000229f  mov     rcx, r14; strIn
0x1800022a2  call    cs:__imp_SysAllocStringLen
0x1800022a8  mov     rbx, rax
0x1800022ab  test    r14, r14
0x1800022ae  jz      short loc_1800022B9
0x1800022b0  mov     rcx, r14; Block
0x1800022b3  call    cs:__imp_free
0x1800022b9  mov     r14, [rsp+68h+arg_0]
0x1800022be  test    rbx, rbx
0x1800022c1  jz      short loc_180002307
0x1800022c3  test    r15, r15
0x1800022c6  jz      short loc_1800022CB
0x1800022c8  mov     [r15], ebp
0x1800022cb  xor     ecx, ecx; bstrString
0x1800022cd  mov     [r12], rbx
0x1800022d1  call    cs:__imp_SysFreeString
0x1800022d7  mov     eax, 1
0x1800022dc  mov     rbx, [rsp+68h+arg_8]
0x1800022e1  mov     rbp, [rsp+68h+arg_10]
0x1800022e9  add     rsp, 40h
0x1800022ed  pop     r15
0x1800022ef  pop     r13
0x1800022f1  pop     r12
0x1800022f3  pop     rdi
0x1800022f4  pop     rsi
0x1800022f5  retn
0x1800022f6  mov     rcx, rbx; psz
0x1800022f9  call    cs:__imp_SysAllocString
0x1800022ff  mov     rbx, rax
0x180002302  test    rax, rax
0x180002305  jnz     short loc_180002322
0x180002307  mov     edi, 8
0x18000230c  mov     rcx, rbx; bstrString
0x18000230f  call    cs:__imp_SysFreeString
0x180002315  mov     ecx, edi; dwErrCode
0x180002317  call    cs:__imp_SetLastError
0x18000231d  mov     eax, r13d
0x180002320  jmp     short loc_1800022DC
0x180002322  test    r15, r15
0x180002325  jz      short loc_1800022CB
0x180002327  mov     rdx, rbx
0x18000232a  mov     ecx, esi
0x18000232c  call    FindInsertion
0x180002331  mov     rcx, rax
0x180002334  test    rax, rax
0x180002337  jnz     short loc_180002340
0x180002339  mov     edi, 0Bh
0x18000233e  jmp     short loc_18000230C
0x180002340  mov     rax, rbx
0x180002343  sub     rax, rcx
0x180002346  sar     rax, 1
0x180002349  mov     [r15], eax
0x18000234c  jmp     loc_1800022CB
0x180002351  xor     ebx, ebx
0x180002353  jmp     loc_1800022AB
```
