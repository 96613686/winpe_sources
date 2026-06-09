# CThemeManager2::_InstallRoamingThemePack(ushort const *,_GUID const &,THEMETYPE,int,IStream *)

- ea: `0x1800560f4`
- end: `0x180056373`
- name: `?_InstallRoamingThemePack@CThemeManager2@@AEAAJPEBGAEBU_GUID@@W4THEMETYPE@@HPEAUIStream@@@Z`
- size: `639`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x180054390`

## callees

- `0x18000b328`
- `0x1800358c0`
- `0x18003633c`
- `0x180042f84`
- `0x1800535e8`
- `0x180055c54`
- `0x180055f4c`
- `0x1800560f4`
- `0x18006d010`

## import_xrefs

- `SHCORE!SHCreateStreamOnFileEx` at `0x180056251`
- `SHCORE!SHCreateStreamOnFileEx` at `0x180056251`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005633e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005633e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180056334`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180056334`
- `OLEAUT32!__imp_SysFreeString` at `0x1800561f8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800561f8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CThemeManager2::_InstallRoamingThemePack(
        CThemeManager2 *a1,
        const unsigned __int16 *a2,
        __int64 a3,
        int a4,
        int a5,
        __int64 a6)
{
  const struct _GUID *v9; // r10
  HRESULT ThemeById; // ebx
  int v11; // edx
  CThemeManager2 *v12; // rcx
  BSTR v13; // r8
  int v14; // r8d
  LPCWSTR pszFile; // [rsp+40h] [rbp-59h] BYREF
  BSTR bstrString; // [rsp+48h] [rbp-51h] BYREF
  struct ITheme *v18[2]; // [rsp+50h] [rbp-49h] BYREF
  _BYTE v19[16]; // [rsp+60h] [rbp-39h] BYREF
  __int64 v20; // [rsp+70h] [rbp-29h]

  ATL::CComPtr<IInitializeWithFile>::CComPtr<IInitializeWithFile>(v18);
  ThemeById = CThemeManager2::_FindThemeById(a1, v9, v18);
  if ( ThemeById >= 0 )
  {
    if ( (unsigned __int8)ATL::CComPtrBase<ITheme>::operator!=(v18, 0)
      && (LODWORD(pszFile) = v11,
          (*(int (__fastcall **)(struct ITheme *, LPCWSTR *))(*(_QWORD *)v18[0] + 264LL))(v18[0], &pszFile) >= 0)
      && (_DWORD)pszFile )
    {
      bstrString = 0;
      ThemeById = (*(__int64 (__fastcall **)(struct ITheme *, __int64, BSTR *))(*(_QWORD *)v18[0] + 288LL))(
                    v18[0],
                    0xFFFFFFFFLL,
                    &bstrString);
      if ( ThemeById >= 0 )
      {
        *((_DWORD *)a1 + 552) = 0;
        v13 = (BSTR)&Default;
        if ( bstrString )
          v13 = bstrString;
        ThemeById = (*(__int64 (__fastcall **)(CThemeManager2 *, _QWORD, BSTR, _QWORD))(*(_QWORD *)a1 + 152LL))(
                      a1,
                      0,
                      v13,
                      (unsigned int)(a5 != 0) + 5);
      }
      SysFreeString(bstrString);
    }
    else
    {
      pszFile = 0;
      ThemeById = CThemeManager2::_GetThemepackFilePath(v12, a2, (unsigned __int16 **)&pszFile);
      if ( ThemeById >= 0 )
      {
        bstrString = 0;
        ThemeById = SHCreateStreamOnFileEx(pszFile, 0x1001u, 0x80u, 1, 0, (IStream **)&bstrString);
        if ( ThemeById >= 0 )
        {
          memset_0(v19, 0, 0x50u);
          ThemeById = (*(__int64 (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a6 + 96LL))(a6, v19, 1);
          if ( ThemeById >= 0 )
          {
            ThemeById = (*(__int64 (__fastcall **)(__int64, BSTR, __int64, _QWORD, _QWORD))(*(_QWORD *)a6 + 56LL))(
                          a6,
                          bstrString,
                          v20,
                          0,
                          0);
            if ( ThemeById >= 0 )
              ThemeById = (*(__int64 (__fastcall **)(BSTR, _QWORD))(*(_QWORD *)bstrString + 64LL))(bstrString, 0);
          }
          (*(void (__fastcall **)(BSTR))(*(_QWORD *)bstrString + 16LL))(bstrString);
          if ( ThemeById >= 0 )
          {
            v14 = 8;
            if ( (unsigned int)(a4 - 1) > 1 )
              v14 = 0;
            ThemeById = (*(__int64 (__fastcall **)(CThemeManager2 *, _QWORD, LPCWSTR, __int64, unsigned int, _QWORD, _QWORD))(*(_QWORD *)a1 + 136LL))(
                          a1,
                          0,
                          pszFile,
                          1,
                          v14 | ((unsigned int)(a5 != 0) + 5),
                          0,
                          0);
          }
        }
        DeleteFileW(pszFile);
        CoTaskMemFree((LPVOID)pszFile);
      }
    }
  }
  ATL::CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>::~CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>(v18);
  return (unsigned int)ThemeById;
}

```

## disassembly

```asm
0x1800560f4  mov     [rsp-8+arg_10], rbx
0x1800560f9  push    rbp
0x1800560fa  push    rsi
0x1800560fb  push    rdi
0x1800560fc  push    r14
0x1800560fe  push    r15
0x180056100  lea     rbp, [rsp-27h]
0x180056105  sub     rsp, 0C0h
0x18005610c  mov     rax, cs:__security_cookie
0x180056113  xor     rax, rsp
0x180056116  mov     [rbp+47h+var_30], rax
0x18005611a  mov     r15d, r9d
0x18005611d  mov     r10, r8
0x180056120  mov     r14, rdx
0x180056123  mov     rsi, rcx
0x180056126  mov     rdi, [rbp+47h+arg_28]
0x18005612a  lea     rcx, [rbp+47h+var_90]
0x18005612e  call    ??0?$CComPtr@UIInitializeWithFile@@@ATL@@QEAA@XZ; ATL::CComPtr<IInitializeWithFile>::CComPtr<IInitializeWithFile>(void)
0x180056133  nop
0x180056134  lea     r8, [rbp+47h+var_90]; struct ITheme **
0x180056138  mov     rdx, r10; struct _GUID *
0x18005613b  mov     rcx, rsi; this
0x18005613e  call    ?_FindThemeById@CThemeManager2@@AEAAJAEBU_GUID@@PEAPEAUITheme@@@Z; CThemeManager2::_FindThemeById(_GUID const &,ITheme * *)
0x180056143  mov     ebx, eax
0x180056145  test    eax, eax
0x180056147  js      loc_180056345
0x18005614d  xor     edx, edx
0x18005614f  lea     rcx, [rbp+47h+var_90]
0x180056153  call    ??9?$CComPtrBase@UITheme@@@ATL@@QEBA_NPEAUITheme@@@Z; ATL::CComPtrBase<ITheme>::operator!=(ITheme *)
0x180056158  test    al, al
0x18005615a  jz      loc_180056203
0x180056160  mov     rcx, [rbp+47h+var_90]
0x180056164  mov     dword ptr [rbp+47h+pszFile], edx
0x180056167  mov     rax, [rcx]
0x18005616a  lea     rdx, [rbp+47h+pszFile]
0x18005616e  mov     rax, [rax+108h]
0x180056175  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005617a  test    eax, eax
0x18005617c  js      loc_180056203
0x180056182  cmp     dword ptr [rbp+47h+pszFile], 0
0x180056186  jz      short loc_180056203
0x180056188  mov     [rbp+47h+bstrString], 0
0x180056190  mov     rcx, [rbp+47h+var_90]
0x180056194  mov     rax, [rcx]
0x180056197  or      edx, 0FFFFFFFFh
0x18005619a  lea     r8, [rbp+47h+bstrString]
0x18005619e  mov     rax, [rax+120h]
0x1800561a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800561aa  mov     ebx, eax
0x1800561ac  test    eax, eax
0x1800561ae  js      short loc_1800561F4
0x1800561b0  mov     dword ptr [rsi+8A0h], 0
0x1800561ba  mov     rax, [rsi]
0x1800561bd  mov     r10, [rax+98h]
0x1800561c4  mov     eax, [rbp+47h+arg_20]
0x1800561c7  neg     eax
0x1800561c9  sbb     r9d, r9d
0x1800561cc  neg     r9d
0x1800561cf  add     r9d, 5
0x1800561d3  lea     r8, Default
0x1800561da  mov     rdx, [rbp+47h+bstrString]
0x1800561de  test    rdx, rdx
0x1800561e1  cmovnz  r8, rdx
0x1800561e5  xor     edx, edx
0x1800561e7  mov     rcx, rsi
0x1800561ea  mov     rax, r10
0x1800561ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800561f2  mov     ebx, eax
0x1800561f4  mov     rcx, [rbp+47h+bstrString]; bstrString
0x1800561f8  call    cs:__imp_SysFreeString
0x1800561fe  jmp     loc_180056345
0x180056203  mov     [rbp+47h+pszFile], 0
0x18005620b  lea     r8, [rbp+47h+pszFile]; unsigned __int16 **
0x18005620f  mov     rdx, r14; unsigned __int16 *
0x180056212  call    ?_GetThemepackFilePath@CThemeManager2@@AEAAJPEBGPEAPEAG@Z; CThemeManager2::_GetThemepackFilePath(ushort const *,ushort * *)
0x180056217  mov     ebx, eax
0x180056219  test    eax, eax
0x18005621b  js      loc_180056345
0x180056221  mov     [rbp+47h+bstrString], 0
0x180056229  lea     rax, [rbp+47h+bstrString]
0x18005622d  mov     [rsp+0E0h+ppstm], rax; ppstm
0x180056232  mov     [rsp+0E0h+pstmTemplate], 0; pstmTemplate
0x18005623b  mov     r14d, 1
0x180056241  mov     r9d, r14d; fCreate
0x180056244  mov     edx, 1001h; grfMode
0x180056249  lea     r8d, [r14+7Fh]; dwAttributes
0x18005624d  mov     rcx, [rbp+47h+pszFile]; pszFile
0x180056251  call    cs:__imp_SHCreateStreamOnFileEx
0x180056257  mov     ebx, eax
0x180056259  test    eax, eax
0x18005625b  js      loc_180056330
0x180056261  xor     edx, edx; Val
0x180056263  lea     r8d, [r14+4Fh]; Size
0x180056267  lea     rcx, [rbp+47h+var_80]; void *
0x18005626b  call    memset_0
0x180056270  mov     rax, [rdi]
0x180056273  mov     r8d, r14d
0x180056276  lea     rdx, [rbp+47h+var_80]
0x18005627a  mov     rcx, rdi
0x18005627d  mov     rax, [rax+60h]
0x180056281  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056286  mov     ebx, eax
0x180056288  test    eax, eax
0x18005628a  js      short loc_1800562C9
0x18005628c  mov     rax, [rdi]
0x18005628f  mov     [rsp+0E0h+pstmTemplate], 0
0x180056298  xor     r9d, r9d
0x18005629b  mov     r8, [rbp+47h+var_70]
0x18005629f  mov     rdx, [rbp+47h+bstrString]
0x1800562a3  mov     rcx, rdi
0x1800562a6  mov     rax, [rax+38h]
0x1800562aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800562af  mov     ebx, eax
0x1800562b1  test    eax, eax
0x1800562b3  js      short loc_1800562C9
0x1800562b5  mov     rcx, [rbp+47h+bstrString]
0x1800562b9  mov     rax, [rcx]
0x1800562bc  xor     edx, edx
0x1800562be  mov     rax, [rax+40h]
0x1800562c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800562c7  mov     ebx, eax
0x1800562c9  mov     rcx, [rbp+47h+bstrString]
0x1800562cd  mov     rax, [rcx]
0x1800562d0  mov     rax, [rax+10h]
0x1800562d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800562d9  test    ebx, ebx
0x1800562db  js      short loc_180056330
0x1800562dd  lea     ecx, [r15-1]
0x1800562e1  xor     eax, eax
0x1800562e3  lea     r8d, [rax+8]
0x1800562e7  cmp     ecx, r14d
0x1800562ea  cmova   r8d, eax
0x1800562ee  mov     rcx, [rsi]
0x1800562f1  mov     eax, [rbp+47h+arg_20]
0x1800562f4  neg     eax
0x1800562f6  sbb     edx, edx
0x1800562f8  neg     edx
0x1800562fa  add     edx, 5
0x1800562fd  or      edx, r8d
0x180056300  mov     rax, [rcx+88h]
0x180056307  mov     [rsp+0E0h+var_B0], 0
0x180056310  mov     [rsp+0E0h+ppstm], 0
0x180056319  mov     dword ptr [rsp+0E0h+pstmTemplate], edx
0x18005631d  mov     r9d, r14d
0x180056320  mov     r8, [rbp+47h+pszFile]
0x180056324  xor     edx, edx
0x180056326  mov     rcx, rsi
0x180056329  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005632e  mov     ebx, eax
0x180056330  mov     rcx, [rbp+47h+pszFile]; lpFileName
0x180056334  call    cs:__imp_DeleteFileW
0x18005633a  mov     rcx, [rbp+47h+pszFile]; pv
0x18005633e  call    cs:__imp_CoTaskMemFree
0x180056344  nop
0x180056345  lea     rcx, [rbp+47h+var_90]
0x180056349  call    ??1?$CComQIPtr@UIShellItemImageFactoryPriv@@$1?_GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc@@3U__s_GUID@@B@ATL@@QEAA@XZ; ATL::CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>::~CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>(void)
0x18005634e  mov     eax, ebx
0x180056350  mov     rcx, [rbp+47h+var_30]
0x180056354  xor     rcx, rsp; StackCookie
0x180056357  call    __security_check_cookie
0x18005635c  mov     rbx, [rsp+0E0h+arg_10]
0x180056364  add     rsp, 0C0h
0x18005636b  pop     r15
0x18005636d  pop     r14
0x18005636f  pop     rdi
0x180056370  pop     rsi
0x180056371  pop     rbp
0x180056372  retn
```
