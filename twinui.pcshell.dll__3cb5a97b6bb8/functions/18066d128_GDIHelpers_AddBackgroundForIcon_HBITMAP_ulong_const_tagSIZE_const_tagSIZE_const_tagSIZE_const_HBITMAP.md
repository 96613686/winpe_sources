# GDIHelpers::AddBackgroundForIcon(HBITMAP__ *,ulong const &,tagSIZE const &,tagSIZE const &,tagSIZE const &,HBITMAP__ * *)

- ea: `0x18066d128`
- end: `0x18066d434`
- name: `?AddBackgroundForIcon@GDIHelpers@@YAJPEAUHBITMAP__@@AEBKAEBUtagSIZE@@22PEAPEAU2@@Z`
- size: `780`
- prototype: `__int64 __usercall@<rax>(HANDLE h@<rcx>, HBITMAP@<rdx>, const unsigned int *@<r8>, const struct tagSIZE *@<r9>, const struct tagSIZE *, const struct tagSIZE *, HBITMAP *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800c8668`

## callees

- `0x1800237c8`
- `0x1801d4c40`
- `0x1802bbaf8`
- `0x180356360`
- `0x18056028c`
- `0x18066d128`

## import_xrefs

- `GDI32!CreateDIBSection` at `0x18066d299`
- `GDI32!CreateDIBSection` at `0x18066d299`
- `GDI32!GetObjectW` at `0x18066d205`
- `GDI32!GetObjectW` at `0x18066d205`
- `GDI32!CreateCompatibleDC` at `0x18066d16e`
- `GDI32!CreateCompatibleDC` at `0x18066d1a7`
- `GDI32!CreateCompatibleDC` at `0x18066d16e`
- `GDI32!CreateCompatibleDC` at `0x18066d1a7`
- `GDI32!SelectObject` at `0x18066d1e5`
- `GDI32!SelectObject` at `0x18066d22c`
- `GDI32!SelectObject` at `0x18066d2db`
- `GDI32!SelectObject` at `0x18066d301`
- `GDI32!SelectObject` at `0x18066d3df`
- `GDI32!SelectObject` at `0x18066d3f7`
- `GDI32!SelectObject` at `0x18066d1e5`
- `GDI32!SelectObject` at `0x18066d22c`
- `GDI32!SelectObject` at `0x18066d2db`
- `GDI32!SelectObject` at `0x18066d301`
- `GDI32!SelectObject` at `0x18066d3df`
- `GDI32!SelectObject` at `0x18066d3f7`
- `GDI32!DeleteDC` at `0x18066d1d6`
- `GDI32!DeleteDC` at `0x18066d236`
- `GDI32!DeleteDC` at `0x18066d240`
- `GDI32!DeleteDC` at `0x18066d2e5`
- `GDI32!DeleteDC` at `0x18066d2ef`
- `GDI32!DeleteDC` at `0x18066d401`
- `GDI32!DeleteDC` at `0x18066d40b`
- `GDI32!DeleteDC` at `0x18066d1d6`
- `GDI32!DeleteDC` at `0x18066d236`
- `GDI32!DeleteDC` at `0x18066d240`
- `GDI32!DeleteDC` at `0x18066d2e5`
- `GDI32!DeleteDC` at `0x18066d2ef`
- `GDI32!DeleteDC` at `0x18066d401`
- `GDI32!DeleteDC` at `0x18066d40b`
- `GDI32!GdiAlphaBlend` at `0x18066d3c7`
- `GDI32!GdiAlphaBlend` at `0x18066d3c7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GDIHelpers::AddBackgroundForIcon(
        HANDLE h,
        HBITMAP a2,
        LONG *a3,
        const struct tagSIZE *a4,
        const struct tagSIZE *a5,
        struct tagSIZE *a6)
{
  HDC CompatibleDC; // rax
  HDC v10; // rdi
  unsigned int LastError; // esi
  HDC v13; // rax
  HDC v14; // rbx
  HGDIOBJ v15; // r15
  const char *v16; // r9
  HBITMAP v17; // rax
  HBITMAP v18; // rsi
  HGDIOBJ v19; // r14
  const struct tagRECT *v20; // r8
  int cx; // r9d
  int cy; // r10d
  int hSection; // [rsp+20h] [rbp-C9h]
  unsigned int hSectiona; // [rsp+20h] [rbp-C9h]
  bool offset; // [rsp+28h] [rbp-C1h]
  BLENDFUNCTION v26[2]; // [rsp+60h] [rbp-89h] BYREF
  void *ppvBits; // [rsp+68h] [rbp-81h] BYREF
  HBITMAP v28; // [rsp+70h] [rbp-79h]
  const struct tagSIZE *v29; // [rsp+78h] [rbp-71h]
  struct tagSIZE *v30; // [rsp+80h] [rbp-69h]
  _OWORD pv[2]; // [rsp+88h] [rbp-61h] BYREF
  struct HDC__ v32; // [rsp+A8h] [rbp-41h] BYREF
  int v33; // [rsp+ACh] [rbp-3Dh]
  int v34; // [rsp+B0h] [rbp-39h]
  int v35; // [rsp+B4h] [rbp-35h]
  BITMAPINFO pbmi; // [rsp+B8h] [rbp-31h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+4Fh]

  v28 = a2;
  v29 = a5;
  v30 = a6;
  CompatibleDC = CreateCompatibleDC(0);
  v10 = CompatibleDC;
  if ( !CompatibleDC )
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x178,
      (unsigned int)"shell\\inc\\GDIHelpers.h",
      (const char *)0x8007000ELL,
      hSection);
    return LastError;
  }
  v13 = CreateCompatibleDC(CompatibleDC);
  v14 = v13;
  if ( !v13 )
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x17B,
      (unsigned int)"shell\\inc\\GDIHelpers.h",
      (const char *)0x8007000ELL,
      hSection);
    DeleteDC(v10);
    return LastError;
  }
  v15 = SelectObject(v13, h);
  memset(pv, 0, sizeof(pv));
  if ( !GetObjectW(h, 32, pv) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x181,
                  (unsigned int)"shell\\inc\\GDIHelpers.h",
                  v16);
    SelectObject(v14, v15);
    DeleteDC(v14);
    DeleteDC(v10);
    return LastError;
  }
  pbmi.bmiHeader.biSize = 44;
  memset(&pbmi.bmiHeader.biWidth, 0, 40);
  pbmi.bmiHeader.biWidth = *a3;
  pbmi.bmiHeader.biHeight = a3[1];
  *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
  ppvBits = 0;
  v17 = CreateDIBSection(v10, &pbmi, 0, &ppvBits, 0, 0);
  v18 = v17;
  *(_QWORD *)&v26[0].BlendOp = v17;
  if ( !v17 )
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18D,
      (unsigned int)"shell\\inc\\GDIHelpers.h",
      (const char *)0x8007000ELL,
      hSectiona);
    CTSmartObj<HFONT__ *,CAutoHandle_Policy<HFONT__ *>>::Release(v26);
    SelectObject(v14, v15);
    DeleteDC(v14);
    DeleteDC(v10);
    return LastError;
  }
  v19 = SelectObject(v10, v17);
  v32.unused = (*a3 - a4->cx) / 2;
  v33 = (a3[1] - a4->cy) / 2;
  v34 = a4->cx + v32.unused;
  v35 = a4->cy + v33;
  GDIHelpers::FillRectARGB(v10, &v32, v20, *(_DWORD *)v28, hSectiona, offset);
  cx = DWORD1(pv[0]);
  if ( v29->cx < SDWORD1(pv[0]) )
    cx = v29->cx;
  cy = DWORD2(pv[0]);
  if ( v29->cy < SDWORD2(pv[0]) )
    cy = v29->cy;
  v26[0] = (BLENDFUNCTION)33488896;
  GdiAlphaBlend(
    v10,
    (*a3 - cx) / 2,
    (a3[1] - cy) / 2,
    cx,
    cy,
    v14,
    0,
    0,
    SDWORD1(pv[0]),
    SDWORD2(pv[0]),
    (BLENDFUNCTION)33488896);
  *(_QWORD *)&v26[0].BlendOp = 0;
  *v30 = (struct tagSIZE)v18;
  SelectObject(v10, v19);
  CTSmartObj<HFONT__ *,CAutoHandle_Policy<HFONT__ *>>::Release(v26);
  SelectObject(v14, v15);
  DeleteDC(v14);
  DeleteDC(v10);
  return 0;
}

```

