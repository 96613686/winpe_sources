# CShellItem::_GetIcon(tagSIZE,int,int,HBITMAP__ * *)

- ea: `0x18009b70c`
- end: `0x18009b8a6`
- name: `?_GetIcon@CShellItem@@IEAAJUtagSIZE@@HHPEAPEAUHBITMAP__@@@Z`
- size: `410`
- prototype: `__int64 __fastcall(CShellItem *__hidden this, struct tagSIZE, int, int, HBITMAP *)`
- caller_count: `1`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callers

- `0x1802931b0`

## callees

- `0x1800937a0`
- `0x18009b70c`
- `0x18009b9c0`
- `0x18009bec0`
- `0x18009cd50`
- `0x18009d300`
- `0x18009d9c0`
- `0x18009ebc8`
- `0x1803b1f60`
- `0x180502778`
- `0x1805027e0`
- `0x180502800`
- `0x180503060`
- `0x180503250`
- `0x180503670`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009b82c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009b82c`
- `GDI32!DeleteObject` at `0x180662b2d`
- `GDI32!DeleteObject` at `0x180662c45`
- `GDI32!DeleteObject` at `0x180662d88`
- `GDI32!DeleteObject` at `0x180662b2d`
- `GDI32!DeleteObject` at `0x180662c45`
- `GDI32!DeleteObject` at `0x180662d88`
- `GDI32!CreateSolidBrush` at `0x180662c18`
- `GDI32!CreateSolidBrush` at `0x180662c18`
- `GDI32!SelectObject` at `0x180662b46`
- `GDI32!SelectObject` at `0x180662cd1`
- `GDI32!SelectObject` at `0x180662d62`
- `GDI32!SelectObject` at `0x180662d9b`
- `GDI32!SelectObject` at `0x180662b46`
- `GDI32!SelectObject` at `0x180662cd1`
- `GDI32!SelectObject` at `0x180662d62`
- `GDI32!SelectObject` at `0x180662d9b`
- `GDI32!CreateCompatibleDC` at `0x180662b10`
- `GDI32!CreateCompatibleDC` at `0x180662cb0`
- `GDI32!CreateCompatibleDC` at `0x180662b10`
- `GDI32!CreateCompatibleDC` at `0x180662cb0`
- `GDI32!GdiAlphaBlend` at `0x180662d50`
- `GDI32!GdiAlphaBlend` at `0x180662d50`
- `GDI32!DeleteDC` at `0x180662d71`
- `GDI32!DeleteDC` at `0x180662daa`
- `GDI32!DeleteDC` at `0x180662d71`
- `GDI32!DeleteDC` at `0x180662daa`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHFillRectClr` at `0x180662b9c`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHFillRectClr` at `0x180662b9c`
- `ext-ms-win-ntuser-gui-l1-1-1!FrameRect` at `0x180662c36`
- `ext-ms-win-ntuser-gui-l1-1-1!FrameRect` at `0x180662c36`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CShellItem::_GetIcon(CShellItem *this, struct tagSIZE a2, int a3, int a4, HBITMAP *a5)
{
  struct IShellItem *v7; // rsi
  int ParentAndChildIDListFromItem; // edi
  int v9; // ecx
  int BitmapFromIcon; // eax
  void *v11; // rcx
  int v13; // r14d
  HDC CompatibleDC; // rax
  HDC v15; // r15
  unsigned int TileBackgroundColorForItem; // eax
  int v17; // r13d
  int v18; // esi
  char v19; // di
  int v20; // ebx
  HBRUSH SolidBrush; // rax
  HBRUSH v22; // rbx
  LONG IconSizeForPhotoMode; // eax
  unsigned int v24; // r14d
  HDC v25; // rax
  HDC hdcSrc; // rsi
  HGDIOBJ v27; // rbx
  int IsThreadRTL; // eax
  BLENDFUNCTION v29; // [rsp+60h] [rbp-A0h] BYREF
  int xoriginDest[4]; // [rsp+68h] [rbp-98h] BYREF
  struct tagSIZE wDest; // [rsp+78h] [rbp-88h] BYREF
  HGDIOBJ ho; // [rsp+80h] [rbp-80h] BYREF
  int v33; // [rsp+88h] [rbp-78h]
  HGDIOBJ h; // [rsp+90h] [rbp-70h] BYREF
  struct tagRECT v35; // [rsp+98h] [rbp-68h] BYREF
  HGDIOBJ v36; // [rsp+A8h] [rbp-58h]
  _QWORD v37[4]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v38; // [rsp+D0h] [rbp-30h]
  int v39; // [rsp+E0h] [rbp-20h]
  struct tagRGBQUAD *v40; // [rsp+E8h] [rbp-18h] BYREF
  int v41; // [rsp+F0h] [rbp-10h] BYREF
  LPVOID pv; // [rsp+F8h] [rbp-8h] BYREF
  struct IShellFolder *v43; // [rsp+100h] [rbp+0h] BYREF
  RECT rc; // [rsp+108h] [rbp+8h] BYREF

  v33 = a4;
  *(struct tagSIZE *)xoriginDest = a2;
  *a5 = 0;
  v43 = 0;
  pv = 0;
  v7 = (struct IShellItem *)(((unsigned __int64)this + 8) & -(__int64)(this != 0));
  ParentAndChildIDListFromItem = GetParentAndChildIDListFromItem(
                                   v7,
                                   &GUID_000214e6_0000_0000_c000_000000000046,
                                   &v43,
                                   &pv);
  if ( ParentAndChildIDListFromItem >= 0 )
  {
    v41 = 0;
    if ( a4 )
    {
      v37[0] = 0;
      v37[1] = v43;
      v37[2] = pv;
      v37[3] = 0;
      v38 = 0;
      v39 = 512;
      ParentAndChildIDListFromItem = SHMapIDListToSystemImageListIndexAsync2(v37, &v41, 0);
      if ( ParentAndChildIDListFromItem < 0 )
        goto LABEL_11;
      v9 = v41;
    }
    else
    {
      v29 = 0;
      _GetILIndexFromItem(v43, (const struct _ITEMID_CHILD *)pv, 0, (int *)&v29);
      v9 = (int)v29;
      v41 = (int)v29;
      if ( *(int *)&v29 < 0 )
      {
        ParentAndChildIDListFromItem = -2147483638;
        goto LABEL_11;
      }
    }
    if ( (a3 & 0x80u) == 0 )
    {
      if ( (a3 & 0x20000000) != 0 )
        BitmapFromIcon = CreateBitmapFromIcon(0, v9, 0, (const struct tagSIZE *)xoriginDest, a5);
      else
        BitmapFromIcon = _CreateBitmapFromSystemImageListWithAlpha(v9, a4, xoriginDest[0], a5);
      ParentAndChildIDListFromItem = BitmapFromIcon;
      goto LABEL_11;
    }
    v13 = a3 & 0x40;
    if ( v13 )
      xoriginDest[1] = GetWideThumbnailHeightFromWidth(xoriginDest[0]);
    ho = 0;
    v40 = 0;
    ParentAndChildIDListFromItem = Create32BitHBITMAP(
                                     0,
                                     (const struct tagSIZE *)xoriginDest,
                                     (void **)&v40,
                                     (HBITMAP *)&ho);
    if ( ParentAndChildIDListFromItem >= 0 )
    {
      CompatibleDC = CreateCompatibleDC(0);
      v15 = CompatibleDC;
      if ( !CompatibleDC )
      {
        ParentAndChildIDListFromItem = -2147467259;
LABEL_20:
        DeleteObject(ho);
        goto LABEL_11;
      }
      v36 = SelectObject(CompatibleDC, ho);
      TileBackgroundColorForItem = GetTileBackgroundColorForItem(v7);
      *(_QWORD *)&rc.left = 0;
      v17 = xoriginDest[0];
      rc.right = xoriginDest[0];
      rc.bottom = xoriginDest[1];
      v18 = (unsigned __int8)TileBackgroundColorForItem;
      v19 = BYTE2(TileBackgroundColorForItem);
      v20 = BYTE1(TileBackgroundColorForItem);
      SHFillRectClr(
        v15,
        &rc,
        (unsigned __int8)TileBackgroundColorForItem
      | (BYTE2(TileBackgroundColorForItem) << 16)
      | (unsigned int)(v20 << 8));
      SolidBrush = CreateSolidBrush(
                     (unsigned __int8)(228 * v18 / 255 + 27)
                   | ((unsigned __int8)(28 * v20 + 27) << 8)
                   | ((unsigned __int8)(28 * v19 + 27) << 16));
      v22 = SolidBrush;
      if ( SolidBrush )
      {
        FrameRect(v15, &rc, SolidBrush);
        DeleteObject(v22);
      }
      DIBSectionUtil::MakeOpaque(v17, xoriginDest[1], v40);
      h = 0;
      if ( v13 )
        IconSizeForPhotoMode = GetIconSizeForPhotoMode(v17);
      else
        IconSizeForPhotoMode = GetIconSizeForTileMode(v17);
      v24 = IconSizeForPhotoMode;
      wDest.cx = IconSizeForPhotoMode;
      wDest.cy = IconSizeForPhotoMode;
      ParentAndChildIDListFromItem = CreateBitmapFromIcon(0, v41, v33, &wDest, (HBITMAP *)&h);
      if ( ParentAndChildIDListFromItem >= 0 )
      {
        v25 = CreateCompatibleDC(0);
        hdcSrc = v25;
        if ( v25 )
        {
          ParentAndChildIDListFromItem = 0;
          v27 = SelectObject(v25, h);
          *(_QWORD *)&v35.left = 0;
          v35.right = v17;
          v35.bottom = xoriginDest[1];
          *(_OWORD *)xoriginDest = 0;
          IsThreadRTL = Mirror_IsThreadRTL();
          GetIconRectFromBackgroundRect(v24, IsThreadRTL, &v35, (struct tagRECT *)xoriginDest);
          v29 = (BLENDFUNCTION)33488896;
          GdiAlphaBlend(
            v15,
            xoriginDest[0],
            xoriginDest[1],
            wDest.cx,
            wDest.cy,
            hdcSrc,
            0,
            0,
            wDest.cx,
            wDest.cy,
            (BLENDFUNCTION)33488896);
          SelectObject(hdcSrc, v27);
          DeleteDC(hdcSrc);
        }
        else
        {
          ParentAndChildIDListFromItem = -2147467259;
        }
        DeleteObject(h);
      }
      SelectObject(v15, v36);
      DeleteDC(v15);
      if ( ParentAndChildIDListFromItem < 0 )
        goto LABEL_20;
      *a5 = (HBITMAP)ho;
    }
  }
LABEL_11:
  v11 = pv;
  pv = 0;
  CoTaskMemFree(v11);
  if ( v43 )
    ((void (__fastcall *)(struct IShellFolder *))v43->lpVtbl->Release)(v43);
  return (unsigned int)ParentAndChildIDListFromItem;
}

```

