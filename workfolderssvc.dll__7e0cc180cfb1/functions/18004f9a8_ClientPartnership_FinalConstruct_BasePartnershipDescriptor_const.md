# ClientPartnership::FinalConstruct(BasePartnershipDescriptor const &)

- ea: `0x18004f9a8`
- end: `0x18004fda8`
- name: `?FinalConstruct@ClientPartnership@@QEAAJAEBVBasePartnershipDescriptor@@@Z`
- size: `1024`
- prototype: `__int64 __fastcall(ClientPartnership *__hidden this, const struct BasePartnershipDescriptor *)`
- caller_count: `4`
- callee_count: `16`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x18003f3c8`
- `0x180041dc4`
- `0x18004b894`
- `0x180051380`

## callees

- `0x180002ab0`
- `0x1800035f8`
- `0x180003604`
- `0x180007b9c`
- `0x180007e10`
- `0x180009158`
- `0x18000a694`
- `0x180010ee0`
- `0x1800110fc`
- `0x180011314`
- `0x1800158d4`
- `0x180015904`
- `0x18004f9a8`
- `0x180060bc4`
- `0x1800bab54`
- `0x18013e010`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchAppendEx` at `0x18004fc2d`
- `api-ms-win-core-path-l1-1-0!PathCchAppendEx` at `0x18004fc2d`
- `USERENV!GetUserProfileDirectoryW` at `0x18004fbd7`
- `USERENV!GetUserProfileDirectoryW` at `0x18004fbd7`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ClientPartnership::FinalConstruct(
        ClientPartnership *this,
        const struct BasePartnershipDescriptor *a2)
{
  _BYTE *v4; // rax
  char v5; // al
  char v6; // r8
  struct IUnknown *v7; // rdx
  struct IUnknown *v8; // rdx
  HRESULT v9; // eax
  const unsigned __int16 *v10; // rax
  int v11; // eax
  int v12; // eax
  unsigned int v13; // ebx
  int v15; // [rsp+30h] [rbp-2B8h] BYREF
  int v16; // [rsp+34h] [rbp-2B4h]
  char v17; // [rsp+38h] [rbp-2B0h]
  const char *v18; // [rsp+40h] [rbp-2A8h]
  __int64 v19; // [rsp+48h] [rbp-2A0h]
  DWORD cchSize; // [rsp+50h] [rbp-298h] BYREF
  int pExceptionObject; // [rsp+54h] [rbp-294h] BYREF
  HRESULT v22; // [rsp+58h] [rbp-290h] BYREF
  int v23; // [rsp+5Ch] [rbp-28Ch] BYREF
  int v24; // [rsp+60h] [rbp-288h] BYREF
  HANDLE hToken; // [rsp+68h] [rbp-280h] BYREF
  struct ICloudFileDataStorageConfiguration *v26; // [rsp+70h] [rbp-278h] BYREF
  int v27; // [rsp+78h] [rbp-270h] BYREF
  __int64 CurrentToken; // [rsp+80h] [rbp-268h] BYREF
  __int64 v29; // [rsp+88h] [rbp-260h] BYREF
  const ATL::CAtlException *v30; // [rsp+90h] [rbp-258h] BYREF
  WCHAR ProfileDir; // [rsp+A0h] [rbp-248h] BYREF
  _BYTE v32[526]; // [rsp+A2h] [rbp-246h] BYREF

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) == 0 )
    {
LABEL_8:
      v5 = 0;
      goto LABEL_9;
    }
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 10, WPP_ed11ef14c19031b8d1eb458ef59662df_Traceguids);
      v4 = WPP_GLOBAL_Control;
    }
  }
  if ( (v4[68] & 8) == 0 || v4[65] < 6u )
    goto LABEL_8;
  v5 = 1;
