# VssSafeDuplicateStr(CVssFunctionTracer &,ushort * &,ushort const *)

- ea: `0x180017284`
- end: `0x180017408`
- name: `?VssSafeDuplicateStr@@YAXAEAVCVssFunctionTracer@@AEAPEAGPEBG@Z`
- size: `388`
- prototype: `void(struct CVssFunctionTracer *, unsigned __int16 **, const unsigned __int16 *)`
- caller_count: `13`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180016550`
- `0x18001b380`
- `0x18001d23c`
- `0x180034484`
- `0x18003a5a0`
- `0x18003a69c`
- `0x18003a790`
- `0x18003a894`
- `0x18003a9f4`
- `0x18003ae94`
- `0x18003b0ec`
- `0x18003b348`
- `0x18003b5e8`

## callees

- `0x18000212c`
- `0x180007604`
- `0x180017284`
- `0x18003649c`
- `0x180037080`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800172eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800172eb`

## string_xrefs

- `0x1800173ec`: `StringCchCopy(%s, %d, %s) failed`

## pseudocode

```c
void __fastcall VssSafeDuplicateStr(struct CVssFunctionTracer *a1, unsigned __int16 **a2, const unsigned __int16 *a3)
{
  __int64 v6; // rbx
  __int64 v7; // rcx
  unsigned __int16 *v8; // rax
  __int64 v9; // rdx
  int v10; // r14d
  __int64 v11; // rsi
  const wchar_t *v12; // [rsp+40h] [rbp-79h] BYREF
  const wchar_t *v13; // [rsp+48h] [rbp-71h]
  const wchar_t *v14; // [rsp+50h] [rbp-69h]
  int v15; // [rsp+58h] [rbp-61h]
  int v16; // [rsp+5Ch] [rbp-5Dh]
  int v17; // [rsp+60h] [rbp-59h]
  _BYTE v18[120]; // [rsp+68h] [rbp-51h] BYREF
  int v19; // [rsp+E0h] [rbp+27h]

  if ( a3 )
  {
    v6 = -1;
    v7 = -1;
    do
      ++v7;
    while ( a3[v7] );
    v8 = (unsigned __int16 *)CoTaskMemAlloc(2 * v7 + 2);
    *a2 = v8;
    if ( !v8 )
    {
      v15 = 84;
      v12 = L"base\\stor\\vss\\inc\\vs_str.hxx";
      v16 = 11;
      v17 = 255;
      v13 = L"VssSafeDuplicateStr";
      v14 = L"INCSTRH";
      v19 = 0x1000000;
      memset_0(v18, 0, sizeof(v18));
      CVssFunctionTracer::Throw(a1, &v12, 2147942414LL, L"Memory allocation error");
    }
    v9 = -1;
    do
      ++v9;
    while ( a3[v9] );
    v10 = StringCchCopyW(v8, v9 + 1, a3);
    if ( v10 < 0 )
    {
      v11 = (__int64)*a2;
      v12 = L"base\\stor\\vss\\inc\\vs_str.hxx";
      v15 = 88;
      v16 = 11;
      v13 = L"VssSafeDuplicateStr";
      v14 = L"INCSTRH";
      v17 = 255;
      v19 = 0x1000000;
      memset_0(v18, 0, sizeof(v18));
      do
        ++v6;
      while ( a3[v6] );
      CVssFunctionTracer::TranslateGenericError(
        a1,
        &v12,
        (unsigned int)v10,
        L"StringCchCopy(%s, %d, %s) failed",
        v11,
        v6 + 1,
        a3);
    }
  }
  else
  {
    *a2 = 0;
  }
}

```

## disassembly

