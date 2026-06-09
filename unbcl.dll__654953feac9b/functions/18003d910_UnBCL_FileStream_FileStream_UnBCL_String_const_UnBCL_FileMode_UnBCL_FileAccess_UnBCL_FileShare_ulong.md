# UnBCL::FileStream::FileStream(UnBCL::String const *,UnBCL::FileMode,UnBCL::FileAccess,UnBCL::FileShare,ulong)

- ea: `0x18003d910`
- end: `0x18003de10`
- name: `??0FileStream@UnBCL@@QEAA@PEBVString@1@W4FileMode@1@W4FileAccess@1@W4FileShare@1@K@Z`
- size: `1280`
- prototype: ``
- caller_count: `3`
- callee_count: `22`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18003b590`
- `0x180059a40`
- `0x18005a850`

## callees

- `0x180001574`
- `0x18000225c`
- `0x180002ca0`
- `0x180002f90`
- `0x1800098b0`
- `0x1800099b0`
- `0x180009b40`
- `0x180009e7c`
- `0x180011570`
- `0x180012480`
- `0x18001a700`
- `0x180025720`
- `0x18002c640`
- `0x18003d910`
- `0x18003e270`
- `0x180047520`
- `0x1800477d0`
- `0x180048fb0`
- `0x180049500`
- `0x18004a440`
- `0x18005bb40`
- `0x180064340`

## import_xrefs

- `KERNEL32!GetFileType` at `0x18003dba4`
- `KERNEL32!GetFileType` at `0x18003dba4`
- `KERNEL32!GetLastError` at `0x18003dbf8`
- `KERNEL32!GetLastError` at `0x18003dbf8`
- `KERNEL32!CreateFileW` at `0x18003db73`
- `KERNEL32!CreateFileW` at `0x18003db73`

## string_xrefs

- `0x18003dc99`: `__cdecl UnBCL::FileStream::FileStream(const class UnBCL::String *,enum UnBCL::FileMode,enum UnBCL::FileAccess,enum UnBCL::FileShare,unsigned long)`
- `0x18003dce4`: `__cdecl UnBCL::FileStream::FileStream(const class UnBCL::String *,enum UnBCL::FileMode,enum UnBCL::FileAccess,enum UnBCL::FileShare,unsigned long)`
- `0x18003dd2f`: `__cdecl UnBCL::FileStream::FileStream(const class UnBCL::String *,enum UnBCL::FileMode,enum UnBCL::FileAccess,enum UnBCL::FileShare,unsigned long)`
- `0x18003dd7a`: `__cdecl UnBCL::FileStream::FileStream(const class UnBCL::String *,enum UnBCL::FileMode,enum UnBCL::FileAccess,enum UnBCL::FileShare,unsigned long)`
- `0x18003dda1`: `__cdecl UnBCL::FileStream::FileStream(const class UnBCL::String *,enum UnBCL::FileMode,enum UnBCL::FileAccess,enum UnBCL::FileShare,unsigned long)`
- `0x18003ddec`: `__cdecl UnBCL::FileStream::FileStream(const class UnBCL::String *,enum UnBCL::FileMode,enum UnBCL::FileAccess,enum UnBCL::FileShare,unsigned long)`
- `0x18003dd1b`: `null path to FileStream constructor`
- `0x18003dd66`: `empty path to FileStream constructor`
- `0x18003db13`: `append mode with access not write-only`
- `0x18003ddd8`: `attempt to create a FileStream on a non-disk file`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall UnBCL::FileStream::FileStream(
        __int64 a1,
        const struct UnBCL::String *a2,
        int a3,
        int a4,
        unsigned int a5,
        DWORD dwFlagsAndAttributes,
        int a7)
{
  __int64 v10; // rcx
  int v11; // r14d
  struct UnBCL::String *FullPath; // rax
  __int64 v13; // rax
  struct UnBCL::String *v14; // rax
  struct UnBCL::String *v15; // r15
  DWORD v16; // r14d
  DWORD v17; // r11d
  struct _SECURITY_ATTRIBUTES *v18; // r10
  DWORD dwCreationDisposition; // r8d
  int v20; // edx
  DWORD v21; // ecx
  UnBCL::ArgumentException *v22; // rax
  __int64 v23; // rax
  HANDLE FileW; // rsi
  _QWORD *v25; // rax
  DWORD LastError; // edi
  const struct UnBCL::String *v28; // rax
  struct UnBCL::String *DirectoryRoot; // rax
  __int64 v30; // rax
  const unsigned __int16 *InnerList; // rbx
  __int64 v32; // rax
  const unsigned __int16 *v33; // rax
  UnBCL::Win32Exception *v34; // rbx
  const struct UnBCL::String *v35; // rax
  __int64 v36; // rax
  UnBCL::ArgumentOutOfRangeException *v37; // rax
  __int64 v38; // rax
  UnBCL::ArgumentNullException *v39; // rax
  __int64 v40; // rax
  UnBCL::ArgumentException *v41; // rax
  __int64 v42; // rax
  UnBCL::NotSupportedException *v43; // rax
  __int64 v44; // rax
  _QWORD v45[2]; // [rsp+58h] [rbp-41h] BYREF
  void **v46; // [rsp+68h] [rbp-31h] BYREF
  struct UnBCL::String *v47; // [rsp+70h] [rbp-29h]
  _QWORD v48[2]; // [rsp+78h] [rbp-21h] BYREF
  __int128 v49; // [rsp+88h] [rbp-11h] BYREF
  __int64 v50; // [rsp+98h] [rbp-1h]
  __int64 pExceptionObject; // [rsp+F0h] [rbp+57h] BYREF

  if ( a7 )
  {
    *(_QWORD *)(a1 + 8) = &UnBCL::FileStream::`vbtable'{for `UnBCL::Stream'};
    *(_QWORD *)(a1 + 72) = &UnBCL::_::HTEnumerator<UnBCL::String *,UnBCL::String *,UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::TableKey,UnBCL::String *,UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::KeyTraits,&protected: static UnBCL::String * UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::RetrieveValue(ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::TableKey,UnBCL::String *,UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::KeyTraits,ATL::CElementTraits<UnBCL::String *>> const *,__POSITION * const &)>::`vbtable'{for `UnBCL::IEnumerator<UnBCL::String *>'};
    *(_QWORD *)(a1 + 40) = &UnBCL::Object::`vftable';
    *(_DWORD *)(a1 + 48) = 0;
    *(_DWORD *)(a1 + 52) = _InterlockedIncrement(&dword_1800FFC68);
  }
  *(_QWORD *)a1 = &UnBCL::Stream::`vftable'{for `UnBCL::Stream'};
  *(_QWORD *)(*(int *)(*(_QWORD *)(a1 + 8) + 4LL) + a1 + 8) = &UnBCL::Stream::`vftable'{for `UnBCL::Object'};
  *(_QWORD *)(*(int *)(*(_QWORD *)(a1 + 8) + 8LL) + a1 + 8) = &UnBCL::Stream::`vftable'{for `UnBCL::IDisposable'};
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)a1 = &UnBCL::FileStream::`vftable'{for `UnBCL::Stream'};
  *(_QWORD *)(*(int *)(*(_QWORD *)(a1 + 8) + 4LL) + a1 + 8) = &UnBCL::FileStream::`vftable'{for `UnBCL::Object'};
  *(_QWORD *)(*(int *)(*(_QWORD *)(a1 + 8) + 8LL) + a1 + 8) = &UnBCL::FileStream::`vftable'{for `UnBCL::IDisposable'};
  v10 = *(int *)(*(_QWORD *)(a1 + 8) + 8LL);
  *(_DWORD *)(v10 + a1 + 4) = v10 - 56;
  v11 = a4 & 1;
  *(_DWORD *)(a1 + 24) = v11;
  *(_QWORD *)(a1 + 32) = 0;
  if ( !a2 )
  {
    v39 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
    v45[0] = v39;
    if ( v39 )
      v40 = UnBCL::ArgumentNullException::ArgumentNullException(v39, L"null path to FileStream constructor");
    else
      v40 = 0;
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v40,
                         "__cdecl UnBCL::FileStream::FileStream(const class UnBCL::String *,enum UnBCL::FileMode,enum UnB"
                         "CL::FileAccess,enum UnBCL::FileShare,unsigned long)");
    throw (UnBCL::ArgumentNullException **)&pExceptionObject;
  }
  if ( !**((_WORD **)a2 + 2) )
  {
    v41 = (UnBCL::ArgumentException *)UnBCL::Object::operator new(0x38u);
    v45[0] = v41;
    if ( v41 )
      v42 = UnBCL::ArgumentException::ArgumentException(v41, L"empty path to FileStream constructor");
    else
      v42 = 0;
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v42,
                         "__cdecl UnBCL::FileStream::FileStream(const class UnBCL::String *,enum UnBCL::FileMode,enum UnB"
                         "CL::FileAccess,enum UnBCL::FileShare,unsigned long)");
    throw (UnBCL::ArgumentException **)&pExceptionObject;
  }
  FullPath = UnBCL::Path::GetFullPath(a2);
  v13 = UnBCL::_::MakeSmartPtr<UnBCL::String>(v48, FullPath);
  v14 = UnBCL::Path::WithLongPrefix(*(const struct UnBCL::String **)(v13 + 8), 1);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v46, v14);
  v48[0] = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(v48);
  v15 = v47;
  UnBCL::Path::CheckPathTooLong(v47);
  v16 = v11 << 30;
  v17 = v16 | 0x80000000;
  if ( (a4 & 2) == 0 )
    v17 = v16;
  v49 = 0;
  v50 = 0;
  v18 = 0;
  if ( (a5 & 1) != 0 )
  {
    LODWORD(v49) = 24;
    *((_QWORD *)&v49 + 1) = 0;
    LODWORD(v50) = 1;
    v18 = (struct _SECURITY_ATTRIBUTES *)&v49;
  }
  dwCreationDisposition = 4;
  v20 = (a5 >> 1) & 1 | 2;
  if ( (a5 & 4) == 0 )
    v20 = (a5 >> 1) & 1;
  v21 = v20 | 4;
  if ( (a5 & 8) == 0 )
    v21 = v20;
  if ( a3 )
  {
    switch ( a3 )
    {
      case 1:
        dwCreationDisposition = 2;
        break;
      case 2:
        dwCreationDisposition = 1;
        break;
      case 3:
        dwCreationDisposition = 3;
        break;
      default:
        if ( a3 != 4 )
        {
          if ( a3 != 5 )
          {
            v37 = (UnBCL::ArgumentOutOfRangeException *)UnBCL::Object::operator new(0x38u);
            v45[0] = v37;
            if ( v37 )
              v38 = UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(
                      v37,
                      L"invalid mode to FileStream constructor");
            else
              v38 = 0;
            pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                                 v38,
                                 "__cdecl UnBCL::FileStream::FileStream(const class UnBCL::String *,enum UnBCL::FileMode,"
                                 "enum UnBCL::FileAccess,enum UnBCL::FileShare,unsigned long)");
            throw (UnBCL::ArgumentOutOfRangeException **)&pExceptionObject;
          }
          dwCreationDisposition = 5;
        }
        break;
    }
  }
  else if ( a4 != 1 )
  {
    v22 = (UnBCL::ArgumentException *)UnBCL::Object::operator new(0x38u);
    v45[0] = v22;
    if ( v22 )
      v23 = UnBCL::ArgumentException::ArgumentException(v22, L"append mode with access not write-only");
    else
      v23 = 0;
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v23,
                         "__cdecl UnBCL::FileStream::FileStream(const class UnBCL::String *,enum UnBCL::FileMode,enum UnB"
                         "CL::FileAccess,enum UnBCL::FileShare,unsigned long)");
    throw (UnBCL::ArgumentException **)&pExceptionObject;
  }
  FileW = CreateFileW(*((LPCWSTR *)v15 + 2), v17, v21, v18, dwCreationDisposition, dwFlagsAndAttributes, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    if ( LastError == 3 )
    {
      v28 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::Decoder>::operator->(&v46);
      DirectoryRoot = UnBCL::Directory::GetDirectoryRoot(v28);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v45, DirectoryRoot);
      v30 = UnBCL::SmartPtr<UnBCL::Decoder>::operator->(v45);
      InnerList = (const unsigned __int16 *)UnBCL::CollectionBase<UnBCL::Object *>::get_InnerList(v30);
      v32 = UnBCL::SmartPtr<UnBCL::Decoder>::operator->(&v46);
      v33 = (const unsigned __int16 *)UnBCL::CollectionBase<UnBCL::Object *>::get_InnerList(v32);
      if ( !(unsigned int)UnBCL::String::Compare(v33, InnerList, 0) )
        LastError = 5;
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v45);
    }
    v34 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
    v45[0] = v34;
    if ( v34 )
    {
      v35 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::Decoder>::operator->(&v46);
      v36 = UnBCL::Win32Exception::Win32Exception(v34, LastError, v35);
    }
    else
    {
      v36 = 0;
    }
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v36,
                         "__cdecl UnBCL::FileStream::FileStream(const class UnBCL::String *,enum UnBCL::FileMode,enum UnB"
                         "CL::FileAccess,enum UnBCL::FileShare,unsigned long)");
    throw (UnBCL::Win32Exception **)&pExceptionObject;
  }
  v25 = operator new(8u);
  pExceptionObject = (__int64)v25;
  if ( v25 )
    *v25 = FileW;
  else
    v25 = 0;
  *(_QWORD *)(a1 + 32) = v25;
  if ( GetFileType(FileW) != 1 )
  {
    v43 = (UnBCL::NotSupportedException *)UnBCL::Object::operator new(0x38u);
    v45[0] = v43;
    if ( v43 )
      v44 = UnBCL::NotSupportedException::NotSupportedException(
              v43,
              L"attempt to create a FileStream on a non-disk file");
    else
      v44 = 0;
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v44,
                         "__cdecl UnBCL::FileStream::FileStream(const class UnBCL::String *,enum UnBCL::FileMode,enum UnB"
                         "CL::FileAccess,enum UnBCL::FileShare,unsigned long)");
    throw (UnBCL::NotSupportedException **)&pExceptionObject;
  }
  if ( !a3 )
    UnBCL::FileStream::Seek(a1, 0, 2);
  v46 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v46);
  return a1;
}

