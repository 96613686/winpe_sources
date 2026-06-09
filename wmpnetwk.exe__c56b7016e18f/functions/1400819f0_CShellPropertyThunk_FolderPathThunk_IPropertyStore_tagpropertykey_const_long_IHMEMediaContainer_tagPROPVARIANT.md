# CShellPropertyThunk::FolderPathThunk(IPropertyStore *,_tagpropertykey const &,long,IHMEMediaContainer *,tagPROPVARIANT *)

- ea: `0x1400819f0`
- end: `0x140081c19`
- name: `?FolderPathThunk@CShellPropertyThunk@@CAJPEAUIPropertyStore@@AEBU_tagpropertykey@@JPEAUIHMEMediaContainer@@PEAUtagPROPVARIANT@@@Z`
- size: `553`
- prototype: `__int64 __fastcall(struct IPropertyStore *, const struct _tagpropertykey *, int, struct IHMEMediaContainer *, PROPVARIANT *pvar)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x14000b3b0`
- `0x14000c920`
- `0x1400282b0`
- `0x140045f20`
- `0x1400476ac`
- `0x1400819f0`
- `0x1400826b8`
- `0x140086618`
- `0x14009e010`

## import_xrefs

- `ole32!PropVariantClear` at `0x140081bb4`
- `ole32!PropVariantClear` at `0x140081be0`
- `ole32!PropVariantClear` at `0x140081bb4`
- `ole32!PropVariantClear` at `0x140081be0`
- `ole32!CoTaskMemFree` at `0x140081bce`
- `ole32!CoTaskMemFree` at `0x140081bce`
- `ole32!CoTaskMemAlloc` at `0x140081b63`
- `ole32!CoTaskMemAlloc` at `0x140081b63`
- `SHLWAPI!PathCreateFromUrlW` at `0x140081a87`
- `SHLWAPI!PathCreateFromUrlW` at `0x140081a87`
- `SHLWAPI!PathFindFileNameW` at `0x140081b24`
- `SHLWAPI!PathFindFileNameW` at `0x140081b24`

## pseudocode

