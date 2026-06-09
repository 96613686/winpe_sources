# IsDirectoryStale(ushort const *,unsigned __int64,int *)

- ea: `0x180018290`
- end: `0x180018469`
- name: `?IsDirectoryStale@@YAJPEBG_KPEAH@Z`
- size: `473`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, service_task`

## callers

- `0x180016cc0`

## callees

- `0x1800068f0`
- `0x180018290`
- `0x180019108`
- `0x18001bd48`
- `0x18001c1a0`
- `0x18001c2e0`
- `0x180078a40`
- `0x1800c50aa`
- `0x1800c50f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800183ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018429`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800183ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018429`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800183a1`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800183a1`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180018359`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180018359`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800183e4`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180018457`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800183e4`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180018457`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1800182c5`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1800182c5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001837a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001837a`

## string_xrefs

- `0x1800182fb`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180018444`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`

## pseudocode

```c
__int64 __fastcall IsDirectoryStale(const unsigned __int16 *a1, __int64 a2, int *a3)
{
  __int64 v5; // r9
  unsigned int v6; // ebx
  HANDLE FirstFileW; // rdi
  FILETIME ftLastWriteTime; // rbx
  signed int LastError; // eax
  struct _FILETIME SystemTimeAsFileTime; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+38h] [rbp-C8h] BYREF
  char v13; // [rsp+48h] [rbp-B8h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+60h] [rbp-A0h] BYREF

  *a3 = 0;
  if ( PathFileExistsW(a1) )
  {
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(lpFileName);
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                             lpFileName,
                             a1) )
    {
      v5 = 809;
LABEL_4:
      v6 = -2147024882;
      Log_UnistoreHREvent_0(
        2147942414LL,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
        v5);
LABEL_5:
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpFileName);
      return v6;
    }
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             lpFileName,
                             L"*",
                             1) )
    {
      v5 = 810;
      goto LABEL_4;
    }
    memset_0(&FindFileData, 0, sizeof(FindFileData));
    FirstFileW = FindFirstFileW(lpFileName[0], &FindFileData);
    if ( FirstFileW == (HANDLE)-1LL )
    {
      v6 = 0;
      goto LABEL_5;
    }
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    ftLastWriteTime = 0;
    do
    {
      if ( (FindFileData.dwFileAttributes & 0x10) == 0
        && *(_QWORD *)&FindFileData.ftLastWriteTime > *(unsigned __int64 *)&ftLastWriteTime )
      {
        ftLastWriteTime = FindFileData.ftLastWriteTime;
      }
    }
    while ( FindNextFileW(FirstFileW, &FindFileData) );
    if ( GetLastError() != 18 )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      Log_UnistoreHREvent_0(
        v6,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
        839);
      FindClose(FirstFileW);
      goto LABEL_5;
    }
    if ( *(_QWORD *)&ftLastWriteTime
      && *(_QWORD *)&ftLastWriteTime < *(unsigned __int64 *)&SystemTimeAsFileTime
      && *(_QWORD *)&SystemTimeAsFileTime - *(_QWORD *)&ftLastWriteTime >= 0x1792F864A710uLL )
    {
      *a3 = 1;
    }
    FindClose(FirstFileW);
    if ( (char *)lpFileName[0] != &v13 )
      operator delete((void *)lpFileName[0]);
  }
  return 0;
}

```

## disassembly