```

## disassembly

```asm
0x18003d910  mov     rax, rsp
0x18003d913  mov     [rax+8], rcx
0x18003d917  push    rbp
0x18003d918  push    rsi
0x18003d919  push    rdi
0x18003d91a  push    r12
0x18003d91c  push    r13
0x18003d91e  push    r14
0x18003d920  push    r15
0x18003d922  lea     rbp, [rax-47h]
0x18003d926  sub     rsp, 0A0h
0x18003d92d  mov     [rbp+3Fh+var_88], 0FFFFFFFFFFFFFFFEh
0x18003d935  mov     [rax+18h], rbx
0x18003d939  mov     esi, r9d
0x18003d93c  mov     edi, r8d
0x18003d93f  mov     r8, rdx
0x18003d942  mov     rbx, rcx
0x18003d945  xor     r12d, r12d
0x18003d948  mov     [rbp+3Fh+var_90], r12d
0x18003d94c  lea     r13d, [r12+1]
0x18003d951  cmp     [rbp+3Fh+arg_30], r12d
0x18003d955  jz      short loc_18003D99C
0x18003d957  lea     rax, ??_8FileStream@UnBCL@@7BStream@1@@; const UnBCL::FileStream::`vbtable'{for `UnBCL::Stream'}
0x18003d95e  mov     [rcx+8], rax
0x18003d962  lea     rax, ??_8?$HTEnumerator@PEAVString@UnBCL@@PEAV12@UTableKey@?$Hashtable@PEAVString@UnBCL@@PEAV12@@2@PEAV12@UKeyTraits@42@$1?RetrieveValue@42@KAPEAV12@PEBV?$CAtlMap@UTableKey@?$Hashtable@PEAVString@UnBCL@@PEAV12@@UnBCL@@PEAVString@3@UKeyTraits@23@V?$CElementTraits@PEAVString@UnBCL@@@ATL@@@ATL@@AEBQEAU__POSITION@@@Z@_@UnBCL@@7B?$IEnumerator@PEAVString@UnBCL@@@2@@; const UnBCL::_::HTEnumerator<UnBCL::String *,UnBCL::String *,UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::TableKey,UnBCL::String *,UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::KeyTraits,&UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::RetrieveValue(ATL::CAtlMap<UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::TableKey,UnBCL::String *,UnBCL::Hashtable<UnBCL::String *,UnBCL::String *>::KeyTraits,ATL::CElementTraits<UnBCL::String *>> const *,__POSITION * const &)>::`vbtable'{for `UnBCL::IEnumerator<UnBCL::String *>'}
0x18003d969  mov     [rcx+48h], rax
0x18003d96d  lea     rax, ??_7Object@UnBCL@@6B@; const UnBCL::Object::`vftable'
0x18003d974  mov     [rcx+28h], rax
0x18003d978  mov     [rcx+30h], r12d
0x18003d97c  mov     eax, r13d
0x18003d97f  lock xadd cs:dword_1800FFC68, eax
0x18003d987  add     eax, r13d
0x18003d98a  mov     [rcx+34h], eax
0x18003d98d  mov     [rbp+3Fh+var_90], r13d
0x18003d991  lea     eax, [r12+2]
0x18003d996  or      eax, r13d
0x18003d999  mov     [rbp+3Fh+var_90], eax
0x18003d99c  lea     rax, ??_7Stream@UnBCL@@6B01@@; const UnBCL::Stream::`vftable'{for `UnBCL::Stream'}
0x18003d9a3  mov     [rcx], rax
0x18003d9a6  mov     rax, [rcx+8]
0x18003d9aa  movsxd  rcx, dword ptr [rax+4]
0x18003d9ae  lea     rax, ??_7Stream@UnBCL@@6BObject@1@@; const UnBCL::Stream::`vftable'{for `UnBCL::Object'}
0x18003d9b5  mov     [rcx+rbx+8], rax
0x18003d9ba  mov     rax, [rbx+8]
0x18003d9be  movsxd  rcx, dword ptr [rax+8]
0x18003d9c2  lea     rax, ??_7Stream@UnBCL@@6BIDisposable@1@@; const UnBCL::Stream::`vftable'{for `UnBCL::IDisposable'}
0x18003d9c9  mov     [rcx+rbx+8], rax
0x18003d9ce  mov     [rbx+10h], r12
0x18003d9d2  lea     rax, ??_7FileStream@UnBCL@@6BStream@1@@; const UnBCL::FileStream::`vftable'{for `UnBCL::Stream'}
0x18003d9d9  mov     [rbx], rax
0x18003d9dc  mov     rax, [rbx+8]
0x18003d9e0  movsxd  rcx, dword ptr [rax+4]
0x18003d9e4  lea     rax, ??_7FileStream@UnBCL@@6BObject@1@@; const UnBCL::FileStream::`vftable'{for `UnBCL::Object'}
0x18003d9eb  mov     [rcx+rbx+8], rax
0x18003d9f0  mov     rax, [rbx+8]
0x18003d9f4  movsxd  rcx, dword ptr [rax+8]
0x18003d9f8  lea     rax, ??_7FileStream@UnBCL@@6BIDisposable@1@@; const UnBCL::FileStream::`vftable'{for `UnBCL::IDisposable'}
0x18003d9ff  mov     [rcx+rbx+8], rax
0x18003da04  mov     rax, [rbx+8]
0x18003da08  movsxd  rcx, dword ptr [rax+8]
0x18003da0c  lea     edx, [rcx-38h]
0x18003da0f  mov     [rcx+rbx+4], edx
0x18003da13  mov     r14d, esi
0x18003da16  and     r14d, r13d
0x18003da19  mov     [rbx+18h], r14d
0x18003da1d  mov     [rbx+20h], r12
0x18003da21  test    r8, r8
0x18003da24  jz      loc_18003DD08
0x18003da2a  mov     rax, [r8+10h]
0x18003da2e  cmp     [rax], r12w
0x18003da32  jz      loc_18003DD53
0x18003da38  mov     rcx, r8; struct UnBCL::String *
0x18003da3b  call    ?GetFullPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Path::GetFullPath(UnBCL::String const *)
0x18003da40  mov     rdx, rax
0x18003da43  lea     rcx, [rbp+3Fh+var_60]
0x18003da47  call    ??$MakeSmartPtr@VString@UnBCL@@@_@UnBCL@@YA?AV?$SmartPtr@VString@UnBCL@@@1@PEAVString@1@@Z; UnBCL::_::MakeSmartPtr<UnBCL::String>(UnBCL::String *)
0x18003da4c  nop
0x18003da4d  mov     edx, r13d; int
0x18003da50  mov     rcx, [rax+8]; struct UnBCL::String *
0x18003da54  call    ?WithLongPrefix@Path@UnBCL@@SAPEAVString@2@PEBV32@H@Z; UnBCL::Path::WithLongPrefix(UnBCL::String const *,int)
0x18003da59  mov     rdx, rax
0x18003da5c  lea     rcx, [rbp+3Fh+var_70]
0x18003da60  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18003da65  nop
0x18003da66  lea     rax, ??_7?$SmartPtr@VString@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::String>::`vftable'
0x18003da6d  mov     [rbp+3Fh+var_60], rax
0x18003da71  lea     rcx, [rbp+3Fh+var_60]
0x18003da75  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18003da7a  mov     r15, [rbp+3Fh+var_68]
0x18003da7e  mov     rcx, r15; struct UnBCL::String *
0x18003da81  call    ?CheckPathTooLong@Path@UnBCL@@KAXPEBVString@2@@Z; UnBCL::Path::CheckPathTooLong(UnBCL::String const *)
0x18003da86  shl     r14d, 1Eh
0x18003da8a  mov     r11d, r14d
0x18003da8d  bts     r11d, 1Fh
0x18003da92  test    sil, 2
0x18003da96  cmovz   r11d, r14d
0x18003da9a  xorps   xmm0, xmm0
0x18003da9d  xor     eax, eax
0x18003da9f  movups  [rbp+3Fh+var_50], xmm0
0x18003daa3  mov     [rbp+3Fh+var_40], rax
0x18003daa7  mov     r10, r12
0x18003daaa  mov     r9d, [rbp+3Fh+arg_20]
0x18003daae  test    r13b, r9b
0x18003dab1  jz      short loc_18003DAC6
0x18003dab3  mov     dword ptr [rbp+3Fh+var_50], 18h
0x18003daba  mov     qword ptr [rbp+3Fh+var_50+8], r12
0x18003dabe  mov     dword ptr [rbp+3Fh+var_40], r13d
0x18003dac2  lea     r10, [rbp+3Fh+var_50]
0x18003dac6  mov     ecx, r9d
0x18003dac9  shr     ecx, 1
0x18003dacb  and     ecx, r13d
0x18003dace  mov     r8d, 4
0x18003dad4  mov     edx, ecx
0x18003dad6  lea     r14d, [r8-2]
0x18003dada  or      edx, r14d
0x18003dadd  test    r8b, r9b
0x18003dae0  cmovz   edx, ecx
0x18003dae3  mov     ecx, edx
0x18003dae5  or      ecx, r8d
0x18003dae8  test    r9b, 8
0x18003daec  cmovz   ecx, edx
0x18003daef  lea     eax, [r8+1]
0x18003daf3  test    edi, edi
0x18003daf5  jnz     short loc_18003DB27
0x18003daf7  cmp     esi, r13d
0x18003dafa  jz      short loc_18003DB55
0x18003dafc  mov     ecx, 38h ; '8'; unsigned __int64
0x18003db01  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18003db06  mov     [rbp+3Fh+var_80], rax
0x18003db0a  test    rax, rax
0x18003db0d  jz      loc_18003DD9E
0x18003db13  lea     rdx, aAppendModeWith; "append mode with access not write-only"
0x18003db1a  mov     rcx, rax; this
0x18003db1d  call    ??0ArgumentException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentException::ArgumentException(ushort const *)
0x18003db22  jmp     loc_18003DDA1
0x18003db27  cmp     edi, r13d
0x18003db2a  jnz     short loc_18003DB31
0x18003db2c  mov     r8d, r14d
0x18003db2f  jmp     short loc_18003DB55
0x18003db31  cmp     edi, r14d
0x18003db34  jnz     short loc_18003DB3B
0x18003db36  mov     r8d, r13d
0x18003db39  jmp     short loc_18003DB55
0x18003db3b  cmp     edi, 3
0x18003db3e  jnz     short loc_18003DB45
0x18003db40  mov     r8d, edi
0x18003db43  jmp     short loc_18003DB55
0x18003db45  cmp     edi, r8d
0x18003db48  jz      short loc_18003DB55
0x18003db4a  cmp     edi, eax
0x18003db4c  jnz     loc_18003DCBD
0x18003db52  mov     r8d, eax
0x18003db55  mov     [rsp+30h], r12; hTemplateFile
0x18003db5a  mov     eax, [rbp+3Fh+arg_28]
0x18003db5d  mov     [rsp+0D0h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x18003db61  mov     [rsp+0D0h+dwCreationDisposition], r8d; dwCreationDisposition
0x18003db66  mov     r9, r10; lpSecurityAttributes
0x18003db69  mov     r8d, ecx; dwShareMode
0x18003db6c  mov     edx, r11d; dwDesiredAccess
0x18003db6f  mov     rcx, [r15+10h]; lpFileName
0x18003db73  call    cs:__imp_CreateFileW
0x18003db79  mov     rsi, rax
0x18003db7c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003db80  jz      short loc_18003DBF8
0x18003db82  mov     ecx, 8; Size
0x18003db87  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003db8c  mov     [rbp+3Fh+pExceptionObject], rax
0x18003db90  test    rax, rax
0x18003db93  jz      short loc_18003DB9A
0x18003db95  mov     [rax], rsi
0x18003db98  jmp     short loc_18003DB9D
0x18003db9a  mov     rax, r12
0x18003db9d  mov     [rbx+20h], rax
0x18003dba1  mov     rcx, rsi; hFile
0x18003dba4  call    cs:__imp_GetFileType
0x18003dbaa  cmp     eax, r13d
0x18003dbad  jnz     loc_18003DDC5
0x18003dbb3  test    edi, edi
0x18003dbb5  jnz     short loc_18003DBC5
0x18003dbb7  mov     r8d, r14d
0x18003dbba  xor     edx, edx
0x18003dbbc  mov     rcx, rbx
0x18003dbbf  call    ?Seek@FileStream@UnBCL@@UEAA_J_JW4SeekOrigin@2@@Z; UnBCL::FileStream::Seek(__int64,UnBCL::SeekOrigin)
0x18003dbc4  nop
0x18003dbc5  lea     rax, ??_7?$SmartPtr@VString@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::String>::`vftable'
0x18003dbcc  mov     [rbp+3Fh+var_70], rax
0x18003dbd0  lea     rcx, [rbp+3Fh+var_70]
0x18003dbd4  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18003dbd9  nop
0x18003dbda  mov     rax, rbx
0x18003dbdd  mov     rbx, [rsp+0D0h+arg_10]
0x18003dbe5  add     rsp, 0A0h
0x18003dbec  pop     r15
0x18003dbee  pop     r14
0x18003dbf0  pop     r13
0x18003dbf2  pop     r12
0x18003dbf4  pop     rdi
0x18003dbf5  pop     rsi
0x18003dbf6  pop     rbp
0x18003dbf7  retn
0x18003dbf8  call    cs:__imp_GetLastError
0x18003dbfe  nop
0x18003dbff  mov     edi, eax
0x18003dc01  cmp     eax, 3
0x18003dc04  jnz     short loc_18003DC68
0x18003dc06  lea     rcx, [rbp+3Fh+var_70]
0x18003dc0a  call    ??C?$SmartPtr@VDecoder@UnBCL@@@UnBCL@@QEBAPEAVDecoder@1@XZ; UnBCL::SmartPtr<UnBCL::Decoder>::operator->(void)
0x18003dc0f  mov     rcx, rax; struct UnBCL::String *
0x18003dc12  call    ?GetDirectoryRoot@Directory@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Directory::GetDirectoryRoot(UnBCL::String const *)
0x18003dc17  mov     rdx, rax
0x18003dc1a  lea     rcx, [rbp+3Fh+var_80]
0x18003dc1e  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18003dc23  nop
0x18003dc24  lea     rcx, [rbp+3Fh+var_80]
0x18003dc28  call    ??C?$SmartPtr@VDecoder@UnBCL@@@UnBCL@@QEBAPEAVDecoder@1@XZ; UnBCL::SmartPtr<UnBCL::Decoder>::operator->(void)
0x18003dc2d  mov     rcx, rax
0x18003dc30  call    ?get_InnerList@?$CollectionBase@PEAVObject@UnBCL@@@UnBCL@@MEBAPEBV?$ArrayList@PEAVObject@UnBCL@@@2@XZ; UnBCL::CollectionBase<UnBCL::Object *>::get_InnerList(void)
0x18003dc35  mov     rbx, rax
0x18003dc38  lea     rcx, [rbp+3Fh+var_70]
0x18003dc3c  call    ??C?$SmartPtr@VDecoder@UnBCL@@@UnBCL@@QEBAPEAVDecoder@1@XZ; UnBCL::SmartPtr<UnBCL::Decoder>::operator->(void)
0x18003dc41  mov     rcx, rax
0x18003dc44  call    ?get_InnerList@?$CollectionBase@PEAVObject@UnBCL@@@UnBCL@@MEBAPEBV?$ArrayList@PEAVObject@UnBCL@@@2@XZ; UnBCL::CollectionBase<UnBCL::Object *>::get_InnerList(void)
0x18003dc49  xor     r8d, r8d; int
0x18003dc4c  mov     rdx, rbx; unsigned __int16 *
0x18003dc4f  mov     rcx, rax; unsigned __int16 *
0x18003dc52  call    ?Compare@String@UnBCL@@SAHPEBG0H@Z; UnBCL::String::Compare(ushort const *,ushort const *,int)
0x18003dc57  test    eax, eax
0x18003dc59  lea     eax, [rdi+2]
0x18003dc5c  cmovz   edi, eax
0x18003dc5f  lea     rcx, [rbp+3Fh+var_80]; void *
0x18003dc63  call    ??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x18003dc68  mov     ecx, 40h ; '@'; unsigned __int64
0x18003dc6d  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18003dc72  mov     rbx, rax
0x18003dc75  mov     [rbp+3Fh+var_80], rax
0x18003dc79  test    rax, rax
0x18003dc7c  jz      short loc_18003DC96
0x18003dc7e  lea     rcx, [rbp+3Fh+var_70]
0x18003dc82  call    ??C?$SmartPtr@VDecoder@UnBCL@@@UnBCL@@QEBAPEAVDecoder@1@XZ; UnBCL::SmartPtr<UnBCL::Decoder>::operator->(void)
0x18003dc87  mov     r8, rax; struct UnBCL::String *
0x18003dc8a  mov     edx, edi; dwMessageId
0x18003dc8c  mov     rcx, rbx; this
0x18003dc8f  call    ??0Win32Exception@UnBCL@@QEAA@KPEBVString@1@@Z; UnBCL::Win32Exception::Win32Exception(ulong,UnBCL::String const *)
0x18003dc94  jmp     short loc_18003DC99
0x18003dc96  mov     rax, r12
0x18003dc99  lea     rdx, aCdeclUnbclFile_1; "__cdecl UnBCL::FileStream::FileStream(c"...
0x18003dca0  mov     rcx, rax
0x18003dca3  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18003dca8  mov     [rbp+3Fh+pExceptionObject], rax
0x18003dcac  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
0x18003dcb3  lea     rcx, [rbp+3Fh+pExceptionObject]; pExceptionObject
0x18003dcb7  call    _CxxThrowException_0
0x18003dcbd  mov     ecx, 38h ; '8'; unsigned __int64
0x18003dcc2  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18003dcc7  mov     [rbp+3Fh+var_80], rax
0x18003dccb  test    rax, rax
0x18003dcce  jz      short loc_18003DCE1
0x18003dcd0  lea     rdx, aInvalidModeToF; "invalid mode to FileStream constructor"
0x18003dcd7  mov     rcx, rax; this
0x18003dcda  call    ??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(ushort const *)
0x18003dcdf  jmp     short loc_18003DCE4
0x18003dce1  mov     rax, r12
0x18003dce4  lea     rdx, aCdeclUnbclFile_1; "__cdecl UnBCL::FileStream::FileStream(c"...
0x18003dceb  mov     rcx, rax
0x18003dcee  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18003dcf3  mov     [rbp+3Fh+pExceptionObject], rax
0x18003dcf7  lea     rdx, _TI6PEAVArgumentOutOfRangeException@UnBCL@@; pThrowInfo
0x18003dcfe  lea     rcx, [rbp+3Fh+pExceptionObject]; pExceptionObject
0x18003dd02  call    _CxxThrowException_0
0x18003dd08  mov     ecx, 38h ; '8'; unsigned __int64
0x18003dd0d  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18003dd12  mov     [rbp+3Fh+var_80], rax
0x18003dd16  test    rax, rax
0x18003dd19  jz      short loc_18003DD2C
0x18003dd1b  lea     rdx, aNullPathToFile_0; "null path to FileStream constructor"
0x18003dd22  mov     rcx, rax; this
0x18003dd25  call    ??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentNullException::ArgumentNullException(ushort const *)
0x18003dd2a  jmp     short loc_18003DD2F
0x18003dd2c  mov     rax, r12
0x18003dd2f  lea     rdx, aCdeclUnbclFile_1; "__cdecl UnBCL::FileStream::FileStream(c"...
0x18003dd36  mov     rcx, rax
0x18003dd39  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18003dd3e  mov     [rbp+3Fh+pExceptionObject], rax
0x18003dd42  lea     rdx, _TI6PEAVArgumentNullException@UnBCL@@; pThrowInfo
0x18003dd49  lea     rcx, [rbp+3Fh+pExceptionObject]; pExceptionObject
0x18003dd4d  call    _CxxThrowException_0
0x18003dd53  mov     ecx, 38h ; '8'; unsigned __int64
0x18003dd58  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18003dd5d  mov     [rbp+3Fh+var_80], rax
0x18003dd61  test    rax, rax
0x18003dd64  jz      short loc_18003DD77
0x18003dd66  lea     rdx, aEmptyPathToFil; "empty path to FileStream constructor"
0x18003dd6d  mov     rcx, rax; this
0x18003dd70  call    ??0ArgumentException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentException::ArgumentException(ushort const *)
0x18003dd75  jmp     short loc_18003DD7A
0x18003dd77  mov     rax, r12
0x18003dd7a  lea     rdx, aCdeclUnbclFile_1; "__cdecl UnBCL::FileStream::FileStream(c"...
0x18003dd81  mov     rcx, rax
0x18003dd84  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18003dd89  mov     [rbp+3Fh+pExceptionObject], rax
  ... truncated ...
```
