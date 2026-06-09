# RemoveDirectoryRecursiveFunc(ushort *,int,int)

- ea: `0x18004a8d8`
- end: `0x18004abf0`
- name: `?RemoveDirectoryRecursiveFunc@@YAJPEAGHH@Z`
- size: `792`
- prototype: `__int64 __fastcall(unsigned __int16 *, int, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18004a8d8`
- `0x18004abf0`

## callees

- `0x180002584`
- `0x180007824`
- `0x18004a8d8`
- `0x18004d030`
- `0x18004d350`
- `0x18004d690`
- `0x18004d754`
- `0x18004d7d4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18004ab7a`
- `KERNEL32!GetLastError` at `0x18004ab7a`
- `KERNEL32!lstrlenW` at `0x18004a91d`
- `KERNEL32!lstrlenW` at `0x18004a978`
- `KERNEL32!lstrlenW` at `0x18004aa28`
- `KERNEL32!lstrlenW` at `0x18004aa35`
- `KERNEL32!lstrlenW` at `0x18004aad0`
- `KERNEL32!lstrlenW` at `0x18004aadd`
- `KERNEL32!lstrlenW` at `0x18004a91d`
- `KERNEL32!lstrlenW` at `0x18004a978`
- `KERNEL32!lstrlenW` at `0x18004aa28`
- `KERNEL32!lstrlenW` at `0x18004aa35`
- `KERNEL32!lstrlenW` at `0x18004aad0`
- `KERNEL32!lstrlenW` at `0x18004aadd`
- `KERNEL32!FindClose` at `0x18004ab88`
- `KERNEL32!FindClose` at `0x18004abb4`
- `KERNEL32!FindClose` at `0x18004ab88`
- `KERNEL32!FindClose` at `0x18004abb4`
- `KERNEL32!FindFirstFileW` at `0x18004a9cc`
- `KERNEL32!FindFirstFileW` at `0x18004a9cc`
- `KERNEL32!lstrcmpW` at `0x18004a9fd`
- `KERNEL32!lstrcmpW` at `0x18004aa17`
- `KERNEL32!lstrcmpW` at `0x18004a9fd`
- `KERNEL32!lstrcmpW` at `0x18004aa17`
- `KERNEL32!FindNextFileW` at `0x18004ab6c`
- `KERNEL32!FindNextFileW` at `0x18004ab6c`
- `KERNEL32!DeleteFileW` at `0x18004ab5e`
- `KERNEL32!DeleteFileW` at `0x18004ab5e`
- `KERNEL32!RemoveDirectoryW` at `0x18004ab9b`
- `KERNEL32!RemoveDirectoryW` at `0x18004ab9b`

## pseudocode