## disassembly

```asm
0x18009b70c  mov     [rsp-8+arg_10], rbx
0x18009b711  push    rbp
0x18009b712  push    rsi
0x18009b713  push    rdi
0x18009b714  push    r12
0x18009b716  push    r13
0x18009b718  push    r14
0x18009b71a  push    r15
0x18009b71c  lea     rbp, [rsp-20h]
0x18009b721  sub     rsp, 120h
0x18009b728  mov     rax, cs:__security_cookie
0x18009b72f  xor     rax, rsp
0x18009b732  mov     [rbp+50h+var_38], rax
0x18009b736  mov     ebx, r9d
0x18009b739  mov     [rbp+50h+var_C8], ebx
0x18009b73c  mov     r14d, r8d
0x18009b73f  mov     qword ptr [rsp+150h+xoriginDest], rdx
0x18009b744  mov     r12, [rbp+50h+arg_20]
0x18009b74b  xor     r13d, r13d
0x18009b74e  mov     [r12], r13
0x18009b752  mov     [rbp+50h+var_50], r13
0x18009b756  mov     [rbp+50h+pv], r13
0x18009b75a  lea     rax, [rcx+8]
0x18009b75e  neg     rcx
0x18009b761  sbb     rsi, rsi
0x18009b764  and     rsi, rax
0x18009b767  lea     r9, [rbp+50h+pv]
0x18009b76b  lea     r8, [rbp+50h+var_50]
0x18009b76f  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046
0x18009b776  mov     rcx, rsi
0x18009b779  call    GetParentAndChildIDListFromItem
0x18009b77e  mov     edi, eax
0x18009b780  test    eax, eax
0x18009b782  js      loc_18009B824
0x18009b788  mov     [rbp+50h+var_60], r13d
0x18009b78c  test    ebx, ebx
0x18009b78e  jnz     short loc_18009B7BC
0x18009b790  mov     dword ptr [rsp+150h+var_F0.BlendOp], r13d
0x18009b795  lea     r9, [rsp+150h+var_F0]; int *
0x18009b79a  xor     r8d, r8d; unsigned int
0x18009b79d  mov     rdx, [rbp+50h+pv]; struct _ITEMID_CHILD *
0x18009b7a1  mov     rcx, [rbp+50h+var_50]; struct IShellFolder *
0x18009b7a5  call    ?_GetILIndexFromItem@@YAJPEAUIShellFolder@@PEFBU_ITEMID_CHILD@@IPEAH@Z; _GetILIndexFromItem(IShellFolder *,_ITEMID_CHILD const *,uint,int *)
0x18009b7aa  mov     ecx, dword ptr [rsp+150h+var_F0.BlendOp]
0x18009b7ae  mov     [rbp+50h+var_60], ecx
0x18009b7b1  test    ecx, ecx
0x18009b7b3  jns     short loc_18009B7FC
0x18009b7b5  mov     edi, 8000000Ah
0x18009b7ba  jmp     short loc_18009B824
0x18009b7bc  mov     [rbp+50h+var_A0], r13
0x18009b7c0  mov     rax, [rbp+50h+var_50]
0x18009b7c4  mov     [rbp+50h+var_98], rax
0x18009b7c8  mov     rax, [rbp+50h+pv]
0x18009b7cc  mov     [rbp+50h+var_90], rax
0x18009b7d0  mov     [rbp+50h+var_88], r13
0x18009b7d4  xorps   xmm0, xmm0
0x18009b7d7  movdqu  [rbp+50h+var_80], xmm0
0x18009b7dc  mov     [rbp+50h+var_70], 200h
0x18009b7e3  xor     r8d, r8d
0x18009b7e6  lea     rdx, [rbp+50h+var_60]
0x18009b7ea  lea     rcx, [rbp+50h+var_A0]
0x18009b7ee  call    SHMapIDListToSystemImageListIndexAsync2
0x18009b7f3  mov     edi, eax
0x18009b7f5  test    eax, eax
0x18009b7f7  js      short loc_18009B824
0x18009b7f9  mov     ecx, [rbp+50h+var_60]; int
0x18009b7fc  test    r14b, r14b
0x18009b7ff  js      loc_18009B88A
0x18009b805  bt      r14d, 1Dh
0x18009b80a  jnb     short loc_18009B879
0x18009b80c  mov     qword ptr [rsp+150h+hDest], r12; HBITMAP *
0x18009b811  lea     r9, [rsp+150h+xoriginDest]; struct tagSIZE *
0x18009b816  xor     r8d, r8d; int
0x18009b819  mov     edx, ecx; int
0x18009b81b  xor     ecx, ecx; hicon
0x18009b81d  call    ?CreateBitmapFromIcon@@YAJPEAUHICON__@@HHPEBUtagSIZE@@PEAPEAUHBITMAP__@@@Z; CreateBitmapFromIcon(HICON__ *,int,int,tagSIZE const *,HBITMAP__ * *)
0x18009b822  mov     edi, eax
0x18009b824  mov     rcx, [rbp+50h+pv]; pv
0x18009b828  mov     [rbp+50h+pv], r13
0x18009b82c  call    cs:__imp_CoTaskMemFree
0x18009b833  nop     dword ptr [rax+rax+00h]
0x18009b838  nop
0x18009b839  mov     rcx, [rbp+50h+var_50]
0x18009b83d  test    rcx, rcx
0x18009b840  jz      short loc_18009B84F
0x18009b842  mov     rax, [rcx]
0x18009b845  mov     rax, [rax+10h]
0x18009b849  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b84e  nop
0x18009b84f  mov     eax, edi
0x18009b851  mov     rcx, [rbp+50h+var_38]
0x18009b855  xor     rcx, rsp; StackCookie
0x18009b858  call    __security_check_cookie
0x18009b85d  mov     rbx, [rsp+150h+arg_10]
0x18009b865  add     rsp, 120h
0x18009b86c  pop     r15
0x18009b86e  pop     r14
0x18009b870  pop     r13
0x18009b872  pop     r12
0x18009b874  pop     rdi
0x18009b875  pop     rsi
0x18009b876  pop     rbp
0x18009b877  retn
0x18009b879  mov     r9, r12; HBITMAP *
0x18009b87c  mov     r8d, [rsp+150h+xoriginDest]; int
0x18009b881  mov     edx, ebx; int
0x18009b883  call    ?_CreateBitmapFromSystemImageListWithAlpha@@YAJHHHPEAPEAUHBITMAP__@@@Z; _CreateBitmapFromSystemImageListWithAlpha(int,int,int,HBITMAP__ * *)
0x18009b888  jmp     short loc_18009B822
0x18009b88a  and     r14d, 40h
0x18009b88e  jz      loc_180662AE8
0x18009b894  mov     ecx, [rsp+150h+xoriginDest]; unsigned int
0x18009b898  call    ?GetWideThumbnailHeightFromWidth@@YAII@Z; GetWideThumbnailHeightFromWidth(uint)
0x18009b89d  mov     [rsp+150h+xoriginDest+4], eax
0x18009b8a1  jmp     loc_180662AE8
0x180662ae8  mov     [rbp+50h+ho], r13
0x180662aec  mov     [rbp+50h+var_68], r13
0x180662af0  lea     r9, [rbp+50h+ho]; HBITMAP *
0x180662af4  lea     r8, [rbp+50h+var_68]; void **
0x180662af8  lea     rdx, [rsp+150h+xoriginDest]; struct tagSIZE *
0x180662afd  xor     ecx, ecx; HDC
0x180662aff  call    ?Create32BitHBITMAP@@YAJPEAUHDC__@@PEBUtagSIZE@@PEAPEAXPEAPEAUHBITMAP__@@@Z; Create32BitHBITMAP(HDC__ *,tagSIZE const *,void * *,HBITMAP__ * *)
0x180662b04  mov     edi, eax
0x180662b06  test    eax, eax
0x180662b08  js      loc_18009B824
0x180662b0e  xor     ecx, ecx; hdc
0x180662b10  call    cs:__imp_CreateCompatibleDC
0x180662b17  nop     dword ptr [rax+rax+00h]
0x180662b1c  mov     r15, rax
0x180662b1f  test    rax, rax
0x180662b22  jnz     short loc_180662B3F
0x180662b24  mov     edi, 80004005h
0x180662b29  mov     rcx, [rbp+50h+ho]; ho
0x180662b2d  call    cs:__imp_DeleteObject
0x180662b34  nop     dword ptr [rax+rax+00h]
0x180662b39  nop
0x180662b3a  jmp     loc_18009B824
0x180662b3f  mov     rdx, [rbp+50h+ho]; h
0x180662b43  mov     rcx, r15; hdc
0x180662b46  call    cs:__imp_SelectObject
0x180662b4d  nop     dword ptr [rax+rax+00h]
0x180662b52  mov     [rbp+50h+var_A8], rax
0x180662b56  mov     rcx, rsi; struct IShellItem *
0x180662b59  call    ?GetTileBackgroundColorForItem@@YAKPEAUIShellItem@@@Z; GetTileBackgroundColorForItem(IShellItem *)
0x180662b5e  mov     qword ptr [rbp+50h+rc.left], r13
0x180662b62  mov     r13d, [rsp+150h+xoriginDest]
0x180662b67  mov     [rbp+50h+rc.right], r13d
0x180662b6b  mov     ecx, [rsp+150h+xoriginDest+4]
0x180662b6f  mov     [rbp+50h+rc.bottom], ecx
0x180662b72  movzx   esi, al
0x180662b75  mov     ecx, eax
0x180662b77  shr     ecx, 10h
0x180662b7a  movzx   edi, cl
0x180662b7d  movzx   ebx, ax
0x180662b80  shr     ebx, 8
0x180662b83  mov     r8d, ebx
0x180662b86  shl     r8d, 8
0x180662b8a  mov     eax, edi
0x180662b8c  shl     eax, 10h
0x180662b8f  or      r8d, eax
0x180662b92  or      r8d, esi
0x180662b95  lea     rdx, [rbp+50h+rc]
0x180662b99  mov     rcx, r15
0x180662b9c  call    cs:__imp_SHFillRectClr
0x180662ba3  nop     dword ptr [rax+rax+00h]
0x180662ba8  imul    ecx, ebx, 0E4h
0x180662bae  mov     r11d, 80808081h
0x180662bb4  mov     eax, r11d
0x180662bb7  imul    ecx
0x180662bb9  add     edx, ecx
0x180662bbb  sar     edx, 7
0x180662bbe  mov     eax, edx
0x180662bc0  shr     eax, 1Fh
0x180662bc3  add     edx, eax
0x180662bc5  mov     r10b, 1Bh
0x180662bc8  add     dl, r10b
0x180662bcb  movzx   r9d, dl
0x180662bcf  shl     r9d, 8
0x180662bd3  imul    ecx, edi, 0E4h
0x180662bd9  mov     eax, r11d
0x180662bdc  imul    ecx
0x180662bde  add     edx, ecx
0x180662be0  sar     edx, 7
0x180662be3  mov     ecx, edx
0x180662be5  shr     ecx, 1Fh
0x180662be8  add     edx, ecx
0x180662bea  add     dl, r10b
0x180662bed  movzx   ecx, dl
0x180662bf0  shl     ecx, 10h
0x180662bf3  or      ecx, r9d
0x180662bf6  imul    r8d, esi, 0E4h
0x180662bfd  mov     eax, r11d
0x180662c00  imul    r8d
0x180662c03  add     edx, r8d
0x180662c06  sar     edx, 7
0x180662c09  mov     eax, edx
0x180662c0b  shr     eax, 1Fh
0x180662c0e  add     edx, eax
0x180662c10  add     dl, r10b
0x180662c13  movzx   eax, dl
0x180662c16  or      ecx, eax; color
0x180662c18  call    cs:__imp_CreateSolidBrush
0x180662c1f  nop     dword ptr [rax+rax+00h]
0x180662c24  mov     rbx, rax
0x180662c27  test    rax, rax
0x180662c2a  jz      short loc_180662C51
0x180662c2c  mov     r8, rax; hbr
0x180662c2f  lea     rdx, [rbp+50h+rc]; lprc
0x180662c33  mov     rcx, r15; hDC
0x180662c36  call    cs:__imp_FrameRect
0x180662c3d  nop     dword ptr [rax+rax+00h]
0x180662c42  mov     rcx, rbx; ho
0x180662c45  call    cs:__imp_DeleteObject
0x180662c4c  nop     dword ptr [rax+rax+00h]
0x180662c51  mov     r8, [rbp+50h+var_68]; struct tagRGBQUAD *
0x180662c55  mov     edx, [rsp+150h+xoriginDest+4]; unsigned int
0x180662c59  mov     ecx, r13d; unsigned int
0x180662c5c  call    ?MakeOpaque@DIBSectionUtil@@SAXIIPEAUtagRGBQUAD@@@Z; DIBSectionUtil::MakeOpaque(uint,uint,tagRGBQUAD *)
0x180662c61  mov     [rbp+50h+h], 0
0x180662c69  mov     ecx, r13d; unsigned int
0x180662c6c  test    r14d, r14d
0x180662c6f  jz      short loc_180662C78
0x180662c71  call    ?GetIconSizeForPhotoMode@@YAII@Z; GetIconSizeForPhotoMode(uint)
0x180662c76  jmp     short loc_180662C7D
0x180662c78  call    ?GetIconSizeForTileMode@@YAII@Z; GetIconSizeForTileMode(uint)
0x180662c7d  mov     r14d, eax
0x180662c80  mov     [rsp+150h+wDest], eax
0x180662c84  mov     [rsp+150h+var_D4], eax
0x180662c88  lea     rax, [rbp+50h+h]
0x180662c8c  mov     qword ptr [rsp+150h+hDest], rax; HBITMAP *
0x180662c91  lea     r9, [rsp+150h+wDest]; struct tagSIZE *
0x180662c96  mov     r8d, [rbp+50h+var_C8]; int
0x180662c9a  mov     edx, [rbp+50h+var_60]; int
0x180662c9d  xor     ecx, ecx; hicon
0x180662c9f  call    ?CreateBitmapFromIcon@@YAJPEAUHICON__@@HHPEBUtagSIZE@@PEAPEAUHBITMAP__@@@Z; CreateBitmapFromIcon(HICON__ *,int,int,tagSIZE const *,HBITMAP__ * *)
0x180662ca4  mov     edi, eax
0x180662ca6  test    eax, eax
0x180662ca8  js      loc_180662D94
0x180662cae  xor     ecx, ecx; hdc
0x180662cb0  call    cs:__imp_CreateCompatibleDC
0x180662cb7  nop     dword ptr [rax+rax+00h]
0x180662cbc  mov     rsi, rax
0x180662cbf  test    rax, rax
0x180662cc2  jz      loc_180662D7F
0x180662cc8  xor     edi, edi
0x180662cca  mov     rdx, [rbp+50h+h]; h
0x180662cce  mov     rcx, rax; hdc
0x180662cd1  call    cs:__imp_SelectObject
0x180662cd8  nop     dword ptr [rax+rax+00h]
0x180662cdd  mov     rbx, rax
0x180662ce0  mov     qword ptr [rbp+50h+var_B8.left], rdi
0x180662ce4  mov     [rbp+50h+var_B8.right], r13d
0x180662ce8  mov     eax, [rsp+150h+xoriginDest+4]
0x180662cec  mov     [rbp+50h+var_B8.bottom], eax
0x180662cef  xorps   xmm0, xmm0
0x180662cf2  movups  xmmword ptr [rsp+150h+xoriginDest], xmm0
0x180662cf7  call    ?Mirror_IsThreadRTL@@YAHXZ; Mirror_IsThreadRTL(void)
0x180662cfc  mov     edx, eax; int
0x180662cfe  lea     r9, [rsp+150h+xoriginDest]; struct tagRECT *
0x180662d03  lea     r8, [rbp+50h+var_B8]; struct tagRECT *
0x180662d07  mov     ecx, r14d; unsigned int
0x180662d0a  call    ?GetIconRectFromBackgroundRect@@YAXIHPEBUtagRECT@@PEAU1@@Z; GetIconRectFromBackgroundRect(uint,int,tagRECT const *,tagRECT *)
0x180662d0f  xor     ecx, ecx
0x180662d11  mov     dword ptr [rsp+150h+var_F0.BlendOp], 1FF0000h
0x180662d19  mov     eax, dword ptr [rsp+150h+var_F0.BlendOp]
0x180662d1d  mov     dword ptr [rsp+150h+ftn.BlendOp], eax; ftn
0x180662d21  mov     eax, [rsp+150h+var_D4]
0x180662d25  mov     [rsp+150h+hSrc], eax; hSrc
0x180662d29  mov     r9d, [rsp+150h+wDest]; wDest
0x180662d2e  mov     [rsp+150h+wSrc], r9d; wSrc
0x180662d33  mov     [rsp+150h+yoriginSrc], ecx; yoriginSrc
0x180662d37  mov     [rsp+150h+xoriginSrc], ecx; xoriginSrc
0x180662d3b  mov     [rsp+150h+hdcSrc], rsi; hdcSrc
0x180662d40  mov     [rsp+150h+hDest], eax; hDest
0x180662d44  mov     r8d, [rsp+150h+xoriginDest+4]; yoriginDest
0x180662d49  mov     edx, [rsp+150h+xoriginDest]; xoriginDest
0x180662d4d  mov     rcx, r15; hdcDest
0x180662d50  call    cs:__imp_GdiAlphaBlend
0x180662d57  nop     dword ptr [rax+rax+00h]
0x180662d5c  mov     rdx, rbx; h
0x180662d5f  mov     rcx, rsi; hdc
0x180662d62  call    cs:__imp_SelectObject
0x180662d69  nop     dword ptr [rax+rax+00h]
0x180662d6e  mov     rcx, rsi; hdc
0x180662d71  call    cs:__imp_DeleteDC
0x180662d78  nop     dword ptr [rax+rax+00h]
0x180662d7d  jmp     short loc_180662D84
0x180662d7f  mov     edi, 80004005h
0x180662d84  mov     rcx, [rbp+50h+h]; ho
0x180662d88  call    cs:__imp_DeleteObject
0x180662d8f  nop     dword ptr [rax+rax+00h]
0x180662d94  mov     rdx, [rbp+50h+var_A8]; h
0x180662d98  mov     rcx, r15; hdc
0x180662d9b  call    cs:__imp_SelectObject
0x180662da2  nop     dword ptr [rax+rax+00h]
0x180662da7  mov     rcx, r15; hdc
0x180662daa  call    cs:__imp_DeleteDC
0x180662db1  nop     dword ptr [rax+rax+00h]
0x180662db6  xor     r13d, r13d
0x180662db9  test    edi, edi
0x180662dbb  js      loc_180662B29
  ... truncated ...
```
