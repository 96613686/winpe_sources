# pGetDirectoriesAndFiles(UnBCL::String const *,UnBCL::String const *,UnBCL::Directory::EnumerationType,int,UnBCL::String *,UnBCL::ArrayList<UnBCL::String *> *)

- ea: `0x180031920`
- end: `0x180031dc8`
- name: `?pGetDirectoriesAndFiles@@YAXPEBVString@UnBCL@@0W4EnumerationType@Directory@2@HPEAV12@PEAV?$ArrayList@PEAVString@UnBCL@@@2@@Z`
- size: `1192`
- prototype: `void __fastcall(struct UnBCL::String *, __int64, int, int, struct UnBCL::String *, __int64)`
- caller_count: `2`
- callee_count: `19`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002c4e0`
- `0x180031920`

## callees

- `0x18000225c`
- `0x180002ca0`
- `0x180002f50`
- `0x180002f90`
- `0x180009e7c`
- `0x180011570`
- `0x180031920`
- `0x1800477d0`
- `0x180049140`
- `0x18005b6d0`
- `0x18005b790`
- `0x18005b9f0`
- `0x18005bda0`
- `0x18005be50`
- `0x18005c060`
- `0x180064340`
- `0x180068fe6`
- `0x180069020`
- `0x18006f010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180031d60`
- `KERNEL32!GetLastError` at `0x180031d60`
- `KERNEL32!FindFirstFileW` at `0x180031a3c`
- `KERNEL32!FindFirstFileW` at `0x180031a3c`
- `KERNEL32!FindNextFileW` at `0x180031d0a`
- `KERNEL32!FindNextFileW` at `0x180031d0a`
- `KERNEL32!FindClose` at `0x180031d1d`
- `KERNEL32!FindClose` at `0x180031d1d`

## string_xrefs

- `0x180031da2`: `void __cdecl pGetDirectoriesAndFiles(const class UnBCL::String *,const class UnBCL::String *,enum UnBCL::Directory::EnumerationType,int,class UnBCL::String *,class UnBCL::ArrayList<class UnBCL::String *> *)`

## pseudocode

```c
void __fastcall pGetDirectoriesAndFiles(
        struct UnBCL::String *a1,
        __int64 a2,
        int a3,
        int a4,
        struct UnBCL::String *a5,
        __int64 a6)
{
  int v10; // ebx
  int v11; // eax
  const unsigned __int16 *v12; // rcx
  struct UnBCL::String *v13; // rax
  HANDLE FirstFileW; // r14
  __int16 dwFileAttributes; // cx
  const struct UnBCL::String *v16; // rax
  struct UnBCL::String *v17; // rax
  UnBCL::String *v18; // rax
  __int64 *v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rdx
  const struct UnBCL::String *v22; // rax
  struct UnBCL::String *v23; // rax
  const struct UnBCL::String *v24; // rax
  struct UnBCL::String *v25; // rax
  UnBCL::String *v26; // rax
  void ***v27; // rcx
  const struct UnBCL::String *v28; // rax
  struct UnBCL::String *v29; // rax
  UnBCL::String *v30; // rax
  __int64 *v31; // rcx
  __int64 v32; // rax
  __int64 v33; // rdx
  DWORD LastError; // edi
  UnBCL::Win32Exception *v35; // rbx
  __int64 v36; // rax
  const struct UnBCL::String *v37; // rax
  void **v38; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v39; // [rsp+40h] [rbp-C0h]
  __int64 pExceptionObject; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v41[2]; // [rsp+50h] [rbp-B0h] BYREF
  void **v42; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v43; // [rsp+68h] [rbp-98h]
  struct UnBCL::String *v44; // [rsp+70h] [rbp-90h]
  UnBCL::String *v45; // [rsp+78h] [rbp-88h]
  _QWORD v46[2]; // [rsp+80h] [rbp-80h] BYREF
  void **v47; // [rsp+90h] [rbp-70h] BYREF
  UnBCL::String *v48; // [rsp+98h] [rbp-68h]
  _BYTE v49[16]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v50; // [rsp+B0h] [rbp-50h]
  __int64 v51; // [rsp+B8h] [rbp-48h]
  UnBCL::String *v52; // [rsp+C0h] [rbp-40h]
  UnBCL::String *v53; // [rsp+C8h] [rbp-38h]
  _BYTE v54[24]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v55[24]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v56[24]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v57[24]; // [rsp+118h] [rbp+18h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+130h] [rbp+30h] BYREF

  v51 = -2;
  pExceptionObject = a2;
  v44 = a1;
  v10 = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  UnBCL::String::String((UnBCL::String *)v49, 0x5Cu, 1);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v41, 0);
  v11 = UnBCL::String::EndsWith(a1, v50, 1);
  v12 = (const unsigned __int16 *)*((_QWORD *)a1 + 2);
  if ( v11 )
    v13 = UnBCL::String::Concat(v12, *(const unsigned __int16 **)(a2 + 16));
  else
    v13 = UnBCL::String::Concat(v12, v50, *(const unsigned __int16 **)(a2 + 16));
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v38, v13);
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(v41, v39);
  v38 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v38);
  FirstFileW = FindFirstFileW(*(LPCWSTR *)(v41[1] + 16LL), &FindFileData);
  if ( FirstFileW != (HANDLE)-1LL )
  {
    while ( 1 )
    {
      dwFileAttributes = FindFileData.dwFileAttributes;
      if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
        break;
      if ( (a3 & 0xFFFFFFFD) == 0 )
      {
        if ( a5 )
        {
          v28 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v57, FindFileData.cFileName);
          v10 |= 4u;
          v29 = UnBCL::Path::Combine(a5, v28);
        }
        else
        {
          v30 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
          v45 = v30;
          if ( v30 )
            v29 = (struct UnBCL::String *)UnBCL::String::String(v30, FindFileData.cFileName);
          else
            v29 = 0;
        }
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v38, v29);
        if ( (v10 & 4) != 0 )
        {
          v10 &= ~4u;
          UnBCL::String::~String((UnBCL::String *)v57);
        }
        v31 = (__int64 *)(a6 + *(int *)(*(_QWORD *)(a6 + 8) + 16LL) + 8LL);
        v32 = *v31;
        v33 = v39;
        if ( v39 )
        {
          _InterlockedDecrement((volatile signed __int32 *)(v39 + 8));
          v39 = 0;
        }
        else
        {
          v33 = 0;
        }
        (*(void (__fastcall **)(__int64 *, __int64, _QWORD))(v32 + 40))(v31, v33, 0);
        v38 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
        v27 = &v38;
LABEL_44:
        UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(v27);
      }
