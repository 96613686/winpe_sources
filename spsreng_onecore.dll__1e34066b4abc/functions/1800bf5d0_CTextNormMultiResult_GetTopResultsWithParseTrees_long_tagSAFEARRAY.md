# CTextNormMultiResult::GetTopResultsWithParseTrees(long,tagSAFEARRAY * *)

- ea: `0x1800bf5d0`
- end: `0x1800bf72f`
- name: `?GetTopResultsWithParseTrees@CTextNormMultiResult@@UEAAJJPEAPEAUtagSAFEARRAY@@@Z`
- size: `351`
- prototype: `__int64 __fastcall(CTextNormMultiResult *__hidden this, int, struct tagSAFEARRAY **)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000ab38`
- `0x1800bbc0c`
- `0x1800bcd8c`
- `0x1800bf5d0`
- `0x180102010`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800bf67a`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800bf67a`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800bf6c9`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800bf6c9`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1800bf6ad`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1800bf6ad`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CTextNormMultiResult::GetTopResultsWithParseTrees(
        CTextNormMultiResult *this,
        __int64 a2,
        struct tagSAFEARRAY **a3)
{
  HRESULT v4; // ebx
  signed int v5; // r14d
  SAFEARRAY *v6; // rdi
  __int64 **v7; // r8
  LONG i; // eax
  __int64 *v9; // r15
  _QWORD *v10; // rdi
  __int64 v11; // rcx
  _QWORD v13[2]; // [rsp+20h] [rbp-39h] BYREF
  ULONG v14; // [rsp+30h] [rbp-29h]
  __int64 v15; // [rsp+38h] [rbp-21h]
  CSPPlex *v16; // [rsp+40h] [rbp-19h]
  int v17; // [rsp+48h] [rbp-11h]
  _QWORD v18[2]; // [rsp+50h] [rbp-9h] BYREF
  int v19; // [rsp+60h] [rbp+7h]
  __int64 v20; // [rsp+68h] [rbp+Fh]
  __int64 v21; // [rsp+70h] [rbp+17h]
  int v22; // [rsp+78h] [rbp+1Fh]
  int v23; // [rsp+84h] [rbp+2Bh]
  LONG rgIndices; // [rsp+C8h] [rbp+6Fh] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+D8h] [rbp+7Fh] BYREF

