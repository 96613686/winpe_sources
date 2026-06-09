# AuthBufferHelper::CreateAuthBuffer(IAuthBufferExecutionContext *,IMemoryManager *,uchar const *,ulong,ushort const *,ulong,int,uchar * *,ulong *)

- ea: `0x1800518a0`
- end: `0x180051d7e`
- name: `?CreateAuthBuffer@AuthBufferHelper@@UEAAJPEAVIAuthBufferExecutionContext@@PEAVIMemoryManager@@PEBEKPEBGKHPEAPEAEPEAK@Z`
- size: `1246`
- prototype: `__int64 __fastcall(AuthBufferHelper *__hidden this, struct IAuthBufferExecutionContext *, struct IMemoryManager *, const unsigned __int8 *, rsize_t DestinationSize, const unsigned __int16 *, unsigned int, int, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x1800061a8`
- `0x1800090c0`
- `0x180009630`
- `0x18000a400`
- `0x18001633c`
- `0x1800189f4`
- `0x1800392b0`
- `0x180051770`
- `0x1800517c8`
- `0x180051844`
- `0x1800518a0`
- `0x180058010`

## string_xrefs

- `0x1800518dc`: `AuthBufferHelper::CreateAuthBuffer`
- `0x180051c43`: `AuthBufferHelper::CreateAuthBuffer`
- `0x180051cf6`: `AuthBufferHelper::CreateAuthBuffer`
- `0x180051d15`: `hr = SafeCopyMemory(pWhere, cbAuthData, pAuthData, cbAuthData)`
- `0x180051b66`: `SspiCopyAuthIdentity failed. 0x%X`
- `0x180051d06`: `hr = SafeCopyMemory(pWhere, cbUserName, wszUserName, cbUserName)`
- `0x180051cda`: `hr = SafeCopyMemory(pWhere, cbDomainName, wszDomainName, cbDomainName)`
- `0x180051cc3`: `hr = SafeCopyMemory(spAuthBuffer, cbAuthBuffer, spMarshaledAuthId, cbMarshaledAuthId)`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall AuthBufferHelper::CreateAuthBuffer(
        AuthBufferHelper *this,
        struct IAuthBufferExecutionContext *a2,
        struct IMemoryManager *a3,
        unsigned __int8 *a4,
        rsize_t DestinationSize,
        unsigned __int16 *a6,
        unsigned int a7,
        int a8,
        unsigned __int8 **a9,
        unsigned int *a10)
{
  int v10; // eax
  int v11; // r9d
  unsigned int v12; // r8d
  __int16 v13; // r15
  rsize_t v14; // r14
  unsigned __int64 v15; // rax
  const char *v16; // rax
  rsize_t v17; // rsi
  rsize_t v18; // rdi
  int v19; // eax
  char *v20; // rbx
  unsigned int v21; // eax
  unsigned int v22; // r13d
  char *v23; // r14
  char *v24; // rsi
  __int64 v25; // rsi
  int v26; // ebx
  const unsigned __int16 *v27; // r9
  unsigned int v28; // r8d
  int v29; // eax
  const char *v30; // rax
  unsigned int v31; // r8d
  unsigned int v32; // ebx
  const unsigned __int16 *v34; // [rsp+28h] [rbp-89h]
  __int64 v35; // [rsp+28h] [rbp-89h]
  const char *v36; // [rsp+28h] [rbp-89h]
  rsize_t SourceSize; // [rsp+38h] [rbp-79h] BYREF
  _QWORD v38[2]; // [rsp+40h] [rbp-71h] BYREF
  __int64 v39; // [rsp+50h] [rbp-61h] BYREF
  rsize_t v40; // [rsp+58h] [rbp-59h]
  __int64 v41; // [rsp+60h] [rbp-51h]
  void *v42; // [rsp+68h] [rbp-49h] BYREF
  __int64 v43; // [rsp+70h] [rbp-41h]
  _QWORD *v44; // [rsp+78h] [rbp-39h]
  void *Destination; // [rsp+80h] [rbp-31h] BYREF
  __int64 v46; // [rsp+88h] [rbp-29h]
  struct IMemoryManager *v47; // [rsp+90h] [rbp-21h]
  _QWORD v48[10]; // [rsp+98h] [rbp-19h] BYREF
  int v50; // [rsp+108h] [rbp+57h] BYREF
  void *Source; // [rsp+110h] [rbp+5Fh]

  Source = a4;
  v50 = 0;
  SourceSize = 0;
  Destination = 0;
  v47 = a3;
  v46 = 0;
  v48[0] = "AuthBufferHelper::CreateAuthBuffer";
  v48[1] = &v50;
  v48[2] = 0;
  v48[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\authbufferhelper.cpp",
    "AuthBufferHelper::CreateAuthBuffer",
    (const char *)0x92,
    0,
    v34);
  *a9 = 0;
  *a10 = 0;
  v10 = StringCbLengthW(a6, 0xFFFFu, &SourceSize);
  v50 = v10;
  if ( v10 < 0 )
  {
    v36 = "hr = StringCbLengthW(wszUserName, USHRT_MAX, &cbUserName)";
    v11 = v10;
    v12 = 157;
LABEL_37:
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\authbufferhelper.cpp",
      "AuthBufferHelper::CreateAuthBuffer",
      v12,
      v11,
      v36);
    goto LABEL_38;
  }
  v13 = DestinationSize;
  v14 = (unsigned int)DestinationSize;
  v15 = (unsigned int)DestinationSize + 92LL;
  if ( v15 < (unsigned int)DestinationSize )
  {
    v16 = "hr = SizeTAdd(cbAuthData, cbAuthBuffer, &cbAuthBuffer)";
    v12 = 166;
LABEL_36:
    v11 = -2147024362;
    v50 = -2147024362;
    v36 = v16;
    goto LABEL_37;
  }
  v17 = SourceSize;
  if ( v15 + SourceSize < SourceSize )
  {
    v16 = "hr = SizeTAdd(cbUserName, cbAuthBuffer, &cbAuthBuffer)";
    v12 = 167;
    goto LABEL_36;
  }
  v18 = v15 + SourceSize + 32;
  if ( v18 < 0x20 )
  {
    v16 = "hr = SizeTAdd(cbDomainName, cbAuthBuffer, &cbAuthBuffer)";
    v12 = 168;
    goto LABEL_36;
  }
  v50 = 0;
  v19 = Auto<unsigned char *,ZeroMemoryFunctor<unsigned char *>,IMemoryManager>::Allocate(&Destination, v18);
  v50 = v19;
  if ( v19 < 0 )
  {
    v36 = "hr = spAuthBuffer.Allocate(cbAuthBuffer)";
    v11 = v19;
    v12 = 170;
    goto LABEL_37;
  }
  v20 = (char *)Destination;
  *(_DWORD *)Destination = 513;
  *((_WORD *)v20 + 2) = 48;
  *((_DWORD *)v20 + 2) = v18;
  *(_QWORD *)(v20 + 36) = 0;
  *((_WORD *)v20 + 22) = 0;
  *((_WORD *)v20 + 24) = 28;
  *((_WORD *)v20 + 25) = v13 + 44;
  *(_OWORD *)(v20 + 52) = xmmword_180074858;
  *((_WORD *)v20 + 16) = v13 + 44;
  *((_DWORD *)v20 + 7) = 48;
  *((_WORD *)v20 + 38) = 16;
  *((_WORD *)v20 + 39) = v13 + 16;
  v21 = a7 & 0xDFFFFFFF;
  v22 = a7 & 0x20000000;
  if ( (a7 & 0x20000000) == 0 )
    v21 = a7;
  *((_DWORD *)v20 + 22) = v21;
  *((_WORD *)v20 + 36) = v13 + 16;
  *((_DWORD *)v20 + 17) = 28;
  if ( memcpy_s_3(v20 + 92, v14, Source, v14) )
  {
    v30 = "hr = SafeCopyMemory(pWhere, cbAuthData, pAuthData, cbAuthData)";
    v31 = 227;
    goto LABEL_32;
  }
  v50 = 0;
  *((_WORD *)v20 + 42) = v13;
  *((_DWORD *)v20 + 20) = 16;
  v23 = &v20[v14 + 92];
  if ( memcpy_s_3(v23, v17, a6, v17) )
  {
    v30 = "hr = SafeCopyMemory(pWhere, cbUserName, wszUserName, cbUserName)";
    v31 = 242;
    goto LABEL_32;
  }
  v50 = 0;
  *((_WORD *)v20 + 8) = v17;
  *((_DWORD *)v20 + 3) = (_DWORD)v23 - (_DWORD)v20;
  v24 = &v23[v17];
  if ( memcpy_s_3(v24, 0x20u, L"MicrosoftAccount", 0x20u) )
  {
    v30 = "hr = SafeCopyMemory(pWhere, cbDomainName, wszDomainName, cbDomainName)";
    v31 = 257;
LABEL_32:
    v50 = -2147418113;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\authbufferhelper.cpp",
      "AuthBufferHelper::CreateAuthBuffer",
      v31,
      -2147418113,
      v30);
    goto LABEL_38;
  }
  v50 = 0;
  *((_WORD *)v20 + 12) = 32;
  *((_DWORD *)v20 + 5) = (_DWORD)v24 - (_DWORD)v20;
  if ( !a8 )
    goto LABEL_29;
  v25 = (*(__int64 (__fastcall **)(struct IAuthBufferExecutionContext *))(*(_QWORD *)a2 + 40LL))(a2);
  v39 = 0;
  v41 = v25;
  v40 = 0;
  v38[0] = &SspiLocalMemoryManager::`vftable';
  v38[1] = v25;
  v42 = 0;
  v44 = v38;
  v43 = 0;
  LODWORD(SourceSize) = 0;
  v26 = (*(__int64 (__fastcall **)(__int64, char *, __int64 *))(*(_QWORD *)v25 + 8LL))(v25, v20, &v39);
  v40 = v18;
  if ( v26 >= 0 )
  {
    v26 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v25 + 16LL))(v25, v22 != 0 ? 4 : 1, v39);
    if ( v26 < 0 )
    {
      v27 = L"SspiEncryptAuthIdentityEx failed. 0x%X";
      v28 = 298;
      goto LABEL_18;
    }
    v26 = (*(__int64 (__fastcall **)(__int64, __int64, rsize_t *, void **))(*(_QWORD *)v25 + 32LL))(
            v25,
            v39,
            &SourceSize,
            &v42);
    v43 = (unsigned int)SourceSize;
    if ( v26 < 0 )
    {
      v27 = L"SspiMarshalAuthIdentity failed. 0x%X";
      v28 = 307;
      goto LABEL_18;
    }
    v29 = Auto<unsigned char *,ZeroMemoryFunctor<unsigned char *>,IMemoryManager>::Allocate(
            &Destination,
            (unsigned int)SourceSize);
    v50 = v29;
    if ( v29 < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\authbufferhelper.cpp",
        "AuthBufferHelper::CreateAuthBuffer",
        0x13Bu,
        v29,
        "hr = spAuthBuffer.Allocate(cbMarshaledAuthId)");
      goto LABEL_19;
    }
    LODWORD(v18) = SourceSize;
    v20 = (char *)Destination;
    if ( memcpy_s_3(Destination, (unsigned int)SourceSize, v42, (unsigned int)SourceSize) )
    {
      v50 = -2147418113;
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\authbufferhelper.cpp",
        "AuthBufferHelper::CreateAuthBuffer",
        0x140u,
        -2147418113,
        "hr = SafeCopyMemory(spAuthBuffer, cbAuthBuffer, spMarshaledAuthId, cbMarshaledAuthId)");
      goto LABEL_19;
    }
    v50 = 0;
    Auto<char *,ZeroMemoryFunctor<char *>,IMemoryManager>::~Auto<char *,ZeroMemoryFunctor<char *>,IMemoryManager>(&v42);
    v38[0] = &IMemoryFunctions::`vftable';
    Auto<void *,SspiAuthIdentityFunctor,ISspiFunctions>::~Auto<void *,SspiAuthIdentityFunctor,ISspiFunctions>(&v39);
