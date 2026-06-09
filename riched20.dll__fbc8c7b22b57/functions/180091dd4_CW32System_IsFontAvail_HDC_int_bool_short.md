# CW32System::IsFontAvail(HDC__ *,int,bool,short *)

- ea: `0x180091dd4`
- end: `0x180091fa9`
- name: `?IsFontAvail@CW32System@@SA_NPEAUHDC__@@H_NPEAF@Z`
- size: `469`
- prototype: `bool __fastcall(HDC hdc, int, bool, __int16 *)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18008fb68`
- `0x1800906a4`

## callees

- `0x18001e2e0`
- `0x18002cc48`
- `0x18003e56c`
- `0x180090024`
- `0x180090a6c`
- `0x180090bf4`
- `0x180091dd4`
- `0x180093aa4`
- `0x180093bca`
- `0x180093c00`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180091e8b`
- `msvcrt!wcscpy_s` at `0x180091e8b`
- `GDI32!DeleteObject` at `0x180091f57`
- `GDI32!DeleteObject` at `0x180091f57`
- `GDI32!SelectObject` at `0x180091ecf`
- `GDI32!SelectObject` at `0x180091f48`
- `GDI32!SelectObject` at `0x180091ecf`
- `GDI32!SelectObject` at `0x180091f48`

## pseudocode

```c
char __fastcall CW32System::IsFontAvail(HDC hdc, int a2, char a3, __int16 *a4)
{
  BYTE CharSet; // si
  BYTE v9; // al
  int v10; // ecx
  const wchar_t *FontName; // rax
  char v12; // di
  HFONT v13; // rax
  HFONT v14; // rbx
  HGDIOBJ v15; // r12
  int v16; // edx
  const unsigned __int16 *v17; // rsi
  int v19[4]; // [rsp+20h] [rbp-E0h] BYREF
  struct tagLOGFONTW v20; // [rsp+30h] [rbp-D0h] BYREF
  struct tagTEXTMETRICW v21; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 Src[32]; // [rsp+D0h] [rbp-30h] BYREF

  memset_0(&v20, 0, sizeof(v20));
  v19[0] = 0;
  CharSet = CW32System::GetCharSet(a2, v19);
  if ( CharSet && v19[0] == -1 )
    return 0;
  v20.lfCharSet = CharSet;
  if ( a3 )
  {
    v20.lfHeight = *((unsigned __int8 *)&g_pfinfo + 8 * v19[0] + 1);
    v9 = *((_BYTE *)&g_pfinfo + 8 * v19[0]);
    v10 = *((__int16 *)&g_pfinfo + 4 * v19[0] + 1);
  }
  else
  {
    v20.lfHeight = *((unsigned __int8 *)&g_pfinfo + 8 * v19[0] + 5);
    v9 = *((_BYTE *)&g_pfinfo + 8 * v19[0] + 4);
    v10 = *((__int16 *)&g_pfinfo + 4 * v19[0] + 3);
  }
  v20.lfPitchAndFamily = v9;
  FontName = GetFontName(v10);
  if ( !FontName )
    return 0;
  wcscpy_s(v20.lfFaceName, 0x20u, FontName);
  v20.lfHeight &= ~0x80u;
  v12 = 0;
  v13 = CW32System::CreateFontIndirect(&v20);
  v14 = v13;
  if ( v13 )
  {
    memset(&v21, 0, sizeof(v21));
    v15 = SelectObject(hdc, v13);
    if ( (unsigned int)CW32System::GetTextMetrics(hdc, &v21) )
    {
      if ( v21.tmCharSet == CharSet )
      {
        v12 = 1;
        if ( a4 )
        {
          v17 = GetFontName(*a4);
          if ( v17 )
          {
            Src[0] = 0;
            CW32System::GetTextFace(hdc, v16, Src);
            if ( Src[0] )
            {
              if ( (unsigned int)CW32System::wcsicmp(v17, Src) )
                *a4 = GetFontNameIndex(Src);
            }
          }
        }
      }
    }
    SelectObject(hdc, v15);
    DeleteObject(v14);
  }
  return v12;
}

