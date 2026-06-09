# IShellItem_VerifyDownloadedItemType(IShellItem *,IBindCtx *,int *)

- ea: `0x180511ffc`
- end: `0x180512308`
- name: `?IShellItem_VerifyDownloadedItemType@@YAJPEAUIShellItem@@PEAUIBindCtx@@PEAH@Z`
- size: `780`
- prototype: `__int64 __fastcall(struct IShellItem *, struct IBindCtx *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1803d1b60`

## callees

- `0x180249490`
- `0x18039b6ac`
- `0x180511ffc`
- `0x1805b2010`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1805120ca`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180512116`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180512194`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1805121d5`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18051226b`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1805120ca`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180512116`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180512194`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1805121d5`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18051226b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x180512180`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x180512180`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180512129`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180512282`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1805122a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1805122b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1805122c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180512129`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180512282`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1805122a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1805122b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1805122c6`
- `SHLWAPI!__imp_MIME_GetExtensionW` at `0x1805121bc`
- `SHLWAPI!__imp_MIME_GetExtensionW` at `0x1805121bc`
- `api-ms-win-shell-associations-l1-1-0!AssocCreateForClasses` at `0x180512226`
- `api-ms-win-shell-associations-l1-1-0!AssocCreateForClasses` at `0x180512226`

## pseudocode

```c
__int64 __fastcall IShellItem_VerifyDownloadedItemType(struct IShellItem *a1, struct IBindCtx *a2, int *a3)
{
  struct IShellItemVtbl *lpVtbl; // rax
  unsigned int v6; // edi
  int v7; // ebx
  const WCHAR *ExtensionW; // rax
  LPCWSTR pszStr1; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR pszStr2; // [rsp+38h] [rbp-C8h] BYREF
  LPCWSTR pszPath; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v13; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR v14; // [rsp+50h] [rbp-B0h] BYREF
  void *ppv; // [rsp+58h] [rbp-A8h] BYREF
  ASSOCIATIONELEMENT rgClasses; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR v17[264]; // [rsp+80h] [rbp-80h] BYREF

  *a3 = 0;
  lpVtbl = a1->lpVtbl;
  v13 = 0;
  v6 = -2147023267;
  if ( ((__int64 (__fastcall *)(struct IShellItem *, GUID *, __int64 *))lpVtbl->QueryInterface)(
         a1,
         &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93,
         &v13) >= 0 )
  {
    pszPath = 0;
    _BindCtx_GetValue<unsigned short *>(a2, L"ServerFileName", &pszPath);
    pszStr2 = 0;
    _BindCtx_GetValue<unsigned short *>(a2, L"MimeType", &pszStr2);
    if ( pszPath )
    {
      if ( !pszStr2 )
        goto LABEL_8;
    }
    else if ( !pszStr2 )
    {
      v6 = 0;
LABEL_20:
      CoTaskMemFree((LPVOID)pszPath);
      CoTaskMemFree((LPVOID)pszStr2);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      return v6;
    }
    pszStr1 = 0;
    *a3 = StrCmpICW(L"text/html", pszStr2) == 0;
    if ( (*(int (__fastcall **)(__int64, const PROPERTYKEY *, LPCWSTR *))(*(_QWORD *)v13 + 136LL))(
           v13,
           &PKEY_MIMEType,
           &pszStr1) >= 0 )
    {
      v7 = StrCmpICW(pszStr1, pszStr2);
      CoTaskMemFree((LPVOID)pszStr1);
      v6 = v7 != 0 ? 0x8007065D : 0;
      if ( !v7 )
        goto LABEL_20;
    }
LABEL_8:
    pszStr1 = 0;
    if ( (*(int (__fastcall **)(__int64, const PROPERTYKEY *, LPCWSTR *))(*(_QWORD *)v13 + 136LL))(
           v13,
           &PKEY_FileExtension,
           &pszStr1) < 0 )
      goto LABEL_20;
    if ( !pszPath || (ExtensionW = PathFindExtensionW(pszPath), StrCmpICW(pszStr1, ExtensionW)) )
    {
      if ( !pszStr2 )
      {
LABEL_19:
        CoTaskMemFree((LPVOID)pszStr1);
        goto LABEL_20;
      }
      if ( !(unsigned int)MIME_GetExtensionW(pszStr2, v17, 260) || StrCmpICW(pszStr1, v17) )
      {
        rgClasses.pszClass = pszStr1;
        ppv = 0;
        rgClasses.ac = ASSOCCLASS_PROGID_STR;
        rgClasses.hkClass = 0;
        if ( AssocCreateForClasses(&rgClasses, 1u, &GUID_d7d31033_ccb5_40e3_8efa_a668f231003f, &ppv) >= 0 )
        {
          v14 = 0;
          if ( (*(int (__fastcall **)(void *, __int64, _QWORD, LPCWSTR *))(*(_QWORD *)ppv + 24LL))(
                 ppv,
                 2147942402LL,
                 0,
                 &v14) >= 0 )
          {
            v6 &= -(StrCmpICW(v14, pszStr2) != 0);
            CoTaskMemFree((LPVOID)v14);
          }
          (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
        }
        goto LABEL_19;
      }
    }
    v6 = 0;
    goto LABEL_19;
  }
  return v6;
}

```

