# CContentAnalyzer::CheckImageMime(ushort const *,bool)

- ea: `0x180060f7c`
- end: `0x180061377`
- name: `?CheckImageMime@CContentAnalyzer@@AEAAHPEBG_N@Z`
- size: `1019`
- prototype: `__int64 __fastcall(CContentAnalyzer *__hidden this, PCNZWCH lpString1, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001f9a0`

## callees

- `0x180047740`
- `0x180060f7c`
- `0x180061380`
- `0x1800613e0`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x1800611ca`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x1800611e2`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x1800611ca`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x1800611e2`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNCA` at `0x1800610ac`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNCA` at `0x18006122f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNCA` at `0x1800610ac`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNCA` at `0x18006122f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180060fcc`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180060ff8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180061040`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180061068`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180061090`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180061109`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180061135`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18006119a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180060fcc`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180060ff8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180061040`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180061068`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180061090`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180061109`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180061135`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18006119a`

## pseudocode

```c
__int64 __fastcall CContentAnalyzer::CheckImageMime(LPCSTR *this, PCNZWCH lpString1, char a3)
{
  unsigned int v3; // edi
  const WCHAR *v7; // rbp
  _BYTE *v8; // rax
  const WCHAR *v10; // rax
  CContentAnalyzer *v11; // rcx
  const wchar_t *v12; // rax
  CContentAnalyzer *v13; // rcx
  unsigned int v14; // r8d
  unsigned int v15; // edx
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
      if ( !StrCmpNCA(this[4], &byte_18012E438, 8) && *(_DWORD *)this >= 8u )
      {
        v10 = L"image/x-png";
        goto LABEL_12;
      }
      return v3;
    }
