# HTTP_REQUEST_HANDLE_OBJECT::InitBeginSendRequest(ushort const *,ulong,void * *,ulong *,unsigned __int64 *)

- ea: `0x1800298fc`
- end: `0x180029d3c`
- name: `?InitBeginSendRequest@HTTP_REQUEST_HANDLE_OBJECT@@QEAAKPEBGKPEAPEAXPEAKPEA_K@Z`
- size: `1088`
- prototype: `unsigned int __usercall@<eax>(HTTP_REQUEST_HANDLE_OBJECT *__hidden this@<rcx>, LPCWSTR lpszHeaders@<rdx>, unsigned int@<r8d>, void **@<r9>, unsigned int *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180027880`

## callees

- `0x18000eae8`
- `0x180010a5c`
- `0x18001ce20`
- `0x180028f60`
- `0x1800298fc`
- `0x180029d50`
- `0x18002a9b8`
- `0x1800388d4`
- `0x180041eb0`
- `0x18004aa40`
- `0x1800a1d10`
- `0x1800a3da8`
- `0x1800b4d9c`
- `0x1800d4b1c`
- `0x1800db6b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__strtoui64` at `0x180029c96`
- `api-ms-win-crt-private-l1-1-0!_o__strtoui64` at `0x180029c96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029a72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029a72`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180029bc6`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180029bf1`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180029bc6`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180029bf1`

## pseudocode

