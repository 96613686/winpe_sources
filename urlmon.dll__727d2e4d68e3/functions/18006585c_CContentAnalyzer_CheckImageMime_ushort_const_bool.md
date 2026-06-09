# CContentAnalyzer::CheckImageMime(ushort const *,bool)

- ea: `0x18006585c`
- end: `0x180065ca3`
- name: `?CheckImageMime@CContentAnalyzer@@AEAAHPEBG_N@Z`
- size: `1095`
- prototype: `__int64 __fastcall(LPCSTR *this, PCNZWCH lpString1, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180026810`

## callees

- `0x1800124b0`
- `0x180065800`
- `0x18006585c`
- `0x180065cac`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x180065ae1`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x180065aff`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x180065ae1`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x180065aff`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNCA` at `0x1800659ab`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNCA` at `0x180065b52`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNCA` at `0x1800659ab`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNCA` at `0x180065b52`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800658ac`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800658de`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18006592d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18006595b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180065989`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180065a0e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180065a40`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180065aab`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800658ac`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800658de`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18006592d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18006595b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180065989`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180065a0e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180065a40`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180065aab`

## pseudocode

```c
__int64 __fastcall CContentAnalyzer::CheckImageMime(LPCSTR *this, PCNZWCH lpString1, char a3)
{
  unsigned int v3; // edi
  const WCHAR *v7; // rbp
  LPCSTR v8; // rax
  const WCHAR *v10; // rax
  CContentAnalyzer *v11; // rcx
  const wchar_t *v12; // rax
  CContentAnalyzer *v13; // rcx
  unsigned int v14; // r8d
  int v15; // edx
  CContentAnalyzer *v16; // rcx

  v3 = 0;
  if ( !lpString1 )
    goto LABEL_15;
  v7 = L"image/gif";
  if ( CompareStringW(0x7Fu, 0x1001u, lpString1, -1, L"image/gif", -1) == 2 )
  {
    if ( StrCmpNICA(this[4], "GIF87", 5) && StrCmpNICA(this[4], "GIF89", 5) )
      return v3;
    goto LABEL_23;
  }
  v7 = L"image/jpeg";
  if ( CompareStringW(0x7Fu, 0x1001u, lpString1, -1, L"image/pjpeg", -1) != 2
    && CompareStringW(0x7Fu, 0x1001u, lpString1, -1, L"image/jpeg", -1) != 2 )
  {
    v7 = L"image/png";
    if ( CompareStringW(0x7Fu, 0x1001u, lpString1, -1, L"image/x-png", -1) == 2
      || CompareStringW(0x7Fu, 0x1001u, lpString1, -1, L"image/png", -1) == 2 )
    {
      if ( !StrCmpNCA(this[4], &byte_18013B4F8, 8) && *(_DWORD *)this >= 8u )
      {
        v10 = L"image/x-png";
        goto LABEL_12;
      }
      return v3;
    }
LABEL_15:
    if ( (unsigned int)CContentAnalyzer::IsBMP(this) )
    {
      v12 = L"image/bmp";
    }
    else
    {
      if ( lpString1 )
      {
        v7 = L"image/vnd.ms-photo";
        if ( CompareStringW(0x7Fu, 0x1001u, lpString1, -1, L"image/vnd.ms-photo", -1) == 2 )
        {
          if ( StrCmpNCA(this[4], aIi, 3) || this[4][3] > 1u )
            return v3;
          goto LABEL_23;
        }
        v7 = L"image/tiff";
        if ( CompareStringW(0x7Fu, 0x1001u, lpString1, -1, L"image/tiff", -1) == 2 )
        {
          if ( !CContentAnalyzer::MatchDWordAtOffset((CContentAnalyzer *)this, 1296891946, 0) )
          {
            v14 = 0;
            v15 = 1229531648;
            goto LABEL_52;
          }
          goto LABEL_23;
        }
      }
      if ( CContentAnalyzer::MatchDWordAtOffset((CContentAnalyzer *)this, 0x1000000, 0)
        && CContentAnalyzer::MatchDWordAtOffset(v11, 541412678, 0x28u) )
      {
        v12 = L"image/x-emf";
        goto LABEL_32;
      }
      if ( !CContentAnalyzer::MatchDWordAtOffset((CContentAnalyzer *)this, -674380134, 0) )
      {
        if ( lpString1 )
        {
          v7 = L"image/vnd.ms-dds";
          if ( CompareStringW(0x7Fu, 0x1001u, lpString1, -1, L"image/vnd.ms-dds", -1) == 2 )
            goto LABEL_23;
        }
        v7 = L"image/x-icon";
        if ( !(unsigned int)StrCmpIIW(lpString1, L"image/x-icon") )
        {
          v14 = 0;
          v15 = 256;
          v13 = (CContentAnalyzer *)this;
          goto LABEL_52;
        }
        if ( !a3 )
          return v3;
        v7 = L"image/webp";
        if ( !(unsigned int)StrCmpIIW(lpString1, L"image/webp") )
        {
          if ( !CContentAnalyzer::MatchDWordAtOffset((CContentAnalyzer *)this, 1380533830, 0) )
            return v3;
          v15 = 1464156752;
          goto LABEL_51;
        }
        v7 = L"image/heic";
        if ( (unsigned int)StrCmpIIW(lpString1, L"image/heic") && (unsigned int)StrCmpIIW(lpString1, L"image/heif")
          || !CContentAnalyzer::MatchDWordAtOffset((CContentAnalyzer *)this, 1718909296, 4u) )
        {
          return v3;
        }
        if ( !CContentAnalyzer::MatchDWordAtOffset(v16, 1751476579, 8u) )
        {
          v15 = 1751476600;
LABEL_51:
          v14 = 8;
LABEL_52:
          if ( !CContentAnalyzer::MatchDWordAtOffset(v13, v15, v14) )
            return v3;
        }
LABEL_23:
        this[7] = (LPCSTR)v7;
        return 1;
      }
      v12 = L"image/x-wmf";
    }
LABEL_32:
    this[7] = (LPCSTR)v12;
    return 1;
  }
  v8 = this[4];
  if ( *v8 == -1 && v8[1] == -40 )
  {
    v10 = L"image/pjpeg";
LABEL_12:
    if ( ((_BYTE)this[8] & 0x20) == 0 )
      v7 = v10;
    goto LABEL_23;
  }
  return v3;
}

```