LABEL_9:
  v15 = 0;
  v16 = 21;
  v17 = v5;
  v18 = "ClientPartnership::FinalConstruct";
  v19 = 0;
  try
  {
    std::wstring::operator=((char *)this + 88, (char *)a2 + 8);
    std::wstring::operator=((char *)this + 8, (char *)a2 + 72);
    std::wstring::operator=((char *)this + 56, (char *)a2 + 40);
    std::wstring::operator=((char *)this + 120, (char *)a2 + 136);
    *((_BYTE *)this + 288) = *((_BYTE *)a2 + 380);
    *((_DWORD *)this + 73) = *((_DWORD *)a2 + 96);
    std::wstring::operator=((char *)this + 152, (char *)a2 + 168);
    *(_OWORD *)((char *)this + 40) = *(_OWORD *)((char *)a2 + 328);
    std::wstring::operator=((char *)this + 184, (char *)a2 + 200);
    std::wstring::operator=((char *)this + 216, (char *)a2 + 264);
    std::wstring::operator=((char *)this + 248, (char *)a2 + 296);
    *((_QWORD *)this + 35) = *((_QWORD *)a2 + 43);
    v7 = (struct IUnknown *)*((_QWORD *)a2 + 46);
    if ( *((struct IUnknown **)this + 37) != v7 )
      ATL::AtlComPtrAssign((struct IUnknown **)this + 37, v7);
    v8 = (struct IUnknown *)*((_QWORD *)a2 + 44);
    if ( *((struct IUnknown **)this + 38) != v8 )
      ATL::AtlComPtrAssign((struct IUnknown **)this + 38, v8);
    if ( *((_QWORD *)this + 29) )
    {
      *((_QWORD *)this + 40) = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 216);
      *((_QWORD *)this + 39) = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 248);
    }
    else
    {
      CurrentToken = CTokenHelper::GetCurrentToken(8u, (__int64)v8, v6);
      hToken = 0;
      EcsUniqueHandle<void *,Win32HandleDeleter,0>::reset(&hToken, &CurrentToken);
      ProfileDir = 0;
      memset_0(v32, 0, 0x206u);
      cchSize = 260;
      if ( !GetUserProfileDirectoryW(hToken, &ProfileDir, &cchSize) )
      {
        HIWORD(v16) = 55;
        pExceptionObject = EcsGetLastFailureAsHRESULT();
        throw (long *)&pExceptionObject;
      }
      LOWORD(v16) = 55;
      v9 = PathCchAppendEx(&ProfileDir, 0x104u, L"AppData\\Local\\Microsoft\\Windows\\WorkFolders\\Metadata", 1u);
      v15 = v9;
      if ( v9 < 0 )
      {
        HIWORD(v16) = 59;
        v22 = v9;
        throw (long *)&v22;
      }
      LOWORD(v16) = 59;
      std::wstring::operator=((char *)this + 88, &ProfileDir);
      v29 = 0;
      EcsUniqueHandle<void *,Win32HandleDeleter,0>::reset(&hToken, &v29);
      *((_QWORD *)this + 40) = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 88);
      *((_QWORD *)this + 39) = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 56);
      v26 = 0;
      v10 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 56);
      v11 = CCloudFileDataStorageConfiguration::CreateInstance(
              v10,
              *((_QWORD *)this + 35),
              *((_DWORD *)this + 73),
              *((struct IFileDownloadManager **)this + 37),
              &v26);
      v15 = v11;
      if ( v11 < 0 )
      {
        HIWORD(v16) = 76;
        v23 = v11;
        throw (long *)&v23;
      }
      LOWORD(v16) = 76;
      v12 = (**(__int64 (__fastcall ***)(struct ICloudFileDataStorageConfiguration *, GUID *, char *))v26)(
              v26,
              &GUID_286cc90b_2281_479b_b861_97df1fd3f1e5,
              (char *)this + 304);
      v15 = v12;
      if ( v12 < 0 )
      {
        HIWORD(v16) = 78;
        v24 = v12;
        throw (long *)&v24;
      }
      LOWORD(v16) = 78;
      ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(&v26);
    }
  }
  catch ( long v27 )
  {
    v15 = v27;
  }
  catch ( std::bad_alloc )
  {
    HIWORD(v16) = 81;
    v15 = -2147024882;
  }
  catch ( std::exception )
  {
    HIWORD(v16) = 81;
    v15 = -2147418113;
  }
  catch ( const ATL::CAtlException *v30 )
  {
    HIWORD(v16) = 81;
    v15 = *(_DWORD *)v30;
  }
  v13 = v15;
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v15);
  return v13;
}

