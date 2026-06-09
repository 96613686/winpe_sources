# rtFilter

- ea: `0x180075dd4`
- end: `0x180076079`
- name: `rtFilter`
- size: `677`
- prototype: `__int64 __fastcall(_WORD *, SAFEARRAY **, __int64, int, unsigned int, int, SAFEARRAY **)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180075400`

## callees

- `0x1800261b8`
- `0x1800367c4`
- `0x180037bc4`
- `0x1800439c8`
- `0x180075dd4`

## import_xrefs

- `OLEAUT32!__imp_VariantCopy` at `0x18007601e`
- `OLEAUT32!__imp_VariantCopy` at `0x18007601e`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180076043`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180076043`
- `OLEAUT32!__imp_SafeArrayLock` at `0x180075e2f`
- `OLEAUT32!__imp_SafeArrayLock` at `0x180075e2f`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180075f82`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180075fe0`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180075ffb`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180075f82`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180075fe0`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180075ffb`

## pseudocode

```c
__int64 __fastcall rtFilter(_WORD *a1, SAFEARRAY **a2, __int64 a3, int a4, unsigned int a5, int a6, SAFEARRAY **a7)
{
  unsigned int cElements; // ebp
  HRESULT ValNoThrow; // ebx
  unsigned int v12; // esi
  __int64 v13; // r14
  const VARIANTARG *pvData; // rbx
  SAFEARRAY *v15; // rcx
  char v16; // al
  unsigned int v17; // edx
  struct tagSAFEARRAY *OneDim; // rax
  SAFEARRAY *v19; // rdi
  VARIANTARG *v20; // r12
  __int64 v21; // r14
  __int64 v22; // r15
  const VARIANTARG *v24; // [rsp+40h] [rbp-58h]
  unsigned __int16 *v25; // [rsp+48h] [rbp-50h] BYREF
  _BYTE *v26; // [rsp+50h] [rbp-48h]
  int v28; // [rsp+A8h] [rbp+10h] BYREF

  v25 = 0;
  v28 = 0;
  cElements = (*a2)->rgsabound[0].cElements;
  v26 = MemAlloc(cElements);
  if ( !v26 )
    return (unsigned int)-2146828281;
  if ( *a2 )
  {
    ValNoThrow = SafeArrayLock(*a2);
    if ( ValNoThrow < 0 )
      return (unsigned int)ValNoThrow;
  }
  v12 = 0;
  v13 = 0;
  pvData = (const VARIANTARG *)(*a2)->pvData;
  v24 = pvData;
  while ( 1 )
  {
    if ( (unsigned int)v13 >= cElements )
      goto LABEL_31;
    ValNoThrow = VAR::BstrGetValNoThrow((VAR *)&pvData[v13], &v25);
    if ( ValNoThrow < 0 )
      goto LABEL_45;
    v15 = *a2;
    if ( ((*a1 - 8204) & 0xBFFF) != 0 )
      break;
    if ( !v15 )
    {
      pvData = v24;
      cElements = 0;
      v12 = 0;
LABEL_31:
      if ( *a2 )
        SafeArrayUnlock(*a2);
      if ( !a4 )
        v12 = cElements - v12;
      OneDim = psaMakeOneDim(v12);
      v19 = OneDim;
      if ( OneDim )
      {
        v20 = (VARIANTARG *)OneDim->pvData;
        v21 = 0;
        v22 = 0;
        while ( 2 )
        {
          if ( (unsigned int)v22 >= v12 || (unsigned int)v21 >= cElements )
          {
            ValNoThrow = 0;
            *a7 = v19;
            return (unsigned int)ValNoThrow;
          }
          if ( v26[v21] )
          {
            if ( !a4 )
              goto LABEL_50;
          }
          else if ( a4 )
          {
LABEL_50:
            pvData = v24;
            v21 = (unsigned int)(v21 + 1);
            continue;
          }
          break;
        }
        ValNoThrow = VariantCopy(&v20[v22], &pvData[v21]);
        if ( ValNoThrow < 0 )
        {
          SafeArrayDestroy(v19);
          return (unsigned int)ValNoThrow;
        }
        v22 = (unsigned int)(v22 + 1);
        goto LABEL_50;
      }
      return (unsigned int)-2146828281;
    }
    if ( v15->cDims != 1 )
      goto LABEL_43;
    pvData = (const VARIANTARG *)v15->pvData;
    if ( cElements >= v15->rgsabound[0].cElements )
      cElements = v15->rgsabound[0].cElements;
    v24 = (const VARIANTARG *)v15->pvData;
    if ( v12 >= cElements )
      v12 = cElements;
    if ( (unsigned int)v13 >= cElements )
      goto LABEL_31;
    if ( v25 == (unsigned __int16 *)-1LL )
    {
      v16 = 0;
      goto LABEL_29;
    }
    if ( !a3 || !*(_DWORD *)(a3 - 4) )
    {
      v28 = 0;
LABEL_27:
      ++v12;
      v16 = 1;
      goto LABEL_28;
    }
    if ( v25 )
      v17 = *((_DWORD *)v25 - 1);
    else
      v17 = 0;
    ValNoThrow = rtStandardInStr(v25, v17 >> 1, a3, a5, a6, 1, &v28);
    if ( ValNoThrow < 0 )
    {
LABEL_45:
      if ( *a2 )
        SafeArrayUnlock(*a2);
      return (unsigned int)ValNoThrow;
    }
    if ( v28 != -1 )
      goto LABEL_27;
    v16 = 0;
LABEL_28:
    pvData = v24;
LABEL_29:
    v26[v13] = v16;
    v13 = (unsigned int)(v13 + 1);
  }
  if ( v15 )
LABEL_43:
    SafeArrayUnlock(v15);
  return 2148139021LL;
}

```

