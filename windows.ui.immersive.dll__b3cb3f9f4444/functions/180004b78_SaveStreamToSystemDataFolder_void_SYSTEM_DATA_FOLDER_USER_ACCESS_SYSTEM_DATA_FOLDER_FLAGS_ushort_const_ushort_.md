# SaveStreamToSystemDataFolder(void *,SYSTEM_DATA_FOLDER_USER_ACCESS,SYSTEM_DATA_FOLDER_FLAGS,ushort const *,ushort const *,IStream *,SAVE_STREAM_MODE,ushort * *)

- ea: `0x180004b78`
- end: `0x180004eb5`
- name: `?SaveStreamToSystemDataFolder@@YAJPEAXW4SYSTEM_DATA_FOLDER_USER_ACCESS@@W4SYSTEM_DATA_FOLDER_FLAGS@@PEBG3PEAUIStream@@W4SAVE_STREAM_MODE@@PEAPEAG@Z`
- size: `829`
- prototype: `__int64 __fastcall(void *, __int64, unsigned int, __int64, const WCHAR *pszMore, IStream *pstm, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18007ea40`

## callees

- `0x180004b78`
- `0x1800053a0`
- `0x180006490`
- `0x18000b5b8`
- `0x18003d244`
- `0x180046178`
- `0x180054130`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004e83`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004e83`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180004c7c`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180004c7c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180004e61`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180004e61`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Copy` at `0x180004db2`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Copy` at `0x180004db2`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Size` at `0x180004d8d`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Size` at `0x180004d8d`
- `SHELL32!SHCreateItemFromParsingName` at `0x180004cdc`
- `SHELL32!SHCreateItemFromParsingName` at `0x180004cdc`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180004ca1`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180004ca1`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SaveStreamToSystemDataFolder(
        void *a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        const WCHAR *pszMore,
        IStream *pstm,
        __int64 a7,
        _QWORD *a8)
{
  unsigned int v10; // r15d
  int SharedSystemDataFolder; // eax
  signed int Error; // ebx
  WCHAR *v13; // rdx
  __int64 v14; // r8
  WCHAR *v15; // rcx
  __int64 v16; // rax
  WCHAR *v17; // rdx
  IStream *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rcx
  IStream *pstmTo; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v23; // [rsp+48h] [rbp-B8h] BYREF
  ULARGE_INTEGER pui; // [rsp+50h] [rbp-B0h] BYREF
  void *ppv; // [rsp+58h] [rbp-A8h] BYREF
  LPWSTR StringSid; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR pszPath[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR v28[264]; // [rsp+280h] [rbp+180h] BYREF

  v10 = a2;
  if ( a8 )
    *a8 = 0;
  if ( (a3 & 1) != 0 )
    SharedSystemDataFolder = GetSharedSystemDataFolder(a4, a2, v28);
  else
    SharedSystemDataFolder = GetSystemDataFolderForUser(a1, a4, (unsigned int)a2, v28);
  Error = SharedSystemDataFolder;
  if ( SharedSystemDataFolder >= 0 )
  {
    v13 = v28;
    v14 = 260;
    v15 = pszPath;
    v16 = 2147483646;
    do
    {
      if ( !v16 )
        break;
      if ( !*v13 )
        break;
      *v15++ = *v13++;
      --v16;
      --v14;
    }
    while ( v14 );
    v17 = v15 - 1;
    Error = v14 == 0 ? 0x8007007A : 0;
    if ( v14 )
      v17 = v15;
    *v17 = 0;
    if ( v14 )
    {
      Error = PathCchAppend(pszPath, 0x104u, pszMore);
      if ( Error >= 0 )
      {
        StringSid = 0;
        if ( ConvertSidToStringSidW(a1, &StringSid) || (Error = ResultFromKnownLastError(), Error >= 0) )
        {
          ppv = 0;
          Error = SHCreateItemFromParsingName(v28, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
          if ( Error >= 0 )
          {
            v23 = 0;
            Error = (*(__int64 (__fastcall **)(void *, _QWORD, const GUID *, GUID *, __int64 *))(*(_QWORD *)ppv + 24LL))(
                      ppv,
                      0,
                      &BHID_SFObject,
                      &GUID_0000000b_0000_0000_c000_000000000046,
                      &v23);
            if ( Error < 0 )
              goto LABEL_33;
            pstmTo = 0;
            Error = (*(__int64 (__fastcall **)(__int64, const WCHAR *, __int64, _QWORD, _DWORD, IStream **))(*(_QWORD *)v23 + 24LL))(
                      v23,
                      pszMore,
                      69633,
                      0,
                      0,
                      &pstmTo);
            if ( Error >= 0 )
            {
              Error = (*(__int64 (__fastcall **)(IStream *, _QWORD))(*(_QWORD *)pstmTo + 48LL))(pstmTo, 0);
              if ( Error >= 0 )
              {
                pui.QuadPart = 0;
                Error = IStream_Size(pstm, &pui);
                if ( Error >= 0 )
                {
                  if ( pui.HighPart )
                  {
                    Error = -2147317563;
                  }
                  else
                  {
                    Error = IStream_Copy(pstm, pstmTo, pui.LowPart);
                    if ( Error >= 0 )
                    {
                      Error = (*(__int64 (__fastcall **)(IStream *, _QWORD))(*(_QWORD *)pstmTo + 64LL))(pstmTo, 0);
                      if ( Error >= 0 )
                        Error = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v23 + 72LL))(v23, 0);
                    }
                  }
                }
              }
            }
            v18 = pstmTo;
            pstmTo = 0;
            if ( v18 )
              (*(void (__fastcall **)(IStream *))(*(_QWORD *)v18 + 16LL))(v18);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
            if ( Error < 0
              || (Error = _SetSecurityOnFileOrFolder(pszPath, StringSid, v10, a3), Error < 0)
              || a8 && (Error = _AllocString<CTCoAllocPolicy>(v20, v19, pszPath, a8), Error < 0) )
            {
LABEL_33:
              DeleteFileW(pszPath);
            }
            (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
          }
          LocalFree(StringSid);
        }
      }
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180004b78  push    rbp
0x180004b7a  push    rbx
0x180004b7b  push    rsi
0x180004b7c  push    rdi
0x180004b7d  push    r12
0x180004b7f  push    r13
0x180004b81  push    r14
0x180004b83  push    r15
0x180004b85  lea     rbp, [rsp-3A8h]
0x180004b8d  sub     rsp, 4A8h
0x180004b94  mov     rax, cs:__security_cookie
0x180004b9b  xor     rax, rsp
0x180004b9e  mov     [rbp+3E0h+var_50], rax
0x180004ba5  mov     rdi, [rbp+3E0h+arg_38]
0x180004bac  mov     rsi, rcx
0x180004baf  mov     r12, [rbp+3E0h+pszMore]
0x180004bb6  xor     ecx, ecx
0x180004bb8  mov     r14, [rbp+3E0h+pstm]
0x180004bbf  mov     rax, r9
0x180004bc2  mov     r13d, r8d
0x180004bc5  mov     r15d, edx
0x180004bc8  test    rdi, rdi
0x180004bcb  jz      short loc_180004BD0
0x180004bcd  mov     [rdi], rcx
0x180004bd0  test    r13b, 1
0x180004bd4  jz      short loc_180004BE7
0x180004bd6  lea     r8, [rbp+3E0h+var_260]
0x180004bdd  mov     rcx, rax
0x180004be0  call    ?GetSharedSystemDataFolder@@YAJPEBGW4SYSTEM_DATA_FOLDER_USER_ACCESS@@PEAGI_N@Z
0x180004be5  jmp     short loc_180004C01
0x180004be7  lea     r9, [rbp+3E0h+var_260]
0x180004bee  mov     byte ptr [rsp+4E0h+var_4B8], 1
0x180004bf3  mov     r8d, r15d
0x180004bf6  mov     rdx, rax
0x180004bf9  mov     rcx, rsi
0x180004bfc  call    ?GetSystemDataFolderForUser@@YAJPEAXPEBGW4SYSTEM_DATA_FOLDER_USER_ACCESS@@PEAGI_N@Z
0x180004c01  xor     r10d, r10d
0x180004c04  mov     ebx, eax
0x180004c06  test    eax, eax
0x180004c08  js      loc_180004E8F
0x180004c0e  mov     r11d, 104h
0x180004c14  lea     rdx, [rbp+3E0h+var_260]
0x180004c1b  mov     r8d, r11d
0x180004c1e  lea     rcx, [rsp+4E0h+pszPath]
0x180004c23  mov     eax, 7FFFFFFEh
0x180004c28  test    rax, rax
0x180004c2b  jz      short loc_180004C4C
0x180004c2d  movzx   r9d, word ptr [rdx]
0x180004c31  test    r9w, r9w
0x180004c35  jz      short loc_180004C4C
0x180004c37  mov     [rcx], r9w
0x180004c3b  add     rdx, 2
0x180004c3f  add     rcx, 2
0x180004c43  dec     rax
0x180004c46  sub     r8, 1
0x180004c4a  jnz     short loc_180004C28
0x180004c4c  mov     rax, r8
0x180004c4f  lea     rdx, [rcx-2]
0x180004c53  neg     rax
0x180004c56  sbb     ebx, ebx
0x180004c58  not     ebx
0x180004c5a  and     ebx, 8007007Ah
0x180004c60  test    r8, r8
0x180004c63  cmovnz  rdx, rcx
0x180004c67  mov     [rdx], r10w
0x180004c6b  jz      loc_180004E8F
0x180004c71  mov     r8, r12; pszMore
0x180004c74  lea     rcx, [rsp+4E0h+pszPath]; pszPath
0x180004c79  mov     rdx, r11; cchPath
0x180004c7c  call    cs:__imp_PathCchAppend
0x180004c83  nop     dword ptr [rax+rax+00h]
0x180004c88  xor     ecx, ecx
0x180004c8a  mov     ebx, eax
0x180004c8c  test    eax, eax
0x180004c8e  js      loc_180004E8F
0x180004c94  mov     [rsp+4E0h+StringSid], rcx
0x180004c99  lea     rdx, [rsp+4E0h+StringSid]; StringSid
0x180004c9e  mov     rcx, rsi; Sid
0x180004ca1  call    cs:__imp_ConvertSidToStringSidW
0x180004ca8  nop     dword ptr [rax+rax+00h]
0x180004cad  xor     esi, esi
0x180004caf  test    eax, eax
0x180004cb1  jnz     short loc_180004CC2
0x180004cb3  call    ?ResultFromKnownLastError@@YAJXZ
0x180004cb8  mov     ebx, eax
0x180004cba  test    eax, eax
0x180004cbc  js      loc_180004E8F
0x180004cc2  lea     r9, [rsp+4E0h+ppv]; ppv
0x180004cc7  mov     [rsp+4E0h+ppv], rsi
0x180004ccc  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180004cd3  xor     edx, edx; pbc
0x180004cd5  lea     rcx, [rbp+3E0h+var_260]; pszPath
0x180004cdc  call    cs:__imp_SHCreateItemFromParsingName
0x180004ce3  nop     dword ptr [rax+rax+00h]
0x180004ce8  mov     ebx, eax
0x180004cea  test    eax, eax
0x180004cec  js      loc_180004E7E
0x180004cf2  mov     rcx, [rsp+4E0h+ppv]
0x180004cf7  lea     rdx, [rsp+4E0h+var_498]
0x180004cfc  mov     [rsp+4E0h+var_4C0], rdx
0x180004d01  lea     r9, _GUID_0000000b_0000_0000_c000_000000000046
0x180004d08  lea     r8, BHID_SFObject
0x180004d0f  mov     [rsp+4E0h+var_498], rsi
0x180004d14  xor     edx, edx
0x180004d16  mov     rax, [rcx]
0x180004d19  mov     rax, [rax+18h]
0x180004d1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d22  mov     ebx, eax
0x180004d24  test    eax, eax
0x180004d26  js      loc_180004E5C
0x180004d2c  mov     rcx, [rsp+4E0h+var_498]
0x180004d31  lea     r8, [rsp+4E0h+pstmTo]
0x180004d36  mov     [rsp+4E0h+var_4B8], r8
0x180004d3b  xor     r9d, r9d
0x180004d3e  mov     [rsp+4E0h+pstmTo], rsi
0x180004d43  mov     r8d, 11001h
0x180004d49  mov     rdx, r12
0x180004d4c  mov     dword ptr [rsp+4E0h+var_4C0], esi
0x180004d50  mov     rax, [rcx]
0x180004d53  mov     rax, [rax+18h]
0x180004d57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d5c  mov     ebx, eax
0x180004d5e  test    eax, eax
0x180004d60  js      loc_180004DF9
0x180004d66  mov     rcx, [rsp+4E0h+pstmTo]
0x180004d6b  mov     rdx, rsi
0x180004d6e  mov     rax, [rcx]
0x180004d71  mov     rax, [rax+30h]
0x180004d75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d7a  mov     ebx, eax
0x180004d7c  test    eax, eax
0x180004d7e  js      short loc_180004DF9
0x180004d80  lea     rdx, [rsp+4E0h+pui]; pui
0x180004d85  mov     qword ptr [rsp+4E0h+pui], rsi
0x180004d8a  mov     rcx, r14; pstm
0x180004d8d  call    cs:__imp_IStream_Size
0x180004d94  nop     dword ptr [rax+rax+00h]
0x180004d99  mov     ebx, eax
0x180004d9b  test    eax, eax
0x180004d9d  js      short loc_180004DF9
0x180004d9f  cmp     dword ptr [rsp+4E0h+pui+4], esi
0x180004da3  jnz     short loc_180004DF4
0x180004da5  mov     r8d, dword ptr [rsp+4E0h+pui]; cb
0x180004daa  mov     rcx, r14; pstmFrom
0x180004dad  mov     rdx, [rsp+4E0h+pstmTo]; pstmTo
0x180004db2  call    cs:__imp_IStream_Copy
0x180004db9  nop     dword ptr [rax+rax+00h]
0x180004dbe  mov     ebx, eax
0x180004dc0  test    eax, eax
0x180004dc2  js      short loc_180004DF9
0x180004dc4  mov     rcx, [rsp+4E0h+pstmTo]
0x180004dc9  xor     edx, edx
0x180004dcb  mov     rax, [rcx]
0x180004dce  mov     rax, [rax+40h]
0x180004dd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004dd7  mov     ebx, eax
0x180004dd9  test    eax, eax
0x180004ddb  js      short loc_180004DF9
0x180004ddd  mov     rcx, [rsp+4E0h+var_498]
0x180004de2  xor     edx, edx
0x180004de4  mov     rax, [rcx]
0x180004de7  mov     rax, [rax+48h]
0x180004deb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004df0  mov     ebx, eax
0x180004df2  jmp     short loc_180004DF9
0x180004df4  mov     ebx, 800288C5h
0x180004df9  mov     rcx, [rsp+4E0h+pstmTo]
0x180004dfe  mov     [rsp+4E0h+pstmTo], rsi
0x180004e03  test    rcx, rcx
0x180004e06  jz      short loc_180004E14
0x180004e08  mov     rax, [rcx]
0x180004e0b  mov     rax, [rax+10h]
0x180004e0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e14  mov     rcx, [rsp+4E0h+var_498]
0x180004e19  mov     rax, [rcx]
0x180004e1c  mov     rax, [rax+10h]
0x180004e20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e25  test    ebx, ebx
0x180004e27  js      short loc_180004E5C
0x180004e29  mov     rdx, [rsp+4E0h+StringSid]
0x180004e2e  lea     rcx, [rsp+4E0h+pszPath]
0x180004e33  mov     r9d, r13d
0x180004e36  mov     r8d, r15d
0x180004e39  call    ?_SetSecurityOnFileOrFolder@@YAJPEBG0W4SYSTEM_DATA_FOLDER_USER_ACCESS@@W4SYSTEM_DATA_FOLDER_FLAGS@@@Z
0x180004e3e  mov     ebx, eax
0x180004e40  test    eax, eax
0x180004e42  js      short loc_180004E5C
0x180004e44  test    rdi, rdi
0x180004e47  jz      short loc_180004E6D
0x180004e49  mov     r9, rdi
0x180004e4c  lea     r8, [rsp+4E0h+pszPath]
0x180004e51  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z
0x180004e56  mov     ebx, eax
0x180004e58  test    eax, eax
0x180004e5a  jns     short loc_180004E6D
0x180004e5c  lea     rcx, [rsp+4E0h+pszPath]; lpFileName
0x180004e61  call    cs:__imp_DeleteFileW
0x180004e68  nop     dword ptr [rax+rax+00h]
0x180004e6d  mov     rcx, [rsp+4E0h+ppv]
0x180004e72  mov     rax, [rcx]
0x180004e75  mov     rax, [rax+10h]
0x180004e79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e7e  mov     rcx, [rsp+4E0h+StringSid]; hMem
0x180004e83  call    cs:__imp_LocalFree
0x180004e8a  nop     dword ptr [rax+rax+00h]
0x180004e8f  mov     eax, ebx
0x180004e91  mov     rcx, [rbp+3E0h+var_50]
0x180004e98  xor     rcx, rsp; StackCookie
0x180004e9b  call    __security_check_cookie
0x180004ea0  add     rsp, 4A8h
0x180004ea7  pop     r15
0x180004ea9  pop     r14
0x180004eab  pop     r13
0x180004ead  pop     r12
0x180004eaf  pop     rdi
0x180004eb0  pop     rsi
0x180004eb1  pop     rbx
0x180004eb2  pop     rbp
0x180004eb3  retn
```
