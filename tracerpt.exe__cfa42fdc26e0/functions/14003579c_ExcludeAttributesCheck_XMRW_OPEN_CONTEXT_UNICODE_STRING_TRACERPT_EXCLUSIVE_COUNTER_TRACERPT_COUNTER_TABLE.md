# ExcludeAttributesCheck(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_EXCLUSIVE_COUNTER *,_TRACERPT_COUNTER_TABLE *)

- ea: `0x14003579c`
- end: `0x140035877`
- name: `?ExcludeAttributesCheck@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_EXCLUSIVE_COUNTER@@PEAU_TRACERPT_COUNTER_TABLE@@@Z`
- size: `219`
- prototype: `unsigned int __fastcall(struct _XMRW_OPEN_CONTEXT *, struct _UNICODE_STRING *, struct _TRACERPT_EXCLUSIVE_COUNTER *, struct _TRACERPT_COUNTER_TABLE *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140035880`

## callees

- `0x140016808`
- `0x14003552c`
- `0x140035658`
- `0x14003579c`
- `0x140041010`

## pseudocode

```c
unsigned int __fastcall ExcludeAttributesCheck(
        struct _XMRW_OPEN_CONTEXT *a1,
        struct _UNICODE_STRING *a2,
        struct _TRACERPT_EXCLUSIVE_COUNTER *a3,
        struct _TRACERPT_COUNTER_TABLE *a4)
{
  __int64 v5; // rcx
  struct _UNICODE_STRING v9; // xmm0
  struct _UNICODE_STRING v11; // [rsp+20h] [rbp-20h] BYREF
  struct _UNICODE_STRING v12; // [rsp+30h] [rbp-10h] BYREF
  int v13; // [rsp+60h] [rbp+20h] BYREF
  WCHAR *v14; // [rsp+68h] [rbp+28h] BYREF

  v14 = 0;
  v5 = *((_QWORD *)a1 + 3);
  v13 = 0;
  v11 = 0;
  (*(void (__fastcall **)(__int64, WCHAR **, int *))(*(_QWORD *)v5 + 128LL))(v5, &v14, &v13);
  v9 = *a2;
  v11.Buffer = v14;
  v11.MaximumLength = 2 * v13;
  v11.Length = 2 * v13;
  v12 = v9;
  if ( EqualString(&v12, L"counter", 0) )
    return ExcludeAttributeCounter(a1, &v11, a3);
  v12 = *a2;
  if ( EqualString(&v12, L"column", 0) )
    return ExcludeAttributeColumn(&v11, a4);
  else
    return 0;
}

```

## disassembly

```asm
0x14003579c  mov     [rsp-18h+arg_10], rbx
0x1400357a1  mov     [rsp-18h+arg_18], rsi
0x1400357a6  push    rbp
0x1400357a7  push    rdi
0x1400357a8  push    r14
0x1400357aa  mov     rbp, rsp
0x1400357ad  sub     rsp, 40h
0x1400357b1  mov     rbx, rcx
0x1400357b4  mov     [rbp+arg_8], 0
0x1400357bc  mov     rcx, [rcx+18h]
0x1400357c0  xorps   xmm0, xmm0
0x1400357c3  mov     [rbp+arg_0], 0
0x1400357ca  mov     r14, r8
0x1400357cd  movups  xmmword ptr [rbp+var_20.Length], xmm0
0x1400357d1  mov     rdi, rdx
0x1400357d4  lea     r8, [rbp+arg_0]
0x1400357d8  mov     rax, [rcx]
0x1400357db  lea     rdx, [rbp+arg_8]
0x1400357df  mov     rsi, r9
0x1400357e2  mov     rax, [rax+80h]
0x1400357e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400357ee  mov     rax, [rbp+arg_8]
0x1400357f2  lea     rdx, aCounter; "counter"
0x1400357f9  movups  xmm0, xmmword ptr [rdi]
0x1400357fc  mov     [rbp+var_20.Buffer], rax
0x140035800  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140035804  movzx   eax, word ptr [rbp+arg_0]
0x140035808  xor     r8d, r8d; unsigned __int8
0x14003580b  add     ax, ax
0x14003580e  mov     [rbp+var_20.MaximumLength], ax
0x140035812  mov     [rbp+var_20.Length], ax
0x140035816  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x14003581b  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140035820  test    al, al
0x140035822  jz      short loc_140035835
0x140035824  mov     r8, r14; struct _TRACERPT_EXCLUSIVE_COUNTER *
0x140035827  lea     rdx, [rbp+var_20]; struct _UNICODE_STRING *
0x14003582b  mov     rcx, rbx; struct _XMRW_OPEN_CONTEXT *
0x14003582e  call    ?ExcludeAttributeCounter@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_EXCLUSIVE_COUNTER@@@Z; ExcludeAttributeCounter(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_EXCLUSIVE_COUNTER *)
0x140035833  jmp     short loc_140035864
0x140035835  movups  xmm0, xmmword ptr [rdi]
0x140035838  xor     r8d, r8d; unsigned __int8
0x14003583b  lea     rdx, aColumn; "column"
0x140035842  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140035846  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x14003584b  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140035850  test    al, al
0x140035852  jz      short loc_140035862
0x140035854  mov     rdx, rsi; struct _TRACERPT_COUNTER_TABLE *
0x140035857  lea     rcx, [rbp+var_20]; struct _UNICODE_STRING *
0x14003585b  call    ?ExcludeAttributeColumn@@YAKAEAU_UNICODE_STRING@@PEAU_TRACERPT_COUNTER_TABLE@@@Z; ExcludeAttributeColumn(_UNICODE_STRING &,_TRACERPT_COUNTER_TABLE *)
0x140035860  jmp     short loc_140035864
0x140035862  xor     eax, eax
0x140035864  mov     rbx, [rsp+40h+arg_10]
0x140035869  mov     rsi, [rsp+40h+arg_18]
0x14003586e  add     rsp, 40h
0x140035872  pop     r14
0x140035874  pop     rdi
0x140035875  pop     rbp
0x140035876  retn
```