LABEL_29:
    Destination = 0;
    v46 = 0;
    *a9 = (unsigned __int8 *)v20;
    *a10 = v18;
    goto LABEL_38;
  }
  v27 = L"SspiCopyAuthIdentity failed. 0x%X";
  v28 = 283;
LABEL_18:
  LODWORD(v35) = v26;
  TracePrintW(2u, "onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\authbufferhelper.cpp", v28, v27, v35);
  v50 = v26 | 0x10000000;
LABEL_19:
  Auto<char *,ZeroMemoryFunctor<char *>,IMemoryManager>::~Auto<char *,ZeroMemoryFunctor<char *>,IMemoryManager>(&v42);
  v38[0] = &IMemoryFunctions::`vftable';
  Auto<void *,SspiAuthIdentityFunctor,ISspiFunctions>::~Auto<void *,SspiAuthIdentityFunctor,ISspiFunctions>(&v39);
LABEL_38:
  v32 = v50;
  CTraceFuncW<long>::~CTraceFuncW<long>(v48);
  Auto<unsigned char *,ZeroMemoryFunctor<unsigned char *>,IMemoryManager>::~Auto<unsigned char *,ZeroMemoryFunctor<unsigned char *>,IMemoryManager>(&Destination);
  return v32;
}

```

## disassembly

