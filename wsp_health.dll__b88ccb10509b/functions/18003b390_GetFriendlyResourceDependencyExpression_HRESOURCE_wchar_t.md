# GetFriendlyResourceDependencyExpression(_HRESOURCE *,wchar_t * *)

- ea: `0x18003b390`
- end: `0x18003b6c1`
- name: `?GetFriendlyResourceDependencyExpression@@YAKPEAU_HRESOURCE@@PEAPEA_W@Z`
- size: `817`
- prototype: `unsigned int __fastcall(HRESOURCE hResource, wchar_t **)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18002f790`

## callees

- `0x180002ae0`
- `0x180009ab4`
- `0x180009b10`
- `0x180016074`
- `0x18003b390`
- `0x18003b9e4`
- `0x18003baec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x18003b4a3`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x18003b4bf`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x18003b4a3`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x18003b4bf`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18003b473`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18003b473`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b442`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b634`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b63e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b442`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b634`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b63e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003b434`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003b585`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003b434`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003b585`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b5af`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b600`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b61d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b680`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b689`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b692`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b5af`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b600`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b61d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b680`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b689`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b692`
- `CLUSAPI!CloseCluster` at `0x18003b662`
- `CLUSAPI!CloseCluster` at `0x18003b662`
- `CLUSAPI!CloseClusterResource` at `0x18003b519`
- `CLUSAPI!CloseClusterResource` at `0x18003b670`
- `CLUSAPI!CloseClusterResource` at `0x18003b519`
- `CLUSAPI!CloseClusterResource` at `0x18003b670`
- `CLUSAPI!OpenClusterResource` at `0x18003b4ee`
- `CLUSAPI!OpenClusterResource` at `0x18003b4ee`
- `CLUSAPI!GetClusterFromResource` at `0x18003b452`
- `CLUSAPI!GetClusterFromResource` at `0x18003b452`

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
0x18003b390  mov     [rsp-8+arg_10], rbx
0x18003b395  push    rbp
0x18003b396  push    rsi
0x18003b397  push    rdi
0x18003b398  push    r12
0x18003b39a  push    r13
0x18003b39c  push    r14
0x18003b39e  push    r15
0x18003b3a0  lea     rbp, [rsp-27h]
0x18003b3a5  sub     rsp, 0C0h
0x18003b3ac  mov     rax, cs:__security_cookie
0x18003b3b3  xor     rax, rsp
0x18003b3b6  mov     [rbp+57h+var_40], rax
0x18003b3ba  xor     r13d, r13d
0x18003b3bd  mov     [rbp+57h+var_A0], rdx
0x18003b3c1  mov     [rbp+57h+String], r13
0x18003b3c5  mov     r12, rdx
0x18003b3c8  mov     dword ptr [rbp+57h+Delimiter], 5Bh ; '['
0x18003b3cf  mov     rsi, rcx
0x18003b3d2  mov     [rbp+57h+hMem], r13
0x18003b3d6  mov     r14d, r13d
0x18003b3d9  mov     edi, r13d
0x18003b3dc  mov     r15d, r13d
0x18003b3df  test    rcx, rcx
0x18003b3e2  jz      loc_18003B678
0x18003b3e8  test    rdx, rdx
0x18003b3eb  jz      loc_18003B678
0x18003b3f1  mov     [rdx], r13
0x18003b3f4  lea     rdx, [rbp+57h+String]; wchar_t **
0x18003b3f8  call    ?WrapGetResourceDependencyExpression@@YAKPEAU_HRESOURCE@@PEAPEA_W@Z; WrapGetResourceDependencyExpression(_HRESOURCE *,wchar_t * *)
0x18003b3fd  mov     r14, [rbp+57h+String]
0x18003b401  mov     ebx, eax
0x18003b403  test    eax, eax
0x18003b405  jnz     loc_18003B67D
0x18003b40b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003b40f  inc     rax
0x18003b412  cmp     [r14+rax*2], r13w
0x18003b417  jnz     short loc_18003B40F
0x18003b419  test    rax, rax
0x18003b41c  jnz     short loc_18003B42A
0x18003b41e  mov     [r12], r14
0x18003b422  mov     r14, r13
0x18003b425  jmp     loc_18003B67D
0x18003b42a  mov     edx, 400h; uBytes
0x18003b42f  mov     ecx, 40h ; '@'; uFlags
0x18003b434  call    cs:__imp_LocalAlloc
0x18003b43a  mov     rdi, rax
0x18003b43d  test    rax, rax
0x18003b440  jnz     short loc_18003B44F
0x18003b442  call    cs:__imp_GetLastError
0x18003b448  mov     ebx, eax
0x18003b44a  jmp     loc_18003B67D
0x18003b44f  mov     rcx, rsi; hResource
0x18003b452  call    cs:__imp_GetClusterFromResource
0x18003b458  mov     [rbp+57h+String], rax
0x18003b45c  mov     rsi, rax
0x18003b45f  test    rax, rax
0x18003b462  jz      short loc_18003B442
0x18003b464  lea     r8, [rbp+57h+Context]; Context
0x18003b468  mov     [rbp+57h+Context], r13
0x18003b46c  lea     rdx, [rbp+57h+Delimiter]; Delimiter
0x18003b470  mov     rcx, r14; String
0x18003b473  call    cs:__imp_wcstok_s
0x18003b479  mov     r12d, 200h
0x18003b47f  mov     rcx, rdi; wchar_t *
0x18003b482  mov     r8, rax; wchar_t *
0x18003b485  mov     edx, r12d; unsigned __int64
0x18003b488  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18003b48d  test    eax, eax
0x18003b48f  jns     short loc_18003B499
0x18003b491  movzx   ebx, ax
0x18003b494  jmp     loc_18003B65B
0x18003b499  lea     r8, [rbp+57h+Context]; Context
0x18003b49d  xor     ecx, ecx; String
0x18003b49f  lea     rdx, [rbp+57h+Delimiter]; Delimiter
0x18003b4a3  call    cs:__imp_wcstok
0x18003b4a9  mov     r13, rax
0x18003b4ac  test    r13, r13
0x18003b4af  jz      loc_18003B64B
0x18003b4b5  lea     r8, [rbp+57h+Context]; Context
0x18003b4b9  xor     ecx, ecx; String
0x18003b4bb  lea     rdx, [rbp+57h+Delimiter]; Delimiter
0x18003b4bf  call    cs:__imp_wcstok
0x18003b4c5  mov     r9d, 24h ; '$'; unsigned __int64
0x18003b4cb  lea     rcx, [rbp+57h+szResourceName]; wchar_t *
0x18003b4cf  mov     r8, r13; wchar_t *
0x18003b4d2  mov     [rbp+57h+var_A8], rax
0x18003b4d6  lea     edx, [r9+1]; unsigned __int64
0x18003b4da  call    ?StringCchCopyNW@@YAJPEA_W_KPEB_W1@Z; StringCchCopyNW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64)
0x18003b4df  test    eax, eax
0x18003b4e1  js      loc_18003B63E
0x18003b4e7  lea     rdx, [rbp+57h+szResourceName]; lpszResourceName
0x18003b4eb  mov     rcx, rsi; hCluster
0x18003b4ee  call    cs:__imp_OpenClusterResource
0x18003b4f4  mov     rsi, rax
0x18003b4f7  test    rax, rax
0x18003b4fa  jz      loc_18003B634
0x18003b500  lea     rdx, [rbp+57h+hMem]; wchar_t **
0x18003b504  mov     rcx, rax; hResource
0x18003b507  call    ?WrapGetResourceName@@YAKPEAU_HRESOURCE@@PEAPEA_W@Z; WrapGetResourceName(_HRESOURCE *,wchar_t * *)
0x18003b50c  mov     ebx, eax
0x18003b50e  test    eax, eax
0x18003b510  jnz     loc_18003B62E
0x18003b516  mov     rcx, rsi; hResource
0x18003b519  call    cs:__imp_CloseClusterResource
0x18003b51f  mov     r15, [rbp+57h+hMem]
0x18003b523  xor     r9d, r9d
0x18003b526  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18003b52a  mov     esi, r9d
0x18003b52d  mov     rcx, rdx
0x18003b530  inc     rcx
0x18003b533  cmp     [r15+rcx*2], r9w
0x18003b538  jnz     short loc_18003B530
0x18003b53a  add     r13, 48h ; 'H'
0x18003b53e  mov     rax, rdx
0x18003b541  mov     [rbp+57h+var_B0], r13
0x18003b545  inc     rax
0x18003b548  cmp     [r13+rax*2+0], r9w
0x18003b54e  jnz     short loc_18003B545
0x18003b550  lea     r8, [rax+rcx]
0x18003b554  inc     rdx
0x18003b557  cmp     [rdi+rdx*2], r9w
0x18003b55c  jnz     short loc_18003B554
0x18003b55e  mov     rcx, r12
0x18003b561  lea     rax, [r8+1]
0x18003b565  sub     rcx, rdx
0x18003b568  cmp     rcx, rax
0x18003b56b  ja      short loc_18003B5C0
0x18003b56d  lea     r13, [rdx+2]
0x18003b571  mov     ecx, 40h ; '@'; uFlags
0x18003b576  add     r13, r8
0x18003b579  mov     [rbp+57h+hMem], r13
0x18003b57d  lea     rdx, ds:0[r13*2]; uBytes
0x18003b585  call    cs:__imp_LocalAlloc
0x18003b58b  mov     r12, rax
0x18003b58e  test    rax, rax
0x18003b591  jz      loc_18003B634
0x18003b597  mov     r8, rdi; wchar_t *
0x18003b59a  mov     rdx, r13; unsigned __int64
0x18003b59d  mov     rcx, rax; wchar_t *
0x18003b5a0  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18003b5a5  mov     r13d, eax
0x18003b5a8  test    eax, eax
0x18003b5aa  js      short loc_18003B61A
0x18003b5ac  mov     rcx, rdi; hMem
0x18003b5af  call    cs:__imp_LocalFree
0x18003b5b5  mov     r13, [rbp+57h+var_B0]
0x18003b5b9  mov     rdi, r12
0x18003b5bc  mov     r12, [rbp+57h+hMem]
0x18003b5c0  lea     r8, asc_18010E948; "["
0x18003b5c7  mov     rdx, r12; unsigned __int64
0x18003b5ca  mov     rcx, rdi; wchar_t *
0x18003b5cd  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18003b5d2  test    eax, eax
0x18003b5d4  js      short loc_18003B629
0x18003b5d6  mov     r8, r15; wchar_t *
0x18003b5d9  mov     rdx, r12; unsigned __int64
0x18003b5dc  mov     rcx, rdi; wchar_t *
0x18003b5df  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18003b5e4  test    eax, eax
0x18003b5e6  js      short loc_18003B629
0x18003b5e8  mov     r8, r13; wchar_t *
0x18003b5eb  mov     rdx, r12; unsigned __int64
0x18003b5ee  mov     rcx, rdi; wchar_t *
0x18003b5f1  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18003b5f6  xor     r13d, r13d
0x18003b5f9  test    eax, eax
0x18003b5fb  js      short loc_18003B629
0x18003b5fd  mov     rcx, r15; hMem
0x18003b600  call    cs:__imp_LocalFree
0x18003b606  mov     rsi, [rbp+57h+String]
0x18003b60a  mov     r15d, r13d
0x18003b60d  mov     [rbp+57h+hMem], r13
0x18003b611  mov     r13, [rbp+57h+var_A8]
0x18003b615  jmp     loc_18003B4AC
0x18003b61a  mov     rcx, r12; hMem
0x18003b61d  call    cs:__imp_LocalFree
0x18003b623  movzx   ebx, r13w
0x18003b627  jmp     short loc_18003B65E
0x18003b629  movzx   ebx, ax
0x18003b62c  jmp     short loc_18003B65E
0x18003b62e  mov     r15, [rbp+57h+hMem]
0x18003b632  jmp     short loc_18003B65E
0x18003b634  call    cs:__imp_GetLastError
0x18003b63a  mov     ebx, eax
0x18003b63c  jmp     short loc_18003B65E
0x18003b63e  call    cs:__imp_GetLastError
0x18003b644  mov     ebx, eax
0x18003b646  xor     r13d, r13d
0x18003b649  jmp     short loc_18003B65B
0x18003b64b  mov     rax, [rbp+57h+var_A0]
0x18003b64f  mov     [rdi+r12*2-2], r13w
0x18003b655  mov     [rax], rdi
0x18003b658  mov     rdi, r13
0x18003b65b  mov     rsi, r13
0x18003b65e  mov     rcx, [rbp+57h+String]; hCluster
0x18003b662  call    cs:__imp_CloseCluster
0x18003b668  test    rsi, rsi
0x18003b66b  jz      short loc_18003B67D
0x18003b66d  mov     rcx, rsi; hResource
0x18003b670  call    cs:__imp_CloseClusterResource
0x18003b676  jmp     short loc_18003B67D
0x18003b678  mov     ebx, 57h ; 'W'
0x18003b67d  mov     rcx, r15; hMem
0x18003b680  call    cs:__imp_LocalFree
0x18003b686  mov     rcx, r14; hMem
0x18003b689  call    cs:__imp_LocalFree
0x18003b68f  mov     rcx, rdi; hMem
0x18003b692  call    cs:__imp_LocalFree
0x18003b698  mov     eax, ebx
0x18003b69a  mov     rcx, [rbp+57h+var_40]
0x18003b69e  xor     rcx, rsp; StackCookie
0x18003b6a1  call    __security_check_cookie
0x18003b6a6  mov     rbx, [rsp+0F0h+arg_10]
0x18003b6ae  add     rsp, 0C0h
0x18003b6b5  pop     r15
0x18003b6b7  pop     r14
0x18003b6b9  pop     r13
0x18003b6bb  pop     r12
0x18003b6bd  pop     rdi
0x18003b6be  pop     rsi
0x18003b6bf  pop     rbp
0x18003b6c0  retn
```
