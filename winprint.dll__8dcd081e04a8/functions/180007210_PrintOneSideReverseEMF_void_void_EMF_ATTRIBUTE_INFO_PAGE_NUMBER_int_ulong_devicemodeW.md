# PrintOneSideReverseEMF(void *,void *,_EMF_ATTRIBUTE_INFO *,_PAGE_NUMBER *,int,ulong,_devicemodeW *)

- ea: `0x180007210`
- end: `0x18000752b`
- name: `?PrintOneSideReverseEMF@@YAHPEAX0PEAU_EMF_ATTRIBUTE_INFO@@PEAU_PAGE_NUMBER@@HKPEAU_devicemodeW@@@Z`
- size: `795`
- prototype: `int(void *, void *, struct _EMF_ATTRIBUTE_INFO *, struct _PAGE_NUMBER *, int, unsigned int, struct _devicemodeW *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, installer_update`

## callees

- `0x180001d60`
- `0x180003200`
- `0x180003cf0`
- `0x1800044a0`
- `0x1800062f8`
- `0x180007210`

## import_xrefs

- `GDI32!GdiGetDevmodeForPage` at `0x180007468`
- `GDI32!GdiGetDevmodeForPage` at `0x180007468`
- `GDI32!GdiGetPageHandle` at `0x1800072e8`
- `GDI32!GdiGetPageHandle` at `0x1800072e8`
- `GDI32!GdiStartPageEMF` at `0x1800073c1`
- `GDI32!GdiStartPageEMF` at `0x1800073c1`
- `GDI32!GdiEndPageEMF` at `0x1800074d0`
- `GDI32!GdiEndPageEMF` at `0x1800074d0`

## pseudocode

