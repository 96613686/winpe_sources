# GetFriendlyResourceDependencyExpression(_HRESOURCE *,wchar_t * *)

- ea: `0x18003c820`
- end: `0x18003cbc4`
- name: `?GetFriendlyResourceDependencyExpression@@YAKPEAU_HRESOURCE@@PEAPEA_W@Z`
- size: `932`
- prototype: `__int64 __fastcall(HRESOURCE hResource, wchar_t **)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180030790`

## callees

- `0x180002b50`
- `0x180009e24`
- `0x180009e80`
- `0x1800168d0`
- `0x18003c820`
- `0x18003cf74`
- `0x18003d0a8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x18003c94b`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x18003c96d`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x18003c94b`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x18003c96d`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18003c915`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18003c915`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c8d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cb0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cb1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c8d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cb0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cb1c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003c8c4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003ca45`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003c8c4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003ca45`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ca75`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003cacc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003caef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003cb70`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003cb7f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003cb8e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ca75`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003cacc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003caef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003cb70`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003cb7f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003cb8e`
- `CLUSAPI!CloseCluster` at `0x18003cb46`
- `CLUSAPI!CloseCluster` at `0x18003cb46`
- `CLUSAPI!CloseClusterResource` at `0x18003c9d3`
- `CLUSAPI!CloseClusterResource` at `0x18003cb5a`
- `CLUSAPI!CloseClusterResource` at `0x18003c9d3`
- `CLUSAPI!CloseClusterResource` at `0x18003cb5a`
- `CLUSAPI!OpenClusterResource` at `0x18003c9a2`
- `CLUSAPI!OpenClusterResource` at `0x18003c9a2`
- `CLUSAPI!GetClusterFromResource` at `0x18003c8ee`
- `CLUSAPI!GetClusterFromResource` at `0x18003c8ee`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetFriendlyResourceDependencyExpression(HRESOURCE hResource, wchar_t **a2)
{
  wchar_t *v4; // r14
  wchar_t *v5; // rdi
  wchar_t *v6; // r15
  unsigned int ResourceDependencyExpression; // eax
  DWORD LastError; // ebx
  __int64 v9; // rax
  struct _HCLUSTER *v10; // rsi
  wchar_t *v11; // rax
  unsigned __int64 v12; // r12
  int v13; // eax
  wchar_t *i; // r13
  struct _HRESOURCE *v15; // rax
  struct _HRESOURCE *v16; // rsi
  __int64 v17; // rdx
  __int64 v18; // rcx
  const wchar_t *v19; // r13
  __int64 v20; // rax
  __int64 v21; // r8
  unsigned __int64 v22; // r13
  wchar_t *v23; // rax
  wchar_t *v24; // r12
  int v25; // eax
  unsigned __int16 v26; // r13
  int v27; // eax
  wchar_t **v28; // rax
  wchar_t Delimiter[4]; // [rsp+20h] [rbp-79h] BYREF
  HLOCAL hMem; // [rsp+28h] [rbp-71h] BYREF
  wchar_t *String; // [rsp+30h] [rbp-69h] BYREF
  wchar_t *Context; // [rsp+38h] [rbp-61h] BYREF
  const wchar_t *v34; // [rsp+40h] [rbp-59h]
  wchar_t *v35; // [rsp+48h] [rbp-51h]
  wchar_t **v36; // [rsp+50h] [rbp-49h]
  WCHAR szResourceName[40]; // [rsp+60h] [rbp-39h] BYREF

  v36 = a2;
  String = 0;
  wcscpy(Delimiter, L"[");
  hMem = 0;
  v4 = 0;
  v5 = 0;
  v6 = 0;
  if ( hResource && a2 )
  {
    *a2 = 0;
    ResourceDependencyExpression = WrapGetResourceDependencyExpression(hResource, &String);
    v4 = String;
    LastError = ResourceDependencyExpression;
    if ( !ResourceDependencyExpression )
    {
      v9 = -1;
      do
        ++v9;
      while ( String[v9] );
      if ( v9 )
      {
        v5 = (wchar_t *)LocalAlloc(0x40u, 0x400u);
        if ( v5 && (String = (wchar_t *)GetClusterFromResource(hResource), (v10 = (struct _HCLUSTER *)String) != 0) )
        {
          Context = 0;
          v11 = wcstok_s(v4, Delimiter, &Context);
          v12 = 512;
          v13 = StringCchCopyW(v5, 0x200u, v11);
          if ( v13 >= 0 )
          {
            for ( i = wcstok(0, Delimiter, &Context); i; i = v35 )
            {
              v35 = wcstok(0, Delimiter, &Context);
              if ( (int)StringCchCopyNW(szResourceName, 0x25u, i, 0x24u) < 0 )
              {
                LastError = GetLastError();
                goto LABEL_38;
              }
              v15 = OpenClusterResource(v10, szResourceName);
              v16 = v15;
              if ( !v15 )
                goto LABEL_35;
              LastError = WrapGetResourceName(v15, (wchar_t **)&hMem);
              if ( LastError )
              {
                v6 = (wchar_t *)hMem;
                goto LABEL_39;
              }
              CloseClusterResource(v16);
              v6 = (wchar_t *)hMem;
              v17 = -1;
              v16 = 0;
              v18 = -1;
              do
                ++v18;
              while ( *((_WORD *)hMem + v18) );
              v19 = i + 36;
              v20 = -1;
              v34 = v19;
              do
                ++v20;
              while ( v19[v20] );
              v21 = v20 + v18;
              do
                ++v17;
              while ( v5[v17] );
              if ( v12 - v17 <= v21 + 1 )
              {
                v22 = v21 + v17 + 2;
                hMem = (HLOCAL)v22;
                v23 = (wchar_t *)LocalAlloc(0x40u, 2 * v22);
                v24 = v23;
                if ( !v23 )
                {
LABEL_35:
                  LastError = GetLastError();
                  goto LABEL_39;
                }
                v25 = StringCchCopyW(v23, v22, v5);
                v26 = v25;
                if ( v25 < 0 )
                {
                  LocalFree(v24);
                  LastError = v26;
                  goto LABEL_39;
                }
                LocalFree(v5);
                v19 = v34;
                v5 = v24;
                v12 = (unsigned __int64)hMem;
              }
              v27 = StringCchCatW(v5, v12, L"[");
              if ( v27 < 0
                || (v27 = StringCchCatW(v5, v12, v6), v27 < 0)
                || (v27 = StringCchCatW(v5, v12, v19), v27 < 0) )
              {
                LastError = (unsigned __int16)v27;
                goto LABEL_39;
              }
              LocalFree(v6);
              v10 = (struct _HCLUSTER *)String;
              v6 = 0;
              hMem = 0;
            }
            v28 = v36;
            v5[v12 - 1] = 0;
            *v28 = v5;
            v5 = 0;
          }
          else
          {
            LastError = (unsigned __int16)v13;
          }
LABEL_38:
          v16 = 0;
LABEL_39:
          CloseCluster((HCLUSTER)String);
          if ( v16 )
            CloseClusterResource(v16);
        }
        else
        {
          LastError = GetLastError();
        }
      }
      else
      {
        *a2 = String;
        v4 = 0;
      }
    }
  }
  else
  {
    LastError = 87;
  }
  LocalFree(v6);
  LocalFree(v4);
  LocalFree(v5);
  return LastError;
}

