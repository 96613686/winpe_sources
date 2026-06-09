# GetHostDisplayNameFromUrlInternal(ushort const *,uint,ushort * *,int *,int,int)

- ea: `0x18011802c`
- end: `0x1801182af`
- name: `?GetHostDisplayNameFromUrlInternal@@YAJPEBGIPEAPEAGPEAHHH@Z`
- size: `643`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int, unsigned __int16 **, int *, int, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800e72f0`

## callees

- `0x18001054c`
- `0x18001e340`
- `0x18008a620`
- `0x1800f6188`
- `0x180117f14`
- `0x18011802c`
- `0x18011baa0`
- `0x18011bb60`
- `0x18011c010`

## import_xrefs

- `iertutil!CreateUri` at `0x18011807c`
- `iertutil!CreateUri` at `0x18011807c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x18011811a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x18011811a`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrTrimW` at `0x1801181b6`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrTrimW` at `0x1801181b6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1801181d2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1801181d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18011825b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18011825b`
- `api-ms-win-core-url-l1-1-0!PathCreateFromUrlW` at `0x180118103`
- `api-ms-win-core-url-l1-1-0!PathCreateFromUrlW` at `0x180118103`
- `OLEAUT32!__imp_SysFreeString` at `0x180118157`
- `OLEAUT32!__imp_SysFreeString` at `0x180118236`
- `OLEAUT32!__imp_SysFreeString` at `0x180118277`
- `OLEAUT32!__imp_SysFreeString` at `0x180118157`
- `OLEAUT32!__imp_SysFreeString` at `0x180118236`
- `OLEAUT32!__imp_SysFreeString` at `0x180118277`

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
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppURI);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18011802c  mov     [rsp-8+arg_8], rbx
0x180118031  push    rbp
0x180118032  push    rsi
0x180118033  push    rdi
0x180118034  push    r14
0x180118036  push    r15
0x180118038  lea     rbp, [rsp-0FB0h]
0x180118040  mov     eax, 10B0h
0x180118045  call    _alloca_probe
0x18011804a  sub     rsp, rax
0x18011804d  mov     rax, cs:__security_cookie
0x180118054  xor     rax, rsp
0x180118057  mov     [rbp+0FD0h+var_30], rax
0x18011805e  xor     r15d, r15d
0x180118061  mov     r14, r9
0x180118064  mov     [r8], r15
0x180118067  mov     rdi, r8
0x18011806a  mov     [r9], r15d
0x18011806d  xor     r8d, r8d; dwReserved
0x180118070  lea     r9, [rsp+10D0h+ppURI]; ppURI
0x180118075  mov     [rsp+10D0h+ppURI], r15
0x18011807a  xor     edx, edx; dwFlags
0x18011807c  call    cs:__imp_CreateUri
0x180118082  mov     ebx, eax
0x180118084  test    eax, eax
0x180118086  js      loc_18011827D
0x18011808c  mov     rcx, [rsp+10D0h+ppURI]
0x180118091  lea     rdx, [rsp+10D0h+var_1088]
0x180118096  mov     [rsp+10D0h+var_1088], r15d
0x18011809b  mov     rax, [rcx]
0x18011809e  mov     rax, [rax+0C0h]
0x1801180a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801180aa  mov     ebx, eax
0x1801180ac  test    eax, eax
0x1801180ae  js      loc_18011827D
0x1801180b4  cmp     [rsp+10D0h+var_1088], 9
0x1801180b9  lea     esi, [r15+1]
0x1801180bd  mov     rcx, [rsp+10D0h+ppURI]
0x1801180c2  mov     [rsp+10D0h+psz], r15
0x1801180c7  jnz     loc_18011815F
0x1801180cd  mov     [rsp+10D0h+pszUrl], r15
0x1801180d2  lea     rdx, [rsp+10D0h+pszUrl]
0x1801180d7  mov     rax, [rcx]
0x1801180da  mov     rax, [rax+38h]
0x1801180de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801180e3  mov     ebx, eax
0x1801180e5  test    eax, eax
0x1801180e7  js      short loc_180118152
0x1801180e9  mov     rcx, [rsp+10D0h+pszUrl]; pszUrl
0x1801180ee  lea     r8, [rsp+10D0h+pcchPath]; pcchPath
0x1801180f3  xor     r9d, r9d; dwFlags
0x1801180f6  mov     [rsp+10D0h+pcchPath], 824h
0x1801180fe  lea     rdx, [rsp+10D0h+pszPath]; pszPath
0x180118103  call    cs:__imp_PathCreateFromUrlW
0x180118109  mov     ebx, eax
0x18011810b  test    eax, eax
0x18011810d  js      short loc_180118152
0x18011810f  mov     [r14], esi
0x180118112  lea     rcx, [rsp+10D0h+pszPath]; pszPath
0x180118117  mov     esi, r15d
0x18011811a  call    cs:__imp_PathIsUNCW
0x180118120  test    eax, eax
0x180118122  jz      short loc_180118131
0x180118124  mov     r8, r14; int *
0x180118127  lea     rcx, [rsp+10D0h+pszPath]; unsigned __int16 *
0x18011812c  call    ?FormatUNCPath@@YAXPEAGKPEAH@Z; FormatUNCPath(ushort *,ulong,int *)
0x180118131  lea     rdx, [rsp+10D0h+pszPath]
0x180118136  lea     rcx, [rsp+10D0h+psz]
0x18011813b  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x180118140  mov     rax, [rsp+10D0h+psz]
0x180118145  neg     rax
0x180118148  sbb     ebx, ebx
0x18011814a  not     ebx
0x18011814c  and     ebx, 8007000Eh
0x180118152  mov     rcx, [rsp+10D0h+pszUrl]; bstrString
0x180118157  call    cs:__imp_SysFreeString
0x18011815d  jmp     short loc_18011817C
0x18011815f  mov     rax, [rcx]
0x180118162  lea     r8, [rsp+10D0h+psz]
0x180118167  mov     r9d, 4
0x18011816d  mov     rax, [rax+18h]
0x180118171  lea     edx, [r9+2]
0x180118175  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011817a  mov     ebx, eax
0x18011817c  test    ebx, ebx
0x18011817e  js      loc_180118272
0x180118184  mov     rcx, [rsp+10D0h+psz]
0x180118189  movzx   eax, word ptr [rcx]
0x18011818c  test    ax, ax
0x18011818f  jz      short loc_1801181AF
0x180118191  mov     edx, 20h ; ' '
0x180118196  cmp     ax, dx
0x180118199  jnb     short loc_18011819E
0x18011819b  mov     [rcx], dx
0x18011819e  add     rcx, 2
0x1801181a2  movzx   eax, word ptr [rcx]
0x1801181a5  test    ax, ax
0x1801181a8  jnz     short loc_180118196
0x1801181aa  mov     rcx, [rsp+10D0h+psz]; psz
0x1801181af  lea     rdx, asc_180136AF0; " "
0x1801181b6  call    cs:__imp_StrTrimW
0x1801181bc  mov     rax, [rsp+10D0h+psz]
0x1801181c1  cmp     [rax], r15w
0x1801181c5  jz      loc_18011826D
0x1801181cb  mov     edx, 1048h; uBytes
0x1801181d0  xor     ecx, ecx; uFlags
0x1801181d2  call    cs:__imp_LocalAlloc
0x1801181d8  mov     [rdi], rax
0x1801181db  test    rax, rax
0x1801181de  jz      loc_180118266
0x1801181e4  test    esi, esi
0x1801181e6  jz      short loc_180118240
0x1801181e8  mov     rcx, [rsp+10D0h+ppURI]
0x1801181ed  lea     rdx, [rsp+10D0h+pszUrl]
0x1801181f2  mov     [rsp+10D0h+pszUrl], r15
0x1801181f7  mov     rax, [rcx]
0x1801181fa  mov     rax, [rax+98h]
0x180118201  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118206  mov     ebx, eax
0x180118208  test    eax, eax
0x18011820a  js      short loc_180118231
0x18011820c  mov     rax, [rsp+10D0h+psz]
0x180118211  lea     r8, aSS; "%s://%s"
0x180118218  mov     r9, [rsp+10D0h+pszUrl]
0x18011821d  mov     edx, 824h; unsigned __int64
0x180118222  mov     rcx, [rdi]; unsigned __int16 *
0x180118225  mov     [rsp+10D0h+var_10B0], rax
0x18011822a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18011822f  mov     ebx, eax
0x180118231  mov     rcx, [rsp+10D0h+pszUrl]; bstrString
0x180118236  call    cs:__imp_SysFreeString
0x18011823c  test    ebx, ebx
0x18011823e  jns     short loc_180118272
0x180118240  mov     r8, [rsp+10D0h+psz]; unsigned __int16 *
0x180118245  mov     edx, 824h; unsigned __int64
0x18011824a  mov     rcx, [rdi]; unsigned __int16 *
0x18011824d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180118252  mov     ebx, eax
0x180118254  test    eax, eax
0x180118256  jns     short loc_180118272
0x180118258  mov     rcx, [rdi]; hMem
0x18011825b  call    cs:__imp_LocalFree
0x180118261  mov     [rdi], r15
0x180118264  jmp     short loc_180118272
0x180118266  mov     ebx, 8007000Eh
0x18011826b  jmp     short loc_180118272
0x18011826d  mov     ebx, 80004005h
0x180118272  mov     rcx, [rsp+10D0h+psz]; bstrString
0x180118277  call    cs:__imp_SysFreeString
0x18011827d  lea     rcx, [rsp+10D0h+ppURI]
0x180118282  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180118287  mov     eax, ebx
0x180118289  mov     rcx, [rbp+0FD0h+var_30]
0x180118290  xor     rcx, rsp; StackCookie
0x180118293  call    __security_check_cookie
0x180118298  mov     rbx, [rsp+10D0h+arg_8]
0x1801182a0  add     rsp, 10B0h
0x1801182a7  pop     r15
0x1801182a9  pop     r14
0x1801182ab  pop     rdi
0x1801182ac  pop     rsi
0x1801182ad  pop     rbp
0x1801182ae  retn
```
