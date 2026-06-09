# Microsoft::Windows::Performance::CNGenEventTraceExtender::CopyNGenPdb(ushort const *,char const *,_RSDS const &)

- ea: `0x18001eb64`
- end: `0x18001ee44`
- name: `?CopyNGenPdb@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEBGPEBDAEBU_RSDS@@@Z`
- size: `736`
- prototype: `int(Microsoft::Windows::Performance::CNGenEventTraceExtender *__hidden this, const unsigned __int16 *, const char *, const struct _RSDS *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001f284`

## callees

- `0x18000ab2c`
- `0x18000abd4`
- `0x18000abfc`
- `0x180018468`
- `0x1800185cc`
- `0x18001e14c`
- `0x18001eb64`
- `0x18001f5f0`
- `0x180020808`
- `0x1800319f0`
- `0x180034010`

## import_xrefs

- `KERNEL32!CopyFileW` at `0x18001ed51`
- `KERNEL32!CopyFileW` at `0x18001ed51`
- `KERNEL32!CreateDirectoryW` at `0x18001ebb9`
- `KERNEL32!CreateDirectoryW` at `0x18001ec24`
- `KERNEL32!CreateDirectoryW` at `0x18001ec67`
- `KERNEL32!CreateDirectoryW` at `0x18001ebb9`
- `KERNEL32!CreateDirectoryW` at `0x18001ec24`
- `KERNEL32!CreateDirectoryW` at `0x18001ec67`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::Windows::Performance::CNGenEventTraceExtender::CopyNGenPdb(
        Microsoft::Windows::Performance::CNGenEventTraceExtender *this,
        const unsigned __int16 *a2,
        const char *a3,
        const struct _RSDS *a4)
{
  const WCHAR *v8; // rbx
  unsigned int v9; // esi
  int v11; // ecx
  const WCHAR *v12; // rbx
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // r8
  const wchar_t *v16; // rdx
  const wchar_t *v17; // rax
  __int64 v18; // rax
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 v21; // rcx
  __int64 v22; // r8
  unsigned int Error; // edi
  LPCWSTR lpPathName[2]; // [rsp+30h] [rbp-39h] BYREF
  _BYTE v25[16]; // [rsp+40h] [rbp-29h] BYREF
  LPCWSTR *v26; // [rsp+50h] [rbp-19h]
  __int64 v27; // [rsp+58h] [rbp-11h]
  const wchar_t *v28; // [rsp+60h] [rbp-9h]
  int v29; // [rsp+68h] [rbp-1h]
  int v30; // [rsp+6Ch] [rbp+3h]

  lpPathName[1] = (LPCWSTR)-2LL;
  v8 = (const WCHAR *)(ATL::CSimpleStringT<unsigned short,0>::CloneData(*((_QWORD *)this + 7) - 24LL) + 24);
  lpPathName[0] = v8;
  if ( (CreateDirectoryW(v8, 0)
     || (v9 = ATL::AtlHresultFromLastError(), v9 == (unsigned int)ATL::AtlHresultFromWin32(0xB7u)))
    && ((ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
           lpPathName,
           L"\\%hs",
           a3),
         v8 = lpPathName[0],
         CreateDirectoryW(lpPathName[0], 0))
     || (v9 = ATL::AtlHresultFromLastError(), v9 == (unsigned int)ATL::AtlHresultFromWin32(0xB7u)))
    && ((Microsoft::Windows::Performance::CNGenEventTraceExtender::CreatePathToPdbFromStoreRoot(
           v11,
           (unsigned int)lpPathName,
           *((_QWORD *)this + 7),
           (_DWORD)a3,
           (__int64)a4),
         v8 = lpPathName[0],
         CreateDirectoryW(lpPathName[0], 0))
     || (v9 = ATL::AtlHresultFromLastError(), v9 == (unsigned int)ATL::AtlHresultFromWin32(0xB7u))) )
  {
    ATL::CSimpleStringT<unsigned short,0>::Append(lpPathName, L"\\", 1);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator+=(
      lpPathName,
      a3);
    v12 = lpPathName[0];
    if ( (Microsoft_Windows_XPerfCoreEnableBits & 1) != 0 )
    {
      v13 = 10;
      if ( a2 )
      {
        v14 = -1;
        do
          ++v14;
        while ( a2[v14] );
        v15 = (unsigned int)(2 * v14 + 2);
      }
      else
      {
        v15 = 10;
      }
      v16 = L"NULL";
      v17 = a2;
      if ( !a2 )
        v17 = L"NULL";
      v26 = (LPCWSTR *)v17;
      v27 = (unsigned int)v15;
      if ( lpPathName[0] )
      {
        v18 = -1;
        do
          ++v18;
        while ( lpPathName[0][v18] );
        v16 = lpPathName[0];
        v13 = (unsigned int)(2 * v18 + 2);
      }
      v28 = v16;
      v29 = v13;
      v30 = 0;
      McGenEventWrite_EventWriteTransfer(v13, TraceMerge_NGEN_CopyingPDB_Start, v15, 3, v25);
    }
    if ( CopyFileW(a2, v12, 0) )
    {
      if ( (Microsoft_Windows_XPerfCoreEnableBits & 1) != 0 )
      {
        LODWORD(lpPathName[0]) = 0;
        v26 = lpPathName;
        v27 = 4;
        McGenEventWrite_EventWriteTransfer(v19, TraceMerge_NGEN_CopyingPDB_Stop, v20, 2, v25);
      }
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v12 - 2, 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v12 - 3) + 8LL))(*((_QWORD *)v12 - 3));
      return 0;
    }
    else
    {
      if ( (Microsoft_Windows_XPerfCoreEnableBits & 1) != 0 )
      {
        LODWORD(lpPathName[0]) = ATL::AtlHresultFromLastError();
        v26 = lpPathName;
        v27 = 4;
        McGenEventWrite_EventWriteTransfer(v21, TraceMerge_NGEN_CopyingPDB_Stop, v22, 2, v25);
      }
      Error = ATL::AtlHresultFromLastError();
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v12 - 2, 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v12 - 3) + 8LL))(*((_QWORD *)v12 - 3));
      return Error;
    }
  }
  else
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v8 - 2, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v8 - 3) + 8LL))(*((_QWORD *)v8 - 3));
    return v9;
  }
}

