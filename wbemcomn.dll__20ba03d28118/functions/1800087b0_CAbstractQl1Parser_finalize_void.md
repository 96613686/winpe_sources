# CAbstractQl1Parser::finalize(void)

- ea: `0x1800087b0`
- end: `0x1800088d0`
- name: `?finalize@CAbstractQl1Parser@@IEAAHXZ`
- size: `288`
- prototype: `__int64 __fastcall(CAbstractQl1Parser *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000da70`

## callees

- `0x1800087b0`
- `0x180009f40`
- `0x18000e180`
- `0x1800442d3`
- `0x180047010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800087e7`
- `OLEAUT32!__imp_VariantInit` at `0x1800087e7`
- `OLEAUT32!__imp_VariantClear` at `0x180008872`
- `OLEAUT32!__imp_VariantClear` at `0x18000887c`
- `OLEAUT32!__imp_VariantClear` at `0x180008872`
- `OLEAUT32!__imp_VariantClear` at `0x18000887c`
- `OLEAUT32!__imp_VariantCopy` at `0x180008815`
- `OLEAUT32!__imp_VariantCopy` at `0x180008815`

## pseudocode

```c
__int64 __fastcall CAbstractQl1Parser::finalize(CAbstractQl1Parser *this)
{
  bool v2; // zf
  __int64 *v3; // rcx
  __int64 v4; // rax
  __int64 result; // rax
  __int128 v6; // xmm0
  int v7; // [rsp+20h] [rbp-60h] BYREF
  __int128 v8; // [rsp+28h] [rbp-58h]
  __int128 v9; // [rsp+38h] [rbp-48h]
  int v10; // [rsp+48h] [rbp-38h]
  VARIANTARG pvarg; // [rsp+50h] [rbp-30h] BYREF
  int v12; // [rsp+68h] [rbp-18h]
  int v13; // [rsp+6Ch] [rbp-14h]
  int v14; // [rsp+70h] [rbp-10h]
  int v15; // [rsp+74h] [rbp-Ch]

  memset_0(&v7, 0, 0x58u);
  CAbstractQl1Parser::InitToken((struct _tag_WbemQl1Token *)&v7);
  v7 = 4;
  VariantInit(&pvarg);
  v2 = *((_DWORD *)this + 40) == 0;
  v8 = *(_OWORD *)((char *)this + 88);
  if ( v2 )
  {
    v15 = 0;
    if ( VariantCopy(&pvarg, (const VARIANTARG *)this + 2) < 0 )
      return 5;
  }
  else
  {
    v6 = *((_OWORD *)this + 8);
    v15 = 1;
    v9 = v6;
  }
  v3 = (__int64 *)*((_QWORD *)this + 1);
  v2 = *((_DWORD *)this + 30) == 0;
  v10 = *((_DWORD *)this + 19);
  v12 = *((_DWORD *)this + 21);
  v13 = *((_DWORD *)this + 20);
  v14 = *((_DWORD *)this + 18);
  v4 = *v3;
  if ( v2 )
    (*(void (__fastcall **)(__int64 *, int *))(v4 + 16))(v3, &v7);
  else
    (*(void (__fastcall **)(__int64 *, int *))(v4 + 80))(v3, &v7);
  CPropertyName::Empty((CAbstractQl1Parser *)((char *)this + 88));
  CPropertyName::Empty((CAbstractQl1Parser *)((char *)this + 128));
  VariantClear((VARIANTARG *)this + 2);
  VariantClear(&pvarg);
  result = 0;
  *(_QWORD *)((char *)this + 76) = 0;
  *((_DWORD *)this + 21) = 0;
  *((_DWORD *)this + 40) = 0;
  return result;
}

```

## disassembly

