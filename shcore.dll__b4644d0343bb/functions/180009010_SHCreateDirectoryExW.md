# SHCreateDirectoryExW

- ea: `0x180009010`
- end: `0x18000921f`
- name: `SHCreateDirectoryExW`
- size: `527`
- prototype: `int __stdcall(HWND hwnd, LPCWSTR pszPath, const SECURITY_ATTRIBUTES *psa)`
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180008d90`
- `0x180009010`
- `0x180009230`
- `0x1800095bc`
- `0x18001adc4`
- `0x1800688d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000904a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800091ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000904a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800091ab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000909b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000909b`
- `ntdll!RtlAreLongPathsEnabled` at `0x1800090b6`
- `ntdll!RtlAreLongPathsEnabled` at `0x1800090b6`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180009040`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180009040`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x18000902d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x18000902d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800091a3`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800091a3`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslashEx` at `0x1800090fc`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslashEx` at `0x1800090fc`
- `api-ms-win-shell-changenotify-l1-1-0!SHChangeNotify` at `0x18000908c`
- `api-ms-win-shell-changenotify-l1-1-0!SHChangeNotify` at `0x18000908c`
- `ext-ms-win-shell-directory-l1-1-0!SHSysErrorMessageBox` at `0x180009212`
- `ext-ms-win-shell-directory-l1-1-0!SHSysErrorMessageBox` at `0x180009212`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __stdcall SHCreateDirectoryExW(HWND hwnd, LPCWSTR pszPath, const SECURITY_ATTRIBUTES *psa)
{
  DWORD LastError; // edi
  __int64 v8; // rax
  unsigned __int64 v9; // rsi
  PWSTR v10; // rbx
  __int16 *v11; // rsi
  __int16 v12; // ax
  LPWSTR FileNameW; // rax
  PWSTR ppszEnd; // [rsp+30h] [rbp-58h] BYREF
  PWSTR pszPatha; // [rsp+A8h] [rbp+20h] BYREF

  if ( PathIsRelativeW(pszPath) )
  {
    LastError = 161;
    SetLastError(0xA1u);
    return LastError;
  }
  if ( CreateDirectoryW(pszPath, (LPSECURITY_ATTRIBUTES)psa) )
  {
    LastError = 0;
    if ( !(unsigned int)IsNotifySuspended() && (unsigned __int8)IsSHSysErrorMessageBoxPresent() )
      SHChangeNotify(8, 5u, pszPath, 0);
  }
  else
  {
    LastError = GetLastError();
    if ( LastError != 3 )
      return LastError;
    v8 = -1;
    do
      ++v8;
    while ( pszPath[v8] );
    v9 = v8 + 1;
    if ( !(unsigned __int8)RtlAreLongPathsEnabled() && v9 > 0x104 )
      return 206;
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &pszPatha,
      pszPath,
      v9);
    v10 = pszPatha;
    if ( !pszPatha )
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszPatha);
      return 14;
    }
    ppszEnd = 0;
    if ( PathCchAddBackslashEx(pszPatha, v9 + 1, &ppszEnd, 0) < 0 )
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszPatha);
      return 206;
    }
    v11 = (__int16 *)(v10 + 3);
    if ( v10[3] )
    {
      do
      {
        v12 = *v11;
        do
        {
          if ( v12 == 92 )
            break;
          v12 = *++v11;
        }
        while ( *v11 );
        if ( *v11 )
        {
          *v11 = 0;
          if ( (unsigned int)Win32CreateDirectory(v10) )
            LastError = 0;
          else
            LastError = GetLastError();
        }
        *v11++ = 92;
      }
      while ( *v11 );
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszPatha);
    if ( LastError && hwnd && LastError != 1223 )
    {
      if ( (unsigned __int8)IsSHSysErrorMessageBoxPresent() )
      {
        if ( pszPath )
          FileNameW = PathFindFileNameW(pszPath);
        else
          FileNameW = 0;
        SHSysErrorMessageBox(hwnd, 0, 8730, LastError, FileNameW, 48);
      }
      return 1223;
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x180009010  push    rbx
0x180009012  push    rbp
0x180009013  push    rsi
0x180009014  push    rdi
0x180009015  push    r12
0x180009017  push    r13
0x180009019  push    r14
0x18000901b  push    r15
0x18000901d  sub     rsp, 48h
0x180009021  mov     r15, r8
0x180009024  mov     rbp, rdx
0x180009027  mov     r14, rcx
0x18000902a  mov     rcx, rdx; pszPath
0x18000902d  call    cs:__imp_PathIsRelativeW
0x180009033  xor     r12d, r12d
0x180009036  test    eax, eax
0x180009038  jnz     short loc_180009094
0x18000903a  mov     rdx, r15; lpSecurityAttributes
0x18000903d  mov     rcx, rbp; lpPathName
0x180009040  call    cs:__imp_CreateDirectoryW
0x180009046  test    eax, eax
0x180009048  jnz     short loc_18000906A
0x18000904a  call    cs:__imp_GetLastError
0x180009050  mov     edi, eax
0x180009052  cmp     eax, 3
0x180009055  jz      short loc_1800090A3
0x180009057  mov     eax, edi
0x180009059  add     rsp, 48h
0x18000905d  pop     r15
0x18000905f  pop     r14
0x180009061  pop     r13
0x180009063  pop     r12
0x180009065  pop     rdi
0x180009066  pop     rsi
0x180009067  pop     rbp
0x180009068  pop     rbx
0x180009069  retn
0x18000906a  mov     edi, r12d
0x18000906d  call    IsNotifySuspended
0x180009072  test    eax, eax
0x180009074  jnz     short loc_180009057
0x180009076  call    IsSHSysErrorMessageBoxPresent
0x18000907b  test    al, al
0x18000907d  jz      short loc_180009057
0x18000907f  xor     r9d, r9d; dwItem2
0x180009082  mov     r8, rbp; dwItem1
0x180009085  lea     edx, [r9+5]; uFlags
0x180009089  lea     ecx, [rdx+3]; wEventId
0x18000908c  call    cs:__imp_SHChangeNotify
0x180009092  jmp     short loc_180009057
0x180009094  mov     edi, 0A1h
0x180009099  mov     ecx, edi; dwErrCode
0x18000909b  call    cs:__imp_SetLastError
0x1800090a1  jmp     short loc_180009057
0x1800090a3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800090a7  inc     rax
0x1800090aa  cmp     [rbp+rax*2+0], r12w
0x1800090b0  jnz     short loc_1800090A7
0x1800090b2  lea     rsi, [rax+1]
0x1800090b6  call    cs:__imp_RtlAreLongPathsEnabled
0x1800090bc  test    al, al
0x1800090be  jz      loc_1800091CD
0x1800090c4  mov     r8, rsi
0x1800090c7  mov     rdx, rbp
0x1800090ca  lea     rcx, [rsp+88h+pszPath]
0x1800090d2  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800090d7  mov     rbx, [rsp+88h+pszPath]
0x1800090df  test    rbx, rbx
0x1800090e2  jz      loc_1800091B5
0x1800090e8  mov     [rsp+88h+ppszEnd], r12
0x1800090ed  lea     rdx, [rsi+1]; cchPath
0x1800090f1  xor     r9d, r9d; pcchRemaining
0x1800090f4  lea     r8, [rsp+88h+ppszEnd]; ppszEnd
0x1800090f9  mov     rcx, rbx; pszPath
0x1800090fc  call    cs:__imp_PathCchAddBackslashEx
0x180009102  test    eax, eax
0x180009104  js      loc_1800091DC
0x18000910a  lea     rsi, [rbx+6]
0x18000910e  cmp     [rsi], r12w
0x180009112  jz      short loc_180009166
0x180009114  mov     r13d, 5Ch ; '\'
0x18000911a  movzx   eax, word ptr [rsi]
0x18000911d  cmp     ax, r13w
0x180009121  jz      short loc_18000912F
0x180009123  add     rsi, 2
0x180009127  movzx   eax, word ptr [rsi]
0x18000912a  test    ax, ax
0x18000912d  jnz     short loc_18000911D
0x18000912f  cmp     [rsi], r12w
0x180009133  jz      short loc_180009158
0x180009135  mov     [rsi], r12w
0x180009139  lea     rax, [rsi+2]
0x18000913d  mov     rdx, r12
0x180009140  cmp     rax, [rsp+88h+ppszEnd]
0x180009145  cmovz   rdx, r15
0x180009149  mov     rcx, rbx; dwItem1
0x18000914c  call    Win32CreateDirectory
0x180009151  test    eax, eax
0x180009153  jz      short loc_1800091AB
0x180009155  mov     edi, r12d
0x180009158  mov     [rsi], r13w
0x18000915c  add     rsi, 2
0x180009160  cmp     [rsi], r12w
0x180009164  jnz     short loc_18000911A
0x180009166  lea     rcx, [rsp+88h+pszPath]
0x18000916e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180009173  nop
0x180009174  test    edi, edi
0x180009176  jz      loc_180009057
0x18000917c  test    r14, r14
0x18000917f  jz      loc_180009057
0x180009185  mov     ebx, 4C7h
0x18000918a  cmp     edi, ebx
0x18000918c  jz      loc_180009057
0x180009192  call    IsSHSysErrorMessageBoxPresent
0x180009197  test    al, al
0x180009199  jz      short loc_180009218
0x18000919b  test    rbp, rbp
0x18000919e  jz      short loc_1800091F4
0x1800091a0  mov     rcx, rbp; pszPath
0x1800091a3  call    cs:__imp_PathFindFileNameW
0x1800091a9  jmp     short loc_1800091F7
0x1800091ab  call    cs:__imp_GetLastError
0x1800091b1  mov     edi, eax
0x1800091b3  jmp     short loc_180009158
0x1800091b5  lea     rcx, [rsp+88h+pszPath]
0x1800091bd  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800091c2  nop
0x1800091c3  mov     edi, 0Eh
0x1800091c8  jmp     loc_180009057
0x1800091cd  cmp     rsi, 104h
0x1800091d4  jbe     loc_1800090C4
0x1800091da  jmp     short loc_1800091EA
0x1800091dc  lea     rcx, [rsp+88h+pszPath]
0x1800091e4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800091e9  nop
0x1800091ea  mov     edi, 0CEh
0x1800091ef  jmp     loc_180009057
0x1800091f4  mov     rax, r12
0x1800091f7  mov     [rsp+88h+var_60], 30h ; '0'
0x1800091ff  mov     [rsp+88h+var_68], rax
0x180009204  mov     r9d, edi
0x180009207  xor     edx, edx
0x180009209  mov     r8d, 221Ah
0x18000920f  mov     rcx, r14
0x180009212  call    cs:__imp_SHSysErrorMessageBox
0x180009218  mov     edi, ebx
0x18000921a  jmp     loc_180009057
```
