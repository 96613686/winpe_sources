# DeleteSystemDataFolderForUser(void *,SYSTEM_DATA_FOLDER_USER_ACCESS,ushort const *,bool)

- ea: `0x1800045a8`
- end: `0x180004b6f`
- name: `?DeleteSystemDataFolderForUser@@YAJPEAXW4SYSTEM_DATA_FOLDER_USER_ACCESS@@PEBG_N@Z`
- size: `1479`
- prototype: `void __fastcall __noreturn(void *, unsigned int, _WORD *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x18000c600`
- `0x18007dd00`

## callees

- `0x1800045a8`
- `0x180004ec0`
- `0x18003d244`
- `0x180047ae0`
- `0x180054130`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800046d1`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800046f1`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800048a3`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800048c3`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800046d1`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800046f1`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800048a3`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800048c3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180004790`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180004961`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180004790`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180004961`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004b36`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004b36`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800046ad`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18000487f`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800046ad`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18000487f`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x180004716`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x1800048ed`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x180004716`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x1800048ed`
- `SHELL32!SHGetFolderPathEx` at `0x180004627`
- `SHELL32!SHGetFolderPathEx` at `0x180004627`
- `SHELL32!SHCreateItemFromParsingName` at `0x180004a64`
- `SHELL32!SHCreateItemFromParsingName` at `0x180004a64`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180004abe`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180004abe`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800045ee`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800045ee`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall __noreturn DeleteSystemDataFolderForUser(void *a1, unsigned int a2, _WORD *a3)
{
  unsigned int v3; // r13d
  __int64 v5; // rdi
  __int64 v6; // r15
  WCHAR *v7; // rcx
  __int64 v8; // rax
  WCHAR *v9; // r8
  __int64 v10; // rdx
  WCHAR *v11; // rcx
  wchar_t *i; // rax
  unsigned __int64 v13; // r14
  unsigned __int64 v14; // rsi
  unsigned __int64 v15; // rax
  __int64 v16; // rax
  WCHAR *v17; // rcx
  __int64 v18; // rdx
  WCHAR *v19; // r8
  WCHAR *v20; // rcx
  __int64 v21; // rax
  WCHAR *v22; // rcx
  __int64 v23; // rdx
  WCHAR *v24; // r8
  WCHAR *v25; // rcx
  HRESULT v26; // ebx
  wchar_t *v27; // rax
  unsigned __int64 v28; // rsi
  WCHAR *v29; // rcx
  WCHAR *v30; // rax
  WCHAR *v31; // rcx
  unsigned int v32; // edx
  HWND v33; // rcx
  const struct _GUID *v34; // r8
  BOOL bIgnoreCase; // [rsp+20h] [rbp-E0h]
  BOOL bIgnoreCasea; // [rsp+20h] [rbp-E0h]
  IUnknown *pProxy; // [rsp+40h] [rbp-C0h] BYREF
  LPWSTR StringSid; // [rsp+48h] [rbp-B8h] BYREF
  void *ppv; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR String1[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR pszPathOut[264]; // [rsp+270h] [rbp+170h] BYREF
  WCHAR pszPath[264]; // [rsp+480h] [rbp+380h] BYREF

  v3 = a2;
  LODWORD(pProxy) = a2;
  StringSid = 0;
  if ( ConvertSidToStringSidW(a1, &StringSid) || (int)ResultFromKnownLastError() >= 0 )
  {
    v5 = 260;
    if ( (int)SHGetFolderPathEx(&FOLDERID_ProgramData, 0, 0, String1, 260) < 0 )
      goto LABEL_70;
    v6 = 2147483646;
    v7 = String1;
    v8 = 2147483646;
    v9 = pszPath;
    v10 = 260;
    do
    {
      if ( !v8 )
        break;
      if ( !*v7 )
        break;
      *v9++ = *v7++;
      --v8;
      --v10;
    }
    while ( v10 );
    v11 = v9 - 1;
    if ( v10 )
      v11 = v9;
    *v11 = 0;
    if ( !v10 || PathCchAppend(pszPath, 0x104u, L"Microsoft\\Windows\\SystemData") < 0 )
      goto LABEL_70;
    for ( i = wcsstr(pszPath, L"/"); i; i = wcsstr(i, L"/") )
      *i = 92;
    if ( PathCchCanonicalizeEx(pszPathOut, 0x104u, pszPath, 0) < 0 )
      goto LABEL_70;
    v13 = -1;
    v14 = -1;
    do
      ++v14;
    while ( String1[v14] );
    if ( v14 > 0xFFFFFFFF )
      goto LABEL_70;
    v15 = -1;
    do
      ++v15;
    while ( pszPathOut[v15] );
    if ( v15 > 0xFFFFFFFF
      || (unsigned int)v15 <= (unsigned int)v14
      || CompareStringOrdinal(String1, v14, pszPathOut, v14, 0) != 2
      || pszPathOut[(unsigned int)v14] != 92 )
    {
      goto LABEL_70;
    }
    v16 = 2147483646;
    v17 = pszPathOut;
    v18 = 260;
    v19 = String1;
    do
    {
      if ( !v16 )
        break;
      if ( !*v17 )
        break;
      *v19++ = *v17++;
      --v16;
      --v18;
    }
    while ( v18 );
    v20 = v19 - 1;
    if ( v18 )
      v20 = v19;
    *v20 = 0;
    if ( !v18 )
      goto LABEL_70;
    v21 = 2147483646;
    v22 = String1;
    v23 = 260;
    v24 = pszPath;
    do
    {
      if ( !v21 )
        break;
      if ( !*v22 )
        break;
      *v24++ = *v22++;
      --v21;
      --v23;
    }
    while ( v23 );
    v25 = v24 - 1;
    if ( v23 )
      v25 = v24;
    *v25 = 0;
    if ( !v23 )
      goto LABEL_70;
    v26 = PathCchAppend(pszPath, 0x104u, StringSid);
    if ( v26 >= 0 )
    {
      v27 = wcsstr(pszPath, L"/");
      if ( v27 )
      {
        do
        {
          *v27 = 92;
          v27 = wcsstr(v27, L"/");
        }
        while ( v27 );
        v3 = (unsigned int)pProxy;
      }
      v26 = PathCchCanonicalizeEx(pszPathOut, 0x104u, pszPath, 0);
      if ( v26 >= 0 )
      {
        v28 = -1;
        do
          ++v28;
        while ( String1[v28] );
        if ( v28 > 0xFFFFFFFF )
          goto LABEL_70;
        do
          ++v13;
        while ( pszPathOut[v13] );
        if ( v13 > 0xFFFFFFFF )
        {
LABEL_70:
          LocalFree(StringSid);
          return;
        }
        v26 = -2147024809;
        if ( (unsigned int)v13 > (unsigned int)v28
          && CompareStringOrdinal(String1, v28, pszPathOut, v28, 0) == 2
          && pszPathOut[(unsigned int)v28] == 92 )
        {
          v29 = pszPathOut;
          v30 = String1;
          do
          {
            if ( !v6 )
              break;
            if ( !*v29 )
              break;
            *v30++ = *v29++;
            --v6;
            --v5;
          }
          while ( v5 );
          v31 = v30 - 1;
          if ( v5 )
            v31 = v30;
          v26 = v5 == 0 ? 0x8007007A : 0;
          *v31 = 0;
        }
      }
    }
    if ( v26 >= 0 )
    {
      if ( !a3
        || !*a3
        || (LOBYTE(bIgnoreCase) = 0,
            (int)_AppendPathAndCreateFolder(off_180100008[3 * (int)v3], StringSid, v3, 0, bIgnoreCase, String1) >= 0)
        && (LOBYTE(bIgnoreCasea) = 0, (int)_AppendPathAndCreateFolder(a3, StringSid, v3, 0, bIgnoreCasea, String1) >= 0) )
      {
        ppv = 0;
        if ( SHCreateItemFromParsingName(String1, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv) >= 0 )
        {
          pProxy = 0;
          if ( (int)SHCreateFileOperation(v33, v32, v34, (void **)&pProxy) >= 0 )
          {
            if ( CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, 0, 0, 3u, 0, 0x40u) >= 0
              && ((int (__fastcall *)(IUnknown *, void *, _QWORD))pProxy->lpVtbl[6].QueryInterface)(pProxy, ppv, 0) >= 0 )
            {
              ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl[7].QueryInterface)(pProxy);
            }
            ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
          }
          (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
        }
      }
    }
    goto LABEL_70;
  }
}

```

