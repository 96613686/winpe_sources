# CImage::ExtractFiles(ushort const *,ulong,ushort * *,ulong)

- ea: `0x18000a13c`
- end: `0x18000a56a`
- name: `?ExtractFiles@CImage@@QEAAJPEBGKPEAPEAGK@Z`
- size: `1070`
- prototype: `int(CImage *__hidden this, const unsigned __int16 *, unsigned int, unsigned __int16 **, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180004530`

## callees

- `0x1800015d8`
- `0x1800072d4`
- `0x1800073c0`
- `0x18000a13c`
- `0x18000d5b0`
- `0x18000d6b0`
- `0x18000ff10`
- `0x180011010`

## import_xrefs

- `msvcrt!wcschr` at `0x18000a43c`
- `msvcrt!wcschr` at `0x18000a43c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a4d4`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a4ee`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a4d4`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a4ee`
- `KERNEL32!GetFullPathNameW` at `0x18000a211`
- `KERNEL32!GetFullPathNameW` at `0x18000a2a0`
- `KERNEL32!GetFullPathNameW` at `0x18000a211`
- `KERNEL32!GetFullPathNameW` at `0x18000a2a0`
- `KERNEL32!DeleteCriticalSection` at `0x18000a529`
- `KERNEL32!DeleteCriticalSection` at `0x18000a529`
- `KERNEL32!InitializeCriticalSection` at `0x18000a195`
- `KERNEL32!InitializeCriticalSection` at `0x18000a195`
- `KERNEL32!DeleteFileW` at `0x18000a4b3`
- `KERNEL32!DeleteFileW` at `0x18000a4b3`
- `KERNEL32!GetFileAttributesW` at `0x18000a48b`
- `KERNEL32!GetFileAttributesW` at `0x18000a48b`
- `KERNEL32!GetLastError` at `0x18000a223`
- `KERNEL32!GetLastError` at `0x18000a2b0`
- `KERNEL32!GetLastError` at `0x18000a223`
- `KERNEL32!GetLastError` at `0x18000a2b0`
- `ImageLib!IID_IDepImageResolvedFileBased` at `0x18000a34e`
- `WdsCommonLib!WdsDeleteDirectory` at `0x18000a4a5`
- `WdsCommonLib!WdsDeleteDirectory` at `0x18000a4a5`
- `WdsCommonLib!ConcatenatePaths` at `0x18000a2d9`
- `WdsCommonLib!ConcatenatePaths` at `0x18000a2d9`

## pseudocode

```c
__int64 __fastcall CImage::ExtractFiles(
        CImage *this,
        const unsigned __int16 *a2,
        char a3,
        unsigned __int16 **a4,
        unsigned int a5)
{
  WCHAR *v5; // rsi
  __int64 v10; // rdx
  bool v11; // zf
  __int64 v12; // rbx
  DWORD FullPathNameW; // ebx
  DWORD LastError; // eax
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  int v18; // eax
  DWORD v19; // ebx
  unsigned __int64 v20; // rax
  WCHAR *v21; // rax
  unsigned int i; // edi
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // rcx
  unsigned int v28; // eax
  __int64 v29; // rdx
  __int64 v30; // r9
  __int64 v31; // rcx
  int v32; // eax
  __int64 v33; // rdx
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // rdi
  wchar_t *v37; // rax
  WCHAR *v38; // rcx
  __int64 j; // rdi
  DWORD FileAttributesW; // eax
  __int64 v41; // rcx
  LPCWSTR lpFileName; // [rsp+20h] [rbp-B1h] BYREF
  unsigned int v44; // [rsp+28h] [rbp-A9h] BYREF
  __int64 v45; // [rsp+30h] [rbp-A1h] BYREF
  __int64 v46; // [rsp+38h] [rbp-99h] BYREF
  int v47; // [rsp+40h] [rbp-91h]
  unsigned int v48; // [rsp+44h] [rbp-8Dh]
  __int64 v49; // [rsp+50h] [rbp-81h] BYREF
  int v50; // [rsp+58h] [rbp-79h]
  unsigned int v51; // [rsp+5Ch] [rbp-75h]
  _OWORD v52[2]; // [rsp+68h] [rbp-69h] BYREF
  __int128 v53; // [rsp+88h] [rbp-49h]
  __int64 v54; // [rsp+98h] [rbp-39h]
  _RTL_CRITICAL_SECTION CriticalSection; // [rsp+A0h] [rbp-31h] BYREF
  _QWORD v56[4]; // [rsp+C8h] [rbp-9h] BYREF

  v44 = 0;
  v5 = 0;
  lpFileName = 0;
  v46 = 0;
  v47 = 0;
  v48 = 0;
  v49 = 0;
  v50 = 0;
  v51 = 0;
  InitializeCriticalSection(&CriticalSection);
  v45 = 0;
  v56[0] = &v46;
  v56[1] = &v49;
  v56[2] = &CriticalSection;
  v56[3] = &v44;
  v11 = *((_DWORD *)this + 7) == 2;
  memset(v52, 0, sizeof(v52));
  v54 = 0;
  v53 = 0;
  if ( !v11 )
  {
    LODWORD(v12) = -2147024846;
    if ( (int)ElValidateHr_5(2147942450LL, v10, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 2004) < 0 )
      goto LABEL_31;
  }
  FullPathNameW = GetFullPathNameW(a2, 0, 0, 0);
  if ( !FullPathNameW )
  {
    LastError = GetLastError();
    v17 = 2013;
LABEL_5:
    v18 = ElValidateWin32_4(LastError, v15, v16, v17);
    LODWORD(v12) = v18;
    if ( v18 > 0 )
      LODWORD(v12) = (unsigned __int16)v18 | 0x80070000;
    if ( (int)v12 >= 0 )
      LODWORD(v12) = -2147467259;
    goto LABEL_31;
  }
  v19 = FullPathNameW + 1;
  v20 = 2LL * v19;
  if ( !is_mul_ok(v19, 2u) )
    v20 = -1;
  v21 = (WCHAR *)operator new[](v20, (const struct std::nothrow_t *)&std::nothrow);
  v5 = v21;
  if ( !v21 )
  {
    LODWORD(v12) = -2147024882;
    goto LABEL_31;
  }
  if ( !GetFullPathNameW(a2, v19, v21, 0) )
  {
    LastError = GetLastError();
    v17 = 2025;
    goto LABEL_5;
  }
  for ( i = 0; i < a5; ++a4 )
  {
    v12 = (unsigned int)ConcatenatePaths(v5, *a4, &lpFileName);
    if ( (unsigned int)ElValidateWin32_4(v12, v23, v24, 2037) )
      goto LABEL_29;
    v12 = (unsigned int)CDynArray<WdsImgParentImage *,CDeallocatePointer>::AddItem(&v46, lpFileName);
    if ( (unsigned int)ElValidateWin32_4(v12, v25, v26, 2040) )
      goto LABEL_29;
    lpFileName = 0;
    ++i;
  }
  v27 = *((_QWORD *)this + 49) + 8LL + *(int *)(*(_QWORD *)(*((_QWORD *)this + 49) + 8LL) + 4LL);
  v28 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v27 + 24LL))(
          v27,
          *(_QWORD *)&IID_IDepImageResolvedFileBased.Data1,
          &v45);
  LODWORD(v12) = v28;
  if ( v28 == -2147467262 )
  {
    LODWORD(v12) = -1056832998;
    v30 = 2056;
    v31 = 3238134298LL;
  }
  else
  {
    v30 = 2060;
    v31 = v28;
  }
  if ( (int)ElValidateHr_5(v31, v29, "base\\eco\\wds\\wdsimage\\src\\image.cpp", v30) >= 0 )
  {
    v32 = 4;
    *((_QWORD *)&v52[0] + 1) = v5;
    *(_QWORD *)&v53 = CImage::_WimExtractCallback;
    *((_QWORD *)&v53 + 1) = v56;
    if ( (a3 & 1) != 0 )
      v32 = 12;
    LODWORD(v52[0]) = v32;
    v12 = (**(unsigned int (__fastcall ***)(__int64, _OWORD *))v45)(v45, v52);
    if ( (int)ElValidateHr_5(v12, v33, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 2078) >= 0
      && v44
      && (unsigned int)ElValidateWin32_4(v44, v34, v35, 2082) )
    {
      LODWORD(v12) = v44;
LABEL_29:
      if ( (int)v12 > 0 )
        LODWORD(v12) = (unsigned __int16)v12 | 0x80070000;
    }
  }
