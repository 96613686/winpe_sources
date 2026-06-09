# CThemeManager2::_WriteCustomThemeToPropStore(ushort const *,_GUID const &,ushort const *,IPropertyStore *)

- ea: `0x180056a04`
- end: `0x180056c44`
- name: `?_WriteCustomThemeToPropStore@CThemeManager2@@AEAAJPEBGAEBU_GUID@@0PEAUIPropertyStore@@@Z`
- size: `576`
- prototype: `int(CThemeManager2 *__hidden this, const unsigned __int16 *, const struct _GUID *, const unsigned __int16 *, struct IPropertyStore *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180056d14`

## callees

- `0x18000b328`
- `0x18000ed70`
- `0x1800358c0`
- `0x180042f84`
- `0x180056a04`
- `0x180061de8`
- `0x180061e78`
- `0x18006d010`

## import_xrefs

- `SHCORE!SHCreateStreamOnFileEx` at `0x180056bc9`
- `SHCORE!SHCreateStreamOnFileEx` at `0x180056bc9`
- `SHELL32!SHGetFolderPathEx` at `0x180056b17`
- `SHELL32!SHGetFolderPathEx` at `0x180056b17`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180056ae8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180056b4e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180056ae8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180056b4e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180056ab7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180056ab7`
- `PROPSYS!InitPropVariantFromCLSID` at `0x180056a85`
- `PROPSYS!InitPropVariantFromCLSID` at `0x180056a85`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CThemeManager2::_WriteCustomThemeToPropStore(
        const WCHAR *this,
        const unsigned __int16 *a2,
        const struct _GUID *a3,
        const unsigned __int16 *a4,
        struct IPropertyStore *a5)
{
  __int64 v9; // rdx
  HRESULT inited; // ebx
  int v11; // ebx
  PROPVARIANT ppropvar[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v14; // [rsp+40h] [rbp-C0h]
  IStream *ppstm; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR String1[264]; // [rsp+50h] [rbp-B0h] BYREF

  inited = IPropertyStore_SetInt(a5, a2, 0);
  if ( inited >= 0 )
  {
    inited = IPropertyStore_SetString(a5, v9, a2);
    if ( inited >= 0 )
    {
      *(_OWORD *)ppropvar = 0;
      v14 = 0;
      inited = InitPropVariantFromCLSID(a3, ppropvar);
      if ( inited >= 0 )
      {
        inited = ((__int64 (__fastcall *)(struct IPropertyStore *, __int64 *, PROPVARIANT *))a5->lpVtbl->SetValue)(
                   a5,
                   qword_18007A818,
                   ppropvar);
        PropVariantClear(ppropvar);
        if ( inited >= 0 )
        {
          if ( CompareStringOrdinal(this + 266, -1, this + 6, -1, 1) == 2 )
          {
            v11 = 1;
          }
          else
          {
            v11 = 0;
            if ( (int)SHGetFolderPathEx(&FOLDERID_LocalAppData, 0, 0, String1, 260) >= 0
              && (int)StringCchCatW(String1, 0x104u, L"\\Microsoft\\Windows\\Themes\\Roamed.theme") >= 0
              && CompareStringOrdinal(String1, -1, this + 6, -1, 1) == 2 )
            {
              v11 = 2;
            }
          }
          *(_OWORD *)ppropvar = 0;
          v14 = 0;
          LOWORD(ppropvar[0]) = 19;
          LODWORD(ppropvar[1]) = v11;
          inited = ((__int64 (__fastcall *)(struct IPropertyStore *, __int64 *, PROPVARIANT *))a5->lpVtbl->SetValue)(
                     a5,
                     qword_18007A7B8,
                     ppropvar);
          if ( inited >= 0 )
          {
            ATL::CComPtr<IInitializeWithFile>::CComPtr<IInitializeWithFile>(&ppstm);
            inited = SHCreateStreamOnFileEx(a4, 0x20u, 0x80u, 0, 0, &ppstm);
            if ( inited >= 0 )
            {
              ppropvar[0] = (PROPVARIANT)13;
              v14 = 0;
              ppropvar[1] = ppstm;
              inited = ((__int64 (__fastcall *)(struct IPropertyStore *, __int64 *, PROPVARIANT *))a5->lpVtbl->SetValue)(
                         a5,
                         qword_18007A7E8,
                         ppropvar);
            }
            ATL::CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>::~CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>(&ppstm);
          }
        }
      }
    }
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180056a04  push    rbp
0x180056a06  push    rbx
0x180056a07  push    rsi
0x180056a08  push    rdi
0x180056a09  push    r12
0x180056a0b  push    r13
0x180056a0d  push    r14
0x180056a0f  push    r15
0x180056a11  lea     rbp, [rsp-178h]
0x180056a19  sub     rsp, 278h
0x180056a20  mov     rax, cs:__security_cookie
0x180056a27  xor     rax, rsp
0x180056a2a  mov     [rbp+1B0h+var_50], rax
0x180056a31  mov     r12, r9
0x180056a34  mov     r15, r8
0x180056a37  mov     rsi, rdx
0x180056a3a  mov     r14, rcx
0x180056a3d  mov     rdi, [rbp+1B0h+arg_20]
0x180056a44  xor     r8d, r8d
0x180056a47  mov     rcx, rdi
0x180056a4a  call    IPropertyStore_SetInt
0x180056a4f  mov     ebx, eax
0x180056a51  test    eax, eax
0x180056a53  js      loc_180056C1F
0x180056a59  mov     r8, rsi
0x180056a5c  mov     rcx, rdi
0x180056a5f  call    IPropertyStore_SetString
0x180056a64  mov     ebx, eax
0x180056a66  test    eax, eax
0x180056a68  js      loc_180056C1F
0x180056a6e  xorps   xmm0, xmm0
0x180056a71  xor     eax, eax
0x180056a73  movups  xmmword ptr [rsp+2B0h+ppropvar], xmm0
0x180056a78  mov     [rsp+2B0h+var_270], rax
0x180056a7d  lea     rdx, [rsp+2B0h+ppropvar]; ppropvar
0x180056a82  mov     rcx, r15; clsid
0x180056a85  call    cs:__imp_InitPropVariantFromCLSID
0x180056a8b  mov     ebx, eax
0x180056a8d  test    eax, eax
0x180056a8f  js      loc_180056C1F
0x180056a95  mov     rax, [rdi]
0x180056a98  lea     r8, [rsp+2B0h+ppropvar]
0x180056a9d  lea     rdx, qword_18007A818
0x180056aa4  mov     rcx, rdi
0x180056aa7  mov     rax, [rax+30h]
0x180056aab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056ab0  mov     ebx, eax
0x180056ab2  lea     rcx, [rsp+2B0h+ppropvar]; pvar
0x180056ab7  call    cs:__imp_PropVariantClear
0x180056abd  test    ebx, ebx
0x180056abf  js      loc_180056C1F
0x180056ac5  lea     rsi, [r14+0Ch]
0x180056ac9  lea     rcx, [r14+214h]; lpString1
0x180056ad0  mov     r14d, 1
0x180056ad6  mov     [rsp+2B0h+bIgnoreCase], r14d; bIgnoreCase
0x180056adb  or      r15d, 0FFFFFFFFh
0x180056adf  mov     r9d, r15d; cchCount2
0x180056ae2  mov     r8, rsi; lpString2
0x180056ae5  mov     edx, r15d; cchCount1
0x180056ae8  call    cs:__imp_CompareStringOrdinal
0x180056aee  lea     r13d, [r14+1]
0x180056af2  cmp     eax, r13d
0x180056af5  jnz     short loc_180056AFC
0x180056af7  mov     ebx, r14d
0x180056afa  jmp     short loc_180056B5B
0x180056afc  xor     ebx, ebx
0x180056afe  mov     [rsp+2B0h+bIgnoreCase], 104h
0x180056b06  lea     r9, [rsp+2B0h+String1]
0x180056b0b  xor     r8d, r8d
0x180056b0e  xor     edx, edx
0x180056b10  lea     rcx, FOLDERID_LocalAppData
0x180056b17  call    cs:__imp_SHGetFolderPathEx
0x180056b1d  test    eax, eax
0x180056b1f  js      short loc_180056B5B
0x180056b21  lea     r8, aMicrosoftWindo_1; "\\Microsoft\\Windows\\Themes\\Roamed.th"...
0x180056b28  mov     edx, 104h; unsigned __int64
0x180056b2d  lea     rcx, [rsp+2B0h+String1]; unsigned __int16 *
0x180056b32  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180056b37  test    eax, eax
0x180056b39  js      short loc_180056B5B
0x180056b3b  mov     [rsp+2B0h+bIgnoreCase], r14d; bIgnoreCase
0x180056b40  mov     r9d, r15d; cchCount2
0x180056b43  mov     r8, rsi; lpString2
0x180056b46  mov     edx, r15d; cchCount1
0x180056b49  lea     rcx, [rsp+2B0h+String1]; lpString1
0x180056b4e  call    cs:__imp_CompareStringOrdinal
0x180056b54  cmp     eax, r13d
0x180056b57  cmovz   ebx, r13d
0x180056b5b  xorps   xmm0, xmm0
0x180056b5e  xor     eax, eax
0x180056b60  movups  xmmword ptr [rsp+2B0h+ppropvar], xmm0
0x180056b65  mov     [rsp+2B0h+var_270], rax
0x180056b6a  mov     eax, 13h
0x180056b6f  mov     word ptr [rsp+2B0h+ppropvar], ax
0x180056b74  mov     dword ptr [rsp+2B0h+ppropvar+8], ebx
0x180056b78  mov     rax, [rdi]
0x180056b7b  lea     r8, [rsp+2B0h+ppropvar]
0x180056b80  lea     rdx, qword_18007A7B8
0x180056b87  mov     rcx, rdi
0x180056b8a  mov     rax, [rax+30h]
0x180056b8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056b93  mov     ebx, eax
0x180056b95  test    eax, eax
0x180056b97  js      loc_180056C1F
0x180056b9d  lea     rcx, [rsp+2B0h+var_268]
0x180056ba2  call    ??0?$CComPtr@UIInitializeWithFile@@@ATL@@QEAA@XZ; ATL::CComPtr<IInitializeWithFile>::CComPtr<IInitializeWithFile>(void)
0x180056ba7  nop
0x180056ba8  lea     rax, [rsp+2B0h+var_268]
0x180056bad  mov     [rsp+2B0h+ppstm], rax; ppstm
0x180056bb2  mov     qword ptr [rsp+2B0h+bIgnoreCase], 0; pstmTemplate
0x180056bbb  xor     r9d, r9d; fCreate
0x180056bbe  lea     edx, [r9+20h]; grfMode
0x180056bc2  lea     r8d, [rdx+60h]; dwAttributes
0x180056bc6  mov     rcx, r12; pszFile
0x180056bc9  call    cs:__imp_SHCreateStreamOnFileEx
0x180056bcf  mov     ebx, eax
0x180056bd1  test    eax, eax
0x180056bd3  js      short loc_180056C15
0x180056bd5  xorps   xmm0, xmm0
0x180056bd8  xor     eax, eax
0x180056bda  movups  xmmword ptr [rsp+2B0h+ppropvar], xmm0
0x180056bdf  mov     [rsp+2B0h+var_270], rax
0x180056be4  mov     eax, 0Dh
0x180056be9  mov     word ptr [rsp+2B0h+ppropvar], ax
0x180056bee  mov     rax, [rsp+2B0h+var_268]
0x180056bf3  mov     [rsp+2B0h+ppropvar+8], rax
0x180056bf8  mov     rax, [rdi]
0x180056bfb  lea     r8, [rsp+2B0h+ppropvar]
0x180056c00  lea     rdx, qword_18007A7E8
0x180056c07  mov     rcx, rdi
0x180056c0a  mov     rax, [rax+30h]
0x180056c0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056c13  mov     ebx, eax
0x180056c15  lea     rcx, [rsp+2B0h+var_268]
0x180056c1a  call    ??1?$CComQIPtr@UIShellItemImageFactoryPriv@@$1?_GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc@@3U__s_GUID@@B@ATL@@QEAA@XZ; ATL::CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>::~CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>(void)
0x180056c1f  mov     eax, ebx
0x180056c21  mov     rcx, [rbp+1B0h+var_50]
0x180056c28  xor     rcx, rsp; StackCookie
0x180056c2b  call    __security_check_cookie
0x180056c30  add     rsp, 278h
0x180056c37  pop     r15
0x180056c39  pop     r14
0x180056c3b  pop     r13
0x180056c3d  pop     r12
0x180056c3f  pop     rdi
0x180056c40  pop     rsi
0x180056c41  pop     rbx
0x180056c42  pop     rbp
0x180056c43  retn
```
