# GetHostDisplayNameFromUrlInternal(ushort const *,uint,ushort * *,int *,int,int)

- ea: `0x18002760c`
- end: `0x18002780b`
- name: `?GetHostDisplayNameFromUrlInternal@@YAJPEBGIPEAPEAGPEAHHH@Z`
- size: `511`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int, unsigned __int16 **, int *, int, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180003810`
- `0x18001d5d8`

## callees

- `0x180008320`
- `0x18000bf34`
- `0x180027220`
- `0x18002732c`
- `0x1800274f4`
- `0x18002760c`
- `0x180027c30`
- `0x180029010`

## import_xrefs

- `SHLWAPI!PathCreateFromUrlW` at `0x1800276da`
- `SHLWAPI!PathCreateFromUrlW` at `0x1800276da`
- `SHLWAPI!PathIsUNCW` at `0x1800276fc`
- `SHLWAPI!PathIsUNCW` at `0x1800276fc`
- `SHLWAPI!StrTrimW` at `0x18002777f`
- `SHLWAPI!StrTrimW` at `0x18002777f`
- `SHLWAPI!PathRemoveFileSpecW` at `0x1800276f1`
- `SHLWAPI!PathRemoveFileSpecW` at `0x1800276f1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027797`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027797`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800277c0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800277c0`
- `OLEAUT32!__imp_SysAllocString` at `0x180027723`
- `OLEAUT32!__imp_SysAllocString` at `0x180027723`
- `OLEAUT32!__imp_SysFreeString` at `0x180027718`
- `OLEAUT32!__imp_SysFreeString` at `0x180027740`
- `OLEAUT32!__imp_SysFreeString` at `0x1800277dc`
- `OLEAUT32!__imp_SysFreeString` at `0x180027718`
- `OLEAUT32!__imp_SysFreeString` at `0x180027740`
- `OLEAUT32!__imp_SysFreeString` at `0x1800277dc`
- `urlmon!CreateUri` at `0x180027657`
- `urlmon!CreateUri` at `0x180027657`

## pseudocode

```c
__int64 __fastcall GetHostDisplayNameFromUrlInternal(const unsigned __int16 *a1, __int64 a2, HLOCAL *a3, int *a4)
{
  HRESULT v6; // ebx
  unsigned int v7; // edx
  unsigned __int16 *v8; // rax
  BSTR bstrString; // [rsp+30h] [rbp-D0h] BYREF
  int v11; // [rsp+38h] [rbp-C8h] BYREF
  IUri *ppURI; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcchPath; // [rsp+48h] [rbp-B8h] BYREF
  PCWSTR pszUrl[2]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszPath[2088]; // [rsp+60h] [rbp-A0h] BYREF

  *a3 = 0;
  *a4 = 0;
  ppURI = 0;
  v6 = CreateUri(a1, 0, 0, &ppURI);
  if ( v6 >= 0 )
  {
    v11 = 0;
    v6 = ((__int64 (__fastcall *)(IUri *, int *))ppURI->lpVtbl->GetScheme)(ppURI, &v11);
    if ( v6 >= 0 )
    {
      bstrString = 0;
      if ( v11 == 9 )
      {
        pszUrl[0] = 0;
        v6 = ((__int64 (__fastcall *)(IUri *, PCWSTR *))ppURI->lpVtbl->GetAbsoluteUri)(ppURI, pszUrl);
        if ( v6 >= 0 )
        {
          pcchPath = 2084;
          v6 = PathCreateFromUrlW(pszUrl[0], pszPath, &pcchPath, 0);
          if ( v6 >= 0 )
          {
            *a4 = 1;
            PathRemoveFileSpecW(pszPath);
            if ( PathIsUNCW(pszPath) )
              FormatUNCPath(pszPath, v7, a4);
            SysFreeString(bstrString);
            bstrString = SysAllocString(pszPath);
            v6 = bstrString == 0 ? 0x8007000E : 0;
          }
        }
        SysFreeString((BSTR)pszUrl[0]);
      }
      else
      {
        v6 = ((__int64 (__fastcall *)(IUri *, __int64, BSTR *))ppURI->lpVtbl->GetPropertyBSTR)(ppURI, 6, &bstrString);
      }
      if ( v6 >= 0 )
      {
        CleanupControlChars(bstrString);
        StrTrimW(bstrString, L" ");
        if ( *bstrString )
        {
          v8 = (unsigned __int16 *)LocalAlloc(0, 0x1048u);
          *a3 = v8;
          if ( v8 )
          {
            v6 = StringCchCopyW(v8, 0x824u, bstrString);
            if ( v6 < 0 )
            {
              LocalFree(*a3);
              *a3 = 0;
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
      SysFreeString(bstrString);
    }
  }
  ATL::CComPtr<IUri>::~CComPtr<IUri>(&ppURI);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18002760c  push    rbp
0x18002760e  push    rbx
0x18002760f  push    rsi
0x180027610  push    rdi
0x180027611  push    r14
0x180027613  lea     rbp, [rsp-0FC0h]
0x18002761b  mov     eax, 10C0h
0x180027620  call    _alloca_probe
0x180027625  sub     rsp, rax
0x180027628  mov     rax, cs:__security_cookie
0x18002762f  xor     rax, rsp
0x180027632  mov     [rbp+0FE0h+var_30], rax
0x180027639  xor     r14d, r14d
0x18002763c  mov     rsi, r9
0x18002763f  mov     [r8], r14
0x180027642  mov     rdi, r8
0x180027645  mov     [r9], r14d
0x180027648  xor     r8d, r8d; dwReserved
0x18002764b  lea     r9, [rsp+10E0h+ppURI]; ppURI
0x180027650  mov     [rsp+10E0h+ppURI], r14
0x180027655  xor     edx, edx; dwFlags
0x180027657  call    cs:__imp_CreateUri
0x18002765d  mov     ebx, eax
0x18002765f  test    eax, eax
0x180027661  js      loc_1800277E2
0x180027667  mov     rcx, [rsp+10E0h+ppURI]
0x18002766c  lea     rdx, [rsp+10E0h+var_10A8]
0x180027671  mov     [rsp+10E0h+var_10A8], r14d
0x180027676  mov     rax, [rcx]
0x180027679  mov     rax, [rax+0C0h]
0x180027680  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027685  mov     ebx, eax
0x180027687  test    eax, eax
0x180027689  js      loc_1800277E2
0x18002768f  cmp     [rsp+10E0h+var_10A8], 9
0x180027694  mov     rcx, [rsp+10E0h+ppURI]
0x180027699  mov     [rsp+10E0h+bstrString], r14
0x18002769e  jnz     loc_180027748
0x1800276a4  mov     [rsp+10E0h+pszUrl], r14
0x1800276a9  lea     rdx, [rsp+10E0h+pszUrl]
0x1800276ae  mov     rax, [rcx]
0x1800276b1  mov     rax, [rax+38h]
0x1800276b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800276ba  mov     ebx, eax
0x1800276bc  test    eax, eax
0x1800276be  js      short loc_18002773B
0x1800276c0  mov     rcx, [rsp+10E0h+pszUrl]; pszUrl
0x1800276c5  lea     r8, [rsp+10E0h+pcchPath]; pcchPath
0x1800276ca  xor     r9d, r9d; dwFlags
0x1800276cd  mov     [rsp+10E0h+pcchPath], 824h
0x1800276d5  lea     rdx, [rsp+10E0h+pszPath]; pszPath
0x1800276da  call    cs:__imp_PathCreateFromUrlW
0x1800276e0  mov     ebx, eax
0x1800276e2  test    eax, eax
0x1800276e4  js      short loc_18002773B
0x1800276e6  lea     rcx, [rsp+10E0h+pszPath]; pszPath
0x1800276eb  mov     dword ptr [rsi], 1
0x1800276f1  call    cs:__imp_PathRemoveFileSpecW
0x1800276f7  lea     rcx, [rsp+10E0h+pszPath]; pszPath
0x1800276fc  call    cs:__imp_PathIsUNCW
0x180027702  test    eax, eax
0x180027704  jz      short loc_180027713
0x180027706  mov     r8, rsi; int *
0x180027709  lea     rcx, [rsp+10E0h+pszPath]; unsigned __int16 *
0x18002770e  call    ?FormatUNCPath@@YAXPEAGKPEAH@Z; FormatUNCPath(ushort *,ulong,int *)
0x180027713  mov     rcx, [rsp+10E0h+bstrString]; bstrString
0x180027718  call    cs:__imp_SysFreeString
0x18002771e  lea     rcx, [rsp+10E0h+pszPath]; psz
0x180027723  call    cs:__imp_SysAllocString
0x180027729  mov     [rsp+10E0h+bstrString], rax
0x18002772e  neg     rax
0x180027731  sbb     ebx, ebx
0x180027733  not     ebx
0x180027735  and     ebx, 8007000Eh
0x18002773b  mov     rcx, [rsp+10E0h+pszUrl]; bstrString
0x180027740  call    cs:__imp_SysFreeString
0x180027746  jmp     short loc_180027765
0x180027748  mov     rax, [rcx]
0x18002774b  lea     r8, [rsp+10E0h+bstrString]
0x180027750  mov     r9d, 4
0x180027756  mov     rax, [rax+18h]
0x18002775a  lea     edx, [r9+2]
0x18002775e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027763  mov     ebx, eax
0x180027765  test    ebx, ebx
0x180027767  js      short loc_1800277D7
0x180027769  mov     rcx, [rsp+10E0h+bstrString]; unsigned __int16 *
0x18002776e  call    ?CleanupControlChars@@YAXPEAG@Z; CleanupControlChars(ushort *)
0x180027773  mov     rcx, [rsp+10E0h+bstrString]; psz
0x180027778  lea     rdx, pszTrimChars; " "
0x18002777f  call    cs:__imp_StrTrimW
0x180027785  mov     rax, [rsp+10E0h+bstrString]
0x18002778a  cmp     [rax], r14w
0x18002778e  jz      short loc_1800277D2
0x180027790  mov     edx, 1048h; uBytes
0x180027795  xor     ecx, ecx; uFlags
0x180027797  call    cs:__imp_LocalAlloc
0x18002779d  mov     [rdi], rax
0x1800277a0  test    rax, rax
0x1800277a3  jz      short loc_1800277CB
0x1800277a5  mov     r8, [rsp+10E0h+bstrString]; unsigned __int16 *
0x1800277aa  mov     edx, 824h; unsigned __int64
0x1800277af  mov     rcx, rax; unsigned __int16 *
0x1800277b2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800277b7  mov     ebx, eax
0x1800277b9  test    eax, eax
0x1800277bb  jns     short loc_1800277D7
0x1800277bd  mov     rcx, [rdi]; hMem
0x1800277c0  call    cs:__imp_LocalFree
0x1800277c6  mov     [rdi], r14
0x1800277c9  jmp     short loc_1800277D7
0x1800277cb  mov     ebx, 8007000Eh
0x1800277d0  jmp     short loc_1800277D7
0x1800277d2  mov     ebx, 80004005h
0x1800277d7  mov     rcx, [rsp+10E0h+bstrString]; bstrString
0x1800277dc  call    cs:__imp_SysFreeString
0x1800277e2  lea     rcx, [rsp+10E0h+ppURI]
0x1800277e7  call    ??1?$CComPtr@UIUri@@@ATL@@QEAA@XZ; ATL::CComPtr<IUri>::~CComPtr<IUri>(void)
0x1800277ec  mov     eax, ebx
0x1800277ee  mov     rcx, [rbp+0FE0h+var_30]
0x1800277f5  xor     rcx, rsp; StackCookie
0x1800277f8  call    __security_check_cookie
0x1800277fd  add     rsp, 10C0h
0x180027804  pop     r14
0x180027806  pop     rdi
0x180027807  pop     rsi
0x180027808  pop     rbx
0x180027809  pop     rbp
0x18002780a  retn
```
