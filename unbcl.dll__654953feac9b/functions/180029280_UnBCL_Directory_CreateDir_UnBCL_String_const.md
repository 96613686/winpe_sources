# UnBCL::Directory::CreateDir(UnBCL::String const *)

- ea: `0x180029280`
- end: `0x180029746`
- name: `?CreateDir@Directory@UnBCL@@SAPEAVDirectoryInfo@2@PEBVString@2@@Z`
- size: `1222`
- prototype: `struct UnBCL::DirectoryInfo *__fastcall(const struct UnBCL::String *)`
- caller_count: `2`
- callee_count: `28`
- tags: `file_ops, registry_config`

## callers

- `0x180028470`
- `0x180029980`

## callees

- `0x18000225c`
- `0x180002ca0`
- `0x180002f90`
- `0x1800098b0`
- `0x1800099b0`
- `0x180009e7c`
- `0x180011530`
- `0x180011570`
- `0x180025720`
- `0x180026784`
- `0x180026be8`
- `0x180027a84`
- `0x180029280`
- `0x18002bca0`
- `0x18002c640`
- `0x180031624`
- `0x1800477d0`
- `0x180048fb0`
- `0x180049500`
- `0x18004a440`
- `0x18004a8b0`
- `0x18005d2b0`
- `0x18005de90`
- `0x18005f390`
- `0x180060150`
- `0x1800641a0`
- `0x180064340`
- `0x180069020`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800294c6`
- `KERNEL32!GetLastError` at `0x1800294c6`
- `KERNEL32!CreateDirectoryW` at `0x1800294bc`
- `KERNEL32!CreateDirectoryW` at `0x1800294bc`
- `KERNEL32!GetFileAttributesW` at `0x1800294d9`
- `KERNEL32!GetFileAttributesW` at `0x1800294d9`

## string_xrefs

- `0x1800295de`: `class UnBCL::DirectoryInfo *__cdecl UnBCL::Directory::CreateDir(const class UnBCL::String *)`
- `0x18002962c`: `class UnBCL::DirectoryInfo *__cdecl UnBCL::Directory::CreateDir(const class UnBCL::String *)`
- `0x18002967a`: `class UnBCL::DirectoryInfo *__cdecl UnBCL::Directory::CreateDir(const class UnBCL::String *)`
- `0x1800296cd`: `class UnBCL::DirectoryInfo *__cdecl UnBCL::Directory::CreateDir(const class UnBCL::String *)`
- `0x180029720`: `class UnBCL::DirectoryInfo *__cdecl UnBCL::Directory::CreateDir(const class UnBCL::String *)`
- `0x180029618`: `null path to Directory::CreateDirectory`
- `0x180029666`: `empty path to Directory::CreateDirectory`
- `0x1800296b4`: `invalid UNC path to Directory::CreateDirectory`
- `0x180029707`: `root of directory to create not found`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
struct UnBCL::DirectoryInfo *__fastcall UnBCL::Directory::CreateDir(const struct UnBCL::String *a1)
{
  struct UnBCL::String *FullPath; // rax
  __int64 v3; // rax
  struct UnBCL::String *v4; // rax
  struct UnBCL::String *v5; // rdi
  struct UnBCL::String *v6; // rax
  UnBCL::String *v7; // r14
  int v8; // ebx
  const unsigned __int16 *Chars; // rax
  const unsigned __int16 *v10; // rax
  int IndexOfAny; // ebx
  struct UnBCL::String *DirectoryRoot; // rax
  struct UnBCL::String *v13; // rax
  __int64 v14; // rax
  int v15; // ebx
  DWORD LastError; // ebx
  int v17; // edi
  __int64 Item; // rax
  struct UnBCL::String *v19; // rsi
  _BYTE *v20; // rax
  _BYTE *v21; // rcx
  UnBCL::Win32Exception *v23; // rdi
  const struct UnBCL::String *v24; // rax
  __int64 v25; // rax
  UnBCL::ArgumentNullException *v26; // rax
  __int64 v27; // rax
  UnBCL::ArgumentException *v28; // rax
  __int64 v29; // rax
  UnBCL::Win32Exception *v30; // rax
  __int64 v31; // rax
  UnBCL::Win32Exception *v32; // rax
  __int64 v33; // rax
  __int64 pExceptionObject; // [rsp+20h] [rbp-E0h] BYREF
  UnBCL::ArgumentNullException *v35; // [rsp+28h] [rbp-D8h]
  void **v36; // [rsp+30h] [rbp-D0h] BYREF
  struct UnBCL::String *v37; // [rsp+38h] [rbp-C8h]
  void **v38; // [rsp+40h] [rbp-C0h] BYREF
  struct UnBCL::String *v39; // [rsp+48h] [rbp-B8h]
  void **v40; // [rsp+50h] [rbp-B0h] BYREF
  UnBCL::String *v41; // [rsp+58h] [rbp-A8h]
  _BYTE v42[8]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v43; // [rsp+68h] [rbp-98h]
  struct UnBCL::String *v44[3]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v45[24]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v46[16]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v47; // [rsp+B0h] [rbp-50h]
  void **v48; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v49[16]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 v50[2]; // [rsp+120h] [rbp+20h] BYREF
  __int16 v51; // [rsp+124h] [rbp+24h]

  v44[2] = (struct UnBCL::String *)-2LL;
  if ( !a1 )
  {
    v26 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
    v35 = v26;
    if ( v26 )
      v27 = UnBCL::ArgumentNullException::ArgumentNullException(v26, L"null path to Directory::CreateDirectory");
    else
      v27 = 0;
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v27,
                         "class UnBCL::DirectoryInfo *__cdecl UnBCL::Directory::CreateDir(const class UnBCL::String *)");
    throw (UnBCL::ArgumentNullException **)&pExceptionObject;
  }
  if ( !**((_WORD **)a1 + 2) )
  {
    v28 = (UnBCL::ArgumentException *)UnBCL::Object::operator new(0x38u);
    v35 = v28;
    if ( v28 )
      v29 = UnBCL::ArgumentException::ArgumentException(v28, L"empty path to Directory::CreateDirectory");
    else
      v29 = 0;
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v29,
                         "class UnBCL::DirectoryInfo *__cdecl UnBCL::Directory::CreateDir(const class UnBCL::String *)");
    throw (UnBCL::ArgumentException **)&pExceptionObject;
  }
  if ( !(unsigned int)UnBCL::Directory::Exists(a1) )
  {
    LODWORD(pExceptionObject) = 0;
    FullPath = UnBCL::Path::GetFullPath(a1);
    v3 = UnBCL::_::MakeSmartPtr<UnBCL::String>(&v36, FullPath);
    v4 = UnBCL::Path::WithLongPrefix(*(const struct UnBCL::String **)(v3 + 8), 1);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v38, v4);
    v36 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
    UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v36);
    v5 = v39;
    v6 = UnBCL::Path::WithoutLongPrefix(v39, (int *)&pExceptionObject);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v40, v6);
    UnBCL::Path::CheckPathTooLong(v5);
    v7 = v41;
    v8 = *(_DWORD *)(*((_QWORD *)v41 + 2) - 16LL);
    if ( v8 >= 2 )
    {
      Chars = UnBCL::String::get_Chars(v41, v8 - 1);
      if ( *Chars == 92 || *Chars == 47 )
        --v8;
      if ( v8 == 2 )
      {
        v10 = UnBCL::String::get_Chars(v7, 1);
        if ( *v10 == 92 || *v10 == 47 )
        {
          v30 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
          v35 = v30;
          if ( v30 )
            v31 = UnBCL::Win32Exception::Win32Exception(v30, 0x57u, L"invalid UNC path to Directory::CreateDirectory");
          else
            v31 = 0;
          pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                               v31,
                               "class UnBCL::DirectoryInfo *__cdecl UnBCL::Directory::CreateDir(const class UnBCL::String *)");
          throw (UnBCL::Win32Exception **)&pExceptionObject;
        }
      }
    }
    *(_DWORD *)v50 = 3080284;
    v51 = 0;
    IndexOfAny = *(_DWORD *)(*((_QWORD *)v5 + 2) - 16LL);
    UnBCL::ArrayList<UnBCL::SmartPtr<UnBCL::String>>::ArrayList<UnBCL::SmartPtr<UnBCL::String>>(v46);
    DirectoryRoot = UnBCL::Directory::GetDirectoryRoot(v5);
    UnBCL::StringPtr::StringPtr((UnBCL::StringPtr *)v42, DirectoryRoot);
    if ( !(unsigned int)UnBCL::Directory::Exists(*(struct UnBCL::String **)((char *)v44 + *(int *)(v43 + 4))) )
    {
      v32 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
      v35 = v32;
      if ( v32 )
        v33 = UnBCL::Win32Exception::Win32Exception(v32, 3u, L"root of directory to create not found");
      else
        v33 = 0;
      pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                           v33,
                           "class UnBCL::DirectoryInfo *__cdecl UnBCL::Directory::CreateDir(const class UnBCL::String *)");
      throw (UnBCL::Win32Exception **)&pExceptionObject;
    }
    while ( 1 )
    {
      v13 = UnBCL::String::Substring(v5, 0, IndexOfAny);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v36, v13);
      if ( (unsigned int)UnBCL::Directory::Exists(v37) )
        break;
      v35 = (UnBCL::ArgumentNullException *)v45;
      v14 = UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v45, &v36);
      UnBCL::ArrayList<UnBCL::SmartPtr<UnBCL::String>>::Add(v49, v14);
      v15 = IndexOfAny - 1;
      v36 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
      UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v36);
      if ( v15 > (int)pExceptionObject )
      {
        IndexOfAny = UnBCL::String::LastIndexOfAny(v5, v50, v15, v15);
        if ( IndexOfAny >= 0 )
          continue;
      }
      goto LABEL_17;
    }
    v36 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
    UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v36);
LABEL_17:
    LastError = 0;
    v17 = *(_DWORD *)(v47 + 8) - 1;
    if ( v17 >= 0 )
    {
      do
      {
        Item = UnBCL::ArrayList<UnBCL::SmartPtr<UnBCL::String>>::get_Item(v49, (unsigned int)v17);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v36, Item);
        v19 = v37;
        if ( !CreateDirectoryW(*((LPCWSTR *)v37 + 2), 0) )
        {
          LastError = GetLastError();
          if ( LastError == 183 && (GetFileAttributesW(*((LPCWSTR *)v19 + 2)) & 0x10) != 0 )
            LastError = 0;
        }
        v36 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
        UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v36);
        --v17;
      }
      while ( v17 >= 0 );
      if ( LastError )
      {
        v23 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
        v35 = v23;
        if ( v23 )
        {
          v24 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::Decoder>::operator->(&v38);
          v25 = UnBCL::Win32Exception::Win32Exception(v23, LastError, v24);
        }
        else
        {
          v25 = 0;
        }
        pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                             v25,
                             "class UnBCL::DirectoryInfo *__cdecl UnBCL::Directory::CreateDir(const class UnBCL::String *)");
        throw (UnBCL::Win32Exception **)&pExceptionObject;
      }
    }
    v44[0] = (struct UnBCL::String *)&UnBCL::SmartPtr<UnBCL::String>::`vftable';
    UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(v44);
    UnBCL::ArrayList<UnBCL::SmartPtr<UnBCL::String>>::~ArrayList<UnBCL::SmartPtr<UnBCL::String>>(&v48);
    v48 = &UnBCL::Object::`vftable';
    v40 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
    UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v40);
    v38 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
    UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v38);
  }
  v20 = UnBCL::Object::operator new(0x10u);
  v21 = v20;
  v35 = (UnBCL::ArgumentNullException *)v20;
  if ( !v20 )
    return 0;
  *(_OWORD *)v20 = 0;
  *(_QWORD *)v20 = &UnBCL::Object::`vftable';
  *((_DWORD *)v20 + 2) = 0;
  *((_DWORD *)v20 + 3) = _InterlockedIncrement(&dword_1800FFC68);
  *(_QWORD *)v20 = &UnBCL::DirectoryInfo::`vftable';
  return (struct UnBCL::DirectoryInfo *)v21;
}

```

