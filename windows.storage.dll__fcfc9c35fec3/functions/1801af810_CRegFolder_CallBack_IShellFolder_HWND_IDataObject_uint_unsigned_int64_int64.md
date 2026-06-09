# CRegFolder::CallBack(IShellFolder *,HWND__ *,IDataObject *,uint,unsigned __int64,__int64)

- ea: `0x1801af810`
- end: `0x1801afb51`
- name: `?CallBack@CRegFolder@@UEAAJPEAUIShellFolder@@PEAUHWND__@@PEAUIDataObject@@I_K_J@Z`
- size: `833`
- prototype: `int(CRegFolder *__hidden this, struct IShellFolder *, HWND, struct IDataObject *, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180094130`
- `0x1800ee270`
- `0x1801af690`
- `0x1801af810`
- `0x1801afb58`
- `0x1801b031c`
- `0x180266d70`
- `0x180368a88`
- `0x18036dfb0`
- `0x18036f284`
- `0x1803b1f60`
- `0x180542500`
- `0x180544240`
- `0x180544c8c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1801af8d8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1801af93f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1801af8d8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1801af93f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1801af911`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1801af970`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1801af911`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1801af970`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801afa06`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801afa06`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801afa7d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801afa7d`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1801afa5f`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1801afa5f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801afa91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801afaa2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801afa91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801afaa2`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_CDefFolderMenu_MergeMenu` at `0x1801af95c`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_CDefFolderMenu_MergeMenu` at `0x1801af95c`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_SHStartNetConnectionDialogW` at `0x1801afb36`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_SHStartNetConnectionDialogW` at `0x1801afb36`

## string_xrefs

- `0x1801af8cd`: `shell32.dll`
- `0x1801af934`: `shell32.dll`

## pseudocode

