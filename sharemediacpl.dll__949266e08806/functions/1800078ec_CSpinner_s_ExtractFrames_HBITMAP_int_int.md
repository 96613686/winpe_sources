# CSpinner::s_ExtractFrames(HBITMAP__ *,int,int *)

- ea: `0x1800078ec`
- end: `0x180007b37`
- name: `?s_ExtractFrames@CSpinner@@AEAAPEAPEAVValue@DirectUI@@PEAUHBITMAP__@@HPEAH@Z`
- size: `587`
- prototype: `struct DirectUI::Value **(CSpinner *__hidden this, HBITMAP, int, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007778`

## callees

- `0x18000291e`
- `0x1800078ec`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x1800079ba`
- `ole32!CoTaskMemAlloc` at `0x1800079ba`
- `ole32!CoTaskMemFree` at `0x180007b25`
- `ole32!CoTaskMemFree` at `0x180007b25`
- `GDI32!DeleteObject` at `0x180007afa`
- `GDI32!DeleteObject` at `0x180007afa`
- `GDI32!GetObjectW` at `0x180007932`
- `GDI32!GetObjectW` at `0x180007932`
- `GDI32!CreateCompatibleDC` at `0x18000795d`
- `GDI32!CreateCompatibleDC` at `0x180007972`
- `GDI32!CreateCompatibleDC` at `0x18000795d`
- `GDI32!CreateCompatibleDC` at `0x180007972`
- `GDI32!CreateCompatibleBitmap` at `0x1800079f3`
- `GDI32!CreateCompatibleBitmap` at `0x1800079f3`
- `GDI32!StretchBlt` at `0x180007a57`
- `GDI32!StretchBlt` at `0x180007a57`
- `GDI32!DeleteDC` at `0x180007aca`
- `GDI32!DeleteDC` at `0x180007ad3`
- `GDI32!DeleteDC` at `0x180007aca`
- `GDI32!DeleteDC` at `0x180007ad3`
- `GDI32!SelectObject` at `0x18000798a`
- `GDI32!SelectObject` at `0x180007a0b`
- `GDI32!SelectObject` at `0x180007a65`
- `GDI32!SelectObject` at `0x180007ac1`
- `GDI32!SelectObject` at `0x18000798a`
- `GDI32!SelectObject` at `0x180007a0b`
- `GDI32!SelectObject` at `0x180007a65`
- `GDI32!SelectObject` at `0x180007ac1`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180007b0e`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180007b0e`
- `DUI70!?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHBITMAP__@@EI_N11@Z` at `0x180007a8b`
- `DUI70!?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHBITMAP__@@EI_N11@Z` at `0x180007a8b`

## pseudocode

```c
struct DirectUI::Value **__fastcall CSpinner::s_ExtractFrames(CSpinner *this, HBITMAP a2, int a3, int *a4)
{
  _QWORD *v5; // rdi
  HDC CompatibleDC; // rax
  HDC hdcSrc; // rsi
  HDC v8; // r12
  void *v9; // r13
  __int64 v10; // rbp
  _QWORD *v11; // rax
  int v12; // r14d
  HBITMAP CompatibleBitmap; // rax
  HBITMAP v14; // r15
  HGDIOBJ v15; // r13
  BOOL v16; // ebx
  struct DirectUI::Value *Graphic; // rax
  int v19; // ebx
  DirectUI::Value *v20; // rcx
  _DWORD wSrc[22]; // [rsp+60h] [rbp-58h] BYREF
  HGDIOBJ v22; // [rsp+C0h] [rbp+8h]

