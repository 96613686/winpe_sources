# _SimpleOpCompareValues(tagPROPVARIANT const &,tagPROPVARIANT const &,tagCONDITION_OPERATION,int,int *)

- ea: `0x18007f61c`
- end: `0x18007f71c`
- name: `?_SimpleOpCompareValues@@YAJAEBUtagPROPVARIANT@@0W4tagCONDITION_OPERATION@@HPEAH@Z`
- size: `256`
- prototype: `__int64 __fastcall(PROPVARIANT *propvar2, PROPVARIANT *propvar1, enum tagCONDITION_OPERATION, int, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800794b0`

## callees

- `0x18007f5ac`
- `0x18007f61c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18007f707`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18007f707`
- `PROPSYS!PropVariantCompareEx` at `0x18007f6eb`
- `PROPSYS!PropVariantCompareEx` at `0x18007f6eb`
- `PROPSYS!PropVariantChangeType` at `0x18007f6ab`
- `PROPSYS!PropVariantChangeType` at `0x18007f6cb`
- `PROPSYS!PropVariantChangeType` at `0x18007f6ab`
- `PROPSYS!PropVariantChangeType` at `0x18007f6cb`

## pseudocode

```c
__int64 __fastcall _SimpleOpCompareValues(
        PROPVARIANT *propvar2,
        PROPVARIANT *propvar1,
        enum tagCONDITION_OPERATION a3,
        int a4,
        int *a5)
{
  VARTYPE v7; // r9
  PROPVARIANT *v8; // rbx
  const PROPVARIANT *v9; // r14
  unsigned int v10; // ebx
  HRESULT v11; // eax
  PROPVARIANT *v12; // r8
  int v13; // eax
  PROPVARIANT ppropvarDest[2]; // [rsp+20h] [rbp-58h] BYREF
  __int64 v16; // [rsp+30h] [rbp-48h]

  v7 = *(_WORD *)propvar2;
  v8 = propvar1;
  v9 = propvar2;
  *a5 = 0;
  if ( v7 == *(_WORD *)propvar1 || v7 && *(_WORD *)propvar1 )
  {
    *(_OWORD *)ppropvarDest = 0;
    v16 = 0;
    if ( v7 != *(_WORD *)propvar1 && v7 != 1 && *(_WORD *)propvar1 != 1 )
    {
      if ( PropVariantChangeType(ppropvarDest, propvar1, 0, v7) < 0 )
      {
        v11 = PropVariantChangeType(ppropvarDest, v9, 0, *(_WORD *)v8);
        v12 = ppropvarDest;
        if ( v11 < 0 )
          v12 = (PROPVARIANT *)v9;
        v9 = v12;
      }
      else
      {
        v8 = ppropvarDest;
      }
    }
    v13 = PropVariantCompareEx(v8, v9, PVCU_DEFAULT, 0);
    v10 = _SimpleOpCompareResult(v13, a3, a4, a5);
    PropVariantClear(ppropvarDest);
  }
  else
  {
    v10 = 0;
    if ( a4 )
    {
      if ( a3 != COP_EQUAL )
        return v10;
      goto LABEL_8;
    }
    if ( a3 == COP_NOTEQUAL )
LABEL_8:
      *a5 = 1;
  }
  return v10;
}

