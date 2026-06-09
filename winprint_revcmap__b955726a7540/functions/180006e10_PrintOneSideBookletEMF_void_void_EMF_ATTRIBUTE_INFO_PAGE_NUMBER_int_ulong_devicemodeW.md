# PrintOneSideBookletEMF(void *,void *,_EMF_ATTRIBUTE_INFO *,_PAGE_NUMBER *,int,ulong,_devicemodeW *)

- ea: `0x180006e10`
- end: `0x1800070cc`
- name: `?PrintOneSideBookletEMF@@YAHPEAX0PEAU_EMF_ATTRIBUTE_INFO@@PEAU_PAGE_NUMBER@@HKPEAU_devicemodeW@@@Z`
- size: `700`
- prototype: `int(void *, void *, struct _EMF_ATTRIBUTE_INFO *, struct _PAGE_NUMBER *, int, unsigned int, struct _devicemodeW *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, installer_update`

## callees

- `0x180001d60`
- `0x180003200`
- `0x180003cf0`
- `0x1800044a0`
- `0x180006e10`

## import_xrefs

- `GDI32!GdiGetDevmodeForPage` at `0x180006fd4`
- `GDI32!GdiGetDevmodeForPage` at `0x180006fd4`
- `GDI32!GdiGetPageHandle` at `0x180006f7b`
- `GDI32!GdiGetPageHandle` at `0x180006f7b`
- `GDI32!GdiStartPageEMF` at `0x180006fa0`
- `GDI32!GdiStartPageEMF` at `0x180006fa0`
- `GDI32!GdiEndPageEMF` at `0x180007086`
- `GDI32!GdiEndPageEMF` at `0x180007086`

## pseudocode

```c
__int64 __fastcall PrintOneSideBookletEMF(
        void *a1,
        HDC a2,
        struct _EMF_ATTRIBUTE_INFO *a3,
        struct _PAGE_NUMBER *a4,
        int a5,
        DWORD dwOptimization,
        struct _devicemodeW *a7)
{
  struct _PAGE_NUMBER *v7; // r14
  __int64 result; // rax
  unsigned int v12; // edi
  unsigned int v13; // ebx
  DWORD v14; // edx
  unsigned int v15; // esi
  struct _PAGE_NUMBER *v16; // rcx
  bool v17; // cf
  int v18; // ebp
  DWORD v19; // r9d
  struct _devicemodeW *v20; // r15
  union _devicemodeW::$5A39A2C3BB0B1D2D5888DFEE2BA0B23C *p_dmOrientation; // rax
  struct _PAGE_NUMBER *v22; // r12
  unsigned int i; // r15d
  DWORD v24; // esi
  __int16 v25; // di
  __int64 v26; // rcx
  __int16 v27; // di
  DWORD v28; // [rsp+50h] [rbp-78h]
  unsigned int v29; // [rsp+54h] [rbp-74h]
  DWORD pdwPageType; // [rsp+58h] [rbp-70h] BYREF
  int v31; // [rsp+5Ch] [rbp-6Ch]
  unsigned int v32; // [rsp+60h] [rbp-68h]
  PDEVMODEW pCurrDM; // [rsp+68h] [rbp-60h] BYREF
  void *PageHandle; // [rsp+70h] [rbp-58h]
  int v37; // [rsp+E0h] [rbp+18h] BYREF
  unsigned int v38; // [rsp+E8h] [rbp+20h]

  v7 = a4;
  pdwPageType = 0;
  pCurrDM = 0;
  v37 = 0;
  if ( !a4 )
    return 1;
  v12 = *((_DWORD *)a3 + 9);
  v13 = 1;
  v14 = *((_DWORD *)a3 + 7);
  v15 = v12;
  v29 = v12;
  if ( v12 <= 1 )
    v15 = *((_DWORD *)a3 + 8);
  v16 = a4;
  v17 = a5 != 0;
  a5 = -a5;
  v28 = v14;
  v32 = v15;
  v18 = v17 + 1;
  while ( 1 )
  {
    result = (__int64)v16;
    do
    {
      v19 = *(_DWORD *)(result + 16);
      if ( v19 && v19 <= v14 )
        break;
      result = *(_QWORD *)(result + 8);
    }
    while ( result );
    if ( result )
      break;
    v16 = *(struct _PAGE_NUMBER **)v16;
    if ( !v16 )
      return result;
  }
  v20 = a7;
  v31 = *((_DWORD *)a3 + 13);
  v38 = 0;
  if ( (unsigned int)ResetDCForNewDevmode(a1, a2, a3, v19, 0, dwOptimization, (PDEVMODEW)&v37, a7, &pCurrDM) )
  {
    PageHandle = 0;
    if ( pCurrDM )
      p_dmOrientation = (union _devicemodeW::$5A39A2C3BB0B1D2D5888DFEE2BA0B23C *)&pCurrDM->dmOrientation;
    else
      p_dmOrientation = (union _devicemodeW::$5A39A2C3BB0B1D2D5888DFEE2BA0B23C *)&v20->dmOrientation;
    LOWORD(v37) = p_dmOrientation->dmOrientation;
LABEL_18:
    if ( v18 && v7 )
    {
      v22 = v7;
      for ( i = 1; ; ++i )
      {
        if ( !v22 || i > v15 )
        {
          v7 = *(struct _PAGE_NUMBER **)v7;
          --v18;
          goto LABEL_18;
        }
        v24 = *((_DWORD *)v22 + 4);
        if ( !v24 )
          v24 = -1;
        if ( v24 <= v28 )
        {
          PageHandle = GdiGetPageHandle(a1, v24, &pdwPageType);
          if ( !PageHandle )
            break;
        }
        if ( (i == 1 || v12 > 1) && !GdiStartPageEMF(a1) )
          break;
        if ( v24 <= v28 )
        {
          v25 = 0;
          pCurrDM = 0;
          if ( GdiGetDevmodeForPage(a1, v24, &pCurrDM, 0)
            && pCurrDM
            && (unsigned int)BIsDevmodeOfLeastAcceptableSize(pCurrDM)
            && *(_WORD *)(v26 + 76) != (_WORD)v37 )
          {
            v25 = 0x8000;
            BUpdateAttributes(a2, a3);
          }
          if ( v18 == 1 && v31 == 1 )
          {
            v27 = v25 | 2;
            if ( v29 > 1 && a7->dmOrientation == 2 )
              v27 |= 0x8000u;
          }
          else
          {
            v27 = v25 | 1;
          }
          if ( !(unsigned int)PlayEMFPage(a1, a2, PageHandle, a3, i, v27) )
            return v38;
          v12 = v29;
        }
        v15 = v32;
        if ( (i == v32 || v12 > 1) && !GdiEndPageEMF(a1, dwOptimization) )
          return v38;
        v22 = (struct _PAGE_NUMBER *)*((_QWORD *)v22 + 1);
      }
      return v38;
    }
  }
  else
  {
    return 0;
  }
  return v13;
}

```