```c
__int64 __fastcall HTTP_REQUEST_HANDLE_OBJECT::InitBeginSendRequest(
        HTTP_REQUEST_HANDLE_OBJECT *this,
        LPCWSTR lpszHeaders,
        int a3,
        void **a4,
        unsigned int *a5,
        unsigned __int64 *a6)
{
  __int64 v7; // rsi
  void *v10; // r9
  unsigned int v11; // eax
  void *v12; // r15
  __int64 v13; // rcx
  LPCWSTR v14; // rax
  unsigned int LastError; // ebx
  int v16; // r9d
  int v17; // eax
  int v18; // ecx
  bool v19; // cf
  char *v20; // rax
  int v21; // eax
  unsigned int v22; // esi
  __int64 v23; // rdx
  int v24; // esi
  __int64 v25; // rax
  unsigned __int64 v26; // rcx
  int v27; // edx
  PCNZCH lpString2; // [rsp+20h] [rbp-79h]
  unsigned int v30; // [rsp+30h] [rbp-69h]
  unsigned __int64 v31; // [rsp+38h] [rbp-61h]
  void *v32; // [rsp+40h] [rbp-59h]
  char *v34; // [rsp+58h] [rbp-41h] BYREF
  void *v35; // [rsp+60h] [rbp-39h] BYREF
  __int64 v36; // [rsp+68h] [rbp-31h]
  unsigned int v37; // [rsp+70h] [rbp-29h] BYREF
  unsigned int v38; // [rsp+74h] [rbp-25h] BYREF
  char v39[24]; // [rsp+78h] [rbp-21h] BYREF

  LODWORD(v7) = a3;
  v10 = 0;
  if ( (xmmword_180107A60 & 2) != 0 )
  {
    if ( a5 )
      v11 = *a5;
    else
      v11 = 0;
    if ( a4 )
      v10 = *a4;
    LODWORD(lpString2) = v11;
    WPP_SF_qdI(1025, 10, WPP_95f422c10c41397b1fe4c9080434197a_Traceguids, v10);
  }
  v12 = 0;
  v32 = *a4;
  v31 = *a6;
  v35 = 0;
  v36 = 0;
  if ( !v32 || (v30 = *a5) == 0 )
  {
    v32 = 0;
    v30 = 0;
  }
  if ( (_DWORD)v7 != -1 )
  {
    if ( !lpszHeaders )
      goto LABEL_25;
    goto LABEL_21;
  }
  if ( !lpszHeaders )
    goto LABEL_25;
  v13 = 0x7FFFFFFF;
  LODWORD(v34) = 0;
  v14 = lpszHeaders;
  do
  {
    if ( !*v14 )
      break;
    ++v14;
    --v13;
  }
  while ( v13 );
  v7 = (0x7FFFFFFF - v13) & -(__int64)(v13 != 0);
  if ( !v13 )
    LODWORD(v7) = 0;
  LastError = WX_WIN32_FROM_HR(v13 == 0 ? 0x80070057 : 0);
  if ( !LastError )
  {
LABEL_21:
    if ( *lpszHeaders )
    {
      if ( !WinHttpAddRequestHeaders(
              *((HINTERNET *)this + 4),
              lpszHeaders,
              v7,
              *((_DWORD *)this + 247) != 0 ? -1610612736 : 0x20000000) )
      {
        LastError = GetLastError();
        goto LABEL_58;
      }
      *((_DWORD *)this + 247) = 1;
    }
LABEL_25:
    *((_DWORD *)this + 202) = 0;
    LastError = 0;
    if ( !(unsigned int)CWebIORequestHeadersShim::IsHeaderPresent(
                          (HTTP_REQUEST_HANDLE_OBJECT *)((char *)this + 680),
                          0x27u) )
    {
      v16 = *((_DWORD *)this + 30) != 0 ? *((_DWORD *)this + 30) - 1 : 0;
      if ( (unsigned int)(v16 - 1) <= 0xFFFD )
        CWebIORequestHeadersShim::SetHeader(
          (HTTP_REQUEST_HANDLE_OBJECT *)((char *)this + 680),
          0x27u,
          *((const char **)this + 14),
          v16);
    }
    if ( (*((_BYTE *)this + 408) & 4) != 0 )
    {
      v17 = *((_DWORD *)this + 100);
      v18 = v17 - 1;
      v19 = v17 != 0;
      v20 = (char *)this + 392;
    }
    else
    {
      v21 = *((_DWORD *)this + 96);
      v18 = v21 - 1;
      v19 = v21 != 0;
      v20 = (char *)this + 376;
    }
    v22 = *((unsigned __int16 *)this + 206);
    v23 = v18 & (unsigned int)-v19;
    if ( v22 != 80 && (_WORD)v22 != 443 )
    {
      LastError = CStringTemplate<unsigned short>::SetString(&v35, *(_QWORD *)v20, (unsigned int)v23, v23 + 12);
      if ( LastError
        || (LastError = CStringTemplate<unsigned short>::Append((__int64)&v35, L":", 1u)) != 0
        || (LastError = CStringTemplate<unsigned short>::AppendDecimalDword((__int64)&v35, v22)) != 0 )
      {
        v12 = v35;
        goto LABEL_58;
      }
      if ( (_DWORD)v36 )
        LODWORD(v23) = v36 - 1;
      else
        LODWORD(v23) = 0;
      v12 = v35;
    }
    if ( (unsigned int)v23 >= 0xFFFF )
      HTTP_REQUEST_HANDLE_OBJECT::RemoveAllRequestHeadersByName(this, v23);
    if ( (unsigned int)CWebIORequestHeadersShim::IsHeaderPresent(
                         (HTTP_REQUEST_HANDLE_OBJECT *)((char *)this + 680),
                         0x3Fu)
      && (CompareStringA(0x7Fu, 1u, *((PCNZCH *)this + 97), -1, "GET", -1) == 2
       || CompareStringA(0x7Fu, 1u, *((PCNZCH *)this + 97), -1, "HEAD", -1) == 2) )
    {
LABEL_45:
      LastError = 87;
      goto LABEL_58;
    }
    v24 = 0;
    if ( (unsigned int)IsTransferEncodingPresent((HTTP_REQUEST_HANDLE_OBJECT *)((char *)this + 680)) )
    {
      *((_DWORD *)this + 168) |= 0x800u;
      v24 = 1;
    }
    v38 = 21;
    strcpy(v39, "18446744073709551615");
    v37 = 0;
    if ( HTTP_REQUEST_HANDLE_OBJECT::QueryInfo(this, 0x80000005, 0, v39, &v38, &v37) )
    {
      v26 = v31;
    }
    else
    {
      if ( v24 )
        goto LABEL_45;
      v34 = v39;
      v25 = _o__strtoui64(v39, &v34, 10);
      if ( *v34 )
        goto LABEL_45;
      v26 = v25;
      v31 = v25;
    }
    if ( a5 )
    {
      v27 = LastError;
      if ( *a5 > v26 )
        v27 = 87;
      LastError = v27;
    }
  }
LABEL_58:
  *a4 = v32;
  *a5 = v30;
  *a6 = v31;
  if ( (xmmword_180107A60 & 2) != 0 )
    WPP_SF_d(1025, 11, WPP_95f422c10c41397b1fe4c9080434197a_Traceguids, LastError, lpString2);
  if ( v12 )
    operator delete(v12);
  return LastError;
}

```