```c
__int64 __fastcall PrintOneSideReverseEMF(
        HANDLE a1,
        HDC a2,
        struct _EMF_ATTRIBUTE_INFO *a3,
        struct _PAGE_NUMBER *a4,
        int a5,
        DWORD dwOptimization,
        struct _devicemodeW *a7)
{
  struct _PAGE_NUMBER *v7; // r15
  unsigned int v10; // ebx
  struct _devicemodeW *v11; // r8
  unsigned int v12; // esi
  int v13; // ebp
  unsigned int v14; // eax
  struct _PAGE_NUMBER *v15; // r14
  unsigned int v16; // r12d
  DWORD v17; // edi
  DWORD v18; // r9d
  struct _PAGE_NUMBER *v19; // rax
  struct _PAGE_NUMBER *i; // rax
  HDC v21; // rdi
  __int64 v22; // rcx
  unsigned int v23; // [rsp+50h] [rbp-78h]
  int dmOrientation; // [rsp+54h] [rbp-74h]
  unsigned int v25; // [rsp+58h] [rbp-70h]
  DWORD pdwPageType; // [rsp+5Ch] [rbp-6Ch] BYREF
  int v27; // [rsp+60h] [rbp-68h] BYREF
  PDEVMODEW pCurrDM; // [rsp+68h] [rbp-60h] BYREF
  void *PageHandle; // [rsp+70h] [rbp-58h]
  HANDLE SpoolFileHandle; // [rsp+D0h] [rbp+8h]
  HDC hdc; // [rsp+D8h] [rbp+10h]
  int v32; // [rsp+E8h] [rbp+20h]

  hdc = a2;
  SpoolFileHandle = a1;
  pdwPageType = 0;
  v7 = a4;
  v27 = 0;
  pCurrDM = 0;
  if ( !a4 )
    return 1;
  v10 = 1;
  v11 = a7;
  v12 = *((_DWORD *)a3 + 7);
  v32 = 0;
  v13 = (a5 != 0) + 1;
  dmOrientation = a7->dmOrientation;
  v14 = *((_DWORD *)a3 + 8);
  v23 = v14;
  PageHandle = 0;
LABEL_4:
  if ( v13 )
  {
    if ( !v7 )
      return 0;
    v15 = v7;
    v16 = 1;
    while ( 1 )
    {
      if ( !v15 || v16 > v14 )
      {
        if ( !v32 )
          goto LABEL_49;
        if ( !GdiEndPageEMF(a1, dwOptimization) )
          return 0;
        a1 = SpoolFileHandle;
        a2 = hdc;
        v11 = a7;
        v32 = 0;
        v14 = v23;
LABEL_49:
        v7 = *(struct _PAGE_NUMBER **)v7;
        --v13;
        goto LABEL_4;
      }
      v17 = *((_DWORD *)v15 + 4);
      if ( !v17 )
        v17 = -1;
      if ( v17 <= v12 )
      {
        PageHandle = GdiGetPageHandle(a1, v17, &pdwPageType);
        if ( !PageHandle )
          return 0;
        a1 = SpoolFileHandle;
        a2 = hdc;
        v14 = v23;
        v11 = a7;
      }
      v25 = 1;
      if ( v16 == 1 )
        break;
      if ( v14 <= 1 )
        goto LABEL_35;
      if ( v17 > v12 )
        goto LABEL_38;
      pCurrDM = 0;
      if ( !GdiGetDevmodeForPage(a1, v17, &pCurrDM, 0)
        || !pCurrDM
        || !(unsigned int)BIsDevmodeOfLeastAcceptableSize(pCurrDM) )
      {
        goto LABEL_36;
      }
      v21 = hdc;
      if ( *(__int16 *)(v22 + 76) != dmOrientation )
      {
        v25 = 32769;
        BUpdateAttributes(hdc, a3);
      }
LABEL_37:
      if ( !(unsigned int)PlayEMFPage(SpoolFileHandle, v21, PageHandle, a3, v16, v25) )
        return 0;
LABEL_38:
      v15 = (struct _PAGE_NUMBER *)*((_QWORD *)v15 + 1);
      ++v16;
      a1 = SpoolFileHandle;
      a2 = hdc;
      v14 = v23;
      v11 = a7;
    }
    if ( v17 > v12 )
    {
      v19 = v15;
      while ( 1 )
      {
        v18 = *((_DWORD *)v19 + 4);
        if ( v18 )
        {
          if ( v18 <= v12 )
            break;
        }
        v19 = (struct _PAGE_NUMBER *)*((_QWORD *)v19 + 1);
        if ( !v19 )
          goto LABEL_21;
      }
    }
    else
    {
      v18 = v17;
LABEL_21:
      if ( !v18 || v18 > v12 )
        goto LABEL_24;
    }
    if ( !(unsigned int)ResetDCForNewDevmode(a1, a2, a3, v18, 0, dwOptimization, (PDEVMODEW)&v27, v11, &pCurrDM) )
      return 0;
LABEL_24:
    if ( v17 > v12 && (unsigned int)BAnyReasonNotToPrintBlankPage(a3, v12) == 1 )
    {
      for ( i = v15; i; i = (struct _PAGE_NUMBER *)*((_QWORD *)i + 1) )
      {
        if ( *((_DWORD *)i + 4) && *((_DWORD *)i + 4) <= v12 )
          goto LABEL_31;
      }
    }
    else
    {
LABEL_31:
      if ( !GdiStartPageEMF(SpoolFileHandle) )
        return 0;
      v32 = 1;
    }
    if ( pCurrDM )
      dmOrientation = pCurrDM->dmOrientation;
LABEL_35:
    if ( v17 > v12 )
      goto LABEL_38;
LABEL_36:
    v21 = hdc;
    goto LABEL_37;
  }
  return v10;
}

```

## disassembly