## disassembly

```asm
0x180006e10  mov     rax, rsp
0x180006e13  mov     [rax+10h], rdx
0x180006e17  mov     [rax+8], rcx
0x180006e1b  push    rbx
0x180006e1c  push    rbp
0x180006e1d  push    rsi
0x180006e1e  push    rdi
0x180006e1f  push    r12
0x180006e21  push    r13
0x180006e23  push    r14
0x180006e25  push    r15
0x180006e27  sub     rsp, 88h
0x180006e2e  xor     r12d, r12d
0x180006e31  mov     r14, r9
0x180006e34  mov     [rax-70h], r12d
0x180006e38  mov     r13, r8
0x180006e3b  mov     [rax-60h], r12
0x180006e3f  mov     r11, rdx
0x180006e42  mov     [rax+18h], r12d
0x180006e46  mov     r10, rcx
0x180006e49  test    r9, r9
0x180006e4c  jnz     short loc_180006E57
0x180006e4e  lea     eax, [r9+1]
0x180006e52  jmp     loc_1800070B8
0x180006e57  mov     edi, [r8+24h]
0x180006e5b  mov     ebx, 1
0x180006e60  mov     edx, [r8+1Ch]
0x180006e64  cmp     edi, ebx
0x180006e66  mov     esi, edi
0x180006e68  mov     [rsp+0C8h+var_74], edi
0x180006e6c  cmovbe  esi, [r8+20h]
0x180006e71  mov     rcx, r9
0x180006e74  neg     dword ptr [rsp+0F0h]
0x180006e7b  mov     [rsp+0C8h+var_78], edx
0x180006e7f  sbb     ebp, ebp
0x180006e81  mov     [rsp+0C8h+var_68], esi
0x180006e85  neg     ebp
0x180006e87  add     ebp, ebx
0x180006e89  mov     rax, rcx
0x180006e8c  mov     r9d, [rax+10h]; dwPageNumber
0x180006e90  test    r9d, r9d
0x180006e93  jz      short loc_180006E9A
0x180006e95  cmp     r9d, edx
0x180006e98  jbe     short loc_180006EA3
0x180006e9a  mov     rax, [rax+8]
0x180006e9e  test    rax, rax
0x180006ea1  jnz     short loc_180006E8C
0x180006ea3  test    rax, rax
0x180006ea6  jnz     short loc_180006EB5
0x180006ea8  mov     rcx, [rcx]
0x180006eab  test    rcx, rcx
0x180006eae  jnz     short loc_180006E89
0x180006eb0  jmp     loc_1800070B8
0x180006eb5  mov     eax, [r8+34h]
0x180006eb9  lea     rcx, [rsp+0C8h+pCurrDM]
0x180006ebe  mov     r15, [rsp+100h]
0x180006ec6  mov     rdx, r11; hdc
0x180006ec9  mov     [rsp+0C8h+var_88], rcx; struct _devicemodeW **
0x180006ece  mov     rcx, r10; SpoolFileHandle
0x180006ed1  mov     [rsp+0C8h+var_6C], eax
0x180006ed5  lea     rax, [rsp+0C8h+arg_10]
0x180006edd  mov     [rsp+0C8h+var_90], r15; struct _devicemodeW *
0x180006ee2  mov     [rsp+0C8h+var_98], rax; pCurrDM
0x180006ee7  mov     eax, [rsp+0F8h]
0x180006eee  mov     [rsp+0C8h+dwOptimization], eax; dwOptimization
0x180006ef2  mov     [rsp+0C8h+var_A8], r12d; int
0x180006ef7  mov     [rsp+0C8h+arg_18], r12d
0x180006eff  call    ?ResetDCForNewDevmode@@YAHPEAX0PEAU_EMF_ATTRIBUTE_INFO@@KHKPEAHPEAU_devicemodeW@@PEAPEAU2@@Z; ResetDCForNewDevmode(void *,void *,_EMF_ATTRIBUTE_INFO *,ulong,int,ulong,int *,_devicemodeW *,_devicemodeW * *)
0x180006f04  test    eax, eax
0x180006f06  jz      loc_1800070B3
0x180006f0c  mov     rax, [rsp+0C8h+pCurrDM]
0x180006f11  mov     [rsp+0C8h+var_58], r12
0x180006f16  test    rax, rax
0x180006f19  jz      short loc_180006F21
0x180006f1b  add     rax, 4Ch ; 'L'
0x180006f1f  jmp     short loc_180006F25
0x180006f21  lea     rax, [r15+4Ch]
0x180006f25  movzx   eax, word ptr [rax]
0x180006f28  mov     word ptr [rsp+0C8h+arg_10], ax
0x180006f30  or      eax, 0FFFFFFFFh
0x180006f33  test    ebp, ebp
0x180006f35  jz      loc_1800070B6
0x180006f3b  test    r14, r14
0x180006f3e  jz      loc_1800070B6
0x180006f44  mov     r12, r14
0x180006f47  mov     r15d, ebx
0x180006f4a  test    r12, r12
0x180006f4d  jz      loc_1800070A0
0x180006f53  cmp     r15d, esi
0x180006f56  ja      loc_1800070A0
0x180006f5c  mov     esi, [r12+10h]
0x180006f61  test    esi, esi
0x180006f63  cmovz   esi, eax
0x180006f66  cmp     esi, [rsp+0C8h+var_78]
0x180006f6a  ja      short loc_180006F8F
0x180006f6c  mov     rcx, [rsp+0C8h+SpoolFileHandle]; SpoolFileHandle
0x180006f74  lea     r8, [rsp+0C8h+pdwPageType]; pdwPageType
0x180006f79  mov     edx, esi; Page
0x180006f7b  call    cs:__imp_GdiGetPageHandle
0x180006f81  mov     [rsp+0C8h+var_58], rax
0x180006f86  test    rax, rax
0x180006f89  jz      loc_1800070AA
0x180006f8f  cmp     r15d, ebx
0x180006f92  jz      short loc_180006F98
0x180006f94  cmp     edi, ebx
0x180006f96  jbe     short loc_180006FAE
0x180006f98  mov     rcx, [rsp+0C8h+SpoolFileHandle]; SpoolFileHandle
0x180006fa0  call    cs:__imp_GdiStartPageEMF
0x180006fa6  test    eax, eax
0x180006fa8  jz      loc_1800070AA
0x180006fae  cmp     esi, [rsp+0C8h+var_78]
0x180006fb2  ja      loc_18000706A
0x180006fb8  mov     edx, esi; dwPageNumber
0x180006fba  lea     r8, [rsp+0C8h+pCurrDM]; pCurrDM
0x180006fbf  mov     rsi, [rsp+0C8h+SpoolFileHandle]
0x180006fc7  xor     edi, edi
0x180006fc9  mov     rcx, rsi; SpoolFileHandle
0x180006fcc  mov     [rsp+0C8h+pCurrDM], rdi
0x180006fd1  xor     r9d, r9d; pLastDM
0x180006fd4  call    cs:__imp_GdiGetDevmodeForPage
0x180006fda  test    eax, eax
0x180006fdc  jz      short loc_180007014
0x180006fde  mov     rcx, [rsp+0C8h+pCurrDM]; struct _devicemodeW *
0x180006fe3  test    rcx, rcx
0x180006fe6  jz      short loc_180007014
0x180006fe8  call    ?BIsDevmodeOfLeastAcceptableSize@@YAHPEAU_devicemodeW@@@Z; BIsDevmodeOfLeastAcceptableSize(_devicemodeW *)
0x180006fed  test    eax, eax
0x180006fef  jz      short loc_180007014
0x180006ff1  movzx   eax, word ptr [rsp+0C8h+arg_10]
0x180006ff9  cmp     [rcx+4Ch], ax
0x180006ffd  jz      short loc_180007014
0x180006fff  mov     rcx, [rsp+0C8h+hdc]; hdc
0x180007007  mov     rdx, r13; struct _EMF_ATTRIBUTE_INFO *
0x18000700a  mov     edi, 8000h
0x18000700f  call    ?BUpdateAttributes@@YAHPEAXPEAU_EMF_ATTRIBUTE_INFO@@@Z; BUpdateAttributes(void *,_EMF_ATTRIBUTE_INFO *)
0x180007014  cmp     ebp, ebx
0x180007016  jnz     short loc_18000703F
0x180007018  cmp     [rsp+0C8h+var_6C], ebx
0x18000701c  jnz     short loc_18000703F
0x18000701e  mov     ecx, 2
0x180007023  or      edi, ecx
0x180007025  cmp     [rsp+0C8h+var_74], ebx
0x180007029  jbe     short loc_180007041
0x18000702b  mov     rax, [rsp+100h]
0x180007033  cmp     [rax+4Ch], cx
0x180007037  jnz     short loc_180007041
0x180007039  bts     edi, 0Fh
0x18000703d  jmp     short loc_180007041
0x18000703f  or      edi, ebx
0x180007041  mov     r8, [rsp+0C8h+var_58]; void *
0x180007046  mov     r9, r13; struct _EMF_ATTRIBUTE_INFO *
0x180007049  mov     rdx, [rsp+0C8h+hdc]; hdc
0x180007051  mov     rcx, rsi; SpoolFileHandle
0x180007054  mov     [rsp+0C8h+dwOptimization], edi; unsigned int
0x180007058  mov     [rsp+0C8h+var_A8], r15d; unsigned int
0x18000705d  call    ?PlayEMFPage@@YAHPEAX00QEAU_EMF_ATTRIBUTE_INFO@@KK@Z; PlayEMFPage(void *,void *,void *,_EMF_ATTRIBUTE_INFO * const,ulong,ulong)
0x180007062  test    eax, eax
0x180007064  jz      short loc_1800070AA
0x180007066  mov     edi, [rsp+0C8h+var_74]
0x18000706a  mov     esi, [rsp+0C8h+var_68]
0x18000706e  cmp     r15d, esi
0x180007071  jz      short loc_180007077
0x180007073  cmp     edi, ebx
0x180007075  jbe     short loc_180007090
0x180007077  mov     edx, [rsp+0F8h]; dwOptimization
0x18000707e  mov     rcx, [rsp+0C8h+SpoolFileHandle]; SpoolFileHandle
0x180007086  call    cs:__imp_GdiEndPageEMF
0x18000708c  test    eax, eax
0x18000708e  jz      short loc_1800070AA
0x180007090  mov     r12, [r12+8]
0x180007095  add     r15d, ebx
0x180007098  or      eax, 0FFFFFFFFh
0x18000709b  jmp     loc_180006F4A
0x1800070a0  mov     r14, [r14]
0x1800070a3  add     ebp, eax
0x1800070a5  jmp     loc_180006F33
0x1800070aa  mov     ebx, [rsp+0C8h+arg_18]
0x1800070b1  jmp     short loc_1800070B6
0x1800070b3  mov     ebx, r12d
0x1800070b6  mov     eax, ebx
0x1800070b8  add     rsp, 88h
0x1800070bf  pop     r15
0x1800070c1  pop     r14
0x1800070c3  pop     r13
0x1800070c5  pop     r12
0x1800070c7  pop     rdi
0x1800070c8  pop     rsi
0x1800070c9  pop     rbp
0x1800070ca  pop     rbx
0x1800070cb  retn
```