## disassembly

```asm
0x1800298fc  push    rbp
0x1800298fe  push    rbx
0x1800298ff  push    rsi
0x180029900  push    rdi
0x180029901  push    r12
0x180029903  push    r13
0x180029905  push    r14
0x180029907  push    r15
0x180029909  lea     rbp, [rsp-0Fh]
0x18002990e  sub     rsp, 0A8h
0x180029915  mov     rax, cs:__security_cookie
0x18002991c  xor     rax, rsp
0x18002991f  mov     [rbp+47h+var_50], rax
0x180029923  mov     r12, [rbp+47h+arg_20]
0x180029927  mov     rbx, r9
0x18002992a  mov     r13, [rbp+47h+arg_28]
0x18002992e  mov     esi, r8d
0x180029931  mov     [rbp+47h+var_90], rbx
0x180029935  mov     r14, rdx
0x180029938  mov     rdi, rcx
0x18002993b  xor     r9d, r9d
0x18002993e  test    byte ptr cs:xmmword_180107A60, 2
0x180029945  jz      short loc_18002998D
0x180029947  test    r13, r13
0x18002994a  jz      short loc_180029952
0x18002994c  mov     r8, [r13+0]
0x180029950  jmp     short loc_180029955
0x180029952  mov     r8, r9
0x180029955  test    r12, r12
0x180029958  jz      short loc_180029960
0x18002995a  mov     eax, [r12]
0x18002995e  jmp     short loc_180029963
0x180029960  mov     eax, r9d
0x180029963  test    rbx, rbx
0x180029966  jz      short loc_18002996B
0x180029968  mov     r9, [rbx]
0x18002996b  mov     qword ptr [rsp+0E0h+cchCount2], r8
0x180029970  mov     edx, 0Ah
0x180029975  lea     r8, WPP_95f422c10c41397b1fe4c9080434197a_Traceguids
0x18002997c  mov     dword ptr [rsp+0E0h+lpString2], eax
0x180029980  mov     ecx, 401h
0x180029985  call    WPP_SF_qdI
0x18002998a  xor     r9d, r9d
0x18002998d  mov     rcx, [rbx]
0x180029990  mov     r15, r9
0x180029993  mov     rax, [r13+0]
0x180029997  mov     [rbp+47h+var_A0], rcx
0x18002999b  mov     [rbp+47h+var_A8], rax
0x18002999f  mov     [rbp+47h+var_80], r9
0x1800299a3  mov     [rbp+47h+var_78], 0
0x1800299ab  test    rcx, rcx
0x1800299ae  jz      short loc_1800299BB
0x1800299b0  mov     eax, [r12]
0x1800299b4  mov     [rbp+47h+var_B0], eax
0x1800299b7  test    eax, eax
0x1800299b9  jnz     short loc_1800299C3
0x1800299bb  mov     [rbp+47h+var_A0], r9
0x1800299bf  mov     [rbp+47h+var_B0], r9d
0x1800299c3  cmp     esi, 0FFFFFFFFh
0x1800299c6  jnz     short loc_180029A38
0x1800299c8  test    r14, r14
0x1800299cb  jz      loc_180029A89
0x1800299d1  mov     r8d, 7FFFFFFFh
0x1800299d7  mov     [rbp+47h+var_94], r9d
0x1800299db  mov     ecx, r8d
0x1800299de  mov     dword ptr [rbp+47h+var_88], r9d
0x1800299e2  mov     rax, r14
0x1800299e5  cmp     [rax], r9w
0x1800299e9  jz      short loc_1800299F5
0x1800299eb  add     rax, 2
0x1800299ef  sub     rcx, 1
0x1800299f3  jnz     short loc_1800299E5
0x1800299f5  mov     rax, rcx
0x1800299f8  neg     rax
0x1800299fb  mov     rax, rcx
0x1800299fe  sbb     edx, edx
0x180029a00  sub     r8, rcx
0x180029a03  not     edx
0x180029a05  and     edx, 80070057h
0x180029a0b  neg     rax
0x180029a0e  sbb     rsi, rsi
0x180029a11  and     rsi, r8
0x180029a14  test    rcx, rcx
0x180029a17  jnz     short loc_180029A23
0x180029a19  mov     [rbp+47h+var_94], 51h ; 'Q'
0x180029a20  mov     esi, r9d
0x180029a23  mov     ecx, edx
0x180029a25  call    WX_WIN32_FROM_HR
0x180029a2a  xor     r9d, r9d
0x180029a2d  mov     ebx, eax
0x180029a2f  test    eax, eax
0x180029a31  jz      short loc_180029A3D
0x180029a33  jmp     loc_180029CD1
0x180029a38  test    r14, r14
0x180029a3b  jz      short loc_180029A89
0x180029a3d  cmp     [r14], r9w
0x180029a41  jz      short loc_180029A89
0x180029a43  mov     eax, [rdi+3DCh]
0x180029a49  mov     r8d, esi; dwHeadersLength
0x180029a4c  mov     rcx, [rdi+20h]; hRequest
0x180029a50  neg     eax
0x180029a52  mov     rdx, r14; lpszHeaders
0x180029a55  sbb     r9d, r9d
0x180029a58  and     r9d, 80000000h
0x180029a5f  add     r9d, 20000000h; dwModifiers
0x180029a66  call    WinHttpAddRequestHeaders
0x180029a6b  xor     r9d, r9d
0x180029a6e  test    eax, eax
0x180029a70  jnz     short loc_180029A7F
0x180029a72  call    cs:__imp_GetLastError
0x180029a78  mov     ebx, eax
0x180029a7a  jmp     loc_180029CD1
0x180029a7f  mov     dword ptr [rdi+3DCh], 1
0x180029a89  lea     r14, [rdi+2A8h]
0x180029a90  mov     [rdi+328h], r9d
0x180029a97  mov     esi, 27h ; '''
0x180029a9c  mov     rcx, r14; this
0x180029a9f  mov     edx, esi; unsigned int
0x180029aa1  mov     ebx, r9d
0x180029aa4  call    ?IsHeaderPresent@CWebIORequestHeadersShim@@QEAAHK@Z; CWebIORequestHeadersShim::IsHeaderPresent(ulong)
0x180029aa9  test    eax, eax
0x180029aab  jnz     short loc_180029AD4
0x180029aad  mov     eax, [rdi+78h]
0x180029ab0  lea     ecx, [rax-1]
0x180029ab3  neg     eax
0x180029ab5  sbb     r9d, r9d
0x180029ab8  and     r9d, ecx; unsigned __int16
0x180029abb  lea     eax, [r9-1]
0x180029abf  cmp     eax, 0FFFDh
0x180029ac4  ja      short loc_180029AD4
0x180029ac6  mov     r8, [rdi+70h]; char *
0x180029aca  mov     edx, esi; unsigned int
0x180029acc  mov     rcx, r14; this
0x180029acf  call    ?SetHeader@CWebIORequestHeadersShim@@QEAAKKPEBDG@Z; CWebIORequestHeadersShim::SetHeader(ulong,char const *,ushort)
0x180029ad4  test    byte ptr [rdi+198h], 4
0x180029adb  jz      short loc_180029AF1
0x180029add  mov     eax, [rdi+190h]
0x180029ae3  lea     ecx, [rax-1]
0x180029ae6  neg     eax
0x180029ae8  lea     rax, [rdi+188h]
0x180029aef  jmp     short loc_180029B03
0x180029af1  mov     eax, [rdi+180h]
0x180029af7  lea     ecx, [rax-1]
0x180029afa  neg     eax
0x180029afc  lea     rax, [rdi+178h]
0x180029b03  movzx   esi, word ptr [rdi+19Ch]
0x180029b0a  sbb     edx, edx
0x180029b0c  and     edx, ecx
0x180029b0e  cmp     esi, 50h ; 'P'
0x180029b11  jz      short loc_180029B82
0x180029b13  mov     ecx, 1BBh
0x180029b18  cmp     si, cx
0x180029b1b  jz      short loc_180029B82
0x180029b1d  mov     r8d, edx
0x180029b20  lea     r9, [rdx+0Ch]
0x180029b24  mov     rdx, [rax]
0x180029b27  lea     rcx, [rbp+47h+var_80]
0x180029b2b  call    ?SetString@?$CStringTemplate@G@@QEAAKPEBG_K1@Z; CStringTemplate<ushort>::SetString(ushort const *,unsigned __int64,unsigned __int64)
0x180029b30  mov     ebx, eax
0x180029b32  test    eax, eax
0x180029b34  jnz     loc_180029C06
0x180029b3a  lea     r8d, [rax+1]
0x180029b3e  lea     rdx, asc_1800E6F78; ":"
0x180029b45  lea     rcx, [rbp+47h+var_80]
0x180029b49  call    ?Append@?$CStringTemplate@G@@QEAAKPEBG_K@Z; CStringTemplate<ushort>::Append(ushort const *,unsigned __int64)
0x180029b4e  mov     ebx, eax
0x180029b50  test    eax, eax
0x180029b52  jnz     loc_180029C06
0x180029b58  mov     edx, esi
0x180029b5a  lea     rcx, [rbp+47h+var_80]
0x180029b5e  call    ?AppendDecimalDword@?$CStringTemplate@G@@QEAAKK@Z; CStringTemplate<ushort>::AppendDecimalDword(ulong)
0x180029b63  xor     r9d, r9d
0x180029b66  mov     ebx, eax
0x180029b68  test    eax, eax
0x180029b6a  jnz     loc_180029C06
0x180029b70  mov     edx, dword ptr [rbp+47h+var_78]
0x180029b73  test    edx, edx
0x180029b75  jz      short loc_180029B7B
0x180029b77  dec     edx
0x180029b79  jmp     short loc_180029B7E
0x180029b7b  mov     edx, r9d; unsigned int
0x180029b7e  mov     r15, [rbp+47h+var_80]
0x180029b82  cmp     edx, 0FFFFh
0x180029b88  jb      short loc_180029B92
0x180029b8a  mov     rcx, rdi; this
0x180029b8d  call    ?RemoveAllRequestHeadersByName@HTTP_REQUEST_HANDLE_OBJECT@@QEAAKK@Z; HTTP_REQUEST_HANDLE_OBJECT::RemoveAllRequestHeadersByName(ulong)
0x180029b92  mov     edx, 3Fh ; '?'; unsigned int
0x180029b97  mov     rcx, r14; this
0x180029b9a  call    ?IsHeaderPresent@CWebIORequestHeadersShim@@QEAAHK@Z; CWebIORequestHeadersShim::IsHeaderPresent(ulong)
0x180029b9f  test    eax, eax
0x180029ba1  jz      short loc_180029C0F
0x180029ba3  mov     r8, [rdi+308h]; lpString1
0x180029baa  lea     rax, aGet_0; "GET"
0x180029bb1  or      esi, 0FFFFFFFFh
0x180029bb4  mov     [rsp+0E0h+cchCount2], esi; cchCount2
0x180029bb8  mov     r9d, esi; cchCount1
0x180029bbb  mov     [rsp+0E0h+lpString2], rax; lpString2
0x180029bc0  lea     edx, [rsi+2]; dwCmpFlags
0x180029bc3  lea     ecx, [rdx+7Eh]; Locale
0x180029bc6  call    cs:__imp_CompareStringA
0x180029bcc  cmp     eax, 2
0x180029bcf  jz      short loc_180029BFC
0x180029bd1  mov     r8, [rdi+308h]; lpString1
0x180029bd8  lea     edx, [rsi+2]; dwCmpFlags
0x180029bdb  lea     rax, aHead; "HEAD"
0x180029be2  mov     [rsp+0E0h+cchCount2], esi; cchCount2
0x180029be6  lea     ecx, [rdx+7Eh]; Locale
0x180029be9  mov     [rsp+0E0h+lpString2], rax; lpString2
0x180029bee  mov     r9d, esi; cchCount1
0x180029bf1  call    cs:__imp_CompareStringA
0x180029bf7  cmp     eax, 2
0x180029bfa  jnz     short loc_180029C0F
0x180029bfc  mov     ebx, 57h ; 'W'
0x180029c01  jmp     loc_180029CD1
0x180029c06  mov     r15, [rbp+47h+var_80]
0x180029c0a  jmp     loc_180029CD1
0x180029c0f  mov     rcx, r14; struct CRequestParameters *
0x180029c12  xor     esi, esi
0x180029c14  call    ?IsTransferEncodingPresent@@YAHPEBVCRequestParameters@@@Z; IsTransferEncodingPresent(CRequestParameters const *)
0x180029c19  test    eax, eax
0x180029c1b  jz      short loc_180029C2A
0x180029c1d  bts     dword ptr [rdi+2A0h], 0Bh
0x180029c25  mov     esi, 1
0x180029c2a  movups  xmm0, xmmword ptr cs:a18446744073709; "18446744073709551615"
0x180029c31  lea     rax, [rbp+47h+var_70]
0x180029c35  xor     r8d, r8d; char *
0x180029c38  movsd   xmm1, qword ptr cs:a18446744073709+0Dh; "9551615"
0x180029c40  lea     r9, [rbp+47h+var_68]; void *
0x180029c44  mov     qword ptr [rsp+0E0h+cchCount2], rax; unsigned int *
0x180029c49  mov     edx, 80000005h; unsigned int
0x180029c4e  lea     rax, [rbp+47h+var_6C]
0x180029c52  mov     [rbp+47h+var_6C], 15h
0x180029c59  movups  xmmword ptr [rbp+47h+var_68], xmm0
0x180029c5d  mov     rcx, rdi; this
0x180029c60  mov     [rsp+0E0h+lpString2], rax; unsigned int *
0x180029c65  movsd   qword ptr [rbp+47h+var_68+0Dh], xmm1
0x180029c6a  mov     [rbp+47h+var_70], 0
0x180029c71  call    ?QueryInfo@HTTP_REQUEST_HANDLE_OBJECT@@QEAAKKPEBDPEAXPEAK2@Z; HTTP_REQUEST_HANDLE_OBJECT::QueryInfo(ulong,char const *,void *,ulong *,ulong *)
0x180029c76  test    eax, eax
0x180029c78  jnz     short loc_180029CB5
0x180029c7a  test    esi, esi
0x180029c7c  jnz     loc_180029BFC
0x180029c82  lea     rax, [rbp+47h+var_68]
0x180029c86  lea     r8d, [rsi+0Ah]
0x180029c8a  mov     [rbp+47h+var_88], rax
0x180029c8e  lea     rdx, [rbp+47h+var_88]
0x180029c92  lea     rcx, [rbp+47h+var_68]
0x180029c96  call    cs:__imp__o__strtoui64
0x180029c9c  mov     rcx, [rbp+47h+var_88]
0x180029ca0  xor     r9d, r9d
0x180029ca3  cmp     [rcx], r9b
0x180029ca6  jnz     loc_180029BFC
0x180029cac  mov     rcx, rax
0x180029caf  mov     [rbp+47h+var_A8], rax
0x180029cb3  jmp     short loc_180029CB9
0x180029cb5  mov     rcx, [rbp+47h+var_A8]
0x180029cb9  test    r12, r12
0x180029cbc  jz      short loc_180029CD1
0x180029cbe  mov     eax, [r12]
0x180029cc2  mov     edx, ebx
0x180029cc4  mov     ebx, 57h ; 'W'
0x180029cc9  cmp     rax, rcx
0x180029ccc  cmova   edx, ebx
0x180029ccf  mov     ebx, edx
0x180029cd1  mov     rax, [rbp+47h+var_A0]
0x180029cd5  mov     rdx, [rbp+47h+var_90]
0x180029cd9  mov     [rdx], rax
0x180029cdc  mov     eax, [rbp+47h+var_B0]
0x180029cdf  mov     [r12], eax
0x180029ce3  mov     rax, [rbp+47h+var_A8]
0x180029ce7  mov     [r13+0], rax
0x180029ceb  test    byte ptr cs:xmmword_180107A60, 2
0x180029cf2  jz      short loc_180029D0D
0x180029cf4  mov     edx, 0Bh
0x180029cf9  lea     r8, WPP_95f422c10c41397b1fe4c9080434197a_Traceguids
0x180029d00  mov     ecx, 401h
0x180029d05  mov     r9d, ebx
0x180029d08  call    WPP_SF_d
0x180029d0d  test    r15, r15
0x180029d10  jz      short loc_180029D1A
0x180029d12  mov     rcx, r15; void *
0x180029d15  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180029d1a  mov     eax, ebx
0x180029d1c  mov     rcx, [rbp+47h+var_50]
0x180029d20  xor     rcx, rsp; StackCookie
0x180029d23  call    __security_check_cookie
0x180029d28  add     rsp, 0A8h
0x180029d2f  pop     r15
0x180029d31  pop     r14
0x180029d33  pop     r13
0x180029d35  pop     r12
0x180029d37  pop     rdi
0x180029d38  pop     rsi
0x180029d39  pop     rbx
0x180029d3a  pop     rbp
0x180029d3b  retn
```
