# _CreateDirectoryHelper

- ea: `0x180008df0`
- end: `0x180009008`
- name: `_CreateDirectoryHelper`
- size: `536`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180008d10`
- `0x18005d3d0`

## callees

- `0x180008d90`
- `0x180008df0`
- `0x180009230`
- `0x1800095bc`
- `0x18001adc4`
- `0x1800688d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008f9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008f9a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008e84`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008e84`
- `ntdll!RtlAreLongPathsEnabled` at `0x180008ea1`
- `ntdll!RtlAreLongPathsEnabled` at `0x180008ea1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008f53`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008f53`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180008e27`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180008e27`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x180008e14`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x180008e14`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180008f92`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180008f92`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslashEx` at `0x180008ee1`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslashEx` at `0x180008ee1`
- `api-ms-win-shell-changenotify-l1-1-0!SHChangeNotify` at `0x180008e75`
- `api-ms-win-shell-changenotify-l1-1-0!SHChangeNotify` at `0x180008e75`
- `ext-ms-win-shell-directory-l1-1-0!SHSysErrorMessageBox` at `0x180008ffb`
- `ext-ms-win-shell-directory-l1-1-0!SHSysErrorMessageBox` at `0x180008ffb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
DWORD __fastcall CreateDirectoryHelper(__int64 a1, const WCHAR *a2, struct _SECURITY_ATTRIBUTES *a3, int a4)
{
  const WCHAR *v6; // rbp
  DWORD result; // eax
  DWORD LastError; // edi
  __int64 v10; // rax
  unsigned __int64 v11; // rsi
  PWSTR v12; // rbx
  __int16 *v13; // rsi
  __int16 v14; // ax
  LPWSTR FileNameW; // rax
  PWSTR pszPath; // [rsp+30h] [rbp-58h] BYREF
  PWSTR ppszEnd; // [rsp+38h] [rbp-50h] BYREF

  v6 = a2;
  if ( PathIsRelativeW(a2) )
  {
    SetLastError(0xA1u);
    return 161;
  }
  if ( CreateDirectoryW(v6, a3) )
  {
    LastError = 0;
    if ( !(unsigned int)IsNotifySuspended() && (unsigned __int8)IsSHSysErrorMessageBoxPresent() )
      SHChangeNotify(8, 5u, v6, 0);
    return LastError;
  }
  result = GetLastError();
  LastError = result;
  if ( result == 3 )
  {
    v10 = -1;
    do
      ++v10;
    while ( v6[v10] );
    v11 = v10 + 1;
    if ( !(unsigned __int8)RtlAreLongPathsEnabled() && v11 > 0x104 )
      return 206;
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &pszPath,
      v6,
      v11);
    v12 = pszPath;
    if ( !pszPath )
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszPath);
      return 14;
    }
    ppszEnd = 0;
    if ( PathCchAddBackslashEx(pszPath, v11 + 1, &ppszEnd, 0) < 0 )
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszPath);
      return 206;
    }
    v13 = (__int16 *)(v12 + 3);
    if ( v12[3] )
    {
      do
      {
        v14 = *v13;
        do
        {
          if ( v14 == 92 )
            break;
          v14 = *++v13;
        }
        while ( *v13 );
        if ( *v13 )
        {
          *v13 = 0;
          if ( (unsigned int)Win32CreateDirectory(v12) )
            LastError = 0;
          else
            LastError = GetLastError();
        }
        *v13++ = 92;
      }
      while ( *v13 );
      v6 = a2;
    }
    LocalFree(v12);
    if ( LastError && a1 && LastError != 1223 )
    {
      if ( a4 && (unsigned __int8)IsSHSysErrorMessageBoxPresent() )
      {
        if ( v6 )
          FileNameW = PathFindFileNameW(v6);
        else
          FileNameW = 0;
        SHSysErrorMessageBox(a1, 0, 8730, LastError, FileNameW, 48);
      }
      return 1223;
    }
    return LastError;
  }
  return result;
}