```asm
0x180007210  mov     rax, rsp
0x180007213  mov     [rax+10h], rdx
0x180007217  mov     [rax+8], rcx
0x18000721b  push    rbx
0x18000721c  push    rbp
0x18000721d  push    rsi
0x18000721e  push    rdi
0x18000721f  push    r12
0x180007221  push    r13
0x180007223  push    r14
0x180007225  push    r15
0x180007227  sub     rsp, 88h
0x18000722e  mov     dword ptr [rax-6Ch], 0
0x180007235  mov     r15, r9
0x180007238  mov     dword ptr [rax-68h], 0
0x18000723f  mov     r13, r8
0x180007242  mov     qword ptr [rax-60h], 0
0x18000724a  test    r9, r9
0x18000724d  jnz     short loc_180007258
0x18000724f  lea     eax, [r9+1]
0x180007253  jmp     loc_180007517
0x180007258  neg     [rsp+0C8h+arg_20]
0x18000725f  mov     ebx, 1
0x180007264  mov     r8, [rsp+0C8h+arg_30]
0x18000726c  mov     esi, [r13+1Ch]
0x180007270  sbb     ebp, ebp
0x180007272  neg     ebp
0x180007274  mov     [rsp+0C8h+arg_18], 0
0x18000727f  add     ebp, ebx
0x180007281  mov     [rsp+0C8h+arg_10], 0
0x18000728c  movsx   eax, word ptr [r8+4Ch]
0x180007291  or      r9d, 0FFFFFFFFh
0x180007295  mov     [rsp+0C8h+var_74], eax
0x180007299  mov     eax, [r13+20h]
0x18000729d  mov     [rsp+0C8h+var_78], eax
0x1800072a1  mov     [rsp+0C8h+var_58], 0
0x1800072aa  test    ebp, ebp
0x1800072ac  jz      loc_180007515
0x1800072b2  test    r15, r15
0x1800072b5  jz      loc_18000750E
0x1800072bb  mov     r14, r15
0x1800072be  mov     r12d, ebx
0x1800072c1  test    r14, r14
0x1800072c4  jz      loc_1800074BF
0x1800072ca  cmp     r12d, eax
0x1800072cd  ja      loc_1800074BF
0x1800072d3  mov     edi, [r14+10h]
0x1800072d7  test    edi, edi
0x1800072d9  cmovz   edi, r9d
0x1800072dd  cmp     edi, esi
0x1800072df  ja      short loc_180007318
0x1800072e1  lea     r8, [rsp+0C8h+pdwPageType]; pdwPageType
0x1800072e6  mov     edx, edi; Page
0x1800072e8  call    cs:__imp_GdiGetPageHandle
0x1800072ee  mov     [rsp+0C8h+var_58], rax
0x1800072f3  test    rax, rax
0x1800072f6  jz      loc_18000750E
0x1800072fc  mov     rcx, [rsp+0C8h+SpoolFileHandle]; SpoolFileHandle
0x180007304  mov     rdx, [rsp+0C8h+hdc]; hdc
0x18000730c  mov     eax, [rsp+0C8h+var_78]
0x180007310  mov     r8, [rsp+0C8h+arg_30]
0x180007318  mov     [rsp+0C8h+var_70], ebx
0x18000731c  cmp     r12d, ebx
0x18000731f  jnz     loc_18000744D
0x180007325  cmp     edi, esi
0x180007327  ja      short loc_18000732E
0x180007329  mov     r9d, edi
0x18000732c  jmp     short loc_180007348
0x18000732e  mov     rax, r14
0x180007331  mov     r9d, [rax+10h]; dwPageNumber
0x180007335  test    r9d, r9d
0x180007338  jz      short loc_18000733F
0x18000733a  cmp     r9d, esi
0x18000733d  jbe     short loc_180007352
0x18000733f  mov     rax, [rax+8]
0x180007343  test    rax, rax
0x180007346  jnz     short loc_180007331
0x180007348  test    r9d, r9d
0x18000734b  jz      short loc_18000738E
0x18000734d  cmp     r9d, esi
0x180007350  ja      short loc_18000738E
0x180007352  lea     rax, [rsp+0C8h+pCurrDM]
0x180007357  mov     [rsp+0C8h+var_88], rax; struct _devicemodeW **
0x18000735c  lea     rax, [rsp+0C8h+var_68]
0x180007361  mov     [rsp+0C8h+var_90], r8; struct _devicemodeW *
0x180007366  mov     r8, r13; struct _EMF_ATTRIBUTE_INFO *
0x180007369  mov     [rsp+0C8h+var_98], rax; pCurrDM
0x18000736e  mov     eax, [rsp+0C8h+dwOptimization]
0x180007375  mov     [rsp+0C8h+var_A0], eax; dwOptimization
0x180007379  mov     [rsp+0C8h+var_A8], 0; int
0x180007381  call    ?ResetDCForNewDevmode@@YAHPEAX0PEAU_EMF_ATTRIBUTE_INFO@@KHKPEAHPEAU_devicemodeW@@PEAPEAU2@@Z; ResetDCForNewDevmode(void *,void *,_EMF_ATTRIBUTE_INFO *,ulong,int,ulong,int *,_devicemodeW *,_devicemodeW * *)
0x180007386  test    eax, eax
0x180007388  jz      loc_18000750E
0x18000738e  cmp     edi, esi
0x180007390  jbe     short loc_1800073B9
0x180007392  mov     edx, esi; unsigned int
0x180007394  mov     rcx, r13; struct _EMF_ATTRIBUTE_INFO *
0x180007397  call    ?BAnyReasonNotToPrintBlankPage@@YAHPEAU_EMF_ATTRIBUTE_INFO@@K@Z; BAnyReasonNotToPrintBlankPage(_EMF_ATTRIBUTE_INFO *,ulong)
0x18000739c  cmp     eax, ebx
0x18000739e  jnz     short loc_1800073B9
0x1800073a0  mov     rax, r14
0x1800073a3  test    rax, rax
0x1800073a6  jz      short loc_1800073D6
0x1800073a8  cmp     dword ptr [rax+10h], 0
0x1800073ac  jbe     short loc_1800073B3
0x1800073ae  cmp     [rax+10h], esi
0x1800073b1  jbe     short loc_1800073B9
0x1800073b3  mov     rax, [rax+8]
0x1800073b7  jmp     short loc_1800073A3
0x1800073b9  mov     rcx, [rsp+0C8h+SpoolFileHandle]; SpoolFileHandle
0x1800073c1  call    cs:__imp_GdiStartPageEMF
0x1800073c7  test    eax, eax
0x1800073c9  jz      loc_18000750E
0x1800073cf  mov     [rsp+0C8h+arg_18], ebx
0x1800073d6  mov     rax, [rsp+0C8h+pCurrDM]
0x1800073db  test    rax, rax
0x1800073de  jz      short loc_1800073E8
0x1800073e0  movsx   eax, word ptr [rax+4Ch]
0x1800073e4  mov     [rsp+0C8h+var_74], eax
0x1800073e8  cmp     edi, esi
0x1800073ea  ja      short loc_180007421
0x1800073ec  mov     rdi, [rsp+0C8h+hdc]
0x1800073f4  mov     eax, [rsp+0C8h+var_70]
0x1800073f8  mov     r9, r13; struct _EMF_ATTRIBUTE_INFO *
0x1800073fb  mov     r8, [rsp+0C8h+var_58]; void *
0x180007400  mov     rdx, rdi; hdc
0x180007403  mov     rcx, [rsp+0C8h+SpoolFileHandle]; SpoolFileHandle
0x18000740b  mov     [rsp+0C8h+var_A0], eax; unsigned int
0x18000740f  mov     [rsp+0C8h+var_A8], r12d; unsigned int
0x180007414  call    ?PlayEMFPage@@YAHPEAX00QEAU_EMF_ATTRIBUTE_INFO@@KK@Z; PlayEMFPage(void *,void *,void *,_EMF_ATTRIBUTE_INFO * const,ulong,ulong)
0x180007419  test    eax, eax
0x18000741b  jz      loc_18000750E
0x180007421  mov     r14, [r14+8]
0x180007425  add     r12d, ebx
0x180007428  mov     rcx, [rsp+0C8h+SpoolFileHandle]
0x180007430  or      r9d, 0FFFFFFFFh
0x180007434  mov     rdx, [rsp+0C8h+hdc]
0x18000743c  mov     eax, [rsp+0C8h+var_78]
0x180007440  mov     r8, [rsp+0C8h+arg_30]
0x180007448  jmp     loc_1800072C1
0x18000744d  cmp     eax, ebx
0x18000744f  jbe     short loc_1800073E8
0x180007451  cmp     edi, esi
0x180007453  ja      short loc_180007421
0x180007455  xor     r9d, r9d; pLastDM
0x180007458  mov     [rsp+0C8h+pCurrDM], 0
0x180007461  lea     r8, [rsp+0C8h+pCurrDM]; pCurrDM
0x180007466  mov     edx, edi; dwPageNumber
0x180007468  call    cs:__imp_GdiGetDevmodeForPage
0x18000746e  test    eax, eax
0x180007470  jz      loc_1800073EC
0x180007476  mov     rcx, [rsp+0C8h+pCurrDM]; struct _devicemodeW *
0x18000747b  test    rcx, rcx
0x18000747e  jz      loc_1800073EC
0x180007484  call    ?BIsDevmodeOfLeastAcceptableSize@@YAHPEAU_devicemodeW@@@Z; BIsDevmodeOfLeastAcceptableSize(_devicemodeW *)
0x180007489  test    eax, eax
0x18000748b  jz      loc_1800073EC
0x180007491  movsx   eax, word ptr [rcx+4Ch]
0x180007495  mov     rdi, [rsp+0C8h+hdc]
0x18000749d  cmp     eax, [rsp+0C8h+var_74]
0x1800074a1  jz      loc_1800073F4
0x1800074a7  mov     rdx, r13; struct _EMF_ATTRIBUTE_INFO *
0x1800074aa  mov     [rsp+0C8h+var_70], 8001h
0x1800074b2  mov     rcx, rdi; hdc
0x1800074b5  call    ?BUpdateAttributes@@YAHPEAXPEAU_EMF_ATTRIBUTE_INFO@@@Z; BUpdateAttributes(void *,_EMF_ATTRIBUTE_INFO *)
0x1800074ba  jmp     loc_1800073F4
0x1800074bf  cmp     [rsp+0C8h+arg_18], 0
0x1800074c7  jz      short loc_180007503
0x1800074c9  mov     edx, [rsp+0C8h+dwOptimization]; dwOptimization
0x1800074d0  call    cs:__imp_GdiEndPageEMF
0x1800074d6  test    eax, eax
0x1800074d8  jz      short loc_18000750E
0x1800074da  mov     rcx, [rsp+0C8h+SpoolFileHandle]
0x1800074e2  xor     eax, eax
0x1800074e4  mov     rdx, [rsp+0C8h+hdc]
0x1800074ec  or      r9d, 0FFFFFFFFh
0x1800074f0  mov     r8, [rsp+0C8h+arg_30]
0x1800074f8  mov     [rsp+0C8h+arg_18], eax
0x1800074ff  mov     eax, [rsp+0C8h+var_78]
0x180007503  mov     r15, [r15]
0x180007506  add     ebp, r9d
0x180007509  jmp     loc_1800072AA
0x18000750e  mov     ebx, [rsp+0C8h+arg_10]
0x180007515  mov     eax, ebx
0x180007517  add     rsp, 88h
0x18000751e  pop     r15
0x180007520  pop     r14
0x180007522  pop     r13
0x180007524  pop     r12
0x180007526  pop     rdi
0x180007527  pop     rsi
0x180007528  pop     rbp
0x180007529  pop     rbx
0x18000752a  retn
```
