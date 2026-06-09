# Microsoft::Windows::Performance::CImageIdEventTraceExtender::RetrieveFileVersionInformation(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *,XPerfCore::CFileMapping *)

- ea: `0x18001c548`
- end: `0x18001c8ee`
- name: `?RetrieveFileVersionInformation@CImageIdEventTraceExtender@Performance@Windows@Microsoft@@AEAAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGPEAVCFileMapping@XPerfCore@@@Z`
- size: `934`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180016478`

## callees

- `0x18000ab2c`
- `0x18000abd4`
- `0x18000abfc`
- `0x180018384`
- `0x180018468`
- `0x180019370`
- `0x180019488`
- `0x180019d10`
- `0x18001c548`
- `0x1800319f0`
- `0x180034010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18001c587`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001c5c5`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001c6a8`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001c6c5`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001c8b8`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001c587`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001c5c5`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001c6a8`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001c6c5`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001c8b8`
- `VERSION!VerQueryValueW` at `0x18001c685`
- `VERSION!VerQueryValueW` at `0x18001c685`

## string_xrefs

- `0x18001c76b`: `CompanyName`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::Windows::Performance::CImageIdEventTraceExtender::RetrieveFileVersionInformation(
        __int64 a1,
        __int64 a2,
        const unsigned __int16 *a3,
        struct XPerfCore::CFileMapping *a4)
{
  void *v8; // rcx
  unsigned int v9; // edi
  int VersionInfo; // eax
  unsigned __int64 v11; // r8
  __int64 result; // rax
  __int64 v13; // r8
  unsigned __int64 v14; // r8
  __int64 v15; // r8
  void *v16; // rsi
  int Error; // ebx
  unsigned __int64 v18; // r8
  __int64 v19; // r8
  unsigned __int64 v20; // r8
  __int64 v21; // r8
  unsigned __int64 v22; // r8
  __int64 v23; // r8
  int v24; // eax
  __int64 *v25; // rax
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // rdx
  __int64 v29; // rdi
  __int64 *v30; // rbx
  unsigned int puLen[2]; // [rsp+30h] [rbp-298h] BYREF
  LPCVOID pBlock; // [rsp+38h] [rbp-290h] BYREF
  unsigned __int16 v33; // [rsp+40h] [rbp-288h]
  LPVOID lpBuffer[3]; // [rsp+48h] [rbp-280h] BYREF
  ATL::CAtlException *v35; // [rsp+60h] [rbp-268h] BYREF
  unsigned __int16 v36[264]; // [rsp+70h] [rbp-258h] BYREF

