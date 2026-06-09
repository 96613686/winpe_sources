# pAddClientUnattendToReply(_IMG_SERVER_CONTEXT *,void *,ushort *)

- ea: `0x180007880`
- end: `0x180007b11`
- name: `?pAddClientUnattendToReply@@YAKPEAU_IMG_SERVER_CONTEXT@@PEAXPEAG@Z`
- size: `657`
- prototype: `__int64 __fastcall(const unsigned __int16 **, void *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180002a0c`

## callees

- `0x180006d10`
- `0x180007880`
- `0x180007eb4`
- `0x180015ff9`
- `0x180016020`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x180007a28`
- `KERNEL32!CreateFileW` at `0x180007a28`
- `KERNEL32!GetFileAttributesW` at `0x1800079ee`
- `KERNEL32!GetFileAttributesW` at `0x1800079ee`
- `KERNEL32!GetLastError` at `0x180007abb`
- `KERNEL32!GetLastError` at `0x180007ada`
- `KERNEL32!GetLastError` at `0x180007abb`
- `KERNEL32!GetLastError` at `0x180007ada`
- `KERNEL32!CloseHandle` at `0x180007acc`
- `KERNEL32!CloseHandle` at `0x180007acc`
- `KERNEL32!GetFileSizeEx` at `0x180007a49`
- `KERNEL32!GetFileSizeEx` at `0x180007a49`
- `KERNEL32!ReadFile` at `0x180007a9c`
- `KERNEL32!ReadFile` at `0x180007a9c`
- `WDSCSL!WdsCpParameterAdd` at `0x180007a76`
- `WDSCSL!WdsCpParameterAdd` at `0x180007a76`
- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x180007902`
- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x180007902`

## pseudocode

```c
__int64 __fastcall pAddClientUnattendToReply(const unsigned __int16 **a1, void *a2, unsigned __int16 *a3)
{
  const unsigned __int16 *v6; // r8
  unsigned int v7; // esi
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v11; // r9
  __int64 v12; // r8
  __int64 v13; // rax
  int v14; // eax
  struct _TEB *v15; // rcx
  HANDLE FileW; // rax
  void *v17; // rdi
  DWORD LastError; // ebx
  void *v19; // rax
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-C0h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR FileName[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v24[524]; // [rsp+54h] [rbp-ACh] BYREF

  *(_DWORD *)FileName = 0;
  memset_0(v24, 0, 0x204u);
  v6 = *a1;
  FileSize.QuadPart = 0;
  NumberOfBytesRead = 0;
  v7 = StringCchCopyW(FileName, 0x104u, v6);
  if ( (int)ElValidateHr(v7, v8, v9, 561) < 0 )
    return WIN32_FROM_HRESULT(v7);
  v11 = 0;
  if ( a3 )
  {
    v12 = -1;
    do
      ++v12;
    while ( FileName[v12] );
    v13 = -1;
    do
      ++v13;
    while ( a3[v13] );
    if ( !v12 || *((_WORD *)&FileSize.QuadPart + v12 + 3) == 92 )
    {
      if ( *a3 == 92 )
      {
        ++a3;
        --v13;
      }
    }
    else if ( *a3 != 92 )
    {
      v11 = 1;
    }
    if ( (unsigned __int64)(v12 + v11 + v13 + 1) <= 0x104 )
    {
      if ( v11 )
        FileName[v12] = 92;
      v14 = StringCchCopyW(&FileName[v11 + v12], 260 - v11 - v12, a3);
      v15 = NtCurrentTeb();
      if ( v14 >= 0 )
        v15->LastErrorValue = 0;
      else
        v15->LastErrorValue = (unsigned __int16)v14;
    }
    else
    {
      NtCurrentTeb()->LastErrorValue = 122;
    }
  }
  else
  {
    NtCurrentTeb()->LastErrorValue = 87;
  }
  if ( GetFileAttributesW(FileName) == -1 )
    return GetLastError();
  FileW = CreateFileW(FileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v17 = FileW;
  if ( FileW == (HANDLE)-1LL )
    return GetLastError();
  if ( !GetFileSizeEx(FileW, &FileSize) )
    goto LABEL_29;
  LastError = 8;
  v19 = (void *)WdsCpParameterAdd(a2, L"CLIENT_UNATTEND", 64);
  if ( v19 )
  {
    if ( ReadFile(v17, v19, FileSize.LowPart, &NumberOfBytesRead, 0) && NumberOfBytesRead == FileSize.LowPart )
    {
      LastError = 0;
      goto LABEL_30;
    }
LABEL_29:
    LastError = GetLastError();
  }
LABEL_30:
  CloseHandle(v17);
  return LastError;
}

```

## disassembly

```asm
0x180007880  mov     [rsp-8+arg_10], rbx
0x180007885  push    rbp
0x180007886  push    rsi
0x180007887  push    rdi
0x180007888  push    r14
0x18000788a  push    r15
0x18000788c  lea     rbp, [rsp-170h]
0x180007894  sub     rsp, 270h
0x18000789b  mov     rax, cs:__security_cookie
0x1800078a2  xor     rax, rsp
0x1800078a5  mov     [rbp+190h+var_30], rax
0x1800078ac  mov     rdi, r8
0x1800078af  mov     r14, rdx
0x1800078b2  mov     rbx, rcx
0x1800078b5  xor     r15d, r15d
0x1800078b8  xor     edx, edx; Val
0x1800078ba  mov     dword ptr [rsp+290h+FileName], r15d
0x1800078bf  mov     r8d, 204h; Size
0x1800078c5  lea     rcx, [rsp+290h+var_23C]; void *
0x1800078ca  call    memset_0
0x1800078cf  mov     r8, [rbx]; unsigned __int16 *
0x1800078d2  lea     rcx, [rsp+290h+FileName]; unsigned __int16 *
0x1800078d7  mov     ebx, 104h
0x1800078dc  mov     qword ptr [rsp+290h+FileSize], r15
0x1800078e1  mov     edx, ebx; unsigned __int64
0x1800078e3  mov     [rsp+290h+NumberOfBytesRead], r15d
0x1800078e8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800078ed  mov     r9d, 231h
0x1800078f3  mov     ecx, eax
0x1800078f5  mov     esi, eax
0x1800078f7  call    ElValidateHr
0x1800078fc  test    eax, eax
0x1800078fe  jns     short loc_180007913
0x180007900  mov     ecx, esi
0x180007902  call    cs:__imp_?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x180007909  nop     dword ptr [rax+rax+00h]
0x18000790e  jmp     loc_180007AE6
0x180007913  mov     r9, r15
0x180007916  mov     esi, 1
0x18000791b  test    rdi, rdi
0x18000791e  jz      loc_1800079D9
0x180007924  lea     rax, [rsp+290h+FileName]
0x180007929  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000792d  inc     r8
0x180007930  cmp     [rax+r8*2], r15w
0x180007935  jnz     short loc_18000792D
0x180007937  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000793b  inc     rax
0x18000793e  cmp     [rdi+rax*2], r15w
0x180007943  jnz     short loc_18000793B
0x180007945  lea     rdx, [r8+r8]
0x180007949  mov     r10d, 5Ch ; '\'
0x18000794f  test    r8, r8
0x180007952  jz      short loc_180007967
0x180007954  cmp     r10w, word ptr [rsp+rdx+290h+FileSize+6]
0x18000795a  jz      short loc_180007967
0x18000795c  cmp     r10w, [rdi]
0x180007960  jz      short loc_180007974
0x180007962  mov     r9, rsi
0x180007965  jmp     short loc_180007974
0x180007967  cmp     r10w, [rdi]
0x18000796b  jnz     short loc_180007974
0x18000796d  add     rdi, 2
0x180007971  sub     rax, rsi
0x180007974  lea     rcx, [rax+1]
0x180007978  add     rcx, r9
0x18000797b  add     rcx, r8
0x18000797e  cmp     rcx, rbx
0x180007981  jbe     short loc_180007995
0x180007983  mov     rax, gs:30h
0x18000798c  mov     dword ptr [rax+68h], 7Ah ; 'z'
0x180007993  jmp     short loc_1800079E9
0x180007995  test    r9, r9
0x180007998  jz      short loc_1800079A0
0x18000799a  mov     [rsp+rdx+290h+FileName], r10w
0x1800079a0  lea     rax, [r9+r8]
0x1800079a4  sub     rbx, r9
0x1800079a7  sub     rbx, r8
0x1800079aa  lea     rcx, [rsp+290h+FileName]
0x1800079af  mov     rdx, rbx; unsigned __int64
0x1800079b2  lea     rcx, [rcx+rax*2]; unsigned __int16 *
0x1800079b6  mov     r8, rdi; unsigned __int16 *
0x1800079b9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800079be  mov     rcx, gs:30h
0x1800079c7  test    eax, eax
0x1800079c9  jns     short loc_1800079D3
0x1800079cb  movzx   eax, ax
0x1800079ce  mov     [rcx+68h], eax
0x1800079d1  jmp     short loc_1800079E9
0x1800079d3  mov     [rcx+68h], r15d
0x1800079d7  jmp     short loc_1800079E9
0x1800079d9  mov     rax, gs:30h
0x1800079e2  mov     dword ptr [rax+68h], 57h ; 'W'
0x1800079e9  lea     rcx, [rsp+290h+FileName]; lpFileName
0x1800079ee  call    cs:__imp_GetFileAttributesW
0x1800079f5  nop     dword ptr [rax+rax+00h]
0x1800079fa  cmp     eax, 0FFFFFFFFh
0x1800079fd  jz      loc_180007ADA
0x180007a03  mov     [rsp+290h+hTemplateFile], r15; hTemplateFile
0x180007a08  lea     rcx, [rsp+290h+FileName]; lpFileName
0x180007a0d  mov     [rsp+290h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180007a15  xor     r9d, r9d; lpSecurityAttributes
0x180007a18  mov     r8d, esi; dwShareMode
0x180007a1b  mov     [rsp+290h+dwCreationDisposition], 3; dwCreationDisposition
0x180007a23  mov     edx, 80000000h; dwDesiredAccess
0x180007a28  call    cs:__imp_CreateFileW
0x180007a2f  nop     dword ptr [rax+rax+00h]
0x180007a34  mov     rdi, rax
0x180007a37  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180007a3b  jz      loc_180007ADA
0x180007a41  lea     rdx, [rsp+290h+FileSize]; lpFileSize
0x180007a46  mov     rcx, rax; hFile
0x180007a49  call    cs:__imp_GetFileSizeEx
0x180007a50  nop     dword ptr [rax+rax+00h]
0x180007a55  test    eax, eax
0x180007a57  jz      short loc_180007ABB
0x180007a59  mov     r9d, dword ptr [rsp+290h+FileSize]
0x180007a5e  lea     rdx, aClientUnattend; "CLIENT_UNATTEND"
0x180007a65  mov     ebx, 8
0x180007a6a  mov     [rsp+290h+dwCreationDisposition], r15d
0x180007a6f  mov     rcx, r14
0x180007a72  lea     r8d, [rbx+38h]
0x180007a76  call    cs:__imp_WdsCpParameterAdd
0x180007a7d  nop     dword ptr [rax+rax+00h]
0x180007a82  test    rax, rax
0x180007a85  jz      short loc_180007AC9
0x180007a87  mov     r8d, dword ptr [rsp+290h+FileSize]; nNumberOfBytesToRead
0x180007a8c  lea     r9, [rsp+290h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180007a91  mov     rdx, rax; lpBuffer
0x180007a94  mov     qword ptr [rsp+290h+dwCreationDisposition], r15; lpOverlapped
0x180007a99  mov     rcx, rdi; hFile
0x180007a9c  call    cs:__imp_ReadFile
0x180007aa3  nop     dword ptr [rax+rax+00h]
0x180007aa8  test    eax, eax
0x180007aaa  jz      short loc_180007ABB
0x180007aac  mov     eax, dword ptr [rsp+290h+FileSize]
0x180007ab0  cmp     [rsp+290h+NumberOfBytesRead], eax
0x180007ab4  jnz     short loc_180007ABB
0x180007ab6  mov     ebx, r15d
0x180007ab9  jmp     short loc_180007AC9
0x180007abb  call    cs:__imp_GetLastError
0x180007ac2  nop     dword ptr [rax+rax+00h]
0x180007ac7  mov     ebx, eax
0x180007ac9  mov     rcx, rdi; hObject
0x180007acc  call    cs:__imp_CloseHandle
0x180007ad3  nop     dword ptr [rax+rax+00h]
0x180007ad8  jmp     short loc_180007AE8
0x180007ada  call    cs:__imp_GetLastError
0x180007ae1  nop     dword ptr [rax+rax+00h]
0x180007ae6  mov     ebx, eax
0x180007ae8  mov     eax, ebx
0x180007aea  mov     rcx, [rbp+190h+var_30]
0x180007af1  xor     rcx, rsp; StackCookie
0x180007af4  call    __security_check_cookie
0x180007af9  mov     rbx, [rsp+290h+arg_10]
0x180007b01  add     rsp, 270h
0x180007b08  pop     r15
0x180007b0a  pop     r14
0x180007b0c  pop     rdi
0x180007b0d  pop     rsi
0x180007b0e  pop     rbp
0x180007b0f  retn
```