  *a4 = 0;
  v5 = 0;
  memset(wSrc, 0, 32);
  GetObjectW(a2, 32, wSrc);
  if ( wSrc[2] > 0 && wSrc[1] >= wSrc[2] && !(wSrc[1] % wSrc[2]) )
  {
    CompatibleDC = CreateCompatibleDC(0);
    hdcSrc = CompatibleDC;
    if ( CompatibleDC )
    {
      v8 = CreateCompatibleDC(CompatibleDC);
      if ( v8 )
      {
        v22 = SelectObject(hdcSrc, a2);
        v9 = v22;
        if ( v22 )
        {
          v10 = wSrc[1] / wSrc[2];
          v11 = CoTaskMemAlloc(8 * v10);
          v5 = v11;
          if ( v11 )
          {
            memset_0(v11, 0, 8 * v10);
            v12 = 0;
            if ( (int)v10 <= 0 )
            {
LABEL_15:
              *a4 = v10;
            }
            else
            {
              while ( 1 )
              {
                CompatibleBitmap = CreateCompatibleBitmap(hdcSrc, a3, a3);
                v14 = CompatibleBitmap;
                if ( !CompatibleBitmap )
                  break;
                v15 = SelectObject(v8, CompatibleBitmap);
                if ( !v15
                  || (v16 = StretchBlt(v8, 0, 0, a3, a3, hdcSrc, wSrc[2] * v12, 0, wSrc[2], wSrc[2], 0xCC0020u),
                      SelectObject(v8, v15),
                      !v16)
                  || (Graphic = DirectUI::Value::CreateGraphic(v14, 2u, 0xFFFFFFu, 0, 0, 0), (v5[v12] = Graphic) == 0) )
                {
                  DeleteObject(v14);
                  break;
                }
                if ( ++v12 >= (int)v10 )
                {
                  v9 = v22;
                  goto LABEL_15;
                }
              }
              v19 = 0;
              do
              {
                v20 = (DirectUI::Value *)v5[v19];
                if ( v20 )
                {
                  DirectUI::Value::Release(v20);
                  v5[v19] = 0;
                }
                ++v19;
              }
              while ( v19 < (int)v10 );
              CoTaskMemFree(v5);
              v9 = v22;
              v5 = 0;
            }
          }
          SelectObject(hdcSrc, v9);
        }
        DeleteDC(v8);
      }
      DeleteDC(hdcSrc);
    }
  }
  return (struct DirectUI::Value **)v5;
}

