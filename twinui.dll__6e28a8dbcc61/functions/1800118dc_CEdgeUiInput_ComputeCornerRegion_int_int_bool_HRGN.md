# CEdgeUiInput::_ComputeCornerRegion(int,int,bool,HRGN__ * *)

- ea: `0x1800118dc`
- end: `0x180011c5f`
- name: `?_ComputeCornerRegion@CEdgeUiInput@@AEAAJHH_NPEAPEAUHRGN__@@@Z`
- size: `899`
- prototype: `int(CEdgeUiInput *__hidden this, int, int, bool, HRGN *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180012650`

## callees

- `0x180008acc`
- `0x1800118dc`
- `0x18013d330`
- `0x1803a3010`

## import_xrefs

- `GDI32!DeleteObject` at `0x180011a7b`
- `GDI32!DeleteObject` at `0x180011b0d`
- `GDI32!DeleteObject` at `0x180011b1b`
- `GDI32!DeleteObject` at `0x180011a7b`
- `GDI32!DeleteObject` at `0x180011b0d`
- `GDI32!DeleteObject` at `0x180011b1b`
- `GDI32!CreateRectRgn` at `0x180011a2a`
- `GDI32!CreateRectRgn` at `0x180011a4a`
- `GDI32!CreateRectRgn` at `0x180011ae2`
- `GDI32!CreateRectRgn` at `0x180011a2a`
- `GDI32!CreateRectRgn` at `0x180011a4a`
- `GDI32!CreateRectRgn` at `0x180011ae2`
- `GDI32!CombineRgn` at `0x180011a6e`
- `GDI32!CombineRgn` at `0x180011afc`
- `GDI32!CombineRgn` at `0x180011a6e`
- `GDI32!CombineRgn` at `0x180011afc`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x1800119e5`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x1800119ef`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x180011b9b`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x180011ba5`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x180011baf`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x1800119e5`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x1800119ef`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x180011b9b`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x180011ba5`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x180011baf`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRect` at `0x180011a11`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRect` at `0x180011b3a`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRect` at `0x180011b5a`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRect` at `0x180011b7f`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRect` at `0x180011bdc`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRect` at `0x180011bfb`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRect` at `0x180011c15`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRect` at `0x180011c3d`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRect` at `0x180011a11`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRect` at `0x180011b3a`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRect` at `0x180011b5a`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRect` at `0x180011b7f`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRect` at `0x180011bdc`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRect` at `0x180011bfb`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRect` at `0x180011c15`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRect` at `0x180011c3d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CEdgeUiInput::_ComputeCornerRegion(CEdgeUiInput *this, int a2, int a3, char a4, HRGN *a5)
{
  __int64 (__fastcall ***v9)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v10)(_QWORD, GUID *, __int64 *); // rbx
  signed int v11; // edi
  int v12; // r8d
  int v13; // edx
  int v14; // r9d
  HRGN RectRgn; // rbx
  HRGN v16; // rax
  HRGN v17; // rsi
  __int64 v18; // rcx
  HRGN v20; // rax
  HRGN v21; // r14
  int v22; // r8d
  int yBottom; // [rsp+20h] [rbp-60h]
  int yBottoma; // [rsp+20h] [rbp-60h]
  int yTop; // [rsp+30h] [rbp-50h] BYREF
  int v26; // [rsp+34h] [rbp-4Ch] BYREF
  int v27; // [rsp+38h] [rbp-48h] BYREF
  int v28; // [rsp+3Ch] [rbp-44h] BYREF
  __int64 v29; // [rsp+40h] [rbp-40h] BYREF
  struct tagRECT v30; // [rsp+48h] [rbp-38h] BYREF
  struct tagRECT v31; // [rsp+58h] [rbp-28h] BYREF
  struct tagRECT rc; // [rsp+68h] [rbp-18h] BYREF

  *a5 = 0;
  rc = 0;
  v31 = 0;
  v30 = 0;
  v29 = 0;
  v9 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 2);
  v10 = **v9;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
  v11 = v10(v9, &GUID_bd9269d0_df79_47e0_8cd2_78762eb6d1bb, &v29);
  if ( v11 < 0 )
    goto LABEL_15;
  v27 = 0;
  yTop = 0;
  v28 = 0;
  v26 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64, int *, int *, int *, int *))(*(_QWORD *)v29 + 24LL))(
          v29,
          &v27,
          &yTop,
          &v28,
          &v26);
  if ( v11 < 0 )
    goto LABEL_15;
  switch ( *((_DWORD *)this + 34) )
  {
    case 4:
      SetRect(&rc, 0, 0, a2, 1);
      yBottoma = a3;
      v22 = yTop;
      if ( !a4 )
      {
LABEL_22:
        SetRect(&v31, 0, v22, 1, yBottoma);
        yBottom = yTop;
        v12 = 0;
LABEL_23:
        v14 = v27;
        v13 = 0;
        goto LABEL_10;
      }
LABEL_24:
      SetRect(&v31, a2 - 1, v22, a2, yBottoma);
      v12 = 0;
      yBottom = yTop;
      goto LABEL_25;
    case 5:
      SetRect(&rc, 0, 0, a2, 1);
      yBottoma = a3;
      v22 = yTop;
      if ( a4 )
        goto LABEL_22;
      goto LABEL_24;
    case 6:
      SetRect(&rc, 0, a3 - 1, a2, a3);
      if ( !a4 )
      {
        SetRect(&v31, 0, 0, 1, v26);
        yBottom = a3;
        v12 = v26;
        goto LABEL_23;
      }
      SetRect(&v31, a2 - 1, 0, a2, v26);
      yBottom = a3;
      v12 = v26;
LABEL_25:
      v13 = v28;
      goto LABEL_9;
  }
  if ( *((_DWORD *)this + 34) != 7 )
  {
    SetRectEmpty(&rc);
    SetRectEmpty(&v31);
    SetRectEmpty(&v30);
    v11 = -2147418113;
    goto LABEL_15;
  }
  SetRectEmpty(&rc);
  SetRectEmpty(&v31);
  v12 = a3 - 20;
  yBottom = a3;
  if ( !a4 )
  {
    v13 = a2 - 20;
LABEL_9:
    v14 = a2;
    goto LABEL_10;
  }
  v13 = 0;
  v14 = 20;
LABEL_10:
  SetRect(&v30, v13, v12, v14, yBottom);
  v11 = -2147024882;
  RectRgn = CreateRectRgn(rc.left, rc.top, rc.right, rc.bottom);
  if ( !RectRgn )
    goto LABEL_20;
  v16 = CreateRectRgn(v31.left, v31.top, v31.right, v31.bottom);
  v17 = v16;
  if ( !v16 )
    goto LABEL_20;
  if ( CombineRgn(RectRgn, RectRgn, v16, 2) )
  {
    v20 = CreateRectRgn(v30.left, v30.top, v30.right, v30.bottom);
    v21 = v20;
    if ( v20 )
    {
      v11 = CombineRgn(RectRgn, RectRgn, v20, 2) == 0 ? 0x8007000E : 0;
      DeleteObject(v21);
    }
  }
  DeleteObject(v17);
  if ( v11 >= 0 )
    *a5 = RectRgn;
  else
LABEL_20:
    DeleteObject(RectRgn);
LABEL_15:
  v18 = v29;
  if ( v29 )
  {
    v29 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800118dc  mov     [rsp-38h+arg_18], rbx
0x1800118e1  push    rbp
0x1800118e2  push    rsi
0x1800118e3  push    rdi
0x1800118e4  push    r12
0x1800118e6  push    r13
0x1800118e8  push    r14
0x1800118ea  push    r15
0x1800118ec  mov     rbp, rsp
0x1800118ef  sub     rsp, 80h
0x1800118f6  mov     rax, cs:__security_cookie
0x1800118fd  xor     rax, rsp
0x180011900  mov     [rbp+var_8], rax
0x180011904  mov     r15b, r9b
0x180011907  mov     r14d, r8d
0x18001190a  mov     esi, edx
0x18001190c  mov     r13, rcx
0x18001190f  mov     r12, [rbp+arg_20]
0x180011913  mov     qword ptr [r12], 0
0x18001191b  xorps   xmm0, xmm0
0x18001191e  movdqu  xmmword ptr [rbp+rc.left], xmm0
0x180011923  xorps   xmm1, xmm1
0x180011926  movdqu  xmmword ptr [rbp+var_28.left], xmm1
0x18001192b  movdqu  xmmword ptr [rbp+var_38.left], xmm0
0x180011930  mov     [rbp+var_40], 0
0x180011938  mov     rdi, [rcx+10h]
0x18001193c  mov     rax, [rdi]
0x18001193f  mov     rbx, [rax]
0x180011942  lea     rcx, [rbp+var_40]
0x180011946  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001194b  lea     r8, [rbp+var_40]
0x18001194f  lea     rdx, _GUID_bd9269d0_df79_47e0_8cd2_78762eb6d1bb
0x180011956  mov     rcx, rdi
0x180011959  mov     rax, rbx
0x18001195c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011961  mov     edi, eax
0x180011963  test    eax, eax
0x180011965  js      loc_180011A8D
0x18001196b  mov     [rbp+var_48], 0
0x180011972  mov     [rbp+yTop], 0
0x180011979  mov     [rbp+var_44], 0
0x180011980  mov     [rbp+var_4C], 0
0x180011987  mov     rcx, [rbp+var_40]
0x18001198b  mov     rax, [rcx]
0x18001198e  lea     rdx, [rbp+var_4C]
0x180011992  mov     qword ptr [rsp+80h+yBottom], rdx
0x180011997  lea     r9, [rbp+var_44]
0x18001199b  lea     r8, [rbp+yTop]
0x18001199f  lea     rdx, [rbp+var_48]
0x1800119a3  mov     rax, [rax+18h]
0x1800119a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119ac  mov     edi, eax
0x1800119ae  test    eax, eax
0x1800119b0  js      loc_180011A8D
0x1800119b6  mov     ecx, [r13+88h]
0x1800119bd  sub     ecx, 4
0x1800119c0  jz      loc_180011B26
0x1800119c6  sub     ecx, 1
0x1800119c9  jz      loc_180011C29
0x1800119cf  sub     ecx, 1
0x1800119d2  jz      loc_180011BCA
0x1800119d8  cmp     ecx, 1
0x1800119db  lea     rcx, [rbp+rc]; lprc
0x1800119df  jnz     loc_180011B9B
0x1800119e5  call    cs:__imp_SetRectEmpty
0x1800119eb  lea     rcx, [rbp+var_28]; lprc
0x1800119ef  call    cs:__imp_SetRectEmpty
0x1800119f5  lea     r8d, [r14-14h]; yTop
0x1800119f9  mov     [rsp+80h+yBottom], r14d; yBottom
0x1800119fe  lea     rcx, [rbp+var_38]; lprc
0x180011a02  test    r15b, r15b
0x180011a05  jnz     loc_180011BBF
0x180011a0b  lea     edx, [rsi-14h]; xLeft
0x180011a0e  mov     r9d, esi; xRight
0x180011a11  call    cs:__imp_SetRect
0x180011a17  mov     edi, 8007000Eh
0x180011a1c  mov     r9d, [rbp+rc.bottom]; y2
0x180011a20  mov     r8d, [rbp+rc.right]; x2
0x180011a24  mov     edx, [rbp+rc.top]; y1
0x180011a27  mov     ecx, [rbp+rc.left]; x1
0x180011a2a  call    cs:__imp_CreateRectRgn
0x180011a30  mov     rbx, rax
0x180011a33  test    rax, rax
0x180011a36  jz      loc_180011B18
0x180011a3c  mov     r9d, [rbp+var_28.bottom]; y2
0x180011a40  mov     r8d, [rbp+var_28.right]; x2
0x180011a44  mov     edx, [rbp+var_28.top]; y1
0x180011a47  mov     ecx, [rbp+var_28.left]; x1
0x180011a4a  call    cs:__imp_CreateRectRgn
0x180011a50  mov     rsi, rax
0x180011a53  test    rax, rax
0x180011a56  jz      loc_180011B18
0x180011a5c  mov     r15d, 2
0x180011a62  mov     r9d, r15d; iMode
0x180011a65  mov     r8, rax; hrgnSrc2
0x180011a68  mov     rdx, rbx; hrgnSrc1
0x180011a6b  mov     rcx, rbx; hrgnDst
0x180011a6e  call    cs:__imp_CombineRgn
0x180011a74  test    eax, eax
0x180011a76  jnz     short loc_180011AD4
0x180011a78  mov     rcx, rsi; ho
0x180011a7b  call    cs:__imp_DeleteObject
0x180011a81  test    edi, edi
0x180011a83  js      loc_180011B18
0x180011a89  mov     [r12], rbx
0x180011a8d  mov     rcx, [rbp+var_40]
0x180011a91  test    rcx, rcx
0x180011a94  jz      short loc_180011AAB
0x180011a96  mov     [rbp+var_40], 0
0x180011a9e  mov     rax, [rcx]
0x180011aa1  mov     rax, [rax+10h]
0x180011aa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011aaa  nop
0x180011aab  mov     eax, edi
0x180011aad  mov     rcx, [rbp+var_8]
0x180011ab1  xor     rcx, rsp; StackCookie
0x180011ab4  call    __security_check_cookie
0x180011ab9  mov     rbx, [rsp+80h+arg_18]
0x180011ac1  add     rsp, 80h
0x180011ac8  pop     r15
0x180011aca  pop     r14
0x180011acc  pop     r13
0x180011ace  pop     r12
0x180011ad0  pop     rdi
0x180011ad1  pop     rsi
0x180011ad2  pop     rbp
0x180011ad3  retn
0x180011ad4  mov     r9d, [rbp+var_38.bottom]; y2
0x180011ad8  mov     r8d, [rbp+var_38.right]; x2
0x180011adc  mov     edx, [rbp+var_38.top]; y1
0x180011adf  mov     ecx, [rbp+var_38.left]; x1
0x180011ae2  call    cs:__imp_CreateRectRgn
0x180011ae8  mov     r14, rax
0x180011aeb  test    rax, rax
0x180011aee  jz      short loc_180011A78
0x180011af0  mov     r9d, r15d; iMode
0x180011af3  mov     r8, rax; hrgnSrc2
0x180011af6  mov     rdx, rbx; hrgnSrc1
0x180011af9  mov     rcx, rbx; hrgnDst
0x180011afc  call    cs:__imp_CombineRgn
0x180011b02  neg     eax
0x180011b04  sbb     ecx, ecx
0x180011b06  not     ecx
0x180011b08  and     edi, ecx
0x180011b0a  mov     rcx, r14; ho
0x180011b0d  call    cs:__imp_DeleteObject
0x180011b13  jmp     loc_180011A78
0x180011b18  mov     rcx, rbx; ho
0x180011b1b  call    cs:__imp_DeleteObject
0x180011b21  jmp     loc_180011A8D
0x180011b26  mov     [rsp+80h+yBottom], 1; yBottom
0x180011b2e  mov     r9d, esi; xRight
0x180011b31  xor     r8d, r8d; yTop
0x180011b34  xor     edx, edx; xLeft
0x180011b36  lea     rcx, [rbp+rc]; lprc
0x180011b3a  call    cs:__imp_SetRect
0x180011b40  mov     [rsp+80h+yBottom], r14d; yBottom
0x180011b45  mov     r8d, [rbp+yTop]; yTop
0x180011b49  lea     rcx, [rbp+var_28]; lprc
0x180011b4d  test    r15b, r15b
0x180011b50  jnz     short loc_180011B79
0x180011b52  mov     r9d, 1; xRight
0x180011b58  xor     edx, edx; xLeft
0x180011b5a  call    cs:__imp_SetRect
0x180011b60  mov     eax, [rbp+yTop]
0x180011b63  mov     [rsp+80h+yBottom], eax
0x180011b67  xor     r8d, r8d
0x180011b6a  mov     r9d, [rbp+var_48]
0x180011b6e  xor     edx, edx
0x180011b70  lea     rcx, [rbp+var_38]
0x180011b74  jmp     loc_180011A11
0x180011b79  mov     r9d, esi; xRight
0x180011b7c  lea     edx, [rsi-1]; xLeft
0x180011b7f  call    cs:__imp_SetRect
0x180011b85  mov     eax, [rbp+yTop]
0x180011b88  xor     r8d, r8d
0x180011b8b  mov     [rsp+80h+yBottom], eax
0x180011b8f  mov     edx, [rbp+var_44]
0x180011b92  lea     rcx, [rbp+var_38]
0x180011b96  jmp     loc_180011A0E
0x180011b9b  call    cs:__imp_SetRectEmpty
0x180011ba1  lea     rcx, [rbp+var_28]; lprc
0x180011ba5  call    cs:__imp_SetRectEmpty
0x180011bab  lea     rcx, [rbp+var_38]; lprc
0x180011baf  call    cs:__imp_SetRectEmpty
0x180011bb5  mov     edi, 8000FFFFh
0x180011bba  jmp     loc_180011A8D
0x180011bbf  xor     edx, edx
0x180011bc1  lea     r9d, [rdx+14h]
0x180011bc5  jmp     loc_180011A11
0x180011bca  lea     r8d, [r14-1]; yTop
0x180011bce  mov     [rsp+80h+yBottom], r14d; yBottom
0x180011bd3  mov     r9d, esi; xRight
0x180011bd6  xor     edx, edx; xLeft
0x180011bd8  lea     rcx, [rbp+rc]; lprc
0x180011bdc  call    cs:__imp_SetRect
0x180011be2  mov     eax, [rbp+var_4C]
0x180011be5  xor     r8d, r8d; yTop
0x180011be8  lea     rcx, [rbp+var_28]; lprc
0x180011bec  mov     [rsp+80h+yBottom], eax; yBottom
0x180011bf0  test    r15b, r15b
0x180011bf3  jnz     short loc_180011C0F
0x180011bf5  lea     r9d, [r8+1]; xRight
0x180011bf9  xor     edx, edx; xLeft
0x180011bfb  call    cs:__imp_SetRect
0x180011c01  mov     [rsp+80h+yBottom], r14d
0x180011c06  mov     r8d, [rbp+var_4C]
0x180011c0a  jmp     loc_180011B6A
0x180011c0f  lea     edx, [rsi-1]; xLeft
0x180011c12  mov     r9d, esi; xRight
0x180011c15  call    cs:__imp_SetRect
0x180011c1b  mov     [rsp+80h+yBottom], r14d
0x180011c20  mov     r8d, [rbp+var_4C]
0x180011c24  jmp     loc_180011B8F
0x180011c29  mov     [rsp+80h+yBottom], 1; yBottom
0x180011c31  mov     r9d, esi; xRight
0x180011c34  xor     r8d, r8d; yTop
0x180011c37  xor     edx, edx; xLeft
0x180011c39  lea     rcx, [rbp+rc]; lprc
0x180011c3d  call    cs:__imp_SetRect
0x180011c43  mov     [rsp+80h+yBottom], r14d
0x180011c48  mov     r8d, [rbp+yTop]
0x180011c4c  lea     rcx, [rbp+var_28]
0x180011c50  test    r15b, r15b
0x180011c53  jz      loc_180011B79
0x180011c59  jmp     loc_180011B52
```