LABEL_45:
      if ( !FindNextFileW(FirstFileW, &FindFileData) )
      {
        FindClose(FirstFileW);
        goto LABEL_47;
      }
    }
    if ( FindFileData.cFileName[0] == 46
      && (!FindFileData.cFileName[1] || FindFileData.cFileName[1] == 46 && !FindFileData.cFileName[2]) )
    {
      goto LABEL_45;
    }
    if ( (unsigned int)(a3 - 1) <= 1 )
    {
      if ( a5 )
      {
        v16 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v54, FindFileData.cFileName);
        v10 |= 1u;
        v17 = UnBCL::Path::Combine(a5, v16);
      }
      else
      {
        v18 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
        v52 = v18;
        if ( v18 )
          v17 = (struct UnBCL::String *)UnBCL::String::String(v18, FindFileData.cFileName);
        else
          v17 = 0;
      }
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v42, v17);
      if ( (v10 & 1) != 0 )
      {
        v10 &= ~1u;
        UnBCL::String::~String((UnBCL::String *)v54);
      }
      v19 = (__int64 *)(a6 + *(int *)(*(_QWORD *)(a6 + 8) + 16LL) + 8LL);
      v20 = *v19;
      v21 = v43;
      if ( v43 )
      {
        _InterlockedDecrement((volatile signed __int32 *)(v43 + 8));
        v43 = 0;
      }
      else
      {
        v21 = 0;
      }
      (*(void (__fastcall **)(__int64 *, __int64, _QWORD))(v20 + 40))(v19, v21, 0);
      v42 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
      UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v42);
      dwFileAttributes = FindFileData.dwFileAttributes;
    }
    if ( !a4 || (dwFileAttributes & 0x400) != 0 )
      goto LABEL_45;
    v22 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v55, FindFileData.cFileName);
    v23 = UnBCL::Path::Combine(v44, v22);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v47, v23);
    UnBCL::String::~String((UnBCL::String *)v55);
    if ( a5 )
    {
      v24 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v56, FindFileData.cFileName);
      v10 |= 2u;
      v25 = UnBCL::Path::Combine(a5, v24);
    }
    else
    {
      v26 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
      v53 = v26;
      if ( v26 )
        v25 = (struct UnBCL::String *)UnBCL::String::String(v26, FindFileData.cFileName);
      else
        v25 = 0;
    }
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v46, v25);
    if ( (v10 & 2) != 0 )
    {
      v10 &= ~2u;
      UnBCL::String::~String((UnBCL::String *)v56);
    }
    pGetDirectoriesAndFiles((_DWORD)v48, pExceptionObject, a3, a4, (struct UnBCL::String *)v46[1], a6);
    v46[0] = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
    UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(v46);
    v47 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
    v27 = &v47;
    goto LABEL_44;
  }
  LastError = GetLastError();
  if ( LastError - 2 > 1 )
  {
    v35 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
    v45 = v35;
    v36 = 0;
    if ( v35 )
    {
      v37 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::Decoder>::operator->(v41);
      v36 = UnBCL::Win32Exception::Win32Exception(v35, LastError, v37);
    }
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v36,
                         "void __cdecl pGetDirectoriesAndFiles(const class UnBCL::String *,const class UnBCL::String *,en"
                         "um UnBCL::Directory::EnumerationType,int,class UnBCL::String *,class UnBCL::ArrayList<class UnB"
                         "CL::String *> *)");
    throw (UnBCL::Win32Exception **)&pExceptionObject;
  }
