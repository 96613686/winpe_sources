# DLPToken::SetPron(CEngineLocaleHandlerJPN *)

- ea: `0x1800dfcc0`
- end: `0x1800dfed7`
- name: `?SetPron@DLPToken@@QEAAJPEAVCEngineLocaleHandlerJPN@@@Z`
- size: `535`
- prototype: `__int64 __fastcall(DLPToken *__hidden this, struct CEngineLocaleHandlerJPN *)`
- caller_count: `6`
- callee_count: `11`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800de1b0`
- `0x1800de9f0`
- `0x1800deba0`
- `0x1800ded40`
- `0x1800deef0`
- `0x1800dfad0`

## callees

- `0x180002470`
- `0x180002e00`
- `0x1800034b0`
- `0x1800060c0`
- `0x1800141c0`
- `0x1800dbb28`
- `0x1800dc284`
- `0x1800dfcc0`
- `0x1800dfee0`
- `0x1800ff490`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dfea0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dfea0`

## pseudocode

```c
__int64 __fastcall DLPToken::SetPron(DLPToken *this, struct CEngineLocaleHandlerJPN *a2)
{
  __int64 v2; // rbx
  __int64 v4; // rcx
  __int64 v5; // rax
  __int64 v7; // rcx
  unsigned __int64 v8; // rsi
  SIZE_T v9; // rax
  unsigned __int16 *v10; // rbp
  unsigned int v11; // esi
  unsigned __int16 *v12; // rcx
  int v13; // eax
  DLPToken *v14; // rcx
  SPPHONEID *szPronunciation; // rdx
  __int64 v16; // r8
  __int64 v17; // rax
  __int64 v18; // rax
  struct SPWORDPRONUNCIATIONLIST pv; // [rsp+30h] [rbp-1B78h] BYREF
  _WORD v21[392]; // [rsp+50h] [rbp-1B58h] BYREF
  _BYTE v22[6160]; // [rsp+360h] [rbp-1848h] BYREF

  v2 = -1;
  v4 = *((_QWORD *)this + 2);
  v5 = -1;
  do
    ++v5;
  while ( *(_WORD *)(v4 + 2 * v5) );
  v7 = -1;
  do
    ++v7;
  while ( *(_WORD *)(*((_QWORD *)this + 3) + 2 * v7) );
  v8 = v5 + v7 + 4;
  v9 = 2 * v8;
  if ( !is_mul_ok(v8, 2u) )
    v9 = -1;
  v10 = (unsigned __int16 *)CWinHeap::Alloc(&g_heap, v9, 0);
  if ( v10 )
  {
    CEngineLocaleHandlerJPN::HalfwidthFromFullwidth(*((unsigned __int16 **)this + 2));
    v12 = (unsigned __int16 *)*((_QWORD *)this + 3);
    if ( *v12 )
    {
      CEngineLocaleHandlerJPN::HalfwidthFromFullwidth(v12);
      v13 = StringCchPrintfW(v10, v8, L"/%s/%s;", *((_QWORD *)this + 2), *((_QWORD *)this + 3));
    }
    else
    {
      v13 = StringCchCopyW(v10, v8, *((const unsigned __int16 **)this + 2));
    }
    v11 = v13;
    if ( v13 >= 0 )
    {
      memset(&pv, 0, sizeof(pv));
      if ( (int)CEngineLocaleHandlerJPN::GetPronunciationsOneWord(a2, v10, 0x1000u, &pv, 1) < 0 )
      {
        v16 = 0;
        szPronunciation = (SPPHONEID *)&word_18010FB50;
      }
      else if ( pv.pFirstWordPronunciation->eLexiconType >= eLEXTYPE_PRIVATE1 )
      {
        v17 = (*(__int64 (__fastcall **)(struct CEngineLocaleHandlerJPN *, __int64))(*(_QWORD *)a2 + 368LL))(a2, 4096);
        if ( (*(int (__fastcall **)(__int64, SPPHONEID *, _BYTE *))(*(_QWORD *)v17 + 48LL))(
               v17,
               pv.pFirstWordPronunciation->szPronunciation,
               v22) >= 0 )
        {
          v18 = (*(__int64 (__fastcall **)(struct CEngineLocaleHandlerJPN *, __int64))(*(_QWORD *)a2 + 368LL))(a2, 1);
          (*(void (__fastcall **)(__int64, _BYTE *, _WORD *))(*(_QWORD *)v18 + 40LL))(v18, v22, v21);
        }
        do
          ++v2;
        while ( v21[v2] );
        v16 = v2;
        szPronunciation = v21;
      }
      else
      {
        szPronunciation = pv.pFirstWordPronunciation->szPronunciation;
        do
          ++v2;
        while ( szPronunciation[v2] );
        v16 = v2;
      }
      v11 = DLPToken::SetString(v14, szPronunciation, v16, (unsigned __int16 **)this + 4);
      if ( pv.pvBuffer )
        CoTaskMemFree(pv.pvBuffer);
    }
  }
  else
  {
    v11 = -2147024882;
  }
  operator delete(v10);
  return v11;
}

```

