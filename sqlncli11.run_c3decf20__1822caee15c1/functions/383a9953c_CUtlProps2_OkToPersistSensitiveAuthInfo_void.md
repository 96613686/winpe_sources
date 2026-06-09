# CUtlProps2::OkToPersistSensitiveAuthInfo(void)

- ea: `0x383a9953c`
- end: `0x383a9963b`
- name: `?OkToPersistSensitiveAuthInfo@CUtlProps2@@QEAAFXZ`
- size: `255`
- prototype: `__int16 __fastcall(CUtlProps2 *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x383a997fc`

## callees

- `0x383a9953c`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x383a9954f`
- `OLEAUT32!__imp_VariantInit` at `0x383a9954f`
- `OLEAUT32!__imp_VariantClear` at `0x383a995f8`
- `OLEAUT32!__imp_VariantClear` at `0x383a995f8`
- `OLEAUT32!__imp_VariantCopy` at `0x383a995ec`
- `OLEAUT32!__imp_VariantCopy` at `0x383a995ec`

## pseudocode

```c
__int64 __fastcall CUtlProps2::OkToPersistSensitiveAuthInfo(CUtlProps2 *this)
{
  __int64 v2; // rax
  VARIANTARG pvarg; // [rsp+30h] [rbp-28h] BYREF
  unsigned int v5; // [rsp+80h] [rbp+28h] BYREF
  unsigned int v6; // [rsp+88h] [rbp+30h] BYREF
  unsigned int v7; // [rsp+90h] [rbp+38h] BYREF
  char v8; // [rsp+98h] [rbp+40h] BYREF

  VariantInit(&pvarg);
  v2 = *(_QWORD *)this;
  v6 = 0;
  if ( !(*(unsigned int (__fastcall **)(CUtlProps2 *, const GUID *, unsigned int *))(v2 + 32))(
          this,
          &DBPROPSET_DBINIT,
          &v5)
    && !(*(unsigned int (__fastcall **)(CUtlProps2 *, _QWORD, __int64, unsigned int *))(*(_QWORD *)this + 40LL))(
          this,
          v5,
          11,
          &v7) )
  {
    if ( (*(_DWORD *)(*(_QWORD *)(32LL * v5 + *((_QWORD *)this + 4) + 16) + 16LL * v7 + 12) & 0x80000400) != 0 )
    {
      if ( (**(int (__fastcall ***)(CUtlProps2 *, _QWORD, __int64, unsigned int *))this)(this, v5, 11, &v6) >= 0 )
        VariantCopy(&pvarg, (const VARIANTARG *)(*(_QWORD *)(*((_QWORD *)this + 6) + 24LL * v5 + 16) + 56LL * v6 + 32));
    }
    else
    {
      VariantClear(&pvarg);
      (*(void (__fastcall **)(CUtlProps2 *, _QWORD, __int64, char *, VARIANTARG *))(*(_QWORD *)this + 96LL))(
        this,
        v5,
        11,
        &v8,
        &pvarg);
    }
  }
  if ( pvarg.vt == 11 )
    return pvarg.uiVal;
  else
    return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x383a9953c  push    rbp
0x383a9953e  push    rbx
0x383a9953f  push    rsi
0x383a99540  push    rdi
0x383a99541  mov     rbp, rsp
0x383a99544  sub     rsp, 58h
0x383a99548  mov     rbx, rcx
0x383a9954b  lea     rcx, [rbp+pvarg]; pvarg
0x383a9954f  call    cs:__imp_VariantInit
0x383a99555  mov     rax, [rbx]
0x383a99558  lea     r8, [rbp+arg_0]
0x383a9955c  lea     rdx, DBPROPSET_DBINIT
0x383a99563  xor     edi, edi
0x383a99565  mov     rcx, rbx
0x383a99568  mov     [rbp+arg_8], edi
0x383a9956b  call    qword ptr [rax+20h]
0x383a9956e  lea     esi, [rdi+0Bh]
0x383a99571  test    eax, eax
0x383a99573  jnz     loc_383A9961B
0x383a99579  mov     rax, [rbx]
0x383a9957c  mov     edx, [rbp+arg_0]
0x383a9957f  lea     r9, [rbp+arg_10]
0x383a99583  mov     r8d, esi
0x383a99586  mov     rcx, rbx
0x383a99589  call    qword ptr [rax+28h]
0x383a9958c  test    eax, eax
0x383a9958e  jnz     loc_383A9961B
0x383a99594  mov     edx, [rbp+arg_0]
0x383a99597  mov     rax, [rbx+20h]
0x383a9959b  mov     ecx, [rbp+arg_10]
0x383a9959e  mov     r8d, edx
0x383a995a1  add     rcx, rcx
0x383a995a4  shl     r8, 5
0x383a995a8  mov     rax, [r8+rax+10h]
0x383a995ad  test    dword ptr [rax+rcx*8+0Ch], 80000400h
0x383a995b5  jz      short loc_383A995F4
0x383a995b7  mov     rax, [rbx]
0x383a995ba  lea     r9, [rbp+arg_8]
0x383a995be  mov     r8d, esi
0x383a995c1  mov     rcx, rbx
0x383a995c4  call    qword ptr [rax]
0x383a995c6  test    eax, eax
0x383a995c8  js      short loc_383A9961B
0x383a995ca  mov     eax, [rbp+arg_0]
0x383a995cd  mov     ecx, [rbp+arg_8]
0x383a995d0  lea     rdx, [rax+rax*2]
0x383a995d4  mov     rax, [rbx+30h]
0x383a995d8  imul    rcx, 38h ; '8'
0x383a995dc  mov     rax, [rax+rdx*8+10h]
0x383a995e1  lea     rdx, [rcx+20h]
0x383a995e5  lea     rcx, [rbp+pvarg]; pvargDest
0x383a995e9  add     rdx, rax; pvargSrc
0x383a995ec  call    cs:__imp_VariantCopy
0x383a995f2  jmp     short loc_383A9961B
0x383a995f4  lea     rcx, [rbp+pvarg]; pvarg
0x383a995f8  call    cs:__imp_VariantClear
0x383a995fe  mov     r11, [rbx]
0x383a99601  mov     edx, [rbp+arg_0]
0x383a99604  lea     rax, [rbp+pvarg]
0x383a99608  lea     r9, [rbp+arg_18]
0x383a9960c  mov     r8d, esi
0x383a9960f  mov     rcx, rbx
0x383a99612  mov     [rsp+58h+var_38], rax
0x383a99617  call    qword ptr [r11+60h]
0x383a9961b  movzx   eax, word ptr [rbp+pvarg]
0x383a9961f  test    ax, ax
0x383a99622  jz      short loc_383A9962F
0x383a99624  cmp     ax, si
0x383a99627  jnz     short loc_383A9962F
0x383a99629  movzx   eax, word ptr [rbp+pvarg+8]
0x383a9962d  jmp     short loc_383A99632
0x383a9962f  or      eax, 0FFFFFFFFh
0x383a99632  add     rsp, 58h
0x383a99636  pop     rdi
0x383a99637  pop     rsi
0x383a99638  pop     rbx
0x383a99639  pop     rbp
0x383a9963a  retn
```