```

## disassembly

```asm
0x18003c820  mov     [rsp-8+arg_10], rbx
0x18003c825  push    rbp
0x18003c826  push    rsi
0x18003c827  push    rdi
0x18003c828  push    r12
0x18003c82a  push    r13
0x18003c82c  push    r14
0x18003c82e  push    r15
0x18003c830  lea     rbp, [rsp-27h]
0x18003c835  sub     rsp, 0C0h
0x18003c83c  mov     rax, cs:__security_cookie
0x18003c843  xor     rax, rsp
0x18003c846  mov     [rbp+57h+var_40], rax
0x18003c84a  xor     r13d, r13d
0x18003c84d  mov     [rbp+57h+var_A0], rdx
0x18003c851  mov     [rbp+57h+String], r13
0x18003c855  mov     r12, rdx
0x18003c858  mov     dword ptr [rbp+57h+Delimiter], 5Bh ; '['
0x18003c85f  mov     rsi, rcx
0x18003c862  mov     [rbp+57h+hMem], r13
0x18003c866  mov     r14d, r13d
0x18003c869  mov     edi, r13d
0x18003c86c  mov     r15d, r13d
0x18003c86f  test    rcx, rcx
0x18003c872  jz      loc_18003CB68
0x18003c878  test    rdx, rdx
0x18003c87b  jz      loc_18003CB68
0x18003c881  mov     [rdx], r13
0x18003c884  lea     rdx, [rbp+57h+String]; wchar_t **
0x18003c888  call    ?WrapGetResourceDependencyExpression@@YAKPEAU_HRESOURCE@@PEAPEA_W@Z; WrapGetResourceDependencyExpression(_HRESOURCE *,wchar_t * *)
0x18003c88d  mov     r14, [rbp+57h+String]
0x18003c891  mov     ebx, eax
0x18003c893  test    eax, eax
0x18003c895  jnz     loc_18003CB6D
0x18003c89b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003c89f  inc     rax
0x18003c8a2  cmp     [r14+rax*2], r13w
0x18003c8a7  jnz     short loc_18003C89F
0x18003c8a9  test    rax, rax
0x18003c8ac  jnz     short loc_18003C8BA
0x18003c8ae  mov     [r12], r14
0x18003c8b2  mov     r14, r13
0x18003c8b5  jmp     loc_18003CB6D
0x18003c8ba  mov     edx, 400h; uBytes
0x18003c8bf  mov     ecx, 40h ; '@'; uFlags
0x18003c8c4  call    cs:__imp_LocalAlloc
0x18003c8cb  nop     dword ptr [rax+rax+00h]
0x18003c8d0  mov     rdi, rax
0x18003c8d3  test    rax, rax
0x18003c8d6  jnz     short loc_18003C8EB
0x18003c8d8  call    cs:__imp_GetLastError
0x18003c8df  nop     dword ptr [rax+rax+00h]
0x18003c8e4  mov     ebx, eax
0x18003c8e6  jmp     loc_18003CB6D
0x18003c8eb  mov     rcx, rsi; hResource
0x18003c8ee  call    cs:__imp_GetClusterFromResource
0x18003c8f5  nop     dword ptr [rax+rax+00h]
0x18003c8fa  mov     [rbp+57h+String], rax
0x18003c8fe  mov     rsi, rax
0x18003c901  test    rax, rax
0x18003c904  jz      short loc_18003C8D8
0x18003c906  lea     r8, [rbp+57h+Context]; Context
0x18003c90a  mov     [rbp+57h+Context], r13
0x18003c90e  lea     rdx, [rbp+57h+Delimiter]; Delimiter
0x18003c912  mov     rcx, r14; String
0x18003c915  call    cs:__imp_wcstok_s
0x18003c91c  nop     dword ptr [rax+rax+00h]
0x18003c921  mov     r12d, 200h
0x18003c927  mov     rcx, rdi; wchar_t *
0x18003c92a  mov     r8, rax; wchar_t *
0x18003c92d  mov     edx, r12d; unsigned __int64
0x18003c930  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18003c935  test    eax, eax
0x18003c937  jns     short loc_18003C941
0x18003c939  movzx   ebx, ax
0x18003c93c  jmp     loc_18003CB3F
0x18003c941  lea     r8, [rbp+57h+Context]; Context
0x18003c945  xor     ecx, ecx; String
0x18003c947  lea     rdx, [rbp+57h+Delimiter]; Delimiter
0x18003c94b  call    cs:__imp_wcstok
0x18003c952  nop     dword ptr [rax+rax+00h]
0x18003c957  mov     r13, rax
0x18003c95a  test    r13, r13
0x18003c95d  jz      loc_18003CB2F
0x18003c963  lea     r8, [rbp+57h+Context]; Context
0x18003c967  xor     ecx, ecx; String
0x18003c969  lea     rdx, [rbp+57h+Delimiter]; Delimiter
0x18003c96d  call    cs:__imp_wcstok
0x18003c974  nop     dword ptr [rax+rax+00h]
0x18003c979  mov     r9d, 24h ; '$'; unsigned __int64
0x18003c97f  lea     rcx, [rbp+57h+szResourceName]; wchar_t *
0x18003c983  mov     r8, r13; wchar_t *
0x18003c986  mov     [rbp+57h+var_A8], rax
0x18003c98a  lea     edx, [r9+1]; unsigned __int64
0x18003c98e  call    ?StringCchCopyNW@@YAJPEA_W_KPEB_W1@Z; StringCchCopyNW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64)
0x18003c993  test    eax, eax
0x18003c995  js      loc_18003CB1C
0x18003c99b  lea     rdx, [rbp+57h+szResourceName]; lpszResourceName
0x18003c99f  mov     rcx, rsi; hCluster
0x18003c9a2  call    cs:__imp_OpenClusterResource
0x18003c9a9  nop     dword ptr [rax+rax+00h]
0x18003c9ae  mov     rsi, rax
0x18003c9b1  test    rax, rax
0x18003c9b4  jz      loc_18003CB0C
0x18003c9ba  lea     rdx, [rbp+57h+hMem]; wchar_t **
0x18003c9be  mov     rcx, rax; hResource
0x18003c9c1  call    ?WrapGetResourceName@@YAKPEAU_HRESOURCE@@PEAPEA_W@Z; WrapGetResourceName(_HRESOURCE *,wchar_t * *)
0x18003c9c6  mov     ebx, eax
0x18003c9c8  test    eax, eax
0x18003c9ca  jnz     loc_18003CB06
0x18003c9d0  mov     rcx, rsi; hResource
0x18003c9d3  call    cs:__imp_CloseClusterResource
0x18003c9da  nop     dword ptr [rax+rax+00h]
0x18003c9df  mov     r15, [rbp+57h+hMem]
0x18003c9e3  xor     r9d, r9d
0x18003c9e6  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18003c9ea  mov     esi, r9d
0x18003c9ed  mov     rcx, rdx
0x18003c9f0  inc     rcx
0x18003c9f3  cmp     [r15+rcx*2], r9w
0x18003c9f8  jnz     short loc_18003C9F0
0x18003c9fa  add     r13, 48h ; 'H'
0x18003c9fe  mov     rax, rdx
0x18003ca01  mov     [rbp+57h+var_B0], r13
0x18003ca05  inc     rax
0x18003ca08  cmp     [r13+rax*2+0], r9w
0x18003ca0e  jnz     short loc_18003CA05
0x18003ca10  lea     r8, [rax+rcx]
0x18003ca14  inc     rdx
0x18003ca17  cmp     [rdi+rdx*2], r9w
0x18003ca1c  jnz     short loc_18003CA14
0x18003ca1e  mov     rcx, r12
0x18003ca21  lea     rax, [r8+1]
0x18003ca25  sub     rcx, rdx
0x18003ca28  cmp     rcx, rax
0x18003ca2b  ja      short loc_18003CA8C
0x18003ca2d  lea     r13, [rdx+2]
0x18003ca31  mov     ecx, 40h ; '@'; uFlags
0x18003ca36  add     r13, r8
0x18003ca39  mov     [rbp+57h+hMem], r13
0x18003ca3d  lea     rdx, ds:0[r13*2]; uBytes
0x18003ca45  call    cs:__imp_LocalAlloc
0x18003ca4c  nop     dword ptr [rax+rax+00h]
0x18003ca51  mov     r12, rax
0x18003ca54  test    rax, rax
0x18003ca57  jz      loc_18003CB0C
0x18003ca5d  mov     r8, rdi; wchar_t *
0x18003ca60  mov     rdx, r13; unsigned __int64
0x18003ca63  mov     rcx, rax; wchar_t *
0x18003ca66  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18003ca6b  mov     r13d, eax
0x18003ca6e  test    eax, eax
0x18003ca70  js      short loc_18003CAEC
0x18003ca72  mov     rcx, rdi; hMem
0x18003ca75  call    cs:__imp_LocalFree
0x18003ca7c  nop     dword ptr [rax+rax+00h]
0x18003ca81  mov     r13, [rbp+57h+var_B0]
0x18003ca85  mov     rdi, r12
0x18003ca88  mov     r12, [rbp+57h+hMem]
0x18003ca8c  lea     r8, asc_180110938; "["
0x18003ca93  mov     rdx, r12; unsigned __int64
0x18003ca96  mov     rcx, rdi; wchar_t *
0x18003ca99  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18003ca9e  test    eax, eax
0x18003caa0  js      short loc_18003CB01
0x18003caa2  mov     r8, r15; wchar_t *
0x18003caa5  mov     rdx, r12; unsigned __int64
0x18003caa8  mov     rcx, rdi; wchar_t *
0x18003caab  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18003cab0  test    eax, eax
0x18003cab2  js      short loc_18003CB01
0x18003cab4  mov     r8, r13; wchar_t *
0x18003cab7  mov     rdx, r12; unsigned __int64
0x18003caba  mov     rcx, rdi; wchar_t *
0x18003cabd  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18003cac2  xor     r13d, r13d
0x18003cac5  test    eax, eax
0x18003cac7  js      short loc_18003CB01
0x18003cac9  mov     rcx, r15; hMem
0x18003cacc  call    cs:__imp_LocalFree
0x18003cad3  nop     dword ptr [rax+rax+00h]
0x18003cad8  mov     rsi, [rbp+57h+String]
0x18003cadc  mov     r15d, r13d
0x18003cadf  mov     [rbp+57h+hMem], r13
0x18003cae3  mov     r13, [rbp+57h+var_A8]
0x18003cae7  jmp     loc_18003C95A
0x18003caec  mov     rcx, r12; hMem
0x18003caef  call    cs:__imp_LocalFree
0x18003caf6  nop     dword ptr [rax+rax+00h]
0x18003cafb  movzx   ebx, r13w
0x18003caff  jmp     short loc_18003CB42
0x18003cb01  movzx   ebx, ax
0x18003cb04  jmp     short loc_18003CB42
0x18003cb06  mov     r15, [rbp+57h+hMem]
0x18003cb0a  jmp     short loc_18003CB42
0x18003cb0c  call    cs:__imp_GetLastError
0x18003cb13  nop     dword ptr [rax+rax+00h]
0x18003cb18  mov     ebx, eax
0x18003cb1a  jmp     short loc_18003CB42
0x18003cb1c  call    cs:__imp_GetLastError
0x18003cb23  nop     dword ptr [rax+rax+00h]
0x18003cb28  mov     ebx, eax
0x18003cb2a  xor     r13d, r13d
0x18003cb2d  jmp     short loc_18003CB3F
0x18003cb2f  mov     rax, [rbp+57h+var_A0]
0x18003cb33  mov     [rdi+r12*2-2], r13w
0x18003cb39  mov     [rax], rdi
0x18003cb3c  mov     rdi, r13
0x18003cb3f  mov     rsi, r13
0x18003cb42  mov     rcx, [rbp+57h+String]; hCluster
0x18003cb46  call    cs:__imp_CloseCluster
0x18003cb4d  nop     dword ptr [rax+rax+00h]
0x18003cb52  test    rsi, rsi
0x18003cb55  jz      short loc_18003CB6D
0x18003cb57  mov     rcx, rsi; hResource
0x18003cb5a  call    cs:__imp_CloseClusterResource
0x18003cb61  nop     dword ptr [rax+rax+00h]
0x18003cb66  jmp     short loc_18003CB6D
0x18003cb68  mov     ebx, 57h ; 'W'
0x18003cb6d  mov     rcx, r15; hMem
0x18003cb70  call    cs:__imp_LocalFree
0x18003cb77  nop     dword ptr [rax+rax+00h]
0x18003cb7c  mov     rcx, r14; hMem
0x18003cb7f  call    cs:__imp_LocalFree
0x18003cb86  nop     dword ptr [rax+rax+00h]
0x18003cb8b  mov     rcx, rdi; hMem
0x18003cb8e  call    cs:__imp_LocalFree
0x18003cb95  nop     dword ptr [rax+rax+00h]
0x18003cb9a  mov     eax, ebx
0x18003cb9c  mov     rcx, [rbp+57h+var_40]
0x18003cba0  xor     rcx, rsp; StackCookie
0x18003cba3  call    __security_check_cookie
0x18003cba8  mov     rbx, [rsp+0F0h+arg_10]
0x18003cbb0  add     rsp, 0C0h
0x18003cbb7  pop     r15
0x18003cbb9  pop     r14
0x18003cbbb  pop     r13
0x18003cbbd  pop     r12
0x18003cbbf  pop     rdi
0x18003cbc0  pop     rsi
0x18003cbc1  pop     rbp
0x18003cbc2  retn
```
