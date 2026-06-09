# CTreeWalker::GetFolderPath(void *,__int64,ulong *,ushort *,_LARGE_INTEGER *,ulong)

- ea: `0x1800450e0`
- end: `0x180045408`
- name: `?GetFolderPath@CTreeWalker@@AEAAJPEAX_JPEAKPEAGPEAT_LARGE_INTEGER@@K@Z`
- size: `808`
- prototype: `int(CTreeWalker *__hidden this, void *, __int64, unsigned int *, unsigned __int16 *, union _LARGE_INTEGER *, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation`

## callers

- `0x18004545c`
- `0x18004ad10`
- `0x18004c754`

## callees

- `0x18000d030`
- `0x18000ddb0`
- `0x18001c130`
- `0x1800450e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18004531e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18004531e`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180045290`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180045290`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004519a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800451d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004519a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800451d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800453d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800453d6`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180045234`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180045234`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180045369`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180045369`
- `api-ms-win-core-file-l2-1-1!OpenFileById` at `0x180045185`
- `api-ms-win-core-file-l2-1-1!OpenFileById` at `0x180045185`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x1800451c8`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180045392`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x1800451c8`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180045392`
- `RPCRT4!RpcRevertToSelf` at `0x18004518e`
- `RPCRT4!RpcRevertToSelf` at `0x180045372`
- `RPCRT4!RpcRevertToSelf` at `0x18004518e`
- `RPCRT4!RpcRevertToSelf` at `0x180045372`
- `RPCRT4!RpcImpersonateClient` at `0x180045162`
- `RPCRT4!RpcImpersonateClient` at `0x180045340`
- `RPCRT4!RpcImpersonateClient` at `0x180045162`
- `RPCRT4!RpcImpersonateClient` at `0x180045340`

## pseudocode

```c
__int64 __fastcall CTreeWalker::GetFolderPath(
        CTreeWalker *this,
        void *a2,
        unsigned __int64 a3,
        unsigned int *a4,
        unsigned __int16 *lpszFilePath,
        union _LARGE_INTEGER *a6)
{
  HANDLE FileW; // rsi
  signed int LastError; // eax
  unsigned int v12; // ebx
  signed int v13; // eax
  unsigned int v14; // edx
  _QWORD *v15; // r8
  _QWORD *v16; // rcx
  __int64 **v17; // rdx
  __int64 i; // rax
  __int64 *j; // rdx
  __int64 v20; // rax
  unsigned int v21; // eax
  FILE_ID_DESCRIPTOR FileId; // [rsp+40h] [rbp-C0h] BYREF
  __int128 FileInformation; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v25; // [rsp+68h] [rbp-98h]
  __int64 v26; // [rsp+78h] [rbp-88h]
  wchar_t SubStr; // [rsp+80h] [rbp-80h] BYREF
  __int128 v28; // [rsp+82h] [rbp-7Eh]
  __int128 v29; // [rsp+92h] [rbp-6Eh]
  __int128 v30; // [rsp+A2h] [rbp-5Eh]
  __int64 v31; // [rsp+B2h] [rbp-4Eh]
  _BYTE v32[470]; // [rsp+BAh] [rbp-46h] BYREF

