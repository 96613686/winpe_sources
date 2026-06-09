# GetHostDisplayNameFromUrlInternal(ushort const *,uint,ushort * *,int *,int,int)

- ea: `0x18012481c`
- end: `0x180124ad6`
- name: `?GetHostDisplayNameFromUrlInternal@@YAJPEBGIPEAPEAGPEAHHH@Z`
- size: `698`
- prototype: `__int64 __fastcall(const unsigned __int16 *, __int64, unsigned __int16 **, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800f1030`

## callees

- `0x1800162d4`
- `0x180024ea0`
- `0x18008f4f8`
- `0x1801008f0`
- `0x1801246dc`
- `0x18012481c`
- `0x180128660`
- `0x180128720`
- `0x180129010`

## import_xrefs

- `iertutil!CreateUri` at `0x18012486c`
- `iertutil!CreateUri` at `0x18012486c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x180124916`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x180124916`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrTrimW` at `0x1801249be`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrTrimW` at `0x1801249be`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1801249e0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1801249e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180124a75`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180124a75`
- `api-ms-win-core-url-l1-1-0!PathCreateFromUrlW` at `0x1801248f9`
- `api-ms-win-core-url-l1-1-0!PathCreateFromUrlW` at `0x1801248f9`
- `OLEAUT32!__imp_SysFreeString` at `0x180124959`
- `OLEAUT32!__imp_SysFreeString` at `0x180124a4a`
- `OLEAUT32!__imp_SysFreeString` at `0x180124a97`
- `OLEAUT32!__imp_SysFreeString` at `0x180124959`
- `OLEAUT32!__imp_SysFreeString` at `0x180124a4a`
- `OLEAUT32!__imp_SysFreeString` at `0x180124a97`

## pseudocode

```c
__int64 __fastcall GetHostDisplayNameFromUrlInternal(
        const unsigned __int16 *a1,
        __int64 a2,
        unsigned __int16 **a3,
        int *a4)
{
  HRESULT v6; // ebx
  int v7; // esi
  __int64 v8; // rdx
  PWSTR v9; // rcx
  WCHAR v10; // ax
  unsigned __int16 *v11; // rax
  PWSTR psz; // [rsp+30h] [rbp-D0h] BYREF
  PCWSTR pszUrl; // [rsp+38h] [rbp-C8h] BYREF
  IUri *ppURI; // [rsp+40h] [rbp-C0h] BYREF
  int v16; // [rsp+48h] [rbp-B8h] BYREF
  DWORD pcchPath; // [rsp+4Ch] [rbp-B4h] BYREF
  WCHAR pszPath[2088]; // [rsp+50h] [rbp-B0h] BYREF

  *a3 = 0;
  *a4 = 0;
  ppURI = 0;
  v6 = CreateUri(a1, 0, 0, &ppURI);
  if ( v6 >= 0 )
  {
    v16 = 0;
    v6 = ((__int64 (__fastcall *)(IUri *, int *))ppURI->lpVtbl->GetScheme)(ppURI, &v16);
    if ( v6 >= 0 )
    {
      v7 = 1;
      psz = 0;
      if ( v16 == 9 )
      {
        pszUrl = 0;
        v6 = ((__int64 (__fastcall *)(IUri *, PCWSTR *))ppURI->lpVtbl->GetAbsoluteUri)(ppURI, &pszUrl);
        if ( v6 >= 0 )
        {
          pcchPath = 2084;
          v6 = PathCreateFromUrlW(pszUrl, pszPath, &pcchPath, 0);
          if ( v6 >= 0 )
          {
            *a4 = 1;
            v7 = 0;
            if ( PathIsUNCW(pszPath) )
              FormatUNCPath(pszPath, v8, a4);
            ATL::CComBSTR::operator=(&psz, pszPath);
            v6 = psz == 0 ? 0x8007000E : 0;
          }
        }
        SysFreeString((BSTR)pszUrl);
      }
      else
      {
        v6 = ((__int64 (__fastcall *)(IUri *, __int64, PWSTR *))ppURI->lpVtbl->GetPropertyBSTR)(ppURI, 6, &psz);
      }
      if ( v6 >= 0 )
      {
        v9 = psz;
        v10 = *psz;
        if ( *psz )
        {
          do
          {
            if ( v10 < 0x20u )
              *v9 = 32;
            v10 = *++v9;
          }
          while ( *v9 );
          v9 = psz;
        }
        StrTrimW(v9, L" ");
        if ( *psz )
        {
          v11 = (unsigned __int16 *)LocalAlloc(0, 0x1048u);
          *a3 = v11;
          if ( v11 )
          {
            if ( !v7 )
              goto LABEL_23;
            pszUrl = 0;
            v6 = ((__int64 (__fastcall *)(IUri *, PCWSTR *))ppURI->lpVtbl->GetSchemeName)(ppURI, &pszUrl);
            if ( v6 >= 0 )
              v6 = StringCchPrintfW(*a3, 0x824u, L"%s://%s", pszUrl, psz);
            SysFreeString((BSTR)pszUrl);
            if ( v6 < 0 )
            {
LABEL_23:
              v6 = StringCchCopyW(*a3, 0x824u, psz);
              if ( v6 < 0 )
              {
                LocalFree(*a3);
                *a3 = 0;
              }
            }
          }
          else
          {
            v6 = -2147024882;
          }
        }
        else
        {
          v6 = -2147467259;
        }
      }
      SysFreeString(psz);
    }
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppURI);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18012481c  mov     [rsp-8+arg_8], rbx
0x180124821  push    rbp
0x180124822  push    rsi
0x180124823  push    rdi
0x180124824  push    r14
0x180124826  push    r15
0x180124828  lea     rbp, [rsp-0FB0h]
0x180124830  mov     eax, 10B0h
0x180124835  call    _alloca_probe
0x18012483a  sub     rsp, rax
0x18012483d  mov     rax, cs:__security_cookie
0x180124844  xor     rax, rsp
0x180124847  mov     [rbp+0FD0h+var_30], rax
0x18012484e  xor     r15d, r15d
0x180124851  mov     r14, r9
0x180124854  mov     [r8], r15
0x180124857  mov     rdi, r8
0x18012485a  mov     [r9], r15d
0x18012485d  xor     r8d, r8d; dwReserved
0x180124860  lea     r9, [rsp+10D0h+ppURI]; ppURI
0x180124865  mov     [rsp+10D0h+ppURI], r15
0x18012486a  xor     edx, edx; dwFlags
0x18012486c  call    cs:__imp_CreateUri
0x180124873  nop     dword ptr [rax+rax+00h]
0x180124878  mov     ebx, eax
0x18012487a  test    eax, eax
0x18012487c  js      loc_180124AA3
0x180124882  mov     rcx, [rsp+10D0h+ppURI]
0x180124887  lea     rdx, [rsp+10D0h+var_1088]
0x18012488c  mov     [rsp+10D0h+var_1088], r15d
0x180124891  mov     rax, [rcx]
0x180124894  mov     rax, [rax+0C0h]
0x18012489b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801248a0  mov     ebx, eax
0x1801248a2  test    eax, eax
0x1801248a4  js      loc_180124AA3
0x1801248aa  cmp     [rsp+10D0h+var_1088], 9
0x1801248af  lea     esi, [r15+1]
0x1801248b3  mov     rcx, [rsp+10D0h+ppURI]
0x1801248b8  mov     [rsp+10D0h+psz], r15
0x1801248bd  jnz     loc_180124967
0x1801248c3  mov     [rsp+10D0h+pszUrl], r15
0x1801248c8  lea     rdx, [rsp+10D0h+pszUrl]
0x1801248cd  mov     rax, [rcx]
0x1801248d0  mov     rax, [rax+38h]
0x1801248d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801248d9  mov     ebx, eax
0x1801248db  test    eax, eax
0x1801248dd  js      short loc_180124954
0x1801248df  mov     rcx, [rsp+10D0h+pszUrl]; pszUrl
0x1801248e4  lea     r8, [rsp+10D0h+pcchPath]; pcchPath
0x1801248e9  xor     r9d, r9d; dwFlags
0x1801248ec  mov     [rsp+10D0h+pcchPath], 824h
0x1801248f4  lea     rdx, [rsp+10D0h+pszPath]; pszPath
0x1801248f9  call    cs:__imp_PathCreateFromUrlW
0x180124900  nop     dword ptr [rax+rax+00h]
0x180124905  mov     ebx, eax
0x180124907  test    eax, eax
0x180124909  js      short loc_180124954
0x18012490b  mov     [r14], esi
0x18012490e  lea     rcx, [rsp+10D0h+pszPath]; pszPath
0x180124913  mov     esi, r15d
0x180124916  call    cs:__imp_PathIsUNCW
0x18012491d  nop     dword ptr [rax+rax+00h]
0x180124922  test    eax, eax
0x180124924  jz      short loc_180124933
0x180124926  mov     r8, r14; int *
0x180124929  lea     rcx, [rsp+10D0h+pszPath]; unsigned __int16 *
0x18012492e  call    ?FormatUNCPath@@YAXPEAGKPEAH@Z; FormatUNCPath(ushort *,ulong,int *)
0x180124933  lea     rdx, [rsp+10D0h+pszPath]
0x180124938  lea     rcx, [rsp+10D0h+psz]
0x18012493d  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x180124942  mov     rax, [rsp+10D0h+psz]
0x180124947  neg     rax
0x18012494a  sbb     ebx, ebx
0x18012494c  not     ebx
0x18012494e  and     ebx, 8007000Eh
0x180124954  mov     rcx, [rsp+10D0h+pszUrl]; bstrString
0x180124959  call    cs:__imp_SysFreeString
0x180124960  nop     dword ptr [rax+rax+00h]
0x180124965  jmp     short loc_180124984
0x180124967  mov     rax, [rcx]
0x18012496a  lea     r8, [rsp+10D0h+psz]
0x18012496f  mov     r9d, 4
0x180124975  mov     rax, [rax+18h]
0x180124979  lea     edx, [r9+2]
0x18012497d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180124982  mov     ebx, eax
0x180124984  test    ebx, ebx
0x180124986  js      loc_180124A92
0x18012498c  mov     rcx, [rsp+10D0h+psz]
0x180124991  movzx   eax, word ptr [rcx]
0x180124994  test    ax, ax
0x180124997  jz      short loc_1801249B7
0x180124999  mov     edx, 20h ; ' '
0x18012499e  cmp     ax, dx
0x1801249a1  jnb     short loc_1801249A6
0x1801249a3  mov     [rcx], dx
0x1801249a6  add     rcx, 2
0x1801249aa  movzx   eax, word ptr [rcx]
0x1801249ad  test    ax, ax
0x1801249b0  jnz     short loc_18012499E
0x1801249b2  mov     rcx, [rsp+10D0h+psz]; psz
0x1801249b7  lea     rdx, asc_180143AD0; " "
0x1801249be  call    cs:__imp_StrTrimW
0x1801249c5  nop     dword ptr [rax+rax+00h]
0x1801249ca  mov     rax, [rsp+10D0h+psz]
0x1801249cf  cmp     [rax], r15w
0x1801249d3  jz      loc_180124A8D
0x1801249d9  mov     edx, 1048h; uBytes
0x1801249de  xor     ecx, ecx; uFlags
0x1801249e0  call    cs:__imp_LocalAlloc
0x1801249e7  nop     dword ptr [rax+rax+00h]
0x1801249ec  mov     [rdi], rax
0x1801249ef  test    rax, rax
0x1801249f2  jz      loc_180124A86
0x1801249f8  test    esi, esi
0x1801249fa  jz      short loc_180124A5A
0x1801249fc  mov     rcx, [rsp+10D0h+ppURI]
0x180124a01  lea     rdx, [rsp+10D0h+pszUrl]
0x180124a06  mov     [rsp+10D0h+pszUrl], r15
0x180124a0b  mov     rax, [rcx]
0x180124a0e  mov     rax, [rax+98h]
0x180124a15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180124a1a  mov     ebx, eax
0x180124a1c  test    eax, eax
0x180124a1e  js      short loc_180124A45
0x180124a20  mov     rax, [rsp+10D0h+psz]
0x180124a25  lea     r8, aSS; "%s://%s"
0x180124a2c  mov     r9, [rsp+10D0h+pszUrl]
0x180124a31  mov     edx, 824h; unsigned __int64
0x180124a36  mov     rcx, [rdi]; unsigned __int16 *
0x180124a39  mov     [rsp+10D0h+var_10B0], rax
0x180124a3e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180124a43  mov     ebx, eax
0x180124a45  mov     rcx, [rsp+10D0h+pszUrl]; bstrString
0x180124a4a  call    cs:__imp_SysFreeString
0x180124a51  nop     dword ptr [rax+rax+00h]
0x180124a56  test    ebx, ebx
0x180124a58  jns     short loc_180124A92
0x180124a5a  mov     r8, [rsp+10D0h+psz]; unsigned __int16 *
0x180124a5f  mov     edx, 824h; unsigned __int64
0x180124a64  mov     rcx, [rdi]; unsigned __int16 *
0x180124a67  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180124a6c  mov     ebx, eax
0x180124a6e  test    eax, eax
0x180124a70  jns     short loc_180124A92
0x180124a72  mov     rcx, [rdi]; hMem
0x180124a75  call    cs:__imp_LocalFree
0x180124a7c  nop     dword ptr [rax+rax+00h]
0x180124a81  mov     [rdi], r15
0x180124a84  jmp     short loc_180124A92
0x180124a86  mov     ebx, 8007000Eh
0x180124a8b  jmp     short loc_180124A92
0x180124a8d  mov     ebx, 80004005h
0x180124a92  mov     rcx, [rsp+10D0h+psz]; bstrString
0x180124a97  call    cs:__imp_SysFreeString
0x180124a9e  nop     dword ptr [rax+rax+00h]
0x180124aa3  lea     rcx, [rsp+10D0h+ppURI]
0x180124aa8  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180124aad  mov     eax, ebx
0x180124aaf  mov     rcx, [rbp+0FD0h+var_30]
0x180124ab6  xor     rcx, rsp; StackCookie
0x180124ab9  call    __security_check_cookie
0x180124abe  mov     rbx, [rsp+10D0h+arg_8]
0x180124ac6  add     rsp, 10B0h
0x180124acd  pop     r15
0x180124acf  pop     r14
0x180124ad1  pop     rdi
0x180124ad2  pop     rsi
0x180124ad3  pop     rbp
0x180124ad4  retn
```
