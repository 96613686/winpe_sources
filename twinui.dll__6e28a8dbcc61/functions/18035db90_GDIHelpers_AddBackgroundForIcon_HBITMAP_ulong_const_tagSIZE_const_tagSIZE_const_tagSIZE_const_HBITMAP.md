# GDIHelpers::AddBackgroundForIcon(HBITMAP__ *,ulong const &,tagSIZE const &,tagSIZE const &,tagSIZE const &,HBITMAP__ * *)

- ea: `0x18035db90`
- end: `0x18035de4a`
- name: `?AddBackgroundForIcon@GDIHelpers@@YAJPEAUHBITMAP__@@AEBKAEBUtagSIZE@@22PEAPEAU2@@Z`
- size: `698`
- prototype: `__int64 __usercall@<rax>(HANDLE h@<rcx>, HBITMAP@<rdx>, const unsigned int *@<r8>, const struct tagSIZE *@<r9>, const struct tagSIZE *, const struct tagSIZE *, HBITMAP *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18035e038`

## callees

- `0x18003c5e4`
- `0x1800baf48`
- `0x1800ead54`
- `0x1800f2c34`
- `0x18010590c`
- `0x180107768`
- `0x18013d330`
- `0x18035db90`

## import_xrefs

- `GDI32!GdiAlphaBlend` at `0x18035dde3`
- `GDI32!GdiAlphaBlend` at `0x18035dde3`
- `GDI32!GetObjectW` at `0x18035dc5c`
- `GDI32!GetObjectW` at `0x18035dc5c`
- `GDI32!CreateCompatibleDC` at `0x18035dbd2`
- `GDI32!CreateCompatibleDC` at `0x18035dc05`
- `GDI32!CreateCompatibleDC` at `0x18035dbd2`
- `GDI32!CreateCompatibleDC` at `0x18035dc05`
- `GDI32!DeleteDC` at `0x18035dc8c`
- `GDI32!DeleteDC` at `0x18035de16`
- `GDI32!DeleteDC` at `0x18035de22`
- `GDI32!DeleteDC` at `0x18035dc8c`
- `GDI32!DeleteDC` at `0x18035de16`
- `GDI32!DeleteDC` at `0x18035de22`
- `GDI32!CreateDIBSection` at `0x18035dce1`
- `GDI32!CreateDIBSection` at `0x18035dce1`

## pseudocode

