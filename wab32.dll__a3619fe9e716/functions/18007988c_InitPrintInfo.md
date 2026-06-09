# _InitPrintInfo

- ea: `0x18007988c`
- end: `0x180079b5a`
- name: `_InitPrintInfo`
- size: `718`
- prototype: `__int64 __usercall@<rax>(HDC hdc@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180077e60`

## callees

- `0x1800045e4`
- `0x180009428`
- `0x18007988c`
- `0x180091eaa`
- `0x180091ef0`

## import_xrefs

- `GDI32!CreateFontIndirectW` at `0x180079a38`
- `GDI32!CreateFontIndirectW` at `0x180079a8f`
- `GDI32!CreateFontIndirectW` at `0x180079aa0`
- `GDI32!CreateFontIndirectW` at `0x180079a38`
- `GDI32!CreateFontIndirectW` at `0x180079a8f`
- `GDI32!CreateFontIndirectW` at `0x180079aa0`
- `GDI32!GetDeviceCaps` at `0x180079907`
- `GDI32!GetDeviceCaps` at `0x180079919`
- `GDI32!GetDeviceCaps` at `0x18007993d`
- `GDI32!GetDeviceCaps` at `0x18007995c`
- `GDI32!GetDeviceCaps` at `0x180079907`
- `GDI32!GetDeviceCaps` at `0x180079919`
- `GDI32!GetDeviceCaps` at `0x18007993d`
- `GDI32!GetDeviceCaps` at `0x18007995c`
- `GDI32!GetTextExtentPointW` at `0x180079b03`
- `GDI32!GetTextExtentPointW` at `0x180079b03`
- `GDI32!SelectObject` at `0x180079adc`
- `GDI32!SelectObject` at `0x180079b1a`
- `GDI32!SelectObject` at `0x180079adc`
- `GDI32!SelectObject` at `0x180079b1a`
- `KERNEL32!MulDiv` at `0x180079981`
- `KERNEL32!MulDiv` at `0x180079999`
- `KERNEL32!MulDiv` at `0x1800799c2`
- `KERNEL32!MulDiv` at `0x1800799d5`
- `KERNEL32!MulDiv` at `0x180079981`
- `KERNEL32!MulDiv` at `0x180079999`
- `KERNEL32!MulDiv` at `0x1800799c2`
- `KERNEL32!MulDiv` at `0x1800799d5`
- `USER32!LoadStringW` at `0x180079a2e`
- `USER32!LoadStringW` at `0x180079a85`
- `USER32!LoadStringW` at `0x180079a2e`
- `USER32!LoadStringW` at `0x180079a85`

## pseudocode