```asm
0x1800087b0  push    rbp
0x1800087b2  push    rbx
0x1800087b3  push    rsi
0x1800087b4  push    rdi
0x1800087b5  push    r14
0x1800087b7  mov     rbp, rsp
0x1800087ba  sub     rsp, 80h
0x1800087c1  xor     edx, edx; Val
0x1800087c3  mov     rbx, rcx
0x1800087c6  lea     rcx, [rbp+var_60]; void *
0x1800087ca  lea     r8d, [rdx+58h]; Size
0x1800087ce  call    memset_0
0x1800087d3  lea     rcx, [rbp+var_60]; struct _tag_WbemQl1Token *
0x1800087d7  call    ?InitToken@CAbstractQl1Parser@@KAXPEAU_tag_WbemQl1Token@@@Z; CAbstractQl1Parser::InitToken(_tag_WbemQl1Token *)
0x1800087dc  lea     rcx, [rbp+pvarg]; pvarg
0x1800087e0  mov     [rbp+var_60], 4
0x1800087e7  call    cs:__imp_VariantInit
0x1800087ed  cmp     dword ptr [rbx+0A0h], 0
0x1800087f4  mov     rdi, rbx
0x1800087f7  movups  xmm0, xmmword ptr [rbx+58h]
0x1800087fb  movdqu  [rbp+var_58], xmm0
0x180008800  jnz     loc_1800088AB
0x180008806  lea     rdx, [rbx+30h]; pvargSrc
0x18000880a  mov     [rbp+var_C], 0
0x180008811  lea     rcx, [rbp+pvarg]; pvargDest
0x180008815  call    cs:__imp_VariantCopy
0x18000881b  test    eax, eax
0x18000881d  js      loc_1800088C9
0x180008823  mov     rcx, [rbx+8]
0x180008827  lea     rdx, [rbp+var_60]
0x18000882b  mov     eax, 80h
0x180008830  add     rdi, rax
0x180008833  mov     eax, [rbx+4Ch]
0x180008836  cmp     dword ptr [rbx+78h], 0
0x18000883a  mov     [rbp+var_38], eax
0x18000883d  mov     eax, [rbx+54h]
0x180008840  mov     [rbp+var_18], eax
0x180008843  mov     eax, [rbx+50h]
0x180008846  mov     [rbp+var_14], eax
0x180008849  mov     eax, [rbx+48h]
0x18000884c  mov     [rbp+var_10], eax
0x18000884f  mov     rax, [rcx]
0x180008852  jnz     short loc_1800088C3
0x180008854  mov     rax, [rax+10h]
0x180008858  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000885d  lea     rcx, [rbx+58h]; this
0x180008861  call    ?Empty@CPropertyName@@QEAAXXZ; CPropertyName::Empty(void)
0x180008866  mov     rcx, rdi; this
0x180008869  call    ?Empty@CPropertyName@@QEAAXXZ; CPropertyName::Empty(void)
0x18000886e  lea     rcx, [rbx+30h]; pvarg
0x180008872  call    cs:__imp_VariantClear
0x180008878  lea     rcx, [rbp+pvarg]; pvarg
0x18000887c  call    cs:__imp_VariantClear
0x180008882  xor     eax, eax
0x180008884  mov     qword ptr [rbx+4Ch], 0
0x18000888c  mov     dword ptr [rbx+54h], 0
0x180008893  mov     dword ptr [rbx+0A0h], 0
0x18000889d  add     rsp, 80h
0x1800088a4  pop     r14
0x1800088a6  pop     rdi
0x1800088a7  pop     rsi
0x1800088a8  pop     rbx
0x1800088a9  pop     rbp
0x1800088aa  retn
0x1800088ab  movups  xmm0, xmmword ptr [rbx+80h]
0x1800088b2  mov     [rbp+var_C], 1
0x1800088b9  movdqu  [rbp+var_48], xmm0
0x1800088be  jmp     loc_180008823
0x1800088c3  mov     rax, [rax+50h]
0x1800088c7  jmp     short loc_180008858
0x1800088c9  mov     eax, 5
0x1800088ce  jmp     short loc_18000889D
```
