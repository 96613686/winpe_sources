# ComputeService::Storage::CreateDirectoryChainInJobFake(ushort const *,void *,bool,bool,bool)

- ea: `0x140042bc4`
- end: `0x140042dfb`
- name: `?CreateDirectoryChainInJobFake@Storage@ComputeService@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEBGPEAX_N22@Z`
- size: `567`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, reparse_path, loader_planting, service_task, broker_com_uri`

## callers

- `0x140042e04`
- `0x1400d9948`

## callees

- `0x140005360`
- `0x140008760`
- `0x14000ddac`
- `0x14000ea60`
- `0x140041ff0`
- `0x140042bc4`
- `0x14004398c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140042d33`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140042d33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140042d20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140042d20`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140042d2b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140042d52`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140042d2b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140042d52`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x140042d66`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x140042d66`
- `api-ms-win-core-path-l1-1-0!PathCchSkipRoot` at `0x140042c3b`
- `api-ms-win-core-path-l1-1-0!PathCchSkipRoot` at `0x140042c3b`

## string_xrefs

- `0x140042dd7`: `onecore\vm\compute\shared\storage\storageutilities.cpp`
- `0x140042de9`: `onecore\vm\compute\shared\storage\storageutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void **__fastcall ComputeService::Storage::CreateDirectoryChainInJobFake(
        void **a1,
        const WCHAR *a2,
        __int64 a3,
        __int64 a4,
        char a5,
        unsigned __int8 a6)
{
  const WCHAR *v7; // rcx
  HRESULT v8; // eax
  unsigned __int64 v9; // r8
  PCWSTR v10; // rdx
  PCWSTR *v11; // rax
  const WCHAR *v12; // r14
  unsigned __int64 v13; // rdi
  unsigned __int64 v14; // rcx
  PCWSTR *v15; // rax
  PCWSTR *v16; // rcx
  int v17; // eax
  __int64 v18; // r9
  int v19; // edx
  void *v20; // r8
  void **v21; // rax
  void **v22; // r12
  void *v23; // r13
  void *v24; // r15
  DWORD LastError; // ebx
  const char *v26; // r9
  PCWSTR *v27; // r14
  int v29; // [rsp+20h] [rbp-69h]
  HANDLE hObject[2]; // [rsp+58h] [rbp-31h] BYREF
  PCWSTR ppszRootEnd; // [rsp+68h] [rbp-21h] BYREF
  PCWSTR pszPath[2]; // [rsp+70h] [rbp-19h] BYREF
  unsigned __int64 v33; // [rsp+80h] [rbp-9h]
  unsigned __int64 v34; // [rsp+88h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+4Fh]

  hObject[1] = a1;
  *a1 = (void *)-1LL;
  CommonUtilities::CombineFilePath(pszPath, a2, L".\\");
  ppszRootEnd = 0;
  v7 = (const WCHAR *)pszPath;
  if ( v34 > 7 )
    v7 = pszPath[0];
  v8 = PathCchSkipRoot(v7, &ppszRootEnd);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x18A,
      (unsigned int)"onecore\\vm\\compute\\shared\\storage\\storageutilities.cpp",
      (const char *)(unsigned int)v8,
      v29);
  v9 = v34;
  v10 = pszPath[0];
  if ( v34 <= 7 )
  {
    v12 = (const WCHAR *)pszPath;
    v11 = pszPath;
  }
  else
  {
    v11 = (PCWSTR *)pszPath[0];
    v12 = pszPath[0];
  }
  v13 = ((char *)ppszRootEnd - (char *)v11) >> 1;
  v14 = v33;
  while ( v13 < v14 )
  {
    v15 = pszPath;
    if ( v9 > 7 )
      v15 = (PCWSTR *)v10;
    if ( *((_WORD *)v15 + v13) == 92 )
    {
      v16 = pszPath;
      if ( v9 > 7 )
        v16 = (PCWSTR *)v10;
      *((_WORD *)v16 + v13) = 0;
      if ( v13 == v33 - 1 )
      {
        v17 = a6 ^ 1;
        v18 = (unsigned int)((v17 + 2) << 30);
        v19 = 2 * v17 + 1;
      }
      else
      {
        v19 = 3;
        v18 = 3221225472LL;
      }
      v20 = 0;
      if ( (char *)*a1 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        v20 = *a1;
      v21 = (void **)ComputeService::Storage::OpenDirectoryInJobFake(hObject, v12, v20, v18, v19, 3, 0);
      v22 = v21;
      if ( a1 != v21 )
      {
        v23 = *v21;
        v24 = *a1;
        if ( (char *)*a1 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        {
          LastError = GetLastError();
          CloseHandle(v24);
          SetLastError(LastError);
        }
        *a1 = v23;
        *v22 = (void *)-1LL;
      }
      if ( (unsigned __int64)hObject[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(hObject[0]);
      if ( a5 && !SetFileAttributesW(v12, 2u) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x1BA,
          (unsigned int)"onecore\\vm\\compute\\shared\\storage\\storageutilities.cpp",
          v26);
      v27 = pszPath;
      v10 = pszPath[0];
      v9 = v34;
      if ( v34 > 7 )
        v27 = (PCWSTR *)pszPath[0];
      v12 = (const WCHAR *)v27 + v13 + 1;
      v14 = v33;
    }
    ++v13;
  }
  std::wstring::~wstring(pszPath);
  return a1;
}

```

