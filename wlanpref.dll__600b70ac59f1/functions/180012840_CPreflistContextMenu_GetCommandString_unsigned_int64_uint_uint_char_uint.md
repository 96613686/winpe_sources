# CPreflistContextMenu::GetCommandString(unsigned __int64,uint,uint *,char *,uint)

- ea: `0x180012840`
- end: `0x180012a13`
- name: `?GetCommandString@CPreflistContextMenu@@UEAAJ_KIPEAIPEADI@Z`
- size: `467`
- prototype: `__int64 __fastcall(CPreflistContextMenu *__hidden this, unsigned __int64, unsigned int, unsigned int *, LPSTR, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180011630`
- `0x180012840`
- `0x180012a1c`
- `0x18002d80e`
- `0x18002d840`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180012963`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180012963`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180012920`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180012920`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001296d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001296d`

## pseudocode

```c
__int64 __fastcall CPreflistContextMenu::GetCommandString(
        CPreflistContextMenu *this,
        int a2,
        int a3,
        unsigned int *a4,
        unsigned __int16 *lpMultiByteStr,
        unsigned int cbMultiByte)
{
  unsigned __int16 *v6; // rdi
  __int64 Node; // rax
  __m128i v10; // xmm6
  __m128i v11; // xmm0
  unsigned int v12; // ebx
  unsigned __int16 *v13; // r8
  signed int LastError; // eax
  __int64 v15; // rdx
  __int64 v16; // rcx
  _BYTE *v17; // rax
  unsigned __int16 *v18; // rax
  int v19; // [rsp+40h] [rbp-248h] BYREF
  int v20; // [rsp+44h] [rbp-244h] BYREF
  _BYTE v21[8]; // [rsp+48h] [rbp-240h] BYREF
  WCHAR Buffer[264]; // [rsp+50h] [rbp-238h] BYREF

  v6 = lpMultiByteStr;
  v20 = 0;
  v19 = 0;
  Node = ATL::CAtlMap<unsigned int,ContextMenuItem,ATL::CElementTraits<unsigned int>,ATL::CElementTraits<ContextMenuItem>>::GetNode(
           (_DWORD)this,
           a2,
           (unsigned int)&v20,
           (unsigned int)&v19,
           (__int64)v21);
  if ( !Node )
    return 2147942487LL;
  v10 = *(__m128i *)(Node + 8);
  v11 = *(__m128i *)(Node + 24);
  if ( lpMultiByteStr )
    *(_BYTE *)lpMultiByteStr = 0;
  switch ( a3 )
  {
    case 0:
      v15 = 2147483646;
      v16 = cbMultiByte;
      if ( cbMultiByte - 1 > 0x7FFFFFFE )
      {
        v12 = -2147024809;
        if ( cbMultiByte )
          *(_BYTE *)lpMultiByteStr = 0;
      }
      else
      {
        v17 = (_BYTE *)_mm_srli_si128(v11, 8).m128i_u64[0];
        do
        {
          if ( !v15 )
            break;
          if ( !*v17 )
            break;
          *(_BYTE *)v6 = *v17++;
          v6 = (unsigned __int16 *)((char *)v6 + 1);
          --v15;
          --v16;
        }
        while ( v16 );
        v18 = (unsigned __int16 *)((char *)v6 - 1);
        if ( v16 )
          v18 = v6;
        v12 = v16 == 0 ? 0x8007007A : 0;
        *(_BYTE *)v18 = 0;
      }
      return v12;
    case 1:
      goto LABEL_12;
    case 4:
      v13 = (unsigned __int16 *)v11.m128i_i64[0];
      return (unsigned int)StringCchCopyW(lpMultiByteStr, cbMultiByte, v13);
    case 5:
LABEL_12:
      memset_0(Buffer, 0, 0x208u);
      if ( !LoadStringW(hModule, _mm_cvtsi128_si32(_mm_srli_si128(v10, 8)), Buffer, 260) )
        goto LABEL_15;
      v13 = Buffer;
      if ( a3 == 1 )
      {
        v12 = -2147024809;
        if ( WideCharToMultiByte(0, 0, Buffer, -1, (LPSTR)lpMultiByteStr, cbMultiByte, 0, 0) )
          return v12;
LABEL_15:
        LastError = GetLastError();
        v12 = LastError;
        if ( LastError > 0 )
          return (unsigned __int16)LastError | 0x80070000;
        return v12;
      }
      return (unsigned int)StringCchCopyW(lpMultiByteStr, cbMultiByte, v13);
  }
  return 0;
}