```c
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
              (const struct ICIVERBTOIDMAP *)&off_180699610);
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
      v8 = _CmdIDToMap(pszStr1, 1, (const struct ICIVERBTOIDMAP *)&off_180699610);
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
0x1801af810  push    rbp
0x1801af812  push    rbx
0x1801af813  push    rsi
0x1801af814  push    rdi
0x1801af815  push    r14
0x1801af817  lea     rbp, [rsp-160h]
0x1801af81f  sub     rsp, 260h
0x1801af826  mov     rax, cs:__security_cookie
0x1801af82d  xor     rax, rsp
0x1801af830  mov     [rbp+180h+var_30], rax
0x1801af837  mov     eax, [rbp+180h+arg_20]
0x1801af83d  mov     r10, r8
0x1801af840  mov     rsi, [rbp+180h+arg_28]
0x1801af847  mov     rbx, rcx
0x1801af84a  mov     r14, [rbp+180h+pszStr1]
0x1801af851  sub     eax, 1
0x1801af854  jz      loc_1801AF91F
0x1801af85a  sub     eax, 4
0x1801af85d  jz      short loc_1801AF8CB
0x1801af85f  sub     eax, 4
0x1801af862  jz      short loc_1801AF8CB
0x1801af864  sub     eax, 2
0x1801af867  jz      short loc_1801AF8CB
0x1801af869  sub     eax, 1
0x1801af86c  jz      loc_1801AF97E
0x1801af872  sub     eax, 1
0x1801af875  jnz     loc_1801AFABD
0x1801af87b  lea     r8, off_180699610; struct ICIVERBTOIDMAP *
0x1801af882  mov     rcx, r14; pszStr1
0x1801af885  lea     edx, [rax+1]; int
0x1801af888  call    ?_CmdIDToMap@@YAPEBUICIVERBTOIDMAP@@_KHPEBU1@@Z; _CmdIDToMap(unsigned __int64,int,ICIVERBTOIDMAP const *)
0x1801af88d  mov     rcx, rax
0x1801af890  test    rax, rax
0x1801af893  jz      loc_1801AFAB3
0x1801af899  mov     eax, [rax+10h]
0x1801af89c  neg     rcx
0x1801af89f  mov     [rsi], eax
0x1801af8a1  sbb     edi, edi
0x1801af8a3  not     edi
0x1801af8a5  and     edi, 80004005h
0x1801af8ab  mov     eax, edi
0x1801af8ad  mov     rcx, [rbp+180h+var_30]
0x1801af8b4  xor     rcx, rsp; StackCookie
0x1801af8b7  call    __security_check_cookie
0x1801af8bc  add     rsp, 260h
0x1801af8c3  pop     r14
0x1801af8c5  pop     rdi
0x1801af8c6  pop     rsi
0x1801af8c7  pop     rbx
0x1801af8c8  pop     rbp
0x1801af8c9  retn
0x1801af8cb  xor     edx, edx; hFile
0x1801af8cd  lea     rcx, aShell32Dll; "shell32.dll"
0x1801af8d4  lea     r8d, [rdx+2]; dwFlags
0x1801af8d8  call    cs:__imp_LoadLibraryExW
0x1801af8df  nop     dword ptr [rax+rax+00h]
0x1801af8e4  mov     edx, [rbp+180h+arg_20]; unsigned int
0x1801af8ea  mov     r9, r14; __int64
0x1801af8ed  mov     rbx, rax
0x1801af8f0  mov     r8, rsi; unsigned __int64
0x1801af8f3  lea     rax, off_180699610; "connectNetworkDrive"
0x1801af8fa  mov     rcx, rbx; HINSTANCE
0x1801af8fd  mov     qword ptr [rsp+280h+bIgnoreCase], rax; struct ICIVERBTOIDMAP *
0x1801af902  call    ?HandleStandardDFM@@YAJPEAUHINSTANCE__@@I_K_JPEBUICIVERBTOIDMAP@@@Z; HandleStandardDFM(HINSTANCE__ *,uint,unsigned __int64,__int64,ICIVERBTOIDMAP const *)
0x1801af907  mov     edi, eax
0x1801af909  test    rbx, rbx
0x1801af90c  jz      short loc_1801AF8AB
0x1801af90e  mov     rcx, rbx; hLibModule
0x1801af911  call    cs:__imp_FreeLibrary
0x1801af918  nop     dword ptr [rax+rax+00h]
0x1801af91d  jmp     short loc_1801AF8AB
0x1801af91f  mov     rdx, r9; struct IDataObject *
0x1801af922  call    ?_CanMapNetDrive@CRegFolder@@AEAAHPEAUIDataObject@@@Z; CRegFolder::_CanMapNetDrive(IDataObject *)
0x1801af927  test    eax, eax
0x1801af929  jnz     short loc_1801AF932
0x1801af92b  xor     edi, edi
0x1801af92d  jmp     loc_1801AF8AB
0x1801af932  xor     edx, edx; hFile
0x1801af934  lea     rcx, aShell32Dll; "shell32.dll"
0x1801af93b  lea     r8d, [rdx+2]; dwFlags
0x1801af93f  call    cs:__imp_LoadLibraryExW
0x1801af946  nop     dword ptr [rax+rax+00h]
0x1801af94b  mov     r9, r14
0x1801af94e  xor     r8d, r8d
0x1801af951  mov     rcx, rax
0x1801af954  mov     edx, 0E1h
0x1801af959  mov     rbx, rax
0x1801af95c  call    cs:__imp_SHELL32_CDefFolderMenu_MergeMenu
0x1801af963  nop     dword ptr [rax+rax+00h]
0x1801af968  test    rbx, rbx
0x1801af96b  jz      short loc_1801AF92B
0x1801af96d  mov     rcx, rbx; hLibModule
0x1801af970  call    cs:__imp_FreeLibrary
0x1801af977  nop     dword ptr [rax+rax+00h]
0x1801af97c  jmp     short loc_1801AF92B
0x1801af97e  xor     edi, edi
0x1801af980  cmp     rsi, 9
0x1801af984  jz      loc_1801AFB47
0x1801af98a  cmp     rsi, 0Eh
0x1801af98e  jz      loc_1801AFB2E
0x1801af994  mov     eax, 0FFFFFFFBh
0x1801af999  cmp     rsi, rax
0x1801af99c  jnz     loc_1801AFAD9
0x1801af9a2  lea     rdx, [rsp+280h+pv]; struct _ITEMID_CHILD **
0x1801af9a7  mov     [rsp+280h+pv], rdi
0x1801af9ac  mov     rcx, r9; struct IDataObject *
0x1801af9af  call    ?DataObj_GetChildIDList@@YAJPEAUIDataObject@@PEAPEAU_ITEMID_CHILD@@@Z; DataObj_GetChildIDList(IDataObject *,_ITEMID_CHILD * *)
0x1801af9b4  test    eax, eax
0x1801af9b6  js      loc_1801AF8AB
0x1801af9bc  mov     rdx, [rsp+280h+pv]; struct _ITEMIDLIST_RELATIVE *
0x1801af9c1  lea     rcx, [rbx-38h]; this
0x1801af9c5  call    ?_IsReg@CRegFolder@@AEAAPEFBUIDLREGITEM@@PEFBU_ITEMIDLIST_RELATIVE@@@Z; CRegFolder::_IsReg(_ITEMIDLIST_RELATIVE const *)
0x1801af9ca  test    rax, rax
0x1801af9cd  jz      loc_1801AFA9D
0x1801af9d3  lea     r8, [rsp+280h+String1]; unsigned __int16 *
0x1801af9d8  mov     rdx, rax; struct IDLREGITEM *
0x1801af9db  lea     rcx, [rbx-38h]; this
0x1801af9df  call    ?_GetControlPanelForItem@CRegFolder@@AEAAJPEFBUIDLREGITEM@@PEAGI@Z; CRegFolder::_GetControlPanelForItem(IDLREGITEM const *,ushort *,uint)
0x1801af9e4  test    eax, eax
0x1801af9e6  js      loc_1801AFB24
0x1801af9ec  or      edx, 0FFFFFFFFh; cchCount1
0x1801af9ef  mov     [rsp+280h+bIgnoreCase], 1; bIgnoreCase
0x1801af9f7  mov     r9d, edx; cchCount2
0x1801af9fa  lea     r8, aSystem; "SYSTEM"
0x1801afa01  lea     rcx, [rsp+280h+String1]; lpString1
0x1801afa06  call    cs:__imp_CompareStringOrdinal
0x1801afa0d  nop     dword ptr [rax+rax+00h]
0x1801afa12  cmp     eax, 2
0x1801afa15  jz      loc_1801AFAF1
0x1801afa1b  lea     rcx, [rsp+280h+pszPathIn]
0x1801afa20  mov     [rsp+280h+pszPathIn], rdi
0x1801afa25  call    ??$GetSystemDirectoryW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@@Z; wil::GetSystemDirectoryW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x1801afa2a  mov     rbx, [rsp+280h+pszPathIn]
0x1801afa2f  mov     edi, eax
0x1801afa31  test    eax, eax
0x1801afa33  js      short loc_1801AFA89
0x1801afa35  xor     edx, edx
0x1801afa37  mov     [rsp+280h+pszPathIn], 0
0x1801afa40  lea     rcx, [rsp+280h+pszPathIn]
0x1801afa45  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1801afa4a  lea     r9, [rsp+280h+pszPathIn]; ppszPathOut
0x1801afa4f  mov     r8d, 1; dwFlags
0x1801afa55  lea     rdx, aControlExe; "control.exe"
0x1801afa5c  mov     rcx, rbx; pszPathIn
0x1801afa5f  call    cs:__imp_PathAllocCombine
0x1801afa66  nop     dword ptr [rax+rax+00h]
0x1801afa6b  test    eax, eax
0x1801afa6d  jns     loc_1801AFAFB
0x1801afa73  mov     rcx, [rsp+280h+pszPathIn]; hMem
0x1801afa78  test    rcx, rcx
0x1801afa7b  jz      short loc_1801AFA89
0x1801afa7d  call    cs:__imp_LocalFree
0x1801afa84  nop     dword ptr [rax+rax+00h]
0x1801afa89  test    rbx, rbx
0x1801afa8c  jz      short loc_1801AFA9D
0x1801afa8e  mov     rcx, rbx; pv
0x1801afa91  call    cs:__imp_CoTaskMemFree
0x1801afa98  nop     dword ptr [rax+rax+00h]
0x1801afa9d  mov     rcx, [rsp+280h+pv]; pv
0x1801afaa2  call    cs:__imp_CoTaskMemFree
0x1801afaa9  nop     dword ptr [rax+rax+00h]
0x1801afaae  jmp     loc_1801AF8AB
0x1801afab3  mov     eax, 0FFFFFFFFh
0x1801afab8  jmp     loc_1801AF89C
0x1801afabd  sub     eax, 2
0x1801afac0  jz      loc_1801AF8CB
0x1801afac6  cmp     eax, 1
0x1801afac9  jz      loc_1801AF8CB
0x1801afacf  mov     edi, 80004001h
0x1801afad4  jmp     loc_1801AF8AB
0x1801afad9  mov     eax, 0FFFFFFFFh
0x1801afade  cmp     rsi, rax
0x1801afae1  jz      loc_18067067C
0x1801afae7  mov     edi, 1
0x1801afaec  jmp     loc_1801AF8AB
0x1801afaf1  call    ?_FireSystemCPLPerfTrackEvent@@YAXXZ; _FireSystemCPLPerfTrackEvent(void)
0x1801afaf6  jmp     loc_1801AFA1B
0x1801afafb  mov     r8, [rsp+280h+pszPathIn]; lpFile
0x1801afb00  lea     r9, [rsp+280h+String1]; lpParameters
0x1801afb05  mov     [rsp+280h+nShowCmd], 5; nShowCmd
0x1801afb0d  xor     edx, edx; lpOperation
0x1801afb0f  xor     ecx, ecx; hwnd
0x1801afb11  mov     qword ptr [rsp+280h+bIgnoreCase], 0; lpDirectory
0x1801afb1a  call    ShellExecuteW
0x1801afb1f  jmp     loc_1801AFA73
0x1801afb24  mov     edi, 1
0x1801afb29  jmp     loc_1801AFA9D
0x1801afb2e  xor     edx, edx
0x1801afb30  xor     ecx, ecx
0x1801afb32  lea     r8d, [rdx+1]
0x1801afb36  call    cs:__imp_SHELL32_SHStartNetConnectionDialogW
0x1801afb3d  nop     dword ptr [rax+rax+00h]
0x1801afb42  jmp     loc_1801AF8AB
0x1801afb47  call    Windows__Internal__ComTaskPool__QueueTask__lambda_dfbd53f5f9ebc03a625422e6d886e0a8___
0x1801afb4c  jmp     loc_1801AF8AB
0x18067067c  mov     r8d, [r14+4]; unsigned int
0x180670680  add     rcx, 0FFFFFFFFFFFFFFC8h; this
0x180670684  mov     rdx, r10; HWND
0x180670687  call    ?_Delete@CRegFolder@@AEAAXPEAUHWND__@@IPEAUIDataObject@@@Z; CRegFolder::_Delete(HWND__ *,uint,IDataObject *)
0x18067068c  nop
0x18067068d  jmp     loc_1801AF8AB
```
