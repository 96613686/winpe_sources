# SHAreIconsEqual

- ea: `0x180009b60`
- end: `0x180009db2`
- name: `SHAreIconsEqual`
- size: `594`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x180009b60`
- `0x180009db8`
- `0x18000b430`
- `0x180012550`
- `0x1800369c5`

## import_xrefs

- `GDI32!GetObjectW` at `0x180009bfc`
- `GDI32!GetObjectW` at `0x180009c1f`
- `GDI32!GetObjectW` at `0x180009bfc`
- `GDI32!GetObjectW` at `0x180009c1f`
- `GDI32!GetDIBits` at `0x180009cdd`
- `GDI32!GetDIBits` at `0x180009d21`
- `GDI32!GetDIBits` at `0x180009cdd`
- `GDI32!GetDIBits` at `0x180009d21`
- `GDI32!DeleteObject` at `0x180009d63`
- `GDI32!DeleteObject` at `0x180009d6d`
- `GDI32!DeleteObject` at `0x180009d77`
- `GDI32!DeleteObject` at `0x180009d81`
- `GDI32!DeleteObject` at `0x180009d63`
- `GDI32!DeleteObject` at `0x180009d6d`
- `GDI32!DeleteObject` at `0x180009d77`
- `GDI32!DeleteObject` at `0x180009d81`
- `USER32!GetDC` at `0x180009c85`
- `USER32!GetDC` at `0x180009c85`
- `USER32!GetIconInfo` at `0x180009bb3`
- `USER32!GetIconInfo` at `0x180009bd5`
- `USER32!GetIconInfo` at `0x180009bb3`
- `USER32!GetIconInfo` at `0x180009bd5`
- `USER32!ReleaseDC` at `0x180009d59`
- `USER32!ReleaseDC` at `0x180009d59`

## pseudocode

```c
__int64 __fastcall SHAreIconsEqual(HICON a1, HICON a2)
{
  unsigned int v2; // r14d
  unsigned __int64 v4; // r15
  HDC DC; // rdi
  void *lpvBits; // rax
  void *v7; // rsi
  void *v8; // rbx
  ICONINFO v10; // [rsp+40h] [rbp-89h] BYREF
  ICONINFO piconinfo; // [rsp+60h] [rbp-69h] BYREF
  struct tagBITMAPINFO bmi; // [rsp+80h] [rbp-49h] BYREF
  _OWORD pv[2]; // [rsp+B0h] [rbp-19h] BYREF
  _OWORD v14[2]; // [rsp+D0h] [rbp+7h] BYREF

  v2 = 0;
  memset(&piconinfo, 0, sizeof(piconinfo));
  if ( a1 && a2 && GetIconInfo(a1, &piconinfo) )
  {
    memset(&v10, 0, sizeof(v10));
    if ( GetIconInfo(a2, &v10) )
    {
      memset(pv, 0, sizeof(pv));
      if ( GetObjectW(piconinfo.hbmColor, 32, pv) )
      {
        memset(v14, 0, sizeof(v14));
        if ( GetObjectW(v10.hbmColor, 32, v14) )
        {
          if ( *(_QWORD *)((char *)pv + 4) == *(_QWORD *)((char *)v14 + 4) )
          {
            v4 = SDWORD1(pv[0]) * (__int64)SDWORD2(pv[0]);
            if ( is_mul_ok(SDWORD1(pv[0]), SDWORD2(pv[0])) )
            {
              bmi.bmiHeader.biSize = 40;
              *(_QWORD *)&bmi.bmiHeader.biWidth = *(_QWORD *)((char *)pv + 4);
              *(_QWORD *)&bmi.bmiHeader.biPlanes = 2097153;
              memset(&bmi.bmiHeader.biSizeImage, 0, 24);
              DC = GetDC(0);
              if ( DC )
              {
                lpvBits = operator new(saturated_mul(v4, 4u));
                v7 = lpvBits;
                if ( lpvBits )
                {
                  if ( GetDIBits(DC, piconinfo.hbmColor, 0, DWORD2(pv[0]), lpvBits, &bmi, 0) )
                  {
                    v8 = operator new(saturated_mul(v4, 4u));
                    if ( v8 )
                    {
                      if ( GetDIBits(DC, v10.hbmColor, 0, DWORD2(pv[0]), v8, &bmi, 0) )
                        LOBYTE(v2) = memcmp_0(v7, v8, 4 * v4) == 0;
                      operator delete(v8);
                    }
                  }
                  operator delete(v7);
                }
                ReleaseDC(0, DC);
              }
            }
          }
        }
      }
      DeleteObject(v10.hbmColor);
      DeleteObject(v10.hbmMask);
    }
    DeleteObject(piconinfo.hbmColor);
    DeleteObject(piconinfo.hbmMask);
  }
  return v2;
}