```c
__int64 __fastcall GDIHelpers::AddBackgroundForIcon(
        HANDLE h,
        int *a2,
        LONG *a3,
        const struct tagSIZE *a4,
        const struct tagSIZE *a5,
        struct tagSIZE *a6)
{
  HDC CompatibleDC; // rax
  HDC v11; // rdi
  unsigned int LastError; // esi
  HDC v13; // rax
  HDC v14; // rbx
  const char *v15; // r9
  LONG v16; // eax
  LONG v17; // eax
  HBITMAP v18; // rax
  HBITMAP v19; // rsi
  int v20; // ecx
  int v21; // r9d
  int v22; // eax
  const struct tagRECT *v23; // r8
  LONG cy; // r10d
  LONG cx; // r9d
  unsigned int v26; // eax
  bool v27; // cc
  int hSection; // [rsp+20h] [rbp-E0h]
  unsigned int hSectiona; // [rsp+20h] [rbp-E0h]
  bool offset; // [rsp+28h] [rbp-D8h]
  BLENDFUNCTION ftn[2]; // [rsp+60h] [rbp-A0h] BYREF
  void *ppvBits; // [rsp+68h] [rbp-98h] BYREF
  struct tagSIZE *v34; // [rsp+70h] [rbp-90h]
  _BYTE v35[16]; // [rsp+78h] [rbp-88h] BYREF
  _OWORD pv[2]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v37[16]; // [rsp+A8h] [rbp-58h] BYREF
  struct HDC__ v38; // [rsp+B8h] [rbp-48h] BYREF
  int v39; // [rsp+BCh] [rbp-44h]
  int v40; // [rsp+C0h] [rbp-40h]
  int v41; // [rsp+C4h] [rbp-3Ch]
  BITMAPINFO pbmi; // [rsp+C8h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v34 = a6;
  CompatibleDC = CreateCompatibleDC(0);
  v11 = CompatibleDC;
  if ( CompatibleDC )
  {
    v13 = CreateCompatibleDC(CompatibleDC);
    v14 = v13;
    if ( v13 )
    {
      Microsoft::WRL::Wrappers::AutoSelectObject<HBITMAP__ *>::AutoSelectObject<HBITMAP__ *>(v35, v13, h);
      memset(pv, 0, sizeof(pv));
      if ( GetObjectW(h, 32, pv) )
      {
        v16 = *a3;
        memset(&pbmi.bmiHeader.biWidth, 0, 40);
        pbmi.bmiHeader.biWidth = v16;
        v17 = a3[1];
        ppvBits = 0;
        pbmi.bmiHeader.biHeight = v17;
        pbmi.bmiHeader.biSize = 44;
        *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
        v18 = CreateDIBSection(v11, &pbmi, 0, &ppvBits, 0, 0);
        *(_QWORD *)&ftn[0].BlendOp = v18;
        v19 = v18;
        if ( v18 )
        {
          Microsoft::WRL::Wrappers::AutoSelectObject<HBITMAP__ *>::AutoSelectObject<HBITMAP__ *>(v37, v11, v18);
          v38.unused = (*a3 - a4->cx) / 2;
          v20 = a4->cx + v38.unused;
          v21 = *a2;
          v39 = (a3[1] - a4->cy) / 2;
          v22 = a4->cy + v39;
          v40 = v20;
          v41 = v22;
          GDIHelpers::FillRectARGB(v11, &v38, v23, v21, hSectiona, offset);
          cy = DWORD2(pv[0]);
          cx = DWORD1(pv[0]);
          v26 = a3[1];
          if ( a5->cx < SDWORD1(pv[0]) )
            cx = a5->cx;
          v27 = a5->cy < SDWORD2(pv[0]);
          ftn[0] = (BLENDFUNCTION)33488896;
          if ( v27 )
            cy = a5->cy;
          GdiAlphaBlend(
            v11,
            (*a3 - cx) / 2,
            (int)(v26 - cy) / 2,
            cx,
            cy,
            v14,
            0,
            0,
            SDWORD1(pv[0]),
            SDWORD2(pv[0]),
            ftn[0]);
          *(_QWORD *)&ftn[0].BlendOp = 0;
          *v34 = (struct tagSIZE)v19;
          Microsoft::WRL::Wrappers::AutoSelectObject<HBITMAP__ *>::~AutoSelectObject<HBITMAP__ *>(v37);
          CTSmartObj<HFONT__ *,CAutoHandle_Policy<HFONT__ *>>::Release(ftn);
          Microsoft::WRL::Wrappers::AutoSelectObject<HBITMAP__ *>::~AutoSelectObject<HBITMAP__ *>(v35);
          DeleteDC(v14);
          LastError = 0;
          goto LABEL_15;
        }
        LastError = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x18D,
          (unsigned int)"shell\\inc\\GDIHelpers.h",
          (const char *)0x8007000ELL,
          hSectiona);
        CTSmartObj<HFONT__ *,CAutoHandle_Policy<HFONT__ *>>::Release(ftn);
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x181,
                      (unsigned int)"shell\\inc\\GDIHelpers.h",
                      v15);
      }
      Microsoft::WRL::Wrappers::AutoSelectObject<HBITMAP__ *>::~AutoSelectObject<HBITMAP__ *>(v35);
      DeleteDC(v14);
    }
    else
    {
      LastError = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x17B,
        (unsigned int)"shell\\inc\\GDIHelpers.h",
        (const char *)0x8007000ELL,
        hSection);
    }
LABEL_15:
    DeleteDC(v11);
    return LastError;
  }
  LastError = -2147024882;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x178,
    (unsigned int)"shell\\inc\\GDIHelpers.h",
    (const char *)0x8007000ELL,
    hSection);
  return LastError;
}

```

## disassembly

