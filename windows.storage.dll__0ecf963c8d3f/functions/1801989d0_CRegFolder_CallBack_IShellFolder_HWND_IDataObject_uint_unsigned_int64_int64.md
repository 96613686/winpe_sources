# CRegFolder::CallBack(IShellFolder *,HWND__ *,IDataObject *,uint,unsigned __int64,__int64)

- ea: `0x1801989d0`
- end: `0x180198cc7`
- name: `?CallBack@CRegFolder@@UEAAJPEAUIShellFolder@@PEAUHWND__@@PEAUIDataObject@@I_K_J@Z`
- size: `759`
- prototype: `__int64 __fastcall(CRegFolder *this, struct IShellFolder *, HWND, struct IDataObject *, unsigned int, int *, LPCSTR pszStr1)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18007e930`
- `0x180169e00`
- `0x180198854`
- `0x1801989d0`
- `0x180198cd0`
- `0x180199438`
- `0x180255440`
- `0x180354f9c`
- `0x18035c79c`
- `0x18035d8b8`
- `0x1803a4cb0`
- `0x18052bb08`
- `0x18052d778`
- `0x18052e188`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180198a97`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180198aef`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180198a97`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180198aef`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180198aca`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180198b14`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180198aca`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180198b14`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180198ba4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180198ba4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180198c0b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180198c0b`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180198bf7`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180198bf7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180198c19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180198c24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180198c19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180198c24`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_CDefFolderMenu_MergeMenu` at `0x180198b06`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_CDefFolderMenu_MergeMenu` at `0x180198b06`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_SHStartNetConnectionDialogW` at `0x180198cb2`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_SHStartNetConnectionDialogW` at `0x180198cb2`

## string_xrefs

- `0x180198a8c`: `shell32.dll`
- `0x180198ae4`: `shell32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CRegFolder::CallBack(
        CRegFolder *this,
        struct IShellFolder *a2,
        HWND a3,
        struct IDataObject *a4,
        unsigned int a5,
        int *a6,
        LPCSTR pszStr1)
{
  const struct ICIVERBTOIDMAP *v8; // rax
  const struct ICIVERBTOIDMAP *v9; // rcx
  int v10; // eax
  unsigned int v11; // edi
  HMODULE v13; // rbx
  HMODULE Library; // rbx
  const struct IDLREGITEM *v15; // rax
  unsigned int v16; // r9d
  int v17; // eax
  WCHAR *v18; // rbx
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  PCWSTR pszPathIn; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR String1[264]; // [rsp+40h] [rbp-C0h] BYREF

  switch ( a5 )
  {
    case 1u:
      if ( CRegFolder::_CanMapNetDrive(this, a4) )
      {
        Library = LoadLibraryExW(L"shell32.dll", 0, 2u);
        SHELL32_CDefFolderMenu_MergeMenu(Library, 225, 0, pszStr1);
        if ( Library )
          FreeLibrary(Library);
      }
      return 0;
    case 5u:
    case 9u:
    case 0xBu:
LABEL_11:
      v13 = LoadLibraryExW(L"shell32.dll", 0, 2u);
      v11 = HandleStandardDFM(
              v13,
              a5,
              (unsigned __int64)a6,
              (__int64)pszStr1,
              (const struct ICIVERBTOIDMAP *)&off_1806759E0);
      if ( v13 )
        FreeLibrary(v13);
      return v11;
    case 0xCu:
      v11 = 0;
      if ( a6 == (int *)9 )
      {
        Windows::Internal::ComTaskPool::QueueTask__lambda_dfbd53f5f9ebc03a625422e6d886e0a8___(this, a2, a3, a4);
      }
      else if ( a6 == (int *)14 )
      {
        SHELL32_SHStartNetConnectionDialogW(0, 0, 1, a4);
      }
      else if ( a6 == (int *)4294967291LL )
      {
        pv = 0;
        if ( DataObj_GetChildIDList(a4, (struct _ITEMID_CHILD **)&pv) >= 0 )
        {
          v15 = CRegFolder::_IsReg((CRegFolder *)((char *)this - 56), (const struct _ITEMIDLIST_RELATIVE *)pv);
          if ( v15 )
          {
            if ( (int)CRegFolder::_GetControlPanelForItem((CRegFolder *)((char *)this - 56), v15, String1, v16) < 0 )
            {
              v11 = 1;
            }
            else
            {
              if ( CompareStringOrdinal(String1, -1, L"SYSTEM", -1, 1) == 2 )
                _FireSystemCPLPerfTrackEvent();
              pszPathIn = 0;
              v17 = wil::GetSystemDirectoryW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(&pszPathIn);
              v18 = (WCHAR *)pszPathIn;
              v11 = v17;
              if ( v17 >= 0 )
              {
                pszPathIn = 0;
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
                  &pszPathIn,
                  0);
                if ( PathAllocCombine(v18, L"control.exe", 1u, (PWSTR *)&pszPathIn) >= 0 )
                  ShellExecuteW(0, 0, pszPathIn, String1, 0, 5);
                if ( pszPathIn )
                  LocalFree((HLOCAL)pszPathIn);
              }
              if ( v18 )
                CoTaskMemFree(v18);
            }
          }
          CoTaskMemFree(pv);
        }
      }
      else if ( a6 == (int *)0xFFFFFFFFLL )
      {
        CRegFolder::_Delete((CRegFolder *)((char *)this - 56), a3, *((_DWORD *)pszStr1 + 1), a4);
      }
      else
      {
        return 1;
      }
      break;
    case 0xDu:
      v8 = _CmdIDToMap(pszStr1, 1, (const struct ICIVERBTOIDMAP *)&off_1806759E0);
      v9 = v8;
      if ( v8 )
        v10 = *((_DWORD *)v8 + 4);
      else
        v10 = -1;
      *a6 = v10;
      return v9 == 0 ? 0x80004005 : 0;
    default:
      if ( a5 - 15 >= 2 )
        return (unsigned int)-2147467263;
      goto LABEL_11;
  }
  return v11;
}