```

## disassembly

```asm
0x180009b60  mov     [rsp-8+arg_10], rbx
0x180009b65  mov     [rsp-8+arg_18], rsi
0x180009b6a  push    rbp
0x180009b6b  push    rdi
0x180009b6c  push    r13
0x180009b6e  push    r14
0x180009b70  push    r15
0x180009b72  lea     rbp, [rsp-37h]
0x180009b77  sub     rsp, 100h
0x180009b7e  mov     rax, cs:__security_cookie
0x180009b85  xor     rax, rsp
0x180009b88  mov     [rbp+57h+var_28], rax
0x180009b8c  xorps   xmm0, xmm0
0x180009b8f  xor     r14d, r14d
0x180009b92  mov     rbx, rdx
0x180009b95  movups  xmmword ptr [rbp+57h+piconinfo.fIcon], xmm0
0x180009b99  movups  xmmword ptr [rbp+57h+piconinfo.hbmMask], xmm0
0x180009b9d  test    rcx, rcx
0x180009ba0  jz      loc_180009D87
0x180009ba6  test    rdx, rdx
0x180009ba9  jz      loc_180009D87
0x180009baf  lea     rdx, [rbp+57h+piconinfo]; piconinfo
0x180009bb3  call    cs:__imp_GetIconInfo
0x180009bb9  test    eax, eax
0x180009bbb  jz      loc_180009D87
0x180009bc1  xorps   xmm0, xmm0
0x180009bc4  lea     rdx, [rsp+120h+var_E0]; piconinfo
0x180009bc9  mov     rcx, rbx; hIcon
0x180009bcc  movups  xmmword ptr [rsp+120h+var_E0.fIcon], xmm0
0x180009bd1  movups  xmmword ptr [rbp+57h+var_E0.hbmMask], xmm0
0x180009bd5  call    cs:__imp_GetIconInfo
0x180009bdb  test    eax, eax
0x180009bdd  jz      loc_180009D73
0x180009be3  mov     rcx, [rbp+57h+piconinfo.hbmColor]; h
0x180009be7  lea     ebx, [r14+20h]
0x180009beb  xorps   xmm0, xmm0
0x180009bee  lea     r8, [rbp+57h+pv]; pv
0x180009bf2  mov     edx, ebx; c
0x180009bf4  movups  [rbp+57h+pv], xmm0
0x180009bf8  movups  [rbp+57h+var_60], xmm0
0x180009bfc  call    cs:__imp_GetObjectW
0x180009c02  test    eax, eax
0x180009c04  jz      loc_180009D5F
0x180009c0a  mov     rcx, [rbp+57h+var_E0.hbmColor]; h
0x180009c0e  lea     r8, [rbp+57h+var_50]; pv
0x180009c12  xorps   xmm0, xmm0
0x180009c15  mov     edx, ebx; c
0x180009c17  movups  [rbp+57h+var_50], xmm0
0x180009c1b  movups  [rbp+57h+var_40], xmm0
0x180009c1f  call    cs:__imp_GetObjectW
0x180009c25  test    eax, eax
0x180009c27  jz      loc_180009D5F
0x180009c2d  movsxd  r8, dword ptr [rbp+57h+pv+4]
0x180009c31  cmp     r8d, dword ptr [rbp+57h+var_50+4]
0x180009c35  jnz     loc_180009D5F
0x180009c3b  movsxd  r9, dword ptr [rbp+57h+pv+8]
0x180009c3f  cmp     r9d, dword ptr [rbp+57h+var_50+8]
0x180009c43  jnz     loc_180009D5F
0x180009c49  mov     rax, r9
0x180009c4c  mul     r8
0x180009c4f  mov     r15, rax
0x180009c52  test    rdx, rdx
0x180009c55  jnz     loc_180009D5F
0x180009c5b  xorps   xmm0, xmm0
0x180009c5e  mov     [rbp+57h+bmi.bmiHeader.biSize], 28h ; '('
0x180009c65  movups  xmmword ptr [rbp+57h+bmi.bmiHeader.biWidth], xmm0
0x180009c69  xor     eax, eax
0x180009c6b  mov     [rbp+57h+bmi.bmiHeader.biWidth], r8d
0x180009c6f  xor     ecx, ecx; hWnd
0x180009c71  mov     [rbp+57h+bmi.bmiHeader.biHeight], r9d
0x180009c75  mov     qword ptr [rbp+57h+bmi.bmiHeader.biPlanes], 200001h
0x180009c7d  movups  xmmword ptr [rbp+57h+bmi.bmiHeader.biSizeImage], xmm0
0x180009c81  mov     qword ptr [rbp+57h+bmi.bmiHeader.biClrImportant], rax
0x180009c85  call    cs:__imp_GetDC
0x180009c8b  mov     rdi, rax
0x180009c8e  test    rax, rax
0x180009c91  jz      loc_180009D5F
0x180009c97  lea     ebx, [r14+4]
0x180009c9b  mov     eax, ebx
0x180009c9d  lea     r13, [r14-1]
0x180009ca1  mul     r15
0x180009ca4  cmovb   rax, r13
0x180009ca8  mov     rcx, rax; unsigned __int64
0x180009cab  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009cb0  mov     rsi, rax
0x180009cb3  test    rax, rax
0x180009cb6  jz      loc_180009D54
0x180009cbc  mov     r9d, dword ptr [rbp+57h+pv+8]; cLines
0x180009cc0  lea     rcx, [rbp+57h+bmi]
0x180009cc4  mov     rdx, [rbp+57h+piconinfo.hbmColor]; hbm
0x180009cc8  xor     r8d, r8d; start
0x180009ccb  mov     [rsp+120h+usage], r14d; usage
0x180009cd0  mov     [rsp+120h+lpbmi], rcx; lpbmi
0x180009cd5  mov     rcx, rdi; hdc
0x180009cd8  mov     [rsp+120h+lpvBits], rax; lpvBits
0x180009cdd  call    cs:__imp_GetDIBits
0x180009ce3  test    eax, eax
0x180009ce5  jz      short loc_180009D4C
0x180009ce7  mov     eax, ebx
0x180009ce9  mul     r15
0x180009cec  cmovb   rax, r13
0x180009cf0  mov     rcx, rax; unsigned __int64
0x180009cf3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009cf8  mov     rbx, rax
0x180009cfb  test    rax, rax
0x180009cfe  jz      short loc_180009D4C
0x180009d00  mov     r9d, dword ptr [rbp+57h+pv+8]; cLines
0x180009d04  lea     rax, [rbp+57h+bmi]
0x180009d08  mov     rdx, [rbp+57h+var_E0.hbmColor]; hbm
0x180009d0c  xor     r8d, r8d; start
0x180009d0f  mov     [rsp+120h+usage], r14d; usage
0x180009d14  mov     rcx, rdi; hdc
0x180009d17  mov     [rsp+120h+lpbmi], rax; lpbmi
0x180009d1c  mov     [rsp+120h+lpvBits], rbx; lpvBits
0x180009d21  call    cs:__imp_GetDIBits
0x180009d27  test    eax, eax
0x180009d29  jz      short loc_180009D44
0x180009d2b  lea     r8, ds:0[r15*4]; Size
0x180009d33  mov     rdx, rbx; Buf2
0x180009d36  mov     rcx, rsi; Buf1
0x180009d39  call    memcmp_0
0x180009d3e  test    eax, eax
0x180009d40  setz    r14b
0x180009d44  mov     rcx, rbx; lpMem
0x180009d47  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009d4c  mov     rcx, rsi; lpMem
0x180009d4f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009d54  mov     rdx, rdi; hDC
0x180009d57  xor     ecx, ecx; hWnd
0x180009d59  call    cs:__imp_ReleaseDC
0x180009d5f  mov     rcx, [rbp+57h+var_E0.hbmColor]; ho
0x180009d63  call    cs:__imp_DeleteObject
0x180009d69  mov     rcx, [rbp+57h+var_E0.hbmMask]; ho
0x180009d6d  call    cs:__imp_DeleteObject
0x180009d73  mov     rcx, [rbp+57h+piconinfo.hbmColor]; ho
0x180009d77  call    cs:__imp_DeleteObject
0x180009d7d  mov     rcx, [rbp+57h+piconinfo.hbmMask]; ho
0x180009d81  call    cs:__imp_DeleteObject
0x180009d87  mov     eax, r14d
0x180009d8a  mov     rcx, [rbp+57h+var_28]
0x180009d8e  xor     rcx, rsp; StackCookie
0x180009d91  call    __security_check_cookie
0x180009d96  lea     r11, [rsp+120h+var_20]
0x180009d9e  mov     rbx, [r11+40h]
0x180009da2  mov     rsi, [r11+48h]
0x180009da6  mov     rsp, r11
0x180009da9  pop     r15
0x180009dab  pop     r14
0x180009dad  pop     r13
0x180009daf  pop     rdi
0x180009db0  pop     rbp
0x180009db1  retn
```
