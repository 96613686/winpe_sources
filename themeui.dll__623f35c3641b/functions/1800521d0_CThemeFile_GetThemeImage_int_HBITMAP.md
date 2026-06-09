# CThemeFile::GetThemeImage(int,HBITMAP__ * *)

- ea: `0x1800521d0`
- end: `0x180052452`
- name: `?GetThemeImage@CThemeFile@@UEAAJHPEAPEAUHBITMAP__@@@Z`
- size: `642`
- prototype: `__int64 __fastcall(CThemeFile *__hidden this, int, HBITMAP *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000b328`
- `0x180042f84`
- `0x18005196c`
- `0x18005199c`
- `0x1800521d0`
- `0x18006d010`

## import_xrefs

- `SHELL32!SHCreateItemFromIDList` at `0x180052280`
- `SHELL32!SHCreateItemFromIDList` at `0x180052280`
- `SHELL32!__imp_SHILCreateFromPath` at `0x180052257`
- `SHELL32!__imp_SHILCreateFromPath` at `0x180052257`
- `SHELL32!__imp_SHRestricted` at `0x1800522cb`
- `SHELL32!__imp_SHRestricted` at `0x1800522cb`
- `SHELL32!__imp_ILFree` at `0x18005234e`
- `SHELL32!__imp_ILFree` at `0x18005234e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005222a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005222a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005221c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005221c`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CThemeFile::GetThemeImage(PCWSTR *this, int a2, HBITMAP *a3)
{
  bool v6; // di
  _QWORD *v7; // r14
  HRESULT v8; // ebx
  __int64 v9; // r9
  LPVOID v11; // [rsp+40h] [rbp-20h] BYREF
  LPITEMIDLIST ppidl; // [rsp+48h] [rbp-18h] BYREF
  void *ppv[2]; // [rsp+50h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+A0h] [rbp+40h] BYREF
  LPVOID v15; // [rsp+A8h] [rbp+48h] BYREF

  *a3 = 0;
  hKey = 0;
  v6 = 1;
  if ( !RegOpenKeyExW(
          HKEY_CURRENT_USER,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\FileExts\\.theme\\UserChoice",
          0,
          1u,
          &hKey) )
  {
    RegCloseKey(hKey);
    v7 = this + 4;
LABEL_15:
    ATL::CComPtr<IInitializeWithFile>::CComPtr<IInitializeWithFile>(&v15);
    v8 = ATL::CComPtrBase<IThemeThumbnail>::CoCreateInstance(&v15);
    if ( v8 >= 0 )
    {
      ATL::CComPtr<IInitializeWithFile>::CComPtr<IInitializeWithFile>(&ppidl);
      v8 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, LPITEMIDLIST *))v15)(
             v15,
             &GUID_b7d14566_0509_4cce_a71f_0a554233bd9b,
             &ppidl);
      if ( v8 >= 0 )
      {
        v8 = (*(__int64 (__fastcall **)(LPITEMIDLIST, _QWORD, _QWORD))(*(_QWORD *)&ppidl->mkid.cb + 24LL))(
               ppidl,
               *v7,
               0);
        if ( v8 >= 0 )
        {
          ATL::CComPtr<IInitializeWithFile>::CComPtr<IInitializeWithFile>(ppv);
          v8 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, void **))v15)(
                 v15,
                 &GUID_e357fccd_a995_4576_b01f_234630154e96,
                 ppv);
          if ( v8 >= 0 )
          {
            LODWORD(hKey) = 0;
            v8 = (*(__int64 (__fastcall **)(void *, __int64, HBITMAP *, HKEY *))(*(_QWORD *)ppv[0] + 24LL))(
                   ppv[0],
                   256,
                   a3,
                   &hKey);
          }
          ATL::CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>::~CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>(ppv);
        }
      }
      ATL::CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>::~CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>(&ppidl);
    }
    ATL::CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>::~CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>(&v15);
    return (unsigned int)v8;
  }
  LODWORD(hKey) = 0;
  ppidl = 0;
  v7 = this + 4;
  v8 = SHILCreateFromPath(this[4], &ppidl, (DWORD *)&hKey);
  if ( v8 >= 0 )
  {
    ATL::CComPtr<IInitializeWithFile>::CComPtr<IInitializeWithFile>(ppv);
    v8 = SHCreateItemFromIDList(ppidl, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, ppv);
    if ( v8 >= 0 )
    {
      ATL::CComPtr<IInitializeWithFile>::CComPtr<IInitializeWithFile>(&v11);
      v8 = ATL::CComPtrBase<IThumbnailCache>::CoCreateInstance(&v11);
      if ( v8 >= 0 )
      {
        ATL::CComPtr<IInitializeWithFile>::CComPtr<IInitializeWithFile>(&v15);
        if ( a2 )
          v9 = 1;
        else
          v9 = SHRestricted(REST_NOTHUMBNAILCACHE) != 0 ? 32 : 4;
        v8 = (*(__int64 (__fastcall **)(LPVOID, void *, __int64, __int64, LPVOID *, _QWORD, _QWORD))(*(_QWORD *)v11 + 24LL))(
               v11,
               ppv[0],
               256,
               v9,
               &v15,
               0,
               0);
        if ( v8 < 0 )
          v6 = a2 != 0;
        else
          v8 = (*(__int64 (__fastcall **)(LPVOID, HBITMAP *))(*(_QWORD *)v15 + 56LL))(v15, a3);
        ATL::CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>::~CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>(&v15);
      }
      ATL::CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>::~CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>(&v11);
    }
    ILFree(ppidl);
    ATL::CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>::~CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>(ppv);
    if ( !v6 )
      goto LABEL_15;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800521d0  mov     [rsp-28h+arg_0], rbx
0x1800521d5  push    rbp
0x1800521d6  push    rsi
0x1800521d7  push    rdi
0x1800521d8  push    r14
0x1800521da  push    r15
0x1800521dc  mov     rbp, rsp
0x1800521df  sub     rsp, 60h
0x1800521e3  mov     r15, r8
0x1800521e6  mov     esi, edx
0x1800521e8  mov     rbx, rcx
0x1800521eb  mov     qword ptr [r8], 0
0x1800521f2  mov     [rbp+hKey], 0
0x1800521fa  lea     rax, [rbp+hKey]
0x1800521fe  mov     [rsp+60h+phkResult], rax; phkResult
0x180052203  mov     edi, 1
0x180052208  mov     r9d, edi; samDesired
0x18005220b  xor     r8d, r8d; ulOptions
0x18005220e  lea     rdx, aSoftwareMicros_6; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180052215  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18005221c  call    cs:__imp_RegOpenKeyExW
0x180052222  test    eax, eax
0x180052224  jnz     short loc_180052239
0x180052226  mov     rcx, [rbp+hKey]; hKey
0x18005222a  call    cs:__imp_RegCloseKey
0x180052230  lea     r14, [rbx+20h]
0x180052234  jmp     loc_180052367
0x180052239  mov     dword ptr [rbp+hKey], 0
0x180052240  mov     [rbp+ppidl], 0
0x180052248  lea     r14, [rbx+20h]
0x18005224c  lea     r8, [rbp+hKey]; rgfInOut
0x180052250  lea     rdx, [rbp+ppidl]; ppidl
0x180052254  mov     rcx, [r14]; pszPath
0x180052257  call    cs:__imp_SHILCreateFromPath
0x18005225d  mov     ebx, eax
0x18005225f  test    eax, eax
0x180052261  js      loc_18005243C
0x180052267  lea     rcx, [rbp+ppv]
0x18005226b  call    ??0?$CComPtr@UIInitializeWithFile@@@ATL@@QEAA@XZ; ATL::CComPtr<IInitializeWithFile>::CComPtr<IInitializeWithFile>(void)
0x180052270  nop
0x180052271  lea     r8, [rbp+ppv]; ppv
0x180052275  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18005227c  mov     rcx, [rbp+ppidl]; pidl
0x180052280  call    cs:__imp_SHCreateItemFromIDList
0x180052286  mov     ebx, eax
0x180052288  test    eax, eax
0x18005228a  js      loc_18005234A
0x180052290  lea     rcx, [rbp+var_20]
0x180052294  call    ??0?$CComPtr@UIInitializeWithFile@@@ATL@@QEAA@XZ; ATL::CComPtr<IInitializeWithFile>::CComPtr<IInitializeWithFile>(void)
0x180052299  nop
0x18005229a  mov     r9d, 17h
0x1800522a0  lea     rcx, [rbp+var_20]; ppv
0x1800522a4  call    ?CoCreateInstance@?$CComPtrBase@UIThumbnailCache@@@ATL@@QEAAJAEBU_GUID@@PEAUIUnknown@@K@Z; ATL::CComPtrBase<IThumbnailCache>::CoCreateInstance(_GUID const &,IUnknown *,ulong)
0x1800522a9  mov     ebx, eax
0x1800522ab  test    eax, eax
0x1800522ad  js      loc_180052341
0x1800522b3  lea     rcx, [rbp+arg_18]
0x1800522b7  call    ??0?$CComPtr@UIInitializeWithFile@@@ATL@@QEAA@XZ; ATL::CComPtr<IInitializeWithFile>::CComPtr<IInitializeWithFile>(void)
0x1800522bc  nop
0x1800522bd  test    esi, esi
0x1800522bf  jz      short loc_1800522C6
0x1800522c1  mov     r9d, edi
0x1800522c4  jmp     short loc_1800522DE
0x1800522c6  mov     ecx, 4000007Dh; rest
0x1800522cb  call    cs:__imp_SHRestricted
0x1800522d1  neg     eax
0x1800522d3  sbb     r9d, r9d
0x1800522d6  and     r9d, 1Ch
0x1800522da  add     r9d, 4
0x1800522de  mov     rcx, [rbp+var_20]
0x1800522e2  mov     rax, [rcx]
0x1800522e5  mov     [rsp+60h+var_30], 0
0x1800522ee  mov     [rsp+60h+var_38], 0
0x1800522f7  lea     rdx, [rbp+arg_18]
0x1800522fb  mov     [rsp+60h+phkResult], rdx
0x180052300  mov     r8d, 100h
0x180052306  mov     rdx, [rbp+ppv]
0x18005230a  mov     rax, [rax+18h]
0x18005230e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052313  mov     ebx, eax
0x180052315  test    eax, eax
0x180052317  js      short loc_180052330
0x180052319  mov     rcx, [rbp+arg_18]
0x18005231d  mov     rax, [rcx]
0x180052320  mov     rdx, r15
0x180052323  mov     rax, [rax+38h]
0x180052327  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005232c  mov     ebx, eax
0x18005232e  jmp     short loc_180052337
0x180052330  neg     esi
0x180052332  sbb     al, al
0x180052334  and     dil, al
0x180052337  lea     rcx, [rbp+arg_18]
0x18005233b  call    ??1?$CComQIPtr@UIShellItemImageFactoryPriv@@$1?_GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc@@3U__s_GUID@@B@ATL@@QEAA@XZ; ATL::CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>::~CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>(void)
0x180052340  nop
0x180052341  lea     rcx, [rbp+var_20]
0x180052345  call    ??1?$CComQIPtr@UIShellItemImageFactoryPriv@@$1?_GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc@@3U__s_GUID@@B@ATL@@QEAA@XZ; ATL::CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>::~CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>(void)
0x18005234a  mov     rcx, [rbp+ppidl]; pidl
0x18005234e  call    cs:__imp_ILFree
0x180052354  nop
0x180052355  lea     rcx, [rbp+ppv]
0x180052359  call    ??1?$CComQIPtr@UIShellItemImageFactoryPriv@@$1?_GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc@@3U__s_GUID@@B@ATL@@QEAA@XZ; ATL::CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>::~CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>(void)
0x18005235e  test    dil, dil
0x180052361  jnz     loc_18005243C
0x180052367  lea     rcx, [rbp+arg_18]
0x18005236b  call    ??0?$CComPtr@UIInitializeWithFile@@@ATL@@QEAA@XZ; ATL::CComPtr<IInitializeWithFile>::CComPtr<IInitializeWithFile>(void)
0x180052370  nop
0x180052371  mov     r9d, 17h
0x180052377  lea     rcx, [rbp+arg_18]; ppv
0x18005237b  call    ?CoCreateInstance@?$CComPtrBase@UIThemeThumbnail@@@ATL@@QEAAJAEBU_GUID@@PEAUIUnknown@@K@Z; ATL::CComPtrBase<IThemeThumbnail>::CoCreateInstance(_GUID const &,IUnknown *,ulong)
0x180052380  mov     ebx, eax
0x180052382  test    eax, eax
0x180052384  js      loc_180052433
0x18005238a  lea     rcx, [rbp+ppidl]
0x18005238e  call    ??0?$CComPtr@UIInitializeWithFile@@@ATL@@QEAA@XZ; ATL::CComPtr<IInitializeWithFile>::CComPtr<IInitializeWithFile>(void)
0x180052393  nop
0x180052394  mov     rcx, [rbp+arg_18]
0x180052398  mov     rax, [rcx]
0x18005239b  lea     r8, [rbp+ppidl]
0x18005239f  lea     rdx, _GUID_b7d14566_0509_4cce_a71f_0a554233bd9b
0x1800523a6  mov     rax, [rax]
0x1800523a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800523ae  mov     ebx, eax
0x1800523b0  test    eax, eax
0x1800523b2  js      short loc_180052429
0x1800523b4  mov     rcx, [rbp+ppidl]
0x1800523b8  mov     rax, [rcx]
0x1800523bb  xor     r8d, r8d
0x1800523be  mov     rdx, [r14]
0x1800523c1  mov     rax, [rax+18h]
0x1800523c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800523ca  mov     ebx, eax
0x1800523cc  test    eax, eax
0x1800523ce  js      short loc_180052429
0x1800523d0  lea     rcx, [rbp+ppv]
0x1800523d4  call    ??0?$CComPtr@UIInitializeWithFile@@@ATL@@QEAA@XZ; ATL::CComPtr<IInitializeWithFile>::CComPtr<IInitializeWithFile>(void)
0x1800523d9  nop
0x1800523da  mov     rcx, [rbp+arg_18]
0x1800523de  mov     rax, [rcx]
0x1800523e1  lea     r8, [rbp+ppv]
0x1800523e5  lea     rdx, _GUID_e357fccd_a995_4576_b01f_234630154e96
0x1800523ec  mov     rax, [rax]
0x1800523ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800523f4  mov     ebx, eax
0x1800523f6  test    eax, eax
0x1800523f8  js      short loc_18005241F
0x1800523fa  mov     dword ptr [rbp+hKey], 0
0x180052401  mov     rcx, [rbp+ppv]
0x180052405  mov     rax, [rcx]
0x180052408  lea     r9, [rbp+hKey]
0x18005240c  mov     r8, r15
0x18005240f  mov     edx, 100h
0x180052414  mov     rax, [rax+18h]
0x180052418  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005241d  mov     ebx, eax
0x18005241f  lea     rcx, [rbp+ppv]
0x180052423  call    ??1?$CComQIPtr@UIShellItemImageFactoryPriv@@$1?_GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc@@3U__s_GUID@@B@ATL@@QEAA@XZ; ATL::CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>::~CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>(void)
0x180052428  nop
0x180052429  lea     rcx, [rbp+ppidl]
0x18005242d  call    ??1?$CComQIPtr@UIShellItemImageFactoryPriv@@$1?_GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc@@3U__s_GUID@@B@ATL@@QEAA@XZ; ATL::CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>::~CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>(void)
0x180052432  nop
0x180052433  lea     rcx, [rbp+arg_18]
0x180052437  call    ??1?$CComQIPtr@UIShellItemImageFactoryPriv@@$1?_GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc@@3U__s_GUID@@B@ATL@@QEAA@XZ; ATL::CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>::~CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>(void)
0x18005243c  mov     eax, ebx
0x18005243e  mov     rbx, [rsp+60h+arg_0]
0x180052446  add     rsp, 60h
0x18005244a  pop     r15
0x18005244c  pop     r14
0x18005244e  pop     rdi
0x18005244f  pop     rsi
0x180052450  pop     rbp
0x180052451  retn
```
