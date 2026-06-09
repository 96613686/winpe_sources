# ComboBoxEx::LoadImageList(ulong,int)

- ea: `0x180010740`
- end: `0x18001088a`
- name: `?LoadImageList@ComboBoxEx@@QEAAJKH@Z`
- size: `330`
- prototype: `int(ComboBoxEx *__hidden this, unsigned int, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800415d0`

## callees

- `0x180010740`
- `0x18004ff74`
- `0x18005521c`
- `0x18005528c`
- `0x1800552f8`
- `0x180057010`

## import_xrefs

- `GDI32!GetObjectW` at `0x1800107a1`
- `GDI32!GetObjectW` at `0x1800107a1`
- `GDI32!DeleteObject` at `0x180010871`
- `GDI32!DeleteObject` at `0x180010871`
- `USER32!SendMessageW` at `0x18001082f`
- `USER32!SendMessageW` at `0x18001082f`
- `DUI70!?SyncRect@HWNDHost@DirectUI@@IEAAXI_N@Z` at `0x180010850`
- `DUI70!?SyncRect@HWNDHost@DirectUI@@IEAAXI_N@Z` at `0x180010850`

## pseudocode

```c
__int64 __fastcall ComboBoxEx::LoadImageList(struct _IMAGELIST **this, unsigned __int16 a2, int a3)
{
  int ImageScaled; // ebx
  struct _IMAGELIST *v6; // rax
  LPARAM v7; // rdi
  HWND v8; // r14
  struct _IMAGELIST *v9; // rcx
  struct _IMAGELIST *v10; // rcx
  LRESULT v11; // rax
  struct _IMAGELIST *v12; // r14
  _OWORD pv[4]; // [rsp+30h] [rbp-48h] BYREF
  HANDLE h; // [rsp+98h] [rbp+20h] BYREF

  h = 0;
  ImageScaled = LoadImageScaled(g_hinst, (unsigned __int16 *)a2, (HBITMAP *)&h);
  if ( ImageScaled >= 0 )
  {
    memset(pv, 0, 32);
    GetObjectW(h, 32, pv);
    v6 = ImageList_Create(a3, SDWORD2(pv[0]), 0x20u, 5, 1);
    v7 = (LPARAM)v6;
    if ( v6 )
    {
      ImageList_Add(v6, (HBITMAP)h, 0);
      v8 = (HWND)(*((__int64 (__fastcall **)(struct _IMAGELIST **))*this + 45))(this);
      if ( v8 )
      {
        v10 = this[40];
        if ( v10 )
          ImageList_Destroy(v10);
        v11 = SendMessageW(v8, 0x402u, 0, v7);
        this[40] = (struct _IMAGELIST *)v7;
        v12 = (struct _IMAGELIST *)v11;
        DirectUI::HWNDHost::SyncRect((DirectUI::HWNDHost *)this, 3u, 1);
        if ( !v12 )
          goto LABEL_11;
        v9 = v12;
      }
      else
      {
        ImageScaled = -2147467259;
        v9 = (struct _IMAGELIST *)v7;
      }
      ImageList_Destroy(v9);
    }
    else
    {
      ImageScaled = -2147467259;
    }
LABEL_11:
    DeleteObject(h);
  }
  return (unsigned int)ImageScaled;
}

```

## disassembly

```asm
0x180010740  mov     r11, rsp
0x180010743  push    rbx
0x180010744  push    rsi
0x180010745  push    rdi
0x180010746  push    r14
0x180010748  sub     rsp, 58h
0x18001074c  mov     rsi, rcx
0x18001074f  movzx   edx, dx; unsigned __int16 *
0x180010752  mov     rcx, cs:g_hinst; HINSTANCE
0x180010759  lea     rax, [r11+20h]
0x18001075d  xor     r9d, r9d
0x180010760  mov     [r11-58h], rax
0x180010764  mov     edi, r8d
0x180010767  mov     qword ptr [r11+20h], 0
0x18001076f  call    LoadImageScaled
0x180010774  mov     ebx, eax
0x180010776  test    eax, eax
0x180010778  js      loc_18001087D
0x18001077e  mov     rcx, [rsp+78h+h]; h
0x180010786  lea     r8, [rsp+78h+pv]; pv
0x18001078b  xorps   xmm0, xmm0
0x18001078e  mov     r14d, 20h ; ' '
0x180010794  mov     edx, r14d; c
0x180010797  movups  [rsp+78h+pv], xmm0
0x18001079c  movups  [rsp+78h+var_38], xmm0
0x1800107a1  call    cs:__imp_GetObjectW
0x1800107a8  nop     dword ptr [rax+rax+00h]
0x1800107ad  mov     edx, dword ptr [rsp+78h+pv+8]; cy
0x1800107b1  lea     r9d, [r14-1Bh]; cInitial
0x1800107b5  mov     r8d, r14d; flags
0x1800107b8  mov     [rsp+78h+cGrow], 1; cGrow
0x1800107c0  mov     ecx, edi; cx
0x1800107c2  call    ImageList_Create
0x1800107c7  mov     rdi, rax
0x1800107ca  test    rax, rax
0x1800107cd  jnz     short loc_1800107D9
0x1800107cf  mov     ebx, 80004005h
0x1800107d4  jmp     loc_180010869
0x1800107d9  mov     rdx, [rsp+78h+h]; hbmImage
0x1800107e1  xor     r8d, r8d; hbmMask
0x1800107e4  mov     rcx, rdi; himl
0x1800107e7  call    ImageList_Add
0x1800107ec  mov     rax, [rsi]
0x1800107ef  mov     rcx, rsi
0x1800107f2  mov     rax, [rax+168h]
0x1800107f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107fe  mov     r14, rax
0x180010801  test    rax, rax
0x180010804  jnz     short loc_180010810
0x180010806  mov     ebx, 80004005h
0x18001080b  mov     rcx, rdi
0x18001080e  jmp     short loc_180010864
0x180010810  mov     rcx, [rsi+140h]; himl
0x180010817  test    rcx, rcx
0x18001081a  jz      short loc_180010821
0x18001081c  call    ImageList_Destroy
0x180010821  mov     r9, rdi; lParam
0x180010824  xor     r8d, r8d; wParam
0x180010827  mov     edx, 402h; Msg
0x18001082c  mov     rcx, r14; hWnd
0x18001082f  call    cs:__imp_SendMessageW
0x180010836  nop     dword ptr [rax+rax+00h]
0x18001083b  mov     r8b, 1
0x18001083e  mov     [rsi+140h], rdi
0x180010845  mov     edx, 3
0x18001084a  mov     rcx, rsi
0x18001084d  mov     r14, rax
0x180010850  call    cs:__imp_?SyncRect@HWNDHost@DirectUI@@IEAAXI_N@Z; DirectUI::HWNDHost::SyncRect(uint,bool)
0x180010857  nop     dword ptr [rax+rax+00h]
0x18001085c  test    r14, r14
0x18001085f  jz      short loc_180010869
0x180010861  mov     rcx, r14; himl
0x180010864  call    ImageList_Destroy
0x180010869  mov     rcx, [rsp+78h+h]; ho
0x180010871  call    cs:__imp_DeleteObject
0x180010878  nop     dword ptr [rax+rax+00h]
0x18001087d  mov     eax, ebx
0x18001087f  add     rsp, 58h
0x180010883  pop     r14
0x180010885  pop     rdi
0x180010886  pop     rsi
0x180010887  pop     rbx
0x180010888  retn
```
