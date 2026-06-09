# CTextNormMultiResult::GetTopResultsWithParseTrees(long,tagSAFEARRAY * *)

- ea: `0x18000d040`
- end: `0x18000d19b`
- name: `?GetTopResultsWithParseTrees@CTextNormMultiResult@@UEAAJJPEAPEAUtagSAFEARRAY@@@Z`
- size: `347`
- prototype: `__int64 __fastcall(CTextNormMultiResult *__hidden this, int, struct tagSAFEARRAY **)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180004f5c`
- `0x180009470`
- `0x18000a614`
- `0x18000d040`
- `0x180010010`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreate` at `0x18000d0e8`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18000d0e8`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18000d13a`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18000d13a`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18000d117`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18000d117`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CTextNormMultiResult::GetTopResultsWithParseTrees(
        CTextNormMultiResult *this,
        __int64 a2,
        struct tagSAFEARRAY **a3)
{
  HRESULT v4; // ebx
  int v5; // esi
  SAFEARRAY *v6; // rdi
  __int64 **v7; // r8
  __int64 *v8; // r15
  _QWORD *v9; // rdi
  __int64 v10; // rcx
  _QWORD v12[2]; // [rsp+20h] [rbp-39h] BYREF
  ULONG v13; // [rsp+30h] [rbp-29h]
  __int64 v14; // [rsp+38h] [rbp-21h]
  CSPPlex *v15; // [rsp+40h] [rbp-19h]
  int v16; // [rsp+48h] [rbp-11h]
  _QWORD v17[2]; // [rsp+50h] [rbp-9h] BYREF
  int v18; // [rsp+60h] [rbp+7h]
  __int64 v19; // [rsp+68h] [rbp+Fh]
  __int64 v20; // [rsp+70h] [rbp+17h]
  int v21; // [rsp+78h] [rbp+1Fh]
  int v22; // [rsp+84h] [rbp+2Bh]
  LONG rgIndices; // [rsp+C8h] [rbp+6Fh] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+D8h] [rbp+7Fh] BYREF

