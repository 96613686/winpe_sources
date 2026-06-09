# CThemePack::_AdjustImageForRoamingTheme(ushort const *,uint,ushort * *,ulong *)

- ea: `0x18006735c`
- end: `0x180067567`
- name: `?_AdjustImageForRoamingTheme@CThemePack@@AEAAJPEBGIPEAPEAGPEAK@Z`
- size: `523`
- prototype: `int(CThemePack *__hidden this, const unsigned __int16 *, unsigned int, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180067570`

## callees

- `0x18000b328`
- `0x180042f84`
- `0x1800535f8`
- `0x180053604`
- `0x1800571c4`
- `0x180065c5c`
- `0x180065cd8`
- `0x18006735c`
- `0x18006760c`
- `0x18006d010`

## import_xrefs

- `SHCORE!IStream_Reset` at `0x180067478`
- `SHCORE!IStream_Reset` at `0x180067478`
- `SHCORE!SHCreateStreamOnFileEx` at `0x1800673bc`
- `SHCORE!SHCreateStreamOnFileEx` at `0x1800673bc`
- `SHCORE!SHStrDupW` at `0x1800674dc`
- `SHCORE!SHStrDupW` at `0x1800674dc`
- `SHCORE!IStream_Size` at `0x1800674bc`
- `SHCORE!IStream_Size` at `0x180067516`
- `SHCORE!IStream_Size` at `0x1800674bc`
- `SHCORE!IStream_Size` at `0x180067516`
- `SHLWAPI!PathFindFileNameW` at `0x18006748d`
- `SHLWAPI!PathFindFileNameW` at `0x18006748d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800674f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800674f1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800673f7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800673f7`

## pseudocode