  v14 = 0;
  v15 = 0;
  v13[1] = 0;
  v13[0] = 0;
  v16 = 0;
  v17 = 10;
  v19 = 0;
  v20 = 0;
  v18[1] = 0;
  v18[0] = 0;
  v21 = 0;
  v22 = 10;
  v23 = 0;
  if ( (int)a2 > 0 && a3 )
  {
    if ( *((_DWORD *)this + 21) )
    {
      v4 = CTextNormMultiResult::ComputeTopResults(this, a2, v18, v13);
      if ( v4 >= 0 )
      {
        v5 = v14;
        rgsabound.cElements = v14;
        rgsabound.lLbound = 0;
        v6 = SafeArrayCreate(0xDu, 1u, &rgsabound);
        if ( v6 )
        {
          v7 = (__int64 **)v13[0];
          rgIndices = 0;
          for ( i = 0; i < v5; i = ++rgIndices )
          {
            v9 = *v7;
            v4 = SafeArrayPutElement(v6, &rgIndices, v7[2]);
            if ( v4 < 0 )
            {
              SafeArrayDestroy(v6);
              goto LABEL_15;
            }
            v7 = (__int64 **)v9;
          }
          *a3 = v6;
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
LABEL_15:
  v10 = (_QWORD *)v13[0];
  while ( v10 )
  {
    v11 = v10[2];
    v10 = (_QWORD *)*v10;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  }
  CTnMultiResStringPackage::~CTnMultiResStringPackage((CTnMultiResStringPackage *)v18);
  if ( v16 )
    CSPPlex::FreeDataChain(v16);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800bf5d0  mov     [rsp-8+arg_0], rbx
0x1800bf5d5  mov     [rsp-8+arg_10], rsi
0x1800bf5da  push    rbp
0x1800bf5db  push    rdi
0x1800bf5dc  push    r12
0x1800bf5de  push    r14
0x1800bf5e0  push    r15
0x1800bf5e2  lea     rbp, [rsp-37h]
0x1800bf5e7  sub     rsp, 90h
0x1800bf5ee  mov     rsi, r8
0x1800bf5f1  xor     r12d, r12d
0x1800bf5f4  mov     [rbp+57h+var_80], r12d
0x1800bf5f8  mov     [rbp+57h+var_78], r12
0x1800bf5fc  mov     [rbp+57h+var_88], r12
0x1800bf600  mov     [rbp+57h+var_90], r12
0x1800bf604  mov     [rbp+57h+var_70], r12
0x1800bf608  lea     eax, [r12+0Ah]
0x1800bf60d  mov     [rbp+57h+var_68], eax
0x1800bf610  mov     [rbp+57h+var_50], r12d
0x1800bf614  mov     [rbp+57h+var_48], r12
0x1800bf618  mov     [rbp+57h+var_58], r12
0x1800bf61c  mov     [rbp+57h+var_60], r12
0x1800bf620  mov     [rbp+57h+var_40], r12
0x1800bf624  mov     [rbp+57h+var_38], eax
0x1800bf627  mov     [rbp+57h+var_2C], r12d
0x1800bf62b  test    edx, edx
0x1800bf62d  jle     loc_1800BF6D6
0x1800bf633  test    r8, r8
0x1800bf636  jz      loc_1800BF6D6
0x1800bf63c  cmp     [rcx+54h], r12d
0x1800bf640  jnz     short loc_1800BF64C
0x1800bf642  mov     ebx, 8000FFFFh
0x1800bf647  jmp     loc_1800BF6DB
0x1800bf64c  lea     r9, [rbp+57h+var_90]
0x1800bf650  lea     r8, [rbp+57h+var_60]
0x1800bf654  call    ?ComputeTopResults@CTextNormMultiResult@@AEAAJJPEAVCTnMultiResStringPackage@@PEAV?$CSPList@PEAUIParseTreeNode@@PEAU1@@@@Z; CTextNormMultiResult::ComputeTopResults(long,CTnMultiResStringPackage *,CSPList<IParseTreeNode *,IParseTreeNode *> *)
0x1800bf659  mov     ebx, eax
0x1800bf65b  test    eax, eax
0x1800bf65d  js      short loc_1800BF6DB
0x1800bf65f  mov     r14d, [rbp+57h+var_80]
0x1800bf663  mov     [rbp+57h+rgsabound.cElements], r14d
0x1800bf667  mov     [rbp+57h+rgsabound.lLbound], r12d
0x1800bf66e  mov     ecx, 0Dh; vt
0x1800bf673  lea     r8, [rbp+57h+rgsabound]; rgsabound
0x1800bf677  lea     edx, [rcx-0Ch]; cDims
0x1800bf67a  call    cs:__imp_SafeArrayCreate
0x1800bf680  mov     rdi, rax
0x1800bf683  test    rax, rax
0x1800bf686  jnz     short loc_1800BF68F
0x1800bf688  mov     ebx, 8007000Eh
0x1800bf68d  jmp     short loc_1800BF6DB
0x1800bf68f  mov     r8, [rbp+57h+var_90]
0x1800bf693  mov     [rbp+57h+rgIndices], r12d
0x1800bf697  mov     eax, r12d
0x1800bf69a  cmp     eax, r14d
0x1800bf69d  jge     short loc_1800BF6D1
0x1800bf69f  mov     r15, [r8]
0x1800bf6a2  mov     r8, [r8+10h]; pv
0x1800bf6a6  lea     rdx, [rbp+57h+rgIndices]; rgIndices
0x1800bf6aa  mov     rcx, rdi; psa
0x1800bf6ad  call    cs:__imp_SafeArrayPutElement
0x1800bf6b3  mov     ebx, eax
0x1800bf6b5  test    eax, eax
0x1800bf6b7  js      short loc_1800BF6C6
0x1800bf6b9  mov     r8, r15
0x1800bf6bc  mov     eax, [rbp+57h+rgIndices]
0x1800bf6bf  inc     eax
0x1800bf6c1  mov     [rbp+57h+rgIndices], eax
0x1800bf6c4  jmp     short loc_1800BF69A
0x1800bf6c6  mov     rcx, rdi; psa
0x1800bf6c9  call    cs:__imp_SafeArrayDestroy
0x1800bf6cf  jmp     short loc_1800BF6DB
0x1800bf6d1  mov     [rsi], rdi
0x1800bf6d4  jmp     short loc_1800BF6DB
0x1800bf6d6  mov     ebx, 80070057h
0x1800bf6db  mov     rdi, [rbp+57h+var_90]
0x1800bf6df  jmp     short loc_1800BF6F4
0x1800bf6e1  mov     rcx, [rdi+10h]
0x1800bf6e5  mov     rdi, [rdi]
0x1800bf6e8  mov     rax, [rcx]
0x1800bf6eb  mov     rax, [rax+10h]
0x1800bf6ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf6f4  test    rdi, rdi
0x1800bf6f7  jnz     short loc_1800BF6E1
0x1800bf6f9  lea     rcx, [rbp+57h+var_60]; this
0x1800bf6fd  call    ??1CTnMultiResStringPackage@@QEAA@XZ; CTnMultiResStringPackage::~CTnMultiResStringPackage(void)
0x1800bf702  nop
0x1800bf703  mov     rcx, [rbp+57h+var_70]; this
0x1800bf707  test    rcx, rcx
0x1800bf70a  jz      short loc_1800BF711
0x1800bf70c  call    ?FreeDataChain@CSPPlex@@QEAAXXZ; CSPPlex::FreeDataChain(void)
0x1800bf711  mov     eax, ebx
0x1800bf713  lea     r11, [rsp+0B0h+var_20]
0x1800bf71b  mov     rbx, [r11+30h]
0x1800bf71f  mov     rsi, [r11+40h]
0x1800bf723  mov     rsp, r11
0x1800bf726  pop     r15
0x1800bf728  pop     r14
0x1800bf72a  pop     r12
0x1800bf72c  pop     rdi
0x1800bf72d  pop     rbp
0x1800bf72e  retn
```
