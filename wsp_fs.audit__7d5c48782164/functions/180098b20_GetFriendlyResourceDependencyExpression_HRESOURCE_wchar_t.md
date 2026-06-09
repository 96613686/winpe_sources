# GetFriendlyResourceDependencyExpression(_HRESOURCE *,wchar_t * *)

- ea: `0x180098b20`
- end: `0x180098ec4`
- name: `?GetFriendlyResourceDependencyExpression@@YAKPEAU_HRESOURCE@@PEAPEA_W@Z`
- size: `932`
- prototype: `unsigned int __fastcall(HRESOURCE hResource, wchar_t **)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180034610`

## callees

- `0x180002ad0`
- `0x180009f34`
- `0x180009f90`
- `0x180019aa0`
- `0x180098b20`
- `0x180099274`
- `0x1800993a8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x180098c4b`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x180098c6d`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x180098c4b`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x180098c6d`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180098c15`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180098c15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098bd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098e0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098e1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098bd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098e0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098e1c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180098bc4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180098d45`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180098bc4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180098d45`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180098d75`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180098dcc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180098def`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180098e70`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180098e7f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180098e8e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180098d75`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180098dcc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180098def`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180098e70`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180098e7f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180098e8e`
- `CLUSAPI!CloseClusterResource` at `0x180098cd3`
- `CLUSAPI!CloseClusterResource` at `0x180098e5a`
- `CLUSAPI!CloseClusterResource` at `0x180098cd3`
- `CLUSAPI!CloseClusterResource` at `0x180098e5a`
- `CLUSAPI!CloseCluster` at `0x180098e46`
- `CLUSAPI!CloseCluster` at `0x180098e46`
- `CLUSAPI!GetClusterFromResource` at `0x180098bee`
- `CLUSAPI!GetClusterFromResource` at `0x180098bee`
- `CLUSAPI!OpenClusterResource` at `0x180098ca2`
- `CLUSAPI!OpenClusterResource` at `0x180098ca2`

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
0x180098b20  mov     [rsp-8+arg_10], rbx
0x180098b25  push    rbp
0x180098b26  push    rsi
0x180098b27  push    rdi
0x180098b28  push    r12
0x180098b2a  push    r13
0x180098b2c  push    r14
0x180098b2e  push    r15
0x180098b30  lea     rbp, [rsp-27h]
0x180098b35  sub     rsp, 0C0h
0x180098b3c  mov     rax, cs:__security_cookie
0x180098b43  xor     rax, rsp
0x180098b46  mov     [rbp+57h+var_40], rax
0x180098b4a  xor     r13d, r13d
0x180098b4d  mov     [rbp+57h+var_A0], rdx
0x180098b51  mov     [rbp+57h+String], r13
0x180098b55  mov     r12, rdx
0x180098b58  mov     dword ptr [rbp+57h+Delimiter], 5Bh ; '['
0x180098b5f  mov     rsi, rcx
0x180098b62  mov     [rbp+57h+hMem], r13
0x180098b66  mov     r14d, r13d
0x180098b69  mov     edi, r13d
0x180098b6c  mov     r15d, r13d
0x180098b6f  test    rcx, rcx
0x180098b72  jz      loc_180098E68
0x180098b78  test    rdx, rdx
0x180098b7b  jz      loc_180098E68
0x180098b81  mov     [rdx], r13
0x180098b84  lea     rdx, [rbp+57h+String]; wchar_t **
0x180098b88  call    ?WrapGetResourceDependencyExpression@@YAKPEAU_HRESOURCE@@PEAPEA_W@Z; WrapGetResourceDependencyExpression(_HRESOURCE *,wchar_t * *)
0x180098b8d  mov     r14, [rbp+57h+String]
0x180098b91  mov     ebx, eax
0x180098b93  test    eax, eax
0x180098b95  jnz     loc_180098E6D
0x180098b9b  or      rax, 0FFFFFFFFFFFFFFFFh
0x180098b9f  inc     rax
0x180098ba2  cmp     [r14+rax*2], r13w
0x180098ba7  jnz     short loc_180098B9F
0x180098ba9  test    rax, rax
0x180098bac  jnz     short loc_180098BBA
0x180098bae  mov     [r12], r14
0x180098bb2  mov     r14, r13
0x180098bb5  jmp     loc_180098E6D
0x180098bba  mov     edx, 400h; uBytes
0x180098bbf  mov     ecx, 40h ; '@'; uFlags
0x180098bc4  call    cs:__imp_LocalAlloc
0x180098bcb  nop     dword ptr [rax+rax+00h]
0x180098bd0  mov     rdi, rax
0x180098bd3  test    rax, rax
0x180098bd6  jnz     short loc_180098BEB
0x180098bd8  call    cs:__imp_GetLastError
0x180098bdf  nop     dword ptr [rax+rax+00h]
0x180098be4  mov     ebx, eax
0x180098be6  jmp     loc_180098E6D
0x180098beb  mov     rcx, rsi; hResource
0x180098bee  call    cs:__imp_GetClusterFromResource
0x180098bf5  nop     dword ptr [rax+rax+00h]
0x180098bfa  mov     [rbp+57h+String], rax
0x180098bfe  mov     rsi, rax
0x180098c01  test    rax, rax
0x180098c04  jz      short loc_180098BD8
0x180098c06  lea     r8, [rbp+57h+Context]; Context
0x180098c0a  mov     [rbp+57h+Context], r13
0x180098c0e  lea     rdx, [rbp+57h+Delimiter]; Delimiter
0x180098c12  mov     rcx, r14; String
0x180098c15  call    cs:__imp_wcstok_s
0x180098c1c  nop     dword ptr [rax+rax+00h]
0x180098c21  mov     r12d, 200h
0x180098c27  mov     rcx, rdi; wchar_t *
0x180098c2a  mov     r8, rax; wchar_t *
0x180098c2d  mov     edx, r12d; unsigned __int64
0x180098c30  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180098c35  test    eax, eax
0x180098c37  jns     short loc_180098C41
0x180098c39  movzx   ebx, ax
0x180098c3c  jmp     loc_180098E3F
0x180098c41  lea     r8, [rbp+57h+Context]; Context
0x180098c45  xor     ecx, ecx; String
0x180098c47  lea     rdx, [rbp+57h+Delimiter]; Delimiter
0x180098c4b  call    cs:__imp_wcstok
0x180098c52  nop     dword ptr [rax+rax+00h]
0x180098c57  mov     r13, rax
0x180098c5a  test    r13, r13
0x180098c5d  jz      loc_180098E2F
0x180098c63  lea     r8, [rbp+57h+Context]; Context
0x180098c67  xor     ecx, ecx; String
0x180098c69  lea     rdx, [rbp+57h+Delimiter]; Delimiter
0x180098c6d  call    cs:__imp_wcstok
0x180098c74  nop     dword ptr [rax+rax+00h]
0x180098c79  mov     r9d, 24h ; '$'; unsigned __int64
0x180098c7f  lea     rcx, [rbp+57h+szResourceName]; wchar_t *
0x180098c83  mov     r8, r13; wchar_t *
0x180098c86  mov     [rbp+57h+var_A8], rax
0x180098c8a  lea     edx, [r9+1]; unsigned __int64
0x180098c8e  call    ?StringCchCopyNW@@YAJPEA_W_KPEB_W1@Z; StringCchCopyNW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64)
0x180098c93  test    eax, eax
0x180098c95  js      loc_180098E1C
0x180098c9b  lea     rdx, [rbp+57h+szResourceName]; lpszResourceName
0x180098c9f  mov     rcx, rsi; hCluster
0x180098ca2  call    cs:__imp_OpenClusterResource
0x180098ca9  nop     dword ptr [rax+rax+00h]
0x180098cae  mov     rsi, rax
0x180098cb1  test    rax, rax
0x180098cb4  jz      loc_180098E0C
0x180098cba  lea     rdx, [rbp+57h+hMem]; wchar_t **
0x180098cbe  mov     rcx, rax; hResource
0x180098cc1  call    ?WrapGetResourceName@@YAKPEAU_HRESOURCE@@PEAPEA_W@Z; WrapGetResourceName(_HRESOURCE *,wchar_t * *)
0x180098cc6  mov     ebx, eax
0x180098cc8  test    eax, eax
0x180098cca  jnz     loc_180098E06
0x180098cd0  mov     rcx, rsi; hResource
0x180098cd3  call    cs:__imp_CloseClusterResource
0x180098cda  nop     dword ptr [rax+rax+00h]
0x180098cdf  mov     r15, [rbp+57h+hMem]
0x180098ce3  xor     r9d, r9d
0x180098ce6  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180098cea  mov     esi, r9d
0x180098ced  mov     rcx, rdx
0x180098cf0  inc     rcx
0x180098cf3  cmp     [r15+rcx*2], r9w
0x180098cf8  jnz     short loc_180098CF0
0x180098cfa  add     r13, 48h ; 'H'
0x180098cfe  mov     rax, rdx
0x180098d01  mov     [rbp+57h+var_B0], r13
0x180098d05  inc     rax
0x180098d08  cmp     [r13+rax*2+0], r9w
0x180098d0e  jnz     short loc_180098D05
0x180098d10  lea     r8, [rax+rcx]
0x180098d14  inc     rdx
0x180098d17  cmp     [rdi+rdx*2], r9w
0x180098d1c  jnz     short loc_180098D14
0x180098d1e  mov     rcx, r12
0x180098d21  lea     rax, [r8+1]
0x180098d25  sub     rcx, rdx
0x180098d28  cmp     rcx, rax
0x180098d2b  ja      short loc_180098D8C
0x180098d2d  lea     r13, [rdx+2]
0x180098d31  mov     ecx, 40h ; '@'; uFlags
0x180098d36  add     r13, r8
0x180098d39  mov     [rbp+57h+hMem], r13
0x180098d3d  lea     rdx, ds:0[r13*2]; uBytes
0x180098d45  call    cs:__imp_LocalAlloc
0x180098d4c  nop     dword ptr [rax+rax+00h]
0x180098d51  mov     r12, rax
0x180098d54  test    rax, rax
0x180098d57  jz      loc_180098E0C
0x180098d5d  mov     r8, rdi; wchar_t *
0x180098d60  mov     rdx, r13; unsigned __int64
0x180098d63  mov     rcx, rax; wchar_t *
0x180098d66  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180098d6b  mov     r13d, eax
0x180098d6e  test    eax, eax
0x180098d70  js      short loc_180098DEC
0x180098d72  mov     rcx, rdi; hMem
0x180098d75  call    cs:__imp_LocalFree
0x180098d7c  nop     dword ptr [rax+rax+00h]
0x180098d81  mov     r13, [rbp+57h+var_B0]
0x180098d85  mov     rdi, r12
0x180098d88  mov     r12, [rbp+57h+hMem]
0x180098d8c  lea     r8, asc_180137E68; "["
0x180098d93  mov     rdx, r12; unsigned __int64
0x180098d96  mov     rcx, rdi; wchar_t *
0x180098d99  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180098d9e  test    eax, eax
0x180098da0  js      short loc_180098E01
0x180098da2  mov     r8, r15; wchar_t *
0x180098da5  mov     rdx, r12; unsigned __int64
0x180098da8  mov     rcx, rdi; wchar_t *
0x180098dab  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180098db0  test    eax, eax
0x180098db2  js      short loc_180098E01
0x180098db4  mov     r8, r13; wchar_t *
0x180098db7  mov     rdx, r12; unsigned __int64
0x180098dba  mov     rcx, rdi; wchar_t *
0x180098dbd  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180098dc2  xor     r13d, r13d
0x180098dc5  test    eax, eax
0x180098dc7  js      short loc_180098E01
0x180098dc9  mov     rcx, r15; hMem
0x180098dcc  call    cs:__imp_LocalFree
0x180098dd3  nop     dword ptr [rax+rax+00h]
0x180098dd8  mov     rsi, [rbp+57h+String]
0x180098ddc  mov     r15d, r13d
0x180098ddf  mov     [rbp+57h+hMem], r13
0x180098de3  mov     r13, [rbp+57h+var_A8]
0x180098de7  jmp     loc_180098C5A
0x180098dec  mov     rcx, r12; hMem
0x180098def  call    cs:__imp_LocalFree
0x180098df6  nop     dword ptr [rax+rax+00h]
0x180098dfb  movzx   ebx, r13w
0x180098dff  jmp     short loc_180098E42
0x180098e01  movzx   ebx, ax
0x180098e04  jmp     short loc_180098E42
0x180098e06  mov     r15, [rbp+57h+hMem]
0x180098e0a  jmp     short loc_180098E42
0x180098e0c  call    cs:__imp_GetLastError
0x180098e13  nop     dword ptr [rax+rax+00h]
0x180098e18  mov     ebx, eax
0x180098e1a  jmp     short loc_180098E42
0x180098e1c  call    cs:__imp_GetLastError
0x180098e23  nop     dword ptr [rax+rax+00h]
0x180098e28  mov     ebx, eax
0x180098e2a  xor     r13d, r13d
0x180098e2d  jmp     short loc_180098E3F
0x180098e2f  mov     rax, [rbp+57h+var_A0]
0x180098e33  mov     [rdi+r12*2-2], r13w
0x180098e39  mov     [rax], rdi
0x180098e3c  mov     rdi, r13
0x180098e3f  mov     rsi, r13
0x180098e42  mov     rcx, [rbp+57h+String]; hCluster
0x180098e46  call    cs:__imp_CloseCluster
0x180098e4d  nop     dword ptr [rax+rax+00h]
0x180098e52  test    rsi, rsi
0x180098e55  jz      short loc_180098E6D
0x180098e57  mov     rcx, rsi; hResource
0x180098e5a  call    cs:__imp_CloseClusterResource
0x180098e61  nop     dword ptr [rax+rax+00h]
0x180098e66  jmp     short loc_180098E6D
0x180098e68  mov     ebx, 57h ; 'W'
0x180098e6d  mov     rcx, r15; hMem
0x180098e70  call    cs:__imp_LocalFree
0x180098e77  nop     dword ptr [rax+rax+00h]
0x180098e7c  mov     rcx, r14; hMem
0x180098e7f  call    cs:__imp_LocalFree
0x180098e86  nop     dword ptr [rax+rax+00h]
0x180098e8b  mov     rcx, rdi; hMem
0x180098e8e  call    cs:__imp_LocalFree
0x180098e95  nop     dword ptr [rax+rax+00h]
0x180098e9a  mov     eax, ebx
0x180098e9c  mov     rcx, [rbp+57h+var_40]
0x180098ea0  xor     rcx, rsp; StackCookie
0x180098ea3  call    __security_check_cookie
0x180098ea8  mov     rbx, [rsp+0F0h+arg_10]
0x180098eb0  add     rsp, 0C0h
0x180098eb7  pop     r15
0x180098eb9  pop     r14
0x180098ebb  pop     r13
0x180098ebd  pop     r12
0x180098ebf  pop     rdi
0x180098ec0  pop     rsi
0x180098ec1  pop     rbp
0x180098ec2  retn
```