```

## disassembly

```asm
0x18001eb64  push    rbp
0x18001eb66  push    rbx
0x18001eb67  push    rsi
0x18001eb68  push    rdi
0x18001eb69  push    r12
0x18001eb6b  push    r13
0x18001eb6d  push    r14
0x18001eb6f  push    r15
0x18001eb71  lea     rbp, [rsp-1Fh]
0x18001eb76  sub     rsp, 88h
0x18001eb7d  mov     [rbp+57h+var_88], 0FFFFFFFFFFFFFFFEh
0x18001eb85  mov     rax, cs:__security_cookie
0x18001eb8c  xor     rax, rsp
0x18001eb8f  mov     [rbp+57h+var_50], rax
0x18001eb93  mov     r12, r9
0x18001eb96  mov     r14, r8
0x18001eb99  mov     rdi, rdx
0x18001eb9c  mov     r15, rcx
0x18001eb9f  mov     rcx, [rcx+38h]
0x18001eba3  sub     rcx, 18h
0x18001eba7  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18001ebac  lea     rbx, [rax+18h]
0x18001ebb0  mov     [rbp+57h+lpPathName], rbx
0x18001ebb4  xor     edx, edx; lpSecurityAttributes
0x18001ebb6  mov     rcx, rbx; lpPathName
0x18001ebb9  call    cs:__imp_CreateDirectoryW
0x18001ebc0  nop     dword ptr [rax+rax+00h]
0x18001ebc5  xor     r13d, r13d
0x18001ebc8  test    eax, eax
0x18001ebca  jnz     short loc_18001EC08
0x18001ebcc  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001ebd1  mov     esi, eax
0x18001ebd3  mov     ecx, 0B7h; unsigned int
0x18001ebd8  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18001ebdd  cmp     esi, eax
0x18001ebdf  jz      short loc_18001EC08
0x18001ebe1  lea     rdx, [rbx-18h]
0x18001ebe5  or      ecx, 0FFFFFFFFh
0x18001ebe8  lock xadd [rdx+10h], ecx
0x18001ebed  sub     ecx, 1
0x18001ebf0  jg      short loc_18001EC01
0x18001ebf2  mov     rcx, [rdx]
0x18001ebf5  mov     rax, [rcx]
0x18001ebf8  mov     rax, [rax+8]
0x18001ebfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec01  mov     eax, esi
0x18001ec03  jmp     loc_18001EE23
0x18001ec08  mov     r8, r14
0x18001ec0b  lea     rdx, aHs_0; "\\%hs"
0x18001ec12  lea     rcx, [rbp+57h+lpPathName]
0x18001ec16  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x18001ec1b  xor     edx, edx; lpSecurityAttributes
0x18001ec1d  mov     rbx, [rbp+57h+lpPathName]
0x18001ec21  mov     rcx, rbx; lpPathName
0x18001ec24  call    cs:__imp_CreateDirectoryW
0x18001ec2b  nop     dword ptr [rax+rax+00h]
0x18001ec30  test    eax, eax
0x18001ec32  jnz     short loc_18001EC49
0x18001ec34  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001ec39  mov     esi, eax
0x18001ec3b  mov     ecx, 0B7h; unsigned int
0x18001ec40  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18001ec45  cmp     esi, eax
0x18001ec47  jnz     short loc_18001EBE1
0x18001ec49  mov     [rsp+0C0h+var_A0], r12
0x18001ec4e  mov     r9, r14
0x18001ec51  mov     r8, [r15+38h]
0x18001ec55  lea     rdx, [rbp+57h+lpPathName]
0x18001ec59  call    ?CreatePathToPdbFromStoreRoot@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGPEBDAEBU_RSDS@@@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::CreatePathToPdbFromStoreRoot(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *,char const *,_RSDS const &)
0x18001ec5e  xor     edx, edx; lpSecurityAttributes
0x18001ec60  mov     rbx, [rbp+57h+lpPathName]
0x18001ec64  mov     rcx, rbx; lpPathName
0x18001ec67  call    cs:__imp_CreateDirectoryW
0x18001ec6e  nop     dword ptr [rax+rax+00h]
0x18001ec73  test    eax, eax
0x18001ec75  jnz     short loc_18001EC90
0x18001ec77  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001ec7c  mov     esi, eax
0x18001ec7e  mov     ecx, 0B7h; unsigned int
0x18001ec83  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18001ec88  cmp     esi, eax
0x18001ec8a  jnz     loc_18001EBE1
0x18001ec90  mov     esi, 1
0x18001ec95  mov     r8d, esi
0x18001ec98  lea     rdx, pszSrc; "\\"
0x18001ec9f  lea     rcx, [rbp+57h+lpPathName]
0x18001eca3  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x18001eca8  mov     rdx, r14
0x18001ecab  lea     rcx, [rbp+57h+lpPathName]
0x18001ecaf  call    ??Y?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator+=(char const *)
0x18001ecb4  mov     rbx, [rbp+57h+lpPathName]
0x18001ecb8  test    cs:Microsoft_Windows_XPerfCoreEnableBits, sil
0x18001ecbf  jz      loc_18001ED48
0x18001ecc5  lea     ecx, [rsi+9]
0x18001ecc8  test    rdi, rdi
0x18001eccb  jz      short loc_18001ECE5
0x18001eccd  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001ecd1  inc     rax
0x18001ecd4  cmp     [rdi+rax*2], r13w
0x18001ecd9  jnz     short loc_18001ECD1
0x18001ecdb  lea     r8d, ds:2[rax*2]
0x18001ece3  jmp     short loc_18001ECE8
0x18001ece5  mov     r8d, ecx
0x18001ece8  lea     rdx, aNull; "NULL"
0x18001ecef  mov     rax, rdi
0x18001ecf2  test    rdi, rdi
0x18001ecf5  cmovz   rax, rdx
0x18001ecf9  mov     [rbp+57h+var_70], rax
0x18001ecfd  mov     dword ptr [rbp+57h+var_68], r8d
0x18001ed01  mov     dword ptr [rbp+57h+var_68+4], r13d
0x18001ed05  test    rbx, rbx
0x18001ed08  jz      short loc_18001ED22
0x18001ed0a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001ed0e  inc     rax
0x18001ed11  cmp     [rbx+rax*2], r13w
0x18001ed16  jnz     short loc_18001ED0E
0x18001ed18  mov     rdx, rbx
0x18001ed1b  lea     ecx, ds:2[rax*2]
0x18001ed22  mov     [rbp+57h+var_60], rdx
0x18001ed26  mov     [rbp+57h+var_58], ecx
0x18001ed29  mov     [rbp+57h+var_54], r13d
0x18001ed2d  lea     rax, [rbp+57h+var_80]
0x18001ed31  mov     [rsp+0C0h+var_A0], rax
0x18001ed36  mov     r9d, 3
0x18001ed3c  lea     rdx, TraceMerge_NGEN_CopyingPDB_Start
0x18001ed43  call    McGenEventWrite_EventWriteTransfer
0x18001ed48  xor     r8d, r8d; bFailIfExists
0x18001ed4b  mov     rdx, rbx; lpNewFileName
0x18001ed4e  mov     rcx, rdi; lpExistingFileName
0x18001ed51  call    cs:__imp_CopyFileW
0x18001ed58  nop     dword ptr [rax+rax+00h]
0x18001ed5d  test    eax, eax
0x18001ed5f  jnz     short loc_18001EDC8
0x18001ed61  test    cs:Microsoft_Windows_XPerfCoreEnableBits, sil
0x18001ed68  jz      short loc_18001ED9D
0x18001ed6a  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001ed6f  mov     dword ptr [rbp+57h+lpPathName], eax
0x18001ed72  lea     rax, [rbp+57h+lpPathName]
0x18001ed76  mov     [rbp+57h+var_70], rax
0x18001ed7a  mov     [rbp+57h+var_68], 4
0x18001ed82  lea     rax, [rbp+57h+var_80]
0x18001ed86  mov     [rsp+0C0h+var_A0], rax
0x18001ed8b  mov     r9d, 2
0x18001ed91  lea     rdx, TraceMerge_NGEN_CopyingPDB_Stop
0x18001ed98  call    McGenEventWrite_EventWriteTransfer
0x18001ed9d  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001eda2  mov     edi, eax
0x18001eda4  lea     rdx, [rbx-18h]
0x18001eda8  or      ecx, 0FFFFFFFFh
0x18001edab  lock xadd [rdx+10h], ecx
0x18001edb0  sub     ecx, 1
0x18001edb3  jg      short loc_18001EDC4
0x18001edb5  mov     rcx, [rdx]
0x18001edb8  mov     r8, [rcx]
0x18001edbb  mov     rax, [r8+8]
0x18001edbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001edc4  mov     eax, edi
0x18001edc6  jmp     short loc_18001EE23
0x18001edc8  test    cs:Microsoft_Windows_XPerfCoreEnableBits, sil
0x18001edcf  jz      short loc_18001EE01
0x18001edd1  mov     dword ptr [rbp+57h+lpPathName], r13d
0x18001edd5  lea     rax, [rbp+57h+lpPathName]
0x18001edd9  mov     [rbp+57h+var_70], rax
0x18001eddd  mov     [rbp+57h+var_68], 4
0x18001ede5  lea     rax, [rbp+57h+var_80]
0x18001ede9  mov     [rsp+0C0h+var_A0], rax
0x18001edee  mov     r9d, 2
0x18001edf4  lea     rdx, TraceMerge_NGEN_CopyingPDB_Stop
0x18001edfb  call    McGenEventWrite_EventWriteTransfer
0x18001ee00  nop
0x18001ee01  lea     rdx, [rbx-18h]
0x18001ee05  or      eax, 0FFFFFFFFh
0x18001ee08  lock xadd [rdx+10h], eax
0x18001ee0d  sub     eax, 1
0x18001ee10  jg      short loc_18001EE21
0x18001ee12  mov     rcx, [rdx]
0x18001ee15  mov     rax, [rcx]
0x18001ee18  mov     rax, [rax+8]
0x18001ee1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee21  xor     eax, eax
0x18001ee23  mov     rcx, [rbp+57h+var_50]
0x18001ee27  xor     rcx, rsp; StackCookie
0x18001ee2a  call    __security_check_cookie
0x18001ee2f  add     rsp, 88h
0x18001ee36  pop     r15
0x18001ee38  pop     r14
0x18001ee3a  pop     r13
0x18001ee3c  pop     r12
0x18001ee3e  pop     rdi
0x18001ee3f  pop     rsi
0x18001ee40  pop     rbx
0x18001ee41  pop     rbp
0x18001ee42  retn
```
