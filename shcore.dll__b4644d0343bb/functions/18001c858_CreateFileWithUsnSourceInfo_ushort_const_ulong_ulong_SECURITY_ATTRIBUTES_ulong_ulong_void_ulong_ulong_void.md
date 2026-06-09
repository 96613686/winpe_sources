# CreateFileWithUsnSourceInfo(ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *,ulong,ulong,void * *)

- ea: `0x18001c858`
- end: `0x18001cb39`
- name: `?CreateFileWithUsnSourceInfo@@YAJPEBGKKPEAU_SECURITY_ATTRIBUTES@@KKPEAXKKPEAPEAX@Z`
- size: `737`
- prototype: `__int64 __usercall@<rax>(wchar_t *Str@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, struct _SECURITY_ATTRIBUTES *@<r9>, unsigned int, DWORD, void *, unsigned int, unsigned int, void **)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x18001c3b0`
- `0x18001c61c`
- `0x180088764`

## callees

- `0x1800137a8`
- `0x18001c858`
- `0x180023730`
- `0x180045e88`
- `0x18004ab14`
- `0x180066910`
- `0x1800886d4`
- `0x180088764`
- `0x180088d24`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c8d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c9c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c8d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c9c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cb2e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cb2e`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18001c9ba`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18001c9ba`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001c8c3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001ca3a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001caee`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001c8c3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001ca3a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001caee`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CreateFileWithUsnSourceInfo(
        wchar_t *Str,
        DWORD a2,
        DWORD a3,
        struct _SECURITY_ATTRIBUTES *a4,
        signed int a5,
        DWORD dwFlagsAndAttributes,
        void *a7,
        char a8,
        unsigned int a9,
        void **a10)
{
  unsigned int v11; // r13d
  char *FileW; // rdi
  int v13; // ebx
  unsigned int v14; // r8d
  int v15; // esi
  __int64 v16; // rax
  unsigned __int64 v17; // rax
  char *v18; // rax
  BOOL v20; // eax
  signed int LastError; // eax
  HANDLE v22; // rax
  unsigned int v23; // r8d
  unsigned int v24; // r8d
  HANDLE v25; // rax
  unsigned int v26; // r8d
  void *v29; // [rsp+50h] [rbp-49h] BYREF
  unsigned __int16 *v30; // [rsp+58h] [rbp-41h]
  void **v31; // [rsp+60h] [rbp-39h]
  __int128 FileInformation; // [rsp+68h] [rbp-31h] BYREF
  __int128 v33; // [rsp+78h] [rbp-21h]
  __int64 v34; // [rsp+88h] [rbp-11h]

  v31 = a10;
  *a10 = (void *)-1LL;
  v11 = a5 & 0x7FFFFFFF;
  FileW = (char *)CreateFileW(Str, a2, a3, 0, a5 & 0x7FFFFFFF, dwFlagsAndAttributes, 0);
  v29 = FileW;
  if ( FileW == (char *)-1LL )
  {
    LastError = GetLastError();
    v13 = LastError;
    if ( LastError > 0 )
      v13 = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    v13 = (unsigned __int16)GetLastError() | 0x70000;
  }
  v15 = v13;
  if ( v13 != -2147022976 )
  {
LABEL_4:
    if ( v13 == -2147024891 )
    {
      if ( (a8 & 1) == 0 )
        goto LABEL_12;
      FileInformation = 0u;
      *(_QWORD *)&v33 = 0;
      v30 = 0;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&FileInformation);
      *((_QWORD *)&FileInformation + 1) = -1;
      *(_QWORD *)&v33 = -1;
      if ( (int)anonymous_namespace_::_GetPrimaryStreamPath(Str) >= 0
        && SetFileAttributesWithUsnSourceInfo(v30, 0, v24, a9) >= 0 )
      {
        v25 = CreateFileW(Str, a2, a3, 0, a5 & 0x7FFFFFFF, dwFlagsAndAttributes, 0);
        v13 = SuccessResultFromWin32Handle(v25, &v29);
        v15 = v13;
        SetFileAttributesWithUsnSourceInfo(v30, 1u, v26, a9);
        FileW = (char *)v29;
      }
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&FileInformation);
    }
    goto LABEL_5;
  }
  if ( (dwFlagsAndAttributes & 0x200000) != 0 )
    goto LABEL_5;
  if ( v11 == 1 )
  {
    v13 = -2147024816;
    goto LABEL_5;
  }
  if ( v11 == 2 || v11 == 5 )
  {
    if ( SetPlaceholderReparsePointAndAttributes(Str, 0, v14) >= 0 )
    {
      v22 = CreateFileW(Str, a2, a3, 0, a5 & 0x7FFFFFFF, dwFlagsAndAttributes, 0);
      v15 = SuccessResultFromWin32Handle(v22, &v29);
      if ( v15 < 0 )
        SetPlaceholderReparsePointAndAttributes(Str, 1, v23);
      FileW = (char *)v29;
    }
    v13 = v15;
    goto LABEL_4;
  }
LABEL_5:
  if ( v13 >= 0 )
  {
    FileInformation = 0;
    v33 = 0;
    v34 = 0;
    v16 = 0;
    if ( (a8 & 2) != 0 )
      v16 = -1;
    *(_QWORD *)&v33 = v16;
    v17 = _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
    if ( (a8 & 4) != 0 )
      v17 = -1;
    *((_QWORD *)&FileInformation + 1) = v17;
    if ( (a8 & 6) != 0 && (int)SetUsnSourceInfo(FileW, a9) >= 0 )
    {
      v20 = SetFileInformationByHandle(FileW, FileBasicInfo, &FileInformation, 0x28u);
      ResultFromWin32Bool(v20);
    }
    v18 = FileW;
    FileW = 0;
    *v31 = v18;
  }
LABEL_12:
  if ( v15 >= 0 )
    v15 = a5 < 0 ? v15 : 0;
  if ( v13 >= 0 )
    v13 = v15;
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(FileW);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18001c858  push    rbp
0x18001c85a  push    rbx
0x18001c85b  push    rsi
0x18001c85c  push    rdi
0x18001c85d  push    r13
0x18001c85f  push    r14
0x18001c861  push    r15
0x18001c863  lea     rbp, [rsp-7]
0x18001c868  sub     rsp, 0A0h
0x18001c86f  mov     rax, cs:__security_cookie
0x18001c876  xor     rax, rsp
0x18001c879  mov     [rbp+37h+var_40], rax
0x18001c87d  mov     [rbp+37h+dwShareMode], r8d
0x18001c881  mov     [rbp+37h+dwDesiredAccess], edx
0x18001c884  mov     r15, rcx
0x18001c887  mov     r14d, [rbp+37h+arg_20]
0x18001c88b  mov     eax, [rbp+37h+arg_28]
0x18001c88e  mov     [rbp+37h+var_90], eax
0x18001c891  mov     rcx, [rbp+37h+arg_48]
0x18001c898  mov     [rbp+37h+var_70], rcx
0x18001c89c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001c8a0  mov     [rcx], rbx
0x18001c8a3  mov     r13d, r14d
0x18001c8a6  btr     r13d, 1Fh
0x18001c8ab  mov     [rsp+0D0h+hTemplateFile], 0; hTemplateFile
0x18001c8b4  mov     [rsp+0D0h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x18001c8b8  mov     [rsp+0D0h+dwCreationDisposition], r13d; dwCreationDisposition
0x18001c8bd  xor     r9d, r9d; lpSecurityAttributes
0x18001c8c0  mov     rcx, r15; lpFileName
0x18001c8c3  call    cs:__imp_CreateFileW
0x18001c8c9  mov     rdi, rax
0x18001c8cc  mov     [rbp+37h+var_80], rax
0x18001c8d0  cmp     rax, rbx
0x18001c8d3  jz      loc_18001C9C9
0x18001c8d9  call    cs:__imp_GetLastError
0x18001c8df  movzx   ebx, ax
0x18001c8e2  or      ebx, 70000h
0x18001c8e8  mov     esi, ebx
0x18001c8ea  cmp     ebx, 80070780h
0x18001c8f0  jz      loc_18001C9E7
0x18001c8f6  cmp     ebx, 80070005h
0x18001c8fc  jz      loc_18001CA71
0x18001c902  test    ebx, ebx
0x18001c904  js      short loc_18001C957
0x18001c906  xorps   xmm0, xmm0
0x18001c909  xor     eax, eax
0x18001c90b  movups  [rbp+37h+FileInformation], xmm0
0x18001c90f  movups  [rbp+37h+var_58], xmm0
0x18001c913  mov     [rbp+37h+var_48], rax
0x18001c917  test    [rbp+37h+arg_38], 2
0x18001c91b  movq    rax, xmm0
0x18001c920  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001c927  cmovnz  rax, rcx
0x18001c92b  mov     qword ptr [rbp+37h+var_58], rax
0x18001c92f  test    [rbp+37h+arg_38], 4
0x18001c933  psrldq  xmm0, 8
0x18001c938  movq    rax, xmm0
0x18001c93d  cmovnz  rax, rcx
0x18001c941  mov     qword ptr [rbp+37h+FileInformation+8], rax
0x18001c945  test    [rbp+37h+arg_38], 6
0x18001c949  jnz     short loc_18001C999
0x18001c94b  mov     rax, rdi
0x18001c94e  xor     edi, edi
0x18001c950  mov     rcx, [rbp+37h+var_70]
0x18001c954  mov     [rcx], rax
0x18001c957  test    esi, esi
0x18001c959  js      short loc_18001C966
0x18001c95b  shr     r14d, 1Fh
0x18001c95f  neg     r14b
0x18001c962  sbb     eax, eax
0x18001c964  and     esi, eax
0x18001c966  test    ebx, ebx
0x18001c968  cmovns  ebx, esi
0x18001c96b  lea     rdx, [rdi-1]
0x18001c96f  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18001c973  jbe     loc_18001CB2B
0x18001c979  mov     eax, ebx
0x18001c97b  mov     rcx, [rbp+37h+var_40]
0x18001c97f  xor     rcx, rsp; StackCookie
0x18001c982  call    __security_check_cookie
0x18001c987  add     rsp, 0A0h
0x18001c98e  pop     r15
0x18001c990  pop     r14
0x18001c992  pop     r13
0x18001c994  pop     rdi
0x18001c995  pop     rsi
0x18001c996  pop     rbx
0x18001c997  pop     rbp
0x18001c998  retn
0x18001c999  mov     edx, [rbp+37h+arg_40]; unsigned int
0x18001c99f  mov     rcx, rdi; void *
0x18001c9a2  call    ?SetUsnSourceInfo@@YAJPEAXK@Z; SetUsnSourceInfo(void *,ulong)
0x18001c9a7  test    eax, eax
0x18001c9a9  js      short loc_18001C94B
0x18001c9ab  mov     r9d, 28h ; '('; dwBufferSize
0x18001c9b1  lea     r8, [rbp+37h+FileInformation]; lpFileInformation
0x18001c9b5  xor     edx, edx; FileInformationClass
0x18001c9b7  mov     rcx, rdi; hFile
0x18001c9ba  call    cs:__imp_SetFileInformationByHandle
0x18001c9c0  mov     ecx, eax; int
0x18001c9c2  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x18001c9c7  jmp     short loc_18001C94B
0x18001c9c9  call    cs:__imp_GetLastError
0x18001c9cf  mov     ebx, eax
0x18001c9d1  test    eax, eax
0x18001c9d3  jle     loc_18001C8E8
0x18001c9d9  movzx   ebx, ax
0x18001c9dc  or      ebx, 80070000h
0x18001c9e2  jmp     loc_18001C8E8
0x18001c9e7  test    [rbp+37h+var_90], 200000h
0x18001c9ee  jnz     loc_18001C902
0x18001c9f4  mov     eax, r13d
0x18001c9f7  sub     eax, 1
0x18001c9fa  jz      short loc_18001CA67
0x18001c9fc  sub     eax, 1
0x18001c9ff  jz      short loc_18001CA0A
0x18001ca01  cmp     eax, 3
0x18001ca04  jnz     loc_18001C902
0x18001ca0a  xor     edx, edx; bool
0x18001ca0c  mov     rcx, r15; unsigned __int16 *
0x18001ca0f  call    ?SetPlaceholderReparsePointAndAttributes@@YAJPEBG_NK@Z; SetPlaceholderReparsePointAndAttributes(ushort const *,bool,ulong)
0x18001ca14  test    eax, eax
0x18001ca16  js      short loc_18001CA60
0x18001ca18  mov     [rsp+0D0h+hTemplateFile], 0; hTemplateFile
0x18001ca21  mov     eax, [rbp+37h+var_90]
0x18001ca24  mov     [rsp+0D0h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x18001ca28  mov     [rsp+0D0h+dwCreationDisposition], r13d; dwCreationDisposition
0x18001ca2d  xor     r9d, r9d; lpSecurityAttributes
0x18001ca30  mov     r8d, [rbp+37h+dwShareMode]; dwShareMode
0x18001ca34  mov     edx, [rbp+37h+dwDesiredAccess]; dwDesiredAccess
0x18001ca37  mov     rcx, r15; lpFileName
0x18001ca3a  call    cs:__imp_CreateFileW
0x18001ca40  lea     rdx, [rbp+37h+var_80]; void **
0x18001ca44  mov     rcx, rax; void *
0x18001ca47  call    ?SuccessResultFromWin32Handle@@YAJPEAXPEAPEAX@Z; SuccessResultFromWin32Handle(void *,void * *)
0x18001ca4c  mov     esi, eax
0x18001ca4e  test    eax, eax
0x18001ca50  jns     short loc_18001CA5C
0x18001ca52  mov     dl, 1; bool
0x18001ca54  mov     rcx, r15; unsigned __int16 *
0x18001ca57  call    ?SetPlaceholderReparsePointAndAttributes@@YAJPEBG_NK@Z; SetPlaceholderReparsePointAndAttributes(ushort const *,bool,ulong)
0x18001ca5c  mov     rdi, [rbp+37h+var_80]
0x18001ca60  mov     ebx, esi
0x18001ca62  jmp     loc_18001C8F6
0x18001ca67  mov     ebx, 80070050h
0x18001ca6c  jmp     loc_18001C902
0x18001ca71  test    [rbp+37h+arg_38], 1
0x18001ca75  jz      loc_18001C957
0x18001ca7b  xor     eax, eax
0x18001ca7d  mov     qword ptr [rbp+37h+FileInformation], rax
0x18001ca81  mov     qword ptr [rbp+37h+FileInformation+8], rax
0x18001ca85  mov     qword ptr [rbp+37h+var_58], rax
0x18001ca89  mov     [rbp+37h+var_78], rax
0x18001ca8d  lea     rcx, [rbp+37h+FileInformation]
0x18001ca91  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001ca96  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001ca9a  mov     qword ptr [rbp+37h+FileInformation+8], rax
0x18001ca9e  mov     qword ptr [rbp+37h+var_58], rax
0x18001caa2  lea     r8, [rbp+37h+var_78]
0x18001caa6  lea     rdx, [rbp+37h+FileInformation]
0x18001caaa  mov     rcx, r15; Str
0x18001caad  call    _anonymous_namespace____GetPrimaryStreamPath
0x18001cab2  test    eax, eax
0x18001cab4  js      short loc_18001CB1D
0x18001cab6  mov     r9d, [rbp+37h+arg_40]; unsigned int
0x18001cabd  xor     edx, edx; unsigned int
0x18001cabf  mov     rcx, [rbp+37h+var_78]; unsigned __int16 *
0x18001cac3  call    ?SetFileAttributesWithUsnSourceInfo@@YAJPEBGKKK@Z; SetFileAttributesWithUsnSourceInfo(ushort const *,ulong,ulong,ulong)
0x18001cac8  test    eax, eax
0x18001caca  js      short loc_18001CB1D
0x18001cacc  mov     [rsp+0D0h+hTemplateFile], 0; hTemplateFile
0x18001cad5  mov     eax, [rbp+37h+var_90]
0x18001cad8  mov     [rsp+0D0h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x18001cadc  mov     [rsp+0D0h+dwCreationDisposition], r13d; dwCreationDisposition
0x18001cae1  xor     r9d, r9d; lpSecurityAttributes
0x18001cae4  mov     r8d, [rbp+37h+dwShareMode]; dwShareMode
0x18001cae8  mov     edx, [rbp+37h+dwDesiredAccess]; dwDesiredAccess
0x18001caeb  mov     rcx, r15; lpFileName
0x18001caee  call    cs:__imp_CreateFileW
0x18001caf4  lea     rdx, [rbp+37h+var_80]; void **
0x18001caf8  mov     rcx, rax; void *
0x18001cafb  call    ?SuccessResultFromWin32Handle@@YAJPEAXPEAPEAX@Z; SuccessResultFromWin32Handle(void *,void * *)
0x18001cb00  mov     ebx, eax
0x18001cb02  mov     esi, eax
0x18001cb04  mov     r9d, [rbp+37h+arg_40]; unsigned int
0x18001cb0b  mov     edx, 1; unsigned int
0x18001cb10  mov     rcx, [rbp+37h+var_78]; unsigned __int16 *
0x18001cb14  call    ?SetFileAttributesWithUsnSourceInfo@@YAJPEBGKKK@Z; SetFileAttributesWithUsnSourceInfo(ushort const *,ulong,ulong,ulong)
0x18001cb19  mov     rdi, [rbp+37h+var_80]
0x18001cb1d  lea     rcx, [rbp+37h+FileInformation]
0x18001cb21  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001cb26  jmp     loc_18001C902
0x18001cb2b  mov     rcx, rdi; hObject
0x18001cb2e  call    cs:__imp_CloseHandle
0x18001cb34  jmp     loc_18001C979
```
