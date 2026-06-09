# GetFriendlyResourceDependencyExpression(_HRESOURCE *,wchar_t * *)

- ea: `0x1800969f0`
- end: `0x180096d21`
- name: `?GetFriendlyResourceDependencyExpression@@YAKPEAU_HRESOURCE@@PEAPEA_W@Z`
- size: `817`
- prototype: `unsigned int __fastcall(HRESOURCE hResource, wchar_t **)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180033500`

## callees

- `0x180002a70`
- `0x180009bd4`
- `0x180009c30`
- `0x18001914c`
- `0x1800969f0`
- `0x180097044`
- `0x18009714c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x180096b03`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x180096b1f`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x180096b03`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x180096b1f`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180096ad3`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180096ad3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096aa2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096c94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096c9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096aa2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096c94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096c9e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180096a94`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180096be5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180096a94`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180096be5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180096c0f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180096c60`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180096c7d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180096ce0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180096ce9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180096cf2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180096c0f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180096c60`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180096c7d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180096ce0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180096ce9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180096cf2`
- `CLUSAPI!CloseClusterResource` at `0x180096b79`
- `CLUSAPI!CloseClusterResource` at `0x180096cd0`
- `CLUSAPI!CloseClusterResource` at `0x180096b79`
- `CLUSAPI!CloseClusterResource` at `0x180096cd0`
- `CLUSAPI!CloseCluster` at `0x180096cc2`
- `CLUSAPI!CloseCluster` at `0x180096cc2`
- `CLUSAPI!GetClusterFromResource` at `0x180096ab2`
- `CLUSAPI!GetClusterFromResource` at `0x180096ab2`
- `CLUSAPI!OpenClusterResource` at `0x180096b4e`
- `CLUSAPI!OpenClusterResource` at `0x180096b4e`

## pseudocode

```c
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
0x1800969f0  mov     [rsp-8+arg_10], rbx
0x1800969f5  push    rbp
0x1800969f6  push    rsi
0x1800969f7  push    rdi
0x1800969f8  push    r12
0x1800969fa  push    r13
0x1800969fc  push    r14
0x1800969fe  push    r15
0x180096a00  lea     rbp, [rsp-27h]
0x180096a05  sub     rsp, 0C0h
0x180096a0c  mov     rax, cs:__security_cookie
0x180096a13  xor     rax, rsp
0x180096a16  mov     [rbp+57h+var_40], rax
0x180096a1a  xor     r13d, r13d
0x180096a1d  mov     [rbp+57h+var_A0], rdx
0x180096a21  mov     [rbp+57h+String], r13
0x180096a25  mov     r12, rdx
0x180096a28  mov     dword ptr [rbp+57h+Delimiter], 5Bh ; '['
0x180096a2f  mov     rsi, rcx
0x180096a32  mov     [rbp+57h+hMem], r13
0x180096a36  mov     r14d, r13d
0x180096a39  mov     edi, r13d
0x180096a3c  mov     r15d, r13d
0x180096a3f  test    rcx, rcx
0x180096a42  jz      loc_180096CD8
0x180096a48  test    rdx, rdx
0x180096a4b  jz      loc_180096CD8
0x180096a51  mov     [rdx], r13
0x180096a54  lea     rdx, [rbp+57h+String]; wchar_t **
0x180096a58  call    ?WrapGetResourceDependencyExpression@@YAKPEAU_HRESOURCE@@PEAPEA_W@Z; WrapGetResourceDependencyExpression(_HRESOURCE *,wchar_t * *)
0x180096a5d  mov     r14, [rbp+57h+String]
0x180096a61  mov     ebx, eax
0x180096a63  test    eax, eax
0x180096a65  jnz     loc_180096CDD
0x180096a6b  or      rax, 0FFFFFFFFFFFFFFFFh
0x180096a6f  inc     rax
0x180096a72  cmp     [r14+rax*2], r13w
0x180096a77  jnz     short loc_180096A6F
0x180096a79  test    rax, rax
0x180096a7c  jnz     short loc_180096A8A
0x180096a7e  mov     [r12], r14
0x180096a82  mov     r14, r13
0x180096a85  jmp     loc_180096CDD
0x180096a8a  mov     edx, 400h; uBytes
0x180096a8f  mov     ecx, 40h ; '@'; uFlags
0x180096a94  call    cs:__imp_LocalAlloc
0x180096a9a  mov     rdi, rax
0x180096a9d  test    rax, rax
0x180096aa0  jnz     short loc_180096AAF
0x180096aa2  call    cs:__imp_GetLastError
0x180096aa8  mov     ebx, eax
0x180096aaa  jmp     loc_180096CDD
0x180096aaf  mov     rcx, rsi; hResource
0x180096ab2  call    cs:__imp_GetClusterFromResource
0x180096ab8  mov     [rbp+57h+String], rax
0x180096abc  mov     rsi, rax
0x180096abf  test    rax, rax
0x180096ac2  jz      short loc_180096AA2
0x180096ac4  lea     r8, [rbp+57h+Context]; Context
0x180096ac8  mov     [rbp+57h+Context], r13
0x180096acc  lea     rdx, [rbp+57h+Delimiter]; Delimiter
0x180096ad0  mov     rcx, r14; String
0x180096ad3  call    cs:__imp_wcstok_s
0x180096ad9  mov     r12d, 200h
0x180096adf  mov     rcx, rdi; wchar_t *
0x180096ae2  mov     r8, rax; wchar_t *
0x180096ae5  mov     edx, r12d; unsigned __int64
0x180096ae8  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180096aed  test    eax, eax
0x180096aef  jns     short loc_180096AF9
0x180096af1  movzx   ebx, ax
0x180096af4  jmp     loc_180096CBB
0x180096af9  lea     r8, [rbp+57h+Context]; Context
0x180096afd  xor     ecx, ecx; String
0x180096aff  lea     rdx, [rbp+57h+Delimiter]; Delimiter
0x180096b03  call    cs:__imp_wcstok
0x180096b09  mov     r13, rax
0x180096b0c  test    r13, r13
0x180096b0f  jz      loc_180096CAB
0x180096b15  lea     r8, [rbp+57h+Context]; Context
0x180096b19  xor     ecx, ecx; String
0x180096b1b  lea     rdx, [rbp+57h+Delimiter]; Delimiter
0x180096b1f  call    cs:__imp_wcstok
0x180096b25  mov     r9d, 24h ; '$'; unsigned __int64
0x180096b2b  lea     rcx, [rbp+57h+szResourceName]; wchar_t *
0x180096b2f  mov     r8, r13; wchar_t *
0x180096b32  mov     [rbp+57h+var_A8], rax
0x180096b36  lea     edx, [r9+1]; unsigned __int64
0x180096b3a  call    ?StringCchCopyNW@@YAJPEA_W_KPEB_W1@Z; StringCchCopyNW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64)
0x180096b3f  test    eax, eax
0x180096b41  js      loc_180096C9E
0x180096b47  lea     rdx, [rbp+57h+szResourceName]; lpszResourceName
0x180096b4b  mov     rcx, rsi; hCluster
0x180096b4e  call    cs:__imp_OpenClusterResource
0x180096b54  mov     rsi, rax
0x180096b57  test    rax, rax
0x180096b5a  jz      loc_180096C94
0x180096b60  lea     rdx, [rbp+57h+hMem]; wchar_t **
0x180096b64  mov     rcx, rax; hResource
0x180096b67  call    ?WrapGetResourceName@@YAKPEAU_HRESOURCE@@PEAPEA_W@Z; WrapGetResourceName(_HRESOURCE *,wchar_t * *)
0x180096b6c  mov     ebx, eax
0x180096b6e  test    eax, eax
0x180096b70  jnz     loc_180096C8E
0x180096b76  mov     rcx, rsi; hResource
0x180096b79  call    cs:__imp_CloseClusterResource
0x180096b7f  mov     r15, [rbp+57h+hMem]
0x180096b83  xor     r9d, r9d
0x180096b86  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180096b8a  mov     esi, r9d
0x180096b8d  mov     rcx, rdx
0x180096b90  inc     rcx
0x180096b93  cmp     [r15+rcx*2], r9w
0x180096b98  jnz     short loc_180096B90
0x180096b9a  add     r13, 48h ; 'H'
0x180096b9e  mov     rax, rdx
0x180096ba1  mov     [rbp+57h+var_B0], r13
0x180096ba5  inc     rax
0x180096ba8  cmp     [r13+rax*2+0], r9w
0x180096bae  jnz     short loc_180096BA5
0x180096bb0  lea     r8, [rax+rcx]
0x180096bb4  inc     rdx
0x180096bb7  cmp     [rdi+rdx*2], r9w
0x180096bbc  jnz     short loc_180096BB4
0x180096bbe  mov     rcx, r12
0x180096bc1  lea     rax, [r8+1]
0x180096bc5  sub     rcx, rdx
0x180096bc8  cmp     rcx, rax
0x180096bcb  ja      short loc_180096C20
0x180096bcd  lea     r13, [rdx+2]
0x180096bd1  mov     ecx, 40h ; '@'; uFlags
0x180096bd6  add     r13, r8
0x180096bd9  mov     [rbp+57h+hMem], r13
0x180096bdd  lea     rdx, ds:0[r13*2]; uBytes
0x180096be5  call    cs:__imp_LocalAlloc
0x180096beb  mov     r12, rax
0x180096bee  test    rax, rax
0x180096bf1  jz      loc_180096C94
0x180096bf7  mov     r8, rdi; wchar_t *
0x180096bfa  mov     rdx, r13; unsigned __int64
0x180096bfd  mov     rcx, rax; wchar_t *
0x180096c00  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180096c05  mov     r13d, eax
0x180096c08  test    eax, eax
0x180096c0a  js      short loc_180096C7A
0x180096c0c  mov     rcx, rdi; hMem
0x180096c0f  call    cs:__imp_LocalFree
0x180096c15  mov     r13, [rbp+57h+var_B0]
0x180096c19  mov     rdi, r12
0x180096c1c  mov     r12, [rbp+57h+hMem]
0x180096c20  lea     r8, asc_180135EB4; "["
0x180096c27  mov     rdx, r12; unsigned __int64
0x180096c2a  mov     rcx, rdi; wchar_t *
0x180096c2d  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180096c32  test    eax, eax
0x180096c34  js      short loc_180096C89
0x180096c36  mov     r8, r15; wchar_t *
0x180096c39  mov     rdx, r12; unsigned __int64
0x180096c3c  mov     rcx, rdi; wchar_t *
0x180096c3f  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180096c44  test    eax, eax
0x180096c46  js      short loc_180096C89
0x180096c48  mov     r8, r13; wchar_t *
0x180096c4b  mov     rdx, r12; unsigned __int64
0x180096c4e  mov     rcx, rdi; wchar_t *
0x180096c51  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180096c56  xor     r13d, r13d
0x180096c59  test    eax, eax
0x180096c5b  js      short loc_180096C89
0x180096c5d  mov     rcx, r15; hMem
0x180096c60  call    cs:__imp_LocalFree
0x180096c66  mov     rsi, [rbp+57h+String]
0x180096c6a  mov     r15d, r13d
0x180096c6d  mov     [rbp+57h+hMem], r13
0x180096c71  mov     r13, [rbp+57h+var_A8]
0x180096c75  jmp     loc_180096B0C
0x180096c7a  mov     rcx, r12; hMem
0x180096c7d  call    cs:__imp_LocalFree
0x180096c83  movzx   ebx, r13w
0x180096c87  jmp     short loc_180096CBE
0x180096c89  movzx   ebx, ax
0x180096c8c  jmp     short loc_180096CBE
0x180096c8e  mov     r15, [rbp+57h+hMem]
0x180096c92  jmp     short loc_180096CBE
0x180096c94  call    cs:__imp_GetLastError
0x180096c9a  mov     ebx, eax
0x180096c9c  jmp     short loc_180096CBE
0x180096c9e  call    cs:__imp_GetLastError
0x180096ca4  mov     ebx, eax
0x180096ca6  xor     r13d, r13d
0x180096ca9  jmp     short loc_180096CBB
0x180096cab  mov     rax, [rbp+57h+var_A0]
0x180096caf  mov     [rdi+r12*2-2], r13w
0x180096cb5  mov     [rax], rdi
0x180096cb8  mov     rdi, r13
0x180096cbb  mov     rsi, r13
0x180096cbe  mov     rcx, [rbp+57h+String]; hCluster
0x180096cc2  call    cs:__imp_CloseCluster
0x180096cc8  test    rsi, rsi
0x180096ccb  jz      short loc_180096CDD
0x180096ccd  mov     rcx, rsi; hResource
0x180096cd0  call    cs:__imp_CloseClusterResource
0x180096cd6  jmp     short loc_180096CDD
0x180096cd8  mov     ebx, 57h ; 'W'
0x180096cdd  mov     rcx, r15; hMem
0x180096ce0  call    cs:__imp_LocalFree
0x180096ce6  mov     rcx, r14; hMem
0x180096ce9  call    cs:__imp_LocalFree
0x180096cef  mov     rcx, rdi; hMem
0x180096cf2  call    cs:__imp_LocalFree
0x180096cf8  mov     eax, ebx
0x180096cfa  mov     rcx, [rbp+57h+var_40]
0x180096cfe  xor     rcx, rsp; StackCookie
0x180096d01  call    __security_check_cookie
0x180096d06  mov     rbx, [rsp+0F0h+arg_10]
0x180096d0e  add     rsp, 0C0h
0x180096d15  pop     r15
0x180096d17  pop     r14
0x180096d19  pop     r13
0x180096d1b  pop     r12
0x180096d1d  pop     rdi
0x180096d1e  pop     rsi
0x180096d1f  pop     rbp
0x180096d20  retn
```