## disassembly

```asm
0x140042bc4  mov     [rsp-8+arg_10], rbx
0x140042bc9  push    rbp
0x140042bca  push    rsi
0x140042bcb  push    rdi
0x140042bcc  push    r12
0x140042bce  push    r13
0x140042bd0  push    r14
0x140042bd2  push    r15
0x140042bd4  lea     rbp, [rsp-17h]
0x140042bd9  sub     rsp, 0A0h
0x140042be0  mov     rax, cs:__security_cookie
0x140042be7  xor     rax, rsp
0x140042bea  mov     [rbp+47h+var_40], rax
0x140042bee  mov     rsi, rcx
0x140042bf1  mov     [rbp+47h+var_70], rcx
0x140042bf5  mov     [rbp+47h+var_80], 1
0x140042bfc  mov     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x140042c03  mov     [rbp+47h+var_80], 1
0x140042c0a  lea     r8, pszMore; ".\\"
0x140042c11  lea     rcx, [rbp+47h+pszPath]; Src
0x140042c15  call    ?CombineFilePath@CommonUtilities@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; CommonUtilities::CombineFilePath(ushort const *,ushort const *)
0x140042c1a  mov     [rbp+47h+var_80], 3
0x140042c21  mov     [rbp+47h+ppszRootEnd], 0
0x140042c29  lea     rcx, [rbp+47h+pszPath]
0x140042c2d  cmp     [rbp+47h+var_48], 7
0x140042c32  cmova   rcx, [rbp+47h+pszPath]; pszPath
0x140042c37  lea     rdx, [rbp+47h+ppszRootEnd]; ppszRootEnd
0x140042c3b  call    cs:__imp_PathCchSkipRoot
0x140042c41  mov     rcx, [rbp+4Fh]; this
0x140042c45  test    eax, eax
0x140042c47  js      loc_140042DD4
0x140042c4d  mov     r8, [rbp+47h+var_48]
0x140042c51  mov     rdx, [rbp+47h+pszPath]
0x140042c55  cmp     r8, 7
0x140042c59  jbe     short loc_140042C63
0x140042c5b  mov     rax, rdx
0x140042c5e  mov     r14, rdx
0x140042c61  jmp     short loc_140042C6B
0x140042c63  lea     r14, [rbp+47h+pszPath]
0x140042c67  lea     rax, [rbp+47h+pszPath]
0x140042c6b  mov     rdi, [rbp+47h+ppszRootEnd]
0x140042c6f  sub     rdi, rax
0x140042c72  sar     rdi, 1
0x140042c75  mov     rcx, [rbp+47h+var_50]
0x140042c79  jmp     loc_140042D97
0x140042c7e  lea     rax, [rbp+47h+pszPath]
0x140042c82  cmp     r8, 7
0x140042c86  cmova   rax, rdx
0x140042c8a  cmp     word ptr [rax+rdi*2], 5Ch ; '\'
0x140042c8f  jnz     loc_140042D94
0x140042c95  lea     rcx, [rbp+47h+pszPath]
0x140042c99  cmp     r8, 7
0x140042c9d  cmova   rcx, rdx
0x140042ca1  xor     eax, eax
0x140042ca3  mov     [rcx+rdi*2], ax
0x140042ca7  mov     rax, [rbp+47h+var_50]
0x140042cab  dec     rax
0x140042cae  cmp     rdi, rax
0x140042cb1  jnz     short loc_140042CCB
0x140042cb3  movzx   eax, [rbp+47h+arg_28]
0x140042cb7  xor     eax, 1
0x140042cba  lea     r9d, [rax+2]
0x140042cbe  shl     r9d, 1Eh
0x140042cc2  lea     edx, ds:1[rax*2]
0x140042cc9  jmp     short loc_140042CD6
0x140042ccb  mov     edx, 3
0x140042cd0  mov     r9d, 0C0000000h
0x140042cd6  mov     rcx, [rsi]
0x140042cd9  lea     rax, [rcx-1]
0x140042cdd  xor     r8d, r8d
0x140042ce0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140042ce4  cmovbe  r8, rcx
0x140042ce8  mov     [rsp+0D0h+var_A0], 0
0x140042cf0  mov     [rsp+0D0h+var_A8], 3
0x140042cf8  mov     [rsp+0D0h+var_B0], edx
0x140042cfc  mov     rdx, r14
0x140042cff  lea     rcx, [rbp+47h+hObject]
0x140042d03  call    ?OpenDirectoryInJobFake@Storage@ComputeService@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEBGPEAXKKKK1PEA_N@Z; ComputeService::Storage::OpenDirectoryInJobFake(ushort const *,void *,ulong,ulong,ulong,ulong,void *,bool *)
0x140042d08  mov     r12, rax
0x140042d0b  cmp     rsi, rax
0x140042d0e  jz      short loc_140042D44
0x140042d10  mov     r13, [rax]
0x140042d13  mov     r15, [rsi]
0x140042d16  lea     rax, [r15-1]
0x140042d1a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140042d1e  ja      short loc_140042D39
0x140042d20  call    cs:__imp_GetLastError
0x140042d26  mov     ebx, eax
0x140042d28  mov     rcx, r15; hObject
0x140042d2b  call    cs:__imp_CloseHandle
0x140042d31  mov     ecx, ebx; dwErrCode
0x140042d33  call    cs:__imp_SetLastError
0x140042d39  mov     [rsi], r13
0x140042d3c  mov     qword ptr [r12], 0FFFFFFFFFFFFFFFFh
0x140042d44  mov     rcx, [rbp+47h+hObject]; hObject
0x140042d48  lea     rax, [rcx-1]
0x140042d4c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140042d50  ja      short loc_140042D58
0x140042d52  call    cs:__imp_CloseHandle
0x140042d58  cmp     [rbp+47h+arg_20], 0
0x140042d5c  jz      short loc_140042D74
0x140042d5e  mov     edx, 2; dwFileAttributes
0x140042d63  mov     rcx, r14; lpFileName
0x140042d66  call    cs:__imp_SetFileAttributesW
0x140042d6c  mov     rcx, [rbp+4Fh]; this
0x140042d70  test    eax, eax
0x140042d72  jz      short loc_140042DE9
0x140042d74  lea     r14, [rbp+47h+pszPath]
0x140042d78  mov     rdx, [rbp+47h+pszPath]
0x140042d7c  mov     r8, [rbp+47h+var_48]
0x140042d80  cmp     r8, 7
0x140042d84  cmova   r14, rdx
0x140042d88  add     r14, 2
0x140042d8c  lea     r14, [r14+rdi*2]
0x140042d90  mov     rcx, [rbp+47h+var_50]
0x140042d94  inc     rdi
0x140042d97  cmp     rdi, rcx
0x140042d9a  jb      loc_140042C7E
0x140042da0  lea     rcx, [rbp+47h+pszPath]; void *
0x140042da4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140042da9  nop
0x140042daa  mov     rax, rsi
0x140042dad  mov     rcx, [rbp+47h+var_40]
0x140042db1  xor     rcx, rsp; StackCookie
0x140042db4  call    __security_check_cookie
0x140042db9  mov     rbx, [rsp+0D0h+arg_10]
0x140042dc1  add     rsp, 0A0h
0x140042dc8  pop     r15
0x140042dca  pop     r14
0x140042dcc  pop     r13
0x140042dce  pop     r12
0x140042dd0  pop     rdi
0x140042dd1  pop     rsi
0x140042dd2  pop     rbp
0x140042dd3  retn
0x140042dd4  mov     r9d, eax; char *
0x140042dd7  lea     r8, aOnecoreVmCompu_20; "onecore\\vm\\compute\\shared\\storage\\"...
0x140042dde  mov     edx, 18Ah; void *
0x140042de3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140042de9  lea     r8, aOnecoreVmCompu_20; "onecore\\vm\\compute\\shared\\storage\\"...
0x140042df0  mov     edx, 1BAh; void *
0x140042df5  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