```c
__int64 __fastcall CThemePack::_AdjustImageForRoamingTheme(
        CThemePack *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned __int16 **a4,
        IStream *a5)
{
  IStream *v5; // rdi
  IStream **ppstm; // rax
  HRESULT Instance; // ebx
  LPVOID *v11; // rax
  __int64 v12; // rax
  struct IStream *v13; // rbx
  const unsigned __int16 *FileNameW; // rax
  CThemePack *v15; // rcx
  LPCWSTR psz; // [rsp+40h] [rbp-10h] BYREF
  _BYTE v18[8]; // [rsp+48h] [rbp-8h] BYREF
  IStream *pstm; // [rsp+80h] [rbp+30h] BYREF
  ULARGE_INTEGER pui; // [rsp+98h] [rbp+48h] BYREF

  pstm = this;
  v5 = a5;
  *a4 = 0;
  *(_DWORD *)v5 = 0;
  ATL::CComPtr<IInitializeWithFile>::CComPtr<IInitializeWithFile>(&a5);
  ppstm = (IStream **)ATL::CComPtrBase<ITheme>::operator&(&a5);
  Instance = SHCreateStreamOnFileEx(a2, 0x20u, 0x80u, 0, 0, ppstm);
  if ( Instance >= 0 )
  {
    ATL::CComPtr<IInitializeWithFile>::CComPtr<IInitializeWithFile>(v18);
    v11 = (LPVOID *)ATL::CComPtrBase<ITheme>::operator&(v18);
    Instance = CoCreateInstance(&CLSID_ImageProcessorForRoaming, 0, 1u, &GUID_d14e769b_4502_48a7_99af_0fc558ef35c7, v11);
    if ( Instance >= 0 )
    {
      ATL::CComPtr<IInitializeWithFile>::CComPtr<IInitializeWithFile>(&pstm);
      v12 = ATL::CComPtrBase<IImageProcessorForRoaming>::operator->(v18);
      Instance = (*(__int64 (__fastcall **)(__int64, IStream *, __int64, _QWORD, int, int, IStream **))(*(_QWORD *)v12 + 24LL))(
                   v12,
                   a5,
                   4096000,
                   a3,
                   80,
                   3,
                   &pstm);
      if ( Instance >= 0 )
      {
        if ( (unsigned __int8)ATL::CComPtrBase<IStream>::operator!=(&pstm) )
        {
          psz = 0;
          IStream_Reset(pstm);
          v13 = (struct IStream *)ATL::CComPtrBase<IImageProcessorForRoaming>::operator->(&pstm);
          FileNameW = PathFindFileNameW(a2);
          Instance = CThemePack::_CopyStreamToTempFile(v15, FileNameW, v13, (unsigned __int16 **)&psz);
          if ( Instance >= 0 )
          {
            pui.QuadPart = 0;
            Instance = IStream_Size(pstm, &pui);
            if ( Instance >= 0 )
            {
              if ( pui.HighPart )
              {
                Instance = -2147023604;
              }
              else
              {
                Instance = SHStrDupW(psz, a4);
                if ( Instance >= 0 )
                  *(_DWORD *)v5 = pui.LowPart;
              }
            }
            CoTaskMemFree((LPVOID)psz);
          }
        }
        else if ( (unsigned __int8)ATL::CComPtrBase<IStream>::operator==(&pstm) )
        {
          pui.QuadPart = 0;
          Instance = IStream_Size(a5, &pui);
          if ( Instance >= 0 )
          {
            if ( pui.HighPart )
            {
              Instance = -2147023604;
            }
            else
            {
              Instance = 0;
              *(_DWORD *)v5 = pui.LowPart;
            }
          }
        }
      }
      ATL::CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>::~CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>(&pstm);
    }
    ATL::CComPtr<IImageProcessorForRoaming>::~CComPtr<IImageProcessorForRoaming>(v18);
  }
  ATL::CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>::~CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>(&a5);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18006735c  mov     [rsp-28h+arg_8], rbx
0x180067361  mov     [rsp-28h+pstm], rcx
0x180067366  push    rbp
0x180067367  push    rsi
0x180067368  push    rdi
0x180067369  push    r14
0x18006736b  push    r15
0x18006736d  mov     rbp, rsp
0x180067370  sub     rsp, 50h
0x180067374  mov     rdi, [rbp+arg_20]
0x180067378  lea     rcx, [rbp+arg_20]
0x18006737c  mov     rsi, r9
0x18006737f  mov     qword ptr [r9], 0
0x180067386  mov     r15d, r8d
0x180067389  mov     r14, rdx
0x18006738c  mov     dword ptr [rdi], 0
0x180067392  call    ??0?$CComPtr@UIInitializeWithFile@@@ATL@@QEAA@XZ; ATL::CComPtr<IInitializeWithFile>::CComPtr<IInitializeWithFile>(void)
0x180067397  lea     rcx, [rbp+arg_20]
0x18006739b  call    ??I?$CComPtrBase@UITheme@@@ATL@@QEAAPEAPEAUITheme@@XZ; ATL::CComPtrBase<ITheme>::operator&(void)
0x1800673a0  xor     r9d, r9d; fCreate
0x1800673a3  mov     [rsp+50h+ppstm], rax; ppstm
0x1800673a8  mov     rcx, r14; pszFile
0x1800673ab  mov     [rsp+50h+pstmTemplate], 0; pstmTemplate
0x1800673b4  lea     edx, [r9+20h]; grfMode
0x1800673b8  lea     r8d, [rdx+60h]; dwAttributes
0x1800673bc  call    cs:__imp_SHCreateStreamOnFileEx
0x1800673c2  mov     ebx, eax
0x1800673c4  test    eax, eax
0x1800673c6  js      loc_180067548
0x1800673cc  lea     rcx, [rbp+var_8]
0x1800673d0  call    ??0?$CComPtr@UIInitializeWithFile@@@ATL@@QEAA@XZ; ATL::CComPtr<IInitializeWithFile>::CComPtr<IInitializeWithFile>(void)
0x1800673d5  lea     rcx, [rbp+var_8]
0x1800673d9  call    ??I?$CComPtrBase@UITheme@@@ATL@@QEAAPEAPEAUITheme@@XZ; ATL::CComPtrBase<ITheme>::operator&(void)
0x1800673de  xor     edx, edx; pUnkOuter
0x1800673e0  mov     [rsp+50h+pstmTemplate], rax; ppv
0x1800673e5  lea     r9, _GUID_d14e769b_4502_48a7_99af_0fc558ef35c7; riid
0x1800673ec  lea     rcx, CLSID_ImageProcessorForRoaming; rclsid
0x1800673f3  lea     r8d, [rdx+1]; dwClsContext
0x1800673f7  call    cs:__imp_CoCreateInstance
0x1800673fd  mov     ebx, eax
0x1800673ff  test    eax, eax
0x180067401  js      loc_18006753F
0x180067407  lea     rcx, [rbp+pstm]
0x18006740b  call    ??0?$CComPtr@UIInitializeWithFile@@@ATL@@QEAA@XZ; ATL::CComPtr<IInitializeWithFile>::CComPtr<IInitializeWithFile>(void)
0x180067410  lea     rcx, [rbp+var_8]
0x180067414  call    ??C?$CComPtrBase@UIImageProcessorForRoaming@@@ATL@@QEBAPEAV?$_NoAddRefReleaseOnCComPtr@UIImageProcessorForRoaming@@@1@XZ; ATL::CComPtrBase<IImageProcessorForRoaming>::operator->(void)
0x180067419  mov     rdx, [rbp+arg_20]
0x18006741d  mov     r10, rax
0x180067420  mov     r9d, r15d
0x180067423  mov     r8d, 3E8000h
0x180067429  mov     rcx, [rax]
0x18006742c  mov     rax, [rcx+18h]
0x180067430  lea     rcx, [rbp+pstm]
0x180067434  mov     [rsp+50h+var_20], rcx
0x180067439  mov     rcx, r10
0x18006743c  mov     dword ptr [rsp+50h+ppstm], 3
0x180067444  mov     dword ptr [rsp+50h+pstmTemplate], 50h ; 'P'
0x18006744c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067451  mov     ebx, eax
0x180067453  test    eax, eax
0x180067455  js      loc_180067536
0x18006745b  lea     rcx, [rbp+pstm]
0x18006745f  call    ??9?$CComPtrBase@UIStream@@@ATL@@QEBA_NPEAUIStream@@@Z; ATL::CComPtrBase<IStream>::operator!=(IStream *)
0x180067464  test    al, al
0x180067466  jz      loc_1800674F9
0x18006746c  mov     rcx, [rbp+pstm]; pstm
0x180067470  mov     [rbp+psz], 0
0x180067478  call    cs:__imp_IStream_Reset
0x18006747e  lea     rcx, [rbp+pstm]
0x180067482  call    ??C?$CComPtrBase@UIImageProcessorForRoaming@@@ATL@@QEBAPEAV?$_NoAddRefReleaseOnCComPtr@UIImageProcessorForRoaming@@@1@XZ; ATL::CComPtrBase<IImageProcessorForRoaming>::operator->(void)
0x180067487  mov     rcx, r14; pszPath
0x18006748a  mov     rbx, rax
0x18006748d  call    cs:__imp_PathFindFileNameW
0x180067493  lea     r9, [rbp+psz]; unsigned __int16 **
0x180067497  mov     r8, rbx; struct IStream *
0x18006749a  mov     rdx, rax; unsigned __int16 *
0x18006749d  call    ?_CopyStreamToTempFile@CThemePack@@AEAAJPEBGPEAUIStream@@PEAPEAG@Z; CThemePack::_CopyStreamToTempFile(ushort const *,IStream *,ushort * *)
0x1800674a2  mov     ebx, eax
0x1800674a4  test    eax, eax
0x1800674a6  js      loc_180067536
0x1800674ac  mov     rcx, [rbp+pstm]; pstm
0x1800674b0  lea     rdx, [rbp+pui]; pui
0x1800674b4  mov     qword ptr [rbp+pui], 0
0x1800674bc  call    cs:__imp_IStream_Size
0x1800674c2  mov     ebx, eax
0x1800674c4  test    eax, eax
0x1800674c6  js      short loc_1800674ED
0x1800674c8  cmp     dword ptr [rbp+pui+4], 0
0x1800674cc  jz      short loc_1800674D5
0x1800674ce  mov     ebx, 8007050Ch
0x1800674d3  jmp     short loc_1800674ED
0x1800674d5  mov     rcx, [rbp+psz]; psz
0x1800674d9  mov     rdx, rsi; ppwsz
0x1800674dc  call    cs:__imp_SHStrDupW
0x1800674e2  mov     ebx, eax
0x1800674e4  test    eax, eax
0x1800674e6  js      short loc_1800674ED
0x1800674e8  mov     eax, dword ptr [rbp+pui]
0x1800674eb  mov     [rdi], eax
0x1800674ed  mov     rcx, [rbp+psz]; pv
0x1800674f1  call    cs:__imp_CoTaskMemFree
0x1800674f7  jmp     short loc_180067536
0x1800674f9  lea     rcx, [rbp+pstm]
0x1800674fd  call    ??8?$CComPtrBase@UIStream@@@ATL@@QEBA_NPEAUIStream@@@Z; ATL::CComPtrBase<IStream>::operator==(IStream *)
0x180067502  test    al, al
0x180067504  jz      short loc_180067536
0x180067506  mov     rcx, [rbp+arg_20]; pstm
0x18006750a  lea     rdx, [rbp+pui]; pui
0x18006750e  mov     qword ptr [rbp+pui], 0
0x180067516  call    cs:__imp_IStream_Size
0x18006751c  mov     ebx, eax
0x18006751e  test    eax, eax
0x180067520  js      short loc_180067536
0x180067522  cmp     dword ptr [rbp+pui+4], 0
0x180067526  jnz     short loc_180067531
0x180067528  mov     eax, dword ptr [rbp+pui]
0x18006752b  xor     ebx, ebx
0x18006752d  mov     [rdi], eax
0x18006752f  jmp     short loc_180067536
0x180067531  mov     ebx, 8007050Ch
0x180067536  lea     rcx, [rbp+pstm]
0x18006753a  call    ??1?$CComQIPtr@UIShellItemImageFactoryPriv@@$1?_GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc@@3U__s_GUID@@B@ATL@@QEAA@XZ; ATL::CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>::~CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>(void)
0x18006753f  lea     rcx, [rbp+var_8]
0x180067543  call    ??1?$CComPtr@UIImageProcessorForRoaming@@@ATL@@QEAA@XZ; ATL::CComPtr<IImageProcessorForRoaming>::~CComPtr<IImageProcessorForRoaming>(void)
0x180067548  lea     rcx, [rbp+arg_20]
0x18006754c  call    ??1?$CComQIPtr@UIShellItemImageFactoryPriv@@$1?_GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc@@3U__s_GUID@@B@ATL@@QEAA@XZ; ATL::CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>::~CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>(void)
0x180067551  mov     eax, ebx
0x180067553  mov     rbx, [rsp+50h+arg_8]
0x18006755b  add     rsp, 50h
0x18006755f  pop     r15
0x180067561  pop     r14
0x180067563  pop     rdi
0x180067564  pop     rsi
0x180067565  pop     rbp
0x180067566  retn
```