```c
__int64 __fastcall CShellPropertyThunk::FolderPathThunk(
        struct IPropertyStore *a1,
        const struct _tagpropertykey *a2,
        int a3,
        struct IHMEMediaContainer *a4,
        PROPVARIANT *pvar)
{
  struct IPropertyStoreVtbl *lpVtbl; // rax
  HRESULT v7; // esi
  CShellLibraryCache *v8; // rax
  void *v9; // r15
  unsigned int v10; // ebx
  __int64 v11; // rax
  const WCHAR *v12; // r12
  LPWSTR FileNameW; // rdi
  unsigned __int16 *v14; // rbx
  __int64 v15; // rdi
  void *v16; // rax
  unsigned __int16 *v18; // [rsp+20h] [rbp-E0h] BYREF
  DWORD pcchPath; // [rsp+28h] [rbp-D8h] BYREF
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  PCWSTR pszUrl[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v22; // [rsp+48h] [rbp-B8h]
  WCHAR pszPath[264]; // [rsp+50h] [rbp-B0h] BYREF

  if ( a3 )
  {
    return (unsigned int)-2147023728;
  }
  else
  {
    v22 = 0;
    lpVtbl = a1->lpVtbl;
    *(_OWORD *)pszUrl = 0;
    if ( ((int (__fastcall *)(struct IPropertyStore *, const struct _tagpropertykey *, PCWSTR *))lpVtbl->GetValue)(
           a1,
           a2,
           pszUrl) >= 0
      && LOWORD(pszUrl[0]) == 31 )
    {
      pcchPath = 260;
      v7 = PathCreateFromUrlW(pszUrl[1], pszPath, &pcchPath, 0);
      if ( v7 >= 0 )
      {
        v8 = (CShellLibraryCache *)(*(__int64 (__fastcall **)(struct IHMEMediaContainer *))(*(_QWORD *)a4 + 88LL))(a4);
        pv = 0;
        LODWORD(v18) = 0;
        CShellLibraryCache::FindBaseFolderPath(v8, pszPath, (unsigned __int16 **)&pv, (enum MediaCacheSchema *)&v18);
        v9 = pv;
        if ( pv )
        {
          if ( (_DWORD)v18 )
          {
            if ( (_DWORD)v18 == 1 )
            {
              v10 = 300;
            }
            else if ( (_DWORD)v18 == 2 )
            {
              v10 = 302;
            }
            else
            {
              v10 = 0;
              if ( (_DWORD)v18 == 6 )
                v10 = 303;
            }
          }
          else
          {
            v10 = 301;
          }
          v11 = -1;
          do
            ++v11;
          while ( *((_WORD *)pv + v11) );
          v12 = &pszPath[v11];
          FileNameW = PathFindFileNameW(v12);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&v18);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::LoadStringW(
            &v18,
            v10);
          v14 = v18;
          v15 = (((__int64)FileNameW + 2LL * *((int *)v18 - 4) - (__int64)v12) >> 1) - 1;
          v16 = CoTaskMemAlloc(2 * v15 + 2);
          pvar[1] = v16;
          if ( v16 )
          {
            *(_WORD *)pvar = 31;
            v7 = StringCchCopyW((unsigned __int16 *)v16, v15 + 1, v14);
            if ( v7 < 0
              || (v7 = StringCchCopyNW(
                         (unsigned __int16 *)pvar[1] + *((int *)v14 - 4),
                         v15 - *((int *)v14 - 4) + 1,
                         v12,
                         v15 - *((int *)v14 - 4)),
                  v7 < 0) )
            {
              PropVariantClear(pvar);
            }
          }
          ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v18);
        }
        else
        {
          v7 = -2147023728;
        }
        CoTaskMemFree(v9);
      }
    }
    else
    {
      v7 = -2147023728;
    }
    PropVariantClear((PROPVARIANT *)pszUrl);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400819f0  mov     [rsp-8+arg_10], rbx
0x1400819f5  push    rbp
0x1400819f6  push    rsi
0x1400819f7  push    rdi
0x1400819f8  push    r12
0x1400819fa  push    r13
0x1400819fc  push    r14
0x1400819fe  push    r15
0x140081a00  lea     rbp, [rsp-170h]
0x140081a08  sub     rsp, 270h
0x140081a0f  mov     rax, cs:__security_cookie
0x140081a16  xor     rax, rsp
0x140081a19  mov     [rbp+1A0h+var_40], rax
0x140081a20  mov     r14, [rbp+1A0h+pvar]
0x140081a27  xor     r13d, r13d
0x140081a2a  mov     rbx, r9
0x140081a2d  test    r8d, r8d
0x140081a30  jnz     loc_140081BE8
0x140081a36  xor     eax, eax
0x140081a38  lea     r8, [rsp+2A0h+pszUrl]
0x140081a3d  mov     [rsp+2A0h+var_258], rax
0x140081a42  xorps   xmm0, xmm0
0x140081a45  mov     rax, [rcx]
0x140081a48  movups  xmmword ptr [rsp+2A0h+pszUrl], xmm0
0x140081a4d  mov     rax, [rax+28h]
0x140081a51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140081a56  test    eax, eax
0x140081a58  js      loc_140081BD6
0x140081a5e  lea     eax, [r13+1Fh]
0x140081a62  cmp     ax, word ptr [rsp+2A0h+pszUrl]
0x140081a67  jnz     loc_140081BD6
0x140081a6d  mov     rcx, [rsp+2A0h+pszUrl+8]; pszUrl
0x140081a72  lea     r8, [rsp+2A0h+pcchPath]; pcchPath
0x140081a77  xor     r9d, r9d; dwFlags
0x140081a7a  mov     [rsp+2A0h+pcchPath], 104h
0x140081a82  lea     rdx, [rsp+2A0h+pszPath]; pszPath
0x140081a87  call    cs:__imp_PathCreateFromUrlW
0x140081a8d  mov     esi, eax
0x140081a8f  test    eax, eax
0x140081a91  js      loc_140081BDB
0x140081a97  mov     rdx, [rbx]
0x140081a9a  mov     rcx, rbx
0x140081a9d  mov     rax, [rdx+58h]
0x140081aa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140081aa6  lea     r9, [rsp+2A0h+var_280]; enum MediaCacheSchema *
0x140081aab  mov     [rsp+2A0h+pv], r13
0x140081ab0  lea     r8, [rsp+2A0h+pv]; unsigned __int16 **
0x140081ab5  mov     dword ptr [rsp+2A0h+var_280], r13d
0x140081aba  lea     rdx, [rsp+2A0h+pszPath]; unsigned __int16 *
0x140081abf  mov     rcx, rax; this
0x140081ac2  call    ?FindBaseFolderPath@CShellLibraryCache@@QEBAXPEBGPEAPEAGPEAW4MediaCacheSchema@@@Z; CShellLibraryCache::FindBaseFolderPath(ushort const *,ushort * *,MediaCacheSchema *)
0x140081ac7  mov     r15, [rsp+2A0h+pv]
0x140081acc  test    r15, r15
0x140081acf  jz      loc_140081BC6
0x140081ad5  mov     eax, dword ptr [rsp+2A0h+var_280]
0x140081ad9  test    eax, eax
0x140081adb  jnz     short loc_140081AE4
0x140081add  mov     ebx, 12Dh
0x140081ae2  jmp     short loc_140081B0A
0x140081ae4  cmp     eax, 1
0x140081ae7  jnz     short loc_140081AF0
0x140081ae9  mov     ebx, 12Ch
0x140081aee  jmp     short loc_140081B0A
0x140081af0  cmp     eax, 2
0x140081af3  jnz     short loc_140081AFC
0x140081af5  mov     ebx, 12Eh
0x140081afa  jmp     short loc_140081B0A
0x140081afc  cmp     eax, 6
0x140081aff  mov     ebx, r13d
0x140081b02  mov     ecx, 12Fh
0x140081b07  cmovz   ebx, ecx
0x140081b0a  or      rax, 0FFFFFFFFFFFFFFFFh
0x140081b0e  inc     rax
0x140081b11  cmp     [r15+rax*2], r13w
0x140081b16  jnz     short loc_140081B0E
0x140081b18  lea     r12, [rsp+2A0h+pszPath]
0x140081b1d  lea     r12, [r12+rax*2]
0x140081b21  mov     rcx, r12; pszPath
0x140081b24  call    cs:__imp_PathFindFileNameW
0x140081b2a  lea     rcx, [rsp+2A0h+var_280]
0x140081b2f  mov     rdi, rax
0x140081b32  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x140081b37  mov     edx, ebx
0x140081b39  lea     rcx, [rsp+2A0h+var_280]
0x140081b3e  call    ?LoadStringW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAAHI@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::LoadStringW(uint)
0x140081b43  mov     rbx, [rsp+2A0h+var_280]
0x140081b48  movsxd  rcx, dword ptr [rbx-10h]
0x140081b4c  add     rcx, rcx
0x140081b4f  sub     rcx, r12
0x140081b52  add     rdi, rcx
0x140081b55  sar     rdi, 1
0x140081b58  dec     rdi
0x140081b5b  lea     rcx, ds:2[rdi*2]; cb
0x140081b63  call    cs:__imp_CoTaskMemAlloc
0x140081b69  mov     [r14+8], rax
0x140081b6d  test    rax, rax
0x140081b70  jz      short loc_140081BBA
0x140081b72  lea     rdx, [rdi+1]; unsigned __int64
0x140081b76  mov     word ptr [r14], 1Fh
0x140081b7c  mov     r8, rbx; unsigned __int16 *
0x140081b7f  mov     rcx, rax; unsigned __int16 *
0x140081b82  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140081b87  mov     esi, eax
0x140081b89  test    eax, eax
0x140081b8b  js      short loc_140081BB1
0x140081b8d  movsxd  r10, dword ptr [rbx-10h]
0x140081b91  mov     r8, r12; unsigned __int16 *
0x140081b94  mov     rax, [r14+8]
0x140081b98  sub     rdi, r10
0x140081b9b  mov     r9, rdi; unsigned __int64
0x140081b9e  lea     rdx, [rdi+1]; unsigned __int64
0x140081ba2  lea     rcx, [rax+r10*2]; unsigned __int16 *
0x140081ba6  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x140081bab  mov     esi, eax
0x140081bad  test    eax, eax
0x140081baf  jns     short loc_140081BBA
0x140081bb1  mov     rcx, r14; pvar
0x140081bb4  call    cs:__imp_PropVariantClear
0x140081bba  lea     rcx, [rsp+2A0h+var_280]
0x140081bbf  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x140081bc4  jmp     short loc_140081BCB
0x140081bc6  mov     esi, 80070490h
0x140081bcb  mov     rcx, r15; pv
0x140081bce  call    cs:__imp_CoTaskMemFree
0x140081bd4  jmp     short loc_140081BDB
0x140081bd6  mov     esi, 80070490h
0x140081bdb  lea     rcx, [rsp+2A0h+pszUrl]; pvar
0x140081be0  call    cs:__imp_PropVariantClear
0x140081be6  jmp     short loc_140081BED
0x140081be8  mov     esi, 80070490h
0x140081bed  mov     eax, esi
0x140081bef  mov     rcx, [rbp+1A0h+var_40]
0x140081bf6  xor     rcx, rsp; StackCookie
0x140081bf9  call    __security_check_cookie
0x140081bfe  mov     rbx, [rsp+2A0h+arg_10]
0x140081c06  add     rsp, 270h
0x140081c0d  pop     r15
0x140081c0f  pop     r14
0x140081c11  pop     r13
0x140081c13  pop     r12
0x140081c15  pop     rdi
0x140081c16  pop     rsi
0x140081c17  pop     rbp
0x140081c18  retn
```