## disassembly

```asm
0x18066d128  push    rbp
0x18066d12a  push    rbx
0x18066d12b  push    rsi
0x18066d12c  push    rdi
0x18066d12d  push    r12
0x18066d12f  push    r13
0x18066d131  push    r14
0x18066d133  push    r15
0x18066d135  lea     rbp, [rsp-0Fh]
0x18066d13a  sub     rsp, 0F8h
0x18066d141  mov     rax, cs:__security_cookie
0x18066d148  xor     rax, rsp
0x18066d14b  mov     [rbp+47h+var_48], rax
0x18066d14f  mov     r13, r9
0x18066d152  mov     r12, r8
0x18066d155  mov     [rbp+47h+var_C0], rdx
0x18066d159  mov     rsi, rcx
0x18066d15c  mov     rax, [rbp+47h+arg_20]
0x18066d160  mov     [rbp+47h+var_B8], rax
0x18066d164  mov     rax, [rbp+47h+arg_28]
0x18066d168  mov     [rbp+47h+var_B0], rax
0x18066d16c  xor     ecx, ecx; hdc
0x18066d16e  call    cs:__imp_CreateCompatibleDC
0x18066d174  mov     rdi, rax
0x18066d177  xor     r14d, r14d
0x18066d17a  test    rax, rax
0x18066d17d  jnz     short loc_18066D1A4
0x18066d17f  mov     rcx, [rbp+4Fh]; this
0x18066d183  mov     esi, 8007000Eh
0x18066d188  mov     r9d, esi; char *
0x18066d18b  lea     r8, aShellIncGdihel; "shell\\inc\\GDIHelpers.h"
0x18066d192  mov     edx, 178h; void *
0x18066d197  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18066d19c  nop
0x18066d19d  mov     eax, esi
0x18066d19f  jmp     loc_18066D414
0x18066d1a4  mov     rcx, rdi; hdc
0x18066d1a7  call    cs:__imp_CreateCompatibleDC
0x18066d1ad  mov     rbx, rax
0x18066d1b0  test    rax, rax
0x18066d1b3  jnz     short loc_18066D1DF
0x18066d1b5  mov     rcx, [rbp+4Fh]; this
0x18066d1b9  mov     esi, 8007000Eh
0x18066d1be  mov     r9d, esi; char *
0x18066d1c1  lea     r8, aShellIncGdihel; "shell\\inc\\GDIHelpers.h"
0x18066d1c8  mov     edx, 17Bh; void *
0x18066d1cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18066d1d2  nop
0x18066d1d3  mov     rcx, rdi; hdc
0x18066d1d6  call    cs:__imp_DeleteDC
0x18066d1dc  nop
0x18066d1dd  jmp     short loc_18066D19D
0x18066d1df  mov     rdx, rsi; h
0x18066d1e2  mov     rcx, rbx; hdc
0x18066d1e5  call    cs:__imp_SelectObject
0x18066d1eb  mov     r15, rax
0x18066d1ee  xorps   xmm0, xmm0
0x18066d1f1  movups  [rbp+47h+pv], xmm0
0x18066d1f5  movups  [rbp+47h+var_98], xmm0
0x18066d1f9  lea     r8, [rbp+47h+pv]; pv
0x18066d1fd  mov     edx, 20h ; ' '; c
0x18066d202  mov     rcx, rsi; h
0x18066d205  call    cs:__imp_GetObjectW
0x18066d20b  test    eax, eax
0x18066d20d  jnz     short loc_18066D24C
0x18066d20f  mov     rcx, [rbp+4Fh]; this
0x18066d213  lea     r8, aShellIncGdihel; "shell\\inc\\GDIHelpers.h"
0x18066d21a  mov     edx, 181h; void *
0x18066d21f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18066d224  mov     esi, eax
0x18066d226  mov     rdx, r15; h
0x18066d229  mov     rcx, rbx; hdc
0x18066d22c  call    cs:__imp_SelectObject
0x18066d232  nop
0x18066d233  mov     rcx, rbx; hdc
0x18066d236  call    cs:__imp_DeleteDC
0x18066d23c  nop
0x18066d23d  mov     rcx, rdi; hdc
0x18066d240  call    cs:__imp_DeleteDC
0x18066d246  nop
0x18066d247  jmp     loc_18066D19D
0x18066d24c  mov     [rbp+47h+pbmi.bmiHeader.biSize], 2Ch ; ','
0x18066d253  xorps   xmm0, xmm0
0x18066d256  xor     eax, eax
0x18066d258  movups  xmmword ptr [rbp+47h+pbmi.bmiHeader.biWidth], xmm0
0x18066d25c  movups  xmmword ptr [rbp+47h+pbmi.bmiHeader.biSizeImage], xmm0
0x18066d260  mov     qword ptr [rbp+47h+pbmi.bmiHeader.biClrImportant], rax
0x18066d264  mov     eax, [r12]
0x18066d268  mov     [rbp+47h+pbmi.bmiHeader.biWidth], eax
0x18066d26b  mov     eax, [r12+4]
0x18066d270  mov     [rbp+47h+pbmi.bmiHeader.biHeight], eax
0x18066d273  mov     qword ptr [rbp+47h+pbmi.bmiHeader.biPlanes], 200001h
0x18066d27b  mov     [rsp+130h+ppvBits], r14
0x18066d280  mov     [rsp+130h+offset], r14d; bool
0x18066d285  mov     [rsp+130h+hSection], r14; unsigned int
0x18066d28a  lea     r9, [rsp+130h+ppvBits]; ppvBits
0x18066d28f  xor     r8d, r8d; usage
0x18066d292  lea     rdx, [rbp+47h+pbmi]; pbmi
0x18066d296  mov     rcx, rdi; hdc
0x18066d299  call    cs:__imp_CreateDIBSection
0x18066d29f  mov     rsi, rax
0x18066d2a2  mov     qword ptr [rsp+130h+var_D0.BlendOp], rax
0x18066d2a7  test    rax, rax
0x18066d2aa  jnz     short loc_18066D2FB
0x18066d2ac  mov     rcx, [rbp+4Fh]; this
0x18066d2b0  mov     esi, 8007000Eh
0x18066d2b5  mov     r9d, esi; char *
0x18066d2b8  lea     r8, aShellIncGdihel; "shell\\inc\\GDIHelpers.h"
0x18066d2bf  mov     edx, 18Dh; void *
0x18066d2c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18066d2c9  nop
0x18066d2ca  lea     rcx, [rsp+130h+var_D0]
0x18066d2cf  call    ?Release@?$CTSmartObj@PEAUHFONT__@@V?$CAutoHandle_Policy@PEAUHFONT__@@@@@@QEAAXXZ; CTSmartObj<HFONT__ *,CAutoHandle_Policy<HFONT__ *>>::Release(void)
0x18066d2d4  nop
0x18066d2d5  mov     rdx, r15; h
0x18066d2d8  mov     rcx, rbx; hdc
0x18066d2db  call    cs:__imp_SelectObject
0x18066d2e1  nop
0x18066d2e2  mov     rcx, rbx; hdc
0x18066d2e5  call    cs:__imp_DeleteDC
0x18066d2eb  nop
0x18066d2ec  mov     rcx, rdi; hdc
0x18066d2ef  call    cs:__imp_DeleteDC
0x18066d2f5  nop
0x18066d2f6  jmp     loc_18066D19D
0x18066d2fb  mov     rdx, rsi; h
0x18066d2fe  mov     rcx, rdi; hdc
0x18066d301  call    cs:__imp_SelectObject
0x18066d307  mov     r14, rax
0x18066d30a  mov     eax, [r12]
0x18066d30e  sub     eax, [r13+0]
0x18066d312  cdq
0x18066d313  mov     r9d, 2
0x18066d319  idiv    r9d
0x18066d31c  mov     ecx, eax
0x18066d31e  mov     [rbp+47h+var_88.unused], eax
0x18066d321  mov     eax, [r12+4]
0x18066d326  sub     eax, [r13+4]
0x18066d32a  cdq
0x18066d32b  idiv    r9d
0x18066d32e  mov     [rbp+47h+var_84], eax
0x18066d331  add     ecx, [r13+0]
0x18066d335  mov     [rbp+47h+var_80], ecx
0x18066d338  add     eax, [r13+4]
0x18066d33c  mov     [rbp+47h+var_7C], eax
0x18066d33f  mov     r9, [rbp+47h+var_C0]
0x18066d343  mov     r9d, [r9]; unsigned __int8
0x18066d346  lea     rdx, [rbp+47h+var_88]; HDC
0x18066d34a  mov     rcx, rdi; hdc
0x18066d34d  call    ?FillRectARGB@GDIHelpers@@YAXPEAUHDC__@@PEBUtagRECT@@EK_N@Z; GDIHelpers::FillRectARGB(HDC__ *,tagRECT const *,uchar,ulong,bool)
0x18066d352  mov     r11d, dword ptr [rbp+47h+pv+4]
0x18066d356  mov     r9d, r11d
0x18066d359  mov     rax, [rbp+47h+var_B8]
0x18066d35d  cmp     [rax], r11d
0x18066d360  cmovl   r9d, [rax]; wDest
0x18066d364  mov     ecx, dword ptr [rbp+47h+pv+8]
0x18066d367  mov     r10d, ecx
0x18066d36a  cmp     [rax+4], ecx
0x18066d36d  cmovl   r10d, [rax+4]
0x18066d372  mov     dword ptr [rsp+130h+var_D0.BlendOp], 1FF0000h
0x18066d37a  mov     eax, [r12+4]
0x18066d37f  sub     eax, r10d
0x18066d382  cdq
0x18066d383  mov     r13d, 2
0x18066d389  idiv    r13d
0x18066d38c  mov     r8d, eax; yoriginDest
0x18066d38f  mov     eax, [r12]
0x18066d393  sub     eax, r9d
0x18066d396  cdq
0x18066d397  idiv    r13d
0x18066d39a  mov     edx, eax; xoriginDest
0x18066d39c  mov     eax, dword ptr [rsp+130h+var_D0.BlendOp]
0x18066d3a0  mov     dword ptr [rsp+130h+ftn.BlendOp], eax; ftn
0x18066d3a4  mov     [rsp+130h+hSrc], ecx; hSrc
0x18066d3a8  mov     [rsp+130h+wSrc], r11d; wSrc
0x18066d3ad  xor     r12d, r12d
0x18066d3b0  mov     [rsp+130h+yoriginSrc], r12d; yoriginSrc
0x18066d3b5  mov     [rsp+130h+xoriginSrc], r12d; xoriginSrc
0x18066d3ba  mov     qword ptr [rsp+130h+offset], rbx; hdcSrc
0x18066d3bf  mov     dword ptr [rsp+130h+hSection], r10d; hDest
0x18066d3c4  mov     rcx, rdi; hdcDest
0x18066d3c7  call    cs:__imp_GdiAlphaBlend
0x18066d3cd  mov     qword ptr [rsp+130h+var_D0.BlendOp], r12
0x18066d3d2  mov     rax, [rbp+47h+var_B0]
0x18066d3d6  mov     [rax], rsi
0x18066d3d9  mov     rdx, r14; h
0x18066d3dc  mov     rcx, rdi; hdc
0x18066d3df  call    cs:__imp_SelectObject
0x18066d3e5  nop
0x18066d3e6  lea     rcx, [rsp+130h+var_D0]
0x18066d3eb  call    ?Release@?$CTSmartObj@PEAUHFONT__@@V?$CAutoHandle_Policy@PEAUHFONT__@@@@@@QEAAXXZ; CTSmartObj<HFONT__ *,CAutoHandle_Policy<HFONT__ *>>::Release(void)
0x18066d3f0  nop
0x18066d3f1  mov     rdx, r15; h
0x18066d3f4  mov     rcx, rbx; hdc
0x18066d3f7  call    cs:__imp_SelectObject
0x18066d3fd  nop
0x18066d3fe  mov     rcx, rbx; hdc
0x18066d401  call    cs:__imp_DeleteDC
0x18066d407  nop
0x18066d408  mov     rcx, rdi; hdc
0x18066d40b  call    cs:__imp_DeleteDC
0x18066d411  nop
0x18066d412  xor     eax, eax
0x18066d414  mov     rcx, [rbp+47h+var_48]
0x18066d418  xor     rcx, rsp; StackCookie
0x18066d41b  call    __security_check_cookie
0x18066d420  add     rsp, 0F8h
0x18066d427  pop     r15
0x18066d429  pop     r14
0x18066d42b  pop     r13
0x18066d42d  pop     r12
0x18066d42f  pop     rdi
0x18066d430  pop     rsi
0x18066d431  pop     rbx
0x18066d432  pop     rbp
0x18066d433  retn
```