```c
__int64 __fastcall InitPrintInfo(HDC hdc, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  int DeviceCaps; // eax
  HDC v10; // rcx
  int v11; // eax
  int v12; // eax
  int v13; // ebx
  int v14; // eax
  int v15; // eax
  int v16; // edx
  int v17; // eax
  int v18; // edx
  int v19; // eax
  int v20; // edx
  int v21; // eax
  int v22; // edx
  LONG v23; // edx
  int v24; // ecx
  HFONT v25; // rax
  HGDIOBJ v26; // rbx
  __int64 v27; // r8
  HDC v28; // rcx
  unsigned int v29; // ecx
  struct tagSIZE sz; // [rsp+20h] [rbp-81h] BYREF
  LOGFONTW lf; // [rsp+30h] [rbp-71h] BYREF
  WCHAR String[20]; // [rsp+90h] [rbp-11h] BYREF

  sz = 0;
  memset_0(&lf, 0, sizeof(lf));
  *(_QWORD *)(a5 + 144) = a3;
  *(_QWORD *)(a5 + 136) = FAbortProc;
  *(_QWORD *)a5 = hdc;
  *(_QWORD *)(a5 + 152) = a2;
  *(_QWORD *)(a5 + 160) = a4;
  DeviceCaps = GetDeviceCaps(hdc, 8);
  v10 = *(HDC *)a5;
  *(_DWORD *)(a5 + 32) = DeviceCaps;
  v11 = GetDeviceCaps(v10, 10);
  *(_DWORD *)(a5 + 36) = v11;
  if ( *(_DWORD *)(a5 + 32) && v11 )
  {
    v12 = GetDeviceCaps(*(HDC *)a5, 88);
    *(_DWORD *)(a5 + 24) = v12;
    v13 = 300;
    if ( !v12 )
      *(_DWORD *)(a5 + 24) = 300;
    v14 = GetDeviceCaps(*(HDC *)a5, 90);
    *(_DWORD *)(a5 + 28) = v14;
    if ( v14 )
      v13 = v14;
    else
      *(_DWORD *)(a5 + 28) = 300;
    v15 = MulDiv(1080, v13, 1440);
    v16 = *(_DWORD *)(a5 + 28);
    *(_DWORD *)(a5 + 12) = v15;
    v17 = MulDiv(720, v16, 1440);
    v18 = *(_DWORD *)(a5 + 36);
    *(_DWORD *)(a5 + 20) = v18 - v17;
    if ( v18 - v17 < *(_DWORD *)(a5 + 12) )
    {
      *(_DWORD *)(a5 + 12) = 0;
      *(_DWORD *)(a5 + 20) = v18;
    }
    v19 = MulDiv(720, *(_DWORD *)(a5 + 24), 1440);
    v20 = *(_DWORD *)(a5 + 24);
    *(_DWORD *)(a5 + 8) = v19;
    v21 = MulDiv(720, v20, 1440);
    v22 = *(_DWORD *)(a5 + 32);
    *(_DWORD *)(a5 + 16) = v22 - v21;
    if ( v22 - v21 < *(_DWORD *)(a5 + 8) )
    {
      *(_DWORD *)(a5 + 8) = 0;
      *(_DWORD *)(a5 + 16) = v22;
    }
    lf.lfCharSet = 1;
    v23 = *(_DWORD *)(a5 + 28) / -6;
    lf.lfWeight = 700;
    lf.lfHeight = v23;
    LoadStringW(hinstMapiX, 0x10B8u, lf.lfFaceName, 32);
    *(_QWORD *)(a5 + 112) = CreateFontIndirectW(&lf);
    memset_0(&lf, 0, sizeof(lf));
    v24 = -10 * *(_DWORD *)(a5 + 28);
    lf.lfWeight = 400;
    lf.lfCharSet = 1;
    lf.lfHeight = v24 / 72;
    LoadStringW(hinstMapiX, 0x10B8u, lf.lfFaceName, 32);
    v25 = CreateFontIndirectW(&lf);
    lf.lfWeight = 700;
    *(_QWORD *)(a5 + 120) = v25;
    *(_QWORD *)(a5 + 128) = CreateFontIndirectW(&lf);
    StringCchCopyW((unsigned __int16 *)(a5 + 68), 0x14u, L"%d");
    StringCchPrintfW(String, 0x14u, (const unsigned __int16 *)(a5 + 68), *(unsigned int *)(a5 + 60), sz);
    v26 = SelectObject(*(HDC *)a5, *(HGDIOBJ *)(a5 + 120));
    v27 = -1;
    do
      ++v27;
    while ( String[v27] );
    GetTextExtentPointW(*(HDC *)a5, String, v27, &sz);
    v28 = *(HDC *)a5;
    *(_DWORD *)(a5 + 108) = *(_DWORD *)(a5 + 20) - sz.cy;
    SelectObject(v28, v26);
    v29 = 0;
    if ( *(_DWORD *)(a5 + 108) < *(_DWORD *)(a5 + 12) )
      return (unsigned int)-2147467259;
  }
  else
  {
    return (unsigned int)-2147467259;
  }
  return v29;
}

```

## disassembly

