# CIconicAnimatedVisual::SetIconicData(CWindowData *,tagRECT const *,TMILFlagsEnum<SWRUsage::FlagsEnum> *)

- ea: `0x1800b907c`
- end: `0x1800b9137`
- name: `?SetIconicData@CIconicAnimatedVisual@@QEAAJPEAVCWindowData@@PEBUtagRECT@@PEAU?$TMILFlagsEnum@W4FlagsEnum@SWRUsage@@@@@Z`
- size: `187`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18001b010`
- `0x1800cee28`

## callees

- `0x180010204`
- `0x180017100`
- `0x1800b907c`

## import_xrefs

- `USER32!SetRectEmpty` at `0x1800b90bf`
- `USER32!SetRectEmpty` at `0x1800b90cf`
- `USER32!SetRectEmpty` at `0x1800b90bf`
- `USER32!SetRectEmpty` at `0x1800b90cf`

## pseudocode

```c
__int64 __fastcall CIconicAnimatedVisual::SetIconicData(__int64 a1, __int64 a2, _OWORD *a3, _DWORD *a4)
{
  unsigned int *v8; // rax
  _OWORD *v9; // rbx
  int v10; // ecx
  int v11; // ecx
  char v13; // [rsp+40h] [rbp+8h] BYREF

  v8 = (unsigned int *)___ConvertDirtyEnumToFlag__MW4DTCVIDirtyFlags_CDesktopThumbnailCVIVisual__09_00__YA_AVDirtyFlags__XZ(&v13);
  CVisual::SetDirtyFlags(a1, *v8);
  *(_QWORD *)(a1 + 224) = a2;
  v9 = (_OWORD *)(a1 + 248);
  SetRectEmpty((LPRECT)(a1 + 248));
  SetRectEmpty((LPRECT)(a1 + 264));
  if ( a3 )
  {
    *v9 = *a3;
    if ( *(int *)a3 < 0 )
    {
      if ( (*a4 & 0x2000) == 0 )
      {
        v10 = *(_DWORD *)v9;
        *(_OWORD *)(a1 + 264) = *a3;
        v11 = v10 - *(_DWORD *)a3;
        *(_DWORD *)(a1 + 256) += *(_DWORD *)a3;
        if ( v11 >= *(_DWORD *)(a1 + 256) )
          v11 = *(_DWORD *)(a1 + 256);
        *(_DWORD *)v9 = v11;
      }
      goto LABEL_8;
    }
  }
  if ( a4 )
LABEL_8:
    *(_DWORD *)(a1 + 280) = *a4;
  return 0;
}

```

## disassembly

```asm
0x1800b907c  mov     [rsp+arg_8], rbx
0x1800b9081  mov     [rsp+arg_10], rbp
0x1800b9086  push    rsi
0x1800b9087  push    rdi
0x1800b9088  push    r14
0x1800b908a  sub     rsp, 20h
0x1800b908e  mov     rdi, rcx
0x1800b9091  mov     rsi, r9
0x1800b9094  lea     rcx, [rsp+38h+arg_0]
0x1800b9099  mov     r14, r8
0x1800b909c  mov     rbx, rdx
0x1800b909f  call    ??$ConvertDirtyEnumToFlag@$MW4DTCVIDirtyFlags@CDesktopThumbnailCVIVisual@@09$00@@YA?AVDirtyFlags@@XZ
0x1800b90a4  mov     rcx, rdi
0x1800b90a7  mov     edx, [rax]
0x1800b90a9  call    ?SetDirtyFlags@CVisual@@MEAAXVDirtyFlags@@@Z; CVisual::SetDirtyFlags(DirtyFlags)
0x1800b90ae  mov     [rdi+0E0h], rbx
0x1800b90b5  lea     rbx, [rdi+0F8h]
0x1800b90bc  mov     rcx, rbx; lprc
0x1800b90bf  call    cs:__imp_SetRectEmpty
0x1800b90c5  lea     rbp, [rdi+108h]
0x1800b90cc  mov     rcx, rbp; lprc
0x1800b90cf  call    cs:__imp_SetRectEmpty
0x1800b90d5  test    r14, r14
0x1800b90d8  jz      short loc_1800B9115
0x1800b90da  movups  xmm0, xmmword ptr [r14]
0x1800b90de  movdqu  xmmword ptr [rbx], xmm0
0x1800b90e2  cmp     dword ptr [r14], 0
0x1800b90e6  jge     short loc_1800B9115
0x1800b90e8  test    dword ptr [rsi], 2000h
0x1800b90ee  jnz     short loc_1800B911A
0x1800b90f0  movups  xmm0, xmmword ptr [r14]
0x1800b90f4  mov     ecx, [rbx]
0x1800b90f6  movdqu  xmmword ptr [rbp+0], xmm0
0x1800b90fb  mov     eax, [r14]
0x1800b90fe  sub     ecx, eax
0x1800b9100  add     [rdi+100h], eax
0x1800b9106  mov     edx, [rdi+100h]
0x1800b910c  cmp     ecx, edx
0x1800b910e  cmovge  ecx, edx
0x1800b9111  mov     [rbx], ecx
0x1800b9113  jmp     short loc_1800B911A
0x1800b9115  test    rsi, rsi
0x1800b9118  jz      short loc_1800B9122
0x1800b911a  mov     eax, [rsi]
0x1800b911c  mov     [rdi+118h], eax
0x1800b9122  mov     rbx, [rsp+38h+arg_8]
0x1800b9127  xor     eax, eax
0x1800b9129  mov     rbp, [rsp+38h+arg_10]
0x1800b912e  add     rsp, 20h
0x1800b9132  pop     r14
0x1800b9134  pop     rdi
0x1800b9135  pop     rsi
0x1800b9136  retn
```