## disassembly

```asm
0x180029280  push    rbp
0x180029282  push    rbx
0x180029283  push    rsi
0x180029284  push    rdi
0x180029285  push    r12
0x180029287  push    r13
0x180029289  push    r14
0x18002928b  push    r15
0x18002928d  lea     rbp, [rsp-38h]
0x180029292  sub     rsp, 138h
0x180029299  mov     [rbp+70h+var_F0], 0FFFFFFFFFFFFFFFEh
0x1800292a1  mov     rax, cs:__security_cookie
0x1800292a8  xor     rax, rsp
0x1800292ab  mov     [rbp+70h+var_48], rax
0x1800292af  mov     rbx, rcx
0x1800292b2  xor     r15d, r15d
0x1800292b5  test    rcx, rcx
0x1800292b8  jz      loc_180029604
0x1800292be  mov     rax, [rcx+10h]
0x1800292c2  cmp     [rax], r15w
0x1800292c6  jz      loc_180029652
0x1800292cc  call    ?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z; UnBCL::Directory::Exists(UnBCL::String const *)
0x1800292d1  lea     r12d, [r15+1]
0x1800292d5  lea     rdi, ??_7Object@UnBCL@@6B@; const UnBCL::Object::`vftable'
0x1800292dc  test    eax, eax
0x1800292de  jnz     loc_180029544
0x1800292e4  mov     dword ptr [rsp+170h+pExceptionObject], r15d
0x1800292e9  mov     rcx, rbx; struct UnBCL::String *
0x1800292ec  call    ?GetFullPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Path::GetFullPath(UnBCL::String const *)
0x1800292f1  mov     rdx, rax
0x1800292f4  lea     rcx, [rsp+170h+var_140]
0x1800292f9  call    ??$MakeSmartPtr@VString@UnBCL@@@_@UnBCL@@YA?AV?$SmartPtr@VString@UnBCL@@@1@PEAVString@1@@Z; UnBCL::_::MakeSmartPtr<UnBCL::String>(UnBCL::String *)
0x1800292fe  nop
0x1800292ff  mov     edx, r12d; int
0x180029302  mov     rcx, [rax+8]; struct UnBCL::String *
0x180029306  call    ?WithLongPrefix@Path@UnBCL@@SAPEAVString@2@PEBV32@H@Z; UnBCL::Path::WithLongPrefix(UnBCL::String const *,int)
0x18002930b  mov     rdx, rax
0x18002930e  lea     rcx, [rsp+170h+var_130]
0x180029313  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180029318  nop
0x180029319  lea     r13, ??_7?$SmartPtr@VString@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::String>::`vftable'
0x180029320  mov     [rsp+170h+var_140], r13
0x180029325  lea     rcx, [rsp+170h+var_140]
0x18002932a  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18002932f  mov     rdi, [rsp+170h+var_128]
0x180029334  lea     rdx, [rsp+170h+pExceptionObject]; int *
0x180029339  mov     rcx, rdi; struct UnBCL::String *
0x18002933c  call    ?WithoutLongPrefix@Path@UnBCL@@SAPEAVString@2@PEBV32@AEAH@Z; UnBCL::Path::WithoutLongPrefix(UnBCL::String const *,int &)
0x180029341  mov     rdx, rax
0x180029344  lea     rcx, [rsp+170h+var_120]
0x180029349  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18002934e  nop
0x18002934f  mov     rcx, rdi; struct UnBCL::String *
0x180029352  call    ?CheckPathTooLong@Path@UnBCL@@KAXPEBVString@2@@Z; UnBCL::Path::CheckPathTooLong(UnBCL::String const *)
0x180029357  mov     r14, [rsp+170h+var_118]
0x18002935c  mov     rax, [r14+10h]
0x180029360  mov     ebx, [rax-10h]
0x180029363  lea     esi, [r15+2Fh]
0x180029367  cmp     ebx, 2
0x18002936a  jl      short loc_1800293AB
0x18002936c  lea     edx, [rbx-1]; int
0x18002936f  mov     rcx, r14; this
0x180029372  call    ?get_Chars@String@UnBCL@@QEBAAEBGH@Z; UnBCL::String::get_Chars(int)
0x180029377  lea     ecx, [rsi+2Dh]
0x18002937a  cmp     [rax], cx
0x18002937d  jz      short loc_180029384
0x18002937f  cmp     [rax], si
0x180029382  jnz     short loc_180029386
0x180029384  dec     ebx
0x180029386  cmp     ebx, 2
0x180029389  jnz     short loc_1800293AB
0x18002938b  mov     edx, r12d; int
0x18002938e  mov     rcx, r14; this
0x180029391  call    ?get_Chars@String@UnBCL@@QEBAAEBGH@Z; UnBCL::String::get_Chars(int)
0x180029396  lea     ecx, [rbx+5Ah]
0x180029399  cmp     [rax], cx
0x18002939c  jz      loc_1800296A0
0x1800293a2  cmp     [rax], si
0x1800293a5  jz      loc_1800296A0
0x1800293ab  mov     dword ptr [rbp+70h+var_50], 2F005Ch
0x1800293b2  mov     [rbp+70h+var_4C], r15w
0x1800293b7  mov     rax, [rdi+10h]
0x1800293bb  mov     ebx, [rax-10h]
0x1800293be  lea     rcx, [rbp+70h+var_D0]
0x1800293c2  call    ??0?$ArrayList@V?$SmartPtr@VString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::ArrayList<UnBCL::SmartPtr<UnBCL::String>>::ArrayList<UnBCL::SmartPtr<UnBCL::String>>(void)
0x1800293c7  nop
0x1800293c8  mov     rcx, rdi; struct UnBCL::String *
0x1800293cb  call    ?GetDirectoryRoot@Directory@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Directory::GetDirectoryRoot(UnBCL::String const *)
0x1800293d0  mov     rdx, rax; struct UnBCL::String *
0x1800293d3  mov     r8d, r12d
0x1800293d6  lea     rcx, [rsp+170h+var_110]; this
0x1800293db  call    ??0StringPtr@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::StringPtr::StringPtr(UnBCL::String *)
0x1800293e0  nop
0x1800293e1  mov     rax, [rsp+170h+var_108]
0x1800293e6  movsxd  rcx, dword ptr [rax+4]
0x1800293ea  mov     rcx, [rsp+rcx+170h+var_100]; struct UnBCL::String *
0x1800293ef  call    ?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z; UnBCL::Directory::Exists(UnBCL::String const *)
0x1800293f4  test    eax, eax
0x1800293f6  jz      loc_1800296F3
0x1800293fc  mov     r8d, ebx; int
0x1800293ff  xor     edx, edx; int
0x180029401  mov     rcx, rdi; this
0x180029404  call    ?Substring@String@UnBCL@@QEBAPEAV12@HH@Z; UnBCL::String::Substring(int,int)
0x180029409  mov     rdx, rax
0x18002940c  lea     rcx, [rsp+170h+var_140]
0x180029411  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180029416  nop
0x180029417  mov     rcx, [rsp+170h+var_138]; struct UnBCL::String *
0x18002941c  call    ?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z; UnBCL::Directory::Exists(UnBCL::String const *)
0x180029421  test    eax, eax
0x180029423  jnz     short loc_18002947A
0x180029425  lea     rax, [rbp+70h+var_E8]
0x180029429  mov     [rsp+170h+var_148], rax
0x18002942e  lea     rdx, [rsp+170h+var_140]
0x180029433  lea     rcx, [rbp+70h+var_E8]
0x180029437  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::SmartPtr<UnBCL::String> const &)
0x18002943c  nop
0x18002943d  mov     rdx, rax
0x180029440  lea     rcx, [rbp+70h+var_60]
0x180029444  call    ?Add@?$ArrayList@V?$SmartPtr@VString@UnBCL@@@UnBCL@@@UnBCL@@UEAAHV?$SmartPtr@VString@UnBCL@@@2@@Z; UnBCL::ArrayList<UnBCL::SmartPtr<UnBCL::String>>::Add(UnBCL::SmartPtr<UnBCL::String>)
0x180029449  dec     ebx
0x18002944b  mov     [rsp+170h+var_140], r13
0x180029450  lea     rcx, [rsp+170h+var_140]
0x180029455  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18002945a  cmp     ebx, dword ptr [rsp+170h+pExceptionObject]
0x18002945e  jle     short loc_180029489
0x180029460  mov     r9d, ebx; int
0x180029463  mov     r8d, ebx; int
0x180029466  lea     rdx, [rbp+70h+var_50]; unsigned __int16 *
0x18002946a  mov     rcx, rdi; this
0x18002946d  call    ?LastIndexOfAny@String@UnBCL@@QEBAHPEBGHH@Z; UnBCL::String::LastIndexOfAny(ushort const *,int,int)
0x180029472  mov     ebx, eax
0x180029474  test    eax, eax
0x180029476  jns     short loc_1800293FC
0x180029478  jmp     short loc_180029489
0x18002947a  mov     [rsp+170h+var_140], r13
0x18002947f  lea     rcx, [rsp+170h+var_140]
0x180029484  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x180029489  mov     ebx, r15d
0x18002948c  mov     rax, [rbp+70h+var_C0]
0x180029490  mov     edi, [rax+8]
0x180029493  sub     edi, r12d
0x180029496  js      short loc_180029501
0x180029498  mov     edx, edi
0x18002949a  lea     rcx, [rbp+70h+var_60]
0x18002949e  call    ?get_Item@?$ArrayList@V?$SmartPtr@VString@UnBCL@@@UnBCL@@@UnBCL@@UEAAAEAV?$SmartPtr@VString@UnBCL@@@2@H@Z; UnBCL::ArrayList<UnBCL::SmartPtr<UnBCL::String>>::get_Item(int)
0x1800294a3  mov     rdx, rax
0x1800294a6  lea     rcx, [rsp+170h+var_140]
0x1800294ab  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::SmartPtr<UnBCL::String> const &)
0x1800294b0  nop
0x1800294b1  mov     rsi, [rsp+170h+var_138]
0x1800294b6  xor     edx, edx; lpSecurityAttributes
0x1800294b8  mov     rcx, [rsi+10h]; lpPathName
0x1800294bc  call    cs:__imp_CreateDirectoryW
0x1800294c2  test    eax, eax
0x1800294c4  jnz     short loc_1800294E5
0x1800294c6  call    cs:__imp_GetLastError
0x1800294cc  mov     ebx, eax
0x1800294ce  cmp     eax, 0B7h
0x1800294d3  jnz     short loc_1800294E5
0x1800294d5  mov     rcx, [rsi+10h]; lpFileName
0x1800294d9  call    cs:__imp_GetFileAttributesW
0x1800294df  test    al, 10h
0x1800294e1  cmovnz  ebx, r15d
0x1800294e5  mov     [rsp+170h+var_140], r13
0x1800294ea  lea     rcx, [rsp+170h+var_140]
0x1800294ef  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x1800294f4  sub     edi, r12d
0x1800294f7  jns     short loc_180029498
0x1800294f9  test    ebx, ebx
0x1800294fb  jnz     loc_1800295AB
0x180029501  mov     [rsp+170h+var_100], r13
0x180029506  lea     rcx, [rsp+170h+var_100]
0x18002950b  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x180029510  nop
0x180029511  lea     rcx, [rbp+70h+var_A0]
0x180029515  call    ??1?$ArrayList@V?$SmartPtr@VString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::ArrayList<UnBCL::SmartPtr<UnBCL::String>>::~ArrayList<UnBCL::SmartPtr<UnBCL::String>>(void)
0x18002951a  lea     rdi, ??_7Object@UnBCL@@6B@; const UnBCL::Object::`vftable'
0x180029521  mov     [rbp+70h+var_A0], rdi
0x180029525  mov     [rsp+170h+var_120], r13
0x18002952a  lea     rcx, [rsp+170h+var_120]
0x18002952f  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x180029534  nop
0x180029535  mov     [rsp+170h+var_130], r13
0x18002953a  lea     rcx, [rsp+170h+var_130]
0x18002953f  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x180029544  mov     ecx, 10h; unsigned __int64
0x180029549  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18002954e  mov     rcx, rax
0x180029551  mov     [rsp+170h+var_148], rax
0x180029556  test    rax, rax
0x180029559  jz      short loc_180029585
0x18002955b  xorps   xmm0, xmm0
0x18002955e  movups  xmmword ptr [rax], xmm0
0x180029561  mov     [rax], rdi
0x180029564  mov     [rax+8], r15d
0x180029568  mov     eax, r12d
0x18002956b  lock xadd cs:dword_1800FFC68, eax
0x180029573  add     eax, r12d
0x180029576  mov     [rcx+0Ch], eax
0x180029579  lea     rax, ??_7DirectoryInfo@UnBCL@@6B@; const UnBCL::DirectoryInfo::`vftable'
0x180029580  mov     [rcx], rax
0x180029583  jmp     short loc_180029588
0x180029585  mov     rcx, r15
0x180029588  mov     rax, rcx
0x18002958b  mov     rcx, [rbp+70h+var_48]
0x18002958f  xor     rcx, rsp; StackCookie
0x180029592  call    __security_check_cookie
0x180029597  add     rsp, 138h
0x18002959e  pop     r15
0x1800295a0  pop     r14
0x1800295a2  pop     r13
0x1800295a4  pop     r12
0x1800295a6  pop     rdi
0x1800295a7  pop     rsi
0x1800295a8  pop     rbx
0x1800295a9  pop     rbp
0x1800295aa  retn
0x1800295ab  mov     ecx, 40h ; '@'; unsigned __int64
0x1800295b0  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1800295b5  mov     rdi, rax
0x1800295b8  mov     [rsp+170h+var_148], rax
0x1800295bd  test    rax, rax
0x1800295c0  jz      short loc_1800295DB
0x1800295c2  lea     rcx, [rsp+170h+var_130]
0x1800295c7  call    ??C?$SmartPtr@VDecoder@UnBCL@@@UnBCL@@QEBAPEAVDecoder@1@XZ; UnBCL::SmartPtr<UnBCL::Decoder>::operator->(void)
0x1800295cc  mov     r8, rax; struct UnBCL::String *
0x1800295cf  mov     edx, ebx; dwMessageId
0x1800295d1  mov     rcx, rdi; this
0x1800295d4  call    ??0Win32Exception@UnBCL@@QEAA@KPEBVString@1@@Z; UnBCL::Win32Exception::Win32Exception(ulong,UnBCL::String const *)
0x1800295d9  jmp     short loc_1800295DE
0x1800295db  mov     rax, r15
0x1800295de  lea     rdx, aClassUnbclDire; "class UnBCL::DirectoryInfo *__cdecl UnB"...
0x1800295e5  mov     rcx, rax
0x1800295e8  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x1800295ed  mov     [rsp+170h+pExceptionObject], rax
0x1800295f2  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
0x1800295f9  lea     rcx, [rsp+170h+pExceptionObject]; pExceptionObject
0x1800295fe  call    _CxxThrowException_0
0x180029604  mov     ecx, 38h ; '8'; unsigned __int64
0x180029609  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18002960e  mov     [rsp+170h+var_148], rax
0x180029613  test    rax, rax
0x180029616  jz      short loc_180029629
0x180029618  lea     rdx, aNullPathToDire; "null path to Directory::CreateDirectory"
0x18002961f  mov     rcx, rax; this
0x180029622  call    ??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentNullException::ArgumentNullException(ushort const *)
0x180029627  jmp     short loc_18002962C
0x180029629  mov     rax, r15
0x18002962c  lea     rdx, aClassUnbclDire; "class UnBCL::DirectoryInfo *__cdecl UnB"...
0x180029633  mov     rcx, rax
0x180029636  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18002963b  mov     [rsp+170h+pExceptionObject], rax
0x180029640  lea     rdx, _TI6PEAVArgumentNullException@UnBCL@@; pThrowInfo
0x180029647  lea     rcx, [rsp+170h+pExceptionObject]; pExceptionObject
0x18002964c  call    _CxxThrowException_0
0x180029652  mov     ecx, 38h ; '8'; unsigned __int64
0x180029657  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18002965c  mov     [rsp+170h+var_148], rax
0x180029661  test    rax, rax
0x180029664  jz      short loc_180029677
0x180029666  lea     rdx, aEmptyPathToDir; "empty path to Directory::CreateDirector"...
0x18002966d  mov     rcx, rax; this
0x180029670  call    ??0ArgumentException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentException::ArgumentException(ushort const *)
0x180029675  jmp     short loc_18002967A
0x180029677  mov     rax, r15
0x18002967a  lea     rdx, aClassUnbclDire; "class UnBCL::DirectoryInfo *__cdecl UnB"...
0x180029681  mov     rcx, rax
0x180029684  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x180029689  mov     [rsp+170h+pExceptionObject], rax
0x18002968e  lea     rdx, _TI5PEAVArgumentException@UnBCL@@; pThrowInfo
0x180029695  lea     rcx, [rsp+170h+pExceptionObject]; pExceptionObject
0x18002969a  call    _CxxThrowException_0
0x1800296a0  mov     ecx, 40h ; '@'; unsigned __int64
0x1800296a5  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1800296aa  mov     [rsp+170h+var_148], rax
0x1800296af  test    rax, rax
0x1800296b2  jz      short loc_1800296CA
0x1800296b4  lea     r8, aInvalidUncPath; "invalid UNC path to Directory::CreateDi"...
0x1800296bb  mov     edx, 57h ; 'W'; dwMessageId
0x1800296c0  mov     rcx, rax; this
0x1800296c3  call    ??0Win32Exception@UnBCL@@QEAA@KPEBG@Z; UnBCL::Win32Exception::Win32Exception(ulong,ushort const *)
0x1800296c8  jmp     short loc_1800296CD
0x1800296ca  mov     rax, r15
0x1800296cd  lea     rdx, aClassUnbclDire; "class UnBCL::DirectoryInfo *__cdecl UnB"...
0x1800296d4  mov     rcx, rax
0x1800296d7  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x1800296dc  mov     [rsp+170h+pExceptionObject], rax
0x1800296e1  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
0x1800296e8  lea     rcx, [rsp+170h+pExceptionObject]; pExceptionObject
0x1800296ed  call    _CxxThrowException_0
0x1800296f3  mov     ecx, 40h ; '@'; unsigned __int64
0x1800296f8  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1800296fd  mov     [rsp+170h+var_148], rax
0x180029702  test    rax, rax
0x180029705  jz      short loc_18002971D
0x180029707  lea     r8, aRootOfDirector; "root of directory to create not found"
0x18002970e  mov     edx, 3; dwMessageId
0x180029713  mov     rcx, rax; this
0x180029716  call    ??0Win32Exception@UnBCL@@QEAA@KPEBG@Z; UnBCL::Win32Exception::Win32Exception(ulong,ushort const *)
  ... truncated ...
```
