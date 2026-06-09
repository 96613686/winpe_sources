# WpCreateProfileSchemaCollectionInternal(IXMLDOMSchemaCollection * *)

- ea: `0x180027f30`
- end: `0x1800283fd`
- name: `?WpCreateProfileSchemaCollectionInternal@@YAKPEAPEAUIXMLDOMSchemaCollection@@@Z`
- size: `1229`
- prototype: `unsigned int __fastcall(struct IXMLDOMSchemaCollection **)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180027c10`
- `0x1801fb5c8`

## callees

- `0x180027f30`
- `0x180106340`
- `0x180107330`
- `0x18022c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002832a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002832a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180027f99`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180027f99`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800280fa`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800280fa`
- `OLEAUT32!__imp_SysAllocString` at `0x1800281b8`
- `OLEAUT32!__imp_SysAllocString` at `0x1800281fd`
- `OLEAUT32!__imp_SysAllocString` at `0x1800281b8`
- `OLEAUT32!__imp_SysAllocString` at `0x1800281fd`
- `OLEAUT32!__imp_SysFreeString` at `0x1800281ac`
- `OLEAUT32!__imp_SysFreeString` at `0x1800281c8`
- `OLEAUT32!__imp_SysFreeString` at `0x180028297`
- `OLEAUT32!__imp_SysFreeString` at `0x1800281ac`
- `OLEAUT32!__imp_SysFreeString` at `0x1800281c8`
- `OLEAUT32!__imp_SysFreeString` at `0x180028297`
- `OLEAUT32!__imp_VariantInit` at `0x180027f70`
- `OLEAUT32!__imp_VariantInit` at `0x180028062`
- `OLEAUT32!__imp_VariantInit` at `0x180027f70`
- `OLEAUT32!__imp_VariantInit` at `0x180028062`
- `OLEAUT32!__imp_VariantClear` at `0x1800281d6`
- `OLEAUT32!__imp_VariantClear` at `0x18002820d`
- `OLEAUT32!__imp_VariantClear` at `0x1800282a2`
- `OLEAUT32!__imp_VariantClear` at `0x1800282c9`
- `OLEAUT32!__imp_VariantClear` at `0x1800281d6`
- `OLEAUT32!__imp_VariantClear` at `0x18002820d`
- `OLEAUT32!__imp_VariantClear` at `0x1800282a2`
- `OLEAUT32!__imp_VariantClear` at `0x1800282c9`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall WpCreateProfileSchemaCollectionInternal(struct IXMLDOMSchemaCollection **a1)
{
  struct IXMLDOMSchemaCollection *v2; // rbx
  UINT SystemWindowsDirectoryW; // eax
  __int64 v4; // r8
  WCHAR *v5; // rax
  unsigned int v6; // edx
  __int64 v7; // r9
  __int64 v8; // rax
  const wchar_t *v9; // rcx
  bool v10; // zf
  __int64 v11; // r8
  WCHAR *v12; // r9
  wchar_t v13; // dx
  WCHAR *v14; // rcx
  OLECHAR *v15; // rdi
  __int64 v16; // rax
  WCHAR *v17; // rcx
  __int64 v18; // rdx
  OLECHAR *v19; // r8
  WCHAR v20; // r9
  DWORD LastError; // esi
  OLECHAR *v22; // rcx
  __int64 v23; // r15
  HRESULT v24; // eax
  unsigned int i; // r14d
  unsigned __int64 v26; // rdx
  OLECHAR *v27; // r8
  __int64 v28; // rcx
  wchar_t *v29; // r9
  wchar_t v30; // ax
  OLECHAR *v31; // rcx
  const OLECHAR *v32; // rsi
  BSTR v33; // rsi
  __m128i v34; // xmm1
  IRecordInfo *pRecInfo; // xmm2_8
  int v36; // eax
  struct IXMLDOMSchemaCollection *v38; // rax
  LPVOID ppv; // [rsp+30h] [rbp-D0h] BYREF
  VARIANTARG v40; // [rsp+38h] [rbp-C8h] BYREF
  __m128i v41; // [rsp+50h] [rbp-B0h] BYREF
  IRecordInfo *v42; // [rsp+60h] [rbp-A0h]
  struct IXMLDOMSchemaCollection *v43; // [rsp+70h] [rbp-90h]
  VARIANTARG pvarg; // [rsp+78h] [rbp-88h] BYREF
  WCHAR Buffer[264]; // [rsp+90h] [rbp-70h] BYREF
  OLECHAR psz[264]; // [rsp+2A0h] [rbp+1A0h] BYREF

  v2 = 0;
  v43 = 0;
  VariantInit(&pvarg);
  memset_0(Buffer, 0, 0x208u);
  *a1 = 0;
  SystemWindowsDirectoryW = GetSystemWindowsDirectoryW(Buffer, 0x104u);
  if ( SystemWindowsDirectoryW )
  {
    if ( SystemWindowsDirectoryW > 0x104 )
    {
      LastError = 122;
    }
    else
    {
      v4 = 260;
      v5 = Buffer;
      do
      {
        if ( !*v5 )
          break;
        ++v5;
        --v4;
      }
      while ( v4 );
      v6 = v4 == 0 ? 0x80070057 : 0;
      v7 = (260 - v4) & -(__int64)(v4 != 0);
      if ( v4 )
      {
        v8 = 2147483646;
        v9 = L"\\L2Schemas\\";
        v11 = 260 - v7;
        v10 = v7 == 260;
        v12 = &Buffer[v7];
        if ( !v10 )
        {
          do
          {
            if ( !v8 )
              break;
            v13 = *v9;
            if ( !*v9 )
              break;
            ++v9;
            *v12++ = v13;
            --v8;
            --v11;
          }
          while ( v11 );
        }
        v6 = v11 == 0 ? 0x8007007A : 0;
        v14 = v12 - 1;
        if ( v11 )
          v14 = v12;
        *v14 = 0;
        if ( v11 )
          goto LABEL_14;
      }
      LastError = (unsigned __int16)v6;
      if ( (v6 & 0x1FFF0000) != 0x70000 )
        LastError = v6;
      if ( !LastError )
      {
LABEL_14:
        ppv = 0;
        VariantInit(&v40);
        v15 = 0;
        v16 = 2147483646;
        v17 = Buffer;
        v18 = 260;
        v19 = psz;
        do
        {
          if ( !v16 )
            break;
          v20 = *v17;
          if ( !*v17 )
            break;
          ++v17;
          *v19++ = v20;
          --v16;
          --v18;
        }
        while ( v18 );
        LastError = v18 == 0 ? 0x8007007A : 0;
        v22 = v19 - 1;
        if ( v18 )
          v22 = v19;
        *v22 = 0;
        if ( v18 || (LastError = (unsigned __int16)LastError, !(_WORD)LastError) )
        {
          v23 = -1;
          do
            ++v23;
          while ( psz[v23] );
          v24 = CoCreateInstance(&CLSID_XMLSchemaCache60, 0, 1u, &IID_IXMLDOMSchemaCollection, &ppv);
          LastError = v24;
          if ( v24 >= 0 )
          {
            LastError = 0;
LABEL_25:
            for ( i = 0; ; ++i )
            {
              if ( i >= 0xA )
              {
                v2 = (struct IXMLDOMSchemaCollection *)ppv;
                ppv = 0;
                v43 = v2;
                goto LABEL_48;
              }
              v26 = 260 - v23;
              v27 = &psz[v23];
              if ( v23 != 260 )
                break;
              LOWORD(LastError) = 87;
              if ( v26 )
                goto LABEL_73;
LABEL_74:
              LastError = (unsigned __int16)LastError;
              if ( (_WORD)LastError )
                goto LABEL_48;
LABEL_36:
              v32 = off_18022D040[2 * i];
              SysFreeString(v15);
              v15 = 0;
              v33 = SysAllocString(v32);
              if ( v33 )
              {
                SysFreeString(0);
                v15 = v33;
              }
              if ( VariantClear(&v40) < 0
                || (v41 = 0,
                    v41.m128i_i16[0] = 8,
                    v41.m128i_i64[1] = (__int64)SysAllocString(psz),
                    VariantClear(&v40) < 0) )
              {
                pRecInfo = v40.pRecInfo;
                v34 = *(__m128i *)&v40.vt;
              }
              else
              {
                v34 = v41;
                *(__m128i *)&v40.vt = v41;
                pRecInfo = 0;
                v40.pRecInfo = 0;
              }
              if ( !v15 || (unsigned __int16)_mm_cvtsi128_si32(v34) != 8 || !_mm_srli_si128(v34, 8).m128i_u64[0] )
              {
                LastError = 8;
                goto LABEL_48;
              }
              v41 = v34;
              v42 = pRecInfo;
              v36 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, __m128i *))(*(_QWORD *)ppv + 56LL))(ppv, v15, &v41);
              LastError = v36;
              if ( v36 < 0 )
              {
                if ( (v36 & 0x1FFF0000) == 0x70000 )
                  LastError = (unsigned __int16)v36;
                if ( LastError )
                  goto LABEL_48;
              }
              else
              {
                LastError = 0;
              }
            }
            if ( v26 <= 0x7FFFFFFF )
            {
              v28 = 2147483646;
              v29 = off_18022D040[2 * i + 1];
              do
              {
                if ( !v28 )
                  break;
                v30 = *v29;
                if ( !*v29 )
                  break;
                ++v29;
                *v27++ = v30;
                --v28;
                --v26;
              }
              while ( v26 );
              LastError = v26 == 0 ? 0x8007007A : 0;
              v31 = v27 - 1;
              if ( v26 )
                v31 = v27;
              *v31 = 0;
              if ( v26 )
                goto LABEL_36;
              goto LABEL_74;
            }
            LOWORD(LastError) = 87;
LABEL_73:
            *v27 = 0;
            goto LABEL_74;
          }
          if ( (v24 & 0x1FFF0000) == 0x70000 )
            LastError = (unsigned __int16)v24;
          if ( !LastError )
            goto LABEL_25;
        }
LABEL_48:
        SysFreeString(v15);
        VariantClear(&v40);
        if ( ppv )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
        if ( !LastError )
        {
          v38 = v2;
          v2 = 0;
          *a1 = v38;
        }
      }
    }
  }
  else
  {
    LastError = GetLastError();
  }
  VariantClear(&pvarg);
  if ( v2 )
    ((void (__fastcall *)(struct IXMLDOMSchemaCollection *))v2->lpVtbl->Release)(v2);
  return LastError;
}

```