```

## disassembly

```asm
0x180091dd4  mov     [rsp-8+arg_10], rbx
0x180091dd9  push    rbp
0x180091dda  push    rsi
0x180091ddb  push    rdi
0x180091ddc  push    r12
0x180091dde  push    r13
0x180091de0  push    r14
0x180091de2  push    r15
0x180091de4  lea     rbp, [rsp-20h]
0x180091de9  sub     rsp, 120h
0x180091df0  mov     rax, cs:__security_cookie
0x180091df7  xor     rax, rsp
0x180091dfa  mov     [rbp+50h+var_40], rax
0x180091dfe  mov     ebx, edx
0x180091e00  mov     dil, r8b
0x180091e03  xor     edx, edx; Val
0x180091e05  mov     r14, rcx
0x180091e08  lea     rcx, [rsp+150h+var_120]; void *
0x180091e0d  mov     r15, r9
0x180091e10  lea     r8d, [rdx+5Ch]; Size
0x180091e14  call    memset_0
0x180091e19  xor     r13d, r13d
0x180091e1c  lea     rdx, [rsp+150h+var_130]; int *
0x180091e21  mov     ecx, ebx; int
0x180091e23  mov     [rsp+150h+var_130], r13d
0x180091e28  call    ?GetCharSet@CW32System@@SAEHPEAH@Z; CW32System::GetCharSet(int,int *)
0x180091e2d  mov     sil, al
0x180091e30  movsxd  rax, [rsp+150h+var_130]
0x180091e35  test    sil, sil
0x180091e38  jz      short loc_180091E43
0x180091e3a  cmp     eax, 0FFFFFFFFh
0x180091e3d  jz      loc_180091FA5
0x180091e43  mov     [rsp+150h+var_120.lfCharSet], sil
0x180091e48  mov     rcx, rax
0x180091e4b  lea     rdx, ?g_pfinfo@@3PAUPreferredFontInfo@@A; PreferredFontInfo near * g_pfinfo
0x180091e52  test    dil, dil
0x180091e55  jz      loc_180091F8E
0x180091e5b  movzx   eax, byte ptr [rdx+rax*8+1]
0x180091e60  mov     [rsp+150h+var_120.lfHeight], eax
0x180091e64  mov     al, [rdx+rcx*8]
0x180091e67  movsx   ecx, word ptr [rdx+rcx*8+2]; int
0x180091e6c  mov     [rsp+150h+var_120.lfPitchAndFamily], al
0x180091e70  call    ?GetFontName@@YAPEBGJ@Z; GetFontName(long)
0x180091e75  test    rax, rax
0x180091e78  jz      loc_180091FA5
0x180091e7e  mov     r8, rax; Source
0x180091e81  lea     rcx, [rsp+150h+var_120.lfFaceName]; Destination
0x180091e86  mov     edx, 20h ; ' '; SizeInWords
0x180091e8b  call    cs:__imp_wcscpy_s
0x180091e92  nop     dword ptr [rax+rax+00h]
0x180091e97  btr     [rsp+150h+var_120.lfHeight], 7
0x180091e9d  lea     rcx, [rsp+150h+var_120]; struct tagLOGFONTW *
0x180091ea2  mov     dil, r13b
0x180091ea5  call    ?CreateFontIndirect@CW32System@@SAPEAUHFONT__@@PEBUtagLOGFONTW@@@Z; CW32System::CreateFontIndirect(tagLOGFONTW const *)
0x180091eaa  mov     rbx, rax
0x180091ead  test    rax, rax
0x180091eb0  jz      loc_180091F63
0x180091eb6  xorps   xmm0, xmm0
0x180091eb9  mov     rdx, rax; h
0x180091ebc  movups  xmmword ptr [rbp+50h+var_C0.tmOverhang], xmm0
0x180091ec0  mov     rcx, r14; hdc
0x180091ec3  movups  xmmword ptr [rbp+50h+var_C0.tmFirstChar], xmm0
0x180091ec7  movups  xmmword ptr [rbp+50h+var_C0.tmHeight], xmm0
0x180091ecb  movups  xmmword ptr [rbp+50h+var_C0.tmExternalLeading], xmm0
0x180091ecf  call    cs:__imp_SelectObject
0x180091ed6  nop     dword ptr [rax+rax+00h]
0x180091edb  lea     rdx, [rbp+50h+var_C0]; struct tagTEXTMETRICW *
0x180091edf  mov     rcx, r14; HDC
0x180091ee2  mov     r12, rax
0x180091ee5  call    ?GetTextMetrics@CW32System@@SAHPEAUHDC__@@PEAUtagTEXTMETRICW@@@Z; CW32System::GetTextMetrics(HDC__ *,tagTEXTMETRICW *)
0x180091eea  test    eax, eax
0x180091eec  jz      short loc_180091F42
0x180091eee  cmp     [rbp+50h+var_C0.tmCharSet], sil
0x180091ef2  jnz     short loc_180091F42
0x180091ef4  mov     dil, 1
0x180091ef7  test    r15, r15
0x180091efa  jz      short loc_180091F42
0x180091efc  movsx   ecx, word ptr [r15]; int
0x180091f00  call    ?GetFontName@@YAPEBGJ@Z; GetFontName(long)
0x180091f05  mov     rsi, rax
0x180091f08  test    rax, rax
0x180091f0b  jz      short loc_180091F42
0x180091f0d  lea     r8, [rbp+50h+Src]; unsigned __int16 *
0x180091f11  mov     [rbp+50h+Src], r13w
0x180091f16  mov     rcx, r14; hdc
0x180091f19  call    ?GetTextFace@CW32System@@SAHPEAUHDC__@@HPEAG@Z; CW32System::GetTextFace(HDC__ *,int,ushort *)
0x180091f1e  cmp     [rbp+50h+Src], r13w
0x180091f23  jz      short loc_180091F42
0x180091f25  lea     rdx, [rbp+50h+Src]; unsigned __int16 *
0x180091f29  mov     rcx, rsi; unsigned __int16 *
0x180091f2c  call    ?wcsicmp@CW32System@@SAHPEBG0@Z; CW32System::wcsicmp(ushort const *,ushort const *)
0x180091f31  test    eax, eax
0x180091f33  jz      short loc_180091F42
0x180091f35  lea     rcx, [rbp+50h+Src]; Src
0x180091f39  call    ?GetFontNameIndex@@YAFPEBG@Z; GetFontNameIndex(ushort const *)
0x180091f3e  mov     [r15], ax
0x180091f42  mov     rdx, r12; h
0x180091f45  mov     rcx, r14; hdc
0x180091f48  call    cs:__imp_SelectObject
0x180091f4f  nop     dword ptr [rax+rax+00h]
0x180091f54  mov     rcx, rbx; ho
0x180091f57  call    cs:__imp_DeleteObject
0x180091f5e  nop     dword ptr [rax+rax+00h]
0x180091f63  mov     al, dil
0x180091f66  mov     rcx, [rbp+50h+var_40]
0x180091f6a  xor     rcx, rsp; StackCookie
0x180091f6d  call    __security_check_cookie
0x180091f72  mov     rbx, [rsp+150h+arg_10]
0x180091f7a  add     rsp, 120h
0x180091f81  pop     r15
0x180091f83  pop     r14
0x180091f85  pop     r13
0x180091f87  pop     r12
0x180091f89  pop     rdi
0x180091f8a  pop     rsi
0x180091f8b  pop     rbp
0x180091f8c  retn
0x180091f8e  movzx   eax, byte ptr [rdx+rax*8+5]
0x180091f93  mov     [rsp+150h+var_120.lfHeight], eax
0x180091f97  mov     al, [rdx+rcx*8+4]
0x180091f9b  movsx   ecx, word ptr [rdx+rcx*8+6]
0x180091fa0  jmp     loc_180091E6C
0x180091fa5  xor     al, al
0x180091fa7  jmp     short loc_180091F66
```