```

## disassembly

```asm
0x18004f9a8  mov     [rsp+arg_10], rbx
0x18004f9ad  mov     [rsp+arg_18], rsi
0x18004f9b2  push    rdi
0x18004f9b3  push    r12
0x18004f9b5  push    r13
0x18004f9b7  push    r14
0x18004f9b9  push    r15
0x18004f9bb  sub     rsp, 2C0h
0x18004f9c2  mov     rax, cs:__security_cookie
0x18004f9c9  xor     rax, rsp
0x18004f9cc  mov     [rsp+2E8h+var_38], rax
0x18004f9d4  mov     rsi, rdx
0x18004f9d7  mov     rdi, rcx
0x18004f9da  lea     rcx, WPP_GLOBAL_Control
0x18004f9e1  mov     rax, cs:WPP_GLOBAL_Control
0x18004f9e8  cmp     rax, rcx
0x18004f9eb  jz      short loc_18004FA15
0x18004f9ed  test    byte ptr [rax+44h], 8
0x18004f9f1  jz      short loc_18004FA27
0x18004f9f3  cmp     byte ptr [rax+41h], 6
0x18004f9f7  jb      short loc_18004FA15
0x18004f9f9  mov     edx, 0Ah
0x18004f9fe  lea     r8, WPP_ed11ef14c19031b8d1eb458ef59662df_Traceguids
0x18004fa05  mov     rcx, [rax+38h]
0x18004fa09  call    WPP_SF_
0x18004fa0e  mov     rax, cs:WPP_GLOBAL_Control
0x18004fa15  test    byte ptr [rax+44h], 8
0x18004fa19  jz      short loc_18004FA27
0x18004fa1b  cmp     byte ptr [rax+41h], 6
0x18004fa1f  jb      short loc_18004FA27
0x18004fa21  mov     al, 1
0x18004fa23  xor     ebx, ebx
0x18004fa25  jmp     short loc_18004FA2B
0x18004fa27  xor     ebx, ebx
0x18004fa29  mov     al, bl
0x18004fa2b  mov     [rsp+2E8h+var_2B8], ebx
0x18004fa2f  mov     [rsp+2E8h+var_2B4], 15h
0x18004fa37  mov     [rsp+2E8h+var_2B0], al
0x18004fa3b  lea     rax, aClientpartners_6; "ClientPartnership::FinalConstruct"
0x18004fa42  mov     [rsp+2E8h+var_2A8], rax
0x18004fa47  mov     [rsp+2E8h+var_2A0], rbx
0x18004fa4c  lea     rcx, [rdi+58h]
0x18004fa50  lea     rdx, [rsi+8]
0x18004fa54  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18004fa59  lea     rdx, [rsi+48h]
0x18004fa5d  lea     rcx, [rdi+8]
0x18004fa61  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18004fa66  lea     r12, [rdi+38h]
0x18004fa6a  lea     rdx, [rsi+28h]
0x18004fa6e  mov     rcx, r12
0x18004fa71  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18004fa76  lea     rdx, [rsi+88h]
0x18004fa7d  lea     rcx, [rdi+78h]
0x18004fa81  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18004fa86  mov     al, [rsi+17Ch]
0x18004fa8c  mov     [rdi+120h], al
0x18004fa92  mov     eax, [rsi+180h]
0x18004fa98  mov     [rdi+124h], eax
0x18004fa9e  lea     rdx, [rsi+0A8h]
0x18004faa5  lea     rcx, [rdi+98h]
0x18004faac  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18004fab1  movups  xmm0, xmmword ptr [rsi+148h]
0x18004fab8  movdqu  xmmword ptr [rdi+28h], xmm0
0x18004fabd  lea     rdx, [rsi+0C8h]
0x18004fac4  lea     rcx, [rdi+0B8h]
0x18004facb  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18004fad0  lea     r13, [rdi+0D8h]
0x18004fad7  lea     rdx, [rsi+108h]
0x18004fade  mov     rcx, r13
0x18004fae1  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18004fae6  lea     rcx, [rdi+0F8h]
0x18004faed  lea     rdx, [rsi+128h]
0x18004faf4  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18004faf9  mov     rax, [rsi+158h]
0x18004fb00  mov     [rdi+118h], rax
0x18004fb07  lea     r15, [rdi+128h]
0x18004fb0e  mov     rdx, [rsi+170h]; struct IUnknown *
0x18004fb15  cmp     [r15], rdx
0x18004fb18  jz      short loc_18004FB22
0x18004fb1a  mov     rcx, r15; struct IUnknown **
0x18004fb1d  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18004fb22  lea     r14, [rdi+130h]
0x18004fb29  mov     rdx, [rsi+160h]; struct IUnknown *
0x18004fb30  cmp     [r14], rdx
0x18004fb33  jz      short loc_18004FB3D
0x18004fb35  mov     rcx, r14; struct IUnknown **
0x18004fb38  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18004fb3d  cmp     [rdi+0E8h], rbx
0x18004fb44  jz      short loc_18004FB6D
0x18004fb46  mov     rcx, r13
0x18004fb49  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004fb4e  mov     [rdi+140h], rax
0x18004fb55  lea     rcx, [rdi+0F8h]
0x18004fb5c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004fb61  mov     [rdi+138h], rax
0x18004fb68  jmp     loc_18004FD63
0x18004fb6d  mov     ecx, 8; DesiredAccess
0x18004fb72  call    ?GetCurrentToken@CTokenHelper@@SAPEAXK_N0@Z; CTokenHelper::GetCurrentToken(ulong,bool,bool)
0x18004fb77  mov     [rsp+2E8h+var_268], rax
0x18004fb7f  mov     [rsp+2E8h+hToken], rbx
0x18004fb84  lea     rdx, [rsp+2E8h+var_268]
0x18004fb8c  lea     rcx, [rsp+2E8h+hToken]
0x18004fb91  call    ?reset@?$EcsUniqueHandle@PEAXUWin32HandleDeleter@@$0A@@@QEAAXAEBQEAX@Z; EcsUniqueHandle<void *,Win32HandleDeleter,0>::reset(void * const &)
0x18004fb96  nop
0x18004fb97  mov     [rsp+2E8h+ProfileDir], bx
0x18004fb9f  xor     edx, edx; Val
0x18004fba1  mov     r8d, 206h; Size
0x18004fba7  lea     rcx, [rsp+2E8h+var_246]; void *
0x18004fbaf  call    memset_0
0x18004fbb4  mov     esi, 104h
0x18004fbb9  mov     [rsp+2E8h+cchSize], esi
0x18004fbbd  mov     eax, [rsp+2E8h+var_2B8]
0x18004fbc1  mov     [rsp+2E8h+var_2B8], eax
0x18004fbc5  lea     r8, [rsp+2E8h+cchSize]; lpcchSize
0x18004fbca  lea     rdx, [rsp+2E8h+ProfileDir]; lpProfileDir
0x18004fbd2  mov     rcx, [rsp+2E8h+hToken]; hToken
0x18004fbd7  call    cs:__imp_GetUserProfileDirectoryW
0x18004fbdd  test    eax, eax
0x18004fbdf  jnz     short loc_18004FC09
0x18004fbe1  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x18004fbe6  mov     [rsp+2E8h+var_2B8], eax
0x18004fbea  mov     ecx, 37h ; '7'
0x18004fbef  mov     word ptr [rsp+2E8h+var_2B4+2], cx
0x18004fbf4  mov     [rsp+2E8h+pExceptionObject], eax
0x18004fbf8  lea     rdx, _TI1J; pThrowInfo
0x18004fbff  lea     rcx, [rsp+2E8h+pExceptionObject]; pExceptionObject
0x18004fc04  call    _CxxThrowException_0
0x18004fc09  mov     [rsp+2E8h+var_2B8], ebx
0x18004fc0d  mov     ecx, 37h ; '7'
0x18004fc12  mov     word ptr [rsp+2E8h+var_2B4], cx
0x18004fc17  lea     r9d, [rcx-36h]; dwFlags
0x18004fc1b  lea     r8, pszMore; "AppData\\Local\\Microsoft\\Windows\\Wor"...
0x18004fc22  mov     rdx, rsi; cchPath
0x18004fc25  lea     rcx, [rsp+2E8h+ProfileDir]; pszPath
0x18004fc2d  call    cs:__imp_PathCchAppendEx
0x18004fc33  mov     [rsp+2E8h+var_2B8], eax
0x18004fc37  mov     [rsp+2E8h+var_2B8], eax
0x18004fc3b  mov     ecx, 3Bh ; ';'
0x18004fc40  test    eax, eax
0x18004fc42  jns     short loc_18004FC5E
0x18004fc44  mov     word ptr [rsp+2E8h+var_2B4+2], cx
0x18004fc49  mov     [rsp+2E8h+var_290], eax
0x18004fc4d  lea     rdx, _TI1J; pThrowInfo
0x18004fc54  lea     rcx, [rsp+2E8h+var_290]; pExceptionObject
0x18004fc59  call    _CxxThrowException_0
0x18004fc5e  mov     word ptr [rsp+2E8h+var_2B4], cx
0x18004fc63  lea     rdx, [rsp+2E8h+ProfileDir]
0x18004fc6b  lea     rcx, [rdi+58h]
0x18004fc6f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator=(ushort const * const)
0x18004fc74  nop
0x18004fc75  mov     [rsp+2E8h+var_260], rbx
0x18004fc7d  lea     rdx, [rsp+2E8h+var_260]
0x18004fc85  lea     rcx, [rsp+2E8h+hToken]
0x18004fc8a  call    ?reset@?$EcsUniqueHandle@PEAXUWin32HandleDeleter@@$0A@@@QEAAXAEBQEAX@Z; EcsUniqueHandle<void *,Win32HandleDeleter,0>::reset(void * const &)
0x18004fc8f  lea     rcx, [rdi+58h]
0x18004fc93  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004fc98  mov     [rdi+140h], rax
0x18004fc9f  mov     rcx, r12
0x18004fca2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004fca7  mov     [rdi+138h], rax
0x18004fcae  mov     [rsp+2E8h+var_278], rbx
0x18004fcb3  mov     rcx, r12
0x18004fcb6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004fcbb  lea     rcx, [rsp+2E8h+var_278]
0x18004fcc0  mov     [rsp+2E8h+var_2C8], rcx; struct ICloudFileDataStorageConfiguration **
0x18004fcc5  mov     r9, [r15]; struct IFileDownloadManager *
0x18004fcc8  mov     r8d, [rdi+124h]; unsigned int
0x18004fccf  mov     rdx, [rdi+118h]; __int64
0x18004fcd6  mov     rcx, rax; unsigned __int16 *
0x18004fcd9  call    ?CreateInstance@CCloudFileDataStorageConfiguration@@SAJPEBG_JKPEAUIFileDownloadManager@@PEAPEAUICloudFileDataStorageConfiguration@@@Z; CCloudFileDataStorageConfiguration::CreateInstance(ushort const *,__int64,ulong,IFileDownloadManager *,ICloudFileDataStorageConfiguration * *)
0x18004fcde  mov     [rsp+2E8h+var_2B8], eax
0x18004fce2  mov     [rsp+2E8h+var_2B8], eax
0x18004fce6  mov     ecx, 4Ch ; 'L'
0x18004fceb  test    eax, eax
0x18004fced  jns     short loc_18004FD09
0x18004fcef  mov     word ptr [rsp+2E8h+var_2B4+2], cx
0x18004fcf4  mov     [rsp+2E8h+var_28C], eax
0x18004fcf8  lea     rdx, _TI1J; pThrowInfo
0x18004fcff  lea     rcx, [rsp+2E8h+var_28C]; pExceptionObject
0x18004fd04  call    _CxxThrowException_0
0x18004fd09  mov     word ptr [rsp+2E8h+var_2B4], cx
0x18004fd0e  mov     rcx, [rsp+2E8h+var_278]
0x18004fd13  mov     rax, [rcx]
0x18004fd16  mov     r8, r14
0x18004fd19  lea     rdx, _GUID_286cc90b_2281_479b_b861_97df1fd3f1e5
0x18004fd20  mov     rax, [rax]
0x18004fd23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fd28  mov     [rsp+2E8h+var_2B8], eax
0x18004fd2c  mov     [rsp+2E8h+var_2B8], eax
0x18004fd30  mov     ecx, 4Eh ; 'N'
0x18004fd35  test    eax, eax
0x18004fd37  jns     short loc_18004FD53
0x18004fd39  mov     word ptr [rsp+2E8h+var_2B4+2], cx
0x18004fd3e  mov     [rsp+2E8h+var_288], eax
0x18004fd42  lea     rdx, _TI1J; pThrowInfo
0x18004fd49  lea     rcx, [rsp+2E8h+var_288]; pExceptionObject
0x18004fd4e  call    _CxxThrowException_0
0x18004fd53  mov     word ptr [rsp+2E8h+var_2B4], cx
0x18004fd58  lea     rcx, [rsp+2E8h+var_278]
0x18004fd5d  call    ??1?$CComPtr@UICloudFileInfoFromDisk@@@ATL@@QEAA@XZ; ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(void)
0x18004fd62  nop
0x18004fd63  jmp     short loc_18004FD6B
0x18004fd65  jmp     short loc_18004FD6B
0x18004fd67  jmp     short loc_18004FD6B
0x18004fd69  jmp     short $+2
0x18004fd6b  mov     ebx, [rsp+2E8h+var_2B8]
0x18004fd6f  lea     rcx, [rsp+2E8h+var_2B8]; this
0x18004fd74  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x18004fd79  mov     eax, ebx
0x18004fd7b  mov     rcx, [rsp+2E8h+var_38]
0x18004fd83  xor     rcx, rsp; StackCookie
0x18004fd86  call    __security_check_cookie
0x18004fd8b  lea     r11, [rsp+2E8h+var_28]
0x18004fd93  mov     rbx, [r11+40h]
0x18004fd97  mov     rsi, [r11+48h]
0x18004fd9b  mov     rsp, r11
0x18004fd9e  pop     r15
0x18004fda0  pop     r14
0x18004fda2  pop     r13
0x18004fda4  pop     r12
0x18004fda6  pop     rdi
0x18004fda7  retn
```