```

## disassembly

```asm
0x18007f61c  push    rbx
0x18007f61e  push    rbp
0x18007f61f  push    rsi
0x18007f620  push    rdi
0x18007f621  push    r14
0x18007f623  push    r15
0x18007f625  sub     rsp, 48h
0x18007f629  mov     rsi, [rsp+78h+arg_20]
0x18007f631  xor     r15d, r15d
0x18007f634  mov     ebp, r9d
0x18007f637  mov     edi, r8d
0x18007f63a  movzx   r9d, word ptr [rcx]; vt
0x18007f63e  mov     rbx, rdx
0x18007f641  mov     r14, rcx
0x18007f644  mov     [rsi], r15d
0x18007f647  cmp     r9w, [rdx]
0x18007f64b  jz      short loc_18007F67E
0x18007f64d  test    r9w, r9w
0x18007f651  jz      short loc_18007F659
0x18007f653  cmp     [rdx], r15w
0x18007f657  jnz     short loc_18007F67E
0x18007f659  mov     ebx, r15d
0x18007f65c  mov     eax, 1
0x18007f661  test    ebp, ebp
0x18007f663  jz      short loc_18007F66E
0x18007f665  cmp     edi, eax
0x18007f667  jz      short loc_18007F677
0x18007f669  jmp     loc_18007F70D
0x18007f66e  cmp     edi, 2
0x18007f671  jnz     loc_18007F70D
0x18007f677  mov     [rsi], eax
0x18007f679  jmp     loc_18007F70D
0x18007f67e  xor     eax, eax
0x18007f680  xorps   xmm0, xmm0
0x18007f683  movups  xmmword ptr [rsp+78h+ppropvarDest], xmm0
0x18007f688  mov     [rsp+78h+var_48], rax
0x18007f68d  cmp     r9w, [rdx]
0x18007f691  jz      short loc_18007F6DF
0x18007f693  mov     eax, 1
0x18007f698  cmp     r9w, ax
0x18007f69c  jz      short loc_18007F6DF
0x18007f69e  cmp     [rdx], ax
0x18007f6a1  jz      short loc_18007F6DF
0x18007f6a3  xor     r8d, r8d; flags
0x18007f6a6  lea     rcx, [rsp+78h+ppropvarDest]; ppropvarDest
0x18007f6ab  call    cs:__imp_PropVariantChangeType
0x18007f6b1  test    eax, eax
0x18007f6b3  js      short loc_18007F6BC
0x18007f6b5  lea     rbx, [rsp+78h+ppropvarDest]
0x18007f6ba  jmp     short loc_18007F6DF
0x18007f6bc  movzx   r9d, word ptr [rbx]; vt
0x18007f6c0  lea     rcx, [rsp+78h+ppropvarDest]; ppropvarDest
0x18007f6c5  xor     r8d, r8d; flags
0x18007f6c8  mov     rdx, r14; propvarSrc
0x18007f6cb  call    cs:__imp_PropVariantChangeType
0x18007f6d1  test    eax, eax
0x18007f6d3  lea     r8, [rsp+78h+ppropvarDest]
0x18007f6d8  cmovs   r8, r14
0x18007f6dc  mov     r14, r8
0x18007f6df  xor     r9d, r9d; flags
0x18007f6e2  xor     r8d, r8d; unit
0x18007f6e5  mov     rdx, r14; propvar2
0x18007f6e8  mov     rcx, rbx; propvar1
0x18007f6eb  call    cs:__imp_PropVariantCompareEx
0x18007f6f1  mov     r9, rsi; int *
0x18007f6f4  mov     r8d, ebp; int
0x18007f6f7  mov     ecx, eax; int
0x18007f6f9  mov     edx, edi; enum tagCONDITION_OPERATION
0x18007f6fb  call    ?_SimpleOpCompareResult@@YAJHW4tagCONDITION_OPERATION@@HPEAH@Z; _SimpleOpCompareResult(int,tagCONDITION_OPERATION,int,int *)
0x18007f700  lea     rcx, [rsp+78h+ppropvarDest]; pvar
0x18007f705  mov     ebx, eax
0x18007f707  call    cs:__imp_PropVariantClear
0x18007f70d  mov     eax, ebx
0x18007f70f  add     rsp, 48h
0x18007f713  pop     r15
0x18007f715  pop     r14
0x18007f717  pop     rdi
0x18007f718  pop     rsi
0x18007f719  pop     rbp
0x18007f71a  pop     rbx
0x18007f71b  retn
```