## disassembly

```asm
0x180075dd4  mov     rax, rsp
0x180075dd7  mov     [rax+18h], rbx
0x180075ddb  mov     [rax+8], rcx
0x180075ddf  push    rbp
0x180075de0  push    rsi
0x180075de1  push    rdi
0x180075de2  push    r12
0x180075de4  push    r13
0x180075de6  push    r14
0x180075de8  push    r15
0x180075dea  sub     rsp, 60h
0x180075dee  mov     qword ptr [rax-50h], 0
0x180075df6  mov     r13d, r9d
0x180075df9  mov     dword ptr [rax+10h], 0
0x180075e00  mov     r15, r8
0x180075e03  mov     rax, [rdx]
0x180075e06  mov     rdi, rdx
0x180075e09  mov     ebp, [rax+18h]
0x180075e0c  mov     ecx, ebp; unsigned int
0x180075e0e  call    ?MemAlloc@@YAPEAXI@Z; MemAlloc(uint)
0x180075e13  mov     [rsp+98h+var_48], rax
0x180075e18  test    rax, rax
0x180075e1b  jnz     short loc_180075E27
0x180075e1d  mov     ebx, 800A0007h
0x180075e22  jmp     loc_18007605E
0x180075e27  mov     rcx, [rdi]; psa
0x180075e2a  test    rcx, rcx
0x180075e2d  jz      short loc_180075E45
0x180075e2f  call    cs:__imp_SafeArrayLock
0x180075e36  nop     dword ptr [rax+rax+00h]
0x180075e3b  mov     ebx, eax
0x180075e3d  test    eax, eax
0x180075e3f  js      loc_18007605E
0x180075e45  mov     rax, [rdi]
0x180075e48  xor     esi, esi
0x180075e4a  xor     r14d, r14d
0x180075e4d  mov     rbx, [rax+10h]
0x180075e51  mov     [rsp+98h+var_58], rbx
0x180075e56  cmp     r14d, ebp
0x180075e59  jnb     loc_180075F7A
0x180075e5f  lea     rax, [r14+r14*2]
0x180075e63  lea     rcx, [rbx+rax*8]; this
0x180075e67  lea     rdx, [rsp+98h+var_50]; unsigned __int16 **
0x180075e6c  call    ?BstrGetValNoThrow@VAR@@QEAAJPEAPEAG@Z; VAR::BstrGetValNoThrow(ushort * *)
0x180075e71  mov     ebx, eax
0x180075e73  test    eax, eax
0x180075e75  js      loc_180075FF3
0x180075e7b  mov     rax, [rsp+98h+arg_0]
0x180075e83  mov     ecx, 200Ch
0x180075e88  movzx   eax, word ptr [rax]
0x180075e8b  sub     ax, cx
0x180075e8e  mov     ecx, 0BFFFh
0x180075e93  test    cx, ax
0x180075e96  mov     rcx, [rdi]; psa
0x180075e99  jnz     loc_180075FDB
0x180075e9f  test    rcx, rcx
0x180075ea2  jz      loc_180075F71
0x180075ea8  mov     r8d, 1
0x180075eae  cmp     [rcx], r8w
0x180075eb2  jnz     loc_180075FE0
0x180075eb8  cmp     ebp, [rcx+18h]
0x180075ebb  mov     rbx, [rcx+10h]
0x180075ebf  cmovnb  ebp, [rcx+18h]
0x180075ec3  cmp     esi, ebp
0x180075ec5  mov     [rsp+98h+var_58], rbx
0x180075eca  cmovnb  esi, ebp
0x180075ecd  cmp     r14d, ebp
0x180075ed0  jnb     loc_180075F7A
0x180075ed6  mov     rcx, [rsp+98h+var_50]
0x180075edb  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180075edf  jnz     short loc_180075EE5
0x180075ee1  xor     al, al
0x180075ee3  jmp     short loc_180075F60
0x180075ee5  test    r15, r15
0x180075ee8  jz      short loc_180075F4A
0x180075eea  cmp     dword ptr [r15-4], 0
0x180075eef  jz      short loc_180075F4A
0x180075ef1  test    rcx, rcx
0x180075ef4  jnz     short loc_180075EFA
0x180075ef6  xor     edx, edx
0x180075ef8  jmp     short loc_180075EFD
0x180075efa  mov     edx, [rcx-4]
0x180075efd  mov     r9d, [rsp+98h+arg_20]
0x180075f05  lea     rax, [rsp+98h+arg_8]
0x180075f0d  mov     [rsp+98h+var_68], rax
0x180075f12  mov     eax, [rsp+98h+arg_28]
0x180075f19  mov     [rsp+98h+var_70], r8d
0x180075f1e  mov     r8, r15
0x180075f21  shr     edx, 1
0x180075f23  mov     [rsp+98h+var_78], eax
0x180075f27  call    rtStandardInStr
0x180075f2c  mov     ebx, eax
0x180075f2e  test    eax, eax
0x180075f30  js      loc_180075FF3
0x180075f36  cmp     [rsp+98h+arg_8], 0FFFFFFFFh
0x180075f3e  mov     r8d, 1
0x180075f44  jnz     short loc_180075F55
0x180075f46  xor     al, al
0x180075f48  jmp     short loc_180075F5B
0x180075f4a  mov     [rsp+98h+arg_8], 0
0x180075f55  add     esi, r8d
0x180075f58  mov     al, r8b
0x180075f5b  mov     rbx, [rsp+98h+var_58]
0x180075f60  mov     rcx, [rsp+98h+var_48]
0x180075f65  mov     [r14+rcx], al
0x180075f69  add     r14d, r8d
0x180075f6c  jmp     loc_180075E56
0x180075f71  mov     rbx, [rsp+98h+var_58]
0x180075f76  xor     ebp, ebp
0x180075f78  xor     esi, esi
0x180075f7a  mov     rcx, [rdi]; psa
0x180075f7d  test    rcx, rcx
0x180075f80  jz      short loc_180075F8E
0x180075f82  call    cs:__imp_SafeArrayUnlock
0x180075f89  nop     dword ptr [rax+rax+00h]
0x180075f8e  test    r13d, r13d
0x180075f91  jnz     short loc_180075F99
0x180075f93  mov     eax, ebp
0x180075f95  sub     eax, esi
0x180075f97  mov     esi, eax
0x180075f99  mov     ecx, esi; int
0x180075f9b  call    ?psaMakeOneDim@@YAPEAUtagSAFEARRAY@@J@Z; psaMakeOneDim(long)
0x180075fa0  mov     rdi, rax
0x180075fa3  test    rax, rax
0x180075fa6  jz      loc_180075E1D
0x180075fac  mov     r12, [rax+10h]
0x180075fb0  xor     r14d, r14d
0x180075fb3  xor     r15d, r15d
0x180075fb6  cmp     r15d, esi
0x180075fb9  jnb     loc_180076051
0x180075fbf  cmp     r14d, ebp
0x180075fc2  jnb     loc_180076051
0x180075fc8  mov     rcx, [rsp+98h+var_48]
0x180075fcd  cmp     byte ptr [r14+rcx], 0
0x180075fd2  jz      short loc_180076009
0x180075fd4  test    r13d, r13d
0x180075fd7  jnz     short loc_18007600E
0x180075fd9  jmp     short loc_180076033
0x180075fdb  test    rcx, rcx
0x180075fde  jz      short loc_180075FEC
0x180075fe0  call    cs:__imp_SafeArrayUnlock
0x180075fe7  nop     dword ptr [rax+rax+00h]
0x180075fec  mov     eax, 800A000Dh
0x180075ff1  jmp     short loc_180076060
0x180075ff3  mov     rcx, [rdi]; psa
0x180075ff6  test    rcx, rcx
0x180075ff9  jz      short loc_18007605E
0x180075ffb  call    cs:__imp_SafeArrayUnlock
0x180076002  nop     dword ptr [rax+rax+00h]
0x180076007  jmp     short loc_18007605E
0x180076009  test    r13d, r13d
0x18007600c  jnz     short loc_180076033
0x18007600e  lea     rax, [r14+r14*2]
0x180076012  lea     rcx, [r15+r15*2]
0x180076016  lea     rdx, [rbx+rax*8]; pvargSrc
0x18007601a  lea     rcx, [r12+rcx*8]; pvargDest
0x18007601e  call    cs:__imp_VariantCopy
0x180076025  nop     dword ptr [rax+rax+00h]
0x18007602a  mov     ebx, eax
0x18007602c  test    eax, eax
0x18007602e  js      short loc_180076040
0x180076030  inc     r15d
0x180076033  mov     rbx, [rsp+98h+var_58]
0x180076038  inc     r14d
0x18007603b  jmp     loc_180075FB6
0x180076040  mov     rcx, rdi; psa
0x180076043  call    cs:__imp_SafeArrayDestroy
0x18007604a  nop     dword ptr [rax+rax+00h]
0x18007604f  jmp     short loc_18007605E
0x180076051  mov     rax, [rsp+98h+arg_30]
0x180076059  xor     ebx, ebx
0x18007605b  mov     [rax], rdi
0x18007605e  mov     eax, ebx
0x180076060  mov     rbx, [rsp+98h+arg_10]
0x180076068  add     rsp, 60h
0x18007606c  pop     r15
0x18007606e  pop     r14
0x180076070  pop     r13
0x180076072  pop     r12
0x180076074  pop     rdi
0x180076075  pop     rsi
0x180076076  pop     rbp
0x180076077  retn
```