```

## disassembly

```asm
0x1801989d0  push    rbp
0x1801989d2  push    rbx
0x1801989d3  push    rsi
0x1801989d4  push    rdi
0x1801989d5  push    r14
0x1801989d7  lea     rbp, [rsp-160h]
0x1801989df  sub     rsp, 260h
0x1801989e6  mov     rax, cs:__security_cookie
0x1801989ed  xor     rax, rsp
0x1801989f0  mov     [rbp+180h+var_30], rax
0x1801989f7  mov     eax, [rbp+180h+arg_20]
0x1801989fd  mov     r10, r8
0x180198a00  mov     rsi, [rbp+180h+arg_28]
0x180198a07  mov     rbx, rcx
0x180198a0a  mov     r14, [rbp+180h+pszStr1]
0x180198a11  sub     eax, 1
0x180198a14  jz      loc_180198AD2
0x180198a1a  sub     eax, 4
0x180198a1d  jz      short loc_180198A8A
0x180198a1f  sub     eax, 4
0x180198a22  jz      short loc_180198A8A
0x180198a24  sub     eax, 2
0x180198a27  jz      short loc_180198A8A
0x180198a29  sub     eax, 1
0x180198a2c  jz      loc_180198B1C
0x180198a32  sub     eax, 1
0x180198a35  jnz     loc_180198C39
0x180198a3b  lea     r8, off_1806759E0; struct ICIVERBTOIDMAP *
0x180198a42  mov     rcx, r14; pszStr1
0x180198a45  lea     edx, [rax+1]; int
0x180198a48  call    ?_CmdIDToMap@@YAPEBUICIVERBTOIDMAP@@_KHPEBU1@@Z; _CmdIDToMap(unsigned __int64,int,ICIVERBTOIDMAP const *)
0x180198a4d  mov     rcx, rax
0x180198a50  test    rax, rax
0x180198a53  jz      loc_180198C2F
0x180198a59  mov     eax, [rax+10h]
0x180198a5c  neg     rcx
0x180198a5f  mov     [rsi], eax
0x180198a61  sbb     edi, edi
0x180198a63  not     edi
0x180198a65  and     edi, 80004005h
0x180198a6b  mov     eax, edi
0x180198a6d  mov     rcx, [rbp+180h+var_30]
0x180198a74  xor     rcx, rsp; StackCookie
0x180198a77  call    __security_check_cookie
0x180198a7c  add     rsp, 260h
0x180198a83  pop     r14
0x180198a85  pop     rdi
0x180198a86  pop     rsi
0x180198a87  pop     rbx
0x180198a88  pop     rbp
0x180198a89  retn
0x180198a8a  xor     edx, edx; hFile
0x180198a8c  lea     rcx, aShell32Dll; "shell32.dll"
0x180198a93  lea     r8d, [rdx+2]; dwFlags
0x180198a97  call    cs:__imp_LoadLibraryExW
0x180198a9d  mov     edx, [rbp+180h+arg_20]; unsigned int
0x180198aa3  mov     r9, r14; __int64
0x180198aa6  mov     rbx, rax
0x180198aa9  mov     r8, rsi; unsigned __int64
0x180198aac  lea     rax, off_1806759E0; "connectNetworkDrive"
0x180198ab3  mov     rcx, rbx; HINSTANCE
0x180198ab6  mov     qword ptr [rsp+280h+bIgnoreCase], rax; struct ICIVERBTOIDMAP *
0x180198abb  call    ?HandleStandardDFM@@YAJPEAUHINSTANCE__@@I_K_JPEBUICIVERBTOIDMAP@@@Z; HandleStandardDFM(HINSTANCE__ *,uint,unsigned __int64,__int64,ICIVERBTOIDMAP const *)
0x180198ac0  mov     edi, eax
0x180198ac2  test    rbx, rbx
0x180198ac5  jz      short loc_180198A6B
0x180198ac7  mov     rcx, rbx; hLibModule
0x180198aca  call    cs:__imp_FreeLibrary
0x180198ad0  jmp     short loc_180198A6B
0x180198ad2  mov     rdx, r9; struct IDataObject *
0x180198ad5  call    ?_CanMapNetDrive@CRegFolder@@AEAAHPEAUIDataObject@@@Z; CRegFolder::_CanMapNetDrive(IDataObject *)
0x180198ada  test    eax, eax
0x180198adc  jnz     short loc_180198AE2
0x180198ade  xor     edi, edi
0x180198ae0  jmp     short loc_180198A6B
0x180198ae2  xor     edx, edx; hFile
0x180198ae4  lea     rcx, aShell32Dll; "shell32.dll"
0x180198aeb  lea     r8d, [rdx+2]; dwFlags
0x180198aef  call    cs:__imp_LoadLibraryExW
0x180198af5  mov     r9, r14
0x180198af8  xor     r8d, r8d
0x180198afb  mov     rcx, rax
0x180198afe  mov     edx, 0E1h
0x180198b03  mov     rbx, rax
0x180198b06  call    cs:__imp_SHELL32_CDefFolderMenu_MergeMenu
0x180198b0c  test    rbx, rbx
0x180198b0f  jz      short loc_180198ADE
0x180198b11  mov     rcx, rbx; hLibModule
0x180198b14  call    cs:__imp_FreeLibrary
0x180198b1a  jmp     short loc_180198ADE
0x180198b1c  xor     edi, edi
0x180198b1e  cmp     rsi, 9
0x180198b22  jz      loc_180198CBD
0x180198b28  cmp     rsi, 0Eh
0x180198b2c  jz      loc_180198CAA
0x180198b32  mov     eax, 0FFFFFFFBh
0x180198b37  cmp     rsi, rax
0x180198b3a  jnz     loc_180198C55
0x180198b40  lea     rdx, [rsp+280h+pv]; struct _ITEMID_CHILD **
0x180198b45  mov     [rsp+280h+pv], rdi
0x180198b4a  mov     rcx, r9; struct IDataObject *
0x180198b4d  call    ?DataObj_GetChildIDList@@YAJPEAUIDataObject@@PEAPEAU_ITEMID_CHILD@@@Z; DataObj_GetChildIDList(IDataObject *,_ITEMID_CHILD * *)
0x180198b52  test    eax, eax
0x180198b54  js      loc_180198A6B
0x180198b5a  mov     rdx, [rsp+280h+pv]; struct _ITEMIDLIST_RELATIVE *
0x180198b5f  lea     rcx, [rbx-38h]; this
0x180198b63  call    ?_IsReg@CRegFolder@@AEAAPEFBUIDLREGITEM@@PEFBU_ITEMIDLIST_RELATIVE@@@Z; CRegFolder::_IsReg(_ITEMIDLIST_RELATIVE const *)
0x180198b68  test    rax, rax
0x180198b6b  jz      loc_180198C1F
0x180198b71  lea     r8, [rsp+280h+String1]; unsigned __int16 *
0x180198b76  mov     rdx, rax; struct IDLREGITEM *
0x180198b79  lea     rcx, [rbx-38h]; this
0x180198b7d  call    ?_GetControlPanelForItem@CRegFolder@@AEAAJPEFBUIDLREGITEM@@PEAGI@Z; CRegFolder::_GetControlPanelForItem(IDLREGITEM const *,ushort *,uint)
0x180198b82  test    eax, eax
0x180198b84  js      loc_180198CA0
0x180198b8a  or      edx, 0FFFFFFFFh; cchCount1
0x180198b8d  mov     [rsp+280h+bIgnoreCase], 1; bIgnoreCase
0x180198b95  mov     r9d, edx; cchCount2
0x180198b98  lea     r8, aSystem; "SYSTEM"
0x180198b9f  lea     rcx, [rsp+280h+String1]; lpString1
0x180198ba4  call    cs:__imp_CompareStringOrdinal
0x180198baa  cmp     eax, 2
0x180198bad  jz      loc_180198C6D
0x180198bb3  lea     rcx, [rsp+280h+pszPathIn]
0x180198bb8  mov     [rsp+280h+pszPathIn], rdi
0x180198bbd  call    ??$GetSystemDirectoryW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@@Z; wil::GetSystemDirectoryW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x180198bc2  mov     rbx, [rsp+280h+pszPathIn]
0x180198bc7  mov     edi, eax
0x180198bc9  test    eax, eax
0x180198bcb  js      short loc_180198C11
0x180198bcd  xor     edx, edx
0x180198bcf  mov     [rsp+280h+pszPathIn], 0
0x180198bd8  lea     rcx, [rsp+280h+pszPathIn]
0x180198bdd  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180198be2  lea     r9, [rsp+280h+pszPathIn]; ppszPathOut
0x180198be7  mov     r8d, 1; dwFlags
0x180198bed  lea     rdx, aControlExe; "control.exe"
0x180198bf4  mov     rcx, rbx; pszPathIn
0x180198bf7  call    cs:__imp_PathAllocCombine
0x180198bfd  test    eax, eax
0x180198bff  jns     short loc_180198C77
0x180198c01  mov     rcx, [rsp+280h+pszPathIn]; hMem
0x180198c06  test    rcx, rcx
0x180198c09  jz      short loc_180198C11
0x180198c0b  call    cs:__imp_LocalFree
0x180198c11  test    rbx, rbx
0x180198c14  jz      short loc_180198C1F
0x180198c16  mov     rcx, rbx; pv
0x180198c19  call    cs:__imp_CoTaskMemFree
0x180198c1f  mov     rcx, [rsp+280h+pv]; pv
0x180198c24  call    cs:__imp_CoTaskMemFree
0x180198c2a  jmp     loc_180198A6B
0x180198c2f  mov     eax, 0FFFFFFFFh
0x180198c34  jmp     loc_180198A5C
0x180198c39  sub     eax, 2
0x180198c3c  jz      loc_180198A8A
0x180198c42  cmp     eax, 1
0x180198c45  jz      loc_180198A8A
0x180198c4b  mov     edi, 80004001h
0x180198c50  jmp     loc_180198A6B
0x180198c55  mov     eax, 0FFFFFFFFh
0x180198c5a  cmp     rsi, rax
0x180198c5d  jz      loc_18064BB62
0x180198c63  mov     edi, 1
0x180198c68  jmp     loc_180198A6B
0x180198c6d  call    ?_FireSystemCPLPerfTrackEvent@@YAXXZ; _FireSystemCPLPerfTrackEvent(void)
0x180198c72  jmp     loc_180198BB3
0x180198c77  mov     r8, [rsp+280h+pszPathIn]; lpFile
0x180198c7c  lea     r9, [rsp+280h+String1]; lpParameters
0x180198c81  mov     [rsp+280h+nShowCmd], 5; nShowCmd
0x180198c89  xor     edx, edx; lpOperation
0x180198c8b  xor     ecx, ecx; hwnd
0x180198c8d  mov     qword ptr [rsp+280h+bIgnoreCase], 0; lpDirectory
0x180198c96  call    ShellExecuteW
0x180198c9b  jmp     loc_180198C01
0x180198ca0  mov     edi, 1
0x180198ca5  jmp     loc_180198C1F
0x180198caa  xor     edx, edx
0x180198cac  xor     ecx, ecx
0x180198cae  lea     r8d, [rdx+1]
0x180198cb2  call    cs:__imp_SHELL32_SHStartNetConnectionDialogW
0x180198cb8  jmp     loc_180198A6B
0x180198cbd  call    Windows__Internal__ComTaskPool__QueueTask__lambda_dfbd53f5f9ebc03a625422e6d886e0a8___
0x180198cc2  jmp     loc_180198A6B
0x18064bb62  mov     r8d, [r14+4]; unsigned int
0x18064bb66  add     rcx, 0FFFFFFFFFFFFFFC8h; this
0x18064bb6a  mov     rdx, r10; HWND
0x18064bb6d  call    ?_Delete@CRegFolder@@AEAAXPEAUHWND__@@IPEAUIDataObject@@@Z; CRegFolder::_Delete(HWND__ *,uint,IDataObject *)
0x18064bb72  nop
0x18064bb73  jmp     loc_180198A6B
```