## disassembly

```asm
0x1800dfcc0  mov     [rsp+arg_10], rbx
0x1800dfcc5  push    rbp
0x1800dfcc6  push    rsi
0x1800dfcc7  push    rdi
0x1800dfcc8  push    r14
0x1800dfcca  push    r15
0x1800dfccc  mov     eax, 1B80h
0x1800dfcd1  call    _alloca_probe
0x1800dfcd6  sub     rsp, rax
0x1800dfcd9  mov     rax, cs:__security_cookie
0x1800dfce0  xor     rax, rsp
0x1800dfce3  mov     [rsp+1BA8h+var_38], rax
0x1800dfceb  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800dfcef  mov     rdi, rcx
0x1800dfcf2  mov     rcx, [rcx+10h]
0x1800dfcf6  mov     rax, rbx
0x1800dfcf9  xor     r15d, r15d
0x1800dfcfc  mov     r14, rdx
0x1800dfcff  inc     rax
0x1800dfd02  cmp     [rcx+rax*2], r15w
0x1800dfd07  jnz     short loc_1800DFCFF
0x1800dfd09  mov     rdx, [rdi+18h]
0x1800dfd0d  mov     rcx, rbx
0x1800dfd10  inc     rcx
0x1800dfd13  cmp     [rdx+rcx*2], r15w
0x1800dfd18  jnz     short loc_1800DFD10
0x1800dfd1a  lea     rsi, [rcx+4]
0x1800dfd1e  add     rsi, rax
0x1800dfd21  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x1800dfd28  mov     eax, 2
0x1800dfd2d  mul     rsi
0x1800dfd30  cmovb   rax, rbx
0x1800dfd34  xor     r8d, r8d; bool
0x1800dfd37  mov     rdx, rax; unsigned __int64
0x1800dfd3a  call    ?Alloc@CWinHeap@@QEAAPEAX_K_N@Z; CWinHeap::Alloc(unsigned __int64,bool)
0x1800dfd3f  mov     rbp, rax
0x1800dfd42  test    rax, rax
0x1800dfd45  jnz     short loc_1800DFD51
0x1800dfd47  mov     esi, 8007000Eh
0x1800dfd4c  jmp     loc_1800DFEA6
0x1800dfd51  mov     rcx, [rdi+10h]; unsigned __int16 *
0x1800dfd55  call    ?HalfwidthFromFullwidth@CEngineLocaleHandlerJPN@@SAXPEAG@Z; CEngineLocaleHandlerJPN::HalfwidthFromFullwidth(ushort *)
0x1800dfd5a  mov     rcx, [rdi+18h]; unsigned __int16 *
0x1800dfd5e  cmp     [rcx], r15w
0x1800dfd62  jz      short loc_1800DFD8A
0x1800dfd64  call    ?HalfwidthFromFullwidth@CEngineLocaleHandlerJPN@@SAXPEAG@Z; CEngineLocaleHandlerJPN::HalfwidthFromFullwidth(ushort *)
0x1800dfd69  mov     r8, [rdi+18h]
0x1800dfd6d  mov     rdx, rsi; unsigned __int64
0x1800dfd70  mov     r9, [rdi+10h]
0x1800dfd74  mov     rcx, rbp; unsigned __int16 *
0x1800dfd77  mov     qword ptr [rsp+1BA8h+var_1B88], r8
0x1800dfd7c  lea     r8, aSS_1; "/%s/%s;"
0x1800dfd83  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800dfd88  jmp     short loc_1800DFD99
0x1800dfd8a  mov     r8, [rdi+10h]; unsigned __int16 *
0x1800dfd8e  mov     rdx, rsi; unsigned __int64
0x1800dfd91  mov     rcx, rbp; unsigned __int16 *
0x1800dfd94  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800dfd99  mov     esi, eax
0x1800dfd9b  test    eax, eax
0x1800dfd9d  js      loc_1800DFEA6
0x1800dfda3  xorps   xmm0, xmm0
0x1800dfda6  mov     [rsp+1BA8h+var_1B88], 1; int
0x1800dfdae  xor     eax, eax
0x1800dfdb0  lea     r9, [rsp+1BA8h+pv]; struct SPWORDPRONUNCIATIONLIST *
0x1800dfdb5  mov     esi, 1000h
0x1800dfdba  mov     [rsp+1BA8h+var_1B68], rax
0x1800dfdbf  mov     r8d, esi; unsigned int
0x1800dfdc2  mov     rdx, rbp; Str
0x1800dfdc5  mov     rcx, r14; this
0x1800dfdc8  movups  xmmword ptr [rsp+1BA8h+pv], xmm0
0x1800dfdcd  call    ?GetPronunciationsOneWord@CEngineLocaleHandlerJPN@@QEAAJPEBGKPEAUSPWORDPRONUNCIATIONLIST@@H@Z; CEngineLocaleHandlerJPN::GetPronunciationsOneWord(ushort const *,ulong,SPWORDPRONUNCIATIONLIST *,int)
0x1800dfdd2  test    eax, eax
0x1800dfdd4  js      loc_1800DFE81
0x1800dfdda  mov     rax, [rsp+1BA8h+var_1B68]
0x1800dfddf  cmp     [rax+8], esi
0x1800dfde2  jge     short loc_1800DFDFA
0x1800dfde4  lea     rdx, [rax+14h]
0x1800dfde8  inc     rbx
0x1800dfdeb  cmp     [rdx+rbx*2], r15w
0x1800dfdf0  jnz     short loc_1800DFDE8
0x1800dfdf2  mov     r8, rbx
0x1800dfdf5  jmp     loc_1800DFE8B
0x1800dfdfa  mov     rax, [r14]
0x1800dfdfd  mov     edx, esi
0x1800dfdff  mov     rcx, r14
0x1800dfe02  mov     rax, [rax+170h]
0x1800dfe09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dfe0e  mov     rdx, [rsp+1BA8h+var_1B68]
0x1800dfe13  mov     rcx, rax
0x1800dfe16  add     rdx, 14h
0x1800dfe1a  mov     r8, [rax]
0x1800dfe1d  mov     rax, [r8+30h]
0x1800dfe21  lea     r8, [rsp+1BA8h+var_1848]
0x1800dfe29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dfe2e  test    eax, eax
0x1800dfe30  js      short loc_1800DFE68
0x1800dfe32  mov     rax, [r14]
0x1800dfe35  mov     edx, 1
0x1800dfe3a  mov     rcx, r14
0x1800dfe3d  mov     rax, [rax+170h]
0x1800dfe44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dfe49  mov     r9, rax
0x1800dfe4c  lea     r8, [rsp+1BA8h+var_1B58]
0x1800dfe51  lea     rdx, [rsp+1BA8h+var_1848]
0x1800dfe59  mov     rcx, [rax]
0x1800dfe5c  mov     rax, [rcx+28h]
0x1800dfe60  mov     rcx, r9
0x1800dfe63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dfe68  lea     rax, [rsp+1BA8h+var_1B58]
0x1800dfe6d  inc     rbx
0x1800dfe70  cmp     [rax+rbx*2], r15w
0x1800dfe75  jnz     short loc_1800DFE6D
0x1800dfe77  mov     r8, rbx
0x1800dfe7a  lea     rdx, [rsp+1BA8h+var_1B58]
0x1800dfe7f  jmp     short loc_1800DFE8B
0x1800dfe81  xor     r8d, r8d; unsigned __int64
0x1800dfe84  lea     rdx, word_18010FB50; unsigned __int16 *
0x1800dfe8b  lea     r9, [rdi+20h]; unsigned __int16 **
0x1800dfe8f  call    ?SetString@DLPToken@@QEAAJPEBG_KPEAPEAG@Z; DLPToken::SetString(ushort const *,unsigned __int64,ushort * *)
0x1800dfe94  mov     rcx, [rsp+1BA8h+pv+8]; pv
0x1800dfe99  mov     esi, eax
0x1800dfe9b  test    rcx, rcx
0x1800dfe9e  jz      short loc_1800DFEA6
0x1800dfea0  call    cs:__imp_CoTaskMemFree
0x1800dfea6  mov     rcx, rbp; void *
0x1800dfea9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800dfeae  mov     eax, esi
0x1800dfeb0  mov     rcx, [rsp+1BA8h+var_38]
0x1800dfeb8  xor     rcx, rsp; StackCookie
0x1800dfebb  call    __security_check_cookie
0x1800dfec0  mov     rbx, [rsp+1BA8h+arg_10]
0x1800dfec8  add     rsp, 1B80h
0x1800dfecf  pop     r15
0x1800dfed1  pop     r14
0x1800dfed3  pop     rdi
0x1800dfed4  pop     rsi
0x1800dfed5  pop     rbp
0x1800dfed6  retn
```
