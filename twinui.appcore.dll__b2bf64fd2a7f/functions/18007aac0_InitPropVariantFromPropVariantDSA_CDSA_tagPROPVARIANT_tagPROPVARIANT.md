# InitPropVariantFromPropVariantDSA(CDSA<tagPROPVARIANT> *,tagPROPVARIANT *)

- ea: `0x18007aac0`
- end: `0x18007ad0a`
- name: `?InitPropVariantFromPropVariantDSA@@YAJPEAV?$CDSA@UtagPROPVARIANT@@@@PEAUtagPROPVARIANT@@@Z`
- size: `586`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18007a410`

## callees

- `0x18007805c`
- `0x18007aac0`
- `0x180080ec0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007ab6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007ab6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007ac39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007ac39`
- `PROPSYS!PropVariantToStringAlloc` at `0x18007ac9a`
- `PROPSYS!PropVariantToStringAlloc` at `0x18007ac9a`

## pseudocode

```c
__int64 __fastcall InitPropVariantFromPropVariantDSA(HDSA *a1, __int64 a2)
{
  int v2; // r14d
  HRESULT v5; // edi
  struct _DSA *v6; // rcx
  int v7; // ebx
  unsigned __int16 v8; // r15
  int v9; // eax
  int v10; // r9d
  int v11; // eax
  void *v12; // rsi
  int v13; // ebx
  const PROPVARIANT *ItemPtr; // rax
  _OWORD *v15; // rcx
  __int128 v17; // [rsp+20h] [rbp-20h]
  int v18; // [rsp+80h] [rbp+40h]
  PWSTR ppszOut; // [rsp+90h] [rbp+50h] BYREF

  v2 = 0;
  v5 = -2147024809;
  *(_OWORD *)a2 = 0;
  *(_QWORD *)(a2 + 16) = 0;
  if ( a1 )
  {
    v6 = *a1;
    v5 = 0;
    if ( v6 )
    {
      v7 = *(_DWORD *)v6;
      v18 = *(_DWORD *)v6;
      if ( *(_DWORD *)v6 )
      {
        v5 = -2147286953;
        v8 = *(_WORD *)g_pfn_DSA_GetItemPtr(v6, 0);
        if ( v8 == 8 )
        {
          v8 = 31;
        }
        else if ( (v8 & 0x1000) != 0 )
        {
          return (unsigned int)v5;
        }
        v9 = CRGTypeSizes::operator[](8, v8);
        v11 = v10 & v9;
        if ( v11 )
        {
          v5 = -2147024882;
          v17 = 0;
          v12 = CoTaskMemAlloc((unsigned int)(v7 * v11));
          if ( v12 )
          {
            v13 = 0;
            DWORD2(v17) = 0;
            v5 = 0;
            while ( 1 )
            {
              if ( v2 >= v18 )
              {
                LOWORD(v17) = v8 | 0x1000;
                *(_OWORD *)a2 = v17;
                *(_QWORD *)(a2 + 16) = v12;
                return (unsigned int)v5;
              }
              ItemPtr = (const PROPVARIANT *)g_pfn_DSA_GetItemPtr(*a1, v2);
              if ( *(_WORD *)ItemPtr != v8 )
              {
                if ( *(_WORD *)ItemPtr == 8 )
                {
                  if ( v8 != 31 )
                    goto LABEL_26;
                }
                else if ( (*(_WORD *)ItemPtr || v8 != 1) && (*(_WORD *)ItemPtr != 1 || v8) )
                {
LABEL_26:
                  v5 = -2147286953;
LABEL_27:
                  CoTaskMemFree(v12);
                  return (unsigned int)v5;
                }
              }
              if ( v8 > 0x13u )
              {
                switch ( v8 )
                {
                  case 0x14u:
                  case 0x15u:
                    goto LABEL_39;
                  case 0x1Fu:
                    ppszOut = 0;
                    v5 = PropVariantToStringAlloc(ItemPtr, &ppszOut);
                    if ( v5 >= 0 )
                    {
                      *((_QWORD *)v12 + v2) = ppszOut;
                      DWORD2(v17) = ++v13;
                    }
                    goto LABEL_41;
                  case 0x40u:
LABEL_39:
                    *((PROPVARIANT *)v12 + v2) = ItemPtr[1];
                    goto LABEL_40;
                  case 0x48u:
                    v15 = (_OWORD *)*((_QWORD *)ItemPtr + 1);
                    if ( v15 )
                    {
                      v5 = 0;
                      *((_OWORD *)v12 + v2) = *v15;
                      goto LABEL_40;
                    }
                    break;
                }
              }
              else
              {
                switch ( v8 )
                {
                  case 0x13u:
                    goto LABEL_28;
                  case 2u:
                    goto LABEL_21;
                  case 3u:
LABEL_28:
                    *((_DWORD *)v12 + v2) = *((_DWORD *)ItemPtr + 2);
                    goto LABEL_40;
                  case 5u:
                    goto LABEL_39;
                  case 0xBu:
                  case 0x12u:
LABEL_21:
                    *((_WORD *)v12 + v2) = *((_WORD *)ItemPtr + 4);
LABEL_40:
                    DWORD2(v17) = ++v13;
                    goto LABEL_41;
                }
              }
              v5 = -2147286953;
LABEL_41:
              ++v2;
              if ( v5 < 0 )
                goto LABEL_27;
            }
          }
        }
      }
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18007aac0  mov     [rsp-38h+arg_8], rbx
0x18007aac5  push    rbp
0x18007aac6  push    rsi
0x18007aac7  push    rdi
0x18007aac8  push    r12
0x18007aaca  push    r13
0x18007aacc  push    r14
0x18007aace  push    r15
0x18007aad0  mov     rbp, rsp
0x18007aad3  sub     rsp, 40h
0x18007aad7  xor     eax, eax
0x18007aad9  xorps   xmm0, xmm0
0x18007aadc  xor     r14d, r14d
0x18007aadf  mov     r13, rdx
0x18007aae2  mov     r12, rcx
0x18007aae5  mov     edi, 80070057h
0x18007aaea  movups  xmmword ptr [rdx], xmm0
0x18007aaed  mov     [rdx+10h], rax
0x18007aaf1  test    rcx, rcx
0x18007aaf4  jz      loc_18007ACF0
0x18007aafa  mov     rcx, [rcx]; hdsa
0x18007aafd  mov     edi, r14d
0x18007ab00  test    rcx, rcx
0x18007ab03  jz      loc_18007ACF0
0x18007ab09  mov     ebx, [rcx]
0x18007ab0b  mov     [rbp+arg_0], ebx
0x18007ab0e  test    ebx, ebx
0x18007ab10  jz      loc_18007ACF0
0x18007ab16  xor     edx, edx; i
0x18007ab18  mov     edi, 80030057h
0x18007ab1d  call    cs:g_pfn_DSA_GetItemPtr
0x18007ab23  lea     ecx, [r14+8]
0x18007ab27  lea     r9d, [r14+1Fh]
0x18007ab2b  movzx   r15d, word ptr [rax]
0x18007ab2f  cmp     r15w, cx
0x18007ab33  jnz     short loc_18007AB3B
0x18007ab35  movzx   r15d, r9w
0x18007ab39  jmp     short loc_18007AB47
0x18007ab3b  bt      r15w, 0Ch
0x18007ab41  jb      loc_18007ACF0
0x18007ab47  movzx   edx, r15w
0x18007ab4b  call    ??ACRGTypeSizes@@QEAAGH@Z; CRGTypeSizes::operator[](int)
0x18007ab50  and     eax, r9d
0x18007ab53  jz      loc_18007ACF0
0x18007ab59  imul    eax, ebx
0x18007ab5c  xorps   xmm0, xmm0
0x18007ab5f  mov     edi, 8007000Eh
0x18007ab64  movups  [rbp+var_20], xmm0
0x18007ab68  mov     ecx, eax; cb
0x18007ab6a  call    cs:__imp_CoTaskMemAlloc
0x18007ab70  mov     rsi, rax
0x18007ab73  test    rax, rax
0x18007ab76  jz      loc_18007ACF0
0x18007ab7c  movzx   eax, r15w
0x18007ab80  mov     ebx, r14d
0x18007ab83  or      ax, 1000h
0x18007ab87  mov     dword ptr [rbp+var_20+8], ebx
0x18007ab8a  mov     word ptr [rbp+var_20], ax
0x18007ab8e  mov     edi, r14d
0x18007ab91  cmp     r14d, [rbp+arg_0]
0x18007ab95  jge     loc_18007ACE3
0x18007ab9b  mov     rcx, [r12]; hdsa
0x18007ab9f  mov     edx, r14d; i
0x18007aba2  call    cs:g_pfn_DSA_GetItemPtr
0x18007aba8  mov     r8, rax
0x18007abab  mov     edx, 8
0x18007abb0  cmp     [rax], r15w
0x18007abb4  jz      short loc_18007ABC4
0x18007abb6  cmp     [rax], dx
0x18007abb9  lea     eax, [rdx+17h]
0x18007abbc  jnz     short loc_18007AC06
0x18007abbe  cmp     r15w, ax
0x18007abc2  jnz     short loc_18007AC31
0x18007abc4  xor     r9d, r9d
0x18007abc7  lea     r10d, [r9+1]
0x18007abcb  cmp     r15w, 13h
0x18007abd0  ja      short loc_18007AC50
0x18007abd2  jz      short loc_18007AC44
0x18007abd4  movzx   ecx, r15w
0x18007abd8  sub     ecx, 2
0x18007abdb  jz      short loc_18007ABF5
0x18007abdd  sub     ecx, 1
0x18007abe0  jz      short loc_18007AC44
0x18007abe2  sub     ecx, 2
0x18007abe5  jz      loc_18007ACBD
0x18007abeb  sub     ecx, 6
0x18007abee  jz      short loc_18007ABF5
0x18007abf0  cmp     ecx, 7
0x18007abf3  jnz     short loc_18007AC6C
0x18007abf5  movzx   eax, word ptr [r8+8]
0x18007abfa  movsxd  rcx, r14d
0x18007abfd  mov     [rsi+rcx*2], ax
0x18007ac01  jmp     loc_18007ACC8
0x18007ac06  cmp     [r8], ax
0x18007ac0a  jnz     short loc_18007AC12
0x18007ac0c  cmp     r15w, dx
0x18007ac10  jz      short loc_18007ABC4
0x18007ac12  xor     r9d, r9d
0x18007ac15  lea     r10d, [r9+1]
0x18007ac19  cmp     [r8], r9w
0x18007ac1d  jnz     short loc_18007AC25
0x18007ac1f  cmp     r15w, r10w
0x18007ac23  jz      short loc_18007ABCB
0x18007ac25  cmp     [r8], r10w
0x18007ac29  jnz     short loc_18007AC31
0x18007ac2b  test    r15w, r15w
0x18007ac2f  jz      short loc_18007ABCB
0x18007ac31  mov     edi, 80030057h
0x18007ac36  mov     rcx, rsi; pv
0x18007ac39  call    cs:__imp_CoTaskMemFree
0x18007ac3f  jmp     loc_18007ACF0
0x18007ac44  mov     eax, [r8+8]
0x18007ac48  movsxd  rcx, r14d
0x18007ac4b  mov     [rsi+rcx*4], eax
0x18007ac4e  jmp     short loc_18007ACC8
0x18007ac50  movzx   ecx, r15w
0x18007ac54  sub     ecx, 14h
0x18007ac57  jz      short loc_18007ACBD
0x18007ac59  sub     ecx, 1
0x18007ac5c  jz      short loc_18007ACBD
0x18007ac5e  sub     ecx, 0Ah
0x18007ac61  jz      short loc_18007AC8F
0x18007ac63  sub     ecx, 21h ; '!'
0x18007ac66  jz      short loc_18007ACBD
0x18007ac68  cmp     ecx, edx
0x18007ac6a  jz      short loc_18007AC73
0x18007ac6c  mov     edi, 80030057h
0x18007ac71  jmp     short loc_18007ACCE
0x18007ac73  mov     rcx, [r8+8]
0x18007ac77  test    rcx, rcx
0x18007ac7a  jz      short loc_18007AC6C
0x18007ac7c  movups  xmm0, xmmword ptr [rcx]
0x18007ac7f  movsxd  rax, r14d
0x18007ac82  mov     edi, r9d
0x18007ac85  add     rax, rax
0x18007ac88  movdqu  xmmword ptr [rsi+rax*8], xmm0
0x18007ac8d  jmp     short loc_18007ACC8
0x18007ac8f  lea     rdx, [rbp+ppszOut]; ppszOut
0x18007ac93  mov     [rbp+ppszOut], r9
0x18007ac97  mov     rcx, r8; propvar
0x18007ac9a  call    cs:__imp_PropVariantToStringAlloc
0x18007aca0  mov     edi, eax
0x18007aca2  test    eax, eax
0x18007aca4  js      short loc_18007ACCE
0x18007aca6  mov     rax, [rbp+ppszOut]
0x18007acaa  movsxd  rcx, r14d
0x18007acad  mov     [rsi+rcx*8], rax
0x18007acb1  mov     eax, 1
0x18007acb6  add     ebx, eax
0x18007acb8  mov     dword ptr [rbp+var_20+8], ebx
0x18007acbb  jmp     short loc_18007ACD3
0x18007acbd  mov     rax, [r8+8]
0x18007acc1  movsxd  rcx, r14d
0x18007acc4  mov     [rsi+rcx*8], rax
0x18007acc8  add     ebx, r10d
0x18007accb  mov     dword ptr [rbp+var_20+8], ebx
0x18007acce  mov     eax, 1
0x18007acd3  add     r14d, eax
0x18007acd6  test    edi, edi
0x18007acd8  jns     loc_18007AB91
0x18007acde  jmp     loc_18007AC36
0x18007ace3  movups  xmm0, [rbp+var_20]
0x18007ace7  movups  xmmword ptr [r13+0], xmm0
0x18007acec  mov     [r13+10h], rsi
0x18007acf0  mov     rbx, [rsp+40h+arg_8]
0x18007acf8  mov     eax, edi
0x18007acfa  add     rsp, 40h
0x18007acfe  pop     r15
0x18007ad00  pop     r14
0x18007ad02  pop     r13
0x18007ad04  pop     r12
0x18007ad06  pop     rdi
0x18007ad07  pop     rsi
0x18007ad08  pop     rbp
0x18007ad09  retn
```
