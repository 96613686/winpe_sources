# CZipFolder::_StgCreate(_ITEMIDLIST const *,ulong,_GUID const &,void * *)

- ea: `0x180026600`
- end: `0x180026957`
- name: `?_StgCreate@CZipFolder@@EEAAJPEFBU_ITEMIDLIST@@KAEBU_GUID@@PEAPEAX@Z`
- size: `855`
- prototype: `int(CZipFolder *__hidden this, const struct _ITEMIDLIST *, unsigned int, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, reparse_path`

## callees

- `0x18000ed28`
- `0x18000f1c0`
- `0x18000f530`
- `0x18000f5f0`
- `0x180010c30`
- `0x18001ceb4`
- `0x18001f080`
- `0x180026600`
- `0x180026960`
- `0x18002840c`
- `0x1800352a8`
- `0x180036f50`
- `0x18003732c`
- `0x180037958`
- `0x180071010`

## import_xrefs

- `SHELL32!__imp_ILFree` at `0x180026904`
- `SHELL32!__imp_ILFree` at `0x180026904`
- `SHLWAPI!__imp_ualstrcpynW` at `0x180026892`
- `SHLWAPI!__imp_ualstrcpynW` at `0x180026892`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002690e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002690e`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180026778`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180026778`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180026787`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180026787`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18002691b`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18002691b`

## pseudocode

```c
__int64 __fastcall CZipFolder::_StgCreate(
        CZipFolder *this,
        const struct _ITEMIDLIST *a2,
        unsigned int a3,
        const struct _GUID *a4,
        void **a5)
{
  __int64 v8; // rax
  __int64 v9; // rax
  CTempFileNameArray *v11; // rcx
  __int64 v12; // r11
  const struct CArchiveIDList *v13; // r14
  int TempLocation; // ebx
  __int64 v15; // rax
  CZipWriteStream *v16; // rax
  CZipWriteStream *v17; // rax
  CZipWriteStream *v18; // rsi
  PWSTR *v19; // r9
  __int64 v20; // rax
  PCWSTR pszMore[2]; // [rsp+40h] [rbp-C0h] BYREF
  LPITEMIDLIST pidl[2]; // [rsp+50h] [rbp-B0h] BYREF
  void *Src[14]; // [rsp+60h] [rbp-A0h] BYREF
  HLOCAL hMem; // [rsp+D0h] [rbp-30h]
  WCHAR pszPath[264]; // [rsp+900h] [rbp+800h] BYREF
  unsigned __int16 v26[264]; // [rsp+B10h] [rbp+A10h] BYREF
  WCHAR pszExt[264]; // [rsp+D20h] [rbp+C20h] BYREF

  *a5 = 0;
  v8 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&IID_IStorage.Data1;
  if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&IID_IStorage.Data1 )
    v8 = *(_QWORD *)a4->Data4 - *(_QWORD *)IID_IStorage.Data4;
  if ( v8 )
  {
    v9 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&IID_IStream.Data1;
    if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&IID_IStream.Data1 )
      v9 = *(_QWORD *)a4->Data4 - *(_QWORD *)IID_IStream.Data4;
    if ( v9 )
      return 2147942487LL;
  }
  v13 = CArchiveIDList::_IsValidID(a2);
  if ( v13 )
  {
    v15 = *(_QWORD *)&a4->Data1 - v12;
    if ( *(_QWORD *)&a4->Data1 == v12 )
      v15 = *(_QWORD *)a4->Data4 - *(_QWORD *)IID_IStream.Data4;
    if ( v15 )
    {
      TempLocation = CTempFileNameArray::GetTempLocation(v11, (const unsigned __int16 *)this + 36, pszPath);
      if ( TempLocation >= 0 )
      {
        *(_OWORD *)pszMore = 0;
        TempLocation = CTempAlignedString::Set((CTempAlignedString *)pszMore, (const unsigned __int16 *)v13 + 46);
        if ( TempLocation >= 0 )
        {
          PathCchAppend(pszPath, 0x104u, pszMore[0]);
          if ( CreateDirectoryW(pszPath, 0) )
          {
            TempLocation = StringCchCopyW(v26, 0x104u, L"\"");
            if ( TempLocation >= 0 )
            {
              StringCchCatW(v26, 0x104u, pszPath);
              StringCchCatW(v26, 0x104u, L"\\*.*\"");
              memset_0(Src, 0, 0x89Cu);
              TempLocation = InitZIPCMDSTRUCTOneRoot(Src, (const unsigned __int16 *)this + 36, v26);
              if ( TempLocation >= 0 )
              {
                HIDWORD(Src[0]) = 4;
                *((_DWORD *)hMem + 65) = 1;
                Src[10] = DropInRenCallback;
                StringCchCopyW((unsigned __int16 *)hMem + 398, 0x104u, pszPath);
                StringCchCopyW((unsigned __int16 *)hMem + 138, 0x104u, (const unsigned __int16 *)this + 296);
                if ( (unsigned int)dzip((char *)Src) )
                {
                  TempLocation = -2147467259;
                }
                else
                {
                  ualstrcpynW(pszExt, (PERCEIVED *)v13 + 23, (PERCEIVEDFLAG *)0x104, v19);
                  v20 = *(_QWORD *)this;
                  pidl[0] = 0;
                  TempLocation = (*(__int64 (__fastcall **)(CZipFolder *, _QWORD, _QWORD, WCHAR *, _QWORD, LPITEMIDLIST *, _QWORD))(v20 + 24))(
                                   this,
                                   0,
                                   0,
                                   pszExt,
                                   0,
                                   pidl,
                                   0);
                  if ( TempLocation >= 0 )
                  {
                    TempLocation = (*(__int64 (__fastcall **)(CZipFolder *, LPITEMIDLIST, _QWORD, const struct _GUID *, void **))(*(_QWORD *)this + 40LL))(
                                     this,
                                     pidl[0],
                                     0,
                                     a4,
                                     a5);
                    ILFree(pidl[0]);
                  }
                }
                LocalFree(hMem);
              }
            }
            RemoveDirectoryW(pszPath);
          }
          else
          {
            TempLocation = ResultFromLastError();
          }
        }
        CTempAlignedString::Clear((CTempAlignedString *)pszMore);
      }
    }
    else
    {
      TempLocation = -2147024882;
      v16 = (CZipWriteStream *)operator new(0x838u, (const struct std::nothrow_t *)&std::nothrow);
      if ( v16 )
      {
        v17 = CZipWriteStream::CZipWriteStream(
                v16,
                (const unsigned __int16 *)this + 36,
                (const unsigned __int16 *)v13 + 46,
                (const unsigned __int16 *)this + 296,
                a3);
        v18 = v17;
        if ( v17 )
        {
          TempLocation = (**(__int64 (__fastcall ***)(CZipWriteStream *, const struct _GUID *, void **))v17)(
                           v17,
                           a4,
                           a5);
          (*(void (__fastcall **)(CZipWriteStream *))(*(_QWORD *)v18 + 16LL))(v18);
        }
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)TempLocation;
}

```

## disassembly

```asm
0x180026600  push    rbp
0x180026602  push    rbx
0x180026603  push    rsi
0x180026604  push    rdi
0x180026605  push    r12
0x180026607  push    r14
0x180026609  push    r15
0x18002660b  lea     rbp, [rsp-0E40h]
0x180026613  sub     rsp, 0F40h
0x18002661a  mov     rax, cs:__security_cookie
0x180026621  xor     rax, rsp
0x180026624  mov     [rbp+0E70h+var_40], rax
0x18002662b  mov     r12, [rbp+0E70h+arg_20]
0x180026632  mov     rdi, r9
0x180026635  mov     r15d, r8d
0x180026638  mov     rsi, rcx
0x18002663b  mov     qword ptr [r12], 0
0x180026643  mov     rax, [r9]
0x180026646  sub     rax, qword ptr cs:IID_IStorage.Data1
0x18002664d  jnz     short loc_18002665A
0x18002664f  mov     rax, [r9+8]
0x180026653  sub     rax, qword ptr cs:IID_IStorage.Data4
0x18002665a  mov     rbx, qword ptr cs:IID_IStream.Data4
0x180026661  mov     r11, qword ptr cs:IID_IStream.Data1
0x180026668  test    rax, rax
0x18002666b  jz      short loc_18002668B
0x18002666d  mov     rax, [r9]
0x180026670  sub     rax, r11
0x180026673  jnz     short loc_18002667C
0x180026675  mov     rax, [r9+8]
0x180026679  sub     rax, rbx
0x18002667c  test    rax, rax
0x18002667f  jz      short loc_18002668B
0x180026681  mov     eax, 80070057h
0x180026686  jmp     loc_180026936
0x18002668b  mov     rcx, rdx; struct _ITEMIDLIST *
0x18002668e  call    ?_IsValidID@CArchiveIDList@@SAPEBV1@PEFBU_ITEMIDLIST@@@Z; CArchiveIDList::_IsValidID(_ITEMIDLIST const *)
0x180026693  mov     r14, rax
0x180026696  test    rax, rax
0x180026699  jnz     short loc_1800266A5
0x18002669b  mov     ebx, 80070057h
0x1800266a0  jmp     loc_180026934
0x1800266a5  mov     rax, [rdi]
0x1800266a8  sub     rax, r11
0x1800266ab  jnz     short loc_1800266B4
0x1800266ad  mov     rax, [rdi+8]
0x1800266b1  sub     rax, rbx
0x1800266b4  test    rax, rax
0x1800266b7  jnz     short loc_18002672A
0x1800266b9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800266c0  mov     ecx, 838h; unsigned __int64
0x1800266c5  mov     ebx, 8007000Eh
0x1800266ca  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800266cf  test    rax, rax
0x1800266d2  jz      loc_180026934
0x1800266d8  lea     r9, [rsi+250h]; unsigned __int16 *
0x1800266df  mov     [rsp+0F70h+var_F50], r15d; unsigned int
0x1800266e4  lea     r8, [r14+5Ch]; unsigned __int16 *
0x1800266e8  mov     rcx, rax; this
0x1800266eb  lea     rdx, [rsi+48h]; unsigned __int16 *
0x1800266ef  call    ??0CZipWriteStream@@QEAA@PEBGPEFBG0K@Z; CZipWriteStream::CZipWriteStream(ushort const *,ushort const *,ushort const *,ulong)
0x1800266f4  mov     rsi, rax
0x1800266f7  test    rax, rax
0x1800266fa  jz      loc_180026934
0x180026700  mov     rcx, [rax]
0x180026703  mov     r8, r12
0x180026706  mov     rdx, rdi
0x180026709  mov     rax, [rcx]
0x18002670c  mov     rcx, rsi
0x18002670f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026714  mov     rcx, [rsi]
0x180026717  mov     ebx, eax
0x180026719  mov     rax, [rcx+10h]
0x18002671d  mov     rcx, rsi
0x180026720  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026725  jmp     loc_180026934
0x18002672a  lea     r8, [rbp+0E70h+pszPath]; unsigned __int16 *
0x180026731  lea     rdx, [rsi+48h]; unsigned __int16 *
0x180026735  call    ?GetTempLocation@CTempFileNameArray@@QEAAJPEBGPEAGI@Z; CTempFileNameArray::GetTempLocation(ushort const *,ushort *,uint)
0x18002673a  mov     ebx, eax
0x18002673c  test    eax, eax
0x18002673e  js      loc_180026934
0x180026744  xorps   xmm0, xmm0
0x180026747  lea     rdx, [r14+5Ch]; unsigned __int16 *
0x18002674b  lea     rcx, [rsp+0F70h+pszMore]; this
0x180026750  movdqu  xmmword ptr [rsp+0F70h+pszMore], xmm0
0x180026756  call    ?Set@CTempAlignedString@@QEAAJPEFBG@Z; CTempAlignedString::Set(ushort const *)
0x18002675b  mov     ebx, eax
0x18002675d  test    eax, eax
0x18002675f  js      loc_18002692A
0x180026765  mov     r8, [rsp+0F70h+pszMore]; pszMore
0x18002676a  lea     rcx, [rbp+0E70h+pszPath]; pszPath
0x180026771  mov     ebx, 104h
0x180026776  mov     edx, ebx; cchPath
0x180026778  call    cs:__imp_PathCchAppend
0x18002677e  xor     edx, edx; lpSecurityAttributes
0x180026780  lea     rcx, [rbp+0E70h+pszPath]; lpPathName
0x180026787  call    cs:__imp_CreateDirectoryW
0x18002678d  test    eax, eax
0x18002678f  jz      loc_180026923
0x180026795  lea     r8, asc_180079070; "\""
0x18002679c  mov     edx, ebx; unsigned __int64
0x18002679e  lea     rcx, [rbp+0E70h+var_460]; unsigned __int16 *
0x1800267a5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800267aa  mov     ebx, eax
0x1800267ac  test    eax, eax
0x1800267ae  js      loc_180026914
0x1800267b4  mov     ebx, 104h
0x1800267b9  lea     r8, [rbp+0E70h+pszPath]; unsigned __int16 *
0x1800267c0  mov     edx, ebx; unsigned __int64
0x1800267c2  lea     rcx, [rbp+0E70h+var_460]; unsigned __int16 *
0x1800267c9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800267ce  lea     r8, asc_18007A9F8; "\\*.*\""
0x1800267d5  mov     edx, ebx; unsigned __int64
0x1800267d7  lea     rcx, [rbp+0E70h+var_460]; unsigned __int16 *
0x1800267de  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800267e3  xor     edx, edx; Val
0x1800267e5  lea     rcx, [rsp+0F70h+Src]; void *
0x1800267ea  mov     r8d, 89Ch; Size
0x1800267f0  call    memset_0
0x1800267f5  lea     r8, [rbp+0E70h+var_460]; unsigned __int16 *
0x1800267fc  lea     rdx, [rsi+48h]; unsigned __int16 *
0x180026800  lea     rcx, [rsp+0F70h+Src]; struct ZIPCMDSTRUCT *
0x180026805  call    ?InitZIPCMDSTRUCTOneRoot@@YAJPEAUZIPCMDSTRUCT@@PEBG1@Z; InitZIPCMDSTRUCTOneRoot(ZIPCMDSTRUCT *,ushort const *,ushort const *)
0x18002680a  mov     ebx, eax
0x18002680c  test    eax, eax
0x18002680e  js      loc_180026914
0x180026814  mov     rax, [rbp+0E70h+hMem]
0x180026818  lea     r8, [rbp+0E70h+pszPath]; unsigned __int16 *
0x18002681f  mov     [rsp+0F70h+var_F0C], 4
0x180026827  mov     ebx, 104h
0x18002682c  mov     edx, ebx; unsigned __int64
0x18002682e  mov     dword ptr [rax+104h], 1
0x180026838  lea     rax, DropInRenCallback
0x18002683f  mov     rcx, [rbp+0E70h+hMem]
0x180026843  add     rcx, 31Ch; unsigned __int16 *
0x18002684a  mov     [rbp+0E70h+var_EC0], rax
0x18002684e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180026853  mov     rcx, [rbp+0E70h+hMem]
0x180026857  lea     r8, [rsi+250h]; unsigned __int16 *
0x18002685e  add     rcx, 114h; unsigned __int16 *
0x180026865  mov     edx, ebx; unsigned __int64
0x180026867  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002686c  lea     rcx, [rsp+0F70h+Src]; Src
0x180026871  call    dzip
0x180026876  test    eax, eax
0x180026878  jz      short loc_180026884
0x18002687a  mov     ebx, 80004005h
0x18002687f  jmp     loc_18002690A
0x180026884  mov     r8d, ebx; pflag
0x180026887  lea     rdx, [r14+5Ch]; ptype
0x18002688b  lea     rcx, [rbp+0E70h+pszExt]; pszExt
0x180026892  call    cs:__imp_ualstrcpynW
0x180026898  mov     rax, [rsi]
0x18002689b  lea     rcx, [rsp+0F70h+pidl]
0x1800268a0  mov     [rsp+0F70h+var_F40], 0
0x1800268a9  lea     r9, [rbp+0E70h+pszExt]
0x1800268b0  mov     [rsp+0F70h+var_F48], rcx
0x1800268b5  xor     r8d, r8d
0x1800268b8  xor     edx, edx
0x1800268ba  mov     [rsp+0F70h+pidl], 0
0x1800268c3  mov     rax, [rax+18h]
0x1800268c7  mov     rcx, rsi
0x1800268ca  mov     qword ptr [rsp+0F70h+var_F50], 0
0x1800268d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800268d8  mov     ebx, eax
0x1800268da  test    eax, eax
0x1800268dc  js      short loc_18002690A
0x1800268de  mov     rax, [rsi]
0x1800268e1  mov     r9, rdi
0x1800268e4  mov     rdx, [rsp+0F70h+pidl]
0x1800268e9  xor     r8d, r8d
0x1800268ec  mov     rcx, rsi
0x1800268ef  mov     qword ptr [rsp+0F70h+var_F50], r12
0x1800268f4  mov     rax, [rax+28h]
0x1800268f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800268fd  mov     rcx, [rsp+0F70h+pidl]; pidl
0x180026902  mov     ebx, eax
0x180026904  call    cs:__imp_ILFree
0x18002690a  mov     rcx, [rbp+0E70h+hMem]; hMem
0x18002690e  call    cs:__imp_LocalFree
0x180026914  lea     rcx, [rbp+0E70h+pszPath]; lpPathName
0x18002691b  call    cs:__imp_RemoveDirectoryW
0x180026921  jmp     short loc_18002692A
0x180026923  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180026928  mov     ebx, eax
0x18002692a  lea     rcx, [rsp+0F70h+pszMore]; this
0x18002692f  call    ?Clear@CTempAlignedString@@QEAAXXZ; CTempAlignedString::Clear(void)
0x180026934  mov     eax, ebx
0x180026936  mov     rcx, [rbp+0E70h+var_40]
0x18002693d  xor     rcx, rsp; StackCookie
0x180026940  call    __security_check_cookie
0x180026945  add     rsp, 0F40h
0x18002694c  pop     r15
0x18002694e  pop     r14
0x180026950  pop     r12
0x180026952  pop     rdi
0x180026953  pop     rsi
0x180026954  pop     rbx
0x180026955  pop     rbp
0x180026956  retn
```