```asm
0x180017284  mov     [rsp-8+arg_0], rbx
0x180017289  mov     [rsp-8+arg_8], rsi
0x18001728e  push    rbp
0x18001728f  push    rdi
0x180017290  push    r12
0x180017292  push    r14
0x180017294  push    r15
0x180017296  lea     rbp, [rsp-37h]
0x18001729b  sub     rsp, 0F0h
0x1800172a2  xor     r12d, r12d
0x1800172a5  mov     rdi, r8
0x1800172a8  mov     rsi, rdx
0x1800172ab  mov     r15, rcx
0x1800172ae  test    r8, r8
0x1800172b1  jnz     short loc_1800172D2
0x1800172b3  mov     [rdx], r12
0x1800172b6  lea     r11, [rsp+110h+var_20]
0x1800172be  mov     rbx, [r11+30h]
0x1800172c2  mov     rsi, [r11+38h]
0x1800172c6  mov     rsp, r11
0x1800172c9  pop     r15
0x1800172cb  pop     r14
0x1800172cd  pop     r12
0x1800172cf  pop     rdi
0x1800172d0  pop     rbp
0x1800172d1  retn
0x1800172d2  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800172d6  mov     rcx, rbx
0x1800172d9  inc     rcx
0x1800172dc  cmp     [r8+rcx*2], r12w
0x1800172e1  jnz     short loc_1800172D9
0x1800172e3  lea     rcx, ds:2[rcx*2]; cb
0x1800172eb  call    cs:__imp_CoTaskMemAlloc
0x1800172f1  mov     [rsi], rax
0x1800172f4  test    rax, rax
0x1800172f7  jnz     short loc_18001735F
0x1800172f9  lea     rax, aBaseStorVssInc_1; "base\\stor\\vss\\inc\\vs_str.hxx"
0x180017300  mov     [rbp+57h+var_B8], 54h ; 'T'
0x180017307  mov     [rbp+57h+var_D0], rax
0x18001730b  lea     rcx, [rbp+57h+var_A8]; void *
0x18001730f  xor     edx, edx; Val
0x180017311  mov     [rbp+57h+var_B4], 0Bh
0x180017318  lea     rax, aVsssafeduplica; "VssSafeDuplicateStr"
0x18001731f  mov     [rbp+57h+var_B0], 0FFh
0x180017326  mov     [rbp+57h+var_C8], rax
0x18001732a  lea     rax, aIncstrh; "INCSTRH"
0x180017331  mov     [rbp+57h+var_C0], rax
0x180017335  lea     r8d, [rdx+78h]; Size
0x180017339  mov     [rbp+57h+var_30], 1000000h
0x180017340  call    memset_0
0x180017345  lea     r9, aMemoryAllocati; "Memory allocation error"
0x18001734c  mov     r8d, 8007000Eh
0x180017352  lea     rdx, [rbp+57h+var_D0]
0x180017356  mov     rcx, r15
0x180017359  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x18001735f  mov     rdx, rbx
0x180017362  inc     rdx
0x180017365  cmp     [rdi+rdx*2], r12w
0x18001736a  jnz     short loc_180017362
0x18001736c  inc     rdx; unsigned __int64
0x18001736f  mov     r8, rdi; unsigned __int16 *
0x180017372  mov     rcx, rax; unsigned __int16 *
0x180017375  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001737a  mov     r14d, eax
0x18001737d  test    eax, eax
0x18001737f  jns     loc_1800172B6
0x180017385  mov     rsi, [rsi]
0x180017388  lea     rax, aBaseStorVssInc_1; "base\\stor\\vss\\inc\\vs_str.hxx"
0x18001738f  mov     [rbp+57h+var_D0], rax
0x180017393  lea     rcx, [rbp+57h+var_A8]; void *
0x180017397  xor     edx, edx; Val
0x180017399  mov     [rbp+57h+var_B8], 58h ; 'X'
0x1800173a0  lea     rax, aVsssafeduplica; "VssSafeDuplicateStr"
0x1800173a7  mov     [rbp+57h+var_B4], 0Bh
0x1800173ae  mov     [rbp+57h+var_C8], rax
0x1800173b2  lea     rax, aIncstrh; "INCSTRH"
0x1800173b9  mov     [rbp+57h+var_C0], rax
0x1800173bd  lea     r8d, [rdx+78h]; Size
0x1800173c1  mov     [rbp+57h+var_B0], 0FFh
0x1800173c8  mov     [rbp+57h+var_30], 1000000h
0x1800173cf  call    memset_0
0x1800173d4  inc     rbx
0x1800173d7  cmp     [rdi+rbx*2], r12w
0x1800173dc  jnz     short loc_1800173D4
0x1800173de  lea     rax, [rbx+1]
0x1800173e2  mov     [rsp+110h+var_E0], rdi
0x1800173e7  mov     [rsp+110h+var_E8], rax
0x1800173ec  lea     r9, aStringcchcopyS; "StringCchCopy(%s, %d, %s) failed"
0x1800173f3  mov     r8d, r14d
0x1800173f6  mov     [rsp+110h+var_F0], rsi
0x1800173fb  lea     rdx, [rbp+57h+var_D0]
0x1800173ff  mov     rcx, r15
0x180017402  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
```