LABEL_31:
  if ( (a3 & 0x20) == 0 )
  {
    v36 = 0;
    if ( v48 )
    {
      while ( 1 )
      {
        lpFileName = *(LPCWSTR *)(v46 + 8 * v36);
        v37 = wcschr(lpFileName, 0x2Au);
        v38 = 0;
        lpFileName = 0;
        if ( !v37 )
          break;
        v36 = (unsigned int)(v36 + 1);
        if ( (unsigned int)v36 >= v48 )
          goto LABEL_38;
      }
      LODWORD(v12) = -2147024894;
      goto LABEL_39;
    }
  }
  v38 = (WCHAR *)lpFileName;
LABEL_38:
  if ( (int)v12 < 0 )
  {
LABEL_39:
    for ( j = 0; (unsigned int)j < v51; lpFileName = 0 )
    {
      lpFileName = *(LPCWSTR *)(v49 + 8 * j);
      FileAttributesW = GetFileAttributesW(lpFileName);
      if ( FileAttributesW != -1 )
      {
        if ( (FileAttributesW & 0x10) != 0 )
          WdsDeleteDirectory(lpFileName);
        else
          DeleteFileW(lpFileName);
      }
      v38 = 0;
      j = (unsigned int)(j + 1);
    }
  }
  if ( v38 )
  {
    operator delete(v38);
    lpFileName = 0;
  }
  if ( v5 )
    operator delete(v5);
  if ( v45 )
  {
    v41 = v45 + 8 + *(int *)(*(_QWORD *)(v45 + 8) + 4LL);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    v45 = 0;
  }
  DeleteCriticalSection(&CriticalSection);
  CDynArray<unsigned short *,CDeallocateString>::~CDynArray<unsigned short *,CDeallocateString>(&v49);
  CDynArray<unsigned short *,CDeallocateString>::~CDynArray<unsigned short *,CDeallocateString>(&v46);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000a13c  push    rbp