LABEL_15:
    if ( (unsigned int)CContentAnalyzer::IsBMP((CContentAnalyzer *)this) )
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
          if ( !(unsigned int)CContentAnalyzer::MatchDWordAtOffset((CContentAnalyzer *)this, 0x4D4D002Au, 0) )
          {
            v14 = 0;
            v15 = 1229531648;
            goto LABEL_52;
          }
          goto LABEL_23;
        }
      }
      if ( (unsigned int)CContentAnalyzer::MatchDWordAtOffset((CContentAnalyzer *)this, 0x1000000u, 0)
        && (unsigned int)CContentAnalyzer::MatchDWordAtOffset(v11, 0x20454D46u, 0x28u) )
      {
        v12 = L"image/x-emf";
        goto LABEL_32;
      }
      if ( !(unsigned int)CContentAnalyzer::MatchDWordAtOffset((CContentAnalyzer *)this, 0xD7CDC69A, 0) )
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
          if ( !(unsigned int)CContentAnalyzer::MatchDWordAtOffset((CContentAnalyzer *)this, 0x52494646u, 0) )
            return v3;
          v15 = 1464156752;
          goto LABEL_51;
        }
        v7 = L"image/heic";
        if ( (unsigned int)StrCmpIIW(lpString1, L"image/heic") && (unsigned int)StrCmpIIW(lpString1, L"image/heif")
          || !(unsigned int)CContentAnalyzer::MatchDWordAtOffset((CContentAnalyzer *)this, 0x66747970u, 4u) )
        {
          return v3;
        }
        if ( !(unsigned int)CContentAnalyzer::MatchDWordAtOffset(v16, 0x68656963u, 8u) )
        {
          v15 = 1751476600;
LABEL_51:
          v14 = 8;
LABEL_52:
          if ( !(unsigned int)CContentAnalyzer::MatchDWordAtOffset(v13, v15, v14) )
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
  if ( *v8 == 0xFF && v8[1] == 0xD8 )
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
0x180060f7c  push    rbx
0x180060f7e  push    rbp
0x180060f7f  push    rsi
0x180060f80  push    rdi
0x180060f81  push    r12
0x180060f83  push    r13
0x180060f85  push    r14
0x180060f87  push    r15
0x180060f89  sub     rsp, 38h
0x180060f8d  xor     edi, edi
0x180060f8f  or      r15d, 0FFFFFFFFh
0x180060f93  mov     r14b, r8b
0x180060f96  mov     rsi, rdx
0x180060f99  mov     rbx, rcx
0x180060f9c  mov     r12d, 1001h
0x180060fa2  lea     r13d, [rdi+7Fh]
0x180060fa6  test    rdx, rdx
0x180060fa9  jz      loc_1800610D7
0x180060faf  mov     r8, rdx; lpString1
0x180060fb2  mov     [rsp+78h+cchCount2], r15d; cchCount2
0x180060fb7  lea     rbp, aImageGif; "image/gif"
0x180060fbe  mov     edx, r12d; dwCmpFlags
0x180060fc1  mov     r9d, r15d; cchCount1
0x180060fc4  mov     [rsp+78h+lpString2], rbp; lpString2
0x180060fc9  mov     ecx, r13d; Locale
0x180060fcc  call    cs:__imp_CompareStringW
0x180060fd2  add     eax, 0FFFFFFFEh
0x180060fd5  jz      loc_1800611B7
0x180060fdb  lea     rax, aImagePjpeg; "image/pjpeg"
0x180060fe2  mov     [rsp+78h+cchCount2], r15d; cchCount2
0x180060fe7  mov     r9d, r15d; cchCount1
0x180060fea  mov     [rsp+78h+lpString2], rax; lpString2
0x180060fef  mov     r8, rsi; lpString1
0x180060ff2  mov     edx, r12d; dwCmpFlags
0x180060ff5  mov     ecx, r13d; Locale
0x180060ff8  call    cs:__imp_CompareStringW
0x180060ffe  lea     rbp, aImageJpeg; "image/jpeg"
0x180061005  add     eax, 0FFFFFFFEh
0x180061008  jnz     short loc_18006102A
0x18006100a  mov     rax, [rbx+20h]
0x18006100e  cmp     byte ptr [rax], 0FFh
0x180061011  jz      loc_1800611F2
0x180061017  mov     eax, edi
0x180061019  add     rsp, 38h
0x18006101d  pop     r15
0x18006101f  pop     r14
0x180061021  pop     r13
0x180061023  pop     r12
0x180061025  pop     rdi
0x180061026  pop     rsi
0x180061027  pop     rbp
0x180061028  pop     rbx
0x180061029  retn
0x18006102a  mov     [rsp+78h+cchCount2], r15d; cchCount2
0x18006102f  mov     r9d, r15d; cchCount1
0x180061032  mov     r8, rsi; lpString1
0x180061035  mov     [rsp+78h+lpString2], rbp; lpString2
0x18006103a  mov     edx, r12d; dwCmpFlags
0x18006103d  mov     ecx, r13d; Locale
0x180061040  call    cs:__imp_CompareStringW
0x180061046  add     eax, 0FFFFFFFEh
0x180061049  jz      short loc_18006100A
0x18006104b  lea     rax, aImageXPng; "image/x-png"
0x180061052  mov     [rsp+78h+cchCount2], r15d; cchCount2
0x180061057  mov     r9d, r15d; cchCount1
0x18006105a  mov     [rsp+78h+lpString2], rax; lpString2
0x18006105f  mov     r8, rsi; lpString1
0x180061062  mov     edx, r12d; dwCmpFlags
0x180061065  mov     ecx, r13d; Locale
0x180061068  call    cs:__imp_CompareStringW
0x18006106e  lea     rbp, aImagePng_0; "image/png"
0x180061075  add     eax, 0FFFFFFFEh
0x180061078  jz      short loc_18006109B
0x18006107a  mov     [rsp+78h+cchCount2], r15d; cchCount2
0x18006107f  mov     r9d, r15d; cchCount1
0x180061082  mov     r8, rsi; lpString1
0x180061085  mov     [rsp+78h+lpString2], rbp; lpString2
0x18006108a  mov     edx, r12d; dwCmpFlags
0x18006108d  mov     ecx, r13d; Locale
0x180061090  call    cs:__imp_CompareStringW
0x180061096  add     eax, 0FFFFFFFEh
0x180061099  jnz     short loc_1800610D7
0x18006109b  mov     rcx, [rbx+20h]; pszStr1
0x18006109f  lea     rdx, byte_18012E438; pszStr2
0x1800610a6  mov     r8d, 8; nChar
0x1800610ac  call    cs:__imp_StrCmpNCA
0x1800610b2  test    eax, eax
0x1800610b4  jnz     loc_180061017
0x1800610ba  cmp     dword ptr [rbx], 8
0x1800610bd  jb      loc_180061017
0x1800610c3  lea     rax, aImageXPng; "image/x-png"
0x1800610ca  test    byte ptr [rbx+40h], 20h
0x1800610ce  cmovz   rbp, rax
0x1800610d2  jmp     loc_1800611A9
0x1800610d7  mov     rcx, rbx; this
0x1800610da  call    ?IsBMP@CContentAnalyzer@@AEAAHXZ; CContentAnalyzer::IsBMP(void)
0x1800610df  test    eax, eax
0x1800610e1  jnz     loc_180061208
0x1800610e7  test    rsi, rsi
0x1800610ea  jz      short loc_180061144
0x1800610ec  lea     rbp, aImageVndMsPhot; "image/vnd.ms-photo"
0x1800610f3  mov     [rsp+78h+cchCount2], r15d; cchCount2
0x1800610f8  mov     r9d, r15d; cchCount1
0x1800610fb  mov     [rsp+78h+lpString2], rbp; lpString2
0x180061100  mov     r8, rsi; lpString1
0x180061103  mov     edx, r12d; dwCmpFlags
0x180061106  mov     ecx, r13d; Locale
0x180061109  call    cs:__imp_CompareStringW
0x18006110f  add     eax, 0FFFFFFFEh
0x180061112  jz      loc_18006121E
0x180061118  lea     rbp, aImageTiff; "image/tiff"
0x18006111f  mov     [rsp+78h+cchCount2], r15d; cchCount2
0x180061124  mov     r9d, r15d; cchCount1
0x180061127  mov     [rsp+78h+lpString2], rbp; lpString2
0x18006112c  mov     r8, rsi; lpString1
0x18006112f  mov     edx, r12d; dwCmpFlags
0x180061132  mov     ecx, r13d; Locale
0x180061135  call    cs:__imp_CompareStringW
0x18006113b  add     eax, 0FFFFFFFEh
0x18006113e  jz      loc_180061250
0x180061144  xor     r8d, r8d; unsigned int
0x180061147  mov     edx, 1000000h; unsigned int
0x18006114c  mov     rcx, rbx; this
0x18006114f  call    ?MatchDWordAtOffset@CContentAnalyzer@@AEAAHKI@Z; CContentAnalyzer::MatchDWordAtOffset(ulong,uint)
0x180061154  test    eax, eax
0x180061156  jnz     loc_180061275
0x18006115c  xor     r8d, r8d; unsigned int
0x18006115f  mov     edx, 0D7CDC69Ah; unsigned int
0x180061164  mov     rcx, rbx; this
0x180061167  call    ?MatchDWordAtOffset@CContentAnalyzer@@AEAAHKI@Z; CContentAnalyzer::MatchDWordAtOffset(ulong,uint)
0x18006116c  test    eax, eax
0x18006116e  jnz     loc_180061211
0x180061174  test    rsi, rsi
0x180061177  jz      loc_180061296
0x18006117d  lea     rbp, aImageVndMsDds; "image/vnd.ms-dds"
0x180061184  mov     [rsp+78h+cchCount2], r15d; cchCount2
0x180061189  mov     r9d, r15d; cchCount1
0x18006118c  mov     [rsp+78h+lpString2], rbp; lpString2
0x180061191  mov     r8, rsi; lpString1
0x180061194  mov     edx, r12d; dwCmpFlags
0x180061197  mov     ecx, r13d; Locale
0x18006119a  call    cs:__imp_CompareStringW
0x1800611a0  add     eax, 0FFFFFFFEh
0x1800611a3  jnz     loc_180061296
0x1800611a9  mov     [rbx+38h], rbp
0x1800611ad  mov     edi, 1
0x1800611b2  jmp     loc_180061017
0x1800611b7  mov     rcx, [rbx+20h]; pszStr1
0x1800611bb  lea     rdx, aGif87; "GIF87"
0x1800611c2  mov     esi, 5
0x1800611c7  mov     r8d, esi; nChar
0x1800611ca  call    cs:__imp_StrCmpNICA
0x1800611d0  test    eax, eax
0x1800611d2  jz      short loc_1800611A9
0x1800611d4  mov     rcx, [rbx+20h]; pszStr1
0x1800611d8  lea     rdx, aGif89; "GIF89"
0x1800611df  mov     r8d, esi; nChar
0x1800611e2  call    cs:__imp_StrCmpNICA
0x1800611e8  test    eax, eax
0x1800611ea  jnz     loc_180061017
0x1800611f0  jmp     short loc_1800611A9
0x1800611f2  cmp     byte ptr [rax+1], 0D8h
0x1800611f6  jnz     loc_180061017
0x1800611fc  lea     rax, aImagePjpeg; "image/pjpeg"
0x180061203  jmp     loc_1800610CA
0x180061208  lea     rax, aImageBmp; "image/bmp"
0x18006120f  jmp     short loc_180061218
0x180061211  lea     rax, aImageXWmf; "image/x-wmf"
0x180061218  mov     [rbx+38h], rax
0x18006121c  jmp     short loc_1800611AD
0x18006121e  mov     rcx, [rbx+20h]; pszStr1
0x180061222  lea     rdx, aIi; "II"
0x180061229  mov     r8d, 3; nChar
0x18006122f  call    cs:__imp_StrCmpNCA
0x180061235  test    eax, eax
0x180061237  jnz     loc_180061017
0x18006123d  mov     rax, [rbx+20h]
0x180061241  cmp     byte ptr [rax+3], 1
0x180061245  ja      loc_180061017
0x18006124b  jmp     loc_1800611A9
0x180061250  xor     r8d, r8d; unsigned int
0x180061253  mov     edx, 4D4D002Ah; unsigned int
0x180061258  mov     rcx, rbx; this
0x18006125b  call    ?MatchDWordAtOffset@CContentAnalyzer@@AEAAHKI@Z; CContentAnalyzer::MatchDWordAtOffset(ulong,uint)
0x180061260  test    eax, eax
0x180061262  jnz     loc_1800611A9
0x180061268  xor     r8d, r8d
0x18006126b  mov     edx, 49492A00h
0x180061270  jmp     loc_180061365
0x180061275  mov     edx, 20454D46h; unsigned int
0x18006127a  mov     r8d, 28h ; '('; unsigned int
0x180061280  call    ?MatchDWordAtOffset@CContentAnalyzer@@AEAAHKI@Z; CContentAnalyzer::MatchDWordAtOffset(ulong,uint)
0x180061285  test    eax, eax
0x180061287  jz      loc_18006115C
0x18006128d  lea     rax, aImageXEmf; "image/x-emf"
0x180061294  jmp     short loc_180061218
0x180061296  lea     rbp, aImageXIcon; "image/x-icon"
0x18006129d  mov     rcx, rsi; lpString1
0x1800612a0  mov     rdx, rbp; lpString2
0x1800612a3  call    ?StrCmpIIW@@YAHPEBG0@Z; StrCmpIIW(ushort const *,ushort const *)
0x1800612a8  test    eax, eax
0x1800612aa  jnz     short loc_1800612BC
0x1800612ac  xor     r8d, r8d
0x1800612af  mov     edx, 100h
0x1800612b4  mov     rcx, rbx
0x1800612b7  jmp     loc_180061365
0x1800612bc  test    r14b, r14b
0x1800612bf  jz      loc_180061017
0x1800612c5  lea     rbp, aImageWebp_0; "image/webp"
0x1800612cc  mov     rcx, rsi; lpString1
0x1800612cf  mov     rdx, rbp; lpString2
0x1800612d2  call    ?StrCmpIIW@@YAHPEBG0@Z; StrCmpIIW(ushort const *,ushort const *)
0x1800612d7  test    eax, eax
0x1800612d9  jnz     short loc_1800612FA
0x1800612db  xor     r8d, r8d; unsigned int
0x1800612de  mov     edx, 52494646h; unsigned int
0x1800612e3  mov     rcx, rbx; this
0x1800612e6  call    ?MatchDWordAtOffset@CContentAnalyzer@@AEAAHKI@Z; CContentAnalyzer::MatchDWordAtOffset(ulong,uint)
0x1800612eb  test    eax, eax
0x1800612ed  jz      loc_180061017
0x1800612f3  mov     edx, 57454250h
0x1800612f8  jmp     short loc_18006135F
0x1800612fa  lea     rbp, aImageHeic_0; "image/heic"
0x180061301  mov     rcx, rsi; lpString1
0x180061304  mov     rdx, rbp; lpString2
0x180061307  call    ?StrCmpIIW@@YAHPEBG0@Z; StrCmpIIW(ushort const *,ushort const *)
0x18006130c  test    eax, eax
0x18006130e  jz      short loc_180061327
0x180061310  lea     rdx, aImageHeif_0; "image/heif"
0x180061317  mov     rcx, rsi; lpString1
0x18006131a  call    ?StrCmpIIW@@YAHPEBG0@Z; StrCmpIIW(ushort const *,ushort const *)
0x18006131f  test    eax, eax
0x180061321  jnz     loc_180061017
0x180061327  mov     edx, 66747970h; unsigned int
0x18006132c  mov     r8d, 4; unsigned int
0x180061332  mov     rcx, rbx; this
0x180061335  call    ?MatchDWordAtOffset@CContentAnalyzer@@AEAAHKI@Z; CContentAnalyzer::MatchDWordAtOffset(ulong,uint)
0x18006133a  test    eax, eax
0x18006133c  jz      loc_180061017
0x180061342  mov     edx, 68656963h; unsigned int
0x180061347  mov     r8d, 8; unsigned int
0x18006134d  call    ?MatchDWordAtOffset@CContentAnalyzer@@AEAAHKI@Z; CContentAnalyzer::MatchDWordAtOffset(ulong,uint)
0x180061352  test    eax, eax
0x180061354  jnz     loc_1800611A9
0x18006135a  mov     edx, 68656978h; unsigned int
0x18006135f  mov     r8d, 8; unsigned int
0x180061365  call    ?MatchDWordAtOffset@CContentAnalyzer@@AEAAHKI@Z; CContentAnalyzer::MatchDWordAtOffset(ulong,uint)
0x18006136a  test    eax, eax
0x18006136c  jz      loc_180061017
0x180061372  jmp     loc_1800611A9
```