```

## disassembly

```asm
0x180012840  mov     rax, rsp
0x180012843  mov     [rax+8], rbx
0x180012847  push    rdi
0x180012848  sub     rsp, 280h
0x18001284f  movaps  xmmword ptr [rax-18h], xmm6
0x180012853  mov     rax, cs:__security_cookie
0x18001285a  xor     rax, rsp
0x18001285d  mov     [rsp+288h+var_28], rax
0x180012865  mov     rdi, [rsp+288h+arg_20]
0x18001286d  lea     rax, [rsp+288h+var_240]
0x180012872  mov     ebx, r8d
0x180012875  mov     [rsp+288h+lpMultiByteStr], rax
0x18001287a  lea     r8, [rsp+288h+var_244]
0x18001287f  mov     [rsp+288h+var_244], 0
0x180012887  lea     r9, [rsp+288h+var_248]
0x18001288c  mov     [rsp+288h+var_248], 0
0x180012894  call    ?GetNode@?$CAtlMap@IVContextMenuItem@@V?$CElementTraits@I@ATL@@V?$CElementTraits@VContextMenuItem@@@3@@ATL@@AEBAPEAVCNode@12@IAEAI0AEAPEAV312@@Z; ATL::CAtlMap<uint,ContextMenuItem,ATL::CElementTraits<uint>,ATL::CElementTraits<ContextMenuItem>>::GetNode(uint,uint &,uint &,ATL::CAtlMap<uint,ContextMenuItem,ATL::CElementTraits<uint>,ATL::CElementTraits<ContextMenuItem>>::CNode * &)
0x180012899  test    rax, rax
0x18001289c  jnz     short loc_1800128A8
0x18001289e  mov     eax, 80070057h
0x1800128a3  jmp     loc_1800129ED
0x1800128a8  movups  xmm6, xmmword ptr [rax+8]
0x1800128ac  movups  xmm0, xmmword ptr [rax+18h]
0x1800128b0  test    rdi, rdi
0x1800128b3  jz      short loc_1800128B8
0x1800128b5  mov     byte ptr [rdi], 0
0x1800128b8  mov     eax, ebx
0x1800128ba  test    ebx, ebx
0x1800128bc  jz      loc_180012984
0x1800128c2  sub     eax, 1
0x1800128c5  jz      short loc_1800128F3
0x1800128c7  sub     eax, 3
0x1800128ca  jz      short loc_1800128D8
0x1800128cc  cmp     eax, 1
0x1800128cf  jz      short loc_1800128F3
0x1800128d1  xor     ebx, ebx
0x1800128d3  jmp     loc_1800129EB
0x1800128d8  movq    r8, xmm0; unsigned __int16 *
0x1800128dd  mov     edx, [rsp+288h+arg_28]; unsigned __int64
0x1800128e4  mov     rcx, rdi; unsigned __int16 *
0x1800128e7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800128ec  mov     ebx, eax
0x1800128ee  jmp     loc_1800129EB
0x1800128f3  xor     edx, edx; Val
0x1800128f5  lea     rcx, [rsp+288h+Buffer]; void *
0x1800128fa  mov     r8d, 208h; Size
0x180012900  call    memset_0
0x180012905  mov     rcx, cs:hModule; hInstance
0x18001290c  lea     r8, [rsp+288h+Buffer]; lpBuffer
0x180012911  psrldq  xmm6, 8
0x180012916  mov     r9d, 104h; cchBufferMax
0x18001291c  movd    edx, xmm6; uID
0x180012920  call    cs:__imp_LoadStringW
0x180012926  test    eax, eax
0x180012928  jz      short loc_18001296D
0x18001292a  lea     r8, [rsp+288h+Buffer]; lpWideCharStr
0x18001292f  cmp     ebx, 1
0x180012932  jnz     short loc_1800128DD
0x180012934  mov     eax, [rsp+288h+arg_28]
0x18001293b  or      r9d, 0FFFFFFFFh; cchWideChar
0x18001293f  mov     [rsp+288h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180012948  xor     edx, edx; dwFlags
0x18001294a  mov     [rsp+288h+lpDefaultChar], 0; lpDefaultChar
0x180012953  xor     ecx, ecx; CodePage
0x180012955  mov     [rsp+288h+cbMultiByte], eax; cbMultiByte
0x180012959  mov     ebx, 80070057h
0x18001295e  mov     [rsp+288h+lpMultiByteStr], rdi; lpMultiByteStr
0x180012963  call    cs:__imp_WideCharToMultiByte
0x180012969  test    eax, eax
0x18001296b  jnz     short loc_1800129EB
0x18001296d  call    cs:__imp_GetLastError
0x180012973  mov     ebx, eax
0x180012975  test    eax, eax
0x180012977  jle     short loc_1800129EB
0x180012979  movzx   ebx, ax
0x18001297c  or      ebx, 80070000h
0x180012982  jmp     short loc_1800129EB
0x180012984  mov     eax, [rsp+288h+arg_28]
0x18001298b  mov     edx, 7FFFFFFEh
0x180012990  mov     ecx, eax
0x180012992  dec     eax
0x180012994  cmp     eax, edx
0x180012996  ja      short loc_1800129DE
0x180012998  psrldq  xmm0, 8
0x18001299d  movq    rax, xmm0
0x1800129a2  test    rdx, rdx
0x1800129a5  jz      short loc_1800129C1
0x1800129a7  mov     r8b, [rax]
0x1800129aa  test    r8b, r8b
0x1800129ad  jz      short loc_1800129C1
0x1800129af  mov     [rdi], r8b
0x1800129b2  inc     rax
0x1800129b5  inc     rdi
0x1800129b8  dec     rdx
0x1800129bb  sub     rcx, 1
0x1800129bf  jnz     short loc_1800129A2
0x1800129c1  test    rcx, rcx
0x1800129c4  lea     rax, [rdi-1]
0x1800129c8  cmovnz  rax, rdi
0x1800129cc  neg     rcx
0x1800129cf  sbb     ebx, ebx
0x1800129d1  not     ebx
0x1800129d3  and     ebx, 8007007Ah
0x1800129d9  mov     byte ptr [rax], 0
0x1800129dc  jmp     short loc_1800129EB
0x1800129de  mov     ebx, 80070057h
0x1800129e3  test    rcx, rcx
0x1800129e6  jz      short loc_1800129EB
0x1800129e8  mov     byte ptr [rdi], 0
0x1800129eb  mov     eax, ebx
0x1800129ed  mov     rcx, [rsp+288h+var_28]
0x1800129f5  xor     rcx, rsp; StackCookie
0x1800129f8  call    __security_check_cookie
0x1800129fd  lea     r11, [rsp+288h+var_8]
0x180012a05  mov     rbx, [r11+10h]
0x180012a09  movaps  xmm6, xmmword ptr [r11-10h]
0x180012a0e  mov     rsp, r11
0x180012a11  pop     rdi
0x180012a12  retn
```
