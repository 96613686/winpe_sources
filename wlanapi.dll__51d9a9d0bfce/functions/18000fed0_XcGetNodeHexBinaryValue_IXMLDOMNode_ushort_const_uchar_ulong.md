# XcGetNodeHexBinaryValue(IXMLDOMNode *,ushort const *,uchar * *,ulong *)

- ea: `0x18000fed0`
- end: `0x180010080`
- name: `?XcGetNodeHexBinaryValue@@YAKPEAUIXMLDOMNode@@PEBGPEAPEAEPEAK@Z`
- size: `432`
- prototype: `unsigned int __fastcall(struct IXMLDOMNode *, const unsigned __int16 *, unsigned __int8 **, unsigned int *)`
- caller_count: `8`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000d660`
- `0x18000df08`
- `0x180046614`
- `0x180046a18`
- `0x180047cec`
- `0x18004844c`
- `0x180048e00`
- `0x1800490d4`

## callees

- `0x18000dea8`
- `0x18000fc48`
- `0x18000fed0`
- `0x180019370`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010067`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010067`
- `OLEAUT32!__imp_VariantInit` at `0x18000feee`
- `OLEAUT32!__imp_VariantInit` at `0x18000feee`
- `OLEAUT32!__imp_VariantClear` at `0x18001002c`
- `OLEAUT32!__imp_VariantClear` at `0x18001002c`

## pseudocode

```c
__int64 __fastcall XcGetNodeHexBinaryValue(
        struct IXMLDOMNode *a1,
        const unsigned __int16 *a2,
        unsigned __int8 **a3,
        unsigned int *a4)
{
  DWORD NodeTypedValue; // eax
  DWORD LastError; // edi
  unsigned __int64 v10; // rbx
  unsigned __int8 *v11; // r10
  __int64 v12; // r9
  unsigned int v13; // r8d
  __int64 v14; // rbp
  __int64 v15; // r11
  unsigned __int64 v16; // rdx
  char v17; // al
  char v18; // cl
  VARIANTARG pvarg; // [rsp+20h] [rbp-38h] BYREF

  VariantInit(&pvarg);
  NodeTypedValue = XcGetNodeTypedValue(a1, a2, &pvarg);
  LastError = NodeTypedValue;
  if ( NodeTypedValue == 1168 )
    goto LABEL_28;
  if ( NodeTypedValue )
    goto LABEL_29;
  v10 = -1;
  do
    ++v10;
  while ( *(_WORD *)(pvarg.llVal + 2 * v10) );
  if ( v10 > 0xFFFFFFFF )
  {
LABEL_28:
    LastError = 1206;
    goto LABEL_29;
  }
  v11 = (unsigned __int8 *)Xc_Process_user_allocate((v10 + 1) >> 1);
  if ( v11 )
  {
    v12 = 0;
    v13 = 0;
    v14 = 0x100002600LL;
    v15 = 0x7E0000007E03FFLL;
    while ( (unsigned int)v12 < v10 )
    {
      v16 = *(unsigned __int16 *)(pvarg.llVal + 2 * v12);
      if ( (unsigned int)v16 > 0x20 || !_bittest64(&v14, v16) )
      {
        if ( (unsigned __int16)(v16 - 48) > 0x36u || !_bittest64(&v15, (unsigned int)(v16 - 48)) )
          goto LABEL_35;
        if ( (v13 & 1) != 0 )
        {
          if ( (unsigned int)v16 > 0x39 )
          {
            v18 = -87;
            if ( (unsigned int)v16 <= 0x46 )
              v18 = -55;
          }
          else
          {
            v18 = -48;
          }
          v11[(unsigned __int64)v13 >> 1] |= v18 + (_BYTE)v16;
        }
        else
        {
          if ( (unsigned int)v16 > 0x39 )
          {
            v17 = -87;
            if ( (unsigned int)v16 <= 0x46 )
              v17 = -55;
          }
          else
          {
            v17 = -48;
          }
          v11[(unsigned __int64)v13 >> 1] = 16 * (v17 + v16);
        }
        ++v13;
      }
      v12 = (unsigned int)(v12 + 1);
    }
    if ( v13 && (v13 & 1) == 0 )
    {
      *a3 = v11;
      *a4 = v13 >> 1;
      goto LABEL_29;
    }
LABEL_35:
    LastError = 1206;
    Xc_Process_user_free(v11);
  }
  else
  {
    LastError = GetLastError();
  }
LABEL_29:
  VariantClear(&pvarg);
  return LastError;
}