```c
__int64 __fastcall RemoveDirectoryRecursiveFunc(unsigned __int16 *a1, int a2, int a3)
{
  WCHAR *v3; // rdi
  unsigned int LastWin32Error; // ebx
  int v8; // eax
  unsigned __int64 v9; // rbp
  unsigned __int16 *v10; // rax
  int v11; // eax
  HANDLE FirstFileW; // rbp
  int v13; // ebx
  unsigned __int64 v14; // r14
  SIZE_T v15; // rax
  unsigned __int16 *v16; // rax
  int v17; // ebx
  unsigned __int64 v18; // r14
  SIZE_T v19; // rax
  unsigned __int16 *v20; // rax
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+20h] [rbp-288h] BYREF

  v3 = 0;
  if ( a1 && (v8 = lstrlenW(a1) + 5, v8 < 0x3FFFFFFF) )
  {
    v9 = v8;
    v10 = (unsigned __int16 *)MemAlloc(saturated_mul(v8, 2u));
    v3 = v10;
    if ( v10 )
    {
      LastWin32Error = StringCchCopyW(v10, v9, a1);
      if ( !LastWin32Error )
      {
        v11 = lstrlenW(v3) - 1;
        if ( v11 < 0 || v3[v11] == 92 || (LastWin32Error = StringCchCatW(v3, v9, L"\\")) == 0 )
        {
          LastWin32Error = StringCchCatW(v3, v9, L"*.*");
          if ( !LastWin32Error )
          {
            FirstFileW = FindFirstFileW(v3, &FindFileData);
            if ( FirstFileW == (HANDLE)-1LL )
            {
              LastWin32Error = GetLastWin32Error();
            }
            else
            {
              do
              {
                if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
                {
                  if ( lstrcmpW(FindFileData.cFileName, L".") && lstrcmpW(FindFileData.cFileName, L"..") )
                  {
                    v13 = lstrlenW(a1);
                    v14 = v13 + lstrlenW(FindFileData.cFileName) + 2;
                    v15 = 2 * v14;
                    if ( !is_mul_ok(v14, 2u) )
                      v15 = -1;
                    v16 = (unsigned __int16 *)MemReAlloc(v3, v15);
                    v3 = v16;
                    if ( !v16 )
                      goto LABEL_36;
                    LastWin32Error = StringCchCopyW(v16, v14, a1);
                    if ( LastWin32Error )
                      goto LABEL_37;
                    LastWin32Error = StringCchCatW(v3, v14, L"\\");
                    if ( LastWin32Error )
                      goto LABEL_37;
                    LastWin32Error = StringCchCatW(v3, v14, FindFileData.cFileName);
                    if ( LastWin32Error )
                      goto LABEL_37;
                    RemoveDirectoryRecursiveFunc(v3, 0, 0);
                  }
                }
                else
                {
                  v17 = lstrlenW(a1);
                  v18 = v17 + lstrlenW(FindFileData.cFileName) + 2;
                  v19 = 2 * v18;
                  if ( !is_mul_ok(v18, 2u) )
                    v19 = -1;
                  v20 = (unsigned __int16 *)MemReAlloc(v3, v19);
                  v3 = v20;
                  if ( !v20 )
                  {
LABEL_36:
                    LastWin32Error = -2147024882;
                    goto LABEL_37;
                  }
                  LastWin32Error = StringCchCopyW(v20, v18, a1);
                  if ( LastWin32Error )
                    goto LABEL_37;
                  LastWin32Error = StringCchCatW(v3, v18, L"\\");
                  if ( LastWin32Error )
                    goto LABEL_37;
                  LastWin32Error = StringCchCatW(v3, v18, FindFileData.cFileName);
                  if ( LastWin32Error )
                    goto LABEL_37;
                  DeleteFileW(v3);
                }
              }
              while ( FindNextFileW(FirstFileW, &FindFileData) );
              if ( GetLastError() != 18 )
              {
                LastWin32Error = GetLastWin32Error();
LABEL_37:
                FindClose(FirstFileW);
                goto LABEL_38;
              }
              FindClose(FirstFileW);
              if ( !a2 || a3 )
                RemoveDirectoryW(a1);
            }
          }
        }
      }
    }
    else
    {
      LastWin32Error = -2147024882;
    }
  }
  else
  {
    LastWin32Error = -2147024809;
  }
LABEL_38:
  MemFree(v3);
  return LastWin32Error;
}

```

## disassembly