```

## disassembly

```asm
0x180008df0  mov     [rsp+arg_8], rdx
0x180008df5  push    rbx
0x180008df6  push    rbp
0x180008df7  push    rsi
0x180008df8  push    rdi
0x180008df9  push    r12
0x180008dfb  push    r13
0x180008dfd  push    r14
0x180008dff  push    r15
0x180008e01  sub     rsp, 48h
0x180008e05  mov     r12d, r9d
0x180008e08  mov     r15, r8
0x180008e0b  mov     rbp, rdx
0x180008e0e  mov     r14, rcx
0x180008e11  mov     rcx, rdx; pszPath
0x180008e14  call    cs:__imp_PathIsRelativeW
0x180008e1a  xor     r13d, r13d
0x180008e1d  test    eax, eax
0x180008e1f  jnz     short loc_180008E7D
0x180008e21  mov     rdx, r15; lpSecurityAttributes
0x180008e24  mov     rcx, rbp; lpPathName
0x180008e27  call    cs:__imp_CreateDirectoryW
0x180008e2d  test    eax, eax
0x180008e2f  jnz     short loc_180008E4F
0x180008e31  call    cs:__imp_GetLastError
0x180008e37  mov     edi, eax
0x180008e39  cmp     eax, 3
0x180008e3c  jz      short loc_180008E8E
0x180008e3e  add     rsp, 48h
0x180008e42  pop     r15
0x180008e44  pop     r14
0x180008e46  pop     r13
0x180008e48  pop     r12
0x180008e4a  pop     rdi
0x180008e4b  pop     rsi
0x180008e4c  pop     rbp
0x180008e4d  pop     rbx
0x180008e4e  retn
0x180008e4f  mov     edi, r13d
0x180008e52  call    IsNotifySuspended
0x180008e57  test    eax, eax
0x180008e59  jnz     short loc_180008E64
0x180008e5b  call    IsSHSysErrorMessageBoxPresent
0x180008e60  test    al, al
0x180008e62  jnz     short loc_180008E68
0x180008e64  mov     eax, edi
0x180008e66  jmp     short loc_180008E3E
0x180008e68  xor     r9d, r9d; dwItem2
0x180008e6b  mov     r8, rbp; dwItem1
0x180008e6e  lea     edx, [r9+5]; uFlags
0x180008e72  lea     ecx, [rdx+3]; wEventId
0x180008e75  call    cs:__imp_SHChangeNotify
0x180008e7b  jmp     short loc_180008E64
0x180008e7d  mov     ebx, 0A1h
0x180008e82  mov     ecx, ebx; dwErrCode
0x180008e84  call    cs:__imp_SetLastError
0x180008e8a  mov     eax, ebx
0x180008e8c  jmp     short loc_180008E3E
0x180008e8e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008e92  inc     rax
0x180008e95  cmp     [rbp+rax*2+0], r13w
0x180008e9b  jnz     short loc_180008E92
0x180008e9d  lea     rsi, [rax+1]
0x180008ea1  call    cs:__imp_RtlAreLongPathsEnabled
0x180008ea7  test    al, al
0x180008ea9  jz      loc_180008FB9
0x180008eaf  mov     r8, rsi
0x180008eb2  mov     rdx, rbp
0x180008eb5  lea     rcx, [rsp+88h+pszPath]
0x180008eba  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180008ebf  mov     rbx, [rsp+88h+pszPath]
0x180008ec4  test    rbx, rbx
0x180008ec7  jz      loc_180008FA4
0x180008ecd  mov     [rsp+88h+ppszEnd], r13
0x180008ed2  lea     rdx, [rsi+1]; cchPath
0x180008ed6  xor     r9d, r9d; pcchRemaining
0x180008ed9  lea     r8, [rsp+88h+ppszEnd]; ppszEnd
0x180008ede  mov     rcx, rbx; pszPath
0x180008ee1  call    cs:__imp_PathCchAddBackslashEx
0x180008ee7  test    eax, eax
0x180008ee9  js      loc_180008FC8
0x180008eef  lea     rsi, [rbx+6]
0x180008ef3  cmp     [rsi], r13w
0x180008ef7  jz      short loc_180008F50
0x180008ef9  mov     ebp, 5Ch ; '\'
0x180008efe  movzx   eax, word ptr [rsi]
0x180008f01  cmp     ax, bp
0x180008f04  jz      short loc_180008F12
0x180008f06  add     rsi, 2
0x180008f0a  movzx   eax, word ptr [rsi]
0x180008f0d  test    ax, ax
0x180008f10  jnz     short loc_180008F01
0x180008f12  cmp     [rsi], r13w
0x180008f16  jz      short loc_180008F3B
0x180008f18  mov     [rsi], r13w
0x180008f1c  lea     rax, [rsi+2]
0x180008f20  mov     rdx, r13
0x180008f23  cmp     rax, [rsp+88h+ppszEnd]
0x180008f28  cmovz   rdx, r15
0x180008f2c  mov     rcx, rbx; dwItem1
0x180008f2f  call    Win32CreateDirectory
0x180008f34  test    eax, eax
0x180008f36  jz      short loc_180008F9A
0x180008f38  mov     edi, r13d
0x180008f3b  mov     [rsi], bp
0x180008f3e  add     rsi, 2
0x180008f42  cmp     [rsi], r13w
0x180008f46  jnz     short loc_180008EFE
0x180008f48  mov     rbp, [rsp+88h+arg_8]
0x180008f50  mov     rcx, rbx; hMem
0x180008f53  call    cs:__imp_LocalFree
0x180008f59  nop
0x180008f5a  test    edi, edi
0x180008f5c  jz      loc_180008E64
0x180008f62  test    r14, r14
0x180008f65  jz      loc_180008E64
0x180008f6b  mov     ebx, 4C7h
0x180008f70  cmp     edi, ebx
0x180008f72  jz      loc_180008E64
0x180008f78  test    r12d, r12d
0x180008f7b  jz      loc_180009001
0x180008f81  call    IsSHSysErrorMessageBoxPresent
0x180008f86  test    al, al
0x180008f88  jz      short loc_180009001
0x180008f8a  test    rbp, rbp
0x180008f8d  jz      short loc_180008FDD
0x180008f8f  mov     rcx, rbp; pszPath
0x180008f92  call    cs:__imp_PathFindFileNameW
0x180008f98  jmp     short loc_180008FE0
0x180008f9a  call    cs:__imp_GetLastError
0x180008fa0  mov     edi, eax
0x180008fa2  jmp     short loc_180008F3B
0x180008fa4  lea     rcx, [rsp+88h+pszPath]
0x180008fa9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180008fae  nop
0x180008faf  mov     eax, 0Eh
0x180008fb4  jmp     loc_180008E3E
0x180008fb9  cmp     rsi, 104h
0x180008fc0  jbe     loc_180008EAF
0x180008fc6  jmp     short loc_180008FD3
0x180008fc8  lea     rcx, [rsp+88h+pszPath]
0x180008fcd  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180008fd2  nop
0x180008fd3  mov     eax, 0CEh
0x180008fd8  jmp     loc_180008E3E
0x180008fdd  mov     rax, r13
0x180008fe0  mov     [rsp+88h+var_60], 30h ; '0'
0x180008fe8  mov     [rsp+88h+var_68], rax
0x180008fed  mov     r9d, edi
0x180008ff0  xor     edx, edx
0x180008ff2  mov     r8d, 221Ah
0x180008ff8  mov     rcx, r14
0x180008ffb  call    cs:__imp_SHSysErrorMessageBox
0x180009001  mov     edi, ebx
0x180009003  jmp     loc_180008E64
```