  v26 = 0;
  FileInformation = 0;
  v25 = 0;
  if ( *((_BYTE *)this + 314) )
  {
    *(_QWORD *)&FileId.dwSize = 24;
    FileId.8 = (union FILE_ID_DESCRIPTOR::$937871D590D7CF78B637FB7A33219D36)a3;
    RpcImpersonateClient(0);
    FileW = OpenFileById(a2, &FileId, 0x80u, 3u, 0, 0x2000000u);
    RpcRevertToSelf();
    if ( FileW == (HANDLE)-1LL )
    {
LABEL_3:
      LastError = GetLastError();
      v12 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
      return v12;
    }
    if ( !GetFileInformationByHandleEx(FileW, FileBasicInfo, &FileInformation, 0x28u) )
      goto LABEL_6;
    v14 = v26;
    if ( a3 != 0x5000000000005LL && ((v26 & 2) != 0 || (v26 & 4) != 0) )
    {
LABEL_11:
      v12 = -2147024891;
    }
    else
    {
      *a6 = *(union _LARGE_INTEGER *)((char *)&v25 + 8);
      *a4 = v14;
      if ( !GetFinalPathNameByHandleW(FileW, lpszFilePath, 0x104u, 0) )
      {
LABEL_6:
        v13 = GetLastError();
        v12 = v13;
        if ( v13 > 0 )
          v12 = (unsigned __int16)v13 | 0x80070000;
        goto LABEL_36;
      }
      v28 = *(_OWORD *)L":\\System Volume Information";
      v29 = *(_OWORD *)L" Volume Information";
      v30 = *(_OWORD *)L"Information";
      v31 = *(_QWORD *)L"ion";
      memset_0(v32, 0, 0x1CEu);
      SubStr = *((_WORD *)this + 164);
      v12 = wcsstr(lpszFilePath, &SubStr) != 0 ? 0x80070005 : 0;
    }
LABEL_36:
    CloseHandle(FileW);
    return v12;
  }
  v15 = (_QWORD *)*((_QWORD *)this + 33);
  v12 = -2147023728;
  v16 = (_QWORD *)*v15;
  while ( v16 != v15 )
  {
    if ( v16[8] == a3 )
    {
      v20 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v16 + 4);
      _o_wcscpy_s(lpszFilePath, 260, v20);
      if ( *lpszFilePath == 92 && lpszFilePath[1] == 92 && lpszFilePath[2] == 46 )
        lpszFilePath[2] = 63;
      RpcImpersonateClient(0);
      FileW = CreateFileW(lpszFilePath, 0x80000000, 3u, 0, 3u, 0x2000080u, 0);
      RpcRevertToSelf();
      if ( FileW == (HANDLE)-1LL )
        goto LABEL_3;
      if ( !GetFileInformationByHandleEx(FileW, FileBasicInfo, &FileInformation, 0x28u) )
        goto LABEL_6;
      v21 = v26;
      if ( a3 == 0x5000000000005LL || (v26 & 2) == 0 && (v26 & 4) == 0 )
      {
        v12 = 0;
        a6->QuadPart = v25;
        *a4 = v21;
        goto LABEL_36;
      }
      goto LABEL_11;
    }
    v17 = (__int64 **)v16[2];
    if ( *((_BYTE *)v17 + 25) )
    {
      for ( i = v16[1]; !*(_BYTE *)(i + 25) && v16 == *(_QWORD **)(i + 16); i = *(_QWORD *)(i + 8) )
        v16 = (_QWORD *)i;
      v16 = (_QWORD *)i;
    }
    else
    {
      v16 = (_QWORD *)v16[2];
      for ( j = *v17; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v16 = j;
    }
  }
  return v12;
}