```asm
0x18004a8d8  mov     [rsp+arg_8], rbx
0x18004a8dd  mov     [rsp+arg_10], rbp
0x18004a8e2  push    rsi
0x18004a8e3  push    rdi
0x18004a8e4  push    r12
0x18004a8e6  push    r14
0x18004a8e8  push    r15
0x18004a8ea  sub     rsp, 280h
0x18004a8f1  mov     rax, cs:__security_cookie
0x18004a8f8  xor     rax, rsp
0x18004a8fb  mov     [rsp+2A8h+var_38], rax
0x18004a903  xor     edi, edi
0x18004a905  mov     r15d, r8d
0x18004a908  mov     r12d, edx
0x18004a90b  mov     rsi, rcx
0x18004a90e  test    rcx, rcx
0x18004a911  jnz     short loc_18004A91D
0x18004a913  mov     ebx, 80070057h
0x18004a918  jmp     loc_18004ABBA
0x18004a91d  call    cs:__imp_lstrlenW
0x18004a923  add     eax, 5
0x18004a926  cmp     eax, 3FFFFFFFh
0x18004a92b  jge     short loc_18004A913
0x18004a92d  movsxd  rbp, eax
0x18004a930  mov     r14, 0FFFFFFFFFFFFFFFFh
0x18004a937  mov     eax, 2
0x18004a93c  mul     rbp
0x18004a93f  cmovo   rax, r14
0x18004a943  mov     rcx, rax; unsigned __int64
0x18004a946  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x18004a94b  mov     rdi, rax
0x18004a94e  test    rax, rax
0x18004a951  jnz     short loc_18004A95D
0x18004a953  mov     ebx, 8007000Eh
0x18004a958  jmp     loc_18004ABBA
0x18004a95d  mov     r8, rsi; unsigned __int16 *
0x18004a960  mov     rdx, rbp; unsigned __int64
0x18004a963  mov     rcx, rdi; unsigned __int16 *
0x18004a966  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004a96b  mov     ebx, eax
0x18004a96d  test    eax, eax
0x18004a96f  jnz     loc_18004ABBA
0x18004a975  mov     rcx, rdi; lpString
0x18004a978  call    cs:__imp_lstrlenW
0x18004a97e  sub     eax, 1
0x18004a981  js      short loc_18004A9A8
0x18004a983  cdqe
0x18004a985  cmp     word ptr [rdi+rax*2], 5Ch ; '\'
0x18004a98a  jz      short loc_18004A9A8
0x18004a98c  lea     r8, SubBlock; "\\"
0x18004a993  mov     rdx, rbp; unsigned __int64
0x18004a996  mov     rcx, rdi; unsigned __int16 *
0x18004a999  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004a99e  mov     ebx, eax
0x18004a9a0  test    eax, eax
0x18004a9a2  jnz     loc_18004ABBA
0x18004a9a8  lea     r8, asc_180076CF0; "*.*"
0x18004a9af  mov     rdx, rbp; unsigned __int64
0x18004a9b2  mov     rcx, rdi; unsigned __int16 *
0x18004a9b5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004a9ba  mov     ebx, eax
0x18004a9bc  test    eax, eax
0x18004a9be  jnz     loc_18004ABBA
0x18004a9c4  lea     rdx, [rsp+2A8h+FindFileData]; lpFindFileData
0x18004a9c9  mov     rcx, rdi; lpFileName
0x18004a9cc  call    cs:__imp_FindFirstFileW
0x18004a9d2  mov     rbp, rax
0x18004a9d5  cmp     rax, r14
0x18004a9d8  jnz     short loc_18004A9E6
0x18004a9da  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18004a9df  mov     ebx, eax
0x18004a9e1  jmp     loc_18004ABBA
0x18004a9e6  test    byte ptr [rsp+2A8h+FindFileData.dwFileAttributes], 10h
0x18004a9eb  jz      loc_18004AACD
0x18004a9f1  lea     rdx, asc_1800766B0; "."
0x18004a9f8  lea     rcx, [rsp+2A8h+FindFileData.cFileName]; lpString1
0x18004a9fd  call    cs:__imp_lstrcmpW
0x18004aa03  test    eax, eax
0x18004aa05  jz      loc_18004AB64
0x18004aa0b  lea     rdx, asc_1800766B4; ".."
0x18004aa12  lea     rcx, [rsp+2A8h+FindFileData.cFileName]; lpString1
0x18004aa17  call    cs:__imp_lstrcmpW
0x18004aa1d  test    eax, eax
0x18004aa1f  jz      loc_18004AB64
0x18004aa25  mov     rcx, rsi; lpString
0x18004aa28  call    cs:__imp_lstrlenW
0x18004aa2e  lea     rcx, [rsp+2A8h+FindFileData.cFileName]; lpString
0x18004aa33  mov     ebx, eax
0x18004aa35  call    cs:__imp_lstrlenW
0x18004aa3b  lea     ecx, [rax+2]
0x18004aa3e  mov     eax, 2
0x18004aa43  add     ecx, ebx
0x18004aa45  movsxd  r14, ecx
0x18004aa48  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18004aa4f  mul     r14
0x18004aa52  cmovo   rax, rcx
0x18004aa56  mov     rcx, rdi; lpMem
0x18004aa59  mov     rdx, rax; dwBytes
0x18004aa5c  call    ?MemReAlloc@@YAPEAXPEAX_K@Z; MemReAlloc(void *,unsigned __int64)
0x18004aa61  mov     rdi, rax
0x18004aa64  test    rax, rax
0x18004aa67  jz      loc_18004ABAC
0x18004aa6d  mov     r8, rsi; unsigned __int16 *
0x18004aa70  mov     rdx, r14; unsigned __int64
0x18004aa73  mov     rcx, rax; unsigned __int16 *
0x18004aa76  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004aa7b  mov     ebx, eax
0x18004aa7d  test    eax, eax
0x18004aa7f  jnz     loc_18004ABB1
0x18004aa85  lea     r8, SubBlock; "\\"
0x18004aa8c  mov     rdx, r14; unsigned __int64
0x18004aa8f  mov     rcx, rdi; unsigned __int16 *
0x18004aa92  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004aa97  mov     ebx, eax
0x18004aa99  test    eax, eax
0x18004aa9b  jnz     loc_18004ABB1
0x18004aaa1  lea     r8, [rsp+2A8h+FindFileData.cFileName]; unsigned __int16 *
0x18004aaa6  mov     rdx, r14; unsigned __int64
0x18004aaa9  mov     rcx, rdi; unsigned __int16 *
0x18004aaac  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004aab1  mov     ebx, eax
0x18004aab3  test    eax, eax
0x18004aab5  jnz     loc_18004ABB1
0x18004aabb  xor     r8d, r8d; int
0x18004aabe  xor     edx, edx; int
0x18004aac0  mov     rcx, rdi; unsigned __int16 *
0x18004aac3  call    ?RemoveDirectoryRecursiveFunc@@YAJPEAGHH@Z; RemoveDirectoryRecursiveFunc(ushort *,int,int)
0x18004aac8  jmp     loc_18004AB64
0x18004aacd  mov     rcx, rsi; lpString
0x18004aad0  call    cs:__imp_lstrlenW
0x18004aad6  lea     rcx, [rsp+2A8h+FindFileData.cFileName]; lpString
0x18004aadb  mov     ebx, eax
0x18004aadd  call    cs:__imp_lstrlenW
0x18004aae3  lea     ecx, [rax+2]
0x18004aae6  mov     eax, 2
0x18004aaeb  add     ecx, ebx
0x18004aaed  movsxd  r14, ecx
0x18004aaf0  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18004aaf7  mul     r14
0x18004aafa  cmovo   rax, rcx
0x18004aafe  mov     rcx, rdi; lpMem
0x18004ab01  mov     rdx, rax; dwBytes
0x18004ab04  call    ?MemReAlloc@@YAPEAXPEAX_K@Z; MemReAlloc(void *,unsigned __int64)
0x18004ab09  mov     rdi, rax
0x18004ab0c  test    rax, rax
0x18004ab0f  jz      loc_18004ABAC
0x18004ab15  mov     r8, rsi; unsigned __int16 *
0x18004ab18  mov     rdx, r14; unsigned __int64
0x18004ab1b  mov     rcx, rax; unsigned __int16 *
0x18004ab1e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004ab23  mov     ebx, eax
0x18004ab25  test    eax, eax
0x18004ab27  jnz     loc_18004ABB1
0x18004ab2d  lea     r8, SubBlock; "\\"
0x18004ab34  mov     rdx, r14; unsigned __int64
0x18004ab37  mov     rcx, rdi; unsigned __int16 *
0x18004ab3a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004ab3f  mov     ebx, eax
0x18004ab41  test    eax, eax
0x18004ab43  jnz     short loc_18004ABB1
0x18004ab45  lea     r8, [rsp+2A8h+FindFileData.cFileName]; unsigned __int16 *
0x18004ab4a  mov     rdx, r14; unsigned __int64
0x18004ab4d  mov     rcx, rdi; unsigned __int16 *
0x18004ab50  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004ab55  mov     ebx, eax
0x18004ab57  test    eax, eax
0x18004ab59  jnz     short loc_18004ABB1
0x18004ab5b  mov     rcx, rdi; lpFileName
0x18004ab5e  call    cs:__imp_DeleteFileW
0x18004ab64  lea     rdx, [rsp+2A8h+FindFileData]; lpFindFileData
0x18004ab69  mov     rcx, rbp; hFindFile
0x18004ab6c  call    cs:__imp_FindNextFileW
0x18004ab72  test    eax, eax
0x18004ab74  jnz     loc_18004A9E6
0x18004ab7a  call    cs:__imp_GetLastError
0x18004ab80  cmp     eax, 12h
0x18004ab83  jnz     short loc_18004ABA3
0x18004ab85  mov     rcx, rbp; hFindFile
0x18004ab88  call    cs:__imp_FindClose
0x18004ab8e  test    r12d, r12d
0x18004ab91  jz      short loc_18004AB98
0x18004ab93  test    r15d, r15d
0x18004ab96  jz      short loc_18004ABBA
0x18004ab98  mov     rcx, rsi; lpPathName
0x18004ab9b  call    cs:__imp_RemoveDirectoryW
0x18004aba1  jmp     short loc_18004ABBA
0x18004aba3  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18004aba8  mov     ebx, eax
0x18004abaa  jmp     short loc_18004ABB1
0x18004abac  mov     ebx, 8007000Eh
0x18004abb1  mov     rcx, rbp; hFindFile
0x18004abb4  call    cs:__imp_FindClose
0x18004abba  mov     rcx, rdi; lpMem
0x18004abbd  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x18004abc2  mov     eax, ebx
0x18004abc4  mov     rcx, [rsp+2A8h+var_38]
0x18004abcc  xor     rcx, rsp; StackCookie
0x18004abcf  call    __security_check_cookie
0x18004abd4  lea     r11, [rsp+2A8h+var_28]
0x18004abdc  mov     rbx, [r11+38h]
0x18004abe0  mov     rbp, [r11+40h]
0x18004abe4  mov     rsp, r11
0x18004abe7  pop     r15
0x18004abe9  pop     r14
0x18004abeb  pop     r12
0x18004abed  pop     rdi
0x18004abee  pop     rsi
0x18004abef  retn
```