## disassembly

```asm
0x1800045a8  mov     [rsp-8+arg_18], rbx
0x1800045ad  push    rbp
0x1800045ae  push    rsi
0x1800045af  push    rdi
0x1800045b0  push    r12
0x1800045b2  push    r13
0x1800045b4  push    r14
0x1800045b6  push    r15
0x1800045b8  lea     rbp, [rsp-5A0h]
0x1800045c0  sub     rsp, 6A0h
0x1800045c7  mov     rax, cs:__security_cookie
0x1800045ce  xor     rax, rsp
0x1800045d1  mov     [rbp+5D0h+var_40], rax
0x1800045d8  mov     r13d, edx
0x1800045db  mov     dword ptr [rsp+6D0h+pProxy], edx
0x1800045df  xor     esi, esi
0x1800045e1  lea     rdx, [rsp+6D0h+StringSid]; StringSid
0x1800045e6  mov     [rsp+6D0h+StringSid], rsi
0x1800045eb  mov     r12, r8
0x1800045ee  call    cs:__imp_ConvertSidToStringSidW
0x1800045f5  nop     dword ptr [rax+rax+00h]
0x1800045fa  test    eax, eax
0x1800045fc  jnz     short loc_18000460D
0x1800045fe  call    ?ResultFromKnownLastError@@YAJXZ
0x180004603  mov     ebx, eax
0x180004605  test    eax, eax
0x180004607  js      loc_180004B42
0x18000460d  mov     edi, 104h
0x180004612  lea     r9, [rsp+6D0h+String1]
0x180004617  xor     r8d, r8d
0x18000461a  mov     [rsp+6D0h+bIgnoreCase], edi
0x18000461e  xor     edx, edx
0x180004620  lea     rcx, FOLDERID_ProgramData
0x180004627  call    cs:__imp_SHGetFolderPathEx
0x18000462e  nop     dword ptr [rax+rax+00h]
0x180004633  mov     ebx, eax
0x180004635  test    eax, eax
0x180004637  js      loc_180004B31
0x18000463d  mov     r15d, 7FFFFFFEh
0x180004643  lea     rcx, [rsp+6D0h+String1]
0x180004648  mov     eax, r15d
0x18000464b  lea     r8, [rbp+5D0h+pszPath]
0x180004652  mov     edx, edi
0x180004654  test    rax, rax
0x180004657  jz      short loc_180004678
0x180004659  movzx   r9d, word ptr [rcx]
0x18000465d  test    r9w, r9w
0x180004661  jz      short loc_180004678
0x180004663  mov     [r8], r9w
0x180004667  add     rcx, 2
0x18000466b  add     r8, 2
0x18000466f  dec     rax
0x180004672  sub     rdx, 1
0x180004676  jnz     short loc_180004654
0x180004678  mov     rax, rdx
0x18000467b  lea     rcx, [r8-2]
0x18000467f  neg     rax
0x180004682  sbb     ebx, ebx
0x180004684  not     ebx
0x180004686  and     ebx, 8007007Ah
0x18000468c  test    rdx, rdx
0x18000468f  cmovnz  rcx, r8
0x180004693  mov     [rcx], si
0x180004696  jz      loc_180004B31
0x18000469c  lea     r8, pszMore
0x1800046a3  mov     rdx, rdi; cchPath
0x1800046a6  lea     rcx, [rbp+5D0h+pszPath]; pszPath
0x1800046ad  call    cs:__imp_PathCchAppend
0x1800046b4  nop     dword ptr [rax+rax+00h]
0x1800046b9  mov     ebx, eax
0x1800046bb  test    eax, eax
0x1800046bd  js      loc_180004B31
0x1800046c3  lea     rdx, SubStr
0x1800046ca  lea     rcx, [rbp+5D0h+pszPath]; Str
0x1800046d1  call    cs:__imp_wcsstr
0x1800046d8  nop     dword ptr [rax+rax+00h]
0x1800046dd  test    rax, rax
0x1800046e0  jz      short loc_180004702
0x1800046e2  lea     rdx, SubStr
0x1800046e9  mov     word ptr [rax], 5Ch ; '\'
0x1800046ee  mov     rcx, rax; Str
0x1800046f1  call    cs:__imp_wcsstr
0x1800046f8  nop     dword ptr [rax+rax+00h]
0x1800046fd  test    rax, rax
0x180004700  jnz     short loc_1800046E2
0x180004702  xor     r9d, r9d; dwFlags
0x180004705  lea     r8, [rbp+5D0h+pszPath]; pszPathIn
0x18000470c  mov     rdx, rdi; cchPathOut
0x18000470f  lea     rcx, [rbp+5D0h+pszPathOut]; pszPathOut
0x180004716  call    cs:__imp_PathCchCanonicalizeEx
0x18000471d  nop     dword ptr [rax+rax+00h]
0x180004722  mov     ebx, eax
0x180004724  test    eax, eax
0x180004726  js      loc_180004B31
0x18000472c  or      r14, 0FFFFFFFFFFFFFFFFh
0x180004730  lea     rax, [rsp+6D0h+String1]
0x180004735  mov     rsi, r14
0x180004738  xor     ecx, ecx
0x18000473a  inc     rsi
0x18000473d  cmp     [rax+rsi*2], cx
0x180004741  jnz     short loc_18000473A
0x180004743  mov     r8d, 0FFFFFFFFh
0x180004749  cmp     rsi, r8
0x18000474c  ja      loc_180004B2C
0x180004752  lea     rdx, [rbp+5D0h+pszPathOut]
0x180004759  mov     rax, r14
0x18000475c  inc     rax
0x18000475f  cmp     [rdx+rax*2], cx
0x180004763  jnz     short loc_18000475C
0x180004765  cmp     rax, r8
0x180004768  ja      loc_180004B2C
0x18000476e  mov     ebx, 80070057h
0x180004773  cmp     eax, esi
0x180004775  jbe     loc_180004B31
0x18000477b  mov     [rsp+6D0h+bIgnoreCase], ecx; bIgnoreCase
0x18000477f  lea     r8, [rbp+5D0h+pszPathOut]; lpString2
0x180004786  lea     rcx, [rsp+6D0h+String1]; lpString1
0x18000478b  mov     r9d, esi; cchCount2
0x18000478e  mov     edx, esi; cchCount1
0x180004790  call    cs:__imp_CompareStringOrdinal
0x180004797  nop     dword ptr [rax+rax+00h]
0x18000479c  cmp     eax, 2
0x18000479f  jnz     loc_180004B31
0x1800047a5  mov     eax, esi
0x1800047a7  mov     ecx, 5Ch ; '\'
0x1800047ac  cmp     [rbp+rax*2+5D0h+pszPathOut], cx
0x1800047b4  jnz     loc_180004B31
0x1800047ba  mov     rax, r15
0x1800047bd  lea     rcx, [rbp+5D0h+pszPathOut]
0x1800047c4  mov     rdx, rdi
0x1800047c7  lea     r8, [rsp+6D0h+String1]
0x1800047cc  xor     esi, esi
0x1800047ce  test    rax, rax
0x1800047d1  jz      short loc_1800047F2
0x1800047d3  movzx   r9d, word ptr [rcx]
0x1800047d7  test    r9w, r9w
0x1800047db  jz      short loc_1800047F2
0x1800047dd  mov     [r8], r9w
0x1800047e1  add     rcx, 2
0x1800047e5  add     r8, 2
0x1800047e9  dec     rax
0x1800047ec  sub     rdx, 1
0x1800047f0  jnz     short loc_1800047CE
0x1800047f2  mov     rax, rdx
0x1800047f5  lea     rcx, [r8-2]
0x1800047f9  neg     rax
0x1800047fc  mov     r10d, 8007007Ah
0x180004802  sbb     ebx, ebx
0x180004804  not     ebx
0x180004806  and     ebx, r10d
0x180004809  test    rdx, rdx
0x18000480c  cmovnz  rcx, r8
0x180004810  mov     [rcx], si
0x180004813  jz      loc_180004B31
0x180004819  mov     rax, r15
0x18000481c  lea     rcx, [rsp+6D0h+String1]
0x180004821  mov     rdx, rdi
0x180004824  lea     r8, [rbp+5D0h+pszPath]
0x18000482b  test    rax, rax
0x18000482e  jz      short loc_18000484F
0x180004830  movzx   r9d, word ptr [rcx]
0x180004834  test    r9w, r9w
0x180004838  jz      short loc_18000484F
0x18000483a  mov     [r8], r9w
0x18000483e  add     rcx, 2
0x180004842  add     r8, 2
0x180004846  dec     rax
0x180004849  sub     rdx, 1
0x18000484d  jnz     short loc_18000482B
0x18000484f  mov     rax, rdx
0x180004852  lea     rcx, [r8-2]
0x180004856  neg     rax
0x180004859  sbb     ebx, ebx
0x18000485b  not     ebx
0x18000485d  and     ebx, r10d
0x180004860  test    rdx, rdx
0x180004863  cmovnz  rcx, r8
0x180004867  mov     [rcx], si
0x18000486a  jz      loc_180004B31
0x180004870  mov     r8, [rsp+6D0h+StringSid]; pszMore
0x180004875  lea     rcx, [rbp+5D0h+pszPath]; pszPath
0x18000487c  mov     rdx, rdi; cchPath
0x18000487f  call    cs:__imp_PathCchAppend
0x180004886  nop     dword ptr [rax+rax+00h]
0x18000488b  mov     ebx, eax
0x18000488d  test    eax, eax
0x18000488f  js      loc_1800049D1
0x180004895  lea     rdx, SubStr
0x18000489c  lea     rcx, [rbp+5D0h+pszPath]; Str
0x1800048a3  call    cs:__imp_wcsstr
0x1800048aa  nop     dword ptr [rax+rax+00h]
0x1800048af  test    rax, rax
0x1800048b2  jz      short loc_1800048D9
0x1800048b4  lea     rdx, SubStr
0x1800048bb  mov     word ptr [rax], 5Ch ; '\'
0x1800048c0  mov     rcx, rax; Str
0x1800048c3  call    cs:__imp_wcsstr
0x1800048ca  nop     dword ptr [rax+rax+00h]
0x1800048cf  test    rax, rax
0x1800048d2  jnz     short loc_1800048B4
0x1800048d4  mov     r13d, dword ptr [rsp+6D0h+pProxy]
0x1800048d9  xor     r9d, r9d; dwFlags
0x1800048dc  lea     r8, [rbp+5D0h+pszPath]; pszPathIn
0x1800048e3  mov     rdx, rdi; cchPathOut
0x1800048e6  lea     rcx, [rbp+5D0h+pszPathOut]; pszPathOut
0x1800048ed  call    cs:__imp_PathCchCanonicalizeEx
0x1800048f4  nop     dword ptr [rax+rax+00h]
0x1800048f9  mov     ebx, eax
0x1800048fb  test    eax, eax
0x1800048fd  js      loc_1800049D1
0x180004903  lea     rax, [rsp+6D0h+String1]
0x180004908  mov     rsi, r14
0x18000490b  xor     ecx, ecx
0x18000490d  inc     rsi
0x180004910  cmp     [rax+rsi*2], cx
0x180004914  jnz     short loc_18000490D
0x180004916  mov     edx, 0FFFFFFFFh
0x18000491b  cmp     rsi, rdx
0x18000491e  ja      loc_180004B2C
0x180004924  lea     rax, [rbp+5D0h+pszPathOut]
0x18000492b  inc     r14
0x18000492e  cmp     [rax+r14*2], cx
0x180004933  jnz     short loc_18000492B
0x180004935  cmp     r14, rdx
0x180004938  ja      loc_180004B2C
0x18000493e  mov     ebx, 80070057h
0x180004943  cmp     r14d, esi
0x180004946  jbe     loc_1800049CF
0x18000494c  mov     [rsp+6D0h+bIgnoreCase], ecx; bIgnoreCase
0x180004950  lea     r8, [rbp+5D0h+pszPathOut]; lpString2
0x180004957  lea     rcx, [rsp+6D0h+String1]; lpString1
0x18000495c  mov     r9d, esi; cchCount2
0x18000495f  mov     edx, esi; cchCount1
0x180004961  call    cs:__imp_CompareStringOrdinal
0x180004968  nop     dword ptr [rax+rax+00h]
0x18000496d  cmp     eax, 2
0x180004970  jnz     short loc_1800049CF
0x180004972  mov     eax, esi
0x180004974  mov     ecx, 5Ch ; '\'
0x180004979  xor     esi, esi
0x18000497b  cmp     [rbp+rax*2+5D0h+pszPathOut], cx
0x180004983  jnz     short loc_1800049D1
0x180004985  lea     rcx, [rbp+5D0h+pszPathOut]
0x18000498c  lea     rax, [rsp+6D0h+String1]
0x180004991  test    r15, r15
0x180004994  jz      short loc_1800049B2
0x180004996  movzx   edx, word ptr [rcx]
0x180004999  test    dx, dx
0x18000499c  jz      short loc_1800049B2
0x18000499e  mov     [rax], dx
0x1800049a1  add     rcx, 2
0x1800049a5  add     rax, 2
0x1800049a9  dec     r15
0x1800049ac  sub     rdi, 1
0x1800049b0  jnz     short loc_180004991
0x1800049b2  test    rdi, rdi
0x1800049b5  lea     rcx, [rax-2]
0x1800049b9  cmovnz  rcx, rax
0x1800049bd  neg     rdi
0x1800049c0  sbb     ebx, ebx
0x1800049c2  not     ebx
0x1800049c4  and     ebx, 8007007Ah
0x1800049ca  mov     [rcx], si
0x1800049cd  jmp     short loc_1800049D1
0x1800049cf  xor     esi, esi
0x1800049d1  test    ebx, ebx
0x1800049d3  js      loc_180004B31
0x1800049d9  test    r12, r12
0x1800049dc  jz      short loc_180004A4C
0x1800049de  cmp     [r12], si
0x1800049e3  jz      short loc_180004A4C
0x1800049e5  mov     rdx, [rsp+6D0h+StringSid]
0x1800049ea  lea     r10, off_180100008
0x1800049f1  movsxd  rax, r13d
0x1800049f4  xor     r9d, r9d
0x1800049f7  mov     r8d, r13d
0x1800049fa  lea     rcx, [rax+rax*2]
0x1800049fe  mov     rcx, [r10+rcx*8]
0x180004a02  lea     rax, [rsp+6D0h+String1]
0x180004a07  mov     qword ptr [rsp+6D0h+dwImpLevel], rax
0x180004a0c  mov     byte ptr [rsp+6D0h+bIgnoreCase], sil
0x180004a11  call    ?_AppendPathAndCreateFolder@@YAJPEBG0W4SYSTEM_DATA_FOLDER_USER_ACCESS@@W4SYSTEM_DATA_FOLDER_FLAGS@@_NPEAGI@Z
0x180004a16  mov     ebx, eax
0x180004a18  test    eax, eax
0x180004a1a  js      loc_180004B31
0x180004a20  mov     rdx, [rsp+6D0h+StringSid]
0x180004a25  lea     rax, [rsp+6D0h+String1]
0x180004a2a  mov     qword ptr [rsp+6D0h+dwImpLevel], rax
0x180004a2f  xor     r9d, r9d
0x180004a32  mov     r8d, r13d
0x180004a35  mov     byte ptr [rsp+6D0h+bIgnoreCase], sil
0x180004a3a  mov     rcx, r12
0x180004a3d  call    ?_AppendPathAndCreateFolder@@YAJPEBG0W4SYSTEM_DATA_FOLDER_USER_ACCESS@@W4SYSTEM_DATA_FOLDER_FLAGS@@_NPEAGI@Z
0x180004a42  mov     ebx, eax
0x180004a44  test    eax, eax
0x180004a46  js      loc_180004B31
0x180004a4c  lea     r9, [rsp+6D0h+ppv]; ppv
0x180004a51  mov     [rsp+6D0h+ppv], rsi
0x180004a56  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180004a5d  xor     edx, edx; pbc
  ... truncated ...
```