  v13 = 0;
  v14 = 0;
  v12[1] = 0;
  v12[0] = 0;
  v15 = 0;
  v16 = 10;
  v18 = 0;
  v19 = 0;
  v17[1] = 0;
  v17[0] = 0;
  v20 = 0;
  v21 = 10;
  v22 = 0;
  if ( (int)a2 > 0 && a3 )
  {
    if ( *((_DWORD *)this + 21) )
    {
      v4 = CTextNormMultiResult::ComputeTopResults(this, a2, v17, v12);
      if ( v4 >= 0 )
      {
        v5 = v13;
        rgsabound.cElements = v13;
        rgsabound.lLbound = 0;
        v6 = SafeArrayCreate(0xDu, 1u, &rgsabound);
        if ( v6 )
        {
          v7 = (__int64 **)v12[0];
          rgIndices = 0;
          if ( v5 <= 0 )
          {
LABEL_11:
            *a3 = v6;
          }
          else
          {
            while ( 1 )
            {
              v8 = *v7;
              v4 = SafeArrayPutElement(v6, &rgIndices, v7[2]);
              if ( v4 < 0 )
                break;
              v7 = (__int64 **)v8;
              if ( ++rgIndices >= v5 )
                goto LABEL_11;
            }
            SafeArrayDestroy(v6);
          }
        }
        else
        {
          v4 = -2147024882;
        }
      }
    }
    else
    {
      v4 = -2147418113;
    }
  }
  else
  {
    v4 = -2147024809;
  }
  v9 = (_QWORD *)v12[0];
  while ( v9 )
  {
    v10 = v9[2];
    v9 = (_QWORD *)*v9;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
  CTnMultiResStringPackage::~CTnMultiResStringPackage((CTnMultiResStringPackage *)v17);
  if ( v15 )
    CSPPlex::FreeDataChain(v15);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000d040  mov     [rsp-8+arg_0], rbx
0x18000d045  mov     [rsp-8+arg_10], rsi
0x18000d04a  push    rbp
0x18000d04b  push    rdi
0x18000d04c  push    r12
0x18000d04e  push    r14
0x18000d050  push    r15
0x18000d052  lea     rbp, [rsp-37h]
0x18000d057  sub     rsp, 90h
0x18000d05e  mov     r14, r8
0x18000d061  xor     r12d, r12d
0x18000d064  mov     [rbp+57h+var_80], r12d
0x18000d068  mov     [rbp+57h+var_78], r12
0x18000d06c  mov     [rbp+57h+var_88], r12
0x18000d070  mov     [rbp+57h+var_90], r12
0x18000d074  mov     [rbp+57h+var_70], r12
0x18000d078  lea     eax, [r12+0Ah]
0x18000d07d  mov     [rbp+57h+var_68], eax
0x18000d080  mov     [rbp+57h+var_50], r12d
0x18000d084  mov     [rbp+57h+var_48], r12
0x18000d088  mov     [rbp+57h+var_58], r12
0x18000d08c  mov     [rbp+57h+var_60], r12
0x18000d090  mov     [rbp+57h+var_40], r12
0x18000d094  mov     [rbp+57h+var_38], eax
0x18000d097  mov     [rbp+57h+var_2C], r12d
0x18000d09b  test    edx, edx
0x18000d09d  jle     loc_18000D142
0x18000d0a3  test    r8, r8
0x18000d0a6  jz      loc_18000D142
0x18000d0ac  cmp     [rcx+54h], r12d
0x18000d0b0  jnz     short loc_18000D0BC
0x18000d0b2  mov     ebx, 8000FFFFh
0x18000d0b7  jmp     loc_18000D147
0x18000d0bc  lea     r9, [rbp+57h+var_90]
0x18000d0c0  lea     r8, [rbp+57h+var_60]
0x18000d0c4  call    ?ComputeTopResults@CTextNormMultiResult@@AEAAJJPEAVCTnMultiResStringPackage@@PEAV?$CSPList@PEAUIParseTreeNode@@PEAU1@@@@Z; CTextNormMultiResult::ComputeTopResults(long,CTnMultiResStringPackage *,CSPList<IParseTreeNode *,IParseTreeNode *> *)
0x18000d0c9  mov     ebx, eax
0x18000d0cb  test    eax, eax
0x18000d0cd  js      short loc_18000D147
0x18000d0cf  mov     esi, [rbp+57h+var_80]
0x18000d0d2  mov     [rbp+57h+rgsabound.cElements], esi
0x18000d0d5  mov     [rbp+57h+rgsabound.lLbound], r12d
0x18000d0dc  mov     ecx, 0Dh; vt
0x18000d0e1  lea     r8, [rbp+57h+rgsabound]; rgsabound
0x18000d0e5  lea     edx, [rcx-0Ch]; cDims
0x18000d0e8  call    cs:__imp_SafeArrayCreate
0x18000d0ee  mov     rdi, rax
0x18000d0f1  test    rax, rax
0x18000d0f4  jnz     short loc_18000D0FD
0x18000d0f6  mov     ebx, 8007000Eh
0x18000d0fb  jmp     short loc_18000D147
0x18000d0fd  mov     r8, [rbp+57h+var_90]
0x18000d101  mov     [rbp+57h+rgIndices], r12d
0x18000d105  test    esi, esi
0x18000d107  jle     short loc_18000D132
0x18000d109  mov     r15, [r8]
0x18000d10c  mov     r8, [r8+10h]; pv
0x18000d110  lea     rdx, [rbp+57h+rgIndices]; rgIndices
0x18000d114  mov     rcx, rdi; psa
0x18000d117  call    cs:__imp_SafeArrayPutElement
0x18000d11d  mov     ebx, eax
0x18000d11f  test    eax, eax
0x18000d121  js      short loc_18000D137
0x18000d123  mov     r8, r15
0x18000d126  mov     eax, [rbp+57h+rgIndices]
0x18000d129  inc     eax
0x18000d12b  mov     [rbp+57h+rgIndices], eax
0x18000d12e  cmp     eax, esi
0x18000d130  jl      short loc_18000D109
0x18000d132  mov     [r14], rdi
0x18000d135  jmp     short loc_18000D147
0x18000d137  mov     rcx, rdi; psa
0x18000d13a  call    cs:__imp_SafeArrayDestroy
0x18000d140  jmp     short loc_18000D147
0x18000d142  mov     ebx, 80070057h
0x18000d147  mov     rdi, [rbp+57h+var_90]
0x18000d14b  jmp     short loc_18000D160
0x18000d14d  mov     rcx, [rdi+10h]
0x18000d151  mov     rdi, [rdi]
0x18000d154  mov     rax, [rcx]
0x18000d157  mov     rax, [rax+10h]
0x18000d15b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d160  test    rdi, rdi
0x18000d163  jnz     short loc_18000D14D
0x18000d165  lea     rcx, [rbp+57h+var_60]; this
0x18000d169  call    ??1CTnMultiResStringPackage@@QEAA@XZ; CTnMultiResStringPackage::~CTnMultiResStringPackage(void)
0x18000d16e  nop
0x18000d16f  mov     rcx, [rbp+57h+var_70]; this
0x18000d173  test    rcx, rcx
0x18000d176  jz      short loc_18000D17D
0x18000d178  call    ?FreeDataChain@CSPPlex@@QEAAXXZ; CSPPlex::FreeDataChain(void)
0x18000d17d  mov     eax, ebx
0x18000d17f  lea     r11, [rsp+0B0h+var_20]
0x18000d187  mov     rbx, [r11+30h]
0x18000d18b  mov     rsi, [r11+40h]
0x18000d18f  mov     rsp, r11
0x18000d192  pop     r15
0x18000d194  pop     r14
0x18000d196  pop     r12
0x18000d198  pop     rdi
0x18000d199  pop     rbp
0x18000d19a  retn
```