## disassembly

```asm
0x180511ffc  mov     [rsp-8+arg_18], rbx
0x180512001  push    rbp
0x180512002  push    rsi
0x180512003  push    rdi
0x180512004  lea     rbp, [rsp-1A0h]
0x18051200c  sub     rsp, 2A0h
0x180512013  mov     rax, cs:__security_cookie
0x18051201a  xor     rax, rsp
0x18051201d  mov     [rbp+1B0h+var_20], rax
0x180512024  mov     dword ptr [r8], 0
0x18051202b  mov     rsi, r8
0x18051202e  mov     rax, [rcx]
0x180512031  lea     r8, [rsp+2B0h+var_268]
0x180512036  mov     rbx, rdx
0x180512039  mov     [rsp+2B0h+var_268], 0
0x180512042  lea     rdx, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93
0x180512049  mov     edi, 8007065Dh
0x18051204e  mov     rax, [rax]
0x180512051  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180512056  test    eax, eax
0x180512058  js      loc_1805122E3
0x18051205e  lea     r8, [rsp+2B0h+pszPath]
0x180512063  mov     [rsp+2B0h+pszStr2], 0
0x18051206c  lea     rdx, aServerfilename; "ServerFileName"
0x180512073  mov     [rsp+2B0h+pszPath], 0
0x18051207c  mov     rcx, rbx
0x18051207f  call    ??$_BindCtx_GetValue@PEAG@@YAJPEAUIBindCtx@@PEBGPEAPEAG@Z; _BindCtx_GetValue<ushort *>(IBindCtx *,ushort const *,ushort * *)
0x180512084  lea     r8, [rsp+2B0h+pszStr2]
0x180512089  mov     [rsp+2B0h+pszStr2], 0
0x180512092  lea     rdx, aMimetype; "MimeType"
0x180512099  mov     rcx, rbx
0x18051209c  call    ??$_BindCtx_GetValue@PEAG@@YAJPEAUIBindCtx@@PEBGPEAPEAG@Z; _BindCtx_GetValue<ushort *>(IBindCtx *,ushort const *,ushort * *)
0x1805120a1  cmp     [rsp+2B0h+pszPath], 0
0x1805120a7  mov     rdx, [rsp+2B0h+pszStr2]; pszStr2
0x1805120ac  jnz     short loc_1805120BA
0x1805120ae  test    rdx, rdx
0x1805120b1  jnz     short loc_1805120C3
0x1805120b3  xor     edi, edi
0x1805120b5  jmp     loc_1805122B0
0x1805120ba  test    rdx, rdx
0x1805120bd  jz      loc_180512145
0x1805120c3  lea     rcx, pszContentType; "text/html"
0x1805120ca  call    cs:__imp_StrCmpICW
0x1805120d1  nop     dword ptr [rax+rax+00h]
0x1805120d6  xor     ecx, ecx
0x1805120d8  mov     [rsp+2B0h+pszStr1], 0
0x1805120e1  test    eax, eax
0x1805120e3  lea     r8, [rsp+2B0h+pszStr1]
0x1805120e8  lea     rdx, PKEY_MIMEType
0x1805120ef  setz    cl
0x1805120f2  mov     [rsi], ecx
0x1805120f4  mov     rcx, [rsp+2B0h+var_268]
0x1805120f9  mov     rax, [rcx]
0x1805120fc  mov     rax, [rax+88h]
0x180512103  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180512108  test    eax, eax
0x18051210a  js      short loc_180512145
0x18051210c  mov     rdx, [rsp+2B0h+pszStr2]; pszStr2
0x180512111  mov     rcx, [rsp+2B0h+pszStr1]; pszStr1
0x180512116  call    cs:__imp_StrCmpICW
0x18051211d  nop     dword ptr [rax+rax+00h]
0x180512122  mov     rcx, [rsp+2B0h+pszStr1]; pv
0x180512127  mov     ebx, eax
0x180512129  call    cs:__imp_CoTaskMemFree
0x180512130  nop     dword ptr [rax+rax+00h]
0x180512135  mov     eax, ebx
0x180512137  neg     eax
0x180512139  sbb     ecx, ecx
0x18051213b  and     edi, ecx
0x18051213d  test    ebx, ebx
0x18051213f  jz      loc_1805122B0
0x180512145  mov     rcx, [rsp+2B0h+var_268]
0x18051214a  lea     r8, [rsp+2B0h+pszStr1]
0x18051214f  mov     [rsp+2B0h+pszStr1], 0
0x180512158  lea     rdx, PKEY_FileExtension
0x18051215f  mov     rax, [rcx]
0x180512162  mov     rax, [rax+88h]
0x180512169  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18051216e  test    eax, eax
0x180512170  js      loc_1805122B0
0x180512176  mov     rcx, [rsp+2B0h+pszPath]; pszPath
0x18051217b  test    rcx, rcx
0x18051217e  jz      short loc_1805121A4
0x180512180  call    cs:__imp_PathFindExtensionW
0x180512187  nop     dword ptr [rax+rax+00h]
0x18051218c  mov     rcx, [rsp+2B0h+pszStr1]; pszStr1
0x180512191  mov     rdx, rax; pszStr2
0x180512194  call    cs:__imp_StrCmpICW
0x18051219b  nop     dword ptr [rax+rax+00h]
0x1805121a0  test    eax, eax
0x1805121a2  jz      short loc_1805121E5
0x1805121a4  mov     rcx, [rsp+2B0h+pszStr2]
0x1805121a9  test    rcx, rcx
0x1805121ac  jz      loc_18051229F
0x1805121b2  mov     r8d, 104h
0x1805121b8  lea     rdx, [rbp+1B0h+var_230]
0x1805121bc  call    cs:__imp_MIME_GetExtensionW
0x1805121c3  nop     dword ptr [rax+rax+00h]
0x1805121c8  test    eax, eax
0x1805121ca  jz      short loc_1805121EC
0x1805121cc  mov     rcx, [rsp+2B0h+pszStr1]; pszStr1
0x1805121d1  lea     rdx, [rbp+1B0h+var_230]; pszStr2
0x1805121d5  call    cs:__imp_StrCmpICW
0x1805121dc  nop     dword ptr [rax+rax+00h]
0x1805121e1  test    eax, eax
0x1805121e3  jnz     short loc_1805121EC
0x1805121e5  xor     edi, edi
0x1805121e7  jmp     loc_18051229F
0x1805121ec  mov     rax, [rsp+2B0h+pszStr1]
0x1805121f1  lea     r9, [rsp+2B0h+ppv]; ppv
0x1805121f6  lea     r8, _GUID_d7d31033_ccb5_40e3_8efa_a668f231003f; riid
0x1805121fd  mov     [rsp+2B0h+rgClasses.pszClass], rax
0x180512202  mov     edx, 1; cClasses
0x180512207  mov     [rsp+2B0h+ppv], 0
0x180512210  lea     rcx, [rsp+2B0h+rgClasses]; rgClasses
0x180512215  mov     [rsp+2B0h+rgClasses.ac], 2
0x18051221d  mov     [rsp+2B0h+rgClasses.hkClass], 0
0x180512226  call    cs:__imp_AssocCreateForClasses
0x18051222d  nop     dword ptr [rax+rax+00h]
0x180512232  test    eax, eax
0x180512234  js      short loc_18051229F
0x180512236  mov     rcx, [rsp+2B0h+ppv]
0x18051223b  lea     r9, [rsp+2B0h+var_260]
0x180512240  mov     [rsp+2B0h+var_260], 0
0x180512249  xor     r8d, r8d
0x18051224c  mov     edx, 80070002h
0x180512251  mov     rax, [rcx]
0x180512254  mov     rax, [rax+18h]
0x180512258  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18051225d  test    eax, eax
0x18051225f  js      short loc_18051228E
0x180512261  mov     rdx, [rsp+2B0h+pszStr2]; pszStr2
0x180512266  mov     rcx, [rsp+2B0h+var_260]; pszStr1
0x18051226b  call    cs:__imp_StrCmpICW
0x180512272  nop     dword ptr [rax+rax+00h]
0x180512277  neg     eax
0x180512279  sbb     ecx, ecx
0x18051227b  and     edi, ecx
0x18051227d  mov     rcx, [rsp+2B0h+var_260]; pv
0x180512282  call    cs:__imp_CoTaskMemFree
0x180512289  nop     dword ptr [rax+rax+00h]
0x18051228e  mov     rcx, [rsp+2B0h+ppv]
0x180512293  mov     rax, [rcx]
0x180512296  mov     rax, [rax+10h]
0x18051229a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18051229f  mov     rcx, [rsp+2B0h+pszStr1]; pv
0x1805122a4  call    cs:__imp_CoTaskMemFree
0x1805122ab  nop     dword ptr [rax+rax+00h]
0x1805122b0  mov     rcx, [rsp+2B0h+pszPath]; pv
0x1805122b5  call    cs:__imp_CoTaskMemFree
0x1805122bc  nop     dword ptr [rax+rax+00h]
0x1805122c1  mov     rcx, [rsp+2B0h+pszStr2]; pv
0x1805122c6  call    cs:__imp_CoTaskMemFree
0x1805122cd  nop     dword ptr [rax+rax+00h]
0x1805122d2  mov     rcx, [rsp+2B0h+var_268]
0x1805122d7  mov     rdx, [rcx]
0x1805122da  mov     rax, [rdx+10h]
0x1805122de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1805122e3  mov     eax, edi
0x1805122e5  mov     rcx, [rbp+1B0h+var_20]
0x1805122ec  xor     rcx, rsp; StackCookie
0x1805122ef  call    __security_check_cookie
0x1805122f4  mov     rbx, [rsp+2B0h+arg_18]
0x1805122fc  add     rsp, 2A0h
0x180512303  pop     rdi
0x180512304  pop     rsi
0x180512305  pop     rbp
0x180512306  retn
```
