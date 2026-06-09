# EncodingWriter::Init(EncodingWriterContext *,Encoding *)

- ea: `0x100422d70`
- end: `0x100423039`
- name: `?Init@EncodingWriter@@QEAAJPEAVEncodingWriterContext@@PEAVEncoding@@@Z`
- size: `713`
- prototype: `__int64 __fastcall(EncodingWriter *__hidden this, struct EncodingWriterContext *, struct Encoding *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x100422580`

## callees

- `0x100420450`
- `0x100422d70`
- `0x100439df0`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x100422f48`
- `KERNEL32!HeapAlloc` at `0x100422f48`
- `ole32!CoCreateInstance` at `0x100422e91`
- `ole32!CoCreateInstance` at `0x100422e91`

## pseudocode

```c
__int64 __fastcall EncodingWriter::Init(EncodingWriter *this, struct EncodingWriterContext *a2, const wchar_t **a3)
{
  __int64 v6; // rsi
  int CharsetInfo; // eax
  int v8; // ecx
  int (*v9)(unsigned int *, unsigned int, wchar_t *, unsigned int *, unsigned __int8 *, unsigned int *); // rax
  bool v10; // zf
  int (*v11)(unsigned int *, unsigned int, wchar_t *, unsigned int *, unsigned __int8 *, unsigned int *); // rcx
  struct IMultiLanguage2 *v12; // rcx
  unsigned int v13; // ebp
  HRESULT v14; // eax
  bool v15; // zf
  _BYTE *v16; // r8
  struct IMalloc *v17; // rcx
  _BYTE *v18; // rax
  int v20; // eax
  char v21; // r9
  void (__fastcall ***v22)(_QWORD, __int64); // rcx
  char v23; // cl
  LPVOID ppv; // [rsp+50h] [rbp+8h] BYREF

  *((_DWORD *)this + 7) = 3;
  v6 = 0;
  *((_DWORD *)this + 8) = 0;
  CharsetInfo = CharEncoder::getCharsetInfo(a3[2], (unsigned int *)this + 6, (unsigned int *)this + 7);
  if ( CharsetInfo < 0 )
  {
    if ( CharsetInfo == -1 )
    {
      _mm_lfence();
      v12 = s_pMultiLanguage2;
      v13 = *((_DWORD *)this + 6);
      if ( !s_pMultiLanguage2 )
      {
        ppv = 0;
        v14 = CoCreateInstance(&CLSID_CMultiLanguage, 0, 1u, &IID_IMultiLanguage2, &ppv);
        v15 = v14 == 0;
        if ( v14 >= 0 )
        {
          if ( _InterlockedCompareExchange64((volatile signed __int64 *)&s_pMultiLanguage2, (signed __int64)ppv, 0) )
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
          v15 = 1;
        }
        if ( !v15 )
          goto LABEL_48;
        v12 = s_pMultiLanguage2;
      }
      if ( !((unsigned int (__fastcall *)(struct IMultiLanguage2 *, __int64, _QWORD))v12->lpVtbl->IsConvertible)(
              v12,
              1200,
              v13) )
      {
        v10 = *((_BYTE *)a3 + 26) == 0;
        v9 = (int (*)(unsigned int *, unsigned int, wchar_t *, unsigned int *, unsigned __int8 *, unsigned int *))CharEncoder::wideCharToMultiByteMlangNoBestFit;
        v11 = (int (*)(unsigned int *, unsigned int, wchar_t *, unsigned int *, unsigned __int8 *, unsigned int *))CharEncoder::wideCharToMultiByteMlang;
LABEL_26:
        if ( !v10 )
          v9 = v11;
        goto LABEL_28;
      }
    }
LABEL_48:
    _mm_lfence();
    return 3222070638LL;
  }
  v8 = *((_DWORD *)this + 6);
  switch ( v8 )
  {
    case 1200:
      v10 = *((_BYTE *)a3 + 24) == 0;
      v9 = (int (*)(unsigned int *, unsigned int, wchar_t *, unsigned int *, unsigned __int8 *, unsigned int *))CharEncoder::wideCharToUtf16Bigendian;
      v11 = CharEncoder::wideCharToUtf16Littleendian;
      goto LABEL_26;
    case 12000:
      v9 = (int (*)(unsigned int *, unsigned int, wchar_t *, unsigned int *, unsigned __int8 *, unsigned int *))CharEncoder::wideCharToUcs4Littleendian;
      if ( !*((_BYTE *)a3 + 24) )
        v9 = (int (*)(unsigned int *, unsigned int, wchar_t *, unsigned int *, unsigned __int8 *, unsigned int *))CharEncoder::wideCharToUcs4Bigendian;
      break;
    case 65537:
      v9 = CharEncoder::wideCharToUtf16Littleendian;
      if ( !*((_BYTE *)a3 + 24) )
        v9 = (int (*)(unsigned int *, unsigned int, wchar_t *, unsigned int *, unsigned __int8 *, unsigned int *))CharEncoder::wideCharToUtf16Bigendian;
      break;
    default:
      if ( *((_BYTE *)a3 + 26) || !*((_BYTE *)&CharEncoder::charsetInfo + 40 * CharsetInfo + 4) )
        v9 = (int (*)(unsigned int *, unsigned int, wchar_t *, unsigned int *, unsigned __int8 *, unsigned int *))*((_QWORD *)&CharEncoder::charsetInfo + 5 * CharsetInfo + 4);
      else
        v9 = CharEncoder::wideCharToMultiByteWin32NoBestFit;
      break;
  }
LABEL_28:
  *((_QWORD *)this + 12) = v9;
  v16 = (_BYTE *)*((_QWORD *)this + 5);
  if ( !v16 )
  {
    v17 = (struct IMalloc *)*((_QWORD *)this + 1);
    if ( v17 || (v17 = g_pMalloc) != 0 )
      v18 = (_BYTE *)((__int64 (__fastcall *)(struct IMalloc *, __int64))v17->lpVtbl->Alloc)(v17, 0x2000);
    else
      v18 = HeapAlloc(g_hHeap, 0, 0x2000u);
    *((_QWORD *)this + 5) = v18;
    v16 = v18;
    if ( !v18 )
      return 2147942414LL;
    *((_QWORD *)this + 6) = v18 + 0x2000;
  }
  *((_QWORD *)this + 7) = v16;
  if ( !*((_BYTE *)a3 + 25) )
    goto LABEL_42;
  v20 = *((_DWORD *)this + 6);
  v21 = *((_BYTE *)a3 + 24);
  switch ( v20 )
  {
    case 1200:
      goto LABEL_40;
    case 12000:
      v23 = 0;
      if ( !v21 )
      {
        v23 = -1;
        LOBYTE(v6) = -2;
      }
      *v16 = -(v21 != 0);
      v16[1] = v21 != 0 ? 0xFE : 0;
      v16[2] = v6;
      v6 = 4;
      v16[3] = v23;
      break;
    case 65537:
LABEL_40:
      v6 = 2;
      *v16 = (v21 != 0) - 2;
      v16[1] = (v21 == 0) - 2;
      break;
  }
  *((_QWORD *)this + 7) += v6;
LABEL_42:
  v22 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 2);
  *((_QWORD *)this + 10) = a2;
  if ( v22 )
    (**v22)(v22, 1);
  *((_QWORD *)this + 2) = a3;
  return 0;
}