```

## disassembly

```asm
0x1800078ec  mov     rax, rsp
0x1800078ef  mov     [rax+10h], rbx
0x1800078f3  mov     [rax+20h], r9
0x1800078f7  mov     [rax+18h], r8d
0x1800078fb  mov     [rax+8], rcx
0x1800078ff  push    rbp
0x180007900  push    rsi
0x180007901  push    rdi
0x180007902  push    r12
0x180007904  push    r13
0x180007906  push    r14
0x180007908  push    r15
0x18000790a  sub     rsp, 80h
0x180007911  mov     rbx, rdx
0x180007914  mov     dword ptr [r9], 0
0x18000791b  xorps   xmm0, xmm0
0x18000791e  lea     r8, [rax-58h]; pv
0x180007922  xor     edi, edi
0x180007924  mov     rcx, rbx; h
0x180007927  movups  xmmword ptr [rax-58h], xmm0
0x18000792b  movups  xmmword ptr [rax-48h], xmm0
0x18000792f  lea     edx, [rdi+20h]; c
0x180007932  call    cs:__imp_GetObjectW
0x180007938  mov     ecx, [rsp+0B8h+var_50]
0x18000793c  test    ecx, ecx
0x18000793e  jle     loc_180007AD9
0x180007944  mov     eax, [rsp+0B8h+var_54]
0x180007948  cmp     eax, ecx
0x18000794a  jl      loc_180007AD9
0x180007950  cdq
0x180007951  idiv    ecx
0x180007953  test    edx, edx
0x180007955  jnz     loc_180007AD9
0x18000795b  xor     ecx, ecx; hdc
0x18000795d  call    cs:__imp_CreateCompatibleDC
0x180007963  mov     rsi, rax
0x180007966  test    rax, rax
0x180007969  jz      loc_180007AD9
0x18000796f  mov     rcx, rax; hdc
0x180007972  call    cs:__imp_CreateCompatibleDC
0x180007978  mov     r12, rax
0x18000797b  test    rax, rax
0x18000797e  jz      loc_180007AD0
0x180007984  mov     rdx, rbx; h
0x180007987  mov     rcx, rsi; hdc
0x18000798a  call    cs:__imp_SelectObject
0x180007990  mov     [rsp+0B8h+arg_0], rax
0x180007998  mov     r13, rax
0x18000799b  test    rax, rax
0x18000799e  jz      loc_180007AC7
0x1800079a4  mov     eax, [rsp+0B8h+var_54]
0x1800079a8  cdq
0x1800079a9  idiv    [rsp+0B8h+var_50]
0x1800079ad  movsxd  rbp, eax
0x1800079b0  mov     rbx, rbp
0x1800079b3  shl     rbx, 3
0x1800079b7  mov     rcx, rbx; cb
0x1800079ba  call    cs:__imp_CoTaskMemAlloc
0x1800079c0  mov     rdi, rax
0x1800079c3  test    rax, rax
0x1800079c6  jz      loc_180007ABB
0x1800079cc  mov     r8, rbx; Size
0x1800079cf  xor     edx, edx; Val
0x1800079d1  mov     rcx, rax; void *
0x1800079d4  call    memset_0
0x1800079d9  xor     r14d, r14d
0x1800079dc  test    ebp, ebp
0x1800079de  jle     loc_180007AB1
0x1800079e4  mov     ebx, [rsp+0B8h+cy]
0x1800079eb  mov     rcx, rsi; hdc
0x1800079ee  mov     r8d, ebx; cy
0x1800079f1  mov     edx, ebx; cx
0x1800079f3  call    cs:__imp_CreateCompatibleBitmap
0x1800079f9  mov     r15, rax
0x1800079fc  test    rax, rax
0x1800079ff  jz      loc_180007B00
0x180007a05  mov     rdx, rax; h
0x180007a08  mov     rcx, r12; hdc
0x180007a0b  call    cs:__imp_SelectObject
0x180007a11  mov     r13, rax
0x180007a14  test    rax, rax
0x180007a17  jz      loc_180007AF7
0x180007a1d  mov     ecx, [rsp+0B8h+var_50]
0x180007a21  mov     edx, r14d
0x180007a24  mov     [rsp+0B8h+rop], 0CC0020h; rop
0x180007a2c  mov     r9d, ebx; wDest
0x180007a2f  mov     [rsp+0B8h+hSrc], ecx; hSrc
0x180007a33  xor     r8d, r8d; yDest
0x180007a36  mov     [rsp+0B8h+wSrc], ecx; wSrc
0x180007a3a  imul    edx, ecx
0x180007a3d  mov     rcx, r12; hdcDest
0x180007a40  mov     [rsp+0B8h+ySrc], 0; ySrc
0x180007a48  mov     [rsp+0B8h+xSrc], edx; xSrc
0x180007a4c  xor     edx, edx; xDest
0x180007a4e  mov     [rsp+0B8h+hdcSrc], rsi; hdcSrc
0x180007a53  mov     [rsp+0B8h+hDest], ebx; hDest
0x180007a57  call    cs:__imp_StretchBlt
0x180007a5d  mov     rdx, r13; h
0x180007a60  mov     rcx, r12; hdc
0x180007a63  mov     ebx, eax
0x180007a65  call    cs:__imp_SelectObject
0x180007a6b  test    ebx, ebx
0x180007a6d  jz      loc_180007AF7
0x180007a73  mov     byte ptr [rsp+0B8h+hdcSrc], 0
0x180007a78  xor     r9d, r9d
0x180007a7b  mov     r8d, 0FFFFFFh
0x180007a81  mov     byte ptr [rsp+0B8h+hDest], 0
0x180007a86  mov     dl, 2
0x180007a88  mov     rcx, r15
0x180007a8b  call    cs:__imp_?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHBITMAP__@@EI_N11@Z; DirectUI::Value::CreateGraphic(HBITMAP__ *,uchar,uint,bool,bool,bool)
0x180007a91  movsxd  rcx, r14d
0x180007a94  mov     [rdi+rcx*8], rax
0x180007a98  test    rax, rax
0x180007a9b  jz      short loc_180007AF7
0x180007a9d  inc     r14d
0x180007aa0  cmp     r14d, ebp
0x180007aa3  jl      loc_1800079E4
0x180007aa9  mov     r13, [rsp+0B8h+arg_0]
0x180007ab1  mov     rax, [rsp+0B8h+arg_18]
0x180007ab9  mov     [rax], ebp
0x180007abb  mov     rdx, r13; h
0x180007abe  mov     rcx, rsi; hdc
0x180007ac1  call    cs:__imp_SelectObject
0x180007ac7  mov     rcx, r12; hdc
0x180007aca  call    cs:__imp_DeleteDC
0x180007ad0  mov     rcx, rsi; hdc
0x180007ad3  call    cs:__imp_DeleteDC
0x180007ad9  mov     rbx, [rsp+0B8h+arg_8]
0x180007ae1  mov     rax, rdi
0x180007ae4  add     rsp, 80h
0x180007aeb  pop     r15
0x180007aed  pop     r14
0x180007aef  pop     r13
0x180007af1  pop     r12
0x180007af3  pop     rdi
0x180007af4  pop     rsi
0x180007af5  pop     rbp
0x180007af6  retn
0x180007af7  mov     rcx, r15; ho
0x180007afa  call    cs:__imp_DeleteObject
0x180007b00  xor     ebx, ebx
0x180007b02  movsxd  r14, ebx
0x180007b05  mov     rcx, [rdi+r14*8]
0x180007b09  test    rcx, rcx
0x180007b0c  jz      short loc_180007B1C
0x180007b0e  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180007b14  mov     qword ptr [rdi+r14*8], 0
0x180007b1c  inc     ebx
0x180007b1e  cmp     ebx, ebp
0x180007b20  jl      short loc_180007B02
0x180007b22  mov     rcx, rdi; pv
0x180007b25  call    cs:__imp_CoTaskMemFree
0x180007b2b  mov     r13, [rsp+0B8h+arg_0]
0x180007b33  xor     edi, edi
0x180007b35  jmp     short loc_180007ABB
```