```

## disassembly

```asm
0x18000fed0  mov     [rsp+arg_18], rbx
0x18000fed5  push    rsi
0x18000fed6  push    rdi
0x18000fed7  push    r14
0x18000fed9  sub     rsp, 40h
0x18000fedd  mov     rdi, rcx
0x18000fee0  mov     rsi, r9
0x18000fee3  lea     rcx, [rsp+58h+pvarg]; pvarg
0x18000fee8  mov     r14, r8
0x18000feeb  mov     rbx, rdx
0x18000feee  call    cs:__imp_VariantInit
0x18000fef4  lea     r8, [rsp+58h+pvarg]; struct tagVARIANT *
0x18000fef9  mov     rdx, rbx; unsigned __int16 *
0x18000fefc  mov     rcx, rdi; struct IXMLDOMNode *
0x18000feff  call    ?XcGetNodeTypedValue@@YAKPEAUIXMLDOMNode@@PEBGPEAUtagVARIANT@@@Z; XcGetNodeTypedValue(IXMLDOMNode *,ushort const *,tagVARIANT *)
0x18000ff04  mov     edi, eax
0x18000ff06  cmp     eax, 490h
0x18000ff0b  jz      loc_180010022
0x18000ff11  test    eax, eax
0x18000ff13  jnz     loc_180010027
0x18000ff19  mov     rax, qword ptr [rsp+58h+pvarg+8]
0x18000ff1e  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000ff25  inc     rbx
0x18000ff28  cmp     word ptr [rax+rbx*2], 0
0x18000ff2d  jnz     short loc_18000FF25
0x18000ff2f  mov     eax, 0FFFFFFFFh
0x18000ff34  cmp     rbx, rax
0x18000ff37  ja      loc_180010022
0x18000ff3d  lea     rcx, [rbx+1]
0x18000ff41  shr     rcx, 1; dwBytes
0x18000ff44  call    ?Xc_Process_user_allocate@@YAPEAX_K@Z; Xc_Process_user_allocate(unsigned __int64)
0x18000ff49  mov     r10, rax
0x18000ff4c  test    rax, rax
0x18000ff4f  jz      loc_180010067
0x18000ff55  mov     [rsp+58h+arg_0], rbp
0x18000ff5a  xor     r9d, r9d
0x18000ff5d  mov     [rsp+58h+arg_8], r12
0x18000ff62  xor     r8d, r8d
0x18000ff65  mov     [rsp+58h+arg_10], r15
0x18000ff6a  mov     rbp, 100002600h
0x18000ff74  mov     r15d, 0C9h
0x18000ff7a  mov     r11, 7E0000007E03FFh
0x18000ff84  mov     r12d, 0FFFFFFC9h
0x18000ff8a  nop     word ptr [rax+rax+00h]
0x18000ff90  mov     edx, r9d
0x18000ff93  cmp     rdx, rbx
0x18000ff96  jnb     loc_180010042
0x18000ff9c  mov     rax, qword ptr [rsp+58h+pvarg+8]
0x18000ffa1  movzx   edx, word ptr [rax+r9*2]
0x18000ffa6  cmp     edx, 20h ; ' '
0x18000ffa9  ja      short loc_18000FFB1
0x18000ffab  bt      rbp, rdx
0x18000ffaf  jb      short loc_18000FFEC
0x18000ffb1  lea     eax, [rdx-30h]
0x18000ffb4  cmp     ax, 36h ; '6'
0x18000ffb8  ja      loc_180010071
0x18000ffbe  bt      r11, rax
0x18000ffc2  jnb     loc_180010071
0x18000ffc8  test    r8b, 1
0x18000ffcc  jnz     short loc_18000FFF1
0x18000ffce  mov     ecx, edx
0x18000ffd0  cmp     edx, 39h ; '9'
0x18000ffd3  ja      short loc_180010014
0x18000ffd5  mov     eax, 0FFFFFFD0h
0x18000ffda  add     cl, al
0x18000ffdc  mov     eax, r8d
0x18000ffdf  shl     cl, 4
0x18000ffe2  shr     rax, 1
0x18000ffe5  mov     [rax+r10], cl
0x18000ffe9  inc     r8d
0x18000ffec  inc     r9d
0x18000ffef  jmp     short loc_18000FF90
0x18000fff1  cmp     edx, 39h ; '9'
0x18000fff4  ja      short loc_180010006
0x18000fff6  mov     cl, 0D0h
0x18000fff8  mov     eax, r8d
0x18000fffb  add     dl, cl
0x18000fffd  shr     rax, 1
0x180010000  or      [rax+r10], dl
0x180010004  jmp     short loc_18000FFE9
0x180010006  cmp     edx, 46h ; 'F'
0x180010009  mov     ecx, 0A9h
0x18001000e  cmovbe  ecx, r15d
0x180010012  jmp     short loc_18000FFF8
0x180010014  cmp     edx, 46h ; 'F'
0x180010017  mov     eax, 0FFFFFFA9h
0x18001001c  cmovbe  eax, r12d
0x180010020  jmp     short loc_18000FFDA
0x180010022  mov     edi, 4B6h
0x180010027  lea     rcx, [rsp+58h+pvarg]; pvarg
0x18001002c  call    cs:__imp_VariantClear
0x180010032  mov     rbx, [rsp+58h+arg_18]
0x180010037  mov     eax, edi
0x180010039  add     rsp, 40h
0x18001003d  pop     r14
0x18001003f  pop     rdi
0x180010040  pop     rsi
0x180010041  retn
0x180010042  test    r8d, r8d
0x180010045  jz      short loc_180010071
0x180010047  test    r8b, 1
0x18001004b  jnz     short loc_180010071
0x18001004d  shr     r8d, 1
0x180010050  mov     [r14], r10
0x180010053  mov     [rsi], r8d
0x180010056  mov     r12, [rsp+58h+arg_8]
0x18001005b  mov     rbp, [rsp+58h+arg_0]
0x180010060  mov     r15, [rsp+58h+arg_10]
0x180010065  jmp     short loc_180010027
0x180010067  call    cs:__imp_GetLastError
0x18001006d  mov     edi, eax
0x18001006f  jmp     short loc_180010027
0x180010071  mov     edi, 4B6h
0x180010076  mov     rcx, r10; lpMem
0x180010079  call    ?Xc_Process_user_free@@YAXPEAX@Z; Xc_Process_user_free(void *)
0x18001007e  jmp     short loc_180010056
```