LABEL_47:
  v41[0] = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(v41);
  UnBCL::String::~String((UnBCL::String *)v49);
}

```

## disassembly

```asm
0x180031920  push    rbp
0x180031922  push    rbx
0x180031923  push    rsi
0x180031924  push    rdi
0x180031925  push    r12
0x180031927  push    r13
0x180031929  push    r14
0x18003192b  push    r15
0x18003192d  lea     rbp, [rsp-298h]
0x180031935  sub     rsp, 398h
0x18003193c  mov     [rbp+2D0h+var_318], 0FFFFFFFFFFFFFFFEh
0x180031944  mov     rax, cs:__security_cookie
0x18003194b  xor     rax, rsp
0x18003194e  mov     [rbp+2D0h+var_50], rax
0x180031955  mov     r12d, r9d
0x180031958  mov     r13d, r8d
0x18003195b  mov     r14, rdx
0x18003195e  mov     [rsp+3D0h+pExceptionObject], rdx
0x180031963  mov     rsi, rcx
0x180031966  mov     [rsp+3D0h+var_360], rcx
0x18003196b  mov     rdi, [rbp+2D0h+arg_20]
0x180031972  mov     r15, [rbp+2D0h+arg_28]
0x180031979  xor     ebx, ebx
0x18003197b  mov     [rsp+3D0h+var_3A0], ebx
0x18003197f  xor     edx, edx; Val
0x180031981  mov     r8d, 250h; Size
0x180031987  lea     rcx, [rbp+2D0h+FindFileData]; void *
0x18003198b  call    memset_0
0x180031990  lea     edx, [rbx+5Ch]; unsigned __int16
0x180031993  lea     r8d, [rbx+1]; int
0x180031997  lea     rcx, [rbp+2D0h+var_330]; this
0x18003199b  call    ??0String@UnBCL@@QEAA@GH@Z; UnBCL::String::String(ushort,int)
0x1800319a0  nop
0x1800319a1  xor     edx, edx
0x1800319a3  lea     rcx, [rsp+3D0h+var_380]
0x1800319a8  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1800319ad  nop
0x1800319ae  lea     r8d, [rbx+1]; int
0x1800319b2  mov     rdx, [rbp+2D0h+var_320]; unsigned __int16 *
0x1800319b6  mov     rcx, rsi; this
0x1800319b9  call    ?EndsWith@String@UnBCL@@QEBAHPEBGH@Z; UnBCL::String::EndsWith(ushort const *,int)
0x1800319be  mov     r8, [r14+10h]; unsigned __int16 *
0x1800319c2  mov     rcx, [rsi+10h]; unsigned __int16 *
0x1800319c6  test    eax, eax
0x1800319c8  jz      short loc_1800319F2
0x1800319ca  mov     rdx, r8; unsigned __int16 *
0x1800319cd  call    ?Concat@String@UnBCL@@SAPEAV12@PEBG0@Z; UnBCL::String::Concat(ushort const *,ushort const *)
0x1800319d2  mov     rdx, rax
0x1800319d5  lea     rcx, [rsp+3D0h+var_398]
0x1800319da  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1800319df  nop
0x1800319e0  mov     rdx, [rsp+3D0h+var_390]
0x1800319e5  lea     rcx, [rsp+3D0h+var_380]
0x1800319ea  call    ?Assign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXPEAVXmlNamespaceManager@2@@Z; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(UnBCL::XmlNamespaceManager *)
0x1800319ef  nop
0x1800319f0  jmp     short loc_180031A19
0x1800319f2  mov     rdx, [rbp+2D0h+var_320]; unsigned __int16 *
0x1800319f6  call    ?Concat@String@UnBCL@@SAPEAV12@PEBG00@Z; UnBCL::String::Concat(ushort const *,ushort const *,ushort const *)
0x1800319fb  mov     rdx, rax
0x1800319fe  lea     rcx, [rsp+3D0h+var_398]
0x180031a03  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180031a08  nop
0x180031a09  mov     rdx, [rsp+3D0h+var_390]
0x180031a0e  lea     rcx, [rsp+3D0h+var_380]
0x180031a13  call    ?Assign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXPEAVXmlNamespaceManager@2@@Z; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(UnBCL::XmlNamespaceManager *)
0x180031a18  nop
0x180031a19  lea     rsi, ??_7?$SmartPtr@VString@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::String>::`vftable'
0x180031a20  mov     [rsp+3D0h+var_398], rsi
0x180031a25  lea     rcx, [rsp+3D0h+var_398]
0x180031a2a  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x180031a2f  lea     rdx, [rbp+2D0h+FindFileData]; lpFindFileData
0x180031a33  mov     rcx, [rsp+3D0h+var_378]
0x180031a38  mov     rcx, [rcx+10h]; lpFileName
0x180031a3c  call    cs:__imp_FindFirstFileW
0x180031a42  mov     r14, rax
0x180031a45  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180031a49  jz      loc_180031D60
0x180031a4f  xor     edx, edx
0x180031a51  mov     ecx, [rbp+2D0h+FindFileData.dwFileAttributes]
0x180031a54  test    cl, 10h
0x180031a57  jz      loc_180031C3F
0x180031a5d  movzx   eax, [rbp+2D0h+FindFileData.cFileName+2]
0x180031a61  cmp     [rbp+2D0h+FindFileData.cFileName], 2Eh ; '.'
0x180031a66  jnz     short loc_180031A88
0x180031a68  test    ax, ax
0x180031a6b  jz      loc_180031D03
0x180031a71  cmp     [rbp+2D0h+FindFileData.cFileName], 2Eh ; '.'
0x180031a76  jnz     short loc_180031A88
0x180031a78  cmp     ax, 2Eh ; '.'
0x180031a7c  jnz     short loc_180031A88
0x180031a7e  cmp     [rbp+2D0h+FindFileData.cFileName+4], dx
0x180031a82  jz      loc_180031D03
0x180031a88  lea     eax, [r13-1]
0x180031a8c  cmp     eax, 1
0x180031a8f  ja      loc_180031B4E
0x180031a95  test    rdi, rdi
0x180031a98  jz      short loc_180031ABC
0x180031a9a  lea     rdx, [rbp+2D0h+FindFileData.cFileName]; unsigned __int16 *
0x180031a9e  lea     rcx, [rbp+2D0h+var_300]; this
0x180031aa2  call    ??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180031aa7  nop
0x180031aa8  or      ebx, 1
0x180031aab  mov     [rsp+3D0h+var_3A0], ebx
0x180031aaf  mov     rdx, rax; struct UnBCL::String *
0x180031ab2  mov     rcx, rdi; struct UnBCL::String *
0x180031ab5  call    ?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x180031aba  jmp     short loc_180031AE2
0x180031abc  mov     ecx, 18h; unsigned __int64
0x180031ac1  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180031ac6  mov     [rbp+2D0h+var_310], rax
0x180031aca  xor     ecx, ecx
0x180031acc  test    rax, rax
0x180031acf  jz      short loc_180031ADF
0x180031ad1  lea     rdx, [rbp+2D0h+FindFileData.cFileName]; unsigned __int16 *
0x180031ad5  mov     rcx, rax; this
0x180031ad8  call    ??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180031add  jmp     short loc_180031AE2
0x180031adf  mov     rax, rcx
0x180031ae2  mov     rdx, rax
0x180031ae5  lea     rcx, [rsp+3D0h+var_370]
0x180031aea  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180031aef  nop
0x180031af0  test    bl, 1
0x180031af3  jz      short loc_180031B05
0x180031af5  and     ebx, 0FFFFFFFEh
0x180031af8  mov     [rsp+3D0h+var_3A0], ebx
0x180031afc  lea     rcx, [rbp+2D0h+var_300]; this
0x180031b00  call    ??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180031b05  mov     rax, [r15+8]
0x180031b09  movsxd  rcx, dword ptr [rax+10h]
0x180031b0d  add     rcx, 8
0x180031b11  add     rcx, r15
0x180031b14  mov     rax, [rcx]
0x180031b17  mov     rdx, [rsp+3D0h+var_368]
0x180031b1c  xor     r8d, r8d
0x180031b1f  test    rdx, rdx
0x180031b22  jnz     short loc_180031B29
0x180031b24  mov     edx, r8d
0x180031b27  jmp     short loc_180031B32
0x180031b29  lock dec dword ptr [rdx+8]
0x180031b2d  mov     [rsp+3D0h+var_368], r8
0x180031b32  mov     rax, [rax+28h]
0x180031b36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031b3b  nop
0x180031b3c  mov     [rsp+3D0h+var_370], rsi
0x180031b41  lea     rcx, [rsp+3D0h+var_370]
0x180031b46  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x180031b4b  mov     ecx, [rbp+2D0h+FindFileData.dwFileAttributes]
0x180031b4e  test    r12d, r12d
0x180031b51  jz      loc_180031D03
0x180031b57  bt      ecx, 0Ah
0x180031b5b  jb      loc_180031D03
0x180031b61  lea     rdx, [rbp+2D0h+FindFileData.cFileName]; unsigned __int16 *
0x180031b65  lea     rcx, [rbp+2D0h+var_2E8]; this
0x180031b69  call    ??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180031b6e  nop
0x180031b6f  mov     rdx, rax; struct UnBCL::String *
0x180031b72  mov     rcx, [rsp+3D0h+var_360]; struct UnBCL::String *
0x180031b77  call    ?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x180031b7c  mov     rdx, rax
0x180031b7f  lea     rcx, [rbp+2D0h+var_340]
0x180031b83  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180031b88  nop
0x180031b89  lea     rcx, [rbp+2D0h+var_2E8]; this
0x180031b8d  call    ??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180031b92  test    rdi, rdi
0x180031b95  jz      short loc_180031BB9
0x180031b97  lea     rdx, [rbp+2D0h+FindFileData.cFileName]; unsigned __int16 *
0x180031b9b  lea     rcx, [rbp+2D0h+var_2D0]; this
0x180031b9f  call    ??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180031ba4  nop
0x180031ba5  or      ebx, 2
0x180031ba8  mov     [rsp+3D0h+var_3A0], ebx
0x180031bac  mov     rdx, rax; struct UnBCL::String *
0x180031baf  mov     rcx, rdi; struct UnBCL::String *
0x180031bb2  call    ?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x180031bb7  jmp     short loc_180031BDF
0x180031bb9  mov     ecx, 18h; unsigned __int64
0x180031bbe  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180031bc3  mov     [rbp+2D0h+var_308], rax
0x180031bc7  xor     ecx, ecx
0x180031bc9  test    rax, rax
0x180031bcc  jz      short loc_180031BDC
0x180031bce  lea     rdx, [rbp+2D0h+FindFileData.cFileName]; unsigned __int16 *
0x180031bd2  mov     rcx, rax; this
0x180031bd5  call    ??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180031bda  jmp     short loc_180031BDF
0x180031bdc  mov     rax, rcx
0x180031bdf  mov     rdx, rax
0x180031be2  lea     rcx, [rbp+2D0h+var_350]
0x180031be6  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180031beb  nop
0x180031bec  test    bl, 2
0x180031bef  jz      short loc_180031C01
0x180031bf1  and     ebx, 0FFFFFFFDh
0x180031bf4  mov     [rsp+3D0h+var_3A0], ebx
0x180031bf8  lea     rcx, [rbp+2D0h+var_2D0]; this
0x180031bfc  call    ??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180031c01  mov     [rsp+3D0h+var_3A8], r15
0x180031c06  mov     rax, [rbp+2D0h+var_348]
0x180031c0a  mov     [rsp+3D0h+var_3B0], rax
0x180031c0f  mov     r9d, r12d
0x180031c12  mov     r8d, r13d
0x180031c15  mov     rdx, [rsp+3D0h+pExceptionObject]
0x180031c1a  mov     rcx, [rbp+2D0h+var_338]
0x180031c1e  call    ?pGetDirectoriesAndFiles@@YAXPEBVString@UnBCL@@0W4EnumerationType@Directory@2@HPEAV12@PEAV?$ArrayList@PEAVString@UnBCL@@@2@@Z; pGetDirectoriesAndFiles(UnBCL::String const *,UnBCL::String const *,UnBCL::Directory::EnumerationType,int,UnBCL::String *,UnBCL::ArrayList<UnBCL::String *> *)
0x180031c23  nop
0x180031c24  mov     [rbp+2D0h+var_350], rsi
0x180031c28  lea     rcx, [rbp+2D0h+var_350]
0x180031c2c  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x180031c31  nop
0x180031c32  mov     [rbp+2D0h+var_340], rsi
0x180031c36  lea     rcx, [rbp+2D0h+var_340]
0x180031c3a  jmp     loc_180031CFE
0x180031c3f  test    r13d, 0FFFFFFFDh
0x180031c46  jnz     loc_180031D03
0x180031c4c  test    rdi, rdi
0x180031c4f  jz      short loc_180031C73
0x180031c51  lea     rdx, [rbp+2D0h+FindFileData.cFileName]; unsigned __int16 *
0x180031c55  lea     rcx, [rbp+2D0h+var_2B8]; this
0x180031c59  call    ??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180031c5e  nop
0x180031c5f  or      ebx, 4
0x180031c62  mov     [rsp+3D0h+var_3A0], ebx
0x180031c66  mov     rdx, rax; struct UnBCL::String *
0x180031c69  mov     rcx, rdi; struct UnBCL::String *
0x180031c6c  call    ?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x180031c71  jmp     short loc_180031C9A
0x180031c73  mov     ecx, 18h; unsigned __int64
0x180031c78  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180031c7d  mov     [rsp+3D0h+var_358], rax
0x180031c82  xor     ecx, ecx
0x180031c84  test    rax, rax
0x180031c87  jz      short loc_180031C97
0x180031c89  lea     rdx, [rbp+2D0h+FindFileData.cFileName]; unsigned __int16 *
0x180031c8d  mov     rcx, rax; this
0x180031c90  call    ??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180031c95  jmp     short loc_180031C9A
0x180031c97  mov     rax, rcx
0x180031c9a  mov     rdx, rax
0x180031c9d  lea     rcx, [rsp+3D0h+var_398]
0x180031ca2  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180031ca7  nop
0x180031ca8  test    bl, 4
0x180031cab  jz      short loc_180031CBD
0x180031cad  and     ebx, 0FFFFFFFBh
0x180031cb0  mov     [rsp+3D0h+var_3A0], ebx
0x180031cb4  lea     rcx, [rbp+2D0h+var_2B8]; this
0x180031cb8  call    ??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180031cbd  mov     rax, [r15+8]
0x180031cc1  movsxd  rcx, dword ptr [rax+10h]
0x180031cc5  add     rcx, 8
0x180031cc9  add     rcx, r15
0x180031ccc  mov     rax, [rcx]
0x180031ccf  mov     rdx, [rsp+3D0h+var_390]
0x180031cd4  xor     r8d, r8d
0x180031cd7  test    rdx, rdx
0x180031cda  jnz     short loc_180031CE1
0x180031cdc  mov     edx, r8d
0x180031cdf  jmp     short loc_180031CEA
0x180031ce1  lock dec dword ptr [rdx+8]
0x180031ce5  mov     [rsp+3D0h+var_390], r8
0x180031cea  mov     rax, [rax+28h]
0x180031cee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031cf3  nop
0x180031cf4  mov     [rsp+3D0h+var_398], rsi
0x180031cf9  lea     rcx, [rsp+3D0h+var_398]
0x180031cfe  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x180031d03  lea     rdx, [rbp+2D0h+FindFileData]; lpFindFileData
0x180031d07  mov     rcx, r14; hFindFile
0x180031d0a  call    cs:__imp_FindNextFileW
0x180031d10  xor     edx, edx
0x180031d12  test    eax, eax
0x180031d14  jnz     loc_180031A51
0x180031d1a  mov     rcx, r14; hFindFile
0x180031d1d  call    cs:__imp_FindClose
0x180031d23  nop
0x180031d24  mov     [rsp+3D0h+var_380], rsi
0x180031d29  lea     rcx, [rsp+3D0h+var_380]
0x180031d2e  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x180031d33  nop
0x180031d34  lea     rcx, [rbp+2D0h+var_330]; this
0x180031d38  call    ??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180031d3d  mov     rcx, [rbp+2D0h+var_50]
0x180031d44  xor     rcx, rsp; StackCookie
0x180031d47  call    __security_check_cookie
0x180031d4c  add     rsp, 398h
0x180031d53  pop     r15
0x180031d55  pop     r14
0x180031d57  pop     r13
0x180031d59  pop     r12
0x180031d5b  pop     rdi
0x180031d5c  pop     rsi
0x180031d5d  pop     rbx
0x180031d5e  pop     rbp
0x180031d5f  retn
0x180031d60  call    cs:__imp_GetLastError
0x180031d66  nop
0x180031d67  mov     edi, eax
0x180031d69  lea     ecx, [rax-2]
  ... truncated ...
```