```

## disassembly

```asm
0x100422d70  mov     [rsp+arg_8], rbx
0x100422d75  mov     [rsp+arg_10], rbp
0x100422d7a  mov     [rsp+arg_18], rsi
0x100422d7f  push    rdi
0x100422d80  push    r14
0x100422d82  push    r15
0x100422d84  sub     rsp, 30h
0x100422d88  mov     rdi, r8
0x100422d8b  mov     dword ptr [rcx+1Ch], 3
0x100422d92  lea     r8, [rcx+1Ch]; unsigned int *
0x100422d96  mov     r15, rdx
0x100422d99  mov     rbx, rcx
0x100422d9c  lea     rdx, [rcx+18h]; unsigned int *
0x100422da0  xor     esi, esi
0x100422da2  mov     [rcx+20h], esi
0x100422da5  mov     rcx, [rdi+10h]; wchar_t *
0x100422da9  call    ?getCharsetInfo@CharEncoder@@SAHPEB_WPEAI1@Z; CharEncoder::getCharsetInfo(wchar_t const *,uint *,uint *)
0x100422dae  test    eax, eax
0x100422db0  js      loc_100422E53
0x100422db6  mov     ecx, [rbx+18h]
0x100422db9  cmp     ecx, 4B0h
0x100422dbf  jz      short loc_100422E3C
0x100422dc1  cmp     ecx, 2EE0h
0x100422dc7  jz      short loc_100422E21
0x100422dc9  cmp     ecx, 10001h
0x100422dcf  jz      short loc_100422E06
0x100422dd1  lea     rdx, ?charsetInfo@CharEncoder@@0QBUEncodingEntry@@B; EncodingEntry const near * const CharEncoder::charsetInfo
0x100422dd8  movsxd  rcx, eax
0x100422ddb  cmp     [rdi+1Ah], sil
0x100422ddf  jnz     short loc_100422DF8
0x100422de1  lea     rax, [rcx+rcx*4]
0x100422de5  cmp     [rdx+rax*8+4], sil
0x100422dea  jz      short loc_100422DF8
0x100422dec  lea     rax, ?wideCharToMultiByteWin32NoBestFit@CharEncoder@@SAJPEAKIPEA_WPEAIPEAE2@Z; CharEncoder::wideCharToMultiByteWin32NoBestFit(ulong *,uint,wchar_t *,uint *,uchar *,uint *)
0x100422df3  jmp     loc_100422F03
0x100422df8  lea     rax, [rcx+rcx*4]
0x100422dfc  mov     rax, [rdx+rax*8+20h]
0x100422e01  jmp     loc_100422F03
0x100422e06  cmp     [rdi+18h], sil
0x100422e0a  lea     rax, ?wideCharToUtf16Littleendian@CharEncoder@@SAJPEAKIPEA_WPEAIPEAE2@Z; CharEncoder::wideCharToUtf16Littleendian(ulong *,uint,wchar_t *,uint *,uchar *,uint *)
0x100422e11  lea     rcx, ?wideCharToUtf16Bigendian@CharEncoder@@SAJPEAKIPEA_WPEAIPEAE2@Z; CharEncoder::wideCharToUtf16Bigendian(ulong *,uint,wchar_t *,uint *,uchar *,uint *)
0x100422e18  cmovz   rax, rcx
0x100422e1c  jmp     loc_100422F03
0x100422e21  cmp     [rdi+18h], sil
0x100422e25  lea     rax, ?wideCharToUcs4Littleendian@CharEncoder@@SAJPEAKIPEA_WPEAIPEAE2@Z; CharEncoder::wideCharToUcs4Littleendian(ulong *,uint,wchar_t *,uint *,uchar *,uint *)
0x100422e2c  lea     rcx, ?wideCharToUcs4Bigendian@CharEncoder@@SAJPEAKIPEA_WPEAIPEAE2@Z; CharEncoder::wideCharToUcs4Bigendian(ulong *,uint,wchar_t *,uint *,uchar *,uint *)
0x100422e33  cmovz   rax, rcx
0x100422e37  jmp     loc_100422F03
0x100422e3c  cmp     [rdi+18h], sil
0x100422e40  lea     rax, ?wideCharToUtf16Bigendian@CharEncoder@@SAJPEAKIPEA_WPEAIPEAE2@Z; CharEncoder::wideCharToUtf16Bigendian(ulong *,uint,wchar_t *,uint *,uchar *,uint *)
0x100422e47  lea     rcx, ?wideCharToUtf16Littleendian@CharEncoder@@SAJPEAKIPEA_WPEAIPEAE2@Z; CharEncoder::wideCharToUtf16Littleendian(ulong *,uint,wchar_t *,uint *,uchar *,uint *)
0x100422e4e  jmp     loc_100422EFF
0x100422e53  cmp     eax, 0FFFFFFFFh
0x100422e56  jnz     loc_100423018
0x100422e5c  lfence
0x100422e5f  mov     rcx, cs:?s_pMultiLanguage2@@3PEAUIMultiLanguage2@@EA; IMultiLanguage2 * s_pMultiLanguage2
0x100422e66  mov     ebp, [rbx+18h]
0x100422e69  test    rcx, rcx
0x100422e6c  jnz     short loc_100422ED0
0x100422e6e  lea     rax, [rsp+48h+arg_0]
0x100422e73  mov     [rsp+48h+arg_0], rsi
0x100422e78  lea     r8d, [rcx+1]; dwClsContext
0x100422e7c  mov     [rsp+48h+ppv], rax; ppv
0x100422e81  lea     rcx, CLSID_CMultiLanguage; rclsid
0x100422e88  xor     edx, edx; pUnkOuter
0x100422e8a  lea     r9, IID_IMultiLanguage2; riid
0x100422e91  call    cs:__imp_CoCreateInstance
0x100422e97  test    eax, eax
0x100422e99  js      short loc_100422EC3
0x100422e9b  mov     rcx, [rsp+48h+arg_0]
0x100422ea0  xor     eax, eax
0x100422ea2  lock cmpxchg cs:?s_pMultiLanguage2@@3PEAUIMultiLanguage2@@EA, rcx; IMultiLanguage2 * s_pMultiLanguage2
0x100422eab  jz      short loc_100422EBF
0x100422ead  mov     rcx, [rsp+48h+arg_0]
0x100422eb2  mov     rax, [rcx]
0x100422eb5  mov     rax, [rax+10h]
0x100422eb9  call    cs:__guard_dispatch_icall_fptr
0x100422ebf  mov     eax, esi
0x100422ec1  test    eax, eax
0x100422ec3  jnz     loc_100423018
0x100422ec9  mov     rcx, cs:?s_pMultiLanguage2@@3PEAUIMultiLanguage2@@EA; IMultiLanguage2 * s_pMultiLanguage2
0x100422ed0  mov     rax, [rcx]
0x100422ed3  mov     r8d, ebp
0x100422ed6  mov     edx, 4B0h
0x100422edb  mov     rax, [rax+40h]
0x100422edf  call    cs:__guard_dispatch_icall_fptr
0x100422ee5  test    eax, eax
0x100422ee7  jnz     loc_100423018
0x100422eed  cmp     [rdi+1Ah], sil
0x100422ef1  lea     rax, ?wideCharToMultiByteMlangNoBestFit@CharEncoder@@SAJPEAKIPEA_WPEAIPEAE2@Z; CharEncoder::wideCharToMultiByteMlangNoBestFit(ulong *,uint,wchar_t *,uint *,uchar *,uint *)
0x100422ef8  lea     rcx, ?wideCharToMultiByteMlang@CharEncoder@@SAJPEAKIPEA_WPEAIPEAE2@Z; CharEncoder::wideCharToMultiByteMlang(ulong *,uint,wchar_t *,uint *,uchar *,uint *)
0x100422eff  cmovnz  rax, rcx
0x100422f03  mov     [rbx+60h], rax
0x100422f07  mov     r8, [rbx+28h]
0x100422f0b  test    r8, r8
0x100422f0e  jnz     short loc_100422F6F
0x100422f10  mov     rcx, [rbx+8]
0x100422f14  test    rcx, rcx
0x100422f17  jz      short loc_100422F2D
0x100422f19  mov     rax, [rcx]
0x100422f1c  mov     edx, 2000h
0x100422f21  mov     rax, [rax+18h]
0x100422f25  call    cs:__guard_dispatch_icall_fptr
0x100422f2b  jmp     short loc_100422F4E
0x100422f2d  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x100422f34  test    rcx, rcx
0x100422f37  jnz     short loc_100422F19
0x100422f39  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x100422f40  xor     edx, edx; dwFlags
0x100422f42  mov     r8d, 2000h; dwBytes
0x100422f48  call    cs:__imp_HeapAlloc
0x100422f4e  mov     [rbx+28h], rax
0x100422f52  mov     r8, rax
0x100422f55  test    rax, rax
0x100422f58  jnz     short loc_100422F64
0x100422f5a  mov     eax, 8007000Eh
0x100422f5f  jmp     loc_100423020
0x100422f64  lea     rax, [r8+2000h]
0x100422f6b  mov     [rbx+30h], rax
0x100422f6f  mov     [rbx+38h], r8
0x100422f73  cmp     [rdi+19h], sil
0x100422f77  jz      short loc_100422FB7
0x100422f79  mov     eax, [rbx+18h]
0x100422f7c  movzx   r9d, byte ptr [rdi+18h]
0x100422f81  cmp     eax, 4B0h
0x100422f86  jz      short loc_100422F96
0x100422f88  cmp     eax, 2EE0h
0x100422f8d  jz      short loc_100422FDD
0x100422f8f  cmp     eax, 10001h
0x100422f94  jnz     short loc_100422FB3
0x100422f96  test    r9b, r9b
0x100422f99  mov     esi, 2
0x100422f9e  setz    cl
0x100422fa1  add     cl, 0FEh
0x100422fa4  test    r9b, r9b
0x100422fa7  setnz   al
0x100422faa  add     al, 0FEh
0x100422fac  mov     [r8], al
0x100422faf  mov     [r8+1], cl
0x100422fb3  add     [rbx+38h], rsi
0x100422fb7  mov     rcx, [rbx+10h]
0x100422fbb  mov     [rbx+50h], r15
0x100422fbf  test    rcx, rcx
0x100422fc2  jz      short loc_100422FD5
0x100422fc4  mov     rax, [rcx]
0x100422fc7  mov     edx, 1
0x100422fcc  mov     rax, [rax]
0x100422fcf  call    cs:__guard_dispatch_icall_fptr
0x100422fd5  mov     [rbx+10h], rdi
0x100422fd9  xor     eax, eax
0x100422fdb  jmp     short loc_100423020
0x100422fdd  movzx   eax, r9b
0x100422fe1  mov     ecx, esi
0x100422fe3  neg     al
0x100422fe5  mov     eax, 0FFh
0x100422fea  sbb     dl, dl
0x100422fec  and     dl, 0FEh
0x100422fef  test    r9b, r9b
0x100422ff2  cmovz   ecx, eax
0x100422ff5  mov     eax, 0FEh
0x100422ffa  cmovz   esi, eax
0x100422ffd  neg     r9b
0x100423000  sbb     al, al
0x100423002  mov     [r8], al
0x100423005  mov     [r8+1], dl
0x100423009  mov     [r8+2], sil
0x10042300d  mov     esi, 4
0x100423012  mov     [r8+3], cl
0x100423016  jmp     short loc_100422FB3
0x100423018  lfence
0x10042301b  mov     eax, 0C00CE56Eh
0x100423020  mov     rbx, [rsp+48h+arg_8]
0x100423025  mov     rbp, [rsp+48h+arg_10]
0x10042302a  mov     rsi, [rsp+48h+arg_18]
0x10042302f  add     rsp, 30h
0x100423033  pop     r15
0x100423035  pop     r14
0x100423037  pop     rdi
0x100423038  retn
```