  lpBuffer[2] = (LPVOID)-2LL;
  lpBuffer[1] = (LPVOID)a1;
  operator delete[](0);
  v8 = 0;
  pBlock = 0;
  if ( !a4 )
  {
    v9 = -2147467261;
LABEL_5:
    operator delete[](v8);
    return v9;
  }
  VersionInfo = XPerfCore::CFileVersionInfo::GetVersionInfo((XPerfCore::CFileVersionInfo *)&pBlock, a3, a4);
  v9 = VersionInfo;
  if ( VersionInfo < 0 )
  {
    v8 = (void *)pBlock;
    goto LABEL_5;
  }
  try
  {
    XPerfCore::CFileVersionInfo::GetValue((XPerfCore::CFileVersionInfo *)&pBlock, v36, v11, L"FileDescription");
    v29 = -1;
    v13 = -1;
    do
      ++v13;
    while ( v36[v13] );
    ATL::CSimpleStringT<unsigned short,0>::Append(a2, v36, v13);
    ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
    XPerfCore::CFileVersionInfo::GetValue((XPerfCore::CFileVersionInfo *)&pBlock, v36, v14, L"FileVersion");
    v15 = -1;
    do
      ++v15;
    while ( v36[v15] );
    ATL::CSimpleStringT<unsigned short,0>::Append(a2, v36, v15);
    ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
    lpBuffer[0] = 0;
    v16 = (void *)pBlock;
    if ( !pBlock )
    {
      Error = -2147418113;
LABEL_13:
      operator delete[](v16);
      return (unsigned int)Error;
    }
    puLen[0] = 0;
    if ( VerQueryValueW(pBlock, L"\\", lpBuffer, puLen) )
    {
      if ( puLen[0] >= 0xC )
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
          a2,
          L"%u.%u.%u.%u",
          *((unsigned __int16 *)lpBuffer[0] + 5),
          *((unsigned __int16 *)lpBuffer[0] + 4),
          *((unsigned __int16 *)lpBuffer[0] + 7),
          *((unsigned __int16 *)lpBuffer[0] + 6));
        ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
          a2,
          L"%u",
          v33);
        ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
        XPerfCore::CFileVersionInfo::GetValue((XPerfCore::CFileVersionInfo *)&pBlock, v36, v18, L"ProductName");
        v19 = -1;
        do
          ++v19;
        while ( v36[v19] );
        ATL::CSimpleStringT<unsigned short,0>::Append(a2, v36, v19);
        ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
        XPerfCore::CFileVersionInfo::GetValue((XPerfCore::CFileVersionInfo *)&pBlock, v36, v20, L"CompanyName");
        v21 = -1;
        do
          ++v21;
        while ( v36[v21] );
        ATL::CSimpleStringT<unsigned short,0>::Append(a2, v36, v21);
        ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
        XPerfCore::CFileVersionInfo::GetValue((XPerfCore::CFileVersionInfo *)&pBlock, v36, v22, L"ProductVersion");
        v23 = -1;
        do
          ++v23;
        while ( v36[v23] );
        ATL::CSimpleStringT<unsigned short,0>::Append(a2, v36, v23);
        ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
        *(_QWORD *)puLen = 0;
        try
        {
          if ( Microsoft::Windows::Performance::CAeDelayLoad::IsLibraryAvailable((Microsoft::Windows::Performance::CAeDelayLoad *)(a1 + 296)) )
            v24 = (*(__int64 (__fastcall **)(const unsigned __int16 *, __int64, unsigned int *))(a1 + 312))(
                    a3,
                    1,
                    puLen);
          else
            v24 = ATL::AtlHresultFromWin32(0x7Fu);
          if ( v24 >= 0 )
          {
            v25 = *(__int64 **)puLen;
          }
          else
          {
            v25 = 0;
            *(_QWORD *)puLen = 0;
          }
          if ( v25 )
          {
            v26 = *v25;
            if ( *v25 )
            {
              v27 = -1;
              do
                ++v27;
              while ( *(_WORD *)(v26 + 2 * v27) );
              ATL::CSimpleStringT<unsigned short,0>::Append(a2, v26, v27);
            }
          }
          ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
          if ( *(_QWORD *)puLen )
          {
            v28 = *(_QWORD *)(*(_QWORD *)puLen + 8LL);
            if ( v28 )
            {
              do
                ++v29;
              while ( *(_WORD *)(v28 + 2 * v29) );
              ATL::CSimpleStringT<unsigned short,0>::Append(a2, v28, (unsigned int)v29);
            }
          }
          ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
          v30 = *(__int64 **)puLen;
          if ( *(_QWORD *)puLen )
          {
            if ( Microsoft::Windows::Performance::CAeDelayLoad::IsLibraryAvailable((Microsoft::Windows::Performance::CAeDelayLoad *)(a1 + 296)) )
              (*(void (__fastcall **)(__int64 *))(a1 + 320))(v30);
            *(_QWORD *)puLen = 0;
          }
        }
        catch ( ... )
        {
          throw;
        }
        operator delete[]((void *)pBlock);
        return 0;
      }
    }
    else
    {
      lpBuffer[0] = 0;
      Error = ATL::AtlHresultFromLastError();
      if ( Error < 0 )
        goto LABEL_13;
    }
    operator delete[](v16);
    result = 2147549183LL;
  }
  catch ( ATL::CAtlException *v35 )
  {
    return *(unsigned int *)v35;
  }
  return result;
}