```asm
0x18007988c  push    rbp
0x18007988e  push    rbx
0x18007988f  push    rsi
0x180079890  push    rdi
0x180079891  push    r12
0x180079893  push    r14
0x180079895  push    r15
0x180079897  lea     rbp, [rsp-1Fh]
0x18007989c  sub     rsp, 0C0h
0x1800798a3  mov     rax, cs:__security_cookie
0x1800798aa  xor     rax, rsp
0x1800798ad  mov     [rbp+4Fh+var_38], rax
0x1800798b1  mov     r15, [rbp+4Fh+arg_20]
0x1800798b5  xor     r12d, r12d
0x1800798b8  mov     rbx, r8
0x1800798bb  mov     qword ptr [rsp+0F0h+sz.cx], r12
0x1800798c0  mov     rdi, rdx
0x1800798c3  mov     r14, rcx
0x1800798c6  xor     edx, edx; Val
0x1800798c8  lea     rcx, [rbp+4Fh+lf]; void *
0x1800798cc  lea     r8d, [r12+5Ch]; Size
0x1800798d1  mov     rsi, r9
0x1800798d4  call    memset_0
0x1800798d9  lea     rax, ?FAbortProc@@YAHPEAUHDC__@@H@Z; FAbortProc(HDC__ *,int)
0x1800798e0  mov     [r15+90h], rbx
0x1800798e7  lea     edx, [r12+8]; index
0x1800798ec  mov     [r15+88h], rax
0x1800798f3  mov     rcx, r14; hdc
0x1800798f6  mov     [r15], r14
0x1800798f9  mov     [r15+98h], rdi
0x180079900  mov     [r15+0A0h], rsi
0x180079907  call    cs:__imp_GetDeviceCaps
0x18007990d  mov     rcx, [r15]; hdc
0x180079910  lea     edx, [r12+0Ah]; index
0x180079915  mov     [r15+20h], eax
0x180079919  call    cs:__imp_GetDeviceCaps
0x18007991f  mov     [r15+24h], eax
0x180079923  cmp     [r15+20h], r12d
0x180079927  jz      loc_180079B35
0x18007992d  test    eax, eax
0x18007992f  jz      loc_180079B35
0x180079935  mov     rcx, [r15]; hdc
0x180079938  lea     edx, [r12+58h]; index
0x18007993d  call    cs:__imp_GetDeviceCaps
0x180079943  mov     [r15+18h], eax
0x180079947  mov     ebx, 12Ch
0x18007994c  test    eax, eax
0x18007994e  jnz     short loc_180079954
0x180079950  mov     [r15+18h], ebx
0x180079954  mov     rcx, [r15]; hdc
0x180079957  mov     edx, 5Ah ; 'Z'; index
0x18007995c  call    cs:__imp_GetDeviceCaps
0x180079962  mov     [r15+1Ch], eax
0x180079966  test    eax, eax
0x180079968  jnz     short loc_180079970
0x18007996a  mov     [r15+1Ch], ebx
0x18007996e  jmp     short loc_180079972
0x180079970  mov     ebx, eax
0x180079972  mov     edi, 5A0h
0x180079977  mov     edx, ebx; nNumerator
0x180079979  mov     r8d, edi; nDenominator
0x18007997c  mov     ecx, 438h; nNumber
0x180079981  call    cs:__imp_MulDiv
0x180079987  mov     edx, [r15+1Ch]; nNumerator
0x18007998b  mov     ebx, 2D0h
0x180079990  mov     ecx, ebx; nNumber
0x180079992  mov     [r15+0Ch], eax
0x180079996  mov     r8d, edi; nDenominator
0x180079999  call    cs:__imp_MulDiv
0x18007999f  mov     edx, [r15+24h]
0x1800799a3  mov     ecx, edx
0x1800799a5  sub     ecx, eax
0x1800799a7  mov     [r15+14h], ecx
0x1800799ab  cmp     ecx, [r15+0Ch]
0x1800799af  jge     short loc_1800799B9
0x1800799b1  mov     [r15+0Ch], r12d
0x1800799b5  mov     [r15+14h], edx
0x1800799b9  mov     edx, [r15+18h]; nNumerator
0x1800799bd  mov     r8d, edi; nDenominator
0x1800799c0  mov     ecx, ebx; nNumber
0x1800799c2  call    cs:__imp_MulDiv
0x1800799c8  mov     edx, [r15+18h]; nNumerator
0x1800799cc  mov     r8d, edi; nDenominator
0x1800799cf  mov     ecx, ebx; nNumber
0x1800799d1  mov     [r15+8], eax
0x1800799d5  call    cs:__imp_MulDiv
0x1800799db  mov     edx, [r15+20h]
0x1800799df  mov     ecx, edx
0x1800799e1  sub     ecx, eax
0x1800799e3  mov     [r15+10h], ecx
0x1800799e7  cmp     ecx, [r15+8]
0x1800799eb  jge     short loc_1800799F5
0x1800799ed  mov     [r15+8], r12d
0x1800799f1  mov     [r15+10h], edx
0x1800799f5  mov     rcx, cs:hinstMapiX; hInstance
0x1800799fc  lea     r8, [rbp+4Fh+lf.lfFaceName]; lpBuffer
0x180079a00  mov     eax, 0D5555555h
0x180079a05  mov     [rbp+4Fh+lf.lfCharSet], 1
0x180079a09  imul    dword ptr [r15+1Ch]
0x180079a0d  mov     edi, 20h ; ' '
0x180079a12  mov     ebx, 10B8h
0x180079a17  mov     eax, edx
0x180079a19  mov     esi, 2BCh
0x180079a1e  shr     eax, 1Fh
0x180079a21  mov     r9d, edi; cchBufferMax
0x180079a24  add     edx, eax
0x180079a26  mov     [rbp+4Fh+lf.lfWeight], esi
0x180079a29  mov     [rbp+4Fh+lf.lfHeight], edx
0x180079a2c  mov     edx, ebx; uID
0x180079a2e  call    cs:__imp_LoadStringW
0x180079a34  lea     rcx, [rbp+4Fh+lf]; lplf
0x180079a38  call    cs:__imp_CreateFontIndirectW
0x180079a3e  xor     edx, edx; Val
0x180079a40  lea     r8d, [rdi+3Ch]; Size
0x180079a44  lea     rcx, [rbp+4Fh+lf]; void *
0x180079a48  mov     [r15+70h], rax
0x180079a4c  call    memset_0
0x180079a51  imul    ecx, [r15+1Ch], -0Ah
0x180079a56  lea     r8, [rbp+4Fh+lf.lfFaceName]; lpBuffer
0x180079a5a  mov     eax, 38E38E39h
0x180079a5f  mov     [rbp+4Fh+lf.lfWeight], 190h
0x180079a66  mov     r9d, edi; cchBufferMax
0x180079a69  mov     [rbp+4Fh+lf.lfCharSet], 1
0x180079a6d  imul    ecx
0x180079a6f  mov     rcx, cs:hinstMapiX; hInstance
0x180079a76  sar     edx, 4
0x180079a79  mov     eax, edx
0x180079a7b  shr     eax, 1Fh
0x180079a7e  add     edx, eax
0x180079a80  mov     [rbp+4Fh+lf.lfHeight], edx
0x180079a83  mov     edx, ebx; uID
0x180079a85  call    cs:__imp_LoadStringW
0x180079a8b  lea     rcx, [rbp+4Fh+lf]; lplf
0x180079a8f  call    cs:__imp_CreateFontIndirectW
0x180079a95  lea     rcx, [rbp+4Fh+lf]; lplf
0x180079a99  mov     [rbp+4Fh+lf.lfWeight], esi
0x180079a9c  mov     [r15+78h], rax
0x180079aa0  call    cs:__imp_CreateFontIndirectW
0x180079aa6  lea     ebx, [rdi-0Ch]
0x180079aa9  mov     [r15+80h], rax
0x180079ab0  mov     edx, ebx; unsigned __int64
0x180079ab2  lea     r8, aD; "%d"
0x180079ab9  lea     rcx, [r15+44h]; unsigned __int16 *
0x180079abd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180079ac2  mov     r9d, [r15+3Ch]
0x180079ac6  lea     r8, [r15+44h]; unsigned __int16 *
0x180079aca  mov     edx, ebx; unsigned __int64
0x180079acc  lea     rcx, [rbp+4Fh+String]; unsigned __int16 *
0x180079ad0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180079ad5  mov     rdx, [r15+78h]; h
0x180079ad9  mov     rcx, [r15]; hdc
0x180079adc  call    cs:__imp_SelectObject
0x180079ae2  mov     rbx, rax
0x180079ae5  or      r8, 0FFFFFFFFFFFFFFFFh
0x180079ae9  lea     rax, [rbp+4Fh+String]
0x180079aed  inc     r8; c
0x180079af0  cmp     [rax+r8*2], r12w
0x180079af5  jnz     short loc_180079AED
0x180079af7  mov     rcx, [r15]; hdc
0x180079afa  lea     r9, [rsp+0F0h+sz]; lpsz
0x180079aff  lea     rdx, [rbp+4Fh+String]; lpString
0x180079b03  call    cs:__imp_GetTextExtentPointW
0x180079b09  mov     eax, [r15+14h]
0x180079b0d  mov     rdx, rbx; h
0x180079b10  sub     eax, [rbp+4Fh+sz.cy]
0x180079b13  mov     rcx, [r15]; hdc
0x180079b16  mov     [r15+6Ch], eax
0x180079b1a  call    cs:__imp_SelectObject
0x180079b20  mov     eax, [r15+0Ch]
0x180079b24  mov     ecx, r12d
0x180079b27  cmp     [r15+6Ch], eax
0x180079b2b  mov     edx, 80004005h
0x180079b30  cmovl   ecx, edx
0x180079b33  jmp     short loc_180079B3A
0x180079b35  mov     ecx, 80004005h
0x180079b3a  mov     eax, ecx
0x180079b3c  mov     rcx, [rbp+4Fh+var_38]
0x180079b40  xor     rcx, rsp; StackCookie
0x180079b43  call    __security_check_cookie
0x180079b48  add     rsp, 0C0h
0x180079b4f  pop     r15
0x180079b51  pop     r14
0x180079b53  pop     r12
0x180079b55  pop     rdi
0x180079b56  pop     rsi
0x180079b57  pop     rbx
0x180079b58  pop     rbp
0x180079b59  retn
```