```asm
0x180018290  mov     [rsp-8+arg_8], rbx
0x180018295  push    rbp
0x180018296  push    rsi
0x180018297  push    rdi
0x180018298  lea     rbp, [rsp-1C0h]
0x1800182a0  sub     rsp, 2C0h
0x1800182a7  mov     rax, cs:__security_cookie
0x1800182ae  xor     rax, rsp
0x1800182b1  mov     [rbp+1D0h+var_20], rax
0x1800182b8  mov     rsi, r8
0x1800182bb  mov     dword ptr [r8], 0
0x1800182c2  mov     rbx, rcx
0x1800182c5  call    cs:__imp_PathFileExistsW
0x1800182cb  test    eax, eax
0x1800182cd  jz      loc_180018405
0x1800182d3  lea     rcx, [rsp+2D0h+lpFileName]
0x1800182d8  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x1800182dd  mov     rdx, rbx
0x1800182e0  lea     rcx, [rsp+2D0h+lpFileName]
0x1800182e5  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x1800182ea  test    al, al
0x1800182ec  jnz     short loc_18001831A
0x1800182ee  mov     r9d, 329h
0x1800182f4  xor     edx, edx
0x1800182f6  mov     ebx, 8007000Eh
0x1800182fb  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180018302  mov     ecx, ebx
0x180018304  call    Log_UnistoreHREvent_0
0x180018309  lea     rcx, [rsp+2D0h+lpFileName]
0x18001830e  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180018313  mov     eax, ebx
0x180018315  jmp     loc_180018407
0x18001831a  mov     r8d, 1
0x180018320  lea     rdx, pszMore; "*"
0x180018327  lea     rcx, [rsp+2D0h+lpFileName]
0x18001832c  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180018331  xor     edx, edx; Val
0x180018333  test    al, al
0x180018335  jnz     short loc_18001833F
0x180018337  mov     r9d, 32Ah
0x18001833d  jmp     short loc_1800182F6
0x18001833f  mov     r8d, 250h; Size
0x180018345  lea     rcx, [rsp+2D0h+FindFileData]; void *
0x18001834a  call    memset_0
0x18001834f  mov     rcx, [rsp+2D0h+lpFileName]; lpFileName
0x180018354  lea     rdx, [rsp+2D0h+FindFileData]; lpFindFileData
0x180018359  call    cs:__imp_FindFirstFileW
0x18001835f  mov     rdi, rax
0x180018362  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180018366  jz      loc_180018462
0x18001836c  lea     rcx, [rsp+2D0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180018371  mov     qword ptr [rsp+2D0h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18001837a  call    cs:__imp_GetSystemTimeAsFileTime
0x180018380  mov     rbx, cs:qword_1800DB318
0x180018387  test    byte ptr [rsp+2D0h+FindFileData.dwFileAttributes], 10h
0x18001838c  jnz     short loc_180018399
0x18001838e  cmp     qword ptr [rsp+2D0h+FindFileData.ftLastWriteTime.dwLowDateTime], rbx
0x180018393  cmova   rbx, qword ptr [rsp+2D0h+FindFileData.ftLastWriteTime.dwLowDateTime]
0x180018399  lea     rdx, [rsp+2D0h+FindFileData]; lpFindFileData
0x18001839e  mov     rcx, rdi; hFindFile
0x1800183a1  call    cs:__imp_FindNextFileW
0x1800183a7  test    eax, eax
0x1800183a9  jnz     short loc_180018387
0x1800183ab  call    cs:__imp_GetLastError
0x1800183b1  cmp     eax, 12h
0x1800183b4  jnz     short loc_180018429
0x1800183b6  cmp     rbx, cs:qword_1800DB318
0x1800183bd  jz      short loc_1800183E1
0x1800183bf  mov     rax, qword ptr [rsp+2D0h+SystemTimeAsFileTime.dwLowDateTime]
0x1800183c4  cmp     rbx, rax
0x1800183c7  jnb     short loc_1800183E1
0x1800183c9  sub     rax, rbx
0x1800183cc  mov     rcx, 1792F864A710h
0x1800183d6  cmp     rax, rcx
0x1800183d9  jb      short loc_1800183E1
0x1800183db  mov     dword ptr [rsi], 1
0x1800183e1  mov     rcx, rdi; hFindFile
0x1800183e4  call    cs:__imp_FindClose
0x1800183ea  mov     rcx, [rsp+2D0h+lpFileName]; Block
0x1800183ef  lea     rax, [rsp+2D0h+var_288]
0x1800183f4  cmp     rcx, rax
0x1800183f7  jz      short loc_180018405
0x1800183f9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180018400  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180018405  xor     eax, eax
0x180018407  mov     rcx, [rbp+1D0h+var_20]
0x18001840e  xor     rcx, rsp; StackCookie
0x180018411  call    __security_check_cookie
0x180018416  mov     rbx, [rsp+2D0h+arg_8]
0x18001841e  add     rsp, 2C0h
0x180018425  pop     rdi
0x180018426  pop     rsi
0x180018427  pop     rbp
0x180018428  retn
0x180018429  call    cs:__imp_GetLastError
0x18001842f  mov     ebx, eax
0x180018431  test    eax, eax
0x180018433  jle     short loc_18001843E
0x180018435  movzx   ebx, ax
0x180018438  or      ebx, 80070000h
0x18001843e  mov     r9d, 347h
0x180018444  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001844b  xor     edx, edx
0x18001844d  mov     ecx, ebx
0x18001844f  call    Log_UnistoreHREvent_0
0x180018454  mov     rcx, rdi; hFindFile
0x180018457  call    cs:__imp_FindClose
0x18001845d  jmp     loc_180018309
0x180018462  xor     ebx, ebx
0x180018464  jmp     loc_180018309
```