## disassembly

```asm
0x180027f30  push    rbp
0x180027f32  push    rbx
0x180027f33  push    rsi
0x180027f34  push    rdi
0x180027f35  push    r12
0x180027f37  push    r13
0x180027f39  push    r14
0x180027f3b  push    r15
0x180027f3d  lea     rbp, [rsp-3C8h]
0x180027f45  sub     rsp, 4C8h
0x180027f4c  mov     rax, cs:__security_cookie
0x180027f53  xor     rax, rsp
0x180027f56  mov     [rbp+400h+var_50], rax
0x180027f5d  mov     r12, rcx
0x180027f60  xor     r13d, r13d
0x180027f63  mov     ebx, r13d
0x180027f66  mov     [rsp+500h+var_490], rbx
0x180027f6b  lea     rcx, [rsp+500h+pvarg]; pvarg
0x180027f70  call    cs:__imp_VariantInit
0x180027f76  nop
0x180027f77  xor     edx, edx; Val
0x180027f79  mov     r8d, 208h; Size
0x180027f7f  lea     rcx, [rbp+400h+Buffer]; void *
0x180027f83  call    memset_0
0x180027f88  mov     [r12], r13
0x180027f8c  mov     r14d, 104h
0x180027f92  mov     edx, r14d; uSize
0x180027f95  lea     rcx, [rbp+400h+Buffer]; lpBuffer
0x180027f99  call    cs:__imp_GetSystemWindowsDirectoryW
0x180027f9f  test    eax, eax
0x180027fa1  jz      loc_18002832A
0x180027fa7  cmp     eax, r14d
0x180027faa  ja      loc_180028341
0x180027fb0  mov     r8d, r14d
0x180027fb3  lea     rax, [rbp+400h+Buffer]
0x180027fb7  cmp     [rax], r13w
0x180027fbb  jz      short loc_180027FC7
0x180027fbd  add     rax, 2
0x180027fc1  sub     r8, 1
0x180027fc5  jnz     short loc_180027FB7
0x180027fc7  mov     rax, r8
0x180027fca  neg     rax
0x180027fcd  sbb     edx, edx
0x180027fcf  not     edx
0x180027fd1  and     edx, 80070057h
0x180027fd7  mov     rax, r8
0x180027fda  mov     rcx, r14
0x180027fdd  sub     rcx, r8
0x180027fe0  neg     rax
0x180027fe3  sbb     r9, r9
0x180027fe6  and     r9, rcx
0x180027fe9  mov     r15d, 1FFF0000h
0x180027fef  test    r8, r8
0x180027ff2  jz      loc_18002834B
0x180027ff8  mov     eax, 7FFFFFFEh
0x180027ffd  lea     rcx, aL2schemas; "\\L2Schemas\\"
0x180028004  mov     r8, r14
0x180028007  sub     r8, r9
0x18002800a  lea     r9, [rbp+r9*2+400h+Buffer]
0x18002800f  jz      short loc_180028033
0x180028011  test    rax, rax
0x180028014  jz      short loc_180028033
0x180028016  movzx   edx, word ptr [rcx]
0x180028019  test    dx, dx
0x18002801c  jz      short loc_180028033
0x18002801e  add     rcx, 2
0x180028022  mov     [r9], dx
0x180028026  add     r9, 2
0x18002802a  dec     rax
0x18002802d  sub     r8, 1
0x180028031  jnz     short loc_180028011
0x180028033  mov     rax, r8
0x180028036  neg     rax
0x180028039  sbb     edx, edx
0x18002803b  not     edx
0x18002803d  and     edx, 8007007Ah
0x180028043  lea     rcx, [r9-2]
0x180028047  test    r8, r8
0x18002804a  cmovnz  rcx, r9
0x18002804e  mov     [rcx], r13w
0x180028052  jz      loc_18002834B
0x180028058  mov     [rsp+500h+var_4D0], r13
0x18002805d  lea     rcx, [rsp+500h+var_4C8]; pvarg
0x180028062  call    cs:__imp_VariantInit
0x180028068  mov     rdi, r13
0x18002806b  mov     eax, 7FFFFFFEh
0x180028070  lea     rcx, [rbp+400h+Buffer]
0x180028074  mov     rdx, r14
0x180028077  lea     r8, [rbp+400h+psz]
0x18002807e  test    rax, rax
0x180028081  jz      short loc_1800280A2
0x180028083  movzx   r9d, word ptr [rcx]
0x180028087  test    r9w, r9w
0x18002808b  jz      short loc_1800280A2
0x18002808d  add     rcx, 2
0x180028091  mov     [r8], r9w
0x180028095  add     r8, 2
0x180028099  dec     rax
0x18002809c  sub     rdx, 1
0x1800280a0  jnz     short loc_18002807E
0x1800280a2  mov     rax, rdx
0x1800280a5  neg     rax
0x1800280a8  sbb     esi, esi
0x1800280aa  not     esi
0x1800280ac  and     esi, 8007007Ah
0x1800280b2  lea     rcx, [r8-2]
0x1800280b6  test    rdx, rdx
0x1800280b9  cmovnz  rcx, r8
0x1800280bd  mov     [rcx], r13w
0x1800280c1  jz      loc_180028368
0x1800280c7  lea     rax, [rbp+400h+psz]
0x1800280ce  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800280d2  inc     r15
0x1800280d5  cmp     [rax+r15*2], r13w
0x1800280da  jnz     short loc_1800280D2
0x1800280dc  lea     rax, [rsp+500h+var_4D0]
0x1800280e1  mov     [rsp+500h+ppv], rax; ppv
0x1800280e6  lea     r9, IID_IXMLDOMSchemaCollection; riid
0x1800280ed  xor     edx, edx; pUnkOuter
0x1800280ef  lea     r8d, [rdx+1]; dwClsContext
0x1800280f3  lea     rcx, CLSID_XMLSchemaCache60; rclsid
0x1800280fa  call    cs:__imp_CoCreateInstance
0x180028100  mov     esi, eax
0x180028102  test    eax, eax
0x180028104  js      loc_180028384
0x18002810a  mov     esi, r13d
0x18002810d  mov     r14d, r13d
0x180028110  lea     r11, off_18022D040; "http://www.microsoft.com/networking/WLA"...
0x180028117  cmp     r14d, 0Ah
0x18002811b  jnb     loc_18002830A
0x180028121  mov     r10d, r14d
0x180028124  mov     edx, 104h
0x180028129  sub     rdx, r15
0x18002812c  lea     r8, [rbp+400h+psz]
0x180028133  lea     r8, [r8+r15*2]
0x180028137  jz      loc_1800283BA
0x18002813d  cmp     rdx, 7FFFFFFFh
0x180028144  ja      loc_1800283A0
0x18002814a  mov     ecx, 7FFFFFFEh
0x18002814f  mov     eax, r10d
0x180028152  add     rax, rax
0x180028155  mov     r9, [r11+rax*8+8]
0x18002815a  test    rcx, rcx
0x18002815d  jz      short loc_18002817D
0x18002815f  movzx   eax, word ptr [r9]
0x180028163  test    ax, ax
0x180028166  jz      short loc_18002817D
0x180028168  add     r9, 2
0x18002816c  mov     [r8], ax
0x180028170  add     r8, 2
0x180028174  dec     rcx
0x180028177  sub     rdx, 1
0x18002817b  jnz     short loc_18002815A
0x18002817d  mov     rax, rdx
0x180028180  neg     rax
0x180028183  sbb     esi, esi
0x180028185  not     esi
0x180028187  and     esi, 8007007Ah
0x18002818d  lea     rcx, [r8-2]
0x180028191  test    rdx, rdx
0x180028194  cmovnz  rcx, r8
0x180028198  mov     [rcx], r13w
0x18002819c  jz      loc_1800283A7
0x1800281a2  add     r10, r10
0x1800281a5  mov     rsi, [r11+r10*8]
0x1800281a9  mov     rcx, rdi; bstrString
0x1800281ac  call    cs:__imp_SysFreeString
0x1800281b2  mov     rdi, r13
0x1800281b5  mov     rcx, rsi; psz
0x1800281b8  call    cs:__imp_SysAllocString
0x1800281be  mov     rsi, rax
0x1800281c1  test    rax, rax
0x1800281c4  jz      short loc_1800281D1
0x1800281c6  xor     ecx, ecx; bstrString
0x1800281c8  call    cs:__imp_SysFreeString
0x1800281ce  mov     rdi, rsi
0x1800281d1  lea     rcx, [rsp+500h+var_4C8]; pvarg
0x1800281d6  call    cs:__imp_VariantClear
0x1800281dc  test    eax, eax
0x1800281de  js      loc_1800283D0
0x1800281e4  xorps   xmm0, xmm0
0x1800281e7  xor     esi, esi
0x1800281e9  movups  [rsp+500h+var_4B0], xmm0
0x1800281ee  lea     eax, [rsi+8]
0x1800281f1  mov     word ptr [rsp+500h+var_4B0], ax
0x1800281f6  lea     rcx, [rbp+400h+psz]; psz
0x1800281fd  call    cs:__imp_SysAllocString
0x180028203  mov     qword ptr [rsp+500h+var_4B0+8], rax
0x180028208  lea     rcx, [rsp+500h+var_4C8]; pvarg
0x18002820d  call    cs:__imp_VariantClear
0x180028213  test    eax, eax
0x180028215  js      loc_1800283D0
0x18002821b  movups  xmm1, [rsp+500h+var_4B0]
0x180028220  movups  xmmword ptr [rsp+500h+var_4C8], xmm1
0x180028225  movq    xmm2, rsi
0x18002822a  movsd   qword ptr [rsp+500h+var_4C8+10h], xmm2
0x180028230  test    rdi, rdi
0x180028233  jz      short loc_18002828F
0x180028235  movd    eax, xmm1
0x180028239  mov     ecx, 8
0x18002823e  cmp     ax, cx
0x180028241  jnz     short loc_18002828F
0x180028243  movdqa  xmm0, xmm1
0x180028247  psrldq  xmm0, 8
0x18002824c  movq    rax, xmm0
0x180028251  test    rax, rax
0x180028254  jz      short loc_18002828F
0x180028256  mov     rcx, [rsp+500h+var_4D0]
0x18002825b  movaps  [rsp+500h+var_4B0], xmm1
0x180028260  movsd   [rsp+500h+var_4A0], xmm2
0x180028266  mov     rax, [rcx]
0x180028269  lea     r8, [rsp+500h+var_4B0]
0x18002826e  mov     rdx, rdi
0x180028271  mov     rax, [rax+38h]
0x180028275  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002827a  mov     esi, eax
0x18002827c  test    eax, eax
0x18002827e  js      loc_1800283E0
0x180028284  mov     esi, r13d
0x180028287  inc     r14d
0x18002828a  jmp     loc_180028110
0x18002828f  mov     esi, 8
0x180028294  mov     rcx, rdi; bstrString
0x180028297  call    cs:__imp_SysFreeString
0x18002829d  lea     rcx, [rsp+500h+var_4C8]; pvarg
0x1800282a2  call    cs:__imp_VariantClear
0x1800282a8  nop
0x1800282a9  mov     rcx, [rsp+500h+var_4D0]
0x1800282ae  test    rcx, rcx
0x1800282b1  jz      short loc_1800282C0
0x1800282b3  mov     rax, [rcx]
0x1800282b6  mov     rax, [rax+10h]
0x1800282ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800282bf  nop
0x1800282c0  test    esi, esi
0x1800282c2  jz      short loc_18002831E
0x1800282c4  lea     rcx, [rsp+500h+pvarg]; pvarg
0x1800282c9  call    cs:__imp_VariantClear
0x1800282cf  nop
0x1800282d0  test    rbx, rbx
0x1800282d3  jz      short loc_1800282E5
0x1800282d5  mov     rax, [rbx]
0x1800282d8  mov     rcx, rbx
0x1800282db  mov     rax, [rax+10h]
0x1800282df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800282e4  nop
0x1800282e5  mov     eax, esi
0x1800282e7  mov     rcx, [rbp+400h+var_50]
0x1800282ee  xor     rcx, rsp; StackCookie
0x1800282f1  call    __security_check_cookie
0x1800282f6  add     rsp, 4C8h
0x1800282fd  pop     r15
0x1800282ff  pop     r14
0x180028301  pop     r13
0x180028303  pop     r12
0x180028305  pop     rdi
0x180028306  pop     rsi
0x180028307  pop     rbx
0x180028308  pop     rbp
0x180028309  retn
0x18002830a  mov     rbx, [rsp+500h+var_4D0]
0x18002830f  mov     [rsp+500h+var_4D0], r13
0x180028314  mov     [rsp+500h+var_490], rbx
0x180028319  jmp     loc_180028294
0x18002831e  mov     rax, rbx
0x180028321  mov     rbx, r13
0x180028324  mov     [r12], rax
0x180028328  jmp     short loc_1800282C4
0x18002832a  call    cs:__imp_GetLastError
0x180028330  mov     esi, eax
0x180028332  jmp     short loc_1800282C4
0x180028334  test    esi, esi
0x180028336  jnz     loc_180028294
0x18002833c  jmp     loc_1800281A2
0x180028341  mov     esi, 7Ah ; 'z'
0x180028346  jmp     loc_1800282C4
0x18002834b  mov     eax, edx
0x18002834d  and     eax, r15d
0x180028350  movzx   esi, dx
0x180028353  cmp     eax, 70000h
0x180028358  cmovnz  esi, edx
0x18002835b  test    esi, esi
0x18002835d  jnz     loc_1800282C4
0x180028363  jmp     loc_180028058
0x180028368  mov     eax, esi
0x18002836a  and     eax, r15d
0x18002836d  cmp     eax, 70000h
0x180028372  jnz     short loc_180028377
0x180028374  movzx   esi, si
0x180028377  test    esi, esi
0x180028379  jnz     loc_180028294
0x18002837f  jmp     loc_1800280C7
0x180028384  and     eax, 1FFF0000h
0x180028389  cmp     eax, 70000h
0x18002838e  jnz     short loc_180028393
0x180028390  movzx   esi, si
0x180028393  test    esi, esi
0x180028395  jnz     loc_180028294
0x18002839b  jmp     loc_18002810D
0x1800283a0  mov     esi, 80070057h
  ... truncated ...
```