```asm
0x18035db90  push    rbp
0x18035db92  push    rbx
0x18035db93  push    rsi
0x18035db94  push    rdi
0x18035db95  push    r12
0x18035db97  push    r13
0x18035db99  push    r14
0x18035db9b  push    r15
0x18035db9d  lea     rbp, [rsp-8]
0x18035dba2  sub     rsp, 108h
0x18035dba9  mov     rax, cs:__security_cookie
0x18035dbb0  xor     rax, rsp
0x18035dbb3  mov     [rbp+40h+var_48], rax
0x18035dbb7  mov     rax, [rbp+40h+arg_28]
0x18035dbbb  mov     rsi, rcx
0x18035dbbe  mov     r12, [rbp+40h+arg_20]
0x18035dbc2  xor     ecx, ecx; hdc
0x18035dbc4  mov     [rsp+140h+var_D0], rax
0x18035dbc9  mov     r15, r9
0x18035dbcc  mov     r14, r8
0x18035dbcf  mov     r13, rdx
0x18035dbd2  call    cs:__imp_CreateCompatibleDC
0x18035dbd8  mov     rdi, rax
0x18035dbdb  test    rax, rax
0x18035dbde  jnz     short loc_18035DC02
0x18035dbe0  mov     rcx, [rbp+48h]; this
0x18035dbe4  lea     r8, aShellIncGdihel; "shell\\inc\\GDIHelpers.h"
0x18035dbeb  mov     esi, 8007000Eh
0x18035dbf0  mov     edx, 178h; void *
0x18035dbf5  mov     r9d, esi; char *
0x18035dbf8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18035dbfd  jmp     loc_18035DE28
0x18035dc02  mov     rcx, rdi; hdc
0x18035dc05  call    cs:__imp_CreateCompatibleDC
0x18035dc0b  mov     rbx, rax
0x18035dc0e  test    rax, rax
0x18035dc11  jnz     short loc_18035DC35
0x18035dc13  mov     rcx, [rbp+48h]; this
0x18035dc17  lea     r8, aShellIncGdihel; "shell\\inc\\GDIHelpers.h"
0x18035dc1e  mov     esi, 8007000Eh
0x18035dc23  mov     edx, 17Bh; void *
0x18035dc28  mov     r9d, esi; char *
0x18035dc2b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18035dc30  jmp     loc_18035DE1F
0x18035dc35  mov     r8, rsi
0x18035dc38  lea     rcx, [rsp+140h+var_C8]
0x18035dc3d  mov     rdx, rbx
0x18035dc40  call    ??0?$AutoSelectObject@PEAUHBITMAP__@@@Wrappers@WRL@Microsoft@@QEAA@PEAUHDC__@@PEAUHBITMAP__@@@Z; Microsoft::WRL::Wrappers::AutoSelectObject<HBITMAP__ *>::AutoSelectObject<HBITMAP__ *>(HDC__ *,HBITMAP__ *)
0x18035dc45  xorps   xmm0, xmm0
0x18035dc48  lea     r8, [rbp+40h+pv]; pv
0x18035dc4c  mov     edx, 20h ; ' '; c
0x18035dc51  mov     rcx, rsi; h
0x18035dc54  movups  [rbp+40h+pv], xmm0
0x18035dc58  movups  [rbp+40h+var_A8], xmm0
0x18035dc5c  call    cs:__imp_GetObjectW
0x18035dc62  xor     ecx, ecx
0x18035dc64  test    eax, eax
0x18035dc66  jnz     short loc_18035DC97
0x18035dc68  mov     rcx, [rbp+48h]; this
0x18035dc6c  lea     r8, aShellIncGdihel; "shell\\inc\\GDIHelpers.h"
0x18035dc73  mov     edx, 181h; void *
0x18035dc78  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18035dc7d  mov     esi, eax
0x18035dc7f  lea     rcx, [rsp+140h+var_C8]
0x18035dc84  call    ??1?$AutoSelectObject@PEAUHBITMAP__@@@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::AutoSelectObject<HBITMAP__ *>::~AutoSelectObject<HBITMAP__ *>(void)
0x18035dc89  mov     rcx, rbx; hdc
0x18035dc8c  call    cs:__imp_DeleteDC
0x18035dc92  jmp     loc_18035DE1F
0x18035dc97  xor     eax, eax
0x18035dc99  mov     [rsp+140h+offset], ecx; bool
0x18035dc9d  xorps   xmm0, xmm0
0x18035dca0  mov     qword ptr [rbp+40h+pbmi.bmiHeader.biClrImportant], rax
0x18035dca4  mov     eax, [r14]
0x18035dca7  lea     r9, [rsp+140h+ppvBits]; ppvBits
0x18035dcac  movups  xmmword ptr [rbp+40h+pbmi.bmiHeader.biWidth], xmm0
0x18035dcb0  mov     [rbp+40h+pbmi.bmiHeader.biWidth], eax
0x18035dcb3  lea     rdx, [rbp+40h+pbmi]; pbmi
0x18035dcb7  mov     eax, [r14+4]
0x18035dcbb  xor     r8d, r8d; usage
0x18035dcbe  mov     [rsp+140h+ppvBits], rcx
0x18035dcc3  mov     [rsp+140h+hSection], rcx; unsigned int
0x18035dcc8  mov     rcx, rdi; hdc
0x18035dccb  mov     [rbp+40h+pbmi.bmiHeader.biHeight], eax
0x18035dcce  mov     [rbp+40h+pbmi.bmiHeader.biSize], 2Ch ; ','
0x18035dcd5  movups  xmmword ptr [rbp+40h+pbmi.bmiHeader.biSizeImage], xmm0
0x18035dcd9  mov     qword ptr [rbp+40h+pbmi.bmiHeader.biPlanes], 200001h
0x18035dce1  call    cs:__imp_CreateDIBSection
0x18035dce7  mov     qword ptr [rsp+140h+var_E0.BlendOp], rax
0x18035dcec  mov     rsi, rax
0x18035dcef  test    rax, rax
0x18035dcf2  jnz     short loc_18035DD20
0x18035dcf4  mov     rcx, [rbp+48h]; this
0x18035dcf8  lea     r8, aShellIncGdihel; "shell\\inc\\GDIHelpers.h"
0x18035dcff  mov     esi, 8007000Eh
0x18035dd04  mov     edx, 18Dh; void *
0x18035dd09  mov     r9d, esi; char *
0x18035dd0c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18035dd11  lea     rcx, [rsp+140h+var_E0]
0x18035dd16  call    ?Release@?$CTSmartObj@PEAUHFONT__@@V?$CAutoHandle_Policy@PEAUHFONT__@@@@@@QEAAXXZ; CTSmartObj<HFONT__ *,CAutoHandle_Policy<HFONT__ *>>::Release(void)
0x18035dd1b  jmp     loc_18035DC7F
0x18035dd20  mov     r8, rsi
0x18035dd23  lea     rcx, [rbp+40h+var_98]
0x18035dd27  mov     rdx, rdi
0x18035dd2a  call    ??0?$AutoSelectObject@PEAUHBITMAP__@@@Wrappers@WRL@Microsoft@@QEAA@PEAUHDC__@@PEAUHBITMAP__@@@Z; Microsoft::WRL::Wrappers::AutoSelectObject<HBITMAP__ *>::AutoSelectObject<HBITMAP__ *>(HDC__ *,HBITMAP__ *)
0x18035dd2f  mov     eax, [r14]
0x18035dd32  mov     r9d, 2
0x18035dd38  sub     eax, [r15]
0x18035dd3b  cdq
0x18035dd3c  idiv    r9d
0x18035dd3f  mov     ecx, eax
0x18035dd41  mov     [rbp+40h+var_88.unused], eax
0x18035dd44  mov     eax, [r14+4]
0x18035dd48  sub     eax, [r15+4]
0x18035dd4c  add     ecx, [r15]
0x18035dd4f  cdq
0x18035dd50  idiv    r9d
0x18035dd53  mov     r9d, [r13+0]; unsigned __int8
0x18035dd57  lea     rdx, [rbp+40h+var_88]; HDC
0x18035dd5b  mov     [rbp+40h+var_84], eax
0x18035dd5e  add     eax, [r15+4]
0x18035dd62  mov     [rbp+40h+var_80], ecx
0x18035dd65  mov     rcx, rdi; hdc
0x18035dd68  mov     [rbp+40h+var_7C], eax
0x18035dd6b  call    ?FillRectARGB@GDIHelpers@@YAXPEAUHDC__@@PEBUtagRECT@@EK_N@Z; GDIHelpers::FillRectARGB(HDC__ *,tagRECT const *,uchar,ulong,bool)
0x18035dd70  mov     ecx, dword ptr [rbp+40h+pv+8]
0x18035dd73  mov     r10d, ecx
0x18035dd76  mov     r11d, dword ptr [rbp+40h+pv+4]
0x18035dd7a  mov     r9d, r11d
0x18035dd7d  cmp     [r12], r11d
0x18035dd81  mov     eax, [r14+4]
0x18035dd85  cmovl   r9d, [r12]; wDest
0x18035dd8a  cmp     [r12+4], ecx
0x18035dd8f  mov     dword ptr [rsp+140h+var_E0.BlendOp], 1FF0000h
0x18035dd97  cmovl   r10d, [r12+4]
0x18035dd9d  xor     r12d, r12d
0x18035dda0  sub     eax, r10d
0x18035dda3  cdq
0x18035dda4  lea     r15d, [r12+2]
0x18035dda9  idiv    r15d
0x18035ddac  mov     r8d, eax; yoriginDest
0x18035ddaf  mov     eax, [r14]
0x18035ddb2  sub     eax, r9d
0x18035ddb5  cdq
0x18035ddb6  idiv    r15d
0x18035ddb9  mov     edx, eax; xoriginDest
0x18035ddbb  mov     eax, dword ptr [rsp+140h+var_E0.BlendOp]
0x18035ddbf  mov     dword ptr [rsp+140h+ftn.BlendOp], eax; ftn
0x18035ddc3  mov     [rsp+140h+hSrc], ecx; hSrc
0x18035ddc7  mov     rcx, rdi; hdcDest
0x18035ddca  mov     [rsp+140h+wSrc], r11d; wSrc
0x18035ddcf  mov     [rsp+140h+yoriginSrc], r12d; yoriginSrc
0x18035ddd4  mov     [rsp+140h+xoriginSrc], r12d; xoriginSrc
0x18035ddd9  mov     qword ptr [rsp+140h+offset], rbx; hdcSrc
0x18035ddde  mov     dword ptr [rsp+140h+hSection], r10d; hDest
0x18035dde3  call    cs:__imp_GdiAlphaBlend
0x18035dde9  mov     rax, [rsp+140h+var_D0]
0x18035ddee  lea     rcx, [rbp+40h+var_98]
0x18035ddf2  mov     qword ptr [rsp+140h+var_E0.BlendOp], r12
0x18035ddf7  mov     [rax], rsi
0x18035ddfa  call    ??1?$AutoSelectObject@PEAUHBITMAP__@@@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::AutoSelectObject<HBITMAP__ *>::~AutoSelectObject<HBITMAP__ *>(void)
0x18035ddff  lea     rcx, [rsp+140h+var_E0]
0x18035de04  call    ?Release@?$CTSmartObj@PEAUHFONT__@@V?$CAutoHandle_Policy@PEAUHFONT__@@@@@@QEAAXXZ; CTSmartObj<HFONT__ *,CAutoHandle_Policy<HFONT__ *>>::Release(void)
0x18035de09  lea     rcx, [rsp+140h+var_C8]
0x18035de0e  call    ??1?$AutoSelectObject@PEAUHBITMAP__@@@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::AutoSelectObject<HBITMAP__ *>::~AutoSelectObject<HBITMAP__ *>(void)
0x18035de13  mov     rcx, rbx; hdc
0x18035de16  call    cs:__imp_DeleteDC
0x18035de1c  mov     esi, r12d
0x18035de1f  mov     rcx, rdi; hdc
0x18035de22  call    cs:__imp_DeleteDC
0x18035de28  mov     eax, esi
0x18035de2a  mov     rcx, [rbp+40h+var_48]
0x18035de2e  xor     rcx, rsp; StackCookie
0x18035de31  call    __security_check_cookie
0x18035de36  add     rsp, 108h
0x18035de3d  pop     r15
0x18035de3f  pop     r14
0x18035de41  pop     r13
0x18035de43  pop     r12
0x18035de45  pop     rdi
0x18035de46  pop     rsi
0x18035de47  pop     rbx
0x18035de48  pop     rbp
0x18035de49  retn
```