```

## disassembly

```asm
0x1800450e0  mov     [rsp-8+arg_0], rbx
0x1800450e5  push    rbp
0x1800450e6  push    rsi
0x1800450e7  push    rdi
0x1800450e8  push    r12
0x1800450ea  push    r13
0x1800450ec  push    r14
0x1800450ee  push    r15
0x1800450f0  lea     rbp, [rsp-1A0h]
0x1800450f8  sub     rsp, 2A0h
0x1800450ff  mov     rax, cs:__security_cookie
0x180045106  xor     rax, rsp
0x180045109  mov     [rbp+1D0h+var_40], rax
0x180045110  mov     rdi, [rbp+1D0h+lpszFilePath]
0x180045117  xor     eax, eax
0x180045119  mov     r13, [rbp+1D0h+arg_28]
0x180045120  xorps   xmm0, xmm0
0x180045123  xor     esi, esi
0x180045125  mov     [rsp+2D0h+var_258], rax
0x18004512a  mov     r12, r9
0x18004512d  mov     r14, r8
0x180045130  mov     rbx, rdx
0x180045133  mov     r15, rcx
0x180045136  movups  [rsp+2D0h+FileInformation], xmm0
0x18004513b  movups  [rsp+2D0h+var_268], xmm0
0x180045140  cmp     [rcx+13Ah], sil
0x180045147  jz      loc_1800452A7
0x18004514d  xor     ecx, ecx; BindingHandle
0x18004514f  mov     qword ptr [rsp+2D0h+FileId.8+8], rsi
0x180045154  mov     qword ptr [rsp+2D0h+FileId.dwSize], 18h
0x18004515d  mov     qword ptr [rsp+2D0h+FileId.8], r8
0x180045162  call    cs:__imp_RpcImpersonateClient
0x180045168  lea     r9d, [rsi+3]; dwShareMode
0x18004516c  mov     [rsp+2D0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x180045174  lea     rdx, [rsp+2D0h+FileId]; lpFileId
0x180045179  mov     [rsp+2D0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18004517e  mov     rcx, rbx; hVolumeHint
0x180045181  lea     r8d, [r9+7Dh]; dwDesiredAccess
0x180045185  call    cs:__imp_OpenFileById
0x18004518b  mov     rsi, rax
0x18004518e  call    cs:__imp_RpcRevertToSelf
0x180045194  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180045198  jnz     short loc_1800451B8
0x18004519a  call    cs:__imp_GetLastError
0x1800451a0  mov     ebx, eax
0x1800451a2  test    eax, eax
0x1800451a4  jle     loc_1800453DC
0x1800451aa  movzx   ebx, ax
0x1800451ad  or      ebx, 80070000h
0x1800451b3  jmp     loc_1800453DC
0x1800451b8  mov     r9d, 28h ; '('; dwBufferSize
0x1800451be  lea     r8, [rsp+2D0h+FileInformation]; lpFileInformation
0x1800451c3  xor     edx, edx; FileInformationClass
0x1800451c5  mov     rcx, rsi; hFile
0x1800451c8  call    cs:__imp_GetFileInformationByHandleEx
0x1800451ce  test    eax, eax
0x1800451d0  jnz     short loc_1800451F0
0x1800451d2  call    cs:__imp_GetLastError
0x1800451d8  mov     ebx, eax
0x1800451da  test    eax, eax
0x1800451dc  jle     loc_1800453D3
0x1800451e2  movzx   ebx, ax
0x1800451e5  or      ebx, 80070000h
0x1800451eb  jmp     loc_1800453D3
0x1800451f0  mov     rdx, [rsp+2D0h+var_258]
0x1800451f5  mov     rcx, 5000000000005h
0x1800451ff  cmp     r14, rcx
0x180045202  jz      short loc_180045218
0x180045204  test    dl, 2
0x180045207  jnz     short loc_18004520E
0x180045209  test    dl, 4
0x18004520c  jz      short loc_180045218
0x18004520e  mov     ebx, 80070005h
0x180045213  jmp     loc_1800453D3
0x180045218  mov     rax, qword ptr [rsp+2D0h+var_268+8]
0x18004521d  xor     r9d, r9d; dwFlags
0x180045220  mov     [r13+0], rax
0x180045224  mov     r8d, 104h; cchFilePath
0x18004522a  mov     [r12], edx
0x18004522e  mov     rcx, rsi; hFile
0x180045231  mov     rdx, rdi; lpszFilePath
0x180045234  call    cs:__imp_GetFinalPathNameByHandleW
0x18004523a  test    eax, eax
0x18004523c  jz      short loc_1800451D2
0x18004523e  movups  xmm0, xmmword ptr cs:aSystemVolumeIn_1+2; ":\\System Volume Information"
0x180045245  xor     edx, edx; Val
0x180045247  mov     r8d, 1CEh; Size
0x18004524d  movups  xmm1, xmmword ptr cs:aSystemVolumeIn_1+12h; " Volume Information"
0x180045254  lea     rcx, [rbp+1D0h+var_216]; void *
0x180045258  movups  [rbp+1D0h+var_24E], xmm0
0x18004525c  movups  xmm0, xmmword ptr cs:aSystemVolumeIn_1+22h; "Information"
0x180045263  movups  [rbp+1D0h+var_23E], xmm1
0x180045267  movsd   xmm1, qword ptr cs:aSystemVolumeIn_1+32h; "ion"
0x18004526f  movups  [rbp+1D0h+var_22E], xmm0
0x180045273  movsd   [rbp+1D0h+var_21E], xmm1
0x180045278  call    memset_0
0x18004527d  movzx   eax, word ptr [r15+148h]
0x180045285  lea     rdx, [rbp+1D0h+SubStr]; SubStr
0x180045289  mov     rcx, rdi; Str
0x18004528c  mov     [rbp+1D0h+SubStr], ax
0x180045290  call    cs:__imp_wcsstr
0x180045296  neg     rax
0x180045299  mov     ebx, 80070005h
0x18004529e  sbb     ecx, ecx
0x1800452a0  and     ebx, ecx
0x1800452a2  jmp     loc_1800453D3
0x1800452a7  mov     r8, [rcx+108h]
0x1800452ae  mov     ebx, 80070490h
0x1800452b3  mov     rcx, [r8]
0x1800452b6  cmp     rcx, r8
0x1800452b9  jz      loc_1800453DC
0x1800452bf  cmp     [rcx+40h], r14
0x1800452c3  jz      short loc_18004530A
0x1800452c5  mov     rdx, [rcx+10h]
0x1800452c9  cmp     [rdx+19h], sil
0x1800452cd  jz      short loc_1800452ED
0x1800452cf  mov     rax, [rcx+8]
0x1800452d3  jmp     short loc_1800452E2
0x1800452d5  cmp     rcx, [rax+10h]
0x1800452d9  jnz     short loc_1800452E8
0x1800452db  mov     rcx, rax
0x1800452de  mov     rax, [rax+8]
0x1800452e2  cmp     [rax+19h], sil
0x1800452e6  jz      short loc_1800452D5
0x1800452e8  mov     rcx, rax
0x1800452eb  jmp     short loc_1800452B6
0x1800452ed  mov     rcx, rdx
0x1800452f0  mov     rdx, [rdx]
0x1800452f3  cmp     [rdx+19h], sil
0x1800452f7  jnz     short loc_1800452B6
0x1800452f9  mov     rax, [rdx]
0x1800452fc  mov     rcx, rdx
0x1800452ff  mov     rdx, rax
0x180045302  cmp     [rax+19h], sil
0x180045306  jz      short loc_1800452F9
0x180045308  jmp     short loc_1800452B6
0x18004530a  add     rcx, 20h ; ' '
0x18004530e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180045313  mov     r8, rax
0x180045316  mov     rcx, rdi
0x180045319  mov     edx, 104h
0x18004531e  call    cs:__imp__o_wcscpy_s
0x180045324  cmp     word ptr [rdi], 5Ch ; '\'
0x180045328  jnz     short loc_18004533E
0x18004532a  cmp     word ptr [rdi+2], 5Ch ; '\'
0x18004532f  jnz     short loc_18004533E
0x180045331  cmp     word ptr [rdi+4], 2Eh ; '.'
0x180045336  jnz     short loc_18004533E
0x180045338  mov     word ptr [rdi+4], 3Fh ; '?'
0x18004533e  xor     ecx, ecx; BindingHandle
0x180045340  call    cs:__imp_RpcImpersonateClient
0x180045346  mov     r8d, 3; dwShareMode
0x18004534c  mov     [rsp+2D0h+hTemplateFile], rsi; hTemplateFile
0x180045351  mov     [rsp+2D0h+dwFlagsAndAttributes], 2000080h; dwFlagsAndAttributes
0x180045359  xor     r9d, r9d; lpSecurityAttributes
0x18004535c  mov     edx, 80000000h; dwDesiredAccess
0x180045361  mov     dword ptr [rsp+2D0h+lpSecurityAttributes], r8d; dwCreationDisposition
0x180045366  mov     rcx, rdi; lpFileName
0x180045369  call    cs:__imp_CreateFileW
0x18004536f  mov     rsi, rax
0x180045372  call    cs:__imp_RpcRevertToSelf
0x180045378  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18004537c  jz      loc_18004519A
0x180045382  mov     r9d, 28h ; '('; dwBufferSize
0x180045388  lea     r8, [rsp+2D0h+FileInformation]; lpFileInformation
0x18004538d  xor     edx, edx; FileInformationClass
0x18004538f  mov     rcx, rsi; hFile
0x180045392  call    cs:__imp_GetFileInformationByHandleEx
0x180045398  test    eax, eax
0x18004539a  jz      loc_1800451D2
0x1800453a0  mov     rax, [rsp+2D0h+var_258]
0x1800453a5  mov     rcx, 5000000000005h
0x1800453af  cmp     r14, rcx
0x1800453b2  jz      short loc_1800453C4
0x1800453b4  test    al, 2
0x1800453b6  jnz     loc_18004520E
0x1800453bc  test    al, 4
0x1800453be  jnz     loc_18004520E
0x1800453c4  mov     rcx, qword ptr [rsp+2D0h+var_268]
0x1800453c9  xor     ebx, ebx
0x1800453cb  mov     [r13+0], rcx
0x1800453cf  mov     [r12], eax
0x1800453d3  mov     rcx, rsi; hObject
0x1800453d6  call    cs:__imp_CloseHandle
0x1800453dc  mov     eax, ebx
0x1800453de  mov     rcx, [rbp+1D0h+var_40]
0x1800453e5  xor     rcx, rsp; StackCookie
0x1800453e8  call    __security_check_cookie
0x1800453ed  mov     rbx, [rsp+2D0h+arg_0]
0x1800453f5  add     rsp, 2A0h
0x1800453fc  pop     r15
0x1800453fe  pop     r14
0x180045400  pop     r13
0x180045402  pop     r12
0x180045404  pop     rdi
0x180045405  pop     rsi
0x180045406  pop     rbp
0x180045407  retn
```