0x18000a13e  push    rbx
0x18000a13f  push    rsi
0x18000a140  push    rdi
0x18000a141  push    r12
0x18000a143  push    r13
0x18000a145  push    r15
0x18000a147  lea     rbp, [rsp-1Fh]
0x18000a14c  sub     rsp, 0F0h
0x18000a153  mov     rax, cs:__security_cookie
0x18000a15a  xor     rax, rsp
0x18000a15d  mov     [rbp+4Fh+var_38], rax
0x18000a161  and     [rsp+120h+var_F8], 0
0x18000a166  xor     esi, esi
0x18000a168  and     [rsp+120h+lpFileName], rsi
0x18000a16d  mov     r13, rcx
0x18000a170  and     [rsp+120h+var_E8], rsi
0x18000a175  lea     rcx, [rbp+4Fh+CriticalSection]; lpCriticalSection
0x18000a179  and     [rsp+120h+var_E0], esi
0x18000a17d  mov     r15, r9
0x18000a180  and     [rsp+120h+var_DC], esi
0x18000a184  mov     r12d, r8d
0x18000a187  and     [rsp+120h+var_D0], rsi
0x18000a18c  mov     rdi, rdx
0x18000a18f  and     [rbp+4Fh+var_C8], esi
0x18000a192  and     [rbp+4Fh+var_C4], esi
0x18000a195  call    cs:__imp_InitializeCriticalSection
0x18000a19c  nop     dword ptr [rax+rax+00h]
0x18000a1a1  and     [rsp+120h+var_F0], rsi
0x18000a1a6  lea     rax, [rsp+120h+var_E8]
0x18000a1ab  mov     [rbp+4Fh+var_58], rax
0x18000a1af  xorps   xmm0, xmm0
0x18000a1b2  lea     rax, [rsp+120h+var_D0]
0x18000a1b7  mov     [rbp+4Fh+var_50], rax
0x18000a1bb  lea     rax, [rbp+4Fh+CriticalSection]
0x18000a1bf  mov     [rbp+4Fh+var_48], rax
0x18000a1c3  lea     rax, [rsp+120h+var_F8]
0x18000a1c8  mov     [rbp+4Fh+var_40], rax
0x18000a1cc  xor     eax, eax
0x18000a1ce  cmp     dword ptr [r13+1Ch], 2
0x18000a1d3  movups  [rbp+4Fh+var_B8], xmm0
0x18000a1d7  mov     [rbp+4Fh+var_88], rax
0x18000a1db  movups  [rbp+4Fh+var_A8], xmm0
0x18000a1df  movups  [rbp+4Fh+var_98], xmm0
0x18000a1e3  jz      short loc_18000A206
0x18000a1e5  mov     ebx, 80070032h
0x18000a1ea  lea     r8, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x18000a1f1  mov     ecx, ebx
0x18000a1f3  mov     r9d, 7D4h
0x18000a1f9  call    ElValidateHr_5
0x18000a1fe  test    eax, eax
0x18000a200  js      loc_18000A410
0x18000a206  xor     r9d, r9d; lpFilePart
0x18000a209  xor     r8d, r8d; lpBuffer
0x18000a20c  xor     edx, edx; nBufferLength
0x18000a20e  mov     rcx, rdi; lpFileName
0x18000a211  call    cs:__imp_GetFullPathNameW
0x18000a218  nop     dword ptr [rax+rax+00h]
0x18000a21d  mov     ebx, eax
0x18000a21f  test    eax, eax
0x18000a221  jnz     short loc_18000A25D
0x18000a223  call    cs:__imp_GetLastError
0x18000a22a  nop     dword ptr [rax+rax+00h]
0x18000a22f  mov     r9d, 7DDh
0x18000a235  mov     ecx, eax
0x18000a237  call    ElValidateWin32_4
0x18000a23c  mov     ebx, eax
0x18000a23e  test    eax, eax
0x18000a240  jle     short loc_18000A24B
0x18000a242  movzx   ebx, ax
0x18000a245  or      ebx, 80070000h
0x18000a24b  test    ebx, ebx
0x18000a24d  js      loc_18000A410
0x18000a253  mov     ebx, 80004005h
0x18000a258  jmp     loc_18000A410
0x18000a25d  inc     ebx
0x18000a25f  mov     eax, 2
0x18000a264  mov     ecx, ebx
0x18000a266  mul     rcx
0x18000a269  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000a270  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a277  cmovo   rax, rcx
0x18000a27b  mov     rcx, rax; unsigned __int64
0x18000a27e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000a283  mov     rsi, rax
0x18000a286  test    rax, rax
0x18000a289  jnz     short loc_18000A295
0x18000a28b  mov     ebx, 8007000Eh
0x18000a290  jmp     loc_18000A410
0x18000a295  xor     r9d, r9d; lpFilePart
0x18000a298  mov     r8, rsi; lpBuffer
0x18000a29b  mov     edx, ebx; nBufferLength
0x18000a29d  mov     rcx, rdi; lpFileName
0x18000a2a0  call    cs:__imp_GetFullPathNameW
0x18000a2a7  nop     dword ptr [rax+rax+00h]
0x18000a2ac  test    eax, eax
0x18000a2ae  jnz     short loc_18000A2C7
0x18000a2b0  call    cs:__imp_GetLastError
0x18000a2b7  nop     dword ptr [rax+rax+00h]
0x18000a2bc  mov     r9d, 7E9h
0x18000a2c2  jmp     loc_18000A235
0x18000a2c7  xor     edi, edi
0x18000a2c9  cmp     [rbp+4Fh+arg_20], edi
0x18000a2cc  jbe     short loc_18000A333
0x18000a2ce  mov     rdx, [r15]
0x18000a2d1  lea     r8, [rsp+120h+lpFileName]
0x18000a2d6  mov     rcx, rsi
0x18000a2d9  call    cs:__imp_ConcatenatePaths
0x18000a2e0  nop     dword ptr [rax+rax+00h]
0x18000a2e5  mov     ecx, eax
0x18000a2e7  mov     r9d, 7F5h
0x18000a2ed  mov     ebx, eax
0x18000a2ef  call    ElValidateWin32_4
0x18000a2f4  test    eax, eax
0x18000a2f6  jnz     loc_18000A403
0x18000a2fc  mov     rdx, [rsp+120h+lpFileName]
0x18000a301  lea     rcx, [rsp+120h+var_E8]
0x18000a306  call    ?AddItem@?$CDynArray@PEAUWdsImgParentImage@@VCDeallocatePointer@@@@QEAAKPEAUWdsImgParentImage@@@Z; CDynArray<WdsImgParentImage *,CDeallocatePointer>::AddItem(WdsImgParentImage *)
0x18000a30b  mov     r9d, 7F8h
0x18000a311  mov     ecx, eax
0x18000a313  mov     ebx, eax
0x18000a315  call    ElValidateWin32_4
0x18000a31a  test    eax, eax
0x18000a31c  jnz     loc_18000A403
0x18000a322  and     [rsp+120h+lpFileName], 0
0x18000a328  inc     edi
0x18000a32a  add     r15, 8
0x18000a32e  cmp     edi, [rbp+4Fh+arg_20]
0x18000a331  jb      short loc_18000A2CE
0x18000a333  mov     rdx, [r13+188h]
0x18000a33a  lea     r8, [rsp+120h+var_F0]
0x18000a33f  mov     rax, [rdx+8]
0x18000a343  add     rdx, 8
0x18000a347  movsxd  rcx, dword ptr [rax+4]
0x18000a34b  add     rcx, rdx
0x18000a34e  mov     rdx, cs:__imp_?IID_IDepImageResolvedFileBased@@3U_GUID@@B.Data1; _GUID const IID_IDepImageResolvedFileBased
0x18000a355  mov     rax, [rcx]
0x18000a358  mov     rax, [rax+18h]
0x18000a35c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a361  lea     r8, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x18000a368  mov     ebx, eax
0x18000a36a  cmp     eax, 80004002h
0x18000a36f  jnz     short loc_18000A380
0x18000a371  mov     ebx, 0C102021Ah
0x18000a376  mov     r9d, 808h
0x18000a37c  mov     ecx, ebx
0x18000a37e  jmp     short loc_18000A388
0x18000a380  mov     r9d, 80Ch
0x18000a386  mov     ecx, eax
0x18000a388  call    ElValidateHr_5
0x18000a38d  test    eax, eax
0x18000a38f  js      short loc_18000A410
0x18000a391  mov     eax, 4
0x18000a396  mov     qword ptr [rbp+4Fh+var_B8+8], rsi
0x18000a39a  lea     rcx, ?_WimExtractCallback@CImage@@SAKK_K_JPEAX@Z; CImage::_WimExtractCallback(ulong,unsigned __int64,__int64,void *)
0x18000a3a1  test    r12b, 1
0x18000a3a5  mov     qword ptr [rbp+4Fh+var_98], rcx
0x18000a3a9  lea     rdx, [rbp+4Fh+var_B8]
0x18000a3ad  lea     rcx, [rbp+4Fh+var_58]
0x18000a3b1  mov     qword ptr [rbp+4Fh+var_98+8], rcx
0x18000a3b5  lea     ecx, [rax+8]
0x18000a3b8  cmovnz  eax, ecx
0x18000a3bb  mov     rcx, [rsp+120h+var_F0]
0x18000a3c0  mov     dword ptr [rbp+4Fh+var_B8], eax
0x18000a3c3  mov     rax, [rcx]
0x18000a3c6  mov     rax, [rax]
0x18000a3c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3ce  mov     r9d, 81Eh
0x18000a3d4  lea     r8, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x18000a3db  mov     ecx, eax
0x18000a3dd  mov     ebx, eax
0x18000a3df  call    ElValidateHr_5
0x18000a3e4  test    eax, eax
0x18000a3e6  js      short loc_18000A410
0x18000a3e8  mov     ecx, [rsp+120h+var_F8]
0x18000a3ec  test    ecx, ecx
0x18000a3ee  jz      short loc_18000A410
0x18000a3f0  mov     r9d, 822h
0x18000a3f6  call    ElValidateWin32_4
0x18000a3fb  test    eax, eax
0x18000a3fd  jz      short loc_18000A410
0x18000a3ff  mov     ebx, [rsp+120h+var_F8]
0x18000a403  test    ebx, ebx
0x18000a405  jle     short loc_18000A410
0x18000a407  movzx   ebx, bx
0x18000a40a  or      ebx, 80070000h
0x18000a410  test    r12b, 20h
0x18000a414  jnz     short loc_18000A467
0x18000a416  mov     eax, [rsp+120h+var_DC]
0x18000a41a  xor     edi, edi
0x18000a41c  test    eax, eax
0x18000a41e  jz      short loc_18000A467
0x18000a420  mov     rcx, [rsp+120h+lpFileName]
0x18000a425  cmp     edi, eax
0x18000a427  jnb     short loc_18000A437
0x18000a429  mov     rax, [rsp+120h+var_E8]
0x18000a42e  mov     rcx, [rax+rdi*8]; Str
0x18000a432  mov     [rsp+120h+lpFileName], rcx
0x18000a437  mov     edx, 2Ah ; '*'; Ch
0x18000a43c  call    cs:__imp_wcschr
0x18000a443  nop     dword ptr [rax+rax+00h]
0x18000a448  xor     ecx, ecx
0x18000a44a  mov     [rsp+120h+lpFileName], rcx
0x18000a44f  test    rax, rax
0x18000a452  jz      short loc_18000A460
0x18000a454  mov     eax, [rsp+120h+var_DC]
0x18000a458  inc     edi
0x18000a45a  cmp     edi, eax
0x18000a45c  jb      short loc_18000A429
0x18000a45e  jmp     short loc_18000A46C
0x18000a460  mov     ebx, 80070002h
0x18000a465  jmp     short loc_18000A470
0x18000a467  mov     rcx, [rsp+120h+lpFileName]
0x18000a46c  test    ebx, ebx
0x18000a46e  jns     short loc_18000A4CF
0x18000a470  mov     eax, [rbp+4Fh+var_C4]
0x18000a473  xor     edi, edi
0x18000a475  test    eax, eax
0x18000a477  jz      short loc_18000A4CF
0x18000a479  cmp     edi, eax
0x18000a47b  jnb     short loc_18000A48B
0x18000a47d  mov     rax, [rsp+120h+var_D0]
0x18000a482  mov     rcx, [rax+rdi*8]; lpFileName
0x18000a486  mov     [rsp+120h+lpFileName], rcx
0x18000a48b  call    cs:__imp_GetFileAttributesW
0x18000a492  nop     dword ptr [rax+rax+00h]
0x18000a497  cmp     eax, 0FFFFFFFFh
0x18000a49a  jz      short loc_18000A4BF
0x18000a49c  mov     rcx, [rsp+120h+lpFileName]; lpFileName
0x18000a4a1  test    al, 10h
0x18000a4a3  jz      short loc_18000A4B3
0x18000a4a5  call    cs:__imp_WdsDeleteDirectory
0x18000a4ac  nop     dword ptr [rax+rax+00h]
0x18000a4b1  jmp     short loc_18000A4BF
0x18000a4b3  call    cs:__imp_DeleteFileW
0x18000a4ba  nop     dword ptr [rax+rax+00h]
0x18000a4bf  mov     eax, [rbp+4Fh+var_C4]
0x18000a4c2  xor     ecx, ecx
0x18000a4c4  inc     edi
0x18000a4c6  mov     [rsp+120h+lpFileName], rcx
0x18000a4cb  cmp     edi, eax
0x18000a4cd  jb      short loc_18000A47D
0x18000a4cf  test    rcx, rcx
0x18000a4d2  jz      short loc_18000A4E6
0x18000a4d4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000a4db  nop     dword ptr [rax+rax+00h]
0x18000a4e0  and     [rsp+120h+lpFileName], 0
0x18000a4e6  test    rsi, rsi
0x18000a4e9  jz      short loc_18000A4FA
0x18000a4eb  mov     rcx, rsi
0x18000a4ee  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000a4f5  nop     dword ptr [rax+rax+00h]
0x18000a4fa  mov     rdx, [rsp+120h+var_F0]
0x18000a4ff  test    rdx, rdx
0x18000a502  jz      short loc_18000A525
0x18000a504  mov     rax, [rdx+8]
0x18000a508  add     rdx, 8
0x18000a50c  movsxd  rcx, dword ptr [rax+4]
0x18000a510  add     rcx, rdx
0x18000a513  mov     rax, [rcx]
0x18000a516  mov     rax, [rax+10h]
0x18000a51a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a51f  and     [rsp+120h+var_F0], 0
0x18000a525  lea     rcx, [rbp+4Fh+CriticalSection]; lpCriticalSection
0x18000a529  call    cs:__imp_DeleteCriticalSection
0x18000a530  nop     dword ptr [rax+rax+00h]
0x18000a535  lea     rcx, [rsp+120h+var_D0]
0x18000a53a  call    ??1?$CDynArray@PEAGVCDeallocateString@@@@QEAA@XZ; CDynArray<ushort *,CDeallocateString>::~CDynArray<ushort *,CDeallocateString>(void)
0x18000a53f  lea     rcx, [rsp+120h+var_E8]
0x18000a544  call    ??1?$CDynArray@PEAGVCDeallocateString@@@@QEAA@XZ; CDynArray<ushort *,CDeallocateString>::~CDynArray<ushort *,CDeallocateString>(void)
0x18000a549  mov     eax, ebx
0x18000a54b  mov     rcx, [rbp+4Fh+var_38]
0x18000a54f  xor     rcx, rsp; StackCookie
0x18000a552  call    __security_check_cookie
0x18000a557  add     rsp, 0F0h
0x18000a55e  pop     r15
0x18000a560  pop     r13
0x18000a562  pop     r12
0x18000a564  pop     rdi
0x18000a565  pop     rsi
0x18000a566  pop     rbx
0x18000a567  pop     rbp
0x18000a568  retn
```