```

## disassembly

```asm
0x18001c548  push    rbx
0x18001c54a  push    rsi
0x18001c54b  push    rdi
0x18001c54c  push    r12
0x18001c54e  push    r14
0x18001c550  push    r15
0x18001c552  sub     rsp, 298h
0x18001c559  mov     [rsp+2C8h+var_270], 0FFFFFFFFFFFFFFFEh
0x18001c562  mov     rax, cs:__security_cookie
0x18001c569  xor     rax, rsp
0x18001c56c  mov     [rsp+2C8h+var_48], rax
0x18001c574  mov     rdi, r9
0x18001c577  mov     r15, r8
0x18001c57a  mov     rbx, rdx
0x18001c57d  mov     r14, rcx
0x18001c580  mov     [rsp+2C8h+var_278], rcx
0x18001c585  xor     ecx, ecx
0x18001c587  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001c58e  nop     dword ptr [rax+rax+00h]
0x18001c593  xor     r12d, r12d
0x18001c596  mov     ecx, r12d
0x18001c599  mov     [rsp+2C8h+pBlock], rcx
0x18001c59e  test    rdi, rdi
0x18001c5a1  jnz     short loc_18001C5AA
0x18001c5a3  mov     edi, 80004003h
0x18001c5a8  jmp     short loc_18001C5C5
0x18001c5aa  mov     r8, rdi; struct XPerfCore::CFileMapping *
0x18001c5ad  mov     rdx, r15; unsigned __int16 *
0x18001c5b0  lea     rcx, [rsp+2C8h+pBlock]; this
0x18001c5b5  call    ?GetVersionInfo@CFileVersionInfo@XPerfCore@@QEAAJPEBGPEAVCFileMapping@2@@Z; XPerfCore::CFileVersionInfo::GetVersionInfo(ushort const *,XPerfCore::CFileMapping *)
0x18001c5ba  mov     edi, eax
0x18001c5bc  test    eax, eax
0x18001c5be  jns     short loc_18001C5D8
0x18001c5c0  mov     rcx, [rsp+2C8h+pBlock]
0x18001c5c5  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001c5cc  nop     dword ptr [rax+rax+00h]
0x18001c5d1  mov     eax, edi
0x18001c5d3  jmp     loc_18001C8CC
0x18001c5d8  lea     r9, aFiledescriptio; "FileDescription"
0x18001c5df  lea     rdx, [rsp+2C8h+var_258]; unsigned __int16 *
0x18001c5e4  lea     rcx, [rsp+2C8h+pBlock]; this
0x18001c5e9  call    ?GetValue@CFileVersionInfo@XPerfCore@@QEAAJPEAG_KPEBG@Z; XPerfCore::CFileVersionInfo::GetValue(ushort *,unsigned __int64,ushort const *)
0x18001c5ee  lea     rax, [rsp+2C8h+var_258]
0x18001c5f3  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001c5f7  mov     r8, rdi
0x18001c5fa  inc     r8
0x18001c5fd  cmp     [rax+r8*2], r12w
0x18001c602  jnz     short loc_18001C5FA
0x18001c604  lea     rdx, [rsp+2C8h+var_258]
0x18001c609  mov     rcx, rbx
0x18001c60c  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x18001c611  mov     rcx, rbx
0x18001c614  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x18001c619  lea     r9, aFileversion; "FileVersion"
0x18001c620  lea     rdx, [rsp+2C8h+var_258]; unsigned __int16 *
0x18001c625  lea     rcx, [rsp+2C8h+pBlock]; this
0x18001c62a  call    ?GetValue@CFileVersionInfo@XPerfCore@@QEAAJPEAG_KPEBG@Z; XPerfCore::CFileVersionInfo::GetValue(ushort *,unsigned __int64,ushort const *)
0x18001c62f  lea     rax, [rsp+2C8h+var_258]
0x18001c634  mov     r8, rdi
0x18001c637  inc     r8
0x18001c63a  cmp     [rax+r8*2], r12w
0x18001c63f  jnz     short loc_18001C637
0x18001c641  lea     rdx, [rsp+2C8h+var_258]
0x18001c646  mov     rcx, rbx
0x18001c649  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x18001c64e  mov     rcx, rbx
0x18001c651  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x18001c656  mov     [rsp+2C8h+lpBuffer], r12
0x18001c65b  mov     rsi, [rsp+2C8h+pBlock]
0x18001c660  test    rsi, rsi
0x18001c663  jnz     short loc_18001C66C
0x18001c665  mov     ebx, 8000FFFFh
0x18001c66a  jmp     short loc_18001C6A5
0x18001c66c  mov     [rsp+2C8h+puLen], r12d
0x18001c671  lea     r9, [rsp+2C8h+puLen]; puLen
0x18001c676  lea     r8, [rsp+2C8h+lpBuffer]; lplpBuffer
0x18001c67b  lea     rdx, pszSrc; "\\"
0x18001c682  mov     rcx, rsi; pBlock
0x18001c685  call    cs:__imp_VerQueryValueW
0x18001c68c  nop     dword ptr [rax+rax+00h]
0x18001c691  test    eax, eax
0x18001c693  jnz     short loc_18001C6BB
0x18001c695  mov     [rsp+2C8h+lpBuffer], r12
0x18001c69a  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001c69f  mov     ebx, eax
0x18001c6a1  test    eax, eax
0x18001c6a3  jns     short loc_18001C6C2
0x18001c6a5  mov     rcx, rsi
0x18001c6a8  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001c6af  nop     dword ptr [rax+rax+00h]
0x18001c6b4  mov     eax, ebx
0x18001c6b6  jmp     loc_18001C8CC
0x18001c6bb  cmp     [rsp+2C8h+puLen], 0Ch
0x18001c6c0  jnb     short loc_18001C6DB
0x18001c6c2  mov     rcx, rsi
0x18001c6c5  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001c6cc  nop     dword ptr [rax+rax+00h]
0x18001c6d1  mov     eax, 8000FFFFh
0x18001c6d6  jmp     loc_18001C8CC
0x18001c6db  mov     rdx, [rsp+2C8h+lpBuffer]
0x18001c6e0  movzx   eax, word ptr [rdx+0Ch]
0x18001c6e4  movzx   ecx, word ptr [rdx+0Eh]
0x18001c6e8  movzx   r9d, word ptr [rdx+8]
0x18001c6ed  movzx   r8d, word ptr [rdx+0Ah]
0x18001c6f2  mov     [rsp+2C8h+var_2A0], eax
0x18001c6f6  mov     [rsp+2C8h+var_2A8], ecx
0x18001c6fa  lea     rdx, aUUUU; "%u.%u.%u.%u"
0x18001c701  mov     rcx, rbx
0x18001c704  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x18001c709  mov     rcx, rbx
0x18001c70c  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x18001c711  movzx   r8d, [rsp+2C8h+var_288]
0x18001c717  lea     rdx, aU; "%u"
0x18001c71e  mov     rcx, rbx
0x18001c721  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x18001c726  mov     rcx, rbx
0x18001c729  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x18001c72e  lea     r9, aProductname; "ProductName"
0x18001c735  lea     rdx, [rsp+2C8h+var_258]; unsigned __int16 *
0x18001c73a  lea     rcx, [rsp+2C8h+pBlock]; this
0x18001c73f  call    ?GetValue@CFileVersionInfo@XPerfCore@@QEAAJPEAG_KPEBG@Z; XPerfCore::CFileVersionInfo::GetValue(ushort *,unsigned __int64,ushort const *)
0x18001c744  lea     rax, [rsp+2C8h+var_258]
0x18001c749  mov     r8, rdi
0x18001c74c  inc     r8
0x18001c74f  cmp     [rax+r8*2], r12w
0x18001c754  jnz     short loc_18001C74C
0x18001c756  lea     rdx, [rsp+2C8h+var_258]
0x18001c75b  mov     rcx, rbx
0x18001c75e  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x18001c763  mov     rcx, rbx
0x18001c766  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x18001c76b  lea     r9, aCompanyname; "CompanyName"
0x18001c772  lea     rdx, [rsp+2C8h+var_258]; unsigned __int16 *
0x18001c777  lea     rcx, [rsp+2C8h+pBlock]; this
0x18001c77c  call    ?GetValue@CFileVersionInfo@XPerfCore@@QEAAJPEAG_KPEBG@Z; XPerfCore::CFileVersionInfo::GetValue(ushort *,unsigned __int64,ushort const *)
0x18001c781  lea     rax, [rsp+2C8h+var_258]
0x18001c786  mov     r8, rdi
0x18001c789  inc     r8
0x18001c78c  cmp     [rax+r8*2], r12w
0x18001c791  jnz     short loc_18001C789
0x18001c793  lea     rdx, [rsp+2C8h+var_258]
0x18001c798  mov     rcx, rbx
0x18001c79b  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x18001c7a0  mov     rcx, rbx
0x18001c7a3  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x18001c7a8  lea     r9, aProductversion; "ProductVersion"
0x18001c7af  lea     rdx, [rsp+2C8h+var_258]; unsigned __int16 *
0x18001c7b4  lea     rcx, [rsp+2C8h+pBlock]; this
0x18001c7b9  call    ?GetValue@CFileVersionInfo@XPerfCore@@QEAAJPEAG_KPEBG@Z; XPerfCore::CFileVersionInfo::GetValue(ushort *,unsigned __int64,ushort const *)
0x18001c7be  lea     rax, [rsp+2C8h+var_258]
0x18001c7c3  mov     r8, rdi
0x18001c7c6  inc     r8
0x18001c7c9  cmp     [rax+r8*2], r12w
0x18001c7ce  jnz     short loc_18001C7C6
0x18001c7d0  lea     rdx, [rsp+2C8h+var_258]
0x18001c7d5  mov     rcx, rbx
0x18001c7d8  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x18001c7dd  mov     rcx, rbx
0x18001c7e0  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x18001c7e5  mov     qword ptr [rsp+2C8h+puLen], r12
0x18001c7ea  lea     rsi, [r14+128h]
0x18001c7f1  mov     rcx, rsi; this
0x18001c7f4  call    ?IsLibraryAvailable@CAeDelayLoad@Performance@Windows@Microsoft@@QEAA_NXZ; Microsoft::Windows::Performance::CAeDelayLoad::IsLibraryAvailable(void)
0x18001c7f9  test    al, al
0x18001c7fb  jz      short loc_18001C815
0x18001c7fd  lea     r8, [rsp+2C8h+puLen]
0x18001c802  mov     edx, 1
0x18001c807  mov     rcx, r15
0x18001c80a  mov     rax, [rsi+10h]
0x18001c80e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c813  jmp     short loc_18001C81F
0x18001c815  mov     ecx, 7Fh; unsigned int
0x18001c81a  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18001c81f  test    eax, eax
0x18001c821  jns     short loc_18001C82D
0x18001c823  mov     rax, r12
0x18001c826  mov     qword ptr [rsp+2C8h+puLen], rax
0x18001c82b  jmp     short loc_18001C832
0x18001c82d  mov     rax, qword ptr [rsp+2C8h+puLen]
0x18001c832  test    rax, rax
0x18001c835  jz      short loc_18001C854
0x18001c837  mov     rdx, [rax]
0x18001c83a  test    rdx, rdx
0x18001c83d  jz      short loc_18001C854
0x18001c83f  mov     r8, rdi
0x18001c842  inc     r8
0x18001c845  cmp     [rdx+r8*2], r12w
0x18001c84a  jnz     short loc_18001C842
0x18001c84c  mov     rcx, rbx
0x18001c84f  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x18001c854  mov     rcx, rbx
0x18001c857  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x18001c85c  mov     rdx, qword ptr [rsp+2C8h+puLen]
0x18001c861  test    rdx, rdx
0x18001c864  jz      short loc_18001C884
0x18001c866  mov     rdx, [rdx+8]
0x18001c86a  test    rdx, rdx
0x18001c86d  jz      short loc_18001C884
0x18001c86f  inc     rdi
0x18001c872  cmp     [rdx+rdi*2], r12w
0x18001c877  jnz     short loc_18001C86F
0x18001c879  mov     r8d, edi
0x18001c87c  mov     rcx, rbx
0x18001c87f  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x18001c884  mov     rcx, rbx
0x18001c887  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x18001c88c  mov     rbx, qword ptr [rsp+2C8h+puLen]
0x18001c891  test    rbx, rbx
0x18001c894  jz      short loc_18001C8B3
0x18001c896  mov     rcx, rsi; this
0x18001c899  call    ?IsLibraryAvailable@CAeDelayLoad@Performance@Windows@Microsoft@@QEAA_NXZ; Microsoft::Windows::Performance::CAeDelayLoad::IsLibraryAvailable(void)
0x18001c89e  test    al, al
0x18001c8a0  jz      short loc_18001C8AE
0x18001c8a2  mov     rcx, rbx
0x18001c8a5  mov     rax, [rsi+18h]
0x18001c8a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c8ae  mov     qword ptr [rsp+2C8h+puLen], r12
0x18001c8b3  mov     rcx, [rsp+2C8h+pBlock]
0x18001c8b8  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001c8bf  nop     dword ptr [rax+rax+00h]
0x18001c8c4  xor     eax, eax
0x18001c8c6  jmp     short loc_18001C8CC
0x18001c8c8  mov     eax, [rsp+2C8h+puLen]
0x18001c8cc  mov     rcx, [rsp+2C8h+var_48]
0x18001c8d4  xor     rcx, rsp; StackCookie
0x18001c8d7  call    __security_check_cookie
0x18001c8dc  add     rsp, 298h
0x18001c8e3  pop     r15
0x18001c8e5  pop     r14
0x18001c8e7  pop     r12
0x18001c8e9  pop     rdi
0x18001c8ea  pop     rsi
0x18001c8eb  pop     rbx
0x18001c8ec  retn
```
