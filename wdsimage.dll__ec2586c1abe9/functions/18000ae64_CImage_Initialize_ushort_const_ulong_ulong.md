# CImage::Initialize(ushort const *,ulong,ulong)

- ea: `0x18000ae64`
- end: `0x18000b102`
- name: `?Initialize@CImage@@QEAAJPEBGKK@Z`
- size: `670`
- prototype: `__int64 __fastcall(CImage *__hidden this, const unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `9`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180005920`
- `0x180006090`
- `0x1800081b8`
- `0x180008e70`
- `0x1800094b8`
- `0x180009cb4`
- `0x18000a948`
- `0x18000abe0`
- `0x18000c77c`

## callees

- `0x18000a70c`
- `0x18000ae64`
- `0x18000ba2c`
- `0x18000d5b0`
- `0x18000d6b0`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18000afca`
- `msvcrt!wcsrchr` at `0x18000afca`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000b0dc`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000b0dc`
- `KERNEL32!GetFileAttributesW` at `0x18000af2a`
- `KERNEL32!GetFileAttributesW` at `0x18000af2a`
- `KERNEL32!GetLastError` at `0x18000af46`
- `KERNEL32!GetLastError` at `0x18000af46`
- `WdsCommonLib!?FormatString@@YAKPEAPEAG_KPEBGZZ` at `0x18000b091`
- `WdsCommonLib!?FormatString@@YAKPEAPEAG_KPEBGZZ` at `0x18000b091`
- `WdsCommonLib!ConcatenatePaths` at `0x18000b012`
- `WdsCommonLib!ConcatenatePaths` at `0x18000b045`
- `WdsCommonLib!ConcatenatePaths` at `0x18000b012`
- `WdsCommonLib!ConcatenatePaths` at `0x18000b045`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x18000aef2`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x18000af91`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x18000aef2`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x18000af91`

## string_xrefs

- `0x18000b03e`: `ImageUnattend.xml`

## pseudocode

```c
__int64 __fastcall CImage::Initialize(CImage *this, const unsigned __int16 *a2, int a3, int a4)
{
  _DWORD *v5; // rbp
  __int64 v8; // rbx
  __int64 v9; // rdx
  __int64 v10; // rdx
  LPCWSTR *v11; // r15
  __int64 v12; // rdx
  __int64 v13; // r8
  DWORD FileAttributesW; // eax
  signed int LastError; // eax
  __int64 v16; // rdx
  const wchar_t **v17; // r14
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rdx
  wchar_t *v21; // r15
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // rdx
  void *v30; // [rsp+60h] [rbp+8h] BYREF

  *((_DWORD *)this + 6) = a4;
  v5 = (_DWORD *)((char *)this + 28);
  v30 = 0;
  LODWORD(v8) = CImage::GetImageFormat(a2, (CImage *)((char *)this + 28));
  if ( (int)ElValidateHr_5((unsigned int)v8, v9, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 94) >= 0 )
  {
    if ( *v5
      || (LODWORD(v8) = -2147024883,
          (int)ElValidateHr_5(2147942413LL, v10, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 102) >= 0) )
    {
      v11 = (LPCWSTR *)((char *)this + 88);
      *((_DWORD *)this + 33) = a3;
      LODWORD(v8) = DuplicateStringW(a2, (unsigned __int16 **)this + 11);
      if ( (unsigned int)ElValidateWin32_4((unsigned int)v8, v12, v13, 110) )
      {
        if ( (int)v8 > 0 )
          LODWORD(v8) = (unsigned __int16)v8 | 0x80070000;
      }
      else
      {
        FileAttributesW = GetFileAttributesW(*v11);
        *((_DWORD *)this + 89) = FileAttributesW;
        if ( FileAttributesW != -1 )
          goto LABEL_13;
        LastError = GetLastError();
        LODWORD(v8) = LastError;
        if ( LastError > 0 )
          LODWORD(v8) = (unsigned __int16)LastError | 0x80070000;
        if ( (_DWORD)v8 == -2147024894 )
          LODWORD(v8) = -1056833013;
        if ( (int)ElValidateHr_5((unsigned int)v8, v16, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 124) >= 0 )
        {
LABEL_13:
          v17 = (const wchar_t **)((char *)this + 96);
          LODWORD(v8) = DuplicateStringW(*v11, (unsigned __int16 **)this + 12);
          if ( !(unsigned int)ElValidateWin32_4((unsigned int)v8, v18, v19, 131) )
          {
            v21 = wcsrchr(*v17, 0x2Eu);
            if ( !v21 )
            {
              LODWORD(v8) = -2147024883;
              if ( (int)ElValidateHr_5(2147942413LL, v20, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 137) < 0 )
                goto LABEL_23;
            }
            *v21 = 0;
            LODWORD(v8) = ConcatenatePaths(*v17, L"Unattend", &v30);
            if ( !(unsigned int)ElValidateWin32_4((unsigned int)v8, v22, v23, 149) )
            {
              v8 = (unsigned int)ConcatenatePaths(v30, L"ImageUnattend.xml", (char *)this + 104);
              if ( !(unsigned int)ElValidateWin32_4(v8, v24, v25, 155) )
              {
                if ( ((*v5 - 1) & 0xFFFFFFFD) != 0
                  || (LODWORD(v8) = FormatString(
                                      (unsigned __int16 **)this + 14,
                                      0,
                                      L"%s%s",
                                      *((_QWORD *)this + 11),
                                      L".permission"),
                      !(unsigned int)ElValidateWin32_4((unsigned int)v8, v26, v27, 169)) )
                {
                  LODWORD(v8) = CImage::Refresh(this);
                  ElValidateHr_5((unsigned int)v8, v28, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 176);
                  goto LABEL_23;
                }
              }
            }
          }
          if ( (int)v8 > 0 )
            LODWORD(v8) = (unsigned __int16)v8 | 0x80070000;
        }
      }
    }
  }
LABEL_23:
  if ( v30 )
    operator delete(v30);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000ae64  mov     [rsp+arg_8], rbx
0x18000ae69  mov     [rsp+arg_10], rbp
0x18000ae6e  push    rsi
0x18000ae6f  push    rdi
0x18000ae70  push    r12
0x18000ae72  push    r14
0x18000ae74  push    r15
0x18000ae76  sub     rsp, 30h
0x18000ae7a  mov     rdi, rdx
0x18000ae7d  mov     [rcx+18h], r9d
0x18000ae81  lea     rbp, [rcx+1Ch]
0x18000ae85  mov     rsi, rcx
0x18000ae88  xor     r12d, r12d
0x18000ae8b  mov     rdx, rbp; enum WdsImgFormat *
0x18000ae8e  mov     rcx, rdi; unsigned __int16 *
0x18000ae91  mov     [rsp+58h+arg_0], r12
0x18000ae96  mov     r14d, r8d
0x18000ae99  call    ?GetImageFormat@CImage@@SAJPEBGPEAW4WdsImgFormat@@@Z; CImage::GetImageFormat(ushort const *,WdsImgFormat *)
0x18000ae9e  lea     r9d, [r12+5Eh]
0x18000aea3  mov     ecx, eax
0x18000aea5  lea     r8, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x18000aeac  mov     ebx, eax
0x18000aeae  call    ElValidateHr_5
0x18000aeb3  test    eax, eax
0x18000aeb5  js      loc_18000B0D2
0x18000aebb  cmp     [rbp+0], r12d
0x18000aebf  jnz     short loc_18000AEE1
0x18000aec1  mov     ebx, 8007000Dh
0x18000aec6  lea     r9d, [r12+66h]
0x18000aecb  mov     ecx, ebx
0x18000aecd  lea     r8, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x18000aed4  call    ElValidateHr_5
0x18000aed9  test    eax, eax
0x18000aedb  js      loc_18000B0D2
0x18000aee1  lea     r15, [rsi+58h]
0x18000aee5  mov     [rsi+84h], r14d
0x18000aeec  mov     rdx, r15
0x18000aeef  mov     rcx, rdi
0x18000aef2  call    cs:__imp_?DuplicateStringW@@YAKPEBGPEAPEAG@Z; DuplicateStringW(ushort const *,ushort * *)
0x18000aef9  nop     dword ptr [rax+rax+00h]
0x18000aefe  mov     ecx, eax
0x18000af00  mov     r9d, 6Eh ; 'n'
0x18000af06  mov     ebx, eax
0x18000af08  call    ElValidateWin32_4
0x18000af0d  test    eax, eax
0x18000af0f  jz      short loc_18000AF27
0x18000af11  test    ebx, ebx
0x18000af13  jle     loc_18000B0D2
0x18000af19  movzx   ebx, bx
0x18000af1c  or      ebx, 80070000h
0x18000af22  jmp     loc_18000B0D2
0x18000af27  mov     rcx, [r15]; lpFileName
0x18000af2a  call    cs:__imp_GetFileAttributesW
0x18000af31  nop     dword ptr [rax+rax+00h]
0x18000af36  mov     [rsi+164h], eax
0x18000af3c  mov     edi, 80070000h
0x18000af41  cmp     eax, 0FFFFFFFFh
0x18000af44  jnz     short loc_18000AF87
0x18000af46  call    cs:__imp_GetLastError
0x18000af4d  nop     dword ptr [rax+rax+00h]
0x18000af52  mov     ebx, eax
0x18000af54  test    eax, eax
0x18000af56  jle     short loc_18000AF5D
0x18000af58  movzx   ebx, ax
0x18000af5b  or      ebx, edi
0x18000af5d  mov     eax, 0C102020Bh
0x18000af62  lea     r8, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x18000af69  cmp     ebx, 80070002h
0x18000af6f  mov     r9d, 7Ch ; '|'
0x18000af75  cmovz   ebx, eax
0x18000af78  mov     ecx, ebx
0x18000af7a  call    ElValidateHr_5
0x18000af7f  test    eax, eax
0x18000af81  js      loc_18000B0D2
0x18000af87  mov     rcx, [r15]
0x18000af8a  lea     r14, [rsi+60h]
0x18000af8e  mov     rdx, r14
0x18000af91  call    cs:__imp_?DuplicateStringW@@YAKPEBGPEAPEAG@Z; DuplicateStringW(ushort const *,ushort * *)
0x18000af98  nop     dword ptr [rax+rax+00h]
0x18000af9d  mov     ecx, eax
0x18000af9f  mov     r9d, 83h
0x18000afa5  mov     ebx, eax
0x18000afa7  call    ElValidateWin32_4
0x18000afac  test    eax, eax
0x18000afae  jz      short loc_18000AFC2
0x18000afb0  test    ebx, ebx
0x18000afb2  jle     loc_18000B0D2
0x18000afb8  movzx   ebx, bx
0x18000afbb  or      ebx, edi
0x18000afbd  jmp     loc_18000B0D2
0x18000afc2  mov     rcx, [r14]; Str
0x18000afc5  mov     edx, 2Eh ; '.'; Ch
0x18000afca  call    cs:__imp_wcsrchr
0x18000afd1  nop     dword ptr [rax+rax+00h]
0x18000afd6  mov     r15, rax
0x18000afd9  test    rax, rax
0x18000afdc  jnz     short loc_18000AFFF
0x18000afde  mov     ebx, 8007000Dh
0x18000afe3  lea     r8, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x18000afea  mov     ecx, ebx
0x18000afec  mov     r9d, 89h
0x18000aff2  call    ElValidateHr_5
0x18000aff7  test    eax, eax
0x18000aff9  js      loc_18000B0D2
0x18000afff  mov     [r15], r12w
0x18000b003  lea     r8, [rsp+58h+arg_0]
0x18000b008  mov     rcx, [r14]
0x18000b00b  lea     rdx, aUnattend; "Unattend"
0x18000b012  call    cs:__imp_ConcatenatePaths
0x18000b019  nop     dword ptr [rax+rax+00h]
0x18000b01e  mov     ecx, eax
0x18000b020  mov     r9d, 95h
0x18000b026  mov     ebx, eax
0x18000b028  call    ElValidateWin32_4
0x18000b02d  test    eax, eax
0x18000b02f  jnz     loc_18000AFB0
0x18000b035  mov     rcx, [rsp+58h+arg_0]
0x18000b03a  lea     r8, [rsi+68h]
0x18000b03e  lea     rdx, aImageunattendX; "ImageUnattend.xml"
0x18000b045  call    cs:__imp_ConcatenatePaths
0x18000b04c  nop     dword ptr [rax+rax+00h]
0x18000b051  mov     ecx, eax
0x18000b053  mov     r9d, 9Bh
0x18000b059  mov     ebx, eax
0x18000b05b  call    ElValidateWin32_4
0x18000b060  test    eax, eax
0x18000b062  jnz     loc_18000AFB0
0x18000b068  mov     eax, [rbp+0]
0x18000b06b  dec     eax
0x18000b06d  test    eax, 0FFFFFFFDh
0x18000b072  jnz     short loc_18000B0B4
0x18000b074  mov     r9, [rsi+58h]
0x18000b078  lea     rax, aPermission; ".permission"
0x18000b07f  lea     rcx, [rsi+70h]
0x18000b083  mov     [rsp+58h+var_38], rax
0x18000b088  lea     r8, aSS_0; "%s%s"
0x18000b08f  xor     edx, edx
0x18000b091  call    cs:__imp_?FormatString@@YAKPEAPEAG_KPEBGZZ; FormatString(ushort * *,unsigned __int64,ushort const *,...)
0x18000b098  nop     dword ptr [rax+rax+00h]
0x18000b09d  mov     ecx, eax
0x18000b09f  mov     r9d, 0A9h
0x18000b0a5  mov     ebx, eax
0x18000b0a7  call    ElValidateWin32_4
0x18000b0ac  test    eax, eax
0x18000b0ae  jnz     loc_18000AFB0
0x18000b0b4  mov     rcx, rsi; this
0x18000b0b7  call    ?Refresh@CImage@@QEAAJXZ; CImage::Refresh(void)
0x18000b0bc  mov     r9d, 0B0h
0x18000b0c2  lea     r8, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x18000b0c9  mov     ecx, eax
0x18000b0cb  mov     ebx, eax
0x18000b0cd  call    ElValidateHr_5
0x18000b0d2  mov     rcx, [rsp+58h+arg_0]
0x18000b0d7  test    rcx, rcx
0x18000b0da  jz      short loc_18000B0E8
0x18000b0dc  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000b0e3  nop     dword ptr [rax+rax+00h]
0x18000b0e8  mov     rbp, [rsp+58h+arg_10]
0x18000b0ed  mov     eax, ebx
0x18000b0ef  mov     rbx, [rsp+58h+arg_8]
0x18000b0f4  add     rsp, 30h
0x18000b0f8  pop     r15
0x18000b0fa  pop     r14
0x18000b0fc  pop     r12
0x18000b0fe  pop     rdi
0x18000b0ff  pop     rsi
0x18000b100  retn
```