```asm
0x1800518a0  mov     rax, rsp
0x1800518a3  mov     [rax+8], rbx
0x1800518a7  mov     [rax+20h], r9
0x1800518ab  mov     [rax+10h], rdx
0x1800518af  push    rbp
0x1800518b0  push    rsi
0x1800518b1  push    rdi
0x1800518b2  push    r12
0x1800518b4  push    r13
0x1800518b6  push    r14
0x1800518b8  push    r15
0x1800518ba  lea     rbp, [rax-3Fh]
0x1800518be  sub     rsp, 0B0h
0x1800518c5  xor     r12d, r12d
0x1800518c8  mov     [rbp+37h+arg_10], r12d
0x1800518cc  mov     [rbp+37h+SourceSize], r12
0x1800518d0  mov     [rbp+37h+Destination], r12
0x1800518d4  mov     [rbp+37h+var_58], r8
0x1800518d8  mov     [rbp+37h+var_60], r12
0x1800518dc  lea     r13, aAuthbufferhelp; "AuthBufferHelper::CreateAuthBuffer"
0x1800518e3  mov     [rbp+37h+var_50], r13
0x1800518e7  lea     rax, [rbp+37h+arg_10]
0x1800518eb  mov     [rbp+37h+var_48], rax
0x1800518ef  mov     [rbp+37h+var_40], r12
0x1800518f3  mov     [rbp+37h+var_38], r12
0x1800518f7  xor     r9d, r9d; unsigned int
0x1800518fa  mov     r8d, 92h; char *
0x180051900  mov     rdx, r13; char *
0x180051903  lea     rbx, aOnecoreuapDsEx_3; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18005190a  mov     rcx, rbx; this
0x18005190d  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180051912  nop
0x180051913  mov     rax, [rbp+37h+arg_40]
0x18005191a  mov     [rax], r12
0x18005191d  mov     rax, [rbp+37h+arg_48]
0x180051924  mov     [rax], r12d
0x180051927  lea     r8, [rbp+37h+SourceSize]; unsigned __int64 *
0x18005192b  mov     edx, 0FFFFh; unsigned __int64
0x180051930  mov     rcx, [rbp+37h+arg_28]; unsigned __int16 *
0x180051934  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180051939  mov     [rbp+37h+arg_10], eax
0x18005193c  test    eax, eax
0x18005193e  jns     short loc_18005195A
0x180051940  lea     r8, aHrStringcbleng; "hr = StringCbLengthW(wszUserName, USHRT"...
0x180051947  mov     [rsp+20h], r8
0x18005194c  mov     r9d, eax
0x18005194f  mov     r8d, 9Dh
0x180051955  jmp     loc_180051D40
0x18005195a  mov     r15d, dword ptr [rbp+37h+DestinationSize]
0x18005195e  mov     r14d, r15d
0x180051961  lea     rax, [r15+5Ch]
0x180051965  cmp     rax, r15
0x180051968  jnb     short loc_18005197C
0x18005196a  lea     rax, aHrSizetaddCbau; "hr = SizeTAdd(cbAuthData, cbAuthBuffer,"...
0x180051971  mov     r8d, 0A6h
0x180051977  jmp     loc_180051D31
0x18005197c  mov     rsi, [rbp+37h+SourceSize]
0x180051980  lea     rdi, [rax+rsi]
0x180051984  cmp     rdi, rsi
0x180051987  jnb     short loc_18005199B
0x180051989  lea     rax, aHrSizetaddCbus; "hr = SizeTAdd(cbUserName, cbAuthBuffer,"...
0x180051990  mov     r8d, 0A7h
0x180051996  jmp     loc_180051D31
0x18005199b  add     rdi, 20h ; ' '
0x18005199f  cmp     rdi, 20h ; ' '
0x1800519a3  jb      loc_180051D24
0x1800519a9  mov     [rbp+37h+arg_10], r12d
0x1800519ad  mov     rdx, rdi
0x1800519b0  lea     rcx, [rbp+37h+Destination]
0x1800519b4  call    ?Allocate@?$Auto@PEAEV?$ZeroMemoryFunctor@PEAE@@VIMemoryManager@@@@QEAAJ_K@Z; Auto<uchar *,ZeroMemoryFunctor<uchar *>,IMemoryManager>::Allocate(unsigned __int64)
0x1800519b9  mov     [rbp+37h+arg_10], eax
0x1800519bc  test    eax, eax
0x1800519be  jns     short loc_1800519DA
0x1800519c0  lea     rcx, aHrSpauthbuffer_0; "hr = spAuthBuffer.Allocate(cbAuthBuffer"...
0x1800519c7  mov     [rsp+20h], rcx
0x1800519cc  mov     r9d, eax
0x1800519cf  mov     r8d, 0AAh
0x1800519d5  jmp     loc_180051D40
0x1800519da  mov     rbx, [rbp+37h+Destination]
0x1800519de  mov     dword ptr [rbx], 201h
0x1800519e4  mov     word ptr [rbx+4], 30h ; '0'
0x1800519ea  mov     [rbx+8], edi
0x1800519ed  mov     [rbx+24h], r12
0x1800519f1  mov     [rbx+2Ch], r12w
0x1800519f6  lea     r8, [rbx+30h]
0x1800519fa  mov     word ptr [r8], 1Ch
0x180051a00  lea     eax, [r15+2Ch]
0x180051a04  mov     [r8+2], ax
0x180051a09  movups  xmm0, cs:xmmword_180074858
0x180051a10  movdqu  xmmword ptr [r8+4], xmm0
0x180051a16  mov     [rbx+20h], ax
0x180051a1a  mov     eax, r8d
0x180051a1d  sub     eax, ebx
0x180051a1f  mov     [rbx+1Ch], eax
0x180051a22  lea     r12, [r8+1Ch]
0x180051a26  mov     ecx, 10h
0x180051a2b  mov     [r12], cx
0x180051a30  lea     edx, [rcx+r15]
0x180051a34  mov     [r12+2], dx
0x180051a3a  mov     ecx, [rbp+37h+arg_30]
0x180051a3d  mov     r13d, ecx
0x180051a40  mov     eax, ecx
0x180051a42  btr     eax, 1Dh
0x180051a46  and     r13d, 20000000h
0x180051a4d  cmovz   eax, ecx
0x180051a50  mov     [r12+0Ch], eax
0x180051a55  mov     [r8+18h], dx
0x180051a5a  mov     eax, r12d
0x180051a5d  sub     eax, r8d
0x180051a60  mov     [r8+14h], eax
0x180051a64  lea     rcx, [r12+10h]; Destination
0x180051a69  mov     r9, r14; SourceSize
0x180051a6c  mov     r8, [rbp+37h+Source]; Source
0x180051a70  mov     rdx, r14; DestinationSize
0x180051a73  call    memcpy_s_3
0x180051a78  test    eax, eax
0x180051a7a  jnz     loc_180051D15
0x180051a80  mov     [rbp+37h+arg_10], eax
0x180051a83  mov     [r12+8], r15w
0x180051a89  lea     rcx, [r12+10h]
0x180051a8e  mov     eax, ecx
0x180051a90  sub     eax, r12d
0x180051a93  mov     [r12+4], eax
0x180051a98  add     r14, rcx
0x180051a9b  mov     r9, rsi; SourceSize
0x180051a9e  mov     r8, [rbp+37h+arg_28]; Source
0x180051aa2  mov     rdx, rsi; DestinationSize
0x180051aa5  mov     rcx, r14; Destination
0x180051aa8  call    memcpy_s_3
0x180051aad  xor     r15d, r15d
0x180051ab0  test    eax, eax
0x180051ab2  jnz     loc_180051D06
0x180051ab8  mov     [rbp+37h+arg_10], r15d
0x180051abc  mov     [rbx+10h], si
0x180051ac0  mov     eax, r14d
0x180051ac3  sub     eax, ebx
0x180051ac5  mov     [rbx+0Ch], eax
0x180051ac8  add     rsi, r14
0x180051acb  lea     r14d, [r15+20h]
0x180051acf  mov     r9d, r14d; SourceSize
0x180051ad2  lea     r8, Src; "MicrosoftAccount"
0x180051ad9  mov     edx, r14d; DestinationSize
0x180051adc  mov     rcx, rsi; Destination
0x180051adf  call    memcpy_s_3
0x180051ae4  test    eax, eax
0x180051ae6  jnz     loc_180051CDA
0x180051aec  mov     [rbp+37h+arg_10], r15d
0x180051af0  mov     [rbx+18h], r14w
0x180051af5  sub     esi, ebx
0x180051af7  mov     [rbx+14h], esi
0x180051afa  cmp     [rbp+37h+arg_38], r15d
0x180051afe  jz      loc_180051C99
0x180051b04  mov     rcx, [rbp+37h+arg_8]
0x180051b08  mov     rax, [rcx]
0x180051b0b  mov     rax, [rax+28h]
0x180051b0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051b14  mov     rsi, rax
0x180051b17  mov     [rbp+37h+var_98], r15
0x180051b1b  mov     [rbp+37h+var_88], rax
0x180051b1f  mov     [rbp+37h+var_90], r15
0x180051b23  lea     rax, ??_7SspiLocalMemoryManager@@6B@; const SspiLocalMemoryManager::`vftable'
0x180051b2a  mov     [rbp+37h+var_A8], rax
0x180051b2e  mov     [rbp+37h+var_A0], rsi
0x180051b32  mov     [rbp+37h+var_80], r15
0x180051b36  lea     rax, [rbp+37h+var_A8]
0x180051b3a  mov     [rbp+37h+var_70], rax
0x180051b3e  mov     [rbp+37h+var_78], r15
0x180051b42  mov     dword ptr [rbp+37h+SourceSize], r15d
0x180051b46  mov     rax, [rsi]
0x180051b49  lea     r8, [rbp+37h+var_98]
0x180051b4d  mov     rdx, rbx
0x180051b50  mov     rcx, rsi
0x180051b53  mov     rax, [rax+8]
0x180051b57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051b5c  mov     ebx, eax
0x180051b5e  mov     [rbp+37h+var_90], rdi
0x180051b62  test    eax, eax
0x180051b64  jns     short loc_180051BB2
0x180051b66  lea     r9, aSspicopyauthid_0; "SspiCopyAuthIdentity failed. 0x%X"
0x180051b6d  mov     r8d, 11Bh; unsigned int
0x180051b73  mov     [rsp+20h], ebx
0x180051b77  lea     rdx, aOnecoreuapDsEx_3; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180051b7e  mov     ecx, 2; unsigned __int8
0x180051b83  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180051b88  bts     ebx, 1Ch
0x180051b8c  mov     [rbp+37h+arg_10], ebx
0x180051b8f  lea     rcx, [rbp+37h+var_80]
0x180051b93  call    ??1?$Auto@PEADV?$ZeroMemoryFunctor@PEAD@@VIMemoryManager@@@@QEAA@XZ; Auto<char *,ZeroMemoryFunctor<char *>,IMemoryManager>::~Auto<char *,ZeroMemoryFunctor<char *>,IMemoryManager>(void)
0x180051b98  nop
0x180051b99  lea     rax, ??_7IMemoryFunctions@@6B@; const IMemoryFunctions::`vftable'
0x180051ba0  mov     [rbp+37h+var_A8], rax
0x180051ba4  lea     rcx, [rbp+37h+var_98]
0x180051ba8  call    ??1?$Auto@PEAXVSspiAuthIdentityFunctor@@VISspiFunctions@@@@QEAA@XZ; Auto<void *,SspiAuthIdentityFunctor,ISspiFunctions>::~Auto<void *,SspiAuthIdentityFunctor,ISspiFunctions>(void)
0x180051bad  jmp     loc_180051D4B
0x180051bb2  mov     rax, [rsi]
0x180051bb5  neg     r13d
0x180051bb8  sbb     edx, edx
0x180051bba  and     edx, 3
0x180051bbd  inc     edx
0x180051bbf  mov     r8, [rbp+37h+var_98]
0x180051bc3  mov     rcx, rsi
0x180051bc6  mov     rax, [rax+10h]
0x180051bca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051bcf  mov     ebx, eax
0x180051bd1  test    eax, eax
0x180051bd3  jns     short loc_180051BE4
0x180051bd5  lea     r9, aSspiencryptaut; "SspiEncryptAuthIdentityEx failed. 0x%X"
0x180051bdc  mov     r8d, 12Ah
0x180051be2  jmp     short loc_180051B73
0x180051be4  mov     rax, [rsi]
0x180051be7  lea     r9, [rbp+37h+var_80]
0x180051beb  lea     r8, [rbp+37h+SourceSize]
0x180051bef  mov     rdx, [rbp+37h+var_98]
0x180051bf3  mov     rcx, rsi
0x180051bf6  mov     rax, [rax+20h]
0x180051bfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051bff  mov     ebx, eax
0x180051c01  mov     edx, dword ptr [rbp+37h+SourceSize]
0x180051c04  mov     [rbp+37h+var_78], rdx
0x180051c08  test    eax, eax
0x180051c0a  jns     short loc_180051C1E
0x180051c0c  lea     r9, aSspimarshalaut_0; "SspiMarshalAuthIdentity failed. 0x%X"
0x180051c13  mov     r8d, 133h
0x180051c19  jmp     loc_180051B73
0x180051c1e  lea     rcx, [rbp+37h+Destination]
0x180051c22  call    ?Allocate@?$Auto@PEAEV?$ZeroMemoryFunctor@PEAE@@VIMemoryManager@@@@QEAAJ_K@Z; Auto<uchar *,ZeroMemoryFunctor<uchar *>,IMemoryManager>::Allocate(unsigned __int64)
0x180051c27  mov     [rbp+37h+arg_10], eax
0x180051c2a  test    eax, eax
0x180051c2c  jns     short loc_180051C5B
0x180051c2e  lea     rcx, aHrSpauthbuffer; "hr = spAuthBuffer.Allocate(cbMarshaledA"...
0x180051c35  mov     [rsp+20h], rcx; char *
0x180051c3a  mov     r9d, eax; int
0x180051c3d  mov     r8d, 13Bh; unsigned int
0x180051c43  lea     rdx, aAuthbufferhelp; "AuthBufferHelper::CreateAuthBuffer"
0x180051c4a  lea     rcx, aOnecoreuapDsEx_3; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180051c51  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180051c56  jmp     loc_180051B8F
0x180051c5b  mov     edi, dword ptr [rbp+37h+SourceSize]
0x180051c5e  mov     r9d, edi; SourceSize
0x180051c61  mov     r8, [rbp+37h+var_80]; Source
0x180051c65  mov     edx, edi; DestinationSize
0x180051c67  mov     rbx, [rbp+37h+Destination]
0x180051c6b  mov     rcx, rbx; Destination
0x180051c6e  call    memcpy_s_3
0x180051c73  test    eax, eax
0x180051c75  jnz     short loc_180051CB9
0x180051c77  mov     [rbp+37h+arg_10], r15d
0x180051c7b  lea     rcx, [rbp+37h+var_80]
0x180051c7f  call    ??1?$Auto@PEADV?$ZeroMemoryFunctor@PEAD@@VIMemoryManager@@@@QEAA@XZ; Auto<char *,ZeroMemoryFunctor<char *>,IMemoryManager>::~Auto<char *,ZeroMemoryFunctor<char *>,IMemoryManager>(void)
0x180051c84  nop
0x180051c85  lea     rax, ??_7IMemoryFunctions@@6B@; const IMemoryFunctions::`vftable'
0x180051c8c  mov     [rbp+37h+var_A8], rax
0x180051c90  lea     rcx, [rbp+37h+var_98]
0x180051c94  call    ??1?$Auto@PEAXVSspiAuthIdentityFunctor@@VISspiFunctions@@@@QEAA@XZ; Auto<void *,SspiAuthIdentityFunctor,ISspiFunctions>::~Auto<void *,SspiAuthIdentityFunctor,ISspiFunctions>(void)
0x180051c99  mov     [rbp+37h+Destination], r15
0x180051c9d  mov     [rbp+37h+var_60], r15
0x180051ca1  mov     rax, [rbp+37h+arg_40]
0x180051ca8  mov     [rax], rbx
0x180051cab  mov     rax, [rbp+37h+arg_48]
0x180051cb2  mov     [rax], edi
0x180051cb4  jmp     loc_180051D4B
0x180051cb9  mov     r9d, 8000FFFFh
0x180051cbf  mov     [rbp+37h+arg_10], r9d
0x180051cc3  lea     rax, aHrSafecopymemo_6; "hr = SafeCopyMemory(spAuthBuffer, cbAut"...
0x180051cca  mov     [rsp+20h], rax
0x180051ccf  mov     r8d, 140h
0x180051cd5  jmp     loc_180051C43
0x180051cda  lea     rax, aHrSafecopymemo; "hr = SafeCopyMemory(pWhere, cbDomainNam"...
0x180051ce1  mov     r8d, 101h
0x180051ce7  mov     r9d, 8000FFFFh
0x180051ced  mov     [rbp+37h+arg_10], r9d
0x180051cf1  mov     [rsp+20h], rax
0x180051cf6  lea     rdx, aAuthbufferhelp; "AuthBufferHelper::CreateAuthBuffer"
0x180051cfd  lea     rcx, aOnecoreuapDsEx_3; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180051d04  jmp     short loc_180051D46
0x180051d06  lea     rax, aHrSafecopymemo_10; "hr = SafeCopyMemory(pWhere, cbUserName,"...
0x180051d0d  mov     r8d, 0F2h
0x180051d13  jmp     short loc_180051CE7
0x180051d15  lea     rax, aHrSafecopymemo_3; "hr = SafeCopyMemory(pWhere, cbAuthData,"...
0x180051d1c  mov     r8d, 0E3h
0x180051d22  jmp     short loc_180051CE7
0x180051d24  lea     rax, aHrSizetaddCbdo; "hr = SizeTAdd(cbDomainName, cbAuthBuffe"...
0x180051d2b  mov     r8d, 0A8h; unsigned int
0x180051d31  mov     r9d, 80070216h; int
0x180051d37  mov     [rbp+37h+arg_10], r9d
0x180051d3b  mov     [rsp+20h], rax; char *
0x180051d40  mov     rdx, r13; char *
0x180051d43  mov     rcx, rbx; char *
0x180051d46  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180051d4b  mov     ebx, [rbp+37h+arg_10]
0x180051d4e  lea     rcx, [rbp+37h+var_50]
0x180051d52  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180051d57  nop
0x180051d58  lea     rcx, [rbp+37h+Destination]
0x180051d5c  call    ??1?$Auto@PEAEV?$ZeroMemoryFunctor@PEAE@@VIMemoryManager@@@@QEAA@XZ; Auto<uchar *,ZeroMemoryFunctor<uchar *>,IMemoryManager>::~Auto<uchar *,ZeroMemoryFunctor<uchar *>,IMemoryManager>(void)
0x180051d61  mov     eax, ebx
0x180051d63  mov     rbx, [rsp+0E0h+arg_0]
0x180051d6b  add     rsp, 0B0h
0x180051d72  pop     r15
0x180051d74  pop     r14
  ... truncated ...
```