## disassembly

```asm
0x18006585c  push    rbx
0x18006585e  push    rbp
0x18006585f  push    rsi
0x180065860  push    rdi
0x180065861  push    r12
0x180065863  push    r13
0x180065865  push    r14
0x180065867  push    r15
0x180065869  sub     rsp, 38h
0x18006586d  xor     edi, edi
0x18006586f  or      r15d, 0FFFFFFFFh
0x180065873  mov     r14b, r8b
0x180065876  mov     rsi, rdx
0x180065879  mov     rbx, rcx
0x18006587c  mov     r12d, 1001h
0x180065882  lea     r13d, [rdi+7Fh]
0x180065886  test    rdx, rdx
0x180065889  jz      loc_1800659DC
0x18006588f  mov     r8, rdx; lpString1
0x180065892  mov     [rsp+78h+cchCount2], r15d; cchCount2
0x180065897  lea     rbp, aImageGif; "image/gif"
0x18006589e  mov     edx, r12d; dwCmpFlags
0x1800658a1  mov     r9d, r15d; cchCount1
0x1800658a4  mov     [rsp+78h+lpString2], rbp; lpString2
0x1800658a9  mov     ecx, r13d; Locale
0x1800658ac  call    cs:__imp_CompareStringW
0x1800658b3  nop     dword ptr [rax+rax+00h]
0x1800658b8  add     eax, 0FFFFFFFEh
0x1800658bb  jz      loc_180065ACE
0x1800658c1  lea     rax, aImagePjpeg; "image/pjpeg"
0x1800658c8  mov     [rsp+78h+cchCount2], r15d; cchCount2
0x1800658cd  mov     r9d, r15d; cchCount1
0x1800658d0  mov     [rsp+78h+lpString2], rax; lpString2
0x1800658d5  mov     r8, rsi; lpString1
0x1800658d8  mov     edx, r12d; dwCmpFlags
0x1800658db  mov     ecx, r13d; Locale
0x1800658de  call    cs:__imp_CompareStringW
0x1800658e5  nop     dword ptr [rax+rax+00h]
0x1800658ea  lea     rbp, aImageJpeg; "image/jpeg"
0x1800658f1  add     eax, 0FFFFFFFEh
0x1800658f4  jnz     short loc_180065917
0x1800658f6  mov     rax, [rbx+20h]
0x1800658fa  cmp     byte ptr [rax], 0FFh
0x1800658fd  jz      loc_180065B15
0x180065903  mov     eax, edi
0x180065905  add     rsp, 38h
0x180065909  pop     r15
0x18006590b  pop     r14
0x18006590d  pop     r13
0x18006590f  pop     r12
0x180065911  pop     rdi
0x180065912  pop     rsi
0x180065913  pop     rbp
0x180065914  pop     rbx
0x180065915  retn
0x180065917  mov     [rsp+78h+cchCount2], r15d; cchCount2
0x18006591c  mov     r9d, r15d; cchCount1
0x18006591f  mov     r8, rsi; lpString1
0x180065922  mov     [rsp+78h+lpString2], rbp; lpString2
0x180065927  mov     edx, r12d; dwCmpFlags
0x18006592a  mov     ecx, r13d; Locale
0x18006592d  call    cs:__imp_CompareStringW
0x180065934  nop     dword ptr [rax+rax+00h]
0x180065939  add     eax, 0FFFFFFFEh
0x18006593c  jz      short loc_1800658F6
0x18006593e  lea     rax, aImageXPng; "image/x-png"
0x180065945  mov     [rsp+78h+cchCount2], r15d; cchCount2
0x18006594a  mov     r9d, r15d; cchCount1
0x18006594d  mov     [rsp+78h+lpString2], rax; lpString2
0x180065952  mov     r8, rsi; lpString1
0x180065955  mov     edx, r12d; dwCmpFlags
0x180065958  mov     ecx, r13d; Locale
0x18006595b  call    cs:__imp_CompareStringW
0x180065962  nop     dword ptr [rax+rax+00h]
0x180065967  lea     rbp, aImagePng_0; "image/png"
0x18006596e  add     eax, 0FFFFFFFEh
0x180065971  jz      short loc_18006599A
0x180065973  mov     [rsp+78h+cchCount2], r15d; cchCount2
0x180065978  mov     r9d, r15d; cchCount1
0x18006597b  mov     r8, rsi; lpString1
0x18006597e  mov     [rsp+78h+lpString2], rbp; lpString2
0x180065983  mov     edx, r12d; dwCmpFlags
0x180065986  mov     ecx, r13d; Locale
0x180065989  call    cs:__imp_CompareStringW
0x180065990  nop     dword ptr [rax+rax+00h]
0x180065995  add     eax, 0FFFFFFFEh
0x180065998  jnz     short loc_1800659DC
0x18006599a  mov     rcx, [rbx+20h]; pszStr1
0x18006599e  lea     rdx, byte_18013B4F8; pszStr2
0x1800659a5  mov     r8d, 8; nChar
0x1800659ab  call    cs:__imp_StrCmpNCA
0x1800659b2  nop     dword ptr [rax+rax+00h]
0x1800659b7  test    eax, eax
0x1800659b9  jnz     loc_180065903
0x1800659bf  cmp     dword ptr [rbx], 8
0x1800659c2  jb      loc_180065903
0x1800659c8  lea     rax, aImageXPng; "image/x-png"
0x1800659cf  test    byte ptr [rbx+40h], 20h
0x1800659d3  cmovz   rbp, rax
0x1800659d7  jmp     loc_180065AC0
0x1800659dc  mov     rcx, rbx; this
0x1800659df  call    ?IsBMP@CContentAnalyzer@@AEAAHXZ; CContentAnalyzer::IsBMP(void)
0x1800659e4  test    eax, eax
0x1800659e6  jnz     loc_180065B2B
0x1800659ec  test    rsi, rsi
0x1800659ef  jz      short loc_180065A55
0x1800659f1  lea     rbp, aImageVndMsPhot; "image/vnd.ms-photo"
0x1800659f8  mov     [rsp+78h+cchCount2], r15d; cchCount2
0x1800659fd  mov     r9d, r15d; cchCount1
0x180065a00  mov     [rsp+78h+lpString2], rbp; lpString2
0x180065a05  mov     r8, rsi; lpString1
0x180065a08  mov     edx, r12d; dwCmpFlags
0x180065a0b  mov     ecx, r13d; Locale
0x180065a0e  call    cs:__imp_CompareStringW
0x180065a15  nop     dword ptr [rax+rax+00h]
0x180065a1a  add     eax, 0FFFFFFFEh
0x180065a1d  jz      loc_180065B41
0x180065a23  lea     rbp, aImageTiff; "image/tiff"
0x180065a2a  mov     [rsp+78h+cchCount2], r15d; cchCount2
0x180065a2f  mov     r9d, r15d; cchCount1
0x180065a32  mov     [rsp+78h+lpString2], rbp; lpString2
0x180065a37  mov     r8, rsi; lpString1
0x180065a3a  mov     edx, r12d; dwCmpFlags
0x180065a3d  mov     ecx, r13d; Locale
0x180065a40  call    cs:__imp_CompareStringW
0x180065a47  nop     dword ptr [rax+rax+00h]
0x180065a4c  add     eax, 0FFFFFFFEh
0x180065a4f  jz      loc_180065B79
0x180065a55  xor     r8d, r8d; unsigned int
0x180065a58  mov     edx, 1000000h; unsigned int
0x180065a5d  mov     rcx, rbx; this
0x180065a60  call    ?MatchDWordAtOffset@CContentAnalyzer@@AEAAHKI@Z; CContentAnalyzer::MatchDWordAtOffset(ulong,uint)
0x180065a65  test    eax, eax
0x180065a67  jnz     loc_180065B9E
0x180065a6d  xor     r8d, r8d; unsigned int
0x180065a70  mov     edx, 0D7CDC69Ah; unsigned int
0x180065a75  mov     rcx, rbx; this
0x180065a78  call    ?MatchDWordAtOffset@CContentAnalyzer@@AEAAHKI@Z; CContentAnalyzer::MatchDWordAtOffset(ulong,uint)
0x180065a7d  test    eax, eax
0x180065a7f  jnz     loc_180065B34
0x180065a85  test    rsi, rsi
0x180065a88  jz      loc_180065BC2
0x180065a8e  lea     rbp, aImageVndMsDds; "image/vnd.ms-dds"
0x180065a95  mov     [rsp+78h+cchCount2], r15d; cchCount2
0x180065a9a  mov     r9d, r15d; cchCount1
0x180065a9d  mov     [rsp+78h+lpString2], rbp; lpString2
0x180065aa2  mov     r8, rsi; lpString1
0x180065aa5  mov     edx, r12d; dwCmpFlags
0x180065aa8  mov     ecx, r13d; Locale
0x180065aab  call    cs:__imp_CompareStringW
0x180065ab2  nop     dword ptr [rax+rax+00h]
0x180065ab7  add     eax, 0FFFFFFFEh
0x180065aba  jnz     loc_180065BC2
0x180065ac0  mov     [rbx+38h], rbp
0x180065ac4  mov     edi, 1
0x180065ac9  jmp     loc_180065903
0x180065ace  mov     rcx, [rbx+20h]; pszStr1
0x180065ad2  lea     rdx, aGif87; "GIF87"
0x180065ad9  mov     esi, 5
0x180065ade  mov     r8d, esi; nChar
0x180065ae1  call    cs:__imp_StrCmpNICA
0x180065ae8  nop     dword ptr [rax+rax+00h]
0x180065aed  test    eax, eax
0x180065aef  jz      short loc_180065AC0
0x180065af1  mov     rcx, [rbx+20h]; pszStr1
0x180065af5  lea     rdx, aGif89; "GIF89"
0x180065afc  mov     r8d, esi; nChar
0x180065aff  call    cs:__imp_StrCmpNICA
0x180065b06  nop     dword ptr [rax+rax+00h]
0x180065b0b  test    eax, eax
0x180065b0d  jnz     loc_180065903
0x180065b13  jmp     short loc_180065AC0
0x180065b15  cmp     byte ptr [rax+1], 0D8h
0x180065b19  jnz     loc_180065903
0x180065b1f  lea     rax, aImagePjpeg; "image/pjpeg"
0x180065b26  jmp     loc_1800659CF
0x180065b2b  lea     rax, aImageBmp; "image/bmp"
0x180065b32  jmp     short loc_180065B3B
0x180065b34  lea     rax, aImageXWmf; "image/x-wmf"
0x180065b3b  mov     [rbx+38h], rax
0x180065b3f  jmp     short loc_180065AC4
0x180065b41  mov     rcx, [rbx+20h]; pszStr1
0x180065b45  lea     rdx, aIi; "II"
0x180065b4c  mov     r8d, 3; nChar
0x180065b52  call    cs:__imp_StrCmpNCA
0x180065b59  nop     dword ptr [rax+rax+00h]
0x180065b5e  test    eax, eax
0x180065b60  jnz     loc_180065903
0x180065b66  mov     rax, [rbx+20h]
0x180065b6a  cmp     byte ptr [rax+3], 1
0x180065b6e  ja      loc_180065903
0x180065b74  jmp     loc_180065AC0
0x180065b79  xor     r8d, r8d; unsigned int
0x180065b7c  mov     edx, 4D4D002Ah; unsigned int
0x180065b81  mov     rcx, rbx; this
0x180065b84  call    ?MatchDWordAtOffset@CContentAnalyzer@@AEAAHKI@Z; CContentAnalyzer::MatchDWordAtOffset(ulong,uint)
0x180065b89  test    eax, eax
0x180065b8b  jnz     loc_180065AC0
0x180065b91  xor     r8d, r8d
0x180065b94  mov     edx, 49492A00h
0x180065b99  jmp     loc_180065C91
0x180065b9e  mov     edx, 20454D46h; unsigned int
0x180065ba3  mov     r8d, 28h ; '('; unsigned int
0x180065ba9  call    ?MatchDWordAtOffset@CContentAnalyzer@@AEAAHKI@Z; CContentAnalyzer::MatchDWordAtOffset(ulong,uint)
0x180065bae  test    eax, eax
0x180065bb0  jz      loc_180065A6D
0x180065bb6  lea     rax, aImageXEmf; "image/x-emf"
0x180065bbd  jmp     loc_180065B3B
0x180065bc2  lea     rbp, aImageXIcon; "image/x-icon"
0x180065bc9  mov     rcx, rsi; lpString1
0x180065bcc  mov     rdx, rbp; lpString2
0x180065bcf  call    ?StrCmpIIW@@YAHPEBG0@Z; StrCmpIIW(ushort const *,ushort const *)
0x180065bd4  test    eax, eax
0x180065bd6  jnz     short loc_180065BE8
0x180065bd8  xor     r8d, r8d
0x180065bdb  mov     edx, 100h
0x180065be0  mov     rcx, rbx
0x180065be3  jmp     loc_180065C91
0x180065be8  test    r14b, r14b
0x180065beb  jz      loc_180065903
0x180065bf1  lea     rbp, aImageWebp_0; "image/webp"
0x180065bf8  mov     rcx, rsi; lpString1
0x180065bfb  mov     rdx, rbp; lpString2
0x180065bfe  call    ?StrCmpIIW@@YAHPEBG0@Z; StrCmpIIW(ushort const *,ushort const *)
0x180065c03  test    eax, eax
0x180065c05  jnz     short loc_180065C26
0x180065c07  xor     r8d, r8d; unsigned int
0x180065c0a  mov     edx, 52494646h; unsigned int
0x180065c0f  mov     rcx, rbx; this
0x180065c12  call    ?MatchDWordAtOffset@CContentAnalyzer@@AEAAHKI@Z; CContentAnalyzer::MatchDWordAtOffset(ulong,uint)
0x180065c17  test    eax, eax
0x180065c19  jz      loc_180065903
0x180065c1f  mov     edx, 57454250h
0x180065c24  jmp     short loc_180065C8B
0x180065c26  lea     rbp, aImageHeic_0; "image/heic"
0x180065c2d  mov     rcx, rsi; lpString1
0x180065c30  mov     rdx, rbp; lpString2
0x180065c33  call    ?StrCmpIIW@@YAHPEBG0@Z; StrCmpIIW(ushort const *,ushort const *)
0x180065c38  test    eax, eax
0x180065c3a  jz      short loc_180065C53
0x180065c3c  lea     rdx, aImageHeif_0; "image/heif"
0x180065c43  mov     rcx, rsi; lpString1
0x180065c46  call    ?StrCmpIIW@@YAHPEBG0@Z; StrCmpIIW(ushort const *,ushort const *)
0x180065c4b  test    eax, eax
0x180065c4d  jnz     loc_180065903
0x180065c53  mov     edx, 66747970h; unsigned int
0x180065c58  mov     r8d, 4; unsigned int
0x180065c5e  mov     rcx, rbx; this
0x180065c61  call    ?MatchDWordAtOffset@CContentAnalyzer@@AEAAHKI@Z; CContentAnalyzer::MatchDWordAtOffset(ulong,uint)
0x180065c66  test    eax, eax
0x180065c68  jz      loc_180065903
0x180065c6e  mov     edx, 68656963h; unsigned int
0x180065c73  mov     r8d, 8; unsigned int
0x180065c79  call    ?MatchDWordAtOffset@CContentAnalyzer@@AEAAHKI@Z; CContentAnalyzer::MatchDWordAtOffset(ulong,uint)
0x180065c7e  test    eax, eax
0x180065c80  jnz     loc_180065AC0
0x180065c86  mov     edx, 68656978h; unsigned int
0x180065c8b  mov     r8d, 8; unsigned int
0x180065c91  call    ?MatchDWordAtOffset@CContentAnalyzer@@AEAAHKI@Z; CContentAnalyzer::MatchDWordAtOffset(ulong,uint)
0x180065c96  test    eax, eax
0x180065c98  jz      loc_180065903
0x180065c9e  jmp     loc_180065AC0
```
